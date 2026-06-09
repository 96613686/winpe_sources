# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x180028d8c`
- end: `0x180028ef9`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `365`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180028f00`

## callees

- `0x18001e1e0`
- `0x180027fc8`
- `0x180028180`
- `0x180028d8c`
- `0x1800290b0`
- `0x180029ed0`
- `0x1800620a0`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180028e28`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180028e28`
- `ole32!CoTaskMemFree` at `0x180028ecf`
- `ole32!CoTaskMemFree` at `0x180028ecf`

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
0x180028d8c  push    rbx
0x180028d8e  push    rbp
0x180028d8f  push    rsi
0x180028d90  push    rdi
0x180028d91  push    r13
0x180028d93  push    r14
0x180028d95  push    r15
0x180028d97  mov     eax, 2050h
0x180028d9c  call    _alloca_probe
0x180028da1  sub     rsp, rax
0x180028da4  mov     rax, cs:__security_cookie
0x180028dab  xor     rax, rsp
0x180028dae  mov     [rsp+2088h+var_48], rax
0x180028db6  mov     r15d, r8d
0x180028db9  mov     [rsp+2088h+pv], 0
0x180028dc2  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x180028dc7  mov     rdi, rcx
0x180028dca  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x180028dcf  mov     ebx, eax
0x180028dd1  test    eax, eax
0x180028dd3  js      loc_180028ED7
0x180028dd9  mov     rbp, [rsp+2088h+pv]
0x180028dde  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x180028de5  mov     [rdi], rbp
0x180028de8  mov     rcx, [rdi]
0x180028deb  xor     eax, eax
0x180028ded  cmp     ax, [rcx]
0x180028df0  jz      loc_180028ECC
0x180028df6  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180028dfb  mov     rcx, rdi; this
0x180028dfe  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180028e03  mov     ebx, eax
0x180028e05  test    eax, eax
0x180028e07  js      loc_180028ECC
0x180028e0d  xor     ebx, ebx
0x180028e0f  cmp     ebx, 0Eh
0x180028e12  jnb     loc_180028EC7
0x180028e18  movsxd  rsi, ebx
0x180028e1b  lea     rcx, [rsp+2088h+String1]; lpString1
0x180028e20  add     rsi, rsi
0x180028e23  mov     rdx, [r13+rsi*8+0]; lpString2
0x180028e28  call    cs:__imp_lstrcmpiW
0x180028e2e  test    eax, eax
0x180028e30  jz      short loc_180028E36
0x180028e32  inc     ebx
0x180028e34  jmp     short loc_180028E0F
0x180028e36  mov     rsi, [r13+rsi*8+8]
0x180028e3b  test    rsi, rsi
0x180028e3e  jz      loc_180028EC7
0x180028e44  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180028e49  mov     rcx, rdi; this
0x180028e4c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180028e51  mov     ebx, eax
0x180028e53  test    eax, eax
0x180028e55  js      short loc_180028ECC
0x180028e57  mov     eax, 7Bh ; '{'
0x180028e5c  cmp     ax, [rsp+2088h+String1]
0x180028e61  jnz     short loc_180028EC7
0x180028e63  mov     [rsp+2088h+var_2068], 0; int
0x180028e6b  mov     r8, rsi; HKEY
0x180028e6e  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180028e73  mov     rcx, rdi; this
0x180028e76  test    r15d, r15d
0x180028e79  jz      short loc_180028EAC
0x180028e7b  mov     r14, [rdi]
0x180028e7e  mov     r9d, r15d; int
0x180028e81  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180028e86  mov     ebx, eax
0x180028e88  test    eax, eax
0x180028e8a  jns     short loc_180028EBA
0x180028e8c  xor     r9d, r9d; int
0x180028e8f  mov     [rdi], r14
0x180028e92  mov     r8, rsi; HKEY
0x180028e95  mov     [rsp+2088h+var_2068], 0; int
0x180028e9d  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180028ea2  mov     rcx, rdi; this
0x180028ea5  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180028eaa  jmp     short loc_180028ECC
0x180028eac  xor     r9d, r9d; int
0x180028eaf  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180028eb4  mov     ebx, eax
0x180028eb6  test    eax, eax
0x180028eb8  js      short loc_180028ECC
0x180028eba  mov     rcx, rdi; this
0x180028ebd  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180028ec2  jmp     loc_180028DE8
0x180028ec7  mov     ebx, 80020009h
0x180028ecc  mov     rcx, rbp; pv
0x180028ecf  call    cs:__imp_CoTaskMemFree
0x180028ed5  mov     eax, ebx
0x180028ed7  mov     rcx, [rsp+2088h+var_48]
0x180028edf  xor     rcx, rsp; StackCookie
0x180028ee2  call    __security_check_cookie
0x180028ee7  add     rsp, 2050h
0x180028eee  pop     r15
0x180028ef0  pop     r14
0x180028ef2  pop     r13
0x180028ef4  pop     rdi
0x180028ef5  pop     rsi
0x180028ef6  pop     rbp
0x180028ef7  pop     rbx
0x180028ef8  retn
```
