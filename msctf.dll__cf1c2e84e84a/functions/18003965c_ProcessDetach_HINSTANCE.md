# ProcessDetach(HINSTANCE__ *)

- ea: `0x18003965c`
- end: `0x18003989d`
- name: `?ProcessDetach@@YAXPEAUHINSTANCE__@@@Z`
- size: `577`
- prototype: `void __fastcall(HINSTANCE)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180081014`

## callees

- `0x1800139a4`
- `0x180039430`
- `0x1800394c0`
- `0x1800394f0`
- `0x1800395cc`
- `0x18003965c`
- `0x18003a344`
- `0x18003a3d4`
- `0x18008ced0`
- `0x180106a60`
- `0x18010a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180039811`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003982c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180039847`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180039811`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003982c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180039847`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x1800396c2`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18003979d`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x1800397b3`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x1800396c2`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18003979d`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x1800397b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800397d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800397ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800397d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800397ef`
- `api-ms-win-core-fibers-l1-1-0!FlsFree` at `0x180039787`
- `api-ms-win-core-fibers-l1-1-0!FlsFree` at `0x180039787`

## pseudocode

```c
void __fastcall ProcessDetach(HINSTANCE a1, __int64 a2, __int64 a3)
{
  CVoidStructArray *v3; // rbx
  __int64 v4; // rcx
  __int64 v5; // r8
  _BYTE v6[16]; // [rsp+30h] [rbp-48h] BYREF

  if ( (Microsoft_Windows_TSF_msctfEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(&Microsoft_Windows_TSF_msctf_Context, UninitMSCTFForProcess_Start, a3, 1, v6);
  wil::details::g_pfnTelemetryCallback = 0;
  UnregisterImeClass();
  TLS::InternalDestroyTLS();
  if ( TLS::dwTLSIndex != -1 )
  {
    TlsFree(TLS::dwTLSIndex);
    TLS::dwTLSIndex = -1;
  }
  if ( qword_180141218 )
  {
    (**(void (__fastcall ***)(CUIFColorTable *, __int64))qword_180141218)(qword_180141218, 1);
    qword_180141218 = 0;
  }
  if ( qword_180141220 )
  {
    (**(void (__fastcall ***)(CUIFColorTable *, __int64))qword_180141220)(qword_180141220, 1);
    qword_180141220 = 0;
  }
  DoneUIFUtil();
  v3 = g_pPropCache;
  if ( g_pPropCache )
  {
    v4 = *((_QWORD *)g_pPropCache + 1);
    *(_QWORD *)g_pPropCache = &CStructArray<char>::`vftable';
    cicMemFree(v4);
    cicMemFree(v3);
  }
  g_pPropCache = 0;
  if ( g_hMlang )
  {
    g_hMlang = 0;
    g_pfnGetGlobalFontLinkObject = 0;
  }
  if ( g_prgModuleRefs )
  {
    (**(void (__fastcall ***)(CVoidStructArray *, __int64))g_prgModuleRefs)(g_prgModuleRefs, 1);
    g_prgModuleRefs = 0;
  }
  UninitProcess();
  if ( g_dwFLSIndex != -1 )
  {
    FlsFree(g_dwFLSIndex);
    g_dwFLSIndex = -1;
  }
  if ( g_dwTLSIndex != -1 )
  {
    TlsFree(g_dwTLSIndex);
    g_dwTLSIndex = -1;
  }
  if ( g_dwTLSIndexForFLS != -1 )
  {
    TlsFree(g_dwTLSIndexForFLS);
    g_dwTLSIndexForFLS = -1;
  }
  CCategoryMgr::UninitGlobal();
  if ( CCicSecAttr::s_psd )
  {
    LocalFree(CCicSecAttr::s_psd);
    CCicSecAttr::s_psd = 0;
    CCicSecAttr::s_fInit = 0;
  }
  if ( CCicSecAttr::s_psdGR )
  {
    LocalFree(CCicSecAttr::s_psdGR);
    CCicSecAttr::s_psdGR = 0;
    CCicSecAttr::s_fInitGR = 0;
  }
  if ( dword_180140688 )
  {
    DeleteCriticalSection(&g_cs);
    dword_180140688 = 0;
  }
  if ( dword_180140650 )
  {
    DeleteCriticalSection(&g_csInDllMain);
    dword_180140650 = 0;
  }
  if ( dword_1801406B8 )
  {
    DeleteCriticalSection(&g_csDelayLoad);
    dword_1801406B8 = 0;
  }
  if ( (Microsoft_Windows_TSF_msctfEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(&Microsoft_Windows_TSF_msctf_Context, UninitMSCTFForProcess_End, v5, 1, v6);
  McGenEventUnregister_EventUnregister();
  g_fDllProcessDetached = 1;
}

```

## disassembly

```asm
0x18003965c  push    rbx
0x18003965e  push    rbp
0x18003965f  push    rsi
0x180039660  push    rdi
0x180039661  sub     rsp, 58h
0x180039665  mov     rax, cs:__security_cookie
0x18003966c  xor     rax, rsp
0x18003966f  mov     [rsp+78h+var_38], rax
0x180039674  mov     ebp, 1
0x180039679  test    cs:Microsoft_Windows_TSF_msctfEnableBits, bpl
0x180039680  jz      short loc_1800396A2
0x180039682  lea     rax, [rsp+78h+var_48]
0x180039687  mov     r9d, ebp
0x18003968a  lea     rdx, UninitMSCTFForProcess_Start
0x180039691  mov     [rsp+78h+var_58], rax
0x180039696  lea     rcx, Microsoft_Windows_TSF_msctf_Context
0x18003969d  call    McGenEventWrite_EventWriteTransfer
0x1800396a2  xor     edi, edi
0x1800396a4  mov     cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA, rdi
0x1800396ab  call    ?UnregisterImeClass@@YAXXZ; UnregisterImeClass(void)
0x1800396b0  call    ?InternalDestroyTLS@TLS@@CAHXZ; TLS::InternalDestroyTLS(void)
0x1800396b5  mov     ecx, cs:?dwTLSIndex@TLS@@0KA; dwTlsIndex
0x1800396bb  or      esi, 0FFFFFFFFh
0x1800396be  cmp     ecx, esi
0x1800396c0  jz      short loc_1800396CE
0x1800396c2  call    cs:__imp_TlsFree
0x1800396c8  mov     cs:?dwTLSIndex@TLS@@0KA, esi; ulong TLS::dwTLSIndex
0x1800396ce  mov     rcx, cs:qword_180141218
0x1800396d5  test    rcx, rcx
0x1800396d8  jz      short loc_1800396EE
0x1800396da  mov     rax, [rcx]
0x1800396dd  mov     edx, ebp
0x1800396df  mov     rax, [rax]
0x1800396e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800396e7  mov     cs:qword_180141218, rdi
0x1800396ee  mov     rcx, cs:qword_180141220
0x1800396f5  test    rcx, rcx
0x1800396f8  jz      short loc_18003970E
0x1800396fa  mov     rax, [rcx]
0x1800396fd  mov     edx, ebp
0x1800396ff  mov     rax, [rax]
0x180039702  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039707  mov     cs:qword_180141220, rdi
0x18003970e  call    ?DoneUIFUtil@@YAXXZ; DoneUIFUtil(void)
0x180039713  mov     rbx, cs:?g_pPropCache@@3PEAVCDispAttrPropCache@@EA; CDispAttrPropCache * g_pPropCache
0x18003971a  test    rbx, rbx
0x18003971d  jz      short loc_18003973A
0x18003971f  mov     rcx, [rbx+8]
0x180039723  lea     rax, ??_7?$CStructArray@D@@6B@; const CStructArray<char>::`vftable'
0x18003972a  mov     [rbx], rax
0x18003972d  call    cicMemFree
0x180039732  mov     rcx, rbx
0x180039735  call    cicMemFree
0x18003973a  cmp     cs:?g_hMlang@@3PEAUHINSTANCE__@@EA, rdi; HINSTANCE__ * g_hMlang
0x180039741  mov     cs:?g_pPropCache@@3PEAVCDispAttrPropCache@@EA, rdi; CDispAttrPropCache * g_pPropCache
0x180039748  jz      short loc_180039758
0x18003974a  mov     cs:?g_hMlang@@3PEAUHINSTANCE__@@EA, rdi; HINSTANCE__ * g_hMlang
0x180039751  mov     cs:?g_pfnGetGlobalFontLinkObject@@3P6AJPEAPEAUIMLangFontLink@@@ZEA, rdi; long (*g_pfnGetGlobalFontLinkObject)(IMLangFontLink * *)
0x180039758  mov     rcx, cs:?g_prgModuleRefs@@3PEAV?$CStructArray@Utag_MODULEREF@@@@EA; CStructArray<tag_MODULEREF> * g_prgModuleRefs
0x18003975f  test    rcx, rcx
0x180039762  jz      short loc_180039778
0x180039764  mov     rax, [rcx]
0x180039767  mov     edx, ebp
0x180039769  mov     rax, [rax]
0x18003976c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039771  mov     cs:?g_prgModuleRefs@@3PEAV?$CStructArray@Utag_MODULEREF@@@@EA, rdi; CStructArray<tag_MODULEREF> * g_prgModuleRefs
0x180039778  call    ?UninitProcess@@YAXXZ; UninitProcess(void)
0x18003977d  mov     ecx, cs:?g_dwFLSIndex@@3KA; dwFlsIndex
0x180039783  cmp     ecx, esi
0x180039785  jz      short loc_180039793
0x180039787  call    cs:__imp_FlsFree
0x18003978d  mov     cs:?g_dwFLSIndex@@3KA, esi; ulong g_dwFLSIndex
0x180039793  mov     ecx, cs:?g_dwTLSIndex@@3KA; dwTlsIndex
0x180039799  cmp     ecx, esi
0x18003979b  jz      short loc_1800397A9
0x18003979d  call    cs:__imp_TlsFree
0x1800397a3  mov     cs:?g_dwTLSIndex@@3KA, esi; ulong g_dwTLSIndex
0x1800397a9  mov     ecx, cs:?g_dwTLSIndexForFLS@@3KA; dwTlsIndex
0x1800397af  cmp     ecx, esi
0x1800397b1  jz      short loc_1800397BF
0x1800397b3  call    cs:__imp_TlsFree
0x1800397b9  mov     cs:?g_dwTLSIndexForFLS@@3KA, esi; ulong g_dwTLSIndexForFLS
0x1800397bf  call    ?UninitGlobal@CCategoryMgr@@SAXXZ; CCategoryMgr::UninitGlobal(void)
0x1800397c4  mov     rcx, cs:?s_psd@CCicSecAttr@@0PEAXEA; hMem
0x1800397cb  test    rcx, rcx
0x1800397ce  jz      short loc_1800397E3
0x1800397d0  call    cs:__imp_LocalFree
0x1800397d6  mov     cs:?s_psd@CCicSecAttr@@0PEAXEA, rdi; void * CCicSecAttr::s_psd
0x1800397dd  mov     cs:?s_fInit@CCicSecAttr@@0HA, edi; int CCicSecAttr::s_fInit
0x1800397e3  mov     rcx, cs:?s_psdGR@CCicSecAttr@@0PEAXEA; hMem
0x1800397ea  test    rcx, rcx
0x1800397ed  jz      short loc_180039802
0x1800397ef  call    cs:__imp_LocalFree
0x1800397f5  mov     cs:?s_psdGR@CCicSecAttr@@0PEAXEA, rdi; void * CCicSecAttr::s_psdGR
0x1800397fc  mov     cs:?s_fInitGR@CCicSecAttr@@0HA, edi; int CCicSecAttr::s_fInitGR
0x180039802  cmp     cs:dword_180140688, edi
0x180039808  jz      short loc_18003981D
0x18003980a  lea     rcx, ?g_cs@@3VCCicCriticalSectionStatic@@A; lpCriticalSection
0x180039811  call    cs:__imp_DeleteCriticalSection
0x180039817  mov     cs:dword_180140688, edi
0x18003981d  cmp     cs:dword_180140650, edi
0x180039823  jz      short loc_180039838
0x180039825  lea     rcx, ?g_csInDllMain@@3VCCicCriticalSectionStatic@@A; lpCriticalSection
0x18003982c  call    cs:__imp_DeleteCriticalSection
0x180039832  mov     cs:dword_180140650, edi
0x180039838  cmp     cs:dword_1801406B8, edi
0x18003983e  jz      short loc_180039853
0x180039840  lea     rcx, ?g_csDelayLoad@@3VCCicCriticalSectionStatic@@A; lpCriticalSection
0x180039847  call    cs:__imp_DeleteCriticalSection
0x18003984d  mov     cs:dword_1801406B8, edi
0x180039853  test    cs:Microsoft_Windows_TSF_msctfEnableBits, bpl
0x18003985a  jz      short loc_18003987C
0x18003985c  lea     rax, [rsp+78h+var_48]
0x180039861  mov     r9d, ebp
0x180039864  lea     rdx, UninitMSCTFForProcess_End
0x18003986b  mov     [rsp+78h+var_58], rax
0x180039870  lea     rcx, Microsoft_Windows_TSF_msctf_Context
0x180039877  call    McGenEventWrite_EventWriteTransfer
0x18003987c  call    McGenEventUnregister_EventUnregister
0x180039881  mov     cs:?g_fDllProcessDetached@@3HA, ebp; int g_fDllProcessDetached
0x180039887  mov     rcx, [rsp+78h+var_38]
0x18003988c  xor     rcx, rsp; StackCookie
0x18003988f  call    __security_check_cookie
0x180039894  add     rsp, 58h
0x180039898  pop     rdi
0x180039899  pop     rsi
0x18003989a  pop     rbp
0x18003989b  pop     rbx
0x18003989c  retn
```
