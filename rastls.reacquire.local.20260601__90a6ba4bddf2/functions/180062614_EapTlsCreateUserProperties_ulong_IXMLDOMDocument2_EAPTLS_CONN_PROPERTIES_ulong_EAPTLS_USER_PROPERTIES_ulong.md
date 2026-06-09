# EapTlsCreateUserProperties(ulong,IXMLDOMDocument2 *,_EAPTLS_CONN_PROPERTIES *,ulong,_EAPTLS_USER_PROPERTIES * *,ulong *)

- ea: `0x180062614`
- end: `0x18006287e`
- name: `?EapTlsCreateUserProperties@@YAKKPEAUIXMLDOMDocument2@@PEAU_EAPTLS_CONN_PROPERTIES@@KPEAPEAU_EAPTLS_USER_PROPERTIES@@PEAK@Z`
- size: `618`
- prototype: `unsigned int(unsigned int, struct IXMLDOMDocument2 *, struct _EAPTLS_CONN_PROPERTIES *, unsigned int, struct _EAPTLS_USER_PROPERTIES **, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180061fc4`

## callees

- `0x180004ae0`
- `0x180005010`
- `0x180007d00`
- `0x1800104b0`
- `0x180021e74`
- `0x18002d070`
- `0x180033f40`
- `0x180062614`
- `0x18006309c`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006280d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006280d`

## string_xrefs

- `0x180062638`: `http://www.microsoft.com/provisioning/BaseEapUserPropertiesV1`
- `0x180062643`: `http://www.microsoft.com/provisioning/EapTlsUserPropertiesV1`
- `0x1800626e4`: `xmlns:baseeapuserpropertiesv1='http://www.microsoft.com/provisioning/BaseEapUserPropertiesV1' xmlns:eaptlsuserpropertiesv1='http://www.microsoft.com/provisioning/EapTlsUserPropertiesV1'`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall EapTlsCreateUserProperties(
        __int64 a1,
        struct IXMLDOMDocument2 *a2,
        struct _EAPTLS_CONN_PROPERTIES *a3,
        __int64 a4,
        struct _EAPTLS_USER_PROPERTIES **a5,
        unsigned int *a6)
{
  struct _EAPTLS_USER_PROPERTIES *v8; // rsi
  unsigned int UserData; // ebx
  unsigned int v10; // eax
  struct _EAPTLS_CONTROL_BLOCK *v11; // rcx
  __int64 v12; // rdx
  unsigned int v13; // eax
  unsigned int v14; // edx
  struct _EAPTLS_USER_PROPERTIES *v15; // rcx
  struct IXMLDOMNode *v17; // [rsp+30h] [rbp-48h] BYREF
  struct IXMLDOMNode *v18; // [rsp+38h] [rbp-40h] BYREF
  unsigned __int16 *v19[3]; // [rsp+40h] [rbp-38h] BYREF
  unsigned __int16 *v20[4]; // [rsp+58h] [rbp-20h] BYREF
  struct _EAPTLS_USER_PROPERTIES *v21; // [rsp+C0h] [rbp+48h] BYREF

  v8 = 0;
  v21 = 0;
  v18 = 0;
  v17 = 0;
  v20[0] = L"http://www.microsoft.com/provisioning/BaseEapUserPropertiesV1";
  v20[1] = L"http://www.microsoft.com/provisioning/EapTlsUserPropertiesV1";
  v20[2] = 0;
  v19[0] = L"BaseEapUserPropertiesV1.xsd";
  v19[1] = L"EapTlsUserPropertiesV1.xsd";
  v19[2] = 0;
  if ( !a3 )
  {
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
    UserData = 87;
    goto LABEL_30;
  }
  if ( (*((_BYTE *)a3 + 8) & 1) == 0 )
  {
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
    UserData = EapTlsReadUserData(0, 0, a5);
    goto LABEL_30;
  }
  v10 = SetNsAndSchema(
          a2,
          L"xmlns:baseeapuserpropertiesv1='http://www.microsoft.com/provisioning/BaseEapUserPropertiesV1' xmlns:eaptlsuser"
           "propertiesv1='http://www.microsoft.com/provisioning/EapTlsUserPropertiesV1'",
          (const unsigned __int16 **)v20,
          (const unsigned __int16 **)v19);
  if ( v10 )
  {
    UserData = (unsigned __int16)v10;
    if ( (v10 & 0x1FFF0000) != 0x70000 )
      UserData = v10;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      v12 = 35;
LABEL_14:
      WPP_SF_d(*((_QWORD *)v11 + 2), v12, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, v10);
    }
  }
  else
  {
    v10 = validate(a2);
    if ( v10 )
    {
      UserData = (unsigned __int16)v10;
      if ( (v10 & 0x1FFF0000) != 0x70000 )
        UserData = v10;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        v12 = 36;
        goto LABEL_14;
      }
    }
    else
    {
      v13 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, GUID *, struct IXMLDOMNode **))a2->lpVtbl->QueryInterface)(
              a2,
              &IID_IXMLDOMNode,
              &v17);
      UserData = v13;
      if ( !v13 )
      {
        UserData = getSingleNode(v17, L"/baseeapuserpropertiesv1:Eap[baseeapuserpropertiesv1:Type=13][1]", &v18);
        if ( !UserData )
        {
          UserData = getEapTlsUserProperties(v18, v14, a3, &v21);
          if ( UserData )
          {
            v8 = v21;
          }
          else
          {
            v15 = v21;
            *a5 = v21;
            *a6 = *((_DWORD *)v15 + 2);
            v8 = 0;
          }
          goto LABEL_30;
        }
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
        v13 = UserData;
      }
      if ( (v13 & 0x1FFF0000) == 0x70000 )
        UserData = (unsigned __int16)UserData;
    }
  }
