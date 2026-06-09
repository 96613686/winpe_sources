# NsiGetParameterEx

- ea: `0x140024cc0`
- end: `0x140025606`
- name: `NsiGetParameterEx`
- size: `2374`
- prototype: ``
- caller_count: `9`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400244e0`
- `0x140024550`
- `0x1400245f0`
- `0x1400249f0`
- `0x140024c40`
- `0x140026570`
- `0x14003d170`
- `0x140040f20`
- `0x140042a40`

## callees

- `0x1400223f0`
- `0x140023a40`
- `0x140023c30`
- `0x140024cc0`
- `0x14002764c`
- `0x140050b00`
- `0x140050ea4`
- `0x1400512d8`
- `0x14005ec50`
- `0x14005f0b0`
- `0x14005f1c4`
- `0x140077fa0`
- `0x140078080`
- `0x140078100`
- `0x140078400`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x140024d53`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140024d53`
- `ntoskrnl!KeGetCurrentIrql` at `0x140024f12`
- `ntoskrnl!KeGetCurrentIrql` at `0x140024f12`
- `ntoskrnl!ExAllocatePool3` at `0x140025282`
- `ntoskrnl!ExAllocatePool3` at `0x140025282`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002524b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400253dc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002524b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400253dc`
- `NDIS!NdisGetThreadObjectCompartmentScope` at `0x140024d83`
- `NDIS!NdisGetThreadObjectCompartmentScope` at `0x140024d83`

## pseudocode

