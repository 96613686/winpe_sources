# InsertCAFilterTags(IXMLDOMDocument2 * *,IXMLDOMNode * *,ushort *,_EAPTLS_FILTER_PROP *)

- ea: `0x1800158f0`
- end: `0x180015e51`
- name: `?InsertCAFilterTags@@YAKPEAPEAUIXMLDOMDocument2@@PEAPEAUIXMLDOMNode@@PEAGPEAU_EAPTLS_FILTER_PROP@@@Z`
- size: `1377`
- prototype: `unsigned int __fastcall(struct IXMLDOMDocument2 **, struct IXMLDOMNode **, unsigned __int16 *, struct _EAPTLS_FILTER_PROP *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180014e00`

## callees

- `0x180004bd0`
- `0x1800158f0`
- `0x180015e60`
- `0x180035680`
- `0x1800362d8`
- `0x18005e7c8`
- `0x18007c010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001596f`
- `OLEAUT32!__imp_SysAllocString` at `0x180015b42`
- `OLEAUT32!__imp_SysAllocString` at `0x180015c29`
- `OLEAUT32!__imp_SysAllocString` at `0x180015c5c`
- `OLEAUT32!__imp_SysAllocString` at `0x18001596f`
- `OLEAUT32!__imp_SysAllocString` at `0x180015b42`
- `OLEAUT32!__imp_SysAllocString` at `0x180015c29`
- `OLEAUT32!__imp_SysAllocString` at `0x180015c5c`
- `OLEAUT32!__imp_SysFreeString` at `0x180015aae`
- `OLEAUT32!__imp_SysFreeString` at `0x180015ab8`
- `OLEAUT32!__imp_SysFreeString` at `0x180015b35`
- `OLEAUT32!__imp_SysFreeString` at `0x180015da4`
- `OLEAUT32!__imp_SysFreeString` at `0x180015e1e`
- `OLEAUT32!__imp_SysFreeString` at `0x180015aae`
- `OLEAUT32!__imp_SysFreeString` at `0x180015ab8`
- `OLEAUT32!__imp_SysFreeString` at `0x180015b35`
- `OLEAUT32!__imp_SysFreeString` at `0x180015da4`
- `OLEAUT32!__imp_SysFreeString` at `0x180015e1e`
- `OLEAUT32!__imp_VariantInit` at `0x180015994`
- `OLEAUT32!__imp_VariantInit` at `0x1800159c4`
- `OLEAUT32!__imp_VariantInit` at `0x180015c1f`
- `OLEAUT32!__imp_VariantInit` at `0x180015c53`
- `OLEAUT32!__imp_VariantInit` at `0x180015cab`
- `OLEAUT32!__imp_VariantInit` at `0x180015994`
- `OLEAUT32!__imp_VariantInit` at `0x1800159c4`
- `OLEAUT32!__imp_VariantInit` at `0x180015c1f`
- `OLEAUT32!__imp_VariantInit` at `0x180015c53`
- `OLEAUT32!__imp_VariantInit` at `0x180015cab`
- `OLEAUT32!__imp_VariantClear` at `0x180015a1d`
- `OLEAUT32!__imp_VariantClear` at `0x180015a60`
- `OLEAUT32!__imp_VariantClear` at `0x180015d05`
- `OLEAUT32!__imp_VariantClear` at `0x180015d7c`
- `OLEAUT32!__imp_VariantClear` at `0x180015a1d`
- `OLEAUT32!__imp_VariantClear` at `0x180015a60`
- `OLEAUT32!__imp_VariantClear` at `0x180015d05`
- `OLEAUT32!__imp_VariantClear` at `0x180015d7c`

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
0x1800158f0  push    rbp
0x1800158f2  push    rbx
0x1800158f3  push    rsi
0x1800158f4  push    rdi
0x1800158f5  push    r12
0x1800158f7  push    r13
0x1800158f9  push    r14
0x1800158fb  push    r15
0x1800158fd  lea     rbp, [rsp-0C8h]
0x180015905  sub     rsp, 1C8h
0x18001590c  movaps  [rsp+200h+var_50], xmm6
0x180015914  mov     rax, cs:__security_cookie
0x18001591b  xor     rax, rsp
0x18001591e  mov     [rbp+100h+var_60], rax
0x180015925  mov     r15, r9
0x180015928  mov     [rbp+100h+var_140], r9
0x18001592c  mov     r12, r8
0x18001592f  mov     [rbp+100h+var_148], r8
0x180015933  mov     rsi, rdx
0x180015936  mov     r13, rcx
0x180015939  mov     [rbp+100h+var_150], rcx
0x18001593d  xor     r14d, r14d
0x180015940  mov     edi, r14d
0x180015943  mov     [rbp+100h+var_158], r14
0x180015947  xorps   xmm0, xmm0
0x18001594a  xor     eax, eax
0x18001594c  movups  xmmword ptr [rbp+100h+var_138], xmm0
0x180015950  mov     qword ptr [rbp+100h+var_138+10h], rax
0x180015954  mov     [rsp+200h+var_1C0], r14
0x180015959  mov     [rsp+200h+var_1C8], r14
0x18001595e  movups  xmmword ptr [rsp+200h+pvarg], xmm0
0x180015963  mov     qword ptr [rsp+200h+pvarg+10h], rax
0x180015968  lea     rcx, aCahashlist; "CAHashList"
0x18001596f  call    cs:__imp_SysAllocString
0x180015975  mov     rbx, rax
0x180015978  mov     [rbp+100h+var_120], rax
0x18001597c  test    rax, rax
0x18001597f  jnz     short loc_180015987
0x180015981  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180015987  mov     [rbp+100h+var_118], r14
0x18001598b  mov     [rbp+100h+var_160], r14
0x18001598f  lea     rcx, [rsp+200h+pvarg]; pvarg
0x180015994  call    cs:__imp_VariantInit
0x18001599a  mov     word ptr [rsp+200h+pvarg], r14w
0x1800159a0  mov     r14, [rsi]
0x1800159a3  mov     rsi, [r13+0]
0x1800159a7  mov     [rsp+200h+var_1D0], 0
0x1800159b0  xorps   xmm0, xmm0
0x1800159b3  xor     eax, eax
0x1800159b5  movups  xmmword ptr [rsp+200h+var_1B8], xmm0
0x1800159ba  mov     qword ptr [rsp+200h+var_1B8+10h], rax
0x1800159bf  lea     rcx, [rsp+200h+var_1B8]; pvarg
0x1800159c4  call    cs:__imp_VariantInit
0x1800159ca  mov     eax, 3
0x1800159cf  mov     word ptr [rsp+200h+var_1B8], ax
0x1800159d4  mov     dword ptr [rsp+200h+var_1B8+8], 1
0x1800159dc  movups  xmm0, xmmword ptr [rsp+200h+var_1B8]
0x1800159e1  movaps  [rbp+100h+var_180], xmm0
0x1800159e5  movsd   xmm1, qword ptr [rsp+200h+var_1B8+10h]
0x1800159eb  movsd   [rbp+100h+var_170], xmm1
0x1800159f0  mov     rax, [rsi]
0x1800159f3  lea     rcx, [rsp+200h+var_1D0]
0x1800159f8  mov     [rsp+200h+var_1E0], rcx
0x1800159fd  mov     r9, r12
0x180015a00  mov     r8, rbx
0x180015a03  lea     rdx, [rbp+100h+var_180]
0x180015a07  mov     rcx, rsi
0x180015a0a  mov     rax, [rax+1C0h]
0x180015a11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a16  mov     esi, eax
0x180015a18  lea     rcx, [rsp+200h+var_1B8]; pvarg
0x180015a1d  call    cs:__imp_VariantClear
0x180015a23  test    esi, esi
0x180015a25  jnz     short loc_180015A45
0x180015a27  mov     rax, [r14]
0x180015a2a  lea     r8, [rsp+200h+var_1C0]
0x180015a2f  mov     rdx, [rsp+200h+var_1D0]
0x180015a34  mov     rcx, r14
0x180015a37  mov     rax, [rax+0A8h]
0x180015a3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a43  mov     esi, eax
0x180015a45  mov     rcx, [rsp+200h+var_1D0]
0x180015a4a  test    rcx, rcx
0x180015a4d  jz      short loc_180015A5B
0x180015a4f  mov     rax, [rcx]
0x180015a52  mov     rax, [rax+10h]
0x180015a56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a5b  lea     rcx, [rsp+200h+pvarg]; pvarg
0x180015a60  call    cs:__imp_VariantClear
0x180015a66  lea     r14, WPP_GLOBAL_Control
0x180015a6d  test    esi, esi
0x180015a6f  jz      short loc_180015A96
0x180015a71  mov     rcx, cs:WPP_GLOBAL_Control
0x180015a78  cmp     rcx, r14
0x180015a7b  jz      short loc_180015A96
0x180015a7d  mov     edx, 45h ; 'E'
0x180015a82  mov     r9d, esi
0x180015a85  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180015a8c  mov     rcx, [rcx+10h]
0x180015a90  call    WPP_SF_d
0x180015a95  nop
0x180015a96  mov     rcx, [rbp+100h+var_160]
0x180015a9a  test    rcx, rcx
0x180015a9d  jz      short loc_180015AAC
0x180015a9f  mov     rax, [rcx]
0x180015aa2  mov     rax, [rax+10h]
0x180015aa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015aab  nop
0x180015aac  xor     ecx, ecx; bstrString
0x180015aae  call    cs:__imp_SysFreeString
0x180015ab4  nop
0x180015ab5  mov     rcx, rbx; bstrString
0x180015ab8  call    cs:__imp_SysFreeString
0x180015abe  test    esi, esi
0x180015ac0  jz      short loc_180015AEF
0x180015ac2  mov     rcx, cs:WPP_GLOBAL_Control
0x180015ac9  cmp     rcx, r14
0x180015acc  jz      loc_180015DDD
0x180015ad2  mov     edx, 51h ; 'Q'
0x180015ad7  mov     r9d, esi
0x180015ada  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180015ae1  mov     rcx, [rcx+10h]
0x180015ae5  call    WPP_SF_d
0x180015aea  jmp     loc_180015DDD
0x180015aef  test    byte ptr [r15], 1
0x180015af3  jz      short loc_180015B33
0x180015af5  mov     r9, [rsp+200h+var_1C0]; struct IXMLDOMNode *
0x180015afa  mov     rcx, [r13+0]; struct IXMLDOMDocument2 *
0x180015afe  call    ?CreateAttributeWithBooleanValue@@YAJPEAUIXMLDOMDocument2@@HPEAGPEAUIXMLDOMNode@@@Z; CreateAttributeWithBooleanValue(IXMLDOMDocument2 *,int,ushort *,IXMLDOMNode *)
0x180015b03  test    eax, eax
0x180015b05  jz      short loc_180015B33
0x180015b07  mov     ecx, eax
0x180015b09  and     ecx, 1FFF0000h
0x180015b0f  cmp     ecx, 70000h
0x180015b15  movzx   esi, ax
0x180015b18  jz      short loc_180015B1C
0x180015b1a  mov     esi, eax
0x180015b1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180015b23  cmp     rcx, r14
0x180015b26  jz      loc_180015DDD
0x180015b2c  mov     edx, 52h ; 'R'
0x180015b31  jmp     short loc_180015AD7
0x180015b33  xor     ecx, ecx; bstrString
0x180015b35  call    cs:__imp_SysFreeString
0x180015b3b  lea     rcx, aIssuerhash; "IssuerHash"
0x180015b42  call    cs:__imp_SysAllocString
0x180015b48  mov     rdi, rax
0x180015b4b  mov     [rbp+100h+var_158], rax
0x180015b4f  test    rax, rax
0x180015b52  jnz     short loc_180015B5A
0x180015b54  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180015b5a  xor     r12d, r12d
0x180015b5d  cmp     r12w, [r15+2]
0x180015b62  jnb     loc_180015DDD
0x180015b68  movzx   eax, r12w
0x180015b6c  lea     rcx, [rax+rax*2]
0x180015b70  mov     rax, [r15+8]
0x180015b74  lea     rsi, [rax+rcx*8]
0x180015b78  xor     ebx, ebx
0x180015b7a  xor     eax, eax
0x180015b7c  mov     qword ptr [rbp+100h+psz], rax
0x180015b80  mov     [rbp+100h+var_108], rax
0x180015b84  mov     [rbp+100h+var_100], rax
0x180015b88  mov     [rbp+100h+var_F8], rax
0x180015b8c  mov     [rbp+100h+var_F0], rax
0x180015b90  mov     [rbp+100h+var_E8], rax
0x180015b94  mov     [rbp+100h+var_E0], rax
0x180015b98  mov     [rbp+100h+var_D8], rax
0x180015b9c  mov     [rbp+100h+var_D0], rax
0x180015ba0  mov     [rbp+100h+var_C8], rax
0x180015ba4  mov     [rbp+100h+var_C0], rax
0x180015ba8  mov     [rbp+100h+var_B8], rax
0x180015bac  mov     [rbp+100h+var_B0], rax
0x180015bb0  mov     [rbp+100h+var_A8], rax
0x180015bb4  mov     [rbp+100h+var_A0], rax
0x180015bb8  mov     [rbp+100h+var_98], rax
0x180015bbc  mov     [rbp+100h+var_90], rax
0x180015bc0  mov     [rbp+100h+var_88], rax
0x180015bc4  mov     [rbp+100h+var_80], rax
0x180015bcb  mov     [rbp+100h+var_78], rax
0x180015bd2  mov     [rbp+100h+var_70], rax
0x180015bd9  lea     r13, a0X; "0%x "
0x180015be0  movzx   ecx, byte ptr [rbx+rsi+4]
0x180015be5  lea     r10d, [rbx+rbx*2]
0x180015be9  mov     r9d, ecx
0x180015bec  lea     r8, asc_180081638; "%x "
0x180015bf3  cmp     cl, 10h
0x180015bf6  cmovb   r8, r13; Format
0x180015bfa  mov     edx, 3Dh ; '='
0x180015bff  sub     edx, r10d; BufferCount
0x180015c02  lea     rcx, [rbp+100h+psz]
0x180015c06  lea     rcx, [rcx+r10*2]; Buffer
0x180015c0a  call    swprintf_s
0x180015c0f  cmp     eax, 0FFFFFFFFh
0x180015c12  jz      short loc_180015C1B
0x180015c14  inc     ebx
0x180015c16  cmp     ebx, 14h
0x180015c19  jb      short loc_180015BE0
0x180015c1b  lea     rcx, [rbp+100h+var_138]; pvarg
0x180015c1f  call    cs:__imp_VariantInit
0x180015c25  lea     rcx, [rbp+100h+psz]; psz
0x180015c29  call    cs:__imp_SysAllocString
0x180015c2f  mov     r14, rax
0x180015c32  test    rax, rax
0x180015c35  mov     r13, [rbp+100h+var_150]
0x180015c39  jz      loc_180015DD8
0x180015c3f  xorps   xmm0, xmm0
0x180015c42  xor     eax, eax
0x180015c44  movups  xmmword ptr [rsp+200h+pvarg], xmm0
0x180015c49  mov     qword ptr [rsp+200h+pvarg+10h], rax
0x180015c4e  lea     rcx, [rsp+200h+pvarg]; pvarg
0x180015c53  call    cs:__imp_VariantInit
0x180015c59  mov     rcx, r14; psz
0x180015c5c  call    cs:__imp_SysAllocString
0x180015c62  mov     qword ptr [rsp+200h+pvarg+8], rax
0x180015c67  mov     eax, 8
0x180015c6c  mov     word ptr [rsp+200h+pvarg], ax
0x180015c71  movups  xmm0, xmmword ptr [rsp+200h+pvarg]
0x180015c76  movups  xmmword ptr [rbp+100h+var_138], xmm0
0x180015c7a  movsd   xmm6, qword ptr [rsp+200h+pvarg+10h]
0x180015c80  movsd   qword ptr [rbp+100h+var_138+10h], xmm6
0x180015c85  mov     r15, [rsp+200h+var_1C0]
0x180015c8a  mov     rbx, [r13+0]
0x180015c8e  mov     [rsp+200h+var_1D0], 0
0x180015c97  xorps   xmm0, xmm0
0x180015c9a  xor     eax, eax
0x180015c9c  movups  xmmword ptr [rsp+200h+var_1B8], xmm0
0x180015ca1  mov     qword ptr [rsp+200h+var_1B8+10h], rax
0x180015ca6  lea     rcx, [rsp+200h+var_1B8]; pvarg
0x180015cab  call    cs:__imp_VariantInit
0x180015cb1  mov     eax, 3
0x180015cb6  mov     word ptr [rsp+200h+var_1B8], ax
0x180015cbb  mov     dword ptr [rsp+200h+var_1B8+8], 1
0x180015cc3  movups  xmm0, xmmword ptr [rsp+200h+var_1B8]
0x180015cc8  movaps  [rbp+100h+var_180], xmm0
0x180015ccc  movsd   xmm1, qword ptr [rsp+200h+var_1B8+10h]
0x180015cd2  movsd   [rbp+100h+var_170], xmm1
0x180015cd7  mov     rax, [rbx]
0x180015cda  lea     rcx, [rsp+200h+var_1D0]
0x180015cdf  mov     [rsp+200h+var_1E0], rcx
0x180015ce4  mov     r9, [rbp+100h+var_148]
0x180015ce8  mov     r8, rdi
0x180015ceb  lea     rdx, [rbp+100h+var_180]
0x180015cef  mov     rcx, rbx
0x180015cf2  mov     rax, [rax+1C0h]
0x180015cf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015cfe  mov     esi, eax
0x180015d00  lea     rcx, [rsp+200h+var_1B8]; pvarg
0x180015d05  call    cs:__imp_VariantClear
0x180015d0b  test    esi, esi
0x180015d0d  jnz     short loc_180015D62
0x180015d0f  mov     rcx, [rsp+200h+var_1D0]
0x180015d14  mov     eax, 8
0x180015d19  mov     word ptr [rbp+100h+var_180], ax
0x180015d1d  movups  xmm0, xmmword ptr [rsp+200h+pvarg+2]
0x180015d22  movups  [rbp+100h+var_180+2], xmm0
0x180015d26  movsd   [rbp+100h+var_170], xmm6
0x180015d2b  mov     rax, [rcx]
0x180015d2e  lea     rdx, [rbp+100h+var_180]
0x180015d32  mov     rax, [rax+0F8h]
0x180015d39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d3e  mov     esi, eax
0x180015d40  test    eax, eax
0x180015d42  jnz     short loc_180015D62
0x180015d44  mov     rax, [r15]
0x180015d47  lea     r8, [rsp+200h+var_1C8]
0x180015d4c  mov     rdx, [rsp+200h+var_1D0]
0x180015d51  mov     rcx, r15
0x180015d54  mov     rax, [rax+0A8h]
0x180015d5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d60  mov     esi, eax
0x180015d62  mov     rcx, [rsp+200h+var_1D0]
0x180015d67  test    rcx, rcx
0x180015d6a  jz      short loc_180015D78
0x180015d6c  mov     rax, [rcx]
0x180015d6f  mov     rax, [rax+10h]
0x180015d73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d78  lea     rcx, [rbp+100h+var_138]; pvarg
0x180015d7c  call    cs:__imp_VariantClear
0x180015d82  mov     rcx, [rsp+200h+var_1C8]
0x180015d87  test    rcx, rcx
0x180015d8a  jz      short loc_180015DA1
0x180015d8c  mov     rax, [rcx]
0x180015d8f  mov     rax, [rax+10h]
0x180015d93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d98  mov     [rsp+200h+var_1C8], 0
0x180015da1  mov     rcx, r14; bstrString
0x180015da4  call    cs:__imp_SysFreeString
0x180015daa  test    esi, esi
0x180015dac  jnz     short loc_180015DBB
0x180015dae  inc     r12w
0x180015db2  mov     r15, [rbp+100h+var_140]
0x180015db6  jmp     loc_180015B5D
0x180015dbb  mov     rcx, cs:WPP_GLOBAL_Control
0x180015dc2  lea     rax, WPP_GLOBAL_Control
0x180015dc9  cmp     rcx, rax
0x180015dcc  jz      short loc_180015DDD
0x180015dce  mov     edx, 53h ; 'S'
0x180015dd3  jmp     loc_180015AD7
0x180015dd8  mov     esi, 8007000Eh
  ... truncated ...
```
