# DOMNode::_constructNamespacesStr(IInspectable *,HSTRING__ * *)

- ea: `0x1800f5904`
- end: `0x1800f5d26`
- name: `?_constructNamespacesStr@DOMNode@@KAJPEAUIInspectable@@PEAPEAUHSTRING__@@@Z`
- size: `1058`
- prototype: `HRESULT __fastcall(IInspectable *namespaces, HSTRING__ **phstrNamespaces)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800f4f10`
- `0x1800f50d0`

## callees

- `0x1800719e4`
- `0x1800c68a0`
- `0x1800cc6c0`
- `0x1800f3020`
- `0x1800f34d4`
- `0x1800f5904`
- `0x180161ce4`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800f59f8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800f5a42`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800f59f8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800f5a42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f5b08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f5b68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f5b08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f5b68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800f5bb5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800f5bb5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800f59d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800f5a28`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800f59d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800f5a28`

## string_xrefs

- `0x1800f59cd`: `xmlns`

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
0x1800f5904  mov     [rsp-8+arg_10], rbx
0x1800f5909  mov     [rsp-8+arg_18], rsi
0x1800f590e  push    rbp
0x1800f590f  push    rdi
0x1800f5910  push    r14
0x1800f5912  lea     rbp, [rsp-10h]
0x1800f5917  sub     rsp, 110h
0x1800f591e  mov     rax, cs:__security_cookie
0x1800f5925  xor     rax, rsp
0x1800f5928  mov     [rbp+20h+var_20], rax
0x1800f592c  mov     rax, [namespaces]
0x1800f592f  mov     rdi, namespaces
0x1800f5932  xor     r14d, r14d
0x1800f5935  lea     namespaces, [rsp+120h+iterable]; this
0x1800f593a  mov     rsi, phstrNamespaces
0x1800f593d  mov     [rsp+120h+hstrNSs._hstring], r14
0x1800f5942  mov     [rsp+120h+iterable.ptr_], r14
0x1800f5947  mov     rbx, [rax]
0x1800f594a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f594f  lea     r8, [rsp+120h+iterable]
0x1800f5954  mov     namespaces, rdi
0x1800f5957  lea     phstrNamespaces, _GUID_fe2f3d47_5d47_5499_8374_430c7cda0204
0x1800f595e  mov     rax, rbx
0x1800f5961  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5966  test    eax, eax
0x1800f5968  js      loc_1800F5CCB
0x1800f596e  mov     rdi, [rsp+120h+iterable.ptr_]
0x1800f5973  lea     namespaces, [rsp+120h+iterator]; this
0x1800f5978  mov     [rsp+120h+iterator.ptr_], r14
0x1800f597d  mov     rax, [rdi]
0x1800f5980  mov     rbx, [rax+30h]
0x1800f5984  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f5989  lea     phstrNamespaces, [rsp+120h+iterator]
0x1800f598e  mov     namespaces, rdi
0x1800f5991  mov     rax, rbx
0x1800f5994  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5999  mov     ebx, eax
0x1800f599b  test    eax, eax
0x1800f599d  jns     short loc_1800F59AE
0x1800f599f  lea     namespaces, [rsp+120h+iterator]; this
0x1800f59a4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f59a9  jmp     $CleanUp_229
0x1800f59ae  lea     phstrNamespaces, stringRef; " "
0x1800f59b5  lea     namespaces, [rbp+20h+hstrSpace]; this
0x1800f59b9  call    ??$?0$01@StringReference@Internal@Windows@@QEAA@AEAY01$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[2])
0x1800f59be  lea     r9, [rsp+120h+hstrXmlns]; string
0x1800f59c3  mov     edx, 5; length
0x1800f59c8  lea     r8, [rsp+120h+hstrXmlns._header]; hstringHeader
0x1800f59cd  lea     namespaces, aXmlns; "xmlns"
0x1800f59d4  call    cs:__imp_WindowsCreateStringReference
0x1800f59db  nop     dword ptr [rax+rax+00h]
0x1800f59e0  mov     ebx, 1
0x1800f59e5  mov     edi, 0C000000Dh
0x1800f59ea  test    eax, eax
0x1800f59ec  jns     short loc_1800F5A04
0x1800f59ee  xor     r9d, r9d; lpArguments
0x1800f59f1  xor     r8d, r8d; nNumberOfArguments
0x1800f59f4  mov     edx, ebx; dwExceptionFlags
0x1800f59f6  mov     ecx, edi; dwExceptionCode
0x1800f59f8  call    cs:__imp_RaiseException
0x1800f59ff  nop     dword ptr [rax+rax+00h]
0x1800f5a04  lea     phstrNamespaces, asc_1801BF3AC; ":"
0x1800f5a0b  lea     namespaces, [rbp+20h+hstrColon]; this
0x1800f5a0f  call    ??$?0$01@StringReference@Internal@Windows@@QEAA@AEAY01$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[2])
0x1800f5a14  lea     r9, [rbp+20h+hstrEqualAndSQuote]; string
0x1800f5a18  mov     edx, 2; length
0x1800f5a1d  lea     r8, [rbp+20h+hstrEqualAndSQuote._header]; hstringHeader
0x1800f5a21  lea     namespaces, asc_1801D6894; "='"
0x1800f5a28  call    cs:__imp_WindowsCreateStringReference
0x1800f5a2f  nop     dword ptr [rax+rax+00h]
0x1800f5a34  test    eax, eax
0x1800f5a36  jns     short loc_1800F5A4E
0x1800f5a38  xor     r9d, r9d; lpArguments
0x1800f5a3b  xor     r8d, r8d; nNumberOfArguments
0x1800f5a3e  mov     edx, ebx; dwExceptionFlags
0x1800f5a40  mov     ecx, edi; dwExceptionCode
0x1800f5a42  call    cs:__imp_RaiseException
0x1800f5a49  nop     dword ptr [rax+rax+00h]
0x1800f5a4e  lea     phstrNamespaces, c; "'"
0x1800f5a55  lea     namespaces, [rbp+20h+hstrSingleQuote]; this
0x1800f5a59  call    ??$?0$01@StringReference@Internal@Windows@@QEAA@AEAY01$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[2])
0x1800f5a5e  mov     namespaces, [rsp+120h+iterator.ptr_]
0x1800f5a63  lea     phstrNamespaces, [rsp+120h+hasCurrent]
0x1800f5a68  mov     [rsp+120h+hstrPrefix._hstring], r14
0x1800f5a6d  mov     [rsp+120h+hstrNamespace._hstring], r14
0x1800f5a72  mov     [rsp+120h+pKeyValuePair.ptr_], r14
0x1800f5a77  mov     [rsp+120h+value.ptr_], r14
0x1800f5a7c  mov     [rsp+120h+hasCurrent], r14b
0x1800f5a81  mov     rax, [namespaces]
0x1800f5a84  mov     rax, [rax+38h]
0x1800f5a88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5a8d  mov     ebx, eax
0x1800f5a8f  test    eax, eax
0x1800f5a91  jns     short loc_1800F5AC0
0x1800f5a93  lea     namespaces, [rsp+120h+value]; this
0x1800f5a98  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f5a9d  lea     namespaces, [rsp+120h+pKeyValuePair]; this
0x1800f5aa2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f5aa7  lea     namespaces, [rsp+120h+hstrNamespace]; this
0x1800f5aac  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800f5ab1  lea     namespaces, [rsp+120h+hstrPrefix]; this
0x1800f5ab6  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800f5abb  jmp     loc_1800F599F
0x1800f5ac0  cmp     [rsp+120h+hasCurrent], r14b
0x1800f5ac5  jz      loc_1800F5C97
0x1800f5acb  mov     rdi, [rsp+120h+iterator.ptr_]
0x1800f5ad0  lea     namespaces, [rsp+120h+pKeyValuePair]; this
0x1800f5ad5  mov     rax, [rdi]
0x1800f5ad8  mov     rbx, [rax+30h]
0x1800f5adc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f5ae1  lea     phstrNamespaces, [rsp+120h+pKeyValuePair]
0x1800f5ae6  mov     namespaces, rdi
0x1800f5ae9  mov     rax, rbx
0x1800f5aec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5af1  mov     ebx, eax
0x1800f5af3  test    eax, eax
0x1800f5af5  js      short loc_1800F5A93
0x1800f5af7  mov     rdi, [rsp+120h+pKeyValuePair.ptr_]
0x1800f5afc  mov     namespaces, [rsp+120h+hstrPrefix._hstring]; string
0x1800f5b01  mov     rax, [rdi]
0x1800f5b04  mov     rbx, [rax+30h]
0x1800f5b08  call    cs:__imp_WindowsDeleteString
0x1800f5b0f  nop     dword ptr [rax+rax+00h]
0x1800f5b14  lea     phstrNamespaces, [rsp+120h+hstrPrefix]
0x1800f5b19  mov     [rsp+120h+hstrPrefix._hstring], r14
0x1800f5b1e  mov     namespaces, rdi
0x1800f5b21  mov     rax, rbx
0x1800f5b24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5b29  lea     namespaces, [rsp+120h+value]; this
0x1800f5b2e  mov     ebx, eax
0x1800f5b30  test    eax, eax
0x1800f5b32  js      loc_1800F5A98
0x1800f5b38  mov     rdi, [rsp+120h+pKeyValuePair.ptr_]
0x1800f5b3d  mov     rax, [rdi]
0x1800f5b40  mov     rbx, [rax+38h]
0x1800f5b44  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f5b49  lea     phstrNamespaces, [rsp+120h+value]
0x1800f5b4e  mov     namespaces, rdi
0x1800f5b51  mov     rax, rbx
0x1800f5b54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5b59  mov     ebx, eax
0x1800f5b5b  test    eax, eax
0x1800f5b5d  js      loc_1800F5A93
0x1800f5b63  mov     namespaces, [rsp+120h+hstrNamespace._hstring]; string
0x1800f5b68  call    cs:__imp_WindowsDeleteString
0x1800f5b6f  nop     dword ptr [rax+rax+00h]
0x1800f5b74  mov     namespaces, [rsp+120h+value.ptr_]; prop
0x1800f5b79  lea     phstrNamespaces, [rsp+120h+hstrNamespace]; returnValue
0x1800f5b7e  mov     [rsp+120h+hstrNamespace._hstring], r14
0x1800f5b83  call    ?PropertyValueToHSTRING@@YAJPEAUIInspectable@@PEAPEAUHSTRING__@@@Z; PropertyValueToHSTRING(IInspectable *,HSTRING__ * *)
0x1800f5b88  mov     ebx, eax
0x1800f5b8a  test    eax, eax
0x1800f5b8c  js      loc_1800F5A93
0x1800f5b92  lea     r8, [rsp+120h+hstrNSs]; newString
0x1800f5b97  lea     phstrNamespaces, [rsp+120h+hstrXmlns]; string
0x1800f5b9c  lea     namespaces, [rsp+120h+hstrNSs]; this
0x1800f5ba1  call    ?Concat@String@Internal@Windows@@QEBAJAEBV123@PEAV123@@Z; Windows::Internal::String::Concat(Windows::Internal::String const &,Windows::Internal::String *)
0x1800f5ba6  mov     ebx, eax
0x1800f5ba8  test    eax, eax
0x1800f5baa  js      loc_1800F5A93
0x1800f5bb0  mov     namespaces, [rsp+120h+hstrPrefix._hstring]; string
0x1800f5bb5  call    cs:__imp_WindowsIsStringEmpty
0x1800f5bbc  nop     dword ptr [rax+rax+00h]
0x1800f5bc1  test    eax, eax
0x1800f5bc3  jnz     short loc_1800F5C00
0x1800f5bc5  lea     r8, [rsp+120h+hstrNSs]; newString
0x1800f5bca  lea     phstrNamespaces, [rbp+20h+hstrColon]; string
0x1800f5bce  lea     namespaces, [rsp+120h+hstrNSs]; this
0x1800f5bd3  call    ?Concat@String@Internal@Windows@@QEBAJAEBV123@PEAV123@@Z; Windows::Internal::String::Concat(Windows::Internal::String const &,Windows::Internal::String *)
0x1800f5bd8  mov     ebx, eax
0x1800f5bda  test    eax, eax
0x1800f5bdc  js      loc_1800F5A93
0x1800f5be2  lea     r8, [rsp+120h+hstrNSs]; newString
0x1800f5be7  lea     phstrNamespaces, [rsp+120h+hstrPrefix]; string
0x1800f5bec  lea     namespaces, [rsp+120h+hstrNSs]; this
0x1800f5bf1  call    ?Concat@String@Internal@Windows@@QEBAJAEBV123@PEAV123@@Z; Windows::Internal::String::Concat(Windows::Internal::String const &,Windows::Internal::String *)
0x1800f5bf6  mov     ebx, eax
0x1800f5bf8  test    eax, eax
0x1800f5bfa  js      loc_1800F5A93
0x1800f5c00  lea     r8, [rsp+120h+hstrNSs]; newString
0x1800f5c05  lea     phstrNamespaces, [rbp+20h+hstrEqualAndSQuote]; string
0x1800f5c09  lea     namespaces, [rsp+120h+hstrNSs]; this
0x1800f5c0e  call    ?Concat@String@Internal@Windows@@QEBAJAEBV123@PEAV123@@Z; Windows::Internal::String::Concat(Windows::Internal::String const &,Windows::Internal::String *)
0x1800f5c13  mov     ebx, eax
0x1800f5c15  test    eax, eax
0x1800f5c17  js      loc_1800F5A93
0x1800f5c1d  lea     r8, [rsp+120h+hstrNSs]; newString
0x1800f5c22  lea     phstrNamespaces, [rsp+120h+hstrNamespace]; string
0x1800f5c27  lea     namespaces, [rsp+120h+hstrNSs]; this
0x1800f5c2c  call    ?Concat@String@Internal@Windows@@QEBAJAEBV123@PEAV123@@Z; Windows::Internal::String::Concat(Windows::Internal::String const &,Windows::Internal::String *)
0x1800f5c31  mov     ebx, eax
0x1800f5c33  test    eax, eax
0x1800f5c35  js      loc_1800F5A93
0x1800f5c3b  lea     r8, [rsp+120h+hstrNSs]; newString
0x1800f5c40  lea     phstrNamespaces, [rbp+20h+hstrSingleQuote]; string
0x1800f5c44  lea     namespaces, [rsp+120h+hstrNSs]; this
0x1800f5c49  call    ?Concat@String@Internal@Windows@@QEBAJAEBV123@PEAV123@@Z; Windows::Internal::String::Concat(Windows::Internal::String const &,Windows::Internal::String *)
0x1800f5c4e  mov     ebx, eax
0x1800f5c50  test    eax, eax
0x1800f5c52  js      loc_1800F5A93
0x1800f5c58  mov     namespaces, [rsp+120h+iterator.ptr_]
0x1800f5c5d  lea     phstrNamespaces, [rsp+120h+hasCurrent]
0x1800f5c62  mov     rax, [namespaces]
0x1800f5c65  mov     rax, [rax+40h]
0x1800f5c69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5c6e  mov     ebx, eax
0x1800f5c70  test    eax, eax
0x1800f5c72  js      loc_1800F5A93
0x1800f5c78  cmp     [rsp+120h+hasCurrent], r14b
0x1800f5c7d  jz      short loc_1800F5C97
0x1800f5c7f  lea     r8, [rsp+120h+hstrNSs]; newString
0x1800f5c84  lea     phstrNamespaces, [rbp+20h+hstrSpace]; string
0x1800f5c88  lea     namespaces, [rsp+120h+hstrNSs]; this
0x1800f5c8d  call    ?Concat@String@Internal@Windows@@QEBAJAEBV123@PEAV123@@Z; Windows::Internal::String::Concat(Windows::Internal::String const &,Windows::Internal::String *)
0x1800f5c92  jmp     loc_1800F5A8D
0x1800f5c97  lea     namespaces, [rsp+120h+value]; this
0x1800f5c9c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f5ca1  lea     namespaces, [rsp+120h+pKeyValuePair]; this
0x1800f5ca6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f5cab  lea     namespaces, [rsp+120h+hstrNamespace]; this
0x1800f5cb0  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800f5cb5  lea     namespaces, [rsp+120h+hstrPrefix]; this
0x1800f5cba  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800f5cbf  lea     namespaces, [rsp+120h+iterator]; this
0x1800f5cc4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f5cc9  jmp     short loc_1800F5CDE
0x1800f5ccb  lea     phstrNamespaces, [rsp+120h+hstrNSs]; returnValue
0x1800f5cd0  mov     namespaces, rdi; prop
0x1800f5cd3  call    ?PropertyValueToHSTRING@@YAJPEAUIInspectable@@PEAPEAUHSTRING__@@@Z; PropertyValueToHSTRING(IInspectable *,HSTRING__ * *)
0x1800f5cd8  mov     ebx, eax
0x1800f5cda  test    eax, eax
0x1800f5cdc  js      short $CleanUp_229
0x1800f5cde  mov     rax, [rsp+120h+hstrNSs._hstring]
0x1800f5ce3  mov     [rsi], rax
0x1800f5ce6  mov     [rsp+120h+hstrNSs._hstring], r14
0x1800f5ceb  lea     namespaces, [rsp+120h+iterable]; this
0x1800f5cf0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f5cf5  lea     namespaces, [rsp+120h+hstrNSs]; this
0x1800f5cfa  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800f5cff  mov     eax, ebx
0x1800f5d01  mov     namespaces, [rbp+20h+var_20]
0x1800f5d05  xor     namespaces, rsp; StackCookie
0x1800f5d08  call    __security_check_cookie
0x1800f5d0d  lea     r11, [rsp+120h+var_10]
0x1800f5d15  mov     rbx, [r11+30h]
0x1800f5d19  mov     rsi, [r11+38h]
0x1800f5d1d  mov     rsp, r11
0x1800f5d20  pop     r14
0x1800f5d22  pop     rdi
0x1800f5d23  pop     rbp
0x1800f5d24  retn
```
