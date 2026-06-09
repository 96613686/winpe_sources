# WFDRoleIoctlSetPersistentGroupIdList(_WFD_IOCTL_HANDLER_ENTRY const *,_WFD_ROLE *,_IRP *,uchar *,ulong)

- ea: `0x14007b100`
- end: `0x14007b337`
- name: `?WFDRoleIoctlSetPersistentGroupIdList@@YAHPEBU_WFD_IOCTL_HANDLER_ENTRY@@PEAU_WFD_ROLE@@PEAU_IRP@@PEAEK@Z`
- size: `567`
- prototype: `__int64 __fastcall(const struct _WFD_IOCTL_HANDLER_ENTRY *, struct _WFD_ROLE *, struct _IRP *, unsigned __int8 *, size_t Size)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x14000d22c`
- `0x140020dc0`
- `0x14007b100`
- `0x14009a4c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007b1c2`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007b1c2`
- `ntoskrnl!ExAllocatePool2` at `0x14007b1da`
- `ntoskrnl!ExAllocatePool2` at `0x14007b1da`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007b2a5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007b2a5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b2b6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b2b6`
- `NDIS!NdisAcquireRWLockWrite` at `0x14007b27e`
- `NDIS!NdisAcquireRWLockWrite` at `0x14007b27e`
- `NDIS!NdisReleaseRWLock` at `0x14007b2cf`
- `NDIS!NdisReleaseRWLock` at `0x14007b2cf`

## pseudocode

```c
__int64 __fastcall WFDRoleIoctlSetPersistentGroupIdList(
        const struct _WFD_IOCTL_HANDLER_ENTRY *a1,
        struct _WFD_ROLE *a2,
        struct _IRP *a3,
        unsigned __int8 *a4,
        size_t Size)
{
  size_t v7; // rbp
  unsigned int v8; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rbx
  char *Pool2; // rax
  unsigned int v11; // ebx
  _DOT11_WFD_PERSISTENT_GROUP_ID_LIST *v12; // rbx
  _DOT11_WFD_PERSISTENT_GROUP_ID_LIST *pCachedPersistentGroupIdList; // rcx
  ULONG *v14; // rcx
  struct _LOCK_STATE_EX LockState; // [rsp+78h] [rbp+20h] BYREF

  LockState.OldIrql = 0;
  *(_WORD *)&LockState.LockState = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 68, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids);
  if ( !a4 || (v7 = (unsigned int)Size, (unsigned int)Size < 52 * (unsigned __int64)*((unsigned int *)a4 + 1) + 8) )
  {
    v11 = -1073676267;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return v11;
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 69, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids, 3221291029LL);
    goto LABEL_31;
  }
  if ( !*a4 )
  {
    v12 = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 72, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids);
    goto LABEL_24;
  }
  v8 = Size + 16;
  if ( (unsigned int)Size < 0xFFFFFFF0 )
  {
    if ( v8 > 0x40 )
    {
      if ( v8 > 0x100 )
      {
        if ( v8 > 0x400 )
        {
          if ( v8 > 0x800 )
          {
            p_WaitListHead = 0;
            Pool2 = (char *)ExAllocatePool2(64, v8, 808679286, a4);
            goto LABEL_17;
          }
          p_WaitListHead = &stru_1400B0180;
        }
        else
        {
          p_WaitListHead = &Lookaside;
        }
      }
      else
      {
        p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      }
    }
    else
    {
      p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
    }
    Pool2 = (char *)ExAllocateFromNPagedLookasideList(p_WaitListHead);
LABEL_17:
    if ( !Pool2 )
      goto LABEL_18;
    *(_QWORD *)Pool2 = p_WaitListHead;
    v12 = (_DOT11_WFD_PERSISTENT_GROUP_ID_LIST *)(Pool2 + 16);
    *((_DWORD *)Pool2 + 2) = 808679286;
    memmove(Pool2 + 16, a4, v7);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        71,
        WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids,
        *((unsigned int *)a4 + 1));
LABEL_24:
    NdisAcquireRWLockWrite(a2->pRWLock, &LockState, 0);
    pCachedPersistentGroupIdList = a2->pCachedPersistentGroupIdList;
    if ( pCachedPersistentGroupIdList )
    {
      v14 = (ULONG *)&pCachedPersistentGroupIdList[-1].GroupList[0].GroupId.SSID.ucSSID[16];
      if ( *(_QWORD *)v14 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v14, v14);
      else
        ExFreePoolWithTag(v14, v14[2]);
    }
    a2->pCachedPersistentGroupIdList = v12;
    NdisReleaseRWLock(a2->pRWLock, &LockState);
    v11 = 0;
    goto LABEL_31;
  }
LABEL_18:
  v11 = -1073741670;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    return v11;
  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 70, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids);
LABEL_31:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 73, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids, v11);
  return v11;
}

```

