# DOMNode::_constructNamespacesStr(IInspectable *,HSTRING__ * *)

- ea: `0x1800f3430`
- end: `0x1800f3827`
- name: `?_constructNamespacesStr@DOMNode@@KAJPEAUIInspectable@@PEAPEAUHSTRING__@@@Z`
- size: `1015`
- prototype: `__int64 __fastcall(IInspectable *namespaces, HSTRING__ **phstrNamespaces)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800f2a70`
- `0x1800f2c20`

## callees

- `0x1800730a4`
- `0x1800c5030`
- `0x1800cada0`
- `0x1800f0bcc`
- `0x1800f1064`
- `0x1800f3430`
- `0x18015e370`
- `0x180188010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800f351e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800f355c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800f351e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800f355c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f361c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f3676`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f361c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f3676`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800f36bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800f36bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800f3500`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800f3548`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800f3500`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800f3548`

## string_xrefs

- `0x1800f34f9`: `xmlns`

## pseudocode

```c
__int64 __fastcall DOMNode::_constructNamespacesStr(IInspectable *namespaces, HSTRING__ **phstrNamespaces)
{
  IInspectable_vtbl *v2; // rax
  HRESULT (__fastcall *QueryInterface)(IUnknown *, const _GUID *, void **); // rbx
  Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *> *ptr; // rdi
  HRESULT (__fastcall *First)(Windows::Foundation::Collections::IIterable_impl<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *> *, Windows::Foundation::Collections::IIterator<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *> **); // rbx
  int v8; // ebx
  int i; // eax
  Windows::Foundation::Collections::IIterator<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *> *v10; // rdi
  HRESULT (__fastcall *get_Current)(Windows::Foundation::Collections::IIterator_impl<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *,1> *, Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> **); // rbx
  Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *v12; // rdi
  HRESULT (__fastcall *get_Key)(Windows::Foundation::Collections::IKeyValuePair_impl<HSTRING__ *,IInspectable *> *, HSTRING__ **); // rbx
  Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *v14; // rdi
  HRESULT (__fastcall *get_Value)(Windows::Foundation::Collections::IKeyValuePair_impl<HSTRING__ *,IInspectable *> *, IInspectable **); // rbx
  unsigned __int8 hasCurrent[8]; // [rsp+20h] [rbp-E0h] BYREF
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *> > iterator; // [rsp+28h] [rbp-D8h] BYREF
  Windows::Internal::String hstrPrefix; // [rsp+30h] [rbp-D0h] BYREF
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> > pKeyValuePair; // [rsp+38h] [rbp-C8h] BYREF
  Windows::Internal::String hstrNamespace; // [rsp+40h] [rbp-C0h] BYREF
  Windows::Internal::String hstrNSs; // [rsp+48h] [rbp-B8h] BYREF
  Microsoft::WRL::ComPtr<IInspectable> value; // [rsp+50h] [rbp-B0h] BYREF
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *> > iterable; // [rsp+58h] [rbp-A8h] BYREF
  Windows::Internal::StringReference hstrXmlns; // [rsp+60h] [rbp-A0h] BYREF
  Windows::Internal::StringReference hstrEqualAndSQuote; // [rsp+80h] [rbp-80h] BYREF
  Windows::Internal::StringReference hstrColon; // [rsp+A0h] [rbp-60h] BYREF
  Windows::Internal::StringReference hstrSingleQuote; // [rsp+C0h] [rbp-40h] BYREF
  Windows::Internal::StringReference hstrSpace; // [rsp+E0h] [rbp-20h] BYREF

  v2 = namespaces->__vftable;
  hstrNSs._hstring = 0;
  iterable.ptr_ = 0;
  QueryInterface = v2->QueryInterface;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&iterable);
  if ( QueryInterface(namespaces, &GUID_fe2f3d47_5d47_5499_8374_430c7cda0204, (void **)&iterable.ptr_) < 0 )
  {
    v8 = PropertyValueToHSTRING(namespaces, &hstrNSs._hstring);
    if ( v8 < 0 )
      goto $CleanUp_229;
LABEL_28:
    *phstrNamespaces = hstrNSs._hstring;
    hstrNSs._hstring = 0;
    goto $CleanUp_229;
  }
  ptr = iterable.ptr_;
  iterator.ptr_ = 0;
  First = iterable.ptr_->First;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&iterator);
  v8 = First(ptr, &iterator.ptr_);
  if ( v8 >= 0 )
  {
    Windows::Internal::StringReference::StringReference(&hstrSpace, (const wchar_t (*)[2])L" ");
    if ( WindowsCreateStringReference(L"xmlns", 5u, &hstrXmlns._header, &hstrXmlns._hstring) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    Windows::Internal::StringReference::StringReference(&hstrColon, (const wchar_t (*)[2])L":");
    if ( WindowsCreateStringReference(L"='", 2u, &hstrEqualAndSQuote._header, &hstrEqualAndSQuote._hstring) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    Windows::Internal::StringReference::StringReference(&hstrSingleQuote, (const wchar_t (*)[2])L"'");
    hstrPrefix._hstring = 0;
    hstrNamespace._hstring = 0;
    pKeyValuePair.ptr_ = 0;
    value.ptr_ = 0;
    hasCurrent[0] = 0;
    for ( i = iterator.ptr_->get_HasCurrent(iterator.ptr_, hasCurrent);
          ;
          i = Windows::Internal::String::Concat(&hstrNSs, (const Windows::Internal::String *)&hstrSpace, &hstrNSs) )
    {
      v8 = i;
      if ( i < 0 )
        goto LABEL_10;
      if ( !hasCurrent[0] )
        break;
      v10 = iterator.ptr_;
      get_Current = iterator.ptr_->get_Current;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&pKeyValuePair);
      v8 = get_Current(v10, &pKeyValuePair.ptr_);
      if ( v8 < 0 )
        goto LABEL_10;
      v12 = pKeyValuePair.ptr_;
      get_Key = pKeyValuePair.ptr_->get_Key;
      WindowsDeleteString(hstrPrefix._hstring);
      hstrPrefix._hstring = 0;
      v8 = get_Key(v12, &hstrPrefix._hstring);
      if ( v8 < 0 )
        goto LABEL_10;
      v14 = pKeyValuePair.ptr_;
      get_Value = pKeyValuePair.ptr_->get_Value;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&value);
      v8 = get_Value(v14, &value.ptr_);
      if ( v8 < 0 )
        goto LABEL_10;
      WindowsDeleteString(hstrNamespace._hstring);
      hstrNamespace._hstring = 0;
      v8 = PropertyValueToHSTRING(value.ptr_, &hstrNamespace._hstring);
      if ( v8 < 0 )
        goto LABEL_10;
      v8 = Windows::Internal::String::Concat(&hstrNSs, (const Windows::Internal::String *)&hstrXmlns, &hstrNSs);
      if ( v8 < 0 )
        goto LABEL_10;
      if ( !WindowsIsStringEmpty(hstrPrefix._hstring) )
      {
        v8 = Windows::Internal::String::Concat(&hstrNSs, (const Windows::Internal::String *)&hstrColon, &hstrNSs);
        if ( v8 < 0 )
          goto LABEL_10;
        v8 = Windows::Internal::String::Concat(&hstrNSs, &hstrPrefix, &hstrNSs);
        if ( v8 < 0 )
          goto LABEL_10;
      }
      v8 = Windows::Internal::String::Concat(&hstrNSs, (const Windows::Internal::String *)&hstrEqualAndSQuote, &hstrNSs);
      if ( v8 < 0
        || (v8 = Windows::Internal::String::Concat(&hstrNSs, &hstrNamespace, &hstrNSs), v8 < 0)
        || (v8 = Windows::Internal::String::Concat(
                   &hstrNSs,
                   (const Windows::Internal::String *)&hstrSingleQuote,
                   &hstrNSs),
            v8 < 0)
        || (v8 = iterator.ptr_->MoveNext(iterator.ptr_, hasCurrent), v8 < 0) )
      {
LABEL_10:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&value);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&pKeyValuePair);
        Windows::Internal::String::~String(&hstrNamespace);
        Windows::Internal::String::~String(&hstrPrefix);
        goto LABEL_3;
      }
      if ( !hasCurrent[0] )
        break;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&value);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&pKeyValuePair);
    Windows::Internal::String::~String(&hstrNamespace);
    Windows::Internal::String::~String(&hstrPrefix);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&iterator);
    goto LABEL_28;
  }
