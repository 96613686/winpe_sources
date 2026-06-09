# RegisterTPIWithFsm

- ea: `0x14000f58c`
- end: `0x14000f9bc`
- name: `RegisterTPIWithFsm`
- size: `1072`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400034d0`

## callees

- `0x140002bd8`
- `0x140002c08`
- `0x14000f420`
- `0x14000f58c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000f5ed`
- `ntoskrnl!ExAllocatePool2` at `0x14000f5ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f8f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f8f4`
- `ntoskrnl!IoAllocateWorkItem` at `0x14000f637`
- `ntoskrnl!IoAllocateWorkItem` at `0x14000f637`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14000f94a`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14000f94a`
- `ntoskrnl!IoFreeWorkItem` at `0x14000f8dc`
- `ntoskrnl!IoFreeWorkItem` at `0x14000f8dc`
- `ntoskrnl!KeInitializeEvent` at `0x14000f6bb`
- `ntoskrnl!KeInitializeEvent` at `0x14000f6bb`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000f69f`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000f961`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000f69f`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000f961`
- `NDIS!NdisGetVersion` at `0x14000f914`
- `NDIS!NdisGetVersion` at `0x14000f914`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x14000f847`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x14000f895`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x14000f847`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x14000f895`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14000f736`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14000f79a`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14000f736`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14000f79a`

## pseudocode

```c
__int64 __fastcall RegisterTPIWithFsm(__int128 *a1, __int128 *a2, struct _DEVICE_OBJECT *a3, _QWORD *a4)
{
  NTSTATUS v8; // edi
  _OWORD *v9; // rax
  __int128 v10; // xmm0
  __int128 v11; // xmm1
  PIO_WORKITEM WorkItem; // rax
  char *v13; // rbx
  bool v14; // zf
  char *v15; // rcx
  __int128 v16; // xmm0
  PDEVICE_OBJECT v17; // rcx
  __int64 v18; // rdx
  PDEVICE_OBJECT v19; // rcx
  __int64 v20; // rdx
  void *v21; // rcx
  void *v22; // rcx
  struct _NPAGED_LOOKASIDE_LIST *v23; // rbx
  _BYTE *v24; // rcx
  _QWORD *v25; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x84) == 0x84 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 134, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids);
  SstpFsmGlobalInfo = (PVOID)ExAllocatePool2(64, 448, 1768384083);
  if ( SstpFsmGlobalInfo )
  {
    _InterlockedAdd((volatile signed __int32 *)&WPP_MAIN_CB.DeviceExtension, 0);
    v9 = SstpFsmGlobalInfo;
    v10 = *a1;
    v11 = a1[1];
    *((_QWORD *)SstpFsmGlobalInfo + 52) = a3;
    v9[6] = v10;
    v9[7] = v11;
    WorkItem = IoAllocateWorkItem(a3);
    v13 = (char *)SstpFsmGlobalInfo;
    *((_QWORD *)SstpFsmGlobalInfo + 53) = WorkItem;
    if ( !WorkItem )
    {
      v8 = -1073741670;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 135, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids);
      }
      goto LABEL_42;
    }
    v8 = 0;
    KeInitializeSpinLock((PKSPIN_LOCK)v13 + 3);
    v13[64] = 1;
    *((_DWORD *)v13 + 8) = 0;
    KeInitializeEvent((PRKEVENT)(v13 + 40), NotificationEvent, 1u);
    v14 = (*((_BYTE *)a2 + 8) & 1) == 0;
    v15 = (char *)SstpFsmGlobalInfo;
    v16 = *a2;
    a4[3] = FsmTpiControlFrameSendComplete;
    a4[2] = FsmTpiDisconnectCall;
    *a4 = FsmTpiNewCall;
    a4[1] = FsmTpiProcessControlFrame;
    a4[4] = FsmTpiSetDataReceivedStatus;
    a4[5] = &FsmTpiSetCryptoBindingKeys;
    *(_OWORD *)(v15 + 4) = v16;
    if ( !v14 )
    {
      v8 = BCryptOpenAlgorithmProvider((BCRYPT_ALG_HANDLE *)v15 + 32, L"SHA1", 0, 8u);
      if ( v8 < 0 )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
          || !BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          goto LABEL_41;
        }
        v18 = 136;