```c
__int64 __fastcall NsiGetParameterEx(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rax
  int v5; // r14d
  int v6; // r15d
  __int128 *v7; // rbx
  char CurrentProcessId; // si
  __int64 v9; // r9
  PDEVICE_OBJECT v10; // rcx
  __int64 v11; // rdx
  int PersistentData; // ebx
  _DWORD *v13; // r14
  __int64 NmpContext; // r13
  int v15; // ecx
  __int64 v16; // rdx
  __int64 v17; // rdx
  unsigned int v18; // r9d
  __int64 v19; // r9
  __int64 v20; // r15
  __int128 v21; // xmm0
  __int128 v22; // xmm1
  int v23; // ecx
  int v24; // eax
  int v25; // ecx
  unsigned int v26; // edx
  char *v27; // rax
  __int128 *v28; // r12
  PDEVICE_OBJECT v29; // rcx
  __int64 v30; // rdx
  unsigned int v31; // esi
  bool v32; // cc
  int IsEnabledDeviceUsageNoInline; // eax
  char *v34; // r14
  char *v35; // rax
  __int64 (__fastcall *v36)(_OWORD *); // rax
  int v37; // eax
  __int64 v38; // rax
  PDEVICE_OBJECT v39; // rcx
  __int64 v40; // rdx
  __int64 v41; // rax
  __int128 *v42; // rdx
  __int64 v44; // [rsp+68h] [rbp-A0h] BYREF
  _QWORD *v45; // [rsp+70h] [rbp-98h] BYREF
  _OWORD v46[2]; // [rsp+78h] [rbp-90h] BYREF
  __int128 v47; // [rsp+98h] [rbp-70h] BYREF
  __int128 v48; // [rsp+A8h] [rbp-60h] BYREF
  __int128 v49; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v50; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v51; // [rsp+D8h] [rbp-30h] BYREF
  __int128 v52; // [rsp+E8h] [rbp-20h]
  __int128 v53; // [rsp+F8h] [rbp-10h]
  __int128 v54; // [rsp+108h] [rbp+0h]
  __int128 v55; // [rsp+118h] [rbp+10h] BYREF

  v51 = 0;
  LODWORD(v44) = 0;
  v52 = 0;
  LODWORD(v45) = 0;
  v53 = 0;
  v54 = 0;
  if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
  {
    v4 = *(_QWORD *)(a1 + 16);
    v5 = *(_DWORD *)(a1 + 32);
    v6 = *(_DWORD *)(a1 + 24);
    v55 = 0;
    v7 = (__int128 *)(v4 + 8);
    if ( !v4 )
      v7 = &v55;
    CurrentProcessId = (unsigned __int8)PsGetCurrentProcessId();
    NdisGetThreadObjectCompartmentScope(KeGetCurrentThread(), &v44, &v45);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    {
      WPP_SF_s_guid_dddqdd(
        WPP_GLOBAL_Control->AttachedDevice,
        v44,
        a3,
        (unsigned int)"NsiGetParameterEx",
        (__int64)v7,
        v6,
        v5,
        CurrentProcessId,
        0,
        (char)v45,
        v44);
    }
  }
  v9 = *(unsigned int *)(a1 + 32);
  if ( (unsigned int)v9 > 3 )
  {
    v39 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0 )
    {
      goto LABEL_153;
    }
    v40 = 14;
LABEL_152:
    WPP_SF_d(v39->AttachedDevice, v40, WPP_b802283a6c2b3e3c6b570e68b8145ddd_Traceguids, v9);
    goto LABEL_153;
  }
  LODWORD(a3) = *(_DWORD *)(a1 + 36);
  if ( (unsigned int)a3 > 2 )
  {
    v39 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0 )
    {
      goto LABEL_153;
    }
    v40 = 15;
    v9 = (unsigned int)a3;
    goto LABEL_152;
  }
  if ( (_DWORD)v9 == 2 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0 )
    {
      goto LABEL_153;
    }
    v11 = 16;
    goto LABEL_16;
  }
  LODWORD(a3) = *(_DWORD *)(a1 + 56);
  if ( (unsigned int)a3 > 2 )
  {
    v39 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0 )
    {
      goto LABEL_153;
    }
    v40 = 17;
    v9 = (unsigned int)a3;
    goto LABEL_152;
  }
  if ( *(_QWORD *)a1 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_b802283a6c2b3e3c6b570e68b8145ddd_Traceguids);
    }
    PersistentData = -1073741822;
    goto LABEL_154;
  }
  v13 = (_DWORD *)(a1 + 72);
  if ( *(unsigned int *)(a1 + 72) + (unsigned __int64)*(unsigned int *)(a1 + 76) > 0xFFFFFFFF )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0 )
    {
      goto LABEL_153;
    }
    v11 = 19;
LABEL_16:
    WPP_SF_(v10->AttachedDevice, v11, WPP_b802283a6c2b3e3c6b570e68b8145ddd_Traceguids);
LABEL_153:
    PersistentData = -1073741811;
    goto LABEL_154;
  }
  NmpContext = 0;
  if ( (_DWORD)v9 )
    NmpContext = NsipGetNmpContext(a1 + 8);
  v15 = *(_DWORD *)(a1 + 32);
  if ( v15 )
  {
    if ( v15 != 3 )
    {
      if ( !NmpContext )
      {
        PersistentData = -1073741637;
        goto LABEL_154;
      }
LABEL_34:
      PersistentData = 0;
      if ( KeGetCurrentIrql() < 2u )
      {
        LOBYTE(v16) = 1;
        PersistentData = NsipAccessCheck(a1 + 8, v16, 0);
        if ( PersistentData < 0 )
          goto LABEL_42;
      }
      v17 = *(_QWORD *)(NmpContext + 48);
      a3 = *(unsigned int *)(a1 + 24);
      v18 = *(_DWORD *)(v17 + 4);
      if ( (unsigned int)a3 >= v18 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
        {
          WPP_SF_Dd(
            WPP_GLOBAL_Control->AttachedDevice,
            21,
            WPP_b802283a6c2b3e3c6b570e68b8145ddd_Traceguids,
            (unsigned int)a3,
            v18);
        }
        goto LABEL_41;
      }
      v19 = *(unsigned int *)(a1 + 48);
      v20 = *(_QWORD *)(v17 + 8) + 104 * a3;
      LODWORD(a3) = *(_DWORD *)v20;
      if ( *(_DWORD *)v20 != (_DWORD)v19 )
      {
LABEL_49:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
        {
          WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_b802283a6c2b3e3c6b570e68b8145ddd_Traceguids, v19, a3);
        }
        goto LABEL_41;
      }
      if ( (_DWORD)v19 )
      {
        if ( !*(_QWORD *)(a1 + 40) )
          goto LABEL_49;
      }
      else if ( *(_QWORD *)(a1 + 40) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_b802283a6c2b3e3c6b570e68b8145ddd_Traceguids);
        }
        *(_QWORD *)(a1 + 40) = 0;
      }
      if ( *(_QWORD *)(a1 + 64) && !*v13 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_b802283a6c2b3e3c6b570e68b8145ddd_Traceguids);
        }
        *(_QWORD *)(a1 + 64) = 0;
      }
      if ( *(_QWORD *)(v20 + 32) )
      {
        v21 = *(_OWORD *)(a1 + 40);
        v22 = *(_OWORD *)(a1 + 56);
        DWORD2(v54) = *(_DWORD *)(a1 + 36);
        v52 = v21;
        *(_QWORD *)&v54 = *(_QWORD *)(a1 + 72);
        v53 = v22;
        *(_QWORD *)&v51 = *(_QWORD *)(NmpContext + 40);
        *((_QWORD *)&v51 + 1) = *(_QWORD *)(v20 + 24);
        PersistentData = (*(__int64 (__fastcall **)(__int128 *))(v20 + 32))(&v51);
        goto LABEL_42;
      }
      if ( !*(_QWORD *)(v20 + 48) )
      {
        PersistentData = -1073741637;
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
        {
          v30 = 31;
          goto LABEL_80;
        }
        goto LABEL_42;
      }
      v23 = *(_DWORD *)(a1 + 56);
      v50 = 0;
      v24 = *(_DWORD *)(a1 + 36);
      v47 = 0;
      LODWORD(v47) = v24;
      v46[0] = 0;
      v48 = 0;
      v49 = 0;
      v46[1] = *(_OWORD *)(a1 + 40);
      if ( v23 )
      {
        v25 = v23 - 1;
        if ( v25 )
        {
          if ( v25 == 1 )
          {
            v26 = *(_DWORD *)(v20 + 12);
            v27 = (char *)&v49 + 8;
            v28 = (__int128 *)&v50;
            goto LABEL_75;
          }
LABEL_41:
          PersistentData = -1073741811;
          goto LABEL_42;
        }
        v26 = *(_DWORD *)(v20 + 8);
        v27 = (char *)&v48 + 8;
        v28 = &v49;
      }
      else
      {
        v26 = *(_DWORD *)(v20 + 4);
        v27 = (char *)&v47 + 8;
        v28 = &v48;
      }
LABEL_75:
      v45 = v27;
      if ( !v26 )
      {
        PersistentData = -1073741637;
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
        {
          v30 = 25;
LABEL_80:
          WPP_SF_(v29->AttachedDevice, v30, WPP_b802283a6c2b3e3c6b570e68b8145ddd_Traceguids);
          goto LABEL_42;
        }
        goto LABEL_42;
      }
      v31 = *v13 + *(_DWORD *)(a1 + 76);
      if ( (*(_BYTE *)(v20 + 16) & 2) != 0 )
      {
        v32 = v26 <= v31;
      }
      else
      {
        v32 = v26 <= v31;
        if ( v26 < v31 )
        {
          PersistentData = -1073741811;
          v29 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
          {
            v30 = 26;
            goto LABEL_80;
          }
LABEL_42:
          if ( NmpContext )
            NsipDereferenceNmpContext(NmpContext);
          goto LABEL_154;
        }
      }
      if ( !v32 )
        v31 = v26;
      if ( (Feature_TCPIP_2025_2511_SFI_58579577_Fix__private_featureState & 0x10) != 0 )
        IsEnabledDeviceUsageNoInline = Feature_TCPIP_2025_2511_SFI_58579577_Fix__private_featureState & 1;
      else
        IsEnabledDeviceUsageNoInline = Feature_TCPIP_2025_2511_SFI_58579577_Fix__private_IsEnabledDeviceUsageNoInline();
      if ( IsEnabledDeviceUsageNoInline && (*(_BYTE *)(v20 + 16) & 2) != 0 && v31 >= 0x100000 )
      {
        PersistentData = -1073741811;
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
        {
          v30 = 27;
          goto LABEL_80;
        }
        goto LABEL_42;
      }
      v34 = 0;
      if ( v31 >= 0x100000 )
      {
LABEL_112:
        if ( PersistentData >= 0 )
        {
LABEL_113:
          memmove(*(void **)(a1 + 64), &v34[*(unsigned int *)(a1 + 76)], *(unsigned int *)(a1 + 72));
LABEL_123:
          if ( v34 )
            ExFreePoolWithTag(v34, 0);
          goto LABEL_42;
        }
      }
      else
      {
        while ( 1 )
        {
          if ( v34 )
            ExFreePoolWithTag(v34, 0);
          v55 = 1u;
          v35 = (char *)ExAllocatePool3(64, v31, 1917408078, &v55, 1);
          v34 = v35;
          if ( !v35 )
            break;
          memset(v35, 0, v31);
          *(_QWORD *)&v46[0] = *(_QWORD *)(NmpContext + 40);
          *((_QWORD *)&v46[0] + 1) = *(_QWORD *)(v20 + 24);
          *v45 = v34;
          v36 = *(__int64 (__fastcall **)(_OWORD *))(v20 + 48);
          *(_DWORD *)v28 = v31;
          v37 = v36(v46);
          PersistentData = v37;
          if ( v37 != -1073741789 )
          {
            if ( v37 < 0 )
              goto LABEL_119;
            if ( *(_DWORD *)v28 >= (unsigned int)(*(_DWORD *)(a1 + 72) + *(_DWORD *)(a1 + 76)) )
              goto LABEL_113;
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
          {
            WPP_SF_Dd(
              WPP_GLOBAL_Control->AttachedDevice,
              29,
              WPP_b802283a6c2b3e3c6b570e68b8145ddd_Traceguids,
              (unsigned int)v37,
              v31);
          }
          v31 *= 2;
          if ( v31 >= 0x100000 )
            goto LABEL_112;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_b802283a6c2b3e3c6b570e68b8145ddd_Traceguids);
        }
        PersistentData = -1073741670;
      }
LABEL_119:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          30,
          WPP_b802283a6c2b3e3c6b570e68b8145ddd_Traceguids,
          (unsigned int)PersistentData);
      }
      goto LABEL_123;
    }
    if ( NmpContext )
      goto LABEL_34;
  }
  if ( *(_DWORD *)(a1 + 56) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_b802283a6c2b3e3c6b570e68b8145ddd_Traceguids);
    }
    goto LABEL_41;
  }
  if ( !*(_QWORD *)(a1 + 16) )
  {
    if ( v15 )
      goto LABEL_41;
    v38 = NsipGetNmpContext(a1 + 8);
    NmpContext = v38;
    if ( !v38 )
      goto LABEL_153;
    *(_QWORD *)(a1 + 16) = *(_QWORD *)(v38 + 24);
  }
  PersistentData = NsipReadPersistentData(
                     (int)a1 + 8,
                     *(_DWORD *)(a1 + 36),
                     (int)a1 + 40,
                     *(_QWORD *)(a1 + 64),
                     0,
                     a1 + 72,
                     *(_DWORD *)(a1 + 76));
  if ( NmpContext )
  {
    *(_QWORD *)(a1 + 16) = 0;
    NsipDereferenceNmpContext(NmpContext);
  }
LABEL_154:
  if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
  {
    v41 = *(_QWORD *)(a1 + 16);
    v55 = 0;
    v42 = (__int128 *)(v41 + 8);
    if ( !v41 )
      v42 = &v55;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_s_guid_dddqddD(
        WPP_GLOBAL_Control->AttachedDevice,
        (_DWORD)v42,
        a3,
        (unsigned int)"NsiGetParameterEx",
        (__int64)v42,
        *(_DWORD *)(a1 + 24),
        *(_DWORD *)(a1 + 32),
        0,
        0,
        0,
        0,
        PersistentData);
  }
  return (unsigned int)PersistentData;
}

```

