# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x14000c4bc`
- end: `0x14000c78b`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `719`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x14000714c`
- `0x140007528`

## callees

- `0x140003450`
- `0x140008cf0`
- `0x14000b0d4`
- `0x14000b0f4`
- `0x14000be18`
- `0x14000c4bc`
- `0x14000ce7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000c553`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000c5e1`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000c553`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000c5e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c6d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c6d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c5a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c62a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c641`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c65f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c68a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c6bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c5a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c62a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c641`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c65f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c68a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c6bd`

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
0x14000c4bc  push    rbp
0x14000c4be  push    rbx
0x14000c4bf  push    rsi
0x14000c4c0  push    rdi
0x14000c4c1  push    r14
0x14000c4c3  push    r15
0x14000c4c5  lea     rbp, [rsp-158h]
0x14000c4cd  sub     rsp, 258h
0x14000c4d4  mov     rax, cs:__security_cookie
0x14000c4db  xor     rax, rsp
0x14000c4de  mov     [rbp+180h+var_40], rax
0x14000c4e5  xor     r15d, r15d
0x14000c4e8  lea     rax, [rsp+280h+Name]
0x14000c4ed  mov     esi, 104h
0x14000c4f2  mov     [r8], r15
0x14000c4f5  mov     edx, esi
0x14000c4f7  mov     r14, r8
0x14000c4fa  mov     r9d, 7FFFFFFEh
0x14000c500  test    r9, r9
0x14000c503  jz      short loc_14000C524
0x14000c505  movzx   r8d, word ptr [rcx]
0x14000c509  test    r8w, r8w
0x14000c50d  jz      short loc_14000C524
0x14000c50f  mov     [rax], r8w
0x14000c513  add     rcx, 2
0x14000c517  add     rax, 2
0x14000c51b  dec     r9
0x14000c51e  sub     rdx, 1
0x14000c522  jnz     short loc_14000C500
0x14000c524  test    rdx, rdx
0x14000c527  lea     rcx, [rax-2]
0x14000c52b  lea     r8, aP0; "_p0"
0x14000c532  mov     rdx, rsi; unsigned __int64
0x14000c535  cmovnz  rcx, rax
0x14000c539  mov     [rcx], r15w
0x14000c53d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000c542  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000c547  lea     r8, [rsp+280h+Name]; lpName
0x14000c54c  xor     edx, edx; bInheritHandle
0x14000c54e  mov     ecx, 1F0003h; dwDesiredAccess
0x14000c553  call    cs:__imp_OpenSemaphoreW
0x14000c55a  nop     dword ptr [rax+rax+00h]
0x14000c55f  mov     rbx, rax
0x14000c562  test    rax, rax
0x14000c565  jz      loc_14000C6D2
0x14000c56b  lea     rdx, [rsp+280h+var_25C]; int *
0x14000c570  mov     [rsp+280h+var_25C], r15d
0x14000c575  mov     rcx, rax; hHandle
0x14000c578  mov     [rsp+280h+var_260], r15d; int
0x14000c57d  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000c582  mov     edi, eax
0x14000c584  test    eax, eax
0x14000c586  jns     short loc_14000C5C1
0x14000c588  mov     rcx, [rbp+188h]; this
0x14000c58f  lea     r8, aWil; "wil"
0x14000c596  mov     r9d, eax; char *
0x14000c599  mov     edx, 0D6h; void *
0x14000c59e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c5a3  mov     rcx, rbx; hObject
0x14000c5a6  call    cs:__imp_CloseHandle
0x14000c5ad  nop     dword ptr [rax+rax+00h]
0x14000c5b2  test    eax, eax
0x14000c5b4  jz      loc_14000C755
0x14000c5ba  mov     eax, edi
0x14000c5bc  jmp     loc_14000C6FF
0x14000c5c1  lea     r8, asc_14006D5F0; "h"
0x14000c5c8  mov     rdx, rsi; unsigned __int64
0x14000c5cb  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000c5d0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000c5d5  lea     r8, [rsp+280h+Name]; lpName
0x14000c5da  xor     edx, edx; bInheritHandle
0x14000c5dc  mov     ecx, 1F0003h; dwDesiredAccess
0x14000c5e1  call    cs:__imp_OpenSemaphoreW
0x14000c5e8  nop     dword ptr [rax+rax+00h]
0x14000c5ed  mov     rdi, rax
0x14000c5f0  test    rax, rax
0x14000c5f3  jz      loc_14000C6A0
0x14000c5f9  lea     rdx, [rsp+280h+var_260]; int *
0x14000c5fe  mov     rcx, rax; hHandle
0x14000c601  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000c606  mov     esi, eax
0x14000c608  test    eax, eax
0x14000c60a  jns     short loc_14000C65C
0x14000c60c  mov     rcx, [rbp+188h]; this
0x14000c613  lea     r8, aWil; "wil"
0x14000c61a  mov     r9d, eax; char *
0x14000c61d  mov     edx, 0DEh; void *
0x14000c622  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c627  mov     rcx, rdi; hObject
0x14000c62a  call    cs:__imp_CloseHandle
0x14000c631  nop     dword ptr [rax+rax+00h]
0x14000c636  test    eax, eax
0x14000c638  jz      loc_14000C767
0x14000c63e  mov     rcx, rbx; hObject
0x14000c641  call    cs:__imp_CloseHandle
0x14000c648  nop     dword ptr [rax+rax+00h]
0x14000c64d  test    eax, eax
0x14000c64f  jz      loc_14000C779
0x14000c655  mov     eax, esi
0x14000c657  jmp     loc_14000C6FF
0x14000c65c  mov     rcx, rdi; hObject
0x14000c65f  call    cs:__imp_CloseHandle
0x14000c666  nop     dword ptr [rax+rax+00h]
0x14000c66b  test    eax, eax
0x14000c66d  jz      loc_14000C71F
0x14000c673  movsxd  rax, [rsp+280h+var_25C]
0x14000c678  movsxd  rcx, [rsp+280h+var_260]
0x14000c67d  shl     rcx, 1Fh
0x14000c681  or      rcx, rax
0x14000c684  mov     [r14], rcx
0x14000c687  mov     rcx, rbx; hObject
0x14000c68a  call    cs:__imp_CloseHandle
0x14000c691  nop     dword ptr [rax+rax+00h]
0x14000c696  test    eax, eax
0x14000c698  jz      loc_14000C731
0x14000c69e  jmp     short loc_14000C6E3
0x14000c6a0  mov     rcx, [rbp+188h]; this
0x14000c6a7  lea     r8, aWil; "wil"
0x14000c6ae  mov     edx, 0DCh; void *
0x14000c6b3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000c6b8  mov     rcx, rbx; hObject
0x14000c6bb  mov     edi, eax
0x14000c6bd  call    cs:__imp_CloseHandle
0x14000c6c4  nop     dword ptr [rax+rax+00h]
0x14000c6c9  test    eax, eax
0x14000c6cb  jz      short loc_14000C743
0x14000c6cd  jmp     loc_14000C5BA
0x14000c6d2  call    cs:__imp_GetLastError
0x14000c6d9  nop     dword ptr [rax+rax+00h]
0x14000c6de  cmp     eax, 2
0x14000c6e1  jnz     short loc_14000C6E7
0x14000c6e3  xor     eax, eax
0x14000c6e5  jmp     short loc_14000C6FF
0x14000c6e7  mov     rcx, [rbp+188h]; this
0x14000c6ee  lea     r8, aWil; "wil"
0x14000c6f5  mov     edx, 0D0h; void *
0x14000c6fa  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000c6ff  mov     rcx, [rbp+180h+var_40]
0x14000c706  xor     rcx, rsp; StackCookie
0x14000c709  call    __security_check_cookie
0x14000c70e  add     rsp, 258h
0x14000c715  pop     r15
0x14000c717  pop     r14
0x14000c719  pop     rdi
0x14000c71a  pop     rsi
0x14000c71b  pop     rbx
0x14000c71c  pop     rbp
0x14000c71d  retn
0x14000c71f  mov     rcx, [rbp+188h]; this
0x14000c726  mov     edx, 0A0Bh; void *
0x14000c72b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000c731  mov     rcx, [rbp+188h]; this
0x14000c738  mov     edx, 0A0Bh; void *
0x14000c73d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000c743  mov     rcx, [rbp+188h]; this
0x14000c74a  mov     edx, 0A0Bh; void *
0x14000c74f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000c755  mov     rcx, [rbp+188h]; this
0x14000c75c  mov     edx, 0A0Bh; void *
0x14000c761  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000c767  mov     rcx, [rbp+188h]; this
0x14000c76e  mov     edx, 0A0Bh; void *
0x14000c773  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000c779  mov     rcx, [rbp+188h]; this
0x14000c780  mov     edx, 0A0Bh; void *
0x14000c785  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
