# CFhService::StartServiceW(void)

- ea: `0x180001950`
- end: `0x180001f0c`
- name: `?StartServiceW@CFhService@@QEAAJXZ`
- size: `1468`
- prototype: `__int64 __fastcall(CFhService *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18000d810`

## callees

- `0x1800012d0`
- `0x180001690`
- `0x180001950`
- `0x180001f20`
- `0x180002480`
- `0x1800026a0`
- `0x180002f30`
- `0x18000ca14`
- `0x18000d840`
- `0x18000da98`
- `0x180013010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180001cde`
- `ADVAPI32!RegCloseKey` at `0x180001ef7`
- `ADVAPI32!RegCloseKey` at `0x180001cde`
- `ADVAPI32!RegCloseKey` at `0x180001ef7`
- `ADVAPI32!RegGetValueW` at `0x180001cb9`
- `ADVAPI32!RegGetValueW` at `0x180001cb9`
- `ADVAPI32!RegOpenKeyExW` at `0x180001c76`
- `ADVAPI32!RegOpenKeyExW` at `0x180001c76`
- `ADVAPI32!RegisterServiceCtrlHandlerExW` at `0x180001a9f`
- `ADVAPI32!RegisterServiceCtrlHandlerExW` at `0x180001a9f`
- `KERNEL32!CreateEventW` at `0x180001a34`
- `KERNEL32!CreateEventW` at `0x180001a34`
- `KERNEL32!GetLastError` at `0x180001a4d`
- `KERNEL32!GetLastError` at `0x180001ab1`
- `KERNEL32!GetLastError` at `0x180001b56`
- `KERNEL32!GetLastError` at `0x180001d15`
- `KERNEL32!GetLastError` at `0x180001a4d`
- `KERNEL32!GetLastError` at `0x180001ab1`
- `KERNEL32!GetLastError` at `0x180001b56`
- `KERNEL32!GetLastError` at `0x180001d15`
- `WTSAPI32!WTSFreeMemory` at `0x180001d8e`
- `WTSAPI32!WTSFreeMemory` at `0x180001d8e`
- `WTSAPI32!WTSEnumerateSessionsW` at `0x180001d0b`
- `WTSAPI32!WTSEnumerateSessionsW` at `0x180001d0b`
- `POWRPROF!PowerSettingRegisterNotification` at `0x180001b4c`
- `POWRPROF!PowerSettingRegisterNotification` at `0x180001b4c`

## string_xrefs

- `0x180001c68`: `System\CurrentControlSet\Services\fhsvc\Parameters`

## pseudocode

