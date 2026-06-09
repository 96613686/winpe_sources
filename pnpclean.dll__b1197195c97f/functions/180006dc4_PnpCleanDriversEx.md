# PnpCleanDriversEx

- ea: `0x180006dc4`
- end: `0x180007368`
- name: `PnpCleanDriversEx`
- size: `1444`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64 (__fastcall *)(), __int64, int)`
- caller_count: `4`
- callee_count: `10`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180001cd4`
- `0x180002fc0`
- `0x1800034b0`
- `0x180003d70`

## callees

- `0x180006644`
- `0x18000684c`
- `0x180006dc4`
- `0x180007370`
- `0x1800073e4`
- `0x180007498`
- `0x18000880c`
- `0x180008dfe`
- `0x180008e30`
- `0x18000a010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180006ed5`
- `KERNEL32!GetLastError` at `0x180006efc`
- `KERNEL32!GetLastError` at `0x180006f2b`
- `KERNEL32!GetLastError` at `0x1800070d6`
- `KERNEL32!GetLastError` at `0x180007189`
- `KERNEL32!GetLastError` at `0x180006ed5`
- `KERNEL32!GetLastError` at `0x180006efc`
- `KERNEL32!GetLastError` at `0x180006f2b`
- `KERNEL32!GetLastError` at `0x1800070d6`
- `KERNEL32!GetLastError` at `0x180007189`
- `SETUPAPI!pSetupStringTableDestroy` at `0x180007305`
- `SETUPAPI!pSetupStringTableDestroy` at `0x18000730f`
- `SETUPAPI!pSetupStringTableDestroy` at `0x18000731d`
- `SETUPAPI!pSetupStringTableDestroy` at `0x18000732b`
- `SETUPAPI!pSetupStringTableDestroy` at `0x180007305`
- `SETUPAPI!pSetupStringTableDestroy` at `0x18000730f`
- `SETUPAPI!pSetupStringTableDestroy` at `0x18000731d`
- `SETUPAPI!pSetupStringTableDestroy` at `0x18000732b`
- `SETUPAPI!pSetupStringTableInitializeEx` at `0x180006ec6`
- `SETUPAPI!pSetupStringTableInitializeEx` at `0x180006eee`
- `SETUPAPI!pSetupStringTableInitializeEx` at `0x180006f0e`
- `SETUPAPI!pSetupStringTableInitializeEx` at `0x180006ec6`
- `SETUPAPI!pSetupStringTableInitializeEx` at `0x180006eee`
- `SETUPAPI!pSetupStringTableInitializeEx` at `0x180006f0e`
- `SETUPAPI!pSetupStringTableInitialize` at `0x180006f1d`
- `SETUPAPI!pSetupStringTableInitialize` at `0x180006f1d`
- `SETUPAPI!pSetupStringTableEnum` at `0x18000717f`
- `SETUPAPI!pSetupStringTableEnum` at `0x18000717f`
- `drvstore!DriverStoreOpenW` at `0x180006f42`
- `drvstore!DriverStoreOpenW` at `0x180006f42`
- `drvstore!DriverStoreEnumW` at `0x1800070cc`
- `drvstore!DriverStoreEnumW` at `0x1800070cc`
- `drvstore!DriverStoreClose` at `0x180007339`
- `drvstore!DriverStoreClose` at `0x180007339`

## string_xrefs

- `0x18000724a`: `removed`
- `0x180007243`: `to remove`
- `0x180006e3a`: `Searching for unused drivers that may be removed from the system.`
- `0x180006e8c`: `Drivers %ws be removed during this pass.`
- `0x180006eaa`: `Will only keep drivers that are installed on some device.`
- `0x180006ff5`: `Processing installed devices...`
- `0x180007025`: `Failed to get the set of Driver Store INFs installed on devices, Err = 0x%lx`
- `0x1800072d3`: `Unable to complete driver store integrity check, Err = 0x%lx`

## pseudocode

