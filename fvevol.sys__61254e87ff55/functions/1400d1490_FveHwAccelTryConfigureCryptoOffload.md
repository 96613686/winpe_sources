# FveHwAccelTryConfigureCryptoOffload

- ea: `0x1400d1490`
- end: `0x1400d1afb`
- name: `FveHwAccelTryConfigureCryptoOffload`
- size: `1643`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1400ab924`
- `0x1400b8a3c`

## callees

- `0x140005e60`
- `0x140008e80`
- `0x140008f04`
- `0x14000d690`
- `0x140012064`
- `0x1400122bc`
- `0x1400cee64`
- `0x1400cf160`
- `0x1400cf890`
- `0x1400d1490`
- `0x1400d1b04`
- `0x1400e89fc`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400d17cf`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400d1837`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400d17cf`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400d1837`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400d1779`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400d17aa`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400d18cd`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400d1779`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400d17aa`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400d18cd`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400d1a7f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400d1a7f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400d152f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400d152f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d153f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d1a8b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d153f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d1a8b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d1517`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d1517`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d18b2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d18b2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d1757`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d1757`

## pseudocode

```c
__int64 __fastcall FveHwAccelTryConfigureCryptoOffload(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // r13
  __int64 v4; // r15
  unsigned int *v5; // rsi
  struct _ERESOURCE *v9; // r12
  __int64 v10; // r9
  unsigned int v11; // ebx
  PDEVICE_OBJECT v12; // rcx
  __int64 v13; // rdx
  int FvekDatumFromVmk; // eax
  int MatchingCapability; // eax
  __int64 v16; // r9
  PDEVICE_OBJECT v17; // rcx
  __int64 v18; // rdx
  int v19; // eax
  KIRQL v20; // al
  void *v21; // rdx
  KIRQL v22; // r12
  void *v23; // rdx
  PVOID v24; // r14
  PDEVICE_OBJECT v25; // rcx
  __int64 v26; // rdx
  PVOID v27; // rax
  PVOID v28; // rax
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v32; // [rsp+50h] [rbp-10h] BYREF
  __int64 v33; // [rsp+58h] [rbp-8h] BYREF
  unsigned int *v34; // [rsp+A0h] [rbp+40h] BYREF
  PVOID P; // [rsp+B8h] [rbp+58h] BYREF

  v3 = *(_QWORD *)(a1 + 8);
  v4 = 0;
  v32 = 0;
  v5 = 0;
  v34 = 0;
  v33 = 0;
  P = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 100, WPP_7f5e3a43786933c00401282694ab6ced_Traceguids);
  }
  FveHwAccelDestroyConfiguration(*(PVOID *)(a1 + 5144));
  *(_QWORD *)(a1 + 5144) = 0;
  KeEnterCriticalRegion();
  v9 = (struct _ERESOURCE *)(v3 + 10600);
  if ( !ExAcquireResourceExclusiveLite((PERESOURCE)(v3 + 10600), 1u) )
    KeLeaveCriticalRegion();
  if ( *(_QWORD *)(v3 + 10752) )
  {
    FvekDatumFromVmk = GetFvekDatumFromVmk(a2, a3, &v32);
    v11 = FvekDatumFromVmk;
    if ( FvekDatumFromVmk < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          102,
          WPP_7f5e3a43786933c00401282694ab6ced_Traceguids,
          (unsigned int)FvekDatumFromVmk);
      }
      v4 = v32;
      goto LABEL_67;
    }
    v4 = v32;
    MatchingCapability = FveHwAccelFindMatchingCapability(
                           a1,
                           *(unsigned __int16 *)(v32 + 8),
                           *(_DWORD *)(a1 + 1308),
                           *(_QWORD *)(a1 + 1048),
                           (__int64)&v34);
    v11 = MatchingCapability;
    if ( MatchingCapability == -1073741275 )
    {
      v16 = 3221225659LL;
      v11 = -1073741637;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
      {
        goto LABEL_24;
      }
      v18 = 103;
LABEL_23:
      WPP_SF_d(v17->AttachedDevice, v18, WPP_7f5e3a43786933c00401282694ab6ced_Traceguids, v16);
LABEL_24:
      v5 = v34;
      goto LABEL_67;
    }
    if ( MatchingCapability < 0 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_24;
      }
      v18 = 104;
      v16 = (unsigned int)MatchingCapability;
      goto LABEL_23;
    }
    v5 = v34;
    v19 = FveHwAccelVerifyCryptoCapability(a1, v34, &v33);
    v11 = v19;
    if ( v19 < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_67;
      }
      v13 = 105;
      goto LABEL_35;
    }
    if ( *(int *)(v33 + 28) < 0 || !*(_BYTE *)(v33 + 24) )
    {
      v11 = -1071579034;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v13 = 106;
        v10 = 3223388262LL;
        goto LABEL_66;
      }
      goto LABEL_67;
    }
    v19 = FveHwAccelCreateConfiguration(a1, v5, v4, &P);
    v11 = v19;
    if ( v19 < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_67;
      }
      v13 = 107;
