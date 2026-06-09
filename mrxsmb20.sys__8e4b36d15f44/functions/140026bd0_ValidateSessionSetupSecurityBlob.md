# ValidateSessionSetupSecurityBlob

- ea: `0x140026bd0`
- end: `0x14002774e`
- name: `ValidateSessionSetupSecurityBlob`
- size: `2942`
- prototype: `unsigned __int64 __fastcall(char *Parameter, struct _SecHandle *, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140053130`

## callees

- `0x14000e800`
- `0x1400122d0`
- `0x14001b4c0`
- `0x14001fc10`
- `0x140026bd0`
- `0x14002e488`
- `0x14002e610`
- `0x14002e984`
- `0x14002eb10`
- `0x14002f09c`
- `0x140037120`
- `0x1400372c0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400271c4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400271c4`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002742d`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002742d`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x140027583`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x140027583`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140026cd8`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140026cd8`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140026dd1`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140026e09`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140026fc5`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140026dd1`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140026e09`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140026fc5`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140026cfc`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140026f92`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140026cfc`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140026f92`
- `rdbss!RxDereferenceSiloAndReleaseRundown` at `0x140027592`
- `rdbss!RxDereferenceSiloAndReleaseRundown` at `0x140027592`
- `rdbss!RxReferenceSiloAndAcquireRundown` at `0x140026cae`
- `rdbss!RxReferenceSiloAndAcquireRundown` at `0x140026cae`
- `ksecdd!FreeContextBuffer` at `0x1400270ce`
- `ksecdd!FreeContextBuffer` at `0x140027564`
- `ksecdd!FreeContextBuffer` at `0x1400275af`
- `ksecdd!FreeContextBuffer` at `0x1400270ce`
- `ksecdd!FreeContextBuffer` at `0x140027564`
- `ksecdd!FreeContextBuffer` at `0x1400275af`
- `ksecdd!QueryContextAttributesW` at `0x140026d18`
- `ksecdd!QueryContextAttributesW` at `0x140026d62`
- `ksecdd!QueryContextAttributesW` at `0x140026da6`
- `ksecdd!QueryContextAttributesW` at `0x140026df2`
- `ksecdd!QueryContextAttributesW` at `0x140026fae`
- `ksecdd!QueryContextAttributesW` at `0x140026d18`
- `ksecdd!QueryContextAttributesW` at `0x140026d62`
- `ksecdd!QueryContextAttributesW` at `0x140026da6`
- `ksecdd!QueryContextAttributesW` at `0x140026df2`
- `ksecdd!QueryContextAttributesW` at `0x140026fae`
- `ksecdd!BCryptDestroyHash` at `0x1400271a3`
- `ksecdd!BCryptDestroyHash` at `0x1400271a3`
- `ksecdd!MapSecurityError` at `0x140026d26`
- `ksecdd!MapSecurityError` at `0x140026d70`
- `ksecdd!MapSecurityError` at `0x140026db4`
- `ksecdd!MapSecurityError` at `0x140026e17`
- `ksecdd!MapSecurityError` at `0x140026fd3`
- `ksecdd!MapSecurityError` at `0x140026d26`
- `ksecdd!MapSecurityError` at `0x140026d70`
- `ksecdd!MapSecurityError` at `0x140026db4`
- `ksecdd!MapSecurityError` at `0x140026e17`
- `ksecdd!MapSecurityError` at `0x140026fd3`
- `mrxsmb!VctReferenceEncryptionKey` at `0x1400273d4`
- `mrxsmb!VctReferenceEncryptionKey` at `0x1400273fa`
- `mrxsmb!VctReferenceEncryptionKey` at `0x1400273d4`
- `mrxsmb!VctReferenceEncryptionKey` at `0x1400273fa`
- `mrxsmb!VctCreateAndRegisterCryptoKeys` at `0x140027299`
- `mrxsmb!VctCreateAndRegisterCryptoKeys` at `0x140027299`
- `mrxsmb!SmbCryptoCreateSigningKey` at `0x140027131`
- `mrxsmb!SmbCryptoCreateSigningKey` at `0x140027131`
- `mrxsmb!SmbCryptoCreateApplicationKey` at `0x14002735e`
- `mrxsmb!SmbCryptoCreateApplicationKey` at `0x14002735e`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140026f0c`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140026f64`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14002701e`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140027083`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140026f0c`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140026f64`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14002701e`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140027083`
- `mrxsmb!SmbCeCheckServerEntryDialect` at `0x1400270fb`
- `mrxsmb!SmbCeCheckServerEntryDialect` at `0x14002732e`
- `mrxsmb!SmbCeCheckServerEntryDialect` at `0x1400270fb`
- `mrxsmb!SmbCeCheckServerEntryDialect` at `0x14002732e`

## pseudocode

