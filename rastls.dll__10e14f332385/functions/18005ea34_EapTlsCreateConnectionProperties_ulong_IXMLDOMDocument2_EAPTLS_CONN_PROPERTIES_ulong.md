# EapTlsCreateConnectionProperties(ulong,IXMLDOMDocument2 *,_EAPTLS_CONN_PROPERTIES * *,ulong *)

- ea: `0x18005ea34`
- end: `0x18005ecec`
- name: `?EapTlsCreateConnectionProperties@@YAKKPEAUIXMLDOMDocument2@@PEAPEAU_EAPTLS_CONN_PROPERTIES@@PEAK@Z`
- size: `696`
- prototype: `unsigned int __fastcall(unsigned int, struct IXMLDOMDocument2 *, struct _EAPTLS_CONN_PROPERTIES **, unsigned int *)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800050d0`
- `0x180005500`

## callees

- `0x1800046e0`
- `0x180004bd0`
- `0x1800075b0`
- `0x18000c1e0`
- `0x18000f690`
- `0x18001dec0`
- `0x1800200b4`
- `0x18002ac1c`
- `0x18005ea34`
- `0x18007c010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005ec6a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005ec73`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005ec6a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005ec73`

## string_xrefs

- `0x18005ea73`: `http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1`
- `0x18005ea94`: `http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1`
- `0x18005ea89`: `http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2`
- `0x18005ea7e`: `http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV3`
- `0x18005eadb`: `xmlns:branding='http://www.microsoft.com/provisioning/Branding' xmlns:baseeapconnectionpropertiesv1='http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1' xmlns:eaptlsconnectionpropertiesv3='http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV3' xmlns:eaptlsconnectionpropertiesv2='http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2' xmlns:eaptlsconnectionpropertiesv1='http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1' xmlns:help='http:/`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall EapTlsCreateConnectionProperties(
        unsigned int a1,
        struct IXMLDOMDocument2 *a2,
        struct _EAPTLS_CONN_PROPERTIES **a3,
        unsigned int *a4)
{
  struct _EAPTLS_CONN_PROPERTIES_V1 *v8; // rdi
  struct _EAPTLS_CONN_PROPERTIES *v9; // rsi
  unsigned int v10; // eax
  unsigned int EapTlsConnectionProperties; // ebx
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int SingleNode; // eax
  struct _EAPTLS_CONN_PROPERTIES *v15; // rax
  struct _EAPTLS_CONN_PROPERTIES *v17; // [rsp+30h] [rbp-49h] BYREF
  struct _EAPTLS_CONN_PROPERTIES_V1 *v18; // [rsp+38h] [rbp-41h] BYREF
  struct IXMLDOMNode *v19; // [rsp+40h] [rbp-39h] BYREF
  struct IXMLDOMNode *v20; // [rsp+48h] [rbp-31h] BYREF
  unsigned __int16 *v21[5]; // [rsp+50h] [rbp-29h] BYREF
  unsigned __int16 *v22[11]; // [rsp+78h] [rbp-1h] BYREF

  v20 = 0;
  v19 = 0;
  v8 = 0;
  v18 = 0;
  v9 = 0;
  v17 = 0;
  v22[0] = L"http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1";
  v22[1] = L"http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV3";
  v22[2] = L"http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2";
  v22[3] = L"http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1";
  v22[4] = 0;
  v21[0] = L"BaseEapConnectionPropertiesV1.xsd";
  v21[1] = L"EapTlsConnectionPropertiesV3.xsd";
  v21[2] = L"EapTlsConnectionPropertiesV2.xsd";
  v21[3] = L"EapTlsConnectionPropertiesV1.xsd";
  v21[4] = 0;
  v10 = SetNsAndSchema(
          a2,
          L"xmlns:branding='http://www.microsoft.com/provisioning/Branding' xmlns:baseeapconnectionpropertiesv1='http://ww"
           "w.microsoft.com/provisioning/BaseEapConnectionPropertiesV1' xmlns:eaptlsconnectionpropertiesv3='http://www.mi"
           "crosoft.com/provisioning/EapTlsConnectionPropertiesV3' xmlns:eaptlsconnectionpropertiesv2='http://www.microso"
           "ft.com/provisioning/EapTlsConnectionPropertiesV2' xmlns:eaptlsconnectionpropertiesv1='http://www.microsoft.co"
           "m/provisioning/EapTlsConnectionPropertiesV1' xmlns:help='http://www.microsoft.com/provisioning/Help' xmlns:lo"
           "cations='http://www.microsoft.com/provisioning/Locations' xmlns:master='http://www.microsoft.com/provisioning"
           "/Master' xmlns:register='http://www.microsoft.com/provisioning/Register' xmlns:ssid='http://www.microsoft.com"
           "/provisioning/SSID'",
          (const unsigned __int16 **)v22,
          (const unsigned __int16 **)v21);
  if ( v10 )
  {
    EapTlsConnectionProperties = (unsigned __int16)v10;
    if ( (v10 & 0x1FFF0000) != 0x70000 )
      EapTlsConnectionProperties = v10;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 161, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, v10);
  }
  else
  {
    v12 = validate(a2);
    if ( v12 )
    {
      EapTlsConnectionProperties = (unsigned __int16)v12;
      if ( (v12 & 0x1FFF0000) != 0x70000 )
        EapTlsConnectionProperties = v12;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 162, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, v12);
    }
    else
    {
      v13 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, GUID *, struct IXMLDOMNode **))a2->lpVtbl->QueryInterface)(
              a2,
              &IID_IXMLDOMNode,
              &v20);
      EapTlsConnectionProperties = v13;
      if ( v13 )
      {
        if ( (v13 & 0x1FFF0000) == 0x70000 )
          EapTlsConnectionProperties = (unsigned __int16)v13;
      }
      else
      {
        SingleNode = getSingleNode(
                       v20,
                       L"/baseeapconnectionpropertiesv1:Eap[baseeapconnectionpropertiesv1:Type=13][1]",
                       &v19);
        EapTlsConnectionProperties = SingleNode;
        if ( SingleNode )
        {
          if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              163,
              WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids,
              SingleNode);
          if ( (EapTlsConnectionProperties & 0x1FFF0000) == 0x70000 )
            EapTlsConnectionProperties = (unsigned __int16)EapTlsConnectionProperties;
        }
        else
        {
          EapTlsConnectionProperties = getEapTlsConnectionProperties(v19, a1, &v18);
          v8 = v18;
          if ( !EapTlsConnectionProperties )
          {
            EapTlsConnectionProperties = ConnPropGetV0Struct(v18, &v17);
            if ( EapTlsConnectionProperties )
            {
              v9 = v17;
            }
            else
            {
              v15 = v17;
              *a3 = v17;
              if ( v15 )
                LODWORD(v15) = *((_DWORD *)v15 + 1);
              *a4 = (unsigned int)v15;
            }
          }
        }
      }
    }
  }
  LocalFree(v8);
  LocalFree(v9);
  if ( EapTlsConnectionProperties )
  {
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        165,
        WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids,
        EapTlsConnectionProperties);
  }
  else if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 164, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
  }
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v19);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v20);
  return EapTlsConnectionProperties;
}

