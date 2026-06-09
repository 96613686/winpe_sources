# EapTlsCreateUserProperties(ulong,IXMLDOMDocument2 *,_EAPTLS_CONN_PROPERTIES *,ulong,_EAPTLS_USER_PROPERTIES * *,ulong *)

- ea: `0x18005ee0c`
- end: `0x18005f06f`
- name: `?EapTlsCreateUserProperties@@YAKKPEAUIXMLDOMDocument2@@PEAU_EAPTLS_CONN_PROPERTIES@@KPEAPEAU_EAPTLS_USER_PROPERTIES@@PEAK@Z`
- size: `611`
- prototype: `unsigned int(unsigned int, struct IXMLDOMDocument2 *, struct _EAPTLS_CONN_PROPERTIES *, unsigned int, struct _EAPTLS_USER_PROPERTIES **, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005e7f0`

## callees

- `0x1800046e0`
- `0x180004bd0`
- `0x1800075b0`
- `0x18000f690`
- `0x1800200b4`
- `0x18002ac1c`
- `0x1800316cc`
- `0x18005ee0c`
- `0x18005f864`
- `0x18007c010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005f005`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005f005`

## string_xrefs

- `0x18005ee30`: `http://www.microsoft.com/provisioning/BaseEapUserPropertiesV1`
- `0x18005ee3b`: `http://www.microsoft.com/provisioning/EapTlsUserPropertiesV1`
- `0x18005eedc`: `xmlns:baseeapuserpropertiesv1='http://www.microsoft.com/provisioning/BaseEapUserPropertiesV1' xmlns:eaptlsuserpropertiesv1='http://www.microsoft.com/provisioning/EapTlsUserPropertiesV1'`

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
  __int64 v14; // rdx
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
0x18005ee0c  push    rbp
0x18005ee0e  push    rbx
0x18005ee0f  push    rsi
0x18005ee10  push    rdi
0x18005ee11  push    r12
0x18005ee13  push    r15
0x18005ee15  mov     rbp, rsp
0x18005ee18  sub     rsp, 78h
0x18005ee1c  mov     rdi, r8
0x18005ee1f  mov     rbx, rdx
0x18005ee22  xor     esi, esi
0x18005ee24  mov     [rbp+arg_10], rsi
0x18005ee28  mov     [rbp+var_40], rsi
0x18005ee2c  mov     [rbp+var_48], rsi
0x18005ee30  lea     rax, aHttpWwwMicroso_8; "http://www.microsoft.com/provisioning/B"...
0x18005ee37  mov     [rbp+var_20], rax
0x18005ee3b  lea     rax, aHttpWwwMicroso_3; "http://www.microsoft.com/provisioning/E"...
0x18005ee42  mov     [rbp+var_18], rax
0x18005ee46  mov     [rbp+var_10], rsi
0x18005ee4a  lea     rax, aBaseeapuserpro_1; "BaseEapUserPropertiesV1.xsd"
0x18005ee51  mov     [rbp+var_38], rax
0x18005ee55  lea     rax, aEaptlsuserprop_1; "EapTlsUserPropertiesV1.xsd"
0x18005ee5c  mov     [rbp+var_30], rax
0x18005ee60  mov     [rbp+var_28], rsi
0x18005ee64  lea     r15, WPP_GLOBAL_Control
0x18005ee6b  lea     r12, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18005ee72  test    r8, r8
0x18005ee75  jnz     short loc_18005EE9C
0x18005ee77  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ee7e  cmp     rcx, r15
0x18005ee81  jz      short loc_18005EE92
0x18005ee83  lea     edx, [rsi+21h]
0x18005ee86  mov     r8, r12
0x18005ee89  mov     rcx, [rcx+10h]
0x18005ee8d  call    WPP_SF_
0x18005ee92  mov     ebx, 57h ; 'W'
0x18005ee97  jmp     loc_18005F002
0x18005ee9c  test    byte ptr [r8+8], 1
0x18005eea1  jnz     short loc_18005EED4
0x18005eea3  mov     rcx, cs:WPP_GLOBAL_Control
0x18005eeaa  cmp     rcx, r15
0x18005eead  jz      short loc_18005EEC0
0x18005eeaf  mov     edx, 22h ; '"'
0x18005eeb4  mov     r8, r12
0x18005eeb7  mov     rcx, [rcx+10h]
0x18005eebb  call    WPP_SF_
0x18005eec0  mov     r8, [rbp+arg_20]; struct _EAPTLS_USER_PROPERTIES **
0x18005eec4  xor     edx, edx; unsigned int
0x18005eec6  xor     ecx, ecx; Src
0x18005eec8  call    ?EapTlsReadUserData@@YAKPEAEKPEAPEAU_EAPTLS_USER_PROPERTIES@@@Z; EapTlsReadUserData(uchar *,ulong,_EAPTLS_USER_PROPERTIES * *)
0x18005eecd  mov     ebx, eax
0x18005eecf  jmp     loc_18005F002
0x18005eed4  lea     r9, [rbp+var_38]; unsigned __int16 **
0x18005eed8  lea     r8, [rbp+var_20]; unsigned __int16 **
0x18005eedc  lea     rdx, aXmlnsBaseeapus; "xmlns:baseeapuserpropertiesv1='http://w"...
0x18005eee3  mov     rcx, rbx; struct IXMLDOMDocument2 *
0x18005eee6  call    ?SetNsAndSchema@@YAJPEAUIXMLDOMDocument2@@PEBGPEAPEBG2KK@Z; SetNsAndSchema(IXMLDOMDocument2 *,ushort const *,ushort const * *,ushort const * *,ulong,ulong)
0x18005eeeb  test    eax, eax
0x18005eeed  jz      short loc_18005EF2D
0x18005eeef  mov     ecx, eax
0x18005eef1  and     ecx, 1FFF0000h
0x18005eef7  cmp     ecx, 70000h
0x18005eefd  movzx   ebx, ax
0x18005ef00  jz      short loc_18005EF04
0x18005ef02  mov     ebx, eax
0x18005ef04  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ef0b  cmp     rcx, r15
0x18005ef0e  jz      loc_18005F002
0x18005ef14  mov     edx, 23h ; '#'
0x18005ef19  mov     r9d, eax
0x18005ef1c  mov     r8, r12
0x18005ef1f  mov     rcx, [rcx+10h]
0x18005ef23  call    WPP_SF_d
0x18005ef28  jmp     loc_18005F002
0x18005ef2d  mov     rcx, rbx; struct IXMLDOMDocument2 *
0x18005ef30  call    ?validate@@YAJPEAUIXMLDOMDocument2@@@Z; validate(IXMLDOMDocument2 *)
0x18005ef35  test    eax, eax
0x18005ef37  jz      short loc_18005EF65
0x18005ef39  mov     ecx, eax
0x18005ef3b  and     ecx, 1FFF0000h
0x18005ef41  cmp     ecx, 70000h
0x18005ef47  movzx   ebx, ax
0x18005ef4a  jz      short loc_18005EF4E
0x18005ef4c  mov     ebx, eax
0x18005ef4e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ef55  cmp     rcx, r15
0x18005ef58  jz      loc_18005F002
0x18005ef5e  mov     edx, 24h ; '$'
0x18005ef63  jmp     short loc_18005EF19
0x18005ef65  mov     rax, [rbx]
0x18005ef68  lea     r8, [rbp+var_48]
0x18005ef6c  lea     rdx, IID_IXMLDOMNode
0x18005ef73  mov     rcx, rbx
0x18005ef76  mov     rax, [rax]
0x18005ef79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ef7e  mov     ebx, eax
0x18005ef80  test    eax, eax
0x18005ef82  jz      short loc_18005EF95
0x18005ef84  and     eax, 1FFF0000h
0x18005ef89  cmp     eax, 70000h
0x18005ef8e  jnz     short loc_18005F002
0x18005ef90  movzx   ebx, bx
0x18005ef93  jmp     short loc_18005F002
0x18005ef95  lea     r8, [rbp+var_40]; struct IXMLDOMNode **
0x18005ef99  lea     rdx, aBaseeapuserpro_0; "/baseeapuserpropertiesv1:Eap[baseeapuse"...
0x18005efa0  mov     rcx, [rbp+var_48]; struct IXMLDOMNode *
0x18005efa4  call    ?getSingleNode@@YAJPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; getSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18005efa9  mov     ebx, eax
0x18005efab  test    eax, eax
0x18005efad  jz      short loc_18005EFD0
0x18005efaf  mov     rcx, cs:WPP_GLOBAL_Control
0x18005efb6  cmp     rcx, r15
0x18005efb9  jz      short loc_18005EFCC
0x18005efbb  mov     edx, 25h ; '%'
0x18005efc0  mov     r8, r12
0x18005efc3  mov     rcx, [rcx+10h]
0x18005efc7  call    WPP_SF_
0x18005efcc  mov     eax, ebx
0x18005efce  jmp     short loc_18005EF84
0x18005efd0  lea     r9, [rbp+arg_10]; struct _EAPTLS_USER_PROPERTIES **
0x18005efd4  mov     r8, rdi; struct _EAPTLS_CONN_PROPERTIES *
0x18005efd7  mov     rcx, [rbp+var_40]; struct IXMLDOMNode *
0x18005efdb  call    ?getEapTlsUserProperties@@YAKPEAUIXMLDOMNode@@KPEAU_EAPTLS_CONN_PROPERTIES@@PEAPEAU_EAPTLS_USER_PROPERTIES@@@Z; getEapTlsUserProperties(IXMLDOMNode *,ulong,_EAPTLS_CONN_PROPERTIES *,_EAPTLS_USER_PROPERTIES * *)
0x18005efe0  mov     ebx, eax
0x18005efe2  test    eax, eax
0x18005efe4  jnz     short loc_18005EFFE
0x18005efe6  mov     rcx, [rbp+arg_10]
0x18005efea  mov     rax, [rbp+arg_20]
0x18005efee  mov     [rax], rcx
0x18005eff1  mov     ecx, [rcx+8]
0x18005eff4  mov     rax, [rbp+arg_28]
0x18005eff8  mov     [rax], ecx
0x18005effa  xor     esi, esi
0x18005effc  jmp     short loc_18005F002
0x18005effe  mov     rsi, [rbp+arg_10]
0x18005f002  mov     rcx, rsi; hMem
0x18005f005  call    cs:__imp_LocalFree
0x18005f00b  test    ebx, ebx
0x18005f00d  jnz     short loc_18005F02C
0x18005f00f  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f016  cmp     rcx, r15
0x18005f019  jz      short loc_18005F04D
0x18005f01b  lea     edx, [rbx+26h]
0x18005f01e  mov     r8, r12
0x18005f021  mov     rcx, [rcx+10h]
0x18005f025  call    WPP_SF_
0x18005f02a  jmp     short loc_18005F04D
0x18005f02c  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f033  cmp     rcx, r15
0x18005f036  jz      short loc_18005F04D
0x18005f038  mov     edx, 27h ; '''
0x18005f03d  mov     r9d, ebx
0x18005f040  mov     r8, r12
0x18005f043  mov     rcx, [rcx+10h]
0x18005f047  call    WPP_SF_d
0x18005f04c  nop
0x18005f04d  lea     rcx, [rbp+var_48]
0x18005f051  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18005f056  nop
0x18005f057  lea     rcx, [rbp+var_40]
0x18005f05b  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18005f060  mov     eax, ebx
0x18005f062  add     rsp, 78h
0x18005f066  pop     r15
0x18005f068  pop     r12
0x18005f06a  pop     rdi
0x18005f06b  pop     rsi
0x18005f06c  pop     rbx
0x18005f06d  pop     rbp
0x18005f06e  retn
```
