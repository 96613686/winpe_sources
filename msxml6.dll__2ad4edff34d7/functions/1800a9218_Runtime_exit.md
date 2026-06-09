# Runtime_exit

- ea: `0x1800a9218`
- end: `0x1800a93bb`
- name: `Runtime_exit`
- size: `419`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x1800b3600`

## callees

- `0x180009490`
- `0x180090ab0`
- `0x18009dedc`
- `0x18009e92c`
- `0x18009f718`
- `0x1800a3e04`
- `0x1800a9218`
- `0x1800bd8b4`
- `0x1800d60dc`
- `0x1800d79fc`
- `0x1800dbb00`
- `0x1801039a8`
- `0x18014185c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800a9380`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800a9380`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a9294`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a9294`

## pseudocode

```c
void Runtime_exit()
{
  __int64 v0; // rdi
  TLSDATA *v1; // rax
  TLSDATA *v2; // rbx

  if ( !fRuntimeExitCalled )
  {
    fRuntimeExitCalled = 1;
    g_fInShutDown = 1;
    if ( g_fClassInitFailed )
      g_fClassInitCalled = 1;
    v0 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + tls_index);
    if ( !*(_QWORD *)(v0 + 8) )
    {
      v1 = AllocTlsData();
      *(_QWORD *)(v0 + 8) = v1;
      if ( !v1 )
      {
        v2 = g_ptlsdataExtra;
        g_ptlsdataExtra = 0;
        v2->_dwTID = GetCurrentThreadId();
        *(_QWORD *)(v0 + 8) = v2;
      }
    }
    Name::classExit();
    RegexCharClass::classExit();
    assign(&RegexMatch::_empty._p, 0);
    assign(&RegexPrefix::_empty._p, 0);
    XMLNames::classExit();
    XSLTKeywords::classExit();
    if ( SchemaNames::names._p )
      assign(&SchemaNames::names._p, 0);
    _MXItem::classExit();
    if ( DecimalFormatSymbols::s_defaultInstance._p )
      assign(&DecimalFormatSymbols::s_defaultInstance._p, 0);
    if ( DOMError::s_pSuccessParseErrorObj._p )
      assign(&DOMError::s_pSuccessParseErrorObj._p, 0);
    if ( MXItemCollection::s_rEmpty._p )
      assign(&MXItemCollection::s_rEmpty._p, 0);
    if ( MXStringCollection::s_rEmpty._p )
      assign(&MXStringCollection::s_rEmpty._p, 0);
    XsdBuilder::classExit();
    if ( NullElement::s_rNullElement._p )
      assign(&NullElement::s_rNullElement._p, 0);
    if ( Resources::s_hInstance )
    {
      if ( Resources::s_hInstance != g_hInstance )
      {
        FreeLibrary((HMODULE)Resources::s_hInstance);
        Resources::s_hInstance = 0;
      }
    }
    Exception::classExit();
    MTExit();
    g_fHasExited = 1;
  }
}

```

## disassembly

