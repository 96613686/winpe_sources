# EapXmlChangeUseWinlogonCredsSetting

- ea: `0x18002e118`
- end: `0x18002e7b5`
- name: `EapXmlChangeUseWinlogonCredsSetting`
- size: `1693`
- prototype: `__int64 __usercall@<rax>(EAP_METHOD_TYPE *pEapMethodType@<rcx>, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800258c8`

## callees

- `0x180005440`
- `0x180010ae0`
- `0x18002dc94`
- `0x18002dd30`
- `0x18002e060`
- `0x18002e118`
- `0x180030010`

## import_xrefs

- `eappcfg!EapHostPeerConfigXml2Blob` at `0x18002e6a7`
- `eappcfg!EapHostPeerConfigXml2Blob` at `0x18002e6a7`
- `eappcfg!EapHostPeerConfigBlob2Xml` at `0x18002e1f5`
- `eappcfg!EapHostPeerConfigBlob2Xml` at `0x18002e1f5`
- `eappcfg!EapHostPeerFreeErrorMemory` at `0x18002e685`
- `eappcfg!EapHostPeerFreeErrorMemory` at `0x18002e73e`
- `eappcfg!EapHostPeerFreeErrorMemory` at `0x18002e685`
- `eappcfg!EapHostPeerFreeErrorMemory` at `0x18002e73e`
- `eappcfg!EapHostPeerFreeMemory` at `0x18002e74c`
- `eappcfg!EapHostPeerFreeMemory` at `0x18002e74c`

## pseudocode

