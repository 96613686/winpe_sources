# BfeSecurityDescriptorEncode

- ea: `0x1800040a0`
- end: `0x180004384`
- name: `BfeSecurityDescriptorEncode`
- size: `740`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR AbsoluteSecurityDescriptor)`
- caller_count: `21`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800020d0`
- `0x180002500`
- `0x1800039a0`
- `0x180003fb0`
- `0x1800140f0`
- `0x180014800`
- `0x180014a00`
- `0x180014eb0`
- `0x180014fc0`
- `0x180015b70`
- `0x180016ad0`
- `0x180017980`
- `0x180017e40`
- `0x1800184d0`
- `0x180018ba0`
- `0x180019590`
- `0x180019aa0`
- `0x18001a790`
- `0x18001bba0`
- `0x18001ef70`
- `0x1800398c0`

## callees

- `0x1800040a0`
- `0x18000438c`
- `0x180007e38`
- `0x18000dd70`
- `0x18000e898`
- `0x180011500`
- `0x180012bd0`
- `0x18003a298`

## import_xrefs

- `ntdll!RtlLengthSecurityDescriptor` at `0x180004100`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180004100`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x18000430a`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x18000430a`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x18000411d`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x18000411d`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800042d6`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800042d6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004182`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000427a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004182`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000427a`

## string_xrefs

- `0x18000433b`: `BfeSecurityDescriptorEncode`
- `0x18000412d`: `RtlGetControlSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall BfeSecurityDescriptorEncode(PSECURITY_DESCRIPTOR AbsoluteSecurityDescriptor, __int64 a2, _QWORD *a3)
{
  __int64 v6; // rbx
  NTSTATUS ControlSecurityDescriptor; // eax
  __int64 v8; // rcx
  const char *v9; // rdx
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 v11; // rcx
  void *v12; // rdi
  int v13; // r8d
  int v14; // ecx
  void *v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rax
  int v19; // [rsp+30h] [rbp-98h] BYREF
  LPVOID v20; // [rsp+38h] [rbp-90h] BYREF
  ULONG dwBytes; // [rsp+40h] [rbp-88h] BYREF
  __int16 dwBytes_4; // [rsp+44h] [rbp-84h] BYREF
  ULONG Revision; // [rsp+48h] [rbp-80h] BYREF
  _BYTE v24[16]; // [rsp+50h] [rbp-78h] BYREF
  const char *v25; // [rsp+60h] [rbp-68h]
  __int64 v26; // [rsp+68h] [rbp-60h]
  int *v27; // [rsp+70h] [rbp-58h]
  __int64 v28; // [rsp+78h] [rbp-50h]

  *(_DWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
  *a3 = 0;
  v6 = 0;
  dwBytes = 0;
  Revision = 0;
  dwBytes_4 = 0;
  v20 = 0;
  if ( !AbsoluteSecurityDescriptor )
    return v6;
  dwBytes = RtlLengthSecurityDescriptor(AbsoluteSecurityDescriptor);
  ControlSecurityDescriptor = RtlGetControlSecurityDescriptor(
                                AbsoluteSecurityDescriptor,
                                (PSECURITY_DESCRIPTOR_CONTROL)&dwBytes_4,
                                &Revision);
  if ( ControlSecurityDescriptor < 0 )
  {
    v9 = "RtlGetControlSecurityDescriptor";
    goto LABEL_31;
  }
  if ( dwBytes_4 < 0 )
  {
    *(_QWORD *)(a2 + 8) = AbsoluteSecurityDescriptor;
LABEL_34:
    *(_DWORD *)a2 = dwBytes;
    return v6;
  }
  if ( (Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 0x10) != 0 )
    IsEnabledDeviceUsageNoInline = Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 1;
  else
    IsEnabledDeviceUsageNoInline = Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline();
  if ( IsEnabledDeviceUsageNoInline )
  {
    v20 = HeapAlloc(gWfpHeap, 0, dwBytes);
    v12 = v20;
    if ( v20 )
    {
      v6 = 0;
      if ( gWfpTrackHeapAllocs )
        _InterlockedIncrement(&gWfpNumHeapAllocs);
    }
    else
    {
      v6 = WfpReportSysErrorAsNtStatus(v11, "HeapAlloc", 3221225495LL);
      if ( v6 )
      {
        v14 = (int)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v13, 0, (__int64)"WfpMemAlloc25B", v6);
        }
        if ( gWfpLogUserModeErrors && (byte_18007C665 & 1) != 0 )
        {
          v19 = v6;
          v27 = &v19;
          v25 = "WfpMemAlloc25B";
          v26 = 15;
          v28 = 4;
          McGenEventWrite_EtwEventWriteTransfer(v14, (unsigned int)WFP_USERMODE_ERROR, v13, 3, (__int64)v24);
        }
      }
    }
  }
  else
  {
    v15 = HeapAlloc(gWfpHeap, 0, dwBytes);
    v20 = v15;
    v12 = v15;
    if ( v15 )
    {
      v6 = 0;
      if ( gWfpTrackHeapBytes )
        _InterlockedAdd(&gWfpHeapBytesAllocated, HeapSize(gWfpHeap, 0, v15));
    }
    else
    {
      v17 = WfpReportSysErrorAsNtStatus(v16, "HeapAlloc", 3221225495LL);
      v6 = v17;
      if ( v17 )
        WfpReportError(v17, "WfpMemAlloc");
    }
  }
  if ( v6 )
  {
    WfpReportError(v6, "WfpPoolAllocNonPaged");
LABEL_32:
    WfpMemFree(&v20);
    WfpReportError(v6, "BfeSecurityDescriptorEncode");
    return v6;
  }
  ControlSecurityDescriptor = RtlAbsoluteToSelfRelativeSD(AbsoluteSecurityDescriptor, v12, &dwBytes);
  if ( ControlSecurityDescriptor >= 0 )
  {
    *(_QWORD *)(a2 + 8) = v12;
    *a3 = v12;
    goto LABEL_34;
  }
  v9 = "RtlAbsoluteToSelfRelativeSD";
