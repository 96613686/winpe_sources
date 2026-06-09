# ATL::CRegParser::RegisterBuffer(wchar_t *,int)

- ea: `0x18001043c`
- end: `0x1800105a9`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEA_WH@Z`
- size: `365`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, wchar_t *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800105b0`

## callees

- `0x1800017a0`
- `0x18000fee4`
- `0x18001009c`
- `0x18001043c`
- `0x18001075c`
- `0x180010e24`
- `0x18002f450`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800104d8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800104d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001057f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001057f`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterBuffer(ATL::CRegParser *this, wchar_t *a2, int a3)
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
  result = ATL::CRegParser::PreProcessBuffer(this, a2, (wchar_t **)&pv);
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
0x18001043c  push    rbx
0x18001043e  push    rbp
0x18001043f  push    rsi
0x180010440  push    rdi
0x180010441  push    r13
0x180010443  push    r14
0x180010445  push    r15
0x180010447  mov     eax, 2050h
0x18001044c  call    _alloca_probe
0x180010451  sub     rsp, rax
0x180010454  mov     rax, cs:__security_cookie
0x18001045b  xor     rax, rsp
0x18001045e  mov     [rsp+2088h+var_48], rax
0x180010466  mov     r15d, r8d
0x180010469  mov     [rsp+2088h+pv], 0
0x180010472  lea     r8, [rsp+2088h+pv]; wchar_t **
0x180010477  mov     rdi, rcx
0x18001047a  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEA_WPEAPEA_W@Z; ATL::CRegParser::PreProcessBuffer(wchar_t *,wchar_t * *)
0x18001047f  mov     ebx, eax
0x180010481  test    eax, eax
0x180010483  js      loc_180010587
0x180010489  mov     rbp, [rsp+2088h+pv]
0x18001048e  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEA_W@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(wchar_t *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(wchar_t *)'::`2'::map
0x180010495  mov     [rdi], rbp
0x180010498  mov     rcx, [rdi]
0x18001049b  xor     eax, eax
0x18001049d  cmp     ax, [rcx]
0x1800104a0  jz      loc_18001057C
0x1800104a6  lea     rdx, [rsp+2088h+String1]; wchar_t *
0x1800104ab  mov     rcx, rdi; this
0x1800104ae  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x1800104b3  mov     ebx, eax
0x1800104b5  test    eax, eax
0x1800104b7  js      loc_18001057C
0x1800104bd  xor     ebx, ebx
0x1800104bf  cmp     ebx, 0Eh
0x1800104c2  jnb     loc_180010577
0x1800104c8  movsxd  rsi, ebx
0x1800104cb  lea     rcx, [rsp+2088h+String1]; lpString1
0x1800104d0  add     rsi, rsi
0x1800104d3  mov     rdx, [r13+rsi*8+0]; lpString2
0x1800104d8  call    cs:__imp_lstrcmpiW
0x1800104de  test    eax, eax
0x1800104e0  jz      short loc_1800104E6
0x1800104e2  inc     ebx
0x1800104e4  jmp     short loc_1800104BF
0x1800104e6  mov     rsi, [r13+rsi*8+8]
0x1800104eb  test    rsi, rsi
0x1800104ee  jz      loc_180010577
0x1800104f4  lea     rdx, [rsp+2088h+String1]; wchar_t *
0x1800104f9  mov     rcx, rdi; this
0x1800104fc  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x180010501  mov     ebx, eax
0x180010503  test    eax, eax
0x180010505  js      short loc_18001057C
0x180010507  mov     eax, 7Bh ; '{'
0x18001050c  cmp     ax, [rsp+2088h+String1]
0x180010511  jnz     short loc_180010577
0x180010513  mov     [rsp+2088h+var_2068], 0; int
0x18001051b  mov     r8, rsi; HKEY
0x18001051e  lea     rdx, [rsp+2088h+String1]; wchar_t *
0x180010523  mov     rcx, rdi; this
0x180010526  test    r15d, r15d
0x180010529  jz      short loc_18001055C
0x18001052b  mov     r14, [rdi]
0x18001052e  mov     r9d, r15d; int
0x180010531  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x180010536  mov     ebx, eax
0x180010538  test    eax, eax
0x18001053a  jns     short loc_18001056A
0x18001053c  xor     r9d, r9d; int
0x18001053f  mov     [rdi], r14
0x180010542  mov     r8, rsi; HKEY
0x180010545  mov     [rsp+2088h+var_2068], 0; int
0x18001054d  lea     rdx, [rsp+2088h+String1]; wchar_t *
0x180010552  mov     rcx, rdi; this
0x180010555  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x18001055a  jmp     short loc_18001057C
0x18001055c  xor     r9d, r9d; int
0x18001055f  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x180010564  mov     ebx, eax
0x180010566  test    eax, eax
0x180010568  js      short loc_18001057C
0x18001056a  mov     rcx, rdi; this
0x18001056d  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180010572  jmp     loc_180010498
0x180010577  mov     ebx, 80020009h
0x18001057c  mov     rcx, rbp; pv
0x18001057f  call    cs:__imp_CoTaskMemFree
0x180010585  mov     eax, ebx
0x180010587  mov     rcx, [rsp+2088h+var_48]
0x18001058f  xor     rcx, rsp; StackCookie
0x180010592  call    __security_check_cookie
0x180010597  add     rsp, 2050h
0x18001059e  pop     r15
0x1800105a0  pop     r14
0x1800105a2  pop     r13
0x1800105a4  pop     rdi
0x1800105a5  pop     rsi
0x1800105a6  pop     rbp
0x1800105a7  pop     rbx
0x1800105a8  retn
```
