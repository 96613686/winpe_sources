# TeredoUPnP::FindUPnPService(ushort const *,ushort const *,IUPnPService * *)

- ea: `0x180027700`
- end: `0x1800279d3`
- name: `?FindUPnPService@TeredoUPnP@@AEAAJPEBG0PEAPEAUIUPnPService@@@Z`
- size: `723`
- prototype: `__int64 __fastcall(TeredoUPnP *this, const unsigned __int16 *, const unsigned __int16 *, struct IUPnPService **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180027054`

## callees

- `0x18000d7c0`
- `0x1800190f0`
- `0x180027700`
- `0x1800279dc`
- `0x180028108`
- `0x180043334`
- `0x180073e28`
- `0x180073e54`
- `0x180083010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002782e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002786b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002782e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002786b`
- `OLEAUT32!__imp_SysAllocString` at `0x180027729`
- `OLEAUT32!__imp_SysAllocString` at `0x180027729`
- `OLEAUT32!__imp_SysFreeString` at `0x1800278f8`
- `OLEAUT32!__imp_SysFreeString` at `0x18002797a`
- `OLEAUT32!__imp_SysFreeString` at `0x18002799e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800278f8`
- `OLEAUT32!__imp_SysFreeString` at `0x18002797a`
- `OLEAUT32!__imp_SysFreeString` at `0x18002799e`

## string_xrefs

- `0x180027793`: `get_Services returned 0x%x`
- `0x18002781d`: `Falling back to service enumeration search for %ws`
- `0x180027955`: `Found UPnP service %ws`
- `0x180027932`: `get_ServiceTypeIdentifier returned 0x%x`
- `0x18002793e`: `Discovered UPnP service has no type identifier`
- `0x18002788b`: `Service enumeration failed with 0x%x`

## pseudocode