```c
unsigned __int64 __fastcall ValidateSessionSetupSecurityBlob(char *Parameter, struct _SecHandle *a2, __int64 a3)
{
  __int64 v4; // r12
  int v6; // eax
  unsigned __int64 v8; // rbx
  unsigned __int64 v9; // rdi
  _QWORD *v10; // r14
  __int64 v11; // rcx
  SECURITY_STATUS v12; // eax
  NTSTATUS v13; // eax
  SECURITY_STATUS v14; // eax
  SECURITY_STATUS ContextAttributesW; // eax
  SECURITY_STATUS v16; // ebx
  NTSTATUS v17; // eax
  int v18; // edx
  __int64 v19; // rcx
  int v20; // r9d
  int v21; // edx
  ULONG_PTR dwUpper; // rax
  __int64 v23; // rcx
  int v24; // ecx
  int v25; // r8d
  __int64 ConfigurationBlock; // rax
  SECURITY_STATUS v27; // ebx
  NTSTATUS v28; // eax
  PVOID v29; // rcx
  int *v30; // r15
  ULONG_PTR v31; // rbx
  __int64 v32; // rdi
  __int64 v33; // rax
  char v34; // r13
  int v35; // edx
  int v36; // r8d
  __int64 v37; // rdi
  __int64 v38; // rbx
  __int64 v39; // rax
  int v40; // edx
  int v41; // r8d
  size_t v42; // r8
  void *dwLower; // rcx
  void *v44; // rcx
  __int64 v45; // rdx
  __int64 v46; // r8
  __int64 v47; // r9
  ULONG_PTR v48; // r10
  int v49; // ecx
  __int64 v50; // r8
  __int64 v51; // rdx
  __int64 v52; // r8
  __int64 v53; // rcx
  _OWORD *v54; // rcx
  void *v55; // rdx
  size_t v56; // r8
  char v57; // al
  bool v58; // zf
  __int64 v59; // rcx
  KIRQL v60; // dl
  char v61; // r15
  int v62; // eax
  char v63; // dl
  char v64; // r13
  char v65; // al
  _BYTE *v66; // rcx
  __int64 v67; // rax
  __int128 *v68; // rax
  PVOID v70; // r10
  unsigned __int16 v71; // r15
  __int64 v72; // r8
  unsigned int v73; // r13d
  __int64 v74; // rax
  __int16 *v75; // rax
  int v76; // edx
  PEVENT_DATA_DESCRIPTOR v77; // [rsp+28h] [rbp-E0h]
  __int64 v78; // [rsp+30h] [rbp-D8h]
  unsigned __int16 v79; // [rsp+88h] [rbp-80h]
  char v80; // [rsp+8Ah] [rbp-7Eh]
  _BYTE v81[13]; // [rsp+8Bh] [rbp-7Dh] BYREF
  PVOID pvContextBuffer; // [rsp+98h] [rbp-70h] BYREF
  int v83; // [rsp+A0h] [rbp-68h]
  _DWORD Size[5]; // [rsp+A4h] [rbp-64h] BYREF
  int pBuffer; // [rsp+B8h] [rbp-50h] BYREF
  ULONG_PTR *p_dwUpper; // [rsp+C0h] [rbp-48h] BYREF
  void *Src; // [rsp+C8h] [rbp-40h] BYREF
  PVOID v88; // [rsp+D0h] [rbp-38h] BYREF
  __int64 v89; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v90; // [rsp+E0h] [rbp-28h] BYREF
  __int64 v91; // [rsp+F0h] [rbp-18h]
  __int64 v92; // [rsp+F8h] [rbp-10h]
  __int64 v93; // [rsp+100h] [rbp-8h]
  __int64 v94; // [rsp+108h] [rbp+0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v95; // [rsp+118h] [rbp+10h] BYREF
  __int64 *v96; // [rsp+138h] [rbp+30h]
  __int64 v97; // [rsp+140h] [rbp+38h]
  __int64 *v98; // [rsp+148h] [rbp+40h]
  __int64 v99; // [rsp+150h] [rbp+48h]
  _DWORD *v100; // [rsp+158h] [rbp+50h]
  __int64 v101; // [rsp+160h] [rbp+58h]
  void **p_Src; // [rsp+168h] [rbp+60h]
  __int64 v103; // [rsp+170h] [rbp+68h]
  ULONG_PTR **p_p_dwUpper; // [rsp+178h] [rbp+70h]
  __int64 v105; // [rsp+180h] [rbp+78h]
  __int128 v106; // [rsp+188h] [rbp+80h] BYREF

  v4 = 16;
  pvContextBuffer = (PVOID)*((_QWORD *)Parameter + 48);
  v6 = *(_DWORD *)(a3 + 1064);
  LODWORD(v89) = 0;
  v88 = 0;
  *(_DWORD *)&v81[5] = 0;
  v81[0] = 0;
  v93 = 0;
  v80 = 0;
  pBuffer = 0;
  v91 = 0;
  v92 = 0;
  *(_OWORD *)&Size[1] = 0;
  if ( v6 )
  {
    v8 = BuildSessionSetupSecurityBlob(Parameter, v6, 0, (__int64)&v89, (__int64)v81);
    v9 = HIDWORD(v8);
    if ( (v8 & 0x80000000) != 0LL )
      goto LABEL_93;
  }
  else
  {
    LODWORD(v9) = 0;
  }
  v10 = (char *)pvContextBuffer + 520;
  if ( *((_QWORD *)pvContextBuffer + 65) )
  {
    if ( !RxReferenceSiloAndAcquireRundown() )
    {
      LODWORD(v8) = -1073741536;
      goto LABEL_94;
    }
    if ( *v10 )
      v11 = *(_QWORD *)(*v10 + 40LL);
    else
      v11 = 0;
    v93 = PsAttachSiloToCurrentThread(v11);
    v80 = 1;
  }
  p_dwUpper = &a2[28].dwUpper;
  ExAcquirePushLockSharedEx(&a2[28].dwUpper, 0);
  v12 = QueryContextAttributesW(a2 + 29, 0x25u, &pBuffer);
  v13 = MapSecurityError(v12);
  LODWORD(v8) = v13;
  if ( v13 == -1073741637 )
  {
    pBuffer = 0;
  }
  else if ( v13 < 0 )
  {
LABEL_16:
    LODWORD(v9) = 204;
    ExReleasePushLockSharedEx(p_dwUpper, 0);
    goto LABEL_94;
  }
  v14 = QueryContextAttributesW(a2 + 29, 0xAu, &v88);
  LODWORD(v8) = MapSecurityError(v14);
  if ( (_DWORD)v8 )
    goto LABEL_16;
  v79 = *((_WORD *)v88 + 3);
  v81[2] = v79 == 10;
  ContextAttributesW = QueryContextAttributesW(a2 + 29, 0xEu, &v81[5]);
  LODWORD(v8) = MapSecurityError(ContextAttributesW);
  if ( (_DWORD)v8 )
    goto LABEL_16;
  v16 = QueryContextAttributesW(a2 + 29, 9u, &Size[1]);
  ExReleasePushLockSharedEx(&a2[28].dwUpper, 0);
  v17 = MapSecurityError(v16);
  v20 = v79;
  LODWORD(v8) = v17;
  if ( v79 == 10 )
  {
    v21 = *(_DWORD *)&v81[5] >> 1;
    LOBYTE(v21) = (v81[5] & 2) != 0;
    v83 = v21;
  }
  else
  {
    LOBYTE(v18) = 0;
    v83 = v18;
    if ( (v81[5] & 2) != 0 )
      LOBYTE(v83) = (*(_DWORD *)v88 & 0x10000) != 0;
  }
  if ( v17 )
  {
    LODWORD(v9) = 202;
  }
  else
  {
    if ( (unsigned int)dword_140046050 > 5 )
    {
      v19 = qword_140046068;
      if ( (qword_140046060 & 0x400000000000LL) != 0 && (qword_140046068 & 0x400000000000LL) == qword_140046068 )
      {
        v94 = 0x2000000;
        v96 = &v94;
        v98 = &v90;
        Size[0] = Size[1];
        v100 = Size;
        dwUpper = a2[24].dwUpper;
        v97 = 8;
        v90 = 1;
        v99 = 8;
        v101 = 4;
        v23 = *(unsigned int *)(dwUpper + 584);
        p_Src = &Src;
        LODWORD(Src) = v23;
        v103 = 4;
        v24 = *(_DWORD *)(MRxSmbGetConfigurationBlock(v23) + 224);
        p_p_dwUpper = &p_dwUpper;
        LODWORD(p_dwUpper) = v24;
        v105 = 4;
        tlgWriteAgg(v24, (int)&dword_140040304, v25, 7, &v95);
      }
    }
    if ( !*(_BYTE *)(a3 + 1081) )
    {
      if ( !pBuffer )
      {
        ConfigurationBlock = MRxSmbGetConfigurationBlock(v19);
        if ( Size[1] < *(_DWORD *)(ConfigurationBlock + 224) )
        {
          pvContextBuffer = 0;
          ExAcquirePushLockSharedEx(&a2[28].dwUpper, 0);
          v27 = QueryContextAttributesW(a2 + 29, 1u, &pvContextBuffer);
          ExReleasePushLockSharedEx(&a2[28].dwUpper, 0);
          v28 = MapSecurityError(v27);
          v29 = pvContextBuffer;
          v30 = &dword_14003EE4C;
          if ( v28 >= 0 )
            v30 = (int *)pvContextBuffer;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            v31 = a2[24].dwUpper;
            v32 = *((_QWORD *)Parameter + 55);
            v33 = MRxSmbGetConfigurationBlock(pvContextBuffer);
            v34 = v79;
            WPP_SF_DDiqdS(
              WPP_GLOBAL_Control->AttachedDevice,
              v35,
              v36,
              *(_DWORD *)(v33 + 224),
              Size[1],
              v32,
              v31,
              v79,
              (__int64)v30);
            v29 = pvContextBuffer;
          }
          else
          {
            v34 = v79;
          }
          if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x40000000) != 0 )
          {
            v37 = *((_QWORD *)Parameter + 48);
            v38 = *((_QWORD *)Parameter + 55);
            v39 = MRxSmbGetConfigurationBlock(v29);
            McTemplateK0hzr0qqxzq_EtwWriteTransfer(
              *(_DWORD *)(v39 + 224),
              v40,
              v41,
              *(unsigned __int16 *)(v37 + 80),
              *(_QWORD *)(v37 + 88),
              Size[1],
              *(_DWORD *)(v39 + 224),
              v38,
              (__int64)v30,
              v34);
            v29 = pvContextBuffer;
          }
          if ( v29 )
            FreeContextBuffer(v29);
          LODWORD(v8) = -1073740521;
          LODWORD(v9) = 206;
          goto LABEL_94;
        }
      }
      if ( (unsigned __int8)SmbCeCheckServerEntryDialect(a2[27].dwLower, 3, 0, 0) )
      {
        LODWORD(v78) = 16;
        v77 = (PEVENT_DATA_DESCRIPTOR)&v106;
        LODWORD(v8) = SmbCryptoCreateSigningKey(
                        *(_QWORD *)&Size[3],
                        Size[1],
                        *(_QWORD *)(a3 + 1040),
                        *(unsigned int *)(a3 + 1048));
        if ( (v8 & 0x80000000) != 0LL )
        {
          LODWORD(v9) = 202;
          goto LABEL_94;
        }
      }
      else
      {
        v42 = 16;
        v106 = 0;
        if ( Size[1] <= 0x10u )
          v42 = Size[1];
        memmove(&v106, *(const void **)&Size[3], v42);
      }
      if ( *(_BYTE *)(a3 + 1083) || (*((_OWORD *)Parameter + 38) = v106, *(_BYTE *)(a3 + 1083)) )
      {
        dwLower = (void *)a2[31].dwLower;
        if ( dwLower )
        {
          BCryptDestroyHash(dwLower);
          v44 = (void *)a2[31].dwUpper;
          a2[31].dwLower = 0;
          ExFreePoolWithTag(v44, 0x6D536F48u);
          a2[31].dwUpper = 0;
        }
      }
      LODWORD(v8) = Smb2InitializeBindingObjectHash(a2, &v106);
      if ( !*(_BYTE *)(a3 + 1083) )
      {
        v48 = a2[24].dwUpper;
        v49 = *(_DWORD *)(v48 + 320);
        if ( ((v49 - 1) & 0xFFFFFFFC) == 0 && v49 != 3 && (*((_DWORD *)pvContextBuffer + 179) & 0x8000) != 0 )
        {
          v50 = *(unsigned int *)(v48 + 584);
          if ( (_DWORD)v50 )
          {
            if ( (*(_DWORD *)&v81[5] & 0x40000) == 0 && (*((_DWORD *)Parameter + 1) & 2) == 0 )
            {
              v78 = *(_QWORD *)(a3 + 1040);
              LODWORD(v77) = Size[1];
              LODWORD(v8) = VctCreateAndRegisterCryptoKeys(
                              *(_QWORD *)(v48 + 504),
                              *((_QWORD *)Parameter + 55),
                              v50,
                              *(_QWORD *)&Size[3]);
              if ( (v8 & 0x80000000) != 0LL )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) )
                {
                  WPP_SF_Dqi(
                    WPP_GLOBAL_Control->AttachedDevice,
                    v51,
                    v52,
                    (unsigned int)v8,
                    a2[24].dwUpper,
                    *((_QWORD *)Parameter + 55));
                }
                LODWORD(v9) = 203;
                goto LABEL_94;
              }
            }
          }
        }
        v53 = *((_QWORD *)Parameter + 48);
        LODWORD(p_dwUpper) = *(_DWORD *)(a3 + 1048);
        v90 = *(_QWORD *)(a3 + 1040);
        Size[0] = Size[1];
        Src = *(void **)&Size[3];
        if ( (unsigned __int8)SmbCeCheckServerEntryDialect(v53, 3, 0, 0) )
        {
          LODWORD(v78) = 16;
          LODWORD(v77) = (_DWORD)Parameter + 448;
          SmbCryptoCreateApplicationKey(Src, Size[0], v90, (unsigned int)p_dwUpper);
        }
        else
        {
          v54 = Parameter + 448;
          v55 = Src;
          v56 = 16;
          if ( Size[0] < 0x10u )
            v56 = Size[0];
          *v54 = 0;
          memmove(v54, v55, v56);
        }
      }
      if ( !*(_BYTE *)(a3 + 1081) )
      {
        v57 = SmbCeAcquireSpinLock(*((_QWORD *)Parameter + 3), v45, v46, v47);
        v58 = *(_BYTE *)(a3 + 1083) == 0;
        v81[1] = v57;
        if ( v58 )
        {
          *((_QWORD *)Parameter + 78) = v91;
          *((_QWORD *)Parameter + 79) = v92;
        }
        if ( *((_QWORD *)Parameter + 78) )
        {
          VctReferenceEncryptionKey();
          a2[33].dwLower = *((_QWORD *)Parameter + 78);
        }
        if ( *((_QWORD *)Parameter + 79) )
        {
          VctReferenceEncryptionKey();
          a2[33].dwUpper = *((_QWORD *)Parameter + 79);
        }
        v59 = *((_QWORD *)Parameter + 3);
        v60 = v81[1];
        *(_DWORD *)(v59 + 2352) = -1;
        ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v59 + 1920), v60);
      }
    }
    v20 = v79;
  }
  if ( *(_BYTE *)(a3 + 1083) )
  {
LABEL_93:
    v10 = (char *)pvContextBuffer + 520;
    goto LABEL_94;
  }
  v61 = 0;
  if ( (*(_DWORD *)&v81[5] & 0x40000) != 0 )
  {
    v62 = *((_DWORD *)Parameter + 1);
    if ( (v62 & 4) != 0 || (v62 & 2) != 0 )
    {
      LODWORD(v8) = -1073741629;
      LODWORD(v9) = 205;
      goto LABEL_94;
    }
    v61 = 1;
  }
  v63 = Parameter[466];
  v64 = v83;
  if ( !v63 || (_BYTE)v83 )
    goto LABEL_91;
  if ( Parameter[465] )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qZdddd(
        WPP_GLOBAL_Control->AttachedDevice,
        31,
        (unsigned __int16)v20,
        (_DWORD)Parameter,
        (__int64)pvContextBuffer + 80,
        *((_WORD *)Parameter + 286),
        v20,
        v63,
        0);
    }
LABEL_91:
    v65 = v81[2];
    Parameter[466] = v64;
    *((_WORD *)Parameter + 286) = v79;
    Parameter[465] = v65;
    if ( v61 )
      *((_DWORD *)Parameter + 1) |= 1u;
    goto LABEL_93;
  }
  v70 = pvContextBuffer;
  v71 = 0;
  v72 = 0;
  LODWORD(v8) = -1073741240;
  v90 = 0;
  LODWORD(v9) = 201;
  v73 = *((unsigned __int8 *)pvContextBuffer + 737);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_qZdddd(
      WPP_GLOBAL_Control->AttachedDevice,
      32,
      (unsigned __int16)v20,
      (_DWORD)Parameter,
      (__int64)pvContextBuffer + 80,
      *((_WORD *)Parameter + 286),
      v20,
      v63,
      0);
    v72 = v90;
    v70 = pvContextBuffer;
  }
  v74 = *((_QWORD *)Parameter + 16);
  if ( v74 )
  {
    v75 = *(__int16 **)(v74 + 16);
    if ( v75 )
    {
      v71 = *v75;
      v72 = *((_QWORD *)v75 + 1);
    }
  }
  if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x40000000) != 0 )
  {
    v76 = 1;
    if ( (v73 & 0xC) != 0xC )
      v76 = ((v73 & 3) == 3) | (v73 >> 5) & 1;
    McTemplateK0qqqxhzr4hzr6hhttt_EtwWriteTransfer(
      *((_WORD *)v70 + 40) >> 1,
      v76,
      v72,
      v20,
      (_DWORD)v77,
      v78,
      *((_QWORD *)Parameter + 12),
      *((_WORD *)v70 + 40) >> 1,
      *((_QWORD *)v70 + 11),
      v71 >> 1,
      v72,
      *((_WORD *)Parameter + 286),
      v79,
      Parameter[466],
      0,
      v76);
  }
LABEL_94:
  v66 = *(_BYTE **)&Size[3];
  if ( *(_QWORD *)&Size[3] )
  {
    v67 = Size[1];
    if ( Size[1] )
    {
      do
      {
        *v66++ = 0;
        --v67;
      }
      while ( v67 );
      v66 = *(_BYTE **)&Size[3];
    }
    FreeContextBuffer(v66);
    *(_QWORD *)&Size[3] = 0;
    Size[1] = 0;
  }
  if ( v80 )
  {
    PsDetachSiloFromCurrentThread(v93);
    RxDereferenceSiloAndReleaseRundown(*v10);
  }
  if ( v88 )
    FreeContextBuffer(v88);
  v68 = &v106;
  do
  {
    *(_BYTE *)v68 = 0;
    v68 = (__int128 *)((char *)v68 + 1);
    --v4;
  }
  while ( v4 );
  return (unsigned int)v8 | ((unsigned __int64)(unsigned int)v9 << 32);
}

```

