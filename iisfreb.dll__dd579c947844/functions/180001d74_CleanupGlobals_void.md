# CleanupGlobals(void)

- ea: `0x180001d74`
- end: `0x180001e83`
- name: `?CleanupGlobals@@YAXXZ`
- size: `271`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180003130`
- `0x180003600`

## callees

- `0x180001048`
- `0x180001d74`
- `0x1800054e8`
- `0x180008958`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180001e06`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180001e06`
- `iisutil!PuDeleteDebugPrintsObject` at `0x180001e66`
- `iisutil!PuDeleteDebugPrintsObject` at `0x180001e66`

## pseudocode

```c
void CleanupGlobals(void)
{
  struct FREB_LOG_NT_EVENT_TABLE *v0; // rbx
  void *v1; // rdx

  switch ( g_StartupState )
  {
    case 1:
      goto LABEL_21;
    case 2:
LABEL_20:
      FREB_REQUEST_CONTEXT::Terminate();
LABEL_21:
      g_pDebug = PuDeleteDebugPrintsObject(g_pDebug);
      break;
    case 3:
LABEL_18:
      if ( FREB_LOG_NT_EVENT::sm_pEventLog )
      {
        operator delete(FREB_LOG_NT_EVENT::sm_pEventLog);
        FREB_LOG_NT_EVENT::sm_pEventLog = 0;
      }
      goto LABEL_20;
    case 4:
LABEL_12:
      v0 = g_pFrebLogNtEventTable;
      if ( g_pFrebLogNtEventTable )
      {
        v1 = (void *)*((_QWORD *)g_pFrebLogNtEventTable + 10);
        if ( v1 )
        {
          DeleteTimerQueueTimer(0, v1, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
          *((_QWORD *)v0 + 10) = 0;
          v0 = g_pFrebLogNtEventTable;
        }
        if ( v0 )
          (**(void (__fastcall ***)(struct FREB_LOG_NT_EVENT_TABLE *, __int64))v0)(v0, 1);
        g_pFrebLogNtEventTable = 0;
      }
      goto LABEL_18;
    case 5:
LABEL_11:
      FREB_LOG_FILE_MANAGER::Terminate();
      goto LABEL_12;
    case 6:
      if ( FREB_XML_SERIALIZER::sm_pszComputerName )
      {
        operator delete(FREB_XML_SERIALIZER::sm_pszComputerName);
        FREB_XML_SERIALIZER::sm_pszComputerName = 0;
      }
      if ( FREB_XML_SERIALIZER::sm_pszSystemLocale )
      {
        operator delete(FREB_XML_SERIALIZER::sm_pszSystemLocale);
        FREB_XML_SERIALIZER::sm_pszSystemLocale = 0;
      }
      goto LABEL_11;
  }
  g_StartupState = 7;
}

```

## disassembly

```asm
0x180001d74  push    rbx
0x180001d76  sub     rsp, 20h
0x180001d7a  mov     ecx, cs:?g_StartupState@@3W4FrebStartup@@A; FrebStartup g_StartupState
0x180001d80  sub     ecx, 1
0x180001d83  jz      loc_180001E5F
0x180001d89  sub     ecx, 1
0x180001d8c  jz      loc_180001E5A
0x180001d92  sub     ecx, 1
0x180001d95  jz      loc_180001E3E
0x180001d9b  sub     ecx, 1
0x180001d9e  jz      short loc_180001DEB
0x180001da0  sub     ecx, 1
0x180001da3  jz      short loc_180001DE6
0x180001da5  cmp     ecx, 1
0x180001da8  jnz     loc_180001E73
0x180001dae  mov     rcx, cs:?sm_pszComputerName@FREB_XML_SERIALIZER@@0PEAGEA; Block
0x180001db5  test    rcx, rcx
0x180001db8  jz      short loc_180001DCA
0x180001dba  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001dbf  mov     cs:?sm_pszComputerName@FREB_XML_SERIALIZER@@0PEAGEA, 0; ushort * FREB_XML_SERIALIZER::sm_pszComputerName
0x180001dca  mov     rcx, cs:?sm_pszSystemLocale@FREB_XML_SERIALIZER@@0PEAGEA; Block
0x180001dd1  test    rcx, rcx
0x180001dd4  jz      short loc_180001DE6
0x180001dd6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001ddb  mov     cs:?sm_pszSystemLocale@FREB_XML_SERIALIZER@@0PEAGEA, 0; ushort * FREB_XML_SERIALIZER::sm_pszSystemLocale
0x180001de6  call    ?Terminate@FREB_LOG_FILE_MANAGER@@SAJXZ; FREB_LOG_FILE_MANAGER::Terminate(void)
0x180001deb  mov     rbx, cs:?g_pFrebLogNtEventTable@@3PEAVFREB_LOG_NT_EVENT_TABLE@@EA; FREB_LOG_NT_EVENT_TABLE * g_pFrebLogNtEventTable
0x180001df2  test    rbx, rbx
0x180001df5  jz      short loc_180001E3E
0x180001df7  mov     rdx, [rbx+50h]; Timer
0x180001dfb  test    rdx, rdx
0x180001dfe  jz      short loc_180001E1B
0x180001e00  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180001e04  xor     ecx, ecx; TimerQueue
0x180001e06  call    cs:__imp_DeleteTimerQueueTimer
0x180001e0c  mov     qword ptr [rbx+50h], 0
0x180001e14  mov     rbx, cs:?g_pFrebLogNtEventTable@@3PEAVFREB_LOG_NT_EVENT_TABLE@@EA; FREB_LOG_NT_EVENT_TABLE * g_pFrebLogNtEventTable
0x180001e1b  test    rbx, rbx
0x180001e1e  jz      short loc_180001E33
0x180001e20  mov     rax, [rbx]
0x180001e23  mov     edx, 1
0x180001e28  mov     rcx, rbx
0x180001e2b  mov     rax, [rax]
0x180001e2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e33  mov     cs:?g_pFrebLogNtEventTable@@3PEAVFREB_LOG_NT_EVENT_TABLE@@EA, 0; FREB_LOG_NT_EVENT_TABLE * g_pFrebLogNtEventTable
0x180001e3e  mov     rcx, cs:?sm_pEventLog@FREB_LOG_NT_EVENT@@0PEAVEVENT_LOG@@EA; Block
0x180001e45  test    rcx, rcx
0x180001e48  jz      short loc_180001E5A
0x180001e4a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001e4f  mov     cs:?sm_pEventLog@FREB_LOG_NT_EVENT@@0PEAVEVENT_LOG@@EA, 0; EVENT_LOG * FREB_LOG_NT_EVENT::sm_pEventLog
0x180001e5a  call    ?Terminate@FREB_REQUEST_CONTEXT@@SAXXZ; FREB_REQUEST_CONTEXT::Terminate(void)
0x180001e5f  mov     rcx, cs:g_pDebug
0x180001e66  call    cs:__imp_PuDeleteDebugPrintsObject
0x180001e6c  mov     cs:g_pDebug, rax
0x180001e73  mov     cs:?g_StartupState@@3W4FrebStartup@@A, 7; FrebStartup g_StartupState
0x180001e7d  add     rsp, 20h
0x180001e81  pop     rbx
0x180001e82  retn
```