LABEL_30:
  LocalFree(v8);
  if ( UserData )
  {
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, UserData);
  }
  else if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
  }
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v17);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v18);
  return UserData;
}

```

## disassembly

```asm
0x180062614  push    rbp
0x180062616  push    rbx
0x180062617  push    rsi
0x180062618  push    rdi
0x180062619  push    r12
0x18006261b  push    r15
0x18006261d  mov     rbp, rsp
0x180062620  sub     rsp, 78h
0x180062624  mov     rdi, r8
0x180062627  mov     rbx, rdx
0x18006262a  xor     esi, esi
0x18006262c  mov     [rbp+arg_10], rsi
0x180062630  mov     [rbp+var_40], rsi
0x180062634  mov     [rbp+var_48], rsi
0x180062638  lea     rax, aHttpWwwMicroso_8; "http://www.microsoft.com/provisioning/B"...
0x18006263f  mov     [rbp+var_20], rax
0x180062643  lea     rax, aHttpWwwMicroso_3; "http://www.microsoft.com/provisioning/E"...
0x18006264a  mov     [rbp+var_18], rax
0x18006264e  mov     [rbp+var_10], rsi
0x180062652  lea     rax, aBaseeapuserpro_1; "BaseEapUserPropertiesV1.xsd"
0x180062659  mov     [rbp+var_38], rax
0x18006265d  lea     rax, aEaptlsuserprop_1; "EapTlsUserPropertiesV1.xsd"
0x180062664  mov     [rbp+var_30], rax
0x180062668  mov     [rbp+var_28], rsi
0x18006266c  lea     r15, WPP_GLOBAL_Control
0x180062673  lea     r12, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18006267a  test    r8, r8
0x18006267d  jnz     short loc_1800626A4
0x18006267f  mov     rcx, cs:WPP_GLOBAL_Control
0x180062686  cmp     rcx, r15
0x180062689  jz      short loc_18006269A
0x18006268b  lea     edx, [rsi+21h]
0x18006268e  mov     r8, r12
0x180062691  mov     rcx, [rcx+10h]
0x180062695  call    WPP_SF_
0x18006269a  mov     ebx, 57h ; 'W'
0x18006269f  jmp     loc_18006280A
0x1800626a4  test    byte ptr [r8+8], 1
0x1800626a9  jnz     short loc_1800626DC
0x1800626ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800626b2  cmp     rcx, r15
0x1800626b5  jz      short loc_1800626C8
0x1800626b7  mov     edx, 22h ; '"'
0x1800626bc  mov     r8, r12
0x1800626bf  mov     rcx, [rcx+10h]
0x1800626c3  call    WPP_SF_
0x1800626c8  mov     r8, [rbp+arg_20]; struct _EAPTLS_USER_PROPERTIES **
0x1800626cc  xor     edx, edx; unsigned int
0x1800626ce  xor     ecx, ecx; Src
0x1800626d0  call    ?EapTlsReadUserData@@YAKPEAEKPEAPEAU_EAPTLS_USER_PROPERTIES@@@Z; EapTlsReadUserData(uchar *,ulong,_EAPTLS_USER_PROPERTIES * *)
0x1800626d5  mov     ebx, eax
0x1800626d7  jmp     loc_18006280A
0x1800626dc  lea     r9, [rbp+var_38]; unsigned __int16 **
0x1800626e0  lea     r8, [rbp+var_20]; unsigned __int16 **
0x1800626e4  lea     rdx, aXmlnsBaseeapus; "xmlns:baseeapuserpropertiesv1='http://w"...
0x1800626eb  mov     rcx, rbx; struct IXMLDOMDocument2 *
0x1800626ee  call    ?SetNsAndSchema@@YAJPEAUIXMLDOMDocument2@@PEBGPEAPEBG2KK@Z; SetNsAndSchema(IXMLDOMDocument2 *,ushort const *,ushort const * *,ushort const * *,ulong,ulong)
0x1800626f3  test    eax, eax
0x1800626f5  jz      short loc_180062735
0x1800626f7  mov     ecx, eax
0x1800626f9  and     ecx, 1FFF0000h
0x1800626ff  cmp     ecx, 70000h
0x180062705  movzx   ebx, ax
0x180062708  jz      short loc_18006270C
0x18006270a  mov     ebx, eax
0x18006270c  mov     rcx, cs:WPP_GLOBAL_Control
0x180062713  cmp     rcx, r15
0x180062716  jz      loc_18006280A
0x18006271c  mov     edx, 23h ; '#'
0x180062721  mov     r9d, eax
0x180062724  mov     r8, r12
0x180062727  mov     rcx, [rcx+10h]
0x18006272b  call    WPP_SF_d
0x180062730  jmp     loc_18006280A
0x180062735  mov     rcx, rbx; struct IXMLDOMDocument2 *
0x180062738  call    ?validate@@YAJPEAUIXMLDOMDocument2@@@Z; validate(IXMLDOMDocument2 *)
0x18006273d  test    eax, eax
0x18006273f  jz      short loc_18006276D
0x180062741  mov     ecx, eax
0x180062743  and     ecx, 1FFF0000h
0x180062749  cmp     ecx, 70000h
0x18006274f  movzx   ebx, ax
0x180062752  jz      short loc_180062756
0x180062754  mov     ebx, eax
0x180062756  mov     rcx, cs:WPP_GLOBAL_Control
0x18006275d  cmp     rcx, r15
0x180062760  jz      loc_18006280A
0x180062766  mov     edx, 24h ; '$'
0x18006276b  jmp     short loc_180062721
0x18006276d  mov     rax, [rbx]
0x180062770  lea     r8, [rbp+var_48]
0x180062774  lea     rdx, IID_IXMLDOMNode
0x18006277b  mov     rcx, rbx
0x18006277e  mov     rax, [rax]
0x180062781  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062786  mov     ebx, eax
0x180062788  test    eax, eax
0x18006278a  jz      short loc_18006279D
0x18006278c  and     eax, 1FFF0000h
0x180062791  cmp     eax, 70000h
0x180062796  jnz     short loc_18006280A
0x180062798  movzx   ebx, bx
0x18006279b  jmp     short loc_18006280A
0x18006279d  lea     r8, [rbp+var_40]; struct IXMLDOMNode **
0x1800627a1  lea     rdx, aBaseeapuserpro_0; "/baseeapuserpropertiesv1:Eap[baseeapuse"...
0x1800627a8  mov     rcx, [rbp+var_48]; struct IXMLDOMNode *
0x1800627ac  call    ?getSingleNode@@YAJPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; getSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x1800627b1  mov     ebx, eax
0x1800627b3  test    eax, eax
0x1800627b5  jz      short loc_1800627D8
0x1800627b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800627be  cmp     rcx, r15
0x1800627c1  jz      short loc_1800627D4
0x1800627c3  mov     edx, 25h ; '%'
0x1800627c8  mov     r8, r12
0x1800627cb  mov     rcx, [rcx+10h]
0x1800627cf  call    WPP_SF_
0x1800627d4  mov     eax, ebx
0x1800627d6  jmp     short loc_18006278C
0x1800627d8  lea     r9, [rbp+arg_10]; struct _EAPTLS_USER_PROPERTIES **
0x1800627dc  mov     r8, rdi; struct _EAPTLS_CONN_PROPERTIES *
0x1800627df  mov     rcx, [rbp+var_40]; struct IXMLDOMNode *
0x1800627e3  call    ?getEapTlsUserProperties@@YAKPEAUIXMLDOMNode@@KPEAU_EAPTLS_CONN_PROPERTIES@@PEAPEAU_EAPTLS_USER_PROPERTIES@@@Z; getEapTlsUserProperties(IXMLDOMNode *,ulong,_EAPTLS_CONN_PROPERTIES *,_EAPTLS_USER_PROPERTIES * *)
0x1800627e8  mov     ebx, eax
0x1800627ea  test    eax, eax
0x1800627ec  jnz     short loc_180062806
0x1800627ee  mov     rcx, [rbp+arg_10]
0x1800627f2  mov     rax, [rbp+arg_20]
0x1800627f6  mov     [rax], rcx
0x1800627f9  mov     ecx, [rcx+8]
0x1800627fc  mov     rax, [rbp+arg_28]
0x180062800  mov     [rax], ecx
0x180062802  xor     esi, esi
0x180062804  jmp     short loc_18006280A
0x180062806  mov     rsi, [rbp+arg_10]
0x18006280a  mov     rcx, rsi; hMem
0x18006280d  call    cs:__imp_LocalFree
0x180062814  nop     dword ptr [rax+rax+00h]
0x180062819  test    ebx, ebx
0x18006281b  jnz     short loc_18006283A
0x18006281d  mov     rcx, cs:WPP_GLOBAL_Control
0x180062824  cmp     rcx, r15
0x180062827  jz      short loc_18006285B
0x180062829  lea     edx, [rbx+26h]
0x18006282c  mov     r8, r12
0x18006282f  mov     rcx, [rcx+10h]
0x180062833  call    WPP_SF_
0x180062838  jmp     short loc_18006285B
0x18006283a  mov     rcx, cs:WPP_GLOBAL_Control
0x180062841  cmp     rcx, r15
0x180062844  jz      short loc_18006285B
0x180062846  mov     edx, 27h ; '''
0x18006284b  mov     r9d, ebx
0x18006284e  mov     r8, r12
0x180062851  mov     rcx, [rcx+10h]
0x180062855  call    WPP_SF_d
0x18006285a  nop
0x18006285b  lea     rcx, [rbp+var_48]
0x18006285f  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180062864  nop
0x180062865  lea     rcx, [rbp+var_40]
0x180062869  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18006286e  mov     eax, ebx
0x180062870  add     rsp, 78h
0x180062874  pop     r15
0x180062876  pop     r12
0x180062878  pop     rdi
0x180062879  pop     rsi
0x18006287a  pop     rbx
0x18006287b  pop     rbp
0x18006287c  retn
```
