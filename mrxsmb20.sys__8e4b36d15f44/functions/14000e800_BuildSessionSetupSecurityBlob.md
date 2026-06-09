# BuildSessionSetupSecurityBlob

- ea: `0x14000e800`
- end: `0x14000f4f0`
- name: `BuildSessionSetupSecurityBlob`
- size: `3312`
- prototype: `__int64 __fastcall(union _RTL_RUN_ONCE *Parameter, struct _SecHandle *, UNICODE_STRING *, __int64, int, __int64, _DWORD *, _BYTE *)`
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000deb0`
- `0x140026bd0`

## callees

- `0x14000ba80`
- `0x14000bcc0`
- `0x14000e800`
- `0x140025b70`
- `0x140029764`
- `0x140029840`
- `0x14002ebe0`
- `0x14002ed54`
- `0x14002edcc`
- `0x14002eea0`
- `0x14002ef34`
- `0x14002f040`
- `0x140037120`
- `0x140053a08`
- `0x140053a60`
- `0x140053b10`

## import_xrefs

- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x14000eca4`
- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x14000eca4`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14000f45b`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14000f45b`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14000e976`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14000e976`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000eaf9`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000eaf9`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000ea9b`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000ea9b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000ec6c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000f00b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000f39f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000ec6c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000f00b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000f39f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000ec3d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000efea`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000f381`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000ec3d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000efea`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000f381`
- `rdbss!RxDereferenceSiloAndReleaseRundown` at `0x14000f46e`
- `rdbss!RxDereferenceSiloAndReleaseRundown` at `0x14000f46e`
- `rdbss!RxReferenceSiloAndAcquireRundown` at `0x14000e94c`
- `rdbss!RxReferenceSiloAndAcquireRundown` at `0x14000e94c`
- `ksecdd!AcquireCredentialsHandleW` at `0x14000ee5d`
- `ksecdd!AcquireCredentialsHandleW` at `0x14000ee5d`
- `ksecdd!InitializeSecurityContextW` at `0x14000f145`
- `ksecdd!InitializeSecurityContextW` at `0x14000f145`
- `ksecdd!MapSecurityError` at `0x14000ef1b`
- `ksecdd!MapSecurityError` at `0x14000f25f`
- `ksecdd!MapSecurityError` at `0x14000f272`
- `ksecdd!MapSecurityError` at `0x14000ef1b`
- `ksecdd!MapSecurityError` at `0x14000f25f`
- `ksecdd!MapSecurityError` at `0x14000f272`
- `mrxsmb!SmbCeIsServerTrustedZoneRunOnce` at `0x14000ec90`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14000ea83`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14000ebc3`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14000ea83`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14000ebc3`

## pseudocode

