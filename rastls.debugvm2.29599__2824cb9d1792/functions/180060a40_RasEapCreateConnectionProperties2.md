# RasEapCreateConnectionProperties2

- ea: `0x180060a40`
- end: `0x180060bfe`
- name: `RasEapCreateConnectionProperties2`
- size: `446`
- prototype: `__int64 __usercall@<rax>(unsigned int@<ecx>, unsigned int@<edx>, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800045f0`
- `0x180004bd0`
- `0x1800050d0`
- `0x180005ac0`
- `0x18001b9b0`
- `0x1800200b4`
- `0x180032824`
- `0x180060a40`
- `0x18007c010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180060b30`
- `OLEAUT32!__imp_SysFreeString` at `0x180060b76`
- `OLEAUT32!__imp_SysFreeString` at `0x180060b30`
- `OLEAUT32!__imp_SysFreeString` at `0x180060b76`
- `OLEAUT32!__imp_VariantClear` at `0x180060b3a`
- `OLEAUT32!__imp_VariantClear` at `0x180060b3a`

## string_xrefs

- `0x180060ad3`: `xmlns:eapconnectionpropertiesv1='http://www.microsoft.com/provisioning/EapConnectionPropertiesV1' xmlns:baseeapconnectionpropertiesv1='http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1'`

## pseudocode

```c
__int64 __fastcall RasEapCreateConnectionProperties2(
        unsigned int a1,
        unsigned int a2,
        __int64 a3,
        unsigned __int8 *a4,
        unsigned int a5,
        unsigned __int8 **a6,
        unsigned int *a7)
{
  unsigned __int8 **v11; // rsi
  unsigned int *v12; // r14
  __int64 (__fastcall *v13)(__int64, _QWORD, __int128 *); // rbx
  __int128 v14; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  _QWORD *v16; // rax
  unsigned int ConnectionPropertiesInternal; // ebx
  __int64 (__fastcall *v18)(__int64, _QWORD, __int64 *); // rbx
  _QWORD *v19; // rax
  __int64 v21; // [rsp+48h] [rbp-71h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp-69h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-61h] BYREF
  __int128 v24; // [rsp+78h] [rbp-41h] BYREF
  IRecordInfo *v25; // [rsp+88h] [rbp-31h]
  struct IXMLDOMDocument2 *v26; // [rsp+118h] [rbp+5Fh] BYREF

  v21 = 0;
  v26 = 0;
  EapTlsInitialize2(1, 0);
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 153, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, a1);
  if ( a3 && (v11 = a6) != 0 && (v12 = a7) != 0 )
  {
    *a6 = 0;
    *v12 = 0;
    v13 = *(__int64 (__fastcall **)(__int64, _QWORD, __int128 *))(*(_QWORD *)a3 + 640LL);
    pvarg.vt = 0;
    ATL::CComVariant::operator=(
      &pvarg,
      L"xmlns:eapconnectionpropertiesv1='http://www.microsoft.com/provisioning/EapConnectionPropertiesV1' xmlns:baseeapcon"
       "nectionpropertiesv1='http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1'");
    v14 = *(_OWORD *)&pvarg.vt;
    pRecInfo = pvarg.pRecInfo;
    v16 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"SelectionNamespaces");
    v24 = v14;
    v25 = pRecInfo;
    ConnectionPropertiesInternal = v13(a3, *v16, &v24);
    SysFreeString(bstrString);
    VariantClear(&pvarg);
    if ( !ConnectionPropertiesInternal )
    {
      v18 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)a3 + 296LL);
      v19 = (_QWORD *)ATL::CComBSTR::CComBSTR(
                        (ATL::CComBSTR *)&bstrString,
                        L"//eapconnectionpropertiesv1:Connections/eapconnectionpropertiesv1:Connection[1]/baseeapconnectio"
                         "npropertiesv1:Eap");
      ConnectionPropertiesInternal = v18(a3, *v19, &v21);
      SysFreeString(bstrString);
      if ( !ConnectionPropertiesInternal )
      {
        ConnectionPropertiesInternal = CopyXmlDoc(v21, (LPVOID *)&v26);
        if ( !ConnectionPropertiesInternal )
          ConnectionPropertiesInternal = EapCreateConnectionPropertiesInternal(a1, a2, v26, a4, a5, v11, v12);
      }
    }
  }
  else
  {
    ConnectionPropertiesInternal = 160;
  }
  EapTlsInitialize2(0, 0);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v26);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v21);
  return ConnectionPropertiesInternal;
}

```

