# WfpStringCopy

- ea: `0x180006230`
- end: `0x180006484`
- name: `WfpStringCopy`
- size: `596`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `9`
- callee_count: `8`
- tags: ``

## callers

- `0x180004bdc`
- `0x18000648c`
- `0x180009bc0`
- `0x1800280f8`
- `0x180038964`
- `0x180038c38`
- `0x18003901c`
- `0x180049454`
- `0x18004959c`

## callees

- `0x180006230`
- `0x180007e38`
- `0x18000dd70`
- `0x18000e898`
- `0x180011500`
- `0x180012bd0`
- `0x18003a298`
- `0x18004a0d1`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180006402`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180006402`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800062c2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800063ad`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800062c2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800063ad`

## string_xrefs

- `0x180006429`: `WfpBufferCopy`
- `0x180006438`: `WfpStringCopy`

## pseudocode

```c
__int64 __fastcall WfpStringCopy(_WORD *Src, __int64 a2, void **a3)
{
  __int64 result; // rax
  __int64 v6; // rax
  SIZE_T v8; // rsi
  int IsEnabledDeviceUsageNoInline; // eax
  LPVOID v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rbx
  __int64 v13; // r8
  void *v14; // rcx
  void *v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rax
  int v18; // [rsp+30h] [rbp-58h] BYREF
  _BYTE v19[16]; // [rsp+38h] [rbp-50h] BYREF
  const char *v20; // [rsp+48h] [rbp-40h]
  __int64 v21; // [rsp+50h] [rbp-38h]
  int *v22; // [rsp+58h] [rbp-30h]
  __int64 v23; // [rsp+60h] [rbp-28h]

  result = 0;
  *a3 = 0;
  if ( Src )
  {
    v6 = -1;
    while ( Src[++v6] != 0 )
      ;
    v8 = 2 * v6 + 2;
    if ( 2 * v6 == -2 )
    {
      return 0;
    }
    else
    {
      if ( (Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 0x10) != 0 )
        IsEnabledDeviceUsageNoInline = Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 1;
      else
        IsEnabledDeviceUsageNoInline = Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline(
                                         Src,
                                         a2,
                                         a3);
      if ( IsEnabledDeviceUsageNoInline )
      {
        v10 = HeapAlloc(gWfpHeap, 0, v8);
        *a3 = v10;
        if ( v10 )
        {
          v12 = 0;
          if ( gWfpTrackHeapAllocs )
            _InterlockedIncrement(&gWfpNumHeapAllocs);
        }
        else
        {
          v12 = WfpReportSysErrorAsNtStatus(v11, "HeapAlloc", 3221225495LL);
          if ( v12 )
          {
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v13, 0, (__int64)"WfpMemAlloc25B", v12);
            }
            if ( gWfpLogUserModeErrors && (byte_18007C665 & 1) != 0 )
            {
              v18 = v12;
              v22 = &v18;
              v20 = "WfpMemAlloc25B";
              v21 = 15;
              v23 = 4;
              McGenEventWrite_EtwEventWriteTransfer((__int64)v14, (__int64)WFP_USERMODE_ERROR, v13, 3, (__int64)v19);
            }
          }
        }
      }
      else
      {
        v15 = HeapAlloc(gWfpHeap, 0, v8);
        *a3 = v15;
        if ( v15 )
        {
          v12 = 0;
          if ( gWfpTrackHeapBytes )
            _InterlockedAdd(&gWfpHeapBytesAllocated, HeapSize(gWfpHeap, 0, v15));
        }
        else
        {
          v17 = WfpReportSysErrorAsNtStatus(v16, "HeapAlloc", 3221225495LL);
          v12 = v17;
          if ( v17 )
            WfpReportError(v17, "WfpMemAlloc");
        }
      }
      if ( v12 )
      {
        WfpReportError(v12, "WfpPoolAllocNonPaged");
        WfpReportError(v12, "WfpBufferCopy");
        WfpReportError(v12, "WfpStringCopy");
      }
      else
      {
        memcpy_0(*a3, Src, v8);
      }
      return v12;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180006230  push    rdi
0x180006232  push    r14
0x180006234  sub     rsp, 78h
0x180006238  mov     rax, cs:__security_cookie
0x18000623f  xor     rax, rsp
0x180006242  mov     [rsp+88h+var_20], rax
0x180006247  xor     eax, eax
0x180006249  mov     r14, r8
0x18000624c  mov     [r8], rax
0x18000624f  mov     rdi, rcx
0x180006252  test    rcx, rcx
0x180006255  jz      loc_18000645A
0x18000625b  mov     [rsp+88h+arg_18], rsi
0x180006263  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000626a  nop     word ptr [rax+rax+00h]
0x180006270  cmp     word ptr [rcx+rax*2+2], 0
0x180006276  lea     rax, [rax+1]
0x18000627a  jnz     short loc_180006270
0x18000627c  lea     rsi, ds:2[rax*2]
0x180006284  test    rsi, rsi
0x180006287  jz      loc_180006480
0x18000628d  mov     [rsp+88h+arg_8], rbx
0x180006295  mov     eax, cs:Feature_BFE_MemAlloc_BugFixes_25B__private_featureState
0x18000629b  test    al, 10h
0x18000629d  jz      short loc_1800062A4
0x18000629f  and     eax, 1
0x1800062a2  jmp     short loc_1800062A9
0x1800062a4  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline
0x1800062a9  mov     rcx, cs:gWfpHeap; hHeap
0x1800062b0  xor     edx, edx; dwFlags
0x1800062b2  mov     r8, rsi; dwBytes
0x1800062b5  test    eax, eax
0x1800062b7  jz      loc_1800063AD
0x1800062bd  mov     [rsp+88h+var_18], r15
0x1800062c2  call    cs:__imp_HeapAlloc
0x1800062c9  nop     dword ptr [rax+rax+00h]
0x1800062ce  mov     [r14], rax
0x1800062d1  test    rax, rax
0x1800062d4  jnz     loc_180006395
0x1800062da  mov     r8d, 0C0000017h
0x1800062e0  lea     rdx, aHeapalloc; "HeapAlloc"
0x1800062e7  call    WfpReportSysErrorAsNtStatus
0x1800062ec  mov     rbx, rax
0x1800062ef  test    rax, rax
0x1800062f2  jz      loc_1800063A6
0x1800062f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800062ff  lea     rax, WPP_GLOBAL_Control
0x180006306  lea     r15, aWfpmemalloc25b; "WfpMemAlloc25B"
0x18000630d  cmp     rcx, rax
0x180006310  jz      short loc_180006338
0x180006312  cmp     byte ptr [rcx+19h], 2
0x180006316  jb      short loc_180006338
0x180006318  test    byte ptr [rcx+1Ch], 1
0x18000631c  jz      short loc_180006338
0x18000631e  mov     rcx, [rcx+10h]
0x180006322  mov     edx, 1Ah
0x180006327  mov     [rsp+88h+var_60], ebx
0x18000632b  xor     r9d, r9d
0x18000632e  mov     [rsp+88h+var_68], r15
0x180006333  call    WPP_SF_Ssd
0x180006338  cmp     cs:gWfpLogUserModeErrors, 0
0x18000633f  jz      short loc_1800063A6
0x180006341  test    cs:byte_18007C665, 1
0x180006348  jz      short loc_1800063A6
0x18000634a  lea     rax, [rsp+88h+var_58]
0x18000634f  mov     [rsp+88h+var_58], ebx
0x180006353  mov     [rsp+88h+var_30], rax
0x180006358  lea     rdx, WFP_USERMODE_ERROR
0x18000635f  lea     rax, [rsp+88h+var_50]
0x180006364  mov     [rsp+88h+var_40], r15
0x180006369  mov     r9d, 3
0x18000636f  mov     [rsp+88h+var_68], rax
0x180006374  mov     [rsp+88h+var_38], 0Fh
0x18000637d  mov     [rsp+88h+var_28], 4
0x180006386  call    McGenEventWrite_EtwEventWriteTransfer
0x18000638b  mov     r15, [rsp+88h+var_18]
0x180006390  jmp     loc_180006415
0x180006395  xor     ebx, ebx
0x180006397  cmp     cs:gWfpTrackHeapAllocs, ebx
0x18000639d  jz      short loc_1800063A6
0x18000639f  lock inc cs:gWfpNumHeapAllocs
0x1800063a6  mov     r15, [rsp+88h+var_18]
0x1800063ab  jmp     short loc_180006415
0x1800063ad  call    cs:__imp_HeapAlloc
0x1800063b4  nop     dword ptr [rax+rax+00h]
0x1800063b9  mov     [r14], rax
0x1800063bc  test    rax, rax
0x1800063bf  jnz     short loc_1800063EC
0x1800063c1  mov     r8d, 0C0000017h
0x1800063c7  lea     rdx, aHeapalloc; "HeapAlloc"
0x1800063ce  call    WfpReportSysErrorAsNtStatus
0x1800063d3  mov     rbx, rax
0x1800063d6  test    rax, rax
0x1800063d9  jz      short loc_180006415
0x1800063db  lea     rdx, aWfpmemalloc; "WfpMemAlloc"
0x1800063e2  mov     rcx, rax
0x1800063e5  call    WfpReportError
0x1800063ea  jmp     short loc_180006415
0x1800063ec  xor     ebx, ebx
0x1800063ee  cmp     cs:gWfpTrackHeapBytes, ebx
0x1800063f4  jz      short loc_180006415
0x1800063f6  mov     rcx, cs:gWfpHeap; hHeap
0x1800063fd  mov     r8, rax; lpMem
0x180006400  xor     edx, edx; dwFlags
0x180006402  call    cs:__imp_HeapSize
0x180006409  nop     dword ptr [rax+rax+00h]
0x18000640e  lock add cs:gWfpHeapBytesAllocated, eax
0x180006415  test    rbx, rbx
0x180006418  jz      short loc_180006470
0x18000641a  lea     rdx, aWfppoolallocno; "WfpPoolAllocNonPaged"
0x180006421  mov     rcx, rbx
0x180006424  call    WfpReportError
0x180006429  lea     rdx, aWfpbuffercopy; "WfpBufferCopy"
0x180006430  mov     rcx, rbx
0x180006433  call    WfpReportError
0x180006438  lea     rdx, aWfpstringcopy; "WfpStringCopy"
0x18000643f  mov     rcx, rbx
0x180006442  call    WfpReportError
0x180006447  mov     rax, rbx
0x18000644a  mov     rbx, [rsp+88h+arg_8]
0x180006452  mov     rsi, [rsp+88h+arg_18]
0x18000645a  mov     rcx, [rsp+88h+var_20]
0x18000645f  xor     rcx, rsp; StackCookie
0x180006462  call    __security_check_cookie
0x180006467  add     rsp, 78h
0x18000646b  pop     r14
0x18000646d  pop     rdi
0x18000646e  retn
0x180006470  mov     rcx, [r14]; void *
0x180006473  mov     r8, rsi; Size
0x180006476  mov     rdx, rdi; Src
0x180006479  call    memcpy_0
0x18000647e  jmp     short loc_180006447
0x180006480  xor     eax, eax
0x180006482  jmp     short loc_180006452
```
