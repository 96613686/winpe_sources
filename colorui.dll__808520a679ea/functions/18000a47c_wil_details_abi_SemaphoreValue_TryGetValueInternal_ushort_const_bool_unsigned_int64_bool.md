# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000a47c`
- end: `0x18000a6f6`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `634`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180003828`
- `0x180003bf8`

## callees

- `0x180006350`
- `0x1800099d8`
- `0x1800099f8`
- `0x180009ed0`
- `0x18000a47c`
- `0x18000b404`
- `0x180018500`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000a64b`
- `KERNEL32!GetLastError` at `0x18000a64b`
- `KERNEL32!OpenSemaphoreW` at `0x18000a510`
- `KERNEL32!OpenSemaphoreW` at `0x18000a58c`
- `KERNEL32!OpenSemaphoreW` at `0x18000a510`
- `KERNEL32!OpenSemaphoreW` at `0x18000a58c`
- `KERNEL32!CloseHandle` at `0x18000a55d`
- `KERNEL32!CloseHandle` at `0x18000a5cf`
- `KERNEL32!CloseHandle` at `0x18000a5e0`
- `KERNEL32!CloseHandle` at `0x18000a5f5`
- `KERNEL32!CloseHandle` at `0x18000a61a`
- `KERNEL32!CloseHandle` at `0x18000a63c`
- `KERNEL32!CloseHandle` at `0x18000a55d`
- `KERNEL32!CloseHandle` at `0x18000a5cf`
- `KERNEL32!CloseHandle` at `0x18000a5e0`
- `KERNEL32!CloseHandle` at `0x18000a5f5`
- `KERNEL32!CloseHandle` at `0x18000a61a`
- `KERNEL32!CloseHandle` at `0x18000a63c`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  __int64 v6; // rdx
  __int64 v7; // r9
  WCHAR *v8; // rcx
  HANDLE v9; // rax
  void *v10; // rbx
  int ValueFromSemaphore; // eax
  __int64 v12; // rdx
  unsigned int LastError; // edi
  __int64 v14; // r8
  const char *v15; // r9
  HANDLE v17; // rax
  unsigned int v18; // r8d
  const char *v19; // r9
  void *v20; // rdi
  int v21; // eax
  unsigned int v22; // esi
  __int64 v23; // r8
  const char *v24; // r9
  __int64 v25; // r8
  const char *v26; // r9
  __int64 v27; // r8
  const char *v28; // r9
  __int64 v29; // r8
  const char *v30; // r9
  __int64 v31; // r8
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
  StringCbCatW(Name, v6, L"_p0");
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, (int)"wil", (const char *)(unsigned int)ValueFromSemaphore);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    return LastError;
  }
  StringCbCatW(Name, v12, L"h");
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
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v21);
  if ( !CloseHandle(v20) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
  return v22;
}

