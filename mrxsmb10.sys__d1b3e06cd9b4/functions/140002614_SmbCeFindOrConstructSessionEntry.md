# SmbCeFindOrConstructSessionEntry

- ea: `0x140002614`
- end: `0x140003445`
- name: `SmbCeFindOrConstructSessionEntry`
- size: `3633`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000ce24`

## callees

- `0x140001e40`
- `0x140002470`
- `0x140002614`
- `0x140003e20`
- `0x140004030`
- `0x14000cbbc`
- `0x14000cda8`
- `0x14000dc44`
- `0x14000de4c`
- `0x14000dfd8`
- `0x14000e52c`
- `0x14000e694`
- `0x14000ed10`
- `0x140010768`
- `0x140011e1c`
- `0x1400166c0`
- `0x140028008`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x14000269d`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000269d`
- `ntoskrnl!LsaFreeReturnBuffer` at `0x1400029ef`
- `ntoskrnl!LsaFreeReturnBuffer` at `0x1400029ef`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002856`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400028ca`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002e2b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000330b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002856`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400028ca`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002e2b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000330b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002763`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002879`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002ddb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000327f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002763`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002879`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002ddb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000327f`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140002a5e`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140002ae6`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140002c00`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140002cf4`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140002d33`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140002a5e`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140002ae6`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140002c00`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140002cf4`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140002d33`
- `ntoskrnl!ExAllocatePool2` at `0x1400031c5`
- `ntoskrnl!ExAllocatePool2` at `0x1400031c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003366`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003366`
- `rdbss!RxCreateCredential` at `0x140003190`
- `rdbss!RxCreateCredential` at `0x140003190`
- `rdbss!RxDereferenceCredential` at `0x140003156`
- `rdbss!RxDereferenceCredential` at `0x140003156`
- `rdbss!RxCloneUnicodeStringNonPagedPool` at `0x14000302c`
- `rdbss!RxCloneUnicodeStringNonPagedPool` at `0x14000302c`
- `rdbss!RxReferenceCredential` at `0x140003118`
- `rdbss!RxReferenceCredential` at `0x140003118`
- `rdbss!RxDiagnosticTrace` at `0x1400033de`
- `rdbss!RxDiagnosticTrace` at `0x1400033de`
- `ksecdd!GetSecurityUserInfo` at `0x140002a21`
- `ksecdd!GetSecurityUserInfo` at `0x140002a21`
- `mrxsmb!MRxSmbBootedRemotely` at `0x140002668`
- `mrxsmb!MRxSmbBootedRemotely` at `0x140002978`
- `mrxsmb!MRxSmbBootedRemotely` at `0x14000313b`
- `mrxsmb!MRxSmbRemoteBootShare` at `0x140002692`
- `mrxsmb!MRxSmbRemoteBootMachineName` at `0x1400026b7`
- `mrxsmb!MRxSmbRemoteBootMachinePassword` at `0x1400026ad`
- `mrxsmb!MRxSmbRemoteBootMachineDomain` at `0x1400026be`

## pseudocode

```c
__int64 __fastcall SmbCeFindOrConstructSessionEntry(__int64 a1, __int64 a2, __int64 *a3)
{
  _QWORD *v3; // rax
  __int64 v6; // r12
  const UNICODE_STRING *v7; // rbx
  const UNICODE_STRING *v8; // rsi
  const UNICODE_STRING *v9; // r14
  int v10; // ebp
  __int64 v11; // rcx
  __int64 v12; // r15
  NTSTATUS SecurityUserInfo; // edi
  __int64 v14; // rbx
  __int64 SessionEntry; // rbx
  __int64 DefaultSessionEntry; // rax
  int v17; // eax
  int v18; // ecx
  bool v19; // zf
  __int64 v20; // rcx
  const UNICODE_STRING *v21; // rdx
  char v22; // r12
  __int64 v23; // r14
  __int64 v24; // rbx
  int v25; // ecx
  _QWORD *v26; // rbp
  const UNICODE_STRING *v27; // rsi
  const UNICODE_STRING *v28; // r14
  int v29; // ecx
  int v30; // ecx
  int v31; // ecx
  int v32; // ecx
  int v33; // ecx
  int v34; // ecx
  const UNICODE_STRING *v35; // rdx
  __int64 v36; // rax
  __int64 v37; // rsi
  KIRQL v38; // al
  __int64 v39; // rcx
  __int64 v40; // r8
  int v41; // ecx
  __int64 v42; // r8
  const UNICODE_STRING *v43; // r8
  int v44; // ecx
  __int64 v45; // rcx
  unsigned __int16 *v46; // rax
  void *Pool2; // rax
  KIRQL v48; // al
  _QWORD *v49; // r8
  __int64 v50; // rdx
  unsigned __int16 *v51; // rdx
  __int64 v53; // [rsp+28h] [rbp-90h]
  const UNICODE_STRING *v54; // [rsp+50h] [rbp-68h]
  const UNICODE_STRING *String1; // [rsp+58h] [rbp-60h]
  PVOID Buffer; // [rsp+60h] [rbp-58h] BYREF
  __int64 v57; // [rsp+68h] [rbp-50h]
  PVOID P; // [rsp+C8h] [rbp+10h] BYREF
  __int64 *v60; // [rsp+D0h] [rbp+18h]
  PCUNICODE_STRING v61; // [rsp+D8h] [rbp+20h]

  v60 = a3;
  v3 = *(_QWORD **)(a2 + 104);
  v6 = a1;
  if ( v3 )
  {
    v7 = (const UNICODE_STRING *)v3[2];
    v8 = (const UNICODE_STRING *)v3[3];
    v9 = (const UNICODE_STRING *)v3[4];
    v57 = v3[5];
  }
  else
  {
    v7 = 0;
    v57 = 0;
    v9 = 0;
    v8 = 0;
  }
  v61 = v8;
  v54 = v9;
  String1 = v7;
  if ( MRxSmbBootedRemotely
    && !RtlCompareUnicodeString(*(PCUNICODE_STRING *)(*(_QWORD *)(a2 + 32) + 88LL), MRxSmbRemoteBootShare, 1u) )
  {
    v8 = (const UNICODE_STRING *)MRxSmbRemoteBootMachinePassword;
    v10 = 4;
    v9 = (const UNICODE_STRING *)MRxSmbRemoteBootMachineDomain;
    String1 = (const UNICODE_STRING *)MRxSmbRemoteBootMachineName;
    v61 = (PCUNICODE_STRING)MRxSmbRemoteBootMachinePassword;
    v54 = (const UNICODE_STRING *)MRxSmbRemoteBootMachineDomain;
LABEL_17:
    LODWORD(P) = v10;
    goto LABEL_18;
  }
  if ( v7 )
  {
    if ( !v7->Length && v8 && !v8->Length && v9 && !v9->Length )
    {
      v10 = 3;
      goto LABEL_17;
    }
LABEL_16:
    v10 = 2;
    goto LABEL_17;
  }
  v10 = 1;
  LODWORD(P) = 1;
  if ( v8 && v8->Length )
    goto LABEL_16;
LABEL_18:
  v11 = *(_QWORD *)(a2 + 32);
  *a3 = 0;
  v12 = SmbCeReferenceAssociatedServerEntry(*(_QWORD *)(v11 + 32));
  if ( !v12 )
    return (unsigned int)-1073741811;
  SecurityUserInfo = 0;
  if ( v10 == 2 || !*(_DWORD *)(v12 + 432) )
  {
    v22 = 0;
    v23 = v12 + 168;
    s_SmbCeDbSpinLockSavedIrql = KeAcquireSpinLockRaiseToDpc(&s_SmbCeDbSpinLock);
    v24 = *(_QWORD *)(v12 + 168);
    if ( v24 == v12 + 168 )
    {
      SessionEntry = 0;
    }
    else
    {
      SessionEntry = v24 - 32;
      if ( SessionEntry )
      {
        MRxSmbTrackRefCount(SessionEntry, "SmbCeFindOrConstructSessionEntry", 1315);
        _InterlockedIncrement((volatile signed __int32 *)(SessionEntry + 8));
      }
    }
    KeReleaseSpinLock(&s_SmbCeDbSpinLock, s_SmbCeDbSpinLockSavedIrql);
    while ( 1 )
    {
      while ( 1 )
      {
        if ( !SessionEntry || v22 )
        {
          v10 = (int)P;
          v9 = v54;
          v6 = a1;
          goto LABEL_144;
        }
        if ( (*(_DWORD *)(SessionEntry + 136) & 0x4C) != 0 )
          goto LABEL_130;
        Buffer = 0;
        if ( *(_DWORD *)(v12 + 432) )
          break;
        v34 = *(_DWORD *)(a2 + 72);
        if ( (*(_DWORD *)(SessionEntry + 144) != v34 || *(_DWORD *)(SessionEntry + 148) != *(_DWORD *)(a2 + 76))
          && (*(_DWORD *)(SessionEntry + 152) != v34 || *(_DWORD *)(SessionEntry + 156) != *(_DWORD *)(a2 + 76)) )
        {
          goto LABEL_130;
        }
        v35 = *(const UNICODE_STRING **)(SessionEntry + 400);
        if ( !v35 || !RtlEqualUnicodeString(*(PCUNICODE_STRING *)(*(_QWORD *)(a2 + 32) + 88LL), v35, 0) )
          goto LABEL_130;
        if ( v8 )
        {
          v36 = *(_QWORD *)(SessionEntry + 176);
          if ( !v36 || (v21 = *(const UNICODE_STRING **)(v36 + 24)) == 0 || !RtlEqualUnicodeString(v8, v21, 0) )
          {
            SecurityUserInfo = -1073741419;
            v41 = (int)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
            {
              WPP_SF_qD(
                WPP_GLOBAL_Control->AttachedDevice,
                20,
                WPP_dc77a1bfe1f333f3a4c6c4eeb4778daa_Traceguids,
                SessionEntry,
                -1073741419);
            }
            v6 = a1;
            if ( (Microsoft_Windows_SMBClientEnableBits & 1) != 0 )
            {
              LODWORD(v53) = 0;
              McTemplateK0qqq_EtwWriteTransfer(v41, (unsigned int)SessionSetupError, a1 + 412, -1073741419, 202, v53);
            }
            v9 = v54;
            v10 = (int)P;
            goto LABEL_144;
          }
        }
        v22 = 1;
LABEL_122:
        if ( *(_DWORD *)(SessionEntry + 144) == 998 && !*(_DWORD *)(SessionEntry + 148) && (v8 || String1 || v54) )
        {
          SecurityUserInfo = -1073741419;
          if ( (Microsoft_Windows_SMBClientEnableBits & 1) != 0 )
          {
            LODWORD(v53) = 0;
            McTemplateK0qqq_EtwWriteTransfer(v29, (unsigned int)SessionSetupError, a1 + 412, -1073741419, 236, v53);
          }
        }
      }
      if ( *(_DWORD *)(SessionEntry + 160) != *(_DWORD *)(a2 + 88) )
        goto LABEL_130;
      v25 = *(_DWORD *)(a2 + 72);
      if ( *(_QWORD *)(SessionEntry + 144) != *(_QWORD *)(a2 + 72)
        && (*(_DWORD *)(SessionEntry + 152) != v25 || *(_DWORD *)(SessionEntry + 156) != *(_DWORD *)(a2 + 76)) )
      {
        goto LABEL_130;
      }
      v26 = *(_QWORD **)(SessionEntry + 176);
      if ( v26 )
      {
        v27 = (const UNICODE_STRING *)v26[2];
        v28 = (const UNICODE_STRING *)v26[4];
        if ( v27 && v28 )
          goto LABEL_79;
      }
      else
      {
        v28 = 0;
        v27 = 0;
      }
      if ( MRxSmbBootedRemotely )
      {
        if ( !String1 && !v54 || (SecurityUserInfo = -1073741419, (Microsoft_Windows_SMBClientEnableBits & 1) == 0) )
        {
          v23 = v12 + 168;
          goto LABEL_130;
        }
        LODWORD(v53) = 0;
        McTemplateK0qqq_EtwWriteTransfer(v25, (unsigned int)SessionSetupError, a1 + 412, -1073741419, 82, v53);
        goto LABEL_69;
      }
      SecurityUserInfo = GetSecurityUserInfo((PLUID)(a2 + 72), 1u, (PSecurityUserData *)&Buffer);
      if ( SecurityUserInfo < 0 )
        goto LABEL_69;
      if ( !v27 )
        v27 = (const UNICODE_STRING *)Buffer;
      if ( !v28 )
        v28 = (const UNICODE_STRING *)((char *)Buffer + 16);
LABEL_79:
      if ( String1 && !RtlEqualUnicodeString(String1, v27, 1u) )
      {
        SecurityUserInfo = -1073741419;
        v30 = (int)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
        {
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            16,
            WPP_dc77a1bfe1f333f3a4c6c4eeb4778daa_Traceguids,
            SessionEntry,
            -1073741419);
        }
        if ( (Microsoft_Windows_SMBClientEnableBits & 1) != 0 )
        {
          LODWORD(v53) = 0;
          McTemplateK0qqq_EtwWriteTransfer(v30, (unsigned int)SessionSetupError, a1 + 412, -1073741419, 111, v53);
        }
LABEL_69:
        v8 = v61;
        goto LABEL_70;
      }
      if ( v54 && !RtlEqualUnicodeString(v54, v28, 1u) )
      {
        SecurityUserInfo = -1073741419;
        v31 = (int)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
        {
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            17,
            WPP_dc77a1bfe1f333f3a4c6c4eeb4778daa_Traceguids,
            SessionEntry,
            -1073741419);
        }
        if ( (Microsoft_Windows_SMBClientEnableBits & 1) != 0 )
        {
          LODWORD(v53) = 0;
          McTemplateK0qqq_EtwWriteTransfer(v31, (unsigned int)SessionSetupError, a1 + 412, -1073741419, 120, v53);
        }
        goto LABEL_69;
      }
      v8 = v61;
      if ( !v61 )
      {
LABEL_110:
        v22 = 1;
        goto LABEL_70;
      }
      if ( !v26 || v26[3] )
      {
        if ( !v61->Length )
          goto LABEL_110;
        if ( !v26 )
          goto LABEL_110;
        v21 = (const UNICODE_STRING *)v26[3];
        if ( !v21 || RtlEqualUnicodeString(v61, v21, 0) )
          goto LABEL_110;
        SecurityUserInfo = -1073741419;
        v33 = (int)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
        {
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            19,
            WPP_dc77a1bfe1f333f3a4c6c4eeb4778daa_Traceguids,
            SessionEntry,
            -1073741419);
        }
        if ( (Microsoft_Windows_SMBClientEnableBits & 1) != 0 )
        {
          LODWORD(v53) = 0;
          McTemplateK0qqq_EtwWriteTransfer(v33, (unsigned int)SessionSetupError, a1 + 412, -1073741419, 156, v53);
        }
      }
      else
      {
        SecurityUserInfo = -1073741419;
        v32 = (int)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
        {
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            18,
            WPP_dc77a1bfe1f333f3a4c6c4eeb4778daa_Traceguids,
            SessionEntry,
            -1073741419);
        }
        if ( (Microsoft_Windows_SMBClientEnableBits & 1) != 0 )
        {
          LODWORD(v53) = 0;
          McTemplateK0qqq_EtwWriteTransfer(v32, (unsigned int)SessionSetupError, a1 + 412, -1073741419, 135, v53);
        }
      }
