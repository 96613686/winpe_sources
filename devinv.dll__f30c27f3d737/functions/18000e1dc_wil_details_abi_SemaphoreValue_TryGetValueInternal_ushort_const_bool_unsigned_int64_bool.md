# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000e1dc`
- end: `0x18000e46b`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `655`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180008ea8`
- `0x180009278`

## callees

- `0x180005e40`
- `0x18000ad84`
- `0x18000d164`
- `0x18000d184`
- `0x18000dbc8`
- `0x18000e1dc`
- `0x18000eabc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000e270`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000e2ec`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000e270`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000e2ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e3b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e3b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e2bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e32f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e340`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e358`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e37d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e3aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e2bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e32f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e340`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e358`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e37d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e3aa`

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
  const char *v18; // r9
  void *v19; // rdi
  int v20; // eax
  unsigned int v21; // esi
  unsigned int v22; // r8d
  const char *v23; // r9
  unsigned int v24; // r8d
  const char *v25; // r9
  unsigned int v26; // r8d
  const char *v27; // r9
  unsigned int v28; // r8d
  const char *v29; // r9
  unsigned int v30; // r8d
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v32);
    return 0;
  }
  v34[0] = 0;
  v33 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v34);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v33);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    return LastError;
  }
  StringCchCatW(Name, v12, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v19 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v18);
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
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v20, v33);
  if ( !CloseHandle(v19) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v22, v23);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
  return v21;
}

