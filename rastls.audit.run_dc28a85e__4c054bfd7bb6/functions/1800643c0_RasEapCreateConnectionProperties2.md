# RasEapCreateConnectionProperties2

- ea: `0x1800643c0`
- end: `0x180064595`
- name: `RasEapCreateConnectionProperties2`
- size: `469`
- prototype: `__int64 __usercall@<rax>(unsigned int@<ecx>, unsigned int@<edx>, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800049e0`
- `0x180005010`
- `0x180005540`
- `0x180005f80`
- `0x18001d350`
- `0x180021e74`
- `0x1800350e4`
- `0x1800643c0`
- `0x180082010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800644b0`
- `OLEAUT32!__imp_SysFreeString` at `0x180064506`
- `OLEAUT32!__imp_SysFreeString` at `0x1800644b0`
- `OLEAUT32!__imp_SysFreeString` at `0x180064506`
- `OLEAUT32!__imp_VariantClear` at `0x1800644c0`
- `OLEAUT32!__imp_VariantClear` at `0x1800644c0`

## string_xrefs

- `0x180064453`: `xmlns:eapconnectionpropertiesv1='http://www.microsoft.com/provisioning/EapConnectionPropertiesV1' xmlns:baseeapconnectionpropertiesv1='http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1'`

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
0x1800643c0  mov     rax, rsp
0x1800643c3  push    rbp
0x1800643c4  push    rbx
0x1800643c5  push    rsi
0x1800643c6  push    rdi
0x1800643c7  push    r12
0x1800643c9  push    r13
0x1800643cb  push    r14
0x1800643cd  push    r15
0x1800643cf  lea     rbp, [rax-47h]
0x1800643d3  sub     rsp, 0B8h
0x1800643da  xor     ebx, ebx
0x1800643dc  movaps  xmmword ptr [rax-58h], xmm6
0x1800643e0  mov     r13d, edx
0x1800643e3  movaps  xmmword ptr [rax-68h], xmm7
0x1800643e7  mov     r15d, ecx
0x1800643ea  mov     [rbp+3Fh+var_B0], rbx
0x1800643ee  xor     edx, edx; int
0x1800643f0  mov     [rbp+3Fh+arg_10], rbx
0x1800643f4  lea     ecx, [rbx+1]; int
0x1800643f7  mov     r12, r9
0x1800643fa  mov     rdi, r8
0x1800643fd  call    ?EapTlsInitialize2@@YAKHH@Z; EapTlsInitialize2(int,int)
0x180064402  mov     rcx, cs:WPP_GLOBAL_Control
0x180064409  lea     rax, WPP_GLOBAL_Control
0x180064410  cmp     rcx, rax
0x180064413  jz      short loc_18006442D
0x180064415  mov     rcx, [rcx+10h]
0x180064419  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180064420  mov     edx, 99h
0x180064425  mov     r9d, r15d
0x180064428  call    WPP_SF_d
0x18006442d  test    rdi, rdi
0x180064430  jz      loc_180064550
0x180064436  mov     rsi, [rbp+3Fh+arg_28]
0x18006443a  test    rsi, rsi
0x18006443d  jz      loc_180064550
0x180064443  mov     r14, [rbp+3Fh+arg_30]
0x180064447  test    r14, r14
0x18006444a  jz      loc_180064550
0x180064450  mov     [rsi], rbx
0x180064453  lea     rdx, aXmlnsEapconnec; "xmlns:eapconnectionpropertiesv1='http:/"...
0x18006445a  mov     [r14], ebx
0x18006445d  lea     rcx, [rbp+3Fh+pvarg]
0x180064461  mov     rax, [rdi]
0x180064464  mov     rbx, [rax+280h]
0x18006446b  xor     eax, eax
0x18006446d  mov     word ptr [rbp+3Fh+pvarg], ax
0x180064471  call    ??4CComVariant@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComVariant::operator=(ushort const *)
0x180064476  movups  xmm6, xmmword ptr [rbp+3Fh+pvarg]
0x18006447a  lea     rdx, aSelectionnames; "SelectionNamespaces"
0x180064481  movsd   xmm7, qword ptr [rbp+3Fh+pvarg+10h]
0x180064486  lea     rcx, [rbp+3Fh+bstrString]; this
0x18006448a  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18006448f  lea     r8, [rbp+3Fh+var_80]
0x180064493  movaps  [rbp+3Fh+var_80], xmm6
0x180064497  mov     rcx, rdi
0x18006449a  movsd   [rbp+3Fh+var_70], xmm7
0x18006449f  mov     rdx, [rax]
0x1800644a2  mov     rax, rbx
0x1800644a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800644aa  mov     rcx, [rbp+3Fh+bstrString]; bstrString
0x1800644ae  mov     ebx, eax
0x1800644b0  call    cs:__imp_SysFreeString
0x1800644b7  nop     dword ptr [rax+rax+00h]
0x1800644bc  lea     rcx, [rbp+3Fh+pvarg]; pvarg
0x1800644c0  call    cs:__imp_VariantClear
0x1800644c7  nop     dword ptr [rax+rax+00h]
0x1800644cc  test    ebx, ebx
0x1800644ce  jnz     loc_180064555
0x1800644d4  mov     rax, [rdi]
0x1800644d7  lea     rdx, aEapconnectionp; "//eapconnectionpropertiesv1:Connections"...
0x1800644de  lea     rcx, [rbp+3Fh+bstrString]; this
0x1800644e2  mov     rbx, [rax+128h]
0x1800644e9  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1800644ee  lea     r8, [rbp+3Fh+var_B0]
0x1800644f2  mov     rcx, rdi
0x1800644f5  mov     rdx, [rax]
0x1800644f8  mov     rax, rbx
0x1800644fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064500  mov     rcx, [rbp+3Fh+bstrString]; bstrString
0x180064504  mov     ebx, eax
0x180064506  call    cs:__imp_SysFreeString
0x18006450d  nop     dword ptr [rax+rax+00h]
0x180064512  test    ebx, ebx
0x180064514  jnz     short loc_180064555
0x180064516  mov     rcx, [rbp+3Fh+var_B0]
0x18006451a  lea     rdx, [rbp+3Fh+arg_10]
0x18006451e  call    ?CopyXmlDoc@@YAJPEAUIXMLDOMNode@@AEAV?$CComPtr@UIXMLDOMDocument2@@@ATL@@@Z; CopyXmlDoc(IXMLDOMNode *,ATL::CComPtr<IXMLDOMDocument2> &)
0x180064523  mov     ebx, eax
0x180064525  test    eax, eax
0x180064527  jnz     short loc_180064555
0x180064529  mov     eax, [rbp+3Fh+arg_20]
0x18006452c  mov     r9, r12; unsigned __int8 *
0x18006452f  mov     r8, [rbp+3Fh+arg_10]; struct IXMLDOMDocument2 *
0x180064533  mov     edx, r13d; unsigned int
0x180064536  mov     [rsp+0F0h+var_C0], r14; unsigned int *
0x18006453b  mov     ecx, r15d; unsigned int
0x18006453e  mov     [rsp+0F0h+var_C8], rsi; unsigned __int8 **
0x180064543  mov     [rsp+0F0h+var_D0], eax; unsigned int
0x180064547  call    ?EapCreateConnectionPropertiesInternal@@YAKKKPEAUIXMLDOMDocument2@@PEAEKPEAPEAEPEAK@Z; EapCreateConnectionPropertiesInternal(ulong,ulong,IXMLDOMDocument2 *,uchar *,ulong,uchar * *,ulong *)
0x18006454c  mov     ebx, eax
0x18006454e  jmp     short loc_180064555
0x180064550  mov     ebx, 0A0h
0x180064555  xor     edx, edx; int
0x180064557  xor     ecx, ecx; int
0x180064559  call    ?EapTlsInitialize2@@YAKHH@Z; EapTlsInitialize2(int,int)
0x18006455e  lea     rcx, [rbp+3Fh+arg_10]
0x180064562  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180064567  lea     rcx, [rbp+3Fh+var_B0]
0x18006456b  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180064570  lea     r11, [rsp+0F0h+var_38]
0x180064578  mov     eax, ebx
0x18006457a  movaps  xmm6, xmmword ptr [r11-18h]
0x18006457f  movaps  xmm7, xmmword ptr [r11-28h]
0x180064584  mov     rsp, r11
0x180064587  pop     r15
0x180064589  pop     r14
0x18006458b  pop     r13
0x18006458d  pop     r12
0x18006458f  pop     rdi
0x180064590  pop     rsi
0x180064591  pop     rbx
0x180064592  pop     rbp
0x180064593  retn
```
