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
  __int64 v4; // rcx
  int TlsMmLuid; // eax
  struct _RTL_CRITICAL_SECTION *v6; // r12
  LPCRITICAL_SECTION v7; // r15
  __int64 v8; // rsi
  struct _RTL_CRITICAL_SECTION *v9; // r14
  __int64 v10; // rcx
  __int64 v11; // rdi
  __int64 v12; // rbx
  __int64 v13; // rcx
  int v14; // eax
  _QWORD *v15; // rax
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rdi
  __int64 v20; // rbx
  __int64 v21; // rcx
  int v22; // eax
  __int64 v23; // [rsp+40h] [rbp-C0h] BYREF
  LPCVOID v24; // [rsp+48h] [rbp-B8h] BYREF
  LPCVOID v25; // [rsp+50h] [rbp-B0h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+58h] [rbp-A8h] BYREF
  _OWORD v27[3]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v28[160]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v29[160]; // [rsp+130h] [rbp+30h] BYREF

  v23 = 0;
  memset(v27, 0, sizeof(v27));
  memset_0(v29, 0, sizeof(v29));
  memset_0(v28, 0, sizeof(v28));
  v1 = gIkeExtGlobals;
  SystemTimeAsFileTime = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v2 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    TlsPeerAddr = IkeGetTlsPeerAddr(v0);
    TlsMmLuid = IkeGetTlsMmLuid(v4);
    WPP_SF_iS(v2, 19, (unsigned int)WPP_0162bb2a8b4239af156c6f597e3eee45_Traceguids, TlsMmLuid, TlsPeerAddr);
  }
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v6 = (LPCRITICAL_SECTION)((char *)v1 + 3848);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v1 + 3848));
  v7 = v1 + 95;
  RtlInitEnumerationHashTable(&v1[95], (char *)v27 + 8);
  *(_QWORD *)&v27[0] = v1 + 95;
  while ( (unsigned int)WfpHashtableIteratorGetNext(v27, &v23) )
  {
    v8 = v23;
    v25 = (LPCVOID)v23;
    v9 = (struct _RTL_CRITICAL_SECTION *)(v23 + 24);
    EnterCriticalSection((LPCRITICAL_SECTION)(v23 + 24));
    if ( SystemTimeAsFileTime.dwLowDateTime
       + ((SystemTimeAsFileTime.dwHighDateTime - (unsigned __int64)*(unsigned int *)(v8 + 204)) << 32)
       - *(unsigned int *)(v8 + 200) < 0x10C388D000LL )
    {
      LeaveCriticalSection(v9);
    }
    else
    {
      IkeAddrGetAddrString(v8 + 76, v29);
      IkeAddrGetAddrString(v8 + 136, v28);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v11 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v12 = IkeGetTlsPeerAddr(v10);
        v14 = IkeGetTlsMmLuid(v13);
        WPP_SF_iSSS(
          v11,
          20,
          (unsigned int)WPP_0162bb2a8b4239af156c6f597e3eee45_Traceguids,
          v14,
          v12,
          (__int64)v29,
          (__int64)v28);
      }
      while ( 1 )
      {
        v15 = (_QWORD *)(v8 + 208);
        v16 = *(_QWORD **)(v8 + 208);
        if ( v16 == (_QWORD *)(v8 + 208) )
          break;
        if ( (_QWORD *)v16[1] != v15 || (v17 = *v16, *(_QWORD **)(*v16 + 8LL) != v16) )
          __fastfail(3u);
        *v15 = v17;
        *(_QWORD *)(v17 + 8) = v15;
        v24 = v16;
        IkeIfrFireEvent(v16, v8);
        WfpMemFree(&v24);
      }
      LeaveCriticalSection(v9);
      RtlRemoveEntryHashTable(v7, v8, 0);
      WfpRestructureHashtable(v7);
      if ( *(_DWORD *)(v8 + 72) )
        WfpCriticalSectionDestroy(v9);
      WfpMemFree(&v25);
    }
  }
  RtlEndEnumerationHashTable(*(_QWORD *)&v27[0], (char *)v27 + 8);
  LeaveCriticalSection(v6);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v19 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v20 = IkeGetTlsPeerAddr(v18);
    v22 = IkeGetTlsMmLuid(v21);
    WPP_SF_iS(v19, 21, (unsigned int)WPP_0162bb2a8b4239af156c6f597e3eee45_Traceguids, v22, v20);
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
