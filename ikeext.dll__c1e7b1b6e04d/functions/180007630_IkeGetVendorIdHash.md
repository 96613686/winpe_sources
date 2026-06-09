# IkeGetVendorIdHash

- ea: `0x180007630`
- end: `0x180007d93`
- name: `IkeGetVendorIdHash`
- size: `1891`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `14`
- tags: `loader_planting, installer_update`

## callers

- `0x18001fc40`
- `0x1800fcf30`
- `0x1800fd86c`

## callees

- `0x1800037c4`
- `0x1800061ec`
- `0x180007630`
- `0x180008388`
- `0x180008480`
- `0x180010db0`
- `0x180011350`
- `0x180016534`
- `0x18004882c`
- `0x18004890c`
- `0x18004aa3c`
- `0x18004ce90`
- `0x180050850`
- `0x1800529a4`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180007a29`
- `ntdll!RtlNtStatusToDosError` at `0x180007a29`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180007b10`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180007c05`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180007cc9`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180007d48`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180007b10`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180007c05`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180007cc9`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180007d48`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007ce5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007d64`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007ce5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007d64`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007709`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007798`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007913`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007941`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007709`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007798`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007913`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007941`
- `ncrypt!BCryptDestroyHash` at `0x18000787e`
- `ncrypt!BCryptDestroyHash` at `0x1800079a5`
- `ncrypt!BCryptDestroyHash` at `0x18000787e`
- `ncrypt!BCryptDestroyHash` at `0x1800079a5`
- `ncrypt!BCryptCreateHash` at `0x1800077e4`
- `ncrypt!BCryptCreateHash` at `0x1800077e4`
- `ncrypt!BCryptGetProperty` at `0x1800076c9`
- `ncrypt!BCryptGetProperty` at `0x180007756`
- `ncrypt!BCryptGetProperty` at `0x1800076c9`
- `ncrypt!BCryptGetProperty` at `0x180007756`
- `ncrypt!BCryptHashData` at `0x18000784c`
- `ncrypt!BCryptHashData` at `0x18000784c`
- `ncrypt!BCryptFinishHash` at `0x180007987`
- `ncrypt!BCryptFinishHash` at `0x180007987`

## string_xrefs

- `0x18000785a`: `IkeHashUpdate`
- `0x180007c34`: `IkeHashUpdate`
- `0x180007c17`: `BCryptCreateHash`

## pseudocode

```c
__int64 __fastcall IkeGetVendorIdHash(int a1, __int64 a2)
{
  __int64 v2; // rsi
  void *CNGHandleForHashAlgo; // rdi
  unsigned int Property; // eax
  __int64 v6; // rcx
  SIZE_T v7; // rbx
  int IsEnabledDeviceUsageNoInline; // eax
  UCHAR *v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rbx
  NTSTATUS v12; // ebx
  SIZE_T v13; // rbx
  int v14; // eax
  const void *v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rbx
  __int64 v19; // r8
  UCHAR *v20; // rdx
  __int64 v21; // rbx
  unsigned int v22; // eax
  __int64 v23; // rcx
  PUCHAR v24; // rax
  __int64 v25; // rcx
  int v26; // eax
  __int64 v28; // rcx
  __int64 v29; // rcx
  unsigned int v30; // eax
  __int64 v31; // rcx
  __int64 v32; // rbx
  PUCHAR v33; // rax
  __int64 v34; // rcx
  int v35; // eax
  __int64 v36; // rcx
  __int64 v37; // rcx
  const char *v38; // rdx
  __int64 v39; // rax
  __int64 v40; // rax
  int TlsPeerAddr; // eax
  int v42; // r8d
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rax
  _BYTE *v46; // rax
  _BYTE *v47; // rax
  UCHAR pbOutput[4]; // [rsp+40h] [rbp-19h] BYREF
  BCRYPT_HASH_HANDLE phHash[2]; // [rsp+48h] [rbp-11h] BYREF
  ULONG cbHashObject[4]; // [rsp+58h] [rbp-1h] BYREF
  PUCHAR pbHashObject[2]; // [rsp+68h] [rbp+Fh] BYREF
  ULONG pcbResult; // [rsp+78h] [rbp+1Fh] BYREF

  v2 = a1;
  TraceLogHelper("IkeGetVendorIdHash", 1);
  *(_OWORD *)phHash = 0;
  *(_DWORD *)pbOutput = 0;
  *(_OWORD *)cbHashObject = 0;
  pcbResult = 0;
  *(_OWORD *)pbHashObject = 0;
  CNGHandleForHashAlgo = (void *)IkeGetCNGHandleForHashAlgo(L"MD5", 0);
  Property = BCryptGetProperty(CNGHandleForHashAlgo, L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
  if ( Property )
  {
    v38 = "BCryptGetProperty";
    goto LABEL_78;
  }
  cbHashObject[2] = *(_DWORD *)pbOutput;
  v7 = *(unsigned int *)pbOutput;
  if ( (Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 0x10) != 0 )
    IsEnabledDeviceUsageNoInline = Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 1;
  else
    IsEnabledDeviceUsageNoInline = Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline();
  if ( IsEnabledDeviceUsageNoInline )
  {
    pbHashObject[0] = (PUCHAR)HeapAlloc(gWfpHeap, 8u, v7);
    if ( pbHashObject[0] )
    {
      v11 = 0;
      if ( gWfpTrackHeapAllocs )
        _InterlockedIncrement(&gWfpNumHeapAllocs);
    }
    else
    {
      v39 = WfpReportSysErrorAsNtStatus(v28, "HeapAlloc", 3221225495LL);
      v11 = v39;
      if ( v39 )
        WfpReportError(v39, "WfpMemAlloc25B");
    }
  }
  else
  {
    v9 = (UCHAR *)HeapAlloc(gWfpHeap, 8u, v7);
    pbHashObject[0] = v9;
    if ( v9 )
    {
      v11 = 0;
      if ( gWfpTrackHeapBytes )
        _InterlockedAdd(&gWfpHeapBytesAllocated, HeapSize(gWfpHeap, 0, v9));
    }
    else
    {
      v40 = WfpReportSysErrorAsNtStatus(v10, "HeapAlloc", 3221225495LL);
      v11 = v40;
      if ( v40 )
        WfpReportError(v40, "WfpMemAlloc");
    }
  }
  if ( !v11 )
  {
    v12 = BCryptGetProperty(CNGHandleForHashAlgo, L"HashDigestLength", pbOutput, 4u, &pcbResult, 0);
    if ( !v12 )
    {
      LODWORD(phHash[1]) = *(_DWORD *)pbOutput;
      v13 = *(unsigned int *)pbOutput;
      if ( (Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 0x10) != 0 )
        v14 = Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 1;
      else
        v14 = Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline();
      if ( v14 )
      {
        *(_QWORD *)cbHashObject = HeapAlloc(gWfpHeap, 8u, v13);
        if ( *(_QWORD *)cbHashObject )
        {
          v11 = 0;
          if ( gWfpTrackHeapAllocs )
            _InterlockedIncrement(&gWfpNumHeapAllocs);
        }
        else
        {
          v43 = WfpReportSysErrorAsNtStatus(v29, "HeapAlloc", 3221225495LL);
          v11 = v43;
          if ( v43 )
            WfpReportError(v43, "WfpMemAlloc25B");
        }
      }
      else
      {
        v15 = HeapAlloc(gWfpHeap, 8u, v13);
        *(_QWORD *)cbHashObject = v15;
        if ( v15 )
        {
          v11 = 0;
          if ( gWfpTrackHeapBytes )
            _InterlockedAdd(&gWfpHeapBytesAllocated, HeapSize(gWfpHeap, 0, v15));
        }
        else
        {
          v44 = WfpReportSysErrorAsNtStatus(v16, "HeapAlloc", 3221225495LL);
          v11 = v44;
          if ( v44 )
            WfpReportError(v44, "WfpMemAlloc");
        }
      }
      if ( v11 )
        goto LABEL_18;
      LODWORD(pbHashObject[1]) = 1;
      Property = BCryptCreateHash(CNGHandleForHashAlgo, phHash, pbHashObject[0], cbHashObject[2], 0, 0, 0);
      if ( !Property )
        goto LABEL_18;
      v38 = "BCryptCreateHash";
LABEL_78:
      v11 = WfpReportSysErrorAsNtStatus(v6, v38, Property);
      goto LABEL_18;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      TlsPeerAddr = IkeGetTlsPeerAddr(&WPP_GLOBAL_Control);
      WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, v42, TlsPeerAddr, (__int64)"BCryptGetProperty", v12);
    }
    LODWORD(v11) = RtlNtStatusToDosError(v12);
    WfpCallUsermodeErrorUTMacro("BCryptGetProperty", (unsigned int)v11);
    if ( (int)v11 > 0 )
      LODWORD(v11) = (unsigned __int16)v11 | 0x80070000;
    v11 = (int)v11;
  }
LABEL_18:
  v17 = IkeReturnError(v11, "IkeHashInitEx");
  v18 = IkeReturnError(v17, "IkeHashInit");
  if ( v18 )
    goto LABEL_24;
  v19 = -1;
  v20 = (UCHAR *)(&off_18011A068)[3 * v2];
  do
    ++v19;
  while ( v20[v19] );
  if ( phHash[0] )
  {
    v21 = 0;
    v22 = BCryptHashData(phHash[0], v20, v19, 0);
    if ( !v22 )
      goto LABEL_23;
    v45 = WfpReportSysErrorAsNtStatus(v23, "BCryptHashData", v22);
  }
  else
  {
    v45 = WfpReportSysErrorAsWinError(0, "IkeHashUpdate", 13804, 1);
  }
  v21 = v45;
LABEL_23:
  v18 = IkeReturnError(v21, "IkeHashUpdate");
  if ( !v18 )
  {
    if ( phHash[0] )
    {
      v30 = BCryptFinishHash(phHash[0], *(PUCHAR *)cbHashObject, (ULONG)phHash[1], 0);
      if ( v30 )
      {
        v32 = WfpReportSysErrorAsNtStatus(v31, "BCryptFinishHash", v30);
      }
      else
      {
        v32 = 0;
        LODWORD(pbHashObject[1]) = 0;
        if ( phHash[0] )
          BCryptDestroyHash(phHash[0]);
        v33 = pbHashObject[0];
        phHash[0] = 0;
        if ( pbHashObject[0] )
        {
          v34 = cbHashObject[2];
          if ( cbHashObject[2] )
          {
            do
            {
              *v33++ = 0;
              --v34;
            }
            while ( v34 );
          }
          if ( (Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 0x10) != 0 )
            v35 = Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 1;
          else
            v35 = Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline();
          if ( v35 )
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
          v46 = *(_BYTE **)cbHashObject;
          if ( *(_QWORD *)cbHashObject )
          {
            v36 = LODWORD(phHash[1]);
            if ( LODWORD(phHash[1]) )
            {
              do
              {
                *v46++ = 0;
                --v36;
              }
              while ( v36 );
            }
            WfpMemFree((LPCVOID *)cbHashObject);
          }
          *(_QWORD *)cbHashObject = 0;
          LODWORD(phHash[1]) = 0;
        }
      }
    }
    else
    {
      v32 = WfpReportSysErrorAsWinError(0, "IkeHashFinal", 13804, 1);
    }
    v18 = IkeReturnError(v32, "IkeHashFinal");
    if ( !v18 )
    {
      *(_QWORD *)(a2 + 8) = *(_QWORD *)cbHashObject;
      *(_DWORD *)a2 = phHash[1];
    }
  }
LABEL_24:
  if ( phHash[0] )
    BCryptDestroyHash(phHash[0]);
  v24 = pbHashObject[0];
  phHash[0] = 0;
  if ( pbHashObject[0] )
  {
    v25 = cbHashObject[2];
    if ( cbHashObject[2] )
    {
      do
      {
        *v24++ = 0;
        --v25;
      }
      while ( v25 );
    }
    if ( (Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 0x10) != 0 )
      v26 = Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 1;
    else
      v26 = Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline();
    if ( v26 )
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
    v47 = *(_BYTE **)cbHashObject;
    if ( *(_QWORD *)cbHashObject )
    {
      v37 = LODWORD(phHash[1]);
      if ( LODWORD(phHash[1]) )
      {
        do
        {
          *v47++ = 0;
          --v37;
        }
        while ( v37 );
      }
      WfpMemFree((LPCVOID *)cbHashObject);
    }
    *(_QWORD *)cbHashObject = 0;
    LODWORD(phHash[1]) = 0;
  }
  TraceLogHelper("IkeGetVendorIdHash", 0);
  return IkeReturnError(v18, "IkeGetVendorIdHash");
}

