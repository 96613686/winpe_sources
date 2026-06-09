# WFDDeviceSendProvisionDiscoveryRequest(_WFD_DEVICE_ROLE *,_DOT11_WFD_PERFORM_PROVISION_DISCOVERY_REQUEST *,uchar)

- ea: `0x14008a69c`
- end: `0x14008ac53`
- name: `?WFDDeviceSendProvisionDiscoveryRequest@@YAHPEAU_WFD_DEVICE_ROLE@@PEAU_DOT11_WFD_PERFORM_PROVISION_DISCOVERY_REQUEST@@E@Z`
- size: `1463`
- prototype: `__int64 __fastcall(struct _WFD_DEVICE_ROLE *, struct _DOT11_WFD_PERFORM_PROVISION_DISCOVERY_REQUEST *, unsigned __int8)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x140089820`

## callees

- `0x14000d21c`
- `0x140019bbc`
- `0x14003da34`
- `0x14007b8bc`
- `0x14008a69c`
- `0x14009a7dc`
- `0x14009bcc0`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008a6e2`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008a74d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008a8d8`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008a6e2`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008a74d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008a8d8`
- `ntoskrnl!ExAllocatePool2` at `0x14008a8f0`
- `ntoskrnl!ExAllocatePool2` at `0x14008a8f0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008ab5c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008ab8d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008abe8`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008ab5c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008ab8d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008abe8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008ab6d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008aba2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008abfd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008ab6d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008aba2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008abfd`
- `NDIS!NdisReleaseRWLock` at `0x14008aa94`
- `NDIS!NdisReleaseRWLock` at `0x14008ab39`
- `NDIS!NdisReleaseRWLock` at `0x14008aa94`
- `NDIS!NdisReleaseRWLock` at `0x14008ab39`
- `NDIS!NdisAcquireRWLockRead` at `0x14008a7d8`
- `NDIS!NdisAcquireRWLockRead` at `0x14008a7d8`

## pseudocode

```c
__int64 __fastcall WFDDeviceSendProvisionDiscoveryRequest(
        struct _WFD_DEVICE_ROLE *a1,
        struct _DOT11_WFD_PERFORM_PROVISION_DISCOVERY_REQUEST *a2,
        char a3)
{
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rdi
  PNPAGED_LOOKASIDE_LIST *v5; // rax
  PNPAGED_LOOKASIDE_LIST *v6; // r14
  PNPAGED_LOOKASIDE_LIST *v7; // rax
  PNPAGED_LOOKASIDE_LIST *v8; // r15
  unsigned int CachedFrameIEs; // ebx
  struct _WFD_ROLE *v10; // rbx
  PNPAGED_LOOKASIDE_LIST *v11; // rsi
  PDEVICE_OBJECT v12; // rcx
  __int64 v13; // rdx
  unsigned int *v14; // r12
  unsigned int v15; // ecx
  unsigned int v16; // edx
  unsigned int v17; // ebx
  unsigned int v18; // eax
  _DWORD *Pool2; // rax
  __int64 v20; // rdx
  _OWORD *v21; // rcx
  PNPAGED_LOOKASIDE_LIST *v22; // rax
  __int128 v23; // xmm1
  __int64 v24; // rcx
  __int64 v25; // rbx
  size_t v26; // r8
  char *v27; // rax
  __int64 v28; // r12
  unsigned int v29; // r8d
  unsigned int v31; // [rsp+40h] [rbp-10h] BYREF
  _DWORD Size[3]; // [rsp+44h] [rbp-Ch] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+A8h] [rbp+58h] BYREF

  p_WaitListHead = &Lookaside;
  *(_QWORD *)&Size[1] = *(_QWORD *)a1;
  v31 = 0;
  *(_WORD *)&LockState.LockState = 0;
  LockState.OldIrql = 0;
  v5 = (PNPAGED_LOOKASIDE_LIST *)ExAllocateFromNPagedLookasideList(&Lookaside);
  v6 = v5;
  if ( v5 )
  {
    *v5 = &Lookaside;
    *((_DWORD *)v5 + 2) = 808679286;
    memset(v5 + 3, 0, 0x200u);
    *((_DWORD *)v6 + 4) = 2;
    *((_DWORD *)v6 + 5) = 8;
    *((_DWORD *)v6 + 6) = *((_DWORD *)a2 + 2);
    *((_DWORD *)v6 + 5) = 524296;
    *((_DWORD *)v6 + 7) |= 1u;
    *((_DWORD *)v6 + 8) = 32;
    Size[0] = 256;
    v7 = (PNPAGED_LOOKASIDE_LIST *)ExAllocateFromNPagedLookasideList(&Lookaside);
    v8 = v7;
    if ( !v7 )
    {
      CachedFrameIEs = -1073741670;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 257, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
      goto LABEL_59;
    }
    *v7 = &Lookaside;
    *((_DWORD *)v7 + 2) = 808679286;
    memset(v7 + 2, 0, 0x100u);
    if ( !(unsigned __int8)WcnGenerateWpsIe(v6 + 2, Size, v8 + 2) )
    {
      CachedFrameIEs = -1073741823;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 258, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
LABEL_53:
      if ( v8 != (PNPAGED_LOOKASIDE_LIST *)-16LL )
      {
        if ( *v8 )
          ExFreeToNPagedLookasideList(*v8, v8);
        else
          ExFreePoolWithTag(v8, *((_DWORD *)v8 + 2));
      }
LABEL_59:
      if ( *v6 )
        ExFreeToNPagedLookasideList(*v6, v6);
      else
        ExFreePoolWithTag(v6, *((_DWORD *)v6 + 2));
      return CachedFrameIEs;
    }
    v10 = *(struct _WFD_ROLE **)&Size[1];
    v11 = 0;
    NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(*(_QWORD *)&Size[1] + 32LL), &LockState, 0);
    CachedFrameIEs = WFDRoleGetCachedFrameIEs(v10, 0xAu, &v31, 0);
    if ( CachedFrameIEs )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        v13 = 259;
LABEL_46:
        WPP_SF_(v12->AttachedDevice, v13, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
        goto LABEL_47;
      }
      goto LABEL_47;
    }
    v14 = (unsigned int *)((char *)a2 + 84);
    v15 = Size[0] + 316;
    if ( (unsigned int)(Size[0] + 316) < 0x13C || (v16 = v15 + *v14, v16 < v15) || (v17 = v16 + v31, v16 + v31 < v16) )
    {
      CachedFrameIEs = -2147483643;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_DDDD(
          WPP_GLOBAL_Control->AttachedDevice,
          260,
          WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids,
          316,
          Size[0],
          *v14,
          v31);
      goto LABEL_47;
    }
    v18 = v17 + 16;
    if ( v17 >= 0xFFFFFFF0 )
    {
LABEL_44:
      CachedFrameIEs = -1073741670;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        v13 = 261;
        goto LABEL_46;
      }
