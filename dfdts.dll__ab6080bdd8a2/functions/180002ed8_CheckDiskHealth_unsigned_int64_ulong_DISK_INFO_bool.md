# CheckDiskHealth(unsigned __int64,ulong *,_DISK_INFO *,bool)

- ea: `0x180002ed8`
- end: `0x180003399`
- name: `?CheckDiskHealth@@YAK_KPEAKPEAU_DISK_INFO@@_N@Z`
- size: `1217`
- prototype: `__int64 __fastcall(__int64, unsigned int *, struct _DISK_INFO *, char)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180002790`

## callees

- `0x180002c90`
- `0x180002d24`
- `0x180002ed8`
- `0x1800033a0`
- `0x180003694`
- `0x180003750`
- `0x1800037bc`
- `0x180003924`
- `0x180003984`
- `0x1800039fc`
- `0x180003aac`
- `0x180003edc`
- `0x1800040b8`
- `0x1800058f4`
- `0x180005b98`
- `0x180005d68`
- `0x180005dac`
- `0x180006020`
- `0x1800064fc`
- `0x180006c74`
- `0x180008370`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180002f6e`
- `KERNEL32!GetLastError` at `0x180003353`
- `KERNEL32!GetLastError` at `0x180002f6e`
- `KERNEL32!GetLastError` at `0x180003353`
- `ADVAPI32!RegOpenKeyExW` at `0x1800031f6`
- `ADVAPI32!RegOpenKeyExW` at `0x1800031f6`
- `ADVAPI32!RegCloseKey` at `0x18000325a`
- `ADVAPI32!RegCloseKey` at `0x18000325a`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x180003337`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x180003337`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x180002f5a`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x180002f5a`

## pseudocode

```c
__int64 __fastcall CheckDiskHealth(__int64 a1, unsigned int *a2, struct _DISK_INFO *a3, char a4)
{
  unsigned int DWORDFromReg; // ebx
  unsigned __int8 v6; // r13
  HDEVINFO ClassDevsW; // r14
  DWORD LastError; // eax
  DWORD v9; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  DWORD v12; // esi
  unsigned int v13; // eax
  DfdDuid *v14; // rbx
  unsigned __int16 *HardwareId; // rax
  __int64 v16; // rdx
  unsigned int v17; // eax
  unsigned int v18; // ebx
  unsigned __int16 *v19; // rax
  unsigned int v20; // eax
  int v21; // esi
  unsigned __int16 *v22; // rax
  DfdManager *v23; // rcx
  bool v24; // r14
  unsigned int v25; // eax
  LSTATUS v26; // eax
  unsigned int v27; // edx
  bool v28; // zf
  char v30; // [rsp+30h] [rbp-D0h]
  unsigned int v32; // [rsp+34h] [rbp-CCh]
  DWORD v33; // [rsp+38h] [rbp-C8h]
  unsigned int v34; // [rsp+3Ch] [rbp-C4h]
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  HDEVINFO v36; // [rsp+48h] [rbp-B8h]
  _QWORD v37[4]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v38; // [rsp+70h] [rbp-90h]
  _BYTE v39[24]; // [rsp+80h] [rbp-80h] BYREF
  DfdDuid *v40; // [rsp+98h] [rbp-68h]

  v38 = g_RegHandle;
  if ( *a2 )
  {
    v6 = 1;
    DWORDFromReg = GetDWORDFromReg(
                     L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\DiskDiagnostics\\FailingDiskList",
                     L"SMARTFailureInject");
  }
  else
  {
    DWORDFromReg = 0;
    v6 = 0;
  }
  v32 = DWORDFromReg;
  *a2 = 0;
  ClassDevsW = SetupDiGetClassDevsW(&GUID_DEVINTERFACE_DISK, 0, 0, 0x12u);
  v36 = ClassDevsW;
  if ( ClassDevsW == (HDEVINFO)-1LL )
  {
    LastError = GetLastError();
    v9 = LastError;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v11 = 10;
      goto LABEL_77;
    }
    return v9;
  }
  v30 = 0;
  v34 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_0ae963c2f6a739e5a6734f4927a5ba0b_Traceguids, ClassDevsW);
  v12 = 0;
  while ( 1 )
  {
    DiskContext::DiskContext((DiskContext *)v39, ClassDevsW, DWORDFromReg);
    v13 = DiskContext::Set((__int64)v39, v6, v12);
    if ( !v13 )
      break;
    if ( v13 == 259 )
    {
      v9 = 0;
      goto LABEL_67;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_0ae963c2f6a739e5a6734f4927a5ba0b_Traceguids, v13);
    ++v12;
LABEL_64:
    DiskContext::~DiskContext((DiskContext *)v39);
  }
  v33 = ++v12;
  if ( !v6 )
  {
    v14 = v40;
    if ( !v40 )
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_63;
      HardwareId = DiskContext::GetHardwareId((DiskContext *)v39);
      v16 = 13;
LABEL_23:
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, WPP_0ae963c2f6a739e5a6734f4927a5ba0b_Traceguids, HardwareId);
LABEL_63:
      DWORDFromReg = v32;
      goto LABEL_64;
    }
    if ( !*((_BYTE *)v40 + 9) )
      DfdDuid::QueryBusType(v40);
    if ( *((_DWORD *)v14 + 7) == 8 )
    {
      SetSMARTFailureStream((struct DiskContext *)v39, 2u);
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_63;
      HardwareId = DiskContext::GetHardwareId((DiskContext *)v39);
      v16 = 14;
      goto LABEL_23;
    }
  }
  v17 = DfdDuid::Query(v40);
  v18 = v17;
  if ( a4 && !v6 && v17 )
  {
    v19 = DiskContext::GetHardwareId((DiskContext *)v39);
    SetDuidFailureSQM(v18, v19);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v20 = (unsigned int)DiskContext::GetHardwareId((DiskContext *)v39);
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        (unsigned int)WPP_0ae963c2f6a739e5a6734f4927a5ba0b_Traceguids,
        v20,
        v18);
    }
    goto LABEL_63;
  }
  v37[0] = v39;
  v37[1] = v40;
  v21 = 0;
  v37[2] = 16;
  v37[3] = 0;
  v22 = DiskContext::GetHardwareId((DiskContext *)v39);
  v24 = DfdManager::ExistInIgnoreList(v23, v22);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v25 = (unsigned int)DiskContext::GetHardwareId((DiskContext *)v39);
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      (unsigned int)WPP_0ae963c2f6a739e5a6734f4927a5ba0b_Traceguids,
      v25,
      v24);
  }
  if ( !v6 && !v24 )
    ++v34;
  hKey = 0;
  v26 = RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\DiskDiagnostics\\FailingDiskList",
          0,
          0x20019u,
          &hKey);
  v9 = v26;
  if ( v26 )
  {
    if ( v26 == 2 )
    {
      v9 = 0;
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        (unsigned int)WPP_3ef5aefce1013aeb7f7a24910fe71d4f_Traceguids,
        (unsigned int)L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\DiskDiagnostics\\FailingDiskList",
        v26);
    }
  }
  else
  {
    v21 = DfdManager::CheckDFDRegistry((DfdManager *)v37, hKey);
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v9 != 14 )
  {
    if ( !v9 && !v6 )
    {
      if ( v21 )
      {
        if ( !v24 )
          v30 = 1;
      }
      else
      {
        DfdManager::AddDuid((DfdManager *)v37);
        if ( v24 )
        {
          v27 = 1;
        }
        else
        {
          ++*a2;
          v27 = 0;
        }
        SetSMARTFailureStream((struct DiskContext *)v39, v27);
        DfdManager::LogSMARTEvent((DfdManager *)v37, v38, v24);
      }
    }
    DfdManager::~DfdManager((DfdManager *)v37);
    ClassDevsW = v36;
    v12 = v33;
    goto LABEL_63;
  }
  DfdManager::~DfdManager((DfdManager *)v37);
  v12 = v33;
  ClassDevsW = v36;
