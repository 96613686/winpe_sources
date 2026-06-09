# IkeHashInitEx

- ea: `0x18000a0d0`
- end: `0x18000a4c2`
- name: `IkeHashInitEx`
- size: `1010`
- prototype: `__int64 __fastcall(BCRYPT_HASH_HANDLE *phHash)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180012a10`

## callees

- `0x180008388`
- `0x180008480`
- `0x18000a0d0`
- `0x180010db0`
- `0x180011350`
- `0x180016534`
- `0x18004882c`
- `0x18004890c`
- `0x180050850`
- `0x1800529a4`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000a2fe`
- `ntdll!RtlNtStatusToDosError` at `0x18000a2fe`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000a3a4`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000a499`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000a3a4`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000a499`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a18c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a21e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a2a0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a2ce`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a18c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a21e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a2a0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a2ce`
- `ncrypt!BCryptCreateHash` at `0x18000a269`
- `ncrypt!BCryptCreateHash` at `0x18000a269`
- `ncrypt!BCryptGetProperty` at `0x18000a14b`
- `ncrypt!BCryptGetProperty` at `0x18000a1db`
- `ncrypt!BCryptGetProperty` at `0x18000a14b`
- `ncrypt!BCryptGetProperty` at `0x18000a1db`

## string_xrefs

- `0x18000a4ab`: `BCryptCreateHash`

## pseudocode

```c
__int64 __fastcall IkeHashInitEx(BCRYPT_HASH_HANDLE *phHash, __int64 a2, UCHAR *a3, ULONG a4)
{
  void *CNGHandleForHashAlgo; // rsi
  unsigned int Property; // eax
  __int64 v9; // rcx
  unsigned int v10; // eax
  SIZE_T v11; // rbx
  int IsEnabledDeviceUsageNoInline; // eax
  void *v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rbx
  NTSTATUS v16; // ebx
  unsigned int v17; // eax
  SIZE_T v18; // rbx
  int v19; // eax
  void *v20; // rax
  __int64 v21; // rcx
  ULONG v22; // r9d
  UCHAR *v23; // r8
  void *v25; // rax
  __int64 v26; // rcx
  void *v27; // rax
  __int64 v28; // rcx
  const char *v29; // rdx
  __int64 v30; // rax
  __int64 v31; // rax
  int TlsPeerAddr; // eax
  int v33; // r8d
  __int64 v34; // rax
  __int64 v35; // rax
  UCHAR pbOutput[4]; // [rsp+40h] [rbp-48h] BYREF
  ULONG pcbResult; // [rsp+44h] [rbp-44h] BYREF

  *(_DWORD *)pbOutput = 0;
  *(_OWORD *)phHash = 0;
  *((_OWORD *)phHash + 1) = 0;
  *((_OWORD *)phHash + 2) = 0;
  pcbResult = 0;
  CNGHandleForHashAlgo = (void *)IkeGetCNGHandleForHashAlgo(a2, a3 != 0);
  Property = BCryptGetProperty(CNGHandleForHashAlgo, L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
  if ( Property )
  {
    v29 = "BCryptGetProperty";
    goto LABEL_44;
  }
  v10 = *(_DWORD *)pbOutput;
  *((_DWORD *)phHash + 6) = *(_DWORD *)pbOutput;
  v11 = v10;
  if ( (Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 0x10) != 0 )
    IsEnabledDeviceUsageNoInline = Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 1;
  else
    IsEnabledDeviceUsageNoInline = Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline();
  if ( IsEnabledDeviceUsageNoInline )
  {
    v25 = HeapAlloc(gWfpHeap, 8u, v11);
    phHash[4] = v25;
    if ( v25 )
    {
      v15 = 0;
      if ( gWfpTrackHeapAllocs )
        _InterlockedIncrement(&gWfpNumHeapAllocs);
    }
    else
    {
      v30 = WfpReportSysErrorAsNtStatus(v26, "HeapAlloc", 3221225495LL);
      v15 = v30;
      if ( v30 )
        WfpReportError(v30, "WfpMemAlloc25B");
    }
  }
  else
  {
    v13 = HeapAlloc(gWfpHeap, 8u, v11);
    phHash[4] = v13;
    if ( v13 )
    {
      v15 = 0;
      if ( gWfpTrackHeapBytes )
        _InterlockedAdd(&gWfpHeapBytesAllocated, HeapSize(gWfpHeap, 0, v13));
    }
    else
    {
      v31 = WfpReportSysErrorAsNtStatus(v14, "HeapAlloc", 3221225495LL);
      v15 = v31;
      if ( v31 )
        WfpReportError(v31, "WfpMemAlloc");
    }
  }
  if ( !v15 )
  {
    v16 = BCryptGetProperty(CNGHandleForHashAlgo, L"HashDigestLength", pbOutput, 4u, &pcbResult, 0);
    if ( !v16 )
    {
      v17 = *(_DWORD *)pbOutput;
      *((_DWORD *)phHash + 2) = *(_DWORD *)pbOutput;
      v18 = v17;
      if ( (Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 0x10) != 0 )
        v19 = Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 1;
      else
        v19 = Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline();
      if ( v19 )
      {
        v27 = HeapAlloc(gWfpHeap, 8u, v18);
        phHash[2] = v27;
        if ( v27 )
        {
          v15 = 0;
          if ( gWfpTrackHeapAllocs )
            _InterlockedIncrement(&gWfpNumHeapAllocs);
        }
        else
        {
          v34 = WfpReportSysErrorAsNtStatus(v28, "HeapAlloc", 3221225495LL);
          v15 = v34;
          if ( v34 )
            WfpReportError(v34, "WfpMemAlloc25B");
        }
      }
      else
      {
        v20 = HeapAlloc(gWfpHeap, 8u, v18);
        phHash[2] = v20;
        if ( v20 )
        {
          v15 = 0;
          if ( gWfpTrackHeapBytes )
            _InterlockedAdd(&gWfpHeapBytesAllocated, HeapSize(gWfpHeap, 0, v20));
        }
        else
        {
          v35 = WfpReportSysErrorAsNtStatus(v21, "HeapAlloc", 3221225495LL);
          v15 = v35;
          if ( v35 )
            WfpReportError(v35, "WfpMemAlloc");
        }
      }
      if ( v15 )
        return IkeReturnError(v15, "IkeHashInitEx");
      v22 = *((_DWORD *)phHash + 6);
      v23 = (UCHAR *)phHash[4];
      *((_DWORD *)phHash + 10) = 1;
      Property = BCryptCreateHash(CNGHandleForHashAlgo, phHash, v23, v22, a3, a4, 0);
      if ( !Property )
        return IkeReturnError(v15, "IkeHashInitEx");
      v29 = "BCryptCreateHash";
LABEL_44:
      v15 = WfpReportSysErrorAsNtStatus(v9, v29, Property);
      return IkeReturnError(v15, "IkeHashInitEx");
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      TlsPeerAddr = IkeGetTlsPeerAddr(&WPP_GLOBAL_Control);
      WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, v33, TlsPeerAddr, (__int64)"BCryptGetProperty", v16);
    }
    LODWORD(v15) = RtlNtStatusToDosError(v16);
    WfpCallUsermodeErrorUTMacro("BCryptGetProperty", (unsigned int)v15);
    if ( (int)v15 > 0 )
      LODWORD(v15) = (unsigned __int16)v15 | 0x80070000;
    v15 = (int)v15;
  }
  return IkeReturnError(v15, "IkeHashInitEx");
}

