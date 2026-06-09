# GetSYSTHREAD(void)

- ea: `0x1800831b8`
- end: `0x18008338b`
- name: `?GetSYSTHREAD@@YAPEAUtagSYSTHREAD@@XZ`
- size: `467`
- prototype: `struct tagSYSTHREAD *(void)`
- caller_count: `45`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800082d4`
- `0x180008c0c`
- `0x180009044`
- `0x1800098e0`
- `0x180009b30`
- `0x18000a368`
- `0x18000a3c0`
- `0x18000e8c4`
- `0x18000e960`
- `0x18000fcf0`
- `0x180016ac0`
- `0x18001a4a8`
- `0x18001d630`
- `0x18001e9f0`
- `0x18001ea24`
- `0x18001ea90`
- `0x18001f208`
- `0x18001f290`
- `0x180020940`
- `0x180021d40`
- `0x180021e88`
- `0x180024ad0`
- `0x180029174`
- `0x18002c25c`
- `0x18002c7f4`
- `0x18002cb7c`
- `0x18002da10`
- `0x180044e20`
- `0x180046e00`
- `0x18004eed0`
- `0x18004eff0`
- `0x180053ba0`
- `0x180055800`
- `0x180058b70`
- `0x18005bffc`
- `0x18005d9d0`
- `0x1800606e0`
- `0x180063310`
- `0x18006e7e0`
- `0x18006fc8c`
- `0x1800830d0`
- `0x1800830f4`
- `0x1800a60a4`
- `0x1800a6a60`
- `0x1800c7930`

## callees

- `0x180024d70`
- `0x18003a46c`
- `0x180044050`
- `0x180044090`
- `0x18004e310`
- `0x180053660`
- `0x1800831b8`
- `0x180083394`
- `0x18008c564`
- `0x1800903fc`
- `0x1800a18d4`
- `0x1800a597c`
- `0x1800a5de4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18008326a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18008326a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008325c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008325c`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18008322e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180083372`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18008322e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180083372`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800831cb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800831cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180083278`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180083278`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008320d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800832d1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008320d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800832d1`
- `api-ms-win-core-fibers-l1-1-0!FlsSetValue` at `0x180083291`
- `api-ms-win-core-fibers-l1-1-0!FlsSetValue` at `0x180083291`

## pseudocode

```c
struct tagSYSTHREAD *GetSYSTHREAD(void)
{
  tagSYSTHREAD *Value; // rax
  tagSYSTHREAD *v1; // rax
  unsigned int v2; // edx
  __int64 v3; // rdx
  __int64 v4; // r9
  int v5; // r8d
  CVoidPtrArray *v6; // rax
  _QWORD *v7; // rcx
  unsigned int v9; // edx
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  tagSYSTHREAD *FlsData; // [rsp+30h] [rbp+8h] BYREF

  if ( g_dwTLSIndex == -1 )
    Value = 0;
  else
    Value = (tagSYSTHREAD *)TlsGetValue(g_dwTLSIndex);
  FlsData = Value;
  if ( Value )
    return FlsData;
  if ( g_fDllProcessDetached || (unsigned int)_IsFlsCallbackCalled() || (unsigned int)DllShutdownInProgress() )
    return 0;
  v1 = (tagSYSTHREAD *)LocalAlloc(0x40u, 0x178u);
  if ( v1 )
    v1 = tagSYSTHREAD::tagSYSTHREAD(v1);
  FlsData = v1;
  if ( !TlsSetValue(g_dwTLSIndex, v1) )
  {
    if ( FlsData )
      tagSYSTHREAD::`scalar deleting destructor'(FlsData, v2);
    FlsData = 0;
  }
  if ( !FlsData )
    return FlsData;
  *((_DWORD *)FlsData + 26) = GetCurrentThreadId();
  *((_DWORD *)FlsData + 27) = GetCurrentProcessId();
  *((_DWORD *)FlsData + 28) = GetTickCount();
  if ( !FlsSetValue(g_dwFLSIndex, &FlsData) )
  {
    v3 = 202;
    v4 = 2147500037LL;
    goto LABEL_29;
  }
  if ( (unsigned int)CicEnterCriticalSection((struct CCicCriticalSectionStatic *)&g_csInDllMain) )
  {
    v6 = g_rgSysThread;
    if ( g_rgSysThread )
      goto LABEL_34;
    v6 = (CVoidPtrArray *)LocalAlloc(0x40u, 0x18u);
    if ( v6 )
      v6 = (CVoidPtrArray *)CPtrArray<tagSYSTHREAD>::CPtrArray<tagSYSTHREAD>(v6);
    g_rgSysThread = v6;
    if ( v6 )
    {
LABEL_34:
      if ( (unsigned int)CVoidPtrArray::Insert(v6, 0, v5) )
      {
        if ( *((int *)g_rgSysThread + 4) > 0 )
        {
          v7 = (_QWORD *)*((_QWORD *)g_rgSysThread + 1);
          if ( v7 )
            *v7 = FlsData;
        }
      }
    }
    CicLeaveCriticalSection((struct CCicCriticalSectionStatic *)&g_csInDllMain);
    EnsurePrivateMessages();
    tagSYSTHREAD::CheckForSyscallFiltering(FlsData);
    ++*((_DWORD *)FlsData + 87);
    return FlsData;
  }
  v3 = 227;
  v4 = 2147549183LL;
