# GatherSystemInformation(ReportData &)

- ea: `0x180032d40`
- end: `0x180033351`
- name: `?GatherSystemInformation@@YAJAEAUReportData@@@Z`
- size: `1553`
- prototype: `__int64 __fastcall(struct ReportData *)`
- caller_count: `3`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180005b40`
- `0x180056040`
- `0x1800778f0`

## callees

- `0x18000b6f0`
- `0x18001ce44`
- `0x18001cf30`
- `0x180020454`
- `0x1800253e0`
- `0x180032d40`
- `0x18003bb60`
- `0x18004ca90`
- `0x18004d8fc`
- `0x18004da30`
- `0x18004dea8`

## import_xrefs

- `ntdll!NtPowerInformation` at `0x180032ff7`
- `ntdll!NtPowerInformation` at `0x180032ff7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180032e2f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180032f19`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180032f5f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800330f6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003317f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180033243`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800332c2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180032e2f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180032f19`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180032f5f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800330f6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003317f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180033243`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800332c2`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18003302d`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18003302d`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180032db2`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180032db2`
- `api-ms-win-power-base-l1-1-0!PowerDeterminePlatformRoleEx` at `0x180032fd6`
- `api-ms-win-power-base-l1-1-0!PowerDeterminePlatformRoleEx` at `0x180032fd6`

## string_xrefs

- `0x180033157`: `SystemProductName`

## pseudocode

```c
int __fastcall GatherSystemInformation(struct ReportData *a1)
{
  __int64 v3; // rdi
  __int64 v4; // r8
  __int64 v5; // rax
  NTSTATUS v6; // eax
  __int64 v7; // rax
  __int64 v8; // rax
  char *v9; // rdi
  char *v10; // rbx
  __int64 v11; // rax
  __int64 v12; // rax
  LPDWORD pdwType; // [rsp+20h] [rbp-E0h]
  DWORD nSize; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE OutputBuffer[4]; // [rsp+44h] [rbp-BCh] BYREF
  int v16; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v17; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v18; // [rsp+60h] [rbp-A0h]
  _OSVERSIONINFOW VersionInformation; // [rsp+70h] [rbp-90h] BYREF
  WCHAR v20[8]; // [rsp+190h] [rbp+90h] BYREF
  __int128 v21; // [rsp+1A0h] [rbp+A0h]
  wchar_t pvData[256]; // [rsp+1B0h] [rbp+B0h] BYREF
  wchar_t Buffer[256]; // [rsp+3B0h] [rbp+2B0h] BYREF

  *(_OWORD *)v20 = 0;
  v21 = 0;
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  OutputBuffer[0] = 0;
  nSize = 0;
  v16 = 0;
  if ( !GetVersionExW(&VersionInformation) )
    return -2147467259;
  *((_DWORD *)a1 + 42) = VersionInformation.dwBuildNumber;
  memset_0(pvData, 0, sizeof(pvData));
  nSize = 510;
  v3 = -1;
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows NT\\CurrentVersion",
         L"BuildLabEx",
         2u,
         0,
         pvData,
         &nSize) )
  {
    std::wstring::_Assign<unsigned short>((char *)a1 + 176, &qword_18009CA18, 0);
  }
  else
  {
    v4 = -1;
    v17 = 0;
    v18 = 0;
    do
      ++v4;
    while ( pvData[v4] );
    std::wstring::_Construct<1,unsigned short const *>(&v17, pvData, v4);
    std::wstring::operator=((char *)a1 + 176, &v17);
    if ( *((_QWORD *)&v18 + 1) > 7u )
      std::_Deallocate<16>((void *)v17, 2LL * *((_QWORD *)&v18 + 1) + 2);
  }
  memset_0(pvData, 0, sizeof(pvData));
  memset_0(Buffer, 0, sizeof(Buffer));
  nSize = 510;
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows NT\\CurrentVersion",
         L"CurrentBuild",
         2u,
         0,
         pvData,
         &nSize) )
  {
    std::wstring::_Assign<unsigned short>((char *)a1 + 208, &qword_18009CA18, 0);
  }
  else
  {
    nSize = 4;
    if ( RegGetValueW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows NT\\CurrentVersion",
           L"UBR",
           0x10u,
           0,
           &v16,
           &nSize) )
    {
      std::wstring::assign((char *)a1 + 208, &qword_18009CA18);
    }
    else
    {
      LODWORD(pdwType) = v16;
      swprintf_s(Buffer, 0x100u, L"%s.%d", pvData, pdwType);
      v5 = std::wstring::wstring((__int64)&v17, (__int64)Buffer);
      std::wstring::operator=((char *)a1 + 208, v5);
      std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(&v17);
    }
  }
  *((_DWORD *)a1 + 60) = PowerDeterminePlatformRoleEx(2);
  v6 = NtPowerInformation((POWER_INFORMATION_LEVEL)66, 0, 0, OutputBuffer, 1u);
  if ( v6 < 0 )
    return v6 | 0x10000000;
  *((_BYTE *)a1 + 244) = OutputBuffer[0];
  nSize = 16;
  if ( !GetComputerNameExW(ComputerNamePhysicalNetBIOS, v20, &nSize) )
    return -2147467259;
  v17 = 0;
  v18 = 0;
  do
    ++v3;
  while ( v20[v3] );
  std::wstring::_Construct<1,unsigned short const *>(&v17, v20, v3);
  std::wstring::operator=((char *)a1 + 8, &v17);
  if ( *((_QWORD *)&v18 + 1) > 7u )
    std::_Deallocate<16>((void *)v17, 2LL * *((_QWORD *)&v18 + 1) + 2);
  memset_0(pvData, 0, sizeof(pvData));
  nSize = 510;
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\SystemInformation",
         L"SystemManufacturer",
         2u,
         0,
         pvData,
         &nSize) )
  {
    std::wstring::_Assign<unsigned short>((char *)a1 + 40, L"UNKNOWN", 7);
    std::wstring::_Assign<unsigned short>((char *)a1 + 72, &qword_18009CA18, 0);
  }
  else
  {
    v7 = std::wstring::wstring((__int64)&v17, (__int64)pvData);
    std::wstring::operator=((char *)a1 + 40, v7);
    std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(&v17);
    memset_0(pvData, 0, sizeof(pvData));
    nSize = 510;
    if ( RegGetValueW(
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Control\\SystemInformation",
           L"SystemProductName",
           2u,
           0,
           pvData,
           &nSize) )
    {
      std::wstring::assign((char *)a1 + 40, L"UNKNOWN");
      std::wstring::assign((char *)a1 + 72, &qword_18009CA18);
    }
    else
    {
      v8 = std::wstring::wstring((__int64)&v17, (__int64)pvData);
      std::wstring::operator=((char *)a1 + 72, v8);
      std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(&v17);
    }
  }
  memset_0(pvData, 0, sizeof(pvData));
  nSize = 510;
  v9 = (char *)a1 + 104;
  v10 = (char *)a1 + 136;
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\SystemInformation",
         L"BIOSReleaseDate",
         2u,
         0,
         pvData,
         &nSize) )
  {
    std::wstring::_Assign<unsigned short>(v9, L"UNKNOWN", 7);
    std::wstring::_Assign<unsigned short>(v10, &qword_18009CA18, 0);
  }
  else
  {
    v11 = std::wstring::wstring((__int64)&v17, (__int64)pvData);
    std::wstring::operator=(v9, v11);
    std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(&v17);
    memset_0(pvData, 0, sizeof(pvData));
    nSize = 510;
    if ( RegGetValueW(
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Control\\SystemInformation",
           L"BIOSVersion",
           2u,
           0,
           pvData,
           &nSize) )
    {
      std::wstring::assign(v9, L"UNKNOWN");
      std::wstring::assign(v10, &qword_18009CA18);
    }
    else
    {
      v12 = std::wstring::wstring((__int64)&v17, (__int64)pvData);
      std::wstring::operator=(v10, v12);
      std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(&v17);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180032d40  push    rbp
0x180032d42  push    rbx
0x180032d43  push    rsi
0x180032d44  push    rdi
0x180032d45  push    r12
0x180032d47  push    r13
0x180032d49  push    r14
0x180032d4b  push    r15
0x180032d4d  lea     rbp, [rsp-4C8h]
0x180032d55  sub     rsp, 5C8h
0x180032d5c  mov     rax, cs:__security_cookie
0x180032d63  xor     rax, rsp
0x180032d66  mov     [rbp+500h+var_50], rax
0x180032d6d  xorps   xmm0, xmm0
0x180032d70  mov     rbx, rcx
0x180032d73  lea     rcx, [rsp+600h+VersionInformation.dwMajorVersion]; void *
0x180032d78  xor     edx, edx; Val
0x180032d7a  mov     r8d, 118h; Size
0x180032d80  movups  xmmword ptr [rbp+500h+var_470], xmm0
0x180032d87  movups  [rbp+500h+var_460], xmm0
0x180032d8e  call    memset_0
0x180032d93  xor     r14d, r14d
0x180032d96  mov     [rsp+600h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x180032d9e  lea     rcx, [rsp+600h+VersionInformation]; lpVersionInformation
0x180032da3  mov     [rsp+600h+OutputBuffer], r14b
0x180032da8  mov     [rsp+600h+nSize], r14d
0x180032dad  mov     [rsp+600h+var_5B8], r14d
0x180032db2  call    cs:__imp_GetVersionExW
0x180032db8  test    eax, eax
0x180032dba  jnz     short loc_180032DC6
0x180032dbc  mov     eax, 80004005h
0x180032dc1  jmp     loc_18003332E
0x180032dc6  mov     eax, [rsp+600h+VersionInformation.dwBuildNumber]
0x180032dca  lea     rcx, [rbp+500h+var_450]; void *
0x180032dd1  xor     edx, edx; Val
0x180032dd3  mov     [rbx+0A8h], eax
0x180032dd9  mov     r8d, 200h; Size
0x180032ddf  call    memset_0
0x180032de4  lea     rax, [rsp+600h+nSize]
0x180032de9  mov     [rsp+600h+nSize], 1FEh
0x180032df1  mov     [rsp+600h+pcbData], rax; pcbData
0x180032df6  lea     r8, aBuildlabex; "BuildLabEx"
0x180032dfd  lea     rax, [rbp+500h+var_450]
0x180032e04  mov     r12d, 2
0x180032e0a  mov     [rsp+600h+pvData], rax; pvData
0x180032e0f  lea     rdx, SubKey; "Software\\Microsoft\\Windows NT\\Curren"...
0x180032e16  mov     r13, 0FFFFFFFF80000002h
0x180032e1d  mov     [rsp+600h+pdwType], r14; pdwType
0x180032e22  mov     r9d, r12d; dwFlags
0x180032e25  lea     rsi, [rbx+0B0h]
0x180032e2c  mov     rcx, r13; hkey
0x180032e2f  call    cs:__imp_RegGetValueW
0x180032e35  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180032e39  lea     r15, qword_18009CA18
0x180032e40  test    eax, eax
0x180032e42  jnz     short loc_180032EA6
0x180032e44  xorps   xmm0, xmm0
0x180032e47  lea     rax, [rbp+500h+var_450]
0x180032e4e  xorps   xmm1, xmm1
0x180032e51  mov     r8, rdi
0x180032e54  movups  [rsp+600h+var_5B0], xmm0
0x180032e59  movdqu  [rsp+600h+var_5A0], xmm1
0x180032e5f  inc     r8
0x180032e62  cmp     [rax+r8*2], r14w
0x180032e67  jnz     short loc_180032E5F
0x180032e69  lea     rdx, [rbp+500h+var_450]
0x180032e70  lea     rcx, [rsp+600h+var_5B0]
0x180032e75  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180032e7a  lea     rdx, [rsp+600h+var_5B0]
0x180032e7f  mov     rcx, rsi
0x180032e82  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180032e87  mov     rdx, qword ptr [rsp+600h+var_5A0+8]
0x180032e8c  cmp     rdx, 7
0x180032e90  jbe     short loc_180032EB4
0x180032e92  mov     rcx, qword ptr [rsp+600h+var_5B0]
0x180032e97  lea     rdx, ds:2[rdx*2]
0x180032e9f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180032ea4  jmp     short loc_180032EB4
0x180032ea6  xor     r8d, r8d
0x180032ea9  mov     rdx, r15
0x180032eac  mov     rcx, rsi
0x180032eaf  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180032eb4  mov     esi, 200h
0x180032eb9  lea     rcx, [rbp+500h+var_450]; void *
0x180032ec0  mov     r8d, esi; Size
0x180032ec3  xor     edx, edx; Val
0x180032ec5  call    memset_0
0x180032eca  mov     r8d, esi; Size
0x180032ecd  lea     rcx, [rbp+500h+Buffer]; void *
0x180032ed4  xor     edx, edx; Val
0x180032ed6  call    memset_0
0x180032edb  lea     rax, [rsp+600h+nSize]
0x180032ee0  mov     [rsp+600h+nSize], 1FEh
0x180032ee8  mov     [rsp+600h+pcbData], rax; pcbData
0x180032eed  lea     r8, aCurrentbuild; "CurrentBuild"
0x180032ef4  lea     rax, [rbp+500h+var_450]
0x180032efb  mov     r9d, r12d; dwFlags
0x180032efe  mov     [rsp+600h+pvData], rax; pvData
0x180032f03  lea     rdx, SubKey; "Software\\Microsoft\\Windows NT\\Curren"...
0x180032f0a  mov     rcx, r13; hkey
0x180032f0d  mov     [rsp+600h+pdwType], r14; pdwType
0x180032f12  lea     rsi, [rbx+0D0h]
0x180032f19  call    cs:__imp_RegGetValueW
0x180032f1f  test    eax, eax
0x180032f21  jnz     loc_180032FC5
0x180032f27  lea     rax, [rsp+600h+nSize]
0x180032f2c  mov     [rsp+600h+nSize], 4
0x180032f34  mov     [rsp+600h+pcbData], rax; pcbData
0x180032f39  lea     r8, aUbr; "UBR"
0x180032f40  lea     rax, [rsp+600h+var_5B8]
0x180032f45  mov     r9d, 10h; dwFlags
0x180032f4b  mov     [rsp+600h+pvData], rax; pvData
0x180032f50  lea     rdx, SubKey; "Software\\Microsoft\\Windows NT\\Curren"...
0x180032f57  mov     rcx, r13; hkey
0x180032f5a  mov     [rsp+600h+pdwType], r14; pdwType
0x180032f5f  call    cs:__imp_RegGetValueW
0x180032f65  test    eax, eax
0x180032f67  jnz     short loc_180032FB8
0x180032f69  mov     eax, [rsp+600h+var_5B8]
0x180032f6d  lea     r9, [rbp+500h+var_450]
0x180032f74  lea     r8, aSD; "%s.%d"
0x180032f7b  mov     dword ptr [rsp+600h+pdwType], eax
0x180032f7f  mov     edx, 100h; BufferCount
0x180032f84  lea     rcx, [rbp+500h+Buffer]; Buffer
0x180032f8b  call    swprintf_s
0x180032f90  lea     rdx, [rbp+500h+Buffer]
0x180032f97  lea     rcx, [rsp+600h+var_5B0]
0x180032f9c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180032fa1  mov     rdx, rax
0x180032fa4  mov     rcx, rsi
0x180032fa7  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180032fac  lea     rcx, [rsp+600h+var_5B0]; void *
0x180032fb1  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring const,ulong>::~pair<std::wstring const,ulong>(void)
0x180032fb6  jmp     short loc_180032FD3
0x180032fb8  mov     rdx, r15
0x180032fbb  mov     rcx, rsi
0x180032fbe  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180032fc3  jmp     short loc_180032FD3
0x180032fc5  xor     r8d, r8d
0x180032fc8  mov     rdx, r15
0x180032fcb  mov     rcx, rsi
0x180032fce  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180032fd3  mov     ecx, r12d
0x180032fd6  call    cs:__imp_PowerDeterminePlatformRoleEx
0x180032fdc  xor     edx, edx; InputBuffer
0x180032fde  mov     dword ptr [rsp+600h+pdwType], 1; OutputBufferLength
0x180032fe6  lea     r9, [rsp+600h+OutputBuffer]; OutputBuffer
0x180032feb  mov     [rbx+0F0h], eax
0x180032ff1  xor     r8d, r8d; InputBufferLength
0x180032ff4  lea     ecx, [rdx+42h]; PowerInformationLevel
0x180032ff7  call    cs:__imp_NtPowerInformation
0x180032ffd  test    eax, eax
0x180032fff  jns     short loc_18003300A
0x180033001  bts     eax, 1Ch
0x180033005  jmp     loc_18003332E
0x18003300a  mov     al, [rsp+600h+OutputBuffer]
0x18003300e  lea     r8, [rsp+600h+nSize]; nSize
0x180033013  lea     rdx, [rbp+500h+var_470]; lpBuffer
0x18003301a  mov     [rbx+0F4h], al
0x180033020  mov     ecx, 4; NameType
0x180033025  mov     [rsp+600h+nSize], 10h
0x18003302d  call    cs:__imp_GetComputerNameExW
0x180033033  test    eax, eax
0x180033035  jz      loc_180032DBC
0x18003303b  xorps   xmm0, xmm0
0x18003303e  lea     rax, [rbp+500h+var_470]
0x180033045  xorps   xmm1, xmm1
0x180033048  movups  [rsp+600h+var_5B0], xmm0
0x18003304d  movdqu  [rsp+600h+var_5A0], xmm1
0x180033053  inc     rdi
0x180033056  cmp     [rax+rdi*2], r14w
0x18003305b  jnz     short loc_180033053
0x18003305d  mov     r8, rdi
0x180033060  lea     rdx, [rbp+500h+var_470]
0x180033067  lea     rcx, [rsp+600h+var_5B0]
0x18003306c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180033071  lea     rcx, [rbx+8]
0x180033075  lea     rdx, [rsp+600h+var_5B0]
0x18003307a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003307f  mov     rdx, qword ptr [rsp+600h+var_5A0+8]
0x180033084  cmp     rdx, 7
0x180033088  jbe     short loc_18003309C
0x18003308a  mov     rcx, qword ptr [rsp+600h+var_5B0]
0x18003308f  lea     rdx, ds:2[rdx*2]
0x180033097  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18003309c  xor     edx, edx; Val
0x18003309e  lea     rcx, [rbp+500h+var_450]; void *
0x1800330a5  mov     r8d, 200h; Size
0x1800330ab  call    memset_0
0x1800330b0  lea     rax, [rsp+600h+nSize]
0x1800330b5  mov     [rsp+600h+nSize], 1FEh
0x1800330bd  mov     [rsp+600h+pcbData], rax; pcbData
0x1800330c2  lea     r13, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Sys"...
0x1800330c9  lea     rax, [rbp+500h+var_450]
0x1800330d0  mov     r9d, r12d; dwFlags
0x1800330d3  mov     [rsp+600h+pvData], rax; pvData
0x1800330d8  lea     r8, aSystemmanufact_0; "SystemManufacturer"
0x1800330df  mov     rdx, r13; lpSubKey
0x1800330e2  mov     [rsp+600h+pdwType], r14; pdwType
0x1800330e7  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800330ee  lea     rsi, [rbx+28h]
0x1800330f2  lea     rdi, [rbx+48h]
0x1800330f6  call    cs:__imp_RegGetValueW
0x1800330fc  lea     r12, aUnknown_2; "UNKNOWN"
0x180033103  test    eax, eax
0x180033105  jnz     loc_1800331C9
0x18003310b  lea     rdx, [rbp+500h+var_450]
0x180033112  lea     rcx, [rsp+600h+var_5B0]
0x180033117  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003311c  mov     rdx, rax
0x18003311f  mov     rcx, rsi
0x180033122  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180033127  lea     rcx, [rsp+600h+var_5B0]; void *
0x18003312c  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring const,ulong>::~pair<std::wstring const,ulong>(void)
0x180033131  xor     edx, edx; Val
0x180033133  lea     rcx, [rbp+500h+var_450]; void *
0x18003313a  mov     r8d, 200h; Size
0x180033140  call    memset_0
0x180033145  lea     rax, [rsp+600h+nSize]
0x18003314a  mov     [rsp+600h+nSize], 1FEh
0x180033152  mov     [rsp+600h+pcbData], rax; pcbData
0x180033157  lea     r8, aSystemproductn_0; "SystemProductName"
0x18003315e  lea     rax, [rbp+500h+var_450]
0x180033165  mov     r9d, 2; dwFlags
0x18003316b  mov     [rsp+600h+pvData], rax; pvData
0x180033170  mov     rdx, r13; lpSubKey
0x180033173  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18003317a  mov     [rsp+600h+pdwType], r14; pdwType
0x18003317f  call    cs:__imp_RegGetValueW
0x180033185  test    eax, eax
0x180033187  jnz     short loc_1800331B1
0x180033189  lea     rdx, [rbp+500h+var_450]
0x180033190  lea     rcx, [rsp+600h+var_5B0]
0x180033195  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003319a  mov     rdx, rax
0x18003319d  mov     rcx, rdi
0x1800331a0  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800331a5  lea     rcx, [rsp+600h+var_5B0]; void *
0x1800331aa  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring const,ulong>::~pair<std::wstring const,ulong>(void)
0x1800331af  jmp     short loc_1800331E8
0x1800331b1  mov     rdx, r12
0x1800331b4  mov     rcx, rsi
0x1800331b7  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1800331bc  mov     rdx, r15
0x1800331bf  mov     rcx, rdi
0x1800331c2  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1800331c7  jmp     short loc_1800331E8
0x1800331c9  mov     r8d, 7
0x1800331cf  mov     rdx, r12
0x1800331d2  mov     rcx, rsi
0x1800331d5  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800331da  xor     r8d, r8d
0x1800331dd  mov     rdx, r15
0x1800331e0  mov     rcx, rdi
0x1800331e3  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800331e8  xor     edx, edx; Val
0x1800331ea  lea     rcx, [rbp+500h+var_450]; void *
0x1800331f1  mov     r8d, 200h; Size
0x1800331f7  call    memset_0
0x1800331fc  lea     rax, [rsp+600h+nSize]
0x180033201  mov     [rsp+600h+nSize], 1FEh
0x180033209  mov     [rsp+600h+pcbData], rax; pcbData
0x18003320e  lea     rdi, [rbx+68h]
0x180033212  lea     rax, [rbp+500h+var_450]
0x180033219  mov     esi, 2
0x18003321e  mov     [rsp+600h+pvData], rax; pvData
0x180033223  lea     r8, aBiosreleasedat; "BIOSReleaseDate"
0x18003322a  mov     r9d, esi; dwFlags
0x18003322d  mov     [rsp+600h+pdwType], r14; pdwType
0x180033232  mov     rdx, r13; lpSubKey
0x180033235  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18003323c  add     rbx, 88h
0x180033243  call    cs:__imp_RegGetValueW
0x180033249  test    eax, eax
0x18003324b  jnz     loc_18003330C
0x180033251  lea     rdx, [rbp+500h+var_450]
0x180033258  lea     rcx, [rsp+600h+var_5B0]
0x18003325d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180033262  mov     rdx, rax
0x180033265  mov     rcx, rdi
0x180033268  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003326d  lea     rcx, [rsp+600h+var_5B0]; void *
0x180033272  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring const,ulong>::~pair<std::wstring const,ulong>(void)
0x180033277  xor     edx, edx; Val
0x180033279  lea     rcx, [rbp+500h+var_450]; void *
0x180033280  mov     r8d, 200h; Size
0x180033286  call    memset_0
0x18003328b  lea     rax, [rsp+600h+nSize]
0x180033290  mov     [rsp+600h+nSize], 1FEh
0x180033298  mov     [rsp+600h+pcbData], rax; pcbData
0x18003329d  lea     r8, aBiosversion; "BIOSVersion"
0x1800332a4  lea     rax, [rbp+500h+var_450]
0x1800332ab  mov     r9d, esi; dwFlags
0x1800332ae  mov     [rsp+600h+pvData], rax; pvData
0x1800332b3  mov     rdx, r13; lpSubKey
0x1800332b6  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800332bd  mov     [rsp+600h+pdwType], r14; pdwType
0x1800332c2  call    cs:__imp_RegGetValueW
0x1800332c8  test    eax, eax
0x1800332ca  jnz     short loc_1800332F4
  ... truncated ...
```
