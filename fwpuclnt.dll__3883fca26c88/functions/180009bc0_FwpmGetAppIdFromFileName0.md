# FwpmGetAppIdFromFileName0

- ea: `0x180009bc0`
- end: `0x18000a485`
- name: `FwpmGetAppIdFromFileName0`
- size: `2245`
- prototype: `DWORD __stdcall(PCWSTR fileName, FWP_BYTE_BLOB **appId)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callees

- `0x1800034e0`
- `0x180004e28`
- `0x180005fc8`
- `0x180006230`
- `0x180006e40`
- `0x180007e38`
- `0x180009bc0`
- `0x18000dd70`
- `0x18000e898`
- `0x180011500`
- `0x180012bd0`
- `0x18003a298`
- `0x18004703c`
- `0x18004a0d1`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180009c4a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180009c4a`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x18000a0e8`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x18000a0e8`
- `ntdll!NtQueryObject` at `0x180009ed6`
- `ntdll!NtQueryObject` at `0x180009f3b`
- `ntdll!NtQueryObject` at `0x180009ed6`
- `ntdll!NtQueryObject` at `0x180009f3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009e85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009e85`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a0f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a0f9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009fd4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a039`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a171`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a1d6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a39d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a402`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009fd4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a039`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a171`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a1d6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a39d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a402`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180009dc1`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000a018`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000a1b5`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000a3e1`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180009dc1`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000a018`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000a1b5`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000a3e1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009c89`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009d6b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009c89`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009d6b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180009e71`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180009e71`

## string_xrefs

- `0x180009de8`: `WfpBufferCopy`
- `0x180009df7`: `WfpStringCopy`
- `0x180009e94`: `CreateFileW`
- `0x18000a1e7`: `BfeGetNtPathName`

## pseudocode

```c
DWORD __stdcall FwpmGetAppIdFromFileName0(PCWSTR fileName, FWP_BYTE_BLOB **appId)
{
  _DWORD *v3; // rdi
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // rbx
  __int64 v7; // r8
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 v12; // rdx
  void *v13; // rcx
  __int64 v14; // r8
  _DWORD *v15; // rax
  __int64 v16; // rax
  HANDLE FileW; // r15
  DWORD LastError; // eax
  __int64 v19; // rcx
  NTSTATUS Object; // eax
  __int64 v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // r8
  int v25; // eax
  BOOL v26; // eax
  char v27; // dl
  int v28; // r8d
  int v29; // r9d
  int v30; // ecx
  int v31; // eax
  BOOL v32; // eax
  __int64 v33; // rax
  __int64 v35; // rcx
  int v36; // eax
  BOOL v37; // eax
  DWORD v39; // edx
  wchar_t dwCreationDisposition; // [rsp+28h] [rbp-E0h]
  long double dwFlagsAndAttributes; // [rsp+30h] [rbp-D8h]
  _DWORD *v42; // [rsp+50h] [rbp-B8h] BYREF
  int v43; // [rsp+58h] [rbp-B0h] BYREF
  ULONG ObjectInformation; // [rsp+60h] [rbp-A8h] BYREF
  __int128 ObjectInformation_8; // [rsp+68h] [rbp-A0h] BYREF
  _QWORD v46[6]; // [rsp+78h] [rbp-90h] BYREF
  char v47[16]; // [rsp+A8h] [rbp-60h] BYREF
  const char *v48; // [rsp+B8h] [rbp-50h]
  __int64 v49; // [rsp+C0h] [rbp-48h]
  void **v50; // [rsp+C8h] [rbp-40h]
  __int64 v51; // [rsp+D0h] [rbp-38h]

  v3 = 0;
  v42 = 0;
  if ( !fileName || !appId )
  {
    v6 = WfpReportSysErrorAsWinError(fileName, "FwpmGetAppIdFromFileName0", 2150760476LL);
    goto LABEL_69;
  }
  *appId = 0;
  if ( !(unsigned int)_o__wcsicmp(fileName, L"System") )
  {
    if ( (Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 0x10) != 0 )
      IsEnabledDeviceUsageNoInline = Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 1;
    else
      IsEnabledDeviceUsageNoInline = Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline(
                                       v9,
                                       v8,
                                       v10);
    if ( IsEnabledDeviceUsageNoInline )
    {
      v3 = HeapAlloc(gWfpHeap, 0, 0xEu);
      if ( v3 )
      {
        v6 = 0;
        if ( gWfpTrackHeapAllocs )
          _InterlockedIncrement(&gWfpNumHeapAllocs);
      }
      else
      {
        v6 = WfpReportSysErrorAsNtStatus(v13, "HeapAlloc", 3221225495LL);
        if ( v6 )
        {
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v14, 0, (__int64)"WfpMemAlloc25B", v6);
          }
          if ( gWfpLogUserModeErrors && (byte_18007C665 & 1) != 0 )
          {
            v43 = v6;
            v46[4] = &v43;
            v46[2] = "WfpMemAlloc25B";
            v46[3] = 15;
            v46[5] = 4;
            McGenEventWrite_EtwEventWriteTransfer((_DWORD)v13, (unsigned int)WFP_USERMODE_ERROR, v14, 3, (__int64)v46);
          }
        }
      }
    }
    else
    {
      v15 = HeapAlloc(gWfpHeap, 0, 0xEu);
      v3 = v15;
      if ( v15 )
      {
        v6 = 0;
        if ( gWfpTrackHeapBytes )
          _InterlockedAdd(&gWfpHeapBytesAllocated, HeapSize(gWfpHeap, 0, v15));
      }
      else
      {
        v16 = WfpReportSysErrorAsNtStatus(v13, "HeapAlloc", 3221225495LL);
        v6 = v16;
        if ( v16 )
          WfpReportError(v16, "WfpMemAlloc");
      }
    }
    if ( v6 )
    {
      WfpReportError(v6, "WfpPoolAllocNonPaged");
      WfpReportError(v6, "WfpBufferCopy");
      WfpReportError(v6, "WfpStringCopy");
    }
    else
    {
      *(_QWORD *)v3 = *(_QWORD *)L"System";
      v3[2] = *(_DWORD *)L"em";
      *((_WORD *)v3 + 6) = aSystem[6];
    }
    goto LABEL_56;
  }
  v6 = BfeExpandEnvironmentStrings(fileName);
  if ( !v6 )
  {
    FileW = CreateFileW(0, 0x80u, 0, 0, 3u, 0x80u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v6 = WfpReportSysErrorAsWinError(v19, "CreateFileW", LastError);
      goto LABEL_56;
    }
    ObjectInformation = 0;
    ObjectInformation_8 = 0;
    Object = NtQueryObject(FileW, ObjectNameInformation, &ObjectInformation_8, 0x10u, &ObjectInformation);
    v21 = Object + 0x80000000;
    if ( (int)v21 < 0 || Object == -2147483643 )
    {
      v6 = WfpMemAlloc(ObjectInformation, 0);
      if ( v6 )
        goto LABEL_37;
      Object = NtQueryObject(FileW, ObjectNameInformation, 0, ObjectInformation, 0);
      if ( Object >= 0 )
      {
        v3 = v42;
        v6 = WfpStringCopy(MEMORY[8]);
        goto LABEL_37;
      }
    }
    v6 = WfpReportSysErrorAsNtStatus(v21, "NtQueryObject", (unsigned int)Object);
LABEL_37:
    if ( (Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 0x10) != 0 )
      v25 = Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 1;
    else
      v25 = Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline(v23, v22, v24);
    if ( v25 )
    {
      v26 = HeapFree(gWfpHeap, 0, 0);
      if ( !gHeapFreeFailedFired && !v26 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
        gHeapFreeFailedFired = 1;
      }
    }
    else
    {
      HeapFree(gWfpHeap, 0, 0);
    }
    if ( v6 )
    {
      v30 = (int)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v28, 0, (__int64)"BfeQueryObjectName");
      }
      if ( gWfpLogUserModeErrors && (byte_18007C665 & 1) != 0 )
      {
        v48 = "BfeQueryObjectName";
        v50 = (void **)&v42;
        LODWORD(v42) = v6;
        v49 = 19;
        v51 = 4;
        McGenEventWrite_EtwEventWriteTransfer(v30, (unsigned int)WFP_USERMODE_ERROR, v28, 3, (__int64)v47);
      }
    }
    else
    {
      o((wchar_t)v3, v27, v28, v29, dwCreationDisposition, dwFlagsAndAttributes);
    }
    CloseHandle(FileW);
  }
