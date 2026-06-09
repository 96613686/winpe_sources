# PropertyValueFactory::PropertyValueFromString(ushort const *,uint,IInspectable * *)

- ea: `0x1800717e8`
- end: `0x1800718e2`
- name: `?PropertyValueFromString@PropertyValueFactory@@QEAAJPEBGIPEAPEAUIInspectable@@@Z`
- size: `250`
- prototype: `HRESULT __fastcall(PropertyValueFactory *this, const wchar_t *pcwValue, unsigned int length, IInspectable **ppPropVal)`
- caller_count: `7`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180071760`
- `0x1800f7230`
- `0x1800f72e0`
- `0x1800f7550`
- `0x1800fd190`
- `0x1800fd290`
- `0x1800fd3a0`

## callees

- `0x1800717e8`
- `0x1800718e8`
- `0x1800719e4`
- `0x180071a5c`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800718d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800718d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180071858`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180071858`

## pseudocode

```c
__int64 __fastcall PropertyValueFactory::PropertyValueFromString(
        PropertyValueFactory *this,
        const wchar_t *pcwValue,
        UINT32 length,
        IInspectable **ppPropVal)
{
  int Instance; // edi
  HRESULT v9; // eax
  int v10; // eax
  HSTRING__ *hstring; // rbx
  Windows::Foundation::IPropertyValueStatics *v12; // rcx
  HSTRING string; // [rsp+20h] [rbp-18h] BYREF
  Windows::Internal::String str; // [rsp+28h] [rbp-10h] BYREF
  Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics> ptr; // [rsp+88h] [rbp+50h] BYREF

  if ( !ppPropVal )
    return 2147500035LL;
  Instance = 0;
  *ppPropVal = 0;
  if ( pcwValue )
  {
    ptr.ptr_ = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&ptr);
    Instance = PropertyValueFactory::GetInstance(this, &ptr.ptr_);
    if ( Instance >= 0 )
    {
      str._hstring = 0;
      string = 0;
      v9 = WindowsCreateString(pcwValue, length, &string);
      v10 = Windows::Internal::String::FreeAndAssignOnSuccess(v9, string, &str._hstring);
      hstring = str._hstring;
      Instance = v10;
      if ( v10 >= 0 )
        Instance = ptr.ptr_->CreateString(ptr.ptr_, str._hstring, ppPropVal);
      if ( hstring )
        WindowsDeleteString(hstring);
    }
    v12 = ptr.ptr_;
    if ( ptr.ptr_ )
    {
      ptr.ptr_ = 0;
      v12->Release(v12);
    }
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800717e8  push    rbp
0x1800717ea  push    rbx
0x1800717eb  push    rsi
0x1800717ec  push    rdi
0x1800717ed  push    r14
0x1800717ef  push    r15
0x1800717f1  mov     rbp, rsp
0x1800717f4  sub     rsp, 38h
0x1800717f8  mov     rsi, ppPropVal
0x1800717fb  mov     r15d, length
0x1800717fe  mov     rbx, pcwValue
0x180071801  mov     r14, this
0x180071804  test    ppPropVal, ppPropVal
0x180071807  jz      loc_1800718CA
0x18007180d  xor     edi, edi
0x18007180f  mov     qword ptr [ppPropVal], 0
0x180071816  test    pcwValue, pcwValue
0x180071819  jz      loc_1800718BA
0x18007181f  lea     this, [rbp+ptr]; this
0x180071823  mov     [rbp+ptr.ptr_], rdi
0x180071827  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007182c  lea     pcwValue, [rbp+ptr]; propertyfactory
0x180071830  mov     this, r14; this
0x180071833  call    ?GetInstance@PropertyValueFactory@@QEAAJPEAPEAUIPropertyValueStatics@Foundation@Windows@@@Z; PropertyValueFactory::GetInstance(Windows::Foundation::IPropertyValueStatics * *)
0x180071838  mov     edi, eax
0x18007183a  test    eax, eax
0x18007183c  js      short loc_18007189D
0x18007183e  lea     r8, [rbp+string]; string
0x180071842  mov     [rbp+str._hstring], 0
0x18007184a  mov     edx, r15d; length
0x18007184d  mov     [rbp+string], 0
0x180071855  mov     this, rbx; sourceString
0x180071858  call    cs:__imp_WindowsCreateString
0x18007185f  nop     dword ptr [rax+rax+00h]
0x180071864  mov     pcwValue, [rbp+string]; newValue
0x180071868  lea     r8, [rbp+str]; target
0x18007186c  mov     ecx, eax; hr
0x18007186e  call    ?FreeAndAssignOnSuccess@String@Internal@Windows@@CAJJPEAUHSTRING__@@PEAPEAU4@@Z; Windows::Internal::String::FreeAndAssignOnSuccess(long,HSTRING__ *,HSTRING__ * *)
0x180071873  mov     rbx, [rbp+str._hstring]
0x180071877  mov     edi, eax
0x180071879  test    eax, eax
0x18007187b  js      short loc_180071898
0x18007187d  mov     this, [rbp+ptr.ptr_]
0x180071881  mov     r8, rsi
0x180071884  mov     pcwValue, rbx
0x180071887  mov     rax, [this]
0x18007188a  mov     rax, [rax+90h]
0x180071891  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071896  mov     edi, eax
0x180071898  test    rbx, rbx
0x18007189b  jnz     short loc_1800718D1
0x18007189d  mov     this, [rbp+ptr.ptr_]
0x1800718a1  test    this, this
0x1800718a4  jz      short loc_1800718BA
0x1800718a6  mov     [rbp+ptr.ptr_], 0
0x1800718ae  mov     rax, [this]
0x1800718b1  mov     rax, [rax+10h]
0x1800718b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800718ba  mov     eax, edi
0x1800718bc  add     rsp, 38h
0x1800718c0  pop     r15
0x1800718c2  pop     r14
0x1800718c4  pop     rdi
0x1800718c5  pop     rsi
0x1800718c6  pop     rbx
0x1800718c7  pop     rbp
0x1800718c8  retn
0x1800718ca  mov     eax, 80004003h
0x1800718cf  jmp     short loc_1800718BC
0x1800718d1  mov     this, rbx; string
0x1800718d4  call    cs:__imp_WindowsDeleteString
0x1800718db  nop     dword ptr [rax+rax+00h]
0x1800718e0  jmp     short loc_18007189D
```
