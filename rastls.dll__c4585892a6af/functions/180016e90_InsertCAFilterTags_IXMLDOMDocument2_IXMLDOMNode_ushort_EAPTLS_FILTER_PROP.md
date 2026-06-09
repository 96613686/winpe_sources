# InsertCAFilterTags(IXMLDOMDocument2 * *,IXMLDOMNode * *,ushort *,_EAPTLS_FILTER_PROP *)

- ea: `0x180016e90`
- end: `0x180017468`
- name: `?InsertCAFilterTags@@YAKPEAPEAUIXMLDOMDocument2@@PEAPEAUIXMLDOMNode@@PEAGPEAU_EAPTLS_FILTER_PROP@@@Z`
- size: `1496`
- prototype: `unsigned int __fastcall(struct IXMLDOMDocument2 **, struct IXMLDOMNode **, unsigned __int16 *, struct _EAPTLS_FILTER_PROP *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800162e0`

## callees

- `0x180005010`
- `0x180016e90`
- `0x180017470`
- `0x180038270`
- `0x180038ee8`
- `0x180061f9c`
- `0x180082010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180016f0f`
- `OLEAUT32!__imp_SysAllocString` at `0x180017112`
- `OLEAUT32!__imp_SysAllocString` at `0x18001720f`
- `OLEAUT32!__imp_SysAllocString` at `0x18001724e`
- `OLEAUT32!__imp_SysAllocString` at `0x180016f0f`
- `OLEAUT32!__imp_SysAllocString` at `0x180017112`
- `OLEAUT32!__imp_SysAllocString` at `0x18001720f`
- `OLEAUT32!__imp_SysAllocString` at `0x18001724e`
- `OLEAUT32!__imp_SysFreeString` at `0x18001706c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001707c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800170ff`
- `OLEAUT32!__imp_SysFreeString` at `0x1800173ae`
- `OLEAUT32!__imp_SysFreeString` at `0x18001742e`
- `OLEAUT32!__imp_SysFreeString` at `0x18001706c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001707c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800170ff`
- `OLEAUT32!__imp_SysFreeString` at `0x1800173ae`
- `OLEAUT32!__imp_SysFreeString` at `0x18001742e`
- `OLEAUT32!__imp_VariantInit` at `0x180016f3a`
- `OLEAUT32!__imp_VariantInit` at `0x180016f70`
- `OLEAUT32!__imp_VariantInit` at `0x1800171ff`
- `OLEAUT32!__imp_VariantInit` at `0x18001723f`
- `OLEAUT32!__imp_VariantInit` at `0x1800172a3`
- `OLEAUT32!__imp_VariantInit` at `0x180016f3a`
- `OLEAUT32!__imp_VariantInit` at `0x180016f70`
- `OLEAUT32!__imp_VariantInit` at `0x1800171ff`
- `OLEAUT32!__imp_VariantInit` at `0x18001723f`
- `OLEAUT32!__imp_VariantInit` at `0x1800172a3`
- `OLEAUT32!__imp_VariantClear` at `0x180016fcf`
- `OLEAUT32!__imp_VariantClear` at `0x180017018`
- `OLEAUT32!__imp_VariantClear` at `0x180017303`
- `OLEAUT32!__imp_VariantClear` at `0x180017380`
- `OLEAUT32!__imp_VariantClear` at `0x180016fcf`
- `OLEAUT32!__imp_VariantClear` at `0x180017018`
- `OLEAUT32!__imp_VariantClear` at `0x180017303`
- `OLEAUT32!__imp_VariantClear` at `0x180017380`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall InsertCAFilterTags(
        struct IXMLDOMDocument2 **a1,
        struct IXMLDOMNode **a2,
        unsigned __int16 *a3,
        struct _EAPTLS_FILTER_PROP *a4)
{
  struct _EAPTLS_FILTER_PROP *v4; // r15
  OLECHAR *v8; // rdi
  int v9; // ecx
  OLECHAR *v10; // rbx
  __int64 v11; // r14
  struct IXMLDOMDocument2 *v12; // rsi
  unsigned int v13; // esi
  int v14; // edx
  unsigned __int16 *v15; // r8
  struct _EAPTLS_CONTROL_BLOCK *v16; // rcx
  __int64 v17; // rdx
  unsigned int AttributeWithBooleanValue; // eax
  int v19; // ecx
  unsigned __int16 i; // r12
  __int64 v21; // rsi
  __int64 v22; // rbx
  const wchar_t *v23; // r8
  OLECHAR *v24; // r14
  struct IXMLDOMDocument2 **v25; // r13
  IRecordInfo *pRecInfo; // xmm6_8
  struct IXMLDOMNode *v27; // r15
  struct IXMLDOMDocument2 *v28; // rbx
  __int64 v30; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v31; // [rsp+38h] [rbp-C8h] BYREF
  struct IXMLDOMNode *v32; // [rsp+40h] [rbp-C0h] BYREF
  VARIANTARG v33; // [rsp+48h] [rbp-B8h] BYREF
  VARIANTARG pvarg; // [rsp+60h] [rbp-A0h] BYREF
  VARIANTARG v35; // [rsp+80h] [rbp-80h] BYREF
  __int64 v36; // [rsp+A0h] [rbp-60h]
  OLECHAR *v37; // [rsp+A8h] [rbp-58h]
  struct IXMLDOMDocument2 **v38; // [rsp+B0h] [rbp-50h]
  unsigned __int16 *v39; // [rsp+B8h] [rbp-48h]
  struct _EAPTLS_FILTER_PROP *v40; // [rsp+C0h] [rbp-40h]
  VARIANTARG v41; // [rsp+C8h] [rbp-38h] BYREF
  OLECHAR *v42; // [rsp+E0h] [rbp-20h]
  __int64 v43; // [rsp+E8h] [rbp-18h]
  OLECHAR psz[4]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v45; // [rsp+F8h] [rbp-8h]
  __int64 v46; // [rsp+100h] [rbp+0h]
  __int64 v47; // [rsp+108h] [rbp+8h]
  __int64 v48; // [rsp+110h] [rbp+10h]
  __int64 v49; // [rsp+118h] [rbp+18h]
  __int64 v50; // [rsp+120h] [rbp+20h]
  __int64 v51; // [rsp+128h] [rbp+28h]
  __int64 v52; // [rsp+130h] [rbp+30h]
  __int64 v53; // [rsp+138h] [rbp+38h]
  __int64 v54; // [rsp+140h] [rbp+40h]
  __int64 v55; // [rsp+148h] [rbp+48h]
  __int64 v56; // [rsp+150h] [rbp+50h]
  __int64 v57; // [rsp+158h] [rbp+58h]
  __int64 v58; // [rsp+160h] [rbp+60h]
  __int64 v59; // [rsp+168h] [rbp+68h]
  __int64 v60; // [rsp+170h] [rbp+70h]
  __int64 v61; // [rsp+178h] [rbp+78h]
  __int64 v62; // [rsp+180h] [rbp+80h]
  __int64 v63; // [rsp+188h] [rbp+88h]
  __int64 v64; // [rsp+190h] [rbp+90h]

