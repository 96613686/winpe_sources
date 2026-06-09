# EapTlsCreateConnectionProperties(ulong,IXMLDOMDocument2 *,_EAPTLS_CONN_PROPERTIES * *,ulong *)

- ea: `0x180062228`
- end: `0x1800624ed`
- name: `?EapTlsCreateConnectionProperties@@YAKKPEAUIXMLDOMDocument2@@PEAPEAU_EAPTLS_CONN_PROPERTIES@@PEAK@Z`
- size: `709`
- prototype: `unsigned int __fastcall(unsigned int, struct IXMLDOMDocument2 *, struct _EAPTLS_CONN_PROPERTIES **, unsigned int *)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180005540`
- `0x1800059b0`

## callees

- `0x180004ae0`
- `0x180005010`
- `0x180007d00`
- `0x18000cbc4`
- `0x1800104b0`
- `0x18001fa30`
- `0x180021e74`
- `0x18002d070`
- `0x180062228`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006245e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006246d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006245e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006246d`

## string_xrefs

- `0x180062267`: `http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1`
- `0x180062288`: `http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1`
- `0x18006227d`: `http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2`
- `0x180062272`: `http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV3`
- `0x1800622cf`: `xmlns:branding='http://www.microsoft.com/provisioning/Branding' xmlns:baseeapconnectionpropertiesv1='http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1' xmlns:eaptlsconnectionpropertiesv3='http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV3' xmlns:eaptlsconnectionpropertiesv2='http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2' xmlns:eaptlsconnectionpropertiesv1='http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1' xmlns:help='http:/`

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
0x180062228  push    rbp
0x18006222a  push    rbx
0x18006222b  push    rsi
0x18006222c  push    rdi
0x18006222d  push    r12
0x18006222f  push    r14
0x180062231  push    r15
0x180062233  lea     rbp, [rsp-27h]
0x180062238  sub     rsp, 0A0h
0x18006223f  mov     r12, r9
0x180062242  mov     r14, r8
0x180062245  mov     rbx, rdx
0x180062248  mov     r15d, ecx
0x18006224b  mov     [rbp+57h+var_88], 0
0x180062253  mov     [rbp+57h+var_90], 0
0x18006225b  xor     edi, edi
0x18006225d  mov     [rbp+57h+var_98], rdi
0x180062261  xor     esi, esi
0x180062263  mov     [rbp+57h+var_A0], rsi
0x180062267  lea     rax, aHttpWwwMicroso_6; "http://www.microsoft.com/provisioning/B"...
0x18006226e  mov     [rbp+57h+var_58], rax
0x180062272  lea     rax, aHttpWwwMicroso_7; "http://www.microsoft.com/provisioning/E"...
0x180062279  mov     [rbp+57h+var_50], rax
0x18006227d  lea     rax, aHttpWwwMicroso_9; "http://www.microsoft.com/provisioning/E"...
0x180062284  mov     [rbp+57h+var_48], rax
0x180062288  lea     rax, aHttpWwwMicroso_4; "http://www.microsoft.com/provisioning/E"...
0x18006228f  mov     [rbp+57h+var_40], rax
0x180062293  mov     [rbp+57h+var_38], rsi
0x180062297  lea     rax, aBaseeapconnect_2; "BaseEapConnectionPropertiesV1.xsd"
0x18006229e  mov     [rbp+57h+var_80], rax
0x1800622a2  lea     rax, aEaptlsconnecti_20; "EapTlsConnectionPropertiesV3.xsd"
0x1800622a9  mov     [rbp+57h+var_78], rax
0x1800622ad  lea     rax, aEaptlsconnecti_25; "EapTlsConnectionPropertiesV2.xsd"
0x1800622b4  mov     [rbp+57h+var_70], rax
0x1800622b8  lea     rax, aEaptlsconnecti_13; "EapTlsConnectionPropertiesV1.xsd"
0x1800622bf  mov     [rbp+57h+var_68], rax
0x1800622c3  mov     [rbp+57h+var_60], rsi
0x1800622c7  lea     r9, [rbp+57h+var_80]; unsigned __int16 **
0x1800622cb  lea     r8, [rbp+57h+var_58]; unsigned __int16 **
0x1800622cf  lea     rdx, aXmlnsBrandingH_0; "xmlns:branding='http://www.microsoft.co"...
0x1800622d6  mov     rcx, rbx; struct IXMLDOMDocument2 *
0x1800622d9  call    ?SetNsAndSchema@@YAJPEAUIXMLDOMDocument2@@PEBGPEAPEBG2KK@Z; SetNsAndSchema(IXMLDOMDocument2 *,ushort const *,ushort const * *,ushort const * *,ulong,ulong)
0x1800622de  lea     rdx, WPP_GLOBAL_Control
0x1800622e5  test    eax, eax
0x1800622e7  jz      short loc_18006232B
0x1800622e9  mov     ecx, eax
0x1800622eb  and     ecx, 1FFF0000h
0x1800622f1  cmp     ecx, 70000h
0x1800622f7  movzx   ebx, ax
0x1800622fa  jz      short loc_1800622FE
0x1800622fc  mov     ebx, eax
0x1800622fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180062305  cmp     rcx, rdx
0x180062308  jz      loc_180062454
0x18006230e  mov     edx, 0A1h
0x180062313  mov     r9d, eax
0x180062316  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18006231d  mov     rcx, [rcx+10h]
0x180062321  call    WPP_SF_d
0x180062326  jmp     loc_180062454
0x18006232b  mov     rcx, rbx; struct IXMLDOMDocument2 *
0x18006232e  call    ?validate@@YAJPEAUIXMLDOMDocument2@@@Z; validate(IXMLDOMDocument2 *)
0x180062333  test    eax, eax
0x180062335  jz      short loc_180062380
0x180062337  mov     ecx, eax
0x180062339  and     ecx, 1FFF0000h
0x18006233f  cmp     ecx, 70000h
0x180062345  movzx   ebx, ax
0x180062348  jz      short loc_18006234C
0x18006234a  mov     ebx, eax
0x18006234c  mov     rcx, cs:WPP_GLOBAL_Control
0x180062353  lea     r14, WPP_GLOBAL_Control
0x18006235a  cmp     rcx, r14
0x18006235d  jz      loc_18006245B
0x180062363  mov     edx, 0A2h
0x180062368  mov     r9d, eax
0x18006236b  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180062372  mov     rcx, [rcx+10h]
0x180062376  call    WPP_SF_d
0x18006237b  jmp     loc_18006245B
0x180062380  mov     rax, [rbx]
0x180062383  lea     r8, [rbp+57h+var_88]
0x180062387  lea     rdx, IID_IXMLDOMNode
0x18006238e  mov     rcx, rbx
0x180062391  mov     rax, [rax]
0x180062394  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062399  mov     ebx, eax
0x18006239b  test    eax, eax
0x18006239d  jz      short loc_1800623B7
0x18006239f  and     eax, 1FFF0000h
0x1800623a4  cmp     eax, 70000h
0x1800623a9  jnz     loc_180062454
0x1800623af  movzx   ebx, bx
0x1800623b2  jmp     loc_180062454
0x1800623b7  lea     r8, [rbp+57h+var_90]; struct IXMLDOMNode **
0x1800623bb  lea     rdx, aBaseeapconnect; "/baseeapconnectionpropertiesv1:Eap[base"...
0x1800623c2  mov     rcx, [rbp+57h+var_88]; struct IXMLDOMNode *
0x1800623c6  call    ?getSingleNode@@YAJPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; getSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x1800623cb  mov     ebx, eax
0x1800623cd  test    eax, eax
0x1800623cf  jz      short loc_18006240F
0x1800623d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800623d8  lea     r14, WPP_GLOBAL_Control
0x1800623df  cmp     rcx, r14
0x1800623e2  jz      short loc_1800623FC
0x1800623e4  mov     edx, 0A3h
0x1800623e9  mov     r9d, eax
0x1800623ec  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x1800623f3  mov     rcx, [rcx+10h]
0x1800623f7  call    WPP_SF_d
0x1800623fc  mov     eax, ebx
0x1800623fe  and     eax, 1FFF0000h
0x180062403  cmp     eax, 70000h
0x180062408  jnz     short loc_18006245B
0x18006240a  movzx   ebx, bx
0x18006240d  jmp     short loc_18006245B
0x18006240f  lea     r8, [rbp+57h+var_98]; struct _EAPTLS_CONN_PROPERTIES_V1 **
0x180062413  mov     edx, r15d; unsigned int
0x180062416  mov     rcx, [rbp+57h+var_90]; struct IXMLDOMNode *
0x18006241a  call    ?getEapTlsConnectionProperties@@YAKPEAUIXMLDOMNode@@KPEAPEAU_EAPTLS_CONN_PROPERTIES_V1@@@Z; getEapTlsConnectionProperties(IXMLDOMNode *,ulong,_EAPTLS_CONN_PROPERTIES_V1 * *)
0x18006241f  mov     ebx, eax
0x180062421  mov     rdi, [rbp+57h+var_98]
0x180062425  test    eax, eax
0x180062427  jnz     short loc_180062454
0x180062429  lea     rdx, [rbp+57h+var_A0]; struct _EAPTLS_CONN_PROPERTIES **
0x18006242d  mov     rcx, rdi; struct _EAPTLS_CONN_PROPERTIES_V1 *
0x180062430  call    ?ConnPropGetV0Struct@@YAKPEAU_EAPTLS_CONN_PROPERTIES_V1@@PEAPEAU_EAPTLS_CONN_PROPERTIES@@@Z; ConnPropGetV0Struct(_EAPTLS_CONN_PROPERTIES_V1 *,_EAPTLS_CONN_PROPERTIES * *)
0x180062435  mov     ebx, eax
0x180062437  test    eax, eax
0x180062439  jnz     short loc_180062450
0x18006243b  mov     rax, [rbp+57h+var_A0]
0x18006243f  mov     [r14], rax
0x180062442  test    rax, rax
0x180062445  jz      short loc_18006244A
0x180062447  mov     eax, [rax+4]
0x18006244a  mov     [r12], eax
0x18006244e  jmp     short loc_180062454
0x180062450  mov     rsi, [rbp+57h+var_A0]
0x180062454  lea     r14, WPP_GLOBAL_Control
0x18006245b  mov     rcx, rdi; hMem
0x18006245e  call    cs:__imp_LocalFree
0x180062465  nop     dword ptr [rax+rax+00h]
0x18006246a  mov     rcx, rsi; hMem
0x18006246d  call    cs:__imp_LocalFree
0x180062474  nop     dword ptr [rax+rax+00h]
0x180062479  test    ebx, ebx
0x18006247b  jnz     short loc_1800624A0
0x18006247d  mov     rcx, cs:WPP_GLOBAL_Control
0x180062484  cmp     rcx, r14
0x180062487  jz      short loc_1800624C5
0x180062489  mov     edx, 0A4h
0x18006248e  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180062495  mov     rcx, [rcx+10h]
0x180062499  call    WPP_SF_
0x18006249e  jmp     short loc_1800624C5
0x1800624a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800624a7  cmp     rcx, r14
0x1800624aa  jz      short loc_1800624C5
0x1800624ac  mov     edx, 0A5h
0x1800624b1  mov     r9d, ebx
0x1800624b4  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x1800624bb  mov     rcx, [rcx+10h]
0x1800624bf  call    WPP_SF_d
0x1800624c4  nop
0x1800624c5  lea     rcx, [rbp+57h+var_90]
0x1800624c9  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x1800624ce  nop
0x1800624cf  lea     rcx, [rbp+57h+var_88]
0x1800624d3  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x1800624d8  mov     eax, ebx
0x1800624da  add     rsp, 0A0h
0x1800624e1  pop     r15
0x1800624e3  pop     r14
0x1800624e5  pop     r12
0x1800624e7  pop     rdi
0x1800624e8  pop     rsi
0x1800624e9  pop     rbx
0x1800624ea  pop     rbp
0x1800624eb  retn
```
