# IkeIfrCleanupStaleTunnels

- ea: `0x18004f598`
- end: `0x18004f887`
- name: `IkeIfrCleanupStaleTunnels`
- size: `751`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting`

## callers

- `0x180065190`

## callees

- `0x1800037c4`
- `0x18000b890`
- `0x18001afe0`
- `0x18001b970`
- `0x180020c2c`
- `0x1800488f0`
- `0x18004890c`
- `0x18004f598`
- `0x18004ff88`
- `0x180050850`
- `0x1800510ee`
- `0x18005bc40`
- `0x1800658ec`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004f666`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004f666`
- `ntdll!RtlRemoveEntryHashTable` at `0x18004f7b9`
- `ntdll!RtlRemoveEntryHashTable` at `0x18004f7b9`
- `ntdll!RtlInitEnumerationHashTable` at `0x18004f68b`
- `ntdll!RtlInitEnumerationHashTable` at `0x18004f68b`
- `ntdll!RtlEndEnumerationHashTable` at `0x18004f80b`
- `ntdll!RtlEndEnumerationHashTable` at `0x18004f80b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f7aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f7e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f814`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f7aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f7e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f814`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f676`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f6ac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f676`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f6ac`

## pseudocode

```c
void IkeIfrCleanupStaleTunnels()
{
  __int64 v0; // rcx
  LPCRITICAL_SECTION v1; // rsi
  __int64 v2; // rdi
  __int64 TlsPeerAddr; // rbx
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  int TlsMmLuid; // eax
  struct _RTL_CRITICAL_SECTION *v9; // r12
  LPCRITICAL_SECTION v10; // r15
  __int64 v11; // rsi
  struct _RTL_CRITICAL_SECTION *v12; // r14
  __int64 v13; // rcx
  __int64 v14; // rdi
  __int64 v15; // rbx
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  int v20; // eax
  _QWORD *v21; // rax
  _QWORD *v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rdi
  __int64 v26; // rbx
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // r8
  __int64 v30; // r9
  int v31; // eax
  __int64 v32; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD *v33; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v34; // [rsp+50h] [rbp-B0h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+58h] [rbp-A8h] BYREF
  _OWORD v36[3]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v37[160]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v38[160]; // [rsp+130h] [rbp+30h] BYREF

  v32 = 0;
  memset(v36, 0, sizeof(v36));
  memset_0(v38, 0, sizeof(v38));
  memset_0(v37, 0, sizeof(v37));
  v1 = gIkeExtGlobals;
  SystemTimeAsFileTime = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v2 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    TlsPeerAddr = IkeGetTlsPeerAddr(v0);
    TlsMmLuid = IkeGetTlsMmLuid(v5, v4, v6, v7);
    WPP_SF_iS(v2, 19, (unsigned int)WPP_0162bb2a8b4239af156c6f597e3eee45_Traceguids, TlsMmLuid, TlsPeerAddr);
  }
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v9 = (LPCRITICAL_SECTION)((char *)v1 + 3848);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v1 + 3848));
  v10 = v1 + 95;
  RtlInitEnumerationHashTable(&v1[95], (char *)v36 + 8);
  *(_QWORD *)&v36[0] = v1 + 95;
  while ( (unsigned int)WfpHashtableIteratorGetNext(v36, &v32) )
  {
    v11 = v32;
    v34 = v32;
    v12 = (struct _RTL_CRITICAL_SECTION *)(v32 + 24);
    EnterCriticalSection((LPCRITICAL_SECTION)(v32 + 24));
    if ( SystemTimeAsFileTime.dwLowDateTime
       + ((SystemTimeAsFileTime.dwHighDateTime - (unsigned __int64)*(unsigned int *)(v11 + 204)) << 32)
       - *(unsigned int *)(v11 + 200) < 0x10C388D000LL )
    {
      LeaveCriticalSection(v12);
    }
    else
    {
      IkeAddrGetAddrString(v11 + 76, v38);
      IkeAddrGetAddrString(v11 + 136, v37);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v14 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v15 = IkeGetTlsPeerAddr(v13);
        v20 = IkeGetTlsMmLuid(v17, v16, v18, v19);
        WPP_SF_iSSS(
          v14,
          20,
          (unsigned int)WPP_0162bb2a8b4239af156c6f597e3eee45_Traceguids,
          v20,
          v15,
          (__int64)v38,
          (__int64)v37);
      }
      while ( 1 )
      {
        v21 = (_QWORD *)(v11 + 208);
        v22 = *(_QWORD **)(v11 + 208);
        if ( v22 == (_QWORD *)(v11 + 208) )
          break;
        if ( (_QWORD *)v22[1] != v21 || (v23 = *v22, *(_QWORD **)(*v22 + 8LL) != v22) )
          __fastfail(3u);
        *v21 = v23;
        *(_QWORD *)(v23 + 8) = v21;
        v33 = v22;
        IkeIfrFireEvent(v22, v11);
        WfpMemFree(&v33);
      }
      LeaveCriticalSection(v12);
      RtlRemoveEntryHashTable(v10, v11, 0);
      WfpRestructureHashtable(v10);
      if ( *(_DWORD *)(v11 + 72) )
        WfpCriticalSectionDestroy(v12);
      WfpMemFree(&v34);
    }
  }
  RtlEndEnumerationHashTable(*(_QWORD *)&v36[0], (char *)v36 + 8);
  LeaveCriticalSection(v9);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v25 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v26 = IkeGetTlsPeerAddr(v24);
    v31 = IkeGetTlsMmLuid(v28, v27, v29, v30);
    WPP_SF_iS(v25, 21, (unsigned int)WPP_0162bb2a8b4239af156c6f597e3eee45_Traceguids, v31, v26);
  }
}

