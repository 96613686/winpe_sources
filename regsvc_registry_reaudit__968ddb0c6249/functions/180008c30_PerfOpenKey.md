# PerfOpenKey

- ea: `0x180008c30`
- end: `0x1800093a1`
- name: `PerfOpenKey`
- size: `1905`
- prototype: `__int64 __fastcall(__int64, char)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800093a8`

## callees

- `0x180005da0`
- `0x180006ae0`
- `0x180007740`
- `0x180007fee`
- `0x180008042`
- `0x180008c30`
- `0x180009ef8`
- `0x18000aaa0`
- `0x18000aac8`
- `0x18000ac34`
- `0x18000ac80`
- `0x18000bef8`
- `0x18000c2b0`
- `0x18000f640`

## import_xrefs

- `ntdll!RtlGetVersion` at `0x180009303`
- `ntdll!RtlGetVersion` at `0x180009303`
- `ntdll!NtWaitForSingleObject` at `0x180008d84`
- `ntdll!NtWaitForSingleObject` at `0x180008d84`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180008cdf`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180008cdf`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008ef9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009343`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008ef9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009343`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008d2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000923d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009251`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008d2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000923d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009251`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000907f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000907f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180008dd6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180008dd6`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000912e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000912e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180009162`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180009162`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800091c7`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800091c7`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18000919f`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18000919f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180008f8a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180008fd2`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180008f8a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180008fd2`

## string_xrefs

- `0x1800090b8`: `%TEMP%\Perflib_Perfdata_`
- `0x18000901a`: `Configuration Flags`

## pseudocode

