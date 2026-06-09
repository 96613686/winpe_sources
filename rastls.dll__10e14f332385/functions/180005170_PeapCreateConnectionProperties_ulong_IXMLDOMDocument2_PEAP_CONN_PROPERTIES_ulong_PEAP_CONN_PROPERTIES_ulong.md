# PeapCreateConnectionProperties(ulong,IXMLDOMDocument2 *,_PEAP_CONN_PROPERTIES *,ulong,_PEAP_CONN_PROPERTIES * *,ulong *)

- ea: `0x180005170`
- end: `0x1800054e9`
- name: `?PeapCreateConnectionProperties@@YAKKPEAUIXMLDOMDocument2@@PEAU_PEAP_CONN_PROPERTIES@@KPEAPEAU2@PEAK@Z`
- size: `889`
- prototype: `unsigned int __fastcall(unsigned int, struct IXMLDOMDocument2 *, struct _PEAP_CONN_PROPERTIES *, unsigned int, struct _PEAP_CONN_PROPERTIES **, unsigned int *)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800050d0`
- `0x180005500`

## callees

- `0x1800046e0`
- `0x180004bd0`
- `0x180005170`
- `0x1800060f0`
- `0x1800075b0`
- `0x18000cbb0`
- `0x18000f350`
- `0x18002ac1c`
- `0x18005e7c8`
- `0x18007c010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005268`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005271`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800053b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800053fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005406`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005473`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000547c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005268`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005271`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800053b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800053fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005406`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005473`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000547c`
- `OLEAUT32!__imp_SysAllocString` at `0x180005322`
- `OLEAUT32!__imp_SysAllocString` at `0x180005322`
- `OLEAUT32!__imp_SysFreeString` at `0x180005369`
- `OLEAUT32!__imp_SysFreeString` at `0x18000543d`
- `OLEAUT32!__imp_SysFreeString` at `0x180005369`
- `OLEAUT32!__imp_SysFreeString` at `0x18000543d`

## string_xrefs

