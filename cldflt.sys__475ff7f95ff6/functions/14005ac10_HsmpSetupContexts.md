# HsmpSetupContexts

- ea: `0x14005ac10`
- end: `0x14005bf21`
- name: `HsmpSetupContexts`
- size: `4881`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `34`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140034010`
- `0x1400451d0`
- `0x140046cc0`
- `0x140063ef8`
- `0x14006486c`

## callees

- `0x140001560`
- `0x140001ab4`
- `0x140001b84`
- `0x140003c50`
- `0x140006d70`
- `0x140006f40`
- `0x1400074b0`
- `0x140007bb0`
- `0x140009300`
- `0x140009a3c`
- `0x140009df8`
- `0x14000abb8`
- `0x14000ac28`
- `0x14000cde0`
- `0x14000cffc`
- `0x14000d5b0`
- `0x14000d868`
- `0x14000d9a0`
- `0x14001e1c0`
- `0x1400431dc`
- `0x140058ddc`
- `0x140059090`
- `0x140059738`
- `0x140059768`
- `0x14005a7dc`
- `0x14005ac10`
- `0x14005bf30`
- `0x14005c720`
- `0x14005c9e0`
- `0x14005ce40`
- `0x14006bcf4`
- `0x140076670`
- `0x1400766ac`
- `0x14007a214`

## import_xrefs

- `ntoskrnl!IoGetTransactionParameterBlock` at `0x14005acd7`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x14005acd7`
- `ntoskrnl!ObfDereferenceObject` at `0x14005b5a5`
- `ntoskrnl!ObfDereferenceObject` at `0x14005b5a5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005b5cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005b5e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005b738`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005b5cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005b5e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005b738`
- `ntoskrnl!ExAllocatePool2` at `0x14005b19f`
- `ntoskrnl!ExAllocatePool2` at `0x14005b19f`
- `FLTMGR!FltGetFileNameInformation` at `0x14005b48f`
- `FLTMGR!FltGetFileNameInformation` at `0x14005b48f`
- `FLTMGR!FltParseFileNameInformation` at `0x14005b4bd`
- `FLTMGR!FltParseFileNameInformation` at `0x14005b4bd`
- `FLTMGR!FltSetStreamContext` at `0x14005af26`
- `FLTMGR!FltSetStreamContext` at `0x14005af26`
- `FLTMGR!FltGetStreamContext` at `0x14005ad9f`
- `FLTMGR!FltGetStreamContext` at `0x14005b3c3`
- `FLTMGR!FltGetStreamContext` at `0x14005ad9f`
- `FLTMGR!FltGetStreamContext` at `0x14005b3c3`
- `FLTMGR!FltGetStreamHandleContext` at `0x14005b428`
- `FLTMGR!FltGetStreamHandleContext` at `0x14005b428`
- `FLTMGR!FltQueryInformationFile` at `0x14005ad31`
- `FLTMGR!FltQueryInformationFile` at `0x14005affe`
- `FLTMGR!FltQueryInformationFile` at `0x14005b870`
- `FLTMGR!FltQueryInformationFile` at `0x14005ad31`
- `FLTMGR!FltQueryInformationFile` at `0x14005affe`
- `FLTMGR!FltQueryInformationFile` at `0x14005b870`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x14005b4fb`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x14005b4fb`
- `FLTMGR!FltSetStreamHandleContext` at `0x14005b10e`
- `FLTMGR!FltSetStreamHandleContext` at `0x14005b10e`
- `FLTMGR!FltAcknowledgeEcp` at `0x14005b6a0`
- `FLTMGR!FltAcknowledgeEcp` at `0x14005b6a0`
- `FLTMGR!FltFindExtraCreateParameter` at `0x14005b538`
- `FLTMGR!FltFindExtraCreateParameter` at `0x14005b538`
- `FLTMGR!FltDeleteContext` at `0x14005b43e`
- `FLTMGR!FltDeleteContext` at `0x14005b43e`
- `FLTMGR!FltGetRequestorProcess` at `0x14005ac82`
- `FLTMGR!FltGetRequestorProcess` at `0x14005ac82`
- `FLTMGR!FltReleasePushLockEx` at `0x14005af92`
- `FLTMGR!FltReleasePushLockEx` at `0x14005b0a9`
- `FLTMGR!FltReleasePushLockEx` at `0x14005b407`
- `FLTMGR!FltReleasePushLockEx` at `0x14005b9c1`
- `FLTMGR!FltReleasePushLockEx` at `0x14005baf1`
- `FLTMGR!FltReleasePushLockEx` at `0x14005af92`
- `FLTMGR!FltReleasePushLockEx` at `0x14005b0a9`
- `FLTMGR!FltReleasePushLockEx` at `0x14005b407`
- `FLTMGR!FltReleasePushLockEx` at `0x14005b9c1`
- `FLTMGR!FltReleasePushLockEx` at `0x14005baf1`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14005ad70`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14005ad70`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14005aee5`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14005b02a`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14005b04d`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14005b3e3`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14005aee5`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14005b02a`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14005b04d`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14005b3e3`
- `FLTMGR!FltReleaseContext` at `0x14005b62d`
- `FLTMGR!FltReleaseContext` at `0x14005b64b`
- `FLTMGR!FltReleaseContext` at `0x14005b6c9`
- `FLTMGR!FltReleaseContext` at `0x14005b78b`
- `FLTMGR!FltReleaseContext` at `0x14005bbd2`
- `FLTMGR!FltReleaseContext` at `0x14005be77`
- `FLTMGR!FltReleaseContext` at `0x14005b62d`
- `FLTMGR!FltReleaseContext` at `0x14005b64b`
- `FLTMGR!FltReleaseContext` at `0x14005b6c9`
- `FLTMGR!FltReleaseContext` at `0x14005b78b`
- `FLTMGR!FltReleaseContext` at `0x14005bbd2`
- `FLTMGR!FltReleaseContext` at `0x14005be77`

## pseudocode

```c
__int64 __fastcall HsmpSetupContexts(__int64 a1, struct _FILE_OBJECT *a2, int a3, __int64 a4)
{
  PEPROCESS RequestorProcess; // rax
  struct _FLT_INSTANCE *v9; // r14
  NTSTATUS Buffer; // ebx
  _DWORD *v11; // r15
  __int64 v12; // rax
  __int64 v13; // rcx
  bool v14; // di
  NTSTATUS StreamContext; // edi
  _DWORD *p_Size; // rcx
  struct _FLT_INSTANCE *v17; // rdi
  int SyncRootFileIdByFileObject; // ebx
  NTSTATUS v19; // ebx
  PFLT_FILE_NAME_INFORMATION v20; // r8
  PFLT_FILE_NAME_INFORMATION v21; // rbx
  _QWORD *v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rdx
  __int64 *v26; // rcx
  __int64 v27; // rax
  struct _FLT_INSTANCE *v28; // rbx
  struct _FLT_INSTANCE *v29; // rcx
  NTSTATUS v30; // edi
  PFLT_CONTEXT v31; // rdi
  PFLT_CONTEXT v32; // rbx
  PFLT_CONTEXT v33; // rdi
  _DWORD *Pool2; // rax
  PVOID *v35; // r14
  _BYTE *v36; // r8
  PFLT_CONTEXT v37; // rdx
  __int64 ProcessFromAttributionInfo; // rax
  int v39; // eax
  __int64 v40; // rcx
  unsigned __int8 v41; // cl
  bool v42; // al
  char v43; // al
  __int64 v44; // r9
  __int64 v45; // r10
  int v46; // edx
  __int128 v47; // xmm6
  NTSTATUS EcpListFromCallbackData; // edi
  NTSTATUS ExtraCreateParameter; // edi
  int v50; // ecx
  __int64 v51; // r8
  PVOID v52; // rcx
  PDEVICE_OBJECT v54; // rcx
  __int64 v55; // rdx
  __int64 v56; // rcx
  __int64 v57; // rax
  __int64 v58; // r8
  __int64 v59; // rdx
  __int64 v60; // r9
  int v61; // r10d
  PDEVICE_OBJECT v62; // rcx
  __int64 v63; // rdx
  __int64 v64; // rax
  __int64 v65; // r8
  __int64 v66; // r9
  __int64 StreamSize; // rax
  __int64 v68; // r10
  __int64 v69; // r8
  __int64 v70; // rax
  __int64 v71; // r8
  __int64 v72; // r10
  PFLT_CONTEXT Context; // [rsp+68h] [rbp-A0h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+70h] [rbp-98h] BYREF
  PFLT_CONTEXT NewContext; // [rsp+78h] [rbp-90h] BYREF
  struct _FLT_FILE_NAME_INFORMATION *LengthReturned; // [rsp+80h] [rbp-88h] BYREF
  PVOID P; // [rsp+88h] [rbp-80h]
  ULONG EcpContextSize; // [rsp+90h] [rbp-78h] BYREF
  PFLT_INSTANCE Instance; // [rsp+98h] [rbp-70h]
  PVOID EcpContext; // [rsp+A0h] [rbp-68h] BYREF
  PECP_LIST EcpList; // [rsp+A8h] [rbp-60h] BYREF
  __int128 FileInformation; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v83; // [rsp+C0h] [rbp-48h]
  _OWORD v84[2]; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v85; // [rsp+E8h] [rbp-20h]
  __int64 v86; // [rsp+F8h] [rbp-10h]

  RequestorProcess = 0;
  v9 = *(struct _FLT_INSTANCE **)(a1 + 32);
  Buffer = 0;
  v11 = 0;
  Instance = v9;
  Context = 0;
  NewContext = 0;
  P = 0;
  EcpList = 0;
  EcpContext = 0;
  EcpContextSize = 0;
  if ( a4 )
    RequestorProcess = FltGetRequestorProcess((PFLT_CALLBACK_DATA)a4);
  if ( (unsigned __int8)HsmOsIsPassThroughModeEnabled(RequestorProcess) )
    goto LABEL_113;
  if ( !a3 )
  {
    FileNameInformation = 0;
    Buffer = FltQueryInformationFile(v9, a2, &FileNameInformation, 8u, FileAttributeTagInformation, 0);
    HsmDbgBreakOnStatus(Buffer);
    if ( Buffer < 0 )
    {
      if ( Buffer == -1073741811 )
        MicrosoftTelemetryAssertTriggeredArgsKM(v56, 0);
      v54 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_113;
      }
      v55 = 30;
LABEL_204:
      WPP_SF_qqqd(v54->AttachedDevice, v55, WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids, v9, a2, a4, Buffer);
      goto LABEL_113;
    }
    if ( ((unsigned __int16)FileNameInformation & 0x400) != 0 )
      a3 = HIDWORD(FileNameInformation);
  }
  if ( (a3 & 0xFFFF0FFF) != dword_140029670 || a4 && ((v12 = *(_QWORD *)(a4 + 32), v12 == 3) || !v12) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qqqd(
        WPP_GLOBAL_Control->AttachedDevice,
        31,
        WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids,
        v9,
        a2,
        a4,
        Buffer);
    }
    FltGetStreamContext(v9, a2, &Context);
    if ( Context )
    {
      FltAcquirePushLockExclusiveEx(*((_QWORD *)Context + 2) + 24LL, 0);
      *((_DWORD *)Context + 7) &= ~1u;
      FltReleasePushLockEx(*((_QWORD *)Context + 2) + 24LL, 0);
      HsmpCldNullifyStreamContext(Context);
    }
    FltGetStreamHandleContext(v9, a2, &NewContext);
    if ( NewContext )
      FltDeleteContext(NewContext);
    if ( a4 && *(_QWORD *)(a4 + 32) == 3 )
    {
      HsmpToggleFileSparseAttribute(a1, a2, 0);
      HsmpToggleFileAttributes(a1, a2, *(_WORD *)(*(_QWORD *)(a4 + 16) + 40LL) & 0x1000, 4198400);
    }
    Buffer = 0;
    goto LABEL_113;
  }
  if ( IoGetTransactionParameterBlock(a2) )
  {
    Buffer = -1072103334;
    HsmDbgBreakOnStatus(-1072103334);
    v54 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_113;
    }
    v55 = 32;
    goto LABEL_204;
  }
  if ( !a4 )
    goto LABEL_18;
  v13 = *(_QWORD *)(a4 + 16);
  v83 = 0;
  FileNameInformation = 0;
  LODWORD(LengthReturned) = 0;
  FileInformation = 0;
  Buffer = FltQueryInformationFile(
             *(PFLT_INSTANCE *)(v13 + 16),
             *(PFILE_OBJECT *)(v13 + 8),
             &FileInformation,
             0x18u,
             FileStandardInformation,
             (PULONG)&LengthReturned);
  HsmDbgBreakOnStatus(Buffer);
  if ( Buffer >= 0 && (_DWORD)LengthReturned == 24 )
  {
    v14 = HIWORD(v83) != 0;
  }
  else
  {
    v47 = *(_OWORD *)(a4 + 24);
    v14 = 0;
    Buffer = FltGetFileNameInformation((PFLT_CALLBACK_DATA)a4, 0x102u, &FileNameInformation);
    HsmDbgBreakOnStatus(Buffer);
    *(_OWORD *)(a4 + 24) = v47;
    if ( Buffer >= 0 )
    {
      Buffer = FltParseFileNameInformation(FileNameInformation);
      HsmDbgBreakOnStatus(Buffer);
      if ( Buffer >= 0 )
        v14 = FileNameInformation->Stream.Length != 0;
    }
  }
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  HsmDbgBreakOnStatus(Buffer);
  if ( Buffer < 0 )
  {
    v54 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_113;
    }
    v55 = 33;
    goto LABEL_204;
  }
  if ( v14 )
  {
LABEL_113:
    p_Size = Context;
    goto LABEL_114;
  }
