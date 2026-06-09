# ChangeCalendar(IXMLDOMNode *,bool)

- ea: `0x18000b000`
- end: `0x18000b29c`
- name: `?ChangeCalendar@@YAJPEAUIXMLDOMNode@@_N@Z`
- size: `668`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, bool)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18000c870`

## callees

- `0x18000aa10`
- `0x18000aa9c`
- `0x18000accc`
- `0x18000b000`
- `0x18000ce98`
- `0x18000d4a0`
- `0x18000da60`
- `0x18000f464`
- `0x180026dc4`
- `0x18002a150`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetCalendarInfoEx` at `0x18000b1f7`
- `api-ms-win-core-localization-l1-2-0!GetCalendarInfoEx` at `0x18000b1f7`
- `api-ms-win-core-localization-l1-2-0!SetLocaleInfoW` at `0x18000b1be`
- `api-ms-win-core-localization-l1-2-0!SetLocaleInfoW` at `0x18000b21e`
- `api-ms-win-core-localization-l1-2-0!SetLocaleInfoW` at `0x18000b1be`
- `api-ms-win-core-localization-l1-2-0!SetLocaleInfoW` at `0x18000b21e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b251`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b251`
- `OLEAUT32!__imp_VariantInit` at `0x18000b059`
- `OLEAUT32!__imp_VariantInit` at `0x18000b059`
- `OLEAUT32!__imp_VariantClear` at `0x18000b25c`
- `OLEAUT32!__imp_VariantClear` at `0x18000b25c`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall ChangeCalendar(struct IXMLDOMNode *a1, char a2)
{
  unsigned __int16 *v4; // rdi
  unsigned int v5; // ebx
  HRESULT (__stdcall *selectSingleNode)(IXMLDOMNode *, BSTR, IXMLDOMNode **); // r14
  _bstr_t *v7; // rbx
  _bstr_t *v8; // rax
  _QWORD *v9; // rdx
  _bstr_t *v10; // rcx
  _bstr_t *v11; // rbx
  _bstr_t *v12; // rax
  _QWORD *v13; // rdx
  int v14; // eax
  CALID v15; // eax
  struct IXMLDOMNode *v17; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v18[8]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v19[8]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v20[8]; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR lpLCData; // [rsp+60h] [rbp-A0h] BYREF
  struct IXMLDOMNode *v22; // [rsp+68h] [rbp-98h] BYREF
  VARIANTARG pvarg; // [rsp+70h] [rbp-90h] BYREF
  WCHAR CalData[88]; // [rsp+90h] [rbp-70h] BYREF

  v17 = 0;
  v22 = 0;
  v4 = 0;
  lpLCData = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  if ( a1 )
  {
    selectSingleNode = a1->lpVtbl->selectSingleNode;
    if ( a2 )
    {
      v7 = _bstr_t::_bstr_t((_bstr_t *)v20, "//");
      v8 = _bstr_t::_bstr_t((_bstr_t *)v19, L"gs:iCalendarType");
      v9 = *(_QWORD **)_bstr_t::operator+(v7, v18, v8);
      if ( v9 )
        v9 = (_QWORD *)*v9;
      v5 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, _QWORD *, struct IXMLDOMNode **))selectSingleNode)(
             a1,
             v9,
             &v17);
      _bstr_t::_Free((_bstr_t *)v18);
      _bstr_t::_Free((_bstr_t *)v19);
      v10 = (_bstr_t *)v20;
    }
    else
    {
      v11 = _bstr_t::_bstr_t((_bstr_t *)v18, "//");
      v12 = _bstr_t::_bstr_t((_bstr_t *)v19, L"gs:Calendar");
      v13 = *(_QWORD **)_bstr_t::operator+(v11, v20, v12);
      if ( v13 )
        v13 = (_QWORD *)*v13;
      v5 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, _QWORD *, struct IXMLDOMNode **))selectSingleNode)(
             a1,
             v13,
             &v17);
      _bstr_t::_Free((_bstr_t *)v20);
      _bstr_t::_Free((_bstr_t *)v19);
      v10 = (_bstr_t *)v18;
    }
    _bstr_t::_Free(v10);
    if ( v5 == 1 )
    {
      v5 = 0;
    }
    else if ( (unsigned int)CheckHR(v5) )
    {
      v14 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, VARIANTARG *))v17->lpVtbl->get_nodeTypedValue)(v17, &pvarg);
      if ( (unsigned int)CheckHR(v14) )
      {
        GetValueFromVariant(&pvarg, (unsigned __int16 **)&lpLCData);
        v4 = (unsigned __int16 *)lpLCData;
        if ( SetLocaleInfoW(0x400u, 0x1009u, lpLCData) )
        {
          v15 = Intl_StrToLong(v4);
          if ( GetCalendarInfoEx(0, v15, 0, 0x2Fu, CalData, 85, 0) )
            SetLocaleInfoW(*(_DWORD *)(*((_QWORD *)g_localeInfo + UserLocaleIndex) + 16LL), 0x1006u, CalData);
        }
      }
      v5 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, struct IXMLDOMNode *, struct IXMLDOMNode **))a1->lpVtbl->removeChild)(
             a1,
             v17,
             &v22);
      CheckHR(v5);
      if ( v4 )
        SysFreeString(v4);
    }
  }
  else
  {
    v5 = -2147024809;
  }
  VariantClear(&pvarg);
  ReleaseDomNode(&v17);
  ReleaseDomNode(&v22);
  return v5;
}

```

