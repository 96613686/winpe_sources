# IsRegistryCertAuthType

- ea: `0x1800998e4`
- end: `0x180099d38`
- name: `IsRegistryCertAuthType`
- size: `1108`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180082fa0`
- `0x1800a5c08`

## callees

- `0x18004e580`
- `0x18004e984`
- `0x18007efdc`
- `0x18007f140`
- `0x180098f20`
- `0x1800998e4`
- `0x1800a7778`
- `0x1800ba4bc`
- `0x1800e0010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180099cdf`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180099cdf`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800999d7`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800999d7`
- `OLEAUT32!__imp_VariantClear` at `0x180099bf3`
- `OLEAUT32!__imp_VariantClear` at `0x180099bf3`
- `eappcfg!EapHostPeerConfigBlob2Xml` at `0x180099a4f`
- `eappcfg!EapHostPeerConfigBlob2Xml` at `0x180099a4f`

## string_xrefs

- `0x180099adb`: `//EapHostConfig:Config`

## pseudocode

```c
__int64 __fastcall IsRegistryCertAuthType(EAP_METHOD_TYPE *a1, DWORD a2, BYTE *a3)
{
  _QWORD *v6; // rcx
  bool v7; // zf
  unsigned int v8; // edi
  int v9; // r15d
  HRESULT v10; // eax
  DWORD v11; // ebx
  __int64 v12; // rcx
  struct IXMLDOMDocument2Vtbl *lpVtbl; // rax
  __int64 v14; // r8
  __int64 v15; // r8
  __int64 v16; // r8
  __int64 v17; // r8
  __int64 v18; // r8
  __int64 v19; // r8
  __int64 v20; // r8
  __int64 v21; // r8
  __int64 v22; // r8
  __int64 v23; // r9
  IXMLDOMDocument2 *ppConfigDoc; // [rsp+30h] [rbp-59h] BYREF
  __int64 v26; // [rsp+38h] [rbp-51h] BYREF
  __int64 v27; // [rsp+40h] [rbp-49h] BYREF
  __int64 v28; // [rsp+48h] [rbp-41h] BYREF
  __int64 v29; // [rsp+50h] [rbp-39h] BYREF
  __int64 v30; // [rsp+58h] [rbp-31h] BYREF
  __int64 v31; // [rsp+60h] [rbp-29h] BYREF
  EAP_ERROR *pEapError; // [rsp+68h] [rbp-21h] BYREF
  VARIANTARG pvarg; // [rsp+70h] [rbp-19h] BYREF
  EAP_METHOD_TYPE eapMethodType; // [rsp+90h] [rbp+7h] BYREF
  IRecordInfo *pRecInfo; // [rsp+A0h] [rbp+17h]
  __int64 v36; // [rsp+F0h] [rbp+67h] BYREF
  __int64 v37; // [rsp+108h] [rbp+7Fh] BYREF

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 124, WPP_425b3625ab793a6219f8039beff53b24_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  v7 = a1->eapType.type == 13;
  pEapError = 0;
  v8 = 0;
  ppConfigDoc = 0;
  v9 = 0;
  v27 = 0;
  v28 = 0;
  v26 = 0;
  v29 = 0;
  v36 = 0;
  v30 = 0;
  v37 = 0;
  v31 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  if ( v7 || a1->eapType.type == 25 )
  {
    v10 = CoInitializeEx(0, 0);
    if ( v10 >= 0 )
    {
      if ( (unsigned int)v10 <= 1 )
        v9 = 1;
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
           && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        126,
        WPP_425b3625ab793a6219f8039beff53b24_Traceguids,
        (unsigned int)v10);
    }
    eapMethodType = *a1;
    v11 = EapHostPeerConfigBlob2Xml(0, &eapMethodType, a2, a3, &ppConfigDoc, &pEapError);
    RasFreeEapConfigErrorMemory(pEapError);
    if ( !v11 && (int)VariantFromString(v12, &pvarg) >= 0 )
    {
      lpVtbl = ppConfigDoc->lpVtbl;
      eapMethodType = *(EAP_METHOD_TYPE *)&pvarg.vt;
      pRecInfo = pvarg.pRecInfo;
      if ( ((int (__fastcall *)(IXMLDOMDocument2 *, const wchar_t *, EAP_METHOD_TYPE *))lpVtbl->setProperty)(
             ppConfigDoc,
             L"SelectionNamespaces",
             &eapMethodType) >= 0
        && ((__int64 (__fastcall *)(IXMLDOMDocument2 *, GUID *, __int64 *))ppConfigDoc->lpVtbl->QueryInterface)(
             ppConfigDoc,
             &IID_IXMLDOMNode,
             &v27) >= 0
        && (int)GetSingleNode(v27, L"//EapHostConfig:Config", v14, &v28) >= 0
        && (int)GetSingleNode(v28, L"BaseEap:Eap", v15, &v26) >= 0 )
      {
        if ( a1->eapType.type == 13 )
        {
          if ( (int)GetSingleNode(v26, L"EapTls:EapType", v16, &v36) >= 0
            && (int)GetSingleNode(v36, L"EapTls:CredentialsSource", v17, &v37) >= 0
            && (int)GetSingleNode(v37, L"EapTls:CertificateStore", v18, &v31) >= 0 )
          {
            v8 = 1;
          }
        }
        else if ( a1->eapType.type == 25
               && (int)GetSingleNode(v26, L"Peap:EapType", v16, &v36) >= 0
               && (int)GetSingleNode(v36, L"BaseEap:Eap", v19, &v29) >= 0
               && (int)GetSingleNode(v29, L"EapTls:EapType", v20, &v30) >= 0
               && (int)GetSingleNode(v30, L"EapTls:CredentialsSource", v21, &v37) >= 0
               && (int)GetSingleNode(v37, L"EapTls:CertificateStore", v22, &v31) >= 0 )
        {
          v8 = 1;
        }
      }
    }
  }
  else if ( v6 != &WPP_GLOBAL_Control && (*((_DWORD *)v6 + 7) & 0x800) != 0 && *((_BYTE *)v6 + 25) >= 2u )
  {
    WPP_SF_Dd(v6[2], 125, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, a1->eapType.type, 87);
  }
  VariantClear(&pvarg);
  if ( ppConfigDoc )
  {
    ((void (__fastcall *)(IXMLDOMDocument2 *))ppConfigDoc->lpVtbl->Release)(ppConfigDoc);
    ppConfigDoc = 0;
  }
  if ( v27 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    v27 = 0;
  }
  if ( v28 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    v28 = 0;
  }
  if ( v26 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    v26 = 0;
  }
  if ( v29 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    v29 = 0;
  }
  if ( v36 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    v36 = 0;
  }
  if ( v30 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    v30 = 0;
  }
  if ( v37 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    v37 = 0;
  }
  if ( v31 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    v31 = 0;
  }
  if ( v9 )
    CoUninitialize();
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    LOBYTE(v23) = v8 != 0;
    WPP_SF_c(*((_QWORD *)WPP_GLOBAL_Control + 2), 127, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v23);
  }
  return v8;
}

```

