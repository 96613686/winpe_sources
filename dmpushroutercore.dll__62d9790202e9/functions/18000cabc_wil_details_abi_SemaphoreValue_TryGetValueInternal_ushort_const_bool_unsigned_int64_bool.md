# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000cabc`
- end: `0x18000cd54`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `664`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180007ee8`
- `0x1800082b8`

## callees

- `0x1800039f0`
- `0x1800098f8`
- `0x18000ba94`
- `0x18000bab4`
- `0x18000c504`
- `0x18000cabc`
- `0x18000d448`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cca2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cca2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cba0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cc18`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cc29`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cc41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cc66`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cc93`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cba0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cc18`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cc29`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cc41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cc66`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cc93`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000cb53`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000cbd5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000cb53`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000cbd5`

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
  __int64 v13; // r8
  const char *v14; // r9
  HANDLE v16; // rax
  const char *v17; // r9
  void *v18; // rdi
  int v19; // eax
  unsigned int v20; // esi
  __int64 v21; // r8
  const char *v22; // r9
  __int64 v23; // r8
  const char *v24; // r9
  __int64 v25; // r8
  const char *v26; // r9
  __int64 v27; // r8
  const char *v28; // r9
  __int64 v29; // r8
  const char *v30; // r9
  const char *v31; // r9
  int v32; // [rsp+20h] [rbp-E0h] BYREF
  int v33[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (int)"wil", v31);
    return 0;
  }
  v33[0] = 0;
  v32 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v33);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, (int)"wil", (const char *)(unsigned int)ValueFromSemaphore);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v13, v14);
    return LastError;
  }
  StringCchCatW(Name, 0x104u, L"h");
  v16 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v18 = v16;
  if ( !v16 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (int)"wil", v17);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    return LastError;
  }
  v19 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v16, &v32);
  v20 = v19;
  if ( v19 >= 0 )
  {
    if ( !CloseHandle(v18) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
    *a3 = v33[0] | (unsigned __int64)((__int64)v32 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v19);
  if ( !CloseHandle(v18) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v21, v22);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
  return v20;
}

```

## disassembly

```asm
0x18000cabc  push    rbp
0x18000cabe  push    rbx
0x18000cabf  push    rsi
0x18000cac0  push    rdi
0x18000cac1  push    r14
0x18000cac3  push    r15
0x18000cac5  lea     rbp, [rsp-158h]
0x18000cacd  sub     rsp, 258h
0x18000cad4  mov     rax, cs:__security_cookie
0x18000cadb  xor     rax, rsp
0x18000cade  mov     [rbp+180h+var_40], rax
0x18000cae5  xor     r15d, r15d
0x18000cae8  lea     rax, [rsp+280h+Name]
0x18000caed  mov     esi, 104h
0x18000caf2  mov     [r8], r15
0x18000caf5  mov     edx, esi
0x18000caf7  mov     r14, r8
0x18000cafa  mov     r9d, 7FFFFFFEh
0x18000cb00  test    r9, r9
0x18000cb03  jz      short loc_18000CB24
0x18000cb05  movzx   r8d, word ptr [rcx]
0x18000cb09  test    r8w, r8w
0x18000cb0d  jz      short loc_18000CB24
0x18000cb0f  mov     [rax], r8w
0x18000cb13  add     rcx, 2
0x18000cb17  add     rax, 2
0x18000cb1b  dec     r9
0x18000cb1e  sub     rdx, 1
0x18000cb22  jnz     short loc_18000CB00
0x18000cb24  test    rdx, rdx
0x18000cb27  lea     rcx, [rax-2]
0x18000cb2b  lea     r8, aP0; "_p0"
0x18000cb32  mov     rdx, rsi; unsigned __int64
0x18000cb35  cmovnz  rcx, rax
0x18000cb39  mov     [rcx], r15w
0x18000cb3d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000cb42  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000cb47  lea     r8, [rsp+280h+Name]; lpName
0x18000cb4c  xor     edx, edx; bInheritHandle
0x18000cb4e  mov     ecx, 1F0003h; dwDesiredAccess
0x18000cb53  call    cs:__imp_OpenSemaphoreW
0x18000cb59  mov     rbx, rax
0x18000cb5c  test    rax, rax
0x18000cb5f  jz      loc_18000CCA2
0x18000cb65  lea     rdx, [rsp+280h+var_25C]; int *
0x18000cb6a  mov     [rsp+280h+var_25C], r15d
0x18000cb6f  mov     rcx, rax; hHandle
0x18000cb72  mov     [rsp+280h+var_260], r15d; int
0x18000cb77  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000cb7c  mov     edi, eax
0x18000cb7e  test    eax, eax
0x18000cb80  jns     short loc_18000CBB5
0x18000cb82  mov     rcx, [rbp+188h]; this
0x18000cb89  lea     r8, aWil; "wil"
0x18000cb90  mov     r9d, eax; char *
0x18000cb93  mov     edx, 0D6h; void *
0x18000cb98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cb9d  mov     rcx, rbx; hObject
0x18000cba0  call    cs:__imp_CloseHandle
0x18000cba6  test    eax, eax
0x18000cba8  jz      loc_18000CD1E
0x18000cbae  mov     eax, edi
0x18000cbb0  jmp     loc_18000CCC9
0x18000cbb5  lea     r8, asc_18003E5E0; "h"
0x18000cbbc  mov     rdx, rsi; unsigned __int64
0x18000cbbf  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000cbc4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000cbc9  lea     r8, [rsp+280h+Name]; lpName
0x18000cbce  xor     edx, edx; bInheritHandle
0x18000cbd0  mov     ecx, 1F0003h; dwDesiredAccess
0x18000cbd5  call    cs:__imp_OpenSemaphoreW
0x18000cbdb  mov     rdi, rax
0x18000cbde  test    rax, rax
0x18000cbe1  jz      loc_18000CC76
0x18000cbe7  lea     rdx, [rsp+280h+var_260]; int *
0x18000cbec  mov     rcx, rax; hHandle
0x18000cbef  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000cbf4  mov     esi, eax
0x18000cbf6  test    eax, eax
0x18000cbf8  jns     short loc_18000CC3E
0x18000cbfa  mov     rcx, [rbp+188h]; this
0x18000cc01  lea     r8, aWil; "wil"
0x18000cc08  mov     r9d, eax; char *
0x18000cc0b  mov     edx, 0DEh; void *
0x18000cc10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cc15  mov     rcx, rdi; hObject
0x18000cc18  call    cs:__imp_CloseHandle
0x18000cc1e  test    eax, eax
0x18000cc20  jz      loc_18000CD30
0x18000cc26  mov     rcx, rbx; hObject
0x18000cc29  call    cs:__imp_CloseHandle
0x18000cc2f  test    eax, eax
0x18000cc31  jz      loc_18000CD42
0x18000cc37  mov     eax, esi
0x18000cc39  jmp     loc_18000CCC9
0x18000cc3e  mov     rcx, rdi; hObject
0x18000cc41  call    cs:__imp_CloseHandle
0x18000cc47  test    eax, eax
0x18000cc49  jz      loc_18000CCE8
0x18000cc4f  movsxd  rax, [rsp+280h+var_25C]
0x18000cc54  movsxd  rcx, [rsp+280h+var_260]
0x18000cc59  shl     rcx, 1Fh
0x18000cc5d  or      rcx, rax
0x18000cc60  mov     [r14], rcx
0x18000cc63  mov     rcx, rbx; hObject
0x18000cc66  call    cs:__imp_CloseHandle
0x18000cc6c  test    eax, eax
0x18000cc6e  jz      loc_18000CCFA
0x18000cc74  jmp     short loc_18000CCAD
0x18000cc76  mov     rcx, [rbp+188h]; this
0x18000cc7d  lea     r8, aWil; "wil"
0x18000cc84  mov     edx, 0DCh; void *
0x18000cc89  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000cc8e  mov     rcx, rbx; hObject
0x18000cc91  mov     edi, eax
0x18000cc93  call    cs:__imp_CloseHandle
0x18000cc99  test    eax, eax
0x18000cc9b  jz      short loc_18000CD0C
0x18000cc9d  jmp     loc_18000CBAE
0x18000cca2  call    cs:__imp_GetLastError
0x18000cca8  cmp     eax, 2
0x18000ccab  jnz     short loc_18000CCB1
0x18000ccad  xor     eax, eax
0x18000ccaf  jmp     short loc_18000CCC9
0x18000ccb1  mov     rcx, [rbp+188h]; this
0x18000ccb8  lea     r8, aWil; "wil"
0x18000ccbf  mov     edx, 0D0h; void *
0x18000ccc4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000ccc9  mov     rcx, [rbp+180h+var_40]
0x18000ccd0  xor     rcx, rsp; StackCookie
0x18000ccd3  call    __security_check_cookie
0x18000ccd8  add     rsp, 258h
0x18000ccdf  pop     r15
0x18000cce1  pop     r14
0x18000cce3  pop     rdi
0x18000cce4  pop     rsi
0x18000cce5  pop     rbx
0x18000cce6  pop     rbp
0x18000cce7  retn
0x18000cce8  mov     rcx, [rbp+188h]; this
0x18000ccef  mov     edx, 0A0Bh; void *
0x18000ccf4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000ccfa  mov     rcx, [rbp+188h]; this
0x18000cd01  mov     edx, 0A0Bh; void *
0x18000cd06  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000cd0c  mov     rcx, [rbp+188h]; this
0x18000cd13  mov     edx, 0A0Bh; void *
0x18000cd18  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000cd1e  mov     rcx, [rbp+188h]; this
0x18000cd25  mov     edx, 0A0Bh; void *
0x18000cd2a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000cd30  mov     rcx, [rbp+188h]; this
0x18000cd37  mov     edx, 0A0Bh; void *
0x18000cd3c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000cd42  mov     rcx, [rbp+188h]; this
0x18000cd49  mov     edx, 0A0Bh; void *
0x18000cd4e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
