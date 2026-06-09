# RecreateSyncPollingForMultipleSession(ushort const *)

- ea: `0x18001ffb4`
- end: `0x180020410`
- name: `?RecreateSyncPollingForMultipleSession@@YAJPEBG@Z`
- size: `1116`
- prototype: `__int64 __fastcall(OLECHAR *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000ea90`

## callees

- `0x1800039f0`
- `0x18000bab4`
- `0x18001ef10`
- `0x18001f0c0`
- `0x18001ffb4`
- `0x180021b88`
- `0x180023660`
- `0x180023ce0`
- `0x180023d64`
- `0x1800245fc`
- `0x180024aa4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020207`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020245`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020207`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020245`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020067`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020102`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002018f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800201c2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020227`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020265`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002038c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800203cb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020067`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020102`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002018f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800201c2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020227`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020265`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002038c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800203cb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800200c8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800200c8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18002012c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18002012c`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800201fd`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18002023b`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800201fd`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18002023b`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18002036b`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18002036b`
- `DMCmnUtils!IsWvdFeatureAllowed` at `0x180020010`
- `DMCmnUtils!IsWvdFeatureAllowed` at `0x180020010`

## string_xrefs

- `0x180020327`: `Schedule #4 created by enrollment client`
- `0x1800203af`: `User Maintenance Schedule created by enrollment client`
- `0x18001ffe9`: `RecreateSyncPollingForMultipleSession`
- `0x18002019f`: `RecreateSyncPollingForMultipleSession`
- `0x1800201d2`: `RecreateSyncPollingForMultipleSession`
- `0x1800203db`: `RecreateSyncPollingForMultipleSession`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall RecreateSyncPollingForMultipleSession(OLECHAR *a1)
{
  __int64 v2; // rcx
  int DeviceEnrollerKey; // eax
  unsigned int v4; // ebx
  HKEY v5; // rcx
  HKEY v7; // rbx
  LSTATUS ValueW; // eax
  unsigned int v9; // edi
  __int64 v10; // rcx
  int v11; // edi
  int i; // r15d
  unsigned int MultipleSessionValueFromRegistry; // r14d
  signed int LastError; // eax
  signed int v15; // eax
  unsigned int v16; // r15d
  unsigned int v17; // r14d
  __int64 j; // rdi
  __int64 v19; // rdx
  __int64 v20; // rcx
  CEnrollmentLogger *Logger; // rax
  int pdwType; // [rsp+20h] [rbp-79h]
  int pdwTypea; // [rsp+20h] [rbp-79h]
  int pcbData; // [rsp+30h] [rbp-69h]
  int v25; // [rsp+38h] [rbp-61h]
  unsigned int Data; // [rsp+50h] [rbp-49h] BYREF
  unsigned int v27[2]; // [rsp+58h] [rbp-41h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-39h] BYREF
  DWORD v29; // [rsp+68h] [rbp-31h] BYREF
  struct _FILETIME FileTime; // [rsp+70h] [rbp-29h] BYREF
  struct _FILETIME v31; // [rsp+78h] [rbp-21h] BYREF
  struct _FILETIME v32; // [rsp+80h] [rbp-19h]
  SYSTEMTIME pvData; // [rsp+88h] [rbp-11h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+98h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  *(_QWORD *)v27 = 0;
  Data = 0;
  if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 1) != 0 )
    McTemplateU0s_EventWriteTransfer(a1, EnteringScopeEvent, "RecreateSyncPollingForMultipleSession");
  if ( !IsWvdFeatureAllowed(a1) )
  {
    if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 1) == 0 )
      return 1;