  v4 = a4;
  v40 = a4;
  v39 = a3;
  v38 = a1;
  v8 = 0;
  v37 = 0;
  memset(&v41, 0, sizeof(v41));
  v32 = 0;
  v31 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v10 = SysAllocString(L"CAHashList");
  v42 = v10;
  if ( !v10 )
    ATL::AtlThrowImpl(v9);
  v43 = 0;
  v36 = 0;
  VariantInit(&pvarg);
  pvarg.vt = 0;
  v11 = (__int64)*a2;
  v12 = *a1;
  v30 = 0;
  memset(&v33, 0, sizeof(v33));
  VariantInit(&v33);
  v33.vt = 3;
  v33.lVal = 1;
  v35 = v33;
  v13 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, VARIANTARG *, OLECHAR *, unsigned __int16 *, __int64 *))v12->lpVtbl->createNode)(
          v12,
          &v35,
          v10,
          a3,
          &v30);
  VariantClear(&v33);
  if ( !v13 )
    v13 = (*(__int64 (__fastcall **)(__int64, __int64, struct IXMLDOMNode **))(*(_QWORD *)v11 + 168LL))(v11, v30, &v32);
  if ( v30 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  VariantClear(&pvarg);
  if ( v13 && WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, v13);
  if ( v36 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
  SysFreeString(0);
  SysFreeString(v10);
  if ( v13 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_44;
    v17 = 81;
    goto LABEL_15;
  }
  if ( (*(_BYTE *)v4 & 1) != 0 && (AttributeWithBooleanValue = CreateAttributeWithBooleanValue(*a1, v14, v15, v32)) != 0 )
  {
    v13 = (unsigned __int16)AttributeWithBooleanValue;
    if ( (AttributeWithBooleanValue & 0x1FFF0000) != 0x70000 )
      v13 = AttributeWithBooleanValue;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      v17 = 82;
LABEL_15:
      WPP_SF_d(*((_QWORD *)v16 + 2), v17, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, v13);
    }
  }
  else
  {
    SysFreeString(0);
    v8 = SysAllocString(L"IssuerHash");
    v37 = v8;
    if ( !v8 )
      ATL::AtlThrowImpl(v19);
    for ( i = 0; i < *((_WORD *)v4 + 1); ++i )
    {
      v21 = *((_QWORD *)v4 + 1) + 24LL * i;
      v22 = 0;
      *(_QWORD *)psz = 0;
      v45 = 0;
      v46 = 0;
      v47 = 0;
      v48 = 0;
      v49 = 0;
      v50 = 0;
      v51 = 0;
      v52 = 0;
      v53 = 0;
      v54 = 0;
      v55 = 0;
      v56 = 0;
      v57 = 0;
      v58 = 0;
      v59 = 0;
      v60 = 0;
      v61 = 0;
      v62 = 0;
      v63 = 0;
      v64 = 0;
      do
      {
        v23 = L"%x ";
        if ( *(_BYTE *)(v22 + v21 + 4) < 0x10u )
          v23 = L"0%x ";
        if ( swprintf_s(
               &psz[(unsigned int)(3 * v22)],
               (unsigned int)(61 - 3 * v22),
               v23,
               *(unsigned __int8 *)(v22 + v21 + 4)) == -1 )
          break;
        v22 = (unsigned int)(v22 + 1);
      }
      while ( (unsigned int)v22 < 0x14 );
      VariantInit(&v41);
      v24 = SysAllocString(psz);
      v25 = v38;
      if ( !v24 )
      {
        v13 = -2147024882;
        break;
      }
      memset(&pvarg, 0, sizeof(pvarg));
      VariantInit(&pvarg);
      pvarg.llVal = (LONGLONG)SysAllocString(v24);
      pvarg.vt = 8;
      v41 = pvarg;
      pRecInfo = pvarg.pRecInfo;
      v27 = v32;
      v28 = *v25;
      v30 = 0;
      memset(&v33, 0, sizeof(v33));
      VariantInit(&v33);
      v33.vt = 3;
      v33.lVal = 1;
      v35 = v33;
      v13 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, VARIANTARG *, OLECHAR *, unsigned __int16 *, __int64 *))v28->lpVtbl->createNode)(
              v28,
              &v35,
              v8,
              v39,
              &v30);
      VariantClear(&v33);
      if ( !v13 )
      {
        strcpy((char *)&v35, "\b");
        *(_OWORD *)&v35.decVal.scale = *(_OWORD *)&pvarg.decVal.scale;
        v35.pRecInfo = pRecInfo;
        v13 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v30 + 248LL))(v30, &v35);
        if ( !v13 )
          v13 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64, __int64 *))v27->lpVtbl->appendChild)(
                  v27,
                  v30,
                  &v31);
      }
      if ( v30 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
      VariantClear(&v41);
      if ( v31 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
        v31 = 0;
      }
      SysFreeString(v24);
      if ( v13 )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          break;
        v17 = 83;
        goto LABEL_15;
      }
      v4 = v40;
    }
  }
