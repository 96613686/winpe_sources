# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000c2cc`
- end: `0x18000c59b`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `719`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000717c`
- `0x180007558`

## callees

- `0x1800026d0`
- `0x180008af4`
- `0x18000b0d4`
- `0x18000b0f4`
- `0x18000bc44`
- `0x18000c2cc`
- `0x18000cc00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000c363`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000c3f1`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000c363`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000c3f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c4e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c4e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c3b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c43a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c451`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c46f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c49a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c4cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c3b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c43a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c451`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c46f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c49a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c4cd`

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
  unsigned int v13; // r8d
  const char *v14; // r9
  HANDLE v16; // rax
  const char *v17; // r9
  void *v18; // rdi
  int v19; // eax
  unsigned int v20; // esi
  unsigned int v21; // r8d
  const char *v22; // r9
  unsigned int v23; // r8d
  const char *v24; // r9
  unsigned int v25; // r8d
  const char *v26; // r9
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned int v29; // r8d
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v31);
    return 0;
  }
  v33[0] = 0;
  v32 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v33);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v32);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v13, v14);
    return LastError;
  }
  StringCchCatW(Name, 0x104u, L"h");
  v16 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v18 = v16;
  if ( !v16 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v17);
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
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v19, v32);
  if ( !CloseHandle(v18) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v21, v22);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
  return v20;
}

