# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x14000a6cc`
- end: `0x14000a946`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `634`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140005738`
- `0x140005b08`

## callees

- `0x140002600`
- `0x1400077b8`
- `0x140009704`
- `0x140009724`
- `0x14000a25c`
- `0x14000a6cc`
- `0x14000af68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000a760`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000a7dc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000a760`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000a7dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a89b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a89b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a7ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a81f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a830`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a845`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a86a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a88c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a7ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a81f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a830`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a845`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a86a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a88c`

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
  unsigned int v14; // r8d
  const char *v15; // r9
  HANDLE v17; // rax
  unsigned int v18; // r8d
  const char *v19; // r9
  void *v20; // rdi
  int v21; // eax
  unsigned int v22; // esi
  unsigned int v23; // r8d
  const char *v24; // r9
  unsigned int v25; // r8d
  const char *v26; // r9
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned int v29; // r8d
  const char *v30; // r9
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  int v35; // [rsp+20h] [rbp-E0h] BYREF
  int v36[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v33, v34);
    return 0;
  }
  v36[0] = 0;
  v35 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v36);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v35);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    return LastError;
  }
  StringCchCatW(Name, v12, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v18, v19);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
    return LastError;
  }
  v21 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v35);
  v22 = v21;
  if ( v21 >= 0 )
  {
    if ( !CloseHandle(v20) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    *a3 = v36[0] | (unsigned __int64)((__int64)v35 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v21, v35);
  if ( !CloseHandle(v20) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
  return v22;
}

```

## disassembly