LABEL_44:
  if ( v31 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    v31 = 0;
  }
  if ( v32 )
  {
    ((void (__fastcall *)(struct IXMLDOMNode *))v32->lpVtbl->Release)(v32);
    v32 = 0;
  }
  SysFreeString(v8);
  return v13;
}

```

## disassembly

```asm
0x180016e90  push    rbp
0x180016e92  push    rbx
0x180016e93  push    rsi
0x180016e94  push    rdi
0x180016e95  push    r12
0x180016e97  push    r13
0x180016e99  push    r14
0x180016e9b  push    r15
0x180016e9d  lea     rbp, [rsp-0C8h]
0x180016ea5  sub     rsp, 1C8h
0x180016eac  movaps  [rsp+200h+var_50], xmm6
0x180016eb4  mov     rax, cs:__security_cookie
0x180016ebb  xor     rax, rsp
0x180016ebe  mov     [rbp+100h+var_60], rax
0x180016ec5  mov     r15, r9
0x180016ec8  mov     [rbp+100h+var_140], r9
0x180016ecc  mov     r12, r8
0x180016ecf  mov     [rbp+100h+var_148], r8
0x180016ed3  mov     rsi, rdx
0x180016ed6  mov     r13, rcx
0x180016ed9  mov     [rbp+100h+var_150], rcx
0x180016edd  xor     r14d, r14d
0x180016ee0  mov     edi, r14d
0x180016ee3  mov     [rbp+100h+var_158], r14
0x180016ee7  xorps   xmm0, xmm0
0x180016eea  xor     eax, eax
0x180016eec  movups  xmmword ptr [rbp+100h+var_138], xmm0
0x180016ef0  mov     qword ptr [rbp+100h+var_138+10h], rax
0x180016ef4  mov     [rsp+200h+var_1C0], r14
0x180016ef9  mov     [rsp+200h+var_1C8], r14
0x180016efe  movups  xmmword ptr [rsp+200h+pvarg], xmm0
0x180016f03  mov     qword ptr [rsp+200h+pvarg+10h], rax
0x180016f08  lea     rcx, aCahashlist; "CAHashList"
0x180016f0f  call    cs:__imp_SysAllocString
0x180016f16  nop     dword ptr [rax+rax+00h]
0x180016f1b  mov     rbx, rax
0x180016f1e  mov     [rbp+100h+var_120], rax
0x180016f22  test    rax, rax
0x180016f25  jnz     short loc_180016F2D
0x180016f27  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180016f2d  mov     [rbp+100h+var_118], r14
0x180016f31  mov     [rbp+100h+var_160], r14
0x180016f35  lea     rcx, [rsp+200h+pvarg]; pvarg
0x180016f3a  call    cs:__imp_VariantInit
0x180016f41  nop     dword ptr [rax+rax+00h]
0x180016f46  mov     word ptr [rsp+200h+pvarg], r14w
0x180016f4c  mov     r14, [rsi]
0x180016f4f  mov     rsi, [r13+0]
0x180016f53  mov     [rsp+200h+var_1D0], 0
0x180016f5c  xorps   xmm0, xmm0
0x180016f5f  xor     eax, eax
0x180016f61  movups  xmmword ptr [rsp+200h+var_1B8], xmm0
0x180016f66  mov     qword ptr [rsp+200h+var_1B8+10h], rax
0x180016f6b  lea     rcx, [rsp+200h+var_1B8]; pvarg
0x180016f70  call    cs:__imp_VariantInit
0x180016f77  nop     dword ptr [rax+rax+00h]
0x180016f7c  mov     eax, 3
0x180016f81  mov     word ptr [rsp+200h+var_1B8], ax
0x180016f86  mov     dword ptr [rsp+200h+var_1B8+8], 1
0x180016f8e  movups  xmm0, xmmword ptr [rsp+200h+var_1B8]
0x180016f93  movaps  [rbp+100h+var_180], xmm0
0x180016f97  movsd   xmm1, qword ptr [rsp+200h+var_1B8+10h]
0x180016f9d  movsd   [rbp+100h+var_170], xmm1
0x180016fa2  mov     rax, [rsi]
0x180016fa5  lea     rcx, [rsp+200h+var_1D0]
0x180016faa  mov     [rsp+200h+var_1E0], rcx
0x180016faf  mov     r9, r12
0x180016fb2  mov     r8, rbx
0x180016fb5  lea     rdx, [rbp+100h+var_180]
0x180016fb9  mov     rcx, rsi
0x180016fbc  mov     rax, [rax+1C0h]
0x180016fc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fc8  mov     esi, eax
0x180016fca  lea     rcx, [rsp+200h+var_1B8]; pvarg
0x180016fcf  call    cs:__imp_VariantClear
0x180016fd6  nop     dword ptr [rax+rax+00h]
0x180016fdb  test    esi, esi
0x180016fdd  jnz     short loc_180016FFD
0x180016fdf  mov     rax, [r14]
0x180016fe2  lea     r8, [rsp+200h+var_1C0]
0x180016fe7  mov     rdx, [rsp+200h+var_1D0]
0x180016fec  mov     rcx, r14
0x180016fef  mov     rax, [rax+0A8h]
0x180016ff6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ffb  mov     esi, eax
0x180016ffd  mov     rcx, [rsp+200h+var_1D0]
0x180017002  test    rcx, rcx
0x180017005  jz      short loc_180017013
0x180017007  mov     rax, [rcx]
0x18001700a  mov     rax, [rax+10h]
0x18001700e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017013  lea     rcx, [rsp+200h+pvarg]; pvarg
0x180017018  call    cs:__imp_VariantClear
0x18001701f  nop     dword ptr [rax+rax+00h]
0x180017024  lea     r14, WPP_GLOBAL_Control
0x18001702b  test    esi, esi
0x18001702d  jz      short loc_180017054
0x18001702f  mov     rcx, cs:WPP_GLOBAL_Control
0x180017036  cmp     rcx, r14
0x180017039  jz      short loc_180017054
0x18001703b  mov     edx, 45h ; 'E'
0x180017040  mov     r9d, esi
0x180017043  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18001704a  mov     rcx, [rcx+10h]
0x18001704e  call    WPP_SF_d
0x180017053  nop
0x180017054  mov     rcx, [rbp+100h+var_160]
0x180017058  test    rcx, rcx
0x18001705b  jz      short loc_18001706A
0x18001705d  mov     rax, [rcx]
0x180017060  mov     rax, [rax+10h]
0x180017064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017069  nop
0x18001706a  xor     ecx, ecx; bstrString
0x18001706c  call    cs:__imp_SysFreeString
0x180017073  nop     dword ptr [rax+rax+00h]
0x180017078  nop
0x180017079  mov     rcx, rbx; bstrString
0x18001707c  call    cs:__imp_SysFreeString
0x180017083  nop     dword ptr [rax+rax+00h]
0x180017088  test    esi, esi
0x18001708a  jz      short loc_1800170B9
0x18001708c  mov     rcx, cs:WPP_GLOBAL_Control
0x180017093  cmp     rcx, r14
0x180017096  jz      loc_1800173ED
0x18001709c  mov     edx, 51h ; 'Q'
0x1800170a1  mov     r9d, esi
0x1800170a4  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x1800170ab  mov     rcx, [rcx+10h]
0x1800170af  call    WPP_SF_d
0x1800170b4  jmp     loc_1800173ED
0x1800170b9  test    byte ptr [r15], 1
0x1800170bd  jz      short loc_1800170FD
0x1800170bf  mov     r9, [rsp+200h+var_1C0]; struct IXMLDOMNode *
0x1800170c4  mov     rcx, [r13+0]; struct IXMLDOMDocument2 *
0x1800170c8  call    ?CreateAttributeWithBooleanValue@@YAJPEAUIXMLDOMDocument2@@HPEAGPEAUIXMLDOMNode@@@Z; CreateAttributeWithBooleanValue(IXMLDOMDocument2 *,int,ushort *,IXMLDOMNode *)
0x1800170cd  test    eax, eax
0x1800170cf  jz      short loc_1800170FD
0x1800170d1  mov     ecx, eax
0x1800170d3  and     ecx, 1FFF0000h
0x1800170d9  cmp     ecx, 70000h
0x1800170df  movzx   esi, ax
0x1800170e2  jz      short loc_1800170E6
0x1800170e4  mov     esi, eax
0x1800170e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800170ed  cmp     rcx, r14
0x1800170f0  jz      loc_1800173ED
0x1800170f6  mov     edx, 52h ; 'R'
0x1800170fb  jmp     short loc_1800170A1
0x1800170fd  xor     ecx, ecx; bstrString
0x1800170ff  call    cs:__imp_SysFreeString
0x180017106  nop     dword ptr [rax+rax+00h]
0x18001710b  lea     rcx, aIssuerhash; "IssuerHash"
0x180017112  call    cs:__imp_SysAllocString
0x180017119  nop     dword ptr [rax+rax+00h]
0x18001711e  mov     rdi, rax
0x180017121  mov     [rbp+100h+var_158], rax
0x180017125  test    rax, rax
0x180017128  jnz     short loc_180017130
0x18001712a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180017130  xor     r12d, r12d
0x180017133  cmp     r12w, [r15+2]
0x180017138  jnb     loc_1800173ED
0x18001713e  movzx   eax, r12w
0x180017142  lea     rcx, [rax+rax*2]
0x180017146  mov     rax, [r15+8]
0x18001714a  lea     rsi, [rax+rcx*8]
0x18001714e  xor     ebx, ebx
0x180017150  xor     eax, eax
0x180017152  mov     qword ptr [rbp+100h+psz], rax
0x180017156  mov     [rbp+100h+var_108], rax
0x18001715a  mov     [rbp+100h+var_100], rax
0x18001715e  mov     [rbp+100h+var_F8], rax
0x180017162  mov     [rbp+100h+var_F0], rax
0x180017166  mov     [rbp+100h+var_E8], rax
0x18001716a  mov     [rbp+100h+var_E0], rax
0x18001716e  mov     [rbp+100h+var_D8], rax
0x180017172  mov     [rbp+100h+var_D0], rax
0x180017176  mov     [rbp+100h+var_C8], rax
0x18001717a  mov     [rbp+100h+var_C0], rax
0x18001717e  mov     [rbp+100h+var_B8], rax
0x180017182  mov     [rbp+100h+var_B0], rax
0x180017186  mov     [rbp+100h+var_A8], rax
0x18001718a  mov     [rbp+100h+var_A0], rax
0x18001718e  mov     [rbp+100h+var_98], rax
0x180017192  mov     [rbp+100h+var_90], rax
0x180017196  mov     [rbp+100h+var_88], rax
0x18001719a  mov     [rbp+100h+var_80], rax
0x1800171a1  mov     [rbp+100h+var_78], rax
0x1800171a8  mov     [rbp+100h+var_70], rax
0x1800171af  lea     r13, a0X; "0%x "
0x1800171b6  nop     word ptr [rax+rax+00000000h]
0x1800171c0  movzx   ecx, byte ptr [rbx+rsi+4]
0x1800171c5  lea     r10d, [rbx+rbx*2]
0x1800171c9  mov     r9d, ecx
0x1800171cc  lea     r8, asc_180087638; "%x "
0x1800171d3  cmp     cl, 10h
0x1800171d6  cmovb   r8, r13; Format
0x1800171da  mov     edx, 3Dh ; '='
0x1800171df  sub     edx, r10d; BufferCount
0x1800171e2  lea     rcx, [rbp+100h+psz]
0x1800171e6  lea     rcx, [rcx+r10*2]; Buffer
0x1800171ea  call    swprintf_s
0x1800171ef  cmp     eax, 0FFFFFFFFh
0x1800171f2  jz      short loc_1800171FB
0x1800171f4  inc     ebx
0x1800171f6  cmp     ebx, 14h
0x1800171f9  jb      short loc_1800171C0
0x1800171fb  lea     rcx, [rbp+100h+var_138]; pvarg
0x1800171ff  call    cs:__imp_VariantInit
0x180017206  nop     dword ptr [rax+rax+00h]
0x18001720b  lea     rcx, [rbp+100h+psz]; psz
0x18001720f  call    cs:__imp_SysAllocString
0x180017216  nop     dword ptr [rax+rax+00h]
0x18001721b  mov     r14, rax
0x18001721e  test    rax, rax
0x180017221  mov     r13, [rbp+100h+var_150]
0x180017225  jz      loc_1800173E8
0x18001722b  xorps   xmm0, xmm0
0x18001722e  xor     eax, eax
0x180017230  movups  xmmword ptr [rsp+200h+pvarg], xmm0
0x180017235  mov     qword ptr [rsp+200h+pvarg+10h], rax
0x18001723a  lea     rcx, [rsp+200h+pvarg]; pvarg
0x18001723f  call    cs:__imp_VariantInit
0x180017246  nop     dword ptr [rax+rax+00h]
0x18001724b  mov     rcx, r14; psz
0x18001724e  call    cs:__imp_SysAllocString
0x180017255  nop     dword ptr [rax+rax+00h]
0x18001725a  mov     qword ptr [rsp+200h+pvarg+8], rax
0x18001725f  mov     eax, 8
0x180017264  mov     word ptr [rsp+200h+pvarg], ax
0x180017269  movups  xmm0, xmmword ptr [rsp+200h+pvarg]
0x18001726e  movups  xmmword ptr [rbp+100h+var_138], xmm0
0x180017272  movsd   xmm6, qword ptr [rsp+200h+pvarg+10h]
0x180017278  movsd   qword ptr [rbp+100h+var_138+10h], xmm6
0x18001727d  mov     r15, [rsp+200h+var_1C0]
0x180017282  mov     rbx, [r13+0]
0x180017286  mov     [rsp+200h+var_1D0], 0
0x18001728f  xorps   xmm0, xmm0
0x180017292  xor     eax, eax
0x180017294  movups  xmmword ptr [rsp+200h+var_1B8], xmm0
0x180017299  mov     qword ptr [rsp+200h+var_1B8+10h], rax
0x18001729e  lea     rcx, [rsp+200h+var_1B8]; pvarg
0x1800172a3  call    cs:__imp_VariantInit
0x1800172aa  nop     dword ptr [rax+rax+00h]
0x1800172af  mov     eax, 3
0x1800172b4  mov     word ptr [rsp+200h+var_1B8], ax
0x1800172b9  mov     dword ptr [rsp+200h+var_1B8+8], 1
0x1800172c1  movups  xmm0, xmmword ptr [rsp+200h+var_1B8]
0x1800172c6  movaps  [rbp+100h+var_180], xmm0
0x1800172ca  movsd   xmm1, qword ptr [rsp+200h+var_1B8+10h]
0x1800172d0  movsd   [rbp+100h+var_170], xmm1
0x1800172d5  mov     rax, [rbx]
0x1800172d8  lea     rcx, [rsp+200h+var_1D0]
0x1800172dd  mov     [rsp+200h+var_1E0], rcx
0x1800172e2  mov     r9, [rbp+100h+var_148]
0x1800172e6  mov     r8, rdi
0x1800172e9  lea     rdx, [rbp+100h+var_180]
0x1800172ed  mov     rcx, rbx
0x1800172f0  mov     rax, [rax+1C0h]
0x1800172f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800172fc  mov     esi, eax
0x1800172fe  lea     rcx, [rsp+200h+var_1B8]; pvarg
0x180017303  call    cs:__imp_VariantClear
0x18001730a  nop     dword ptr [rax+rax+00h]
0x18001730f  test    esi, esi
0x180017311  jnz     short loc_180017366
0x180017313  mov     rcx, [rsp+200h+var_1D0]
0x180017318  mov     eax, 8
0x18001731d  mov     word ptr [rbp+100h+var_180], ax
0x180017321  movups  xmm0, xmmword ptr [rsp+200h+pvarg+2]
0x180017326  movups  [rbp+100h+var_180+2], xmm0
0x18001732a  movsd   [rbp+100h+var_170], xmm6
0x18001732f  mov     rax, [rcx]
0x180017332  lea     rdx, [rbp+100h+var_180]
0x180017336  mov     rax, [rax+0F8h]
0x18001733d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017342  mov     esi, eax
0x180017344  test    eax, eax
0x180017346  jnz     short loc_180017366
0x180017348  mov     rax, [r15]
0x18001734b  lea     r8, [rsp+200h+var_1C8]
0x180017350  mov     rdx, [rsp+200h+var_1D0]
0x180017355  mov     rcx, r15
0x180017358  mov     rax, [rax+0A8h]
0x18001735f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017364  mov     esi, eax
0x180017366  mov     rcx, [rsp+200h+var_1D0]
0x18001736b  test    rcx, rcx
0x18001736e  jz      short loc_18001737C
0x180017370  mov     rax, [rcx]
0x180017373  mov     rax, [rax+10h]
0x180017377  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001737c  lea     rcx, [rbp+100h+var_138]; pvarg
0x180017380  call    cs:__imp_VariantClear
0x180017387  nop     dword ptr [rax+rax+00h]
0x18001738c  mov     rcx, [rsp+200h+var_1C8]
0x180017391  test    rcx, rcx
0x180017394  jz      short loc_1800173AB
0x180017396  mov     rax, [rcx]
  ... truncated ...
```