```c
__int64 __fastcall PnpCleanDriversEx(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 (__fastcall *a5)(),
        __int64 a6,
        int a7)
{
  DWORD LastError; // ebx
  __int64 (__fastcall *v8)(); // rdi
  const wchar_t *v9; // rax
  __int64 v10; // r14
  __int64 v11; // rsi
  __int64 v12; // r15
  int SystemDriveClusterSize; // eax
  int v14; // edx
  DWORD InstalledInfs; // eax
  __int64 v16; // rcx
  const char *v17; // r9
  DWORD AllDeviceIds; // eax
  DWORD v19; // eax
  const wchar_t *v20; // rcx
  DWORD v21; // eax
  DWORD v23; // [rsp+20h] [rbp-E0h]
  DWORD v24; // [rsp+20h] [rbp-E0h]
  DWORD v25; // [rsp+20h] [rbp-E0h]
  __int64 v26; // [rsp+20h] [rbp-E0h]
  _QWORD v27[5]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 (__fastcall *v28)(); // [rsp+78h] [rbp-88h]
  __int64 v29; // [rsp+80h] [rbp-80h]
  BOOL v30; // [rsp+88h] [rbp-78h]
  BOOL v31; // [rsp+8Ch] [rbp-74h]
  __int64 v32; // [rsp+90h] [rbp-70h]
  int v33; // [rsp+98h] [rbp-68h]
  int v34; // [rsp+9Ch] [rbp-64h]
  __int64 v35; // [rsp+A0h] [rbp-60h]
  __int64 v36; // [rsp+A8h] [rbp-58h]
  __int64 v37; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v38; // [rsp+B8h] [rbp-48h]
  __int64 v39; // [rsp+C0h] [rbp-40h]
  __int64 v40; // [rsp+C8h] [rbp-38h]
  __int64 v41; // [rsp+D0h] [rbp-30h]
  __int64 v42; // [rsp+E0h] [rbp-20h]
  __int64 v43; // [rsp+E8h] [rbp-18h]
  __int64 v44; // [rsp+F0h] [rbp-10h]
  __int64 v45; // [rsp+F8h] [rbp-8h]
  _OWORD v46[2]; // [rsp+100h] [rbp+0h] BYREF

  v44 = a3;
  v45 = a4;
  memset_0(v27, 0, 0x88u);
  if ( (a7 & 0xFFFFFFFC) != 0 )
    return 87;
  v8 = guard_check_icall_nop;
  if ( a5 )
    v8 = a5;
  ((void (__fastcall *)(__int64, __int64, __int64, const char *))v8)(
    a6,
    3,
    1,
    "Searching for unused drivers that may be removed from the system.");
  v9 = L"will";
  if ( (a7 & 1) != 0 )
    v9 = L"will NOT";
  ((void (*)(__int64, __int64, _QWORD, const char *, ...))v8)(a6, 3, 0, "Drivers %ws be removed during this pass.", v9);
  if ( (a7 & 2) != 0 )
    ((void (__fastcall *)(__int64, __int64, _QWORD, const char *))v8)(
      a6,
      3,
      0,
      "Will only keep drivers that are installed on some device.");
  v43 = pSetupStringTableInitializeEx(32);
  if ( !v43 )
    return GetLastError();
  v10 = 0;
  v11 = 0;
  v12 = pSetupStringTableInitializeEx(160);
  if ( v12 )
  {
    v42 = pSetupStringTableInitializeEx(8);
    if ( v42 )
    {
      v11 = pSetupStringTableInitialize();
      if ( !v11 || (v10 = DriverStoreOpenW(0, 0, 0, 0)) == 0 )
      {
        LastError = GetLastError();
LABEL_50:
        pSetupStringTableDestroy(v42);
        goto LABEL_51;
      }
      memset(v27, 0, 24);
      v33 = 0;
      v34 = 0;
      v37 = 0;
      v27[3] = v44;
      v27[4] = v45;
      v31 = (a7 & 2) != 0;
      v38 = v43;
      v40 = v42;
      v35 = 0;
      v32 = (a7 & 2) == 0 ? 0xA : 0;
      v28 = v8;
      v29 = a6;
      v30 = !(a7 & 1);
      v39 = v12;
      v41 = v11;
      v36 = v10;
      SystemDriveClusterSize = pUtilGetSystemDriveClusterSize(&v37);
      v14 = v37;
      HIDWORD(v32) = 0;
      if ( SystemDriveClusterSize )
        v14 = 0;
      LODWORD(v37) = v14;
      if ( !(unsigned int)PnpCleanDriversNotifyCallback(v27) )
      {
LABEL_20:
        LastError = 1223;
        goto LABEL_50;
      }
      ((void (__fastcall *)(__int64, __int64, __int64, const char *))v8)(v29, 4, 1, "Processing installed devices...");
      InstalledInfs = GetInstalledInfs(v27);
      v16 = v29;
      LastError = InstalledInfs;
      if ( InstalledInfs )
      {
        v24 = InstalledInfs;
        v17 = "Failed to get the set of Driver Store INFs installed on devices, Err = 0x%lx";
LABEL_23:
        ((void (__fastcall *)(__int64, __int64, __int64, const char *, DWORD))v8)(v16, 1, 1, v17, v24);
        goto LABEL_50;
      }
      ((void (__fastcall *)(__int64, __int64, __int64, const char *))v8)(v29, 4, 1, "Gathering all device ids...");
      AllDeviceIds = GetAllDeviceIds(v27);
      LastError = AllDeviceIds;
      if ( AllDeviceIds )
      {
        v24 = AllDeviceIds;
        v17 = "Failed to get the set of devices ids for all devices, Err = 0x%lx";
LABEL_26:
        v16 = v29;
        goto LABEL_23;
      }
      HIDWORD(v32) = 1;
      if ( !(unsigned int)PnpCleanDriversNotifyCallback(v27) )
        goto LABEL_20;
      ((void (__fastcall *)(__int64, __int64, __int64, const char *))v8)(v29, 4, 1, "Processing published drivers...");
      if ( (unsigned int)DriverStoreEnumW(v36, 6, EnumDriverPackageCallback, v27) )
      {
        LastError = v27[0];
        if ( !LODWORD(v27[0]) )
          goto LABEL_34;
        v23 = v27[0];
      }
      else
      {
        LastError = GetLastError();
        v23 = LastError;
      }
      ((void (__fastcall *)(__int64, __int64))v28)(v29, 1);
      if ( LastError )
      {
        v24 = LastError;
        v17 = "Failed to get published Driver Store INFs failed, Err = 0x%lx";
        goto LABEL_26;
      }
LABEL_34:
      if ( !(unsigned int)PnpCleanDriversNotifyCallback(v27) )
        goto LABEL_20;
      ((void (__fastcall *)(__int64, __int64, __int64, const char *, DWORD))v8)(
        v29,
        4,
        1,
        "Processing device ID matches...",
        v23);
      memset(v46, 0, sizeof(v46));
      if ( (unsigned int)pSetupStringTableEnum(v38, v46, 32, StrTabEnumDriverStoreDeviceIdSetBestMatchCallback, v27) )
      {
        LastError = v27[0];
        if ( !LODWORD(v27[0]) )
          goto LABEL_41;
        v25 = v27[0];
      }
      else
      {
        LastError = GetLastError();
        v25 = LastError;
      }
      ((void (__fastcall *)(__int64, __int64))v28)(v29, 1);
      if ( LastError )
      {
        v24 = LastError;
        v17 = "Failed to process Driver Store INF device ID matches, Err = 0x%lx";
        goto LABEL_26;
      }
LABEL_41:
      HIDWORD(v32) = !(a7 & 1) + 2;
      if ( !(unsigned int)PnpCleanDriversNotifyCallback(v27) )
        goto LABEL_20;
      ((void (__fastcall *)(__int64, __int64, __int64, const char *, DWORD))v8)(
        v29,
        4,
        1,
        "Processing driver packages...",
        v25);
      v19 = ProcessDriverStoreInfsForRemoval(v27);
      LastError = v19;
      if ( !v19 )
      {
        v20 = L"removed";
        if ( !v30 )
          v20 = L"to remove";
        ((void (*)(__int64, __int64, __int64, const char *, ...))v8)(v29, 3, 1, "Driver packages %ws: %d", v20, v33);
        ((void (*)(__int64, __int64, _QWORD, const char *, ...))v8)(v29, 3, 0, "Total size on disk: %I64d", v35);
        if ( (a7 & 1) == 0 )
        {
          ((void (__fastcall *)(__int64, __int64, __int64, const char *))v8)(
            v29,
            3,
            1,
            "Verifying driver store integrity...");
          v21 = PnpCleanVerifyDriverStoreIntegrity(v8, a6);
          LastError = v21;
          if ( v21 )
          {
            LODWORD(v26) = v21;
            ((void (*)(__int64, __int64, __int64, const char *, ...))v8)(
              v29,
              2,
              1,
              "Unable to complete driver store integrity check, Err = 0x%lx",
              v26);
            LastError = 0;
          }
        }
        HIDWORD(v32) = 4;
        PnpCleanDriversNotifyCallback(v27);
        goto LABEL_50;
      }
      v24 = v19;
      v17 = "Failed to process Driver Store INFs for removal, Err = 0x%lx";
      goto LABEL_26;
    }
  }
  LastError = GetLastError();
LABEL_51:
  pSetupStringTableDestroy(v43);
  if ( v12 )
    pSetupStringTableDestroy(v12);
  if ( v11 )
    pSetupStringTableDestroy(v11);
  if ( v10 )
    DriverStoreClose(v10);
  return LastError;
}

```

