# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18001087c`
- end: `0x180010b79`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `765`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000e58c`
- `0x180017fdc`

## callees

- `0x180004f70`
- `0x18000f594`
- `0x18000ff04`
- `0x18000ff24`
- `0x1800106d8`
- `0x18001087c`
- `0x180010d94`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180010913`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800109a1`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180010913`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800109a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010a96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010a96`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010966`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800109ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010a01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010a1f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010a4a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010a7d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010966`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800109ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010a01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010a1f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010a4a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010a7d`

## string_xrefs

- `0x180010aea`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180010b03`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180010b1c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180010b35`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180010b4e`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180010b67`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  unsigned int LastError; // edi
  const char *v13; // r9
  HANDLE v15; // rax
  const char *v16; // r9
  void *v17; // rdi
  int v18; // eax
  unsigned int v19; // esi
  const char *v20; // r9
  const char *v21; // r9
  const char *v22; // r9
  const char *v23; // r9
  const char *v24; // r9
  const char *v25; // r9
  int v26; // [rsp+20h] [rbp-E0h] BYREF
  int v27[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v25);
    return 0;
  }
  v27[0] = 0;
  v26 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v27);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v26);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v13);
    return LastError;
  }
  StringCchCatW(Name, 0x104u, L"h");
  v15 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v17 = v15;
  if ( !v15 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v16);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v24);
    return LastError;
  }
  v18 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v15, &v26);
  v19 = v18;
  if ( v18 >= 0 )
  {
    if ( !CloseHandle(v17) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v22);
    *a3 = v27[0] | (unsigned __int64)((__int64)v26 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v23);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v18, v26);
  if ( !CloseHandle(v17) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v20);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v21);
  return v19;
}