LABEL_18:
  StreamContext = FltGetStreamContext(v9, a2, &Context);
  HsmDbgBreakOnStatus(StreamContext);
  Buffer = 0;
  if ( StreamContext != -1073741275 )
    Buffer = StreamContext;
  if ( Buffer < 0 )
  {
    v54 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_113;
    }
    v55 = 34;
    goto LABEL_204;
  }
  p_Size = Context;
  if ( !Context )
  {
    v17 = Instance;
    FileNameInformation = 0;
    Buffer = HsmpRpReadBuffer(Instance, a2);
    HsmDbgBreakOnStatus(Buffer);
    if ( Buffer == -1073741195 || Buffer == -1073741156 || Buffer == -2147483643 || Buffer == -1073741808 )
    {
      Buffer = 0;
    }
    else
    {
      if ( Buffer >= 0 )
      {
        v11 = P;
        if ( (*(_DWORD *)P & 0xFFFF0FFF) != dword_140029670 )
          goto LABEL_111;
        LOWORD(LengthReturned) = *((_WORD *)P + 2);
        SyncRootFileIdByFileObject = HsmiCldGetSyncRootFileIdByFileObject(a1, a2, &FileNameInformation, 0, 0);
        HsmDbgBreakOnStatus(SyncRootFileIdByFileObject);
        if ( SyncRootFileIdByFileObject >= 0
          || WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
        {
          HsmDbgBreakOnStatus(SyncRootFileIdByFileObject);
          if ( SyncRootFileIdByFileObject >= 0 )
            goto LABEL_30;
        }
        else
        {
          WPP_SF_qqqd(
            WPP_GLOBAL_Control->AttachedDevice,
            55,
            WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids,
            a1,
            0,
            a2,
            SyncRootFileIdByFileObject);
          HsmDbgBreakOnStatus(SyncRootFileIdByFileObject);
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        {
          WPP_SF_qqqd(
            WPP_GLOBAL_Control->AttachedDevice,
            36,
            WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids,
            a1,
            v17,
            a2,
            SyncRootFileIdByFileObject);
        }
LABEL_30:
        Buffer = HsmpCtxCreateStreamContext(
                   a1,
                   (_DWORD)a2,
                   (_DWORD)FileNameInformation,
                   (int)v11 + 8,
                   (unsigned __int16)LengthReturned,
                   (__int64)&Context);
        HsmDbgBreakOnStatus(Buffer);
        if ( Buffer < 0 )
        {
          v62 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            goto LABEL_111;
          }
          v63 = 37;
        }
        else
        {
          *((_DWORD *)Context + 6) = *v11;
          FltAcquirePushLockExclusiveEx(*((_QWORD *)Context + 2) + 24LL, 0);
          LengthReturned = (struct _FLT_FILE_NAME_INFORMATION *)Context;
          FileNameInformation = 0;
          P = (PVOID)*((_QWORD *)Context + 2);
          v19 = FltSetStreamContext(
                  *(PFLT_INSTANCE *)(a1 + 32),
                  a2,
                  FLT_SET_CONTEXT_KEEP_IF_EXISTS,
                  Context,
                  (PFLT_CONTEXT *)&FileNameInformation);
          HsmDbgBreakOnStatus(v19);
          if ( v19 == -1071906814 )
          {
            v21 = FileNameInformation;
            HsmDbgBreakOnStatus(0);
            FltReleasePushLockEx(*((_QWORD *)Context + 2) + 24LL, 0);
            goto LABEL_39;
          }
          if ( v19 >= 0 )
          {
            v20 = FileNameInformation;
            if ( FileNameInformation )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                StreamSize = HsmpGetStreamSize(FileNameInformation);
                WPP_SF_qqLii(
                  *(_QWORD *)(v68 + 24),
                  83,
                  v69,
                  a1,
                  v69,
                  *(_DWORD *)(v69 + 28),
                  StreamSize,
                  *((_QWORD *)P + 4));
                v20 = FileNameInformation;
              }
              FltReleaseContext(v20);
            }
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            {
              v64 = HsmpGetStreamSize(LengthReturned);
              WPP_SF_qqLii(*(_QWORD *)(v65 + 24), 84, v65, a1, v66, *(_DWORD *)(v66 + 28), v64, *((_QWORD *)P + 4));
            }
            HsmDbgBreakOnStatus(v19);
            FltReleasePushLockEx(*((_QWORD *)Context + 2) + 24LL, 0);
            v21 = LengthReturned;
LABEL_39:
            p_Size = Context;
            if ( Context != v21 )
            {
              FltReleaseContext(Context);
              p_Size = &v21->Size;
              Context = v21;
            }
            if ( (!p_Size || (p_Size[7] & 4) == 0) && (p_Size[7] & 2) == 0 )
            {
              memset(v84, 0, sizeof(v84));
              v86 = 0;
              v85 = 0;
              Buffer = FltQueryInformationFile(v17, a2, v84, 0x38u, FileNetworkOpenInformation, 0);
              HsmDbgBreakOnStatus(Buffer);
              if ( Buffer < 0 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  WPP_SF_qqqd(
                    WPP_GLOBAL_Control->AttachedDevice,
                    39,
                    WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids,
                    a1,
                    v17,
                    Context,
                    Buffer);
                }
                goto LABEL_111;
              }
              FltAcquirePushLockExclusiveEx(*((_QWORD *)Context + 2) + 24LL, 0);
              v22 = Context;
              v23 = *((_QWORD *)Context + 20);
              if ( v23 )
              {
                FltAcquirePushLockExclusiveEx(v23 + 40, 0);
                v22 = Context;
              }
              v24 = *((_QWORD *)&v84[0] + 1);
              v25 = v22[2];
              if ( *(_QWORD *)(v25 + 40) > *((__int64 *)&v84[0] + 1) )
                v24 = *(_QWORD *)(v25 + 40);
              *(_QWORD *)(v25 + 40) = v24;
              v26 = (__int64 *)*((_QWORD *)Context + 20);
              v27 = *v26;
              if ( *v26 >= *((__int64 *)&v85 + 1) )
                v27 = *((_QWORD *)&v85 + 1);
              *v26 = v27;
              HsmpReleaseBitmapLock(Context);
              FltReleasePushLockEx(*((_QWORD *)Context + 2) + 24LL, 0);
              p_Size = Context;
            }
LABEL_52:
            Buffer = HsmpCtxCreateStreamHandleContext(a1, a2, a4, p_Size, &NewContext);
            HsmDbgBreakOnStatus(Buffer);
            if ( Buffer < 0 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              {
                WPP_SF_qqqd(
                  WPP_GLOBAL_Control->AttachedDevice,
                  40,
                  WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids,
                  a1,
                  v17,
                  Context,
                  Buffer);
              }
              goto LABEL_111;
            }
            v28 = (struct _FLT_INSTANCE *)NewContext;
            v29 = *(struct _FLT_INSTANCE **)(a1 + 32);
            FileNameInformation = 0;
            v30 = FltSetStreamHandleContext(
                    v29,
                    a2,
                    FLT_SET_CONTEXT_KEEP_IF_EXISTS,
                    NewContext,
                    (PFLT_CONTEXT *)&FileNameInformation);
            HsmDbgBreakOnStatus(v30);
            if ( v30 == -1071906814 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_qqq(
                  WPP_GLOBAL_Control->AttachedDevice,
                  91,
                  WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids,
                  a1,
                  v28,
                  FileNameInformation);
              }
              v31 = FileNameInformation;
              HsmDbgBreakOnStatus(0);
              Buffer = 0;
            }
            else
            {
              if ( v30 < 0 )
              {
                Instance = 0;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  WPP_SF_qqd(
                    WPP_GLOBAL_Control->AttachedDevice,
                    92,
                    WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids,
                    a1,
                    v28,
                    v30);
                }
                v30 = -1073741757;
                HsmDbgBreakOnStatus(-1073741757);
              }
              else
              {
                Instance = v28;
              }
              if ( FileNameInformation )
                FltReleaseContext(FileNameInformation);
              Buffer = v30;
              HsmDbgBreakOnStatus(v30);
              if ( v30 < 0 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  v70 = HsmpGetStreamSize(Context);
                  WPP_SF_qqiqLiq(
                    *(_QWORD *)(v72 + 24),
                    *(_QWORD *)(v71 + 16),
                    v71,
                    a1,
                    a2,
                    *(_QWORD *)(*(_QWORD *)(v71 + 16) + 32LL),
                    v71,
                    *(_DWORD *)(v71 + 28),
                    v70,
                    NewContext);
                }
                goto LABEL_111;
              }
              v31 = Instance;
            }
            if ( NewContext != v31 )
            {
              FltReleaseContext(NewContext);
              NewContext = v31;
            }
            if ( a4 )
            {
              HsmpDbgBreakOnOpen(NewContext, a2, a4);
              v32 = Context;
              v33 = NewContext;
              Pool2 = (_DWORD *)ExAllocatePool2(256, 24, 1766028104);
              v35 = (PVOID *)Pool2;
              if ( !Pool2 )
              {
                Buffer = -1073741670;
                HsmDbgBreakOnStatus(-1073741670);
                HsmDbgBreakOnStatus(-1073741670);
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  WPP_SF_qqiqd(
                    WPP_GLOBAL_Control->AttachedDevice,
                    42,
                    WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids,
                    a1,
                    Context,
                    a2,
                    *(_QWORD *)(*((_QWORD *)Context + 2) + 32LL),
                    -1073741670);
                }
                goto LABEL_111;
              }
              *Pool2 |= 2u;
              HsmpFillOutAttributionInformation(v33, v32, a4, Pool2);
              HsmDbgBreakOnStatus(0);
              if ( (unsigned __int8)HsmOsIsSyncProviderProcessFromAttributionInfo(v35)
                || (v36 = NewContext, Buffer = 0, (*((_DWORD *)NewContext + 10) & 0x40) == 0) )
              {
                Buffer = HsmpPrepareForMgmtOperation(a1, a2, 4294967294LL);
                HsmDbgBreakOnStatus(Buffer);
                if ( Buffer < 0 )
                {
                  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
                    || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                  {
                    goto LABEL_105;
                  }
                  v43 = HsmpGetStreamSize(Context);
                  v46 = 43;
                  goto LABEL_81;
                }
                *((_DWORD *)NewContext + 10) |= 8u;
                v36 = NewContext;
              }
              v37 = Context;
              if ( (*((_DWORD *)Context + 7) & 2) == 0
                && (v36[40] & 0x20) != 0
                && (*((_DWORD *)Context + 7) & 0x100) == 0 )
              {
                LOBYTE(LengthReturned) = 0;
                HsmpCldIsHydrationDisallowed(v35, Context, v36, &LengthReturned);
                if ( (_BYTE)LengthReturned )
                {
                  Buffer = -1073688808;
                  HsmDbgBreakOnStatus(-1073688808);
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                  {
                    v57 = HsmpGetStreamSize(Context);
                    WPP_SF_qqiqLiqD(
                      *(_QWORD *)(v58 + 24),
                      v59,
                      v58,
                      a1,
                      a2,
                      *(_QWORD *)(*(_QWORD *)(v59 + 16) + 32LL),
                      v59,
                      *(_DWORD *)(v59 + 28),
                      v57,
                      v60,
                      v61);
                  }
                  goto LABEL_105;
                }
              }
              ProcessFromAttributionInfo = HsmOsGetProcessFromAttributionInfo(v35, v37, v36);
              HsmOsSetPebCloudFileOpened(ProcessFromAttributionInfo);
              if ( (*((_DWORD *)Context + 7) & 2) != 0 || (*((_DWORD *)NewContext + 10) & 0x20) == 0 )
                goto LABEL_97;
              LOBYTE(LengthReturned) = 0;
              v39 = HsmOsCheckAppCompatPolicy(v35, 2, &LengthReturned);
              v40 = (unsigned __int8)LengthReturned;
              if ( v39 < 0 )
                v40 = 1;
              v42 = (unsigned __int8)HsmpDbgFullyHydrateOnUserModeOpen(v40) && *(_BYTE *)(a4 + 80) == 1;
              if ( !(v41 | v42)
                || (HsmpRecallInitiateHydration((_DWORD)NewContext, (_DWORD)Context, (_DWORD)a2, 65544, a4, 0, -1),
                    Buffer = *(_DWORD *)(a4 + 24),
                    HsmDbgBreakOnStatus(Buffer),
                    Buffer >= 0) )
              {
LABEL_97:
                EcpListFromCallbackData = FltGetEcpListFromCallbackData(Filter, (PFLT_CALLBACK_DATA)a4, &EcpList);
                HsmDbgBreakOnStatus(EcpListFromCallbackData);
                if ( EcpListFromCallbackData >= 0 )
                {
                  if ( EcpList )
                  {
                    ExtraCreateParameter = FltFindExtraCreateParameter(
                                             Filter,
                                             EcpList,
                                             &GUID_ECP_CREATE_REDIRECTION,
                                             &EcpContext,
                                             &EcpContextSize);
                    HsmDbgBreakOnStatus(ExtraCreateParameter);
                    if ( ExtraCreateParameter >= 0 && EcpContextSize >= 4 && (*((_DWORD *)Context + 7) & 0x100) == 0 )
                    {
                      *((_WORD *)EcpContext + 1) |= 0x10u;
                      FltAcknowledgeEcp(Filter, EcpContext);
                    }
                  }
                }
                if ( (*(_DWORD *)(*(_QWORD *)(a4 + 16) + 32LL) & 0x1000) != 0 )
                  *((_DWORD *)NewContext + 10) |= 0x1000u;
                v50 = *((_DWORD *)Context + 7);
                if ( (v50 & 8) != 0 )
                  v51 = 1;
                else
                  v51 = ((unsigned __int8)v50 >> 3) & 2;
                HsmpCldNotifyPostOperation(1, a4, v51, 0, 0);
                goto LABEL_105;
              }
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
                || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
              {
LABEL_105:
                v52 = v35[2];
                if ( v52 )
                  ObfDereferenceObject(v52);
                if ( (*(_DWORD *)v35 & 1) != 0 )
                  ExFreePoolWithTag(v35[1], 0x69417348u);
                if ( (*(_DWORD *)v35 & 2) != 0 )
                  ExFreePoolWithTag(v35, 0x69437348u);
                goto LABEL_111;
              }
              v43 = HsmpGetStreamSize(Context);
              v46 = 45;
