# GetSidFromToken

- ea: `0x180016730`
- end: `0x180016b0d`
- name: `GetSidFromToken`
- size: `989`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, _QWORD *)`
- caller_count: `9`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001d260`
- `0x18002f080`
- `0x18004ee6c`
- `0x180073284`
- `0x18007b6c4`
- `0x18007f760`
- `0x18008073c`
- `0x180080908`
- `0x1800c901c`

## callees

- `0x1800037c4`
- `0x1800061ec`
- `0x180008388`
- `0x180010db0`
- `0x180016534`
- `0x180016730`
- `0x18004882c`
- `0x18004aa3c`
- `0x180050850`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016944`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800169fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016abb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016944`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800169fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016abb`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800169e8`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180016a95`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800169e8`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180016a95`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800167d5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016865`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800168e0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016912`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800167d5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016865`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800168e0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016912`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001682f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001682f`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180016ab1`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180016ab1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180016794`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001681e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180016794`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001681e`

## string_xrefs

- `0x180016ac7`: `CopySid`
- `0x180016753`: `GetSidFromToken`
- `0x1800168bd`: `GetSidFromToken`
- `0x180016959`: `GetSidFromToken`
- `0x180016a06`: `GetTokenInformation`

## pseudocode

```c
__int64 __fastcall GetSidFromToken(HANDLE TokenHandle, _QWORD *a2)
{
  void *v4; // rsi
  SIZE_T v5; // rbx
  int IsEnabledDeviceUsageNoInline; // eax
  PSID *v7; // rax
  __int64 v8; // rcx
  PSID *v9; // rdi
  __int64 v10; // rbx
  DWORD LengthSid; // eax
  SIZE_T v12; // rbx
  int v13; // eax
  const void *v14; // rax
  __int64 v15; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  DWORD v19; // eax
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rax
  DWORD v23; // eax
  __int64 v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rax
  DWORD LastError; // eax
  __int64 v28; // rcx
  LPCVOID v29; // [rsp+30h] [rbp-48h] BYREF
  PSID *v30; // [rsp+38h] [rbp-40h] BYREF
  DWORD TokenInformationLength; // [rsp+40h] [rbp-38h] BYREF

  *a2 = 0;
  v4 = 0;
  TokenInformationLength = 0;
  v29 = 0;
  TraceLogHelper("GetSidFromToken", 1);
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) || (v19 = GetLastError(), v19 == 122) )
  {
    v5 = TokenInformationLength;
    if ( (Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 0x10) != 0 )
      IsEnabledDeviceUsageNoInline = Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 1;
    else
      IsEnabledDeviceUsageNoInline = Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline();
    if ( IsEnabledDeviceUsageNoInline )
    {
      v30 = (PSID *)HeapAlloc(gWfpHeap, 8u, v5);
      v9 = v30;
      if ( v30 )
      {
        v10 = 0;
        if ( gWfpTrackHeapAllocs )
          _InterlockedIncrement(&gWfpNumHeapAllocs);
      }
      else
      {
        v21 = WfpReportSysErrorAsNtStatus(v17, "HeapAlloc", 3221225495LL);
        v10 = v21;
        if ( v21 )
          WfpReportError(v21, "WfpMemAlloc25B");
      }
    }
    else
    {
      v7 = (PSID *)HeapAlloc(gWfpHeap, 8u, v5);
      v30 = v7;
      v9 = v7;
      if ( v7 )
      {
        v10 = 0;
        if ( gWfpTrackHeapBytes )
          _InterlockedAdd(&gWfpHeapBytesAllocated, HeapSize(gWfpHeap, 0, v7));
      }
      else
      {
        v22 = WfpReportSysErrorAsNtStatus(v8, "HeapAlloc", 3221225495LL);
        v10 = v22;
        if ( v22 )
          WfpReportError(v22, "WfpMemAlloc");
      }
    }
    if ( !v10 )
    {
      if ( GetTokenInformation(TokenHandle, TokenUser, v9, TokenInformationLength, &TokenInformationLength) )
      {
        LengthSid = GetLengthSid(*v9);
        v12 = LengthSid;
        TokenInformationLength = LengthSid;
        if ( (Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 0x10) != 0 )
          v13 = Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 1;
        else
          v13 = Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline();
        if ( v13 )
        {
          v29 = HeapAlloc(gWfpHeap, 8u, v12);
          v4 = (void *)v29;
          if ( v29 )
          {
            v10 = 0;
            if ( gWfpTrackHeapAllocs )
              _InterlockedIncrement(&gWfpNumHeapAllocs);
          }
          else
          {
            v25 = WfpReportSysErrorAsNtStatus(v18, "HeapAlloc", 3221225495LL);
            v10 = v25;
            if ( v25 )
              WfpReportError(v25, "WfpMemAlloc25B");
          }
        }
        else
        {
          v14 = HeapAlloc(gWfpHeap, 8u, v12);
          v29 = v14;
          v4 = (void *)v14;
          if ( v14 )
          {
            v10 = 0;
            if ( gWfpTrackHeapBytes )
              _InterlockedAdd(&gWfpHeapBytesAllocated, HeapSize(gWfpHeap, 0, v14));
          }
          else
          {
            v26 = WfpReportSysErrorAsNtStatus(v15, "HeapAlloc", 3221225495LL);
            v10 = v26;
            if ( v26 )
              WfpReportError(v26, "WfpMemAlloc");
          }
        }
        if ( !v10 )
        {
          if ( CopySid(TokenInformationLength, v4, *v9) )
          {
            *a2 = v4;
          }
          else
          {
            LastError = GetLastError();
            v10 = WfpReportSysErrorAsWinError(v28, "CopySid", LastError, 1);
          }
        }
      }
      else
      {
        v23 = GetLastError();
        v10 = WfpReportSysErrorAsWinError(v24, "GetTokenInformation", v23, 1);
      }
    }
    if ( v9 )
      WfpMemFree((LPCVOID *)&v30);
  }
  else
  {
    v10 = WfpReportSysErrorAsWinError(v20, "GetSidFromToken", v19, 1);
  }
  if ( v10 && v4 )
    WfpMemFree(&v29);
  return IkeReturnError(v10, "GetSidFromToken");
}

```

