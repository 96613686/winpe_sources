# TeredoUPnP::FindUPnPServiceByEnumeration(ushort const *,IUPnPService * *)

- ea: `0x180028108`
- end: `0x18002853c`
- name: `?FindUPnPServiceByEnumeration@TeredoUPnP@@AEAAJPEBGPEAPEAUIUPnPService@@@Z`
- size: `1076`
- prototype: `__int64 __fastcall(TeredoUPnP *this, const unsigned __int16 *, struct IUPnPService **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180027700`

## callees

- `0x18000d7c0`
- `0x1800190f0`
- `0x1800279dc`
- `0x180028108`
- `0x180043334`
- `0x180073e28`
- `0x180073e54`
- `0x180083010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180028485`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180028485`
- `OLEAUT32!__imp_SysFreeString` at `0x1800281ae`
- `OLEAUT32!__imp_SysFreeString` at `0x180028318`
- `OLEAUT32!__imp_SysFreeString` at `0x180028437`
- `OLEAUT32!__imp_SysFreeString` at `0x1800281ae`
- `OLEAUT32!__imp_SysFreeString` at `0x180028318`
- `OLEAUT32!__imp_SysFreeString` at `0x180028437`
- `OLEAUT32!__imp_VariantInit` at `0x18002813a`
- `OLEAUT32!__imp_VariantInit` at `0x1800283b0`
- `OLEAUT32!__imp_VariantInit` at `0x18002813a`
- `OLEAUT32!__imp_VariantInit` at `0x1800283b0`
- `OLEAUT32!__imp_VariantClear` at `0x1800281be`
- `OLEAUT32!__imp_VariantClear` at `0x180028328`
- `OLEAUT32!__imp_VariantClear` at `0x1800283a0`
- `OLEAUT32!__imp_VariantClear` at `0x1800284e2`
- `OLEAUT32!__imp_VariantClear` at `0x1800281be`
- `OLEAUT32!__imp_VariantClear` at `0x180028328`
- `OLEAUT32!__imp_VariantClear` at `0x1800283a0`
- `OLEAUT32!__imp_VariantClear` at `0x1800284e2`

## string_xrefs

- `0x180028191`: `get_Services returned 0x%x`
- `0x180028472`: `Service enumeration found UPnP service %ws`
- `0x180028530`: `QueryInterface<IUPnPService> returned 0x%x`
- `0x180028524`: `get_ServiceTypeIdentifier returned 0x%x`
- `0x180028251`: `No services to enumerate!`
- `0x18002849e`: `Using enumerated service %ws`
- `0x1800284bf`: `Service enumeration found no matching service`

## pseudocode

```c
__int64 __fastcall TeredoUPnP::FindUPnPServiceByEnumeration(
        TeredoUPnP *this,
        const unsigned __int16 *a2,
        struct IUPnPService **a3)
{
  __int64 *v6; // rbx
  __int64 v7; // rax
  int v8; // ebx
  unsigned int v10; // esi
  __int64 v11; // rcx
  __int64 v12; // rbx
  __int64 v13; // rax
  __int64 (__fastcall *v14)(__int64, __int64 *); // rdi
  int v15; // eax
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rdi
  unsigned int (__fastcall *v19)(__int64, __int64, VARIANTARG *); // rbx
  struct IUPnPService *v20; // rcx
  struct IUPnPService *v21; // rdi
  OLECHAR *v22; // rbx
  HRESULT (__stdcall *get_ServiceTypeIdentifier)(IUPnPService *, BSTR *); // rsi
  int v24; // eax
  __int64 *v25; // [rsp+30h] [rbp-40h] BYREF
  __int64 v26; // [rsp+38h] [rbp-38h] BYREF
  __int64 v27; // [rsp+40h] [rbp-30h] BYREF
  _BYTE v28[8]; // [rsp+48h] [rbp-28h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-20h] BYREF
  int v30; // [rsp+B0h] [rbp+40h] BYREF
  BSTR bstrString; // [rsp+C0h] [rbp+50h] BYREF
  struct IUPnPService *v32; // [rsp+C8h] [rbp+58h] BYREF

