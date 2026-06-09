# PMKCacheRequestGetPmkidListWorker(_VELAN *,ulong,DOT11_PMKID_CANDIDATE_LIST_PARAMETERS *)

- ea: `0x140023854`
- end: `0x1400239f1`
- name: `?PMKCacheRequestGetPmkidListWorker@@YAHPEAU_VELAN@@KPEAUDOT11_PMKID_CANDIDATE_LIST_PARAMETERS@@@Z`
- size: `413`
- prototype: `__int64 __fastcall(struct _VELAN *, size_t Size, struct DOT11_PMKID_CANDIDATE_LIST_PARAMETERS *Src)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140061388`

## callees

- `0x14000ad38`
- `0x140023854`
- `0x1400239f8`
- `0x14009a4c0`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400238d3`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400238d3`
- `ntoskrnl!ExAllocatePool2` at `0x1400238e8`
- `ntoskrnl!ExAllocatePool2` at `0x1400238e8`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400239b7`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400239b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400239cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400239cb`
- `NDIS!NdisAcquireRWLockWrite` at `0x140023969`
- `NDIS!NdisAcquireRWLockWrite` at `0x140023969`
- `NDIS!NdisReleaseRWLock` at `0x14002399b`
- `NDIS!NdisReleaseRWLock` at `0x14002399b`

## string_xrefs

- `0x140023919`: `PMKCacheRequestGetPmkidListWorker [PmkId]: Failed to Allocate worker context`

## pseudocode

```c
__int64 __fastcall PMKCacheRequestGetPmkidListWorker(
        struct _VELAN *a1,
        size_t Size,
        struct DOT11_PMKID_CANDIDATE_LIST_PARAMETERS *Src,
        __int64 a4)
{
  size_t v4; // r15
  unsigned int v7; // ebp
  unsigned int v8; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rbx
  PNPAGED_LOOKASIDE_LIST *Pool2; // rax
  PNPAGED_LOOKASIDE_LIST *v11; // rdi
  unsigned int v12; // esi
  struct _LOCK_STATE_EX LockState; // [rsp+68h] [rbp+10h] BYREF

  v4 = (unsigned int)Size;
  *(_WORD *)&LockState.LockState = 0;
  LockState.OldIrql = 0;
  v7 = Size + 36;
  v8 = Size + 52;
  if ( (unsigned int)(Size + 52) < 0x10 )
  {
LABEL_13:
    v12 = -1073741670;
    if ( (byte_1400AF804 & 0x10) != 0 )
      McTemplateK0zqq_EtwWriteTransfer(
        (_DWORD)a1,
        Size,
        (_DWORD)a1 + 4920,
        (unsigned int)L"PMKCacheRequestGetPmkidListWorker [PmkId]: Failed to Allocate worker context",
        154,
        v7);
    return v12;
  }
  if ( v8 <= 0x40 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_10:
    Pool2 = (PNPAGED_LOOKASIDE_LIST *)ExAllocateFromNPagedLookasideList(p_DeviceQueue);
    goto LABEL_12;
  }
  if ( v8 <= 0x100 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_10;
  }
  if ( v8 <= 0x400 )
  {
    p_DeviceQueue = &Lookaside;
    goto LABEL_10;
  }
  if ( v8 <= 0x800 )
  {
    p_DeviceQueue = &stru_1400B0180;
    goto LABEL_10;
  }
  p_DeviceQueue = 0;
  Pool2 = (PNPAGED_LOOKASIDE_LIST *)ExAllocatePool2(64, v8, 2053731191, a4);
LABEL_12:
  v11 = Pool2;
  if ( !Pool2 )
    goto LABEL_13;
  *Pool2 = p_DeviceQueue;
  *((_DWORD *)Pool2 + 2) = 2053731191;
  v12 = 0;
  memset(Pool2 + 2, 0, v7);
  memmove((char *)v11 + 52, Src, v4);
  NdisAcquireRWLockWrite(a1->pRWLock, &LockState, 0);
  Dot11WorkerRequestHandler(
    a1,
    DOT11_WORKER_REQUEST_TYPE_PMKID_LIST,
    (void (*)(struct _VELAN *, struct _NWIFI_LOCK_STATE *, void *))PMKCacheGetPmkidListCallback,
    v7,
    v11 + 2);
  NdisReleaseRWLock(a1->pRWLock, &LockState);
  if ( v11 != (PNPAGED_LOOKASIDE_LIST *)-16LL )
  {
    if ( *v11 )
      ExFreeToNPagedLookasideList(*v11, v11);
    else
      ExFreePoolWithTag(v11, *((_DWORD *)v11 + 2));
  }
  return v12;
}

```

## disassembly

