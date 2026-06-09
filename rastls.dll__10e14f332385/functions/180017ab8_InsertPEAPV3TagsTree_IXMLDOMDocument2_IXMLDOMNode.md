# InsertPEAPV3TagsTree(IXMLDOMDocument2 * *,IXMLDOMNode * *)

- ea: `0x180017ab8`
- end: `0x180017ef6`
- name: `?InsertPEAPV3TagsTree@@YAKPEAPEAUIXMLDOMDocument2@@PEAPEAUIXMLDOMNode@@@Z`
- size: `1086`
- prototype: `unsigned int __fastcall(struct IXMLDOMDocument2 **, struct IXMLDOMNode **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001cbf0`

## callees

- `0x180004bd0`
- `0x180017ab8`
- `0x180017f00`
- `0x180017f60`
- `0x18005e7c8`
- `0x18007c010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180017af5`
- `OLEAUT32!__imp_SysAllocString` at `0x180017b21`
- `OLEAUT32!__imp_SysAllocString` at `0x180017ca5`
- `OLEAUT32!__imp_SysAllocString` at `0x180017cd1`
- `OLEAUT32!__imp_SysAllocString` at `0x180017af5`
- `OLEAUT32!__imp_SysAllocString` at `0x180017b21`
- `OLEAUT32!__imp_SysAllocString` at `0x180017ca5`
- `OLEAUT32!__imp_SysAllocString` at `0x180017cd1`
- `OLEAUT32!__imp_SysFreeString` at `0x180017ae8`
- `OLEAUT32!__imp_SysFreeString` at `0x180017c4c`
- `OLEAUT32!__imp_SysFreeString` at `0x180017c56`
- `OLEAUT32!__imp_SysFreeString` at `0x180017c9c`
- `OLEAUT32!__imp_SysFreeString` at `0x180017e7c`
- `OLEAUT32!__imp_SysFreeString` at `0x180017e86`
- `OLEAUT32!__imp_SysFreeString` at `0x180017ece`
- `OLEAUT32!__imp_SysFreeString` at `0x180017ae8`
- `OLEAUT32!__imp_SysFreeString` at `0x180017c4c`
- `OLEAUT32!__imp_SysFreeString` at `0x180017c56`
- `OLEAUT32!__imp_SysFreeString` at `0x180017c9c`
- `OLEAUT32!__imp_SysFreeString` at `0x180017e7c`
- `OLEAUT32!__imp_SysFreeString` at `0x180017e86`
- `OLEAUT32!__imp_SysFreeString` at `0x180017ece`
- `OLEAUT32!__imp_VariantInit` at `0x180017b45`
- `OLEAUT32!__imp_VariantInit` at `0x180017b6c`
- `OLEAUT32!__imp_VariantInit` at `0x180017cf5`
- `OLEAUT32!__imp_VariantInit` at `0x180017d5d`
- `OLEAUT32!__imp_VariantInit` at `0x180017b45`
- `OLEAUT32!__imp_VariantInit` at `0x180017b6c`
- `OLEAUT32!__imp_VariantInit` at `0x180017cf5`
- `OLEAUT32!__imp_VariantInit` at `0x180017d5d`
- `OLEAUT32!__imp_VariantClear` at `0x180017bbf`
- `OLEAUT32!__imp_VariantClear` at `0x180017bfe`
- `OLEAUT32!__imp_VariantClear` at `0x180017db0`
- `OLEAUT32!__imp_VariantClear` at `0x180017e24`
- `OLEAUT32!__imp_VariantClear` at `0x180017bbf`
- `OLEAUT32!__imp_VariantClear` at `0x180017bfe`
- `OLEAUT32!__imp_VariantClear` at `0x180017db0`
- `OLEAUT32!__imp_VariantClear` at `0x180017e24`

## string_xrefs

