# LuafvPreCreate

- ea: `0x140025820`
- end: `0x1400261f3`
- name: `LuafvPreCreate`
- size: `2515`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `23`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callees

- `0x140001adc`
- `0x140001c0c`
- `0x140002348`
- `0x140003b6c`
- `0x1400045c0`
- `0x1400047cc`
- `0x140004c3c`
- `0x140004e18`
- `0x140014a90`
- `0x1400184e0`
- `0x1400185bc`
- `0x140018760`
- `0x140019730`
- `0x140019a24`
- `0x14001a378`
- `0x14001dbd0`
- `0x14001dd40`
- `0x14001fc40`
- `0x140020850`
- `0x140020e40`
- `0x140021730`
- `0x14002249c`
- `0x140025820`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x140025a6b`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140025a6b`
- `ntoskrnl!RtlEqualSid` at `0x140025b9d`
- `ntoskrnl!RtlEqualSid` at `0x140025b9d`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140025d18`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140025d18`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140025a22`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140025a22`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025cf8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025cf8`
- `ntoskrnl!ExAllocatePool2` at `0x140025cd1`
- `ntoskrnl!ExAllocatePool2` at `0x140025cd1`
- `FLTMGR!FltIsEcpFromUserMode` at `0x14002590c`
- `FLTMGR!FltIsEcpFromUserMode` at `0x14002595e`
- `FLTMGR!FltIsEcpFromUserMode` at `0x14002590c`
- `FLTMGR!FltIsEcpFromUserMode` at `0x14002595e`
- `FLTMGR!FltFindExtraCreateParameter` at `0x1400258f1`
- `FLTMGR!FltFindExtraCreateParameter` at `0x14002593f`
- `FLTMGR!FltFindExtraCreateParameter` at `0x1400258f1`
- `FLTMGR!FltFindExtraCreateParameter` at `0x14002593f`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x1400258bd`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x1400258bd`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140025d36`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140025d36`
- `FLTMGR!FltReleaseContext` at `0x140025a07`
- `FLTMGR!FltReleaseContext` at `0x14002617c`
- `FLTMGR!FltReleaseContext` at `0x140025a07`
- `FLTMGR!FltReleaseContext` at `0x14002617c`
- `FLTMGR!FltGetInstanceContext` at `0x1400259b3`
- `FLTMGR!FltGetInstanceContext` at `0x1400259b3`
- `FLTMGR!FltReferenceContext` at `0x140025a39`
- `FLTMGR!FltReferenceContext` at `0x140025a39`

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
  PFLT_IO_PARAMETER_BLOCK Iopb; // rdx
  char v14; // r14
  char v15; // r12
  int IsTargetWRP; // eax
  ULONG Options; // r12d
  NTSTATUS IsSystemManagedAdminCaller; // ebx
  PFLT_IO_PARAMETER_BLOCK v19; // rdx
  int v20; // ebx
  int v21; // edx
  int v22; // eax
  PFLT_IO_PARAMETER_BLOCK v23; // rdx
  int v24; // edx
  int v25; // ebx
  int v26; // r9d
  __int64 Pool2; // rdi
  PFILE_OBJECT TargetFileObject; // rbx
  PWSTR Buffer; // rcx
  int VirtualizationCaller; // eax
  __int64 *v31; // r8
  __int64 v32; // rdx
  int v33; // edx
  char v34; // cl
  __int64 v35; // r9
  __int64 v36; // r14
  PFLT_INSTANCE *v37; // rbx
  char IsVirtualFileObject; // r15
  NTSTATUS v39; // eax
  char v40; // al
  char v41; // al
  _DWORD *v42; // r15
  char v43; // bl
  PFLT_IO_PARAMETER_BLOCK v44; // rax
  char v45; // cl
  char v46; // al
  char v47; // [rsp+48h] [rbp-79h] BYREF
  _BYTE v48[8]; // [rsp+49h] [rbp-78h] BYREF
  char v49; // [rsp+51h] [rbp-70h] BYREF
  char v50; // [rsp+52h] [rbp-6Fh]
  char v51; // [rsp+53h] [rbp-6Eh]
  __int64 v52; // [rsp+58h] [rbp-69h] BYREF
  PVOID EcpContext; // [rsp+60h] [rbp-61h] BYREF
  int v54[2]; // [rsp+68h] [rbp-59h] BYREF
  __int64 v55; // [rsp+70h] [rbp-51h] BYREF
  int v56; // [rsp+78h] [rbp-49h] BYREF
  PECP_LIST EcpList; // [rsp+80h] [rbp-41h] BYREF
  UNICODE_STRING SourceString; // [rsp+88h] [rbp-39h] BYREF
  PFLT_CONTEXT Context; // [rsp+98h] [rbp-29h] BYREF
  PFLT_CONTEXT v60; // [rsp+A0h] [rbp-21h] BYREF
  UNICODE_STRING String1; // [rsp+A8h] [rbp-19h] BYREF
  __int64 v62; // [rsp+B8h] [rbp-9h] BYREF
  __int64 v63; // [rsp+C0h] [rbp-1h]
  struct _UNICODE_STRING DestinationString; // [rsp+C8h] [rbp+7h] BYREF
  struct _UNICODE_STRING v65; // [rsp+D8h] [rbp+17h] BYREF
  char v68; // [rsp+140h] [rbp+7Fh]

  v4 = 0;
  v60 = 0;
  v62 = 0;
  EcpList = 0;
  EcpContext = 0;
  v7 = 1;
  Context = 0;
  String1 = 0;
  v63 = 0;
  DestinationString = 0;
  v52 = 0;
  SourceString = 0;
  v56 = 0;
  v68 = 0;
  v49 = 0;
  v47 = 0;
  v51 = 0;
  v50 = 0;
  memset(v48, 0, sizeof(v48));
  *(_QWORD *)v54 = 0;
  v55 = 0;
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
        if ( v8 && (dword_14000EAD8 & 8) == 0 && ((dword_14000EAD8 & 4) == 0 || (v8 & 0x400) == 0) )
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
  v14 = 0;
  v15 = 0;
  if ( (*(_DWORD *)(Iopb->Parameters.WMI.ProviderId + 16) & 0xD0156) != 0
    || (Iopb->Parameters.Create.Options & 0xFF000000) != 0x1000000 )
  {
    LuafvIsRequestorProcessExcludedForWRP(CallbackData);
    IsTargetWRP = LuafvIsTargetWRP(CallbackData, a2, &v49);
    if ( IsTargetWRP >= 0 )
    {
      v68 = v49;
    }
    else
    {
      if ( IsTargetWRP != -1073741773 && IsTargetWRP != -1073741790 )
        LuafvLogFileError(CallbackData, 0, LuafvIsTargetWRPFailed, (unsigned int)IsTargetWRP);
      v68 = 0;
    }
  }
  if ( (unsigned int)Feature_ShadowAdminAppCompat__private_IsEnabledDeviceUsageNoInline() )
  {
    Options = CallbackData->Iopb->Parameters.Create.Options;
    IsSystemManagedAdminCaller = LuafvIsSystemManagedAdminCaller(CallbackData, &v47);
    if ( IsSystemManagedAdminCaller < 0 )
      goto LABEL_127;
    v15 = Options & 1;
    if ( v47 )
    {
      v19 = CallbackData->Iopb;
      if ( ((*(_DWORD *)(v19->Parameters.WMI.ProviderId + 16) & 0xD0156) != 0
         || (v19->Parameters.Create.Options & 0xFF000000) != 0x1000000
         || (v19->Parameters.Create.Options & 1) != 0)
        && CallbackData->RequestorMode == 1 )
      {
        IsSystemManagedAdminCaller = LuafvLookupSystemManagedAdminAndUser(CallbackData, v54, &v55);
        if ( IsSystemManagedAdminCaller < 0 )
          goto LABEL_127;
        v20 = v54[0];
        if ( !RtlEqualSid((PSID)(*(_QWORD *)v54 + 80LL), (PSID)(v55 + 80)) )
        {
          v22 = LuafvIsInProfile((int)CallbackData, v21, v20, (int)v48, 0);
          IsSystemManagedAdminCaller = v22;
          if ( v22 == -1073741766 )
          {
            v23 = CallbackData->Iopb;
            if ( (*(_DWORD *)(v23->Parameters.WMI.ProviderId + 16) & 0xD0156) == 0
              && (v23->Parameters.Create.Options & 0xFF000000) == 0x1000000 )
            {
              goto LABEL_131;
            }
            IsSystemManagedAdminCaller = LuafvCheckAndCreateAdminDirectoryTree(a2, *(_QWORD *)v54, v55);
            if ( IsSystemManagedAdminCaller < 0 )
              goto LABEL_127;
            goto LABEL_41;
          }
          if ( v22 < 0 )
            goto LABEL_127;
          if ( v48[0] )
          {
LABEL_41:
            v47 = 1;
LABEL_69:
            VirtualizationCaller = LuafvCreateStreamHandleContext(&v60);
            IsSystemManagedAdminCaller = VirtualizationCaller;
            if ( VirtualizationCaller >= 0 )
            {
              v42 = v60;
              v43 = v48[2];
              *(_QWORD *)v60 = v52;
              v44 = CallbackData->Iopb;
              v52 = 0;
              v42[10] = v44->Parameters.Create.Options;
              v42[11] = *(_DWORD *)(CallbackData->Iopb->Parameters.WMI.ProviderId + 16);
              v42[12] = *(_DWORD *)&v48[3];
              v42[13] = 0;
              *((_BYTE *)v42 + 52) = v51 & 1 | (2 * (v43 & 1 | (4 * (v4 & 1 | (2 * (v68 & 1))))));
              v45 = *((_BYTE *)v42 + 53) & 0xF7 | (v42[10] >> 9) & 8;
              *((_BYTE *)v42 + 53) = v45;
              if ( CallbackData->RequestorMode != 1 )
                *((_BYTE *)v42 + 53) = v45 | 1;
              if ( (unsigned int)Feature_ShadowAdminAppCompat__private_IsEnabledDeviceUsageNoInline() )
              {
                if ( v47 )
                {
                  v46 = *((_BYTE *)v42 + 53);
                  if ( (v46 & 1) == 0 )
                  {
                    *((_BYTE *)v42 + 53) = (32 * v15) | (16 * v47) & 0xDF | v46 & 0xCF;
                    *((_QWORD *)v42 + 1) = *(_QWORD *)v54;
                    *((_QWORD *)v42 + 2) = v55;
                  }
                }
              }
              if ( !v14 )
              {
                Feature_ShadowAdminAppCompat__private_IsEnabledDeviceUsageNoInline();
                v7 = 0;
                *a3 = v42;
                goto LABEL_131;
              }
              IsSystemManagedAdminCaller = LuafvReparse(CallbackData);
              FltReleaseContext(v42);
              if ( IsSystemManagedAdminCaller >= 0 )
              {
                v7 = ((IsSystemManagedAdminCaller >> 31) & 0xFFFFFFFD) + 4;
                goto LABEL_131;
              }
              goto LABEL_127;
            }
            v31 = LuafvCreateStreamHandleContextFailed;
LABEL_106:
            v32 = v52;
            goto LABEL_56;
          }
        }
      }
    }
    else if ( (int)LuafvGetUserAndLinkedSystemManagedAdmin(CallbackData, &v55, v54) >= 0 && *(_QWORD *)v54 )
    {
      IsSystemManagedAdminCaller = LuafvIsInProfile((int)CallbackData, v24, v54[0], (int)v48, &DestinationString);
      if ( IsSystemManagedAdminCaller < 0 )
        goto LABEL_127;
      v25 = v54[0];
      v65 = DestinationString;
      if ( !(unsigned int)LuafvIsFileInSystemManagedAdminAppData(*(_QWORD *)v54, &v65) )
        goto LABEL_131;
      if ( v48[0] )
      {
        IsSystemManagedAdminCaller = LuafvGetMirrorFileName(
                                       v25,
                                       v55,
                                       (unsigned int)&DestinationString,
                                       v26,
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
    v31 = (__int64 *)&LuafvQueryVirtualizationFailed;
LABEL_55:
    v32 = 0;
LABEL_56:
    LuafvLogFileError(CallbackData, v32, v31, (unsigned int)VirtualizationCaller);
    goto LABEL_127;
  }
  v33 = *(_DWORD *)&v48[3];
  v47 = 0;
  v51 = v50;
  if ( !v50 )
  {
    if ( v68 )
      goto LABEL_69;
    if ( (dword_14000EAD8 & 8) == 0 || !*(_DWORD *)&v48[3] )
      goto LABEL_131;
  }
  if ( (v48[3] & 1) != 0 )
    goto LABEL_69;
  if ( (CallbackData->Iopb->Parameters.Create.Options & 0x2000) != 0 )
  {
    v33 = *(_DWORD *)&v48[3] | 4;
    v34 = 0;
    *(_DWORD *)&v48[3] |= 4u;
    if ( (dword_14000EAD8 & 8) == 0 )
    {
LABEL_67:
      if ( (dword_14000EAD8 & 8) == 0 && !v68 )
        goto LABEL_131;
      goto LABEL_69;
    }
  }
  else
  {
    v34 = 1;
  }
  v35 = *(_QWORD *)(a2 + 32);
  if ( (*(_DWORD *)(v35 + 80) & 0x800) != 0 )
  {
    *(_DWORD *)&v48[3] = v33 | 8;
    goto LABEL_67;
  }
  if ( !v34 )
    goto LABEL_67;
  v36 = *(_QWORD *)(v35 + 64);
  v37 = (PFLT_INSTANCE *)(a2 + 24);
  if ( v36 )
  {
    if ( (int)LuafvGetNameFileObject(*v37, *(PFILE_OBJECT *)(v35 + 64)) < 0 )
      goto LABEL_131;
    IsVirtualFileObject = LuafvIsVirtualFileObject(*v37, v36);
    v35 = *(_QWORD *)(a2 + 32);
  }
  else
  {
    IsVirtualFileObject = 0;
  }
  VirtualizationCaller = LuafvQueryStoreFile(
                           (unsigned int)*v37,
                           (_DWORD)CallbackData,
                           (unsigned __int64)&v62 & -(__int64)(v36 != 0),
                           (int)v35 + 88,
                           IsVirtualFileObject != 0,
                           (__int64)&v52,
                           (__int64)&v56,
                           (__int64)&v48[3]);
  IsSystemManagedAdminCaller = VirtualizationCaller;
  if ( VirtualizationCaller >= 0 )
  {
    if ( (v56 & 2) != 0 )
    {
      v7 = 4;
      v39 = -1073741790;
      if ( (CallbackData->Iopb->Parameters.Create.Options & 0xFF000000) == 0x1000000 )
        v39 = -1073741772;
      CallbackData->IoStatus.Status = v39;
      CallbackData->IoStatus.Information = 0;
      if ( (dword_14000EAD8 & 4) != 0 || (dword_14000EAD8 & 8) != 0 )
        LuafvLogExclusion((_DWORD)CallbackData);
      goto LABEL_131;
    }
    v14 = v56 & 1;
    if ( !v52 )
    {
      if ( ((dword_14000EAD8 & 4) == 0 || (*(_WORD *)&v48[3] & 0x400) == 0) && !v68 )
        goto LABEL_133;
      goto LABEL_69;
    }
    if ( v14 )
    {
      if ( (*(_BYTE *)(v52 + 40) & 4) != 0 )
      {
        v40 = *(_BYTE *)(v52 + 88);
        if ( (v40 & 1) != 0 && ((*(_BYTE *)(v52 + 40) & 4) != 0) == ((v40 & 4) != 0) )
          v4 = 1;
      }
      goto LABEL_114;
    }
    if ( !*(_DWORD *)&v48[3] || (dword_14000EAD8 & 8) != 0 )
    {
      VirtualizationCaller = LuafvSelectFile(
                               (_DWORD)CallbackData,
                               a2,
                               v52,
                               (unsigned int)&v48[2],
                               (__int64)&v48[1],
                               (__int64)&v48[3]);
      IsSystemManagedAdminCaller = VirtualizationCaller;
      if ( VirtualizationCaller < 0 )
      {
        if ( VirtualizationCaller == -1073741773 )
          goto LABEL_127;
        v31 = LuafvSelectFileFailed;
        goto LABEL_106;
      }
      v4 = v48[1];
      if ( v48[2] != IsVirtualFileObject )
      {
        v14 = 1;
        goto LABEL_114;
      }
      v14 = 0;
    }
    else if ( (*(_BYTE *)(v52 + 40) & 4) != 0 )
    {
      v41 = *(_BYTE *)(v52 + 88);
      if ( (v41 & 1) != 0 && ((*(_BYTE *)(v52 + 40) & 4) != 0) == ((v41 & 4) != 0) )
        v4 = 1;
    }
    if ( (dword_14000EAD8 & 8) == 0 )
    {
      if ( !*(_DWORD *)&v48[3] || v4 )
        goto LABEL_69;
      if ( !v68 )
        goto LABEL_131;
    }
LABEL_114:
    if ( (dword_14000EAD8 & 8) != 0 && v4 && (*(_DWORD *)&v48[3] & 0xFFFFFD4F) != 0 )
      v4 = 0;
    goto LABEL_69;
  }
  if ( VirtualizationCaller != -1073741790 && VirtualizationCaller != -1073741773 )
  {
    v31 = LuafvQueryStoreFileFailed;
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
  if ( v52 )
    LuafvFreeStoreFile();
LABEL_133:
  if ( v63 )
    LuafvFreePool(v63);
  return v7;
}

```

