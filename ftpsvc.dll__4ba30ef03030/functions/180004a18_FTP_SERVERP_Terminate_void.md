# FTP_SERVERP::Terminate(void)

- ea: `0x180004a18`
- end: `0x180004e5f`
- name: `?Terminate@FTP_SERVERP@@QEAAXXZ`
- size: `1095`
- prototype: `void __fastcall(FTP_SERVERP *__hidden this)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800029fc`
- `0x180005ca0`

## callees

- `0x180001250`
- `0x18000485c`
- `0x180004a18`
- `0x18000865c`
- `0x18000b308`
- `0x180013b50`
- `0x180017128`
- `0x18001a62c`
- `0x18001ec28`
- `0x180020138`
- `0x180021fec`
- `0x180023f3c`
- `0x180025a58`
- `0x18002f684`
- `0x180033ec4`
- `0x180046e10`
- `0x18004700f`
- `0x180049010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180004d16`
- `KERNEL32!FreeLibrary` at `0x180004d16`
- `KERNEL32!DeleteTimerQueueTimer` at `0x180004deb`
- `KERNEL32!DeleteTimerQueueTimer` at `0x180004deb`
- `WS2_32!__imp_WSACleanup` at `0x180004e1e`
- `WS2_32!__imp_WSACleanup` at `0x180004e1e`
- `ole32!CoUninitialize` at `0x180004e24`
- `ole32!CoUninitialize` at `0x180004e24`
- `iisutil!?UnRegister@CEtwTracer@@QEAAKXZ` at `0x180004e2e`
- `iisutil!?UnRegister@CEtwTracer@@QEAAKXZ` at `0x180004e2e`
- `iisutil!TerminateLocalRequest` at `0x180004e18`
- `iisutil!TerminateLocalRequest` at `0x180004e18`
- `iisutil!?Clear@CLKRHashTable@@QEAAXXZ` at `0x180004cec`
- `iisutil!?Clear@CLKRHashTable@@QEAAXXZ` at `0x180004dcf`
- `iisutil!?Clear@CLKRHashTable@@QEAAXXZ` at `0x180004cec`
- `iisutil!?Clear@CLKRHashTable@@QEAAXXZ` at `0x180004dcf`
- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x180004c89`
- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x180004c89`
- `iisutil!DestroyRefTraceLog` at `0x180004c6d`
- `iisutil!DestroyRefTraceLog` at `0x180004caa`
- `iisutil!DestroyRefTraceLog` at `0x180004c6d`
- `iisutil!DestroyRefTraceLog` at `0x180004caa`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x180004ccb`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x180004d34`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x180004d69`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x180004ccb`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x180004d34`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x180004d69`

## pseudocode

