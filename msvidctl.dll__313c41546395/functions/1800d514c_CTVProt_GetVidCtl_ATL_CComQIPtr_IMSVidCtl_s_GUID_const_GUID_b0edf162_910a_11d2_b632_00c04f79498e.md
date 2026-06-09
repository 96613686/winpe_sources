# CTVProt::GetVidCtl(ATL::CComQIPtr<IMSVidCtl,&__s_GUID const _GUID_b0edf162_910a_11d2_b632_00c04f79498e> &)

- ea: `0x1800d514c`
- end: `0x1800d54c5`
- name: `?GetVidCtl@CTVProt@@QEAAJAEAV?$CComQIPtr@UIMSVidCtl@@$1?_GUID_b0edf162_910a_11d2_b632_00c04f79498e@@3U__s_GUID@@B@ATL@@@Z`
- size: `889`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800d5870`

## callees

- `0x180004640`
- `0x180004b54`
- `0x180006b38`
- `0x18000ff74`
- `0x18001414c`
- `0x18001a0f8`
- `0x180030cb4`
- `0x18007c4c0`
- `0x18007c698`
- `0x18008061c`
- `0x1800c362c`
- `0x1800d4e08`
- `0x1800d4f94`
- `0x1800d514c`
- `0x1800eee0c`
- `0x1800f8010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1800d51be`
- `ole32!CoCreateInstance` at `0x1800d51be`
- `OLEAUT32!__imp_SysAllocString` at `0x1800d51f4`
- `OLEAUT32!__imp_SysAllocString` at `0x1800d51f4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d5208`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d5242`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d5208`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d5242`
- `OLEAUT32!__imp_VariantClear` at `0x1800d5277`
- `OLEAUT32!__imp_VariantClear` at `0x1800d52bb`
- `OLEAUT32!__imp_VariantClear` at `0x1800d5361`
- `OLEAUT32!__imp_VariantClear` at `0x1800d5475`
- `OLEAUT32!__imp_VariantClear` at `0x1800d5277`
- `OLEAUT32!__imp_VariantClear` at `0x1800d52bb`
- `OLEAUT32!__imp_VariantClear` at `0x1800d5361`
- `OLEAUT32!__imp_VariantClear` at `0x1800d5475`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CTVProt::GetVidCtl(__int64 a1, LPVOID *a2)
{
  HRESULT CachedVidCtl; // ebx
  BSTR v4; // rax
  OLECHAR *v5; // rbx
  __int64 v6; // rbx
  __int64 v7; // rax
  __int64 v8; // r8
  __int64 v9; // r14
  __int64 v10; // r15
  _QWORD *i; // rbx
  int v12; // eax
  BSTR v14; // [rsp+30h] [rbp-49h] BYREF
  __int64 v15; // [rsp+38h] [rbp-41h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-39h] BYREF
  __int64 v17; // [rsp+58h] [rbp-21h] BYREF
  void *v18; // [rsp+60h] [rbp-19h] BYREF
  _BYTE v19[24]; // [rsp+68h] [rbp-11h] BYREF
  GUID Buf1; // [rsp+80h] [rbp+7h] BYREF
  __int64 v21; // [rsp+90h] [rbp+17h]

  LODWORD(v14) = 0;
  v17 = 0;
  CachedVidCtl = CTVProt::GetCachedVidCtl(a1, a2, &v17);
  if ( CachedVidCtl < 0 )
    goto LABEL_41;
  if ( *a2 )
    goto LABEL_38;
  CachedVidCtl = CoCreateInstance(&CLSID_MSVidCtl, 0, 1u, &GUID_b0edf162_910a_11d2_b632_00c04f79498e, a2);
  if ( CachedVidCtl < 0 )
    goto LABEL_41;
  if ( v17 )
  {
    Buf1 = 0;
    LOWORD(Buf1.Data1) = 13;
    *(_QWORD *)Buf1.Data4 = *a2;
    v4 = SysAllocString(L"B0EDF163-910A-11D2-B632-00C04F79498E");
    v5 = v4;
    v14 = v4;
    if ( !v4 )
    {
      SysFreeString(0);
      CachedVidCtl = -2147418113;
      goto LABEL_41;
    }
    v21 = 0;
    (*(void (__fastcall **)(__int64, BSTR, GUID *))(*(_QWORD *)v17 + 272LL))(v17, v4, &Buf1);
    SysFreeString(v5);
  }
  CFactoryHelper::GetDefaultTR(&pvarg);
  if ( (unsigned __int8)ATL::CComVariant::operator!(&pvarg) )
  {
    if ( pvarg.vt == 4095 )
      pvarg.vt = 8;
    VariantClear(&pvarg);
    CachedVidCtl = -2147024809;
    goto LABEL_41;
  }
  CachedVidCtl = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *))(*(_QWORD *)*a2 + 328LL))(*a2, &pvarg);
  if ( CachedVidCtl < 0 )
  {
LABEL_13:
    if ( pvarg.vt != 4095 )
    {
LABEL_15:
      VariantClear(&pvarg);
      goto LABEL_41;
    }
LABEL_14:
    pvarg.vt = 8;
    goto LABEL_15;
  }
  v15 = 0;
  CachedVidCtl = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)*a2 + 232LL))(*a2, &v15);
  if ( CachedVidCtl < 0 )
  {
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v15);
    goto LABEL_13;
  }
  if ( v15 )
    v6 = v15 - 24;
  else
    v6 = 0;
  v18 = operator new(0x48u);
  v7 = std::vector<DSPin>::vector<DSPin>(v19);
  LODWORD(v14) = 1;
  v9 = CTypedDevices<IMSVidFeatures,IMSVidFeature,&_GUID const CLSID_MSVidFeatures,&unsigned short const near * const STR_FEATURES_PROGID,252>::CTypedDevices<IMSVidFeatures,IMSVidFeature,&_GUID const CLSID_MSVidFeatures,&unsigned short const near * const STR_FEATURES_PROGID,252>(
         v8,
         v7);
  std::vector<ATL::CComQIPtr<IComponent,&__s_GUID const _GUID_1a5576fc_0e19_11d3_9d8e_00c04f72d980>>::_Tidy(v19);
  if ( v9 )
  {
    v10 = v6 + 48;
    std::_Tree<std::_Tmap_traits<ATL::CComBSTR,unsigned long,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,unsigned long>>,0>>::end(
      v6 + 48,
      &v14);
    for ( i = v14; i != *(_QWORD **)std::vector<ATL::CComBSTR>::end(v10, &v18); ++i )
    {
      ATL::CComQIPtr<IMSVidFeature,&__s_GUID const _GUID_37b03547_a4c8_11d2_b634_00c04f79498e>::CComQIPtr<IMSVidFeature,&__s_GUID const _GUID_37b03547_a4c8_11d2_b634_00c04f79498e>(
        &v14,
        *i);
      Buf1 = GUID_NULL;
      if ( (*(int (__fastcall **)(BSTR, GUID *))(*(_QWORD *)v14 + 112LL))(v14, &Buf1) >= 0
        && (!memcmp_0(&Buf1, &CLSID_MSVidClosedCaptioning, 0x10u) || !memcmp_0(&Buf1, &CLSID_MSVidDataServices, 0x10u)) )
      {
        std::vector<ATL::CComQIPtr<IMSVidDevice,&__s_GUID const _GUID_1c15d47c_911d_11d2_b632_00c04f79498e>>::push_back(
          v9 + 48,
          i);
      }
      ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v14);
    }
    CachedVidCtl = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)*a2 + 312LL))(*a2, v9 + 24);
    if ( CachedVidCtl < 0 )
    {
      ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v15);
      if ( pvarg.vt != 4095 )
        goto LABEL_15;
      goto LABEL_14;
    }
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v15);
    if ( pvarg.vt == 4095 )
      pvarg.vt = 8;
    VariantClear(&pvarg);
