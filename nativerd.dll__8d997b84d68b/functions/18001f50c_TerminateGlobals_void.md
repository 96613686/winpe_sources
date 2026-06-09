# TerminateGlobals(void)

- ea: `0x18001f50c`
- end: `0x18001f7aa`
- name: `?TerminateGlobals@@YAXXZ`
- size: `670`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x18001fa70`

## callees

- `0x18001a684`
- `0x18001c290`
- `0x18001e508`
- `0x18001f50c`
- `0x18001fd70`
- `0x18002b1b0`
- `0x18005b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001f778`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001f778`
- `iisutil!DestroyRefTraceLog` at `0x18001f639`
- `iisutil!DestroyRefTraceLog` at `0x18001f6ba`
- `iisutil!DestroyRefTraceLog` at `0x18001f6d3`
- `iisutil!DestroyRefTraceLog` at `0x18001f6ec`
- `iisutil!DestroyRefTraceLog` at `0x18001f705`
- `iisutil!DestroyRefTraceLog` at `0x18001f71e`
- `iisutil!DestroyRefTraceLog` at `0x18001f737`
- `iisutil!DestroyRefTraceLog` at `0x18001f639`
- `iisutil!DestroyRefTraceLog` at `0x18001f6ba`
- `iisutil!DestroyRefTraceLog` at `0x18001f6d3`
- `iisutil!DestroyRefTraceLog` at `0x18001f6ec`
- `iisutil!DestroyRefTraceLog` at `0x18001f705`
- `iisutil!DestroyRefTraceLog` at `0x18001f71e`
- `iisutil!DestroyRefTraceLog` at `0x18001f737`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001f51d`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001f51d`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001f544`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001f544`
- `iisutil!?Clear@CLKRHashTable@@QEAAXXZ` at `0x18001f5f4`
- `iisutil!?Clear@CLKRHashTable@@QEAAXXZ` at `0x18001f5f4`
- `iisutil!?Terminate@BIG_REF_TRACE@@QEAAJXZ` at `0x18001f665`
- `iisutil!?Terminate@BIG_REF_TRACE@@QEAAJXZ` at `0x18001f665`
- `iisutil!PuDeleteDebugPrintsObject` at `0x18001f78c`
- `iisutil!PuDeleteDebugPrintsObject` at `0x18001f78c`
- `iisutil!??1BIG_REF_TRACE@@QEAA@XZ` at `0x18001f67a`
- `iisutil!??1BIG_REF_TRACE@@QEAA@XZ` at `0x18001f67a`
- `CRYPTSP!CryptReleaseContext` at `0x18001f608`
- `CRYPTSP!CryptReleaseContext` at `0x18001f608`

## pseudocode