## disassembly

```asm
0x18000b000  mov     [rsp-8+arg_8], rbx
0x18000b005  mov     [rsp-8+arg_10], rsi
0x18000b00a  push    rbp
0x18000b00b  push    rdi
0x18000b00c  push    r14
0x18000b00e  lea     rbp, [rsp-50h]
0x18000b013  sub     rsp, 150h
0x18000b01a  mov     rax, cs:__security_cookie
0x18000b021  xor     rax, rsp
0x18000b024  mov     [rbp+60h+var_20], rax
0x18000b028  mov     bl, dl
0x18000b02a  mov     rsi, rcx
0x18000b02d  mov     [rsp+160h+var_120], 0
0x18000b036  mov     [rsp+160h+var_F8], 0
0x18000b03f  xor     edi, edi
0x18000b041  mov     [rsp+160h+lpLCData], rdi
0x18000b046  xorps   xmm0, xmm0
0x18000b049  xor     eax, eax
0x18000b04b  movups  xmmword ptr [rsp+160h+pvarg], xmm0
0x18000b050  mov     qword ptr [rbp+60h+pvarg+10h], rax
0x18000b054  lea     rcx, [rsp+160h+pvarg]; pvarg
0x18000b059  call    cs:__imp_VariantInit
0x18000b05f  test    rsi, rsi
0x18000b062  jnz     short loc_18000B06E
0x18000b064  mov     ebx, 80070057h
0x18000b069  jmp     loc_18000B257
0x18000b06e  mov     rax, [rsi]
0x18000b071  mov     r14, [rax+128h]
0x18000b078  lea     rdx, asc_180030760; "//"
0x18000b07f  test    bl, bl
0x18000b081  jz      short loc_18000B0ED
0x18000b083  lea     rcx, [rsp+160h+var_108]; this
0x18000b088  call    ??0_bstr_t@@QEAA@PEBD@Z; _bstr_t::_bstr_t(char const *)
0x18000b08d  mov     rbx, rax
0x18000b090  lea     rdx, aGsIcalendartyp_0; "gs:iCalendarType"
0x18000b097  lea     rcx, [rsp+160h+var_110]; this
0x18000b09c  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000b0a1  nop
0x18000b0a2  mov     r8, rax
0x18000b0a5  lea     rdx, [rsp+160h+var_118]
0x18000b0aa  mov     rcx, rbx
0x18000b0ad  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x18000b0b2  nop
0x18000b0b3  mov     rdx, [rax]
0x18000b0b6  test    rdx, rdx
0x18000b0b9  jz      short loc_18000B0BE
0x18000b0bb  mov     rdx, [rdx]
0x18000b0be  lea     r8, [rsp+160h+var_120]
0x18000b0c3  mov     rcx, rsi
0x18000b0c6  mov     rax, r14
0x18000b0c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0ce  mov     ebx, eax
0x18000b0d0  lea     rcx, [rsp+160h+var_118]; this
0x18000b0d5  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000b0da  nop
0x18000b0db  lea     rcx, [rsp+160h+var_110]; this
0x18000b0e0  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000b0e5  nop
0x18000b0e6  lea     rcx, [rsp+160h+var_108]
0x18000b0eb  jmp     short loc_18000B155
0x18000b0ed  lea     rcx, [rsp+160h+var_118]; this
0x18000b0f2  call    ??0_bstr_t@@QEAA@PEBD@Z; _bstr_t::_bstr_t(char const *)
0x18000b0f7  mov     rbx, rax
0x18000b0fa  lea     rdx, aGsCalendar_0; "gs:Calendar"
0x18000b101  lea     rcx, [rsp+160h+var_110]; this
0x18000b106  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000b10b  nop
0x18000b10c  mov     r8, rax
0x18000b10f  lea     rdx, [rsp+160h+var_108]
0x18000b114  mov     rcx, rbx
0x18000b117  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x18000b11c  nop
0x18000b11d  mov     rdx, [rax]
0x18000b120  test    rdx, rdx
0x18000b123  jz      short loc_18000B128
0x18000b125  mov     rdx, [rdx]
0x18000b128  lea     r8, [rsp+160h+var_120]
0x18000b12d  mov     rcx, rsi
0x18000b130  mov     rax, r14
0x18000b133  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b138  mov     ebx, eax
0x18000b13a  lea     rcx, [rsp+160h+var_108]; this
0x18000b13f  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000b144  nop
0x18000b145  lea     rcx, [rsp+160h+var_110]; this
0x18000b14a  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000b14f  nop
0x18000b150  lea     rcx, [rsp+160h+var_118]; this
0x18000b155  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000b15a  cmp     ebx, 1
0x18000b15d  jnz     short loc_18000B166
0x18000b15f  xor     ebx, ebx
0x18000b161  jmp     loc_18000B257
0x18000b166  mov     ecx, ebx; int
0x18000b168  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000b16d  test    eax, eax
0x18000b16f  jz      loc_18000B257
0x18000b175  mov     rcx, [rsp+160h+var_120]
0x18000b17a  mov     rax, [rcx]
0x18000b17d  lea     rdx, [rsp+160h+pvarg]
0x18000b182  mov     rax, [rax+0F0h]
0x18000b189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b18e  mov     ecx, eax; int
0x18000b190  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000b195  test    eax, eax
0x18000b197  jz      loc_18000B224
0x18000b19d  lea     rdx, [rsp+160h+lpLCData]; unsigned __int16 **
0x18000b1a2  lea     rcx, [rsp+160h+pvarg]; struct tagVARIANT *
0x18000b1a7  call    ?GetValueFromVariant@@YAXPEAUtagVARIANT@@PEAPEAG@Z; GetValueFromVariant(tagVARIANT *,ushort * *)
0x18000b1ac  mov     rdi, [rsp+160h+lpLCData]
0x18000b1b1  mov     r8, rdi; lpLCData
0x18000b1b4  mov     edx, 1009h; LCType
0x18000b1b9  mov     ecx, 400h; Locale
0x18000b1be  call    cs:__imp_SetLocaleInfoW
0x18000b1c4  test    eax, eax
0x18000b1c6  jz      short loc_18000B224
0x18000b1c8  mov     rcx, rdi; unsigned __int16 *
0x18000b1cb  call    ?Intl_StrToLong@@YAJPEBG@Z; Intl_StrToLong(ushort const *)
0x18000b1d0  mov     [rsp+160h+lpValue], 0; lpValue
0x18000b1d9  mov     [rsp+160h+cchData], 55h ; 'U'; cchData
0x18000b1e1  lea     rcx, [rbp+60h+CalData]
0x18000b1e5  mov     [rsp+160h+lpCalData], rcx; lpCalData
0x18000b1ea  mov     r9d, 2Fh ; '/'; CalType
0x18000b1f0  xor     r8d, r8d; lpReserved
0x18000b1f3  mov     edx, eax; Calendar
0x18000b1f5  xor     ecx, ecx; lpLocaleName
0x18000b1f7  call    cs:__imp_GetCalendarInfoEx
0x18000b1fd  test    eax, eax
0x18000b1ff  jz      short loc_18000B224
0x18000b201  mov     edx, cs:?UserLocaleIndex@@3KA; ulong UserLocaleIndex
0x18000b207  mov     rax, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x18000b20e  mov     rcx, [rax+rdx*8]
0x18000b212  lea     r8, [rbp+60h+CalData]; lpLCData
0x18000b216  mov     edx, 1006h; LCType
0x18000b21b  mov     ecx, [rcx+10h]; Locale
0x18000b21e  call    cs:__imp_SetLocaleInfoW
0x18000b224  mov     rax, [rsi]
0x18000b227  lea     r8, [rsp+160h+var_F8]
0x18000b22c  mov     rdx, [rsp+160h+var_120]
0x18000b231  mov     rcx, rsi
0x18000b234  mov     rax, [rax+0A0h]
0x18000b23b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b240  mov     ebx, eax
0x18000b242  mov     ecx, eax; int
0x18000b244  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000b249  test    rdi, rdi
0x18000b24c  jz      short loc_18000B257
0x18000b24e  mov     rcx, rdi; bstrString
0x18000b251  call    cs:__imp_SysFreeString
0x18000b257  lea     rcx, [rsp+160h+pvarg]; pvarg
0x18000b25c  call    cs:__imp_VariantClear
0x18000b262  lea     rcx, [rsp+160h+var_120]; struct IXMLDOMNode **
0x18000b267  call    ?ReleaseDomNode@@YAXPEAPEAUIXMLDOMNode@@@Z; ReleaseDomNode(IXMLDOMNode * *)
0x18000b26c  lea     rcx, [rsp+160h+var_F8]; struct IXMLDOMNode **
0x18000b271  call    ?ReleaseDomNode@@YAXPEAPEAUIXMLDOMNode@@@Z; ReleaseDomNode(IXMLDOMNode * *)
0x18000b276  mov     eax, ebx
0x18000b278  mov     rcx, [rbp+60h+var_20]
0x18000b27c  xor     rcx, rsp; StackCookie
0x18000b27f  call    __security_check_cookie
0x18000b284  lea     r11, [rsp+160h+var_10]
0x18000b28c  mov     rbx, [r11+28h]
0x18000b290  mov     rsi, [r11+30h]
0x18000b294  mov     rsp, r11
0x18000b297  pop     r14
0x18000b299  pop     rdi
0x18000b29a  pop     rbp
0x18000b29b  retn
```
