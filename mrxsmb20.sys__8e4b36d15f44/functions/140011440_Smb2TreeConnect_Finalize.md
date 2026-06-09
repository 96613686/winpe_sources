# Smb2TreeConnect_Finalize

- ea: `0x140011440`
- end: `0x140011c79`
- name: `Smb2TreeConnect_Finalize`
- size: `2105`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x14000fa00`
- `0x140011440`
- `0x140011c80`
- `0x1400122d0`
- `0x1400283b0`
- `0x140029764`
- `0x1400297a8`
- `0x140029894`
- `0x140037120`
- `0x140037240`

## import_xrefs

- `ntoskrnl!ExUuidCreate` at `0x140011763`
- `ntoskrnl!ExUuidCreate` at `0x140011763`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140011a05`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140011a05`
- `ntoskrnl!KeGetCurrentIrql` at `0x140011495`
- `ntoskrnl!KeGetCurrentIrql` at `0x140011495`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x1400118dc`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x1400118dc`
- `rdbss!RxDispatchToWorkerThread` at `0x140011698`
- `rdbss!RxDispatchToWorkerThread` at `0x140011698`
- `mrxsmb!SmbCseFinalizeBufferContext` at `0x1400115e4`
- `mrxsmb!SmbCseFinalizeBufferContext` at `0x1400115e4`
- `mrxsmb!SmbCeDereferenceVNetRootContext` at `0x1400116b1`
- `mrxsmb!SmbCeDereferenceVNetRootContext` at `0x1400116b1`
- `mrxsmb!SmbCeReferenceVNetRootContext` at `0x140011678`
- `mrxsmb!SmbCeReferenceVNetRootContext` at `0x140011678`
- `mrxsmb!SmbCeSetConnectionKeepalive` at `0x140011619`
- `mrxsmb!SmbCeSetConnectionKeepalive` at `0x140011c3e`
- `mrxsmb!SmbCeSetConnectionKeepalive` at `0x140011c68`
- `mrxsmb!SmbCeSetConnectionKeepalive` at `0x140011619`
- `mrxsmb!SmbCeSetConnectionKeepalive` at `0x140011c3e`
- `mrxsmb!SmbCeSetConnectionKeepalive` at `0x140011c68`
- `mrxsmb!MRxSmbProcessClientMoveNotification` at `0x140011bf9`
- `mrxsmb!MRxSmbProcessClientMoveNotification` at `0x140011bf9`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140011602`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14001162a`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140011afe`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140011602`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14001162a`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140011afe`
- `mrxsmb!SmbCeCheckServerEntryDialect` at `0x140011aae`
- `mrxsmb!SmbCeCheckServerEntryDialect` at `0x140011aae`
- `mrxsmb!SmbCeDisconnectServerConnections` at `0x14003a924`
- `mrxsmb!SmbCeDisconnectServerConnections` at `0x14003a924`

## pseudocode

```c
__int64 __fastcall Smb2TreeConnect_Finalize(__int64 a1)
{
  __int64 v1; // rbp
  __int64 v3; // rbx
  __int64 v4; // r14
  __int64 v5; // r15
  __int64 v6; // r12
  __int64 v7; // r13
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  _QWORD *v11; // rsi
  _QWORD *v12; // rcx
  __int64 v13; // rax
  PDEVICE_OBJECT *v14; // r8
  __int64 v15; // rdx
  __int64 v16; // rcx
  unsigned int v17; // r14d
  __int64 v18; // rcx
  _QWORD *v19; // rcx
  _QWORD *v20; // rdi
  __int64 result; // rax
  _QWORD *v22; // rdx
  _QWORD *v23; // rcx
  __int64 v24; // rdx
  int v25; // eax
  signed __int32 v26; // edx
  char v27; // al
  __int64 v28; // rcx
  KIRQL v29; // r9
  __int64 v30; // r10
  int v31; // ecx
  char v32; // al
  char v33; // cl
  char v34; // cl
  volatile LONG *p_SecurityDescriptor; // rcx
  KIRQL v36; // al
  unsigned int v37; // edx
  unsigned int v38; // ecx
  __int64 v39; // r9
  _QWORD *v40; // rbx
  __int64 v41; // rcx
  PVOID v42; // rax
  __int64 v43; // r10
  unsigned int v44; // r11d
  char v45; // al
  __int64 ConfigurationBlock; // rax
  int v47; // ecx
  int v48; // eax
  unsigned int v49; // eax
  unsigned int v50; // eax
  __int64 v51; // rdx
  KIRQL v52; // [rsp+30h] [rbp-78h]
  unsigned int v53; // [rsp+34h] [rbp-74h] BYREF
  __int64 v54; // [rsp+38h] [rbp-70h]
  PRDBSS_DEVICE_OBJECT pMRxDeviceObject; // [rsp+40h] [rbp-68h]
  UUID Uuid; // [rsp+48h] [rbp-60h] BYREF

  v1 = *(_QWORD *)(a1 + 88);
  v3 = *(_QWORD *)(a1 + 16);
  v4 = *(_QWORD *)(a1 + 3800);
  v54 = v3;
  v5 = *(_QWORD *)(v1 + 416);
  v6 = *(_QWORD *)(v1 + 424);
  v7 = *(_QWORD *)(v5 + 384);
  pMRxDeviceObject = *(PRDBSS_DEVICE_OBJECT *)(v7 + 24);
  KeGetCurrentIrql();
  v11 = (_QWORD *)(a1 + 160);
  v12 = *(_QWORD **)(a1 + 160);
  if ( v12 == (_QWORD *)(a1 + 160) )
    v13 = 0;
  else
    v13 = *(_QWORD *)(a1 + 168) - 8LL;
  if ( *(int *)(a1 + 16) >= 0 && v13 )
  {
    v3 = *(_QWORD *)(v13 + 48);
    v54 = v3;
  }
  if ( (int)v3 >= 0 )
  {
    v36 = SmbCeAcquireSpinLock(pMRxDeviceObject, v8, v9, v10);
    v37 = *(_DWORD *)(a1 + 3818);
    v52 = v36;
    v38 = (v37 >> 2) & 2;
    if ( (v37 & 0x40) != 0 )
      v38 = (v37 >> 2) & 2 | 0x40;
    v53 = v38;
    if ( (v37 & 0x10) != 0 )
    {
      v38 |= 0x80u;
      v53 = v38;
    }
    if ( (v37 & 0x20) != 0 )
    {
      v38 |= 0x100u;
      v53 = v38;
    }
    if ( (v37 & 0x80u) != 0
      && (*(_QWORD *)&Uuid.Data1 = v6 + 88,
          v45 = SmbCeCheckServerEntryDialect(*(_QWORD *)(v6 + 88), 3, 0, 2),
          v38 = v53,
          v45) )
    {
      v38 = v53 | 0x200;
    }
    else
    {
      *(_QWORD *)&Uuid.Data1 = v6 + 88;
    }
    *(_DWORD *)(v6 + 176) = v38;
    if ( *(_BYTE *)(a1 + 3808) && ((*(_DWORD *)(a1 + 3818) & 0x100) != 0 || dbgForceSynchronousRedirect) )
    {
      *(_BYTE *)(v6 + 189) = 1;
      *(_BYTE *)(v7 + 737) |= 0x80u;
    }
    *(_DWORD *)(v6 + 184) = *(_DWORD *)(a1 + 3814) & 0x1B4FF33;
    *(_DWORD *)(v6 + 180) = Smb2TranslateShareFlags(*(unsigned int *)(a1 + 3814));
    if ( (*(_DWORD *)(v6 + 176) & 0x80u) != 0
      && (ConfigurationBlock = MRxSmbGetConfigurationBlock(v28),
          v29 = v52,
          v30 = *(_QWORD *)&Uuid.Data1,
          *(_BYTE *)(ConfigurationBlock + 237) != 1)
      || *(_QWORD *)(*(_QWORD *)v30 + 520LL) )
    {
      *(_DWORD *)(v6 + 180) = *(_DWORD *)(v6 + 180) & 0xFFFCFFF3 | 0xC;
    }
    v31 = *(unsigned __int8 *)(a1 + 3812);
    if ( v31 == 1 )
    {
      v32 = 0;
    }
    else
    {
      v47 = v31 - 2;
      if ( v47 )
      {
        if ( v47 == 1 )
          v32 = 3;
        else
          v32 = 4;
      }
      else
      {
        v32 = 1;
      }
    }
    *(_BYTE *)(v6 + 188) = v32;
    if ( dbgForceAsymmetricClusterShare && !*(_BYTE *)(v6 + 188) )
      *(_DWORD *)(v6 + 176) |= 0x240u;
    if ( dbgForceAsymmetricShare )
    {
      v48 = *(_DWORD *)(v6 + 176);
      if ( (v48 & 0x40) != 0 )
        *(_DWORD *)(v6 + 176) = v48 | 0x200;
    }
    if ( (*(_DWORD *)(v6 + 176) & 0x80u) != 0 )
    {
      *(_BYTE *)(*(_QWORD *)v30 + 737LL) |= 3u;
    }
    else if ( !*(_BYTE *)(v6 + 188) )
    {
      v33 = *(_BYTE *)(*(_QWORD *)v30 + 737LL);
      if ( (v33 & 3) != 3 )
        *(_BYTE *)(*(_QWORD *)v30 + 737LL) = v33 & 0xFC | 2;
    }
    if ( (*(_DWORD *)(v6 + 176) & 0x100) != 0 )
    {
      *(_BYTE *)(*(_QWORD *)v30 + 737LL) |= 0xCu;
    }
    else if ( !*(_BYTE *)(v6 + 188) )
    {
      v34 = *(_BYTE *)(*(_QWORD *)v30 + 737LL);
      if ( (v34 & 0xC) != 0xC )
        *(_BYTE *)(*(_QWORD *)v30 + 737LL) = v34 & 0xF3 | 8;
    }
    _InterlockedExchange((volatile __int32 *)(*(_QWORD *)(v1 + 424) + 12LL), 0);
    p_SecurityDescriptor = (volatile LONG *)&pMRxDeviceObject[1].SecurityDescriptor;
    LODWORD(pMRxDeviceObject[1].RxNetNameTableInDeviceObject.TableLock.SystemResourcesList.Flink) = -1;
    ExReleaseSpinLockExclusive(p_SecurityDescriptor, v29);
    *(_DWORD *)(v1 + 676) = 0;
    if ( !*(_BYTE *)(v6 + 188) )
      *(_DWORD *)(v7 + 760) = 0;
    goto LABEL_12;
  }
  v14 = &WPP_GLOBAL_Control;
  v15 = 1;
  if ( !*(_BYTE *)(a1 + 3808) || (_DWORD)v3 != -1073741620 )
    goto LABEL_6;
  v39 = 0;
  *(_QWORD *)&Uuid.Data1 = 0;
  v53 = 0;
  if ( v12 == v11 )
    v40 = 0;
  else
    v40 = v12 - 1;
  v41 = v40[94];
  if ( !v41 )
    goto LABEL_131;
  if ( (*(_BYTE *)(v41 + 10) & 5) != 0 )
    v42 = *(PVOID *)(v41 + 24);
  else
    v42 = MmMapLockedPagesSpecifyCache((PMDL)v41, 0, MmCached, 0, 0, 0x40000010u);
  if ( (int)Smb2QueryErrorDataFromResponse((__int64)v42, *(_DWORD *)(v40[94] + 40LL), 1919177299, &Uuid, &v53) >= 0 )
  {
    v39 = v53;
    if ( v53 < 0x18 )
    {
      v15 = 1;
LABEL_131:
      v14 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_bbbb5ecce09d378367c344661863d2d2_Traceguids, v39);
        v15 = 1;
        v14 = &WPP_GLOBAL_Control;
      }
      LODWORD(v3) = -1073741620;
      goto LABEL_9;
    }
    v43 = *(_QWORD *)&Uuid.Data1;
    v44 = *(_DWORD *)(*(_QWORD *)&Uuid.Data1 + 8LL);
    v53 = *(_DWORD *)(*(_QWORD *)&Uuid.Data1 + 12LL);
    if ( v44 + v53 >= v44 )
    {
      LODWORD(v3) = 0;
      if ( (unsigned int)v39 >= v44 + v53 )
      {
        v14 = (PDEVICE_OBJECT *)*(unsigned int *)(*(_QWORD *)&Uuid.Data1 + 20LL);
        v49 = 24 * (_DWORD)v14;
        if ( (unsigned __int64)(24LL * (_QWORD)v14) > 0xFFFFFFFF || v49 + 24 < v49 || (unsigned int)v39 < v49 + 24 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_DD(
              WPP_GLOBAL_Control->AttachedDevice,
              16,
              WPP_bbbb5ecce09d378367c344661863d2d2_Traceguids,
              (unsigned int)v14,
              v39);
          }
        }
        else
        {
          *(_BYTE *)(v6 + 189) = 1;
          *(_BYTE *)(v7 + 737) |= 0x80u;
          MRxSmbProcessClientMoveNotification(v43, v7, v6 + 96);
        }
        goto LABEL_12;
      }
    }
    else
    {
      LODWORD(v3) = -1073741675;
    }
    v14 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_DD(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_bbbb5ecce09d378367c344661863d2d2_Traceguids, v44, v53);
      v14 = &WPP_GLOBAL_Control;
    }
    v15 = 1;
