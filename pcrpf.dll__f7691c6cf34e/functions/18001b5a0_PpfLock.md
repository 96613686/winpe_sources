# PpfLock

- ea: `0x18001b5a0`
- end: `0x18001b7de`
- name: `PpfLock`
- size: `574`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `8`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180013ef4`
- `0x1800141f4`
- `0x180015ff8`
- `0x180016498`
- `0x18001b140`
- `0x18001b930`
- `0x180052728`
- `0x180053280`

## callees

- `0x180009c44`
- `0x18000dfa0`
- `0x180013e6c`
- `0x18001b5a0`
- `0x18002d5ec`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18001b634`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18001b634`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001b6da`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001b6da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b69b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b69b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b672`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b705`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b7b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b672`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b705`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b7b8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001b5cb`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001b5cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b5fb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b687`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b71e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b77a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b7cd`

## string_xrefs

- `0x18001b5df`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`
- `0x18001b652`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`
- `0x18001b6c5`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`
- `0x18001b737`: `Owning thread abandoned mutex`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall PpfLock(_QWORD *a1)
{
  const char *v2; // r9
  unsigned int LastError; // ebx
  char *v5; // rbx
  const char *v6; // r9
  unsigned int v7; // edi
  DWORD v8; // eax
  const char *v9; // r9
  char *v10; // [rsp+28h] [rbp-30h]
  _SECURITY_ATTRIBUTES MutexAttributes; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+20h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+88h] [rbp+30h] BYREF

  SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(L"D:P(A;;GA;;;BA)(A;;GA;;;SY)", 1u, &SecurityDescriptor, 0) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x57C,
                  (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
                  v2);
    if ( SecurityDescriptor )
      ((void (*)(void))LocalFree)();
    return LastError;
  }
  *(_QWORD *)&MutexAttributes.nLength = 24;
  *(_QWORD *)&MutexAttributes.bInheritHandle = 0;
  MutexAttributes.lpSecurityDescriptor = SecurityDescriptor;
  v5 = (char *)CreateMutexW(&MutexAttributes, 1, L"Global\\ppf-3b94dddc-1799-4242-9637-203f8c6b8c1a");
  if ( ((unsigned __int64)(v5 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v7 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x583,
           (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
           v6);
    if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v5);
    if ( !SecurityDescriptor )
      return v7;
LABEL_9:
    ((void (*)(void))LocalFree)();
    return v7;
  }
  if ( GetLastError() != 183 )
    goto LABEL_19;
  PpfTraceLogFormat("onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp", 0x586u, "PpfLock", "Waiting on mutex");
  v8 = WaitForSingleObject(v5, 0xFFFFFFFF);
  switch ( v8 )
  {
    case 0u:
LABEL_18:
      PpfTraceLogFormat("onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp", 0x594u, "PpfLock", "Mutex owned");
LABEL_19:
      *a1 = v5;
      if ( SecurityDescriptor )
        ((void (*)(void))LocalFree)();
      return 0;
    case 0xFFFFFFFF:
      v7 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x58A,
             (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
             v9);
      CloseHandle(v5);
      if ( !SecurityDescriptor )
        return v7;
      goto LABEL_9;
    case 0x80u:
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0x58D,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
        (const char *)0x80004004LL,
        (int)"Owning thread abandoned mutex",
        v10);
      goto LABEL_18;
  }
  LODWORD(v10) = v8;
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0x591,
    (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
    (const char *)0x8000FFFFLL,
    (int)"Unexpected wait error: 0x%x",
    v10);
  CloseHandle(v5);
  if ( SecurityDescriptor )
    ((void (*)(void))LocalFree)();
  return 2147549183LL;
}

