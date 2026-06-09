# TeredoUPnP::FindUPnPServiceByEnumeration(ushort const *,IUPnPService * *)

- ea: `0x1800280f8`
- end: `0x18002852c`
- name: `?FindUPnPServiceByEnumeration@TeredoUPnP@@AEAAJPEBGPEAPEAUIUPnPService@@@Z`
- size: `1076`
- prototype: `int(TeredoUPnP *__hidden this, const unsigned __int16 *, struct IUPnPService **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800276f0`

## callees

- `0x18000d7b0`
- `0x1800190e0`
- `0x1800279cc`
- `0x1800280f8`
- `0x180043374`
- `0x180073e08`
- `0x180073e34`
- `0x180083010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180028475`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180028475`
- `OLEAUT32!__imp_SysFreeString` at `0x18002819e`
- `OLEAUT32!__imp_SysFreeString` at `0x180028308`
- `OLEAUT32!__imp_SysFreeString` at `0x180028427`
- `OLEAUT32!__imp_SysFreeString` at `0x18002819e`
- `OLEAUT32!__imp_SysFreeString` at `0x180028308`
- `OLEAUT32!__imp_SysFreeString` at `0x180028427`
- `OLEAUT32!__imp_VariantInit` at `0x18002812a`
- `OLEAUT32!__imp_VariantInit` at `0x1800283a0`
- `OLEAUT32!__imp_VariantInit` at `0x18002812a`
- `OLEAUT32!__imp_VariantInit` at `0x1800283a0`
- `OLEAUT32!__imp_VariantClear` at `0x1800281ae`
- `OLEAUT32!__imp_VariantClear` at `0x180028318`
- `OLEAUT32!__imp_VariantClear` at `0x180028390`
- `OLEAUT32!__imp_VariantClear` at `0x1800284d2`
- `OLEAUT32!__imp_VariantClear` at `0x1800281ae`
- `OLEAUT32!__imp_VariantClear` at `0x180028318`
- `OLEAUT32!__imp_VariantClear` at `0x180028390`
- `OLEAUT32!__imp_VariantClear` at `0x1800284d2`

## string_xrefs

- `0x180028181`: `get_Services returned 0x%x`
- `0x180028462`: `Service enumeration found UPnP service %ws`
- `0x180028520`: `QueryInterface<IUPnPService> returned 0x%x`
- `0x180028514`: `get_ServiceTypeIdentifier returned 0x%x`
- `0x180028241`: `No services to enumerate!`
- `0x18002848e`: `Using enumerated service %ws`
- `0x1800284af`: `Service enumeration found no matching service`

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
  __int64 *v12; // rbx
  __int64 v13; // rax
  __int64 (__fastcall *v14)(__int64 *, __int64 *); // rdi
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
      v12 = v25;
      v13 = *v25;
      v27 = 0;
      v14 = *(__int64 (__fastcall **)(__int64 *, __int64 *))(v13 + 64);
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
    wil::com_ptr_t<IUPnPServices,wil::err_returncode_policy>::~com_ptr_t<IUPnPServices,wil::err_returncode_policy>(&v32);
    wil::com_ptr_t<IUPnPServices,wil::err_returncode_policy>::~com_ptr_t<IUPnPServices,wil::err_returncode_policy>(&v26);
    wil::com_ptr_t<IUPnPServices,wil::err_returncode_policy>::~com_ptr_t<IUPnPServices,wil::err_returncode_policy>(&v27);
    wil::com_ptr_t<IUPnPServices,wil::err_returncode_policy>::~com_ptr_t<IUPnPServices,wil::err_returncode_policy>(&v25);
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
0x1800280f8  push    rbp
0x1800280fa  push    rbx
0x1800280fb  push    rsi
0x1800280fc  push    rdi
0x1800280fd  push    r12
0x1800280ff  push    r14
0x180028101  push    r15
0x180028103  mov     rbp, rsp
0x180028106  sub     rsp, 70h
0x18002810a  xor     r12d, r12d
0x18002810d  mov     rbx, rcx
0x180028110  lea     rcx, [rbp+pvarg]; pvarg
0x180028114  mov     [rbp+var_40], r12
0x180028118  mov     [rbp+var_30], r12
0x18002811c  mov     r14, r8
0x18002811f  mov     [rbp+var_38], r12
0x180028123  mov     r15, rdx
0x180028126  mov     [rbp+arg_18], r12
0x18002812a  call    cs:__imp_VariantInit
0x180028131  nop     dword ptr [rax+rax+00h]
0x180028136  mov     rcx, [rbp+var_40]
0x18002813a  mov     [r14], r12
0x18002813d  mov     rbx, [rbx+18h]
0x180028141  mov     [rbp+bstrString], r12
0x180028145  mov     [rbp+arg_0], r12d
0x180028149  mov     rax, [rbx]
0x18002814c  mov     [rbp+var_40], r12
0x180028150  mov     rdi, [rax+0C8h]
0x180028157  test    rcx, rcx
0x18002815a  jz      short loc_180028168
0x18002815c  mov     rax, [rcx]
0x18002815f  mov     rax, [rax+10h]
0x180028163  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028168  lea     rdx, [rbp+var_40]
0x18002816c  mov     rcx, rbx
0x18002816f  mov     rax, rdi
0x180028172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028177  mov     ebx, eax
0x180028179  test    eax, eax
0x18002817b  jns     loc_180028215
0x180028181  lea     rdx, aGetServicesRet; "get_Services returned 0x%x"
0x180028188  mov     r8d, ebx
0x18002818b  mov     ecx, 100000h
0x180028190  call    EventWriteError0
0x180028195  mov     rcx, [rbp+bstrString]; bstrString
0x180028199  test    rcx, rcx
0x18002819c  jz      short loc_1800281AA
0x18002819e  call    cs:__imp_SysFreeString
0x1800281a5  nop     dword ptr [rax+rax+00h]
0x1800281aa  lea     rcx, [rbp+pvarg]; pvarg
0x1800281ae  call    cs:__imp_VariantClear
0x1800281b5  nop     dword ptr [rax+rax+00h]
0x1800281ba  mov     rcx, [rbp+arg_18]
0x1800281be  test    rcx, rcx
0x1800281c1  jz      short loc_1800281CF
0x1800281c3  mov     rax, [rcx]
0x1800281c6  mov     rax, [rax+10h]
0x1800281ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800281cf  mov     rcx, [rbp+var_38]
0x1800281d3  test    rcx, rcx
0x1800281d6  jz      short loc_1800281E4
0x1800281d8  mov     rax, [rcx]
0x1800281db  mov     rax, [rax+10h]
0x1800281df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800281e4  mov     rcx, [rbp+var_30]
0x1800281e8  test    rcx, rcx
0x1800281eb  jz      short loc_1800281F9
0x1800281ed  mov     rax, [rcx]
0x1800281f0  mov     rax, [rax+10h]
0x1800281f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800281f9  mov     rcx, [rbp+var_40]
0x1800281fd  test    rcx, rcx
0x180028200  jz      short loc_18002820E
0x180028202  mov     rax, [rcx]
0x180028205  mov     rax, [rax+10h]
0x180028209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002820e  mov     eax, ebx
0x180028210  jmp     loc_180028504
0x180028215  mov     rcx, [rbp+var_40]
0x180028219  lea     rdx, [rbp+arg_0]
0x18002821d  mov     rax, [rcx]
0x180028220  mov     rax, [rax+38h]
0x180028224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028229  mov     ebx, eax
0x18002822b  test    eax, eax
0x18002822d  jns     short loc_18002823B
0x18002822f  lea     rdx, aGetCountReturn; "get_Count returned 0x%x"
0x180028236  jmp     loc_180028188
0x18002823b  cmp     [rbp+arg_0], r12d
0x18002823f  jnz     short loc_18002825C
0x180028241  lea     rdx, aNoServicesToEn; "No services to enumerate!"
0x180028248  mov     ecx, 100000h
0x18002824d  call    EventWriteError0
0x180028252  mov     esi, 80070103h
0x180028257  jmp     loc_1800284C5
0x18002825c  mov     rcx, [rbp+var_30]
0x180028260  mov     rbx, [rbp+var_40]
0x180028264  mov     rax, [rbx]
0x180028267  mov     [rbp+var_30], r12
0x18002826b  mov     rdi, [rax+40h]
0x18002826f  test    rcx, rcx
0x180028272  jz      short loc_180028280
0x180028274  mov     rdx, [rcx]
0x180028277  mov     rax, [rdx+10h]
0x18002827b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028280  lea     rdx, [rbp+var_30]
0x180028284  mov     rcx, rbx
0x180028287  mov     rax, rdi
0x18002828a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002828f  mov     esi, eax
0x180028291  test    eax, eax
0x180028293  jns     short loc_1800282AE
0x180028295  lea     rdx, aGetNewenumRetu; "get_NewEnum returned 0x%x"
0x18002829c  mov     ecx, 100000h
0x1800282a1  mov     r8d, eax
0x1800282a4  call    EventWriteError0
0x1800282a9  jmp     loc_1800284C5
0x1800282ae  mov     rcx, [rbp+var_38]
0x1800282b2  mov     [rbp+var_38], r12
0x1800282b6  test    rcx, rcx
0x1800282b9  jz      short loc_1800282C7
0x1800282bb  mov     rax, [rcx]
0x1800282be  mov     rax, [rax+10h]
0x1800282c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800282c7  mov     rcx, [rbp+var_30]
0x1800282cb  lea     r8, [rbp+var_38]
0x1800282cf  lea     rdx, _GUID_00020404_0000_0000_c000_000000000046
0x1800282d6  mov     rax, [rcx]
0x1800282d9  mov     rax, [rax]
0x1800282dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800282e1  mov     esi, eax
0x1800282e3  test    eax, eax
0x1800282e5  jns     loc_180028381
0x1800282eb  mov     r8d, eax
0x1800282ee  lea     rdx, aQueryinterface_1; "QueryInterface<IEnumVARIANT> returned 0"...
0x1800282f5  mov     ecx, 100000h
0x1800282fa  call    EventWriteError0
0x1800282ff  mov     rcx, [rbp+bstrString]; bstrString
0x180028303  test    rcx, rcx
0x180028306  jz      short loc_180028314
0x180028308  call    cs:__imp_SysFreeString
0x18002830f  nop     dword ptr [rax+rax+00h]
0x180028314  lea     rcx, [rbp+pvarg]; pvarg
0x180028318  call    cs:__imp_VariantClear
0x18002831f  nop     dword ptr [rax+rax+00h]
0x180028324  mov     rcx, [rbp+arg_18]
0x180028328  test    rcx, rcx
0x18002832b  jz      short loc_180028339
0x18002832d  mov     rax, [rcx]
0x180028330  mov     rax, [rax+10h]
0x180028334  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028339  mov     rcx, [rbp+var_38]
0x18002833d  test    rcx, rcx
0x180028340  jz      short loc_18002834E
0x180028342  mov     rax, [rcx]
0x180028345  mov     rax, [rax+10h]
0x180028349  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002834e  mov     rcx, [rbp+var_30]
0x180028352  test    rcx, rcx
0x180028355  jz      short loc_180028363
0x180028357  mov     rax, [rcx]
0x18002835a  mov     rax, [rax+10h]
0x18002835e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028363  mov     rcx, [rbp+var_40]
0x180028367  test    rcx, rcx
0x18002836a  jz      loc_180028502
0x180028370  mov     rax, [rcx]
0x180028373  mov     rax, [rax+10h]
0x180028377  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002837c  jmp     loc_180028502
0x180028381  mov     rdi, [rbp+var_38]
0x180028385  lea     rcx, [rbp+pvarg]; pvarg
0x180028389  mov     rax, [rdi]
0x18002838c  mov     rbx, [rax+18h]
0x180028390  call    cs:__imp_VariantClear
0x180028397  nop     dword ptr [rax+rax+00h]
0x18002839c  lea     rcx, [rbp+pvarg]; pvarg
0x1800283a0  call    cs:__imp_VariantInit
0x1800283a7  nop     dword ptr [rax+rax+00h]
0x1800283ac  xor     r9d, r9d
0x1800283af  lea     r8, [rbp+pvarg]
0x1800283b3  mov     rcx, rdi
0x1800283b6  mov     rax, rbx
0x1800283b9  lea     edx, [r9+1]
0x1800283bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800283c2  test    eax, eax
0x1800283c4  jnz     loc_1800284AA
0x1800283ca  mov     rcx, [rbp+arg_18]
0x1800283ce  mov     [rbp+arg_18], r12
0x1800283d2  test    rcx, rcx
0x1800283d5  jz      short loc_1800283E3
0x1800283d7  mov     rax, [rcx]
0x1800283da  mov     rax, [rax+10h]
0x1800283de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800283e3  mov     rcx, qword ptr [rbp+pvarg+8]
0x1800283e7  lea     r8, [rbp+arg_18]
0x1800283eb  lea     rdx, _GUID_a295019c_dc65_47dd_90dc_7fe918a1ab44
0x1800283f2  mov     rax, [rcx]
0x1800283f5  mov     rax, [rax]
0x1800283f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800283fd  mov     ebx, eax
0x1800283ff  test    eax, eax
0x180028401  js      loc_180028520
0x180028407  mov     rdi, [rbp+arg_18]
0x18002840b  mov     rbx, [rbp+bstrString]
0x18002840f  mov     rax, [rdi]
0x180028412  mov     rsi, [rax+48h]
0x180028416  test    rbx, rbx
0x180028419  jz      short loc_18002843C
0x18002841b  lea     rcx, [rbp+var_28]; this
0x18002841f  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180028424  mov     rcx, rbx; bstrString
0x180028427  call    cs:__imp_SysFreeString
0x18002842e  nop     dword ptr [rax+rax+00h]
0x180028433  lea     rcx, [rbp+var_28]; this
0x180028437  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002843c  lea     rdx, [rbp+bstrString]
0x180028440  mov     [rbp+bstrString], r12
0x180028444  mov     rcx, rdi
0x180028447  mov     rax, rsi
0x18002844a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002844f  mov     esi, eax
0x180028451  mov     ecx, 100000h
0x180028456  test    eax, eax
0x180028458  js      loc_180028514
0x18002845e  mov     r8, [rbp+bstrString]
0x180028462  lea     rdx, aServiceEnumera; "Service enumeration found UPnP service "...
0x180028469  call    EventWrite0
0x18002846e  mov     rcx, [rbp+bstrString]; Str
0x180028472  mov     rdx, r15; SubStr
0x180028475  call    cs:__imp_wcsstr
0x18002847c  nop     dword ptr [rax+rax+00h]
0x180028481  test    rax, rax
0x180028484  jz      loc_180028381
0x18002848a  mov     r8, [rbp+bstrString]
0x18002848e  lea     rdx, aUsingEnumerate; "Using enumerated service %ws"
0x180028495  mov     ecx, 100000h
0x18002849a  call    EventWrite0
0x18002849f  mov     rax, [rbp+arg_18]
0x1800284a3  mov     [r14], rax
0x1800284a6  mov     [rbp+arg_18], r12
0x1800284aa  cmp     [r14], r12
0x1800284ad  jnz     short loc_1800284C5
0x1800284af  lea     rdx, aServiceEnumera_0; "Service enumeration found no matching s"...
0x1800284b6  mov     ecx, 100000h
0x1800284bb  call    EventWriteError0
0x1800284c0  mov     esi, 80070490h
0x1800284c5  lea     rcx, [rbp+bstrString]
0x1800284c9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800284ce  lea     rcx, [rbp+pvarg]; pvarg
0x1800284d2  call    cs:__imp_VariantClear
0x1800284d9  nop     dword ptr [rax+rax+00h]
0x1800284de  lea     rcx, [rbp+arg_18]
0x1800284e2  call    ??1?$com_ptr_t@UIUPnPServices@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUPnPServices,wil::err_returncode_policy>::~com_ptr_t<IUPnPServices,wil::err_returncode_policy>(void)
0x1800284e7  lea     rcx, [rbp+var_38]
0x1800284eb  call    ??1?$com_ptr_t@UIUPnPServices@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUPnPServices,wil::err_returncode_policy>::~com_ptr_t<IUPnPServices,wil::err_returncode_policy>(void)
0x1800284f0  lea     rcx, [rbp+var_30]
0x1800284f4  call    ??1?$com_ptr_t@UIUPnPServices@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUPnPServices,wil::err_returncode_policy>::~com_ptr_t<IUPnPServices,wil::err_returncode_policy>(void)
0x1800284f9  lea     rcx, [rbp+var_40]
0x1800284fd  call    ??1?$com_ptr_t@UIUPnPServices@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUPnPServices,wil::err_returncode_policy>::~com_ptr_t<IUPnPServices,wil::err_returncode_policy>(void)
0x180028502  mov     eax, esi
0x180028504  add     rsp, 70h
0x180028508  pop     r15
0x18002850a  pop     r14
0x18002850c  pop     r12
0x18002850e  pop     rdi
0x18002850f  pop     rsi
0x180028510  pop     rbx
0x180028511  pop     rbp
0x180028512  retn
0x180028514  lea     rdx, aGetServicetype; "get_ServiceTypeIdentifier returned 0x%x"
0x18002851b  jmp     loc_1800282A1
0x180028520  lea     rdx, aQueryinterface; "QueryInterface<IUPnPService> returned 0"...
0x180028527  jmp     loc_180028188
```
