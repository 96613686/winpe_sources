# DasHostCloseQuery

- ea: `0x14000a920`
- end: `0x14000aad6`
- name: `DasHostCloseQuery`
- size: `438`
- prototype: `__int64 __fastcall(void **, int, int)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x14000adb0`
- `0x140015bf0`

## callees

- `0x140008eec`
- `0x140008f88`
- `0x140009cd8`
- `0x14000a920`
- `0x14001c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000a999`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000a999`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000aa3e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000aa3e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000a9aa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000a9aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000aa2e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000aa71`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000aa2e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000aa71`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000a9fd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000aa4b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000a9fd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000aa4b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000aa85`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000aa85`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000aa77`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000aa77`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a9c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a9db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a9c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a9db`

## pseudocode

```c
__int64 __fastcall DasHostCloseQuery(void **a1, int a2, int a3)
{
  char *v3; // rdi
  __int64 v5; // rcx
  __int64 v6; // rsi
  void *v7; // rcx
  void *v8; // rcx
  struct _RTL_CRITICAL_SECTION *v9; // rcx
  _QWORD *v10; // rax
  struct _DAS_HOST_QUERY_RESULT *v11; // rsi
  __int64 v12; // rcx
  _QWORD *v13; // rdx
  void **v14; // rax
  HANDLE ProcessHeap; // rax
  int v16; // edx
  int v17; // r8d
  int v19; // [rsp+28h] [rbp-50h]

  v3 = (char *)*a1;
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 5), a2, a3, 26, &WPP_92038ab37ee4317b05ca4ff2fd992641_Traceguids);
  v5 = *((_QWORD *)v3 + 4);
  if ( v5 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 48LL))(v5);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v3 + 4) + 16LL))(*((_QWORD *)v3 + 4));
  }
  v6 = *((_QWORD *)v3 + 5);
  if ( v6 )
  {
    AcquireSRWLockExclusive((PSRWLOCK)(v6 + 96));
    *(_DWORD *)(v6 + 104) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)(v6 + 96));
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v3 + 5) + 16LL))(*((_QWORD *)v3 + 5));
  }
  v7 = (void *)*((_QWORD *)v3 + 9);
  if ( v7 )
    CloseHandle(v7);
  v8 = (void *)*((_QWORD *)v3 + 20);
  if ( v8 )
  {
    CloseHandle(v8);
    *((_QWORD *)v3 + 20) = 0;
  }
  while ( 1 )
  {
    v9 = (struct _RTL_CRITICAL_SECTION *)(v3 + 88);
    if ( *((char **)v3 + 16) == v3 + 128 )
      break;
    EnterCriticalSection(v9);
    v10 = v3 + 128;
    v11 = (struct _DAS_HOST_QUERY_RESULT *)*((_QWORD *)v3 + 16);
    if ( *((char **)v11 + 1) != v3 + 128 )
      goto LABEL_20;
    v12 = *(_QWORD *)v11;
    if ( *(struct _DAS_HOST_QUERY_RESULT **)(*(_QWORD *)v11 + 8LL) != v11 )
      goto LABEL_20;
    *v10 = v12;
    *(_QWORD *)(v12 + 8) = v10;
    LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 88));
    FreeResult(v11);
  }
  DeleteCriticalSection(v9);
  EnterCriticalSection(&g_ActiveProviderQueriesList);
  v13 = *(_QWORD **)v3;
  if ( *(char **)(*(_QWORD *)v3 + 8LL) != v3 || (v14 = (void **)*((_QWORD *)v3 + 1), *v14 != v3) )
LABEL_20:
    __fastfail(3u);
  *v14 = v13;
  v13[1] = v14;
  LeaveCriticalSection(&g_ActiveProviderQueriesList);
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, v3);
  *a1 = 0;
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v16,
      v17,
      27,
      &WPP_92038ab37ee4317b05ca4ff2fd992641_Traceguids,
      v19,
      0);
  return 0;
}

```

## disassembly

