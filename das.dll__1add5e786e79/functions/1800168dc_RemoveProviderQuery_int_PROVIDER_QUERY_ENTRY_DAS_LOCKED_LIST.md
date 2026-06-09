# RemoveProviderQuery(int,_PROVIDER_QUERY_ENTRY *,_DAS_LOCKED_LIST *)

- ea: `0x1800168dc`
- end: `0x180016b0d`
- name: `?RemoveProviderQuery@@YAXHPEAU_PROVIDER_QUERY_ENTRY@@PEAU_DAS_LOCKED_LIST@@@Z`
- size: `561`
- prototype: `void(int, struct _PROVIDER_QUERY_ENTRY *, struct _DAS_LOCKED_LIST *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800154b4`
- `0x180020168`
- `0x18005379c`

## callees

- `0x1800168dc`
- `0x180016cc8`
- `0x18001a268`
- `0x180062514`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001691b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016ab9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001691b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016ab9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800168fc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016a98`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800168fc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016a98`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016a5b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016a5b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016a86`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016a86`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016aa7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016aa7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016adf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016adf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016aed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016aed`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180016979`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180016979`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180016967`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180016967`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001699d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001699d`

## pseudocode

```c
void __fastcall RemoveProviderQuery(int a1, RTL_SRWLOCK *a2, struct _RTL_CRITICAL_SECTION *a3)
{
  _QWORD *v5; // rax
  const char *v6; // r9
  _QWORD *v7; // rax
  struct _TP_WAIT *v8; // rcx
  void *v9; // rcx
  CQueryCallback *v10; // rcx
  __int64 v11; // rcx
  _QWORD *v12; // rdx
  LPVOID *v13; // rcx
  LPVOID v14; // rax
  std::_Ref_count_base *v15; // rcx
  void *v16; // rbx
  HANDLE ProcessHeap; // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  LPVOID lpMem; // [rsp+38h] [rbp+10h] BYREF
  LPVOID *p_lpMem; // [rsp+48h] [rbp+20h] BYREF

  lpMem = a2;
  AcquireSRWLockExclusive(a2 + 21);
  *((_DWORD *)lpMem + 44) = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)lpMem + 21);
  v5 = lpMem;
  if ( a1 )
  {
    if ( *((_QWORD *)lpMem + 10) )
    {
      try
      {
        p_lpMem = &lpMem;
        lambda_0f0953e5aae94c2e9c0b0e664a2acf1c_::operator()(&p_lpMem);
        v5 = lpMem;
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0x1F1,
          (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providerquerymanagement.cpp",
          v6);
        return;
      }
    }
    v5[10] = 0;
    v7 = lpMem;
    v8 = (struct _TP_WAIT *)*((_QWORD *)lpMem + 19);
    if ( v8 )
    {
      WaitForThreadpoolWaitCallbacks(v8, 1);
      CloseThreadpoolWait(*((PTP_WAIT *)lpMem + 19));
      *((_QWORD *)lpMem + 19) = 0;
      v7 = lpMem;
    }
    v9 = (void *)v7[9];
    if ( v9 )
    {
      CloseHandle(v9);
      *((_QWORD *)lpMem + 9) = 0;
    }
  }
  else
  {
    if ( !*((_QWORD *)lpMem + 7) )
      goto LABEL_15;
    v10 = (CQueryCallback *)*((_QWORD *)lpMem + 5);
    if ( v10 )
    {
      CQueryCallback::InactivateContext(v10);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)lpMem + 5) + 16LL))(*((_QWORD *)lpMem + 5));
      *((_QWORD *)lpMem + 5) = 0;
      v5 = lpMem;
    }
    v11 = v5[4];
    if ( *((_DWORD *)v5 + 45) )
    {
      if ( !v11 )
        goto LABEL_15;
    }
    else if ( !v11 )
    {
      goto LABEL_15;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 48LL))(v11);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)lpMem + 4) + 16LL))(*((_QWORD *)lpMem + 4));
    *((_QWORD *)lpMem + 4) = 0;
  }
LABEL_15:
  if ( a3 )
  {
    EnterCriticalSection(a3);
    v12 = *(_QWORD **)lpMem;
    if ( *(LPVOID *)(*(_QWORD *)lpMem + 8LL) != lpMem || (v13 = (LPVOID *)*((_QWORD *)lpMem + 1), *v13 != lpMem) )
      __fastfail(3u);
    *v13 = v12;
    v12[1] = v13;
    LeaveCriticalSection(a3);
    AcquireSRWLockExclusive((PSRWLOCK)lpMem + 21);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)lpMem + 88));
    ReleaseSRWLockExclusive((PSRWLOCK)lpMem + 21);
    v14 = lpMem;
    *((_QWORD *)lpMem + 7) = 0;
    v15 = (std::_Ref_count_base *)*((_QWORD *)v14 + 8);
    *((_QWORD *)v14 + 8) = 0;
    if ( v15 )
      std::_Ref_count_base::_Decref(v15);
    v16 = lpMem;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v16);
  }
}

```