LABEL_6:
    if ( (_DWORD)v3 != -1073741623 && (_DWORD)v3 != -1073741620 && (_DWORD)v3 != -1067646975 )
      goto LABEL_12;
    goto LABEL_9;
  }
  LODWORD(v3) = -1073741620;
  v14 = &WPP_GLOBAL_Control;
  v15 = 1;
LABEL_9:
  if ( *(_DWORD *)(a1 + 104) == *(_DWORD *)(v7 + 392) )
  {
    v26 = _InterlockedExchangeAdd((volatile signed __int32 *)(v7 + 760), 1u);
    ++*(_DWORD *)(v1 + 676);
    v15 = (unsigned int)(v26 + 1);
    if ( (_DWORD)v3 == -1067646975 )
    {
      *(_WORD *)(v7 + 740) = *(_WORD *)(a1 + 1024);
      Uuid = 0;
      LODWORD(v3) = -1073741620;
      if ( ExUuidCreate(&Uuid) < 0 )
      {
        *(_QWORD *)&Uuid.Data1 = MEMORY[0xFFFFF78000000320];
        *(_QWORD *)Uuid.Data4 = v7;
      }
      *(UUID *)(v7 + 684) = Uuid;
    }
    else
    {
      if ( (int)v15 < 2 )
        goto LABEL_12;
      if ( (*(_DWORD *)(v6 + 176) & 0x100) != 0 )
      {
        if ( *(_DWORD *)(v1 + 676) >= 6u )
          goto LABEL_12;
      }
      else
      {
        v27 = *(_BYTE *)(v7 + 737) & 0xC;
        if ( v27 != 12 && v27 != 4
          || (unsigned int)Smb2GetServerActiveHandleCount(v7, v15, &WPP_GLOBAL_Control)
          || *(_DWORD *)(v1 + 676) >= 6u )
        {
          goto LABEL_12;
        }
      }
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qZd(
        WPP_GLOBAL_Control->AttachedDevice,
        17,
        (unsigned int)WPP_bbbb5ecce09d378367c344661863d2d2_Traceguids,
        v7,
        v7 + 80,
        (*(_BYTE *)(v7 + 737) >> 2) & 3);
    }
    LODWORD(v54) = v3;
    SmbCeDisconnectServerConnections(v7, 0, 0, 0, v54, 5);
  }
  if ( (_DWORD)v3 == -1067646975 )
    LODWORD(v3) = -1073741620;
