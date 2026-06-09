# BfeGetThreadPreferredUILanguages

- ea: `0x18000b0e0`
- end: `0x18000b393`
- name: `BfeGetThreadPreferredUILanguages`
- size: `691`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180007550`

## callees

- `0x180007e38`
- `0x18000b0e0`
- `0x18000b6a0`
- `0x18000c8a0`
- `0x18000dd70`
- `0x18000e898`
- `0x180011500`
- `0x180012bd0`
- `0x18003a298`

## import_xrefs

- `ntdll!RtlGetThreadPreferredUILanguages` at `0x18000b127`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x18000b315`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x18000b127`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x18000b315`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000b2d2`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000b2d2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b190`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b27b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b190`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b27b`

## string_xrefs

- `0x18000b345`: `BfeGetThreadPreferredUILanguages`
- `0x18000b328`: `RtlGetThreadPreferredUILanguages`

## pseudocode

```c
__int64 __fastcall BfeGetThreadPreferredUILanguages(_QWORD *a1)
{
  _QWORD *v2; // rdi
  unsigned int ThreadPreferredUILanguages; // eax
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // rbx
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 v9; // rdx
  __int64 v10; // rcx
  int v11; // r8d
  int v12; // ecx
  _QWORD *v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rax
  int v16; // eax
  _QWORD *v18; // [rsp+30h] [rbp-50h] BYREF
  int v19; // [rsp+38h] [rbp-48h] BYREF
  unsigned int v20; // [rsp+40h] [rbp-40h] BYREF
  int v21; // [rsp+44h] [rbp-3Ch] BYREF
  char v22[16]; // [rsp+48h] [rbp-38h] BYREF
  const char *v23; // [rsp+58h] [rbp-28h]
  __int64 v24; // [rsp+60h] [rbp-20h]
  int *v25; // [rsp+68h] [rbp-18h]
  __int64 v26; // [rsp+70h] [rbp-10h]

  v18 = 0;
  v21 = 0;
  v20 = 0;
  v2 = 0;
  ThreadPreferredUILanguages = RtlGetThreadPreferredUILanguages(40, &v21, 0, &v20);
  v5 = 0x80000000LL;
  v6 = ThreadPreferredUILanguages;
  if ( (int)(ThreadPreferredUILanguages + 0x80000000) < 0 || ThreadPreferredUILanguages == -1073741789 )
  {
    v7 = 0;
    if ( v20 )
    {
      if ( (Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 0x10) != 0 )
        IsEnabledDeviceUsageNoInline = Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 1;
      else
        IsEnabledDeviceUsageNoInline = Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline(
                                         0x80000000LL,
                                         v4,
                                         ThreadPreferredUILanguages);
      if ( IsEnabledDeviceUsageNoInline )
      {
        v18 = HeapAlloc(gWfpHeap, 8u, 0x18u);
        v2 = v18;
        if ( v18 )
        {
          if ( gWfpTrackHeapAllocs )
            _InterlockedIncrement(&gWfpNumHeapAllocs);
        }
        else
        {
          v7 = WfpReportSysErrorAsNtStatus(v10, "HeapAlloc", 3221225495LL);
          if ( v7 )
          {
            v12 = (int)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v11, 0, (__int64)"WfpMemAlloc25B", v7, v18);
            }
            if ( gWfpLogUserModeErrors && (byte_18007C665 & 1) != 0 )
            {
              v19 = v7;
              v25 = &v19;
              v23 = "WfpMemAlloc25B";
              v24 = 15;
              v26 = 4;
              McGenEventWrite_EtwEventWriteTransfer(v12, (unsigned int)WFP_USERMODE_ERROR, v11, 3, (__int64)v22);
            }
          }
        }
      }
      else
      {
        v13 = HeapAlloc(gWfpHeap, 8u, 0x18u);
        v18 = v13;
        v2 = v13;
        if ( v13 )
        {
          if ( gWfpTrackHeapBytes )
            _InterlockedAdd(&gWfpHeapBytesAllocated, HeapSize(gWfpHeap, 0, v13));
        }
        else
        {
          v15 = WfpReportSysErrorAsNtStatus(v14, "HeapAlloc", 3221225495LL);
          v7 = v15;
          if ( v15 )
            WfpReportError(v15, "WfpMemAlloc");
        }
      }
      if ( v7 )
        goto LABEL_30;
      v7 = WfpMemAllocArray(v20, v9, 8, v2 + 2);
      if ( v7 )
        goto LABEL_30;
      v16 = RtlGetThreadPreferredUILanguages(40, &v21, v2[2], &v20);
      if ( v16 < 0 )
      {
        v6 = (unsigned int)v16;
        goto LABEL_29;
      }
      *(_DWORD *)v2 = 8;
      *((_DWORD *)v2 + 1) = v21;
      *((_DWORD *)v2 + 2) = v20;
    }
    *a1 = v2;
    return v7;
  }
LABEL_29:
  v7 = WfpReportSysErrorAsNtStatus(v5, "RtlGetThreadPreferredUILanguages", v6);
  if ( v7 )
  {
LABEL_30:
    BfeFwpmLangInfoDestroy(&v18);
    WfpReportError(v7, "BfeGetThreadPreferredUILanguages");
  }
  return v7;
}

```

