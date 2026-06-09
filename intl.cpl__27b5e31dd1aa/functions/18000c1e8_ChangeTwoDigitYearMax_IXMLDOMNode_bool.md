# ChangeTwoDigitYearMax(IXMLDOMNode *,bool)

- ea: `0x18000c1e8`
- end: `0x18000c44e`
- name: `?ChangeTwoDigitYearMax@@YAJPEAUIXMLDOMNode@@_N@Z`
- size: `614`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, bool)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18000c870`

## callees

- `0x18000aa10`
- `0x18000aa9c`
- `0x18000accc`
- `0x18000c1e8`
- `0x18000ce98`
- `0x18000d4a0`
- `0x18000da60`
- `0x18000f464`
- `0x18002a150`
- `0x18002b010`

## import_xrefs

- `msvcrt!_wtoi` at `0x18000c3c6`
- `msvcrt!_wtoi` at `0x18000c3c6`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18000c3b7`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18000c3b7`
- `api-ms-win-core-localization-l1-2-0!SetCalendarInfoW` at `0x18000c3dc`
- `api-ms-win-core-localization-l1-2-0!SetCalendarInfoW` at `0x18000c3dc`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c40f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c40f`
- `OLEAUT32!__imp_SysStringLen` at `0x18000c398`
- `OLEAUT32!__imp_SysStringLen` at `0x18000c398`
- `OLEAUT32!__imp_VariantInit` at `0x18000c23b`
- `OLEAUT32!__imp_VariantInit` at `0x18000c23b`
- `OLEAUT32!__imp_VariantClear` at `0x18000c41a`
- `OLEAUT32!__imp_VariantClear` at `0x18000c41a`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall ChangeTwoDigitYearMax(struct IXMLDOMNode *a1, char a2)
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
  CALID v14; // eax
  struct IXMLDOMNode *v16; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v17[8]; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v18[8]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v19[8]; // [rsp+38h] [rbp-C8h] BYREF
  BSTR pbstr; // [rsp+40h] [rbp-C0h] BYREF
  struct IXMLDOMNode *v21; // [rsp+48h] [rbp-B8h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR LCData[88]; // [rsp+70h] [rbp-90h] BYREF

  v16 = 0;
  v21 = 0;
  pbstr = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  if ( a1 )
  {
    selectSingleNode = a1->lpVtbl->selectSingleNode;
    if ( a2 )
    {
      v6 = _bstr_t::_bstr_t((_bstr_t *)v19, "//");
      v7 = _bstr_t::_bstr_t((_bstr_t *)v18, L"gs:iTwoDigitYearMax");
      v8 = *(_QWORD **)_bstr_t::operator+(v6, v17, v7);
      if ( v8 )
        v8 = (_QWORD *)*v8;
      v4 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, _QWORD *, struct IXMLDOMNode **))selectSingleNode)(
             a1,
             v8,
             &v16);
      _bstr_t::_Free((_bstr_t *)v17);
      _bstr_t::_Free((_bstr_t *)v18);
      v9 = (_bstr_t *)v19;
    }
    else
    {
      v10 = _bstr_t::_bstr_t((_bstr_t *)v17, "//");
      v11 = _bstr_t::_bstr_t((_bstr_t *)v18, L"gs:TwoDigitYearMax");
      v12 = *(_QWORD **)_bstr_t::operator+(v10, v19, v11);
      if ( v12 )
        v12 = (_QWORD *)*v12;
      v4 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, _QWORD *, struct IXMLDOMNode **))selectSingleNode)(
             a1,
             v12,
             &v16);
      _bstr_t::_Free((_bstr_t *)v19);
      _bstr_t::_Free((_bstr_t *)v18);
      v9 = (_bstr_t *)v17;
    }
    _bstr_t::_Free(v9);
    if ( v4 == 1 )
    {
      v4 = 0;
    }
    else if ( (unsigned int)CheckHR(v4) )
    {
      v4 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, VARIANTARG *))v16->lpVtbl->get_nodeTypedValue)(v16, &pvarg);
      if ( (unsigned int)CheckHR(v4) )
      {
        GetValueFromVariant(&pvarg, &pbstr);
        v13 = pbstr;
        if ( SysStringLen(pbstr) && GetLocaleInfoW(0x400u, 0x1009u, LCData, 85) )
        {
          v14 = _wtoi(LCData);
          SetCalendarInfoW(0x400u, v14, 0x30u, v13);
          v4 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, struct IXMLDOMNode *, struct IXMLDOMNode **))a1->lpVtbl->removeChild)(
                 a1,
                 v16,
                 &v21);
          CheckHR(v4);
        }
        if ( v13 )
          SysFreeString(v13);
      }
    }
  }
  else
  {
    v4 = -2147024809;
  }
  VariantClear(&pvarg);
  ReleaseDomNode(&v16);
  ReleaseDomNode(&v21);
  return v4;
}