LABEL_31:
  v6 = WfpReportSysErrorAsNtStatus(v8, v9, (unsigned int)ControlSecurityDescriptor);
  if ( v6 )
    goto LABEL_32;
  return v6;
}

```

## disassembly

```asm
0x1800040a0  push    rbx
0x1800040a2  push    rbp
0x1800040a3  push    rsi
0x1800040a4  push    r14
0x1800040a6  push    r15
0x1800040a8  sub     rsp, 0A0h
0x1800040af  mov     rax, cs:__security_cookie
0x1800040b6  xor     rax, rsp
0x1800040b9  mov     [rsp+0C8h+var_48], rax
0x1800040c1  xor     r15d, r15d
0x1800040c4  mov     r14, r8
0x1800040c7  mov     [rdx], r15d
0x1800040ca  mov     rsi, rdx
0x1800040cd  mov     [rdx+8], r15
0x1800040d1  mov     rbp, rcx
0x1800040d4  mov     [r8], r15
0x1800040d7  mov     ebx, r15d
0x1800040da  mov     dword ptr [rsp+0C8h+dwBytes], r15d
0x1800040df  mov     [rsp+0C8h+Revision], r15d
0x1800040e4  mov     word ptr [rsp+0C8h+dwBytes+4], r15w
0x1800040ea  mov     [rsp+0C8h+var_90], r15
0x1800040ef  test    rcx, rcx
0x1800040f2  jz      loc_180004361
0x1800040f8  mov     [rsp+0C8h+var_30], rdi
0x180004100  call    cs:__imp_RtlLengthSecurityDescriptor
0x180004107  nop     dword ptr [rax+rax+00h]
0x18000410c  lea     r8, [rsp+0C8h+Revision]; Revision
0x180004111  mov     rcx, rbp; SecurityDescriptor
0x180004114  lea     rdx, [rsp+0C8h+dwBytes+4]; Control
0x180004119  mov     dword ptr [rsp+0C8h+dwBytes], eax
0x18000411d  call    cs:__imp_RtlGetControlSecurityDescriptor
0x180004124  nop     dword ptr [rax+rax+00h]
0x180004129  test    eax, eax
0x18000412b  jns     short loc_180004139
0x18000412d  lea     rdx, aRtlgetcontrols; "RtlGetControlSecurityDescriptor"
0x180004134  jmp     loc_180004321
0x180004139  mov     eax, 8000h
0x18000413e  test    word ptr [rsp+0C8h+dwBytes+4], ax
0x180004143  jz      short loc_18000414E
0x180004145  mov     [rsi+8], rbp
0x180004149  jmp     loc_180004353
0x18000414e  mov     ebx, dword ptr [rsp+0C8h+dwBytes]
0x180004152  mov     eax, cs:Feature_BFE_MemAlloc_BugFixes_25B__private_featureState
0x180004158  test    al, 10h
0x18000415a  jz      short loc_180004161
0x18000415c  and     eax, 1
0x18000415f  jmp     short loc_180004166
0x180004161  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline
0x180004166  mov     rcx, cs:gWfpHeap; hHeap
0x18000416d  xor     edx, edx; dwFlags
0x18000416f  mov     r8, rbx; dwBytes
0x180004172  test    eax, eax
0x180004174  jz      loc_18000427A
0x18000417a  mov     [rsp+0C8h+var_38], r12
0x180004182  call    cs:__imp_HeapAlloc
0x180004189  nop     dword ptr [rax+rax+00h]
0x18000418e  mov     [rsp+0C8h+var_90], rax
0x180004193  mov     rdi, rax
0x180004196  test    rax, rax
0x180004199  jnz     loc_18000425D
0x18000419f  mov     r8d, 0C0000017h
0x1800041a5  lea     rdx, aHeapalloc; "HeapAlloc"
0x1800041ac  call    WfpReportSysErrorAsNtStatus
0x1800041b1  mov     rbx, rax
0x1800041b4  test    rax, rax
0x1800041b7  jz      loc_180004270
0x1800041bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800041c4  lea     rax, WPP_GLOBAL_Control
0x1800041cb  lea     r12, aWfpmemalloc25b; "WfpMemAlloc25B"
0x1800041d2  cmp     rcx, rax
0x1800041d5  jz      short loc_1800041FD
0x1800041d7  cmp     byte ptr [rcx+19h], 2
0x1800041db  jb      short loc_1800041FD
0x1800041dd  test    byte ptr [rcx+1Ch], 1
0x1800041e1  jz      short loc_1800041FD
0x1800041e3  mov     rcx, [rcx+10h]
0x1800041e7  mov     edx, 1Ah
0x1800041ec  mov     [rsp+0C8h+var_A0], ebx
0x1800041f0  xor     r9d, r9d
0x1800041f3  mov     [rsp+0C8h+var_A8], r12
0x1800041f8  call    WPP_SF_Ssd
0x1800041fd  cmp     cs:gWfpLogUserModeErrors, r15d
0x180004204  jz      short loc_180004270
0x180004206  test    cs:byte_18007C665, 1
0x18000420d  jz      short loc_180004270
0x18000420f  lea     rax, [rsp+0C8h+var_98]
0x180004214  mov     [rsp+0C8h+var_98], ebx
0x180004218  mov     [rsp+0C8h+var_58], rax
0x18000421d  lea     rdx, WFP_USERMODE_ERROR
0x180004224  lea     rax, [rsp+0C8h+var_78]
0x180004229  mov     [rsp+0C8h+var_68], r12
0x18000422e  mov     r9d, 3
0x180004234  mov     [rsp+0C8h+var_A8], rax
0x180004239  mov     [rsp+0C8h+var_60], 0Fh
0x180004242  mov     [rsp+0C8h+var_50], 4
0x18000424b  call    McGenEventWrite_EtwEventWriteTransfer
0x180004250  mov     r12, [rsp+0C8h+var_38]
0x180004258  jmp     loc_1800042E9
0x18000425d  cmp     cs:gWfpTrackHeapAllocs, r15d
0x180004264  mov     rbx, r15
0x180004267  jz      short loc_180004270
0x180004269  lock inc cs:gWfpNumHeapAllocs
0x180004270  mov     r12, [rsp+0C8h+var_38]
0x180004278  jmp     short loc_1800042E9
0x18000427a  call    cs:__imp_HeapAlloc
0x180004281  nop     dword ptr [rax+rax+00h]
0x180004286  mov     [rsp+0C8h+var_90], rax
0x18000428b  mov     rdi, rax
0x18000428e  test    rax, rax
0x180004291  jnz     short loc_1800042BE
0x180004293  mov     r8d, 0C0000017h
0x180004299  lea     rdx, aHeapalloc; "HeapAlloc"
0x1800042a0  call    WfpReportSysErrorAsNtStatus
0x1800042a5  mov     rbx, rax
0x1800042a8  test    rax, rax
0x1800042ab  jz      short loc_1800042E9
0x1800042ad  lea     rdx, aWfpmemalloc; "WfpMemAlloc"
0x1800042b4  mov     rcx, rax
0x1800042b7  call    WfpReportError
0x1800042bc  jmp     short loc_1800042E9
0x1800042be  cmp     cs:gWfpTrackHeapBytes, r15d
0x1800042c5  mov     rbx, r15
0x1800042c8  jz      short loc_1800042E9
0x1800042ca  mov     rcx, cs:gWfpHeap; hHeap
0x1800042d1  mov     r8, rax; lpMem
0x1800042d4  xor     edx, edx; dwFlags
0x1800042d6  call    cs:__imp_HeapSize
0x1800042dd  nop     dword ptr [rax+rax+00h]
0x1800042e2  lock add cs:gWfpHeapBytesAllocated, eax
0x1800042e9  test    rbx, rbx
0x1800042ec  jz      short loc_1800042FF
0x1800042ee  lea     rdx, aWfppoolallocno; "WfpPoolAllocNonPaged"
0x1800042f5  mov     rcx, rbx
0x1800042f8  call    WfpReportError
0x1800042fd  jmp     short loc_180004331
0x1800042ff  lea     r8, [rsp+0C8h+dwBytes]; BufferLength
0x180004304  mov     rdx, rdi; SelfRelativeSecurityDescriptor
0x180004307  mov     rcx, rbp; AbsoluteSecurityDescriptor
0x18000430a  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x180004311  nop     dword ptr [rax+rax+00h]
0x180004316  test    eax, eax
0x180004318  jns     short loc_18000434C
0x18000431a  lea     rdx, aRtlabsolutetos; "RtlAbsoluteToSelfRelativeSD"
0x180004321  mov     r8d, eax
0x180004324  call    WfpReportSysErrorAsNtStatus
0x180004329  mov     rbx, rax
0x18000432c  test    rax, rax
0x18000432f  jz      short loc_180004359
0x180004331  lea     rcx, [rsp+0C8h+var_90]
0x180004336  call    WfpMemFree
0x18000433b  lea     rdx, aBfesecuritydes; "BfeSecurityDescriptorEncode"
0x180004342  mov     rcx, rbx
0x180004345  call    WfpReportError
0x18000434a  jmp     short loc_180004359
0x18000434c  mov     [rsi+8], rdi
0x180004350  mov     [r14], rdi
0x180004353  mov     eax, dword ptr [rsp+0C8h+dwBytes]
0x180004357  mov     [rsi], eax
0x180004359  mov     rdi, [rsp+0C8h+var_30]
0x180004361  mov     rax, rbx
0x180004364  mov     rcx, [rsp+0C8h+var_48]
0x18000436c  xor     rcx, rsp; StackCookie
0x18000436f  call    __security_check_cookie
0x180004374  add     rsp, 0A0h
0x18000437b  pop     r15
0x18000437d  pop     r14
0x18000437f  pop     rsi
0x180004380  pop     rbp
0x180004381  pop     rbx
0x180004382  retn
```
