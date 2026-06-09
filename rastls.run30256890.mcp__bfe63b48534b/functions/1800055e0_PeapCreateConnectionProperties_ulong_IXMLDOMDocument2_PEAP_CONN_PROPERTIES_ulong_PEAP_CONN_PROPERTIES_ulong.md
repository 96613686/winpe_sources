# PeapCreateConnectionProperties(ulong,IXMLDOMDocument2 *,_PEAP_CONN_PROPERTIES *,ulong,_PEAP_CONN_PROPERTIES * *,ulong *)

- ea: `0x1800055e0`
- end: `0x18000599a`
- name: `?PeapCreateConnectionProperties@@YAKKPEAUIXMLDOMDocument2@@PEAU_PEAP_CONN_PROPERTIES@@KPEAPEAU2@PEAK@Z`
- size: `954`
- prototype: `unsigned int __fastcall(unsigned int, struct IXMLDOMDocument2 *, struct _PEAP_CONN_PROPERTIES *, unsigned int, struct _PEAP_CONN_PROPERTIES **, unsigned int *)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180005540`
- `0x1800059b0`

## callees

- `0x180004ae0`
- `0x180005010`
- `0x1800055e0`
- `0x180006620`
- `0x180007d00`
- `0x18000d660`
- `0x180010140`
- `0x18002d070`
- `0x180061f9c`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800056dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800056eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000583f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000588f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000589e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005917`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005926`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800056dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800056eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000583f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000588f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000589e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005917`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005926`
- `OLEAUT32!__imp_SysAllocString` at `0x1800057a2`
- `OLEAUT32!__imp_SysAllocString` at `0x1800057a2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800057ef`
- `OLEAUT32!__imp_SysFreeString` at `0x1800058db`
- `OLEAUT32!__imp_SysFreeString` at `0x1800057ef`
- `OLEAUT32!__imp_SysFreeString` at `0x1800058db`

## string_xrefs

