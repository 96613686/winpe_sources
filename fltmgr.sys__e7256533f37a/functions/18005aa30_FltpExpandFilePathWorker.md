# FltpExpandFilePathWorker

- ea: `0x18005aa30`
- end: `0x18005b4a1`
- name: `FltpExpandFilePathWorker`
- size: `2673`
- prototype: ``
- caller_count: `3`
- callee_count: `18`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001c130`
- `0x180059470`
- `0x18005b880`

## callees

- `0x180009f20`
- `0x18000dcb0`
- `0x18000e2e0`
- `0x180015240`
- `0x180024940`
- `0x180058190`
- `0x180058380`
- `0x18005aa30`
- `0x18005bf90`
- `0x18005c1d0`
- `0x18005c3b0`
- `0x18005c450`
- `0x18005c5a0`
- `0x18005d850`
- `0x18005df50`
- `0x180066990`
- `0x18006e9a0`
- `0x1800718a0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18005b443`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005b443`
- `ntoskrnl!ObfDereferenceObject` at `0x18005b1bd`
- `ntoskrnl!ObfDereferenceObject` at `0x18005b2eb`
- `ntoskrnl!ObfDereferenceObject` at `0x18005b1bd`
- `ntoskrnl!ObfDereferenceObject` at `0x18005b2eb`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x18005aefb`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x18005aefb`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18005b14d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18005b14d`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x18005b2c5`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x18005b2c5`
- `ntoskrnl!RtlEqualUnicodeString` at `0x18005afcb`
- `ntoskrnl!RtlEqualUnicodeString` at `0x18005afcb`
- `ntoskrnl!ZwClose` at `0x18005b0c3`
- `ntoskrnl!ZwClose` at `0x18005b1db`
- `ntoskrnl!ZwClose` at `0x18005b0c3`
- `ntoskrnl!ZwClose` at `0x18005b1db`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18005adc9`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18005adc9`
- `ntoskrnl!FsRtlIsEcpAcknowledged` at `0x18005b25d`
- `ntoskrnl!FsRtlIsEcpAcknowledged` at `0x18005b25d`
- `ntoskrnl!IoFileObjectType` at `0x18005ada2`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x18005ae14`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x18005ae14`
- `ntoskrnl!IoCreateFileEx` at `0x18005ad31`
- `ntoskrnl!IoCreateFileEx` at `0x18005ad31`
- `ntoskrnl!IoGetSilo` at `0x18005ac68`
- `ntoskrnl!IoGetSilo` at `0x18005ac68`
- `ntoskrnl!PsGetHostSilo` at `0x18005ac7d`
- `ntoskrnl!PsGetHostSilo` at `0x18005ac7d`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x1800794aa`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x1800794aa`
- `ntoskrnl!IoGetAttachedDevice` at `0x18005ae27`
- `ntoskrnl!IoGetAttachedDevice` at `0x18005ae39`
- `ntoskrnl!IoGetAttachedDevice` at `0x18005b343`
- `ntoskrnl!IoGetAttachedDevice` at `0x18005ae27`
- `ntoskrnl!IoGetAttachedDevice` at `0x18005ae39`
- `ntoskrnl!IoGetAttachedDevice` at `0x18005b343`

## string_xrefs

- `0x18005b3c3`: `FltpExpandFilePathWorker`

## pseudocode

```c
__int64 __fastcall FltpExpandFilePathWorker(__int64 a1)
{
  bool v1; // di
  char *v2; // r12
  __int64 v4; // r15
  unsigned __int16 **v5; // r13
  int v6; // eax
  unsigned __int16 *v7; // rdx
  __int64 v8; // r9
  __int64 ECP; // rsi
  __int16 v10; // ax
  __int64 v11; // r9
  unsigned __int16 v12; // dx
  __int64 *v13; // r9
  __int64 v14; // rax
  __int64 *v15; // rdx
  void *v16; // rcx
  int v17; // r8d
  PUNICODE_STRING *v18; // rbx
  unsigned __int16 *v19; // rdx
  int v20; // ecx
  void **v21; // rcx
  char v22; // al
  ULONG CreateOptions; // r8d
  __int64 v24; // rax
  ULONG Options; // eax
  NTSTATUS v26; // eax
  __int64 v27; // rdx
  NTSTATUS v28; // edi
  struct _FILE_OBJECT **v29; // rdi
  __int64 v30; // rax
  __int64 v31; // rbx
  struct _DEVICE_OBJECT *RelatedDeviceObject; // rdi
  struct _DEVICE_OBJECT *AttachedDevice; // rbx
  int v34; // eax
  unsigned __int16 *v35; // rax
  unsigned __int16 *v36; // r10
  unsigned int v37; // edx
  unsigned int v38; // edx
  __int64 v39; // rax
  int v40; // ecx
  _BYTE *v41; // rbx
  PUNICODE_STRING v42; // rax
  unsigned __int16 *v44; // rcx
  __int64 v45; // rdx
  void *v46; // rcx
  PDEVICE_OBJECT DeviceAttachmentBaseRef; // rax
  unsigned int v48; // eax
  __int64 v49; // rcx
  _WORD *v50; // rcx
  __int64 v51; // rcx
  __int64 v52; // rcx
  unsigned __int16 *v53; // rdx
  __int64 v54; // r8
  PVOID EaBuffer; // [rsp+50h] [rbp-B8h]
  __int64 v56; // [rsp+88h] [rbp-80h] BYREF
  PVOID EcpContext; // [rsp+90h] [rbp-78h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+98h] [rbp-70h] BYREF
  __int64 Silo; // [rsp+B8h] [rbp-50h]
  PVOID Entry; // [rsp+C0h] [rbp-48h] BYREF
  struct _DEVICE_OBJECT *v61; // [rsp+C8h] [rbp-40h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+D0h] [rbp-38h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+E0h] [rbp-28h] BYREF
  bool v64; // [rsp+168h] [rbp+60h]
  _BYTE *v65; // [rsp+170h] [rbp+68h] BYREF
  unsigned int v66; // [rsp+178h] [rbp+70h]
  _BYTE *v67; // [rsp+180h] [rbp+78h]

  v1 = 0;
  v2 = 0;
  Entry = 0;
  v67 = 0;
  LOWORD(v4) = 0;
  v65 = 0;
  v5 = 0;
  LOWORD(Silo) = 0;
  v6 = *(_DWORD *)(a1 + 40);
  EcpContext = 0;
  v56 = 0;
  v64 = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  memset(&DriverContext, 0, sizeof(DriverContext));
  if ( (v6 & 0x80u) != 0 )
  {
    v7 = *(unsigned __int16 **)(a1 + 112);
    if ( *(_WORD *)(*((_QWORD *)v7 + 1) + 2 * ((unsigned __int64)*v7 >> 1) - 2) == 92 )
      *v7 -= 2;
    if ( (unsigned __int8)FltpNameCanBeExpanded(a1) )
    {
      v8 = *(_QWORD *)(a1 + 112);
      LODWORD(ECP) = -1073741772;
      v10 = *(_WORD *)v8 >> 1;
      if ( v10 )
      {
        v11 = *(_QWORD *)(v8 + 8);
        if ( v11 )
        {
          v12 = v10 - 1;
          if ( (__int16)(v10 - 1) >= 0 )
          {
            while ( *(_WORD *)(v11 + 2LL * v12) != 92 )
            {
              if ( (--v12 & 0x8000u) != 0 )
                goto LABEL_10;
            }
            v2 = (char *)(v11 + 2LL * v12);
            LODWORD(ECP) = 0;
            LOWORD(v4) = 2 * (v10 - v12);
          }
        }
      }
LABEL_10:
      if ( (int)FltpDbgStatus((unsigned int)ECP, "minkernel\\fs\\filtermgr\\filter\\namesup.c", 4041, 0) < 0 )
      {
        v42 = *(PUNICODE_STRING *)(a1 + 112);
        goto LABEL_60;
      }
    }
    else
    {
      v49 = *(_QWORD *)(a1 + 24);
      if ( v49 )
        v50 = (_WORD *)(v49 + 112);
      else
        v50 = (_WORD *)(*(_QWORD *)(a1 + 32) + 8LL);
      v53 = *(unsigned __int16 **)(a1 + 112);
      v54 = *v53;
      v4 = (unsigned __int16)(v54 - v53[12] - *v50);
      v2 = (char *)(v54 + *((_QWORD *)v53 + 1) - v4);
    }
    v2 += 2;
    LOWORD(v4) = v4 - 2;
    **(_WORD **)(a1 + 112) -= v4;
  }
  v13 = *(__int64 **)(a1 + 8);
  Silo = 1;
  memset(&DriverContext, 0, sizeof(DriverContext));
  DriverContext.Size = 40;
  if ( v13 )
  {
    v14 = *(_QWORD *)(a1 + 16);
    if ( v14 )
    {
      v15 = 0;
      v16 = *(void **)(v14 + 72);
      v17 = 2 * (*(_DWORD *)(a1 + 108) & 0x1000000 | 0x800000);
    }
    else
    {
      v17 = 16777218;
      v16 = 0;
      v14 = 0;
      v15 = v13;
    }
    ECP = (unsigned int)TargetedIOCtrlGenerateECP(
                          (PVOID *)&v65,
                          0,
                          v17,
                          v13[13],
                          v16,
                          v14,
                          v15,
                          &DriverContext.ExtraCreateParameter,
                          0);
    if ( (int)FltpDbgStatus(ECP, "minkernel\\fs\\filtermgr\\filter\\namesup.c", 4166, 0) < 0 )
    {
      v42 = *(PUNICODE_STRING *)(a1 + 112);
      v41 = v65;
      goto LABEL_61;
    }
    v67 = v65;
    v64 = (v65[6] & 8) != 0;
  }
  v18 = (PUNICODE_STRING *)(a1 + 112);
  v19 = *(unsigned __int16 **)(a1 + 112);
  DriverContext.TxnParameters = *(PTXN_PARAMETER_BLOCK *)(a1 + 72);
  DriverContext.DeviceObjectHint = *(PVOID *)a1;
  ECP = (unsigned int)FltpGenerateDeviceHintEcp(&EcpContext, *v19, DriverContext.ExtraCreateParameter);
  if ( (int)FltpDbgStatus(ECP, "minkernel\\fs\\filtermgr\\filter\\namesup.c", 4196, 0) < 0 )
    goto LABEL_58;
  v66 = 0;
  if ( (byte_180040A43 & 4) != 0 )
    McTemplateU0sw_EtwWriteTransfer(
      v20,
      (unsigned int)NameSup_c4204,
      (unsigned int)"FltpExpandFilePathWorker",
      (*v18)->Length >> 1,
      (__int64)(*v18)->Buffer);
  Silo = IoGetSilo(*(_QWORD *)(a1 + 64));
  if ( !Silo )
    Silo = PsGetHostSilo();
  v21 = (void **)(a1 + 152);
  v22 = 2 * *(_DWORD *)(a1 + 40);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = ~v22 & 0x40 | 0x200;
  CreateOptions = 16417;
  ObjectAttributes.ObjectName = *v18;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  LODWORD(v65) = 16417;
  while ( 1 )
  {
    v24 = *(_QWORD *)(a1 + 80);
    if ( v24
      && (v45 = *(_QWORD *)(v24 + 16),
          (*((_BYTE *)FltpOperationFlags + (unsigned __int8)(*(_BYTE *)(v45 + 4) + 22)) & 2) != 0)
      && (*(_BYTE *)(v45 + 6) & 8) != 0 )
    {
      Options = 2056;
    }
    else
    {
      Options = 2048;
    }
    v26 = IoCreateFileEx(
            v21,
            0x100001u,
            &ObjectAttributes,
            &IoStatusBlock,
            0,
            0x80u,
            7u,
            1u,
            CreateOptions,
            0,
            0,
            CreateFileTypeNone,
            0,
            Options,
            &DriverContext);
    LODWORD(ECP) = v26;
    v28 = v26;
    if ( v26 == -1073741191 )
      break;
    if ( (unsigned int)(v26 + 1073740952) > 1 && v26 != -1073740650 )
      goto LABEL_28;
    LODWORD(v65) = (unsigned int)v65 & 0xFFDFFFFF;
    if ( v26 == -1073740650 )
    {
      LOBYTE(v27) = 1;
      ECP = (unsigned int)FltpResetDeviceHintEcp(EcpContext, v27);
      if ( (int)FltpDbgStatus(ECP, "minkernel\\fs\\filtermgr\\filter\\namesup.c", 4305, 0) < 0 )
        goto LABEL_28;
      v48 = v66;
    }
    else
    {
      if ( !FsRtlIsEcpAcknowledged(EcpContext) )
        goto LABEL_28;
      FltpCleanupTargetInfo(0, 0, v56);
      v56 = 0;
      ECP = (unsigned int)FltpGetTargetInfo(EcpContext, 0, 0, 0, &v56);
      if ( (int)FltpDbgStatus(ECP, "minkernel\\fs\\filtermgr\\filter\\namesup.c", 4333, 0) < 0 )
        goto LABEL_28;
      DeviceAttachmentBaseRef = IoGetDeviceAttachmentBaseRef(*(PDEVICE_OBJECT *)(*(_QWORD *)(a1 + 8) + 64LL));
      v61 = DeviceAttachmentBaseRef;
      if ( *(PDEVICE_OBJECT *)EcpContext == DeviceAttachmentBaseRef )
      {
        DriverContext.DeviceObjectHint = *(PVOID *)a1;
      }
      else
      {
        DriverContext.DeviceObjectHint = IoGetAttachedDevice(*(PDEVICE_OBJECT *)EcpContext);
        DeviceAttachmentBaseRef = v61;
      }
      ObfDereferenceObject(DeviceAttachmentBaseRef);
      ObjectAttributes.ObjectName = (PUNICODE_STRING)(v56 + 8);
      FltpResetDeviceHintEcp(EcpContext, 0);
      v48 = ++v66;
    }
    CreateOptions = (unsigned int)v65;
LABEL_86:
    v21 = (void **)(a1 + 152);
    if ( v48 >= 0x40 )
      goto LABEL_28;
  }
  if ( (unsigned __int8)FsRtlIsNonEmptyDirectoryReparsePointAllowed(LODWORD(IoStatusBlock.Information)) )
  {
    if ( ((unsigned int)v65 & 0x200000) == 0 )
    {
      ECP = (unsigned int)FltpResetDeviceHintEcp(EcpContext, 0);
      if ( (int)FltpDbgStatus(ECP, "minkernel\\fs\\filtermgr\\filter\\namesup.c", 4281, 0) >= 0 )
      {
        v48 = v66;
        CreateOptions = (unsigned int)v65 | 0x200000;
        LODWORD(v65) = (unsigned int)v65 | 0x200000;
        goto LABEL_86;
      }
    }
  }
LABEL_28:
  FltpCleanupDeviceHintEcp(DriverContext.ExtraCreateParameter);
  FltpCleanupTargetInfo(0, 0, v56);
  if ( v66 >= 0x40 )
    LODWORD(ECP) = v28;
  if ( (int)FltpDbgStatus((unsigned int)ECP, "minkernel\\fs\\filtermgr\\filter\\namesup.c", 4384, 0) < 0 )
  {
    if ( (_DWORD)ECP == -2147483603 )
    {
      if ( IoStatusBlock.Information )
        ExFreePoolWithTag((PVOID)IoStatusBlock.Information, 0);
    }
    else if ( ((_DWORD)ECP == -1073741772 || (_DWORD)ECP == -1073741565) && *(char *)(a1 + 40) < 0 )
    {
      LODWORD(ECP) = -1073741766;
    }
    goto LABEL_58;
  }
  v29 = (struct _FILE_OBJECT **)(a1 + 160);
  LODWORD(ECP) = ObReferenceObjectByHandle(
                   *(HANDLE *)(a1 + 152),
                   0,
                   (POBJECT_TYPE)IoFileObjectType,
                   0,
                   (PVOID *)(a1 + 160),
                   0);
  if ( (int)FltpDbgStatus((unsigned int)ECP, "minkernel\\fs\\filtermgr\\filter\\namesup.c", 4445, 0) < 0 )
  {
    ZwClose(*(HANDLE *)(a1 + 152));
    *(_QWORD *)(a1 + 152) = 0;
    goto LABEL_58;
  }
  if ( !(*v29)->FsContext )
  {
    LODWORD(ECP) = -1071906811;
    goto LABEL_58;
  }
  v30 = *(_QWORD *)(a1 + 24);
  if ( !v30 )
  {
LABEL_36:
    if ( ((*v29)->Flags & 0x400000) == 0 )
    {
      LODWORD(ECP) = FltpAllocateInitializeNameGenerationContext(
                       (PFLT_INSTANCE **)&Entry,
                       *(struct _FLT_INSTANCE **)(a1 + 16),
                       *v29,
                       0,
                       *(_DWORD *)(a1 + 108) & 0x1000000 | 0x102u,
                       0,
                       0,
                       0,
                       0,
                       (__int64)EaBuffer,
                       *(_DWORD *)(a1 + 40) & 0x400 | 1u);
      v34 = FltpDbgStatus((unsigned int)ECP, "minkernel\\fs\\filtermgr\\filter\\namesup.c", 4525, 3221225626LL);
      v5 = (unsigned __int16 **)Entry;
      if ( v34 >= 0 )
      {
        *((_QWORD *)Entry + 6) = *(_QWORD *)(a1 + 48);
        v5[7] = *(unsigned __int16 **)(a1 + 56);
        v35 = (unsigned __int16 *)ExAllocateFromNPagedLookasideList(&stru_18003F340);
        v5[14] = v35;
        if ( v35 )
        {
          *((_DWORD *)v35 + 4) = 0;
          *((_DWORD *)v35 + 6) = 0;
          *((_DWORD *)v35 + 5) = 254;
          *(_OWORD *)v35 = 0;
          v35[1] = 254;
          *((_QWORD *)v35 + 1) = v35 + 14;
          LODWORD(ECP) = FltpCallOpenedFileNameHandler(v5);
          if ( (int)ECP >= 0 )
          {
            v36 = v5[14];
            if ( *(_WORD *)(*((_QWORD *)v36 + 1) + 2 * ((unsigned __int64)*v36 >> 1) - 2) != 92 )
            {
              v37 = *v36 + 2;
              if ( v37 > 0xFFFE )
              {
                LODWORD(ECP) = -1073741562;
              }
              else if ( v37 > (unsigned __int64)*((unsigned int *)v36 + 5) - 2 )
              {
                LODWORD(ECP) = FltpReallocNameControl(v5[14], (unsigned int)*v36 + 516, 0, 0);
              }
              else
              {
                LODWORD(ECP) = 0;
              }
              if ( (int)FltpDbgStatus((unsigned int)ECP, "minkernel\\fs\\filtermgr\\filter\\namesup.c", 4577, 0) < 0 )
                goto LABEL_58;
              *(_WORD *)(*((_QWORD *)v5[14] + 1) + 2 * ((unsigned __int64)*v5[14] >> 1)) = 92;
              *v5[14] += 2;
            }
            if ( !RtlEqualUnicodeString(*v18, (PCUNICODE_STRING)v5[14], 0) )
            {
              v38 = (unsigned __int16)v4 + *v5[14];
              if ( v38 > 0xFFFE )
                LODWORD(ECP) = -1073741562;
              else
                LODWORD(ECP) = v38 <= (unsigned __int64)*(unsigned int *)(&(*v18)[1].MaximumLength + 1) - 2
                             ? 0
                             : FltpReallocNameControl(*v18, v38 + 514, 0, 0);
              if ( (int)FltpDbgStatus((unsigned int)ECP, "minkernel\\fs\\filtermgr\\filter\\namesup.c", 4612, 0) >= 0 )
              {
                v1 = v64;
                if ( (*(_DWORD *)(a1 + 40) & 0x80u) != 0 )
                  memmove(&(*v18)->Buffer[(unsigned __int64)*v5[14] >> 1], v2, (unsigned __int16)v4);
                memmove((*v18)->Buffer, *((const void **)v5[14] + 1), *v5[14]);
                (*v18)->Length = *v5[14];
                (*v18)->Length += v4;
                v39 = *(_QWORD *)(a1 + 24);
                if ( v39 )
                  v40 = *(_DWORD *)(v39 + 56);
                else
                  v40 = **(_DWORD **)(a1 + 32);
                if ( (v40 & 1) != 0 )
                {
                  v51 = *(_QWORD *)(a1 + 24);
                  if ( v51 )
                    v52 = v51 + 112;
                  else
                    v52 = *(_QWORD *)(a1 + 32) + 8LL;
                  FltpParseShareName(v52, *v18);
                }
                v41 = v67;
                goto LABEL_62;
              }
            }
          }
        }
        else
        {
          LODWORD(ECP) = -1073741670;
        }
      }
    }
LABEL_58:
    v42 = *v18;
    goto LABEL_59;
  }
  v31 = *(_QWORD *)(*(_QWORD *)(v30 + 64) + 64LL);
  RelatedDeviceObject = IoGetRelatedDeviceObject(*v29);
  AttachedDevice = IoGetAttachedDevice(*(PDEVICE_OBJECT *)(v31 + 8));
  if ( IoGetAttachedDevice(RelatedDeviceObject) == AttachedDevice )
  {
    v18 = (PUNICODE_STRING *)(a1 + 112);
    v29 = (struct _FILE_OBJECT **)(a1 + 160);
    goto LABEL_36;
  }
  v42 = *(PUNICODE_STRING *)(a1 + 112);
  LODWORD(ECP) = -1073741612;
LABEL_59:
  v1 = v64;
LABEL_60:
  v41 = v67;
LABEL_61:
  v42->Length += v4;
LABEL_62:
  if ( v41 )
  {
    if ( (int)FltpDbgStatus((unsigned int)ECP, "minkernel\\fs\\filtermgr\\filter\\namesup.c", 4673, 0) < 0 )
      v41 = 0;
    CleanupTargetedIo(v41, &DriverContext.ExtraCreateParameter, v1);
  }
  if ( *(_QWORD *)(a1 + 152)
    && ((int)FltpDbgStatus((unsigned int)ECP, "minkernel\\fs\\filtermgr\\filter\\namesup.c", 4692, 0) < 0
     || (*(_DWORD *)(a1 + 40) & 0x40) == 0) )
  {
    ObfDereferenceObject(*(PVOID *)(a1 + 160));
    v46 = *(void **)(a1 + 152);
    *(_QWORD *)(a1 + 160) = 0;
    ZwClose(v46);
    *(_QWORD *)(a1 + 152) = 0;
  }
  if ( v5 )
  {
    v44 = v5[14];
    if ( v44 )
    {
      FltpCleanupNameControl(v44);
      ExFreeToNPagedLookasideList(&stru_18003F340, v5[14]);
    }
    FltpFreeNameGenerationContext(v5);
  }
  return (unsigned int)ECP;
}