```asm
0x1800a9218  mov     [rsp+arg_0], rbx
0x1800a921d  mov     [rsp+arg_8], rdi
0x1800a9222  push    r14
0x1800a9224  sub     rsp, 20h
0x1800a9228  cmp     cs:fRuntimeExitCalled, 0
0x1800a922f  jnz     loc_1800A93AA
0x1800a9235  mov     cs:fRuntimeExitCalled, 1
0x1800a923c  mov     cs:?g_fInShutDown@@3HA, 1; int g_fInShutDown
0x1800a9246  cmp     cs:?g_fClassInitFailed@@3_NA, 0; bool g_fClassInitFailed
0x1800a924d  jz      short loc_1800A9256
0x1800a924f  mov     cs:?g_fClassInitCalled@@3_NC, 1; bool volatile g_fClassInitCalled
0x1800a9256  mov     ecx, cs:_tls_index
0x1800a925c  mov     rax, gs:58h
0x1800a9265  mov     r14d, 8
0x1800a926b  mov     rdi, [rax+rcx*8]
0x1800a926f  mov     rax, [rdi+r14]
0x1800a9273  test    rax, rax
0x1800a9276  jnz     short loc_1800A92A1
0x1800a9278  call    ?AllocTlsData@@YAPEAUTLSDATA@@XZ; AllocTlsData(void)
0x1800a927d  mov     [rdi+r14], rax
0x1800a9281  test    rax, rax
0x1800a9284  jnz     short loc_1800A92A1
0x1800a9286  mov     rbx, cs:?g_ptlsdataExtra@@3PEAUTLSDATA@@EA; TLSDATA * g_ptlsdataExtra
0x1800a928d  mov     cs:?g_ptlsdataExtra@@3PEAUTLSDATA@@EA, rax; TLSDATA * g_ptlsdataExtra
0x1800a9294  call    cs:__imp_GetCurrentThreadId
0x1800a929a  mov     [rbx+24h], eax
0x1800a929d  mov     [rdi+r14], rbx
0x1800a92a1  call    ?classExit@Name@@SAXXZ; Name::classExit(void)
0x1800a92a6  call    ?classExit@RegexCharClass@@SAXXZ; RegexCharClass::classExit(void)
0x1800a92ab  xor     edx, edx; pref
0x1800a92ad  lea     rcx, ?_empty@RegexMatch@@2V?$_reference@VRegexMatch@@@@A; ppref
0x1800a92b4  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800a92b9  xor     edx, edx; pref
0x1800a92bb  lea     rcx, ?_empty@RegexPrefix@@2V?$_reference@VRegexPrefix@@@@A; ppref
0x1800a92c2  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800a92c7  call    ?classExit@XMLNames@@SAXXZ; XMLNames::classExit(void)
0x1800a92cc  call    ?classExit@XSLTKeywords@@SAXXZ; XSLTKeywords::classExit(void)
0x1800a92d1  cmp     cs:?names@SchemaNames@@2V?$_reference@V?$_array@V?$_reference@VName@@@@@@@@A._p, 0; _reference<_array<_reference<Name>>> SchemaNames::names ...
0x1800a92d9  jz      short loc_1800A92E9
0x1800a92db  xor     edx, edx; pref
0x1800a92dd  lea     rcx, ?names@SchemaNames@@2V?$_reference@V?$_array@V?$_reference@VName@@@@@@@@A; ppref
0x1800a92e4  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800a92e9  call    ?classExit@_MXItem@@SAXXZ; _MXItem::classExit(void)
0x1800a92ee  cmp     cs:?s_defaultInstance@DecimalFormatSymbols@@0V?$_reference@VDecimalFormatSymbols@@@@A._p, 0; _reference<DecimalFormatSymbols> DecimalFormatSymbols::s_defaultInstance ...
0x1800a92f6  jz      short loc_1800A9306
0x1800a92f8  xor     edx, edx; pref
0x1800a92fa  lea     rcx, ?s_defaultInstance@DecimalFormatSymbols@@0V?$_reference@VDecimalFormatSymbols@@@@A; ppref
0x1800a9301  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800a9306  cmp     cs:?s_pSuccessParseErrorObj@DOMError@@2V?$_reference@VDOMError@@@@A._p, 0; _reference<DOMError> DOMError::s_pSuccessParseErrorObj ...
0x1800a930e  jz      short loc_1800A931E
0x1800a9310  xor     edx, edx; pref
0x1800a9312  lea     rcx, ?s_pSuccessParseErrorObj@DOMError@@2V?$_reference@VDOMError@@@@A; ppref
0x1800a9319  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800a931e  cmp     cs:?s_rEmpty@MXItemCollection@@1V?$_reference@UISchemaItemCollection@@@@A._p, 0; _reference<ISchemaItemCollection> MXItemCollection::s_rEmpty ...
0x1800a9326  jz      short loc_1800A9336
0x1800a9328  xor     edx, edx; pref
0x1800a932a  lea     rcx, ?s_rEmpty@MXItemCollection@@1V?$_reference@UISchemaItemCollection@@@@A; ppref
0x1800a9331  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800a9336  cmp     cs:?s_rEmpty@MXStringCollection@@1V?$_reference@UISchemaStringCollection@@@@A._p, 0; _reference<ISchemaStringCollection> MXStringCollection::s_rEmpty ...
0x1800a933e  jz      short loc_1800A934E
0x1800a9340  xor     edx, edx; pref
0x1800a9342  lea     rcx, ?s_rEmpty@MXStringCollection@@1V?$_reference@UISchemaStringCollection@@@@A; ppref
0x1800a9349  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800a934e  call    ?classExit@XsdBuilder@@SAXXZ; XsdBuilder::classExit(void)
0x1800a9353  cmp     cs:?s_rNullElement@NullElement@@1V?$_reference@VSchemaElement@@@@A._p, 0; _reference<SchemaElement> NullElement::s_rNullElement ...
0x1800a935b  jz      short loc_1800A936B
0x1800a935d  xor     edx, edx; pref
0x1800a935f  lea     rcx, ?s_rNullElement@NullElement@@1V?$_reference@VSchemaElement@@@@A; ppref
0x1800a9366  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800a936b  mov     rcx, cs:?s_hInstance@Resources@@2PEAUHINSTANCE__@@EA; hLibModule
0x1800a9372  test    rcx, rcx
0x1800a9375  jz      short loc_1800A9391
0x1800a9377  cmp     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x1800a937e  jz      short loc_1800A9391
0x1800a9380  call    cs:__imp_FreeLibrary
0x1800a9386  mov     cs:?s_hInstance@Resources@@2PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * Resources::s_hInstance
0x1800a9391  call    ?classExit@Exception@@SAXXZ; Exception::classExit(void)
0x1800a9396  jmp     short loc_1800A939E
0x1800a9398  call    ?exceptionCatch@Exception@@SAXXZ; Exception::exceptionCatch(void)
0x1800a939d  nop
0x1800a939e  call    ?MTExit@@YAXXZ; MTExit(void)
0x1800a93a3  mov     cs:?g_fHasExited@@3_NA, 1; bool g_fHasExited
0x1800a93aa  mov     rbx, [rsp+28h+arg_0]
0x1800a93af  mov     rdi, [rsp+28h+arg_8]
0x1800a93b4  add     rsp, 20h
0x1800a93b8  pop     r14
0x1800a93ba  retn
0x18017e438  push    rbp
0x18017e43a  sub     rsp, 20h
0x18017e43e  mov     rbp, rdx
0x18017e441  call    ?fillException@Exception@@SAHPEAU_EXCEPTION_POINTERS@@@Z; Exception::fillException(_EXCEPTION_POINTERS *)
0x18017e446  nop
0x18017e447  add     rsp, 20h
0x18017e44b  pop     rbp
0x18017e44c  retn
```
