# DOMNode::_constructNamespacesStr(IInspectable *,HSTRING__ * *)

- ea: `0x100abdf5`
- end: `0x100ac1f0`
- name: `?_constructNamespacesStr@DOMNode@@KGJPAUIInspectable@@PAPAUHSTRING__@@@Z`
- size: `1019`
- prototype: `HRESULT __userpurge@<eax>(IInspectable *namespaces@<ecx>, HSTRING__ **phstrNamespaces@<edx>)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x100ab390`
- `0x100ab630`

## callees

- `0x10067bc0`
- `0x1006b510`
- `0x10073a99`
- `0x10090fd7`
- `0x100a92de`
- `0x100a9b47`
- `0x100abdf5`
- `0x10140af0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x100abec1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x100abef4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x100abec1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x100abef4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x100abfc1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x100ac025`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x100abfc1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x100ac025`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x100abeab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x100abee3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x100abeab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x100abee3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x100ac076`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x100ac076`

## string_xrefs

- `0x100abea6`: `xmlns`

## pseudocode

```c
HRESULT __fastcall DOMNode::_constructNamespacesStr(IInspectable *namespaces, HSTRING__ **phstrNamespaces)
{
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const _GUID *, void **); // esi
  Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *> *ptr; // esi
  HRESULT (__stdcall *First)(Windows::Foundation::Collections::IIterable_impl<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *> *, Windows::Foundation::Collections::IIterator<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *> **); // edi
  int v7; // esi
  int i; // eax
  Windows::Foundation::Collections::IIterator<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *> *v9; // esi
  HRESULT (__stdcall *get_Current)(Windows::Foundation::Collections::IIterator_impl<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *,1> *, Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> **); // edi
  Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *v11; // esi
  HRESULT (__stdcall *get_Key)(Windows::Foundation::Collections::IKeyValuePair_impl<HSTRING__ *,IInspectable *> *, HSTRING__ **); // edi
  Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *v13; // esi
  HRESULT (__stdcall *get_Value)(Windows::Foundation::Collections::IKeyValuePair_impl<HSTRING__ *,IInspectable *> *, IInspectable **); // edi
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *> > iterable; // [esp+Ch] [ebp-9Ch] BYREF
  Microsoft::WRL::ComPtr<IInspectable> value; // [esp+10h] [ebp-98h] BYREF
  Windows::Internal::String hstrNSs; // [esp+14h] [ebp-94h] BYREF
  Windows::Internal::String hstrNamespace; // [esp+18h] [ebp-90h] BYREF
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> > pKeyValuePair; // [esp+1Ch] [ebp-8Ch] BYREF
  Windows::Internal::String hstrPrefix; // [esp+20h] [ebp-88h] BYREF
  unsigned __int8 hasCurrent; // [esp+27h] [ebp-81h] BYREF
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *> > iterator; // [esp+28h] [ebp-80h] BYREF
  Windows::Internal::StringReference hstrSpace; // [esp+2Ch] [ebp-7Ch] BYREF
  Windows::Internal::StringReference hstrSingleQuote; // [esp+44h] [ebp-64h] BYREF
  Windows::Internal::StringReference hstrColon; // [esp+5Ch] [ebp-4Ch] BYREF
  Windows::Internal::StringReference hstrEqualAndSQuote; // [esp+74h] [ebp-34h] BYREF
  Windows::Internal::StringReference hstrXmlns; // [esp+8Ch] [ebp-1Ch] BYREF

  hstrNSs._hstring = 0;
  iterable.ptr_ = 0;
  QueryInterface = namespaces->QueryInterface;
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&iterable);
  if ( ((int (__thiscall *)(HRESULT (__stdcall *)(IUnknown *, const _GUID *, void **), IInspectable *, GUID *, Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *> > *))QueryInterface)(
         QueryInterface,
         namespaces,
         &_GUID_fe2f3d47_5d47_5499_8374_430c7cda0204,
         &iterable) < 0 )
  {
    v7 = PropertyValueToHSTRING(namespaces, &hstrNSs._hstring);
    if ( v7 < 0 )
      goto CleanUp_116;
LABEL_28:
    *phstrNamespaces = hstrNSs._hstring;
    hstrNSs._hstring = 0;
    goto CleanUp_116;
  }
  ptr = iterable.ptr_;
  iterator.ptr_ = 0;
  First = iterable.ptr_->First;
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&iterator);
  v7 = ((int (__thiscall *)(HRESULT (__stdcall *)(Windows::Foundation::Collections::IIterable_impl<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *> *, Windows::Foundation::Collections::IIterator<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *> **), Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *> *, Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *> > *))First)(
         First,
         ptr,
         &iterator);
  if ( v7 >= 0 )
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
    hasCurrent = 0;
    for ( i = ((int (__thiscall *)(HRESULT (__stdcall *)(Windows::Foundation::Collections::IIterator_impl<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *,1> *, unsigned __int8 *), Windows::Foundation::Collections::IIterator<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *> *, unsigned __int8 *))iterator.ptr_->get_HasCurrent)(
                iterator.ptr_->get_HasCurrent,
                iterator.ptr_,
                &hasCurrent);
          ;
          i = Windows::Internal::String::Concat(&hstrNSs, (const Windows::Internal::String *)&hstrSpace, &hstrNSs) )
    {
      v7 = i;
      if ( i < 0 )
        goto LABEL_10;
      if ( !hasCurrent )
        break;
      v9 = iterator.ptr_;
      get_Current = iterator.ptr_->get_Current;
      Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&pKeyValuePair);
      v7 = ((int (__thiscall *)(HRESULT (__stdcall *)(Windows::Foundation::Collections::IIterator_impl<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *,1> *, Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> **), Windows::Foundation::Collections::IIterator<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *> *, Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> > *))get_Current)(
             get_Current,
             v9,
             &pKeyValuePair);
      if ( v7 < 0 )
        goto LABEL_10;
      v11 = pKeyValuePair.ptr_;
      get_Key = pKeyValuePair.ptr_->get_Key;
      WindowsDeleteString(hstrPrefix._hstring);
      hstrPrefix._hstring = 0;
      v7 = ((int (__thiscall *)(HRESULT (__stdcall *)(Windows::Foundation::Collections::IKeyValuePair_impl<HSTRING__ *,IInspectable *> *, HSTRING__ **), Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *, Windows::Internal::String *))get_Key)(
             get_Key,
             v11,
             &hstrPrefix);
      if ( v7 < 0 )
        goto LABEL_10;
      v13 = pKeyValuePair.ptr_;
      get_Value = pKeyValuePair.ptr_->get_Value;
      Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&value);
      v7 = ((int (__thiscall *)(HRESULT (__stdcall *)(Windows::Foundation::Collections::IKeyValuePair_impl<HSTRING__ *,IInspectable *> *, IInspectable **), Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *, Microsoft::WRL::ComPtr<IInspectable> *))get_Value)(
             get_Value,
             v13,
             &value);
      if ( v7 < 0 )
        goto LABEL_10;
      WindowsDeleteString(hstrNamespace._hstring);
      hstrNamespace._hstring = 0;
      v7 = PropertyValueToHSTRING(value.ptr_, &hstrNamespace._hstring);
      if ( v7 < 0 )
        goto LABEL_10;
      v7 = Windows::Internal::String::Concat(&hstrNSs, (const Windows::Internal::String *)&hstrXmlns, &hstrNSs);
      if ( v7 < 0 )
        goto LABEL_10;
      if ( !WindowsIsStringEmpty(hstrPrefix._hstring) )
      {
        v7 = Windows::Internal::String::Concat(&hstrNSs, (const Windows::Internal::String *)&hstrColon, &hstrNSs);
        if ( v7 < 0 )
          goto LABEL_10;
        v7 = Windows::Internal::String::Concat(&hstrNSs, &hstrPrefix, &hstrNSs);
        if ( v7 < 0 )
          goto LABEL_10;
      }
      v7 = Windows::Internal::String::Concat(&hstrNSs, (const Windows::Internal::String *)&hstrEqualAndSQuote, &hstrNSs);
      if ( v7 < 0
        || (v7 = Windows::Internal::String::Concat(&hstrNSs, &hstrNamespace, &hstrNSs), v7 < 0)
        || (v7 = Windows::Internal::String::Concat(
                   &hstrNSs,
                   (const Windows::Internal::String *)&hstrSingleQuote,
                   &hstrNSs),
            v7 < 0)
        || (v7 = ((int (__thiscall *)(HRESULT (__stdcall *)(Windows::Foundation::Collections::IIterator_impl<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *,1> *, unsigned __int8 *), Windows::Foundation::Collections::IIterator<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *> *, unsigned __int8 *))iterator.ptr_->MoveNext)(
                   iterator.ptr_->MoveNext,
                   iterator.ptr_,
                   &hasCurrent),
            v7 < 0) )
      {
LABEL_10:
        Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&value);
        Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&pKeyValuePair);
        Windows::Internal::String::~String(&hstrNamespace);
        Windows::Internal::String::~String(&hstrPrefix);
        goto LABEL_3;
      }
      if ( !hasCurrent )
        break;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&value);
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&pKeyValuePair);
    Windows::Internal::String::~String(&hstrNamespace);
    Windows::Internal::String::~String(&hstrPrefix);
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&iterator);
    goto LABEL_28;
  }