LABEL_70:
      v29 = (int)Buffer;
      if ( Buffer )
        LsaFreeReturnBuffer(Buffer);
      v23 = v12 + 168;
      if ( v22 )
        goto LABEL_122;
LABEL_130:
      v37 = SessionEntry;
      if ( SecurityUserInfo )
      {
        SessionEntry = 0;
        v40 = 1509;
      }
      else
      {
        v38 = KeAcquireSpinLockRaiseToDpc(&s_SmbCeDbSpinLock);
        v39 = *(_QWORD *)(SessionEntry + 32);
        s_SmbCeDbSpinLockSavedIrql = v38;
        SessionEntry = 0;
        if ( v39 != v23 )
          SessionEntry = v39 - 32;
        if ( SessionEntry )
        {
          MRxSmbTrackRefCount(SessionEntry, "SmbCeFindOrConstructSessionEntry", 1500);
          _InterlockedIncrement((volatile signed __int32 *)(SessionEntry + 8));
        }
        KeReleaseSpinLock(&s_SmbCeDbSpinLock, s_SmbCeDbSpinLockSavedIrql);
        v40 = 1504;
      }
      MRxSmbTrackDerefCount(v37, "SmbCeFindOrConstructSessionEntry", v40);
      SmbCepDereferenceSessionEntry(v37);
      v8 = v61;
    }
  }
  s_SmbCeDbSpinLockSavedIrql = KeAcquireSpinLockRaiseToDpc(&s_SmbCeDbSpinLock);
  if ( v10 == 1 )
  {
    while ( 1 )
    {
      DefaultSessionEntry = SmbCeGetDefaultSessionEntry(v12, a2 + 72);
      SessionEntry = DefaultSessionEntry;
      if ( !DefaultSessionEntry )
        break;
      if ( (*(_DWORD *)(DefaultSessionEntry + 136) & 0x40) == 0 )
        goto LABEL_44;
      SmbCeRemoveDefaultSessionEntry(DefaultSessionEntry);
    }
  }
  v14 = *(_QWORD *)(v12 + 168);
  if ( v14 == v12 + 168 )
  {
    SessionEntry = 0;
  }
  else
  {
    SessionEntry = v14 - 32;
    if ( SessionEntry )
    {
      do
      {
        v17 = *(_DWORD *)(SessionEntry + 136);
        if ( (v17 & 0x40) == 0 )
        {
          if ( v10 == 1 )
          {
            v18 = *(_DWORD *)(a2 + 72);
            if ( *(_DWORD *)(SessionEntry + 144) == v18 && *(_DWORD *)(SessionEntry + 148) == *(_DWORD *)(a2 + 76)
              || *(_DWORD *)(SessionEntry + 152) == v18 && *(_DWORD *)(SessionEntry + 156) == *(_DWORD *)(a2 + 76) )
            {
              break;
            }
          }
          else
          {
            if ( v10 == 3 )
              v19 = (v17 & 4) == 0;
            else
              v19 = (v17 & 8) == 0;
            if ( !v19 )
              break;
          }
        }
        v20 = *(_QWORD *)(SessionEntry + 32);
        SessionEntry = 0;
        if ( v20 != v12 + 168 )
          SessionEntry = v20 - 32;
      }
      while ( SessionEntry );
      if ( SessionEntry )
      {
LABEL_44:
        MRxSmbTrackRefCount(SessionEntry, "SmbCeFindOrConstructSessionEntry", 1305);
        _InterlockedIncrement((volatile signed __int32 *)(SessionEntry + 8));
      }
    }
  }
  KeReleaseSpinLock(&s_SmbCeDbSpinLock, s_SmbCeDbSpinLockSavedIrql);
  v8 = v61;
