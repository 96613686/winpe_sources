# ATL::CRegParser::RegisterBuffer(wchar_t *,int)

- ea: `0x18001024c`
- end: `0x1800103c6`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEA_WH@Z`
- size: `378`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, wchar_t *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800103cc`

## callees

- `0x180002af0`
- `0x18000fc34`
- `0x18000fe68`
- `0x18001024c`
- `0x1800105a0`
- `0x180010ca0`
- `0x1800350c0`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800102e8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800102e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010395`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010395`

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
0x18001024c  push    rbx
0x18001024e  push    rbp
0x18001024f  push    rsi
0x180010250  push    rdi
0x180010251  push    r13
0x180010253  push    r14
0x180010255  push    r15
0x180010257  mov     eax, 2050h
0x18001025c  call    _alloca_probe
0x180010261  sub     rsp, rax
0x180010264  mov     rax, cs:__security_cookie
0x18001026b  xor     rax, rsp
0x18001026e  mov     [rsp+2088h+var_48], rax
0x180010276  mov     r15d, r8d
0x180010279  mov     [rsp+2088h+pv], 0
0x180010282  lea     r8, [rsp+2088h+pv]; wchar_t **
0x180010287  mov     rdi, rcx
0x18001028a  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEA_WPEAPEA_W@Z; ATL::CRegParser::PreProcessBuffer(wchar_t *,wchar_t * *)
0x18001028f  mov     ebx, eax
0x180010291  test    eax, eax
0x180010293  js      loc_1800103A3
0x180010299  mov     rbp, [rsp+2088h+pv]
0x18001029e  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEA_W@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(wchar_t *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(wchar_t *)'::`2'::map
0x1800102a5  mov     [rdi], rbp
0x1800102a8  mov     rcx, [rdi]
0x1800102ab  xor     eax, eax
0x1800102ad  cmp     ax, [rcx]
0x1800102b0  jz      loc_180010392
0x1800102b6  lea     rdx, [rsp+2088h+String1]; wchar_t *
0x1800102bb  mov     rcx, rdi; this
0x1800102be  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x1800102c3  mov     ebx, eax
0x1800102c5  test    eax, eax
0x1800102c7  js      loc_180010392
0x1800102cd  xor     ebx, ebx
0x1800102cf  cmp     ebx, 0Eh
0x1800102d2  jnb     loc_18001038D
0x1800102d8  movsxd  rsi, ebx
0x1800102db  lea     rcx, [rsp+2088h+String1]; lpString1
0x1800102e0  add     rsi, rsi
0x1800102e3  mov     rdx, [r13+rsi*8+0]; lpString2
0x1800102e8  call    cs:__imp_lstrcmpiW
0x1800102ef  nop     dword ptr [rax+rax+00h]
0x1800102f4  test    eax, eax
0x1800102f6  jz      short loc_1800102FC
0x1800102f8  inc     ebx
0x1800102fa  jmp     short loc_1800102CF
0x1800102fc  mov     rsi, [r13+rsi*8+8]
0x180010301  test    rsi, rsi
0x180010304  jz      loc_18001038D
0x18001030a  lea     rdx, [rsp+2088h+String1]; wchar_t *
0x18001030f  mov     rcx, rdi; this
0x180010312  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x180010317  mov     ebx, eax
0x180010319  test    eax, eax
0x18001031b  js      short loc_180010392
0x18001031d  mov     eax, 7Bh ; '{'
0x180010322  cmp     ax, [rsp+2088h+String1]
0x180010327  jnz     short loc_18001038D
0x180010329  mov     [rsp+2088h+var_2068], 0; int
0x180010331  mov     r8, rsi; HKEY
0x180010334  lea     rdx, [rsp+2088h+String1]; wchar_t *
0x180010339  mov     rcx, rdi; this
0x18001033c  test    r15d, r15d
0x18001033f  jz      short loc_180010372
0x180010341  mov     r14, [rdi]
0x180010344  mov     r9d, r15d; int
0x180010347  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x18001034c  mov     ebx, eax
0x18001034e  test    eax, eax
0x180010350  jns     short loc_180010380
0x180010352  xor     r9d, r9d; int
0x180010355  mov     [rdi], r14
0x180010358  mov     r8, rsi; HKEY
0x18001035b  mov     [rsp+2088h+var_2068], 0; int
0x180010363  lea     rdx, [rsp+2088h+String1]; wchar_t *
0x180010368  mov     rcx, rdi; this
0x18001036b  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x180010370  jmp     short loc_180010392
0x180010372  xor     r9d, r9d; int
0x180010375  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x18001037a  mov     ebx, eax
0x18001037c  test    eax, eax
0x18001037e  js      short loc_180010392
0x180010380  mov     rcx, rdi; this
0x180010383  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180010388  jmp     loc_1800102A8
0x18001038d  mov     ebx, 80020009h
0x180010392  mov     rcx, rbp; pv
0x180010395  call    cs:__imp_CoTaskMemFree
0x18001039c  nop     dword ptr [rax+rax+00h]
0x1800103a1  mov     eax, ebx
0x1800103a3  mov     rcx, [rsp+2088h+var_48]
0x1800103ab  xor     rcx, rsp; StackCookie
0x1800103ae  call    __security_check_cookie
0x1800103b3  add     rsp, 2050h
0x1800103ba  pop     r15
0x1800103bc  pop     r14
0x1800103be  pop     r13
0x1800103c0  pop     rdi
0x1800103c1  pop     rsi
0x1800103c2  pop     rbp
0x1800103c3  pop     rbx
0x1800103c4  retn
```
