# LuafvPreCreate

- ea: `0x1400258a0`
- end: `0x14002626a`
- name: `LuafvPreCreate`
- size: `2506`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `0`
- callee_count: `23`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callees

- `0x140001adc`
- `0x140001c0c`
- `0x1400020c0`
- `0x14000393c`
- `0x140004390`
- `0x14000459c`
- `0x140004a74`
- `0x140004c50`
- `0x140014a90`
- `0x140018530`
- `0x14001860c`
- `0x1400187b0`
- `0x140019780`
- `0x140019a74`
- `0x14001a3c8`
- `0x14001dc20`
- `0x14001dd90`
- `0x14001fc90`
- `0x1400208a0`
- `0x140020e90`
- `0x140021780`
- `0x1400224ec`
- `0x1400258a0`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x140025aeb`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140025aeb`
- `ntoskrnl!RtlEqualSid` at `0x140025c1d`
- `ntoskrnl!RtlEqualSid` at `0x140025c1d`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140025d8f`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140025d8f`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140025aa2`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140025aa2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025d6f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025d6f`
- `ntoskrnl!ExAllocatePool2` at `0x140025d48`
- `ntoskrnl!ExAllocatePool2` at `0x140025d48`
- `FLTMGR!FltIsEcpFromUserMode` at `0x14002598c`
- `FLTMGR!FltIsEcpFromUserMode` at `0x1400259de`
- `FLTMGR!FltIsEcpFromUserMode` at `0x14002598c`
- `FLTMGR!FltIsEcpFromUserMode` at `0x1400259de`
- `FLTMGR!FltFindExtraCreateParameter` at `0x140025971`
- `FLTMGR!FltFindExtraCreateParameter` at `0x1400259bf`
- `FLTMGR!FltFindExtraCreateParameter` at `0x140025971`
- `FLTMGR!FltFindExtraCreateParameter` at `0x1400259bf`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x14002593d`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x14002593d`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140025dad`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140025dad`
- `FLTMGR!FltReleaseContext` at `0x140025a87`
- `FLTMGR!FltReleaseContext` at `0x1400261f3`
- `FLTMGR!FltReleaseContext` at `0x140025a87`
- `FLTMGR!FltReleaseContext` at `0x1400261f3`
- `FLTMGR!FltGetInstanceContext` at `0x140025a33`
- `FLTMGR!FltGetInstanceContext` at `0x140025a33`
- `FLTMGR!FltReferenceContext` at `0x140025ab9`
- `FLTMGR!FltReferenceContext` at `0x140025ab9`

## pseudocode