LABEL_144:
  if ( !Win9xSessionRestriction )
  {
    if ( !SessionEntry )
    {
      if ( !SecurityUserInfo )
        goto LABEL_164;
      goto LABEL_210;
    }
LABEL_205:
    if ( !SecurityUserInfo )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      {
        WPP_SF_qq(
          WPP_GLOBAL_Control->AttachedDevice,
          25,
          WPP_dc77a1bfe1f333f3a4c6c4eeb4778daa_Traceguids,
          SessionEntry,
          a2);
      }
      goto LABEL_209;
    }
    goto LABEL_210;
  }
  if ( SessionEntry )
    goto LABEL_205;
  if ( !SecurityUserInfo )
  {
    if ( (*(_DWORD *)(v12 + 420) & 0x10000000) != 0 )
    {
      v42 = *(_QWORD *)(v12 + 168);
      if ( v42 == v12 + 168 )
        v43 = 0;
      else
        v43 = (const UNICODE_STRING *)(v42 - 32);
      while ( v43 )
      {
        if ( ((__int64)v43[8].Buffer & 4) == 0 )
        {
          SecurityUserInfo = -1073741240;
          v44 = (int)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              21,
              WPP_dc77a1bfe1f333f3a4c6c4eeb4778daa_Traceguids,
              3221226056LL);
          }
          if ( (Microsoft_Windows_SMBClientEnableBits & 1) != 0 )
          {
            LODWORD(v53) = 0;
            McTemplateK0qqq_EtwWriteTransfer(v44, (unsigned int)SessionSetupError, v6 + 412, -1073741240, 255, v53);
          }
          goto LABEL_210;
        }
        v21 = *(const UNICODE_STRING **)&v43[2].Length;
        v43 = 0;
        if ( v21 != (const UNICODE_STRING *)(v12 + 168) )
          v43 = v21 - 2;
      }
    }