## disassembly

```asm
0x180016730  mov     r11, rsp
0x180016733  push    rbx
0x180016734  push    rsi
0x180016735  sub     rsp, 68h
0x180016739  mov     rax, cs:__security_cookie
0x180016740  xor     rax, rsp
0x180016743  mov     [rsp+78h+var_30], rax
0x180016748  mov     [r11+18h], rbp
0x18001674c  mov     rbp, rcx
0x18001674f  mov     [r11-20h], r14
0x180016753  lea     rcx, aGetsidfromtoke; "GetSidFromToken"
0x18001675a  mov     [r11-28h], r15
0x18001675e  mov     r14, rdx
0x180016761  xor     r15d, r15d
0x180016764  mov     [rdx], r15
0x180016767  mov     esi, r15d
0x18001676a  mov     edx, 1
0x18001676f  mov     [r11-38h], r15d
0x180016773  mov     [r11-48h], r15
0x180016777  call    TraceLogHelper
0x18001677c  lea     rax, [rsp+78h+TokenInformationLength]
0x180016781  xor     r9d, r9d; TokenInformationLength
0x180016784  xor     r8d, r8d; TokenInformation
0x180016787  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x18001678c  mov     edx, 1; TokenInformationClass
0x180016791  mov     rcx, rbp; TokenHandle
0x180016794  call    cs:__imp_GetTokenInformation
0x18001679a  test    eax, eax
0x18001679c  jz      loc_180016944
0x1800167a2  mov     ebx, [rsp+78h+TokenInformationLength]
0x1800167a6  mov     [rsp+78h+var_18], rdi
0x1800167ab  mov     eax, cs:Feature_BFE_MemAlloc_BugFixes_25B__private_featureState
0x1800167b1  test    al, 10h
0x1800167b3  jnz     loc_180016970
0x1800167b9  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline
0x1800167be  mov     rcx, cs:gWfpHeap; hHeap
0x1800167c5  mov     r8, rbx; dwBytes
0x1800167c8  mov     edx, 8; dwFlags
0x1800167cd  test    eax, eax
0x1800167cf  jnz     loc_1800168E0
0x1800167d5  call    cs:__imp_HeapAlloc
0x1800167db  mov     [rsp+78h+var_40], rax
0x1800167e0  mov     rdi, rax
0x1800167e3  test    rax, rax
0x1800167e6  jz      loc_1800169AA
0x1800167ec  mov     rbx, r15
0x1800167ef  cmp     cs:gWfpTrackHeapBytes, ebx
0x1800167f5  jnz     loc_1800169DC
0x1800167fb  test    rbx, rbx
0x1800167fe  jnz     loc_180016894
0x180016804  mov     r9d, [rsp+78h+TokenInformationLength]; TokenInformationLength
0x180016809  lea     rax, [rsp+78h+TokenInformationLength]
0x18001680e  mov     r8, rdi; TokenInformation
0x180016811  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x180016816  mov     edx, 1; TokenInformationClass
0x18001681b  mov     rcx, rbp; TokenHandle
0x18001681e  call    cs:__imp_GetTokenInformation
0x180016824  test    eax, eax
0x180016826  jz      loc_1800169FA
0x18001682c  mov     rcx, [rdi]; pSid
0x18001682f  call    cs:__imp_GetLengthSid
0x180016835  mov     ebx, eax
0x180016837  mov     [rsp+78h+TokenInformationLength], ebx
0x18001683b  mov     eax, cs:Feature_BFE_MemAlloc_BugFixes_25B__private_featureState
0x180016841  test    al, 10h
0x180016843  jnz     loc_180016A1D
0x180016849  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline
0x18001684e  mov     rcx, cs:gWfpHeap; hHeap
0x180016855  mov     r8, rbx; dwBytes
0x180016858  mov     edx, 8; dwFlags
0x18001685d  test    eax, eax
0x18001685f  jnz     loc_180016912
0x180016865  call    cs:__imp_HeapAlloc
0x18001686b  mov     [rsp+78h+var_48], rax
0x180016870  mov     rsi, rax
0x180016873  test    rax, rax
0x180016876  jz      loc_180016A57
0x18001687c  mov     rbx, r15
0x18001687f  cmp     cs:gWfpTrackHeapBytes, ebx
0x180016885  jnz     loc_180016A89
0x18001688b  test    rbx, rbx
0x18001688e  jz      loc_180016AA7
0x180016894  test    rdi, rdi
0x180016897  mov     rdi, [rsp+78h+var_18]
0x18001689c  jnz     loc_180016AE6
0x1800168a2  mov     r15, [rsp+78h+var_28]
0x1800168a7  mov     r14, [rsp+78h+var_20]
0x1800168ac  mov     rbp, [rsp+78h+arg_10]
0x1800168b4  test    rbx, rbx
0x1800168b7  jnz     loc_180016AF5
0x1800168bd  lea     rdx, aGetsidfromtoke; "GetSidFromToken"
0x1800168c4  mov     rcx, rbx
0x1800168c7  call    IkeReturnError
0x1800168cc  mov     rcx, [rsp+78h+var_30]
0x1800168d1  xor     rcx, rsp; StackCookie
0x1800168d4  call    __security_check_cookie
0x1800168d9  add     rsp, 68h
0x1800168dd  pop     rsi
0x1800168de  pop     rbx
0x1800168df  retn
0x1800168e0  call    cs:__imp_HeapAlloc
0x1800168e6  mov     [rsp+78h+var_40], rax
0x1800168eb  mov     rdi, rax
0x1800168ee  test    rax, rax
0x1800168f1  jz      loc_180016978
0x1800168f7  mov     rbx, r15
0x1800168fa  cmp     cs:gWfpTrackHeapAllocs, ebx
0x180016900  jz      loc_1800167FB
0x180016906  lock inc cs:gWfpNumHeapAllocs
0x18001690d  jmp     loc_1800167FB
0x180016912  call    cs:__imp_HeapAlloc
0x180016918  mov     [rsp+78h+var_48], rax
0x18001691d  mov     rsi, rax
0x180016920  test    rax, rax
0x180016923  jz      loc_180016A25
0x180016929  mov     rbx, r15
0x18001692c  cmp     cs:gWfpTrackHeapAllocs, ebx
0x180016932  jz      loc_18001688B
0x180016938  lock inc cs:gWfpNumHeapAllocs
0x18001693f  jmp     loc_18001688B
0x180016944  call    cs:__imp_GetLastError
0x18001694a  cmp     eax, 7Ah ; 'z'
0x18001694d  jz      loc_1800167A2
0x180016953  mov     r9d, 1
0x180016959  lea     rdx, aGetsidfromtoke; "GetSidFromToken"
0x180016960  mov     r8d, eax
0x180016963  call    WfpReportSysErrorAsWinError
0x180016968  mov     rbx, rax
0x18001696b  jmp     loc_1800168A2
0x180016970  and     eax, 1
0x180016973  jmp     loc_1800167BE
0x180016978  mov     r8d, 0C0000017h
0x18001697e  lea     rdx, aHeapalloc; "HeapAlloc"
0x180016985  call    WfpReportSysErrorAsNtStatus
0x18001698a  mov     rbx, rax
0x18001698d  test    rax, rax
0x180016990  jz      loc_1800167FB
0x180016996  lea     rdx, aWfpmemalloc25b; "WfpMemAlloc25B"
0x18001699d  mov     rcx, rax
0x1800169a0  call    WfpReportError
0x1800169a5  jmp     loc_1800167FB
0x1800169aa  mov     r8d, 0C0000017h
0x1800169b0  lea     rdx, aHeapalloc; "HeapAlloc"
0x1800169b7  call    WfpReportSysErrorAsNtStatus
0x1800169bc  mov     rbx, rax
0x1800169bf  test    rax, rax
0x1800169c2  jz      loc_1800167FB
0x1800169c8  lea     rdx, aWfpmemalloc; "WfpMemAlloc"
0x1800169cf  mov     rcx, rax
0x1800169d2  call    WfpReportError
0x1800169d7  jmp     loc_1800167FB
0x1800169dc  mov     rcx, cs:gWfpHeap; hHeap
0x1800169e3  mov     r8, rax; lpMem
0x1800169e6  xor     edx, edx; dwFlags
0x1800169e8  call    cs:__imp_HeapSize
0x1800169ee  lock add cs:gWfpHeapBytesAllocated, eax
0x1800169f5  jmp     loc_1800167FB
0x1800169fa  call    cs:__imp_GetLastError
0x180016a00  mov     r9d, 1
0x180016a06  lea     rdx, aGettokeninform; "GetTokenInformation"
0x180016a0d  mov     r8d, eax
0x180016a10  call    WfpReportSysErrorAsWinError
0x180016a15  mov     rbx, rax
0x180016a18  jmp     loc_180016894
0x180016a1d  and     eax, 1
0x180016a20  jmp     loc_18001684E
0x180016a25  mov     r8d, 0C0000017h
0x180016a2b  lea     rdx, aHeapalloc; "HeapAlloc"
0x180016a32  call    WfpReportSysErrorAsNtStatus
0x180016a37  mov     rbx, rax
0x180016a3a  test    rax, rax
0x180016a3d  jz      loc_18001688B
0x180016a43  lea     rdx, aWfpmemalloc25b; "WfpMemAlloc25B"
0x180016a4a  mov     rcx, rax
0x180016a4d  call    WfpReportError
0x180016a52  jmp     loc_18001688B
0x180016a57  mov     r8d, 0C0000017h
0x180016a5d  lea     rdx, aHeapalloc; "HeapAlloc"
0x180016a64  call    WfpReportSysErrorAsNtStatus
0x180016a69  mov     rbx, rax
0x180016a6c  test    rax, rax
0x180016a6f  jz      loc_18001688B
0x180016a75  lea     rdx, aWfpmemalloc; "WfpMemAlloc"
0x180016a7c  mov     rcx, rax
0x180016a7f  call    WfpReportError
0x180016a84  jmp     loc_18001688B
0x180016a89  mov     rcx, cs:gWfpHeap; hHeap
0x180016a90  mov     r8, rax; lpMem
0x180016a93  xor     edx, edx; dwFlags
0x180016a95  call    cs:__imp_HeapSize
0x180016a9b  lock add cs:gWfpHeapBytesAllocated, eax
0x180016aa2  jmp     loc_18001688B
0x180016aa7  mov     r8, [rdi]; pSourceSid
0x180016aaa  mov     rdx, rsi; pDestinationSid
0x180016aad  mov     ecx, [rsp+78h+TokenInformationLength]; nDestinationSidLength
0x180016ab1  call    cs:__imp_CopySid
0x180016ab7  test    eax, eax
0x180016ab9  jnz     short loc_180016ADE
0x180016abb  call    cs:__imp_GetLastError
0x180016ac1  mov     r9d, 1
0x180016ac7  lea     rdx, aCopysid; "CopySid"
0x180016ace  mov     r8d, eax
0x180016ad1  call    WfpReportSysErrorAsWinError
0x180016ad6  mov     rbx, rax
0x180016ad9  jmp     loc_180016894
0x180016ade  mov     [r14], rsi
0x180016ae1  jmp     loc_180016894
0x180016ae6  lea     rcx, [rsp+78h+var_40]
0x180016aeb  call    WfpMemFree
0x180016af0  jmp     loc_1800168A2
0x180016af5  test    rsi, rsi
0x180016af8  jz      loc_1800168BD
0x180016afe  lea     rcx, [rsp+78h+var_48]
0x180016b03  call    WfpMemFree
0x180016b08  jmp     loc_1800168BD
```
