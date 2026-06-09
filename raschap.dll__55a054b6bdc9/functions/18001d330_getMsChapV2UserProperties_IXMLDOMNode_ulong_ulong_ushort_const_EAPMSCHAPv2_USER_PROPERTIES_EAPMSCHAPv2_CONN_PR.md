# getMsChapV2UserProperties(IXMLDOMNode *,ulong,ulong,ushort const *,_EAPMSCHAPv2_USER_PROPERTIES *,_EAPMSCHAPv2_CONN_PROPERTIES *,_EAPMSCHAPv2_USER_PROPERTIES * *)

- ea: `0x18001d330`
- end: `0x18001d945`
- name: `?getMsChapV2UserProperties@@YAKPEAUIXMLDOMNode@@KKPEBGPEAU_EAPMSCHAPv2_USER_PROPERTIES@@PEAU_EAPMSCHAPv2_CONN_PROPERTIES@@PEAPEAU2@@Z`
- size: `1557`
- prototype: `unsigned int __usercall@<eax>(struct IXMLDOMNode *@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, const unsigned __int16 *@<r9>, struct _EAPMSCHAPv2_USER_PROPERTIES *, struct _EAPMSCHAPv2_CONN_PROPERTIES *, struct _EAPMSCHAPv2_USER_PROPERTIES **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001cbe4`

## callees

