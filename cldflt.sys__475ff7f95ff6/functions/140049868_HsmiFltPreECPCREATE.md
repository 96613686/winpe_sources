# HsmiFltPreECPCREATE

- ea: `0x140049868`
- end: `0x140049f0e`
- name: `HsmiFltPreECPCREATE`
- size: `1702`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, __int64, _QWORD *)`
- caller_count: `3`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140049790`
- `0x140049810`
- `0x140049850`

## callees

- `0x140003c50`
- `0x140006b78`
- `0x140007220`
- `0x1400074b0`
- `0x140008b74`
- `0x140008e90`
- `0x140009300`
- `0x140009d7c`
- `0x14000bfd4`
- `0x14001e1c0`
- `0x14001e600`
- `0x140049868`
- `0x140049f20`
- `0x14005c6a0`
- `0x14005cdd0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140049c64`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140049c64`
- `ntoskrnl!ExReleaseResourceLite` at `0x140049c58`
- `ntoskrnl!ExReleaseResourceLite` at `0x140049c58`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140049bb5`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140049bb5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140049b9d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140049b9d`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140049a28`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140049a28`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140049931`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140049931`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140049bda`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140049c06`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140049bda`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140049c06`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140049ea5`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140049ea5`
- `FLTMGR!FltGetFileNameInformation` at `0x140049a83`
- `FLTMGR!FltGetFileNameInformation` at `0x140049a83`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140049a39`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140049a39`
- `FLTMGR!FltGetInstanceContext` at `0x1400498e7`
- `FLTMGR!FltGetInstanceContext` at `0x1400498e7`
- `FLTMGR!FltReleaseContext` at `0x140049962`
- `FLTMGR!FltReleaseContext` at `0x140049962`

## pseudocode

```c
__int64 __fastcall HsmiFltPreECPCREATE(PFLT_CALLBACK_DATA CallbackData, __int64 a2, _QWORD *a3)
{
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  void *v4; // r14
  unsigned int v7; // r12d
  struct _FLT_INSTANCE *TargetInstance; // r15
  PFLT_IO_PARAMETER_BLOCK v9; // rcx
  PFILE_OBJECT TargetFileObject; // rax
  int ECPTags; // esi
  NTSTATUS v13; // ebx
  __int64 v14; // rdx
  __int64 v15; // rcx
  char v16; // bl
  int v17; // r13d
  __int64 v18; // rdx
  __int64 v19; // rcx
  _DWORD *v20; // rax
  _DWORD *v21; // rbx
  PFLT_IO_PARAMETER_BLOCK v22; // rax
  PIO_SECURITY_CONTEXT SecurityContext; // rax
  int AttributionInformation; // ebx
  PDEVICE_OBJECT v25; // rcx
  __int64 v26; // rdx
  __int64 *v27; // rdx
  struct _RTL_AVL_TABLE *v28; // rcx
  unsigned __int8 v29[8]; // [rsp+30h] [rbp-D0h] BYREF
  PFLT_CONTEXT Context; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int8 NewElement[8]; // [rsp+40h] [rbp-C0h] BYREF
  PVOID inserted; // [rsp+48h] [rbp-B8h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD Buffer[8]; // [rsp+58h] [rbp-A8h] BYREF
  int v35; // [rsp+98h] [rbp-68h]
  int v36; // [rsp+9Ch] [rbp-64h]
  __int64 v37; // [rsp+A0h] [rbp-60h]
  __int64 Parameter; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v39; // [rsp+B0h] [rbp-50h] BYREF
  _OWORD v40[5]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v41; // [rsp+110h] [rbp+10h] BYREF
  __int128 v42; // [rsp+118h] [rbp+18h]

  Iopb = CallbackData->Iopb;
  v4 = 0;
  inserted = 0;
  v7 = 1;
  TargetInstance = Iopb->TargetInstance;
  *a3 = 0;
  v9 = CallbackData->Iopb;
  Context = 0;
  FileNameInformation = 0;
  if ( (v9->OperationFlags & 2) != 0 )
    return v7;
  TargetFileObject = v9->TargetFileObject;
  if ( TargetFileObject )
  {
    if ( (TargetFileObject->Flags & 0x400000) != 0 )
      return v7;
  }
  ECPTags = 0;
  FltGetInstanceContext(TargetInstance, &Context);
  if ( !Context )
    goto LABEL_7;
  if ( *(_DWORD *)Context != 843674440 && !(unsigned __int8)HsmOsIsCbdTransacted(CallbackData->Thread, CallbackData) )
  {
    HsmpDbgBreakOnCbd(CallbackData);
    if ( ExAcquireRundownProtection((PEX_RUNDOWN_REF)Context + 22) )
    {
      v7 = 5;
      ECPTags = HsmiCreateAllocateECPTags((__int64)CallbackData, a3);
      HsmDbgBreakOnStatus(ECPTags);
      if ( ECPTags < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qqd(
            WPP_GLOBAL_Control->AttachedDevice,
            27,
            WPP_666dd97b4df534fdc194a0db3f3e286d_Traceguids,
            TargetInstance,
            Context,
            CallbackData->IoStatus.Status);
        }
        ExReleaseRundownProtection((PEX_RUNDOWN_REF)Context + 22);
      }
    }
    goto LABEL_7;
  }
  memset(v40, 0, 0x44u);
  v39 = 0;
  if ( *(_DWORD *)Context == 843674440 )
  {
    v22 = CallbackData->Iopb;
    v29[0] = 0;
    if ( v22->MajorFunction )
      goto LABEL_7;
    SecurityContext = v22->Parameters.Create.SecurityContext;
    if ( !SecurityContext || (SecurityContext->DesiredAccess & 0x2000027) == 0 )
      goto LABEL_7;
    AttributionInformation = HsmpGetAttributionInformation(0, 0, CallbackData, &inserted);
    HsmDbgBreakOnStatus(AttributionInformation);
    if ( AttributionInformation < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qqd(
          WPP_GLOBAL_Control->AttachedDevice,
          22,
          WPP_666dd97b4df534fdc194a0db3f3e286d_Traceguids,
          TargetInstance,
          Context,
          AttributionInformation);
      }
      v4 = inserted;
      goto LABEL_7;
    }
    v4 = inserted;
    v13 = HsmOsCheckAppCompatPolicy(inserted, 3, v29);
    HsmDbgBreakOnStatus(v13);
    if ( v13 < 0 )
    {
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_7;
      }
      v26 = 23;