LABEL_67:
  DiskContext::~DiskContext((DiskContext *)v39);
  if ( !v6 )
  {
    v28 = *a2 == 0;
    if ( *a2 )
    {
      SetSMARTFailureDiskCount(0x42Bu, v12);
      SetSMARTFailureDiskCount(0x42Cu, v34);
      v28 = *a2 == 0;
    }
    if ( v28 && v30 == 1 )
      *a2 = 1;
  }
  if ( !SetupDiDestroyDeviceInfoList(ClassDevsW)
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    LastError = GetLastError();
    v11 = 17;
    v10 = WPP_GLOBAL_Control;
LABEL_77:
    WPP_SF_d(v10[2], v11, WPP_0ae963c2f6a739e5a6734f4927a5ba0b_Traceguids, LastError);
  }
  return v9;
}

```

## disassembly

```asm
0x180002ed8  push    rbp
0x180002eda  push    rbx
0x180002edb  push    rsi
0x180002edc  push    rdi
0x180002edd  push    r12
0x180002edf  push    r13
0x180002ee1  push    r14
0x180002ee3  push    r15
0x180002ee5  lea     rbp, [rsp-228h]
0x180002eed  sub     rsp, 328h
0x180002ef4  mov     rax, cs:__security_cookie
0x180002efb  xor     rax, rsp
0x180002efe  mov     [rbp+260h+var_50], rax
0x180002f05  mov     [rsp+360h+var_32F], r9b
0x180002f0a  mov     r15, rdx
0x180002f0d  mov     rax, cs:?g_RegHandle@@3_KA; unsigned __int64 g_RegHandle
0x180002f14  mov     [rsp+360h+var_2F0], rax
0x180002f19  cmp     dword ptr [rdx], 0
0x180002f1c  jnz     short loc_180002F25
0x180002f1e  xor     ebx, ebx
0x180002f20  xor     r13b, r13b
0x180002f23  jmp     short loc_180002F3D
0x180002f25  mov     r13b, 1
0x180002f28  lea     rdx, aSmartfailurein; "SMARTFailureInject"
0x180002f2f  lea     rcx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180002f36  call    ?GetDWORDFromReg@@YAKPEBG0@Z; GetDWORDFromReg(ushort const *,ushort const *)
0x180002f3b  mov     ebx, eax
0x180002f3d  mov     [rsp+360h+var_32C], ebx
0x180002f41  mov     dword ptr [r15], 0
0x180002f48  mov     r9d, 12h; Flags
0x180002f4e  xor     r8d, r8d; hwndParent
0x180002f51  xor     edx, edx; Enumerator
0x180002f53  lea     rcx, GUID_DEVINTERFACE_DISK; ClassGuid
0x180002f5a  call    cs:__imp_SetupDiGetClassDevsW
0x180002f60  mov     r14, rax
0x180002f63  mov     [rsp+360h+var_318], rax
0x180002f68  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180002f6c  jnz     short loc_180002FA7
0x180002f6e  call    cs:__imp_GetLastError
0x180002f74  mov     ebx, eax
0x180002f76  lea     rdi, WPP_GLOBAL_Control
0x180002f7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f84  cmp     rcx, rdi
0x180002f87  jz      loc_180003374
0x180002f8d  test    byte ptr [rcx+1Ch], 1
0x180002f91  jz      loc_180003374
0x180002f97  lea     edx, [r14+0Bh]
0x180002f9b  lea     r8, WPP_0ae963c2f6a739e5a6734f4927a5ba0b_Traceguids
0x180002fa2  jmp     loc_180003368
0x180002fa7  xor     al, al
0x180002fa9  mov     [rsp+360h+var_330], al
0x180002fad  xor     edx, edx
0x180002faf  mov     [rsp+360h+var_324], edx
0x180002fb3  lea     rdi, WPP_GLOBAL_Control
0x180002fba  lea     r12, WPP_0ae963c2f6a739e5a6734f4927a5ba0b_Traceguids
0x180002fc1  mov     rcx, cs:WPP_GLOBAL_Control
0x180002fc8  cmp     rcx, rdi
0x180002fcb  jz      short loc_180002FE7
0x180002fcd  test    byte ptr [rcx+1Ch], 4
0x180002fd1  jz      short loc_180002FE7
0x180002fd3  mov     edx, 0Bh
0x180002fd8  mov     r9, r14
0x180002fdb  mov     r8, r12
0x180002fde  mov     rcx, [rcx+10h]
0x180002fe2  call    WPP_SF_q
0x180002fe7  xor     esi, esi
0x180002fe9  mov     r8d, ebx; unsigned int
0x180002fec  mov     rdx, r14; void *
0x180002fef  lea     rcx, [rbp+260h+var_2E0]; this
0x180002ff3  call    ??0DiskContext@@QEAA@PEAXK@Z; DiskContext::DiskContext(void *,ulong)
0x180002ff8  nop
0x180002ff9  mov     r8d, esi
0x180002ffc  movzx   edx, r13b
0x180003000  lea     rcx, [rbp+260h+var_2E0]
0x180003004  call    ?Set@DiskContext@@QEAAKW4DFD_IDENTITY@@K@Z; DiskContext::Set(DFD_IDENTITY,ulong)
0x180003009  test    eax, eax
0x18000300b  jz      short loc_180003045
0x18000300d  cmp     eax, 103h
0x180003012  jz      loc_1800032DA
0x180003018  mov     rcx, cs:WPP_GLOBAL_Control
0x18000301f  cmp     rcx, rdi
0x180003022  jz      short loc_18000303E
0x180003024  test    byte ptr [rcx+1Ch], 1
0x180003028  jz      short loc_18000303E
0x18000302a  mov     edx, 0Ch
0x18000302f  mov     r9d, eax
0x180003032  mov     r8, r12
0x180003035  mov     rcx, [rcx+10h]
0x180003039  call    WPP_SF_d
0x18000303e  inc     esi
0x180003040  jmp     loc_1800032CC
0x180003045  inc     esi
0x180003047  mov     [rsp+360h+var_328], esi
0x18000304b  test    r13b, r13b
0x18000304e  jnz     loc_1800030DB
0x180003054  mov     rbx, [rbp+260h+var_2C8]
0x180003058  test    rbx, rbx
0x18000305b  jnz     short loc_180003097
0x18000305d  mov     rax, cs:WPP_GLOBAL_Control
0x180003064  cmp     rax, rdi
0x180003067  jz      short loc_180003092
0x180003069  test    byte ptr [rax+1Ch], 4
0x18000306d  jz      short loc_180003092
0x18000306f  lea     rcx, [rbp+260h+var_2E0]; this
0x180003073  call    ?GetHardwareId@DiskContext@@QEAAPEAGXZ; DiskContext::GetHardwareId(void)
0x180003078  lea     edx, [rbx+0Dh]
0x18000307b  mov     r9, rax
0x18000307e  mov     r8, r12
0x180003081  mov     rcx, cs:WPP_GLOBAL_Control
0x180003088  mov     rcx, [rcx+10h]
0x18000308c  call    WPP_SF_S
0x180003091  nop
0x180003092  jmp     loc_1800032C8
0x180003097  cmp     byte ptr [rbx+9], 0
0x18000309b  jnz     short loc_1800030A5
0x18000309d  mov     rcx, rbx; this
0x1800030a0  call    ?QueryBusType@DfdDuid@@AEAAKXZ; DfdDuid::QueryBusType(void)
0x1800030a5  cmp     dword ptr [rbx+1Ch], 8
0x1800030a9  jnz     short loc_1800030DB
0x1800030ab  mov     edx, 2; unsigned int
0x1800030b0  lea     rcx, [rbp+260h+var_2E0]; this
0x1800030b4  call    ?SetSMARTFailureStream@@YAXPEAVDiskContext@@K@Z; SetSMARTFailureStream(DiskContext *,ulong)
0x1800030b9  mov     rax, cs:WPP_GLOBAL_Control
0x1800030c0  cmp     rax, rdi
0x1800030c3  jz      short loc_180003092
0x1800030c5  test    byte ptr [rax+1Ch], 4
0x1800030c9  jz      short loc_180003092
0x1800030cb  lea     rcx, [rbp+260h+var_2E0]; this
0x1800030cf  call    ?GetHardwareId@DiskContext@@QEAAPEAGXZ; DiskContext::GetHardwareId(void)
0x1800030d4  mov     edx, 0Eh
0x1800030d9  jmp     short loc_18000307B
0x1800030db  mov     rcx, [rbp+260h+var_2C8]; this
0x1800030df  call    ?Query@DfdDuid@@QEAAKXZ; DfdDuid::Query(void)
0x1800030e4  mov     ebx, eax
0x1800030e6  cmp     [rsp+360h+var_32F], 0
0x1800030eb  jz      short loc_180003150
0x1800030ed  test    r13b, r13b
0x1800030f0  jnz     short loc_180003150
0x1800030f2  test    eax, eax
0x1800030f4  jz      short loc_180003150
0x1800030f6  lea     rcx, [rbp+260h+var_2E0]; this
0x1800030fa  call    ?GetHardwareId@DiskContext@@QEAAPEAGXZ; DiskContext::GetHardwareId(void)
0x1800030ff  mov     rdx, rax; unsigned __int16 *
0x180003102  mov     ecx, ebx; unsigned int
0x180003104  call    ?SetDuidFailureSQM@@YAXKPEAG@Z; SetDuidFailureSQM(ulong,ushort *)
0x180003109  mov     rax, cs:WPP_GLOBAL_Control
0x180003110  cmp     rax, rdi
0x180003113  jz      loc_180003092
0x180003119  test    byte ptr [rax+1Ch], 1
0x18000311d  jz      loc_180003092
0x180003123  lea     rcx, [rbp+260h+var_2E0]; this
0x180003127  call    ?GetHardwareId@DiskContext@@QEAAPEAGXZ; DiskContext::GetHardwareId(void)
0x18000312c  mov     edx, 0Fh
0x180003131  mov     dword ptr [rsp+360h+phkResult], ebx
0x180003135  mov     r9, rax
0x180003138  mov     r8, r12
0x18000313b  mov     rcx, cs:WPP_GLOBAL_Control
0x180003142  mov     rcx, [rcx+10h]
0x180003146  call    WPP_SF_Sd
0x18000314b  jmp     loc_180003092
0x180003150  lea     rax, [rbp+260h+var_2E0]
0x180003154  mov     [rsp+360h+var_310], rax
0x180003159  mov     rax, [rbp+260h+var_2C8]
0x18000315d  mov     [rsp+360h+var_308], rax
0x180003162  xor     esi, esi
0x180003164  mov     [rsp+360h+var_300], 10h
0x18000316d  lea     ebx, [rsi+10h]
0x180003170  mov     [rsp+360h+var_2F8], rsi
0x180003175  lea     rcx, [rbp+260h+var_2E0]; this
0x180003179  call    ?GetHardwareId@DiskContext@@QEAAPEAGXZ; DiskContext::GetHardwareId(void)
0x18000317e  mov     rdx, rax; unsigned __int16 *
0x180003181  call    ?ExistInIgnoreList@DfdManager@@QEAA_NPEAG@Z; DfdManager::ExistInIgnoreList(ushort *)
0x180003186  movzx   r14d, al
0x18000318a  mov     rcx, cs:WPP_GLOBAL_Control
0x180003191  cmp     rcx, rdi
0x180003194  jz      short loc_1800031C2
0x180003196  test    byte ptr [rcx+1Ch], 4
0x18000319a  jz      short loc_1800031C2
0x18000319c  lea     rcx, [rbp+260h+var_2E0]; this
0x1800031a0  call    ?GetHardwareId@DiskContext@@QEAAPEAGXZ; DiskContext::GetHardwareId(void)
0x1800031a5  mov     edx, ebx
0x1800031a7  mov     dword ptr [rsp+360h+phkResult], r14d
0x1800031ac  mov     r9, rax
0x1800031af  mov     r8, r12
0x1800031b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800031b9  mov     rcx, [rcx+10h]
0x1800031bd  call    WPP_SF_Sd
0x1800031c2  test    r13b, r13b
0x1800031c5  jnz     short loc_1800031D0
0x1800031c7  test    r14b, r14b
0x1800031ca  jnz     short loc_1800031D0
0x1800031cc  inc     [rsp+360h+var_324]
0x1800031d0  mov     [rsp+360h+hKey], rsi
0x1800031d5  lea     rax, [rsp+360h+hKey]
0x1800031da  mov     [rsp+360h+phkResult], rax; phkResult
0x1800031df  mov     r9d, 20019h; samDesired
0x1800031e5  xor     r8d, r8d; ulOptions
0x1800031e8  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800031ef  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800031f6  call    cs:__imp_RegOpenKeyExW
0x1800031fc  mov     ebx, eax
0x1800031fe  test    eax, eax
0x180003200  jz      short loc_18000323F
0x180003202  cmp     eax, 2
0x180003205  jnz     short loc_18000320B
0x180003207  xor     ebx, ebx
0x180003209  jmp     short loc_180003250
0x18000320b  mov     rcx, cs:WPP_GLOBAL_Control
0x180003212  cmp     rcx, rdi
0x180003215  jz      short loc_180003250
0x180003217  test    byte ptr [rcx+1Ch], 1
0x18000321b  jz      short loc_180003250
0x18000321d  mov     edx, 14h
0x180003222  mov     dword ptr [rsp+360h+phkResult], eax
0x180003226  lea     r9, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18000322d  lea     r8, WPP_3ef5aefce1013aeb7f7a24910fe71d4f_Traceguids
0x180003234  mov     rcx, [rcx+10h]
0x180003238  call    WPP_SF_Sd
0x18000323d  jmp     short loc_180003250
0x18000323f  mov     rdx, [rsp+360h+hKey]; hKey
0x180003244  lea     rcx, [rsp+360h+var_310]; this
0x180003249  call    ?CheckDFDRegistry@DfdManager@@QEAAHPEAUHKEY__@@@Z; DfdManager::CheckDFDRegistry(HKEY__ *)
0x18000324e  mov     esi, eax
0x180003250  mov     rcx, [rsp+360h+hKey]; hKey
0x180003255  test    rcx, rcx
0x180003258  jz      short loc_180003260
0x18000325a  call    cs:__imp_RegCloseKey
0x180003260  cmp     ebx, 0Eh
0x180003263  jz      short loc_1800032DE
0x180003265  test    ebx, ebx
0x180003267  jnz     short loc_1800032B4
0x180003269  test    r13b, r13b
0x18000326c  jnz     short loc_1800032B4
0x18000326e  test    esi, esi
0x180003270  jz      short loc_18000327E
0x180003272  test    r14b, r14b
0x180003275  jnz     short loc_1800032B4
0x180003277  mov     [rsp+360h+var_330], 1
0x18000327c  jmp     short loc_1800032B4
0x18000327e  lea     rcx, [rsp+360h+var_310]; this
0x180003283  call    ?AddDuid@DfdManager@@QEAAKXZ; SYSTEM writes FailingDiskList\{generated-guid}\DiskUniqueID from physical disk DUID; parent key protected, no low-priv-controlled path/name or weak inherited ACL found.
0x180003288  test    r14b, r14b
0x18000328b  jnz     short loc_180003294
0x18000328d  inc     dword ptr [r15]
0x180003290  xor     edx, edx
0x180003292  jmp     short loc_180003299
0x180003294  mov     edx, 1; unsigned int
0x180003299  lea     rcx, [rbp+260h+var_2E0]; this
0x18000329d  call    ?SetSMARTFailureStream@@YAXPEAVDiskContext@@K@Z; SetSMARTFailureStream(DiskContext *,ulong)
0x1800032a2  mov     r8b, r14b; bool
0x1800032a5  mov     rdx, [rsp+360h+var_2F0]; unsigned __int64
0x1800032aa  lea     rcx, [rsp+360h+var_310]; this
0x1800032af  call    ?LogSMARTEvent@DfdManager@@QEAAK_K_N@Z; DfdManager::LogSMARTEvent(unsigned __int64,bool)
0x1800032b4  lea     rcx, [rsp+360h+var_310]; this
0x1800032b9  call    ??1DfdManager@@QEAA@XZ; DfdManager::~DfdManager(void)
0x1800032be  nop
0x1800032bf  mov     r14, [rsp+360h+var_318]
0x1800032c4  mov     esi, [rsp+360h+var_328]
0x1800032c8  mov     ebx, [rsp+360h+var_32C]
0x1800032cc  lea     rcx, [rbp+260h+var_2E0]; this
0x1800032d0  call    ??1DiskContext@@QEAA@XZ; DiskContext::~DiskContext(void)
0x1800032d5  jmp     loc_180002FE9
0x1800032da  xor     ebx, ebx
0x1800032dc  jmp     short loc_1800032F2
0x1800032de  lea     rcx, [rsp+360h+var_310]; this
0x1800032e3  call    ??1DfdManager@@QEAA@XZ; DfdManager::~DfdManager(void)
0x1800032e8  nop
0x1800032e9  mov     esi, [rsp+360h+var_328]
0x1800032ed  mov     r14, [rsp+360h+var_318]
0x1800032f2  lea     rcx, [rbp+260h+var_2E0]; this
0x1800032f6  call    ??1DiskContext@@QEAA@XZ; DiskContext::~DiskContext(void)
0x1800032fb  test    r13b, r13b
0x1800032fe  jnz     short loc_180003334
0x180003300  cmp     dword ptr [r15], 0
0x180003304  jbe     short loc_180003324
0x180003306  mov     edx, esi; unsigned int
0x180003308  mov     ecx, 42Bh; unsigned int
0x18000330d  call    ?SetSMARTFailureDiskCount@@YAXKK@Z; SetSMARTFailureDiskCount(ulong,ulong)
0x180003312  mov     edx, [rsp+360h+var_324]; unsigned int
0x180003316  mov     ecx, 42Ch; unsigned int
0x18000331b  call    ?SetSMARTFailureDiskCount@@YAXKK@Z; SetSMARTFailureDiskCount(ulong,ulong)
0x180003320  cmp     dword ptr [r15], 0
0x180003324  jnz     short loc_180003334
0x180003326  cmp     [rsp+360h+var_330], 1
0x18000332b  jnz     short loc_180003334
0x18000332d  mov     dword ptr [r15], 1
0x180003334  mov     rcx, r14; DeviceInfoSet
0x180003337  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x18000333d  test    eax, eax
0x18000333f  jnz     short loc_180003374
0x180003341  mov     rax, cs:WPP_GLOBAL_Control
0x180003348  cmp     rax, rdi
0x18000334b  jz      short loc_180003374
0x18000334d  test    byte ptr [rax+1Ch], 2
0x180003351  jz      short loc_180003374
0x180003353  call    cs:__imp_GetLastError
0x180003359  mov     edx, 11h
0x18000335e  mov     r8, r12
0x180003361  mov     rcx, cs:WPP_GLOBAL_Control
0x180003368  mov     r9d, eax
  ... truncated ...
```
