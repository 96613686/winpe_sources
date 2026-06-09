# IkeHmacInit

- ea: `0x180012a10`
- end: `0x180012fa7`
- name: `IkeHmacInit`
- size: `1431`
- prototype: `__int64 __fastcall(BCRYPT_HASH_HANDLE *phHash)`
- caller_count: `25`
- callee_count: `18`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180031dd0`
- `0x180048aec`
- `0x18004c084`
- `0x18004c1ac`
- `0x18004db7c`
- `0x18004dca4`
- `0x18004ddfc`
- `0x18004df5c`
- `0x18004e22c`
- `0x18004e508`
- `0x18004e690`
- `0x180050180`
- `0x1800502d8`
- `0x1800b0f0c`
- `0x1800b14f8`
- `0x1800b2d8c`
- `0x1800b56f0`
- `0x1800deff0`
- `0x1800fe380`
- `0x1800fe57c`
- `0x1800fe7d8`
- `0x1800ff044`
- `0x1800ff1f0`
- `0x1801037cc`
- `0x1801040b8`

## callees

- `0x1800037c4`
- `0x180008388`
- `0x180008480`
- `0x180009f30`
- `0x18000a0d0`
- `0x180010db0`
- `0x180011350`
- `0x180011680`
- `0x180012a10`
- `0x180016534`
- `0x18001c390`
- `0x18004882c`
- `0x18004890c`
- `0x18004ce90`
- `0x180050850`
- `0x1800510ee`
- `0x1800528e4`
- `0x1800529a4`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180012c32`
- `ntdll!RtlNtStatusToDosError` at `0x180012c32`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180012ba3`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180012d16`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180012f1d`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180012ba3`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180012d16`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180012f1d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012f39`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012f39`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012b0a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012b59`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012c87`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012cd1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012b0a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012b59`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012c87`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012cd1`
- `ncrypt!BCryptDestroyHash` at `0x180012eb9`
- `ncrypt!BCryptDestroyHash` at `0x180012eb9`
- `ncrypt!BCryptCreateHash` at `0x180012d4d`
- `ncrypt!BCryptCreateHash` at `0x180012d4d`
- `ncrypt!BCryptGetProperty` at `0x180012ab8`
- `ncrypt!BCryptGetProperty` at `0x180012bd8`
- `ncrypt!BCryptGetProperty` at `0x180012ab8`
- `ncrypt!BCryptGetProperty` at `0x180012bd8`

## string_xrefs

- `0x180012d5a`: `BCryptCreateHash`

## pseudocode

