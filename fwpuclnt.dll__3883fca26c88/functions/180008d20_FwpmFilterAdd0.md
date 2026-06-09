# FwpmFilterAdd0

- ea: `0x180008d20`
- end: `0x180009221`
- name: `FwpmFilterAdd0`
- size: `1281`
- prototype: `DWORD __stdcall(HANDLE engineHandle, const FWPM_FILTER0 *filter, PSECURITY_DESCRIPTOR sd, UINT64 *id)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800034e0`
- `0x18000438c`
- `0x180007e38`
- `0x180008d20`
- `0x18000dd70`
- `0x18000e898`
- `0x180011500`
- `0x180012bd0`
- `0x18003a298`
- `0x18004703c`
- `0x18004b010`

## import_xrefs

- `ntdll!RtlLengthSecurityDescriptor` at `0x180008db1`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180008db1`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x180008fa3`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x180008fa3`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x180008dcb`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x180008dcb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009140`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800091a5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009140`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800091a5`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180008f70`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180009184`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180008f70`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180009184`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008e2e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008f17`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008e2e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008f17`
- `RPCRT4!NdrClientCall3` at `0x18000903c`
- `RPCRT4!NdrClientCall3` at `0x18000903c`

## string_xrefs

- `0x180008fd5`: `BfeSecurityDescriptorEncode`
- `0x180008dde`: `RtlGetControlSecurityDescriptor`

## pseudocode

```c
DWORD __stdcall FwpmFilterAdd0(HANDLE engineHandle, const FWPM_FILTER0 *filter, PSECURITY_DESCRIPTOR sd, UINT64 *id)
{
  void *v8; // rsi
  __int64 v9; // rbx
  NTSTATUS ControlSecurityDescriptor; // eax
  __int64 v11; // rcx
  __int64 v12; // rax
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 v14; // rcx
  void *v15; // rdi
  int v16; // ecx
  void *v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rax
  NTSTATUS v20; // eax
  __int64 v21; // rcx
  __int64 v22; // rdx
  __int64 *v23; // rcx
  unsigned int Pointer; // eax
  CLIENT_CALL_RETURN v25; // rcx
  __int64 *v26; // r9
  unsigned int v27; // eax
  __int64 v28; // rcx
  int v29; // eax
  BOOL v30; // eax
  DWORD v32; // edx
  int v33; // [rsp+48h] [rbp-59h] BYREF
  LPVOID v34; // [rsp+50h] [rbp-51h] BYREF
  ULONG dwBytes; // [rsp+58h] [rbp-49h] BYREF
  __int16 dwBytes_4; // [rsp+5Ch] [rbp-45h] BYREF
  __int64 v37; // [rsp+60h] [rbp-41h] BYREF
  PSECURITY_DESCRIPTOR v38; // [rsp+68h] [rbp-39h]
  ULONG Revision; // [rsp+70h] [rbp-31h] BYREF
  UINT64 v40; // [rsp+78h] [rbp-29h] BYREF
  _BYTE v41[16]; // [rsp+80h] [rbp-21h] BYREF
  const char *v42; // [rsp+90h] [rbp-11h]
  __int64 v43; // [rsp+98h] [rbp-9h]
  int *v44; // [rsp+A0h] [rbp-1h]
  __int64 v45; // [rsp+A8h] [rbp+7h]

  LODWORD(v38) = 0;
  v37 = 0;
  v8 = 0;
  v40 = 0;
  if ( !engineHandle )
  {
    v9 = WfpReportSysErrorAsWinError(0, "FwpmFilterAdd0", 2150760476LL);
    goto LABEL_47;
  }
  dwBytes = 0;
  v9 = 0;
  Revision = 0;
  dwBytes_4 = 0;
  v34 = 0;
  v38 = 0;
  if ( !sd )
    goto LABEL_36;
  dwBytes = RtlLengthSecurityDescriptor(sd);
  ControlSecurityDescriptor = RtlGetControlSecurityDescriptor(sd, (PSECURITY_DESCRIPTOR_CONTROL)&dwBytes_4, &Revision);
  if ( ControlSecurityDescriptor < 0 )
  {
    v12 = WfpReportSysErrorAsNtStatus(v11, "RtlGetControlSecurityDescriptor", (unsigned int)ControlSecurityDescriptor);
    goto LABEL_32;
  }
  if ( dwBytes_4 < 0 )
  {
    v38 = sd;
LABEL_35:
    LODWORD(v37) = dwBytes;
    goto LABEL_36;
  }
  if ( (Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 0x10) != 0 )
    IsEnabledDeviceUsageNoInline = Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 1;
  else
    IsEnabledDeviceUsageNoInline = Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline();
  if ( IsEnabledDeviceUsageNoInline )
  {
    v34 = HeapAlloc(gWfpHeap, 0, dwBytes);
    v15 = v34;
    if ( v34 )
    {
      v9 = 0;
      if ( gWfpTrackHeapAllocs )
        _InterlockedIncrement(&gWfpNumHeapAllocs);
    }
    else
    {
      v9 = WfpReportSysErrorAsNtStatus(v14, "HeapAlloc", 3221225495LL);
      if ( v9 )
      {
        v16 = (int)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_Ssd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            26,
            (unsigned int)"WfpMemAlloc25B",
            0,
            (__int64)"WfpMemAlloc25B",
            v9);
        }
        if ( gWfpLogUserModeErrors && (byte_18007C665 & 1) != 0 )
        {
          v33 = v9;
          v44 = &v33;
          v42 = "WfpMemAlloc25B";
          v43 = 15;
          v45 = 4;
          McGenEventWrite_EtwEventWriteTransfer(
            v16,
            (unsigned int)WFP_USERMODE_ERROR,
            (unsigned int)"WfpMemAlloc25B",
            3,
            (__int64)v41);
        }
      }
    }
  }
  else
  {
    v17 = HeapAlloc(gWfpHeap, 0, dwBytes);
    v34 = v17;
    v15 = v17;
    if ( v17 )
    {
      v9 = 0;
      if ( gWfpTrackHeapBytes )
        _InterlockedAdd(&gWfpHeapBytesAllocated, HeapSize(gWfpHeap, 0, v17));
    }
    else
    {
      v19 = WfpReportSysErrorAsNtStatus(v18, "HeapAlloc", 3221225495LL);
      v9 = v19;
      if ( v19 )
        WfpReportError(v19, "WfpMemAlloc");
    }
  }
  if ( v9 )
  {
    WfpReportError(v9, "WfpPoolAllocNonPaged");
LABEL_33:
    WfpMemFree(&v34);
    WfpReportError(v9, "BfeSecurityDescriptorEncode");
    goto LABEL_47;
  }
  v20 = RtlAbsoluteToSelfRelativeSD(sd, v15, &dwBytes);
  if ( v20 >= 0 )
  {
    v38 = v15;
    v8 = v15;
    goto LABEL_35;
  }
  v12 = WfpReportSysErrorAsNtStatus(v21, "RtlAbsoluteToSelfRelativeSD", (unsigned int)v20);