LABEL_57:
      WPP_SF_qqd(
        v25->AttachedDevice,
        v26,
        WPP_666dd97b4df534fdc194a0db3f3e286d_Traceguids,
        TargetInstance,
        Context,
        v13);
      goto LABEL_7;
    }
    if ( !v29[0] )
      goto LABEL_7;
  }
  v13 = FltGetFileNameInformation(CallbackData, 0x102u, &FileNameInformation);
  HsmDbgBreakOnStatus(v13);
  if ( (unsigned int)(v13 + 1073741773) <= 1 || v13 == -1073741766 )
    goto LABEL_7;
  if ( v13 < 0 )
  {
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_7;
    }
    v26 = 24;
    goto LABEL_57;
  }
  LODWORD(v40[0]) = 48;
  LOBYTE(v14) = 2;
  *(_QWORD *)&v40[1] = &FileNameInformation->Name;
  *((_QWORD *)&v40[0] + 1) = 0;
  DWORD2(v40[1]) = 576;
  v40[2] = 0;
  v16 = HsmOsSetPlaceholderCompatMode(v15, v14);
  Parameter = 0;
  Buffer[3] = Filter;
  Buffer[4] = TargetInstance;
  Buffer[5] = v40;
  Buffer[6] = &v39;
  Buffer[7] = v40;
  v35 = 72;
  v36 = 68;
  v37 = 0;
  v17 = HsmExpandKernelStackAndCallout(FltQueryInformationByNameCallout, (NTSTATUS *)&Parameter);
  HsmDbgBreakOnStatus(v17);
  LOBYTE(v18) = v16;
  HsmOsSetPlaceholderCompatMode(v19, v18);
  if ( v17 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qqd(
        WPP_GLOBAL_Control->AttachedDevice,
        25,
        WPP_666dd97b4df534fdc194a0db3f3e286d_Traceguids,
        TargetInstance,
        Context,
        v17);
    }
    goto LABEL_7;
  }
  if ( *(_DWORD *)Context != 843674440 )
  {
    if ( (HIDWORD(v40[3]) & 0xFFFF0FFF) == dword_140029670 )
    {
      ECPTags = -1072103334;
      HsmDbgBreakOnStatus(-1072103334);
    }
    goto LABEL_7;
  }
  if ( (HIDWORD(v40[3]) & 0xFFFF0FFF) == dword_140029670 )
  {
    v42 = 0;
    v41 = *(_QWORD *)&v40[0];
    Buffer[1] = 0;
    NewElement[0] = 0;
    v29[0] = 0;
    Buffer[0] = CallbackData;
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite((PERESOURCE)((char *)Context + 8), 1u);
    inserted = RtlInsertElementGenericTableAvl((PRTL_AVL_TABLE)((char *)Context + 112), Buffer, 0x10u, NewElement);
    v20 = RtlInsertElementGenericTableAvl((PRTL_AVL_TABLE)((char *)Context + 216), &v41, 0x18u, v29);
    v21 = v20;
    if ( inserted )
    {
      if ( v20 )
      {
        *((_QWORD *)inserted + 1) = v41;
        if ( ++v20[2] == 1 )
        {
          v20[3] = HsmOsGetProcessId(v4);
          *((_BYTE *)v21 + 16) = HsmOsGetThreadPlaceholderHydrationAlwaysExplicit(CallbackData);
        }
        v7 = 0;
        goto LABEL_34;
      }
      v27 = Buffer;
      v28 = (struct _RTL_AVL_TABLE *)((char *)Context + 112);
    }
    else
    {
      if ( !v20 || !v29[0] )
      {
LABEL_33:
        ECPTags = -1073741670;
        HsmDbgBreakOnStatus(-1073741670);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qqd(
            WPP_GLOBAL_Control->AttachedDevice,
            26,
            WPP_666dd97b4df534fdc194a0db3f3e286d_Traceguids,
            TargetInstance,
            Context,
            v17);
        }
LABEL_34:
        ExReleaseResourceLite((PERESOURCE)((char *)Context + 8));
        KeLeaveCriticalRegion();
        goto LABEL_7;
      }
      v27 = &v41;
      v28 = (struct _RTL_AVL_TABLE *)((char *)Context + 216);
    }
    RtlDeleteElementGenericTableAvl(v28, v27);
    goto LABEL_33;
  }