LABEL_56:
  if ( (Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 0x10) != 0 )
    v31 = Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 1;
  else
    v31 = Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline(v13, v12, v14);
  if ( v31 )
  {
    v32 = HeapFree(gWfpHeap, 0, 0);
    if ( !gHeapFreeFailedFired && !v32 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      gHeapFreeFailedFired = 1;
    }
  }
  else
  {
    HeapFree(gWfpHeap, 0, 0);
  }
  if ( v6 )
  {
    WfpReportError(v6, "BfeGetNtPathName");
  }
  else
  {
    v33 = -1;
    while ( *((_WORD *)v3 + ++v33) != 0 )
      ;
    WfpPoolAllocNonPaged((unsigned int)(2 * v33 + 2) + 16LL);
    v6 = WfpReportSysErrorAsNtStatus(v35, "MIDL_user_allocate", 3221225495LL);
  }
LABEL_69:
  if ( (Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 0x10) != 0 )
    v36 = Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 1;
  else
    v36 = Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline(v5, v4, v7);
  if ( v36 )
  {
    if ( gWfpTrackHeapAllocs && v3 && _InterlockedDecrement(&gWfpNumHeapAllocs) < 0 )
    {
      if ( !gMisalignedHeapTelemFired )
      {
        if ( gWfpNumHeapAllocs <= 0 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        gMisalignedHeapTelemFired = 1;
      }
      _InterlockedIncrement(&gWfpNumHeapAllocs);
    }
    else
    {
      v37 = HeapFree(gWfpHeap, 0, v3);
      if ( !gHeapFreeFailedFired && !v37 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
        gHeapFreeFailedFired = 1;
      }
    }
  }
  else
  {
    if ( gWfpTrackHeapBytes && v3 )
      _InterlockedAdd(&gWfpHeapBytesAllocated, -(int)HeapSize(gWfpHeap, 0, v3));
    HeapFree(gWfpHeap, 0, v3);
  }
  if ( !v6 )
    return 0;
  v39 = (unsigned __int16)v6;
  if ( (v6 & 0x1FFF0000) != 0x70000 )
    v39 = v6;
  switch ( v39 )
  {
    case 6u:
    case 0x6BFu:
      return -2144206832;
    case 0x6C5u:
      return -2144206819;
    case 0x6EFu:
    case 0x6F4u:
      return -2144206820;
  }
  return v39;
}