LABEL_29:
    McTemplateU0s_EventWriteTransfer(v2, LeavingScopeEvent, "RecreateSyncPollingForMultipleSession");
    return 1;
  }
  hKey = 0;
  DeviceEnrollerKey = GetDeviceEnrollerKey(a1, &hKey);
  v4 = DeviceEnrollerKey;
  if ( DeviceEnrollerKey >= 0 )
  {
    pvData = 0;
    v29 = 16;
    v7 = hKey;
    ValueW = RegGetValueW(hKey, 0, L"UserSessionScheduleTimestamp", 8u, 0, &pvData, &v29);
    v9 = ValueW;
    if ( ValueW > 0 )
      v9 = (unsigned __int16)ValueW | 0x80070000;
    if ( (v9 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x14B1,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
        (const char *)v9,
        pdwTypea);
      if ( v7 )
        RegCloseKey(v7);
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 1) == 0 )
        return v9;
      goto LABEL_62;
    }
    v11 = 0;
    SystemTime = 0;
    GetSystemTime(&SystemTime);
    for ( i = 0; i < 2; ++i )
    {
      MultipleSessionValueFromRegistry = GetMultipleSessionValueFromRegistry(
                                           a1,
                                           (LPCWSTR)(&g_MultipleSessionRegistryKeyNames)[i],
                                           &v27[i]);
      Data = MultipleSessionValueFromRegistry;
      v2 = MultipleSessionValueFromRegistry + 0x80000000;
      if ( (int)v2 >= 0 && MultipleSessionValueFromRegistry != -2147024894 )
      {
        if ( v7 )
          RegCloseKey(v7);
        if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 1) != 0 )
          McTemplateU0s_EventWriteTransfer(v2, LeavingScopeEvent, "RecreateSyncPollingForMultipleSession");
        return MultipleSessionValueFromRegistry;
      }
      if ( MultipleSessionValueFromRegistry != -2147024894 )
        v11 = 1;
    }
    if ( !v11 )
    {
      if ( v7 )
        RegCloseKey(v7);
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 1) == 0 )
        return 1;
      goto LABEL_29;
    }
    FileTime = 0;
    v31 = 0;
    if ( !SystemTimeToFileTime(&pvData, &FileTime) )
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      Data = v9;
      if ( v7 )
        RegCloseKey(v7);
      goto LABEL_61;
    }
    if ( !SystemTimeToFileTime(&SystemTime, &v31) )
    {
      v15 = GetLastError();
      v9 = v15;
      if ( v15 > 0 )
        v9 = (unsigned __int16)v15 | 0x80070000;
      Data = v9;
      if ( v7 )
        RegCloseKey(v7);
      goto LABEL_61;
    }
    v32 = FileTime;
    hKey = (HKEY)v31;
    v16 = v27[0];
    v17 = v27[0] != 0 ? v27[1] : 0;
    v27[1] = v17;
    for ( j = 0; j != 2; ++j )
    {
      SetMultipleSessionValueToRegistry(a1, (LPCWSTR)(&g_MultipleSessionRegistryKeyNames)[j], v27[j]);
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 2) != 0 )
        McTemplateU0zq_EventWriteTransfer(v20, v19, (&g_MultipleSessionRegistryKeyNames)[j], v27[j]);
    }
    if ( v17 || !v16 )
    {
      v9 = ScheduleOneOmaDmSession(
             a1,
             (OLECHAR *)L"User Maintenance Schedule created by enrollment client",
             1u,
             1u,
             0,
             1,
             pcbData,
             v25,
             1,
             1);
      Data = v9;
    }
    else
    {
      v9 = ScheduleOneOmaDmSession(
             a1,
             (OLECHAR *)L"Schedule #4 created by enrollment client",
             0,
             v16,
             (unsigned int)(((unsigned __int64)hKey - *(_QWORD *)&v32) / 0x23C34600) % v16,
             0,
             pcbData,
             v25,
             0,
             1);
      Data = v9;
      if ( (v9 & 0x80000000) != 0 )
      {
        RegSetKeyValueW(HKEY_LOCAL_MACHINE, c_szEnrollmentDB, L"ScheduleOneOmaDmSession", 4u, &Data, 4u);
        Logger = CEnrollmentLogger::GetLogger();
        CEnrollmentLogger::LogDMPollUserScheduleSetupFail(Logger, Data);
        v9 = Data;
        if ( v7 )
          RegCloseKey(v7);
        goto LABEL_61;
      }
    }
    if ( v7 )
      RegCloseKey(v7);
LABEL_61:
    if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 1) == 0 )
      return v9;
LABEL_62:
    McTemplateU0s_EventWriteTransfer(v10, LeavingScopeEvent, "RecreateSyncPollingForMultipleSession");
    return v9;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x14A6,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
    (const char *)(unsigned int)DeviceEnrollerKey,
    pdwType);
  v5 = hKey;
  if ( hKey )
    RegCloseKey(hKey);
  if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 1) != 0 )
    McTemplateU0s_EventWriteTransfer(v5, LeavingScopeEvent, "RecreateSyncPollingForMultipleSession");
  return v4;
}

