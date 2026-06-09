# SyncPollingOptionsForMultipleSession(ushort const *)

- ea: `0x18001c61c`
- end: `0x18001c916`
- name: `?SyncPollingOptionsForMultipleSession@@YAJPEBG@Z`
- size: `762`
- prototype: `__int64 __fastcall(unsigned __int16 *pszMore, __int64, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000be00`

## callees

- `0x1800022e0`
- `0x180006294`
- `0x1800097fc`
- `0x180011ccc`
- `0x180017558`
- `0x180017734`
- `0x180019904`
- `0x18001bb10`
- `0x18001c61c`
- `0x18001d2a4`
- `0x18001dce8`
- `0x18001e178`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18001c800`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18001c800`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001c8cb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001c8cb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c84b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c8e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c84b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c8e5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001c892`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001c892`
- `DMCmnUtils!IsWvdFeatureAllowed` at `0x18001c69d`
- `DMCmnUtils!IsWvdFeatureAllowed` at `0x18001c69d`
- `DMCmnUtils!DmDeleteTask` at `0x18001c7b8`
- `DMCmnUtils!DmDeleteTask` at `0x18001c7b8`

## string_xrefs

- `0x18001c794`: `Schedule #4 created by enrollment client`
- `0x18001c7a7`: `Schedule #4 created by enrollment client`

## pseudocode

```c
__int64 __fastcall SyncPollingOptionsForMultipleSession(unsigned __int16 *pszMore, __int64 a2, __int64 a3)
{
  int v5; // ebx
  __int64 v6; // r14
  unsigned int MultipleSessionValueFromRegistry; // esi
  unsigned int v8; // esi
  int v9; // r14d
  __int64 i; // rbx
  __int64 v11; // rdx
  __int64 v12; // rcx
  int v13; // ebx
  int v14; // eax
  CEnrollmentLogger *Logger; // rax
  int DeviceEnrollerKey; // eax
  HKEY v17; // rbx
  LSTATUS ValueW; // eax
  int v19; // edi
  int pcbData; // [rsp+30h] [rbp-49h]
  int v21; // [rsp+38h] [rbp-41h]
  HKEY hKey; // [rsp+50h] [rbp-29h] BYREF
  const char *v23; // [rsp+58h] [rbp-21h] BYREF
  DWORD v24; // [rsp+60h] [rbp-19h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+68h] [rbp-11h] BYREF
  __int128 pvData; // [rsp+78h] [rbp-1h] BYREF
  int v27[4]; // [rsp+88h] [rbp+Fh] BYREF
  const char *v28; // [rsp+98h] [rbp+1Fh]
  __int64 v29; // [rsp+A0h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  hKey = 0;
  v23 = "SyncPollingOptionsForMultipleSession";
  if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 1) != 0 )
  {
    v28 = "SyncPollingOptionsForMultipleSession";
    v29 = 37;
    McGenEventWrite_EventWriteTransfer(WP_ENROLLMENT_API_PROVIDER_Context, EnteringScopeEvent, a3, 2, v27);
  }
  if ( IsWvdFeatureAllowed(pszMore) )
  {
    v5 = 0;
    v6 = 0;
    do
    {
      MultipleSessionValueFromRegistry = GetMultipleSessionValueFromRegistry(
                                           pszMore,
                                           (LPCWSTR)(&g_MultipleSessionRegistryKeyNames)[v6],
                                           (unsigned int *)&hKey + v6);
      if ( (int)(MultipleSessionValueFromRegistry + 0x80000000) >= 0 && MultipleSessionValueFromRegistry != -2147024894 )
      {
        EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)&v23);
        return MultipleSessionValueFromRegistry;
      }
      if ( MultipleSessionValueFromRegistry != -2147024894 )
        v5 = 1;
      v6 = (unsigned int)(v6 + 1);
    }
    while ( (int)v6 < 2 );
    if ( !v5 )
    {
      EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)&v23);
      return 1;
    }
    v8 = (unsigned int)hKey;
    v9 = (_DWORD)hKey != 0 ? HIDWORD(hKey) : 0;
    HIDWORD(hKey) = v9;
    for ( i = 0; i != 2; ++i )
    {
      SetMultipleSessionValueToRegistry(
        pszMore,
        (LPCWSTR)(&g_MultipleSessionRegistryKeyNames)[i],
        *((_DWORD *)&hKey + i));
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 2) != 0 )
        McTemplateU0zq_EventWriteTransfer(
          v12,
          v11,
          (&g_MultipleSessionRegistryKeyNames)[i],
          *((unsigned int *)&hKey + i));
    }
    if ( v8 )
    {
      v13 = ScheduleOneOmaDmSession(
              pszMore,
              L"Schedule #4 created by enrollment client",
              v9,
              v8,
              v8,
              0,
              pcbData,
              v21,
              0,
              1);
    }
    else
    {
      v14 = DmDeleteTask(L"\\Microsoft\\Windows\\EnterpriseMgmt", pszMore, L"Schedule #4 created by enrollment client");
      v13 = v14;
      if ( v14 == -2147023728 || (unsigned int)(v14 + 2147024894) <= 1 )
        goto LABEL_26;
    }
    if ( v13 < 0 )
    {
      Logger = CEnrollmentLogger::GetLogger();
      CEnrollmentLogger::LogDMPollUserScheduleSetupFail(Logger, v13);
      EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)&v23);
      return (unsigned int)v13;
    }
LABEL_26:
    SystemTime = 0;
    GetSystemTime(&SystemTime);
    hKey = 0;
    DeviceEnrollerKey = GetDeviceEnrollerKey(pszMore, &hKey);
    v13 = DeviceEnrollerKey;
    if ( DeviceEnrollerKey >= 0 )
    {
      pvData = 0;
      v24 = 16;
      v17 = hKey;
      ValueW = RegGetValueW(hKey, 0, L"UserSessionScheduleTimestamp", 8u, 0, &pvData, &v24);
      v19 = ValueW;
      if ( ValueW > 0 )
        v19 = (unsigned __int16)ValueW | 0x80070000;
      if ( v19 < 0 )
        v19 = RegSetValueExW(v17, L"UserSessionScheduleTimestamp", 0, 3u, (const BYTE *)&SystemTime, 0x10u);
      EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)&v23);
      if ( v17 )
        RegCloseKey(v17);
      return (unsigned int)v19;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1479,
      (int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)(unsigned int)DeviceEnrollerKey);
    EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)&v23);
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)v13;
  }
  EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)&v23);
  return 1;
}

```

