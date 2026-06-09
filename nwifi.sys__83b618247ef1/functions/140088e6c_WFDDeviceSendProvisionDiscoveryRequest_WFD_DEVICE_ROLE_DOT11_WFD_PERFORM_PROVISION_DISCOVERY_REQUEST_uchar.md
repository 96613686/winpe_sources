# WFDDeviceSendProvisionDiscoveryRequest(_WFD_DEVICE_ROLE *,_DOT11_WFD_PERFORM_PROVISION_DISCOVERY_REQUEST *,uchar)

- ea: `0x140088e6c`
- end: `0x140089423`
- name: `?WFDDeviceSendProvisionDiscoveryRequest@@YAHPEAU_WFD_DEVICE_ROLE@@PEAU_DOT11_WFD_PERFORM_PROVISION_DISCOVERY_REQUEST@@E@Z`
- size: `1463`
- prototype: `__int64 __fastcall(struct _WFD_DEVICE_ROLE *, struct _DOT11_WFD_PERFORM_PROVISION_DISCOVERY_REQUEST *, char)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x140087ff0`

## callees

- `0x14000d22c`
- `0x140019bbc`
- `0x14003d814`
- `0x14007a08c`
- `0x140088e6c`
- `0x140098ffc`
- `0x14009a4c0`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140088eb2`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140088f1d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400890a8`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140088eb2`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140088f1d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400890a8`
- `ntoskrnl!ExAllocatePool2` at `0x1400890c0`
- `ntoskrnl!ExAllocatePool2` at `0x1400890c0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008932c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008935d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400893b8`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008932c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008935d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400893b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008933d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140089372`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400893cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008933d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140089372`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400893cd`
- `NDIS!NdisReleaseRWLock` at `0x140089264`
- `NDIS!NdisReleaseRWLock` at `0x140089309`
- `NDIS!NdisReleaseRWLock` at `0x140089264`
- `NDIS!NdisReleaseRWLock` at `0x140089309`
- `NDIS!NdisAcquireRWLockRead` at `0x140088fa8`
- `NDIS!NdisAcquireRWLockRead` at `0x140088fa8`

## pseudocode

```c
__int64 __fastcall WFDDeviceSendProvisionDiscoveryRequest(
        struct _WFD_DEVICE_ROLE *a1,
        struct _DOT11_WFD_PERFORM_PROVISION_DISCOVERY_REQUEST *a2,
        char a3)
{
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rdi
  int *v5; // rax
  int *v6; // r14
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
  v5 = (int *)ExAllocateFromNPagedLookasideList(&Lookaside);
  v6 = v5;
  if ( v5 )
  {
    *(_QWORD *)v5 = &Lookaside;
    v5[2] = 808679286;
    memset(v5 + 6, 0, 0x200u);
    v6[4] = 2;
    v6[5] = 8;
    v6[6] = *((_DWORD *)a2 + 2);
    v6[5] = 524296;
    v6[7] |= 1u;
    v6[8] = 32;
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
    if ( !WcnGenerateWpsIe(v6 + 4, Size, (_BYTE *)v8 + 16) )
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
      if ( *(_QWORD *)v6 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v6, v6);
      else
        ExFreePoolWithTag(v6, v6[2]);
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
            Pool2 = (_DWORD *)ExAllocatePool2(64, v18, 808679286, 316);
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
          p_WaitListHead = &stru_1400B0180;
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
0x140088e6c  mov     [rsp-38h+arg_8], rbx
0x140088e71  mov     [rsp-38h+arg_10], r8b
0x140088e76  mov     [rsp-38h+arg_0], rcx
0x140088e7b  push    rbp
0x140088e7c  push    rsi
0x140088e7d  push    rdi
0x140088e7e  push    r12
0x140088e80  push    r13
0x140088e82  push    r14
0x140088e84  push    r15
0x140088e86  mov     rbp, rsp
0x140088e89  sub     rsp, 50h
0x140088e8d  mov     rax, [rcx]
0x140088e90  lea     rdi, Lookaside
0x140088e97  mov     qword ptr [rbp+Size+4], rax
0x140088e9b  mov     rcx, rdi; Lookaside
0x140088e9e  xor     eax, eax
0x140088ea0  mov     [rbp+var_10], 0
0x140088ea7  mov     word ptr [rbp+LockState.LockState], ax
0x140088eab  mov     r13, rdx
0x140088eae  mov     [rbp+LockState.OldIrql], 0
0x140088eb2  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140088eb9  nop     dword ptr [rax+rax+00h]
0x140088ebe  mov     r14, rax
0x140088ec1  test    rax, rax
0x140088ec4  jz      loc_1400893DB
0x140088eca  mov     esi, 30337776h
0x140088ecf  mov     [rax], rdi
0x140088ed2  lea     rcx, [rax+18h]; void *
0x140088ed6  mov     [rax+8], esi
0x140088ed9  xor     edx, edx; Val
0x140088edb  mov     r8d, 200h; Size
0x140088ee1  call    memset
0x140088ee6  mov     dword ptr [r14+10h], 2
0x140088eee  mov     rcx, rdi; Lookaside
0x140088ef1  mov     dword ptr [r14+14h], 8
0x140088ef9  mov     eax, [r13+8]
0x140088efd  mov     [r14+18h], eax
0x140088f01  mov     dword ptr [r14+14h], 80008h
0x140088f09  or      dword ptr [r14+1Ch], 1
0x140088f0e  mov     dword ptr [r14+20h], 20h ; ' '
0x140088f16  mov     dword ptr [rbp+Size], 100h
0x140088f1d  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140088f24  nop     dword ptr [rax+rax+00h]
0x140088f29  mov     r15, rax
0x140088f2c  test    rax, rax
0x140088f2f  jz      loc_140089380
0x140088f35  lea     rcx, [rax+10h]; void *
0x140088f39  mov     [rax], rdi
0x140088f3c  xor     edx, edx; Val
0x140088f3e  mov     [rax+8], esi
0x140088f41  mov     r8d, 100h; Size
0x140088f47  call    memset
0x140088f4c  lea     r8, [r15+10h]
0x140088f50  lea     rdx, [rbp+Size]
0x140088f54  lea     rcx, [r14+10h]
0x140088f58  call    WcnGenerateWpsIe
0x140088f5d  test    al, al
0x140088f5f  jnz     short loc_140088F97
0x140088f61  mov     ebx, 0C0000001h
0x140088f66  mov     rcx, cs:WPP_GLOBAL_Control
0x140088f6d  lea     rdi, WPP_GLOBAL_Control
0x140088f74  cmp     rcx, rdi
0x140088f77  jz      loc_140089349
0x140088f7d  mov     rcx, [rcx+18h]
0x140088f81  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140088f88  mov     edx, 102h
0x140088f8d  call    WPP_SF_
0x140088f92  jmp     loc_140089349
0x140088f97  mov     rbx, qword ptr [rbp+Size+4]
0x140088f9b  lea     rdx, [rbp+LockState]; LockState
0x140088f9f  xor     r8d, r8d; Flags
0x140088fa2  xor     esi, esi
0x140088fa4  mov     rcx, [rbx+20h]; Lock
0x140088fa8  call    cs:__imp_NdisAcquireRWLockRead
0x140088faf  nop     dword ptr [rax+rax+00h]
0x140088fb4  xor     r9d, r9d; unsigned __int8 *
0x140088fb7  lea     r8, [rbp+var_10]; unsigned int *
0x140088fbb  lea     edx, [rsi+0Ah]; enum MANAGEMENT_FRAME_TYPE
0x140088fbe  mov     rcx, rbx; struct _WFD_ROLE *
0x140088fc1  call    ?WFDRoleGetCachedFrameIEs@@YAHPEAU_WFD_ROLE@@W4MANAGEMENT_FRAME_TYPE@@PEAKPEAE@Z; WFDRoleGetCachedFrameIEs(_WFD_ROLE *,MANAGEMENT_FRAME_TYPE,ulong *,uchar *)
0x140088fc6  mov     ebx, eax
0x140088fc8  test    eax, eax
0x140088fca  jz      short loc_140088FED
0x140088fcc  mov     rcx, cs:WPP_GLOBAL_Control
0x140088fd3  lea     rdi, WPP_GLOBAL_Control
0x140088fda  cmp     rcx, rdi
0x140088fdd  jz      loc_1400892FC
0x140088fe3  mov     edx, 103h
0x140088fe8  jmp     loc_1400892EC
0x140088fed  mov     r8d, dword ptr [rbp+Size]
0x140088ff1  lea     r12, [r13+54h]
0x140088ff5  mov     eax, [rbp+var_10]
0x140088ff8  mov     r9d, 13Ch
0x140088ffe  lea     ecx, [r8+13Ch]
0x140089005  cmp     ecx, r9d
0x140089008  jb      short loc_14008901B
0x14008900a  mov     edx, [r12]
0x14008900e  add     edx, ecx
0x140089010  cmp     edx, ecx
0x140089012  jb      short loc_14008901B
0x140089014  lea     ebx, [rdx+rax]
0x140089017  cmp     ebx, edx
0x140089019  jnb     short loc_140089062
0x14008901b  mov     ebx, 80000005h
0x140089020  mov     rcx, cs:WPP_GLOBAL_Control
0x140089027  lea     rdi, WPP_GLOBAL_Control
0x14008902e  cmp     rcx, rdi
0x140089031  jz      loc_1400892FC
0x140089037  mov     rcx, [rcx+18h]
0x14008903b  mov     edx, 104h
0x140089040  mov     [rsp+50h+var_20], eax
0x140089044  mov     eax, [r12]
0x140089048  mov     [rsp+50h+var_28], eax
0x14008904c  mov     [rsp+50h+var_30], r8d
0x140089051  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140089058  call    WPP_SF_DDDD
0x14008905d  jmp     loc_1400892FC
0x140089062  lea     eax, [rbx+10h]
0x140089065  cmp     eax, 10h
0x140089068  jb      loc_1400892CF
0x14008906e  mov     ecx, 40h ; '@'
0x140089073  cmp     eax, ecx
0x140089075  ja      short loc_140089080
0x140089077  lea     rdi, WPP_MAIN_CB.DeviceQueue
0x14008907e  jmp     short loc_1400890A5
0x140089080  cmp     eax, 100h
0x140089085  ja      short loc_140089090
0x140089087  lea     rdi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14008908e  jmp     short loc_1400890A5
0x140089090  cmp     eax, 400h
0x140089095  jbe     short loc_1400890A5
0x140089097  cmp     eax, 800h
0x14008909c  ja      short loc_1400890B6
0x14008909e  lea     rdi, stru_1400B0180
0x1400890a5  mov     rcx, rdi; Lookaside
0x1400890a8  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400890af  nop     dword ptr [rax+rax+00h]
0x1400890b4  jmp     short loc_1400890CC
0x1400890b6  xor     edi, edi
0x1400890b8  mov     edx, eax
0x1400890ba  mov     r8d, 30337776h
0x1400890c0  call    cs:__imp_ExAllocatePool2
0x1400890c7  nop     dword ptr [rax+rax+00h]
0x1400890cc  test    rax, rax
0x1400890cf  jz      loc_1400892CF
0x1400890d5  lea     rsi, [rax+10h]
0x1400890d9  mov     r8d, ebx; Size
0x1400890dc  mov     rcx, rsi; void *
0x1400890df  mov     [rax], rdi
0x1400890e2  xor     edx, edx; Val
0x1400890e4  mov     dword ptr [rax+8], 30337776h
0x1400890eb  call    memset
0x1400890f0  mov     edx, 2
0x1400890f5  lea     rcx, [r13+0Ch]
0x1400890f9  mov     rax, rsi
0x1400890fc  lea     r8d, [rdx+7Eh]
0x140089100  movups  xmm0, xmmword ptr [rcx]
0x140089103  movups  xmmword ptr [rax], xmm0
0x140089106  movups  xmm1, xmmword ptr [rcx+10h]
0x14008910a  movups  xmmword ptr [rax+10h], xmm1
0x14008910e  movups  xmm0, xmmword ptr [rcx+20h]
0x140089112  movups  xmmword ptr [rax+20h], xmm0
0x140089116  movups  xmm1, xmmword ptr [rcx+30h]
0x14008911a  movups  xmmword ptr [rax+30h], xmm1
0x14008911e  movups  xmm0, xmmword ptr [rcx+40h]
0x140089122  movups  xmmword ptr [rax+40h], xmm0
0x140089126  movups  xmm1, xmmword ptr [rcx+50h]
0x14008912a  movups  xmmword ptr [rax+50h], xmm1
0x14008912e  movups  xmm0, xmmword ptr [rcx+60h]
0x140089132  movups  xmmword ptr [rax+60h], xmm0
0x140089136  movups  xmm1, xmmword ptr [rcx+70h]
0x14008913a  add     rcx, r8
0x14008913d  movups  xmmword ptr [rax+70h], xmm1
0x140089141  add     rax, r8
0x140089144  sub     rdx, 1
0x140089148  jnz     short loc_140089100
0x14008914a  movups  xmm0, xmmword ptr [rcx]
0x14008914d  lea     rdi, WPP_GLOBAL_Control
0x140089154  movups  xmmword ptr [rax], xmm0
0x140089157  movups  xmm1, xmmword ptr [rcx+10h]
0x14008915b  movups  xmmword ptr [rax+10h], xmm1
0x14008915f  movups  xmm0, xmmword ptr [rcx+20h]
0x140089163  movups  xmmword ptr [rax+20h], xmm0
0x140089167  movups  xmm1, xmmword ptr [rcx+2Ch]
0x14008916b  movups  xmmword ptr [rax+2Ch], xmm1
0x14008916f  lea     eax, [rdx+4Ch]
0x140089172  mov     [rsi+44h], eax
0x140089175  mov     ecx, eax
0x140089177  cmp     [r13+58h], dl
0x14008917b  jz      short loc_1400891B7
0x14008917d  mov     rcx, cs:WPP_GLOBAL_Control
0x140089184  cmp     rcx, rdi
0x140089187  jz      short loc_1400891AD
0x140089189  cmp     byte ptr [rcx+29h], 3
0x14008918d  jb      short loc_1400891AD
0x14008918f  test    dword ptr [rcx+2Ch], 200000h
0x140089196  jz      short loc_1400891AD
0x140089198  mov     rcx, [rcx+18h]
0x14008919c  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x1400891a3  mov     edx, 106h
0x1400891a8  call    WPP_SF_
0x1400891ad  mov     eax, 13Ch
0x1400891b2  mov     [rsi+44h], eax
0x1400891b5  mov     ecx, eax
0x1400891b7  mov     edx, dword ptr [rbp+Size]
0x1400891ba  add     rcx, rsi; void *
0x1400891bd  mov     eax, [r12]
0x1400891c1  mov     ebx, edx
0x1400891c3  add     eax, [rbp+var_10]
0x1400891c6  mov     r8d, edx; Size
0x1400891c9  add     eax, edx
0x1400891cb  lea     rdx, [r15+10h]; Src
0x1400891cf  mov     [rsi+48h], eax
0x1400891d2  call    memmove
0x1400891d7  mov     eax, [r12]
0x1400891db  test    eax, eax
0x1400891dd  jz      short loc_1400891FB
0x1400891df  mov     edx, [r13+50h]
0x1400891e3  mov     r8d, eax; Size
0x1400891e6  mov     ecx, [rsi+44h]
0x1400891e9  add     rdx, 0Ch
0x1400891ed  add     rcx, rsi
0x1400891f0  add     rdx, r13; Src
0x1400891f3  add     rcx, rbx; void *
0x1400891f6  call    memmove
0x1400891fb  cmp     [rbp+var_10], 0
0x1400891ff  jbe     short loc_140089257
0x140089201  mov     eax, [r12]
0x140089205  lea     r8, [rbp+var_10]; unsigned int *
0x140089209  mov     r9d, [rsi+44h]
0x14008920d  add     rax, rsi
0x140089210  mov     r12, qword ptr [rbp+Size+4]
0x140089214  add     r9, rax
0x140089217  add     r9, rbx; unsigned __int8 *
0x14008921a  mov     edx, 0Ah; enum MANAGEMENT_FRAME_TYPE
0x14008921f  mov     rcx, r12; struct _WFD_ROLE *
0x140089222  call    ?WFDRoleGetCachedFrameIEs@@YAHPEAU_WFD_ROLE@@W4MANAGEMENT_FRAME_TYPE@@PEAKPEAE@Z; WFDRoleGetCachedFrameIEs(_WFD_ROLE *,MANAGEMENT_FRAME_TYPE,ulong *,uchar *)
0x140089227  mov     ebx, eax
0x140089229  test    eax, eax
0x14008922b  jz      short loc_14008925B
0x14008922d  mov     rcx, cs:WPP_GLOBAL_Control
0x140089234  cmp     rcx, rdi
0x140089237  jz      loc_140089300
0x14008923d  mov     rcx, [rcx+18h]
0x140089241  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x140089248  mov     edx, 107h
0x14008924d  call    WPP_SF_
0x140089252  jmp     loc_140089300
0x140089257  mov     r12, qword ptr [rbp+Size+4]
0x14008925b  mov     rcx, [r12+20h]; Lock
0x140089260  lea     rdx, [rbp+LockState]; LockState
0x140089264  call    cs:__imp_NdisReleaseRWLock
0x14008926b  nop     dword ptr [rax+rax+00h]
0x140089270  mov     dword ptr [rsi], 4C0180h
0x140089276  cmp     byte ptr [r13+58h], 0
0x14008927b  jz      short loc_140089287
0x14008927d  mov     word ptr [rsi+2], 13Ch
0x140089283  mov     byte ptr [rsi+1], 2
0x140089287  mov     al, [rbp+arg_10]
0x14008928a  mov     r9, rsi; void *
0x14008928d  mov     r8d, [rsi+48h]
0x140089291  mov     edx, 1; unsigned int
0x140089296  add     r8d, [rsi+44h]
0x14008929a  mov     [rsi+4], al
0x14008929d  mov     rax, [rbp+arg_0]
0x1400892a1  mov     dword ptr [rsi+0Ch], 2710h
0x1400892a8  mov     [rsp+50h+var_30], r8d; unsigned int
0x1400892ad  mov     r8d, 0E05010Fh; unsigned int
0x1400892b3  mov     rax, [rax]
0x1400892b6  mov     rcx, [rax]
0x1400892b9  mov     rcx, [rcx+10h]; struct _ADAPT *
0x1400892bd  call    ?PtRequestAdapterSync@@YAHPEAU_ADAPT@@KKPEAXK@Z; PtRequestAdapterSync(_ADAPT *,ulong,ulong,void *,ulong)
0x1400892c2  mov     ebx, eax
0x1400892c4  cmp     eax, 40230001h
0x1400892c9  jnz     short loc_140089315
0x1400892cb  xor     ebx, ebx
0x1400892cd  jmp     short loc_140089315
0x1400892cf  mov     ebx, 0C000009Ah
0x1400892d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400892db  lea     rdi, WPP_GLOBAL_Control
0x1400892e2  cmp     rcx, rdi
0x1400892e5  jz      short loc_1400892FC
0x1400892e7  mov     edx, 105h
0x1400892ec  mov     rcx, [rcx+18h]
0x1400892f0  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x1400892f7  call    WPP_SF_
0x1400892fc  mov     r12, qword ptr [rbp+Size+4]
0x140089300  mov     rcx, [r12+20h]; Lock
0x140089305  lea     rdx, [rbp+LockState]; LockState
0x140089309  call    cs:__imp_NdisReleaseRWLock
0x140089310  nop     dword ptr [rax+rax+00h]
0x140089315  test    rsi, rsi
0x140089318  jz      short loc_140089349
0x14008931a  lea     rcx, [rsi-10h]; P
0x14008931e  mov     rax, [rcx]
0x140089321  test    rax, rax
0x140089324  jz      short loc_14008933A
0x140089326  mov     rdx, rcx; Entry
0x140089329  mov     rcx, rax; Lookaside
  ... truncated ...
```
