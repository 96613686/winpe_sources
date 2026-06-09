# IoctlGetPmkIdList(_FILE_OBJECT *,void *,ulong,ulong *)

- ea: `0x14004ea64`
- end: `0x14004ed86`
- name: `?IoctlGetPmkIdList@@YAJPEAU_FILE_OBJECT@@PEAXKPEAK@Z`
- size: `802`
- prototype: `int(struct _FILE_OBJECT *, void *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x1400337f4`

## callees

- `0x140020dc0`
- `0x140020f20`
- `0x14004ea64`
- `0x140052fd8`
- `0x14008f3f8`
- `0x14009a4c0`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004eb95`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004eb95`
- `ntoskrnl!ExAllocatePool2` at `0x14004ebaa`
- `ntoskrnl!ExAllocatePool2` at `0x14004ebaa`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004ed17`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004ed17`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004ed2b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004ed2b`
- `NDIS!NdisAcquireRWLockWrite` at `0x14004ec3f`
- `NDIS!NdisAcquireRWLockWrite` at `0x14004ec3f`
- `NDIS!NdisReleaseRWLock` at `0x14004ecd9`
- `NDIS!NdisReleaseRWLock` at `0x14004ecd9`

## pseudocode

```c
__int64 __fastcall IoctlGetPmkIdList(struct _FILE_OBJECT *a1, unsigned int *a2, unsigned int a3, unsigned int *a4)
{
  unsigned int *v4; // r12
  unsigned int v5; // r15d
  __int64 v7; // r13
  unsigned int PmkId; // ebx
  __int64 v9; // r9
  __int64 v10; // r8
  unsigned int v11; // ecx
  unsigned int v12; // edi
  unsigned int v13; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rbx
  _DWORD *Pool2; // rax
  PNPAGED_LOOKASIDE_LIST *v16; // rsi
  _DWORD *v17; // rbp
  unsigned int v18; // edi
  __int64 v19; // r12
  __int64 v20; // rdx
  struct _LOCK_STATE_EX LockState; // [rsp+A0h] [rbp+8h] BYREF
  PNPAGED_LOOKASIDE_LIST *v23; // [rsp+A8h] [rbp+10h]
  unsigned int v24; // [rsp+B0h] [rbp+18h]
  unsigned int *v25; // [rsp+B8h] [rbp+20h]

  v25 = a4;
  v24 = a3;
  v4 = a4;
  v5 = a3;
  v7 = *((_QWORD *)a1->FsContext + 2);
  LockState.OldIrql = 0;
  *(_WORD *)&LockState.LockState = 0;
  if ( a3 < 0x2C )
  {
    PmkId = -1073741811;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 357, WPP_e90d411d816e312466897e39e745b158_Traceguids, a3, 44);
    return PmkId;
  }
  v9 = *a2;
  if ( (_DWORD)v9 )
  {
    PmkId = -1073741811;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 358, WPP_e90d411d816e312466897e39e745b158_Traceguids, v9, 1);
    return PmkId;
  }
  v10 = a2[2];
  v11 = 28 * v10;
  if ( (unsigned __int64)(28 * v10) > 0xFFFFFFFF )
  {
    v12 = 0;
    v11 = -1;
LABEL_35:
    PmkId = -1073741811;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_dDDD(WPP_GLOBAL_Control->AttachedDevice, WPP_GLOBAL_Control, v10, v5, v10, v11, v12);
    return PmkId;
  }
  v12 = v11 + 16;
  if ( v11 + 16 < v11 )
  {
    v12 = -1;
    goto LABEL_35;
  }
  if ( v5 < v12 )
    goto LABEL_35;
  v13 = v11 + 32;
  if ( v12 >= 0xFFFFFFF0 )
    goto LABEL_23;
  if ( v13 > 0x40 )
  {
    if ( v13 > 0x100 )
    {
      if ( v13 > 0x400 )
      {
        if ( v13 > 0x800 )
        {
          p_WaitListHead = 0;
          Pool2 = (_DWORD *)ExAllocatePool2(64, v13, 2053731191, v9);
          goto LABEL_22;
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
  Pool2 = ExAllocateFromNPagedLookasideList(p_WaitListHead);
LABEL_22:
  v23 = (PNPAGED_LOOKASIDE_LIST *)Pool2;
  v16 = (PNPAGED_LOOKASIDE_LIST *)Pool2;
  if ( !Pool2 )
  {
LABEL_23:
    PmkId = -1073741670;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 360, WPP_e90d411d816e312466897e39e745b158_Traceguids, v12);
    return PmkId;
  }
  Pool2[2] = 2053731191;
  *(_QWORD *)Pool2 = p_WaitListHead;
  v17 = Pool2 + 4;
  PmkId = 0;
  memset(Pool2 + 4, 0, v12);
  *(_QWORD *)v17 = *(_QWORD *)(a2 + 1);
  *((_DWORD *)v16 + 6) = a2[3];
  *((_DWORD *)v16 + 5) = 0;
  NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(v7 + 144), &LockState, 0);
  v18 = 0;
  if ( a2[2] )
  {
    do
    {
      v19 = 7LL * v18;
      PmkId = Dot11GetPmkId((struct _DOT11_PMK_CACHE *)(v7 + 8168));
      if ( !PmkId )
      {
        v20 = 7LL * *((unsigned int *)v16 + 5);
        v17[v20 + 3] = a2[v19 + 4];
        LOWORD(v17[v20 + 4]) = a2[v19 + 5];
        ++*((_DWORD *)v16 + 5);
      }
      ++v18;
    }
    while ( v18 < a2[2] );
    v16 = v23;
    v5 = v24;
    v4 = v25;
  }
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v7 + 144), &LockState);
  *v4 = 28 * v17[1] + 12;
  memset(a2, 0, v5);
  memmove(a2, v17, *v4);
  if ( *v16 )
    ExFreeToNPagedLookasideList(*v16, v16);
  else
    ExFreePoolWithTag(v16, *((_DWORD *)v16 + 2));
  return PmkId;
}

