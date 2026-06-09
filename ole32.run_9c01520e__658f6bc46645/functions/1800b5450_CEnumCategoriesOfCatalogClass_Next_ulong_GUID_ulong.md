# CEnumCategoriesOfCatalogClass::Next(ulong,_GUID *,ulong *)

- ea: `0x1800b5450`
- end: `0x1800b5644`
- name: `?Next@CEnumCategoriesOfCatalogClass@@UEAAJKPEAU_GUID@@PEAK@Z`
- size: `500`
- prototype: `HRESULT __fastcall(CEnumCategoriesOfCatalogClass *this, unsigned int celt, _GUID *rgelt, unsigned int *pceltFetched)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800085a8`
- `0x18001217c`
- `0x1800b5450`
- `0x1800d8010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800b556f`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800b556f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b5526`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b55a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b55ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b5526`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b55a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b55ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b5555`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b5555`

## string_xrefs

- `0x1800b548f`: `com\ole32\comcat\src\catenum.cpp`
- `0x1800b55da`: `com\ole32\comcat\src\catenum.cpp`
- `0x1800b5603`: `com\ole32\comcat\src\catenum.cpp`

## pseudocode

```c
__int64 __fastcall CEnumCategoriesOfCatalogClass::Next(
        CEnumCategoriesOfCatalogClass *this,
        unsigned int celt,
        _GUID *rgelt,
        unsigned int *pceltFetched)
{
  unsigned int v4; // esi
  HRESULT v8; // ebx
  unsigned int v9; // edx
  Windows::Foundation::Collections::IIterator<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *> *ptr; // rcx
  unsigned int v12; // r15d
  bool v13; // cf
  Windows::Foundation::Collections::IIterator<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *> *v14; // rdi
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
  HRESULT v16; // eax
  Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *v17; // rbx
  HRESULT (__stdcall *v18)(IUnknown *, const IID *const, void **); // rdi
  HRESULT v19; // eax
  const OLECHAR *StringRawBuffer; // rax
  unsigned int v21; // edx
  Microsoft::WRL::Wrappers::HString categoryString; // [rsp+20h] [rbp-10h] BYREF
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> > keyValuePair; // [rsp+28h] [rbp-8h] BYREF
  void *retaddr; // [rsp+68h] [rbp+38h]
  unsigned __int8 hasCurrent; // [rsp+78h] [rbp+48h] BYREF
  _GUID *v26; // [rsp+80h] [rbp+50h]

  v26 = rgelt;
  v4 = 0;
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
  while ( 1 )
  {
    v13 = v12 < celt;
    if ( v12 >= celt )
      goto LABEL_27;
    if ( !hasCurrent )
      break;
    v14 = this->_categoriesIterator.ptr_;
    keyValuePair.ptr_ = 0;
    QueryInterface = v14->lpVtbl[2].QueryInterface;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<ITypeLibRegistrationReader> *)&keyValuePair);
    v16 = ((__int64 (__fastcall *)(Windows::Foundation::Collections::IIterator<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *> *, Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> > *))QueryInterface)(
            v14,
            &keyValuePair);
    v8 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, 0x231u, "com\\ole32\\comcat\\src\\catenum.cpp", v16);
      goto LABEL_25;
    }
    v17 = keyValuePair.ptr_;
    v18 = keyValuePair.ptr_->lpVtbl[2].QueryInterface;
    WindowsDeleteString(0);
    categoryString.hstr_ = 0;
    v19 = ((__int64 (__fastcall *)(Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *, Microsoft::WRL::Wrappers::HString *))v18)(
            v17,
            &categoryString);
    v8 = v19;
    if ( v19 < 0 )
    {
      v21 = 564;
LABEL_23:
      wil::details::in1diag3::Return_Hr(retaddr, v21, "com\\ole32\\comcat\\src\\catenum.cpp", v19);
      WindowsDeleteString(categoryString.hstr_);
      categoryString.hstr_ = 0;
LABEL_25:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<ITypeLibRegistrationReader> *)&keyValuePair);
      return (unsigned int)v8;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(categoryString.hstr_, 0);
    if ( IIDFromString(StringRawBuffer, &v26[v12]) >= 0 )
    {
      if ( pceltFetched )
        ++*pceltFetched;
      ++v12;
    }
    v19 = ((__int64 (__fastcall *)(Windows::Foundation::Collections::IIterator<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *> *, unsigned __int8 *))this->_categoriesIterator.ptr_->lpVtbl[2].Release)(
            this->_categoriesIterator.ptr_,
            &hasCurrent);
    v8 = v19;
    if ( v19 < 0 )
    {
      v21 = 576;
      goto LABEL_23;
    }
    WindowsDeleteString(categoryString.hstr_);
    categoryString.hstr_ = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<ITypeLibRegistrationReader> *)&keyValuePair);
    ++this->_iteratorPosition;
  }
  v13 = v12 < celt;
LABEL_27:
  LOBYTE(v4) = v13;
  return v4;
}

```

