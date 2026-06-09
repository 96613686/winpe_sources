# LcmCmMakeCallPassive

- ea: `0x1400024e0`
- end: `0x140002cd1`
- name: `LcmCmMakeCallPassive`
- size: `2033`
- prototype: `__int64 __fastcall(PVOID VirtualAddress, NDIS_HANDLE NdisIoWorkItemHandle)`
- caller_count: `0`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140001850`
- `0x140001870`
- `0x140001b70`
- `0x1400024e0`
- `0x140003050`
- `0x1400030c4`
- `0x1400047f0`
- `0x1400106b4`
- `0x140011144`
- `0x140011288`
- `0x140018844`
- `0x14001c050`
- `0x14001dc40`

## import_xrefs

- `ntoskrnl!RtlIpv6StringToAddressA` at `0x140002646`
- `ntoskrnl!RtlIpv6StringToAddressA` at `0x140002646`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002670`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400026bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002a92`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002670`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400026bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002a92`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002c2e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002c41`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002c2e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002c41`
- `ntoskrnl!MmLockPagableDataSection` at `0x14000257c`
- `ntoskrnl!MmLockPagableDataSection` at `0x14000257c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002b9f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002bd6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002b9f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002bd6`
- `NDIS!NdisFreeIoWorkItem` at `0x1400025a2`
- `NDIS!NdisFreeIoWorkItem` at `0x1400025a2`
- `NDIS!NdisCmMakeCallComplete` at `0x140002c9d`
- `NDIS!NdisCmMakeCallComplete` at `0x140002c9d`
- `NDIS!NdisFreeMemory` at `0x1400025b8`
- `NDIS!NdisFreeMemory` at `0x1400025b8`

## pseudocode

```c
void __fastcall LcmCmMakeCallPassive(__int64 *VirtualAddress, NDIS_HANDLE NdisIoWorkItemHandle)
{
  __int64 v2; // r13
  signed __int64 v3; // r12
  __int64 v6; // r14
  int v7; // ebx
  __int64 v8; // rax
  __int64 v9; // rbx
  __int64 v10; // rdx
  __int64 v11; // r15
  __int64 v12; // rcx
  const CHAR *v13; // rax
  const CHAR *v14; // rdi
  int v15; // eax
  _DWORD *v16; // r15
  char *v17; // rbx
  int v18; // ecx
  char v19; // al
  char v20; // r8
  char v21; // r10
  char v22; // r11
  char v23; // bl
  char v24; // di
  char v25; // si
  char v26; // r14
  char v27; // r15
  char v28; // r12
  struct _DEVICE_OBJECT *AttachedDevice; // rcx
  int v30; // r9d
  char v31; // al
  char v32; // cl
  char v33; // r10
  char v34; // r8
  char v35; // r11
  char v36; // bl
  char v37; // di
  char v38; // si
  char v39; // r14
  char v40; // r15
  char v41; // r12
  char v42; // r13
  struct _DEVICE_OBJECT *v43; // rcx
  __int64 v44; // rdi
  char v45; // si
  char v46; // r9
  __int64 v47; // rax
  NDIS_STATUS v48; // ecx
  unsigned int v49; // r8d
  __int64 v50; // rdx
  __int64 v51; // r9
  in6_addr *v52; // rdx
  __int64 v53; // rax
  __int64 v54; // rdi
  KIRQL v55; // al
  bool v56; // zf
  __int64 *v57; // rcx
  int v58; // [rsp+28h] [rbp-F8h]
  char v59; // [rsp+28h] [rbp-F8h]
  int v60; // [rsp+30h] [rbp-F0h]
  char v61; // [rsp+30h] [rbp-F0h]
  char v62; // [rsp+38h] [rbp-E8h]
  char v63; // [rsp+88h] [rbp-98h]
  char v64; // [rsp+88h] [rbp-98h]
  char v65; // [rsp+A0h] [rbp-80h]
  bool v66; // [rsp+A1h] [rbp-7Fh]
  PCSTR Terminator; // [rsp+B0h] [rbp-70h] BYREF
  int v68; // [rsp+B8h] [rbp-68h]
  _BYTE *v69; // [rsp+C0h] [rbp-60h]
  PDEVICE_OBJECT v70; // [rsp+C8h] [rbp-58h]
  char *v71; // [rsp+D0h] [rbp-50h]
  __int64 v72; // [rsp+D8h] [rbp-48h]
  __int64 v73; // [rsp+E0h] [rbp-40h]
  _DWORD *v74; // [rsp+E8h] [rbp-38h]
  signed __int64 v75; // [rsp+F0h] [rbp-30h]
  in6_addr Addr; // [rsp+F8h] [rbp-28h] BYREF
  in6_addr v77[2]; // [rsp+108h] [rbp-18h] BYREF
  __int128 v78; // [rsp+128h] [rbp+8h] BYREF

  v2 = *VirtualAddress;
  v3 = VirtualAddress[1];
  memset(v77, 0, 28);
  v69 = (_BYTE *)v2;
  v75 = v3;
  v78 = 0;
  Addr = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids);
  }
  if ( !g_fPagesLocked )
  {
    MmLockPagableDataSection(CreateTunnelCb);
    g_fPagesLocked = 1;
  }
  v6 = *(_QWORD *)(v2 + 24);
  v73 = v6;
  DereferenceAdapter(v6);
  NdisFreeIoWorkItem(NdisIoWorkItemHandle);
  NdisFreeMemory(VirtualAddress, 0x10u, 0);
  if ( (*(_DWORD *)v3 & 0x19) != 0 )
  {
    v7 = -1073741637;
    goto LABEL_80;
  }
  if ( (*(_DWORD *)v3 & 2) != 0 )
    goto LABEL_79;
  v8 = *(_QWORD *)(v3 + 16);
  if ( !v8 )
    goto LABEL_79;
  if ( *(_DWORD *)(v8 + 20) < 0x30u )
    goto LABEL_79;
  v9 = v8 + 24;
  v72 = v8 + 24;
  if ( *(_WORD *)(v8 + 56) < 0xB4u )
    goto LABEL_79;
  v10 = *(unsigned __int16 *)(v8 + 40);
  v11 = *(_QWORD *)(v8 + 64);
  v12 = v8 + 24 + *(_QWORD *)(v8 + 48) + 16LL;
  Terminator = 0;
  v13 = (const CHAR *)StrDupUnicodeToAscii(v12, v10);
  v14 = v13;
  if ( !v13 )
  {
LABEL_14:
    v7 = -1073741670;
    goto LABEL_80;
  }
  if ( RtlIpv6StringToAddressA(v13, &Terminator, &Addr) < 0 || *Terminator )
  {
    v15 = IpAddressFromDotted(v14);
    v68 = v15;
    if ( (unsigned int)(v15 - 1) > 0xFFFFFFFD )
      goto LABEL_18;
    v65 = 0;
    if ( (v15 & 0xF0) == 0xE0 )
      goto LABEL_18;
  }
  else
  {
    if ( Addr.u.Byte[0] == 0xFF )
    {
LABEL_18:
      v7 = -1073676254;
      ExFreePoolWithTag((PVOID)(v14 - 16), 0);
      goto LABEL_80;
    }
    v68 = 0;
    v65 = 1;
  }
  v16 = (_DWORD *)(v9 + v11 + 32);
  v74 = v16;
  ExFreePoolWithTag((PVOID)(v14 - 16), 0);
  if ( (v16[4] & 0xFFFFFEEF) != 0 )
  {
LABEL_79:
    v7 = -1073676267;
    goto LABEL_80;
  }
  if ( v16[26] == 36 )
  {
    v17 = (char *)v16 + (unsigned int)v16[27];
    v71 = v17;
    *(_QWORD *)(v2 + 192) = v17;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids);
    }
    v18 = *((_DWORD *)v17 + 2);
    if ( (v18 & 2) == 0 )
      *((_DWORD *)v17 + 3) = -1;
    v66 = (v18 & 1) == 0;
    if ( (v18 & 8) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids);
      }
      *(_OWORD *)(v2 + 208) = *(_OWORD *)(v17 + 20);
      *(_BYTE *)(v2 + 224) = 0;
      v70 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v19 = *(_BYTE *)(v2 + 223);
          v20 = *(_BYTE *)(v2 + 221);
          v21 = *(_BYTE *)(v2 + 220);
          v22 = *(_BYTE *)(v2 + 219);
          v23 = *(_BYTE *)(v2 + 218);
          v24 = *(_BYTE *)(v2 + 217);
          v25 = *(_BYTE *)(v2 + 216);
          v26 = *(_BYTE *)(v2 + 215);
          v27 = *(_BYTE *)(v2 + 214);
          v28 = *(_BYTE *)(v2 + 213);
          v63 = *(_BYTE *)(v2 + 222);
          AttachedDevice = v70->AttachedDevice;
          v30 = (unsigned __int8)v69[208];
          v62 = *(_BYTE *)(v2 + 212);
          v61 = v69[211];
          v59 = v69[210];
          LODWORD(Terminator) = (unsigned __int8)v69[209];
          WPP_SF_DDDDDDDDDDDDDDDD(
            (_DWORD)AttachedDevice,
            27,
            (unsigned int)WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids,
            v30,
            (char)Terminator,
            v59,
            v61,
            v62,
            v28,
            v27,
            v26,
            v25,
            v24,
            v23,
            v22,
            v21,
            v20,
            v63,
            v19);
          v2 = (__int64)v69;
        }
        v70 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v31 = *(_BYTE *)(v2 + 223);
          v32 = *(_BYTE *)(v2 + 222);
          v33 = *(_BYTE *)(v2 + 221);
          v34 = v69[213];
          v35 = *(_BYTE *)(v2 + 220);
          v36 = *(_BYTE *)(v2 + 219);
          v37 = *(_BYTE *)(v2 + 218);
          v38 = *(_BYTE *)(v2 + 217);
          v39 = *(_BYTE *)(v2 + 216);
          v40 = *(_BYTE *)(v2 + 214);
          v41 = *(_BYTE *)(v2 + 215);
          v42 = *(_BYTE *)(v2 + 212);
          v64 = v32;
          v43 = v70->AttachedDevice;
          LODWORD(Terminator) = (unsigned __int8)v69[208];
          WPP_SF_DDDDDDDDDDDDDDDD(
            (_DWORD)v43,
            28,
            (unsigned int)WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids,
            (unsigned __int8)v69[211],
            v69[210],
            v69[209],
            (char)Terminator,
            v34,
            v42,
            v41,
            v40,
            v39,
            v38,
            v37,
            v36,
            v35,
            v33,
            v64,
            v31);
        }
      }
    }
    v2 = (__int64)v69;
    v44 = (__int64)v71;
    v9 = v72;
    v45 = v66;
    v6 = v73;
    v16 = v74;
    v46 = 0;
    v3 = v75;
  }
  else
  {
    v47 = ALLOC_NONPAGED(36, 1817457228);
    v44 = v47;
    if ( !v47 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids);
      }
      goto LABEL_14;
    }
    v45 = 1;
    *(_DWORD *)(v47 + 12) = -1;
    v46 = 1;
  }
  if ( _InterlockedCompareExchange64((volatile signed __int64 *)(v2 + 168), v3, 0) )
  {
    if ( v46 )
      ExFreePoolWithTag((PVOID)(v44 - 16), 0);
    v48 = 65543;
    goto LABEL_81;
  }
  *(_QWORD *)(v2 + 176) = v9;
  *(_QWORD *)(v2 + 184) = v16;
  *(_QWORD *)(v2 + 192) = v44;
  v49 = **(_DWORD **)(v3 + 16) & 1 | 0x10;
  if ( (*(_BYTE *)(v6 + 8) & 1) == 0 )
    v49 = **(_DWORD **)(v3 + 16) & 1;
  v50 = v49 | 8;
  if ( !v46 )
    v50 = v49;
  if ( (_DWORD)v50 )
    SetFlags(v2 + 60, v50);
  _InterlockedAdd((volatile signed __int32 *)(v6 + 80), 1u);
  v7 = ReserveCallIdSlot(v2);
  if ( !v7 )
  {
    if ( v45 )
      v51 = *(_DWORD *)(v6 + 8) >> 2;
    else
      LOBYTE(v51) = *(_BYTE *)(v44 + 8);
    LOBYTE(v51) = v51 & 1;
    if ( v65 )
    {
      v77[0].u.Word[0] = 23;
      *(in6_addr *)((char *)v77 + 8) = Addr;
    }
    else
    {
      LOWORD(v78) = 2;
      DWORD1(v78) = v68;
    }
    v52 = v77;
    if ( !v65 )
      v52 = (in6_addr *)&v78;
    v53 = SetupTunnel(v6, v52, 0, v51);
    v54 = v53;
    if ( v53 )
    {
      v55 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v53 + 32));
      v56 = (*(_DWORD *)(v54 + 120) & 0x100) == 0;
      *(_BYTE *)(v54 + 40) = v55;
      if ( v56 )
      {
        SetFlags(v2 + 60, 8198);
        *(_BYTE *)(v54 + 368) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v54 + 360));
        *(_QWORD *)(v2 + 32) = v54;
        _InterlockedAdd((volatile signed __int32 *)(v2 + 20), 1u);
        v57 = *(__int64 **)(v54 + 352);
        if ( *v57 != v54 + 344 )
          __fastfail(3u);
        *(_QWORD *)(v2 + 8) = v57;
        *(_QWORD *)v2 = v54 + 344;
        *v57 = v2;
        *(_QWORD *)(v54 + 352) = v2;
        SetFlags(v2 + 60, 0x2000000);
        KeReleaseSpinLock((PKSPIN_LOCK)(v54 + 360), *(_BYTE *)(v54 + 368));
      }
      else
      {
        v7 = -1073668063;
      }
      KeReleaseSpinLock((PKSPIN_LOCK)(v54 + 32), *(_BYTE *)(v54 + 40));
      if ( !v7 )
      {
        *(_DWORD *)(v2 + 88) = 1;
        ScheduleTunnelWork(v54, v2, (__int64)FsmOpenTunnel, 0, 0, v58, v60, 0);
        return;
      }
    }
    else
    {
      v7 = -1073741670;
    }
  }
  CallCleanUp(v2);
