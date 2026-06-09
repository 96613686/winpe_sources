# IkeHashInit

- ea: `0x180009a50`
- end: `0x180009e3f`
- name: `IkeHashInit`
- size: `1007`
- prototype: `__int64 __fastcall(BCRYPT_HASH_HANDLE *phHash)`
- caller_count: `8`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x18008c8cc`
- `0x1800b2758`
- `0x1800b28b4`
- `0x1800b29cc`
- `0x1800b5cfc`
- `0x1800e92ec`
- `0x1800fee04`
- `0x1800fef24`

## callees

- `0x180008388`
- `0x180008480`
- `0x180009a50`
- `0x180010db0`
- `0x180011350`
- `0x180016534`
- `0x18004882c`
- `0x18004890c`
- `0x180050850`
- `0x1800529a4`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180009c7b`
- `ntdll!RtlNtStatusToDosError` at `0x180009c7b`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180009d21`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180009e16`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180009d21`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180009e16`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009afa`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009b8b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009c1d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009c4b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009afa`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009b8b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009c1d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009c4b`
- `ncrypt!BCryptCreateHash` at `0x180009bd4`
- `ncrypt!BCryptCreateHash` at `0x180009bd4`
- `ncrypt!BCryptGetProperty` at `0x180009ab9`
- `ncrypt!BCryptGetProperty` at `0x180009b48`
- `ncrypt!BCryptGetProperty` at `0x180009ab9`
- `ncrypt!BCryptGetProperty` at `0x180009b48`

## string_xrefs

- `0x180009e28`: `BCryptCreateHash`

## pseudocode

```c
__int64 __fastcall IkeHashInit(BCRYPT_HASH_HANDLE *phHash, __int64 a2)
{
  void *CNGHandleForHashAlgo; // rsi
  unsigned int Property; // eax
  __int64 v5; // rcx
  unsigned int v6; // eax
  SIZE_T v7; // rbx
  int IsEnabledDeviceUsageNoInline; // eax
  void *v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rbx
  NTSTATUS v12; // ebx
  unsigned int v13; // eax
  SIZE_T v14; // rbx
  int v15; // eax
  void *v16; // rax
  __int64 v17; // rcx
  ULONG v18; // r9d
  UCHAR *v19; // r8
  __int64 v20; // rax
  void *v22; // rax
  __int64 v23; // rcx
  void *v24; // rax
  __int64 v25; // rcx
  const char *v26; // rdx
  __int64 v27; // rax
  __int64 v28; // rax
  int TlsPeerAddr; // eax
  int v30; // r8d
  __int64 v31; // rax
  __int64 v32; // rax
  UCHAR pbOutput[4]; // [rsp+40h] [rbp-28h] BYREF
  ULONG pcbResult; // [rsp+44h] [rbp-24h] BYREF

  *(_OWORD *)phHash = 0;
  *((_OWORD *)phHash + 1) = 0;
  *(_DWORD *)pbOutput = 0;
  *((_OWORD *)phHash + 2) = 0;
  pcbResult = 0;
  CNGHandleForHashAlgo = (void *)IkeGetCNGHandleForHashAlgo(a2, 0);
  Property = BCryptGetProperty(CNGHandleForHashAlgo, L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
  if ( Property )
  {
    v26 = "BCryptGetProperty";
    goto LABEL_44;
  }
  v6 = *(_DWORD *)pbOutput;
  *((_DWORD *)phHash + 6) = *(_DWORD *)pbOutput;
  v7 = v6;
  if ( (Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 0x10) != 0 )
    IsEnabledDeviceUsageNoInline = Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 1;
  else
    IsEnabledDeviceUsageNoInline = Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline();
  if ( IsEnabledDeviceUsageNoInline )
  {
    v22 = HeapAlloc(gWfpHeap, 8u, v7);
    phHash[4] = v22;
    if ( v22 )
    {
      v11 = 0;
      if ( gWfpTrackHeapAllocs )
        _InterlockedIncrement(&gWfpNumHeapAllocs);
    }
    else
    {
      v27 = WfpReportSysErrorAsNtStatus(v23, "HeapAlloc", 3221225495LL);
      v11 = v27;
      if ( v27 )
        WfpReportError(v27, "WfpMemAlloc25B");
    }
  }
  else
  {
    v9 = HeapAlloc(gWfpHeap, 8u, v7);
    phHash[4] = v9;
    if ( v9 )
    {
      v11 = 0;
      if ( gWfpTrackHeapBytes )
        _InterlockedAdd(&gWfpHeapBytesAllocated, HeapSize(gWfpHeap, 0, v9));
    }
    else
    {
      v28 = WfpReportSysErrorAsNtStatus(v10, "HeapAlloc", 3221225495LL);
      v11 = v28;
      if ( v28 )
        WfpReportError(v28, "WfpMemAlloc");
    }
  }
  if ( !v11 )
  {
    v12 = BCryptGetProperty(CNGHandleForHashAlgo, L"HashDigestLength", pbOutput, 4u, &pcbResult, 0);
    if ( !v12 )
    {
      v13 = *(_DWORD *)pbOutput;
      *((_DWORD *)phHash + 2) = *(_DWORD *)pbOutput;
      v14 = v13;
      if ( (Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 0x10) != 0 )
        v15 = Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 1;
      else
        v15 = Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline();
      if ( v15 )
      {
        v24 = HeapAlloc(gWfpHeap, 8u, v14);
        phHash[2] = v24;
        if ( v24 )
        {
          v11 = 0;
          if ( gWfpTrackHeapAllocs )
            _InterlockedIncrement(&gWfpNumHeapAllocs);
        }
        else
        {
          v31 = WfpReportSysErrorAsNtStatus(v25, "HeapAlloc", 3221225495LL);
          v11 = v31;
          if ( v31 )
            WfpReportError(v31, "WfpMemAlloc25B");
        }
      }
      else
      {
        v16 = HeapAlloc(gWfpHeap, 8u, v14);
        phHash[2] = v16;
        if ( v16 )
        {
          v11 = 0;
          if ( gWfpTrackHeapBytes )
            _InterlockedAdd(&gWfpHeapBytesAllocated, HeapSize(gWfpHeap, 0, v16));
        }
        else
        {
          v32 = WfpReportSysErrorAsNtStatus(v17, "HeapAlloc", 3221225495LL);
          v11 = v32;
          if ( v32 )
            WfpReportError(v32, "WfpMemAlloc");
        }
      }
      if ( v11 )
        goto LABEL_18;
      v18 = *((_DWORD *)phHash + 6);
      v19 = (UCHAR *)phHash[4];
      *((_DWORD *)phHash + 10) = 1;
      Property = BCryptCreateHash(CNGHandleForHashAlgo, phHash, v19, v18, 0, 0, 0);
      if ( !Property )
        goto LABEL_18;
      v26 = "BCryptCreateHash";
LABEL_44:
      v11 = WfpReportSysErrorAsNtStatus(v5, v26, Property);
      goto LABEL_18;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      TlsPeerAddr = IkeGetTlsPeerAddr(&WPP_GLOBAL_Control);
      WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, v30, TlsPeerAddr, (__int64)"BCryptGetProperty", v12);
    }
    LODWORD(v11) = RtlNtStatusToDosError(v12);
    WfpCallUsermodeErrorUTMacro("BCryptGetProperty", (unsigned int)v11);
    if ( (int)v11 > 0 )
      LODWORD(v11) = (unsigned __int16)v11 | 0x80070000;
    v11 = (int)v11;
  }
LABEL_18:
  v20 = IkeReturnError(v11, "IkeHashInitEx");
  return IkeReturnError(v20, "IkeHashInit");
}