```c
__int64 __fastcall EapXmlChangeUseWinlogonCredsSetting(
        EAP_METHOD_TYPE *pEapMethodType,
        int a2,
        DWORD a3,
        BYTE *a4,
        DWORD *a5,
        BYTE **a6,
        int *a7)
{
  int v7; // esi
  int v10; // edi
  BYTE **v11; // r12
  int *v12; // r13
  unsigned int v13; // ebx
  DWORD v14; // eax
  const unsigned __int16 *v15; // rdx
  const unsigned __int16 **v16; // r8
  const unsigned __int16 **v17; // r9
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r9
  int v21; // eax
  _QWORD *v22; // rcx
  __int64 v23; // rdx
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  int v29; // eax
  int v30; // eax
  int v31; // eax
  DWORD v32; // eax
  DWORD v33; // eax
  DWORD *v34; // rcx
  DWORD pdwSizeOfConfigOut; // [rsp+38h] [rbp-51h] BYREF
  struct IXMLDOMNode *v37; // [rsp+40h] [rbp-49h] BYREF
  IXMLDOMDocument2 *ppConfigDoc; // [rsp+48h] [rbp-41h] BYREF
  EAP_ERROR *ppEapError; // [rsp+50h] [rbp-39h] BYREF
  BYTE *ppConfigOut; // [rsp+58h] [rbp-31h] BYREF
  __int64 v41; // [rsp+60h] [rbp-29h] BYREF
  __int64 v42; // [rsp+68h] [rbp-21h] BYREF
  IXMLDOMNode *pConfigDoc; // [rsp+70h] [rbp-19h] BYREF
  _QWORD v44[2]; // [rsp+78h] [rbp-11h] BYREF
  EAP_METHOD_TYPE eapMethodType; // [rsp+88h] [rbp-1h] BYREF
  int v46; // [rsp+D8h] [rbp+4Fh] BYREF
  DWORD v47; // [rsp+E8h] [rbp+5Fh]
  BYTE *v48; // [rsp+F0h] [rbp+67h]

  v48 = a4;
  v47 = a3;
  v7 = 0;
  pdwSizeOfConfigOut = 0;
  ppConfigOut = 0;
  v10 = 0;
  ppEapError = 0;
  ppConfigDoc = 0;
  v44[0] = 0;
  pConfigDoc = 0;
  v42 = 0;
  v41 = 0;
  v37 = 0;
  v46 = 0;
  if ( pEapMethodType )
  {
    if ( a5 )
    {
      v11 = a6;
      if ( a6 )
      {
        if ( !*a6 )
        {
          v12 = a7;
          if ( a7 )
          {
            v13 = 0;
            *a7 = 0;
            if ( pEapMethodType->dwAuthorId
              || pEapMethodType->eapType.dwVendorId
              || pEapMethodType->eapType.dwVendorType
              || pEapMethodType->eapType.type != 25 )
            {
              goto LABEL_124;
            }
            eapMethodType = *pEapMethodType;
            v14 = EapHostPeerConfigBlob2Xml(0x80u, &eapMethodType, a3, a4, &ppConfigDoc, &ppEapError);
            v13 = v14;
            if ( v14 )
            {
              v18 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
              {
                if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 7),
                    10,
                    WPP_14573380d6903f44e364973397d47e0a_Traceguids,
                    v14);
                  v18 = WPP_GLOBAL_Control;
                }
                if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 68) & 1) != 0 )
                {
                  v19 = 12;
LABEL_17:
                  v20 = v13;
LABEL_18:
                  WPP_SF_d(v18[7], v19, WPP_14573380d6903f44e364973397d47e0a_Traceguids, v20);
                  goto LABEL_117;
                }
              }
              goto LABEL_117;
            }
            v21 = EapSetNsAndSchema(ppConfigDoc, v15, v16, v17);
            v10 = v21;
            if ( v21 == 1 )
            {
              v13 = 1168;
LABEL_25:
              v22 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
              {
                goto LABEL_117;
              }
              v23 = 13;
              goto LABEL_28;
            }
            if ( v21 < 0 )
            {
              v13 = (unsigned __int16)v21;
              if ( (v21 & 0x1FFF0000) != 0x70000 )
                v13 = v21;
              if ( v13 )
                goto LABEL_25;
            }
            v24 = ((__int64 (__fastcall *)(IXMLDOMDocument2 *, GUID *, _QWORD *))ppConfigDoc->lpVtbl->QueryInterface)(
                    ppConfigDoc,
                    &IID_IXMLDOMNode,
                    v44);
            v10 = v24;
            if ( v24 < 0 )
            {
              v13 = (unsigned __int16)v24;
              if ( (v24 & 0x1FFF0000) != 0x70000 )
                v13 = v24;
              if ( v13 )
              {
                v18 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
                {
                  v19 = 14;
                  goto LABEL_17;
                }
LABEL_117:
                if ( ppEapError )
                  EapHostPeerFreeErrorMemory(ppEapError);
                if ( !v13 )
                  goto LABEL_121;
                goto LABEL_120;
              }
            }
            v25 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 *))(*(_QWORD *)v44[0] + 296LL))(
                    v44[0],
                    L"//baseeapconnectionpropertiesv1:Eap[baseeapconnectionpropertiesv1:Type=26][1]",
                    &v42);
            v10 = v25;
            if ( v25 == 1 )
            {
              v13 = 1168;
LABEL_42:
              v22 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
              {
                goto LABEL_117;
              }
              v23 = 15;
              goto LABEL_28;
            }
            if ( v25 < 0 )
            {
              v13 = (unsigned __int16)v25;
              if ( (v25 & 0x1FFF0000) != 0x70000 )
                v13 = v25;
              if ( v13 )
                goto LABEL_42;
            }
            v26 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v42 + 296LL))(
                    v42,
                    L"mschapv2connectionpropertiesv1:EapType[1]",
                    &v41);
            v10 = v26;
            if ( v26 == 1 )
            {
              v13 = 1168;
LABEL_51:
              v22 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
              {
                goto LABEL_117;
              }
              v23 = 16;
              goto LABEL_28;
            }
            if ( v26 < 0 )
            {
              v13 = (unsigned __int16)v26;
              if ( (v26 & 0x1FFF0000) != 0x70000 )
                v13 = v26;
              if ( v13 )
                goto LABEL_51;
            }
            v27 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, struct IXMLDOMNode **))(*(_QWORD *)v41 + 296LL))(
                    v41,
                    L"mschapv2connectionpropertiesv1:UseWinLogonCredentials[1]",
                    &v37);
            v10 = v27;
            if ( v27 == 1 )
            {
              v13 = 1168;
LABEL_60:
              v22 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
              {
                goto LABEL_117;
              }
              v23 = 17;
              goto LABEL_28;
            }
            if ( v27 < 0 )
            {
              v13 = (unsigned __int16)v27;
              if ( (v27 & 0x1FFF0000) != 0x70000 )
                v13 = v27;
              if ( v13 )
                goto LABEL_60;
            }
            v28 = ReadBOOLEANFromXMLNode(v37, &v46);
            v10 = v28;
            if ( v28 == 1 )
            {
              v13 = 1168;
LABEL_69:
              v22 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
              {
                goto LABEL_117;
              }
              v23 = 18;
              goto LABEL_28;
            }
            if ( v28 < 0 )
            {
              v13 = (unsigned __int16)v28;
              if ( (v28 & 0x1FFF0000) != 0x70000 )
                v13 = v28;
              if ( v13 )
                goto LABEL_69;
            }
            if ( a2 )
            {
              if ( v46 )
                goto LABEL_94;
              v29 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, const WCHAR *))v37->lpVtbl->put_text)(v37, L"true");
              v10 = v29;
              if ( v29 == 1 )
              {
                v13 = 1168;
LABEL_80:
                v22 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
                {
                  goto LABEL_117;
                }
                v23 = 19;
                goto LABEL_28;
              }
              if ( v29 < 0 )
              {
                v13 = (unsigned __int16)v29;
                if ( (v29 & 0x1FFF0000) != 0x70000 )
                  v13 = v29;
                if ( v13 )
                  goto LABEL_80;
              }
              goto LABEL_93;
            }
            if ( !v46 )
              goto LABEL_94;
            v30 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, const WCHAR *))v37->lpVtbl->put_text)(v37, L"false");
            v10 = v30;
            if ( v30 == 1 )
            {
              v13 = 1168;
            }
            else
            {
              if ( v30 >= 0 )
                goto LABEL_93;
              v13 = (unsigned __int16)v30;
              if ( (v30 & 0x1FFF0000) != 0x70000 )
                v13 = v30;
              if ( !v13 )
              {
LABEL_93:
                v7 = 1;
LABEL_94:
                if ( !v47 && !v48 )
                  v7 = 1;
                v31 = ((__int64 (__fastcall *)(IXMLDOMDocument2 *, IXMLDOMNode **))ppConfigDoc->lpVtbl->get_documentElement)(
                        ppConfigDoc,
                        &pConfigDoc);
                v10 = v31;
                if ( v31 == 1 )
                {
                  v13 = 1168;
                }
                else
                {
                  if ( v31 >= 0 )
                    goto LABEL_106;
                  v13 = (unsigned __int16)v31;
                  if ( (v31 & 0x1FFF0000) != 0x70000 )
                    v13 = v31;
                  if ( !v13 )
                  {
LABEL_106:
                    if ( ppEapError )
                      EapHostPeerFreeErrorMemory(ppEapError);
                    v32 = EapHostPeerConfigXml2Blob(
                            0,
                            pConfigDoc,
                            &pdwSizeOfConfigOut,
                            &ppConfigOut,
                            pEapMethodType,
                            &ppEapError);
                    v13 = v32;
                    if ( v32 )
                    {
                      v18 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
                      {
                        v19 = 22;
                        v20 = v32;
                        goto LABEL_18;
                      }
                    }
                    else
                    {
                      v33 = pdwSizeOfConfigOut;
                      v34 = a5;
                      *v12 = v7;
                      *v34 = v33;
                      *v11 = ppConfigOut;
                    }
                    goto LABEL_117;
                  }
                }
                v22 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
                {
                  goto LABEL_117;
                }
                v23 = 21;
LABEL_28:
                WPP_SF_d(v22[7], v23, WPP_14573380d6903f44e364973397d47e0a_Traceguids, v13);
                goto LABEL_117;
              }
            }
            v22 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
              goto LABEL_117;
            v23 = 20;
            goto LABEL_28;
          }
        }
      }
    }
  }
  v13 = 87;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, WPP_14573380d6903f44e364973397d47e0a_Traceguids);
    goto LABEL_117;
  }
LABEL_120:
  EapHostPeerFreeMemory(ppConfigOut);
LABEL_121:
  if ( v13 == 1168 && v10 == 1 )
    v13 = 0;
LABEL_124:
  ATL::CComPtrBase<IXMLDOMSchemaCollection2>::~CComPtrBase<IXMLDOMSchemaCollection2>(&v37);
  ATL::CComPtrBase<IXMLDOMSchemaCollection2>::~CComPtrBase<IXMLDOMSchemaCollection2>(&v41);
  ATL::CComPtrBase<IXMLDOMSchemaCollection2>::~CComPtrBase<IXMLDOMSchemaCollection2>(&v42);
  ATL::CComPtrBase<IXMLDOMSchemaCollection2>::~CComPtrBase<IXMLDOMSchemaCollection2>(&pConfigDoc);
  ATL::CComPtrBase<IXMLDOMSchemaCollection2>::~CComPtrBase<IXMLDOMSchemaCollection2>(v44);
  ATL::CComPtrBase<IXMLDOMSchemaCollection2>::~CComPtrBase<IXMLDOMSchemaCollection2>(&ppConfigDoc);
  return v13;
}

```

