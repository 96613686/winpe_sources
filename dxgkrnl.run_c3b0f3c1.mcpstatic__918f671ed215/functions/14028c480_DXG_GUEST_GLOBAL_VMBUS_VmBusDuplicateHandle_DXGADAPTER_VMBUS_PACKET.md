# DXG_GUEST_GLOBAL_VMBUS::VmBusDuplicateHandle(DXGADAPTER_VMBUS_PACKET *)

- ea: `0x14028c480`
- end: `0x14028c8e6`
- name: `?VmBusDuplicateHandle@DXG_GUEST_GLOBAL_VMBUS@@SAEPEAUDXGADAPTER_VMBUS_PACKET@@@Z`
- size: `1126`
- prototype: `unsigned __int8 __fastcall(struct DXGADAPTER_VMBUS_PACKET *)`
- caller_count: `0`
- callee_count: `13`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callees

- `0x140012540`
- `0x140015940`
- `0x140015bc0`
- `0x14001b9c0`
- `0x14001f630`
- `0x14002ee60`
- `0x140062800`
- `0x1400a0bd0`
- `0x140241f6c`
- `0x1402860d8`
- `0x14028c480`
- `0x140293218`
- `0x14035f600`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14028c88b`
- `ntoskrnl!ObfDereferenceObject` at `0x14028c89f`
- `ntoskrnl!ObfDereferenceObject` at `0x14028c88b`
- `ntoskrnl!ObfDereferenceObject` at `0x14028c89f`
- `ntoskrnl!ZwClose` at `0x14028c650`
- `ntoskrnl!ZwClose` at `0x14028c650`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14028c776`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14028c776`
- `ntoskrnl!KeStackAttachProcess` at `0x14028c738`
- `ntoskrnl!KeStackAttachProcess` at `0x14028c738`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14028c637`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14028c637`
- `ntoskrnl!ObCloseHandle` at `0x14028c875`
- `ntoskrnl!ObCloseHandle` at `0x14028c875`
- `ntoskrnl!PsProcessType` at `0x14028c60f`
- `ntoskrnl!ObInsertObject` at `0x14028c761`
- `ntoskrnl!ObInsertObject` at `0x14028c761`
- `ntoskrnl!ZwOpenProcess` at `0x14028c5b6`
- `ntoskrnl!ZwOpenProcess` at `0x14028c5b6`
- `watchdog!WdLogSingleEntry2` at `0x14028c5d5`
- `watchdog!WdLogSingleEntry2` at `0x14028c66c`
- `watchdog!WdLogSingleEntry2` at `0x14028c5d5`
- `watchdog!WdLogSingleEntry2` at `0x14028c66c`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14028c4fc`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14028c547`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14028c4fc`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14028c547`
- `watchdog!WdLogSingleEntry0` at `0x14028c6c5`
- `watchdog!WdLogSingleEntry0` at `0x14028c78b`
- `watchdog!WdLogSingleEntry0` at `0x14028c6c5`
- `watchdog!WdLogSingleEntry0` at `0x14028c78b`

## string_xrefs

- `0x14028c5e6`: `Failed to open process handle for process id 0x%I64x, Status=0x%.8x`
- `0x14028c79c`: `Failed to create nt handle in guest process`
- `0x14028c6d6`: `Failed to create shared resource for guest`

## pseudocode

```c
unsigned __int8 __fastcall DXG_GUEST_GLOBAL_VMBUS::VmBusDuplicateHandle(struct DXGADAPTER_VMBUS_PACKET *a1)
{
  __int64 v1; // rsi
  PVOID v2; // r14
  struct _KPROCESS *v3; // r15
  DXGGLOBAL *Global; // rax
  struct ADAPTER_RENDER **v5; // r13
  __int64 v6; // rax
  __int64 v7; // rdi
  int v8; // ebx
  unsigned __int64 v9; // rdx
  __int64 v10; // rax
  NTSTATUS v11; // eax
  NTSTATUS v12; // eax
  struct DXG_VMBUS_CHANNEL_BASE *v13; // rbx
  __int64 v14; // rcx
  void *v15; // rdx
  __int64 v16; // rax
  PVOID Object; // [rsp+50h] [rbp-B0h] BYREF
  void *ProcessHandle; // [rsp+58h] [rbp-A8h] BYREF
  PVOID v20; // [rsp+60h] [rbp-A0h] BYREF
  void *Handle; // [rsp+68h] [rbp-98h] BYREF
  struct _CLIENT_ID ClientId; // [rsp+70h] [rbp-90h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-80h] BYREF
  __int128 v24; // [rsp+B0h] [rbp-50h] BYREF
  int v25; // [rsp+C0h] [rbp-40h]
  struct _KAPC_STATE ApcState; // [rsp+1D0h] [rbp+D0h] BYREF
  _BYTE v27[144]; // [rsp+200h] [rbp+100h] BYREF

  v1 = *((_QWORD *)a1 + 17);
  Handle = 0;
  v2 = 0;
  v20 = 0;
  v3 = 0;
  Object = 0;
  Global = DXGGLOBAL::GetGlobal();
  v5 = (struct ADAPTER_RENDER **)DXGGLOBAL::ReferenceAdapterByHostLuid(
                                   Global,
                                   *(struct _LUID *)(v1 + 24),
                                   (unsigned __int64 *)&Object);
  COREADAPTERACCESS::COREADAPTERACCESS((COREADAPTERACCESS *)v27, (struct DXGADAPTER *const)v5, 0);
  if ( !v5 )
  {
    v6 = WdLogNewEntry5_WdTrace();
    *(_QWORD *)(v6 + 24) = *(int *)(v1 + 28);
    *(_QWORD *)(v6 + 32) = *(unsigned int *)(v1 + 24);
    WdLogGlobalForLineNumber = 14870;
LABEL_3:
    LODWORD(v7) = -1073741811;
    goto LABEL_14;
  }
  v8 = COREADAPTERACCESS::AcquireShared((COREADAPTERACCESS *)v27, 0);
  DXGADAPTER::ReleaseReference((DXGADAPTER *)v5, v9);
  if ( v8 < 0 )
  {
    v10 = WdLogNewEntry5_WdTrace();
    *(_QWORD *)(v10 + 24) = *(int *)(v1 + 28);
    *(_QWORD *)(v10 + 32) = *(unsigned int *)(v1 + 24);
    WdLogGlobalForLineNumber = 14884;
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
  v11 = ZwOpenProcess(&ProcessHandle, 0x2000000u, &ObjectAttributes, &ClientId);
  v7 = v11;
  if ( v11 >= 0 )
  {
    Object = 0;
    v12 = ObReferenceObjectByHandle(ProcessHandle, 0, (POBJECT_TYPE)PsProcessType, 0, &Object, 0);
    v3 = (struct _KPROCESS *)Object;
    v7 = v12;
    ZwClose(ProcessHandle);
    if ( (int)v7 >= 0 )
    {
      LODWORD(v7) = DxgkpCreateSharedObjectFromHostDesc(
                      v5[407],
                      (const unsigned __int8 *)v1,
                      (struct _DXGSHAREDALLOCOBJECT **)&v20);
      if ( (int)v7 >= 0 )
      {
        memset(&ApcState, 0, sizeof(ApcState));
        KeStackAttachProcess(v3, &ApcState);
        LODWORD(v7) = ObInsertObject(v20, 0, *(_DWORD *)(v1 + 48), 0, 0, &Handle);
        KeUnstackDetachProcess(&ApcState);
        if ( (int)v7 < 0 )
        {
          WdLogSingleEntry0(2);
          WdLogGlobalForLineNumber = 14957;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"Failed to create nt handle in guest process",
            14957,
            0,
            0,
            0,
            0);
        }
      }
      else
      {
        WdLogSingleEntry0(2);
        WdLogGlobalForLineNumber = 14925;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"Failed to create shared resource for guest",
          14925,
          0,
          0,
          0,
          0);
        v2 = v20;
      }
    }
    else
    {
      WdLogSingleEntry2(2, *(_QWORD *)(v1 + 40), v7);
      WdLogGlobalForLineNumber = 14917;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Failed to reference process by handle for process id 0x%I64x, Status=0x%.8x",
        *(_QWORD *)(v1 + 40),
        v7,
        0,
        0,
        0);
    }
  }
  else
  {
    WdLogSingleEntry2(2, *(_QWORD *)(v1 + 40), v11);
    WdLogGlobalForLineNumber = 14908;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Failed to open process handle for process id 0x%I64x, Status=0x%.8x",
      *(_QWORD *)(v1 + 40),
      v7,
      0,
      0,
      0);
  }
