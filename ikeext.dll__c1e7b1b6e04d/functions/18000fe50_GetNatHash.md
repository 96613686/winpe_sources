# GetNatHash

- ea: `0x18000fe50`
- end: `0x180010679`
- name: `GetNatHash`
- size: `2089`
- prototype: `__int64 __fastcall(PUCHAR pbInput, PUCHAR, __int64, __int64, int, _DWORD *, __int64)`
- caller_count: `4`
- callee_count: `21`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180047450`
- `0x180101a30`
- `0x180101eb4`
- `0x180102124`

## callees

- `0x1800037c4`
- `0x1800061ec`
- `0x180008310`
- `0x180008388`
- `0x180008480`
- `0x180009ed0`
- `0x180009f30`
- `0x18000fe50`
- `0x180010770`
- `0x180010db0`
- `0x180011350`
- `0x180011680`
- `0x180016534`
- `0x18001c390`
- `0x18004882c`
- `0x18004890c`
- `0x18004aa3c`
- `0x18004ce90`
- `0x180050850`
- `0x1800528e4`
- `0x1800529a4`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800102df`
- `ntdll!RtlNtStatusToDosError` at `0x1800102df`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800103e2`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800104d7`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18001062e`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800103e2`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800104d7`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18001062e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001064a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001064a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010087`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800100ad`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010138`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001015e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010087`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800100ad`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010138`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001015e`
- `ncrypt!BCryptDestroyHash` at `0x18000ff6f`
- `ncrypt!BCryptDestroyHash` at `0x18000ff6f`
- `ncrypt!BCryptCreateHash` at `0x1800101a7`
- `ncrypt!BCryptCreateHash` at `0x1800101a7`
- `ncrypt!BCryptGetProperty` at `0x18001004a`
- `ncrypt!BCryptGetProperty` at `0x1800100f9`
- `ncrypt!BCryptGetProperty` at `0x18001004a`
- `ncrypt!BCryptGetProperty` at `0x1800100f9`
- `ncrypt!BCryptHashData` at `0x1800101fe`
- `ncrypt!BCryptHashData` at `0x180010248`
- `ncrypt!BCryptHashData` at `0x18001029c`
- `ncrypt!BCryptHashData` at `0x1800101fe`
- `ncrypt!BCryptHashData` at `0x180010248`
- `ncrypt!BCryptHashData` at `0x18001029c`

## string_xrefs

- `0x18001020c`: `IkeHashUpdate`
- `0x180010256`: `IkeHashUpdate`
- `0x1800102aa`: `IkeHashUpdate`
- `0x180010506`: `IkeHashUpdate`
- `0x18001053a`: `IkeHashUpdate`
- `0x18001056b`: `IkeHashUpdate`
- `0x1800104e9`: `BCryptCreateHash`

## pseudocode

