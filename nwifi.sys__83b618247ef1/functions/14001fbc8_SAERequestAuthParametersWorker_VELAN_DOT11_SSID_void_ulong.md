# SAERequestAuthParametersWorker(_VELAN *,_DOT11_SSID *,void *,ulong)

- ea: `0x14001fbc8`
- end: `0x14001fdd5`
- name: `?SAERequestAuthParametersWorker@@YAXPEAU_VELAN@@PEAU_DOT11_SSID@@PEAXK@Z`
- size: `525`
- prototype: `void __fastcall(struct _VELAN *, struct _DOT11_SSID *, void *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140062d7c`

## callees

- `0x14000ad38`
- `0x14001fbc8`
- `0x1400239f8`
- `0x14009a4c0`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001fc4e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001fc4e`
- `ntoskrnl!ExAllocatePool2` at `0x14001fc63`
- `ntoskrnl!ExAllocatePool2` at `0x14001fc63`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001fd76`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001fd76`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001fd87`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001fd87`
- `NDIS!NdisAcquireRWLockWrite` at `0x14001fcfd`
- `NDIS!NdisAcquireRWLockWrite` at `0x14001fcfd`
- `NDIS!NdisReleaseRWLock` at `0x14001fd58`
- `NDIS!NdisReleaseRWLock` at `0x14001fd58`

## pseudocode

```c
void __fastcall SAERequestAuthParametersWorker(struct _VELAN *a1, struct _DOT11_SSID *a2, void *a3, __int64 a4)
{
  size_t v4; // r14
  unsigned int v8; // esi
  unsigned int v9; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rdi
  _DWORD *Pool2; // rax
  _DWORD *v12; // rbp
  int v13; // edx
  int v14; // ecx
  unsigned int *p_uWorkItemsQueued; // rdi
  int v16; // edx
  int v17; // ecx
  struct _LOCK_STATE_EX LockState; // [rsp+78h] [rbp+20h] BYREF

  v4 = (unsigned int)a4;
  *(_WORD *)&LockState.LockState = 0;
  LockState.OldIrql = 0;
  v8 = a4 + 40;
  v9 = a4 + 56;
  if ( (unsigned int)(a4 + 56) < 0x10 )
    goto LABEL_21;
  if ( v9 <= 0x40 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_10:
    Pool2 = ExAllocateFromNPagedLookasideList(p_DeviceQueue);
    goto LABEL_12;
  }
  if ( v9 <= 0x100 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_10;
  }
  if ( v9 <= 0x400 )
  {
    p_DeviceQueue = &Lookaside;
    goto LABEL_10;
  }
  if ( v9 <= 0x800 )
  {
    p_DeviceQueue = &stru_1400B0180;
    goto LABEL_10;
  }
  p_DeviceQueue = 0;
  Pool2 = (_DWORD *)ExAllocatePool2(64, v9, 2053731191, a4);
LABEL_12:
  if ( Pool2 )
  {
    Pool2[2] = 2053731191;
    v12 = Pool2 + 4;
    *(_QWORD *)Pool2 = p_DeviceQueue;
    memset(Pool2 + 4, 0, v8);
    v12[9] = v4;
    memmove(v12 + 10, a3, v4);
    p_uWorkItemsQueued = &a1->WorkerRequestHandler.uWorkItemsQueued;
    *(_OWORD *)v12 = *(_OWORD *)&a2->uSSIDLength;
    *((_OWORD *)v12 + 1) = *(_OWORD *)&a2->ucSSID[12];
    v12[8] = *(_DWORD *)&a2->ucSSID[28];
    if ( (byte_1400AF804 & 0x10) != 0 )
      McTemplateK0zqq_EtwWriteTransfer(
        v14,
        v13,
        (_DWORD)a1 + 4920,
        (unsigned int)L"SAERequestAuthParametersWorker: [WPA3]: Requesting new SAE worker",
        0,
        *p_uWorkItemsQueued);
    NdisAcquireRWLockWrite(a1->pRWLock, &LockState, 0);
    if ( (int)Dot11WorkerRequestHandler(
                a1,
                DOT11_WORKER_REQUEST_TYPE_SAE_AUTH_PARAMETERS,
                SAEAuthParametersCallbackFn,
                v8,
                v12) < 0
      && (byte_1400AF804 & 0x10) != 0 )
    {
      McTemplateK0zqq_EtwWriteTransfer(
        v17,
        v16,
        (_DWORD)a1 + 4920,
        (unsigned int)L"SAERequestAuthParametersWorker: [WPA3-Fail]: Dot11WorkerRequestHandler failed to queue worker",
        0,
        *p_uWorkItemsQueued);
    }
    NdisReleaseRWLock(a1->pRWLock, &LockState);
    if ( *((_QWORD *)v12 - 2) )
      ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v12 - 2), v12 - 4);
    else
      ExFreePoolWithTag(v12 - 4, *(v12 - 2));
    return;
  }
