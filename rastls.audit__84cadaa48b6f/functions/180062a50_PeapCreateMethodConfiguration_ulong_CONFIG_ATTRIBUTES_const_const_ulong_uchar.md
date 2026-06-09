# PeapCreateMethodConfiguration(ulong,_CONFIG_ATTRIBUTES const * const,ulong *,uchar * *)

- ea: `0x180062a50`
- end: `0x180062e52`
- name: `?PeapCreateMethodConfiguration@@YAKKQEBU_CONFIG_ATTRIBUTES@@PEAKPEAPEAE@Z`
- size: `1026`
- prototype: `unsigned int __fastcall(unsigned int, const struct _CONFIG_ATTRIBUTES *const, unsigned int *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800645a0`

## callees

- `0x180005010`
- `0x180006620`
- `0x180007d00`
- `0x180020d80`
- `0x180021e74`
- `0x18002d070`
- `0x180038e4c`
- `0x180062a50`
- `0x1800633e0`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180062ce3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180062ce3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180062e0a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180062e1e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180062e0a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180062e1e`

## string_xrefs

- `0x180062bd2`: `xmlns:EapHostConfig='http://www.microsoft.com/provisioning/EapHostConfig' xmlns:baseeapconnectionpropertiesv1='http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1' `

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall PeapCreateMethodConfiguration(
        unsigned int a1,
        const struct _CONFIG_ATTRIBUTES *a2,
        unsigned int *a3,
        struct _PEAP_CONN_PROPERTIES **a4)
{
  const struct _CONFIG_ATTRIBUTES *v4; // r15
  unsigned int v5; // r12d
  struct IXMLDOMDocument2 *v6; // rbx
  unsigned __int8 *v7; // r14
  unsigned int v8; // r13d
  unsigned int ConnectionData; // esi
  struct _PEAP_CONN_PROPERTIES *v10; // rdi
  char v11; // al
  __int64 v12; // rdx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  struct IXMLDOMDocument2 *v17; // r15
  struct _EAPTLS_CONTROL_BLOCK *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r9
  unsigned int v21; // eax
  __int64 v22; // r9
  struct _EAPTLS_CONTROL_BLOCK *v23; // rcx
  __int64 v24; // rdx
  unsigned int v25; // eax
  unsigned int v26; // r15d
  struct _PEAP_CONN_PROPERTIES *v27; // rax
  struct _PEAP_CONN_PROPERTIES *v28; // rbx
  struct _PEAP_ENTRY_CONN_PROPERTIES *v29; // rcx
  unsigned int v30; // r15d
  char v32; // [rsp+30h] [rbp-48h]
  char v33; // [rsp+31h] [rbp-47h]
  char v34; // [rsp+32h] [rbp-46h]
  unsigned int v35; // [rsp+34h] [rbp-44h] BYREF
  unsigned int v36; // [rsp+38h] [rbp-40h] BYREF
  unsigned __int8 *v37; // [rsp+40h] [rbp-38h] BYREF
  void *Src; // [rsp+48h] [rbp-30h] BYREF
  struct IXMLDOMNode *v39; // [rsp+50h] [rbp-28h] BYREF
  struct _PEAP_ENTRY_CONN_PROPERTIES *v40; // [rsp+58h] [rbp-20h] BYREF
  struct IXMLDOMDocument2 *v41; // [rsp+60h] [rbp-18h] BYREF
  unsigned __int16 *v42; // [rsp+68h] [rbp-10h] BYREF

  v4 = a2;
  v5 = 0;
  Src = 0;
  v6 = 0;
  v41 = 0;
  v39 = 0;
  v40 = 0;
  v7 = 0;
  v37 = 0;
  v8 = 0;
  v35 = 0;
  v36 = 0;
  *a4 = 0;
  *a3 = 0;
  ConnectionData = PeapReadConnectionData(a1, 0, 0, (struct _PEAP_CONN_PROPERTIES **)&Src);
  v10 = (struct _PEAP_CONN_PROPERTIES *)Src;
  if ( !ConnectionData )
  {
    v11 = 0;
    v32 = 0;
    v33 = 0;
    v34 = 0;
    while ( v5 < *(_DWORD *)v4 )
    {
      v12 = *((_QWORD *)a2 + 1);
      v13 = *(_DWORD *)(v12 + 16LL * v5);
      if ( (unsigned int)(v13 - 1) > 9 )
      {
        ConnectionData = 13;
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          goto LABEL_59;
        v19 = 141;
        v20 = v5;
LABEL_58:
        WPP_SF_d(*((_QWORD *)v18 + 2), v19, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, v20);
        goto LABEL_59;
      }
      v14 = v13 - 2;
      if ( v14 )
      {
        v15 = v14 - 1;
        if ( v15 )
        {
          v16 = v15 - 1;
          if ( v16 )
          {
            if ( v16 == 1 )
            {
              v17 = *(struct IXMLDOMDocument2 **)(v12 + 16LL * v5 + 8);
              if ( v6 != v17 )
              {
                if ( v17 )
                  ((void (__fastcall *)(struct IXMLDOMDocument2 *))v17->lpVtbl->AddRef)(v17);
                if ( v6 )
                  ((void (__fastcall *)(struct IXMLDOMDocument2 *))v6->lpVtbl->Release)(v6);
                v6 = v17;
                v41 = v17;
              }
            }
          }
          else
          {
            v34 = 1;
          }
        }
        else
        {
          v33 = 1;
        }
        v11 = v32;
      }
      else
      {
        v11 = 1;
        v32 = 1;
      }
      ++v5;
      v4 = a2;
    }
    if ( v33 )
      *((_DWORD *)v10 + 3) |= 8u;
    else
      *((_DWORD *)v10 + 3) &= ~8u;
    if ( v34 )
      *((_DWORD *)v10 + 3) |= 1u;
    else
      *((_DWORD *)v10 + 3) &= ~1u;
    if ( v11 )
      *((_DWORD *)v10 + 6) &= 0xFFFFFFF9;
    else
      *((_DWORD *)v10 + 6) |= 6u;
    if ( v6 )
    {
      v42 = 0;
      Src = 0;
      v21 = SetNsAndSchema(
              v6,
              L"xmlns:EapHostConfig='http://www.microsoft.com/provisioning/EapHostConfig' xmlns:baseeapconnectionpropertie"
               "sv1='http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1' ",
              (const unsigned __int16 **)&v42,
              (const unsigned __int16 **)&Src);
      v22 = v21;
      if ( v21 )
      {
        ConnectionData = (unsigned __int16)v21;
        if ( (v21 & 0x1FFF0000) != 0x70000 )
          ConnectionData = v21;
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          goto LABEL_59;
        v24 = 143;
LABEL_37:
        WPP_SF_d(*((_QWORD *)v23 + 2), v24, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, v22);
        goto LABEL_59;
      }
      v25 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, GUID *, struct IXMLDOMNode **, _QWORD))v6->lpVtbl->QueryInterface)(
              v6,
              &IID_IXMLDOMNode,
              &v39,
              0);
      v22 = v25;
      if ( v25 )
      {
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          goto LABEL_59;
        v24 = 144;
        goto LABEL_37;
      }
      ConnectionData = getInnerConnectionPropertiesFromDOMNode(v39, a1, &v36, v10, &v37, &v35);
      if ( ConnectionData )
      {
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            145,
            WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids,
            ConnectionData);
        v7 = v37;
        goto LABEL_59;
      }
      v7 = v37;
      v8 = v35;
    }
    v26 = v8 + *((_DWORD *)v10 + 1);
    v27 = (struct _PEAP_CONN_PROPERTIES *)LocalAlloc(0x40u, v26);
    v28 = v27;
    if ( v27 )
    {
      memcpy_0(v27, v10, *((unsigned int *)v10 + 1));
      *((_DWORD *)v28 + 1) = v26;
      if ( v7 && v8 )
      {
        PeapGetFirstEntryConnProp(v28, &v40);
        v29 = v40;
        *(_DWORD *)v40 = 1;
        v30 = v36;
        *((_DWORD *)v29 + 2) = v36;
        *((_DWORD *)v29 + 1) = v8 + 15;
        memcpy_0((char *)v29 + 12, v7, v8);
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 147, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, v30);
      }
      else if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 148, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
      }
      *a3 = *((_DWORD *)v28 + 1);
      *a4 = v28;
    }
    else
    {
      v20 = 8;
      ConnectionData = 8;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        v19 = 146;
        goto LABEL_58;
      }
    }
    goto LABEL_59;
  }
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    v19 = 142;
    v20 = ConnectionData;
    goto LABEL_58;
  }
LABEL_59:
  if ( v10 )
    LocalFree(v10);
  if ( v7 )
    LocalFree(v7);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v39);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v41);
  return ConnectionData;
}

```