```

## disassembly

```asm
0x18000c1e8  push    rbp
0x18000c1ea  push    rbx
0x18000c1eb  push    rsi
0x18000c1ec  push    rdi
0x18000c1ed  lea     rbp, [rsp-38h]
0x18000c1f2  sub     rsp, 138h
0x18000c1f9  mov     rax, cs:__security_cookie
0x18000c200  xor     rax, rsp
0x18000c203  mov     [rbp+50h+var_30], rax
0x18000c207  mov     bl, dl
0x18000c209  mov     rsi, rcx
0x18000c20c  mov     [rsp+150h+var_130], 0
0x18000c215  mov     [rsp+150h+var_108], 0
0x18000c21e  mov     [rsp+150h+pbstr], 0
0x18000c227  xorps   xmm0, xmm0
0x18000c22a  xor     eax, eax
0x18000c22c  movups  xmmword ptr [rsp+150h+pvarg], xmm0
0x18000c231  mov     qword ptr [rsp+150h+pvarg+10h], rax
0x18000c236  lea     rcx, [rsp+150h+pvarg]; pvarg
0x18000c23b  call    cs:__imp_VariantInit
0x18000c241  test    rsi, rsi
0x18000c244  jnz     short loc_18000C250
0x18000c246  mov     ebx, 80070057h
0x18000c24b  jmp     loc_18000C415
0x18000c250  mov     rax, [rsi]
0x18000c253  mov     rdi, [rax+128h]
0x18000c25a  lea     rdx, asc_180030760; "//"
0x18000c261  test    bl, bl
0x18000c263  jz      short loc_18000C2CF
0x18000c265  lea     rcx, [rsp+150h+var_118]; this
0x18000c26a  call    ??0_bstr_t@@QEAA@PEBD@Z; _bstr_t::_bstr_t(char const *)
0x18000c26f  mov     rbx, rax
0x18000c272  lea     rdx, aGsItwodigityea; "gs:iTwoDigitYearMax"
0x18000c279  lea     rcx, [rsp+150h+var_120]; this
0x18000c27e  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000c283  nop
0x18000c284  mov     r8, rax
0x18000c287  lea     rdx, [rsp+150h+var_128]
0x18000c28c  mov     rcx, rbx
0x18000c28f  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x18000c294  nop
0x18000c295  mov     rdx, [rax]
0x18000c298  test    rdx, rdx
0x18000c29b  jz      short loc_18000C2A0
0x18000c29d  mov     rdx, [rdx]
0x18000c2a0  lea     r8, [rsp+150h+var_130]
0x18000c2a5  mov     rcx, rsi
0x18000c2a8  mov     rax, rdi
0x18000c2ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2b0  mov     ebx, eax
0x18000c2b2  lea     rcx, [rsp+150h+var_128]; this
0x18000c2b7  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000c2bc  nop
0x18000c2bd  lea     rcx, [rsp+150h+var_120]; this
0x18000c2c2  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000c2c7  nop
0x18000c2c8  lea     rcx, [rsp+150h+var_118]
0x18000c2cd  jmp     short loc_18000C337
0x18000c2cf  lea     rcx, [rsp+150h+var_128]; this
0x18000c2d4  call    ??0_bstr_t@@QEAA@PEBD@Z; _bstr_t::_bstr_t(char const *)
0x18000c2d9  mov     rbx, rax
0x18000c2dc  lea     rdx, aGsTwodigityear; "gs:TwoDigitYearMax"
0x18000c2e3  lea     rcx, [rsp+150h+var_120]; this
0x18000c2e8  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18000c2ed  nop
0x18000c2ee  mov     r8, rax
0x18000c2f1  lea     rdx, [rsp+150h+var_118]
0x18000c2f6  mov     rcx, rbx
0x18000c2f9  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x18000c2fe  nop
0x18000c2ff  mov     rdx, [rax]
0x18000c302  test    rdx, rdx
0x18000c305  jz      short loc_18000C30A
0x18000c307  mov     rdx, [rdx]
0x18000c30a  lea     r8, [rsp+150h+var_130]
0x18000c30f  mov     rcx, rsi
0x18000c312  mov     rax, rdi
0x18000c315  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c31a  mov     ebx, eax
0x18000c31c  lea     rcx, [rsp+150h+var_118]; this
0x18000c321  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000c326  nop
0x18000c327  lea     rcx, [rsp+150h+var_120]; this
0x18000c32c  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000c331  nop
0x18000c332  lea     rcx, [rsp+150h+var_128]; this
0x18000c337  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000c33c  cmp     ebx, 1
0x18000c33f  jnz     short loc_18000C348
0x18000c341  xor     ebx, ebx
0x18000c343  jmp     loc_18000C415
0x18000c348  mov     ecx, ebx; int
0x18000c34a  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000c34f  test    eax, eax
0x18000c351  jz      loc_18000C415
0x18000c357  mov     rcx, [rsp+150h+var_130]
0x18000c35c  mov     rax, [rcx]
0x18000c35f  lea     rdx, [rsp+150h+pvarg]
0x18000c364  mov     rax, [rax+0F0h]
0x18000c36b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c370  mov     ebx, eax
0x18000c372  mov     ecx, eax; int
0x18000c374  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000c379  test    eax, eax
0x18000c37b  jz      loc_18000C415
0x18000c381  lea     rdx, [rsp+150h+pbstr]; unsigned __int16 **
0x18000c386  lea     rcx, [rsp+150h+pvarg]; struct tagVARIANT *
0x18000c38b  call    ?GetValueFromVariant@@YAXPEAUtagVARIANT@@PEAPEAG@Z; GetValueFromVariant(tagVARIANT *,ushort * *)
0x18000c390  mov     rdi, [rsp+150h+pbstr]
0x18000c395  mov     rcx, rdi; pbstr
0x18000c398  call    cs:__imp_SysStringLen
0x18000c39e  test    eax, eax
0x18000c3a0  jz      short loc_18000C407
0x18000c3a2  mov     r9d, 55h ; 'U'; cchData
0x18000c3a8  lea     r8, [rsp+150h+LCData]; lpLCData
0x18000c3ad  mov     edx, 1009h; LCType
0x18000c3b2  mov     ecx, 400h; Locale
0x18000c3b7  call    cs:__imp_GetLocaleInfoW
0x18000c3bd  test    eax, eax
0x18000c3bf  jz      short loc_18000C407
0x18000c3c1  lea     rcx, [rsp+150h+LCData]; String
0x18000c3c6  call    cs:__imp__wtoi
0x18000c3cc  mov     r9, rdi; lpCalData
0x18000c3cf  mov     r8d, 30h ; '0'; CalType
0x18000c3d5  mov     edx, eax; Calendar
0x18000c3d7  mov     ecx, 400h; Locale
0x18000c3dc  call    cs:__imp_SetCalendarInfoW
0x18000c3e2  mov     rax, [rsi]
0x18000c3e5  lea     r8, [rsp+150h+var_108]
0x18000c3ea  mov     rdx, [rsp+150h+var_130]
0x18000c3ef  mov     rcx, rsi
0x18000c3f2  mov     rax, [rax+0A0h]
0x18000c3f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3fe  mov     ebx, eax
0x18000c400  mov     ecx, eax; int
0x18000c402  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000c407  test    rdi, rdi
0x18000c40a  jz      short loc_18000C415
0x18000c40c  mov     rcx, rdi; bstrString
0x18000c40f  call    cs:__imp_SysFreeString
0x18000c415  lea     rcx, [rsp+150h+pvarg]; pvarg
0x18000c41a  call    cs:__imp_VariantClear
0x18000c420  lea     rcx, [rsp+150h+var_130]; struct IXMLDOMNode **
0x18000c425  call    ?ReleaseDomNode@@YAXPEAPEAUIXMLDOMNode@@@Z; ReleaseDomNode(IXMLDOMNode * *)
0x18000c42a  lea     rcx, [rsp+150h+var_108]; struct IXMLDOMNode **
0x18000c42f  call    ?ReleaseDomNode@@YAXPEAPEAUIXMLDOMNode@@@Z; ReleaseDomNode(IXMLDOMNode * *)
0x18000c434  mov     eax, ebx
0x18000c436  mov     rcx, [rbp+50h+var_30]
0x18000c43a  xor     rcx, rsp; StackCookie
0x18000c43d  call    __security_check_cookie
0x18000c442  add     rsp, 138h
0x18000c449  pop     rdi
0x18000c44a  pop     rsi
0x18000c44b  pop     rbx
0x18000c44c  pop     rbp
0x18000c44d  retn
```
