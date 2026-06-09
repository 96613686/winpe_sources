# SyncPollingOptionsForMultipleSession(ushort const *)

- ea: `0x1800de864`
- end: `0x1800deb73`
- name: `?SyncPollingOptionsForMultipleSession@@YAJPEBG@Z`
- size: `783`
- prototype: `__int64 __fastcall(PCWSTR pszMore)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002e510`

## callees

- `0x180008de0`
- `0x18000d4d4`
- `0x180025ac0`
- `0x18002dcc8`
- `0x1800d11a4`
- `0x1800d13dc`
- `0x1800d71f4`
- `0x1800d72d0`
- `0x1800da990`
- `0x1800dab54`
- `0x1800dbe9c`
- `0x1800dddcc`
- `0x1800de864`
- `0x1800dffac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800deb32`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800deb32`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800deaf2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800deaf2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800dea5d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800dea5d`
- `DMCmnUtils!IsWvdFeatureAllowed` at `0x1800de8ad`
- `DMCmnUtils!IsWvdFeatureAllowed` at `0x1800de8ad`
- `DMCmnUtils!DmDeleteTask` at `0x1800dea05`
- `DMCmnUtils!DmDeleteTask` at `0x1800dea05`

## string_xrefs

- `0x1800de9e1`: `Schedule #4 created by enrollment client`
- `0x1800de9f4`: `Schedule #4 created by enrollment client`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SyncPollingOptionsForMultipleSession(PCWSTR pszMore)
{
  int v3; // edi
  int v4; // r15d
  int v5; // ebx
  unsigned int MultipleSessionValueFromRegistry; // r14d
  unsigned int v7; // r14d
  unsigned int v8; // r15d
  __int64 i; // rdi
  __int64 v10; // rdx
  __int64 v11; // rcx
  int v12; // edi
  CEnrollmentLogger *Logger; // rax
  int DeviceEnrollerKey; // eax
  LSTATUS ValueW; // eax
  int pdwType; // [rsp+20h] [rbp-59h]
  int pcbData; // [rsp+30h] [rbp-49h]
  int v18; // [rsp+38h] [rbp-41h]
  HKEY hkey; // [rsp+50h] [rbp-29h] BYREF
  unsigned int v20[2]; // [rsp+58h] [rbp-21h] BYREF
  _BYTE v21[8]; // [rsp+60h] [rbp-19h] BYREF
  DWORD v22; // [rsp+68h] [rbp-11h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+70h] [rbp-9h] BYREF
  __int128 pvData; // [rsp+80h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  *(_QWORD *)v20 = 0;
  hkey = 0;
  EvtPerfTraceScope::EvtPerfTraceScope((EvtPerfTraceScope *)v21, "SyncPollingOptionsForMultipleSession");
  if ( !IsWvdFeatureAllowed(pszMore) )
  {
    EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v21);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    return 1;
  }
  v3 = 0;
  v4 = 0;
  v5 = 1;
  while ( v4 < 2 )
  {
    MultipleSessionValueFromRegistry = GetMultipleSessionValueFromRegistry(
                                         pszMore,
                                         (LPCWSTR)(&g_MultipleSessionRegistryKeyNames)[v4],
                                         &v20[v4]);
    if ( (int)(MultipleSessionValueFromRegistry + 0x80000000) >= 0 && MultipleSessionValueFromRegistry != -2147024894 )
    {
      EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v21);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      return MultipleSessionValueFromRegistry;
    }
    if ( MultipleSessionValueFromRegistry != -2147024894 )
      v3 = 1;
    ++v4;
  }
  if ( v3 )
  {
    v7 = v20[0];
    v8 = v20[0] != 0 ? v20[1] : 0;
    v20[1] = v8;
    for ( i = 0; i != 2; ++i )
    {
      SetMultipleSessionValueToRegistry(pszMore, (LPCWSTR)(&g_MultipleSessionRegistryKeyNames)[i], v20[i]);
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 2) != 0 )
        McTemplateU0zq_EventWriteTransfer(v11, v10, (&g_MultipleSessionRegistryKeyNames)[i], v20[i]);
    }
    if ( v7 )
    {
      v12 = ScheduleOneOmaDmSession(
              pszMore,
              L"Schedule #4 created by enrollment client",
              v8,
              v7,
              v7,
              0,
              pcbData,
              v18,
              0,
              1);
    }
    else
    {
      v12 = DmDeleteTask(L"\\Microsoft\\Windows\\EnterpriseMgmt", pszMore, L"Schedule #4 created by enrollment client");
      if ( (unsigned int)(v12 + 2147024894) <= 1 || v12 == -2147023728 )
      {
LABEL_23:
        SystemTime = 0;
        GetSystemTime(&SystemTime);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
          &hkey,
          0);
        DeviceEnrollerKey = GetDeviceEnrollerKey(pszMore, &hkey);
        v5 = DeviceEnrollerKey;
        if ( DeviceEnrollerKey >= 0 )
        {
          pvData = 0;
          v22 = 16;
          ValueW = RegGetValueW(hkey, 0, L"UserSessionScheduleTimestamp", 8u, 0, &pvData, &v22);
          v5 = ValueW;
          if ( ValueW > 0 )
            v5 = (unsigned __int16)ValueW | 0x80070000;
          if ( v5 < 0 )
            v5 = RegSetValueExW(hkey, L"UserSessionScheduleTimestamp", 0, 3u, (const BYTE *)&SystemTime, 0x10u);
          EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v21);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1479,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
            (const char *)(unsigned int)DeviceEnrollerKey,
            pdwType);
          EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v21);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
        }
        return (unsigned int)v5;
      }
    }
    if ( v12 < 0 )
    {
      Logger = CEnrollmentLogger::GetLogger();
      CEnrollmentLogger::LogDMPollUserScheduleSetupFail(Logger, v12);
      EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v21);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      return (unsigned int)v12;
    }
    goto LABEL_23;
  }
  EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v21);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800de864  push    rbp
