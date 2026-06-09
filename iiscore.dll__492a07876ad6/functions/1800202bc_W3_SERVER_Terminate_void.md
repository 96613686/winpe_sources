# W3_SERVER::Terminate(void)

- ea: `0x1800202bc`
- end: `0x1800207fe`
- name: `?Terminate@W3_SERVER@@QEAAXXZ`
- size: `1346`
- prototype: `void __fastcall(W3_SERVER *__hidden this)`
- caller_count: `4`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800338ac`
- `0x1800340e0`
- `0x180034190`
- `0x1800342a0`

## callees

- `0x18000f2cc`
- `0x18001a2d8`
- `0x18001ab70`
- `0x18001c238`
- `0x18001c268`
- `0x1800201dc`
- `0x1800202bc`
- `0x180020804`
- `0x180020ca4`
- `0x180026144`
- `0x180028564`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800203e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800206fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800203e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800206fe`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180020785`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180020785`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800203ce`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800203ce`
- `CRYPTSP!CryptReleaseContext` at `0x18002061f`
- `CRYPTSP!CryptReleaseContext` at `0x18002065d`
- `CRYPTSP!CryptReleaseContext` at `0x18002061f`
- `CRYPTSP!CryptReleaseContext` at `0x18002065d`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x180020697`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x180020697`
- `iisutil!PuDbgPrint` at `0x180020500`
- `iisutil!PuDbgPrint` at `0x180020500`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x18002032c`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x1800207e2`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x18002032c`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x1800207e2`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18002039f`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18002039f`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800203b3`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800203b3`
- `iisutil!DestroyRefTraceLog` at `0x1800205a5`
- `iisutil!DestroyRefTraceLog` at `0x1800206d6`
- `iisutil!DestroyRefTraceLog` at `0x1800205a5`
- `iisutil!DestroyRefTraceLog` at `0x1800206d6`
- `iisutil!?Terminate@LANG_STRING@@QEAAJXZ` at `0x180020745`
- `iisutil!?Terminate@LANG_STRING@@QEAAJXZ` at `0x180020745`
- `iisutil!TerminateLocalRequest` at `0x180020764`
- `iisutil!TerminateLocalRequest` at `0x180020764`
- `iisutil!TerminateIISUtil` at `0x180020770`
- `iisutil!TerminateIISUtil` at `0x180020770`
- `w3dt!UlAtqTerminate` at `0x180020711`
- `w3dt!UlAtqTerminate` at `0x180020711`
- `W3TP!ThreadPoolTerminate` at `0x180020721`
- `W3TP!ThreadPoolTerminate` at `0x180020721`
- `WS2_32!__imp_WSACleanup` at `0x18002072d`
- `WS2_32!__imp_WSACleanup` at `0x18002072d`

## string_xrefs

- `0x1800204f9`: `servercommon\inetsrv\iis\iisrearc\iis70\core\w3server.cxx`

## pseudocode