## disassembly

```asm
0x1800b5450  mov     [rsp-38h+arg_0], rbx
0x1800b5455  mov     [rsp-38h+arg_10], rgelt
0x1800b545a  push    rbp
0x1800b545b  push    rsi
0x1800b545c  push    rdi
0x1800b545d  push    r12
0x1800b545f  push    r13
0x1800b5461  push    r14
0x1800b5463  push    r15
0x1800b5465  mov     rbp, rsp
0x1800b5468  sub     rsp, 30h
0x1800b546c  xor     esi, esi
0x1800b546e  mov     r14, pceltFetched
0x1800b5471  mov     r12d, celt
0x1800b5474  mov     r13, this
0x1800b5477  cmp     celt, 1
0x1800b547a  jbe     short loc_1800B54A5
0x1800b547c  test    pceltFetched, pceltFetched
0x1800b547f  jnz     short loc_1800B54AA
0x1800b5481  mov     ebx, 80070057h
0x1800b5486  mov     celt, 223h; lineNumber
0x1800b548b  mov     this, [rbp+38h]; callerReturnAddress
0x1800b548f  lea     rgelt, aComOle32Comcat_0; "com\\ole32\\comcat\\src\\catenum.cpp"
0x1800b5496  mov     r9d, ebx; hr
0x1800b5499  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b549e  mov     eax, ebx
0x1800b54a0  jmp     loc_1800B562E
0x1800b54a5  test    r14, r14
0x1800b54a8  jz      short loc_1800B54AD
0x1800b54aa  mov     [pceltFetched], esi
0x1800b54ad  mov     this, [this+18h]
0x1800b54b1  lea     rdx, [rbp+hasCurrent]
0x1800b54b5  mov     [rbp+hasCurrent], sil
0x1800b54b9  mov     rax, [this]
0x1800b54bc  mov     rax, [rax+38h]
0x1800b54c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b54c5  mov     ebx, eax
0x1800b54c7  test    eax, eax
0x1800b54c9  jns     short loc_1800B54D2
0x1800b54cb  mov     celt, 22Bh
0x1800b54d0  jmp     short loc_1800B548B
0x1800b54d2  mov     r15d, esi
0x1800b54d5  cmp     r15d, r12d
0x1800b54d8  jnb     loc_1800B5628
0x1800b54de  cmp     [rbp+hasCurrent], sil
0x1800b54e2  jz      loc_1800B5625
0x1800b54e8  mov     rdi, [r13+18h]
0x1800b54ec  lea     this, [rbp+keyValuePair]; this
0x1800b54f0  mov     [rbp+keyValuePair.ptr_], rsi
0x1800b54f4  mov     rax, [rdi]
0x1800b54f7  mov     rbx, [rax+30h]
0x1800b54fb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b5500  lea     rdx, [rbp+keyValuePair]
0x1800b5504  mov     this, rdi
0x1800b5507  mov     rax, rbx
0x1800b550a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b550f  mov     ebx, eax
0x1800b5511  test    eax, eax
0x1800b5513  js      loc_1800B55FF
0x1800b5519  mov     rbx, [rbp+keyValuePair.ptr_]
0x1800b551d  xor     ecx, ecx; string
0x1800b551f  mov     rax, [rbx]
0x1800b5522  mov     rdi, [rax+30h]
0x1800b5526  call    cs:__imp_WindowsDeleteString
0x1800b552d  nop     dword ptr [rax+rax+00h]
0x1800b5532  lea     rdx, [rbp+categoryString]
0x1800b5536  mov     [rbp+categoryString.hstr_], rsi
0x1800b553a  mov     this, rbx
0x1800b553d  mov     rax, rdi
0x1800b5540  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5545  mov     ebx, eax
0x1800b5547  test    eax, eax
0x1800b5549  js      loc_1800B55D1
0x1800b554f  mov     this, [rbp+categoryString.hstr_]; string
0x1800b5553  xor     celt, celt; length
0x1800b5555  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b555c  nop     dword ptr [rax+rax+00h]
0x1800b5561  mov     celt, r15d
0x1800b5564  mov     this, rax; lpsz
0x1800b5567  shl     rdx, 4
0x1800b556b  add     rdx, [rbp+arg_10]; lpiid
0x1800b556f  call    cs:__imp_IIDFromString
0x1800b5576  nop     dword ptr [rax+rax+00h]
0x1800b557b  test    eax, eax
0x1800b557d  js      short loc_1800B558A
0x1800b557f  test    r14, r14
0x1800b5582  jz      short loc_1800B5587
0x1800b5584  inc     dword ptr [r14]
0x1800b5587  inc     r15d
0x1800b558a  mov     this, [r13+18h]
0x1800b558e  lea     rdx, [rbp+hasCurrent]
0x1800b5592  mov     rax, [this]
0x1800b5595  mov     rax, [rax+40h]
0x1800b5599  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b559e  mov     ebx, eax
0x1800b55a0  test    eax, eax
0x1800b55a2  js      short loc_1800B55CA
0x1800b55a4  mov     this, [rbp+categoryString.hstr_]; string
0x1800b55a8  call    cs:__imp_WindowsDeleteString
0x1800b55af  nop     dword ptr [rax+rax+00h]
0x1800b55b4  lea     this, [rbp+keyValuePair]; this
0x1800b55b8  mov     [rbp+categoryString.hstr_], rsi
0x1800b55bc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b55c1  inc     dword ptr [r13+20h]
0x1800b55c5  jmp     loc_1800B54D5
0x1800b55ca  mov     celt, 240h
0x1800b55cf  jmp     short loc_1800B55D6
0x1800b55d1  mov     celt, 234h; lineNumber
0x1800b55d6  mov     this, [rbp+38h]; callerReturnAddress
0x1800b55da  lea     rgelt, aComOle32Comcat_0; "com\\ole32\\comcat\\src\\catenum.cpp"
0x1800b55e1  mov     r9d, eax; hr
0x1800b55e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b55e9  mov     this, [rbp+categoryString.hstr_]; string
0x1800b55ed  call    cs:__imp_WindowsDeleteString
0x1800b55f4  nop     dword ptr [rax+rax+00h]
0x1800b55f9  mov     [rbp+categoryString.hstr_], rsi
0x1800b55fd  jmp     short loc_1800B5617
0x1800b55ff  mov     this, [rbp+38h]; callerReturnAddress
0x1800b5603  lea     rgelt, aComOle32Comcat_0; "com\\ole32\\comcat\\src\\catenum.cpp"
0x1800b560a  mov     r9d, eax; hr
0x1800b560d  mov     celt, 231h; lineNumber
0x1800b5612  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b5617  lea     this, [rbp+keyValuePair]; this
0x1800b561b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b5620  jmp     loc_1800B549E
0x1800b5625  cmp     r15d, r12d
0x1800b5628  setb    sil
0x1800b562c  mov     eax, esi
0x1800b562e  mov     rbx, [rsp+30h+arg_0]
0x1800b5633  add     rsp, 30h
0x1800b5637  pop     r15
0x1800b5639  pop     r14
0x1800b563b  pop     r13
0x1800b563d  pop     r12
0x1800b563f  pop     rdi
0x1800b5640  pop     rsi
0x1800b5641  pop     rbp
0x1800b5642  retn
```