```

## disassembly

```asm
0x180009bc0  mov     r11, rsp
0x180009bc3  push    rbp
0x180009bc4  push    rbx
0x180009bc5  lea     rbp, [r11-48h]
0x180009bc9  sub     rsp, 138h
0x180009bd0  mov     rax, cs:__security_cookie
0x180009bd7  xor     rax, rsp
0x180009bda  mov     [rbp+40h+var_40], rax
0x180009bde  mov     [r11+18h], rsi
0x180009be2  mov     rbx, rcx
0x180009be5  mov     [r11-18h], rdi
0x180009be9  xor     esi, esi
0x180009beb  mov     [r11-20h], r12
0x180009bef  mov     edi, esi
0x180009bf1  mov     [r11-28h], r13
0x180009bf5  mov     r13, rdx
0x180009bf8  mov     [rsp+140h+var_F8], rsi
0x180009bfd  mov     r12, 0FFFFFFFFFFFFFFFFh
0x180009c04  test    rcx, rcx
0x180009c07  jnz     short loc_180009C23
0x180009c09  mov     r8d, 8032001Ch
0x180009c0f  lea     rdx, aFwpmgetappidfr_0; "FwpmGetAppIdFromFileName0"
0x180009c16  call    WfpReportSysErrorAsWinError
0x180009c1b  mov     rbx, rax
0x180009c1e  jmp     loc_18000A322
0x180009c23  test    r13, r13
0x180009c26  jz      short loc_180009C09
0x180009c28  mov     [rdx], rsi
0x180009c2b  lea     rdx, aSystem; "System"
0x180009c32  mov     [rsp+140h+var_28], r14
0x180009c3a  mov     r14, rsi
0x180009c3d  mov     [rsp+140h+var_30], r15
0x180009c45  mov     [rsp+140h+lpFileName], rsi
0x180009c4a  call    cs:__imp__o__wcsicmp
0x180009c51  nop     dword ptr [rax+rax+00h]
0x180009c56  test    eax, eax
0x180009c58  jnz     loc_180009E30
0x180009c5e  mov     eax, cs:Feature_BFE_MemAlloc_BugFixes_25B__private_featureState
0x180009c64  test    al, 10h
0x180009c66  jz      short loc_180009C6D
0x180009c68  and     eax, 1
0x180009c6b  jmp     short loc_180009C72
0x180009c6d  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline
0x180009c72  mov     rcx, cs:gWfpHeap; hHeap
0x180009c79  xor     edx, edx; dwFlags
0x180009c7b  mov     r8d, 0Eh; dwBytes
0x180009c81  test    eax, eax
0x180009c83  jz      loc_180009D6B
0x180009c89  call    cs:__imp_HeapAlloc
0x180009c90  nop     dword ptr [rax+rax+00h]
0x180009c95  mov     rdi, rax
0x180009c98  test    rax, rax
0x180009c9b  jnz     loc_180009D57
0x180009ca1  mov     r8d, 0C0000017h
0x180009ca7  lea     rdx, aHeapalloc; "HeapAlloc"
0x180009cae  call    WfpReportSysErrorAsNtStatus
0x180009cb3  mov     rbx, rax
0x180009cb6  test    rax, rax
0x180009cb9  jz      loc_180009DD4
0x180009cbf  mov     rcx, cs:WPP_GLOBAL_Control
0x180009cc6  lea     rax, WPP_GLOBAL_Control
0x180009ccd  lea     r15, aWfpmemalloc25b; "WfpMemAlloc25B"
0x180009cd4  cmp     rcx, rax
0x180009cd7  jz      short loc_180009CFF
0x180009cd9  cmp     byte ptr [rcx+19h], 2
0x180009cdd  jb      short loc_180009CFF
0x180009cdf  test    byte ptr [rcx+1Ch], 1
0x180009ce3  jz      short loc_180009CFF
0x180009ce5  mov     rcx, [rcx+10h]
0x180009ce9  mov     edx, 1Ah
0x180009cee  mov     [rsp+140h+dwFlagsAndAttributes], ebx
0x180009cf2  xor     r9d, r9d
0x180009cf5  mov     qword ptr [rsp+140h+dwCreationDisposition], r15
0x180009cfa  call    WPP_SF_Ssd
0x180009cff  cmp     cs:gWfpLogUserModeErrors, esi
0x180009d05  jz      loc_180009DD4
0x180009d0b  test    cs:byte_18007C665, 1
0x180009d12  jz      loc_180009DD4
0x180009d18  lea     rax, [rsp+140h+var_F0]
0x180009d1d  mov     [rsp+140h+var_F0], ebx
0x180009d21  mov     [rbp+40h+var_B0], rax
0x180009d25  lea     rdx, WFP_USERMODE_ERROR
0x180009d2c  lea     rax, [rsp+70h]
0x180009d31  mov     [rbp+40h+var_C0], r15
0x180009d35  mov     r9d, 3
0x180009d3b  mov     qword ptr [rsp+140h+dwCreationDisposition], rax
0x180009d40  mov     [rbp+40h+var_B8], 0Fh
0x180009d48  mov     [rbp+40h+var_A8], 4
0x180009d50  call    McGenEventWrite_EtwEventWriteTransfer
0x180009d55  jmp     short loc_180009DD4
0x180009d57  cmp     cs:gWfpTrackHeapAllocs, esi
0x180009d5d  mov     rbx, rsi
0x180009d60  jz      short loc_180009DD4
0x180009d62  lock inc cs:gWfpNumHeapAllocs
0x180009d69  jmp     short loc_180009DD4
0x180009d6b  call    cs:__imp_HeapAlloc
0x180009d72  nop     dword ptr [rax+rax+00h]
0x180009d77  mov     rdi, rax
0x180009d7a  test    rax, rax
0x180009d7d  jnz     short loc_180009DAA
0x180009d7f  mov     r8d, 0C0000017h
0x180009d85  lea     rdx, aHeapalloc; "HeapAlloc"
0x180009d8c  call    WfpReportSysErrorAsNtStatus
0x180009d91  mov     rbx, rax
0x180009d94  test    rax, rax
0x180009d97  jz      short loc_180009DD4
0x180009d99  lea     rdx, aWfpmemalloc; "WfpMemAlloc"
0x180009da0  mov     rcx, rax
0x180009da3  call    WfpReportError
0x180009da8  jmp     short loc_180009DD4
0x180009daa  cmp     cs:gWfpTrackHeapBytes, esi
0x180009db0  mov     rbx, rsi
0x180009db3  jz      short loc_180009DD4
0x180009db5  mov     rcx, cs:gWfpHeap; hHeap
0x180009dbc  mov     r8, rax; lpMem
0x180009dbf  xor     edx, edx; dwFlags
0x180009dc1  call    cs:__imp_HeapSize
0x180009dc8  nop     dword ptr [rax+rax+00h]
0x180009dcd  lock add cs:gWfpHeapBytesAllocated, eax
0x180009dd4  test    rbx, rbx
0x180009dd7  jz      short loc_180009E0B
0x180009dd9  lea     rdx, aWfppoolallocno; "WfpPoolAllocNonPaged"
0x180009de0  mov     rcx, rbx
0x180009de3  call    WfpReportError
0x180009de8  lea     rdx, aWfpbuffercopy; "WfpBufferCopy"
0x180009def  mov     rcx, rbx
0x180009df2  call    WfpReportError
0x180009df7  lea     rdx, aWfpstringcopy; "WfpStringCopy"
0x180009dfe  mov     rcx, rbx
0x180009e01  call    WfpReportError
0x180009e06  jmp     loc_18000A105
0x180009e0b  movsd   xmm0, qword ptr cs:aSystem; "System"
0x180009e13  movsd   qword ptr [rdi], xmm0
0x180009e17  mov     eax, dword ptr cs:aSystem+8; "em"
0x180009e1d  mov     [rdi+8], eax
0x180009e20  movzx   eax, word ptr cs:aSystem+0Ch; ""
0x180009e27  mov     [rdi+0Ch], ax
0x180009e2b  jmp     loc_18000A105
0x180009e30  lea     rdx, [rsp+140h+lpFileName]
0x180009e35  mov     rcx, rbx; lpSrc
0x180009e38  call    BfeExpandEnvironmentStrings
0x180009e3d  mov     r14, [rsp+140h+lpFileName]
0x180009e42  mov     rbx, rax
0x180009e45  test    rax, rax
0x180009e48  jnz     loc_18000A105
0x180009e4e  mov     [rsp+30h], rsi; hTemplateFile
0x180009e53  xor     r9d, r9d; lpSecurityAttributes
0x180009e56  mov     [rsp+140h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180009e5e  xor     r8d, r8d; dwShareMode
0x180009e61  mov     edx, 80h; dwDesiredAccess
0x180009e66  mov     dword ptr [rsp+140h+dwCreationDisposition], 3; dwCreationDisposition
0x180009e6e  mov     rcx, r14; lpFileName
0x180009e71  call    cs:__imp_CreateFileW
0x180009e78  nop     dword ptr [rax+rax+00h]
0x180009e7d  mov     r15, rax
0x180009e80  cmp     rax, r12
0x180009e83  jnz     short loc_180009EA8
0x180009e85  call    cs:__imp_GetLastError
0x180009e8c  nop     dword ptr [rax+rax+00h]
0x180009e91  mov     r8d, eax
0x180009e94  lea     rdx, aCreatefilew; "CreateFileW"
0x180009e9b  call    WfpReportSysErrorAsWinError
0x180009ea0  mov     rbx, rax
0x180009ea3  jmp     loc_18000A105
0x180009ea8  xorps   xmm0, xmm0
0x180009eab  mov     [rsp+140h+lpFileName], rsi
0x180009eb0  lea     rax, [rsp+140h+ObjectInformation]
0x180009eb5  mov     dword ptr [rsp+140h+ObjectInformation], esi
0x180009eb9  mov     r9d, 10h; ObjectInformationLength
0x180009ebf  mov     qword ptr [rsp+140h+dwCreationDisposition], rax; ReturnLength
0x180009ec4  lea     r8, [rsp+140h+ObjectInformation+8]; ObjectInformation
0x180009ec9  mov     edx, 1; ObjectInformationClass
0x180009ece  mov     rcx, r15; Handle
0x180009ed1  movups  [rsp+140h+ObjectInformation+8], xmm0
0x180009ed6  call    cs:__imp_NtQueryObject
0x180009edd  nop     dword ptr [rax+rax+00h]
0x180009ee2  mov     edx, 80000000h
0x180009ee7  lea     ecx, [rax+rdx]
0x180009eea  test    edx, ecx
0x180009eec  jnz     short loc_180009F09
0x180009eee  cmp     eax, 80000005h
0x180009ef3  jz      short loc_180009F09
0x180009ef5  mov     r8d, eax
0x180009ef8  lea     rdx, aNtqueryobject; "NtQueryObject"
0x180009eff  call    WfpReportSysErrorAsNtStatus
0x180009f04  mov     rbx, rax
0x180009f07  jmp     short loc_180009F68
0x180009f09  mov     ecx, dword ptr [rsp+140h+ObjectInformation]; dwBytes
0x180009f0d  lea     r8, [rsp+140h+lpFileName]
0x180009f12  xor     edx, edx; dwFlags
0x180009f14  call    WfpMemAlloc
0x180009f19  mov     rbx, rax
0x180009f1c  test    rax, rax
0x180009f1f  jnz     short loc_180009F63
0x180009f21  mov     r9d, dword ptr [rsp+140h+ObjectInformation]; ObjectInformationLength
0x180009f26  mov     edx, 1; ObjectInformationClass
0x180009f2b  mov     qword ptr [rsp+140h+dwCreationDisposition], rsi; ReturnLength
0x180009f30  mov     rcx, r15; Handle
0x180009f33  mov     rsi, [rsp+140h+lpFileName]
0x180009f38  mov     r8, rsi; ObjectInformation
0x180009f3b  call    cs:__imp_NtQueryObject
0x180009f42  nop     dword ptr [rax+rax+00h]
0x180009f47  test    eax, eax
0x180009f49  js      short loc_180009EF5
0x180009f4b  mov     rcx, [rsi+8]; Src
0x180009f4f  lea     r8, [rsp+140h+var_F8]
0x180009f54  call    WfpStringCopy
0x180009f59  mov     rdi, [rsp+140h+var_F8]
0x180009f5e  mov     rbx, rax
0x180009f61  jmp     short loc_180009F68
0x180009f63  mov     rsi, [rsp+140h+lpFileName]
0x180009f68  mov     eax, cs:Feature_BFE_MemAlloc_BugFixes_25B__private_featureState
0x180009f6e  test    al, 10h
0x180009f70  jz      short loc_180009F77
0x180009f72  and     eax, 1
0x180009f75  jmp     short loc_180009F7C
0x180009f77  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline
0x180009f7c  test    eax, eax
0x180009f7e  jz      short loc_180009FFE
0x180009f80  cmp     cs:gWfpTrackHeapAllocs, 0
0x180009f87  jz      short loc_180009FC8
0x180009f89  test    rsi, rsi
0x180009f8c  jz      short loc_180009FC8
0x180009f8e  mov     eax, r12d
0x180009f91  lock xadd cs:gWfpNumHeapAllocs, eax
0x180009f99  cmp     eax, 1
0x180009f9c  jns     short loc_180009FC8
0x180009f9e  cmp     cs:gMisalignedHeapTelemFired, 0
0x180009fa5  jnz     short loc_180009FBF
0x180009fa7  cmp     cs:gWfpNumHeapAllocs, 0
0x180009fae  jg      short loc_180009FB5
0x180009fb0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180009fb5  mov     cs:gMisalignedHeapTelemFired, 1
0x180009fbf  lock inc cs:gWfpNumHeapAllocs
0x180009fc6  jmp     short loc_18000A045
0x180009fc8  mov     rcx, cs:gWfpHeap; hHeap
0x180009fcf  mov     r8, rsi; lpMem
0x180009fd2  xor     edx, edx; dwFlags
0x180009fd4  call    cs:__imp_HeapFree
0x180009fdb  nop     dword ptr [rax+rax+00h]
0x180009fe0  cmp     cs:gHeapFreeFailedFired, 0
0x180009fe7  jnz     short loc_18000A045
0x180009fe9  test    eax, eax
0x180009feb  jnz     short loc_18000A045
0x180009fed  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180009ff2  mov     cs:gHeapFreeFailedFired, 1
0x180009ffc  jmp     short loc_18000A045
0x180009ffe  cmp     cs:gWfpTrackHeapBytes, 0
0x18000a005  jz      short loc_18000A02D
0x18000a007  test    rsi, rsi
0x18000a00a  jz      short loc_18000A02D
0x18000a00c  mov     rcx, cs:gWfpHeap; hHeap
0x18000a013  mov     r8, rsi; lpMem
0x18000a016  xor     edx, edx; dwFlags
0x18000a018  call    cs:__imp_HeapSize
0x18000a01f  nop     dword ptr [rax+rax+00h]
0x18000a024  neg     eax
0x18000a026  lock add cs:gWfpHeapBytesAllocated, eax
0x18000a02d  mov     rcx, cs:gWfpHeap; hHeap
0x18000a034  mov     r8, rsi; lpMem
0x18000a037  xor     edx, edx; dwFlags
0x18000a039  call    cs:__imp_HeapFree
0x18000a040  nop     dword ptr [rax+rax+00h]
0x18000a045  test    rbx, rbx
0x18000a048  jz      loc_18000A0E5
0x18000a04e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a055  lea     rax, WPP_GLOBAL_Control
0x18000a05c  lea     rsi, aBfequeryobject; "BfeQueryObjectName"
0x18000a063  cmp     rcx, rax
0x18000a066  jz      short loc_18000A08E
0x18000a068  cmp     byte ptr [rcx+19h], 2
0x18000a06c  jb      short loc_18000A08E
0x18000a06e  test    byte ptr [rcx+1Ch], 1
0x18000a072  jz      short loc_18000A08E
0x18000a074  mov     rcx, [rcx+10h]
0x18000a078  mov     edx, 1Ah
0x18000a07d  mov     [rsp+140h+dwFlagsAndAttributes], ebx
0x18000a081  xor     r9d, r9d
0x18000a084  mov     qword ptr [rsp+140h+dwCreationDisposition], rsi
0x18000a089  call    WPP_SF_Ssd
0x18000a08e  cmp     cs:gWfpLogUserModeErrors, 0
0x18000a095  jz      short loc_18000A0E0
0x18000a097  test    cs:byte_18007C665, 1
0x18000a09e  jz      short loc_18000A0E0
0x18000a0a0  lea     rax, [rsp+140h+var_F8]
0x18000a0a5  mov     [rbp+40h+var_90], rsi
0x18000a0a9  mov     [rbp+40h+var_80], rax
0x18000a0ad  lea     rdx, WFP_USERMODE_ERROR
0x18000a0b4  lea     rax, [rbp+40h+var_A0]
0x18000a0b8  mov     dword ptr [rsp+140h+var_F8], ebx
0x18000a0bc  xor     esi, esi
0x18000a0be  mov     qword ptr [rsp+140h+dwCreationDisposition], rax
0x18000a0c3  mov     r9d, 3
0x18000a0c9  mov     [rbp+40h+var_88], 13h
0x18000a0d1  mov     [rbp+40h+var_78], 4
0x18000a0d9  call    McGenEventWrite_EtwEventWriteTransfer
0x18000a0de  jmp     short loc_18000A0F6
0x18000a0e0  test    rbx, rbx
0x18000a0e3  jnz     short loc_18000A0F4
0x18000a0e5  mov     rcx, rdi
  ... truncated ...
```
