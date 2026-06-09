# BfsPreCleanupOperation

- ea: `0x140002350`
- end: `0x140002617`
- name: `BfsPreCleanupOperation`
- size: `711`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x140001270`
- `0x140002350`
- `0x140004b68`
- `0x140004d60`
- `0x140013860`
- `0x1400138a0`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtection` at `0x140002599`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140002599`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400023b1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140002586`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400023b1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140002586`
- `ntoskrnl!ExAcquireRundownProtection` at `0x1400023c4`
- `ntoskrnl!ExAcquireRundownProtection` at `0x1400023c4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400023d3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400025a5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400023d3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400025a5`
- `ntoskrnl!EtwWriteTransfer` at `0x14000257a`
- `ntoskrnl!EtwWriteTransfer` at `0x14000257a`
- `FLTMGR!FltGetFileNameInformation` at `0x1400024c3`
- `FLTMGR!FltGetFileNameInformation` at `0x1400024c3`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140002600`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140002600`
- `FLTMGR!FltReleaseContext` at `0x1400025ba`
- `FLTMGR!FltReleaseContext` at `0x1400025ba`
- `FLTMGR!FltGetFileContext` at `0x1400023f7`
- `FLTMGR!FltGetFileContext` at `0x1400023f7`

## pseudocode

```c
__int64 __fastcall BfsPreCleanupOperation(PFLT_CALLBACK_DATA CallbackData, __int64 a2, PFLT_CONTEXT *a3)
{
  PDEVICE_OBJECT DeviceObject; // rax
  BOOLEAN v7; // bl
  __int64 v8; // rbx
  NTSTATUS v9; // eax
  char v11; // [rsp+30h] [rbp-69h]
  int v12; // [rsp+50h] [rbp-49h] BYREF
  __int64 v13; // [rsp+58h] [rbp-41h]
  PFLT_CONTEXT Context; // [rsp+60h] [rbp-39h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+68h] [rbp-31h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+70h] [rbp-29h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+80h] [rbp-19h] BYREF
  int *v18; // [rsp+90h] [rbp-9h]
  int v19; // [rsp+98h] [rbp-1h]
  int v20; // [rsp+9Ch] [rbp+3h]
  int *v21; // [rsp+A0h] [rbp+7h]
  __int64 v22; // [rsp+A8h] [rbp+Fh]

  Context = 0;
  FileNameInformation = 0;
  if ( (unsigned int)Feature_AppSiloSmbNoTrackDelete__private_IsEnabledDeviceUsageNoInline() )
  {
    DeviceObject = CallbackData->Iopb->TargetFileObject->DeviceObject;
    if ( !DeviceObject || DeviceObject->DeviceType == 20 )
      goto LABEL_16;
  }
  KeEnterCriticalRegion();
  v7 = ExAcquireRundownProtection(&gBfsRundownProtection);
  KeLeaveCriticalRegion();
  if ( !v7 )
    goto LABEL_16;
  if ( FltGetFileContext(*(PFLT_INSTANCE *)(a2 + 24), CallbackData->Iopb->TargetFileObject, &Context) >= 0 )
  {
    v13 = (unsigned int)Feature_AppSiloBFSPagePoolCleanup__private_featureState;
    if ( (Feature_AppSiloBFSPagePoolCleanup__private_featureState & 0x10) == 0 )
    {
      LODWORD(v13) = Feature_AppSiloBFSPagePoolCleanup__private_featureState | 1;
      v8 = v13;
      v12 = 3;
      if ( (unsigned int)wil_details_FeatureReporting_ReportUsageToServiceDirect(
                           wil_details_featureDescriptors_a,
                           v13,
                           2)
        && g_wil_details_pfnFeatureLoggingHook )
      {
        v11 = 0;
        g_wil_details_pfnFeatureLoggingHook(
          57751298,
          &Feature_AppSiloBFSPagePoolCleanup_logged_traits,
          0,
          1,
          &v12,
          0,
          v11,
          1);
      }
      wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(v8, 3, wil_details_featureDescriptors_a);
    }
    if ( !*((_QWORD *)Context + 1) )
    {
      v9 = FltGetFileNameInformation(CallbackData, 0x101u, &FileNameInformation);
      if ( v9 < 0 )
      {
        if ( (unsigned int)dword_140019000 > 3 )
        {
          v12 = v9;
          v22 = 4;
          v21 = &v12;
          UserData.Ptr = (ULONGLONG)EventInformation;
          *(_DWORD *)&EventDescriptor.Level = 3;
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          EventDescriptor.Keyword = 0;
          UserData.Size = *(unsigned __int16 *)EventInformation;
          v18 = &dword_140016D9C;
          UserData.Reserved = 2;
          v19 = 30;
          v20 = 1;
          LODWORD(v13) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
        }
        goto LABEL_15;
      }
      if ( _InterlockedCompareExchange64((volatile signed __int64 *)Context + 1, (signed __int64)FileNameInformation, 0) )
        FltReleaseFileNameInformation(FileNameInformation);
    }
    *a3 = Context;
    return 0;
  }
LABEL_15:
  KeEnterCriticalRegion();
  ExReleaseRundownProtection(&gBfsRundownProtection);
  KeLeaveCriticalRegion();
LABEL_16:
  if ( Context )
    FltReleaseContext(Context);
  return 1;
}

