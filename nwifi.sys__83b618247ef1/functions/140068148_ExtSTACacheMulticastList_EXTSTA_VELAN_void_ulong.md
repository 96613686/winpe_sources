# ExtSTACacheMulticastList(EXTSTA_VELAN *,void *,ulong)

- ea: `0x140068148`
- end: `0x1400682c6`
- name: `?ExtSTACacheMulticastList@@YAHPEAUEXTSTA_VELAN@@PEAXK@Z`
- size: `382`
- prototype: `int(struct EXTSTA_VELAN *, void *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140068540`

## callees

- `0x140068148`
- `0x14009a4c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400681f9`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400681f9`
- `ntoskrnl!ExAllocatePool2` at `0x14006820c`
- `ntoskrnl!ExAllocatePool2` at `0x14006820c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140068247`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140068247`
- `ntoskrnl!ExFreePoolWithTag` at `0x140068258`
- `ntoskrnl!ExFreePoolWithTag` at `0x140068258`
- `NDIS!NdisAcquireRWLockWrite` at `0x140068187`
- `NDIS!NdisAcquireRWLockWrite` at `0x140068187`
- `NDIS!NdisReleaseRWLock` at `0x1400682a4`
- `NDIS!NdisReleaseRWLock` at `0x1400682a4`

## pseudocode

```c
__int64 __fastcall ExtSTACacheMulticastList(struct EXTSTA_VELAN *a1, void *a2, unsigned int a3)
{
  size_t v4; // rsi
  _VELAN *pGenVElan; // rcx
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rdi
  __int64 v8; // r9
  unsigned int v9; // eax
  _DWORD *Pool2; // rax
  void *v11; // rbp
  char *pMcastList; // rcx
  ULONG *v13; // rcx
  void *v14; // rcx
  struct _LOCK_STATE_EX LockState; // [rsp+50h] [rbp+18h] BYREF

  v4 = a3;
  pGenVElan = a1->pGenVElan;
  *(_WORD *)&LockState.LockState = 0;
  p_DeviceQueue = 0;
  LockState.OldIrql = 0;
  NdisAcquireRWLockWrite(pGenVElan->pRWLock, &LockState, 0);
  if ( a1->Rw.MulticastList.uMaxListSize >= (unsigned int)v4 )
    goto LABEL_21;
  v9 = v4 + 16;
  if ( (unsigned int)v4 >= 0xFFFFFFF0 )
    goto LABEL_3;
  if ( v9 <= 0x40 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_12:
    Pool2 = ExAllocateFromNPagedLookasideList(p_DeviceQueue);
    goto LABEL_14;
  }
  if ( v9 <= 0x100 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_12;
  }
  if ( v9 <= 0x400 )
  {
    p_DeviceQueue = &Lookaside;
    goto LABEL_12;
  }
  if ( v9 <= 0x800 )
  {
    p_DeviceQueue = &stru_1400B0180;
    goto LABEL_12;
  }
  Pool2 = (_DWORD *)ExAllocatePool2(64, v9, 845771639, v8);
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
  v11 = Pool2 + 4;
  pMcastList = (char *)a1->Rw.MulticastList.pMcastList;
  if ( pMcastList )
  {
    v13 = (ULONG *)(pMcastList - 16);
    if ( *(_QWORD *)v13 )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v13, v13);
    else
      ExFreePoolWithTag(v13, v13[2]);
  }
  a1->Rw.MulticastList.pMcastList = v11;
  a1->Rw.MulticastList.uMaxListSize = v4;
LABEL_20:
  if ( a1->Rw.MulticastList.uMaxListSize >= (unsigned int)v4 )
  {
LABEL_21:
    v14 = a1->Rw.MulticastList.pMcastList;
    a1->Rw.MulticastList.uCurrentListSize = v4;
    memmove(v14, a2, v4);
  }
  NdisReleaseRWLock(a1->pGenVElan->pRWLock, &LockState);
  return (unsigned int)p_DeviceQueue;
}

```

## disassembly

