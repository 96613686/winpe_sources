# IkeCopySid

- ea: `0x180006c50`
- end: `0x180006de6`
- name: `IkeCopySid`
- size: `406`
- prototype: `__int64 __fastcall(PSID pSourceSid)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180072a14`

## callees

- `0x1800037c4`
- `0x1800061ec`
- `0x180006c50`
- `0x180008388`
- `0x180010db0`
- `0x180016534`
- `0x18004882c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006cdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006cdf`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180006dd4`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180006dd4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006c9a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006d23`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006c9a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006d23`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180006c63`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180006c63`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180006cd0`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180006cd0`

## string_xrefs

- `0x180006d02`: `IkeCopySid`
- `0x180006ceb`: `CopySid`

## pseudocode

```c
__int64 __fastcall IkeCopySid(PSID pSourceSid, _QWORD *a2)
{
  __int64 v4; // rcx
  SIZE_T LengthSid; // rsi
  int IsEnabledDeviceUsageNoInline; // eax
  void *v7; // rax
  __int64 v8; // rcx
  void *v9; // rdi
  __int64 v10; // rbx
  DWORD LastError; // eax
  __int64 v12; // rcx
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rax
  LPVOID v17; // [rsp+50h] [rbp+18h] BYREF

  LengthSid = GetLengthSid(pSourceSid);
  if ( (Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 0x10) != 0 )
    IsEnabledDeviceUsageNoInline = Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 1;
  else
    IsEnabledDeviceUsageNoInline = Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline(v4);
  if ( IsEnabledDeviceUsageNoInline )
  {
    v17 = HeapAlloc(gWfpHeap, 8u, LengthSid);
    v9 = v17;
    if ( v17 )
    {
      v10 = 0;
      if ( gWfpTrackHeapAllocs )
        _InterlockedIncrement(&gWfpNumHeapAllocs);
    }
    else
    {
      v15 = WfpReportSysErrorAsNtStatus(v14, "HeapAlloc", 3221225495LL);
      v10 = v15;
      if ( v15 )
        WfpReportError(v15, "WfpMemAlloc25B");
    }
  }
  else
  {
    v7 = HeapAlloc(gWfpHeap, 8u, LengthSid);
    v17 = v7;
    v9 = v7;
    if ( v7 )
    {
      v10 = 0;
      if ( gWfpTrackHeapBytes )
        _InterlockedAdd(&gWfpHeapBytesAllocated, HeapSize(gWfpHeap, 0, v7));
    }
    else
    {
      v16 = WfpReportSysErrorAsNtStatus(v8, "HeapAlloc", 3221225495LL);
      v10 = v16;
      if ( v16 )
        WfpReportError(v16, "WfpMemAlloc");
    }
  }
  if ( v10 )
    goto LABEL_15;
  if ( !CopySid(LengthSid, v9, pSourceSid) )
  {
    LastError = GetLastError();
    v10 = WfpReportSysErrorAsWinError(v12, "CopySid", LastError, 1);
    if ( !v10 )
      return IkeReturnError(v10, "IkeCopySid");
LABEL_15:
    WfpMemFree(&v17);
    return IkeReturnError(v10, "IkeCopySid");
  }
  *a2 = v9;
  return IkeReturnError(v10, "IkeCopySid");
}

