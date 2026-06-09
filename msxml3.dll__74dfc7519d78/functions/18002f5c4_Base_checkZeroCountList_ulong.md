# Base::checkZeroCountList(ulong)

- ea: `0x18002f5c4`
- end: `0x18002fc8b`
- name: `?checkZeroCountList@Base@@CAXK@Z`
- size: `1735`
- prototype: `void __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `17`
- tags: ``

## callers

- `0x18002c740`

## callees

- `0x18000d5c0`
- `0x180020910`
- `0x18002f5c4`
- `0x18002fca0`
- `0x18002fd78`
- `0x18003d8dc`
- `0x18003d92c`
- `0x18004219c`
- `0x180043540`
- `0x18004b488`
- `0x180050f44`
- `0x18006059c`
- `0x180064034`
- `0x1800e86e8`
- `0x180102cde`
- `0x180102d20`
- `0x180107010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x18002fa53`
- `msvcrt!_resetstkoflw` at `0x18002fa53`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002faa6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002faa6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002f6ac`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002fa41`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002f6ac`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002fa41`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18002f7c3`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18002f94b`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18002fb49`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18002f7c3`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18002f94b`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18002fb49`
- `api-ms-win-core-processthreads-l1-1-0!SuspendThread` at `0x18002f7a6`
- `api-ms-win-core-processthreads-l1-1-0!SuspendThread` at `0x18002f7a6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18002faf7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18002faf7`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x18002f802`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x18002f802`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18002f8d0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18002f8d0`
- `api-ms-win-core-processthreads-l1-1-1!GetThreadContext` at `0x18002f815`
- `api-ms-win-core-processthreads-l1-1-1!GetThreadContext` at `0x18002f815`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x18002f877`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x18002f8ed`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x18002f877`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x18002f8ed`

## pseudocode

