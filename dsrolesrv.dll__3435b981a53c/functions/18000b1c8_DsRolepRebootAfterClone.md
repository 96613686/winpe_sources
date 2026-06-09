# DsRolepRebootAfterClone

- ea: `0x18000b1c8`
- end: `0x18000b47a`
- name: `DsRolepRebootAfterClone`
- size: `690`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180003ff0`
- `0x180012460`

## callees

- `0x18000ace0`
- `0x18000b1c8`
- `0x18000b480`
- `0x18000b914`
- `0x18000bd88`
- `0x18001e204`
- `0x180020838`
- `0x180020dbc`
- `0x180022e54`
- `0x1800235f0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b37d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b37d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b3f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b3f9`
- `bcd!BcdCloseObject` at `0x18000b2a1`
- `bcd!BcdCloseObject` at `0x18000b2a1`
- `bcd!BcdDeleteElement` at `0x18000b279`
- `bcd!BcdDeleteElement` at `0x18000b279`
- `ntdll!RtlLeaveCriticalSection` at `0x18000b395`
- `ntdll!RtlLeaveCriticalSection` at `0x18000b395`
- `ntdll!NtShutdownSystem` at `0x18000b427`
- `ntdll!NtShutdownSystem` at `0x18000b427`
- `ntdll!RtlEnterCriticalSection` at `0x18000b36b`
- `ntdll!RtlEnterCriticalSection` at `0x18000b36b`
- `ntdll!RtlNtStatusToDosError` at `0x18000b2d5`
- `ntdll!RtlNtStatusToDosError` at `0x18000b3d0`
- `ntdll!RtlNtStatusToDosError` at `0x18000b45d`
- `ntdll!RtlNtStatusToDosError` at `0x18000b2d5`
- `ntdll!RtlNtStatusToDosError` at `0x18000b3d0`
- `ntdll!RtlNtStatusToDosError` at `0x18000b45d`
- `api-ms-win-core-shutdown-l1-1-0!InitiateSystemShutdownExW` at `0x18000b3ef`
- `api-ms-win-core-shutdown-l1-1-0!InitiateSystemShutdownExW` at `0x18000b3ef`

## string_xrefs

- `0x18000b201`: `vDC Cloning: SYSVOL and/or NTDS databases have been changed during cloning process. Cloning is not retryable. Please discard this clone image.\n`
- `0x18000b21a`: `vDC Cloning: Computer name is provided in clone config file and clone objects have been created on PDC. To retry the cloning attempt, please modify the clone config file with a new computer name.\n`
- `0x18000b352`: `vDC Cloning: Cannot set VdcCloningDone registry value: 0x%x (%lu)\n`
- `0x18000b3bf`: `Failed to get shutdown privilege\n`

## pseudocode

```c
__int64 __fastcall DsRolepRebootAfterClone(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  ULONG LastError; // ebx
  char v5; // si
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // r8
  __int64 v11; // r9
  NTSTATUS v12; // edi
  int v13; // eax
  __int64 v14; // r9
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 v17; // rdx
  LSTATUS v18; // eax
  int v19; // edi
  NTSTATUS v20; // eax
  unsigned int v21; // edi
  __int64 v22; // r9
  int v24; // [rsp+50h] [rbp+8h] BYREF
  __int64 v25; // [rsp+60h] [rbp+18h] BYREF

  LastError = 0;
  v5 = a2;
  v24 = 1;
  if ( (_DWORD)a1 )
  {
    DsRolepLogPrintRoutine(1, "vDC Cloning: Cloning failed with error code 0x%x.\n", a1);
    if ( gfCloningRetryable )
    {
      if ( gfProvisionedCloneName && gfRpcAddCloneDcFinished )
        DsRolepLogPrintRoutine(
          1,
          "vDC Cloning: Computer name is provided in clone config file and clone objects have been created on PDC. To ret"
          "ry the cloning attempt, please modify the clone config file with a new computer name.\n");
    }
    else
    {
      DsRolepLogPrintRoutine(
        1,
        "vDC Cloning: SYSVOL and/or NTDS databases have been changed during cloning process. Cloning is not retryable. Pl"
        "ease discard this clone image.\n");
    }
    gdwCloningProgress = 999;
    DsRolepUpdateCloningProgressMessage(v7, v6, v8, v9);
    DsRolepEventWrite(DSROLERES_FAIL_VDC_CLONE_EVENT, 0, v10, v11);
  }
  else
  {
    gdwCloningProgress = 100;
    DsRolepUpdateCloningProgressMessage(a1, a2, a3, a4);
    v25 = 0;
    v12 = OpenBootEntry((__int64)&v25);
    if ( v12 >= 0 )
    {
      v13 = BcdDeleteElement(v25, 620757120);
      v12 = v13;
      if ( v13 < 0 )
        DsRolepLogPrintRoutine(1, "vDC Cloning: Error deleting DSRM Mode, NTSTATUS code: 0x%x\n", v13);
    }
    if ( v25 )
      BcdCloseObject();
    if ( v12 >= 0 )
    {
      DsRolepLogPrintRoutine(4, "vDC Cloning: Clearing Boot into DSRM flag succeeded.\n");
    }
    else
    {
      DsRolepLogPrintRoutine(1, "vDC Cloning: Clearing Boot into DSRM flag failed with NTSTATUS code 0x%x.\n", v12);
      DsRolepEventWrite(DSROLERES_VDC_CLONE_FAILED_CLEAR_DSRM_EVENT, L"d", (unsigned int)v12, v14);
      LastError = RtlNtStatusToDosError(v12);
    }
    if ( v5 )
    {
      DsRolepEventWrite(DSROLERES_VDC_CLONE_SUCCESS_EVENT, 0, v15, v16);
      DeleteConfigParam("VdcIsCloning");
      DeleteConfigParam("ClonePhase");
      DeleteConfigParam("CloneMachineName");
      DeleteConfigParam("ReturnedSite");
      DsRolepRenameCloneConfigFiles();
      v18 = SetConfigParam("VdcCloningDone", v17, (const BYTE *)&v24);
      LastError = v18;
      if ( v18 )
        DsRolepLogPrintRoutine(1, "vDC Cloning: Cannot set VdcCloningDone registry value: 0x%x (%lu)\n", v18, v18);
    }
  }
  RtlEnterCriticalSection(&gcsUpdateMessage);
  if ( gpwszCloningProgressMessage )
  {
    LocalFree(gpwszCloningProgressMessage);
    gpwszCloningProgressMessage = 0;
  }
  RtlLeaveCriticalSection(&gcsUpdateMessage);
  DsRolepLogPrintRoutine(4, "Rebooting machine\n");
  v19 = DsRolepEnablePrivilege(0x13u, 1u);
  if ( v19 < 0 )
  {
    DsRolepLogPrintRoutine(1, "Failed to get shutdown privilege\n");
    LastError = RtlNtStatusToDosError(v19);
  }
  if ( !InitiateSystemShutdownExW(0, 0, 0, 1, 1, 0x80020004) )
  {
    LastError = GetLastError();
    DsRolepLogPrintRoutine(1, "Failed to reboot using InitiateSystemShutdownExW, error code = 0x%x\n", LastError);
    DsRolepLogPrintRoutine(4, "Now try to reboot using NtShutdownSystem\n");
    v20 = NtShutdownSystem(ShutdownReboot);
    v21 = v20;
    if ( v20 < 0 )
    {
      DsRolepLogPrintRoutine(1, "Failed to reboot using NtShutdownSystem. Returnd NTSTATUS code is 0x%x\n", v20);
      DsRolepEventWrite(DSROLERES_VDC_CLONE_FAILED_REBOOT_EVENT, L"d", v21, v22);
      LastError = RtlNtStatusToDosError(v21);
    }
  }
  DsRolepCloseLog();
  return LastError;
}

