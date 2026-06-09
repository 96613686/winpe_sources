# TeredoUPnP::FindUPnPService(ushort const *,ushort const *,IUPnPService * *)

- ea: `0x1800276f0`
- end: `0x1800279c3`
- name: `?FindUPnPService@TeredoUPnP@@AEAAJPEBG0PEAPEAUIUPnPService@@@Z`
- size: `723`
- prototype: `int(TeredoUPnP *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct IUPnPService **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180027044`

## callees

- `0x18000d7b0`
- `0x1800190e0`
- `0x1800276f0`
- `0x1800279cc`
- `0x1800280f8`
- `0x180043374`
- `0x180073e08`
- `0x180073e34`
- `0x180083010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002781e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002785b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002781e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002785b`
- `OLEAUT32!__imp_SysAllocString` at `0x180027719`
- `OLEAUT32!__imp_SysAllocString` at `0x180027719`
- `OLEAUT32!__imp_SysFreeString` at `0x1800278e8`
- `OLEAUT32!__imp_SysFreeString` at `0x18002796a`
- `OLEAUT32!__imp_SysFreeString` at `0x18002798e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800278e8`
- `OLEAUT32!__imp_SysFreeString` at `0x18002796a`
- `OLEAUT32!__imp_SysFreeString` at `0x18002798e`

## string_xrefs