```

## disassembly

```asm
0x18005ea34  push    rbp
0x18005ea36  push    rbx
0x18005ea37  push    rsi
0x18005ea38  push    rdi
0x18005ea39  push    r12
0x18005ea3b  push    r14
0x18005ea3d  push    r15
0x18005ea3f  lea     rbp, [rsp-27h]
0x18005ea44  sub     rsp, 0A0h
0x18005ea4b  mov     r12, r9
0x18005ea4e  mov     r14, r8
0x18005ea51  mov     rbx, rdx
0x18005ea54  mov     r15d, ecx
0x18005ea57  mov     [rbp+57h+var_88], 0
0x18005ea5f  mov     [rbp+57h+var_90], 0
0x18005ea67  xor     edi, edi
0x18005ea69  mov     [rbp+57h+var_98], rdi
0x18005ea6d  xor     esi, esi
0x18005ea6f  mov     [rbp+57h+var_A0], rsi
0x18005ea73  lea     rax, aHttpWwwMicroso_6; "http://www.microsoft.com/provisioning/B"...
0x18005ea7a  mov     [rbp+57h+var_58], rax
0x18005ea7e  lea     rax, aHttpWwwMicroso_7; "http://www.microsoft.com/provisioning/E"...
0x18005ea85  mov     [rbp+57h+var_50], rax
0x18005ea89  lea     rax, aHttpWwwMicroso_9; "http://www.microsoft.com/provisioning/E"...
0x18005ea90  mov     [rbp+57h+var_48], rax
0x18005ea94  lea     rax, aHttpWwwMicroso_4; "http://www.microsoft.com/provisioning/E"...
0x18005ea9b  mov     [rbp+57h+var_40], rax
0x18005ea9f  mov     [rbp+57h+var_38], rsi
0x18005eaa3  lea     rax, aBaseeapconnect_2; "BaseEapConnectionPropertiesV1.xsd"
0x18005eaaa  mov     [rbp+57h+var_80], rax
0x18005eaae  lea     rax, aEaptlsconnecti_20; "EapTlsConnectionPropertiesV3.xsd"
0x18005eab5  mov     [rbp+57h+var_78], rax
0x18005eab9  lea     rax, aEaptlsconnecti_25; "EapTlsConnectionPropertiesV2.xsd"
0x18005eac0  mov     [rbp+57h+var_70], rax
0x18005eac4  lea     rax, aEaptlsconnecti_13; "EapTlsConnectionPropertiesV1.xsd"
0x18005eacb  mov     [rbp+57h+var_68], rax
0x18005eacf  mov     [rbp+57h+var_60], rsi
0x18005ead3  lea     r9, [rbp+57h+var_80]; unsigned __int16 **
0x18005ead7  lea     r8, [rbp+57h+var_58]; unsigned __int16 **
0x18005eadb  lea     rdx, aXmlnsBrandingH_0; "xmlns:branding='http://www.microsoft.co"...
0x18005eae2  mov     rcx, rbx; struct IXMLDOMDocument2 *
0x18005eae5  call    ?SetNsAndSchema@@YAJPEAUIXMLDOMDocument2@@PEBGPEAPEBG2KK@Z; SetNsAndSchema(IXMLDOMDocument2 *,ushort const *,ushort const * *,ushort const * *,ulong,ulong)
0x18005eaea  lea     rdx, WPP_GLOBAL_Control
0x18005eaf1  test    eax, eax
0x18005eaf3  jz      short loc_18005EB37
0x18005eaf5  mov     ecx, eax
0x18005eaf7  and     ecx, 1FFF0000h
0x18005eafd  cmp     ecx, 70000h
0x18005eb03  movzx   ebx, ax
0x18005eb06  jz      short loc_18005EB0A
0x18005eb08  mov     ebx, eax
0x18005eb0a  mov     rcx, cs:WPP_GLOBAL_Control
0x18005eb11  cmp     rcx, rdx
0x18005eb14  jz      loc_18005EC60
0x18005eb1a  mov     edx, 0A1h
0x18005eb1f  mov     r9d, eax
0x18005eb22  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18005eb29  mov     rcx, [rcx+10h]
0x18005eb2d  call    WPP_SF_d
0x18005eb32  jmp     loc_18005EC60
0x18005eb37  mov     rcx, rbx; struct IXMLDOMDocument2 *
0x18005eb3a  call    ?validate@@YAJPEAUIXMLDOMDocument2@@@Z; validate(IXMLDOMDocument2 *)
0x18005eb3f  test    eax, eax
0x18005eb41  jz      short loc_18005EB8C
0x18005eb43  mov     ecx, eax
0x18005eb45  and     ecx, 1FFF0000h
0x18005eb4b  cmp     ecx, 70000h
0x18005eb51  movzx   ebx, ax
0x18005eb54  jz      short loc_18005EB58
0x18005eb56  mov     ebx, eax
0x18005eb58  mov     rcx, cs:WPP_GLOBAL_Control
0x18005eb5f  lea     r14, WPP_GLOBAL_Control
0x18005eb66  cmp     rcx, r14
0x18005eb69  jz      loc_18005EC67
0x18005eb6f  mov     edx, 0A2h
0x18005eb74  mov     r9d, eax
0x18005eb77  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18005eb7e  mov     rcx, [rcx+10h]
0x18005eb82  call    WPP_SF_d
0x18005eb87  jmp     loc_18005EC67
0x18005eb8c  mov     rax, [rbx]
0x18005eb8f  lea     r8, [rbp+57h+var_88]
0x18005eb93  lea     rdx, IID_IXMLDOMNode
0x18005eb9a  mov     rcx, rbx
0x18005eb9d  mov     rax, [rax]
0x18005eba0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005eba5  mov     ebx, eax
0x18005eba7  test    eax, eax
0x18005eba9  jz      short loc_18005EBC3
0x18005ebab  and     eax, 1FFF0000h
0x18005ebb0  cmp     eax, 70000h
0x18005ebb5  jnz     loc_18005EC60
0x18005ebbb  movzx   ebx, bx
0x18005ebbe  jmp     loc_18005EC60
0x18005ebc3  lea     r8, [rbp+57h+var_90]; struct IXMLDOMNode **
0x18005ebc7  lea     rdx, aBaseeapconnect; "/baseeapconnectionpropertiesv1:Eap[base"...
0x18005ebce  mov     rcx, [rbp+57h+var_88]; struct IXMLDOMNode *
0x18005ebd2  call    ?getSingleNode@@YAJPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; getSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18005ebd7  mov     ebx, eax
0x18005ebd9  test    eax, eax
0x18005ebdb  jz      short loc_18005EC1B
0x18005ebdd  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ebe4  lea     r14, WPP_GLOBAL_Control
0x18005ebeb  cmp     rcx, r14
0x18005ebee  jz      short loc_18005EC08
0x18005ebf0  mov     edx, 0A3h
0x18005ebf5  mov     r9d, eax
0x18005ebf8  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18005ebff  mov     rcx, [rcx+10h]
0x18005ec03  call    WPP_SF_d
0x18005ec08  mov     eax, ebx
0x18005ec0a  and     eax, 1FFF0000h
0x18005ec0f  cmp     eax, 70000h
0x18005ec14  jnz     short loc_18005EC67
0x18005ec16  movzx   ebx, bx
0x18005ec19  jmp     short loc_18005EC67
0x18005ec1b  lea     r8, [rbp+57h+var_98]; struct _EAPTLS_CONN_PROPERTIES_V1 **
0x18005ec1f  mov     edx, r15d; unsigned int
0x18005ec22  mov     rcx, [rbp+57h+var_90]; struct IXMLDOMNode *
0x18005ec26  call    ?getEapTlsConnectionProperties@@YAKPEAUIXMLDOMNode@@KPEAPEAU_EAPTLS_CONN_PROPERTIES_V1@@@Z; getEapTlsConnectionProperties(IXMLDOMNode *,ulong,_EAPTLS_CONN_PROPERTIES_V1 * *)
0x18005ec2b  mov     ebx, eax
0x18005ec2d  mov     rdi, [rbp+57h+var_98]
0x18005ec31  test    eax, eax
0x18005ec33  jnz     short loc_18005EC60
0x18005ec35  lea     rdx, [rbp+57h+var_A0]; struct _EAPTLS_CONN_PROPERTIES **
0x18005ec39  mov     rcx, rdi; struct _EAPTLS_CONN_PROPERTIES_V1 *
0x18005ec3c  call    ?ConnPropGetV0Struct@@YAKPEAU_EAPTLS_CONN_PROPERTIES_V1@@PEAPEAU_EAPTLS_CONN_PROPERTIES@@@Z; ConnPropGetV0Struct(_EAPTLS_CONN_PROPERTIES_V1 *,_EAPTLS_CONN_PROPERTIES * *)
0x18005ec41  mov     ebx, eax
0x18005ec43  test    eax, eax
0x18005ec45  jnz     short loc_18005EC5C
0x18005ec47  mov     rax, [rbp+57h+var_A0]
0x18005ec4b  mov     [r14], rax
0x18005ec4e  test    rax, rax
0x18005ec51  jz      short loc_18005EC56
0x18005ec53  mov     eax, [rax+4]
0x18005ec56  mov     [r12], eax
0x18005ec5a  jmp     short loc_18005EC60
0x18005ec5c  mov     rsi, [rbp+57h+var_A0]
0x18005ec60  lea     r14, WPP_GLOBAL_Control
0x18005ec67  mov     rcx, rdi; hMem
0x18005ec6a  call    cs:__imp_LocalFree
0x18005ec70  mov     rcx, rsi; hMem
0x18005ec73  call    cs:__imp_LocalFree
0x18005ec79  test    ebx, ebx
0x18005ec7b  jnz     short loc_18005ECA0
0x18005ec7d  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ec84  cmp     rcx, r14
0x18005ec87  jz      short loc_18005ECC5
0x18005ec89  mov     edx, 0A4h
0x18005ec8e  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18005ec95  mov     rcx, [rcx+10h]
0x18005ec99  call    WPP_SF_
0x18005ec9e  jmp     short loc_18005ECC5
0x18005eca0  mov     rcx, cs:WPP_GLOBAL_Control
0x18005eca7  cmp     rcx, r14
0x18005ecaa  jz      short loc_18005ECC5
0x18005ecac  mov     edx, 0A5h
0x18005ecb1  mov     r9d, ebx
0x18005ecb4  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18005ecbb  mov     rcx, [rcx+10h]
0x18005ecbf  call    WPP_SF_d
0x18005ecc4  nop
0x18005ecc5  lea     rcx, [rbp+57h+var_90]
0x18005ecc9  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18005ecce  nop
0x18005eccf  lea     rcx, [rbp+57h+var_88]
0x18005ecd3  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18005ecd8  mov     eax, ebx
0x18005ecda  add     rsp, 0A0h
0x18005ece1  pop     r15
0x18005ece3  pop     r14
0x18005ece5  pop     r12
0x18005ece7  pop     rdi
0x18005ece8  pop     rsi
0x18005ece9  pop     rbx
0x18005ecea  pop     rbp
0x18005eceb  retn
```
