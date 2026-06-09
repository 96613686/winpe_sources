# MsChapV2CreateUserProperties(ulong,ushort const *,IXMLDOMDocument2 *,_EAPMSCHAPv2_CONN_PROPERTIES *,ulong,_EAPMSCHAPv2_USER_PROPERTIES *,ulong,_EAPMSCHAPv2_USER_PROPERTIES * *,ulong *)

- ea: `0x18001cbe4`
- end: `0x18001cf1f`
- name: `?MsChapV2CreateUserProperties@@YAKKPEBGPEAUIXMLDOMDocument2@@PEAU_EAPMSCHAPv2_CONN_PROPERTIES@@KPEAU_EAPMSCHAPv2_USER_PROPERTIES@@KPEAPEAU3@PEAK@Z`
- size: `827`
- prototype: `unsigned int __usercall@<eax>(unsigned int@<ecx>, const unsigned __int16 *@<rdx>, struct IXMLDOMDocument2 *@<r8>, struct _EAPMSCHAPv2_CONN_PROPERTIES *@<r9>, unsigned int, struct _EAPMSCHAPv2_USER_PROPERTIES *Src, unsigned int, struct _EAPMSCHAPv2_USER_PROPERTIES **, unsigned int *)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001d130`
- `0x18001d950`

## callees

- `0x180001210`
- `0x1800038d0`
- `0x180003bd0`
- `0x180006600`
- `0x180006a20`
- `0x180007060`
- `0x18000b070`
- `0x18000e500`
- `0x18001cbe4`
- `0x18001d330`
- `0x180025efc`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ce90`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ce9e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ce90`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ce9e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ce22`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ce22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ce47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ce47`

## string_xrefs