```

## disassembly

```asm
0x18000b1c8  mov     [rsp+arg_8], rbx
0x18000b1cd  push    rsi
0x18000b1ce  push    rdi
0x18000b1cf  push    r14
0x18000b1d1  sub     rsp, 30h
0x18000b1d5  xor     ebx, ebx
0x18000b1d7  mov     sil, dl
0x18000b1da  lea     r14d, [rbx+1]
0x18000b1de  mov     [rsp+48h+arg_0], r14d
0x18000b1e3  test    ecx, ecx
0x18000b1e5  jz      short loc_18000B24B
0x18000b1e7  mov     r8d, ecx
0x18000b1ea  lea     rdx, aVdcCloningClon; "vDC Cloning: Cloning failed with error "...
0x18000b1f1  mov     ecx, r14d
0x18000b1f4  call    DsRolepLogPrintRoutine
0x18000b1f9  cmp     cs:gfCloningRetryable, ebx
0x18000b1ff  jnz     short loc_18000B20A
0x18000b201  lea     rdx, aVdcCloningSysv; "vDC Cloning: SYSVOL and/or NTDS databas"...
0x18000b208  jmp     short loc_18000B221
0x18000b20a  cmp     cs:gfProvisionedCloneName, ebx
0x18000b210  jz      short loc_18000B229
0x18000b212  cmp     cs:gfRpcAddCloneDcFinished, ebx
0x18000b218  jz      short loc_18000B229
0x18000b21a  lea     rdx, aVdcCloningComp_1; "vDC Cloning: Computer name is provided "...
0x18000b221  mov     ecx, r14d
0x18000b224  call    DsRolepLogPrintRoutine
0x18000b229  mov     cs:gdwCloningProgress, 3E7h
0x18000b233  call    DsRolepUpdateCloningProgressMessage
0x18000b238  xor     edx, edx
0x18000b23a  lea     rcx, DSROLERES_FAIL_VDC_CLONE_EVENT
0x18000b241  call    DsRolepEventWrite
0x18000b246  jmp     loc_18000B364
0x18000b24b  mov     cs:gdwCloningProgress, 64h ; 'd'
0x18000b255  call    DsRolepUpdateCloningProgressMessage
0x18000b25a  lea     rcx, [rsp+48h+arg_10]
0x18000b25f  mov     [rsp+48h+arg_10], rbx
0x18000b264  call    OpenBootEntry
0x18000b269  mov     edi, eax
0x18000b26b  test    eax, eax
0x18000b26d  js      short loc_18000B297
0x18000b26f  mov     rcx, [rsp+48h+arg_10]
0x18000b274  mov     edx, 25000080h
0x18000b279  call    cs:__imp_BcdDeleteElement
0x18000b27f  mov     edi, eax
0x18000b281  test    eax, eax
0x18000b283  jns     short loc_18000B297
0x18000b285  mov     r8d, eax
0x18000b288  lea     rdx, aVdcCloningErro_0; "vDC Cloning: Error deleting DSRM Mode, "...
0x18000b28f  mov     ecx, r14d
0x18000b292  call    DsRolepLogPrintRoutine
0x18000b297  mov     rcx, [rsp+48h+arg_10]
0x18000b29c  test    rcx, rcx
0x18000b29f  jz      short loc_18000B2A7
0x18000b2a1  call    cs:__imp_BcdCloseObject
0x18000b2a7  test    edi, edi
0x18000b2a9  jns     short loc_18000B2DF
0x18000b2ab  mov     r8d, edi
0x18000b2ae  lea     rdx, aVdcCloningClea; "vDC Cloning: Clearing Boot into DSRM fl"...
0x18000b2b5  mov     ecx, r14d
0x18000b2b8  call    DsRolepLogPrintRoutine
0x18000b2bd  mov     r8d, edi
0x18000b2c0  lea     rdx, aD; "d"
0x18000b2c7  lea     rcx, DSROLERES_VDC_CLONE_FAILED_CLEAR_DSRM_EVENT
0x18000b2ce  call    DsRolepEventWrite
0x18000b2d3  mov     ecx, edi; Status
0x18000b2d5  call    cs:__imp_RtlNtStatusToDosError
0x18000b2db  mov     ebx, eax
0x18000b2dd  jmp     short loc_18000B2F0
0x18000b2df  lea     rdx, aVdcCloningClea_0; "vDC Cloning: Clearing Boot into DSRM fl"...
0x18000b2e6  mov     ecx, 4
0x18000b2eb  call    DsRolepLogPrintRoutine
0x18000b2f0  test    sil, sil
0x18000b2f3  jz      short loc_18000B364
0x18000b2f5  xor     edx, edx
0x18000b2f7  lea     rcx, DSROLERES_VDC_CLONE_SUCCESS_EVENT
0x18000b2fe  call    DsRolepEventWrite
0x18000b303  lea     rcx, aVdciscloning; "VdcIsCloning"
0x18000b30a  call    DeleteConfigParam
0x18000b30f  lea     rcx, aClonephase_0; "ClonePhase"
0x18000b316  call    DeleteConfigParam
0x18000b31b  lea     rcx, aClonemachinena; "CloneMachineName"
0x18000b322  call    DeleteConfigParam
0x18000b327  lea     rcx, aReturnedsite; "ReturnedSite"
0x18000b32e  call    DeleteConfigParam
0x18000b333  call    DsRolepRenameCloneConfigFiles
0x18000b338  lea     r8, [rsp+48h+arg_0]
0x18000b33d  lea     rcx, aVdccloningdone; "VdcCloningDone"
0x18000b344  call    SetConfigParam
0x18000b349  mov     ebx, eax
0x18000b34b  test    eax, eax
0x18000b34d  jz      short loc_18000B364
0x18000b34f  mov     r9d, eax
0x18000b352  lea     rdx, aVdcCloningCann_3; "vDC Cloning: Cannot set VdcCloningDone "...
0x18000b359  mov     r8d, eax
0x18000b35c  mov     ecx, r14d
0x18000b35f  call    DsRolepLogPrintRoutine
0x18000b364  lea     rcx, gcsUpdateMessage; CriticalSection
0x18000b36b  call    cs:__imp_RtlEnterCriticalSection
0x18000b371  mov     rcx, cs:gpwszCloningProgressMessage; hMem
0x18000b378  test    rcx, rcx
0x18000b37b  jz      short loc_18000B38E
0x18000b37d  call    cs:__imp_LocalFree
0x18000b383  mov     cs:gpwszCloningProgressMessage, 0
0x18000b38e  lea     rcx, gcsUpdateMessage; CriticalSection
0x18000b395  call    cs:__imp_RtlLeaveCriticalSection
0x18000b39b  lea     rdx, aRebootingMachi; "Rebooting machine\n"
0x18000b3a2  mov     ecx, 4
0x18000b3a7  call    DsRolepLogPrintRoutine
0x18000b3ac  mov     edx, r14d
0x18000b3af  mov     ecx, 13h; Privilege
0x18000b3b4  call    DsRolepEnablePrivilege
0x18000b3b9  mov     edi, eax
0x18000b3bb  test    eax, eax
0x18000b3bd  jns     short loc_18000B3D8
0x18000b3bf  lea     rdx, aFailedToGetShu; "Failed to get shutdown privilege\n"
0x18000b3c6  mov     ecx, r14d
0x18000b3c9  call    DsRolepLogPrintRoutine
0x18000b3ce  mov     ecx, edi; Status
0x18000b3d0  call    cs:__imp_RtlNtStatusToDosError
0x18000b3d6  mov     ebx, eax
0x18000b3d8  mov     [rsp+48h+dwReason], 80020004h; dwReason
0x18000b3e0  mov     r9d, r14d; bForceAppsClosed
0x18000b3e3  xor     r8d, r8d; dwTimeout
0x18000b3e6  mov     [rsp+48h+bRebootAfterShutdown], r14d; bRebootAfterShutdown
0x18000b3eb  xor     edx, edx; lpMessage
0x18000b3ed  xor     ecx, ecx; lpMachineName
0x18000b3ef  call    cs:__imp_InitiateSystemShutdownExW
0x18000b3f5  test    eax, eax
0x18000b3f7  jnz     short loc_18000B465
0x18000b3f9  call    cs:__imp_GetLastError
0x18000b3ff  lea     rdx, aFailedToReboot; "Failed to reboot using InitiateSystemSh"...
0x18000b406  mov     ecx, r14d
0x18000b409  mov     r8d, eax
0x18000b40c  mov     ebx, eax
0x18000b40e  call    DsRolepLogPrintRoutine
0x18000b413  lea     rdx, aNowTryToReboot; "Now try to reboot using NtShutdownSyste"...
0x18000b41a  mov     ecx, 4
0x18000b41f  call    DsRolepLogPrintRoutine
0x18000b424  mov     ecx, r14d; Action
0x18000b427  call    cs:__imp_NtShutdownSystem
0x18000b42d  mov     edi, eax
0x18000b42f  test    eax, eax
0x18000b431  jns     short loc_18000B465
0x18000b433  mov     r8d, eax
0x18000b436  lea     rdx, aFailedToReboot_0; "Failed to reboot using NtShutdownSystem"...
0x18000b43d  mov     ecx, r14d
0x18000b440  call    DsRolepLogPrintRoutine
0x18000b445  mov     r8d, edi
0x18000b448  lea     rdx, aD; "d"
0x18000b44f  lea     rcx, DSROLERES_VDC_CLONE_FAILED_REBOOT_EVENT
0x18000b456  call    DsRolepEventWrite
0x18000b45b  mov     ecx, edi; Status
0x18000b45d  call    cs:__imp_RtlNtStatusToDosError
0x18000b463  mov     ebx, eax
0x18000b465  call    DsRolepCloseLog
0x18000b46a  mov     eax, ebx
0x18000b46c  mov     rbx, [rsp+48h+arg_8]
0x18000b471  add     rsp, 30h
0x18000b475  pop     r14
0x18000b477  pop     rdi
0x18000b478  pop     rsi
0x18000b479  retn
```
