# ExtSTACacheMulticastList(EXTSTA_VELAN *,void *,ulong)

- ea: `0x140069978`
- end: `0x140069af6`
- name: `?ExtSTACacheMulticastList@@YAHPEAUEXTSTA_VELAN@@PEAXK@Z`
- size: `382`
- prototype: `__int64 __fastcall(struct EXTSTA_VELAN *, void *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140069d70`

## callees

- `0x140069978`
- `0x14009bcc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140069a29`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140069a29`
- `ntoskrnl!ExAllocatePool2` at `0x140069a3c`
- `ntoskrnl!ExAllocatePool2` at `0x140069a3c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140069a77`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140069a77`
- `ntoskrnl!ExFreePoolWithTag` at `0x140069a88`
- `ntoskrnl!ExFreePoolWithTag` at `0x140069a88`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400699b7`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400699b7`
- `NDIS!NdisReleaseRWLock` at `0x140069ad4`
- `NDIS!NdisReleaseRWLock` at `0x140069ad4`

## pseudocode

```c
__int64 __fastcall ExtSTACacheMulticastList(struct EXTSTA_VELAN *a1, void *a2, unsigned int a3)
{
  size_t v4; // rsi
  _VELAN *pGenVElan; // rcx
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rdi
  unsigned int v8; // eax
  _DWORD *Pool2; // rax
  void *v10; // rbp
  char *pMcastList; // rcx
  ULONG *v12; // rcx
  void *v13; // rcx
  struct _LOCK_STATE_EX LockState; // [rsp+50h] [rbp+18h] BYREF

  v4 = a3;
  pGenVElan = a1->pGenVElan;
  *(_WORD *)&LockState.LockState = 0;
  p_DeviceQueue = 0;
  LockState.OldIrql = 0;
  NdisAcquireRWLockWrite(pGenVElan->pRWLock, &LockState, 0);
  if ( a1->Rw.MulticastList.uMaxListSize >= (unsigned int)v4 )
    goto LABEL_21;
  v8 = v4 + 16;
  if ( (unsigned int)v4 >= 0xFFFFFFF0 )
    goto LABEL_3;
  if ( v8 <= 0x40 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_12:
    Pool2 = ExAllocateFromNPagedLookasideList(p_DeviceQueue);
    goto LABEL_14;
  }
  if ( v8 <= 0x100 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_12;
  }
  if ( v8 <= 0x400 )
  {
    p_DeviceQueue = &Lookaside;
    goto LABEL_12;
  }
  if ( v8 <= 0x800 )
  {
    p_DeviceQueue = &stru_1400B31C0;
    goto LABEL_12;
  }
  Pool2 = (_DWORD *)ExAllocatePool2(64, v8, 845771639);
LABEL_14:
  if ( !Pool2 )
  {
LABEL_3:
    LODWORD(p_DeviceQueue) = -1073741670;
    goto LABEL_20;
  }
  *(_QWORD *)Pool2 = p_DeviceQueue;
  LODWORD(p_DeviceQueue) = 0;
  Pool2[2] = 845771639;
  v10 = Pool2 + 4;
  pMcastList = (char *)a1->Rw.MulticastList.pMcastList;
  if ( pMcastList )
  {
    v12 = (ULONG *)(pMcastList - 16);
    if ( *(_QWORD *)v12 )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v12, v12);
    else
      ExFreePoolWithTag(v12, v12[2]);
  }
  a1->Rw.MulticastList.pMcastList = v10;
  a1->Rw.MulticastList.uMaxListSize = v4;
LABEL_20:
  if ( a1->Rw.MulticastList.uMaxListSize >= (unsigned int)v4 )
  {
LABEL_21:
    v13 = a1->Rw.MulticastList.pMcastList;
    a1->Rw.MulticastList.uCurrentListSize = v4;
    memmove(v13, a2, v4);
  }
  NdisReleaseRWLock(a1->pGenVElan->pRWLock, &LockState);
  return (unsigned int)p_DeviceQueue;
}

```

## disassembly