LABEL_7:
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  if ( v4 )
    HsmpCleanupAttributionInformation(v4);
  if ( Context )
    FltReleaseContext(Context);
  if ( ECPTags < 0 )
  {
    CallbackData->IoStatus.Status = ECPTags;
    v7 = 4;
    CallbackData->IoStatus.Information = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x140049868  mov     [rsp-8+arg_8], rbx
0x14004986d  push    rbp
0x14004986e  push    rsi
0x14004986f  push    rdi
0x140049870  push    r12
0x140049872  push    r13
0x140049874  push    r14
0x140049876  push    r15
0x140049878  lea     rbp, [rsp-30h]
0x14004987d  sub     rsp, 130h
0x140049884  mov     rax, cs:__security_cookie
0x14004988b  xor     rax, rsp
0x14004988e  mov     [rbp+60h+var_38], rax
0x140049892  mov     rax, [rcx+10h]
0x140049896  xor     r14d, r14d
0x140049899  mov     rdi, rcx
0x14004989c  mov     [rsp+160h+var_118], r14
0x1400498a1  mov     r13d, 1
0x1400498a7  mov     rbx, r8
0x1400498aa  mov     r12d, r13d
0x1400498ad  mov     r15, [rax+10h]
0x1400498b1  mov     [r8], r14
0x1400498b4  mov     rcx, [rcx+10h]
0x1400498b8  mov     [rsp+160h+Context], 0
0x1400498c1  mov     [rsp+160h+FileNameInformation], r14
0x1400498c6  test    byte ptr [rcx+6], 2
0x1400498ca  jnz     loc_140049976
0x1400498d0  mov     rax, [rcx+8]
0x1400498d4  test    rax, rax
0x1400498d7  jnz     loc_1400499A1
0x1400498dd  lea     rdx, [rsp+160h+Context]; Context
0x1400498e2  mov     rcx, r15; Instance
0x1400498e5  xor     esi, esi
0x1400498e7  call    cs:__imp_FltGetInstanceContext
0x1400498ee  nop     dword ptr [rax+rax+00h]
0x1400498f3  mov     rcx, [rsp+160h+Context]
0x1400498f8  test    rcx, rcx
0x1400498fb  jz      short loc_140049941
0x1400498fd  cmp     dword ptr [rcx], 32497348h
0x140049903  jz      loc_140049A4A
0x140049909  mov     rcx, [rdi+8]
0x14004990d  mov     rdx, rdi
0x140049910  call    HsmOsIsCbdTransacted
0x140049915  test    al, al
0x140049917  jnz     loc_140049A4A
0x14004991d  mov     rcx, rdi
0x140049920  call    HsmpDbgBreakOnCbd
0x140049925  mov     rcx, [rsp+160h+Context]
0x14004992a  add     rcx, 0B0h; RunRef
0x140049931  call    cs:__imp_ExAcquireRundownProtection
0x140049938  nop     dword ptr [rax+rax+00h]
0x14004993d  test    al, al
0x14004993f  jnz     short loc_1400499B0
0x140049941  mov     rcx, [rsp+160h+FileNameInformation]; FileNameInformation
0x140049946  test    rcx, rcx
0x140049949  jnz     loc_140049A39
0x14004994f  test    r14, r14
0x140049952  jnz     loc_140049C75
0x140049958  mov     rcx, [rsp+160h+Context]; Context
0x14004995d  test    rcx, rcx
0x140049960  jz      short loc_14004996E
0x140049962  call    cs:__imp_FltReleaseContext
0x140049969  nop     dword ptr [rax+rax+00h]
0x14004996e  test    esi, esi
0x140049970  js      loc_140049EF8
0x140049976  mov     eax, r12d
0x140049979  mov     rcx, [rbp+60h+var_38]
0x14004997d  xor     rcx, rsp; StackCookie
0x140049980  call    __security_check_cookie
0x140049985  mov     rbx, [rsp+160h+arg_8]
0x14004998d  add     rsp, 130h
0x140049994  pop     r15
0x140049996  pop     r14
0x140049998  pop     r13
0x14004999a  pop     r12
0x14004999c  pop     rdi
0x14004999d  pop     rsi
0x14004999e  pop     rbp
0x14004999f  retn
0x1400499a1  test    dword ptr [rax+50h], 400000h
0x1400499a8  jz      loc_1400498DD
0x1400499ae  jmp     short loc_140049976
0x1400499b0  mov     rdx, rbx
0x1400499b3  mov     rcx, rdi
0x1400499b6  mov     r12d, 5
0x1400499bc  call    HsmiCreateAllocateECPTags
0x1400499c1  mov     ecx, eax
0x1400499c3  mov     esi, eax
0x1400499c5  call    HsmDbgBreakOnStatus
0x1400499ca  test    esi, esi
0x1400499cc  jns     loc_140049941
0x1400499d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400499d9  lea     rax, WPP_GLOBAL_Control
0x1400499e0  cmp     rcx, rax
0x1400499e3  jz      short loc_140049A1C
0x1400499e5  mov     eax, [rcx+2Ch]
0x1400499e8  test    r13b, al
0x1400499eb  jz      short loc_140049A1C
0x1400499ed  cmp     byte ptr [rcx+29h], 2
0x1400499f1  jb      short loc_140049A1C
0x1400499f3  mov     eax, [rdi+18h]
0x1400499f6  lea     edx, [r12+16h]
0x1400499fb  mov     rcx, [rcx+18h]
0x1400499ff  lea     r8, WPP_666dd97b4df534fdc194a0db3f3e286d_Traceguids
0x140049a06  mov     [rsp+160h+var_138], eax
0x140049a0a  mov     r9, r15
0x140049a0d  mov     rax, [rsp+160h+Context]
0x140049a12  mov     [rsp+160h+var_140], rax
0x140049a17  call    WPP_SF_qqd
0x140049a1c  mov     rcx, [rsp+160h+Context]
0x140049a21  add     rcx, 0B0h; RunRef
0x140049a28  call    cs:__imp_ExReleaseRundownProtection
0x140049a2f  nop     dword ptr [rax+rax+00h]
0x140049a34  jmp     loc_140049941
0x140049a39  call    cs:__imp_FltReleaseFileNameInformation
0x140049a40  nop     dword ptr [rax+rax+00h]
0x140049a45  jmp     loc_14004994F
0x140049a4a  xor     eax, eax
0x140049a4c  lea     rcx, [rbp+60h+var_A0]; void *
0x140049a50  xor     edx, edx; Val
0x140049a52  mov     dword ptr [rbp+60h+var_A0+4], eax
0x140049a55  lea     r8d, [rax+44h]; Size
0x140049a59  call    memset
0x140049a5e  mov     rax, [rsp+160h+Context]
0x140049a63  xorps   xmm0, xmm0
0x140049a66  movups  [rbp+60h+var_B0], xmm0
0x140049a6a  cmp     dword ptr [rax], 32497348h
0x140049a70  jz      loc_140049C82
0x140049a76  lea     r8, [rsp+160h+FileNameInformation]; FileNameInformation
0x140049a7b  mov     edx, 102h; NameOptions
0x140049a80  mov     rcx, rdi; CallbackData
0x140049a83  call    cs:__imp_FltGetFileNameInformation
0x140049a8a  nop     dword ptr [rax+rax+00h]
0x140049a8f  mov     ecx, eax
0x140049a91  mov     ebx, eax
0x140049a93  call    HsmDbgBreakOnStatus
0x140049a98  lea     eax, [rbx+3FFFFFCDh]
0x140049a9e  cmp     eax, r13d
0x140049aa1  jbe     loc_140049941
0x140049aa7  cmp     ebx, 0C000003Ah
0x140049aad  jz      loc_140049941
0x140049ab3  test    ebx, ebx
0x140049ab5  js      loc_140049E17
0x140049abb  mov     rax, [rsp+160h+FileNameInformation]
0x140049ac0  xorps   xmm0, xmm0
0x140049ac3  add     rax, 8
0x140049ac7  mov     dword ptr [rbp+60h+var_A0], 30h ; '0'
0x140049ace  mov     dl, 2
0x140049ad0  mov     [rbp+60h+var_90], rax
0x140049ad4  mov     [rbp+60h+var_98], rsi
0x140049ad8  mov     [rbp+60h+var_88], 240h
0x140049adf  movdqa  [rbp+60h+var_80], xmm0
0x140049ae4  call    HsmOsSetPlaceholderCompatMode
0x140049ae9  mov     bl, al
0x140049aeb  mov     [rbp+60h+Parameter], rsi
0x140049aef  mov     rax, cs:Filter
0x140049af6  lea     rdx, [rbp+60h+Parameter]; Parameter
0x140049afa  mov     [rsp+160h+var_F0], rax
0x140049aff  lea     rcx, FltQueryInformationByNameCallout; Callout
0x140049b06  lea     rax, [rbp+60h+var_A0]
0x140049b0a  mov     [rsp+160h+var_E8], r15
0x140049b0f  mov     [rbp+60h+var_E0], rax
0x140049b13  lea     rax, [rbp+60h+var_B0]
0x140049b17  mov     [rbp+60h+var_D8], rax
0x140049b1b  lea     rax, [rbp+60h+var_A0]
0x140049b1f  mov     [rbp+60h+var_D0], rax
0x140049b23  mov     [rbp+60h+var_C8], 48h ; 'H'
0x140049b2a  mov     [rbp+60h+var_C4], 44h ; 'D'
0x140049b31  mov     [rbp+60h+var_C0], rsi
0x140049b35  call    HsmExpandKernelStackAndCallout
0x140049b3a  mov     ecx, eax
0x140049b3c  mov     r13d, eax
0x140049b3f  call    HsmDbgBreakOnStatus
0x140049b44  mov     dl, bl
0x140049b46  call    HsmOsSetPlaceholderCompatMode
0x140049b4b  xor     ecx, ecx
0x140049b4d  test    r13d, r13d
0x140049b50  js      loc_140049D09
0x140049b56  mov     rax, [rsp+160h+Context]
0x140049b5b  cmp     dword ptr [rax], 32497348h
0x140049b61  mov     eax, [rbp+60h+var_64]
0x140049b64  jnz     loc_140049D62
0x140049b6a  and     eax, 0FFFF0FFFh
0x140049b6f  cmp     eax, cs:dword_140029670
0x140049b75  jnz     loc_140049941
0x140049b7b  mov     rax, [rbp+60h+var_A0]
0x140049b7f  xorps   xmm0, xmm0
0x140049b82  movdqu  [rbp+60h+var_48], xmm0
0x140049b87  mov     [rbp+60h+var_50], rax
0x140049b8b  mov     [rsp+160h+var_100], rcx
0x140049b90  mov     [rsp+160h+NewElement], cl
0x140049b94  mov     [rsp+160h+var_130], cl
0x140049b98  mov     [rsp+160h+Buffer], rdi
0x140049b9d  call    cs:__imp_KeEnterCriticalRegion
0x140049ba4  nop     dword ptr [rax+rax+00h]
0x140049ba9  mov     rcx, [rsp+160h+Context]
0x140049bae  mov     dl, r12b; Wait
0x140049bb1  add     rcx, 8; Resource
0x140049bb5  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140049bbc  nop     dword ptr [rax+rax+00h]
0x140049bc1  mov     rcx, [rsp+160h+Context]
0x140049bc6  lea     r9, [rsp+160h+NewElement]; NewElement
0x140049bcb  add     rcx, 70h ; 'p'; Table
0x140049bcf  lea     rdx, [rsp+160h+Buffer]; Buffer
0x140049bd4  mov     r8d, 10h; BufferSize
0x140049bda  call    cs:__imp_RtlInsertElementGenericTableAvl
0x140049be1  nop     dword ptr [rax+rax+00h]
0x140049be6  mov     rcx, [rsp+160h+Context]
0x140049beb  lea     r9, [rsp+160h+var_130]; NewElement
0x140049bf0  add     rcx, 0D8h; Table
0x140049bf7  mov     [rsp+160h+var_118], rax
0x140049bfc  mov     r8d, 18h; BufferSize
0x140049c02  lea     rdx, [rbp+60h+var_50]; Buffer
0x140049c06  call    cs:__imp_RtlInsertElementGenericTableAvl
0x140049c0d  nop     dword ptr [rax+rax+00h]
0x140049c12  mov     rcx, [rsp+160h+var_118]
0x140049c17  mov     rbx, rax
0x140049c1a  test    rcx, rcx
0x140049c1d  jnz     loc_140049E46
0x140049c23  test    rax, rax
0x140049c26  jnz     loc_140049E8A
0x140049c2c  mov     esi, 0C000009Ah
0x140049c31  mov     ecx, esi
0x140049c33  call    HsmDbgBreakOnStatus
0x140049c38  mov     rcx, cs:WPP_GLOBAL_Control
0x140049c3f  lea     rax, WPP_GLOBAL_Control
0x140049c46  cmp     rcx, rax
0x140049c49  jnz     loc_140049EB6
0x140049c4f  mov     rcx, [rsp+160h+Context]
0x140049c54  add     rcx, 8; Resource
0x140049c58  call    cs:__imp_ExReleaseResourceLite
0x140049c5f  nop     dword ptr [rax+rax+00h]
0x140049c64  call    cs:__imp_KeLeaveCriticalRegion
0x140049c6b  nop     dword ptr [rax+rax+00h]
0x140049c70  jmp     loc_140049941
0x140049c75  mov     rcx, r14; P
0x140049c78  call    HsmpCleanupAttributionInformation
0x140049c7d  jmp     loc_140049958
0x140049c82  mov     rax, [rdi+10h]
0x140049c86  mov     [rsp+160h+var_130], sil
0x140049c8b  cmp     [rax+4], sil
0x140049c8f  jnz     loc_140049941
0x140049c95  mov     rax, [rax+18h]
0x140049c99  test    rax, rax
0x140049c9c  jz      loc_140049941
0x140049ca2  test    dword ptr [rax+10h], 2000027h
0x140049ca9  jz      loc_140049941
0x140049caf  lea     r9, [rsp+160h+var_118]
0x140049cb4  mov     r8, rdi
0x140049cb7  xor     edx, edx
0x140049cb9  xor     ecx, ecx
0x140049cbb  call    HsmpGetAttributionInformation
0x140049cc0  mov     ecx, eax
0x140049cc2  mov     ebx, eax
0x140049cc4  call    HsmDbgBreakOnStatus
0x140049cc9  test    ebx, ebx
0x140049ccb  js      loc_140049D84
0x140049cd1  mov     r14, [rsp+160h+var_118]
0x140049cd6  lea     r8, [rsp+160h+var_130]
0x140049cdb  mov     rcx, r14
0x140049cde  mov     edx, 3
0x140049ce3  call    HsmOsCheckAppCompatPolicy
0x140049ce8  mov     ecx, eax
0x140049cea  mov     ebx, eax
0x140049cec  call    HsmDbgBreakOnStatus
0x140049cf1  test    ebx, ebx
0x140049cf3  js      loc_140049DD5
0x140049cf9  cmp     [rsp+160h+var_130], sil
0x140049cfe  jz      loc_140049941
0x140049d04  jmp     loc_140049A76
0x140049d09  mov     rcx, cs:WPP_GLOBAL_Control
0x140049d10  lea     rax, WPP_GLOBAL_Control
0x140049d17  cmp     rcx, rax
0x140049d1a  jz      loc_140049941
0x140049d20  mov     eax, [rcx+2Ch]
0x140049d23  test    r12b, al
0x140049d26  jz      loc_140049941
0x140049d2c  cmp     byte ptr [rcx+29h], 2
0x140049d30  jb      loc_140049941
0x140049d36  mov     edx, 19h
0x140049d3b  mov     [rsp+160h+var_138], r13d
0x140049d40  mov     rax, [rsp+160h+Context]
0x140049d45  lea     r8, WPP_666dd97b4df534fdc194a0db3f3e286d_Traceguids
0x140049d4c  mov     rcx, [rcx+18h]
0x140049d50  mov     r9, r15
0x140049d53  mov     [rsp+160h+var_140], rax
0x140049d58  call    WPP_SF_qqd
0x140049d5d  jmp     loc_140049941
0x140049d62  and     eax, 0FFFF0FFFh
0x140049d67  cmp     eax, cs:dword_140029670
0x140049d6d  jnz     loc_140049941
0x140049d73  mov     esi, 0C019005Ah
0x140049d78  mov     ecx, esi
0x140049d7a  call    HsmDbgBreakOnStatus
0x140049d7f  jmp     loc_140049941
0x140049d84  mov     rcx, cs:WPP_GLOBAL_Control
0x140049d8b  lea     rax, WPP_GLOBAL_Control
0x140049d92  cmp     rcx, rax
0x140049d95  jz      short loc_140049DCB
0x140049d97  mov     eax, [rcx+2Ch]
  ... truncated ...
```
