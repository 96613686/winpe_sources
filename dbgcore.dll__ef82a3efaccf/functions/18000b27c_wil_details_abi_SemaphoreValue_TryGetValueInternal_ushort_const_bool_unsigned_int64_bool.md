# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000b27c`
- end: `0x18000b4f1`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `629`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180004c68`
- `0x18000500c`

## callees

- `0x180001710`
- `0x180007eb4`
- `0x180009ee4`
- `0x180009f0c`
- `0x18000ae3c`
- `0x18000b27c`
- `0x18000f34c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b313`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b38e`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b313`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b38e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b446`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b446`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b359`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b3ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b3db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b3f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b415`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b437`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b359`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b3ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b3db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b3f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b415`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b437`

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
0x18000b27c  push    rbp
0x18000b27e  push    rbx
0x18000b27f  push    rsi
0x18000b280  push    rdi
0x18000b281  push    r14
0x18000b283  push    r15
0x18000b285  lea     rbp, [rsp-158h]
0x18000b28d  sub     rsp, 258h
0x18000b294  mov     rax, cs:__security_cookie
0x18000b29b  xor     rax, rsp
0x18000b29e  mov     [rbp+180h+var_40], rax
0x18000b2a5  xor     r15d, r15d
0x18000b2a8  lea     rax, [rsp+280h+Name]
0x18000b2ad  mov     esi, 104h
0x18000b2b2  mov     [r8], r15
0x18000b2b5  mov     edx, esi
0x18000b2b7  mov     r14, r8
0x18000b2ba  mov     r9d, 7FFFFFFEh
0x18000b2c0  test    r9, r9
0x18000b2c3  jz      short loc_18000B2E4
0x18000b2c5  movzx   r8d, word ptr [rcx]
0x18000b2c9  test    r8w, r8w
0x18000b2cd  jz      short loc_18000B2E4
0x18000b2cf  mov     [rax], r8w
0x18000b2d3  add     rcx, 2
0x18000b2d7  add     rax, 2
0x18000b2db  dec     r9
0x18000b2de  sub     rdx, 1
0x18000b2e2  jnz     short loc_18000B2C0
0x18000b2e4  test    rdx, rdx
0x18000b2e7  lea     rcx, [rax-2]
0x18000b2eb  lea     r8, aP0; "_p0"
0x18000b2f2  mov     rdx, rsi; unsigned __int64
0x18000b2f5  cmovnz  rcx, rax
0x18000b2f9  mov     [rcx], r15w
0x18000b2fd  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000b302  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000b307  lea     r8, [rsp+280h+Name]; lpName
0x18000b30c  xor     edx, edx; bInheritHandle
0x18000b30e  mov     ecx, 1F0003h; dwDesiredAccess
0x18000b313  call    cs:__imp_OpenSemaphoreW
0x18000b319  mov     rbx, rax
0x18000b31c  test    rax, rax
0x18000b31f  jz      loc_18000B446
0x18000b325  lea     rdx, [rsp+280h+var_25C]; int *
0x18000b32a  mov     [rsp+280h+var_25C], r15d
0x18000b32f  mov     rcx, rax; hHandle
0x18000b332  mov     [rsp+280h+var_260], r15d; int
0x18000b337  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000b33c  mov     edi, eax
0x18000b33e  test    eax, eax
0x18000b340  jns     short loc_18000B36E
0x18000b342  mov     rcx, [rbp+188h]; this
0x18000b349  mov     r9d, eax; char *
0x18000b34c  mov     edx, 0D6h; void *
0x18000b351  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b356  mov     rcx, rbx; hObject
0x18000b359  call    cs:__imp_CloseHandle
0x18000b35f  test    eax, eax
0x18000b361  jz      loc_18000B4BB
0x18000b367  mov     eax, edi
0x18000b369  jmp     loc_18000B466
0x18000b36e  lea     r8, asc_18002F198; "h"
0x18000b375  mov     rdx, rsi; unsigned __int64
0x18000b378  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000b37d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000b382  lea     r8, [rsp+280h+Name]; lpName
0x18000b387  xor     edx, edx; bInheritHandle
0x18000b389  mov     ecx, 1F0003h; dwDesiredAccess
0x18000b38e  call    cs:__imp_OpenSemaphoreW
0x18000b394  mov     rdi, rax
0x18000b397  test    rax, rax
0x18000b39a  jz      loc_18000B421
0x18000b3a0  lea     rdx, [rsp+280h+var_260]; int *
0x18000b3a5  mov     rcx, rax; hHandle
0x18000b3a8  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000b3ad  mov     esi, eax
0x18000b3af  test    eax, eax
0x18000b3b1  jns     short loc_18000B3ED
0x18000b3b3  mov     rcx, [rbp+188h]; this
0x18000b3ba  mov     r9d, eax; char *
0x18000b3bd  mov     edx, 0DEh; void *
0x18000b3c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b3c7  mov     rcx, rdi; hObject
0x18000b3ca  call    cs:__imp_CloseHandle
0x18000b3d0  test    eax, eax
0x18000b3d2  jz      loc_18000B4CD
0x18000b3d8  mov     rcx, rbx; hObject
0x18000b3db  call    cs:__imp_CloseHandle
0x18000b3e1  test    eax, eax
0x18000b3e3  jz      loc_18000B4DF
0x18000b3e9  mov     eax, esi
0x18000b3eb  jmp     short loc_18000B466
0x18000b3ed  mov     rcx, rdi; hObject
0x18000b3f0  call    cs:__imp_CloseHandle
0x18000b3f6  test    eax, eax
0x18000b3f8  jz      loc_18000B485
0x18000b3fe  movsxd  rax, [rsp+280h+var_25C]
0x18000b403  movsxd  rcx, [rsp+280h+var_260]
0x18000b408  shl     rcx, 1Fh
0x18000b40c  or      rcx, rax
0x18000b40f  mov     [r14], rcx
0x18000b412  mov     rcx, rbx; hObject
0x18000b415  call    cs:__imp_CloseHandle
0x18000b41b  test    eax, eax
0x18000b41d  jz      short loc_18000B497
0x18000b41f  jmp     short loc_18000B451
0x18000b421  mov     rcx, [rbp+188h]; this
0x18000b428  mov     edx, 0DCh; void *
0x18000b42d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b432  mov     rcx, rbx; hObject
0x18000b435  mov     edi, eax
0x18000b437  call    cs:__imp_CloseHandle
0x18000b43d  test    eax, eax
0x18000b43f  jz      short loc_18000B4A9
0x18000b441  jmp     loc_18000B367
0x18000b446  call    cs:__imp_GetLastError
0x18000b44c  cmp     eax, 2
0x18000b44f  jnz     short loc_18000B455
0x18000b451  xor     eax, eax
0x18000b453  jmp     short loc_18000B466
0x18000b455  mov     rcx, [rbp+188h]; this
0x18000b45c  mov     edx, 0D0h; void *
0x18000b461  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b466  mov     rcx, [rbp+180h+var_40]
0x18000b46d  xor     rcx, rsp; StackCookie
0x18000b470  call    __security_check_cookie
0x18000b475  add     rsp, 258h
0x18000b47c  pop     r15
0x18000b47e  pop     r14
0x18000b480  pop     rdi
0x18000b481  pop     rsi
0x18000b482  pop     rbx
0x18000b483  pop     rbp
0x18000b484  retn
0x18000b485  mov     rcx, [rbp+188h]; this
0x18000b48c  mov     edx, 0A0Bh; void *
0x18000b491  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b497  mov     rcx, [rbp+188h]; this
0x18000b49e  mov     edx, 0A0Bh; void *
0x18000b4a3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b4a9  mov     rcx, [rbp+188h]; this
0x18000b4b0  mov     edx, 0A0Bh; void *
0x18000b4b5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b4bb  mov     rcx, [rbp+188h]; this
0x18000b4c2  mov     edx, 0A0Bh; void *
0x18000b4c7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b4cd  mov     rcx, [rbp+188h]; this
0x18000b4d4  mov     edx, 0A0Bh; void *
0x18000b4d9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b4df  mov     rcx, [rbp+188h]; this
0x18000b4e6  mov     edx, 0A0Bh; void *
0x18000b4eb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