LABEL_12:
  *(_DWORD *)(v4 + 12) = HIDWORD(v54);
  *(_DWORD *)(v4 + 8) = v3;
  (*(void (__fastcall **)(__int64, __int64, PDEVICE_OBJECT *))v4)(v4, v15, v14);
  if ( *(_DWORD *)(v5 + 432) )
  {
    v24 = *(unsigned int *)(v7 + 776);
    if ( !(_DWORD)v24 )
      v24 = *(_DWORD *)(MRxSmbGetConfigurationBlock(v16) + 12) >> 1;
    SmbCeSetConnectionKeepalive(v5, v24, 0);
  }
  v17 = 10;
  if ( *(_DWORD *)(v5 + 704)
    || (v18 = *(unsigned __int8 *)(*(_QWORD *)(a1 + 72) + 737LL), LOBYTE(v18) = v18 & 3, (_BYTE)v18 == 3) )
  {
    v50 = *(_DWORD *)(v7 + 772);
    v51 = 10;
    if ( v50 )
      v51 = v50;
    SmbCeSetConnectionKeepalive(v5, v51, 2);
  }
  if ( *(char *)(v7 + 764) < 0 )
  {
    if ( *(_DWORD *)(v7 + 780) )
      v17 = *(_DWORD *)(v7 + 780);
    SmbCeSetConnectionKeepalive(v5, v17, 3);
  }
  if ( (int)v3 >= 0 && !*(_BYTE *)(MRxSmbGetConfigurationBlock(v18) + 234) )
  {
    v25 = *(_DWORD *)(v7 + 716);
    if ( (v25 & 0x1000) != 0 && (v25 & 0x80u) == 0 && (*(_BYTE *)(v5 + 4) & 3) == 0 && !*(_QWORD *)(v7 + 576) )
    {
      SmbCeReferenceVNetRootContext(v1);
      LODWORD(v3) = RxDispatchToWorkerThread(pMRxDeviceObject, NormalWorkQueue, MRxSmb2UpdateConnectionInfo, (PVOID)v1);
      if ( (_DWORD)v3 )
        SmbCeDereferenceVNetRootContext(v1);
    }
  }
  v19 = (_QWORD *)*v11;
  if ( (_QWORD *)*v11 == v11 )
    return (unsigned int)v3;
  v20 = v19 - 1;
  if ( v19 == (_QWORD *)8 )
    return (unsigned int)v3;
  do
  {
    v22 = (_QWORD *)v20[1];
    v23 = v20;
    v20 = 0;
    if ( v22 != v11 )
      v20 = v22 - 1;
    result = SmbCseFinalizeBufferContext(v23);
  }
  while ( v20 );
  return result;
}