```c
__int64 __fastcall LuafvPreCreate(PFLT_CALLBACK_DATA CallbackData, __int64 a2, _QWORD *a3)
{
  char v4; // r13
  unsigned int v7; // edi
  int v8; // edx
  __int64 v9; // r8
  __int64 v10; // r9
  unsigned int v11; // edx
  __int64 result; // rax
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  PFLT_IO_PARAMETER_BLOCK Iopb; // rdx
  char v17; // r14
  char v18; // r12
  int IsTargetWRP; // eax
  ULONG Options; // r12d
  NTSTATUS IsSystemManagedAdminCaller; // ebx
  PFLT_IO_PARAMETER_BLOCK v22; // rdx
  int v23; // ebx
  int v24; // edx
  int v25; // eax
  PFLT_IO_PARAMETER_BLOCK v26; // rdx
  int v27; // edx
  int v28; // ebx
  int v29; // r9d
  __int64 Pool2; // rdi
  PFILE_OBJECT TargetFileObject; // rbx
  PWSTR Buffer; // rcx
  int VirtualizationCaller; // eax
  __int64 *v34; // r8
  __int64 v35; // rdx
  int v36; // edx
  char v37; // cl
  __int64 v38; // r9
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // r9
  __int64 v42; // r14
  PFLT_INSTANCE *v43; // rbx
  char IsVirtualFileObject; // r15
  NTSTATUS v45; // eax
  char v46; // al
  char v47; // al
  _DWORD *v48; // r15
  char v49; // bl
  PFLT_IO_PARAMETER_BLOCK v50; // rax
  __int64 v51; // rcx
  __int64 v52; // rdx
  __int64 v53; // rcx
  __int64 v54; // r8
  __int64 v55; // r9
  char v56; // al
  char v57; // [rsp+48h] [rbp-69h] BYREF
  _BYTE v58[8]; // [rsp+49h] [rbp-68h] BYREF
  char v59; // [rsp+51h] [rbp-60h] BYREF
  char v60; // [rsp+52h] [rbp-5Fh]
  char v61; // [rsp+53h] [rbp-5Eh]
  __int64 v62; // [rsp+58h] [rbp-59h] BYREF
  PVOID EcpContext; // [rsp+60h] [rbp-51h] BYREF
  int v64[2]; // [rsp+68h] [rbp-49h] BYREF
  __int64 v65; // [rsp+70h] [rbp-41h] BYREF
  int v66; // [rsp+78h] [rbp-39h] BYREF
  PECP_LIST EcpList; // [rsp+80h] [rbp-31h] BYREF
  UNICODE_STRING SourceString; // [rsp+88h] [rbp-29h] BYREF
  PFLT_CONTEXT Context; // [rsp+98h] [rbp-19h] BYREF
  PFLT_CONTEXT v70; // [rsp+A0h] [rbp-11h] BYREF
  UNICODE_STRING String1; // [rsp+A8h] [rbp-9h] BYREF
  __int64 v72; // [rsp+B8h] [rbp+7h] BYREF
  __int64 v73; // [rsp+C0h] [rbp+Fh]
  struct _UNICODE_STRING DestinationString; // [rsp+C8h] [rbp+17h] BYREF
  char v77; // [rsp+130h] [rbp+7Fh]

  v4 = 0;
  v70 = 0;
  v72 = 0;
  EcpList = 0;
  EcpContext = 0;
  v7 = 1;
  Context = 0;
  String1 = 0;
  v73 = 0;
  DestinationString = 0;
  v62 = 0;
  SourceString = 0;
  v66 = 0;
  v77 = 0;
  v59 = 0;
  v57 = 0;
  v61 = 0;
  v60 = 0;
  memset(v58, 0, sizeof(v58));
  *(_QWORD *)v64 = 0;
  v65 = 0;
  FltGetEcpListFromCallbackData(LuafvDriverData, CallbackData, &EcpList);
  if ( EcpList )
  {
    if ( FltFindExtraCreateParameter(LuafvDriverData, EcpList, &GUID_ECP_PREFETCH_OPEN, &EcpContext, 0) >= 0
      && !FltIsEcpFromUserMode(LuafvDriverData, EcpContext) )
    {
      return v7;
    }
    if ( FltFindExtraCreateParameter(LuafvDriverData, EcpList, &LuafvEcpType, &EcpContext, 0) >= 0 )
    {
      if ( !FltIsEcpFromUserMode(LuafvDriverData, EcpContext) )
      {
        v8 = *(_DWORD *)(*(_QWORD *)EcpContext + 48LL);
        if ( v8 && (dword_14000F118 & 8) == 0 && ((dword_14000F118 & 4) == 0 || (v8 & 0x400) == 0) )
          return v7;
        if ( !*(_QWORD *)(*(_QWORD *)(a2 + 32) + 64LL) )
        {
          if ( FltGetInstanceContext(*(PFLT_INSTANCE *)(a2 + 24), &Context) < 0 )
            goto LABEL_131;
          v9 = **(_QWORD **)EcpContext;
          v10 = (*(_BYTE *)(*(_QWORD *)EcpContext + 52LL) & 2) != 0 ? 0x30 : 0;
          v11 = *(unsigned __int16 *)(*((_QWORD *)Context + 3) + 56LL);
          String1.Length = *(_WORD *)(v10 + v9 + 16) - v11;
          String1.MaximumLength = String1.Length;
          String1.Buffer = (PWSTR)(*(_QWORD *)(v10 + v9 + 24) + v11);
          FltReleaseContext(Context);
          if ( RtlEqualUnicodeString(&String1, (PCUNICODE_STRING)(*(_QWORD *)(a2 + 32) + 88LL), 1u) )
          {
            FltReferenceContext(*(PFLT_CONTEXT *)EcpContext);
            result = 0;
            *a3 = *(_QWORD *)EcpContext;
            return result;
          }
        }
      }
      LuafvRemoveEcp(CallbackData);
    }
  }
  if ( DisableVirt || IoGetTopLevelIrp() )
    goto LABEL_131;
  Iopb = CallbackData->Iopb;
  v17 = 0;
  v18 = 0;
  if ( (*(_DWORD *)(Iopb->Parameters.WMI.ProviderId + 16) & 0xD0156) != 0
    || (Iopb->Parameters.Create.Options & 0xFF000000) != 0x1000000 )
  {
    LuafvIsRequestorProcessExcludedForWRP(CallbackData);
    IsTargetWRP = LuafvIsTargetWRP(CallbackData, a2, &v59);
    if ( IsTargetWRP >= 0 )
    {
      v77 = v59;
    }
    else
    {
      if ( IsTargetWRP != -1073741773 && IsTargetWRP != -1073741790 )
        LuafvLogFileError(CallbackData, 0, LuafvIsTargetWRPFailed, (unsigned int)IsTargetWRP);
      v77 = 0;
    }
  }
  if ( (unsigned int)Feature_ShadowAdminAppCompat__private_IsEnabledDeviceUsageNoInline(v13, Iopb, v14, v15) )
  {
    Options = CallbackData->Iopb->Parameters.Create.Options;
    IsSystemManagedAdminCaller = LuafvIsSystemManagedAdminCaller(CallbackData, &v57);
    if ( IsSystemManagedAdminCaller < 0 )
      goto LABEL_127;
    v18 = Options & 1;
    if ( v57 )
    {
      v22 = CallbackData->Iopb;
      if ( ((*(_DWORD *)(v22->Parameters.WMI.ProviderId + 16) & 0xD0156) != 0
         || (v22->Parameters.Create.Options & 0xFF000000) != 0x1000000
         || (v22->Parameters.Create.Options & 1) != 0)
        && CallbackData->RequestorMode == 1 )
      {
        IsSystemManagedAdminCaller = LuafvLookupSystemManagedAdminAndUser(CallbackData, v64, &v65);
        if ( IsSystemManagedAdminCaller < 0 )
          goto LABEL_127;
        v23 = v64[0];
        if ( !RtlEqualSid(*(PSID *)(*(_QWORD *)v64 + 80LL), *(PSID *)(v65 + 80)) )
        {
          v25 = LuafvIsInProfile((int)CallbackData, v24, v23, (int)v58, 0);
          IsSystemManagedAdminCaller = v25;
          if ( v25 == -1073741766 )
          {
            v26 = CallbackData->Iopb;
            if ( (*(_DWORD *)(v26->Parameters.WMI.ProviderId + 16) & 0xD0156) == 0
              && (v26->Parameters.Create.Options & 0xFF000000) == 0x1000000 )
            {
              goto LABEL_131;
            }
            IsSystemManagedAdminCaller = LuafvCheckAndCreateAdminDirectoryTree(a2, *(_QWORD *)v64, v65);
            if ( IsSystemManagedAdminCaller < 0 )
              goto LABEL_127;
            goto LABEL_41;
          }
          if ( v25 < 0 )
            goto LABEL_127;
          if ( v58[0] )
          {
LABEL_41:
            v57 = 1;
LABEL_69:
            VirtualizationCaller = LuafvCreateStreamHandleContext(&v70);
            IsSystemManagedAdminCaller = VirtualizationCaller;
            if ( VirtualizationCaller >= 0 )
            {
              v48 = v70;
              v49 = v58[2];
              *(_QWORD *)v70 = v62;
              v50 = CallbackData->Iopb;
              v62 = 0;
              v48[10] = v50->Parameters.Create.Options;
              v48[11] = *(_DWORD *)(CallbackData->Iopb->Parameters.WMI.ProviderId + 16);
              v48[12] = *(_DWORD *)&v58[3];
              v48[13] = 0;
              *((_BYTE *)v48 + 52) = v61 & 1 | (2 * (v49 & 1 | (4 * (v4 & 1 | (2 * (v77 & 1))))));
              v51 = v48[10] >> 9;
              LOBYTE(v51) = *((_BYTE *)v48 + 53) & 0xF7 | v51 & 8;
              *((_BYTE *)v48 + 53) = v51;
              if ( CallbackData->RequestorMode != 1 )
              {
                LOBYTE(v51) = v51 | 1;
                *((_BYTE *)v48 + 53) = v51;
              }
              if ( (unsigned int)Feature_ShadowAdminAppCompat__private_IsEnabledDeviceUsageNoInline(v51, v39, v40, v41) )
              {
                LOBYTE(v53) = v57;
                if ( v57 )
                {
                  v56 = *((_BYTE *)v48 + 53);
                  if ( (v56 & 1) == 0 )
                  {
                    LOBYTE(v53) = 16 * v57;
                    *((_BYTE *)v48 + 53) = (32 * v18) | (16 * v57) & 0xDF | v56 & 0xCF;
                    *((_QWORD *)v48 + 1) = *(_QWORD *)v64;
                    *((_QWORD *)v48 + 2) = v65;
                  }
                }
              }
              if ( !v17 )
              {
                Feature_ShadowAdminAppCompat__private_IsEnabledDeviceUsageNoInline(v53, v52, v54, v55);
                v7 = 0;
                *a3 = v48;
                goto LABEL_131;
              }
              IsSystemManagedAdminCaller = LuafvReparse(CallbackData);
              FltReleaseContext(v48);
              if ( IsSystemManagedAdminCaller >= 0 )
              {
                v7 = ((IsSystemManagedAdminCaller >> 31) & 0xFFFFFFFD) + 4;
                goto LABEL_131;
              }
              goto LABEL_127;
            }
            v34 = LuafvCreateStreamHandleContextFailed;
LABEL_106:
            v35 = v62;
            goto LABEL_56;
          }
        }
      }
    }
    else if ( (int)LuafvGetUserAndLinkedSystemManagedAdmin((__int64)CallbackData, &v65, v64) >= 0 && *(_QWORD *)v64 )
    {
      IsSystemManagedAdminCaller = LuafvIsInProfile((int)CallbackData, v27, v64[0], (int)v58, &DestinationString);
      if ( IsSystemManagedAdminCaller < 0 )
        goto LABEL_127;
      v28 = v64[0];
      if ( !(unsigned int)LuafvIsFileInSystemManagedAdminAppData(*(_QWORD *)v64, &DestinationString) )
        goto LABEL_131;
      if ( v58[0] )
      {
        IsSystemManagedAdminCaller = LuafvGetMirrorFileName(
                                       v28,
                                       v65,
                                       (unsigned int)&DestinationString,
                                       v29,
                                       (__int64)&SourceString);
        if ( IsSystemManagedAdminCaller >= 0 )
        {
          Pool2 = ExAllocatePool2(256, SourceString.Length, 1717663052);
          if ( Pool2 )
          {
            TargetFileObject = CallbackData->Iopb->TargetFileObject;
            Buffer = TargetFileObject->FileName.Buffer;
            if ( Buffer )
              ExFreePoolWithTag(Buffer, 0);
            TargetFileObject->FileName.MaximumLength = SourceString.Length;
            TargetFileObject->FileName.Buffer = (PWSTR)Pool2;
            RtlCopyUnicodeString(&TargetFileObject->FileName, &SourceString);
            CallbackData->IoStatus.Information = 0;
            CallbackData->IoStatus.Status = 260;
            FltSetCallbackDataDirty(CallbackData);
            v7 = 4;
            LuafvFreePool(SourceString.Buffer);
            goto LABEL_131;
          }
          IsSystemManagedAdminCaller = -1073741670;
          LuafvFreePool(SourceString.Buffer);
          goto LABEL_129;
        }
        goto LABEL_127;
      }
    }
  }
  VirtualizationCaller = LuafvQueryVirtualizationCaller((_DWORD)CallbackData);
  IsSystemManagedAdminCaller = VirtualizationCaller;
  if ( VirtualizationCaller < 0 )
  {
    v34 = (__int64 *)&LuafvQueryVirtualizationFailed;
LABEL_55:
    v35 = 0;
LABEL_56:
    LuafvLogFileError(CallbackData, v35, v34, (unsigned int)VirtualizationCaller);
    goto LABEL_127;
  }
  v36 = *(_DWORD *)&v58[3];
  v57 = 0;
  v61 = v60;
  if ( !v60 )
  {
    if ( v77 )
      goto LABEL_69;
    if ( (dword_14000F118 & 8) == 0 || !*(_DWORD *)&v58[3] )
      goto LABEL_131;
  }
  if ( (v58[3] & 1) != 0 )
    goto LABEL_69;
  if ( (CallbackData->Iopb->Parameters.Create.Options & 0x2000) != 0 )
  {
    v36 = *(_DWORD *)&v58[3] | 4;
    v37 = 0;
    *(_DWORD *)&v58[3] |= 4u;
    if ( (dword_14000F118 & 8) == 0 )
    {
LABEL_67:
      if ( (dword_14000F118 & 8) == 0 && !v77 )
        goto LABEL_131;
      goto LABEL_69;
    }
  }
  else
  {
    v37 = 1;
  }
  v38 = *(_QWORD *)(a2 + 32);
  if ( (*(_DWORD *)(v38 + 80) & 0x800) != 0 )
  {
    *(_DWORD *)&v58[3] = v36 | 8;
    goto LABEL_67;
  }
  if ( !v37 )
    goto LABEL_67;
  v42 = *(_QWORD *)(v38 + 64);
  v43 = (PFLT_INSTANCE *)(a2 + 24);
  if ( v42 )
  {
    if ( (int)LuafvGetNameFileObject(*v43, *(PFILE_OBJECT *)(v38 + 64)) < 0 )
      goto LABEL_131;
    IsVirtualFileObject = LuafvIsVirtualFileObject(*v43, v42);
    v38 = *(_QWORD *)(a2 + 32);
  }
  else
  {
    IsVirtualFileObject = 0;
  }
  VirtualizationCaller = LuafvQueryStoreFile(
                           (unsigned int)*v43,
                           (_DWORD)CallbackData,
                           (unsigned __int64)&v72 & -(__int64)(v42 != 0),
                           (int)v38 + 88,
                           IsVirtualFileObject != 0,
                           (__int64)&v62,
                           (__int64)&v66,
                           (__int64)&v58[3]);
  IsSystemManagedAdminCaller = VirtualizationCaller;
  if ( VirtualizationCaller >= 0 )
  {
    if ( (v66 & 2) != 0 )
    {
      v7 = 4;
      v45 = -1073741790;
      if ( (CallbackData->Iopb->Parameters.Create.Options & 0xFF000000) == 0x1000000 )
        v45 = -1073741772;
      CallbackData->IoStatus.Status = v45;
      CallbackData->IoStatus.Information = 0;
      if ( (dword_14000F118 & 4) != 0 || (dword_14000F118 & 8) != 0 )
        LuafvLogExclusion((_DWORD)CallbackData);
      goto LABEL_131;
    }
    v17 = v66 & 1;
    if ( !v62 )
    {
      if ( ((dword_14000F118 & 4) == 0 || (*(_WORD *)&v58[3] & 0x400) == 0) && !v77 )
        goto LABEL_133;
      goto LABEL_69;
    }
    if ( v17 )
    {
      if ( (*(_BYTE *)(v62 + 40) & 4) != 0 )
      {
        v46 = *(_BYTE *)(v62 + 88);
        if ( (v46 & 1) != 0 && ((*(_BYTE *)(v62 + 40) & 4) != 0) == ((v46 & 4) != 0) )
          v4 = 1;
      }
      goto LABEL_114;
    }
    if ( !*(_DWORD *)&v58[3] || (dword_14000F118 & 8) != 0 )
    {
      VirtualizationCaller = LuafvSelectFile(
                               (_DWORD)CallbackData,
                               a2,
                               v62,
                               (unsigned int)&v58[2],
                               (__int64)&v58[1],
                               (__int64)&v58[3]);
      IsSystemManagedAdminCaller = VirtualizationCaller;
      if ( VirtualizationCaller < 0 )
      {
        if ( VirtualizationCaller == -1073741773 )
          goto LABEL_127;
        v34 = LuafvSelectFileFailed;
        goto LABEL_106;
      }
      v4 = v58[1];
      if ( v58[2] != IsVirtualFileObject )
      {
        v17 = 1;
        goto LABEL_114;
      }
      v17 = 0;
    }
    else if ( (*(_BYTE *)(v62 + 40) & 4) != 0 )
    {
      v47 = *(_BYTE *)(v62 + 88);
      if ( (v47 & 1) != 0 && ((*(_BYTE *)(v62 + 40) & 4) != 0) == ((v47 & 4) != 0) )
        v4 = 1;
    }
    if ( (dword_14000F118 & 8) == 0 )
    {
      if ( !*(_DWORD *)&v58[3] || v4 )
        goto LABEL_69;
      if ( !v77 )
        goto LABEL_131;
    }
LABEL_114:
    if ( (dword_14000F118 & 8) != 0 && v4 && (*(_DWORD *)&v58[3] & 0xFFFFFD4F) != 0 )
      v4 = 0;
    goto LABEL_69;
  }
  if ( VirtualizationCaller != -1073741790 && VirtualizationCaller != -1073741773 )
  {
    v34 = LuafvQueryStoreFileFailed;
    goto LABEL_55;
  }
LABEL_127:
  if ( IsSystemManagedAdminCaller == -1073741670 || IsSystemManagedAdminCaller == -1073741773 )
  {
LABEL_129:
    CallbackData->IoStatus.Status = IsSystemManagedAdminCaller;
    v7 = 4;
    CallbackData->IoStatus.Information = 0;
  }
LABEL_131:
  if ( v62 )
    LuafvFreeStoreFile();
LABEL_133:
  if ( v73 )
    LuafvFreePool(v73);
  return v7;
}

```