```c
__int64 __fastcall GetNatHash(PUCHAR pbInput, PUCHAR a2, __int64 a3, __int64 a4, int a5, _DWORD *a6, __int64 a7)
{
  int v11; // r8d
  __int64 v12; // rbx
  PUCHAR v13; // rax
  __int64 v14; // rcx
  int v15; // eax
  const WCHAR *v17; // rcx
  void *CNGHandleForHashAlgo; // r14
  ULONG dwFlags; // edx
  unsigned int Property; // eax
  __int64 v21; // rcx
  SIZE_T v22; // rbx
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 v24; // rcx
  __int64 v25; // rbx
  UCHAR *v26; // rax
  __int64 v27; // rcx
  NTSTATUS v28; // ebx
  SIZE_T v29; // rbx
  int v30; // eax
  __int64 v31; // rcx
  const void *v32; // rax
  __int64 v33; // rcx
  __int64 v34; // rax
  __int64 v35; // rbx
  unsigned int v36; // eax
  __int64 v37; // rcx
  __int64 v38; // rbx
  unsigned int v39; // eax
  __int64 v40; // rcx
  __int64 v41; // rbx
  unsigned int v42; // eax
  __int64 v43; // rcx
  __int64 v44; // rax
  int TlsPeerAddr; // eax
  int v46; // edx
  int v47; // r8d
  const char *v48; // rdx
  __int64 v49; // rax
  __int64 v50; // rax
  int v51; // eax
  int v52; // r8d
  __int64 v53; // rax
  __int64 v54; // rax
  __int64 v55; // rax
  __int64 v56; // rax
  __int64 v57; // rax
  _BYTE *v58; // rcx
  ULONG cbInput; // [rsp+40h] [rbp-91h] BYREF
  PUCHAR pbInputa; // [rsp+48h] [rbp-89h] BYREF
  UCHAR pbOutput[4]; // [rsp+50h] [rbp-81h] BYREF
  BCRYPT_HASH_HANDLE hHash[2]; // [rsp+58h] [rbp-79h] BYREF
  ULONG cbHashObject[4]; // [rsp+68h] [rbp-69h] BYREF
  PUCHAR pbHashObject[2]; // [rsp+78h] [rbp-59h] BYREF
  _WORD v65[2]; // [rsp+88h] [rbp-49h] BYREF
  ULONG pcbResult; // [rsp+8Ch] [rbp-45h] BYREF
  _BYTE v67[16]; // [rsp+90h] [rbp-41h] BYREF
  const char *v68; // [rsp+A0h] [rbp-31h]
  __int64 v69; // [rsp+A8h] [rbp-29h]
  ULONG *p_cbInput; // [rsp+B0h] [rbp-21h]
  __int64 v71; // [rsp+B8h] [rbp-19h]

  pbInputa = 0;
  cbInput = 0;
  v65[0] = 0;
  *(_OWORD *)hHash = 0;
  *(_OWORD *)cbHashObject = 0;
  *(_OWORD *)pbHashObject = 0;
  TraceLogHelper("GetNatHash", 1);
  if ( !a5 )
    a3 += 60;
  if ( (unsigned int)IkeAddrGetIPVersion(a3) && *a6 != 2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      TlsPeerAddr = IkeGetTlsPeerAddr(&WPP_GLOBAL_Control);
      WPP_SF_SsD(*((_QWORD *)WPP_GLOBAL_Control + 2), v46, v47, TlsPeerAddr, (__int64)"GetNatHash", 87);
    }
    if ( gWfpLogUserModeErrors && (byte_180178161 & 1) != 0 )
    {
      cbInput = 87;
      p_cbInput = &cbInput;
      v68 = "GetNatHash";
      v69 = 11;
      v71 = 4;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
        (unsigned int)WFP_USERMODE_ERROR,
        v11,
        3,
        (__int64)v67);
    }
    v12 = -2147024809;
    goto LABEL_11;
  }
  if ( *a6 )
    v17 = L"SHA1";
  else
    v17 = *(const WCHAR **)(a4 + 104);
  *(_DWORD *)pbOutput = 0;
  pcbResult = 0;
  *(_OWORD *)hHash = 0;
  *(_OWORD *)cbHashObject = 0;
  *(_OWORD *)pbHashObject = 0;
  CNGHandleForHashAlgo = (void *)IkeGetCNGHandleForHashAlgo(v17, 0);
  Property = BCryptGetProperty(CNGHandleForHashAlgo, L"ObjectLength", pbOutput, 4u, &pcbResult, dwFlags);
  if ( Property )
  {
    v48 = "BCryptGetProperty";
    goto LABEL_83;
  }
  cbHashObject[2] = *(_DWORD *)pbOutput;
  v22 = *(unsigned int *)pbOutput;
  if ( (Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 0x10) != 0 )
    IsEnabledDeviceUsageNoInline = Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 1;
  else
    IsEnabledDeviceUsageNoInline = Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline();
  if ( IsEnabledDeviceUsageNoInline )
  {
    pbHashObject[0] = (PUCHAR)HeapAlloc(gWfpHeap, 8u, v22);
    if ( pbHashObject[0] )
    {
      v25 = 0;
      if ( gWfpTrackHeapAllocs )
        _InterlockedIncrement(&gWfpNumHeapAllocs);
    }
    else
    {
      v49 = WfpReportSysErrorAsNtStatus(v24, "HeapAlloc", 3221225495LL);
      v25 = v49;
      if ( v49 )
        WfpReportError(v49, "WfpMemAlloc25B");
    }
  }
  else
  {
    v26 = (UCHAR *)HeapAlloc(gWfpHeap, 8u, v22);
    pbHashObject[0] = v26;
    if ( v26 )
    {
      v25 = 0;
      if ( gWfpTrackHeapBytes )
        _InterlockedAdd(&gWfpHeapBytesAllocated, HeapSize(gWfpHeap, 0, v26));
    }
    else
    {
      v50 = WfpReportSysErrorAsNtStatus(v27, "HeapAlloc", 3221225495LL);
      v25 = v50;
      if ( v50 )
        WfpReportError(v50, "WfpMemAlloc");
    }
  }
  if ( !v25 )
  {
    v28 = BCryptGetProperty(CNGHandleForHashAlgo, L"HashDigestLength", pbOutput, 4u, &pcbResult, 0);
    if ( !v28 )
    {
      LODWORD(hHash[1]) = *(_DWORD *)pbOutput;
      v29 = *(unsigned int *)pbOutput;
      if ( (Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 0x10) != 0 )
        v30 = Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 1;
      else
        v30 = Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline();
      if ( v30 )
      {
        *(_QWORD *)cbHashObject = HeapAlloc(gWfpHeap, 8u, v29);
        if ( *(_QWORD *)cbHashObject )
        {
          v25 = 0;
          if ( gWfpTrackHeapAllocs )
            _InterlockedIncrement(&gWfpNumHeapAllocs);
        }
        else
        {
          v53 = WfpReportSysErrorAsNtStatus(v31, "HeapAlloc", 3221225495LL);
          v25 = v53;
          if ( v53 )
            WfpReportError(v53, "WfpMemAlloc25B");
        }
      }
      else
      {
        v32 = HeapAlloc(gWfpHeap, 8u, v29);
        *(_QWORD *)cbHashObject = v32;
        if ( v32 )
        {
          v25 = 0;
          if ( gWfpTrackHeapBytes )
            _InterlockedAdd(&gWfpHeapBytesAllocated, HeapSize(gWfpHeap, 0, v32));
        }
        else
        {
          v54 = WfpReportSysErrorAsNtStatus(v33, "HeapAlloc", 3221225495LL);
          v25 = v54;
          if ( v54 )
            WfpReportError(v54, "WfpMemAlloc");
        }
      }
      if ( v25 )
        goto LABEL_46;
      LODWORD(pbHashObject[1]) = 1;
      Property = BCryptCreateHash(CNGHandleForHashAlgo, hHash, pbHashObject[0], cbHashObject[2], 0, 0, 0);
      if ( !Property )
        goto LABEL_46;
      v48 = "BCryptCreateHash";
LABEL_83:
      v25 = WfpReportSysErrorAsNtStatus(v21, v48, Property);
      goto LABEL_46;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v51 = IkeGetTlsPeerAddr(&WPP_GLOBAL_Control);
      WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, v52, v51, (__int64)"BCryptGetProperty", v28);
    }
    v25 = RtlNtStatusToDosError(v28);
    WfpCallUsermodeErrorUTMacro("BCryptGetProperty", v25);
    if ( (int)v25 > 0 )
      LODWORD(v25) = (unsigned __int16)v25 | 0x80070000;
    v25 = (int)v25;
  }
LABEL_46:
  v34 = IkeReturnError(v25, "IkeHashInitEx");
  v12 = IkeReturnError(v34, "IkeHashInit");
  if ( v12 )
    goto LABEL_11;
  if ( hHash[0] )
  {
    v35 = 0;
    v36 = BCryptHashData(hHash[0], pbInput, 8u, 0);
    if ( !v36 )
      goto LABEL_49;
    v55 = WfpReportSysErrorAsNtStatus(v37, "BCryptHashData", v36);
  }
  else
  {
    v55 = WfpReportSysErrorAsWinError(0, "IkeHashUpdate", 13804, 1);
  }
  v35 = v55;
LABEL_49:
  v12 = IkeReturnError(v35, "IkeHashUpdate");
  if ( v12 )
    goto LABEL_11;
  if ( *a6 == 1 )
    goto LABEL_54;
  if ( hHash[0] )
  {
    v38 = 0;
    v39 = BCryptHashData(hHash[0], a2, 8u, 0);
    if ( !v39 )
      goto LABEL_53;
    v56 = WfpReportSysErrorAsNtStatus(v40, "BCryptHashData", v39);
  }
  else
  {
    v56 = WfpReportSysErrorAsWinError(0, "IkeHashUpdate", 13804, 1);
  }
  v38 = v56;
LABEL_53:
  v12 = IkeReturnError(v38, "IkeHashUpdate");
  if ( v12 )
    goto LABEL_11;
LABEL_54:
  IkeAddrGetAddrBytes(a3, &pbInputa, &cbInput);
  if ( !hHash[0] )
  {
    v57 = WfpReportSysErrorAsWinError(0, "IkeHashUpdate", 13804, 1);
LABEL_92:
    v41 = v57;
    goto LABEL_56;
  }
  v41 = 0;
  v42 = BCryptHashData(hHash[0], pbInputa, cbInput, 0);
  if ( v42 )
  {
    v57 = WfpReportSysErrorAsNtStatus(v43, "BCryptHashData", v42);
    goto LABEL_92;
  }
LABEL_56:
  v12 = IkeReturnError(v41, "IkeHashUpdate");
  if ( !v12 )
  {
    IkeAddrGetPort(a3, v65);
    v12 = IkeHashUpdate(hHash, v65, 2);
    if ( !v12 )
    {
      v12 = IkeHashFinal(hHash);
      if ( !v12 )
      {
        *(_DWORD *)a7 = hHash[1];
        *(_QWORD *)(a7 + 8) = *(_QWORD *)cbHashObject;
      }
    }
  }
LABEL_11:
  if ( hHash[0] )
    BCryptDestroyHash(hHash[0]);
  v13 = pbHashObject[0];
  hHash[0] = 0;
  if ( pbHashObject[0] )
  {
    v14 = cbHashObject[2];
    if ( cbHashObject[2] )
    {
      do
      {
        *v13++ = 0;
        --v14;
      }
      while ( v14 );
    }
    if ( (Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 0x10) != 0 )
      v15 = Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 1;
    else
      v15 = Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline();
    if ( v15 )
    {
      WfpMemFree25B(pbHashObject);
    }
    else
    {
      if ( gWfpTrackHeapBytes && pbHashObject[0] )
        _InterlockedAdd(&gWfpHeapBytesAllocated, -(int)HeapSize(gWfpHeap, 0, pbHashObject[0]));
      HeapFree(gWfpHeap, 0, pbHashObject[0]);
    }
  }
  pbHashObject[0] = 0;
  cbHashObject[2] = 0;
  if ( LODWORD(pbHashObject[1]) )
  {
    v58 = *(_BYTE **)cbHashObject;
    if ( *(_QWORD *)cbHashObject )
    {
      v44 = LODWORD(hHash[1]);
      if ( LODWORD(hHash[1]) )
      {
        do
        {
          *v58++ = 0;
          --v44;
        }
        while ( v44 );
      }
      WfpMemFree((LPCVOID *)cbHashObject);
    }
    *(_QWORD *)cbHashObject = 0;
    LODWORD(hHash[1]) = 0;
  }
  TraceLogHelper("GetNatHash", 0);
  return IkeReturnError(v12, "GetNatHash");
}

```