## disassembly

```asm
0x1800168dc  mov     [rsp+arg_0], rbx
0x1800168e1  mov     [rsp+arg_10], rsi
0x1800168e6  mov     [rsp+lpMem], rdx
0x1800168eb  push    rdi
0x1800168ec  sub     rsp, 20h
0x1800168f0  mov     rbx, r8
0x1800168f3  mov     edi, ecx
0x1800168f5  lea     rcx, [rdx+0A8h]; SRWLock
0x1800168fc  call    cs:__imp_AcquireSRWLockExclusive
0x180016902  xor     esi, esi
0x180016904  mov     rax, [rsp+28h+lpMem]
0x180016909  mov     [rax+0B0h], esi
0x18001690f  mov     rcx, [rsp+28h+lpMem]
0x180016914  add     rcx, 0A8h; SRWLock
0x18001691b  call    cs:__imp_ReleaseSRWLockExclusive
0x180016921  mov     rax, [rsp+28h+lpMem]
0x180016926  test    edi, edi
0x180016928  jz      loc_1800169B1
0x18001692e  cmp     [rax+50h], rsi
0x180016932  jz      short loc_18001694D
0x180016934  lea     rax, [rsp+28h+lpMem]
0x180016939  mov     [rsp+28h+arg_18], rax
0x18001693e  lea     rcx, [rsp+28h+arg_18]
0x180016943  call    _lambda_0f0953e5aae94c2e9c0b0e664a2acf1c___operator__
0x180016948  mov     rax, [rsp+28h+lpMem]
0x18001694d  mov     [rax+50h], rsi
0x180016951  mov     rax, [rsp+28h+lpMem]
0x180016956  mov     rcx, [rax+98h]; pwa
0x18001695d  test    rcx, rcx
0x180016960  jz      short loc_180016990
0x180016962  mov     edx, 1; fCancelPendingCallbacks
0x180016967  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18001696d  mov     rcx, [rsp+28h+lpMem]
0x180016972  mov     rcx, [rcx+98h]; pwa
0x180016979  call    cs:__imp_CloseThreadpoolWait
0x18001697f  mov     rax, [rsp+28h+lpMem]
0x180016984  mov     [rax+98h], rsi
0x18001698b  mov     rax, [rsp+28h+lpMem]
0x180016990  mov     rcx, [rax+48h]; hObject
0x180016994  test    rcx, rcx
0x180016997  jz      loc_180016A4F
0x18001699d  call    cs:__imp_CloseHandle
0x1800169a3  mov     rax, [rsp+28h+lpMem]
0x1800169a8  mov     [rax+48h], rsi
0x1800169ac  jmp     loc_180016A4F
0x1800169b1  cmp     [rax+38h], rsi
0x1800169b5  jz      loc_180016A4F
0x1800169bb  mov     rcx, [rax+28h]; this
0x1800169bf  test    rcx, rcx
0x1800169c2  jz      short loc_1800169EC
0x1800169c4  call    ?InactivateContext@CQueryCallback@@QEAAJXZ; CQueryCallback::InactivateContext(void)
0x1800169c9  mov     rax, [rsp+28h+lpMem]
0x1800169ce  mov     rcx, [rax+28h]
0x1800169d2  mov     rax, [rcx]
0x1800169d5  mov     rax, [rax+10h]
0x1800169d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169de  mov     rax, [rsp+28h+lpMem]
0x1800169e3  mov     [rax+28h], rsi
0x1800169e7  mov     rax, [rsp+28h+lpMem]
0x1800169ec  mov     rcx, [rax+20h]
0x1800169f0  cmp     [rax+0B4h], esi
0x1800169f6  jz      short loc_180016A20
0x1800169f8  test    rcx, rcx
0x1800169fb  jz      short loc_180016A4F
0x1800169fd  mov     rax, [rcx]
0x180016a00  mov     rax, [rax+30h]
0x180016a04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a09  mov     rax, [rsp+28h+lpMem]
0x180016a0e  mov     rcx, [rax+20h]
0x180016a12  mov     rax, [rcx]
0x180016a15  mov     rax, [rax+10h]
0x180016a19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a1e  jmp     short loc_180016A46
0x180016a20  test    rcx, rcx
0x180016a23  jz      short loc_180016A4F
0x180016a25  mov     rax, [rcx]
0x180016a28  mov     rax, [rax+30h]
0x180016a2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a31  mov     rax, [rsp+28h+lpMem]
0x180016a36  mov     rcx, [rax+20h]
0x180016a3a  mov     rax, [rcx]
0x180016a3d  mov     rax, [rax+10h]
0x180016a41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a46  mov     rax, [rsp+28h+lpMem]
0x180016a4b  mov     [rax+20h], rsi
0x180016a4f  test    rbx, rbx
0x180016a52  jz      loc_180016AF4
0x180016a58  mov     rcx, rbx; lpCriticalSection
0x180016a5b  call    cs:__imp_EnterCriticalSection
0x180016a61  mov     rax, [rsp+28h+lpMem]
0x180016a66  mov     rdx, [rax]
0x180016a69  cmp     [rdx+8], rax
0x180016a6d  jnz     loc_180016AF6
0x180016a73  mov     rcx, [rax+8]
0x180016a77  cmp     [rcx], rax
0x180016a7a  jnz     short loc_180016AF6
0x180016a7c  mov     [rcx], rdx
0x180016a7f  mov     [rdx+8], rcx
0x180016a83  mov     rcx, rbx; lpCriticalSection
0x180016a86  call    cs:__imp_LeaveCriticalSection
0x180016a8c  mov     rcx, [rsp+28h+lpMem]
0x180016a91  add     rcx, 0A8h; SRWLock
0x180016a98  call    cs:__imp_AcquireSRWLockExclusive
0x180016a9e  mov     rcx, [rsp+28h+lpMem]
0x180016aa3  add     rcx, 58h ; 'X'; lpCriticalSection
0x180016aa7  call    cs:__imp_DeleteCriticalSection
0x180016aad  mov     rcx, [rsp+28h+lpMem]
0x180016ab2  add     rcx, 0A8h; SRWLock
0x180016ab9  call    cs:__imp_ReleaseSRWLockExclusive
0x180016abf  mov     rax, [rsp+28h+lpMem]
0x180016ac4  mov     [rax+38h], rsi
0x180016ac8  mov     rcx, [rax+40h]; this
0x180016acc  mov     [rax+40h], rsi
0x180016ad0  test    rcx, rcx
0x180016ad3  jz      short loc_180016ADA
0x180016ad5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180016ada  mov     rbx, [rsp+28h+lpMem]
0x180016adf  call    cs:__imp_GetProcessHeap
0x180016ae5  mov     r8, rbx; lpMem
0x180016ae8  xor     edx, edx; dwFlags
0x180016aea  mov     rcx, rax; hHeap
0x180016aed  call    cs:__imp_HeapFree
0x180016af3  nop
0x180016af4  jmp     short loc_180016AFD
0x180016af6  mov     ecx, 3
0x180016afb  int     29h; Win8: RtlFailFast(ecx)
0x180016afd  mov     rbx, [rsp+28h+arg_0]
0x180016b02  mov     rsi, [rsp+28h+arg_10]
0x180016b07  add     rsp, 20h
0x180016b0b  pop     rdi
0x180016b0c  retn
```