```

## disassembly

```asm
0x140002350  push    rbp
0x140002352  push    rbx
0x140002353  push    rsi
0x140002354  push    rdi
0x140002355  push    r12
0x140002357  push    r14
0x140002359  push    r15
0x14000235b  lea     rbp, [rsp-27h]
0x140002360  sub     rsp, 0C0h
0x140002367  mov     rax, cs:__security_cookie
0x14000236e  xor     rax, rsp
0x140002371  mov     [rbp+57h+var_40], rax
0x140002375  xor     r12d, r12d
0x140002378  mov     r15, r8
0x14000237b  mov     [rbp+57h+Context], r12
0x14000237f  mov     r14, rdx
0x140002382  mov     [rbp+57h+FileNameInformation], r12
0x140002386  mov     rsi, rcx
0x140002389  call    Feature_AppSiloSmbNoTrackDelete__private_IsEnabledDeviceUsageNoInline
0x14000238e  test    eax, eax
0x140002390  jz      short loc_1400023B1
0x140002392  mov     rax, [rsi+10h]
0x140002396  mov     rcx, [rax+8]
0x14000239a  mov     rax, [rcx+8]
0x14000239e  test    rax, rax
0x1400023a1  jz      loc_1400025B1
0x1400023a7  cmp     dword ptr [rax+48h], 14h
0x1400023ab  jz      loc_1400025B1
0x1400023b1  call    cs:__imp_KeEnterCriticalRegion
0x1400023b8  nop     dword ptr [rax+rax+00h]
0x1400023bd  lea     rcx, gBfsRundownProtection; RunRef
0x1400023c4  call    cs:__imp_ExAcquireRundownProtection
0x1400023cb  nop     dword ptr [rax+rax+00h]
0x1400023d0  movzx   ebx, al
0x1400023d3  call    cs:__imp_KeLeaveCriticalRegion
0x1400023da  nop     dword ptr [rax+rax+00h]
0x1400023df  test    bl, bl
0x1400023e1  jz      loc_1400025B1
0x1400023e7  mov     rdx, [rsi+10h]
0x1400023eb  lea     r8, [rbp+57h+Context]; Context
0x1400023ef  mov     rcx, [r14+18h]; Instance
0x1400023f3  mov     rdx, [rdx+8]; FileObject
0x1400023f7  call    cs:__imp_FltGetFileContext
0x1400023fe  nop     dword ptr [rax+rax+00h]
0x140002403  test    eax, eax
0x140002405  js      loc_140002586
0x14000240b  mov     ecx, cs:Feature_AppSiloBFSPagePoolCleanup__private_featureState
0x140002411  mov     [rbp+57h+var_98], r12
0x140002415  mov     dword ptr [rbp+57h+var_98], ecx
0x140002418  test    cl, 10h
0x14000241b  jnz     loc_1400024A9
0x140002421  mov     rax, [rbp+57h+var_98]
0x140002425  or      ecx, 1
0x140002428  mov     [rbp+57h+var_98], rax
0x14000242c  mov     r8d, 2
0x140002432  mov     dword ptr [rbp+57h+var_98], ecx
0x140002435  lea     rcx, wil_details_featureDescriptors_a
0x14000243c  mov     rbx, [rbp+57h+var_98]
0x140002440  mov     rdx, rbx
0x140002443  mov     [rbp+57h+var_A0], 3
0x14000244a  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x14000244f  test    eax, eax
0x140002451  jz      short loc_140002495
0x140002453  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x14000245a  test    rax, rax
0x14000245d  jz      short loc_140002495
0x14000245f  mov     rdx, cs:off_140018088
0x140002466  lea     rcx, [rbp+57h+var_A0]
0x14000246a  mov     [rsp+0F0h+var_B8], 1
0x140002473  mov     r9d, 1
0x140002479  mov     [rsp+0F0h+var_C0], r12b
0x14000247e  xor     r8d, r8d
0x140002481  mov     [rsp+0F0h+UserData], r12
0x140002486  mov     qword ptr [rsp+0F0h+UserDataCount], rcx
0x14000248b  mov     ecx, 3713702h
0x140002490  call    _guard_dispatch_icall
0x140002495  lea     r8, wil_details_featureDescriptors_a
0x14000249c  mov     edx, 3
0x1400024a1  mov     rcx, rbx
0x1400024a4  call    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath
0x1400024a9  mov     rax, [rbp+57h+Context]
0x1400024ad  cmp     [rax+8], r12
0x1400024b1  jnz     loc_14000260C
0x1400024b7  lea     r8, [rbp+57h+FileNameInformation]; FileNameInformation
0x1400024bb  mov     edx, 101h; NameOptions
0x1400024c0  mov     rcx, rsi; CallbackData
0x1400024c3  call    cs:__imp_FltGetFileNameInformation
0x1400024ca  nop     dword ptr [rax+rax+00h]
0x1400024cf  test    eax, eax
0x1400024d1  jns     loc_1400025EA
0x1400024d7  mov     ecx, cs:dword_140019000
0x1400024dd  cmp     ecx, 3
0x1400024e0  jbe     loc_140002586
0x1400024e6  mov     [rbp+57h+var_A0], eax
0x1400024e9  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x1400024ed  mov     [rbp+57h+var_48], 4
0x1400024f5  lea     rax, [rbp+57h+var_A0]
0x1400024f9  mov     [rbp+57h+var_50], rax
0x1400024fd  xor     r9d, r9d; RelatedActivityId
0x140002500  mov     rax, cs:qword_140016D92
0x140002507  xor     r8d, r8d; ActivityId
0x14000250a  movzx   ecx, ax
0x14000250d  mov     rax, cs:EventInformation
0x140002514  mov     [rbp+57h+var_70.Ptr], rax
0x140002518  mov     dword ptr [rbp+57h+EventDescriptor.Level], ecx
0x14000251b  lea     rcx, _TraceLoggingMetadata
0x140002522  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x140002529  mov     [rbp+57h+EventDescriptor.Keyword], r12
0x14000252d  movzx   eax, word ptr [rax]
0x140002530  mov     [rbp+57h+var_70.Size], eax
0x140002533  lea     rax, dword_140016D9C
0x14000253a  mov     [rbp+57h+var_60], rax
0x14000253e  lea     rax, _TraceLoggingMetadataEnd
0x140002545  sub     eax, ecx
0x140002547  mov     dword ptr [rbp+57h+var_70.0Ch], 2
0x14000254e  mov     [rbp+57h+var_58], 1Eh
0x140002555  mov     [rbp+57h+var_54], 1
0x14000255c  mov     dword ptr [rbp+57h+var_98], eax
0x14000255f  mov     eax, dword ptr [rbp+57h+var_98]
0x140002562  mov     rcx, cs:RegHandle; RegHandle
0x140002569  lea     rax, [rbp+57h+var_70]
0x14000256d  mov     [rsp+0F0h+UserData], rax; UserData
0x140002572  mov     [rsp+0F0h+UserDataCount], 3; UserDataCount
0x14000257a  call    cs:__imp_EtwWriteTransfer
0x140002581  nop     dword ptr [rax+rax+00h]
0x140002586  call    cs:__imp_KeEnterCriticalRegion
0x14000258d  nop     dword ptr [rax+rax+00h]
0x140002592  lea     rcx, gBfsRundownProtection; RunRef
0x140002599  call    cs:__imp_ExReleaseRundownProtection
0x1400025a0  nop     dword ptr [rax+rax+00h]
0x1400025a5  call    cs:__imp_KeLeaveCriticalRegion
0x1400025ac  nop     dword ptr [rax+rax+00h]
0x1400025b1  mov     rcx, [rbp+57h+Context]; Context
0x1400025b5  test    rcx, rcx
0x1400025b8  jz      short loc_1400025C6
0x1400025ba  call    cs:__imp_FltReleaseContext
0x1400025c1  nop     dword ptr [rax+rax+00h]
0x1400025c6  mov     eax, 1
0x1400025cb  mov     rcx, [rbp+57h+var_40]
0x1400025cf  xor     rcx, rsp; StackCookie
0x1400025d2  call    __security_check_cookie
0x1400025d7  add     rsp, 0C0h
0x1400025de  pop     r15
0x1400025e0  pop     r14
0x1400025e2  pop     r12
0x1400025e4  pop     rdi
0x1400025e5  pop     rsi
0x1400025e6  pop     rbx
0x1400025e7  pop     rbp
0x1400025e8  retn
0x1400025ea  mov     rdx, [rbp+57h+Context]
0x1400025ee  xor     eax, eax
0x1400025f0  mov     rcx, [rbp+57h+FileNameInformation]
0x1400025f4  lock cmpxchg [rdx+8], rcx
0x1400025fa  jz      short loc_14000260C
0x1400025fc  mov     rcx, [rbp+57h+FileNameInformation]; FileNameInformation
0x140002600  call    cs:__imp_FltReleaseFileNameInformation
0x140002607  nop     dword ptr [rax+rax+00h]
0x14000260c  mov     rax, [rbp+57h+Context]
0x140002610  mov     [r15], rax
0x140002613  xor     eax, eax
0x140002615  jmp     short loc_1400025CB
```