LABEL_47:
      v28 = *(_QWORD *)&Size[1];
LABEL_48:
      NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v28 + 32), &LockState);
LABEL_49:
      if ( v11 )
      {
        if ( *(v11 - 2) )
          ExFreeToNPagedLookasideList(*(v11 - 2), v11 - 2);
        else
          ExFreePoolWithTag(v11 - 2, *((_DWORD *)v11 - 2));
      }
      goto LABEL_53;
    }
    if ( v18 > 0x40 )
    {
      if ( v18 > 0x100 )
      {
        if ( v18 > 0x400 )
        {
          if ( v18 > 0x800 )
          {
            p_WaitListHead = 0;
            Pool2 = (_DWORD *)ExAllocatePool2(64, v18, 808679286);
LABEL_24:
            if ( Pool2 )
            {
              v11 = (PNPAGED_LOOKASIDE_LIST *)(Pool2 + 4);
              *(_QWORD *)Pool2 = p_WaitListHead;
              Pool2[2] = 808679286;
              memset(Pool2 + 4, 0, v17);
              v20 = 2;
              v21 = (_OWORD *)((char *)a2 + 12);
              v22 = v11;
              do
              {
                *(_OWORD *)v22 = *v21;
                *((_OWORD *)v22 + 1) = v21[1];
                *((_OWORD *)v22 + 2) = v21[2];
                *((_OWORD *)v22 + 3) = v21[3];
                *((_OWORD *)v22 + 4) = v21[4];
                *((_OWORD *)v22 + 5) = v21[5];
                *((_OWORD *)v22 + 6) = v21[6];
                v23 = v21[7];
                v21 += 8;
                *((_OWORD *)v22 + 7) = v23;
                v22 += 16;
                --v20;
              }
              while ( v20 );
              *(_OWORD *)v22 = *v21;
              *((_OWORD *)v22 + 1) = v21[1];
              *((_OWORD *)v22 + 2) = v21[2];
              *(_OWORD *)((char *)v22 + 44) = *(_OWORD *)((char *)v21 + 44);
              *((_DWORD *)v11 + 17) = 76;
              v24 = 76;
              if ( *((_BYTE *)a2 + 88) )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
                {
                  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 262, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
                }
                *((_DWORD *)v11 + 17) = 316;
                v24 = 316;
              }
              v25 = Size[0];
              v26 = Size[0];
              *((_DWORD *)v11 + 18) = Size[0] + v31 + *v14;
              memmove((char *)v11 + v24, v8 + 2, v26);
              if ( *v14 )
                memmove(
                  (char *)v11 + *((unsigned int *)v11 + 17) + v25,
                  (char *)a2 + *((unsigned int *)a2 + 20) + 12,
                  *v14);
              if ( v31 )
              {
                v27 = (char *)v11 + *v14;
                v28 = *(_QWORD *)&Size[1];
                CachedFrameIEs = WFDRoleGetCachedFrameIEs(
                                   *(struct _WFD_ROLE **)&Size[1],
                                   0xAu,
                                   &v31,
                                   (unsigned __int8 *)&v27[*((unsigned int *)v11 + 17) + v25]);
                if ( CachedFrameIEs )
                {
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 263, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
                  goto LABEL_48;
                }
              }
              else
              {
                v28 = *(_QWORD *)&Size[1];
              }
              NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v28 + 32), &LockState);
              *(_DWORD *)v11 = 4981120;
              if ( *((_BYTE *)a2 + 88) )
              {
                *((_WORD *)v11 + 1) = 316;
                *((_BYTE *)v11 + 1) = 2;
              }
              v29 = *((_DWORD *)v11 + 17) + *((_DWORD *)v11 + 18);
              *((_BYTE *)v11 + 4) = a3;
              *((_DWORD *)v11 + 3) = 10000;
              CachedFrameIEs = PtRequestAdapterSync(
                                 *(struct _ADAPT **)(**(_QWORD **)a1 + 16LL),
                                 1u,
                                 0xE05010Fu,
                                 v11,
                                 v29);
              if ( CachedFrameIEs == 1076035585 )
                CachedFrameIEs = 0;
              goto LABEL_49;
            }
            goto LABEL_44;
          }
          p_WaitListHead = &stru_1400B31C0;
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
    goto LABEL_24;
  }
  CachedFrameIEs = -1073741670;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 256, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids);
  return CachedFrameIEs;
}