```c
void __fastcall W3_SERVER::Terminate(W3_SERVER *this)
{
  W3_SERVER *v1; // rdi
  __int64 v2; // rcx
  unsigned int v3; // edx
  void *v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  _QWORD *v10; // rcx
  __int64 v11; // rcx
  int v12; // ecx
  int v13; // esi
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  int v26; // ecx
  CDirMonitor *v27; // rcx
  void *v28; // rbx
  void *v29; // rbx
  void *v30; // rcx
  LANG_STRING *v31; // rcx
  HMODULE v32; // rcx
  struct CEtwTracer *v33; // rcx
  struct _EVENT_TRACE_HEADER v34; // [rsp+30h] [rbp-30h] BYREF

  v1 = g_pW3Server;
  if ( *((_DWORD *)g_pEtwGlobalTracer + 2)
    && (*((_BYTE *)g_pEtwGlobalTracer + 40) & 2) != 0
    && *((_DWORD *)g_pEtwGlobalTracer + 11) >= 4u )
  {
    v34.Size = 48;
    *(LARGE_INTEGER *)((char *)&v34.TimeStamp + 2) = 0;
    v34.GuidPtr = (ULONGLONG)&`IISShutdownEvents::GetAreaGuid'::`2'::AreaGuid;
    *(_OWORD *)&v34.FieldTypeFlags = 0;
    v34.Class.Version = 1;
    *(union _EVENT_TRACE_HEADER::$146F82FB58FCEC23F5D30A6BD72C4E4F *)((char *)&v34.24 + 8) = 0;
    v34.UserTime = 1703936;
    v34.Class.Type = 11;
    CEtwTracer::EtwTraceEvent(g_pEtwGlobalTracer, &v34);
  }
  W3_SERVER::WaitForPreloadAction(v1);
  W3_SERVER::NotifyResumeProcess(v1, 0);
  if ( !*((_DWORD *)v1 + 137) )
  {
    W3_MAIN_CONTEXT::UninitializeCounters();
    W3_RESPONSE::UnInitializeCounters();
  }
  v2 = *((_QWORD *)v1 + 187);
  if ( v2 && *((_QWORD *)v1 + 189) )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 48LL))(v2);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v1 + 189) + 16LL))(*((_QWORD *)v1 + 189));
    *((_QWORD *)v1 + 189) = 0;
  }
  CReaderWriterLock3::WriteLock((W3_SERVER *)((char *)v1 + 44));
  *((_DWORD *)v1 + 5) = 1;
  CReaderWriterLock3::WriteUnlock((W3_SERVER *)((char *)v1 + 44));
  v4 = (void *)*((_QWORD *)v1 + 195);
  if ( v4 )
  {
    WaitForSingleObject(v4, 0xFFFFFFFF);
    CloseHandle(*((HANDLE *)v1 + 195));
    *((_QWORD *)v1 + 195) = 0;
  }
  v5 = *((_QWORD *)v1 + 187);
  if ( v5 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    *((_QWORD *)v1 + 187) = 0;
  }
  v6 = *((_QWORD *)v1 + 188);
  if ( v6 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    *((_QWORD *)v1 + 188) = 0;
  }
  v7 = *((_QWORD *)v1 + 190);
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
    *((_QWORD *)v1 + 190) = 0;
  }
  v8 = *((_QWORD *)v1 + 191);
  if ( v8 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
    *((_QWORD *)v1 + 191) = 0;
  }
  v9 = *((_QWORD *)v1 + 192);
  if ( v9 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
    *((_QWORD *)v1 + 192) = 0;
  }
  v10 = (_QWORD *)*((_QWORD *)v1 + 200);
  if ( v10 )
  {
    *v10 = &APPLICATION_PRELOAD_PROVIDER::`vftable';
    operator delete(v10);
    *((_QWORD *)v1 + 200) = 0;
  }
  v11 = *((_QWORD *)v1 + 186);
  *((_QWORD *)v1 + 185) = 0;
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\core\\w3server.cxx",
      1052,
      "W3_SERVER::Terminate",
      "Terminating W3_SERVER object\n");
  v12 = *((_DWORD *)v1 + 6);
  v13 = 0;
  if ( v12 > 9 )
  {
    v21 = v12 - 10;
    if ( v21 )
    {
      v22 = v21 - 1;
      if ( v22 )
      {
        v23 = v22 - 1;
        if ( v23 )
        {
          v24 = v23 - 1;
          if ( v24 )
          {
            v25 = v24 - 1;
            if ( v25 )
            {
              v26 = v25 - 2;
              if ( v26 )
              {
                if ( v26 != 1 )
                  goto LABEL_81;
                if ( NOTIFICATION_CONTEXT::sm_pTraceLog )
                {
                  DestroyRefTraceLog();
                  NOTIFICATION_CONTEXT::sm_pTraceLog = 0;
                }
              }
              W3_SERVER::TerminateGlobalModules(v1);
              v13 = 1;
            }
            v27 = (CDirMonitor *)*((_QWORD *)v1 + 183);
            if ( v27 )
            {
              CDirMonitor::`scalar deleting destructor'(v27, v3);
              *((_QWORD *)v1 + 183) = 0;
            }
          }
          v28 = (void *)*((_QWORD *)v1 + 69);
          if ( v28 )
          {
            W3_TRACE_EVENT_MANAGER::~W3_TRACE_EVENT_MANAGER(*((W3_TRACE_EVENT_MANAGER **)v1 + 69));
            operator delete(v28);
            *((_QWORD *)v1 + 69) = 0;
          }
        }
        operator delete(*((void **)v1 + 197));
        *((_QWORD *)v1 + 197) = 0;
      }
      if ( TOKEN_KEY::sm_hCryptProv )
      {
        CryptReleaseContext(TOKEN_KEY::sm_hCryptProv, 0);
        TOKEN_KEY::sm_hCryptProv = 0;
      }
    }
    W3_MAIN_CONTEXT::Terminate();
    goto LABEL_57;
  }
  if ( v12 == 9 )
  {
LABEL_57:
    if ( CERTIFICATE_CONTEXT::sm_pachCertContexts )
    {
      ALLOC_CACHE_HANDLER::`scalar deleting destructor'(CERTIFICATE_CONTEXT::sm_pachCertContexts, v3);
      CERTIFICATE_CONTEXT::sm_pachCertContexts = 0;
    }
    if ( CERTIFICATE_CONTEXT::sm_CryptProvider )
    {
      CryptReleaseContext(CERTIFICATE_CONTEXT::sm_CryptProvider, 0);
      CERTIFICATE_CONTEXT::sm_CryptProvider = 0;
    }
    goto LABEL_61;
  }
  v14 = v12 - 1;
  if ( !v14 )
  {
LABEL_80:
    TerminateIISUtil();
    goto LABEL_81;
  }
  v15 = v14 - 1;
  if ( !v15 )
  {
LABEL_79:
    TerminateLocalRequest();
    goto LABEL_80;
  }
  v16 = v15 - 1;
  if ( !v16 || (v17 = v16 - 1) == 0 )
  {
LABEL_77:
    v31 = (LANG_STRING *)*((_QWORD *)v1 + 194);
    if ( v31 )
    {
      LANG_STRING::Terminate(v31);
      operator delete(*((void **)v1 + 194));
      *((_QWORD *)v1 + 194) = 0;
    }
    goto LABEL_79;
  }
  v18 = v17 - 1;
  if ( !v18 )
  {
LABEL_76:
    WSACleanup();
    goto LABEL_77;
  }
  v19 = v18 - 1;
  if ( !v19 )
  {
LABEL_70:
    if ( *((_DWORD *)v1 + 392) )
    {
      v30 = (void *)*((_QWORD *)v1 + 211);
      if ( v30 )
      {
        CloseHandle(v30);
        *((_QWORD *)v1 + 211) = 0;
      }
      UlAtqTerminate();
    }
    if ( !v13 )
      ThreadPoolTerminate();
    goto LABEL_76;
  }
  v20 = v19 - 1;
  if ( !v20 )
  {
LABEL_64:
    v29 = W3_CONNECTION::sm_pConnectionTable;
    if ( W3_CONNECTION::sm_pConnectionTable )
    {
      CLKRHashTable::~CLKRHashTable((CLKRHashTable *)W3_CONNECTION::sm_pConnectionTable);
      operator delete(v29);
      W3_CONNECTION::sm_pConnectionTable = 0;
    }
    if ( W3_CONNECTION::sm_pachW3Connections )
      ALLOC_CACHE_HANDLER::`scalar deleting destructor'(W3_CONNECTION::sm_pachW3Connections, v3);
    W3_CONNECTION::sm_pachW3Connections = 0;
    if ( W3_CONNECTION::sm_pTraceLog )
    {
      DestroyRefTraceLog();
      W3_CONNECTION::sm_pTraceLog = 0;
    }
    goto LABEL_70;
  }
  if ( v20 == 1 )
  {
LABEL_61:
    if ( W3_FILE_INFO::sm_pachW3FileInfo )
      ALLOC_CACHE_HANDLER::`scalar deleting destructor'(W3_FILE_INFO::sm_pachW3FileInfo, v3);
    W3_FILE_INFO::sm_pachW3FileInfo = 0;
    goto LABEL_64;
  }
LABEL_81:
  v32 = (HMODULE)*((_QWORD *)v1 + 4);
  if ( v32 )
  {
    FreeLibrary(v32);
    *((_QWORD *)v1 + 4) = 0;
  }
  v33 = g_pEtwGlobalTracer;
  *((_DWORD *)v1 + 6) = 0;
  if ( *((_DWORD *)v33 + 2) && (*((_BYTE *)v33 + 40) & 2) != 0 && *((_DWORD *)v33 + 11) >= 4u )
  {
    *(LARGE_INTEGER *)((char *)&v34.TimeStamp + 2) = 0;
    v34.GuidPtr = (ULONGLONG)&`IISShutdownEvents::GetAreaGuid'::`2'::AreaGuid;
    *(_OWORD *)&v34.FieldTypeFlags = 0;
    v34.Size = 48;
    *(union _EVENT_TRACE_HEADER::$146F82FB58FCEC23F5D30A6BD72C4E4F *)((char *)&v34.24 + 8) = 0;
    v34.UserTime = 1703936;
    v34.Class.Version = 1;
    v34.Class.Type = 12;
    CEtwTracer::EtwTraceEvent(v33, &v34);
  }
}

