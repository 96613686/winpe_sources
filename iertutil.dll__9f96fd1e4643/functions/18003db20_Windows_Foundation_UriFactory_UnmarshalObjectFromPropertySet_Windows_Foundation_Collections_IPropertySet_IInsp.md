# Windows::Foundation::UriFactory::UnmarshalObjectFromPropertySet(Windows::Foundation::Collections::IPropertySet *,IInspectable * *)

- ea: `0x18003db20`
- end: `0x18003dd2b`
- name: `?UnmarshalObjectFromPropertySet@UriFactory@Foundation@Windows@@UEAAJPEAUIPropertySet@Collections@23@PEAPEAUIInspectable@@@Z`
- size: `523`
- prototype: `__int64 __fastcall(Windows::Foundation::UriFactory *__hidden this, struct Windows::Foundation::Collections::IPropertySet *, struct IInspectable **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180026834`
- `0x18003db20`
- `0x180083c10`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003dd24`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003dd24`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003dbb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003dbb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003dc1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003dccd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003dc1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003dccd`

## string_xrefs

- `0x18003dbab`: `RawUri`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::UriFactory::UnmarshalObjectFromPropertySet(
        Windows::Foundation::UriFactory *this,
        struct Windows::Foundation::Collections::IPropertySet *a2,
        struct IInspectable **a3)
{
  __int64 (__fastcall **v4)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, _QWORD **); // rax
  __int64 (__fastcall *v7)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, _QWORD **); // rbx
  int v8; // ebx
  _QWORD *v9; // rbx
  __int64 v10; // rdi
  HRESULT v11; // eax
  int v12; // eax
  __int64 (__fastcall ***v13)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v14)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, HSTRING *); // rbx
  __int64 v17; // rcx
  struct IInspectable *v18; // rcx
  __int64 (__fastcall *v19)(char *, HSTRING, struct IInspectable **); // rbx
  struct IInspectable *v20; // rax
  __int64 (__fastcall ***v21)(_QWORD, _QWORD, _QWORD); // rcx
  _QWORD *v22; // rcx
  struct IInspectable *v24; // [rsp+20h] [rbp-50h] BYREF
  HSTRING v25; // [rsp+28h] [rbp-48h] BYREF
  __int64 v26; // [rsp+30h] [rbp-40h] BYREF
  __int64 (__fastcall ***v27)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-38h] BYREF
  _QWORD *v28; // [rsp+40h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF
  HSTRING string; // [rsp+60h] [rbp-10h] BYREF

  *a3 = 0;
  v4 = *(__int64 (__fastcall ***)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, _QWORD **))a2;
  v28 = 0;
  v7 = *v4;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
  v25 = 0;
  v8 = v7(a2, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v28);
  v27 = 0;
  if ( v8 >= 0 )
  {
    v9 = v28;
    v10 = *v28;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
    string = 0;
    v11 = WindowsCreateStringReference(L"RawUri", 6u, &hstringHeader, &string);
    if ( v11 < 0 )
    {
      RaiseException(v11, 1u, 0, 0);
      JUMPOUT(0x18003DD2ALL);
    }
    v12 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, _QWORD))(v10 + 48))(v9, string, &v27);
    v26 = 0;
    v8 = v12;
    if ( v12 >= 0 )
    {
      v13 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v27;
      v14 = **v27;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
      v8 = v14(v13, &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62, &v26);
      if ( v8 >= 0 )
      {
        v15 = v26;
        v16 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v26 + 152LL);
        WindowsDeleteString(v25);
        v25 = 0;
        v8 = v16(v15, &v25);
      }
    }
    v17 = v26;
    if ( v26 )
    {
      v26 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
  }
  v18 = 0;
  v24 = 0;
  if ( v8 >= 0 )
  {
    v19 = *(__int64 (__fastcall **)(char *, HSTRING, struct IInspectable **))(*((_QWORD *)this - 3) + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
    v8 = v19((char *)this - 24, v25, &v24);
    if ( v8 < 0 )
    {
      v18 = v24;
    }
    else
    {
      v20 = v24;
      v18 = 0;
      v24 = 0;
      *a3 = v20;
    }
  }
  if ( v18 )
  {
    v24 = 0;
    ((void (__fastcall *)(struct IInspectable *))v18->lpVtbl->Release)(v18);
  }
  v21 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v27;
  if ( v27 )
  {
    v27 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v21)[2])(v21);
  }
  WindowsDeleteString(v25);
  v22 = v28;
  v25 = 0;
  if ( v28 )
  {
    v28 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v22 + 16LL))(v22);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18003db20  mov     [rsp-28h+arg_18], rbx
0x18003db25  push    rbp
0x18003db26  push    rsi
0x18003db27  push    rdi
0x18003db28  push    r14
0x18003db2a  push    r15
0x18003db2c  mov     rbp, rsp
0x18003db2f  sub     rsp, 70h
0x18003db33  mov     rax, cs:__security_cookie
0x18003db3a  xor     rax, rsp
0x18003db3d  mov     [rbp+var_8], rax
0x18003db41  xor     r15d, r15d
0x18003db44  mov     r14, rcx
0x18003db47  mov     [r8], r15
0x18003db4a  lea     rcx, [rbp+var_30]
0x18003db4e  mov     rax, [rdx]
0x18003db51  mov     rsi, r8
0x18003db54  mov     rdi, rdx
0x18003db57  mov     [rbp+var_30], r15
0x18003db5b  mov     rbx, [rax]
0x18003db5e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003db63  lea     r8, [rbp+var_30]
0x18003db67  mov     rcx, rdi
0x18003db6a  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x18003db71  mov     rax, rbx
0x18003db74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003db79  mov     [rbp+var_48], r15
0x18003db7d  mov     ebx, eax
0x18003db7f  mov     [rbp+var_38], r15
0x18003db83  test    eax, eax
0x18003db85  js      loc_18003DC53
0x18003db8b  mov     rbx, [rbp+var_30]
0x18003db8f  lea     rcx, [rbp+var_38]
0x18003db93  mov     rdi, [rbx]
0x18003db96  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003db9b  lea     r9, [rbp+string]; string
0x18003db9f  mov     [rbp+string], r15
0x18003dba3  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18003dba7  lea     edx, [r15+6]; length
0x18003dbab  lea     rcx, sourceString; "RawUri"
0x18003dbb2  call    cs:__imp_WindowsCreateStringReference
0x18003dbb8  test    eax, eax
0x18003dbba  js      loc_18003DD18
0x18003dbc0  mov     rdx, [rbp+string]
0x18003dbc4  lea     r8, [rbp+var_38]
0x18003dbc8  mov     rax, [rdi+30h]
0x18003dbcc  mov     rcx, rbx
0x18003dbcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dbd4  mov     [rbp+var_40], r15
0x18003dbd8  mov     ebx, eax
0x18003dbda  test    eax, eax
0x18003dbdc  js      short loc_18003DC3A
0x18003dbde  mov     rbx, [rbp+var_38]
0x18003dbe2  lea     rcx, [rbp+var_40]
0x18003dbe6  mov     rax, [rbx]
0x18003dbe9  mov     rdi, [rax]
0x18003dbec  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003dbf1  lea     r8, [rbp+var_40]
0x18003dbf5  mov     rcx, rbx
0x18003dbf8  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x18003dbff  mov     rax, rdi
0x18003dc02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dc07  mov     ebx, eax
0x18003dc09  test    eax, eax
0x18003dc0b  js      short loc_18003DC3A
0x18003dc0d  mov     rdi, [rbp+var_40]
0x18003dc11  mov     rcx, [rbp+var_48]; string
0x18003dc15  mov     rax, [rdi]
0x18003dc18  mov     rbx, [rax+98h]
0x18003dc1f  call    cs:__imp_WindowsDeleteString
0x18003dc25  lea     rdx, [rbp+var_48]
0x18003dc29  mov     [rbp+var_48], r15
0x18003dc2d  mov     rcx, rdi
0x18003dc30  mov     rax, rbx
0x18003dc33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dc38  mov     ebx, eax
0x18003dc3a  mov     rcx, [rbp+var_40]
0x18003dc3e  test    rcx, rcx
0x18003dc41  jz      short loc_18003DC53
0x18003dc43  mov     [rbp+var_40], r15
0x18003dc47  mov     rax, [rcx]
0x18003dc4a  mov     rax, [rax+10h]
0x18003dc4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dc53  mov     rcx, r15
0x18003dc56  mov     [rbp+var_50], rcx
0x18003dc5a  test    ebx, ebx
0x18003dc5c  js      short loc_18003DC9B
0x18003dc5e  mov     rax, [r14-18h]
0x18003dc62  lea     rcx, [rbp+var_50]
0x18003dc66  mov     rbx, [rax+30h]
0x18003dc6a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003dc6f  mov     rdx, [rbp+var_48]
0x18003dc73  lea     r8, [rbp+var_50]
0x18003dc77  lea     rcx, [r14-18h]
0x18003dc7b  mov     rax, rbx
0x18003dc7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dc83  mov     ebx, eax
0x18003dc85  test    eax, eax
0x18003dc87  js      loc_18003DD12
0x18003dc8d  mov     rax, [rbp+var_50]
0x18003dc91  mov     rcx, r15
0x18003dc94  mov     [rbp+var_50], rcx
0x18003dc98  mov     [rsi], rax
0x18003dc9b  test    rcx, rcx
0x18003dc9e  jz      short loc_18003DCB0
0x18003dca0  mov     [rbp+var_50], r15
0x18003dca4  mov     rax, [rcx]
0x18003dca7  mov     rax, [rax+10h]
0x18003dcab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dcb0  mov     rcx, [rbp+var_38]
0x18003dcb4  test    rcx, rcx
0x18003dcb7  jz      short loc_18003DCC9
0x18003dcb9  mov     [rbp+var_38], r15
0x18003dcbd  mov     rax, [rcx]
0x18003dcc0  mov     rax, [rax+10h]
0x18003dcc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dcc9  mov     rcx, [rbp+var_48]; string
0x18003dccd  call    cs:__imp_WindowsDeleteString
0x18003dcd3  mov     rcx, [rbp+var_30]
0x18003dcd7  mov     [rbp+var_48], r15
0x18003dcdb  test    rcx, rcx
0x18003dcde  jz      short loc_18003DCF0
0x18003dce0  mov     [rbp+var_30], r15
0x18003dce4  mov     rax, [rcx]
0x18003dce7  mov     rax, [rax+10h]
0x18003dceb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dcf0  mov     eax, ebx
0x18003dcf2  mov     rcx, [rbp+var_8]
0x18003dcf6  xor     rcx, rsp; StackCookie
0x18003dcf9  call    __security_check_cookie
0x18003dcfe  mov     rbx, [rsp+70h+arg_18]
0x18003dd06  add     rsp, 70h
0x18003dd0a  pop     r15
0x18003dd0c  pop     r14
0x18003dd0e  pop     rdi
0x18003dd0f  pop     rsi
0x18003dd10  pop     rbp
0x18003dd11  retn
0x18003dd12  mov     rcx, [rbp+var_50]
0x18003dd16  jmp     short loc_18003DC9B
0x18003dd18  xor     r9d, r9d; lpArguments
0x18003dd1b  xor     r8d, r8d; nNumberOfArguments
0x18003dd1e  mov     ecx, eax; dwExceptionCode
0x18003dd20  lea     edx, [r9+1]; dwExceptionFlags
0x18003dd24  call    cs:__imp_RaiseException
```