```c
__int64 __fastcall CFhService::StartServiceW(CFhService *this)
{
  PVOID *v1; // rcx
  unsigned int v2; // ebx
  int v3; // r8d
  signed int LastError; // eax
  __int64 v5; // rdx
  signed int v6; // eax
  int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // r9
  CManagerThread *v10; // rcx
  signed int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // r8d
  int v15; // eax
  signed int v16; // eax
  unsigned int v17; // ebx
  unsigned int i; // r8d
  CFhService *v19; // rcx
  int started; // eax
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  int v24; // eax
  signed int v25; // edi
  CFhService *pCount; // [rsp+60h] [rbp+8h] BYREF
  PWTS_SESSION_INFOW ppSessionInfo; // [rsp+68h] [rbp+10h] BYREF
  HKEY hkey; // [rsp+70h] [rbp+18h] BYREF

  pCount = this;
  hkey = 0;
  v1 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_305fb7554e703b1695bfea0e3f3a03b2_Traceguids);
    v1 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !qword_1800198C0 )
  {
    v2 = -2147418113;
    if ( v1 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v1 + 28) & 1) == 0 )
        goto LABEL_82;
      WPP_SF_d(v1[2], 11, &WPP_305fb7554e703b1695bfea0e3f3a03b2_Traceguids, 2147549183LL);
      goto LABEL_81;
    }
LABEL_85:
    CFhService::ShutdownService((CFhService *)&g_Service);
    goto LABEL_90;
  }
  xmmword_180019888 = 0;
  *(__int128 *)((char *)&xmmword_180019888 + 12) = 0;
  *(_QWORD *)&xmmword_180019888 = 0x100000030LL;
  dword_1800198A0 = 0;
  dword_1800198B8 = 2;
  qword_1800198B0 = CreateEventW(0, 1, 0, 0);
  if ( !qword_1800198B0 )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    v1 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = 12;
LABEL_33:
      WPP_SF_d(v1[2], v5, &WPP_305fb7554e703b1695bfea0e3f3a03b2_Traceguids, v2);
      v1 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_34;
    }
    goto LABEL_34;
  }
  if ( !dword_1800198D4 )
  {
    g_Service = RegisterServiceCtrlHandlerExW(
                  L"fhsvc",
                  (LPHANDLER_FUNCTION_EX)CFhService::ServiceControlHandler,
                  &g_Service);
    if ( !g_Service )
    {
      v6 = GetLastError();
      v2 = v6;
      if ( v6 > 0 )
        v2 = (unsigned __int16)v6 | 0x80070000;
      v1 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v5 = 13;
        goto LABEL_33;
      }
LABEL_34:
      if ( (v2 & 0x80000000) == 0 )
        goto LABEL_87;
LABEL_82:
      if ( v1 != &WPP_GLOBAL_Control && (*((_BYTE *)v1 + 28) & 1) != 0 )
        WPP_SF_(v1[2], 21, &WPP_305fb7554e703b1695bfea0e3f3a03b2_Traceguids);
      goto LABEL_85;
    }
  }
  v7 = CFhService::ReportStatus((CFhService *)&g_Service, 2, v3, 1, 0x2710u);
  v2 = v7;
  if ( v7 < 0 )
  {
    v1 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_85;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_82;
    v8 = 14;
    v9 = (unsigned int)v7;
    goto LABEL_80;
  }
  if ( PowerSettingRegisterNotification(&GUID_LOW_POWER_EPOCH, 1u, g_Service, &RegistrationHandle) )
  {
    v11 = GetLastError();
    v2 = v11;
    if ( v11 > 0 )
      v2 = (unsigned __int16)v11 | 0x80070000;
    v1 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = 15;
      goto LABEL_33;
    }
    goto LABEL_34;
  }
  v12 = CManagerThread::Start(v10, (__int64)qword_1800198B0);
  v2 = v12;
  if ( v12 < 0 )
  {
    v1 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_85;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_82;
    v8 = 16;
    v9 = (unsigned int)v12;
    goto LABEL_80;
  }
  v13 = RpcRegisterServer();
  v2 = v13;
  if ( v13 < 0 )
  {
    v1 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_85;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_82;
    v8 = 17;
    v9 = (unsigned int)v13;
    goto LABEL_80;
  }
  v15 = CFhService::ReportStatus((CFhService *)&g_Service, 4, v14, 0, 0);
  v2 = v15;
  if ( v15 < 0 )
  {
    v1 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_85;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_82;
    v8 = 18;
    v9 = (unsigned int)v15;
    goto LABEL_80;
  }
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\fhsvc\\Parameters", 0, 0x20019u, &hkey) )
  {
    LODWORD(ppSessionInfo) = 0;
    LODWORD(pCount) = 4;
    if ( !RegGetValueW(hkey, 0, L"TestFlags", 0x10u, 0, &ppSessionInfo, (LPDWORD)&pCount) && (_DWORD)pCount == 4 )
      dword_180019A78 = (int)ppSessionInfo;
    if ( hkey )
    {
      RegCloseKey(hkey);
      hkey = 0;
    }
  }
  ppSessionInfo = 0;
  LODWORD(pCount) = 0;
  if ( WTSEnumerateSessionsW(0, 0, 1u, &ppSessionInfo, (DWORD *)&pCount) )
  {
    v17 = 0;
    for ( i = (unsigned int)pCount; v17 < i; ++v17 )
    {
      if ( ppSessionInfo[v17].State == WTSActive )
      {
        CManagerThread::QueueBackupForLoggedOnUser((CManagerThread *)(3LL * v17), ppSessionInfo[v17].SessionId);
        i = (unsigned int)pCount;
      }
    }
  }
  else
  {
    v16 = GetLastError();
    if ( v16 > 0 )
      v16 = (unsigned __int16)v16 | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        101,
        &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
        (unsigned int)v16);
  }
  v19 = (CFhService *)ppSessionInfo;
  if ( ppSessionInfo )
    WTSFreeMemory(ppSessionInfo);
  started = CFhService::SetServiceStartType(v19, dword_1800198E8 == 0);
  v2 = started;
  if ( started < 0 )
  {
    v1 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_85;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_82;
    LOBYTE(v23) = dword_1800198E8 != 0;
    WPP_SF_cd(*((_QWORD *)WPP_GLOBAL_Control + 2), v21, v22, v23, started);
LABEL_81:
    v1 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_82;
  }
  v24 = (*(__int64 (__fastcall **)(__int64 *, const WCHAR *, void *, void (__fastcall *)(CFhService *, unsigned __int8), HANDLE *, int))(qword_1800198C0 + 192))(
          &qword_1800198A8,
          L"fhsvc",
          qword_1800198B0,
          CFhService::StopServiceCallback,
          &g_Service,
          8);
  v25 = v24;
  if ( v24 > 0 )
    v25 = (unsigned __int16)v24 | 0x80070000;
  v1 = (PVOID *)WPP_GLOBAL_Control;
  if ( v25 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      50,
      &WPP_305fb7554e703b1695bfea0e3f3a03b2_Traceguids,
      (unsigned int)v25);
    v2 = v25;
    v1 = (PVOID *)WPP_GLOBAL_Control;
LABEL_77:
    if ( v1 == &WPP_GLOBAL_Control )
      goto LABEL_85;
    if ( (*((_BYTE *)v1 + 28) & 1) == 0 )
      goto LABEL_82;
    v8 = 20;
    v9 = (unsigned int)v25;
LABEL_80:
    WPP_SF_d(v1[2], v8, &WPP_305fb7554e703b1695bfea0e3f3a03b2_Traceguids, v9);
    goto LABEL_81;
  }
  v2 = v25;
  if ( v25 < 0 )
    goto LABEL_77;
  _InterlockedAnd(&dword_1800198B8, 0xFFFFFFFD);
  v1 = (PVOID *)WPP_GLOBAL_Control;
LABEL_87:
  if ( v1 != &WPP_GLOBAL_Control && (*((_BYTE *)v1 + 28) & 8) != 0 )
    WPP_SF_(v1[2], 22, &WPP_305fb7554e703b1695bfea0e3f3a03b2_Traceguids);
LABEL_90:
  if ( hkey )
    RegCloseKey(hkey);
  return v2;
}

```