```

## disassembly

```asm
0x18000a47c  push    rbp
0x18000a47e  push    rbx
0x18000a47f  push    rsi
0x18000a480  push    rdi
0x18000a481  push    r14
0x18000a483  push    r15
0x18000a485  lea     rbp, [rsp-158h]
0x18000a48d  sub     rsp, 258h
0x18000a494  mov     rax, cs:__security_cookie
0x18000a49b  xor     rax, rsp
0x18000a49e  mov     [rbp+180h+var_40], rax
0x18000a4a5  xor     r15d, r15d
0x18000a4a8  lea     rax, [rsp+280h+Name]
0x18000a4ad  mov     [r8], r15
0x18000a4b0  mov     r14, r8
0x18000a4b3  mov     edx, 104h
0x18000a4b8  mov     r9d, 7FFFFFFEh
0x18000a4be  test    r9, r9
0x18000a4c1  jz      short loc_18000A4E2
0x18000a4c3  movzx   r8d, word ptr [rcx]
0x18000a4c7  test    r8w, r8w
0x18000a4cb  jz      short loc_18000A4E2
0x18000a4cd  mov     [rax], r8w
0x18000a4d1  add     rcx, 2
0x18000a4d5  add     rax, 2
0x18000a4d9  dec     r9
0x18000a4dc  sub     rdx, 1; unsigned __int64
0x18000a4e0  jnz     short loc_18000A4BE
0x18000a4e2  test    rdx, rdx
0x18000a4e5  lea     rcx, [rax-2]
0x18000a4e9  lea     r8, aP0; "_p0"
0x18000a4f0  cmovnz  rcx, rax
0x18000a4f4  mov     [rcx], r15w
0x18000a4f8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000a4fd  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x18000a502  mov     esi, 1F0003h
0x18000a507  lea     r8, [rsp+280h+Name]; lpName
0x18000a50c  mov     ecx, esi; dwDesiredAccess
0x18000a50e  xor     edx, edx; bInheritHandle
0x18000a510  call    cs:__imp_OpenSemaphoreW
0x18000a516  mov     rbx, rax
0x18000a519  test    rax, rax
0x18000a51c  jz      loc_18000A64B
0x18000a522  lea     rdx, [rsp+280h+var_25C]; int *
0x18000a527  mov     [rsp+280h+var_25C], r15d
0x18000a52c  mov     rcx, rax; hHandle
0x18000a52f  mov     [rsp+280h+var_260], r15d; int
0x18000a534  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000a539  mov     edi, eax
0x18000a53b  test    eax, eax
0x18000a53d  jns     short loc_18000A572
0x18000a53f  mov     rcx, [rbp+188h]; this
0x18000a546  lea     r8, aWil; "wil"
0x18000a54d  mov     r9d, eax; char *
0x18000a550  mov     edx, 0D6h; void *
0x18000a555  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a55a  mov     rcx, rbx; hObject
0x18000a55d  call    cs:__imp_CloseHandle
0x18000a563  test    eax, eax
0x18000a565  jz      loc_18000A6C0
0x18000a56b  mov     eax, edi
0x18000a56d  jmp     loc_18000A66B
0x18000a572  lea     r8, asc_18001C560; "h"
0x18000a579  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000a57e  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x18000a583  lea     r8, [rsp+280h+Name]; lpName
0x18000a588  xor     edx, edx; bInheritHandle
0x18000a58a  mov     ecx, esi; dwDesiredAccess
0x18000a58c  call    cs:__imp_OpenSemaphoreW
0x18000a592  mov     rdi, rax
0x18000a595  test    rax, rax
0x18000a598  jz      loc_18000A626
0x18000a59e  lea     rdx, [rsp+280h+var_260]; int *
0x18000a5a3  mov     rcx, rax; hHandle
0x18000a5a6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000a5ab  mov     esi, eax
0x18000a5ad  test    eax, eax
0x18000a5af  jns     short loc_18000A5F2
0x18000a5b1  mov     rcx, [rbp+188h]; this
0x18000a5b8  lea     r8, aWil; "wil"
0x18000a5bf  mov     r9d, eax; char *
0x18000a5c2  mov     edx, 0DEh; void *
0x18000a5c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a5cc  mov     rcx, rdi; hObject
0x18000a5cf  call    cs:__imp_CloseHandle
0x18000a5d5  test    eax, eax
0x18000a5d7  jz      loc_18000A6D2
0x18000a5dd  mov     rcx, rbx; hObject
0x18000a5e0  call    cs:__imp_CloseHandle
0x18000a5e6  test    eax, eax
0x18000a5e8  jz      loc_18000A6E4
0x18000a5ee  mov     eax, esi
0x18000a5f0  jmp     short loc_18000A66B
0x18000a5f2  mov     rcx, rdi; hObject
0x18000a5f5  call    cs:__imp_CloseHandle
0x18000a5fb  test    eax, eax
0x18000a5fd  jz      loc_18000A68A
0x18000a603  movsxd  rax, [rsp+280h+var_25C]
0x18000a608  movsxd  rcx, [rsp+280h+var_260]
0x18000a60d  shl     rcx, 1Fh
0x18000a611  or      rcx, rax
0x18000a614  mov     [r14], rcx
0x18000a617  mov     rcx, rbx; hObject
0x18000a61a  call    cs:__imp_CloseHandle
0x18000a620  test    eax, eax
0x18000a622  jz      short loc_18000A69C
0x18000a624  jmp     short loc_18000A656
0x18000a626  mov     rcx, [rbp+188h]; this
0x18000a62d  mov     edx, 0DCh; void *
0x18000a632  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a637  mov     rcx, rbx; hObject
0x18000a63a  mov     edi, eax
0x18000a63c  call    cs:__imp_CloseHandle
0x18000a642  test    eax, eax
0x18000a644  jz      short loc_18000A6AE
0x18000a646  jmp     loc_18000A56B
0x18000a64b  call    cs:__imp_GetLastError
0x18000a651  cmp     eax, 2
0x18000a654  jnz     short loc_18000A65A
0x18000a656  xor     eax, eax
0x18000a658  jmp     short loc_18000A66B
0x18000a65a  mov     rcx, [rbp+188h]; this
0x18000a661  mov     edx, 0D0h; void *
0x18000a666  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a66b  mov     rcx, [rbp+180h+var_40]
0x18000a672  xor     rcx, rsp; StackCookie
0x18000a675  call    __security_check_cookie
0x18000a67a  add     rsp, 258h
0x18000a681  pop     r15
0x18000a683  pop     r14
0x18000a685  pop     rdi
0x18000a686  pop     rsi
0x18000a687  pop     rbx
0x18000a688  pop     rbp
0x18000a689  retn
0x18000a68a  mov     rcx, [rbp+188h]; this
0x18000a691  mov     edx, 0A0Bh; void *
0x18000a696  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a69c  mov     rcx, [rbp+188h]; this
0x18000a6a3  mov     edx, 0A0Bh; void *
0x18000a6a8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a6ae  mov     rcx, [rbp+188h]; this
0x18000a6b5  mov     edx, 0A0Bh; void *
0x18000a6ba  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a6c0  mov     rcx, [rbp+188h]; this
0x18000a6c7  mov     edx, 0A0Bh; void *
0x18000a6cc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a6d2  mov     rcx, [rbp+188h]; this
0x18000a6d9  mov     edx, 0A0Bh; void *
0x18000a6de  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a6e4  mov     rcx, [rbp+188h]; this
0x18000a6eb  mov     edx, 0A0Bh; void *
0x18000a6f0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