```c
__int64 __fastcall IkeHmacInit(BCRYPT_HASH_HANDLE *phHash, __int64 a2, __int64 a3, unsigned int a4)
{
  BCRYPT_HASH_HANDLE *v7; // rsi
  int v8; // r8d
  void *CNGHandleForHashAlgo; // r12
  unsigned int Property; // eax
  __int64 v11; // rcx
  __int64 v12; // rbx
  SIZE_T v13; // rbx
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 v15; // rcx
  __int64 v16; // rax
  const char *v17; // rdx
  UCHAR *v18; // rax
  __int64 v19; // rcx
  NTSTATUS v20; // ebx
  int v21; // eax
  int v22; // r8d
  SIZE_T v23; // rbx
  int v24; // eax
  __int64 v25; // rcx
  __int64 v26; // rax
  const char *v27; // rdx
  const void *v28; // rax
  __int64 v29; // rcx
  unsigned int Hash; // eax
  __int64 v31; // rcx
  __int64 v32; // rax
  __int64 v33; // rbx
  int TlsPeerAddr; // eax
  int v35; // edx
  int v36; // r8d
  _BYTE *v37; // rax
  __int64 v38; // rcx
  PUCHAR v39; // rax
  __int64 v40; // rcx
  int v41; // eax
  _BYTE *v42; // rax
  __int64 v43; // rcx
  UCHAR pbOutput[4]; // [rsp+48h] [rbp-61h] BYREF
  BCRYPT_HASH_HANDLE phHasha[2]; // [rsp+50h] [rbp-59h] BYREF
  ULONG cbHashObject[4]; // [rsp+60h] [rbp-49h] BYREF
  PUCHAR pbHashObject[2]; // [rsp+70h] [rbp-39h] BYREF
  ULONG pcbResult; // [rsp+80h] [rbp-29h] BYREF
  _BYTE v51[16]; // [rsp+88h] [rbp-21h] BYREF
  const char *v52; // [rsp+98h] [rbp-11h]
  __int64 v53; // [rsp+A0h] [rbp-9h]
  ULONG *p_pcbResult; // [rsp+A8h] [rbp-1h]
  __int64 v55; // [rsp+B0h] [rbp+7h]

  v7 = phHash;
  memset_0(phHash, 0, 0x40u);
  *(_OWORD *)phHasha = 0;
  *(_OWORD *)cbHashObject = 0;
  *(_OWORD *)pbHashObject = 0;
  if ( !a3 || !a4 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      TlsPeerAddr = IkeGetTlsPeerAddr(&WPP_GLOBAL_Control);
      WPP_SF_SsD(*((_QWORD *)WPP_GLOBAL_Control + 2), v35, v36, TlsPeerAddr, (__int64)"IkeHmacInit", 236);
    }
    if ( gWfpLogUserModeErrors && (byte_180178161 & 1) != 0 )
    {
      pcbResult = 13804;
      p_pcbResult = &pcbResult;
      v52 = "IkeHmacInit";
      v53 = 12;
      v55 = 4;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
        (unsigned int)WFP_USERMODE_ERROR,
        v8,
        3,
        (__int64)v51);
    }
    v33 = -2147011092;
    goto LABEL_61;
  }
  if ( a4 <= 0x40 )
  {
LABEL_52:
    v33 = IkeHashInitEx(v7);
    goto LABEL_61;
  }
  *(_DWORD *)pbOutput = 0;
  pcbResult = 0;
  CNGHandleForHashAlgo = (void *)IkeGetCNGHandleForHashAlgo(a2, 0);
  Property = BCryptGetProperty(CNGHandleForHashAlgo, L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
  if ( !Property )
  {
    cbHashObject[2] = *(_DWORD *)pbOutput;
    v13 = *(unsigned int *)pbOutput;
    if ( (Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 0x10) != 0 )
      IsEnabledDeviceUsageNoInline = Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 1;
    else
      IsEnabledDeviceUsageNoInline = Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline();
    if ( IsEnabledDeviceUsageNoInline )
    {
      pbHashObject[0] = (PUCHAR)HeapAlloc(gWfpHeap, 8u, v13);
      if ( !pbHashObject[0] )
      {
        v16 = WfpReportSysErrorAsNtStatus(v15, "HeapAlloc", 3221225495LL);
        v12 = v16;
        if ( !v16 )
          goto LABEL_21;
        v17 = "WfpMemAlloc25B";
        goto LABEL_13;
      }
      v12 = 0;
      if ( gWfpTrackHeapAllocs )
        _InterlockedIncrement(&gWfpNumHeapAllocs);
    }
    else
    {
      v18 = (UCHAR *)HeapAlloc(gWfpHeap, 8u, v13);
      pbHashObject[0] = v18;
      if ( v18 )
      {
        v12 = 0;
        if ( gWfpTrackHeapBytes )
          _InterlockedAdd(&gWfpHeapBytesAllocated, HeapSize(gWfpHeap, 0, v18));
      }
      else
      {
        v16 = WfpReportSysErrorAsNtStatus(v19, "HeapAlloc", 3221225495LL);
        v12 = v16;
        if ( v16 )
        {
          v17 = "WfpMemAlloc";
LABEL_13:
          WfpReportError(v16, v17);
        }
      }
    }
LABEL_21:
    if ( v12 )
    {
LABEL_48:
      v7 = phHash;
      goto LABEL_49;
    }
    v20 = BCryptGetProperty(CNGHandleForHashAlgo, L"HashDigestLength", pbOutput, 4u, &pcbResult, 0);
    if ( v20 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v21 = IkeGetTlsPeerAddr(&WPP_GLOBAL_Control);
        WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, v22, v21, (__int64)"BCryptGetProperty", v20);
      }
      LODWORD(v12) = RtlNtStatusToDosError(v20);
      WfpCallUsermodeErrorUTMacro("BCryptGetProperty", (unsigned int)v12);
      if ( (int)v12 > 0 )
        LODWORD(v12) = (unsigned __int16)v12 | 0x80070000;
      v12 = (int)v12;
      goto LABEL_48;
    }
    LODWORD(phHasha[1]) = *(_DWORD *)pbOutput;
    v23 = *(unsigned int *)pbOutput;
    if ( (Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 0x10) != 0 )
      v24 = Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 1;
    else
      v24 = Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline();
    if ( v24 )
    {
      *(_QWORD *)cbHashObject = HeapAlloc(gWfpHeap, 8u, v23);
      if ( *(_QWORD *)cbHashObject )
      {
        v12 = 0;
        if ( gWfpTrackHeapAllocs )
          _InterlockedIncrement(&gWfpNumHeapAllocs);
        goto LABEL_45;
      }
      v26 = WfpReportSysErrorAsNtStatus(v25, "HeapAlloc", 3221225495LL);
      v12 = v26;
      if ( v26 )
      {
        v27 = "WfpMemAlloc25B";
LABEL_37:
        WfpReportError(v26, v27);
      }
    }
    else
    {
      v28 = HeapAlloc(gWfpHeap, 8u, v23);
      *(_QWORD *)cbHashObject = v28;
      if ( v28 )
      {
        v12 = 0;
        if ( gWfpTrackHeapBytes )
          _InterlockedAdd(&gWfpHeapBytesAllocated, HeapSize(gWfpHeap, 0, v28));
        goto LABEL_45;
      }
      v26 = WfpReportSysErrorAsNtStatus(v29, "HeapAlloc", 3221225495LL);
      v12 = v26;
      if ( v26 )
      {
        v27 = "WfpMemAlloc";
        goto LABEL_37;
      }
    }
LABEL_45:
    if ( !v12 )
    {
      LODWORD(pbHashObject[1]) = 1;
      Hash = BCryptCreateHash(CNGHandleForHashAlgo, phHasha, pbHashObject[0], cbHashObject[2], 0, 0, 0);
      if ( Hash )
        v12 = WfpReportSysErrorAsNtStatus(v31, "BCryptCreateHash", Hash);
    }
    goto LABEL_48;
  }
  v12 = WfpReportSysErrorAsNtStatus(v11, "BCryptGetProperty", Property);
LABEL_49:
  v32 = IkeReturnError(v12, "IkeHashInitEx");
  v33 = IkeReturnError(v32, "IkeHashInit");
  if ( !v33 )
  {
    v33 = IkeHashUpdate(phHasha, a3, a4);
    if ( !v33 )
    {
      v33 = IkeHashFinal(phHasha);
      if ( !v33 )
        goto LABEL_52;
    }
  }
LABEL_61:
  v37 = *(_BYTE **)cbHashObject;
  if ( *(_QWORD *)cbHashObject )
  {
    v38 = LODWORD(phHasha[1]);
    if ( LODWORD(phHasha[1]) )
    {
      do
      {
        *v37++ = 0;
        --v38;
      }
      while ( v38 );
    }
    WfpMemFree((LPCVOID *)cbHashObject);
  }
  if ( phHasha[0] )
    BCryptDestroyHash(phHasha[0]);
  v39 = pbHashObject[0];
  phHasha[0] = 0;
  if ( pbHashObject[0] )
  {
    v40 = cbHashObject[2];
    if ( cbHashObject[2] )
    {
      do
      {
        *v39++ = 0;
        --v40;
      }
      while ( v40 );
    }
    if ( (Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 0x10) != 0 )
      v41 = Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 1;
    else
      v41 = Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline();
    if ( v41 )
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
    v42 = *(_BYTE **)cbHashObject;
    if ( *(_QWORD *)cbHashObject )
    {
      v43 = LODWORD(phHasha[1]);
      if ( LODWORD(phHasha[1]) )
      {
        do
        {
          *v42++ = 0;
          --v43;
        }
        while ( v43 );
      }
      WfpMemFree((LPCVOID *)cbHashObject);
    }
    *(_QWORD *)cbHashObject = 0;
    LODWORD(phHasha[1]) = 0;
  }
  return IkeReturnError(v33, "IkeHmacInit");
}

```