## disassembly

```asm
0x14007b100  push    rbx
0x14007b102  push    rbp
0x14007b103  push    rsi
0x14007b104  push    rdi
0x14007b105  push    r14
0x14007b107  push    r15
0x14007b109  sub     rsp, 28h
0x14007b10d  xor     eax, eax
0x14007b10f  mov     [rsp+58h+LockState.OldIrql], 0
0x14007b114  mov     word ptr [rsp+58h+LockState.LockState], ax
0x14007b119  mov     rdi, r9
0x14007b11c  mov     rsi, rdx
0x14007b11f  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b126  lea     r15, WPP_GLOBAL_Control
0x14007b12d  lea     r14, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x14007b134  cmp     rcx, r15
0x14007b137  jz      short loc_14007B148
0x14007b139  mov     rcx, [rcx+18h]
0x14007b13d  lea     edx, [rax+44h]
0x14007b140  mov     r8, r14
0x14007b143  call    WPP_SF_
0x14007b148  test    rdi, rdi
0x14007b14b  jz      loc_14007B2DF
0x14007b151  mov     edx, dword ptr [rsp+58h+Size]
0x14007b158  mov     eax, [rdi+4]
0x14007b15b  mov     ebp, edx
0x14007b15d  imul    rcx, rax, 34h ; '4'
0x14007b161  add     rcx, 8
0x14007b165  cmp     rdx, rcx
0x14007b168  jb      loc_14007B2DF
0x14007b16e  cmp     byte ptr [rdi], 0
0x14007b171  jz      loc_14007B255
0x14007b177  lea     eax, [rdx+10h]
0x14007b17a  cmp     eax, 10h
0x14007b17d  jb      short loc_14007B1EB
0x14007b17f  mov     ecx, 40h ; '@'
0x14007b184  cmp     eax, ecx
0x14007b186  ja      short loc_14007B191
0x14007b188  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x14007b18f  jmp     short loc_14007B1BF
0x14007b191  cmp     eax, 100h
0x14007b196  ja      short loc_14007B1A1
0x14007b198  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14007b19f  jmp     short loc_14007B1BF
0x14007b1a1  cmp     eax, 400h
0x14007b1a6  ja      short loc_14007B1B1
0x14007b1a8  lea     rbx, Lookaside
0x14007b1af  jmp     short loc_14007B1BF
0x14007b1b1  cmp     eax, 800h
0x14007b1b6  ja      short loc_14007B1D0
0x14007b1b8  lea     rbx, stru_1400B0180
0x14007b1bf  mov     rcx, rbx; Lookaside
0x14007b1c2  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14007b1c9  nop     dword ptr [rax+rax+00h]
0x14007b1ce  jmp     short loc_14007B1E6
0x14007b1d0  xor     ebx, ebx
0x14007b1d2  mov     edx, eax
0x14007b1d4  mov     r8d, 30337776h
0x14007b1da  call    cs:__imp_ExAllocatePool2
0x14007b1e1  nop     dword ptr [rax+rax+00h]
0x14007b1e6  test    rax, rax
0x14007b1e9  jnz     short loc_14007B216
0x14007b1eb  mov     ebx, 0C000009Ah
0x14007b1f0  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b1f7  cmp     rcx, r15
0x14007b1fa  jz      loc_14007B327
0x14007b200  mov     rcx, [rcx+18h]
0x14007b204  mov     edx, 46h ; 'F'
0x14007b209  mov     r8, r14
0x14007b20c  call    WPP_SF_
0x14007b211  jmp     loc_14007B307
0x14007b216  mov     [rax], rbx
0x14007b219  mov     r8, rbp; Size
0x14007b21c  lea     rbx, [rax+10h]
0x14007b220  mov     dword ptr [rax+8], 30337776h
0x14007b227  mov     rcx, rbx; void *
0x14007b22a  mov     rdx, rdi; Src
0x14007b22d  call    memmove
0x14007b232  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b239  cmp     rcx, r15
0x14007b23c  jz      short loc_14007B272
0x14007b23e  mov     r9d, [rdi+4]
0x14007b242  mov     edx, 47h ; 'G'
0x14007b247  mov     rcx, [rcx+18h]
0x14007b24b  mov     r8, r14
0x14007b24e  call    WPP_SF_d
0x14007b253  jmp     short loc_14007B272
0x14007b255  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b25c  xor     ebx, ebx
0x14007b25e  cmp     rcx, r15
0x14007b261  jz      short loc_14007B272
0x14007b263  mov     rcx, [rcx+18h]
0x14007b267  lea     edx, [rbx+48h]
0x14007b26a  mov     r8, r14
0x14007b26d  call    WPP_SF_
0x14007b272  mov     rcx, [rsi+20h]; Lock
0x14007b276  lea     rdx, [rsp+58h+LockState]; LockState
0x14007b27b  xor     r8d, r8d; Flags
0x14007b27e  call    cs:__imp_NdisAcquireRWLockWrite
0x14007b285  nop     dword ptr [rax+rax+00h]
0x14007b28a  mov     rcx, [rsi+48h]
0x14007b28e  test    rcx, rcx
0x14007b291  jz      short loc_14007B2C2
0x14007b293  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14007b297  mov     rax, [rcx]
0x14007b29a  test    rax, rax
0x14007b29d  jz      short loc_14007B2B3
0x14007b29f  mov     rdx, rcx; Entry
0x14007b2a2  mov     rcx, rax; Lookaside
0x14007b2a5  call    cs:__imp_ExFreeToNPagedLookasideList
0x14007b2ac  nop     dword ptr [rax+rax+00h]
0x14007b2b1  jmp     short loc_14007B2C2
0x14007b2b3  mov     edx, [rcx+8]; Tag
0x14007b2b6  call    cs:__imp_ExFreePoolWithTag
0x14007b2bd  nop     dword ptr [rax+rax+00h]
0x14007b2c2  mov     [rsi+48h], rbx
0x14007b2c6  mov     rcx, [rsi+20h]; Lock
0x14007b2ca  lea     rdx, [rsp+58h+LockState]; LockState
0x14007b2cf  call    cs:__imp_NdisReleaseRWLock
0x14007b2d6  nop     dword ptr [rax+rax+00h]
0x14007b2db  xor     ebx, ebx
0x14007b2dd  jmp     short loc_14007B307
0x14007b2df  mov     ebx, 0C0010015h
0x14007b2e4  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b2eb  cmp     rcx, r15
0x14007b2ee  jz      short loc_14007B327
0x14007b2f0  mov     rcx, [rcx+18h]
0x14007b2f4  mov     edx, 45h ; 'E'
0x14007b2f9  mov     r9d, 0C0010015h
0x14007b2ff  mov     r8, r14
0x14007b302  call    WPP_SF_d
0x14007b307  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b30e  cmp     rcx, r15
0x14007b311  jz      short loc_14007B327
0x14007b313  mov     rcx, [rcx+18h]
0x14007b317  mov     edx, 49h ; 'I'
0x14007b31c  mov     r9d, ebx
0x14007b31f  mov     r8, r14
0x14007b322  call    WPP_SF_d
0x14007b327  mov     eax, ebx
0x14007b329  add     rsp, 28h
0x14007b32d  pop     r15
0x14007b32f  pop     r14
0x14007b331  pop     rdi
0x14007b332  pop     rsi
0x14007b333  pop     rbp
0x14007b334  pop     rbx
0x14007b335  retn
```