## disassembly

```asm
0x140025820  mov     rax, rsp
0x140025823  mov     [rax+8], rbx
0x140025827  mov     [rax+18h], r8
0x14002582b  mov     [rax+10h], rdx
0x14002582f  push    rbp
0x140025830  push    rsi
0x140025831  push    rdi
0x140025832  push    r12
0x140025834  push    r13
0x140025836  push    r14
0x140025838  push    r15
0x14002583a  lea     rbp, [rax-5Fh]
0x14002583e  sub     rsp, 0E0h
0x140025845  xor     eax, eax
0x140025847  xorps   xmm0, xmm0
0x14002584a  mov     r15, rdx
0x14002584d  movzx   r13d, al
0x140025851  mov     r14, r8
0x140025854  mov     [rbp+57h+var_78], rax
0x140025858  mov     rsi, rcx
0x14002585b  mov     [rbp+57h+var_60], rax
0x14002585f  xorps   xmm1, xmm1
0x140025862  mov     [rbp+57h+EcpList], rax
0x140025866  mov     rdx, rcx; CallbackData
0x140025869  mov     [rbp+57h+EcpContext], rax
0x14002586d  mov     rcx, cs:LuafvDriverData; Filter
0x140025874  lea     r8, [rbp+57h+EcpList]; EcpList
0x140025878  lea     edi, [rax+1]
0x14002587b  mov     [rbp+57h+Context], rax
0x14002587f  movups  xmmword ptr [rbp+57h+String1.Length], xmm0
0x140025883  mov     [rbp+57h+var_58], rax
0x140025887  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x14002588b  mov     [rbp+57h+var_C0], rax
0x14002588f  movups  xmmword ptr [rbp+57h+SourceString.Length], xmm0
0x140025893  mov     [rbp+57h+var_A0], eax
0x140025896  mov     dword ptr [rbp+57h+var_CF+3], eax
0x140025899  mov     [rbp+57h+var_CF+2], al
0x14002589c  mov     [rbp+57h+var_CF+1], r13b
0x1400258a0  mov     [rbp+57h+arg_18], al
0x1400258a3  mov     [rbp+57h+var_C7], al
0x1400258a6  mov     [rbp+57h+var_C8], al
0x1400258a9  mov     [rbp+57h+var_D0], al
0x1400258ac  mov     [rbp+57h+var_C5], al
0x1400258af  mov     [rbp+57h+var_C6], al
0x1400258b2  mov     [rbp+57h+var_CF], al
0x1400258b5  mov     qword ptr [rbp+57h+var_B0], rax
0x1400258b9  mov     [rbp+57h+var_A8], rax
0x1400258bd  call    cs:__imp_FltGetEcpListFromCallbackData
0x1400258c4  nop     dword ptr [rax+rax+00h]
0x1400258c9  mov     rdx, [rbp+57h+EcpList]; EcpList
0x1400258cd  test    rdx, rdx
0x1400258d0  jz      loc_140025A5E
0x1400258d6  mov     rcx, cs:LuafvDriverData; Filter
0x1400258dd  lea     r9, [rbp+57h+EcpContext]; EcpContext
0x1400258e1  lea     r8, GUID_ECP_PREFETCH_OPEN; EcpType
0x1400258e8  mov     [rsp+110h+EcpContextSize], 0; EcpContextSize
0x1400258f1  call    cs:__imp_FltFindExtraCreateParameter
0x1400258f8  nop     dword ptr [rax+rax+00h]
0x1400258fd  test    eax, eax
0x1400258ff  js      short loc_140025920
0x140025901  mov     rdx, [rbp+57h+EcpContext]; EcpContext
0x140025905  mov     rcx, cs:LuafvDriverData; Filter
0x14002590c  call    cs:__imp_FltIsEcpFromUserMode
0x140025913  nop     dword ptr [rax+rax+00h]
0x140025918  test    al, al
0x14002591a  jz      loc_1400261D5
0x140025920  mov     rdx, [rbp+57h+EcpList]; EcpList
0x140025924  lea     r9, [rbp+57h+EcpContext]; EcpContext
0x140025928  mov     rcx, cs:LuafvDriverData; Filter
0x14002592f  lea     r8, LuafvEcpType; EcpType
0x140025936  mov     [rsp+110h+EcpContextSize], 0; EcpContextSize
0x14002593f  call    cs:__imp_FltFindExtraCreateParameter
0x140025946  nop     dword ptr [rax+rax+00h]
0x14002594b  test    eax, eax
0x14002594d  js      loc_140025A5E
0x140025953  mov     rdx, [rbp+57h+EcpContext]; EcpContext
0x140025957  mov     rcx, cs:LuafvDriverData; Filter
0x14002595e  call    cs:__imp_FltIsEcpFromUserMode
0x140025965  nop     dword ptr [rax+rax+00h]
0x14002596a  test    al, al
0x14002596c  jnz     loc_140025A56
0x140025972  mov     rax, [rbp+57h+EcpContext]
0x140025976  mov     rcx, [rax]
0x140025979  mov     edx, [rcx+30h]
0x14002597c  test    edx, edx
0x14002597e  jz      short loc_14002599C
0x140025980  mov     eax, cs:dword_14000EAD8
0x140025986  test    al, 8
0x140025988  jnz     short loc_14002599C
0x14002598a  test    al, 4
0x14002598c  jz      loc_1400261D5
0x140025992  bt      edx, 0Ah
0x140025996  jnb     loc_1400261D5
0x14002599c  mov     rax, [r15+20h]
0x1400259a0  cmp     qword ptr [rax+40h], 0
0x1400259a5  jnz     loc_140025A56
0x1400259ab  mov     rcx, [r15+18h]; Instance
0x1400259af  lea     rdx, [rbp+57h+Context]; Context
0x1400259b3  call    cs:__imp_FltGetInstanceContext
0x1400259ba  nop     dword ptr [rax+rax+00h]
0x1400259bf  test    eax, eax
0x1400259c1  js      loc_1400261B9
0x1400259c7  mov     rax, [rbp+57h+EcpContext]
0x1400259cb  mov     rcx, [rax]
0x1400259ce  mov     al, [rcx+34h]
0x1400259d1  mov     r8, [rcx]
0x1400259d4  and     al, 2
0x1400259d6  mov     rcx, [rbp+57h+Context]; Context
0x1400259da  neg     al
0x1400259dc  sbb     r9, r9
0x1400259df  and     r9d, 30h
0x1400259e3  mov     rax, [rcx+18h]
0x1400259e7  movzx   edx, word ptr [rax+38h]
0x1400259eb  movzx   eax, word ptr [r9+r8+10h]
0x1400259f1  sub     ax, dx
0x1400259f4  mov     [rbp+57h+String1.Length], ax
0x1400259f8  mov     [rbp+57h+String1.MaximumLength], ax
0x1400259fc  mov     eax, edx
0x1400259fe  add     rax, [r9+r8+18h]
0x140025a03  mov     [rbp+57h+String1.Buffer], rax
0x140025a07  call    cs:__imp_FltReleaseContext
0x140025a0e  nop     dword ptr [rax+rax+00h]
0x140025a13  mov     rdx, [r15+20h]
0x140025a17  lea     rcx, [rbp+57h+String1]; String1
0x140025a1b  add     rdx, 58h ; 'X'; String2
0x140025a1f  mov     r8b, dil; CaseInSensitive
0x140025a22  call    cs:__imp_RtlEqualUnicodeString
0x140025a29  nop     dword ptr [rax+rax+00h]
0x140025a2e  test    al, al
0x140025a30  jz      short loc_140025A56
0x140025a32  mov     rcx, [rbp+57h+EcpContext]
0x140025a36  mov     rcx, [rcx]; Context
0x140025a39  call    cs:__imp_FltReferenceContext
0x140025a40  nop     dword ptr [rax+rax+00h]
0x140025a45  mov     rax, [rbp+57h+EcpContext]
0x140025a49  mov     rcx, [rax]
0x140025a4c  xor     eax, eax
0x140025a4e  mov     [r14], rcx
0x140025a51  jmp     loc_1400261D7
0x140025a56  mov     rcx, rsi; CallbackData
0x140025a59  call    LuafvRemoveEcp
0x140025a5e  cmp     cs:DisableVirt, 0
0x140025a65  jnz     loc_1400261B9
0x140025a6b  call    cs:__imp_IoGetTopLevelIrp
0x140025a72  nop     dword ptr [rax+rax+00h]
0x140025a77  test    rax, rax
0x140025a7a  jnz     loc_1400261B9
0x140025a80  mov     rdx, [rsi+10h]
0x140025a84  xor     r14b, r14b
0x140025a87  xor     r12b, r12b
0x140025a8a  mov     rax, [rdx+18h]
0x140025a8e  test    dword ptr [rax+10h], 0D0156h
0x140025a95  jnz     short loc_140025AA6
0x140025a97  mov     eax, [rdx+20h]
0x140025a9a  and     eax, 0FF000000h
0x140025a9f  cmp     eax, 1000000h
0x140025aa4  jz      short loc_140025B05
0x140025aa6  lea     r8, [rbp+57h+var_C8]
0x140025aaa  mov     rdx, r15
0x140025aad  mov     rcx, rsi; CallbackData
0x140025ab0  call    LuafvIsRequestorProcessExcludedForWRP
0x140025ab5  movzx   edx, [rbp+57h+var_C8]
0x140025ab9  xor     ecx, ecx
0x140025abb  test    eax, eax
0x140025abd  cmovs   edx, ecx
0x140025ac0  test    dl, dl
0x140025ac2  jnz     short loc_140025B05
0x140025ac4  lea     r8, [rbp+57h+var_C7]
0x140025ac8  mov     rdx, r15
0x140025acb  mov     rcx, rsi
0x140025ace  call    LuafvIsTargetWRP
0x140025ad3  test    eax, eax
0x140025ad5  jns     short loc_140025AFF
0x140025ad7  cmp     eax, 0C0000033h
0x140025adc  jz      short loc_140025AF9
0x140025ade  cmp     eax, 0C0000022h
0x140025ae3  jz      short loc_140025AF9
0x140025ae5  mov     r9d, eax
0x140025ae8  lea     r8, LuafvIsTargetWRPFailed
0x140025aef  xor     edx, edx
0x140025af1  mov     rcx, rsi
0x140025af4  call    LuafvLogFileError
0x140025af9  mov     [rbp+57h+arg_18], r12b
0x140025afd  jmp     short loc_140025B05
0x140025aff  mov     al, [rbp+57h+var_C7]
0x140025b02  mov     [rbp+57h+arg_18], al
0x140025b05  call    Feature_ShadowAdminAppCompat__private_IsEnabledDeviceUsageNoInline
0x140025b0a  test    eax, eax
0x140025b0c  jz      loc_140025D68
0x140025b12  mov     rax, [rsi+10h]
0x140025b16  lea     rdx, [rbp+57h+var_D0]
0x140025b1a  mov     rcx, rsi
0x140025b1d  mov     r12d, [rax+20h]
0x140025b21  call    LuafvIsSystemManagedAdminCaller
0x140025b26  mov     ebx, eax
0x140025b28  test    eax, eax
0x140025b2a  js      loc_14002618C
0x140025b30  and     r12b, dil
0x140025b33  cmp     [rbp+57h+var_D0], r14b
0x140025b37  jz      loc_140025C2D
0x140025b3d  mov     rdx, [rsi+10h]
0x140025b41  mov     rax, [rdx+18h]
0x140025b45  test    dword ptr [rax+10h], 0D0156h
0x140025b4c  jnz     short loc_140025B69
0x140025b4e  mov     eax, [rdx+20h]
0x140025b51  and     eax, 0FF000000h
0x140025b56  cmp     eax, 1000000h
0x140025b5b  jnz     short loc_140025B69
0x140025b5d  mov     eax, [rdx+20h]
0x140025b60  test    dil, al
0x140025b63  jz      loc_140025D68
0x140025b69  cmp     [rsi+50h], dil
0x140025b6d  jnz     loc_140025D68
0x140025b73  lea     r8, [rbp+57h+var_A8]
0x140025b77  mov     rcx, rsi
0x140025b7a  lea     rdx, [rbp+57h+var_B0]
0x140025b7e  call    LuafvLookupSystemManagedAdminAndUser
0x140025b83  mov     ebx, eax
0x140025b85  test    eax, eax
0x140025b87  js      loc_14002618C
0x140025b8d  mov     rbx, qword ptr [rbp+57h+var_B0]
0x140025b91  mov     rdx, [rbp+57h+var_A8]
0x140025b95  add     rdx, 50h ; 'P'; Sid2
0x140025b99  lea     rcx, [rbx+50h]; Sid1
0x140025b9d  call    cs:__imp_RtlEqualSid
0x140025ba4  nop     dword ptr [rax+rax+00h]
0x140025ba9  test    al, al
0x140025bab  jnz     loc_140025D68
0x140025bb1  lea     r9, [rbp+57h+var_CF]; int
0x140025bb5  mov     [rsp+110h+EcpContextSize], 0; DestinationString
0x140025bbe  mov     r8, rbx; int
0x140025bc1  mov     rcx, rsi; int
0x140025bc4  call    LuafvIsInProfile
0x140025bc9  mov     ebx, eax
0x140025bcb  cmp     eax, 0C000003Ah
0x140025bd0  jnz     short loc_140025C12
0x140025bd2  mov     rdx, [rsi+10h]
0x140025bd6  mov     rax, [rdx+18h]
0x140025bda  test    dword ptr [rax+10h], 0D0156h
0x140025be1  jnz     short loc_140025BF6
0x140025be3  mov     eax, [rdx+20h]
0x140025be6  and     eax, 0FF000000h
0x140025beb  cmp     eax, 1000000h
0x140025bf0  jz      loc_1400261B9
0x140025bf6  mov     r8, [rbp+57h+var_A8]
0x140025bfa  mov     rcx, r15
0x140025bfd  mov     rdx, qword ptr [rbp+57h+var_B0]
0x140025c01  call    LuafvCheckAndCreateAdminDirectoryTree
0x140025c06  mov     ebx, eax
0x140025c08  test    eax, eax
0x140025c0a  js      loc_14002618C
0x140025c10  jmp     short loc_140025C24
0x140025c12  test    eax, eax
0x140025c14  js      loc_14002618C
0x140025c1a  cmp     [rbp+57h+var_CF], r14b
0x140025c1e  jz      loc_140025D68
0x140025c24  mov     [rbp+57h+var_D0], dil
0x140025c28  jmp     loc_140025E18
0x140025c2d  lea     r8, [rbp+57h+var_B0]
0x140025c31  mov     rcx, rsi
0x140025c34  lea     rdx, [rbp+57h+var_A8]
0x140025c38  call    LuafvGetUserAndLinkedSystemManagedAdmin
0x140025c3d  test    eax, eax
0x140025c3f  js      loc_140025D68
0x140025c45  mov     rax, qword ptr [rbp+57h+var_B0]
0x140025c49  test    rax, rax
0x140025c4c  jz      loc_140025D68
0x140025c52  lea     rcx, [rbp+57h+DestinationString]
0x140025c56  mov     r8, rax; int
0x140025c59  mov     [rsp+110h+EcpContextSize], rcx; DestinationString
0x140025c5e  lea     r9, [rbp+57h+var_CF]; int
0x140025c62  mov     rcx, rsi; int
0x140025c65  call    LuafvIsInProfile
0x140025c6a  mov     ebx, eax
0x140025c6c  test    eax, eax
0x140025c6e  js      loc_14002618C
0x140025c74  movaps  xmm0, xmmword ptr [rbp+57h+DestinationString.Length]
0x140025c78  lea     rdx, [rbp+57h+var_40]
0x140025c7c  mov     rbx, qword ptr [rbp+57h+var_B0]
0x140025c80  mov     rcx, rbx
0x140025c83  movdqa  [rbp+57h+var_40], xmm0
0x140025c88  call    LuafvIsFileInSystemManagedAdminAppData
0x140025c8d  test    eax, eax
0x140025c8f  jz      loc_1400261B9
0x140025c95  cmp     [rbp+57h+var_CF], r14b
0x140025c99  jz      loc_140025D68
0x140025c9f  mov     rdx, [rbp+57h+var_A8]
0x140025ca3  lea     rax, [rbp+57h+SourceString]
0x140025ca7  lea     r8, [rbp+57h+DestinationString]
0x140025cab  mov     [rsp+110h+EcpContextSize], rax
0x140025cb0  mov     rcx, rbx
0x140025cb3  call    LuafvGetMirrorFileName
0x140025cb8  mov     ebx, eax
0x140025cba  test    eax, eax
0x140025cbc  js      loc_14002618C
0x140025cc2  movzx   edx, [rbp+57h+SourceString.Length]
0x140025cc6  mov     ecx, 100h
0x140025ccb  mov     r8d, 6661754Ch
0x140025cd1  call    cs:__imp_ExAllocatePool2
0x140025cd8  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
