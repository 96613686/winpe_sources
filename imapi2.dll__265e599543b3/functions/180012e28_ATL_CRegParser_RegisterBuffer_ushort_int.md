# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x180012e28`
- end: `0x180012f95`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `365`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180012f9c`

## callees

- `0x180012760`
- `0x180012918`
- `0x180012e28`
- `0x180013134`
- `0x180013980`
- `0x180049880`
- `0x180049940`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180012f6b`
- `ole32!CoTaskMemFree` at `0x180012f6b`
- `KERNEL32!lstrcmpiW` at `0x180012ec4`
- `KERNEL32!lstrcmpiW` at `0x180012ec4`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterBuffer(const wchar_t **this, unsigned __int16 *a2, int a3)
{
  __int64 result; // rax
  int Token; // ebx
  void *v7; // rbp
  unsigned int i; // ebx
  HKEY v9; // rsi
  const wchar_t *v10; // r14
  LPVOID pv; // [rsp+30h] [rbp-2058h] BYREF
  WCHAR String1[4096]; // [rsp+40h] [rbp-2048h] BYREF

  pv = 0;
  result = ATL::CRegParser::PreProcessBuffer(this, a2, &pv);
  Token = result;
  if ( (int)result >= 0 )
  {
    v7 = pv;
    *this = (const wchar_t *)pv;
    while ( **this )
    {
      Token = ATL::CRegParser::NextToken((ATL::CRegParser *)this, String1);
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
      Token = ATL::CRegParser::NextToken((ATL::CRegParser *)this, String1);
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
        v10 = *this;
        Token = ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, String1, v9, a3, 0);
        if ( Token < 0 )
        {
          *this = v10;
          ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, String1, v9, 0, 0);
          break;
        }
      }
      else
      {
        Token = ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, String1, v9, 0, 0);
        if ( Token < 0 )
          break;
      }
      ATL::CRegParser::SkipWhiteSpace((ATL::CRegParser *)this);
    }
    CoTaskMemFree(v7);
    return (unsigned int)Token;
  }
  return result;
}

```

## disassembly

```asm
0x180012e28  push    rbx
0x180012e2a  push    rbp
0x180012e2b  push    rsi
0x180012e2c  push    rdi
0x180012e2d  push    r13
0x180012e2f  push    r14
0x180012e31  push    r15
0x180012e33  mov     eax, 2050h
0x180012e38  call    _alloca_probe
0x180012e3d  sub     rsp, rax
0x180012e40  mov     rax, cs:__security_cookie
0x180012e47  xor     rax, rsp
0x180012e4a  mov     [rsp+2088h+var_48], rax
0x180012e52  mov     r15d, r8d
0x180012e55  mov     [rsp+2088h+pv], 0
0x180012e5e  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x180012e63  mov     rdi, rcx
0x180012e66  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x180012e6b  mov     ebx, eax
0x180012e6d  test    eax, eax
0x180012e6f  js      loc_180012F73
0x180012e75  mov     rbp, [rsp+2088h+pv]
0x180012e7a  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x180012e81  mov     [rdi], rbp
0x180012e84  mov     rcx, [rdi]
0x180012e87  xor     eax, eax
0x180012e89  cmp     ax, [rcx]
0x180012e8c  jz      loc_180012F68
0x180012e92  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180012e97  mov     rcx, rdi; this
0x180012e9a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180012e9f  mov     ebx, eax
0x180012ea1  test    eax, eax
0x180012ea3  js      loc_180012F68
0x180012ea9  xor     ebx, ebx
0x180012eab  cmp     ebx, 0Eh
0x180012eae  jnb     loc_180012F63
0x180012eb4  movsxd  rsi, ebx
0x180012eb7  lea     rcx, [rsp+2088h+String1]; lpString1
0x180012ebc  add     rsi, rsi
0x180012ebf  mov     rdx, [r13+rsi*8+0]; lpString2
0x180012ec4  call    cs:__imp_lstrcmpiW
0x180012eca  test    eax, eax
0x180012ecc  jz      short loc_180012ED2
0x180012ece  inc     ebx
0x180012ed0  jmp     short loc_180012EAB
0x180012ed2  mov     rsi, [r13+rsi*8+8]
0x180012ed7  test    rsi, rsi
0x180012eda  jz      loc_180012F63
0x180012ee0  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180012ee5  mov     rcx, rdi; this
0x180012ee8  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180012eed  mov     ebx, eax
0x180012eef  test    eax, eax
0x180012ef1  js      short loc_180012F68
0x180012ef3  mov     eax, 7Bh ; '{'
0x180012ef8  cmp     ax, [rsp+2088h+String1]
0x180012efd  jnz     short loc_180012F63
0x180012eff  mov     [rsp+2088h+var_2068], 0; int
0x180012f07  mov     r8, rsi; HKEY
0x180012f0a  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180012f0f  mov     rcx, rdi; this
0x180012f12  test    r15d, r15d
0x180012f15  jz      short loc_180012F48
0x180012f17  mov     r14, [rdi]
0x180012f1a  mov     r9d, r15d; int
0x180012f1d  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180012f22  mov     ebx, eax
0x180012f24  test    eax, eax
0x180012f26  jns     short loc_180012F56
0x180012f28  xor     r9d, r9d; int
0x180012f2b  mov     [rdi], r14
0x180012f2e  mov     r8, rsi; HKEY
0x180012f31  mov     [rsp+2088h+var_2068], 0; int
0x180012f39  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180012f3e  mov     rcx, rdi; this
0x180012f41  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180012f46  jmp     short loc_180012F68
0x180012f48  xor     r9d, r9d; int
0x180012f4b  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180012f50  mov     ebx, eax
0x180012f52  test    eax, eax
0x180012f54  js      short loc_180012F68
0x180012f56  mov     rcx, rdi; this
0x180012f59  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180012f5e  jmp     loc_180012E84
0x180012f63  mov     ebx, 80020009h
0x180012f68  mov     rcx, rbp; pv
0x180012f6b  call    cs:__imp_CoTaskMemFree
0x180012f71  mov     eax, ebx
0x180012f73  mov     rcx, [rsp+2088h+var_48]
0x180012f7b  xor     rcx, rsp; StackCookie
0x180012f7e  call    __security_check_cookie
0x180012f83  add     rsp, 2050h
0x180012f8a  pop     r15
0x180012f8c  pop     r14
0x180012f8e  pop     r13
0x180012f90  pop     rdi
0x180012f91  pop     rsi
0x180012f92  pop     rbp
0x180012f93  pop     rbx
0x180012f94  retn
```