```c
void __fastcall FTP_SERVERP::Terminate(FTP_SERVERP *this)
{
  THREAD_POOL *v2; // rcx
  __int64 v3; // rcx
  FTP_SERVERP *v4; // rcx
  void *v5; // rdi
  void (__fastcall ***v6)(_QWORD, __int64); // rcx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
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
  void (__fastcall ***v25)(_QWORD, __int64); // rcx
  void *v26; // rdi
  FTP_CONTROL_API_CLASS_FACTORY *v27; // rcx
  void *v28; // rdi
  void *v29; // rdi
  CLKRHashTable *v30; // rcx
  CLKRHashTable *v31; // rdi
  HMODULE v32; // rcx
  CREDENTIALS_CACHE *v33; // rcx
  void *v34; // rdi
  __int64 v35; // rcx
  BUFFER_POOL *v36; // rdi
  __int64 v37; // rcx
  __int64 v38; // rdi
  void *v39; // rdx
  void (__fastcall ***v40)(_QWORD, __int64); // rcx
  _OWORD v41[4]; // [rsp+20h] [rbp-48h] BYREF

  v2 = (THREAD_POOL *)*((_QWORD *)this + 10);
  if ( v2 )
  {
    THREAD_POOL::TerminateThreadPool(v2);
    *((_QWORD *)this + 10) = 0;
  }
  FTP_HOST_MONITOR::Terminate((FTP_SERVERP *)((char *)this + 320));
  v3 = *((_QWORD *)this + 22);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    *((_QWORD *)this + 22) = 0;
    FTP_SERVERP::StopFTPComPlusApplication(v4);
  }
  if ( *((int *)this + 2) >= 25 )
    FTP_SITE_PERF_CTRS::GlobalTerminate();
  v5 = (void *)*((_QWORD *)this + 11);
  if ( v5 )
  {
    FTP_SITE_MANAGER::~FTP_SITE_MANAGER(*((FTP_SITE_MANAGER **)this + 11));
    operator delete(v5);
    *((_QWORD *)this + 11) = 0;
  }
  if ( *((_DWORD *)this + 110) )
  {
    memset_0(v41, 0, sizeof(v41));
    v41[0] = SumGuid_FTP;
    SumInstrumentationStop(v41);
  }
  v6 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 56);
  if ( v6 )
  {
    (**v6)(v6, 1);
    *((_QWORD *)this + 56) = 0;
  }
  v7 = *((_DWORD *)this + 2);
  if ( v7 > 19 )
  {
    if ( v7 > 26 )
    {
      v20 = v7 - 27;
      if ( v20 )
      {
        v21 = v20 - 1;
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
                if ( v24 != 1 )
                  goto LABEL_86;
                IP_RESTRICTION_LIST::Terminate();
              }
              v25 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 54);
              if ( v25 )
              {
                (**v25)(v25, 1);
                *((_QWORD *)this + 54) = 0;
              }
            }
            v26 = (void *)*((_QWORD *)this + 38);
            if ( v26 )
            {
              AD_LOOKUP_MANAGER::Terminate(*((AD_LOOKUP_MANAGER **)this + 38));
              operator delete(v26);
              *((_QWORD *)this + 38) = 0;
            }
          }
          v27 = (FTP_CONTROL_API_CLASS_FACTORY *)*((_QWORD *)this + 23);
          if ( v27 )
          {
            FTP_CONTROL_API_CLASS_FACTORY::Terminate(v27);
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 23) + 16LL))(*((_QWORD *)this + 23));
            *((_QWORD *)this + 23) = 0;
          }
        }
        if ( FTP_LOG_FILE_MANAGER::sm_pRefTraceLog )
        {
          DestroyRefTraceLog();
          FTP_LOG_FILE_MANAGER::sm_pRefTraceLog = 0;
        }
      }
    }
    else if ( v7 != 26 )
    {
      v16 = v7 - 20;
      if ( !v16 )
      {
LABEL_65:
        v33 = (CREDENTIALS_CACHE *)*((_QWORD *)this + 51);
        if ( v33 )
        {
          CREDENTIALS_CACHE::Terminate(v33);
          v34 = (void *)*((_QWORD *)this + 51);
          if ( v34 )
          {
            CLKRHashTable::~CLKRHashTable(*((CLKRHashTable **)this + 51));
            operator delete(v34);
          }
          *((_QWORD *)this + 51) = 0;
        }
        goto LABEL_69;
      }
      v17 = v16 - 1;
      if ( !v17 )
      {
LABEL_59:
        v30 = (CLKRHashTable *)*((_QWORD *)this + 20);
        if ( v30 )
        {
          CLKRHashTable::Clear(v30);
          TOKEN_CACHE::Terminate(*((TOKEN_CACHE **)this + 20));
          v31 = (CLKRHashTable *)*((_QWORD *)this + 20);
          if ( v31 )
          {
            v32 = (HMODULE)*((_QWORD *)v31 + 18);
            if ( v32 )
            {
              FreeLibrary(v32);
              *((_QWORD *)v31 + 18) = 0;
              *((_QWORD *)v31 + 16) = 0;
              *((_QWORD *)v31 + 17) = 0;
            }
            CLKRHashTable::~CLKRHashTable(v31);
            operator delete(v31);
          }
          *((_QWORD *)this + 20) = 0;
        }
        goto LABEL_65;
      }
      v18 = v17 - 1;
      if ( !v18 || (v19 = v18 - 1) == 0 )
      {
LABEL_57:
        v29 = (void *)*((_QWORD *)this + 19);
        if ( v29 )
        {
          CLKRHashTable::~CLKRHashTable(*((CLKRHashTable **)this + 19));
          operator delete(v29);
          *((_QWORD *)this + 19) = 0;
        }
        goto LABEL_59;
      }
      if ( (unsigned int)(v19 - 1) >= 2 )
        goto LABEL_86;
LABEL_56:
      FTP_SESSION_PUBLIC::GlobalTerminate();
      goto LABEL_57;
    }
    v28 = FTP_SITE_CONFIG::sm_pAllocHandler;
    if ( FTP_SITE_CONFIG::sm_pAllocHandler )
    {
      ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER((ALLOC_CACHE_HANDLER *)FTP_SITE_CONFIG::sm_pAllocHandler);
      operator delete(v28);
      FTP_SITE_CONFIG::sm_pAllocHandler = 0;
    }
    if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
    {
      DestroyRefTraceLog();
      FTP_SITE_CONFIG::sm_pRefTraceLog = 0;
    }
    goto LABEL_56;
  }
  if ( v7 == 19 )
    goto LABEL_69;
  if ( v7 > 12 )
  {
    v12 = v7 - 13;
    if ( !v12 || (v13 = v12 - 1) == 0 )
    {
LABEL_74:
      v37 = *((_QWORD *)this + 18);
      if ( v37 )
      {
        CLKRHashTable::Clear((CLKRHashTable *)(v37 + 8));
        v38 = *((_QWORD *)this + 18);
        v39 = *(void **)(v38 + 80);
        if ( v39 )
        {
          DeleteTimerQueueTimer(0, v39, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
          *(_QWORD *)(v38 + 80) = 0;
        }
        v40 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 18);
        if ( v40 )
          (**v40)(v40, 1);
        *((_QWORD *)this + 18) = 0;
      }
      goto LABEL_80;
    }
    v14 = v13 - 1;
    if ( !v14 )
    {
LABEL_72:
      v36 = DATA_STREAM_BUFFER::sm_pBufferPool;
      if ( DATA_STREAM_BUFFER::sm_pBufferPool )
      {
        BUFFER_POOL::~BUFFER_POOL(DATA_STREAM_BUFFER::sm_pBufferPool);
        operator delete(v36);
        DATA_STREAM_BUFFER::sm_pBufferPool = 0;
      }
      goto LABEL_74;
    }
    v15 = v14 - 1;
    if ( !v15 )
    {
LABEL_71:
      SSL_STREAM_CONTEXT::GlobalTerminate();
      goto LABEL_72;
    }
    if ( (unsigned int)(v15 - 1) >= 2 )
      goto LABEL_86;
LABEL_69:
    v35 = *((_QWORD *)this + 12);
    if ( v35 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
      *((_QWORD *)this + 12) = 0;
    }
    goto LABEL_71;
  }
  if ( v7 == 12 )
    goto LABEL_74;
  v8 = v7 - 1;
  if ( !v8 )
    goto LABEL_84;
  v9 = v8 - 1;
  if ( v9 )
  {
    v10 = v9 - 2;
    if ( !v10 )
    {
LABEL_82:
      CoUninitialize();
      goto LABEL_83;
    }
    v11 = v10 - 1;
    if ( !v11 )
    {
LABEL_81:
      WSACleanup();
      goto LABEL_82;
    }
    if ( (unsigned int)(v11 - 1) >= 2 )
      goto LABEL_86;
LABEL_80:
    TerminateLocalRequest();
    goto LABEL_81;
  }
LABEL_83:
  CEtwTracer::UnRegister((FTP_SERVERP *)((char *)this + 16));
LABEL_84:
  if ( FTP_LOG_NT_EVENT::sm_pEventLog )
  {
    operator delete(FTP_LOG_NT_EVENT::sm_pEventLog);
    FTP_LOG_NT_EVENT::sm_pEventLog = 0;
  }
LABEL_86:
  *((_DWORD *)this + 2) = 0;
}

```

