# Microsoft::CommonDatapoints::UpdateStaticCommonDatapointsInRegistry(void)

- ea: `0x1800154ac`
- end: `0x1800159de`
- name: `?UpdateStaticCommonDatapointsInRegistry@CommonDatapoints@Microsoft@@SAJXZ`
- size: `1330`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1802549f8`

## callees

- `0x1800154ac`
- `0x1800e65d4`
- `0x180107fc4`
- `0x18010f8f4`
- `0x180117080`
- `0x1801d7060`
- `0x1801f1c7c`
- `0x18020aac0`
- `0x18020bab8`
- `0x18020bd7c`
- `0x180252aec`
- `0x180258138`
- `0x180258210`
- `0x1802582e4`
- `0x180369010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001587c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001587c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180015863`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180015863`
- `ntdll!NtPowerInformation` at `0x18001574a`
- `ntdll!NtPowerInformation` at `0x18001574a`
- `ntdll!RtlCheckPortableOperatingSystem` at `0x18001578e`
- `ntdll!RtlCheckPortableOperatingSystem` at `0x18001578e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800155aa`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800155aa`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x180015602`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x180015602`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001555c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001555c`
- `api-ms-win-core-sysinfo-l1-2-1!GetPhysicallyInstalledSystemMemory` at `0x18001568a`
- `api-ms-win-core-sysinfo-l1-2-1!GetPhysicallyInstalledSystemMemory` at `0x18001568a`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!GetActiveProcessorCount` at `0x1800155ca`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!GetActiveProcessorCount` at `0x1800155ca`
- `api-ms-win-shcore-sysinfo-l1-1-0!IsOS` at `0x1800156ca`
- `api-ms-win-shcore-sysinfo-l1-1-0!IsOS` at `0x1800156ca`
- `api-ms-win-power-base-l1-1-0!PowerDeterminePlatformRoleEx` at `0x180015705`
- `api-ms-win-power-base-l1-1-0!PowerDeterminePlatformRoleEx` at `0x180015705`

## string_xrefs