```asm
0x14000a6cc  push    rbp
0x14000a6ce  push    rbx
0x14000a6cf  push    rsi
0x14000a6d0  push    rdi
0x14000a6d1  push    r14
0x14000a6d3  push    r15
0x14000a6d5  lea     rbp, [rsp-158h]
0x14000a6dd  sub     rsp, 258h
0x14000a6e4  mov     rax, cs:__security_cookie
0x14000a6eb  xor     rax, rsp
0x14000a6ee  mov     [rbp+180h+var_40], rax
0x14000a6f5  xor     r15d, r15d
0x14000a6f8  lea     rax, [rsp+280h+Name]
0x14000a6fd  mov     [r8], r15
0x14000a700  mov     r14, r8
0x14000a703  mov     edx, 104h
0x14000a708  mov     r9d, 7FFFFFFEh
0x14000a70e  test    r9, r9
0x14000a711  jz      short loc_14000A732
0x14000a713  movzx   r8d, word ptr [rcx]
0x14000a717  test    r8w, r8w
0x14000a71b  jz      short loc_14000A732
0x14000a71d  mov     [rax], r8w
0x14000a721  add     rcx, 2
0x14000a725  add     rax, 2
0x14000a729  dec     r9
0x14000a72c  sub     rdx, 1; unsigned __int64
0x14000a730  jnz     short loc_14000A70E
0x14000a732  test    rdx, rdx
0x14000a735  lea     rcx, [rax-2]
0x14000a739  lea     r8, aP0; "_p0"
0x14000a740  cmovnz  rcx, rax
0x14000a744  mov     [rcx], r15w
0x14000a748  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000a74d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000a752  mov     esi, 1F0003h
0x14000a757  lea     r8, [rsp+280h+Name]; lpName
0x14000a75c  mov     ecx, esi; dwDesiredAccess
0x14000a75e  xor     edx, edx; bInheritHandle
0x14000a760  call    cs:__imp_OpenSemaphoreW
0x14000a766  mov     rbx, rax
0x14000a769  test    rax, rax
0x14000a76c  jz      loc_14000A89B
0x14000a772  lea     rdx, [rsp+280h+var_25C]; int *
0x14000a777  mov     [rsp+280h+var_25C], r15d
0x14000a77c  mov     rcx, rax; hHandle
0x14000a77f  mov     [rsp+280h+var_260], r15d; int
0x14000a784  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000a789  mov     edi, eax
0x14000a78b  test    eax, eax
0x14000a78d  jns     short loc_14000A7C2
0x14000a78f  mov     rcx, [rbp+188h]; this
0x14000a796  lea     r8, aWil; "wil"
0x14000a79d  mov     r9d, eax; char *
0x14000a7a0  mov     edx, 0D6h; void *
0x14000a7a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000a7aa  mov     rcx, rbx; hObject
0x14000a7ad  call    cs:__imp_CloseHandle
0x14000a7b3  test    eax, eax
0x14000a7b5  jz      loc_14000A910
0x14000a7bb  mov     eax, edi
0x14000a7bd  jmp     loc_14000A8BB
0x14000a7c2  lea     r8, asc_140015F50; "h"
0x14000a7c9  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000a7ce  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000a7d3  lea     r8, [rsp+280h+Name]; lpName
0x14000a7d8  xor     edx, edx; bInheritHandle
0x14000a7da  mov     ecx, esi; dwDesiredAccess
0x14000a7dc  call    cs:__imp_OpenSemaphoreW
0x14000a7e2  mov     rdi, rax
0x14000a7e5  test    rax, rax
0x14000a7e8  jz      loc_14000A876
0x14000a7ee  lea     rdx, [rsp+280h+var_260]; int *
0x14000a7f3  mov     rcx, rax; hHandle
0x14000a7f6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000a7fb  mov     esi, eax
0x14000a7fd  test    eax, eax
0x14000a7ff  jns     short loc_14000A842
0x14000a801  mov     rcx, [rbp+188h]; this
0x14000a808  lea     r8, aWil; "wil"
0x14000a80f  mov     r9d, eax; char *
0x14000a812  mov     edx, 0DEh; void *
0x14000a817  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000a81c  mov     rcx, rdi; hObject
0x14000a81f  call    cs:__imp_CloseHandle
0x14000a825  test    eax, eax
0x14000a827  jz      loc_14000A922
0x14000a82d  mov     rcx, rbx; hObject
0x14000a830  call    cs:__imp_CloseHandle
0x14000a836  test    eax, eax
0x14000a838  jz      loc_14000A934
0x14000a83e  mov     eax, esi
0x14000a840  jmp     short loc_14000A8BB
0x14000a842  mov     rcx, rdi; hObject
0x14000a845  call    cs:__imp_CloseHandle
0x14000a84b  test    eax, eax
0x14000a84d  jz      loc_14000A8DA
0x14000a853  movsxd  rax, [rsp+280h+var_25C]
0x14000a858  movsxd  rcx, [rsp+280h+var_260]
0x14000a85d  shl     rcx, 1Fh
0x14000a861  or      rcx, rax
0x14000a864  mov     [r14], rcx
0x14000a867  mov     rcx, rbx; hObject
0x14000a86a  call    cs:__imp_CloseHandle
0x14000a870  test    eax, eax
0x14000a872  jz      short loc_14000A8EC
0x14000a874  jmp     short loc_14000A8A6
0x14000a876  mov     rcx, [rbp+188h]; this
0x14000a87d  mov     edx, 0DCh; void *
0x14000a882  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000a887  mov     rcx, rbx; hObject
0x14000a88a  mov     edi, eax
0x14000a88c  call    cs:__imp_CloseHandle
0x14000a892  test    eax, eax
0x14000a894  jz      short loc_14000A8FE
0x14000a896  jmp     loc_14000A7BB
0x14000a89b  call    cs:__imp_GetLastError
0x14000a8a1  cmp     eax, 2
0x14000a8a4  jnz     short loc_14000A8AA
0x14000a8a6  xor     eax, eax
0x14000a8a8  jmp     short loc_14000A8BB
0x14000a8aa  mov     rcx, [rbp+188h]; this
0x14000a8b1  mov     edx, 0D0h; void *
0x14000a8b6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000a8bb  mov     rcx, [rbp+180h+var_40]
0x14000a8c2  xor     rcx, rsp; StackCookie
0x14000a8c5  call    __security_check_cookie
0x14000a8ca  add     rsp, 258h
0x14000a8d1  pop     r15
0x14000a8d3  pop     r14
0x14000a8d5  pop     rdi
0x14000a8d6  pop     rsi
0x14000a8d7  pop     rbx
0x14000a8d8  pop     rbp
0x14000a8d9  retn
0x14000a8da  mov     rcx, [rbp+188h]; this
0x14000a8e1  mov     edx, 0A0Bh; void *
0x14000a8e6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000a8ec  mov     rcx, [rbp+188h]; this
0x14000a8f3  mov     edx, 0A0Bh; void *
0x14000a8f8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000a8fe  mov     rcx, [rbp+188h]; this
0x14000a905  mov     edx, 0A0Bh; void *
0x14000a90a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000a910  mov     rcx, [rbp+188h]; this
0x14000a917  mov     edx, 0A0Bh; void *
0x14000a91c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000a922  mov     rcx, [rbp+188h]; this
0x14000a929  mov     edx, 0A0Bh; void *
0x14000a92e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000a934  mov     rcx, [rbp+188h]; this
0x14000a93b  mov     edx, 0A0Bh; void *
0x14000a940  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
