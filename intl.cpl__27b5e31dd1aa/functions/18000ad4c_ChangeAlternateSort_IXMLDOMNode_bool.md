# ChangeAlternateSort(IXMLDOMNode *,bool)

- ea: `0x18000ad4c`
- end: `0x18000aff7`
- name: `?ChangeAlternateSort@@YAJPEAUIXMLDOMNode@@_N@Z`
- size: `683`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, bool)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update`

## callers

- `0x18000c870`

## callees

- `0x18000aa10`
- `0x18000aa9c`
- `0x18000accc`
- `0x18000ad4c`
- `0x18000ce98`
- `0x18000d4a0`
- `0x18000da60`
- `0x18000f464`
- `0x180012dc8`
- `0x18002a150`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18000af28`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18000af28`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x18000af08`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x18000af3e`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x18000af08`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x18000af3e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000afb4`
- `OLEAUT32!__imp_SysFreeString` at `0x18000afb4`
- `OLEAUT32!__imp_VariantInit` at `0x18000ada3`
- `OLEAUT32!__imp_VariantInit` at `0x18000ada3`
- `OLEAUT32!__imp_VariantClear` at `0x18000afbf`
- `OLEAUT32!__imp_VariantClear` at `0x18000afbf`
- `KERNEL32!NlsUpdateLocale` at `0x18000af69`
- `KERNEL32!NlsUpdateLocale` at `0x18000af69`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall ChangeAlternateSort(struct IXMLDOMNode *a1, char a2)
{
  unsigned int v4; // ebx
  HRESULT (__stdcall *selectSingleNode)(IXMLDOMNode *, BSTR, IXMLDOMNode **); // rdi
  _bstr_t *v6; // rbx
  _bstr_t *v7; // rax
  _QWORD *v8; // rdx
  _bstr_t *v9; // rcx
  _bstr_t *v10; // rbx
  _bstr_t *v11; // rax
  _QWORD *v12; // rdx
  WCHAR *v13; // rdi
  LCID v14; // esi
  LCID v15; // eax
  struct IXMLDOMNode *v17; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v18[8]; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v19[8]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v20[8]; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR lpName; // [rsp+40h] [rbp-C0h] BYREF
  struct IXMLDOMNode *v22; // [rsp+48h] [rbp-B8h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR LCData[88]; // [rsp+70h] [rbp-90h] BYREF

  v17 = 0;
  v22 = 0;
  lpName = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  if ( !a1 )
  {
    v4 = -2147024809;
    goto LABEL_29;
  }
  selectSingleNode = a1->lpVtbl->selectSingleNode;
  if ( a2 )
  {
    v6 = _bstr_t::_bstr_t((_bstr_t *)v20, "//");
    v7 = _bstr_t::_bstr_t((_bstr_t *)v19, L"gs:sSort");
    v8 = *(_QWORD **)_bstr_t::operator+(v6, v18, v7);
    if ( v8 )
      v8 = (_QWORD *)*v8;
    v4 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, _QWORD *, struct IXMLDOMNode **))selectSingleNode)(a1, v8, &v17);
    _bstr_t::_Free((_bstr_t *)v18);
    _bstr_t::_Free((_bstr_t *)v19);
    v9 = (_bstr_t *)v20;
  }
  else
  {
    v10 = _bstr_t::_bstr_t((_bstr_t *)v18, "//");
    v11 = _bstr_t::_bstr_t((_bstr_t *)v19, L"gs:AlternateSort");
    v12 = *(_QWORD **)_bstr_t::operator+(v10, v20, v11);
    if ( v12 )
      v12 = (_QWORD *)*v12;
    v4 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, _QWORD *, struct IXMLDOMNode **))selectSingleNode)(
           a1,
           v12,
           &v17);
    _bstr_t::_Free((_bstr_t *)v20);
    _bstr_t::_Free((_bstr_t *)v19);
    v9 = (_bstr_t *)v18;
  }
  _bstr_t::_Free(v9);
  if ( v4 == 1 )
  {
    v4 = 0;
    goto LABEL_29;
  }
  if ( (unsigned int)CheckHR(v4) )
  {
    v4 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, VARIANTARG *))v17->lpVtbl->get_nodeTypedValue)(v17, &pvarg);
    if ( (unsigned int)CheckHR(v4) )
    {
      GetValueFromVariant(&pvarg, (unsigned __int16 **)&lpName);
      v13 = (WCHAR *)lpName;
      v14 = LocaleNameToLCID(lpName, 0);
      if ( v14 )
      {
        if ( !GetLocaleInfoW(0x400u, 0x5Cu, LCData, 85) )
        {
          v4 = 1;
          goto LABEL_27;
        }
        v15 = LocaleNameToLCID(LCData, 0);
        if ( v15 == 3082 && v14 == 1034 || v15 == 1034 && v14 == 3082 || (_WORD)v15 == (_WORD)v14 )
        {
          if ( (unsigned int)NlsUpdateLocale(v13, 1) )
            v4 = 1;
          if ( v4 != 1 )
            Input_InstallLayout(0, v13, 0);
        }
      }
      v4 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, struct IXMLDOMNode *, struct IXMLDOMNode **))a1->lpVtbl->removeChild)(
             a1,
             v17,
             &v22);
      CheckHR(v4);
LABEL_27:
      if ( v13 )
        SysFreeString(v13);
    }
  }
LABEL_29:
  VariantClear(&pvarg);
  ReleaseDomNode(&v17);
  ReleaseDomNode(&v22);
  return v4;
}

```

