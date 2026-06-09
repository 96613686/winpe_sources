# CConfigPolicy::AdjustMeritOrderingHelper(_com_ptr_t<_com_IIID<SDOIASLib::ISdo,&__s_GUID const _GUID_56bc53de_96db_11d1_bf3f_000000000000>>,_com_ptr_t<_com_IIID<SDOIASLib::ISdo,&__s_GUID const _GUID_56bc53de_96db_11d1_bf3f_000000000000>>,long,long)

- ea: `0x180039524`
- end: `0x1800397ac`
- name: `?AdjustMeritOrderingHelper@CConfigPolicy@@AEAAJV?$_com_ptr_t@V?$_com_IIID@UISdo@SDOIASLib@@$1?_GUID_56bc53de_96db_11d1_bf3f_000000000000@@3U__s_GUID@@B@@@@0JJ@Z`
- size: `648`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *, int, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800391e4`

## callees

- `0x180039524`
- `0x18003b954`
- `0x18003c6d0`
- `0x18003edbc`
- `0x180050dbc`
- `0x180050e4c`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18003956a`
- `OLEAUT32!__imp_VariantInit` at `0x18003956a`
- `OLEAUT32!__imp_VariantClear` at `0x1800395c1`
- `OLEAUT32!__imp_VariantClear` at `0x180039728`
- `OLEAUT32!__imp_VariantClear` at `0x1800395c1`
- `OLEAUT32!__imp_VariantClear` at `0x180039728`
- `OLEAUT32!__imp_VariantCopy` at `0x1800395ae`
- `OLEAUT32!__imp_VariantCopy` at `0x1800395ae`

## string_xrefs

- `0x180039601`: `CConfigPolicy::AdjustMeritOrderingHelper(): Received an invalid data type for the Policy's merit value!`
- `0x180039687`: `CConfigPolicy::AdjustMeritOrderingHelper(): Error %lx Couldn't determine the new Merit value!`
- `0x1800396ec`: `CConfigPolicy::AdjustMeritOrderingHelper(): Error %lx Couldn't save new Merit value to the Policy!`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CConfigPolicy::AdjustMeritOrderingHelper(__int64 a1, _QWORD *a2, _QWORD *a3, int a4, int a5)
{
  const VARIANTARG *Property; // rax
  HRESULT v9; // eax
  HRESULT v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // rdx
  const wchar_t *v13; // r8
  __int64 v14; // rcx
  __int64 v15; // rcx
  int NewMeritValue; // eax
  const wchar_t *v17; // rdx
  __int128 v18; // xmm6
  __int64 v19; // xmm7_8
  __int64 v20; // rcx
  HRESULT v21; // eax
  int v23[2]; // [rsp+38h] [rbp-D0h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v25; // [rsp+58h] [rbp-B0h]
  VARIANTARG v26; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v27; // [rsp+78h] [rbp-90h]
  _QWORD *v28; // [rsp+88h] [rbp-80h]
  _QWORD *v29; // [rsp+90h] [rbp-78h]
  int v30; // [rsp+98h] [rbp-70h] BYREF
  _BYTE v31[2044]; // [rsp+9Ch] [rbp-6Ch] BYREF

  v28 = a2;
  v29 = a3;
  VariantInit((VARIANTARG *)&pvarg.decVal.8);
  v30 = 0;
  memset_0(v31, 0, sizeof(v31));
  if ( !*a2 )
    _com_issue_error(-2147467261);
  Property = (const VARIANTARG *)SDOIASLib::ISdo::GetProperty(*a2, &v26.decVal.Lo32, 1025);
  v9 = VariantCopy((VARIANTARG *)&pvarg.decVal.8, Property);
  if ( v9 < 0 )
    _com_issue_error(v9);
  v10 = VariantClear((VARIANTARG *)&v26.decVal.8);
  if ( v10 < 0 )
    _com_issue_error(v10);
  if ( pvarg.iVal == 3 || !pvarg.iVal )
  {
    v14 = *a3;
    *(_QWORD *)&pvarg.vt = v14;
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
    v15 = *a2;
    *(_QWORD *)v23 = v15;
    if ( v15 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
    NewMeritValue = CConfigPolicy::GetNewMeritValue(v15, (int)v23, (int)&pvarg, a4, a5, (VARIANTARG *)&pvarg.decVal.8);
    v11 = NewMeritValue;
    if ( NewMeritValue >= 0 )
    {
      v18 = *(_OWORD *)&pvarg.decVal.Lo32;
      v19 = v25;
      v20 = *a2;
      *(_QWORD *)v23 = v20;
      if ( v20 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 8LL))(v20);
      *(_OWORD *)&v26.decVal.Lo32 = v18;
      v27 = v19;
      NewMeritValue = PutSdoProperty(v23, 1025, &v26.decVal.Lo32);
      v11 = NewMeritValue;
      if ( NewMeritValue >= 0 || !gIsSdoUtilEtwTracingAvailable || !(_QWORD)xmmword_180078BA0 )
        goto LABEL_25;
      v17 = L"CConfigPolicy::AdjustMeritOrderingHelper(): Error %lx Couldn't save new Merit value to the Policy!";
    }
    else
    {
      if ( !gIsSdoUtilEtwTracingAvailable || !(_QWORD)xmmword_180078BA0 )
        goto LABEL_25;
      v17 = L"CConfigPolicy::AdjustMeritOrderingHelper(): Error %lx Couldn't determine the new Merit value!";
    }
    LOWORD(v30) = 0;
    FormatRRASErrorString(&v30, v17, (unsigned int)NewMeritValue);
    v12 = xmmword_180078BA0;
    v13 = (const wchar_t *)&v30;
    goto LABEL_24;
  }
  v11 = -2147023092;
  if ( gIsSdoUtilEtwTracingAvailable )
  {
    v12 = xmmword_180078BA0;
    if ( (_QWORD)xmmword_180078BA0 )
    {
      v13 = L"CConfigPolicy::AdjustMeritOrderingHelper(): Received an invalid data type for the Policy's merit value!";
LABEL_24:
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, __int64, const wchar_t *))gSdoUtilTemplateFunc)(
        gSdoUtilEtwContext,
        v12,
        v13);
    }
  }