LABEL_38:
    v12 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)*a2 + 352LL))(*a2);
    if ( v12 >= 0 )
      CachedVidCtl = 0;
    else
      CachedVidCtl = v12;
    goto LABEL_41;
  }
  ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v15);
  if ( pvarg.vt == 4095 )
    pvarg.vt = 8;
  VariantClear(&pvarg);
  CachedVidCtl = -2147024882;
LABEL_41:
  ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v17);
  return (unsigned int)CachedVidCtl;
}

```

## disassembly

```asm
0x1800d514c  mov     [rsp-8+arg_10], rbx
0x1800d5151  push    rbp
0x1800d5152  push    rsi
0x1800d5153  push    rdi
0x1800d5154  push    r14
0x1800d5156  push    r15
0x1800d5158  lea     rbp, [rsp-37h]
0x1800d515d  sub     rsp, 0B0h
0x1800d5164  mov     rax, cs:__security_cookie
0x1800d516b  xor     rax, rsp
0x1800d516e  mov     [rbp+57h+var_30], rax
0x1800d5172  mov     rsi, rdx
0x1800d5175  mov     dword ptr [rbp+57h+var_A0], 0
0x1800d517c  mov     [rbp+57h+var_78], 0
0x1800d5184  lea     r8, [rbp+57h+var_78]
0x1800d5188  call    ?GetCachedVidCtl@CTVProt@@QEAAJAEAV?$CComQIPtr@UIMSVidCtl@@$1?_GUID_b0edf162_910a_11d2_b632_00c04f79498e@@3U__s_GUID@@B@ATL@@AEAV?$CComQIPtr@UIWebBrowser2@@$1?_GUID_d30c1661_cdaf_11d0_8a3e_00c04fc9e26e@@3U__s_GUID@@B@3@@Z; CTVProt::GetCachedVidCtl(ATL::CComQIPtr<IMSVidCtl,&__s_GUID const _GUID_b0edf162_910a_11d2_b632_00c04f79498e> &,ATL::CComQIPtr<IWebBrowser2,&__s_GUID const _GUID_d30c1661_cdaf_11d0_8a3e_00c04fc9e26e> &)
0x1800d518d  mov     ebx, eax
0x1800d518f  test    eax, eax
0x1800d5191  js      loc_1800D5497
0x1800d5197  cmp     qword ptr [rsi], 0
0x1800d519b  jnz     loc_1800D547B
0x1800d51a1  mov     [rsp+0D0h+ppv], rsi; ppv
0x1800d51a6  lea     r9, _GUID_b0edf162_910a_11d2_b632_00c04f79498e; riid
0x1800d51ad  mov     edi, 1
0x1800d51b2  mov     r8d, edi; dwClsContext
0x1800d51b5  xor     edx, edx; pUnkOuter
0x1800d51b7  lea     rcx, CLSID_MSVidCtl; rclsid
0x1800d51be  call    cs:__imp_CoCreateInstance
0x1800d51c4  mov     ebx, eax
0x1800d51c6  test    eax, eax
0x1800d51c8  js      loc_1800D5497
0x1800d51ce  cmp     [rbp+57h+var_78], 0
0x1800d51d3  jz      short loc_1800D5248
0x1800d51d5  xorps   xmm0, xmm0
0x1800d51d8  xor     r14d, r14d
0x1800d51db  movups  [rbp+57h+Buf1], xmm0
0x1800d51df  lea     eax, [rdi+0Ch]
0x1800d51e2  mov     word ptr [rbp+57h+Buf1], ax
0x1800d51e6  mov     rax, [rsi]
0x1800d51e9  mov     qword ptr [rbp+57h+Buf1+8], rax
0x1800d51ed  lea     rcx, aB0edf163910a11; "B0EDF163-910A-11D2-B632-00C04F79498E"
0x1800d51f4  call    cs:__imp_SysAllocString
0x1800d51fa  mov     rbx, rax
0x1800d51fd  mov     [rbp+57h+var_A0], rax
0x1800d5201  test    rax, rax
0x1800d5204  jnz     short loc_1800D5218
0x1800d5206  xor     ecx, ecx; bstrString
0x1800d5208  call    cs:__imp_SysFreeString
0x1800d520e  mov     ebx, 8000FFFFh
0x1800d5213  jmp     loc_1800D5497
0x1800d5218  mov     rcx, [rbp+57h+var_78]
0x1800d521c  movups  xmm0, [rbp+57h+Buf1]
0x1800d5220  movaps  [rbp+57h+Buf1], xmm0
0x1800d5224  mov     [rbp+57h+var_40], r14
0x1800d5228  mov     rax, [rcx]
0x1800d522b  lea     r8, [rbp+57h+Buf1]
0x1800d522f  mov     rdx, rbx
0x1800d5232  mov     rax, [rax+110h]
0x1800d5239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d523e  nop
0x1800d523f  mov     rcx, rbx; bstrString
0x1800d5242  call    cs:__imp_SysFreeString
0x1800d5248  lea     rcx, [rbp+57h+pvarg]
0x1800d524c  call    ?GetDefaultTR@CFactoryHelper@@SA?AVCComVariant@ATL@@XZ; CFactoryHelper::GetDefaultTR(void)
0x1800d5251  nop
0x1800d5252  lea     rcx, [rbp+57h+pvarg]
0x1800d5256  call    ??7CComVariant@ATL@@QEBA_NXZ; ATL::CComVariant::operator!(void)
0x1800d525b  test    al, al
0x1800d525d  jz      short loc_1800D5287
0x1800d525f  mov     eax, 0FFFh
0x1800d5264  cmp     word ptr [rbp+57h+pvarg], ax
0x1800d5268  jnz     short loc_1800D5273
0x1800d526a  mov     edi, 8
0x1800d526f  mov     word ptr [rbp+57h+pvarg], di
0x1800d5273  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800d5277  call    cs:__imp_VariantClear
0x1800d527d  mov     ebx, 80070057h
0x1800d5282  jmp     loc_1800D5497
0x1800d5287  mov     rcx, [rsi]
0x1800d528a  mov     rax, [rcx]
0x1800d528d  lea     rdx, [rbp+57h+pvarg]
0x1800d5291  mov     rax, [rax+148h]
0x1800d5298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d529d  mov     ebx, eax
0x1800d529f  test    eax, eax
0x1800d52a1  jns     short loc_1800D52C6
0x1800d52a3  mov     eax, 0FFFh
0x1800d52a8  cmp     word ptr [rbp+57h+pvarg], ax
0x1800d52ac  jnz     short loc_1800D52B7
0x1800d52ae  mov     edi, 8
0x1800d52b3  mov     word ptr [rbp+57h+pvarg], di
0x1800d52b7  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800d52bb  call    cs:__imp_VariantClear
0x1800d52c1  jmp     loc_1800D5497
0x1800d52c6  mov     [rbp+57h+var_98], 0
0x1800d52ce  mov     rcx, [rsi]
0x1800d52d1  mov     rax, [rcx]
0x1800d52d4  lea     rdx, [rbp+57h+var_98]
0x1800d52d8  mov     rax, [rax+0E8h]
0x1800d52df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d52e4  mov     ebx, eax
0x1800d52e6  test    eax, eax
0x1800d52e8  jns     short loc_1800D52F5
0x1800d52ea  lea     rcx, [rbp+57h+var_98]
0x1800d52ee  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800d52f3  jmp     short loc_1800D52A3
0x1800d52f5  mov     rax, [rbp+57h+var_98]
0x1800d52f9  test    rax, rax
0x1800d52fc  jz      short loc_1800D5304
0x1800d52fe  lea     rbx, [rax-18h]
0x1800d5302  jmp     short loc_1800D5306
0x1800d5304  xor     ebx, ebx
0x1800d5306  mov     ecx, 48h ; 'H'; Size
0x1800d530b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d5310  mov     r8, rax
0x1800d5313  mov     [rbp+57h+var_70], rax
0x1800d5317  lea     rcx, [rbp+57h+var_68]
0x1800d531b  call    ??0?$vector@VDSPin@@V?$allocator@VDSPin@@@std@@@std@@QEAA@XZ; std::vector<DSPin>::vector<DSPin>(void)
0x1800d5320  nop
0x1800d5321  mov     dword ptr [rbp+57h+var_A0], edi
0x1800d5324  mov     rdx, rax
0x1800d5327  mov     rcx, r8
0x1800d532a  call    ??0?$CTypedDevices@UIMSVidFeatures@@UIMSVidFeature@@$1?CLSID_MSVidFeatures@@3U_GUID@@B$1?STR_FEATURES_PROGID@@3QBGB$0PM@@@QEAA@AEBV?$vector@V?$CComQIPtr@UIMSVidDevice@@$1?_GUID_1c15d47c_911d_11d2_b632_00c04f79498e@@3U__s_GUID@@B@ATL@@V?$allocator@V?$CComQIPtr@UIMSVidDevice@@$1?_GUID_1c15d47c_911d_11d2_b632_00c04f79498e@@3U__s_GUID@@B@ATL@@@std@@@std@@_N1@Z; CTypedDevices<IMSVidFeatures,IMSVidFeature,&_GUID const CLSID_MSVidFeatures,&ushort const near * const STR_FEATURES_PROGID,252>::CTypedDevices<IMSVidFeatures,IMSVidFeature,&_GUID const CLSID_MSVidFeatures,&ushort const near * const STR_FEATURES_PROGID,252>(std::vector<ATL::CComQIPtr<IMSVidDevice,&__s_GUID const _GUID_1c15d47c_911d_11d2_b632_00c04f79498e>> const &,bool,bool)
0x1800d532f  mov     r14, rax
0x1800d5332  lea     rcx, [rbp+57h+var_68]
0x1800d5336  call    ?_Tidy@?$vector@V?$CComQIPtr@UIComponent@@$1?_GUID_1a5576fc_0e19_11d3_9d8e_00c04f72d980@@3U__s_GUID@@B@ATL@@V?$allocator@V?$CComQIPtr@UIComponent@@$1?_GUID_1a5576fc_0e19_11d3_9d8e_00c04f72d980@@3U__s_GUID@@B@ATL@@@std@@@std@@AEAAXXZ; std::vector<ATL::CComQIPtr<IComponent,&__s_GUID const _GUID_1a5576fc_0e19_11d3_9d8e_00c04f72d980>>::_Tidy(void)
0x1800d533b  test    r14, r14
0x1800d533e  jnz     short loc_1800D5371
0x1800d5340  lea     rcx, [rbp+57h+var_98]
0x1800d5344  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800d5349  nop
0x1800d534a  mov     eax, 0FFFh
0x1800d534f  cmp     word ptr [rbp+57h+pvarg], ax
0x1800d5353  jnz     short loc_1800D535D
0x1800d5355  lea     edi, [r14+8]
0x1800d5359  mov     word ptr [rbp+57h+pvarg], di
0x1800d535d  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800d5361  call    cs:__imp_VariantClear
0x1800d5367  mov     ebx, 8007000Eh
0x1800d536c  jmp     loc_1800D5497
0x1800d5371  lea     r15, [rbx+30h]
0x1800d5375  lea     rdx, [rbp+57h+var_A0]
0x1800d5379  mov     rcx, r15
0x1800d537c  call    ?end@?$_Tree@V?$_Tmap_traits@VCComBSTR@ATL@@KU?$less@VCComBSTR@ATL@@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@K@std@@@4@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVCComBSTR@ATL@@K@std@@@std@@@std@@@2@XZ; std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ulong,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ulong>>,0>>::end(void)
0x1800d5381  mov     edi, 8
0x1800d5386  mov     rbx, [rbp+57h+var_A0]
0x1800d538a  lea     rdx, [rbp+57h+var_70]
0x1800d538e  mov     rcx, r15
0x1800d5391  call    ?end@?$vector@VCComBSTR@ATL@@V?$allocator@VCComBSTR@ATL@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VCComBSTR@ATL@@@std@@@std@@@2@XZ; std::vector<ATL::CComBSTR>::end(void)
0x1800d5396  cmp     rbx, [rax]
0x1800d5399  jz      loc_1800D5422
0x1800d539f  mov     rdx, [rbx]
0x1800d53a2  lea     rcx, [rbp+57h+var_A0]
0x1800d53a6  call    ??0?$CComQIPtr@UIMSVidFeature@@$1?_GUID_37b03547_a4c8_11d2_b634_00c04f79498e@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IMSVidFeature,&__s_GUID const _GUID_37b03547_a4c8_11d2_b634_00c04f79498e>::CComQIPtr<IMSVidFeature,&__s_GUID const _GUID_37b03547_a4c8_11d2_b634_00c04f79498e>(IUnknown *)
0x1800d53ab  nop
0x1800d53ac  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800d53b3  movdqu  [rbp+57h+Buf1], xmm0
0x1800d53b8  mov     rcx, [rbp+57h+var_A0]
0x1800d53bc  mov     rax, [rcx]
0x1800d53bf  lea     rdx, [rbp+57h+Buf1]
0x1800d53c3  mov     rax, [rax+70h]
0x1800d53c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d53cc  test    eax, eax
0x1800d53ce  js      short loc_1800D5411
0x1800d53d0  mov     r8d, 10h; Size
0x1800d53d6  lea     rdx, CLSID_MSVidClosedCaptioning; Buf2
0x1800d53dd  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1800d53e1  call    memcmp_0
0x1800d53e6  test    eax, eax
0x1800d53e8  jz      short loc_1800D5404
0x1800d53ea  mov     r8d, 10h; Size
0x1800d53f0  lea     rdx, CLSID_MSVidDataServices; Buf2
0x1800d53f7  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1800d53fb  call    memcmp_0
0x1800d5400  test    eax, eax
0x1800d5402  jnz     short loc_1800D5411
0x1800d5404  lea     rcx, [r14+30h]
0x1800d5408  mov     rdx, rbx
0x1800d540b  call    ?push_back@?$vector@V?$CComQIPtr@UIMSVidDevice@@$1?_GUID_1c15d47c_911d_11d2_b632_00c04f79498e@@3U__s_GUID@@B@ATL@@V?$allocator@V?$CComQIPtr@UIMSVidDevice@@$1?_GUID_1c15d47c_911d_11d2_b632_00c04f79498e@@3U__s_GUID@@B@ATL@@@std@@@std@@QEAAXAEBV?$CComQIPtr@UIMSVidDevice@@$1?_GUID_1c15d47c_911d_11d2_b632_00c04f79498e@@3U__s_GUID@@B@ATL@@@Z; std::vector<ATL::CComQIPtr<IMSVidDevice,&__s_GUID const _GUID_1c15d47c_911d_11d2_b632_00c04f79498e>>::push_back(ATL::CComQIPtr<IMSVidDevice,&__s_GUID const _GUID_1c15d47c_911d_11d2_b632_00c04f79498e> const &)
0x1800d5410  nop
0x1800d5411  lea     rcx, [rbp+57h+var_A0]
0x1800d5415  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800d541a  add     rbx, rdi
0x1800d541d  jmp     loc_1800D538A
0x1800d5422  mov     rcx, [rsi]
0x1800d5425  mov     rax, [rcx]
0x1800d5428  lea     rdx, [r14+18h]
0x1800d542c  mov     rax, [rax+138h]
0x1800d5433  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d5438  mov     ebx, eax
0x1800d543a  lea     rcx, [rbp+57h+var_98]
0x1800d543e  test    eax, eax
0x1800d5440  jns     short loc_1800D545C
0x1800d5442  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800d5447  nop
0x1800d5448  mov     eax, 0FFFh
0x1800d544d  cmp     word ptr [rbp+57h+pvarg], ax
0x1800d5451  jnz     loc_1800D52B7
0x1800d5457  jmp     loc_1800D52B3
0x1800d545c  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800d5461  nop
0x1800d5462  mov     eax, 0FFFh
0x1800d5467  cmp     word ptr [rbp+57h+pvarg], ax
0x1800d546b  jnz     short loc_1800D5471
0x1800d546d  mov     word ptr [rbp+57h+pvarg], di
0x1800d5471  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800d5475  call    cs:__imp_VariantClear
0x1800d547b  mov     rcx, [rsi]
0x1800d547e  mov     rax, [rcx]
0x1800d5481  mov     rax, [rax+160h]
0x1800d5488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d548d  test    eax, eax
0x1800d548f  jns     short loc_1800D5495
0x1800d5491  mov     ebx, eax
0x1800d5493  jmp     short loc_1800D5497
0x1800d5495  xor     ebx, ebx
0x1800d5497  lea     rcx, [rbp+57h+var_78]
0x1800d549b  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800d54a0  mov     eax, ebx
0x1800d54a2  mov     rcx, [rbp+57h+var_30]
0x1800d54a6  xor     rcx, rsp; StackCookie
0x1800d54a9  call    __security_check_cookie
0x1800d54ae  mov     rbx, [rsp+0D0h+arg_10]
0x1800d54b6  add     rsp, 0B0h
0x1800d54bd  pop     r15
0x1800d54bf  pop     r14
0x1800d54c1  pop     rdi
0x1800d54c2  pop     rsi
0x1800d54c3  pop     rbp
0x1800d54c4  retn
```