```

## disassembly

```asm
0x18004f598  push    rbp
0x18004f59a  push    rbx
0x18004f59b  push    rsi
0x18004f59c  push    rdi
0x18004f59d  push    r12
0x18004f59f  push    r14
0x18004f5a1  push    r15
0x18004f5a3  lea     rbp, [rsp-0E0h]
0x18004f5ab  sub     rsp, 1E0h
0x18004f5b2  mov     rax, cs:__security_cookie
0x18004f5b9  xor     rax, rsp
0x18004f5bc  mov     [rbp+110h+var_40], rax
0x18004f5c3  xorps   xmm0, xmm0
0x18004f5c6  mov     [rsp+210h+var_1D0], 0
0x18004f5cf  mov     ebx, 0A0h
0x18004f5d4  lea     rcx, [rbp+110h+var_E0]; void *
0x18004f5d8  mov     r8d, ebx; Size
0x18004f5db  xor     edx, edx; Val
0x18004f5dd  movups  [rsp+210h+var_1B0], xmm0
0x18004f5e2  movups  [rsp+210h+var_1A0], xmm0
0x18004f5e7  movups  [rbp+110h+var_190], xmm0
0x18004f5eb  call    memset_0
0x18004f5f0  mov     r8d, ebx; Size
0x18004f5f3  lea     rcx, [rbp+110h+var_180]; void *
0x18004f5f7  xor     edx, edx; Val
0x18004f5f9  call    memset_0
0x18004f5fe  mov     rsi, cs:gIkeExtGlobals
0x18004f605  mov     qword ptr [rsp+210h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18004f60e  mov     rdi, cs:WPP_GLOBAL_Control
0x18004f615  lea     rbx, WPP_GLOBAL_Control
0x18004f61c  cmp     rdi, rbx
0x18004f61f  jz      short loc_18004F661
0x18004f621  cmp     byte ptr [rdi+19h], 4
0x18004f625  jb      short loc_18004F661
0x18004f627  test    byte ptr [rdi+1Ch], 10h
0x18004f62b  jz      short loc_18004F661
0x18004f62d  mov     rdi, [rdi+10h]
0x18004f631  call    IkeGetTlsPeerAddr
0x18004f636  mov     rbx, rax
0x18004f639  call    IkeGetTlsMmLuid
0x18004f63e  mov     r9, rax
0x18004f641  mov     [rsp+210h+var_1F0], rbx
0x18004f646  mov     edx, 13h
0x18004f64b  lea     r8, WPP_0162bb2a8b4239af156c6f597e3eee45_Traceguids
0x18004f652  mov     rcx, rdi
0x18004f655  call    WPP_SF_iS
0x18004f65a  lea     rbx, WPP_GLOBAL_Control
0x18004f661  lea     rcx, [rsp+210h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18004f666  call    cs:__imp_GetSystemTimeAsFileTime
0x18004f66c  lea     r12, [rsi+0F08h]
0x18004f673  mov     rcx, r12; lpCriticalSection
0x18004f676  call    cs:__imp_EnterCriticalSection
0x18004f67c  lea     r15, [rsi+0ED8h]
0x18004f683  mov     rcx, r15
0x18004f686  lea     rdx, [rsp+210h+var_1B0+8]
0x18004f68b  call    cs:__imp_RtlInitEnumerationHashTable
0x18004f691  mov     qword ptr [rsp+210h+var_1B0], r15
0x18004f696  jmp     loc_18004F7EA
0x18004f69b  mov     rsi, [rsp+210h+var_1D0]
0x18004f6a0  mov     [rsp+210h+var_1C0], rsi
0x18004f6a5  lea     r14, [rsi+18h]
0x18004f6a9  mov     rcx, r14; lpCriticalSection
0x18004f6ac  call    cs:__imp_EnterCriticalSection
0x18004f6b2  mov     eax, [rsi+0CCh]
0x18004f6b8  mov     ecx, [rsp+210h+SystemTimeAsFileTime.dwHighDateTime]
0x18004f6bc  sub     rcx, rax
0x18004f6bf  mov     eax, [rsi+0C8h]
0x18004f6c5  shl     rcx, 20h
0x18004f6c9  sub     rcx, rax
0x18004f6cc  mov     eax, [rsp+210h+SystemTimeAsFileTime.dwLowDateTime]
0x18004f6d0  add     rcx, rax
0x18004f6d3  mov     rax, 10C388D000h
0x18004f6dd  cmp     rcx, rax
0x18004f6e0  jb      loc_18004F7E1
0x18004f6e6  lea     rcx, [rsi+4Ch]
0x18004f6ea  lea     rdx, [rbp+110h+var_E0]
0x18004f6ee  call    IkeAddrGetAddrString
0x18004f6f3  lea     rcx, [rsi+88h]
0x18004f6fa  lea     rdx, [rbp+110h+var_180]
0x18004f6fe  call    IkeAddrGetAddrString
0x18004f703  mov     rdi, cs:WPP_GLOBAL_Control
0x18004f70a  cmp     rdi, rbx
0x18004f70d  jz      short loc_18004F761
0x18004f70f  cmp     byte ptr [rdi+19h], 4
0x18004f713  jb      short loc_18004F761
0x18004f715  test    byte ptr [rdi+1Ch], 10h
0x18004f719  jz      short loc_18004F761
0x18004f71b  mov     rdi, [rdi+10h]
0x18004f71f  call    IkeGetTlsPeerAddr
0x18004f724  mov     rbx, rax
0x18004f727  call    IkeGetTlsMmLuid
0x18004f72c  mov     r9, rax
0x18004f72f  lea     r8, WPP_0162bb2a8b4239af156c6f597e3eee45_Traceguids
0x18004f736  lea     rax, [rbp+110h+var_180]
0x18004f73a  mov     edx, 14h
0x18004f73f  mov     [rsp+210h+var_1E0], rax
0x18004f744  mov     rcx, rdi
0x18004f747  lea     rax, [rbp+110h+var_E0]
0x18004f74b  mov     [rsp+210h+var_1E8], rax
0x18004f750  mov     [rsp+210h+var_1F0], rbx
0x18004f755  call    WPP_SF_iSSS
0x18004f75a  lea     rbx, WPP_GLOBAL_Control
0x18004f761  lea     rax, [rsi+0D0h]
0x18004f768  mov     rcx, [rax]
0x18004f76b  cmp     rcx, rax
0x18004f76e  jz      short loc_18004F7A7
0x18004f770  cmp     [rcx+8], rax
0x18004f774  jnz     loc_18004F880
0x18004f77a  mov     rdx, [rcx]
0x18004f77d  cmp     [rdx+8], rcx
0x18004f781  jnz     loc_18004F880
0x18004f787  mov     [rax], rdx
0x18004f78a  mov     [rdx+8], rax
0x18004f78e  mov     rdx, rsi
0x18004f791  mov     [rsp+210h+var_1C8], rcx
0x18004f796  call    IkeIfrFireEvent
0x18004f79b  lea     rcx, [rsp+210h+var_1C8]
0x18004f7a0  call    WfpMemFree
0x18004f7a5  jmp     short loc_18004F761
0x18004f7a7  mov     rcx, r14; lpCriticalSection
0x18004f7aa  call    cs:__imp_LeaveCriticalSection
0x18004f7b0  xor     r8d, r8d
0x18004f7b3  mov     rdx, rsi
0x18004f7b6  mov     rcx, r15
0x18004f7b9  call    cs:__imp_RtlRemoveEntryHashTable
0x18004f7bf  mov     rcx, r15
0x18004f7c2  call    WfpRestructureHashtable
0x18004f7c7  cmp     dword ptr [rsi+48h], 0
0x18004f7cb  jz      short loc_18004F7D5
0x18004f7cd  mov     rcx, r14
0x18004f7d0  call    WfpCriticalSectionDestroy
0x18004f7d5  lea     rcx, [rsp+210h+var_1C0]
0x18004f7da  call    WfpMemFree
0x18004f7df  jmp     short loc_18004F7EA
0x18004f7e1  mov     rcx, r14; lpCriticalSection
0x18004f7e4  call    cs:__imp_LeaveCriticalSection
0x18004f7ea  lea     rdx, [rsp+210h+var_1D0]
0x18004f7ef  lea     rcx, [rsp+210h+var_1B0]
0x18004f7f4  call    WfpHashtableIteratorGetNext
0x18004f7f9  test    eax, eax
0x18004f7fb  jnz     loc_18004F69B
0x18004f801  mov     rcx, qword ptr [rsp+210h+var_1B0]
0x18004f806  lea     rdx, [rsp+210h+var_1B0+8]
0x18004f80b  call    cs:__imp_RtlEndEnumerationHashTable
0x18004f811  mov     rcx, r12; lpCriticalSection
0x18004f814  call    cs:__imp_LeaveCriticalSection
0x18004f81a  mov     rdi, cs:WPP_GLOBAL_Control
0x18004f821  cmp     rdi, rbx
0x18004f824  jz      short loc_18004F85F
0x18004f826  cmp     byte ptr [rdi+19h], 4
0x18004f82a  jb      short loc_18004F85F
0x18004f82c  test    byte ptr [rdi+1Ch], 10h
0x18004f830  jz      short loc_18004F85F
0x18004f832  mov     rdi, [rdi+10h]
0x18004f836  call    IkeGetTlsPeerAddr
0x18004f83b  mov     rbx, rax
0x18004f83e  call    IkeGetTlsMmLuid
0x18004f843  mov     r9, rax
0x18004f846  mov     [rsp+210h+var_1F0], rbx
0x18004f84b  mov     edx, 15h
0x18004f850  lea     r8, WPP_0162bb2a8b4239af156c6f597e3eee45_Traceguids
0x18004f857  mov     rcx, rdi
0x18004f85a  call    WPP_SF_iS
0x18004f85f  mov     rcx, [rbp+110h+var_40]
0x18004f866  xor     rcx, rsp; StackCookie
0x18004f869  call    __security_check_cookie
0x18004f86e  add     rsp, 1E0h
0x18004f875  pop     r15
0x18004f877  pop     r14
0x18004f879  pop     r12
0x18004f87b  pop     rdi
0x18004f87c  pop     rsi
0x18004f87d  pop     rbx
0x18004f87e  pop     rbp
0x18004f87f  retn
0x18004f880  mov     ecx, 3
0x18004f885  int     29h; Win8: RtlFailFast(ecx)
```