- `0x18001559c`: `Software\Microsoft\SQMClient\Windows\CommonDatapoints`
- `0x18001585c`: `ReAgent.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 Microsoft::CommonDatapoints::UpdateStaticCommonDatapointsInRegistry(void)
{
  const wchar_t *v0; // rdx
  HKEY v1; // rcx
  const wchar_t *v2; // r8
  const wchar_t *v3; // rdx
  HKEY v4; // rcx
  struct _SECURITY_ATTRIBUTES *v5; // r8
  const wchar_t *v6; // r9
  HKEY *phkResult; // rax
  LSTATUS Key; // eax
  signed int v9; // ebx
  bool v10; // cc
  DWORDLONG ullTotalPhys; // rcx
  int v12; // eax
  HMODULE Library; // rax
  const wchar_t *v14; // rdx
  HKEY v15; // rcx
  FARPROC ProcAddress; // rax
  unsigned int dwOptions; // [rsp+20h] [rbp-E0h]
  unsigned __int8 v19[4]; // [rsp+50h] [rbp-B0h] BYREF
  char OutputBuffer; // [rsp+54h] [rbp-ACh] BYREF
  _BYTE v21[3]; // [rsp+55h] [rbp-ABh] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int8 v23[4]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int8 v24[4]; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned __int8 v25[4]; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int8 v26[4]; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned __int8 v27[8]; // [rsp+70h] [rbp-90h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 TotalMemoryInKilobytes; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v30; // [rsp+88h] [rbp-78h] BYREF
  HMODULE v31; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v32; // [rsp+98h] [rbp-68h] BYREF
  _MEMORYSTATUSEX Buffer; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t v34; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v35[124]; // [rsp+E2h] [rbp-1Eh] BYREF
  __int16 v36; // [rsp+15Eh] [rbp+5Eh]
  wchar_t v37; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v38[126]; // [rsp+162h] [rbp+62h] BYREF

  memset_0(&Buffer, 0, sizeof(Buffer));
  v34 = 0;
  memset_0(v35, 0, 0x7Eu);
  *(_DWORD *)v19 = 0;
  *(_DWORD *)v23 = 0;
  hKey = 0;
  OutputBuffer = 0;
  v21[0] = 0;
  TotalMemoryInKilobytes = 0;
  *(_DWORD *)v24 = 0;
  *(_DWORD *)v25 = 0;
  v37 = 0;
  memset_0(v38, 0, sizeof(v38));
  *(_DWORD *)v26 = 0;
  *(_DWORD *)v27 = 0;
  v31 = 0;
  v32 = 0;
  SystemTimeAsFileTime = 0;
  if ( Microsoft::CommonDatapoints::RegGetDWord64Value(v1, v0, v2, &v32) )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    Microsoft::CommonDatapoints::RegSetDWord64Value(v4, v3, v5, v6, SystemTimeAsFileTime.dwLowDateTime);
  }
  phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  Key = RegCreateKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\SQMClient\\Windows\\CommonDatapoints",
          0,
          0,
          0,
          0xF003Fu,
          0,
          phkResult,
          0);
  v9 = Key;
  v10 = Key <= 0;
  if ( Key )
  {
LABEL_43:
    if ( !v10 )
      v9 = (unsigned __int16)Key | 0x80070000;
    goto LABEL_45;
  }
  if ( hKey )
  {
    *(_DWORD *)v23 = GetActiveProcessorCount(0xFFFFu);
    v9 = Microsoft::CommonDatapoints::RegSetCommonDatapointValue(hKey, 0x1Fu, 4u, v23, 4u);
    if ( v9 >= 0 )
    {
      Buffer.dwLength = 64;
      if ( !GlobalMemoryStatusEx(&Buffer) )
        goto LABEL_48;
      ullTotalPhys = 1;
      v12 = 0;
      while ( ullTotalPhys < Buffer.ullTotalPhys )
      {
        ullTotalPhys *= 2LL;
        if ( (unsigned int)++v12 >= 0x40 )
        {
          if ( ullTotalPhys < Buffer.ullTotalPhys )
          {
            ullTotalPhys = Buffer.ullTotalPhys;
            goto LABEL_16;
          }
          break;
        }
      }
      if ( ullTotalPhys - Buffer.ullTotalPhys > 0x1000000 )
      {
        ullTotalPhys >>= 1;
        if ( ullTotalPhys < Buffer.ullTotalPhys && Buffer.ullTotalPhys - ullTotalPhys > 0x1000000 )
          ullTotalPhys = Buffer.ullTotalPhys;
      }
LABEL_16:
      *(_DWORD *)v19 = ullTotalPhys >> 20;
      v9 = Microsoft::CommonDatapoints::RegSetCommonDatapointValue(hKey, 0x23u, 4u, v19, 4u);
      if ( v9 >= 0 )
      {
LABEL_48:
        if ( !GetPhysicallyInstalledSystemMemory(&TotalMemoryInKilobytes)
          || (*(_DWORD *)v19 = TotalMemoryInKilobytes >> 10,
              v9 = Microsoft::CommonDatapoints::RegSetCommonDatapointValue(hKey, 0x28C1u, 4u, v19, 4u),
              v9 >= 0) )
        {
          *(_DWORD *)v19 = IsOS(0x1Cu);
          v9 = Microsoft::CommonDatapoints::RegSetCommonDatapointValue(hKey, 0x260u, 4u, v19, 4u);
          if ( v9 >= 0 )
          {
            *(_DWORD *)v19 = PowerDeterminePlatformRoleEx(2);
            Key = Microsoft::CommonDatapoints::RegSetCommonDatapointValue(hKey, 0x1F89u, 4u, v19, 4u);
            v9 = Key;
            v10 = Key <= 0;
            if ( !Key )
            {
              *(_DWORD *)v19 = 0;
              if ( NtPowerInformation((POWER_INFORMATION_LEVEL)66, 0, 0, &OutputBuffer, 1u) >= 0 && OutputBuffer )
                *(_DWORD *)v19 = 1;
              v9 = Microsoft::CommonDatapoints::RegSetCommonDatapointValue(hKey, 0x244Au, 4u, v19, 4u);
              if ( v9 >= 0 )
              {
                *(_DWORD *)v19 = 0;
                if ( (int)RtlCheckPortableOperatingSystem(v21) < 0 )
                  goto LABEL_29;
                if ( v21[0] )
                  *(_DWORD *)v19 = 1;
                v9 = Microsoft::CommonDatapoints::RegSetCommonDatapointValue(hKey, 0x23EDu, 4u, v19, 4u);
                if ( v9 >= 0 )
                {
LABEL_29:
                  *(_DWORD *)v19 = Microsoft::CommonDatapoints::DetermineInstallType();
                  v9 = Microsoft::CommonDatapoints::RegSetCommonDatapointValue(hKey, 0x244Cu, 4u, v19, 4u);
                  if ( v9 >= 0 )
                  {
                    if ( (int)Microsoft::CommonDatapoints::GetDiskGeometry((unsigned int *)v24, (unsigned int *)v25) < 0
                      || (v9 = Microsoft::CommonDatapoints::RegSetCommonDatapointValue(hKey, 0x31B8u, 4u, v24, 4u),
                          v9 >= 0)
                      && (v9 = Microsoft::CommonDatapoints::RegSetCommonDatapointValue(hKey, 0x31B9u, 4u, v25, 4u),
                          v9 >= 0) )
                    {
                      Library = LoadLibraryExW(L"ReAgent.dll", 0, 0x800u);
                      v31 = Library;
                      if ( !Library
                        || (ProcAddress = GetProcAddress(Library, "WinReIsWimBootEnabled")) == 0
                        || (*(_DWORD *)v19 = ((__int64 (__fastcall *)(_QWORD))ProcAddress)(0) != 0,
                            v9 = Microsoft::CommonDatapoints::RegSetCommonDatapointValue(hKey, 0x31BAu, 4u, v19, 4u),
                            v9 >= 0) )
                      {
                        v34 = 0;
                        v30 = 0;
                        if ( Microsoft::CommonDatapoints::RegGetStringValue(v15, v14, L"BuildLabEx", &v34, dwOptions)
                          || (v36 = 0, swscanf_s(&v34, L"%*d.%*d.%*[^.].%[^.].%d-%d", &v37, 64, v26, v27) != 3)
                          || (v9 = Microsoft::CommonDatapoints::RegSetCommonDatapointValue(hKey, 0x31C0u, 4u, v26, 4u),
                              v9 >= 0)
                          && (v9 = Microsoft::CommonDatapoints::RegSetCommonDatapointValue(hKey, 0x31C1u, 4u, v27, 4u),
                              v9 >= 0)
                          && (v9 = StringCchLengthW(&v37, 0x40u, &v30), v9 >= 0)
                          && (v9 = Microsoft::CommonDatapoints::RegSetCommonDatapointValue(
                                     hKey,
                                     0x31C2u,
                                     1u,
                                     (unsigned __int8 *)&v37,
                                     2 * (int)v30 + 2),
                              v9 >= 0) )
                        {
                          v9 = 0;
                        }
                      }
                    }
                  }
                }
              }
              goto LABEL_45;
            }
            goto LABEL_43;
          }
        }
      }
    }
  }
LABEL_45:
  Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::~CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>(&v31);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800154ac  push    rbp
0x1800154ae  push    rbx
0x1800154af  push    rsi
0x1800154b0  push    rdi
0x1800154b1  push    r14
0x1800154b3  push    r15
0x1800154b5  lea     rbp, [rsp-0F8h]
0x1800154bd  sub     rsp, 1F8h
0x1800154c4  mov     rax, cs:__security_cookie
0x1800154cb  xor     rax, rsp
0x1800154ce  mov     [rbp+120h+var_40], rax
0x1800154d5  mov     r15d, 40h ; '@'
0x1800154db  mov     r8d, r15d; Size
0x1800154de  xor     edx, edx; Val
0x1800154e0  lea     rcx, [rbp+120h+Buffer]; void *
0x1800154e4  call    memset_0
0x1800154e9  xor     edi, edi
0x1800154eb  mov     [rbp+120h+var_140], di
0x1800154ef  lea     ebx, [rdi+7Eh]
0x1800154f2  mov     r8d, ebx; Size
0x1800154f5  xor     edx, edx; Val
0x1800154f7  lea     rcx, [rbp+120h+var_13E]; void *
0x1800154fb  call    memset_0
0x180015500  mov     dword ptr [rsp+220h+var_1D0], edi
0x180015504  mov     dword ptr [rsp+220h+var_1C0], edi
0x180015508  mov     [rsp+220h+hKey], rdi
0x18001550d  mov     [rsp+220h+OutputBuffer], dil
0x180015512  mov     [rsp+220h+var_1CB], dil
0x180015517  mov     [rbp+120h+TotalMemoryInKilobytes], rdi
0x18001551b  mov     dword ptr [rsp+220h+var_1BC], edi
0x18001551f  mov     dword ptr [rsp+220h+var_1B8], edi
0x180015523  mov     [rbp+120h+var_C0], di
0x180015527  mov     r8d, ebx; Size
0x18001552a  xor     edx, edx; Val
0x18001552c  lea     rcx, [rbp+120h+var_BE]; void *
0x180015530  call    memset_0
0x180015535  mov     dword ptr [rsp+220h+var_1B4], edi
0x180015539  mov     dword ptr [rsp+220h+var_1B0], edi
0x18001553d  mov     [rbp+120h+var_190], rdi
0x180015541  mov     [rbp+120h+var_188], rdi
0x180015545  mov     qword ptr [rsp+220h+SystemTimeAsFileTime.dwLowDateTime], rdi
0x18001554a  lea     r9, [rbp+120h+var_188]; unsigned __int64 *
0x18001554e  call    ?RegGetDWord64Value@CommonDatapoints@Microsoft@@CAKPEAUHKEY__@@PEB_W1PEA_K@Z; Microsoft::CommonDatapoints::RegGetDWord64Value(HKEY__ *,wchar_t const *,wchar_t const *,unsigned __int64 *)
0x180015553  test    eax, eax
0x180015555  jz      short loc_180015571
0x180015557  lea     rcx, [rsp+220h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001555c  call    cs:__imp_GetSystemTimeAsFileTime
0x180015562  mov     rax, qword ptr [rsp+220h+SystemTimeAsFileTime.dwLowDateTime]
0x180015567  mov     qword ptr [rsp+220h+dwOptions], rax; Data
0x18001556c  call    ?RegSetDWord64Value@CommonDatapoints@Microsoft@@CAKPEAUHKEY__@@PEB_WPEAU_SECURITY_ATTRIBUTES@@1_K@Z; Microsoft::CommonDatapoints::RegSetDWord64Value(HKEY__ *,wchar_t const *,_SECURITY_ATTRIBUTES *,wchar_t const *,unsigned __int64)
0x180015571  lea     rcx, [rsp+220h+hKey]
0x180015576  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18001557b  mov     [rsp+220h+lpdwDisposition], rdi; lpdwDisposition
0x180015580  mov     [rsp+220h+phkResult], rax; phkResult
0x180015585  mov     [rsp+220h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18001558a  mov     [rsp+220h+samDesired], 0F003Fh; samDesired
0x180015592  mov     [rsp+220h+dwOptions], edi; dwOptions
0x180015596  xor     r9d, r9d; lpClass
0x180015599  xor     r8d, r8d; Reserved
0x18001559c  lea     rdx, SubKey; "Software\\Microsoft\\SQMClient\\Windows"...
0x1800155a3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800155aa  call    cs:__imp_RegCreateKeyExW
0x1800155b0  mov     ebx, eax
0x1800155b2  test    eax, eax
0x1800155b4  jnz     loc_18001599E
0x1800155ba  cmp     [rsp+220h+hKey], rdi
0x1800155bf  jz      loc_1800159A9
0x1800155c5  mov     ecx, 0FFFFh; GroupNumber
0x1800155ca  call    cs:__imp_GetActiveProcessorCount
0x1800155d0  mov     dword ptr [rsp+220h+var_1C0], eax
0x1800155d4  lea     esi, [rbx+4]
0x1800155d7  mov     [rsp+220h+dwOptions], esi; unsigned int
0x1800155db  lea     r9, [rsp+220h+var_1C0]; unsigned __int8 *
0x1800155e0  mov     r8d, esi; unsigned int
0x1800155e3  lea     edx, [rbx+1Fh]; unsigned int
0x1800155e6  mov     rcx, [rsp+220h+hKey]; hKey
0x1800155eb  call    ?RegSetCommonDatapointValue@CommonDatapoints@Microsoft@@CAJPEAUHKEY__@@KKPEAEK@Z; Microsoft::CommonDatapoints::RegSetCommonDatapointValue(HKEY__ *,ulong,ulong,uchar *,ulong)
0x1800155f0  mov     ebx, eax
0x1800155f2  test    eax, eax
0x1800155f4  js      loc_1800159A9
0x1800155fa  mov     [rbp+120h+Buffer.dwLength], r15d
0x1800155fe  lea     rcx, [rbp+120h+Buffer]; lpBuffer
0x180015602  call    cs:__imp_GlobalMemoryStatusEx
0x180015608  lea     r14d, [rsi-3]
0x18001560c  test    eax, eax
0x18001560e  jz      short loc_180015686
0x180015610  mov     rdx, [rbp+120h+Buffer.ullTotalPhys]
0x180015614  mov     ecx, r14d
0x180015617  mov     eax, edi
0x180015619  cmp     rcx, rdx
0x18001561c  jnb     short loc_180015633
0x18001561e  add     rcx, rcx
0x180015621  add     eax, r14d
0x180015624  cmp     eax, r15d
0x180015627  jb      short loc_180015619
0x180015629  cmp     rcx, rdx
0x18001562c  jnb     short loc_180015633
0x18001562e  mov     rcx, rdx
0x180015631  jmp     short loc_180015659
0x180015633  mov     rax, rcx
0x180015636  sub     rax, rdx
0x180015639  mov     r8d, 1000000h
0x18001563f  cmp     rax, r8
0x180015642  jbe     short loc_180015659
0x180015644  shr     rcx, 1
0x180015647  cmp     rcx, rdx
0x18001564a  jnb     short loc_180015659
0x18001564c  mov     rax, rdx
0x18001564f  sub     rax, rcx
0x180015652  cmp     rax, r8
0x180015655  cmova   rcx, rdx
0x180015659  shr     rcx, 14h
0x18001565d  mov     dword ptr [rsp+220h+var_1D0], ecx
0x180015661  mov     [rsp+220h+dwOptions], esi; unsigned int
0x180015665  lea     r9, [rsp+220h+var_1D0]; unsigned __int8 *
0x18001566a  mov     r8d, esi; unsigned int
0x18001566d  mov     edx, 23h ; '#'; unsigned int
0x180015672  mov     rcx, [rsp+220h+hKey]; hKey
0x180015677  call    ?RegSetCommonDatapointValue@CommonDatapoints@Microsoft@@CAJPEAUHKEY__@@KKPEAEK@Z; Microsoft::CommonDatapoints::RegSetCommonDatapointValue(HKEY__ *,ulong,ulong,uchar *,ulong)
0x18001567c  mov     ebx, eax
0x18001567e  test    eax, eax
0x180015680  js      loc_1800159A9
0x180015686  lea     rcx, [rbp+120h+TotalMemoryInKilobytes]; TotalMemoryInKilobytes
0x18001568a  call    cs:__imp_GetPhysicallyInstalledSystemMemory
0x180015690  test    eax, eax
0x180015692  jz      short loc_1800156C5
0x180015694  mov     rax, [rbp+120h+TotalMemoryInKilobytes]
0x180015698  shr     rax, 0Ah
0x18001569c  mov     dword ptr [rsp+220h+var_1D0], eax
0x1800156a0  mov     [rsp+220h+dwOptions], esi; unsigned int
0x1800156a4  lea     r9, [rsp+220h+var_1D0]; unsigned __int8 *
0x1800156a9  mov     r8d, esi; unsigned int
0x1800156ac  mov     edx, 28C1h; unsigned int
0x1800156b1  mov     rcx, [rsp+220h+hKey]; hKey
0x1800156b6  call    ?RegSetCommonDatapointValue@CommonDatapoints@Microsoft@@CAJPEAUHKEY__@@KKPEAEK@Z; Microsoft::CommonDatapoints::RegSetCommonDatapointValue(HKEY__ *,ulong,ulong,uchar *,ulong)
0x1800156bb  mov     ebx, eax
0x1800156bd  test    eax, eax
0x1800156bf  js      loc_1800159A9
0x1800156c5  mov     ecx, 1Ch; dwOS
0x1800156ca  call    cs:__imp_IsOS
0x1800156d0  mov     ecx, edi
0x1800156d2  test    eax, eax
0x1800156d4  setnz   cl
0x1800156d7  mov     dword ptr [rsp+220h+var_1D0], ecx
0x1800156db  mov     [rsp+220h+dwOptions], esi; unsigned int
0x1800156df  lea     r9, [rsp+220h+var_1D0]; unsigned __int8 *
0x1800156e4  mov     r8d, esi; unsigned int
0x1800156e7  mov     edx, 260h; unsigned int
0x1800156ec  mov     rcx, [rsp+220h+hKey]; hKey
0x1800156f1  call    ?RegSetCommonDatapointValue@CommonDatapoints@Microsoft@@CAJPEAUHKEY__@@KKPEAEK@Z; Microsoft::CommonDatapoints::RegSetCommonDatapointValue(HKEY__ *,ulong,ulong,uchar *,ulong)
0x1800156f6  mov     ebx, eax
0x1800156f8  test    eax, eax
0x1800156fa  js      loc_1800159A9
0x180015700  mov     ecx, 2
0x180015705  call    cs:__imp_PowerDeterminePlatformRoleEx
0x18001570b  mov     dword ptr [rsp+220h+var_1D0], eax
0x18001570f  mov     [rsp+220h+dwOptions], esi; unsigned int
0x180015713  lea     r9, [rsp+220h+var_1D0]; unsigned __int8 *
0x180015718  mov     r8d, esi; unsigned int
0x18001571b  mov     edx, 1F89h; unsigned int
0x180015720  mov     rcx, [rsp+220h+hKey]; hKey
0x180015725  call    ?RegSetCommonDatapointValue@CommonDatapoints@Microsoft@@CAJPEAUHKEY__@@KKPEAEK@Z; Microsoft::CommonDatapoints::RegSetCommonDatapointValue(HKEY__ *,ulong,ulong,uchar *,ulong)
0x18001572a  mov     ebx, eax
0x18001572c  test    eax, eax
0x18001572e  jnz     loc_18001599E
0x180015734  mov     dword ptr [rsp+220h+var_1D0], edi
0x180015738  mov     [rsp+220h+dwOptions], r14d; OutputBufferLength
0x18001573d  lea     r9, [rsp+220h+OutputBuffer]; OutputBuffer
0x180015742  xor     r8d, r8d; InputBufferLength
0x180015745  xor     edx, edx; InputBuffer
0x180015747  lea     ecx, [rax+42h]; PowerInformationLevel
0x18001574a  call    cs:__imp_NtPowerInformation
0x180015750  test    eax, eax
0x180015752  js      short loc_180015760
0x180015754  cmp     [rsp+220h+OutputBuffer], dil
0x180015759  jz      short loc_180015760
0x18001575b  mov     dword ptr [rsp+220h+var_1D0], r14d
0x180015760  mov     [rsp+220h+dwOptions], esi; unsigned int
0x180015764  lea     r9, [rsp+220h+var_1D0]; unsigned __int8 *
0x180015769  mov     r8d, esi; unsigned int
0x18001576c  mov     edx, 244Ah; unsigned int
0x180015771  mov     rcx, [rsp+220h+hKey]; hKey
0x180015776  call    ?RegSetCommonDatapointValue@CommonDatapoints@Microsoft@@CAJPEAUHKEY__@@KKPEAEK@Z; Microsoft::CommonDatapoints::RegSetCommonDatapointValue(HKEY__ *,ulong,ulong,uchar *,ulong)
0x18001577b  mov     ebx, eax
0x18001577d  test    eax, eax
0x18001577f  js      loc_1800159A9
0x180015785  mov     dword ptr [rsp+220h+var_1D0], edi
0x180015789  lea     rcx, [rsp+220h+var_1CB]
0x18001578e  call    cs:__imp_RtlCheckPortableOperatingSystem
0x180015794  test    eax, eax
0x180015796  js      short loc_1800157C9
0x180015798  cmp     [rsp+220h+var_1CB], dil
0x18001579d  jz      short loc_1800157A4
0x18001579f  mov     dword ptr [rsp+220h+var_1D0], r14d
0x1800157a4  mov     [rsp+220h+dwOptions], esi; unsigned int
0x1800157a8  lea     r9, [rsp+220h+var_1D0]; unsigned __int8 *
0x1800157ad  mov     r8d, esi; unsigned int
0x1800157b0  mov     edx, 23EDh; unsigned int
0x1800157b5  mov     rcx, [rsp+220h+hKey]; hKey
0x1800157ba  call    ?RegSetCommonDatapointValue@CommonDatapoints@Microsoft@@CAJPEAUHKEY__@@KKPEAEK@Z; Microsoft::CommonDatapoints::RegSetCommonDatapointValue(HKEY__ *,ulong,ulong,uchar *,ulong)
0x1800157bf  mov     ebx, eax
0x1800157c1  test    eax, eax
0x1800157c3  js      loc_1800159A9
0x1800157c9  call    ?DetermineInstallType@CommonDatapoints@Microsoft@@CAKXZ; Microsoft::CommonDatapoints::DetermineInstallType(void)
0x1800157ce  mov     dword ptr [rsp+220h+var_1D0], eax
0x1800157d2  mov     [rsp+220h+dwOptions], esi; unsigned int
0x1800157d6  lea     r9, [rsp+220h+var_1D0]; unsigned __int8 *
0x1800157db  mov     r8d, esi; unsigned int
0x1800157de  mov     edx, 244Ch; unsigned int
0x1800157e3  mov     rcx, [rsp+220h+hKey]; hKey
0x1800157e8  call    ?RegSetCommonDatapointValue@CommonDatapoints@Microsoft@@CAJPEAUHKEY__@@KKPEAEK@Z; Microsoft::CommonDatapoints::RegSetCommonDatapointValue(HKEY__ *,ulong,ulong,uchar *,ulong)
0x1800157ed  mov     ebx, eax
0x1800157ef  test    eax, eax
0x1800157f1  js      loc_1800159A9
0x1800157f7  lea     rdx, [rsp+220h+var_1B8]; unsigned int *
0x1800157fc  lea     rcx, [rsp+220h+var_1BC]; unsigned int *
0x180015801  call    ?GetDiskGeometry@CommonDatapoints@Microsoft@@CAJPEAK0@Z; Microsoft::CommonDatapoints::GetDiskGeometry(ulong *,ulong *)
0x180015806  test    eax, eax
0x180015808  js      short loc_180015854
0x18001580a  mov     [rsp+220h+dwOptions], esi; unsigned int
0x18001580e  lea     r9, [rsp+220h+var_1BC]; unsigned __int8 *
0x180015813  mov     r8d, esi; unsigned int
0x180015816  mov     edx, 31B8h; unsigned int
0x18001581b  mov     rcx, [rsp+220h+hKey]; hKey
0x180015820  call    ?RegSetCommonDatapointValue@CommonDatapoints@Microsoft@@CAJPEAUHKEY__@@KKPEAEK@Z; Microsoft::CommonDatapoints::RegSetCommonDatapointValue(HKEY__ *,ulong,ulong,uchar *,ulong)
0x180015825  mov     ebx, eax
0x180015827  test    eax, eax
0x180015829  js      loc_1800159A9
0x18001582f  mov     [rsp+220h+dwOptions], esi; unsigned int
0x180015833  lea     r9, [rsp+220h+var_1B8]; unsigned __int8 *
0x180015838  mov     r8d, esi; unsigned int
0x18001583b  mov     edx, 31B9h; unsigned int
0x180015840  mov     rcx, [rsp+220h+hKey]; hKey
0x180015845  call    ?RegSetCommonDatapointValue@CommonDatapoints@Microsoft@@CAJPEAUHKEY__@@KKPEAEK@Z; Microsoft::CommonDatapoints::RegSetCommonDatapointValue(HKEY__ *,ulong,ulong,uchar *,ulong)
0x18001584a  mov     ebx, eax
0x18001584c  test    eax, eax
0x18001584e  js      loc_1800159A9
0x180015854  xor     edx, edx; hFile
0x180015856  mov     r8d, 800h; dwFlags
0x18001585c  lea     rcx, LibFileName; "ReAgent.dll"
0x180015863  call    cs:__imp_LoadLibraryExW
0x180015869  mov     [rbp+120h+var_190], rax
0x18001586d  test    rax, rax
0x180015870  jz      short loc_1800158C0
0x180015872  lea     rdx, ProcName; "WinReIsWimBootEnabled"
0x180015879  mov     rcx, rax; hModule
0x18001587c  call    cs:__imp_GetProcAddress
0x180015882  test    rax, rax
0x180015885  jz      short loc_1800158C0
0x180015887  mov     dword ptr [rsp+220h+var_1D0], edi
0x18001588b  xor     ecx, ecx
0x18001588d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015892  test    eax, eax
0x180015894  jz      short loc_18001589B
0x180015896  mov     dword ptr [rsp+220h+var_1D0], r14d
0x18001589b  mov     [rsp+220h+dwOptions], esi; unsigned int
0x18001589f  lea     r9, [rsp+220h+var_1D0]; unsigned __int8 *
0x1800158a4  mov     r8d, esi; unsigned int
0x1800158a7  mov     edx, 31BAh; unsigned int
0x1800158ac  mov     rcx, [rsp+220h+hKey]; hKey
0x1800158b1  call    ?RegSetCommonDatapointValue@CommonDatapoints@Microsoft@@CAJPEAUHKEY__@@KKPEAEK@Z; Microsoft::CommonDatapoints::RegSetCommonDatapointValue(HKEY__ *,ulong,ulong,uchar *,ulong)
0x1800158b6  mov     ebx, eax
0x1800158b8  test    eax, eax
0x1800158ba  js      loc_1800159A9
0x1800158c0  mov     [rbp+120h+var_140], di
0x1800158c4  mov     [rbp+120h+var_198], rdi
0x1800158c8  lea     r9, [rbp+120h+var_140]; wchar_t *
0x1800158cc  lea     r8, aBuildlabex; "BuildLabEx"
0x1800158d3  call    ?RegGetStringValue@CommonDatapoints@Microsoft@@CAKPEAUHKEY__@@PEB_W1PEA_WK@Z; Microsoft::CommonDatapoints::RegGetStringValue(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t *,ulong)
0x1800158d8  test    eax, eax
0x1800158da  jnz     loc_18001599A
0x1800158e0  mov     [rbp+120h+var_C2], di
0x1800158e4  lea     rax, [rsp+220h+var_1B0]
0x1800158e9  mov     qword ptr [rsp+220h+samDesired], rax
0x1800158ee  lea     rax, [rsp+220h+var_1B4]
0x1800158f3  mov     qword ptr [rsp+220h+dwOptions], rax
0x1800158f8  mov     r9d, r15d
0x1800158fb  lea     r8, [rbp+120h+var_C0]
0x1800158ff  lea     rdx, aDDDD; "%*d.%*d.%*[^.].%[^.].%d-%d"
0x180015906  lea     rcx, [rbp+120h+var_140]; Buffer
0x18001590a  call    swscanf_s
0x18001590f  cmp     eax, 3
0x180015912  jnz     loc_18001599A
0x180015918  mov     [rsp+220h+dwOptions], esi; unsigned int
0x18001591c  lea     r9, [rsp+220h+var_1B4]; unsigned __int8 *
0x180015921  mov     r8d, esi; unsigned int
0x180015924  mov     edx, 31C0h; unsigned int
0x180015929  mov     rcx, [rsp+220h+hKey]; hKey
0x18001592e  call    ?RegSetCommonDatapointValue@CommonDatapoints@Microsoft@@CAJPEAUHKEY__@@KKPEAEK@Z; Microsoft::CommonDatapoints::RegSetCommonDatapointValue(HKEY__ *,ulong,ulong,uchar *,ulong)
0x180015933  mov     ebx, eax
0x180015935  test    eax, eax
0x180015937  js      short loc_1800159A9
0x180015939  mov     [rsp+220h+dwOptions], esi; unsigned int
0x18001593d  lea     r9, [rsp+220h+var_1B0]; unsigned __int8 *
0x180015942  mov     r8d, esi; unsigned int
0x180015945  mov     edx, 31C1h; unsigned int
0x18001594a  mov     rcx, [rsp+220h+hKey]; hKey
0x18001594f  call    ?RegSetCommonDatapointValue@CommonDatapoints@Microsoft@@CAJPEAUHKEY__@@KKPEAEK@Z; Microsoft::CommonDatapoints::RegSetCommonDatapointValue(HKEY__ *,ulong,ulong,uchar *,ulong)
0x180015954  mov     ebx, eax
0x180015956  test    eax, eax
  ... truncated ...
```
