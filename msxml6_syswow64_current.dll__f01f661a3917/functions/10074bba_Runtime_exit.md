# Runtime_exit()

- ea: `0x10074bba`
- end: `0x10074d4e`
- name: `_Runtime_exit@0`
- size: `404`
- prototype: `_DWORD __stdcall()`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x1005b380`

## callees

- `0x1003fba3`
- `0x10057b75`
- `0x1006c080`
- `0x10074bba`
- `0x100767e0`
- `0x10077965`
- `0x100779c5`
- `0x10077a1b`
- `0x1007a159`
- `0x10081599`
- `0x100885cc`
- `0x100bf127`
- `0x100e53bc`
- `0x1010d551`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x10074d03`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x10074d03`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10074c27`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10074c27`

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
0x10074bba  push    8
0x10074bbc  push    offset stru_10173FA8
0x10074bc1  call    __SEH_prolog4
0x10074bc6  cmp     fRuntimeExitCalled, 0
0x10074bcd  jnz     loc_10074D3E
0x10074bd3  mov     fRuntimeExitCalled, 1
0x10074bda  mov     ?g_fInShutDown@@3HA, 1; int g_fInShutDown
0x10074be4  cmp     ?g_fClassInitFailed@@3_NA, 0; bool g_fClassInitFailed
0x10074beb  jz      short loc_10074BF4
0x10074bed  mov     ?g_fClassInitCalled@@3_NC, 1; bool volatile g_fClassInitCalled
0x10074bf4  mov     ecx, __tls_index
0x10074bfa  mov     eax, large fs:2Ch
0x10074c00  mov     edi, [eax+ecx*4]
0x10074c03  mov     eax, [edi+4]
0x10074c09  test    eax, eax
0x10074c0b  jnz     short loc_10074C36
0x10074c0d  call    ?AllocTlsData@@YGPAUTLSDATA@@XZ; AllocTlsData(void)
0x10074c12  mov     [edi+4], eax
0x10074c18  test    eax, eax
0x10074c1a  jnz     short loc_10074C36
0x10074c1c  mov     esi, ?g_ptlsdataExtra@@3PAUTLSDATA@@A; TLSDATA * g_ptlsdataExtra
0x10074c22  mov     ?g_ptlsdataExtra@@3PAUTLSDATA@@A, eax; TLSDATA * g_ptlsdataExtra
0x10074c27  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x10074c2d  mov     [esi+18h], eax
0x10074c30  mov     [edi+4], esi
0x10074c36  mov     [ebp+ms_exc.registration.TryLevel], 0
0x10074c3d  call    ?classExit@Name@@SGXXZ; Name::classExit(void)
0x10074c42  call    ?classExit@RegexCharClass@@SGXXZ; RegexCharClass::classExit(void)
0x10074c47  xor     edx, edx; pref
0x10074c49  mov     ecx, offset ?_empty@RegexMatch@@2V?$_reference@VRegexMatch@@@@A; ppref
0x10074c4e  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x10074c53  xor     edx, edx; pref
0x10074c55  mov     ecx, offset ?_empty@RegexPrefix@@2V?$_reference@VRegexPrefix@@@@A; ppref
0x10074c5a  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x10074c5f  call    ?classExit@XMLNames@@SGXXZ; XMLNames::classExit(void)
0x10074c64  call    ?classExit@XSLTKeywords@@SGXXZ; XSLTKeywords::classExit(void)
0x10074c69  cmp     ?names@SchemaNames@@2V?$_reference@V?$_array@V?$_reference@VName@@@@@@@@A._p, 0; _reference<_array<_reference<Name>>> SchemaNames::names ...
0x10074c70  jz      short loc_10074C7E
0x10074c72  xor     edx, edx; pref
0x10074c74  mov     ecx, offset ?names@SchemaNames@@2V?$_reference@V?$_array@V?$_reference@VName@@@@@@@@A; ppref
0x10074c79  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x10074c7e  call    ?classExit@_MXItem@@SGXXZ; _MXItem::classExit(void)
0x10074c83  cmp     ?s_defaultInstance@DecimalFormatSymbols@@0V?$_reference@VDecimalFormatSymbols@@@@A._p, 0; _reference<DecimalFormatSymbols> DecimalFormatSymbols::s_defaultInstance ...
0x10074c8a  jz      short loc_10074C98
0x10074c8c  xor     edx, edx; pref
0x10074c8e  mov     ecx, offset ?s_defaultInstance@DecimalFormatSymbols@@0V?$_reference@VDecimalFormatSymbols@@@@A; ppref
0x10074c93  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x10074c98  cmp     ?s_pSuccessParseErrorObj@DOMError@@2V?$_reference@VDOMError@@@@A._p, 0; _reference<DOMError> DOMError::s_pSuccessParseErrorObj ...
0x10074c9f  jz      short loc_10074CAD
0x10074ca1  xor     edx, edx; pref
0x10074ca3  mov     ecx, offset ?s_pSuccessParseErrorObj@DOMError@@2V?$_reference@VDOMError@@@@A; ppref
0x10074ca8  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x10074cad  cmp     ?s_rEmpty@MXItemCollection@@1V?$_reference@UISchemaItemCollection@@@@A._p, 0; _reference<ISchemaItemCollection> MXItemCollection::s_rEmpty ...
0x10074cb4  jz      short loc_10074CC2
0x10074cb6  xor     edx, edx; pref
0x10074cb8  mov     ecx, offset ?s_rEmpty@MXItemCollection@@1V?$_reference@UISchemaItemCollection@@@@A; ppref
0x10074cbd  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x10074cc2  cmp     ?s_rEmpty@MXStringCollection@@1V?$_reference@UISchemaStringCollection@@@@A._p, 0; _reference<ISchemaStringCollection> MXStringCollection::s_rEmpty ...
0x10074cc9  jz      short loc_10074CD7
0x10074ccb  xor     edx, edx; pref
0x10074ccd  mov     ecx, offset ?s_rEmpty@MXStringCollection@@1V?$_reference@UISchemaStringCollection@@@@A; ppref
0x10074cd2  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x10074cd7  call    ?classExit@XsdBuilder@@SGXXZ; XsdBuilder::classExit(void)
0x10074cdc  cmp     ?s_rNullElement@NullElement@@1V?$_reference@VSchemaElement@@@@A._p, 0; _reference<SchemaElement> NullElement::s_rNullElement ...
0x10074ce3  jz      short loc_10074CF1
0x10074ce5  xor     edx, edx; pref
0x10074ce7  mov     ecx, offset ?s_rNullElement@NullElement@@1V?$_reference@VSchemaElement@@@@A; ppref
0x10074cec  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x10074cf1  mov     eax, ?s_hInstance@Resources@@2PAUHINSTANCE__@@A; HINSTANCE__ * Resources::s_hInstance
0x10074cf6  test    eax, eax
0x10074cf8  jz      short loc_10074D13
0x10074cfa  cmp     eax, ?g_hInstance@@3PAUHINSTANCE__@@A; HINSTANCE__ * g_hInstance
0x10074d00  jz      short loc_10074D13
0x10074d02  push    eax; hLibModule
0x10074d03  call    ds:__imp__FreeLibrary@4; FreeLibrary(x)
0x10074d09  mov     ?s_hInstance@Resources@@2PAUHINSTANCE__@@A, 0; HINSTANCE__ * Resources::s_hInstance
0x10074d13  call    ?classExit@Exception@@SGXXZ; Exception::classExit(void)
0x10074d18  jmp     short loc_10074D2B
0x10074d1a  mov     ecx, [ebp+ms_exc.exc_ptr]; ep
0x10074d1d  call    ?fillException@Exception@@SGHPAU_EXCEPTION_POINTERS@@@Z; Exception::fillException(_EXCEPTION_POINTERS *)
0x10074d22  retn
0x10074d23  mov     esp, [ebp+ms_exc.old_esp]
0x10074d26  call    ?exceptionCatch@Exception@@SGXXZ; Exception::exceptionCatch(void)
0x10074d2b  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x10074d32  call    ?MTExit@@YGXXZ; MTExit(void)
0x10074d37  mov     ?g_fHasExited@@3_NA, 1; bool g_fHasExited
0x10074d3e  mov     ecx, [ebp+ms_exc.registration.Next]
0x10074d41  mov     large fs:0, ecx
0x10074d48  pop     ecx
0x10074d49  pop     edi
0x10074d4a  pop     esi
0x10074d4b  pop     ebx
0x10074d4c  leave
0x10074d4d  retn
```