## disassembly

```asm
0x18000fe50  push    rbp
0x18000fe52  push    rbx
0x18000fe53  push    rsi
0x18000fe54  push    rdi
0x18000fe55  push    r12
0x18000fe57  push    r13
0x18000fe59  push    r14
0x18000fe5b  push    r15
0x18000fe5d  lea     rbp, [rsp-7]
0x18000fe62  sub     rsp, 0D8h
0x18000fe69  mov     rax, cs:__security_cookie
0x18000fe70  xor     rax, rsp
0x18000fe73  mov     [rbp+3Fh+var_50], rax
0x18000fe77  mov     r13, [rbp+3Fh+arg_30]
0x18000fe7b  xorps   xmm0, xmm0
0x18000fe7e  xor     r14d, r14d
0x18000fe81  mov     r12, rdx
0x18000fe84  mov     r15, rcx
0x18000fe87  mov     [rsp+110h+pbInput], r14
0x18000fe8c  mov     edx, 1
0x18000fe91  mov     [rsp+110h+cbInput], r14d
0x18000fe96  lea     rcx, aGetnathash; "GetNatHash"
0x18000fe9d  mov     [rbp+3Fh+var_88], r14w
0x18000fea2  movups  xmmword ptr [rbp+3Fh+hHash], xmm0
0x18000fea6  mov     rbx, r9
0x18000fea9  mov     rsi, r8
0x18000feac  movups  xmmword ptr [rbp+3Fh+cbHashObject], xmm0
0x18000feb0  movups  xmmword ptr [rbp+3Fh+pbHashObject], xmm0
0x18000feb4  call    TraceLogHelper
0x18000feb9  cmp     [rbp+3Fh+arg_20], r14d
0x18000febd  lea     rax, [rsi+3Ch]
0x18000fec1  cmovz   rsi, rax
0x18000fec5  mov     rcx, rsi
0x18000fec8  call    IkeAddrGetIPVersion
0x18000fecd  mov     rdi, [rbp+3Fh+arg_28]
0x18000fed1  test    eax, eax
0x18000fed3  jz      loc_18000FFF9
0x18000fed9  cmp     dword ptr [rdi], 2
0x18000fedc  jz      loc_18000FFF9
0x18000fee2  mov     rax, cs:WPP_GLOBAL_Control
0x18000fee9  lea     rcx, WPP_GLOBAL_Control
0x18000fef0  cmp     rax, rcx
0x18000fef3  jz      short loc_18000FEFF
0x18000fef5  cmp     byte ptr [rax+19h], 2
0x18000fef9  jnb     loc_180010323
0x18000feff  lea     rdi, aGetnathash; "GetNatHash"
0x18000ff06  cmp     cs:gWfpLogUserModeErrors, r14d
0x18000ff0d  jz      short loc_18000FF5F
0x18000ff0f  test    cs:byte_180178161, 1
0x18000ff16  jz      short loc_18000FF5F
0x18000ff18  lea     rax, [rsp+110h+cbInput]
0x18000ff1d  mov     [rsp+110h+cbInput], 57h ; 'W'
0x18000ff25  mov     [rbp+3Fh+var_60], rax
0x18000ff29  lea     rdx, WFP_USERMODE_ERROR
0x18000ff30  lea     rax, [rbp+3Fh+var_80]
0x18000ff34  mov     [rbp+3Fh+var_70], rdi
0x18000ff38  mov     r9d, 3
0x18000ff3e  mov     [rsp+110h+pcbResult], rax
0x18000ff43  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x18000ff4a  mov     [rbp+3Fh+var_68], 0Bh
0x18000ff52  mov     [rbp+3Fh+var_58], 4
0x18000ff5a  call    McGenEventWrite_EtwEventWriteTransfer
0x18000ff5f  mov     rbx, 0FFFFFFFF80070057h
0x18000ff66  mov     rcx, [rbp+3Fh+hHash]; hHash
0x18000ff6a  test    rcx, rcx
0x18000ff6d  jz      short loc_18000FF75
0x18000ff6f  call    cs:__imp_BCryptDestroyHash
0x18000ff75  mov     rax, [rbp+3Fh+pbHashObject]
0x18000ff79  mov     [rbp+3Fh+hHash], r14
0x18000ff7d  test    rax, rax
0x18000ff80  jz      short loc_18000FFB2
0x18000ff82  mov     ecx, [rbp+3Fh+cbHashObject+8]
0x18000ff85  test    rcx, rcx
0x18000ff88  jnz     loc_1800105F9
0x18000ff8e  mov     eax, cs:Feature_BFE_MemAlloc_BugFixes_25B__private_featureState
0x18000ff94  test    al, 10h
0x18000ff96  jnz     loc_18001060B
0x18000ff9c  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline
0x18000ffa1  test    eax, eax
0x18000ffa3  jz      loc_180010613
0x18000ffa9  lea     rcx, [rbp+3Fh+pbHashObject]
0x18000ffad  call    WfpMemFree25B
0x18000ffb2  cmp     dword ptr [rbp+3Fh+pbHashObject+8], 0
0x18000ffb6  mov     [rbp+3Fh+pbHashObject], r14
0x18000ffba  mov     [rbp+3Fh+cbHashObject+8], r14d
0x18000ffbe  jnz     loc_180010655
0x18000ffc4  xor     edx, edx
0x18000ffc6  mov     rcx, rdi
0x18000ffc9  call    TraceLogHelper
0x18000ffce  mov     rdx, rdi
0x18000ffd1  mov     rcx, rbx
0x18000ffd4  call    IkeReturnError
0x18000ffd9  mov     rcx, [rbp+3Fh+var_50]
0x18000ffdd  xor     rcx, rsp; StackCookie
0x18000ffe0  call    __security_check_cookie
0x18000ffe5  add     rsp, 0D8h
0x18000ffec  pop     r15
0x18000ffee  pop     r14
0x18000fff0  pop     r13
0x18000fff2  pop     r12
0x18000fff4  pop     rdi
0x18000fff5  pop     rsi
0x18000fff6  pop     rbx
0x18000fff7  pop     rbp
0x18000fff8  retn
0x18000fff9  cmp     [rdi], r14d
0x18000fffc  jnz     loc_1800102D1
0x180010002  mov     rcx, [rbx+68h]
0x180010006  xorps   xmm0, xmm0
0x180010009  mov     dword ptr [rsp+110h+pbOutput], r14d
0x18001000e  xor     edx, edx
0x180010010  mov     [rbp+3Fh+var_84], r14d
0x180010014  movups  xmmword ptr [rbp+3Fh+hHash], xmm0
0x180010018  movups  xmmword ptr [rbp+3Fh+cbHashObject], xmm0
0x18001001c  movups  xmmword ptr [rbp+3Fh+pbHashObject], xmm0
0x180010020  call    IkeGetCNGHandleForHashAlgo
0x180010025  mov     r14, rax
0x180010028  mov     [rsp+110h+dwFlags], edx; dwFlags
0x18001002c  lea     rax, [rbp+3Fh+var_84]
0x180010030  mov     rcx, r14; hObject
0x180010033  mov     r9d, 4; cbOutput
0x180010039  mov     [rsp+110h+pcbResult], rax; pcbResult
0x18001003e  lea     r8, [rsp+110h+pbOutput]; pbOutput
0x180010043  lea     rdx, pszProperty; "ObjectLength"
0x18001004a  call    cs:__imp_BCryptGetProperty
0x180010050  test    eax, eax
0x180010052  jnz     loc_18001035E
0x180010058  mov     eax, dword ptr [rsp+110h+pbOutput]
0x18001005c  mov     [rbp+3Fh+cbHashObject+8], eax
0x18001005f  mov     ebx, eax
0x180010061  mov     eax, cs:Feature_BFE_MemAlloc_BugFixes_25B__private_featureState
0x180010067  test    al, 10h
0x180010069  jnz     loc_18001036A
0x18001006f  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline
0x180010074  mov     rcx, cs:gWfpHeap; hHeap
0x18001007b  mov     r8, rbx; dwBytes
0x18001007e  mov     edx, 8; dwFlags
0x180010083  test    eax, eax
0x180010085  jz      short loc_1800100AD
0x180010087  call    cs:__imp_HeapAlloc
0x18001008d  mov     [rbp+3Fh+pbHashObject], rax
0x180010091  test    rax, rax
0x180010094  jz      loc_180010372
0x18001009a  xor     ebx, ebx
0x18001009c  cmp     cs:gWfpTrackHeapAllocs, ebx
0x1800100a2  jz      short loc_1800100CE
0x1800100a4  lock inc cs:gWfpNumHeapAllocs
0x1800100ab  jmp     short loc_1800100CE
0x1800100ad  call    cs:__imp_HeapAlloc
0x1800100b3  mov     [rbp+3Fh+pbHashObject], rax
0x1800100b7  test    rax, rax
0x1800100ba  jz      loc_1800103A4
0x1800100c0  xor     ebx, ebx
0x1800100c2  cmp     cs:gWfpTrackHeapBytes, ebx
0x1800100c8  jnz     loc_1800103D6
0x1800100ce  test    rbx, rbx
0x1800100d1  jnz     loc_1800101B5
0x1800100d7  lea     rax, [rbp+3Fh+var_84]
0x1800100db  mov     [rsp+110h+dwFlags], ebx; dwFlags
0x1800100df  mov     r9d, 4; cbOutput
0x1800100e5  mov     [rsp+110h+pcbResult], rax; pcbResult
0x1800100ea  lea     r8, [rsp+110h+pbOutput]; pbOutput
0x1800100ef  mov     rcx, r14; hObject
0x1800100f2  lea     rdx, aHashdigestleng; "HashDigestLength"
0x1800100f9  call    cs:__imp_BCryptGetProperty
0x1800100ff  mov     ebx, eax
0x180010101  test    eax, eax
0x180010103  jnz     loc_1800103F4
0x180010109  mov     eax, dword ptr [rsp+110h+pbOutput]
0x18001010d  mov     dword ptr [rbp+3Fh+hHash+8], eax
0x180010110  mov     ebx, eax
0x180010112  mov     eax, cs:Feature_BFE_MemAlloc_BugFixes_25B__private_featureState
0x180010118  test    al, 10h
0x18001011a  jnz     loc_18001045F
0x180010120  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline
0x180010125  mov     rcx, cs:gWfpHeap; hHeap
0x18001012c  mov     r8, rbx; dwBytes
0x18001012f  mov     edx, 8; dwFlags
0x180010134  test    eax, eax
0x180010136  jz      short loc_18001015E
0x180010138  call    cs:__imp_HeapAlloc
0x18001013e  mov     qword ptr [rbp+3Fh+cbHashObject], rax
0x180010142  test    rax, rax
0x180010145  jz      loc_180010467
0x18001014b  xor     ebx, ebx
0x18001014d  cmp     cs:gWfpTrackHeapAllocs, ebx
0x180010153  jz      short loc_18001017F
0x180010155  lock inc cs:gWfpNumHeapAllocs
0x18001015c  jmp     short loc_18001017F
0x18001015e  call    cs:__imp_HeapAlloc
0x180010164  mov     qword ptr [rbp+3Fh+cbHashObject], rax
0x180010168  test    rax, rax
0x18001016b  jz      loc_180010499
0x180010171  xor     ebx, ebx
0x180010173  cmp     cs:gWfpTrackHeapBytes, ebx
0x180010179  jnz     loc_1800104CB
0x18001017f  test    rbx, rbx
0x180010182  jnz     short loc_1800101B5
0x180010184  mov     r9d, [rbp+3Fh+cbHashObject+8]; cbHashObject
0x180010188  lea     rdx, [rbp+3Fh+hHash]; phHash
0x18001018c  mov     r8, [rbp+3Fh+pbHashObject]; pbHashObject
0x180010190  mov     rcx, r14; hAlgorithm
0x180010193  mov     [rsp+110h+var_E0], ebx; dwFlags
0x180010197  mov     [rsp+110h+dwFlags], ebx; cbSecret
0x18001019b  mov     [rsp+110h+pcbResult], rbx; pbSecret
0x1800101a0  mov     dword ptr [rbp+3Fh+pbHashObject+8], 1
0x1800101a7  call    cs:__imp_BCryptCreateHash
0x1800101ad  test    eax, eax
0x1800101af  jnz     loc_1800104E9
0x1800101b5  lea     rdx, aIkehashinitex; "IkeHashInitEx"
0x1800101bc  mov     rcx, rbx
0x1800101bf  call    IkeReturnError
0x1800101c4  lea     rdx, aIkehashinit; "IkeHashInit"
0x1800101cb  mov     rcx, rax
0x1800101ce  call    IkeReturnError
0x1800101d3  mov     rbx, rax
0x1800101d6  test    rax, rax
0x1800101d9  jnz     loc_1800105F1
0x1800101df  mov     rcx, [rbp+3Fh+hHash]; hHash
0x1800101e3  test    rcx, rcx
0x1800101e6  jz      loc_180010500
0x1800101ec  xor     r14d, r14d
0x1800101ef  xor     r9d, r9d; dwFlags
0x1800101f2  mov     r8d, 8; cbInput
0x1800101f8  mov     rdx, r15; pbInput
0x1800101fb  mov     ebx, r14d
0x1800101fe  call    cs:__imp_BCryptHashData
0x180010204  test    eax, eax
0x180010206  jnz     loc_18001051D
0x18001020c  lea     rdx, aIkehashupdate; "IkeHashUpdate"
0x180010213  mov     rcx, rbx
0x180010216  call    IkeReturnError
0x18001021b  mov     rbx, rax
0x18001021e  test    rax, rax
0x180010221  jnz     loc_1800102C5
0x180010227  cmp     dword ptr [rdi], 1
0x18001022a  jz      short loc_18001026D
0x18001022c  mov     rcx, [rbp+3Fh+hHash]; hHash
0x180010230  test    rcx, rcx
0x180010233  jz      loc_180010534
0x180010239  xor     r9d, r9d; dwFlags
0x18001023c  mov     r8d, 8; cbInput
0x180010242  mov     rdx, r12; pbInput
0x180010245  mov     rbx, r14
0x180010248  call    cs:__imp_BCryptHashData
0x18001024e  test    eax, eax
0x180010250  jnz     loc_18001054E
0x180010256  lea     rdx, aIkehashupdate; "IkeHashUpdate"
0x18001025d  mov     rcx, rbx
0x180010260  call    IkeReturnError
0x180010265  mov     rbx, rax
0x180010268  test    rax, rax
0x18001026b  jnz     short loc_1800102C5
0x18001026d  lea     r8, [rsp+110h+cbInput]
0x180010272  mov     rcx, rsi
0x180010275  lea     rdx, [rsp+110h+pbInput]
0x18001027a  call    IkeAddrGetAddrBytes
0x18001027f  mov     rcx, [rbp+3Fh+hHash]; hHash
0x180010283  test    rcx, rcx
0x180010286  jz      loc_180010565
0x18001028c  mov     r8d, [rsp+110h+cbInput]; cbInput
0x180010291  xor     r9d, r9d; dwFlags
0x180010294  mov     rdx, [rsp+110h+pbInput]; pbInput
0x180010299  mov     rbx, r14
0x18001029c  call    cs:__imp_BCryptHashData
0x1800102a2  test    eax, eax
0x1800102a4  jnz     loc_18001057F
0x1800102aa  lea     rdx, aIkehashupdate; "IkeHashUpdate"
0x1800102b1  mov     rcx, rbx
0x1800102b4  call    IkeReturnError
0x1800102b9  mov     rbx, rax
0x1800102bc  test    rax, rax
0x1800102bf  jz      loc_180010596
0x1800102c5  lea     rdi, aGetnathash; "GetNatHash"
0x1800102cc  jmp     loc_18000FF66
0x1800102d1  lea     rcx, aSha1; "SHA1"
0x1800102d8  jmp     loc_180010006
0x1800102dd  mov     ecx, ebx; Status
0x1800102df  call    cs:__imp_RtlNtStatusToDosError
0x1800102e5  mov     edx, eax
0x1800102e7  mov     rcx, r14
0x1800102ea  mov     ebx, eax
0x1800102ec  call    WfpCallUsermodeErrorUTMacro
0x1800102f1  test    ebx, ebx
0x1800102f3  jg      loc_180010451
0x1800102f9  movsxd  rbx, ebx
0x1800102fc  jmp     loc_1800101B5
0x180010301  mov     eax, dword ptr [rbp+3Fh+hHash+8]
0x180010304  test    rax, rax
0x180010307  jnz     loc_180010667
0x18001030d  lea     rcx, [rbp+3Fh+cbHashObject]
0x180010311  call    WfpMemFree
0x180010316  mov     qword ptr [rbp+3Fh+cbHashObject], r14
0x18001031a  mov     dword ptr [rbp+3Fh+hHash+8], r14d
0x18001031e  jmp     loc_18000FFC4
0x180010323  test    byte ptr [rax+1Ch], 1
0x180010327  jz      loc_18000FEFF
0x18001032d  call    IkeGetTlsPeerAddr
0x180010332  mov     rcx, cs:WPP_GLOBAL_Control
0x180010339  lea     rdi, aGetnathash; "GetNatHash"
  ... truncated ...
```
