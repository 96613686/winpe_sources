# RemoveAssociationEntry(_ASSOCIATION_ENTRY *)

- ea: `0x14000bc74`
- end: `0x14000be5c`
- name: `?RemoveAssociationEntry@@YAJPEAU_ASSOCIATION_ENTRY@@@Z`
- size: `488`
- prototype: `__int64 __fastcall(struct _ASSOCIATION_ENTRY *lpMem, int, int)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x14000bef0`
- `0x14000bf80`
- `0x14000c350`
- `0x140010928`

## callees

- `0x140008eec`
- `0x140008f88`
- `0x140009090`
- `0x14000bc74`
- `0x14001c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000bd5f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000bd5f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000bd05`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000be15`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000bd05`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000be15`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000bcbc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000bcf4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000bcbc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000bcf4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000bd32`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000be08`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000bd32`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000be08`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000bd24`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000bdfa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000bd24`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000bdfa`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14000bd82`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14000bd82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000bd70`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000bd70`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14000bd50`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14000bd50`

## pseudocode

```c
__int64 __fastcall RemoveAssociationEntry(struct _ASSOCIATION_ENTRY *lpMem, int a2, int a3)
{
  __int64 v4; // rdx
  struct _ASSOCIATION_ENTRY **v5; // rcx
  __int64 v6; // rsi
  void *v7; // rbx
  HANDLE ProcessHeap; // rax
  void *v9; // rcx
  int v10; // ebx
  struct _TP_WAIT *v11; // rcx
  __int64 v12; // rcx
  void *v13; // rcx
  volatile signed __int32 *v14; // rbx
  HANDLE v15; // rax
  int v16; // edx
  int v17; // r8d
  int v19; // [rsp+28h] [rbp-40h]

  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 5), a2, a3, 12, &WPP_c086fa40671c3989c8f4ec8bc168966d_Traceguids);
  EnterCriticalSection(&ActiveAssociationsList);
  v4 = *((_QWORD *)lpMem + 2);
  if ( *(struct _ASSOCIATION_ENTRY **)(v4 + 8) != (struct _ASSOCIATION_ENTRY *)((char *)lpMem + 16)
    || (v5 = (struct _ASSOCIATION_ENTRY **)*((_QWORD *)lpMem + 3),
        *v5 != (struct _ASSOCIATION_ENTRY *)((char *)lpMem + 16)) )
  {
    __fastfail(3u);
  }
  *v5 = (struct _ASSOCIATION_ENTRY *)v4;
  *(_QWORD *)(v4 + 8) = v5;
  v6 = *((_QWORD *)lpMem + 7);
  if ( v6 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v6 + 112));
    *(_DWORD *)(v6 + 104) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)(v6 + 112));
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)lpMem + 7) + 16LL))(*((_QWORD *)lpMem + 7));
  }
  v7 = (void *)*((_QWORD *)lpMem + 9);
  if ( v7 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v7);
  }
  v9 = (void *)*((_QWORD *)lpMem + 22);
  if ( v9 )
  {
    v10 = 1;
    while ( !WaitForSingleObject(v9, 0) )
    {
      v10 *= 2;
      Sleep(100 * v10);
      v9 = (void *)*((_QWORD *)lpMem + 22);
    }
    CloseHandle(*((HANDLE *)lpMem + 22));
  }
  v11 = (struct _TP_WAIT *)*((_QWORD *)lpMem + 23);
  if ( v11 )
    CloseThreadpoolWait(v11);
  v12 = *((_QWORD *)lpMem + 6);
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  v13 = (void *)*((_QWORD *)lpMem + 10);
  if ( v13 )
    MIDL_user_free(v13);
  *((_QWORD *)lpMem + 4) = 0;
  v14 = (volatile signed __int32 *)*((_QWORD *)lpMem + 5);
  *((_QWORD *)lpMem + 5) = 0;
  if ( v14 )
  {
    if ( _InterlockedExchangeAdd(v14 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
      if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
    }
  }
  v15 = GetProcessHeap();
  HeapFree(v15, 0, lpMem);
  LeaveCriticalSection(&ActiveAssociationsList);
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v16,
      v17,
      13,
      &WPP_c086fa40671c3989c8f4ec8bc168966d_Traceguids,
      v19,
      0);
  return 0;
}