  v25 = 0;
  v27 = 0;
  v26 = 0;
  v32 = 0;
  VariantInit(&pvarg);
  *a3 = 0;
  v6 = (__int64 *)*((_QWORD *)this + 3);
  bstrString = 0;
  v30 = 0;
  v7 = *v6;
  v25 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v7 + 200))(v6, &v25);
  if ( v8 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v25 + 56))(v25, &v30);
    if ( v8 < 0 )
    {
      EventWriteError0(0x100000, L"get_Count returned 0x%x", (unsigned int)v8);
      goto LABEL_3;
    }
    if ( v30 )
    {
      v11 = v27;
      v12 = (__int64)v25;
      v13 = *v25;
      v27 = 0;
      v14 = *(__int64 (__fastcall **)(__int64, __int64 *))(v13 + 64);
      if ( v11 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      v15 = v14(v12, &v27);
      v10 = v15;
      if ( v15 >= 0 )
      {
        v16 = v26;
        v26 = 0;
        if ( v16 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
        v17 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v27)(
                v27,
                &GUID_00020404_0000_0000_c000_000000000046,
                &v26);
        v10 = v17;
        if ( v17 < 0 )
        {
          EventWriteError0(0x100000, L"QueryInterface<IEnumVARIANT> returned 0x%x", (unsigned int)v17);
          if ( bstrString )
            SysFreeString(bstrString);
          VariantClear(&pvarg);
          if ( v32 )
            ((void (__fastcall *)(struct IUPnPService *))v32->lpVtbl->Release)(v32);
          if ( v26 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
          if ( v27 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
          if ( v25 )
            (*(void (__fastcall **)(__int64 *))(*v25 + 16))(v25);
          return v10;
        }
        while ( 1 )
        {
          v18 = v26;
          v19 = *(unsigned int (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v26 + 24LL);
          VariantClear(&pvarg);
          VariantInit(&pvarg);
          if ( v19(v18, 1, &pvarg) )
            break;
          v20 = v32;
          v32 = 0;
          if ( v20 )
            ((void (__fastcall *)(struct IUPnPService *))v20->lpVtbl->Release)(v20);
          v8 = (**(__int64 (__fastcall ***)(LONGLONG, GUID *, struct IUPnPService **))pvarg.llVal)(
                 pvarg.llVal,
                 &GUID_a295019c_dc65_47dd_90dc_7fe918a1ab44,
                 &v32);
          if ( v8 < 0 )
          {
            EventWriteError0(0x100000, L"QueryInterface<IUPnPService> returned 0x%x", (unsigned int)v8);
            goto LABEL_3;
          }
          v21 = v32;
          v22 = bstrString;
          get_ServiceTypeIdentifier = v32->lpVtbl->get_ServiceTypeIdentifier;
          if ( bstrString )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)v28);
            SysFreeString(v22);
            wil::last_error_context::~last_error_context((wil::last_error_context *)v28);
          }
          bstrString = 0;
          v24 = ((__int64 (__fastcall *)(struct IUPnPService *, BSTR *))get_ServiceTypeIdentifier)(v21, &bstrString);
          v10 = v24;
          if ( v24 < 0 )
          {
            EventWriteError0(0x100000, L"get_ServiceTypeIdentifier returned 0x%x", (unsigned int)v24);
            goto LABEL_46;
          }
          EventWrite0(0x100000, L"Service enumeration found UPnP service %ws", bstrString);
          if ( wcsstr(bstrString, a2) )
          {
            EventWrite0(0x100000, L"Using enumerated service %ws", bstrString);
            *a3 = v32;
            v32 = 0;
            break;
          }
        }
        if ( !*a3 )
        {
          EventWriteError0(0x100000, L"Service enumeration found no matching service");
          v10 = -2147023728;
        }
      }
      else
      {
        EventWriteError0(0x100000, L"get_NewEnum returned 0x%x", (unsigned int)v15);
      }
    }
    else
    {
      EventWriteError0(0x100000, L"No services to enumerate!");
      v10 = -2147024637;
    }
LABEL_46:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&bstrString);
    VariantClear(&pvarg);
    wil::com_ptr_t<IUPnPServices,wil::err_returncode_policy>::~com_ptr_t<IUPnPServices,wil::err_returncode_policy>((__int64 *)&v32);
    wil::com_ptr_t<IUPnPServices,wil::err_returncode_policy>::~com_ptr_t<IUPnPServices,wil::err_returncode_policy>(&v26);
    wil::com_ptr_t<IUPnPServices,wil::err_returncode_policy>::~com_ptr_t<IUPnPServices,wil::err_returncode_policy>(&v27);
    wil::com_ptr_t<IUPnPServices,wil::err_returncode_policy>::~com_ptr_t<IUPnPServices,wil::err_returncode_policy>((__int64 *)&v25);
    return v10;
  }
  EventWriteError0(0x100000, L"get_Services returned 0x%x", (unsigned int)v8);
