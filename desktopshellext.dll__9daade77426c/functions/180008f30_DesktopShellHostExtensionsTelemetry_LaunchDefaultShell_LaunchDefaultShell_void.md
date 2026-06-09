# DesktopShellHostExtensionsTelemetry::LaunchDefaultShell::~LaunchDefaultShell(void)

- ea: `0x180008f30`
- end: `0x18000913f`
- name: `??1LaunchDefaultShell@DesktopShellHostExtensionsTelemetry@@QEAA@XZ`
- size: `527`
- prototype: `void __fastcall(DesktopShellHostExtensionsTelemetry::LaunchDefaultShell *__hidden this)`
- caller_count: `7`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18000851c`
- `0x180009150`
- `0x180023078`
- `0x18008330e`
- `0x180083370`
- `0x1800833f0`
- `0x180083450`

## callees

- `0x180008f30`
- `0x180009c60`
- `0x18000a1c4`
- `0x18000cad8`
- `0x18000f2a0`
- `0x180013064`
- `0x180035118`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008ff8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008ff8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000903f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000903f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800090e8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009113`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800090e8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009113`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800090da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009105`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800090da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009105`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008fc7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008fc7`

## string_xrefs

- `0x18000909c`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall DesktopShellHostExtensionsTelemetry::LaunchDefaultShell::~LaunchDefaultShell(
        DesktopShellHostExtensionsTelemetry::LaunchDefaultShell *this)
{
  RTL_SRWLOCK *v2; // rax
  _DWORD *v3; // rcx
  __int64 **v4; // rdi
  volatile signed __int32 *v5; // rax
  __int64 v6; // rax
  RTL_SRWLOCK *v7; // r14
  volatile signed __int32 *v8; // rcx
  char v9; // di
  void *v10; // rcx
  int v11; // eax
  __int64 v12; // rdx
  void *v13; // rdi
  HANDLE ProcessHeap; // rax
  void *v15; // rdi
  HANDLE v16; // rax
  const struct _tlgProvider_t *v17; // rax
  void *retaddr; // [rsp+58h] [rbp+0h]
  int v19; // [rsp+60h] [rbp+8h] BYREF

  *(_QWORD *)this = &DesktopShellHostExtensionsTelemetry::LaunchDefaultShell::`vftable';
  v2 = (RTL_SRWLOCK *)*((_QWORD *)this + 35);
  if ( !v2 )
    goto LABEL_2;
  v7 = v2 + 33;
  AcquireSRWLockExclusive(v2 + 33);
  v8 = (volatile signed __int32 *)*((_QWORD *)this + 35);
  if ( v8 && *v8 == 1 )
  {
    v9 = 1;
  }
  else
  {
    v9 = 0;
    if ( v8 )
    {
      if ( _InterlockedExchangeAdd(v8, 0xFFFFFFFF) == 1 )
      {
        v10 = (void *)*((_QWORD *)this + 35);
        if ( v10 )
          wil::details::shared_object<wil::ActivityBase<DesktopShellHostExtensionsLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DesktopShellHostExtensionsLogging,_TlgReflectorTag_Param0IsProviderType>>::RefAndObject::`scalar deleting destructor'(v10);
      }
      *((_QWORD *)this + 35) = 0;
    }
  }
  if ( v7 )
    ReleaseSRWLockExclusive(v7);
  if ( v9 )
  {
LABEL_2:
    v3 = (_DWORD *)*((_QWORD *)this + 34);
    if ( *v3 == 1 )
    {
      v11 = v3[22];
      v19 = v11;
      v12 = 2147942974LL;
      if ( v11 < 0 )
        v12 = (unsigned int)v11;
      wil::ActivityBase<DesktopShellHostExtensionsLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DesktopShellHostExtensionsLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
        v3,
        v12,
        &v19);
      wil::ActivityBase<DesktopShellHostExtensionsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(this);
    }
  }
  v4 = (__int64 **)((char *)this + 288);
  if ( *((_DWORD *)this + 78) )
  {
    if ( *((_DWORD *)this + 78) != GetCurrentThreadId() && wil::details::g_pfnReportFatalUsageError )
      wil::details::g_pfnReportFatalUsageError(
        "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
        retaddr);
    *((_DWORD *)this + 78) = 0;
    while ( 1 )
    {
      v6 = **v4;
      if ( !v6 )
        break;
      if ( (__int64 **)v6 == v4 )
      {
        **v4 = *((_QWORD *)this + 38);
        break;
      }
      *v4 = (__int64 *)(v6 + 16);
    }
    *v4 = 0;
  }
  wil::details::shared_object<wil::ActivityBase<DesktopShellHostExtensionsLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DesktopShellHostExtensionsLogging,_TlgReflectorTag_Param0IsProviderType>>::reset((char *)this + 280);
  v5 = (volatile signed __int32 *)*((_QWORD *)this + 30);
  if ( v5 )
  {
    if ( _InterlockedExchangeAdd(v5, 0xFFFFFFFF) == 1 )
    {
      v13 = (void *)*((_QWORD *)this + 30);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v13);
    }
    *((_QWORD *)this + 30) = 0;
    *((_QWORD *)this + 31) = 0;
  }
  if ( *((_BYTE *)this + 72) )
  {
    v15 = (void *)*((_QWORD *)this + 8);
    v16 = GetProcessHeap();
    HeapFree(v16, 0, v15);
    *((_BYTE *)this + 72) = 0;
  }
  *((_QWORD *)this + 8) = 0;
  if ( *((_DWORD *)this + 2) == 1 )
  {
    *((_DWORD *)this + 2) = 2;
    v17 = DesktopShellHostExtensionsLogging::Provider();
    _tlgWriteActivityAutoStop<70368744177664,5>(v17, (char *)this + 16);
  }
  *((_DWORD *)this + 2) = 3;
}

