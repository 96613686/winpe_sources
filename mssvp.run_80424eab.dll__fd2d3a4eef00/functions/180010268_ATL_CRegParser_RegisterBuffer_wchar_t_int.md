# ATL::CRegParser::RegisterBuffer(wchar_t *,int)

- ea: `0x180010268`
- end: `0x1800103d5`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEA_WH@Z`
- size: `365`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, wchar_t *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800103dc`

## callees

- `0x180006270`
- `0x18000e960`
- `0x18000eccc`
- `0x180010268`
- `0x180010624`
- `0x1800118b4`
- `0x180038ab0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800103ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800103ab`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180010304`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180010304`

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
0x180010268  push    rbx
0x18001026a  push    rbp
0x18001026b  push    rsi
0x18001026c  push    rdi
0x18001026d  push    r13
0x18001026f  push    r14
0x180010271  push    r15
0x180010273  mov     eax, 2050h
0x180010278  call    _alloca_probe
0x18001027d  sub     rsp, rax
0x180010280  mov     rax, cs:__security_cookie
0x180010287  xor     rax, rsp
0x18001028a  mov     [rsp+2088h+var_48], rax
0x180010292  mov     r15d, r8d
0x180010295  mov     [rsp+2088h+pv], 0
0x18001029e  lea     r8, [rsp+2088h+pv]; wchar_t **
0x1800102a3  mov     rdi, rcx
0x1800102a6  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEA_WPEAPEA_W@Z; ATL::CRegParser::PreProcessBuffer(wchar_t *,wchar_t * *)
0x1800102ab  mov     ebx, eax
0x1800102ad  test    eax, eax
0x1800102af  js      loc_1800103B3
0x1800102b5  mov     rbp, [rsp+2088h+pv]
0x1800102ba  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEA_W@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(wchar_t *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(wchar_t *)'::`2'::map
0x1800102c1  mov     [rdi], rbp
0x1800102c4  mov     rcx, [rdi]
0x1800102c7  xor     eax, eax
0x1800102c9  cmp     ax, [rcx]
0x1800102cc  jz      loc_1800103A8
0x1800102d2  lea     rdx, [rsp+2088h+String1]; wchar_t *
0x1800102d7  mov     rcx, rdi; this
0x1800102da  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x1800102df  mov     ebx, eax
0x1800102e1  test    eax, eax
0x1800102e3  js      loc_1800103A8
0x1800102e9  xor     ebx, ebx
0x1800102eb  cmp     ebx, 0Eh
0x1800102ee  jnb     loc_1800103A3
0x1800102f4  movsxd  rsi, ebx
0x1800102f7  lea     rcx, [rsp+2088h+String1]; lpString1
0x1800102fc  add     rsi, rsi
0x1800102ff  mov     rdx, [r13+rsi*8+0]; lpString2
0x180010304  call    cs:__imp_lstrcmpiW
0x18001030a  test    eax, eax
0x18001030c  jz      short loc_180010312
0x18001030e  inc     ebx
0x180010310  jmp     short loc_1800102EB
0x180010312  mov     rsi, [r13+rsi*8+8]
0x180010317  test    rsi, rsi
0x18001031a  jz      loc_1800103A3
0x180010320  lea     rdx, [rsp+2088h+String1]; wchar_t *
0x180010325  mov     rcx, rdi; this
0x180010328  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18001032d  mov     ebx, eax
0x18001032f  test    eax, eax
0x180010331  js      short loc_1800103A8
0x180010333  mov     eax, 7Bh ; '{'
0x180010338  cmp     ax, [rsp+2088h+String1]
0x18001033d  jnz     short loc_1800103A3
0x18001033f  mov     [rsp+2088h+var_2068], 0; int
0x180010347  mov     r8, rsi; HKEY
0x18001034a  lea     rdx, [rsp+2088h+String1]; wchar_t *
0x18001034f  mov     rcx, rdi; this
0x180010352  test    r15d, r15d
0x180010355  jz      short loc_180010388
0x180010357  mov     r14, [rdi]
0x18001035a  mov     r9d, r15d; int
0x18001035d  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x180010362  mov     ebx, eax
0x180010364  test    eax, eax
0x180010366  jns     short loc_180010396
0x180010368  xor     r9d, r9d; int
0x18001036b  mov     [rdi], r14
0x18001036e  mov     r8, rsi; HKEY
0x180010371  mov     [rsp+2088h+var_2068], 0; int
0x180010379  lea     rdx, [rsp+2088h+String1]; wchar_t *
0x18001037e  mov     rcx, rdi; this
0x180010381  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x180010386  jmp     short loc_1800103A8
0x180010388  xor     r9d, r9d; int
0x18001038b  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x180010390  mov     ebx, eax
0x180010392  test    eax, eax
0x180010394  js      short loc_1800103A8
0x180010396  mov     rcx, rdi; this
0x180010399  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18001039e  jmp     loc_1800102C4
0x1800103a3  mov     ebx, 80020009h
0x1800103a8  mov     rcx, rbp; pv
0x1800103ab  call    cs:__imp_CoTaskMemFree
0x1800103b1  mov     eax, ebx
0x1800103b3  mov     rcx, [rsp+2088h+var_48]
0x1800103bb  xor     rcx, rsp; StackCookie
0x1800103be  call    __security_check_cookie
0x1800103c3  add     rsp, 2050h
0x1800103ca  pop     r15
0x1800103cc  pop     r14
0x1800103ce  pop     r13
0x1800103d0  pop     rdi
0x1800103d1  pop     rsi
0x1800103d2  pop     rbp
0x1800103d3  pop     rbx
0x1800103d4  retn
```