LABEL_40:
        WPP_SF_d(v17->AttachedDevice, v18, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids);
LABEL_41:
        IoFreeWorkItem(*((PIO_WORKITEM *)SstpFsmGlobalInfo + 53));
LABEL_42:
        ExFreePoolWithTag(SstpFsmGlobalInfo, 0x69676653u);
        SstpFsmGlobalInfo = 0;
        goto LABEL_44;
      }
    }
    if ( (*((_BYTE *)a2 + 8) & 2) != 0
      && (v8 = BCryptOpenAlgorithmProvider((BCRYPT_ALG_HANDLE *)SstpFsmGlobalInfo + 33, L"SHA256", 0, 8u), v8 < 0) )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        goto LABEL_35;
      }
      v20 = 137;
    }
    else
    {
      if ( !*((_BYTE *)a2 + 8) || (v8 = FipsInit((PFILE_OBJECT *)SstpFsmGlobalInfo + 34), v8 >= 0) )
      {
        v23 = (struct _NPAGED_LOOKASIDE_LIST *)SstpFsmGlobalInfo;
        NdisGetVersion();
        ExInitializeNPagedLookasideList(v23 + 1, 0, 0, 0x200u, 0x1018u, 0x666C6353u, 0);
        KeInitializeSpinLock((PKSPIN_LOCK)SstpFsmGlobalInfo + 9);
        v24 = SstpFsmGlobalInfo;
        v25 = (char *)SstpFsmGlobalInfo + 80;
        *((_QWORD *)SstpFsmGlobalInfo + 11) = (char *)SstpFsmGlobalInfo + 80;
        *v25 = v25;
        *v24 = 1;
        goto LABEL_44;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 138, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids);
      }
      v21 = (void *)*((_QWORD *)SstpFsmGlobalInfo + 33);
      if ( !v21 )
        goto LABEL_35;
      BCryptCloseAlgorithmProvider(v21, 0);
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_35;
      }
      v20 = 139;
    }
    WPP_SF_d(v19->AttachedDevice, v20, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids);
LABEL_35:
    v22 = (void *)*((_QWORD *)SstpFsmGlobalInfo + 32);
    if ( !v22 )
      goto LABEL_41;
    BCryptCloseAlgorithmProvider(v22, 0);
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_41;
    }
    v18 = 140;
    goto LABEL_40;
  }
  v8 = -1073741670;