```c
__int64 __fastcall TeredoUPnP::FindUPnPService(
        TeredoUPnP *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct IUPnPService **a4)
{
  OLECHAR *v8; // rbx
  int UPnPServiceByEnumeration; // edi
  __int64 *v10; // rdi
  __int64 v11; // rax
  OLECHAR *v12; // rcx
  __int64 v13; // rax
  int v14; // eax
  int TickCount64; // eax
  struct IUPnPService *v16; // rcx
  int v17; // r14d
  int v18; // eax
  struct IUPnPService *v19; // rsi
  OLECHAR *v20; // rdi
  HRESULT (__stdcall *get_ServiceTypeIdentifier)(IUPnPService *, BSTR *); // r14
  int v22; // eax
  struct IUPnPService *v23; // rax
  struct IUPnPService *v25; // [rsp+20h] [rbp-28h] BYREF
  BSTR bstrString; // [rsp+28h] [rbp-20h] BYREF
  __int64 *v27; // [rsp+30h] [rbp-18h] BYREF
  _QWORD v28[2]; // [rsp+38h] [rbp-10h] BYREF

  v27 = 0;
  v28[0] = SysAllocString(a2);
  v8 = (OLECHAR *)v28[0];
  v25 = 0;
  bstrString = 0;
  if ( !v28[0] )
  {
    UPnPServiceByEnumeration = -2147024882;
LABEL_14:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&bstrString);
    wil::com_ptr_t<IUPnPServices,wil::err_returncode_policy>::~com_ptr_t<IUPnPServices,wil::err_returncode_policy>((__int64 *)&v25);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v28);
    wil::com_ptr_t<IUPnPServices,wil::err_returncode_policy>::~com_ptr_t<IUPnPServices,wil::err_returncode_policy>((__int64 *)&v27);
    return (unsigned int)UPnPServiceByEnumeration;
  }
  v10 = (__int64 *)*((_QWORD *)this + 3);
  v11 = *v10;
  v27 = 0;
  UPnPServiceByEnumeration = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v11 + 200))(v10, &v27);
  if ( UPnPServiceByEnumeration < 0 )
  {
    EventWriteError0(0x100000, L"get_Services returned 0x%x", (unsigned int)UPnPServiceByEnumeration);
    goto LABEL_5;
  }
  v13 = *v27;
  v25 = 0;
  v14 = (*(__int64 (__fastcall **)(__int64 *, OLECHAR *, struct IUPnPService **))(v13 + 72))(v27, v8, &v25);
  UPnPServiceByEnumeration = v14;
  if ( v14 == -2147024809 )
  {
    EventWriteError0(0x100000, L"get_Item for %ws return 0x%x", a2, 2147943568LL);
    EventWrite0(0x100000, L"Falling back to service enumeration search for %ws", a3);
    TickCount64 = GetTickCount64();
    v16 = v25;
    v17 = TickCount64;
    v25 = 0;
    if ( v16 )
      ((void (__fastcall *)(struct IUPnPService *))v16->lpVtbl->Release)(v16);
    UPnPServiceByEnumeration = TeredoUPnP::FindUPnPServiceByEnumeration(this, a3, &v25);
    v18 = GetTickCount64();
    ++*((_DWORD *)this + 29);
    *((_DWORD *)this + 30) += v18 - v17;
    *((_DWORD *)this + 31) = UPnPServiceByEnumeration;
    if ( UPnPServiceByEnumeration < 0 )
    {
      EventWriteError0(0x100000, L"Service enumeration failed with 0x%x", (unsigned int)UPnPServiceByEnumeration);
LABEL_5:
      v12 = bstrString;
      if ( !bstrString )
      {
LABEL_22:
        if ( v25 )
          ((void (__fastcall *)(struct IUPnPService *))v25->lpVtbl->Release)(v25);
        goto LABEL_24;
      }
LABEL_21:
      SysFreeString(v12);
      goto LABEL_22;
    }
  }
  else
  {
    if ( v14 < 0 )
    {
      EventWriteError0(0x100000, L"get_Item returned 0x%x", (unsigned int)v14);
      goto LABEL_14;
    }
    v19 = v25;
    v20 = bstrString;
    get_ServiceTypeIdentifier = v25->lpVtbl->get_ServiceTypeIdentifier;
    if ( bstrString )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)v28);
      SysFreeString(v20);
      wil::last_error_context::~last_error_context((wil::last_error_context *)v28);
    }
    bstrString = 0;
    v22 = ((__int64 (__fastcall *)(struct IUPnPService *, BSTR *))get_ServiceTypeIdentifier)(v19, &bstrString);
    UPnPServiceByEnumeration = v22;
    if ( v22 >= 0 )
    {
      EventWrite0(0x100000, L"Found UPnP service %ws", bstrString);
    }
    else
    {
      EventWriteError0(0x100000, L"get_ServiceTypeIdentifier returned 0x%x", (unsigned int)v22);
      EventWriteError0(0x100000, L"Discovered UPnP service has no type identifier");
    }
  }
  v23 = v25;
  v12 = bstrString;
  v25 = 0;
  *a4 = v23;
  if ( v12 )
    goto LABEL_21;
LABEL_24:
  SysFreeString(v8);
  if ( v27 )
    (*(void (__fastcall **)(__int64 *))(*v27 + 16))(v27);
  return (unsigned int)UPnPServiceByEnumeration;
}

```

## disassembly

