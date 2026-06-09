# W3_SERVER::Terminate(void)

- ea: `0x18001e7f0`
- end: `0x18001ecb9`
- name: `?Terminate@W3_SERVER@@QEAAXXZ`
- size: `1225`
- prototype: `void __fastcall(W3_SERVER *__hidden this)`
- caller_count: `4`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180030bac`
- `0x180031300`
- `0x1800313a0`
- `0x1800314a0`

## callees

- `0x18000e690`
- `0x180018d8c`
- `0x180019598`
- `0x18001ab40`
- `0x18001ab68`
- `0x18001e718`
- `0x18001e7f0`
- `0x18001ecc0`
- `0x18001f130`
- `0x18002429c`
- `0x18002650c`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e8fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ebf0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e8fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ebf0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001ec4d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001ec4d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001e8f0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001e8f0`
- `CRYPTSP!CryptReleaseContext` at `0x18001eb29`
- `CRYPTSP!CryptReleaseContext` at `0x18001eb61`
- `CRYPTSP!CryptReleaseContext` at `0x18001eb29`
- `CRYPTSP!CryptReleaseContext` at `0x18001eb61`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x18001eb95`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x18001eb95`
- `iisutil!PuDbgPrint` at `0x18001ea16`
- `iisutil!PuDbgPrint` at `0x18001ea16`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x18001e860`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x18001eca4`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x18001e860`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x18001eca4`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001e8cd`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001e8cd`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001e8db`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001e8db`
- `iisutil!DestroyRefTraceLog` at `0x18001eab5`
- `iisutil!DestroyRefTraceLog` at `0x18001ebce`
- `iisutil!DestroyRefTraceLog` at `0x18001eab5`
- `iisutil!DestroyRefTraceLog` at `0x18001ebce`
- `iisutil!?Terminate@LANG_STRING@@QEAAJXZ` at `0x18001ec1f`
- `iisutil!?Terminate@LANG_STRING@@QEAAJXZ` at `0x18001ec1f`
- `iisutil!TerminateLocalRequest` at `0x18001ec38`
- `iisutil!TerminateLocalRequest` at `0x18001ec38`
- `iisutil!TerminateIISUtil` at `0x18001ec3e`
- `iisutil!TerminateIISUtil` at `0x18001ec3e`
- `w3dt!UlAtqTerminate` at `0x18001ebfd`
- `w3dt!UlAtqTerminate` at `0x18001ebfd`
- `W3TP!ThreadPoolTerminate` at `0x18001ec07`
- `W3TP!ThreadPoolTerminate` at `0x18001ec07`
- `WS2_32!__imp_WSACleanup` at `0x18001ec0d`
- `WS2_32!__imp_WSACleanup` at `0x18001ec0d`

## string_xrefs

