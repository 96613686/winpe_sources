# CIISModuleFactory::Terminate(void)

- ea: `0x18000a270`
- end: `0x18000a354`
- name: `?Terminate@CIISModuleFactory@@UEAAXXZ`
- size: `228`
- prototype: `void __fastcall(CIISModuleFactory *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callees

- `0x1800088fc`
- `0x18000a270`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000a304`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000a304`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a2c9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a2c9`
- `iisutil!DestroyRefTraceLog` at `0x18000a2b1`
- `iisutil!DestroyRefTraceLog` at `0x18000a2b1`
- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x18000a28c`
- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x18000a28c`
- `iisutil!?Terminate@LANG_STRING@@QEAAJXZ` at `0x18000a2db`
- `iisutil!?Terminate@LANG_STRING@@QEAAJXZ` at `0x18000a2db`

## pseudocode

```c
void __fastcall CIISModuleFactory::Terminate(CIISModuleFactory *this)
{
  void *v1; // rbx

  v1 = W3_FILTER_CONTEXT::sm_pachFilterContexts;
  if ( W3_FILTER_CONTEXT::sm_pachFilterContexts )
  {
    ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER((ALLOC_CACHE_HANDLER *)W3_FILTER_CONTEXT::sm_pachFilterContexts);
    operator delete(v1);
    W3_FILTER_CONTEXT::sm_pachFilterContexts = 0;
  }
  if ( W3_FILTER_CONTEXT::sm_pTraceLog )
  {
    DestroyRefTraceLog();
    W3_FILTER_CONTEXT::sm_pTraceLog = 0;
  }
  DeleteCriticalSection(&HTTP_FILTER_DLL::sm_csFilterDlls);
  if ( g_pLangString )
  {
    LANG_STRING::Terminate((LANG_STRING *)g_pLangString);
    operator delete(g_pLangString);
    g_pLangString = 0;
  }
  if ( g_hResourceDll )
  {
    FreeLibrary(g_hResourceDll);
    g_hResourceDll = 0;
  }
  if ( g_pEventLog )
  {
    operator delete(g_pEventLog);
    g_pEventLog = 0;
  }
  if ( this )
  {
    *((_QWORD *)this + 1) = &CHttpModule::`vftable';
    operator delete(this);
  }
}

```

## disassembly

```asm
0x18000a270  mov     [rsp+arg_0], rbx
0x18000a275  push    rdi
0x18000a276  sub     rsp, 20h
0x18000a27a  mov     rbx, cs:?sm_pachFilterContexts@W3_FILTER_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * W3_FILTER_CONTEXT::sm_pachFilterContexts
0x18000a281  mov     rdi, rcx
0x18000a284  test    rbx, rbx
0x18000a287  jz      short loc_18000A2A5
0x18000a289  mov     rcx, rbx
0x18000a28c  call    cs:__imp_??1ALLOC_CACHE_HANDLER@@QEAA@XZ; ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER(void)
0x18000a292  mov     rcx, rbx; Block
0x18000a295  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a29a  mov     cs:?sm_pachFilterContexts@W3_FILTER_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA, 0; ALLOC_CACHE_HANDLER * W3_FILTER_CONTEXT::sm_pachFilterContexts
0x18000a2a5  mov     rcx, cs:?sm_pTraceLog@W3_FILTER_CONTEXT@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * W3_FILTER_CONTEXT::sm_pTraceLog
0x18000a2ac  test    rcx, rcx
0x18000a2af  jz      short loc_18000A2C2
0x18000a2b1  call    cs:__imp_DestroyRefTraceLog
0x18000a2b7  mov     cs:?sm_pTraceLog@W3_FILTER_CONTEXT@@0PEAU_TRACE_LOG@@EA, 0; _TRACE_LOG * W3_FILTER_CONTEXT::sm_pTraceLog
0x18000a2c2  lea     rcx, ?sm_csFilterDlls@HTTP_FILTER_DLL@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000a2c9  call    cs:__imp_DeleteCriticalSection
0x18000a2cf  mov     rcx, cs:?g_pLangString@@3PEAVLANG_STRING@@EA; LANG_STRING * g_pLangString
0x18000a2d6  test    rcx, rcx
0x18000a2d9  jz      short loc_18000A2F8
0x18000a2db  call    cs:__imp_?Terminate@LANG_STRING@@QEAAJXZ; LANG_STRING::Terminate(void)
0x18000a2e1  mov     rcx, cs:?g_pLangString@@3PEAVLANG_STRING@@EA; Block
0x18000a2e8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a2ed  mov     cs:?g_pLangString@@3PEAVLANG_STRING@@EA, 0; LANG_STRING * g_pLangString
0x18000a2f8  mov     rcx, cs:?g_hResourceDll@@3PEAUHINSTANCE__@@EA; hLibModule
0x18000a2ff  test    rcx, rcx
0x18000a302  jz      short loc_18000A315
0x18000a304  call    cs:__imp_FreeLibrary
0x18000a30a  mov     cs:?g_hResourceDll@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_hResourceDll
0x18000a315  mov     rcx, cs:?g_pEventLog@@3PEAVEVENT_LOG@@EA; Block
0x18000a31c  test    rcx, rcx
0x18000a31f  jz      short loc_18000A331
0x18000a321  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a326  mov     cs:?g_pEventLog@@3PEAVEVENT_LOG@@EA, 0; EVENT_LOG * g_pEventLog
0x18000a331  test    rdi, rdi
0x18000a334  jz      short loc_18000A349
0x18000a336  lea     rax, ??_7CHttpModule@@6B@; const CHttpModule::`vftable'
0x18000a33d  mov     rcx, rdi; Block
0x18000a340  mov     [rdi+8], rax
0x18000a344  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a349  mov     rbx, [rsp+28h+arg_0]
0x18000a34e  add     rsp, 20h
0x18000a352  pop     rdi
0x18000a353  retn
```
