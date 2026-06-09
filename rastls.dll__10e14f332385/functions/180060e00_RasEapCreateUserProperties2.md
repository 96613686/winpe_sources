# RasEapCreateUserProperties2

- ea: `0x180060e00`
- end: `0x180060fee`
- name: `RasEapCreateUserProperties2`
- size: `494`
- prototype: `__int64 __usercall@<rax>(unsigned int@<ecx>, unsigned int@<edx>, unsigned __int16 *@<r8>, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, BSTR bstrString, unsigned int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800045f0`
- `0x180004bd0`
- `0x180005ac0`
- `0x18001b9b0`
- `0x1800200b4`
- `0x180032824`
- `0x18005e7f0`
- `0x180060e00`
- `0x18007c010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180060efa`
- `OLEAUT32!__imp_SysFreeString` at `0x180060f4a`
- `OLEAUT32!__imp_SysFreeString` at `0x180060efa`
- `OLEAUT32!__imp_SysFreeString` at `0x180060f4a`
- `OLEAUT32!__imp_VariantClear` at `0x180060f04`
- `OLEAUT32!__imp_VariantClear` at `0x180060f04`

## string_xrefs

- `0x180060e97`: `xmlns:eapuserpropertiesv1='http://www.microsoft.com/provisioning/EapUserPropertiesV1' xmlns:baseeapuserpropertiesv1='http://www.microsoft.com/provisioning/BaseEapUserPropertiesV1'`

## pseudocode

```c
__int64 __fastcall RasEapCreateUserProperties2(
        unsigned int a1,
        unsigned int a2,
        unsigned __int16 *a3,
        __int64 a4,
        unsigned __int8 *a5,
        unsigned int a6,
        unsigned __int8 *a7,
        unsigned int a8,
        unsigned __int8 **bstrString,
        unsigned int *a10)
{
  unsigned __int8 **v14; // rsi
  unsigned int *v15; // r14
  __int64 (__fastcall *v16)(__int64, _QWORD, __int128 *); // rbx
  __int128 v17; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  _QWORD *v19; // rax
  unsigned int UserPropertiesInternal; // ebx
  __int64 (__fastcall *v21)(__int64, _QWORD, __int64 *); // rbx
  _QWORD *v22; // rax
  struct IXMLDOMDocument2 *v24; // [rsp+58h] [rbp-71h] BYREF
  __int64 v25; // [rsp+60h] [rbp-69h] BYREF
  VARIANTARG pvarg; // [rsp+68h] [rbp-61h] BYREF
  __int128 v27; // [rsp+88h] [rbp-41h] BYREF
  IRecordInfo *v28; // [rsp+98h] [rbp-31h]

  v25 = 0;
  v24 = 0;
  EapTlsInitialize2(1, 0);
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, a1);
  v14 = bstrString;
  if ( bstrString && (v15 = a10) != 0 && a4 )
  {
    *bstrString = 0;
    *v15 = 0;
    v16 = *(__int64 (__fastcall **)(__int64, _QWORD, __int128 *))(*(_QWORD *)a4 + 640LL);
    pvarg.vt = 0;
    ATL::CComVariant::operator=(
      &pvarg,
      L"xmlns:eapuserpropertiesv1='http://www.microsoft.com/provisioning/EapUserPropertiesV1' xmlns:baseeapuserpropertiesv"
       "1='http://www.microsoft.com/provisioning/BaseEapUserPropertiesV1'");
    v17 = *(_OWORD *)&pvarg.vt;
    pRecInfo = pvarg.pRecInfo;
    v19 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"SelectionNamespaces");
    v27 = v17;
    v28 = pRecInfo;
    UserPropertiesInternal = v16(a4, *v19, &v27);
    SysFreeString((BSTR)bstrString);
    VariantClear(&pvarg);
    if ( !UserPropertiesInternal )
    {
      v21 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)a4 + 296LL);
      v22 = (_QWORD *)ATL::CComBSTR::CComBSTR(
                        (ATL::CComBSTR *)&bstrString,
                        L"//eapuserpropertiesv1:User[1]/baseeapuserpropertiesv1:Eap[1]");
      UserPropertiesInternal = v21(a4, *v22, &v25);
      SysFreeString((BSTR)bstrString);
      if ( !UserPropertiesInternal )
      {
        UserPropertiesInternal = CopyXmlDoc(v25, (LPVOID *)&v24);
        if ( !UserPropertiesInternal )
          UserPropertiesInternal = EapCreateUserPropertiesInternal(a1, a2, a3, v24, a5, a6, a7, a8, v14, v15);
      }
    }
  }
  else
  {
    UserPropertiesInternal = 160;
  }
  EapTlsInitialize2(0, 0);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v24);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v25);
  return UserPropertiesInternal;
}

```

