# Runtime_exit()

- ea: `0x10074bea`
- end: `0x10074d7e`
- name: `_Runtime_exit@0`
- size: `404`
- prototype: `_DWORD __stdcall()`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x1005b2f0`

## callees

- `0x1003fb13`
- `0x10057ae5`
- `0x1006bff0`
- `0x10074bea`
- `0x10076810`
- `0x10077995`
- `0x100779f5`
- `0x10077a4b`
- `0x1007a199`
- `0x100815d7`
- `0x1008860c`
- `0x100bf227`
- `0x100e54dc`
- `0x1010d671`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x10074d33`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x10074d33`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10074c57`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10074c57`

## pseudocode

```c
void __stdcall Runtime_exit()
{
  int v0; // edi
  TLSDATA *v1; // eax
  TLSDATA *v2; // esi

  if ( !fRuntimeExitCalled )
  {
    fRuntimeExitCalled = 1;
    g_fInShutDown = 1;
    if ( g_fClassInitFailed )
      g_fClassInitCalled = 1;
    v0 = *((_DWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + _tls_index);
    if ( !*(_DWORD *)(v0 + 4) )
    {
      v1 = AllocTlsData();
      *(_DWORD *)(v0 + 4) = v1;
      if ( !v1 )
      {
        v2 = g_ptlsdataExtra;
        g_ptlsdataExtra = 0;
        v2->_dwTID = GetCurrentThreadId();
        *(_DWORD *)(v0 + 4) = v2;
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
        FreeLibrary(Resources::s_hInstance);
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
0x10074bea  push    8
0x10074bec  push    offset stru_10174098
0x10074bf1  call    __SEH_prolog4
0x10074bf6  cmp     fRuntimeExitCalled, 0
0x10074bfd  jnz     loc_10074D6E
0x10074c03  mov     fRuntimeExitCalled, 1
0x10074c0a  mov     ?g_fInShutDown@@3HA, 1; int g_fInShutDown
0x10074c14  cmp     ?g_fClassInitFailed@@3_NA, 0; bool g_fClassInitFailed
0x10074c1b  jz      short loc_10074C24
0x10074c1d  mov     ?g_fClassInitCalled@@3_NC, 1; bool volatile g_fClassInitCalled
0x10074c24  mov     ecx, __tls_index
0x10074c2a  mov     eax, large fs:2Ch
0x10074c30  mov     edi, [eax+ecx*4]
0x10074c33  mov     eax, [edi+4]
0x10074c39  test    eax, eax
0x10074c3b  jnz     short loc_10074C66
0x10074c3d  call    ?AllocTlsData@@YGPAUTLSDATA@@XZ; AllocTlsData(void)
0x10074c42  mov     [edi+4], eax
0x10074c48  test    eax, eax
0x10074c4a  jnz     short loc_10074C66
0x10074c4c  mov     esi, ?g_ptlsdataExtra@@3PAUTLSDATA@@A; TLSDATA * g_ptlsdataExtra
0x10074c52  mov     ?g_ptlsdataExtra@@3PAUTLSDATA@@A, eax; TLSDATA * g_ptlsdataExtra
0x10074c57  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x10074c5d  mov     [esi+18h], eax
0x10074c60  mov     [edi+4], esi
0x10074c66  mov     [ebp+ms_exc.registration.TryLevel], 0
0x10074c6d  call    ?classExit@Name@@SGXXZ; Name::classExit(void)
0x10074c72  call    ?classExit@RegexCharClass@@SGXXZ; RegexCharClass::classExit(void)
0x10074c77  xor     edx, edx; pref
0x10074c79  mov     ecx, offset ?_empty@RegexMatch@@2V?$_reference@VRegexMatch@@@@A; ppref
0x10074c7e  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x10074c83  xor     edx, edx; pref
0x10074c85  mov     ecx, offset ?_empty@RegexPrefix@@2V?$_reference@VRegexPrefix@@@@A; ppref
0x10074c8a  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x10074c8f  call    ?classExit@XMLNames@@SGXXZ; XMLNames::classExit(void)
0x10074c94  call    ?classExit@XSLTKeywords@@SGXXZ; XSLTKeywords::classExit(void)
0x10074c99  cmp     ?names@SchemaNames@@2V?$_reference@V?$_array@V?$_reference@VName@@@@@@@@A._p, 0; _reference<_array<_reference<Name>>> SchemaNames::names ...
0x10074ca0  jz      short loc_10074CAE
0x10074ca2  xor     edx, edx; pref
0x10074ca4  mov     ecx, offset ?names@SchemaNames@@2V?$_reference@V?$_array@V?$_reference@VName@@@@@@@@A; ppref
0x10074ca9  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x10074cae  call    ?classExit@_MXItem@@SGXXZ; _MXItem::classExit(void)
0x10074cb3  cmp     ?s_defaultInstance@DecimalFormatSymbols@@0V?$_reference@VDecimalFormatSymbols@@@@A._p, 0; _reference<DecimalFormatSymbols> DecimalFormatSymbols::s_defaultInstance ...
0x10074cba  jz      short loc_10074CC8
0x10074cbc  xor     edx, edx; pref
0x10074cbe  mov     ecx, offset ?s_defaultInstance@DecimalFormatSymbols@@0V?$_reference@VDecimalFormatSymbols@@@@A; ppref
0x10074cc3  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x10074cc8  cmp     ?s_pSuccessParseErrorObj@DOMError@@2V?$_reference@VDOMError@@@@A._p, 0; _reference<DOMError> DOMError::s_pSuccessParseErrorObj ...
0x10074ccf  jz      short loc_10074CDD
0x10074cd1  xor     edx, edx; pref
0x10074cd3  mov     ecx, offset ?s_pSuccessParseErrorObj@DOMError@@2V?$_reference@VDOMError@@@@A; ppref
0x10074cd8  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x10074cdd  cmp     ?s_rEmpty@MXItemCollection@@1V?$_reference@UISchemaItemCollection@@@@A._p, 0; _reference<ISchemaItemCollection> MXItemCollection::s_rEmpty ...
0x10074ce4  jz      short loc_10074CF2
0x10074ce6  xor     edx, edx; pref
0x10074ce8  mov     ecx, offset ?s_rEmpty@MXItemCollection@@1V?$_reference@UISchemaItemCollection@@@@A; ppref
0x10074ced  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x10074cf2  cmp     ?s_rEmpty@MXStringCollection@@1V?$_reference@UISchemaStringCollection@@@@A._p, 0; _reference<ISchemaStringCollection> MXStringCollection::s_rEmpty ...
0x10074cf9  jz      short loc_10074D07
0x10074cfb  xor     edx, edx; pref
0x10074cfd  mov     ecx, offset ?s_rEmpty@MXStringCollection@@1V?$_reference@UISchemaStringCollection@@@@A; ppref
0x10074d02  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x10074d07  call    ?classExit@XsdBuilder@@SGXXZ; XsdBuilder::classExit(void)
0x10074d0c  cmp     ?s_rNullElement@NullElement@@1V?$_reference@VSchemaElement@@@@A._p, 0; _reference<SchemaElement> NullElement::s_rNullElement ...
0x10074d13  jz      short loc_10074D21
0x10074d15  xor     edx, edx; pref
0x10074d17  mov     ecx, offset ?s_rNullElement@NullElement@@1V?$_reference@VSchemaElement@@@@A; ppref
0x10074d1c  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x10074d21  mov     eax, ?s_hInstance@Resources@@2PAUHINSTANCE__@@A; HINSTANCE__ * Resources::s_hInstance
0x10074d26  test    eax, eax
0x10074d28  jz      short loc_10074D43
0x10074d2a  cmp     eax, ?g_hInstance@@3PAUHINSTANCE__@@A; HINSTANCE__ * g_hInstance
0x10074d30  jz      short loc_10074D43
0x10074d32  push    eax; hLibModule
0x10074d33  call    ds:__imp__FreeLibrary@4; FreeLibrary(x)
0x10074d39  mov     ?s_hInstance@Resources@@2PAUHINSTANCE__@@A, 0; HINSTANCE__ * Resources::s_hInstance
0x10074d43  call    ?classExit@Exception@@SGXXZ; Exception::classExit(void)
0x10074d48  jmp     short loc_10074D5B
0x10074d4a  mov     ecx, [ebp+ms_exc.exc_ptr]; ep
0x10074d4d  call    ?fillException@Exception@@SGHPAU_EXCEPTION_POINTERS@@@Z; Exception::fillException(_EXCEPTION_POINTERS *)
0x10074d52  retn
0x10074d53  mov     esp, [ebp+ms_exc.old_esp]
0x10074d56  call    ?exceptionCatch@Exception@@SGXXZ; Exception::exceptionCatch(void)
0x10074d5b  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x10074d62  call    ?MTExit@@YGXXZ; MTExit(void)
0x10074d67  mov     ?g_fHasExited@@3_NA, 1; bool g_fHasExited
0x10074d6e  mov     ecx, [ebp+ms_exc.registration.Next]
0x10074d71  mov     large fs:0, ecx
0x10074d78  pop     ecx
0x10074d79  pop     edi
0x10074d7a  pop     esi
0x10074d7b  pop     ebx
0x10074d7c  leave
0x10074d7d  retn
```
