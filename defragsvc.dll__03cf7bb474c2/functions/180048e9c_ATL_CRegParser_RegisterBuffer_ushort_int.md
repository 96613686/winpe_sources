# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x180048e9c`
- end: `0x180049009`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `365`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180049128`

## callees

- `0x180048910`
- `0x180048ad4`
- `0x180048e9c`
- `0x1800493b8`
- `0x180049c08`
- `0x180067b30`
- `0x180067bf0`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180048f38`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180048f38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048fdf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048fdf`

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
0x180048e9c  push    rbx
0x180048e9e  push    rbp
0x180048e9f  push    rsi
0x180048ea0  push    rdi
0x180048ea1  push    r13
0x180048ea3  push    r14
0x180048ea5  push    r15
0x180048ea7  mov     eax, 2050h
0x180048eac  call    _alloca_probe
0x180048eb1  sub     rsp, rax
0x180048eb4  mov     rax, cs:__security_cookie
0x180048ebb  xor     rax, rsp
0x180048ebe  mov     [rsp+2088h+var_48], rax
0x180048ec6  mov     r15d, r8d
0x180048ec9  mov     [rsp+2088h+pv], 0
0x180048ed2  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x180048ed7  mov     rdi, rcx
0x180048eda  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x180048edf  mov     ebx, eax
0x180048ee1  test    eax, eax
0x180048ee3  js      loc_180048FE7
0x180048ee9  mov     rbp, [rsp+2088h+pv]
0x180048eee  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x180048ef5  mov     [rdi], rbp
0x180048ef8  mov     rcx, [rdi]
0x180048efb  xor     eax, eax
0x180048efd  cmp     ax, [rcx]
0x180048f00  jz      loc_180048FDC
0x180048f06  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180048f0b  mov     rcx, rdi; this
0x180048f0e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180048f13  mov     ebx, eax
0x180048f15  test    eax, eax
0x180048f17  js      loc_180048FDC
0x180048f1d  xor     ebx, ebx
0x180048f1f  cmp     ebx, 0Eh
0x180048f22  jnb     loc_180048FD7
0x180048f28  movsxd  rsi, ebx
0x180048f2b  lea     rcx, [rsp+2088h+String1]; lpString1
0x180048f30  add     rsi, rsi
0x180048f33  mov     rdx, [r13+rsi*8+0]; lpString2
0x180048f38  call    cs:__imp_lstrcmpiW
0x180048f3e  test    eax, eax
0x180048f40  jz      short loc_180048F46
0x180048f42  inc     ebx
0x180048f44  jmp     short loc_180048F1F
0x180048f46  mov     rsi, [r13+rsi*8+8]
0x180048f4b  test    rsi, rsi
0x180048f4e  jz      loc_180048FD7
0x180048f54  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180048f59  mov     rcx, rdi; this
0x180048f5c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180048f61  mov     ebx, eax
0x180048f63  test    eax, eax
0x180048f65  js      short loc_180048FDC
0x180048f67  mov     eax, 7Bh ; '{'
0x180048f6c  cmp     ax, [rsp+2088h+String1]
0x180048f71  jnz     short loc_180048FD7
0x180048f73  mov     [rsp+2088h+var_2068], 0; int
0x180048f7b  mov     r8, rsi; HKEY
0x180048f7e  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180048f83  mov     rcx, rdi; this
0x180048f86  test    r15d, r15d
0x180048f89  jz      short loc_180048FBC
0x180048f8b  mov     r14, [rdi]
0x180048f8e  mov     r9d, r15d; int
0x180048f91  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180048f96  mov     ebx, eax
0x180048f98  test    eax, eax
0x180048f9a  jns     short loc_180048FCA
0x180048f9c  xor     r9d, r9d; int
0x180048f9f  mov     [rdi], r14
0x180048fa2  mov     r8, rsi; HKEY
0x180048fa5  mov     [rsp+2088h+var_2068], 0; int
0x180048fad  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180048fb2  mov     rcx, rdi; this
0x180048fb5  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180048fba  jmp     short loc_180048FDC
0x180048fbc  xor     r9d, r9d; int
0x180048fbf  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180048fc4  mov     ebx, eax
0x180048fc6  test    eax, eax
0x180048fc8  js      short loc_180048FDC
0x180048fca  mov     rcx, rdi; this
0x180048fcd  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180048fd2  jmp     loc_180048EF8
0x180048fd7  mov     ebx, 80020009h
0x180048fdc  mov     rcx, rbp; pv
0x180048fdf  call    cs:__imp_CoTaskMemFree
0x180048fe5  mov     eax, ebx
0x180048fe7  mov     rcx, [rsp+2088h+var_48]
0x180048fef  xor     rcx, rsp; StackCookie
0x180048ff2  call    __security_check_cookie
0x180048ff7  add     rsp, 2050h
0x180048ffe  pop     r15
0x180049000  pop     r14
0x180049002  pop     r13
0x180049004  pop     rdi
0x180049005  pop     rsi
0x180049006  pop     rbp
0x180049007  pop     rbx
0x180049008  retn
```
