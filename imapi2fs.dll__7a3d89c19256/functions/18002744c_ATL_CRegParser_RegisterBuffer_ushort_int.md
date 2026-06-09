# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x18002744c`
- end: `0x1800275b9`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `365`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x1800275c0`

## callees

- `0x180026f14`
- `0x1800270cc`
- `0x18002744c`
- `0x180027800`
- `0x180027ed4`
- `0x180081750`
- `0x180081810`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002758f`
- `ole32!CoTaskMemFree` at `0x18002758f`
- `KERNEL32!lstrcmpiW` at `0x1800274e8`
- `KERNEL32!lstrcmpiW` at `0x1800274e8`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterBuffer(LPCWSTR *this, unsigned __int16 *a2, int a3)
{
  __int64 result; // rax
  int Token; // ebx
  void *v7; // rbp
  unsigned int i; // ebx
  HKEY v9; // rsi
  LPCWSTR v10; // r14
  LPVOID pv; // [rsp+30h] [rbp-2058h] BYREF
  WCHAR String1[4096]; // [rsp+40h] [rbp-2048h] BYREF

  pv = 0;
  result = ATL::CRegParser::PreProcessBuffer(this, a2, (unsigned __int16 **)&pv);
  Token = result;
  if ( (int)result >= 0 )
  {
    v7 = pv;
    *this = (LPCWSTR)pv;
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
0x18002744c  push    rbx
0x18002744e  push    rbp
0x18002744f  push    rsi
0x180027450  push    rdi
0x180027451  push    r13
0x180027453  push    r14
0x180027455  push    r15
0x180027457  mov     eax, 2050h
0x18002745c  call    _alloca_probe
0x180027461  sub     rsp, rax
0x180027464  mov     rax, cs:__security_cookie
0x18002746b  xor     rax, rsp
0x18002746e  mov     [rsp+2088h+var_48], rax
0x180027476  mov     r15d, r8d
0x180027479  mov     [rsp+2088h+pv], 0
0x180027482  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x180027487  mov     rdi, rcx
0x18002748a  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x18002748f  mov     ebx, eax
0x180027491  test    eax, eax
0x180027493  js      loc_180027597
0x180027499  mov     rbp, [rsp+2088h+pv]
0x18002749e  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x1800274a5  mov     [rdi], rbp
0x1800274a8  mov     rcx, [rdi]
0x1800274ab  xor     eax, eax
0x1800274ad  cmp     ax, [rcx]
0x1800274b0  jz      loc_18002758C
0x1800274b6  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800274bb  mov     rcx, rdi; this
0x1800274be  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800274c3  mov     ebx, eax
0x1800274c5  test    eax, eax
0x1800274c7  js      loc_18002758C
0x1800274cd  xor     ebx, ebx
0x1800274cf  cmp     ebx, 0Eh
0x1800274d2  jnb     loc_180027587
0x1800274d8  movsxd  rsi, ebx
0x1800274db  lea     rcx, [rsp+2088h+String1]; lpString1
0x1800274e0  add     rsi, rsi
0x1800274e3  mov     rdx, [r13+rsi*8+0]; lpString2
0x1800274e8  call    cs:__imp_lstrcmpiW
0x1800274ee  test    eax, eax
0x1800274f0  jz      short loc_1800274F6
0x1800274f2  inc     ebx
0x1800274f4  jmp     short loc_1800274CF
0x1800274f6  mov     rsi, [r13+rsi*8+8]
0x1800274fb  test    rsi, rsi
0x1800274fe  jz      loc_180027587
0x180027504  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180027509  mov     rcx, rdi; this
0x18002750c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180027511  mov     ebx, eax
0x180027513  test    eax, eax
0x180027515  js      short loc_18002758C
0x180027517  mov     eax, 7Bh ; '{'
0x18002751c  cmp     ax, [rsp+2088h+String1]
0x180027521  jnz     short loc_180027587
0x180027523  mov     [rsp+2088h+var_2068], 0; int
0x18002752b  mov     r8, rsi; HKEY
0x18002752e  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180027533  mov     rcx, rdi; this
0x180027536  test    r15d, r15d
0x180027539  jz      short loc_18002756C
0x18002753b  mov     r14, [rdi]
0x18002753e  mov     r9d, r15d; int
0x180027541  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180027546  mov     ebx, eax
0x180027548  test    eax, eax
0x18002754a  jns     short loc_18002757A
0x18002754c  xor     r9d, r9d; int
0x18002754f  mov     [rdi], r14
0x180027552  mov     r8, rsi; HKEY
0x180027555  mov     [rsp+2088h+var_2068], 0; int
0x18002755d  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180027562  mov     rcx, rdi; this
0x180027565  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18002756a  jmp     short loc_18002758C
0x18002756c  xor     r9d, r9d; int
0x18002756f  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180027574  mov     ebx, eax
0x180027576  test    eax, eax
0x180027578  js      short loc_18002758C
0x18002757a  mov     rcx, rdi; this
0x18002757d  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180027582  jmp     loc_1800274A8
0x180027587  mov     ebx, 80020009h
0x18002758c  mov     rcx, rbp; pv
0x18002758f  call    cs:__imp_CoTaskMemFree
0x180027595  mov     eax, ebx
0x180027597  mov     rcx, [rsp+2088h+var_48]
0x18002759f  xor     rcx, rsp; StackCookie
0x1800275a2  call    __security_check_cookie
0x1800275a7  add     rsp, 2050h
0x1800275ae  pop     r15
0x1800275b0  pop     r14
0x1800275b2  pop     r13
0x1800275b4  pop     rdi
0x1800275b5  pop     rsi
0x1800275b6  pop     rbp
0x1800275b7  pop     rbx
0x1800275b8  retn
```