```

## disassembly

```asm
0x18001087c  push    rbp
0x18001087e  push    rbx
0x18001087f  push    rsi
0x180010880  push    rdi
0x180010881  push    r14
0x180010883  push    r15
0x180010885  lea     rbp, [rsp-158h]
0x18001088d  sub     rsp, 258h
0x180010894  mov     rax, cs:__security_cookie
0x18001089b  xor     rax, rsp
0x18001089e  mov     [rbp+180h+var_40], rax
0x1800108a5  xor     r15d, r15d
0x1800108a8  lea     rax, [rsp+280h+Name]
0x1800108ad  mov     esi, 104h
0x1800108b2  mov     [r8], r15
0x1800108b5  mov     edx, esi
0x1800108b7  mov     r14, r8
0x1800108ba  mov     r9d, 7FFFFFFEh
0x1800108c0  test    r9, r9
0x1800108c3  jz      short loc_1800108E4
0x1800108c5  movzx   r8d, word ptr [rcx]
0x1800108c9  test    r8w, r8w
0x1800108cd  jz      short loc_1800108E4
0x1800108cf  mov     [rax], r8w
0x1800108d3  add     rcx, 2
0x1800108d7  add     rax, 2
0x1800108db  dec     r9
0x1800108de  sub     rdx, 1
0x1800108e2  jnz     short loc_1800108C0
0x1800108e4  test    rdx, rdx
0x1800108e7  lea     rcx, [rax-2]
0x1800108eb  lea     r8, aP0; "_p0"
0x1800108f2  mov     rdx, rsi; unsigned __int64
0x1800108f5  cmovnz  rcx, rax
0x1800108f9  mov     [rcx], r15w
0x1800108fd  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180010902  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180010907  lea     r8, [rsp+280h+Name]; lpName
0x18001090c  xor     edx, edx; bInheritHandle
0x18001090e  mov     ecx, 1F0003h; dwDesiredAccess
0x180010913  call    cs:__imp_OpenSemaphoreW
0x18001091a  nop     dword ptr [rax+rax+00h]
0x18001091f  mov     rbx, rax
0x180010922  test    rax, rax
0x180010925  jz      loc_180010A96
0x18001092b  lea     rdx, [rsp+280h+var_25C]; int *
0x180010930  mov     [rsp+280h+var_25C], r15d
0x180010935  mov     rcx, rax; hHandle
0x180010938  mov     [rsp+280h+var_260], r15d; int
0x18001093d  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180010942  mov     edi, eax
0x180010944  test    eax, eax
0x180010946  jns     short loc_180010981
0x180010948  mov     rcx, [rbp+188h]; this
0x18001094f  lea     r8, aWil; "wil"
0x180010956  mov     r9d, eax; char *
0x180010959  mov     edx, 0D6h; void *
0x18001095e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010963  mov     rcx, rbx; hObject
0x180010966  call    cs:__imp_CloseHandle
0x18001096d  nop     dword ptr [rax+rax+00h]
0x180010972  test    eax, eax
0x180010974  jz      loc_180010B2E
0x18001097a  mov     eax, edi
0x18001097c  jmp     loc_180010AC3
0x180010981  lea     r8, asc_1800D6D90; "h"
0x180010988  mov     rdx, rsi; unsigned __int64
0x18001098b  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180010990  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180010995  lea     r8, [rsp+280h+Name]; lpName
0x18001099a  xor     edx, edx; bInheritHandle
0x18001099c  mov     ecx, 1F0003h; dwDesiredAccess
0x1800109a1  call    cs:__imp_OpenSemaphoreW
0x1800109a8  nop     dword ptr [rax+rax+00h]
0x1800109ad  mov     rdi, rax
0x1800109b0  test    rax, rax
0x1800109b3  jz      loc_180010A60
0x1800109b9  lea     rdx, [rsp+280h+var_260]; int *
0x1800109be  mov     rcx, rax; hHandle
0x1800109c1  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800109c6  mov     esi, eax
0x1800109c8  test    eax, eax
0x1800109ca  jns     short loc_180010A1C
0x1800109cc  mov     rcx, [rbp+188h]; this
0x1800109d3  lea     r8, aWil; "wil"
0x1800109da  mov     r9d, eax; char *
0x1800109dd  mov     edx, 0DEh; void *
0x1800109e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800109e7  mov     rcx, rdi; hObject
0x1800109ea  call    cs:__imp_CloseHandle
0x1800109f1  nop     dword ptr [rax+rax+00h]
0x1800109f6  test    eax, eax
0x1800109f8  jz      loc_180010B47
0x1800109fe  mov     rcx, rbx; hObject
0x180010a01  call    cs:__imp_CloseHandle
0x180010a08  nop     dword ptr [rax+rax+00h]
0x180010a0d  test    eax, eax
0x180010a0f  jz      loc_180010B60
0x180010a15  mov     eax, esi
0x180010a17  jmp     loc_180010AC3
0x180010a1c  mov     rcx, rdi; hObject
0x180010a1f  call    cs:__imp_CloseHandle
0x180010a26  nop     dword ptr [rax+rax+00h]
0x180010a2b  test    eax, eax
0x180010a2d  jz      loc_180010AE3
0x180010a33  movsxd  rax, [rsp+280h+var_25C]
0x180010a38  movsxd  rcx, [rsp+280h+var_260]
0x180010a3d  shl     rcx, 1Fh
0x180010a41  or      rcx, rax
0x180010a44  mov     [r14], rcx
0x180010a47  mov     rcx, rbx; hObject
0x180010a4a  call    cs:__imp_CloseHandle
0x180010a51  nop     dword ptr [rax+rax+00h]
0x180010a56  test    eax, eax
0x180010a58  jz      loc_180010AFC
0x180010a5e  jmp     short loc_180010AA7
0x180010a60  mov     rcx, [rbp+188h]; this
0x180010a67  lea     r8, aWil; "wil"
0x180010a6e  mov     edx, 0DCh; void *
0x180010a73  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180010a78  mov     rcx, rbx; hObject
0x180010a7b  mov     edi, eax
0x180010a7d  call    cs:__imp_CloseHandle
0x180010a84  nop     dword ptr [rax+rax+00h]
0x180010a89  test    eax, eax
0x180010a8b  jz      loc_180010B15
0x180010a91  jmp     loc_18001097A
0x180010a96  call    cs:__imp_GetLastError
0x180010a9d  nop     dword ptr [rax+rax+00h]
0x180010aa2  cmp     eax, 2
0x180010aa5  jnz     short loc_180010AAB
0x180010aa7  xor     eax, eax
0x180010aa9  jmp     short loc_180010AC3
0x180010aab  mov     rcx, [rbp+188h]; this
0x180010ab2  lea     r8, aWil; "wil"
0x180010ab9  mov     edx, 0D0h; void *
0x180010abe  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180010ac3  mov     rcx, [rbp+180h+var_40]
0x180010aca  xor     rcx, rsp; StackCookie
0x180010acd  call    __security_check_cookie
0x180010ad2  add     rsp, 258h
0x180010ad9  pop     r15
0x180010adb  pop     r14
0x180010add  pop     rdi
0x180010ade  pop     rsi
0x180010adf  pop     rbx
0x180010ae0  pop     rbp
0x180010ae1  retn
0x180010ae3  mov     rcx, [rbp+188h]; this
0x180010aea  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180010af1  mov     edx, 0A0Bh; void *
0x180010af6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010afc  mov     rcx, [rbp+188h]; this
0x180010b03  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180010b0a  mov     edx, 0A0Bh; void *
0x180010b0f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010b15  mov     rcx, [rbp+188h]; this
0x180010b1c  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180010b23  mov     edx, 0A0Bh; void *
0x180010b28  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010b2e  mov     rcx, [rbp+188h]; this
0x180010b35  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180010b3c  mov     edx, 0A0Bh; void *
0x180010b41  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010b47  mov     rcx, [rbp+188h]; this
0x180010b4e  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180010b55  mov     edx, 0A0Bh; void *
0x180010b5a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010b60  mov     rcx, [rbp+188h]; this
0x180010b67  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180010b6e  mov     edx, 0A0Bh; void *
0x180010b73  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