```c
void __fastcall Base::checkZeroCountList(int a1)
{
  CSMutex *v1; // rbx
  char v2; // r15
  struct TLSDATA *Value; // r13
  struct TLSDATA *v4; // r14
  TLSDATA *v5; // rdi
  bool v6; // di
  HANDLE v7; // rax
  __int64 *BaseAddress; // r10
  struct TLSDATA *i; // rdi
  struct TLSDATA *j; // rdi
  void *v11; // rcx
  __int64 v12; // rdi
  struct TLSDATA *v13; // rdi
  struct TLSDATA **v14; // r15
  unsigned __int64 v15; // r13
  unsigned __int64 v16; // rax
  unsigned __int64 k; // rbx
  unsigned __int64 v18; // r14
  _BYTE v19[8]; // [rsp+28h] [rbp-7C0h] BYREF
  HANDLE hThread; // [rsp+30h] [rbp-7B8h] BYREF
  CSMutex *v21; // [rsp+38h] [rbp-7B0h] BYREF
  int v22; // [rsp+40h] [rbp-7A8h]
  DWORD64 Rsp; // [rsp+48h] [rbp-7A0h]
  struct TLSDATA *v24; // [rsp+50h] [rbp-798h]
  CSMutex *v25; // [rsp+58h] [rbp-790h]
  DWORD64 v26; // [rsp+60h] [rbp-788h]
  _MEMORY_BASIC_INFORMATION Buffer; // [rsp+68h] [rbp-780h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+98h] [rbp-750h] BYREF
  CONTEXT ContextRecord; // [rsp+D0h] [rbp-718h] BYREF
  __int64 v30[9]; // [rsp+7A0h] [rbp-48h] BYREF

  v22 = a1;
  memset_0(&ContextRecord, 0, 0x6D0u);
  memset(&Buffer, 0, sizeof(Buffer));
  if ( Base::s_fNoFullGC )
    return;
  v1 = g_pMutexFullGC;
  v25 = g_pMutexFullGC;
  v21 = g_pMutexFullGC;
  if ( g_pMutexFullGC )
  {
    (*(void (__fastcall **)(CSMutex *))(*(_QWORD *)g_pMutexFullGC + 8LL))(g_pMutexFullGC);
    (*(void (__fastcall **)(CSMutex *))(*(_QWORD *)v1 + 24LL))(v1);
  }
  if ( *((int *)g_pMutexName + 16) > 0 || *((int *)g_pMutexAtom + 16) > 0 )
  {
    if ( !Base::s_fStartedPartialGC )
      --Base::s_lInGC;
    MutexLock::Release((MutexLock *)&v21);
    return;
  }
  v2 = 0;
  ++Base::s_ulGCCycle;
  Base::FreeDeadList();
  byte_180170118 = 0;
  qword_180170110 = (__int64)lpMem;
  Value = (struct TLSDATA *)TlsGetValue(g_dwTlsIndex);
  v24 = Value;
  Base::flushToZeroList(Value);
  v4 = g_ptlsdata;
  s_ptlsdataGC = g_ptlsdata;
  v5 = g_ptlsdata;
  while ( v5 )
  {
    if ( *((_BYTE *)v5 + 128) )
      Base::flushToZeroList(v5);
    if ( *((_BYTE *)v5 + 48) )
    {
      *((_BYTE *)v5 + 49) = 0;
    }
    else
    {
      SpinLock((volatile unsigned __int64 *)v5 + 3);
      *((_QWORD *)v5 + 3) = SpinLock((volatile unsigned __int64 *)v5 + 1) & 0xFFFFFFFFFFFFFFF9uLL;
      *((_QWORD *)v5 + 1) = v5;
      *((_BYTE *)v5 + 48) = 1;
    }
    v5 = (TLSDATA *)*((_QWORD *)v5 + 5);
    v4 = s_ptlsdataGC;
  }
  if ( Base::s_fStartedPartialGC )
  {
    g_pfnExit = (void (*)(struct TLSDATA *))Base::StackExitNormal;
    Base::s_fStartedPartialGC = 0;
  }
  qword_180170128 = (__int64)qword_180170120;
  while ( v4 )
  {
    MutexLock::MutexLock((MutexLock *)v19, g_pMutexPointer);
    if ( !*((_DWORD *)v4 + 20) )
      goto LABEL_46;
    v6 = v4 == Value;
    v7 = (HANDLE)*((_QWORD *)v4 + 4);
    hThread = v7;
    if ( !v7 )
      goto LABEL_46;
    if ( v4 == Value )
      goto LABEL_28;
    if ( SuspendThread(v7) == -1 )
      goto LABEL_23;
    if ( *((_DWORD *)v4 + 20) )
    {
      v7 = hThread;
LABEL_28:
      *((_BYTE *)v4 + 50) = 1;
      if ( (v22 & 4) == 0 || v4 != Value )
      {
        ContextRecord.ContextFlags = 1048587;
        if ( v4 == Value )
        {
          RtlCaptureContext(&ContextRecord);
        }
        else if ( !GetThreadContext(v7, &ContextRecord) )
        {
          goto LABEL_38;
        }
        Base::markStackObjects((__int64 *)&ContextRecord, v30, v6, v4);
        Rsp = ContextRecord.Rsp;
        v26 = ContextRecord.Rsp;
        if ( !VirtualQuery((LPCVOID)ContextRecord.Rsp, &Buffer, 0x30u) )
        {
LABEL_38:
          failure_tracing::record();
          v2 = 1;
          MutexLock::Release((MutexLock *)v19);
          goto LABEL_54;
        }
        if ( v4 == Value || (Buffer.AllocationProtect & 0x100) == 0 )
        {
          BaseAddress = (__int64 *)Rsp;
        }
        else
        {
          memset(&SystemInfo, 0, sizeof(SystemInfo));
          GetSystemInfo(&SystemInfo);
          if ( !VirtualQuery((LPCVOID)(Rsp + SystemInfo.dwPageSize), &Buffer, 0x30u) )
            goto LABEL_38;
          BaseAddress = (__int64 *)Buffer.BaseAddress;
          v26 = (DWORD64)Buffer.BaseAddress;
        }
        Base::markStackObjects(BaseAddress, (__int64 *)((char *)Buffer.BaseAddress + Buffer.RegionSize), v6, v4);
        if ( v4 != Value && ResumeThread(hThread) == -1 )
          failure_tracing::record();
      }
      *((_BYTE *)v4 + 50) = 0;
      if ( byte_180170118 )
      {
        MutexLock::Release((MutexLock *)v19);
        goto LABEL_54;
      }
      goto LABEL_46;
    }
    if ( ResumeThread(hThread) == -1 )
LABEL_23:
      failure_tracing::record();
LABEL_46:
    MutexLock::Release((MutexLock *)v19);
    v4 = (struct TLSDATA *)*((_QWORD *)v4 + 5);
  }
  Base::s_ptlsCheckZeroList = Value;
  Base::s_ptlsGC = Value;
  Base::freeRentalObjects(Value, 1, 0);
  for ( i = s_ptlsdataGC; i; i = (struct TLSDATA *)*((_QWORD *)i + 5) )
    Base::FreeObjects(i);
  if ( g_fClassInitCalled && (Base::s_ulGCCycle & 3) == 0 )
  {
    MutexLock::MutexLock((MutexLock *)&hThread, g_pMutexName);
    Base::FreeObjects(Name::s_pNames);
    MutexLock::Release((MutexLock *)&hThread);
    MutexLock::MutexLock((MutexLock *)&hThread, g_pMutexAtom);
    Base::FreeObjects(Atom::atoms);
    MutexLock::Release((MutexLock *)&hThread);
  }
  Base::s_ptlsCheckZeroList = 0;
  Base::s_ptlsGC = 0;
  qword_180170128 = (__int64)qword_180170120;
LABEL_54:
  if ( v2 )
  {
    for ( j = s_ptlsdataGC; j; j = (struct TLSDATA *)*((_QWORD *)j + 5) )
    {
      if ( *((_BYTE *)j + 50) )
      {
        if ( j != Value )
        {
          MutexLock::MutexLock((MutexLock *)&v21, g_pMutexPointer);
          v11 = (void *)*((_QWORD *)j + 4);
          if ( v11 && ResumeThread(v11) == -1 )
            failure_tracing::record();
          MutexLock::Release((MutexLock *)&v21);
        }
        *((_BYTE *)j + 50) = 0;
      }
    }
  }
  while ( qword_180170110 > (unsigned __int64)lpMem )
  {
    qword_180170110 -= 8;
    v12 = *(_QWORD *)qword_180170110;
    *(_QWORD *)(v12 + 8) = SpinLock((volatile unsigned __int64 *)(*(_QWORD *)qword_180170110 + 8LL))
                         & 0xFFFFFFFFFFFFFFFDuLL;
  }
  Base::s_ptlsGC = Value;
  v13 = s_ptlsdataGC;
  if ( s_ptlsdataGC )
  {
    v14 = &s_ptlsdataGC;
    do
    {
      if ( *((_BYTE *)v13 + 48) )
      {
        v15 = SpinLock((volatile unsigned __int64 *)v13 + 3);
        v16 = SpinLock((volatile unsigned __int64 *)v13 + 1);
        for ( k = (unsigned __int64)v13; ; k = v18 )
        {
          v18 = v16 & 0xFFFFFFFFFFFFFFF9uLL;
          if ( (struct TLSDATA *)(v16 & 0xFFFFFFFFFFFFFFF9uLL) == v13 )
            break;
          v16 = SpinLock((volatile unsigned __int64 *)(v18 + 8));
          *(_QWORD *)(k + 8) = v18;
        }
        *(_QWORD *)(k + 8) = v15 & 0xFFFFFFFFFFFFFFF9uLL;
        *((_QWORD *)v13 + 3) = v13;
        *((_BYTE *)v13 + 48) = 0;
      }
      v14 = Base::TestAndDeleteThreadExitedAndReturnNextOne(v14);
      v13 = *v14;
    }
    while ( *v14 );
    v1 = v25;
  }
  Base::s_ptlsGC = 0;
  --Base::s_lInGC;
  if ( v1 )
  {
    (*(void (__fastcall **)(CSMutex *))(*(_QWORD *)v1 + 32LL))(v1);
    (*(void (__fastcall **)(CSMutex *))(*(_QWORD *)v1 + 16LL))(v1);
  }
}

```