LABEL_164:
    P = 0;
    if ( !*(_DWORD *)(v12 + 432)
      && !(unsigned __int8)RxCloneUnicodeStringNonPagedPool(*(_QWORD *)(*(_QWORD *)(a2 + 32) + 88LL), &P)
      || (LOBYTE(v21) = v10 == 4, (SessionEntry = SmbMmAllocateSessionEntry(v12, v21)) == 0) )
    {
      SecurityUserInfo = -1073741670;
      goto LABEL_202;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      WPP_SF_qq(
        WPP_GLOBAL_Control->AttachedDevice,
        22,
        WPP_dc77a1bfe1f333f3a4c6c4eeb4778daa_Traceguids,
        SessionEntry,
        a2);
    *(_DWORD *)(SessionEntry + 12) = 1;
    *(_QWORD *)(SessionEntry + 64) = v12;
    *(_QWORD *)(SessionEntry + 400) = P;
    if ( !*(_DWORD *)(v12 + 432) )
      *(_WORD *)(SessionEntry + 132) = -1;
    *(_DWORD *)(SessionEntry + 136) = 0;
    if ( v10 == 4 )
    {
      *(_DWORD *)(SessionEntry + 136) = 8;
    }
    else if ( v10 == 3 )
    {
      *(_DWORD *)(SessionEntry + 136) = 4;
    }
    v45 = *(_QWORD *)(a2 + 104);
    *(_OWORD *)(SessionEntry + 144) = *(_OWORD *)(a2 + 72);
    *(_OWORD *)(SessionEntry + 160) = *(_OWORD *)(a2 + 88);
    *(_QWORD *)(SessionEntry + 176) = *(_QWORD *)(a2 + 104);
    if ( v45 )
      RxReferenceCredential();
    if ( *(_BYTE *)(v12 + 505) )
      *(_QWORD *)(SessionEntry + 152) = *(_QWORD *)(SessionEntry + 144);
    if ( !MRxSmbBootedRemotely )
      goto LABEL_184;
    if ( *(_QWORD *)(SessionEntry + 176) )
    {
      RxDereferenceCredential();
      *(_QWORD *)(SessionEntry + 176) = 0;
    }
    SecurityUserInfo = RxCreateCredential(SessionEntry + 176, 0, 0, String1, v8, v9, v57, 0, 0);
    if ( SecurityUserInfo >= 0 )
    {
LABEL_184:
      v46 = *(unsigned __int16 **)(v6 + 680);
      if ( !v46 )
      {
LABEL_189:
        MRxSmbTrackRefCount(SessionEntry, "SmbCeFindOrConstructSessionEntry", 1650);
        _InterlockedIncrement((volatile signed __int32 *)(SessionEntry + 8));
        v48 = KeAcquireSpinLockRaiseToDpc(&s_SmbCeDbSpinLock);
        s_SmbCeDbSpinLockSavedIrql = v48;
        v49 = *(_QWORD **)(v12 + 176);
        if ( *v49 != v12 + 168 )
          __fastfail(3u);
        *(_QWORD *)(SessionEntry + 32) = v12 + 168;
        *(_QWORD *)(SessionEntry + 40) = v49;
        *v49 = SessionEntry + 32;
        *(_QWORD *)(v12 + 176) = SessionEntry + 32;
        KeReleaseSpinLock(&s_SmbCeDbSpinLock, v48);
        v50 = *(_QWORD *)(SessionEntry + 176);
        if ( v50 )
        {
          v51 = *(unsigned __int16 **)(v50 + 40);
          if ( v51 )
          {
            if ( !*(_WORD *)(*((_QWORD *)v51 + 1) + 2 * ((unsigned __int64)*v51 >> 1) - 2) )
              *v51 -= 2;
          }
        }
        goto LABEL_199;
      }
      Pool2 = (void *)ExAllocatePool2(66, *v46, 1061124178);
      *(_QWORD *)(SessionEntry + 392) = Pool2;
      if ( Pool2 )
      {
        memmove(Pool2, (const void *)(*(_QWORD *)(v6 + 680) + 2LL), **(unsigned __int16 **)(v6 + 680));
        *(_WORD *)(SessionEntry + 384) = **(_WORD **)(v6 + 680);
        *(_WORD *)(SessionEntry + 386) = **(_WORD **)(v6 + 680);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
        {
          WPP_SF_Zq(
            WPP_GLOBAL_Control->AttachedDevice,
            23,
            (unsigned int)WPP_dc77a1bfe1f333f3a4c6c4eeb4778daa_Traceguids,
            SessionEntry + 384,
            SessionEntry);
        }
        goto LABEL_189;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
      {
        WPP_SF_qZ(
          WPP_GLOBAL_Control->AttachedDevice,
          24,
          (unsigned int)WPP_dc77a1bfe1f333f3a4c6c4eeb4778daa_Traceguids,
          SessionEntry,
          v12 + 80);
      }
      SecurityUserInfo = -1073741670;
    }
LABEL_199:
    if ( !SecurityUserInfo )
    {
LABEL_209:
      RxDiagnosticTrace(
        *(_QWORD *)(SessionEntry + 16),
        1,
        "Active VNrCtxts++ %x VNetRoot %p",
        _InterlockedIncrement((volatile signed __int32 *)(SessionEntry + 124)),
        (const void *)a2);
      *v60 = SessionEntry;
      goto LABEL_210;
    }
LABEL_202:
    if ( P )
    {
      ExFreePoolWithTag(P, 0);
      P = 0;
    }
  }
LABEL_210:
  MRxSmbTrackDerefCount(v12, "SmbCeFindOrConstructSessionEntry", 1695);
  SmbReferenceRecord(v12 + 792, "SmbCeFindOrConstructSessionEntry", 1695);
  SmbCepDereferenceServerEntry((PVOID)v12);
  return (unsigned int)SecurityUserInfo;
}