- `0x180027783`: `get_Services returned 0x%x`
- `0x18002780d`: `Falling back to service enumeration search for %ws`
- `0x180027945`: `Found UPnP service %ws`
- `0x180027922`: `get_ServiceTypeIdentifier returned 0x%x`
- `0x18002792e`: `Discovered UPnP service has no type identifier`
- `0x18002787b`: `Service enumeration failed with 0x%x`

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
    wil::com_ptr_t<IUPnPServices,wil::err_returncode_policy>::~com_ptr_t<IUPnPServices,wil::err_returncode_policy>(&v25);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v28);
    wil::com_ptr_t<IUPnPServices,wil::err_returncode_policy>::~com_ptr_t<IUPnPServices,wil::err_returncode_policy>(&v27);
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
0x1800276f0  push    rbp
0x1800276f2  push    rbx
0x1800276f3  push    rsi
0x1800276f4  push    rdi
0x1800276f5  push    r12
0x1800276f7  push    r13
0x1800276f9  push    r14
0x1800276fb  push    r15
0x1800276fd  mov     rbp, rsp
0x180027700  sub     rsp, 48h
0x180027704  mov     rsi, rcx
0x180027707  xor     edi, edi
0x180027709  mov     rcx, rdx; psz
0x18002770c  mov     [rbp+var_18], rdi
0x180027710  mov     r13, r9
0x180027713  mov     r12, r8
0x180027716  mov     r15, rdx
0x180027719  call    cs:__imp_SysAllocString
0x180027720  nop     dword ptr [rax+rax+00h]
0x180027725  mov     [rbp+var_10], rax
0x180027729  mov     rbx, rax
0x18002772c  mov     [rbp+var_28], rdi
0x180027730  mov     [rbp+bstrString], rdi
0x180027734  test    rax, rax
0x180027737  jnz     short loc_180027743
0x180027739  mov     edi, 8007000Eh
0x18002773e  jmp     loc_18002789F
0x180027743  mov     rcx, [rbp+var_18]
0x180027747  mov     rdi, [rsi+18h]
0x18002774b  mov     rax, [rdi]
0x18002774e  mov     [rbp+var_18], 0
0x180027756  mov     r14, [rax+0C8h]
0x18002775d  test    rcx, rcx
0x180027760  jz      short loc_18002776E
0x180027762  mov     rax, [rcx]
0x180027765  mov     rax, [rax+10h]
0x180027769  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002776e  lea     rdx, [rbp+var_18]
0x180027772  mov     rcx, rdi
0x180027775  mov     rax, r14
0x180027778  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002777d  mov     edi, eax
0x18002777f  test    eax, eax
0x180027781  jns     short loc_1800277A9
0x180027783  lea     rdx, aGetServicesRet; "get_Services returned 0x%x"
0x18002778a  mov     r8d, edi
0x18002778d  mov     ecx, 100000h
0x180027792  call    EventWriteError0
0x180027797  mov     rcx, [rbp+bstrString]
0x18002779b  test    rcx, rcx
0x18002779e  jnz     loc_18002796A
0x1800277a4  jmp     loc_180027976
0x1800277a9  mov     rcx, [rbp+var_28]
0x1800277ad  mov     rdi, [rbp+var_18]
0x1800277b1  mov     rax, [rdi]
0x1800277b4  mov     [rbp+var_28], 0
0x1800277bc  mov     r14, [rax+48h]
0x1800277c0  test    rcx, rcx
0x1800277c3  jz      short loc_1800277D1
0x1800277c5  mov     rdx, [rcx]
0x1800277c8  mov     rax, [rdx+10h]
0x1800277cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800277d1  lea     r8, [rbp+var_28]
0x1800277d5  mov     rdx, rbx
0x1800277d8  mov     rcx, rdi
0x1800277db  mov     rax, r14
0x1800277de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800277e3  mov     edi, eax
0x1800277e5  cmp     eax, 80070057h
0x1800277ea  jnz     loc_180027887
0x1800277f0  mov     r9d, 80070490h
0x1800277f6  lea     rdx, aGetItemForWsRe; "get_Item for %ws return 0x%x"
0x1800277fd  mov     r8, r15
0x180027800  mov     ecx, 100000h
0x180027805  call    EventWriteError0
0x18002780a  mov     r8, r12
0x18002780d  lea     rdx, aFallingBackToS; "Falling back to service enumeration sea"...
0x180027814  mov     ecx, 100000h
0x180027819  call    EventWrite0
0x18002781e  call    cs:__imp_GetTickCount64
0x180027825  nop     dword ptr [rax+rax+00h]
0x18002782a  mov     rcx, [rbp+var_28]
0x18002782e  mov     r14, rax
0x180027831  mov     [rbp+var_28], 0
0x180027839  test    rcx, rcx
0x18002783c  jz      short loc_18002784A
0x18002783e  mov     rdx, [rcx]
0x180027841  mov     rax, [rdx+10h]
0x180027845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002784a  lea     r8, [rbp+var_28]; struct IUPnPService **
0x18002784e  mov     rdx, r12; unsigned __int16 *
0x180027851  mov     rcx, rsi; this
0x180027854  call    ?FindUPnPServiceByEnumeration@TeredoUPnP@@AEAAJPEBGPEAPEAUIUPnPService@@@Z; TeredoUPnP::FindUPnPServiceByEnumeration(ushort const *,IUPnPService * *)
0x180027859  mov     edi, eax
0x18002785b  call    cs:__imp_GetTickCount64
0x180027862  nop     dword ptr [rax+rax+00h]
0x180027867  inc     dword ptr [rsi+74h]
0x18002786a  sub     eax, r14d
0x18002786d  add     [rsi+78h], eax
0x180027870  mov     [rsi+7Ch], edi
0x180027873  test    edi, edi
0x180027875  jns     loc_180027951
0x18002787b  lea     rdx, aServiceEnumera_1; "Service enumeration failed with 0x%x"
0x180027882  jmp     loc_18002778A
0x180027887  test    eax, eax
0x180027889  jns     short loc_1800278C8
0x18002788b  mov     r8d, eax
0x18002788e  lea     rdx, aGetItemReturne; "get_Item returned 0x%x"
0x180027895  mov     ecx, 100000h
0x18002789a  call    EventWriteError0
0x18002789f  lea     rcx, [rbp+bstrString]
0x1800278a3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800278a8  lea     rcx, [rbp+var_28]
0x1800278ac  call    ??1?$com_ptr_t@UIUPnPServices@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUPnPServices,wil::err_returncode_policy>::~com_ptr_t<IUPnPServices,wil::err_returncode_policy>(void)
0x1800278b1  lea     rcx, [rbp+var_10]
0x1800278b5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800278ba  lea     rcx, [rbp+var_18]
0x1800278be  call    ??1?$com_ptr_t@UIUPnPServices@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUPnPServices,wil::err_returncode_policy>::~com_ptr_t<IUPnPServices,wil::err_returncode_policy>(void)
0x1800278c3  jmp     loc_1800279AF
0x1800278c8  mov     rsi, [rbp+var_28]
0x1800278cc  mov     rdi, [rbp+bstrString]
0x1800278d0  mov     rax, [rsi]
0x1800278d3  mov     r14, [rax+48h]
0x1800278d7  test    rdi, rdi
0x1800278da  jz      short loc_1800278FD
0x1800278dc  lea     rcx, [rbp+var_10]; this
0x1800278e0  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800278e5  mov     rcx, rdi; bstrString
0x1800278e8  call    cs:__imp_SysFreeString
0x1800278ef  nop     dword ptr [rax+rax+00h]
0x1800278f4  lea     rcx, [rbp+var_10]; this
0x1800278f8  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800278fd  lea     rdx, [rbp+bstrString]
0x180027901  mov     [rbp+bstrString], 0
0x180027909  mov     rcx, rsi
0x18002790c  mov     rax, r14
0x18002790f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027914  mov     edi, eax
0x180027916  mov     ecx, 100000h
0x18002791b  test    eax, eax
0x18002791d  jns     short loc_180027941
0x18002791f  mov     r8d, eax
0x180027922  lea     rdx, aGetServicetype; "get_ServiceTypeIdentifier returned 0x%x"
0x180027929  call    EventWriteError0
0x18002792e  lea     rdx, aDiscoveredUpnp; "Discovered UPnP service has no type ide"...
0x180027935  mov     ecx, 100000h
0x18002793a  call    EventWriteError0
0x18002793f  jmp     short loc_180027951
0x180027941  mov     r8, [rbp+bstrString]
0x180027945  lea     rdx, aFoundUpnpServi; "Found UPnP service %ws"
0x18002794c  call    EventWrite0
0x180027951  mov     rax, [rbp+var_28]
0x180027955  mov     rcx, [rbp+bstrString]; bstrString
0x180027959  mov     [rbp+var_28], 0
0x180027961  mov     [r13+0], rax
0x180027965  test    rcx, rcx
0x180027968  jz      short loc_18002798B
0x18002796a  call    cs:__imp_SysFreeString
0x180027971  nop     dword ptr [rax+rax+00h]
0x180027976  mov     rcx, [rbp+var_28]
0x18002797a  test    rcx, rcx
0x18002797d  jz      short loc_18002798B
0x18002797f  mov     rax, [rcx]
0x180027982  mov     rax, [rax+10h]
0x180027986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002798b  mov     rcx, rbx; bstrString
0x18002798e  call    cs:__imp_SysFreeString
0x180027995  nop     dword ptr [rax+rax+00h]
0x18002799a  mov     rcx, [rbp+var_18]
0x18002799e  test    rcx, rcx
0x1800279a1  jz      short loc_1800279AF
0x1800279a3  mov     rax, [rcx]
0x1800279a6  mov     rax, [rax+10h]
0x1800279aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800279af  mov     eax, edi
0x1800279b1  add     rsp, 48h
0x1800279b5  pop     r15
0x1800279b7  pop     r14
0x1800279b9  pop     r13
0x1800279bb  pop     r12
0x1800279bd  pop     rdi
0x1800279be  pop     rsi
0x1800279bf  pop     rbx
0x1800279c0  pop     rbp
0x1800279c1  retn
```
