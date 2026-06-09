# InsertPEAPV3TagsTree(IXMLDOMDocument2 * *,IXMLDOMNode * *)

- ea: `0x180019274`
- end: `0x180019725`
- name: `?InsertPEAPV3TagsTree@@YAKPEAPEAUIXMLDOMDocument2@@PEAPEAUIXMLDOMNode@@@Z`
- size: `1201`
- prototype: `unsigned int __fastcall(struct IXMLDOMDocument2 **, struct IXMLDOMNode **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001e680`

## callees

- `0x180005010`
- `0x180019274`
- `0x180019730`
- `0x1800197a0`
- `0x180061f9c`
- `0x180082010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800192b7`
- `OLEAUT32!__imp_SysAllocString` at `0x1800192e9`
- `OLEAUT32!__imp_SysAllocString` at `0x18001949d`
- `OLEAUT32!__imp_SysAllocString` at `0x1800194cf`
- `OLEAUT32!__imp_SysAllocString` at `0x1800192b7`
- `OLEAUT32!__imp_SysAllocString` at `0x1800192e9`
- `OLEAUT32!__imp_SysAllocString` at `0x18001949d`
- `OLEAUT32!__imp_SysAllocString` at `0x1800194cf`
- `OLEAUT32!__imp_SysFreeString` at `0x1800192a4`
- `OLEAUT32!__imp_SysFreeString` at `0x180019432`
- `OLEAUT32!__imp_SysFreeString` at `0x180019442`
- `OLEAUT32!__imp_SysFreeString` at `0x18001948e`
- `OLEAUT32!__imp_SysFreeString` at `0x180019698`
- `OLEAUT32!__imp_SysFreeString` at `0x1800196a8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800196f6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800192a4`
- `OLEAUT32!__imp_SysFreeString` at `0x180019432`
- `OLEAUT32!__imp_SysFreeString` at `0x180019442`
- `OLEAUT32!__imp_SysFreeString` at `0x18001948e`
- `OLEAUT32!__imp_SysFreeString` at `0x180019698`
- `OLEAUT32!__imp_SysFreeString` at `0x1800196a8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800196f6`
- `OLEAUT32!__imp_VariantInit` at `0x180019313`
- `OLEAUT32!__imp_VariantInit` at `0x180019340`
- `OLEAUT32!__imp_VariantInit` at `0x1800194f9`
- `OLEAUT32!__imp_VariantInit` at `0x180019567`
- `OLEAUT32!__imp_VariantInit` at `0x180019313`
- `OLEAUT32!__imp_VariantInit` at `0x180019340`
- `OLEAUT32!__imp_VariantInit` at `0x1800194f9`
- `OLEAUT32!__imp_VariantInit` at `0x180019567`
- `OLEAUT32!__imp_VariantClear` at `0x180019399`
- `OLEAUT32!__imp_VariantClear` at `0x1800193de`
- `OLEAUT32!__imp_VariantClear` at `0x1800195c0`
- `OLEAUT32!__imp_VariantClear` at `0x18001963a`
- `OLEAUT32!__imp_VariantClear` at `0x180019399`
- `OLEAUT32!__imp_VariantClear` at `0x1800193de`
- `OLEAUT32!__imp_VariantClear` at `0x1800195c0`
- `OLEAUT32!__imp_VariantClear` at `0x18001963a`

## string_xrefs