LABEL_21:
  if ( (byte_1400AF804 & 0x10) != 0 )
    McTemplateK0zqq_EtwWriteTransfer(
      (_DWORD)a1,
      (_DWORD)a2,
      (_DWORD)a1 + 4920,
      (unsigned int)L"SAERequestAuthParametersWorker [WPA3]: Unable to allocate WorkItem for queuing",
      2,
      v8);
}

```

## disassembly

```asm
0x14001fbc8  mov     [rsp+arg_0], rbx
0x14001fbcd  mov     [rsp+arg_8], rbp
0x14001fbd2  push    rsi
0x14001fbd3  push    rdi
0x14001fbd4  push    r12
0x14001fbd6  push    r14
0x14001fbd8  push    r15
0x14001fbda  sub     rsp, 30h
0x14001fbde  xor     eax, eax
0x14001fbe0  mov     r14d, r9d
0x14001fbe3  mov     word ptr [rsp+58h+LockState.LockState], ax
0x14001fbe8  mov     r12, r8
0x14001fbeb  mov     r15, rdx
0x14001fbee  mov     [rsp+58h+LockState.OldIrql], 0
0x14001fbf3  mov     rbx, rcx
0x14001fbf6  lea     esi, [r14+28h]
0x14001fbfa  lea     eax, [rsi+10h]
0x14001fbfd  cmp     eax, 10h
0x14001fc00  jb      loc_14001FD95
0x14001fc06  mov     ecx, 40h ; '@'
0x14001fc0b  mov     ebp, 7A697377h
0x14001fc10  cmp     eax, ecx
0x14001fc12  ja      short loc_14001FC1D
0x14001fc14  lea     rdi, WPP_MAIN_CB.DeviceQueue
0x14001fc1b  jmp     short loc_14001FC4B
0x14001fc1d  cmp     eax, 100h
0x14001fc22  ja      short loc_14001FC2D
0x14001fc24  lea     rdi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14001fc2b  jmp     short loc_14001FC4B
0x14001fc2d  cmp     eax, 400h
0x14001fc32  ja      short loc_14001FC3D
0x14001fc34  lea     rdi, Lookaside
0x14001fc3b  jmp     short loc_14001FC4B
0x14001fc3d  cmp     eax, 800h
0x14001fc42  ja      short loc_14001FC5C
0x14001fc44  lea     rdi, stru_1400B0180
0x14001fc4b  mov     rcx, rdi; Lookaside
0x14001fc4e  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14001fc55  nop     dword ptr [rax+rax+00h]
0x14001fc5a  jmp     short loc_14001FC6F
0x14001fc5c  xor     edi, edi
0x14001fc5e  mov     edx, eax
0x14001fc60  mov     r8d, ebp
0x14001fc63  call    cs:__imp_ExAllocatePool2
0x14001fc6a  nop     dword ptr [rax+rax+00h]
0x14001fc6f  test    rax, rax
0x14001fc72  jz      loc_14001FD95
0x14001fc78  mov     [rax+8], ebp
0x14001fc7b  xor     edx, edx; Val
0x14001fc7d  lea     rbp, [rax+10h]
0x14001fc81  mov     r8d, esi; Size
0x14001fc84  mov     rcx, rbp; void *
0x14001fc87  mov     [rax], rdi
0x14001fc8a  call    memset
0x14001fc8f  mov     r8, r14; Size
0x14001fc92  mov     [rbp+24h], r14d
0x14001fc96  lea     rcx, [rbp+28h]; void *
0x14001fc9a  mov     rdx, r12; Src
0x14001fc9d  call    memmove
0x14001fca2  movups  xmm0, xmmword ptr [r15]
0x14001fca6  lea     r14, [rbx+1338h]
0x14001fcad  lea     rdi, [rbx+1FD0h]
0x14001fcb4  movups  xmmword ptr [rbp+0], xmm0
0x14001fcb8  movups  xmm1, xmmword ptr [r15+10h]
0x14001fcbd  movups  xmmword ptr [rbp+10h], xmm1
0x14001fcc1  mov     eax, [r15+20h]
0x14001fcc5  mov     [rbp+20h], eax
0x14001fcc8  test    cs:byte_1400AF804, 10h
0x14001fccf  jz      short loc_14001FCEE
0x14001fcd1  mov     eax, [rdi]
0x14001fcd3  lea     r9, aSaerequestauth_1; "SAERequestAuthParametersWorker: [WPA3]:"...
0x14001fcda  mov     [rsp+58h+var_30], eax
0x14001fcde  mov     r8, r14
0x14001fce1  mov     dword ptr [rsp+58h+var_38], 0
0x14001fce9  call    McTemplateK0zqq_EtwWriteTransfer
0x14001fcee  mov     rcx, [rbx+90h]; Lock
0x14001fcf5  lea     rdx, [rsp+58h+LockState]; LockState
0x14001fcfa  xor     r8d, r8d; Flags
0x14001fcfd  call    cs:__imp_NdisAcquireRWLockWrite
0x14001fd04  nop     dword ptr [rax+rax+00h]
0x14001fd09  mov     r9d, esi; Size
0x14001fd0c  mov     [rsp+58h+var_38], rbp; void *
0x14001fd11  lea     r8, ?SAEAuthParametersCallbackFn@@YAXPEAU_VELAN@@PEAU_NWIFI_LOCK_STATE@@PEAX@Z; void (*)(struct _VELAN *, struct _NWIFI_LOCK_STATE *, void *)
0x14001fd18  xor     edx, edx; enum DOT11_WORKER_REQUEST_TYPE
0x14001fd1a  mov     rcx, rbx; struct _VELAN *
0x14001fd1d  call    ?Dot11WorkerRequestHandler@@YAJPEAU_VELAN@@W4DOT11_WORKER_REQUEST_TYPE@@P6AX0PEAU_NWIFI_LOCK_STATE@@PEAX@ZK3@Z; Dot11WorkerRequestHandler(_VELAN *,DOT11_WORKER_REQUEST_TYPE,void (*)(_VELAN *,_NWIFI_LOCK_STATE *,void *),ulong,void *)
0x14001fd22  test    eax, eax
0x14001fd24  jns     short loc_14001FD4C
0x14001fd26  test    cs:byte_1400AF804, 10h
0x14001fd2d  jz      short loc_14001FD4C
0x14001fd2f  mov     eax, [rdi]
0x14001fd31  lea     r9, aSaerequestauth_0; "SAERequestAuthParametersWorker: [WPA3-F"...
0x14001fd38  mov     [rsp+58h+var_30], eax
0x14001fd3c  mov     r8, r14
0x14001fd3f  mov     dword ptr [rsp+58h+var_38], 0
0x14001fd47  call    McTemplateK0zqq_EtwWriteTransfer
0x14001fd4c  mov     rcx, [rbx+90h]; Lock
0x14001fd53  lea     rdx, [rsp+58h+LockState]; LockState
0x14001fd58  call    cs:__imp_NdisReleaseRWLock
0x14001fd5f  nop     dword ptr [rax+rax+00h]
0x14001fd64  lea     rcx, [rbp-10h]; P
0x14001fd68  mov     rax, [rcx]
0x14001fd6b  test    rax, rax
0x14001fd6e  jz      short loc_14001FD84
0x14001fd70  mov     rdx, rcx; Entry
0x14001fd73  mov     rcx, rax; Lookaside
0x14001fd76  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001fd7d  nop     dword ptr [rax+rax+00h]
0x14001fd82  jmp     short loc_14001FDBD
0x14001fd84  mov     edx, [rcx+8]; Tag
0x14001fd87  call    cs:__imp_ExFreePoolWithTag
0x14001fd8e  nop     dword ptr [rax+rax+00h]
0x14001fd93  jmp     short loc_14001FDBD
0x14001fd95  test    cs:byte_1400AF804, 10h
0x14001fd9c  jz      short loc_14001FDBD
0x14001fd9e  lea     r8, [rbx+1338h]
0x14001fda5  mov     [rsp+58h+var_30], esi
0x14001fda9  lea     r9, aSaerequestauth; "SAERequestAuthParametersWorker [WPA3]: "...
0x14001fdb0  mov     dword ptr [rsp+58h+var_38], 2
0x14001fdb8  call    McTemplateK0zqq_EtwWriteTransfer
0x14001fdbd  mov     rbx, [rsp+58h+arg_0]
0x14001fdc2  mov     rbp, [rsp+58h+arg_8]
0x14001fdc7  add     rsp, 30h
0x14001fdcb  pop     r15
0x14001fdcd  pop     r14
0x14001fdcf  pop     r12
0x14001fdd1  pop     rdi
0x14001fdd2  pop     rsi
0x14001fdd3  retn
```