LABEL_32:
  v9 = v12;
  if ( v12 )
    goto LABEL_33;
LABEL_36:
  v22 = *((_QWORD *)engineHandle + 14);
  if ( v22 )
  {
    v26 = &v37;
    if ( !sd )
      v26 = 0;
    v27 = (*(__int64 (__fastcall **)(_QWORD, __int64, const FWPM_FILTER0 *, __int64 *, UINT64 *))(g_pBfeDirectDispatchTable
                                                                                                + 16))(
            0,
            v22,
            filter,
            v26,
            &v40);
    if ( v27 )
    {
      v9 = WfpReportSysErrorAsWinError(v28, "BfeRpcFilterAdd", v27);
      goto LABEL_47;
    }
  }
  else
  {
    v23 = &v37;
    if ( !sd )
      v23 = 0;
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                              0x46u,
                              0,
                              *(_QWORD *)engineHandle,
                              *((_QWORD *)engineHandle + 1),
                              filter,
                              v23,
                              &v40).Pointer;
    if ( Pointer )
    {
      v9 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))WfpReportSysErrorAsWinError)(
             (CLIENT_CALL_RETURN)v25.Simple,
             "FwppProxyFilterAdd",
             Pointer);
      goto LABEL_47;
    }
  }
  if ( id )
    *id = v40;
LABEL_47:
  if ( (Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 0x10) != 0 )
    v29 = Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 1;
  else
    v29 = Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline();
  if ( v29 )
  {
    if ( gWfpTrackHeapAllocs && v8 && _InterlockedDecrement(&gWfpNumHeapAllocs) < 0 )
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
      v30 = HeapFree(gWfpHeap, 0, v8);
      if ( !gHeapFreeFailedFired && !v30 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
        gHeapFreeFailedFired = 1;
      }
    }
  }
  else
  {
    if ( gWfpTrackHeapBytes && v8 )
      _InterlockedAdd(&gWfpHeapBytesAllocated, -(int)HeapSize(gWfpHeap, 0, v8));
    HeapFree(gWfpHeap, 0, v8);
  }
  if ( !v9 )
    return 0;
  v32 = (unsigned __int16)v9;
  if ( (v9 & 0x1FFF0000) != 0x70000 )
    v32 = v9;
  switch ( v32 )
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
  return v32;
}