```asm
0x180027700  push    rbp
0x180027702  push    rbx
0x180027703  push    rsi
0x180027704  push    rdi
0x180027705  push    r12
0x180027707  push    r13
0x180027709  push    r14
0x18002770b  push    r15
0x18002770d  mov     rbp, rsp
0x180027710  sub     rsp, 48h
0x180027714  mov     rsi, rcx
0x180027717  xor     edi, edi
0x180027719  mov     rcx, rdx; psz
0x18002771c  mov     [rbp+var_18], rdi
0x180027720  mov     r13, r9
0x180027723  mov     r12, r8
0x180027726  mov     r15, rdx
0x180027729  call    cs:__imp_SysAllocString
0x180027730  nop     dword ptr [rax+rax+00h]
0x180027735  mov     [rbp+var_10], rax
0x180027739  mov     rbx, rax
0x18002773c  mov     [rbp+var_28], rdi
0x180027740  mov     [rbp+bstrString], rdi
0x180027744  test    rax, rax
0x180027747  jnz     short loc_180027753
0x180027749  mov     edi, 8007000Eh
0x18002774e  jmp     loc_1800278AF
0x180027753  mov     rcx, [rbp+var_18]
0x180027757  mov     rdi, [rsi+18h]
0x18002775b  mov     rax, [rdi]
0x18002775e  mov     [rbp+var_18], 0
0x180027766  mov     r14, [rax+0C8h]
0x18002776d  test    rcx, rcx
0x180027770  jz      short loc_18002777E
0x180027772  mov     rax, [rcx]
0x180027775  mov     rax, [rax+10h]
0x180027779  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002777e  lea     rdx, [rbp+var_18]
0x180027782  mov     rcx, rdi
0x180027785  mov     rax, r14
0x180027788  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002778d  mov     edi, eax
0x18002778f  test    eax, eax
0x180027791  jns     short loc_1800277B9
0x180027793  lea     rdx, aGetServicesRet; "get_Services returned 0x%x"
0x18002779a  mov     r8d, edi
0x18002779d  mov     ecx, 100000h
0x1800277a2  call    EventWriteError0
0x1800277a7  mov     rcx, [rbp+bstrString]
0x1800277ab  test    rcx, rcx
0x1800277ae  jnz     loc_18002797A
0x1800277b4  jmp     loc_180027986
0x1800277b9  mov     rcx, [rbp+var_28]
0x1800277bd  mov     rdi, [rbp+var_18]
0x1800277c1  mov     rax, [rdi]
0x1800277c4  mov     [rbp+var_28], 0
0x1800277cc  mov     r14, [rax+48h]
0x1800277d0  test    rcx, rcx
0x1800277d3  jz      short loc_1800277E1
0x1800277d5  mov     rdx, [rcx]
0x1800277d8  mov     rax, [rdx+10h]
0x1800277dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800277e1  lea     r8, [rbp+var_28]
0x1800277e5  mov     rdx, rbx
0x1800277e8  mov     rcx, rdi
0x1800277eb  mov     rax, r14
0x1800277ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800277f3  mov     edi, eax
0x1800277f5  cmp     eax, 80070057h
0x1800277fa  jnz     loc_180027897
0x180027800  mov     r9d, 80070490h
0x180027806  lea     rdx, aGetItemForWsRe; "get_Item for %ws return 0x%x"
0x18002780d  mov     r8, r15
0x180027810  mov     ecx, 100000h
0x180027815  call    EventWriteError0
0x18002781a  mov     r8, r12
0x18002781d  lea     rdx, aFallingBackToS; "Falling back to service enumeration sea"...
0x180027824  mov     ecx, 100000h
0x180027829  call    EventWrite0
0x18002782e  call    cs:__imp_GetTickCount64
0x180027835  nop     dword ptr [rax+rax+00h]
0x18002783a  mov     rcx, [rbp+var_28]
0x18002783e  mov     r14, rax
0x180027841  mov     [rbp+var_28], 0
0x180027849  test    rcx, rcx
0x18002784c  jz      short loc_18002785A
0x18002784e  mov     rdx, [rcx]
0x180027851  mov     rax, [rdx+10h]
0x180027855  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002785a  lea     r8, [rbp+var_28]; struct IUPnPService **
0x18002785e  mov     rdx, r12; unsigned __int16 *
0x180027861  mov     rcx, rsi; this
0x180027864  call    ?FindUPnPServiceByEnumeration@TeredoUPnP@@AEAAJPEBGPEAPEAUIUPnPService@@@Z; TeredoUPnP::FindUPnPServiceByEnumeration(ushort const *,IUPnPService * *)
0x180027869  mov     edi, eax
0x18002786b  call    cs:__imp_GetTickCount64
0x180027872  nop     dword ptr [rax+rax+00h]
0x180027877  inc     dword ptr [rsi+74h]
0x18002787a  sub     eax, r14d
0x18002787d  add     [rsi+78h], eax
0x180027880  mov     [rsi+7Ch], edi
0x180027883  test    edi, edi
0x180027885  jns     loc_180027961
0x18002788b  lea     rdx, aServiceEnumera_1; "Service enumeration failed with 0x%x"
0x180027892  jmp     loc_18002779A
0x180027897  test    eax, eax
0x180027899  jns     short loc_1800278D8
0x18002789b  mov     r8d, eax
0x18002789e  lea     rdx, aGetItemReturne; "get_Item returned 0x%x"
0x1800278a5  mov     ecx, 100000h
0x1800278aa  call    EventWriteError0
0x1800278af  lea     rcx, [rbp+bstrString]
0x1800278b3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800278b8  lea     rcx, [rbp+var_28]
0x1800278bc  call    ??1?$com_ptr_t@UIUPnPServices@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUPnPServices,wil::err_returncode_policy>::~com_ptr_t<IUPnPServices,wil::err_returncode_policy>(void)
0x1800278c1  lea     rcx, [rbp+var_10]
0x1800278c5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800278ca  lea     rcx, [rbp+var_18]
0x1800278ce  call    ??1?$com_ptr_t@UIUPnPServices@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUPnPServices,wil::err_returncode_policy>::~com_ptr_t<IUPnPServices,wil::err_returncode_policy>(void)
0x1800278d3  jmp     loc_1800279BF
0x1800278d8  mov     rsi, [rbp+var_28]
0x1800278dc  mov     rdi, [rbp+bstrString]
0x1800278e0  mov     rax, [rsi]
0x1800278e3  mov     r14, [rax+48h]
0x1800278e7  test    rdi, rdi
0x1800278ea  jz      short loc_18002790D
0x1800278ec  lea     rcx, [rbp+var_10]; this
0x1800278f0  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800278f5  mov     rcx, rdi; bstrString
0x1800278f8  call    cs:__imp_SysFreeString
0x1800278ff  nop     dword ptr [rax+rax+00h]
0x180027904  lea     rcx, [rbp+var_10]; this
0x180027908  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002790d  lea     rdx, [rbp+bstrString]
0x180027911  mov     [rbp+bstrString], 0
0x180027919  mov     rcx, rsi
0x18002791c  mov     rax, r14
0x18002791f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027924  mov     edi, eax
0x180027926  mov     ecx, 100000h
0x18002792b  test    eax, eax
0x18002792d  jns     short loc_180027951
0x18002792f  mov     r8d, eax
0x180027932  lea     rdx, aGetServicetype; "get_ServiceTypeIdentifier returned 0x%x"
0x180027939  call    EventWriteError0
0x18002793e  lea     rdx, aDiscoveredUpnp; "Discovered UPnP service has no type ide"...
0x180027945  mov     ecx, 100000h
0x18002794a  call    EventWriteError0
0x18002794f  jmp     short loc_180027961
0x180027951  mov     r8, [rbp+bstrString]
0x180027955  lea     rdx, aFoundUpnpServi; "Found UPnP service %ws"
0x18002795c  call    EventWrite0
0x180027961  mov     rax, [rbp+var_28]
0x180027965  mov     rcx, [rbp+bstrString]; bstrString
0x180027969  mov     [rbp+var_28], 0
0x180027971  mov     [r13+0], rax
0x180027975  test    rcx, rcx
0x180027978  jz      short loc_18002799B
0x18002797a  call    cs:__imp_SysFreeString
0x180027981  nop     dword ptr [rax+rax+00h]
0x180027986  mov     rcx, [rbp+var_28]
0x18002798a  test    rcx, rcx
0x18002798d  jz      short loc_18002799B
0x18002798f  mov     rax, [rcx]
0x180027992  mov     rax, [rax+10h]
0x180027996  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002799b  mov     rcx, rbx; bstrString
0x18002799e  call    cs:__imp_SysFreeString
0x1800279a5  nop     dword ptr [rax+rax+00h]
0x1800279aa  mov     rcx, [rbp+var_18]
0x1800279ae  test    rcx, rcx
0x1800279b1  jz      short loc_1800279BF
0x1800279b3  mov     rax, [rcx]
0x1800279b6  mov     rax, [rax+10h]
0x1800279ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800279bf  mov     eax, edi
0x1800279c1  add     rsp, 48h
0x1800279c5  pop     r15
0x1800279c7  pop     r14
0x1800279c9  pop     r13
0x1800279cb  pop     r12
0x1800279cd  pop     rdi
0x1800279ce  pop     rsi
0x1800279cf  pop     rbx
0x1800279d0  pop     rbp
0x1800279d1  retn
```