```

## disassembly

```asm
0x14004ea64  mov     r11, rsp
0x14004ea67  mov     [r11+20h], r9
0x14004ea6b  mov     [r11+18h], r8d
0x14004ea6f  push    rbx
0x14004ea70  push    rbp
0x14004ea71  push    rsi
0x14004ea72  push    rdi
0x14004ea73  push    r12
0x14004ea75  push    r13
0x14004ea77  push    r14
0x14004ea79  push    r15
0x14004ea7b  sub     rsp, 58h
0x14004ea7f  mov     rax, [rcx+18h]
0x14004ea83  mov     r12, r9
0x14004ea86  mov     r15d, r8d
0x14004ea89  mov     r14, rdx
0x14004ea8c  mov     r13, [rax+10h]
0x14004ea90  xor     eax, eax
0x14004ea92  mov     [rsp+98h+var_50], r13
0x14004ea97  mov     byte ptr [r11+8], 0
0x14004ea9c  mov     [r11+9], ax
0x14004eaa1  cmp     r8d, 2Ch ; ','
0x14004eaa5  jnb     short loc_14004EAE8
0x14004eaa7  mov     ebx, 0C000000Dh
0x14004eaac  mov     rcx, cs:WPP_GLOBAL_Control
0x14004eab3  lea     rax, WPP_GLOBAL_Control
0x14004eaba  cmp     rcx, rax
0x14004eabd  jz      loc_14004ED72
0x14004eac3  mov     edx, 165h
0x14004eac8  mov     [rsp+98h+var_78], 2Ch ; ','
0x14004ead0  mov     r9d, r8d
0x14004ead3  mov     rcx, [rcx+18h]
0x14004ead7  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x14004eade  call    WPP_SF_Dd
0x14004eae3  jmp     loc_14004ED72
0x14004eae8  mov     r9d, [rdx]
0x14004eaeb  test    r9d, r9d
0x14004eaee  jz      short loc_14004EB1B
0x14004eaf0  mov     ebx, 0C000000Dh
0x14004eaf5  mov     rcx, cs:WPP_GLOBAL_Control
0x14004eafc  lea     rax, WPP_GLOBAL_Control
0x14004eb03  cmp     rcx, rax
0x14004eb06  jz      loc_14004ED72
0x14004eb0c  mov     edx, 166h
0x14004eb11  mov     [rsp+98h+var_78], 1
0x14004eb19  jmp     short loc_14004EAD3
0x14004eb1b  mov     r8d, [rdx+8]
0x14004eb1f  mov     eax, 0FFFFFFFFh
0x14004eb24  imul    rcx, r8, 1Ch
0x14004eb28  cmp     rcx, rax
0x14004eb2b  ja      loc_14004ED3D
0x14004eb31  lea     edi, [rcx+10h]
0x14004eb34  cmp     edi, ecx
0x14004eb36  jb      loc_14004ED39
0x14004eb3c  cmp     r15d, edi
0x14004eb3f  jb      loc_14004ED41
0x14004eb45  lea     eax, [rdi+10h]
0x14004eb48  cmp     eax, 10h
0x14004eb4b  jb      short loc_14004EBC6
0x14004eb4d  mov     ecx, 40h ; '@'
0x14004eb52  mov     ebp, 7A697377h
0x14004eb57  cmp     eax, ecx
0x14004eb59  ja      short loc_14004EB64
0x14004eb5b  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x14004eb62  jmp     short loc_14004EB92
0x14004eb64  cmp     eax, 100h
0x14004eb69  ja      short loc_14004EB74
0x14004eb6b  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14004eb72  jmp     short loc_14004EB92
0x14004eb74  cmp     eax, 400h
0x14004eb79  ja      short loc_14004EB84
0x14004eb7b  lea     rbx, Lookaside
0x14004eb82  jmp     short loc_14004EB92
0x14004eb84  cmp     eax, 800h
0x14004eb89  ja      short loc_14004EBA3
0x14004eb8b  lea     rbx, stru_1400B0180
0x14004eb92  mov     rcx, rbx; Lookaside
0x14004eb95  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14004eb9c  nop     dword ptr [rax+rax+00h]
0x14004eba1  jmp     short loc_14004EBB6
0x14004eba3  xor     ebx, ebx
0x14004eba5  mov     edx, eax
0x14004eba7  mov     r8d, ebp
0x14004ebaa  call    cs:__imp_ExAllocatePool2
0x14004ebb1  nop     dword ptr [rax+rax+00h]
0x14004ebb6  mov     [rsp+98h+arg_8], rax
0x14004ebbe  mov     rsi, rax
0x14004ebc1  test    rax, rax
0x14004ebc4  jnz     short loc_14004EBFF
0x14004ebc6  mov     ebx, 0C000009Ah
0x14004ebcb  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ebd2  lea     rax, WPP_GLOBAL_Control
0x14004ebd9  cmp     rcx, rax
0x14004ebdc  jz      loc_14004ED72
0x14004ebe2  mov     rcx, [rcx+18h]
0x14004ebe6  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x14004ebed  mov     edx, 168h
0x14004ebf2  mov     r9d, edi
0x14004ebf5  call    WPP_SF_d
0x14004ebfa  jmp     loc_14004ED72
0x14004ebff  mov     [rsi+8], ebp
0x14004ec02  xor     edx, edx; Val
0x14004ec04  mov     [rsi], rbx
0x14004ec07  lea     rbp, [rsi+10h]
0x14004ec0b  mov     rcx, rbp; void *
0x14004ec0e  mov     r8d, edi; Size
0x14004ec11  xor     ebx, ebx
0x14004ec13  call    memset
0x14004ec18  movsd   xmm0, qword ptr [r14+4]
0x14004ec1e  lea     rdx, [rsp+98h+LockState]; LockState
0x14004ec26  movsd   qword ptr [rbp+0], xmm0
0x14004ec2b  xor     r8d, r8d; Flags
0x14004ec2e  mov     eax, [r14+0Ch]
0x14004ec32  mov     [rbp+8], eax
0x14004ec35  mov     [rbp+4], ebx
0x14004ec38  mov     rcx, [r13+90h]; Lock
0x14004ec3f  call    cs:__imp_NdisAcquireRWLockWrite
0x14004ec46  nop     dword ptr [rax+rax+00h]
0x14004ec4b  xor     edi, edi
0x14004ec4d  cmp     [r14+8], ebx
0x14004ec51  jbe     short loc_14004ECCA
0x14004ec53  lea     r15, [rbp+12h]
0x14004ec57  mov     eax, edi
0x14004ec59  lea     rdx, [r14+10h]
0x14004ec5d  imul    r12, rax, 1Ch
0x14004ec61  mov     eax, [rbp+4]
0x14004ec64  lea     r8, [r13+132Ah]
0x14004ec6b  imul    r9, rax, 1Ch
0x14004ec6f  add     rdx, r12
0x14004ec72  lea     rcx, [r13+1FE8h]; struct _DOT11_PMK_CACHE *
0x14004ec79  add     r9, r15
0x14004ec7c  call    Dot11GetPmkId
0x14004ec81  mov     ebx, eax
0x14004ec83  test    eax, eax
0x14004ec85  jnz     short loc_14004ECA5
0x14004ec87  mov     ecx, [rbp+4]
0x14004ec8a  imul    rdx, rcx, 1Ch
0x14004ec8e  mov     ecx, [r12+r14+10h]
0x14004ec93  mov     [rdx+rbp+0Ch], ecx
0x14004ec97  movzx   ecx, word ptr [r12+r14+14h]
0x14004ec9d  mov     [rdx+rbp+10h], cx
0x14004eca2  inc     dword ptr [rbp+4]
0x14004eca5  inc     edi
0x14004eca7  cmp     edi, [r14+8]
0x14004ecab  jb      short loc_14004EC57
0x14004ecad  mov     rsi, [rsp+98h+arg_8]
0x14004ecb5  mov     r15d, [rsp+98h+arg_10]
0x14004ecbd  mov     r13, [rsp+98h+var_50]
0x14004ecc2  mov     r12, [rsp+98h+arg_18]
0x14004ecca  mov     rcx, [r13+90h]; Lock
0x14004ecd1  lea     rdx, [rsp+98h+LockState]; LockState
0x14004ecd9  call    cs:__imp_NdisReleaseRWLock
0x14004ece0  nop     dword ptr [rax+rax+00h]
0x14004ece5  imul    eax, [rbp+4], 1Ch
0x14004ece9  xor     edx, edx; Val
0x14004eceb  mov     r8d, r15d; Size
0x14004ecee  mov     rcx, r14; void *
0x14004ecf1  add     eax, 0Ch
0x14004ecf4  mov     [r12], eax
0x14004ecf8  call    memset
0x14004ecfd  mov     r8d, [r12]; Size
0x14004ed01  mov     rdx, rbp; Src
0x14004ed04  mov     rcx, r14; void *
0x14004ed07  call    memmove
0x14004ed0c  mov     rcx, [rsi]; Lookaside
0x14004ed0f  test    rcx, rcx
0x14004ed12  jz      short loc_14004ED25
0x14004ed14  mov     rdx, rsi; Entry
0x14004ed17  call    cs:__imp_ExFreeToNPagedLookasideList
0x14004ed1e  nop     dword ptr [rax+rax+00h]
0x14004ed23  jmp     short loc_14004ED72
0x14004ed25  mov     edx, [rsi+8]; Tag
0x14004ed28  mov     rcx, rsi; P
0x14004ed2b  call    cs:__imp_ExFreePoolWithTag
0x14004ed32  nop     dword ptr [rax+rax+00h]
0x14004ed37  jmp     short loc_14004ED72
0x14004ed39  mov     edi, eax
0x14004ed3b  jmp     short loc_14004ED41
0x14004ed3d  xor     edi, edi
0x14004ed3f  mov     ecx, eax
0x14004ed41  mov     ebx, 0C000000Dh
0x14004ed46  mov     rdx, cs:WPP_GLOBAL_Control
0x14004ed4d  lea     rax, WPP_GLOBAL_Control
0x14004ed54  cmp     rdx, rax
0x14004ed57  jz      short loc_14004ED72
0x14004ed59  mov     [rsp+98h+var_68], edi
0x14004ed5d  mov     r9d, r15d
0x14004ed60  mov     [rsp+98h+var_70], ecx
0x14004ed64  mov     rcx, [rdx+18h]
0x14004ed68  mov     [rsp+98h+var_78], r8d
0x14004ed6d  call    WPP_SF_dDDD
0x14004ed72  mov     eax, ebx
0x14004ed74  add     rsp, 58h
0x14004ed78  pop     r15
0x14004ed7a  pop     r14
0x14004ed7c  pop     r13
0x14004ed7e  pop     r12
0x14004ed80  pop     rdi
0x14004ed81  pop     rsi
0x14004ed82  pop     rbp
0x14004ed83  pop     rbx
0x14004ed84  retn
```