```

## disassembly

```asm
0x18000e1dc  push    rbp
0x18000e1de  push    rbx
0x18000e1df  push    rsi
0x18000e1e0  push    rdi
0x18000e1e1  push    r14
0x18000e1e3  push    r15
0x18000e1e5  lea     rbp, [rsp-158h]
0x18000e1ed  sub     rsp, 258h
0x18000e1f4  mov     rax, cs:__security_cookie
0x18000e1fb  xor     rax, rsp
0x18000e1fe  mov     [rbp+180h+var_40], rax
0x18000e205  xor     r15d, r15d
0x18000e208  lea     rax, [rsp+280h+Name]
0x18000e20d  mov     [r8], r15
0x18000e210  mov     r14, r8
0x18000e213  mov     edx, 104h
0x18000e218  mov     r9d, 7FFFFFFEh
0x18000e21e  test    r9, r9
0x18000e221  jz      short loc_18000E242
0x18000e223  movzx   r8d, word ptr [rcx]
0x18000e227  test    r8w, r8w
0x18000e22b  jz      short loc_18000E242
0x18000e22d  mov     [rax], r8w
0x18000e231  add     rcx, 2
0x18000e235  add     rax, 2
0x18000e239  dec     r9
0x18000e23c  sub     rdx, 1; unsigned __int64
0x18000e240  jnz     short loc_18000E21E
0x18000e242  test    rdx, rdx
0x18000e245  lea     rcx, [rax-2]
0x18000e249  lea     r8, aP0; "_p0"
0x18000e250  cmovnz  rcx, rax
0x18000e254  mov     [rcx], r15w
0x18000e258  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000e25d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000e262  mov     esi, 1F0003h
0x18000e267  lea     r8, [rsp+280h+Name]; lpName
0x18000e26c  mov     ecx, esi; dwDesiredAccess
0x18000e26e  xor     edx, edx; bInheritHandle
0x18000e270  call    cs:__imp_OpenSemaphoreW
0x18000e276  mov     rbx, rax
0x18000e279  test    rax, rax
0x18000e27c  jz      loc_18000E3B9
0x18000e282  lea     rdx, [rsp+280h+var_25C]; int *
0x18000e287  mov     [rsp+280h+var_25C], r15d
0x18000e28c  mov     rcx, rax; hHandle
0x18000e28f  mov     [rsp+280h+var_260], r15d; int
0x18000e294  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000e299  mov     edi, eax
0x18000e29b  test    eax, eax
0x18000e29d  jns     short loc_18000E2D2
0x18000e29f  mov     rcx, [rbp+188h]; this
0x18000e2a6  lea     r8, aWil; "wil"
0x18000e2ad  mov     r9d, eax; char *
0x18000e2b0  mov     edx, 0D6h; void *
0x18000e2b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e2ba  mov     rcx, rbx; hObject
0x18000e2bd  call    cs:__imp_CloseHandle
0x18000e2c3  test    eax, eax
0x18000e2c5  jz      loc_18000E435
0x18000e2cb  mov     eax, edi
0x18000e2cd  jmp     loc_18000E3E0
0x18000e2d2  lea     r8, asc_18011E3C8; "h"
0x18000e2d9  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000e2de  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000e2e3  lea     r8, [rsp+280h+Name]; lpName
0x18000e2e8  xor     edx, edx; bInheritHandle
0x18000e2ea  mov     ecx, esi; dwDesiredAccess
0x18000e2ec  call    cs:__imp_OpenSemaphoreW
0x18000e2f2  mov     rdi, rax
0x18000e2f5  test    rax, rax
0x18000e2f8  jz      loc_18000E38D
0x18000e2fe  lea     rdx, [rsp+280h+var_260]; int *
0x18000e303  mov     rcx, rax; hHandle
0x18000e306  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000e30b  mov     esi, eax
0x18000e30d  test    eax, eax
0x18000e30f  jns     short loc_18000E355
0x18000e311  mov     rcx, [rbp+188h]; this
0x18000e318  lea     r8, aWil; "wil"
0x18000e31f  mov     r9d, eax; char *
0x18000e322  mov     edx, 0DEh; void *
0x18000e327  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e32c  mov     rcx, rdi; hObject
0x18000e32f  call    cs:__imp_CloseHandle
0x18000e335  test    eax, eax
0x18000e337  jz      loc_18000E447
0x18000e33d  mov     rcx, rbx; hObject
0x18000e340  call    cs:__imp_CloseHandle
0x18000e346  test    eax, eax
0x18000e348  jz      loc_18000E459
0x18000e34e  mov     eax, esi
0x18000e350  jmp     loc_18000E3E0
0x18000e355  mov     rcx, rdi; hObject
0x18000e358  call    cs:__imp_CloseHandle
0x18000e35e  test    eax, eax
0x18000e360  jz      loc_18000E3FF
0x18000e366  movsxd  rax, [rsp+280h+var_25C]
0x18000e36b  movsxd  rcx, [rsp+280h+var_260]
0x18000e370  shl     rcx, 1Fh
0x18000e374  or      rcx, rax
0x18000e377  mov     [r14], rcx
0x18000e37a  mov     rcx, rbx; hObject
0x18000e37d  call    cs:__imp_CloseHandle
0x18000e383  test    eax, eax
0x18000e385  jz      loc_18000E411
0x18000e38b  jmp     short loc_18000E3C4
0x18000e38d  mov     rcx, [rbp+188h]; this
0x18000e394  lea     r8, aWil; "wil"
0x18000e39b  mov     edx, 0DCh; void *
0x18000e3a0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000e3a5  mov     rcx, rbx; hObject
0x18000e3a8  mov     edi, eax
0x18000e3aa  call    cs:__imp_CloseHandle
0x18000e3b0  test    eax, eax
0x18000e3b2  jz      short loc_18000E423
0x18000e3b4  jmp     loc_18000E2CB
0x18000e3b9  call    cs:__imp_GetLastError
0x18000e3bf  cmp     eax, 2
0x18000e3c2  jnz     short loc_18000E3C8
0x18000e3c4  xor     eax, eax
0x18000e3c6  jmp     short loc_18000E3E0
0x18000e3c8  mov     rcx, [rbp+188h]; this
0x18000e3cf  lea     r8, aWil; "wil"
0x18000e3d6  mov     edx, 0D0h; void *
0x18000e3db  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000e3e0  mov     rcx, [rbp+180h+var_40]
0x18000e3e7  xor     rcx, rsp; StackCookie
0x18000e3ea  call    __security_check_cookie
0x18000e3ef  add     rsp, 258h
0x18000e3f6  pop     r15
0x18000e3f8  pop     r14
0x18000e3fa  pop     rdi
0x18000e3fb  pop     rsi
0x18000e3fc  pop     rbx
0x18000e3fd  pop     rbp
0x18000e3fe  retn
0x18000e3ff  mov     rcx, [rbp+188h]; this
0x18000e406  mov     edx, 0A0Bh; void *
0x18000e40b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000e411  mov     rcx, [rbp+188h]; this
0x18000e418  mov     edx, 0A0Bh; void *
0x18000e41d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000e423  mov     rcx, [rbp+188h]; this
0x18000e42a  mov     edx, 0A0Bh; void *
0x18000e42f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000e435  mov     rcx, [rbp+188h]; this
0x18000e43c  mov     edx, 0A0Bh; void *
0x18000e441  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000e447  mov     rcx, [rbp+188h]; this
0x18000e44e  mov     edx, 0A0Bh; void *
0x18000e453  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000e459  mov     rcx, [rbp+188h]; this
0x18000e460  mov     edx, 0A0Bh; void *
0x18000e465  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