```

## disassembly

```asm
0x140002614  mov     [rsp+arg_10], r8
0x140002619  mov     [rsp+arg_0], rcx
0x14000261e  push    rbx
0x14000261f  push    rbp
0x140002620  push    rsi
0x140002621  push    rdi
0x140002622  push    r12
0x140002624  push    r13
0x140002626  push    r14
0x140002628  push    r15
0x14000262a  sub     rsp, 78h
0x14000262e  mov     rax, [rdx+68h]
0x140002632  xor     r15d, r15d
0x140002635  mov     rdi, r8
0x140002638  mov     r13, rdx
0x14000263b  mov     r12, rcx
0x14000263e  test    rax, rax
0x140002641  jz      short loc_14000265A
0x140002643  mov     rcx, [rax+28h]
0x140002647  mov     rbx, [rax+10h]
0x14000264b  mov     rsi, [rax+18h]
0x14000264f  mov     r14, [rax+20h]
0x140002653  mov     [rsp+0B8h+var_50], rcx
0x140002658  jmp     short loc_140002668
0x14000265a  mov     rbx, r15
0x14000265d  mov     [rsp+0B8h+var_50], r15
0x140002662  mov     r14, r15
0x140002665  mov     rsi, r15
0x140002668  mov     rax, cs:__imp_MRxSmbBootedRemotely
0x14000266f  mov     ecx, 2
0x140002674  mov     [rsp+0B8h+arg_18], rsi
0x14000267c  mov     [rsp+0B8h+var_68], r14
0x140002681  mov     [rsp+0B8h+String1], rbx
0x140002686  cmp     [rax], r15b
0x140002689  jz      short loc_1400026DE
0x14000268b  mov     rcx, [rdx+20h]
0x14000268f  mov     r8b, 1; CaseInSensitive
0x140002692  mov     rdx, cs:__imp_MRxSmbRemoteBootShare; String2
0x140002699  mov     rcx, [rcx+58h]; String1
0x14000269d  call    cs:__imp_RtlCompareUnicodeString
0x1400026a4  nop     dword ptr [rax+rax+00h]
0x1400026a9  test    eax, eax
0x1400026ab  jnz     short loc_1400026D9
0x1400026ad  mov     rsi, cs:__imp_MRxSmbRemoteBootMachinePassword
0x1400026b4  lea     ebp, [rax+4]
0x1400026b7  mov     rax, cs:__imp_MRxSmbRemoteBootMachineName
0x1400026be  mov     r14, cs:__imp_MRxSmbRemoteBootMachineDomain
0x1400026c5  mov     [rsp+0B8h+String1], rax
0x1400026ca  mov     [rsp+0B8h+arg_18], rsi
0x1400026d2  mov     [rsp+0B8h+var_68], r14
0x1400026d7  jmp     short loc_14000271F
0x1400026d9  mov     ecx, 2
0x1400026de  test    rbx, rbx
0x1400026e1  jz      short loc_140002706
0x1400026e3  cmp     [rbx], r15w
0x1400026e7  jnz     short loc_14000271D
0x1400026e9  test    rsi, rsi
0x1400026ec  jz      short loc_14000271D
0x1400026ee  cmp     [rsi], r15w
0x1400026f2  jnz     short loc_14000271D
0x1400026f4  test    r14, r14
0x1400026f7  jz      short loc_14000271D
0x1400026f9  cmp     [r14], r15w
0x1400026fd  jnz     short loc_14000271D
0x1400026ff  mov     ebp, 3
0x140002704  jmp     short loc_14000271F
0x140002706  mov     ebp, 1
0x14000270b  mov     dword ptr [rsp+0B8h+P], ebp
0x140002712  test    rsi, rsi
0x140002715  jz      short loc_140002726
0x140002717  cmp     [rsi], r15w
0x14000271b  jbe     short loc_140002726
0x14000271d  mov     ebp, ecx
0x14000271f  mov     dword ptr [rsp+0B8h+P], ebp
0x140002726  mov     rcx, [r13+20h]
0x14000272a  mov     [rdi], r15
0x14000272d  mov     rcx, [rcx+20h]
0x140002731  call    SmbCeReferenceAssociatedServerEntry
0x140002736  mov     r15, rax
0x140002739  xor     eax, eax
0x14000273b  test    r15, r15
0x14000273e  jz      loc_14000342C
0x140002744  mov     edi, eax
0x140002746  cmp     ebp, 2
0x140002749  jz      loc_14000286F
0x14000274f  cmp     [r15+1B0h], eax
0x140002756  jz      loc_14000286F
0x14000275c  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x140002763  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000276a  nop     dword ptr [rax+rax+00h]
0x14000276f  mov     cs:s_SmbCeDbSpinLockSavedIrql, al
0x140002775  cmp     ebp, 1
0x140002778  jz      short loc_1400027AB
0x14000277a  xor     r8d, r8d
0x14000277d  lea     rdx, [r15+0A8h]
0x140002784  mov     rbx, [rdx]
0x140002787  cmp     rbx, rdx
0x14000278a  jnz     short loc_1400027C4
0x14000278c  mov     rbx, r8
0x14000278f  jmp     loc_140002849
0x140002794  mov     ecx, [rbx+88h]
0x14000279a  test    cl, 40h
0x14000279d  jz      loc_140002830
0x1400027a3  mov     rcx, rbx
0x1400027a6  call    SmbCeRemoveDefaultSessionEntry
0x1400027ab  lea     rdx, [r13+48h]
0x1400027af  mov     rcx, r15
0x1400027b2  call    SmbCeGetDefaultSessionEntry
0x1400027b7  xor     r8d, r8d
0x1400027ba  mov     rbx, rax
0x1400027bd  test    rax, rax
0x1400027c0  jnz     short loc_140002794
0x1400027c2  jmp     short loc_14000277D
0x1400027c4  add     rbx, 0FFFFFFFFFFFFFFE0h
0x1400027c8  jz      short loc_140002849
0x1400027ca  mov     eax, [rbx+88h]
0x1400027d0  test    al, 40h
0x1400027d2  jnz     short loc_140002814
0x1400027d4  cmp     ebp, 1
0x1400027d7  jnz     short loc_140002807
0x1400027d9  mov     ecx, [r13+48h]
0x1400027dd  cmp     [rbx+90h], ecx
0x1400027e3  jnz     short loc_1400027F1
0x1400027e5  mov     eax, [r13+4Ch]
0x1400027e9  cmp     [rbx+94h], eax
0x1400027ef  jz      short loc_14000282B
0x1400027f1  cmp     [rbx+98h], ecx
0x1400027f7  jnz     short loc_140002814
0x1400027f9  mov     eax, [r13+4Ch]
0x1400027fd  cmp     [rbx+9Ch], eax
0x140002803  jnz     short loc_140002814
0x140002805  jmp     short loc_14000282B
0x140002807  cmp     ebp, 3
0x14000280a  jnz     short loc_140002810
0x14000280c  test    al, 4
0x14000280e  jmp     short loc_140002812
0x140002810  test    al, 8
0x140002812  jnz     short loc_14000282B
0x140002814  mov     rcx, [rbx+20h]
0x140002818  mov     rbx, r8
0x14000281b  cmp     rcx, rdx
0x14000281e  lea     rax, [rcx-20h]
0x140002822  cmovnz  rbx, rax
0x140002826  test    rbx, rbx
0x140002829  jnz     short loc_1400027CA
0x14000282b  test    rbx, rbx
0x14000282e  jz      short loc_140002849
0x140002830  mov     r8d, 519h
0x140002836  lea     rdx, aSmbcefindorcon_0; "SmbCeFindOrConstructSessionEntry"
0x14000283d  mov     rcx, rbx
0x140002840  call    MRxSmbTrackRefCount
0x140002845  lock inc dword ptr [rbx+8]
0x140002849  mov     dl, cs:s_SmbCeDbSpinLockSavedIrql; NewIrql
0x14000284f  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x140002856  call    cs:__imp_KeReleaseSpinLock
0x14000285d  nop     dword ptr [rax+rax+00h]
0x140002862  mov     rsi, [rsp+0B8h+arg_18]
0x14000286a  jmp     loc_140002EF4
0x14000286f  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x140002876  mov     r12b, al
0x140002879  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002880  nop     dword ptr [rax+rax+00h]
0x140002885  lea     r14, [r15+0A8h]
0x14000288c  mov     cs:s_SmbCeDbSpinLockSavedIrql, al
0x140002892  mov     rbx, [r14]
0x140002895  cmp     rbx, r14
0x140002898  jnz     short loc_14000289E
0x14000289a  xor     ebx, ebx
0x14000289c  jmp     short loc_1400028BD
0x14000289e  add     rbx, 0FFFFFFFFFFFFFFE0h
0x1400028a2  jz      short loc_1400028BD
0x1400028a4  mov     r8d, 523h
0x1400028aa  lea     rdx, aSmbcefindorcon_0; "SmbCeFindOrConstructSessionEntry"
0x1400028b1  mov     rcx, rbx
0x1400028b4  call    MRxSmbTrackRefCount
0x1400028b9  lock inc dword ptr [rbx+8]
0x1400028bd  mov     dl, cs:s_SmbCeDbSpinLockSavedIrql; NewIrql
0x1400028c3  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x1400028ca  call    cs:__imp_KeReleaseSpinLock
0x1400028d1  nop     dword ptr [rax+rax+00h]
0x1400028d6  xor     r10d, r10d
0x1400028d9  test    rbx, rbx
0x1400028dc  jz      loc_140002F3A
0x1400028e2  test    r12b, r12b
0x1400028e5  jnz     loc_140002F3A
0x1400028eb  mov     eax, [rbx+88h]
0x1400028f1  test    al, 4Ch
0x1400028f3  jnz     loc_140002DCD
0x1400028f9  mov     [rsp+0B8h+Buffer], r10
0x1400028fe  cmp     [r15+1B0h], r10d
0x140002905  jz      loc_140002CA5
0x14000290b  mov     eax, [r13+58h]
0x14000290f  cmp     [rbx+0A0h], eax
0x140002915  jnz     loc_140002DCD
0x14000291b  mov     ecx, [r13+48h]
0x14000291f  cmp     [rbx+90h], ecx
0x140002925  jnz     short loc_140002933
0x140002927  mov     eax, [r13+4Ch]
0x14000292b  cmp     [rbx+94h], eax
0x140002931  jz      short loc_14000294F
0x140002933  cmp     [rbx+98h], ecx
0x140002939  jnz     loc_140002DCD
0x14000293f  mov     eax, [r13+4Ch]
0x140002943  cmp     [rbx+9Ch], eax
0x140002949  jnz     loc_140002DCD
0x14000294f  mov     rbp, [rbx+0B0h]
0x140002956  test    rbp, rbp
0x140002959  jz      short loc_140002972
0x14000295b  mov     rsi, [rbp+10h]
0x14000295f  mov     r14, [rbp+20h]
0x140002963  test    rsi, rsi
0x140002966  jz      short loc_140002978
0x140002968  test    r14, r14
0x14000296b  jz      short loc_140002978
0x14000296d  jmp     loc_140002A4B
0x140002972  mov     r14, r10
0x140002975  mov     rsi, r10
0x140002978  mov     rax, cs:__imp_MRxSmbBootedRemotely
0x14000297f  cmp     [rax], r10b
0x140002982  jz      loc_140002A13
0x140002988  cmp     [rsp+0B8h+String1], r10
0x14000298d  jnz     short loc_14000299A
0x14000298f  cmp     [rsp+0B8h+var_68], r10
0x140002994  jz      loc_140002DC6
0x14000299a  test    byte ptr cs:Microsoft_Windows_SMBClientEnableBits, 1
0x1400029a1  mov     edi, 0C0000195h
0x1400029a6  jz      loc_140002DC6
0x1400029ac  mov     dword ptr [rsp+0B8h+var_90], r10d
0x1400029b1  mov     dword ptr [rsp+0B8h+var_98], 10600552h
0x1400029b9  mov     r8, [rsp+0B8h+arg_0]
0x1400029c1  lea     rdx, SessionSetupError
0x1400029c8  add     r8, 19Ch
0x1400029cf  mov     r9d, 0C0000195h
0x1400029d5  call    McTemplateK0qqq_EtwWriteTransfer
0x1400029da  xor     r10d, r10d
0x1400029dd  mov     rsi, [rsp+0B8h+arg_18]
0x1400029e5  mov     rcx, [rsp+0B8h+Buffer]; Buffer
0x1400029ea  test    rcx, rcx
0x1400029ed  jz      short loc_1400029FE
0x1400029ef  call    cs:__imp_LsaFreeReturnBuffer
0x1400029f6  nop     dword ptr [rax+rax+00h]
0x1400029fb  xor     r10d, r10d
0x1400029fe  lea     r14, [r15+0A8h]
0x140002a05  test    r12b, r12b
0x140002a08  jz      loc_140002DCD
0x140002a0e  jmp     loc_140002D4D
0x140002a13  lea     r8, [rsp+0B8h+Buffer]; UserInformation
0x140002a18  mov     edx, 1; Flags
0x140002a1d  lea     rcx, [r13+48h]; LogonId
0x140002a21  call    cs:__imp_GetSecurityUserInfo
0x140002a28  nop     dword ptr [rax+rax+00h]
0x140002a2d  xor     r10d, r10d
0x140002a30  mov     edi, eax
0x140002a32  test    eax, eax
0x140002a34  js      short loc_1400029DD
0x140002a36  mov     rcx, [rsp+0B8h+Buffer]
0x140002a3b  test    rsi, rsi
0x140002a3e  cmovz   rsi, rcx
0x140002a42  test    r14, r14
0x140002a45  jnz     short loc_140002A4B
0x140002a47  lea     r14, [rcx+10h]
0x140002a4b  mov     rax, [rsp+0B8h+String1]
0x140002a50  test    rax, rax
0x140002a53  jz      short loc_140002AD3
0x140002a55  mov     r8b, 1; CaseInSensitive
0x140002a58  mov     rdx, rsi; String2
0x140002a5b  mov     rcx, rax; String1
0x140002a5e  call    cs:__imp_RtlEqualUnicodeString
0x140002a65  nop     dword ptr [rax+rax+00h]
0x140002a6a  xor     r10d, r10d
0x140002a6d  test    al, al
0x140002a6f  jnz     short loc_140002AD3
0x140002a71  mov     edi, 0C0000195h
0x140002a76  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140002a7d  lea     rax, WPP_GLOBAL_Control
0x140002a84  cmp     rcx, rax
0x140002a87  jz      short loc_140002AB4
0x140002a89  test    dword ptr [rcx+2Ch], 100h
0x140002a90  jz      short loc_140002AB4
0x140002a92  mov     rcx, [rcx+18h]
0x140002a96  lea     edx, [r10+10h]
0x140002a9a  mov     r9, rbx
0x140002a9d  mov     dword ptr [rsp+0B8h+var_98], 0C0000195h
0x140002aa5  lea     r8, WPP_dc77a1bfe1f333f3a4c6c4eeb4778daa_Traceguids
0x140002aac  call    WPP_SF_qD
0x140002ab1  xor     r10d, r10d
0x140002ab4  test    byte ptr cs:Microsoft_Windows_SMBClientEnableBits, 1
0x140002abb  jz      loc_1400029DD
0x140002ac1  mov     dword ptr [rsp+0B8h+var_90], r10d
0x140002ac6  mov     dword ptr [rsp+0B8h+var_98], 1060056Fh
0x140002ace  jmp     loc_1400029B9
0x140002ad3  mov     rax, [rsp+0B8h+var_68]
0x140002ad8  test    rax, rax
0x140002adb  jz      short loc_140002B5B
0x140002add  mov     r8b, 1; CaseInSensitive
0x140002ae0  mov     rdx, r14; String2
0x140002ae3  mov     rcx, rax; String1
0x140002ae6  call    cs:__imp_RtlEqualUnicodeString
0x140002aed  nop     dword ptr [rax+rax+00h]
0x140002af2  xor     r10d, r10d
  ... truncated ...
```