- `0x18001ea0f`: `servercommon\inetsrv\iis\iisrearc\iis70\core\w3server.cxx`

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
0x18001e7f0  push    rbp
0x18001e7f2  push    rbx
0x18001e7f3  push    rsi
0x18001e7f4  push    rdi
0x18001e7f5  push    r13
0x18001e7f7  push    r14
0x18001e7f9  push    r15
0x18001e7fb  mov     rbp, rsp
0x18001e7fe  sub     rsp, 60h
0x18001e802  mov     rcx, cs:?g_pEtwGlobalTracer@@3PEAVCEtwTracer@@EA; CEtwTracer * g_pEtwGlobalTracer
0x18001e809  lea     r13, ?AreaGuid@?1??GetAreaGuid@IISShutdownEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISShutdownEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18001e810  mov     rdi, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x18001e817  mov     edx, 30h ; '0'
0x18001e81c  xor     r14d, r14d
0x18001e81f  lea     r15d, [rdx-2Fh]
0x18001e823  cmp     [rcx+8], r14d
0x18001e827  jz      short loc_18001E866
0x18001e829  test    byte ptr [rcx+28h], 2
0x18001e82d  jz      short loc_18001E866
0x18001e82f  cmp     dword ptr [rcx+2Ch], 4
0x18001e833  jb      short loc_18001E866
0x18001e835  xorps   xmm0, xmm0
0x18001e838  mov     [rbp+var_30], dx
0x18001e83c  movups  [rbp+var_1E], xmm0
0x18001e840  lea     rdx, [rbp+var_30]
0x18001e844  mov     qword ptr [rbp+var_1E+6], r13
0x18001e848  movups  [rbp+var_2E], xmm0
0x18001e84c  mov     word ptr [rbp+var_2E+4], r15w
0x18001e851  movups  [rbp+var_1E+0Eh], xmm0
0x18001e855  mov     [rbp+var_4], 1A0000h
0x18001e85c  mov     byte ptr [rbp+var_2E+2], 0Bh
0x18001e860  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z; CEtwTracer::EtwTraceEvent(_EVENT_TRACE_HEADER *)
0x18001e866  mov     rcx, rdi; this
0x18001e869  call    ?WaitForPreloadAction@W3_SERVER@@AEBAXXZ; W3_SERVER::WaitForPreloadAction(void)
0x18001e86e  xor     edx, edx; int
0x18001e870  mov     rcx, rdi; this
0x18001e873  call    ?NotifyResumeProcess@W3_SERVER@@QEAAXH@Z; W3_SERVER::NotifyResumeProcess(int)
0x18001e878  cmp     [rdi+224h], r14d
0x18001e87f  jnz     short loc_18001E88B
0x18001e881  call    ?UninitializeCounters@W3_MAIN_CONTEXT@@SAXXZ; W3_MAIN_CONTEXT::UninitializeCounters(void)
0x18001e886  call    ?UnInitializeCounters@W3_RESPONSE@@SAXXZ; W3_RESPONSE::UnInitializeCounters(void)
0x18001e88b  mov     rcx, [rdi+5D8h]
0x18001e892  test    rcx, rcx
0x18001e895  jz      short loc_18001E8C9
0x18001e897  mov     rdx, [rdi+5E8h]
0x18001e89e  test    rdx, rdx
0x18001e8a1  jz      short loc_18001E8C9
0x18001e8a3  mov     rax, [rcx]
0x18001e8a6  mov     rax, [rax+30h]
0x18001e8aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e8af  mov     rcx, [rdi+5E8h]
0x18001e8b6  mov     rax, [rcx]
0x18001e8b9  mov     rax, [rax+10h]
0x18001e8bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e8c2  mov     [rdi+5E8h], r14
0x18001e8c9  lea     rcx, [rdi+2Ch]
0x18001e8cd  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18001e8d3  lea     rcx, [rdi+2Ch]
0x18001e8d7  mov     [rdi+14h], r15d
0x18001e8db  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18001e8e1  mov     rcx, [rdi+618h]; hHandle
0x18001e8e8  test    rcx, rcx
0x18001e8eb  jz      short loc_18001E90A
0x18001e8ed  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001e8f0  call    cs:__imp_WaitForSingleObject
0x18001e8f6  mov     rcx, [rdi+618h]; hObject
0x18001e8fd  call    cs:__imp_CloseHandle
0x18001e903  mov     [rdi+618h], r14
0x18001e90a  mov     rcx, [rdi+5D8h]
0x18001e911  test    rcx, rcx
0x18001e914  jz      short loc_18001E929
0x18001e916  mov     rax, [rcx]
0x18001e919  mov     rax, [rax+10h]
0x18001e91d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e922  mov     [rdi+5D8h], r14
0x18001e929  mov     rcx, [rdi+5E0h]
0x18001e930  test    rcx, rcx
0x18001e933  jz      short loc_18001E948
0x18001e935  mov     rax, [rcx]
0x18001e938  mov     rax, [rax+10h]
0x18001e93c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e941  mov     [rdi+5E0h], r14
0x18001e948  mov     rcx, [rdi+5F0h]
0x18001e94f  test    rcx, rcx
0x18001e952  jz      short loc_18001E967
0x18001e954  mov     rax, [rcx]
0x18001e957  mov     rax, [rax+8]
0x18001e95b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e960  mov     [rdi+5F0h], r14
0x18001e967  mov     rcx, [rdi+5F8h]
0x18001e96e  test    rcx, rcx
0x18001e971  jz      short loc_18001E986
0x18001e973  mov     rax, [rcx]
0x18001e976  mov     rax, [rax+8]
0x18001e97a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e97f  mov     [rdi+5F8h], r14
0x18001e986  mov     rcx, [rdi+600h]
0x18001e98d  test    rcx, rcx
0x18001e990  jz      short loc_18001E9A5
0x18001e992  mov     rax, [rcx]
0x18001e995  mov     rax, [rax+8]
0x18001e999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e99e  mov     [rdi+600h], r14
0x18001e9a5  mov     rcx, [rdi+640h]; Block
0x18001e9ac  test    rcx, rcx
0x18001e9af  jz      short loc_18001E9C7
0x18001e9b1  lea     rax, ??_7APPLICATION_PRELOAD_PROVIDER@@6B@; const APPLICATION_PRELOAD_PROVIDER::`vftable'
0x18001e9b8  mov     [rcx], rax
0x18001e9bb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001e9c0  mov     [rdi+640h], r14
0x18001e9c7  mov     rcx, [rdi+5D0h]
0x18001e9ce  mov     [rdi+5C8h], r14
0x18001e9d5  test    rcx, rcx
0x18001e9d8  jz      short loc_18001E9E6
0x18001e9da  mov     rax, [rcx]
0x18001e9dd  mov     rax, [rax+8]
0x18001e9e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e9e6  test    byte ptr cs:g_dwDebugFlags, 3
0x18001e9ed  jz      short loc_18001EA1C
0x18001e9ef  mov     rcx, cs:g_pDebug
0x18001e9f6  lea     rax, aTerminatingW3S; "Terminating W3_SERVER object\n"
0x18001e9fd  lea     r9, aW3ServerTermin; "W3_SERVER::Terminate"
0x18001ea04  mov     [rsp+60h+var_40], rax
0x18001ea09  mov     r8d, 41Ch
0x18001ea0f  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18001ea16  call    cs:__imp_PuDbgPrint
0x18001ea1c  mov     ecx, [rdi+18h]
0x18001ea1f  mov     esi, r14d
0x18001ea22  cmp     ecx, 9
0x18001ea25  jg      short loc_18001EA7A
0x18001ea27  jz      loc_18001EB3B
0x18001ea2d  sub     ecx, r15d
0x18001ea30  jz      loc_18001EC3E
0x18001ea36  sub     ecx, r15d
0x18001ea39  jz      loc_18001EC38
0x18001ea3f  sub     ecx, r15d
0x18001ea42  jz      loc_18001EC13
0x18001ea48  sub     ecx, r15d
0x18001ea4b  jz      loc_18001EC13
0x18001ea51  sub     ecx, r15d
0x18001ea54  jz      loc_18001EC0D
0x18001ea5a  sub     ecx, r15d
0x18001ea5d  jz      loc_18001EBDB
0x18001ea63  sub     ecx, r15d
0x18001ea66  jz      loc_18001EB86
0x18001ea6c  cmp     ecx, r15d
0x18001ea6f  jz      loc_18001EB6E
0x18001ea75  jmp     loc_18001EC44
0x18001ea7a  sub     ecx, 0Ah
0x18001ea7d  jz      loc_18001EB36
0x18001ea83  sub     ecx, r15d
0x18001ea86  jz      loc_18001EB1B
0x18001ea8c  sub     ecx, r15d
0x18001ea8f  jz      short loc_18001EB08
0x18001ea91  sub     ecx, r15d
0x18001ea94  jz      short loc_18001EAE5
0x18001ea96  sub     ecx, r15d
0x18001ea99  jz      short loc_18001EACD
0x18001ea9b  sub     ecx, 2
0x18001ea9e  jz      short loc_18001EAC2
0x18001eaa0  cmp     ecx, r15d
0x18001eaa3  jnz     loc_18001EC44
0x18001eaa9  mov     rcx, cs:?sm_pTraceLog@NOTIFICATION_CONTEXT@@2PEAU_TRACE_LOG@@EA; _TRACE_LOG * NOTIFICATION_CONTEXT::sm_pTraceLog
0x18001eab0  test    rcx, rcx
0x18001eab3  jz      short loc_18001EAC2
0x18001eab5  call    cs:__imp_DestroyRefTraceLog
0x18001eabb  mov     cs:?sm_pTraceLog@NOTIFICATION_CONTEXT@@2PEAU_TRACE_LOG@@EA, r14; _TRACE_LOG * NOTIFICATION_CONTEXT::sm_pTraceLog
0x18001eac2  mov     rcx, rdi; this
0x18001eac5  call    ?TerminateGlobalModules@W3_SERVER@@QEAAXXZ; W3_SERVER::TerminateGlobalModules(void)
0x18001eaca  mov     esi, r15d
0x18001eacd  mov     rcx, [rdi+5B8h]; this
0x18001ead4  test    rcx, rcx
0x18001ead7  jz      short loc_18001EAE5
0x18001ead9  call    ??_GCDirMonitor@@QEAAPEAXI@Z; CDirMonitor::`scalar deleting destructor'(uint)
0x18001eade  mov     [rdi+5B8h], r14
0x18001eae5  mov     rbx, [rdi+228h]
0x18001eaec  test    rbx, rbx
0x18001eaef  jz      short loc_18001EB08
0x18001eaf1  mov     rcx, rbx; this
0x18001eaf4  call    ??1W3_TRACE_EVENT_MANAGER@@QEAA@XZ; W3_TRACE_EVENT_MANAGER::~W3_TRACE_EVENT_MANAGER(void)
0x18001eaf9  mov     rcx, rbx; Block
0x18001eafc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001eb01  mov     [rdi+228h], r14
0x18001eb08  mov     rcx, [rdi+628h]; Block
0x18001eb0f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001eb14  mov     [rdi+628h], r14
0x18001eb1b  mov     rcx, cs:?sm_hCryptProv@TOKEN_KEY@@0_KA; hProv
0x18001eb22  test    rcx, rcx
0x18001eb25  jz      short loc_18001EB36
0x18001eb27  xor     edx, edx; dwFlags
0x18001eb29  call    cs:__imp_CryptReleaseContext
0x18001eb2f  mov     cs:?sm_hCryptProv@TOKEN_KEY@@0_KA, r14; unsigned __int64 TOKEN_KEY::sm_hCryptProv
0x18001eb36  call    ?Terminate@W3_MAIN_CONTEXT@@SAXXZ; W3_MAIN_CONTEXT::Terminate(void)
0x18001eb3b  mov     rcx, cs:?sm_pachCertContexts@CERTIFICATE_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA; this
0x18001eb42  test    rcx, rcx
0x18001eb45  jz      short loc_18001EB53
0x18001eb47  call    ??_GALLOC_CACHE_HANDLER@@QEAAPEAXI@Z; ALLOC_CACHE_HANDLER::`scalar deleting destructor'(uint)
0x18001eb4c  mov     cs:?sm_pachCertContexts@CERTIFICATE_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA, r14; ALLOC_CACHE_HANDLER * CERTIFICATE_CONTEXT::sm_pachCertContexts
0x18001eb53  mov     rcx, cs:?sm_CryptProvider@CERTIFICATE_CONTEXT@@0_KA; hProv
0x18001eb5a  test    rcx, rcx
0x18001eb5d  jz      short loc_18001EB6E
0x18001eb5f  xor     edx, edx; dwFlags
0x18001eb61  call    cs:__imp_CryptReleaseContext
0x18001eb67  mov     cs:?sm_CryptProvider@CERTIFICATE_CONTEXT@@0_KA, r14; unsigned __int64 CERTIFICATE_CONTEXT::sm_CryptProvider
0x18001eb6e  mov     rcx, cs:?sm_pachW3FileInfo@W3_FILE_INFO@@0PEAVALLOC_CACHE_HANDLER@@EA; this
0x18001eb75  test    rcx, rcx
0x18001eb78  jz      short loc_18001EB7F
0x18001eb7a  call    ??_GALLOC_CACHE_HANDLER@@QEAAPEAXI@Z; ALLOC_CACHE_HANDLER::`scalar deleting destructor'(uint)
0x18001eb7f  mov     cs:?sm_pachW3FileInfo@W3_FILE_INFO@@0PEAVALLOC_CACHE_HANDLER@@EA, r14; ALLOC_CACHE_HANDLER * W3_FILE_INFO::sm_pachW3FileInfo
0x18001eb86  mov     rbx, cs:?sm_pConnectionTable@W3_CONNECTION@@0PEAVW3_CONNECTION_HASH@@EA; W3_CONNECTION_HASH * W3_CONNECTION::sm_pConnectionTable
0x18001eb8d  test    rbx, rbx
0x18001eb90  jz      short loc_18001EBAA
0x18001eb92  mov     rcx, rbx
0x18001eb95  call    cs:__imp_??1CLKRHashTable@@QEAA@XZ; CLKRHashTable::~CLKRHashTable(void)
0x18001eb9b  mov     rcx, rbx; Block
0x18001eb9e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001eba3  mov     cs:?sm_pConnectionTable@W3_CONNECTION@@0PEAVW3_CONNECTION_HASH@@EA, r14; W3_CONNECTION_HASH * W3_CONNECTION::sm_pConnectionTable
0x18001ebaa  mov     rcx, cs:?sm_pachW3Connections@W3_CONNECTION@@0PEAVALLOC_CACHE_HANDLER@@EA; this
0x18001ebb1  test    rcx, rcx
0x18001ebb4  jz      short loc_18001EBBB
0x18001ebb6  call    ??_GALLOC_CACHE_HANDLER@@QEAAPEAXI@Z; ALLOC_CACHE_HANDLER::`scalar deleting destructor'(uint)
0x18001ebbb  mov     rcx, cs:?sm_pTraceLog@W3_CONNECTION@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * W3_CONNECTION::sm_pTraceLog
0x18001ebc2  mov     cs:?sm_pachW3Connections@W3_CONNECTION@@0PEAVALLOC_CACHE_HANDLER@@EA, r14; ALLOC_CACHE_HANDLER * W3_CONNECTION::sm_pachW3Connections
0x18001ebc9  test    rcx, rcx
0x18001ebcc  jz      short loc_18001EBDB
0x18001ebce  call    cs:__imp_DestroyRefTraceLog
0x18001ebd4  mov     cs:?sm_pTraceLog@W3_CONNECTION@@0PEAU_TRACE_LOG@@EA, r14; _TRACE_LOG * W3_CONNECTION::sm_pTraceLog
0x18001ebdb  cmp     [rdi+620h], r14d
0x18001ebe2  jz      short loc_18001EC03
0x18001ebe4  mov     rcx, [rdi+698h]; hObject
0x18001ebeb  test    rcx, rcx
0x18001ebee  jz      short loc_18001EBFD
0x18001ebf0  call    cs:__imp_CloseHandle
0x18001ebf6  mov     [rdi+698h], r14
0x18001ebfd  call    cs:__imp_?UlAtqTerminate@@YAXXZ; UlAtqTerminate(void)
0x18001ec03  test    esi, esi
0x18001ec05  jnz     short loc_18001EC0D
0x18001ec07  call    cs:__imp_?ThreadPoolTerminate@@YAJXZ; ThreadPoolTerminate(void)
0x18001ec0d  call    cs:__imp_WSACleanup
0x18001ec13  mov     rcx, [rdi+610h]
0x18001ec1a  test    rcx, rcx
0x18001ec1d  jz      short loc_18001EC38
0x18001ec1f  call    cs:__imp_?Terminate@LANG_STRING@@QEAAJXZ; LANG_STRING::Terminate(void)
0x18001ec25  mov     rcx, [rdi+610h]; Block
0x18001ec2c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001ec31  mov     [rdi+610h], r14
0x18001ec38  call    cs:__imp_?TerminateLocalRequest@@YAJXZ; TerminateLocalRequest(void)
0x18001ec3e  call    cs:__imp_TerminateIISUtil
0x18001ec44  mov     rcx, [rdi+20h]; hLibModule
0x18001ec48  test    rcx, rcx
0x18001ec4b  jz      short loc_18001EC57
0x18001ec4d  call    cs:__imp_FreeLibrary
0x18001ec53  mov     [rdi+20h], r14
0x18001ec57  mov     rcx, cs:?g_pEtwGlobalTracer@@3PEAVCEtwTracer@@EA; CEtwTracer * g_pEtwGlobalTracer
0x18001ec5e  mov     [rdi+18h], r14d
0x18001ec62  cmp     [rcx+8], r14d
0x18001ec66  jz      short loc_18001ECAA
0x18001ec68  test    byte ptr [rcx+28h], 2
0x18001ec6c  jz      short loc_18001ECAA
0x18001ec6e  cmp     dword ptr [rcx+2Ch], 4
0x18001ec72  jb      short loc_18001ECAA
0x18001ec74  xorps   xmm0, xmm0
0x18001ec77  lea     rdx, [rbp+var_30]
0x18001ec7b  movups  [rbp+var_1E], xmm0
0x18001ec7f  mov     eax, 30h ; '0'
0x18001ec84  mov     qword ptr [rbp+var_1E+6], r13
0x18001ec88  movups  [rbp+var_2E], xmm0
0x18001ec8c  mov     [rbp+var_30], ax
0x18001ec90  movups  [rbp+var_1E+0Eh], xmm0
0x18001ec94  mov     [rbp+var_4], 1A0000h
0x18001ec9b  mov     word ptr [rbp+var_2E+4], r15w
0x18001eca0  mov     byte ptr [rbp+var_2E+2], 0Ch
0x18001eca4  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z; CEtwTracer::EtwTraceEvent(_EVENT_TRACE_HEADER *)
0x18001ecaa  add     rsp, 60h
0x18001ecae  pop     r15
0x18001ecb0  pop     r14
0x18001ecb2  pop     r13
0x18001ecb4  pop     rdi
0x18001ecb5  pop     rsi
0x18001ecb6  pop     rbx
0x18001ecb7  pop     rbp
0x18001ecb8  retn
```
