# CPnpCleanTaskHandler::Worker(void)

- ea: `0x180003d70`
- end: `0x180003fce`
- name: `?Worker@CPnpCleanTaskHandler@@EEAAJXZ`
- size: `606`
- prototype: `__int64 __fastcall(CPnpCleanTaskHandler *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180003d70`
- `0x1800043a0`
- `0x180004690`
- `0x180004e0c`
- `0x180004e74`
- `0x180006dc4`
- `0x180007dec`
- `0x180008dfe`

## import_xrefs

- `SETUPAPI!pSetupCreateTextLogSectionW` at `0x180003dbe`
- `SETUPAPI!pSetupCreateTextLogSectionW` at `0x180003dbe`
- `SETUPAPI!pSetupCloseTextLogSection` at `0x180003faa`
- `SETUPAPI!pSetupCloseTextLogSection` at `0x180003faa`

## string_xrefs

- `0x180003db5`: `Device and Driver Disk Cleanup Task`
- `0x180003de2`: `Searching for not-recently detected devices that may be removed from the system.`
- `0x180003e02`: `Devices %ws be removed during this pass.`
- `0x180003ef6`: `removed`
- `0x180003eef`: `to remove`

## pseudocode

```c
__int64 __fastcall CPnpCleanTaskHandler::Worker(CPnpCleanTaskHandler *this)
{
  _DWORD *v1; // rdi
  signed int v2; // ebx
  int v3; // esi
  __int64 v4; // rdx
  __int64 v5; // rcx
  int CurrentConfiguration; // eax
  int v7; // ecx
  int v8; // edx
  int v9; // ecx
  signed int v10; // eax
  const wchar_t *v11; // rcx
  int v12; // eax
  int v13; // eax
  _QWORD v15[3]; // [rsp+40h] [rbp-19h] BYREF
  _QWORD v16[5]; // [rsp+58h] [rbp-1h] BYREF
  __int64 v17; // [rsp+80h] [rbp+27h]
  int v18; // [rsp+88h] [rbp+2Fh]
  int v19; // [rsp+8Ch] [rbp+33h]
  __int64 v20; // [rsp+C0h] [rbp+67h] BYREF

  v1 = (_DWORD *)((char *)this + 64);
  v20 = 0;
  if ( *((_DWORD *)this + 16) )
    return (unsigned int)-2147023673;
  v3 = pSetupCreateTextLogSectionW(0, 3, L"Device and Driver Disk Cleanup Task", &v20);
  if ( !v3 )
    v20 = 1;
  memset_0(v15, 0, 0x50u);
  PnpCleanSetupLogCallback(
    &v20,
    3,
    1,
    "Searching for not-recently detected devices that may be removed from the system.");
  PnpCleanSetupLogCallback(&v20, 3, 0, "Devices %ws be removed during this pass.", L"will");
  v16[0] = 0;
  v16[1] = PnpCleanTaskStatusCallback;
  v17 = 1;
  v16[3] = PnpCleanSetupLogCallback;
  v16[4] = &v20;
  memset(v15, 0, sizeof(v15));
  v16[2] = v1;
  v18 = 0;
  v19 = 30;
  CurrentConfiguration = HwCfgGetCurrentConfiguration(v5, v4, v16);
  v7 = v16[0];
  HIDWORD(v17) = 0;
  if ( CurrentConfiguration )
    v7 = -1;
  LODWORD(v16[0]) = v7;
  if ( !(unsigned int)PnpCleanDevicesNotifyCallback(v15)
    || (HIDWORD(v17) = 3, !(unsigned int)PnpCleanDevicesNotifyCallback(v15)) )
  {
    LOWORD(v2) = 1223;
LABEL_12:
    v2 = (unsigned __int16)v2 | 0x80070000;
    goto LABEL_16;
  }
  PnpCleanSetupLogCallback(&v20, 4, 1, "Processing devices...");
  v10 = ProcessDevicesToRemove(v15);
  v2 = v10;
  if ( !v10 )
  {
    v11 = L"removed";
    if ( !(_DWORD)v17 )
      v11 = L"to remove";
    v2 = 0;
    PnpCleanSetupLogCallback(&v20, 3, 1, "Devices %ws: %d", v11, v18);
    HIDWORD(v17) = 4;
    PnpCleanDevicesNotifyCallback(v15);
    goto LABEL_16;
  }
  PnpCleanSetupLogCallback(&v20, 1, 1, "Failed to process devices for removal, Err = 0x%lx", v10);
  if ( v2 > 0 )
    goto LABEL_12;
LABEL_16:
  v12 = PnpCleanDriversEx(
          v9,
          v8,
          (unsigned int)PnpCleanTaskStatusCallback,
          (_DWORD)v1,
          (__int64)PnpCleanSetupLogCallback,
          (__int64)&v20,
          0);
  if ( v12 )
  {
    if ( v12 > 0 )
      v2 = (unsigned __int16)v12 | 0x80070000;
    else
      v2 = v12;
  }
  v13 = PnpCleanFiles(
          (unsigned int)PnpCleanTaskStatusCallback,
          (_DWORD)v1,
          (unsigned int)PnpCleanSetupLogCallback,
          (unsigned int)&v20,
          0);
  if ( v13 )
  {
    if ( v13 > 0 )
      v2 = (unsigned __int16)v13 | 0x80070000;
    else
      v2 = v13;
  }
  *v1 = 1;
  if ( v3 )
    pSetupCloseTextLogSection(v20, (unsigned int)v13);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180003d70  mov     [rsp-8+arg_8], rbx
0x180003d75  mov     [rsp-8+arg_10], rsi
0x180003d7a  push    rbp
0x180003d7b  push    rdi
0x180003d7c  push    r12
0x180003d7e  push    r14
0x180003d80  push    r15
0x180003d82  lea     rbp, [rsp-37h]
0x180003d87  sub     rsp, 90h
0x180003d8e  xor     r14d, r14d
0x180003d91  lea     rdi, [rcx+40h]
0x180003d95  mov     [rbp+57h+arg_0], r14
0x180003d99  cmp     [rdi], r14d
0x180003d9c  jz      short loc_180003DA8
0x180003d9e  mov     ebx, 800704C7h
0x180003da3  jmp     loc_180003FB0
0x180003da8  mov     r12d, 3
0x180003dae  lea     r9, [rbp+57h+arg_0]
0x180003db2  mov     edx, r12d
0x180003db5  lea     r8, aDeviceAndDrive_0; "Device and Driver Disk Cleanup Task"
0x180003dbc  xor     ecx, ecx
0x180003dbe  call    cs:__imp_pSetupCreateTextLogSectionW
0x180003dc4  lea     r15d, [r12-2]
0x180003dc9  mov     esi, eax
0x180003dcb  test    eax, eax
0x180003dcd  jnz     short loc_180003DD3
0x180003dcf  mov     [rbp+57h+arg_0], r15
0x180003dd3  xor     edx, edx; Val
0x180003dd5  lea     rcx, [rbp+57h+var_70]; void *
0x180003dd9  lea     r8d, [rdx+50h]; Size
0x180003ddd  call    memset_0
0x180003de2  lea     r9, aSearchingForNo; "Searching for not-recently detected dev"...
0x180003de9  mov     r8d, r15d
0x180003dec  mov     edx, r12d
0x180003def  lea     rcx, [rbp+57h+arg_0]
0x180003df3  call    PnpCleanSetupLogCallback
0x180003df8  lea     rax, aWill; "will"
0x180003dff  xor     r8d, r8d
0x180003e02  lea     r9, aDevicesWsBeRem; "Devices %ws be removed during this pass"...
0x180003e09  mov     [rsp+0B0h+var_90], rax
0x180003e0e  mov     edx, r12d
0x180003e11  lea     rcx, [rbp+57h+arg_0]
0x180003e15  call    PnpCleanSetupLogCallback
0x180003e1a  lea     rax, ?PnpCleanTaskStatusCallback@@YAHPEAU_PNPCLEAN_STATUS_DATA@@PEAX@Z; PnpCleanTaskStatusCallback(_PNPCLEAN_STATUS_DATA *,void *)
0x180003e21  mov     [rbp+57h+var_58], r14
0x180003e25  mov     [rbp+57h+var_50], rax
0x180003e29  lea     r8, [rbp+57h+var_58]
0x180003e2d  lea     rax, PnpCleanSetupLogCallback
0x180003e34  mov     [rbp+57h+var_30], r15
0x180003e38  mov     [rbp+57h+var_40], rax
0x180003e3c  lea     rax, [rbp+57h+arg_0]
0x180003e40  mov     [rbp+57h+var_38], rax
0x180003e44  mov     [rbp+57h+var_70], r14
0x180003e48  mov     [rbp+57h+var_68], r14
0x180003e4c  mov     [rbp+57h+var_60], r14
0x180003e50  mov     [rbp+57h+var_48], rdi
0x180003e54  mov     [rbp+57h+var_28], r14d
0x180003e58  mov     [rbp+57h+var_24], 1Eh
0x180003e5f  call    HwCfgGetCurrentConfiguration
0x180003e64  mov     ecx, dword ptr [rbp+57h+var_58]
0x180003e67  or      edx, 0FFFFFFFFh
0x180003e6a  test    eax, eax
0x180003e6c  mov     dword ptr [rbp+57h+var_30+4], r14d
0x180003e70  cmovnz  ecx, edx
0x180003e73  mov     dword ptr [rbp+57h+var_58], ecx
0x180003e76  lea     rcx, [rbp+57h+var_70]
0x180003e7a  call    PnpCleanDevicesNotifyCallback
0x180003e7f  test    eax, eax
0x180003e81  jnz     short loc_180003E8A
0x180003e83  mov     ebx, 4C7h
0x180003e88  jmp     short loc_180003EE0
0x180003e8a  lea     rcx, [rbp+57h+var_70]
0x180003e8e  mov     dword ptr [rbp+57h+var_30+4], r12d
0x180003e92  call    PnpCleanDevicesNotifyCallback
0x180003e97  test    eax, eax
0x180003e99  jz      short loc_180003E83
0x180003e9b  lea     r9, aProcessingDevi_0; "Processing devices..."
0x180003ea2  mov     r8d, r15d
0x180003ea5  mov     edx, 4
0x180003eaa  lea     rcx, [rbp+57h+arg_0]
0x180003eae  call    PnpCleanSetupLogCallback
0x180003eb3  lea     rcx, [rbp+57h+var_70]
0x180003eb7  call    ProcessDevicesToRemove
0x180003ebc  mov     ebx, eax
0x180003ebe  mov     r8d, r15d
0x180003ec1  test    eax, eax
0x180003ec3  jz      short loc_180003EEB
0x180003ec5  lea     r9, aFailedToProces; "Failed to process devices for removal, "...
0x180003ecc  mov     dword ptr [rsp+0B0h+var_90], eax
0x180003ed0  mov     edx, r15d
0x180003ed3  lea     rcx, [rbp+57h+arg_0]
0x180003ed7  call    PnpCleanSetupLogCallback
0x180003edc  test    ebx, ebx
0x180003ede  jle     short loc_180003F33
0x180003ee0  movzx   ebx, bx
0x180003ee3  or      ebx, 80070000h
0x180003ee9  jmp     short loc_180003F33
0x180003eeb  cmp     dword ptr [rbp+57h+var_30], r14d
0x180003eef  lea     rax, aToRemove; "to remove"
0x180003ef6  lea     rcx, aRemoved; "removed"
0x180003efd  mov     edx, r12d
0x180003f00  cmovz   rcx, rax
0x180003f04  lea     r9, aDevicesWsD; "Devices %ws: %d"
0x180003f0b  mov     eax, [rbp+57h+var_28]
0x180003f0e  mov     ebx, r14d
0x180003f11  mov     dword ptr [rsp+0B0h+var_88], eax
0x180003f15  mov     [rsp+0B0h+var_90], rcx
0x180003f1a  lea     rcx, [rbp+57h+arg_0]
0x180003f1e  call    PnpCleanSetupLogCallback
0x180003f23  lea     rcx, [rbp+57h+var_70]
0x180003f27  mov     dword ptr [rbp+57h+var_30+4], 4
0x180003f2e  call    PnpCleanDevicesNotifyCallback
0x180003f33  lea     rax, [rbp+57h+arg_0]
0x180003f37  mov     [rsp+0B0h+var_80], r14d
0x180003f3c  mov     [rsp+0B0h+var_88], rax
0x180003f41  lea     r12, PnpCleanSetupLogCallback
0x180003f48  mov     r9, rdi
0x180003f4b  mov     [rsp+0B0h+var_90], r12
0x180003f50  lea     r8, ?PnpCleanTaskStatusCallback@@YAHPEAU_PNPCLEAN_STATUS_DATA@@PEAX@Z; PnpCleanTaskStatusCallback(_PNPCLEAN_STATUS_DATA *,void *)
0x180003f57  call    PnpCleanDriversEx
0x180003f5c  test    eax, eax
0x180003f5e  jz      short loc_180003F6F
0x180003f60  jg      short loc_180003F66
0x180003f62  mov     ebx, eax
0x180003f64  jmp     short loc_180003F6F
0x180003f66  movzx   ebx, ax
0x180003f69  or      ebx, 80070000h
0x180003f6f  lea     r9, [rbp+57h+arg_0]
0x180003f73  mov     dword ptr [rsp+0B0h+var_90], r14d
0x180003f78  mov     r8, r12
0x180003f7b  lea     rcx, ?PnpCleanTaskStatusCallback@@YAHPEAU_PNPCLEAN_STATUS_DATA@@PEAX@Z; PnpCleanTaskStatusCallback(_PNPCLEAN_STATUS_DATA *,void *)
0x180003f82  mov     rdx, rdi
0x180003f85  call    PnpCleanFiles
0x180003f8a  test    eax, eax
0x180003f8c  jz      short loc_180003F9D
0x180003f8e  jg      short loc_180003F94
0x180003f90  mov     ebx, eax
0x180003f92  jmp     short loc_180003F9D
0x180003f94  movzx   ebx, ax
0x180003f97  or      ebx, 80070000h
0x180003f9d  mov     [rdi], r15d
0x180003fa0  test    esi, esi
0x180003fa2  jz      short loc_180003FB0
0x180003fa4  mov     rcx, [rbp+57h+arg_0]
0x180003fa8  mov     edx, eax
0x180003faa  call    cs:__imp_pSetupCloseTextLogSection
0x180003fb0  lea     r11, [rsp+0B0h+var_20]
0x180003fb8  mov     eax, ebx
0x180003fba  mov     rbx, [r11+38h]
0x180003fbe  mov     rsi, [r11+40h]
0x180003fc2  mov     rsp, r11
0x180003fc5  pop     r15
0x180003fc7  pop     r14
0x180003fc9  pop     r12
0x180003fcb  pop     rdi
0x180003fcc  pop     rbp
0x180003fcd  retn
```
