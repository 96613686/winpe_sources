# DOMNode::_constructNamespacesStr(IInspectable *,HSTRING__ * *)

- ea: `0x100abf05`
- end: `0x100ac300`
- name: `?_constructNamespacesStr@DOMNode@@KGJPAUIInspectable@@PAPAUHSTRING__@@@Z`
- size: `1019`
- prototype: `HRESULT __userpurge@<eax>(IInspectable *namespaces@<ecx>, HSTRING__ **phstrNamespaces@<edx>)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x100ab4a0`
- `0x100ab740`

## callees

- `0x10067b20`
- `0x1006b470`
- `0x10073ac9`
- `0x100910a1`
- `0x100a93ee`
- `0x100a9c57`
- `0x100abf05`
- `0x10140c00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x100abfd1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x100ac004`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x100abfd1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x100ac004`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x100ac0d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x100ac135`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x100ac0d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x100ac135`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x100abfbb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x100abff3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x100abfbb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x100abff3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x100ac186`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x100ac186`

## string_xrefs

- `0x100abfb6`: `xmlns`

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
0x100abf05  mov     edi, edi
0x100abf07  push    ebp
0x100abf08  mov     ebp, esp
0x100abf0a  sub     esp, 9Ch
0x100abf10  mov     eax, ___security_cookie
0x100abf15  xor     eax, ebp
0x100abf17  mov     [ebp+var_4], eax
0x100abf1a  push    ebx
0x100abf1b  push    esi
0x100abf1c  push    edi
0x100abf1d  mov     edi, namespaces
0x100abf1f  mov     [ebp+hstrNSs._hstring], 0
0x100abf29  lea     namespaces, [ebp+iterable]; this
0x100abf2f  mov     [ebp+iterable.ptr_], 0
0x100abf39  mov     ebx, phstrNamespaces
0x100abf3b  mov     eax, [edi]
0x100abf3d  mov     esi, [eax]
0x100abf3f  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100abf44  lea     eax, [ebp+iterable]
0x100abf4a  mov     namespaces, esi; this
0x100abf4c  push    eax
0x100abf4d  push    offset __GUID_fe2f3d47_5d47_5499_8374_430c7cda0204
0x100abf52  push    edi
0x100abf53  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100abf59  call    esi
0x100abf5b  test    eax, eax
0x100abf5d  js      loc_100AC2B4
0x100abf63  mov     esi, [ebp+iterable.ptr_]
0x100abf69  lea     namespaces, [ebp+iterator]; this
0x100abf6c  mov     [ebp+iterator.ptr_], 0
0x100abf73  mov     eax, [esi]
0x100abf75  mov     edi, [eax+18h]
0x100abf78  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100abf7d  lea     eax, [ebp+iterator]
0x100abf80  mov     namespaces, edi; this
0x100abf82  push    eax
0x100abf83  push    esi
0x100abf84  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100abf8a  call    edi
0x100abf8c  mov     esi, eax
0x100abf8e  test    esi, esi
0x100abf90  jns     short loc_100ABF9F
0x100abf92  lea     namespaces, [ebp+iterator]; this
0x100abf95  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100abf9a  jmp     CleanUp_116
0x100abf9f  push    offset stringRef; " "
0x100abfa4  lea     namespaces, [ebp+hstrSpace]; this
0x100abfa7  call    ??$?0$01@StringReference@Internal@Windows@@QAE@AAY01$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[2])
0x100abfac  lea     eax, [ebp+hstrXmlns]
0x100abfaf  push    eax; string
0x100abfb0  lea     eax, [ebp+hstrXmlns._header]
0x100abfb3  push    eax; hstringHeader
0x100abfb4  push    5; length
0x100abfb6  push    offset aXmlns_0; "xmlns"
0x100abfbb  call    ds:__imp__WindowsCreateStringReference@16; WindowsCreateStringReference(x,x,x,x)
0x100abfc1  mov     esi, 0C000000Dh
0x100abfc6  test    eax, eax
0x100abfc8  jns     short loc_100ABFD7
0x100abfca  push    0; lpArguments
0x100abfcc  push    0; nNumberOfArguments
0x100abfce  push    1; dwExceptionFlags
0x100abfd0  push    esi; dwExceptionCode
0x100abfd1  call    ds:__imp__RaiseException@16; RaiseException(x,x,x,x)
0x100abfd7  push    offset text; ":"
0x100abfdc  lea     namespaces, [ebp+hstrColon]; this
0x100abfdf  call    ??$?0$01@StringReference@Internal@Windows@@QAE@AAY01$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[2])
0x100abfe4  lea     eax, [ebp+hstrEqualAndSQuote]
0x100abfe7  push    eax; string
0x100abfe8  lea     eax, [ebp+hstrEqualAndSQuote._header]
0x100abfeb  push    eax; hstringHeader
0x100abfec  push    2; length
0x100abfee  push    offset asc_100309F8; "='"
0x100abff3  call    ds:__imp__WindowsCreateStringReference@16; WindowsCreateStringReference(x,x,x,x)
0x100abff9  test    eax, eax
0x100abffb  jns     short loc_100AC00A
0x100abffd  push    0; lpArguments
0x100abfff  push    0; nNumberOfArguments
0x100ac001  push    1; dwExceptionFlags
0x100ac003  push    esi; dwExceptionCode
0x100ac004  call    ds:__imp__RaiseException@16; RaiseException(x,x,x,x)
0x100ac00a  push    offset asc_10030A00; "'"
0x100ac00f  lea     namespaces, [ebp+hstrSingleQuote]; this
0x100ac012  call    ??$?0$01@StringReference@Internal@Windows@@QAE@AAY01$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[2])
0x100ac017  mov     namespaces, [ebp+iterator.ptr_]
0x100ac01a  xor     eax, eax
0x100ac01c  mov     [ebp+hstrPrefix._hstring], eax
0x100ac022  mov     [ebp+hstrNamespace._hstring], eax
0x100ac028  mov     [ebp+pKeyValuePair.ptr_], eax
0x100ac02e  mov     [ebp+value.ptr_], eax
0x100ac034  mov     [ebp+hasCurrent], al
0x100ac03a  mov     eax, [namespaces]
0x100ac03c  mov     esi, [eax+1Ch]
0x100ac03f  lea     eax, [ebp+hasCurrent]
0x100ac045  push    eax
0x100ac046  push    namespaces
0x100ac047  mov     namespaces, esi; this
0x100ac049  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100ac04f  call    esi
0x100ac051  mov     esi, eax
0x100ac053  test    esi, esi
0x100ac055  jns     short loc_100AC088
0x100ac057  lea     namespaces, [ebp+value]; this
0x100ac05d  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100ac062  lea     namespaces, [ebp+pKeyValuePair]; this
0x100ac068  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100ac06d  lea     namespaces, [ebp+hstrNamespace]; this
0x100ac073  call    ??1String@Internal@Windows@@QAE@XZ; Windows::Internal::String::~String(void)
0x100ac078  lea     namespaces, [ebp+hstrPrefix]; this
0x100ac07e  call    ??1String@Internal@Windows@@QAE@XZ; Windows::Internal::String::~String(void)
0x100ac083  jmp     loc_100ABF92
0x100ac088  cmp     [ebp+hasCurrent], 0
0x100ac08f  jz      loc_100AC27E
0x100ac095  mov     esi, [ebp+iterator.ptr_]
0x100ac098  lea     namespaces, [ebp+pKeyValuePair]; this
0x100ac09e  mov     eax, [esi]
0x100ac0a0  mov     edi, [eax+18h]
0x100ac0a3  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100ac0a8  lea     eax, [ebp+pKeyValuePair]
0x100ac0ae  mov     namespaces, edi; this
0x100ac0b0  push    eax
0x100ac0b1  push    esi
0x100ac0b2  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100ac0b8  call    edi
0x100ac0ba  mov     esi, eax
0x100ac0bc  test    esi, esi
0x100ac0be  js      short loc_100AC057
0x100ac0c0  mov     esi, [ebp+pKeyValuePair.ptr_]
0x100ac0c6  push    [ebp+hstrPrefix._hstring]; string
0x100ac0cc  mov     eax, [esi]
0x100ac0ce  mov     edi, [eax+18h]
0x100ac0d1  call    ds:__imp__WindowsDeleteString@4; WindowsDeleteString(x)
0x100ac0d7  lea     eax, [ebp+hstrPrefix]
0x100ac0dd  mov     [ebp+hstrPrefix._hstring], 0
0x100ac0e7  push    eax
0x100ac0e8  push    esi
0x100ac0e9  mov     namespaces, edi; this
0x100ac0eb  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100ac0f1  call    edi
0x100ac0f3  mov     esi, eax
0x100ac0f5  lea     namespaces, [ebp+value]; this
0x100ac0fb  test    esi, esi
0x100ac0fd  js      loc_100AC05D
0x100ac103  mov     esi, [ebp+pKeyValuePair.ptr_]
0x100ac109  mov     eax, [esi]
0x100ac10b  mov     edi, [eax+1Ch]
0x100ac10e  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100ac113  lea     eax, [ebp+value]
0x100ac119  mov     namespaces, edi; this
0x100ac11b  push    eax
0x100ac11c  push    esi
0x100ac11d  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100ac123  call    edi
0x100ac125  mov     esi, eax
0x100ac127  test    esi, esi
0x100ac129  js      loc_100AC057
0x100ac12f  push    [ebp+hstrNamespace._hstring]; string
0x100ac135  call    ds:__imp__WindowsDeleteString@4; WindowsDeleteString(x)
0x100ac13b  mov     namespaces, [ebp+value.ptr_]; prop
0x100ac141  lea     phstrNamespaces, [ebp+hstrNamespace]; returnValue
0x100ac147  mov     [ebp+hstrNamespace._hstring], 0
0x100ac151  call    ?PropertyValueToHSTRING@@YGJPAUIInspectable@@PAPAUHSTRING__@@@Z; PropertyValueToHSTRING(IInspectable *,HSTRING__ * *)
0x100ac156  mov     esi, eax
0x100ac158  test    esi, esi
0x100ac15a  js      loc_100AC057
0x100ac160  lea     eax, [ebp+hstrNSs]
0x100ac166  push    eax; newString
0x100ac167  lea     eax, [ebp+hstrXmlns]
0x100ac16a  push    eax; string
0x100ac16b  lea     namespaces, [ebp+hstrNSs]; this
0x100ac171  call    ?Concat@String@Internal@Windows@@QBEJABV123@PAV123@@Z; Windows::Internal::String::Concat(Windows::Internal::String const &,Windows::Internal::String *)
0x100ac176  mov     esi, eax
0x100ac178  test    esi, esi
0x100ac17a  js      loc_100AC057
0x100ac180  push    [ebp+hstrPrefix._hstring]; string
0x100ac186  call    ds:__imp__WindowsIsStringEmpty@4; WindowsIsStringEmpty(x)
0x100ac18c  test    eax, eax
0x100ac18e  jnz     short loc_100AC1D3
0x100ac190  lea     eax, [ebp+hstrNSs]
0x100ac196  push    eax; newString
0x100ac197  lea     eax, [ebp+hstrColon]
0x100ac19a  push    eax; string
0x100ac19b  lea     namespaces, [ebp+hstrNSs]; this
0x100ac1a1  call    ?Concat@String@Internal@Windows@@QBEJABV123@PAV123@@Z; Windows::Internal::String::Concat(Windows::Internal::String const &,Windows::Internal::String *)
0x100ac1a6  mov     esi, eax
0x100ac1a8  test    esi, esi
0x100ac1aa  js      loc_100AC057
0x100ac1b0  lea     eax, [ebp+hstrNSs]
0x100ac1b6  push    eax; newString
0x100ac1b7  lea     eax, [ebp+hstrPrefix]
0x100ac1bd  push    eax; string
0x100ac1be  lea     namespaces, [ebp+hstrNSs]; this
0x100ac1c4  call    ?Concat@String@Internal@Windows@@QBEJABV123@PAV123@@Z; Windows::Internal::String::Concat(Windows::Internal::String const &,Windows::Internal::String *)
0x100ac1c9  mov     esi, eax
0x100ac1cb  test    esi, esi
0x100ac1cd  js      loc_100AC057
0x100ac1d3  lea     eax, [ebp+hstrNSs]
0x100ac1d9  push    eax; newString
0x100ac1da  lea     eax, [ebp+hstrEqualAndSQuote]
0x100ac1dd  push    eax; string
0x100ac1de  lea     namespaces, [ebp+hstrNSs]; this
0x100ac1e4  call    ?Concat@String@Internal@Windows@@QBEJABV123@PAV123@@Z; Windows::Internal::String::Concat(Windows::Internal::String const &,Windows::Internal::String *)
0x100ac1e9  mov     esi, eax
0x100ac1eb  test    esi, esi
0x100ac1ed  js      loc_100AC057
0x100ac1f3  lea     eax, [ebp+hstrNSs]
0x100ac1f9  push    eax; newString
0x100ac1fa  lea     eax, [ebp+hstrNamespace]
0x100ac200  push    eax; string
0x100ac201  lea     namespaces, [ebp+hstrNSs]; this
0x100ac207  call    ?Concat@String@Internal@Windows@@QBEJABV123@PAV123@@Z; Windows::Internal::String::Concat(Windows::Internal::String const &,Windows::Internal::String *)
0x100ac20c  mov     esi, eax
0x100ac20e  test    esi, esi
0x100ac210  js      loc_100AC057
0x100ac216  lea     eax, [ebp+hstrNSs]
0x100ac21c  push    eax; newString
0x100ac21d  lea     eax, [ebp+hstrSingleQuote]
0x100ac220  push    eax; string
0x100ac221  lea     namespaces, [ebp+hstrNSs]; this
0x100ac227  call    ?Concat@String@Internal@Windows@@QBEJABV123@PAV123@@Z; Windows::Internal::String::Concat(Windows::Internal::String const &,Windows::Internal::String *)
0x100ac22c  mov     esi, eax
0x100ac22e  test    esi, esi
0x100ac230  js      loc_100AC057
0x100ac236  mov     namespaces, [ebp+iterator.ptr_]
0x100ac239  mov     eax, [namespaces]
0x100ac23b  mov     esi, [eax+20h]
0x100ac23e  lea     eax, [ebp+hasCurrent]
0x100ac244  push    eax
0x100ac245  push    namespaces
0x100ac246  mov     namespaces, esi; this
0x100ac248  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100ac24e  call    esi
0x100ac250  mov     esi, eax
0x100ac252  test    esi, esi
0x100ac254  js      loc_100AC057
0x100ac25a  cmp     [ebp+hasCurrent], 0
0x100ac261  jz      short loc_100AC27E
0x100ac263  lea     eax, [ebp+hstrNSs]
0x100ac269  push    eax; newString
0x100ac26a  lea     eax, [ebp+hstrSpace]
0x100ac26d  push    eax; string
0x100ac26e  lea     namespaces, [ebp+hstrNSs]; this
0x100ac274  call    ?Concat@String@Internal@Windows@@QBEJABV123@PAV123@@Z; Windows::Internal::String::Concat(Windows::Internal::String const &,Windows::Internal::String *)
0x100ac279  jmp     loc_100AC051
0x100ac27e  lea     namespaces, [ebp+value]; this
0x100ac284  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100ac289  lea     namespaces, [ebp+pKeyValuePair]; this
0x100ac28f  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100ac294  lea     namespaces, [ebp+hstrNamespace]; this
0x100ac29a  call    ??1String@Internal@Windows@@QAE@XZ; Windows::Internal::String::~String(void)
0x100ac29f  lea     namespaces, [ebp+hstrPrefix]; this
0x100ac2a5  call    ??1String@Internal@Windows@@QAE@XZ; Windows::Internal::String::~String(void)
0x100ac2aa  lea     namespaces, [ebp+iterator]; this
0x100ac2ad  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100ac2b2  jmp     short loc_100AC2C7
0x100ac2b4  lea     phstrNamespaces, [ebp+hstrNSs]; returnValue
0x100ac2ba  mov     namespaces, edi; prop
0x100ac2bc  call    ?PropertyValueToHSTRING@@YGJPAUIInspectable@@PAPAUHSTRING__@@@Z; PropertyValueToHSTRING(IInspectable *,HSTRING__ * *)
0x100ac2c1  mov     esi, eax
0x100ac2c3  test    esi, esi
0x100ac2c5  js      short CleanUp_116
0x100ac2c7  mov     eax, [ebp+hstrNSs._hstring]
0x100ac2cd  mov     [ebx], eax
0x100ac2cf  mov     [ebp+hstrNSs._hstring], 0
0x100ac2d9  lea     namespaces, [ebp+iterable]; this
0x100ac2df  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x100ac2e4  lea     namespaces, [ebp+hstrNSs]; this
0x100ac2ea  call    ??1String@Internal@Windows@@QAE@XZ; Windows::Internal::String::~String(void)
0x100ac2ef  mov     namespaces, [ebp+var_4]
0x100ac2f2  mov     eax, esi
0x100ac2f4  pop     edi
0x100ac2f5  pop     esi
0x100ac2f6  xor     namespaces, ebp; cookie
0x100ac2f8  pop     ebx
0x100ac2f9  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100ac2fe  leave
0x100ac2ff  retn
```