```

## disassembly

```asm
0x18005aa30  mov     rax, rsp
0x18005aa33  push    rbp
0x18005aa34  push    rsi
0x18005aa35  push    r13
0x18005aa37  lea     rbp, [rax-58h]
0x18005aa3b  sub     rsp, 140h
0x18005aa42  xor     r10d, r10d
0x18005aa45  mov     [rax-20h], rbx
0x18005aa49  mov     [rax-28h], rdi
0x18005aa4d  xorps   xmm0, xmm0
0x18005aa50  mov     [rax-30h], r12
0x18005aa54  xor     dil, dil
0x18005aa57  mov     [rax-38h], r14
0x18005aa5b  mov     r12d, r10d
0x18005aa5e  mov     [rax-40h], r15
0x18005aa62  mov     r14, rcx
0x18005aa65  xor     eax, eax
0x18005aa67  mov     [rbp+50h+Entry], r10
0x18005aa6b  mov     [rbp+50h+arg_18], rax
0x18005aa6f  mov     r15d, r10d
0x18005aa72  mov     [rbp+50h+arg_8], rax
0x18005aa76  mov     r13d, r10d
0x18005aa79  mov     word ptr [rbp+50h+var_A0], ax
0x18005aa7d  mov     eax, [rcx+28h]
0x18005aa80  mov     [rbp+50h+EcpContext], r10
0x18005aa84  mov     [rbp+50h+var_D0], r10
0x18005aa88  mov     [rbp+50h+arg_0], dil
0x18005aa8c  movups  xmmword ptr [rbp+50h+ObjectAttributes.ObjectName], xmm0
0x18005aa90  movups  xmmword ptr [rbp+50h+ObjectAttributes.Length], xmm0
0x18005aa94  movups  xmmword ptr [rbp+50h+ObjectAttributes+1Ch], xmm0
0x18005aa98  movups  xmmword ptr [rbp+50h+IoStatusBlock], xmm0
0x18005aa9c  movups  xmmword ptr [rbp+50h+DriverContext.Size], xmm0
0x18005aaa0  movups  xmmword ptr [rbp+50h+DriverContext.DeviceObjectHint], xmm0
0x18005aaa4  test    al, al
0x18005aaa6  jns     loc_18005AB56
0x18005aaac  mov     rdx, [rcx+70h]
0x18005aab0  movzx   r8d, word ptr [rdx]
0x18005aab4  mov     rax, [rdx+8]
0x18005aab8  mov     ecx, r8d
0x18005aabb  shr     rcx, 1
0x18005aabe  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x18005aac4  jz      loc_18005B372
0x18005aaca  mov     rcx, r14
0x18005aacd  call    FltpNameCanBeExpanded
0x18005aad2  test    al, al
0x18005aad4  jz      loc_18005B389
0x18005aada  mov     r9, [r14+70h]
0x18005aade  mov     esi, 0C0000034h
0x18005aae3  movzx   eax, word ptr [r9]
0x18005aae7  shr     ax, 1
0x18005aaea  jz      short loc_18005AB1F
0x18005aaec  mov     r9, [r9+8]
0x18005aaf0  test    r9, r9
0x18005aaf3  jz      short loc_18005AB1F
0x18005aaf5  movzx   edx, ax
0x18005aaf8  sub     dx, 1
0x18005aafc  js      short loc_18005AB1F
0x18005aafe  xchg    ax, ax
0x18005ab00  movzx   ecx, dx
0x18005ab03  cmp     word ptr [r9+rcx*2], 5Ch ; '\'
0x18005ab09  lea     r8, [r9+rcx*2]
0x18005ab0d  jnz     loc_18005B363
0x18005ab13  sub     ax, dx
0x18005ab16  mov     r12, r8
0x18005ab19  xor     esi, esi
0x18005ab1b  lea     r15d, [rax+rax]
0x18005ab1f  mov     r8d, 0FC9h
0x18005ab25  lea     rdx, aMinkernelFsFil_25; "minkernel\\fs\\filtermgr\\filter\\names"...
0x18005ab2c  xor     r9d, r9d
0x18005ab2f  mov     ecx, esi
0x18005ab31  call    FltpDbgStatus
0x18005ab36  test    eax, eax
0x18005ab38  js      loc_18005B380
0x18005ab3e  mov     eax, 0FFFEh
0x18005ab43  add     r12, 2
0x18005ab47  add     r15w, ax
0x18005ab4b  mov     rax, [r14+70h]
0x18005ab4f  sub     [rax], r15w
0x18005ab53  xor     r10d, r10d
0x18005ab56  mov     r9, [r14+8]
0x18005ab5a  xorps   xmm0, xmm0
0x18005ab5d  mov     [rbp+50h+var_A0], 1
0x18005ab65  mov     eax, 28h ; '('
0x18005ab6a  movups  xmmword ptr [rbp+50h+DriverContext.Size], xmm0
0x18005ab6e  mov     [rbp+50h+DriverContext.Size], ax
0x18005ab72  movups  xmmword ptr [rbp+50h+DriverContext.DeviceObjectHint], xmm0
0x18005ab76  test    r9, r9
0x18005ab79  jz      loc_18005AC0B
0x18005ab7f  mov     rax, [r14+10h]
0x18005ab83  test    rax, rax
0x18005ab86  jz      loc_18005B39F
0x18005ab8c  mov     r8d, [r14+6Ch]
0x18005ab90  mov     rdx, r10
0x18005ab93  mov     rcx, [rax+48h]
0x18005ab97  and     r8d, 1000000h
0x18005ab9e  bts     r8d, 17h
0x18005aba3  add     r8d, r8d; int
0x18005aba6  mov     r9, [r9+68h]; int
0x18005abaa  mov     qword ptr [rsp+150h+CreateOptions], r10; __int64
0x18005abaf  lea     r10, [rbp+50h+DriverContext.ExtraCreateParameter]
0x18005abb3  mov     qword ptr [rsp+150h+Disposition], r10; EcpList
0x18005abb8  mov     qword ptr [rsp+150h+ShareAccess], rdx; PVOID
0x18005abbd  xor     edx, edx; int
0x18005abbf  mov     qword ptr [rsp+150h+FileAttributes], rax; __int64
0x18005abc4  mov     [rsp+150h+AllocationSize], rcx; FltObject
0x18005abc9  lea     rcx, [rbp+50h+arg_8]; int
0x18005abcd  call    TargetedIOCtrlGenerateECP
0x18005abd2  mov     r8d, 1046h
0x18005abd8  lea     rdx, aMinkernelFsFil_25; "minkernel\\fs\\filtermgr\\filter\\names"...
0x18005abdf  xor     r9d, r9d
0x18005abe2  mov     ecx, eax
0x18005abe4  mov     esi, eax
0x18005abe6  call    FltpDbgStatus
0x18005abeb  test    eax, eax
0x18005abed  js      loc_18005B3B3
0x18005abf3  mov     rax, [rbp+50h+arg_8]
0x18005abf7  mov     [rbp+50h+arg_18], rax
0x18005abfb  movzx   edi, byte ptr [rax+6]
0x18005abff  shr     dil, 3
0x18005ac03  and     dil, 1
0x18005ac07  mov     [rbp+50h+arg_0], dil
0x18005ac0b  mov     rax, [r14+48h]
0x18005ac0f  lea     rbx, [r14+70h]
0x18005ac13  mov     rdx, [rbx]
0x18005ac16  lea     rcx, [rbp+50h+EcpContext]
0x18005ac1a  mov     r8, [rbp+50h+DriverContext.ExtraCreateParameter]
0x18005ac1e  mov     [rbp+50h+DriverContext.TxnParameters], rax
0x18005ac22  mov     rax, [r14]
0x18005ac25  mov     [rbp+50h+DriverContext.DeviceObjectHint], rax
0x18005ac29  movzx   edx, word ptr [rdx]
0x18005ac2c  call    FltpGenerateDeviceHintEcp
0x18005ac31  mov     r8d, 1064h
0x18005ac37  lea     rdx, aMinkernelFsFil_25; "minkernel\\fs\\filtermgr\\filter\\names"...
0x18005ac3e  xor     r9d, r9d
0x18005ac41  mov     ecx, eax
0x18005ac43  mov     esi, eax
0x18005ac45  call    FltpDbgStatus
0x18005ac4a  test    eax, eax
0x18005ac4c  js      loc_18005B0D6
0x18005ac52  xor     edi, edi
0x18005ac54  test    cs:byte_180040A43, 4
0x18005ac5b  mov     [rbp+50h+arg_10], edi
0x18005ac5e  jnz     loc_18005B3C0
0x18005ac64  mov     rcx, [r14+40h]
0x18005ac68  call    cs:__imp_IoGetSilo
0x18005ac6f  nop     dword ptr [rax+rax+00h]
0x18005ac74  mov     [rbp+50h+var_A0], rax
0x18005ac78  test    rax, rax
0x18005ac7b  jnz     short loc_18005AC8D
0x18005ac7d  call    cs:__imp_PsGetHostSilo
0x18005ac84  nop     dword ptr [rax+rax+00h]
0x18005ac89  mov     [rbp+50h+var_A0], rax
0x18005ac8d  mov     eax, [r14+28h]
0x18005ac91  lea     rcx, [r14+98h]; FileHandle
0x18005ac98  add     eax, eax
0x18005ac9a  mov     [rbp+50h+ObjectAttributes.Length], 30h ; '0'
0x18005aca1  not     eax
0x18005aca3  mov     [rbp+50h+ObjectAttributes.RootDirectory], rdi
0x18005aca7  and     eax, 40h
0x18005acaa  lea     r9, FltpOperationFlags
0x18005acb1  bts     eax, 9
0x18005acb5  xorps   xmm0, xmm0
0x18005acb8  mov     [rbp+50h+ObjectAttributes.Attributes], eax
0x18005acbb  mov     r8d, 4021h
0x18005acc1  mov     rax, [rbx]
0x18005acc4  mov     [rbp+50h+ObjectAttributes.ObjectName], rax
0x18005acc8  movdqu  xmmword ptr [rbp+50h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005accd  mov     dword ptr [rbp+50h+arg_8], r8d
0x18005acd1  mov     rax, [r14+50h]
0x18005acd5  test    rax, rax
0x18005acd8  jnz     loc_18005B163
0x18005acde  mov     eax, 800h
0x18005ace3  lea     rdx, [rbp+50h+DriverContext]
0x18005ace7  mov     [rsp+70h], rdx; DriverContext
0x18005acec  lea     r9, [rbp+50h+IoStatusBlock]; IoStatusBlock
0x18005acf0  mov     [rsp+150h+Options], eax; Options
0x18005acf4  mov     edx, 100001h; DesiredAccess
0x18005acf9  mov     [rsp+150h+InternalParameters], rdi; InternalParameters
0x18005acfe  mov     [rsp+150h+CreateFileType], edi; CreateFileType
0x18005ad02  mov     [rsp+150h+EaLength], edi; EaLength
0x18005ad06  mov     [rsp+150h+EaBuffer], rdi; EaBuffer
0x18005ad0b  mov     [rsp+150h+CreateOptions], r8d; CreateOptions
0x18005ad10  lea     r8, [rbp+50h+ObjectAttributes]; ObjectAttributes
0x18005ad14  mov     [rsp+150h+Disposition], 1; Disposition
0x18005ad1c  mov     [rsp+150h+ShareAccess], 7; ShareAccess
0x18005ad24  mov     [rsp+150h+FileAttributes], 80h; FileAttributes
0x18005ad2c  mov     [rsp+150h+AllocationSize], rdi; AllocationSize
0x18005ad31  call    cs:__imp_IoCreateFileEx
0x18005ad38  nop     dword ptr [rax+rax+00h]
0x18005ad3d  mov     esi, eax
0x18005ad3f  mov     edi, eax
0x18005ad41  cmp     eax, 0C0000279h
0x18005ad46  jz      loc_1800794A7
0x18005ad4c  add     eax, 3FFFFC98h
0x18005ad51  cmp     eax, 1
0x18005ad54  jbe     loc_18005B246
0x18005ad5a  cmp     edi, 0C0000496h
0x18005ad60  jz      loc_18005B246
0x18005ad66  mov     rcx, [rbp+50h+DriverContext.ExtraCreateParameter]
0x18005ad6a  call    FltpCleanupDeviceHintEcp
0x18005ad6f  mov     r8, [rbp+50h+var_D0]
0x18005ad73  xor     edx, edx
0x18005ad75  xor     ecx, ecx
0x18005ad77  call    FltpCleanupTargetInfo
0x18005ad7c  cmp     [rbp+50h+arg_10], 40h ; '@'
0x18005ad80  lea     rdx, aMinkernelFsFil_25; "minkernel\\fs\\filtermgr\\filter\\names"...
0x18005ad87  mov     r8d, 1120h
0x18005ad8d  cmovnb  esi, edi
0x18005ad90  xor     r9d, r9d
0x18005ad93  mov     ecx, esi
0x18005ad95  call    FltpDbgStatus
0x18005ad9a  test    eax, eax
0x18005ad9c  js      loc_18005B428
0x18005ada2  mov     r8, cs:__imp_IoFileObjectType
0x18005ada9  lea     rdi, [r14+0A0h]
0x18005adb0  mov     rcx, [r14+98h]; Handle
0x18005adb7  xor     r9d, r9d; AccessMode
0x18005adba  mov     qword ptr [rsp+150h+FileAttributes], r13; HandleInformation
0x18005adbf  xor     edx, edx; DesiredAccess
0x18005adc1  mov     [rsp+150h+AllocationSize], rdi; Object
0x18005adc6  mov     r8, [r8]; ObjectType
0x18005adc9  call    cs:__imp_ObReferenceObjectByHandle
0x18005add0  nop     dword ptr [rax+rax+00h]
0x18005add5  mov     r8d, 115Dh
0x18005addb  lea     rdx, aMinkernelFsFil_25; "minkernel\\fs\\filtermgr\\filter\\names"...
0x18005ade2  mov     ecx, eax
0x18005ade4  xor     r9d, r9d
0x18005ade7  mov     esi, eax
0x18005ade9  call    FltpDbgStatus
0x18005adee  test    eax, eax
0x18005adf0  js      loc_18005B0BC
0x18005adf6  mov     rcx, [rdi]; FileObject
0x18005adf9  cmp     [rcx+18h], r13
0x18005adfd  jz      loc_18005B454
0x18005ae03  mov     rax, [r14+18h]
0x18005ae07  test    rax, rax
0x18005ae0a  jz      short loc_18005AE59
0x18005ae0c  mov     rax, [rax+40h]
0x18005ae10  mov     rbx, [rax+40h]
0x18005ae14  call    cs:__imp_IoGetRelatedDeviceObject
0x18005ae1b  nop     dword ptr [rax+rax+00h]
0x18005ae20  mov     rcx, [rbx+8]; DeviceObject
0x18005ae24  mov     rdi, rax
0x18005ae27  call    cs:__imp_IoGetAttachedDevice
0x18005ae2e  nop     dword ptr [rax+rax+00h]
0x18005ae33  mov     rcx, rdi; DeviceObject
0x18005ae36  mov     rbx, rax
0x18005ae39  call    cs:__imp_IoGetAttachedDevice
0x18005ae40  nop     dword ptr [rax+rax+00h]
0x18005ae45  cmp     rax, rbx
0x18005ae48  jnz     loc_18005B45E
0x18005ae4e  lea     rbx, [r14+70h]
0x18005ae52  lea     rdi, [r14+0A0h]
0x18005ae59  mov     rax, [rdi]
0x18005ae5c  mov     ecx, [rax+50h]
0x18005ae5f  bt      ecx, 16h
0x18005ae63  jb      loc_18005B0D6
0x18005ae69  mov     eax, [r14+28h]
0x18005ae6d  xor     r9d, r9d
0x18005ae70  mov     ecx, [r14+6Ch]
0x18005ae74  and     eax, 400h
0x18005ae79  mov     r8, [rdi]
0x18005ae7c  or      eax, 1
0x18005ae7f  mov     rdx, [r14+10h]
0x18005ae83  and     ecx, 1000000h
0x18005ae89  mov     [rsp+150h+EaLength], eax
0x18005ae8d  or      ecx, 102h
0x18005ae93  xor     eax, eax
0x18005ae95  mov     [rsp+150h+CreateOptions], eax
0x18005ae99  mov     qword ptr [rsp+150h+Disposition], rax
0x18005ae9e  mov     qword ptr [rsp+150h+ShareAccess], rax
0x18005aea3  mov     qword ptr [rsp+150h+FileAttributes], rax
0x18005aea8  mov     dword ptr [rsp+150h+AllocationSize], ecx
0x18005aeac  lea     rcx, [rbp+50h+Entry]
0x18005aeb0  call    FltpAllocateInitializeNameGenerationContext
0x18005aeb5  xor     edi, edi
0x18005aeb7  lea     rdx, aMinkernelFsFil_25; "minkernel\\fs\\filtermgr\\filter\\names"...
0x18005aebe  mov     r8d, 11ADh
0x18005aec4  mov     [rsp+150h+AllocationSize], rdi
0x18005aec9  mov     r9d, 0C000009Ah
0x18005aecf  mov     ecx, eax
0x18005aed1  mov     esi, eax
0x18005aed3  call    FltpDbgStatus
0x18005aed8  mov     r13, [rbp+50h+Entry]
0x18005aedc  test    eax, eax
0x18005aede  js      loc_18005B0D6
0x18005aee4  mov     rax, [r14+30h]
0x18005aee8  lea     rcx, stru_18003F340; Lookaside
0x18005aeef  mov     [r13+30h], rax
0x18005aef3  mov     rax, [r14+38h]
0x18005aef7  mov     [r13+38h], rax
0x18005aefb  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x18005af02  nop     dword ptr [rax+rax+00h]
0x18005af07  mov     [r13+70h], rax
0x18005af0b  mov     rcx, rax
0x18005af0e  test    rax, rax
0x18005af11  jz      loc_18005B46C
0x18005af17  mov     [rax+10h], edi
0x18005af1a  xorps   xmm0, xmm0
0x18005af1d  mov     [rax+18h], edi
  ... truncated ...
```