## disassembly

```asm
0x140026bd0  mov     r11, rsp
0x140026bd3  push    rbp
0x140026bd4  push    rbx
0x140026bd5  push    rdi
0x140026bd6  lea     rbp, [r11-0D8h]
0x140026bdd  sub     rsp, 1C0h
0x140026be4  mov     rax, cs:__security_cookie
0x140026beb  xor     rax, rsp
0x140026bee  mov     [rbp+0D0h+var_40], rax
0x140026bf5  mov     rax, [rcx+180h]
0x140026bfc  xor     ebx, ebx
0x140026bfe  mov     [r11+20h], rsi
0x140026c02  xorps   xmm0, xmm0
0x140026c05  mov     [r11-20h], r12
0x140026c09  mov     rsi, rcx
0x140026c0c  mov     [r11-28h], r13
0x140026c10  mov     r12d, 10h
0x140026c16  mov     [rbp+0D0h+pvContextBuffer], rax
0x140026c1a  mov     r13, rdx
0x140026c1d  mov     eax, [r8+428h]
0x140026c24  mov     [r11-30h], r14
0x140026c28  mov     [r11-38h], r15
0x140026c2c  mov     r15, r8
0x140026c2f  mov     dword ptr [rbp+0D0h+var_100], ebx
0x140026c32  mov     [rbp+0D0h+var_108], rbx
0x140026c36  mov     dword ptr [rbp+0D0h+var_14D+5], ebx
0x140026c39  mov     [rbp+0D0h+var_14D], bl
0x140026c3c  mov     [rbp+0D0h+var_D8], rbx
0x140026c40  mov     [rbp+0D0h+var_14E], bl
0x140026c43  mov     [rbp+0D0h+pBuffer], ebx
0x140026c46  mov     [rbp+0D0h+var_E8], rbx
0x140026c4a  mov     [rbp+0D0h+var_E0], rbx
0x140026c4e  movups  xmmword ptr [rbp+0D0h+Size+4], xmm0
0x140026c52  test    eax, eax
0x140026c54  jz      short loc_140026CD1
0x140026c56  mov     r9, [r15+420h]
0x140026c5d  lea     rcx, [rbp+0D0h+var_14D]
0x140026c61  mov     [rsp+1D0h+var_198], rcx; __int64
0x140026c66  add     r8, 440h
0x140026c6d  lea     rcx, [rbp+0D0h+var_100]
0x140026c71  mov     [rsp+1D0h+var_1A0], rcx; __int64
0x140026c76  mov     rcx, rsi; Parameter
0x140026c79  mov     [rsp+1D0h+var_1A8], rbx; __int64
0x140026c7e  mov     dword ptr [rsp+1D0h+var_1B0], eax; int
0x140026c82  call    BuildSessionSetupSecurityBlob
0x140026c87  mov     rdi, rax
0x140026c8a  mov     rbx, rax
0x140026c8d  shr     rdi, 20h
0x140026c91  test    eax, eax
0x140026c93  js      loc_14002751F
0x140026c99  xor     ebx, ebx
0x140026c9b  mov     r14, [rbp+0D0h+pvContextBuffer]
0x140026c9f  add     r14, 208h
0x140026ca6  mov     rcx, [r14]
0x140026ca9  test    rcx, rcx
0x140026cac  jz      short loc_140026CEC
0x140026cae  call    cs:__imp_RxReferenceSiloAndAcquireRundown
0x140026cb5  nop     dword ptr [rax+rax+00h]
0x140026cba  test    rax, rax
0x140026cbd  jz      loc_140026D44
0x140026cc3  mov     rax, [r14]
0x140026cc6  test    rax, rax
0x140026cc9  jz      short loc_140026CD5
0x140026ccb  mov     rcx, [rax+28h]
0x140026ccf  jmp     short loc_140026CD8
0x140026cd1  mov     edi, ebx
0x140026cd3  jmp     short loc_140026C9B
0x140026cd5  mov     rcx, rbx
0x140026cd8  call    cs:__imp_PsAttachSiloToCurrentThread
0x140026cdf  nop     dword ptr [rax+rax+00h]
0x140026ce4  mov     [rbp+0D0h+var_D8], rax
0x140026ce8  mov     [rbp+0D0h+var_14E], 1
0x140026cec  lea     rax, [r13+1C8h]
0x140026cf3  xor     edx, edx
0x140026cf5  mov     rcx, rax
0x140026cf8  mov     [rbp+0D0h+var_118], rax
0x140026cfc  call    cs:__imp_ExAcquirePushLockSharedEx
0x140026d03  nop     dword ptr [rax+rax+00h]
0x140026d08  lea     rcx, [r13+1D0h]; phContext
0x140026d0f  mov     edx, 25h ; '%'; ulAttribute
0x140026d14  lea     r8, [rbp+0D0h+pBuffer]; pBuffer
0x140026d18  call    cs:__imp_QueryContextAttributesW
0x140026d1f  nop     dword ptr [rax+rax+00h]
0x140026d24  mov     ecx, eax; SecStatus
0x140026d26  call    cs:__imp_MapSecurityError
0x140026d2d  nop     dword ptr [rax+rax+00h]
0x140026d32  mov     ebx, eax
0x140026d34  cmp     eax, 0C00000BBh
0x140026d39  jnz     short loc_140026D4E
0x140026d3b  mov     [rbp+0D0h+pBuffer], 0
0x140026d42  jmp     short loc_140026D52
0x140026d44  mov     ebx, 0C0000120h
0x140026d49  jmp     loc_14002752A
0x140026d4e  test    eax, eax
0x140026d50  js      short loc_140026DC6
0x140026d52  lea     r8, [rbp+0D0h+var_108]; pBuffer
0x140026d56  mov     edx, 0Ah; ulAttribute
0x140026d5b  lea     rcx, [r13+1D0h]; phContext
0x140026d62  call    cs:__imp_QueryContextAttributesW
0x140026d69  nop     dword ptr [rax+rax+00h]
0x140026d6e  mov     ecx, eax; SecStatus
0x140026d70  call    cs:__imp_MapSecurityError
0x140026d77  nop     dword ptr [rax+rax+00h]
0x140026d7c  mov     ebx, eax
0x140026d7e  test    eax, eax
0x140026d80  jnz     short loc_140026DC6
0x140026d82  mov     rax, [rbp+0D0h+var_108]
0x140026d86  lea     r8, [rbp+0D0h+var_14D+5]; pBuffer
0x140026d8a  mov     edx, 0Eh; ulAttribute
0x140026d8f  lea     rcx, [r13+1D0h]; phContext
0x140026d96  movzx   eax, word ptr [rax+6]
0x140026d9a  cmp     ax, 0Ah
0x140026d9e  mov     [rbp+0D0h+var_150], ax
0x140026da2  setz    [rbp+0D0h+var_14D+2]
0x140026da6  call    cs:__imp_QueryContextAttributesW
0x140026dad  nop     dword ptr [rax+rax+00h]
0x140026db2  mov     ecx, eax; SecStatus
0x140026db4  call    cs:__imp_MapSecurityError
0x140026dbb  nop     dword ptr [rax+rax+00h]
0x140026dc0  mov     ebx, eax
0x140026dc2  test    eax, eax
0x140026dc4  jz      short loc_140026DE2
0x140026dc6  mov     rcx, [rbp+0D0h+var_118]
0x140026dca  xor     edx, edx
0x140026dcc  mov     edi, 0CCh
0x140026dd1  call    cs:__imp_ExReleasePushLockSharedEx
0x140026dd8  nop     dword ptr [rax+rax+00h]
0x140026ddd  jmp     loc_14002752A
0x140026de2  lea     r8, [rbp+0D0h+Size+4]; pBuffer
0x140026de6  mov     edx, 9; ulAttribute
0x140026deb  lea     rcx, [r13+1D0h]; phContext
0x140026df2  call    cs:__imp_QueryContextAttributesW
0x140026df9  nop     dword ptr [rax+rax+00h]
0x140026dfe  xor     edx, edx
0x140026e00  lea     rcx, [r13+1C8h]
0x140026e07  mov     ebx, eax
0x140026e09  call    cs:__imp_ExReleasePushLockSharedEx
0x140026e10  nop     dword ptr [rax+rax+00h]
0x140026e15  mov     ecx, ebx; SecStatus
0x140026e17  call    cs:__imp_MapSecurityError
0x140026e1e  nop     dword ptr [rax+rax+00h]
0x140026e23  movzx   r9d, [rbp+0D0h+var_150]
0x140026e28  mov     r8d, 1
0x140026e2e  mov     ebx, eax
0x140026e30  cmp     r9w, 0Ah
0x140026e35  jnz     short loc_140026E44
0x140026e37  mov     edx, dword ptr [rbp+0D0h+var_14D+5]
0x140026e3a  shr     edx, 1
0x140026e3c  and     dl, r8b
0x140026e3f  mov     [rbp+0D0h+var_138], edx
0x140026e42  jmp     short loc_140026E63
0x140026e44  xor     dl, dl
0x140026e46  test    [rbp+0D0h+var_14D+5], 2
0x140026e4a  mov     [rbp+0D0h+var_138], edx
0x140026e4d  jz      short loc_140026E63
0x140026e4f  mov     rax, [rbp+0D0h+var_108]
0x140026e53  test    dword ptr [rax], 10000h
0x140026e59  movzx   eax, dl
0x140026e5c  cmovnz  eax, r8d
0x140026e60  mov     byte ptr [rbp+0D0h+var_138], al
0x140026e63  test    ebx, ebx
0x140026e65  jnz     loc_140027440
0x140026e6b  mov     eax, cs:dword_140046050
0x140026e71  cmp     eax, 5
0x140026e74  jbe     loc_140026F4C
0x140026e7a  mov     rcx, cs:qword_140046068
0x140026e81  mov     rdx, 400000000000h
0x140026e8b  mov     rax, cs:qword_140046060
0x140026e92  test    rdx, rax
0x140026e95  jz      loc_140026F4C
0x140026e9b  mov     rax, rcx
0x140026e9e  and     rax, rdx
0x140026ea1  cmp     rax, rcx
0x140026ea4  jnz     loc_140026F4C
0x140026eaa  lea     rax, [rbp+0D0h+var_D0]
0x140026eae  mov     [rbp+0D0h+var_D0], 2000000h
0x140026eb6  mov     [rbp+0D0h+var_A0], rax
0x140026eba  lea     rax, [rbp+0D0h+var_F8]
0x140026ebe  mov     [rbp+0D0h+var_90], rax
0x140026ec2  mov     eax, dword ptr [rbp+0D0h+Size+4]
0x140026ec5  mov     dword ptr [rbp+0D0h+Size], eax
0x140026ec8  lea     rax, [rbp+0D0h+Size]
0x140026ecc  mov     [rbp+0D0h+var_80], rax
0x140026ed0  mov     rax, [r13+188h]
0x140026ed7  mov     [rbp+0D0h+var_98], 8
0x140026edf  mov     [rbp+0D0h+var_F8], r8
0x140026ee3  mov     [rbp+0D0h+var_88], 8
0x140026eeb  mov     [rbp+0D0h+var_78], 4
0x140026ef3  mov     ecx, [rax+248h]
0x140026ef9  lea     rax, [rbp+0D0h+Src]
0x140026efd  mov     [rbp+0D0h+var_70], rax
0x140026f01  mov     dword ptr [rbp+0D0h+Src], ecx
0x140026f04  mov     [rbp+0D0h+var_68], 4
0x140026f0c  call    cs:__imp_MRxSmbGetConfigurationBlock
0x140026f13  nop     dword ptr [rax+rax+00h]
0x140026f18  mov     r9d, 7; int
0x140026f1e  lea     rdx, dword_140040304; int
0x140026f25  mov     ecx, [rax+0E0h]; int
0x140026f2b  lea     rax, [rbp+0D0h+var_118]
0x140026f2f  mov     [rbp+0D0h+var_60], rax
0x140026f33  lea     rax, [rbp+0D0h+var_C0]
0x140026f37  mov     [rsp+1D0h+var_1B0], rax; PEVENT_DATA_DESCRIPTOR
0x140026f3c  mov     dword ptr [rbp+0D0h+var_118], ecx
0x140026f3f  mov     [rbp+0D0h+var_58], 4
0x140026f47  call    _tlgWriteAgg
0x140026f4c  cmp     byte ptr [r15+439h], 0
0x140026f54  jnz     loc_140027439
0x140026f5a  cmp     [rbp+0D0h+pBuffer], 0
0x140026f5e  jnz     loc_1400270E9
0x140026f64  call    cs:__imp_MRxSmbGetConfigurationBlock
0x140026f6b  nop     dword ptr [rax+rax+00h]
0x140026f70  mov     r8d, [rax+0E0h]
0x140026f77  cmp     dword ptr [rbp+0D0h+Size+4], r8d
0x140026f7b  jnb     loc_1400270E9
0x140026f81  xor     edx, edx
0x140026f83  mov     [rbp+0D0h+pvContextBuffer], 0
0x140026f8b  lea     rcx, [r13+1C8h]
0x140026f92  call    cs:__imp_ExAcquirePushLockSharedEx
0x140026f99  nop     dword ptr [rax+rax+00h]
0x140026f9e  lea     r8, [rbp+0D0h+pvContextBuffer]; pBuffer
0x140026fa2  mov     edx, 1; ulAttribute
0x140026fa7  lea     rcx, [r13+1D0h]; phContext
0x140026fae  call    cs:__imp_QueryContextAttributesW
0x140026fb5  nop     dword ptr [rax+rax+00h]
0x140026fba  xor     edx, edx
0x140026fbc  lea     rcx, [r13+1C8h]
0x140026fc3  mov     ebx, eax
0x140026fc5  call    cs:__imp_ExReleasePushLockSharedEx
0x140026fcc  nop     dword ptr [rax+rax+00h]
0x140026fd1  mov     ecx, ebx; SecStatus
0x140026fd3  call    cs:__imp_MapSecurityError
0x140026fda  nop     dword ptr [rax+rax+00h]
0x140026fdf  mov     rcx, [rbp+0D0h+pvContextBuffer]
0x140026fe3  lea     r15, dword_14003EE4C
0x140026fea  test    eax, eax
0x140026fec  cmovns  r15, rcx
0x140026ff0  mov     rdx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140026ff7  lea     rax, WPP_GLOBAL_Control
0x140026ffe  cmp     rdx, rax
0x140027001  jz      short loc_140027067
0x140027003  mov     eax, [rdx+2Ch]
0x140027006  test    al, 8
0x140027008  jz      short loc_140027067
0x14002700a  cmp     byte ptr [rdx+29h], 1
0x14002700e  jb      short loc_140027067
0x140027010  mov     rbx, [r13+188h]
0x140027017  mov     rdi, [rsi+1B8h]
0x14002701e  call    cs:__imp_MRxSmbGetConfigurationBlock
0x140027025  nop     dword ptr [rax+rax+00h]
0x14002702a  mov     rcx, cs:WPP_GLOBAL_Control
0x140027031  movzx   r13d, [rbp+0D0h+var_150]
0x140027036  mov     qword ptr [rsp+1D0h+var_190], r15
0x14002703b  mov     r9d, [rax+0E0h]
0x140027042  mov     eax, dword ptr [rbp+0D0h+Size+4]
0x140027045  mov     rcx, [rcx+18h]
0x140027049  mov     dword ptr [rsp+1D0h+var_198], r13d
0x14002704e  mov     [rsp+1D0h+var_1A0], rbx
0x140027053  mov     [rsp+1D0h+var_1A8], rdi
0x140027058  mov     dword ptr [rsp+1D0h+var_1B0], eax
0x14002705c  call    WPP_SF_DDiqdS
0x140027061  mov     rcx, [rbp+0D0h+pvContextBuffer]
0x140027065  jmp     short loc_14002706C
0x140027067  movzx   r13d, [rbp+0D0h+var_150]
0x14002706c  test    byte ptr cs:WPP_MAIN_CB.Queue+13h, 40h
0x140027073  jz      short loc_1400270C9
0x140027075  mov     rdi, [rsi+180h]
0x14002707c  mov     rbx, [rsi+1B8h]
0x140027083  call    cs:__imp_MRxSmbGetConfigurationBlock
0x14002708a  nop     dword ptr [rax+rax+00h]
0x14002708f  movzx   r9d, word ptr [rdi+50h]
0x140027094  mov     ecx, [rax+0E0h]
0x14002709a  movzx   eax, r13w
0x14002709e  mov     dword ptr [rsp+1D0h+var_188], eax
0x1400270a2  mov     eax, dword ptr [rbp+0D0h+Size+4]
0x1400270a5  mov     qword ptr [rsp+1D0h+var_190], r15
0x1400270aa  mov     [rsp+1D0h+var_198], rbx
0x1400270af  mov     dword ptr [rsp+1D0h+var_1A0], ecx
0x1400270b3  mov     dword ptr [rsp+1D0h+var_1A8], eax
0x1400270b7  mov     rax, [rdi+58h]
0x1400270bb  mov     [rsp+1D0h+var_1B0], rax
0x1400270c0  call    McTemplateK0hzr0qqxzq_EtwWriteTransfer
0x1400270c5  mov     rcx, [rbp+0D0h+pvContextBuffer]; pvContextBuffer
0x1400270c9  test    rcx, rcx
0x1400270cc  jz      short loc_1400270DA
0x1400270ce  call    cs:__imp_FreeContextBuffer
0x1400270d5  nop     dword ptr [rax+rax+00h]
0x1400270da  mov     ebx, 0C0000517h
0x1400270df  mov     edi, 0CEh
0x1400270e4  jmp     loc_14002752A
0x1400270e9  mov     rcx, [r13+1B0h]
0x1400270f0  xor     r9d, r9d
0x1400270f3  xor     r8d, r8d
0x1400270f6  mov     edx, 3
0x1400270fb  call    cs:__imp_SmbCeCheckServerEntryDialect
0x140027102  nop     dword ptr [rax+rax+00h]
0x140027107  test    al, al
0x140027109  jz      short loc_14002714D
0x14002710b  mov     r9d, [r15+418h]
0x140027112  lea     rax, [rbp+0D0h+var_50]
0x140027119  mov     r8, [r15+410h]
  ... truncated ...
```