LABEL_29:
  wil::details::in1diag3::Log_Hr(
    retaddr,
    (void *)v3,
    (unsigned int)"clientcore\\windows\\advcore\\ctf\\uim\\default.cpp",
    (const char *)v4,
    v10);
  TlsSetValue(g_dwTLSIndex, 0);
  if ( FlsData )
    tagSYSTHREAD::`scalar deleting destructor'(FlsData, v9);
  return 0;
}

```

## disassembly

```asm
0x1800831b8  sub     rsp, 28h
0x1800831bc  mov     ecx, cs:?g_dwTLSIndex@@3KA; dwTlsIndex
0x1800831c2  cmp     ecx, 0FFFFFFFFh
0x1800831c5  jnz     short loc_1800831CB
0x1800831c7  xor     eax, eax
0x1800831c9  jmp     short loc_1800831D1
0x1800831cb  call    cs:__imp_TlsGetValue
0x1800831d1  mov     [rsp+28h+FlsData], rax
0x1800831d6  test    rax, rax
0x1800831d9  jnz     loc_180083344
0x1800831df  cmp     cs:?g_fDllProcessDetached@@3HA, eax; int g_fDllProcessDetached
0x1800831e5  jnz     loc_180083387
0x1800831eb  call    ?_IsFlsCallbackCalled@@YAHXZ; _IsFlsCallbackCalled(void)
0x1800831f0  test    eax, eax
0x1800831f2  jnz     loc_180083387
0x1800831f8  call    ?DllShutdownInProgress@@YAHXZ; DllShutdownInProgress(void)
0x1800831fd  test    eax, eax
0x1800831ff  jnz     loc_180083387
0x180083205  mov     edx, 178h; uBytes
0x18008320a  lea     ecx, [rax+40h]; uFlags
0x18008320d  call    cs:__imp_LocalAlloc
0x180083213  test    rax, rax
0x180083216  jz      short loc_180083220
0x180083218  mov     rcx, rax; this
0x18008321b  call    ??0tagSYSTHREAD@@QEAA@XZ; tagSYSTHREAD::tagSYSTHREAD(void)
0x180083220  mov     [rsp+28h+FlsData], rax
0x180083225  mov     rdx, rax; lpTlsValue
0x180083228  mov     ecx, cs:?g_dwTLSIndex@@3KA; dwTlsIndex
0x18008322e  call    cs:__imp_TlsSetValue
0x180083234  test    eax, eax
0x180083236  jnz     short loc_180083250
0x180083238  mov     rcx, [rsp+28h+FlsData]; this
0x18008323d  test    rcx, rcx
0x180083240  jz      short loc_180083247
0x180083242  call    ??_GtagSYSTHREAD@@QEAAPEAXI@Z; tagSYSTHREAD::`scalar deleting destructor'(uint)
0x180083247  mov     [rsp+28h+FlsData], 0
0x180083250  cmp     [rsp+28h+FlsData], 0
0x180083256  jz      loc_180083344
0x18008325c  call    cs:__imp_GetCurrentThreadId
0x180083262  mov     rcx, [rsp+28h+FlsData]
0x180083267  mov     [rcx+68h], eax
0x18008326a  call    cs:__imp_GetCurrentProcessId
0x180083270  mov     rcx, [rsp+28h+FlsData]
0x180083275  mov     [rcx+6Ch], eax
0x180083278  call    cs:__imp_GetTickCount
0x18008327e  mov     rcx, [rsp+28h+FlsData]
0x180083283  mov     [rcx+70h], eax
0x180083286  lea     rdx, [rsp+28h+FlsData]; lpFlsData
0x18008328b  mov     ecx, cs:?g_dwFLSIndex@@3KA; dwFlsIndex
0x180083291  call    cs:__imp_FlsSetValue
0x180083297  test    eax, eax
0x180083299  jnz     short loc_1800832AB
0x18008329b  mov     edx, 0CAh
0x1800832a0  mov     r9d, 80004005h
0x1800832a6  jmp     loc_180083359
0x1800832ab  lea     rcx, ?g_csInDllMain@@3VCCicCriticalSectionStatic@@A; struct CCicCriticalSectionStatic *
0x1800832b2  call    ?CicEnterCriticalSection@@YAHAEAVCCicCriticalSectionStatic@@@Z; CicEnterCriticalSection(CCicCriticalSectionStatic &)
0x1800832b7  test    eax, eax
0x1800832b9  jz      loc_18008334E
0x1800832bf  mov     rax, cs:?g_rgSysThread@@3PEAV?$CPtrArray@UtagSYSTHREAD@@@@EA; CPtrArray<tagSYSTHREAD> * g_rgSysThread
0x1800832c6  test    rax, rax
0x1800832c9  jnz     short loc_1800832F0
0x1800832cb  lea     edx, [rax+18h]; uBytes
0x1800832ce  lea     ecx, [rax+40h]; uFlags
0x1800832d1  call    cs:__imp_LocalAlloc
0x1800832d7  test    rax, rax
0x1800832da  jz      short loc_1800832E4
0x1800832dc  mov     rcx, rax
0x1800832df  call    ??0?$CPtrArray@UtagSYSTHREAD@@@@QEAA@XZ; CPtrArray<tagSYSTHREAD>::CPtrArray<tagSYSTHREAD>(void)
0x1800832e4  mov     cs:?g_rgSysThread@@3PEAV?$CPtrArray@UtagSYSTHREAD@@@@EA, rax; CPtrArray<tagSYSTHREAD> * g_rgSysThread
0x1800832eb  test    rax, rax
0x1800832ee  jz      short loc_18008331C
0x1800832f0  xor     edx, edx; int
0x1800832f2  mov     rcx, rax; this
0x1800832f5  call    ?Insert@CVoidPtrArray@@QEAAHHH@Z; CVoidPtrArray::Insert(int,int)
0x1800832fa  test    eax, eax
0x1800832fc  jz      short loc_18008331C
0x1800832fe  mov     rcx, cs:?g_rgSysThread@@3PEAV?$CPtrArray@UtagSYSTHREAD@@@@EA; CPtrArray<tagSYSTHREAD> * g_rgSysThread
0x180083305  cmp     dword ptr [rcx+10h], 0
0x180083309  jle     short loc_18008331C
0x18008330b  mov     rcx, [rcx+8]
0x18008330f  test    rcx, rcx
0x180083312  jz      short loc_18008331C
0x180083314  mov     rax, [rsp+28h+FlsData]
0x180083319  mov     [rcx], rax
0x18008331c  jmp     short $+2
0x18008331e  lea     rcx, ?g_csInDllMain@@3VCCicCriticalSectionStatic@@A; struct CCicCriticalSectionStatic *
0x180083325  call    ?CicLeaveCriticalSection@@YAXAEAVCCicCriticalSectionStatic@@@Z; CicLeaveCriticalSection(CCicCriticalSectionStatic &)
0x18008332a  call    ?EnsurePrivateMessages@@YAHXZ; EnsurePrivateMessages(void)
0x18008332f  mov     rcx, [rsp+28h+FlsData]; this
0x180083334  call    ?CheckForSyscallFiltering@tagSYSTHREAD@@QEAAXXZ; tagSYSTHREAD::CheckForSyscallFiltering(void)
0x180083339  mov     rax, [rsp+28h+FlsData]
0x18008333e  inc     dword ptr [rax+15Ch]
0x180083344  mov     rax, [rsp+28h+FlsData]
0x180083349  add     rsp, 28h
0x18008334d  retn
0x18008334e  mov     edx, 0E3h; void *
0x180083353  mov     r9d, 8000FFFFh; char *
0x180083359  mov     rcx, [rsp+28h]; this
0x18008335e  lea     r8, aClientcoreWind_0; "clientcore\\windows\\advcore\\ctf\\uim"...
0x180083365  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18008336a  xor     edx, edx; lpTlsValue
0x18008336c  mov     ecx, cs:?g_dwTLSIndex@@3KA; dwTlsIndex
0x180083372  call    cs:__imp_TlsSetValue
0x180083378  mov     rcx, [rsp+28h+FlsData]; this
0x18008337d  test    rcx, rcx
0x180083380  jz      short loc_180083387
0x180083382  call    ??_GtagSYSTHREAD@@QEAAPEAXI@Z; tagSYSTHREAD::`scalar deleting destructor'(uint)
0x180083387  xor     eax, eax
0x180083389  jmp     short loc_180083349
0x180107b4d  push    rbp
0x180107b4f  sub     rsp, 20h
0x180107b53  mov     rbp, rdx
0x180107b56  mov     dl, cs:?g_fEnableFailFast@@3_NA; bool
0x180107b5c  call    ?CicExceptionFilter@@YAJPEAU_EXCEPTION_POINTERS@@_N@Z; CicExceptionFilter(_EXCEPTION_POINTERS *,bool)
0x180107b61  nop
0x180107b62  add     rsp, 20h
0x180107b66  pop     rbp
0x180107b67  retn
```