LABEL_35:
      v10 = (unsigned int)v19;
      goto LABEL_66;
    }
    v20 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 2032));
    v21 = *(void **)(a1 + 2192);
    v22 = v20;
    if ( v21 )
    {
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v3 + 10712), v21);
      *(_QWORD *)(a1 + 2192) = 0;
      *(_BYTE *)(a1 + 2200) = 0;
    }
    v23 = *(void **)(a1 + 2176);
    if ( v23 )
    {
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v3 + 10720), v23);
      *(_QWORD *)(a1 + 2176) = 0;
      *(_BYTE *)(a1 + 2184) = 0;
    }
    v24 = ExAllocateFromNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v3 + 10712));
    if ( v24 )
    {
      v27 = ExAllocateFromNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v3 + 10720));
      if ( v27 )
      {
        *(_QWORD *)(a1 + 2176) = v27;
        v28 = P;
        *(_QWORD *)(a1 + 2192) = v24;
        v24 = 0;
        *(_QWORD *)(a1 + 5144) = v28;
        *(_BYTE *)(a1 + 2200) = 0;
        *(_BYTE *)(a1 + 2184) = 0;
        P = 0;
        goto LABEL_59;
      }
      v11 = -1073741670;
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_59;
      }
      v26 = 109;
    }
    else
    {
      v11 = -1073741670;
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_59;
      }
      v26 = 108;
    }
    WPP_SF_d(v25->AttachedDevice, v26, WPP_7f5e3a43786933c00401282694ab6ced_Traceguids, 3221225626LL);
LABEL_59:
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 2032), v22);
    if ( v24 )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v3 + 10712), v24);
    v9 = (struct _ERESOURCE *)(v3 + 10600);
    goto LABEL_67;
  }
  v10 = 3221225659LL;
  v11 = -1073741637;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    v13 = 101;
LABEL_66:
    WPP_SF_d(v12->AttachedDevice, v13, WPP_7f5e3a43786933c00401282694ab6ced_Traceguids, v10);
  }
LABEL_67:
  if ( *(_QWORD *)(v3 + 10752) )
  {
    if ( (v11 & 0x80000000) != 0 )
    {
      FveLogStatusEventWithData(v3, a1, FVE_HW_ACCEL_CRYPTO_CONFIG_FAILED);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_ddddLi(
          WPP_GLOBAL_Control->AttachedDevice,
          v4 != 0,
          v5 != 0,
          v11,
          v4 != 0,
          v5 != 0,
          v33 != 0,
          *(_DWORD *)(a1 + 1308),
          *(_QWORD *)(a1 + 1048));
      }
    }
    else
    {
      FveLogStatusEventWithData(v3, a1, FVE_HW_ACCEL_CRYPTO_CONFIGURED);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_LddLi(
          WPP_GLOBAL_Control->AttachedDevice,
          v29,
          v30,
          *v5,
          v5[4],
          v5[5],
          *(_DWORD *)(a1 + 1308),
          *(_QWORD *)(a1 + 1048));
      }
    }
  }
  ExReleaseResourceLite(v9);
  KeLeaveCriticalRegion();
  FveHwAccelDestroyConfiguration(P);
  if ( v4 )
    FveDatumFree(v4);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 112, WPP_7f5e3a43786933c00401282694ab6ced_Traceguids, v11);
  }
  return v11;
}