## disassembly

```asm
0x18000ad4c  push    rbp
0x18000ad4e  push    rbx
0x18000ad4f  push    rsi
0x18000ad50  push    rdi
0x18000ad51  push    r12
0x18000ad53  push    r14
0x18000ad55  lea     rbp, [rsp-38h]
0x18000ad5a  sub     rsp, 138h
0x18000ad61  mov     rax, cs:__security_cookie
0x18000ad68  xor     rax, rsp
0x18000ad6b  mov     [rbp+60h+var_40], rax
0x18000ad6f  mov     bl, dl
0x18000ad71  mov     r14, rcx
0x18000ad74  mov     [rsp+160h+var_140], 0
0x18000ad7d  mov     [rsp+160h+var_118], 0
0x18000ad86  mov     [rsp+160h+lpName], 0
0x18000ad8f  xorps   xmm0, xmm0
0x18000ad92  xor     eax, eax
0x18000ad94  movups  xmmword ptr [rsp+160h+pvarg], xmm0
0x18000ad99  mov     qword ptr [rsp+160h+pvarg+10h], rax
0x18000ad9e  lea     rcx, [rsp+160h+pvarg]; pvarg
0x18000ada3  call    cs:__imp_VariantInit
0x18000ada9  test    r14, r14
0x18000adac  jnz     short loc_18000ADB8
0x18000adae  mov     ebx, 80070057h
0x18000adb3  jmp     loc_18000AFBA
0x18000adb8  mov     rax, [r14]
0x18000adbb  mov     rdi, [rax+128h]
0x18000adc2  lea     rdx, asc_180030760; "//"
0x18000adc9  test    bl, bl
0x18000adcb  jz      short loc_18000AE37
0x18000adcd  lea     rcx, [rsp+160h+var_128]; this
0x18000add2  call    ??0_bstr_t@@QEAA@PEBD@Z; _bstr_t::_bstr_t(char const *)
0x18000add7  mov     rbx, rax
0x18000adda  lea     rdx, aGsSsort; "gs:sSort"
0x18000ade1  lea     rcx, [rsp+160h+var_130]; this
0x18000ade6  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000adeb  nop
0x18000adec  mov     r8, rax
0x18000adef  lea     rdx, [rsp+160h+var_138]
0x18000adf4  mov     rcx, rbx
0x18000adf7  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x18000adfc  nop
0x18000adfd  mov     rdx, [rax]
0x18000ae00  test    rdx, rdx
0x18000ae03  jz      short loc_18000AE08
0x18000ae05  mov     rdx, [rdx]
0x18000ae08  lea     r8, [rsp+160h+var_140]
0x18000ae0d  mov     rcx, r14
0x18000ae10  mov     rax, rdi
0x18000ae13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae18  mov     ebx, eax
0x18000ae1a  lea     rcx, [rsp+160h+var_138]; this
0x18000ae1f  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000ae24  nop
0x18000ae25  lea     rcx, [rsp+160h+var_130]; this
0x18000ae2a  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000ae2f  nop
0x18000ae30  lea     rcx, [rsp+160h+var_128]
0x18000ae35  jmp     short loc_18000AE9F
0x18000ae37  lea     rcx, [rsp+160h+var_138]; this
0x18000ae3c  call    ??0_bstr_t@@QEAA@PEBD@Z; _bstr_t::_bstr_t(char const *)
0x18000ae41  mov     rbx, rax
0x18000ae44  lea     rdx, aGsAlternatesor; "gs:AlternateSort"
0x18000ae4b  lea     rcx, [rsp+160h+var_130]; this
0x18000ae50  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000ae55  nop
0x18000ae56  mov     r8, rax
0x18000ae59  lea     rdx, [rsp+160h+var_128]
0x18000ae5e  mov     rcx, rbx
0x18000ae61  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x18000ae66  nop
0x18000ae67  mov     rdx, [rax]
0x18000ae6a  test    rdx, rdx
0x18000ae6d  jz      short loc_18000AE72
0x18000ae6f  mov     rdx, [rdx]
0x18000ae72  lea     r8, [rsp+160h+var_140]
0x18000ae77  mov     rcx, r14
0x18000ae7a  mov     rax, rdi
0x18000ae7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae82  mov     ebx, eax
0x18000ae84  lea     rcx, [rsp+160h+var_128]; this
0x18000ae89  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000ae8e  nop
0x18000ae8f  lea     rcx, [rsp+160h+var_130]; this
0x18000ae94  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000ae99  nop
0x18000ae9a  lea     rcx, [rsp+160h+var_138]; this
0x18000ae9f  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000aea4  mov     r12d, 1
0x18000aeaa  cmp     ebx, r12d
0x18000aead  jnz     short loc_18000AEB6
0x18000aeaf  xor     ebx, ebx
0x18000aeb1  jmp     loc_18000AFBA
0x18000aeb6  mov     ecx, ebx; int
0x18000aeb8  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000aebd  test    eax, eax
0x18000aebf  jz      loc_18000AFBA
0x18000aec5  mov     rcx, [rsp+160h+var_140]
0x18000aeca  mov     rax, [rcx]
0x18000aecd  lea     rdx, [rsp+160h+pvarg]
0x18000aed2  mov     rax, [rax+0F0h]
0x18000aed9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aede  mov     ebx, eax
0x18000aee0  mov     ecx, eax; int
0x18000aee2  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000aee7  test    eax, eax
0x18000aee9  jz      loc_18000AFBA
0x18000aeef  lea     rdx, [rsp+160h+lpName]; unsigned __int16 **
0x18000aef4  lea     rcx, [rsp+160h+pvarg]; struct tagVARIANT *
0x18000aef9  call    ?GetValueFromVariant@@YAXPEAUtagVARIANT@@PEAPEAG@Z; GetValueFromVariant(tagVARIANT *,ushort * *)
0x18000aefe  xor     edx, edx; dwFlags
0x18000af00  mov     rdi, [rsp+160h+lpName]
0x18000af05  mov     rcx, rdi; lpName
0x18000af08  call    cs:__imp_LocaleNameToLCID
0x18000af0e  mov     esi, eax
0x18000af10  test    eax, eax
0x18000af12  jz      short loc_18000AF87
0x18000af14  mov     r9d, 55h ; 'U'; cchData
0x18000af1a  lea     r8, [rsp+160h+LCData]; lpLCData
0x18000af1f  lea     edx, [r9+7]; LCType
0x18000af23  mov     ecx, 400h; Locale
0x18000af28  call    cs:__imp_GetLocaleInfoW
0x18000af2e  test    eax, eax
0x18000af30  jnz     short loc_18000AF37
0x18000af32  mov     ebx, r12d
0x18000af35  jmp     short loc_18000AFAC
0x18000af37  xor     edx, edx; dwFlags
0x18000af39  lea     rcx, [rsp+160h+LCData]; lpName
0x18000af3e  call    cs:__imp_LocaleNameToLCID
0x18000af44  mov     ecx, 40Ah
0x18000af49  mov     edx, 0C0Ah
0x18000af4e  cmp     eax, edx
0x18000af50  jnz     short loc_18000AF56
0x18000af52  cmp     esi, ecx
0x18000af54  jz      short loc_18000AF63
0x18000af56  cmp     eax, ecx
0x18000af58  jnz     short loc_18000AF5E
0x18000af5a  cmp     esi, edx
0x18000af5c  jz      short loc_18000AF63
0x18000af5e  cmp     ax, si
0x18000af61  jnz     short loc_18000AF87
0x18000af63  mov     edx, r12d
0x18000af66  mov     rcx, rdi
0x18000af69  call    cs:__imp_NlsUpdateLocale
0x18000af6f  test    eax, eax
0x18000af71  cmovnz  ebx, r12d
0x18000af75  cmp     ebx, r12d
0x18000af78  jz      short loc_18000AF87
0x18000af7a  xor     r8d, r8d; unsigned int
0x18000af7d  mov     rdx, rdi; lpLocaleName
0x18000af80  xor     ecx, ecx; hWnd
0x18000af82  call    ?Input_InstallLayout@@YAHPEAUHWND__@@PEBGK@Z; Input_InstallLayout(HWND__ *,ushort const *,ulong)
0x18000af87  mov     rax, [r14]
0x18000af8a  lea     r8, [rsp+160h+var_118]
0x18000af8f  mov     rdx, [rsp+160h+var_140]
0x18000af94  mov     rcx, r14
0x18000af97  mov     rax, [rax+0A0h]
0x18000af9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afa3  mov     ebx, eax
0x18000afa5  mov     ecx, eax; int
0x18000afa7  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000afac  test    rdi, rdi
0x18000afaf  jz      short loc_18000AFBA
0x18000afb1  mov     rcx, rdi; bstrString
0x18000afb4  call    cs:__imp_SysFreeString
0x18000afba  lea     rcx, [rsp+160h+pvarg]; pvarg
0x18000afbf  call    cs:__imp_VariantClear
0x18000afc5  lea     rcx, [rsp+160h+var_140]; struct IXMLDOMNode **
0x18000afca  call    ?ReleaseDomNode@@YAXPEAPEAUIXMLDOMNode@@@Z; ReleaseDomNode(IXMLDOMNode * *)
0x18000afcf  lea     rcx, [rsp+160h+var_118]; struct IXMLDOMNode **
0x18000afd4  call    ?ReleaseDomNode@@YAXPEAPEAUIXMLDOMNode@@@Z; ReleaseDomNode(IXMLDOMNode * *)
0x18000afd9  mov     eax, ebx
0x18000afdb  mov     rcx, [rbp+60h+var_40]
0x18000afdf  xor     rcx, rsp; StackCookie
0x18000afe2  call    __security_check_cookie
0x18000afe7  add     rsp, 138h
0x18000afee  pop     r14
0x18000aff0  pop     r12
0x18000aff2  pop     rdi
0x18000aff3  pop     rsi
0x18000aff4  pop     rbx
0x18000aff5  pop     rbp
0x18000aff6  retn
```