```

## disassembly

```asm
0x180008d20  mov     r11, rsp
0x180008d23  push    rbp
0x180008d24  push    rbx
0x180008d25  push    rdi
0x180008d26  lea     rbp, [r11-5Fh]
0x180008d2a  sub     rsp, 0E0h
0x180008d31  mov     rax, cs:__security_cookie
0x180008d38  xor     rax, rsp
0x180008d3b  mov     [rbp+57h+var_48], rax
0x180008d3f  mov     [r11-20h], rsi
0x180008d43  xor     eax, eax
0x180008d45  mov     [r11-28h], r12
0x180008d49  xor     edi, edi
0x180008d4b  mov     [r11-30h], r13
0x180008d4f  mov     r12, r9
0x180008d52  mov     [r11-38h], r14
0x180008d56  mov     r14, r8
0x180008d59  mov     [r11-40h], r15
0x180008d5d  mov     r15, rcx
0x180008d60  mov     qword ptr [rbp+57h+var_94], rax
0x180008d64  mov     r13, rdx
0x180008d67  mov     [rbp-41h], rax
0x180008d6b  mov     esi, edi
0x180008d6d  mov     [rbp+57h+var_80], rdi
0x180008d71  test    rcx, rcx
0x180008d74  jnz     short loc_180008D90
0x180008d76  mov     r8d, 8032001Ch
0x180008d7c  lea     rdx, aFwpmfilteradd0_0; "FwpmFilterAdd0"
0x180008d83  call    WfpReportSysErrorAsWinError
0x180008d88  mov     rbx, rax
0x180008d8b  jmp     loc_1800090AE
0x180008d90  mov     dword ptr [rbp+57h+dwBytes], edi
0x180008d93  mov     rbx, rdi
0x180008d96  mov     [rbp+57h+Revision], edi
0x180008d99  mov     word ptr [rbp+57h+dwBytes+4], di
0x180008d9d  mov     [rbp+57h+var_A8], rdi
0x180008da1  mov     qword ptr [rbp+57h+var_94+4], rdi
0x180008da5  test    r14, r14
0x180008da8  jz      loc_180008FFA
0x180008dae  mov     rcx, r14; SecurityDescriptor
0x180008db1  call    cs:__imp_RtlLengthSecurityDescriptor
0x180008db8  nop     dword ptr [rax+rax+00h]
0x180008dbd  lea     r8, [rbp+57h+Revision]; Revision
0x180008dc1  mov     rcx, r14; SecurityDescriptor
0x180008dc4  lea     rdx, [rbp+57h+dwBytes+4]; Control
0x180008dc8  mov     dword ptr [rbp+57h+dwBytes], eax
0x180008dcb  call    cs:__imp_RtlGetControlSecurityDescriptor
0x180008dd2  nop     dword ptr [rax+rax+00h]
0x180008dd7  test    eax, eax
0x180008dd9  jns     short loc_180008DEF
0x180008ddb  mov     r8d, eax
0x180008dde  lea     rdx, aRtlgetcontrols; "RtlGetControlSecurityDescriptor"
0x180008de5  call    WfpReportSysErrorAsNtStatus
0x180008dea  jmp     loc_180008FC4
0x180008def  mov     eax, 8000h
0x180008df4  test    word ptr [rbp+57h+dwBytes+4], ax
0x180008df8  jz      short loc_180008E03
0x180008dfa  mov     qword ptr [rbp+57h+var_94+4], r14
0x180008dfe  jmp     loc_180008FF4
0x180008e03  mov     ebx, dword ptr [rbp+57h+dwBytes]
0x180008e06  mov     eax, cs:Feature_BFE_MemAlloc_BugFixes_25B__private_featureState
0x180008e0c  test    al, 10h
0x180008e0e  jz      short loc_180008E15
0x180008e10  and     eax, 1
0x180008e13  jmp     short loc_180008E1A
0x180008e15  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline
0x180008e1a  mov     rcx, cs:gWfpHeap; hHeap
0x180008e21  xor     edx, edx; dwFlags
0x180008e23  mov     r8, rbx; dwBytes
0x180008e26  test    eax, eax
0x180008e28  jz      loc_180008F17
0x180008e2e  call    cs:__imp_HeapAlloc
0x180008e35  nop     dword ptr [rax+rax+00h]
0x180008e3a  mov     [rbp+57h+var_A8], rax
0x180008e3e  mov     rdi, rax
0x180008e41  test    rax, rax
0x180008e44  jnz     loc_180008F04
0x180008e4a  mov     r8d, 0C0000017h
0x180008e50  lea     rdx, aHeapalloc; "HeapAlloc"
0x180008e57  call    WfpReportSysErrorAsNtStatus
0x180008e5c  mov     rbx, rax
0x180008e5f  test    rax, rax
0x180008e62  jz      loc_180008F83
0x180008e68  mov     rcx, cs:WPP_GLOBAL_Control
0x180008e6f  lea     rax, WPP_GLOBAL_Control
0x180008e76  lea     r8, aWfpmemalloc25b; "WfpMemAlloc25B"
0x180008e7d  cmp     rcx, rax
0x180008e80  jz      short loc_180008EAF
0x180008e82  cmp     byte ptr [rcx+19h], 2
0x180008e86  jb      short loc_180008EAF
0x180008e88  test    byte ptr [rcx+1Ch], 1
0x180008e8c  jz      short loc_180008EAF
0x180008e8e  mov     rcx, [rcx+10h]
0x180008e92  mov     edx, 1Ah
0x180008e97  mov     dword ptr [rsp+0F0h+var_C8], ebx
0x180008e9b  xor     r9d, r9d
0x180008e9e  mov     [rsp+0F0h+var_D0], r8
0x180008ea3  call    WPP_SF_Ssd
0x180008ea8  lea     r8, aWfpmemalloc25b; "WfpMemAlloc25B"
0x180008eaf  cmp     cs:gWfpLogUserModeErrors, esi
0x180008eb5  jz      loc_180008F83
0x180008ebb  test    cs:byte_18007C665, 1
0x180008ec2  jz      loc_180008F83
0x180008ec8  lea     rax, [rbp+57h+var_B0]
0x180008ecc  mov     [rbp+57h+var_B0], ebx
0x180008ecf  mov     [rbp+57h+var_58], rax
0x180008ed3  lea     rdx, WFP_USERMODE_ERROR
0x180008eda  lea     rax, [rbp+57h+var_78]
0x180008ede  mov     [rbp+57h+var_68], r8
0x180008ee2  mov     r9d, 3
0x180008ee8  mov     [rsp+0F0h+var_D0], rax
0x180008eed  mov     [rbp+57h+var_60], 0Fh
0x180008ef5  mov     [rbp+57h+var_50], 4
0x180008efd  call    McGenEventWrite_EtwEventWriteTransfer
0x180008f02  jmp     short loc_180008F83
0x180008f04  xor     ebx, ebx
0x180008f06  cmp     cs:gWfpTrackHeapAllocs, ebx
0x180008f0c  jz      short loc_180008F83
0x180008f0e  lock inc cs:gWfpNumHeapAllocs
0x180008f15  jmp     short loc_180008F83
0x180008f17  call    cs:__imp_HeapAlloc
0x180008f1e  nop     dword ptr [rax+rax+00h]
0x180008f23  mov     [rbp+57h+var_A8], rax
0x180008f27  mov     rdi, rax
0x180008f2a  test    rax, rax
0x180008f2d  jnz     short loc_180008F5A
0x180008f2f  mov     r8d, 0C0000017h
0x180008f35  lea     rdx, aHeapalloc; "HeapAlloc"
0x180008f3c  call    WfpReportSysErrorAsNtStatus
0x180008f41  mov     rbx, rax
0x180008f44  test    rax, rax
0x180008f47  jz      short loc_180008F83
0x180008f49  lea     rdx, aWfpmemalloc; "WfpMemAlloc"
0x180008f50  mov     rcx, rax
0x180008f53  call    WfpReportError
0x180008f58  jmp     short loc_180008F83
0x180008f5a  xor     ebx, ebx
0x180008f5c  cmp     cs:gWfpTrackHeapBytes, ebx
0x180008f62  jz      short loc_180008F83
0x180008f64  mov     rcx, cs:gWfpHeap; hHeap
0x180008f6b  mov     r8, rax; lpMem
0x180008f6e  xor     edx, edx; dwFlags
0x180008f70  call    cs:__imp_HeapSize
0x180008f77  nop     dword ptr [rax+rax+00h]
0x180008f7c  lock add cs:gWfpHeapBytesAllocated, eax
0x180008f83  test    rbx, rbx
0x180008f86  jz      short loc_180008F99
0x180008f88  lea     rdx, aWfppoolallocno; "WfpPoolAllocNonPaged"
0x180008f8f  mov     rcx, rbx
0x180008f92  call    WfpReportError
0x180008f97  jmp     short loc_180008FCC
0x180008f99  lea     r8, [rbp+57h+dwBytes]; BufferLength
0x180008f9d  mov     rdx, rdi; SelfRelativeSecurityDescriptor
0x180008fa0  mov     rcx, r14; AbsoluteSecurityDescriptor
0x180008fa3  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x180008faa  nop     dword ptr [rax+rax+00h]
0x180008faf  test    eax, eax
0x180008fb1  jns     short loc_180008FEB
0x180008fb3  mov     r8d, eax
0x180008fb6  lea     rdx, aRtlabsolutetos; "RtlAbsoluteToSelfRelativeSD"
0x180008fbd  call    WfpReportSysErrorAsNtStatus
0x180008fc2  xor     edi, edi
0x180008fc4  mov     rbx, rax
0x180008fc7  test    rax, rax
0x180008fca  jz      short loc_180008FFA
0x180008fcc  lea     rcx, [rbp+57h+var_A8]
0x180008fd0  call    WfpMemFree
0x180008fd5  lea     rdx, aBfesecuritydes; "BfeSecurityDescriptorEncode"
0x180008fdc  mov     rcx, rbx
0x180008fdf  call    WfpReportError
0x180008fe4  xor     edi, edi
0x180008fe6  jmp     loc_1800090AE
0x180008feb  mov     qword ptr [rbp+57h+var_94+4], rdi
0x180008fef  mov     rsi, rdi
0x180008ff2  xor     edi, edi
0x180008ff4  mov     eax, dword ptr [rbp+57h+dwBytes]
0x180008ff7  mov     [rbp+57h+var_98], eax
0x180008ffa  mov     rdx, [r15+70h]
0x180008ffe  test    rdx, rdx
0x180009001  jnz     short loc_180009060
0x180009003  mov     r9, [r15]
0x180009006  lea     rax, [rbp+57h+var_80]
0x18000900a  mov     [rsp+38h], rax
0x18000900f  lea     rcx, [rbp+57h+var_98]
0x180009013  mov     rax, [r15+8]
0x180009017  test    r14, r14
0x18000901a  mov     edx, 46h ; 'F'; nProcNum
0x18000901f  cmovz   rcx, rdi
0x180009023  xor     r8d, r8d; pReturnValue
0x180009026  mov     [rsp+0F0h+var_C0], rcx
0x18000902b  lea     rcx, pProxyInfo; pProxyInfo
0x180009032  mov     [rsp+0F0h+var_C8], r13
0x180009037  mov     [rsp+0F0h+var_D0], rax
0x18000903c  call    cs:__imp_NdrClientCall3
0x180009043  nop     dword ptr [rax+rax+00h]
0x180009048  test    eax, eax
0x18000904a  jz      short loc_1800090A1
0x18000904c  mov     r8d, eax
0x18000904f  lea     rdx, aFwppproxyfilte_2; "FwppProxyFilterAdd"
0x180009056  call    WfpReportSysErrorAsWinError
0x18000905b  mov     rbx, rax
0x18000905e  jmp     short loc_1800090AE
0x180009060  mov     rax, cs:g_pBfeDirectDispatchTable
0x180009067  lea     rcx, [rbp+57h+var_80]
0x18000906b  mov     [rsp+0F0h+var_D0], rcx
0x180009070  lea     r9, [rbp+57h+var_98]
0x180009074  test    r14, r14
0x180009077  mov     r8, r13
0x18000907a  mov     rax, [rax+10h]
0x18000907e  cmovz   r9, rdi
0x180009082  xor     ecx, ecx
0x180009084  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009089  test    eax, eax
0x18000908b  jz      short loc_1800090A1
0x18000908d  mov     r8d, eax
0x180009090  lea     rdx, aBferpcfilterad; "BfeRpcFilterAdd"
0x180009097  call    WfpReportSysErrorAsWinError
0x18000909c  mov     rbx, rax
0x18000909f  jmp     short loc_1800090AE
0x1800090a1  test    r12, r12
0x1800090a4  jz      short loc_1800090AE
0x1800090a6  mov     rax, [rbp+57h+var_80]
0x1800090aa  mov     [r12], rax
0x1800090ae  mov     eax, cs:Feature_BFE_MemAlloc_BugFixes_25B__private_featureState
0x1800090b4  mov     r15, [rsp+0F0h+var_38]
0x1800090bc  mov     r14, [rsp+0F0h+var_30]
0x1800090c4  mov     r13, [rsp+0F0h+var_28]
0x1800090cc  mov     r12, [rsp+0F0h+var_20]
0x1800090d4  test    al, 10h
0x1800090d6  jz      short loc_1800090DD
0x1800090d8  and     eax, 1
0x1800090db  jmp     short loc_1800090E2
0x1800090dd  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline
0x1800090e2  test    eax, eax
0x1800090e4  jz      loc_18000916A
0x1800090ea  cmp     cs:gWfpTrackHeapAllocs, 0
0x1800090f1  jz      short loc_180009134
0x1800090f3  test    rsi, rsi
0x1800090f6  jz      short loc_180009134
0x1800090f8  mov     eax, 0FFFFFFFFh
0x1800090fd  lock xadd cs:gWfpNumHeapAllocs, eax
0x180009105  cmp     eax, 1
0x180009108  jns     short loc_180009134
0x18000910a  cmp     cs:gMisalignedHeapTelemFired, 0
0x180009111  jnz     short loc_18000912B
0x180009113  cmp     cs:gWfpNumHeapAllocs, 0
0x18000911a  jg      short loc_180009121
0x18000911c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180009121  mov     cs:gMisalignedHeapTelemFired, 1
0x18000912b  lock inc cs:gWfpNumHeapAllocs
0x180009132  jmp     short loc_1800091B1
0x180009134  mov     rcx, cs:gWfpHeap; hHeap
0x18000913b  mov     r8, rsi; lpMem
0x18000913e  xor     edx, edx; dwFlags
0x180009140  call    cs:__imp_HeapFree
0x180009147  nop     dword ptr [rax+rax+00h]
0x18000914c  cmp     cs:gHeapFreeFailedFired, 0
0x180009153  jnz     short loc_1800091B1
0x180009155  test    eax, eax
0x180009157  jnz     short loc_1800091B1
0x180009159  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000915e  mov     cs:gHeapFreeFailedFired, 1
0x180009168  jmp     short loc_1800091B1
0x18000916a  cmp     cs:gWfpTrackHeapBytes, 0
0x180009171  jz      short loc_180009199
0x180009173  test    rsi, rsi
0x180009176  jz      short loc_180009199
0x180009178  mov     rcx, cs:gWfpHeap; hHeap
0x18000917f  mov     r8, rsi; lpMem
0x180009182  xor     edx, edx; dwFlags
0x180009184  call    cs:__imp_HeapSize
0x18000918b  nop     dword ptr [rax+rax+00h]
0x180009190  neg     eax
0x180009192  lock add cs:gWfpHeapBytesAllocated, eax
0x180009199  mov     rcx, cs:gWfpHeap; hHeap
0x1800091a0  mov     r8, rsi; lpMem
0x1800091a3  xor     edx, edx; dwFlags
0x1800091a5  call    cs:__imp_HeapFree
0x1800091ac  nop     dword ptr [rax+rax+00h]
0x1800091b1  mov     rsi, [rsp+0D8h]
0x1800091b9  test    rbx, rbx
0x1800091bc  jnz     short loc_1800091C2
0x1800091be  mov     eax, edi
0x1800091c0  jmp     short loc_180009209
0x1800091c2  mov     eax, ebx
0x1800091c4  movzx   edx, bx
0x1800091c7  and     eax, 1FFF0000h
0x1800091cc  cmp     eax, 70000h
0x1800091d1  cmovnz  edx, ebx
0x1800091d4  mov     ecx, edx
0x1800091d6  sub     ecx, 6
0x1800091d9  jz      short loc_180009204
0x1800091db  sub     ecx, 6B9h
0x1800091e1  jz      short loc_180009204
0x1800091e3  sub     ecx, 6
0x1800091e6  jz      short loc_1800091FD
0x1800091e8  sub     ecx, 2Ah ; '*'
0x1800091eb  jz      short loc_1800091F6
0x1800091ed  cmp     ecx, 5
0x1800091f0  jz      short loc_1800091F6
  ... truncated ...
```