```c
__int64 __fastcall BuildSessionSetupSecurityBlob(
        union _RTL_RUN_ONCE *Parameter,
        struct _SecHandle *a2,
        UNICODE_STRING *a3,
        __int64 a4,
        int a5,
        __int64 a6,
        _DWORD *a7,
        _BYTE *a8)
{
  union _RTL_RUN_ONCE v8; // r15
  union _RTL_RUN_ONCE v9; // rdi
  struct _SecHandle *v10; // r14
  __int64 Timer_high; // rdx
  __int64 v13; // rbx
  NTSTATUS v14; // edi
  union _RTL_RUN_ONCE v15; // rax
  __int128 *v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rcx
  char v20; // r13
  struct _SecHandle *v21; // rcx
  char v22; // r14
  __int64 v23; // rcx
  __int64 ConfigurationBlock; // rdi
  unsigned __int16 v25; // bx
  PDEVICE_OBJECT v26; // rcx
  int v27; // edx
  __int64 v28; // r8
  int Ptr_high; // r13d
  int Ptr; // r14d
  int v31; // r12d
  PDEVICE_OBJECT *v32; // rdx
  __int64 v33; // r8
  int v34; // edi
  int v35; // ebx
  NTSTATUS v36; // eax
  char v37; // r13
  char v38; // di
  __int64 v39; // rbx
  SECURITY_STATUS v40; // r14d
  int v41; // edi
  __int64 *v42; // rdx
  struct _SecHandle *v43; // rdx
  struct _SecHandle *v44; // r12
  __int64 v45; // rbx
  SECURITY_STATUS v46; // eax
  SECURITY_STATUS v47; // r14d
  int v48; // edi
  __int64 *v49; // rdx
  struct _SecHandle *v50; // rbx
  unsigned int v51; // eax
  char v53; // [rsp+70h] [rbp-90h]
  char v54; // [rsp+71h] [rbp-8Fh]
  char v55; // [rsp+74h] [rbp-8Ch]
  UNICODE_STRING StringIn; // [rsp+78h] [rbp-88h] BYREF
  __int64 pvLogonId; // [rsp+88h] [rbp-78h] BYREF
  void *pAuthData; // [rsp+90h] [rbp-70h] BYREF
  __int64 v59; // [rsp+98h] [rbp-68h]
  struct _SecHandle *v60; // [rsp+A0h] [rbp-60h]
  unsigned int pfContextAttr; // [rsp+A8h] [rbp-58h] BYREF
  PSECURITY_STRING pTargetName; // [rsp+B0h] [rbp-50h]
  _DWORD *v63; // [rsp+B8h] [rbp-48h]
  __int128 v64; // [rsp+C0h] [rbp-40h]
  __int64 v65; // [rsp+D0h] [rbp-30h]
  __int128 v66; // [rsp+D8h] [rbp-28h] BYREF
  UNICODE_STRING pPackage; // [rsp+E8h] [rbp-18h] BYREF
  struct _SecBufferDesc pOutput; // [rsp+F8h] [rbp-8h] BYREF
  _SecBufferDesc pInput; // [rsp+108h] [rbp+8h] BYREF
  SECURITY_INTEGER ptsExpiry; // [rsp+118h] [rbp+18h] BYREF
  __int64 v71; // [rsp+120h] [rbp+20h]
  SECURITY_INTEGER v72; // [rsp+128h] [rbp+28h] BYREF
  _BYTE *v73; // [rsp+130h] [rbp+30h]
  _OWORD v74[2]; // [rsp+138h] [rbp+38h] BYREF
  __int64 v75; // [rsp+158h] [rbp+58h]
  struct _SecHandle phNewContext; // [rsp+160h] [rbp+60h] BYREF
  struct _SecHandle phCredential; // [rsp+170h] [rbp+70h] BYREF
  _DWORD v78[2]; // [rsp+180h] [rbp+80h] BYREF
  __int64 v79; // [rsp+188h] [rbp+88h]
  int v80; // [rsp+190h] [rbp+90h]
  int v81; // [rsp+194h] [rbp+94h]
  char *v82; // [rsp+198h] [rbp+98h]
  int MaximumLength; // [rsp+1A0h] [rbp+A0h]
  int v84; // [rsp+1A4h] [rbp+A4h]
  PWSTR Buffer; // [rsp+1A8h] [rbp+A8h]

  v8.Ptr = Parameter[48].Ptr;
  v9.Ptr = Parameter[16].Ptr;
  v60 = a2;
  v10 = a2;
  Timer_high = (__int64)a7;
  pfContextAttr = 0;
  v72.QuadPart = 0;
  v71 = a4;
  pTargetName = a3;
  v63 = a7;
  v73 = a8;
  v59 = 0;
  pAuthData = 0;
  StringIn = 0;
  pInput = 0;
  pOutput = 0;
  v66 = 0;
  phNewContext = 0;
  v13 = *((_QWORD *)v8.Ptr + 3);
  pvLogonId = 996;
  v64 = 0;
  if ( a8 )
    *a8 = 0;
  if ( *a7 > 0xFFFFu )
  {
    v14 = -1073741811;
LABEL_155:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qL(WPP_GLOBAL_Control->AttachedDevice, Timer_high, a3, Parameter, v14);
    }
    goto LABEL_159;
  }
  StringIn = (UNICODE_STRING)*((_OWORD *)v8.Ptr + 8);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_ZZ(WPP_GLOBAL_Control->AttachedDevice, 15, (_DWORD)a3, (unsigned int)&StringIn, (__int64)a3);
    Timer_high = (__int64)v63;
  }
  v15.Ptr = Parameter[16].Ptr;
  if ( v15.Ptr )
  {
    v16 = (__int128 *)*((_QWORD *)v15.Ptr + 2);
    if ( v16 )
      v64 = *v16;
  }
  if ( (*(_BYTE *)(v13 + 1314) & 8) != 0 )
  {
    *(_DWORD *)Timer_high = 0;
    v14 = 0;
    goto LABEL_159;
  }
  v17 = *((_QWORD *)v8.Ptr + 65);
  v65 = 0;
  v54 = 0;
  if ( v17 )
  {
    if ( !RxReferenceSiloAndAcquireRundown(v17, Timer_high) )
    {
      v14 = -1073741536;
      goto LABEL_155;
    }
    v18 = *((_QWORD *)v8.Ptr + 65);
    if ( v18 )
      v19 = *(_QWORD *)(v18 + 40);
    else
      v19 = 0;
    v65 = PsAttachSiloToCurrentThread(v19);
    v54 = 1;
  }
  v20 = 0;
  if ( LODWORD(Parameter[12].Ptr) != `RxIsGlobalMappingLuid'::`2'::globalMappingLuid
    || HIDWORD(Parameter[12].Ptr) != dword_140046144 )
  {
    pvLogonId = (__int64)Parameter[12].Ptr;
  }
  v21 = v10 + 30;
  if ( v10[30].dwLower != -1 && v10[30].dwUpper != -1 )
  {
LABEL_107:
    v43 = 0;
    v44 = v10 + 29;
    if ( v10[29].dwLower != -1 && v10[29].dwUpper != -1 )
    {
      v43 = v10 + 29;
      phNewContext = *v44;
    }
    v78[1] = 2;
    pInput.ulVersion = 0;
    pInput.pBuffers = (PSecBuffer)v78;
    v79 = v71;
    v78[0] = a5;
    v82 = (char *)v8.Ptr + 800;
    Buffer = StringIn.Buffer;
    MaximumLength = StringIn.MaximumLength;
    pOutput.pBuffers = (PSecBuffer)&v66;
    *((_QWORD *)&v66 + 1) = a6;
    pOutput.ulVersion = 0;
    v80 = 28;
    v81 = 129;
    LODWORD(v66) = *v63;
    v84 = 130;
    pInput.cBuffers = 3;
    pOutput.cBuffers = 1;
    DWORD1(v66) = 2;
    v45 = MEMORY[0xFFFFF78000000008];
    v46 = InitializeSecurityContextW(
            v21,
            v43,
            pTargetName,
            0x210003u,
            0,
            0x10u,
            &pInput,
            0,
            &phNewContext,
            &pOutput,
            &pfContextAttr,
            &v72);
    a3 = (UNICODE_STRING *)0xD6BF94D5E57A42BDLL;
    v47 = v46;
    Timer_high = v45 / 10000000;
    v48 = MEMORY[0xFFFFF78000000008] / 10000000 - v45 / 10000000;
    if ( v48 > 15 )
    {
      if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x4000000) != 0 )
      {
        v49 = SmbLsassCallDurationWarning;
        goto LABEL_115;
      }
    }
    else if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x20000000) != 0 )
    {
      v49 = SmbLsassCallDurationInfo;
LABEL_115:
      McTemplateK0qdd_EtwWriteTransfer(
        (unsigned __int64)(MEMORY[0xFFFFF78000000008]
                         + ((unsigned __int128)(MEMORY[0xFFFFF78000000008] * (__int128)(__int64)0xD6BF94D5E57A42BDuLL) >> 64)) >> 63,
        v49,
        0xD6BF94D5E57A42BDuLL,
        0,
        MEMORY[0xFFFFF78000000008] / 10000000 - v45 / 10000000);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        25,
        WPP_981a12f1532a3df13e243e2e48204374_Traceguids,
        (unsigned int)v48);
    }
    if ( v47 == -2146893042 )
    {
      v14 = -1073741715;
    }
    else if ( v20
           && v47 == -1073740776
           && (v47 = -1067646964, WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control)
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
           && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_Zq(WPP_GLOBAL_Control->AttachedDevice, 26, (_DWORD)a3, (unsigned int)&StringIn, (char)Parameter);
      v14 = MapSecurityError(-1067646964);
    }
    else
    {
      v14 = MapSecurityError(v47);
      if ( v47 == 590610 && v73 )
        *v73 = 1;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_LL(WPP_GLOBAL_Control->AttachedDevice, 27, a3, (unsigned int)v14, v47);
    }
    if ( v14 && (unsigned int)(v47 - 590610) > 1 )
    {
      if ( v44->dwLower == -1 || (v50 = v60, v60[29].dwUpper == -1) )
      {
        if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x40000000) != 0 )
          McTemplateK0qqqxhzr4hzr6hzr8_EtwWriteTransfer(
            (unsigned __int16)v64 >> 1,
            (unsigned int)ISCFailure,
            *((_WORD *)v8.Ptr + 40) >> 1,
            10,
            v14,
            v47,
            pvLogonId,
            *((_WORD *)v8.Ptr + 40) >> 1,
            *((_QWORD *)v8.Ptr + 11),
            pTargetName->Length >> 1,
            (__int64)pTargetName->Buffer,
            (unsigned __int16)v64 >> 1,
            *((__int64 *)&v64 + 1));
        goto LABEL_141;
      }
    }
    else
    {
      v50 = v60;
    }
    ExAcquirePushLockExclusiveEx(&v50[28].dwUpper, 0);
    *v44 = phNewContext;
    ExReleasePushLockExclusiveEx(&v50[28].dwUpper, 0);
    v51 = v47 - 590610;
    if ( v14 )
    {
      if ( v51 > 1 )
      {
        if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x40000000) != 0 )
        {
          McTemplateK0qqqxhzr4hzr6hzr8_EtwWriteTransfer(
            (unsigned __int16)v64 >> 1,
            (unsigned int)ISCFailure,
            *((_WORD *)v8.Ptr + 40) >> 1,
            10,
            v14,
            v47,
            pvLogonId,
            *((_WORD *)v8.Ptr + 40) >> 1,
            *((_QWORD *)v8.Ptr + 11),
            pTargetName->Length >> 1,
            (__int64)pTargetName->Buffer,
            (unsigned __int16)v64 >> 1,
            *((__int64 *)&v64 + 1));
          HIDWORD(v59) = 10;
          goto LABEL_150;
        }