```

## disassembly

```asm
0x180006c50  mov     [rsp+arg_8], rbx
0x180006c55  push    rbp
0x180006c56  push    rsi
0x180006c57  push    r14
0x180006c59  sub     rsp, 20h
0x180006c5d  mov     r14, rdx
0x180006c60  mov     rbp, rcx
0x180006c63  call    cs:__imp_GetLengthSid
0x180006c69  mov     esi, eax
0x180006c6b  mov     eax, cs:Feature_BFE_MemAlloc_BugFixes_25B__private_featureState
0x180006c71  test    al, 10h
0x180006c73  jnz     loc_180006D5C
0x180006c79  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline
0x180006c7e  mov     rcx, cs:gWfpHeap; hHeap
0x180006c85  mov     r8, rsi; dwBytes
0x180006c88  mov     [rsp+38h+arg_0], rdi
0x180006c8d  mov     edx, 8; dwFlags
0x180006c92  test    eax, eax
0x180006c94  jnz     loc_180006D23
0x180006c9a  call    cs:__imp_HeapAlloc
0x180006ca0  mov     [rsp+38h+arg_10], rax
0x180006ca5  mov     rdi, rax
0x180006ca8  test    rax, rax
0x180006cab  jz      loc_180006D96
0x180006cb1  xor     ebx, ebx
0x180006cb3  cmp     cs:gWfpTrackHeapBytes, ebx
0x180006cb9  jnz     loc_180006DC8
0x180006cbf  test    rbx, rbx
0x180006cc2  jnz     loc_180006D50
0x180006cc8  mov     r8, rbp; pSourceSid
0x180006ccb  mov     rdx, rdi; pDestinationSid
0x180006cce  mov     ecx, esi; nDestinationSidLength
0x180006cd0  call    cs:__imp_CopySid
0x180006cd6  test    eax, eax
0x180006cd8  jz      short loc_180006CDF
0x180006cda  mov     [r14], rdi
0x180006cdd  jmp     short loc_180006D02
0x180006cdf  call    cs:__imp_GetLastError
0x180006ce5  mov     r9d, 1
0x180006ceb  lea     rdx, aCopysid; "CopySid"
0x180006cf2  mov     r8d, eax
0x180006cf5  call    WfpReportSysErrorAsWinError
0x180006cfa  mov     rbx, rax
0x180006cfd  test    rax, rax
0x180006d00  jnz     short loc_180006D50
0x180006d02  lea     rdx, aIkecopysid; "IkeCopySid"
0x180006d09  mov     rcx, rbx
0x180006d0c  mov     rdi, [rsp+38h+arg_0]
0x180006d11  mov     rbx, [rsp+38h+arg_8]
0x180006d16  add     rsp, 20h
0x180006d1a  pop     r14
0x180006d1c  pop     rsi
0x180006d1d  pop     rbp
0x180006d1e  jmp     IkeReturnError
0x180006d23  call    cs:__imp_HeapAlloc
0x180006d29  mov     [rsp+38h+arg_10], rax
0x180006d2e  mov     rdi, rax
0x180006d31  test    rax, rax
0x180006d34  jz      short loc_180006D64
0x180006d36  xor     ebx, ebx
0x180006d38  cmp     cs:gWfpTrackHeapAllocs, ebx
0x180006d3e  jz      loc_180006CBF
0x180006d44  lock inc cs:gWfpNumHeapAllocs
0x180006d4b  jmp     loc_180006CBF
0x180006d50  lea     rcx, [rsp+38h+arg_10]
0x180006d55  call    WfpMemFree
0x180006d5a  jmp     short loc_180006D02
0x180006d5c  and     eax, 1
0x180006d5f  jmp     loc_180006C7E
0x180006d64  mov     r8d, 0C0000017h
0x180006d6a  lea     rdx, aHeapalloc; "HeapAlloc"
0x180006d71  call    WfpReportSysErrorAsNtStatus
0x180006d76  mov     rbx, rax
0x180006d79  test    rax, rax
0x180006d7c  jz      loc_180006CBF
0x180006d82  lea     rdx, aWfpmemalloc25b; "WfpMemAlloc25B"
0x180006d89  mov     rcx, rax
0x180006d8c  call    WfpReportError
0x180006d91  jmp     loc_180006CBF
0x180006d96  mov     r8d, 0C0000017h
0x180006d9c  lea     rdx, aHeapalloc; "HeapAlloc"
0x180006da3  call    WfpReportSysErrorAsNtStatus
0x180006da8  mov     rbx, rax
0x180006dab  test    rax, rax
0x180006dae  jz      loc_180006CBF
0x180006db4  lea     rdx, aWfpmemalloc; "WfpMemAlloc"
0x180006dbb  mov     rcx, rax
0x180006dbe  call    WfpReportError
0x180006dc3  jmp     loc_180006CBF
0x180006dc8  mov     rcx, cs:gWfpHeap; hHeap
0x180006dcf  mov     r8, rax; lpMem
0x180006dd2  xor     edx, edx; dwFlags
0x180006dd4  call    cs:__imp_HeapSize
0x180006dda  lock add cs:gWfpHeapBytesAllocated, eax
0x180006de1  jmp     loc_180006CBF
```
