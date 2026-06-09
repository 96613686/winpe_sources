# CEnumCategoriesOfCatalogClass::Next(ulong,_GUID *,ulong *)

- ea: `0x1800ad440`
- end: `0x1800ad613`
- name: `?Next@CEnumCategoriesOfCatalogClass@@UEAAJKPEAU_GUID@@PEAK@Z`
- size: `467`
- prototype: `HRESULT __fastcall(CEnumCategoriesOfCatalogClass *this, unsigned int celt, _GUID *rgelt, unsigned int *pceltFetched)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000a0e8`
- `0x1800185ec`
- `0x1800ad440`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800ad557`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800ad557`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad519`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad589`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad5c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad519`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad589`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad5c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ad544`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ad544`

## string_xrefs

- `0x1800ad47a`: `com\ole32\comcat\src\catenum.cpp`
- `0x1800ad5b5`: `com\ole32\comcat\src\catenum.cpp`
- `0x1800ad5d8`: `com\ole32\comcat\src\catenum.cpp`

## pseudocode

```c
__int64 __fastcall CEnumCategoriesOfCatalogClass::Next(
        CEnumCategoriesOfCatalogClass *this,
        unsigned int celt,
        _GUID *rgelt,
        unsigned int *pceltFetched)
{
  HRESULT v8; // ebx
  unsigned int v9; // edx
  Windows::Foundation::Collections::IIterator<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *> *ptr; // rcx
  unsigned int v12; // r14d
  Windows::Foundation::Collections::IIterator<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *> *v13; // rdi
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
  HRESULT v15; // eax
  Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *v16; // rdi
  HRESULT (__stdcall *v17)(IUnknown *, const IID *const, void **); // rbx
  HRESULT v18; // eax
  const OLECHAR *StringRawBuffer; // rax
  unsigned int v20; // edx
  Microsoft::WRL::Wrappers::HString categoryString; // [rsp+20h] [rbp-18h] BYREF
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> > keyValuePair; // [rsp+28h] [rbp-10h] BYREF
  void *retaddr; // [rsp+78h] [rbp+40h]
  unsigned __int8 hasCurrent; // [rsp+88h] [rbp+50h] BYREF

  if ( celt <= 1 )
  {
    if ( !pceltFetched )
      goto LABEL_8;
  }
  else if ( !pceltFetched )
  {
    v8 = -2147024809;
    v9 = 547;
    goto LABEL_4;
  }
  *pceltFetched = 0;
LABEL_8:
  ptr = this->_categoriesIterator.ptr_;
  hasCurrent = 0;
  v8 = ((__int64 (__fastcall *)(Windows::Foundation::Collections::IIterator<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *> *, unsigned __int8 *))ptr->lpVtbl[2].AddRef)(
         ptr,
         &hasCurrent);
  if ( v8 < 0 )
  {
    v9 = 555;
LABEL_4:
    wil::details::in1diag3::Return_Hr(retaddr, v9, "com\\ole32\\comcat\\src\\catenum.cpp", v8);
    return (unsigned int)v8;
  }
  v12 = 0;
  while ( v12 < celt && hasCurrent )
  {
    keyValuePair.ptr_ = 0;
    v13 = this->_categoriesIterator.ptr_;
    QueryInterface = v13->lpVtbl[2].QueryInterface;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<ITypeLibRegistrationReader> *)&keyValuePair);
    v15 = ((__int64 (__fastcall *)(Windows::Foundation::Collections::IIterator<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *> *, Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> > *))QueryInterface)(
            v13,
            &keyValuePair);
    v8 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, 0x231u, "com\\ole32\\comcat\\src\\catenum.cpp", v15);
      goto LABEL_25;
    }
    v16 = keyValuePair.ptr_;
    categoryString.hstr_ = 0;
    v17 = keyValuePair.ptr_->lpVtbl[2].QueryInterface;
    WindowsDeleteString(0);
    categoryString.hstr_ = 0;
    v18 = ((__int64 (__fastcall *)(Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *, Microsoft::WRL::Wrappers::HString *))v17)(
            v16,
            &categoryString);
    v8 = v18;
    if ( v18 < 0 )
    {
      v20 = 564;
LABEL_23:
      wil::details::in1diag3::Return_Hr(retaddr, v20, "com\\ole32\\comcat\\src\\catenum.cpp", v18);
      WindowsDeleteString(categoryString.hstr_);
      categoryString.hstr_ = 0;
LABEL_25:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<ITypeLibRegistrationReader> *)&keyValuePair);
      return (unsigned int)v8;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(categoryString.hstr_, 0);
    if ( IIDFromString(StringRawBuffer, &rgelt[v12]) >= 0 )
    {
      if ( pceltFetched )
        ++*pceltFetched;
      ++v12;
    }
    v18 = ((__int64 (__fastcall *)(Windows::Foundation::Collections::IIterator<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *> *, unsigned __int8 *))this->_categoriesIterator.ptr_->lpVtbl[2].Release)(
            this->_categoriesIterator.ptr_,
            &hasCurrent);
    v8 = v18;
    if ( v18 < 0 )
    {
      v20 = 576;
      goto LABEL_23;
    }
    WindowsDeleteString(categoryString.hstr_);
    categoryString.hstr_ = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<ITypeLibRegistrationReader> *)&keyValuePair);
    ++this->_iteratorPosition;
  }
  return v12 < celt;
}

```