## disassembly

```asm
0x18000b0e0  mov     [rsp-18h+arg_10], rbx
0x18000b0e5  mov     [rsp-18h+arg_18], rsi
0x18000b0ea  push    rbp
0x18000b0eb  push    rdi
0x18000b0ec  push    r14
0x18000b0ee  mov     rbp, rsp
0x18000b0f1  sub     rsp, 80h
0x18000b0f8  mov     rax, cs:__security_cookie
0x18000b0ff  xor     rax, rsp
0x18000b102  mov     [rbp+var_8], rax
0x18000b106  xor     esi, esi
0x18000b108  lea     r9, [rbp+var_40]
0x18000b10c  mov     r14, rcx
0x18000b10f  mov     [rbp+var_50], rsi
0x18000b113  mov     ecx, 28h ; '('
0x18000b118  mov     [rbp+var_3C], esi
0x18000b11b  xor     r8d, r8d
0x18000b11e  mov     [rbp+var_40], esi
0x18000b121  lea     rdx, [rbp+var_3C]
0x18000b125  mov     edi, esi
0x18000b127  call    cs:__imp_RtlGetThreadPreferredUILanguages
0x18000b12e  nop     dword ptr [rax+rax+00h]
0x18000b133  mov     ecx, 80000000h
0x18000b138  mov     r8d, eax
0x18000b13b  add     eax, ecx
0x18000b13d  test    ecx, eax
0x18000b13f  jnz     short loc_18000B14E
0x18000b141  cmp     r8d, 0C0000023h
0x18000b148  jnz     loc_18000B328
0x18000b14e  mov     rbx, rsi
0x18000b151  cmp     [rbp+var_40], esi
0x18000b154  jbe     loc_18000B368
0x18000b15a  mov     eax, cs:Feature_BFE_MemAlloc_BugFixes_25B__private_featureState
0x18000b160  test    al, 10h
0x18000b162  jz      short loc_18000B169
0x18000b164  and     eax, 1
0x18000b167  jmp     short loc_18000B16E
0x18000b169  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline
0x18000b16e  mov     rcx, cs:gWfpHeap; hHeap
0x18000b175  mov     edx, 8; dwFlags
0x18000b17a  mov     r8d, 18h; dwBytes
0x18000b180  test    eax, eax
0x18000b182  jz      loc_18000B27B
0x18000b188  mov     [rsp+80h+arg_8], r15
0x18000b190  call    cs:__imp_HeapAlloc
0x18000b197  nop     dword ptr [rax+rax+00h]
0x18000b19c  mov     [rbp+var_50], rax
0x18000b1a0  mov     rdi, rax
0x18000b1a3  test    rax, rax
0x18000b1a6  jnz     loc_18000B262
0x18000b1ac  mov     r8d, 0C0000017h
0x18000b1b2  lea     rdx, aHeapalloc; "HeapAlloc"
0x18000b1b9  call    WfpReportSysErrorAsNtStatus
0x18000b1be  mov     rbx, rax
0x18000b1c1  test    rax, rax
0x18000b1c4  jz      loc_18000B271
0x18000b1ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b1d1  lea     rax, WPP_GLOBAL_Control
0x18000b1d8  lea     r15, aWfpmemalloc25b; "WfpMemAlloc25B"
0x18000b1df  cmp     rcx, rax
0x18000b1e2  jz      short loc_18000B20A
0x18000b1e4  cmp     byte ptr [rcx+19h], 2
0x18000b1e8  jb      short loc_18000B20A
0x18000b1ea  test    byte ptr [rcx+1Ch], 1
0x18000b1ee  jz      short loc_18000B20A
0x18000b1f0  mov     rcx, [rcx+10h]
0x18000b1f4  mov     edx, 1Ah
0x18000b1f9  mov     [rsp+80h+var_58], ebx
0x18000b1fd  xor     r9d, r9d
0x18000b200  mov     [rsp+80h+var_60], r15
0x18000b205  call    WPP_SF_Ssd
0x18000b20a  cmp     cs:gWfpLogUserModeErrors, esi
0x18000b210  jz      short loc_18000B271
0x18000b212  test    cs:byte_18007C665, 1
0x18000b219  jz      short loc_18000B271
0x18000b21b  lea     rax, [rbp+var_48]
0x18000b21f  mov     [rbp+var_48], ebx
0x18000b222  mov     [rbp+var_18], rax
0x18000b226  lea     rdx, WFP_USERMODE_ERROR
0x18000b22d  lea     rax, [rbp+var_38]
0x18000b231  mov     [rbp+var_28], r15
0x18000b235  mov     r9d, 3
0x18000b23b  mov     [rsp+80h+var_60], rax
0x18000b240  mov     [rbp+var_20], 0Fh
0x18000b248  mov     [rbp+var_10], 4
0x18000b250  call    McGenEventWrite_EtwEventWriteTransfer
0x18000b255  mov     r15, [rsp+80h+arg_8]
0x18000b25d  jmp     loc_18000B2E5
0x18000b262  cmp     cs:gWfpTrackHeapAllocs, ebx
0x18000b268  jz      short loc_18000B271
0x18000b26a  lock inc cs:gWfpNumHeapAllocs
0x18000b271  mov     r15, [rsp+80h+arg_8]
0x18000b279  jmp     short loc_18000B2E5
0x18000b27b  call    cs:__imp_HeapAlloc
0x18000b282  nop     dword ptr [rax+rax+00h]
0x18000b287  mov     [rbp+var_50], rax
0x18000b28b  mov     rdi, rax
0x18000b28e  test    rax, rax
0x18000b291  jnz     short loc_18000B2BE
0x18000b293  mov     r8d, 0C0000017h
0x18000b299  lea     rdx, aHeapalloc; "HeapAlloc"
0x18000b2a0  call    WfpReportSysErrorAsNtStatus
0x18000b2a5  mov     rbx, rax
0x18000b2a8  test    rax, rax
0x18000b2ab  jz      short loc_18000B2E5
0x18000b2ad  lea     rdx, aWfpmemalloc; "WfpMemAlloc"
0x18000b2b4  mov     rcx, rax
0x18000b2b7  call    WfpReportError
0x18000b2bc  jmp     short loc_18000B2E5
0x18000b2be  cmp     cs:gWfpTrackHeapBytes, ebx
0x18000b2c4  jz      short loc_18000B2E5
0x18000b2c6  mov     rcx, cs:gWfpHeap; hHeap
0x18000b2cd  mov     r8, rax; lpMem
0x18000b2d0  xor     edx, edx; dwFlags
0x18000b2d2  call    cs:__imp_HeapSize
0x18000b2d9  nop     dword ptr [rax+rax+00h]
0x18000b2de  lock add cs:gWfpHeapBytesAllocated, eax
0x18000b2e5  test    rbx, rbx
0x18000b2e8  jnz     short loc_18000B33C
0x18000b2ea  mov     ecx, [rbp+var_40]
0x18000b2ed  lea     r9, [rdi+10h]
0x18000b2f1  mov     r8d, 8
0x18000b2f7  call    WfpMemAllocArray
0x18000b2fc  mov     rbx, rax
0x18000b2ff  test    rax, rax
0x18000b302  jnz     short loc_18000B33C
0x18000b304  mov     r8, [rdi+10h]
0x18000b308  lea     r9, [rbp+var_40]
0x18000b30c  lea     rdx, [rbp+var_3C]
0x18000b310  mov     ecx, 28h ; '('
0x18000b315  call    cs:__imp_RtlGetThreadPreferredUILanguages
0x18000b31c  nop     dword ptr [rax+rax+00h]
0x18000b321  test    eax, eax
0x18000b323  jns     short loc_18000B356
0x18000b325  mov     r8d, eax
0x18000b328  lea     rdx, aRtlgetthreadpr; "RtlGetThreadPreferredUILanguages"
0x18000b32f  call    WfpReportSysErrorAsNtStatus
0x18000b334  mov     rbx, rax
0x18000b337  test    rax, rax
0x18000b33a  jz      short loc_18000B36B
0x18000b33c  lea     rcx, [rbp+var_50]
0x18000b340  call    BfeFwpmLangInfoDestroy
0x18000b345  lea     rdx, aBfegetthreadpr; "BfeGetThreadPreferredUILanguages"
0x18000b34c  mov     rcx, rbx
0x18000b34f  call    WfpReportError
0x18000b354  jmp     short loc_18000B36B
0x18000b356  mov     dword ptr [rdi], 8
0x18000b35c  mov     eax, [rbp+var_3C]
0x18000b35f  mov     [rdi+4], eax
0x18000b362  mov     eax, [rbp+var_40]
0x18000b365  mov     [rdi+8], eax
0x18000b368  mov     [r14], rdi
0x18000b36b  mov     rax, rbx
0x18000b36e  mov     rcx, [rbp+var_8]
0x18000b372  xor     rcx, rsp; StackCookie
0x18000b375  call    __security_check_cookie
0x18000b37a  lea     r11, [rsp+80h+var_s0]
0x18000b382  mov     rbx, [r11+30h]
0x18000b386  mov     rsi, [r11+38h]
0x18000b38a  mov     rsp, r11
0x18000b38d  pop     r14
0x18000b38f  pop     rdi
0x18000b390  pop     rbp
0x18000b391  retn
```