```

## disassembly

```asm
0x180008f30  push    rbx
0x180008f32  push    rbp
0x180008f33  push    rsi
0x180008f34  push    rdi
0x180008f35  push    r14
0x180008f37  push    r15
0x180008f39  sub     rsp, 28h
0x180008f3d  mov     rbx, rcx
0x180008f40  xor     r15d, r15d
0x180008f43  lea     rax, ??_7LaunchDefaultShell@DesktopShellHostExtensionsTelemetry@@6B@; const DesktopShellHostExtensionsTelemetry::LaunchDefaultShell::`vftable'
0x180008f4a  mov     [rcx], rax
0x180008f4d  mov     rax, [rcx+118h]
0x180008f54  mov     ebp, 0FFFFFFFFh
0x180008f59  test    rax, rax
0x180008f5c  jnz     loc_180008FEE
0x180008f62  mov     rcx, [rbx+110h]
0x180008f69  cmp     dword ptr [rcx], 1
0x180008f6c  jz      loc_18000905F
0x180008f72  lea     rdi, [rbx+120h]
0x180008f79  cmp     dword ptr [rdi+18h], 0
0x180008f7d  jnz     short loc_180008FC7
0x180008f7f  lea     rcx, [rbx+118h]
0x180008f86  call    ?reset@?$shared_object@V?$ActivityData@VDesktopShellHostExtensionsLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VDesktopShellHostExtensionsLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<DesktopShellHostExtensionsLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DesktopShellHostExtensionsLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x180008f8b  mov     rax, [rbx+0F0h]
0x180008f92  test    rax, rax
0x180008f95  jnz     loc_1800090CA
0x180008f9b  cmp     byte ptr [rbx+48h], 0
0x180008f9f  jnz     loc_180009101
0x180008fa5  mov     [rbx+40h], r15
0x180008fa9  cmp     dword ptr [rbx+8], 1
0x180008fad  jz      loc_180009122
0x180008fb3  mov     dword ptr [rbx+8], 3
0x180008fba  add     rsp, 28h
0x180008fbe  pop     r15
0x180008fc0  pop     r14
0x180008fc2  pop     rdi
0x180008fc3  pop     rsi
0x180008fc4  pop     rbp
0x180008fc5  pop     rbx
0x180008fc6  retn
0x180008fc7  call    cs:__imp_GetCurrentThreadId
0x180008fcd  cmp     [rdi+18h], eax
0x180008fd0  jnz     loc_180009087
0x180008fd6  mov     [rdi+18h], r15d
0x180008fda  mov     rcx, [rdi]
0x180008fdd  mov     rax, [rcx]
0x180008fe0  test    rax, rax
0x180008fe3  jnz     loc_1800090AD
0x180008fe9  mov     [rdi], r15
0x180008fec  jmp     short loc_180008F7F
0x180008fee  lea     r14, [rax+108h]
0x180008ff5  mov     rcx, r14; SRWLock
0x180008ff8  call    cs:__imp_AcquireSRWLockExclusive
0x180008ffe  mov     rcx, [rbx+118h]
0x180009005  test    rcx, rcx
0x180009008  jz      short loc_18000900F
0x18000900a  cmp     dword ptr [rcx], 1
0x18000900d  jz      short loc_18000905A
0x18000900f  xor     dil, dil
0x180009012  test    rcx, rcx
0x180009015  jz      short loc_180009029
0x180009017  mov     eax, ebp
0x180009019  lock xadd [rcx], eax
0x18000901d  cmp     eax, 1
0x180009020  jz      short loc_180009047
0x180009022  mov     [rbx+118h], r15
0x180009029  test    r14, r14
0x18000902c  jnz     short loc_18000903C
0x18000902e  test    dil, dil
0x180009031  jnz     loc_180008F62
0x180009037  jmp     loc_180008F72
0x18000903c  mov     rcx, r14; SRWLock
0x18000903f  call    cs:__imp_ReleaseSRWLockExclusive
0x180009045  jmp     short loc_18000902E
0x180009047  mov     rcx, [rbx+118h]; void *
0x18000904e  test    rcx, rcx
0x180009051  jz      short loc_180009022
0x180009053  call    ??_GRefAndObject@?$shared_object@V?$ActivityData@VDesktopShellHostExtensionsLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VDesktopShellHostExtensionsLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAPEAXI@Z; wil::details::shared_object<wil::ActivityBase<DesktopShellHostExtensionsLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DesktopShellHostExtensionsLogging,_TlgReflectorTag_Param0IsProviderType>>::RefAndObject::`scalar deleting destructor'(uint)
0x180009058  jmp     short loc_180009022
0x18000905a  mov     dil, 1
0x18000905d  jmp     short loc_180009029
0x18000905f  mov     eax, [rcx+58h]
0x180009062  mov     [rsp+58h+arg_0], eax
0x180009066  mov     edx, 8007023Eh
0x18000906b  test    eax, eax
0x18000906d  cmovs   edx, eax
0x180009070  lea     r8, [rsp+58h+arg_0]
0x180009075  call    ?SetStopResult@?$ActivityData@VDesktopShellHostExtensionsLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VDesktopShellHostExtensionsLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<DesktopShellHostExtensionsLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DesktopShellHostExtensionsLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x18000907a  mov     rcx, rbx
0x18000907d  call    ?ReportStopActivity@?$ActivityBase@VDesktopShellHostExtensionsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z; wil::ActivityBase<DesktopShellHostExtensionsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)
0x180009082  jmp     loc_180008F72
0x180009087  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18000908e  test    rax, rax
0x180009091  jz      loc_180008FD6
0x180009097  mov     rdx, [rsp+58h]
0x18000909c  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x1800090a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090a8  jmp     loc_180008FD6
0x1800090ad  cmp     rax, rdi
0x1800090b0  jz      short loc_1800090BE
0x1800090b2  add     rax, 10h
0x1800090b6  mov     [rdi], rax
0x1800090b9  jmp     loc_180008FDA
0x1800090be  mov     rax, [rdi+10h]
0x1800090c2  mov     [rcx], rax
0x1800090c5  jmp     loc_180008FE9
0x1800090ca  lock xadd [rax], ebp
0x1800090ce  cmp     ebp, 1
0x1800090d1  jnz     short loc_1800090EE
0x1800090d3  mov     rdi, [rbx+0F0h]
0x1800090da  call    cs:__imp_GetProcessHeap
0x1800090e0  mov     r8, rdi; lpMem
0x1800090e3  xor     edx, edx; dwFlags
0x1800090e5  mov     rcx, rax; hHeap
0x1800090e8  call    cs:__imp_HeapFree
0x1800090ee  mov     [rbx+0F0h], r15
0x1800090f5  mov     [rbx+0F8h], r15
0x1800090fc  jmp     loc_180008F9B
0x180009101  mov     rdi, [rbx+40h]
0x180009105  call    cs:__imp_GetProcessHeap
0x18000910b  mov     r8, rdi; lpMem
0x18000910e  xor     edx, edx; dwFlags
0x180009110  mov     rcx, rax; hHeap
0x180009113  call    cs:__imp_HeapFree
0x180009119  mov     byte ptr [rbx+48h], 0
0x18000911d  jmp     loc_180008FA5
0x180009122  mov     dword ptr [rbx+8], 2
0x180009129  call    ?Provider@DesktopShellHostExtensionsLogging@@SAPEBU_tlgProvider_t@@XZ; DesktopShellHostExtensionsLogging::Provider(void)
0x18000912e  lea     rdx, [rbx+10h]
0x180009132  mov     rcx, rax
0x180009135  call    ??$_tlgWriteActivityAutoStop@$0EAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z; _tlgWriteActivityAutoStop<70368744177664,5>(_tlgProvider_t const *,_GUID const *)
0x18000913a  jmp     loc_180008FB3
```