- `0x1800051bf`: `http://www.microsoft.com/provisioning/MsPeapConnectionPropertiesV2`
- `0x1800051b4`: `http://www.microsoft.com/provisioning/MsPeapConnectionPropertiesV3`
- `0x180005211`: `xmlns:branding='http://www.microsoft.com/provisioning/Branding' xmlns:baseeapconnectionpropertiesv1='http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1' xmlns:mspeapconnectionpropertiesv3='http://www.microsoft.com/provisioning/MsPeapConnectionPropertiesV3' xmlns:mspeapconnectionpropertiesv2='http://www.microsoft.com/provisioning/MsPeapConnectionPropertiesV2' xmlns:mspeapconnectionpropertiesv1='http://www.microsoft.com/provisioning/MsPeapConnectionPropertiesV1' xmlns:help='http:/`
- `0x1800051a9`: `http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1`
- `0x1800051ca`: `http://www.microsoft.com/provisioning/MsPeapConnectionPropertiesV1`

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
          ConnectionData = PeapReadConnectionData(a1, (unsigned __int8 *)a3, a4, (BYTE **)&v25);
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
0x180005170  push    rbp
0x180005172  push    rbx
0x180005173  push    rsi
0x180005174  push    rdi
0x180005175  push    r12
0x180005177  push    r13
0x180005179  push    r14
0x18000517b  push    r15
0x18000517d  lea     rbp, [rsp-0Fh]
0x180005182  sub     rsp, 0B8h
0x180005189  mov     r14d, r9d
0x18000518c  mov     r12, r8
0x18000518f  mov     rbx, rdx
0x180005192  mov     r15d, ecx
0x180005195  xor     ecx, ecx
0x180005197  mov     [rbp+47h+hMem], rcx
0x18000519b  mov     edi, ecx
0x18000519d  mov     [rbp+47h+var_B0], rcx
0x1800051a1  mov     [rbp+47h+var_A8], rcx
0x1800051a5  mov     [rbp+47h+var_B8], rcx
0x1800051a9  lea     rax, aHttpWwwMicroso_6; "http://www.microsoft.com/provisioning/B"...
0x1800051b0  mov     [rbp+47h+var_78], rax
0x1800051b4  lea     rax, aHttpWwwMicroso_0; "http://www.microsoft.com/provisioning/M"...
0x1800051bb  mov     [rbp+47h+var_70], rax
0x1800051bf  lea     rax, aHttpWwwMicroso; "http://www.microsoft.com/provisioning/M"...
0x1800051c6  mov     [rbp+47h+var_68], rax
0x1800051ca  lea     rax, aHttpWwwMicroso_1; "http://www.microsoft.com/provisioning/M"...
0x1800051d1  mov     [rbp+47h+var_60], rax
0x1800051d5  mov     [rbp+47h+var_58], rcx
0x1800051d9  lea     rax, aBaseeapconnect_2; "BaseEapConnectionPropertiesV1.xsd"
0x1800051e0  mov     [rbp+47h+var_A0], rax
0x1800051e4  lea     rax, aMspeapconnecti_4; "MsPeapConnectionPropertiesV3.xsd"
0x1800051eb  mov     [rbp+47h+var_98], rax
0x1800051ef  lea     rax, aMspeapconnecti; "MsPeapConnectionPropertiesV2.xsd"
0x1800051f6  mov     [rbp+47h+var_90], rax
0x1800051fa  lea     rax, aMspeapconnecti_13; "MsPeapConnectionPropertiesV1.xsd"
0x180005201  mov     [rbp+47h+var_88], rax
0x180005205  mov     [rbp+47h+var_80], rcx
0x180005209  lea     r9, [rbp+47h+var_A0]; unsigned __int16 **
0x18000520d  lea     r8, [rbp+47h+var_78]; unsigned __int16 **
0x180005211  lea     rdx, aXmlnsBrandingH; "xmlns:branding='http://www.microsoft.co"...
0x180005218  mov     rcx, rbx; struct IXMLDOMDocument2 *
0x18000521b  call    ?SetNsAndSchema@@YAJPEAUIXMLDOMDocument2@@PEBGPEAPEBG2KK@Z; SetNsAndSchema(IXMLDOMDocument2 *,ushort const *,ushort const * *,ushort const * *,ulong,ulong)
0x180005220  lea     r13, WPP_GLOBAL_Control
0x180005227  test    eax, eax
0x180005229  jz      short loc_1800052A9
0x18000522b  mov     ecx, eax
0x18000522d  and     ecx, 1FFF0000h
0x180005233  cmp     ecx, 70000h
0x180005239  movzx   ebx, ax
0x18000523c  jz      short loc_180005240
0x18000523e  mov     ebx, eax
0x180005240  mov     rcx, cs:WPP_GLOBAL_Control
0x180005247  cmp     rcx, r13
0x18000524a  jz      short loc_180005264
0x18000524c  mov     edx, 9Bh
0x180005251  mov     r9d, eax
0x180005254  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000525b  mov     rcx, [rcx+10h]
0x18000525f  call    WPP_SF_d
0x180005264  mov     rcx, [rbp+47h+hMem]; hMem
0x180005268  call    cs:__imp_LocalFree
0x18000526e  mov     rcx, rdi; hMem
0x180005271  call    cs:__imp_LocalFree
0x180005277  test    ebx, ebx
0x180005279  jnz     loc_180005482
0x18000527f  mov     rcx, cs:WPP_GLOBAL_Control
0x180005286  cmp     rcx, r13
0x180005289  jz      loc_1800054A7
0x18000528f  mov     edx, 9Fh
0x180005294  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000529b  mov     rcx, [rcx+10h]
0x18000529f  call    WPP_SF_
0x1800052a4  jmp     loc_1800054A7
0x1800052a9  mov     rcx, rbx; struct IXMLDOMDocument2 *
0x1800052ac  call    ?validate@@YAJPEAUIXMLDOMDocument2@@@Z; validate(IXMLDOMDocument2 *)
0x1800052b1  test    eax, eax
0x1800052b3  jz      short loc_1800052E0
0x1800052b5  mov     ecx, eax
0x1800052b7  and     ecx, 1FFF0000h
0x1800052bd  cmp     ecx, 70000h
0x1800052c3  movzx   ebx, ax
0x1800052c6  jz      short loc_1800052CA
0x1800052c8  mov     ebx, eax
0x1800052ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800052d1  cmp     rcx, r13
0x1800052d4  jz      short loc_180005264
0x1800052d6  mov     edx, 9Ch
0x1800052db  jmp     loc_180005251
0x1800052e0  mov     rax, [rbx]
0x1800052e3  lea     r8, [rbp+47h+var_A8]
0x1800052e7  lea     rdx, IID_IXMLDOMNode
0x1800052ee  mov     rcx, rbx
0x1800052f1  mov     rax, [rax]
0x1800052f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052f9  mov     ebx, eax
0x1800052fb  test    eax, eax
0x1800052fd  jz      short loc_180005317
0x1800052ff  and     eax, 1FFF0000h
0x180005304  cmp     eax, 70000h
0x180005309  jnz     loc_180005264
0x18000530f  movzx   ebx, bx
0x180005312  jmp     loc_180005264
0x180005317  mov     rsi, [rbp+47h+var_A8]
0x18000531b  lea     rcx, psz; "/baseeapconnectionpropertiesv1:Eap[base"...
0x180005322  call    cs:__imp_SysAllocString
0x180005328  mov     rbx, rax
0x18000532b  mov     [rbp+47h+var_50], rax
0x18000532f  test    rax, rax
0x180005332  jnz     short loc_18000533A
0x180005334  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000533a  mov     rax, [rsi]
0x18000533d  lea     r8, [rbp+47h+var_B8]
0x180005341  mov     rdx, rbx
0x180005344  mov     rcx, rsi
0x180005347  mov     rax, [rax+128h]
0x18000534e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005353  test    eax, eax
0x180005355  jnz     loc_180005411
0x18000535b  cmp     [rbp+47h+var_B8], 0
0x180005360  jz      loc_180005411
0x180005366  mov     rcx, rbx; bstrString
0x180005369  call    cs:__imp_SysFreeString
0x18000536f  cmp     r14d, 24h ; '$'
0x180005373  jb      short loc_1800053C1
0x180005375  lea     r9, [rbp+47h+var_B0]; struct _PEAP_CONN_PROPERTIES **
0x180005379  mov     r8d, r14d; unsigned int
0x18000537c  mov     rdx, r12; unsigned __int8 *
0x18000537f  mov     ecx, r15d; unsigned int
0x180005382  call    ?PeapReadConnectionData@@YAKKPEAEKPEAPEAU_PEAP_CONN_PROPERTIES@@@Z; PeapReadConnectionData(ulong,uchar *,ulong,_PEAP_CONN_PROPERTIES * *)
0x180005387  test    eax, eax
0x180005389  jz      short loc_1800053BD
0x18000538b  mov     rcx, cs:WPP_GLOBAL_Control
0x180005392  cmp     rcx, r13
0x180005395  jz      short loc_1800053AF
0x180005397  mov     edx, 9Eh
0x18000539c  mov     r9d, eax
0x18000539f  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x1800053a6  mov     rcx, [rcx+10h]
0x1800053aa  call    WPP_SF_d
0x1800053af  mov     rcx, [rbp+47h+var_B0]; hMem
0x1800053b3  call    cs:__imp_LocalFree
0x1800053b9  xor     edi, edi
0x1800053bb  jmp     short loc_1800053C1
0x1800053bd  mov     rdi, [rbp+47h+var_B0]
0x1800053c1  lea     r9, [rbp+47h+hMem]; struct _PEAP_CONN_PROPERTIES **
0x1800053c5  mov     r8, rdi; struct _PEAP_CONN_PROPERTIES *
0x1800053c8  mov     edx, r15d; unsigned int
0x1800053cb  mov     rcx, [rbp+47h+var_B8]; struct IXMLDOMNode *
0x1800053cf  call    ?getPeapConnectionProperties@@YAKPEAUIXMLDOMNode@@KPEAU_PEAP_CONN_PROPERTIES@@PEAPEAU2@@Z; getPeapConnectionProperties(IXMLDOMNode *,ulong,_PEAP_CONN_PROPERTIES *,_PEAP_CONN_PROPERTIES * *)
0x1800053d4  mov     ebx, eax
0x1800053d6  test    eax, eax
0x1800053d8  jnz     loc_180005264
0x1800053de  mov     rcx, [rbp+47h+hMem]
0x1800053e2  mov     rax, [rbp+47h+arg_20]
0x1800053e6  mov     [rax], rcx
0x1800053e9  test    rcx, rcx
0x1800053ec  jz      short loc_1800053F1
0x1800053ee  mov     ecx, [rcx+4]
0x1800053f1  mov     rax, [rbp+47h+arg_28]
0x1800053f5  mov     [rax], ecx
0x1800053f7  xor     ecx, ecx; hMem
0x1800053f9  mov     [rbp+47h+hMem], rcx
0x1800053fd  call    cs:__imp_LocalFree
0x180005403  mov     rcx, rdi; hMem
0x180005406  call    cs:__imp_LocalFree
0x18000540c  jmp     loc_18000527F
0x180005411  mov     rcx, cs:WPP_GLOBAL_Control
0x180005418  cmp     rcx, r13
0x18000541b  jz      short loc_18000543A
0x18000541d  mov     edx, 0FCh
0x180005422  lea     r9, psz; "/baseeapconnectionpropertiesv1:Eap[base"...
0x180005429  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180005430  mov     rcx, [rcx+10h]
0x180005434  call    WPP_SF_S
0x180005439  nop
0x18000543a  mov     rcx, rbx; bstrString
0x18000543d  call    cs:__imp_SysFreeString
0x180005443  mov     rcx, cs:WPP_GLOBAL_Control
0x18000544a  cmp     rcx, r13
0x18000544d  jz      short loc_18000546A
0x18000544f  mov     edx, 9Dh
0x180005454  mov     r9d, 80070057h
0x18000545a  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180005461  mov     rcx, [rcx+10h]
0x180005465  call    WPP_SF_d
0x18000546a  mov     ebx, 57h ; 'W'
0x18000546f  mov     rcx, [rbp+47h+hMem]; hMem
0x180005473  call    cs:__imp_LocalFree
0x180005479  mov     rcx, rdi; hMem
0x18000547c  call    cs:__imp_LocalFree
0x180005482  mov     rcx, cs:WPP_GLOBAL_Control
0x180005489  cmp     rcx, r13
0x18000548c  jz      short loc_1800054A7
0x18000548e  mov     edx, 0A0h
0x180005493  mov     r9d, ebx
0x180005496  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000549d  mov     rcx, [rcx+10h]
0x1800054a1  call    WPP_SF_d
0x1800054a6  nop
0x1800054a7  mov     rcx, [rbp+47h+var_B8]
0x1800054ab  test    rcx, rcx
0x1800054ae  jz      short loc_1800054BD
0x1800054b0  mov     rax, [rcx]
0x1800054b3  mov     rax, [rax+10h]
0x1800054b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054bc  nop
0x1800054bd  mov     rcx, [rbp+47h+var_A8]
0x1800054c1  test    rcx, rcx
0x1800054c4  jz      short loc_1800054D3
0x1800054c6  mov     rax, [rcx]
0x1800054c9  mov     rax, [rax+10h]
0x1800054cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054d2  nop
0x1800054d3  mov     eax, ebx
0x1800054d5  add     rsp, 0B8h
0x1800054dc  pop     r15
0x1800054de  pop     r14
0x1800054e0  pop     r13
0x1800054e2  pop     r12
0x1800054e4  pop     rdi
0x1800054e5  pop     rsi
0x1800054e6  pop     rbx
0x1800054e7  pop     rbp
0x1800054e8  retn
```
