# ATL::CRegParser::RegisterBuffer(wchar_t *,int)

- ea: `0x18001a418`
- end: `0x18001a585`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEA_WH@Z`
- size: `365`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, wchar_t *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001a58c`

## callees

- `0x18000fcd0`
- `0x180019a40`
- `0x180019e88`
- `0x18001a418`
- `0x18001a7d4`
- `0x18001b960`
- `0x180024dc0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a55b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a55b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001a4b4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001a4b4`

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
0x18001a418  push    rbx
0x18001a41a  push    rbp
0x18001a41b  push    rsi
0x18001a41c  push    rdi
0x18001a41d  push    r13
0x18001a41f  push    r14
0x18001a421  push    r15
0x18001a423  mov     eax, 2050h
0x18001a428  call    _alloca_probe
0x18001a42d  sub     rsp, rax
0x18001a430  mov     rax, cs:__security_cookie
0x18001a437  xor     rax, rsp
0x18001a43a  mov     [rsp+2088h+var_48], rax
0x18001a442  mov     r15d, r8d
0x18001a445  mov     [rsp+2088h+pv], 0
0x18001a44e  lea     r8, [rsp+2088h+pv]; wchar_t **
0x18001a453  mov     rdi, rcx
0x18001a456  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEA_WPEAPEA_W@Z; ATL::CRegParser::PreProcessBuffer(wchar_t *,wchar_t * *)
0x18001a45b  mov     ebx, eax
0x18001a45d  test    eax, eax
0x18001a45f  js      loc_18001A563
0x18001a465  mov     rbp, [rsp+2088h+pv]
0x18001a46a  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEA_W@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(wchar_t *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(wchar_t *)'::`2'::map
0x18001a471  mov     [rdi], rbp
0x18001a474  mov     rcx, [rdi]
0x18001a477  xor     eax, eax
0x18001a479  cmp     ax, [rcx]
0x18001a47c  jz      loc_18001A558
0x18001a482  lea     rdx, [rsp+2088h+String1]; wchar_t *
0x18001a487  mov     rcx, rdi; this
0x18001a48a  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18001a48f  mov     ebx, eax
0x18001a491  test    eax, eax
0x18001a493  js      loc_18001A558
0x18001a499  xor     ebx, ebx
0x18001a49b  cmp     ebx, 0Eh
0x18001a49e  jnb     loc_18001A553
0x18001a4a4  movsxd  rsi, ebx
0x18001a4a7  lea     rcx, [rsp+2088h+String1]; lpString1
0x18001a4ac  add     rsi, rsi
0x18001a4af  mov     rdx, [r13+rsi*8+0]; lpString2
0x18001a4b4  call    cs:__imp_lstrcmpiW
0x18001a4ba  test    eax, eax
0x18001a4bc  jz      short loc_18001A4C2
0x18001a4be  inc     ebx
0x18001a4c0  jmp     short loc_18001A49B
0x18001a4c2  mov     rsi, [r13+rsi*8+8]
0x18001a4c7  test    rsi, rsi
0x18001a4ca  jz      loc_18001A553
0x18001a4d0  lea     rdx, [rsp+2088h+String1]; wchar_t *
0x18001a4d5  mov     rcx, rdi; this
0x18001a4d8  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18001a4dd  mov     ebx, eax
0x18001a4df  test    eax, eax
0x18001a4e1  js      short loc_18001A558
0x18001a4e3  mov     eax, 7Bh ; '{'
0x18001a4e8  cmp     ax, [rsp+2088h+String1]
0x18001a4ed  jnz     short loc_18001A553
0x18001a4ef  mov     [rsp+2088h+var_2068], 0; int
0x18001a4f7  mov     r8, rsi; HKEY
0x18001a4fa  lea     rdx, [rsp+2088h+String1]; wchar_t *
0x18001a4ff  mov     rcx, rdi; this
0x18001a502  test    r15d, r15d
0x18001a505  jz      short loc_18001A538
0x18001a507  mov     r14, [rdi]
0x18001a50a  mov     r9d, r15d; int
0x18001a50d  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x18001a512  mov     ebx, eax
0x18001a514  test    eax, eax
0x18001a516  jns     short loc_18001A546
0x18001a518  xor     r9d, r9d; int
0x18001a51b  mov     [rdi], r14
0x18001a51e  mov     r8, rsi; HKEY
0x18001a521  mov     [rsp+2088h+var_2068], 0; int
0x18001a529  lea     rdx, [rsp+2088h+String1]; wchar_t *
0x18001a52e  mov     rcx, rdi; this
0x18001a531  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x18001a536  jmp     short loc_18001A558
0x18001a538  xor     r9d, r9d; int
0x18001a53b  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x18001a540  mov     ebx, eax
0x18001a542  test    eax, eax
0x18001a544  js      short loc_18001A558
0x18001a546  mov     rcx, rdi; this
0x18001a549  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18001a54e  jmp     loc_18001A474
0x18001a553  mov     ebx, 80020009h
0x18001a558  mov     rcx, rbp; pv
0x18001a55b  call    cs:__imp_CoTaskMemFree
0x18001a561  mov     eax, ebx
0x18001a563  mov     rcx, [rsp+2088h+var_48]
0x18001a56b  xor     rcx, rsp; StackCookie
0x18001a56e  call    __security_check_cookie
0x18001a573  add     rsp, 2050h
0x18001a57a  pop     r15
0x18001a57c  pop     r14
0x18001a57e  pop     r13
0x18001a580  pop     rdi
0x18001a581  pop     rsi
0x18001a582  pop     rbp
0x18001a583  pop     rbx
0x18001a584  retn
```
