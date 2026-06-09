# FwpmProviderContextAdd3

- ea: `0x180001b00`
- end: `0x180002000`
- name: `FwpmProviderContextAdd3`
- size: `1280`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800023b0`
- `0x180016be0`
- `0x180016c80`

## callees

- `0x180001b00`
- `0x1800034e0`
- `0x18000438c`
- `0x180007e38`
- `0x18000dd70`
- `0x18000e898`
- `0x180011500`
- `0x180012bd0`
- `0x18003a298`
- `0x18004703c`
- `0x18004b010`

## import_xrefs

- `ntdll!RtlLengthSecurityDescriptor` at `0x180001b91`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180001b91`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x180001d83`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x180001d83`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x180001bab`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x180001bab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001f1f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001f84`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001f1f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001f84`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180001d50`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180001f63`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180001d50`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180001f63`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001c0e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001cf7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001c0e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001cf7`
- `RPCRT4!NdrClientCall3` at `0x180001e1c`
- `RPCRT4!NdrClientCall3` at `0x180001e1c`

## string_xrefs

- `0x180001db5`: `BfeSecurityDescriptorEncode`
- `0x180001bbe`: `RtlGetControlSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall FwpmProviderContextAdd3(_QWORD *a1, __int64 a2, void *a3, _QWORD *a4)
{
  void *v8; // rsi
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rbx
  __int64 v12; // r8
  NTSTATUS ControlSecurityDescriptor; // eax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // rax
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 v19; // rcx
  void *v20; // rdi
  int v21; // ecx
  void *v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rax
  NTSTATUS v25; // eax
  __int64 v26; // rcx
  __int64 v27; // rdx
  __int64 *v28; // rcx
  unsigned int Pointer; // eax
  __int64 *v30; // r9
  unsigned int v31; // eax
  int v32; // eax
  BOOL v33; // eax
  unsigned int v35; // edx
  int v36; // [rsp+48h] [rbp-59h] BYREF
  LPVOID v37; // [rsp+50h] [rbp-51h] BYREF
  ULONG dwBytes; // [rsp+58h] [rbp-49h] BYREF
  __int16 dwBytes_4; // [rsp+5Ch] [rbp-45h] BYREF
  __int64 v40; // [rsp+60h] [rbp-41h] BYREF
  void *v41; // [rsp+68h] [rbp-39h]
  ULONG Revision; // [rsp+70h] [rbp-31h] BYREF
  __int64 v43; // [rsp+78h] [rbp-29h] BYREF
  _BYTE v44[16]; // [rsp+80h] [rbp-21h] BYREF
  const char *v45; // [rsp+90h] [rbp-11h]
  __int64 v46; // [rsp+98h] [rbp-9h]
  int *v47; // [rsp+A0h] [rbp-1h]
  __int64 v48; // [rsp+A8h] [rbp+7h]

  LODWORD(v41) = 0;
  v40 = 0;
  v8 = 0;
  v43 = 0;
  if ( !a1 )
  {
    v11 = WfpReportSysErrorAsWinError(0, "FwpmProviderContextAdd3", 2150760476LL);
    goto LABEL_47;
  }
  dwBytes = 0;
  v11 = 0;
  Revision = 0;
  dwBytes_4 = 0;
  v37 = 0;
  v41 = 0;
  if ( !a3 )
    goto LABEL_36;
  dwBytes = RtlLengthSecurityDescriptor(a3);
  ControlSecurityDescriptor = RtlGetControlSecurityDescriptor(a3, (PSECURITY_DESCRIPTOR_CONTROL)&dwBytes_4, &Revision);
  if ( ControlSecurityDescriptor < 0 )
  {
    v17 = WfpReportSysErrorAsNtStatus(v15, "RtlGetControlSecurityDescriptor", (unsigned int)ControlSecurityDescriptor);
    goto LABEL_32;
  }
  if ( dwBytes_4 < 0 )
  {
    v41 = a3;
LABEL_35:
    LODWORD(v40) = dwBytes;
    goto LABEL_36;
  }
  if ( (Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 0x10) != 0 )
    IsEnabledDeviceUsageNoInline = Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 1;
  else
    IsEnabledDeviceUsageNoInline = Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline(
                                     v15,
                                     v14,
                                     v16);
  if ( IsEnabledDeviceUsageNoInline )
  {
    v37 = HeapAlloc(gWfpHeap, 0, dwBytes);
    v20 = v37;
    if ( v37 )
    {
      v11 = 0;
      if ( gWfpTrackHeapAllocs )
        _InterlockedIncrement(&gWfpNumHeapAllocs);
    }
    else
    {
      v11 = WfpReportSysErrorAsNtStatus(v19, "HeapAlloc", 3221225495LL);
      if ( v11 )
      {
        v21 = (int)WPP_GLOBAL_Control;
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
            v11);
        }
        if ( gWfpLogUserModeErrors && (byte_18007C665 & 1) != 0 )
        {
          v36 = v11;
          v47 = &v36;
          v45 = "WfpMemAlloc25B";
          v46 = 15;
          v48 = 4;
          McGenEventWrite_EtwEventWriteTransfer(
            v21,
            (unsigned int)WFP_USERMODE_ERROR,
            (unsigned int)"WfpMemAlloc25B",
            3,
            (__int64)v44);
        }
      }
    }
  }
  else
  {
    v22 = HeapAlloc(gWfpHeap, 0, dwBytes);
    v37 = v22;
    v20 = v22;
    if ( v22 )
    {
      v11 = 0;
      if ( gWfpTrackHeapBytes )
        _InterlockedAdd(&gWfpHeapBytesAllocated, HeapSize(gWfpHeap, 0, v22));
    }
    else
    {
      v24 = WfpReportSysErrorAsNtStatus(v23, "HeapAlloc", 3221225495LL);
      v11 = v24;
      if ( v24 )
        WfpReportError(v24, "WfpMemAlloc");
    }
  }
  if ( v11 )
  {
    WfpReportError(v11, "WfpPoolAllocNonPaged");
LABEL_33:
    WfpMemFree(&v37);
    WfpReportError(v11, "BfeSecurityDescriptorEncode");
    goto LABEL_47;
  }
  v25 = RtlAbsoluteToSelfRelativeSD(a3, v20, &dwBytes);
  if ( v25 >= 0 )
  {
    v41 = v20;
    v8 = v20;
    goto LABEL_35;
  }
  v17 = WfpReportSysErrorAsNtStatus(v26, "RtlAbsoluteToSelfRelativeSD", (unsigned int)v25);
LABEL_32:
  v11 = v17;
  if ( v17 )
    goto LABEL_33;
LABEL_36:
  v27 = a1[14];
  if ( v27 )
  {
    v30 = &v40;
    if ( !a3 )
      v30 = 0;
    v31 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64 *, __int64 *))g_pBfeDirectDispatchTable)(
            0,
            v27,
            a2,
            v30,
            &v43);
    if ( v31 )
    {
      v11 = WfpReportSysErrorAsWinError(v10, "BfeRpcProviderContextAdd", v31);
      goto LABEL_47;
    }
  }
  else
  {
    v28 = &v40;
    if ( !a3 )
      v28 = 0;
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x1Au, 0, *a1, a1[1], a2, v28, &v43).Pointer;
    if ( Pointer )
    {
      v11 = WfpReportSysErrorAsWinError(v10, "FwppProxyProviderContextAdd", Pointer);
      goto LABEL_47;
    }
  }
  if ( a4 )
    *a4 = v43;
LABEL_47:
  if ( (Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 0x10) != 0 )
    v32 = Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 1;
  else
    v32 = Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline(v10, v9, v12);
  if ( v32 )
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
      v33 = HeapFree(gWfpHeap, 0, v8);
      if ( !gHeapFreeFailedFired && !v33 )
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
  if ( !v11 )
    return 0;
  v35 = (unsigned __int16)v11;
  if ( (v11 & 0x1FFF0000) != 0x70000 )
    v35 = v11;
  switch ( v35 )
  {
    case 6u:
    case 0x6BFu:
      return 2150760464LL;
    case 0x6C5u:
      return 2150760477LL;
    case 0x6EFu:
    case 0x6F4u:
      return 2150760476LL;
  }
  return v35;
}

```