LABEL_3:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&iterator);
$CleanUp_229:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&iterable);
  Windows::Internal::String::~String(&hstrNSs);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800f3430  mov     [rsp-8+arg_10], rbx
0x1800f3435  mov     [rsp-8+arg_18], rsi
0x1800f343a  push    rbp
0x1800f343b  push    rdi
0x1800f343c  push    r14
0x1800f343e  lea     rbp, [rsp-10h]
0x1800f3443  sub     rsp, 110h
0x1800f344a  mov     rax, cs:__security_cookie
0x1800f3451  xor     rax, rsp
0x1800f3454  mov     [rbp+20h+var_20], rax
0x1800f3458  mov     rax, [namespaces]
0x1800f345b  mov     rdi, namespaces
0x1800f345e  xor     r14d, r14d
0x1800f3461  lea     namespaces, [rsp+120h+iterable]; this
0x1800f3466  mov     rsi, phstrNamespaces
0x1800f3469  mov     [rsp+120h+hstrNSs._hstring], r14
0x1800f346e  mov     [rsp+120h+iterable.ptr_], r14
0x1800f3473  mov     rbx, [rax]
0x1800f3476  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f347b  lea     r8, [rsp+120h+iterable]
0x1800f3480  mov     namespaces, rdi
0x1800f3483  lea     phstrNamespaces, _GUID_fe2f3d47_5d47_5499_8374_430c7cda0204
0x1800f348a  mov     rax, rbx
0x1800f348d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3492  test    eax, eax
0x1800f3494  js      loc_1800F37CD
0x1800f349a  mov     rdi, [rsp+120h+iterable.ptr_]
0x1800f349f  lea     namespaces, [rsp+120h+iterator]; this
0x1800f34a4  mov     [rsp+120h+iterator.ptr_], r14
0x1800f34a9  mov     rax, [rdi]
0x1800f34ac  mov     rbx, [rax+30h]
0x1800f34b0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f34b5  lea     phstrNamespaces, [rsp+120h+iterator]
0x1800f34ba  mov     namespaces, rdi
0x1800f34bd  mov     rax, rbx
0x1800f34c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f34c5  mov     ebx, eax
0x1800f34c7  test    eax, eax
0x1800f34c9  jns     short loc_1800F34DA
0x1800f34cb  lea     namespaces, [rsp+120h+iterator]; this
0x1800f34d0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f34d5  jmp     $CleanUp_229
0x1800f34da  lea     phstrNamespaces, stringRef; " "
0x1800f34e1  lea     namespaces, [rbp+20h+hstrSpace]; this
0x1800f34e5  call    ??$?0$01@StringReference@Internal@Windows@@QEAA@AEAY01$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[2])
0x1800f34ea  lea     r9, [rsp+120h+hstrXmlns]; string
0x1800f34ef  mov     edx, 5; length
0x1800f34f4  lea     r8, [rsp+120h+hstrXmlns._header]; hstringHeader
0x1800f34f9  lea     namespaces, aXmlns; "xmlns"
0x1800f3500  call    cs:__imp_WindowsCreateStringReference
0x1800f3506  mov     ebx, 1
0x1800f350b  mov     edi, 0C000000Dh
0x1800f3510  test    eax, eax
0x1800f3512  jns     short loc_1800F3524
0x1800f3514  xor     r9d, r9d; lpArguments
0x1800f3517  xor     r8d, r8d; nNumberOfArguments
0x1800f351a  mov     edx, ebx; dwExceptionFlags
0x1800f351c  mov     ecx, edi; dwExceptionCode
0x1800f351e  call    cs:__imp_RaiseException
0x1800f3524  lea     phstrNamespaces, asc_1801BFA84; ":"
0x1800f352b  lea     namespaces, [rbp+20h+hstrColon]; this
0x1800f352f  call    ??$?0$01@StringReference@Internal@Windows@@QEAA@AEAY01$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[2])
0x1800f3534  lea     r9, [rbp+20h+hstrEqualAndSQuote]; string
0x1800f3538  mov     edx, 2; length
0x1800f353d  lea     r8, [rbp+20h+hstrEqualAndSQuote._header]; hstringHeader
0x1800f3541  lea     namespaces, asc_1801D2894; "='"
0x1800f3548  call    cs:__imp_WindowsCreateStringReference
0x1800f354e  test    eax, eax
0x1800f3550  jns     short loc_1800F3562
0x1800f3552  xor     r9d, r9d; lpArguments
0x1800f3555  xor     r8d, r8d; nNumberOfArguments
0x1800f3558  mov     edx, ebx; dwExceptionFlags
0x1800f355a  mov     ecx, edi; dwExceptionCode
0x1800f355c  call    cs:__imp_RaiseException
0x1800f3562  lea     phstrNamespaces, asc_1801BF8E8; "'"
0x1800f3569  lea     namespaces, [rbp+20h+hstrSingleQuote]; this
0x1800f356d  call    ??$?0$01@StringReference@Internal@Windows@@QEAA@AEAY01$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[2])
0x1800f3572  mov     namespaces, [rsp+120h+iterator.ptr_]
0x1800f3577  lea     phstrNamespaces, [rsp+120h+hasCurrent]
0x1800f357c  mov     [rsp+120h+hstrPrefix._hstring], r14
0x1800f3581  mov     [rsp+120h+hstrNamespace._hstring], r14
0x1800f3586  mov     [rsp+120h+pKeyValuePair.ptr_], r14
0x1800f358b  mov     [rsp+120h+value.ptr_], r14
0x1800f3590  mov     [rsp+120h+hasCurrent], r14b
0x1800f3595  mov     rax, [namespaces]
0x1800f3598  mov     rax, [rax+38h]
0x1800f359c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f35a1  mov     ebx, eax
0x1800f35a3  test    eax, eax
0x1800f35a5  jns     short loc_1800F35D4
0x1800f35a7  lea     namespaces, [rsp+120h+value]; this
0x1800f35ac  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f35b1  lea     namespaces, [rsp+120h+pKeyValuePair]; this
0x1800f35b6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f35bb  lea     namespaces, [rsp+120h+hstrNamespace]; this
0x1800f35c0  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800f35c5  lea     namespaces, [rsp+120h+hstrPrefix]; this
0x1800f35ca  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800f35cf  jmp     loc_1800F34CB
0x1800f35d4  cmp     [rsp+120h+hasCurrent], r14b
0x1800f35d9  jz      loc_1800F3799
0x1800f35df  mov     rdi, [rsp+120h+iterator.ptr_]
0x1800f35e4  lea     namespaces, [rsp+120h+pKeyValuePair]; this
0x1800f35e9  mov     rax, [rdi]
0x1800f35ec  mov     rbx, [rax+30h]
0x1800f35f0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f35f5  lea     phstrNamespaces, [rsp+120h+pKeyValuePair]
0x1800f35fa  mov     namespaces, rdi
0x1800f35fd  mov     rax, rbx
0x1800f3600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3605  mov     ebx, eax
0x1800f3607  test    eax, eax
0x1800f3609  js      short loc_1800F35A7
0x1800f360b  mov     rdi, [rsp+120h+pKeyValuePair.ptr_]
0x1800f3610  mov     namespaces, [rsp+120h+hstrPrefix._hstring]; string
0x1800f3615  mov     rax, [rdi]
0x1800f3618  mov     rbx, [rax+30h]
0x1800f361c  call    cs:__imp_WindowsDeleteString
0x1800f3622  lea     phstrNamespaces, [rsp+120h+hstrPrefix]
0x1800f3627  mov     [rsp+120h+hstrPrefix._hstring], r14
0x1800f362c  mov     namespaces, rdi
0x1800f362f  mov     rax, rbx
0x1800f3632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3637  lea     namespaces, [rsp+120h+value]; this
0x1800f363c  mov     ebx, eax
0x1800f363e  test    eax, eax
0x1800f3640  js      loc_1800F35AC
0x1800f3646  mov     rdi, [rsp+120h+pKeyValuePair.ptr_]
0x1800f364b  mov     rax, [rdi]
0x1800f364e  mov     rbx, [rax+38h]
0x1800f3652  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f3657  lea     phstrNamespaces, [rsp+120h+value]
0x1800f365c  mov     namespaces, rdi
0x1800f365f  mov     rax, rbx
0x1800f3662  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3667  mov     ebx, eax
0x1800f3669  test    eax, eax
0x1800f366b  js      loc_1800F35A7
0x1800f3671  mov     namespaces, [rsp+120h+hstrNamespace._hstring]; string
0x1800f3676  call    cs:__imp_WindowsDeleteString
0x1800f367c  mov     namespaces, [rsp+120h+value.ptr_]; prop
0x1800f3681  lea     phstrNamespaces, [rsp+120h+hstrNamespace]; returnValue
0x1800f3686  mov     [rsp+120h+hstrNamespace._hstring], r14
0x1800f368b  call    ?PropertyValueToHSTRING@@YAJPEAUIInspectable@@PEAPEAUHSTRING__@@@Z; PropertyValueToHSTRING(IInspectable *,HSTRING__ * *)
0x1800f3690  mov     ebx, eax
0x1800f3692  test    eax, eax
0x1800f3694  js      loc_1800F35A7
0x1800f369a  lea     r8, [rsp+120h+hstrNSs]; newString
0x1800f369f  lea     phstrNamespaces, [rsp+120h+hstrXmlns]; string
0x1800f36a4  lea     namespaces, [rsp+120h+hstrNSs]; this
0x1800f36a9  call    ?Concat@String@Internal@Windows@@QEBAJAEBV123@PEAV123@@Z; Windows::Internal::String::Concat(Windows::Internal::String const &,Windows::Internal::String *)
0x1800f36ae  mov     ebx, eax
0x1800f36b0  test    eax, eax
0x1800f36b2  js      loc_1800F35A7
0x1800f36b8  mov     namespaces, [rsp+120h+hstrPrefix._hstring]; string
0x1800f36bd  call    cs:__imp_WindowsIsStringEmpty
0x1800f36c3  test    eax, eax
0x1800f36c5  jnz     short loc_1800F3702
0x1800f36c7  lea     r8, [rsp+120h+hstrNSs]; newString
0x1800f36cc  lea     phstrNamespaces, [rbp+20h+hstrColon]; string
0x1800f36d0  lea     namespaces, [rsp+120h+hstrNSs]; this
0x1800f36d5  call    ?Concat@String@Internal@Windows@@QEBAJAEBV123@PEAV123@@Z; Windows::Internal::String::Concat(Windows::Internal::String const &,Windows::Internal::String *)
0x1800f36da  mov     ebx, eax
0x1800f36dc  test    eax, eax
0x1800f36de  js      loc_1800F35A7
0x1800f36e4  lea     r8, [rsp+120h+hstrNSs]; newString
0x1800f36e9  lea     phstrNamespaces, [rsp+120h+hstrPrefix]; string
0x1800f36ee  lea     namespaces, [rsp+120h+hstrNSs]; this
0x1800f36f3  call    ?Concat@String@Internal@Windows@@QEBAJAEBV123@PEAV123@@Z; Windows::Internal::String::Concat(Windows::Internal::String const &,Windows::Internal::String *)
0x1800f36f8  mov     ebx, eax
0x1800f36fa  test    eax, eax
0x1800f36fc  js      loc_1800F35A7
0x1800f3702  lea     r8, [rsp+120h+hstrNSs]; newString
0x1800f3707  lea     phstrNamespaces, [rbp+20h+hstrEqualAndSQuote]; string
0x1800f370b  lea     namespaces, [rsp+120h+hstrNSs]; this
0x1800f3710  call    ?Concat@String@Internal@Windows@@QEBAJAEBV123@PEAV123@@Z; Windows::Internal::String::Concat(Windows::Internal::String const &,Windows::Internal::String *)
0x1800f3715  mov     ebx, eax
0x1800f3717  test    eax, eax
0x1800f3719  js      loc_1800F35A7
0x1800f371f  lea     r8, [rsp+120h+hstrNSs]; newString
0x1800f3724  lea     phstrNamespaces, [rsp+120h+hstrNamespace]; string
0x1800f3729  lea     namespaces, [rsp+120h+hstrNSs]; this
0x1800f372e  call    ?Concat@String@Internal@Windows@@QEBAJAEBV123@PEAV123@@Z; Windows::Internal::String::Concat(Windows::Internal::String const &,Windows::Internal::String *)
0x1800f3733  mov     ebx, eax
0x1800f3735  test    eax, eax
0x1800f3737  js      loc_1800F35A7
0x1800f373d  lea     r8, [rsp+120h+hstrNSs]; newString
0x1800f3742  lea     phstrNamespaces, [rbp+20h+hstrSingleQuote]; string
0x1800f3746  lea     namespaces, [rsp+120h+hstrNSs]; this
0x1800f374b  call    ?Concat@String@Internal@Windows@@QEBAJAEBV123@PEAV123@@Z; Windows::Internal::String::Concat(Windows::Internal::String const &,Windows::Internal::String *)
0x1800f3750  mov     ebx, eax
0x1800f3752  test    eax, eax
0x1800f3754  js      loc_1800F35A7
0x1800f375a  mov     namespaces, [rsp+120h+iterator.ptr_]
0x1800f375f  lea     phstrNamespaces, [rsp+120h+hasCurrent]
0x1800f3764  mov     rax, [namespaces]
0x1800f3767  mov     rax, [rax+40h]
0x1800f376b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3770  mov     ebx, eax
0x1800f3772  test    eax, eax
0x1800f3774  js      loc_1800F35A7
0x1800f377a  cmp     [rsp+120h+hasCurrent], r14b
0x1800f377f  jz      short loc_1800F3799
0x1800f3781  lea     r8, [rsp+120h+hstrNSs]; newString
0x1800f3786  lea     phstrNamespaces, [rbp+20h+hstrSpace]; string
0x1800f378a  lea     namespaces, [rsp+120h+hstrNSs]; this
0x1800f378f  call    ?Concat@String@Internal@Windows@@QEBAJAEBV123@PEAV123@@Z; Windows::Internal::String::Concat(Windows::Internal::String const &,Windows::Internal::String *)
0x1800f3794  jmp     loc_1800F35A1
0x1800f3799  lea     namespaces, [rsp+120h+value]; this
0x1800f379e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f37a3  lea     namespaces, [rsp+120h+pKeyValuePair]; this
0x1800f37a8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f37ad  lea     namespaces, [rsp+120h+hstrNamespace]; this
0x1800f37b2  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800f37b7  lea     namespaces, [rsp+120h+hstrPrefix]; this
0x1800f37bc  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800f37c1  lea     namespaces, [rsp+120h+iterator]; this
0x1800f37c6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f37cb  jmp     short loc_1800F37E0
0x1800f37cd  lea     phstrNamespaces, [rsp+120h+hstrNSs]; returnValue
0x1800f37d2  mov     namespaces, rdi; prop
0x1800f37d5  call    ?PropertyValueToHSTRING@@YAJPEAUIInspectable@@PEAPEAUHSTRING__@@@Z; PropertyValueToHSTRING(IInspectable *,HSTRING__ * *)
0x1800f37da  mov     ebx, eax
0x1800f37dc  test    eax, eax
0x1800f37de  js      short $CleanUp_229
0x1800f37e0  mov     rax, [rsp+120h+hstrNSs._hstring]
0x1800f37e5  mov     [rsi], rax
0x1800f37e8  mov     [rsp+120h+hstrNSs._hstring], r14
0x1800f37ed  lea     namespaces, [rsp+120h+iterable]; this
0x1800f37f2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f37f7  lea     namespaces, [rsp+120h+hstrNSs]; this
0x1800f37fc  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800f3801  mov     eax, ebx
0x1800f3803  mov     namespaces, [rbp+20h+var_20]
0x1800f3807  xor     namespaces, rsp; StackCookie
0x1800f380a  call    __security_check_cookie
0x1800f380f  lea     r11, [rsp+120h+var_10]
0x1800f3817  mov     rbx, [r11+30h]
0x1800f381b  mov     rsi, [r11+38h]
0x1800f381f  mov     rsp, r11
0x1800f3822  pop     r14
0x1800f3824  pop     rdi
0x1800f3825  pop     rbp
0x1800f3826  retn
```