```

## disassembly

```asm
0x180009a50  mov     [rsp+arg_10], rbx
0x180009a55  push    rbp
0x180009a56  push    rsi
0x180009a57  push    rdi
0x180009a58  sub     rsp, 50h
0x180009a5c  mov     rax, cs:__security_cookie
0x180009a63  xor     rax, rsp
0x180009a66  mov     [rsp+68h+var_20], rax
0x180009a6b  xorps   xmm0, xmm0
0x180009a6e  mov     rax, rdx
0x180009a71  movups  xmmword ptr [rcx], xmm0
0x180009a74  mov     rdi, rcx
0x180009a77  xor     ebp, ebp
0x180009a79  movups  xmmword ptr [rcx+10h], xmm0
0x180009a7d  xor     edx, edx
0x180009a7f  mov     dword ptr [rsp+68h+pbOutput], ebp
0x180009a83  movups  xmmword ptr [rcx+20h], xmm0
0x180009a87  mov     rcx, rax
0x180009a8a  mov     [rsp+68h+var_24], ebp
0x180009a8e  call    IkeGetCNGHandleForHashAlgo
0x180009a93  mov     rsi, rax
0x180009a96  mov     [rsp+68h+dwFlags], ebp; dwFlags
0x180009a9a  lea     rax, [rsp+68h+var_24]
0x180009a9f  mov     rcx, rsi; hObject
0x180009aa2  mov     r9d, 4; cbOutput
0x180009aa8  mov     [rsp+68h+pcbResult], rax; pcbResult
0x180009aad  lea     r8, [rsp+68h+pbOutput]; pbOutput
0x180009ab2  lea     rdx, pszProperty; "ObjectLength"
0x180009ab9  call    cs:__imp_BCryptGetProperty
0x180009abf  test    eax, eax
0x180009ac1  jnz     loc_180009C9D
0x180009ac7  mov     eax, dword ptr [rsp+68h+pbOutput]
0x180009acb  mov     [rdi+18h], eax
0x180009ace  mov     ebx, eax
0x180009ad0  mov     eax, cs:Feature_BFE_MemAlloc_BugFixes_25B__private_featureState
0x180009ad6  test    al, 10h
0x180009ad8  jnz     loc_180009CA9
0x180009ade  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline
0x180009ae3  mov     rcx, cs:gWfpHeap; hHeap
0x180009aea  mov     r8, rbx; dwBytes
0x180009aed  mov     edx, 8; dwFlags
0x180009af2  test    eax, eax
0x180009af4  jnz     loc_180009C1D
0x180009afa  call    cs:__imp_HeapAlloc
0x180009b00  mov     [rdi+20h], rax
0x180009b04  test    rax, rax
0x180009b07  jz      loc_180009CE3
0x180009b0d  mov     rbx, rbp
0x180009b10  cmp     cs:gWfpTrackHeapBytes, ebx
0x180009b16  jnz     loc_180009D15
0x180009b1c  test    rbx, rbx
0x180009b1f  jnz     loc_180009BE2
0x180009b25  lea     rax, [rsp+68h+var_24]
0x180009b2a  mov     [rsp+68h+dwFlags], ebp; dwFlags
0x180009b2e  mov     r9d, 4; cbOutput
0x180009b34  mov     [rsp+68h+pcbResult], rax; pcbResult
0x180009b39  lea     r8, [rsp+68h+pbOutput]; pbOutput
0x180009b3e  mov     rcx, rsi; hObject
0x180009b41  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180009b48  call    cs:__imp_BCryptGetProperty
0x180009b4e  mov     ebx, eax
0x180009b50  test    eax, eax
0x180009b52  jnz     loc_180009D33
0x180009b58  mov     eax, dword ptr [rsp+68h+pbOutput]
0x180009b5c  mov     [rdi+8], eax
0x180009b5f  mov     ebx, eax
0x180009b61  mov     eax, cs:Feature_BFE_MemAlloc_BugFixes_25B__private_featureState
0x180009b67  test    al, 10h
0x180009b69  jnz     loc_180009D9E
0x180009b6f  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline
0x180009b74  mov     rcx, cs:gWfpHeap; hHeap
0x180009b7b  mov     r8, rbx; dwBytes
0x180009b7e  mov     edx, 8; dwFlags
0x180009b83  test    eax, eax
0x180009b85  jnz     loc_180009C4B
0x180009b8b  call    cs:__imp_HeapAlloc
0x180009b91  mov     [rdi+10h], rax
0x180009b95  test    rax, rax
0x180009b98  jz      loc_180009DD8
0x180009b9e  mov     rbx, rbp
0x180009ba1  cmp     cs:gWfpTrackHeapBytes, ebx
0x180009ba7  jnz     loc_180009E0A
0x180009bad  test    rbx, rbx
0x180009bb0  jnz     short loc_180009BE2
0x180009bb2  mov     r9d, [rdi+18h]; cbHashObject
0x180009bb6  mov     rdx, rdi; phHash
0x180009bb9  mov     r8, [rdi+20h]; pbHashObject
0x180009bbd  mov     rcx, rsi; hAlgorithm
0x180009bc0  mov     [rsp+68h+var_38], ebp; dwFlags
0x180009bc4  mov     [rsp+68h+dwFlags], ebp; cbSecret
0x180009bc8  mov     [rsp+68h+pcbResult], rbp; pbSecret
0x180009bcd  mov     dword ptr [rdi+28h], 1
0x180009bd4  call    cs:__imp_BCryptCreateHash
0x180009bda  test    eax, eax
0x180009bdc  jnz     loc_180009E28
0x180009be2  lea     rdx, aIkehashinitex; "IkeHashInitEx"
0x180009be9  mov     rcx, rbx
0x180009bec  call    IkeReturnError
0x180009bf1  lea     rdx, aIkehashinit; "IkeHashInit"
0x180009bf8  mov     rcx, rax
0x180009bfb  call    IkeReturnError
0x180009c00  mov     rcx, [rsp+68h+var_20]
0x180009c05  xor     rcx, rsp; StackCookie
0x180009c08  call    __security_check_cookie
0x180009c0d  mov     rbx, [rsp+68h+arg_10]
0x180009c15  add     rsp, 50h
0x180009c19  pop     rdi
0x180009c1a  pop     rsi
0x180009c1b  pop     rbp
0x180009c1c  retn
0x180009c1d  call    cs:__imp_HeapAlloc
0x180009c23  mov     [rdi+20h], rax
0x180009c27  test    rax, rax
0x180009c2a  jz      loc_180009CB1
0x180009c30  mov     rbx, rbp
0x180009c33  cmp     cs:gWfpTrackHeapAllocs, ebx
0x180009c39  jz      loc_180009B1C
0x180009c3f  lock inc cs:gWfpNumHeapAllocs
0x180009c46  jmp     loc_180009B1C
0x180009c4b  call    cs:__imp_HeapAlloc
0x180009c51  mov     [rdi+10h], rax
0x180009c55  test    rax, rax
0x180009c58  jz      loc_180009DA6
0x180009c5e  mov     rbx, rbp
0x180009c61  cmp     cs:gWfpTrackHeapAllocs, ebx
0x180009c67  jz      loc_180009BAD
0x180009c6d  lock inc cs:gWfpNumHeapAllocs
0x180009c74  jmp     loc_180009BAD
0x180009c79  mov     ecx, ebx; Status
0x180009c7b  call    cs:__imp_RtlNtStatusToDosError
0x180009c81  mov     edx, eax
0x180009c83  mov     rcx, rdi
0x180009c86  mov     ebx, eax
0x180009c88  call    WfpCallUsermodeErrorUTMacro
0x180009c8d  test    ebx, ebx
0x180009c8f  jg      loc_180009D90
0x180009c95  movsxd  rbx, ebx
0x180009c98  jmp     loc_180009BE2
0x180009c9d  lea     rdx, aBcryptgetprope_0; "BCryptGetProperty"
0x180009ca4  jmp     loc_180009E2F
0x180009ca9  and     eax, 1
0x180009cac  jmp     loc_180009AE3
0x180009cb1  mov     r8d, 0C0000017h
0x180009cb7  lea     rdx, aHeapalloc; "HeapAlloc"
0x180009cbe  call    WfpReportSysErrorAsNtStatus
0x180009cc3  mov     rbx, rax
0x180009cc6  test    rax, rax
0x180009cc9  jz      loc_180009B1C
0x180009ccf  lea     rdx, aWfpmemalloc25b; "WfpMemAlloc25B"
0x180009cd6  mov     rcx, rax
0x180009cd9  call    WfpReportError
0x180009cde  jmp     loc_180009B1C
0x180009ce3  mov     r8d, 0C0000017h
0x180009ce9  lea     rdx, aHeapalloc; "HeapAlloc"
0x180009cf0  call    WfpReportSysErrorAsNtStatus
0x180009cf5  mov     rbx, rax
0x180009cf8  test    rax, rax
0x180009cfb  jz      loc_180009B1C
0x180009d01  lea     rdx, aWfpmemalloc; "WfpMemAlloc"
0x180009d08  mov     rcx, rax
0x180009d0b  call    WfpReportError
0x180009d10  jmp     loc_180009B1C
0x180009d15  mov     rcx, cs:gWfpHeap; hHeap
0x180009d1c  mov     r8, rax; lpMem
0x180009d1f  xor     edx, edx; dwFlags
0x180009d21  call    cs:__imp_HeapSize
0x180009d27  lock add cs:gWfpHeapBytesAllocated, eax
0x180009d2e  jmp     loc_180009B1C
0x180009d33  mov     rax, cs:WPP_GLOBAL_Control
0x180009d3a  lea     rcx, WPP_GLOBAL_Control
0x180009d41  lea     rdi, aBcryptgetprope_0; "BCryptGetProperty"
0x180009d48  cmp     rax, rcx
0x180009d4b  jz      loc_180009C79
0x180009d51  cmp     byte ptr [rax+19h], 2
0x180009d55  jb      loc_180009C79
0x180009d5b  test    byte ptr [rax+1Ch], 1
0x180009d5f  jz      loc_180009C79
0x180009d65  call    IkeGetTlsPeerAddr
0x180009d6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180009d71  mov     edx, 16h
0x180009d76  mov     [rsp+68h+dwFlags], ebx
0x180009d7a  mov     r9, rax
0x180009d7d  mov     [rsp+68h+pcbResult], rdi
0x180009d82  mov     rcx, [rcx+10h]
0x180009d86  call    WPP_SF_Ssd
0x180009d8b  jmp     loc_180009C79
0x180009d90  movzx   ebx, bx
0x180009d93  or      ebx, 80070000h
0x180009d99  jmp     loc_180009C95
0x180009d9e  and     eax, 1
0x180009da1  jmp     loc_180009B74
0x180009da6  mov     r8d, 0C0000017h
0x180009dac  lea     rdx, aHeapalloc; "HeapAlloc"
0x180009db3  call    WfpReportSysErrorAsNtStatus
0x180009db8  mov     rbx, rax
0x180009dbb  test    rax, rax
0x180009dbe  jz      loc_180009BAD
0x180009dc4  lea     rdx, aWfpmemalloc25b; "WfpMemAlloc25B"
0x180009dcb  mov     rcx, rax
0x180009dce  call    WfpReportError
0x180009dd3  jmp     loc_180009BAD
0x180009dd8  mov     r8d, 0C0000017h
0x180009dde  lea     rdx, aHeapalloc; "HeapAlloc"
0x180009de5  call    WfpReportSysErrorAsNtStatus
0x180009dea  mov     rbx, rax
0x180009ded  test    rax, rax
0x180009df0  jz      loc_180009BAD
0x180009df6  lea     rdx, aWfpmemalloc; "WfpMemAlloc"
0x180009dfd  mov     rcx, rax
0x180009e00  call    WfpReportError
0x180009e05  jmp     loc_180009BAD
0x180009e0a  mov     rcx, cs:gWfpHeap; hHeap
0x180009e11  mov     r8, rax; lpMem
0x180009e14  xor     edx, edx; dwFlags
0x180009e16  call    cs:__imp_HeapSize
0x180009e1c  lock add cs:gWfpHeapBytesAllocated, eax
0x180009e23  jmp     loc_180009BAD
0x180009e28  lea     rdx, aBcryptcreateha_0; "BCryptCreateHash"
0x180009e2f  mov     r8d, eax
0x180009e32  call    WfpReportSysErrorAsNtStatus
0x180009e37  mov     rbx, rax
0x180009e3a  jmp     loc_180009BE2
```