```

## disassembly

```asm
0x180007630  mov     [rsp-8+arg_10], rbx
0x180007635  push    rbp
0x180007636  push    rsi
0x180007637  push    rdi
0x180007638  push    r14
0x18000763a  push    r15
0x18000763c  lea     rbp, [rsp-37h]
0x180007641  sub     rsp, 90h
0x180007648  mov     rax, cs:__security_cookie
0x18000764f  xor     rax, rsp
0x180007652  mov     [rbp+57h+var_30], rax
0x180007656  xorps   xmm0, xmm0
0x180007659  movsxd  rsi, ecx
0x18000765c  mov     r14, rdx
0x18000765f  lea     rcx, aIkegetvendorid; "IkeGetVendorIdHash"
0x180007666  mov     edx, 1
0x18000766b  movups  xmmword ptr [rbp+57h+phHash], xmm0
0x18000766f  movups  xmmword ptr [rbp+57h+cbHashObject], xmm0
0x180007673  movups  xmmword ptr [rbp+57h+pbHashObject], xmm0
0x180007677  call    TraceLogHelper
0x18000767c  xorps   xmm0, xmm0
0x18000767f  lea     rcx, aMd5; "MD5"
0x180007686  xor     r15d, r15d
0x180007689  xor     edx, edx
0x18000768b  movups  xmmword ptr [rbp+57h+phHash], xmm0
0x18000768f  mov     dword ptr [rbp+57h+pbOutput], r15d
0x180007693  movups  xmmword ptr [rbp+57h+cbHashObject], xmm0
0x180007697  mov     [rbp+57h+var_38], r15d
0x18000769b  movups  xmmword ptr [rbp+57h+pbHashObject], xmm0
0x18000769f  call    IkeGetCNGHandleForHashAlgo
0x1800076a4  mov     rdi, rax
0x1800076a7  mov     [rsp+0B0h+dwFlags], r15d; dwFlags
0x1800076ac  lea     rax, [rbp+57h+var_38]
0x1800076b0  mov     rcx, rdi; hObject
0x1800076b3  mov     r9d, 4; cbOutput
0x1800076b9  mov     [rsp+0B0h+pcbResult], rax; pcbResult
0x1800076be  lea     r8, [rbp+57h+pbOutput]; pbOutput
0x1800076c2  lea     rdx, pszProperty; "ObjectLength"
0x1800076c9  call    cs:__imp_BCryptGetProperty
0x1800076cf  test    eax, eax
0x1800076d1  jnz     loc_180007A8C
0x1800076d7  mov     eax, dword ptr [rbp+57h+pbOutput]
0x1800076da  mov     [rbp+57h+cbHashObject+8], eax
0x1800076dd  mov     ebx, eax
0x1800076df  mov     eax, cs:Feature_BFE_MemAlloc_BugFixes_25B__private_featureState
0x1800076e5  test    al, 10h
0x1800076e7  jnz     loc_180007A98
0x1800076ed  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline
0x1800076f2  mov     rcx, cs:gWfpHeap; hHeap
0x1800076f9  mov     r8, rbx; dwBytes
0x1800076fc  mov     edx, 8; dwFlags
0x180007701  test    eax, eax
0x180007703  jnz     loc_180007913
0x180007709  call    cs:__imp_HeapAlloc
0x18000770f  mov     [rbp+57h+pbHashObject], rax
0x180007713  test    rax, rax
0x180007716  jz      loc_180007AD2
0x18000771c  mov     rbx, r15
0x18000771f  cmp     cs:gWfpTrackHeapBytes, ebx
0x180007725  jnz     loc_180007B04
0x18000772b  test    rbx, rbx
0x18000772e  jnz     loc_1800077F2
0x180007734  lea     rax, [rbp+57h+var_38]
0x180007738  mov     [rsp+0B0h+dwFlags], r15d; dwFlags
0x18000773d  mov     r9d, 4; cbOutput
0x180007743  mov     [rsp+0B0h+pcbResult], rax; pcbResult
0x180007748  lea     r8, [rbp+57h+pbOutput]; pbOutput
0x18000774c  mov     rcx, rdi; hObject
0x18000774f  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180007756  call    cs:__imp_BCryptGetProperty
0x18000775c  mov     ebx, eax
0x18000775e  test    eax, eax
0x180007760  jnz     loc_180007B22
0x180007766  mov     eax, dword ptr [rbp+57h+pbOutput]
0x180007769  mov     dword ptr [rbp+57h+phHash+8], eax
0x18000776c  mov     ebx, eax
0x18000776e  mov     eax, cs:Feature_BFE_MemAlloc_BugFixes_25B__private_featureState
0x180007774  test    al, 10h
0x180007776  jnz     loc_180007B8D
0x18000777c  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline
0x180007781  mov     rcx, cs:gWfpHeap; hHeap
0x180007788  mov     r8, rbx; dwBytes
0x18000778b  mov     edx, 8; dwFlags
0x180007790  test    eax, eax
0x180007792  jnz     loc_180007941
0x180007798  call    cs:__imp_HeapAlloc
0x18000779e  mov     qword ptr [rbp+57h+cbHashObject], rax
0x1800077a2  test    rax, rax
0x1800077a5  jz      loc_180007BC7
0x1800077ab  mov     rbx, r15
0x1800077ae  cmp     cs:gWfpTrackHeapBytes, ebx
0x1800077b4  jnz     loc_180007BF9
0x1800077ba  test    rbx, rbx
0x1800077bd  jnz     short loc_1800077F2
0x1800077bf  mov     r9d, [rbp+57h+cbHashObject+8]; cbHashObject
0x1800077c3  lea     rdx, [rbp+57h+phHash]; phHash
0x1800077c7  mov     r8, [rbp+57h+pbHashObject]; pbHashObject
0x1800077cb  mov     rcx, rdi; hAlgorithm
0x1800077ce  mov     [rsp+0B0h+var_80], r15d; dwFlags
0x1800077d3  mov     [rsp+0B0h+dwFlags], r15d; cbSecret
0x1800077d8  mov     [rsp+0B0h+pcbResult], r15; pbSecret
0x1800077dd  mov     dword ptr [rbp+57h+pbHashObject+8], 1
0x1800077e4  call    cs:__imp_BCryptCreateHash
0x1800077ea  test    eax, eax
0x1800077ec  jnz     loc_180007C17
0x1800077f2  lea     rdx, aIkehashinitex; "IkeHashInitEx"
0x1800077f9  mov     rcx, rbx
0x1800077fc  call    IkeReturnError
0x180007801  lea     rdx, aIkehashinit; "IkeHashInit"
0x180007808  mov     rcx, rax
0x18000780b  call    IkeReturnError
0x180007810  mov     rbx, rax
0x180007813  test    rax, rax
0x180007816  jnz     short loc_180007875
0x180007818  lea     rcx, [rsi+rsi*2]
0x18000781c  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180007823  lea     rdx, off_18011A068; "MS NT5 ISAKMPOAKLEY"
0x18000782a  mov     rdx, [rdx+rcx*8]; pbInput
0x18000782e  xchg    ax, ax
0x180007830  inc     r8; cbInput
0x180007833  cmp     [rdx+r8], r15b
0x180007837  jnz     short loc_180007830
0x180007839  mov     rcx, [rbp+57h+phHash]; hHash
0x18000783d  test    rcx, rcx
0x180007840  jz      loc_180007C2E
0x180007846  xor     r9d, r9d; dwFlags
0x180007849  mov     rbx, r15
0x18000784c  call    cs:__imp_BCryptHashData
0x180007852  test    eax, eax
0x180007854  jnz     loc_180007C48
0x18000785a  lea     rdx, aIkehashupdate; "IkeHashUpdate"
0x180007861  mov     rcx, rbx
0x180007864  call    IkeReturnError
0x180007869  mov     rbx, rax
0x18000786c  test    rax, rax
0x18000786f  jz      loc_18000796F
0x180007875  mov     rcx, [rbp+57h+phHash]; hHash
0x180007879  test    rcx, rcx
0x18000787c  jz      short loc_180007884
0x18000787e  call    cs:__imp_BCryptDestroyHash
0x180007884  mov     rax, [rbp+57h+pbHashObject]
0x180007888  mov     [rbp+57h+phHash], r15
0x18000788c  test    rax, rax
0x18000788f  jz      short loc_1800078C1
0x180007891  mov     ecx, [rbp+57h+cbHashObject+8]
0x180007894  test    rcx, rcx
0x180007897  jnz     loc_180007D13
0x18000789d  mov     eax, cs:Feature_BFE_MemAlloc_BugFixes_25B__private_featureState
0x1800078a3  test    al, 10h
0x1800078a5  jnz     loc_180007D25
0x1800078ab  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline
0x1800078b0  test    eax, eax
0x1800078b2  jz      loc_180007D2D
0x1800078b8  lea     rcx, [rbp+57h+pbHashObject]
0x1800078bc  call    WfpMemFree25B
0x1800078c1  mov     [rbp+57h+pbHashObject], r15
0x1800078c5  mov     [rbp+57h+cbHashObject+8], r15d
0x1800078c9  cmp     dword ptr [rbp+57h+pbHashObject+8], r15d
0x1800078cd  jnz     loc_180007D6F
0x1800078d3  xor     edx, edx
0x1800078d5  lea     rcx, aIkegetvendorid; "IkeGetVendorIdHash"
0x1800078dc  call    TraceLogHelper
0x1800078e1  lea     rdx, aIkegetvendorid; "IkeGetVendorIdHash"
0x1800078e8  mov     rcx, rbx
0x1800078eb  call    IkeReturnError
0x1800078f0  mov     rcx, [rbp+57h+var_30]
0x1800078f4  xor     rcx, rsp; StackCookie
0x1800078f7  call    __security_check_cookie
0x1800078fc  mov     rbx, [rsp+0B0h+arg_10]
0x180007904  add     rsp, 90h
0x18000790b  pop     r15
0x18000790d  pop     r14
0x18000790f  pop     rdi
0x180007910  pop     rsi
0x180007911  pop     rbp
0x180007912  retn
0x180007913  call    cs:__imp_HeapAlloc
0x180007919  mov     [rbp+57h+pbHashObject], rax
0x18000791d  test    rax, rax
0x180007920  jz      loc_180007AA0
0x180007926  mov     rbx, r15
0x180007929  cmp     cs:gWfpTrackHeapAllocs, ebx
0x18000792f  jz      loc_18000772B
0x180007935  lock inc cs:gWfpNumHeapAllocs
0x18000793c  jmp     loc_18000772B
0x180007941  call    cs:__imp_HeapAlloc
0x180007947  mov     qword ptr [rbp+57h+cbHashObject], rax
0x18000794b  test    rax, rax
0x18000794e  jz      loc_180007B95
0x180007954  mov     rbx, r15
0x180007957  cmp     cs:gWfpTrackHeapAllocs, ebx
0x18000795d  jz      loc_1800077BA
0x180007963  lock inc cs:gWfpNumHeapAllocs
0x18000796a  jmp     loc_1800077BA
0x18000796f  mov     rcx, [rbp+57h+phHash]; hHash
0x180007973  test    rcx, rcx
0x180007976  jz      loc_180007C5F
0x18000797c  mov     r8d, dword ptr [rbp+57h+phHash+8]; cbOutput
0x180007980  xor     r9d, r9d; dwFlags
0x180007983  mov     rdx, qword ptr [rbp+57h+cbHashObject]; pbOutput
0x180007987  call    cs:__imp_BCryptFinishHash
0x18000798d  test    eax, eax
0x18000798f  jnz     loc_180007C7F
0x180007995  mov     rcx, [rbp+57h+phHash]; hHash
0x180007999  mov     rbx, r15
0x18000799c  mov     dword ptr [rbp+57h+pbHashObject+8], r15d
0x1800079a0  test    rcx, rcx
0x1800079a3  jz      short loc_1800079AB
0x1800079a5  call    cs:__imp_BCryptDestroyHash
0x1800079ab  mov     rax, [rbp+57h+pbHashObject]
0x1800079af  mov     [rbp+57h+phHash], r15
0x1800079b3  test    rax, rax
0x1800079b6  jz      short loc_1800079E8
0x1800079b8  mov     ecx, [rbp+57h+cbHashObject+8]
0x1800079bb  test    rcx, rcx
0x1800079be  jnz     loc_180007C96
0x1800079c4  mov     eax, cs:Feature_BFE_MemAlloc_BugFixes_25B__private_featureState
0x1800079ca  test    al, 10h
0x1800079cc  jnz     loc_180007CA7
0x1800079d2  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline
0x1800079d7  test    eax, eax
0x1800079d9  jz      loc_180007CAF
0x1800079df  lea     rcx, [rbp+57h+pbHashObject]
0x1800079e3  call    WfpMemFree25B
0x1800079e8  mov     [rbp+57h+pbHashObject], r15
0x1800079ec  mov     [rbp+57h+cbHashObject+8], r15d
0x1800079f0  cmp     dword ptr [rbp+57h+pbHashObject+8], ebx
0x1800079f3  jnz     loc_180007CF0
0x1800079f9  lea     rdx, aIkehashfinal; "IkeHashFinal"
0x180007a00  mov     rcx, rbx
0x180007a03  call    IkeReturnError
0x180007a08  mov     rbx, rax
0x180007a0b  test    rax, rax
0x180007a0e  jnz     loc_180007875
0x180007a14  mov     rax, qword ptr [rbp+57h+cbHashObject]
0x180007a18  mov     [r14+8], rax
0x180007a1c  mov     eax, dword ptr [rbp+57h+phHash+8]
0x180007a1f  mov     [r14], eax
0x180007a22  jmp     loc_180007875
0x180007a27  mov     ecx, ebx; Status
0x180007a29  call    cs:__imp_RtlNtStatusToDosError
0x180007a2f  mov     edx, eax
0x180007a31  mov     rcx, rdi
0x180007a34  mov     ebx, eax
0x180007a36  call    WfpCallUsermodeErrorUTMacro
0x180007a3b  test    ebx, ebx
0x180007a3d  jg      loc_180007B7F
0x180007a43  movsxd  rbx, ebx
0x180007a46  jmp     loc_1800077F2
0x180007a4b  mov     ecx, dword ptr [rbp+57h+phHash+8]
0x180007a4e  test    rcx, rcx
0x180007a51  jnz     loc_180007D02
0x180007a57  lea     rcx, [rbp+57h+cbHashObject]
0x180007a5b  call    WfpMemFree
0x180007a60  mov     qword ptr [rbp+57h+cbHashObject], r15
0x180007a64  mov     dword ptr [rbp+57h+phHash+8], r15d
0x180007a68  jmp     short loc_1800079F9
0x180007a6a  mov     ecx, dword ptr [rbp+57h+phHash+8]
0x180007a6d  test    rcx, rcx
0x180007a70  jnz     loc_180007D81
0x180007a76  lea     rcx, [rbp+57h+cbHashObject]
0x180007a7a  call    WfpMemFree
0x180007a7f  mov     qword ptr [rbp+57h+cbHashObject], r15
0x180007a83  mov     dword ptr [rbp+57h+phHash+8], r15d
0x180007a87  jmp     loc_1800078D3
0x180007a8c  lea     rdx, aBcryptgetprope_0; "BCryptGetProperty"
0x180007a93  jmp     loc_180007C1E
0x180007a98  and     eax, 1
0x180007a9b  jmp     loc_1800076F2
0x180007aa0  mov     r8d, 0C0000017h
0x180007aa6  lea     rdx, aHeapalloc; "HeapAlloc"
0x180007aad  call    WfpReportSysErrorAsNtStatus
0x180007ab2  mov     rbx, rax
0x180007ab5  test    rax, rax
0x180007ab8  jz      loc_18000772B
0x180007abe  lea     rdx, aWfpmemalloc25b; "WfpMemAlloc25B"
0x180007ac5  mov     rcx, rax
0x180007ac8  call    WfpReportError
0x180007acd  jmp     loc_18000772B
0x180007ad2  mov     r8d, 0C0000017h
0x180007ad8  lea     rdx, aHeapalloc; "HeapAlloc"
0x180007adf  call    WfpReportSysErrorAsNtStatus
0x180007ae4  mov     rbx, rax
0x180007ae7  test    rax, rax
0x180007aea  jz      loc_18000772B
0x180007af0  lea     rdx, aWfpmemalloc; "WfpMemAlloc"
0x180007af7  mov     rcx, rax
0x180007afa  call    WfpReportError
0x180007aff  jmp     loc_18000772B
0x180007b04  mov     rcx, cs:gWfpHeap; hHeap
0x180007b0b  mov     r8, rax; lpMem
0x180007b0e  xor     edx, edx; dwFlags
0x180007b10  call    cs:__imp_HeapSize
0x180007b16  lock add cs:gWfpHeapBytesAllocated, eax
0x180007b1d  jmp     loc_18000772B
0x180007b22  mov     rax, cs:WPP_GLOBAL_Control
0x180007b29  lea     rcx, WPP_GLOBAL_Control
0x180007b30  lea     rdi, aBcryptgetprope_0; "BCryptGetProperty"
0x180007b37  cmp     rax, rcx
0x180007b3a  jz      loc_180007A27
  ... truncated ...
```