LABEL_44:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x84) == 0x84 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 141, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14000f58c  push    rbx
0x14000f58e  push    rbp
0x14000f58f  push    rdi
0x14000f590  push    r12
0x14000f592  push    r13
0x14000f594  push    r14
0x14000f596  sub     rsp, 48h
0x14000f59a  mov     r14, r9
0x14000f59d  mov     rbx, r8
0x14000f5a0  mov     rbp, rdx
0x14000f5a3  mov     rdi, rcx
0x14000f5a6  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f5ad  lea     r12, WPP_GLOBAL_Control
0x14000f5b4  lea     r13, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x14000f5bb  cmp     rcx, r12
0x14000f5be  jz      short loc_14000F5DD
0x14000f5c0  mov     eax, [rcx+2Ch]
0x14000f5c3  and     eax, 84h
0x14000f5c8  cmp     al, 84h
0x14000f5ca  jnz     short loc_14000F5DD
0x14000f5cc  mov     rcx, [rcx+18h]
0x14000f5d0  mov     edx, 86h
0x14000f5d5  mov     r8, r13
0x14000f5d8  call    WPP_SF_
0x14000f5dd  mov     edx, 1C0h
0x14000f5e2  mov     ecx, 40h ; '@'
0x14000f5e7  mov     r8d, 69676653h
0x14000f5ed  call    cs:__imp_ExAllocatePool2
0x14000f5f4  nop     dword ptr [rax+rax+00h]
0x14000f5f9  mov     cs:SstpFsmGlobalInfo, rax
0x14000f600  test    rax, rax
0x14000f603  jnz     short loc_14000F60F
0x14000f605  mov     edi, 0C000009Ah
0x14000f60a  jmp     loc_14000F982
0x14000f60f  lock add dword ptr cs:WPP_MAIN_CB.DeviceExtension, 0
0x14000f617  mov     rax, cs:SstpFsmGlobalInfo
0x14000f61e  mov     rcx, rbx; DeviceObject
0x14000f621  movups  xmm0, xmmword ptr [rdi]
0x14000f624  movups  xmm1, xmmword ptr [rdi+10h]
0x14000f628  mov     [rax+1A0h], rbx
0x14000f62f  movups  xmmword ptr [rax+60h], xmm0
0x14000f633  movups  xmmword ptr [rax+70h], xmm1
0x14000f637  call    cs:__imp_IoAllocateWorkItem
0x14000f63e  nop     dword ptr [rax+rax+00h]
0x14000f643  mov     rbx, cs:SstpFsmGlobalInfo
0x14000f64a  mov     [rbx+1A8h], rax
0x14000f651  test    rax, rax
0x14000f654  jnz     short loc_14000F699
0x14000f656  mov     edi, 0C000009Ah
0x14000f65b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f662  cmp     rcx, r12
0x14000f665  jz      loc_14000F8E8
0x14000f66b  mov     eax, [rcx+2Ch]
0x14000f66e  test    al, 4
0x14000f670  jz      loc_14000F8E8
0x14000f676  cmp     byte ptr [rcx+29h], 1
0x14000f67a  jb      loc_14000F8E8
0x14000f680  mov     rcx, [rcx+18h]
0x14000f684  mov     edx, 87h
0x14000f689  mov     r9d, edi
0x14000f68c  mov     r8, r13
0x14000f68f  call    WPP_SF_d
0x14000f694  jmp     loc_14000F8E8
0x14000f699  lea     rcx, [rbx+18h]; SpinLock
0x14000f69d  xor     edi, edi
0x14000f69f  call    cs:__imp_KeInitializeSpinLock
0x14000f6a6  nop     dword ptr [rax+rax+00h]
0x14000f6ab  lea     rcx, [rbx+28h]; Event
0x14000f6af  mov     byte ptr [rbx+40h], 1
0x14000f6b3  mov     r8b, 1; State
0x14000f6b6  mov     [rbx+20h], edi
0x14000f6b9  xor     edx, edx; Type
0x14000f6bb  call    cs:__imp_KeInitializeEvent
0x14000f6c2  nop     dword ptr [rax+rax+00h]
0x14000f6c7  test    byte ptr [rbp+8], 1
0x14000f6cb  lea     rax, FsmTpiControlFrameSendComplete
0x14000f6d2  mov     rcx, cs:SstpFsmGlobalInfo
0x14000f6d9  movups  xmm0, xmmword ptr [rbp+0]
0x14000f6dd  mov     [r14+18h], rax
0x14000f6e1  lea     rax, FsmTpiDisconnectCall
0x14000f6e8  mov     [r14+10h], rax
0x14000f6ec  lea     rax, FsmTpiNewCall
0x14000f6f3  mov     [r14], rax
0x14000f6f6  lea     rax, FsmTpiProcessControlFrame
0x14000f6fd  mov     [r14+8], rax
0x14000f701  lea     rax, FsmTpiSetDataReceivedStatus
0x14000f708  mov     [r14+20h], rax
0x14000f70c  lea     rax, FsmTpiSetCryptoBindingKeys
0x14000f713  mov     [r14+28h], rax
0x14000f717  lea     r14d, [rdi+8]
0x14000f71b  movdqu  xmmword ptr [rcx+4], xmm0
0x14000f720  jz      short loc_14000F778
0x14000f722  add     rcx, 100h; phAlgorithm
0x14000f729  lea     rdx, pszAlgId; "SHA1"
0x14000f730  mov     r9d, r14d; dwFlags
0x14000f733  xor     r8d, r8d; pszImplementation
0x14000f736  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14000f73d  nop     dword ptr [rax+rax+00h]
0x14000f742  mov     edi, eax
0x14000f744  test    eax, eax
0x14000f746  jns     short loc_14000F778
0x14000f748  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f74f  cmp     rcx, r12
0x14000f752  jz      loc_14000F8CE
0x14000f758  mov     edx, [rcx+2Ch]
0x14000f75b  test    dl, 4
0x14000f75e  jz      loc_14000F8CE
0x14000f764  cmp     byte ptr [rcx+29h], 1
0x14000f768  jb      loc_14000F8CE
0x14000f76e  mov     edx, 88h
0x14000f773  jmp     loc_14000F8BF
0x14000f778  mov     bl, 2
0x14000f77a  test    [rbp+8], bl
0x14000f77d  jz      short loc_14000F7DE
0x14000f77f  mov     rcx, cs:SstpFsmGlobalInfo
0x14000f786  lea     rdx, aSha256; "SHA256"
0x14000f78d  add     rcx, 108h; phAlgorithm
0x14000f794  mov     r9d, r14d; dwFlags
0x14000f797  xor     r8d, r8d; pszImplementation
0x14000f79a  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14000f7a1  nop     dword ptr [rax+rax+00h]
0x14000f7a6  mov     edi, eax
0x14000f7a8  test    eax, eax
0x14000f7aa  jns     short loc_14000F7DE
0x14000f7ac  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f7b3  cmp     rcx, r12
0x14000f7b6  jz      loc_14000F880
0x14000f7bc  mov     eax, [rcx+2Ch]
0x14000f7bf  test    al, 4
0x14000f7c1  jz      loc_14000F880
0x14000f7c7  cmp     byte ptr [rcx+29h], 1
0x14000f7cb  jb      loc_14000F880
0x14000f7d1  mov     edx, 89h
0x14000f7d6  mov     r9d, edi
0x14000f7d9  jmp     loc_14000F874
0x14000f7de  cmp     byte ptr [rbp+8], 0
0x14000f7e2  jz      loc_14000F90D
0x14000f7e8  mov     rcx, cs:SstpFsmGlobalInfo
0x14000f7ef  add     rcx, 110h; FileObject
0x14000f7f6  call    FipsInit
0x14000f7fb  mov     edi, eax
0x14000f7fd  test    eax, eax
0x14000f7ff  jns     loc_14000F90D
0x14000f805  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f80c  cmp     rcx, r12
0x14000f80f  jz      short loc_14000F832
0x14000f811  mov     eax, [rcx+2Ch]
0x14000f814  test    al, 4
0x14000f816  jz      short loc_14000F832
0x14000f818  cmp     byte ptr [rcx+29h], 1
0x14000f81c  jb      short loc_14000F832
0x14000f81e  mov     rcx, [rcx+18h]
0x14000f822  mov     edx, 8Ah
0x14000f827  mov     r9d, edi
0x14000f82a  mov     r8, r13
0x14000f82d  call    WPP_SF_d
0x14000f832  mov     rax, cs:SstpFsmGlobalInfo
0x14000f839  mov     rcx, [rax+108h]; hAlgorithm
0x14000f840  test    rcx, rcx
0x14000f843  jz      short loc_14000F880
0x14000f845  xor     edx, edx; dwFlags
0x14000f847  call    cs:__imp_BCryptCloseAlgorithmProvider
0x14000f84e  nop     dword ptr [rax+rax+00h]
0x14000f853  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f85a  cmp     rcx, r12
0x14000f85d  jz      short loc_14000F880
0x14000f85f  mov     edx, [rcx+2Ch]
0x14000f862  test    dl, 4
0x14000f865  jz      short loc_14000F880
0x14000f867  cmp     [rcx+29h], bl
0x14000f86a  jb      short loc_14000F880
0x14000f86c  mov     edx, 8Bh
0x14000f871  mov     r9d, eax
0x14000f874  mov     rcx, [rcx+18h]
0x14000f878  mov     r8, r13
0x14000f87b  call    WPP_SF_d
0x14000f880  mov     rax, cs:SstpFsmGlobalInfo
0x14000f887  mov     rcx, [rax+100h]; hAlgorithm
0x14000f88e  test    rcx, rcx
0x14000f891  jz      short loc_14000F8CE
0x14000f893  xor     edx, edx; dwFlags
0x14000f895  call    cs:__imp_BCryptCloseAlgorithmProvider
0x14000f89c  nop     dword ptr [rax+rax+00h]
0x14000f8a1  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f8a8  cmp     rcx, r12
0x14000f8ab  jz      short loc_14000F8CE
0x14000f8ad  mov     edx, [rcx+2Ch]
0x14000f8b0  test    dl, 4
0x14000f8b3  jz      short loc_14000F8CE
0x14000f8b5  cmp     [rcx+29h], bl
0x14000f8b8  jb      short loc_14000F8CE
0x14000f8ba  mov     edx, 8Ch
0x14000f8bf  mov     rcx, [rcx+18h]
0x14000f8c3  mov     r9d, eax
0x14000f8c6  mov     r8, r13
0x14000f8c9  call    WPP_SF_d
0x14000f8ce  mov     rcx, cs:SstpFsmGlobalInfo
0x14000f8d5  mov     rcx, [rcx+1A8h]; IoWorkItem
0x14000f8dc  call    cs:__imp_IoFreeWorkItem
0x14000f8e3  nop     dword ptr [rax+rax+00h]
0x14000f8e8  mov     rcx, cs:SstpFsmGlobalInfo; P
0x14000f8ef  mov     edx, 69676653h; Tag
0x14000f8f4  call    cs:__imp_ExFreePoolWithTag
0x14000f8fb  nop     dword ptr [rax+rax+00h]
0x14000f900  mov     cs:SstpFsmGlobalInfo, 0
0x14000f90b  jmp     short loc_14000F982
0x14000f90d  mov     rbx, cs:SstpFsmGlobalInfo
0x14000f914  call    cs:__imp_NdisGetVersion
0x14000f91b  nop     dword ptr [rax+rax+00h]
0x14000f920  xor     eax, eax
0x14000f922  lea     rcx, [rbx+80h]; Lookaside
0x14000f929  mov     [rsp+78h+Depth], ax; Depth
0x14000f92e  mov     r9d, 200h; Flags
0x14000f934  mov     [rsp+78h+Tag], 666C6353h; Tag
0x14000f93c  xor     r8d, r8d; Free
0x14000f93f  xor     edx, edx; Allocate
0x14000f941  mov     [rsp+78h+Size], 1018h; Size
0x14000f94a  call    cs:__imp_ExInitializeNPagedLookasideList
0x14000f951  nop     dword ptr [rax+rax+00h]
0x14000f956  mov     rcx, cs:SstpFsmGlobalInfo
0x14000f95d  add     rcx, 48h ; 'H'; SpinLock
0x14000f961  call    cs:__imp_KeInitializeSpinLock
0x14000f968  nop     dword ptr [rax+rax+00h]
0x14000f96d  mov     rcx, cs:SstpFsmGlobalInfo
0x14000f974  lea     rax, [rcx+50h]
0x14000f978  mov     [rax+8], rax
0x14000f97c  mov     [rax], rax
0x14000f97f  mov     byte ptr [rcx], 1
0x14000f982  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f989  cmp     rcx, r12
0x14000f98c  jz      short loc_14000F9AB
0x14000f98e  mov     eax, [rcx+2Ch]
0x14000f991  and     eax, 84h
0x14000f996  cmp     al, 84h
0x14000f998  jnz     short loc_14000F9AB
0x14000f99a  mov     rcx, [rcx+18h]
0x14000f99e  mov     edx, 8Dh
0x14000f9a3  mov     r8, r13
0x14000f9a6  call    WPP_SF_
0x14000f9ab  mov     eax, edi
0x14000f9ad  add     rsp, 48h
0x14000f9b1  pop     r14
0x14000f9b3  pop     r13
0x14000f9b5  pop     r12
0x14000f9b7  pop     rdi
0x14000f9b8  pop     rbp
0x14000f9b9  pop     rbx
0x14000f9ba  retn
```
