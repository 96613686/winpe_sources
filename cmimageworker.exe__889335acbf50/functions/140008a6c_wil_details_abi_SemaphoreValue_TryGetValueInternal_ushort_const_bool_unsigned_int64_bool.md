# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x140008a6c`
- end: `0x140008d32`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `710`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x14000418c`
- `0x140016494`

## callees

- `0x1400020b0`
- `0x14000512c`
- `0x140006fc4`
- `0x140006fe4`
- `0x1400088dc`
- `0x140008a6c`
- `0x140008f74`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140008b00`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140008b88`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140008b00`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140008b88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008c79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008c79`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008b53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008bd1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008be8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008c06`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008c31`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008c64`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008b53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008bd1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008be8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008c06`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008c31`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008c64`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  unsigned __int64 v6; // rdx
  __int64 v7; // r9
  WCHAR *v8; // rcx
  HANDLE v9; // rax
  void *v10; // rbx
  int ValueFromSemaphore; // eax
  unsigned __int64 v12; // rdx
  unsigned int LastError; // edi
  __int64 v14; // r8
  const char *v15; // r9
  HANDLE v17; // rax
  const char *v18; // r9
  void *v19; // rdi
  int v20; // eax
  unsigned int v21; // esi
  __int64 v22; // r8
  const char *v23; // r9
  __int64 v24; // r8
  const char *v25; // r9
  __int64 v26; // r8
  const char *v27; // r9
  __int64 v28; // r8
  const char *v29; // r9
  __int64 v30; // r8
  const char *v31; // r9
  const char *v32; // r9
  int v33; // [rsp+20h] [rbp-E0h] BYREF
  int v34[3]; // [rsp+24h] [rbp-DCh] BYREF
  WCHAR Name[264]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v4 = Name;
  *a3 = 0;
  v6 = 260;
  v7 = 2147483646;
  do
  {
    if ( !v7 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v7;
    --v6;
  }
  while ( v6 );
  v8 = v4 - 1;
  if ( v6 )
    v8 = v4;
  *v8 = 0;
  StringCchCatW(Name, v6, L"_p0");
  v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v10 = v9;
  if ( !v9 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (int)"wil", v32);
    return 0;
  }
  v34[0] = 0;
  v33 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v34);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, (int)"wil", (const char *)(unsigned int)ValueFromSemaphore);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    return LastError;
  }
  StringCchCatW(Name, v12, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v19 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (int)"wil", v18);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    return LastError;
  }
  v20 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v33);
  v21 = v20;
  if ( v20 >= 0 )
  {
    if ( !CloseHandle(v19) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    *a3 = v34[0] | (unsigned __int64)((__int64)v33 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v20);
  if ( !CloseHandle(v19) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v22, v23);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
  return v21;
}

```

## disassembly