LABEL_14:
  while ( 1 )
  {
    v13 = (struct DXG_VMBUS_CHANNEL_BASE *)*((_QWORD *)DXGGLOBAL::GetGlobal() + 212);
    v24 = 0;
    v25 = 0;
    DXGVMBUSMESSAGE::InitializeMessage((DXGVMBUSMESSAGE *)&v24, v13, 0x38u, 0, 0, 0);
    v14 = v24;
    if ( (_QWORD)v24 )
      break;
    LODWORD(v7) = -1073741801;
    DXGVMBUSMESSAGE::~DXGVMBUSMESSAGE((DXGVMBUSMESSAGE *)&v24);
  }
  v15 = Handle;
  v16 = *(_QWORD *)(v1 + 32);
  *(_BYTE *)(v24 + 12) = 1;
  *(_DWORD *)(v14 + 12) &= 0x1FFu;
  *(_QWORD *)(v14 + 48) = v15;
  *(_QWORD *)(v14 + 32) = v16;
  *(_QWORD *)v14 = 0;
  *(_DWORD *)(v14 + 8) = 0;
  *(_QWORD *)(v14 + 16) = 1011;
  *(_DWORD *)(v14 + 24) = v7;
  *(_DWORD *)(v14 + 40) = 8;
  if ( (int)DXG_GUEST_GLOBAL_VMBUS::VmBusSendCompleteTransaction(v13, (struct DXGVMBUSMESSAGE *)&v24) < 0 || (int)v7 < 0 )
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
  DXGVMBUSMESSAGE::~DXGVMBUSMESSAGE((DXGVMBUSMESSAGE *)&v24);
  COREADAPTERACCESS::~COREADAPTERACCESS((COREADAPTERACCESS *)v27);
  return 0;
}

