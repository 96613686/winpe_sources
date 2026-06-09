# SuspendImpersonate(void * *)

- ea: `0x18004ca0c`
- end: `0x18004ca7d`
- name: `?SuspendImpersonate@@YAJPEAPEAX@Z`
- size: `113`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800369a0`

## callees

- `0x18003f62c`
- `0x18004ca0c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004ca45`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004ca45`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004ca30`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004ca30`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18004ca53`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18004ca53`

## string_xrefs

- `0x18004ca60`: `onecore\internal\com\inc\combase\impersonate.hxx`

## pseudocode

```c
__int64 __fastcall SuspendImpersonate(PHANDLE TokenHandle)
{
  HANDLE CurrentThread; // rax
  const char *v4; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !NtCurrentTeb()->IsImpersonating )
  {
    *TokenHandle = 0;
    return 0;
  }
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 4u, 1, TokenHandle) )
  {
    SetThreadToken(0, 0);
    return 0;
  }
  *TokenHandle = 0;
  return wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x3D,
           (unsigned int)"onecore\\internal\\com\\inc\\combase\\impersonate.hxx",
           v4);
}

```

## disassembly

```asm
0x18004ca0c  push    rbx
0x18004ca0e  sub     rsp, 20h
0x18004ca12  mov     eax, gs:179Ch
0x18004ca1a  mov     rbx, rcx
0x18004ca1d  test    eax, eax
0x18004ca1f  jnz     short loc_18004CA30
0x18004ca21  mov     qword ptr [rcx], 0
0x18004ca28  xor     eax, eax
0x18004ca2a  add     rsp, 20h
0x18004ca2e  pop     rbx
0x18004ca2f  retn
0x18004ca30  call    cs:__imp_GetCurrentThread
0x18004ca36  mov     edx, 4; DesiredAccess
0x18004ca3b  mov     r9, rbx; TokenHandle
0x18004ca3e  mov     rcx, rax; ThreadHandle
0x18004ca41  lea     r8d, [rdx-3]; OpenAsSelf
0x18004ca45  call    cs:__imp_OpenThreadToken
0x18004ca4b  test    eax, eax
0x18004ca4d  jz      short loc_18004CA5B
0x18004ca4f  xor     edx, edx; Token
0x18004ca51  xor     ecx, ecx; Thread
0x18004ca53  call    cs:__imp_SetThreadToken
0x18004ca59  jmp     short loc_18004CA28
0x18004ca5b  mov     rcx, [rsp+28h]; this
0x18004ca60  lea     r8, aOnecoreInterna_4; "onecore\\internal\\com\\inc\\combase\\i"...
0x18004ca67  mov     edx, 3Dh ; '='; void *
0x18004ca6c  mov     qword ptr [rbx], 0
0x18004ca73  add     rsp, 20h
0x18004ca77  pop     rbx
0x18004ca78  jmp     ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
```
