# SyncPollingOptionsForMultipleSession(ushort const *)

- ea: `0x18001208c`
- end: `0x180012368`
- name: `?SyncPollingOptionsForMultipleSession@@YAJPEBG@Z`
- size: `732`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18004ff88`

## callees

- `0x1800071c0`
- `0x180011938`
- `0x18001208c`
- `0x1800128c4`
- `0x18001aec8`
- `0x18002e1a0`
- `0x18003dba8`
- `0x18004e314`
- `0x180062988`
- `0x180062b48`
- `0x1800643c0`
- `0x180065b80`
- `0x180071300`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180012329`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180012329`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800122f0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800122f0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800122a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012343`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800122a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012343`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180012258`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180012258`
- `DMCmnUtils!IsWvdFeatureAllowed` at `0x1800120d5`
- `DMCmnUtils!IsWvdFeatureAllowed` at `0x1800120d5`
- `DMCmnUtils!DmDeleteTask` at `0x180012212`
- `DMCmnUtils!DmDeleteTask` at `0x180012212`

## string_xrefs

- `0x1800121ee`: `Schedule #4 created by enrollment client`
- `0x180012201`: `Schedule #4 created by enrollment client`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SyncPollingOptionsForMultipleSession(const unsigned __int16 *a1)
{
  int v3; // edi
  int v4; // r15d
  unsigned int v5; // ebx
  unsigned int MultipleSessionValueFromRegistry; // r14d
  unsigned int v7; // r14d
  unsigned int v8; // r15d
  __int64 i; // rdi
  __int64 v10; // rcx
  int v11; // edi
  CEnrollmentLogger *Logger; // rax
  int DeviceEnrollerKey; // eax
  HKEY v14; // rbx
  LSTATUS ValueW; // eax
  int pdwType; // [rsp+20h] [rbp-59h]
  int pcbData; // [rsp+30h] [rbp-49h]
  int v18; // [rsp+38h] [rbp-41h]
  unsigned int v19[2]; // [rsp+50h] [rbp-29h] BYREF
  _BYTE v20[8]; // [rsp+58h] [rbp-21h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-19h] BYREF
  DWORD v22; // [rsp+68h] [rbp-11h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+70h] [rbp-9h] BYREF
  __int128 pvData; // [rsp+80h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  *(_QWORD *)v19 = 0;
  hKey = 0;
  EvtPerfTraceScope::EvtPerfTraceScope((EvtPerfTraceScope *)v20, "SyncPollingOptionsForMultipleSession");
  if ( !IsWvdFeatureAllowed(a1) )
  {
    EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v20);
    return 1;
  }
  v3 = 0;
  v4 = 0;
  v5 = 1;
  while ( v4 < 2 )
  {
    MultipleSessionValueFromRegistry = GetMultipleSessionValueFromRegistry(
                                         a1,
                                         (LPCWSTR)(&g_MultipleSessionRegistryKeyNames)[v4],
                                         &v19[v4]);
    if ( (int)(MultipleSessionValueFromRegistry + 0x80000000) >= 0 && MultipleSessionValueFromRegistry != -2147024894 )
    {
      EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v20);
      return MultipleSessionValueFromRegistry;
    }
    if ( MultipleSessionValueFromRegistry != -2147024894 )
      v3 = 1;
    ++v4;
  }
  if ( !v3 )
  {
    EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v20);
    return v5;
  }
  v7 = v19[0];
  v8 = v19[0] != 0 ? v19[1] : 0;
  v19[1] = v8;
  for ( i = 0; i != 2; ++i )
  {
    SetMultipleSessionValueToRegistry(a1, (LPCWSTR)(&g_MultipleSessionRegistryKeyNames)[i], v19[i]);
    if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 2) != 0 )
      McTemplateU0zq_EventWriteTransfer(v10, DMScheduleAdminPollValues, (&g_MultipleSessionRegistryKeyNames)[i], v19[i]);
  }
  if ( v7 )
  {
    v11 = ScheduleOneOmaDmSession(a1, L"Schedule #4 created by enrollment client", v8, v7, v7, 0, pcbData, v18, 0, 1);
  }
  else
  {
    v11 = DmDeleteTask(L"\\Microsoft\\Windows\\EnterpriseMgmt", a1, L"Schedule #4 created by enrollment client");
    if ( (unsigned int)(v11 + 2147024894) <= 1 || v11 == -2147023728 )
      goto LABEL_24;
  }
  if ( v11 < 0 )
  {
    Logger = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogDMPollUserScheduleSetupFail(Logger, v11);
    EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v20);
    return (unsigned int)v11;
  }
