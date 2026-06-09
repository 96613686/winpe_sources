# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180009af8`
- end: `0x180009d6d`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `629`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000443c`
- `0x1800047e0`

## callees

- `0x180002240`
- `0x180006830`
- `0x180009150`
- `0x180009170`
- `0x18000958c`
- `0x180009af8`
- `0x18000a3cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009b8f`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009c0a`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009b8f`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009c0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009cc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009cc2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009bd5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009c46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009c57`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009c6c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009c91`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009cb3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009bd5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009c46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009c57`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009c6c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009c91`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009cb3`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  __int64 v5; // rdx
  __int64 v7; // r9
  WCHAR *v8; // rcx
  HANDLE v9; // rax
  void *v10; // rbx
  int ValueFromSemaphore; // eax
  unsigned int v12; // r8d
  unsigned int LastError; // edi
  unsigned int v14; // r8d
  const char *v15; // r9
  HANDLE v17; // rax
  unsigned int v18; // r8d
  const char *v19; // r9
  void *v20; // rdi
  int v21; // eax
  unsigned int v22; // r8d
  unsigned int v23; // esi
  unsigned int v24; // r8d
  const char *v25; // r9
  unsigned int v26; // r8d
  const char *v27; // r9
  unsigned int v28; // r8d
  const char *v29; // r9
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  unsigned int v34; // r8d
  const char *v35; // r9
  int v36; // [rsp+20h] [rbp-E0h] BYREF
  int v37[3]; // [rsp+24h] [rbp-DCh] BYREF
  WCHAR Name[264]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v4 = Name;
  *a3 = 0;
  v5 = 260;
  v7 = 2147483646;
  do
  {
    if ( !v7 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v7;
    --v5;
  }
  while ( v5 );
  v8 = v4 - 1;
  if ( v5 )
    v8 = v4;
  *v8 = 0;
  StringCchCatW(Name, 0x104u, L"_p0");
  v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v10 = v9;
  if ( !v9 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v34, v35);
    return 0;
  }
  v37[0] = 0;
  v36 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v37);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v12, (const char *)(unsigned int)ValueFromSemaphore, v36);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    return LastError;
  }
  StringCchCatW(Name, 0x104u, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v18, v19);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    return LastError;
  }
  v21 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v36);
  v23 = v21;
  if ( v21 >= 0 )
  {
    if ( !CloseHandle(v20) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    *a3 = v37[0] | (unsigned __int64)((__int64)v36 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v22, (const char *)(unsigned int)v21, v36);
  if ( !CloseHandle(v20) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
  return v23;
}

```

## disassembly

```asm
0x180009af8  push    rbp
0x180009afa  push    rbx
0x180009afb  push    rsi
0x180009afc  push    rdi
0x180009afd  push    r14
0x180009aff  push    r15
0x180009b01  lea     rbp, [rsp-158h]
0x180009b09  sub     rsp, 258h
0x180009b10  mov     rax, cs:__security_cookie
0x180009b17  xor     rax, rsp
0x180009b1a  mov     [rbp+180h+var_40], rax
0x180009b21  xor     r15d, r15d
0x180009b24  lea     rax, [rsp+280h+Name]
0x180009b29  mov     esi, 104h
0x180009b2e  mov     [r8], r15
0x180009b31  mov     edx, esi
0x180009b33  mov     r14, r8
0x180009b36  mov     r9d, 7FFFFFFEh
0x180009b3c  test    r9, r9
0x180009b3f  jz      short loc_180009B60
0x180009b41  movzx   r8d, word ptr [rcx]
0x180009b45  test    r8w, r8w
0x180009b49  jz      short loc_180009B60
0x180009b4b  mov     [rax], r8w
0x180009b4f  add     rcx, 2
0x180009b53  add     rax, 2
0x180009b57  dec     r9
0x180009b5a  sub     rdx, 1
0x180009b5e  jnz     short loc_180009B3C
0x180009b60  test    rdx, rdx
0x180009b63  lea     rcx, [rax-2]
0x180009b67  lea     r8, aP0; "_p0"
0x180009b6e  mov     rdx, rsi; unsigned __int64
0x180009b71  cmovnz  rcx, rax
0x180009b75  mov     [rcx], r15w
0x180009b79  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180009b7e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009b83  lea     r8, [rsp+280h+Name]; lpName
0x180009b88  xor     edx, edx; bInheritHandle
0x180009b8a  mov     ecx, 1F0003h; dwDesiredAccess
0x180009b8f  call    cs:__imp_OpenSemaphoreW
0x180009b95  mov     rbx, rax
0x180009b98  test    rax, rax
0x180009b9b  jz      loc_180009CC2
0x180009ba1  lea     rdx, [rsp+280h+var_25C]; int *
0x180009ba6  mov     [rsp+280h+var_25C], r15d
0x180009bab  mov     rcx, rax; hHandle
0x180009bae  mov     [rsp+280h+var_260], r15d; int
0x180009bb3  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009bb8  mov     edi, eax
0x180009bba  test    eax, eax
0x180009bbc  jns     short loc_180009BEA
0x180009bbe  mov     rcx, [rbp+188h]; this
0x180009bc5  mov     r9d, eax; char *
0x180009bc8  mov     edx, 0D6h; void *
0x180009bcd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009bd2  mov     rcx, rbx; hObject
0x180009bd5  call    cs:__imp_CloseHandle
0x180009bdb  test    eax, eax
0x180009bdd  jz      loc_180009D37
0x180009be3  mov     eax, edi
0x180009be5  jmp     loc_180009CE2
0x180009bea  lea     r8, asc_18002B0A0; "h"
0x180009bf1  mov     rdx, rsi; unsigned __int64
0x180009bf4  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180009bf9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009bfe  lea     r8, [rsp+280h+Name]; lpName
0x180009c03  xor     edx, edx; bInheritHandle
0x180009c05  mov     ecx, 1F0003h; dwDesiredAccess
0x180009c0a  call    cs:__imp_OpenSemaphoreW
0x180009c10  mov     rdi, rax
0x180009c13  test    rax, rax
0x180009c16  jz      loc_180009C9D
0x180009c1c  lea     rdx, [rsp+280h+var_260]; int *
0x180009c21  mov     rcx, rax; hHandle
0x180009c24  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009c29  mov     esi, eax
0x180009c2b  test    eax, eax
0x180009c2d  jns     short loc_180009C69
0x180009c2f  mov     rcx, [rbp+188h]; this
0x180009c36  mov     r9d, eax; char *
0x180009c39  mov     edx, 0DEh; void *
0x180009c3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009c43  mov     rcx, rdi; hObject
0x180009c46  call    cs:__imp_CloseHandle
0x180009c4c  test    eax, eax
0x180009c4e  jz      loc_180009D49
0x180009c54  mov     rcx, rbx; hObject
0x180009c57  call    cs:__imp_CloseHandle
0x180009c5d  test    eax, eax
0x180009c5f  jz      loc_180009D5B
0x180009c65  mov     eax, esi
0x180009c67  jmp     short loc_180009CE2
0x180009c69  mov     rcx, rdi; hObject
0x180009c6c  call    cs:__imp_CloseHandle
0x180009c72  test    eax, eax
0x180009c74  jz      loc_180009D01
0x180009c7a  movsxd  rax, [rsp+280h+var_25C]
0x180009c7f  movsxd  rcx, [rsp+280h+var_260]
0x180009c84  shl     rcx, 1Fh
0x180009c88  or      rcx, rax
0x180009c8b  mov     [r14], rcx
0x180009c8e  mov     rcx, rbx; hObject
0x180009c91  call    cs:__imp_CloseHandle
0x180009c97  test    eax, eax
0x180009c99  jz      short loc_180009D13
0x180009c9b  jmp     short loc_180009CCD
0x180009c9d  mov     rcx, [rbp+188h]; this
0x180009ca4  mov     edx, 0DCh; void *
0x180009ca9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009cae  mov     rcx, rbx; hObject
0x180009cb1  mov     edi, eax
0x180009cb3  call    cs:__imp_CloseHandle
0x180009cb9  test    eax, eax
0x180009cbb  jz      short loc_180009D25
0x180009cbd  jmp     loc_180009BE3
0x180009cc2  call    cs:__imp_GetLastError
0x180009cc8  cmp     eax, 2
0x180009ccb  jnz     short loc_180009CD1
0x180009ccd  xor     eax, eax
0x180009ccf  jmp     short loc_180009CE2
0x180009cd1  mov     rcx, [rbp+188h]; this
0x180009cd8  mov     edx, 0D0h; void *
0x180009cdd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009ce2  mov     rcx, [rbp+180h+var_40]
0x180009ce9  xor     rcx, rsp; StackCookie
0x180009cec  call    __security_check_cookie
0x180009cf1  add     rsp, 258h
0x180009cf8  pop     r15
0x180009cfa  pop     r14
0x180009cfc  pop     rdi
0x180009cfd  pop     rsi
0x180009cfe  pop     rbx
0x180009cff  pop     rbp
0x180009d00  retn
0x180009d01  mov     rcx, [rbp+188h]; this
0x180009d08  mov     edx, 0A0Bh; void *
0x180009d0d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009d13  mov     rcx, [rbp+188h]; this
0x180009d1a  mov     edx, 0A0Bh; void *
0x180009d1f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009d25  mov     rcx, [rbp+188h]; this
0x180009d2c  mov     edx, 0A0Bh; void *
0x180009d31  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009d37  mov     rcx, [rbp+188h]; this
0x180009d3e  mov     edx, 0A0Bh; void *
0x180009d43  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009d49  mov     rcx, [rbp+188h]; this
0x180009d50  mov     edx, 0A0Bh; void *
0x180009d55  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009d5b  mov     rcx, [rbp+188h]; this
0x180009d62  mov     edx, 0A0Bh; void *
0x180009d67  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
