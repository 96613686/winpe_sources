# RemoveProviderQuery(int,_PROVIDER_QUERY_ENTRY *,_DAS_LOCKED_LIST *)

- ea: `0x140015e58`
- end: `0x1400160cf`
- name: `?RemoveProviderQuery@@YAXHPEAU_PROVIDER_QUERY_ENTRY@@PEAU_DAS_LOCKED_LIST@@@Z`
- size: `631`
- prototype: `void __fastcall(int, RTL_SRWLOCK *, struct _RTL_CRITICAL_SECTION *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140010928`
- `0x1400160d8`

## callees

- `0x140015bf0`
- `0x140015e58`
- `0x14001c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140015e76`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140015f44`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001602c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140015e76`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140015f44`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001602c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14001603b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14001603b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140015e97`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140015f52`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001604d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140015e97`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140015f52`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001604d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001601a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001601a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140015feb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140015feb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400160b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400160b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400160a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400160a4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x140015ee3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x140015ee3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x140015ef5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x140015ef5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140015f19`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140015f19`

## pseudocode

```c
void __fastcall RemoveProviderQuery(int a1, RTL_SRWLOCK *a2, struct _RTL_CRITICAL_SECTION *a3)
{
  _QWORD *v5; // rax
  _QWORD *v6; // rax
  struct _TP_WAIT *v7; // rcx
  void *v8; // rcx
  __int64 v9; // rdi
  __int64 v10; // rcx
  unsigned int v11; // r8d
  const char *v12; // r9
  _QWORD *v13; // rdx
  LPVOID *v14; // rcx
  LPVOID v15; // rax
  volatile signed __int32 *v16; // rbx
  void *v17; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v19; // [rsp+0h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  LPVOID lpMem; // [rsp+48h] [rbp+10h] BYREF
  LPVOID *p_lpMem; // [rsp+58h] [rbp+20h] BYREF

  lpMem = a2;
  AcquireSRWLockExclusive(a2 + 21);
  *((_DWORD *)lpMem + 44) = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)lpMem + 21);
  v5 = lpMem;
  if ( a1 )
  {
    if ( *((_QWORD *)lpMem + 10) )
    {
      p_lpMem = &lpMem;
      lambda_0f0953e5aae94c2e9c0b0e664a2acf1c_::operator()(&p_lpMem);
      v5 = lpMem;
    }
    v5[10] = 0;
    v6 = lpMem;
    v7 = (struct _TP_WAIT *)*((_QWORD *)lpMem + 19);
    if ( v7 )
    {
      WaitForThreadpoolWaitCallbacks(v7, 1);
      CloseThreadpoolWait(*((PTP_WAIT *)lpMem + 19));
      *((_QWORD *)lpMem + 19) = 0;
      v6 = lpMem;
    }
    v8 = (void *)v6[9];
    if ( v8 )
    {
      CloseHandle(v8);
      *((_QWORD *)lpMem + 9) = 0;
    }
  }
  else
  {
    if ( !*((_QWORD *)lpMem + 7) )
      goto LABEL_17;
    v9 = *((_QWORD *)lpMem + 5);
    if ( v9 )
    {
      AcquireSRWLockExclusive((PSRWLOCK)(v9 + 96));
      *(_DWORD *)(v9 + 104) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)(v9 + 96));
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)lpMem + 5) + 16LL))(*((_QWORD *)lpMem + 5));
      *((_QWORD *)lpMem + 5) = 0;
      v5 = lpMem;
    }
    v10 = v5[4];
    if ( *((_DWORD *)v5 + 45) )
    {
      if ( !v10 )
        goto LABEL_17;
      try
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 48LL))(v10);
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)lpMem + 4) + 16LL))(*((_QWORD *)lpMem + 4));
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(retaddr, &v19, v11, v12);
        return;
      }
    }
    else
    {
      if ( !v10 )
        goto LABEL_17;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 48LL))(v10);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)lpMem + 4) + 16LL))(*((_QWORD *)lpMem + 4));
    }
    *((_QWORD *)lpMem + 4) = 0;
  }
