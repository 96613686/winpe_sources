# ATL::CRegParser::RegisterBuffer(wchar_t *,int)

- ea: `0x18000fb7c`
- end: `0x18000fce9`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEA_WH@Z`
- size: `365`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, wchar_t *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000fcf0`

## callees

- `0x180002a90`
- `0x18000f5e4`
- `0x18000f7e0`
- `0x18000fb7c`
- `0x18000fea0`
- `0x180010568`
- `0x180033d00`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000fc18`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000fc18`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fcbf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fcbf`

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
0x18000fb7c  push    rbx
0x18000fb7e  push    rbp
0x18000fb7f  push    rsi
0x18000fb80  push    rdi
0x18000fb81  push    r13
0x18000fb83  push    r14
0x18000fb85  push    r15
0x18000fb87  mov     eax, 2050h
0x18000fb8c  call    _alloca_probe
0x18000fb91  sub     rsp, rax
0x18000fb94  mov     rax, cs:__security_cookie
0x18000fb9b  xor     rax, rsp
0x18000fb9e  mov     [rsp+2088h+var_48], rax
0x18000fba6  mov     r15d, r8d
0x18000fba9  mov     [rsp+2088h+pv], 0
0x18000fbb2  lea     r8, [rsp+2088h+pv]; wchar_t **
0x18000fbb7  mov     rdi, rcx
0x18000fbba  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEA_WPEAPEA_W@Z; ATL::CRegParser::PreProcessBuffer(wchar_t *,wchar_t * *)
0x18000fbbf  mov     ebx, eax
0x18000fbc1  test    eax, eax
0x18000fbc3  js      loc_18000FCC7
0x18000fbc9  mov     rbp, [rsp+2088h+pv]
0x18000fbce  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEA_W@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(wchar_t *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(wchar_t *)'::`2'::map
0x18000fbd5  mov     [rdi], rbp
0x18000fbd8  mov     rcx, [rdi]
0x18000fbdb  xor     eax, eax
0x18000fbdd  cmp     ax, [rcx]
0x18000fbe0  jz      loc_18000FCBC
0x18000fbe6  lea     rdx, [rsp+2088h+String1]; wchar_t *
0x18000fbeb  mov     rcx, rdi; this
0x18000fbee  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18000fbf3  mov     ebx, eax
0x18000fbf5  test    eax, eax
0x18000fbf7  js      loc_18000FCBC
0x18000fbfd  xor     ebx, ebx
0x18000fbff  cmp     ebx, 0Eh
0x18000fc02  jnb     loc_18000FCB7
0x18000fc08  movsxd  rsi, ebx
0x18000fc0b  lea     rcx, [rsp+2088h+String1]; lpString1
0x18000fc10  add     rsi, rsi
0x18000fc13  mov     rdx, [r13+rsi*8+0]; lpString2
0x18000fc18  call    cs:__imp_lstrcmpiW
0x18000fc1e  test    eax, eax
0x18000fc20  jz      short loc_18000FC26
0x18000fc22  inc     ebx
0x18000fc24  jmp     short loc_18000FBFF
0x18000fc26  mov     rsi, [r13+rsi*8+8]
0x18000fc2b  test    rsi, rsi
0x18000fc2e  jz      loc_18000FCB7
0x18000fc34  lea     rdx, [rsp+2088h+String1]; wchar_t *
0x18000fc39  mov     rcx, rdi; this
0x18000fc3c  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18000fc41  mov     ebx, eax
0x18000fc43  test    eax, eax
0x18000fc45  js      short loc_18000FCBC
0x18000fc47  mov     eax, 7Bh ; '{'
0x18000fc4c  cmp     ax, [rsp+2088h+String1]
0x18000fc51  jnz     short loc_18000FCB7
0x18000fc53  mov     [rsp+2088h+var_2068], 0; int
0x18000fc5b  mov     r8, rsi; HKEY
0x18000fc5e  lea     rdx, [rsp+2088h+String1]; wchar_t *
0x18000fc63  mov     rcx, rdi; this
0x18000fc66  test    r15d, r15d
0x18000fc69  jz      short loc_18000FC9C
0x18000fc6b  mov     r14, [rdi]
0x18000fc6e  mov     r9d, r15d; int
0x18000fc71  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x18000fc76  mov     ebx, eax
0x18000fc78  test    eax, eax
0x18000fc7a  jns     short loc_18000FCAA
0x18000fc7c  xor     r9d, r9d; int
0x18000fc7f  mov     [rdi], r14
0x18000fc82  mov     r8, rsi; HKEY
0x18000fc85  mov     [rsp+2088h+var_2068], 0; int
0x18000fc8d  lea     rdx, [rsp+2088h+String1]; wchar_t *
0x18000fc92  mov     rcx, rdi; this
0x18000fc95  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x18000fc9a  jmp     short loc_18000FCBC
0x18000fc9c  xor     r9d, r9d; int
0x18000fc9f  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x18000fca4  mov     ebx, eax
0x18000fca6  test    eax, eax
0x18000fca8  js      short loc_18000FCBC
0x18000fcaa  mov     rcx, rdi; this
0x18000fcad  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18000fcb2  jmp     loc_18000FBD8
0x18000fcb7  mov     ebx, 80020009h
0x18000fcbc  mov     rcx, rbp; pv
0x18000fcbf  call    cs:__imp_CoTaskMemFree
0x18000fcc5  mov     eax, ebx
0x18000fcc7  mov     rcx, [rsp+2088h+var_48]
0x18000fccf  xor     rcx, rsp; StackCookie
0x18000fcd2  call    __security_check_cookie
0x18000fcd7  add     rsp, 2050h
0x18000fcde  pop     r15
0x18000fce0  pop     r14
0x18000fce2  pop     r13
0x18000fce4  pop     rdi
0x18000fce5  pop     rsi
0x18000fce6  pop     rbp
0x18000fce7  pop     rbx
0x18000fce8  retn
```