LABEL_141:
        HIDWORD(v59) = 10;
        goto LABEL_150;
      }
    }
    else if ( v51 > 1 )
    {
LABEL_149:
      *v63 = (unsigned __int16)v66;
      goto LABEL_150;
    }
    v14 = 0;
    goto LABEL_149;
  }
  *(_QWORD *)&pPackage.Length = 1310738;
  ptsExpiry.QuadPart = 0;
  pPackage.Buffer = L"Negotiate";
  phCredential = 0;
  if ( v9.Ptr )
    pAuthData = (void *)*((_QWORD *)v9.Ptr + 1);
  memset(v74, 0, sizeof(v74));
  v75 = 0;
  if ( StringIn.Buffer )
  {
    v22 = 0;
    if ( (int)RfsServerNameInitialize(&StringIn) >= 0 )
    {
      ConfigurationBlock = MRxSmbGetConfigurationBlock(v23);
      ExAcquirePushLockSharedEx(ConfigurationBlock + 456, 0);
      v25 = 0;
      if ( *(_WORD *)(ConfigurationBlock + 472) )
      {
        while ( !(unsigned __int8)RfsServerNameEqual(v74, *(_QWORD *)(ConfigurationBlock + 464) + 40LL * v25) )
        {
          if ( ++v25 >= *(_WORD *)(ConfigurationBlock + 472) )
            goto LABEL_39;
        }
        v22 = 1;
      }
LABEL_39:
      ExReleasePushLockSharedEx(ConfigurationBlock + 456, 0);
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
           && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_981a12f1532a3df13e243e2e48204374_Traceguids, &StringIn);
    }
    RfsServerNameCleanup(v74);
    BYTE5(Parameter[58].Ptr) = v22;
    if ( v22 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_Zq(WPP_GLOBAL_Control->AttachedDevice, 16, (_DWORD)a3, (unsigned int)&StringIn, (char)Parameter);
      }
      goto LABEL_89;
    }
  }
  else
  {
    BYTE5(Parameter[58].Ptr) = 0;
  }
  if ( LOBYTE(Parameter[82].Ptr) )
  {
    v14 = HandleNTLMBlocking(&StringIn, &pAuthData, a3, 0);
    v26 = WPP_GLOBAL_Control;
    Timer_high = (__int64)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      Timer_high = HIDWORD(WPP_GLOBAL_Control->Timer);
      if ( (Timer_high & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        v27 = 17;
LABEL_56:
        WPP_SF_Zq(v26->AttachedDevice, v27, (_DWORD)a3, (unsigned int)&StringIn, (char)Parameter);
      }
    }
  }
  else
  {
    if ( !*(_BYTE *)(MRxSmbGetConfigurationBlock(v21) + 452) )
    {
      ExAcquirePushLockExclusiveEx(&Parameter[69], 0);
      Ptr_high = HIDWORD(Parameter[70].Ptr);
      Ptr = (int)Parameter[71].Ptr;
      v31 = (int)Parameter[70].Ptr;
      v55 = Ptr_high;
      ExReleasePushLockExclusiveEx(&Parameter[69], 0);
      v34 = v31 + Ptr_high;
      v35 = v31;
      if ( v31 + Ptr_high && v34 == Ptr )
      {
        v36 = RtlRunOnceExecuteOnce(Parameter + 59, SmbCeIsServerTrustedZoneRunOnce, Parameter, 0);
        v37 = (char)Parameter[60].Ptr;
        if ( v36 < 0 )
        {
          v32 = &WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            LODWORD(v32) = HIDWORD(WPP_GLOBAL_Control->Timer);
            if ( ((unsigned __int8)v32 & 1) != 0 )
            {
              if ( BYTE1(WPP_GLOBAL_Control->Timer) )
                WPP_SF_d(
                  WPP_GLOBAL_Control->AttachedDevice,
                  19,
                  WPP_981a12f1532a3df13e243e2e48204374_Traceguids,
                  (unsigned int)v36);
            }
          }
        }
        if ( !v37 )
          v35 = v34;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          LOBYTE(Ptr_high) = v55;
        }
        else
        {
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            WPP_SF_qD(
              WPP_GLOBAL_Control->AttachedDevice,
              20,
              WPP_981a12f1532a3df13e243e2e48204374_Traceguids,
              Parameter,
              v37 == 0);
          LOBYTE(Ptr_high) = v55;
        }
      }
      v38 = v35 && v35 == Ptr;
      v53 = v38;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_Zqddddd(
          WPP_GLOBAL_Control->AttachedDevice,
          (_DWORD)v32,
          v33,
          (unsigned int)&StringIn,
          (char)Parameter,
          v38,
          Ptr,
          v35,
          v31,
          Ptr_high);
      }
      if ( !v38 )
      {
        v20 = 0;
        goto LABEL_89;
      }
      v14 = HandleNTLMBlocking(&StringIn, &pAuthData, v33, 2);
      Timer_high = (__int64)&WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_Zq(WPP_GLOBAL_Control->AttachedDevice, 22, (_DWORD)a3, (unsigned int)&StringIn, (char)Parameter);
      }
      v20 = v53;
      goto LABEL_86;
    }
    v14 = HandleNTLMBlocking(&StringIn, &pAuthData, v28, 1);
    v26 = WPP_GLOBAL_Control;
    Timer_high = (__int64)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      v27 = 18;
      goto LABEL_56;
    }
  }