LABEL_3:
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&iterator);
CleanUp_116:
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&iterable);
  Windows::Internal::String::~String(&hstrNSs);
  return v7;
}

```

## disassembly

```asm
0x100abdf5  mov     edi, edi
0x100abdf7  push    ebp
0x100abdf8  mov     ebp, esp
0x100abdfa  sub     esp, 9Ch
0x100abe00  mov     eax, ___security_cookie
0x100abe05  xor     eax, ebp
0x100abe07  mov     [ebp+var_4], eax
0x100abe0a  push    ebx
0x100abe0b  push    esi
0x100abe0c  push    edi
0x100abe0d  mov     edi, namespaces
0x100abe0f  mov     [ebp+hstrNSs._hstring], 0
0x100abe19  lea     namespaces, [ebp+iterable]; this
0x100abe1f  mov     [ebp+iterable.ptr_], 0
0x100abe29  mov     ebx, phstrNamespaces
0x100abe2b  mov     eax, [edi]
0x100abe2d  mov     esi, [eax]
0x100abe2f  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100abe34  lea     eax, [ebp+iterable]
0x100abe3a  mov     namespaces, esi; this
0x100abe3c  push    eax
0x100abe3d  push    offset __GUID_fe2f3d47_5d47_5499_8374_430c7cda0204
0x100abe42  push    edi
0x100abe43  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100abe49  call    esi
0x100abe4b  test    eax, eax
0x100abe4d  js      loc_100AC1A4
0x100abe53  mov     esi, [ebp+iterable.ptr_]
0x100abe59  lea     namespaces, [ebp+iterator]; this
0x100abe5c  mov     [ebp+iterator.ptr_], 0
0x100abe63  mov     eax, [esi]
0x100abe65  mov     edi, [eax+18h]
0x100abe68  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100abe6d  lea     eax, [ebp+iterator]
0x100abe70  mov     namespaces, edi; this
0x100abe72  push    eax
0x100abe73  push    esi
0x100abe74  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100abe7a  call    edi
0x100abe7c  mov     esi, eax
0x100abe7e  test    esi, esi
0x100abe80  jns     short loc_100ABE8F
0x100abe82  lea     namespaces, [ebp+iterator]; this
0x100abe85  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100abe8a  jmp     CleanUp_116
0x100abe8f  push    offset stringRef; " "
0x100abe94  lea     namespaces, [ebp+hstrSpace]; this
0x100abe97  call    ??$?0$01@StringReference@Internal@Windows@@QAE@AAY01$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[2])
0x100abe9c  lea     eax, [ebp+hstrXmlns]
0x100abe9f  push    eax; string
0x100abea0  lea     eax, [ebp+hstrXmlns._header]
0x100abea3  push    eax; hstringHeader
0x100abea4  push    5; length
0x100abea6  push    offset aXmlns; "xmlns"
0x100abeab  call    ds:__imp__WindowsCreateStringReference@16; WindowsCreateStringReference(x,x,x,x)
0x100abeb1  mov     esi, 0C000000Dh
0x100abeb6  test    eax, eax
0x100abeb8  jns     short loc_100ABEC7
0x100abeba  push    0; lpArguments
0x100abebc  push    0; nNumberOfArguments
0x100abebe  push    1; dwExceptionFlags
0x100abec0  push    esi; dwExceptionCode
0x100abec1  call    ds:__imp__RaiseException@16; RaiseException(x,x,x,x)
0x100abec7  push    offset text; ":"
0x100abecc  lea     namespaces, [ebp+hstrColon]; this
0x100abecf  call    ??$?0$01@StringReference@Internal@Windows@@QAE@AAY01$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[2])
0x100abed4  lea     eax, [ebp+hstrEqualAndSQuote]
0x100abed7  push    eax; string
0x100abed8  lea     eax, [ebp+hstrEqualAndSQuote._header]
0x100abedb  push    eax; hstringHeader
0x100abedc  push    2; length
0x100abede  push    offset asc_10030A08; "='"
0x100abee3  call    ds:__imp__WindowsCreateStringReference@16; WindowsCreateStringReference(x,x,x,x)
0x100abee9  test    eax, eax
0x100abeeb  jns     short loc_100ABEFA
0x100abeed  push    0; lpArguments
0x100abeef  push    0; nNumberOfArguments
0x100abef1  push    1; dwExceptionFlags
0x100abef3  push    esi; dwExceptionCode
0x100abef4  call    ds:__imp__RaiseException@16; RaiseException(x,x,x,x)
0x100abefa  push    offset asc_10030A10; "'"
0x100abeff  lea     namespaces, [ebp+hstrSingleQuote]; this
0x100abf02  call    ??$?0$01@StringReference@Internal@Windows@@QAE@AAY01$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[2])
0x100abf07  mov     namespaces, [ebp+iterator.ptr_]
0x100abf0a  xor     eax, eax
0x100abf0c  mov     [ebp+hstrPrefix._hstring], eax
0x100abf12  mov     [ebp+hstrNamespace._hstring], eax
0x100abf18  mov     [ebp+pKeyValuePair.ptr_], eax
0x100abf1e  mov     [ebp+value.ptr_], eax
0x100abf24  mov     [ebp+hasCurrent], al
0x100abf2a  mov     eax, [namespaces]
0x100abf2c  mov     esi, [eax+1Ch]
0x100abf2f  lea     eax, [ebp+hasCurrent]
0x100abf35  push    eax
0x100abf36  push    namespaces
0x100abf37  mov     namespaces, esi; this
0x100abf39  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100abf3f  call    esi
0x100abf41  mov     esi, eax
0x100abf43  test    esi, esi
0x100abf45  jns     short loc_100ABF78
0x100abf47  lea     namespaces, [ebp+value]; this
0x100abf4d  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100abf52  lea     namespaces, [ebp+pKeyValuePair]; this
0x100abf58  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100abf5d  lea     namespaces, [ebp+hstrNamespace]; this
0x100abf63  call    ??1String@Internal@Windows@@QAE@XZ; Windows::Internal::String::~String(void)
0x100abf68  lea     namespaces, [ebp+hstrPrefix]; this
0x100abf6e  call    ??1String@Internal@Windows@@QAE@XZ; Windows::Internal::String::~String(void)
0x100abf73  jmp     loc_100ABE82
0x100abf78  cmp     [ebp+hasCurrent], 0
0x100abf7f  jz      loc_100AC16E
0x100abf85  mov     esi, [ebp+iterator.ptr_]
0x100abf88  lea     namespaces, [ebp+pKeyValuePair]; this
0x100abf8e  mov     eax, [esi]
0x100abf90  mov     edi, [eax+18h]
0x100abf93  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100abf98  lea     eax, [ebp+pKeyValuePair]
0x100abf9e  mov     namespaces, edi; this
0x100abfa0  push    eax
0x100abfa1  push    esi
0x100abfa2  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100abfa8  call    edi
0x100abfaa  mov     esi, eax
0x100abfac  test    esi, esi
0x100abfae  js      short loc_100ABF47
0x100abfb0  mov     esi, [ebp+pKeyValuePair.ptr_]
0x100abfb6  push    [ebp+hstrPrefix._hstring]; string
0x100abfbc  mov     eax, [esi]
0x100abfbe  mov     edi, [eax+18h]
0x100abfc1  call    ds:__imp__WindowsDeleteString@4; WindowsDeleteString(x)
0x100abfc7  lea     eax, [ebp+hstrPrefix]
0x100abfcd  mov     [ebp+hstrPrefix._hstring], 0
0x100abfd7  push    eax
0x100abfd8  push    esi
0x100abfd9  mov     namespaces, edi; this
0x100abfdb  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100abfe1  call    edi
0x100abfe3  mov     esi, eax
0x100abfe5  lea     namespaces, [ebp+value]; this
0x100abfeb  test    esi, esi
0x100abfed  js      loc_100ABF4D
0x100abff3  mov     esi, [ebp+pKeyValuePair.ptr_]
0x100abff9  mov     eax, [esi]
0x100abffb  mov     edi, [eax+1Ch]
0x100abffe  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100ac003  lea     eax, [ebp+value]
0x100ac009  mov     namespaces, edi; this
0x100ac00b  push    eax
0x100ac00c  push    esi
0x100ac00d  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100ac013  call    edi
0x100ac015  mov     esi, eax
0x100ac017  test    esi, esi
0x100ac019  js      loc_100ABF47
0x100ac01f  push    [ebp+hstrNamespace._hstring]; string
0x100ac025  call    ds:__imp__WindowsDeleteString@4; WindowsDeleteString(x)
0x100ac02b  mov     namespaces, [ebp+value.ptr_]; prop
0x100ac031  lea     phstrNamespaces, [ebp+hstrNamespace]; returnValue
0x100ac037  mov     [ebp+hstrNamespace._hstring], 0
0x100ac041  call    ?PropertyValueToHSTRING@@YGJPAUIInspectable@@PAPAUHSTRING__@@@Z; PropertyValueToHSTRING(IInspectable *,HSTRING__ * *)
0x100ac046  mov     esi, eax
0x100ac048  test    esi, esi
0x100ac04a  js      loc_100ABF47
0x100ac050  lea     eax, [ebp+hstrNSs]
0x100ac056  push    eax; newString
0x100ac057  lea     eax, [ebp+hstrXmlns]
0x100ac05a  push    eax; string
0x100ac05b  lea     namespaces, [ebp+hstrNSs]; this
0x100ac061  call    ?Concat@String@Internal@Windows@@QBEJABV123@PAV123@@Z; Windows::Internal::String::Concat(Windows::Internal::String const &,Windows::Internal::String *)
0x100ac066  mov     esi, eax
0x100ac068  test    esi, esi
0x100ac06a  js      loc_100ABF47
0x100ac070  push    [ebp+hstrPrefix._hstring]; string
0x100ac076  call    ds:__imp__WindowsIsStringEmpty@4; WindowsIsStringEmpty(x)
0x100ac07c  test    eax, eax
0x100ac07e  jnz     short loc_100AC0C3
0x100ac080  lea     eax, [ebp+hstrNSs]
0x100ac086  push    eax; newString
0x100ac087  lea     eax, [ebp+hstrColon]
0x100ac08a  push    eax; string
0x100ac08b  lea     namespaces, [ebp+hstrNSs]; this
0x100ac091  call    ?Concat@String@Internal@Windows@@QBEJABV123@PAV123@@Z; Windows::Internal::String::Concat(Windows::Internal::String const &,Windows::Internal::String *)
0x100ac096  mov     esi, eax
0x100ac098  test    esi, esi
0x100ac09a  js      loc_100ABF47
0x100ac0a0  lea     eax, [ebp+hstrNSs]
0x100ac0a6  push    eax; newString
0x100ac0a7  lea     eax, [ebp+hstrPrefix]
0x100ac0ad  push    eax; string
0x100ac0ae  lea     namespaces, [ebp+hstrNSs]; this
0x100ac0b4  call    ?Concat@String@Internal@Windows@@QBEJABV123@PAV123@@Z; Windows::Internal::String::Concat(Windows::Internal::String const &,Windows::Internal::String *)
0x100ac0b9  mov     esi, eax
0x100ac0bb  test    esi, esi
0x100ac0bd  js      loc_100ABF47
0x100ac0c3  lea     eax, [ebp+hstrNSs]
0x100ac0c9  push    eax; newString
0x100ac0ca  lea     eax, [ebp+hstrEqualAndSQuote]
0x100ac0cd  push    eax; string
0x100ac0ce  lea     namespaces, [ebp+hstrNSs]; this
0x100ac0d4  call    ?Concat@String@Internal@Windows@@QBEJABV123@PAV123@@Z; Windows::Internal::String::Concat(Windows::Internal::String const &,Windows::Internal::String *)
0x100ac0d9  mov     esi, eax
0x100ac0db  test    esi, esi
0x100ac0dd  js      loc_100ABF47
0x100ac0e3  lea     eax, [ebp+hstrNSs]
0x100ac0e9  push    eax; newString
0x100ac0ea  lea     eax, [ebp+hstrNamespace]
0x100ac0f0  push    eax; string
0x100ac0f1  lea     namespaces, [ebp+hstrNSs]; this
0x100ac0f7  call    ?Concat@String@Internal@Windows@@QBEJABV123@PAV123@@Z; Windows::Internal::String::Concat(Windows::Internal::String const &,Windows::Internal::String *)
0x100ac0fc  mov     esi, eax
0x100ac0fe  test    esi, esi
0x100ac100  js      loc_100ABF47
0x100ac106  lea     eax, [ebp+hstrNSs]
0x100ac10c  push    eax; newString
0x100ac10d  lea     eax, [ebp+hstrSingleQuote]
0x100ac110  push    eax; string
0x100ac111  lea     namespaces, [ebp+hstrNSs]; this
0x100ac117  call    ?Concat@String@Internal@Windows@@QBEJABV123@PAV123@@Z; Windows::Internal::String::Concat(Windows::Internal::String const &,Windows::Internal::String *)
0x100ac11c  mov     esi, eax
0x100ac11e  test    esi, esi
0x100ac120  js      loc_100ABF47
0x100ac126  mov     namespaces, [ebp+iterator.ptr_]
0x100ac129  mov     eax, [namespaces]
0x100ac12b  mov     esi, [eax+20h]
0x100ac12e  lea     eax, [ebp+hasCurrent]
0x100ac134  push    eax
0x100ac135  push    namespaces
0x100ac136  mov     namespaces, esi; this
0x100ac138  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100ac13e  call    esi
0x100ac140  mov     esi, eax
0x100ac142  test    esi, esi
0x100ac144  js      loc_100ABF47
0x100ac14a  cmp     [ebp+hasCurrent], 0
0x100ac151  jz      short loc_100AC16E
0x100ac153  lea     eax, [ebp+hstrNSs]
0x100ac159  push    eax; newString
0x100ac15a  lea     eax, [ebp+hstrSpace]
0x100ac15d  push    eax; string
0x100ac15e  lea     namespaces, [ebp+hstrNSs]; this
0x100ac164  call    ?Concat@String@Internal@Windows@@QBEJABV123@PAV123@@Z; Windows::Internal::String::Concat(Windows::Internal::String const &,Windows::Internal::String *)
0x100ac169  jmp     loc_100ABF41
0x100ac16e  lea     namespaces, [ebp+value]; this
0x100ac174  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100ac179  lea     namespaces, [ebp+pKeyValuePair]; this
0x100ac17f  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100ac184  lea     namespaces, [ebp+hstrNamespace]; this
0x100ac18a  call    ??1String@Internal@Windows@@QAE@XZ; Windows::Internal::String::~String(void)
0x100ac18f  lea     namespaces, [ebp+hstrPrefix]; this
0x100ac195  call    ??1String@Internal@Windows@@QAE@XZ; Windows::Internal::String::~String(void)
0x100ac19a  lea     namespaces, [ebp+iterator]; this
0x100ac19d  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100ac1a2  jmp     short loc_100AC1B7
0x100ac1a4  lea     phstrNamespaces, [ebp+hstrNSs]; returnValue
0x100ac1aa  mov     namespaces, edi; prop
0x100ac1ac  call    ?PropertyValueToHSTRING@@YGJPAUIInspectable@@PAPAUHSTRING__@@@Z; PropertyValueToHSTRING(IInspectable *,HSTRING__ * *)
0x100ac1b1  mov     esi, eax
0x100ac1b3  test    esi, esi
0x100ac1b5  js      short CleanUp_116
0x100ac1b7  mov     eax, [ebp+hstrNSs._hstring]
0x100ac1bd  mov     [ebx], eax
0x100ac1bf  mov     [ebp+hstrNSs._hstring], 0
0x100ac1c9  lea     namespaces, [ebp+iterable]; this
0x100ac1cf  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100ac1d4  lea     namespaces, [ebp+hstrNSs]; this
0x100ac1da  call    ??1String@Internal@Windows@@QAE@XZ; Windows::Internal::String::~String(void)
0x100ac1df  mov     namespaces, [ebp+var_4]
0x100ac1e2  mov     eax, esi
0x100ac1e4  pop     edi
0x100ac1e5  pop     esi
0x100ac1e6  xor     namespaces, ebp; cookie
0x100ac1e8  pop     ebx
0x100ac1e9  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100ac1ee  leave
0x100ac1ef  retn
```
