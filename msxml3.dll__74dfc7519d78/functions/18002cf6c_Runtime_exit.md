# Runtime_exit

- ea: `0x18002cf6c`
- end: `0x18002d215`
- name: `Runtime_exit`
- size: `681`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x1800369e0`

## callees

- `0x180020038`
- `0x18002cf6c`
- `0x18002d21c`
- `0x18002d390`
- `0x18002d3b8`
- `0x18002d3fc`
- `0x18002d468`
- `0x18002dac0`
- `0x18004b488`
- `0x18004bdb4`
- `0x180051d40`
- `0x180064034`
- `0x180107010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x18002d08c`
- `msvcrt!_resetstkoflw` at `0x18002d172`
- `msvcrt!_resetstkoflw` at `0x18002d08c`
- `msvcrt!_resetstkoflw` at `0x18002d172`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002d058`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002d058`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002d0df`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002d1c5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002d0df`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002d1c5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002cfb4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002d016`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002d07a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002d160`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002cfb4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002d016`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002d07a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002d160`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18002cffa`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18002cffa`

## string_xrefs

- `0x18002cff3`: `At least one thread was killed while executing inside msxml.dll.\n!! msxml.dll is unable to shut down !!\n`

## pseudocode

```c
void Runtime_exit()
{
  TLSDATA *Value; // rsi
  TLSDATA *i; // rdi
  SlotAllocator *v2; // rdi
  SlotAllocator *v3; // rcx

  if ( !byte_18014B2D0 )
  {
    byte_18014B2D0 = 1;
    g_fInShutDown = 1;
    if ( g_fClassInitFailed )
      g_fClassInitCalled = 1;
    EnsureTlsData();
    Value = (TLSDATA *)TlsGetValue(g_dwTlsIndex);
    for ( i = g_ptlsdata; i; i = (TLSDATA *)*((_QWORD *)i + 5) )
    {
      if ( i != Value && *((_DWORD *)i + 20) )
        g_fBadShutDown = 1;
      TLSDATA::clear(i);
    }
    if ( g_fBadShutDown )
    {
      OutputDebugStringW(L"At least one thread was killed while executing inside msxml.dll.\n!! msxml.dll is unable to shut down !!\n");
    }
    else
    {
      TerminateMimeDwn();
      ++Base::s_lInGC;
      Base::s_ptlsCheckZeroList = (struct TLSDATA *)TlsGetValue(g_dwTlsIndex);
      Base::s_ptlsGC = Base::s_ptlsCheckZeroList;
      Base::s_fInFreeObjects = 1;
      if ( g_fClassInitCalled )
        DOMNode::classExit();
      ClearReferences();
      if ( Resources::s_hInstance && Resources::s_hInstance != g_hInstance )
      {
        FreeLibrary(Resources::s_hInstance);
        Resources::s_hInstance = 0;
      }
      Exception::classExit();
      Base::FinishFreeObjects();
      if ( g_fClassInitCalled )
      {
        v2 = NodeManager::s_pFreeList;
        while ( v2 )
        {
          v3 = v2;
          v2 = (SlotAllocator *)*((_QWORD *)v2 + 23);
          (*(void (__fastcall **)(SlotAllocator *))(*(_QWORD *)v3 + 16LL))(v3);
        }
        if ( s_pDefaultVMM )
        {
          if ( _xunknown::Release((struct VMManager *)((char *)s_pDefaultVMM + 8)) )
            failure_tracing::record();
        }
      }
    }
    MTExit();
    g_fHasExited = 1;
    g_pfnEntry = (struct TLSDATA *(*)(void))ReplFactory::Error;
  }
}

