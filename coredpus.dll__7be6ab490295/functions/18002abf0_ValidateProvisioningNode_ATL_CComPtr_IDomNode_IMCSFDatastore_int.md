# ValidateProvisioningNode(ATL::CComPtr<IDomNode>,IMCSFDatastore *,int *)

- ea: `0x18002abf0`
- end: `0x18002ad13`
- name: `?ValidateProvisioningNode@@YAJV?$CComPtr@UIDomNode@@@ATL@@PEAUIMCSFDatastore@@PEAH@Z`
- size: `291`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180029240`

## callees

- `0x1800110bc`
- `0x180011d6c`
- `0x180011d9c`
- `0x18002abf0`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18002acf0`
- `OLEAUT32!__imp_SysFreeString` at `0x18002acf0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002ac6a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002ac6a`

## string_xrefs

- `0x18002ac25`: `SettingsPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ValidateProvisioningNode(_QWORD *a1, __int64 a2, _DWORD *a3)
{
  unsigned int v6; // ebx
  HRESULT v7; // eax
  __int64 v8; // rdx
  int ppv; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  LPVOID v12; // [rsp+70h] [rbp+40h] BYREF
  BSTR bstrString; // [rsp+78h] [rbp+48h] BYREF

  v6 = 1;
  *a3 = 1;
  bstrString = 0;
  if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, BSTR *))(*(_QWORD *)*a1 + 88LL))(
         *a1,
         L"SettingsPath",
         &bstrString) >= 0 )
  {
    v12 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
    v7 = CoCreateInstance(
           &GUID_50a41ef1_6bfa_4b7e_973e_798ea0bebad4,
           0,
           1u,
           &GUID_e34e5896_40b2_45c4_a9c0_8a9601c3b0a6,
           &v12);
    v6 = v7;
    if ( v7 < 0 )
    {
      v8 = 62;
LABEL_4:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecoreuap\\admin\\dm\\coredpus\\wapdpu\\wapdpuimpl.cpp",
        (const char *)(unsigned int)v7,
        ppv);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
      goto LABEL_10;
    }
    v7 = (*(__int64 (__fastcall **)(LPVOID, BSTR))(*(_QWORD *)v12 + 40LL))(v12, bstrString);
    v6 = v7;
    if ( v7 < 0 )
    {
      v8 = 65;
      goto LABEL_4;
    }
    if ( (*(int (__fastcall **)(__int64, LPVOID, _DWORD *))(*(_QWORD *)a2 + 32LL))(a2, v12, a3) < 0 )
      *a3 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
    v6 = 0;
  }
LABEL_10:
  SysFreeString(bstrString);
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(a1);
  return v6;
}

```

## disassembly

```asm
0x18002abf0  mov     [rsp-28h+arg_0], rcx
0x18002abf5  push    rbp
0x18002abf6  push    rbx
0x18002abf7  push    rsi
0x18002abf8  push    rdi
0x18002abf9  push    r14
0x18002abfb  mov     rbp, rsp
0x18002abfe  sub     rsp, 30h
0x18002ac02  mov     rdi, r8
0x18002ac05  mov     r14, rdx
0x18002ac08  mov     rsi, rcx
0x18002ac0b  mov     ebx, 1
0x18002ac10  mov     [r8], ebx
0x18002ac13  mov     [rbp+bstrString], 0
0x18002ac1b  mov     rcx, [rcx]
0x18002ac1e  mov     rax, [rcx]
0x18002ac21  lea     r8, [rbp+bstrString]
0x18002ac25  lea     rdx, aSettingspath; "SettingsPath"
0x18002ac2c  mov     rax, [rax+58h]
0x18002ac30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ac35  test    eax, eax
0x18002ac37  js      loc_18002ACEC
0x18002ac3d  mov     [rbp+arg_10], 0
0x18002ac45  lea     rcx, [rbp+arg_10]
0x18002ac49  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002ac4e  lea     rax, [rbp+arg_10]
0x18002ac52  mov     qword ptr [rsp+30h+ppv], rax; int
0x18002ac57  lea     r9, _GUID_e34e5896_40b2_45c4_a9c0_8a9601c3b0a6; riid
0x18002ac5e  mov     r8d, ebx; dwClsContext
0x18002ac61  xor     edx, edx; pUnkOuter
0x18002ac63  lea     rcx, _GUID_50a41ef1_6bfa_4b7e_973e_798ea0bebad4; rclsid
0x18002ac6a  call    cs:__imp_CoCreateInstance
0x18002ac71  nop     dword ptr [rax+rax+00h]
0x18002ac76  mov     ebx, eax
0x18002ac78  test    eax, eax
0x18002ac7a  jns     short loc_18002ACA0
0x18002ac7c  mov     edx, 3Eh ; '>'; void *
0x18002ac81  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\dm\\coredpus\\wapdpu"...
0x18002ac88  mov     r9d, eax; char *
0x18002ac8b  mov     rcx, [rbp+28h]; this
0x18002ac8f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ac94  nop
0x18002ac95  lea     rcx, [rbp+arg_10]
0x18002ac99  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002ac9e  jmp     short loc_18002ACEC
0x18002aca0  mov     rcx, [rbp+arg_10]
0x18002aca4  mov     rax, [rcx]
0x18002aca7  mov     rdx, [rbp+bstrString]
0x18002acab  mov     rax, [rax+28h]
0x18002acaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002acb4  mov     ebx, eax
0x18002acb6  test    eax, eax
0x18002acb8  jns     short loc_18002ACC1
0x18002acba  mov     edx, 41h ; 'A'
0x18002acbf  jmp     short loc_18002AC81
0x18002acc1  mov     rax, [r14]
0x18002acc4  mov     r8, rdi
0x18002acc7  mov     rdx, [rbp+arg_10]
0x18002accb  mov     rcx, r14
0x18002acce  mov     rax, [rax+20h]
0x18002acd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002acd7  test    eax, eax
0x18002acd9  jns     short loc_18002ACE1
0x18002acdb  mov     dword ptr [rdi], 0
0x18002ace1  lea     rcx, [rbp+arg_10]
0x18002ace5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002acea  xor     ebx, ebx
0x18002acec  mov     rcx, [rbp+bstrString]; bstrString
0x18002acf0  call    cs:__imp_SysFreeString
0x18002acf7  nop     dword ptr [rax+rax+00h]
0x18002acfc  nop
0x18002acfd  mov     rcx, rsi
0x18002ad00  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x18002ad05  mov     eax, ebx
0x18002ad07  add     rsp, 30h
0x18002ad0b  pop     r14
0x18002ad0d  pop     rdi
0x18002ad0e  pop     rsi
0x18002ad0f  pop     rbx
0x18002ad10  pop     rbp
0x18002ad11  retn
```
