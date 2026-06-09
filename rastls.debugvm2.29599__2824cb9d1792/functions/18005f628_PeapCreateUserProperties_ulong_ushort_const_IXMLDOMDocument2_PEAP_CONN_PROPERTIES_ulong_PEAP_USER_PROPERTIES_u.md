# PeapCreateUserProperties(ulong,ushort const *,IXMLDOMDocument2 *,_PEAP_CONN_PROPERTIES *,ulong,_PEAP_USER_PROPERTIES *,ulong,_PEAP_USER_PROPERTIES * *,ulong *)

- ea: `0x18005f628`
- end: `0x18005f85d`
- name: `?PeapCreateUserProperties@@YAKKPEBGPEAUIXMLDOMDocument2@@PEAU_PEAP_CONN_PROPERTIES@@KPEAU_PEAP_USER_PROPERTIES@@KPEAPEAU3@PEAK@Z`
- size: `565`
- prototype: `unsigned int __fastcall(unsigned int, const unsigned __int16 *, struct IXMLDOMDocument2 *, struct _PEAP_CONN_PROPERTIES *, unsigned int, struct _PEAP_USER_PROPERTIES *, unsigned int, struct _PEAP_USER_PROPERTIES **, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
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
- `0x18005f628`
- `0x1800604e4`
- `0x18007c010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005f7e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005f7e6`

## string_xrefs

- `0x18005f657`: `http://www.microsoft.com/provisioning/BaseEapUserPropertiesV1`
- `0x18005f662`: `http://www.microsoft.com/provisioning/MsPeapUserPropertiesV1`
- `0x18005f693`: `xmlns:baseeapuserpropertiesv1='http://www.microsoft.com/provisioning/BaseEapUserPropertiesV1' xmlns:mspeapuserpropertiesv1='http://www.microsoft.com/provisioning/MsPeapUserPropertiesV1'`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PeapCreateUserProperties(
        unsigned int a1,
        const unsigned __int16 *a2,
        struct IXMLDOMDocument2 *a3,
        struct _PEAP_CONN_PROPERTIES *a4,
        unsigned int a5,
        struct _PEAP_USER_PROPERTIES *a6,
        unsigned int a7,
        struct _PEAP_USER_PROPERTIES **a8,
        unsigned int *a9)
{
  struct _PEAP_USER_PROPERTIES *v13; // rdi
  unsigned int v14; // eax
  unsigned int SingleNode; // ebx
  struct _EAPTLS_CONTROL_BLOCK *v16; // rcx
  __int64 v17; // rdx
  unsigned int v18; // eax
  struct _PEAP_USER_PROPERTIES *v19; // rdx
  struct _PEAP_USER_PROPERTIES *v21; // [rsp+30h] [rbp-50h] BYREF
  struct IXMLDOMNode *v22; // [rsp+38h] [rbp-48h] BYREF
  struct IXMLDOMNode *v23; // [rsp+40h] [rbp-40h] BYREF
  unsigned __int16 *v24[3]; // [rsp+48h] [rbp-38h] BYREF
  unsigned __int16 *v25[4]; // [rsp+60h] [rbp-20h] BYREF

  v13 = 0;
  v21 = 0;
  v23 = 0;
  v22 = 0;
  v25[0] = L"http://www.microsoft.com/provisioning/BaseEapUserPropertiesV1";
  v25[1] = L"http://www.microsoft.com/provisioning/MsPeapUserPropertiesV1";
  v25[2] = 0;
  v24[0] = L"BaseEapUserPropertiesV1.xsd";
  v24[1] = L"MsPeapUserPropertiesV1.xsd";
  v24[2] = 0;
  v14 = SetNsAndSchema(
          a3,
          L"xmlns:baseeapuserpropertiesv1='http://www.microsoft.com/provisioning/BaseEapUserPropertiesV1' xmlns:mspeapuser"
           "propertiesv1='http://www.microsoft.com/provisioning/MsPeapUserPropertiesV1'",
          (const unsigned __int16 **)v25,
          (const unsigned __int16 **)v24);
  if ( v14 )
  {
    SingleNode = (unsigned __int16)v14;
    if ( (v14 & 0x1FFF0000) != 0x70000 )
      SingleNode = v14;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      v17 = 28;
LABEL_6:
      WPP_SF_d(*((_QWORD *)v16 + 2), v17, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, v14);
    }
  }
  else
  {
    v14 = validate(a3);
    if ( v14 )
    {
      SingleNode = (unsigned __int16)v14;
      if ( (v14 & 0x1FFF0000) != 0x70000 )
        SingleNode = v14;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        v17 = 29;
        goto LABEL_6;
      }
    }
    else
    {
      v18 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, GUID *, struct IXMLDOMNode **))a3->lpVtbl->QueryInterface)(
              a3,
              &IID_IXMLDOMNode,
              &v23);
      SingleNode = v18;
      if ( !v18 )
      {
        SingleNode = getSingleNode(v23, L"/baseeapuserpropertiesv1:Eap[baseeapuserpropertiesv1:Type=25][1]", &v22);
        if ( !SingleNode )
        {
          SingleNode = getPeapUserProperties(v22, a1, a2, a6, a4, &v21);
          if ( SingleNode )
          {
            v13 = v21;
          }
          else
          {
            v19 = v21;
            *a8 = v21;
            *a9 = *((_DWORD *)v19 + 1);
            v13 = 0;
          }
          goto LABEL_22;
        }
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
        v18 = SingleNode;
      }
      if ( (v18 & 0x1FFF0000) == 0x70000 )
        SingleNode = (unsigned __int16)SingleNode;
    }
  }