## disassembly

```asm
0x180001950  mov     [rsp+arg_18], rbx
0x180001955  mov     [rsp+pCount], rcx
0x18000195a  push    rbp
0x18000195b  push    rsi
0x18000195c  push    rdi
0x18000195d  sub     rsp, 40h
0x180001961  xor     edi, edi
0x180001963  mov     [rsp+58h+hkey], rdi
0x180001968  lea     rbp, WPP_GLOBAL_Control
0x18000196f  mov     rcx, cs:WPP_GLOBAL_Control
0x180001976  cmp     rcx, rbp
0x180001979  jz      short loc_18000199D
0x18000197b  test    byte ptr [rcx+1Ch], 8
0x18000197f  jz      short loc_18000199D
0x180001981  mov     edx, 0Ah
0x180001986  lea     r8, WPP_305fb7554e703b1695bfea0e3f3a03b2_Traceguids
0x18000198d  mov     rcx, [rcx+10h]
0x180001991  call    WPP_SF_
0x180001996  mov     rcx, cs:WPP_GLOBAL_Control
0x18000199d  cmp     cs:qword_1800198C0, rdi
0x1800019a4  jnz     short loc_1800019F2
0x1800019a6  mov     ebx, 8000FFFFh
0x1800019ab  cmp     rcx, rbp
0x1800019ae  jz      short loc_1800019E6
0x1800019b0  test    byte ptr [rcx+1Ch], 1
0x1800019b4  jz      short loc_1800019DA
0x1800019b6  mov     edx, 0Bh
0x1800019bb  mov     r9d, ebx
0x1800019be  lea     r8, WPP_305fb7554e703b1695bfea0e3f3a03b2_Traceguids
0x1800019c5  mov     rcx, [rcx+10h]
0x1800019c9  call    WPP_SF_d
0x1800019ce  lea     rsi, ?g_Service@@3VCFhService@@A; CFhService g_Service
0x1800019d5  jmp     loc_180001E8D
0x1800019da  lea     rsi, ?g_Service@@3VCFhService@@A; CFhService g_Service
0x1800019e1  jmp     loc_180001E94
0x1800019e6  lea     rsi, ?g_Service@@3VCFhService@@A; CFhService g_Service
0x1800019ed  jmp     loc_180001EB4
0x1800019f2  xorps   xmm0, xmm0
0x1800019f5  movups  cs:xmmword_180019888, xmm0
0x1800019fc  movups  cs:xmmword_180019888+0Ch, xmm0
0x180001a03  mov     dword ptr cs:xmmword_180019888, 30h ; '0'
0x180001a0d  mov     cs:dword_1800198A0, edi
0x180001a13  mov     dword ptr cs:xmmword_180019888+4, 1
0x180001a1d  mov     cs:dword_1800198B8, 2
0x180001a27  xor     r9d, r9d; lpName
0x180001a2a  xor     r8d, r8d; bInitialState
0x180001a2d  mov     edx, 1; bManualReset
0x180001a32  xor     ecx, ecx; lpEventAttributes
0x180001a34  call    cs:__imp_CreateEventW
0x180001a3a  mov     cs:qword_1800198B0, rax
0x180001a41  lea     rsi, ?g_Service@@3VCFhService@@A; CFhService g_Service
0x180001a48  test    rax, rax
0x180001a4b  jnz     short loc_180001A86
0x180001a4d  call    cs:__imp_GetLastError
0x180001a53  mov     ebx, eax
0x180001a55  test    eax, eax
0x180001a57  jle     short loc_180001A62
0x180001a59  movzx   ebx, ax
0x180001a5c  or      ebx, 80070000h
0x180001a62  mov     rcx, cs:WPP_GLOBAL_Control
0x180001a69  cmp     rcx, rbp
0x180001a6c  jz      loc_180001B9C
0x180001a72  test    byte ptr [rcx+1Ch], 1
0x180001a76  jz      loc_180001B9C
0x180001a7c  mov     edx, 0Ch
0x180001a81  jmp     loc_180001B82
0x180001a86  cmp     cs:dword_1800198D4, edi
0x180001a8c  jnz     short loc_180001AEA
0x180001a8e  mov     r8, rsi; lpContext
0x180001a91  lea     rdx, ?ServiceControlHandler@CFhService@@CAKKKPEAX0@Z; lpHandlerProc
0x180001a98  lea     rcx, ServiceName; "fhsvc"
0x180001a9f  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180001aa5  mov     cs:?g_Service@@3VCFhService@@A, rax; CFhService g_Service
0x180001aac  test    rax, rax
0x180001aaf  jnz     short loc_180001AEA
0x180001ab1  call    cs:__imp_GetLastError
0x180001ab7  mov     ebx, eax
0x180001ab9  test    eax, eax
0x180001abb  jle     short loc_180001AC6
0x180001abd  movzx   ebx, ax
0x180001ac0  or      ebx, 80070000h
0x180001ac6  mov     rcx, cs:WPP_GLOBAL_Control
0x180001acd  cmp     rcx, rbp
0x180001ad0  jz      loc_180001B9C
0x180001ad6  test    byte ptr [rcx+1Ch], 1
0x180001ada  jz      loc_180001B9C
0x180001ae0  mov     edx, 0Dh
0x180001ae5  jmp     loc_180001B82
0x180001aea  mov     dword ptr [rsp+58h+phkResult], 2710h; unsigned int
0x180001af2  mov     edx, 2; unsigned int
0x180001af7  mov     r9d, 1; unsigned int
0x180001afd  mov     rcx, rsi; this
0x180001b00  call    ?ReportStatus@CFhService@@AEAAJKKKK@Z; CFhService::ReportStatus(ulong,ulong,ulong,ulong)
0x180001b05  mov     ebx, eax
0x180001b07  test    eax, eax
0x180001b09  jns     short loc_180001B32
0x180001b0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180001b12  cmp     rcx, rbp
0x180001b15  jz      loc_180001EB4
0x180001b1b  test    byte ptr [rcx+1Ch], 1
0x180001b1f  jz      loc_180001E94
0x180001b25  mov     edx, 0Eh
0x180001b2a  mov     r9d, eax
0x180001b2d  jmp     loc_180001E7D
0x180001b32  lea     r9, RegistrationHandle; RegistrationHandle
0x180001b39  mov     r8, cs:?g_Service@@3VCFhService@@A; Recipient
0x180001b40  mov     edx, 1; Flags
0x180001b45  lea     rcx, GUID_LOW_POWER_EPOCH; SettingGuid
0x180001b4c  call    cs:__imp_PowerSettingRegisterNotification
0x180001b52  test    eax, eax
0x180001b54  jz      short loc_180001BA9
0x180001b56  call    cs:__imp_GetLastError
0x180001b5c  mov     ebx, eax
0x180001b5e  test    eax, eax
0x180001b60  jle     short loc_180001B6B
0x180001b62  movzx   ebx, ax
0x180001b65  or      ebx, 80070000h
0x180001b6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180001b72  cmp     rcx, rbp
0x180001b75  jz      short loc_180001B9C
0x180001b77  test    byte ptr [rcx+1Ch], 1
0x180001b7b  jz      short loc_180001B9C
0x180001b7d  mov     edx, 0Fh
0x180001b82  mov     r9d, ebx
0x180001b85  lea     r8, WPP_305fb7554e703b1695bfea0e3f3a03b2_Traceguids
0x180001b8c  mov     rcx, [rcx+10h]
0x180001b90  call    WPP_SF_d
0x180001b95  mov     rcx, cs:WPP_GLOBAL_Control
0x180001b9c  test    ebx, ebx
0x180001b9e  js      loc_180001E94
0x180001ba4  jmp     loc_180001ECD
0x180001ba9  mov     rdx, cs:qword_1800198B0; void *
0x180001bb0  call    ?Start@CManagerThread@@QEAAJPEAX@Z; CManagerThread::Start(void *)
0x180001bb5  mov     ebx, eax
0x180001bb7  test    eax, eax
0x180001bb9  jns     short loc_180001BE2
0x180001bbb  mov     rcx, cs:WPP_GLOBAL_Control
0x180001bc2  cmp     rcx, rbp
0x180001bc5  jz      loc_180001EB4
0x180001bcb  test    byte ptr [rcx+1Ch], 1
0x180001bcf  jz      loc_180001E94
0x180001bd5  mov     edx, 10h
0x180001bda  mov     r9d, eax
0x180001bdd  jmp     loc_180001E7D
0x180001be2  call    ?RpcRegisterServer@@YAJXZ; RpcRegisterServer(void)
0x180001be7  mov     ebx, eax
0x180001be9  test    eax, eax
0x180001beb  jns     short loc_180001C14
0x180001bed  mov     rcx, cs:WPP_GLOBAL_Control
0x180001bf4  cmp     rcx, rbp
0x180001bf7  jz      loc_180001EB4
0x180001bfd  test    byte ptr [rcx+1Ch], 1
0x180001c01  jz      loc_180001E94
0x180001c07  mov     edx, 11h
0x180001c0c  mov     r9d, eax
0x180001c0f  jmp     loc_180001E7D
0x180001c14  mov     dword ptr [rsp+58h+phkResult], edi; unsigned int
0x180001c18  xor     r9d, r9d; unsigned int
0x180001c1b  mov     edx, 4; unsigned int
0x180001c20  mov     rcx, rsi; this
0x180001c23  call    ?ReportStatus@CFhService@@AEAAJKKKK@Z; CFhService::ReportStatus(ulong,ulong,ulong,ulong)
0x180001c28  mov     ebx, eax
0x180001c2a  test    eax, eax
0x180001c2c  jns     short loc_180001C55
0x180001c2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180001c35  cmp     rcx, rbp
0x180001c38  jz      loc_180001EB4
0x180001c3e  test    byte ptr [rcx+1Ch], 1
0x180001c42  jz      loc_180001E94
0x180001c48  mov     edx, 12h
0x180001c4d  mov     r9d, eax
0x180001c50  jmp     loc_180001E7D
0x180001c55  lea     rax, [rsp+58h+hkey]
0x180001c5a  mov     [rsp+58h+phkResult], rax; phkResult
0x180001c5f  mov     r9d, 20019h; samDesired
0x180001c65  xor     r8d, r8d; ulOptions
0x180001c68  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\fh"...
0x180001c6f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180001c76  call    cs:__imp_RegOpenKeyExW
0x180001c7c  test    eax, eax
0x180001c7e  jnz     short loc_180001CE9
0x180001c80  mov     dword ptr [rsp+58h+ppSessionInfo], edi
0x180001c84  mov     dword ptr [rsp+58h+pCount], 4
0x180001c8c  lea     rax, [rsp+58h+pCount]
0x180001c91  mov     [rsp+58h+pcbData], rax; pcbData
0x180001c96  lea     rax, [rsp+58h+ppSessionInfo]
0x180001c9b  mov     [rsp+58h+pvData], rax; pvData
0x180001ca0  mov     [rsp+58h+phkResult], rdi; pdwType
0x180001ca5  mov     r9d, 10h; dwFlags
0x180001cab  lea     r8, Value; "TestFlags"
0x180001cb2  xor     edx, edx; lpSubKey
0x180001cb4  mov     rcx, [rsp+58h+hkey]; hkey
0x180001cb9  call    cs:__imp_RegGetValueW
0x180001cbf  test    eax, eax
0x180001cc1  jnz     short loc_180001CD4
0x180001cc3  cmp     dword ptr [rsp+58h+pCount], 4
0x180001cc8  jnz     short loc_180001CD4
0x180001cca  mov     eax, dword ptr [rsp+58h+ppSessionInfo]
0x180001cce  mov     cs:dword_180019A78, eax
0x180001cd4  mov     rcx, [rsp+58h+hkey]; hKey
0x180001cd9  test    rcx, rcx
0x180001cdc  jz      short loc_180001CE9
0x180001cde  call    cs:__imp_RegCloseKey
0x180001ce4  mov     [rsp+58h+hkey], rdi
0x180001ce9  mov     [rsp+58h+ppSessionInfo], rdi
0x180001cee  mov     dword ptr [rsp+58h+pCount], edi
0x180001cf2  lea     rax, [rsp+58h+pCount]
0x180001cf7  mov     [rsp+58h+phkResult], rax; pCount
0x180001cfc  lea     r9, [rsp+58h+ppSessionInfo]; ppSessionInfo
0x180001d01  xor     edx, edx; Reserved
0x180001d03  xor     ecx, ecx; hServer
0x180001d05  mov     r8d, 1; Version
0x180001d0b  call    cs:__imp_WTSEnumerateSessionsW
0x180001d11  test    eax, eax
0x180001d13  jnz     short loc_180001D53
0x180001d15  call    cs:__imp_GetLastError
0x180001d1b  test    eax, eax
0x180001d1d  jle     short loc_180001D27
0x180001d1f  movzx   eax, ax
0x180001d22  or      eax, 80070000h
0x180001d27  mov     rcx, cs:WPP_GLOBAL_Control
0x180001d2e  cmp     rcx, rbp
0x180001d31  jz      short loc_180001D84
0x180001d33  test    byte ptr [rcx+1Ch], 1
0x180001d37  jz      short loc_180001D84
0x180001d39  mov     edx, 65h ; 'e'
0x180001d3e  mov     r9d, eax
0x180001d41  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x180001d48  mov     rcx, [rcx+10h]
0x180001d4c  call    WPP_SF_d
0x180001d51  jmp     short loc_180001D84
0x180001d53  mov     ebx, edi
0x180001d55  mov     r8d, dword ptr [rsp+58h+pCount]
0x180001d5a  test    r8d, r8d
0x180001d5d  jz      short loc_180001D84
0x180001d5f  mov     eax, ebx
0x180001d61  lea     rcx, [rax+rax*2]; this
0x180001d65  mov     rax, [rsp+58h+ppSessionInfo]
0x180001d6a  cmp     [rax+rcx*8+10h], edi
0x180001d6e  jnz     short loc_180001D7D
0x180001d70  mov     edx, [rax+rcx*8]; unsigned int
0x180001d73  call    ?QueueBackupForLoggedOnUser@CManagerThread@@QEAAXK@Z; CManagerThread::QueueBackupForLoggedOnUser(ulong)
0x180001d78  mov     r8d, dword ptr [rsp+58h+pCount]
0x180001d7d  inc     ebx
0x180001d7f  cmp     ebx, r8d
0x180001d82  jb      short loc_180001D5F
0x180001d84  mov     rcx, [rsp+58h+ppSessionInfo]; pMemory
0x180001d89  test    rcx, rcx
0x180001d8c  jz      short loc_180001D94
0x180001d8e  call    cs:__imp_WTSFreeMemory
0x180001d94  mov     edx, edi
0x180001d96  cmp     cs:dword_1800198E8, edx
0x180001d9c  setz    dl; int
0x180001d9f  call    ?SetServiceStartType@CFhService@@QEAAJH@Z; CFhService::SetServiceStartType(int)
0x180001da4  mov     ebx, eax
0x180001da6  test    eax, eax
0x180001da8  jns     short loc_180001DE0
0x180001daa  mov     rcx, cs:WPP_GLOBAL_Control
0x180001db1  cmp     rcx, rbp
0x180001db4  jz      loc_180001EB4
0x180001dba  test    byte ptr [rcx+1Ch], 1
0x180001dbe  jz      loc_180001E94
0x180001dc4  cmp     cs:dword_1800198E8, edi
0x180001dca  setnz   r9b
0x180001dce  mov     dword ptr [rsp+58h+phkResult], eax
0x180001dd2  mov     rcx, [rcx+10h]
0x180001dd6  call    WPP_SF_cd
0x180001ddb  jmp     loc_180001E8D
0x180001de0  mov     rax, cs:qword_1800198C0
0x180001de7  mov     dword ptr [rsp+58h+pvData], 8
0x180001def  mov     [rsp+58h+phkResult], rsi
0x180001df4  lea     r9, ?StopServiceCallback@CFhService@@CAXPEAXE@Z; CFhService::StopServiceCallback(void *,uchar)
0x180001dfb  mov     r8, cs:qword_1800198B0
0x180001e02  lea     rdx, ServiceName; "fhsvc"
0x180001e09  lea     rcx, qword_1800198A8
0x180001e10  mov     rax, [rax+0C0h]
0x180001e17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e1c  mov     edi, eax
0x180001e1e  test    eax, eax
0x180001e20  jle     short loc_180001E2B
0x180001e22  movzx   edi, ax
0x180001e25  or      edi, 80070000h
0x180001e2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180001e32  test    edi, edi
0x180001e34  jns     short loc_180001E64
0x180001e36  cmp     rcx, rbp
0x180001e39  jz      short loc_180001E64
0x180001e3b  test    byte ptr [rcx+1Ch], 1
0x180001e3f  jz      short loc_180001E64
0x180001e41  mov     edx, 32h ; '2'
0x180001e46  mov     r9d, edi
0x180001e49  lea     r8, WPP_305fb7554e703b1695bfea0e3f3a03b2_Traceguids
0x180001e50  mov     rcx, [rcx+10h]
0x180001e54  call    WPP_SF_d
0x180001e59  mov     ebx, edi
0x180001e5b  mov     rcx, cs:WPP_GLOBAL_Control
0x180001e62  jmp     short loc_180001E6A
0x180001e64  mov     ebx, edi
0x180001e66  test    edi, edi
0x180001e68  jns     short loc_180001EBE
  ... truncated ...
```