```

## disassembly

```asm
0x18000a0d0  push    rbx
0x18000a0d2  push    rbp
0x18000a0d3  push    rsi
0x18000a0d4  push    rdi
0x18000a0d5  push    r14
0x18000a0d7  push    r15
0x18000a0d9  sub     rsp, 58h
0x18000a0dd  mov     rax, cs:__security_cookie
0x18000a0e4  xor     rax, rsp
0x18000a0e7  mov     [rsp+88h+var_40], rax
0x18000a0ec  xor     r15d, r15d
0x18000a0ef  mov     rax, rdx
0x18000a0f2  xorps   xmm0, xmm0
0x18000a0f5  mov     dword ptr [rsp+88h+pbOutput], r15d
0x18000a0fa  movups  xmmword ptr [rcx], xmm0
0x18000a0fd  test    r8, r8
0x18000a100  mov     edx, r15d
0x18000a103  movups  xmmword ptr [rcx+10h], xmm0
0x18000a107  mov     rdi, rcx
0x18000a10a  setnz   dl
0x18000a10d  movups  xmmword ptr [rcx+20h], xmm0
0x18000a111  mov     rcx, rax
0x18000a114  mov     [rsp+88h+var_44], r15d
0x18000a119  mov     r14d, r9d
0x18000a11c  mov     rbp, r8
0x18000a11f  call    IkeGetCNGHandleForHashAlgo
0x18000a124  mov     rsi, rax
0x18000a127  mov     [rsp+88h+dwFlags], r15d; dwFlags
0x18000a12c  lea     rax, [rsp+88h+var_44]
0x18000a131  mov     rcx, rsi; hObject
0x18000a134  mov     r9d, 4; cbOutput
0x18000a13a  mov     [rsp+88h+pcbResult], rax; pcbResult
0x18000a13f  lea     r8, [rsp+88h+pbOutput]; pbOutput
0x18000a144  lea     rdx, pszProperty; "ObjectLength"
0x18000a14b  call    cs:__imp_BCryptGetProperty
0x18000a151  test    eax, eax
0x18000a153  jnz     loc_18000A320
0x18000a159  mov     eax, dword ptr [rsp+88h+pbOutput]
0x18000a15d  mov     [rdi+18h], eax
0x18000a160  mov     ebx, eax
0x18000a162  mov     eax, cs:Feature_BFE_MemAlloc_BugFixes_25B__private_featureState
0x18000a168  test    al, 10h
0x18000a16a  jnz     loc_18000A32C
0x18000a170  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline
0x18000a175  mov     rcx, cs:gWfpHeap; hHeap
0x18000a17c  mov     r8, rbx; dwBytes
0x18000a17f  mov     edx, 8; dwFlags
0x18000a184  test    eax, eax
0x18000a186  jnz     loc_18000A2A0
0x18000a18c  call    cs:__imp_HeapAlloc
0x18000a192  mov     [rdi+20h], rax
0x18000a196  test    rax, rax
0x18000a199  jz      loc_18000A366
0x18000a19f  mov     rbx, r15
0x18000a1a2  cmp     cs:gWfpTrackHeapBytes, ebx
0x18000a1a8  jnz     loc_18000A398
0x18000a1ae  test    rbx, rbx
0x18000a1b1  jnz     loc_18000A277
0x18000a1b7  lea     rax, [rsp+88h+var_44]
0x18000a1bc  mov     [rsp+88h+dwFlags], r15d; dwFlags
0x18000a1c1  mov     r9d, 4; cbOutput
0x18000a1c7  mov     [rsp+88h+pcbResult], rax; pcbResult
0x18000a1cc  lea     r8, [rsp+88h+pbOutput]; pbOutput
0x18000a1d1  mov     rcx, rsi; hObject
0x18000a1d4  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18000a1db  call    cs:__imp_BCryptGetProperty
0x18000a1e1  mov     ebx, eax
0x18000a1e3  test    eax, eax
0x18000a1e5  jnz     loc_18000A3B6
0x18000a1eb  mov     eax, dword ptr [rsp+88h+pbOutput]
0x18000a1ef  mov     [rdi+8], eax
0x18000a1f2  mov     ebx, eax
0x18000a1f4  mov     eax, cs:Feature_BFE_MemAlloc_BugFixes_25B__private_featureState
0x18000a1fa  test    al, 10h
0x18000a1fc  jnz     loc_18000A421
0x18000a202  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline
0x18000a207  mov     rcx, cs:gWfpHeap; hHeap
0x18000a20e  mov     r8, rbx; dwBytes
0x18000a211  mov     edx, 8; dwFlags
0x18000a216  test    eax, eax
0x18000a218  jnz     loc_18000A2CE
0x18000a21e  call    cs:__imp_HeapAlloc
0x18000a224  mov     [rdi+10h], rax
0x18000a228  test    rax, rax
0x18000a22b  jz      loc_18000A45B
0x18000a231  mov     rbx, r15
0x18000a234  cmp     cs:gWfpTrackHeapBytes, ebx
0x18000a23a  jnz     loc_18000A48D
0x18000a240  test    rbx, rbx
0x18000a243  jnz     short loc_18000A277
0x18000a245  mov     r9d, [rdi+18h]; cbHashObject
0x18000a249  mov     rdx, rdi; phHash
0x18000a24c  mov     r8, [rdi+20h]; pbHashObject
0x18000a250  mov     rcx, rsi; hAlgorithm
0x18000a253  mov     [rsp+88h+var_58], r15d; dwFlags
0x18000a258  mov     [rsp+88h+dwFlags], r14d; cbSecret
0x18000a25d  mov     [rsp+88h+pcbResult], rbp; pbSecret
0x18000a262  mov     dword ptr [rdi+28h], 1
0x18000a269  call    cs:__imp_BCryptCreateHash
0x18000a26f  test    eax, eax
0x18000a271  jnz     loc_18000A4AB
0x18000a277  lea     rdx, aIkehashinitex; "IkeHashInitEx"
0x18000a27e  mov     rcx, rbx
0x18000a281  call    IkeReturnError
0x18000a286  mov     rcx, [rsp+88h+var_40]
0x18000a28b  xor     rcx, rsp; StackCookie
0x18000a28e  call    __security_check_cookie
0x18000a293  add     rsp, 58h
0x18000a297  pop     r15
0x18000a299  pop     r14
0x18000a29b  pop     rdi
0x18000a29c  pop     rsi
0x18000a29d  pop     rbp
0x18000a29e  pop     rbx
0x18000a29f  retn
0x18000a2a0  call    cs:__imp_HeapAlloc
0x18000a2a6  mov     [rdi+20h], rax
0x18000a2aa  test    rax, rax
0x18000a2ad  jz      loc_18000A334
0x18000a2b3  mov     rbx, r15
0x18000a2b6  cmp     cs:gWfpTrackHeapAllocs, ebx
0x18000a2bc  jz      loc_18000A1AE
0x18000a2c2  lock inc cs:gWfpNumHeapAllocs
0x18000a2c9  jmp     loc_18000A1AE
0x18000a2ce  call    cs:__imp_HeapAlloc
0x18000a2d4  mov     [rdi+10h], rax
0x18000a2d8  test    rax, rax
0x18000a2db  jz      loc_18000A429
0x18000a2e1  mov     rbx, r15
0x18000a2e4  cmp     cs:gWfpTrackHeapAllocs, ebx
0x18000a2ea  jz      loc_18000A240
0x18000a2f0  lock inc cs:gWfpNumHeapAllocs
0x18000a2f7  jmp     loc_18000A240
0x18000a2fc  mov     ecx, ebx; Status
0x18000a2fe  call    cs:__imp_RtlNtStatusToDosError
0x18000a304  mov     edx, eax
0x18000a306  mov     rcx, rdi
0x18000a309  mov     ebx, eax
0x18000a30b  call    WfpCallUsermodeErrorUTMacro
0x18000a310  test    ebx, ebx
0x18000a312  jg      loc_18000A413
0x18000a318  movsxd  rbx, ebx
0x18000a31b  jmp     loc_18000A277
0x18000a320  lea     rdx, aBcryptgetprope_0; "BCryptGetProperty"
0x18000a327  jmp     loc_18000A4B2
0x18000a32c  and     eax, 1
0x18000a32f  jmp     loc_18000A175
0x18000a334  mov     r8d, 0C0000017h
0x18000a33a  lea     rdx, aHeapalloc; "HeapAlloc"
0x18000a341  call    WfpReportSysErrorAsNtStatus
0x18000a346  mov     rbx, rax
0x18000a349  test    rax, rax
0x18000a34c  jz      loc_18000A1AE
0x18000a352  lea     rdx, aWfpmemalloc25b; "WfpMemAlloc25B"
0x18000a359  mov     rcx, rax
0x18000a35c  call    WfpReportError
0x18000a361  jmp     loc_18000A1AE
0x18000a366  mov     r8d, 0C0000017h
0x18000a36c  lea     rdx, aHeapalloc; "HeapAlloc"
0x18000a373  call    WfpReportSysErrorAsNtStatus
0x18000a378  mov     rbx, rax
0x18000a37b  test    rax, rax
0x18000a37e  jz      loc_18000A1AE
0x18000a384  lea     rdx, aWfpmemalloc; "WfpMemAlloc"
0x18000a38b  mov     rcx, rax
0x18000a38e  call    WfpReportError
0x18000a393  jmp     loc_18000A1AE
0x18000a398  mov     rcx, cs:gWfpHeap; hHeap
0x18000a39f  mov     r8, rax; lpMem
0x18000a3a2  xor     edx, edx; dwFlags
0x18000a3a4  call    cs:__imp_HeapSize
0x18000a3aa  lock add cs:gWfpHeapBytesAllocated, eax
0x18000a3b1  jmp     loc_18000A1AE
0x18000a3b6  mov     rax, cs:WPP_GLOBAL_Control
0x18000a3bd  lea     rcx, WPP_GLOBAL_Control
0x18000a3c4  lea     rdi, aBcryptgetprope_0; "BCryptGetProperty"
0x18000a3cb  cmp     rax, rcx
0x18000a3ce  jz      loc_18000A2FC
0x18000a3d4  cmp     byte ptr [rax+19h], 2
0x18000a3d8  jb      loc_18000A2FC
0x18000a3de  test    byte ptr [rax+1Ch], 1
0x18000a3e2  jz      loc_18000A2FC
0x18000a3e8  call    IkeGetTlsPeerAddr
0x18000a3ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a3f4  mov     edx, 16h
0x18000a3f9  mov     [rsp+88h+dwFlags], ebx
0x18000a3fd  mov     r9, rax
0x18000a400  mov     [rsp+88h+pcbResult], rdi
0x18000a405  mov     rcx, [rcx+10h]
0x18000a409  call    WPP_SF_Ssd
0x18000a40e  jmp     loc_18000A2FC
0x18000a413  movzx   ebx, bx
0x18000a416  or      ebx, 80070000h
0x18000a41c  jmp     loc_18000A318
0x18000a421  and     eax, 1
0x18000a424  jmp     loc_18000A207
0x18000a429  mov     r8d, 0C0000017h
0x18000a42f  lea     rdx, aHeapalloc; "HeapAlloc"
0x18000a436  call    WfpReportSysErrorAsNtStatus
0x18000a43b  mov     rbx, rax
0x18000a43e  test    rax, rax
0x18000a441  jz      loc_18000A240
0x18000a447  lea     rdx, aWfpmemalloc25b; "WfpMemAlloc25B"
0x18000a44e  mov     rcx, rax
0x18000a451  call    WfpReportError
0x18000a456  jmp     loc_18000A240
0x18000a45b  mov     r8d, 0C0000017h
0x18000a461  lea     rdx, aHeapalloc; "HeapAlloc"
0x18000a468  call    WfpReportSysErrorAsNtStatus
0x18000a46d  mov     rbx, rax
0x18000a470  test    rax, rax
0x18000a473  jz      loc_18000A240
0x18000a479  lea     rdx, aWfpmemalloc; "WfpMemAlloc"
0x18000a480  mov     rcx, rax
0x18000a483  call    WfpReportError
0x18000a488  jmp     loc_18000A240
0x18000a48d  mov     rcx, cs:gWfpHeap; hHeap
0x18000a494  mov     r8, rax; lpMem
0x18000a497  xor     edx, edx; dwFlags
0x18000a499  call    cs:__imp_HeapSize
0x18000a49f  lock add cs:gWfpHeapBytesAllocated, eax
0x18000a4a6  jmp     loc_18000A240
0x18000a4ab  lea     rdx, aBcryptcreateha_0; "BCryptCreateHash"
0x18000a4b2  mov     r8d, eax
0x18000a4b5  call    WfpReportSysErrorAsNtStatus
0x18000a4ba  mov     rbx, rax
0x18000a4bd  jmp     loc_18000A277
```