- `0x180003bd0`
- `0x180006a20`
- `0x18000b070`
- `0x18000e500`
- `0x180013b20`
- `0x180014610`
- `0x18001d330`
- `0x180025efc`
- `0x180027010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strpbrk` at `0x18001d692`
- `api-ms-win-crt-string-l1-1-0!strpbrk` at `0x18001d692`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x18001d6aa`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x18001d6aa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d441`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d441`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001d524`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001d650`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001d90d`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001d524`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001d650`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001d90d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d52e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d65a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d91b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d52e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d65a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d91b`
- `OLEAUT32!__imp_VariantInit` at `0x18001d38a`
- `OLEAUT32!__imp_VariantInit` at `0x18001d396`
- `OLEAUT32!__imp_VariantInit` at `0x18001d3a2`
- `OLEAUT32!__imp_VariantInit` at `0x18001d38a`
- `OLEAUT32!__imp_VariantInit` at `0x18001d396`
- `OLEAUT32!__imp_VariantInit` at `0x18001d3a2`
- `OLEAUT32!__imp_VariantClear` at `0x18001d757`
- `OLEAUT32!__imp_VariantClear` at `0x18001d763`
- `OLEAUT32!__imp_VariantClear` at `0x18001d76e`
- `OLEAUT32!__imp_VariantClear` at `0x18001d757`
- `OLEAUT32!__imp_VariantClear` at `0x18001d763`
- `OLEAUT32!__imp_VariantClear` at `0x18001d76e`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall getMsChapV2UserProperties(
        struct IXMLDOMNode *a1,
        __int64 a2,
        char a3,
        const unsigned __int16 *a4,
        struct _EAPMSCHAPv2_USER_PROPERTIES *a5,
        struct _EAPMSCHAPv2_CONN_PROPERTIES *a6,
        struct _EAPMSCHAPv2_USER_PROPERTIES **a7)
{
  DWORD SingleNode; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  _DWORD *v12; // rax
  _DWORD *v13; // rdi
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  _OWORD *v16; // rcx
  CHAR *v17; // rax
  __int64 v18; // rdx
  _OWORD *v19; // rbx
  char *v20; // rax
  char *v21; // rsi
  int v22; // eax
  CHAR *v24; // rax
  __int64 v25; // rcx
  CHAR *v26; // rax
  __int64 v27; // rcx
  int v28; // ebx
  struct IXMLDOMNode *v29; // [rsp+40h] [rbp-C0h] BYREF
  struct IXMLDOMNode *v30; // [rsp+48h] [rbp-B8h] BYREF
  struct IXMLDOMNode *v31; // [rsp+50h] [rbp-B0h] BYREF
  struct IXMLDOMNode *v32; // [rsp+58h] [rbp-A8h] BYREF
  VARIANTARG v33; // [rsp+60h] [rbp-A0h] BYREF
  VARIANTARG v34; // [rsp+78h] [rbp-88h] BYREF
  VARIANTARG pvarg; // [rsp+90h] [rbp-70h] BYREF
  CHAR Str[256]; // [rsp+B0h] [rbp-50h] BYREF
  char v37; // [rsp+1B0h] [rbp+B0h] BYREF
  CHAR MultiByteStr[272]; // [rsp+1C0h] [rbp+C0h] BYREF

  memset_0(MultiByteStr, 0, 0x101u);
  VariantInit(&pvarg);
  VariantInit(&v34);
  VariantInit(&v33);
  v29 = 0;
  v32 = 0;
  v31 = 0;
  v30 = 0;
  memset_0(Str, 0, 0x101u);
  SingleNode = getSingleNode(a1, L"mschapv2userpropertiesv1:EapType[1]", &v29);
  if ( SingleNode )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_5;
    v11 = 46;
    goto LABEL_4;
  }
  v12 = LocalAlloc(0x40u, 0x318u);
  v13 = v12;
  if ( !v12 )
  {
    SingleNode = 14;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_40;
    v15 = 47;
LABEL_10:
    WPP_SF_d(v14[2], v15, WPP_47d2ae5abdbe322473422603828ba620_Traceguids, SingleNode);
    goto LABEL_40;
  }
  *v12 = 3;
  v12[2] = 0;
  SingleNode = getSingleNode(v29, L"mschapv2userpropertiesv1:Password[1]", &v31);
  if ( SingleNode )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      v11 = 48;
LABEL_4:
      WPP_SF_(v10[2], v11, WPP_47d2ae5abdbe322473422603828ba620_Traceguids);
      goto LABEL_5;
    }
    goto LABEL_5;
  }
  if ( !((unsigned int (__fastcall *)(struct IXMLDOMNode *, VARIANTARG *))v31->lpVtbl->get_nodeTypedValue)(v31, &v34)
    && v34.vt == 8
    && !WideCharToMultiByte(0, 0, v34.bstrVal, -1, MultiByteStr, 257, 0, 0) )
  {
    SingleNode = GetLastError();
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_40;
    v15 = 49;
    goto LABEL_10;
  }
  v16 = (_OWORD *)((char *)v13 + 269);
  v17 = MultiByteStr;
  v18 = 2;
  do
  {
    *v16 = *(_OWORD *)v17;
    v16[1] = *((_OWORD *)v17 + 1);
    v16[2] = *((_OWORD *)v17 + 2);
    v16[3] = *((_OWORD *)v17 + 3);
    v16[4] = *((_OWORD *)v17 + 4);
    v16[5] = *((_OWORD *)v17 + 5);
    v16[6] = *((_OWORD *)v17 + 6);
    v16[7] = *((_OWORD *)v17 + 7);
    v16 += 8;
    v17 += 128;
    --v18;
  }
  while ( v18 );
  *(_BYTE *)v16 = *v17;
  SingleNode = getSingleNode(v29, L"mschapv2userpropertiesv1:Username[1]", &v32);
  if ( SingleNode )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      v11 = 50;
      goto LABEL_4;
    }
LABEL_5:
    if ( (SingleNode & 0x1FFF0000) == 0x70000 )
      SingleNode = (unsigned __int16)SingleNode;
    goto LABEL_40;
  }
  if ( !((unsigned int (__fastcall *)(struct IXMLDOMNode *, VARIANTARG *))v32->lpVtbl->get_nodeTypedValue)(v32, &pvarg)
    && pvarg.vt == 8 )
  {
    if ( !WideCharToMultiByte(0, 0, pvarg.bstrVal, -1, Str, 257, 0, 0) )
    {
      SingleNode = GetLastError();
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_40;
      v15 = 51;
      goto LABEL_10;
    }
    v19 = v13 + 3;
    if ( strpbrk(Str, "@\\") )
    {
      v20 = strchr(Str, 92);
      v21 = v20;
      if ( v20 )
      {
        memcpy_0(v13 + 3, v20 + 1, &v37 - v20);
        memcpy_0((char *)v13 + 526, Str, v21 - Str);
      }
      else
      {
        v24 = Str;
        v25 = 2;
        do
        {
          *v19 = *(_OWORD *)v24;
          v19[1] = *((_OWORD *)v24 + 1);
          v19[2] = *((_OWORD *)v24 + 2);
          v19[3] = *((_OWORD *)v24 + 3);
          v19[4] = *((_OWORD *)v24 + 4);
          v19[5] = *((_OWORD *)v24 + 5);
          v19[6] = *((_OWORD *)v24 + 6);
          v19[7] = *((_OWORD *)v24 + 7);
          v19 += 8;
          v24 += 128;
          --v25;
        }
        while ( v25 );
        *(_BYTE *)v19 = *v24;
      }
      goto LABEL_32;
    }
    v26 = Str;
    v27 = 2;
    do
    {
      *v19 = *(_OWORD *)v26;
      v19[1] = *((_OWORD *)v26 + 1);
      v19[2] = *((_OWORD *)v26 + 2);
      v19[3] = *((_OWORD *)v26 + 3);
      v19[4] = *((_OWORD *)v26 + 4);
      v19[5] = *((_OWORD *)v26 + 5);
      v19[6] = *((_OWORD *)v26 + 6);
      v19[7] = *((_OWORD *)v26 + 7);
      v19 += 8;
      v26 += 128;
      --v27;
    }
    while ( v27 );
    *(_BYTE *)v19 = *v26;
  }
  v28 = getSingleNode(v29, L"mschapv2userpropertiesv1:LogonDomain[1]", &v30);
  if ( v28 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_47d2ae5abdbe322473422603828ba620_Traceguids);
    if ( v28 == -2147024882 )
    {
      SingleNode = 14;
      goto LABEL_40;
    }
  }
  else if ( !((unsigned int (__fastcall *)(struct IXMLDOMNode *, VARIANTARG *))v30->lpVtbl->get_nodeTypedValue)(
               v30,
               &v33)
         && v33.vt == 8
         && !WideCharToMultiByte(0, 0, v33.bstrVal, -1, (LPSTR)v13 + 526, 257, 0, 0) )
  {
    SingleNode = GetLastError();
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_40;
    v15 = 53;
    goto LABEL_10;
  }
LABEL_32:
  SingleNode = 0;
  if ( (*((_BYTE *)a6 + 4) & 2) == 0 )
  {
    if ( (a3 & 4) != 0 )
      v13[1] = v13[1] & 0xFFFFFFEE | 0x10;
    if ( a3 < 0 )
      v13[1] |= 0x20u;
  }
  v22 = v13[1];
  if ( (v22 & 0x30) == 0 )
    v13[1] = v22 | 1;
  *a7 = (struct _EAPMSCHAPv2_USER_PROPERTIES *)v13;
LABEL_40:
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v30);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v31);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v32);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v29);
  VariantClear(&v33);
  VariantClear(&v34);
  VariantClear(&pvarg);
  return SingleNode;
}

```

