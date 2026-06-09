# RetrieveNcryptHandle(IX509PrivateKey *,bool,unsigned __int64 *)

- ea: `0x18005773c`
- end: `0x1800578f0`
- name: `?RetrieveNcryptHandle@@YAJPEAUIX509PrivateKey@@_NPEA_K@Z`
- size: `436`
- prototype: `__int64 __fastcall(struct IX509PrivateKey *, bool, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b3ac`

## callees

- `0x18000d810`
- `0x180011938`
- `0x180020cb4`
- `0x18003aabc`
- `0x180055000`
- `0x18005773c`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800577cf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005786c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800577cf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005786c`
- `ncrypt!NCryptFreeObject` at `0x1800577c0`
- `ncrypt!NCryptFreeObject` at `0x18005785d`
- `ncrypt!NCryptFreeObject` at `0x1800577c0`
- `ncrypt!NCryptFreeObject` at `0x18005785d`
- `ncrypt!NCryptOpenKey` at `0x18005788c`
- `ncrypt!NCryptOpenKey` at `0x18005788c`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800577e7`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800577e7`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall RetrieveNcryptHandle(struct IX509PrivateKey *a1, unsigned __int8 a2, unsigned __int64 *a3)
{
  int v4; // r15d
  HRESULT (__stdcall *get_ProviderName)(IX509PrivateKey *, BSTR *); // rbx
  __int64 v7; // rax
  SECURITY_STATUS v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdx
  const WCHAR *v11; // rdi
  NCRYPT_HANDLE v12; // rbx
  HRESULT (__stdcall *get_ContainerName)(IX509PrivateKey *, BSTR *); // rbx
  __int64 v14; // rax
  const WCHAR *v15; // rsi
  NCRYPT_HANDLE v16; // rdi
  NCRYPT_HANDLE v17; // rax
  DWORD dwFlags; // [rsp+20h] [rbp-30h]
  LPCWSTR pszProviderName; // [rsp+30h] [rbp-20h] BYREF
  LPCWSTR pszKeyName; // [rsp+38h] [rbp-18h] BYREF
  _BYTE v22[4]; // [rsp+40h] [rbp-10h] BYREF
  DWORD dwErrCode; // [rsp+44h] [rbp-Ch]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  NCRYPT_HANDLE phKey; // [rsp+80h] [rbp+30h] BYREF
  NCRYPT_HANDLE hObject; // [rsp+98h] [rbp+48h] BYREF

  v4 = a2;
  hObject = 0;
  phKey = 0;
  pszKeyName = 0;
  pszProviderName = 0;
  get_ProviderName = a1->lpVtbl->get_ProviderName;
  v7 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pszProviderName);
  v8 = ((__int64 (__fastcall *)(struct IX509PrivateKey *, __int64))get_ProviderName)(a1, v7);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v11 = pszProviderName;
    v12 = hObject;
    if ( hObject )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)v22);
      NCryptFreeObject(v12);
      if ( !v22[0] )
        SetLastError(dwErrCode);
    }
    hObject = 0;
    v8 = NCryptOpenStorageProvider(&hObject, v11, 0);
    v9 = v8;
    if ( v8 >= 0 )
    {
      get_ContainerName = a1->lpVtbl->get_ContainerName;
      v14 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pszKeyName);
      v8 = ((__int64 (__fastcall *)(struct IX509PrivateKey *, __int64))get_ContainerName)(a1, v14);
      v9 = v8;
      if ( v8 >= 0 )
      {
        v15 = pszKeyName;
        v16 = phKey;
        if ( phKey )
        {
          wil::last_error_context::last_error_context((wil::last_error_context *)v22);
          NCryptFreeObject(v16);
          if ( !v22[0] )
            SetLastError(dwErrCode);
        }
        phKey = 0;
        v8 = NCryptOpenKey(hObject, &phKey, v15, 0, (32 * v4) | 0x40);
        v9 = v8;
        if ( v8 >= 0 )
        {
          v17 = phKey;
          phKey = 0;
          *a3 = v17;
          v9 = 0;
          goto LABEL_17;
        }
        v10 = 2263;
      }
      else
      {
        v10 = 2261;
      }
    }
    else
    {
      v10 = 2259;
    }
  }
  else
  {
    v10 = 2257;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\certrequest.cpp",
    (const char *)(unsigned int)v8,
    dwFlags);
LABEL_17:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((OLECHAR **)&pszProviderName);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((OLECHAR **)&pszKeyName);
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
  return v9;
}

```

## disassembly