- `0x18001cc22`: `http://www.microsoft.com/provisioning/BaseEapUserPropertiesV1`
- `0x18001cc2d`: `http://www.microsoft.com/provisioning/MsChapV2UserPropertiesV1`
- `0x18001cc5e`: `xmlns:baseeapuserpropertiesv1='http://www.microsoft.com/provisioning/BaseEapUserPropertiesV1' xmlns:mschapv2userpropertiesv1='http://www.microsoft.com/provisioning/MsChapV2UserPropertiesV1'`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MsChapV2CreateUserProperties(
        unsigned int a1,
        const unsigned __int16 *a2,
        struct IXMLDOMDocument2 *a3,
        struct _EAPMSCHAPv2_CONN_PROPERTIES *a4,
        unsigned int a5,
        struct _EAPMSCHAPv2_USER_PROPERTIES *Src,
        unsigned int a7,
        struct _EAPMSCHAPv2_USER_PROPERTIES **a8,
        unsigned int *a9)
{
  struct _EAPMSCHAPv2_USER_PROPERTIES *v12; // rdi
  struct _EAPMSCHAPv2_CONN_PROPERTIES *v13; // rsi
  unsigned int SingleNode; // ebx
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // edx
  const unsigned __int16 *v19; // r9
  unsigned int v20; // eax
  unsigned int *v21; // r14
  struct _EAPMSCHAPv2_USER_PROPERTIES *v22; // rax
  DWORD LastError; // eax
  struct _EAPMSCHAPv2_USER_PROPERTIES *v25; // [rsp+20h] [rbp-60h]
  struct IXMLDOMNode *v26; // [rsp+40h] [rbp-40h] BYREF
  struct IXMLDOMNode *v27; // [rsp+48h] [rbp-38h] BYREF
  unsigned __int16 *v28[3]; // [rsp+50h] [rbp-30h] BYREF
  unsigned __int16 *v29[3]; // [rsp+68h] [rbp-18h] BYREF
  struct _EAPMSCHAPv2_CONN_PROPERTIES *v30; // [rsp+B8h] [rbp+38h] BYREF

  v12 = 0;
  Src = 0;
  v13 = 0;
  v30 = 0;
  v27 = 0;
  v26 = 0;
  v29[0] = L"http://www.microsoft.com/provisioning/BaseEapUserPropertiesV1";
  v29[1] = L"http://www.microsoft.com/provisioning/MsChapV2UserPropertiesV1";
  v29[2] = 0;
  v28[0] = L"BaseEapUserPropertiesV1.xsd";
  v28[1] = L"MsChapV2UserPropertiesV1.xsd";
  v28[2] = 0;
  SingleNode = SetNsAndSchema(
                 a3,
                 L"xmlns:baseeapuserpropertiesv1='http://www.microsoft.com/provisioning/BaseEapUserPropertiesV1' xmlns:msc"
                  "hapv2userpropertiesv1='http://www.microsoft.com/provisioning/MsChapV2UserPropertiesV1'",
                 (const unsigned __int16 **)v29,
                 (const unsigned __int16 **)v28);
  if ( SingleNode )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_47d2ae5abdbe322473422603828ba620_Traceguids, SingleNode);
    v15 = SingleNode;
    goto LABEL_5;
  }
  v16 = validate(a3);
  if ( v16 )
  {
    SingleNode = (unsigned __int16)v16;
    if ( (v16 & 0x1FFF0000) != 0x70000 )
      SingleNode = v16;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_47d2ae5abdbe322473422603828ba620_Traceguids, v16);
  }
  else
  {
    v15 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, GUID *, struct IXMLDOMNode **, _QWORD))a3->lpVtbl->QueryInterface)(
            a3,
            &IID_IXMLDOMNode,
            &v27,
            0);
    SingleNode = v15;
    if ( v15 )
    {
LABEL_5:
      if ( (v15 & 0x1FFF0000) == 0x70000 )
        SingleNode = (unsigned __int16)SingleNode;
      goto LABEL_30;
    }
    SingleNode = getSingleNode(v27, L"/baseeapuserpropertiesv1:Eap[baseeapuserpropertiesv1:Type=26][1]", &v26);
    if ( SingleNode )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_47d2ae5abdbe322473422603828ba620_Traceguids);
      if ( (SingleNode & 0x1FFF0000) == 0x70000 )
        SingleNode = (unsigned __int16)SingleNode;
    }
    else
    {
      v17 = ReadConnectionData(a1, a4, a5, &v30);
      SingleNode = v17;
      if ( v17 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_47d2ae5abdbe322473422603828ba620_Traceguids, v17);
        v13 = v30;
      }
      else
      {
        v13 = v30;
        SingleNode = getMsChapV2UserProperties(v26, v18, a1, v19, v25, v30, &Src);
        v12 = Src;
        if ( !SingleNode )
        {
          v20 = MschapV2UserPropBuffSize(Src);
          if ( v20 )
          {
            v21 = a9;
            *a9 = v20;
            v22 = (struct _EAPMSCHAPv2_USER_PROPERTIES *)LocalAlloc(0x40u, v20);
            *a8 = v22;
            if ( v22 )
            {
              memcpy_0(v22, v12, *v21);
            }
            else
            {
              *v21 = 0;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
              {
                LastError = GetLastError();
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  25,
                  WPP_47d2ae5abdbe322473422603828ba620_Traceguids,
                  LastError);
              }
              SingleNode = 14;
            }
          }
          else
          {
            SingleNode = 534;
          }
        }
      }
    }
  }
LABEL_30:
  if ( v13 )
    LocalFree(v13);
  if ( v12 )
    LocalFree(v12);
  if ( SingleNode )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_47d2ae5abdbe322473422603828ba620_Traceguids, SingleNode);
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_47d2ae5abdbe322473422603828ba620_Traceguids);
  }
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v26);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v27);
  return SingleNode;
}