LABEL_25:
  v21 = VariantClear((VARIANTARG *)&pvarg.decVal.8);
  if ( v21 < 0 )
    _com_issue_error(v21);
  if ( *a2 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 16LL))(*a2);
  if ( *a3 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 16LL))(*a3);
  return v11;
}

```

## disassembly

```asm
0x180039524  mov     rax, rsp
0x180039527  push    rbp
0x180039528  push    rbx
0x180039529  push    rsi
0x18003952a  push    rdi
0x18003952b  push    r14
0x18003952d  lea     rbp, [rax-7E8h]
0x180039534  sub     rsp, 8C0h
0x18003953b  movaps  xmmword ptr [rax-38h], xmm6
0x18003953f  movaps  xmmword ptr [rax-48h], xmm7
0x180039543  mov     rax, cs:__security_cookie
0x18003954a  xor     rax, rsp
0x18003954d  mov     [rbp+7E0h+var_50], rax
0x180039554  mov     ebx, r9d
0x180039557  mov     rsi, r8
0x18003955a  mov     rdi, rdx
0x18003955d  mov     [rbp+7E0h+var_860], rdx
0x180039561  mov     [rbp+7E0h+var_858], r8
0x180039565  lea     rcx, [rsp+8E0h+pvarg+8]; pvarg
0x18003956a  call    cs:__imp_VariantInit
0x180039570  nop
0x180039571  xor     r14d, r14d
0x180039574  mov     [rbp+7E0h+var_850], r14d
0x180039578  xor     edx, edx; Val
0x18003957a  mov     r8d, 7FCh; Size
0x180039580  lea     rcx, [rbp+7E0h+var_84C]; void *
0x180039584  call    memset_0
0x180039589  mov     rcx, [rdi]
0x18003958c  test    rcx, rcx
0x18003958f  jz      loc_180039791
0x180039595  mov     r8d, 401h
0x18003959b  lea     rdx, [rsp+8E0h+var_888+8]
0x1800395a0  call    ?GetProperty@ISdo@SDOIASLib@@QEAA?AV_variant_t@@J@Z; SDOIASLib::ISdo::GetProperty(long)
0x1800395a5  nop
0x1800395a6  mov     rdx, rax; pvargSrc
0x1800395a9  lea     rcx, [rsp+8E0h+pvarg+8]; pvargDest
0x1800395ae  call    cs:__imp_VariantCopy
0x1800395b4  test    eax, eax
0x1800395b6  js      loc_18003979C
0x1800395bc  lea     rcx, [rsp+8E0h+var_888+8]; pvarg
0x1800395c1  call    cs:__imp_VariantClear
0x1800395c7  test    eax, eax
0x1800395c9  js      loc_1800397A4
0x1800395cf  movzx   eax, word ptr [rsp+8E0h+pvarg+8]
0x1800395d4  cmp     ax, 3
0x1800395d8  jz      short loc_18003960D
0x1800395da  test    ax, ax
0x1800395dd  jz      short loc_18003960D
0x1800395df  mov     ebx, 8007070Ch
0x1800395e4  cmp     cs:?gIsSdoUtilEtwTracingAvailable@@3HA, r14d; int gIsSdoUtilEtwTracingAvailable
0x1800395eb  jz      loc_180039723
0x1800395f1  mov     rdx, qword ptr cs:xmmword_180078BA0
0x1800395f8  test    rdx, rdx
0x1800395fb  jz      loc_180039723
0x180039601  lea     r8, aCconfigpolicyA_13; "CConfigPolicy::AdjustMeritOrderingHelpe"...
0x180039608  jmp     loc_18003970F
0x18003960d  mov     rcx, [rsi]
0x180039610  mov     qword ptr [rsp+8E0h+pvarg], rcx
0x180039615  test    rcx, rcx
0x180039618  jz      short loc_180039627
0x18003961a  mov     rax, [rcx]
0x18003961d  mov     rax, [rax+8]
0x180039621  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039626  nop
0x180039627  mov     rcx, [rdi]
0x18003962a  mov     qword ptr [rsp+8E0h+var_8B0], rcx
0x18003962f  test    rcx, rcx
0x180039632  jz      short loc_180039641
0x180039634  mov     rax, [rcx]
0x180039637  mov     rax, [rax+8]
0x18003963b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039640  nop
0x180039641  lea     rax, [rsp+8E0h+pvarg+8]
0x180039646  mov     [rsp+8E0h+var_8B8], rax; pvarg
0x18003964b  mov     eax, [rbp+7E0h+arg_20]
0x180039651  mov     [rsp+8E0h+var_8C0], eax; int
0x180039655  mov     r9d, ebx; int
0x180039658  lea     r8, [rsp+8E0h+pvarg]; int
0x18003965d  lea     rdx, [rsp+8E0h+var_8B0]; int
0x180039662  call    ?GetNewMeritValue@CConfigPolicy@@AEAAJV?$_com_ptr_t@V?$_com_IIID@UISdo@SDOIASLib@@$1?_GUID_56bc53de_96db_11d1_bf3f_000000000000@@3U__s_GUID@@B@@@@0JJAEAV_variant_t@@@Z; CConfigPolicy::GetNewMeritValue(_com_ptr_t<_com_IIID<SDOIASLib::ISdo,&__s_GUID const _GUID_56bc53de_96db_11d1_bf3f_000000000000>>,_com_ptr_t<_com_IIID<SDOIASLib::ISdo,&__s_GUID const _GUID_56bc53de_96db_11d1_bf3f_000000000000>>,long,long,_variant_t &)
0x180039667  mov     ebx, eax
0x180039669  test    eax, eax
0x18003966b  jns     short loc_180039690
0x18003966d  cmp     cs:?gIsSdoUtilEtwTracingAvailable@@3HA, r14d; int gIsSdoUtilEtwTracingAvailable
0x180039674  jz      loc_180039723
0x18003967a  cmp     qword ptr cs:xmmword_180078BA0, r14
0x180039681  jz      loc_180039723
0x180039687  lea     rdx, aCconfigpolicyA_12; "CConfigPolicy::AdjustMeritOrderingHelpe"...
0x18003968e  jmp     short loc_1800396F3
0x180039690  movups  xmm6, xmmword ptr [rsp+8E0h+pvarg+8]
0x180039695  movsd   xmm7, [rsp+8E0h+var_890]
0x18003969b  mov     rcx, [rdi]
0x18003969e  mov     qword ptr [rsp+8E0h+var_8B0], rcx
0x1800396a3  test    rcx, rcx
0x1800396a6  jz      short loc_1800396B5
0x1800396a8  mov     rax, [rcx]
0x1800396ab  mov     rax, [rax+8]
0x1800396af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800396b4  nop
0x1800396b5  movaps  xmmword ptr [rsp+8E0h+var_888+8], xmm6
0x1800396ba  movsd   [rsp+8E0h+var_870], xmm7
0x1800396c0  lea     r8, [rsp+8E0h+var_888+8]
0x1800396c5  mov     edx, 401h
0x1800396ca  lea     rcx, [rsp+8E0h+var_8B0]
0x1800396cf  call    ?PutSdoProperty@@YAJV?$_com_ptr_t@V?$_com_IIID@UISdo@SDOIASLib@@$1?_GUID_56bc53de_96db_11d1_bf3f_000000000000@@3U__s_GUID@@B@@@@JUtagVARIANT@@@Z; PutSdoProperty(_com_ptr_t<_com_IIID<SDOIASLib::ISdo,&__s_GUID const _GUID_56bc53de_96db_11d1_bf3f_000000000000>>,long,tagVARIANT)
0x1800396d4  mov     ebx, eax
0x1800396d6  test    eax, eax
0x1800396d8  jns     short loc_180039723
0x1800396da  cmp     cs:?gIsSdoUtilEtwTracingAvailable@@3HA, r14d; int gIsSdoUtilEtwTracingAvailable
0x1800396e1  jz      short loc_180039723
0x1800396e3  cmp     qword ptr cs:xmmword_180078BA0, r14
0x1800396ea  jz      short loc_180039723
0x1800396ec  lea     rdx, aCconfigpolicyA_2; "CConfigPolicy::AdjustMeritOrderingHelpe"...
0x1800396f3  mov     word ptr [rbp+7E0h+var_850], r14w
0x1800396f8  mov     r8d, eax
0x1800396fb  lea     rcx, [rbp+7E0h+var_850]
0x1800396ff  call    FormatRRASErrorString
0x180039704  mov     rdx, qword ptr cs:xmmword_180078BA0
0x18003970b  lea     r8, [rbp+7E0h+var_850]
0x18003970f  mov     rcx, cs:?gSdoUtilEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gSdoUtilEtwContext
0x180039716  mov     rax, cs:?gSdoUtilTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gSdoUtilTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18003971d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039722  nop
0x180039723  lea     rcx, [rsp+8E0h+pvarg+8]; pvarg
0x180039728  call    cs:__imp_VariantClear
0x18003972e  test    eax, eax
0x180039730  js      short loc_180039789
0x180039732  mov     rcx, [rdi]
0x180039735  test    rcx, rcx
0x180039738  jz      short loc_180039747
0x18003973a  mov     rax, [rcx]
0x18003973d  mov     rax, [rax+10h]
0x180039741  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039746  nop
0x180039747  mov     rcx, [rsi]
0x18003974a  test    rcx, rcx
0x18003974d  jz      short loc_18003975C
0x18003974f  mov     rax, [rcx]
0x180039752  mov     rax, [rax+10h]
0x180039756  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003975b  nop
0x18003975c  mov     eax, ebx
0x18003975e  mov     rcx, [rbp+7E0h+var_50]
0x180039765  xor     rcx, rsp; StackCookie
0x180039768  call    __security_check_cookie
0x18003976d  lea     r11, [rsp+8E0h+var_20]
0x180039775  movaps  xmm6, xmmword ptr [r11-10h]
0x18003977a  movaps  xmm7, xmmword ptr [r11-20h]
0x18003977f  mov     rsp, r11
0x180039782  pop     r14
0x180039784  pop     rdi
0x180039785  pop     rsi
0x180039786  pop     rbx
0x180039787  pop     rbp
0x180039788  retn
0x180039789  mov     ecx, eax; int
0x18003978b  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180039791  mov     ecx, 80004003h; int
0x180039796  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18003979c  mov     ecx, eax; int
0x18003979e  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1800397a4  mov     ecx, eax; int
0x1800397a6  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