LABEL_81:
              WPP_SF_qqiqLiqd(
                *(_QWORD *)(v45 + 24),
                v46,
                (unsigned int)WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids,
                a1,
                (char)a2,
                *(_QWORD *)(*(_QWORD *)(v44 + 16) + 32LL),
                v44,
                *(_DWORD *)(v44 + 28),
                v43,
                NewContext,
                Buffer);
              goto LABEL_105;
            }
LABEL_111:
            if ( v11 )
              ExFreePoolWithTag(v11, 0x70527348u);
            goto LABEL_113;
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_qqqd(
              WPP_GLOBAL_Control->AttachedDevice,
              82,
              WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids,
              a1,
              LengthReturned,
              *((_QWORD *)P + 4),
              v19);
          }
          Buffer = -1073741757;
          HsmDbgBreakOnStatus(-1073741757);
          HsmDbgBreakOnStatus(-1073741757);
          FltReleasePushLockEx(*((_QWORD *)Context + 2) + 24LL, 0);
          v62 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            goto LABEL_111;
          }
          v63 = 38;
        }
        WPP_SF_qqqd(v62->AttachedDevice, v63, WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids, a1, v17, a2, Buffer);
        goto LABEL_111;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qqqd(
          WPP_GLOBAL_Control->AttachedDevice,
          35,
          WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids,
          v17,
          a2,
          a4,
          Buffer);
      }
    }
    v11 = P;
    goto LABEL_111;
  }
  if ( (*((_DWORD *)Context + 7) & 1) != 0 )
  {
    v17 = Instance;
    goto LABEL_52;
  }
