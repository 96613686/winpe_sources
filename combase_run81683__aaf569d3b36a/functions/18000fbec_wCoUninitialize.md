# wCoUninitialize

- ea: `0x18000fbec`
- end: `0x1800100d5`
- name: `wCoUninitialize`
- size: `1257`
- prototype: `void __fastcall(COleTls *Tls, int fHostThread)`
- caller_count: `3`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000ee90`
- `0x1800898d0`
- `0x18008b0f4`

## callees

- `0x180006250`
- `0x180006390`
- `0x18000712c`
- `0x18000cda0`
- `0x18000d190`
- `0x18000f72c`
- `0x18000fbec`
- `0x1800100dc`
- `0x1800101c8`
- `0x180010250`
- `0x1800188a0`
- `0x18007fdf8`
- `0x18008db2c`
- `0x180141170`
- `0x1801457c0`
- `0x180255010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000fe05`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000fe05`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fd24`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fd79`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fde9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ff1e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fd24`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fd79`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fde9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ff1e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fde3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fde3`
- `OLEAUT32!__imp_OACleanup` at `0x18000fe10`
- `OLEAUT32!__imp_OACleanup` at `0x18000fe10`

## string_xrefs

- `0x18000fd3f`: `onecore\com\combase\class\compobj.cxx`
- `0x180010032`: `onecore\com\combase\class\compobj.cxx`
- `0x1800100b8`: `onecore\com\combase\class\compobj.cxx`
- `0x18000fdfe`: `oleaut32.dll`

## pseudocode

```c
void __fastcall wCoUninitialize(COleTls *Tls, int fHostThread)
{
  _QWORD *ReservedForOle; // rbx
  __int64 *v5; // rdi
  __int64 v6; // r14
  bool v7; // zf
  __int64 *v8; // rdx
  _QWORD *v9; // rcx
  __int64 *v10; // r8
  unsigned int dwFlags; // edx
  tagSOleTlsData *pData; // rbx
  __int64 v13; // rcx
  const char *v14; // r9
  __int64 v15; // rcx
  __int64 v16; // rcx
  _DWORD *v17; // rdi
  int v18; // ebx
  __int64 v19; // rcx
  _QWORD *v20; // rbx
  __int64 *v21; // rdi
  __int64 v22; // rsi
  __int64 *v23; // rdx
  _QWORD *v24; // rcx
  __int64 *v25; // r8
  COleStaticMutexSem *v26; // rcx
  __int64 v27; // rcx
  COleStaticMutexSem *v28; // rcx
  __int64 v29; // rcx
  COleStaticMutexSem *v30; // rcx
  __int64 v31; // rcx
  unsigned int v32; // edx
  TraceLevel v33; // r9d
  __int64 v34; // rcx
  TraceLevel v35; // r9d
  COleTls v36; // [rsp+60h] [rbp+8h] BYREF

  if ( fHostThread )
  {
    ReservedForOle = NtCurrentTeb()->ReservedForOle;
    v5 = (__int64 *)ReservedForOle[46];
    if ( v5 )
    {
      do
      {
        ++*((_DWORD *)v5 + 4);
        v6 = v5[3];
        if ( v6 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v5[3]);
          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v6 + 40LL))(v6, *((unsigned int *)ReservedForOle + 10));
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
        }
        v7 = (*((_DWORD *)v5 + 4))-- == 1;
        v8 = (__int64 *)*v5;
        if ( v7 )
        {
          v9 = NtCurrentTeb()->ReservedForOle;
          if ( v8 )
            v8[1] = v5[1];
          v10 = (__int64 *)v5[1];
          if ( v10 )
            *v10 = *v5;
          if ( v5 == (__int64 *)v9[46] )
            v9[46] = *v5;
          v5[1] = 0;
          *v5 = v9[47];
          v9[47] = v5;
        }
        v5 = v8;
      }
      while ( v8 );
    }
  }
  dwFlags = Tls->_pData->dwFlags;
  if ( (dwFlags & 0x20) != 0 )
  {
    if ( gfEnableTracing && IsWppLevelEnabled(VERBOSE) )
      ComTraceMessageT<unsigned int>(
        "onecore\\com\\combase\\class\\compobj.cxx",
        "wCoUninitialize",
        3950,
        v33,
        L"CoUninit calling CoUninit. TLS->Flags %d",
        v32);
    goto $exit;
  }
  Tls->_pData->dwFlags = dwFlags | 0x20;
  pData = (tagSOleTlsData *)NtCurrentTeb()->ReservedForOle;
  v36._pData = pData;
  if ( !pData )
  {
    if ( COleTls::TLSAllocData(&v36) < 0 )
      goto LABEL_17;
    pData = v36._pData;
  }
  TlsClearErrorInfo();
  pData->punkError = 0;