```

## disassembly

```asm
0x18001ffb4  push    rbp
0x18001ffb6  push    rbx
0x18001ffb7  push    rsi
0x18001ffb8  push    rdi
0x18001ffb9  push    r12
0x18001ffbb  push    r13
0x18001ffbd  push    r14
0x18001ffbf  push    r15
0x18001ffc1  lea     rbp, [rsp-1Fh]
0x18001ffc6  sub     rsp, 0B8h
0x18001ffcd  mov     rax, cs:__security_cookie
0x18001ffd4  xor     rax, rsp
0x18001ffd7  mov     [rbp+57h+var_48], rax
0x18001ffdb  mov     rsi, rcx
0x18001ffde  xor     r12d, r12d
0x18001ffe1  mov     qword ptr [rbp+57h+var_98], r12
0x18001ffe5  mov     [rbp+57h+Data], r12d
0x18001ffe9  lea     r14, aRecreatesyncpo_0; "RecreateSyncPollingForMultipleSession"
0x18001fff0  lea     r13d, [r12+1]
0x18001fff5  test    cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, r13b
0x18001fffc  jz      short loc_18002000D
0x18001fffe  mov     r8, r14
0x180020001  lea     rdx, EnteringScopeEvent
0x180020008  call    McTemplateU0s_EventWriteTransfer
0x18002000d  mov     rcx, rsi
0x180020010  call    cs:__imp_?IsWvdFeatureAllowed@@YAHPEBG@Z; IsWvdFeatureAllowed(ushort const *)
0x180020016  test    eax, eax
0x180020018  jnz     short loc_18002002F
0x18002001a  test    cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, r13b
0x180020021  jz      loc_1800201B2
0x180020027  mov     r8, r14
0x18002002a  jmp     loc_1800201A6
0x18002002f  mov     [rbp+57h+hKey], r12
0x180020033  lea     rdx, [rbp+57h+hKey]; HKEY *
0x180020037  mov     rcx, rsi; pszMore
0x18002003a  call    ?GetDeviceEnrollerKey@@YAJPEBGPEAPEAUHKEY__@@H@Z; GetDeviceEnrollerKey(ushort const *,HKEY__ * *,int)
0x18002003f  mov     ebx, eax
0x180020041  test    eax, eax
0x180020043  jns     short loc_18002008D
0x180020045  mov     rcx, [rbp+5Fh]; this
0x180020049  mov     r9d, eax; char *
0x18002004c  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180020053  mov     edx, 14A6h; void *
0x180020058  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002005d  nop
0x18002005e  mov     rcx, [rbp+57h+hKey]; hKey
0x180020062  test    rcx, rcx
0x180020065  jz      short loc_18002006E
0x180020067  call    cs:__imp_RegCloseKey
0x18002006d  nop
0x18002006e  test    cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, r13b
0x180020075  jz      short loc_180020086
0x180020077  mov     r8, r14
0x18002007a  lea     rdx, LeavingScopeEvent
0x180020081  call    McTemplateU0s_EventWriteTransfer
0x180020086  mov     eax, ebx
0x180020088  jmp     loc_1800203F0
0x18002008d  xorps   xmm0, xmm0
0x180020090  movups  xmmword ptr [rbp+57h+var_68.wYear], xmm0
0x180020094  mov     [rbp+57h+var_88], 10h
0x18002009b  lea     rax, [rbp+57h+var_88]
0x18002009f  mov     [rsp+0F0h+pcbData], rax; int
0x1800200a4  lea     rax, [rbp+57h+var_68]
0x1800200a8  mov     [rsp+0F0h+pvData], rax; pvData
0x1800200ad  mov     [rsp+0F0h+pdwType], r12; int
0x1800200b2  mov     r9d, 8; dwFlags
0x1800200b8  lea     r8, aUsersessionsch; "UserSessionScheduleTimestamp"
0x1800200bf  xor     edx, edx; lpSubKey
0x1800200c1  mov     rbx, [rbp+57h+hKey]
0x1800200c5  mov     rcx, rbx; hkey
0x1800200c8  call    cs:__imp_RegGetValueW
0x1800200ce  mov     edi, eax
0x1800200d0  test    eax, eax
0x1800200d2  jle     short loc_1800200DD
0x1800200d4  movzx   edi, ax
0x1800200d7  or      edi, 80070000h
0x1800200dd  test    edi, edi
0x1800200df  jns     short loc_18002011E
0x1800200e1  mov     rcx, [rbp+5Fh]; this
0x1800200e5  mov     r9d, edi; char *
0x1800200e8  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800200ef  mov     edx, 14B1h; void *
0x1800200f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800200f9  nop
0x1800200fa  test    rbx, rbx
0x1800200fd  jz      short loc_180020109
0x1800200ff  mov     rcx, rbx; hKey
0x180020102  call    cs:__imp_RegCloseKey
0x180020108  nop
0x180020109  test    cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, r13b
0x180020110  jz      loc_1800203EE
0x180020116  mov     r8, r14
0x180020119  jmp     loc_1800203E2
0x18002011e  mov     edi, r12d
0x180020121  xorps   xmm0, xmm0
0x180020124  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x180020128  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x18002012c  call    cs:__imp_GetSystemTime
0x180020132  mov     r15d, r12d
0x180020135  lea     rax, ?g_MultipleSessionRegistryKeyNames@@3PAPEBGA; ushort const * near * g_MultipleSessionRegistryKeyNames
0x18002013c  mov     edx, r15d
0x18002013f  lea     r8, [rbp+57h+var_98]
0x180020143  lea     r8, [r8+rdx*4]; unsigned int *
0x180020147  mov     rdx, [rax+rdx*8]; lpValue
0x18002014b  mov     rcx, rsi; unsigned __int16 *
0x18002014e  call    ?GetMultipleSessionValueFromRegistry@@YAJPEBG0PEAK@Z; GetMultipleSessionValueFromRegistry(ushort const *,ushort const *,ulong *)
0x180020153  mov     r14d, eax
0x180020156  mov     [rbp+57h+Data], eax
0x180020159  mov     eax, 80000000h
0x18002015e  lea     ecx, [r14+rax]
0x180020162  test    eax, ecx
0x180020164  jnz     short loc_18002016F
0x180020166  cmp     r14d, 80070002h
0x18002016d  jnz     short loc_1800201BA
0x18002016f  cmp     r14d, 80070002h
0x180020176  cmovnz  edi, r13d
0x18002017a  add     r15d, r13d
0x18002017d  cmp     r15d, 2
0x180020181  jl      short loc_180020135
0x180020183  test    edi, edi
0x180020185  jnz     short loc_1800201ED
0x180020187  test    rbx, rbx
0x18002018a  jz      short loc_180020196
0x18002018c  mov     rcx, rbx; hKey
0x18002018f  call    cs:__imp_RegCloseKey
0x180020195  nop
0x180020196  test    cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, r13b
0x18002019d  jz      short loc_1800201B2
0x18002019f  lea     r8, aRecreatesyncpo_0; "RecreateSyncPollingForMultipleSession"
0x1800201a6  lea     rdx, LeavingScopeEvent
0x1800201ad  call    McTemplateU0s_EventWriteTransfer
0x1800201b2  mov     eax, r13d
0x1800201b5  jmp     loc_1800203F0
0x1800201ba  test    rbx, rbx
0x1800201bd  jz      short loc_1800201C9
0x1800201bf  mov     rcx, rbx; hKey
0x1800201c2  call    cs:__imp_RegCloseKey
0x1800201c8  nop
0x1800201c9  test    cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, r13b
0x1800201d0  jz      short loc_1800201E5
0x1800201d2  lea     r8, aRecreatesyncpo_0; "RecreateSyncPollingForMultipleSession"
0x1800201d9  lea     rdx, LeavingScopeEvent
0x1800201e0  call    McTemplateU0s_EventWriteTransfer
0x1800201e5  mov     eax, r14d
0x1800201e8  jmp     loc_1800203F0
0x1800201ed  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], r12
0x1800201f1  mov     qword ptr [rbp+57h+var_78.dwLowDateTime], r12
0x1800201f5  lea     rdx, [rbp+57h+FileTime]; lpFileTime
0x1800201f9  lea     rcx, [rbp+57h+var_68]; lpSystemTime
0x1800201fd  call    cs:__imp_SystemTimeToFileTime
0x180020203  test    eax, eax
0x180020205  jnz     short loc_180020233
0x180020207  call    cs:__imp_GetLastError
0x18002020d  mov     edi, eax
0x18002020f  test    eax, eax
0x180020211  jle     short loc_18002021C
0x180020213  movzx   edi, ax
0x180020216  or      edi, 80070000h
0x18002021c  mov     [rbp+57h+Data], edi
0x18002021f  test    rbx, rbx
0x180020222  jz      short loc_18002022E
0x180020224  mov     rcx, rbx; hKey
0x180020227  call    cs:__imp_RegCloseKey
0x18002022d  nop
0x18002022e  jmp     loc_1800203D2
0x180020233  lea     rdx, [rbp+57h+var_78]; lpFileTime
0x180020237  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x18002023b  call    cs:__imp_SystemTimeToFileTime
0x180020241  test    eax, eax
0x180020243  jnz     short loc_180020271
0x180020245  call    cs:__imp_GetLastError
0x18002024b  mov     edi, eax
0x18002024d  test    eax, eax
0x18002024f  jle     short loc_18002025A
0x180020251  movzx   edi, ax
0x180020254  or      edi, 80070000h
0x18002025a  mov     [rbp+57h+Data], edi
0x18002025d  test    rbx, rbx
0x180020260  jz      short loc_18002026C
0x180020262  mov     rcx, rbx; hKey
0x180020265  call    cs:__imp_RegCloseKey
0x18002026b  nop
0x18002026c  jmp     loc_1800203D2
0x180020271  mov     eax, [rbp+57h+FileTime.dwHighDateTime]
0x180020274  mov     dword ptr [rbp+57h+var_70+4], eax
0x180020277  mov     eax, [rbp+57h+FileTime.dwLowDateTime]
0x18002027a  mov     dword ptr [rbp+57h+var_70], eax
0x18002027d  mov     eax, [rbp+57h+var_78.dwHighDateTime]
0x180020280  mov     dword ptr [rbp+57h+hKey+4], eax
0x180020283  mov     eax, [rbp+57h+var_78.dwLowDateTime]
0x180020286  mov     dword ptr [rbp+57h+hKey], eax
0x180020289  mov     r15d, [rbp+57h+var_98]
0x18002028d  mov     eax, r15d
0x180020290  neg     eax
0x180020292  sbb     r14d, r14d
0x180020295  and     r14d, [rbp+57h+var_98+4]
0x180020299  mov     [rbp+57h+var_98+4], r14d
0x18002029d  mov     rdi, r12
0x1800202a0  lea     r12, ?g_MultipleSessionRegistryKeyNames@@3PAPEBGA; ushort const * near * g_MultipleSessionRegistryKeyNames
0x1800202a7  mov     r8d, [rbp+rdi*4+57h+var_98]; unsigned int
0x1800202ac  mov     rdx, [r12+rdi*8]; lpValueName
0x1800202b0  mov     rcx, rsi; unsigned __int16 *
0x1800202b3  call    ?SetMultipleSessionValueToRegistry@@YAJPEBG0K@Z; SetMultipleSessionValueToRegistry(ushort const *,ushort const *,ulong)
0x1800202b8  test    cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 2
0x1800202bf  jz      short loc_1800202CF
0x1800202c1  mov     r9d, [rbp+rdi*4+57h+var_98]
0x1800202c6  mov     r8, [r12+rdi*8]
0x1800202ca  call    McTemplateU0zq_EventWriteTransfer
0x1800202cf  add     rdi, r13
0x1800202d2  cmp     rdi, 2
0x1800202d6  jnz     short loc_1800202A7
0x1800202d8  xor     r12d, r12d
0x1800202db  test    r14d, r14d
0x1800202de  jnz     loc_180020395
0x1800202e4  test    r15d, r15d
0x1800202e7  jz      loc_180020395
0x1800202ed  mov     rdx, [rbp+57h+hKey]
0x1800202f1  sub     rdx, [rbp+57h+var_70]
0x1800202f5  mov     rax, 0E5109EC205D7BEA7h
0x1800202ff  mul     rdx
0x180020302  mov     rax, rdx
0x180020305  shr     rax, 1Dh
0x180020309  xor     edx, edx
0x18002030b  div     r15d
0x18002030e  mov     [rsp+0F0h+var_A8], r13d; int
0x180020313  mov     [rsp+0F0h+var_B0], r12d; int
0x180020318  mov     dword ptr [rsp+0F0h+pvData], r12d; int
0x18002031d  mov     dword ptr [rsp+0F0h+pdwType], edx; unsigned int
0x180020321  mov     r9d, r15d; unsigned int
0x180020324  xor     r8d, r8d; unsigned int
0x180020327  lea     rdx, aSchedule4Creat; "Schedule #4 created by enrollment clien"...
0x18002032e  mov     rcx, rsi; OLECHAR *
0x180020331  call    ?ScheduleOneOmaDmSession@@YAJPEBG0KKKHHHHH@Z; ScheduleOneOmaDmSession(ushort const *,ushort const *,ulong,ulong,ulong,int,int,int,int,int)
0x180020336  mov     edi, eax
0x180020338  mov     [rbp+57h+Data], eax
0x18002033b  test    eax, eax
0x18002033d  jns     loc_1800203C3
0x180020343  lea     r9d, [r12+4]; dwType
0x180020348  mov     dword ptr [rsp+0F0h+pvData], r9d; cbData
0x18002034d  lea     rax, [rbp+57h+Data]
0x180020351  mov     [rsp+0F0h+pdwType], rax; lpData
0x180020356  lea     r8, aScheduleoneoma; "ScheduleOneOmaDmSession"
0x18002035d  mov     rdx, cs:?c_szEnrollmentDB@@3PEBGEB; lpSubKey
0x180020364  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002036b  call    cs:__imp_RegSetKeyValueW
0x180020371  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180020376  mov     edx, [rbp+57h+Data]; int
0x180020379  mov     rcx, rax; this
0x18002037c  call    ?LogDMPollUserScheduleSetupFail@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogDMPollUserScheduleSetupFail(long)
0x180020381  mov     edi, [rbp+57h+Data]
0x180020384  test    rbx, rbx
0x180020387  jz      short loc_180020393
0x180020389  mov     rcx, rbx; hKey
0x18002038c  call    cs:__imp_RegCloseKey
0x180020392  nop
0x180020393  jmp     short loc_1800203D2
0x180020395  mov     [rsp+0F0h+var_A8], r13d; int
0x18002039a  mov     [rsp+0F0h+var_B0], r13d; int
0x18002039f  mov     dword ptr [rsp+0F0h+pvData], r13d; int
0x1800203a4  mov     dword ptr [rsp+0F0h+pdwType], r12d; unsigned int
0x1800203a9  mov     r9d, r13d; unsigned int
0x1800203ac  mov     r8d, r13d; unsigned int
0x1800203af  lea     rdx, aUserMaintenanc; "User Maintenance Schedule created by en"...
0x1800203b6  mov     rcx, rsi; OLECHAR *
0x1800203b9  call    ?ScheduleOneOmaDmSession@@YAJPEBG0KKKHHHHH@Z; ScheduleOneOmaDmSession(ushort const *,ushort const *,ulong,ulong,ulong,int,int,int,int,int)
0x1800203be  mov     edi, eax
0x1800203c0  mov     [rbp+57h+Data], eax
0x1800203c3  test    rbx, rbx
0x1800203c6  jz      short loc_1800203D2
0x1800203c8  mov     rcx, rbx; hKey
0x1800203cb  call    cs:__imp_RegCloseKey
0x1800203d1  nop
0x1800203d2  test    cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, r13b
0x1800203d9  jz      short loc_1800203EE
0x1800203db  lea     r8, aRecreatesyncpo_0; "RecreateSyncPollingForMultipleSession"
0x1800203e2  lea     rdx, LeavingScopeEvent
0x1800203e9  call    McTemplateU0s_EventWriteTransfer
0x1800203ee  mov     eax, edi
0x1800203f0  mov     rcx, [rbp+57h+var_48]
0x1800203f4  xor     rcx, rsp; StackCookie
0x1800203f7  call    __security_check_cookie
0x1800203fc  add     rsp, 0B8h
0x180020403  pop     r15
0x180020405  pop     r14
0x180020407  pop     r13
0x180020409  pop     r12
0x18002040b  pop     rdi
0x18002040c  pop     rsi
0x18002040d  pop     rbx
0x18002040e  pop     rbp
0x18002040f  retn
```