LABEL_22:
  LocalFree(v13);
  if ( SingleNode )
  {
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, SingleNode);
  }
  else if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
  }
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v22);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v23);
  return SingleNode;
}

```

## disassembly

```asm
0x18005f628  push    rbp
0x18005f62a  push    rbx
0x18005f62b  push    rsi
0x18005f62c  push    rdi
0x18005f62d  push    r13
0x18005f62f  push    r14
0x18005f631  push    r15
0x18005f633  mov     rbp, rsp
0x18005f636  sub     rsp, 80h
0x18005f63d  mov     rsi, r9
0x18005f640  mov     rbx, r8
0x18005f643  mov     r14, rdx
0x18005f646  mov     r15d, ecx
0x18005f649  xor     edi, edi
0x18005f64b  mov     [rbp+var_50], rdi
0x18005f64f  mov     [rbp+var_40], rdi
0x18005f653  mov     [rbp+var_48], rdi
0x18005f657  lea     rax, aHttpWwwMicroso_8; "http://www.microsoft.com/provisioning/B"...
0x18005f65e  mov     [rbp+var_20], rax
0x18005f662  lea     rax, aHttpWwwMicroso_5; "http://www.microsoft.com/provisioning/M"...
0x18005f669  mov     [rbp+var_18], rax
0x18005f66d  mov     [rbp+var_10], rdi
0x18005f671  lea     rax, aBaseeapuserpro_1; "BaseEapUserPropertiesV1.xsd"
0x18005f678  mov     [rbp+var_38], rax
0x18005f67c  lea     rax, aMspeapuserprop; "MsPeapUserPropertiesV1.xsd"
0x18005f683  mov     [rbp+var_30], rax
0x18005f687  mov     [rbp+var_28], rdi
0x18005f68b  lea     r9, [rbp+var_38]; unsigned __int16 **
0x18005f68f  lea     r8, [rbp+var_20]; unsigned __int16 **
0x18005f693  lea     rdx, aXmlnsBaseeapus_0; "xmlns:baseeapuserpropertiesv1='http://w"...
0x18005f69a  mov     rcx, rbx; struct IXMLDOMDocument2 *
0x18005f69d  call    ?SetNsAndSchema@@YAJPEAUIXMLDOMDocument2@@PEBGPEAPEBG2KK@Z; SetNsAndSchema(IXMLDOMDocument2 *,ushort const *,ushort const * *,ushort const * *,ulong,ulong)
0x18005f6a2  lea     r13, WPP_GLOBAL_Control
0x18005f6a9  test    eax, eax
0x18005f6ab  jz      short loc_18005F6EF
0x18005f6ad  mov     ecx, eax
0x18005f6af  and     ecx, 1FFF0000h
0x18005f6b5  cmp     ecx, 70000h
0x18005f6bb  movzx   ebx, ax
0x18005f6be  jz      short loc_18005F6C2
0x18005f6c0  mov     ebx, eax
0x18005f6c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f6c9  cmp     rcx, r13
0x18005f6cc  jz      loc_18005F7E3
0x18005f6d2  mov     edx, 1Ch
0x18005f6d7  mov     r9d, eax
0x18005f6da  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18005f6e1  mov     rcx, [rcx+10h]
0x18005f6e5  call    WPP_SF_d
0x18005f6ea  jmp     loc_18005F7E3
0x18005f6ef  mov     rcx, rbx; struct IXMLDOMDocument2 *
0x18005f6f2  call    ?validate@@YAJPEAUIXMLDOMDocument2@@@Z; validate(IXMLDOMDocument2 *)
0x18005f6f7  test    eax, eax
0x18005f6f9  jz      short loc_18005F727
0x18005f6fb  mov     ecx, eax
0x18005f6fd  and     ecx, 1FFF0000h
0x18005f703  cmp     ecx, 70000h
0x18005f709  movzx   ebx, ax
0x18005f70c  jz      short loc_18005F710
0x18005f70e  mov     ebx, eax
0x18005f710  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f717  cmp     rcx, r13
0x18005f71a  jz      loc_18005F7E3
0x18005f720  mov     edx, 1Dh
0x18005f725  jmp     short loc_18005F6D7
0x18005f727  mov     rax, [rbx]
0x18005f72a  lea     r8, [rbp+var_40]
0x18005f72e  lea     rdx, IID_IXMLDOMNode
0x18005f735  mov     rcx, rbx
0x18005f738  mov     rax, [rax]
0x18005f73b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f740  mov     ebx, eax
0x18005f742  test    eax, eax
0x18005f744  jz      short loc_18005F75E
0x18005f746  and     eax, 1FFF0000h
0x18005f74b  cmp     eax, 70000h
0x18005f750  jnz     loc_18005F7E3
0x18005f756  movzx   ebx, bx
0x18005f759  jmp     loc_18005F7E3
0x18005f75e  lea     r8, [rbp+var_48]; struct IXMLDOMNode **
0x18005f762  lea     rdx, aBaseeapuserpro_3; "/baseeapuserpropertiesv1:Eap[baseeapuse"...
0x18005f769  mov     rcx, [rbp+var_40]; struct IXMLDOMNode *
0x18005f76d  call    ?getSingleNode@@YAJPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; getSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18005f772  mov     ebx, eax
0x18005f774  test    eax, eax
0x18005f776  jz      short loc_18005F79D
0x18005f778  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f77f  cmp     rcx, r13
0x18005f782  jz      short loc_18005F799
0x18005f784  mov     edx, 1Eh
0x18005f789  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18005f790  mov     rcx, [rcx+10h]
0x18005f794  call    WPP_SF_
0x18005f799  mov     eax, ebx
0x18005f79b  jmp     short loc_18005F746
0x18005f79d  lea     rax, [rbp+var_50]
0x18005f7a1  mov     [rsp+80h+var_58], rax; struct _PEAP_USER_PROPERTIES **
0x18005f7a6  mov     [rsp+80h+var_60], rsi; struct _PEAP_CONN_PROPERTIES *
0x18005f7ab  mov     r9, [rbp+arg_28]; struct _PEAP_USER_PROPERTIES *
0x18005f7af  mov     r8, r14; unsigned __int16 *
0x18005f7b2  mov     edx, r15d; unsigned int
0x18005f7b5  mov     rcx, [rbp+var_48]; struct IXMLDOMNode *
0x18005f7b9  call    ?getPeapUserProperties@@YAKPEAUIXMLDOMNode@@KPEBGPEAU_PEAP_USER_PROPERTIES@@PEAU_PEAP_CONN_PROPERTIES@@PEAPEAU2@@Z; getPeapUserProperties(IXMLDOMNode *,ulong,ushort const *,_PEAP_USER_PROPERTIES *,_PEAP_CONN_PROPERTIES *,_PEAP_USER_PROPERTIES * *)
0x18005f7be  mov     ebx, eax
0x18005f7c0  test    eax, eax
0x18005f7c2  jnz     short loc_18005F7DF
0x18005f7c4  mov     rdx, [rbp+var_50]
0x18005f7c8  mov     rcx, [rbp+arg_38]
0x18005f7cc  mov     [rcx], rdx
0x18005f7cf  mov     edx, [rdx+4]
0x18005f7d2  mov     rcx, [rbp+arg_40]
0x18005f7d9  mov     [rcx], edx
0x18005f7db  xor     edi, edi
0x18005f7dd  jmp     short loc_18005F7E3
0x18005f7df  mov     rdi, [rbp+var_50]
0x18005f7e3  mov     rcx, rdi; hMem
0x18005f7e6  call    cs:__imp_LocalFree
0x18005f7ec  test    ebx, ebx
0x18005f7ee  jnz     short loc_18005F811
0x18005f7f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f7f7  cmp     rcx, r13
0x18005f7fa  jz      short loc_18005F836
0x18005f7fc  lea     edx, [rbx+1Fh]
0x18005f7ff  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18005f806  mov     rcx, [rcx+10h]
0x18005f80a  call    WPP_SF_
0x18005f80f  jmp     short loc_18005F836
0x18005f811  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f818  cmp     rcx, r13
0x18005f81b  jz      short loc_18005F836
0x18005f81d  mov     edx, 20h ; ' '
0x18005f822  mov     r9d, ebx
0x18005f825  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18005f82c  mov     rcx, [rcx+10h]
0x18005f830  call    WPP_SF_d
0x18005f835  nop
0x18005f836  lea     rcx, [rbp+var_48]
0x18005f83a  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18005f83f  nop
0x18005f840  lea     rcx, [rbp+var_40]
0x18005f844  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18005f849  mov     eax, ebx
0x18005f84b  add     rsp, 80h
0x18005f852  pop     r15
0x18005f854  pop     r14
0x18005f856  pop     r13
0x18005f858  pop     rdi
0x18005f859  pop     rsi
0x18005f85a  pop     rbx
0x18005f85b  pop     rbp
0x18005f85c  retn
```