```

## disassembly

```asm
0x14000bc74  push    rbx
0x14000bc76  push    rsi
0x14000bc77  push    rdi
0x14000bc78  push    r14
0x14000bc7a  push    r15
0x14000bc7c  sub     rsp, 40h
0x14000bc80  mov     rdi, rcx
0x14000bc83  lea     r15, WPP_RECORDER_INITIALIZED
0x14000bc8a  lea     r14, WPP_c086fa40671c3989c8f4ec8bc168966d_Traceguids
0x14000bc91  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14000bc98  jz      short loc_14000BCB5
0x14000bc9a  mov     r9d, 0Ch; int
0x14000bca0  mov     [rsp+68h+MessageGuid], r14; MessageGuid
0x14000bca5  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bcac  mov     rcx, [rcx+28h]; int
0x14000bcb0  call    WPP_RECORDER_SF_s
0x14000bcb5  lea     rcx, ?ActiveAssociationsList@@3U_DAS_LOCKED_LIST@@A; lpCriticalSection
0x14000bcbc  call    cs:__imp_EnterCriticalSection
0x14000bcc2  lea     rax, [rdi+10h]
0x14000bcc6  mov     rdx, [rax]
0x14000bcc9  cmp     [rdx+8], rax
0x14000bccd  jnz     loc_14000BE55
0x14000bcd3  mov     rcx, [rax+8]
0x14000bcd7  cmp     [rcx], rax
0x14000bcda  jnz     loc_14000BE55
0x14000bce0  mov     [rcx], rdx
0x14000bce3  mov     [rdx+8], rcx
0x14000bce7  mov     rsi, [rdi+38h]
0x14000bceb  test    rsi, rsi
0x14000bcee  jz      short loc_14000BD1B
0x14000bcf0  lea     rcx, [rsi+70h]; lpCriticalSection
0x14000bcf4  call    cs:__imp_EnterCriticalSection
0x14000bcfa  mov     dword ptr [rsi+68h], 0
0x14000bd01  lea     rcx, [rsi+70h]; lpCriticalSection
0x14000bd05  call    cs:__imp_LeaveCriticalSection
0x14000bd0b  mov     rcx, [rdi+38h]
0x14000bd0f  mov     rax, [rcx]
0x14000bd12  mov     rax, [rax+10h]
0x14000bd16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bd1b  mov     rbx, [rdi+48h]
0x14000bd1f  test    rbx, rbx
0x14000bd22  jz      short loc_14000BD38
0x14000bd24  call    cs:__imp_GetProcessHeap
0x14000bd2a  mov     r8, rbx; lpMem
0x14000bd2d  xor     edx, edx; dwFlags
0x14000bd2f  mov     rcx, rax; hHeap
0x14000bd32  call    cs:__imp_HeapFree
0x14000bd38  mov     rcx, [rdi+0B0h]
0x14000bd3f  test    rcx, rcx
0x14000bd42  jz      short loc_14000BD76
0x14000bd44  mov     ebx, 1
0x14000bd49  jmp     short loc_14000BD5D
0x14000bd4b  add     ebx, ebx
0x14000bd4d  imul    ecx, ebx, 64h ; 'd'; dwMilliseconds
0x14000bd50  call    cs:__imp_Sleep
0x14000bd56  mov     rcx, [rdi+0B0h]; hHandle
0x14000bd5d  xor     edx, edx; dwMilliseconds
0x14000bd5f  call    cs:__imp_WaitForSingleObject
0x14000bd65  test    eax, eax
0x14000bd67  jz      short loc_14000BD4B
0x14000bd69  mov     rcx, [rdi+0B0h]; hObject
0x14000bd70  call    cs:__imp_CloseHandle
0x14000bd76  mov     rcx, [rdi+0B8h]; pwa
0x14000bd7d  test    rcx, rcx
0x14000bd80  jz      short loc_14000BD88
0x14000bd82  call    cs:__imp_CloseThreadpoolWait
0x14000bd88  mov     rcx, [rdi+30h]
0x14000bd8c  test    rcx, rcx
0x14000bd8f  jz      short loc_14000BD9D
0x14000bd91  mov     rax, [rcx]
0x14000bd94  mov     rax, [rax+10h]
0x14000bd98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bd9d  mov     rcx, [rdi+50h]; void *
0x14000bda1  test    rcx, rcx
0x14000bda4  jz      short loc_14000BDAB
0x14000bda6  call    MIDL_user_free
0x14000bdab  mov     qword ptr [rdi+20h], 0
0x14000bdb3  mov     rbx, [rdi+28h]
0x14000bdb7  mov     qword ptr [rdi+28h], 0
0x14000bdbf  test    rbx, rbx
0x14000bdc2  jz      short loc_14000BDFA
0x14000bdc4  or      esi, 0FFFFFFFFh
0x14000bdc7  mov     eax, esi
0x14000bdc9  lock xadd [rbx+8], eax
0x14000bdce  add     eax, esi
0x14000bdd0  jnz     short loc_14000BDFA
0x14000bdd2  mov     rax, [rbx]
0x14000bdd5  mov     rcx, rbx
0x14000bdd8  mov     rax, [rax]
0x14000bddb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bde0  mov     eax, esi
0x14000bde2  lock xadd [rbx+0Ch], eax
0x14000bde7  add     eax, esi
0x14000bde9  jnz     short loc_14000BDFA
0x14000bdeb  mov     rax, [rbx]
0x14000bdee  mov     rcx, rbx
0x14000bdf1  mov     rax, [rax+8]
0x14000bdf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bdfa  call    cs:__imp_GetProcessHeap
0x14000be00  mov     rcx, rax; hHeap
0x14000be03  mov     r8, rdi; lpMem
0x14000be06  xor     edx, edx; dwFlags
0x14000be08  call    cs:__imp_HeapFree
0x14000be0e  lea     rcx, ?ActiveAssociationsList@@3U_DAS_LOCKED_LIST@@A; lpCriticalSection
0x14000be15  call    cs:__imp_LeaveCriticalSection
0x14000be1b  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14000be22  jz      short loc_14000BE47
0x14000be24  mov     r9d, 0Dh; int
0x14000be2a  mov     dword ptr [rsp+68h+var_38], 0; char
0x14000be32  mov     [rsp+68h+MessageGuid], r14; MessageGuid
0x14000be37  mov     rcx, cs:WPP_GLOBAL_Control
0x14000be3e  mov     rcx, [rcx+28h]; int
0x14000be42  call    WPP_RECORDER_SF_sd
0x14000be47  xor     eax, eax
0x14000be49  add     rsp, 40h
0x14000be4d  pop     r15
0x14000be4f  pop     r14
0x14000be51  pop     rdi
0x14000be52  pop     rsi
0x14000be53  pop     rbx
0x14000be54  retn
0x14000be55  mov     ecx, 3
0x14000be5a  int     29h; Win8: RtlFailFast(ecx)
```