## disassembly

```asm
0x1400258a0  mov     rax, rsp
0x1400258a3  mov     [rax+8], rbx
0x1400258a7  mov     [rax+18h], r8
0x1400258ab  mov     [rax+10h], rdx
0x1400258af  push    rbp
0x1400258b0  push    rsi
0x1400258b1  push    rdi
0x1400258b2  push    r12
0x1400258b4  push    r13
0x1400258b6  push    r14
0x1400258b8  push    r15
0x1400258ba  lea     rbp, [rax-5Fh]
0x1400258be  sub     rsp, 0D0h
0x1400258c5  xor     eax, eax
0x1400258c7  xorps   xmm0, xmm0
0x1400258ca  mov     r15, rdx
0x1400258cd  movzx   r13d, al
0x1400258d1  mov     r14, r8
0x1400258d4  mov     [rbp+57h+var_68], rax
0x1400258d8  mov     rsi, rcx
0x1400258db  mov     [rbp+57h+var_50], rax
0x1400258df  xorps   xmm1, xmm1
0x1400258e2  mov     [rbp+57h+EcpList], rax
0x1400258e6  mov     rdx, rcx; CallbackData
0x1400258e9  mov     [rbp+57h+EcpContext], rax
0x1400258ed  mov     rcx, cs:LuafvDriverData; Filter
0x1400258f4  lea     r8, [rbp+57h+EcpList]; EcpList
0x1400258f8  lea     edi, [rax+1]
0x1400258fb  mov     [rbp+57h+Context], rax
0x1400258ff  movups  xmmword ptr [rbp+57h+String1.Length], xmm0
0x140025903  mov     [rbp+57h+var_48], rax
0x140025907  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x14002590b  mov     [rbp+57h+var_B0], rax
0x14002590f  movups  xmmword ptr [rbp+57h+SourceString.Length], xmm0
0x140025913  mov     [rbp+57h+var_90], eax
0x140025916  mov     dword ptr [rbp+57h+var_BF+3], eax
0x140025919  mov     [rbp+57h+var_BF+2], al
0x14002591c  mov     [rbp+57h+var_BF+1], r13b
0x140025920  mov     [rbp+57h+arg_18], al
0x140025923  mov     [rbp+57h+var_B7], al
0x140025926  mov     [rbp+57h+var_B8], al
0x140025929  mov     [rbp+57h+var_C0], al
0x14002592c  mov     [rbp+57h+var_B5], al
0x14002592f  mov     [rbp+57h+var_B6], al
0x140025932  mov     [rbp+57h+var_BF], al
0x140025935  mov     qword ptr [rbp+57h+var_A0], rax
0x140025939  mov     [rbp+57h+var_98], rax
0x14002593d  call    cs:__imp_FltGetEcpListFromCallbackData
0x140025944  nop     dword ptr [rax+rax+00h]
0x140025949  mov     rdx, [rbp+57h+EcpList]; EcpList
0x14002594d  test    rdx, rdx
0x140025950  jz      loc_140025ADE
0x140025956  mov     rcx, cs:LuafvDriverData; Filter
0x14002595d  lea     r9, [rbp+57h+EcpContext]; EcpContext
0x140025961  lea     r8, GUID_ECP_PREFETCH_OPEN; EcpType
0x140025968  mov     [rsp+100h+EcpContextSize], 0; EcpContextSize
0x140025971  call    cs:__imp_FltFindExtraCreateParameter
0x140025978  nop     dword ptr [rax+rax+00h]
0x14002597d  test    eax, eax
0x14002597f  js      short loc_1400259A0
0x140025981  mov     rdx, [rbp+57h+EcpContext]; EcpContext
0x140025985  mov     rcx, cs:LuafvDriverData; Filter
0x14002598c  call    cs:__imp_FltIsEcpFromUserMode
0x140025993  nop     dword ptr [rax+rax+00h]
0x140025998  test    al, al
0x14002599a  jz      loc_14002624C
0x1400259a0  mov     rdx, [rbp+57h+EcpList]; EcpList
0x1400259a4  lea     r9, [rbp+57h+EcpContext]; EcpContext
0x1400259a8  mov     rcx, cs:LuafvDriverData; Filter
0x1400259af  lea     r8, LuafvEcpType; EcpType
0x1400259b6  mov     [rsp+100h+EcpContextSize], 0; EcpContextSize
0x1400259bf  call    cs:__imp_FltFindExtraCreateParameter
0x1400259c6  nop     dword ptr [rax+rax+00h]
0x1400259cb  test    eax, eax
0x1400259cd  js      loc_140025ADE
0x1400259d3  mov     rdx, [rbp+57h+EcpContext]; EcpContext
0x1400259d7  mov     rcx, cs:LuafvDriverData; Filter
0x1400259de  call    cs:__imp_FltIsEcpFromUserMode
0x1400259e5  nop     dword ptr [rax+rax+00h]
0x1400259ea  test    al, al
0x1400259ec  jnz     loc_140025AD6
0x1400259f2  mov     rax, [rbp+57h+EcpContext]
0x1400259f6  mov     rcx, [rax]
0x1400259f9  mov     edx, [rcx+30h]
0x1400259fc  test    edx, edx
0x1400259fe  jz      short loc_140025A1C
0x140025a00  mov     eax, cs:dword_14000F118
0x140025a06  test    al, 8
0x140025a08  jnz     short loc_140025A1C
0x140025a0a  test    al, 4
0x140025a0c  jz      loc_14002624C
0x140025a12  bt      edx, 0Ah
0x140025a16  jnb     loc_14002624C
0x140025a1c  mov     rax, [r15+20h]
0x140025a20  cmp     qword ptr [rax+40h], 0
0x140025a25  jnz     loc_140025AD6
0x140025a2b  mov     rcx, [r15+18h]; Instance
0x140025a2f  lea     rdx, [rbp+57h+Context]; Context
0x140025a33  call    cs:__imp_FltGetInstanceContext
0x140025a3a  nop     dword ptr [rax+rax+00h]
0x140025a3f  test    eax, eax
0x140025a41  js      loc_140026230
0x140025a47  mov     rax, [rbp+57h+EcpContext]
0x140025a4b  mov     rcx, [rax]
0x140025a4e  mov     al, [rcx+34h]
0x140025a51  mov     r8, [rcx]
0x140025a54  and     al, 2
0x140025a56  mov     rcx, [rbp+57h+Context]; Context
0x140025a5a  neg     al
0x140025a5c  sbb     r9, r9
0x140025a5f  and     r9d, 30h
0x140025a63  mov     rax, [rcx+18h]
0x140025a67  movzx   edx, word ptr [rax+38h]
0x140025a6b  movzx   eax, word ptr [r9+r8+10h]
0x140025a71  sub     ax, dx
0x140025a74  mov     [rbp+57h+String1.Length], ax
0x140025a78  mov     [rbp+57h+String1.MaximumLength], ax
0x140025a7c  mov     eax, edx
0x140025a7e  add     rax, [r9+r8+18h]
0x140025a83  mov     [rbp+57h+String1.Buffer], rax
0x140025a87  call    cs:__imp_FltReleaseContext
0x140025a8e  nop     dword ptr [rax+rax+00h]
0x140025a93  mov     rdx, [r15+20h]
0x140025a97  lea     rcx, [rbp+57h+String1]; String1
0x140025a9b  add     rdx, 58h ; 'X'; String2
0x140025a9f  mov     r8b, dil; CaseInSensitive
0x140025aa2  call    cs:__imp_RtlEqualUnicodeString
0x140025aa9  nop     dword ptr [rax+rax+00h]
0x140025aae  test    al, al
0x140025ab0  jz      short loc_140025AD6
0x140025ab2  mov     rcx, [rbp+57h+EcpContext]
0x140025ab6  mov     rcx, [rcx]; Context
0x140025ab9  call    cs:__imp_FltReferenceContext
0x140025ac0  nop     dword ptr [rax+rax+00h]
0x140025ac5  mov     rax, [rbp+57h+EcpContext]
0x140025ac9  mov     rcx, [rax]
0x140025acc  xor     eax, eax
0x140025ace  mov     [r14], rcx
0x140025ad1  jmp     loc_14002624E
0x140025ad6  mov     rcx, rsi; CallbackData
0x140025ad9  call    LuafvRemoveEcp
0x140025ade  cmp     cs:DisableVirt, 0
0x140025ae5  jnz     loc_140026230
0x140025aeb  call    cs:__imp_IoGetTopLevelIrp
0x140025af2  nop     dword ptr [rax+rax+00h]
0x140025af7  test    rax, rax
0x140025afa  jnz     loc_140026230
0x140025b00  mov     rdx, [rsi+10h]
0x140025b04  xor     r14b, r14b
0x140025b07  xor     r12b, r12b
0x140025b0a  mov     rax, [rdx+18h]
0x140025b0e  test    dword ptr [rax+10h], 0D0156h
0x140025b15  jnz     short loc_140025B26
0x140025b17  mov     eax, [rdx+20h]
0x140025b1a  and     eax, 0FF000000h
0x140025b1f  cmp     eax, 1000000h
0x140025b24  jz      short loc_140025B85
0x140025b26  lea     r8, [rbp+57h+var_B8]
0x140025b2a  mov     rdx, r15
0x140025b2d  mov     rcx, rsi; CallbackData
0x140025b30  call    LuafvIsRequestorProcessExcludedForWRP
0x140025b35  movzx   edx, [rbp+57h+var_B8]
0x140025b39  xor     ecx, ecx
0x140025b3b  test    eax, eax
0x140025b3d  cmovs   edx, ecx
0x140025b40  test    dl, dl
0x140025b42  jnz     short loc_140025B85
0x140025b44  lea     r8, [rbp+57h+var_B7]
0x140025b48  mov     rdx, r15
0x140025b4b  mov     rcx, rsi
0x140025b4e  call    LuafvIsTargetWRP
0x140025b53  test    eax, eax
0x140025b55  jns     short loc_140025B7F
0x140025b57  cmp     eax, 0C0000033h
0x140025b5c  jz      short loc_140025B79
0x140025b5e  cmp     eax, 0C0000022h
0x140025b63  jz      short loc_140025B79
0x140025b65  mov     r9d, eax
0x140025b68  lea     r8, LuafvIsTargetWRPFailed
0x140025b6f  xor     edx, edx
0x140025b71  mov     rcx, rsi
0x140025b74  call    LuafvLogFileError
0x140025b79  mov     [rbp+57h+arg_18], r12b
0x140025b7d  jmp     short loc_140025B85
0x140025b7f  mov     al, [rbp+57h+var_B7]
0x140025b82  mov     [rbp+57h+arg_18], al
0x140025b85  call    Feature_ShadowAdminAppCompat__private_IsEnabledDeviceUsageNoInline
0x140025b8a  test    eax, eax
0x140025b8c  jz      loc_140025DDF
0x140025b92  mov     rax, [rsi+10h]
0x140025b96  lea     rdx, [rbp+57h+var_C0]
0x140025b9a  mov     rcx, rsi
0x140025b9d  mov     r12d, [rax+20h]
0x140025ba1  call    LuafvIsSystemManagedAdminCaller
0x140025ba6  mov     ebx, eax
0x140025ba8  test    eax, eax
0x140025baa  js      loc_140026203
0x140025bb0  and     r12b, dil
0x140025bb3  cmp     [rbp+57h+var_C0], r14b
0x140025bb7  jz      loc_140025CAD
0x140025bbd  mov     rdx, [rsi+10h]
0x140025bc1  mov     rax, [rdx+18h]
0x140025bc5  test    dword ptr [rax+10h], 0D0156h
0x140025bcc  jnz     short loc_140025BE9
0x140025bce  mov     eax, [rdx+20h]
0x140025bd1  and     eax, 0FF000000h
0x140025bd6  cmp     eax, 1000000h
0x140025bdb  jnz     short loc_140025BE9
0x140025bdd  mov     eax, [rdx+20h]
0x140025be0  test    dil, al
0x140025be3  jz      loc_140025DDF
0x140025be9  cmp     [rsi+50h], dil
0x140025bed  jnz     loc_140025DDF
0x140025bf3  lea     r8, [rbp+57h+var_98]
0x140025bf7  mov     rcx, rsi
0x140025bfa  lea     rdx, [rbp+57h+var_A0]
0x140025bfe  call    LuafvLookupSystemManagedAdminAndUser
0x140025c03  mov     ebx, eax
0x140025c05  test    eax, eax
0x140025c07  js      loc_140026203
0x140025c0d  mov     rdx, [rbp+57h+var_98]
0x140025c11  mov     rbx, qword ptr [rbp+57h+var_A0]
0x140025c15  mov     rdx, [rdx+50h]; Sid2
0x140025c19  mov     rcx, [rbx+50h]; Sid1
0x140025c1d  call    cs:__imp_RtlEqualSid
0x140025c24  nop     dword ptr [rax+rax+00h]
0x140025c29  test    al, al
0x140025c2b  jnz     loc_140025DDF
0x140025c31  lea     r9, [rbp+57h+var_BF]; int
0x140025c35  mov     [rsp+100h+EcpContextSize], 0; DestinationString
0x140025c3e  mov     r8, rbx; int
0x140025c41  mov     rcx, rsi; int
0x140025c44  call    LuafvIsInProfile
0x140025c49  mov     ebx, eax
0x140025c4b  cmp     eax, 0C000003Ah
0x140025c50  jnz     short loc_140025C92
0x140025c52  mov     rdx, [rsi+10h]
0x140025c56  mov     rax, [rdx+18h]
0x140025c5a  test    dword ptr [rax+10h], 0D0156h
0x140025c61  jnz     short loc_140025C76
0x140025c63  mov     eax, [rdx+20h]
0x140025c66  and     eax, 0FF000000h
0x140025c6b  cmp     eax, 1000000h
0x140025c70  jz      loc_140026230
0x140025c76  mov     r8, [rbp+57h+var_98]
0x140025c7a  mov     rcx, r15
0x140025c7d  mov     rdx, qword ptr [rbp+57h+var_A0]
0x140025c81  call    LuafvCheckAndCreateAdminDirectoryTree
0x140025c86  mov     ebx, eax
0x140025c88  test    eax, eax
0x140025c8a  js      loc_140026203
0x140025c90  jmp     short loc_140025CA4
0x140025c92  test    eax, eax
0x140025c94  js      loc_140026203
0x140025c9a  cmp     [rbp+57h+var_BF], r14b
0x140025c9e  jz      loc_140025DDF
0x140025ca4  mov     [rbp+57h+var_C0], dil
0x140025ca8  jmp     loc_140025E8F
0x140025cad  lea     r8, [rbp+57h+var_A0]
0x140025cb1  mov     rcx, rsi
0x140025cb4  lea     rdx, [rbp+57h+var_98]
0x140025cb8  call    LuafvGetUserAndLinkedSystemManagedAdmin
0x140025cbd  test    eax, eax
0x140025cbf  js      loc_140025DDF
0x140025cc5  mov     rax, qword ptr [rbp+57h+var_A0]
0x140025cc9  test    rax, rax
0x140025ccc  jz      loc_140025DDF
0x140025cd2  lea     rcx, [rbp+57h+DestinationString]
0x140025cd6  mov     r8, rax; int
0x140025cd9  mov     [rsp+100h+EcpContextSize], rcx; DestinationString
0x140025cde  lea     r9, [rbp+57h+var_BF]; int
0x140025ce2  mov     rcx, rsi; int
0x140025ce5  call    LuafvIsInProfile
0x140025cea  mov     ebx, eax
0x140025cec  test    eax, eax
0x140025cee  js      loc_140026203
0x140025cf4  mov     rbx, qword ptr [rbp+57h+var_A0]
0x140025cf8  lea     rdx, [rbp+57h+DestinationString]
0x140025cfc  mov     rcx, rbx
0x140025cff  call    LuafvIsFileInSystemManagedAdminAppData
0x140025d04  test    eax, eax
0x140025d06  jz      loc_140026230
0x140025d0c  cmp     [rbp+57h+var_BF], r14b
0x140025d10  jz      loc_140025DDF
0x140025d16  mov     rdx, [rbp+57h+var_98]
0x140025d1a  lea     rax, [rbp+57h+SourceString]
0x140025d1e  lea     r8, [rbp+57h+DestinationString]
0x140025d22  mov     [rsp+100h+EcpContextSize], rax
0x140025d27  mov     rcx, rbx
0x140025d2a  call    LuafvGetMirrorFileName
0x140025d2f  mov     ebx, eax
0x140025d31  test    eax, eax
0x140025d33  js      loc_140026203
0x140025d39  movzx   edx, [rbp+57h+SourceString.Length]
0x140025d3d  mov     ecx, 100h
0x140025d42  mov     r8d, 6661754Ch
0x140025d48  call    cs:__imp_ExAllocatePool2
0x140025d4f  nop     dword ptr [rax+rax+00h]
0x140025d54  mov     rdi, rax
0x140025d57  test    rax, rax
  ... truncated ...
```
