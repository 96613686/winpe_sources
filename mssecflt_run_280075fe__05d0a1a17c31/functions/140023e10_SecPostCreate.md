# SecPostCreate

- ea: `0x140023e10`
- end: `0x140024669`
- name: `SecPostCreate`
- size: `2137`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `0`
- callee_count: `50`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x140005a90`
- `0x140005f34`
- `0x1400061dc`
- `0x140006400`
- `0x1400065d4`
- `0x140006684`
- `0x140006754`
- `0x140006b6c`
- `0x140006d3c`
- `0x140008984`
- `0x140009b80`
- `0x1400102ff`
- `0x14001030b`
- `0x140010317`
- `0x14001032f`
- `0x140010347`
- `0x1400103a7`
- `0x140010443`
- `0x140011610`
- `0x140011650`
- `0x1400233b4`
- `0x1400237dc`
- `0x140023e10`
- `0x14002466c`
- `0x1400247b8`
- `0x140024900`
- `0x140026ec4`
- `0x1400275b4`
- `0x1400280f8`
- `0x140028c8c`
- `0x140028db0`
- `0x140028df8`
- `0x140028f9c`
- `0x140029598`
- `0x140029810`
- `0x1400299b8`
- `0x14002ab0c`
- `0x140030900`
- `0x1400309d8`
- `0x140030ac4`
- `0x14003b670`
- `0x14003b708`
- `0x14003b7ec`
- `0x14003b840`
- `0x14003b894`
- `0x14003b8ac`
- `0x14003b96c`
- `0x14003ba4c`
- `0x14003d224`
- `0x14003fa28`

## import_xrefs

- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140024633`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140024633`
- `ntoskrnl!ExQueryDepthSList` at `0x14002402f`
- `ntoskrnl!ExQueryDepthSList` at `0x14002402f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023fe6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023fe6`

## pseudocode

```c
__int64 __fastcall SecPostCreate(PFLT_CALLBACK_DATA CallbackData, __int64 a2, __int64 a3, char a4)
{
  char v4; // bl
  __int64 v5; // r15
  char IsFileSensitive; // r12
  PFLT_IO_PARAMETER_BLOCK Iopb; // rcx
  ULONG v10; // r14d
  NTSTATUS Status; // eax
  int v12; // eax
  ULONG_PTR Information; // rax
  __int64 v14; // rax
  int v15; // ecx
  void *v16; // rcx
  char *v17; // rdi
  USHORT v18; // bx
  __int64 v19; // rcx
  int v20; // r13d
  NTSTATUS IsDirectory_0; // eax
  PEPROCESS RequestorProcess; // rax
  int v23; // r8d
  int v24; // r9d
  PEPROCESS v25; // rax
  int v26; // ebx
  int v27; // r14d
  PSLIST_ENTRY v28; // rcx
  PEPROCESS v29; // rax
  _OWORD *v30; // rcx
  char *v31; // rax
  char v33; // [rsp+50h] [rbp-49h]
  bool v34; // [rsp+51h] [rbp-48h]
  USHORT ShareAccess; // [rsp+52h] [rbp-47h]
  int v36; // [rsp+54h] [rbp-45h]
  ULONG Options; // [rsp+5Ch] [rbp-3Dh]
  PFLT_CONTEXT v38; // [rsp+60h] [rbp-39h] BYREF
  PFLT_CONTEXT Context; // [rsp+68h] [rbp-31h] BYREF
  PSLIST_ENTRY ListEntry; // [rsp+70h] [rbp-29h] BYREF
  __int64 v41; // [rsp+78h] [rbp-21h]
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+80h] [rbp-19h] BYREF
  PVOID P; // [rsp+88h] [rbp-11h] BYREF
  __int64 v44; // [rsp+90h] [rbp-9h]
  char v45; // [rsp+98h] [rbp-1h] BYREF
  unsigned __int8 IsDirectory; // [rsp+99h] [rbp+0h] BYREF
  char v47; // [rsp+9Ah] [rbp+1h] BYREF
  char v48; // [rsp+9Bh] [rbp+2h] BYREF
  char v49[4]; // [rsp+9Ch] [rbp+3h] BYREF
  __int64 v50[2]; // [rsp+A0h] [rbp+7h] BYREF

  v4 = 0;
  v38 = 0;
  v5 = a3;
  Context = 0;
  v48 = 0;
  FileNameInformation = 0;
  IsFileSensitive = 0;
  ListEntry = 0;
  IsDirectory = 0;
  P = 0;
  v49[0] = 0;
  v44 = 0;
  v41 = 0;
  v45 = 0;
  v33 = 0;
  v47 = 0;
  *(_OWORD *)v50 = 0;
  if ( !a3 )
    goto LABEL_34;
  if ( (a4 & 1) != 0 )
    goto LABEL_34;
  if ( !*(_QWORD *)(a2 + 32) )
    goto LABEL_34;
  Iopb = CallbackData->Iopb;
  Options = Iopb->Parameters.Create.Options;
  v10 = HIBYTE(Options);
  v36 = *(_DWORD *)(Iopb->Parameters.WMI.ProviderId + 16);
  ShareAccess = Iopb->Parameters.Create.ShareAccess;
  if ( CallbackData->IoStatus.Status == 260 )
    goto LABEL_34;
  LOBYTE(a3) = 1;
  if ( (unsigned __int8)SecShouldHandleAppCompat(CallbackData, a2, a3) )
    SecHandleAppCompat(CallbackData);
  Status = CallbackData->IoStatus.Status;
  if ( Status < 0 )
  {
    if ( Status == -1073741790 && _bittest64((const signed __int64 *)&xmmword_14001B740, 0x21u) )
    {
      v12 = SecPopulateFileShareContext(*(PFLT_FILTER *)(a2 + 8));
      SecSendUnauthorizedFileOpenAttemptEvent((__int64)CallbackData, v12, v44, v41);
    }
    goto LABEL_23;
  }
  Information = CallbackData->IoStatus.Information;
  if ( Information == 2 || Information == 3 || !Information && !v10 )
    v4 = 1;
  if ( !FltSupportsStreamHandleContexts_0(*(PFILE_OBJECT *)(a2 + 32)) )
    goto LABEL_23;
  if ( !FltSupportsStreamContexts_0(*(PFILE_OBJECT *)(a2 + 32)) )
    goto LABEL_23;
  v14 = *(_QWORD *)(a2 + 32);
  v15 = *(_DWORD *)(v14 + 80);
  if ( (v15 & 0x200) != 0 || !*(_QWORD *)(v14 + 32) && (v15 & 0x400000) == 0 )
    goto LABEL_23;
  if ( (*(_QWORD *)v5 & 2) != 0 )
  {
    SecPostCreateHandlePrefetch(CallbackData, a2);
    goto LABEL_23;
  }
  if ( (*(_QWORD *)v5 & 0x40) != 0 && (unsigned __int8)SecLmfShouldEnforcePolicy(CallbackData) )
  {
    CallbackData->IoStatus.Status = -1073741790;
    CallbackData->IoStatus.Information = 0;
    FltCancelFileOpen_0(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32));
    goto LABEL_23;
  }
  v19 = *(_QWORD *)(a2 + 32);
  if ( (*(_DWORD *)(v19 + 80) & 0x80u) != 0 )
  {
    if ( *(_WORD *)(v19 + 88) )
      SecSendPipeOpenEvent(CallbackData, a2);
    goto LABEL_23;
  }
  v20 = SecPopulateFileShareContext(*(PFLT_FILTER *)(a2 + 8));
  if ( (int)SecGetEffectiveTokenUser(CallbackData->Thread, 0, &P, v49, 0) >= 0 )
  {
    v34 = SecCheckUserSid(*(char **)P);
    IsDirectory_0 = FltIsDirectory_0(*(PFILE_OBJECT *)(a2 + 32), *(PFLT_INSTANCE *)(a2 + 24), &IsDirectory);
    if ( v44 )
      IsDirectory_0 = SecUnicodeToNullTerminatedUnicode(v44, v50);
    if ( IsDirectory_0 >= 0 && IsDirectory )
    {
      SecPostCreateHandleDirectory(CallbackData, a2);
      if ( v4 )
        SecSendFileCreateEvent(CallbackData, a2, v20, (__int64)v50, v41);
      goto LABEL_23;
    }
    if ( (*(_DWORD *)(*(_QWORD *)(a2 + 32) + 80LL) & 0x400000) != 0 )
    {
      SecPostCreateHandleDirectVolumeAccess(CallbackData, a2);
      goto LABEL_23;
    }
    if ( v10 != 1 )
    {
      if ( v4 )
      {
        SecSendFileCreateEvent(CallbackData, a2, v20, (__int64)v50, v41);
        if ( (unsigned __int8)SecIsFileSourceMonitoringEnabled() )
        {
          RequestorProcess = SecFltGetRequestorProcess(CallbackData);
          if ( (int)SecGetProcessContextByObject(RequestorProcess, &ListEntry) >= 0 )
          {
            if ( BYTE4(ListEntry[45].Next) )
              SecCreateFileCreatorEa(*(_QWORD *)(a2 + 32), &ListEntry[10].Next + 1);
          }
        }
      }
    }
    if ( FltGetStreamContext_0(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32), &v38) < 0
      && (int)SecCreateStreamContext(a2, &v38) < 0 )
    {
      goto LABEL_23;
    }
    _mm_lfence();
    if ( (*(_QWORD *)v5 & 0x10) == 0 )
    {
      v33 = 0;
      IsFileSensitive = 0;
      if ( v4 )
        goto LABEL_116;
      goto LABEL_97;
    }
    if ( v4 )
      goto LABEL_116;
    if ( (*(_QWORD *)v5 & 8) == 0 )
    {
LABEL_97:
      if ( (xmmword_14001B740 & 0x20) != 0
        && (v25 = SecFltGetRequestorProcess(CallbackData), (int)SecGetProcessContextByObject(v25, &ListEntry) >= 0) )
      {
        _mm_lfence();
        v26 = (HIDWORD(ListEntry[38].Next) >> 5) & 2;
        v27 = v26 | 1;
        if ( !(unsigned __int8)SecIsFileMonitored(
                                 (_DWORD)CallbackData,
                                 a2,
                                 Options,
                                 v36,
                                 (__int64)ListEntry,
                                 (__int64)&v48) )
          v27 = v26;
        if ( v27 )
        {
          _mm_lfence();
          SecSendFileOpenEvent(CallbackData, a2, v36, ShareAccess, (__int64)ListEntry, v27, v20, (__int64)v50, v48, v41);
        }
      }
      else
      {
        v27 = 0;
      }
      if ( !v33 || !v34 )
        goto LABEL_116;
      if ( v27 )
        goto LABEL_111;
      v28 = ListEntry;
      if ( !ListEntry )
      {
        v29 = SecFltGetRequestorProcess(CallbackData);
        if ( (int)SecGetProcessContextByObject(v29, &ListEntry) < 0 )
        {
LABEL_111:
          if ( !IsFileSensitive
            && ((*((_DWORD *)v38 + 4) & 0x20) != 0
             || (unsigned __int8)SecIsNetworkEnforcementEnabled() && (unsigned __int8)SecIsWriteRemoteFileEaEnabled()) )
          {
            SecCreateDlpCandidateEa(*(_QWORD *)(a2 + 32));
          }
          goto LABEL_116;
        }
        v28 = ListEntry;
      }
      if ( !(unsigned __int8)SecIsProcessOpenForReadFilter(&v28[10].Next + 1) )
        goto LABEL_111;
LABEL_116:
      if ( (int)SecCreateHandleContext(a2, &Context) >= 0 )
      {
        _mm_lfence();
        *((_DWORD *)Context + 50) |= 0x200u;
        if ( (Options & 0x1000) != 0 )
          SecSetObjectContextThread(Context, 4, 16, CallbackData->Thread);
        if ( (unsigned __int8)SecIsCreateUserProcessKernelEcpPresent(*(_QWORD *)(a2 + 8), CallbackData) )
          *((_DWORD *)Context + 50) |= 0x20u;
        *((_DWORD *)Context + 50) |= 0x100u;
        *((_QWORD *)Context + 5) = P;
        P = 0;
        *((_DWORD *)Context + 12) = v20;
        v30 = (_OWORD *)v41;
        if ( v41 )
        {
          v31 = (char *)Context;
          *(_OWORD *)((char *)Context + 56) = *(_OWORD *)v41;
          *(_OWORD *)(v31 + 72) = v30[1];
          *(_OWORD *)(v31 + 88) = v30[2];
          *(_OWORD *)(v31 + 104) = v30[3];
          *(_OWORD *)(v31 + 120) = v30[4];
          *(_OWORD *)(v31 + 136) = v30[5];
          *(_OWORD *)(v31 + 152) = v30[6];
          *(_OWORD *)(v31 + 168) = v30[7];
        }
        SecSwapUnicodeStrings(v50, (char *)Context + 184);
      }
      goto LABEL_23;
    }
    if ( (*((_DWORD *)v38 + 4) & 0x20) == 0 && (int)SecIsRemoteFile(*(_QWORD *)(a2 + 32), &v45) >= 0 )
    {
      if ( !v45 )
        goto LABEL_72;
      if ( (int)SecIsLoopbackByObj(a2, &v47) >= 0 && v47 )
        v45 = 0;
      if ( !v45 )
LABEL_72:
        _InterlockedOr((volatile signed __int32 *)v38 + 4, 0x20u);
    }
    if ( (*((_DWORD *)v38 + 4) & 8) != 0 )
    {
      IsFileSensitive = 1;
    }
    else
    {
      LOBYTE(v24) = 1;
      LOBYTE(v23) = 1;
      IsFileSensitive = SecIsFileSensitive((_DWORD)CallbackData, a2, v23, v24, *(_QWORD *)(a2 + 32), v45);
      if ( !IsFileSensitive )
      {
LABEL_81:
        if ( ((unsigned __int8)SecIsJitEnforcementEnabled()
           || (unsigned __int8)SecIsReadFileByExtensionEnabled() && (*((_DWORD *)v38 + 4) & 0x10) == 0)
          && (int)SecQueryParsedFileName(
                    CallbackData,
                    *(unsigned int *)(*((_QWORD *)v38 + 1) + 44LL),
                    &FileNameInformation) >= 0
          && (FileNameInformation->NamesParsed & 2) != 0 )
        {
          if ( (unsigned __int8)SecIsReadFileByExtensionEnabled()
            && (*((_DWORD *)v38 + 4) & 0x10) == 0
            && ((unsigned __int8)SecIsInReadFileExtensionsList(&FileNameInformation->Extension)
             || (unsigned __int8)SecIsInDlpReadFileExtensionsList(&FileNameInformation->Extension)) )
          {
            _InterlockedOr((volatile signed __int32 *)v38 + 4, 0x10u);
          }
          if ( (unsigned __int8)SecIsJitEnforcementEnabled()
            && (*((_DWORD *)v38 + 4) & 0x10) != 0
            && (unsigned __int8)SecIsInDlpReadFileExtensionsList(&FileNameInformation->Extension)
            && !(unsigned __int8)SecIsInSyncClassificationExcludedFileExtensionsList(&FileNameInformation->Extension) )
          {
            v33 = 1;
          }
        }
        goto LABEL_97;
      }
    }
    if ( (*((_DWORD *)v38 + 4) & 8) == 0 )
    {
      LOBYTE(v23) = 1;
      if ( (unsigned __int8)SecIsFileSensitive((_DWORD)CallbackData, a2, v23, 0, *(_QWORD *)(a2 + 32), v45) )
        _InterlockedOr((volatile signed __int32 *)v38 + 4, 8u);
    }
    if ( (*((_DWORD *)v38 + 4) & 0x10) == 0 )
      _InterlockedOr((volatile signed __int32 *)v38 + 4, 0x10u);
    goto LABEL_81;
  }