```

## disassembly

```asm
0x140011440  push    rbx
0x140011442  push    rbp
0x140011443  push    rsi
0x140011444  push    rdi
0x140011445  push    r12
0x140011447  push    r13
0x140011449  push    r14
0x14001144b  push    r15
0x14001144d  sub     rsp, 68h
0x140011451  mov     rax, cs:__security_cookie
0x140011458  xor     rax, rsp
0x14001145b  mov     [rsp+0A8h+var_50], rax
0x140011460  mov     rbp, [rcx+58h]
0x140011464  mov     rdi, rcx
0x140011467  mov     rbx, [rcx+10h]
0x14001146b  mov     r14, [rcx+0ED8h]
0x140011472  mov     [rsp+0A8h+var_70], rbx
0x140011477  mov     r15, [rbp+1A0h]
0x14001147e  mov     r12, [rbp+1A8h]
0x140011485  mov     r13, [r15+180h]
0x14001148c  mov     rax, [r13+18h]
0x140011490  mov     [rsp+0A8h+pMRxDeviceObject], rax
0x140011495  call    cs:__imp_KeGetCurrentIrql
0x14001149c  nop     dword ptr [rax+rax+00h]
0x1400114a1  lea     rsi, [rdi+0A0h]
0x1400114a8  mov     rcx, [rsi]
0x1400114ab  cmp     rcx, rsi
0x1400114ae  jz      loc_14001173B
0x1400114b4  mov     rax, [rdi+0A8h]
0x1400114bb  sub     rax, 8
0x1400114bf  cmp     dword ptr [rdi+10h], 0
0x1400114c3  jge     loc_1400115B8
0x1400114c9  test    ebx, ebx
0x1400114cb  jns     loc_140011925
0x1400114d1  cmp     byte ptr [rdi+0EE0h], 0
0x1400114d8  lea     r8, WPP_GLOBAL_Control
0x1400114df  mov     edx, 1
0x1400114e4  jnz     loc_140011B99
0x1400114ea  cmp     ebx, 0C00000C9h
0x1400114f0  jz      short loc_140011503
0x1400114f2  mov     eax, ebx
0x1400114f4  cmp     ebx, 0C00000CCh
0x1400114fa  jz      short loc_140011503
0x1400114fc  cmp     eax, 0C05D0001h
0x140011501  jnz     short loc_140011520
0x140011503  mov     eax, [r13+188h]
0x14001150a  cmp     [rdi+68h], eax
0x14001150d  jz      loc_1400116C2
0x140011513  cmp     ebx, 0C05D0001h
0x140011519  jnz     short loc_140011520
0x14001151b  mov     ebx, 0C00000CCh
0x140011520  mov     eax, dword ptr [rsp+0A8h+var_70+4]
0x140011524  mov     rcx, r14
0x140011527  mov     [r14+0Ch], eax
0x14001152b  mov     [r14+8], ebx
0x14001152f  mov     rax, [r14]
0x140011532  call    _guard_dispatch_icall
0x140011537  cmp     dword ptr [r15+1B0h], 0
0x14001153f  ja      loc_1400115F7
0x140011545  cmp     dword ptr [r15+2C0h], 0
0x14001154d  mov     r14d, 0Ah
0x140011553  ja      loc_140011C26
0x140011559  mov     rax, [rdi+48h]
0x14001155d  movzx   ecx, byte ptr [rax+2E1h]
0x140011564  and     cl, 3
0x140011567  cmp     cl, 3
0x14001156a  jz      loc_140011C26
0x140011570  cmp     byte ptr [r13+2FCh], 0
0x140011578  jl      loc_140011C4F
0x14001157e  test    ebx, ebx
0x140011580  jns     loc_14001162A
0x140011586  mov     rcx, [rsi]
0x140011589  cmp     rcx, rsi
0x14001158c  jz      short loc_140011597
0x14001158e  lea     rdi, [rcx-8]
0x140011592  test    rdi, rdi
0x140011595  jnz     short loc_1400115D0
0x140011597  mov     eax, ebx
0x140011599  mov     rcx, [rsp+0A8h+var_50]
0x14001159e  xor     rcx, rsp; StackCookie
0x1400115a1  call    __security_check_cookie
0x1400115a6  add     rsp, 68h
0x1400115aa  pop     r15
0x1400115ac  pop     r14
0x1400115ae  pop     r13
0x1400115b0  pop     r12
0x1400115b2  pop     rdi
0x1400115b3  pop     rsi
0x1400115b4  pop     rbp
0x1400115b5  pop     rbx
0x1400115b6  retn
0x1400115b8  test    rax, rax
0x1400115bb  jz      loc_1400114C9
0x1400115c1  mov     rbx, [rax+30h]
0x1400115c5  mov     [rsp+0A8h+var_70], rbx
0x1400115ca  jmp     loc_1400114C9
0x1400115d0  mov     rdx, [rdi+8]
0x1400115d4  mov     rcx, rdi
0x1400115d7  xor     edi, edi
0x1400115d9  cmp     rdx, rsi
0x1400115dc  lea     rax, [rdx-8]
0x1400115e0  cmovnz  rdi, rax
0x1400115e4  call    cs:__imp_SmbCseFinalizeBufferContext
0x1400115eb  nop     dword ptr [rax+rax+00h]
0x1400115f0  test    rdi, rdi
0x1400115f3  jz      short loc_140011599
0x1400115f5  jmp     short loc_1400115D0
0x1400115f7  mov     edx, [r13+308h]
0x1400115fe  test    edx, edx
0x140011600  jnz     short loc_140011613
0x140011602  call    cs:__imp_MRxSmbGetConfigurationBlock
0x140011609  nop     dword ptr [rax+rax+00h]
0x14001160e  mov     edx, [rax+0Ch]
0x140011611  shr     edx, 1
0x140011613  xor     r8d, r8d
0x140011616  mov     rcx, r15
0x140011619  call    cs:__imp_SmbCeSetConnectionKeepalive
0x140011620  nop     dword ptr [rax+rax+00h]
0x140011625  jmp     loc_140011545
0x14001162a  call    cs:__imp_MRxSmbGetConfigurationBlock
0x140011631  nop     dword ptr [rax+rax+00h]
0x140011636  cmp     byte ptr [rax+0EAh], 0
0x14001163d  jnz     loc_140011586
0x140011643  mov     eax, [r13+2CCh]
0x14001164a  bt      eax, 0Ch
0x14001164e  jnb     loc_140011586
0x140011654  test    al, al
0x140011656  js      loc_140011586
0x14001165c  test    byte ptr [r15+4], 3
0x140011661  jnz     loc_140011586
0x140011667  cmp     qword ptr [r13+240h], 0
0x14001166f  jnz     loc_140011586
0x140011675  mov     rcx, rbp
0x140011678  call    cs:__imp_SmbCeReferenceVNetRootContext
0x14001167f  nop     dword ptr [rax+rax+00h]
0x140011684  mov     rcx, [rsp+0A8h+pMRxDeviceObject]; pMRxDeviceObject
0x140011689  lea     r8, MRxSmb2UpdateConnectionInfo; Routine
0x140011690  mov     r9, rbp; pContext
0x140011693  mov     edx, 3; WorkQueueType
0x140011698  call    cs:__imp_RxDispatchToWorkerThread
0x14001169f  nop     dword ptr [rax+rax+00h]
0x1400116a4  mov     ebx, eax
0x1400116a6  test    eax, eax
0x1400116a8  jz      loc_140011586
0x1400116ae  mov     rcx, rbp
0x1400116b1  call    cs:__imp_SmbCeDereferenceVNetRootContext
0x1400116b8  nop     dword ptr [rax+rax+00h]
0x1400116bd  jmp     loc_140011586
0x1400116c2  lock xadd [r13+2F8h], edx
0x1400116cb  inc     dword ptr [rbp+2A4h]
0x1400116d1  inc     edx
0x1400116d3  mov     ecx, [rbp+2A4h]
0x1400116d9  cmp     ebx, 0C05D0001h
0x1400116df  jz      short loc_140011742
0x1400116e1  cmp     edx, 2
0x1400116e4  jl      loc_140011520
0x1400116ea  test    dword ptr [r12+0B0h], 100h
0x1400116f6  jnz     loc_140011790
0x1400116fc  movzx   eax, byte ptr [r13+2E1h]
0x140011704  and     al, 0Ch
0x140011706  cmp     al, 0Ch
0x140011708  jz      short loc_140011712
0x14001170a  cmp     al, 4
0x14001170c  jnz     loc_140011520
0x140011712  mov     rcx, r13
0x140011715  call    Smb2GetServerActiveHandleCount
0x14001171a  test    eax, eax
0x14001171c  jnz     loc_140011520
0x140011722  cmp     dword ptr [rbp+2A4h], 6
0x140011729  jnb     loc_140011520
0x14001172f  lea     r8, WPP_GLOBAL_Control
0x140011736  jmp     loc_14003A8B4
0x14001173b  xor     eax, eax
0x14001173d  jmp     loc_1400114BF
0x140011742  movzx   eax, word ptr [rdi+400h]
0x140011749  lea     rcx, [rsp+0A8h+Uuid]; Uuid
0x14001174e  xorps   xmm0, xmm0
0x140011751  mov     [r13+2E4h], ax
0x140011759  movups  xmmword ptr [rsp+0A8h+Uuid.Data1], xmm0
0x14001175e  mov     ebx, 0C00000CCh
0x140011763  call    cs:__imp_ExUuidCreate
0x14001176a  nop     dword ptr [rax+rax+00h]
0x14001176f  test    eax, eax
0x140011771  js      loc_140011C0A
0x140011777  movups  xmm0, xmmword ptr [rsp+0A8h+Uuid.Data1]
0x14001177c  lea     r8, WPP_GLOBAL_Control
0x140011783  movups  xmmword ptr [r13+2ACh], xmm0
0x14001178b  jmp     loc_14003A8B4
0x140011790  cmp     ecx, 6
0x140011793  jnb     loc_140011520
0x140011799  jmp     loc_14003A8B4
0x14001179e  test    dl, dl
0x1400117a0  js      loc_140011A93
0x1400117a6  lea     r10, [r12+58h]
0x1400117ab  mov     qword ptr [rsp+0A8h+Uuid.Data1], r10
0x1400117b0  mov     [r12+0B0h], ecx
0x1400117b8  cmp     byte ptr [rdi+0EE0h], 0
0x1400117bf  jnz     loc_140011ADA
0x1400117c5  mov     eax, [rdi+0EE6h]
0x1400117cb  and     eax, 1B4FF33h
0x1400117d0  mov     [r12+0B8h], eax
0x1400117d8  mov     ecx, [rdi+0EE6h]
0x1400117de  call    Smb2TranslateShareFlags
0x1400117e3  mov     [r12+0B4h], eax
0x1400117eb  mov     eax, [r12+0B0h]
0x1400117f3  test    al, al
0x1400117f5  js      loc_140011AFE
0x1400117fb  mov     rax, [r10]
0x1400117fe  cmp     qword ptr [rax+208h], 0
0x140011806  jnz     loc_140011B22
0x14001180c  movzx   ecx, byte ptr [rdi+0EE4h]
0x140011813  cmp     ecx, 1
0x140011816  jnz     loc_140011B3F
0x14001181c  xor     al, al
0x14001181e  mov     [r12+0BCh], al
0x140011826  movzx   eax, cs:dbgForceAsymmetricClusterShare
0x14001182d  test    al, al
0x14001182f  jnz     loc_140011B58
0x140011835  movzx   eax, cs:dbgForceAsymmetricShare
0x14001183c  test    al, al
0x14001183e  jnz     loc_140011B78
0x140011844  mov     eax, [r12+0B0h]
0x14001184c  test    al, al
0x14001184e  js      loc_140011916
0x140011854  cmp     byte ptr [r12+0BCh], 0
0x14001185d  jnz     short loc_14001187E
0x14001185f  mov     rdx, [r10]
0x140011862  movzx   ecx, byte ptr [rdx+2E1h]
0x140011869  movzx   eax, cl
0x14001186c  and     al, 3
0x14001186e  cmp     al, 3
0x140011870  jz      short loc_14001187E
0x140011872  and     cl, 0FEh
0x140011875  or      cl, 2
0x140011878  mov     [rdx+2E1h], cl
0x14001187e  test    dword ptr [r12+0B0h], 100h
0x14001188a  jnz     short loc_14001190A
0x14001188c  cmp     byte ptr [r12+0BCh], 0
0x140011895  jnz     short loc_1400118B6
0x140011897  mov     rdx, [r10]
0x14001189a  movzx   ecx, byte ptr [rdx+2E1h]
0x1400118a1  movzx   eax, cl
0x1400118a4  and     al, 0Ch
0x1400118a6  cmp     al, 0Ch
0x1400118a8  jz      short loc_1400118B6
0x1400118aa  and     cl, 0FBh
0x1400118ad  or      cl, 8
0x1400118b0  mov     [rdx+2E1h], cl
0x1400118b6  mov     rcx, [rbp+1A8h]
0x1400118bd  xor     eax, eax
0x1400118bf  movzx   edx, r9b; OldIrql
0x1400118c3  xchg    eax, [rcx+0Ch]
0x1400118c6  mov     rax, [rsp+0A8h+pMRxDeviceObject]
0x1400118cb  lea     rcx, [rax+780h]; SpinLock
0x1400118d2  mov     dword ptr [rax+930h], 0FFFFFFFFh
0x1400118dc  call    cs:__imp_ExReleaseSpinLockExclusive
0x1400118e3  nop     dword ptr [rax+rax+00h]
0x1400118e8  xor     eax, eax
0x1400118ea  mov     [rbp+2A4h], eax
0x1400118f0  cmp     [r12+0BCh], al
0x1400118f8  jnz     loc_140011520
0x1400118fe  mov     [r13+2F8h], eax
0x140011905  jmp     loc_140011520
0x14001190a  mov     rax, [r10]
0x14001190d  or      byte ptr [rax+2E1h], 0Ch
0x140011914  jmp     short loc_1400118B6
0x140011916  mov     rax, [r10]
0x140011919  or      byte ptr [rax+2E1h], 3
0x140011920  jmp     loc_14001187E
0x140011925  mov     rcx, [rsp+0A8h+pMRxDeviceObject]
0x14001192a  call    SmbCeAcquireSpinLock
0x14001192f  mov     edx, [rdi+0EEAh]
0x140011935  movzx   r9d, al
0x140011939  mov     [rsp+0A8h+var_78], al
0x14001193d  mov     ecx, edx
0x14001193f  shr     ecx, 2
0x140011942  and     ecx, 2
0x140011945  mov     eax, ecx
0x140011947  or      eax, 40h
0x14001194a  test    dl, 40h
0x14001194d  cmovnz  ecx, eax
0x140011950  mov     [rsp+0A8h+var_74], ecx
0x140011954  test    dl, 10h
0x140011957  jz      short loc_140011961
0x140011959  bts     ecx, 7
0x14001195d  mov     [rsp+0A8h+var_74], ecx
0x140011961  test    dl, 20h
0x140011964  jz      loc_14001179E
0x14001196a  bts     ecx, 8
0x14001196e  mov     [rsp+0A8h+var_74], ecx
0x140011972  jmp     loc_14001179E
0x140011977  xor     r9d, r9d; RequestedAddress
0x14001197a  mov     qword ptr [rsp+0A8h+Uuid.Data1], 0
0x140011983  mov     [rsp+0A8h+var_74], r9d
0x140011988  cmp     rcx, rsi
0x14001198b  jnz     short loc_1400119ED
0x14001198d  xor     ebx, ebx
0x14001198f  mov     rcx, [rbx+2F0h]; MemoryDescriptorList
0x140011996  test    rcx, rcx
0x140011999  jz      loc_14003A869
  ... truncated ...
```