## disassembly

```asm
0x180006dc4  mov     [rsp-8+arg_0], rbx
0x180006dc9  push    rbp
0x180006dca  push    rsi
0x180006dcb  push    rdi
0x180006dcc  push    r12
0x180006dce  push    r13
0x180006dd0  push    r14
0x180006dd2  push    r15
0x180006dd4  lea     rbp, [rsp-30h]
0x180006dd9  sub     rsp, 130h
0x180006de0  mov     rax, cs:__security_cookie
0x180006de7  xor     rax, rsp
0x180006dea  mov     [rbp+60h+var_40], rax
0x180006dee  mov     rsi, [rbp+60h+arg_20]
0x180006df5  lea     rcx, [rsp+160h+var_110]; void *
0x180006dfa  mov     r12, [rbp+60h+arg_28]
0x180006e01  xor     edx, edx; Val
0x180006e03  mov     [rbp+60h+var_70], r8
0x180006e07  mov     r8d, 88h; Size
0x180006e0d  mov     [rbp+60h+var_68], r9
0x180006e11  call    memset_0
0x180006e16  mov     ebx, [rbp+60h+arg_30]
0x180006e1c  test    ebx, 0FFFFFFFCh
0x180006e22  jz      short loc_180006E2E
0x180006e24  mov     ebx, 57h ; 'W'
0x180006e29  jmp     loc_18000733F
0x180006e2e  mov     ecx, ebx
0x180006e30  lea     rdi, _guard_check_icall_nop
0x180006e37  and     ecx, 1
0x180006e3a  lea     r9, aSearchingForUn; "Searching for unused drivers that may b"...
0x180006e41  mov     eax, 0
0x180006e46  mov     [rsp+160h+var_11C], ecx
0x180006e4a  and     ebx, 2
0x180006e4d  mov     r13d, ecx
0x180006e50  mov     rcx, r12
0x180006e53  setnz   al
0x180006e56  test    rsi, rsi
0x180006e59  mov     [rsp+160h+var_120], eax
0x180006e5d  cmovnz  rdi, rsi
0x180006e61  mov     esi, 3
0x180006e66  mov     edx, esi
0x180006e68  mov     rax, rdi
0x180006e6b  lea     r8d, [rsi-2]
0x180006e6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e74  lea     rcx, aWillNot; "will NOT"
0x180006e7b  xor     r13d, 1
0x180006e7f  lea     rax, aWill; "will"
0x180006e86  mov     edx, esi
0x180006e88  cmovz   rax, rcx
0x180006e8c  lea     r9, aDriversWsBeRem; "Drivers %ws be removed during this pass"...
0x180006e93  mov     [rsp+160h+var_140], rax
0x180006e98  xor     r8d, r8d
0x180006e9b  mov     rax, rdi
0x180006e9e  mov     rcx, r12
0x180006ea1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ea6  test    ebx, ebx
0x180006ea8  jz      short loc_180006EC1
0x180006eaa  lea     r9, aWillOnlyKeepDr; "Will only keep drivers that are install"...
0x180006eb1  xor     r8d, r8d
0x180006eb4  mov     edx, esi
0x180006eb6  mov     rcx, r12
0x180006eb9  mov     rax, rdi
0x180006ebc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ec1  xor     edx, edx
0x180006ec3  lea     ecx, [rdx+20h]
0x180006ec6  call    cs:__imp_pSetupStringTableInitializeEx
0x180006ecc  mov     [rbp+60h+var_78], rax
0x180006ed0  test    rax, rax
0x180006ed3  jnz     short loc_180006EE2
0x180006ed5  call    cs:__imp_GetLastError
0x180006edb  mov     ebx, eax
0x180006edd  jmp     loc_18000733F
0x180006ee2  xor     edx, edx
0x180006ee4  mov     ecx, 0A0h
0x180006ee9  xor     r14d, r14d
0x180006eec  xor     esi, esi
0x180006eee  call    cs:__imp_pSetupStringTableInitializeEx
0x180006ef4  mov     r15, rax
0x180006ef7  test    rax, rax
0x180006efa  jnz     short loc_180006F09
0x180006efc  call    cs:__imp_GetLastError
0x180006f02  mov     ebx, eax
0x180006f04  jmp     loc_18000730B
0x180006f09  xor     edx, edx
0x180006f0b  lea     ecx, [rdx+8]
0x180006f0e  call    cs:__imp_pSetupStringTableInitializeEx
0x180006f14  mov     [rbp+60h+var_80], rax
0x180006f18  test    rax, rax
0x180006f1b  jz      short loc_180006EFC
0x180006f1d  call    cs:__imp_pSetupStringTableInitialize
0x180006f23  mov     rsi, rax
0x180006f26  test    rax, rax
0x180006f29  jnz     short loc_180006F38
0x180006f2b  call    cs:__imp_GetLastError
0x180006f31  mov     ebx, eax
0x180006f33  jmp     loc_180007301
0x180006f38  xor     r9d, r9d
0x180006f3b  xor     r8d, r8d
0x180006f3e  xor     edx, edx
0x180006f40  xor     ecx, ecx
0x180006f42  call    cs:__imp_DriverStoreOpenW
0x180006f48  xor     ecx, ecx
0x180006f4a  mov     r14, rax
0x180006f4d  test    rax, rax
0x180006f50  jz      short loc_180006F2B
0x180006f52  xor     eax, eax
0x180006f54  mov     [rsp+160h+var_110], rcx
0x180006f59  mov     [rbp+60h+var_CC], rax
0x180006f5d  neg     ebx
0x180006f5f  mov     [rbp+60h+var_C4], eax
0x180006f62  mov     [rbp+60h+var_B0], rax
0x180006f66  mov     rax, [rbp+60h+var_70]
0x180006f6a  mov     [rsp+160h+var_F8], rax
0x180006f6f  mov     rax, [rbp+60h+var_68]
0x180006f73  mov     [rsp+160h+var_F0], rax
0x180006f78  mov     eax, [rsp+160h+var_120]
0x180006f7c  mov     [rbp+60h+var_D4], eax
0x180006f7f  mov     rax, [rbp+60h+var_78]
0x180006f83  mov     [rbp+60h+var_A8], rax
0x180006f87  mov     rax, [rbp+60h+var_80]
0x180006f8b  mov     [rbp+60h+var_98], rax
0x180006f8f  sbb     eax, eax
0x180006f91  not     eax
0x180006f93  mov     [rsp+160h+var_108], rcx
0x180006f98  and     eax, 0Ah
0x180006f9b  mov     [rsp+160h+var_100], rcx
0x180006fa0  mov     [rbp+60h+var_C0], rcx
0x180006fa4  lea     rcx, [rbp+60h+var_B0]
0x180006fa8  mov     [rbp+60h+var_D0], eax
0x180006fab  mov     [rsp+160h+var_E8], rdi
0x180006fb0  mov     [rbp+60h+var_E0], r12
0x180006fb4  mov     [rbp+60h+var_D8], r13d
0x180006fb8  mov     [rbp+60h+var_A0], r15
0x180006fbc  mov     [rbp+60h+var_90], rsi
0x180006fc0  mov     [rbp+60h+var_B8], r14
0x180006fc4  call    pUtilGetSystemDriveClusterSize
0x180006fc9  mov     edx, dword ptr [rbp+60h+var_B0]
0x180006fcc  xor     ecx, ecx
0x180006fce  test    eax, eax
0x180006fd0  mov     dword ptr [rbp+60h+var_CC], ecx
0x180006fd3  cmovnz  edx, ecx
0x180006fd6  lea     rcx, [rsp+160h+var_110]
0x180006fdb  mov     dword ptr [rbp+60h+var_B0], edx
0x180006fde  call    PnpCleanDriversNotifyCallback
0x180006fe3  test    eax, eax
0x180006fe5  jnz     short loc_180006FF1
0x180006fe7  mov     ebx, 4C7h
0x180006fec  jmp     loc_180007301
0x180006ff1  mov     rcx, [rbp+60h+var_E0]
0x180006ff5  lea     r9, aProcessingInst; "Processing installed devices..."
0x180006ffc  mov     edx, 4
0x180007001  mov     rax, rdi
0x180007004  lea     r8d, [rdx-3]
0x180007008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000700d  lea     rcx, [rsp+160h+var_110]
0x180007012  call    GetInstalledInfs
0x180007017  mov     rcx, [rbp+60h+var_E0]
0x18000701b  mov     ebx, eax
0x18000701d  test    eax, eax
0x18000701f  jz      short loc_180007043
0x180007021  mov     dword ptr [rsp+160h+var_140], eax
0x180007025  lea     r9, aFailedToGetThe; "Failed to get the set of Driver Store I"...
0x18000702c  mov     eax, 1
0x180007031  mov     r8d, eax
0x180007034  mov     edx, eax
0x180007036  mov     rax, rdi
0x180007039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000703e  jmp     loc_180007301
0x180007043  mov     edx, 4
0x180007048  lea     r9, aGatheringAllDe; "Gathering all device ids..."
0x18000704f  mov     rax, rdi
0x180007052  lea     r8d, [rdx-3]
0x180007056  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000705b  lea     rcx, [rsp+160h+var_110]
0x180007060  call    GetAllDeviceIds
0x180007065  mov     ebx, eax
0x180007067  test    eax, eax
0x180007069  jz      short loc_180007086
0x18000706b  mov     dword ptr [rsp+160h+var_140], eax
0x18000706f  lea     r9, aFailedToGetThe_0; "Failed to get the set of devices ids fo"...
0x180007076  mov     eax, 1
0x18000707b  mov     r8d, eax
0x18000707e  mov     edx, eax
0x180007080  mov     rcx, [rbp+60h+var_E0]
0x180007084  jmp     short loc_180007036
0x180007086  mov     ebx, 1
0x18000708b  lea     rcx, [rsp+160h+var_110]
0x180007090  mov     dword ptr [rbp+60h+var_CC], ebx
0x180007093  call    PnpCleanDriversNotifyCallback
0x180007098  test    eax, eax
0x18000709a  jz      loc_180006FE7
0x1800070a0  mov     rcx, [rbp+60h+var_E0]
0x1800070a4  lea     r9, aProcessingPubl; "Processing published drivers..."
0x1800070ab  mov     r8d, ebx
0x1800070ae  lea     edx, [rbx+3]
0x1800070b1  mov     rax, rdi
0x1800070b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070b9  mov     rcx, [rbp+60h+var_B8]
0x1800070bd  lea     r9, [rsp+160h+var_110]
0x1800070c2  lea     r8, EnumDriverPackageCallback
0x1800070c9  lea     edx, [rbx+5]
0x1800070cc  call    cs:__imp_DriverStoreEnumW
0x1800070d2  test    eax, eax
0x1800070d4  jnz     short loc_1800070EB
0x1800070d6  call    cs:__imp_GetLastError
0x1800070dc  mov     ebx, eax
0x1800070de  mov     dword ptr [rsp+160h+var_140], eax
0x1800070e2  lea     r9, aFailedToEnumer_2; "Failed to enumerate driver packages, Er"...
0x1800070e9  jmp     short loc_1800070FE
0x1800070eb  mov     ebx, dword ptr [rsp+160h+var_110]
0x1800070ef  test    ebx, ebx
0x1800070f1  jz      short loc_180007127
0x1800070f3  mov     dword ptr [rsp+160h+var_140], ebx
0x1800070f7  lea     r9, aFailedToEnumer; "Failed to enumerate driver packages, re"...
0x1800070fe  mov     rcx, [rbp+60h+var_E0]
0x180007102  xor     r8d, r8d
0x180007105  mov     rax, [rsp+160h+var_E8]
0x18000710a  lea     edx, [r8+1]
0x18000710e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007113  test    ebx, ebx
0x180007115  jz      short loc_180007127
0x180007117  mov     dword ptr [rsp+160h+var_140], ebx
0x18000711b  lea     r9, aFailedToGetPub; "Failed to get published Driver Store IN"...
0x180007122  jmp     loc_180007076
0x180007127  lea     rcx, [rsp+160h+var_110]
0x18000712c  call    PnpCleanDriversNotifyCallback
0x180007131  test    eax, eax
0x180007133  jz      loc_180006FE7
0x180007139  mov     rcx, [rbp+60h+var_E0]
0x18000713d  lea     r9, aProcessingDevi; "Processing device ID matches..."
0x180007144  mov     edx, 4
0x180007149  mov     rax, rdi
0x18000714c  lea     r8d, [rdx-3]
0x180007150  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007155  mov     rcx, [rbp+60h+var_A8]
0x180007159  lea     rax, [rsp+160h+var_110]
0x18000715e  xorps   xmm0, xmm0
0x180007161  mov     [rsp+160h+var_140], rax
0x180007166  lea     r9, StrTabEnumDriverStoreDeviceIdSetBestMatchCallback
0x18000716d  mov     r8d, 20h ; ' '
0x180007173  lea     rdx, [rbp+60h+var_60]
0x180007177  movups  [rbp+60h+var_60], xmm0
0x18000717b  movups  [rbp+60h+var_50], xmm0
0x18000717f  call    cs:__imp_pSetupStringTableEnum
0x180007185  test    eax, eax
0x180007187  jnz     short loc_18000719E
0x180007189  call    cs:__imp_GetLastError
0x18000718f  mov     ebx, eax
0x180007191  mov     dword ptr [rsp+160h+var_140], eax
0x180007195  lea     r9, aPsetupstringta; "pSetupStringTableEnum StrTabDriverStore"...
0x18000719c  jmp     short loc_1800071B1
0x18000719e  mov     ebx, dword ptr [rsp+160h+var_110]
0x1800071a2  test    ebx, ebx
0x1800071a4  jz      short loc_1800071DA
0x1800071a6  mov     dword ptr [rsp+160h+var_140], ebx
0x1800071aa  lea     r9, aStrtabenumdriv_0; "StrTabEnumDriverStoreDeviceIdSetBestMat"...
0x1800071b1  mov     rcx, [rbp+60h+var_E0]
0x1800071b5  xor     r8d, r8d
0x1800071b8  mov     rax, [rsp+160h+var_E8]
0x1800071bd  lea     edx, [r8+1]
0x1800071c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071c6  test    ebx, ebx
0x1800071c8  jz      short loc_1800071DA
0x1800071ca  mov     dword ptr [rsp+160h+var_140], ebx
0x1800071ce  lea     r9, aFailedToProces_2; "Failed to process Driver Store INF devi"...
0x1800071d5  jmp     loc_180007076
0x1800071da  neg     r13d
0x1800071dd  lea     rcx, [rsp+160h+var_110]
0x1800071e2  sbb     eax, eax
0x1800071e4  neg     eax
0x1800071e6  add     eax, 2
0x1800071e9  mov     dword ptr [rbp+60h+var_CC], eax
0x1800071ec  call    PnpCleanDriversNotifyCallback
0x1800071f1  test    eax, eax
0x1800071f3  jz      loc_180006FE7
0x1800071f9  mov     rcx, [rbp+60h+var_E0]
0x1800071fd  lea     r9, aProcessingDriv; "Processing driver packages..."
0x180007204  mov     r13d, 1
0x18000720a  mov     rax, rdi
0x18000720d  mov     r8d, r13d
0x180007210  lea     edx, [r13+3]
0x180007214  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007219  lea     rcx, [rsp+160h+var_110]
0x18000721e  call    ProcessDriverStoreInfsForRemoval
0x180007223  mov     ebx, eax
0x180007225  mov     r8d, r13d
0x180007228  test    eax, eax
0x18000722a  jz      short loc_18000723F
0x18000722c  mov     dword ptr [rsp+160h+var_140], eax
0x180007230  lea     r9, aFailedToProces_1; "Failed to process Driver Store INFs for"...
0x180007237  mov     edx, r13d
0x18000723a  jmp     loc_180007080
0x18000723f  cmp     [rbp+60h+var_D8], 0
0x180007243  lea     rax, aToRemove; "to remove"
0x18000724a  lea     rcx, aRemoved; "removed"
0x180007251  mov     edx, 3
0x180007256  cmovz   rcx, rax
0x18000725a  lea     r9, aDriverPackages; "Driver packages %ws: %d"
0x180007261  mov     eax, dword ptr [rbp+60h+var_CC+4]
0x180007264  mov     [rsp+160h+var_138], eax
  ... truncated ...
```
