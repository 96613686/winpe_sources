# WFDRoleIoctlSetPersistentGroupIdList(_WFD_IOCTL_HANDLER_ENTRY const *,_WFD_ROLE *,_IRP *,uchar *,ulong)

- ea: `0x14007c930`
- end: `0x14007cb67`
- name: `?WFDRoleIoctlSetPersistentGroupIdList@@YAHPEBU_WFD_IOCTL_HANDLER_ENTRY@@PEAU_WFD_ROLE@@PEAU_IRP@@PEAEK@Z`
- size: `567`
- prototype: `__int64 __fastcall(const struct _WFD_IOCTL_HANDLER_ENTRY *, struct _WFD_ROLE *, struct _IRP *, unsigned __int8 *, size_t Size)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x14000d21c`
- `0x140020dc0`
- `0x14007c930`
- `0x14009bcc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007c9f2`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007c9f2`
- `ntoskrnl!ExAllocatePool2` at `0x14007ca0a`
- `ntoskrnl!ExAllocatePool2` at `0x14007ca0a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007cad5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007cad5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007cae6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007cae6`
- `NDIS!NdisAcquireRWLockWrite` at `0x14007caae`
- `NDIS!NdisAcquireRWLockWrite` at `0x14007caae`
- `NDIS!NdisReleaseRWLock` at `0x14007caff`
- `NDIS!NdisReleaseRWLock` at `0x14007caff`

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
            Pool2 = (char *)ExAllocatePool2(64, v8, 808679286);
            goto LABEL_17;
          }
          p_WaitListHead = &stru_1400B31C0;
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
0x14007c930  push    rbx
0x14007c932  push    rbp
0x14007c933  push    rsi
0x14007c934  push    rdi
0x14007c935  push    r14
0x14007c937  push    r15
0x14007c939  sub     rsp, 28h
0x14007c93d  xor     eax, eax
0x14007c93f  mov     [rsp+58h+LockState.OldIrql], 0
0x14007c944  mov     word ptr [rsp+58h+LockState.LockState], ax
0x14007c949  mov     rdi, r9
0x14007c94c  mov     rsi, rdx
0x14007c94f  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c956  lea     r15, WPP_GLOBAL_Control
0x14007c95d  lea     r14, WPP_a6c1fa7bb8453ce1dc93022cc2702135_Traceguids
0x14007c964  cmp     rcx, r15
0x14007c967  jz      short loc_14007C978
0x14007c969  mov     rcx, [rcx+18h]
0x14007c96d  lea     edx, [rax+44h]
0x14007c970  mov     r8, r14
0x14007c973  call    WPP_SF_
0x14007c978  test    rdi, rdi
0x14007c97b  jz      loc_14007CB0F
0x14007c981  mov     edx, dword ptr [rsp+58h+Size]
0x14007c988  mov     eax, [rdi+4]
0x14007c98b  mov     ebp, edx
0x14007c98d  imul    rcx, rax, 34h ; '4'
0x14007c991  add     rcx, 8
0x14007c995  cmp     rdx, rcx
0x14007c998  jb      loc_14007CB0F
0x14007c99e  cmp     byte ptr [rdi], 0
0x14007c9a1  jz      loc_14007CA85
0x14007c9a7  lea     eax, [rdx+10h]
0x14007c9aa  cmp     eax, 10h
0x14007c9ad  jb      short loc_14007CA1B
0x14007c9af  mov     ecx, 40h ; '@'
0x14007c9b4  cmp     eax, ecx
0x14007c9b6  ja      short loc_14007C9C1
0x14007c9b8  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x14007c9bf  jmp     short loc_14007C9EF
0x14007c9c1  cmp     eax, 100h
0x14007c9c6  ja      short loc_14007C9D1
0x14007c9c8  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14007c9cf  jmp     short loc_14007C9EF
0x14007c9d1  cmp     eax, 400h
0x14007c9d6  ja      short loc_14007C9E1
0x14007c9d8  lea     rbx, Lookaside
0x14007c9df  jmp     short loc_14007C9EF
0x14007c9e1  cmp     eax, 800h
0x14007c9e6  ja      short loc_14007CA00
0x14007c9e8  lea     rbx, stru_1400B31C0
0x14007c9ef  mov     rcx, rbx; Lookaside
0x14007c9f2  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14007c9f9  nop     dword ptr [rax+rax+00h]
0x14007c9fe  jmp     short loc_14007CA16
0x14007ca00  xor     ebx, ebx
0x14007ca02  mov     edx, eax
0x14007ca04  mov     r8d, 30337776h
0x14007ca0a  call    cs:__imp_ExAllocatePool2
0x14007ca11  nop     dword ptr [rax+rax+00h]
0x14007ca16  test    rax, rax
0x14007ca19  jnz     short loc_14007CA46
0x14007ca1b  mov     ebx, 0C000009Ah
0x14007ca20  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ca27  cmp     rcx, r15
0x14007ca2a  jz      loc_14007CB57
0x14007ca30  mov     rcx, [rcx+18h]
0x14007ca34  mov     edx, 46h ; 'F'
0x14007ca39  mov     r8, r14
0x14007ca3c  call    WPP_SF_
0x14007ca41  jmp     loc_14007CB37
0x14007ca46  mov     [rax], rbx
0x14007ca49  mov     r8, rbp; Size
0x14007ca4c  lea     rbx, [rax+10h]
0x14007ca50  mov     dword ptr [rax+8], 30337776h
0x14007ca57  mov     rcx, rbx; void *
0x14007ca5a  mov     rdx, rdi; Src
0x14007ca5d  call    memmove
0x14007ca62  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ca69  cmp     rcx, r15
0x14007ca6c  jz      short loc_14007CAA2
0x14007ca6e  mov     r9d, [rdi+4]
0x14007ca72  mov     edx, 47h ; 'G'
0x14007ca77  mov     rcx, [rcx+18h]
0x14007ca7b  mov     r8, r14
0x14007ca7e  call    WPP_SF_d
0x14007ca83  jmp     short loc_14007CAA2
0x14007ca85  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ca8c  xor     ebx, ebx
0x14007ca8e  cmp     rcx, r15
0x14007ca91  jz      short loc_14007CAA2
0x14007ca93  mov     rcx, [rcx+18h]
0x14007ca97  lea     edx, [rbx+48h]
0x14007ca9a  mov     r8, r14
0x14007ca9d  call    WPP_SF_
0x14007caa2  mov     rcx, [rsi+20h]; Lock
0x14007caa6  lea     rdx, [rsp+58h+LockState]; LockState
0x14007caab  xor     r8d, r8d; Flags
0x14007caae  call    cs:__imp_NdisAcquireRWLockWrite
0x14007cab5  nop     dword ptr [rax+rax+00h]
0x14007caba  mov     rcx, [rsi+48h]
0x14007cabe  test    rcx, rcx
0x14007cac1  jz      short loc_14007CAF2
0x14007cac3  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14007cac7  mov     rax, [rcx]
0x14007caca  test    rax, rax
0x14007cacd  jz      short loc_14007CAE3
0x14007cacf  mov     rdx, rcx; Entry
0x14007cad2  mov     rcx, rax; Lookaside
0x14007cad5  call    cs:__imp_ExFreeToNPagedLookasideList
0x14007cadc  nop     dword ptr [rax+rax+00h]
0x14007cae1  jmp     short loc_14007CAF2
0x14007cae3  mov     edx, [rcx+8]; Tag
0x14007cae6  call    cs:__imp_ExFreePoolWithTag
0x14007caed  nop     dword ptr [rax+rax+00h]
0x14007caf2  mov     [rsi+48h], rbx
0x14007caf6  mov     rcx, [rsi+20h]; Lock
0x14007cafa  lea     rdx, [rsp+58h+LockState]; LockState
0x14007caff  call    cs:__imp_NdisReleaseRWLock
0x14007cb06  nop     dword ptr [rax+rax+00h]
0x14007cb0b  xor     ebx, ebx
0x14007cb0d  jmp     short loc_14007CB37
0x14007cb0f  mov     ebx, 0C0010015h
0x14007cb14  mov     rcx, cs:WPP_GLOBAL_Control
0x14007cb1b  cmp     rcx, r15
0x14007cb1e  jz      short loc_14007CB57
0x14007cb20  mov     rcx, [rcx+18h]
0x14007cb24  mov     edx, 45h ; 'E'
0x14007cb29  mov     r9d, 0C0010015h
0x14007cb2f  mov     r8, r14
0x14007cb32  call    WPP_SF_d
0x14007cb37  mov     rcx, cs:WPP_GLOBAL_Control
0x14007cb3e  cmp     rcx, r15
0x14007cb41  jz      short loc_14007CB57
0x14007cb43  mov     rcx, [rcx+18h]
0x14007cb47  mov     edx, 49h ; 'I'
0x14007cb4c  mov     r9d, ebx
0x14007cb4f  mov     r8, r14
0x14007cb52  call    WPP_SF_d
0x14007cb57  mov     eax, ebx
0x14007cb59  add     rsp, 28h
0x14007cb5d  pop     r15
0x14007cb5f  pop     r14
0x14007cb61  pop     rdi
0x14007cb62  pop     rsi
0x14007cb63  pop     rbp
0x14007cb64  pop     rbx
0x14007cb65  retn
```
