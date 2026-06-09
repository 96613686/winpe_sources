# ATL::CRegParser::RegisterBuffer(wchar_t *,int)

- ea: `0x1400067cc`
- end: `0x140006939`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEA_WH@Z`
- size: `365`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, wchar_t *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x140006940`

## callees

- `0x140002070`
- `0x140005eb0`
- `0x1400063cc`
- `0x1400067cc`
- `0x140006af0`
- `0x140007548`
- `0x14005d370`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x140006868`
- `KERNEL32!lstrcmpiW` at `0x140006868`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000690f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000690f`

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
0x1400067cc  push    rbx
0x1400067ce  push    rbp
0x1400067cf  push    rsi
0x1400067d0  push    rdi
0x1400067d1  push    r13
0x1400067d3  push    r14
0x1400067d5  push    r15
0x1400067d7  mov     eax, 2050h
0x1400067dc  call    _alloca_probe
0x1400067e1  sub     rsp, rax
0x1400067e4  mov     rax, cs:__security_cookie
0x1400067eb  xor     rax, rsp
0x1400067ee  mov     [rsp+2088h+var_48], rax
0x1400067f6  mov     r15d, r8d
0x1400067f9  mov     [rsp+2088h+pv], 0
0x140006802  lea     r8, [rsp+2088h+pv]; wchar_t **
0x140006807  mov     rdi, rcx
0x14000680a  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEA_WPEAPEA_W@Z; ATL::CRegParser::PreProcessBuffer(wchar_t *,wchar_t * *)
0x14000680f  mov     ebx, eax
0x140006811  test    eax, eax
0x140006813  js      loc_140006917
0x140006819  mov     rbp, [rsp+2088h+pv]
0x14000681e  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEA_W@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(wchar_t *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(wchar_t *)'::`2'::map
0x140006825  mov     [rdi], rbp
0x140006828  mov     rcx, [rdi]
0x14000682b  xor     eax, eax
0x14000682d  cmp     ax, [rcx]
0x140006830  jz      loc_14000690C
0x140006836  lea     rdx, [rsp+2088h+String1]; wchar_t *
0x14000683b  mov     rcx, rdi; this
0x14000683e  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x140006843  mov     ebx, eax
0x140006845  test    eax, eax
0x140006847  js      loc_14000690C
0x14000684d  xor     ebx, ebx
0x14000684f  cmp     ebx, 0Eh
0x140006852  jnb     loc_140006907
0x140006858  movsxd  rsi, ebx
0x14000685b  lea     rcx, [rsp+2088h+String1]; lpString1
0x140006860  add     rsi, rsi
0x140006863  mov     rdx, [r13+rsi*8+0]; lpString2
0x140006868  call    cs:__imp_lstrcmpiW
0x14000686e  test    eax, eax
0x140006870  jz      short loc_140006876
0x140006872  inc     ebx
0x140006874  jmp     short loc_14000684F
0x140006876  mov     rsi, [r13+rsi*8+8]
0x14000687b  test    rsi, rsi
0x14000687e  jz      loc_140006907
0x140006884  lea     rdx, [rsp+2088h+String1]; wchar_t *
0x140006889  mov     rcx, rdi; this
0x14000688c  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x140006891  mov     ebx, eax
0x140006893  test    eax, eax
0x140006895  js      short loc_14000690C
0x140006897  mov     eax, 7Bh ; '{'
0x14000689c  cmp     ax, [rsp+2088h+String1]
0x1400068a1  jnz     short loc_140006907
0x1400068a3  mov     [rsp+2088h+var_2068], 0; int
0x1400068ab  mov     r8, rsi; HKEY
0x1400068ae  lea     rdx, [rsp+2088h+String1]; wchar_t *
0x1400068b3  mov     rcx, rdi; this
0x1400068b6  test    r15d, r15d
0x1400068b9  jz      short loc_1400068EC
0x1400068bb  mov     r14, [rdi]
0x1400068be  mov     r9d, r15d; int
0x1400068c1  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x1400068c6  mov     ebx, eax
0x1400068c8  test    eax, eax
0x1400068ca  jns     short loc_1400068FA
0x1400068cc  xor     r9d, r9d; int
0x1400068cf  mov     [rdi], r14
0x1400068d2  mov     r8, rsi; HKEY
0x1400068d5  mov     [rsp+2088h+var_2068], 0; int
0x1400068dd  lea     rdx, [rsp+2088h+String1]; wchar_t *
0x1400068e2  mov     rcx, rdi; this
0x1400068e5  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x1400068ea  jmp     short loc_14000690C
0x1400068ec  xor     r9d, r9d; int
0x1400068ef  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x1400068f4  mov     ebx, eax
0x1400068f6  test    eax, eax
0x1400068f8  js      short loc_14000690C
0x1400068fa  mov     rcx, rdi; this
0x1400068fd  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x140006902  jmp     loc_140006828
0x140006907  mov     ebx, 80020009h
0x14000690c  mov     rcx, rbp; pv
0x14000690f  call    cs:__imp_CoTaskMemFree
0x140006915  mov     eax, ebx
0x140006917  mov     rcx, [rsp+2088h+var_48]
0x14000691f  xor     rcx, rsp; StackCookie
0x140006922  call    __security_check_cookie
0x140006927  add     rsp, 2050h
0x14000692e  pop     r15
0x140006930  pop     r14
0x140006932  pop     r13
0x140006934  pop     rdi
0x140006935  pop     rsi
0x140006936  pop     rbp
0x140006937  pop     rbx
0x140006938  retn
```