LABEL_24:
  SystemTime = 0;
  GetSystemTime(&SystemTime);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  DeviceEnrollerKey = GetDeviceEnrollerKey(a1, &hKey);
  v5 = DeviceEnrollerKey;
  if ( DeviceEnrollerKey < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1479,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)(unsigned int)DeviceEnrollerKey,
      pdwType);
    EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v20);
    if ( hKey )
      RegCloseKey(hKey);
    return v5;
  }
  pvData = 0;
  v22 = 16;
  v14 = hKey;
  ValueW = RegGetValueW(hKey, 0, L"UserSessionScheduleTimestamp", 8u, 0, &pvData, &v22);
  v11 = ValueW;
  if ( ValueW > 0 )
    v11 = (unsigned __int16)ValueW | 0x80070000;
  if ( v11 < 0 )
    v11 = RegSetValueExW(v14, L"UserSessionScheduleTimestamp", 0, 3u, (const BYTE *)&SystemTime, 0x10u);
  EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v20);
  if ( v14 )
    RegCloseKey(v14);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18001208c  push    rbp
0x18001208e  push    rbx
0x18001208f  push    rsi
0x180012090  push    rdi
0x180012091  push    r14
0x180012093  push    r15
0x180012095  lea     rbp, [rsp-2Fh]
0x18001209a  sub     rsp, 0A8h
0x1800120a1  mov     rax, cs:__security_cookie
0x1800120a8  xor     rax, rsp
0x1800120ab  mov     [rbp+57h+var_40], rax
0x1800120af  mov     rsi, rcx
0x1800120b2  mov     qword ptr [rbp+57h+var_80], 0
0x1800120ba  mov     [rbp+57h+hKey], 0
0x1800120c2  lea     rdx, aSyncpollingopt; "SyncPollingOptionsForMultipleSession"
0x1800120c9  lea     rcx, [rbp+57h+var_78]; this
0x1800120cd  call    ??0EvtPerfTraceScope@@QEAA@PEBD@Z; EvtPerfTraceScope::EvtPerfTraceScope(char const *)
0x1800120d2  mov     rcx, rsi
0x1800120d5  call    cs:__imp_?IsWvdFeatureAllowed@@YAHPEBG@Z; IsWvdFeatureAllowed(ushort const *)
0x1800120db  test    eax, eax
0x1800120dd  jnz     short loc_1800120F3
0x1800120df  lea     rcx, [rbp+57h+var_78]; this
0x1800120e3  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x1800120e8  nop
0x1800120e9  mov     eax, 1
0x1800120ee  jmp     loc_18001234C
0x1800120f3  xor     edi, edi
0x1800120f5  xor     r15d, r15d
0x1800120f8  lea     ebx, [rdi+1]
0x1800120fb  lea     rcx, ?g_MultipleSessionRegistryKeyNames@@3PAPEBGA; ushort const * near * g_MultipleSessionRegistryKeyNames
0x180012102  cmp     r15d, 2
0x180012106  jge     short loc_180012159
0x180012108  movsxd  rdx, r15d
0x18001210b  lea     r8, [rbp+57h+var_80]
0x18001210f  lea     r8, [r8+rdx*4]; unsigned int *
0x180012113  mov     rdx, [rcx+rdx*8]; lpValue
0x180012117  mov     rcx, rsi; unsigned __int16 *
0x18001211a  call    ?GetMultipleSessionValueFromRegistry@@YAJPEBG0PEAK@Z; GetMultipleSessionValueFromRegistry(ushort const *,ushort const *,ulong *)
0x18001211f  mov     r14d, eax
0x180012122  mov     eax, 80000000h
0x180012127  lea     ecx, [r14+rax]
0x18001212b  test    eax, ecx
0x18001212d  jnz     short loc_180012138
0x18001212f  cmp     r14d, 80070002h
0x180012136  jnz     short loc_180012147
0x180012138  cmp     r14d, 80070002h
0x18001213f  cmovnz  edi, ebx
0x180012142  add     r15d, ebx
0x180012145  jmp     short loc_1800120FB
0x180012147  lea     rcx, [rbp+57h+var_78]; this
0x18001214b  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x180012150  nop
0x180012151  mov     eax, r14d
0x180012154  jmp     loc_18001234C
0x180012159  test    edi, edi
0x18001215b  jnz     short loc_18001216E
0x18001215d  lea     rcx, [rbp+57h+var_78]; this
0x180012161  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x180012166  nop
0x180012167  mov     eax, ebx
0x180012169  jmp     loc_18001234C
0x18001216e  mov     r14d, [rbp+57h+var_80]
0x180012172  mov     eax, r14d
0x180012175  neg     eax
0x180012177  sbb     r15d, r15d
0x18001217a  and     r15d, [rbp+57h+var_80+4]
0x18001217e  mov     [rbp+57h+var_80+4], r15d
0x180012182  xor     edi, edi
0x180012184  mov     r8d, [rbp+rdi*4+57h+var_80]; unsigned int
0x180012189  mov     rdx, [rcx+rdi*8]; lpValueName
0x18001218d  mov     rcx, rsi; unsigned __int16 *
0x180012190  call    ?SetMultipleSessionValueToRegistry@@YAJPEBG0K@Z; SetMultipleSessionValueToRegistry(ushort const *,ushort const *,ulong)
0x180012195  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 2
0x18001219c  jz      short loc_1800121BA
0x18001219e  mov     r9d, [rbp+rdi*4+57h+var_80]
0x1800121a3  lea     r8, ?g_MultipleSessionRegistryKeyNames@@3PAPEBGA; ushort const * near * g_MultipleSessionRegistryKeyNames
0x1800121aa  mov     r8, [r8+rdi*8]
0x1800121ae  lea     rdx, DMScheduleAdminPollValues
0x1800121b5  call    McTemplateU0zq_EventWriteTransfer
0x1800121ba  add     rdi, rbx
0x1800121bd  cmp     rdi, 2
0x1800121c1  lea     rcx, ?g_MultipleSessionRegistryKeyNames@@3PAPEBGA; ushort const * near * g_MultipleSessionRegistryKeyNames
0x1800121c8  jnz     short loc_180012184
0x1800121ca  test    r14d, r14d
0x1800121cd  jz      short loc_180012201
0x1800121cf  mov     [rsp+0D0h+var_88], ebx; int
0x1800121d3  mov     [rsp+0D0h+var_90], 0; int
0x1800121db  mov     dword ptr [rsp+0D0h+pvData], 0; int
0x1800121e3  mov     dword ptr [rsp+0D0h+pdwType], r14d; unsigned int
0x1800121e8  mov     r9d, r14d; unsigned int
0x1800121eb  mov     r8d, r15d; unsigned int
0x1800121ee  lea     rdx, aSchedule4Creat; "Schedule #4 created by enrollment clien"...
0x1800121f5  mov     rcx, rsi; unsigned __int16 *
0x1800121f8  call    ?ScheduleOneOmaDmSession@@YAJPEBG0KKKHHHHH@Z; ScheduleOneOmaDmSession(ushort const *,ushort const *,ulong,ulong,ulong,int,int,int,int,int)
0x1800121fd  mov     edi, eax
0x1800121ff  jmp     short loc_18001222B
0x180012201  lea     r8, aSchedule4Creat; "Schedule #4 created by enrollment clien"...
0x180012208  mov     rdx, rsi
0x18001220b  lea     rcx, aMicrosoftWindo_3; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x180012212  call    cs:__imp_?DmDeleteTask@@YAJPEBG00@Z; DmDeleteTask(ushort const *,ushort const *,ushort const *)
0x180012218  mov     edi, eax
0x18001221a  add     eax, 7FF8FFFEh
0x18001221f  cmp     eax, ebx
0x180012221  jbe     short loc_18001224D
0x180012223  cmp     edi, 80070490h
0x180012229  jz      short loc_18001224D
0x18001222b  test    edi, edi
0x18001222d  jns     short loc_18001224D
0x18001222f  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180012234  mov     edx, edi; int
0x180012236  mov     rcx, rax; this
0x180012239  call    ?LogDMPollUserScheduleSetupFail@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogDMPollUserScheduleSetupFail(long)
0x18001223e  lea     rcx, [rbp+57h+var_78]; this
0x180012242  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x180012247  nop
0x180012248  jmp     loc_18001234A
0x18001224d  xorps   xmm0, xmm0
0x180012250  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x180012254  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x180012258  call    cs:__imp_GetSystemTime
0x18001225e  xor     edx, edx
0x180012260  lea     rcx, [rbp+57h+hKey]
0x180012264  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180012269  lea     rdx, [rbp+57h+hKey]; HKEY *
0x18001226d  mov     rcx, rsi; pszMore
0x180012270  call    ?GetDeviceEnrollerKey@@YAJPEBGPEAPEAUHKEY__@@H@Z; GetDeviceEnrollerKey(ushort const *,HKEY__ * *,int)
0x180012275  mov     ebx, eax
0x180012277  test    eax, eax
0x180012279  jns     short loc_1800122B2
0x18001227b  mov     rcx, [rbp+5Fh]; this
0x18001227f  mov     r9d, eax; char *
0x180012282  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180012289  mov     edx, 1479h; void *
0x18001228e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012293  lea     rcx, [rbp+57h+var_78]; this
0x180012297  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x18001229c  nop
0x18001229d  mov     rcx, [rbp+57h+hKey]; hKey
0x1800122a1  test    rcx, rcx
0x1800122a4  jz      short loc_1800122AD
0x1800122a6  call    cs:__imp_RegCloseKey
0x1800122ac  nop
0x1800122ad  jmp     loc_180012167
0x1800122b2  xorps   xmm0, xmm0
0x1800122b5  movups  [rbp+57h+var_50], xmm0
0x1800122b9  mov     esi, 10h
0x1800122be  mov     [rbp+57h+var_68], esi
0x1800122c1  lea     rax, [rbp+57h+var_68]
0x1800122c5  mov     [rsp+0D0h+pcbData], rax; pcbData
0x1800122ca  lea     rax, [rbp+57h+var_50]
0x1800122ce  mov     [rsp+0D0h+pvData], rax; pvData
0x1800122d3  mov     [rsp+0D0h+pdwType], 0; pdwType
0x1800122dc  lea     r9d, [rsi-8]; dwFlags
0x1800122e0  lea     r8, ValueName; "UserSessionScheduleTimestamp"
0x1800122e7  xor     edx, edx; lpSubKey
0x1800122e9  mov     rbx, [rbp+57h+hKey]
0x1800122ed  mov     rcx, rbx; hkey
0x1800122f0  call    cs:__imp_RegGetValueW
0x1800122f6  mov     edi, eax
0x1800122f8  test    eax, eax
0x1800122fa  jle     short loc_180012305
0x1800122fc  movzx   edi, ax
0x1800122ff  or      edi, 80070000h
0x180012305  test    edi, edi
0x180012307  jns     short loc_180012331
0x180012309  mov     dword ptr [rsp+0D0h+pvData], esi; cbData
0x18001230d  lea     rax, [rbp+57h+SystemTime]
0x180012311  mov     [rsp+0D0h+pdwType], rax; lpData
0x180012316  mov     r9d, 3; dwType
0x18001231c  xor     r8d, r8d; Reserved
0x18001231f  lea     rdx, ValueName; "UserSessionScheduleTimestamp"
0x180012326  mov     rcx, rbx; hKey
0x180012329  call    cs:__imp_RegSetValueExW
0x18001232f  mov     edi, eax
0x180012331  lea     rcx, [rbp+57h+var_78]; this
0x180012335  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x18001233a  nop
0x18001233b  test    rbx, rbx
0x18001233e  jz      short loc_18001234A
0x180012340  mov     rcx, rbx; hKey
0x180012343  call    cs:__imp_RegCloseKey
0x180012349  nop
0x18001234a  mov     eax, edi
0x18001234c  mov     rcx, [rbp+57h+var_40]
0x180012350  xor     rcx, rsp; StackCookie
0x180012353  call    __security_check_cookie
0x180012358  add     rsp, 0A8h
0x18001235f  pop     r15
0x180012361  pop     r14
0x180012363  pop     rdi
0x180012364  pop     rsi
0x180012365  pop     rbx
0x180012366  pop     rbp
0x180012367  retn
```
