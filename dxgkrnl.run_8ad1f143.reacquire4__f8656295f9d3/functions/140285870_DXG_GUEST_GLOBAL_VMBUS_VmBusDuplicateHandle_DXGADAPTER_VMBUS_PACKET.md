# DXG_GUEST_GLOBAL_VMBUS::VmBusDuplicateHandle(DXGADAPTER_VMBUS_PACKET *)

- ea: `0x140285870`
- end: `0x140285cd6`
- name: `?VmBusDuplicateHandle@DXG_GUEST_GLOBAL_VMBUS@@SAEPEAUDXGADAPTER_VMBUS_PACKET@@@Z`
- size: `1126`
- prototype: `unsigned __int8 __fastcall(struct DXGADAPTER_VMBUS_PACKET *)`
- caller_count: `0`
- callee_count: `13`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callees

- `0x140012380`
- `0x140015780`
- `0x140015a00`
- `0x14001b890`
- `0x14001f460`
- `0x14002ec90`
- `0x140062450`
- `0x1400a0100`
- `0x14023f40c`
- `0x14027f4c8`
- `0x140285870`
- `0x14028c8b8`
- `0x14035f150`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140285c7b`
- `ntoskrnl!ObfDereferenceObject` at `0x140285c8f`
- `ntoskrnl!ObfDereferenceObject` at `0x140285c7b`
- `ntoskrnl!ObfDereferenceObject` at `0x140285c8f`
- `ntoskrnl!ZwClose` at `0x140285a40`
- `ntoskrnl!ZwClose` at `0x140285a40`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140285b66`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140285b66`
- `ntoskrnl!KeStackAttachProcess` at `0x140285b28`
- `ntoskrnl!KeStackAttachProcess` at `0x140285b28`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140285a27`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140285a27`
- `ntoskrnl!ObCloseHandle` at `0x140285c65`
- `ntoskrnl!ObCloseHandle` at `0x140285c65`
- `ntoskrnl!PsProcessType` at `0x1402859ff`
- `ntoskrnl!ObInsertObject` at `0x140285b51`
- `ntoskrnl!ObInsertObject` at `0x140285b51`
- `ntoskrnl!ZwOpenProcess` at `0x1402859a6`
- `ntoskrnl!ZwOpenProcess` at `0x1402859a6`
- `watchdog!WdLogSingleEntry2` at `0x1402859c5`
- `watchdog!WdLogSingleEntry2` at `0x140285a5c`
- `watchdog!WdLogSingleEntry2` at `0x1402859c5`
- `watchdog!WdLogSingleEntry2` at `0x140285a5c`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1402858ec`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x140285937`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1402858ec`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x140285937`
- `watchdog!WdLogSingleEntry0` at `0x140285ab5`
- `watchdog!WdLogSingleEntry0` at `0x140285b7b`
- `watchdog!WdLogSingleEntry0` at `0x140285ab5`
- `watchdog!WdLogSingleEntry0` at `0x140285b7b`

## string_xrefs

- `0x1402859d6`: `Failed to open process handle for process id 0x%I64x, Status=0x%.8x`
- `0x140285b8c`: `Failed to create nt handle in guest process`
- `0x140285ac6`: `Failed to create shared resource for guest`

## pseudocode

```c
unsigned __int8 __fastcall DXG_GUEST_GLOBAL_VMBUS::VmBusDuplicateHandle(struct DXGADAPTER_VMBUS_PACKET *a1)
{
  __int64 v1; // rsi
  PVOID v2; // r14
  struct _KPROCESS *v3; // r15
  DXGGLOBAL *Global; // rax
  struct ADAPTER_RENDER **v5; // r13
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rdi
  int v9; // ebx
  unsigned __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rax
  NTSTATUS v13; // eax
  NTSTATUS v14; // eax
  struct DXG_VMBUS_CHANNEL_BASE *v15; // rbx
  __int64 v16; // rcx
  void *v17; // rdx
  __int64 v18; // rax
  PVOID Object; // [rsp+50h] [rbp-B0h] BYREF
  void *ProcessHandle; // [rsp+58h] [rbp-A8h] BYREF
  PVOID v22; // [rsp+60h] [rbp-A0h] BYREF
  void *Handle; // [rsp+68h] [rbp-98h] BYREF
  struct _CLIENT_ID ClientId; // [rsp+70h] [rbp-90h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-80h] BYREF
  __int128 v26; // [rsp+B0h] [rbp-50h] BYREF
  int v27; // [rsp+C0h] [rbp-40h]
  struct _KAPC_STATE ApcState; // [rsp+1D0h] [rbp+D0h] BYREF
  _BYTE v29[144]; // [rsp+200h] [rbp+100h] BYREF

  v1 = *((_QWORD *)a1 + 17);
  Handle = 0;
  v2 = 0;
  v22 = 0;
  v3 = 0;
  Object = 0;
  Global = DXGGLOBAL::GetGlobal();
  v5 = (struct ADAPTER_RENDER **)DXGGLOBAL::ReferenceAdapterByHostLuid(
                                   Global,
                                   *(struct _LUID *)(v1 + 24),
                                   (unsigned __int64 *)&Object);
  COREADAPTERACCESS::COREADAPTERACCESS((COREADAPTERACCESS *)v29, (struct DXGADAPTER *const)v5, 0);
  if ( !v5 )
  {
    v7 = WdLogNewEntry5_WdTrace(v6);
    *(_QWORD *)(v7 + 24) = *(int *)(v1 + 28);
    *(_QWORD *)(v7 + 32) = *(unsigned int *)(v1 + 24);
    WdLogGlobalForLineNumber = 14872;
LABEL_3:
    LODWORD(v8) = -1073741811;
    goto LABEL_14;
  }
  v9 = COREADAPTERACCESS::AcquireShared((COREADAPTERACCESS *)v29, 0);
  DXGADAPTER::ReleaseReference((DXGADAPTER *)v5, v10);
  if ( v9 < 0 )
  {
    v12 = WdLogNewEntry5_WdTrace(v11);
    *(_QWORD *)(v12 + 24) = *(int *)(v1 + 28);
    *(_QWORD *)(v12 + 32) = *(unsigned int *)(v1 + 24);
    WdLogGlobalForLineNumber = 14886;
    goto LABEL_3;
  }
  ClientId.UniqueProcess = *(HANDLE *)(v1 + 40);
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ClientId.UniqueThread = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  ProcessHandle = 0;
  v13 = ZwOpenProcess(&ProcessHandle, 0x2000000u, &ObjectAttributes, &ClientId);
  v8 = v13;
  if ( v13 >= 0 )
  {
    Object = 0;
    v14 = ObReferenceObjectByHandle(ProcessHandle, 0, (POBJECT_TYPE)PsProcessType, 0, &Object, 0);
    v3 = (struct _KPROCESS *)Object;
    v8 = v14;
    ZwClose(ProcessHandle);
    if ( (int)v8 >= 0 )
    {
      LODWORD(v8) = DxgkpCreateSharedObjectFromHostDesc(
                      v5[405],
                      (const unsigned __int8 *)v1,
                      (struct _DXGSHAREDALLOCOBJECT **)&v22);
      if ( (int)v8 >= 0 )
      {
        memset(&ApcState, 0, sizeof(ApcState));
        KeStackAttachProcess(v3, &ApcState);
        LODWORD(v8) = ObInsertObject(v22, 0, *(_DWORD *)(v1 + 48), 0, 0, &Handle);
        KeUnstackDetachProcess(&ApcState);
        if ( (int)v8 < 0 )
        {
          WdLogSingleEntry0(2);
          WdLogGlobalForLineNumber = 14959;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"Failed to create nt handle in guest process",
            14959,
            0,
            0,
            0,
            0);
        }
      }
      else
      {
        WdLogSingleEntry0(2);
        WdLogGlobalForLineNumber = 14927;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"Failed to create shared resource for guest",
          14927,
          0,
          0,
          0,
          0);
        v2 = v22;
      }
    }
    else
    {
      WdLogSingleEntry2(2, *(_QWORD *)(v1 + 40));
      WdLogGlobalForLineNumber = 14919;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Failed to reference process by handle for process id 0x%I64x, Status=0x%.8x",
        *(_QWORD *)(v1 + 40),
        v8,
        0,
        0,
        0);
    }
  }
  else
  {
    WdLogSingleEntry2(2, *(_QWORD *)(v1 + 40));
    WdLogGlobalForLineNumber = 14910;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Failed to open process handle for process id 0x%I64x, Status=0x%.8x",
      *(_QWORD *)(v1 + 40),
      v8,
      0,
      0,
      0);
  }