## disassembly

```asm
0x140024cc0  mov     r11, rsp
0x140024cc3  push    rbp
0x140024cc4  push    rbx
0x140024cc5  push    rdi
0x140024cc6  push    r12
0x140024cc8  lea     rbp, [r11-58h]
0x140024ccc  sub     rsp, 138h
0x140024cd3  mov     rax, cs:__security_cookie
0x140024cda  xor     rax, rsp
0x140024cdd  mov     [rbp+50h+var_30], rax
0x140024ce1  mov     rax, cs:WPP_GLOBAL_Control
0x140024ce8  lea     r12, WPP_GLOBAL_Control
0x140024cef  xorps   xmm0, xmm0
0x140024cf2  mov     [r11+10h], rsi
0x140024cf6  movups  [rbp+50h+var_80], xmm0
0x140024cfa  mov     dword ptr [rsp+150h+var_F0], 0
0x140024d02  mov     rdi, rcx
0x140024d05  movups  [rbp+50h+var_70], xmm0
0x140024d09  mov     dword ptr [rsp+150h+var_E8], 0
0x140024d11  movups  [rbp+50h+var_60], xmm0
0x140024d15  mov     [r11+20h], r14
0x140024d19  movups  [rbp+50h+var_50], xmm0
0x140024d1d  cmp     byte ptr [rax+29h], 5
0x140024d21  mov     [r11-28h], r15
0x140024d25  jb      loc_140024DE4
0x140024d2b  mov     eax, [rax+2Ch]
0x140024d2e  test    al, 10h
0x140024d30  jz      loc_140024DE4
0x140024d36  mov     rax, [rcx+10h]
0x140024d3a  mov     r14d, [rcx+20h]
0x140024d3e  mov     r15d, [rcx+18h]
0x140024d42  movups  [rbp+50h+var_40], xmm0
0x140024d46  lea     rbx, [rax+8]
0x140024d4a  test    rax, rax
0x140024d4d  jnz     short loc_140024D53
0x140024d4f  lea     rbx, [rbp+50h+var_40]
0x140024d53  call    cs:__imp_PsGetCurrentProcessId
0x140024d5a  nop     dword ptr [rax+rax+00h]
0x140024d5f  mov     edx, dword ptr [rsp+150h+var_F0]
0x140024d63  mov     rsi, rax
0x140024d66  test    edx, edx
0x140024d68  jnz     short loc_140024D93
0x140024d6a  cmp     dword ptr [rsp+150h+var_E8], edx
0x140024d6e  jnz     short loc_140024D93
0x140024d70  mov     rcx, gs:188h
0x140024d79  lea     r8, [rsp+150h+var_E8]
0x140024d7e  lea     rdx, [rsp+150h+var_F0]
0x140024d83  call    cs:__imp_NdisGetThreadObjectCompartmentScope
0x140024d8a  nop     dword ptr [rax+rax+00h]
0x140024d8f  mov     edx, dword ptr [rsp+150h+var_F0]
0x140024d93  mov     rcx, cs:WPP_GLOBAL_Control
0x140024d9a  cmp     rcx, r12
0x140024d9d  jz      short loc_140024DE4
0x140024d9f  cmp     byte ptr [rcx+29h], 5
0x140024da3  jb      short loc_140024DE4
0x140024da5  mov     eax, [rcx+2Ch]
0x140024da8  test    al, 10h
0x140024daa  jz      short loc_140024DE4
0x140024dac  mov     eax, dword ptr [rsp+150h+var_E8]
0x140024db0  lea     r9, aNsigetparamete; "NsiGetParameterEx"
0x140024db7  mov     rcx, [rcx+18h]
0x140024dbb  mov     [rsp+150h+var_100], edx
0x140024dbf  mov     [rsp+150h+var_108], eax
0x140024dc3  mov     qword ptr [rsp+150h+var_110], 0
0x140024dcc  mov     dword ptr [rsp+150h+var_118], esi
0x140024dd0  mov     [rsp+150h+var_120], r14d
0x140024dd5  mov     [rsp+150h+var_128], r15d
0x140024dda  mov     [rsp+150h+var_130], rbx
0x140024ddf  call    WPP_SF_s_guid_dddqdd
0x140024de4  mov     r9d, [rdi+20h]
0x140024de8  mov     [rsp+150h+arg_10], r13
0x140024df0  cmp     r9d, 3
0x140024df4  ja      loc_14002551E
0x140024dfa  mov     r8d, [rdi+24h]
0x140024dfe  cmp     r8d, 2
0x140024e02  ja      loc_1400254FB
0x140024e08  cmp     r9d, 2
0x140024e0c  jnz     short loc_140024E4D
0x140024e0e  mov     rcx, cs:WPP_GLOBAL_Control
0x140024e15  cmp     rcx, r12
0x140024e18  jz      loc_14002554C
0x140024e1e  cmp     [rcx+29h], r9b
0x140024e22  jb      loc_14002554C
0x140024e28  mov     eax, [rcx+2Ch]
0x140024e2b  test    al, 10h
0x140024e2d  jz      loc_14002554C
0x140024e33  mov     edx, 10h
0x140024e38  mov     rcx, [rcx+18h]
0x140024e3c  lea     r8, WPP_b802283a6c2b3e3c6b570e68b8145ddd_Traceguids
0x140024e43  call    WPP_SF_
0x140024e48  jmp     loc_14002554C
0x140024e4d  mov     r8d, [rdi+38h]
0x140024e51  cmp     r8d, 2
0x140024e55  ja      loc_1400254D8
0x140024e5b  cmp     qword ptr [rdi], 0
0x140024e5f  jz      short loc_140024E99
0x140024e61  mov     rcx, cs:WPP_GLOBAL_Control
0x140024e68  cmp     rcx, r12
0x140024e6b  jz      short loc_140024E8F
0x140024e6d  cmp     byte ptr [rcx+29h], 2
0x140024e71  jb      short loc_140024E8F
0x140024e73  mov     eax, [rcx+2Ch]
0x140024e76  test    al, 10h
0x140024e78  jz      short loc_140024E8F
0x140024e7a  mov     rcx, [rcx+18h]
0x140024e7e  lea     r8, WPP_b802283a6c2b3e3c6b570e68b8145ddd_Traceguids
0x140024e85  mov     edx, 12h
0x140024e8a  call    WPP_SF_
0x140024e8f  mov     ebx, 0C0000002h
0x140024e94  jmp     loc_140025551
0x140024e99  mov     eax, [rdi+48h]
0x140024e9c  lea     r14, [rdi+48h]
0x140024ea0  mov     ecx, [rdi+4Ch]
0x140024ea3  add     rcx, rax
0x140024ea6  mov     eax, 0FFFFFFFFh
0x140024eab  cmp     rcx, rax
0x140024eae  jbe     short loc_140024EDF
0x140024eb0  mov     rcx, cs:WPP_GLOBAL_Control
0x140024eb7  cmp     rcx, r12
0x140024eba  jz      loc_14002554C
0x140024ec0  cmp     byte ptr [rcx+29h], 2
0x140024ec4  jb      loc_14002554C
0x140024eca  mov     eax, [rcx+2Ch]
0x140024ecd  test    al, 10h
0x140024ecf  jz      loc_14002554C
0x140024ed5  mov     edx, 13h
0x140024eda  jmp     loc_140024E38
0x140024edf  xor     r13d, r13d
0x140024ee2  test    r9d, r9d
0x140024ee5  jz      short loc_140024EF3
0x140024ee7  lea     rcx, [rdi+8]
0x140024eeb  call    NsipGetNmpContext
0x140024ef0  mov     r13, rax
0x140024ef3  mov     ecx, [rdi+20h]
0x140024ef6  test    ecx, ecx
0x140024ef8  jz      loc_140025421
0x140024efe  cmp     ecx, 3
0x140024f01  jnz     loc_140024F98
0x140024f07  test    r13, r13
0x140024f0a  jz      loc_140025421
0x140024f10  xor     ebx, ebx
0x140024f12  call    cs:__imp_KeGetCurrentIrql
0x140024f19  nop     dword ptr [rax+rax+00h]
0x140024f1e  cmp     al, 2
0x140024f20  jnb     short loc_140024F36
0x140024f22  xor     r8d, r8d
0x140024f25  lea     rcx, [rdi+8]
0x140024f29  mov     dl, 1
0x140024f2b  call    NsipAccessCheck
0x140024f30  mov     ebx, eax
0x140024f32  test    eax, eax
0x140024f34  js      short loc_140024F82
0x140024f36  mov     rdx, [r13+30h]
0x140024f3a  mov     r8d, [rdi+18h]
0x140024f3e  mov     r9d, [rdx+4]
0x140024f42  cmp     r8d, r9d
0x140024f45  jb      short loc_140024FAB
0x140024f47  mov     rcx, cs:WPP_GLOBAL_Control
0x140024f4e  cmp     rcx, r12
0x140024f51  jz      short loc_140024F7D
0x140024f53  cmp     byte ptr [rcx+29h], 2
0x140024f57  jb      short loc_140024F7D
0x140024f59  mov     eax, [rcx+2Ch]
0x140024f5c  test    al, 10h
0x140024f5e  jz      short loc_140024F7D
0x140024f60  mov     dword ptr [rsp+150h+var_130], r9d
0x140024f65  mov     edx, 15h
0x140024f6a  mov     r9d, r8d
0x140024f6d  mov     rcx, [rcx+18h]
0x140024f71  lea     r8, WPP_b802283a6c2b3e3c6b570e68b8145ddd_Traceguids
0x140024f78  call    WPP_SF_Dd
0x140024f7d  mov     ebx, 0C000000Dh
0x140024f82  test    r13, r13
0x140024f85  jz      loc_140025551
0x140024f8b  mov     rcx, r13
0x140024f8e  call    NsipDereferenceNmpContext
0x140024f93  jmp     loc_140025551
0x140024f98  test    r13, r13
0x140024f9b  jnz     loc_140024F10
0x140024fa1  mov     ebx, 0C00000BBh
0x140024fa6  jmp     loc_140025551
0x140024fab  mov     r9d, [rdi+30h]
0x140024faf  imul    r15, r8, 68h ; 'h'
0x140024fb3  add     r15, [rdx+8]
0x140024fb7  mov     r8d, [r15]
0x140024fba  cmp     r8d, r9d
0x140024fbd  jnz     short loc_140024FCB
0x140024fbf  test    r9d, r9d
0x140024fc2  jz      short loc_140024FF3
0x140024fc4  cmp     qword ptr [rdi+28h], 0
0x140024fc9  jnz     short loc_140025030
0x140024fcb  mov     rcx, cs:WPP_GLOBAL_Control
0x140024fd2  cmp     rcx, r12
0x140024fd5  jz      short loc_140024F7D
0x140024fd7  cmp     byte ptr [rcx+29h], 2
0x140024fdb  jb      short loc_140024F7D
0x140024fdd  mov     eax, [rcx+2Ch]
0x140024fe0  test    al, 10h
0x140024fe2  jz      short loc_140024F7D
0x140024fe4  mov     edx, 16h
0x140024fe9  mov     dword ptr [rsp+150h+var_130], r8d
0x140024fee  jmp     loc_140024F6D
0x140024ff3  cmp     qword ptr [rdi+28h], 0
0x140024ff8  jz      short loc_140025030
0x140024ffa  mov     rcx, cs:WPP_GLOBAL_Control
0x140025001  cmp     rcx, r12
0x140025004  jz      short loc_140025028
0x140025006  cmp     byte ptr [rcx+29h], 3
0x14002500a  jb      short loc_140025028
0x14002500c  mov     eax, [rcx+2Ch]
0x14002500f  test    al, 10h
0x140025011  jz      short loc_140025028
0x140025013  mov     rcx, [rcx+18h]
0x140025017  lea     r8, WPP_b802283a6c2b3e3c6b570e68b8145ddd_Traceguids
0x14002501e  mov     edx, 17h
0x140025023  call    WPP_SF_
0x140025028  mov     qword ptr [rdi+28h], 0
0x140025030  cmp     qword ptr [rdi+40h], 0
0x140025035  jz      short loc_140025073
0x140025037  cmp     dword ptr [r14], 0
0x14002503b  jnz     short loc_140025073
0x14002503d  mov     rcx, cs:WPP_GLOBAL_Control
0x140025044  cmp     rcx, r12
0x140025047  jz      short loc_14002506B
0x140025049  cmp     byte ptr [rcx+29h], 3
0x14002504d  jb      short loc_14002506B
0x14002504f  mov     eax, [rcx+2Ch]
0x140025052  test    al, 10h
0x140025054  jz      short loc_14002506B
0x140025056  mov     rcx, [rcx+18h]
0x14002505a  lea     r8, WPP_b802283a6c2b3e3c6b570e68b8145ddd_Traceguids
0x140025061  mov     edx, 18h
0x140025066  call    WPP_SF_
0x14002506b  mov     qword ptr [rdi+40h], 0
0x140025073  cmp     qword ptr [r15+20h], 0
0x140025078  jz      short loc_1400250BE
0x14002507a  movups  xmm0, xmmword ptr [rdi+28h]
0x14002507e  mov     eax, [rdi+24h]
0x140025081  lea     rcx, [rbp+50h+var_80]
0x140025085  movups  xmm1, xmmword ptr [rdi+38h]
0x140025089  mov     dword ptr [rbp+50h+var_50+8], eax
0x14002508c  movaps  [rbp+50h+var_70], xmm0
0x140025090  movsd   xmm0, qword ptr [rdi+48h]
0x140025095  movsd   qword ptr [rbp+50h+var_50], xmm0
0x14002509a  movaps  [rbp+50h+var_60], xmm1
0x14002509e  mov     rax, [r13+28h]
0x1400250a2  mov     qword ptr [rbp+50h+var_80], rax
0x1400250a6  mov     rax, [r15+18h]
0x1400250aa  mov     qword ptr [rbp+50h+var_80+8], rax
0x1400250ae  mov     rax, [r15+20h]
0x1400250b2  call    _guard_dispatch_icall
0x1400250b7  mov     ebx, eax
0x1400250b9  jmp     loc_140024F82
0x1400250be  cmp     qword ptr [r15+30h], 0
0x1400250c3  jz      loc_1400253ED
0x1400250c9  mov     ecx, [rdi+38h]
0x1400250cc  xorps   xmm0, xmm0
0x1400250cf  xor     eax, eax
0x1400250d1  mov     [rbp+50h+var_90], rax
0x1400250d5  mov     eax, [rdi+24h]
0x1400250d8  movups  [rbp+50h+var_C0], xmm0
0x1400250dc  mov     dword ptr [rbp+50h+var_C0], eax
0x1400250df  movups  [rsp+150h+var_E8+8], xmm0
0x1400250e4  movups  [rbp+50h+var_B0], xmm0
0x1400250e8  movups  [rbp+50h+var_A0], xmm0
0x1400250ec  movups  xmm0, xmmword ptr [rdi+28h]
0x1400250f0  movaps  [rbp+50h+var_D0], xmm0
0x1400250f4  test    ecx, ecx
0x1400250f6  jz      short loc_140025122
0x1400250f8  sub     ecx, 1
0x1400250fb  jz      short loc_140025114
0x1400250fd  cmp     ecx, 1
0x140025100  jnz     loc_140024F7D
0x140025106  mov     edx, [r15+0Ch]
0x14002510a  lea     rax, [rbp+50h+var_A0+8]
0x14002510e  lea     r12, [rbp+50h+var_90]
0x140025112  jmp     short loc_14002512E
0x140025114  mov     edx, [r15+8]
0x140025118  lea     rax, [rbp+50h+var_B0+8]
0x14002511c  lea     r12, [rbp+50h+var_A0]
0x140025120  jmp     short loc_14002512E
0x140025122  mov     edx, [r15+4]
0x140025126  lea     rax, [rbp+50h+var_C0+8]
0x14002512a  lea     r12, [rbp+50h+var_B0]
0x14002512e  mov     qword ptr [rsp+150h+var_E8], rax
0x140025133  test    edx, edx
0x140025135  jnz     short loc_140025182
0x140025137  mov     ebx, 0C00000BBh
0x14002513c  mov     rcx, cs:WPP_GLOBAL_Control
0x140025143  lea     r12, WPP_GLOBAL_Control
0x14002514a  cmp     rcx, r12
0x14002514d  jz      loc_140024F82
0x140025153  cmp     byte ptr [rcx+29h], 2
0x140025157  jb      loc_140024F82
0x14002515d  mov     eax, [rcx+2Ch]
0x140025160  test    al, 10h
0x140025162  jz      loc_140024F82
0x140025168  mov     edx, 19h
0x14002516d  mov     rcx, [rcx+18h]
0x140025171  lea     r8, WPP_b802283a6c2b3e3c6b570e68b8145ddd_Traceguids
  ... truncated ...
```
