# WfpAuditPolicyNotifyCreate

- ea: `0x180015fb4`
- end: `0x18001629d`
- name: `WfpAuditPolicyNotifyCreate`
- size: `745`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x18011763c`

## callees

- `0x180003cf0`
- `0x1800061ec`
- `0x180010db0`
- `0x180015fb4`
- `0x1800163b0`
- `0x180016534`
- `0x1800165c0`
- `0x18004882c`
- `0x180050850`
- `0x180052ae8`
- `0x180117a64`
- `0x180117fa8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800161b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001621f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800161b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001621f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800161a1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800161a1`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800160a4`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800160a4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016007`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016058`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016007`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016058`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180016210`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180016210`
- `SspiCli!LsaRegisterPolicyChangeNotification` at `0x1800161d8`
- `SspiCli!LsaRegisterPolicyChangeNotification` at `0x1800161d8`

## string_xrefs

- `0x1800161b6`: `CreateEventW`
- `0x180016105`: `WfpBufferCopy`
- `0x180016271`: `WfpAuditPolicyNotifyCreate`

## pseudocode

```c
__int64 __fastcall WfpAuditPolicyNotifyCreate(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, __int64 *a6)
{
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 v7; // rcx
  __int64 v8; // rdi
  __int64 v9; // rax
  __int64 v10; // rbx
  const char *v11; // rdx
  const void *v12; // rax
  __int64 v13; // rcx
  unsigned __int128 v14; // rax
  __int64 v15; // rax
  __int64 v16; // r8
  int v17; // esi
  __int64 i; // r8
  __int64 v19; // rdx
  HANDLE EventW; // rax
  DWORD LastError; // eax
  __int64 v22; // rcx
  const char *v23; // rdx
  __int64 v24; // rax
  NTSTATUS v25; // eax
  __int64 v26; // rcx
  __int64 v27; // rax
  _QWORD v29[2]; // [rsp+30h] [rbp-58h] BYREF

  *a6 = 0;
  if ( (Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 0x10) != 0 )
    IsEnabledDeviceUsageNoInline = Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 1;
  else
    IsEnabledDeviceUsageNoInline = Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline(a1);
  if ( IsEnabledDeviceUsageNoInline )
  {
    v29[0] = HeapAlloc(gWfpHeap, 8u, 0x58u);
    v8 = v29[0];
    if ( !v29[0] )
    {
      v9 = WfpReportSysErrorAsNtStatus(v7, "HeapAlloc", 3221225495LL);
      v10 = v9;
      if ( !v9 )
        goto LABEL_16;
      v11 = "WfpMemAlloc25B";
      goto LABEL_8;
    }
    v10 = 0;
    if ( gWfpTrackHeapAllocs )
      _InterlockedIncrement(&gWfpNumHeapAllocs);
  }
  else
  {
    v12 = HeapAlloc(gWfpHeap, 8u, 0x58u);
    v29[0] = v12;
    v8 = (__int64)v12;
    if ( v12 )
    {
      v10 = 0;
      if ( gWfpTrackHeapBytes )
        _InterlockedAdd(&gWfpHeapBytesAllocated, HeapSize(gWfpHeap, 0, v12));
    }
    else
    {
      v9 = WfpReportSysErrorAsNtStatus(v13, "HeapAlloc", 3221225495LL);
      v10 = v9;
      if ( v9 )
      {
        v11 = "WfpMemAlloc";
LABEL_8:
        WfpReportError(v9, v11);
      }
    }
  }
LABEL_16:
  if ( v10 )
    goto LABEL_35;
  v29[1] = 0;
  *(_DWORD *)(v8 + 16) = 3;
  v14 = 3 * (unsigned __int128)0x10u;
  if ( !is_mul_ok(3u, 0x10u) )
  {
    v24 = WfpReportSysErrorAsHResult(3, "ULongLongMult", 2147942934LL, 1);
    goto LABEL_34;
  }
  *(_QWORD *)(v8 + 24) = *((_QWORD *)&v14 + 1);
  v15 = WfpMemAlloc(0x30u, DWORD2(v14));
  v10 = v15;
  if ( v15 )
  {
    WfpReportError(v15, "WfpPoolAllocNonPaged");
    WfpReportError(v10, "WfpBufferCopy");
    goto LABEL_35;
  }
  memcpy_0(*(void **)(v8 + 24), &IKE_AUDIT_POLICY_INFO, 0x30u);
  v10 = WfpMemAllocArray(3, 16, v16, v8 + 32);
  if ( !v10 )
  {
    v17 = 0;
    for ( i = 0; i != 3; ++i )
    {
      v19 = 2 * i;
      *(GUID *)(*(_QWORD *)(v8 + 32) + v19 * 8) = *(&IKE_AUDIT_POLICY_INFO)[v19];
      v17 |= *((_DWORD *)&IKE_AUDIT_POLICY_INFO + 2 * v19 + 2) | *((_DWORD *)&IKE_AUDIT_POLICY_INFO + 2 * v19 + 3);
    }
    *(_QWORD *)(v8 + 40) = WfpAuditOnAuditFlagsChange;
    *(_QWORD *)(v8 + 48) = 0;
    EventW = CreateEventW(0, 0, 0, 0);
    *(_QWORD *)(v8 + 56) = EventW;
    if ( !EventW )
    {
      LastError = GetLastError();
      v23 = "CreateEventW";
LABEL_27:
      v24 = WfpReportSysErrorAsWinError(v22, v23, LastError, 1);
      goto LABEL_34;
    }
    v25 = LsaRegisterPolicyChangeNotification(PolicyNotifyAuditEventsInformation, EventW);
    if ( v25 >= 0 )
    {
      *(_DWORD *)(v8 + 64) = 1;
      v27 = RegisterWaitForSingleObjectEx(*(_QWORD *)(v8 + 56), WfpAuditPolicyNotifyOnChange, v8, 0xFFFFFFFFLL, 16);
      *(_QWORD *)(v8 + 72) = v27;
      if ( v27 )
      {
        *(_DWORD *)(v8 + 80) = ~v17;
        WfpAuditPolicyNotifyOnChange(v8);
        *a6 = v8;
        return v10;
      }
      LastError = GetLastError();
      v23 = "RegisterWaitForSingleObjectEx";
      goto LABEL_27;
    }
    v24 = WfpReportSysErrorAsNtStatus(v26, "LsaRegisterPolicyChangeNotification", (unsigned int)v25);
LABEL_34:
    v10 = v24;
    if ( !v24 )
      return v10;
  }
LABEL_35:
  WfpAuditPolicyNotifyDestroy(v29);
  if ( v10 )
    WfpReportError(v10, "WfpAuditPolicyNotifyCreate");
  return v10;
}

```