## disassembly

```asm
0x180060e00  mov     rax, rsp
0x180060e03  push    rbp
0x180060e04  push    rbx
0x180060e05  push    rsi
0x180060e06  push    rdi
0x180060e07  push    r12
0x180060e09  push    r13
0x180060e0b  push    r14
0x180060e0d  push    r15
0x180060e0f  lea     rbp, [rax-47h]
0x180060e13  sub     rsp, 0C8h
0x180060e1a  xor     ebx, ebx
0x180060e1c  movaps  xmmword ptr [rax-58h], xmm6
0x180060e20  mov     r13d, edx
0x180060e23  movaps  xmmword ptr [rax-68h], xmm7
0x180060e27  mov     r15d, ecx
0x180060e2a  mov     [rbp+3Fh+var_A8], rbx
0x180060e2e  xor     edx, edx; int
0x180060e30  mov     [rbp+3Fh+var_B0], rbx
0x180060e34  lea     ecx, [rbx+1]; int
0x180060e37  mov     rdi, r9
0x180060e3a  mov     r12, r8
0x180060e3d  call    ?EapTlsInitialize2@@YAKHH@Z; EapTlsInitialize2(int,int)
0x180060e42  mov     rcx, cs:WPP_GLOBAL_Control
0x180060e49  lea     rax, WPP_GLOBAL_Control
0x180060e50  cmp     rcx, rax
0x180060e53  jz      short loc_180060E6B
0x180060e55  mov     rcx, [rcx+10h]
0x180060e59  lea     edx, [rbx+16h]
0x180060e5c  mov     r9d, r15d
0x180060e5f  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180060e66  call    WPP_SF_d
0x180060e6b  mov     rsi, [rbp+3Fh+bstrString]
0x180060e72  test    rsi, rsi
0x180060e75  jz      loc_180060FAA
0x180060e7b  mov     r14, [rbp+3Fh+arg_48]
0x180060e82  test    r14, r14
0x180060e85  jz      loc_180060FAA
0x180060e8b  test    rdi, rdi
0x180060e8e  jz      loc_180060FAA
0x180060e94  mov     [rsi], rbx
0x180060e97  lea     rdx, aXmlnsEapuserpr; "xmlns:eapuserpropertiesv1='http://www.m"...
0x180060e9e  mov     [r14], ebx
0x180060ea1  lea     rcx, [rbp+3Fh+pvarg]
0x180060ea5  mov     rax, [rdi]
0x180060ea8  mov     rbx, [rax+280h]
0x180060eaf  xor     eax, eax
0x180060eb1  mov     word ptr [rbp+3Fh+pvarg], ax
0x180060eb5  call    ??4CComVariant@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComVariant::operator=(ushort const *)
0x180060eba  movups  xmm6, xmmword ptr [rbp+3Fh+pvarg]
0x180060ebe  lea     rdx, aSelectionnames; "SelectionNamespaces"
0x180060ec5  movsd   xmm7, qword ptr [rbp+3Fh+pvarg+10h]
0x180060eca  lea     rcx, [rbp+3Fh+bstrString]; this
0x180060ed1  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180060ed6  lea     r8, [rbp+3Fh+var_80]
0x180060eda  movaps  [rbp+3Fh+var_80], xmm6
0x180060ede  mov     rcx, rdi
0x180060ee1  movsd   [rbp+3Fh+var_70], xmm7
0x180060ee6  mov     rdx, [rax]
0x180060ee9  mov     rax, rbx
0x180060eec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060ef1  mov     rcx, [rbp+3Fh+bstrString]; bstrString
0x180060ef8  mov     ebx, eax
0x180060efa  call    cs:__imp_SysFreeString
0x180060f00  lea     rcx, [rbp+3Fh+pvarg]; pvarg
0x180060f04  call    cs:__imp_VariantClear
0x180060f0a  test    ebx, ebx
0x180060f0c  jnz     loc_180060FAF
0x180060f12  mov     rax, [rdi]
0x180060f15  lea     rdx, aEapuserpropert; "//eapuserpropertiesv1:User[1]/baseeapus"...
0x180060f1c  lea     rcx, [rbp+3Fh+bstrString]; this
0x180060f23  mov     rbx, [rax+128h]
0x180060f2a  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180060f2f  lea     r8, [rbp+3Fh+var_A8]
0x180060f33  mov     rcx, rdi
0x180060f36  mov     rdx, [rax]
0x180060f39  mov     rax, rbx
0x180060f3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060f41  mov     rcx, [rbp+3Fh+bstrString]; bstrString
0x180060f48  mov     ebx, eax
0x180060f4a  call    cs:__imp_SysFreeString
0x180060f50  test    ebx, ebx
0x180060f52  jnz     short loc_180060FAF
0x180060f54  mov     rcx, [rbp+3Fh+var_A8]
0x180060f58  lea     rdx, [rbp+3Fh+var_B0]
0x180060f5c  call    ?CopyXmlDoc@@YAJPEAUIXMLDOMNode@@AEAV?$CComPtr@UIXMLDOMDocument2@@@ATL@@@Z; CopyXmlDoc(IXMLDOMNode *,ATL::CComPtr<IXMLDOMDocument2> &)
0x180060f61  mov     ebx, eax
0x180060f63  test    eax, eax
0x180060f65  jnz     short loc_180060FAF
0x180060f67  mov     eax, [rbp+3Fh+arg_38]
0x180060f6d  mov     r8, r12; unsigned __int16 *
0x180060f70  mov     r9, [rbp+3Fh+var_B0]; struct IXMLDOMDocument2 *
0x180060f74  mov     edx, r13d; unsigned int
0x180060f77  mov     [rsp+100h+var_B8], r14; unsigned int *
0x180060f7c  mov     ecx, r15d; unsigned int
0x180060f7f  mov     [rsp+100h+var_C0], rsi; unsigned __int8 **
0x180060f84  mov     [rsp+100h+var_C8], eax; unsigned int
0x180060f88  mov     rax, [rbp+3Fh+arg_30]
0x180060f8c  mov     [rsp+100h+var_D0], rax; unsigned __int8 *
0x180060f91  mov     eax, [rbp+3Fh+arg_28]
0x180060f94  mov     [rsp+100h+var_D8], eax; unsigned int
0x180060f98  mov     rax, [rbp+3Fh+arg_20]
0x180060f9c  mov     [rsp+100h+var_E0], rax; unsigned __int8 *
0x180060fa1  call    ?EapCreateUserPropertiesInternal@@YAKKKPEBGPEAUIXMLDOMDocument2@@PEAEK2KPEAPEAEPEAK@Z; EapCreateUserPropertiesInternal(ulong,ulong,ushort const *,IXMLDOMDocument2 *,uchar *,ulong,uchar *,ulong,uchar * *,ulong *)
0x180060fa6  mov     ebx, eax
0x180060fa8  jmp     short loc_180060FAF
0x180060faa  mov     ebx, 0A0h
0x180060faf  xor     edx, edx; int
0x180060fb1  xor     ecx, ecx; int
0x180060fb3  call    ?EapTlsInitialize2@@YAKHH@Z; EapTlsInitialize2(int,int)
0x180060fb8  lea     rcx, [rbp+3Fh+var_B0]
0x180060fbc  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180060fc1  lea     rcx, [rbp+3Fh+var_A8]
0x180060fc5  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180060fca  lea     r11, [rsp+100h+var_38]
0x180060fd2  mov     eax, ebx
0x180060fd4  movaps  xmm6, xmmword ptr [r11-18h]
0x180060fd9  movaps  xmm7, xmmword ptr [r11-28h]
0x180060fde  mov     rsp, r11
0x180060fe1  pop     r15
0x180060fe3  pop     r14
0x180060fe5  pop     r13
0x180060fe7  pop     r12
0x180060fe9  pop     rdi
0x180060fea  pop     rsi
0x180060feb  pop     rbx
0x180060fec  pop     rbp
0x180060fed  retn
```