## disassembly

```asm
0x180004a18  mov     [rsp+arg_0], rbx
0x180004a1d  mov     [rsp+arg_8], rsi
0x180004a22  push    rdi
0x180004a23  sub     rsp, 60h
0x180004a27  mov     rbx, rcx
0x180004a2a  xor     esi, esi
0x180004a2c  mov     rcx, [rcx+50h]; this
0x180004a30  test    rcx, rcx
0x180004a33  jz      short loc_180004A3E
0x180004a35  call    ?TerminateThreadPool@THREAD_POOL@@QEAAXXZ; THREAD_POOL::TerminateThreadPool(void)
0x180004a3a  mov     [rbx+50h], rsi
0x180004a3e  lea     rcx, [rbx+140h]; this
0x180004a45  call    ?Terminate@FTP_HOST_MONITOR@@QEAAXXZ; FTP_HOST_MONITOR::Terminate(void)
0x180004a4a  mov     rcx, [rbx+0B0h]
0x180004a51  test    rcx, rcx
0x180004a54  jz      short loc_180004A6E
0x180004a56  mov     rax, [rcx]
0x180004a59  mov     rax, [rax+10h]
0x180004a5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a62  mov     [rbx+0B0h], rsi
0x180004a69  call    ?StopFTPComPlusApplication@FTP_SERVERP@@AEAAJXZ; FTP_SERVERP::StopFTPComPlusApplication(void)
0x180004a6e  cmp     dword ptr [rbx+8], 19h
0x180004a72  jl      short loc_180004A79
0x180004a74  call    ?GlobalTerminate@FTP_SITE_PERF_CTRS@@SAXXZ; FTP_SITE_PERF_CTRS::GlobalTerminate(void)
0x180004a79  mov     rdi, [rbx+58h]
0x180004a7d  test    rdi, rdi
0x180004a80  jz      short loc_180004A96
0x180004a82  mov     rcx, rdi; this
0x180004a85  call    ??1FTP_SITE_MANAGER@@QEAA@XZ; FTP_SITE_MANAGER::~FTP_SITE_MANAGER(void)
0x180004a8a  mov     rcx, rdi; Block
0x180004a8d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004a92  mov     [rbx+58h], rsi
0x180004a96  cmp     [rbx+1B8h], esi
0x180004a9c  jz      short loc_180004AC5
0x180004a9e  xor     edx, edx; Val
0x180004aa0  lea     rcx, [rsp+68h+var_48]; void *
0x180004aa5  lea     r8d, [rdx+40h]; Size
0x180004aa9  call    memset_0
0x180004aae  movups  xmm0, cs:SumGuid_FTP
0x180004ab5  lea     rcx, [rsp+68h+var_48]
0x180004aba  movdqu  [rsp+68h+var_48], xmm0
0x180004ac0  call    SumInstrumentationStop
0x180004ac5  mov     rcx, [rbx+1C0h]
0x180004acc  test    rcx, rcx
0x180004acf  jz      short loc_180004AE8
0x180004ad1  mov     rax, [rcx]
0x180004ad4  mov     edx, 1
0x180004ad9  mov     rax, [rax]
0x180004adc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ae1  mov     [rbx+1C0h], rsi
0x180004ae8  mov     ecx, [rbx+8]
0x180004aeb  cmp     ecx, 13h
0x180004aee  jg      loc_180004B7B
0x180004af4  jz      loc_180004D7E
0x180004afa  cmp     ecx, 0Ch
0x180004afd  jg      short loc_180004B40
0x180004aff  jz      loc_180004DBF
0x180004b05  sub     ecx, 1
0x180004b08  jz      loc_180004E34
0x180004b0e  sub     ecx, 1
0x180004b11  jz      loc_180004E2A
0x180004b17  sub     ecx, 2
0x180004b1a  jz      loc_180004E24
0x180004b20  sub     ecx, 1
0x180004b23  jz      loc_180004E1E
0x180004b29  sub     ecx, 1
0x180004b2c  jz      loc_180004E18
0x180004b32  cmp     ecx, 1
0x180004b35  jz      loc_180004E18
0x180004b3b  jmp     loc_180004E4C
0x180004b40  sub     ecx, 0Dh
0x180004b43  jz      loc_180004DBF
0x180004b49  sub     ecx, 1
0x180004b4c  jz      loc_180004DBF
0x180004b52  sub     ecx, 1
0x180004b55  jz      loc_180004D9C
0x180004b5b  sub     ecx, 1
0x180004b5e  jz      loc_180004D97
0x180004b64  sub     ecx, 1
0x180004b67  jz      loc_180004D7E
0x180004b6d  cmp     ecx, 1
0x180004b70  jz      loc_180004D7E
0x180004b76  jmp     loc_180004E4C
0x180004b7b  cmp     ecx, 1Ah
0x180004b7e  jg      short loc_180004BC1
0x180004b80  jz      loc_180004C7A
0x180004b86  sub     ecx, 14h
0x180004b89  jz      loc_180004D49
0x180004b8f  sub     ecx, 1
0x180004b92  jz      loc_180004CE0
0x180004b98  sub     ecx, 1
0x180004b9b  jz      loc_180004CBC
0x180004ba1  sub     ecx, 1
0x180004ba4  jz      loc_180004CBC
0x180004baa  sub     ecx, 1
0x180004bad  jz      loc_180004CB7
0x180004bb3  cmp     ecx, 1
0x180004bb6  jz      loc_180004CB7
0x180004bbc  jmp     loc_180004E4C
0x180004bc1  sub     ecx, 1Bh
0x180004bc4  jz      loc_180004C7A
0x180004bca  sub     ecx, 1
0x180004bcd  jz      loc_180004C61
0x180004bd3  sub     ecx, 1
0x180004bd6  jz      short loc_180004C36
0x180004bd8  sub     ecx, 1
0x180004bdb  jz      short loc_180004C13
0x180004bdd  sub     ecx, 1
0x180004be0  jz      short loc_180004BF0
0x180004be2  cmp     ecx, 1
0x180004be5  jnz     loc_180004E4C
0x180004beb  call    ?Terminate@IP_RESTRICTION_LIST@@SAXXZ; IP_RESTRICTION_LIST::Terminate(void)
0x180004bf0  mov     rcx, [rbx+1B0h]
0x180004bf7  test    rcx, rcx
0x180004bfa  jz      short loc_180004C13
0x180004bfc  mov     rax, [rcx]
0x180004bff  mov     edx, 1
0x180004c04  mov     rax, [rax]
0x180004c07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c0c  mov     [rbx+1B0h], rsi
0x180004c13  mov     rdi, [rbx+130h]
0x180004c1a  test    rdi, rdi
0x180004c1d  jz      short loc_180004C36
0x180004c1f  mov     rcx, rdi; this
0x180004c22  call    ?Terminate@AD_LOOKUP_MANAGER@@QEAAXXZ; AD_LOOKUP_MANAGER::Terminate(void)
0x180004c27  mov     rcx, rdi; Block
0x180004c2a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004c2f  mov     [rbx+130h], rsi
0x180004c36  mov     rcx, [rbx+0B8h]; this
0x180004c3d  test    rcx, rcx
0x180004c40  jz      short loc_180004C61
0x180004c42  call    ?Terminate@FTP_CONTROL_API_CLASS_FACTORY@@QEAAXXZ; FTP_CONTROL_API_CLASS_FACTORY::Terminate(void)
0x180004c47  mov     rcx, [rbx+0B8h]
0x180004c4e  mov     rax, [rcx]
0x180004c51  mov     rax, [rax+10h]
0x180004c55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c5a  mov     [rbx+0B8h], rsi
0x180004c61  mov     rcx, cs:?sm_pRefTraceLog@FTP_LOG_FILE_MANAGER@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_LOG_FILE_MANAGER::sm_pRefTraceLog
0x180004c68  test    rcx, rcx
0x180004c6b  jz      short loc_180004C7A
0x180004c6d  call    cs:__imp_DestroyRefTraceLog
0x180004c73  mov     cs:?sm_pRefTraceLog@FTP_LOG_FILE_MANAGER@@0PEAU_TRACE_LOG@@EA, rsi; _TRACE_LOG * FTP_LOG_FILE_MANAGER::sm_pRefTraceLog
0x180004c7a  mov     rdi, cs:?sm_pAllocHandler@FTP_SITE_CONFIG@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * FTP_SITE_CONFIG::sm_pAllocHandler
0x180004c81  test    rdi, rdi
0x180004c84  jz      short loc_180004C9E
0x180004c86  mov     rcx, rdi
0x180004c89  call    cs:__imp_??1ALLOC_CACHE_HANDLER@@QEAA@XZ; ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER(void)
0x180004c8f  mov     rcx, rdi; Block
0x180004c92  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004c97  mov     cs:?sm_pAllocHandler@FTP_SITE_CONFIG@@0PEAVALLOC_CACHE_HANDLER@@EA, rsi; ALLOC_CACHE_HANDLER * FTP_SITE_CONFIG::sm_pAllocHandler
0x180004c9e  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x180004ca5  test    rcx, rcx
0x180004ca8  jz      short loc_180004CB7
0x180004caa  call    cs:__imp_DestroyRefTraceLog
0x180004cb0  mov     cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA, rsi; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x180004cb7  call    ?GlobalTerminate@FTP_SESSION_PUBLIC@@SAXXZ; FTP_SESSION_PUBLIC::GlobalTerminate(void)
0x180004cbc  mov     rdi, [rbx+98h]
0x180004cc3  test    rdi, rdi
0x180004cc6  jz      short loc_180004CE0
0x180004cc8  mov     rcx, rdi
0x180004ccb  call    cs:__imp_??1CLKRHashTable@@QEAA@XZ; CLKRHashTable::~CLKRHashTable(void)
0x180004cd1  mov     rcx, rdi; Block
0x180004cd4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004cd9  mov     [rbx+98h], rsi
0x180004ce0  mov     rcx, [rbx+0A0h]
0x180004ce7  test    rcx, rcx
0x180004cea  jz      short loc_180004D49
0x180004cec  call    cs:__imp_?Clear@CLKRHashTable@@QEAAXXZ; CLKRHashTable::Clear(void)
0x180004cf2  mov     rcx, [rbx+0A0h]; this
0x180004cf9  call    ?Terminate@TOKEN_CACHE@@QEAAXXZ; TOKEN_CACHE::Terminate(void)
0x180004cfe  mov     rdi, [rbx+0A0h]
0x180004d05  test    rdi, rdi
0x180004d08  jz      short loc_180004D42
0x180004d0a  mov     rcx, [rdi+90h]; hLibModule
0x180004d11  test    rcx, rcx
0x180004d14  jz      short loc_180004D31
0x180004d16  call    cs:__imp_FreeLibrary
0x180004d1c  mov     [rdi+90h], rsi
0x180004d23  mov     [rdi+80h], rsi
0x180004d2a  mov     [rdi+88h], rsi
0x180004d31  mov     rcx, rdi
0x180004d34  call    cs:__imp_??1CLKRHashTable@@QEAA@XZ; CLKRHashTable::~CLKRHashTable(void)
0x180004d3a  mov     rcx, rdi; Block
0x180004d3d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004d42  mov     [rbx+0A0h], rsi
0x180004d49  mov     rcx, [rbx+198h]; this
0x180004d50  test    rcx, rcx
0x180004d53  jz      short loc_180004D7E
0x180004d55  call    ?Terminate@CREDENTIALS_CACHE@@QEAAXXZ; CREDENTIALS_CACHE::Terminate(void)
0x180004d5a  mov     rdi, [rbx+198h]
0x180004d61  test    rdi, rdi
0x180004d64  jz      short loc_180004D77
0x180004d66  mov     rcx, rdi
0x180004d69  call    cs:__imp_??1CLKRHashTable@@QEAA@XZ; CLKRHashTable::~CLKRHashTable(void)
0x180004d6f  mov     rcx, rdi; Block
0x180004d72  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004d77  mov     [rbx+198h], rsi
0x180004d7e  mov     rcx, [rbx+60h]
0x180004d82  test    rcx, rcx
0x180004d85  jz      short loc_180004D97
0x180004d87  mov     rax, [rcx]
0x180004d8a  mov     rax, [rax+10h]
0x180004d8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d93  mov     [rbx+60h], rsi
0x180004d97  call    ?GlobalTerminate@SSL_STREAM_CONTEXT@@SAXXZ; SSL_STREAM_CONTEXT::GlobalTerminate(void)
0x180004d9c  mov     rdi, cs:?sm_pBufferPool@DATA_STREAM_BUFFER@@0PEAVBUFFER_POOL@@EA; BUFFER_POOL * DATA_STREAM_BUFFER::sm_pBufferPool
0x180004da3  test    rdi, rdi
0x180004da6  jz      short loc_180004DBF
0x180004da8  mov     rcx, rdi; this
0x180004dab  call    ??1BUFFER_POOL@@QEAA@XZ; BUFFER_POOL::~BUFFER_POOL(void)
0x180004db0  mov     rcx, rdi; Block
0x180004db3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004db8  mov     cs:?sm_pBufferPool@DATA_STREAM_BUFFER@@0PEAVBUFFER_POOL@@EA, rsi; BUFFER_POOL * DATA_STREAM_BUFFER::sm_pBufferPool
0x180004dbf  mov     rcx, [rbx+90h]
0x180004dc6  test    rcx, rcx
0x180004dc9  jz      short loc_180004E18
0x180004dcb  add     rcx, 8
0x180004dcf  call    cs:__imp_?Clear@CLKRHashTable@@QEAAXXZ; CLKRHashTable::Clear(void)
0x180004dd5  mov     rdi, [rbx+90h]
0x180004ddc  mov     rdx, [rdi+50h]; Timer
0x180004de0  test    rdx, rdx
0x180004de3  jz      short loc_180004DF5
0x180004de5  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180004de9  xor     ecx, ecx; TimerQueue
0x180004deb  call    cs:__imp_DeleteTimerQueueTimer
0x180004df1  mov     [rdi+50h], rsi
0x180004df5  mov     rcx, [rbx+90h]
0x180004dfc  test    rcx, rcx
0x180004dff  jz      short loc_180004E11
0x180004e01  mov     rax, [rcx]
0x180004e04  mov     edx, 1
0x180004e09  mov     rax, [rax]
0x180004e0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e11  mov     [rbx+90h], rsi
0x180004e18  call    cs:__imp_?TerminateLocalRequest@@YAJXZ; TerminateLocalRequest(void)
0x180004e1e  call    cs:__imp_WSACleanup
0x180004e24  call    cs:__imp_CoUninitialize
0x180004e2a  lea     rcx, [rbx+10h]
0x180004e2e  call    cs:__imp_?UnRegister@CEtwTracer@@QEAAKXZ; CEtwTracer::UnRegister(void)
0x180004e34  mov     rcx, cs:?sm_pEventLog@FTP_LOG_NT_EVENT@@0PEAVEVENT_LOG@@EA; Block
0x180004e3b  test    rcx, rcx
0x180004e3e  jz      short loc_180004E4C
0x180004e40  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004e45  mov     cs:?sm_pEventLog@FTP_LOG_NT_EVENT@@0PEAVEVENT_LOG@@EA, rsi; EVENT_LOG * FTP_LOG_NT_EVENT::sm_pEventLog
0x180004e4c  mov     [rbx+8], esi
0x180004e4f  mov     rbx, [rsp+68h+arg_0]
0x180004e54  mov     rsi, [rsp+68h+arg_8]
0x180004e59  add     rsp, 60h
0x180004e5d  pop     rdi
0x180004e5e  retn
```
