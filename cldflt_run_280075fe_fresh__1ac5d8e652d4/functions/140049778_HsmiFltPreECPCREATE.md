# HsmiFltPreECPCREATE

- ea: `0x140049778`
- end: `0x140049e1e`
- name: `HsmiFltPreECPCREATE`
- size: `1702`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `3`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400496a0`
- `0x140049720`
- `0x140049760`

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
- `0x14001e140`
- `0x14001e580`
- `0x140049778`
- `0x140049e30`
- `0x14005c580`
- `0x14005ccb0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140049b74`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140049b74`
- `ntoskrnl!ExReleaseResourceLite` at `0x140049b68`
- `ntoskrnl!ExReleaseResourceLite` at `0x140049b68`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140049ac5`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140049ac5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140049aad`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140049aad`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140049938`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140049938`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140049841`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140049841`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140049aea`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140049b16`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140049aea`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140049b16`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140049db5`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140049db5`
- `FLTMGR!FltGetFileNameInformation` at `0x140049993`
- `FLTMGR!FltGetFileNameInformation` at `0x140049993`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140049949`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140049949`
- `FLTMGR!FltGetInstanceContext` at `0x1400497f7`
- `FLTMGR!FltGetInstanceContext` at `0x1400497f7`
- `FLTMGR!FltReleaseContext` at `0x140049872`
- `FLTMGR!FltReleaseContext` at `0x140049872`

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
  NTSTATUS ECPTags; // esi
  NTSTATUS v13; // ebx
  __int64 v14; // rcx
  char v15; // bl
  int v16; // r13d
  __int64 v17; // rcx
  _DWORD *v18; // rax
  _DWORD *v19; // rbx
  PFLT_IO_PARAMETER_BLOCK v20; // rax
  PIO_SECURITY_CONTEXT SecurityContext; // rax
  int AttributionInformation; // ebx
  PDEVICE_OBJECT v23; // rcx
  __int64 v24; // rdx
  __int64 *v25; // rdx
  struct _RTL_AVL_TABLE *v26; // rcx
  unsigned __int8 v27[8]; // [rsp+30h] [rbp-D0h] BYREF
  PFLT_CONTEXT Context; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int8 NewElement[8]; // [rsp+40h] [rbp-C0h] BYREF
  PVOID inserted; // [rsp+48h] [rbp-B8h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD Buffer[8]; // [rsp+58h] [rbp-A8h] BYREF
  int v33; // [rsp+98h] [rbp-68h]
  int v34; // [rsp+9Ch] [rbp-64h]
  __int64 v35; // [rsp+A0h] [rbp-60h]
  __int64 Parameter; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v37; // [rsp+B0h] [rbp-50h] BYREF
  _OWORD v38[5]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v39; // [rsp+110h] [rbp+10h] BYREF
  __int128 v40; // [rsp+118h] [rbp+18h]

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
      HsmDbgBreakOnStatus((unsigned int)ECPTags);
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
  memset(v38, 0, 0x44u);
  v37 = 0;
  if ( *(_DWORD *)Context == 843674440 )
  {
    v20 = CallbackData->Iopb;
    v27[0] = 0;
    if ( v20->MajorFunction )
      goto LABEL_7;
    SecurityContext = v20->Parameters.Create.SecurityContext;
    if ( !SecurityContext || (SecurityContext->DesiredAccess & 0x2000027) == 0 )
      goto LABEL_7;
    AttributionInformation = HsmpGetAttributionInformation(0, 0, (__int64)CallbackData, &inserted);
    HsmDbgBreakOnStatus((unsigned int)AttributionInformation);
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
    v13 = HsmOsCheckAppCompatPolicy(inserted, 3, v27);
    HsmDbgBreakOnStatus((unsigned int)v13);
    if ( v13 < 0 )
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_7;
      }
      v24 = 23;
LABEL_57:
      WPP_SF_qqd(
        v23->AttachedDevice,
        v24,
        WPP_666dd97b4df534fdc194a0db3f3e286d_Traceguids,
        TargetInstance,
        Context,
        v13);
      goto LABEL_7;
    }
    if ( !v27[0] )
      goto LABEL_7;
  }
  v13 = FltGetFileNameInformation(CallbackData, 0x102u, &FileNameInformation);
  HsmDbgBreakOnStatus((unsigned int)v13);
  if ( (unsigned int)(v13 + 1073741773) <= 1 || v13 == -1073741766 )
    goto LABEL_7;
  if ( v13 < 0 )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_7;
    }
    v24 = 24;
    goto LABEL_57;
  }
  LODWORD(v38[0]) = 48;
  *(_QWORD *)&v38[1] = &FileNameInformation->Name;
  *((_QWORD *)&v38[0] + 1) = 0;
  DWORD2(v38[1]) = 576;
  v38[2] = 0;
  v15 = HsmOsSetPlaceholderCompatMode(v14, 2);
  Parameter = 0;
  Buffer[3] = Filter;
  Buffer[4] = TargetInstance;
  Buffer[5] = v38;
  Buffer[6] = &v37;
  Buffer[7] = v38;
  v33 = 72;
  v34 = 68;
  v35 = 0;
  v16 = HsmExpandKernelStackAndCallout(FltQueryInformationByNameCallout, &Parameter);
  HsmDbgBreakOnStatus((unsigned int)v16);
  HsmOsSetPlaceholderCompatMode(v17, v15);
  if ( v16 < 0 )
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
        v16);
    }
    goto LABEL_7;
  }
  if ( *(_DWORD *)Context != 843674440 )
  {
    if ( (HIDWORD(v38[3]) & 0xFFFF0FFF) == dword_140029670 )
    {
      ECPTags = -1072103334;
      HsmDbgBreakOnStatus(3222863962LL);
    }
    goto LABEL_7;
  }
  if ( (HIDWORD(v38[3]) & 0xFFFF0FFF) == dword_140029670 )
  {
    v40 = 0;
    v39 = *(_QWORD *)&v38[0];
    Buffer[1] = 0;
    NewElement[0] = 0;
    v27[0] = 0;
    Buffer[0] = CallbackData;
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite((PERESOURCE)((char *)Context + 8), 1u);
    inserted = RtlInsertElementGenericTableAvl((PRTL_AVL_TABLE)((char *)Context + 112), Buffer, 0x10u, NewElement);
    v18 = RtlInsertElementGenericTableAvl((PRTL_AVL_TABLE)((char *)Context + 216), &v39, 0x18u, v27);
    v19 = v18;
    if ( inserted )
    {
      if ( v18 )
      {
        *((_QWORD *)inserted + 1) = v39;
        if ( ++v18[2] == 1 )
        {
          v18[3] = HsmOsGetProcessId(v4);
          *((_BYTE *)v19 + 16) = HsmOsGetThreadPlaceholderHydrationAlwaysExplicit((__int64)CallbackData);
        }
        v7 = 0;
        goto LABEL_34;
      }
      v25 = Buffer;
      v26 = (struct _RTL_AVL_TABLE *)((char *)Context + 112);
    }
    else
    {
      if ( !v18 || !v27[0] )
      {
LABEL_33:
        ECPTags = -1073741670;
        HsmDbgBreakOnStatus(3221225626LL);
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
            v16);
        }
LABEL_34:
        ExReleaseResourceLite((PERESOURCE)((char *)Context + 8));
        KeLeaveCriticalRegion();
        goto LABEL_7;
      }
      v25 = &v39;
      v26 = (struct _RTL_AVL_TABLE *)((char *)Context + 216);
    }
    RtlDeleteElementGenericTableAvl(v26, v25);
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
0x140049778  mov     [rsp-8+arg_8], rbx
0x14004977d  push    rbp
0x14004977e  push    rsi
0x14004977f  push    rdi
0x140049780  push    r12
0x140049782  push    r13
0x140049784  push    r14
0x140049786  push    r15
0x140049788  lea     rbp, [rsp-30h]
0x14004978d  sub     rsp, 130h
0x140049794  mov     rax, cs:__security_cookie
0x14004979b  xor     rax, rsp
0x14004979e  mov     [rbp+60h+var_38], rax
0x1400497a2  mov     rax, [rcx+10h]
0x1400497a6  xor     r14d, r14d
0x1400497a9  mov     rdi, rcx
0x1400497ac  mov     [rsp+160h+var_118], r14
0x1400497b1  mov     r13d, 1
0x1400497b7  mov     rbx, r8
0x1400497ba  mov     r12d, r13d
0x1400497bd  mov     r15, [rax+10h]
0x1400497c1  mov     [r8], r14
0x1400497c4  mov     rcx, [rcx+10h]
0x1400497c8  mov     [rsp+160h+Context], 0
0x1400497d1  mov     [rsp+160h+FileNameInformation], r14
0x1400497d6  test    byte ptr [rcx+6], 2
0x1400497da  jnz     loc_140049886
0x1400497e0  mov     rax, [rcx+8]
0x1400497e4  test    rax, rax
0x1400497e7  jnz     loc_1400498B1
0x1400497ed  lea     rdx, [rsp+160h+Context]; Context
0x1400497f2  mov     rcx, r15; Instance
0x1400497f5  xor     esi, esi
0x1400497f7  call    cs:__imp_FltGetInstanceContext
0x1400497fe  nop     dword ptr [rax+rax+00h]
0x140049803  mov     rcx, [rsp+160h+Context]
0x140049808  test    rcx, rcx
0x14004980b  jz      short loc_140049851
0x14004980d  cmp     dword ptr [rcx], 32497348h
0x140049813  jz      loc_14004995A
0x140049819  mov     rcx, [rdi+8]
0x14004981d  mov     rdx, rdi
0x140049820  call    HsmOsIsCbdTransacted
0x140049825  test    al, al
0x140049827  jnz     loc_14004995A
0x14004982d  mov     rcx, rdi
0x140049830  call    HsmpDbgBreakOnCbd
0x140049835  mov     rcx, [rsp+160h+Context]
0x14004983a  add     rcx, 0B0h; RunRef
0x140049841  call    cs:__imp_ExAcquireRundownProtection
0x140049848  nop     dword ptr [rax+rax+00h]
0x14004984d  test    al, al
0x14004984f  jnz     short loc_1400498C0
0x140049851  mov     rcx, [rsp+160h+FileNameInformation]; FileNameInformation
0x140049856  test    rcx, rcx
0x140049859  jnz     loc_140049949
0x14004985f  test    r14, r14
0x140049862  jnz     loc_140049B85
0x140049868  mov     rcx, [rsp+160h+Context]; Context
0x14004986d  test    rcx, rcx
0x140049870  jz      short loc_14004987E
0x140049872  call    cs:__imp_FltReleaseContext
0x140049879  nop     dword ptr [rax+rax+00h]
0x14004987e  test    esi, esi
0x140049880  js      loc_140049E08
0x140049886  mov     eax, r12d
0x140049889  mov     rcx, [rbp+60h+var_38]
0x14004988d  xor     rcx, rsp; StackCookie
0x140049890  call    __security_check_cookie
0x140049895  mov     rbx, [rsp+160h+arg_8]
0x14004989d  add     rsp, 130h
0x1400498a4  pop     r15
0x1400498a6  pop     r14
0x1400498a8  pop     r13
0x1400498aa  pop     r12
0x1400498ac  pop     rdi
0x1400498ad  pop     rsi
0x1400498ae  pop     rbp
0x1400498af  retn
0x1400498b1  test    dword ptr [rax+50h], 400000h
0x1400498b8  jz      loc_1400497ED
0x1400498be  jmp     short loc_140049886
0x1400498c0  mov     rdx, rbx
0x1400498c3  mov     rcx, rdi
0x1400498c6  mov     r12d, 5
0x1400498cc  call    HsmiCreateAllocateECPTags
0x1400498d1  mov     ecx, eax
0x1400498d3  mov     esi, eax
0x1400498d5  call    HsmDbgBreakOnStatus
0x1400498da  test    esi, esi
0x1400498dc  jns     loc_140049851
0x1400498e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400498e9  lea     rax, WPP_GLOBAL_Control
0x1400498f0  cmp     rcx, rax
0x1400498f3  jz      short loc_14004992C
0x1400498f5  mov     eax, [rcx+2Ch]
0x1400498f8  test    r13b, al
0x1400498fb  jz      short loc_14004992C
0x1400498fd  cmp     byte ptr [rcx+29h], 2
0x140049901  jb      short loc_14004992C
0x140049903  mov     eax, [rdi+18h]
0x140049906  lea     edx, [r12+16h]
0x14004990b  mov     rcx, [rcx+18h]
0x14004990f  lea     r8, WPP_666dd97b4df534fdc194a0db3f3e286d_Traceguids
0x140049916  mov     [rsp+160h+var_138], eax
0x14004991a  mov     r9, r15
0x14004991d  mov     rax, [rsp+160h+Context]
0x140049922  mov     [rsp+160h+var_140], rax
0x140049927  call    WPP_SF_qqd
0x14004992c  mov     rcx, [rsp+160h+Context]
0x140049931  add     rcx, 0B0h; RunRef
0x140049938  call    cs:__imp_ExReleaseRundownProtection
0x14004993f  nop     dword ptr [rax+rax+00h]
0x140049944  jmp     loc_140049851
0x140049949  call    cs:__imp_FltReleaseFileNameInformation
0x140049950  nop     dword ptr [rax+rax+00h]
0x140049955  jmp     loc_14004985F
0x14004995a  xor     eax, eax
0x14004995c  lea     rcx, [rbp+60h+var_A0]; void *
0x140049960  xor     edx, edx; Val
0x140049962  mov     dword ptr [rbp+60h+var_A0+4], eax
0x140049965  lea     r8d, [rax+44h]; Size
0x140049969  call    memset
0x14004996e  mov     rax, [rsp+160h+Context]
0x140049973  xorps   xmm0, xmm0
0x140049976  movups  [rbp+60h+var_B0], xmm0
0x14004997a  cmp     dword ptr [rax], 32497348h
0x140049980  jz      loc_140049B92
0x140049986  lea     r8, [rsp+160h+FileNameInformation]; FileNameInformation
0x14004998b  mov     edx, 102h; NameOptions
0x140049990  mov     rcx, rdi; CallbackData
0x140049993  call    cs:__imp_FltGetFileNameInformation
0x14004999a  nop     dword ptr [rax+rax+00h]
0x14004999f  mov     ecx, eax
0x1400499a1  mov     ebx, eax
0x1400499a3  call    HsmDbgBreakOnStatus
0x1400499a8  lea     eax, [rbx+3FFFFFCDh]
0x1400499ae  cmp     eax, r13d
0x1400499b1  jbe     loc_140049851
0x1400499b7  cmp     ebx, 0C000003Ah
0x1400499bd  jz      loc_140049851
0x1400499c3  test    ebx, ebx
0x1400499c5  js      loc_140049D27
0x1400499cb  mov     rax, [rsp+160h+FileNameInformation]
0x1400499d0  xorps   xmm0, xmm0
0x1400499d3  add     rax, 8
0x1400499d7  mov     dword ptr [rbp+60h+var_A0], 30h ; '0'
0x1400499de  mov     dl, 2
0x1400499e0  mov     [rbp+60h+var_90], rax
0x1400499e4  mov     [rbp+60h+var_98], rsi
0x1400499e8  mov     [rbp+60h+var_88], 240h
0x1400499ef  movdqa  [rbp+60h+var_80], xmm0
0x1400499f4  call    HsmOsSetPlaceholderCompatMode
0x1400499f9  mov     bl, al
0x1400499fb  mov     [rbp+60h+Parameter], rsi
0x1400499ff  mov     rax, cs:Filter
0x140049a06  lea     rdx, [rbp+60h+Parameter]; Parameter
0x140049a0a  mov     [rsp+160h+var_F0], rax
0x140049a0f  lea     rcx, FltQueryInformationByNameCallout; Callout
0x140049a16  lea     rax, [rbp+60h+var_A0]
0x140049a1a  mov     [rsp+160h+var_E8], r15
0x140049a1f  mov     [rbp+60h+var_E0], rax
0x140049a23  lea     rax, [rbp+60h+var_B0]
0x140049a27  mov     [rbp+60h+var_D8], rax
0x140049a2b  lea     rax, [rbp+60h+var_A0]
0x140049a2f  mov     [rbp+60h+var_D0], rax
0x140049a33  mov     [rbp+60h+var_C8], 48h ; 'H'
0x140049a3a  mov     [rbp+60h+var_C4], 44h ; 'D'
0x140049a41  mov     [rbp+60h+var_C0], rsi
0x140049a45  call    HsmExpandKernelStackAndCallout
0x140049a4a  mov     ecx, eax
0x140049a4c  mov     r13d, eax
0x140049a4f  call    HsmDbgBreakOnStatus
0x140049a54  mov     dl, bl
0x140049a56  call    HsmOsSetPlaceholderCompatMode
0x140049a5b  xor     ecx, ecx
0x140049a5d  test    r13d, r13d
0x140049a60  js      loc_140049C19
0x140049a66  mov     rax, [rsp+160h+Context]
0x140049a6b  cmp     dword ptr [rax], 32497348h
0x140049a71  mov     eax, [rbp+60h+var_64]
0x140049a74  jnz     loc_140049C72
0x140049a7a  and     eax, 0FFFF0FFFh
0x140049a7f  cmp     eax, cs:dword_140029670
0x140049a85  jnz     loc_140049851
0x140049a8b  mov     rax, [rbp+60h+var_A0]
0x140049a8f  xorps   xmm0, xmm0
0x140049a92  movdqu  [rbp+60h+var_48], xmm0
0x140049a97  mov     [rbp+60h+var_50], rax
0x140049a9b  mov     [rsp+160h+var_100], rcx
0x140049aa0  mov     [rsp+160h+NewElement], cl
0x140049aa4  mov     [rsp+160h+var_130], cl
0x140049aa8  mov     [rsp+160h+Buffer], rdi
0x140049aad  call    cs:__imp_KeEnterCriticalRegion
0x140049ab4  nop     dword ptr [rax+rax+00h]
0x140049ab9  mov     rcx, [rsp+160h+Context]
0x140049abe  mov     dl, r12b; Wait
0x140049ac1  add     rcx, 8; Resource
0x140049ac5  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140049acc  nop     dword ptr [rax+rax+00h]
0x140049ad1  mov     rcx, [rsp+160h+Context]
0x140049ad6  lea     r9, [rsp+160h+NewElement]; NewElement
0x140049adb  add     rcx, 70h ; 'p'; Table
0x140049adf  lea     rdx, [rsp+160h+Buffer]; Buffer
0x140049ae4  mov     r8d, 10h; BufferSize
0x140049aea  call    cs:__imp_RtlInsertElementGenericTableAvl
0x140049af1  nop     dword ptr [rax+rax+00h]
0x140049af6  mov     rcx, [rsp+160h+Context]
0x140049afb  lea     r9, [rsp+160h+var_130]; NewElement
0x140049b00  add     rcx, 0D8h; Table
0x140049b07  mov     [rsp+160h+var_118], rax
0x140049b0c  mov     r8d, 18h; BufferSize
0x140049b12  lea     rdx, [rbp+60h+var_50]; Buffer
0x140049b16  call    cs:__imp_RtlInsertElementGenericTableAvl
0x140049b1d  nop     dword ptr [rax+rax+00h]
0x140049b22  mov     rcx, [rsp+160h+var_118]
0x140049b27  mov     rbx, rax
0x140049b2a  test    rcx, rcx
0x140049b2d  jnz     loc_140049D56
0x140049b33  test    rax, rax
0x140049b36  jnz     loc_140049D9A
0x140049b3c  mov     esi, 0C000009Ah
0x140049b41  mov     ecx, esi
0x140049b43  call    HsmDbgBreakOnStatus
0x140049b48  mov     rcx, cs:WPP_GLOBAL_Control
0x140049b4f  lea     rax, WPP_GLOBAL_Control
0x140049b56  cmp     rcx, rax
0x140049b59  jnz     loc_140049DC6
0x140049b5f  mov     rcx, [rsp+160h+Context]
0x140049b64  add     rcx, 8; Resource
0x140049b68  call    cs:__imp_ExReleaseResourceLite
0x140049b6f  nop     dword ptr [rax+rax+00h]
0x140049b74  call    cs:__imp_KeLeaveCriticalRegion
0x140049b7b  nop     dword ptr [rax+rax+00h]
0x140049b80  jmp     loc_140049851
0x140049b85  mov     rcx, r14; P
0x140049b88  call    HsmpCleanupAttributionInformation
0x140049b8d  jmp     loc_140049868
0x140049b92  mov     rax, [rdi+10h]
0x140049b96  mov     [rsp+160h+var_130], sil
0x140049b9b  cmp     [rax+4], sil
0x140049b9f  jnz     loc_140049851
0x140049ba5  mov     rax, [rax+18h]
0x140049ba9  test    rax, rax
0x140049bac  jz      loc_140049851
0x140049bb2  test    dword ptr [rax+10h], 2000027h
0x140049bb9  jz      loc_140049851
0x140049bbf  lea     r9, [rsp+160h+var_118]
0x140049bc4  mov     r8, rdi
0x140049bc7  xor     edx, edx
0x140049bc9  xor     ecx, ecx
0x140049bcb  call    HsmpGetAttributionInformation
0x140049bd0  mov     ecx, eax
0x140049bd2  mov     ebx, eax
0x140049bd4  call    HsmDbgBreakOnStatus
0x140049bd9  test    ebx, ebx
0x140049bdb  js      loc_140049C94
0x140049be1  mov     r14, [rsp+160h+var_118]
0x140049be6  lea     r8, [rsp+160h+var_130]
0x140049beb  mov     rcx, r14
0x140049bee  mov     edx, 3
0x140049bf3  call    HsmOsCheckAppCompatPolicy
0x140049bf8  mov     ecx, eax
0x140049bfa  mov     ebx, eax
0x140049bfc  call    HsmDbgBreakOnStatus
0x140049c01  test    ebx, ebx
0x140049c03  js      loc_140049CE5
0x140049c09  cmp     [rsp+160h+var_130], sil
0x140049c0e  jz      loc_140049851
0x140049c14  jmp     loc_140049986
0x140049c19  mov     rcx, cs:WPP_GLOBAL_Control
0x140049c20  lea     rax, WPP_GLOBAL_Control
0x140049c27  cmp     rcx, rax
0x140049c2a  jz      loc_140049851
0x140049c30  mov     eax, [rcx+2Ch]
0x140049c33  test    r12b, al
0x140049c36  jz      loc_140049851
0x140049c3c  cmp     byte ptr [rcx+29h], 2
0x140049c40  jb      loc_140049851
0x140049c46  mov     edx, 19h
0x140049c4b  mov     [rsp+160h+var_138], r13d
0x140049c50  mov     rax, [rsp+160h+Context]
0x140049c55  lea     r8, WPP_666dd97b4df534fdc194a0db3f3e286d_Traceguids
0x140049c5c  mov     rcx, [rcx+18h]
0x140049c60  mov     r9, r15
0x140049c63  mov     [rsp+160h+var_140], rax
0x140049c68  call    WPP_SF_qqd
0x140049c6d  jmp     loc_140049851
0x140049c72  and     eax, 0FFFF0FFFh
0x140049c77  cmp     eax, cs:dword_140029670
0x140049c7d  jnz     loc_140049851
0x140049c83  mov     esi, 0C019005Ah
0x140049c88  mov     ecx, esi
0x140049c8a  call    HsmDbgBreakOnStatus
0x140049c8f  jmp     loc_140049851
0x140049c94  mov     rcx, cs:WPP_GLOBAL_Control
0x140049c9b  lea     rax, WPP_GLOBAL_Control
0x140049ca2  cmp     rcx, rax
0x140049ca5  jz      short loc_140049CDB
0x140049ca7  mov     eax, [rcx+2Ch]
  ... truncated ...
```