```

## disassembly

```asm
0x18002cf6c  mov     [rsp+arg_0], rbx
0x18002cf71  mov     [rsp+arg_8], rsi
0x18002cf76  push    rdi
0x18002cf77  sub     rsp, 20h
0x18002cf7b  xor     ebx, ebx
0x18002cf7d  cmp     cs:byte_18014B2D0, bl
0x18002cf83  jnz     loc_18002D205
0x18002cf89  mov     cs:byte_18014B2D0, 1
0x18002cf90  mov     cs:?g_fInShutDown@@3HA, 1; int g_fInShutDown
0x18002cf9a  cmp     cs:?g_fClassInitFailed@@3_NA, bl; bool g_fClassInitFailed
0x18002cfa0  jz      short loc_18002CFA9
0x18002cfa2  mov     cs:?g_fClassInitCalled@@3_NA, 1; bool g_fClassInitCalled
0x18002cfa9  call    ?EnsureTlsData@@YAPEAUTLSDATA@@XZ; EnsureTlsData(void)
0x18002cfae  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x18002cfb4  call    cs:__imp_TlsGetValue
0x18002cfba  mov     rsi, rax
0x18002cfbd  mov     rdi, cs:?g_ptlsdata@@3PEAUTLSDATA@@EA; TLSDATA * g_ptlsdata
0x18002cfc4  jmp     short loc_18002CFE6
0x18002cfc6  cmp     rdi, rsi
0x18002cfc9  jz      short loc_18002CFDA
0x18002cfcb  cmp     [rdi+50h], ebx
0x18002cfce  jz      short loc_18002CFDA
0x18002cfd0  mov     cs:?g_fBadShutDown@@3HA, 1; int g_fBadShutDown
0x18002cfda  mov     rcx, rdi; this
0x18002cfdd  call    ?clear@TLSDATA@@QEAAXXZ; TLSDATA::clear(void)
0x18002cfe2  mov     rdi, [rdi+28h]
0x18002cfe6  test    rdi, rdi
0x18002cfe9  jnz     short loc_18002CFC6
0x18002cfeb  cmp     cs:?g_fBadShutDown@@3HA, ebx; int g_fBadShutDown
0x18002cff1  jz      short loc_18002D005
0x18002cff3  lea     rcx, aAtLeastOneThre; "At least one thread was killed while ex"...
0x18002cffa  call    cs:__imp_OutputDebugStringW
0x18002d000  jmp     loc_18002D1EB
0x18002d005  call    ?TerminateMimeDwn@@YAXXZ; TerminateMimeDwn(void)
0x18002d00a  inc     cs:?s_lInGC@Base@@0KA; ulong Base::s_lInGC
0x18002d010  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x18002d016  call    cs:__imp_TlsGetValue
0x18002d01c  mov     cs:?s_ptlsCheckZeroList@Base@@0PEAUTLSDATA@@EA, rax; TLSDATA * Base::s_ptlsCheckZeroList
0x18002d023  mov     cs:?s_ptlsGC@Base@@0PEAUTLSDATA@@EA, rax; TLSDATA * Base::s_ptlsGC
0x18002d02a  mov     cs:?s_fInFreeObjects@Base@@0_NA, 1; bool Base::s_fInFreeObjects
0x18002d031  cmp     cs:?g_fClassInitCalled@@3_NA, bl; bool g_fClassInitCalled
0x18002d037  jz      short loc_18002D03E
0x18002d039  call    ?classExit@DOMNode@@SAXXZ; DOMNode::classExit(void)
0x18002d03e  call    ?ClearReferences@@YAXXZ; ClearReferences(void)
0x18002d043  mov     rcx, cs:?s_hInstance@Resources@@2PEAUHINSTANCE__@@EA; hLibModule
0x18002d04a  test    rcx, rcx
0x18002d04d  jz      short loc_18002D065
0x18002d04f  cmp     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x18002d056  jz      short loc_18002D065
0x18002d058  call    cs:__imp_FreeLibrary
0x18002d05e  mov     cs:?s_hInstance@Resources@@2PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * Resources::s_hInstance
0x18002d065  call    ?classExit@Exception@@SAXXZ; Exception::classExit(void)
0x18002d06a  call    ?FinishFreeObjects@Base@@SAXXZ; Base::FinishFreeObjects(void)
0x18002d06f  jmp     loc_18002D107
0x18002d074  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x18002d07a  call    cs:__imp_TlsGetValue
0x18002d080  mov     rbx, rax
0x18002d083  cmp     dword ptr [rax+54h], 0C00000FDh
0x18002d08a  jnz     short loc_18002D105
0x18002d08c  call    cs:__imp__resetstkoflw
0x18002d092  test    eax, eax
0x18002d094  jnz     short loc_18002D0E7
0x18002d096  mov     rcx, cs:?g_pMutexGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexGC
0x18002d09d  test    rcx, rcx
0x18002d0a0  jz      short loc_18002D0B4
0x18002d0a2  cmp     [rcx+50h], rbx
0x18002d0a6  jnz     short loc_18002D0B4
0x18002d0a8  mov     rax, [rcx]
0x18002d0ab  mov     rax, [rax+20h]
0x18002d0af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d0b4  mov     rcx, cs:?g_pMutexFullGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexFullGC
0x18002d0bb  test    rcx, rcx
0x18002d0be  jz      short loc_18002D0D2
0x18002d0c0  cmp     [rcx+50h], rbx
0x18002d0c4  jnz     short loc_18002D0D2
0x18002d0c6  mov     rax, [rcx]
0x18002d0c9  mov     rax, [rax+20h]
0x18002d0cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d0d2  xor     r9d, r9d; lpArguments
0x18002d0d5  xor     r8d, r8d; nNumberOfArguments
0x18002d0d8  xor     edx, edx; dwExceptionFlags
0x18002d0da  mov     ecx, 0C00000FDh; dwExceptionCode
0x18002d0df  call    cs:__imp_RaiseException
0x18002d0e5  jmp     short loc_18002D105
0x18002d0e7  mov     rax, [rbx+60h]
0x18002d0eb  mov     [rbx+68h], rax
0x18002d0ef  lea     rax, ?s_cexpOutOfStack@Exception@@2V_CodebaseException@@B; _CodebaseException const Exception::s_cexpOutOfStack
0x18002d0f6  mov     [rbx+60h], rax
0x18002d0fa  mov     dword ptr [rbx+54h], 800703E9h
0x18002d101  mov     byte ptr [rbx+78h], 0
0x18002d105  xor     ebx, ebx
0x18002d107  cmp     cs:?g_fClassInitCalled@@3_NA, bl; bool g_fClassInitCalled
0x18002d10d  jz      loc_18002D1EB
0x18002d113  mov     rdi, cs:?s_pFreeList@NodeManager@@0PEAV1@EA; NodeManager * NodeManager::s_pFreeList
0x18002d11a  test    rdi, rdi
0x18002d11d  jz      short loc_18002D137
0x18002d11f  mov     rcx, rdi
0x18002d122  mov     rdi, [rdi+0B8h]
0x18002d129  mov     rax, [rcx]
0x18002d12c  mov     rax, [rax+10h]
0x18002d130  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d135  jmp     short loc_18002D11A
0x18002d137  mov     rcx, cs:?s_pDefaultVMM@@3PEAVVMManager@@EA; VMManager * s_pDefaultVMM
0x18002d13e  test    rcx, rcx
0x18002d141  jz      short loc_18002D155
0x18002d143  add     rcx, 8; this
0x18002d147  call    ?Release@_xunknown@@QEAAKXZ; _xunknown::Release(void)
0x18002d14c  test    eax, eax
0x18002d14e  jz      short loc_18002D155
0x18002d150  call    ?record@failure_tracing@@SAXXZ; failure_tracing::record(void)
0x18002d155  jmp     loc_18002D1EB
0x18002d15a  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x18002d160  call    cs:__imp_TlsGetValue
0x18002d166  mov     rbx, rax
0x18002d169  cmp     dword ptr [rax+54h], 0C00000FDh
0x18002d170  jnz     short loc_18002D1EB
0x18002d172  call    cs:__imp__resetstkoflw
0x18002d178  test    eax, eax
0x18002d17a  jnz     short loc_18002D1CD
0x18002d17c  mov     rcx, cs:?g_pMutexGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexGC
0x18002d183  test    rcx, rcx
0x18002d186  jz      short loc_18002D19A
0x18002d188  cmp     [rcx+50h], rbx
0x18002d18c  jnz     short loc_18002D19A
0x18002d18e  mov     rax, [rcx]
0x18002d191  mov     rax, [rax+20h]
0x18002d195  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d19a  mov     rcx, cs:?g_pMutexFullGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexFullGC
0x18002d1a1  test    rcx, rcx
0x18002d1a4  jz      short loc_18002D1B8
0x18002d1a6  cmp     [rcx+50h], rbx
0x18002d1aa  jnz     short loc_18002D1B8
0x18002d1ac  mov     rax, [rcx]
0x18002d1af  mov     rax, [rax+20h]
0x18002d1b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d1b8  xor     r9d, r9d; lpArguments
0x18002d1bb  xor     r8d, r8d; nNumberOfArguments
0x18002d1be  xor     edx, edx; dwExceptionFlags
0x18002d1c0  mov     ecx, 0C00000FDh; dwExceptionCode
0x18002d1c5  call    cs:__imp_RaiseException
0x18002d1cb  jmp     short loc_18002D1EB
0x18002d1cd  mov     rax, [rbx+60h]
0x18002d1d1  mov     [rbx+68h], rax
0x18002d1d5  lea     rax, ?s_cexpOutOfStack@Exception@@2V_CodebaseException@@B; _CodebaseException const Exception::s_cexpOutOfStack
0x18002d1dc  mov     [rbx+60h], rax
0x18002d1e0  mov     dword ptr [rbx+54h], 800703E9h
0x18002d1e7  mov     byte ptr [rbx+78h], 0
0x18002d1eb  call    ?MTExit@@YAXXZ; MTExit(void)
0x18002d1f0  mov     cs:?g_fHasExited@@3_NA, 1; bool g_fHasExited
0x18002d1f7  lea     rax, ?Error@ReplFactory@@UEAAJPEAUIXMLNodeSource@@JGPEAPEAU_XML_NODE_INFO@@@Z; ReplFactory::Error(IXMLNodeSource *,long,ushort,_XML_NODE_INFO * *)
0x18002d1fe  mov     cs:?g_pfnEntry@@3P6APEAUTLSDATA@@XZEA, rax; TLSDATA * (*g_pfnEntry)(void)
0x18002d205  mov     rbx, [rsp+28h+arg_0]
0x18002d20a  mov     rsi, [rsp+28h+arg_8]
0x18002d20f  add     rsp, 20h
0x18002d213  pop     rdi
0x18002d214  retn
0x180103628  push    rbp
0x18010362a  sub     rsp, 20h
0x18010362e  mov     rbp, rdx
0x180103631  xor     edx, edx; bool
0x180103633  call    ?fillException@Exception@@SAHPEAU_EXCEPTION_POINTERS@@_N@Z; Exception::fillException(_EXCEPTION_POINTERS *,bool)
0x180103638  nop
0x180103639  add     rsp, 20h
0x18010363d  pop     rbp
0x18010363e  retn
0x180103640  push    rbp
0x180103642  sub     rsp, 20h
0x180103646  mov     rbp, rdx
0x180103649  xor     edx, edx; bool
0x18010364b  call    ?fillException@Exception@@SAHPEAU_EXCEPTION_POINTERS@@_N@Z; Exception::fillException(_EXCEPTION_POINTERS *,bool)
0x180103650  nop
0x180103651  add     rsp, 20h
0x180103655  pop     rbp
0x180103656  retn
```
