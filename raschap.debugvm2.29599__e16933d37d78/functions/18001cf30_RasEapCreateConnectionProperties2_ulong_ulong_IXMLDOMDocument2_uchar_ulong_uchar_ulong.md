# RasEapCreateConnectionProperties2(ulong,ulong,IXMLDOMDocument2 *,uchar *,ulong,uchar * *,ulong *)

- ea: `0x18001cf30`
- end: `0x18001d127`
- name: `?RasEapCreateConnectionProperties2@@YAKKKPEAUIXMLDOMDocument2@@PEAEKPEAPEAEPEAK@Z`
- size: `503`
- prototype: `unsigned int(unsigned int, unsigned int, struct IXMLDOMDocument2 *, unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003ad0`
- `0x180003bd0`
- `0x180004690`
- `0x180005df0`
- `0x18000e500`
- `0x18001227c`
- `0x18001256c`
- `0x18001cf30`
- `0x180027010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001d05f`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d0a7`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d05f`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d0a7`
- `OLEAUT32!__imp_VariantClear` at `0x18001d06a`
- `OLEAUT32!__imp_VariantClear` at `0x18001d06a`

## string_xrefs

- `0x18001d013`: `xmlns:eapconnectionpropertiesv1='http://www.microsoft.com/provisioning/EapConnectionPropertiesV1' xmlns:baseeapconnectionpropertiesv1='http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1'`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall RasEapCreateConnectionProperties2(
        unsigned int a1,
        char a2,
        struct IXMLDOMDocument2 *a3,
        struct _EAPMSCHAPv2_CONN_PROPERTIES *a4,
        unsigned int a5,
        struct _EAPMSCHAPv2_CONN_PROPERTIES **a6,
        unsigned int *a7)
{
  _QWORD *v11; // rcx
  unsigned int ConnectionProperties; // ebx
  HRESULT (__stdcall *setProperty)(IXMLDOMDocument2 *, BSTR, VARIANT); // rbx
  __int128 v14; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  _QWORD *v16; // rax
  HRESULT (__stdcall *selectSingleNode)(IXMLDOMDocument2 *, BSTR, IXMLDOMNode **); // rbx
  _QWORD *v18; // rax
  struct IXMLDOMDocument2 *v20; // [rsp+38h] [rbp-61h] BYREF
  __int64 v21; // [rsp+40h] [rbp-59h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-51h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-49h] BYREF
  __int128 v24; // [rsp+68h] [rbp-31h] BYREF
  IRecordInfo *v25; // [rsp+78h] [rbp-21h]

  v21 = 0;
  v20 = 0;
  DebuggingInit(1);
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_47d2ae5abdbe322473422603828ba620_Traceguids, a1);
    v11 = WPP_GLOBAL_Control;
  }
  if ( a1 == 26 )
  {
    if ( a6 && a7 && a3 )
    {
      *a6 = 0;
      *a7 = 0;
      setProperty = a3->lpVtbl->setProperty;
      pvarg.vt = 0;
      ATL::CComVariant::operator=(
        &pvarg,
        L"xmlns:eapconnectionpropertiesv1='http://www.microsoft.com/provisioning/EapConnectionPropertiesV1' xmlns:baseeapc"
         "onnectionpropertiesv1='http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1'");
      v14 = *(_OWORD *)&pvarg.vt;
      pRecInfo = pvarg.pRecInfo;
      v16 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"SelectionNamespaces");
      v24 = v14;
      v25 = pRecInfo;
      ConnectionProperties = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, _QWORD, __int128 *))setProperty)(
                               a3,
                               *v16,
                               &v24);
      SysFreeString(bstrString);
      VariantClear(&pvarg);
      if ( !ConnectionProperties )
      {
        selectSingleNode = a3->lpVtbl->selectSingleNode;
        v18 = (_QWORD *)ATL::CComBSTR::CComBSTR(
                          (ATL::CComBSTR *)&bstrString,
                          L"//eapconnectionpropertiesv1:Connections/eapconnectionpropertiesv1:Connection[1]/baseeapconnect"
                           "ionpropertiesv1:Eap");
        ConnectionProperties = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, _QWORD, __int64 *))selectSingleNode)(
                                 a3,
                                 *v18,
                                 &v21);
        SysFreeString(bstrString);
        if ( !ConnectionProperties )
        {
          ConnectionProperties = CopyXmlDoc(v21, (LPVOID *)&v20);
          if ( !ConnectionProperties )
            ConnectionProperties = MsChapV2CreateConnectionProperties(a2, v20, a4, a5, a6, a7);
        }
      }
    }
    else
    {
      ConnectionProperties = 160;
    }
  }
  else
  {
    if ( v11 != &WPP_GLOBAL_Control )
      WPP_SF_d(v11[2], 39, WPP_47d2ae5abdbe322473422603828ba620_Traceguids, a1);
    ConnectionProperties = 50;
  }
  DebuggingInit(0);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v20);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v21);
  return ConnectionProperties;
}

```