- `0x18000562f`: `http://www.microsoft.com/provisioning/MsPeapConnectionPropertiesV2`
- `0x180005624`: `http://www.microsoft.com/provisioning/MsPeapConnectionPropertiesV3`
- `0x180005681`: `xmlns:branding='http://www.microsoft.com/provisioning/Branding' xmlns:baseeapconnectionpropertiesv1='http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1' xmlns:mspeapconnectionpropertiesv3='http://www.microsoft.com/provisioning/MsPeapConnectionPropertiesV3' xmlns:mspeapconnectionpropertiesv2='http://www.microsoft.com/provisioning/MsPeapConnectionPropertiesV2' xmlns:mspeapconnectionpropertiesv1='http://www.microsoft.com/provisioning/MsPeapConnectionPropertiesV1' xmlns:help='http:/`
- `0x180005619`: `http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1`
- `0x18000563a`: `http://www.microsoft.com/provisioning/MsPeapConnectionPropertiesV1`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall PeapCreateConnectionProperties(
        unsigned int a1,
        struct IXMLDOMDocument2 *a2,
        struct _PEAP_CONN_PROPERTIES *a3,
        unsigned int a4,
        struct _PEAP_CONN_PROPERTIES **a5,
        unsigned int *a6)
{
  struct _PEAP_CONN_PROPERTIES *v10; // rdi
  unsigned int v11; // eax
  unsigned int PeapConnectionProperties; // ebx
  struct _EAPTLS_CONTROL_BLOCK *v13; // rcx
  __int64 v14; // rdx
  unsigned int v15; // eax
  __int64 v16; // rsi
  unsigned __int16 *v17; // rax
  int v18; // ecx
  OLECHAR *v19; // rbx
  unsigned int ConnectionData; // eax
  _DWORD *v21; // rcx
  HLOCAL hMem; // [rsp+30h] [rbp-79h] BYREF
  struct IXMLDOMNode *v24; // [rsp+38h] [rbp-71h] BYREF
  HLOCAL v25; // [rsp+40h] [rbp-69h] BYREF
  __int64 v26; // [rsp+48h] [rbp-61h] BYREF
  unsigned __int16 *v27[5]; // [rsp+50h] [rbp-59h] BYREF
  unsigned __int16 *v28[15]; // [rsp+78h] [rbp-31h] BYREF

  hMem = 0;
  v10 = 0;
  v25 = 0;
  v26 = 0;
  v24 = 0;
  v28[0] = L"http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1";
  v28[1] = L"http://www.microsoft.com/provisioning/MsPeapConnectionPropertiesV3";
  v28[2] = L"http://www.microsoft.com/provisioning/MsPeapConnectionPropertiesV2";
  v28[3] = L"http://www.microsoft.com/provisioning/MsPeapConnectionPropertiesV1";
  v28[4] = 0;
  v27[0] = L"BaseEapConnectionPropertiesV1.xsd";
  v27[1] = L"MsPeapConnectionPropertiesV3.xsd";
  v27[2] = L"MsPeapConnectionPropertiesV2.xsd";
  v27[3] = L"MsPeapConnectionPropertiesV1.xsd";
  v27[4] = 0;
  v11 = SetNsAndSchema(
          a2,
          L"xmlns:branding='http://www.microsoft.com/provisioning/Branding' xmlns:baseeapconnectionpropertiesv1='http://ww"
           "w.microsoft.com/provisioning/BaseEapConnectionPropertiesV1' xmlns:mspeapconnectionpropertiesv3='http://www.mi"
           "crosoft.com/provisioning/MsPeapConnectionPropertiesV3' xmlns:mspeapconnectionpropertiesv2='http://www.microso"
           "ft.com/provisioning/MsPeapConnectionPropertiesV2' xmlns:mspeapconnectionpropertiesv1='http://www.microsoft.co"
           "m/provisioning/MsPeapConnectionPropertiesV1' xmlns:help='http://www.microsoft.com/provisioning/Help' xmlns:lo"
           "cations='http://www.microsoft.com/provisioning/Locations' xmlns:master='http://www.microsoft.com/provisioning"
           "/Master' xmlns:register='http://www.microsoft.com/provisioning/Register' xmlns:ssid='http://www.microsoft.com"
           "/provisioning/SSID'",
          (const unsigned __int16 **)v28,
          (const unsigned __int16 **)v27);
  if ( v11 )
  {
    PeapConnectionProperties = (unsigned __int16)v11;
    if ( (v11 & 0x1FFF0000) != 0x70000 )
      PeapConnectionProperties = v11;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      v14 = 155;
LABEL_6:
      WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, v11);
    }
  }
  else
  {
    v11 = validate(a2);
    if ( v11 )
    {
      PeapConnectionProperties = (unsigned __int16)v11;
      if ( (v11 & 0x1FFF0000) != 0x70000 )
        PeapConnectionProperties = v11;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        v14 = 156;
        goto LABEL_6;
      }
    }
    else
    {
      v15 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
              a2,
              &IID_IXMLDOMNode,
              &v26);
      PeapConnectionProperties = v15;
      if ( v15 )
      {
        if ( (v15 & 0x1FFF0000) == 0x70000 )
          PeapConnectionProperties = (unsigned __int16)v15;
      }
      else
      {
        v16 = v26;
        v17 = SysAllocString(L"/baseeapconnectionpropertiesv1:Eap[baseeapconnectionpropertiesv1:Type=25][1]");
        v19 = v17;
        v28[5] = v17;
        if ( !v17 )
          ATL::AtlThrowImpl(v18);
        if ( (*(unsigned int (__fastcall **)(__int64, unsigned __int16 *, struct IXMLDOMNode **))(*(_QWORD *)v16 + 296LL))(
               v16,
               v17,
               &v24)
          || !v24 )
        {
          if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            WPP_SF_S(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              252,
              WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids,
              L"/baseeapconnectionpropertiesv1:Eap[baseeapconnectionpropertiesv1:Type=25][1]");
          SysFreeString(v19);
          if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              157,
              WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids,
              2147942487LL);
          PeapConnectionProperties = 87;
          LocalFree(hMem);
          LocalFree(0);
          goto LABEL_37;
        }
        SysFreeString(v19);
        if ( a4 >= 0x24 )
        {
          ConnectionData = PeapReadConnectionData(a1, (unsigned __int8 *)a3, a4, (struct _PEAP_CONN_PROPERTIES **)&v25);
          if ( ConnectionData )
          {
            if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                158,
                WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids,
                ConnectionData);
            LocalFree(v25);
            v10 = 0;
          }
          else
          {
            v10 = (struct _PEAP_CONN_PROPERTIES *)v25;
          }
        }
        PeapConnectionProperties = getPeapConnectionProperties(v24, a1, v10, (struct _PEAP_CONN_PROPERTIES **)&hMem);
        if ( !PeapConnectionProperties )
        {
          v21 = hMem;
          *a5 = (struct _PEAP_CONN_PROPERTIES *)hMem;
          if ( v21 )
            LODWORD(v21) = v21[1];
          *a6 = (unsigned int)v21;
          hMem = 0;
          LocalFree(0);
          LocalFree(v10);
          goto LABEL_8;
        }
      }
    }
  }
  LocalFree(hMem);
  LocalFree(v10);
  if ( !PeapConnectionProperties )
  {
LABEL_8:
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 159, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
    goto LABEL_39;
  }