```asm
0x140023854  mov     [rsp+arg_0], rbx
0x140023859  mov     [rsp+arg_10], rbp
0x14002385e  push    rsi
0x14002385f  push    rdi
0x140023860  push    r12
0x140023862  push    r14
0x140023864  push    r15
0x140023866  sub     rsp, 30h
0x14002386a  xor     eax, eax
0x14002386c  mov     r15d, edx
0x14002386f  mov     word ptr [rsp+58h+LockState.LockState], ax
0x140023874  mov     r12, r8
0x140023877  mov     r14, rcx
0x14002387a  mov     [rsp+58h+LockState.OldIrql], 0
0x14002387f  lea     ebp, [r15+24h]
0x140023883  lea     eax, [rbp+10h]
0x140023886  cmp     eax, 10h
0x140023889  jb      short loc_1400238FC
0x14002388b  mov     ecx, 40h ; '@'
0x140023890  mov     esi, 7A697377h
0x140023895  cmp     eax, ecx
0x140023897  ja      short loc_1400238A2
0x140023899  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x1400238a0  jmp     short loc_1400238D0
0x1400238a2  cmp     eax, 100h
0x1400238a7  ja      short loc_1400238B2
0x1400238a9  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x1400238b0  jmp     short loc_1400238D0
0x1400238b2  cmp     eax, 400h
0x1400238b7  ja      short loc_1400238C2
0x1400238b9  lea     rbx, Lookaside
0x1400238c0  jmp     short loc_1400238D0
0x1400238c2  cmp     eax, 800h
0x1400238c7  ja      short loc_1400238E1
0x1400238c9  lea     rbx, stru_1400B0180
0x1400238d0  mov     rcx, rbx; Lookaside
0x1400238d3  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400238da  nop     dword ptr [rax+rax+00h]
0x1400238df  jmp     short loc_1400238F4
0x1400238e1  xor     ebx, ebx
0x1400238e3  mov     edx, eax
0x1400238e5  mov     r8d, esi
0x1400238e8  call    cs:__imp_ExAllocatePool2
0x1400238ef  nop     dword ptr [rax+rax+00h]
0x1400238f4  mov     rdi, rax
0x1400238f7  test    rax, rax
0x1400238fa  jnz     short loc_140023932
0x1400238fc  test    cs:byte_1400AF804, 10h
0x140023903  mov     esi, 0C000009Ah
0x140023908  jz      loc_1400239D7
0x14002390e  lea     r8, [r14+1338h]
0x140023915  mov     [rsp+58h+var_30], ebp
0x140023919  lea     r9, aPmkcachereques; "PMKCacheRequestGetPmkidListWorker [PmkI"...
0x140023920  mov     dword ptr [rsp+58h+var_38], 0C000009Ah
0x140023928  call    McTemplateK0zqq_EtwWriteTransfer
0x14002392d  jmp     loc_1400239D7
0x140023932  mov     [rdi], rbx
0x140023935  xor     edx, edx; Val
0x140023937  mov     [rdi+8], esi
0x14002393a  lea     rbx, [rdi+10h]
0x14002393e  mov     rcx, rbx; void *
0x140023941  mov     r8d, ebp; Size
0x140023944  xor     esi, esi
0x140023946  call    memset
0x14002394b  mov     r8, r15; Size
0x14002394e  lea     rcx, [rbx+24h]; void *
0x140023952  mov     rdx, r12; Src
0x140023955  call    memmove
0x14002395a  mov     rcx, [r14+90h]; Lock
0x140023961  lea     rdx, [rsp+58h+LockState]; LockState
0x140023966  xor     r8d, r8d; Flags
0x140023969  call    cs:__imp_NdisAcquireRWLockWrite
0x140023970  nop     dword ptr [rax+rax+00h]
0x140023975  mov     r9d, ebp; Size
0x140023978  mov     [rsp+58h+var_38], rbx; void *
0x14002397d  lea     r8, ?PMKCacheGetPmkidListCallback@@YAXPEAU_VELAN@@PEAU_NWIFI_LOCK_STATE@@PEAX@Z; void (*)(struct _VELAN *, struct _NWIFI_LOCK_STATE *, void *)
0x140023984  mov     rcx, r14; struct _VELAN *
0x140023987  lea     edx, [rsi+1]; enum DOT11_WORKER_REQUEST_TYPE
0x14002398a  call    ?Dot11WorkerRequestHandler@@YAJPEAU_VELAN@@W4DOT11_WORKER_REQUEST_TYPE@@P6AX0PEAU_NWIFI_LOCK_STATE@@PEAX@ZK3@Z; Dot11WorkerRequestHandler(_VELAN *,DOT11_WORKER_REQUEST_TYPE,void (*)(_VELAN *,_NWIFI_LOCK_STATE *,void *),ulong,void *)
0x14002398f  mov     rcx, [r14+90h]; Lock
0x140023996  lea     rdx, [rsp+58h+LockState]; LockState
0x14002399b  call    cs:__imp_NdisReleaseRWLock
0x1400239a2  nop     dword ptr [rax+rax+00h]
0x1400239a7  test    rbx, rbx
0x1400239aa  jz      short loc_1400239D7
0x1400239ac  mov     rcx, [rdi]; Lookaside
0x1400239af  test    rcx, rcx
0x1400239b2  jz      short loc_1400239C5
0x1400239b4  mov     rdx, rdi; Entry
0x1400239b7  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400239be  nop     dword ptr [rax+rax+00h]
0x1400239c3  jmp     short loc_1400239D7
0x1400239c5  mov     edx, [rdi+8]; Tag
0x1400239c8  mov     rcx, rdi; P
0x1400239cb  call    cs:__imp_ExFreePoolWithTag
0x1400239d2  nop     dword ptr [rax+rax+00h]
0x1400239d7  mov     rbx, [rsp+58h+arg_0]
0x1400239dc  mov     eax, esi
0x1400239de  mov     rbp, [rsp+58h+arg_10]
0x1400239e3  add     rsp, 30h
0x1400239e7  pop     r15
0x1400239e9  pop     r14
0x1400239eb  pop     r12
0x1400239ed  pop     rdi
0x1400239ee  pop     rsi
0x1400239ef  retn
```
