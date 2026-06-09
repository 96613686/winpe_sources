# PeapCreateUserProperties(ulong,ushort const *,IXMLDOMDocument2 *,_PEAP_CONN_PROPERTIES *,ulong,_PEAP_USER_PROPERTIES *,ulong,_PEAP_USER_PROPERTIES * *,ulong *)

- ea: `0x180062e58`
- end: `0x180063094`
- name: `?PeapCreateUserProperties@@YAKKPEBGPEAUIXMLDOMDocument2@@PEAU_PEAP_CONN_PROPERTIES@@KPEAU_PEAP_USER_PROPERTIES@@KPEAPEAU3@PEAK@Z`
- size: `572`
- prototype: `unsigned int __fastcall(unsigned int, const unsigned __int16 *, struct IXMLDOMDocument2 *, struct _PEAP_CONN_PROPERTIES *, unsigned int, struct _PEAP_USER_PROPERTIES *, unsigned int, struct _PEAP_USER_PROPERTIES **, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
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
- `0x180062e58`
- `0x180063df0`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180063016`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180063016`

## string_xrefs

- `0x180062e87`: `http://www.microsoft.com/provisioning/BaseEapUserPropertiesV1`
- `0x180062e92`: `http://www.microsoft.com/provisioning/MsPeapUserPropertiesV1`
- `0x180062ec3`: `xmlns:baseeapuserpropertiesv1='http://www.microsoft.com/provisioning/BaseEapUserPropertiesV1' xmlns:mspeapuserpropertiesv1='http://www.microsoft.com/provisioning/MsPeapUserPropertiesV1'`

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
0x180062e58  push    rbp
0x180062e5a  push    rbx
0x180062e5b  push    rsi
0x180062e5c  push    rdi
0x180062e5d  push    r13
0x180062e5f  push    r14
0x180062e61  push    r15
0x180062e63  mov     rbp, rsp
0x180062e66  sub     rsp, 80h
0x180062e6d  mov     rsi, r9
0x180062e70  mov     rbx, r8
0x180062e73  mov     r14, rdx
0x180062e76  mov     r15d, ecx
0x180062e79  xor     edi, edi
0x180062e7b  mov     [rbp+var_50], rdi
0x180062e7f  mov     [rbp+var_40], rdi
0x180062e83  mov     [rbp+var_48], rdi
0x180062e87  lea     rax, aHttpWwwMicroso_8; "http://www.microsoft.com/provisioning/B"...
0x180062e8e  mov     [rbp+var_20], rax
0x180062e92  lea     rax, aHttpWwwMicroso_5; "http://www.microsoft.com/provisioning/M"...
0x180062e99  mov     [rbp+var_18], rax
0x180062e9d  mov     [rbp+var_10], rdi
0x180062ea1  lea     rax, aBaseeapuserpro_1; "BaseEapUserPropertiesV1.xsd"
0x180062ea8  mov     [rbp+var_38], rax
0x180062eac  lea     rax, aMspeapuserprop; "MsPeapUserPropertiesV1.xsd"
0x180062eb3  mov     [rbp+var_30], rax
0x180062eb7  mov     [rbp+var_28], rdi
0x180062ebb  lea     r9, [rbp+var_38]; unsigned __int16 **
0x180062ebf  lea     r8, [rbp+var_20]; unsigned __int16 **
0x180062ec3  lea     rdx, aXmlnsBaseeapus_0; "xmlns:baseeapuserpropertiesv1='http://w"...
0x180062eca  mov     rcx, rbx; struct IXMLDOMDocument2 *
0x180062ecd  call    ?SetNsAndSchema@@YAJPEAUIXMLDOMDocument2@@PEBGPEAPEBG2KK@Z; SetNsAndSchema(IXMLDOMDocument2 *,ushort const *,ushort const * *,ushort const * *,ulong,ulong)
0x180062ed2  lea     r13, WPP_GLOBAL_Control
0x180062ed9  test    eax, eax
0x180062edb  jz      short loc_180062F1F
0x180062edd  mov     ecx, eax
0x180062edf  and     ecx, 1FFF0000h
0x180062ee5  cmp     ecx, 70000h
0x180062eeb  movzx   ebx, ax
0x180062eee  jz      short loc_180062EF2
0x180062ef0  mov     ebx, eax
0x180062ef2  mov     rcx, cs:WPP_GLOBAL_Control
0x180062ef9  cmp     rcx, r13
0x180062efc  jz      loc_180063013
0x180062f02  mov     edx, 1Ch
0x180062f07  mov     r9d, eax
0x180062f0a  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180062f11  mov     rcx, [rcx+10h]
0x180062f15  call    WPP_SF_d
0x180062f1a  jmp     loc_180063013
0x180062f1f  mov     rcx, rbx; struct IXMLDOMDocument2 *
0x180062f22  call    ?validate@@YAJPEAUIXMLDOMDocument2@@@Z; validate(IXMLDOMDocument2 *)
0x180062f27  test    eax, eax
0x180062f29  jz      short loc_180062F57
0x180062f2b  mov     ecx, eax
0x180062f2d  and     ecx, 1FFF0000h
0x180062f33  cmp     ecx, 70000h
0x180062f39  movzx   ebx, ax
0x180062f3c  jz      short loc_180062F40
0x180062f3e  mov     ebx, eax
0x180062f40  mov     rcx, cs:WPP_GLOBAL_Control
0x180062f47  cmp     rcx, r13
0x180062f4a  jz      loc_180063013
0x180062f50  mov     edx, 1Dh
0x180062f55  jmp     short loc_180062F07
0x180062f57  mov     rax, [rbx]
0x180062f5a  lea     r8, [rbp+var_40]
0x180062f5e  lea     rdx, IID_IXMLDOMNode
0x180062f65  mov     rcx, rbx
0x180062f68  mov     rax, [rax]
0x180062f6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062f70  mov     ebx, eax
0x180062f72  test    eax, eax
0x180062f74  jz      short loc_180062F8E
0x180062f76  and     eax, 1FFF0000h
0x180062f7b  cmp     eax, 70000h
0x180062f80  jnz     loc_180063013
0x180062f86  movzx   ebx, bx
0x180062f89  jmp     loc_180063013
0x180062f8e  lea     r8, [rbp+var_48]; struct IXMLDOMNode **
0x180062f92  lea     rdx, aBaseeapuserpro_3; "/baseeapuserpropertiesv1:Eap[baseeapuse"...
0x180062f99  mov     rcx, [rbp+var_40]; struct IXMLDOMNode *
0x180062f9d  call    ?getSingleNode@@YAJPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; getSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x180062fa2  mov     ebx, eax
0x180062fa4  test    eax, eax
0x180062fa6  jz      short loc_180062FCD
0x180062fa8  mov     rcx, cs:WPP_GLOBAL_Control
0x180062faf  cmp     rcx, r13
0x180062fb2  jz      short loc_180062FC9
0x180062fb4  mov     edx, 1Eh
0x180062fb9  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180062fc0  mov     rcx, [rcx+10h]
0x180062fc4  call    WPP_SF_
0x180062fc9  mov     eax, ebx
0x180062fcb  jmp     short loc_180062F76
0x180062fcd  lea     rax, [rbp+var_50]
0x180062fd1  mov     [rsp+80h+var_58], rax; struct _PEAP_USER_PROPERTIES **
0x180062fd6  mov     [rsp+80h+var_60], rsi; struct _PEAP_CONN_PROPERTIES *
0x180062fdb  mov     r9, [rbp+arg_28]; struct _PEAP_USER_PROPERTIES *
0x180062fdf  mov     r8, r14; unsigned __int16 *
0x180062fe2  mov     edx, r15d; unsigned int
0x180062fe5  mov     rcx, [rbp+var_48]; struct IXMLDOMNode *
0x180062fe9  call    ?getPeapUserProperties@@YAKPEAUIXMLDOMNode@@KPEBGPEAU_PEAP_USER_PROPERTIES@@PEAU_PEAP_CONN_PROPERTIES@@PEAPEAU2@@Z; getPeapUserProperties(IXMLDOMNode *,ulong,ushort const *,_PEAP_USER_PROPERTIES *,_PEAP_CONN_PROPERTIES *,_PEAP_USER_PROPERTIES * *)
0x180062fee  mov     ebx, eax
0x180062ff0  test    eax, eax
0x180062ff2  jnz     short loc_18006300F
0x180062ff4  mov     rdx, [rbp+var_50]
0x180062ff8  mov     rcx, [rbp+arg_38]
0x180062ffc  mov     [rcx], rdx
0x180062fff  mov     edx, [rdx+4]
0x180063002  mov     rcx, [rbp+arg_40]
0x180063009  mov     [rcx], edx
0x18006300b  xor     edi, edi
0x18006300d  jmp     short loc_180063013
0x18006300f  mov     rdi, [rbp+var_50]
0x180063013  mov     rcx, rdi; hMem
0x180063016  call    cs:__imp_LocalFree
0x18006301d  nop     dword ptr [rax+rax+00h]
0x180063022  test    ebx, ebx
0x180063024  jnz     short loc_180063047
0x180063026  mov     rcx, cs:WPP_GLOBAL_Control
0x18006302d  cmp     rcx, r13
0x180063030  jz      short loc_18006306C
0x180063032  lea     edx, [rbx+1Fh]
0x180063035  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18006303c  mov     rcx, [rcx+10h]
0x180063040  call    WPP_SF_
0x180063045  jmp     short loc_18006306C
0x180063047  mov     rcx, cs:WPP_GLOBAL_Control
0x18006304e  cmp     rcx, r13
0x180063051  jz      short loc_18006306C
0x180063053  mov     edx, 20h ; ' '
0x180063058  mov     r9d, ebx
0x18006305b  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180063062  mov     rcx, [rcx+10h]
0x180063066  call    WPP_SF_d
0x18006306b  nop
0x18006306c  lea     rcx, [rbp+var_48]
0x180063070  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180063075  nop
0x180063076  lea     rcx, [rbp+var_40]
0x18006307a  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18006307f  mov     eax, ebx
0x180063081  add     rsp, 80h
0x180063088  pop     r15
0x18006308a  pop     r14
0x18006308c  pop     r13
0x18006308e  pop     rdi
0x18006308f  pop     rsi
0x180063090  pop     rbx
0x180063091  pop     rbp
0x180063092  retn
```