```

## disassembly

```asm
0x18000c2cc  push    rbp
0x18000c2ce  push    rbx
0x18000c2cf  push    rsi
0x18000c2d0  push    rdi
0x18000c2d1  push    r14
0x18000c2d3  push    r15
0x18000c2d5  lea     rbp, [rsp-158h]
0x18000c2dd  sub     rsp, 258h
0x18000c2e4  mov     rax, cs:__security_cookie
0x18000c2eb  xor     rax, rsp
0x18000c2ee  mov     [rbp+180h+var_40], rax
0x18000c2f5  xor     r15d, r15d
0x18000c2f8  lea     rax, [rsp+280h+Name]
0x18000c2fd  mov     esi, 104h
0x18000c302  mov     [r8], r15
0x18000c305  mov     edx, esi
0x18000c307  mov     r14, r8
0x18000c30a  mov     r9d, 7FFFFFFEh
0x18000c310  test    r9, r9
0x18000c313  jz      short loc_18000C334
0x18000c315  movzx   r8d, word ptr [rcx]
0x18000c319  test    r8w, r8w
0x18000c31d  jz      short loc_18000C334
0x18000c31f  mov     [rax], r8w
0x18000c323  add     rcx, 2
0x18000c327  add     rax, 2
0x18000c32b  dec     r9
0x18000c32e  sub     rdx, 1
0x18000c332  jnz     short loc_18000C310
0x18000c334  test    rdx, rdx
0x18000c337  lea     rcx, [rax-2]
0x18000c33b  lea     r8, aP0; "_p0"
0x18000c342  mov     rdx, rsi; unsigned __int64
0x18000c345  cmovnz  rcx, rax
0x18000c349  mov     [rcx], r15w
0x18000c34d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000c352  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000c357  lea     r8, [rsp+280h+Name]; lpName
0x18000c35c  xor     edx, edx; bInheritHandle
0x18000c35e  mov     ecx, 1F0003h; dwDesiredAccess
0x18000c363  call    cs:__imp_OpenSemaphoreW
0x18000c36a  nop     dword ptr [rax+rax+00h]
0x18000c36f  mov     rbx, rax
0x18000c372  test    rax, rax
0x18000c375  jz      loc_18000C4E2
0x18000c37b  lea     rdx, [rsp+280h+var_25C]; int *
0x18000c380  mov     [rsp+280h+var_25C], r15d
0x18000c385  mov     rcx, rax; hHandle
0x18000c388  mov     [rsp+280h+var_260], r15d; int
0x18000c38d  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000c392  mov     edi, eax
0x18000c394  test    eax, eax
0x18000c396  jns     short loc_18000C3D1
0x18000c398  mov     rcx, [rbp+188h]; this
0x18000c39f  lea     r8, aWil; "wil"
0x18000c3a6  mov     r9d, eax; char *
0x18000c3a9  mov     edx, 0D6h; void *
0x18000c3ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c3b3  mov     rcx, rbx; hObject
0x18000c3b6  call    cs:__imp_CloseHandle
0x18000c3bd  nop     dword ptr [rax+rax+00h]
0x18000c3c2  test    eax, eax
0x18000c3c4  jz      loc_18000C565
0x18000c3ca  mov     eax, edi
0x18000c3cc  jmp     loc_18000C50F
0x18000c3d1  lea     r8, asc_180050B08; "h"
0x18000c3d8  mov     rdx, rsi; unsigned __int64
0x18000c3db  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000c3e0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000c3e5  lea     r8, [rsp+280h+Name]; lpName
0x18000c3ea  xor     edx, edx; bInheritHandle
0x18000c3ec  mov     ecx, 1F0003h; dwDesiredAccess
0x18000c3f1  call    cs:__imp_OpenSemaphoreW
0x18000c3f8  nop     dword ptr [rax+rax+00h]
0x18000c3fd  mov     rdi, rax
0x18000c400  test    rax, rax
0x18000c403  jz      loc_18000C4B0
0x18000c409  lea     rdx, [rsp+280h+var_260]; int *
0x18000c40e  mov     rcx, rax; hHandle
0x18000c411  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000c416  mov     esi, eax
0x18000c418  test    eax, eax
0x18000c41a  jns     short loc_18000C46C
0x18000c41c  mov     rcx, [rbp+188h]; this
0x18000c423  lea     r8, aWil; "wil"
0x18000c42a  mov     r9d, eax; char *
0x18000c42d  mov     edx, 0DEh; void *
0x18000c432  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c437  mov     rcx, rdi; hObject
0x18000c43a  call    cs:__imp_CloseHandle
0x18000c441  nop     dword ptr [rax+rax+00h]
0x18000c446  test    eax, eax
0x18000c448  jz      loc_18000C577
0x18000c44e  mov     rcx, rbx; hObject
0x18000c451  call    cs:__imp_CloseHandle
0x18000c458  nop     dword ptr [rax+rax+00h]
0x18000c45d  test    eax, eax
0x18000c45f  jz      loc_18000C589
0x18000c465  mov     eax, esi
0x18000c467  jmp     loc_18000C50F
0x18000c46c  mov     rcx, rdi; hObject
0x18000c46f  call    cs:__imp_CloseHandle
0x18000c476  nop     dword ptr [rax+rax+00h]
0x18000c47b  test    eax, eax
0x18000c47d  jz      loc_18000C52F
0x18000c483  movsxd  rax, [rsp+280h+var_25C]
0x18000c488  movsxd  rcx, [rsp+280h+var_260]
0x18000c48d  shl     rcx, 1Fh
0x18000c491  or      rcx, rax
0x18000c494  mov     [r14], rcx
0x18000c497  mov     rcx, rbx; hObject
0x18000c49a  call    cs:__imp_CloseHandle
0x18000c4a1  nop     dword ptr [rax+rax+00h]
0x18000c4a6  test    eax, eax
0x18000c4a8  jz      loc_18000C541
0x18000c4ae  jmp     short loc_18000C4F3
0x18000c4b0  mov     rcx, [rbp+188h]; this
0x18000c4b7  lea     r8, aWil; "wil"
0x18000c4be  mov     edx, 0DCh; void *
0x18000c4c3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000c4c8  mov     rcx, rbx; hObject
0x18000c4cb  mov     edi, eax
0x18000c4cd  call    cs:__imp_CloseHandle
0x18000c4d4  nop     dword ptr [rax+rax+00h]
0x18000c4d9  test    eax, eax
0x18000c4db  jz      short loc_18000C553
0x18000c4dd  jmp     loc_18000C3CA
0x18000c4e2  call    cs:__imp_GetLastError
0x18000c4e9  nop     dword ptr [rax+rax+00h]
0x18000c4ee  cmp     eax, 2
0x18000c4f1  jnz     short loc_18000C4F7
0x18000c4f3  xor     eax, eax
0x18000c4f5  jmp     short loc_18000C50F
0x18000c4f7  mov     rcx, [rbp+188h]; this
0x18000c4fe  lea     r8, aWil; "wil"
0x18000c505  mov     edx, 0D0h; void *
0x18000c50a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000c50f  mov     rcx, [rbp+180h+var_40]
0x18000c516  xor     rcx, rsp; StackCookie
0x18000c519  call    __security_check_cookie
0x18000c51e  add     rsp, 258h
0x18000c525  pop     r15
0x18000c527  pop     r14
0x18000c529  pop     rdi
0x18000c52a  pop     rsi
0x18000c52b  pop     rbx
0x18000c52c  pop     rbp
0x18000c52d  retn
0x18000c52f  mov     rcx, [rbp+188h]; this
0x18000c536  mov     edx, 0A0Bh; void *
0x18000c53b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c541  mov     rcx, [rbp+188h]; this
0x18000c548  mov     edx, 0A0Bh; void *
0x18000c54d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c553  mov     rcx, [rbp+188h]; this
0x18000c55a  mov     edx, 0A0Bh; void *
0x18000c55f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c565  mov     rcx, [rbp+188h]; this
0x18000c56c  mov     edx, 0A0Bh; void *
0x18000c571  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c577  mov     rcx, [rbp+188h]; this
0x18000c57e  mov     edx, 0A0Bh; void *
0x18000c583  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c589  mov     rcx, [rbp+188h]; this
0x18000c590  mov     edx, 0A0Bh; void *
0x18000c595  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