```

## disassembly

```asm
0x14028c480  push    rbp
0x14028c482  push    rbx
0x14028c483  push    rsi
0x14028c484  push    rdi
0x14028c485  push    r12
0x14028c487  push    r13
0x14028c489  push    r14
0x14028c48b  push    r15
0x14028c48d  lea     rbp, [rsp-1A8h]
0x14028c495  sub     rsp, 2A8h
0x14028c49c  mov     rax, cs:__security_cookie
0x14028c4a3  xor     rax, rsp
0x14028c4a6  mov     [rbp+1E0h+var_50], rax
0x14028c4ad  mov     rsi, [rcx+88h]
0x14028c4b4  xor     r12d, r12d
0x14028c4b7  mov     [rsp+2E0h+Handle], r12
0x14028c4bc  mov     r14d, r12d
0x14028c4bf  mov     [rsp+2E0h+var_280], r12
0x14028c4c4  mov     r15d, r12d
0x14028c4c7  mov     [rsp+2E0h+var_290], r12
0x14028c4cc  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x14028c4d1  mov     rdx, [rsi+18h]; struct _LUID
0x14028c4d5  lea     r8, [rsp+2E0h+var_290]; unsigned __int64 *
0x14028c4da  mov     rcx, rax; this
0x14028c4dd  call    ?ReferenceAdapterByHostLuid@DXGGLOBAL@@QEAAPEAVDXGADAPTER@@U_LUID@@PEA_K@Z; DXGGLOBAL::ReferenceAdapterByHostLuid(_LUID,unsigned __int64 *)
0x14028c4e2  xor     r8d, r8d; struct DXGADAPTER *
0x14028c4e5  lea     rcx, [rbp+1E0h+var_E0]; this
0x14028c4ec  mov     rdx, rax; struct DXGADAPTER *
0x14028c4ef  mov     r13, rax
0x14028c4f2  call    ??0COREADAPTERACCESS@@QEAA@QEAVDXGADAPTER@@0@Z; COREADAPTERACCESS::COREADAPTERACCESS(DXGADAPTER * const,DXGADAPTER * const)
0x14028c4f7  test    r13, r13
0x14028c4fa  jnz     short loc_14028C52B
0x14028c4fc  call    cs:__imp_WdLogNewEntry5_WdTrace
0x14028c503  nop     dword ptr [rax+rax+00h]
0x14028c508  movsxd  rcx, dword ptr [rsi+1Ch]
0x14028c50c  mov     [rax+18h], rcx
0x14028c510  mov     ecx, [rsi+18h]
0x14028c513  mov     [rax+20h], rcx
0x14028c517  mov     cs:WdLogGlobalForLineNumber, 3A16h
0x14028c521  mov     edi, 0C000000Dh
0x14028c526  jmp     loc_14028C7D2
0x14028c52b  xor     edx, edx; char *
0x14028c52d  lea     rcx, [rbp+1E0h+var_E0]; this
0x14028c534  call    ?AcquireShared@COREADAPTERACCESS@@QEAAJPEBD@Z; COREADAPTERACCESS::AcquireShared(char const *)
0x14028c539  mov     rcx, r13; this
0x14028c53c  mov     ebx, eax
0x14028c53e  call    ?ReleaseReference@DXGADAPTER@@QEAAX_K@Z; DXGADAPTER::ReleaseReference(unsigned __int64)
0x14028c543  test    ebx, ebx
0x14028c545  jns     short loc_14028C56E
0x14028c547  call    cs:__imp_WdLogNewEntry5_WdTrace
0x14028c54e  nop     dword ptr [rax+rax+00h]
0x14028c553  movsxd  rcx, dword ptr [rsi+1Ch]
0x14028c557  mov     [rax+18h], rcx
0x14028c55b  mov     ecx, [rsi+18h]
0x14028c55e  mov     [rax+20h], rcx
0x14028c562  mov     cs:WdLogGlobalForLineNumber, 3A24h
0x14028c56c  jmp     short loc_14028C521
0x14028c56e  mov     rax, [rsi+28h]
0x14028c572  lea     r9, [rsp+2E0h+ClientId]; ClientId
0x14028c577  mov     [rsp+2E0h+ClientId.UniqueProcess], rax
0x14028c57c  lea     r8, [rbp+1E0h+ObjectAttributes]; ObjectAttributes
0x14028c580  xor     eax, eax
0x14028c582  mov     qword ptr [rbp+1E0h+ObjectAttributes.Length], 30h ; '0'
0x14028c58a  xorps   xmm0, xmm0
0x14028c58d  mov     [rsp+2E0h+ClientId.UniqueThread], rax
0x14028c592  mov     edx, 2000000h; DesiredAccess
0x14028c597  mov     qword ptr [rbp+1E0h+ObjectAttributes.Attributes], 240h
0x14028c59f  lea     rcx, [rsp+2E0h+ProcessHandle]; ProcessHandle
0x14028c5a4  mov     [rbp+1E0h+ObjectAttributes.RootDirectory], r12
0x14028c5a8  mov     [rbp+1E0h+ObjectAttributes.ObjectName], r12
0x14028c5ac  movdqu  xmmword ptr [rbp+1E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x14028c5b1  mov     [rsp+2E0h+ProcessHandle], r12
0x14028c5b6  call    cs:__imp_ZwOpenProcess
0x14028c5bd  nop     dword ptr [rax+rax+00h]
0x14028c5c2  movsxd  rdi, eax
0x14028c5c5  test    eax, eax
0x14028c5c7  jns     short loc_14028C60F
0x14028c5c9  mov     rdx, [rsi+28h]
0x14028c5cd  mov     r8, rdi
0x14028c5d0  mov     ecx, 2
0x14028c5d5  call    cs:__imp_WdLogSingleEntry2
0x14028c5dc  nop     dword ptr [rax+rax+00h]
0x14028c5e1  mov     [rsp+2E0h+var_2A0], r12
0x14028c5e6  lea     r9, aFailedToOpenPr; "Failed to open process handle for proce"...
0x14028c5ed  mov     [rsp+2E0h+var_2A8], r12
0x14028c5f2  mov     [rsp+2E0h+var_2B0], r12
0x14028c5f7  mov     cs:WdLogGlobalForLineNumber, 3A3Ch
0x14028c601  mov     rax, [rsi+28h]
0x14028c605  mov     [rsp+2E0h+HandleInformation], rdi
0x14028c60a  jmp     loc_14028C7BD
0x14028c60f  mov     r8, cs:__imp_PsProcessType
0x14028c616  lea     rax, [rsp+2E0h+var_290]
0x14028c61b  mov     rcx, [rsp+2E0h+ProcessHandle]; Handle
0x14028c620  xor     r9d, r9d; AccessMode
0x14028c623  mov     [rsp+2E0h+HandleInformation], r12; HandleInformation
0x14028c628  xor     edx, edx; DesiredAccess
0x14028c62a  mov     [rsp+2E0h+var_290], r12
0x14028c62f  mov     r8, [r8]; ObjectType
0x14028c632  mov     [rsp+2E0h+Object], rax; Object
0x14028c637  call    cs:__imp_ObReferenceObjectByHandle
0x14028c63e  nop     dword ptr [rax+rax+00h]
0x14028c643  mov     rcx, [rsp+2E0h+ProcessHandle]; Handle
0x14028c648  mov     r15, [rsp+2E0h+var_290]
0x14028c64d  movsxd  rdi, eax
0x14028c650  call    cs:__imp_ZwClose
0x14028c657  nop     dword ptr [rax+rax+00h]
0x14028c65c  test    edi, edi
0x14028c65e  jns     short loc_14028C6A6
0x14028c660  mov     rdx, [rsi+28h]
0x14028c664  mov     r8, rdi
0x14028c667  mov     ecx, 2
0x14028c66c  call    cs:__imp_WdLogSingleEntry2
0x14028c673  nop     dword ptr [rax+rax+00h]
0x14028c678  mov     [rsp+2E0h+var_2A0], r12
0x14028c67d  lea     r9, aFailedToRefere_2; "Failed to reference process by handle f"...
0x14028c684  mov     [rsp+2E0h+var_2A8], r12
0x14028c689  mov     [rsp+2E0h+var_2B0], r12
0x14028c68e  mov     cs:WdLogGlobalForLineNumber, 3A45h
0x14028c698  mov     rax, [rsi+28h]
0x14028c69c  mov     [rsp+2E0h+HandleInformation], rdi
0x14028c6a1  jmp     loc_14028C7BD
0x14028c6a6  mov     rcx, [r13+0CB8h]; struct ADAPTER_RENDER *
0x14028c6ad  lea     r8, [rsp+2E0h+var_280]; struct _DXGSHAREDALLOCOBJECT **
0x14028c6b2  mov     rdx, rsi; unsigned __int8 *
0x14028c6b5  call    ?DxgkpCreateSharedObjectFromHostDesc@@YAJPEAVADAPTER_RENDER@@PEBEPEAPEAU_DXGSHAREDALLOCOBJECT@@@Z; DxgkpCreateSharedObjectFromHostDesc(ADAPTER_RENDER *,uchar const *,_DXGSHAREDALLOCOBJECT * *)
0x14028c6ba  mov     edi, eax
0x14028c6bc  test    eax, eax
0x14028c6be  jns     short loc_14028C716
0x14028c6c0  mov     ecx, 2
0x14028c6c5  call    cs:__imp_WdLogSingleEntry0
0x14028c6cc  nop     dword ptr [rax+rax+00h]
0x14028c6d1  mov     [rsp+2E0h+var_2A0], r12
0x14028c6d6  lea     r9, aFailedToCreate_18; "Failed to create shared resource for gu"...
0x14028c6dd  mov     [rsp+2E0h+var_2A8], r12
0x14028c6e2  mov     eax, 3A4Dh
0x14028c6e7  mov     [rsp+2E0h+var_2B0], r12
0x14028c6ec  or      r8d, 0FFFFFFFFh
0x14028c6f0  mov     [rsp+2E0h+HandleInformation], r12
0x14028c6f5  mov     edx, 40000h
0x14028c6fa  xor     ecx, ecx
0x14028c6fc  mov     [rsp+2E0h+Object], rax
0x14028c701  mov     cs:WdLogGlobalForLineNumber, eax
0x14028c707  call    DxgkLogInternalTriageEvent
0x14028c70c  mov     r14, [rsp+2E0h+var_280]
0x14028c711  jmp     loc_14028C7D2
0x14028c716  xorps   xmm0, xmm0
0x14028c719  lea     rdx, [rbp+1E0h+ApcState]; ApcState
0x14028c720  mov     rcx, r15; PROCESS
0x14028c723  movups  xmmword ptr [rbp+1E0h+ApcState.ApcListHead.Flink], xmm0
0x14028c72a  movups  xmmword ptr [rbp+1E0h+ApcState.ApcListHead.Flink+10h], xmm0
0x14028c731  movups  xmmword ptr [rbp+1E0h+ApcState.Process], xmm0
0x14028c738  call    cs:__imp_KeStackAttachProcess
0x14028c73f  nop     dword ptr [rax+rax+00h]
0x14028c744  mov     r8d, [rsi+30h]; DesiredAccess
0x14028c748  lea     rax, [rsp+2E0h+Handle]
0x14028c74d  mov     rcx, [rsp+2E0h+var_280]; Object
0x14028c752  xor     r9d, r9d; ObjectPointerBias
0x14028c755  mov     [rsp+2E0h+HandleInformation], rax; Handle
0x14028c75a  xor     edx, edx; PassedAccessState
0x14028c75c  mov     [rsp+2E0h+Object], r12; NewObject
0x14028c761  call    cs:__imp_ObInsertObject
0x14028c768  nop     dword ptr [rax+rax+00h]
0x14028c76d  lea     rcx, [rbp+1E0h+ApcState]; ApcState
0x14028c774  mov     edi, eax
0x14028c776  call    cs:__imp_KeUnstackDetachProcess
0x14028c77d  nop     dword ptr [rax+rax+00h]
0x14028c782  test    edi, edi
0x14028c784  jns     short loc_14028C7D2
0x14028c786  mov     ecx, 2
0x14028c78b  call    cs:__imp_WdLogSingleEntry0
0x14028c792  nop     dword ptr [rax+rax+00h]
0x14028c797  mov     [rsp+2E0h+var_2A0], r12
0x14028c79c  lea     r9, aFailedToCreate_50; "Failed to create nt handle in guest pro"...
0x14028c7a3  mov     [rsp+2E0h+var_2A8], r12
0x14028c7a8  mov     eax, 3A6Dh
0x14028c7ad  mov     [rsp+2E0h+var_2B0], r12
0x14028c7b2  mov     cs:WdLogGlobalForLineNumber, eax
0x14028c7b8  mov     [rsp+2E0h+HandleInformation], r12
0x14028c7bd  or      r8d, 0FFFFFFFFh
0x14028c7c1  mov     [rsp+2E0h+Object], rax
0x14028c7c6  mov     edx, 40000h
0x14028c7cb  xor     ecx, ecx
0x14028c7cd  call    DxgkLogInternalTriageEvent
0x14028c7d2  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x14028c7d7  xor     r9d, r9d; unsigned int *
0x14028c7da  mov     [rsp+2E0h+HandleInformation], r12; unsigned int *
0x14028c7df  xorps   xmm0, xmm0
0x14028c7e2  mov     [rsp+2E0h+Object], r12; unsigned int *
0x14028c7e7  lea     rcx, [rbp+1E0h+var_230]; this
0x14028c7eb  mov     rbx, [rax+6A0h]
0x14028c7f2  lea     r8d, [r9+38h]; unsigned int
0x14028c7f6  movdqa  [rbp+1E0h+var_230], xmm0
0x14028c7fb  mov     rdx, rbx; struct DXG_VMBUS_CHANNEL_BASE *
0x14028c7fe  mov     [rbp+1E0h+var_220], r12d
0x14028c802  call    ?InitializeMessage@DXGVMBUSMESSAGE@@QEAAXPEAUDXG_VMBUS_CHANNEL_BASE@@IPEAI11@Z; DXGVMBUSMESSAGE::InitializeMessage(DXG_VMBUS_CHANNEL_BASE *,uint,uint *,uint *,uint *)
0x14028c807  mov     rcx, qword ptr [rbp+1E0h+var_230]
0x14028c80b  test    rcx, rcx
0x14028c80e  jnz     short loc_14028C820
0x14028c810  lea     rcx, [rbp+1E0h+var_230]; this
0x14028c814  mov     edi, 0C0000017h
0x14028c819  call    ??1DXGVMBUSMESSAGE@@QEAA@XZ; DXGVMBUSMESSAGE::~DXGVMBUSMESSAGE(void)
0x14028c81e  jmp     short loc_14028C7D2
0x14028c820  mov     rdx, [rsp+2E0h+Handle]
0x14028c825  mov     rax, [rsi+20h]
0x14028c829  mov     byte ptr [rcx+0Ch], 1
0x14028c82d  and     dword ptr [rcx+0Ch], 1FFh
0x14028c834  mov     [rcx+30h], rdx
0x14028c838  lea     rdx, [rbp+1E0h+var_230]; struct DXGVMBUSMESSAGE *
0x14028c83c  mov     [rcx+20h], rax
0x14028c840  mov     [rcx], r12
0x14028c843  mov     [rcx+8], r12d
0x14028c847  mov     qword ptr [rcx+10h], 3F3h
0x14028c84f  mov     [rcx+18h], edi
0x14028c852  mov     dword ptr [rcx+28h], 8
0x14028c859  mov     rcx, rbx; this
0x14028c85c  call    ?VmBusSendCompleteTransaction@DXG_GUEST_GLOBAL_VMBUS@@QEAAJPEAUDXGVMBUSMESSAGE@@@Z; DXG_GUEST_GLOBAL_VMBUS::VmBusSendCompleteTransaction(DXGVMBUSMESSAGE *)
0x14028c861  test    eax, eax
0x14028c863  js      short loc_14028C869
0x14028c865  test    edi, edi
0x14028c867  jns     short loc_14028C897
0x14028c869  mov     rcx, [rsp+2E0h+Handle]; Handle
0x14028c86e  test    rcx, rcx
0x14028c871  jz      short loc_14028C883
0x14028c873  mov     dl, 1; PreviousMode
0x14028c875  call    cs:__imp_ObCloseHandle
0x14028c87c  nop     dword ptr [rax+rax+00h]
0x14028c881  jmp     short loc_14028C897
0x14028c883  test    r14, r14
0x14028c886  jz      short loc_14028C897
0x14028c888  mov     rcx, r14; Object
0x14028c88b  call    cs:__imp_ObfDereferenceObject
0x14028c892  nop     dword ptr [rax+rax+00h]
0x14028c897  test    r15, r15
0x14028c89a  jz      short loc_14028C8AB
0x14028c89c  mov     rcx, r15; Object
0x14028c89f  call    cs:__imp_ObfDereferenceObject
0x14028c8a6  nop     dword ptr [rax+rax+00h]
0x14028c8ab  lea     rcx, [rbp+1E0h+var_230]; this
0x14028c8af  call    ??1DXGVMBUSMESSAGE@@QEAA@XZ; DXGVMBUSMESSAGE::~DXGVMBUSMESSAGE(void)
0x14028c8b4  lea     rcx, [rbp+1E0h+var_E0]; this
0x14028c8bb  call    ??1COREADAPTERACCESS@@QEAA@XZ; COREADAPTERACCESS::~COREADAPTERACCESS(void)
0x14028c8c0  xor     al, al
0x14028c8c2  mov     rcx, [rbp+1E0h+var_50]
0x14028c8c9  xor     rcx, rsp; StackCookie
0x14028c8cc  call    __security_check_cookie
0x14028c8d1  add     rsp, 2A8h
0x14028c8d8  pop     r15
0x14028c8da  pop     r14
0x14028c8dc  pop     r13
0x14028c8de  pop     r12
0x14028c8e0  pop     rdi
0x14028c8e1  pop     rsi
0x14028c8e2  pop     rbx
0x14028c8e3  pop     rbp
0x14028c8e4  retn
```