```asm
0x140069978  mov     [rsp+arg_0], rbx
0x14006997d  mov     [rsp+arg_8], rbp
0x140069982  push    rsi
0x140069983  push    rdi
0x140069984  push    r14
0x140069986  sub     rsp, 20h
0x14006998a  mov     rbx, rcx
0x14006998d  mov     esi, r8d
0x140069990  mov     rcx, [rcx+0A38h]
0x140069997  xor     eax, eax
0x140069999  mov     r14, rdx
0x14006999c  mov     word ptr [rsp+38h+LockState.LockState], ax
0x1400699a1  xor     edi, edi
0x1400699a3  lea     rdx, [rsp+38h+LockState]; LockState
0x1400699a8  mov     [rsp+38h+LockState.OldIrql], dil
0x1400699ad  xor     r8d, r8d; Flags
0x1400699b0  mov     rcx, [rcx+90h]; Lock
0x1400699b7  call    cs:__imp_NdisAcquireRWLockWrite
0x1400699be  nop     dword ptr [rax+rax+00h]
0x1400699c3  cmp     [rbx+724h], esi
0x1400699c9  jnb     loc_140069AA9
0x1400699cf  lea     eax, [rsi+10h]
0x1400699d2  cmp     eax, 10h
0x1400699d5  jnb     short loc_1400699E1
0x1400699d7  mov     edi, 0C000009Ah
0x1400699dc  jmp     loc_140069AA1
0x1400699e1  mov     ecx, 40h ; '@'
0x1400699e6  mov     ebp, 32697377h
0x1400699eb  cmp     eax, ecx
0x1400699ed  ja      short loc_1400699F8
0x1400699ef  lea     rdi, WPP_MAIN_CB.DeviceQueue
0x1400699f6  jmp     short loc_140069A26
0x1400699f8  cmp     eax, 100h
0x1400699fd  ja      short loc_140069A08
0x1400699ff  lea     rdi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140069a06  jmp     short loc_140069A26
0x140069a08  cmp     eax, 400h
0x140069a0d  ja      short loc_140069A18
0x140069a0f  lea     rdi, Lookaside
0x140069a16  jmp     short loc_140069A26
0x140069a18  cmp     eax, 800h
0x140069a1d  ja      short loc_140069A37
0x140069a1f  lea     rdi, stru_1400B31C0
0x140069a26  mov     rcx, rdi; Lookaside
0x140069a29  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140069a30  nop     dword ptr [rax+rax+00h]
0x140069a35  jmp     short loc_140069A48
0x140069a37  mov     edx, eax
0x140069a39  mov     r8d, ebp
0x140069a3c  call    cs:__imp_ExAllocatePool2
0x140069a43  nop     dword ptr [rax+rax+00h]
0x140069a48  test    rax, rax
0x140069a4b  jz      short loc_1400699D7
0x140069a4d  mov     [rax], rdi
0x140069a50  xor     edi, edi
0x140069a52  mov     [rax+8], ebp
0x140069a55  lea     rbp, [rax+10h]
0x140069a59  mov     rcx, [rbx+718h]
0x140069a60  test    rcx, rcx
0x140069a63  jz      short loc_140069A94
0x140069a65  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140069a69  mov     rax, [rcx]
0x140069a6c  test    rax, rax
0x140069a6f  jz      short loc_140069A85
0x140069a71  mov     rdx, rcx; Entry
0x140069a74  mov     rcx, rax; Lookaside
0x140069a77  call    cs:__imp_ExFreeToNPagedLookasideList
0x140069a7e  nop     dword ptr [rax+rax+00h]
0x140069a83  jmp     short loc_140069A94
0x140069a85  mov     edx, [rcx+8]; Tag
0x140069a88  call    cs:__imp_ExFreePoolWithTag
0x140069a8f  nop     dword ptr [rax+rax+00h]
0x140069a94  mov     [rbx+718h], rbp
0x140069a9b  mov     [rbx+724h], esi
0x140069aa1  cmp     [rbx+724h], esi
0x140069aa7  jb      short loc_140069AC1
0x140069aa9  mov     rcx, [rbx+718h]; void *
0x140069ab0  mov     r8, rsi; Size
0x140069ab3  mov     rdx, r14; Src
0x140069ab6  mov     [rbx+720h], esi
0x140069abc  call    memmove
0x140069ac1  mov     rcx, [rbx+0A38h]
0x140069ac8  lea     rdx, [rsp+38h+LockState]; LockState
0x140069acd  mov     rcx, [rcx+90h]; Lock
0x140069ad4  call    cs:__imp_NdisReleaseRWLock
0x140069adb  nop     dword ptr [rax+rax+00h]
0x140069ae0  mov     rbx, [rsp+38h+arg_0]
0x140069ae5  mov     eax, edi
0x140069ae7  mov     rbp, [rsp+38h+arg_8]
0x140069aec  add     rsp, 20h
0x140069af0  pop     r14
0x140069af2  pop     rdi
0x140069af3  pop     rsi
0x140069af4  retn
```