```

## disassembly

```asm
0x18001cbe4  mov     [rsp-28h+arg_0], rbx
0x18001cbe9  mov     [rsp-28h+arg_10], rsi
0x18001cbee  mov     [rsp-28h+arg_8], rdx
0x18001cbf3  push    rbp
0x18001cbf4  push    rdi
0x18001cbf5  push    r12
0x18001cbf7  push    r14
0x18001cbf9  push    r15
0x18001cbfb  mov     rbp, rsp
0x18001cbfe  sub     rsp, 80h
0x18001cc05  mov     r12, r9
0x18001cc08  mov     r14, r8
0x18001cc0b  mov     r15d, ecx
0x18001cc0e  xor     edi, edi
0x18001cc10  mov     [rbp+Src], rdi
0x18001cc14  xor     esi, esi
0x18001cc16  mov     [rbp+arg_8], rsi
0x18001cc1a  mov     [rbp+var_38], rsi
0x18001cc1e  mov     [rbp+var_40], rsi
0x18001cc22  lea     rax, aHttpWwwMicroso_2; "http://www.microsoft.com/provisioning/B"...
0x18001cc29  mov     [rbp+var_18], rax
0x18001cc2d  lea     rax, aHttpWwwMicroso_3; "http://www.microsoft.com/provisioning/M"...
0x18001cc34  mov     [rbp+var_10], rax
0x18001cc38  mov     [rbp+var_8], rsi
0x18001cc3c  lea     rax, aBaseeapuserpro; "BaseEapUserPropertiesV1.xsd"
0x18001cc43  mov     [rbp+var_30], rax
0x18001cc47  lea     rax, aMschapv2userpr_0; "MsChapV2UserPropertiesV1.xsd"
0x18001cc4e  mov     [rbp+var_28], rax
0x18001cc52  mov     [rbp+var_20], rsi
0x18001cc56  lea     r9, [rbp+var_30]; unsigned __int16 **
0x18001cc5a  lea     r8, [rbp+var_18]; unsigned __int16 **
0x18001cc5e  lea     rdx, aXmlnsBaseeapus; "xmlns:baseeapuserpropertiesv1='http://w"...
0x18001cc65  mov     rcx, r14; struct IXMLDOMDocument2 *
0x18001cc68  call    ?SetNsAndSchema@@YAJPEAUIXMLDOMDocument2@@PEBGPEAPEBG2@Z; SetNsAndSchema(IXMLDOMDocument2 *,ushort const *,ushort const * *,ushort const * *)
0x18001cc6d  mov     ebx, eax
0x18001cc6f  lea     rax, WPP_GLOBAL_Control
0x18001cc76  test    ebx, ebx
0x18001cc78  jz      short loc_18001CCB6
0x18001cc7a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cc81  cmp     rcx, rax
0x18001cc84  jz      short loc_18001CC9C
0x18001cc86  lea     edx, [rdi+15h]
0x18001cc89  mov     r9d, ebx
0x18001cc8c  lea     r8, WPP_47d2ae5abdbe322473422603828ba620_Traceguids
0x18001cc93  mov     rcx, [rcx+10h]
0x18001cc97  call    WPP_SF_d
0x18001cc9c  mov     eax, ebx
0x18001cc9e  and     eax, 1FFF0000h
0x18001cca3  cmp     eax, 70000h
0x18001cca8  jnz     loc_18001CE81
0x18001ccae  movzx   ebx, bx
0x18001ccb1  jmp     loc_18001CE81
0x18001ccb6  mov     rcx, r14; struct IXMLDOMDocument2 *
0x18001ccb9  call    ?validate@@YAJPEAUIXMLDOMDocument2@@@Z; validate(IXMLDOMDocument2 *)
0x18001ccbe  mov     r9d, eax
0x18001ccc1  test    eax, eax
0x18001ccc3  jz      short loc_18001CD09
0x18001ccc5  and     eax, 1FFF0000h
0x18001ccca  cmp     eax, 70000h
0x18001cccf  movzx   ebx, r9w
0x18001ccd3  jz      short loc_18001CCD8
0x18001ccd5  mov     ebx, r9d
0x18001ccd8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ccdf  lea     r14, WPP_GLOBAL_Control
0x18001cce6  cmp     rcx, r14
0x18001cce9  jz      loc_18001CE88
0x18001ccef  mov     edx, 16h
0x18001ccf4  lea     r8, WPP_47d2ae5abdbe322473422603828ba620_Traceguids
0x18001ccfb  mov     rcx, [rcx+10h]
0x18001ccff  call    WPP_SF_d
0x18001cd04  jmp     loc_18001CE88
0x18001cd09  mov     rax, [r14]
0x18001cd0c  lea     r8, [rbp+var_38]
0x18001cd10  lea     rdx, IID_IXMLDOMNode
0x18001cd17  mov     rcx, r14
0x18001cd1a  mov     rax, [rax]
0x18001cd1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd22  mov     ebx, eax
0x18001cd24  test    eax, eax
0x18001cd26  jnz     loc_18001CC9E
0x18001cd2c  lea     r8, [rbp+var_40]; struct IXMLDOMNode **
0x18001cd30  lea     rdx, aBaseeapuserpro_0; "/baseeapuserpropertiesv1:Eap[baseeapuse"...
0x18001cd37  mov     rcx, [rbp+var_38]; struct IXMLDOMNode *
0x18001cd3b  call    ?getSingleNode@@YAJPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; getSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18001cd40  mov     ebx, eax
0x18001cd42  test    eax, eax
0x18001cd44  jz      short loc_18001CD88
0x18001cd46  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cd4d  lea     r14, WPP_GLOBAL_Control
0x18001cd54  cmp     rcx, r14
0x18001cd57  jz      short loc_18001CD6E
0x18001cd59  mov     edx, 17h
0x18001cd5e  lea     r8, WPP_47d2ae5abdbe322473422603828ba620_Traceguids
0x18001cd65  mov     rcx, [rcx+10h]
0x18001cd69  call    WPP_SF_
0x18001cd6e  mov     eax, ebx
0x18001cd70  and     eax, 1FFF0000h
0x18001cd75  cmp     eax, 70000h
0x18001cd7a  jnz     loc_18001CE88
0x18001cd80  movzx   ebx, bx
0x18001cd83  jmp     loc_18001CE88
0x18001cd88  lea     r9, [rbp+arg_8]
0x18001cd8c  mov     r8d, [rbp+arg_20]
0x18001cd90  mov     rdx, r12
0x18001cd93  mov     ecx, r15d
0x18001cd96  call    ReadConnectionData
0x18001cd9b  mov     ebx, eax
0x18001cd9d  test    eax, eax
0x18001cd9f  jz      short loc_18001CDD5
0x18001cda1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cda8  lea     r14, WPP_GLOBAL_Control
0x18001cdaf  cmp     rcx, r14
0x18001cdb2  jz      short loc_18001CDCC
0x18001cdb4  mov     edx, 18h
0x18001cdb9  mov     r9d, eax
0x18001cdbc  lea     r8, WPP_47d2ae5abdbe322473422603828ba620_Traceguids
0x18001cdc3  mov     rcx, [rcx+10h]
0x18001cdc7  call    WPP_SF_d
0x18001cdcc  mov     rsi, [rbp+arg_8]
0x18001cdd0  jmp     loc_18001CE88
0x18001cdd5  lea     rax, [rbp+Src]
0x18001cdd9  mov     [rsp+80h+var_50], rax; struct _EAPMSCHAPv2_USER_PROPERTIES **
0x18001cdde  mov     rsi, [rbp+arg_8]
0x18001cde2  mov     [rsp+80h+var_58], rsi; struct _EAPMSCHAPv2_CONN_PROPERTIES *
0x18001cde7  mov     r8d, r15d; unsigned int
0x18001cdea  mov     rcx, [rbp+var_40]; struct IXMLDOMNode *
0x18001cdee  call    ?getMsChapV2UserProperties@@YAKPEAUIXMLDOMNode@@KKPEBGPEAU_EAPMSCHAPv2_USER_PROPERTIES@@PEAU_EAPMSCHAPv2_CONN_PROPERTIES@@PEAPEAU2@@Z; getMsChapV2UserProperties(IXMLDOMNode *,ulong,ulong,ushort const *,_EAPMSCHAPv2_USER_PROPERTIES *,_EAPMSCHAPv2_CONN_PROPERTIES *,_EAPMSCHAPv2_USER_PROPERTIES * *)
0x18001cdf3  mov     ebx, eax
0x18001cdf5  mov     rdi, [rbp+Src]
0x18001cdf9  test    eax, eax
0x18001cdfb  jnz     loc_18001CE81
0x18001ce01  mov     rcx, rdi
0x18001ce04  call    MschapV2UserPropBuffSize
0x18001ce09  test    eax, eax
0x18001ce0b  jnz     short loc_18001CE14
0x18001ce0d  mov     ebx, 216h
0x18001ce12  jmp     short loc_18001CE81
0x18001ce14  mov     r14, [rbp+arg_40]
0x18001ce18  mov     [r14], eax
0x18001ce1b  mov     edx, eax; uBytes
0x18001ce1d  mov     ecx, 40h ; '@'; uFlags
0x18001ce22  call    cs:__imp_LocalAlloc
0x18001ce28  mov     rcx, [rbp+arg_38]
0x18001ce2c  mov     [rcx], rax
0x18001ce2f  test    rax, rax
0x18001ce32  jnz     short loc_18001CE73
0x18001ce34  mov     [r14], eax
0x18001ce37  lea     r14, WPP_GLOBAL_Control
0x18001ce3e  cmp     cs:WPP_GLOBAL_Control, r14
0x18001ce45  jz      short loc_18001CE6C
0x18001ce47  call    cs:__imp_GetLastError
0x18001ce4d  mov     edx, 19h
0x18001ce52  mov     r9d, eax
0x18001ce55  lea     r8, WPP_47d2ae5abdbe322473422603828ba620_Traceguids
0x18001ce5c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ce63  mov     rcx, [rcx+10h]
0x18001ce67  call    WPP_SF_d
0x18001ce6c  mov     ebx, 0Eh
0x18001ce71  jmp     short loc_18001CE88
0x18001ce73  mov     r8d, [r14]; Size
0x18001ce76  mov     rdx, rdi; Src
0x18001ce79  mov     rcx, rax; void *
0x18001ce7c  call    memcpy_0
0x18001ce81  lea     r14, WPP_GLOBAL_Control
0x18001ce88  test    rsi, rsi
0x18001ce8b  jz      short loc_18001CE96
0x18001ce8d  mov     rcx, rsi; hMem
0x18001ce90  call    cs:__imp_LocalFree
0x18001ce96  test    rdi, rdi
0x18001ce99  jz      short loc_18001CEA4
0x18001ce9b  mov     rcx, rdi; hMem
0x18001ce9e  call    cs:__imp_LocalFree
0x18001cea4  test    ebx, ebx
0x18001cea6  jnz     short loc_18001CEC9
0x18001cea8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ceaf  cmp     rcx, r14
0x18001ceb2  jz      short loc_18001CEEE
0x18001ceb4  lea     edx, [rbx+1Ah]
0x18001ceb7  lea     r8, WPP_47d2ae5abdbe322473422603828ba620_Traceguids
0x18001cebe  mov     rcx, [rcx+10h]
0x18001cec2  call    WPP_SF_
0x18001cec7  jmp     short loc_18001CEEE
0x18001cec9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ced0  cmp     rcx, r14
0x18001ced3  jz      short loc_18001CEEE
0x18001ced5  mov     edx, 1Bh
0x18001ceda  mov     r9d, ebx
0x18001cedd  lea     r8, WPP_47d2ae5abdbe322473422603828ba620_Traceguids
0x18001cee4  mov     rcx, [rcx+10h]
0x18001cee8  call    WPP_SF_d
0x18001ceed  nop
0x18001ceee  lea     rcx, [rbp+var_40]
0x18001cef2  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18001cef7  nop
0x18001cef8  lea     rcx, [rbp+var_38]
0x18001cefc  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18001cf01  mov     eax, ebx
0x18001cf03  lea     r11, [rsp+80h+var_s0]
0x18001cf0b  mov     rbx, [r11+30h]
0x18001cf0f  mov     rsi, [r11+40h]
0x18001cf13  mov     rsp, r11
0x18001cf16  pop     r15
0x18001cf18  pop     r14
0x18001cf1a  pop     r12
0x18001cf1c  pop     rdi
0x18001cf1d  pop     rbp
0x18001cf1e  retn
```