```c
__int64 __fastcall PerfOpenKey(__int64 a1, char a2)
{
  NTSTATUS Version; // ebx
  unsigned int v5; // edi
  _QWORD *v6; // rcx
  HANDLE v7; // r9
  HANDLE MutexW; // rax
  union _LARGE_INTEGER *v9; // r8
  NTSTATUS v10; // eax
  HANDLE v11; // rcx
  signed __int32 v12; // eax
  HKEY KeyPerflib; // rsi
  unsigned int *v14; // r8
  unsigned int *v15; // r8
  void *v16; // rax
  unsigned int *v17; // r8
  DWORD v18; // eax
  unsigned __int8 v19; // al
  DWORD CurrentProcessId; // eax
  char *FileW; // rcx
  HANDLE FileMappingW; // rax
  _DWORD *v23; // rax
  _DWORD *v24; // rbx
  unsigned int dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  unsigned int dwFlagsAndAttributesa; // [rsp+28h] [rbp-D8h]
  unsigned int dwFlagsAndAttributesb; // [rsp+28h] [rbp-D8h]
  unsigned __int16 *v29; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v30[2]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int8 v31[8]; // [rsp+50h] [rbp-B0h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v33; // [rsp+60h] [rbp-A0h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+70h] [rbp-90h] BYREF
  char v35; // [rsp+18Ah] [rbp+8Ah]
  unsigned __int16 v36[32]; // [rsp+190h] [rbp+90h] BYREF

  v33 = 0;
  *(_DWORD *)v31 = 0;
  Version = 0;
  v5 = 0;
  memset_0(&VersionInformation, 0, 0x11Cu);
  SystemTimeAsFileTime = 0;
  v6 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_qd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids,
      a1,
      NumberOfOpens);
    v6 = WPP_GLOBAL_Control;
  }
  v7 = hGlobalDataMutex;
  if ( hGlobalDataMutex )
    goto LABEL_13;
  MutexW = CreateMutexW(0, 0, 0);
  if ( MutexW )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&hGlobalDataMutex, (signed __int64)MutexW, 0) )
      CloseHandle(MutexW);
    v7 = hGlobalDataMutex;
    v6 = WPP_GLOBAL_Control;
    if ( !hGlobalDataMutex )
    {
      v5 = 1359;
      goto LABEL_89;
    }
LABEL_13:
    if ( a2 )
      goto LABEL_89;
    if ( dwThreadAndLibraryTimeout - 1 > 0xFFFFFFFD )
    {
      v9 = 0;
    }
    else
    {
      v9 = (union _LARGE_INTEGER *)&v33;
      v33 = (int)(-10000 * dwThreadAndLibraryTimeout);
    }
    v10 = NtWaitForSingleObject(v7, 0, v9);
    Version = v10;
    if ( v10 )
    {
      v5 = PerfpDosError(v10);
      v6 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        return v5;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_89;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids,
        (unsigned int)Version);
      goto LABEL_88;
    }
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    if ( bPerflibOpen && qword_18002B588 + 18000000000LL > *(unsigned __int64 *)&SystemTimeAsFileTime )
    {
      v11 = hGlobalDataMutex;
LABEL_87:
      ReleaseMutex(v11);
      goto LABEL_88;
    }
    v12 = _InterlockedIncrement(&NumberOfOpens);
    if ( bPerflibOpen )
    {
      if ( v12 != 2 )
        goto LABEL_83;
    }
    else if ( v12 != 1 )
    {
      goto LABEL_83;
    }
    KeyPerflib = PerflibciGetKeyPerflib();
    if ( !KeyPerflib )
    {
      _InterlockedAdd(&NumberOfOpens, 0xFFFFFFFF);
      v6 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids);
        v6 = WPP_GLOBAL_Control;
      }
      if ( !hGlobalDataMutex )
        goto LABEL_89;
      v11 = hGlobalDataMutex;
      goto LABEL_87;
    }
    v30[0] = 520;
    memset_0(&szUpdatingServiceName, 0, 0x208u);
    if ( !(unsigned int)PrivateRegQueryValueExT(
                          KeyPerflib,
                          L"Updating",
                          v14,
                          (unsigned int *)&v29,
                          &szUpdatingServiceName,
                          v30,
                          1) )
    {
      _InterlockedAdd(&NumberOfOpens, 0xFFFFFFFF);
      if ( hGlobalDataMutex )
        ReleaseMutex(hGlobalDataMutex);
      v5 = 0;
      goto LABEL_88;
    }
    v30[0] = 4;
    LODWORD(v29) = 0;
    *(_DWORD *)v31 = 0;
    if ( !(unsigned int)PrivateRegQueryValueExT(
                          KeyPerflib,
                          L"Disable Performance Counters",
                          v15,
                          (unsigned int *)&v29,
                          v31,
                          v30,
                          1)
      && (_DWORD)v29 == 4
      && *(_DWORD *)v31 == 1 )
    {
      _InterlockedAdd(&NumberOfOpens, 0xFFFFFFFF);
      v5 = 1058;
    }
    else
    {
      v5 = 0;
      if ( !pComputerName )
      {
        ComputerNameLength = 0;
        GetComputerNameW(0, &ComputerNameLength);
        v16 = (void *)operator new(saturated_mul(++ComputerNameLength, 2u));
        pComputerName = v16;
        if ( v16 && GetComputerNameW((LPWSTR)v16, &ComputerNameLength) )
        {
          *((_WORD *)pComputerName + ComputerNameLength) = 0;
          v18 = 2 * ComputerNameLength + 2;
        }
        else
        {
          v18 = 0;
        }
        ComputerNameLength = v18;
        LODWORD(v29) = 0;
        v30[0] = 4;
        if ( (unsigned int)PrivateRegQueryValueExT(
                             KeyPerflib,
                             L"Configuration Flags",
                             v17,
                             (unsigned int *)&v29,
                             &lPerflibConfigFlags,
                             v30,
                             1)
          || (_DWORD)v29 != 4 )
        {
          v19 = 4;
          *(_DWORD *)&lPerflibConfigFlags = 4;
        }
        else
        {
          v19 = lPerflibConfigFlags;
        }
        if ( !hPerflibSectionFile && (v19 & 0x10) != 0 )
        {
          *(_QWORD *)v30 = 0;
          v29 = 0;
          CurrentProcessId = GetCurrentProcessId();
          o__ultow_s_0(CurrentProcessId, v36, 32);
          if ( (int)StringCchCopyExW(
                      &szPerflibSectionName,
                      0x104u,
                      L"%TEMP%\\Perflib_Perfdata_",
                      &v29,
                      (unsigned __int64 *)v30,
                      dwFlagsAndAttributes) < 0
            || (int)StringCchCopyExW(
                      v29,
                      *(unsigned __int64 *)v30,
                      v36,
                      &v29,
                      (unsigned __int64 *)v30,
                      dwFlagsAndAttributesa) < 0
            || (int)StringCchCopyExW(
                      v29,
                      *(unsigned __int64 *)v30,
                      L".dat",
                      &v29,
                      (unsigned __int64 *)v30,
                      dwFlagsAndAttributesb) < 0
            || ExpandEnvironmentStringsW(&szPerflibSectionName, &szPerflibSectionFile, 0x104u) - 1 > 0x103 )
          {
            FileW = (char *)hPerflibSectionFile;
          }
          else
          {
            FileW = (char *)CreateFileW(&szPerflibSectionFile, 0xC0000000, 3u, 0, 4u, 0x14000100u, 0);
            hPerflibSectionFile = FileW;
          }
          if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
          {
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids);
          }
          else
          {
            FileMappingW = CreateFileMappingW(FileW, 0, 4u, 0, 0x4000u, &szPerflibSectionName);
            hPerflibSectionMap = FileMappingW;
            if ( FileMappingW )
            {
              v23 = MapViewOfFile(FileMappingW, 2u, 0, 0, 0x4000u);
              lpPerflibSectionAddr = v23;
              v24 = v23;
              if ( v23 )
              {
                if ( v23[3] != 19088743 )
                {
                  memset_0(v23 + 4, 0, 0x3FF0u);
                  *v24 = 0;
                  *(_QWORD *)(v24 + 1) = 127;
                  v24[3] = 19088743;
                }
                goto LABEL_76;
              }
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids);
              CloseHandle(hPerflibSectionMap);
              hPerflibSectionMap = 0;
            }
            else if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids);
            }
            CloseHandle(hPerflibSectionFile);
          }
          hPerflibSectionFile = 0;
        }
      }
    }
LABEL_76:
    OpenExtensibleObjects();
    if ( bPerflibOpen )
      _InterlockedAdd(&NumberOfOpens, 0xFFFFFFFF);
    bPerflibOpen = 1;
    if ( a1 == -2147483644 )
      qword_18002B588 = (__int64)SystemTimeAsFileTime;
    memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
    VersionInformation.dwOSVersionInfoSize = 284;
    Version = RtlGetVersion(&VersionInformation);
    if ( Version >= 0 && v35 == 1 )
      dwBoostPriority = 0;
LABEL_83:
    if ( a1 != -2147483644 && v5 != 1058 )
      _InterlockedAdd(&NumberOfOpens, 0xFFFFFFFF);
    v11 = hGlobalDataMutex;
    if ( !hGlobalDataMutex )
      goto LABEL_88;
    goto LABEL_87;
  }
  v6 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    return v5;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids);
LABEL_88:
    v6 = WPP_GLOBAL_Control;
  }
LABEL_89:
  if ( (*((_BYTE *)v6 + 28) & 4) != 0 && *((_BYTE *)v6 + 25) >= 4u )
    WPP_SF_dD(v6[2], 17, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids, (unsigned int)NumberOfOpens, Version);
  return v5;
}

```