```asm
0x18005773c  mov     [rsp-28h+arg_8], rbx
0x180057741  push    rbp
0x180057742  push    rsi
0x180057743  push    rdi
0x180057744  push    r14
0x180057746  push    r15
0x180057748  mov     rbp, rsp
0x18005774b  sub     rsp, 50h
0x18005774f  mov     r14, r8
0x180057752  movzx   r15d, dl
0x180057756  mov     rsi, rcx
0x180057759  mov     [rbp+hObject], 0
0x180057761  mov     [rbp+phKey], 0
0x180057769  mov     [rbp+pszKeyName], 0
0x180057771  mov     [rbp+pszProviderName], 0
0x180057779  mov     rax, [rcx]
0x18005777c  mov     rbx, [rax+0C8h]
0x180057783  lea     rcx, [rbp+pszProviderName]
0x180057787  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x18005778c  mov     rdx, rax
0x18005778f  mov     rcx, rsi
0x180057792  mov     rax, rbx
0x180057795  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005779a  mov     ebx, eax
0x18005779c  test    eax, eax
0x18005779e  jns     short loc_1800577A7
0x1800577a0  mov     edx, 8D1h
0x1800577a5  jmp     short loc_1800577F8
0x1800577a7  mov     rdi, [rbp+pszProviderName]
0x1800577ab  mov     rbx, [rbp+hObject]
0x1800577af  test    rbx, rbx
0x1800577b2  jz      short loc_1800577D5
0x1800577b4  lea     rcx, [rbp+var_10]; this
0x1800577b8  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800577bd  mov     rcx, rbx; hObject
0x1800577c0  call    cs:__imp_NCryptFreeObject
0x1800577c6  cmp     [rbp+var_10], 0
0x1800577ca  jnz     short loc_1800577D5
0x1800577cc  mov     ecx, [rbp+dwErrCode]; dwErrCode
0x1800577cf  call    cs:__imp_SetLastError
0x1800577d5  mov     [rbp+hObject], 0
0x1800577dd  xor     r8d, r8d; dwFlags
0x1800577e0  mov     rdx, rdi; pszProviderName
0x1800577e3  lea     rcx, [rbp+hObject]; phProvider
0x1800577e7  call    cs:__imp_NCryptOpenStorageProvider
0x1800577ed  mov     ebx, eax
0x1800577ef  test    eax, eax
0x1800577f1  jns     short loc_180057810
0x1800577f3  mov     edx, 8D3h; void *
0x1800577f8  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800577ff  mov     r9d, eax; char *
0x180057802  mov     rcx, [rbp+28h]; this
0x180057806  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005780b  jmp     loc_1800578B3
0x180057810  mov     rax, [rsi]
0x180057813  mov     rbx, [rax+78h]
0x180057817  lea     rcx, [rbp+pszKeyName]
0x18005781b  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x180057820  mov     rdx, rax
0x180057823  mov     rcx, rsi
0x180057826  mov     rax, rbx
0x180057829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005782e  mov     ebx, eax
0x180057830  test    eax, eax
0x180057832  jns     short loc_18005783B
0x180057834  mov     edx, 8D5h
0x180057839  jmp     short loc_1800577F8
0x18005783b  mov     ebx, r15d
0x18005783e  shl     ebx, 5
0x180057841  or      ebx, 40h
0x180057844  mov     rsi, [rbp+pszKeyName]
0x180057848  mov     rdi, [rbp+phKey]
0x18005784c  test    rdi, rdi
0x18005784f  jz      short loc_180057872
0x180057851  lea     rcx, [rbp+var_10]; this
0x180057855  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18005785a  mov     rcx, rdi; hObject
0x18005785d  call    cs:__imp_NCryptFreeObject
0x180057863  cmp     [rbp+var_10], 0
0x180057867  jnz     short loc_180057872
0x180057869  mov     ecx, [rbp+dwErrCode]; dwErrCode
0x18005786c  call    cs:__imp_SetLastError
0x180057872  mov     [rbp+phKey], 0
0x18005787a  mov     [rsp+50h+dwFlags], ebx; dwFlags
0x18005787e  xor     r9d, r9d; dwLegacyKeySpec
0x180057881  mov     r8, rsi; pszKeyName
0x180057884  lea     rdx, [rbp+phKey]; phKey
0x180057888  mov     rcx, [rbp+hObject]; hProvider
0x18005788c  call    cs:__imp_NCryptOpenKey
0x180057892  mov     ebx, eax
0x180057894  test    eax, eax
0x180057896  jns     short loc_1800578A2
0x180057898  mov     edx, 8D7h
0x18005789d  jmp     loc_1800577F8
0x1800578a2  mov     rax, [rbp+phKey]
0x1800578a6  mov     [rbp+phKey], 0
0x1800578ae  mov     [r14], rax
0x1800578b1  xor     ebx, ebx
0x1800578b3  lea     rcx, [rbp+pszProviderName]
0x1800578b7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800578bc  nop
0x1800578bd  lea     rcx, [rbp+pszKeyName]
0x1800578c1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800578c6  nop
0x1800578c7  lea     rcx, [rbp+phKey]
0x1800578cb  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1800578d0  nop
0x1800578d1  lea     rcx, [rbp+hObject]
0x1800578d5  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1800578da  mov     eax, ebx
0x1800578dc  mov     rbx, [rsp+50h+arg_8]
0x1800578e4  add     rsp, 50h
0x1800578e8  pop     r15
0x1800578ea  pop     r14
0x1800578ec  pop     rdi
0x1800578ed  pop     rsi
0x1800578ee  pop     rbp
0x1800578ef  retn
```