## disassembly

```asm
0x180015fb4  push    rbx
0x180015fb6  push    rbp
0x180015fb7  push    rsi
0x180015fb8  push    rdi
0x180015fb9  push    r14
0x180015fbb  push    r15
0x180015fbd  sub     rsp, 58h
0x180015fc1  mov     rax, cs:__security_cookie
0x180015fc8  xor     rax, rsp
0x180015fcb  mov     [rsp+88h+var_48], rax
0x180015fd0  mov     r15, [rsp+88h+arg_28]
0x180015fd8  mov     qword ptr [r15], 0
0x180015fdf  mov     eax, cs:Feature_BFE_MemAlloc_BugFixes_25B__private_featureState
0x180015fe5  test    al, 10h
0x180015fe7  jz      short loc_180015FEE
0x180015fe9  and     eax, 1
0x180015fec  jmp     short loc_180015FF3
0x180015fee  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline
0x180015ff3  mov     rcx, cs:gWfpHeap; hHeap
0x180015ffa  mov     edx, 8; dwFlags
0x180015fff  lea     r8d, [rdx+50h]; dwBytes
0x180016003  test    eax, eax
0x180016005  jz      short loc_180016058
0x180016007  call    cs:__imp_HeapAlloc
0x18001600d  mov     [rsp+88h+var_58], rax
0x180016012  mov     rdi, rax
0x180016015  test    rax, rax
0x180016018  jnz     short loc_180016045
0x18001601a  mov     r8d, 0C0000017h
0x180016020  lea     rdx, aHeapalloc; "HeapAlloc"
0x180016027  call    WfpReportSysErrorAsNtStatus
0x18001602c  mov     rbx, rax
0x18001602f  test    rax, rax
0x180016032  jz      short loc_1800160B1
0x180016034  lea     rdx, aWfpmemalloc25b; "WfpMemAlloc25B"
0x18001603b  mov     rcx, rax
0x18001603e  call    WfpReportError
0x180016043  jmp     short loc_1800160B1
0x180016045  xor     ebx, ebx
0x180016047  cmp     cs:gWfpTrackHeapAllocs, ebx
0x18001604d  jz      short loc_1800160B1
0x18001604f  lock inc cs:gWfpNumHeapAllocs
0x180016056  jmp     short loc_1800160B1
0x180016058  call    cs:__imp_HeapAlloc
0x18001605e  mov     [rsp+88h+var_58], rax
0x180016063  mov     rdi, rax
0x180016066  test    rax, rax
0x180016069  jnz     short loc_18001608E
0x18001606b  mov     r8d, 0C0000017h
0x180016071  lea     rdx, aHeapalloc; "HeapAlloc"
0x180016078  call    WfpReportSysErrorAsNtStatus
0x18001607d  mov     rbx, rax
0x180016080  test    rax, rax
0x180016083  jz      short loc_1800160B1
0x180016085  lea     rdx, aWfpmemalloc; "WfpMemAlloc"
0x18001608c  jmp     short loc_18001603B
0x18001608e  xor     ebx, ebx
0x180016090  cmp     cs:gWfpTrackHeapBytes, ebx
0x180016096  jz      short loc_1800160B1
0x180016098  mov     rcx, cs:gWfpHeap; hHeap
0x18001609f  mov     r8, rax; lpMem
0x1800160a2  xor     edx, edx; dwFlags
0x1800160a4  call    cs:__imp_HeapSize
0x1800160aa  lock add cs:gWfpHeapBytesAllocated, eax
0x1800160b1  test    rbx, rbx
0x1800160b4  jnz     loc_180016262
0x1800160ba  lea     ecx, [rbx+3]
0x1800160bd  mov     [rsp+88h+var_50], rbx
0x1800160c2  lea     eax, [rbx+10h]
0x1800160c5  mov     [rdi+10h], ecx
0x1800160c8  mul     rcx
0x1800160cb  mov     rbp, rax
0x1800160ce  test    rdx, rdx
0x1800160d1  jnz     loc_180016242
0x1800160d7  lea     rsi, [rdi+18h]
0x1800160db  mov     [rsi], rdx
0x1800160de  test    rax, rax
0x1800160e1  jz      short loc_180016130
0x1800160e3  mov     r8, rsi
0x1800160e6  mov     rcx, rax; dwBytes
0x1800160e9  call    WfpMemAlloc
0x1800160ee  mov     rbx, rax
0x1800160f1  test    rax, rax
0x1800160f4  jz      short loc_180016119
0x1800160f6  lea     rdx, aWfppoolallocno; "WfpPoolAllocNonPaged"
0x1800160fd  mov     rcx, rax
0x180016100  call    WfpReportError
0x180016105  lea     rdx, aWfpbuffercopy; "WfpBufferCopy"
0x18001610c  mov     rcx, rbx
0x18001610f  call    WfpReportError
0x180016114  jmp     loc_180016262
0x180016119  mov     rcx, [rsi]; void *
0x18001611c  lea     rdx, IKE_AUDIT_POLICY_INFO; Src
0x180016123  mov     r8, rbp; Size
0x180016126  call    memcpy_0
0x18001612b  mov     ecx, 3
0x180016130  mov     ebp, 10h
0x180016135  lea     r9, [rdi+20h]
0x180016139  mov     edx, ebp
0x18001613b  call    WfpMemAllocArray
0x180016140  mov     rbx, rax
0x180016143  test    rax, rax
0x180016146  jnz     loc_180016262
0x18001614c  xor     esi, esi
0x18001614e  lea     r9, IKE_AUDIT_POLICY_INFO
0x180016155  xor     r8d, r8d
0x180016158  mov     rax, [rdi+20h]
0x18001615c  mov     rdx, r8
0x18001615f  shl     rdx, 4
0x180016163  inc     r8
0x180016166  mov     rcx, [rdx+r9]
0x18001616a  movups  xmm0, xmmword ptr [rcx]
0x18001616d  movdqu  xmmword ptr [rax+rdx], xmm0
0x180016172  mov     eax, [rdx+r9+0Ch]
0x180016177  or      eax, [rdx+r9+8]
0x18001617c  or      esi, eax
0x18001617e  cmp     r8, 3
0x180016182  jnz     short loc_180016158
0x180016184  lea     rax, WfpAuditOnAuditFlagsChange
0x18001618b  xor     r9d, r9d; lpName
0x18001618e  mov     [rdi+28h], rax
0x180016192  xor     r8d, r8d; bInitialState
0x180016195  xor     edx, edx; bManualReset
0x180016197  mov     qword ptr [rdi+30h], 0
0x18001619f  xor     ecx, ecx; lpEventAttributes
0x1800161a1  call    cs:__imp_CreateEventW
0x1800161a7  mov     [rdi+38h], rax
0x1800161ab  test    rax, rax
0x1800161ae  jnz     short loc_1800161D0
0x1800161b0  call    cs:__imp_GetLastError
0x1800161b6  lea     rdx, aCreateeventw; "CreateEventW"
0x1800161bd  mov     r9d, 1
0x1800161c3  mov     r8d, eax
0x1800161c6  call    WfpReportSysErrorAsWinError
0x1800161cb  jmp     loc_18001625A
0x1800161d0  mov     rdx, rax; NotificationEventHandle
0x1800161d3  mov     ecx, 1; InformationClass
0x1800161d8  call    cs:__imp_LsaRegisterPolicyChangeNotification
0x1800161de  test    eax, eax
0x1800161e0  jns     short loc_1800161F3
0x1800161e2  mov     r8d, eax
0x1800161e5  lea     rdx, aLsaregisterpol_0; "LsaRegisterPolicyChangeNotification"
0x1800161ec  call    WfpReportSysErrorAsNtStatus
0x1800161f1  jmp     short loc_18001625A
0x1800161f3  mov     dword ptr [rdi+40h], 1
0x1800161fa  lea     rdx, WfpAuditPolicyNotifyOnChange
0x180016201  mov     rcx, [rdi+38h]
0x180016205  or      r9d, 0FFFFFFFFh
0x180016209  mov     r8, rdi
0x18001620c  mov     [rsp+88h+var_68], ebp
0x180016210  call    cs:__imp_RegisterWaitForSingleObjectEx
0x180016216  mov     [rdi+48h], rax
0x18001621a  test    rax, rax
0x18001621d  jnz     short loc_18001622E
0x18001621f  call    cs:__imp_GetLastError
0x180016225  lea     rdx, aRegisterwaitfo; "RegisterWaitForSingleObjectEx"
0x18001622c  jmp     short loc_1800161BD
0x18001622e  not     esi
0x180016230  xor     edx, edx
0x180016232  mov     rcx, rdi
0x180016235  mov     [rdi+50h], esi
0x180016238  call    WfpAuditPolicyNotifyOnChange
0x18001623d  mov     [r15], rdi
0x180016240  jmp     short loc_180016280
0x180016242  mov     r9d, 1
0x180016248  lea     rdx, aUlonglongmult; "ULongLongMult"
0x18001624f  mov     r8d, 80070216h
0x180016255  call    WfpReportSysErrorAsHResult
0x18001625a  mov     rbx, rax
0x18001625d  test    rax, rax
0x180016260  jz      short loc_180016280
0x180016262  lea     rcx, [rsp+88h+var_58]
0x180016267  call    WfpAuditPolicyNotifyDestroy
0x18001626c  test    rbx, rbx
0x18001626f  jz      short loc_180016280
0x180016271  lea     rdx, aWfpauditpolicy; "WfpAuditPolicyNotifyCreate"
0x180016278  mov     rcx, rbx
0x18001627b  call    WfpReportError
0x180016280  mov     rax, rbx
0x180016283  mov     rcx, [rsp+88h+var_48]
0x180016288  xor     rcx, rsp; StackCookie
0x18001628b  call    __security_check_cookie
0x180016290  add     rsp, 58h
0x180016294  pop     r15
0x180016296  pop     r14
0x180016298  pop     rdi
0x180016299  pop     rsi
0x18001629a  pop     rbp
0x18001629b  pop     rbx
0x18001629c  retn
```