## disassembly

```asm
0x18001c61c  mov     [rsp-8+arg_8], rbx
0x18001c621  mov     [rsp-8+arg_10], rsi
0x18001c626  push    rbp
0x18001c627  push    rdi
0x18001c628  push    r12
0x18001c62a  push    r13
0x18001c62c  push    r14
0x18001c62e  lea     rbp, [rsp-37h]
0x18001c633  sub     rsp, 0B0h
0x18001c63a  mov     rax, cs:__security_cookie
0x18001c641  xor     rax, rsp
0x18001c644  mov     [rbp+57h+var_28], rax
0x18001c648  mov     rdi, rcx
0x18001c64b  mov     [rbp+57h+hKey], 0
0x18001c653  lea     rax, aSyncpollingopt; "SyncPollingOptionsForMultipleSession"
0x18001c65a  mov     [rbp+57h+var_78], rax
0x18001c65e  mov     r12d, 1
0x18001c664  test    cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, r12b
0x18001c66b  jz      short loc_18001C69A
0x18001c66d  mov     [rbp+57h+var_38], rax
0x18001c671  mov     [rbp+57h+var_30], 25h ; '%'
0x18001c679  lea     rax, [rbp+57h+var_48]
0x18001c67d  mov     [rsp+0D0h+pdwType], rax; int
0x18001c682  lea     r9d, [r12+1]
0x18001c687  lea     rdx, EnteringScopeEvent
0x18001c68e  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x18001c695  call    McGenEventWrite_EventWriteTransfer
0x18001c69a  mov     rcx, rdi
0x18001c69d  call    cs:__imp_?IsWvdFeatureAllowed@@YAHPEBG@Z; IsWvdFeatureAllowed(ushort const *)
0x18001c6a3  test    eax, eax
0x18001c6a5  jnz     short loc_18001C6B9
0x18001c6a7  lea     rcx, [rbp+57h+var_78]; this
0x18001c6ab  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x18001c6b0  nop
0x18001c6b1  mov     eax, r12d
0x18001c6b4  jmp     loc_18001C8EE
0x18001c6b9  xor     ebx, ebx
0x18001c6bb  xor     r14d, r14d
0x18001c6be  mov     r13d, 80070002h
0x18001c6c4  lea     rax, ?g_MultipleSessionRegistryKeyNames@@3PAPEBGA; ushort const * near * g_MultipleSessionRegistryKeyNames
0x18001c6cb  lea     r8, [rbp+57h+hKey]
0x18001c6cf  lea     r8, [r8+r14*4]; unsigned int *
0x18001c6d3  mov     rdx, [rax+r14*8]; lpValue
0x18001c6d7  mov     rcx, rdi; unsigned __int16 *
0x18001c6da  call    ?GetMultipleSessionValueFromRegistry@@YAJPEBG0PEAK@Z; GetMultipleSessionValueFromRegistry(ushort const *,ushort const *,ulong *)
0x18001c6df  mov     esi, eax
0x18001c6e1  mov     eax, 80000000h
0x18001c6e6  lea     ecx, [rsi+rax]
0x18001c6e9  test    eax, ecx
0x18001c6eb  jnz     short loc_18001C6F2
0x18001c6ed  cmp     esi, r13d
0x18001c6f0  jnz     short loc_18001C712
0x18001c6f2  cmp     esi, r13d
0x18001c6f5  cmovnz  ebx, r12d
0x18001c6f9  add     r14d, r12d
0x18001c6fc  cmp     r14d, 2
0x18001c700  jl      short loc_18001C6C4
0x18001c702  test    ebx, ebx
0x18001c704  jnz     short loc_18001C723
0x18001c706  lea     rcx, [rbp+57h+var_78]; this
0x18001c70a  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x18001c70f  nop
0x18001c710  jmp     short loc_18001C6B1
0x18001c712  lea     rcx, [rbp+57h+var_78]; this
0x18001c716  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x18001c71b  nop
0x18001c71c  mov     eax, esi
0x18001c71e  jmp     loc_18001C8EE
0x18001c723  mov     esi, dword ptr [rbp+57h+hKey]
0x18001c726  mov     eax, esi
0x18001c728  neg     eax
0x18001c72a  sbb     r14d, r14d
0x18001c72d  and     r14d, dword ptr [rbp+57h+hKey+4]
0x18001c731  mov     dword ptr [rbp+57h+hKey+4], r14d
0x18001c735  xor     ebx, ebx
0x18001c737  lea     r13, ?g_MultipleSessionRegistryKeyNames@@3PAPEBGA; ushort const * near * g_MultipleSessionRegistryKeyNames
0x18001c73e  mov     r8d, dword ptr [rbp+rbx*4+57h+hKey]; unsigned int
0x18001c743  mov     rdx, [r13+rbx*8+0]; lpValueName
0x18001c748  mov     rcx, rdi; unsigned __int16 *
0x18001c74b  call    ?SetMultipleSessionValueToRegistry@@YAJPEBG0K@Z; SetMultipleSessionValueToRegistry(ushort const *,ushort const *,ulong)
0x18001c750  test    cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 2
0x18001c757  jz      short loc_18001C768
0x18001c759  mov     r9d, dword ptr [rbp+rbx*4+57h+hKey]
0x18001c75e  mov     r8, [r13+rbx*8+0]
0x18001c763  call    McTemplateU0zq_EventWriteTransfer
0x18001c768  add     rbx, r12
0x18001c76b  cmp     rbx, 2
0x18001c76f  jnz     short loc_18001C73E
0x18001c771  test    esi, esi
0x18001c773  jz      short loc_18001C7A7
0x18001c775  mov     [rsp+0D0h+var_88], r12d; int
0x18001c77a  mov     [rsp+0D0h+var_90], 0; int
0x18001c782  mov     dword ptr [rsp+0D0h+pvData], 0; int
0x18001c78a  mov     dword ptr [rsp+0D0h+pdwType], esi; unsigned int
0x18001c78e  mov     r9d, esi; unsigned int
0x18001c791  mov     r8d, r14d; unsigned int
0x18001c794  lea     rdx, aSchedule4Creat; "Schedule #4 created by enrollment clien"...
0x18001c79b  mov     rcx, rdi; unsigned __int16 *
0x18001c79e  call    ?ScheduleOneOmaDmSession@@YAJPEBG0KKKHHHHH@Z; ScheduleOneOmaDmSession(ushort const *,ushort const *,ulong,ulong,ulong,int,int,int,int,int)
0x18001c7a3  mov     ebx, eax
0x18001c7a5  jmp     short loc_18001C7D1
0x18001c7a7  lea     r8, aSchedule4Creat; "Schedule #4 created by enrollment clien"...
0x18001c7ae  mov     rdx, rdi
0x18001c7b1  lea     rcx, aMicrosoftWindo; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x18001c7b8  call    cs:__imp_?DmDeleteTask@@YAJPEBG00@Z; DmDeleteTask(ushort const *,ushort const *,ushort const *)
0x18001c7be  mov     ebx, eax
0x18001c7c0  cmp     eax, 80070490h
0x18001c7c5  jz      short loc_18001C7F5
0x18001c7c7  add     eax, 7FF8FFFEh
0x18001c7cc  cmp     eax, r12d
0x18001c7cf  jbe     short loc_18001C7F5
0x18001c7d1  test    ebx, ebx
0x18001c7d3  jns     short loc_18001C7F5
0x18001c7d5  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18001c7da  mov     edx, ebx; int
0x18001c7dc  mov     rcx, rax; this
0x18001c7df  call    ?LogDMPollUserScheduleSetupFail@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogDMPollUserScheduleSetupFail(long)
0x18001c7e4  lea     rcx, [rbp+57h+var_78]; this
0x18001c7e8  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x18001c7ed  nop
0x18001c7ee  mov     eax, ebx
0x18001c7f0  jmp     loc_18001C8EE
0x18001c7f5  xorps   xmm0, xmm0
0x18001c7f8  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x18001c7fc  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x18001c800  call    cs:__imp_GetSystemTime
0x18001c806  mov     [rbp+57h+hKey], 0
0x18001c80e  lea     rdx, [rbp+57h+hKey]; HKEY *
0x18001c812  mov     rcx, rdi; pszMore
0x18001c815  call    ?GetDeviceEnrollerKey@@YAJPEBGPEAPEAUHKEY__@@H@Z; GetDeviceEnrollerKey(ushort const *,HKEY__ * *,int)
0x18001c81a  mov     ebx, eax
0x18001c81c  test    eax, eax
0x18001c81e  jns     short loc_18001C854
0x18001c820  mov     rcx, [rbp+5Fh]; this
0x18001c824  mov     r9d, eax; char *
0x18001c827  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18001c82e  mov     edx, 1479h; void *
0x18001c833  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c838  lea     rcx, [rbp+57h+var_78]; this
0x18001c83c  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x18001c841  nop
0x18001c842  mov     rcx, [rbp+57h+hKey]; hKey
0x18001c846  test    rcx, rcx
0x18001c849  jz      short loc_18001C852
0x18001c84b  call    cs:__imp_RegCloseKey
0x18001c851  nop
0x18001c852  jmp     short loc_18001C7EE
0x18001c854  xorps   xmm0, xmm0
0x18001c857  movups  [rbp+57h+var_58], xmm0
0x18001c85b  mov     esi, 10h
0x18001c860  mov     [rbp+57h+var_70], esi
0x18001c863  lea     rax, [rbp+57h+var_70]
0x18001c867  mov     [rsp+0D0h+pcbData], rax; pcbData
0x18001c86c  lea     rax, [rbp+57h+var_58]
0x18001c870  mov     [rsp+0D0h+pvData], rax; pvData
0x18001c875  mov     [rsp+0D0h+pdwType], 0; pdwType
0x18001c87e  lea     r9d, [rsi-8]; dwFlags
0x18001c882  lea     r8, aUsersessionsch; "UserSessionScheduleTimestamp"
0x18001c889  xor     edx, edx; lpSubKey
0x18001c88b  mov     rbx, [rbp+57h+hKey]
0x18001c88f  mov     rcx, rbx; hkey
0x18001c892  call    cs:__imp_RegGetValueW
0x18001c898  mov     edi, eax
0x18001c89a  test    eax, eax
0x18001c89c  jle     short loc_18001C8A7
0x18001c89e  movzx   edi, ax
0x18001c8a1  or      edi, 80070000h
0x18001c8a7  test    edi, edi
0x18001c8a9  jns     short loc_18001C8D3
0x18001c8ab  mov     dword ptr [rsp+0D0h+pvData], esi; cbData
0x18001c8af  lea     rax, [rbp+57h+SystemTime]
0x18001c8b3  mov     [rsp+0D0h+pdwType], rax; lpData
0x18001c8b8  mov     r9d, 3; dwType
0x18001c8be  xor     r8d, r8d; Reserved
0x18001c8c1  lea     rdx, aUsersessionsch; "UserSessionScheduleTimestamp"
0x18001c8c8  mov     rcx, rbx; hKey
0x18001c8cb  call    cs:__imp_RegSetValueExW
0x18001c8d1  mov     edi, eax
0x18001c8d3  lea     rcx, [rbp+57h+var_78]; this
0x18001c8d7  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x18001c8dc  nop
0x18001c8dd  test    rbx, rbx
0x18001c8e0  jz      short loc_18001C8EC
0x18001c8e2  mov     rcx, rbx; hKey
0x18001c8e5  call    cs:__imp_RegCloseKey
0x18001c8eb  nop
0x18001c8ec  mov     eax, edi
0x18001c8ee  mov     rcx, [rbp+57h+var_28]
0x18001c8f2  xor     rcx, rsp; StackCookie
0x18001c8f5  call    __security_check_cookie
0x18001c8fa  lea     r11, [rsp+0D0h+var_20]
0x18001c902  mov     rbx, [r11+38h]
0x18001c906  mov     rsi, [r11+40h]
0x18001c90a  mov     rsp, r11
0x18001c90d  pop     r14
0x18001c90f  pop     r13
0x18001c911  pop     r12
0x18001c913  pop     rdi
0x18001c914  pop     rbp
0x18001c915  retn
```