LABEL_37:
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      160,
      WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids,
      PeapConnectionProperties);
LABEL_39:
  if ( v24 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v24->lpVtbl->Release)(v24);
  if ( v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  return PeapConnectionProperties;
}

```

## disassembly

```asm
0x1800055e0  push    rbp
0x1800055e2  push    rbx
0x1800055e3  push    rsi
0x1800055e4  push    rdi
0x1800055e5  push    r12
0x1800055e7  push    r13
0x1800055e9  push    r14
0x1800055eb  push    r15
0x1800055ed  lea     rbp, [rsp-0Fh]
0x1800055f2  sub     rsp, 0B8h
0x1800055f9  mov     r14d, r9d
0x1800055fc  mov     r12, r8
0x1800055ff  mov     rbx, rdx
0x180005602  mov     r15d, ecx
0x180005605  xor     ecx, ecx
0x180005607  mov     [rbp+47h+hMem], rcx
0x18000560b  mov     edi, ecx
0x18000560d  mov     [rbp+47h+var_B0], rcx
0x180005611  mov     [rbp+47h+var_A8], rcx
0x180005615  mov     [rbp+47h+var_B8], rcx
0x180005619  lea     rax, aHttpWwwMicroso_6; "http://www.microsoft.com/provisioning/B"...
0x180005620  mov     [rbp+47h+var_78], rax
0x180005624  lea     rax, aHttpWwwMicroso_0; "http://www.microsoft.com/provisioning/M"...
0x18000562b  mov     [rbp+47h+var_70], rax
0x18000562f  lea     rax, aHttpWwwMicroso; "http://www.microsoft.com/provisioning/M"...
0x180005636  mov     [rbp+47h+var_68], rax
0x18000563a  lea     rax, aHttpWwwMicroso_1; "http://www.microsoft.com/provisioning/M"...
0x180005641  mov     [rbp+47h+var_60], rax
0x180005645  mov     [rbp+47h+var_58], rcx
0x180005649  lea     rax, aBaseeapconnect_2; "BaseEapConnectionPropertiesV1.xsd"
0x180005650  mov     [rbp+47h+var_A0], rax
0x180005654  lea     rax, aMspeapconnecti_4; "MsPeapConnectionPropertiesV3.xsd"
0x18000565b  mov     [rbp+47h+var_98], rax
0x18000565f  lea     rax, aMspeapconnecti; "MsPeapConnectionPropertiesV2.xsd"
0x180005666  mov     [rbp+47h+var_90], rax
0x18000566a  lea     rax, aMspeapconnecti_13; "MsPeapConnectionPropertiesV1.xsd"
0x180005671  mov     [rbp+47h+var_88], rax
0x180005675  mov     [rbp+47h+var_80], rcx
0x180005679  lea     r9, [rbp+47h+var_A0]; unsigned __int16 **
0x18000567d  lea     r8, [rbp+47h+var_78]; unsigned __int16 **
0x180005681  lea     rdx, aXmlnsBrandingH; "xmlns:branding='http://www.microsoft.co"...
0x180005688  mov     rcx, rbx; struct IXMLDOMDocument2 *
0x18000568b  call    ?SetNsAndSchema@@YAJPEAUIXMLDOMDocument2@@PEBGPEAPEBG2KK@Z; SetNsAndSchema(IXMLDOMDocument2 *,ushort const *,ushort const * *,ushort const * *,ulong,ulong)
0x180005690  lea     r13, WPP_GLOBAL_Control
0x180005697  test    eax, eax
0x180005699  jz      loc_180005729
0x18000569f  mov     ecx, eax
0x1800056a1  and     ecx, 1FFF0000h
0x1800056a7  cmp     ecx, 70000h
0x1800056ad  movzx   ebx, ax
0x1800056b0  jz      short loc_1800056B4
0x1800056b2  mov     ebx, eax
0x1800056b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800056bb  cmp     rcx, r13
0x1800056be  jz      short loc_1800056D8
0x1800056c0  mov     edx, 9Bh
0x1800056c5  mov     r9d, eax
0x1800056c8  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x1800056cf  mov     rcx, [rcx+10h]
0x1800056d3  call    WPP_SF_d
0x1800056d8  mov     rcx, [rbp+47h+hMem]; hMem
0x1800056dc  call    cs:__imp_LocalFree
0x1800056e3  nop     dword ptr [rax+rax+00h]
0x1800056e8  mov     rcx, rdi; hMem
0x1800056eb  call    cs:__imp_LocalFree
0x1800056f2  nop     dword ptr [rax+rax+00h]
0x1800056f7  test    ebx, ebx
0x1800056f9  jnz     loc_180005932
0x1800056ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180005706  cmp     rcx, r13
0x180005709  jz      loc_180005957
0x18000570f  mov     edx, 9Fh
0x180005714  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000571b  mov     rcx, [rcx+10h]
0x18000571f  call    WPP_SF_
0x180005724  jmp     loc_180005957
0x180005729  mov     rcx, rbx; struct IXMLDOMDocument2 *
0x18000572c  call    ?validate@@YAJPEAUIXMLDOMDocument2@@@Z; validate(IXMLDOMDocument2 *)
0x180005731  test    eax, eax
0x180005733  jz      short loc_180005760
0x180005735  mov     ecx, eax
0x180005737  and     ecx, 1FFF0000h
0x18000573d  cmp     ecx, 70000h
0x180005743  movzx   ebx, ax
0x180005746  jz      short loc_18000574A
0x180005748  mov     ebx, eax
0x18000574a  mov     rcx, cs:WPP_GLOBAL_Control
0x180005751  cmp     rcx, r13
0x180005754  jz      short loc_1800056D8
0x180005756  mov     edx, 9Ch
0x18000575b  jmp     loc_1800056C5
0x180005760  mov     rax, [rbx]
0x180005763  lea     r8, [rbp+47h+var_A8]
0x180005767  lea     rdx, IID_IXMLDOMNode
0x18000576e  mov     rcx, rbx
0x180005771  mov     rax, [rax]
0x180005774  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005779  mov     ebx, eax
0x18000577b  test    eax, eax
0x18000577d  jz      short loc_180005797
0x18000577f  and     eax, 1FFF0000h
0x180005784  cmp     eax, 70000h
0x180005789  jnz     loc_1800056D8
0x18000578f  movzx   ebx, bx
0x180005792  jmp     loc_1800056D8
0x180005797  mov     rsi, [rbp+47h+var_A8]
0x18000579b  lea     rcx, psz; "/baseeapconnectionpropertiesv1:Eap[base"...
0x1800057a2  call    cs:__imp_SysAllocString
0x1800057a9  nop     dword ptr [rax+rax+00h]
0x1800057ae  mov     rbx, rax
0x1800057b1  mov     [rbp+47h+var_50], rax
0x1800057b5  test    rax, rax
0x1800057b8  jnz     short loc_1800057C0
0x1800057ba  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800057c0  mov     rax, [rsi]
0x1800057c3  lea     r8, [rbp+47h+var_B8]
0x1800057c7  mov     rdx, rbx
0x1800057ca  mov     rcx, rsi
0x1800057cd  mov     rax, [rax+128h]
0x1800057d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057d9  test    eax, eax
0x1800057db  jnz     loc_1800058AF
0x1800057e1  cmp     [rbp+47h+var_B8], 0
0x1800057e6  jz      loc_1800058AF
0x1800057ec  mov     rcx, rbx; bstrString
0x1800057ef  call    cs:__imp_SysFreeString
0x1800057f6  nop     dword ptr [rax+rax+00h]
0x1800057fb  cmp     r14d, 24h ; '$'
0x1800057ff  jb      short loc_180005853
0x180005801  lea     r9, [rbp+47h+var_B0]; struct _PEAP_CONN_PROPERTIES **
0x180005805  mov     r8d, r14d; unsigned int
0x180005808  mov     rdx, r12; unsigned __int8 *
0x18000580b  mov     ecx, r15d; unsigned int
0x18000580e  call    ?PeapReadConnectionData@@YAKKPEAEKPEAPEAU_PEAP_CONN_PROPERTIES@@@Z; PeapReadConnectionData(ulong,uchar *,ulong,_PEAP_CONN_PROPERTIES * *)
0x180005813  test    eax, eax
0x180005815  jz      short loc_18000584F
0x180005817  mov     rcx, cs:WPP_GLOBAL_Control
0x18000581e  cmp     rcx, r13
0x180005821  jz      short loc_18000583B
0x180005823  mov     edx, 9Eh
0x180005828  mov     r9d, eax
0x18000582b  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180005832  mov     rcx, [rcx+10h]
0x180005836  call    WPP_SF_d
0x18000583b  mov     rcx, [rbp+47h+var_B0]; hMem
0x18000583f  call    cs:__imp_LocalFree
0x180005846  nop     dword ptr [rax+rax+00h]
0x18000584b  xor     edi, edi
0x18000584d  jmp     short loc_180005853
0x18000584f  mov     rdi, [rbp+47h+var_B0]
0x180005853  lea     r9, [rbp+47h+hMem]; struct _PEAP_CONN_PROPERTIES **
0x180005857  mov     r8, rdi; struct _PEAP_CONN_PROPERTIES *
0x18000585a  mov     edx, r15d; unsigned int
0x18000585d  mov     rcx, [rbp+47h+var_B8]; struct IXMLDOMNode *
0x180005861  call    ?getPeapConnectionProperties@@YAKPEAUIXMLDOMNode@@KPEAU_PEAP_CONN_PROPERTIES@@PEAPEAU2@@Z; getPeapConnectionProperties(IXMLDOMNode *,ulong,_PEAP_CONN_PROPERTIES *,_PEAP_CONN_PROPERTIES * *)
0x180005866  mov     ebx, eax
0x180005868  test    eax, eax
0x18000586a  jnz     loc_1800056D8
0x180005870  mov     rcx, [rbp+47h+hMem]
0x180005874  mov     rax, [rbp+47h+arg_20]
0x180005878  mov     [rax], rcx
0x18000587b  test    rcx, rcx
0x18000587e  jz      short loc_180005883
0x180005880  mov     ecx, [rcx+4]
0x180005883  mov     rax, [rbp+47h+arg_28]
0x180005887  mov     [rax], ecx
0x180005889  xor     ecx, ecx; hMem
0x18000588b  mov     [rbp+47h+hMem], rcx
0x18000588f  call    cs:__imp_LocalFree
0x180005896  nop     dword ptr [rax+rax+00h]
0x18000589b  mov     rcx, rdi; hMem
0x18000589e  call    cs:__imp_LocalFree
0x1800058a5  nop     dword ptr [rax+rax+00h]
0x1800058aa  jmp     loc_1800056FF
0x1800058af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800058b6  cmp     rcx, r13
0x1800058b9  jz      short loc_1800058D8
0x1800058bb  mov     edx, 0FCh
0x1800058c0  lea     r9, psz; "/baseeapconnectionpropertiesv1:Eap[base"...
0x1800058c7  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x1800058ce  mov     rcx, [rcx+10h]
0x1800058d2  call    WPP_SF_S
0x1800058d7  nop
0x1800058d8  mov     rcx, rbx; bstrString
0x1800058db  call    cs:__imp_SysFreeString
0x1800058e2  nop     dword ptr [rax+rax+00h]
0x1800058e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800058ee  cmp     rcx, r13
0x1800058f1  jz      short loc_18000590E
0x1800058f3  mov     edx, 9Dh
0x1800058f8  mov     r9d, 80070057h
0x1800058fe  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180005905  mov     rcx, [rcx+10h]
0x180005909  call    WPP_SF_d
0x18000590e  mov     ebx, 57h ; 'W'
0x180005913  mov     rcx, [rbp+47h+hMem]; hMem
0x180005917  call    cs:__imp_LocalFree
0x18000591e  nop     dword ptr [rax+rax+00h]
0x180005923  mov     rcx, rdi; hMem
0x180005926  call    cs:__imp_LocalFree
0x18000592d  nop     dword ptr [rax+rax+00h]
0x180005932  mov     rcx, cs:WPP_GLOBAL_Control
0x180005939  cmp     rcx, r13
0x18000593c  jz      short loc_180005957
0x18000593e  mov     edx, 0A0h
0x180005943  mov     r9d, ebx
0x180005946  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000594d  mov     rcx, [rcx+10h]
0x180005951  call    WPP_SF_d
0x180005956  nop
0x180005957  mov     rcx, [rbp+47h+var_B8]
0x18000595b  test    rcx, rcx
0x18000595e  jz      short loc_18000596D
0x180005960  mov     rax, [rcx]
0x180005963  mov     rax, [rax+10h]
0x180005967  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000596c  nop
0x18000596d  mov     rcx, [rbp+47h+var_A8]
0x180005971  test    rcx, rcx
0x180005974  jz      short loc_180005983
0x180005976  mov     rax, [rcx]
0x180005979  mov     rax, [rax+10h]
0x18000597d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005982  nop
0x180005983  mov     eax, ebx
0x180005985  add     rsp, 0B8h
0x18000598c  pop     r15
0x18000598e  pop     r14
0x180005990  pop     r13
0x180005992  pop     r12
0x180005994  pop     rdi
0x180005995  pop     rsi
0x180005996  pop     rbx
0x180005997  pop     rbp
0x180005998  retn
```