LABEL_23:
  if ( FileNameInformation )
    FltReleaseFileNameInformation_0(FileNameInformation);
  if ( Context )
    FltReleaseContext_0(Context);
  if ( v38 )
    FltReleaseContext_0(v38);
  if ( ListEntry )
    SecReleaseProcessContext(ListEntry);
  if ( P && v49[0] )
    ExFreePoolWithTag(P, 0);
LABEL_34:
  SecFreeNullTerminatedUnicode(v50);
  if ( v5 )
  {
    v16 = *(void **)(v5 + 8);
    if ( v16 )
      SecFreePool(v16, 0x74736353u);
    v17 = (char *)SecData + 1024;
    ++*((_DWORD *)SecData + 263);
    v18 = *((_WORD *)v17 + 8);
    if ( ExQueryDepthSList((PSLIST_HEADER)v17) < v18 )
    {
      _mm_lfence();
      ExpInterlockedPushEntrySList((PSLIST_HEADER)v17, (PSLIST_ENTRY)v5);
    }
    else
    {
      ++*((_DWORD *)v17 + 8);
      (*((void (__fastcall **)(__int64))v17 + 7))(v5);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140023e10  mov     [rsp-8+arg_18], rbx
0x140023e15  push    rbp
0x140023e16  push    rsi
0x140023e17  push    rdi
0x140023e18  push    r12
0x140023e1a  push    r13
0x140023e1c  push    r14
0x140023e1e  push    r15
0x140023e20  lea     rbp, [rsp-27h]
0x140023e25  sub     rsp, 0C0h
0x140023e2c  mov     rax, cs:__security_cookie
0x140023e33  xor     rax, rsp
0x140023e36  mov     [rbp+57h+var_40], rax
0x140023e3a  xor     ebx, ebx
0x140023e3c  xorps   xmm0, xmm0
0x140023e3f  mov     [rbp+57h+var_90], rbx
0x140023e43  mov     r15, r8
0x140023e46  mov     [rbp+57h+Context], rbx
0x140023e4a  mov     rdi, rdx
0x140023e4d  mov     [rbp+57h+var_55], bl
0x140023e50  mov     rsi, rcx
0x140023e53  mov     [rbp+57h+FileNameInformation], rbx
0x140023e57  mov     r12b, bl
0x140023e5a  mov     [rbp+57h+ListEntry], rbx
0x140023e5e  mov     [rbp+57h+var_98], ebx
0x140023e61  mov     [rbp+57h+IsDirectory], bl
0x140023e64  mov     [rbp+57h+P], rbx
0x140023e68  mov     [rbp+57h+var_54], bl
0x140023e6b  mov     [rbp+57h+var_60], rbx
0x140023e6f  mov     [rbp+57h+var_78], rbx
0x140023e73  mov     [rbp+57h+var_58], bl
0x140023e76  mov     [rbp+57h+var_A0], bl
0x140023e79  mov     [rbp+57h+var_56], bl
0x140023e7c  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x140023e80  test    r8, r8
0x140023e83  jz      loc_140023FF2
0x140023e89  test    r9b, 1
0x140023e8d  jnz     loc_140023FF2
0x140023e93  cmp     [rdx+20h], rbx
0x140023e97  jz      loc_140023FF2
0x140023e9d  mov     rcx, [rcx+10h]
0x140023ea1  mov     eax, [rcx+20h]
0x140023ea4  mov     r14d, eax
0x140023ea7  mov     [rbp+57h+var_94], eax
0x140023eaa  mov     rax, [rcx+18h]
0x140023eae  shr     r14d, 18h
0x140023eb2  cmp     dword ptr [rsi+18h], 104h
0x140023eb9  mov     eax, [rax+10h]
0x140023ebc  mov     [rbp+57h+var_9C], eax
0x140023ebf  movzx   eax, word ptr [rcx+2Ah]
0x140023ec3  mov     [rbp+57h+var_9E], ax
0x140023ec7  jz      loc_140023FF2
0x140023ecd  mov     r8b, 1
0x140023ed0  mov     rcx, rsi
0x140023ed3  call    SecShouldHandleAppCompat
0x140023ed8  test    al, al
0x140023eda  jz      short loc_140023EEB
0x140023edc  mov     r8, [r15+8]
0x140023ee0  mov     rdx, rdi
0x140023ee3  mov     rcx, rsi; CallbackData
0x140023ee6  call    SecHandleAppCompat
0x140023eeb  mov     eax, [rsi+18h]
0x140023eee  test    eax, eax
0x140023ef0  jns     short loc_140023F34
0x140023ef2  cmp     eax, 0C0000022h
0x140023ef7  jnz     loc_140023F9E
0x140023efd  bt      qword ptr cs:xmmword_14001B740, 21h ; '!'
0x140023f06  jnb     loc_140023F9E
0x140023f0c  mov     rcx, [rdi+8]; Filter
0x140023f10  lea     r9, [rbp+57h+var_78]
0x140023f14  lea     r8, [rbp+57h+var_60]
0x140023f18  mov     rdx, rsi
0x140023f1b  call    SecPopulateFileShareContext
0x140023f20  mov     r9, [rbp+57h+var_78]
0x140023f24  mov     edx, eax
0x140023f26  mov     r8, [rbp+57h+var_60]
0x140023f2a  mov     rcx, rsi
0x140023f2d  call    SecSendUnauthorizedFileOpenAttemptEvent
0x140023f32  jmp     short loc_140023F9E
0x140023f34  mov     rax, [rsi+20h]
0x140023f38  cmp     rax, 2
0x140023f3c  jz      short loc_140023F4E
0x140023f3e  cmp     rax, 3
0x140023f42  jz      short loc_140023F4E
0x140023f44  test    rax, rax
0x140023f47  jnz     short loc_140023F50
0x140023f49  test    r14d, r14d
0x140023f4c  jnz     short loc_140023F50
0x140023f4e  mov     bl, 1
0x140023f50  mov     rcx, [rdi+20h]; FileObject
0x140023f54  call    FltSupportsStreamHandleContexts_0
0x140023f59  xor     r13d, r13d
0x140023f5c  test    al, al
0x140023f5e  jz      short loc_140023F9C
0x140023f60  mov     rcx, [rdi+20h]; FileObject
0x140023f64  call    FltSupportsStreamContexts_0
0x140023f69  test    al, al
0x140023f6b  jz      short loc_140023F9C
0x140023f6d  mov     rax, [rdi+20h]
0x140023f71  mov     ecx, [rax+50h]
0x140023f74  bt      ecx, 9
0x140023f78  jb      short loc_140023F9C
0x140023f7a  cmp     [rax+20h], r13
0x140023f7e  jnz     short loc_140023F86
0x140023f80  bt      ecx, 16h
0x140023f84  jnb     short loc_140023F9C
0x140023f86  mov     rax, [r15]
0x140023f89  test    al, 2
0x140023f8b  jz      loc_140024059
0x140023f91  mov     rdx, rdi
0x140023f94  mov     rcx, rsi
0x140023f97  call    SecPostCreateHandlePrefetch
0x140023f9c  xor     ebx, ebx
0x140023f9e  mov     rcx, [rbp+57h+FileNameInformation]; FileNameInformation
0x140023fa2  test    rcx, rcx
0x140023fa5  jz      short loc_140023FAC
0x140023fa7  call    FltReleaseFileNameInformation_0
0x140023fac  mov     rcx, [rbp+57h+Context]; Context
0x140023fb0  test    rcx, rcx
0x140023fb3  jz      short loc_140023FBA
0x140023fb5  call    FltReleaseContext_0
0x140023fba  mov     rcx, [rbp+57h+var_90]; Context
0x140023fbe  test    rcx, rcx
0x140023fc1  jz      short loc_140023FC8
0x140023fc3  call    FltReleaseContext_0
0x140023fc8  mov     rcx, [rbp+57h+ListEntry]; ListEntry
0x140023fcc  test    rcx, rcx
0x140023fcf  jz      short loc_140023FD6
0x140023fd1  call    SecReleaseProcessContext
0x140023fd6  mov     rcx, [rbp+57h+P]; P
0x140023fda  test    rcx, rcx
0x140023fdd  jz      short loc_140023FF2
0x140023fdf  cmp     [rbp+57h+var_54], bl
0x140023fe2  jz      short loc_140023FF2
0x140023fe4  xor     edx, edx; Tag
0x140023fe6  call    cs:__imp_ExFreePoolWithTag
0x140023fed  nop     dword ptr [rax+rax+00h]
0x140023ff2  lea     rcx, [rbp+57h+var_50]
0x140023ff6  call    SecFreeNullTerminatedUnicode
0x140023ffb  test    r15, r15
0x140023ffe  jz      loc_14002463F
0x140024004  mov     rcx, [r15+8]; P
0x140024008  test    rcx, rcx
0x14002400b  jz      short loc_140024017
0x14002400d  mov     edx, 74736353h; Tag
0x140024012  call    SecFreePool
0x140024017  mov     rdi, cs:SecData
0x14002401e  add     rdi, 400h
0x140024025  mov     rcx, rdi; SListHead
0x140024028  inc     dword ptr [rdi+1Ch]
0x14002402b  movzx   ebx, word ptr [rdi+10h]
0x14002402f  call    cs:__imp_ExQueryDepthSList
0x140024036  nop     dword ptr [rax+rax+00h]
0x14002403b  cmp     ax, bx
0x14002403e  jb      loc_14002462A
0x140024044  inc     dword ptr [rdi+20h]
0x140024047  mov     rcx, r15
0x14002404a  mov     rax, [rdi+38h]
0x14002404e  call    cs:__guard_dispatch_icall_fptr
0x140024054  jmp     loc_14002463F
0x140024059  test    al, 40h
0x14002405b  jz      short loc_14002408E
0x14002405d  xor     r8d, r8d
0x140024060  mov     rdx, rdi
0x140024063  mov     rcx, rsi; CallbackData
0x140024066  call    SecLmfShouldEnforcePolicy
0x14002406b  test    al, al
0x14002406d  jz      short loc_14002408E
0x14002406f  mov     dword ptr [rsi+18h], 0C0000022h
0x140024076  xor     ebx, ebx
0x140024078  mov     [rsi+20h], rbx
0x14002407c  mov     rdx, [rdi+20h]; FileObject
0x140024080  mov     rcx, [rdi+18h]; Instance
0x140024084  call    FltCancelFileOpen_0
0x140024089  jmp     loc_140023F9E
0x14002408e  mov     rcx, [rdi+20h]
0x140024092  mov     eax, [rcx+50h]
0x140024095  test    al, al
0x140024097  jns     short loc_1400240B5
0x140024099  xor     ebx, ebx
0x14002409b  cmp     [rcx+58h], bx
0x14002409f  jz      loc_140023F9E
0x1400240a5  mov     rdx, rdi
0x1400240a8  mov     rcx, rsi; CallbackData
0x1400240ab  call    SecSendPipeOpenEvent
0x1400240b0  jmp     loc_140023F9E
0x1400240b5  mov     rcx, [rdi+8]; Filter
0x1400240b9  lea     r9, [rbp+57h+var_78]
0x1400240bd  lea     r8, [rbp+57h+var_60]
0x1400240c1  mov     rdx, rsi
0x1400240c4  call    SecPopulateFileShareContext
0x1400240c9  mov     rcx, [rsi+8]; Thread
0x1400240cd  lea     r9, [rbp+57h+var_54]
0x1400240d1  lea     r8, [rbp+57h+P]
0x1400240d5  mov     [rsp+0F0h+var_D0], 0; __int64
0x1400240de  xor     edx, edx
0x1400240e0  mov     r13d, eax
0x1400240e3  call    SecGetEffectiveTokenUser
0x1400240e8  test    eax, eax
0x1400240ea  js      loc_140023F9C
0x1400240f0  mov     rcx, [rbp+57h+P]
0x1400240f4  mov     rcx, [rcx]; Sid
0x1400240f7  call    SecCheckUserSid
0x1400240fc  mov     rdx, [rdi+18h]; Instance
0x140024100  lea     r8, [rbp+57h+IsDirectory]; IsDirectory
0x140024104  mov     rcx, [rdi+20h]; FileObject
0x140024108  mov     [rbp+57h+var_9F], al
0x14002410b  call    FltIsDirectory_0
0x140024110  mov     rcx, [rbp+57h+var_60]
0x140024114  test    rcx, rcx
0x140024117  jz      short loc_140024122
0x140024119  lea     rdx, [rbp+57h+var_50]
0x14002411d  call    SecUnicodeToNullTerminatedUnicode
0x140024122  test    eax, eax
0x140024124  js      short loc_14002415F
0x140024126  cmp     [rbp+57h+IsDirectory], r12b
0x14002412a  jz      short loc_14002415F
0x14002412c  mov     rdx, rdi
0x14002412f  mov     rcx, rsi; CallbackData
0x140024132  call    SecPostCreateHandleDirectory
0x140024137  test    bl, bl
0x140024139  jz      loc_140023F9C
0x14002413f  mov     rax, [rbp+57h+var_78]
0x140024143  lea     r9, [rbp+57h+var_50]
0x140024147  mov     r8d, r13d
0x14002414a  mov     [rsp+0F0h+var_D0], rax; __int64
0x14002414f  mov     rdx, rdi
0x140024152  mov     rcx, rsi; CallbackData
0x140024155  call    SecSendFileCreateEvent
0x14002415a  jmp     loc_140023F9C
0x14002415f  mov     rax, [rdi+20h]
0x140024163  test    dword ptr [rax+50h], 400000h
0x14002416a  jz      short loc_14002417C
0x14002416c  mov     rdx, rdi
0x14002416f  mov     rcx, rsi
0x140024172  call    SecPostCreateHandleDirectVolumeAccess
0x140024177  jmp     loc_140023F9C
0x14002417c  cmp     r14d, 1
0x140024180  jz      short loc_1400241E4
0x140024182  xor     r14d, r14d
0x140024185  test    bl, bl
0x140024187  jz      short loc_1400241E7
0x140024189  mov     rax, [rbp+57h+var_78]
0x14002418d  lea     r9, [rbp+57h+var_50]
0x140024191  mov     r8d, r13d
0x140024194  mov     [rsp+0F0h+var_D0], rax; __int64
0x140024199  mov     rdx, rdi
0x14002419c  mov     rcx, rsi; CallbackData
0x14002419f  call    SecSendFileCreateEvent
0x1400241a4  call    SecIsFileSourceMonitoringEnabled
0x1400241a9  test    al, al
0x1400241ab  jz      short loc_1400241E7
0x1400241ad  mov     rcx, rsi
0x1400241b0  call    SecFltGetRequestorProcess
0x1400241b5  mov     rcx, rax
0x1400241b8  lea     rdx, [rbp+57h+ListEntry]
0x1400241bc  call    SecGetProcessContextByObject
0x1400241c1  test    eax, eax
0x1400241c3  js      short loc_1400241E7
0x1400241c5  mov     rdx, [rbp+57h+ListEntry]
0x1400241c9  cmp     [rdx+2D4h], r14b
0x1400241d0  jz      short loc_1400241E7
0x1400241d2  mov     rcx, [rdi+20h]
0x1400241d6  add     rdx, 0A8h
0x1400241dd  call    SecCreateFileCreatorEa
0x1400241e2  jmp     short loc_1400241E7
0x1400241e4  xor     r14d, r14d
0x1400241e7  mov     rdx, [rdi+20h]; FileObject
0x1400241eb  lea     r8, [rbp+57h+var_90]; Context
0x1400241ef  mov     rcx, [rdi+18h]; Instance
0x1400241f3  call    FltGetStreamContext_0
0x1400241f8  test    eax, eax
0x1400241fa  jns     short loc_140024210
0x1400241fc  lea     rdx, [rbp+57h+var_90]
0x140024200  mov     rcx, rdi
0x140024203  call    SecCreateStreamContext
0x140024208  test    eax, eax
0x14002420a  js      loc_140023F9C
0x140024210  lfence
0x140024213  mov     rax, [r15]
0x140024216  test    al, 10h
0x140024218  jz      loc_1400243CF
0x14002421e  test    bl, bl
0x140024220  jnz     loc_140024515
0x140024226  test    al, 8
0x140024228  jz      loc_1400243DE
0x14002422e  mov     rax, [rbp+57h+var_90]
0x140024232  mov     ecx, [rax+10h]
0x140024235  test    cl, 20h
0x140024238  jnz     short loc_14002427A
0x14002423a  mov     rcx, [rdi+20h]
0x14002423e  lea     rdx, [rbp+57h+var_58]
0x140024242  call    SecIsRemoteFile
0x140024247  xor     ebx, ebx
0x140024249  test    eax, eax
0x14002424b  js      short loc_14002427C
0x14002424d  cmp     [rbp+57h+var_58], bl
0x140024250  jz      short loc_14002426F
0x140024252  lea     rdx, [rbp+57h+var_56]
0x140024256  mov     rcx, rdi
  ... truncated ...
```