LABEL_14:
  while ( 1 )
  {
    v15 = (struct DXG_VMBUS_CHANNEL_BASE *)*((_QWORD *)DXGGLOBAL::GetGlobal() + 212);
    v26 = 0;
    v27 = 0;
    DXGVMBUSMESSAGE::InitializeMessage((DXGVMBUSMESSAGE *)&v26, v15, 0x38u, 0, 0, 0);
    v16 = v26;
    if ( (_QWORD)v26 )
      break;
    LODWORD(v8) = -1073741801;
    DXGVMBUSMESSAGE::~DXGVMBUSMESSAGE((DXGVMBUSMESSAGE *)&v26);
  }
  v17 = Handle;
  v18 = *(_QWORD *)(v1 + 32);
  *(_BYTE *)(v26 + 12) = 1;
  *(_DWORD *)(v16 + 12) &= 0x1FFu;
  *(_QWORD *)(v16 + 48) = v17;
  *(_QWORD *)(v16 + 32) = v18;
  *(_QWORD *)v16 = 0;
  *(_DWORD *)(v16 + 8) = 0;
  *(_QWORD *)(v16 + 16) = 1011;
  *(_DWORD *)(v16 + 24) = v8;
  *(_DWORD *)(v16 + 40) = 8;
  if ( (int)DXG_GUEST_GLOBAL_VMBUS::VmBusSendCompleteTransaction(v15, (struct DXGVMBUSMESSAGE *)&v26) < 0 || (int)v8 < 0 )
  {
    if ( Handle )
    {
      ObCloseHandle(Handle, 1);
    }
    else if ( v2 )
    {
      ObfDereferenceObject(v2);
    }
  }
  if ( v3 )
    ObfDereferenceObject(v3);
  DXGVMBUSMESSAGE::~DXGVMBUSMESSAGE((DXGVMBUSMESSAGE *)&v26);
  COREADAPTERACCESS::~COREADAPTERACCESS((COREADAPTERACCESS *)v29);
  return 0;
}