## disassembly

```asm
0x180062a50  mov     rax, rsp
0x180062a53  mov     [rax+20h], r9
0x180062a57  mov     [rax+18h], r8
0x180062a5b  mov     [rax+10h], rdx
0x180062a5f  mov     [rax+8], ecx
0x180062a62  push    rbp
0x180062a63  push    rbx
0x180062a64  push    rsi
0x180062a65  push    rdi
0x180062a66  push    r12
0x180062a68  push    r13
0x180062a6a  push    r14
0x180062a6c  push    r15
0x180062a6e  mov     rbp, rsp
0x180062a71  sub     rsp, 78h
0x180062a75  mov     r15, rdx
0x180062a78  xor     r12d, r12d
0x180062a7b  mov     [rbp+Src], r12
0x180062a7f  mov     ebx, r12d
0x180062a82  mov     [rbp+var_18], rbx
0x180062a86  mov     [rbp+var_28], r12
0x180062a8a  mov     [rbp+var_20], r12
0x180062a8e  mov     r14d, r12d
0x180062a91  mov     [rbp+var_38], r12
0x180062a95  mov     r13d, r12d
0x180062a98  mov     [rbp+var_44], r12d
0x180062a9c  mov     [rbp+var_40], r12d
0x180062aa0  mov     [r9], r12
0x180062aa3  mov     [r8], r12d
0x180062aa6  lea     r9, [rbp+Src]; struct _PEAP_CONN_PROPERTIES **
0x180062aaa  xor     r8d, r8d; unsigned int
0x180062aad  xor     edx, edx; unsigned __int8 *
0x180062aaf  call    ?PeapReadConnectionData@@YAKKPEAEKPEAPEAU_PEAP_CONN_PROPERTIES@@@Z; PeapReadConnectionData(ulong,uchar *,ulong,_PEAP_CONN_PROPERTIES * *)
0x180062ab4  mov     esi, eax
0x180062ab6  mov     rdi, [rbp+Src]
0x180062aba  test    eax, eax
0x180062abc  jnz     loc_180062DD7
0x180062ac2  mov     al, r12b
0x180062ac5  mov     [rbp+var_48], al
0x180062ac8  mov     [rbp+var_47], r12b
0x180062acc  mov     [rbp+var_46], r12b
0x180062ad0  cmp     r12d, [r15]
0x180062ad3  jnb     loc_180062B88
0x180062ad9  mov     r15d, r12d
0x180062adc  add     r15, r15
0x180062adf  mov     rdx, [rbp+arg_8]
0x180062ae3  mov     rdx, [rdx+8]
0x180062ae7  mov     ecx, [rdx+r15*8]
0x180062aeb  lea     eax, [rcx-1]
0x180062aee  cmp     eax, 9
0x180062af1  ja      short loc_180062B5F
0x180062af3  sub     ecx, 2
0x180062af6  jz      short loc_180062B58
0x180062af8  sub     ecx, 1
0x180062afb  jz      short loc_180062B52
0x180062afd  sub     ecx, 1
0x180062b00  jz      short loc_180062B4C
0x180062b02  cmp     ecx, 1
0x180062b05  jnz     short loc_180062B40
0x180062b07  mov     r15, [rdx+r15*8+8]
0x180062b0c  cmp     rbx, r15
0x180062b0f  jz      short loc_180062B40
0x180062b11  test    r15, r15
0x180062b14  jz      short loc_180062B25
0x180062b16  mov     rax, [r15]
0x180062b19  mov     rcx, r15
0x180062b1c  mov     rax, [rax+8]
0x180062b20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062b25  test    rbx, rbx
0x180062b28  jz      short loc_180062B39
0x180062b2a  mov     rax, [rbx]
0x180062b2d  mov     rcx, rbx
0x180062b30  mov     rax, [rax+10h]
0x180062b34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062b39  mov     rbx, r15
0x180062b3c  mov     [rbp+var_18], rbx
0x180062b40  mov     al, [rbp+var_48]
0x180062b43  inc     r12d
0x180062b46  mov     r15, [rbp+arg_8]
0x180062b4a  jmp     short loc_180062AD0
0x180062b4c  mov     [rbp+var_46], 1
0x180062b50  jmp     short loc_180062B40
0x180062b52  mov     [rbp+var_47], 1
0x180062b56  jmp     short loc_180062B40
0x180062b58  mov     al, 1
0x180062b5a  mov     [rbp+var_48], al
0x180062b5d  jmp     short loc_180062B43
0x180062b5f  mov     esi, 0Dh
0x180062b64  lea     rax, WPP_GLOBAL_Control
0x180062b6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180062b72  cmp     rcx, rax
0x180062b75  jz      loc_180062E02
0x180062b7b  mov     edx, 8Dh
0x180062b80  mov     r9d, r12d
0x180062b83  jmp     loc_180062DF2
0x180062b88  xor     r12d, r12d
0x180062b8b  cmp     [rbp+var_47], r12b
0x180062b8f  jz      short loc_180062B97
0x180062b91  or      dword ptr [rdi+0Ch], 8
0x180062b95  jmp     short loc_180062B9B
0x180062b97  and     dword ptr [rdi+0Ch], 0FFFFFFF7h
0x180062b9b  cmp     [rbp+var_46], r12b
0x180062b9f  jz      short loc_180062BA7
0x180062ba1  or      dword ptr [rdi+0Ch], 1
0x180062ba5  jmp     short loc_180062BAB
0x180062ba7  and     dword ptr [rdi+0Ch], 0FFFFFFFEh
0x180062bab  test    al, al
0x180062bad  jnz     short loc_180062BB5
0x180062baf  or      dword ptr [rdi+18h], 6
0x180062bb3  jmp     short loc_180062BB9
0x180062bb5  and     dword ptr [rdi+18h], 0FFFFFFF9h
0x180062bb9  test    rbx, rbx
0x180062bbc  jz      loc_180062CD4
0x180062bc2  mov     [rbp+var_10], r12
0x180062bc6  mov     [rbp+Src], r12
0x180062bca  lea     r9, [rbp+Src]; unsigned __int16 **
0x180062bce  lea     r8, [rbp+var_10]; unsigned __int16 **
0x180062bd2  lea     rdx, aXmlnsEaphostco; "xmlns:EapHostConfig='http://www.microso"...
0x180062bd9  mov     rcx, rbx; struct IXMLDOMDocument2 *
0x180062bdc  call    ?SetNsAndSchema@@YAJPEAUIXMLDOMDocument2@@PEBGPEAPEBG2KK@Z; SetNsAndSchema(IXMLDOMDocument2 *,ushort const *,ushort const * *,ushort const * *,ulong,ulong)
0x180062be1  mov     r9d, eax
0x180062be4  test    eax, eax
0x180062be6  jz      short loc_180062C2F
0x180062be8  mov     ecx, eax
0x180062bea  and     ecx, 1FFF0000h
0x180062bf0  cmp     ecx, 70000h
0x180062bf6  movzx   esi, r9w
0x180062bfa  jz      short loc_180062BFE
0x180062bfc  mov     esi, eax
0x180062bfe  lea     rax, WPP_GLOBAL_Control
0x180062c05  mov     rcx, cs:WPP_GLOBAL_Control
0x180062c0c  cmp     rcx, rax
0x180062c0f  jz      loc_180062E02
0x180062c15  mov     edx, 8Fh
0x180062c1a  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180062c21  mov     rcx, [rcx+10h]
0x180062c25  call    WPP_SF_d
0x180062c2a  jmp     loc_180062E02
0x180062c2f  mov     rax, [rbx]
0x180062c32  lea     r8, [rbp+var_28]
0x180062c36  lea     rdx, IID_IXMLDOMNode
0x180062c3d  mov     rcx, rbx
0x180062c40  mov     rax, [rax]
0x180062c43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062c48  mov     r9d, eax
0x180062c4b  test    eax, eax
0x180062c4d  jz      short loc_180062C6D
0x180062c4f  lea     rax, WPP_GLOBAL_Control
0x180062c56  mov     rcx, cs:WPP_GLOBAL_Control
0x180062c5d  cmp     rcx, rax
0x180062c60  jz      loc_180062E02
0x180062c66  mov     edx, 90h
0x180062c6b  jmp     short loc_180062C1A
0x180062c6d  lea     rax, [rbp+var_44]
0x180062c71  mov     [rsp+78h+var_50], rax; unsigned int *
0x180062c76  lea     rax, [rbp+var_38]
0x180062c7a  mov     [rsp+78h+var_58], rax; unsigned __int8 **
0x180062c7f  mov     r9, rdi; struct _PEAP_CONN_PROPERTIES *
0x180062c82  lea     r8, [rbp+var_40]; unsigned int *
0x180062c86  mov     edx, [rbp+arg_0]; unsigned int
0x180062c89  mov     rcx, [rbp+var_28]; struct IXMLDOMNode *
0x180062c8d  call    ?getInnerConnectionPropertiesFromDOMNode@@YAKPEAUIXMLDOMNode@@KPEAKPEAU_PEAP_CONN_PROPERTIES@@PEAPEAE1@Z; getInnerConnectionPropertiesFromDOMNode(IXMLDOMNode *,ulong,ulong *,_PEAP_CONN_PROPERTIES *,uchar * *,ulong *)
0x180062c92  mov     esi, eax
0x180062c94  test    eax, eax
0x180062c96  jz      short loc_180062CCC
0x180062c98  lea     rax, WPP_GLOBAL_Control
0x180062c9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180062ca6  cmp     rcx, rax
0x180062ca9  jz      short loc_180062CC3
0x180062cab  mov     edx, 91h
0x180062cb0  mov     r9d, esi
0x180062cb3  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180062cba  mov     rcx, [rcx+10h]
0x180062cbe  call    WPP_SF_d
0x180062cc3  mov     r14, [rbp+var_38]
0x180062cc7  jmp     loc_180062E02
0x180062ccc  mov     r14, [rbp+var_38]
0x180062cd0  mov     r13d, [rbp+var_44]
0x180062cd4  mov     r15d, [rdi+4]
0x180062cd8  add     r15d, r13d
0x180062cdb  mov     edx, r15d; uBytes
0x180062cde  mov     ecx, 40h ; '@'; uFlags
0x180062ce3  call    cs:__imp_LocalAlloc
0x180062cea  nop     dword ptr [rax+rax+00h]
0x180062cef  mov     rbx, rax
0x180062cf2  test    rax, rax
0x180062cf5  jnz     short loc_180062D1F
0x180062cf7  lea     r9d, [rax+8]
0x180062cfb  mov     esi, r9d
0x180062cfe  lea     rax, WPP_GLOBAL_Control
0x180062d05  mov     rcx, cs:WPP_GLOBAL_Control
0x180062d0c  cmp     rcx, rax
0x180062d0f  jz      loc_180062E02
0x180062d15  mov     edx, 92h
0x180062d1a  jmp     loc_180062DF2
0x180062d1f  mov     r8d, [rdi+4]; Size
0x180062d23  mov     rdx, rdi; Src
0x180062d26  mov     rcx, rbx; void *
0x180062d29  call    memcpy_0
0x180062d2e  mov     [rbx+4], r15d
0x180062d32  test    r14, r14
0x180062d35  jz      short loc_180062D9D
0x180062d37  test    r13d, r13d
0x180062d3a  jz      short loc_180062D9D
0x180062d3c  lea     rdx, [rbp+var_20]; struct _PEAP_ENTRY_CONN_PROPERTIES **
0x180062d40  mov     rcx, rbx; struct _PEAP_CONN_PROPERTIES *
0x180062d43  call    ?PeapGetFirstEntryConnProp@@YAKPEAU_PEAP_CONN_PROPERTIES@@PEAPEFAU_PEAP_ENTRY_CONN_PROPERTIES@@@Z; PeapGetFirstEntryConnProp(_PEAP_CONN_PROPERTIES *,_PEAP_ENTRY_CONN_PROPERTIES * *)
0x180062d48  mov     rcx, [rbp+var_20]
0x180062d4c  mov     dword ptr [rcx], 1
0x180062d52  mov     r15d, [rbp+var_40]
0x180062d56  mov     [rcx+8], r15d
0x180062d5a  lea     eax, [r13+0Fh]
0x180062d5e  mov     [rcx+4], eax
0x180062d61  mov     r8d, r13d; Size
0x180062d64  add     rcx, 0Ch; void *
0x180062d68  mov     rdx, r14; Src
0x180062d6b  call    memcpy_0
0x180062d70  lea     rax, WPP_GLOBAL_Control
0x180062d77  mov     rcx, cs:WPP_GLOBAL_Control
0x180062d7e  cmp     rcx, rax
0x180062d81  jz      short loc_180062DC5
0x180062d83  mov     edx, 93h
0x180062d88  mov     r9d, r15d
0x180062d8b  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180062d92  mov     rcx, [rcx+10h]
0x180062d96  call    WPP_SF_d
0x180062d9b  jmp     short loc_180062DC5
0x180062d9d  lea     rax, WPP_GLOBAL_Control
0x180062da4  mov     rcx, cs:WPP_GLOBAL_Control
0x180062dab  cmp     rcx, rax
0x180062dae  jz      short loc_180062DC5
0x180062db0  mov     edx, 94h
0x180062db5  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180062dbc  mov     rcx, [rcx+10h]
0x180062dc0  call    WPP_SF_
0x180062dc5  mov     eax, [rbx+4]
0x180062dc8  mov     rcx, [rbp+arg_10]
0x180062dcc  mov     [rcx], eax
0x180062dce  mov     rax, [rbp+arg_18]
0x180062dd2  mov     [rax], rbx
0x180062dd5  jmp     short loc_180062E02
0x180062dd7  lea     rax, WPP_GLOBAL_Control
0x180062dde  mov     rcx, cs:WPP_GLOBAL_Control
0x180062de5  cmp     rcx, rax
0x180062de8  jz      short loc_180062E02
0x180062dea  mov     edx, 8Eh
0x180062def  mov     r9d, esi
0x180062df2  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180062df9  mov     rcx, [rcx+10h]
0x180062dfd  call    WPP_SF_d
0x180062e02  test    rdi, rdi
0x180062e05  jz      short loc_180062E16
0x180062e07  mov     rcx, rdi; hMem
0x180062e0a  call    cs:__imp_LocalFree
0x180062e11  nop     dword ptr [rax+rax+00h]
0x180062e16  test    r14, r14
0x180062e19  jz      short loc_180062E2B
0x180062e1b  mov     rcx, r14; hMem
0x180062e1e  call    cs:__imp_LocalFree
0x180062e25  nop     dword ptr [rax+rax+00h]
0x180062e2a  nop
0x180062e2b  lea     rcx, [rbp+var_28]
0x180062e2f  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180062e34  nop
0x180062e35  lea     rcx, [rbp+var_18]
0x180062e39  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180062e3e  mov     eax, esi
0x180062e40  add     rsp, 78h
0x180062e44  pop     r15
0x180062e46  pop     r14
0x180062e48  pop     r13
0x180062e4a  pop     r12
0x180062e4c  pop     rdi
0x180062e4d  pop     rsi
0x180062e4e  pop     rbx
0x180062e4f  pop     rbp
0x180062e50  retn
```