```asm
0x140068148  mov     [rsp+arg_0], rbx
0x14006814d  mov     [rsp+arg_8], rbp
0x140068152  push    rsi
0x140068153  push    rdi
0x140068154  push    r14
0x140068156  sub     rsp, 20h
0x14006815a  mov     rbx, rcx
0x14006815d  mov     esi, r8d
0x140068160  mov     rcx, [rcx+0A38h]
0x140068167  xor     eax, eax
0x140068169  mov     r14, rdx
0x14006816c  mov     word ptr [rsp+38h+LockState.LockState], ax
0x140068171  xor     edi, edi
0x140068173  lea     rdx, [rsp+38h+LockState]; LockState
0x140068178  mov     [rsp+38h+LockState.OldIrql], dil
0x14006817d  xor     r8d, r8d; Flags
0x140068180  mov     rcx, [rcx+90h]; Lock
0x140068187  call    cs:__imp_NdisAcquireRWLockWrite
0x14006818e  nop     dword ptr [rax+rax+00h]
0x140068193  cmp     [rbx+724h], esi
0x140068199  jnb     loc_140068279
0x14006819f  lea     eax, [rsi+10h]
0x1400681a2  cmp     eax, 10h
0x1400681a5  jnb     short loc_1400681B1
0x1400681a7  mov     edi, 0C000009Ah
0x1400681ac  jmp     loc_140068271
0x1400681b1  mov     ecx, 40h ; '@'
0x1400681b6  mov     ebp, 32697377h
0x1400681bb  cmp     eax, ecx
0x1400681bd  ja      short loc_1400681C8
0x1400681bf  lea     rdi, WPP_MAIN_CB.DeviceQueue
0x1400681c6  jmp     short loc_1400681F6
0x1400681c8  cmp     eax, 100h
0x1400681cd  ja      short loc_1400681D8
0x1400681cf  lea     rdi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x1400681d6  jmp     short loc_1400681F6
0x1400681d8  cmp     eax, 400h
0x1400681dd  ja      short loc_1400681E8
0x1400681df  lea     rdi, Lookaside
0x1400681e6  jmp     short loc_1400681F6
0x1400681e8  cmp     eax, 800h
0x1400681ed  ja      short loc_140068207
0x1400681ef  lea     rdi, stru_1400B0180
0x1400681f6  mov     rcx, rdi; Lookaside
0x1400681f9  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140068200  nop     dword ptr [rax+rax+00h]
0x140068205  jmp     short loc_140068218
0x140068207  mov     edx, eax
0x140068209  mov     r8d, ebp
0x14006820c  call    cs:__imp_ExAllocatePool2
0x140068213  nop     dword ptr [rax+rax+00h]
0x140068218  test    rax, rax
0x14006821b  jz      short loc_1400681A7
0x14006821d  mov     [rax], rdi
0x140068220  xor     edi, edi
0x140068222  mov     [rax+8], ebp
0x140068225  lea     rbp, [rax+10h]
0x140068229  mov     rcx, [rbx+718h]
0x140068230  test    rcx, rcx
0x140068233  jz      short loc_140068264
0x140068235  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140068239  mov     rax, [rcx]
0x14006823c  test    rax, rax
0x14006823f  jz      short loc_140068255
0x140068241  mov     rdx, rcx; Entry
0x140068244  mov     rcx, rax; Lookaside
0x140068247  call    cs:__imp_ExFreeToNPagedLookasideList
0x14006824e  nop     dword ptr [rax+rax+00h]
0x140068253  jmp     short loc_140068264
0x140068255  mov     edx, [rcx+8]; Tag
0x140068258  call    cs:__imp_ExFreePoolWithTag
0x14006825f  nop     dword ptr [rax+rax+00h]
0x140068264  mov     [rbx+718h], rbp
0x14006826b  mov     [rbx+724h], esi
0x140068271  cmp     [rbx+724h], esi
0x140068277  jb      short loc_140068291
0x140068279  mov     rcx, [rbx+718h]; void *
0x140068280  mov     r8, rsi; Size
0x140068283  mov     rdx, r14; Src
0x140068286  mov     [rbx+720h], esi
0x14006828c  call    memmove
0x140068291  mov     rcx, [rbx+0A38h]
0x140068298  lea     rdx, [rsp+38h+LockState]; LockState
0x14006829d  mov     rcx, [rcx+90h]; Lock
0x1400682a4  call    cs:__imp_NdisReleaseRWLock
0x1400682ab  nop     dword ptr [rax+rax+00h]
0x1400682b0  mov     rbx, [rsp+38h+arg_0]
0x1400682b5  mov     eax, edi
0x1400682b7  mov     rbp, [rsp+38h+arg_8]
0x1400682bc  add     rsp, 20h
0x1400682c0  pop     r14
0x1400682c2  pop     rdi
0x1400682c3  pop     rsi
0x1400682c4  retn
```