## disassembly

```asm
0x18002e118  mov     rax, rsp
0x18002e11b  mov     [rax+10h], rbx
0x18002e11f  mov     [rax+20h], r9
0x18002e123  mov     [rax+18h], r8d
0x18002e127  push    rbp
0x18002e128  push    rsi
0x18002e129  push    rdi
0x18002e12a  push    r12
0x18002e12c  push    r13
0x18002e12e  push    r14
0x18002e130  push    r15
0x18002e132  lea     rbp, [rax-47h]
0x18002e136  sub     rsp, 90h
0x18002e13d  xor     esi, esi
0x18002e13f  mov     r15d, edx
0x18002e142  mov     [rbp+3Fh+pdwSizeOfConfigOut], esi
0x18002e145  mov     r14, rcx
0x18002e148  mov     [rbp+3Fh+ppConfigOut], rsi
0x18002e14c  mov     edi, esi
0x18002e14e  mov     [rbp+3Fh+ppEapError], rsi
0x18002e152  mov     [rbp+3Fh+var_80], rsi
0x18002e156  lea     r12d, [rsi+1]
0x18002e15a  mov     [rbp+3Fh+var_50], rsi
0x18002e15e  mov     [rbp+3Fh+pConfigDoc], rsi
0x18002e162  mov     [rbp+3Fh+var_60], rsi
0x18002e166  mov     [rbp+3Fh+var_68], rsi
0x18002e16a  mov     [rbp+3Fh+var_88], rsi
0x18002e16e  mov     [rbp+3Fh+arg_0], esi
0x18002e171  test    rcx, rcx
0x18002e174  jz      loc_18002E704
0x18002e17a  cmp     [rbp+3Fh+arg_20], rsi
0x18002e17e  jz      loc_18002E704
0x18002e184  mov     r12, [rbp+3Fh+arg_28]
0x18002e188  test    r12, r12
0x18002e18b  jz      loc_18002E6FE
0x18002e191  cmp     [r12], rsi
0x18002e195  jnz     loc_18002E6FE
0x18002e19b  mov     r13, [rbp+3Fh+arg_30]
0x18002e19f  test    r13, r13
0x18002e1a2  jz      loc_18002E6FE
0x18002e1a8  mov     ebx, esi
0x18002e1aa  mov     [r13+0], esi
0x18002e1ae  cmp     [rcx+0Ch], esi
0x18002e1b1  jnz     loc_18002E762
0x18002e1b7  cmp     [rcx+4], esi
0x18002e1ba  jnz     loc_18002E762
0x18002e1c0  cmp     [rcx+8], esi
0x18002e1c3  jnz     loc_18002E762
0x18002e1c9  cmp     byte ptr [rcx], 19h
0x18002e1cc  jnz     loc_18002E762
0x18002e1d2  movups  xmm0, xmmword ptr [rcx]
0x18002e1d5  lea     rcx, [rbp+3Fh+ppEapError]
0x18002e1d9  mov     [rsp+28h], rcx; ppEapError
0x18002e1de  lea     rdx, [rbp+3Fh+eapMethodType]; eapMethodType
0x18002e1e2  lea     rcx, [rbp+3Fh+var_80]
0x18002e1e6  mov     [rsp+0C0h+ppConfigDoc], rcx; ppConfigDoc
0x18002e1eb  mov     ecx, 80h; dwFlags
0x18002e1f0  movdqu  xmmword ptr [rbp+3Fh+eapMethodType.eapType.type], xmm0
0x18002e1f5  call    cs:__imp_EapHostPeerConfigBlob2Xml
0x18002e1fb  mov     ebx, eax
0x18002e1fd  test    eax, eax
0x18002e1ff  jz      short loc_18002E273
0x18002e201  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e208  lea     rsi, WPP_GLOBAL_Control
0x18002e20f  mov     r12d, 1
0x18002e215  cmp     rcx, rsi
0x18002e218  jz      loc_18002E735
0x18002e21e  test    [rcx+44h], r12b
0x18002e222  jz      short loc_18002E243
0x18002e224  mov     rcx, [rcx+38h]
0x18002e228  lea     edx, [r12+9]
0x18002e22d  mov     r9d, eax
0x18002e230  lea     r8, WPP_14573380d6903f44e364973397d47e0a_Traceguids
0x18002e237  call    WPP_SF_d
0x18002e23c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e243  cmp     rcx, rsi
0x18002e246  jz      loc_18002E735
0x18002e24c  test    [rcx+44h], r12b
0x18002e250  jz      loc_18002E735
0x18002e256  mov     edx, 0Ch
0x18002e25b  mov     r9d, ebx
0x18002e25e  mov     rcx, [rcx+38h]
0x18002e262  lea     r8, WPP_14573380d6903f44e364973397d47e0a_Traceguids
0x18002e269  call    WPP_SF_d
0x18002e26e  jmp     loc_18002E735
0x18002e273  mov     rcx, [rbp+3Fh+var_80]; struct IXMLDOMDocument2 *
0x18002e277  call    ?EapSetNsAndSchema@@YAJPEAUIXMLDOMDocument2@@PEBGPEAPEBG2@Z; EapSetNsAndSchema(IXMLDOMDocument2 *,ushort const *,ushort const * *,ushort const * *)
0x18002e27c  mov     edx, 1
0x18002e281  mov     edi, eax
0x18002e283  cmp     eax, edx
0x18002e285  jnz     short loc_18002E28E
0x18002e287  mov     ebx, 490h
0x18002e28c  jmp     short loc_18002E2A7
0x18002e28e  test    edi, edi
0x18002e290  jns     short loc_18002E2EA
0x18002e292  and     eax, 1FFF0000h
0x18002e297  movzx   ebx, di
0x18002e29a  cmp     eax, 70000h
0x18002e29f  jz      short loc_18002E2A3
0x18002e2a1  mov     ebx, edi
0x18002e2a3  test    ebx, ebx
0x18002e2a5  jz      short loc_18002E2EA
0x18002e2a7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e2ae  lea     rsi, WPP_GLOBAL_Control
0x18002e2b5  cmp     rcx, rsi
0x18002e2b8  jz      loc_18002E6DF
0x18002e2be  test    [rcx+44h], dl
0x18002e2c1  jz      loc_18002E6DF
0x18002e2c7  mov     edx, 0Dh
0x18002e2cc  mov     rcx, [rcx+38h]
0x18002e2d0  lea     r8, WPP_14573380d6903f44e364973397d47e0a_Traceguids
0x18002e2d7  mov     r9d, ebx
0x18002e2da  call    WPP_SF_d
0x18002e2df  mov     r12d, 1
0x18002e2e5  jmp     loc_18002E735
0x18002e2ea  mov     rcx, [rbp+3Fh+var_80]
0x18002e2ee  lea     r8, [rbp+3Fh+var_50]
0x18002e2f2  lea     rdx, IID_IXMLDOMNode
0x18002e2f9  mov     rax, [rcx]
0x18002e2fc  mov     rax, [rax]
0x18002e2ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e304  mov     edi, eax
0x18002e306  test    eax, eax
0x18002e308  jns     short loc_18002E350
0x18002e30a  and     eax, 1FFF0000h
0x18002e30f  movzx   ebx, di
0x18002e312  cmp     eax, 70000h
0x18002e317  jz      short loc_18002E31B
0x18002e319  mov     ebx, edi
0x18002e31b  test    ebx, ebx
0x18002e31d  jz      short loc_18002E350
0x18002e31f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e326  lea     rsi, WPP_GLOBAL_Control
0x18002e32d  mov     r12d, 1
0x18002e333  cmp     rcx, rsi
0x18002e336  jz      loc_18002E735
0x18002e33c  test    [rcx+44h], r12b
0x18002e340  jz      loc_18002E735
0x18002e346  lea     edx, [r12+0Dh]
0x18002e34b  jmp     loc_18002E25B
0x18002e350  mov     rcx, [rbp+3Fh+var_50]
0x18002e354  lea     r8, [rbp+3Fh+var_60]
0x18002e358  lea     rdx, aBaseeapconnect_0; "//baseeapconnectionpropertiesv1:Eap[bas"...
0x18002e35f  mov     rax, [rcx]
0x18002e362  mov     rax, [rax+128h]
0x18002e369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e36e  mov     edx, 1
0x18002e373  mov     edi, eax
0x18002e375  cmp     eax, edx
0x18002e377  jnz     short loc_18002E380
0x18002e379  mov     ebx, 490h
0x18002e37e  jmp     short loc_18002E399
0x18002e380  test    edi, edi
0x18002e382  jns     short loc_18002E3C3
0x18002e384  and     eax, 1FFF0000h
0x18002e389  movzx   ebx, di
0x18002e38c  cmp     eax, 70000h
0x18002e391  jz      short loc_18002E395
0x18002e393  mov     ebx, edi
0x18002e395  test    ebx, ebx
0x18002e397  jz      short loc_18002E3C3
0x18002e399  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e3a0  lea     rsi, WPP_GLOBAL_Control
0x18002e3a7  cmp     rcx, rsi
0x18002e3aa  jz      loc_18002E6DF
0x18002e3b0  test    [rcx+44h], dl
0x18002e3b3  jz      loc_18002E6DF
0x18002e3b9  mov     edx, 0Fh
0x18002e3be  jmp     loc_18002E2CC
0x18002e3c3  mov     rcx, [rbp+3Fh+var_60]
0x18002e3c7  lea     r8, [rbp+3Fh+var_68]
0x18002e3cb  lea     rdx, aMschapv2connec; "mschapv2connectionpropertiesv1:EapType["...
0x18002e3d2  mov     rax, [rcx]
0x18002e3d5  mov     rax, [rax+128h]
0x18002e3dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e3e1  mov     edx, 1
0x18002e3e6  mov     edi, eax
0x18002e3e8  cmp     eax, edx
0x18002e3ea  jnz     short loc_18002E3F3
0x18002e3ec  mov     ebx, 490h
0x18002e3f1  jmp     short loc_18002E40C
0x18002e3f3  test    edi, edi
0x18002e3f5  jns     short loc_18002E436
0x18002e3f7  and     eax, 1FFF0000h
0x18002e3fc  movzx   ebx, di
0x18002e3ff  cmp     eax, 70000h
0x18002e404  jz      short loc_18002E408
0x18002e406  mov     ebx, edi
0x18002e408  test    ebx, ebx
0x18002e40a  jz      short loc_18002E436
0x18002e40c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e413  lea     rsi, WPP_GLOBAL_Control
0x18002e41a  cmp     rcx, rsi
0x18002e41d  jz      loc_18002E6DF
0x18002e423  test    [rcx+44h], dl
0x18002e426  jz      loc_18002E6DF
0x18002e42c  mov     edx, 10h
0x18002e431  jmp     loc_18002E2CC
0x18002e436  mov     rcx, [rbp+3Fh+var_68]
0x18002e43a  lea     r8, [rbp+3Fh+var_88]
0x18002e43e  lea     rdx, aMschapv2connec_1; "mschapv2connectionpropertiesv1:UseWinLo"...
0x18002e445  mov     rax, [rcx]
0x18002e448  mov     rax, [rax+128h]
0x18002e44f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e454  mov     edx, 1
0x18002e459  mov     edi, eax
0x18002e45b  cmp     eax, edx
0x18002e45d  jnz     short loc_18002E466
0x18002e45f  mov     ebx, 490h
0x18002e464  jmp     short loc_18002E47F
0x18002e466  test    edi, edi
0x18002e468  jns     short loc_18002E4A9
0x18002e46a  and     eax, 1FFF0000h
0x18002e46f  movzx   ebx, di
0x18002e472  cmp     eax, 70000h
0x18002e477  jz      short loc_18002E47B
0x18002e479  mov     ebx, edi
0x18002e47b  test    ebx, ebx
0x18002e47d  jz      short loc_18002E4A9
0x18002e47f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e486  lea     rsi, WPP_GLOBAL_Control
0x18002e48d  cmp     rcx, rsi
0x18002e490  jz      loc_18002E6DF
0x18002e496  test    [rcx+44h], dl
0x18002e499  jz      loc_18002E6DF
0x18002e49f  mov     edx, 11h
0x18002e4a4  jmp     loc_18002E2CC
0x18002e4a9  mov     rcx, [rbp+3Fh+var_88]; struct IXMLDOMNode *
0x18002e4ad  lea     rdx, [rbp+3Fh+arg_0]; int *
0x18002e4b1  call    ?ReadBOOLEANFromXMLNode@@YAJPEAUIXMLDOMNode@@PEAH@Z; ReadBOOLEANFromXMLNode(IXMLDOMNode *,int *)
0x18002e4b6  mov     edx, 1
0x18002e4bb  mov     edi, eax
0x18002e4bd  cmp     eax, edx
0x18002e4bf  jnz     short loc_18002E4C8
0x18002e4c1  mov     ebx, 490h
0x18002e4c6  jmp     short loc_18002E4E1
0x18002e4c8  test    edi, edi
0x18002e4ca  jns     short loc_18002E50B
0x18002e4cc  and     eax, 1FFF0000h
0x18002e4d1  movzx   ebx, di
0x18002e4d4  cmp     eax, 70000h
0x18002e4d9  jz      short loc_18002E4DD
0x18002e4db  mov     ebx, edi
0x18002e4dd  test    ebx, ebx
0x18002e4df  jz      short loc_18002E50B
0x18002e4e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e4e8  lea     rsi, WPP_GLOBAL_Control
0x18002e4ef  cmp     rcx, rsi
0x18002e4f2  jz      loc_18002E6DF
0x18002e4f8  test    [rcx+44h], dl
0x18002e4fb  jz      loc_18002E6DF
0x18002e501  mov     edx, 12h
0x18002e506  jmp     loc_18002E2CC
0x18002e50b  test    r15d, r15d
0x18002e50e  jz      loc_18002E594
0x18002e514  cmp     [rbp+3Fh+arg_0], esi
0x18002e517  jnz     loc_18002E60A
0x18002e51d  mov     rcx, [rbp+3Fh+var_88]
0x18002e521  lea     rdx, aTrue; "true"
0x18002e528  mov     rax, [rcx]
0x18002e52b  mov     rax, [rax+0D8h]
0x18002e532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e537  mov     edx, 1
0x18002e53c  mov     edi, eax
0x18002e53e  cmp     eax, edx
0x18002e540  jnz     short loc_18002E549
0x18002e542  mov     ebx, 490h
0x18002e547  jmp     short loc_18002E56A
0x18002e549  test    edi, edi
0x18002e54b  jns     loc_18002E608
0x18002e551  and     eax, 1FFF0000h
0x18002e556  movzx   ebx, di
0x18002e559  cmp     eax, 70000h
0x18002e55e  jz      short loc_18002E562
0x18002e560  mov     ebx, edi
0x18002e562  test    ebx, ebx
0x18002e564  jz      loc_18002E608
0x18002e56a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e571  lea     rsi, WPP_GLOBAL_Control
0x18002e578  cmp     rcx, rsi
0x18002e57b  jz      loc_18002E6DF
0x18002e581  test    [rcx+44h], dl
0x18002e584  jz      loc_18002E6DF
0x18002e58a  mov     edx, 13h
0x18002e58f  jmp     loc_18002E2CC
0x18002e594  cmp     [rbp+3Fh+arg_0], esi
0x18002e597  jz      short loc_18002E60A
0x18002e599  mov     rcx, [rbp+3Fh+var_88]
0x18002e59d  lea     rdx, aFalse; "false"
0x18002e5a4  mov     rax, [rcx]
0x18002e5a7  mov     rax, [rax+0D8h]
0x18002e5ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e5b3  mov     edx, 1
0x18002e5b8  mov     edi, eax
0x18002e5ba  cmp     eax, edx
0x18002e5bc  jnz     short loc_18002E5C5
0x18002e5be  mov     ebx, 490h
0x18002e5c3  jmp     short loc_18002E5DE
0x18002e5c5  test    edi, edi
0x18002e5c7  jns     short loc_18002E608
  ... truncated ...
```