## disassembly

```asm
0x18002f5c4  push    rbx
0x18002f5c6  push    rsi
0x18002f5c7  push    rdi
0x18002f5c8  push    r13
0x18002f5ca  push    r14
0x18002f5cc  push    r15
0x18002f5ce  sub     rsp, 7B8h
0x18002f5d5  mov     rax, cs:__security_cookie
0x18002f5dc  xor     rax, rsp
0x18002f5df  mov     [rsp+7E8h+var_48], rax
0x18002f5e7  mov     [rsp+7E8h+var_7A8], ecx
0x18002f5eb  xor     edx, edx; Val
0x18002f5ed  mov     r8d, 6D0h; Size
0x18002f5f3  lea     rcx, [rsp+7E8h+ContextRecord]; void *
0x18002f5fb  call    memset_0
0x18002f600  xorps   xmm0, xmm0
0x18002f603  movups  xmmword ptr [rsp+7E8h+Buffer.BaseAddress], xmm0
0x18002f608  movups  xmmword ptr [rsp+7E8h+Buffer.AllocationProtect], xmm0
0x18002f60d  movups  xmmword ptr [rsp+7E8h+Buffer.State], xmm0
0x18002f615  xor     esi, esi
0x18002f617  cmp     cs:?s_fNoFullGC@Base@@2_NA, sil; bool Base::s_fNoFullGC
0x18002f61e  jnz     loc_18002FC6A
0x18002f624  mov     rbx, cs:?g_pMutexFullGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexFullGC
0x18002f62b  mov     [rsp+7E8h+var_790], rbx
0x18002f630  mov     [rsp+7E8h+var_7B0], rbx
0x18002f635  test    rbx, rbx
0x18002f638  jz      short loc_18002F658
0x18002f63a  mov     rax, [rbx]
0x18002f63d  mov     rcx, rbx
0x18002f640  mov     rax, [rax+8]
0x18002f644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f649  mov     rax, [rbx]
0x18002f64c  mov     rcx, rbx
0x18002f64f  mov     rax, [rax+18h]
0x18002f653  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f658  mov     rax, cs:?g_pMutexName@@3PEAVApartmentMutex@@EA; ApartmentMutex * g_pMutexName
0x18002f65f  cmp     [rax+40h], esi
0x18002f662  jg      loc_18002FC51
0x18002f668  mov     rax, cs:?g_pMutexAtom@@3PEAVApartmentMutex@@EA; ApartmentMutex * g_pMutexAtom
0x18002f66f  cmp     [rax+40h], esi
0x18002f672  jg      loc_18002FC51
0x18002f678  mov     [rsp+7E8h+var_798], rsi
0x18002f67d  mov     r15b, sil
0x18002f680  mov     [rsp+7E8h+var_7C8], sil
0x18002f685  inc     cs:?s_ulGCCycle@Base@@0KA; ulong Base::s_ulGCCycle
0x18002f68b  call    ?FreeDeadList@Base@@CAXXZ; Base::FreeDeadList(void)
0x18002f690  nop
0x18002f691  mov     cs:byte_180170118, sil
0x18002f698  mov     rax, cs:lpMem
0x18002f69f  mov     cs:qword_180170110, rax
0x18002f6a6  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x18002f6ac  call    cs:__imp_TlsGetValue
0x18002f6b2  mov     r13, rax
0x18002f6b5  mov     [rsp+7E8h+var_798], rax
0x18002f6ba  mov     rcx, rax; struct TLSDATA *
0x18002f6bd  call    ?flushToZeroList@Base@@CAXPEAUTLSDATA@@@Z; Base::flushToZeroList(TLSDATA *)
0x18002f6c2  mov     r14, cs:?g_ptlsdata@@3PEAUTLSDATA@@EA; TLSDATA * g_ptlsdata
0x18002f6c9  mov     cs:?s_ptlsdataGC@@3PEAUTLSDATA@@EA, r14; TLSDATA * s_ptlsdataGC
0x18002f6d0  mov     rdi, r14
0x18002f6d3  test    rdi, rdi
0x18002f6d6  jz      short loc_18002F724
0x18002f6d8  cmp     [rdi+80h], sil
0x18002f6df  jz      short loc_18002F6E9
0x18002f6e1  mov     rcx, rdi; struct TLSDATA *
0x18002f6e4  call    ?flushToZeroList@Base@@CAXPEAUTLSDATA@@@Z; Base::flushToZeroList(TLSDATA *)
0x18002f6e9  cmp     [rdi+30h], sil
0x18002f6ed  jnz     short loc_18002F713
0x18002f6ef  lea     rcx, [rdi+18h]; volatile unsigned __int64 *
0x18002f6f3  call    ?SpinLock@@YA_KPEC_K@Z; SpinLock(unsigned __int64 volatile *)
0x18002f6f8  lea     rcx, [rdi+8]; volatile unsigned __int64 *
0x18002f6fc  call    ?SpinLock@@YA_KPEC_K@Z; SpinLock(unsigned __int64 volatile *)
0x18002f701  and     rax, 0FFFFFFFFFFFFFFF9h
0x18002f705  mov     [rdi+18h], rax
0x18002f709  mov     [rdi+8], rdi
0x18002f70d  mov     byte ptr [rdi+30h], 1
0x18002f711  jmp     short loc_18002F717
0x18002f713  mov     [rdi+31h], sil
0x18002f717  mov     rdi, [rdi+28h]
0x18002f71b  mov     r14, cs:?s_ptlsdataGC@@3PEAUTLSDATA@@EA; TLSDATA * s_ptlsdataGC
0x18002f722  jmp     short loc_18002F6D3
0x18002f724  cmp     cs:?s_fStartedPartialGC@Base@@0_NA, sil; bool Base::s_fStartedPartialGC
0x18002f72b  jz      short loc_18002F742
0x18002f72d  lea     rax, ?StackExitNormal@Base@@SAXPEAUTLSDATA@@@Z; Base::StackExitNormal(TLSDATA *)
0x18002f734  mov     cs:?g_pfnExit@@3P6AXPEAUTLSDATA@@@ZEA, rax; void (*g_pfnExit)(TLSDATA *)
0x18002f73b  mov     cs:?s_fStartedPartialGC@Base@@0_NA, sil; bool Base::s_fStartedPartialGC
0x18002f742  mov     rax, cs:qword_180170120
0x18002f749  mov     cs:qword_180170128, rax
0x18002f750  test    r14, r14
0x18002f753  jz      loc_18002F985
0x18002f759  mov     [rsp+7E8h+var_7C8], sil
0x18002f75e  mov     rdx, cs:?g_pMutexPointer@@3PEAVCSMutex@@EA; struct Mutex *
0x18002f765  lea     rcx, [rsp+7E8h+var_7C0]; this
0x18002f76a  call    ??0MutexLock@@QEAA@PEAVMutex@@@Z; MutexLock::MutexLock(Mutex *)
0x18002f76f  mov     [rsp+7E8h+var_7C8], 1
0x18002f774  cmp     [r14+50h], esi
0x18002f778  jnz     short loc_18002F789
0x18002f77a  lea     rcx, [rsp+7E8h+var_7C0]; this
0x18002f77f  call    ?Release@MutexLock@@QEAAXXZ; MutexLock::Release(void)
0x18002f784  jmp     loc_18002F97C
0x18002f789  cmp     r14, r13
0x18002f78c  setz    dil
0x18002f790  mov     rax, [r14+20h]
0x18002f794  mov     [rsp+7E8h+hThread], rax
0x18002f799  test    rax, rax
0x18002f79c  jz      short loc_18002F77A
0x18002f79e  test    dil, dil
0x18002f7a1  jnz     short loc_18002F7D5
0x18002f7a3  mov     rcx, rax; hThread
0x18002f7a6  call    cs:__imp_SuspendThread
0x18002f7ac  cmp     eax, 0FFFFFFFFh
0x18002f7af  jnz     short loc_18002F7B8
0x18002f7b1  call    ?record@failure_tracing@@SAXXZ; failure_tracing::record(void)
0x18002f7b6  jmp     short loc_18002F77A
0x18002f7b8  cmp     [r14+50h], esi
0x18002f7bc  jnz     short loc_18002F7D0
0x18002f7be  mov     rcx, [rsp+7E8h+hThread]; hThread
0x18002f7c3  call    cs:__imp_ResumeThread
0x18002f7c9  cmp     eax, 0FFFFFFFFh
0x18002f7cc  jnz     short loc_18002F77A
0x18002f7ce  jmp     short loc_18002F7B1
0x18002f7d0  mov     rax, [rsp+7E8h+hThread]
0x18002f7d5  mov     byte ptr [r14+32h], 1
0x18002f7da  test    byte ptr [rsp+7E8h+var_7A8], 4
0x18002f7df  jz      short loc_18002F7EA
0x18002f7e1  test    dil, dil
0x18002f7e4  jnz     loc_18002F95B
0x18002f7ea  mov     [rsp+7E8h+ContextRecord.ContextFlags], 10000Bh
0x18002f7f5  test    dil, dil
0x18002f7f8  jz      short loc_18002F80A
0x18002f7fa  lea     rcx, [rsp+7E8h+ContextRecord]; ContextRecord
0x18002f802  call    cs:__imp_RtlCaptureContext
0x18002f808  jmp     short loc_18002F83B
0x18002f80a  lea     rdx, [rsp+7E8h+ContextRecord]; lpContext
0x18002f812  mov     rcx, rax; hThread
0x18002f815  call    cs:__imp_GetThreadContext
0x18002f81b  test    eax, eax
0x18002f81d  jnz     short loc_18002F83B
0x18002f81f  call    ?record@failure_tracing@@SAXXZ; failure_tracing::record(void)
0x18002f824  mov     r15b, 1
0x18002f827  mov     [rsp+7E8h+var_7C7], r15b
0x18002f82c  lea     rcx, [rsp+7E8h+var_7C0]; this
0x18002f831  call    ?Release@MutexLock@@QEAAXXZ; MutexLock::Release(void)
0x18002f836  jmp     loc_18002FB16
0x18002f83b  movzx   r8d, dil; int
0x18002f83f  mov     r9, r14; struct TLSDATA *
0x18002f842  lea     rdx, [rsp+7E8h+var_48]; __int64 *
0x18002f84a  lea     rcx, [rsp+7E8h+ContextRecord]; __int64 *
0x18002f852  call    ?markStackObjects@Base@@CAXPEA_J0HPEAUTLSDATA@@@Z; Base::markStackObjects(__int64 *,__int64 *,int,TLSDATA *)
0x18002f857  mov     rax, [rsp+7E8h+ContextRecord.Rsp]
0x18002f85f  mov     [rsp+7E8h+var_7A0], rax
0x18002f864  mov     [rsp+7E8h+var_788], rax
0x18002f869  mov     r8d, 30h ; '0'; dwLength
0x18002f86f  lea     rdx, [rsp+7E8h+Buffer]; lpBuffer
0x18002f874  mov     rcx, rax; lpAddress
0x18002f877  call    cs:__imp_VirtualQuery
0x18002f87d  test    rax, rax
0x18002f880  jnz     short loc_18002F89E
0x18002f882  call    ?record@failure_tracing@@SAXXZ; failure_tracing::record(void)
0x18002f887  mov     r15b, 1
0x18002f88a  mov     [rsp+7E8h+var_7C7], r15b
0x18002f88f  lea     rcx, [rsp+7E8h+var_7C0]; this
0x18002f894  call    ?Release@MutexLock@@QEAAXXZ; MutexLock::Release(void)
0x18002f899  jmp     loc_18002FB16
0x18002f89e  test    dil, dil
0x18002f8a1  jnz     short loc_18002F920
0x18002f8a3  test    [rsp+7E8h+Buffer.AllocationProtect], 100h
0x18002f8ab  jz      short loc_18002F920
0x18002f8ad  xorps   xmm0, xmm0
0x18002f8b0  movups  xmmword ptr [rsp+7E8h+SystemInfo], xmm0
0x18002f8b8  movups  xmmword ptr [rsp+7E8h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x18002f8c0  movups  xmmword ptr [rsp+7E8h+SystemInfo.dwNumberOfProcessors], xmm0
0x18002f8c8  lea     rcx, [rsp+7E8h+SystemInfo]; lpSystemInfo
0x18002f8d0  call    cs:__imp_GetSystemInfo
0x18002f8d6  mov     ecx, [rsp+7E8h+SystemInfo.dwPageSize]
0x18002f8dd  add     rcx, [rsp+7E8h+var_7A0]; lpAddress
0x18002f8e2  mov     r8d, 30h ; '0'; dwLength
0x18002f8e8  lea     rdx, [rsp+7E8h+Buffer]; lpBuffer
0x18002f8ed  call    cs:__imp_VirtualQuery
0x18002f8f3  test    rax, rax
0x18002f8f6  jnz     short loc_18002F914
0x18002f8f8  call    ?record@failure_tracing@@SAXXZ; failure_tracing::record(void)
0x18002f8fd  mov     r15b, 1
0x18002f900  mov     [rsp+7E8h+var_7C7], r15b
0x18002f905  lea     rcx, [rsp+7E8h+var_7C0]; this
0x18002f90a  call    ?Release@MutexLock@@QEAAXXZ; MutexLock::Release(void)
0x18002f90f  jmp     loc_18002FB16
0x18002f914  mov     r10, [rsp+7E8h+Buffer.BaseAddress]
0x18002f919  mov     [rsp+7E8h+var_788], r10
0x18002f91e  jmp     short loc_18002F925
0x18002f920  mov     r10, [rsp+7E8h+var_7A0]
0x18002f925  mov     rdx, [rsp+7E8h+Buffer.RegionSize]
0x18002f92d  add     rdx, [rsp+7E8h+Buffer.BaseAddress]; __int64 *
0x18002f932  mov     r9, r14; struct TLSDATA *
0x18002f935  movzx   r8d, dil; int
0x18002f939  mov     rcx, r10; __int64 *
0x18002f93c  call    ?markStackObjects@Base@@CAXPEA_J0HPEAUTLSDATA@@@Z; Base::markStackObjects(__int64 *,__int64 *,int,TLSDATA *)
0x18002f941  test    dil, dil
0x18002f944  jnz     short loc_18002F95B
0x18002f946  mov     rcx, [rsp+7E8h+hThread]; hThread
0x18002f94b  call    cs:__imp_ResumeThread
0x18002f951  cmp     eax, 0FFFFFFFFh
0x18002f954  jnz     short loc_18002F95B
0x18002f956  call    ?record@failure_tracing@@SAXXZ; failure_tracing::record(void)
0x18002f95b  mov     [r14+32h], sil
0x18002f95f  lea     rcx, [rsp+7E8h+var_7C0]; this
0x18002f964  cmp     cs:byte_180170118, sil
0x18002f96b  jz      short loc_18002F977
0x18002f96d  call    ?Release@MutexLock@@QEAAXXZ; MutexLock::Release(void)
0x18002f972  jmp     loc_18002FB16
0x18002f977  call    ?Release@MutexLock@@QEAAXXZ; MutexLock::Release(void)
0x18002f97c  mov     r14, [r14+28h]
0x18002f980  jmp     loc_18002F750
0x18002f985  mov     cs:?s_ptlsCheckZeroList@Base@@0PEAUTLSDATA@@EA, r13; TLSDATA * Base::s_ptlsCheckZeroList
0x18002f98c  mov     cs:?s_ptlsGC@Base@@0PEAUTLSDATA@@EA, r13; TLSDATA * Base::s_ptlsGC
0x18002f993  xor     r8d, r8d; unsigned int
0x18002f996  mov     dl, 1; bool
0x18002f998  mov     rcx, r13; struct TLSDATA *
0x18002f99b  call    ?freeRentalObjects@Base@@CAXPEAUTLSDATA@@_NI@Z; Base::freeRentalObjects(TLSDATA *,bool,uint)
0x18002f9a0  mov     rdi, cs:?s_ptlsdataGC@@3PEAUTLSDATA@@EA; TLSDATA * s_ptlsdataGC
0x18002f9a7  test    rdi, rdi
0x18002f9aa  jz      short loc_18002F9BA
0x18002f9ac  mov     rcx, rdi; struct TLSDATA *
0x18002f9af  call    ?FreeObjects@Base@@CAHPEAUTLSDATA@@@Z; Base::FreeObjects(TLSDATA *)
0x18002f9b4  mov     rdi, [rdi+28h]
0x18002f9b8  jmp     short loc_18002F9A7
0x18002f9ba  cmp     cs:?g_fClassInitCalled@@3_NA, sil; bool g_fClassInitCalled
0x18002f9c1  jz      short loc_18002FA1A
0x18002f9c3  test    byte ptr cs:?s_ulGCCycle@Base@@0KA, 3; ulong Base::s_ulGCCycle
0x18002f9ca  jnz     short loc_18002FA1A
0x18002f9cc  mov     rdx, cs:?g_pMutexName@@3PEAVApartmentMutex@@EA; struct Mutex *
0x18002f9d3  lea     rcx, [rsp+7E8h+hThread]; this
0x18002f9d8  call    ??0MutexLock@@QEAA@PEAVMutex@@@Z; MutexLock::MutexLock(Mutex *)
0x18002f9dd  mov     rcx, cs:?s_pNames@Name@@1PEAVStringHashtable@@EA; struct Hashtable *
0x18002f9e4  call    ?FreeObjects@Base@@KAHPEAVHashtable@@@Z; Base::FreeObjects(Hashtable *)
0x18002f9e9  lea     rcx, [rsp+7E8h+hThread]; this
0x18002f9ee  call    ?Release@MutexLock@@QEAAXXZ; MutexLock::Release(void)
0x18002f9f3  mov     rdx, cs:?g_pMutexAtom@@3PEAVApartmentMutex@@EA; struct Mutex *
0x18002f9fa  lea     rcx, [rsp+7E8h+hThread]; this
0x18002f9ff  call    ??0MutexLock@@QEAA@PEAVMutex@@@Z; MutexLock::MutexLock(Mutex *)
0x18002fa04  mov     rcx, cs:?atoms@Atom@@0PEAVStringHashtable@@EA; struct Hashtable *
0x18002fa0b  call    ?FreeObjects@Base@@KAHPEAVHashtable@@@Z; Base::FreeObjects(Hashtable *)
0x18002fa10  lea     rcx, [rsp+7E8h+hThread]; this
0x18002fa15  call    ?Release@MutexLock@@QEAAXXZ; MutexLock::Release(void)
0x18002fa1a  mov     cs:?s_ptlsCheckZeroList@Base@@0PEAUTLSDATA@@EA, rsi; TLSDATA * Base::s_ptlsCheckZeroList
0x18002fa21  mov     cs:?s_ptlsGC@Base@@0PEAUTLSDATA@@EA, rsi; TLSDATA * Base::s_ptlsGC
0x18002fa28  mov     rax, cs:qword_180170120
0x18002fa2f  mov     cs:qword_180170128, rax
0x18002fa36  jmp     loc_18002FB16
0x18002fa3b  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x18002fa41  call    cs:__imp_TlsGetValue
0x18002fa47  mov     rbx, rax
0x18002fa4a  cmp     dword ptr [rax+54h], 0C00000FDh
0x18002fa51  jnz     short loc_18002FACC
0x18002fa53  call    cs:__imp__resetstkoflw
0x18002fa59  test    eax, eax
0x18002fa5b  jnz     short loc_18002FAAE
0x18002fa5d  mov     rcx, cs:?g_pMutexGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexGC
0x18002fa64  test    rcx, rcx
0x18002fa67  jz      short loc_18002FA7B
0x18002fa69  cmp     [rcx+50h], rbx
0x18002fa6d  jnz     short loc_18002FA7B
0x18002fa6f  mov     rax, [rcx]
0x18002fa72  mov     rax, [rax+20h]
0x18002fa76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fa7b  mov     rcx, cs:?g_pMutexFullGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexFullGC
0x18002fa82  test    rcx, rcx
0x18002fa85  jz      short loc_18002FA99
0x18002fa87  cmp     [rcx+50h], rbx
0x18002fa8b  jnz     short loc_18002FA99
0x18002fa8d  mov     rax, [rcx]
0x18002fa90  mov     rax, [rax+20h]
0x18002fa94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fa99  xor     r9d, r9d; lpArguments
0x18002fa9c  xor     r8d, r8d; nNumberOfArguments
0x18002fa9f  xor     edx, edx; dwExceptionFlags
0x18002faa1  mov     ecx, 0C00000FDh; dwExceptionCode
0x18002faa6  call    cs:__imp_RaiseException
0x18002faac  jmp     short loc_18002FACC
0x18002faae  mov     rax, [rbx+60h]
0x18002fab2  mov     [rbx+68h], rax
0x18002fab6  lea     rax, ?s_cexpOutOfStack@Exception@@2V_CodebaseException@@B; _CodebaseException const Exception::s_cexpOutOfStack
0x18002fabd  mov     [rbx+60h], rax
0x18002fac1  mov     dword ptr [rbx+54h], 800703E9h
0x18002fac8  mov     byte ptr [rbx+78h], 0
0x18002facc  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002fad1  call    ?record@failure_tracing@@SAXXZ; failure_tracing::record(void)
0x18002fad6  cmp     [rsp+7E8h+var_7C8], 0
0x18002fadb  jz      short loc_18002FAF0
0x18002fadd  mov     rcx, cs:?g_pMutexPointer@@3PEAVCSMutex@@EA; CSMutex * g_pMutexPointer
0x18002fae4  mov     rax, [rcx]
0x18002fae7  mov     rax, [rax+20h]
0x18002faeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002faf0  lea     rcx, aExceptionInGar_1; "Exception in garbage collecting (Base::"...
0x18002faf7  call    cs:__imp_OutputDebugStringW
0x18002fafd  mov     r15b, 1
0x18002fb00  mov     [rsp+7E8h+var_7C7], r15b
0x18002fb05  xor     esi, esi
0x18002fb07  mov     r13, [rsp+7E8h+var_798]
0x18002fb0c  mov     rbx, [rsp+7E8h+var_7B0]
0x18002fb11  mov     [rsp+7E8h+var_790], rbx
  ... truncated ...
```