## disassembly

```asm
0x180012a10  push    rbp
0x180012a12  push    rbx
0x180012a13  push    rsi
0x180012a14  push    rdi
0x180012a15  push    r12
0x180012a17  push    r13
0x180012a19  push    r14
0x180012a1b  push    r15
0x180012a1d  lea     rbp, [rsp-1Fh]
0x180012a22  sub     rsp, 0C8h
0x180012a29  mov     rax, cs:__security_cookie
0x180012a30  xor     rax, rsp
0x180012a33  mov     [rbp+57h+var_48], rax
0x180012a37  mov     r13, rdx
0x180012a3a  mov     [rbp+57h+var_C0], rcx
0x180012a3e  xor     edx, edx; Val
0x180012a40  mov     r15, r8
0x180012a43  mov     r14d, r9d
0x180012a46  mov     rsi, rcx
0x180012a49  lea     r8d, [rdx+40h]; Size
0x180012a4d  call    memset_0
0x180012a52  xorps   xmm0, xmm0
0x180012a55  lea     r12, aIkehmacinit; "IkeHmacInit"
0x180012a5c  xor     edi, edi
0x180012a5e  movups  xmmword ptr [rbp+57h+phHash], xmm0
0x180012a62  movups  xmmword ptr [rbp+57h+cbHashObject], xmm0
0x180012a66  movups  xmmword ptr [rbp+57h+pbHashObject], xmm0
0x180012a6a  test    r15, r15
0x180012a6d  jz      loc_180012DEC
0x180012a73  test    r14d, r14d
0x180012a76  jz      loc_180012DEC
0x180012a7c  cmp     r14d, 40h ; '@'
0x180012a80  jbe     loc_180012DD3
0x180012a86  xor     edx, edx
0x180012a88  mov     dword ptr [rbp+57h+pbOutput], edi
0x180012a8b  mov     rcx, r13
0x180012a8e  mov     [rbp+57h+var_80], edi
0x180012a91  call    IkeGetCNGHandleForHashAlgo
0x180012a96  mov     r12, rax
0x180012a99  mov     [rsp+100h+dwFlags], edi; dwFlags
0x180012a9d  lea     rax, [rbp+57h+var_80]
0x180012aa1  mov     rcx, r12; hObject
0x180012aa4  lea     r9d, [rdi+4]; cbOutput
0x180012aa8  mov     [rsp+100h+pcbResult], rax; pcbResult
0x180012aad  lea     r8, [rbp+57h+pbOutput]; pbOutput
0x180012ab1  lea     rdx, pszProperty; "ObjectLength"
0x180012ab8  call    cs:__imp_BCryptGetProperty
0x180012abe  test    eax, eax
0x180012ac0  jz      short loc_180012AD9
0x180012ac2  mov     r8d, eax
0x180012ac5  lea     rdx, aBcryptgetprope_0; "BCryptGetProperty"
0x180012acc  call    WfpReportSysErrorAsNtStatus
0x180012ad1  mov     rbx, rax
0x180012ad4  jmp     loc_180012D71
0x180012ad9  mov     eax, dword ptr [rbp+57h+pbOutput]
0x180012adc  mov     [rbp+57h+cbHashObject+8], eax
0x180012adf  mov     ebx, eax
0x180012ae1  mov     eax, cs:Feature_BFE_MemAlloc_BugFixes_25B__private_featureState
0x180012ae7  test    al, 10h
0x180012ae9  jz      short loc_180012AF0
0x180012aeb  and     eax, 1
0x180012aee  jmp     short loc_180012AF5
0x180012af0  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline
0x180012af5  mov     rcx, cs:gWfpHeap; hHeap
0x180012afc  mov     esi, 8
0x180012b01  mov     edx, esi; dwFlags
0x180012b03  mov     r8, rbx; dwBytes
0x180012b06  test    eax, eax
0x180012b08  jz      short loc_180012B59
0x180012b0a  call    cs:__imp_HeapAlloc
0x180012b10  mov     [rbp+57h+pbHashObject], rax
0x180012b14  mov     edi, 0C0000017h
0x180012b19  test    rax, rax
0x180012b1c  jnz     short loc_180012B46
0x180012b1e  mov     r8d, edi
0x180012b21  lea     rdx, aHeapalloc; "HeapAlloc"
0x180012b28  call    WfpReportSysErrorAsNtStatus
0x180012b2d  mov     rbx, rax
0x180012b30  test    rax, rax
0x180012b33  jz      short loc_180012BB0
0x180012b35  lea     rdx, aWfpmemalloc25b; "WfpMemAlloc25B"
0x180012b3c  mov     rcx, rax
0x180012b3f  call    WfpReportError
0x180012b44  jmp     short loc_180012BB0
0x180012b46  xor     ebx, ebx
0x180012b48  cmp     cs:gWfpTrackHeapAllocs, ebx
0x180012b4e  jz      short loc_180012BB0
0x180012b50  lock inc cs:gWfpNumHeapAllocs
0x180012b57  jmp     short loc_180012BB0
0x180012b59  call    cs:__imp_HeapAlloc
0x180012b5f  mov     [rbp+57h+pbHashObject], rax
0x180012b63  mov     edi, 0C0000017h
0x180012b68  test    rax, rax
0x180012b6b  jnz     short loc_180012B8D
0x180012b6d  mov     r8d, edi
0x180012b70  lea     rdx, aHeapalloc; "HeapAlloc"
0x180012b77  call    WfpReportSysErrorAsNtStatus
0x180012b7c  mov     rbx, rax
0x180012b7f  test    rax, rax
0x180012b82  jz      short loc_180012BB0
0x180012b84  lea     rdx, aWfpmemalloc; "WfpMemAlloc"
0x180012b8b  jmp     short loc_180012B3C
0x180012b8d  xor     ebx, ebx
0x180012b8f  cmp     cs:gWfpTrackHeapBytes, ebx
0x180012b95  jz      short loc_180012BB0
0x180012b97  mov     rcx, cs:gWfpHeap; hHeap
0x180012b9e  mov     r8, rax; lpMem
0x180012ba1  xor     edx, edx; dwFlags
0x180012ba3  call    cs:__imp_HeapSize
0x180012ba9  lock add cs:gWfpHeapBytesAllocated, eax
0x180012bb0  test    rbx, rbx
0x180012bb3  jnz     loc_180012D6B
0x180012bb9  lea     rax, [rbp+57h+var_80]
0x180012bbd  mov     [rsp+100h+dwFlags], ebx; dwFlags
0x180012bc1  lea     r9d, [rbx+4]; cbOutput
0x180012bc5  mov     [rsp+100h+pcbResult], rax; pcbResult
0x180012bca  lea     r8, [rbp+57h+pbOutput]; pbOutput
0x180012bce  mov     rcx, r12; hObject
0x180012bd1  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180012bd8  call    cs:__imp_BCryptGetProperty
0x180012bde  mov     ebx, eax
0x180012be0  test    eax, eax
0x180012be2  jz      short loc_180012C5B
0x180012be4  mov     rdx, cs:WPP_GLOBAL_Control
0x180012beb  lea     rcx, WPP_GLOBAL_Control
0x180012bf2  lea     rdi, aBcryptgetprope_0; "BCryptGetProperty"
0x180012bf9  cmp     rdx, rcx
0x180012bfc  jz      short loc_180012C30
0x180012bfe  cmp     byte ptr [rdx+19h], 2
0x180012c02  jb      short loc_180012C30
0x180012c04  test    byte ptr [rdx+1Ch], 1
0x180012c08  jz      short loc_180012C30
0x180012c0a  call    IkeGetTlsPeerAddr
0x180012c0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180012c16  mov     edx, 16h
0x180012c1b  mov     [rsp+100h+dwFlags], ebx
0x180012c1f  mov     r9, rax
0x180012c22  mov     [rsp+100h+pcbResult], rdi
0x180012c27  mov     rcx, [rcx+10h]
0x180012c2b  call    WPP_SF_Ssd
0x180012c30  mov     ecx, ebx; Status
0x180012c32  call    cs:__imp_RtlNtStatusToDosError
0x180012c38  mov     edx, eax
0x180012c3a  mov     rcx, rdi
0x180012c3d  mov     ebx, eax
0x180012c3f  call    WfpCallUsermodeErrorUTMacro
0x180012c44  xor     edi, edi
0x180012c46  test    ebx, ebx
0x180012c48  jle     short loc_180012C53
0x180012c4a  movzx   ebx, bx
0x180012c4d  or      ebx, 80070000h
0x180012c53  movsxd  rbx, ebx
0x180012c56  jmp     loc_180012D6D
0x180012c5b  mov     eax, dword ptr [rbp+57h+pbOutput]
0x180012c5e  mov     dword ptr [rbp+57h+phHash+8], eax
0x180012c61  mov     ebx, eax
0x180012c63  mov     eax, cs:Feature_BFE_MemAlloc_BugFixes_25B__private_featureState
0x180012c69  test    al, 10h
0x180012c6b  jz      short loc_180012C72
0x180012c6d  and     eax, 1
0x180012c70  jmp     short loc_180012C77
0x180012c72  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline
0x180012c77  mov     rcx, cs:gWfpHeap; hHeap
0x180012c7e  mov     r8, rbx; dwBytes
0x180012c81  mov     edx, esi; dwFlags
0x180012c83  test    eax, eax
0x180012c85  jz      short loc_180012CD1
0x180012c87  call    cs:__imp_HeapAlloc
0x180012c8d  mov     qword ptr [rbp+57h+cbHashObject], rax
0x180012c91  test    rax, rax
0x180012c94  jnz     short loc_180012CBE
0x180012c96  mov     r8d, edi
0x180012c99  lea     rdx, aHeapalloc; "HeapAlloc"
0x180012ca0  call    WfpReportSysErrorAsNtStatus
0x180012ca5  mov     rbx, rax
0x180012ca8  test    rax, rax
0x180012cab  jz      short loc_180012D23
0x180012cad  lea     rdx, aWfpmemalloc25b; "WfpMemAlloc25B"
0x180012cb4  mov     rcx, rax
0x180012cb7  call    WfpReportError
0x180012cbc  jmp     short loc_180012D23
0x180012cbe  xor     ebx, ebx
0x180012cc0  cmp     cs:gWfpTrackHeapAllocs, ebx
0x180012cc6  jz      short loc_180012D23
0x180012cc8  lock inc cs:gWfpNumHeapAllocs
0x180012ccf  jmp     short loc_180012D23
0x180012cd1  call    cs:__imp_HeapAlloc
0x180012cd7  mov     qword ptr [rbp+57h+cbHashObject], rax
0x180012cdb  test    rax, rax
0x180012cde  jnz     short loc_180012D00
0x180012ce0  mov     r8d, edi
0x180012ce3  lea     rdx, aHeapalloc; "HeapAlloc"
0x180012cea  call    WfpReportSysErrorAsNtStatus
0x180012cef  mov     rbx, rax
0x180012cf2  test    rax, rax
0x180012cf5  jz      short loc_180012D23
0x180012cf7  lea     rdx, aWfpmemalloc; "WfpMemAlloc"
0x180012cfe  jmp     short loc_180012CB4
0x180012d00  xor     ebx, ebx
0x180012d02  cmp     cs:gWfpTrackHeapBytes, ebx
0x180012d08  jz      short loc_180012D23
0x180012d0a  mov     rcx, cs:gWfpHeap; hHeap
0x180012d11  mov     r8, rax; lpMem
0x180012d14  xor     edx, edx; dwFlags
0x180012d16  call    cs:__imp_HeapSize
0x180012d1c  lock add cs:gWfpHeapBytesAllocated, eax
0x180012d23  xor     edi, edi
0x180012d25  test    rbx, rbx
0x180012d28  jnz     short loc_180012D6D
0x180012d2a  mov     r9d, [rbp+57h+cbHashObject+8]; cbHashObject
0x180012d2e  lea     rdx, [rbp+57h+phHash]; phHash
0x180012d32  mov     r8, [rbp+57h+pbHashObject]; pbHashObject
0x180012d36  mov     rcx, r12; hAlgorithm
0x180012d39  mov     [rsp+100h+var_D0], edi; dwFlags
0x180012d3d  mov     [rsp+100h+dwFlags], edi; cbSecret
0x180012d41  mov     [rsp+100h+pcbResult], rdi; pbSecret
0x180012d46  mov     dword ptr [rbp+57h+pbHashObject+8], 1
0x180012d4d  call    cs:__imp_BCryptCreateHash
0x180012d53  test    eax, eax
0x180012d55  jz      short loc_180012D6D
0x180012d57  mov     r8d, eax
0x180012d5a  lea     rdx, aBcryptcreateha_0; "BCryptCreateHash"
0x180012d61  call    WfpReportSysErrorAsNtStatus
0x180012d66  mov     rbx, rax
0x180012d69  jmp     short loc_180012D6D
0x180012d6b  xor     edi, edi
0x180012d6d  mov     rsi, [rbp+57h+var_C0]
0x180012d71  lea     rdx, aIkehashinitex; "IkeHashInitEx"
0x180012d78  mov     rcx, rbx
0x180012d7b  call    IkeReturnError
0x180012d80  lea     rdx, aIkehashinit; "IkeHashInit"
0x180012d87  mov     rcx, rax
0x180012d8a  call    IkeReturnError
0x180012d8f  mov     rbx, rax
0x180012d92  test    rax, rax
0x180012d95  jnz     loc_180012E8A
0x180012d9b  mov     r8d, r14d
0x180012d9e  lea     rcx, [rbp+57h+phHash]
0x180012da2  mov     rdx, r15
0x180012da5  call    IkeHashUpdate
0x180012daa  mov     rbx, rax
0x180012dad  test    rax, rax
0x180012db0  jnz     loc_180012E8A
0x180012db6  lea     rcx, [rbp+57h+phHash]
0x180012dba  call    IkeHashFinal
0x180012dbf  mov     rbx, rax
0x180012dc2  test    rax, rax
0x180012dc5  jnz     loc_180012E8A
0x180012dcb  mov     r15, qword ptr [rbp+57h+cbHashObject]
0x180012dcf  mov     r14d, dword ptr [rbp+57h+phHash+8]
0x180012dd3  mov     r9d, r14d
0x180012dd6  mov     r8, r15
0x180012dd9  mov     rdx, r13
0x180012ddc  mov     rcx, rsi; phHash
0x180012ddf  call    IkeHashInitEx
0x180012de4  mov     rbx, rax
0x180012de7  jmp     loc_180012E8A
0x180012dec  mov     rax, cs:WPP_GLOBAL_Control
0x180012df3  lea     rcx, WPP_GLOBAL_Control
0x180012dfa  mov     ebx, 35ECh
0x180012dff  cmp     rax, rcx
0x180012e02  jz      short loc_180012E31
0x180012e04  cmp     byte ptr [rax+19h], 2
0x180012e08  jb      short loc_180012E31
0x180012e0a  test    byte ptr [rax+1Ch], 1
0x180012e0e  jz      short loc_180012E31
0x180012e10  call    IkeGetTlsPeerAddr
0x180012e15  mov     rcx, cs:WPP_GLOBAL_Control
0x180012e1c  mov     r9, rax
0x180012e1f  mov     [rsp+100h+dwFlags], ebx
0x180012e23  mov     [rsp+100h+pcbResult], r12
0x180012e28  mov     rcx, [rcx+10h]
0x180012e2c  call    WPP_SF_SsD
0x180012e31  cmp     cs:gWfpLogUserModeErrors, edi
0x180012e37  jz      short loc_180012E83
0x180012e39  test    cs:byte_180178161, 1
0x180012e40  jz      short loc_180012E83
0x180012e42  lea     rax, [rbp+57h+var_80]
0x180012e46  mov     [rbp+57h+var_80], ebx
0x180012e49  mov     [rbp+57h+var_58], rax
0x180012e4d  lea     rdx, WFP_USERMODE_ERROR
0x180012e54  lea     rax, [rbp+57h+var_78]
0x180012e58  mov     [rbp+57h+var_68], r12
0x180012e5c  mov     r9d, 3
0x180012e62  mov     [rsp+100h+pcbResult], rax
0x180012e67  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x180012e6e  mov     [rbp+57h+var_60], 0Ch
0x180012e76  mov     [rbp+57h+var_50], 4
0x180012e7e  call    McGenEventWrite_EtwEventWriteTransfer
0x180012e83  mov     rbx, 0FFFFFFFF800735ECh
0x180012e8a  mov     rax, qword ptr [rbp+57h+cbHashObject]
0x180012e8e  test    rax, rax
0x180012e91  jz      short loc_180012EB0
0x180012e93  mov     ecx, dword ptr [rbp+57h+phHash+8]
0x180012e96  test    rcx, rcx
0x180012e99  jz      short loc_180012EA7
0x180012e9b  mov     [rax], dil
0x180012e9e  inc     rax
0x180012ea1  sub     rcx, 1
0x180012ea5  jnz     short loc_180012E9B
  ... truncated ...
```