0x1800de866  push    rbx
0x1800de867  push    rsi
0x1800de868  push    rdi
0x1800de869  push    r14
0x1800de86b  push    r15
0x1800de86d  lea     rbp, [rsp-2Fh]
0x1800de872  sub     rsp, 0A8h
0x1800de879  mov     rax, cs:__security_cookie
0x1800de880  xor     rax, rsp
0x1800de883  mov     [rbp+57h+var_40], rax
0x1800de887  mov     rsi, rcx
0x1800de88a  mov     qword ptr [rbp+57h+var_78], 0
0x1800de892  mov     [rbp+57h+hkey], 0
0x1800de89a  lea     rdx, aSyncpollingopt; "SyncPollingOptionsForMultipleSession"
0x1800de8a1  lea     rcx, [rbp+57h+var_70]; this
0x1800de8a5  call    ??0EvtPerfTraceScope@@QEAA@PEBD@Z; EvtPerfTraceScope::EvtPerfTraceScope(char const *)
0x1800de8aa  mov     rcx, rsi
0x1800de8ad  call    cs:__imp_?IsWvdFeatureAllowed@@YAHPEBG@Z; IsWvdFeatureAllowed(ushort const *)
0x1800de8b4  nop     dword ptr [rax+rax+00h]
0x1800de8b9  test    eax, eax
0x1800de8bb  jnz     short loc_1800DE8DB
0x1800de8bd  lea     rcx, [rbp+57h+var_70]; this
0x1800de8c1  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x1800de8c6  nop
0x1800de8c7  lea     rcx, [rbp+57h+hkey]
0x1800de8cb  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800de8d0  nop
0x1800de8d1  mov     eax, 1
0x1800de8d6  jmp     loc_1800DEB56
0x1800de8db  xor     edi, edi
0x1800de8dd  xor     r15d, r15d
0x1800de8e0  lea     ebx, [rdi+1]
0x1800de8e3  lea     rcx, ?g_MultipleSessionRegistryKeyNames@@3PAPEBGA; ushort const * near * g_MultipleSessionRegistryKeyNames
0x1800de8ea  cmp     r15d, 2
0x1800de8ee  jge     short loc_1800DE94B
0x1800de8f0  movsxd  rdx, r15d
0x1800de8f3  lea     r8, [rbp+57h+var_78]
0x1800de8f7  lea     r8, [r8+rdx*4]; unsigned int *
0x1800de8fb  mov     rdx, [rcx+rdx*8]; lpValue
0x1800de8ff  mov     rcx, rsi; unsigned __int16 *
0x1800de902  call    ?GetMultipleSessionValueFromRegistry@@YAJPEBG0PEAK@Z; GetMultipleSessionValueFromRegistry(ushort const *,ushort const *,ulong *)
0x1800de907  mov     r14d, eax
0x1800de90a  mov     eax, 80000000h
0x1800de90f  lea     ecx, [r14+rax]
0x1800de913  test    eax, ecx
0x1800de915  jnz     short loc_1800DE920
0x1800de917  cmp     r14d, 80070002h
0x1800de91e  jnz     short loc_1800DE92F
0x1800de920  cmp     r14d, 80070002h
0x1800de927  cmovnz  edi, ebx
0x1800de92a  add     r15d, ebx
0x1800de92d  jmp     short loc_1800DE8E3
0x1800de92f  lea     rcx, [rbp+57h+var_70]; this
0x1800de933  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x1800de938  nop
0x1800de939  lea     rcx, [rbp+57h+hkey]
0x1800de93d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800de942  nop
0x1800de943  mov     eax, r14d
0x1800de946  jmp     loc_1800DEB56
0x1800de94b  test    edi, edi
0x1800de94d  jnz     short loc_1800DE968
0x1800de94f  lea     rcx, [rbp+57h+var_70]; this
0x1800de953  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x1800de958  nop
0x1800de959  lea     rcx, [rbp+57h+hkey]
0x1800de95d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800de962  nop
0x1800de963  jmp     loc_1800DEB54
0x1800de968  mov     r14d, [rbp+57h+var_78]
0x1800de96c  mov     eax, r14d
0x1800de96f  neg     eax
0x1800de971  sbb     r15d, r15d
0x1800de974  and     r15d, [rbp+57h+var_78+4]
0x1800de978  mov     [rbp+57h+var_78+4], r15d
0x1800de97c  xor     edi, edi
0x1800de97e  mov     r8d, [rbp+rdi*4+57h+var_78]; unsigned int
0x1800de983  mov     rdx, [rcx+rdi*8]; lpValueName
0x1800de987  mov     rcx, rsi; unsigned __int16 *
0x1800de98a  call    ?SetMultipleSessionValueToRegistry@@YAJPEBG0K@Z; SetMultipleSessionValueToRegistry(ushort const *,ushort const *,ulong)
0x1800de98f  test    cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 2
0x1800de996  jz      short loc_1800DE9AD
0x1800de998  mov     r9d, [rbp+rdi*4+57h+var_78]
0x1800de99d  lea     r8, ?g_MultipleSessionRegistryKeyNames@@3PAPEBGA; ushort const * near * g_MultipleSessionRegistryKeyNames
0x1800de9a4  mov     r8, [r8+rdi*8]
0x1800de9a8  call    McTemplateU0zq_EventWriteTransfer
0x1800de9ad  add     rdi, rbx
0x1800de9b0  cmp     rdi, 2
0x1800de9b4  lea     rcx, ?g_MultipleSessionRegistryKeyNames@@3PAPEBGA; ushort const * near * g_MultipleSessionRegistryKeyNames
0x1800de9bb  jnz     short loc_1800DE97E
0x1800de9bd  test    r14d, r14d
0x1800de9c0  jz      short loc_1800DE9F4
0x1800de9c2  mov     [rsp+0D0h+var_88], ebx; int
0x1800de9c6  mov     [rsp+0D0h+var_90], 0; int
0x1800de9ce  mov     dword ptr [rsp+0D0h+pvData], 0; int
0x1800de9d6  mov     dword ptr [rsp+0D0h+pdwType], r14d; unsigned int
0x1800de9db  mov     r9d, r14d; unsigned int
0x1800de9de  mov     r8d, r15d; unsigned int
0x1800de9e1  lea     rdx, aSchedule4Creat; "Schedule #4 created by enrollment clien"...
0x1800de9e8  mov     rcx, rsi; unsigned __int16 *
0x1800de9eb  call    ?ScheduleOneOmaDmSession@@YAJPEBG0KKKHHHHH@Z; ScheduleOneOmaDmSession(ushort const *,ushort const *,ulong,ulong,ulong,int,int,int,int,int)
0x1800de9f0  mov     edi, eax
0x1800de9f2  jmp     short loc_1800DEA24
0x1800de9f4  lea     r8, aSchedule4Creat; "Schedule #4 created by enrollment clien"...
0x1800de9fb  mov     rdx, rsi
0x1800de9fe  lea     rcx, aMicrosoftWindo_3; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x1800dea05  call    cs:__imp_?DmDeleteTask@@YAJPEBG00@Z; DmDeleteTask(ushort const *,ushort const *,ushort const *)
0x1800dea0c  nop     dword ptr [rax+rax+00h]
0x1800dea11  mov     edi, eax
0x1800dea13  add     eax, 7FF8FFFEh
0x1800dea18  cmp     eax, ebx
0x1800dea1a  jbe     short loc_1800DEA52
0x1800dea1c  cmp     edi, 80070490h
0x1800dea22  jz      short loc_1800DEA52
0x1800dea24  test    edi, edi
0x1800dea26  jns     short loc_1800DEA52
0x1800dea28  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x1800dea2d  mov     edx, edi; int
0x1800dea2f  mov     rcx, rax; this
0x1800dea32  call    ?LogDMPollUserScheduleSetupFail@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogDMPollUserScheduleSetupFail(long)
0x1800dea37  lea     rcx, [rbp+57h+var_70]; this
0x1800dea3b  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x1800dea40  nop
0x1800dea41  lea     rcx, [rbp+57h+hkey]
0x1800dea45  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800dea4a  nop
0x1800dea4b  mov     eax, edi
0x1800dea4d  jmp     loc_1800DEB56
0x1800dea52  xorps   xmm0, xmm0
0x1800dea55  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x1800dea59  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x1800dea5d  call    cs:__imp_GetSystemTime
0x1800dea64  nop     dword ptr [rax+rax+00h]
0x1800dea69  xor     edx, edx
0x1800dea6b  lea     rcx, [rbp+57h+hkey]
0x1800dea6f  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800dea74  lea     rdx, [rbp+57h+hkey]; HKEY *
0x1800dea78  mov     rcx, rsi; pszMore
0x1800dea7b  call    ?GetDeviceEnrollerKey@@YAJPEBGPEAPEAUHKEY__@@H@Z; GetDeviceEnrollerKey(ushort const *,HKEY__ * *,int)
0x1800dea80  mov     ebx, eax
0x1800dea82  test    eax, eax
0x1800dea84  jns     short loc_1800DEAB7
0x1800dea86  mov     rcx, [rbp+5Fh]; this
0x1800dea8a  mov     r9d, eax; char *
0x1800dea8d  lea     r8, aOnecoreuapAdmi_82; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800dea94  mov     edx, 1479h; void *
0x1800dea99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dea9e  lea     rcx, [rbp+57h+var_70]; this
0x1800deaa2  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x1800deaa7  nop
0x1800deaa8  lea     rcx, [rbp+57h+hkey]
0x1800deaac  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800deab1  nop
0x1800deab2  jmp     loc_1800DEB54
0x1800deab7  xorps   xmm0, xmm0
0x1800deaba  movups  [rbp+57h+var_50], xmm0
0x1800deabe  mov     edi, 10h
0x1800deac3  mov     [rbp+57h+var_68], edi
0x1800deac6  lea     rax, [rbp+57h+var_68]
0x1800deaca  mov     [rsp+0D0h+pcbData], rax; pcbData
0x1800deacf  lea     rax, [rbp+57h+var_50]
0x1800dead3  mov     [rsp+0D0h+pvData], rax; pvData
0x1800dead8  mov     [rsp+0D0h+pdwType], 0; pdwType
0x1800deae1  lea     r9d, [rdi-8]; dwFlags
0x1800deae5  lea     r8, aUsersessionsch; "UserSessionScheduleTimestamp"
0x1800deaec  xor     edx, edx; lpSubKey
0x1800deaee  mov     rcx, [rbp+57h+hkey]; hkey
0x1800deaf2  call    cs:__imp_RegGetValueW
0x1800deaf9  nop     dword ptr [rax+rax+00h]
0x1800deafe  mov     ebx, eax
0x1800deb00  test    eax, eax
0x1800deb02  jle     short loc_1800DEB0D
0x1800deb04  movzx   ebx, ax
0x1800deb07  or      ebx, 80070000h
0x1800deb0d  test    ebx, ebx
0x1800deb0f  jns     short loc_1800DEB40
0x1800deb11  mov     dword ptr [rsp+0D0h+pvData], edi; cbData
0x1800deb15  lea     rax, [rbp+57h+SystemTime]
0x1800deb19  mov     [rsp+0D0h+pdwType], rax; lpData
0x1800deb1e  mov     r9d, 3; dwType
0x1800deb24  xor     r8d, r8d; Reserved
0x1800deb27  lea     rdx, aUsersessionsch; "UserSessionScheduleTimestamp"
0x1800deb2e  mov     rcx, [rbp+57h+hkey]; hKey
0x1800deb32  call    cs:__imp_RegSetValueExW
0x1800deb39  nop     dword ptr [rax+rax+00h]
0x1800deb3e  mov     ebx, eax
0x1800deb40  lea     rcx, [rbp+57h+var_70]; this
0x1800deb44  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x1800deb49  nop
0x1800deb4a  lea     rcx, [rbp+57h+hkey]
0x1800deb4e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800deb53  nop
0x1800deb54  mov     eax, ebx
0x1800deb56  mov     rcx, [rbp+57h+var_40]
0x1800deb5a  xor     rcx, rsp; StackCookie
0x1800deb5d  call    __security_check_cookie
0x1800deb62  add     rsp, 0A8h
0x1800deb69  pop     r15
0x1800deb6b  pop     r14
0x1800deb6d  pop     rdi
0x1800deb6e  pop     rsi
0x1800deb6f  pop     rbx
0x1800deb70  pop     rbp
0x1800deb71  retn
```
