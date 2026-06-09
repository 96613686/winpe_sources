# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x180031ecc`
- end: `0x180032039`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `365`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180032040`

## callees

- `0x18002b530`
- `0x180031720`
- `0x1800318d8`
- `0x180031ecc`
- `0x180032298`
- `0x180033130`
- `0x180081700`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180031f68`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180031f68`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003200f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003200f`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterBuffer(ATL::CRegParser *this, unsigned __int16 *a2, int a3)
{
  __int64 result; // rax
  int Token; // ebx
  void *v7; // rbp
  unsigned int i; // ebx
  HKEY v9; // rsi
  __int64 v10; // r14
  LPVOID pv; // [rsp+30h] [rbp-2058h] BYREF
  WCHAR String1[4096]; // [rsp+40h] [rbp-2048h] BYREF

  pv = 0;
  result = ATL::CRegParser::PreProcessBuffer(this, a2, (unsigned __int16 **)&pv);
  Token = result;
  if ( (int)result >= 0 )
  {
    v7 = pv;
    *(_QWORD *)this = pv;
    while ( **(_WORD **)this )
    {
      Token = ATL::CRegParser::NextToken(this, String1);
      if ( Token < 0 )
        break;
      for ( i = 0; ; ++i )
      {
        if ( i >= 0xE )
          goto LABEL_17;
        if ( !lstrcmpiW(String1, (&`ATL::CRegParser::HKeyFromString'::`2'::map)[2 * (int)i]) )
          break;
      }
      v9 = (HKEY)*(&`ATL::CRegParser::HKeyFromString'::`2'::map + 2 * (int)i + 1);
      if ( !v9 )
        goto LABEL_17;
      Token = ATL::CRegParser::NextToken(this, String1);
      if ( Token < 0 )
        break;
      if ( String1[0] != 123 )
      {
LABEL_17:
        Token = -2147352567;
        break;
      }
      if ( a3 )
      {
        v10 = *(_QWORD *)this;
        Token = ATL::CRegParser::RegisterSubkeys(this, String1, v9, a3, 0);
        if ( Token < 0 )
        {
          *(_QWORD *)this = v10;
          ATL::CRegParser::RegisterSubkeys(this, String1, v9, 0, 0);
          break;
        }
      }
      else
      {
        Token = ATL::CRegParser::RegisterSubkeys(this, String1, v9, 0, 0);
        if ( Token < 0 )
          break;
      }
      ATL::CRegParser::SkipWhiteSpace(this);
    }
    CoTaskMemFree(v7);
    return (unsigned int)Token;
  }
  return result;
}

```

## disassembly

```asm
0x180031ecc  push    rbx
0x180031ece  push    rbp
0x180031ecf  push    rsi
0x180031ed0  push    rdi
0x180031ed1  push    r13
0x180031ed3  push    r14
0x180031ed5  push    r15
0x180031ed7  mov     eax, 2050h
0x180031edc  call    _alloca_probe
0x180031ee1  sub     rsp, rax
0x180031ee4  mov     rax, cs:__security_cookie
0x180031eeb  xor     rax, rsp
0x180031eee  mov     [rsp+2088h+var_48], rax
0x180031ef6  mov     r15d, r8d
0x180031ef9  mov     [rsp+2088h+pv], 0
0x180031f02  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x180031f07  mov     rdi, rcx
0x180031f0a  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x180031f0f  mov     ebx, eax
0x180031f11  test    eax, eax
0x180031f13  js      loc_180032017
0x180031f19  mov     rbp, [rsp+2088h+pv]
0x180031f1e  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x180031f25  mov     [rdi], rbp
0x180031f28  mov     rcx, [rdi]
0x180031f2b  xor     eax, eax
0x180031f2d  cmp     ax, [rcx]
0x180031f30  jz      loc_18003200C
0x180031f36  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180031f3b  mov     rcx, rdi; this
0x180031f3e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180031f43  mov     ebx, eax
0x180031f45  test    eax, eax
0x180031f47  js      loc_18003200C
0x180031f4d  xor     ebx, ebx
0x180031f4f  cmp     ebx, 0Eh
0x180031f52  jnb     loc_180032007
0x180031f58  movsxd  rsi, ebx
0x180031f5b  lea     rcx, [rsp+2088h+String1]; lpString1
0x180031f60  add     rsi, rsi
0x180031f63  mov     rdx, [r13+rsi*8+0]; lpString2
0x180031f68  call    cs:__imp_lstrcmpiW
0x180031f6e  test    eax, eax
0x180031f70  jz      short loc_180031F76
0x180031f72  inc     ebx
0x180031f74  jmp     short loc_180031F4F
0x180031f76  mov     rsi, [r13+rsi*8+8]
0x180031f7b  test    rsi, rsi
0x180031f7e  jz      loc_180032007
0x180031f84  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180031f89  mov     rcx, rdi; this
0x180031f8c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180031f91  mov     ebx, eax
0x180031f93  test    eax, eax
0x180031f95  js      short loc_18003200C
0x180031f97  mov     eax, 7Bh ; '{'
0x180031f9c  cmp     ax, [rsp+2088h+String1]
0x180031fa1  jnz     short loc_180032007
0x180031fa3  mov     [rsp+2088h+var_2068], 0; int
0x180031fab  mov     r8, rsi; HKEY
0x180031fae  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180031fb3  mov     rcx, rdi; this
0x180031fb6  test    r15d, r15d
0x180031fb9  jz      short loc_180031FEC
0x180031fbb  mov     r14, [rdi]
0x180031fbe  mov     r9d, r15d; int
0x180031fc1  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180031fc6  mov     ebx, eax
0x180031fc8  test    eax, eax
0x180031fca  jns     short loc_180031FFA
0x180031fcc  xor     r9d, r9d; int
0x180031fcf  mov     [rdi], r14
0x180031fd2  mov     r8, rsi; HKEY
0x180031fd5  mov     [rsp+2088h+var_2068], 0; int
0x180031fdd  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180031fe2  mov     rcx, rdi; this
0x180031fe5  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180031fea  jmp     short loc_18003200C
0x180031fec  xor     r9d, r9d; int
0x180031fef  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180031ff4  mov     ebx, eax
0x180031ff6  test    eax, eax
0x180031ff8  js      short loc_18003200C
0x180031ffa  mov     rcx, rdi; this
0x180031ffd  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180032002  jmp     loc_180031F28
0x180032007  mov     ebx, 80020009h
0x18003200c  mov     rcx, rbp; pv
0x18003200f  call    cs:__imp_CoTaskMemFree
0x180032015  mov     eax, ebx
0x180032017  mov     rcx, [rsp+2088h+var_48]
0x18003201f  xor     rcx, rsp; StackCookie
0x180032022  call    __security_check_cookie
0x180032027  add     rsp, 2050h
0x18003202e  pop     r15
0x180032030  pop     r14
0x180032032  pop     r13
0x180032034  pop     rdi
0x180032035  pop     rsi
0x180032036  pop     rbp
0x180032037  pop     rbx
0x180032038  retn
```