## disassembly

```asm
0x180060a40  mov     rax, rsp
0x180060a43  push    rbp
0x180060a44  push    rbx
0x180060a45  push    rsi
0x180060a46  push    rdi
0x180060a47  push    r12
0x180060a49  push    r13
0x180060a4b  push    r14
0x180060a4d  push    r15
0x180060a4f  lea     rbp, [rax-47h]
0x180060a53  sub     rsp, 0B8h
0x180060a5a  xor     ebx, ebx
0x180060a5c  movaps  xmmword ptr [rax-58h], xmm6
0x180060a60  mov     r13d, edx
0x180060a63  movaps  xmmword ptr [rax-68h], xmm7
0x180060a67  mov     r15d, ecx
0x180060a6a  mov     [rbp+3Fh+var_B0], rbx
0x180060a6e  xor     edx, edx; int
0x180060a70  mov     [rbp+3Fh+arg_10], rbx
0x180060a74  lea     ecx, [rbx+1]; int
0x180060a77  mov     r12, r9
0x180060a7a  mov     rdi, r8
0x180060a7d  call    ?EapTlsInitialize2@@YAKHH@Z; EapTlsInitialize2(int,int)
0x180060a82  mov     rcx, cs:WPP_GLOBAL_Control
0x180060a89  lea     rax, WPP_GLOBAL_Control
0x180060a90  cmp     rcx, rax
0x180060a93  jz      short loc_180060AAD
0x180060a95  mov     rcx, [rcx+10h]
0x180060a99  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180060aa0  mov     edx, 99h
0x180060aa5  mov     r9d, r15d
0x180060aa8  call    WPP_SF_d
0x180060aad  test    rdi, rdi
0x180060ab0  jz      loc_180060BBA
0x180060ab6  mov     rsi, [rbp+3Fh+arg_28]
0x180060aba  test    rsi, rsi
0x180060abd  jz      loc_180060BBA
0x180060ac3  mov     r14, [rbp+3Fh+arg_30]
0x180060ac7  test    r14, r14
0x180060aca  jz      loc_180060BBA
0x180060ad0  mov     [rsi], rbx
0x180060ad3  lea     rdx, aXmlnsEapconnec; "xmlns:eapconnectionpropertiesv1='http:/"...
0x180060ada  mov     [r14], ebx
0x180060add  lea     rcx, [rbp+3Fh+pvarg]
0x180060ae1  mov     rax, [rdi]
0x180060ae4  mov     rbx, [rax+280h]
0x180060aeb  xor     eax, eax
0x180060aed  mov     word ptr [rbp+3Fh+pvarg], ax
0x180060af1  call    ??4CComVariant@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComVariant::operator=(ushort const *)
0x180060af6  movups  xmm6, xmmword ptr [rbp+3Fh+pvarg]
0x180060afa  lea     rdx, aSelectionnames; "SelectionNamespaces"
0x180060b01  movsd   xmm7, qword ptr [rbp+3Fh+pvarg+10h]
0x180060b06  lea     rcx, [rbp+3Fh+bstrString]; this
0x180060b0a  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180060b0f  lea     r8, [rbp+3Fh+var_80]
0x180060b13  movaps  [rbp+3Fh+var_80], xmm6
0x180060b17  mov     rcx, rdi
0x180060b1a  movsd   [rbp+3Fh+var_70], xmm7
0x180060b1f  mov     rdx, [rax]
0x180060b22  mov     rax, rbx
0x180060b25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060b2a  mov     rcx, [rbp+3Fh+bstrString]; bstrString
0x180060b2e  mov     ebx, eax
0x180060b30  call    cs:__imp_SysFreeString
0x180060b36  lea     rcx, [rbp+3Fh+pvarg]; pvarg
0x180060b3a  call    cs:__imp_VariantClear
0x180060b40  test    ebx, ebx
0x180060b42  jnz     short loc_180060BBF
0x180060b44  mov     rax, [rdi]
0x180060b47  lea     rdx, aEapconnectionp; "//eapconnectionpropertiesv1:Connections"...
0x180060b4e  lea     rcx, [rbp+3Fh+bstrString]; this
0x180060b52  mov     rbx, [rax+128h]
0x180060b59  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180060b5e  lea     r8, [rbp+3Fh+var_B0]
0x180060b62  mov     rcx, rdi
0x180060b65  mov     rdx, [rax]
0x180060b68  mov     rax, rbx
0x180060b6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060b70  mov     rcx, [rbp+3Fh+bstrString]; bstrString
0x180060b74  mov     ebx, eax
0x180060b76  call    cs:__imp_SysFreeString
0x180060b7c  test    ebx, ebx
0x180060b7e  jnz     short loc_180060BBF
0x180060b80  mov     rcx, [rbp+3Fh+var_B0]
0x180060b84  lea     rdx, [rbp+3Fh+arg_10]
0x180060b88  call    ?CopyXmlDoc@@YAJPEAUIXMLDOMNode@@AEAV?$CComPtr@UIXMLDOMDocument2@@@ATL@@@Z; CopyXmlDoc(IXMLDOMNode *,ATL::CComPtr<IXMLDOMDocument2> &)
0x180060b8d  mov     ebx, eax
0x180060b8f  test    eax, eax
0x180060b91  jnz     short loc_180060BBF
0x180060b93  mov     eax, [rbp+3Fh+arg_20]
0x180060b96  mov     r9, r12; unsigned __int8 *
0x180060b99  mov     r8, [rbp+3Fh+arg_10]; struct IXMLDOMDocument2 *
0x180060b9d  mov     edx, r13d; unsigned int
0x180060ba0  mov     [rsp+0F0h+var_C0], r14; unsigned int *
0x180060ba5  mov     ecx, r15d; unsigned int
0x180060ba8  mov     [rsp+0F0h+var_C8], rsi; unsigned __int8 **
0x180060bad  mov     [rsp+0F0h+var_D0], eax; unsigned int
0x180060bb1  call    ?EapCreateConnectionPropertiesInternal@@YAKKKPEAUIXMLDOMDocument2@@PEAEKPEAPEAEPEAK@Z; EapCreateConnectionPropertiesInternal(ulong,ulong,IXMLDOMDocument2 *,uchar *,ulong,uchar * *,ulong *)
0x180060bb6  mov     ebx, eax
0x180060bb8  jmp     short loc_180060BBF
0x180060bba  mov     ebx, 0A0h
0x180060bbf  xor     edx, edx; int
0x180060bc1  xor     ecx, ecx; int
0x180060bc3  call    ?EapTlsInitialize2@@YAKHH@Z; EapTlsInitialize2(int,int)
0x180060bc8  lea     rcx, [rbp+3Fh+arg_10]
0x180060bcc  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180060bd1  lea     rcx, [rbp+3Fh+var_B0]
0x180060bd5  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180060bda  lea     r11, [rsp+0F0h+var_38]
0x180060be2  mov     eax, ebx
0x180060be4  movaps  xmm6, xmmword ptr [r11-18h]
0x180060be9  movaps  xmm7, xmmword ptr [r11-28h]
0x180060bee  mov     rsp, r11
0x180060bf1  pop     r15
0x180060bf3  pop     r14
0x180060bf5  pop     r13
0x180060bf7  pop     r12
0x180060bf9  pop     rdi
0x180060bfa  pop     rsi
0x180060bfb  pop     rbx
0x180060bfc  pop     rbp
0x180060bfd  retn
```