LABEL_86:
  if ( v14 < 0 )
    goto LABEL_150;
LABEL_89:
  v39 = MEMORY[0xFFFFF78000000008];
  v40 = AcquireCredentialsHandleW(0, &pPackage, 2u, &pvLogonId, pAuthData, 0, 0, &phCredential, &ptsExpiry);
  v41 = MEMORY[0xFFFFF78000000008] / 10000000 - v39 / 10000000;
  if ( v41 > 15 )
  {
    if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x4000000) != 0 )
    {
      v42 = SmbLsassCallDurationWarning;
      goto LABEL_94;
    }
  }
  else if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x20000000) != 0 )
  {
    v42 = SmbLsassCallDurationInfo;
LABEL_94:
    McTemplateK0qdd_EtwWriteTransfer(
      (unsigned __int64)(MEMORY[0xFFFFF78000000008]
                       + ((unsigned __int128)(MEMORY[0xFFFFF78000000008] * (__int128)(__int64)0xD6BF94D5E57A42BDuLL) >> 64)) >> 63,
      v42,
      0xD6BF94D5E57A42BDuLL,
      1,
      v41);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_981a12f1532a3df13e243e2e48204374_Traceguids, (unsigned int)v41);
  }
  v14 = MapSecurityError(v40);
  if ( v14 >= 0 )
  {
    v10 = v60;
    ExAcquirePushLockExclusiveEx(&v60[28].dwUpper, 0);
    v10[30] = phCredential;
    ExReleasePushLockExclusiveEx(&v10[28].dwUpper, 0);
    v21 = v10 + 30;
    goto LABEL_107;
  }
  if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x40000000) != 0 )
    McTemplateK0qqqxhzr4hzr6hzr8_EtwWriteTransfer(
      (unsigned __int16)v64 >> 1,
      (unsigned int)AcquireCredHandleFailure,
      *((_WORD *)v8.Ptr + 40) >> 1,
      9,
      v14,
      v40,
      pvLogonId,
      *((_WORD *)v8.Ptr + 40) >> 1,
      *((_QWORD *)v8.Ptr + 11),
      0,
      0,
      (unsigned __int16)v64 >> 1,
      *((__int64 *)&v64 + 1));
  HIDWORD(v59) = 9;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_LL(WPP_GLOBAL_Control->AttachedDevice, 24, a3, (unsigned int)v14, v40);
  }