LABEL_80:
  v48 = v7;
LABEL_81:
  NdisCmMakeCallComplete(v48, *(NDIS_HANDLE *)(v2 + 304), 0, 0, *(PCO_CALL_PARAMETERS *)(v2 + 168));
}

```

## disassembly

```asm
0x1400024e0  mov     [rsp-8+arg_10], rbx
0x1400024e5  push    rbp
0x1400024e6  push    rsi
0x1400024e7  push    rdi
0x1400024e8  push    r12
0x1400024ea  push    r13
0x1400024ec  push    r14
0x1400024ee  push    r15
0x1400024f0  lea     rbp, [rsp-20h]
0x1400024f5  sub     rsp, 140h
0x1400024fc  mov     rax, cs:__security_cookie
0x140002503  xor     rax, rsp
0x140002506  mov     [rbp+50h+var_38], rax
0x14000250a  mov     r13, [rcx]
0x14000250d  xorps   xmm0, xmm0
0x140002510  mov     r12, [rcx+8]
0x140002514  xorps   xmm1, xmm1
0x140002517  movups  [rbp+50h+var_68], xmm0
0x14000251b  mov     rdi, rdx
0x14000251e  mov     rbx, rcx
0x140002521  movups  [rbp+50h+var_68+0Ch], xmm0
0x140002525  mov     [rbp+50h+var_B0], r13
0x140002529  mov     [rbp+50h+var_80], r12
0x14000252d  movups  [rbp+50h+var_48], xmm0
0x140002531  movups  xmmword ptr [rbp+50h+Addr.u], xmm1
0x140002535  mov     rcx, cs:WPP_GLOBAL_Control
0x14000253c  lea     rax, WPP_GLOBAL_Control
0x140002543  cmp     rcx, rax
0x140002546  jz      short loc_14000256A
0x140002548  mov     eax, [rcx+2Ch]
0x14000254b  test    al, 4
0x14000254d  jz      short loc_14000256A
0x14000254f  cmp     byte ptr [rcx+29h], 1
0x140002553  jb      short loc_14000256A
0x140002555  mov     rcx, [rcx+18h]
0x140002559  lea     r8, WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids
0x140002560  mov     edx, 18h
0x140002565  call    WPP_SF_
0x14000256a  xor     esi, esi
0x14000256c  cmp     cs:g_fPagesLocked, sil
0x140002573  jnz     short loc_14000258F
0x140002575  lea     rcx, CreateTunnelCb; AddressWithinSection
0x14000257c  call    cs:__imp_MmLockPagableDataSection
0x140002583  nop     dword ptr [rax+rax+00h]
0x140002588  mov     cs:g_fPagesLocked, 1
0x14000258f  mov     r14, [r13+18h]
0x140002593  mov     rcx, r14
0x140002596  mov     [rbp+50h+var_90], r14
0x14000259a  call    DereferenceAdapter
0x14000259f  mov     rcx, rdi; NdisIoWorkItemHandle
0x1400025a2  call    cs:__imp_NdisFreeIoWorkItem
0x1400025a9  nop     dword ptr [rax+rax+00h]
0x1400025ae  xor     r8d, r8d; MemoryFlags
0x1400025b1  mov     rcx, rbx; VirtualAddress
0x1400025b4  lea     edx, [r8+10h]; Length
0x1400025b8  call    cs:__imp_NdisFreeMemory
0x1400025bf  nop     dword ptr [rax+rax+00h]
0x1400025c4  mov     eax, [r12]
0x1400025c8  test    al, 19h
0x1400025ca  jz      short loc_1400025D6
0x1400025cc  mov     ebx, 0C00000BBh
0x1400025d1  jmp     loc_140002C82
0x1400025d6  test    al, 2
0x1400025d8  jnz     loc_140002C7D
0x1400025de  mov     rax, [r12+10h]
0x1400025e3  test    rax, rax
0x1400025e6  jz      loc_140002C7D
0x1400025ec  cmp     dword ptr [rax+14h], 30h ; '0'
0x1400025f0  jb      loc_140002C7D
0x1400025f6  lea     rbx, [rax+18h]
0x1400025fa  mov     eax, 0B4h
0x1400025ff  mov     [rbp+50h+var_98], rbx
0x140002603  cmp     [rbx+20h], ax
0x140002607  jb      loc_140002C7D
0x14000260d  mov     rcx, [rbx+18h]
0x140002611  movzx   edx, word ptr [rbx+10h]
0x140002615  add     rcx, 10h
0x140002619  mov     r15, [rbx+28h]
0x14000261d  add     rcx, rbx
0x140002620  mov     [rbp+50h+Terminator], rsi
0x140002624  call    StrDupUnicodeToAscii
0x140002629  mov     rdi, rax
0x14000262c  test    rax, rax
0x14000262f  jnz     short loc_14000263B
0x140002631  mov     ebx, 0C000009Ah
0x140002636  jmp     loc_140002C82
0x14000263b  lea     r8, [rbp+50h+Addr]; Addr
0x14000263f  mov     rcx, rdi; S
0x140002642  lea     rdx, [rbp+50h+Terminator]; Terminator
0x140002646  call    cs:__imp_RtlIpv6StringToAddressA
0x14000264d  nop     dword ptr [rax+rax+00h]
0x140002652  test    eax, eax
0x140002654  js      short loc_14000268A
0x140002656  mov     rax, [rbp+50h+Terminator]
0x14000265a  cmp     [rax], sil
0x14000265d  jnz     short loc_14000268A
0x14000265f  cmp     byte ptr [rbp+50h+Addr.u], 0FFh
0x140002663  jnz     short loc_140002681
0x140002665  lea     rcx, [rdi-10h]; P
0x140002669  xor     edx, edx; Tag
0x14000266b  mov     ebx, 0C0010022h
0x140002670  call    cs:__imp_ExFreePoolWithTag
0x140002677  nop     dword ptr [rax+rax+00h]
0x14000267c  jmp     loc_140002C82
0x140002681  mov     [rbp+50h+var_B8], esi
0x140002684  mov     [rbp+50h+var_D0], 1
0x140002688  jmp     short loc_1400026AE
0x14000268a  mov     rcx, rdi
0x14000268d  call    IpAddressFromDotted
0x140002692  mov     [rbp+50h+var_B8], eax
0x140002695  lea     ecx, [rax-1]
0x140002698  cmp     ecx, 0FFFFFFFDh
0x14000269b  ja      short loc_140002665
0x14000269d  mov     ecx, eax
0x14000269f  mov     [rbp+50h+var_D0], sil
0x1400026a3  and     ecx, 0F0h
0x1400026a9  cmp     cl, 0E0h
0x1400026ac  jz      short loc_140002665
0x1400026ae  add     r15, 20h ; ' '
0x1400026b2  lea     rcx, [rdi-10h]; P
0x1400026b6  add     r15, rbx
0x1400026b9  xor     edx, edx; Tag
0x1400026bb  mov     [rbp+50h+var_88], r15
0x1400026bf  call    cs:__imp_ExFreePoolWithTag
0x1400026c6  nop     dword ptr [rax+rax+00h]
0x1400026cb  test    dword ptr [r15+10h], 0FFFFFEEFh
0x1400026d3  jnz     loc_140002C7D
0x1400026d9  mov     ecx, 24h ; '$'
0x1400026de  cmp     [r15+68h], ecx
0x1400026e2  jnz     loc_140002A17
0x1400026e8  mov     ebx, [r15+6Ch]
0x1400026ec  add     rbx, r15
0x1400026ef  mov     [rbp+50h+var_CE], sil
0x1400026f3  mov     [rbp+50h+var_A0], rbx
0x1400026f7  mov     [r13+0C0h], rbx
0x1400026fe  mov     rcx, cs:WPP_GLOBAL_Control
0x140002705  lea     rdi, WPP_GLOBAL_Control
0x14000270c  cmp     rcx, rdi
0x14000270f  jz      short loc_140002733
0x140002711  mov     eax, [rcx+2Ch]
0x140002714  test    al, 4
0x140002716  jz      short loc_140002733
0x140002718  cmp     byte ptr [rcx+29h], 1
0x14000271c  jb      short loc_140002733
0x14000271e  mov     rcx, [rcx+18h]
0x140002722  lea     r8, WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids
0x140002729  mov     edx, 19h
0x14000272e  call    WPP_SF_
0x140002733  mov     ecx, [rbx+8]
0x140002736  mov     r14d, 2
0x14000273c  test    r14b, cl
0x14000273f  jnz     short loc_140002748
0x140002741  mov     dword ptr [rbx+0Ch], 0FFFFFFFFh
0x140002748  mov     al, cl
0x14000274a  not     al
0x14000274c  and     al, 1
0x14000274e  mov     [rbp+50h+var_CF], al
0x140002751  test    cl, 8
0x140002754  jz      loc_1400029F5
0x14000275a  mov     rcx, cs:WPP_GLOBAL_Control
0x140002761  cmp     rcx, rdi
0x140002764  jz      short loc_140002788
0x140002766  mov     eax, [rcx+2Ch]
0x140002769  test    al, 4
0x14000276b  jz      short loc_140002788
0x14000276d  cmp     byte ptr [rcx+29h], 1
0x140002771  jb      short loc_140002788
0x140002773  mov     rcx, [rcx+18h]
0x140002777  lea     r8, WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids
0x14000277e  mov     edx, 1Ah
0x140002783  call    WPP_SF_
0x140002788  movups  xmm0, xmmword ptr [rbx+14h]
0x14000278c  movdqu  xmmword ptr [r13+0D0h], xmm0
0x140002795  mov     [r13+0E0h], sil
0x14000279c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400027a3  mov     [rbp+50h+var_A8], rcx
0x1400027a7  cmp     rcx, rdi
0x1400027aa  jz      loc_1400029F5
0x1400027b0  mov     eax, [rcx+2Ch]
0x1400027b3  test    al, 4
0x1400027b5  jz      loc_1400028D1
0x1400027bb  cmp     [rcx+29h], r14b
0x1400027bf  jb      loc_1400028D1
0x1400027c5  mov     r9, [rbp+50h+var_B0]
0x1400027c9  movzx   eax, byte ptr [r13+0DFh]
0x1400027d1  movzx   ecx, byte ptr [r13+0DEh]
0x1400027d9  movzx   r8d, byte ptr [r13+0DDh]
0x1400027e1  movzx   edx, byte ptr [r9+0D3h]
0x1400027e9  movzx   r10d, byte ptr [r13+0DCh]
0x1400027f1  movzx   r11d, byte ptr [r13+0DBh]
0x1400027f9  movzx   ebx, byte ptr [r13+0DAh]
0x140002801  movzx   edi, byte ptr [r13+0D9h]
0x140002809  movzx   esi, byte ptr [r13+0D8h]
0x140002811  movzx   r14d, byte ptr [r13+0D7h]
0x140002819  movzx   r15d, byte ptr [r13+0D6h]
0x140002821  movzx   r12d, byte ptr [r13+0D5h]
0x140002829  movzx   r13d, byte ptr [r13+0D4h]
0x140002831  mov     [rsp+170h+var_E0], eax
0x140002838  mov     dword ptr [rsp+170h+var_E8], ecx
0x14000283f  mov     rcx, [rbp+50h+var_A8]
0x140002843  mov     [rsp+170h+var_F0], r8d
0x14000284b  lea     r8, WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids
0x140002852  mov     [rsp+170h+var_F8], r10d
0x140002857  mov     [rsp+170h+var_100], r11d
0x14000285c  mov     rcx, [rcx+18h]
0x140002860  mov     [rsp+170h+var_108], ebx
0x140002864  mov     [rsp+170h+var_110], edi
0x140002868  mov     [rsp+170h+var_118], esi
0x14000286c  mov     [rsp+170h+var_120], r14d
0x140002871  mov     [rbp+50h+var_CC], edx
0x140002874  movzx   edx, byte ptr [r9+0D2h]
0x14000287c  mov     eax, [rbp+50h+var_CC]
0x14000287f  mov     [rsp+170h+var_128], r15d
0x140002884  mov     [rsp+170h+var_130], r12d
0x140002889  mov     [rbp+50h+var_C8], edx
0x14000288c  movzx   edx, byte ptr [r9+0D1h]
0x140002894  movzx   r9d, byte ptr [r9+0D0h]
0x14000289c  mov     dword ptr [rsp+170h+var_138], r13d
0x1400028a1  mov     [rsp+170h+var_140], eax
0x1400028a5  mov     eax, [rbp+50h+var_C8]
0x1400028a8  mov     [rsp+170h+var_148], eax
0x1400028ac  mov     dword ptr [rbp+50h+Terminator], edx
0x1400028af  mov     edx, 1Bh
0x1400028b4  mov     eax, dword ptr [rbp+50h+Terminator]
0x1400028b7  mov     dword ptr [rsp+170h+CallParameters], eax
0x1400028bb  call    WPP_SF_DDDDDDDDDDDDDDDD
0x1400028c0  mov     r13, [rbp+50h+var_B0]
0x1400028c4  lea     rdi, WPP_GLOBAL_Control
0x1400028cb  mov     r14d, 2
0x1400028d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400028d8  mov     [rbp+50h+var_A8], rcx
0x1400028dc  cmp     rcx, rdi
0x1400028df  jz      loc_1400029F5
0x1400028e5  mov     eax, [rcx+2Ch]
0x1400028e8  test    al, 4
0x1400028ea  jz      loc_1400029F5
0x1400028f0  cmp     [rcx+29h], r14b
0x1400028f4  jb      loc_1400029F5
0x1400028fa  mov     r9, [rbp+50h+var_B0]
0x1400028fe  movzx   eax, byte ptr [r13+0DFh]
0x140002906  movzx   ecx, byte ptr [r13+0DEh]
0x14000290e  movzx   r10d, byte ptr [r13+0DDh]
0x140002916  movzx   edx, byte ptr [r9+0D0h]
0x14000291e  movzx   r8d, byte ptr [r9+0D5h]
0x140002926  movzx   r11d, byte ptr [r13+0DCh]
0x14000292e  movzx   ebx, byte ptr [r13+0DBh]
0x140002936  movzx   edi, byte ptr [r13+0DAh]
0x14000293e  movzx   esi, byte ptr [r13+0D9h]
0x140002946  movzx   r14d, byte ptr [r13+0D8h]
0x14000294e  movzx   r15d, byte ptr [r13+0D6h]
0x140002956  movzx   r12d, byte ptr [r13+0D7h]
0x14000295e  movzx   r13d, byte ptr [r13+0D4h]
0x140002966  mov     [rsp+170h+var_E0], eax
0x14000296d  mov     dword ptr [rsp+170h+var_E8], ecx
0x140002974  mov     rcx, [rbp+50h+var_A8]
0x140002978  mov     [rsp+170h+var_F0], r10d
0x140002980  mov     [rsp+170h+var_F8], r11d
0x140002985  mov     [rsp+170h+var_100], ebx
0x140002989  mov     rcx, [rcx+18h]
0x14000298d  mov     [rsp+170h+var_108], edi
0x140002991  mov     [rsp+170h+var_110], esi
0x140002995  mov     [rsp+170h+var_118], r14d
0x14000299a  mov     [rsp+170h+var_120], r15d
0x14000299f  mov     dword ptr [rbp+50h+Terminator], edx
0x1400029a2  movzx   edx, byte ptr [r9+0D1h]
0x1400029aa  mov     eax, dword ptr [rbp+50h+Terminator]
0x1400029ad  mov     [rsp+170h+var_128], r12d
0x1400029b2  mov     [rsp+170h+var_130], r13d
0x1400029b7  mov     dword ptr [rsp+170h+var_138], r8d
0x1400029bc  lea     r8, WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids
0x1400029c3  mov     [rsp+170h+var_140], eax
0x1400029c7  mov     [rbp+50h+var_C8], edx
0x1400029ca  movzx   edx, byte ptr [r9+0D2h]
0x1400029d2  mov     eax, [rbp+50h+var_C8]
0x1400029d5  movzx   r9d, byte ptr [r9+0D3h]
0x1400029dd  mov     [rbp+50h+var_CC], edx
0x1400029e0  mov     edx, 1Ch
0x1400029e5  mov     [rsp+170h+var_148], eax
0x1400029e9  mov     eax, [rbp+50h+var_CC]
0x1400029ec  mov     dword ptr [rsp+170h+CallParameters], eax
0x1400029f0  call    WPP_SF_DDDDDDDDDDDDDDDD
0x1400029f5  mov     r13, [rbp+50h+var_B0]
0x1400029f9  mov     rdi, [rbp+50h+var_A0]
0x1400029fd  mov     rbx, [rbp+50h+var_98]
0x140002a01  mov     sil, [rbp+50h+var_CF]
0x140002a05  mov     r14, [rbp+50h+var_90]
0x140002a09  mov     r15, [rbp+50h+var_88]
0x140002a0d  mov     r9b, [rbp+50h+var_CE]
0x140002a11  mov     r12, [rbp+50h+var_80]
0x140002a15  jmp     short loc_140002A7A
0x140002a17  mov     edx, 6C54324Ch
0x140002a1c  call    ALLOC_NONPAGED
0x140002a21  mov     rdi, rax
0x140002a24  test    rax, rax
0x140002a27  jnz     short loc_140002A6D
0x140002a29  mov     rcx, cs:WPP_GLOBAL_Control
0x140002a30  lea     rax, WPP_GLOBAL_Control
0x140002a37  cmp     rcx, rax
0x140002a3a  jz      loc_140002631
0x140002a40  mov     eax, [rcx+2Ch]
  ... truncated ...
```