```

## disassembly

```asm
0x140285870  push    rbp
0x140285872  push    rbx
0x140285873  push    rsi
0x140285874  push    rdi
0x140285875  push    r12
0x140285877  push    r13
0x140285879  push    r14
0x14028587b  push    r15
0x14028587d  lea     rbp, [rsp-1A8h]
0x140285885  sub     rsp, 2A8h
0x14028588c  mov     rax, cs:__security_cookie
0x140285893  xor     rax, rsp
0x140285896  mov     [rbp+1E0h+var_50], rax
0x14028589d  mov     rsi, [rcx+88h]
0x1402858a4  xor     r12d, r12d
0x1402858a7  mov     [rsp+2E0h+Handle], r12
0x1402858ac  mov     r14d, r12d
0x1402858af  mov     [rsp+2E0h+var_280], r12
0x1402858b4  mov     r15d, r12d
0x1402858b7  mov     [rsp+2E0h+var_290], r12
0x1402858bc  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x1402858c1  mov     rdx, [rsi+18h]; struct _LUID
0x1402858c5  lea     r8, [rsp+2E0h+var_290]; unsigned __int64 *
0x1402858ca  mov     rcx, rax; this
0x1402858cd  call    ?ReferenceAdapterByHostLuid@DXGGLOBAL@@QEAAPEAVDXGADAPTER@@U_LUID@@PEA_K@Z; DXGGLOBAL::ReferenceAdapterByHostLuid(_LUID,unsigned __int64 *)
0x1402858d2  xor     r8d, r8d; struct DXGADAPTER *
0x1402858d5  lea     rcx, [rbp+1E0h+var_E0]; this
0x1402858dc  mov     rdx, rax; struct DXGADAPTER *
0x1402858df  mov     r13, rax
0x1402858e2  call    ??0COREADAPTERACCESS@@QEAA@QEAVDXGADAPTER@@0@Z; COREADAPTERACCESS::COREADAPTERACCESS(DXGADAPTER * const,DXGADAPTER * const)
0x1402858e7  test    r13, r13
0x1402858ea  jnz     short loc_14028591B
0x1402858ec  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1402858f3  nop     dword ptr [rax+rax+00h]
0x1402858f8  movsxd  rcx, dword ptr [rsi+1Ch]
0x1402858fc  mov     [rax+18h], rcx
0x140285900  mov     ecx, [rsi+18h]
0x140285903  mov     [rax+20h], rcx
0x140285907  mov     cs:WdLogGlobalForLineNumber, 3A18h
0x140285911  mov     edi, 0C000000Dh
0x140285916  jmp     loc_140285BC2
0x14028591b  xor     edx, edx; char *
0x14028591d  lea     rcx, [rbp+1E0h+var_E0]; this
0x140285924  call    ?AcquireShared@COREADAPTERACCESS@@QEAAJPEBD@Z; COREADAPTERACCESS::AcquireShared(char const *)
0x140285929  mov     rcx, r13; this
0x14028592c  mov     ebx, eax
0x14028592e  call    ?ReleaseReference@DXGADAPTER@@QEAAX_K@Z; DXGADAPTER::ReleaseReference(unsigned __int64)
0x140285933  test    ebx, ebx
0x140285935  jns     short loc_14028595E
0x140285937  call    cs:__imp_WdLogNewEntry5_WdTrace
0x14028593e  nop     dword ptr [rax+rax+00h]
0x140285943  movsxd  rcx, dword ptr [rsi+1Ch]
0x140285947  mov     [rax+18h], rcx
0x14028594b  mov     ecx, [rsi+18h]
0x14028594e  mov     [rax+20h], rcx
0x140285952  mov     cs:WdLogGlobalForLineNumber, 3A26h
0x14028595c  jmp     short loc_140285911
0x14028595e  mov     rax, [rsi+28h]
0x140285962  lea     r9, [rsp+2E0h+ClientId]; ClientId
0x140285967  mov     [rsp+2E0h+ClientId.UniqueProcess], rax
0x14028596c  lea     r8, [rbp+1E0h+ObjectAttributes]; ObjectAttributes
0x140285970  xor     eax, eax
0x140285972  mov     qword ptr [rbp+1E0h+ObjectAttributes.Length], 30h ; '0'
0x14028597a  xorps   xmm0, xmm0
0x14028597d  mov     [rsp+2E0h+ClientId.UniqueThread], rax
0x140285982  mov     edx, 2000000h; DesiredAccess
0x140285987  mov     qword ptr [rbp+1E0h+ObjectAttributes.Attributes], 240h
0x14028598f  lea     rcx, [rsp+2E0h+ProcessHandle]; ProcessHandle
0x140285994  mov     [rbp+1E0h+ObjectAttributes.RootDirectory], r12
0x140285998  mov     [rbp+1E0h+ObjectAttributes.ObjectName], r12
0x14028599c  movdqu  xmmword ptr [rbp+1E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1402859a1  mov     [rsp+2E0h+ProcessHandle], r12
0x1402859a6  call    cs:__imp_ZwOpenProcess
0x1402859ad  nop     dword ptr [rax+rax+00h]
0x1402859b2  movsxd  rdi, eax
0x1402859b5  test    eax, eax
0x1402859b7  jns     short loc_1402859FF
0x1402859b9  mov     rdx, [rsi+28h]
0x1402859bd  mov     r8, rdi
0x1402859c0  mov     ecx, 2
0x1402859c5  call    cs:__imp_WdLogSingleEntry2
0x1402859cc  nop     dword ptr [rax+rax+00h]
0x1402859d1  mov     [rsp+2E0h+var_2A0], r12
0x1402859d6  lea     r9, aFailedToOpenPr; "Failed to open process handle for proce"...
0x1402859dd  mov     [rsp+2E0h+var_2A8], r12
0x1402859e2  mov     [rsp+2E0h+var_2B0], r12
0x1402859e7  mov     cs:WdLogGlobalForLineNumber, 3A3Eh
0x1402859f1  mov     rax, [rsi+28h]
0x1402859f5  mov     [rsp+2E0h+HandleInformation], rdi
0x1402859fa  jmp     loc_140285BAD
0x1402859ff  mov     r8, cs:__imp_PsProcessType
0x140285a06  lea     rax, [rsp+2E0h+var_290]
0x140285a0b  mov     rcx, [rsp+2E0h+ProcessHandle]; Handle
0x140285a10  xor     r9d, r9d; AccessMode
0x140285a13  mov     [rsp+2E0h+HandleInformation], r12; HandleInformation
0x140285a18  xor     edx, edx; DesiredAccess
0x140285a1a  mov     [rsp+2E0h+var_290], r12
0x140285a1f  mov     r8, [r8]; ObjectType
0x140285a22  mov     [rsp+2E0h+Object], rax; Object
0x140285a27  call    cs:__imp_ObReferenceObjectByHandle
0x140285a2e  nop     dword ptr [rax+rax+00h]
0x140285a33  mov     rcx, [rsp+2E0h+ProcessHandle]; Handle
0x140285a38  mov     r15, [rsp+2E0h+var_290]
0x140285a3d  movsxd  rdi, eax
0x140285a40  call    cs:__imp_ZwClose
0x140285a47  nop     dword ptr [rax+rax+00h]
0x140285a4c  test    edi, edi
0x140285a4e  jns     short loc_140285A96
0x140285a50  mov     rdx, [rsi+28h]
0x140285a54  mov     r8, rdi
0x140285a57  mov     ecx, 2
0x140285a5c  call    cs:__imp_WdLogSingleEntry2
0x140285a63  nop     dword ptr [rax+rax+00h]
0x140285a68  mov     [rsp+2E0h+var_2A0], r12
0x140285a6d  lea     r9, aFailedToRefere_2; "Failed to reference process by handle f"...
0x140285a74  mov     [rsp+2E0h+var_2A8], r12
0x140285a79  mov     [rsp+2E0h+var_2B0], r12
0x140285a7e  mov     cs:WdLogGlobalForLineNumber, 3A47h
0x140285a88  mov     rax, [rsi+28h]
0x140285a8c  mov     [rsp+2E0h+HandleInformation], rdi
0x140285a91  jmp     loc_140285BAD
0x140285a96  mov     rcx, [r13+0CA8h]; struct ADAPTER_RENDER *
0x140285a9d  lea     r8, [rsp+2E0h+var_280]; struct _DXGSHAREDALLOCOBJECT **
0x140285aa2  mov     rdx, rsi; unsigned __int8 *
0x140285aa5  call    ?DxgkpCreateSharedObjectFromHostDesc@@YAJPEAVADAPTER_RENDER@@PEBEPEAPEAU_DXGSHAREDALLOCOBJECT@@@Z; DxgkpCreateSharedObjectFromHostDesc(ADAPTER_RENDER *,uchar const *,_DXGSHAREDALLOCOBJECT * *)
0x140285aaa  mov     edi, eax
0x140285aac  test    eax, eax
0x140285aae  jns     short loc_140285B06
0x140285ab0  mov     ecx, 2
0x140285ab5  call    cs:__imp_WdLogSingleEntry0
0x140285abc  nop     dword ptr [rax+rax+00h]
0x140285ac1  mov     [rsp+2E0h+var_2A0], r12
0x140285ac6  lea     r9, aFailedToCreate_17; "Failed to create shared resource for gu"...
0x140285acd  mov     [rsp+2E0h+var_2A8], r12
0x140285ad2  mov     eax, 3A4Fh
0x140285ad7  mov     [rsp+2E0h+var_2B0], r12
0x140285adc  or      r8d, 0FFFFFFFFh
0x140285ae0  mov     [rsp+2E0h+HandleInformation], r12
0x140285ae5  mov     edx, 40000h
0x140285aea  xor     ecx, ecx
0x140285aec  mov     [rsp+2E0h+Object], rax
0x140285af1  mov     cs:WdLogGlobalForLineNumber, eax
0x140285af7  call    DxgkLogInternalTriageEvent
0x140285afc  mov     r14, [rsp+2E0h+var_280]
0x140285b01  jmp     loc_140285BC2
0x140285b06  xorps   xmm0, xmm0
0x140285b09  lea     rdx, [rbp+1E0h+ApcState]; ApcState
0x140285b10  mov     rcx, r15; PROCESS
0x140285b13  movups  xmmword ptr [rbp+1E0h+ApcState.ApcListHead.Flink], xmm0
0x140285b1a  movups  xmmword ptr [rbp+1E0h+ApcState.ApcListHead.Flink+10h], xmm0
0x140285b21  movups  xmmword ptr [rbp+1E0h+ApcState.Process], xmm0
0x140285b28  call    cs:__imp_KeStackAttachProcess
0x140285b2f  nop     dword ptr [rax+rax+00h]
0x140285b34  mov     r8d, [rsi+30h]; DesiredAccess
0x140285b38  lea     rax, [rsp+2E0h+Handle]
0x140285b3d  mov     rcx, [rsp+2E0h+var_280]; Object
0x140285b42  xor     r9d, r9d; ObjectPointerBias
0x140285b45  mov     [rsp+2E0h+HandleInformation], rax; Handle
0x140285b4a  xor     edx, edx; PassedAccessState
0x140285b4c  mov     [rsp+2E0h+Object], r12; NewObject
0x140285b51  call    cs:__imp_ObInsertObject
0x140285b58  nop     dword ptr [rax+rax+00h]
0x140285b5d  lea     rcx, [rbp+1E0h+ApcState]; ApcState
0x140285b64  mov     edi, eax
0x140285b66  call    cs:__imp_KeUnstackDetachProcess
0x140285b6d  nop     dword ptr [rax+rax+00h]
0x140285b72  test    edi, edi
0x140285b74  jns     short loc_140285BC2
0x140285b76  mov     ecx, 2
0x140285b7b  call    cs:__imp_WdLogSingleEntry0
0x140285b82  nop     dword ptr [rax+rax+00h]
0x140285b87  mov     [rsp+2E0h+var_2A0], r12
0x140285b8c  lea     r9, aFailedToCreate_49; "Failed to create nt handle in guest pro"...
0x140285b93  mov     [rsp+2E0h+var_2A8], r12
0x140285b98  mov     eax, 3A6Fh
0x140285b9d  mov     [rsp+2E0h+var_2B0], r12
0x140285ba2  mov     cs:WdLogGlobalForLineNumber, eax
0x140285ba8  mov     [rsp+2E0h+HandleInformation], r12
0x140285bad  or      r8d, 0FFFFFFFFh
0x140285bb1  mov     [rsp+2E0h+Object], rax
0x140285bb6  mov     edx, 40000h
0x140285bbb  xor     ecx, ecx
0x140285bbd  call    DxgkLogInternalTriageEvent
0x140285bc2  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x140285bc7  xor     r9d, r9d; unsigned int *
0x140285bca  mov     [rsp+2E0h+HandleInformation], r12; unsigned int *
0x140285bcf  xorps   xmm0, xmm0
0x140285bd2  mov     [rsp+2E0h+Object], r12; unsigned int *
0x140285bd7  lea     rcx, [rbp+1E0h+var_230]; this
0x140285bdb  mov     rbx, [rax+6A0h]
0x140285be2  lea     r8d, [r9+38h]; unsigned int
0x140285be6  movdqa  [rbp+1E0h+var_230], xmm0
0x140285beb  mov     rdx, rbx; struct DXG_VMBUS_CHANNEL_BASE *
0x140285bee  mov     [rbp+1E0h+var_220], r12d
0x140285bf2  call    ?InitializeMessage@DXGVMBUSMESSAGE@@QEAAXPEAUDXG_VMBUS_CHANNEL_BASE@@IPEAI11@Z; DXGVMBUSMESSAGE::InitializeMessage(DXG_VMBUS_CHANNEL_BASE *,uint,uint *,uint *,uint *)
0x140285bf7  mov     rcx, qword ptr [rbp+1E0h+var_230]
0x140285bfb  test    rcx, rcx
0x140285bfe  jnz     short loc_140285C10
0x140285c00  lea     rcx, [rbp+1E0h+var_230]; this
0x140285c04  mov     edi, 0C0000017h
0x140285c09  call    ??1DXGVMBUSMESSAGE@@QEAA@XZ; DXGVMBUSMESSAGE::~DXGVMBUSMESSAGE(void)
0x140285c0e  jmp     short loc_140285BC2
0x140285c10  mov     rdx, [rsp+2E0h+Handle]
0x140285c15  mov     rax, [rsi+20h]
0x140285c19  mov     byte ptr [rcx+0Ch], 1
0x140285c1d  and     dword ptr [rcx+0Ch], 1FFh
0x140285c24  mov     [rcx+30h], rdx
0x140285c28  lea     rdx, [rbp+1E0h+var_230]; struct DXGVMBUSMESSAGE *
0x140285c2c  mov     [rcx+20h], rax
0x140285c30  mov     [rcx], r12
0x140285c33  mov     [rcx+8], r12d
0x140285c37  mov     qword ptr [rcx+10h], 3F3h
0x140285c3f  mov     [rcx+18h], edi
0x140285c42  mov     dword ptr [rcx+28h], 8
0x140285c49  mov     rcx, rbx; this
0x140285c4c  call    ?VmBusSendCompleteTransaction@DXG_GUEST_GLOBAL_VMBUS@@QEAAJPEAUDXGVMBUSMESSAGE@@@Z; DXG_GUEST_GLOBAL_VMBUS::VmBusSendCompleteTransaction(DXGVMBUSMESSAGE *)
0x140285c51  test    eax, eax
0x140285c53  js      short loc_140285C59
0x140285c55  test    edi, edi
0x140285c57  jns     short loc_140285C87
0x140285c59  mov     rcx, [rsp+2E0h+Handle]; Handle
0x140285c5e  test    rcx, rcx
0x140285c61  jz      short loc_140285C73
0x140285c63  mov     dl, 1; PreviousMode
0x140285c65  call    cs:__imp_ObCloseHandle
0x140285c6c  nop     dword ptr [rax+rax+00h]
0x140285c71  jmp     short loc_140285C87
0x140285c73  test    r14, r14
0x140285c76  jz      short loc_140285C87
0x140285c78  mov     rcx, r14; Object
0x140285c7b  call    cs:__imp_ObfDereferenceObject
0x140285c82  nop     dword ptr [rax+rax+00h]
0x140285c87  test    r15, r15
0x140285c8a  jz      short loc_140285C9B
0x140285c8c  mov     rcx, r15; Object
0x140285c8f  call    cs:__imp_ObfDereferenceObject
0x140285c96  nop     dword ptr [rax+rax+00h]
0x140285c9b  lea     rcx, [rbp+1E0h+var_230]; this
0x140285c9f  call    ??1DXGVMBUSMESSAGE@@QEAA@XZ; DXGVMBUSMESSAGE::~DXGVMBUSMESSAGE(void)
0x140285ca4  lea     rcx, [rbp+1E0h+var_E0]; this
0x140285cab  call    ??1COREADAPTERACCESS@@QEAA@XZ; COREADAPTERACCESS::~COREADAPTERACCESS(void)
0x140285cb0  xor     al, al
0x140285cb2  mov     rcx, [rbp+1E0h+var_50]
0x140285cb9  xor     rcx, rsp; StackCookie
0x140285cbc  call    __security_check_cookie
0x140285cc1  add     rsp, 2A8h
0x140285cc8  pop     r15
0x140285cca  pop     r14
0x140285ccc  pop     r13
0x140285cce  pop     r12
0x140285cd0  pop     rdi
0x140285cd1  pop     rsi
0x140285cd2  pop     rbx
0x140285cd3  pop     rbp
0x140285cd4  retn
```