- `0x1800192b0`: `http://www.microsoft.com/provisioning/MsPeapConnectionPropertiesV2`
- `0x18001947f`: `http://www.microsoft.com/provisioning/MsPeapConnectionPropertiesV3`
- `0x1800192e2`: `PeapExtensionsV2`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall InsertPEAPV3TagsTree(struct IXMLDOMDocument2 **a1, struct IXMLDOMNode **a2)
{
  int v4; // ecx
  OLECHAR *v5; // rbx
  int v6; // ecx
  OLECHAR *v7; // rdi
  __int64 v8; // r14
  __int64 v9; // rsi
  unsigned int v10; // esi
  int v11; // ecx
  int v12; // ecx
  OLECHAR *v13; // rdi
  struct tagVARIANT *v14; // rax
  IRecordInfo *pRecInfo; // xmm6_8
  VARTYPE v16; // r14
  __int64 v17; // r15
  __int64 v18; // rsi
  VARIANTARG v20; // [rsp+38h] [rbp-79h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-61h] BYREF
  __int64 v22; // [rsp+68h] [rbp-49h] BYREF
  OLECHAR *v23; // [rsp+70h] [rbp-41h] BYREF
  VARIANTARG v24; // [rsp+78h] [rbp-39h] BYREF
  OLECHAR *v25; // [rsp+98h] [rbp-19h]
  OLECHAR *v26; // [rsp+A0h] [rbp-11h]
  struct tagVARIANT v27; // [rsp+A8h] [rbp-9h] BYREF
  __int64 v28; // [rsp+128h] [rbp+77h] BYREF
  BSTR bstrString; // [rsp+130h] [rbp+7Fh] BYREF

  v22 = 0;
  SysFreeString(0);
  v5 = SysAllocString(L"http://www.microsoft.com/provisioning/MsPeapConnectionPropertiesV2");
  v25 = v5;
  if ( !v5 )
    ATL::AtlThrowImpl(v4);
  memset(&pvarg, 0, sizeof(pvarg));
  v7 = SysAllocString(L"PeapExtensionsV2");
  v23 = v7;
  if ( !v7 )
    ATL::AtlThrowImpl(v6);
  v26 = 0;
  bstrString = 0;
  VariantInit(&pvarg);
  pvarg.vt = 0;
  v8 = (__int64)*a2;
  v9 = (__int64)*a1;
  v28 = 0;
  memset(&v20, 0, sizeof(v20));
  VariantInit(&v20);
  v20.vt = 3;
  v20.lVal = 1;
  v24 = v20;
  v10 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *, OLECHAR *, OLECHAR *, __int64 *))(*(_QWORD *)v9 + 448LL))(
          v9,
          &v24,
          v7,
          v5,
          &v28);
  VariantClear(&v20);
  if ( !v10 )
    v10 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v8 + 168LL))(v8, v28, &v22);
  if ( v28 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  VariantClear(&pvarg);
  if ( v10 && WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, v10);
  if ( bstrString )
    (*(void (__fastcall **)(BSTR))(*(_QWORD *)bstrString + 16LL))(bstrString);
  SysFreeString(0);
  SysFreeString(v7);
  if ( v10 )
  {
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, v10);
  }
  else
  {
    if ( L"http://www.microsoft.com/provisioning/MsPeapConnectionPropertiesV3" != v5 )
    {
      SysFreeString(v5);
      v5 = SysAllocString(L"http://www.microsoft.com/provisioning/MsPeapConnectionPropertiesV3");
      v25 = v5;
      if ( !v5 )
        ATL::AtlThrowImpl(v11);
    }
    memset(&pvarg, 0, sizeof(pvarg));
    v13 = SysAllocString(L"AllowPromptingWhenServerCANotFound");
    v26 = v13;
    if ( !v13 )
      ATL::AtlThrowImpl(v12);
    bstrString = 0;
    v23 = 0;
    VariantInit(&pvarg);
    pvarg.vt = 0;
    ATL::CComBSTR::operator=(&bstrString, L"true");
    v14 = StringtoVariant(&v27, bstrString);
    *(_OWORD *)&pvarg.vt = *(_OWORD *)&v14->vt;
    pRecInfo = v14->pRecInfo;
    pvarg.pRecInfo = pRecInfo;
    v16 = _mm_cvtsi128_si32(*(__m128i *)&pvarg.vt);
    v17 = v22;
    v18 = (__int64)*a1;
    v28 = 0;
    *(_OWORD *)&v27.decVal.scale = *(_OWORD *)&pvarg.decVal.scale;
    v27.pRecInfo = pRecInfo;
    memset(&v20, 0, sizeof(v20));
    VariantInit(&v20);
    v20.vt = 3;
    v20.lVal = 1;
    v24 = v20;
    v10 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *, OLECHAR *, OLECHAR *, __int64 *))(*(_QWORD *)v18 + 448LL))(
            v18,
            &v24,
            v13,
            v5,
            &v28);
    VariantClear(&v20);
    if ( !v10 )
    {
      if ( !v16
        || (v24.vt = v16,
            *(_OWORD *)&v24.decVal.scale = *(_OWORD *)&v27.decVal.scale,
            v24.pRecInfo = pRecInfo,
            (v10 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v28 + 248LL))(v28, &v24)) == 0) )
      {
        v10 = (*(__int64 (__fastcall **)(__int64, __int64, OLECHAR **))(*(_QWORD *)v17 + 168LL))(v17, v28, &v23);
      }
    }
    if ( v28 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    VariantClear(&pvarg);
    if ( v10 && WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, v10);
    if ( v23 )
      (*(void (__fastcall **)(OLECHAR *))(*(_QWORD *)v23 + 16LL))(v23);
    SysFreeString(bstrString);
    SysFreeString(v13);
    if ( v10 && WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, v10);
  }
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  SysFreeString(v5);
  return v10;
}