```

## disassembly

```asm
0x1400d1490  mov     [rsp-38h+arg_8], rbx
0x1400d1495  push    rbp
0x1400d1496  push    rsi
0x1400d1497  push    rdi
0x1400d1498  push    r12
0x1400d149a  push    r13
0x1400d149c  push    r14
0x1400d149e  push    r15
0x1400d14a0  mov     rbp, rsp
0x1400d14a3  sub     rsp, 60h
0x1400d14a7  mov     r13, [rcx+8]
0x1400d14ab  xor     r12d, r12d
0x1400d14ae  mov     r15d, r12d
0x1400d14b1  mov     [rbp+var_10], r12
0x1400d14b5  mov     esi, r12d
0x1400d14b8  mov     [rbp+arg_0], r12
0x1400d14bc  mov     [rbp+var_8], r12
0x1400d14c0  mov     rbx, r8
0x1400d14c3  mov     [rbp+P], r12
0x1400d14c7  mov     r14, rdx
0x1400d14ca  mov     rdi, rcx
0x1400d14cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d14d4  lea     rax, WPP_GLOBAL_Control
0x1400d14db  cmp     rcx, rax
0x1400d14de  jz      short loc_1400D1504
0x1400d14e0  test    dword ptr [rcx+2Ch], 400000h
0x1400d14e7  jz      short loc_1400D1504
0x1400d14e9  cmp     byte ptr [rcx+29h], 5
0x1400d14ed  jb      short loc_1400D1504
0x1400d14ef  mov     rcx, [rcx+18h]
0x1400d14f3  lea     edx, [r12+64h]
0x1400d14f8  lea     r8, WPP_7f5e3a43786933c00401282694ab6ced_Traceguids
0x1400d14ff  call    WPP_SF_
0x1400d1504  mov     rcx, [rdi+1418h]; P
0x1400d150b  call    FveHwAccelDestroyConfiguration
0x1400d1510  mov     [rdi+1418h], r12
0x1400d1517  call    cs:__imp_KeEnterCriticalRegion
0x1400d151e  nop     dword ptr [rax+rax+00h]
0x1400d1523  lea     r12, [r13+2968h]
0x1400d152a  mov     dl, 1; Wait
0x1400d152c  mov     rcx, r12; Resource
0x1400d152f  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400d1536  nop     dword ptr [rax+rax+00h]
0x1400d153b  test    al, al
0x1400d153d  jnz     short loc_1400D154B
0x1400d153f  call    cs:__imp_KeLeaveCriticalRegion
0x1400d1546  nop     dword ptr [rax+rax+00h]
0x1400d154b  cmp     [r13+2A00h], rsi
0x1400d1552  jnz     short loc_1400D1595
0x1400d1554  mov     r9d, 0C00000BBh
0x1400d155a  mov     ebx, r9d
0x1400d155d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d1564  lea     r14, WPP_GLOBAL_Control
0x1400d156b  cmp     rcx, r14
0x1400d156e  jz      loc_1400D1928
0x1400d1574  test    dword ptr [rcx+2Ch], 400000h
0x1400d157b  jz      loc_1400D1928
0x1400d1581  cmp     byte ptr [rcx+29h], 5
0x1400d1585  jb      loc_1400D1928
0x1400d158b  mov     edx, 65h ; 'e'
0x1400d1590  jmp     loc_1400D1918
0x1400d1595  lea     r8, [rbp+var_10]
0x1400d1599  mov     rdx, rbx
0x1400d159c  mov     rcx, r14
0x1400d159f  call    GetFvekDatumFromVmk
0x1400d15a4  mov     ebx, eax
0x1400d15a6  test    eax, eax
0x1400d15a8  jns     short loc_1400D15ED
0x1400d15aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d15b1  lea     r14, WPP_GLOBAL_Control
0x1400d15b8  cmp     rcx, r14
0x1400d15bb  jz      short loc_1400D15E4
0x1400d15bd  test    dword ptr [rcx+2Ch], 400000h
0x1400d15c4  jz      short loc_1400D15E4
0x1400d15c6  cmp     byte ptr [rcx+29h], 2
0x1400d15ca  jb      short loc_1400D15E4
0x1400d15cc  mov     rcx, [rcx+18h]
0x1400d15d0  lea     r8, WPP_7f5e3a43786933c00401282694ab6ced_Traceguids
0x1400d15d7  mov     edx, 66h ; 'f'
0x1400d15dc  mov     r9d, eax
0x1400d15df  call    WPP_SF_d
0x1400d15e4  mov     r15, [rbp+var_10]
0x1400d15e8  jmp     loc_1400D1928
0x1400d15ed  mov     r15, [rbp+var_10]
0x1400d15f1  lea     rax, [rbp+arg_0]
0x1400d15f5  mov     r9, [rdi+418h]
0x1400d15fc  mov     rcx, rdi
0x1400d15ff  mov     r8d, [rdi+51Ch]
0x1400d1606  mov     [rsp+60h+var_40], rax
0x1400d160b  movzx   edx, word ptr [r15+8]
0x1400d1610  call    FveHwAccelFindMatchingCapability
0x1400d1615  mov     ebx, eax
0x1400d1617  cmp     eax, 0C0000225h
0x1400d161c  jnz     short loc_1400D1667
0x1400d161e  mov     r9d, 0C00000BBh
0x1400d1624  mov     ebx, r9d
0x1400d1627  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d162e  lea     r14, WPP_GLOBAL_Control
0x1400d1635  cmp     rcx, r14
0x1400d1638  jz      short loc_1400D165E
0x1400d163a  test    dword ptr [rcx+2Ch], 400000h
0x1400d1641  jz      short loc_1400D165E
0x1400d1643  cmp     byte ptr [rcx+29h], 5
0x1400d1647  jb      short loc_1400D165E
0x1400d1649  mov     edx, 67h ; 'g'
0x1400d164e  mov     rcx, [rcx+18h]
0x1400d1652  lea     r8, WPP_7f5e3a43786933c00401282694ab6ced_Traceguids
0x1400d1659  call    WPP_SF_d
0x1400d165e  mov     rsi, [rbp+arg_0]
0x1400d1662  jmp     loc_1400D1928
0x1400d1667  test    eax, eax
0x1400d1669  jns     short loc_1400D1697
0x1400d166b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d1672  lea     r14, WPP_GLOBAL_Control
0x1400d1679  cmp     rcx, r14
0x1400d167c  jz      short loc_1400D165E
0x1400d167e  test    dword ptr [rcx+2Ch], 400000h
0x1400d1685  jz      short loc_1400D165E
0x1400d1687  cmp     byte ptr [rcx+29h], 2
0x1400d168b  jb      short loc_1400D165E
0x1400d168d  mov     edx, 68h ; 'h'
0x1400d1692  mov     r9d, eax
0x1400d1695  jmp     short loc_1400D164E
0x1400d1697  mov     rsi, [rbp+arg_0]
0x1400d169b  lea     r8, [rbp+var_8]
0x1400d169f  mov     rdx, rsi
0x1400d16a2  mov     rcx, rdi
0x1400d16a5  call    FveHwAccelVerifyCryptoCapability
0x1400d16aa  mov     ebx, eax
0x1400d16ac  test    eax, eax
0x1400d16ae  jns     short loc_1400D16EB
0x1400d16b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d16b7  lea     r14, WPP_GLOBAL_Control
0x1400d16be  cmp     rcx, r14
0x1400d16c1  jz      loc_1400D1928
0x1400d16c7  test    dword ptr [rcx+2Ch], 400000h
0x1400d16ce  jz      loc_1400D1928
0x1400d16d4  cmp     byte ptr [rcx+29h], 2
0x1400d16d8  jb      loc_1400D1928
0x1400d16de  mov     edx, 69h ; 'i'
0x1400d16e3  mov     r9d, eax
0x1400d16e6  jmp     loc_1400D1918
0x1400d16eb  mov     rax, [rbp+var_8]
0x1400d16ef  cmp     dword ptr [rax+1Ch], 0
0x1400d16f3  jl      loc_1400D18E9
0x1400d16f9  cmp     byte ptr [rax+18h], 0
0x1400d16fd  jz      loc_1400D18E9
0x1400d1703  lea     r9, [rbp+P]
0x1400d1707  mov     r8, r15
0x1400d170a  mov     rdx, rsi
0x1400d170d  mov     rcx, rdi
0x1400d1710  call    FveHwAccelCreateConfiguration
0x1400d1715  mov     ebx, eax
0x1400d1717  test    eax, eax
0x1400d1719  jns     short loc_1400D1750
0x1400d171b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d1722  lea     r14, WPP_GLOBAL_Control
0x1400d1729  cmp     rcx, r14
0x1400d172c  jz      loc_1400D1928
0x1400d1732  test    dword ptr [rcx+2Ch], 400000h
0x1400d1739  jz      loc_1400D1928
0x1400d173f  cmp     byte ptr [rcx+29h], 2
0x1400d1743  jb      loc_1400D1928
0x1400d1749  mov     edx, 6Bh ; 'k'
0x1400d174e  jmp     short loc_1400D16E3
0x1400d1750  lea     rcx, [rdi+7F0h]; SpinLock
0x1400d1757  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400d175e  nop     dword ptr [rax+rax+00h]
0x1400d1763  mov     rdx, [rdi+890h]; Entry
0x1400d176a  mov     r12b, al
0x1400d176d  test    rdx, rdx
0x1400d1770  jz      short loc_1400D1797
0x1400d1772  mov     rcx, [r13+29D8h]; Lookaside
0x1400d1779  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400d1780  nop     dword ptr [rax+rax+00h]
0x1400d1785  mov     qword ptr [rdi+890h], 0
0x1400d1790  mov     byte ptr [rdi+898h], 0
0x1400d1797  mov     rdx, [rdi+880h]; Entry
0x1400d179e  test    rdx, rdx
0x1400d17a1  jz      short loc_1400D17C8
0x1400d17a3  mov     rcx, [r13+29E0h]; Lookaside
0x1400d17aa  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400d17b1  nop     dword ptr [rax+rax+00h]
0x1400d17b6  mov     qword ptr [rdi+880h], 0
0x1400d17c1  mov     byte ptr [rdi+888h], 0
0x1400d17c8  mov     rcx, [r13+29D8h]; Lookaside
0x1400d17cf  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400d17d6  nop     dword ptr [rax+rax+00h]
0x1400d17db  mov     r14, rax
0x1400d17de  test    rax, rax
0x1400d17e1  jnz     short loc_1400D1830
0x1400d17e3  mov     r9d, 0C000009Ah
0x1400d17e9  mov     ebx, r9d
0x1400d17ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d17f3  lea     rax, WPP_GLOBAL_Control
0x1400d17fa  cmp     rcx, rax
0x1400d17fd  jz      loc_1400D18A8
0x1400d1803  test    dword ptr [rcx+2Ch], 400000h
0x1400d180a  jz      loc_1400D18A8
0x1400d1810  cmp     byte ptr [rcx+29h], 2
0x1400d1814  jb      loc_1400D18A8
0x1400d181a  lea     edx, [r14+6Ch]
0x1400d181e  mov     rcx, [rcx+18h]
0x1400d1822  lea     r8, WPP_7f5e3a43786933c00401282694ab6ced_Traceguids
0x1400d1829  call    WPP_SF_d
0x1400d182e  jmp     short loc_1400D18A8
0x1400d1830  mov     rcx, [r13+29E0h]; Lookaside
0x1400d1837  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400d183e  nop     dword ptr [rax+rax+00h]
0x1400d1843  xor     ecx, ecx
0x1400d1845  test    rax, rax
0x1400d1848  jnz     short loc_1400D187C
0x1400d184a  mov     r9d, 0C000009Ah
0x1400d1850  mov     ebx, r9d
0x1400d1853  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d185a  lea     rax, WPP_GLOBAL_Control
0x1400d1861  cmp     rcx, rax
0x1400d1864  jz      short loc_1400D18A8
0x1400d1866  test    dword ptr [rcx+2Ch], 400000h
0x1400d186d  jz      short loc_1400D18A8
0x1400d186f  cmp     byte ptr [rcx+29h], 2
0x1400d1873  jb      short loc_1400D18A8
0x1400d1875  mov     edx, 6Dh ; 'm'
0x1400d187a  jmp     short loc_1400D181E
0x1400d187c  mov     [rdi+880h], rax
0x1400d1883  mov     rax, [rbp+P]
0x1400d1887  mov     [rdi+890h], r14
0x1400d188e  mov     r14, rcx
0x1400d1891  mov     [rdi+1418h], rax
0x1400d1898  mov     [rdi+898h], cl
0x1400d189e  mov     [rdi+888h], cl
0x1400d18a4  mov     [rbp+P], rcx
0x1400d18a8  lea     rcx, [rdi+7F0h]; SpinLock
0x1400d18af  mov     dl, r12b; NewIrql
0x1400d18b2  call    cs:__imp_KeReleaseSpinLock
0x1400d18b9  nop     dword ptr [rax+rax+00h]
0x1400d18be  test    r14, r14
0x1400d18c1  jz      short loc_1400D18D9
0x1400d18c3  mov     rcx, [r13+29D8h]; Lookaside
0x1400d18ca  mov     rdx, r14; Entry
0x1400d18cd  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400d18d4  nop     dword ptr [rax+rax+00h]
0x1400d18d9  lea     r12, [r13+2968h]
0x1400d18e0  lea     r14, WPP_GLOBAL_Control
0x1400d18e7  jmp     short loc_1400D1928
0x1400d18e9  mov     ebx, 0C0210066h
0x1400d18ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d18f5  lea     r14, WPP_GLOBAL_Control
0x1400d18fc  cmp     rcx, r14
0x1400d18ff  jz      short loc_1400D1928
0x1400d1901  test    dword ptr [rcx+2Ch], 400000h
0x1400d1908  jz      short loc_1400D1928
0x1400d190a  cmp     byte ptr [rcx+29h], 2
0x1400d190e  jb      short loc_1400D1928
0x1400d1910  mov     edx, 6Ah ; 'j'
0x1400d1915  mov     r9d, ebx
0x1400d1918  mov     rcx, [rcx+18h]
0x1400d191c  lea     r8, WPP_7f5e3a43786933c00401282694ab6ced_Traceguids
0x1400d1923  call    WPP_SF_d
0x1400d1928  cmp     qword ptr [r13+2A00h], 0
0x1400d1930  jz      loc_1400D1A7C
0x1400d1936  mov     r9d, ebx
0x1400d1939  test    ebx, ebx
0x1400d193b  js      loc_1400D19CD
0x1400d1941  mov     eax, [rdi+51Ch]
0x1400d1947  lea     r8, FVE_HW_ACCEL_CRYPTO_CONFIGURED
0x1400d194e  mov     dword ptr [rsp+60h+var_28], eax
0x1400d1952  mov     rdx, rdi
0x1400d1955  mov     eax, [rsi+14h]
0x1400d1958  mov     rcx, r13
0x1400d195b  mov     [rsp+60h+var_30], eax
0x1400d195f  mov     eax, [rsi+10h]
0x1400d1962  mov     [rsp+60h+var_38], eax
0x1400d1966  mov     eax, [rsi]
0x1400d1968  mov     dword ptr [rsp+60h+var_40], eax
0x1400d196c  call    FveLogStatusEventWithData
0x1400d1971  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d1978  cmp     rcx, r14
0x1400d197b  jz      loc_1400D1A7C
0x1400d1981  test    dword ptr [rcx+2Ch], 400000h
0x1400d1988  jz      loc_1400D1A7C
0x1400d198e  cmp     byte ptr [rcx+29h], 4
0x1400d1992  jb      loc_1400D1A7C
0x1400d1998  mov     rax, [rdi+418h]
0x1400d199f  mov     r9d, [rsi]
0x1400d19a2  mov     rcx, [rcx+18h]
0x1400d19a6  mov     [rsp+60h+var_28], rax
0x1400d19ab  mov     eax, [rdi+51Ch]
0x1400d19b1  mov     [rsp+60h+var_30], eax
0x1400d19b5  mov     eax, [rsi+14h]
0x1400d19b8  mov     [rsp+60h+var_38], eax
0x1400d19bc  mov     eax, [rsi+10h]
0x1400d19bf  mov     dword ptr [rsp+60h+var_40], eax
0x1400d19c3  call    WPP_SF_LddLi
0x1400d19c8  jmp     loc_1400D1A7C
0x1400d19cd  xor     r8d, r8d
0x1400d19d0  cmp     [rbp+P], r8
0x1400d19d4  setnz   r8b
0x1400d19d8  xor     edx, edx
0x1400d19da  cmp     [rbp+var_8], rdx
  ... truncated ...
```