## disassembly

```asm
0x180001b00  mov     r11, rsp
0x180001b03  push    rbp
0x180001b04  push    rbx
0x180001b05  push    rdi
0x180001b06  lea     rbp, [r11-5Fh]
0x180001b0a  sub     rsp, 0E0h
0x180001b11  mov     rax, cs:__security_cookie
0x180001b18  xor     rax, rsp
0x180001b1b  mov     [rbp+57h+var_48], rax
0x180001b1f  mov     [r11-20h], rsi
0x180001b23  xor     eax, eax
0x180001b25  mov     [r11-28h], r12
0x180001b29  xor     edi, edi
0x180001b2b  mov     [r11-30h], r13
0x180001b2f  mov     r12, r9
0x180001b32  mov     [r11-38h], r14
0x180001b36  mov     r14, r8
0x180001b39  mov     [r11-40h], r15
0x180001b3d  mov     r15, rcx
0x180001b40  mov     qword ptr [rbp+57h+var_94], rax
0x180001b44  mov     r13, rdx
0x180001b47  mov     [rbp-41h], rax
0x180001b4b  mov     esi, edi
0x180001b4d  mov     [rbp+57h+var_80], rdi
0x180001b51  test    rcx, rcx
0x180001b54  jnz     short loc_180001B70
0x180001b56  mov     r8d, 8032001Ch
0x180001b5c  lea     rdx, aFwpmproviderco_46; "FwpmProviderContextAdd3"
0x180001b63  call    WfpReportSysErrorAsWinError
0x180001b68  mov     rbx, rax
0x180001b6b  jmp     loc_180001E8D
0x180001b70  mov     dword ptr [rbp+57h+dwBytes], edi
0x180001b73  mov     rbx, rdi
0x180001b76  mov     [rbp+57h+Revision], edi
0x180001b79  mov     word ptr [rbp+57h+dwBytes+4], di
0x180001b7d  mov     [rbp+57h+var_A8], rdi
0x180001b81  mov     qword ptr [rbp+57h+var_94+4], rdi
0x180001b85  test    r14, r14
0x180001b88  jz      loc_180001DDA
0x180001b8e  mov     rcx, r14; SecurityDescriptor
0x180001b91  call    cs:__imp_RtlLengthSecurityDescriptor
0x180001b98  nop     dword ptr [rax+rax+00h]
0x180001b9d  lea     r8, [rbp+57h+Revision]; Revision
0x180001ba1  mov     rcx, r14; SecurityDescriptor
0x180001ba4  lea     rdx, [rbp+57h+dwBytes+4]; Control
0x180001ba8  mov     dword ptr [rbp+57h+dwBytes], eax
0x180001bab  call    cs:__imp_RtlGetControlSecurityDescriptor
0x180001bb2  nop     dword ptr [rax+rax+00h]
0x180001bb7  test    eax, eax
0x180001bb9  jns     short loc_180001BCF
0x180001bbb  mov     r8d, eax
0x180001bbe  lea     rdx, aRtlgetcontrols; "RtlGetControlSecurityDescriptor"
0x180001bc5  call    WfpReportSysErrorAsNtStatus
0x180001bca  jmp     loc_180001DA4
0x180001bcf  mov     eax, 8000h
0x180001bd4  test    word ptr [rbp+57h+dwBytes+4], ax
0x180001bd8  jz      short loc_180001BE3
0x180001bda  mov     qword ptr [rbp+57h+var_94+4], r14
0x180001bde  jmp     loc_180001DD4
0x180001be3  mov     ebx, dword ptr [rbp+57h+dwBytes]
0x180001be6  mov     eax, cs:Feature_BFE_MemAlloc_BugFixes_25B__private_featureState
0x180001bec  test    al, 10h
0x180001bee  jz      short loc_180001BF5
0x180001bf0  and     eax, 1
0x180001bf3  jmp     short loc_180001BFA
0x180001bf5  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline
0x180001bfa  mov     rcx, cs:gWfpHeap; hHeap
0x180001c01  xor     edx, edx; dwFlags
0x180001c03  mov     r8, rbx; dwBytes
0x180001c06  test    eax, eax
0x180001c08  jz      loc_180001CF7
0x180001c0e  call    cs:__imp_HeapAlloc
0x180001c15  nop     dword ptr [rax+rax+00h]
0x180001c1a  mov     [rbp+57h+var_A8], rax
0x180001c1e  mov     rdi, rax
0x180001c21  test    rax, rax
0x180001c24  jnz     loc_180001CE4
0x180001c2a  mov     r8d, 0C0000017h
0x180001c30  lea     rdx, aHeapalloc; "HeapAlloc"
0x180001c37  call    WfpReportSysErrorAsNtStatus
0x180001c3c  mov     rbx, rax
0x180001c3f  test    rax, rax
0x180001c42  jz      loc_180001D63
0x180001c48  mov     rcx, cs:WPP_GLOBAL_Control
0x180001c4f  lea     rax, WPP_GLOBAL_Control
0x180001c56  lea     r8, aWfpmemalloc25b; "WfpMemAlloc25B"
0x180001c5d  cmp     rcx, rax
0x180001c60  jz      short loc_180001C8F
0x180001c62  cmp     byte ptr [rcx+19h], 2
0x180001c66  jb      short loc_180001C8F
0x180001c68  test    byte ptr [rcx+1Ch], 1
0x180001c6c  jz      short loc_180001C8F
0x180001c6e  mov     rcx, [rcx+10h]
0x180001c72  mov     edx, 1Ah
0x180001c77  mov     dword ptr [rsp+0F0h+var_C8], ebx
0x180001c7b  xor     r9d, r9d
0x180001c7e  mov     [rsp+0F0h+var_D0], r8
0x180001c83  call    WPP_SF_Ssd
0x180001c88  lea     r8, aWfpmemalloc25b; "WfpMemAlloc25B"
0x180001c8f  cmp     cs:gWfpLogUserModeErrors, esi
0x180001c95  jz      loc_180001D63
0x180001c9b  test    cs:byte_18007C665, 1
0x180001ca2  jz      loc_180001D63
0x180001ca8  lea     rax, [rbp+57h+var_B0]
0x180001cac  mov     [rbp+57h+var_B0], ebx
0x180001caf  mov     [rbp+57h+var_58], rax
0x180001cb3  lea     rdx, WFP_USERMODE_ERROR
0x180001cba  lea     rax, [rbp+57h+var_78]
0x180001cbe  mov     [rbp+57h+var_68], r8
0x180001cc2  mov     r9d, 3
0x180001cc8  mov     [rsp+0F0h+var_D0], rax
0x180001ccd  mov     [rbp+57h+var_60], 0Fh
0x180001cd5  mov     [rbp+57h+var_50], 4
0x180001cdd  call    McGenEventWrite_EtwEventWriteTransfer
0x180001ce2  jmp     short loc_180001D63
0x180001ce4  xor     ebx, ebx
0x180001ce6  cmp     cs:gWfpTrackHeapAllocs, ebx
0x180001cec  jz      short loc_180001D63
0x180001cee  lock inc cs:gWfpNumHeapAllocs
0x180001cf5  jmp     short loc_180001D63
0x180001cf7  call    cs:__imp_HeapAlloc
0x180001cfe  nop     dword ptr [rax+rax+00h]
0x180001d03  mov     [rbp+57h+var_A8], rax
0x180001d07  mov     rdi, rax
0x180001d0a  test    rax, rax
0x180001d0d  jnz     short loc_180001D3A
0x180001d0f  mov     r8d, 0C0000017h
0x180001d15  lea     rdx, aHeapalloc; "HeapAlloc"
0x180001d1c  call    WfpReportSysErrorAsNtStatus
0x180001d21  mov     rbx, rax
0x180001d24  test    rax, rax
0x180001d27  jz      short loc_180001D63
0x180001d29  lea     rdx, aWfpmemalloc; "WfpMemAlloc"
0x180001d30  mov     rcx, rax
0x180001d33  call    WfpReportError
0x180001d38  jmp     short loc_180001D63
0x180001d3a  xor     ebx, ebx
0x180001d3c  cmp     cs:gWfpTrackHeapBytes, ebx
0x180001d42  jz      short loc_180001D63
0x180001d44  mov     rcx, cs:gWfpHeap; hHeap
0x180001d4b  mov     r8, rax; lpMem
0x180001d4e  xor     edx, edx; dwFlags
0x180001d50  call    cs:__imp_HeapSize
0x180001d57  nop     dword ptr [rax+rax+00h]
0x180001d5c  lock add cs:gWfpHeapBytesAllocated, eax
0x180001d63  test    rbx, rbx
0x180001d66  jz      short loc_180001D79
0x180001d68  lea     rdx, aWfppoolallocno; "WfpPoolAllocNonPaged"
0x180001d6f  mov     rcx, rbx
0x180001d72  call    WfpReportError
0x180001d77  jmp     short loc_180001DAC
0x180001d79  lea     r8, [rbp+57h+dwBytes]; BufferLength
0x180001d7d  mov     rdx, rdi; SelfRelativeSecurityDescriptor
0x180001d80  mov     rcx, r14; AbsoluteSecurityDescriptor
0x180001d83  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x180001d8a  nop     dword ptr [rax+rax+00h]
0x180001d8f  test    eax, eax
0x180001d91  jns     short loc_180001DCB
0x180001d93  mov     r8d, eax
0x180001d96  lea     rdx, aRtlabsolutetos; "RtlAbsoluteToSelfRelativeSD"
0x180001d9d  call    WfpReportSysErrorAsNtStatus
0x180001da2  xor     edi, edi
0x180001da4  mov     rbx, rax
0x180001da7  test    rax, rax
0x180001daa  jz      short loc_180001DDA
0x180001dac  lea     rcx, [rbp+57h+var_A8]
0x180001db0  call    WfpMemFree
0x180001db5  lea     rdx, aBfesecuritydes; "BfeSecurityDescriptorEncode"
0x180001dbc  mov     rcx, rbx
0x180001dbf  call    WfpReportError
0x180001dc4  xor     edi, edi
0x180001dc6  jmp     loc_180001E8D
0x180001dcb  mov     qword ptr [rbp+57h+var_94+4], rdi
0x180001dcf  mov     rsi, rdi
0x180001dd2  xor     edi, edi
0x180001dd4  mov     eax, dword ptr [rbp+57h+dwBytes]
0x180001dd7  mov     [rbp+57h+var_98], eax
0x180001dda  mov     rdx, [r15+70h]
0x180001dde  test    rdx, rdx
0x180001de1  jnz     short loc_180001E40
0x180001de3  mov     r9, [r15]
0x180001de6  lea     rax, [rbp+57h+var_80]
0x180001dea  mov     [rsp+38h], rax
0x180001def  lea     rcx, [rbp+57h+var_98]
0x180001df3  mov     rax, [r15+8]
0x180001df7  test    r14, r14
0x180001dfa  mov     edx, 1Ah; nProcNum
0x180001dff  cmovz   rcx, rdi
0x180001e03  xor     r8d, r8d; pReturnValue
0x180001e06  mov     [rsp+0F0h+var_C0], rcx
0x180001e0b  lea     rcx, pProxyInfo; pProxyInfo
0x180001e12  mov     [rsp+0F0h+var_C8], r13
0x180001e17  mov     [rsp+0F0h+var_D0], rax
0x180001e1c  call    cs:__imp_NdrClientCall3
0x180001e23  nop     dword ptr [rax+rax+00h]
0x180001e28  test    eax, eax
0x180001e2a  jz      short loc_180001E80
0x180001e2c  mov     r8d, eax
0x180001e2f  lea     rdx, aFwppproxyprovi_7; "FwppProxyProviderContextAdd"
0x180001e36  call    WfpReportSysErrorAsWinError
0x180001e3b  mov     rbx, rax
0x180001e3e  jmp     short loc_180001E8D
0x180001e40  mov     rax, cs:g_pBfeDirectDispatchTable
0x180001e47  lea     rcx, [rbp+57h+var_80]
0x180001e4b  mov     [rsp+0F0h+var_D0], rcx
0x180001e50  lea     r9, [rbp+57h+var_98]
0x180001e54  test    r14, r14
0x180001e57  mov     r8, r13
0x180001e5a  mov     rax, [rax]
0x180001e5d  cmovz   r9, rdi
0x180001e61  xor     ecx, ecx
0x180001e63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e68  test    eax, eax
0x180001e6a  jz      short loc_180001E80
0x180001e6c  mov     r8d, eax
0x180001e6f  lea     rdx, aBferpcprovider_2; "BfeRpcProviderContextAdd"
0x180001e76  call    WfpReportSysErrorAsWinError
0x180001e7b  mov     rbx, rax
0x180001e7e  jmp     short loc_180001E8D
0x180001e80  test    r12, r12
0x180001e83  jz      short loc_180001E8D
0x180001e85  mov     rax, [rbp+57h+var_80]
0x180001e89  mov     [r12], rax
0x180001e8d  mov     eax, cs:Feature_BFE_MemAlloc_BugFixes_25B__private_featureState
0x180001e93  mov     r15, [rsp+0F0h+var_38]
0x180001e9b  mov     r14, [rsp+0F0h+var_30]
0x180001ea3  mov     r13, [rsp+0F0h+var_28]
0x180001eab  mov     r12, [rsp+0F0h+var_20]
0x180001eb3  test    al, 10h
0x180001eb5  jz      short loc_180001EBC
0x180001eb7  and     eax, 1
0x180001eba  jmp     short loc_180001EC1
0x180001ebc  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline
0x180001ec1  test    eax, eax
0x180001ec3  jz      loc_180001F49
0x180001ec9  cmp     cs:gWfpTrackHeapAllocs, 0
0x180001ed0  jz      short loc_180001F13
0x180001ed2  test    rsi, rsi
0x180001ed5  jz      short loc_180001F13
0x180001ed7  mov     eax, 0FFFFFFFFh
0x180001edc  lock xadd cs:gWfpNumHeapAllocs, eax
0x180001ee4  cmp     eax, 1
0x180001ee7  jns     short loc_180001F13
0x180001ee9  cmp     cs:gMisalignedHeapTelemFired, 0
0x180001ef0  jnz     short loc_180001F0A
0x180001ef2  cmp     cs:gWfpNumHeapAllocs, 0
0x180001ef9  jg      short loc_180001F00
0x180001efb  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180001f00  mov     cs:gMisalignedHeapTelemFired, 1
0x180001f0a  lock inc cs:gWfpNumHeapAllocs
0x180001f11  jmp     short loc_180001F90
0x180001f13  mov     rcx, cs:gWfpHeap; hHeap
0x180001f1a  mov     r8, rsi; lpMem
0x180001f1d  xor     edx, edx; dwFlags
0x180001f1f  call    cs:__imp_HeapFree
0x180001f26  nop     dword ptr [rax+rax+00h]
0x180001f2b  cmp     cs:gHeapFreeFailedFired, 0
0x180001f32  jnz     short loc_180001F90
0x180001f34  test    eax, eax
0x180001f36  jnz     short loc_180001F90
0x180001f38  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180001f3d  mov     cs:gHeapFreeFailedFired, 1
0x180001f47  jmp     short loc_180001F90
0x180001f49  cmp     cs:gWfpTrackHeapBytes, 0
0x180001f50  jz      short loc_180001F78
0x180001f52  test    rsi, rsi
0x180001f55  jz      short loc_180001F78
0x180001f57  mov     rcx, cs:gWfpHeap; hHeap
0x180001f5e  mov     r8, rsi; lpMem
0x180001f61  xor     edx, edx; dwFlags
0x180001f63  call    cs:__imp_HeapSize
0x180001f6a  nop     dword ptr [rax+rax+00h]
0x180001f6f  neg     eax
0x180001f71  lock add cs:gWfpHeapBytesAllocated, eax
0x180001f78  mov     rcx, cs:gWfpHeap; hHeap
0x180001f7f  mov     r8, rsi; lpMem
0x180001f82  xor     edx, edx; dwFlags
0x180001f84  call    cs:__imp_HeapFree
0x180001f8b  nop     dword ptr [rax+rax+00h]
0x180001f90  mov     rsi, [rsp+0D8h]
0x180001f98  test    rbx, rbx
0x180001f9b  jnz     short loc_180001FA1
0x180001f9d  mov     eax, edi
0x180001f9f  jmp     short loc_180001FE8
0x180001fa1  mov     eax, ebx
0x180001fa3  movzx   edx, bx
0x180001fa6  and     eax, 1FFF0000h
0x180001fab  cmp     eax, 70000h
0x180001fb0  cmovnz  edx, ebx
0x180001fb3  mov     ecx, edx
0x180001fb5  sub     ecx, 6
0x180001fb8  jz      short loc_180001FE3
0x180001fba  sub     ecx, 6B9h
0x180001fc0  jz      short loc_180001FE3
0x180001fc2  sub     ecx, 6
0x180001fc5  jz      short loc_180001FDC
0x180001fc7  sub     ecx, 2Ah ; '*'
0x180001fca  jz      short loc_180001FD5
0x180001fcc  cmp     ecx, 5
0x180001fcf  jz      short loc_180001FD5
  ... truncated ...
```