LABEL_150:
  if ( v54 )
  {
    PsDetachSiloFromCurrentThread(v65);
    RxDereferenceSiloAndReleaseRundown(*((_QWORD *)v8.Ptr + 65));
  }
  if ( v14 && v14 != -1073741718 && v14 != -1073741802 )
    goto LABEL_155;
LABEL_159:
  LODWORD(v59) = v14;
  return v59;
}

```

## disassembly

```asm
0x14000e800  mov     [rsp-8+arg_18], rbx
0x14000e805  push    rbp
0x14000e806  push    rsi
0x14000e807  push    rdi
0x14000e808  push    r12
0x14000e80a  push    r13
0x14000e80c  push    r14
0x14000e80e  push    r15
0x14000e810  lea     rbp, [rsp-0C0h]
0x14000e818  sub     rsp, 1C0h
0x14000e81f  mov     rax, cs:__security_cookie
0x14000e826  xor     rax, rsp
0x14000e829  mov     [rbp+0F0h+var_40], rax
0x14000e830  mov     rax, [rbp+0F0h+arg_38]
0x14000e837  xor     r12d, r12d
0x14000e83a  mov     r15, [rcx+180h]
0x14000e841  xorps   xmm0, xmm0
0x14000e844  mov     rdi, [rcx+80h]
0x14000e84b  xorps   xmm1, xmm1
0x14000e84e  mov     [rbp+0F0h+var_150], rdx
0x14000e852  mov     r14, rdx
0x14000e855  mov     rdx, [rbp+0F0h+arg_30]
0x14000e85c  mov     rsi, rcx
0x14000e85f  mov     [rbp+0F0h+var_148], r12d
0x14000e863  mov     qword ptr [rbp+0F0h+var_C8], r12
0x14000e867  mov     [rbp+0F0h+var_D0], r9
0x14000e86b  mov     [rbp+0F0h+pTargetName], r8
0x14000e86f  mov     [rbp+0F0h+var_138], rdx
0x14000e873  mov     [rbp+0F0h+var_C0], rax
0x14000e877  mov     [rbp+0F0h+var_158], r12
0x14000e87b  mov     [rbp+0F0h+var_160], r12
0x14000e87f  movups  xmmword ptr [rsp+1F0h+StringIn.Length], xmm0
0x14000e884  movups  xmmword ptr [rbp+0F0h+pInput.ulVersion], xmm1
0x14000e888  movups  xmmword ptr [rbp+0F0h+var_F8.ulVersion], xmm0
0x14000e88c  movups  [rbp+0F0h+var_118], xmm1
0x14000e890  movups  xmmword ptr [rbp+0F0h+phNewContext.dwLower], xmm0
0x14000e894  mov     rbx, [r15+18h]
0x14000e898  mov     [rbp+0F0h+pvLogonId], 3E4h
0x14000e8a0  movups  [rbp+0F0h+var_130], xmm0
0x14000e8a4  test    rax, rax
0x14000e8a7  jz      short loc_14000E8AC
0x14000e8a9  mov     [rax], r12b
0x14000e8ac  cmp     dword ptr [rdx], 0FFFFh
0x14000e8b2  lea     r13, WPP_GLOBAL_Control
0x14000e8b9  jbe     short loc_14000E8C5
0x14000e8bb  mov     edi, 0C000000Dh
0x14000e8c0  jmp     loc_14000F495
0x14000e8c5  movups  xmm0, xmmword ptr [r15+80h]
0x14000e8cd  movups  xmmword ptr [rsp+1F0h+StringIn.Length], xmm0
0x14000e8d2  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000e8d9  cmp     rcx, r13
0x14000e8dc  jz      short loc_14000E907
0x14000e8de  mov     eax, [rcx+2Ch]
0x14000e8e1  test    al, 8
0x14000e8e3  jz      short loc_14000E907
0x14000e8e5  cmp     byte ptr [rcx+29h], 4
0x14000e8e9  jb      short loc_14000E907
0x14000e8eb  mov     rcx, [rcx+18h]
0x14000e8ef  lea     r9, [rsp+1F0h+StringIn]
0x14000e8f4  mov     edx, 0Fh
0x14000e8f9  mov     [rsp+1F0h+pAuthData], r8
0x14000e8fe  call    WPP_SF_ZZ
0x14000e903  mov     rdx, [rbp+0F0h+var_138]
0x14000e907  mov     rax, [rsi+80h]
0x14000e90e  test    rax, rax
0x14000e911  jz      short loc_14000E923
0x14000e913  mov     rcx, [rax+10h]
0x14000e917  test    rcx, rcx
0x14000e91a  jz      short loc_14000E923
0x14000e91c  movups  xmm0, xmmword ptr [rcx]
0x14000e91f  movups  [rbp+0F0h+var_130], xmm0
0x14000e923  test    byte ptr [rbx+522h], 8
0x14000e92a  jz      short loc_14000E937
0x14000e92c  mov     [rdx], r12d
0x14000e92f  mov     edi, r12d
0x14000e932  jmp     loc_14000F4BE
0x14000e937  mov     rcx, [r15+208h]
0x14000e93e  mov     [rbp+0F0h+var_120], r12
0x14000e942  mov     [rsp+1F0h+var_17F], r12b
0x14000e947  test    rcx, rcx
0x14000e94a  jz      short loc_14000E98B
0x14000e94c  call    cs:__imp_RxReferenceSiloAndAcquireRundown
0x14000e953  nop     dword ptr [rax+rax+00h]
0x14000e958  test    rax, rax
0x14000e95b  jz      loc_14000EA79
0x14000e961  mov     rax, [r15+208h]
0x14000e968  test    rax, rax
0x14000e96b  jz      short loc_14000E973
0x14000e96d  mov     rcx, [rax+28h]
0x14000e971  jmp     short loc_14000E976
0x14000e973  mov     rcx, r12
0x14000e976  call    cs:__imp_PsAttachSiloToCurrentThread
0x14000e97d  nop     dword ptr [rax+rax+00h]
0x14000e982  mov     [rbp+0F0h+var_120], rax
0x14000e986  mov     [rsp+1F0h+var_17F], 1
0x14000e98b  mov     eax, cs:?globalMappingLuid@?1??RxIsGlobalMappingLuid@@9@9; `RxIsGlobalMappingLuid'::`2'::globalMappingLuid
0x14000e991  xor     r13b, r13b
0x14000e994  cmp     [rsi+60h], eax
0x14000e997  jnz     short loc_14000E9A4
0x14000e999  mov     eax, cs:dword_140046144
0x14000e99f  cmp     [rsi+64h], eax
0x14000e9a2  jz      short loc_14000E9AC
0x14000e9a4  mov     rax, [rsi+60h]
0x14000e9a8  mov     [rbp+0F0h+pvLogonId], rax
0x14000e9ac  lea     rcx, [r14+1E0h]
0x14000e9b3  mov     r9, 0FFFFF78000000008h
0x14000e9bd  cmp     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x14000e9c1  jz      short loc_14000E9D1
0x14000e9c3  cmp     qword ptr [r14+1E8h], 0FFFFFFFFFFFFFFFFh
0x14000e9cb  jnz     loc_14000F028
0x14000e9d1  mov     qword ptr [rbp+0F0h+pPackage.Length], 140012h
0x14000e9d9  xorps   xmm0, xmm0
0x14000e9dc  mov     qword ptr [rbp+0F0h+var_D8], r12
0x14000e9e0  lea     rax, aNegotiate; "Negotiate"
0x14000e9e7  mov     [rbp+0F0h+pPackage.Buffer], rax
0x14000e9eb  mov     ebx, 12h
0x14000e9f0  movups  xmmword ptr [rbp+0F0h+var_80.dwLower], xmm0
0x14000e9f4  test    rdi, rdi
0x14000e9f7  jz      short loc_14000EA01
0x14000e9f9  mov     rax, [rdi+8]
0x14000e9fd  mov     [rbp+0F0h+var_160], rax
0x14000ea01  xor     eax, eax
0x14000ea03  movups  [rbp+0F0h+var_B8], xmm0
0x14000ea07  mov     [rbp+0F0h+var_98], rax
0x14000ea0b  movups  [rbp+0F0h+var_A8], xmm0
0x14000ea0f  cmp     [rbp+0F0h+StringIn.Buffer], rax
0x14000ea13  jz      loc_14000EB66
0x14000ea19  lea     rdx, [rbp+0F0h+var_B8]
0x14000ea1d  xor     r14b, r14b
0x14000ea20  lea     rcx, [rsp+1F0h+StringIn]; StringIn
0x14000ea25  call    RfsServerNameInitialize
0x14000ea2a  test    eax, eax
0x14000ea2c  jns     short loc_14000EA83
0x14000ea2e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000ea35  lea     rbx, WPP_GLOBAL_Control
0x14000ea3c  cmp     rcx, rbx
0x14000ea3f  jz      loc_14000EB0C
0x14000ea45  mov     eax, [rcx+2Ch]
0x14000ea48  test    al, 1
0x14000ea4a  jz      loc_14000EB0C
0x14000ea50  cmp     byte ptr [rcx+29h], 1
0x14000ea54  jb      loc_14000EB0C
0x14000ea5a  mov     rcx, [rcx+18h]
0x14000ea5e  lea     r9, [rsp+1F0h+StringIn]
0x14000ea63  mov     edx, 0Ch
0x14000ea68  lea     r8, WPP_981a12f1532a3df13e243e2e48204374_Traceguids
0x14000ea6f  call    WPP_SF_Z
0x14000ea74  jmp     loc_14000EB0C
0x14000ea79  mov     edi, 0C0000120h
0x14000ea7e  jmp     loc_14000F495
0x14000ea83  call    cs:__imp_MRxSmbGetConfigurationBlock
0x14000ea8a  nop     dword ptr [rax+rax+00h]
0x14000ea8f  xor     edx, edx
0x14000ea91  mov     rdi, rax
0x14000ea94  lea     rcx, [rax+1C8h]
0x14000ea9b  call    cs:__imp_ExAcquirePushLockSharedEx
0x14000eaa2  nop     dword ptr [rax+rax+00h]
0x14000eaa7  xor     eax, eax
0x14000eaa9  xor     ebx, ebx
0x14000eaab  cmp     ax, [rdi+1D8h]
0x14000eab2  jnb     short loc_14000EAF0
0x14000eab4  nop     dword ptr [rax+00h]
0x14000eab8  nop     dword ptr [rax+rax+00000000h]
0x14000eac0  movzx   eax, bx
0x14000eac3  lea     rcx, [rax+rax*4]
0x14000eac7  mov     rax, [rdi+1D0h]
0x14000eace  lea     rdx, [rax+rcx*8]
0x14000ead2  lea     rcx, [rbp+0F0h+var_B8]
0x14000ead6  call    RfsServerNameEqual
0x14000eadb  test    al, al
0x14000eadd  jnz     short loc_14000EAED
0x14000eadf  inc     bx
0x14000eae2  cmp     bx, [rdi+1D8h]
0x14000eae9  jb      short loc_14000EAC0
0x14000eaeb  jmp     short loc_14000EAF0
0x14000eaed  mov     r14b, 1
0x14000eaf0  xor     edx, edx
0x14000eaf2  lea     rcx, [rdi+1C8h]
0x14000eaf9  call    cs:__imp_ExReleasePushLockSharedEx
0x14000eb00  nop     dword ptr [rax+rax+00h]
0x14000eb05  lea     rbx, WPP_GLOBAL_Control
0x14000eb0c  lea     rcx, [rbp+0F0h+var_B8]
0x14000eb10  call    RfsServerNameCleanup
0x14000eb15  movzx   eax, r14b
0x14000eb19  xchg    al, [rsi+1D5h]
0x14000eb1f  test    r14b, r14b
0x14000eb22  jz      short loc_14000EB6E
0x14000eb24  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000eb2b  cmp     rcx, rbx
0x14000eb2e  jz      loc_14000EE1B
0x14000eb34  mov     eax, [rcx+2Ch]
0x14000eb37  test    al, 8
0x14000eb39  jz      loc_14000EE1B
0x14000eb3f  cmp     byte ptr [rcx+29h], 4
0x14000eb43  jb      loc_14000EE1B
0x14000eb49  mov     rcx, [rcx+18h]
0x14000eb4d  lea     r9, [rsp+1F0h+StringIn]
0x14000eb52  mov     edx, 10h
0x14000eb57  mov     [rsp+1F0h+pAuthData], rsi
0x14000eb5c  call    WPP_SF_Zq
0x14000eb61  jmp     loc_14000EE1B
0x14000eb66  xchg    al, [rsi+1D5h]
0x14000eb6c  jmp     short loc_14000EB73
0x14000eb6e  mov     ebx, 12h
0x14000eb73  cmp     [rsi+290h], r13b
0x14000eb7a  jz      short loc_14000EBC3
0x14000eb7c  xor     r9d, r9d
0x14000eb7f  lea     rdx, [rbp+0F0h+var_160]
0x14000eb83  lea     rcx, [rsp+1F0h+StringIn]
0x14000eb88  call    HandleNTLMBlocking
0x14000eb8d  mov     edi, eax
0x14000eb8f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000eb96  lea     rdx, WPP_GLOBAL_Control
0x14000eb9d  cmp     rcx, rdx
0x14000eba0  jz      loc_14000EE08
0x14000eba6  mov     edx, [rcx+2Ch]
0x14000eba9  test    dl, 8
0x14000ebac  jz      loc_14000EE08
0x14000ebb2  cmp     byte ptr [rcx+29h], 4
0x14000ebb6  jb      loc_14000EE08
0x14000ebbc  mov     edx, 11h
0x14000ebc1  jmp     short loc_14000EC1C
0x14000ebc3  call    cs:__imp_MRxSmbGetConfigurationBlock
0x14000ebca  nop     dword ptr [rax+rax+00h]
0x14000ebcf  cmp     [rax+1C4h], r13b
0x14000ebd6  jz      short loc_14000EC34
0x14000ebd8  mov     r9d, 1
0x14000ebde  lea     rdx, [rbp+0F0h+var_160]
0x14000ebe2  lea     rcx, [rsp+1F0h+StringIn]
0x14000ebe7  call    HandleNTLMBlocking
0x14000ebec  mov     edi, eax
0x14000ebee  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000ebf5  lea     rdx, WPP_GLOBAL_Control
0x14000ebfc  cmp     rcx, rdx
0x14000ebff  jz      loc_14000EE08
0x14000ec05  mov     eax, [rcx+2Ch]
0x14000ec08  test    al, 8
0x14000ec0a  jz      loc_14000EE08
0x14000ec10  cmp     byte ptr [rcx+29h], 4
0x14000ec14  jb      loc_14000EE08
0x14000ec1a  mov     edx, ebx
0x14000ec1c  mov     rcx, [rcx+18h]
0x14000ec20  lea     r9, [rsp+1F0h+StringIn]
0x14000ec25  mov     [rsp+1F0h+pAuthData], rsi
0x14000ec2a  call    WPP_SF_Zq
0x14000ec2f  jmp     loc_14000EE08
0x14000ec34  xor     edx, edx
0x14000ec36  lea     rcx, [rsi+228h]
0x14000ec3d  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000ec44  nop     dword ptr [rax+rax+00h]
0x14000ec49  mov     r13d, [rsi+234h]
0x14000ec50  lea     rcx, [rsi+228h]
0x14000ec57  mov     r14d, [rsi+238h]
0x14000ec5e  xor     edx, edx
0x14000ec60  mov     r12d, [rsi+230h]
0x14000ec67  mov     [rsp+1F0h+var_17C], r13d
0x14000ec6c  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000ec73  nop     dword ptr [rax+rax+00h]
0x14000ec78  lea     edi, [r12+r13]
0x14000ec7c  mov     ebx, r12d
0x14000ec7f  test    edi, edi
0x14000ec81  jz      loc_14000ED44
0x14000ec87  cmp     edi, r14d
0x14000ec8a  jnz     loc_14000ED44
0x14000ec90  mov     rdx, cs:__imp_SmbCeIsServerTrustedZoneRunOnce; InitFn
0x14000ec97  lea     rcx, [rsi+1D8h]; RunOnce
0x14000ec9e  xor     r9d, r9d; Context
0x14000eca1  mov     r8, rsi; Parameter
0x14000eca4  call    cs:__imp_RtlRunOnceExecuteOnce
0x14000ecab  nop     dword ptr [rax+rax+00h]
0x14000ecb0  movzx   r13d, byte ptr [rsi+1E0h]
0x14000ecb8  test    eax, eax
0x14000ecba  jns     short loc_14000ECF5
0x14000ecbc  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000ecc3  lea     rdx, WPP_GLOBAL_Control
0x14000ecca  cmp     rcx, rdx
0x14000eccd  jz      short loc_14000ECF5
0x14000eccf  mov     edx, [rcx+2Ch]
0x14000ecd2  test    dl, 1
0x14000ecd5  jz      short loc_14000ECF5
0x14000ecd7  cmp     byte ptr [rcx+29h], 1
0x14000ecdb  jb      short loc_14000ECF5
0x14000ecdd  mov     rcx, [rcx+18h]
0x14000ece1  lea     r8, WPP_981a12f1532a3df13e243e2e48204374_Traceguids
0x14000ece8  mov     edx, 13h
0x14000eced  mov     r9d, eax
0x14000ecf0  call    WPP_SF_d
0x14000ecf5  test    r13b, r13b
0x14000ecf8  cmovz   ebx, edi
0x14000ecfb  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000ed02  lea     rax, WPP_GLOBAL_Control
0x14000ed09  cmp     rcx, rax
0x14000ed0c  jz      short loc_14000ED59
0x14000ed0e  mov     eax, [rcx+2Ch]
0x14000ed11  test    al, 8
0x14000ed13  jz      short loc_14000ED3F
0x14000ed15  cmp     byte ptr [rcx+29h], 2
0x14000ed19  jb      short loc_14000ED3F
0x14000ed1b  mov     rcx, [rcx+18h]
0x14000ed1f  lea     r8, WPP_981a12f1532a3df13e243e2e48204374_Traceguids
  ... truncated ...
```