## disassembly

```asm
0x1800ad440  push    rbp
0x1800ad442  push    rbx
0x1800ad443  push    rsi
0x1800ad444  push    rdi
0x1800ad445  push    r12
0x1800ad447  push    r13
0x1800ad449  push    r14
0x1800ad44b  push    r15
0x1800ad44d  mov     rbp, rsp
0x1800ad450  sub     rsp, 38h
0x1800ad454  xor     edi, edi
0x1800ad456  mov     rsi, pceltFetched
0x1800ad459  mov     r13, rgelt
0x1800ad45c  mov     r12d, celt
0x1800ad45f  mov     r15, this
0x1800ad462  cmp     celt, 1
0x1800ad465  jbe     short loc_1800AD490
0x1800ad467  test    pceltFetched, pceltFetched
0x1800ad46a  jnz     short loc_1800AD495
0x1800ad46c  mov     ebx, 80070057h
0x1800ad471  mov     celt, 223h; lineNumber
0x1800ad476  mov     this, [rbp+40h]; callerReturnAddress
0x1800ad47a  lea     rgelt, aComOle32Comcat_0; "com\\ole32\\comcat\\src\\catenum.cpp"
0x1800ad481  mov     r9d, ebx; hr
0x1800ad484  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ad489  mov     eax, ebx
0x1800ad48b  jmp     loc_1800AD602
0x1800ad490  test    rsi, rsi
0x1800ad493  jz      short loc_1800AD498
0x1800ad495  mov     [pceltFetched], edi
0x1800ad498  mov     this, [this+18h]
0x1800ad49c  lea     rdx, [rbp+hasCurrent]
0x1800ad4a0  mov     [rbp+hasCurrent], dil
0x1800ad4a4  mov     rax, [this]
0x1800ad4a7  mov     rax, [rax+38h]
0x1800ad4ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad4b0  mov     ebx, eax
0x1800ad4b2  test    eax, eax
0x1800ad4b4  jns     short loc_1800AD4BD
0x1800ad4b6  mov     celt, 22Bh
0x1800ad4bb  jmp     short loc_1800AD476
0x1800ad4bd  mov     r14d, edi
0x1800ad4c0  cmp     r14d, r12d
0x1800ad4c3  jnb     loc_1800AD5FA
0x1800ad4c9  cmp     [rbp+hasCurrent], dil
0x1800ad4cd  jz      loc_1800AD5FA
0x1800ad4d3  mov     [rbp+keyValuePair.ptr_], rdi
0x1800ad4d7  lea     this, [rbp+keyValuePair]; this
0x1800ad4db  mov     rdi, [r15+18h]
0x1800ad4df  mov     rax, [rdi]
0x1800ad4e2  mov     rbx, [rax+30h]
0x1800ad4e6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ad4eb  lea     rdx, [rbp+keyValuePair]
0x1800ad4ef  mov     this, rdi
0x1800ad4f2  mov     rax, rbx
0x1800ad4f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad4fa  mov     ebx, eax
0x1800ad4fc  test    eax, eax
0x1800ad4fe  js      loc_1800AD5D4
0x1800ad504  mov     rdi, [rbp+keyValuePair.ptr_]
0x1800ad508  xor     ecx, ecx; string
0x1800ad50a  mov     [rbp+categoryString.hstr_], 0
0x1800ad512  mov     rax, [rdi]
0x1800ad515  mov     rbx, [rax+30h]
0x1800ad519  call    cs:__imp_WindowsDeleteString
0x1800ad51f  lea     rdx, [rbp+categoryString]
0x1800ad523  mov     [rbp+categoryString.hstr_], 0
0x1800ad52b  mov     this, rdi
0x1800ad52e  mov     rax, rbx
0x1800ad531  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad536  xor     edi, edi
0x1800ad538  mov     ebx, eax
0x1800ad53a  test    eax, eax
0x1800ad53c  js      short loc_1800AD5AC
0x1800ad53e  mov     this, [rbp+categoryString.hstr_]; string
0x1800ad542  xor     celt, celt; length
0x1800ad544  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ad54a  mov     celt, r14d
0x1800ad54d  mov     this, rax; lpsz
0x1800ad550  shl     rdx, 4
0x1800ad554  add     rdx, r13; lpiid
0x1800ad557  call    cs:__imp_IIDFromString
0x1800ad55d  test    eax, eax
0x1800ad55f  js      short loc_1800AD56B
0x1800ad561  test    rsi, rsi
0x1800ad564  jz      short loc_1800AD568
0x1800ad566  inc     dword ptr [rsi]
0x1800ad568  inc     r14d
0x1800ad56b  mov     this, [r15+18h]
0x1800ad56f  lea     rdx, [rbp+hasCurrent]
0x1800ad573  mov     rax, [this]
0x1800ad576  mov     rax, [rax+40h]
0x1800ad57a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad57f  mov     ebx, eax
0x1800ad581  test    eax, eax
0x1800ad583  js      short loc_1800AD5A5
0x1800ad585  mov     this, [rbp+categoryString.hstr_]; string
0x1800ad589  call    cs:__imp_WindowsDeleteString
0x1800ad58f  lea     this, [rbp+keyValuePair]; this
0x1800ad593  mov     [rbp+categoryString.hstr_], rdi
0x1800ad597  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ad59c  inc     dword ptr [r15+20h]
0x1800ad5a0  jmp     loc_1800AD4C0
0x1800ad5a5  mov     celt, 240h
0x1800ad5aa  jmp     short loc_1800AD5B1
0x1800ad5ac  mov     celt, 234h; lineNumber
0x1800ad5b1  mov     this, [rbp+40h]; callerReturnAddress
0x1800ad5b5  lea     rgelt, aComOle32Comcat_0; "com\\ole32\\comcat\\src\\catenum.cpp"
0x1800ad5bc  mov     r9d, eax; hr
0x1800ad5bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ad5c4  mov     this, [rbp+categoryString.hstr_]; string
0x1800ad5c8  call    cs:__imp_WindowsDeleteString
0x1800ad5ce  mov     [rbp+categoryString.hstr_], rdi
0x1800ad5d2  jmp     short loc_1800AD5EC
0x1800ad5d4  mov     this, [rbp+40h]; callerReturnAddress
0x1800ad5d8  lea     rgelt, aComOle32Comcat_0; "com\\ole32\\comcat\\src\\catenum.cpp"
0x1800ad5df  mov     r9d, eax; hr
0x1800ad5e2  mov     celt, 231h; lineNumber
0x1800ad5e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ad5ec  lea     this, [rbp+keyValuePair]; this
0x1800ad5f0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ad5f5  jmp     loc_1800AD489
0x1800ad5fa  cmp     r14d, r12d
0x1800ad5fd  mov     eax, edi
0x1800ad5ff  setb    al
0x1800ad602  add     rsp, 38h
0x1800ad606  pop     r15
0x1800ad608  pop     r14
0x1800ad60a  pop     r13
0x1800ad60c  pop     r12
0x1800ad60e  pop     rdi
0x1800ad60f  pop     rsi
0x1800ad610  pop     rbx
0x1800ad611  pop     rbp
0x1800ad612  retn
```