```asm
0x140008a6c  push    rbp
0x140008a6e  push    rbx
0x140008a6f  push    rsi
0x140008a70  push    rdi
0x140008a71  push    r14
0x140008a73  push    r15
0x140008a75  lea     rbp, [rsp-158h]
0x140008a7d  sub     rsp, 258h
0x140008a84  mov     rax, cs:__security_cookie
0x140008a8b  xor     rax, rsp
0x140008a8e  mov     [rbp+180h+var_40], rax
0x140008a95  xor     r15d, r15d
0x140008a98  lea     rax, [rsp+280h+Name]
0x140008a9d  mov     [r8], r15
0x140008aa0  mov     r14, r8
0x140008aa3  mov     edx, 104h
0x140008aa8  mov     r9d, 7FFFFFFEh
0x140008aae  test    r9, r9
0x140008ab1  jz      short loc_140008AD2
0x140008ab3  movzx   r8d, word ptr [rcx]
0x140008ab7  test    r8w, r8w
0x140008abb  jz      short loc_140008AD2
0x140008abd  mov     [rax], r8w
0x140008ac1  add     rcx, 2
0x140008ac5  add     rax, 2
0x140008ac9  dec     r9
0x140008acc  sub     rdx, 1; unsigned __int64
0x140008ad0  jnz     short loc_140008AAE
0x140008ad2  test    rdx, rdx
0x140008ad5  lea     rcx, [rax-2]
0x140008ad9  lea     r8, aP0; "_p0"
0x140008ae0  cmovnz  rcx, rax
0x140008ae4  mov     [rcx], r15w
0x140008ae8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140008aed  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140008af2  mov     esi, 1F0003h
0x140008af7  lea     r8, [rsp+280h+Name]; lpName
0x140008afc  mov     ecx, esi; dwDesiredAccess
0x140008afe  xor     edx, edx; bInheritHandle
0x140008b00  call    cs:__imp_OpenSemaphoreW
0x140008b07  nop     dword ptr [rax+rax+00h]
0x140008b0c  mov     rbx, rax
0x140008b0f  test    rax, rax
0x140008b12  jz      loc_140008C79
0x140008b18  lea     rdx, [rsp+280h+var_25C]; int *
0x140008b1d  mov     [rsp+280h+var_25C], r15d
0x140008b22  mov     rcx, rax; hHandle
0x140008b25  mov     [rsp+280h+var_260], r15d; int
0x140008b2a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140008b2f  mov     edi, eax
0x140008b31  test    eax, eax
0x140008b33  jns     short loc_140008B6E
0x140008b35  mov     rcx, [rbp+188h]; this
0x140008b3c  lea     r8, aWil; "wil"
0x140008b43  mov     r9d, eax; char *
0x140008b46  mov     edx, 0D6h; void *
0x140008b4b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008b50  mov     rcx, rbx; hObject
0x140008b53  call    cs:__imp_CloseHandle
0x140008b5a  nop     dword ptr [rax+rax+00h]
0x140008b5f  test    eax, eax
0x140008b61  jz      loc_140008CFC
0x140008b67  mov     eax, edi
0x140008b69  jmp     loc_140008CA6
0x140008b6e  lea     r8, asc_1400368A0; "h"
0x140008b75  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140008b7a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140008b7f  lea     r8, [rsp+280h+Name]; lpName
0x140008b84  xor     edx, edx; bInheritHandle
0x140008b86  mov     ecx, esi; dwDesiredAccess
0x140008b88  call    cs:__imp_OpenSemaphoreW
0x140008b8f  nop     dword ptr [rax+rax+00h]
0x140008b94  mov     rdi, rax
0x140008b97  test    rax, rax
0x140008b9a  jz      loc_140008C47
0x140008ba0  lea     rdx, [rsp+280h+var_260]; int *
0x140008ba5  mov     rcx, rax; hHandle
0x140008ba8  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140008bad  mov     esi, eax
0x140008baf  test    eax, eax
0x140008bb1  jns     short loc_140008C03
0x140008bb3  mov     rcx, [rbp+188h]; this
0x140008bba  lea     r8, aWil; "wil"
0x140008bc1  mov     r9d, eax; char *
0x140008bc4  mov     edx, 0DEh; void *
0x140008bc9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008bce  mov     rcx, rdi; hObject
0x140008bd1  call    cs:__imp_CloseHandle
0x140008bd8  nop     dword ptr [rax+rax+00h]
0x140008bdd  test    eax, eax
0x140008bdf  jz      loc_140008D0E
0x140008be5  mov     rcx, rbx; hObject
0x140008be8  call    cs:__imp_CloseHandle
0x140008bef  nop     dword ptr [rax+rax+00h]
0x140008bf4  test    eax, eax
0x140008bf6  jz      loc_140008D20
0x140008bfc  mov     eax, esi
0x140008bfe  jmp     loc_140008CA6
0x140008c03  mov     rcx, rdi; hObject
0x140008c06  call    cs:__imp_CloseHandle
0x140008c0d  nop     dword ptr [rax+rax+00h]
0x140008c12  test    eax, eax
0x140008c14  jz      loc_140008CC6
0x140008c1a  movsxd  rax, [rsp+280h+var_25C]
0x140008c1f  movsxd  rcx, [rsp+280h+var_260]
0x140008c24  shl     rcx, 1Fh
0x140008c28  or      rcx, rax
0x140008c2b  mov     [r14], rcx
0x140008c2e  mov     rcx, rbx; hObject
0x140008c31  call    cs:__imp_CloseHandle
0x140008c38  nop     dword ptr [rax+rax+00h]
0x140008c3d  test    eax, eax
0x140008c3f  jz      loc_140008CD8
0x140008c45  jmp     short loc_140008C8A
0x140008c47  mov     rcx, [rbp+188h]; this
0x140008c4e  lea     r8, aWil; "wil"
0x140008c55  mov     edx, 0DCh; void *
0x140008c5a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140008c5f  mov     rcx, rbx; hObject
0x140008c62  mov     edi, eax
0x140008c64  call    cs:__imp_CloseHandle
0x140008c6b  nop     dword ptr [rax+rax+00h]
0x140008c70  test    eax, eax
0x140008c72  jz      short loc_140008CEA
0x140008c74  jmp     loc_140008B67
0x140008c79  call    cs:__imp_GetLastError
0x140008c80  nop     dword ptr [rax+rax+00h]
0x140008c85  cmp     eax, 2
0x140008c88  jnz     short loc_140008C8E
0x140008c8a  xor     eax, eax
0x140008c8c  jmp     short loc_140008CA6
0x140008c8e  mov     rcx, [rbp+188h]; this
0x140008c95  lea     r8, aWil; "wil"
0x140008c9c  mov     edx, 0D0h; void *
0x140008ca1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140008ca6  mov     rcx, [rbp+180h+var_40]
0x140008cad  xor     rcx, rsp; StackCookie
0x140008cb0  call    __security_check_cookie
0x140008cb5  add     rsp, 258h
0x140008cbc  pop     r15
0x140008cbe  pop     r14
0x140008cc0  pop     rdi
0x140008cc1  pop     rsi
0x140008cc2  pop     rbx
0x140008cc3  pop     rbp
0x140008cc4  retn
0x140008cc6  mov     rcx, [rbp+188h]; this
0x140008ccd  mov     edx, 0A0Bh; void *
0x140008cd2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008cd8  mov     rcx, [rbp+188h]; this
0x140008cdf  mov     edx, 0A0Bh; void *
0x140008ce4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008cea  mov     rcx, [rbp+188h]; this
0x140008cf1  mov     edx, 0A0Bh; void *
0x140008cf6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008cfc  mov     rcx, [rbp+188h]; this
0x140008d03  mov     edx, 0A0Bh; void *
0x140008d08  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008d0e  mov     rcx, [rbp+188h]; this
0x140008d15  mov     edx, 0A0Bh; void *
0x140008d1a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008d20  mov     rcx, [rbp+188h]; this
0x140008d27  mov     edx, 0A0Bh; void *
0x140008d2c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
