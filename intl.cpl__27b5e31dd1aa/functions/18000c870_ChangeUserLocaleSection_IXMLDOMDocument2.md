# ChangeUserLocaleSection(IXMLDOMDocument2 *)

- ea: `0x18000c870`
- end: `0x18000ce91`
- name: `?ChangeUserLocaleSection@@YAJPEAUIXMLDOMDocument2@@@Z`
- size: `1569`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, installer_update`

## callers

- `0x18000dce0`

## callees

- `0x18000aa10`
- `0x18000aa9c`
- `0x18000accc`
- `0x18000ad4c`
- `0x18000b000`
- `0x18000c1e8`
- `0x18000c454`
- `0x18000c870`
- `0x18000ce98`
- `0x18000cf94`
- `0x18000d4a0`
- `0x18000da60`
- `0x18000f344`
- `0x18000f464`
- `0x18002a150`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18000cdc2`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18000cdc2`
- `api-ms-win-core-localization-l1-2-0!SetLocaleInfoW` at `0x18000cd9c`
- `api-ms-win-core-localization-l1-2-0!SetLocaleInfoW` at `0x18000cd9c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cc94`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ccaa`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ce5f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ce6d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cc94`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ccaa`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ce5f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ce6d`
- `OLEAUT32!__imp_VariantInit` at `0x18000c8df`
- `OLEAUT32!__imp_VariantInit` at `0x18000c8df`
- `OLEAUT32!__imp_VariantClear` at `0x18000ce03`
- `OLEAUT32!__imp_VariantClear` at `0x18000ce03`
- `KERNEL32!NlsUpdateLocale` at `0x18000cdd5`
- `KERNEL32!NlsUpdateLocale` at `0x18000cdd5`
- `USER32!SendNotifyMessageW` at `0x18000cdf9`
- `USER32!SendNotifyMessageW` at `0x18000cdf9`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall ChangeUserLocaleSection(struct IXMLDOMDocument2 *a1)
{
  OLECHAR *v2; // rdi
  int v3; // ebx
  HRESULT (__stdcall *selectSingleNode)(IXMLDOMDocument2 *, BSTR, IXMLDOMNode **); // r14
  _bstr_t *v5; // rbx
  _bstr_t *v6; // rax
  __int64 **v7; // rax
  __int64 v8; // rdx
  HRESULT (__stdcall *v9)(IXMLDOMNode *, BSTR, IXMLDOMNode **); // r14
  _bstr_t *v10; // rbx
  _bstr_t *v11; // rax
  __int64 **v12; // rax
  __int64 v13; // rdx
  int v14; // eax
  HRESULT (__stdcall *v15)(IXMLDOMDocument2 *, BSTR, IXMLDOMNode **); // r14
  _bstr_t *v16; // rbx
  _bstr_t *v17; // rax
  __int64 **v18; // rax
  __int64 v19; // rdx
  HRESULT (__stdcall *v20)(IXMLDOMNode *, BSTR, IXMLDOMNode **); // rsi
  _bstr_t *v21; // rbx
  _bstr_t *v22; // rax
  __int64 **v23; // rax
  __int64 v24; // rdx
  bool v25; // si
  int v26; // eax
  int v27; // eax
  int i; // r14d
  LCTYPE v29; // eax
  __int16 v31; // [rsp+20h] [rbp-E0h] BYREF
  int v32; // [rsp+28h] [rbp-D8h] BYREF
  struct IXMLDOMNode *v33; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v34[8]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v35[8]; // [rsp+40h] [rbp-C0h] BYREF
  struct IXMLDOMNode *v36; // [rsp+48h] [rbp-B8h] BYREF
  int v37; // [rsp+50h] [rbp-B0h] BYREF
  struct IXMLDOMNode *v38; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v39; // [rsp+60h] [rbp-A0h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp-98h] BYREF
  LPCWSTR lpLCData; // [rsp+70h] [rbp-90h] BYREF
  struct IXMLDOMNode *v42; // [rsp+78h] [rbp-88h] BYREF
  struct IXMLDOMNode *v43; // [rsp+80h] [rbp-80h] BYREF
  VARIANTARG pvarg; // [rsp+88h] [rbp-78h] BYREF
  WCHAR LCData[88]; // [rsp+A0h] [rbp-60h] BYREF

  v37 = 0;
  v42 = 0;
  v38 = 0;
  v33 = 0;
  v36 = 0;
  v43 = 0;
  v39 = 0;
  bstrString = 0;
  v2 = 0;
  lpLCData = 0;
  v31 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  if ( !a1 )
  {
    v3 = -2147024809;
    goto LABEL_58;
  }
  selectSingleNode = a1->lpVtbl->selectSingleNode;
  v5 = _bstr_t::_bstr_t((_bstr_t *)v35, "//");
  v6 = _bstr_t::_bstr_t((_bstr_t *)v34, L"gs:UserLocale");
  v7 = (__int64 **)_bstr_t::operator+(v5, &v32, v6);
  if ( *v7 )
    v8 = **v7;
  else
    v8 = 0;
  v3 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, __int64, struct IXMLDOMNode **))selectSingleNode)(
         a1,
         v8,
         &v42);
  _bstr_t::_Free((_bstr_t *)&v32);
  _bstr_t::_Free((_bstr_t *)v34);
  _bstr_t::_Free((_bstr_t *)v35);
  if ( v3 == 1 )
    goto LABEL_7;
  if ( (unsigned int)CheckHR(v3) )
  {
    v9 = v42->lpVtbl->selectSingleNode;
    v10 = _bstr_t::_bstr_t((_bstr_t *)&v32, "//");
    v11 = _bstr_t::_bstr_t((_bstr_t *)v34, L"gs:Locale");
    v12 = (__int64 **)_bstr_t::operator+(v10, v35, v11);
    if ( *v12 )
      v13 = **v12;
    else
      v13 = 0;
    v3 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64, struct IXMLDOMNode **))v9)(v42, v13, &v38);
    _bstr_t::_Free((_bstr_t *)v35);
    _bstr_t::_Free((_bstr_t *)v34);
    _bstr_t::_Free((_bstr_t *)&v32);
    if ( v3 == 1 )
      goto LABEL_7;
    if ( !(unsigned int)CheckHR(v3) )
      goto LABEL_58;
    v14 = ChangeUserLocale(v38);
    v3 = v14;
    if ( v14 < 0 || v14 == 1 )
      goto LABEL_58;
    v15 = a1->lpVtbl->selectSingleNode;
    v16 = _bstr_t::_bstr_t((_bstr_t *)&v32, "//");
    v17 = _bstr_t::_bstr_t((_bstr_t *)v34, L"gs:Win32");
    v18 = (__int64 **)_bstr_t::operator+(v16, v35, v17);
    if ( *v18 )
      v19 = **v18;
    else
      v19 = 0;
    v3 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, __int64, struct IXMLDOMNode **))v15)(a1, v19, &v33);
    _bstr_t::_Free((_bstr_t *)v35);
    _bstr_t::_Free((_bstr_t *)v34);
    _bstr_t::_Free((_bstr_t *)&v32);
    if ( v3 == 1 )
    {
      v20 = v38->lpVtbl->selectSingleNode;
      v21 = _bstr_t::_bstr_t((_bstr_t *)&v32, "//");
      v22 = _bstr_t::_bstr_t((_bstr_t *)v34, L"gs:Framework");
      v23 = (__int64 **)_bstr_t::operator+(v21, v35, v22);
      if ( *v23 )
        v24 = **v23;
      else
        v24 = 0;
      v3 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64, struct IXMLDOMNode **))v20)(v38, v24, &v33);
      _bstr_t::_Free((_bstr_t *)v35);
      _bstr_t::_Free((_bstr_t *)v34);
      _bstr_t::_Free((_bstr_t *)&v32);
      if ( v3 == 1 )
        goto LABEL_7;
      if ( !(unsigned int)CheckHR(v3) )
        goto LABEL_58;
      v25 = 0;
    }
    else
    {
      if ( !(unsigned int)CheckHR(v3) )
        goto LABEL_58;
      v25 = 1;
    }
    v26 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int16 *))v33->lpVtbl->hasChildNodes)(v33, &v31);
    v3 = v26;
    if ( v26 != 1 )
    {
      if ( !(unsigned int)CheckHR(v26) )
        goto LABEL_58;
      if ( !v31 )
        goto LABEL_58;
      v3 = ChangeAlternateSort(v33, v25);
      if ( v3 < 0 )
        goto LABEL_58;
      v3 = ChangeCalendar(v33, v25);
      if ( v3 < 0 )
        goto LABEL_58;
      v3 = ChangeTwoDigitYearMax(v33, v25);
      if ( v3 < 0 )
        goto LABEL_58;
      v27 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64 *))v33->lpVtbl->get_childNodes)(v33, &v39);
      v3 = v27;
      if ( v27 != 1 )
      {
        if ( (unsigned int)CheckHR(v27) )
        {
          v3 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v39 + 64LL))(v39, &v37);
          if ( (unsigned int)CheckHR(v3) )
          {
            for ( i = 0; i < v37; ++i )
            {
              ReleaseDomNode(&v36);
              if ( bstrString )
              {
                SysFreeString(bstrString);
                v2 = 0;
                lpLCData = 0;
              }
              if ( v2 )
              {
                SysFreeString(v2);
                v2 = 0;
                lpLCData = 0;
              }
              v3 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IXMLDOMNode **))(*(_QWORD *)v39 + 56LL))(
                     v39,
                     (unsigned int)i,
                     &v36);
              if ( !(unsigned int)CheckHR(v3) )
                goto LABEL_58;
              v32 = 0;
              v3 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, int *))v36->lpVtbl->get_nodeType)(v36, &v32);
              if ( !(unsigned int)CheckHR(v3) )
                goto LABEL_58;
              if ( v32 != 8 )
              {
                v3 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))v36->lpVtbl->get_nodeName)(v36, &bstrString);
                if ( !(unsigned int)CheckHR(v3) )
                  goto LABEL_58;
                v3 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, VARIANTARG *))v36->lpVtbl->get_nodeTypedValue)(
                       v36,
                       &pvarg);
                if ( !(unsigned int)CheckHR(v3) )
                  goto LABEL_58;
                GetValueFromVariant(&pvarg, (unsigned __int16 **)&lpLCData);
                if ( v25 )
                  v29 = Win32ToLctype(bstrString);
                else
                  v29 = FrameworkToLctype(bstrString);
                v2 = (OLECHAR *)lpLCData;
                SetLocaleInfoW(0x400u, v29, lpLCData);
              }
            }
            if ( i > 0 && GetLocaleInfoW(0x400u, 0x5Cu, LCData, 85) )
            {
              if ( (unsigned int)NlsUpdateLocale(LCData, 4) )
                v3 = 1;
              else
                SendNotifyMessageW(HWND_BROADCAST, 0x1Au, 0, (LPARAM)L"intl");
            }
          }
        }
        goto LABEL_58;
      }
    }
LABEL_7:
    v3 = 0;
  }
LABEL_58:
  VariantClear(&pvarg);
  ReleaseDomNode(&v42);
  ReleaseDomNode(&v38);
  ReleaseDomNode(&v33);
  ReleaseDomNode(&v36);
  ReleaseDomNode(&v43);
  if ( v39 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    v39 = 0;
  }
  if ( bstrString )
    SysFreeString(bstrString);
  if ( v2 )
    SysFreeString(v2);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000c870  push    rbp
0x18000c872  push    rbx
0x18000c873  push    rsi
0x18000c874  push    rdi
0x18000c875  push    r14
0x18000c877  push    r15
0x18000c879  lea     rbp, [rsp-68h]
0x18000c87e  sub     rsp, 168h
0x18000c885  mov     rax, cs:__security_cookie
0x18000c88c  xor     rax, rsp
0x18000c88f  mov     [rbp+90h+var_40], rax
0x18000c893  mov     rsi, rcx
0x18000c896  xor     r15d, r15d
0x18000c899  mov     [rsp+190h+var_140], r15d
0x18000c89e  mov     [rsp+190h+var_118], r15
0x18000c8a3  mov     [rsp+190h+var_138], r15
0x18000c8a8  mov     [rsp+190h+var_160], r15
0x18000c8ad  mov     [rsp+190h+var_148], r15
0x18000c8b2  mov     [rbp+90h+var_110], r15
0x18000c8b6  mov     [rsp+190h+var_130], r15
0x18000c8bb  mov     [rsp+190h+bstrString], r15
0x18000c8c0  mov     edi, r15d
0x18000c8c3  mov     [rsp+190h+lpLCData], r15
0x18000c8c8  mov     [rsp+190h+var_170], r15w
0x18000c8ce  xorps   xmm0, xmm0
0x18000c8d1  xor     eax, eax
0x18000c8d3  movups  xmmword ptr [rbp+90h+pvarg], xmm0
0x18000c8d7  mov     qword ptr [rbp+90h+pvarg+10h], rax
0x18000c8db  lea     rcx, [rbp+90h+pvarg]; pvarg
0x18000c8df  call    cs:__imp_VariantInit
0x18000c8e5  test    rsi, rsi
0x18000c8e8  jnz     short loc_18000C8F4
0x18000c8ea  mov     ebx, 80070057h
0x18000c8ef  jmp     loc_18000CDFF
0x18000c8f4  mov     rax, [rsi]
0x18000c8f7  mov     r14, [rax+128h]
0x18000c8fe  lea     rdx, asc_180030760; "//"
0x18000c905  lea     rcx, [rsp+190h+var_150]; this
0x18000c90a  call    ??0_bstr_t@@QEAA@PEBD@Z; _bstr_t::_bstr_t(char const *)
0x18000c90f  mov     rbx, rax
0x18000c912  lea     rdx, aGsUserlocale; "gs:UserLocale"
0x18000c919  lea     rcx, [rsp+190h+var_158]; this
0x18000c91e  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000c923  nop
0x18000c924  mov     r8, rax
0x18000c927  lea     rdx, [rsp+190h+var_168]
0x18000c92c  mov     rcx, rbx
0x18000c92f  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x18000c934  nop
0x18000c935  mov     rdx, [rax]
0x18000c938  test    rdx, rdx
0x18000c93b  jz      short loc_18000C942
0x18000c93d  mov     rdx, [rdx]
0x18000c940  jmp     short loc_18000C945
0x18000c942  mov     rdx, r15
0x18000c945  lea     r8, [rsp+190h+var_118]
0x18000c94a  mov     rcx, rsi
0x18000c94d  mov     rax, r14
0x18000c950  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c955  mov     ebx, eax
0x18000c957  lea     rcx, [rsp+190h+var_168]; this
0x18000c95c  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000c961  nop
0x18000c962  lea     rcx, [rsp+190h+var_158]; this
0x18000c967  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000c96c  nop
0x18000c96d  lea     rcx, [rsp+190h+var_150]; this
0x18000c972  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000c977  cmp     ebx, 1
0x18000c97a  jnz     short loc_18000C984
0x18000c97c  mov     ebx, r15d
0x18000c97f  jmp     loc_18000CDFF
0x18000c984  mov     ecx, ebx; int
0x18000c986  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000c98b  test    eax, eax
0x18000c98d  jz      loc_18000CDFF
0x18000c993  mov     rax, [rsp+190h+var_118]
0x18000c998  mov     rcx, [rax]
0x18000c99b  mov     r14, [rcx+128h]
0x18000c9a2  lea     rdx, asc_180030760; "//"
0x18000c9a9  lea     rcx, [rsp+190h+var_168]; this
0x18000c9ae  call    ??0_bstr_t@@QEAA@PEBD@Z; _bstr_t::_bstr_t(char const *)
0x18000c9b3  mov     rbx, rax
0x18000c9b6  lea     rdx, aGsLocale; "gs:Locale"
0x18000c9bd  lea     rcx, [rsp+190h+var_158]; this
0x18000c9c2  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000c9c7  nop
0x18000c9c8  mov     r8, rax
0x18000c9cb  lea     rdx, [rsp+190h+var_150]
0x18000c9d0  mov     rcx, rbx
0x18000c9d3  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x18000c9d8  nop
0x18000c9d9  mov     rdx, [rax]
0x18000c9dc  test    rdx, rdx
0x18000c9df  jz      short loc_18000C9E6
0x18000c9e1  mov     rdx, [rdx]
0x18000c9e4  jmp     short loc_18000C9E9
0x18000c9e6  mov     rdx, r15
0x18000c9e9  lea     r8, [rsp+190h+var_138]
0x18000c9ee  mov     rcx, [rsp+190h+var_118]
0x18000c9f3  mov     rax, r14
0x18000c9f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c9fb  mov     ebx, eax
0x18000c9fd  lea     rcx, [rsp+190h+var_150]; this
0x18000ca02  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000ca07  nop
0x18000ca08  lea     rcx, [rsp+190h+var_158]; this
0x18000ca0d  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000ca12  nop
0x18000ca13  lea     rcx, [rsp+190h+var_168]; this
0x18000ca18  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000ca1d  cmp     ebx, 1
0x18000ca20  jz      loc_18000C97C
0x18000ca26  mov     ecx, ebx; int
0x18000ca28  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000ca2d  test    eax, eax
0x18000ca2f  jz      loc_18000CDFF
0x18000ca35  mov     rcx, [rsp+190h+var_138]; struct IXMLDOMNode *
0x18000ca3a  call    ?ChangeUserLocale@@YAJPEAUIXMLDOMNode@@@Z; ChangeUserLocale(IXMLDOMNode *)
0x18000ca3f  mov     ebx, eax
0x18000ca41  test    eax, eax
0x18000ca43  js      loc_18000CDFF
0x18000ca49  cmp     eax, 1
0x18000ca4c  jz      loc_18000CDFF
0x18000ca52  mov     rax, [rsi]
0x18000ca55  mov     r14, [rax+128h]
0x18000ca5c  lea     rdx, asc_180030760; "//"
0x18000ca63  lea     rcx, [rsp+190h+var_168]; this
0x18000ca68  call    ??0_bstr_t@@QEAA@PEBD@Z; _bstr_t::_bstr_t(char const *)
0x18000ca6d  mov     rbx, rax
0x18000ca70  lea     rdx, aGsWin32; "gs:Win32"
0x18000ca77  lea     rcx, [rsp+190h+var_158]; this
0x18000ca7c  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000ca81  nop
0x18000ca82  mov     r8, rax
0x18000ca85  lea     rdx, [rsp+190h+var_150]
0x18000ca8a  mov     rcx, rbx
0x18000ca8d  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x18000ca92  nop
0x18000ca93  mov     rdx, [rax]
0x18000ca96  test    rdx, rdx
0x18000ca99  jz      short loc_18000CAA0
0x18000ca9b  mov     rdx, [rdx]
0x18000ca9e  jmp     short loc_18000CAA3
0x18000caa0  mov     rdx, r15
0x18000caa3  lea     r8, [rsp+190h+var_160]
0x18000caa8  mov     rcx, rsi
0x18000caab  mov     rax, r14
0x18000caae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cab3  mov     ebx, eax
0x18000cab5  lea     rcx, [rsp+190h+var_150]; this
0x18000caba  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000cabf  nop
0x18000cac0  lea     rcx, [rsp+190h+var_158]; this
0x18000cac5  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000caca  nop
0x18000cacb  lea     rcx, [rsp+190h+var_168]; this
0x18000cad0  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000cad5  cmp     ebx, 1
0x18000cad8  jnz     loc_18000CB85
0x18000cade  mov     rax, [rsp+190h+var_138]
0x18000cae3  mov     rcx, [rax]
0x18000cae6  mov     rsi, [rcx+128h]
0x18000caed  lea     rdx, asc_180030760; "//"
0x18000caf4  lea     rcx, [rsp+190h+var_168]; this
0x18000caf9  call    ??0_bstr_t@@QEAA@PEBD@Z; _bstr_t::_bstr_t(char const *)
0x18000cafe  mov     rbx, rax
0x18000cb01  lea     rdx, aGsFramework; "gs:Framework"
0x18000cb08  lea     rcx, [rsp+190h+var_158]; this
0x18000cb0d  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000cb12  nop
0x18000cb13  mov     r8, rax
0x18000cb16  lea     rdx, [rsp+190h+var_150]
0x18000cb1b  mov     rcx, rbx
0x18000cb1e  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x18000cb23  nop
0x18000cb24  mov     rdx, [rax]
0x18000cb27  test    rdx, rdx
0x18000cb2a  jz      short loc_18000CB31
0x18000cb2c  mov     rdx, [rdx]
0x18000cb2f  jmp     short loc_18000CB34
0x18000cb31  mov     rdx, r15
0x18000cb34  lea     r8, [rsp+190h+var_160]
0x18000cb39  mov     rcx, [rsp+190h+var_138]
0x18000cb3e  mov     rax, rsi
0x18000cb41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb46  mov     ebx, eax
0x18000cb48  lea     rcx, [rsp+190h+var_150]; this
0x18000cb4d  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000cb52  nop
0x18000cb53  lea     rcx, [rsp+190h+var_158]; this
0x18000cb58  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000cb5d  nop
0x18000cb5e  lea     rcx, [rsp+190h+var_168]; this
0x18000cb63  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000cb68  cmp     ebx, 1
0x18000cb6b  jz      loc_18000C97C
0x18000cb71  mov     ecx, ebx; int
0x18000cb73  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000cb78  test    eax, eax
0x18000cb7a  jz      loc_18000CDFF
0x18000cb80  mov     sil, r15b
0x18000cb83  jmp     short loc_18000CB97
0x18000cb85  mov     ecx, ebx; int
0x18000cb87  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000cb8c  test    eax, eax
0x18000cb8e  jz      loc_18000CDFF
0x18000cb94  mov     sil, 1
0x18000cb97  mov     rcx, [rsp+190h+var_160]
0x18000cb9c  mov     rax, [rcx]
0x18000cb9f  lea     rdx, [rsp+190h+var_170]
0x18000cba4  mov     rax, [rax+0B0h]
0x18000cbab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbb0  mov     ebx, eax
0x18000cbb2  cmp     eax, 1
0x18000cbb5  jz      loc_18000C97C
0x18000cbbb  mov     ecx, eax; int
0x18000cbbd  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000cbc2  test    eax, eax
0x18000cbc4  jz      loc_18000CDFF
0x18000cbca  cmp     [rsp+190h+var_170], r15w
0x18000cbd0  jz      loc_18000CDFF
0x18000cbd6  mov     dl, sil; bool
0x18000cbd9  mov     rcx, [rsp+190h+var_160]; struct IXMLDOMNode *
0x18000cbde  call    ?ChangeAlternateSort@@YAJPEAUIXMLDOMNode@@_N@Z; ChangeAlternateSort(IXMLDOMNode *,bool)
0x18000cbe3  mov     ebx, eax
0x18000cbe5  test    eax, eax
0x18000cbe7  js      loc_18000CDFF
0x18000cbed  mov     dl, sil; bool
0x18000cbf0  mov     rcx, [rsp+190h+var_160]; struct IXMLDOMNode *
0x18000cbf5  call    ?ChangeCalendar@@YAJPEAUIXMLDOMNode@@_N@Z; ChangeCalendar(IXMLDOMNode *,bool)
0x18000cbfa  mov     ebx, eax
0x18000cbfc  test    eax, eax
0x18000cbfe  js      loc_18000CDFF
0x18000cc04  mov     dl, sil; bool
0x18000cc07  mov     rcx, [rsp+190h+var_160]; struct IXMLDOMNode *
0x18000cc0c  call    ?ChangeTwoDigitYearMax@@YAJPEAUIXMLDOMNode@@_N@Z; ChangeTwoDigitYearMax(IXMLDOMNode *,bool)
0x18000cc11  mov     ebx, eax
0x18000cc13  test    eax, eax
0x18000cc15  js      loc_18000CDFF
0x18000cc1b  mov     rcx, [rsp+190h+var_160]
0x18000cc20  mov     rax, [rcx]
0x18000cc23  lea     rdx, [rsp+190h+var_130]
0x18000cc28  mov     rax, [rax+60h]
0x18000cc2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc31  mov     ebx, eax
0x18000cc33  cmp     eax, 1
0x18000cc36  jz      loc_18000C97C
0x18000cc3c  mov     ecx, eax; int
0x18000cc3e  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000cc43  test    eax, eax
0x18000cc45  jz      loc_18000CDFF
0x18000cc4b  mov     rcx, [rsp+190h+var_130]
0x18000cc50  mov     rax, [rcx]
0x18000cc53  lea     rdx, [rsp+190h+var_140]
0x18000cc58  mov     rax, [rax+40h]
0x18000cc5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc61  mov     ebx, eax
0x18000cc63  mov     ecx, eax; int
0x18000cc65  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000cc6a  test    eax, eax
0x18000cc6c  jz      loc_18000CDFF
0x18000cc72  mov     r14d, r15d
0x18000cc75  cmp     r14d, [rsp+190h+var_140]
0x18000cc7a  jge     loc_18000CDAA
0x18000cc80  lea     rcx, [rsp+190h+var_148]; struct IXMLDOMNode **
0x18000cc85  call    ?ReleaseDomNode@@YAXPEAPEAUIXMLDOMNode@@@Z; ReleaseDomNode(IXMLDOMNode * *)
0x18000cc8a  mov     rcx, [rsp+190h+bstrString]; bstrString
0x18000cc8f  test    rcx, rcx
0x18000cc92  jz      short loc_18000CCA2
0x18000cc94  call    cs:__imp_SysFreeString
0x18000cc9a  mov     rdi, r15
0x18000cc9d  mov     [rsp+190h+lpLCData], r15
0x18000cca2  test    rdi, rdi
0x18000cca5  jz      short loc_18000CCB8
0x18000cca7  mov     rcx, rdi; bstrString
0x18000ccaa  call    cs:__imp_SysFreeString
0x18000ccb0  mov     rdi, r15
0x18000ccb3  mov     [rsp+190h+lpLCData], r15
0x18000ccb8  mov     rcx, [rsp+190h+var_130]
0x18000ccbd  mov     rax, [rcx]
0x18000ccc0  lea     r8, [rsp+190h+var_148]
0x18000ccc5  mov     edx, r14d
0x18000ccc8  mov     rax, [rax+38h]
0x18000cccc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ccd1  mov     ebx, eax
0x18000ccd3  mov     ecx, eax; int
0x18000ccd5  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000ccda  test    eax, eax
0x18000ccdc  jz      loc_18000CDFF
0x18000cce2  mov     [rsp+190h+var_168], r15d
0x18000cce7  mov     rcx, [rsp+190h+var_148]
0x18000ccec  mov     rax, [rcx]
0x18000ccef  lea     rdx, [rsp+190h+var_168]
0x18000ccf4  mov     rax, [rax+50h]
0x18000ccf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ccfd  mov     ebx, eax
0x18000ccff  mov     ecx, eax; int
0x18000cd01  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000cd06  test    eax, eax
  ... truncated ...
```