## disassembly

```asm
0x1800998e4  mov     [rsp-8+arg_8], rbx
0x1800998e9  push    rbp
0x1800998ea  push    rsi
0x1800998eb  push    rdi
0x1800998ec  push    r12
0x1800998ee  push    r13
0x1800998f0  push    r14
0x1800998f2  push    r15
0x1800998f4  lea     rbp, [rsp-27h]
0x1800998f9  sub     rsp, 0B0h
0x180099900  mov     rbx, r8
0x180099903  mov     r14d, edx
0x180099906  mov     rsi, rcx
0x180099909  mov     rcx, cs:WPP_GLOBAL_Control
0x180099910  lea     r13, WPP_GLOBAL_Control
0x180099917  cmp     rcx, r13
0x18009991a  jz      short loc_180099947
0x18009991c  test    dword ptr [rcx+1Ch], 800h
0x180099923  jz      short loc_180099947
0x180099925  cmp     byte ptr [rcx+19h], 6
0x180099929  jb      short loc_180099947
0x18009992b  mov     rcx, [rcx+10h]
0x18009992f  lea     r8, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x180099936  mov     edx, 7Ch ; '|'
0x18009993b  call    WPP_SF_
0x180099940  mov     rcx, cs:WPP_GLOBAL_Control
0x180099947  xor     r12d, r12d
0x18009994a  xor     eax, eax
0x18009994c  cmp     byte ptr [rsi], 0Dh
0x18009994f  xorps   xmm0, xmm0
0x180099952  mov     [rbp+57h+pEapError], r12
0x180099956  mov     edi, r12d
0x180099959  mov     [rbp+57h+var_B0], r12
0x18009995d  mov     r15d, r12d
0x180099960  mov     [rbp+57h+var_A0], r12
0x180099964  mov     [rbp+57h+var_98], r12
0x180099968  mov     [rbp+57h+var_A8], r12
0x18009996c  mov     [rbp+57h+var_90], r12
0x180099970  mov     [rbp+57h+arg_0], r12
0x180099974  mov     [rbp+57h+var_88], r12
0x180099978  mov     [rbp+57h+arg_18], r12
0x18009997c  mov     [rbp+57h+var_80], r12
0x180099980  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180099984  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180099988  jz      short loc_1800999D3
0x18009998a  cmp     byte ptr [rsi], 19h
0x18009998d  jz      short loc_1800999D3
0x18009998f  cmp     rcx, r13
0x180099992  jz      loc_180099BEF
0x180099998  test    dword ptr [rcx+1Ch], 800h
0x18009999f  jz      loc_180099BEF
0x1800999a5  cmp     byte ptr [rcx+19h], 2
0x1800999a9  jb      loc_180099BEF
0x1800999af  movzx   r9d, byte ptr [rsi]
0x1800999b3  lea     edx, [rax+7Dh]
0x1800999b6  mov     rcx, [rcx+10h]
0x1800999ba  lea     r8, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x1800999c1  mov     dword ptr [rsp+0E0h+ppConfigDoc], 57h ; 'W'
0x1800999c9  call    WPP_SF_Dd
0x1800999ce  jmp     loc_180099BEF
0x1800999d3  xor     edx, edx; dwCoInit
0x1800999d5  xor     ecx, ecx; pvReserved
0x1800999d7  call    cs:__imp_CoInitializeEx
0x1800999dd  mov     r13d, 1
0x1800999e3  test    eax, eax
0x1800999e5  jns     short loc_180099A22
0x1800999e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800999ee  lea     rdx, WPP_GLOBAL_Control
0x1800999f5  cmp     rcx, rdx
0x1800999f8  jz      short loc_180099A29
0x1800999fa  test    dword ptr [rcx+1Ch], 800h
0x180099a01  jz      short loc_180099A29
0x180099a03  cmp     byte ptr [rcx+19h], 2
0x180099a07  jb      short loc_180099A29
0x180099a09  mov     rcx, [rcx+10h]
0x180099a0d  lea     edx, [r13+7Dh]
0x180099a11  mov     r9d, eax
0x180099a14  lea     r8, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x180099a1b  call    WPP_SF_d
0x180099a20  jmp     short loc_180099A29
0x180099a22  cmp     eax, r13d
0x180099a25  cmovbe  r15d, r13d
0x180099a29  movaps  xmm0, xmmword ptr [rsi]
0x180099a2c  lea     rax, [rbp+57h+pEapError]
0x180099a30  mov     [rsp+0E0h+ppEapError], rax; ppEapError
0x180099a35  lea     rdx, [rbp+57h+eapMethodType]; eapMethodType
0x180099a39  lea     rax, [rbp+57h+var_B0]
0x180099a3d  movdqa  xmmword ptr [rbp+57h+eapMethodType.eapType.type], xmm0
0x180099a42  mov     r9, rbx; pConfigIn
0x180099a45  mov     [rsp+0E0h+ppConfigDoc], rax; ppConfigDoc
0x180099a4a  mov     r8d, r14d; dwSizeOfConfigIn
0x180099a4d  xor     ecx, ecx; dwFlags
0x180099a4f  call    cs:__imp_EapHostPeerConfigBlob2Xml
0x180099a55  mov     rcx, [rbp+57h+pEapError]; pEapError
0x180099a59  mov     ebx, eax
0x180099a5b  call    RasFreeEapConfigErrorMemory
0x180099a60  test    ebx, ebx
0x180099a62  jnz     loc_180099BE8
0x180099a68  lea     rdx, [rbp+57h+pvarg]
0x180099a6c  call    VariantFromString
0x180099a71  test    eax, eax
0x180099a73  js      loc_180099BE8
0x180099a79  mov     rcx, [rbp+57h+var_B0]
0x180099a7d  lea     r8, [rbp+57h+eapMethodType]
0x180099a81  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x180099a85  lea     rdx, aSelectionnames; "SelectionNamespaces"
0x180099a8c  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x180099a91  mov     rax, [rcx]
0x180099a94  movaps  xmmword ptr [rbp+57h+eapMethodType.eapType.type], xmm0
0x180099a98  movsd   [rbp+57h+var_40], xmm1
0x180099a9d  mov     rax, [rax+280h]
0x180099aa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099aa9  test    eax, eax
0x180099aab  js      loc_180099BE8
0x180099ab1  mov     rcx, [rbp+57h+var_B0]
0x180099ab5  lea     r8, [rbp+57h+var_A0]
0x180099ab9  lea     rdx, IID_IXMLDOMNode
0x180099ac0  mov     rax, [rcx]
0x180099ac3  mov     rax, [rax]
0x180099ac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099acb  test    eax, eax
0x180099acd  js      loc_180099BE8
0x180099ad3  mov     rcx, [rbp+57h+var_A0]
0x180099ad7  lea     r9, [rbp+57h+var_98]
0x180099adb  lea     rdx, aEaphostconfigC; "//EapHostConfig:Config"
0x180099ae2  call    GetSingleNode
0x180099ae7  test    eax, eax
0x180099ae9  js      loc_180099BE8
0x180099aef  mov     rcx, [rbp+57h+var_98]
0x180099af3  lea     r9, [rbp+57h+var_A8]
0x180099af7  lea     rdx, aBaseeapEap; "BaseEap:Eap"
0x180099afe  call    GetSingleNode
0x180099b03  test    eax, eax
0x180099b05  js      loc_180099BE8
0x180099b0b  cmp     byte ptr [rsi], 0Dh
0x180099b0e  jnz     short loc_180099B69
0x180099b10  mov     rcx, [rbp+57h+var_A8]
0x180099b14  lea     r9, [rbp+57h+arg_0]
0x180099b18  lea     rdx, aEaptlsEaptype; "EapTls:EapType"
0x180099b1f  call    GetSingleNode
0x180099b24  test    eax, eax
0x180099b26  js      loc_180099BE8
0x180099b2c  mov     rcx, [rbp+57h+arg_0]
0x180099b30  lea     r9, [rbp+57h+arg_18]
0x180099b34  lea     rdx, aEaptlsCredenti; "EapTls:CredentialsSource"
0x180099b3b  call    GetSingleNode
0x180099b40  test    eax, eax
0x180099b42  js      loc_180099BE8
0x180099b48  mov     rcx, [rbp+57h+arg_18]
0x180099b4c  lea     r9, [rbp+57h+var_80]
0x180099b50  lea     rdx, aEaptlsCertific; "EapTls:CertificateStore"
0x180099b57  call    GetSingleNode
0x180099b5c  test    eax, eax
0x180099b5e  js      loc_180099BE8
0x180099b64  mov     edi, r13d
0x180099b67  jmp     short loc_180099BE8
0x180099b69  cmp     byte ptr [rsi], 19h
0x180099b6c  jnz     short loc_180099BE8
0x180099b6e  mov     rcx, [rbp+57h+var_A8]
0x180099b72  lea     r9, [rbp+57h+arg_0]
0x180099b76  lea     rdx, aPeapEaptype; "Peap:EapType"
0x180099b7d  call    GetSingleNode
0x180099b82  test    eax, eax
0x180099b84  js      short loc_180099BE8
0x180099b86  mov     rcx, [rbp+57h+arg_0]
0x180099b8a  lea     r9, [rbp+57h+var_90]
0x180099b8e  lea     rdx, aBaseeapEap; "BaseEap:Eap"
0x180099b95  call    GetSingleNode
0x180099b9a  test    eax, eax
0x180099b9c  js      short loc_180099BE8
0x180099b9e  mov     rcx, [rbp+57h+var_90]
0x180099ba2  lea     r9, [rbp+57h+var_88]
0x180099ba6  lea     rdx, aEaptlsEaptype; "EapTls:EapType"
0x180099bad  call    GetSingleNode
0x180099bb2  test    eax, eax
0x180099bb4  js      short loc_180099BE8
0x180099bb6  mov     rcx, [rbp+57h+var_88]
0x180099bba  lea     r9, [rbp+57h+arg_18]
0x180099bbe  lea     rdx, aEaptlsCredenti; "EapTls:CredentialsSource"
0x180099bc5  call    GetSingleNode
0x180099bca  test    eax, eax
0x180099bcc  js      short loc_180099BE8
0x180099bce  mov     rcx, [rbp+57h+arg_18]
0x180099bd2  lea     r9, [rbp+57h+var_80]
0x180099bd6  lea     rdx, aEaptlsCertific; "EapTls:CertificateStore"
0x180099bdd  call    GetSingleNode
0x180099be2  test    eax, eax
0x180099be4  cmovns  edi, r13d
0x180099be8  lea     r13, WPP_GLOBAL_Control
0x180099bef  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180099bf3  call    cs:__imp_VariantClear
0x180099bf9  mov     rcx, [rbp+57h+var_B0]
0x180099bfd  test    rcx, rcx
0x180099c00  jz      short loc_180099C12
0x180099c02  mov     rax, [rcx]
0x180099c05  mov     rax, [rax+10h]
0x180099c09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099c0e  mov     [rbp+57h+var_B0], r12
0x180099c12  mov     rcx, [rbp+57h+var_A0]
0x180099c16  test    rcx, rcx
0x180099c19  jz      short loc_180099C2B
0x180099c1b  mov     rax, [rcx]
0x180099c1e  mov     rax, [rax+10h]
0x180099c22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099c27  mov     [rbp+57h+var_A0], r12
0x180099c2b  mov     rcx, [rbp+57h+var_98]
0x180099c2f  test    rcx, rcx
0x180099c32  jz      short loc_180099C44
0x180099c34  mov     rax, [rcx]
0x180099c37  mov     rax, [rax+10h]
0x180099c3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099c40  mov     [rbp+57h+var_98], r12
0x180099c44  mov     rcx, [rbp+57h+var_A8]
0x180099c48  test    rcx, rcx
0x180099c4b  jz      short loc_180099C5D
0x180099c4d  mov     rax, [rcx]
0x180099c50  mov     rax, [rax+10h]
0x180099c54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099c59  mov     [rbp+57h+var_A8], r12
0x180099c5d  mov     rcx, [rbp+57h+var_90]
0x180099c61  test    rcx, rcx
0x180099c64  jz      short loc_180099C76
0x180099c66  mov     rax, [rcx]
0x180099c69  mov     rax, [rax+10h]
0x180099c6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099c72  mov     [rbp+57h+var_90], r12
0x180099c76  mov     rcx, [rbp+57h+arg_0]
0x180099c7a  test    rcx, rcx
0x180099c7d  jz      short loc_180099C8F
0x180099c7f  mov     rax, [rcx]
0x180099c82  mov     rax, [rax+10h]
0x180099c86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099c8b  mov     [rbp+57h+arg_0], r12
0x180099c8f  mov     rcx, [rbp+57h+var_88]
0x180099c93  test    rcx, rcx
0x180099c96  jz      short loc_180099CA8
0x180099c98  mov     rax, [rcx]
0x180099c9b  mov     rax, [rax+10h]
0x180099c9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099ca4  mov     [rbp+57h+var_88], r12
0x180099ca8  mov     rcx, [rbp+57h+arg_18]
0x180099cac  test    rcx, rcx
0x180099caf  jz      short loc_180099CC1
0x180099cb1  mov     rax, [rcx]
0x180099cb4  mov     rax, [rax+10h]
0x180099cb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099cbd  mov     [rbp+57h+arg_18], r12
0x180099cc1  mov     rcx, [rbp+57h+var_80]
0x180099cc5  test    rcx, rcx
0x180099cc8  jz      short loc_180099CDA
0x180099cca  mov     rax, [rcx]
0x180099ccd  mov     rax, [rax+10h]
0x180099cd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099cd6  mov     [rbp+57h+var_80], r12
0x180099cda  test    r15d, r15d
0x180099cdd  jz      short loc_180099CE5
0x180099cdf  call    cs:__imp_CoUninitialize
0x180099ce5  mov     rcx, cs:WPP_GLOBAL_Control
0x180099cec  cmp     rcx, r13
0x180099cef  jz      short loc_180099D1B
0x180099cf1  test    dword ptr [rcx+1Ch], 800h
0x180099cf8  jz      short loc_180099D1B
0x180099cfa  cmp     byte ptr [rcx+19h], 6
0x180099cfe  jb      short loc_180099D1B
0x180099d00  mov     rcx, [rcx+10h]
0x180099d04  lea     r8, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x180099d0b  test    edi, edi
0x180099d0d  mov     edx, 7Fh
0x180099d12  setnz   r9b
0x180099d16  call    WPP_SF_c
0x180099d1b  mov     rbx, [rsp+0E0h+arg_8]
0x180099d23  mov     eax, edi
0x180099d25  add     rsp, 0B0h
0x180099d2c  pop     r15
0x180099d2e  pop     r14
0x180099d30  pop     r13
0x180099d32  pop     r12
0x180099d34  pop     rdi
0x180099d35  pop     rsi
0x180099d36  pop     rbp
0x180099d37  retn
```