LABEL_114:
  if ( p_Size )
  {
    if ( (p_Size[7] & 4) != 0 )
    {
      HsmpReportCorruption(a1, *(_QWORD *)(*((_QWORD *)p_Size + 2) + 32LL), 3221278466LL);
      p_Size = Context;
    }
    FltReleaseContext(p_Size);
  }
  if ( NewContext )
    FltReleaseContext(NewContext);
  return (unsigned int)Buffer;
}

```

## disassembly

```asm
0x14005ac10  mov     r11, rsp
0x14005ac13  push    rbp
0x14005ac14  push    rbx
0x14005ac15  lea     rbp, [r11-48h]
0x14005ac19  sub     rsp, 138h
0x14005ac20  mov     rax, cs:__security_cookie
0x14005ac27  xor     rax, rsp
0x14005ac2a  mov     qword ptr [rbp+40h+var_48], rax
0x14005ac2e  xor     eax, eax
0x14005ac30  mov     [r11+18h], rsi
0x14005ac34  mov     [r11-18h], rdi
0x14005ac38  mov     rsi, r9
0x14005ac3b  mov     [r11-20h], r12
0x14005ac3f  mov     edi, r8d
0x14005ac42  mov     [r11-28h], r13
0x14005ac46  mov     r12, rdx
0x14005ac49  mov     [r11-30h], r14
0x14005ac4d  mov     r13, rcx
0x14005ac50  mov     r14, [rcx+20h]
0x14005ac54  mov     ebx, eax
0x14005ac56  mov     [r11-38h], r15
0x14005ac5a  mov     r15d, eax
0x14005ac5d  mov     [rbp+40h+Instance], r14
0x14005ac61  mov     [rsp+140h+Context], rax
0x14005ac66  mov     [rsp+140h+NewContext], rax
0x14005ac6b  mov     [rbp+40h+P], rax
0x14005ac6f  mov     [rbp+40h+EcpList], rax
0x14005ac73  mov     [rbp+40h+EcpContext], rax
0x14005ac77  mov     [rbp+40h+EcpContextSize], eax
0x14005ac7a  test    r9, r9
0x14005ac7d  jz      short loc_14005AC8E
0x14005ac7f  mov     rcx, r9; CallbackData
0x14005ac82  call    cs:__imp_FltGetRequestorProcess
0x14005ac89  nop     dword ptr [rax+rax+00h]
0x14005ac8e  mov     rcx, rax
0x14005ac91  call    HsmOsIsPassThroughModeEnabled
0x14005ac96  test    al, al
0x14005ac98  jnz     loc_14005B5F0
0x14005ac9e  test    edi, edi
0x14005aca0  jz      loc_14005B84B
0x14005aca6  and     edi, 0FFFF0FFFh
0x14005acac  cmp     edi, cs:dword_140029670
0x14005acb2  jnz     loc_14005B372
0x14005acb8  test    rsi, rsi
0x14005acbb  jz      short loc_14005ACD4
0x14005acbd  mov     rax, [rsi+20h]
0x14005acc1  cmp     rax, 3
0x14005acc5  jz      loc_14005B372
0x14005accb  test    rax, rax
0x14005acce  jz      loc_14005B372
0x14005acd4  mov     rcx, r12; FileObject
0x14005acd7  call    cs:__imp_IoGetTransactionParameterBlock
0x14005acde  nop     dword ptr [rax+rax+00h]
0x14005ace3  test    rax, rax
0x14005ace6  jnz     loc_14005B749
0x14005acec  test    rsi, rsi
0x14005acef  jz      loc_14005AD94
0x14005acf5  mov     rcx, [rsi+10h]
0x14005acf9  lea     r8, [rbp+40h+FileInformation]; FileInformation
0x14005acfd  mov     [rbp+40h+var_88], rax
0x14005ad01  xorps   xmm0, xmm0
0x14005ad04  mov     [rsp+140h+FileNameInformation], rax
0x14005ad09  mov     r9d, 18h; Length
0x14005ad0f  mov     dword ptr [rsp+140h+var_C8], eax
0x14005ad13  lea     rax, [rsp+140h+var_C8]
0x14005ad18  movups  [rbp+40h+FileInformation], xmm0
0x14005ad1c  mov     rdx, [rcx+8]; FileObject
0x14005ad20  mov     rcx, [rcx+10h]; Instance
0x14005ad24  mov     [rsp+140h+LengthReturned], rax; LengthReturned
0x14005ad29  mov     [rsp+140h+FileInformationClass], 5; FileInformationClass
0x14005ad31  call    cs:__imp_FltQueryInformationFile
0x14005ad38  nop     dword ptr [rax+rax+00h]
0x14005ad3d  mov     ecx, eax
0x14005ad3f  mov     ebx, eax
0x14005ad41  call    HsmDbgBreakOnStatus
0x14005ad46  test    ebx, ebx
0x14005ad48  js      loc_14005B473
0x14005ad4e  cmp     dword ptr [rsp+140h+var_C8], 18h
0x14005ad53  jnz     loc_14005B473
0x14005ad59  cmp     byte ptr [rbp+40h+var_88+7], r15b
0x14005ad5d  jz      loc_14005B461
0x14005ad63  mov     dil, 1
0x14005ad66  mov     rcx, [rsp+140h+FileNameInformation]; FileNameInformation
0x14005ad6b  test    rcx, rcx
0x14005ad6e  jz      short loc_14005AD7C
0x14005ad70  call    cs:__imp_FltReleaseFileNameInformation
0x14005ad77  nop     dword ptr [rax+rax+00h]
0x14005ad7c  mov     ecx, ebx
0x14005ad7e  call    HsmDbgBreakOnStatus
0x14005ad83  test    ebx, ebx
0x14005ad85  js      loc_14005BDC7
0x14005ad8b  test    dil, dil
0x14005ad8e  jnz     loc_14005B5F0
0x14005ad94  lea     r8, [rsp+140h+Context]; Context
0x14005ad99  mov     rdx, r12; FileObject
0x14005ad9c  mov     rcx, r14; Instance
0x14005ad9f  call    cs:__imp_FltGetStreamContext
0x14005ada6  nop     dword ptr [rax+rax+00h]
0x14005adab  mov     ecx, eax
0x14005adad  mov     edi, eax
0x14005adaf  call    HsmDbgBreakOnStatus
0x14005adb4  xor     ebx, ebx
0x14005adb6  cmp     edi, 0C0000225h
0x14005adbc  cmovnz  ebx, edi
0x14005adbf  test    ebx, ebx
0x14005adc1  js      loc_14005BDFA
0x14005adc7  mov     rcx, [rsp+140h+Context]
0x14005adcc  lea     r14, WPP_GLOBAL_Control
0x14005add3  test    rcx, rcx
0x14005add6  jnz     loc_14005BD0A
0x14005addc  mov     rdi, [rbp+40h+Instance]
0x14005ade0  lea     r8, [rbp+40h+P]
0x14005ade4  mov     rcx, rdi; Instance
0x14005ade7  mov     [rsp+140h+FileNameInformation], r15
0x14005adec  mov     rdx, r12; FileObject
0x14005adef  call    HsmpRpReadBuffer
0x14005adf4  mov     ecx, eax
0x14005adf6  mov     ebx, eax
0x14005adf8  call    HsmDbgBreakOnStatus
0x14005adfd  cmp     ebx, 0C0000275h
0x14005ae03  jz      loc_14005BEC2
0x14005ae09  cmp     ebx, 0C000029Ch
0x14005ae0f  jz      loc_14005BEC2
0x14005ae15  cmp     ebx, 80000005h
0x14005ae1b  jz      loc_14005BEC2
0x14005ae21  cmp     ebx, 0C0000010h
0x14005ae27  jz      loc_14005BEC2
0x14005ae2d  test    ebx, ebx
0x14005ae2f  js      loc_14005BE2B
0x14005ae35  mov     r15, [rbp+40h+P]
0x14005ae39  mov     eax, [r15]
0x14005ae3c  and     eax, 0FFFF0FFFh
0x14005ae41  cmp     eax, cs:dword_140029670
0x14005ae47  jnz     loc_14005B5D7
0x14005ae4d  movzx   eax, word ptr [r15+4]
0x14005ae52  lea     r8, [rsp+140h+FileNameInformation]
0x14005ae57  xor     r9d, r9d
0x14005ae5a  mov     word ptr [rsp+140h+var_C8], ax
0x14005ae5f  mov     rdx, r12
0x14005ae62  mov     qword ptr [rsp+140h+FileInformationClass], 0
0x14005ae6b  mov     rcx, r13
0x14005ae6e  call    HsmiCldGetSyncRootFileIdByFileObject
0x14005ae73  mov     ecx, eax
0x14005ae75  mov     ebx, eax
0x14005ae77  call    HsmDbgBreakOnStatus
0x14005ae7c  test    ebx, ebx
0x14005ae7e  js      loc_14005B7A4
0x14005ae84  mov     ecx, ebx
0x14005ae86  call    HsmDbgBreakOnStatus
0x14005ae8b  test    ebx, ebx
0x14005ae8d  js      loc_14005B7FB
0x14005ae93  movzx   eax, word ptr [rsp+140h+var_C8]
0x14005ae98  lea     rcx, [rsp+140h+Context]
0x14005ae9d  mov     r8, [rsp+140h+FileNameInformation]
0x14005aea2  lea     r9, [r15+8]
0x14005aea6  mov     [rsp+140h+LengthReturned], rcx
0x14005aeab  mov     rdx, r12
0x14005aeae  mov     rcx, r13
0x14005aeb1  mov     [rsp+140h+FileInformationClass], eax
0x14005aeb5  call    HsmpCtxCreateStreamContext
0x14005aeba  mov     ecx, eax
0x14005aebc  mov     ebx, eax
0x14005aebe  call    HsmDbgBreakOnStatus
0x14005aec3  test    ebx, ebx
0x14005aec5  js      loc_14005BA54
0x14005aecb  mov     rax, [rsp+140h+Context]
0x14005aed0  xor     edx, edx
0x14005aed2  mov     ecx, [r15]
0x14005aed5  mov     [rax+18h], ecx
0x14005aed8  mov     rax, [rsp+140h+Context]
0x14005aedd  mov     rcx, [rax+10h]
0x14005aee1  add     rcx, 18h
0x14005aee5  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14005aeec  nop     dword ptr [rax+rax+00h]
0x14005aef1  mov     rax, [rsp+140h+Context]
0x14005aef6  lea     rdx, [rsp+140h+FileNameInformation]
0x14005aefb  mov     qword ptr [rsp+140h+FileInformationClass], rdx; OldContext
0x14005af00  mov     r9, rax; NewContext
0x14005af03  mov     r8d, 1; Operation
0x14005af09  mov     [rsp+140h+var_C8], rax
0x14005af0e  mov     rdx, r12; FileObject
0x14005af11  mov     [rsp+140h+FileNameInformation], 0
0x14005af1a  mov     rcx, [rax+10h]
0x14005af1e  mov     [rbp+40h+P], rcx
0x14005af22  mov     rcx, [r13+20h]; Instance
0x14005af26  call    cs:__imp_FltSetStreamContext
0x14005af2d  nop     dword ptr [rax+rax+00h]
0x14005af32  mov     ecx, eax
0x14005af34  mov     ebx, eax
0x14005af36  call    HsmDbgBreakOnStatus
0x14005af3b  cmp     ebx, 0C01C0002h
0x14005af41  jz      loc_14005B9A6
0x14005af47  test    ebx, ebx
0x14005af49  js      loc_14005BA83
0x14005af4f  mov     r8, [rsp+140h+FileNameInformation]
0x14005af54  test    r8, r8
0x14005af57  jnz     loc_14005BB77
0x14005af5d  mov     r8, cs:WPP_GLOBAL_Control
0x14005af64  cmp     r8, r14
0x14005af67  jz      short loc_14005AF7C
0x14005af69  mov     eax, [r8+2Ch]
0x14005af6d  test    al, 1
0x14005af6f  jz      short loc_14005AF7C
0x14005af71  cmp     byte ptr [r8+29h], 5
0x14005af76  jnb     loc_14005BB35
0x14005af7c  mov     ecx, ebx
0x14005af7e  call    HsmDbgBreakOnStatus
0x14005af83  mov     rax, [rsp+140h+Context]
0x14005af88  xor     edx, edx
0x14005af8a  mov     rcx, [rax+10h]
0x14005af8e  add     rcx, 18h
0x14005af92  call    cs:__imp_FltReleasePushLockEx
0x14005af99  nop     dword ptr [rax+rax+00h]
0x14005af9e  mov     rbx, [rsp+140h+var_C8]
0x14005afa3  mov     rcx, [rsp+140h+Context]; Context
0x14005afa8  cmp     rcx, rbx
0x14005afab  jnz     loc_14005B78B
0x14005afb1  test    rcx, rcx
0x14005afb4  jz      short loc_14005AFC1
0x14005afb6  mov     eax, [rcx+1Ch]
0x14005afb9  test    al, 4
0x14005afbb  jnz     loc_14005B0BA
0x14005afc1  mov     eax, [rcx+1Ch]
0x14005afc4  test    al, 2
0x14005afc6  jnz     loc_14005B0BA
0x14005afcc  xorps   xmm0, xmm0
0x14005afcf  lea     r8, [rbp+40h+var_80]; FileInformation
0x14005afd3  xor     eax, eax
0x14005afd5  mov     r9d, 38h ; '8'; Length
0x14005afdb  mov     [rsp+140h+LengthReturned], rax; LengthReturned
0x14005afe0  mov     rdx, r12; FileObject
0x14005afe3  mov     rcx, rdi; Instance
0x14005afe6  mov     [rsp+140h+FileInformationClass], 22h ; '"'; FileInformationClass
0x14005afee  movups  [rbp+40h+var_80], xmm0
0x14005aff2  mov     [rbp+40h+var_50], rax
0x14005aff6  movups  [rbp+40h+var_70], xmm0
0x14005affa  movups  [rbp+40h+var_60], xmm0
0x14005affe  call    cs:__imp_FltQueryInformationFile
0x14005b005  nop     dword ptr [rax+rax+00h]
0x14005b00a  mov     ecx, eax
0x14005b00c  mov     ebx, eax
0x14005b00e  call    HsmDbgBreakOnStatus
0x14005b013  test    ebx, ebx
0x14005b015  js      loc_14005BA17
0x14005b01b  mov     rax, [rsp+140h+Context]
0x14005b020  xor     edx, edx
0x14005b022  mov     rcx, [rax+10h]
0x14005b026  add     rcx, 18h
0x14005b02a  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14005b031  nop     dword ptr [rax+rax+00h]
0x14005b036  mov     rdx, [rsp+140h+Context]
0x14005b03b  mov     rcx, [rdx+0A0h]
0x14005b042  test    rcx, rcx
0x14005b045  jz      short loc_14005B05E
0x14005b047  add     rcx, 28h ; '('
0x14005b04b  xor     edx, edx
0x14005b04d  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14005b054  nop     dword ptr [rax+rax+00h]
0x14005b059  mov     rdx, [rsp+140h+Context]
0x14005b05e  mov     rcx, qword ptr [rbp+40h+var_80+8]
0x14005b062  mov     rdx, [rdx+10h]
0x14005b066  mov     rax, [rdx+28h]
0x14005b06a  cmp     rax, rcx
0x14005b06d  cmovg   rcx, rax
0x14005b071  mov     [rdx+28h], rcx
0x14005b075  mov     rax, [rsp+140h+Context]
0x14005b07a  mov     rcx, [rax+0A0h]
0x14005b081  mov     rax, [rcx]
0x14005b084  cmp     rax, qword ptr [rbp+40h+var_60+8]
0x14005b088  cmovge  rax, qword ptr [rbp+40h+var_60+8]
0x14005b08d  mov     [rcx], rax
0x14005b090  mov     rcx, [rsp+140h+Context]
0x14005b095  call    HsmpReleaseBitmapLock
0x14005b09a  mov     rax, [rsp+140h+Context]
0x14005b09f  xor     edx, edx
0x14005b0a1  mov     rcx, [rax+10h]
0x14005b0a5  add     rcx, 18h
0x14005b0a9  call    cs:__imp_FltReleasePushLockEx
0x14005b0b0  nop     dword ptr [rax+rax+00h]
0x14005b0b5  mov     rcx, [rsp+140h+Context]
0x14005b0ba  lea     rax, [rsp+140h+NewContext]
0x14005b0bf  mov     r9, rcx
0x14005b0c2  mov     rcx, r13
0x14005b0c5  mov     qword ptr [rsp+140h+FileInformationClass], rax
0x14005b0ca  mov     r8, rsi
0x14005b0cd  mov     rdx, r12
0x14005b0d0  call    HsmpCtxCreateStreamHandleContext
0x14005b0d5  mov     ecx, eax
0x14005b0d7  mov     ebx, eax
0x14005b0d9  call    HsmDbgBreakOnStatus
0x14005b0de  test    ebx, ebx
0x14005b0e0  js      loc_14005B6DA
0x14005b0e6  mov     rbx, [rsp+140h+NewContext]
0x14005b0eb  lea     rax, [rsp+140h+FileNameInformation]
0x14005b0f0  mov     rcx, [r13+20h]; Instance
0x14005b0f4  mov     r9, rbx; NewContext
0x14005b0f7  mov     r8d, 1; Operation
0x14005b0fd  mov     [rsp+140h+FileNameInformation], 0
0x14005b106  mov     rdx, r12; FileObject
0x14005b109  mov     qword ptr [rsp+140h+FileInformationClass], rax; OldContext
  ... truncated ...
```