```

## disassembly

```asm
0x180019274  mov     rax, rsp
0x180019277  mov     [rax+8], rbx
0x18001927b  push    rbp
0x18001927c  push    rsi
0x18001927d  push    rdi
0x18001927e  push    r12
0x180019280  push    r13
0x180019282  push    r14
0x180019284  push    r15
0x180019286  lea     rbp, [rax-5Fh]
0x18001928a  sub     rsp, 0D0h
0x180019291  movaps  xmmword ptr [rax-48h], xmm6
0x180019295  mov     r14, rdx
0x180019298  mov     r12, rcx
0x18001929b  xor     r13d, r13d
0x18001929e  mov     [rbp+57h+var_A0], r13
0x1800192a2  xor     ecx, ecx; bstrString
0x1800192a4  call    cs:__imp_SysFreeString
0x1800192ab  nop     dword ptr [rax+rax+00h]
0x1800192b0  lea     rcx, aHttpWwwMicroso; "http://www.microsoft.com/provisioning/M"...
0x1800192b7  call    cs:__imp_SysAllocString
0x1800192be  nop     dword ptr [rax+rax+00h]
0x1800192c3  mov     rbx, rax
0x1800192c6  mov     [rbp+57h+var_70], rax
0x1800192ca  test    rax, rax
0x1800192cd  jnz     short loc_1800192D5
0x1800192cf  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800192d5  xorps   xmm0, xmm0
0x1800192d8  xor     eax, eax
0x1800192da  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x1800192de  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x1800192e2  lea     rcx, aPeapextensions_0; "PeapExtensionsV2"
0x1800192e9  call    cs:__imp_SysAllocString
0x1800192f0  nop     dword ptr [rax+rax+00h]
0x1800192f5  mov     rdi, rax
0x1800192f8  mov     [rbp+57h+var_98], rax
0x1800192fc  test    rax, rax
0x1800192ff  jnz     short loc_180019307
0x180019301  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180019307  mov     [rbp+57h+var_68], r13
0x18001930b  mov     [rbp+57h+bstrString], r13
0x18001930f  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180019313  call    cs:__imp_VariantInit
0x18001931a  nop     dword ptr [rax+rax+00h]
0x18001931f  mov     word ptr [rbp+57h+pvarg], r13w
0x180019324  mov     r14, [r14]
0x180019327  mov     rsi, [r12]
0x18001932b  mov     [rbp+57h+arg_10], r13
0x18001932f  xorps   xmm0, xmm0
0x180019332  xor     eax, eax
0x180019334  movups  xmmword ptr [rbp+57h+var_D0], xmm0
0x180019338  mov     qword ptr [rbp+57h+var_D0+10h], rax
0x18001933c  lea     rcx, [rbp+57h+var_D0]; pvarg
0x180019340  call    cs:__imp_VariantInit
0x180019347  nop     dword ptr [rax+rax+00h]
0x18001934c  mov     eax, 3
0x180019351  mov     word ptr [rbp+57h+var_D0], ax
0x180019355  mov     dword ptr [rbp+57h+var_D0+8], 1
0x18001935c  movups  xmm0, xmmword ptr [rbp+57h+var_D0]
0x180019360  movaps  [rbp+57h+var_90], xmm0
0x180019364  movsd   xmm1, qword ptr [rbp+57h+var_D0+10h]
0x180019369  movsd   [rbp+57h+var_80], xmm1
0x18001936e  mov     rax, [rsi]
0x180019371  lea     rcx, [rbp+57h+arg_10]
0x180019375  mov     [rsp+100h+var_E0], rcx
0x18001937a  mov     r9, rbx
0x18001937d  mov     r8, rdi
0x180019380  lea     rdx, [rbp+57h+var_90]
0x180019384  mov     rcx, rsi
0x180019387  mov     rax, [rax+1C0h]
0x18001938e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019393  mov     esi, eax
0x180019395  lea     rcx, [rbp+57h+var_D0]; pvarg
0x180019399  call    cs:__imp_VariantClear
0x1800193a0  nop     dword ptr [rax+rax+00h]
0x1800193a5  test    esi, esi
0x1800193a7  jnz     short loc_1800193C5
0x1800193a9  mov     rax, [r14]
0x1800193ac  lea     r8, [rbp+57h+var_A0]
0x1800193b0  mov     rdx, [rbp+57h+arg_10]
0x1800193b4  mov     rcx, r14
0x1800193b7  mov     rax, [rax+0A8h]
0x1800193be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800193c3  mov     esi, eax
0x1800193c5  mov     rcx, [rbp+57h+arg_10]
0x1800193c9  test    rcx, rcx
0x1800193cc  jz      short loc_1800193DA
0x1800193ce  mov     rax, [rcx]
0x1800193d1  mov     rax, [rax+10h]
0x1800193d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800193da  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800193de  call    cs:__imp_VariantClear
0x1800193e5  nop     dword ptr [rax+rax+00h]
0x1800193ea  lea     r14, WPP_GLOBAL_Control
0x1800193f1  test    esi, esi
0x1800193f3  jz      short loc_18001941A
0x1800193f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800193fc  cmp     rcx, r14
0x1800193ff  jz      short loc_18001941A
0x180019401  mov     edx, 45h ; 'E'
0x180019406  mov     r9d, esi
0x180019409  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180019410  mov     rcx, [rcx+10h]
0x180019414  call    WPP_SF_d
0x180019419  nop
0x18001941a  mov     rcx, [rbp+57h+bstrString]
0x18001941e  test    rcx, rcx
0x180019421  jz      short loc_180019430
0x180019423  mov     rax, [rcx]
0x180019426  mov     rax, [rax+10h]
0x18001942a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001942f  nop
0x180019430  xor     ecx, ecx; bstrString
0x180019432  call    cs:__imp_SysFreeString
0x180019439  nop     dword ptr [rax+rax+00h]
0x18001943e  nop
0x18001943f  mov     rcx, rdi; bstrString
0x180019442  call    cs:__imp_SysFreeString
0x180019449  nop     dword ptr [rax+rax+00h]
0x18001944e  test    esi, esi
0x180019450  jz      short loc_18001947F
0x180019452  mov     rcx, cs:WPP_GLOBAL_Control
0x180019459  cmp     rcx, r14
0x18001945c  jz      loc_1800196DD
0x180019462  mov     edx, 5Ch ; '\'
0x180019467  mov     r9d, esi
0x18001946a  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180019471  mov     rcx, [rcx+10h]
0x180019475  call    WPP_SF_d
0x18001947a  jmp     loc_1800196DD
0x18001947f  lea     rdi, aHttpWwwMicroso_0; "http://www.microsoft.com/provisioning/M"...
0x180019486  cmp     rdi, rbx
0x180019489  jz      short loc_1800194BB
0x18001948b  mov     rcx, rbx; bstrString
0x18001948e  call    cs:__imp_SysFreeString
0x180019495  nop     dword ptr [rax+rax+00h]
0x18001949a  mov     rcx, rdi; psz
0x18001949d  call    cs:__imp_SysAllocString
0x1800194a4  nop     dword ptr [rax+rax+00h]
0x1800194a9  mov     rbx, rax
0x1800194ac  mov     [rbp+57h+var_70], rax
0x1800194b0  test    rax, rax
0x1800194b3  jnz     short loc_1800194BB
0x1800194b5  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800194bb  xorps   xmm0, xmm0
0x1800194be  xor     eax, eax
0x1800194c0  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x1800194c4  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x1800194c8  lea     rcx, aAllowprompting; "AllowPromptingWhenServerCANotFound"
0x1800194cf  call    cs:__imp_SysAllocString
0x1800194d6  nop     dword ptr [rax+rax+00h]
0x1800194db  mov     rdi, rax
0x1800194de  mov     [rbp+57h+var_68], rax
0x1800194e2  test    rax, rax
0x1800194e5  jnz     short loc_1800194ED
0x1800194e7  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800194ed  mov     [rbp+57h+bstrString], r13
0x1800194f1  mov     [rbp+57h+var_98], r13
0x1800194f5  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800194f9  call    cs:__imp_VariantInit
0x180019500  nop     dword ptr [rax+rax+00h]
0x180019505  mov     word ptr [rbp+57h+pvarg], r13w
0x18001950a  lea     rdx, String2; "true"
0x180019511  lea     rcx, [rbp+57h+bstrString]
0x180019515  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18001951a  mov     rdx, [rbp+57h+bstrString]; unsigned __int16 *
0x18001951e  lea     rcx, [rbp+57h+var_60]; retstr
0x180019522  call    ?StringtoVariant@@YA?AUtagVARIANT@@PEAG@Z; StringtoVariant(ushort *)
0x180019527  movups  xmm0, xmmword ptr [rax]
0x18001952a  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18001952e  movsd   xmm6, qword ptr [rax+10h]
0x180019533  movsd   qword ptr [rbp+57h+pvarg+10h], xmm6
0x180019538  movd    r14d, xmm0
0x18001953d  mov     r15, [rbp+57h+var_A0]
0x180019541  mov     rsi, [r12]
0x180019545  mov     [rbp+57h+arg_10], r13
0x180019549  movups  xmm0, xmmword ptr [rbp+57h+pvarg+2]
0x18001954d  movups  xmmword ptr [rbp+57h+var_60+2], xmm0
0x180019551  movsd   qword ptr [rbp+57h+var_60+10h], xmm6
0x180019556  xorps   xmm0, xmm0
0x180019559  xor     eax, eax
0x18001955b  movups  xmmword ptr [rbp+57h+var_D0], xmm0
0x18001955f  mov     qword ptr [rbp+57h+var_D0+10h], rax
0x180019563  lea     rcx, [rbp+57h+var_D0]; pvarg
0x180019567  call    cs:__imp_VariantInit
0x18001956e  nop     dword ptr [rax+rax+00h]
0x180019573  mov     eax, 3
0x180019578  mov     word ptr [rbp+57h+var_D0], ax
0x18001957c  mov     dword ptr [rbp+57h+var_D0+8], 1
0x180019583  movups  xmm0, xmmword ptr [rbp+57h+var_D0]
0x180019587  movaps  [rbp+57h+var_90], xmm0
0x18001958b  movsd   xmm1, qword ptr [rbp+57h+var_D0+10h]
0x180019590  movsd   [rbp+57h+var_80], xmm1
0x180019595  mov     rax, [rsi]
0x180019598  lea     rcx, [rbp+57h+arg_10]
0x18001959c  mov     [rsp+100h+var_E0], rcx
0x1800195a1  mov     r9, rbx
0x1800195a4  mov     r8, rdi
0x1800195a7  lea     rdx, [rbp+57h+var_90]
0x1800195ab  mov     rcx, rsi
0x1800195ae  mov     rax, [rax+1C0h]
0x1800195b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800195ba  mov     esi, eax
0x1800195bc  lea     rcx, [rbp+57h+var_D0]; pvarg
0x1800195c0  call    cs:__imp_VariantClear
0x1800195c7  nop     dword ptr [rax+rax+00h]
0x1800195cc  test    esi, esi
0x1800195ce  jnz     short loc_180019621
0x1800195d0  test    r14w, r14w
0x1800195d4  jz      short loc_180019605
0x1800195d6  mov     rcx, [rbp+57h+arg_10]
0x1800195da  mov     word ptr [rbp+57h+var_90], r14w
0x1800195df  movups  xmm0, xmmword ptr [rbp+57h+var_60+2]
0x1800195e3  movups  [rbp+57h+var_90+2], xmm0
0x1800195e7  movsd   [rbp+57h+var_80], xmm6
0x1800195ec  mov     rax, [rcx]
0x1800195ef  lea     rdx, [rbp+57h+var_90]
0x1800195f3  mov     rax, [rax+0F8h]
0x1800195fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800195ff  mov     esi, eax
0x180019601  test    eax, eax
0x180019603  jnz     short loc_180019621
0x180019605  mov     rax, [r15]
0x180019608  lea     r8, [rbp+57h+var_98]
0x18001960c  mov     rdx, [rbp+57h+arg_10]
0x180019610  mov     rcx, r15
0x180019613  mov     rax, [rax+0A8h]
0x18001961a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001961f  mov     esi, eax
0x180019621  mov     rcx, [rbp+57h+arg_10]
0x180019625  test    rcx, rcx
0x180019628  jz      short loc_180019636
0x18001962a  mov     rax, [rcx]
0x18001962d  mov     rax, [rax+10h]
0x180019631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019636  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001963a  call    cs:__imp_VariantClear
0x180019641  nop     dword ptr [rax+rax+00h]
0x180019646  test    esi, esi
0x180019648  jz      short loc_180019677
0x18001964a  mov     rcx, cs:WPP_GLOBAL_Control
0x180019651  lea     r14, WPP_GLOBAL_Control
0x180019658  cmp     rcx, r14
0x18001965b  jz      short loc_18001967E
0x18001965d  mov     edx, 45h ; 'E'
0x180019662  mov     r9d, esi
0x180019665  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18001966c  mov     rcx, [rcx+10h]
0x180019670  call    WPP_SF_d
0x180019675  jmp     short loc_18001967E
0x180019677  lea     r14, WPP_GLOBAL_Control
0x18001967e  mov     rcx, [rbp+57h+var_98]
0x180019682  test    rcx, rcx
0x180019685  jz      short loc_180019694
0x180019687  mov     rax, [rcx]
0x18001968a  mov     rax, [rax+10h]
0x18001968e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019693  nop
0x180019694  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180019698  call    cs:__imp_SysFreeString
0x18001969f  nop     dword ptr [rax+rax+00h]
0x1800196a4  nop
0x1800196a5  mov     rcx, rdi; bstrString
0x1800196a8  call    cs:__imp_SysFreeString
0x1800196af  nop     dword ptr [rax+rax+00h]
0x1800196b4  test    esi, esi
0x1800196b6  jz      short loc_1800196DD
0x1800196b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800196bf  cmp     rcx, r14
0x1800196c2  jz      short loc_1800196DD
0x1800196c4  mov     edx, 5Dh ; ']'
0x1800196c9  mov     r9d, esi
0x1800196cc  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x1800196d3  mov     rcx, [rcx+10h]
0x1800196d7  call    WPP_SF_d
0x1800196dc  nop
0x1800196dd  mov     rcx, [rbp+57h+var_A0]
0x1800196e1  test    rcx, rcx
0x1800196e4  jz      short loc_1800196F3
0x1800196e6  mov     rdx, [rcx]
0x1800196e9  mov     rax, [rdx+10h]
0x1800196ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800196f2  nop
0x1800196f3  mov     rcx, rbx; bstrString
0x1800196f6  call    cs:__imp_SysFreeString
0x1800196fd  nop     dword ptr [rax+rax+00h]
0x180019702  mov     eax, esi
0x180019704  lea     r11, [rsp+100h+var_30]
0x18001970c  mov     rbx, [r11+40h]
0x180019710  movaps  xmm6, xmmword ptr [r11-10h]
0x180019715  mov     rsp, r11
0x180019718  pop     r15
0x18001971a  pop     r14
0x18001971c  pop     r13
0x18001971e  pop     r12
0x180019720  pop     rdi
0x180019721  pop     rsi
0x180019722  pop     rbp
0x180019723  retn
```