```asm
0x14000a920  push    rbx
0x14000a922  push    rbp
0x14000a923  push    rsi
0x14000a924  push    rdi
0x14000a925  push    r12
0x14000a927  push    r13
0x14000a929  push    r14
0x14000a92b  sub     rsp, 40h
0x14000a92f  mov     rdi, [rcx]
0x14000a932  mov     r14, rcx
0x14000a935  lea     r13, WPP_RECORDER_INITIALIZED
0x14000a93c  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14000a943  lea     r12, WPP_92038ab37ee4317b05ca4ff2fd992641_Traceguids
0x14000a94a  jz      short loc_14000A967
0x14000a94c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a953  mov     r9d, 1Ah; int
0x14000a959  mov     [rsp+78h+MessageGuid], r12; MessageGuid
0x14000a95e  mov     rcx, [rcx+28h]; int
0x14000a962  call    WPP_RECORDER_SF_s
0x14000a967  mov     rcx, [rdi+20h]
0x14000a96b  test    rcx, rcx
0x14000a96e  jz      short loc_14000A98C
0x14000a970  mov     rax, [rcx]
0x14000a973  mov     rax, [rax+30h]
0x14000a977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a97c  mov     rcx, [rdi+20h]
0x14000a980  mov     rax, [rcx]
0x14000a983  mov     rax, [rax+10h]
0x14000a987  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a98c  mov     rsi, [rdi+28h]
0x14000a990  test    rsi, rsi
0x14000a993  jz      short loc_14000A9C0
0x14000a995  lea     rcx, [rsi+60h]; SRWLock
0x14000a999  call    cs:__imp_AcquireSRWLockExclusive
0x14000a99f  lea     rcx, [rsi+60h]; SRWLock
0x14000a9a3  mov     dword ptr [rsi+68h], 0
0x14000a9aa  call    cs:__imp_ReleaseSRWLockExclusive
0x14000a9b0  mov     rcx, [rdi+28h]
0x14000a9b4  mov     rax, [rcx]
0x14000a9b7  mov     rax, [rax+10h]
0x14000a9bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a9c0  mov     rcx, [rdi+48h]; hObject
0x14000a9c4  test    rcx, rcx
0x14000a9c7  jz      short loc_14000A9CF
0x14000a9c9  call    cs:__imp_CloseHandle
0x14000a9cf  mov     rcx, [rdi+0A0h]; hObject
0x14000a9d6  test    rcx, rcx
0x14000a9d9  jz      short loc_14000A9EC
0x14000a9db  call    cs:__imp_CloseHandle
0x14000a9e1  mov     qword ptr [rdi+0A0h], 0
0x14000a9ec  lea     rbx, [rdi+58h]
0x14000a9f0  lea     rbp, [rbx+28h]
0x14000a9f4  mov     rcx, rbx; lpCriticalSection
0x14000a9f7  cmp     [rbp+0], rbp
0x14000a9fb  jz      short loc_14000AA3E
0x14000a9fd  call    cs:__imp_EnterCriticalSection
0x14000aa03  lea     rax, [rdi+80h]
0x14000aa0a  mov     rsi, [rax]
0x14000aa0d  cmp     [rsi+8], rax
0x14000aa11  jnz     loc_14000AACF
0x14000aa17  mov     rcx, [rsi]
0x14000aa1a  cmp     [rcx+8], rsi
0x14000aa1e  jnz     loc_14000AACF
0x14000aa24  mov     [rax], rcx
0x14000aa27  mov     [rcx+8], rax
0x14000aa2b  mov     rcx, rbx; lpCriticalSection
0x14000aa2e  call    cs:__imp_LeaveCriticalSection
0x14000aa34  mov     rcx, rsi; lpMem
0x14000aa37  call    ?FreeResult@@YAXPEAU_DAS_HOST_QUERY_RESULT@@@Z; FreeResult(_DAS_HOST_QUERY_RESULT *)
0x14000aa3c  jmp     short loc_14000A9F4
0x14000aa3e  call    cs:__imp_DeleteCriticalSection
0x14000aa44  lea     rcx, ?g_ActiveProviderQueriesList@@3U_DAS_LOCKED_LIST@@A; lpCriticalSection
0x14000aa4b  call    cs:__imp_EnterCriticalSection
0x14000aa51  mov     rdx, [rdi]
0x14000aa54  cmp     [rdx+8], rdi
0x14000aa58  jnz     short loc_14000AACF
0x14000aa5a  mov     rax, [rdi+8]
0x14000aa5e  cmp     [rax], rdi
0x14000aa61  jnz     short loc_14000AACF
0x14000aa63  mov     [rax], rdx
0x14000aa66  lea     rcx, ?g_ActiveProviderQueriesList@@3U_DAS_LOCKED_LIST@@A; lpCriticalSection
0x14000aa6d  mov     [rdx+8], rax
0x14000aa71  call    cs:__imp_LeaveCriticalSection
0x14000aa77  call    cs:__imp_GetProcessHeap
0x14000aa7d  mov     r8, rdi; lpMem
0x14000aa80  xor     edx, edx; dwFlags
0x14000aa82  mov     rcx, rax; hHeap
0x14000aa85  call    cs:__imp_HeapFree
0x14000aa8b  mov     qword ptr [r14], 0
0x14000aa92  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14000aa99  jz      short loc_14000AABE
0x14000aa9b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000aaa2  mov     r9d, 1Bh; int
0x14000aaa8  mov     dword ptr [rsp+78h+var_48], 0; char
0x14000aab0  mov     [rsp+78h+MessageGuid], r12; MessageGuid
0x14000aab5  mov     rcx, [rcx+28h]; int
0x14000aab9  call    WPP_RECORDER_SF_sd
0x14000aabe  xor     eax, eax
0x14000aac0  add     rsp, 40h
0x14000aac4  pop     r14
0x14000aac6  pop     r13
0x14000aac8  pop     r12
0x14000aaca  pop     rdi
0x14000aacb  pop     rsi
0x14000aacc  pop     rbp
0x14000aacd  pop     rbx
0x14000aace  retn
0x14000aacf  mov     ecx, 3
0x14000aad4  int     29h; Win8: RtlFailFast(ecx)
```