```c
void TerminateGlobals(void)
{
  unsigned int v0; // edx
  void *v1; // rbx

  CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)&g_schemaTableLock);
  if ( g_pSchemaTable )
  {
    SCHEMA_TABLE::DereferenceSchemaTable(g_pSchemaTable);
    g_pSchemaTable = 0;
  }
  CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)&g_schemaTableLock);
  if ( g_initStatus <= 9 )
  {
    if ( g_initStatus != 9 )
    {
      switch ( g_initStatus )
      {
        case 1:
LABEL_55:
          g_pDebug = PuDeleteDebugPrintsObject(g_pDebug);
          goto LABEL_56;
        case 2:
LABEL_54:
          FreeLibrary((HMODULE)g_hResourceDll);
          g_hResourceDll = 0;
          goto LABEL_55;
        case 3:
LABEL_53:
          McGenEventUnregister_EtwEventUnregister();
          goto LABEL_54;
        case 4:
LABEL_50:
          if ( g_pFastStringTable )
            (**(void (__fastcall ***)(struct FAST_STRING_TABLE *, __int64))g_pFastStringTable)(g_pFastStringTable, 1);
          g_pFastStringTable = 0;
          goto LABEL_53;
        case 5:
LABEL_49:
          CONFIG_SECTION::Terminate();
          goto LABEL_50;
        case 6:
        case 7:
LABEL_47:
          if ( CONFIG_DOM_NODE::sm_pTraceLog )
          {
            DestroyRefTraceLog();
            CONFIG_DOM_NODE::sm_pTraceLog = 0;
          }
          goto LABEL_49;
      }
      if ( g_initStatus != 8 )
        goto LABEL_56;
LABEL_45:
      if ( ATTRIBUTE_VALUE::sm_pTraceLog )
      {
        DestroyRefTraceLog();
        ATTRIBUTE_VALUE::sm_pTraceLog = 0;
      }
      goto LABEL_47;
    }
LABEL_43:
    if ( CONFIG_ELEMENT::sm_pTraceLog )
    {
      DestroyRefTraceLog();
      CONFIG_ELEMENT::sm_pTraceLog = 0;
    }
    goto LABEL_45;
  }
  switch ( g_initStatus )
  {
    case 0xA:
LABEL_41:
      if ( SCHEMA_ELEMENT::sm_pTraceLog )
      {
        DestroyRefTraceLog();
        SCHEMA_ELEMENT::sm_pTraceLog = 0;
      }
      goto LABEL_43;
    case 0xB:
LABEL_39:
      if ( LOCATION_CONTEXT::s_pTraceLog )
      {
        DestroyRefTraceLog();
        LOCATION_CONTEXT::s_pTraceLog = 0;
      }
      goto LABEL_41;
    case 0xC:
LABEL_37:
      if ( SEARCH_RESULT::sm_pTraceLog )
      {
        DestroyRefTraceLog();
        SEARCH_RESULT::sm_pTraceLog = 0;
      }
      goto LABEL_39;
    case 0xD:
LABEL_35:
      if ( g_pSupportErrorInfo )
      {
        (*(void (__fastcall **)(struct SUPPORT_ERROR_INFO *))(*(_QWORD *)g_pSupportErrorInfo + 16LL))(g_pSupportErrorInfo);
        g_pSupportErrorInfo = 0;
      }
      goto LABEL_37;
    case 0xE:
LABEL_31:
      if ( g_pBigRefTrace )
      {
        BIG_REF_TRACE::Terminate((BIG_REF_TRACE *)g_pBigRefTrace);
        v1 = g_pBigRefTrace;
        if ( g_pBigRefTrace )
        {
          BIG_REF_TRACE::~BIG_REF_TRACE((BIG_REF_TRACE *)g_pBigRefTrace);
          operator delete(v1);
        }
        g_pBigRefTrace = 0;
      }
      goto LABEL_35;
    case 0xF:
LABEL_30:
      operator delete(g_pExtensionTable);
      g_pExtensionTable = 0;
      goto LABEL_31;
    case 0x10:
LABEL_28:
      if ( CONFIG_EXCEPTION::sm_pTraceLog )
      {
        DestroyRefTraceLog();
        CONFIG_EXCEPTION::sm_pTraceLog = 0;
      }
      goto LABEL_30;
    case 0x11:
      if ( g_pTokenCache )
      {
        CLKRHashTable::Clear(g_pTokenCache);
        if ( TOKEN_CACHE_ENTRY::sm_hCryptProv )
        {
          CryptReleaseContext(TOKEN_CACHE_ENTRY::sm_hCryptProv, 0);
          TOKEN_CACHE_ENTRY::sm_hCryptProv = 0;
        }
        if ( g_pTokenCache )
          TOKEN_CACHE::`scalar deleting destructor'(g_pTokenCache, v0);
        g_pTokenCache = 0;
      }
      goto LABEL_28;
  }
LABEL_56:
  g_initStatus = 0;
}