LABEL_17:
  if ( SLOBYTE(Tls->_pData->dwFlags) >= 0 )
  {
    if ( g_mxsSingleThreadOle._cs.OwningThread == (void *)GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs(v13);
    COleStaticMutexSem::Request(&g_mxsSingleThreadOle, "onecore\\com\\combase\\class\\compobj.cxx", 0xFA0u, v14);
    while ( g_cMTAInits == 1 || g_cProcessInits == 2 && !fHostThread && (gMTHost._dwType & 0x40) != 0 )
    {
      COleStaticMutexSem::Release(&g_mxsSingleThreadOle);
      if ( COleStaticMutexSem::IsLockHeld(v28) )
        MicrosoftTelemetryAssertTriggeredNoArgs(v29);
      if ( ApartmentUninitialize(fHostThread) )
        break;
      if ( !COleStaticMutexSem::IsLockHeld(v30) )
        MicrosoftTelemetryAssertTriggeredNoArgs(v31);
    }
    wCoDecrementMTAUsage();
LABEL_24:
    ClearTlsApartmentAndEmptyContext(Tls);
    if ( g_mxsSingleThreadOle._cs.OwningThread != (void *)GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs(v15);
    DecrementProcessInitializeCount();
    if ( !--g_mxsSingleThreadOle._cLocks && g_mxsSingleThreadOle._lockOrder != Highest )
    {
      v17 = NtCurrentTeb()->ReservedForOle;
      if ( v17 )
      {
        LOBYTE(v16) = g_mxsSingleThreadOle._lockOrder;
        v18 = 1 << g_mxsSingleThreadOle._lockOrder;
        if ( ((1 << g_mxsSingleThreadOle._lockOrder) & v17[144]) == 0 )
          MicrosoftTelemetryAssertTriggeredNoArgs(v16);
        v17[144] &= ~v18;
      }
    }
    LeaveCriticalSection(&g_mxsSingleThreadOle._cs);
    if ( g_mxsSingleThreadOle._cs.OwningThread == (void *)GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs(v19);
    if ( GetModuleHandleW(L"oleaut32.dll") )
      OACleanup();
    Tls->_pData->dwFlags = Tls->_pData->dwFlags & 2 | 1;
    Tls->_pData->cComInits = 0;
    goto $exit;
  }
  if ( ApartmentUninitialize(fHostThread) )
  {
    if ( g_mxsSingleThreadOle._cs.OwningThread != (void *)GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs(v27);
    UninitMainThreadWnd();
    if ( (Tls->_pData->dwFlags & 0x40400000) == 0 && !--g_cClassicSTAInits )
      UnRegisterOleWndClass();
    --g_cSTAInits;
    goto LABEL_24;
  }
  Tls->_pData->dwFlags &= ~0x20u;
  if ( gfEnableTracing && IsWppLevelEnabled(VERBOSE) )
    ComTraceMessageT<unsigned int>(
      "onecore\\com\\combase\\class\\compobj.cxx",
      "wCoUninitialize",
      3969,
      v35,
      L"Wait aborted. TLS->Flags %d",
      Tls->_pData->dwFlags);
  if ( COleStaticMutexSem::IsLockHeld(v26) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v34);
$exit:
  if ( fHostThread )
  {
    v20 = NtCurrentTeb()->ReservedForOle;
    v21 = (__int64 *)v20[46];
    if ( v21 )
    {
      do
      {
        ++*((_DWORD *)v21 + 4);
        v22 = v21[3];
        if ( v22 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 8LL))(v21[3]);
          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v22 + 48LL))(v22, *((unsigned int *)v20 + 10));
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
        }
        v7 = (*((_DWORD *)v21 + 4))-- == 1;
        v23 = (__int64 *)*v21;
        if ( v7 )
        {
          v24 = NtCurrentTeb()->ReservedForOle;
          if ( v23 )
            v23[1] = v21[1];
          v25 = (__int64 *)v21[1];
          if ( v25 )
            *v25 = *v21;
          if ( v21 == (__int64 *)v24[46] )
            v24[46] = *v21;
          v21[1] = 0;
          *v21 = v24[47];
          v24[47] = v21;
        }
        v21 = v23;
      }
      while ( v23 );
    }
  }
}