LABEL_17:
  if ( a3 )
  {
    EnterCriticalSection(a3);
    v13 = *(_QWORD **)lpMem;
    if ( *(LPVOID *)(*(_QWORD *)lpMem + 8LL) != lpMem || (v14 = (LPVOID *)*((_QWORD *)lpMem + 1), *v14 != lpMem) )
      __fastfail(3u);
    *v14 = v13;
    v13[1] = v14;
    LeaveCriticalSection(a3);
    AcquireSRWLockExclusive((PSRWLOCK)lpMem + 21);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)lpMem + 88));
    ReleaseSRWLockExclusive((PSRWLOCK)lpMem + 21);
    v15 = lpMem;
    *((_QWORD *)lpMem + 7) = 0;
    v16 = (volatile signed __int32 *)*((_QWORD *)v15 + 8);
    *((_QWORD *)v15 + 8) = 0;
    if ( v16 && _InterlockedExchangeAdd(v16 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
      if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
    }
    v17 = lpMem;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v17);
  }
}

```

## disassembly

```asm
0x140015e58  mov     [rsp+arg_0], rbx
0x140015e5d  mov     [rsp+lpMem], rdx
0x140015e62  push    rsi
0x140015e63  push    rdi
0x140015e64  push    r14
0x140015e66  sub     rsp, 20h
0x140015e6a  mov     rsi, r8
0x140015e6d  mov     ebx, ecx
0x140015e6f  lea     rcx, [rdx+0A8h]; SRWLock
0x140015e76  call    cs:__imp_AcquireSRWLockExclusive
0x140015e7c  xor     r14d, r14d
0x140015e7f  mov     rax, [rsp+38h+lpMem]
0x140015e84  mov     [rax+0B0h], r14d
0x140015e8b  mov     rcx, [rsp+38h+lpMem]
0x140015e90  add     rcx, 0A8h; SRWLock
0x140015e97  call    cs:__imp_ReleaseSRWLockExclusive
0x140015e9d  mov     rax, [rsp+38h+lpMem]
0x140015ea2  test    ebx, ebx
0x140015ea4  jz      loc_140015F2D
0x140015eaa  cmp     [rax+50h], r14
0x140015eae  jz      short loc_140015EC9
0x140015eb0  lea     rax, [rsp+38h+lpMem]
0x140015eb5  mov     [rsp+38h+arg_18], rax
0x140015eba  lea     rcx, [rsp+38h+arg_18]
0x140015ebf  call    _lambda_0f0953e5aae94c2e9c0b0e664a2acf1c___operator__
0x140015ec4  mov     rax, [rsp+38h+lpMem]
0x140015ec9  mov     [rax+50h], r14
0x140015ecd  mov     rax, [rsp+38h+lpMem]
0x140015ed2  mov     rcx, [rax+98h]; pwa
0x140015ed9  test    rcx, rcx
0x140015edc  jz      short loc_140015F0C
0x140015ede  mov     edx, 1; fCancelPendingCallbacks
0x140015ee3  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x140015ee9  mov     rcx, [rsp+38h+lpMem]
0x140015eee  mov     rcx, [rcx+98h]; pwa
0x140015ef5  call    cs:__imp_CloseThreadpoolWait
0x140015efb  mov     rax, [rsp+38h+lpMem]
0x140015f00  mov     [rax+98h], r14
0x140015f07  mov     rax, [rsp+38h+lpMem]
0x140015f0c  mov     rcx, [rax+48h]; hObject
0x140015f10  test    rcx, rcx
0x140015f13  jz      loc_140015FDF
0x140015f19  call    cs:__imp_CloseHandle
0x140015f1f  mov     rax, [rsp+38h+lpMem]
0x140015f24  mov     [rax+48h], r14
0x140015f28  jmp     loc_140015FDF
0x140015f2d  cmp     [rax+38h], r14
0x140015f31  jz      loc_140015FDF
0x140015f37  mov     rdi, [rax+28h]
0x140015f3b  test    rdi, rdi
0x140015f3e  jz      short loc_140015F7B
0x140015f40  lea     rcx, [rdi+60h]; SRWLock
0x140015f44  call    cs:__imp_AcquireSRWLockExclusive
0x140015f4a  mov     [rdi+68h], r14d
0x140015f4e  lea     rcx, [rdi+60h]; SRWLock
0x140015f52  call    cs:__imp_ReleaseSRWLockExclusive
0x140015f58  mov     rax, [rsp+38h+lpMem]
0x140015f5d  mov     rcx, [rax+28h]
0x140015f61  mov     rax, [rcx]
0x140015f64  mov     rax, [rax+10h]
0x140015f68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015f6d  mov     rax, [rsp+38h+lpMem]
0x140015f72  mov     [rax+28h], r14
0x140015f76  mov     rax, [rsp+38h+lpMem]
0x140015f7b  mov     rcx, [rax+20h]
0x140015f7f  cmp     [rax+0B4h], r14d
0x140015f86  jz      short loc_140015FB0
0x140015f88  test    rcx, rcx
0x140015f8b  jz      short loc_140015FDF
0x140015f8d  mov     rax, [rcx]
0x140015f90  mov     rax, [rax+30h]
0x140015f94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015f99  mov     rax, [rsp+38h+lpMem]
0x140015f9e  mov     rcx, [rax+20h]
0x140015fa2  mov     rax, [rcx]
0x140015fa5  mov     rax, [rax+10h]
0x140015fa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015fae  jmp     short loc_140015FD6
0x140015fb0  test    rcx, rcx
0x140015fb3  jz      short loc_140015FDF
0x140015fb5  mov     rax, [rcx]
0x140015fb8  mov     rax, [rax+30h]
0x140015fbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015fc1  mov     rax, [rsp+38h+lpMem]
0x140015fc6  mov     rcx, [rax+20h]
0x140015fca  mov     rax, [rcx]
0x140015fcd  mov     rax, [rax+10h]
0x140015fd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015fd6  mov     rax, [rsp+38h+lpMem]
0x140015fdb  mov     [rax+20h], r14
0x140015fdf  test    rsi, rsi
0x140015fe2  jz      loc_1400160B9
0x140015fe8  mov     rcx, rsi; lpCriticalSection
0x140015feb  call    cs:__imp_EnterCriticalSection
0x140015ff1  mov     rax, [rsp+38h+lpMem]
0x140015ff6  mov     rdx, [rax]
0x140015ff9  cmp     [rdx+8], rax
0x140015ffd  jnz     loc_1400160C7
0x140016003  mov     rcx, [rax+8]
0x140016007  cmp     [rcx], rax
0x14001600a  jnz     loc_1400160C7
0x140016010  mov     [rcx], rdx
0x140016013  mov     [rdx+8], rcx
0x140016017  mov     rcx, rsi; lpCriticalSection
0x14001601a  call    cs:__imp_LeaveCriticalSection
0x140016020  mov     rcx, [rsp+38h+lpMem]
0x140016025  add     rcx, 0A8h; SRWLock
0x14001602c  call    cs:__imp_AcquireSRWLockExclusive
0x140016032  mov     rcx, [rsp+38h+lpMem]
0x140016037  add     rcx, 58h ; 'X'; lpCriticalSection
0x14001603b  call    cs:__imp_DeleteCriticalSection
0x140016041  mov     rcx, [rsp+38h+lpMem]
0x140016046  add     rcx, 0A8h; SRWLock
0x14001604d  call    cs:__imp_ReleaseSRWLockExclusive
0x140016053  mov     rax, [rsp+38h+lpMem]
0x140016058  mov     [rax+38h], r14
0x14001605c  mov     rbx, [rax+40h]
0x140016060  mov     [rax+40h], r14
0x140016064  test    rbx, rbx
0x140016067  jz      short loc_14001609F
0x140016069  or      edi, 0FFFFFFFFh
0x14001606c  mov     eax, edi
0x14001606e  lock xadd [rbx+8], eax
0x140016073  add     eax, edi
0x140016075  jnz     short loc_14001609F
0x140016077  mov     rax, [rbx]
0x14001607a  mov     rcx, rbx
0x14001607d  mov     rax, [rax]
0x140016080  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016085  mov     eax, edi
0x140016087  lock xadd [rbx+0Ch], eax
0x14001608c  add     eax, edi
0x14001608e  jnz     short loc_14001609F
0x140016090  mov     rax, [rbx]
0x140016093  mov     rcx, rbx
0x140016096  mov     rax, [rax+8]
0x14001609a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001609f  mov     rbx, [rsp+38h+lpMem]
0x1400160a4  call    cs:__imp_GetProcessHeap
0x1400160aa  mov     r8, rbx; lpMem
0x1400160ad  xor     edx, edx; dwFlags
0x1400160af  mov     rcx, rax; hHeap
0x1400160b2  call    cs:__imp_HeapFree
0x1400160b8  nop
0x1400160b9  mov     rbx, [rsp+38h+arg_0]
0x1400160be  add     rsp, 20h
0x1400160c2  pop     r14
0x1400160c4  pop     rdi
0x1400160c5  pop     rsi
0x1400160c6  retn
0x1400160c7  mov     ecx, 3
0x1400160cc  int     29h; Win8: RtlFailFast(ecx)
```