## disassembly

```asm
0x18001d330  mov     [rsp-8+arg_8], rbx
0x18001d335  mov     [rsp-8+arg_10], rsi
0x18001d33a  push    rbp
0x18001d33b  push    rdi
0x18001d33c  push    r13
0x18001d33e  push    r14
0x18001d340  push    r15
0x18001d342  lea     rbp, [rsp-1E0h]
0x18001d34a  sub     rsp, 2E0h
0x18001d351  mov     rax, cs:__security_cookie
0x18001d358  xor     rax, rsp
0x18001d35b  mov     [rbp+200h+var_30], rax
0x18001d362  mov     r14d, r8d
0x18001d365  mov     rbx, rcx
0x18001d368  mov     r15, [rbp+200h+arg_30]
0x18001d36f  mov     r13d, 101h
0x18001d375  mov     r8d, r13d; Size
0x18001d378  xor     edx, edx; Val
0x18001d37a  lea     rcx, [rbp+200h+MultiByteStr]; void *
0x18001d381  call    memset_0
0x18001d386  lea     rcx, [rbp+200h+pvarg]; pvarg
0x18001d38a  call    cs:__imp_VariantInit
0x18001d390  nop
0x18001d391  lea     rcx, [rsp+300h+var_288]; pvarg
0x18001d396  call    cs:__imp_VariantInit
0x18001d39c  nop
0x18001d39d  lea     rcx, [rsp+300h+var_2A0]; pvarg
0x18001d3a2  call    cs:__imp_VariantInit
0x18001d3a8  nop
0x18001d3a9  mov     [rsp+300h+var_2C0], 0
0x18001d3b2  mov     [rsp+300h+var_2A8], 0
0x18001d3bb  mov     [rsp+300h+var_2B0], 0
0x18001d3c4  mov     [rsp+300h+var_2B8], 0
0x18001d3cd  mov     r8d, r13d; Size
0x18001d3d0  xor     edx, edx; Val
0x18001d3d2  lea     rcx, [rbp+200h+Str]; void *
0x18001d3d6  call    memset_0
0x18001d3db  lea     r8, [rsp+300h+var_2C0]; struct IXMLDOMNode **
0x18001d3e0  lea     rdx, aMschapv2userpr_1; "mschapv2userpropertiesv1:EapType[1]"
0x18001d3e7  mov     rcx, rbx; struct IXMLDOMNode *
0x18001d3ea  call    ?getSingleNode@@YAJPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; getSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18001d3ef  mov     ebx, eax
0x18001d3f1  test    eax, eax
0x18001d3f3  jz      short loc_18001D437
0x18001d3f5  lea     rax, WPP_GLOBAL_Control
0x18001d3fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d403  cmp     rcx, rax
0x18001d406  jz      short loc_18001D41D
0x18001d408  mov     edx, 2Eh ; '.'
0x18001d40d  lea     r8, WPP_47d2ae5abdbe322473422603828ba620_Traceguids
0x18001d414  mov     rcx, [rcx+10h]
0x18001d418  call    WPP_SF_
0x18001d41d  mov     eax, ebx
0x18001d41f  and     eax, 1FFF0000h
0x18001d424  cmp     eax, 70000h
0x18001d429  jnz     loc_18001D726
0x18001d42f  movzx   ebx, bx
0x18001d432  jmp     loc_18001D726
0x18001d437  mov     edx, 318h; uBytes
0x18001d43c  mov     ecx, 40h ; '@'; uFlags
0x18001d441  call    cs:__imp_LocalAlloc
0x18001d447  mov     rdi, rax
0x18001d44a  test    rax, rax
0x18001d44d  jnz     short loc_18001D484
0x18001d44f  lea     ebx, [rax+0Eh]
0x18001d452  lea     rax, WPP_GLOBAL_Control
0x18001d459  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d460  cmp     rcx, rax
0x18001d463  jz      loc_18001D726
0x18001d469  lea     edx, [rdi+2Fh]
0x18001d46c  mov     r9d, ebx
0x18001d46f  lea     r8, WPP_47d2ae5abdbe322473422603828ba620_Traceguids
0x18001d476  mov     rcx, [rcx+10h]
0x18001d47a  call    WPP_SF_d
0x18001d47f  jmp     loc_18001D726
0x18001d484  mov     dword ptr [rax], 3
0x18001d48a  mov     dword ptr [rax+8], 0
0x18001d491  lea     r8, [rsp+300h+var_2B0]; struct IXMLDOMNode **
0x18001d496  lea     rdx, aMschapv2userpr_3; "mschapv2userpropertiesv1:Password[1]"
0x18001d49d  mov     rcx, [rsp+300h+var_2C0]; struct IXMLDOMNode *
0x18001d4a2  call    ?getSingleNode@@YAJPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; getSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18001d4a7  mov     ebx, eax
0x18001d4a9  test    eax, eax
0x18001d4ab  jz      short loc_18001D4CE
0x18001d4ad  lea     rax, WPP_GLOBAL_Control
0x18001d4b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d4bb  cmp     rcx, rax
0x18001d4be  jz      loc_18001D41D
0x18001d4c4  mov     edx, 30h ; '0'
0x18001d4c9  jmp     loc_18001D40D
0x18001d4ce  mov     rcx, [rsp+300h+var_2B0]
0x18001d4d3  mov     rax, [rcx]
0x18001d4d6  lea     rdx, [rsp+300h+var_288]
0x18001d4db  mov     rax, [rax+0F0h]
0x18001d4e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d4e7  or      esi, 0FFFFFFFFh
0x18001d4ea  test    eax, eax
0x18001d4ec  jnz     short loc_18001D555
0x18001d4ee  cmp     word ptr [rsp+300h+var_288], 8
0x18001d4f4  jnz     short loc_18001D555
0x18001d4f6  mov     [rsp+300h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18001d4ff  mov     [rsp+300h+lpDefaultChar], 0; lpDefaultChar
0x18001d508  mov     [rsp+300h+cbMultiByte], r13d; cbMultiByte
0x18001d50d  lea     rax, [rbp+200h+MultiByteStr]
0x18001d514  mov     [rsp+300h+lpMultiByteStr], rax; lpMultiByteStr
0x18001d519  mov     r9d, esi; cchWideChar
0x18001d51c  mov     r8, qword ptr [rbp+200h+var_288+8]; lpWideCharStr
0x18001d520  xor     edx, edx; dwFlags
0x18001d522  xor     ecx, ecx; CodePage
0x18001d524  call    cs:__imp_WideCharToMultiByte
0x18001d52a  test    eax, eax
0x18001d52c  jnz     short loc_18001D555
0x18001d52e  call    cs:__imp_GetLastError
0x18001d534  mov     ebx, eax
0x18001d536  lea     rax, WPP_GLOBAL_Control
0x18001d53d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d544  cmp     rcx, rax
0x18001d547  jz      loc_18001D726
0x18001d54d  lea     edx, [rsi+32h]
0x18001d550  jmp     loc_18001D46C
0x18001d555  lea     rcx, [rdi+10Dh]
0x18001d55c  lea     rax, [rbp+200h+MultiByteStr]
0x18001d563  mov     edx, 2
0x18001d568  lea     r13d, [rdx+7Eh]
0x18001d56c  movups  xmm0, xmmword ptr [rax]
0x18001d56f  movups  xmmword ptr [rcx], xmm0
0x18001d572  movups  xmm1, xmmword ptr [rax+10h]
0x18001d576  movups  xmmword ptr [rcx+10h], xmm1
0x18001d57a  movups  xmm0, xmmword ptr [rax+20h]
0x18001d57e  movups  xmmword ptr [rcx+20h], xmm0
0x18001d582  movups  xmm1, xmmword ptr [rax+30h]
0x18001d586  movups  xmmword ptr [rcx+30h], xmm1
0x18001d58a  movups  xmm0, xmmword ptr [rax+40h]
0x18001d58e  movups  xmmword ptr [rcx+40h], xmm0
0x18001d592  movups  xmm1, xmmword ptr [rax+50h]
0x18001d596  movups  xmmword ptr [rcx+50h], xmm1
0x18001d59a  movups  xmm0, xmmword ptr [rax+60h]
0x18001d59e  movups  xmmword ptr [rcx+60h], xmm0
0x18001d5a2  movups  xmm1, xmmword ptr [rax+70h]
0x18001d5a6  movups  xmmword ptr [rcx+70h], xmm1
0x18001d5aa  add     rcx, r13
0x18001d5ad  add     rax, r13
0x18001d5b0  sub     rdx, 1
0x18001d5b4  jnz     short loc_18001D56C
0x18001d5b6  mov     al, [rax]
0x18001d5b8  mov     [rcx], al
0x18001d5ba  lea     r8, [rsp+300h+var_2A8]; struct IXMLDOMNode **
0x18001d5bf  lea     rdx, aMschapv2userpr_2; "mschapv2userpropertiesv1:Username[1]"
0x18001d5c6  mov     rcx, [rsp+300h+var_2C0]; struct IXMLDOMNode *
0x18001d5cb  call    ?getSingleNode@@YAJPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; getSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18001d5d0  mov     ebx, eax
0x18001d5d2  test    eax, eax
0x18001d5d4  jz      short loc_18001D5F7
0x18001d5d6  lea     rax, WPP_GLOBAL_Control
0x18001d5dd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d5e4  cmp     rcx, rax
0x18001d5e7  jz      loc_18001D41D
0x18001d5ed  mov     edx, 32h ; '2'
0x18001d5f2  jmp     loc_18001D40D
0x18001d5f7  mov     rcx, [rsp+300h+var_2A8]
0x18001d5fc  mov     rax, [rcx]
0x18001d5ff  lea     rdx, [rbp+200h+pvarg]
0x18001d603  mov     rax, [rax+0F0h]
0x18001d60a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d60f  test    eax, eax
0x18001d611  jnz     loc_18001D854
0x18001d617  cmp     word ptr [rbp+200h+pvarg], 8
0x18001d61c  jnz     loc_18001D854
0x18001d622  mov     [rsp+300h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18001d62b  mov     [rsp+300h+lpDefaultChar], 0; lpDefaultChar
0x18001d634  mov     [rsp+300h+cbMultiByte], 101h; cbMultiByte
0x18001d63c  lea     rax, [rbp+200h+Str]
0x18001d640  mov     [rsp+300h+lpMultiByteStr], rax; lpMultiByteStr
0x18001d645  mov     r9d, esi; cchWideChar
0x18001d648  mov     r8, qword ptr [rbp+200h+pvarg+8]; lpWideCharStr
0x18001d64c  xor     edx, edx; dwFlags
0x18001d64e  xor     ecx, ecx; CodePage
0x18001d650  call    cs:__imp_WideCharToMultiByte
0x18001d656  test    eax, eax
0x18001d658  jnz     short loc_18001D683
0x18001d65a  call    cs:__imp_GetLastError
0x18001d660  mov     ebx, eax
0x18001d662  lea     rax, WPP_GLOBAL_Control
0x18001d669  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d670  cmp     rcx, rax
0x18001d673  jz      loc_18001D726
0x18001d679  mov     edx, 33h ; '3'
0x18001d67e  jmp     loc_18001D46C
0x18001d683  lea     rbx, [rdi+0Ch]
0x18001d687  lea     rdx, Control; "@\\"
0x18001d68e  lea     rcx, [rbp+200h+Str]; Str
0x18001d692  call    cs:__imp_strpbrk
0x18001d698  test    rax, rax
0x18001d69b  jz      loc_18001D7FD
0x18001d6a1  mov     edx, 5Ch ; '\'; Val
0x18001d6a6  lea     rcx, [rbp+200h+Str]; Str
0x18001d6aa  call    cs:__imp_strchr
0x18001d6b0  mov     rsi, rax
0x18001d6b3  test    rax, rax
0x18001d6b6  jz      loc_18001D7A1
0x18001d6bc  lea     r8, [rbp+200h+var_150]
0x18001d6c3  sub     r8, rax; Size
0x18001d6c6  lea     rdx, [rax+1]; Src
0x18001d6ca  mov     rcx, rbx; void *
0x18001d6cd  call    memcpy_0
0x18001d6d2  lea     rax, [rbp+200h+Str]
0x18001d6d6  sub     rsi, rax
0x18001d6d9  lea     rcx, [rdi+20Eh]; void *
0x18001d6e0  mov     r8, rsi; Size
0x18001d6e3  lea     rdx, [rbp+200h+Str]; Src
0x18001d6e7  call    memcpy_0
0x18001d6ec  xor     ebx, ebx
0x18001d6ee  mov     rax, [rbp+200h+arg_28]
0x18001d6f5  test    byte ptr [rax+4], 2
0x18001d6f9  jnz     short loc_18001D716
0x18001d6fb  test    r14b, 4
0x18001d6ff  jz      short loc_18001D70D
0x18001d701  mov     eax, [rdi+4]
0x18001d704  and     eax, 0FFFFFFFEh
0x18001d707  or      eax, 10h
0x18001d70a  mov     [rdi+4], eax
0x18001d70d  test    r13b, r14b
0x18001d710  jz      short loc_18001D716
0x18001d712  or      dword ptr [rdi+4], 20h
0x18001d716  mov     eax, [rdi+4]
0x18001d719  test    al, 30h
0x18001d71b  jnz     short loc_18001D723
0x18001d71d  or      eax, 1
0x18001d720  mov     [rdi+4], eax
0x18001d723  mov     [r15], rdi
0x18001d726  lea     rcx, [rsp+300h+var_2B8]
0x18001d72b  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18001d730  nop
0x18001d731  lea     rcx, [rsp+300h+var_2B0]
0x18001d736  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18001d73b  nop
0x18001d73c  lea     rcx, [rsp+300h+var_2A8]
0x18001d741  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18001d746  nop
0x18001d747  lea     rcx, [rsp+300h+var_2C0]
0x18001d74c  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18001d751  nop
0x18001d752  lea     rcx, [rsp+300h+var_2A0]; pvarg
0x18001d757  call    cs:__imp_VariantClear
0x18001d75d  nop
0x18001d75e  lea     rcx, [rsp+300h+var_288]; pvarg
0x18001d763  call    cs:__imp_VariantClear
0x18001d769  nop
0x18001d76a  lea     rcx, [rbp+200h+pvarg]; pvarg
0x18001d76e  call    cs:__imp_VariantClear
0x18001d774  mov     eax, ebx
0x18001d776  mov     rcx, [rbp+200h+var_30]
0x18001d77d  xor     rcx, rsp; StackCookie
0x18001d780  call    __security_check_cookie
0x18001d785  lea     r11, [rsp+300h+var_20]
0x18001d78d  mov     rbx, [r11+38h]
0x18001d791  mov     rsi, [r11+40h]
0x18001d795  mov     rsp, r11
0x18001d798  pop     r15
0x18001d79a  pop     r14
0x18001d79c  pop     r13
0x18001d79e  pop     rdi
0x18001d79f  pop     rbp
0x18001d7a0  retn
0x18001d7a1  lea     rax, [rbp+200h+Str]
0x18001d7a5  mov     ecx, 2
0x18001d7aa  movups  xmm0, xmmword ptr [rax]
0x18001d7ad  movups  xmmword ptr [rbx], xmm0
0x18001d7b0  movups  xmm1, xmmword ptr [rax+10h]
0x18001d7b4  movups  xmmword ptr [rbx+10h], xmm1
0x18001d7b8  movups  xmm0, xmmword ptr [rax+20h]
0x18001d7bc  movups  xmmword ptr [rbx+20h], xmm0
0x18001d7c0  movups  xmm1, xmmword ptr [rax+30h]
0x18001d7c4  movups  xmmword ptr [rbx+30h], xmm1
0x18001d7c8  movups  xmm0, xmmword ptr [rax+40h]
0x18001d7cc  movups  xmmword ptr [rbx+40h], xmm0
0x18001d7d0  movups  xmm1, xmmword ptr [rax+50h]
0x18001d7d4  movups  xmmword ptr [rbx+50h], xmm1
0x18001d7d8  movups  xmm0, xmmword ptr [rax+60h]
0x18001d7dc  movups  xmmword ptr [rbx+60h], xmm0
0x18001d7e0  movups  xmm1, xmmword ptr [rax+70h]
0x18001d7e4  movups  xmmword ptr [rbx+70h], xmm1
0x18001d7e8  add     rbx, r13
0x18001d7eb  add     rax, r13
0x18001d7ee  sub     rcx, 1
0x18001d7f2  jnz     short loc_18001D7AA
0x18001d7f4  mov     al, [rax]
0x18001d7f6  mov     [rbx], al
0x18001d7f8  jmp     loc_18001D6EC
0x18001d7fd  lea     rax, [rbp+200h+Str]
0x18001d801  mov     ecx, 2
0x18001d806  movups  xmm0, xmmword ptr [rax]
0x18001d809  movups  xmmword ptr [rbx], xmm0
0x18001d80c  movups  xmm1, xmmword ptr [rax+10h]
0x18001d810  movups  xmmword ptr [rbx+10h], xmm1
0x18001d814  movups  xmm0, xmmword ptr [rax+20h]
0x18001d818  movups  xmmword ptr [rbx+20h], xmm0
0x18001d81c  movups  xmm1, xmmword ptr [rax+30h]
0x18001d820  movups  xmmword ptr [rbx+30h], xmm1
0x18001d824  movups  xmm0, xmmword ptr [rax+40h]
  ... truncated ...
```