```

## disassembly

```asm
0x1800202bc  push    rbp
0x1800202be  push    rbx
0x1800202bf  push    rsi
0x1800202c0  push    rdi
0x1800202c1  push    r13
0x1800202c3  push    r14
0x1800202c5  push    r15
0x1800202c7  mov     rbp, rsp
0x1800202ca  sub     rsp, 60h
0x1800202ce  mov     rcx, cs:?g_pEtwGlobalTracer@@3PEAVCEtwTracer@@EA; CEtwTracer * g_pEtwGlobalTracer
0x1800202d5  lea     r13, ?AreaGuid@?1??GetAreaGuid@IISShutdownEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISShutdownEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x1800202dc  mov     rdi, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x1800202e3  mov     edx, 30h ; '0'
0x1800202e8  xor     r14d, r14d
0x1800202eb  lea     r15d, [rdx-2Fh]
0x1800202ef  cmp     [rcx+8], r14d
0x1800202f3  jz      short loc_180020338
0x1800202f5  test    byte ptr [rcx+28h], 2
0x1800202f9  jz      short loc_180020338
0x1800202fb  cmp     dword ptr [rcx+2Ch], 4
0x1800202ff  jb      short loc_180020338
0x180020301  xorps   xmm0, xmm0
0x180020304  mov     [rbp+var_30], dx
0x180020308  movups  [rbp+var_1E], xmm0
0x18002030c  lea     rdx, [rbp+var_30]
0x180020310  mov     qword ptr [rbp+var_1E+6], r13
0x180020314  movups  [rbp+var_2E], xmm0
0x180020318  mov     word ptr [rbp+var_2E+4], r15w
0x18002031d  movups  [rbp+var_1E+0Eh], xmm0
0x180020321  mov     [rbp+var_4], 1A0000h
0x180020328  mov     byte ptr [rbp+var_2E+2], 0Bh
0x18002032c  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z; CEtwTracer::EtwTraceEvent(_EVENT_TRACE_HEADER *)
0x180020333  nop     dword ptr [rax+rax+00h]
0x180020338  mov     rcx, rdi; this
0x18002033b  call    ?WaitForPreloadAction@W3_SERVER@@AEBAXXZ; W3_SERVER::WaitForPreloadAction(void)
0x180020340  xor     edx, edx; int
0x180020342  mov     rcx, rdi; this
0x180020345  call    ?NotifyResumeProcess@W3_SERVER@@QEAAXH@Z; W3_SERVER::NotifyResumeProcess(int)
0x18002034a  cmp     [rdi+224h], r14d
0x180020351  jnz     short loc_18002035D
0x180020353  call    ?UninitializeCounters@W3_MAIN_CONTEXT@@SAXXZ; W3_MAIN_CONTEXT::UninitializeCounters(void)
0x180020358  call    ?UnInitializeCounters@W3_RESPONSE@@SAXXZ; W3_RESPONSE::UnInitializeCounters(void)
0x18002035d  mov     rcx, [rdi+5D8h]
0x180020364  test    rcx, rcx
0x180020367  jz      short loc_18002039B
0x180020369  mov     rdx, [rdi+5E8h]
0x180020370  test    rdx, rdx
0x180020373  jz      short loc_18002039B
0x180020375  mov     rax, [rcx]
0x180020378  mov     rax, [rax+30h]
0x18002037c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020381  mov     rcx, [rdi+5E8h]
0x180020388  mov     rax, [rcx]
0x18002038b  mov     rax, [rax+10h]
0x18002038f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020394  mov     [rdi+5E8h], r14
0x18002039b  lea     rcx, [rdi+2Ch]
0x18002039f  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x1800203a6  nop     dword ptr [rax+rax+00h]
0x1800203ab  lea     rcx, [rdi+2Ch]
0x1800203af  mov     [rdi+14h], r15d
0x1800203b3  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x1800203ba  nop     dword ptr [rax+rax+00h]
0x1800203bf  mov     rcx, [rdi+618h]; hHandle
0x1800203c6  test    rcx, rcx
0x1800203c9  jz      short loc_1800203F4
0x1800203cb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800203ce  call    cs:__imp_WaitForSingleObject
0x1800203d5  nop     dword ptr [rax+rax+00h]
0x1800203da  mov     rcx, [rdi+618h]; hObject
0x1800203e1  call    cs:__imp_CloseHandle
0x1800203e8  nop     dword ptr [rax+rax+00h]
0x1800203ed  mov     [rdi+618h], r14
0x1800203f4  mov     rcx, [rdi+5D8h]
0x1800203fb  test    rcx, rcx
0x1800203fe  jz      short loc_180020413
0x180020400  mov     rax, [rcx]
0x180020403  mov     rax, [rax+10h]
0x180020407  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002040c  mov     [rdi+5D8h], r14
0x180020413  mov     rcx, [rdi+5E0h]
0x18002041a  test    rcx, rcx
0x18002041d  jz      short loc_180020432
0x18002041f  mov     rax, [rcx]
0x180020422  mov     rax, [rax+10h]
0x180020426  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002042b  mov     [rdi+5E0h], r14
0x180020432  mov     rcx, [rdi+5F0h]
0x180020439  test    rcx, rcx
0x18002043c  jz      short loc_180020451
0x18002043e  mov     rax, [rcx]
0x180020441  mov     rax, [rax+8]
0x180020445  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002044a  mov     [rdi+5F0h], r14
0x180020451  mov     rcx, [rdi+5F8h]
0x180020458  test    rcx, rcx
0x18002045b  jz      short loc_180020470
0x18002045d  mov     rax, [rcx]
0x180020460  mov     rax, [rax+8]
0x180020464  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020469  mov     [rdi+5F8h], r14
0x180020470  mov     rcx, [rdi+600h]
0x180020477  test    rcx, rcx
0x18002047a  jz      short loc_18002048F
0x18002047c  mov     rax, [rcx]
0x18002047f  mov     rax, [rax+8]
0x180020483  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020488  mov     [rdi+600h], r14
0x18002048f  mov     rcx, [rdi+640h]; Block
0x180020496  test    rcx, rcx
0x180020499  jz      short loc_1800204B1
0x18002049b  lea     rax, ??_7APPLICATION_PRELOAD_PROVIDER@@6B@; const APPLICATION_PRELOAD_PROVIDER::`vftable'
0x1800204a2  mov     [rcx], rax
0x1800204a5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800204aa  mov     [rdi+640h], r14
0x1800204b1  mov     rcx, [rdi+5D0h]
0x1800204b8  mov     [rdi+5C8h], r14
0x1800204bf  test    rcx, rcx
0x1800204c2  jz      short loc_1800204D0
0x1800204c4  mov     rax, [rcx]
0x1800204c7  mov     rax, [rax+8]
0x1800204cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800204d0  test    byte ptr cs:g_dwDebugFlags, 3
0x1800204d7  jz      short loc_18002050C
0x1800204d9  mov     rcx, cs:g_pDebug
0x1800204e0  lea     rax, aTerminatingW3S; "Terminating W3_SERVER object\n"
0x1800204e7  lea     r9, aW3ServerTermin; "W3_SERVER::Terminate"
0x1800204ee  mov     [rsp+60h+var_40], rax
0x1800204f3  mov     r8d, 41Ch
0x1800204f9  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180020500  call    cs:__imp_PuDbgPrint
0x180020507  nop     dword ptr [rax+rax+00h]
0x18002050c  mov     ecx, [rdi+18h]
0x18002050f  mov     esi, r14d
0x180020512  cmp     ecx, 9
0x180020515  jg      short loc_18002056A
0x180020517  jz      loc_180020637
0x18002051d  sub     ecx, r15d
0x180020520  jz      loc_180020770
0x180020526  sub     ecx, r15d
0x180020529  jz      loc_180020764
0x18002052f  sub     ecx, r15d
0x180020532  jz      loc_180020739
0x180020538  sub     ecx, r15d
0x18002053b  jz      loc_180020739
0x180020541  sub     ecx, r15d
0x180020544  jz      loc_18002072D
0x18002054a  sub     ecx, r15d
0x18002054d  jz      loc_1800206E9
0x180020553  sub     ecx, r15d
0x180020556  jz      loc_180020688
0x18002055c  cmp     ecx, r15d
0x18002055f  jz      loc_180020670
0x180020565  jmp     loc_18002077C
0x18002056a  sub     ecx, 0Ah
0x18002056d  jz      loc_180020632
0x180020573  sub     ecx, r15d
0x180020576  jz      loc_180020611
0x18002057c  sub     ecx, r15d
0x18002057f  jz      short loc_1800205FE
0x180020581  sub     ecx, r15d
0x180020584  jz      short loc_1800205DB
0x180020586  sub     ecx, r15d
0x180020589  jz      short loc_1800205C3
0x18002058b  sub     ecx, 2
0x18002058e  jz      short loc_1800205B8
0x180020590  cmp     ecx, r15d
0x180020593  jnz     loc_18002077C
0x180020599  mov     rcx, cs:?sm_pTraceLog@NOTIFICATION_CONTEXT@@2PEAU_TRACE_LOG@@EA; _TRACE_LOG * NOTIFICATION_CONTEXT::sm_pTraceLog
0x1800205a0  test    rcx, rcx
0x1800205a3  jz      short loc_1800205B8
0x1800205a5  call    cs:__imp_DestroyRefTraceLog
0x1800205ac  nop     dword ptr [rax+rax+00h]
0x1800205b1  mov     cs:?sm_pTraceLog@NOTIFICATION_CONTEXT@@2PEAU_TRACE_LOG@@EA, r14; _TRACE_LOG * NOTIFICATION_CONTEXT::sm_pTraceLog
0x1800205b8  mov     rcx, rdi; this
0x1800205bb  call    ?TerminateGlobalModules@W3_SERVER@@QEAAXXZ; W3_SERVER::TerminateGlobalModules(void)
0x1800205c0  mov     esi, r15d
0x1800205c3  mov     rcx, [rdi+5B8h]; this
0x1800205ca  test    rcx, rcx
0x1800205cd  jz      short loc_1800205DB
0x1800205cf  call    ??_GCDirMonitor@@QEAAPEAXI@Z; CDirMonitor::`scalar deleting destructor'(uint)
0x1800205d4  mov     [rdi+5B8h], r14
0x1800205db  mov     rbx, [rdi+228h]
0x1800205e2  test    rbx, rbx
0x1800205e5  jz      short loc_1800205FE
0x1800205e7  mov     rcx, rbx; this
0x1800205ea  call    ??1W3_TRACE_EVENT_MANAGER@@QEAA@XZ; W3_TRACE_EVENT_MANAGER::~W3_TRACE_EVENT_MANAGER(void)
0x1800205ef  mov     rcx, rbx; Block
0x1800205f2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800205f7  mov     [rdi+228h], r14
0x1800205fe  mov     rcx, [rdi+628h]; Block
0x180020605  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002060a  mov     [rdi+628h], r14
0x180020611  mov     rcx, cs:?sm_hCryptProv@TOKEN_KEY@@0_KA; hProv
0x180020618  test    rcx, rcx
0x18002061b  jz      short loc_180020632
0x18002061d  xor     edx, edx; dwFlags
0x18002061f  call    cs:__imp_CryptReleaseContext
0x180020626  nop     dword ptr [rax+rax+00h]
0x18002062b  mov     cs:?sm_hCryptProv@TOKEN_KEY@@0_KA, r14; unsigned __int64 TOKEN_KEY::sm_hCryptProv
0x180020632  call    ?Terminate@W3_MAIN_CONTEXT@@SAXXZ; W3_MAIN_CONTEXT::Terminate(void)
0x180020637  mov     rcx, cs:?sm_pachCertContexts@CERTIFICATE_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA; this
0x18002063e  test    rcx, rcx
0x180020641  jz      short loc_18002064F
0x180020643  call    ??_GALLOC_CACHE_HANDLER@@QEAAPEAXI@Z; ALLOC_CACHE_HANDLER::`scalar deleting destructor'(uint)
0x180020648  mov     cs:?sm_pachCertContexts@CERTIFICATE_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA, r14; ALLOC_CACHE_HANDLER * CERTIFICATE_CONTEXT::sm_pachCertContexts
0x18002064f  mov     rcx, cs:?sm_CryptProvider@CERTIFICATE_CONTEXT@@0_KA; hProv
0x180020656  test    rcx, rcx
0x180020659  jz      short loc_180020670
0x18002065b  xor     edx, edx; dwFlags
0x18002065d  call    cs:__imp_CryptReleaseContext
0x180020664  nop     dword ptr [rax+rax+00h]
0x180020669  mov     cs:?sm_CryptProvider@CERTIFICATE_CONTEXT@@0_KA, r14; unsigned __int64 CERTIFICATE_CONTEXT::sm_CryptProvider
0x180020670  mov     rcx, cs:?sm_pachW3FileInfo@W3_FILE_INFO@@0PEAVALLOC_CACHE_HANDLER@@EA; this
0x180020677  test    rcx, rcx
0x18002067a  jz      short loc_180020681
0x18002067c  call    ??_GALLOC_CACHE_HANDLER@@QEAAPEAXI@Z; ALLOC_CACHE_HANDLER::`scalar deleting destructor'(uint)
0x180020681  mov     cs:?sm_pachW3FileInfo@W3_FILE_INFO@@0PEAVALLOC_CACHE_HANDLER@@EA, r14; ALLOC_CACHE_HANDLER * W3_FILE_INFO::sm_pachW3FileInfo
0x180020688  mov     rbx, cs:?sm_pConnectionTable@W3_CONNECTION@@0PEAVW3_CONNECTION_HASH@@EA; W3_CONNECTION_HASH * W3_CONNECTION::sm_pConnectionTable
0x18002068f  test    rbx, rbx
0x180020692  jz      short loc_1800206B2
0x180020694  mov     rcx, rbx
0x180020697  call    cs:__imp_??1CLKRHashTable@@QEAA@XZ; CLKRHashTable::~CLKRHashTable(void)
0x18002069e  nop     dword ptr [rax+rax+00h]
0x1800206a3  mov     rcx, rbx; Block
0x1800206a6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800206ab  mov     cs:?sm_pConnectionTable@W3_CONNECTION@@0PEAVW3_CONNECTION_HASH@@EA, r14; W3_CONNECTION_HASH * W3_CONNECTION::sm_pConnectionTable
0x1800206b2  mov     rcx, cs:?sm_pachW3Connections@W3_CONNECTION@@0PEAVALLOC_CACHE_HANDLER@@EA; this
0x1800206b9  test    rcx, rcx
0x1800206bc  jz      short loc_1800206C3
0x1800206be  call    ??_GALLOC_CACHE_HANDLER@@QEAAPEAXI@Z; ALLOC_CACHE_HANDLER::`scalar deleting destructor'(uint)
0x1800206c3  mov     rcx, cs:?sm_pTraceLog@W3_CONNECTION@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * W3_CONNECTION::sm_pTraceLog
0x1800206ca  mov     cs:?sm_pachW3Connections@W3_CONNECTION@@0PEAVALLOC_CACHE_HANDLER@@EA, r14; ALLOC_CACHE_HANDLER * W3_CONNECTION::sm_pachW3Connections
0x1800206d1  test    rcx, rcx
0x1800206d4  jz      short loc_1800206E9
0x1800206d6  call    cs:__imp_DestroyRefTraceLog
0x1800206dd  nop     dword ptr [rax+rax+00h]
0x1800206e2  mov     cs:?sm_pTraceLog@W3_CONNECTION@@0PEAU_TRACE_LOG@@EA, r14; _TRACE_LOG * W3_CONNECTION::sm_pTraceLog
0x1800206e9  cmp     [rdi+620h], r14d
0x1800206f0  jz      short loc_18002071D
0x1800206f2  mov     rcx, [rdi+698h]; hObject
0x1800206f9  test    rcx, rcx
0x1800206fc  jz      short loc_180020711
0x1800206fe  call    cs:__imp_CloseHandle
0x180020705  nop     dword ptr [rax+rax+00h]
0x18002070a  mov     [rdi+698h], r14
0x180020711  call    cs:__imp_?UlAtqTerminate@@YAXXZ; UlAtqTerminate(void)
0x180020718  nop     dword ptr [rax+rax+00h]
0x18002071d  test    esi, esi
0x18002071f  jnz     short loc_18002072D
0x180020721  call    cs:__imp_?ThreadPoolTerminate@@YAJXZ; ThreadPoolTerminate(void)
0x180020728  nop     dword ptr [rax+rax+00h]
0x18002072d  call    cs:__imp_WSACleanup
0x180020734  nop     dword ptr [rax+rax+00h]
0x180020739  mov     rcx, [rdi+610h]
0x180020740  test    rcx, rcx
0x180020743  jz      short loc_180020764
0x180020745  call    cs:__imp_?Terminate@LANG_STRING@@QEAAJXZ; LANG_STRING::Terminate(void)
0x18002074c  nop     dword ptr [rax+rax+00h]
0x180020751  mov     rcx, [rdi+610h]; Block
0x180020758  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002075d  mov     [rdi+610h], r14
0x180020764  call    cs:__imp_?TerminateLocalRequest@@YAJXZ; TerminateLocalRequest(void)
0x18002076b  nop     dword ptr [rax+rax+00h]
0x180020770  call    cs:__imp_TerminateIISUtil
0x180020777  nop     dword ptr [rax+rax+00h]
0x18002077c  mov     rcx, [rdi+20h]; hLibModule
0x180020780  test    rcx, rcx
0x180020783  jz      short loc_180020795
0x180020785  call    cs:__imp_FreeLibrary
0x18002078c  nop     dword ptr [rax+rax+00h]
0x180020791  mov     [rdi+20h], r14
0x180020795  mov     rcx, cs:?g_pEtwGlobalTracer@@3PEAVCEtwTracer@@EA; CEtwTracer * g_pEtwGlobalTracer
0x18002079c  mov     [rdi+18h], r14d
0x1800207a0  cmp     [rcx+8], r14d
0x1800207a4  jz      short loc_1800207EE
0x1800207a6  test    byte ptr [rcx+28h], 2
0x1800207aa  jz      short loc_1800207EE
0x1800207ac  cmp     dword ptr [rcx+2Ch], 4
0x1800207b0  jb      short loc_1800207EE
0x1800207b2  xorps   xmm0, xmm0
0x1800207b5  lea     rdx, [rbp+var_30]
0x1800207b9  movups  [rbp+var_1E], xmm0
0x1800207bd  mov     eax, 30h ; '0'
0x1800207c2  mov     qword ptr [rbp+var_1E+6], r13
0x1800207c6  movups  [rbp+var_2E], xmm0
0x1800207ca  mov     [rbp+var_30], ax
0x1800207ce  movups  [rbp+var_1E+0Eh], xmm0
0x1800207d2  mov     [rbp+var_4], 1A0000h
0x1800207d9  mov     word ptr [rbp+var_2E+4], r15w
0x1800207de  mov     byte ptr [rbp+var_2E+2], 0Ch
0x1800207e2  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z; CEtwTracer::EtwTraceEvent(_EVENT_TRACE_HEADER *)
0x1800207e9  nop     dword ptr [rax+rax+00h]
0x1800207ee  add     rsp, 60h
0x1800207f2  pop     r15
0x1800207f4  pop     r14
0x1800207f6  pop     r13
0x1800207f8  pop     rdi
0x1800207f9  pop     rsi
0x1800207fa  pop     rbx
  ... truncated ...
```