```

## disassembly

```asm
0x18001f50c  mov     [rsp+arg_0], rbx
0x18001f511  push    rdi
0x18001f512  sub     rsp, 20h
0x18001f516  lea     rcx, ?g_schemaTableLock@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_schemaTableLock
0x18001f51d  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18001f523  mov     rcx, cs:?g_pSchemaTable@@3PEAVSCHEMA_TABLE@@EA; this
0x18001f52a  xor     edi, edi
0x18001f52c  test    rcx, rcx
0x18001f52f  jz      short loc_18001F53D
0x18001f531  call    ?DereferenceSchemaTable@SCHEMA_TABLE@@QEAAXXZ; SCHEMA_TABLE::DereferenceSchemaTable(void)
0x18001f536  mov     cs:?g_pSchemaTable@@3PEAVSCHEMA_TABLE@@EA, rdi; SCHEMA_TABLE * g_pSchemaTable
0x18001f53d  lea     rcx, ?g_schemaTableLock@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_schemaTableLock
0x18001f544  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18001f54a  mov     ecx, cs:?g_initStatus@@3W4GLOBAL_INIT_STATUS@@A; GLOBAL_INIT_STATUS g_initStatus
0x18001f550  cmp     ecx, 9
0x18001f553  jg      short loc_18001F5A8
0x18001f555  jz      loc_18001F6F9
0x18001f55b  sub     ecx, 1
0x18001f55e  jz      loc_18001F785
0x18001f564  sub     ecx, 1
0x18001f567  jz      loc_18001F771
0x18001f56d  sub     ecx, 1
0x18001f570  jz      loc_18001F76C
0x18001f576  sub     ecx, 1
0x18001f579  jz      loc_18001F749
0x18001f57f  sub     ecx, 1
0x18001f582  jz      loc_18001F744
0x18001f588  sub     ecx, 1
0x18001f58b  jz      loc_18001F72B
0x18001f591  sub     ecx, 1
0x18001f594  jz      loc_18001F72B
0x18001f59a  cmp     ecx, 1
0x18001f59d  jz      loc_18001F712
0x18001f5a3  jmp     loc_18001F799
0x18001f5a8  sub     ecx, 0Ah
0x18001f5ab  jz      loc_18001F6E0
0x18001f5b1  sub     ecx, 1
0x18001f5b4  jz      loc_18001F6C7
0x18001f5ba  sub     ecx, 1
0x18001f5bd  jz      loc_18001F6AE
0x18001f5c3  sub     ecx, 1
0x18001f5c6  jz      loc_18001F68F
0x18001f5cc  sub     ecx, 1
0x18001f5cf  jz      loc_18001F659
0x18001f5d5  sub     ecx, 1
0x18001f5d8  jz      short loc_18001F646
0x18001f5da  sub     ecx, 1
0x18001f5dd  jz      short loc_18001F62D
0x18001f5df  cmp     ecx, 1
0x18001f5e2  jnz     loc_18001F799
0x18001f5e8  mov     rcx, cs:?g_pTokenCache@@3PEAVTOKEN_CACHE@@EA; TOKEN_CACHE * g_pTokenCache
0x18001f5ef  test    rcx, rcx
0x18001f5f2  jz      short loc_18001F62D
0x18001f5f4  call    cs:__imp_?Clear@CLKRHashTable@@QEAAXXZ; CLKRHashTable::Clear(void)
0x18001f5fa  mov     rcx, cs:?sm_hCryptProv@TOKEN_CACHE_ENTRY@@0_KA; hProv
0x18001f601  test    rcx, rcx
0x18001f604  jz      short loc_18001F615
0x18001f606  xor     edx, edx; dwFlags
0x18001f608  call    cs:__imp_CryptReleaseContext
0x18001f60e  mov     cs:?sm_hCryptProv@TOKEN_CACHE_ENTRY@@0_KA, rdi; unsigned __int64 TOKEN_CACHE_ENTRY::sm_hCryptProv
0x18001f615  mov     rcx, cs:?g_pTokenCache@@3PEAVTOKEN_CACHE@@EA; this
0x18001f61c  test    rcx, rcx
0x18001f61f  jz      short loc_18001F626
0x18001f621  call    ??_GTOKEN_CACHE@@QEAAPEAXI@Z; TOKEN_CACHE::`scalar deleting destructor'(uint)
0x18001f626  mov     cs:?g_pTokenCache@@3PEAVTOKEN_CACHE@@EA, rdi; TOKEN_CACHE * g_pTokenCache
0x18001f62d  mov     rcx, cs:?sm_pTraceLog@CONFIG_EXCEPTION@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * CONFIG_EXCEPTION::sm_pTraceLog
0x18001f634  test    rcx, rcx
0x18001f637  jz      short loc_18001F646
0x18001f639  call    cs:__imp_DestroyRefTraceLog
0x18001f63f  mov     cs:?sm_pTraceLog@CONFIG_EXCEPTION@@0PEAU_TRACE_LOG@@EA, rdi; _TRACE_LOG * CONFIG_EXCEPTION::sm_pTraceLog
0x18001f646  mov     rcx, cs:?g_pExtensionTable@@3PEAVEXTENSION_TABLE@@EA; Block
0x18001f64d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001f652  mov     cs:?g_pExtensionTable@@3PEAVEXTENSION_TABLE@@EA, rdi; EXTENSION_TABLE * g_pExtensionTable
0x18001f659  mov     rcx, cs:?g_pBigRefTrace@@3PEAVBIG_REF_TRACE@@EA; BIG_REF_TRACE * g_pBigRefTrace
0x18001f660  test    rcx, rcx
0x18001f663  jz      short loc_18001F68F
0x18001f665  call    cs:__imp_?Terminate@BIG_REF_TRACE@@QEAAJXZ; BIG_REF_TRACE::Terminate(void)
0x18001f66b  mov     rbx, cs:?g_pBigRefTrace@@3PEAVBIG_REF_TRACE@@EA; BIG_REF_TRACE * g_pBigRefTrace
0x18001f672  test    rbx, rbx
0x18001f675  jz      short loc_18001F688
0x18001f677  mov     rcx, rbx
0x18001f67a  call    cs:__imp_??1BIG_REF_TRACE@@QEAA@XZ; BIG_REF_TRACE::~BIG_REF_TRACE(void)
0x18001f680  mov     rcx, rbx; Block
0x18001f683  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001f688  mov     cs:?g_pBigRefTrace@@3PEAVBIG_REF_TRACE@@EA, rdi; BIG_REF_TRACE * g_pBigRefTrace
0x18001f68f  mov     rcx, cs:?g_pSupportErrorInfo@@3PEAVSUPPORT_ERROR_INFO@@EA; SUPPORT_ERROR_INFO * g_pSupportErrorInfo
0x18001f696  test    rcx, rcx
0x18001f699  jz      short loc_18001F6AE
0x18001f69b  mov     rax, [rcx]
0x18001f69e  mov     rax, [rax+10h]
0x18001f6a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f6a7  mov     cs:?g_pSupportErrorInfo@@3PEAVSUPPORT_ERROR_INFO@@EA, rdi; SUPPORT_ERROR_INFO * g_pSupportErrorInfo
0x18001f6ae  mov     rcx, cs:?sm_pTraceLog@SEARCH_RESULT@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * SEARCH_RESULT::sm_pTraceLog
0x18001f6b5  test    rcx, rcx
0x18001f6b8  jz      short loc_18001F6C7
0x18001f6ba  call    cs:__imp_DestroyRefTraceLog
0x18001f6c0  mov     cs:?sm_pTraceLog@SEARCH_RESULT@@0PEAU_TRACE_LOG@@EA, rdi; _TRACE_LOG * SEARCH_RESULT::sm_pTraceLog
0x18001f6c7  mov     rcx, cs:?s_pTraceLog@LOCATION_CONTEXT@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * LOCATION_CONTEXT::s_pTraceLog
0x18001f6ce  test    rcx, rcx
0x18001f6d1  jz      short loc_18001F6E0
0x18001f6d3  call    cs:__imp_DestroyRefTraceLog
0x18001f6d9  mov     cs:?s_pTraceLog@LOCATION_CONTEXT@@0PEAU_TRACE_LOG@@EA, rdi; _TRACE_LOG * LOCATION_CONTEXT::s_pTraceLog
0x18001f6e0  mov     rcx, cs:?sm_pTraceLog@SCHEMA_ELEMENT@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * SCHEMA_ELEMENT::sm_pTraceLog
0x18001f6e7  test    rcx, rcx
0x18001f6ea  jz      short loc_18001F6F9
0x18001f6ec  call    cs:__imp_DestroyRefTraceLog
0x18001f6f2  mov     cs:?sm_pTraceLog@SCHEMA_ELEMENT@@0PEAU_TRACE_LOG@@EA, rdi; _TRACE_LOG * SCHEMA_ELEMENT::sm_pTraceLog
0x18001f6f9  mov     rcx, cs:?sm_pTraceLog@CONFIG_ELEMENT@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * CONFIG_ELEMENT::sm_pTraceLog
0x18001f700  test    rcx, rcx
0x18001f703  jz      short loc_18001F712
0x18001f705  call    cs:__imp_DestroyRefTraceLog
0x18001f70b  mov     cs:?sm_pTraceLog@CONFIG_ELEMENT@@0PEAU_TRACE_LOG@@EA, rdi; _TRACE_LOG * CONFIG_ELEMENT::sm_pTraceLog
0x18001f712  mov     rcx, cs:?sm_pTraceLog@ATTRIBUTE_VALUE@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * ATTRIBUTE_VALUE::sm_pTraceLog
0x18001f719  test    rcx, rcx
0x18001f71c  jz      short loc_18001F72B
0x18001f71e  call    cs:__imp_DestroyRefTraceLog
0x18001f724  mov     cs:?sm_pTraceLog@ATTRIBUTE_VALUE@@0PEAU_TRACE_LOG@@EA, rdi; _TRACE_LOG * ATTRIBUTE_VALUE::sm_pTraceLog
0x18001f72b  mov     rcx, cs:?sm_pTraceLog@CONFIG_DOM_NODE@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * CONFIG_DOM_NODE::sm_pTraceLog
0x18001f732  test    rcx, rcx
0x18001f735  jz      short loc_18001F744
0x18001f737  call    cs:__imp_DestroyRefTraceLog
0x18001f73d  mov     cs:?sm_pTraceLog@CONFIG_DOM_NODE@@0PEAU_TRACE_LOG@@EA, rdi; _TRACE_LOG * CONFIG_DOM_NODE::sm_pTraceLog
0x18001f744  call    ?Terminate@CONFIG_SECTION@@SAXXZ; CONFIG_SECTION::Terminate(void)
0x18001f749  mov     rcx, cs:?g_pFastStringTable@@3PEAVFAST_STRING_TABLE@@EA; FAST_STRING_TABLE * g_pFastStringTable
0x18001f750  test    rcx, rcx
0x18001f753  jz      short loc_18001F765
0x18001f755  mov     rax, [rcx]
0x18001f758  mov     edx, 1
0x18001f75d  mov     rax, [rax]
0x18001f760  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f765  mov     cs:?g_pFastStringTable@@3PEAVFAST_STRING_TABLE@@EA, rdi; FAST_STRING_TABLE * g_pFastStringTable
0x18001f76c  call    McGenEventUnregister_EtwEventUnregister
0x18001f771  mov     rcx, cs:?g_hResourceDll@@3PEAUHINSTANCE__@@EA; hLibModule
0x18001f778  call    cs:__imp_FreeLibrary
0x18001f77e  mov     cs:?g_hResourceDll@@3PEAUHINSTANCE__@@EA, rdi; HINSTANCE__ * g_hResourceDll
0x18001f785  mov     rcx, cs:g_pDebug
0x18001f78c  call    cs:__imp_PuDeleteDebugPrintsObject
0x18001f792  mov     cs:g_pDebug, rax
0x18001f799  mov     rbx, [rsp+28h+arg_0]
0x18001f79e  mov     cs:?g_initStatus@@3W4GLOBAL_INIT_STATUS@@A, edi; GLOBAL_INIT_STATUS g_initStatus
0x18001f7a4  add     rsp, 20h
0x18001f7a8  pop     rdi
0x18001f7a9  retn
```