```

## disassembly

```asm
0x18000fbec  mov     [rsp+arg_10], rbx
0x18000fbf1  push    rbp
0x18000fbf2  push    rsi
0x18000fbf3  push    rdi
0x18000fbf4  push    r12
0x18000fbf6  push    r14
0x18000fbf8  sub     rsp, 30h
0x18000fbfc  or      r12d, 0FFFFFFFFh
0x18000fc00  mov     ebp, fHostThread
0x18000fc02  mov     rsi, Tls
0x18000fc05  test    fHostThread, fHostThread
0x18000fc07  jz      loc_18000FCD4
0x18000fc0d  mov     rbx, gs:30h
0x18000fc16  mov     rbx, [rbx+1758h]
0x18000fc1d  mov     rdi, [rbx+170h]
0x18000fc24  test    rdi, rdi
0x18000fc27  jz      loc_18000FCD4
0x18000fc2d  inc     dword ptr [rdi+10h]
0x18000fc30  mov     r14, [rdi+18h]
0x18000fc34  test    r14, r14
0x18000fc37  jz      short loc_18000FC69
0x18000fc39  mov     rax, [r14]
0x18000fc3c  mov     Tls, r14
0x18000fc3f  mov     rax, [rax+8]
0x18000fc43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc48  mov     rax, [r14]
0x18000fc4b  mov     Tls, r14
0x18000fc4e  mov     fHostThread, [rbx+28h]
0x18000fc51  mov     rax, [rax+28h]
0x18000fc55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc5a  mov     rax, [r14]
0x18000fc5d  mov     Tls, r14
0x18000fc60  mov     rax, [rax+10h]
0x18000fc64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc69  add     [rdi+10h], r12d
0x18000fc6d  mov     rdx, [rdi]
0x18000fc70  jnz     short loc_18000FCC8
0x18000fc72  mov     rax, gs:30h
0x18000fc7b  mov     Tls, [rax+1758h]
0x18000fc82  test    rdx, rdx
0x18000fc85  jz      short loc_18000FC8F
0x18000fc87  mov     rax, [rdi+8]
0x18000fc8b  mov     [rdx+8], rax
0x18000fc8f  mov     r8, [rdi+8]
0x18000fc93  test    r8, r8
0x18000fc96  jnz     loc_18000FFD0
0x18000fc9c  cmp     rdi, [Tls+170h]
0x18000fca3  jnz     short loc_18000FCAF
0x18000fca5  mov     rax, [rdi]
0x18000fca8  mov     [Tls+170h], rax
0x18000fcaf  mov     qword ptr [rdi+8], 0
0x18000fcb7  mov     rax, [Tls+178h]
0x18000fcbe  mov     [rdi], rax
0x18000fcc1  mov     [Tls+178h], rdi
0x18000fcc8  mov     rdi, rdx
0x18000fccb  test    rdx, rdx
0x18000fcce  jnz     loc_18000FC2D
0x18000fcd4  mov     rax, [rsi]
0x18000fcd7  mov     fHostThread, [rax+14h]
0x18000fcda  test    dl, 20h
0x18000fcdd  jnz     loc_18000FFF2
0x18000fce3  or      fHostThread, 20h
0x18000fce6  mov     [rax+14h], fHostThread
0x18000fce9  mov     rbx, gs:30h
0x18000fcf2  mov     rbx, [rbx+1758h]
0x18000fcf9  mov     [rsp+58h+arg_0._pData], rbx
0x18000fcfe  test    rbx, rbx
0x18000fd01  jz      loc_18000FF55
0x18000fd07  call    ?TlsClearErrorInfo@@YAXXZ; TlsClearErrorInfo(void)
0x18000fd0c  mov     qword ptr [rbx+198h], 0
0x18000fd17  mov     rax, [rsi]
0x18000fd1a  test    byte ptr [rax+14h], 80h
0x18000fd1e  jnz     loc_18000FF0F
0x18000fd24  call    cs:__imp_GetCurrentThreadId
0x18000fd2a  mov     eax, eax
0x18000fd2c  cmp     cs:?g_mxsSingleThreadOle@@3VCOleStaticMutexSem@@A._cs.OwningThread, rax; COleStaticMutexSem g_mxsSingleThreadOle ...
0x18000fd33  jz      loc_180010074
0x18000fd39  mov     r8d, 0FA0h; dwLine
0x18000fd3f  lea     rdx, aOnecoreComComb_154; "onecore\\com\\combase\\class\\compobj.c"...
0x18000fd46  lea     Tls, ?g_mxsSingleThreadOle@@3VCOleStaticMutexSem@@A; this
0x18000fd4d  call    ?Request@COleStaticMutexSem@@QEAAXPEBDK0@Z; COleStaticMutexSem::Request(char const *,ulong,char const *)
0x18000fd52  cmp     cs:g_cMTAInits, 1
0x18000fd59  jz      loc_18000FF86
0x18000fd5f  cmp     cs:g_cProcessInits, 2
0x18000fd66  jz      loc_18000FF71
0x18000fd6c  call    ?wCoDecrementMTAUsage@@YAXXZ; wCoDecrementMTAUsage(void)
0x18000fd71  mov     Tls, rsi; tls
0x18000fd74  call    ?ClearTlsApartmentAndEmptyContext@@YAXAEAVCOleTls@@@Z; ClearTlsApartmentAndEmptyContext(COleTls &)
0x18000fd79  call    cs:__imp_GetCurrentThreadId
0x18000fd7f  mov     eax, eax
0x18000fd81  cmp     cs:?g_mxsSingleThreadOle@@3VCOleStaticMutexSem@@A._cs.OwningThread, rax; COleStaticMutexSem g_mxsSingleThreadOle ...
0x18000fd88  jz      short loc_18000FD8F
0x18000fd8a  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "g_mxsSingleThreadOle.IsLockHeld()")
0x18000fd8f  call    ?DecrementProcessInitializeCount@@YA_NXZ; DecrementProcessInitializeCount(void)
0x18000fd94  add     cs:?g_mxsSingleThreadOle@@3VCOleStaticMutexSem@@A._cLocks, r12d; COleStaticMutexSem g_mxsSingleThreadOle ...
0x18000fd9b  jnz     short loc_18000FDDC
0x18000fd9d  cmp     cs:?g_mxsSingleThreadOle@@3VCOleStaticMutexSem@@A._lockOrder, 13h; COleStaticMutexSem g_mxsSingleThreadOle ...
0x18000fda4  jz      short loc_18000FDDC
0x18000fda6  mov     rax, gs:30h
0x18000fdaf  mov     rdi, [rax+1758h]
0x18000fdb6  test    rdi, rdi
0x18000fdb9  jz      short loc_18000FDDC
0x18000fdbb  mov     cl, cs:?g_mxsSingleThreadOle@@3VCOleStaticMutexSem@@A._lockOrder; COleStaticMutexSem g_mxsSingleThreadOle ...
0x18000fdc1  mov     ebx, 1
0x18000fdc6  shl     ebx, cl
0x18000fdc8  test    [rdi+240h], ebx
0x18000fdce  jz      loc_180010043
0x18000fdd4  not     ebx
0x18000fdd6  and     [rdi+240h], ebx
0x18000fddc  lea     Tls, ?g_mxsSingleThreadOle@@3VCOleStaticMutexSem@@A._cs; lpCriticalSection
0x18000fde3  call    cs:__imp_LeaveCriticalSection
0x18000fde9  call    cs:__imp_GetCurrentThreadId
0x18000fdef  mov     eax, eax
0x18000fdf1  cmp     cs:?g_mxsSingleThreadOle@@3VCOleStaticMutexSem@@A._cs.OwningThread, rax; COleStaticMutexSem g_mxsSingleThreadOle ...
0x18000fdf8  jz      loc_18001007E
0x18000fdfe  lea     Tls, aOleaut32Dll; "oleaut32.dll"
0x18000fe05  call    cs:__imp_GetModuleHandleW
0x18000fe0b  test    rax, rax
0x18000fe0e  jz      short loc_18000FE16
0x18000fe10  call    cs:__imp_OACleanup
0x18000fe16  mov     Tls, [rsi]
0x18000fe19  mov     eax, [Tls+14h]
0x18000fe1c  and     eax, 2
0x18000fe1f  or      eax, 1
0x18000fe22  mov     [Tls+14h], eax
0x18000fe25  mov     rax, [rsi]
0x18000fe28  mov     dword ptr [rax+28h], 0
0x18000fe2f  test    ebp, ebp
0x18000fe31  jz      loc_18000FEFE
0x18000fe37  mov     rbx, gs:30h
0x18000fe40  mov     rbx, [rbx+1758h]
0x18000fe47  mov     rdi, [rbx+170h]
0x18000fe4e  test    rdi, rdi
0x18000fe51  jz      loc_18000FEFE
0x18000fe57  inc     dword ptr [rdi+10h]
0x18000fe5a  mov     rsi, [rdi+18h]
0x18000fe5e  test    rsi, rsi
0x18000fe61  jz      short loc_18000FE93
0x18000fe63  mov     rax, [rsi]
0x18000fe66  mov     Tls, rsi
0x18000fe69  mov     rax, [rax+8]
0x18000fe6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe72  mov     rax, [rsi]
0x18000fe75  mov     Tls, rsi
0x18000fe78  mov     fHostThread, [rbx+28h]
0x18000fe7b  mov     rax, [rax+30h]
0x18000fe7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe84  mov     rax, [rsi]
0x18000fe87  mov     Tls, rsi
0x18000fe8a  mov     rax, [rax+10h]
0x18000fe8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe93  add     [rdi+10h], r12d
0x18000fe97  mov     rdx, [rdi]
0x18000fe9a  jnz     short loc_18000FEF2
0x18000fe9c  mov     rax, gs:30h
0x18000fea5  mov     Tls, [rax+1758h]
0x18000feac  test    rdx, rdx
0x18000feaf  jz      short loc_18000FEB9
0x18000feb1  mov     rax, [rdi+8]
0x18000feb5  mov     [rdx+8], rax
0x18000feb9  mov     r8, [rdi+8]
0x18000febd  test    r8, r8
0x18000fec0  jnz     loc_18000FFC5
0x18000fec6  cmp     rdi, [Tls+170h]
0x18000fecd  jnz     short loc_18000FED9
0x18000fecf  mov     rax, [rdi]
0x18000fed2  mov     [Tls+170h], rax
0x18000fed9  mov     qword ptr [rdi+8], 0
0x18000fee1  mov     rax, [Tls+178h]
0x18000fee8  mov     [rdi], rax
0x18000feeb  mov     [Tls+178h], rdi
0x18000fef2  mov     rdi, rdx
0x18000fef5  test    rdx, rdx
0x18000fef8  jnz     loc_18000FE57
0x18000fefe  mov     rbx, [rsp+58h+arg_10]
0x18000ff03  add     rsp, 30h
0x18000ff07  pop     r14
0x18000ff09  pop     r12
0x18000ff0b  pop     rdi
0x18000ff0c  pop     rsi
0x18000ff0d  pop     rbp
0x18000ff0e  retn
0x18000ff0f  mov     ecx, ebp; fHostThread
0x18000ff11  call    ?ApartmentUninitialize@@YAHH@Z; ApartmentUninitialize(int)
0x18000ff16  test    eax, eax
0x18000ff18  jz      loc_18001004D
0x18000ff1e  call    cs:__imp_GetCurrentThreadId
0x18000ff24  mov     eax, eax
0x18000ff26  cmp     cs:?g_mxsSingleThreadOle@@3VCOleStaticMutexSem@@A._cs.OwningThread, rax; COleStaticMutexSem g_mxsSingleThreadOle ...
0x18000ff2d  jz      short loc_18000FF34
0x18000ff2f  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "g_mxsSingleThreadOle.IsLockHeld()")
0x18000ff34  call    ?UninitMainThreadWnd@@YAXXZ; UninitMainThreadWnd(void)
0x18000ff39  mov     rax, [rsi]
0x18000ff3c  test    dword ptr [rax+14h], 40400000h
0x18000ff43  jz      loc_18000FFDB
0x18000ff49  add     cs:g_cSTAInits, r12d
0x18000ff50  jmp     loc_18000FD71
0x18000ff55  lea     Tls, [rsp+58h+arg_0]; this
0x18000ff5a  call    ?TLSAllocData@COleTls@@QEAAJXZ; COleTls::TLSAllocData(void)
0x18000ff5f  test    eax, eax
0x18000ff61  js      loc_18000FD17
0x18000ff67  mov     rbx, [rsp+58h+arg_0._pData]
0x18000ff6c  jmp     loc_18000FD07
0x18000ff71  test    ebp, ebp
0x18000ff73  jnz     loc_18000FD6C
0x18000ff79  test    byte ptr cs:?gMTHost@@3VCDllHost@@A._dwType, 40h; CDllHost gMTHost ...
0x18000ff80  jz      loc_18000FD6C
0x18000ff86  lea     Tls, ?g_mxsSingleThreadOle@@3VCOleStaticMutexSem@@A; this
0x18000ff8d  call    ?Release@COleStaticMutexSem@@QEAAXXZ; COleStaticMutexSem::Release(void)
0x18000ff92  call    ?IsLockHeld@COleStaticMutexSem@@QEAA_NXZ; COleStaticMutexSem::IsLockHeld(void)
0x18000ff97  test    al, al
0x18000ff99  jnz     loc_1800100CB
0x18000ff9f  mov     ecx, ebp; fHostThread
0x18000ffa1  call    ?ApartmentUninitialize@@YAHH@Z; ApartmentUninitialize(int)
0x18000ffa6  test    eax, eax
0x18000ffa8  jnz     loc_18000FD6C
0x18000ffae  call    ?IsLockHeld@COleStaticMutexSem@@QEAA_NXZ; COleStaticMutexSem::IsLockHeld(void)
0x18000ffb3  test    al, al
0x18000ffb5  jnz     loc_18000FD52
0x18000ffbb  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "g_mxsSingleThreadOle.IsLockHeld()")
0x18000ffc0  jmp     loc_18000FD52
0x18000ffc5  mov     rax, [rdi]
0x18000ffc8  mov     [r8], rax
0x18000ffcb  jmp     loc_18000FEC6
0x18000ffd0  mov     rax, [rdi]
0x18000ffd3  mov     [r8], rax
0x18000ffd6  jmp     loc_18000FC9C
0x18000ffdb  add     cs:g_cClassicSTAInits, r12d
0x18000ffe2  jnz     loc_18000FF49
0x18000ffe8  call    ?UnRegisterOleWndClass@@YAXXZ; UnRegisterOleWndClass(void)
0x18000ffed  jmp     loc_18000FF49
0x18000fff2  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x18000fff9  jz      $exit
0x18000ffff  mov     r9d, 3
0x180010005  mov     ecx, r9d; level
0x180010008  call    IsWppLevelEnabled
0x18001000d  test    al, al
0x18001000f  jz      $exit
0x180010015  mov     [rsp+58h+var_30], fHostThread; <args_0>
0x180010019  lea     rax, aCouninitCallin; "CoUninit calling CoUninit. TLS->Flags %"...
0x180010020  lea     rdx, aWcouninitializ; "wCoUninitialize"
0x180010027  mov     [rsp+58h+format], rax; format
0x18001002c  mov     r8d, 0F6Eh; line
0x180010032  lea     Tls, aOnecoreComComb_154; "onecore\\com\\combase\\class\\compobj.c"...
0x180010039  call    ??$ComTraceMessageT@I@@YAXPEBD0HW4TraceLevel@@PEBGI@Z; ComTraceMessageT<uint>(char const *,char const *,int,TraceLevel,ushort const *,uint)
0x18001003e  jmp     $exit
0x180010043  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "lockFlag & _locksHeldByThread")
0x180010048  jmp     loc_18000FDD4
0x18001004d  mov     rax, [rsi]
0x180010050  and     dword ptr [rax+14h], 0FFFFFFDFh
0x180010054  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x18001005b  jnz     short loc_180010088
0x18001005d  call    ?IsLockHeld@COleStaticMutexSem@@QEAA_NXZ; COleStaticMutexSem::IsLockHeld(void)
0x180010062  test    al, al
0x180010064  jz      $exit
0x18001006a  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "!g_mxsSingleThreadOle.IsLockHeld()")
0x18001006f  jmp     $exit
0x180010074  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "!g_mxsSingleThreadOle.IsLockHeld()")
0x180010079  jmp     loc_18000FD39
0x18001007e  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "!g_mxsSingleThreadOle.IsLockHeld()")
0x180010083  jmp     loc_18000FDFE
0x180010088  mov     r9d, 3
0x18001008e  mov     ecx, r9d; level
0x180010091  call    IsWppLevelEnabled
0x180010096  test    al, al
0x180010098  jz      short loc_18001005D
0x18001009a  mov     rax, [rsi]
0x18001009d  lea     rdx, aWcouninitializ; "wCoUninitialize"
0x1800100a4  mov     r8d, 0F81h; line
0x1800100aa  mov     ecx, [rax+14h]
0x1800100ad  lea     rax, aWaitAbortedTls; "Wait aborted. TLS->Flags %d"
0x1800100b4  mov     [rsp+58h+var_30], ecx; <args_0>
0x1800100b8  lea     Tls, aOnecoreComComb_154; "onecore\\com\\combase\\class\\compobj.c"...
0x1800100bf  mov     [rsp+58h+format], rax; format
0x1800100c4  call    ??$ComTraceMessageT@I@@YAXPEBD0HW4TraceLevel@@PEBGI@Z; ComTraceMessageT<uint>(char const *,char const *,int,TraceLevel,ushort const *,uint)
0x1800100c9  jmp     short loc_18001005D
0x1800100cb  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "!g_mxsSingleThreadOle.IsLockHeld()")
0x1800100d0  jmp     loc_18000FF9F
```