```

## disassembly

```asm
0x18001b5a0  push    rbp
0x18001b5a2  push    rbx
0x18001b5a3  push    rsi
0x18001b5a4  push    rdi
0x18001b5a5  mov     rbp, rsp
0x18001b5a8  sub     rsp, 58h
0x18001b5ac  mov     rsi, rcx
0x18001b5af  mov     [rbp+SecurityDescriptor], 0
0x18001b5b7  xor     r9d, r9d; SecurityDescriptorSize
0x18001b5ba  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18001b5be  lea     ebx, [r9+1]
0x18001b5c2  mov     edx, ebx; StringSDRevision
0x18001b5c4  lea     rcx, StringSecurityDescriptor; "D:P(A;;GA;;;BA)(A;;GA;;;SY)"
0x18001b5cb  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18001b5d2  nop     dword ptr [rax+rax+00h]
0x18001b5d7  test    eax, eax
0x18001b5d9  jnz     short loc_18001B60F
0x18001b5db  mov     rcx, [rbp+20h]; this
0x18001b5df  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x18001b5e6  mov     edx, 57Ch; void *
0x18001b5eb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001b5f0  mov     ebx, eax
0x18001b5f2  mov     rcx, [rbp+SecurityDescriptor]
0x18001b5f6  test    rcx, rcx
0x18001b5f9  jz      short loc_18001B608
0x18001b5fb  mov     rax, cs:__imp_LocalFree
0x18001b602  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b607  nop
0x18001b608  mov     eax, ebx
0x18001b60a  jmp     loc_18001B789
0x18001b60f  mov     qword ptr [rbp+MutexAttributes.nLength], 18h
0x18001b617  mov     qword ptr [rbp+MutexAttributes.bInheritHandle], 0
0x18001b61f  mov     rax, [rbp+SecurityDescriptor]
0x18001b623  mov     [rbp+MutexAttributes.lpSecurityDescriptor], rax
0x18001b627  lea     r8, Name; "Global\\ppf-3b94dddc-1799-4242-9637-203"...
0x18001b62e  mov     edx, ebx; bInitialOwner
0x18001b630  lea     rcx, [rbp+MutexAttributes]; lpMutexAttributes
0x18001b634  call    cs:__imp_CreateMutexW
0x18001b63b  nop     dword ptr [rax+rax+00h]
0x18001b640  mov     rbx, rax
0x18001b643  inc     rax
0x18001b646  test    rax, 0FFFFFFFFFFFFFFFEh
0x18001b64c  jnz     short loc_18001B69B
0x18001b64e  mov     rcx, [rbp+20h]; this
0x18001b652  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x18001b659  mov     edx, 583h; void *
0x18001b65e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001b663  mov     edi, eax
0x18001b665  lea     rcx, [rbx-1]
0x18001b669  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18001b66d  ja      short loc_18001B67E
0x18001b66f  mov     rcx, rbx; hObject
0x18001b672  call    cs:__imp_CloseHandle
0x18001b679  nop     dword ptr [rax+rax+00h]
0x18001b67e  mov     rcx, [rbp+SecurityDescriptor]
0x18001b682  test    rcx, rcx
0x18001b685  jz      short loc_18001B694
0x18001b687  mov     rax, cs:__imp_LocalFree
0x18001b68e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b693  nop
0x18001b694  mov     eax, edi
0x18001b696  jmp     loc_18001B789
0x18001b69b  call    cs:__imp_GetLastError
0x18001b6a2  nop     dword ptr [rax+rax+00h]
0x18001b6a7  cmp     eax, 0B7h
0x18001b6ac  jnz     loc_18001B76E
0x18001b6b2  lea     r9, aWaitingOnMutex; "Waiting on mutex"
0x18001b6b9  lea     r8, aPpflock_0; "PpfLock"
0x18001b6c0  mov     edx, 586h; unsigned int
0x18001b6c5  lea     rdi, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x18001b6cc  mov     rcx, rdi; char *
0x18001b6cf  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18001b6d4  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001b6d7  mov     rcx, rbx; hHandle
0x18001b6da  call    cs:__imp_WaitForSingleObject
0x18001b6e1  nop     dword ptr [rax+rax+00h]
0x18001b6e6  test    eax, eax
0x18001b6e8  jz      short loc_18001B753
0x18001b6ea  mov     rcx, [rbp+20h]; this
0x18001b6ee  mov     r8, rdi; unsigned int
0x18001b6f1  cmp     eax, 0FFFFFFFFh
0x18001b6f4  jnz     short loc_18001B730
0x18001b6f6  mov     edx, 58Ah; void *
0x18001b6fb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001b700  mov     edi, eax
0x18001b702  mov     rcx, rbx; hObject
0x18001b705  call    cs:__imp_CloseHandle
0x18001b70c  nop     dword ptr [rax+rax+00h]
0x18001b711  mov     rcx, [rbp+SecurityDescriptor]
0x18001b715  test    rcx, rcx
0x18001b718  jz      loc_18001B694
0x18001b71e  mov     rax, cs:__imp_LocalFree
0x18001b725  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b72a  nop
0x18001b72b  jmp     loc_18001B694
0x18001b730  cmp     eax, 80h
0x18001b735  jnz     short loc_18001B793
0x18001b737  lea     rax, aOwningThreadAb; "Owning thread abandoned mutex"
0x18001b73e  mov     qword ptr [rsp+58h+var_38], rax; int
0x18001b743  mov     r9d, 80004004h; char *
0x18001b749  mov     edx, 58Dh; void *
0x18001b74e  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001b753  lea     r9, aMutexOwned; "Mutex owned"
0x18001b75a  lea     r8, aPpflock_0; "PpfLock"
0x18001b761  mov     edx, 594h; unsigned int
0x18001b766  mov     rcx, rdi; char *
0x18001b769  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18001b76e  mov     [rsi], rbx
0x18001b771  mov     rcx, [rbp+SecurityDescriptor]
0x18001b775  test    rcx, rcx
0x18001b778  jz      short loc_18001B787
0x18001b77a  mov     rax, cs:__imp_LocalFree
0x18001b781  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b786  nop
0x18001b787  xor     eax, eax
0x18001b789  add     rsp, 58h
0x18001b78d  pop     rdi
0x18001b78e  pop     rsi
0x18001b78f  pop     rbx
0x18001b790  pop     rbp
0x18001b791  retn
0x18001b793  mov     dword ptr [rsp+58h+var_30], eax; char *
0x18001b797  lea     rax, aUnexpectedWait; "Unexpected wait error: 0x%x"
0x18001b79e  mov     qword ptr [rsp+58h+var_38], rax; int
0x18001b7a3  mov     esi, 8000FFFFh
0x18001b7a8  mov     r9d, esi; char *
0x18001b7ab  mov     edx, 591h; void *
0x18001b7b0  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001b7b5  mov     rcx, rbx; hObject
0x18001b7b8  call    cs:__imp_CloseHandle
0x18001b7bf  nop     dword ptr [rax+rax+00h]
0x18001b7c4  mov     rcx, [rbp+SecurityDescriptor]
0x18001b7c8  test    rcx, rcx
0x18001b7cb  jz      short loc_18001B7DA
0x18001b7cd  mov     rax, cs:__imp_LocalFree
0x18001b7d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b7d9  nop
0x18001b7da  mov     eax, esi
0x18001b7dc  jmp     short loc_18001B789
```