## disassembly

```asm
0x180008c30  push    rbp
0x180008c32  push    rbx
0x180008c33  push    rsi
0x180008c34  push    rdi
0x180008c35  push    r12
0x180008c37  push    r13
0x180008c39  push    r14
0x180008c3b  push    r15
0x180008c3d  lea     rbp, [rsp-0E8h]
0x180008c45  sub     rsp, 1E8h
0x180008c4c  mov     rax, cs:__security_cookie
0x180008c53  xor     rax, rsp
0x180008c56  mov     [rbp+120h+var_50], rax
0x180008c5d  xor     r15d, r15d
0x180008c60  mov     sil, dl
0x180008c63  mov     r14, rcx
0x180008c66  mov     [rsp+220h+var_1C0], r15
0x180008c6b  xor     edx, edx; Val
0x180008c6d  mov     dword ptr [rsp+220h+var_1D0], r15d
0x180008c72  lea     rcx, [rsp+220h+VersionInformation]; void *
0x180008c77  mov     r8d, 11Ch; Size
0x180008c7d  mov     ebx, r15d
0x180008c80  mov     edi, r15d
0x180008c83  call    memset_0
0x180008c88  mov     qword ptr [rsp+220h+SystemTimeAsFileTime.dwLowDateTime], r15
0x180008c8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180008c94  lea     r12d, [r15+4]
0x180008c98  test    [rcx+1Ch], r12b
0x180008c9c  jz      short loc_180008CCC
0x180008c9e  cmp     [rcx+19h], r12b
0x180008ca2  jb      short loc_180008CCC
0x180008ca4  mov     eax, cs:?NumberOfOpens@@3JA; long NumberOfOpens
0x180008caa  lea     edx, [r15+0Ah]
0x180008cae  mov     rcx, [rcx+10h]
0x180008cb2  lea     r8, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids
0x180008cb9  mov     r9, r14
0x180008cbc  mov     [rsp+220h+dwCreationDisposition], eax
0x180008cc0  call    WPP_SF_qd
0x180008cc5  mov     rcx, cs:WPP_GLOBAL_Control
0x180008ccc  mov     r9, cs:?hGlobalDataMutex@@3PEAXEA; void * hGlobalDataMutex
0x180008cd3  test    r9, r9
0x180008cd6  jnz     short loc_180008D50
0x180008cd8  xor     r8d, r8d; lpName
0x180008cdb  xor     edx, edx; bInitialOwner
0x180008cdd  xor     ecx, ecx; lpMutexAttributes
0x180008cdf  call    cs:__imp_CreateMutexW
0x180008ce5  mov     rcx, rax; hObject
0x180008ce8  test    rax, rax
0x180008ceb  jnz     short loc_180008D20
0x180008ced  mov     rcx, cs:WPP_GLOBAL_Control
0x180008cf4  test    [rcx+1Ch], r12b
0x180008cf8  jz      loc_18000937C
0x180008cfe  cmp     byte ptr [rcx+19h], 2
0x180008d02  jb      loc_180009350
0x180008d08  mov     rcx, [rcx+10h]
0x180008d0c  lea     edx, [rax+0Bh]
0x180008d0f  lea     r8, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids
0x180008d16  call    WPP_SF_
0x180008d1b  jmp     loc_180009349
0x180008d20  xor     eax, eax
0x180008d22  lock cmpxchg cs:?hGlobalDataMutex@@3PEAXEA, rcx; void * hGlobalDataMutex
0x180008d2b  jz      short loc_180008D33
0x180008d2d  call    cs:__imp_CloseHandle
0x180008d33  mov     r9, cs:?hGlobalDataMutex@@3PEAXEA; void * hGlobalDataMutex
0x180008d3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180008d41  test    r9, r9
0x180008d44  jnz     short loc_180008D50
0x180008d46  mov     edi, 54Fh
0x180008d4b  jmp     loc_180009350
0x180008d50  test    sil, sil
0x180008d53  jnz     loc_180009350
0x180008d59  mov     ecx, cs:?dwThreadAndLibraryTimeout@@3KA; ulong dwThreadAndLibraryTimeout
0x180008d5f  lea     eax, [rcx-1]
0x180008d62  cmp     eax, 0FFFFFFFDh
0x180008d65  ja      short loc_180008D7C
0x180008d67  imul    eax, ecx, 0FFFFD8F0h
0x180008d6d  lea     r8, [rsp+220h+var_1C0]
0x180008d72  movsxd  rcx, eax
0x180008d75  mov     [rsp+220h+var_1C0], rcx
0x180008d7a  jmp     short loc_180008D7F
0x180008d7c  mov     r8, r15; Timeout
0x180008d7f  xor     edx, edx; Alertable
0x180008d81  mov     rcx, r9; Handle
0x180008d84  call    cs:__imp_NtWaitForSingleObject
0x180008d8a  mov     ebx, eax
0x180008d8c  test    eax, eax
0x180008d8e  jz      short loc_180008DD1
0x180008d90  mov     ecx, eax; int
0x180008d92  call    ?PerfpDosError@@YAKJ@Z; PerfpDosError(long)
0x180008d97  mov     edi, eax
0x180008d99  mov     rcx, cs:WPP_GLOBAL_Control
0x180008da0  test    [rcx+1Ch], r12b
0x180008da4  jz      loc_18000937C
0x180008daa  cmp     byte ptr [rcx+19h], 2
0x180008dae  jb      loc_180009350
0x180008db4  mov     rcx, [rcx+10h]
0x180008db8  lea     r8, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids
0x180008dbf  mov     edx, 0Ch
0x180008dc4  mov     r9d, ebx
0x180008dc7  call    WPP_SF_d
0x180008dcc  jmp     loc_180009349
0x180008dd1  lea     rcx, [rsp+220h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180008dd6  call    cs:__imp_GetSystemTimeAsFileTime
0x180008ddc  cmp     cs:?bPerflibOpen@@3EA, r15b; uchar bPerflibOpen
0x180008de3  jz      short loc_180008E09
0x180008de5  mov     rcx, 430E23400h
0x180008def  add     rcx, cs:qword_18002B588
0x180008df6  cmp     rcx, qword ptr [rsp+220h+SystemTimeAsFileTime.dwLowDateTime]
0x180008dfb  jbe     short loc_180008E09
0x180008dfd  mov     rcx, cs:?hGlobalDataMutex@@3PEAXEA; void * hGlobalDataMutex
0x180008e04  jmp     loc_180009343
0x180008e09  mov     r13d, 1
0x180008e0f  mov     eax, r13d
0x180008e12  lock xadd cs:?NumberOfOpens@@3JA, eax; long NumberOfOpens
0x180008e1a  add     eax, r13d
0x180008e1d  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180008e21  cmp     cs:?bPerflibOpen@@3EA, r15b; uchar bPerflibOpen
0x180008e28  jnz     short loc_180008E34
0x180008e2a  cmp     eax, r13d
0x180008e2d  jz      short loc_180008E3D
0x180008e2f  jmp     loc_18000931F
0x180008e34  cmp     eax, 2
0x180008e37  jnz     loc_18000931F
0x180008e3d  call    ?PerflibciGetKeyPerflib@@YAPEAUHKEY__@@XZ; PerflibciGetKeyPerflib(void)
0x180008e42  mov     rsi, rax
0x180008e45  test    rax, rax
0x180008e48  jnz     short loc_180008E9A
0x180008e4a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180008e4e  lock add cs:?NumberOfOpens@@3JA, ecx; long NumberOfOpens
0x180008e55  mov     rcx, cs:WPP_GLOBAL_Control
0x180008e5c  test    [rcx+1Ch], r12b
0x180008e60  jz      short loc_180008E82
0x180008e62  cmp     byte ptr [rcx+19h], 2
0x180008e66  jb      short loc_180008E82
0x180008e68  mov     rcx, [rcx+10h]
0x180008e6c  lea     edx, [rax+0Dh]
0x180008e6f  lea     r8, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids
0x180008e76  call    WPP_SF_
0x180008e7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180008e82  mov     rax, cs:?hGlobalDataMutex@@3PEAXEA; void * hGlobalDataMutex
0x180008e89  test    rax, rax
0x180008e8c  jz      loc_180009350
0x180008e92  mov     rcx, rax
0x180008e95  jmp     loc_180009343
0x180008e9a  mov     r8d, 208h; Size
0x180008ea0  lea     rdi, ?szUpdatingServiceName@@3PAGA; ushort near * szUpdatingServiceName
0x180008ea7  mov     rcx, rdi; void *
0x180008eaa  mov     [rsp+220h+var_1D8], r8d
0x180008eaf  xor     edx, edx; Val
0x180008eb1  call    memset_0
0x180008eb6  lea     rax, [rsp+220h+var_1D8]
0x180008ebb  mov     dword ptr [rsp+220h+hTemplateFile], r13d; int
0x180008ec0  mov     qword ptr [rsp+220h+dwFlagsAndAttributes], rax; unsigned int *
0x180008ec5  lea     r9, [rsp+220h+var_1E0]; unsigned int *
0x180008eca  lea     rdx, aUpdating; "Updating"
0x180008ed1  mov     qword ptr [rsp+220h+dwCreationDisposition], rdi; unsigned __int8 *
0x180008ed6  mov     rcx, rsi; KeyHandle
0x180008ed9  call    ?PrivateRegQueryValueExT@@YAJPEAUHKEY__@@PEBGPEAK2PEAE2H@Z; PrivateRegQueryValueExT(HKEY__ *,ushort const *,ulong *,ulong *,uchar *,ulong *,int)
0x180008ede  test    eax, eax
0x180008ee0  jnz     short loc_180008F07
0x180008ee2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180008ee6  lock add cs:?NumberOfOpens@@3JA, ecx; long NumberOfOpens
0x180008eed  mov     rcx, cs:?hGlobalDataMutex@@3PEAXEA; hMutex
0x180008ef4  test    rcx, rcx
0x180008ef7  jz      short loc_180008EFF
0x180008ef9  call    cs:__imp_ReleaseMutex
0x180008eff  mov     edi, r15d
0x180008f02  jmp     loc_180009349
0x180008f07  lea     rax, [rsp+220h+var_1D8]
0x180008f0c  mov     dword ptr [rsp+220h+hTemplateFile], r13d; int
0x180008f11  mov     qword ptr [rsp+220h+dwFlagsAndAttributes], rax; unsigned int *
0x180008f16  lea     r9, [rsp+220h+var_1E0]; unsigned int *
0x180008f1b  lea     rax, [rsp+220h+var_1D0]
0x180008f20  mov     [rsp+220h+var_1D8], r12d
0x180008f25  lea     rdx, ?DisablePerformanceCounters@@3QBGB; "Disable Performance Counters"
0x180008f2c  mov     qword ptr [rsp+220h+dwCreationDisposition], rax; unsigned __int8 *
0x180008f31  mov     rcx, rsi; KeyHandle
0x180008f34  mov     dword ptr [rsp+220h+var_1E0], r15d
0x180008f39  mov     dword ptr [rsp+220h+var_1D0], r15d
0x180008f3e  call    ?PrivateRegQueryValueExT@@YAJPEAUHKEY__@@PEBGPEAK2PEAE2H@Z; PrivateRegQueryValueExT(HKEY__ *,ushort const *,ulong *,ulong *,uchar *,ulong *,int)
0x180008f43  test    eax, eax
0x180008f45  jnz     short loc_180008F6A
0x180008f47  cmp     dword ptr [rsp+220h+var_1E0], r12d
0x180008f4c  jnz     short loc_180008F6A
0x180008f4e  cmp     dword ptr [rsp+220h+var_1D0], r13d
0x180008f53  jnz     short loc_180008F6A
0x180008f55  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180008f59  lock add cs:?NumberOfOpens@@3JA, esi; long NumberOfOpens
0x180008f60  mov     edi, 422h
0x180008f65  jmp     loc_1800092B3
0x180008f6a  cmp     cs:?pComputerName@@3PEAGEA, r15; ushort * pComputerName
0x180008f71  mov     edi, r15d
0x180008f74  jnz     loc_1800092AF
0x180008f7a  lea     rdx, ?ComputerNameLength@@3KA; nSize
0x180008f81  mov     cs:?ComputerNameLength@@3KA, r15d; ulong ComputerNameLength
0x180008f88  xor     ecx, ecx; lpBuffer
0x180008f8a  call    cs:__imp_GetComputerNameW
0x180008f90  mov     eax, cs:?ComputerNameLength@@3KA; ulong ComputerNameLength
0x180008f96  add     eax, r13d
0x180008f99  mov     ecx, eax
0x180008f9b  mov     cs:?ComputerNameLength@@3KA, eax; ulong ComputerNameLength
0x180008fa1  mov     eax, 2
0x180008fa6  mul     rcx
0x180008fa9  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180008fb0  cmovb   rax, rcx
0x180008fb4  mov     rcx, rax
0x180008fb7  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x180008fbc  mov     cs:?pComputerName@@3PEAGEA, rax; ushort * pComputerName
0x180008fc3  test    rax, rax
0x180008fc6  jz      short loc_180008FDC
0x180008fc8  lea     rdx, ?ComputerNameLength@@3KA; nSize
0x180008fcf  mov     rcx, rax; lpBuffer
0x180008fd2  call    cs:__imp_GetComputerNameW
0x180008fd8  test    eax, eax
0x180008fda  jnz     short loc_180008FE1
0x180008fdc  mov     eax, r15d
0x180008fdf  jmp     short loc_180009000
0x180008fe1  mov     rax, cs:?pComputerName@@3PEAGEA; ushort * pComputerName
0x180008fe8  mov     edx, cs:?ComputerNameLength@@3KA; ulong ComputerNameLength
0x180008fee  mov     [rax+rdx*2], r15w
0x180008ff3  mov     eax, cs:?ComputerNameLength@@3KA; ulong ComputerNameLength
0x180008ff9  lea     eax, ds:2[rax*2]
0x180009000  mov     cs:?ComputerNameLength@@3KA, eax; ulong ComputerNameLength
0x180009006  lea     r9, [rsp+220h+var_1E0]; unsigned int *
0x18000900b  lea     rax, [rsp+220h+var_1D8]
0x180009010  mov     dword ptr [rsp+220h+hTemplateFile], r13d; int
0x180009015  mov     qword ptr [rsp+220h+dwFlagsAndAttributes], rax; unsigned int
0x18000901a  lea     rdx, ?cszPerflibFlags@@3QBGB; "Configuration Flags"
0x180009021  lea     rax, ?lPerflibConfigFlags@@3JA; long lPerflibConfigFlags
0x180009028  mov     dword ptr [rsp+220h+var_1E0], r15d
0x18000902d  mov     rcx, rsi; KeyHandle
0x180009030  mov     qword ptr [rsp+220h+dwCreationDisposition], rax; unsigned __int8 *
0x180009035  mov     [rsp+220h+var_1D8], r12d
0x18000903a  call    ?PrivateRegQueryValueExT@@YAJPEAUHKEY__@@PEBGPEAK2PEAE2H@Z; PrivateRegQueryValueExT(HKEY__ *,ushort const *,ulong *,ulong *,uchar *,ulong *,int)
0x18000903f  test    eax, eax
0x180009041  jnz     short loc_180009052
0x180009043  cmp     dword ptr [rsp+220h+var_1E0], r12d
0x180009048  jnz     short loc_180009052
0x18000904a  mov     eax, cs:?lPerflibConfigFlags@@3JA; long lPerflibConfigFlags
0x180009050  jmp     short loc_18000905B
0x180009052  mov     eax, r12d
0x180009055  mov     cs:?lPerflibConfigFlags@@3JA, eax; long lPerflibConfigFlags
0x18000905b  cmp     cs:?hPerflibSectionFile@@3PEAXEA, r15; void * hPerflibSectionFile
0x180009062  jnz     loc_1800092AF
0x180009068  mov     ebx, 10h
0x18000906d  test    bl, al
0x18000906f  jz      loc_1800092AF
0x180009075  mov     qword ptr [rsp+220h+var_1D8], r15
0x18000907a  mov     [rsp+220h+var_1E0], r15
0x18000907f  call    cs:__imp_GetCurrentProcessId
0x180009085  mov     r9d, ebx
0x180009088  lea     r8d, [rbx+10h]
0x18000908c  mov     ecx, eax
0x18000908e  lea     rdx, [rbp+120h+var_90]
0x180009095  call    _o__ultow_s_0
0x18000909a  lea     rax, [rsp+220h+var_1D8]
0x18000909f  mov     edx, 104h; unsigned __int64
0x1800090a4  lea     rsi, ?szPerflibSectionName@@3PAGA; ushort near * szPerflibSectionName
0x1800090ab  mov     qword ptr [rsp+220h+dwCreationDisposition], rax; unsigned __int64 *
0x1800090b0  mov     rcx, rsi; unsigned __int16 *
0x1800090b3  lea     r9, [rsp+220h+var_1E0]; unsigned __int16 **
0x1800090b8  lea     r8, aTempPerflibPer; "%TEMP%\\Perflib_Perfdata_"
0x1800090bf  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x1800090c4  test    eax, eax
0x1800090c6  js      loc_180009174
0x1800090cc  mov     rdx, qword ptr [rsp+220h+var_1D8]; unsigned __int64
0x1800090d1  lea     rax, [rsp+220h+var_1D8]
0x1800090d6  mov     rcx, [rsp+220h+var_1E0]; unsigned __int16 *
0x1800090db  lea     r9, [rsp+220h+var_1E0]; unsigned __int16 **
0x1800090e0  lea     r8, [rbp+120h+var_90]; unsigned __int16 *
0x1800090e7  mov     qword ptr [rsp+220h+dwCreationDisposition], rax; unsigned __int64 *
0x1800090ec  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x1800090f1  test    eax, eax
0x1800090f3  js      short loc_180009174
0x1800090f5  mov     rdx, qword ptr [rsp+220h+var_1D8]; unsigned __int64
0x1800090fa  lea     rax, [rsp+220h+var_1D8]
0x1800090ff  mov     rcx, [rsp+220h+var_1E0]; unsigned __int16 *
0x180009104  lea     r9, [rsp+220h+var_1E0]; unsigned __int16 **
0x180009109  lea     r8, aDat; ".dat"
0x180009110  mov     qword ptr [rsp+220h+dwCreationDisposition], rax; unsigned __int64 *
0x180009115  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x18000911a  test    eax, eax
0x18000911c  js      short loc_180009174
0x18000911e  mov     r8d, 104h; nSize
0x180009124  lea     rdx, ?szPerflibSectionFile@@3PAGA; lpDst
0x18000912b  mov     rcx, rsi; lpSrc
0x18000912e  call    cs:__imp_ExpandEnvironmentStringsW
0x180009134  dec     eax
0x180009136  cmp     eax, 103h
0x18000913b  ja      short loc_180009174
0x18000913d  mov     [rsp+220h+hTemplateFile], r15; hTemplateFile
0x180009142  lea     r8d, [rbx-0Dh]; dwShareMode
0x180009146  mov     [rsp+220h+dwFlagsAndAttributes], 14000100h; dwFlagsAndAttributes
0x18000914e  lea     rcx, ?szPerflibSectionFile@@3PAGA; lpFileName
0x180009155  xor     r9d, r9d; lpSecurityAttributes
0x180009158  mov     [rsp+220h+dwCreationDisposition], r12d; dwCreationDisposition
0x18000915d  mov     edx, 0C0000000h; dwDesiredAccess
0x180009162  call    cs:__imp_CreateFileW
0x180009168  mov     rcx, rax
0x18000916b  mov     cs:?hPerflibSectionFile@@3PEAXEA, rax; void * hPerflibSectionFile
  ... truncated ...
```