LABEL_3:
  if ( bstrString )
    SysFreeString(bstrString);
  VariantClear(&pvarg);
  if ( v32 )
    ((void (__fastcall *)(struct IUPnPService *))v32->lpVtbl->Release)(v32);
  if ( v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  if ( v27 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  if ( v25 )
    (*(void (__fastcall **)(__int64 *))(*v25 + 16))(v25);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180028108  push    rbp
0x18002810a  push    rbx
0x18002810b  push    rsi
0x18002810c  push    rdi
0x18002810d  push    r12
0x18002810f  push    r14
0x180028111  push    r15
0x180028113  mov     rbp, rsp
0x180028116  sub     rsp, 70h
0x18002811a  xor     r12d, r12d
0x18002811d  mov     rbx, rcx
0x180028120  lea     rcx, [rbp+pvarg]; pvarg
0x180028124  mov     [rbp+var_40], r12
0x180028128  mov     [rbp+var_30], r12
0x18002812c  mov     r14, r8
0x18002812f  mov     [rbp+var_38], r12
0x180028133  mov     r15, rdx
0x180028136  mov     [rbp+arg_18], r12
0x18002813a  call    cs:__imp_VariantInit
0x180028141  nop     dword ptr [rax+rax+00h]
0x180028146  mov     rcx, [rbp+var_40]
0x18002814a  mov     [r14], r12
0x18002814d  mov     rbx, [rbx+18h]
0x180028151  mov     [rbp+bstrString], r12
0x180028155  mov     [rbp+arg_0], r12d
0x180028159  mov     rax, [rbx]
0x18002815c  mov     [rbp+var_40], r12
0x180028160  mov     rdi, [rax+0C8h]
0x180028167  test    rcx, rcx
0x18002816a  jz      short loc_180028178
0x18002816c  mov     rax, [rcx]
0x18002816f  mov     rax, [rax+10h]
0x180028173  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028178  lea     rdx, [rbp+var_40]
0x18002817c  mov     rcx, rbx
0x18002817f  mov     rax, rdi
0x180028182  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028187  mov     ebx, eax
0x180028189  test    eax, eax
0x18002818b  jns     loc_180028225
0x180028191  lea     rdx, aGetServicesRet; "get_Services returned 0x%x"
0x180028198  mov     r8d, ebx
0x18002819b  mov     ecx, 100000h
0x1800281a0  call    EventWriteError0
0x1800281a5  mov     rcx, [rbp+bstrString]; bstrString
0x1800281a9  test    rcx, rcx
0x1800281ac  jz      short loc_1800281BA
0x1800281ae  call    cs:__imp_SysFreeString
0x1800281b5  nop     dword ptr [rax+rax+00h]
0x1800281ba  lea     rcx, [rbp+pvarg]; pvarg
0x1800281be  call    cs:__imp_VariantClear
0x1800281c5  nop     dword ptr [rax+rax+00h]
0x1800281ca  mov     rcx, [rbp+arg_18]
0x1800281ce  test    rcx, rcx
0x1800281d1  jz      short loc_1800281DF
0x1800281d3  mov     rax, [rcx]
0x1800281d6  mov     rax, [rax+10h]
0x1800281da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800281df  mov     rcx, [rbp+var_38]
0x1800281e3  test    rcx, rcx
0x1800281e6  jz      short loc_1800281F4
0x1800281e8  mov     rax, [rcx]
0x1800281eb  mov     rax, [rax+10h]
0x1800281ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800281f4  mov     rcx, [rbp+var_30]
0x1800281f8  test    rcx, rcx
0x1800281fb  jz      short loc_180028209
0x1800281fd  mov     rax, [rcx]
0x180028200  mov     rax, [rax+10h]
0x180028204  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028209  mov     rcx, [rbp+var_40]
0x18002820d  test    rcx, rcx
0x180028210  jz      short loc_18002821E
0x180028212  mov     rax, [rcx]
0x180028215  mov     rax, [rax+10h]
0x180028219  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002821e  mov     eax, ebx
0x180028220  jmp     loc_180028514
0x180028225  mov     rcx, [rbp+var_40]
0x180028229  lea     rdx, [rbp+arg_0]
0x18002822d  mov     rax, [rcx]
0x180028230  mov     rax, [rax+38h]
0x180028234  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028239  mov     ebx, eax
0x18002823b  test    eax, eax
0x18002823d  jns     short loc_18002824B
0x18002823f  lea     rdx, aGetCountReturn; "get_Count returned 0x%x"
0x180028246  jmp     loc_180028198
0x18002824b  cmp     [rbp+arg_0], r12d
0x18002824f  jnz     short loc_18002826C
0x180028251  lea     rdx, aNoServicesToEn; "No services to enumerate!"
0x180028258  mov     ecx, 100000h
0x18002825d  call    EventWriteError0
0x180028262  mov     esi, 80070103h
0x180028267  jmp     loc_1800284D5
0x18002826c  mov     rcx, [rbp+var_30]
0x180028270  mov     rbx, [rbp+var_40]
0x180028274  mov     rax, [rbx]
0x180028277  mov     [rbp+var_30], r12
0x18002827b  mov     rdi, [rax+40h]
0x18002827f  test    rcx, rcx
0x180028282  jz      short loc_180028290
0x180028284  mov     rdx, [rcx]
0x180028287  mov     rax, [rdx+10h]
0x18002828b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028290  lea     rdx, [rbp+var_30]
0x180028294  mov     rcx, rbx
0x180028297  mov     rax, rdi
0x18002829a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002829f  mov     esi, eax
0x1800282a1  test    eax, eax
0x1800282a3  jns     short loc_1800282BE
0x1800282a5  lea     rdx, aGetNewenumRetu; "get_NewEnum returned 0x%x"
0x1800282ac  mov     ecx, 100000h
0x1800282b1  mov     r8d, eax
0x1800282b4  call    EventWriteError0
0x1800282b9  jmp     loc_1800284D5
0x1800282be  mov     rcx, [rbp+var_38]
0x1800282c2  mov     [rbp+var_38], r12
0x1800282c6  test    rcx, rcx
0x1800282c9  jz      short loc_1800282D7
0x1800282cb  mov     rax, [rcx]
0x1800282ce  mov     rax, [rax+10h]
0x1800282d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800282d7  mov     rcx, [rbp+var_30]
0x1800282db  lea     r8, [rbp+var_38]
0x1800282df  lea     rdx, _GUID_00020404_0000_0000_c000_000000000046
0x1800282e6  mov     rax, [rcx]
0x1800282e9  mov     rax, [rax]
0x1800282ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800282f1  mov     esi, eax
0x1800282f3  test    eax, eax
0x1800282f5  jns     loc_180028391
0x1800282fb  mov     r8d, eax
0x1800282fe  lea     rdx, aQueryinterface_1; "QueryInterface<IEnumVARIANT> returned 0"...
0x180028305  mov     ecx, 100000h
0x18002830a  call    EventWriteError0
0x18002830f  mov     rcx, [rbp+bstrString]; bstrString
0x180028313  test    rcx, rcx
0x180028316  jz      short loc_180028324
0x180028318  call    cs:__imp_SysFreeString
0x18002831f  nop     dword ptr [rax+rax+00h]
0x180028324  lea     rcx, [rbp+pvarg]; pvarg
0x180028328  call    cs:__imp_VariantClear
0x18002832f  nop     dword ptr [rax+rax+00h]
0x180028334  mov     rcx, [rbp+arg_18]
0x180028338  test    rcx, rcx
0x18002833b  jz      short loc_180028349
0x18002833d  mov     rax, [rcx]
0x180028340  mov     rax, [rax+10h]
0x180028344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028349  mov     rcx, [rbp+var_38]
0x18002834d  test    rcx, rcx
0x180028350  jz      short loc_18002835E
0x180028352  mov     rax, [rcx]
0x180028355  mov     rax, [rax+10h]
0x180028359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002835e  mov     rcx, [rbp+var_30]
0x180028362  test    rcx, rcx
0x180028365  jz      short loc_180028373
0x180028367  mov     rax, [rcx]
0x18002836a  mov     rax, [rax+10h]
0x18002836e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028373  mov     rcx, [rbp+var_40]
0x180028377  test    rcx, rcx
0x18002837a  jz      loc_180028512
0x180028380  mov     rax, [rcx]
0x180028383  mov     rax, [rax+10h]
0x180028387  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002838c  jmp     loc_180028512
0x180028391  mov     rdi, [rbp+var_38]
0x180028395  lea     rcx, [rbp+pvarg]; pvarg
0x180028399  mov     rax, [rdi]
0x18002839c  mov     rbx, [rax+18h]
0x1800283a0  call    cs:__imp_VariantClear
0x1800283a7  nop     dword ptr [rax+rax+00h]
0x1800283ac  lea     rcx, [rbp+pvarg]; pvarg
0x1800283b0  call    cs:__imp_VariantInit
0x1800283b7  nop     dword ptr [rax+rax+00h]
0x1800283bc  xor     r9d, r9d
0x1800283bf  lea     r8, [rbp+pvarg]
0x1800283c3  mov     rcx, rdi
0x1800283c6  mov     rax, rbx
0x1800283c9  lea     edx, [r9+1]
0x1800283cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800283d2  test    eax, eax
0x1800283d4  jnz     loc_1800284BA
0x1800283da  mov     rcx, [rbp+arg_18]
0x1800283de  mov     [rbp+arg_18], r12
0x1800283e2  test    rcx, rcx
0x1800283e5  jz      short loc_1800283F3
0x1800283e7  mov     rax, [rcx]
0x1800283ea  mov     rax, [rax+10h]
0x1800283ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800283f3  mov     rcx, qword ptr [rbp+pvarg+8]
0x1800283f7  lea     r8, [rbp+arg_18]
0x1800283fb  lea     rdx, _GUID_a295019c_dc65_47dd_90dc_7fe918a1ab44
0x180028402  mov     rax, [rcx]
0x180028405  mov     rax, [rax]
0x180028408  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002840d  mov     ebx, eax
0x18002840f  test    eax, eax
0x180028411  js      loc_180028530
0x180028417  mov     rdi, [rbp+arg_18]
0x18002841b  mov     rbx, [rbp+bstrString]
0x18002841f  mov     rax, [rdi]
0x180028422  mov     rsi, [rax+48h]
0x180028426  test    rbx, rbx
0x180028429  jz      short loc_18002844C
0x18002842b  lea     rcx, [rbp+var_28]; this
0x18002842f  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180028434  mov     rcx, rbx; bstrString
0x180028437  call    cs:__imp_SysFreeString
0x18002843e  nop     dword ptr [rax+rax+00h]
0x180028443  lea     rcx, [rbp+var_28]; this
0x180028447  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002844c  lea     rdx, [rbp+bstrString]
0x180028450  mov     [rbp+bstrString], r12
0x180028454  mov     rcx, rdi
0x180028457  mov     rax, rsi
0x18002845a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002845f  mov     esi, eax
0x180028461  mov     ecx, 100000h
0x180028466  test    eax, eax
0x180028468  js      loc_180028524
0x18002846e  mov     r8, [rbp+bstrString]
0x180028472  lea     rdx, aServiceEnumera; "Service enumeration found UPnP service "...
0x180028479  call    EventWrite0
0x18002847e  mov     rcx, [rbp+bstrString]; Str
0x180028482  mov     rdx, r15; SubStr
0x180028485  call    cs:__imp_wcsstr
0x18002848c  nop     dword ptr [rax+rax+00h]
0x180028491  test    rax, rax
0x180028494  jz      loc_180028391
0x18002849a  mov     r8, [rbp+bstrString]
0x18002849e  lea     rdx, aUsingEnumerate; "Using enumerated service %ws"
0x1800284a5  mov     ecx, 100000h
0x1800284aa  call    EventWrite0
0x1800284af  mov     rax, [rbp+arg_18]
0x1800284b3  mov     [r14], rax
0x1800284b6  mov     [rbp+arg_18], r12
0x1800284ba  cmp     [r14], r12
0x1800284bd  jnz     short loc_1800284D5
0x1800284bf  lea     rdx, aServiceEnumera_0; "Service enumeration found no matching s"...
0x1800284c6  mov     ecx, 100000h
0x1800284cb  call    EventWriteError0
0x1800284d0  mov     esi, 80070490h
0x1800284d5  lea     rcx, [rbp+bstrString]
0x1800284d9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800284de  lea     rcx, [rbp+pvarg]; pvarg
0x1800284e2  call    cs:__imp_VariantClear
0x1800284e9  nop     dword ptr [rax+rax+00h]
0x1800284ee  lea     rcx, [rbp+arg_18]
0x1800284f2  call    ??1?$com_ptr_t@UIUPnPServices@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUPnPServices,wil::err_returncode_policy>::~com_ptr_t<IUPnPServices,wil::err_returncode_policy>(void)
0x1800284f7  lea     rcx, [rbp+var_38]
0x1800284fb  call    ??1?$com_ptr_t@UIUPnPServices@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUPnPServices,wil::err_returncode_policy>::~com_ptr_t<IUPnPServices,wil::err_returncode_policy>(void)
0x180028500  lea     rcx, [rbp+var_30]
0x180028504  call    ??1?$com_ptr_t@UIUPnPServices@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUPnPServices,wil::err_returncode_policy>::~com_ptr_t<IUPnPServices,wil::err_returncode_policy>(void)
0x180028509  lea     rcx, [rbp+var_40]
0x18002850d  call    ??1?$com_ptr_t@UIUPnPServices@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUPnPServices,wil::err_returncode_policy>::~com_ptr_t<IUPnPServices,wil::err_returncode_policy>(void)
0x180028512  mov     eax, esi
0x180028514  add     rsp, 70h
0x180028518  pop     r15
0x18002851a  pop     r14
0x18002851c  pop     r12
0x18002851e  pop     rdi
0x18002851f  pop     rsi
0x180028520  pop     rbx
0x180028521  pop     rbp
0x180028522  retn
0x180028524  lea     rdx, aGetServicetype; "get_ServiceTypeIdentifier returned 0x%x"
0x18002852b  jmp     loc_1800282B1
0x180028530  lea     rdx, aQueryinterface; "QueryInterface<IUPnPService> returned 0"...
0x180028537  jmp     loc_180028198
```