## disassembly

```asm
0x18001cf30  mov     rax, rsp
0x18001cf33  push    rbp
0x18001cf34  push    rbx
0x18001cf35  push    rsi
0x18001cf36  push    rdi
0x18001cf37  push    r12
0x18001cf39  push    r14
0x18001cf3b  push    r15
0x18001cf3d  lea     rbp, [rax-47h]
0x18001cf41  sub     rsp, 0A0h
0x18001cf48  movaps  xmmword ptr [rax-48h], xmm6
0x18001cf4c  movaps  xmmword ptr [rax-58h], xmm7
0x18001cf50  mov     r15, r9
0x18001cf53  mov     r14, r8
0x18001cf56  mov     r12d, edx
0x18001cf59  mov     ebx, ecx
0x18001cf5b  mov     [rbp+3Fh+var_98], 0
0x18001cf63  mov     [rbp+3Fh+var_A0], 0
0x18001cf6b  mov     ecx, 1
0x18001cf70  call    DebuggingInit
0x18001cf75  lea     rdi, WPP_GLOBAL_Control
0x18001cf7c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cf83  cmp     rcx, rdi
0x18001cf86  jz      short loc_18001CFA7
0x18001cf88  mov     edx, 26h ; '&'
0x18001cf8d  mov     r9d, ebx
0x18001cf90  lea     r8, WPP_47d2ae5abdbe322473422603828ba620_Traceguids
0x18001cf97  mov     rcx, [rcx+10h]
0x18001cf9b  call    WPP_SF_d
0x18001cfa0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cfa7  cmp     ebx, 1Ah
0x18001cfaa  jz      short loc_18001CFD3
0x18001cfac  cmp     rcx, rdi
0x18001cfaf  jz      short loc_18001CFC9
0x18001cfb1  mov     edx, 27h ; '''
0x18001cfb6  mov     r9d, ebx
0x18001cfb9  lea     r8, WPP_47d2ae5abdbe322473422603828ba620_Traceguids
0x18001cfc0  mov     rcx, [rcx+10h]
0x18001cfc4  call    WPP_SF_d
0x18001cfc9  mov     ebx, 32h ; '2'
0x18001cfce  jmp     loc_18001D0EA
0x18001cfd3  mov     rdi, [rbp+3Fh+arg_28]
0x18001cfd7  test    rdi, rdi
0x18001cfda  jz      loc_18001D0E5
0x18001cfe0  mov     rsi, [rbp+3Fh+arg_30]
0x18001cfe4  test    rsi, rsi
0x18001cfe7  jz      loc_18001D0E5
0x18001cfed  test    r14, r14
0x18001cff0  jz      loc_18001D0E5
0x18001cff6  mov     qword ptr [rdi], 0
0x18001cffd  mov     dword ptr [rsi], 0
0x18001d003  mov     rax, [r14]
0x18001d006  mov     rbx, [rax+280h]
0x18001d00d  xor     eax, eax
0x18001d00f  mov     word ptr [rbp+3Fh+pvarg], ax
0x18001d013  lea     rdx, aXmlnsEapconnec; "xmlns:eapconnectionpropertiesv1='http:/"...
0x18001d01a  lea     rcx, [rbp+3Fh+pvarg]
0x18001d01e  call    ??4CComVariant@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComVariant::operator=(ushort const *)
0x18001d023  nop
0x18001d024  movups  xmm6, xmmword ptr [rbp+3Fh+pvarg]
0x18001d028  movsd   xmm7, qword ptr [rbp+3Fh+pvarg+10h]
0x18001d02d  lea     rdx, aSelectionnames; "SelectionNamespaces"
0x18001d034  lea     rcx, [rbp+3Fh+bstrString]; this
0x18001d038  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18001d03d  nop
0x18001d03e  movaps  [rbp+3Fh+var_70], xmm6
0x18001d042  movsd   [rbp+3Fh+var_60], xmm7
0x18001d047  lea     r8, [rbp+3Fh+var_70]
0x18001d04b  mov     rdx, [rax]
0x18001d04e  mov     rcx, r14
0x18001d051  mov     rax, rbx
0x18001d054  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d059  mov     ebx, eax
0x18001d05b  mov     rcx, [rbp+3Fh+bstrString]; bstrString
0x18001d05f  call    cs:__imp_SysFreeString
0x18001d065  nop
0x18001d066  lea     rcx, [rbp+3Fh+pvarg]; pvarg
0x18001d06a  call    cs:__imp_VariantClear
0x18001d070  test    ebx, ebx
0x18001d072  jnz     short loc_18001D0EA
0x18001d074  mov     rax, [r14]
0x18001d077  mov     rbx, [rax+128h]
0x18001d07e  lea     rdx, aEapconnectionp; "//eapconnectionpropertiesv1:Connections"...
0x18001d085  lea     rcx, [rbp+3Fh+bstrString]; this
0x18001d089  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18001d08e  nop
0x18001d08f  lea     r8, [rbp+3Fh+var_98]
0x18001d093  mov     rdx, [rax]
0x18001d096  mov     rcx, r14
0x18001d099  mov     rax, rbx
0x18001d09c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d0a1  mov     ebx, eax
0x18001d0a3  mov     rcx, [rbp+3Fh+bstrString]; bstrString
0x18001d0a7  call    cs:__imp_SysFreeString
0x18001d0ad  test    ebx, ebx
0x18001d0af  jnz     short loc_18001D0EA
0x18001d0b1  lea     rdx, [rbp+3Fh+var_A0]
0x18001d0b5  mov     rcx, [rbp+3Fh+var_98]
0x18001d0b9  call    ?CopyXmlDoc@@YAJPEAUIXMLDOMNode@@AEAV?$CComPtr@UIXMLDOMDocument2@@@ATL@@@Z; CopyXmlDoc(IXMLDOMNode *,ATL::CComPtr<IXMLDOMDocument2> &)
0x18001d0be  mov     ebx, eax
0x18001d0c0  test    eax, eax
0x18001d0c2  jnz     short loc_18001D0EA
0x18001d0c4  mov     [rsp+0D0h+var_A8], rsi; unsigned int *
0x18001d0c9  mov     [rsp+0D0h+var_B0], rdi; struct _EAPMSCHAPv2_CONN_PROPERTIES **
0x18001d0ce  mov     r9d, [rbp+3Fh+arg_20]; unsigned int
0x18001d0d2  mov     r8, r15; struct _EAPMSCHAPv2_CONN_PROPERTIES *
0x18001d0d5  mov     rdx, [rbp+3Fh+var_A0]; struct IXMLDOMDocument2 *
0x18001d0d9  mov     ecx, r12d; unsigned int
0x18001d0dc  call    ?MsChapV2CreateConnectionProperties@@YAKKPEAUIXMLDOMDocument2@@PEAU_EAPMSCHAPv2_CONN_PROPERTIES@@KPEAPEAU2@PEAK@Z; MsChapV2CreateConnectionProperties(ulong,IXMLDOMDocument2 *,_EAPMSCHAPv2_CONN_PROPERTIES *,ulong,_EAPMSCHAPv2_CONN_PROPERTIES * *,ulong *)
0x18001d0e1  mov     ebx, eax
0x18001d0e3  jmp     short loc_18001D0EA
0x18001d0e5  mov     ebx, 0A0h
0x18001d0ea  xor     ecx, ecx
0x18001d0ec  call    DebuggingInit
0x18001d0f1  nop
0x18001d0f2  lea     rcx, [rbp+3Fh+var_A0]
0x18001d0f6  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18001d0fb  nop
0x18001d0fc  lea     rcx, [rbp+3Fh+var_98]
0x18001d100  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18001d105  mov     eax, ebx
0x18001d107  lea     r11, [rsp+0D0h+var_30]
0x18001d10f  movaps  xmm6, xmmword ptr [r11-10h]
0x18001d114  movaps  xmm7, xmmword ptr [r11-20h]
0x18001d119  mov     rsp, r11
0x18001d11c  pop     r15
0x18001d11e  pop     r14
0x18001d120  pop     r12
0x18001d122  pop     rdi
0x18001d123  pop     rsi
0x18001d124  pop     rbx
0x18001d125  pop     rbp
0x18001d126  retn
```