- `0x180017aee`: `http://www.microsoft.com/provisioning/MsPeapConnectionPropertiesV2`
- `0x180017c8d`: `http://www.microsoft.com/provisioning/MsPeapConnectionPropertiesV3`
- `0x180017b1a`: `PeapExtensionsV2`

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
0x180017ab8  mov     rax, rsp
0x180017abb  mov     [rax+8], rbx
0x180017abf  push    rbp
0x180017ac0  push    rsi
0x180017ac1  push    rdi
0x180017ac2  push    r12
0x180017ac4  push    r13
0x180017ac6  push    r14
0x180017ac8  push    r15
0x180017aca  lea     rbp, [rax-5Fh]
0x180017ace  sub     rsp, 0D0h
0x180017ad5  movaps  xmmword ptr [rax-48h], xmm6
0x180017ad9  mov     r14, rdx
0x180017adc  mov     r12, rcx
0x180017adf  xor     r13d, r13d
0x180017ae2  mov     [rbp+57h+var_A0], r13
0x180017ae6  xor     ecx, ecx; bstrString
0x180017ae8  call    cs:__imp_SysFreeString
0x180017aee  lea     rcx, aHttpWwwMicroso; "http://www.microsoft.com/provisioning/M"...
0x180017af5  call    cs:__imp_SysAllocString
0x180017afb  mov     rbx, rax
0x180017afe  mov     [rbp+57h+var_70], rax
0x180017b02  test    rax, rax
0x180017b05  jnz     short loc_180017B0D
0x180017b07  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180017b0d  xorps   xmm0, xmm0
0x180017b10  xor     eax, eax
0x180017b12  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180017b16  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180017b1a  lea     rcx, aPeapextensions_0; "PeapExtensionsV2"
0x180017b21  call    cs:__imp_SysAllocString
0x180017b27  mov     rdi, rax
0x180017b2a  mov     [rbp+57h+var_98], rax
0x180017b2e  test    rax, rax
0x180017b31  jnz     short loc_180017B39
0x180017b33  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180017b39  mov     [rbp+57h+var_68], r13
0x180017b3d  mov     [rbp+57h+bstrString], r13
0x180017b41  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180017b45  call    cs:__imp_VariantInit
0x180017b4b  mov     word ptr [rbp+57h+pvarg], r13w
0x180017b50  mov     r14, [r14]
0x180017b53  mov     rsi, [r12]
0x180017b57  mov     [rbp+57h+arg_10], r13
0x180017b5b  xorps   xmm0, xmm0
0x180017b5e  xor     eax, eax
0x180017b60  movups  xmmword ptr [rbp+57h+var_D0], xmm0
0x180017b64  mov     qword ptr [rbp+57h+var_D0+10h], rax
0x180017b68  lea     rcx, [rbp+57h+var_D0]; pvarg
0x180017b6c  call    cs:__imp_VariantInit
0x180017b72  mov     eax, 3
0x180017b77  mov     word ptr [rbp+57h+var_D0], ax
0x180017b7b  mov     dword ptr [rbp+57h+var_D0+8], 1
0x180017b82  movups  xmm0, xmmword ptr [rbp+57h+var_D0]
0x180017b86  movaps  [rbp+57h+var_90], xmm0
0x180017b8a  movsd   xmm1, qword ptr [rbp+57h+var_D0+10h]
0x180017b8f  movsd   [rbp+57h+var_80], xmm1
0x180017b94  mov     rax, [rsi]
0x180017b97  lea     rcx, [rbp+57h+arg_10]
0x180017b9b  mov     [rsp+100h+var_E0], rcx
0x180017ba0  mov     r9, rbx
0x180017ba3  mov     r8, rdi
0x180017ba6  lea     rdx, [rbp+57h+var_90]
0x180017baa  mov     rcx, rsi
0x180017bad  mov     rax, [rax+1C0h]
0x180017bb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017bb9  mov     esi, eax
0x180017bbb  lea     rcx, [rbp+57h+var_D0]; pvarg
0x180017bbf  call    cs:__imp_VariantClear
0x180017bc5  test    esi, esi
0x180017bc7  jnz     short loc_180017BE5
0x180017bc9  mov     rax, [r14]
0x180017bcc  lea     r8, [rbp+57h+var_A0]
0x180017bd0  mov     rdx, [rbp+57h+arg_10]
0x180017bd4  mov     rcx, r14
0x180017bd7  mov     rax, [rax+0A8h]
0x180017bde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017be3  mov     esi, eax
0x180017be5  mov     rcx, [rbp+57h+arg_10]
0x180017be9  test    rcx, rcx
0x180017bec  jz      short loc_180017BFA
0x180017bee  mov     rax, [rcx]
0x180017bf1  mov     rax, [rax+10h]
0x180017bf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017bfa  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180017bfe  call    cs:__imp_VariantClear
0x180017c04  lea     r14, WPP_GLOBAL_Control
0x180017c0b  test    esi, esi
0x180017c0d  jz      short loc_180017C34
0x180017c0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180017c16  cmp     rcx, r14
0x180017c19  jz      short loc_180017C34
0x180017c1b  mov     edx, 45h ; 'E'
0x180017c20  mov     r9d, esi
0x180017c23  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180017c2a  mov     rcx, [rcx+10h]
0x180017c2e  call    WPP_SF_d
0x180017c33  nop
0x180017c34  mov     rcx, [rbp+57h+bstrString]
0x180017c38  test    rcx, rcx
0x180017c3b  jz      short loc_180017C4A
0x180017c3d  mov     rax, [rcx]
0x180017c40  mov     rax, [rax+10h]
0x180017c44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c49  nop
0x180017c4a  xor     ecx, ecx; bstrString
0x180017c4c  call    cs:__imp_SysFreeString
0x180017c52  nop
0x180017c53  mov     rcx, rdi; bstrString
0x180017c56  call    cs:__imp_SysFreeString
0x180017c5c  test    esi, esi
0x180017c5e  jz      short loc_180017C8D
0x180017c60  mov     rcx, cs:WPP_GLOBAL_Control
0x180017c67  cmp     rcx, r14
0x180017c6a  jz      loc_180017EB5
0x180017c70  mov     edx, 5Ch ; '\'
0x180017c75  mov     r9d, esi
0x180017c78  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180017c7f  mov     rcx, [rcx+10h]
0x180017c83  call    WPP_SF_d
0x180017c88  jmp     loc_180017EB5
0x180017c8d  lea     rdi, aHttpWwwMicroso_0; "http://www.microsoft.com/provisioning/M"...
0x180017c94  cmp     rdi, rbx
0x180017c97  jz      short loc_180017CBD
0x180017c99  mov     rcx, rbx; bstrString
0x180017c9c  call    cs:__imp_SysFreeString
0x180017ca2  mov     rcx, rdi; psz
0x180017ca5  call    cs:__imp_SysAllocString
0x180017cab  mov     rbx, rax
0x180017cae  mov     [rbp+57h+var_70], rax
0x180017cb2  test    rax, rax
0x180017cb5  jnz     short loc_180017CBD
0x180017cb7  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180017cbd  xorps   xmm0, xmm0
0x180017cc0  xor     eax, eax
0x180017cc2  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180017cc6  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180017cca  lea     rcx, aAllowprompting; "AllowPromptingWhenServerCANotFound"
0x180017cd1  call    cs:__imp_SysAllocString
0x180017cd7  mov     rdi, rax
0x180017cda  mov     [rbp+57h+var_68], rax
0x180017cde  test    rax, rax
0x180017ce1  jnz     short loc_180017CE9
0x180017ce3  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180017ce9  mov     [rbp+57h+bstrString], r13
0x180017ced  mov     [rbp+57h+var_98], r13
0x180017cf1  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180017cf5  call    cs:__imp_VariantInit
0x180017cfb  mov     word ptr [rbp+57h+pvarg], r13w
0x180017d00  lea     rdx, String2; "true"
0x180017d07  lea     rcx, [rbp+57h+bstrString]
0x180017d0b  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x180017d10  mov     rdx, [rbp+57h+bstrString]; unsigned __int16 *
0x180017d14  lea     rcx, [rbp+57h+var_60]; retstr
0x180017d18  call    ?StringtoVariant@@YA?AUtagVARIANT@@PEAG@Z; StringtoVariant(ushort *)
0x180017d1d  movups  xmm0, xmmword ptr [rax]
0x180017d20  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180017d24  movsd   xmm6, qword ptr [rax+10h]
0x180017d29  movsd   qword ptr [rbp+57h+pvarg+10h], xmm6
0x180017d2e  movd    r14d, xmm0
0x180017d33  mov     r15, [rbp+57h+var_A0]
0x180017d37  mov     rsi, [r12]
0x180017d3b  mov     [rbp+57h+arg_10], r13
0x180017d3f  movups  xmm0, xmmword ptr [rbp+57h+pvarg+2]
0x180017d43  movups  xmmword ptr [rbp+57h+var_60+2], xmm0
0x180017d47  movsd   qword ptr [rbp+57h+var_60+10h], xmm6
0x180017d4c  xorps   xmm0, xmm0
0x180017d4f  xor     eax, eax
0x180017d51  movups  xmmword ptr [rbp+57h+var_D0], xmm0
0x180017d55  mov     qword ptr [rbp+57h+var_D0+10h], rax
0x180017d59  lea     rcx, [rbp+57h+var_D0]; pvarg
0x180017d5d  call    cs:__imp_VariantInit
0x180017d63  mov     eax, 3
0x180017d68  mov     word ptr [rbp+57h+var_D0], ax
0x180017d6c  mov     dword ptr [rbp+57h+var_D0+8], 1
0x180017d73  movups  xmm0, xmmword ptr [rbp+57h+var_D0]
0x180017d77  movaps  [rbp+57h+var_90], xmm0
0x180017d7b  movsd   xmm1, qword ptr [rbp+57h+var_D0+10h]
0x180017d80  movsd   [rbp+57h+var_80], xmm1
0x180017d85  mov     rax, [rsi]
0x180017d88  lea     rcx, [rbp+57h+arg_10]
0x180017d8c  mov     [rsp+100h+var_E0], rcx
0x180017d91  mov     r9, rbx
0x180017d94  mov     r8, rdi
0x180017d97  lea     rdx, [rbp+57h+var_90]
0x180017d9b  mov     rcx, rsi
0x180017d9e  mov     rax, [rax+1C0h]
0x180017da5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017daa  mov     esi, eax
0x180017dac  lea     rcx, [rbp+57h+var_D0]; pvarg
0x180017db0  call    cs:__imp_VariantClear
0x180017db6  test    esi, esi
0x180017db8  jnz     short loc_180017E0B
0x180017dba  test    r14w, r14w
0x180017dbe  jz      short loc_180017DEF
0x180017dc0  mov     rcx, [rbp+57h+arg_10]
0x180017dc4  mov     word ptr [rbp+57h+var_90], r14w
0x180017dc9  movups  xmm0, xmmword ptr [rbp+57h+var_60+2]
0x180017dcd  movups  [rbp+57h+var_90+2], xmm0
0x180017dd1  movsd   [rbp+57h+var_80], xmm6
0x180017dd6  mov     rax, [rcx]
0x180017dd9  lea     rdx, [rbp+57h+var_90]
0x180017ddd  mov     rax, [rax+0F8h]
0x180017de4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017de9  mov     esi, eax
0x180017deb  test    eax, eax
0x180017ded  jnz     short loc_180017E0B
0x180017def  mov     rax, [r15]
0x180017df2  lea     r8, [rbp+57h+var_98]
0x180017df6  mov     rdx, [rbp+57h+arg_10]
0x180017dfa  mov     rcx, r15
0x180017dfd  mov     rax, [rax+0A8h]
0x180017e04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e09  mov     esi, eax
0x180017e0b  mov     rcx, [rbp+57h+arg_10]
0x180017e0f  test    rcx, rcx
0x180017e12  jz      short loc_180017E20
0x180017e14  mov     rax, [rcx]
0x180017e17  mov     rax, [rax+10h]
0x180017e1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e20  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180017e24  call    cs:__imp_VariantClear
0x180017e2a  test    esi, esi
0x180017e2c  jz      short loc_180017E5B
0x180017e2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180017e35  lea     r14, WPP_GLOBAL_Control
0x180017e3c  cmp     rcx, r14
0x180017e3f  jz      short loc_180017E62
0x180017e41  mov     edx, 45h ; 'E'
0x180017e46  mov     r9d, esi
0x180017e49  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180017e50  mov     rcx, [rcx+10h]
0x180017e54  call    WPP_SF_d
0x180017e59  jmp     short loc_180017E62
0x180017e5b  lea     r14, WPP_GLOBAL_Control
0x180017e62  mov     rcx, [rbp+57h+var_98]
0x180017e66  test    rcx, rcx
0x180017e69  jz      short loc_180017E78
0x180017e6b  mov     rax, [rcx]
0x180017e6e  mov     rax, [rax+10h]
0x180017e72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e77  nop
0x180017e78  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180017e7c  call    cs:__imp_SysFreeString
0x180017e82  nop
0x180017e83  mov     rcx, rdi; bstrString
0x180017e86  call    cs:__imp_SysFreeString
0x180017e8c  test    esi, esi
0x180017e8e  jz      short loc_180017EB5
0x180017e90  mov     rcx, cs:WPP_GLOBAL_Control
0x180017e97  cmp     rcx, r14
0x180017e9a  jz      short loc_180017EB5
0x180017e9c  mov     edx, 5Dh ; ']'
0x180017ea1  mov     r9d, esi
0x180017ea4  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180017eab  mov     rcx, [rcx+10h]
0x180017eaf  call    WPP_SF_d
0x180017eb4  nop
0x180017eb5  mov     rcx, [rbp+57h+var_A0]
0x180017eb9  test    rcx, rcx
0x180017ebc  jz      short loc_180017ECB
0x180017ebe  mov     rdx, [rcx]
0x180017ec1  mov     rax, [rdx+10h]
0x180017ec5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017eca  nop
0x180017ecb  mov     rcx, rbx; bstrString
0x180017ece  call    cs:__imp_SysFreeString
0x180017ed4  mov     eax, esi
0x180017ed6  lea     r11, [rsp+100h+var_30]
0x180017ede  mov     rbx, [r11+40h]
0x180017ee2  movaps  xmm6, xmmword ptr [r11-10h]
0x180017ee7  mov     rsp, r11
0x180017eea  pop     r15
0x180017eec  pop     r14
0x180017eee  pop     r13
0x180017ef0  pop     r12
0x180017ef2  pop     rdi
0x180017ef3  pop     rsi
0x180017ef4  pop     rbp
0x180017ef5  retn
```