```

## disassembly

```asm
0x14008a69c  mov     [rsp-38h+arg_8], rbx
0x14008a6a1  mov     [rsp-38h+arg_10], r8b
0x14008a6a6  mov     [rsp-38h+arg_0], rcx
0x14008a6ab  push    rbp
0x14008a6ac  push    rsi
0x14008a6ad  push    rdi
0x14008a6ae  push    r12
0x14008a6b0  push    r13
0x14008a6b2  push    r14
0x14008a6b4  push    r15
0x14008a6b6  mov     rbp, rsp
0x14008a6b9  sub     rsp, 50h
0x14008a6bd  mov     rax, [rcx]
0x14008a6c0  lea     rdi, Lookaside
0x14008a6c7  mov     qword ptr [rbp+Size+4], rax
0x14008a6cb  mov     rcx, rdi; Lookaside
0x14008a6ce  xor     eax, eax
0x14008a6d0  mov     [rbp+var_10], 0
0x14008a6d7  mov     word ptr [rbp+LockState.LockState], ax
0x14008a6db  mov     r13, rdx
0x14008a6de  mov     [rbp+LockState.OldIrql], 0
0x14008a6e2  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14008a6e9  nop     dword ptr [rax+rax+00h]
0x14008a6ee  mov     r14, rax
0x14008a6f1  test    rax, rax
0x14008a6f4  jz      loc_14008AC0B
0x14008a6fa  mov     esi, 30337776h
0x14008a6ff  mov     [rax], rdi
0x14008a702  lea     rcx, [rax+18h]; void *
0x14008a706  mov     [rax+8], esi
0x14008a709  xor     edx, edx; Val
0x14008a70b  mov     r8d, 200h; Size
0x14008a711  call    memset
0x14008a716  mov     dword ptr [r14+10h], 2
0x14008a71e  mov     rcx, rdi; Lookaside
0x14008a721  mov     dword ptr [r14+14h], 8
0x14008a729  mov     eax, [r13+8]
0x14008a72d  mov     [r14+18h], eax
0x14008a731  mov     dword ptr [r14+14h], 80008h
0x14008a739  or      dword ptr [r14+1Ch], 1
0x14008a73e  mov     dword ptr [r14+20h], 20h ; ' '
0x14008a746  mov     dword ptr [rbp+Size], 100h
0x14008a74d  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14008a754  nop     dword ptr [rax+rax+00h]
0x14008a759  mov     r15, rax
0x14008a75c  test    rax, rax
0x14008a75f  jz      loc_14008ABB0
0x14008a765  lea     rcx, [rax+10h]; void *
0x14008a769  mov     [rax], rdi
0x14008a76c  xor     edx, edx; Val
0x14008a76e  mov     [rax+8], esi
0x14008a771  mov     r8d, 100h; Size
0x14008a777  call    memset
0x14008a77c  lea     r8, [r15+10h]
0x14008a780  lea     rdx, [rbp+Size]
0x14008a784  lea     rcx, [r14+10h]
0x14008a788  call    WcnGenerateWpsIe
0x14008a78d  test    al, al
0x14008a78f  jnz     short loc_14008A7C7
0x14008a791  mov     ebx, 0C0000001h
0x14008a796  mov     rcx, cs:WPP_GLOBAL_Control
0x14008a79d  lea     rdi, WPP_GLOBAL_Control
0x14008a7a4  cmp     rcx, rdi
0x14008a7a7  jz      loc_14008AB79
0x14008a7ad  mov     rcx, [rcx+18h]
0x14008a7b1  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x14008a7b8  mov     edx, 102h
0x14008a7bd  call    WPP_SF_
0x14008a7c2  jmp     loc_14008AB79
0x14008a7c7  mov     rbx, qword ptr [rbp+Size+4]
0x14008a7cb  lea     rdx, [rbp+LockState]; LockState
0x14008a7cf  xor     r8d, r8d; Flags
0x14008a7d2  xor     esi, esi
0x14008a7d4  mov     rcx, [rbx+20h]; Lock
0x14008a7d8  call    cs:__imp_NdisAcquireRWLockRead
0x14008a7df  nop     dword ptr [rax+rax+00h]
0x14008a7e4  xor     r9d, r9d; unsigned __int8 *
0x14008a7e7  lea     r8, [rbp+var_10]; unsigned int *
0x14008a7eb  lea     edx, [rsi+0Ah]; enum MANAGEMENT_FRAME_TYPE
0x14008a7ee  mov     rcx, rbx; struct _WFD_ROLE *
0x14008a7f1  call    ?WFDRoleGetCachedFrameIEs@@YAHPEAU_WFD_ROLE@@W4MANAGEMENT_FRAME_TYPE@@PEAKPEAE@Z; WFDRoleGetCachedFrameIEs(_WFD_ROLE *,MANAGEMENT_FRAME_TYPE,ulong *,uchar *)
0x14008a7f6  mov     ebx, eax
0x14008a7f8  test    eax, eax
0x14008a7fa  jz      short loc_14008A81D
0x14008a7fc  mov     rcx, cs:WPP_GLOBAL_Control
0x14008a803  lea     rdi, WPP_GLOBAL_Control
0x14008a80a  cmp     rcx, rdi
0x14008a80d  jz      loc_14008AB2C
0x14008a813  mov     edx, 103h
0x14008a818  jmp     loc_14008AB1C
0x14008a81d  mov     r8d, dword ptr [rbp+Size]
0x14008a821  lea     r12, [r13+54h]
0x14008a825  mov     eax, [rbp+var_10]
0x14008a828  mov     r9d, 13Ch
0x14008a82e  lea     ecx, [r8+13Ch]
0x14008a835  cmp     ecx, r9d
0x14008a838  jb      short loc_14008A84B
0x14008a83a  mov     edx, [r12]
0x14008a83e  add     edx, ecx
0x14008a840  cmp     edx, ecx
0x14008a842  jb      short loc_14008A84B
0x14008a844  lea     ebx, [rdx+rax]
0x14008a847  cmp     ebx, edx
0x14008a849  jnb     short loc_14008A892
0x14008a84b  mov     ebx, 80000005h
0x14008a850  mov     rcx, cs:WPP_GLOBAL_Control
0x14008a857  lea     rdi, WPP_GLOBAL_Control
0x14008a85e  cmp     rcx, rdi
0x14008a861  jz      loc_14008AB2C
0x14008a867  mov     rcx, [rcx+18h]
0x14008a86b  mov     edx, 104h
0x14008a870  mov     [rsp+50h+var_20], eax
0x14008a874  mov     eax, [r12]
0x14008a878  mov     [rsp+50h+var_28], eax
0x14008a87c  mov     [rsp+50h+var_30], r8d
0x14008a881  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x14008a888  call    WPP_SF_DDDD
0x14008a88d  jmp     loc_14008AB2C
0x14008a892  lea     eax, [rbx+10h]
0x14008a895  cmp     eax, 10h
0x14008a898  jb      loc_14008AAFF
0x14008a89e  mov     ecx, 40h ; '@'
0x14008a8a3  cmp     eax, ecx
0x14008a8a5  ja      short loc_14008A8B0
0x14008a8a7  lea     rdi, WPP_MAIN_CB.DeviceQueue
0x14008a8ae  jmp     short loc_14008A8D5
0x14008a8b0  cmp     eax, 100h
0x14008a8b5  ja      short loc_14008A8C0
0x14008a8b7  lea     rdi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14008a8be  jmp     short loc_14008A8D5
0x14008a8c0  cmp     eax, 400h
0x14008a8c5  jbe     short loc_14008A8D5
0x14008a8c7  cmp     eax, 800h
0x14008a8cc  ja      short loc_14008A8E6
0x14008a8ce  lea     rdi, stru_1400B31C0
0x14008a8d5  mov     rcx, rdi; Lookaside
0x14008a8d8  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14008a8df  nop     dword ptr [rax+rax+00h]
0x14008a8e4  jmp     short loc_14008A8FC
0x14008a8e6  xor     edi, edi
0x14008a8e8  mov     edx, eax
0x14008a8ea  mov     r8d, 30337776h
0x14008a8f0  call    cs:__imp_ExAllocatePool2
0x14008a8f7  nop     dword ptr [rax+rax+00h]
0x14008a8fc  test    rax, rax
0x14008a8ff  jz      loc_14008AAFF
0x14008a905  lea     rsi, [rax+10h]
0x14008a909  mov     r8d, ebx; Size
0x14008a90c  mov     rcx, rsi; void *
0x14008a90f  mov     [rax], rdi
0x14008a912  xor     edx, edx; Val
0x14008a914  mov     dword ptr [rax+8], 30337776h
0x14008a91b  call    memset
0x14008a920  mov     edx, 2
0x14008a925  lea     rcx, [r13+0Ch]
0x14008a929  mov     rax, rsi
0x14008a92c  lea     r8d, [rdx+7Eh]
0x14008a930  movups  xmm0, xmmword ptr [rcx]
0x14008a933  movups  xmmword ptr [rax], xmm0
0x14008a936  movups  xmm1, xmmword ptr [rcx+10h]
0x14008a93a  movups  xmmword ptr [rax+10h], xmm1
0x14008a93e  movups  xmm0, xmmword ptr [rcx+20h]
0x14008a942  movups  xmmword ptr [rax+20h], xmm0
0x14008a946  movups  xmm1, xmmword ptr [rcx+30h]
0x14008a94a  movups  xmmword ptr [rax+30h], xmm1
0x14008a94e  movups  xmm0, xmmword ptr [rcx+40h]
0x14008a952  movups  xmmword ptr [rax+40h], xmm0
0x14008a956  movups  xmm1, xmmword ptr [rcx+50h]
0x14008a95a  movups  xmmword ptr [rax+50h], xmm1
0x14008a95e  movups  xmm0, xmmword ptr [rcx+60h]
0x14008a962  movups  xmmword ptr [rax+60h], xmm0
0x14008a966  movups  xmm1, xmmword ptr [rcx+70h]
0x14008a96a  add     rcx, r8
0x14008a96d  movups  xmmword ptr [rax+70h], xmm1
0x14008a971  add     rax, r8
0x14008a974  sub     rdx, 1
0x14008a978  jnz     short loc_14008A930
0x14008a97a  movups  xmm0, xmmword ptr [rcx]
0x14008a97d  lea     rdi, WPP_GLOBAL_Control
0x14008a984  movups  xmmword ptr [rax], xmm0
0x14008a987  movups  xmm1, xmmword ptr [rcx+10h]
0x14008a98b  movups  xmmword ptr [rax+10h], xmm1
0x14008a98f  movups  xmm0, xmmword ptr [rcx+20h]
0x14008a993  movups  xmmword ptr [rax+20h], xmm0
0x14008a997  movups  xmm1, xmmword ptr [rcx+2Ch]
0x14008a99b  movups  xmmword ptr [rax+2Ch], xmm1
0x14008a99f  lea     eax, [rdx+4Ch]
0x14008a9a2  mov     [rsi+44h], eax
0x14008a9a5  mov     ecx, eax
0x14008a9a7  cmp     [r13+58h], dl
0x14008a9ab  jz      short loc_14008A9E7
0x14008a9ad  mov     rcx, cs:WPP_GLOBAL_Control
0x14008a9b4  cmp     rcx, rdi
0x14008a9b7  jz      short loc_14008A9DD
0x14008a9b9  cmp     byte ptr [rcx+29h], 3
0x14008a9bd  jb      short loc_14008A9DD
0x14008a9bf  test    dword ptr [rcx+2Ch], 200000h
0x14008a9c6  jz      short loc_14008A9DD
0x14008a9c8  mov     rcx, [rcx+18h]
0x14008a9cc  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x14008a9d3  mov     edx, 106h
0x14008a9d8  call    WPP_SF_
0x14008a9dd  mov     eax, 13Ch
0x14008a9e2  mov     [rsi+44h], eax
0x14008a9e5  mov     ecx, eax
0x14008a9e7  mov     edx, dword ptr [rbp+Size]
0x14008a9ea  add     rcx, rsi; void *
0x14008a9ed  mov     eax, [r12]
0x14008a9f1  mov     ebx, edx
0x14008a9f3  add     eax, [rbp+var_10]
0x14008a9f6  mov     r8d, edx; Size
0x14008a9f9  add     eax, edx
0x14008a9fb  lea     rdx, [r15+10h]; Src
0x14008a9ff  mov     [rsi+48h], eax
0x14008aa02  call    memmove
0x14008aa07  mov     eax, [r12]
0x14008aa0b  test    eax, eax
0x14008aa0d  jz      short loc_14008AA2B
0x14008aa0f  mov     edx, [r13+50h]
0x14008aa13  mov     r8d, eax; Size
0x14008aa16  mov     ecx, [rsi+44h]
0x14008aa19  add     rdx, 0Ch
0x14008aa1d  add     rcx, rsi
0x14008aa20  add     rdx, r13; Src
0x14008aa23  add     rcx, rbx; void *
0x14008aa26  call    memmove
0x14008aa2b  cmp     [rbp+var_10], 0
0x14008aa2f  jbe     short loc_14008AA87
0x14008aa31  mov     eax, [r12]
0x14008aa35  lea     r8, [rbp+var_10]; unsigned int *
0x14008aa39  mov     r9d, [rsi+44h]
0x14008aa3d  add     rax, rsi
0x14008aa40  mov     r12, qword ptr [rbp+Size+4]
0x14008aa44  add     r9, rax
0x14008aa47  add     r9, rbx; unsigned __int8 *
0x14008aa4a  mov     edx, 0Ah; enum MANAGEMENT_FRAME_TYPE
0x14008aa4f  mov     rcx, r12; struct _WFD_ROLE *
0x14008aa52  call    ?WFDRoleGetCachedFrameIEs@@YAHPEAU_WFD_ROLE@@W4MANAGEMENT_FRAME_TYPE@@PEAKPEAE@Z; WFDRoleGetCachedFrameIEs(_WFD_ROLE *,MANAGEMENT_FRAME_TYPE,ulong *,uchar *)
0x14008aa57  mov     ebx, eax
0x14008aa59  test    eax, eax
0x14008aa5b  jz      short loc_14008AA8B
0x14008aa5d  mov     rcx, cs:WPP_GLOBAL_Control
0x14008aa64  cmp     rcx, rdi
0x14008aa67  jz      loc_14008AB30
0x14008aa6d  mov     rcx, [rcx+18h]
0x14008aa71  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x14008aa78  mov     edx, 107h
0x14008aa7d  call    WPP_SF_
0x14008aa82  jmp     loc_14008AB30
0x14008aa87  mov     r12, qword ptr [rbp+Size+4]
0x14008aa8b  mov     rcx, [r12+20h]; Lock
0x14008aa90  lea     rdx, [rbp+LockState]; LockState
0x14008aa94  call    cs:__imp_NdisReleaseRWLock
0x14008aa9b  nop     dword ptr [rax+rax+00h]
0x14008aaa0  mov     dword ptr [rsi], 4C0180h
0x14008aaa6  cmp     byte ptr [r13+58h], 0
0x14008aaab  jz      short loc_14008AAB7
0x14008aaad  mov     word ptr [rsi+2], 13Ch
0x14008aab3  mov     byte ptr [rsi+1], 2
0x14008aab7  mov     al, [rbp+arg_10]
0x14008aaba  mov     r9, rsi; void *
0x14008aabd  mov     r8d, [rsi+48h]
0x14008aac1  mov     edx, 1; unsigned int
0x14008aac6  add     r8d, [rsi+44h]
0x14008aaca  mov     [rsi+4], al
0x14008aacd  mov     rax, [rbp+arg_0]
0x14008aad1  mov     dword ptr [rsi+0Ch], 2710h
0x14008aad8  mov     [rsp+50h+var_30], r8d; unsigned int
0x14008aadd  mov     r8d, 0E05010Fh; unsigned int
0x14008aae3  mov     rax, [rax]
0x14008aae6  mov     rcx, [rax]
0x14008aae9  mov     rcx, [rcx+10h]; struct _ADAPT *
0x14008aaed  call    ?PtRequestAdapterSync@@YAHPEAU_ADAPT@@KKPEAXK@Z; PtRequestAdapterSync(_ADAPT *,ulong,ulong,void *,ulong)
0x14008aaf2  mov     ebx, eax
0x14008aaf4  cmp     eax, 40230001h
0x14008aaf9  jnz     short loc_14008AB45
0x14008aafb  xor     ebx, ebx
0x14008aafd  jmp     short loc_14008AB45
0x14008aaff  mov     ebx, 0C000009Ah
0x14008ab04  mov     rcx, cs:WPP_GLOBAL_Control
0x14008ab0b  lea     rdi, WPP_GLOBAL_Control
0x14008ab12  cmp     rcx, rdi
0x14008ab15  jz      short loc_14008AB2C
0x14008ab17  mov     edx, 105h
0x14008ab1c  mov     rcx, [rcx+18h]
0x14008ab20  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x14008ab27  call    WPP_SF_
0x14008ab2c  mov     r12, qword ptr [rbp+Size+4]
0x14008ab30  mov     rcx, [r12+20h]; Lock
0x14008ab35  lea     rdx, [rbp+LockState]; LockState
0x14008ab39  call    cs:__imp_NdisReleaseRWLock
0x14008ab40  nop     dword ptr [rax+rax+00h]
0x14008ab45  test    rsi, rsi
0x14008ab48  jz      short loc_14008AB79
0x14008ab4a  lea     rcx, [rsi-10h]; P
0x14008ab4e  mov     rax, [rcx]
0x14008ab51  test    rax, rax
0x14008ab54  jz      short loc_14008AB6A
0x14008ab56  mov     rdx, rcx; Entry
0x14008ab59  mov     rcx, rax; Lookaside
  ... truncated ...
```
