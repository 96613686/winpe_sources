# RasEapCreateUserProperties2

- ea: `0x180064790`
- end: `0x180064991`
- name: `RasEapCreateUserProperties2`
- size: `513`
- prototype: `__int64 __usercall@<rax>(unsigned int@<ecx>, unsigned int@<edx>, unsigned __int16 *@<r8>, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, BSTR bstrString, unsigned int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800049e0`
- `0x180005010`
- `0x180005f80`
- `0x18001d350`
- `0x180021e74`
- `0x1800350e4`
- `0x180061fc4`
- `0x180064790`
- `0x180082010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18006488a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800648e6`
- `OLEAUT32!__imp_SysFreeString` at `0x18006488a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800648e6`
- `OLEAUT32!__imp_VariantClear` at `0x18006489a`
- `OLEAUT32!__imp_VariantClear` at `0x18006489a`

## string_xrefs

- `0x180064827`: `xmlns:eapuserpropertiesv1='http://www.microsoft.com/provisioning/EapUserPropertiesV1' xmlns:baseeapuserpropertiesv1='http://www.microsoft.com/provisioning/BaseEapUserPropertiesV1'`

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
0x180064790  mov     rax, rsp
0x180064793  push    rbp
0x180064794  push    rbx
0x180064795  push    rsi
0x180064796  push    rdi
0x180064797  push    r12
0x180064799  push    r13
0x18006479b  push    r14
0x18006479d  push    r15
0x18006479f  lea     rbp, [rax-47h]
0x1800647a3  sub     rsp, 0C8h
0x1800647aa  xor     ebx, ebx
0x1800647ac  movaps  xmmword ptr [rax-58h], xmm6
0x1800647b0  mov     r13d, edx
0x1800647b3  movaps  xmmword ptr [rax-68h], xmm7
0x1800647b7  mov     r15d, ecx
0x1800647ba  mov     [rbp+3Fh+var_A8], rbx
0x1800647be  xor     edx, edx; int
0x1800647c0  mov     [rbp+3Fh+var_B0], rbx
0x1800647c4  lea     ecx, [rbx+1]; int
0x1800647c7  mov     rdi, r9
0x1800647ca  mov     r12, r8
0x1800647cd  call    ?EapTlsInitialize2@@YAKHH@Z; EapTlsInitialize2(int,int)
0x1800647d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800647d9  lea     rax, WPP_GLOBAL_Control
0x1800647e0  cmp     rcx, rax
0x1800647e3  jz      short loc_1800647FB
0x1800647e5  mov     rcx, [rcx+10h]
0x1800647e9  lea     edx, [rbx+16h]
0x1800647ec  mov     r9d, r15d
0x1800647ef  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x1800647f6  call    WPP_SF_d
0x1800647fb  mov     rsi, [rbp+3Fh+bstrString]
0x180064802  test    rsi, rsi
0x180064805  jz      loc_18006494C
0x18006480b  mov     r14, [rbp+3Fh+arg_48]
0x180064812  test    r14, r14
0x180064815  jz      loc_18006494C
0x18006481b  test    rdi, rdi
0x18006481e  jz      loc_18006494C
0x180064824  mov     [rsi], rbx
0x180064827  lea     rdx, aXmlnsEapuserpr; "xmlns:eapuserpropertiesv1='http://www.m"...
0x18006482e  mov     [r14], ebx
0x180064831  lea     rcx, [rbp+3Fh+pvarg]
0x180064835  mov     rax, [rdi]
0x180064838  mov     rbx, [rax+280h]
0x18006483f  xor     eax, eax
0x180064841  mov     word ptr [rbp+3Fh+pvarg], ax
0x180064845  call    ??4CComVariant@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComVariant::operator=(ushort const *)
0x18006484a  movups  xmm6, xmmword ptr [rbp+3Fh+pvarg]
0x18006484e  lea     rdx, aSelectionnames; "SelectionNamespaces"
0x180064855  movsd   xmm7, qword ptr [rbp+3Fh+pvarg+10h]
0x18006485a  lea     rcx, [rbp+3Fh+bstrString]; this
0x180064861  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180064866  lea     r8, [rbp+3Fh+var_80]
0x18006486a  movaps  [rbp+3Fh+var_80], xmm6
0x18006486e  mov     rcx, rdi
0x180064871  movsd   [rbp+3Fh+var_70], xmm7
0x180064876  mov     rdx, [rax]
0x180064879  mov     rax, rbx
0x18006487c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064881  mov     rcx, [rbp+3Fh+bstrString]; bstrString
0x180064888  mov     ebx, eax
0x18006488a  call    cs:__imp_SysFreeString
0x180064891  nop     dword ptr [rax+rax+00h]
0x180064896  lea     rcx, [rbp+3Fh+pvarg]; pvarg
0x18006489a  call    cs:__imp_VariantClear
0x1800648a1  nop     dword ptr [rax+rax+00h]
0x1800648a6  test    ebx, ebx
0x1800648a8  jnz     loc_180064951
0x1800648ae  mov     rax, [rdi]
0x1800648b1  lea     rdx, aEapuserpropert; "//eapuserpropertiesv1:User[1]/baseeapus"...
0x1800648b8  lea     rcx, [rbp+3Fh+bstrString]; this
0x1800648bf  mov     rbx, [rax+128h]
0x1800648c6  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1800648cb  lea     r8, [rbp+3Fh+var_A8]
0x1800648cf  mov     rcx, rdi
0x1800648d2  mov     rdx, [rax]
0x1800648d5  mov     rax, rbx
0x1800648d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800648dd  mov     rcx, [rbp+3Fh+bstrString]; bstrString
0x1800648e4  mov     ebx, eax
0x1800648e6  call    cs:__imp_SysFreeString
0x1800648ed  nop     dword ptr [rax+rax+00h]
0x1800648f2  test    ebx, ebx
0x1800648f4  jnz     short loc_180064951
0x1800648f6  mov     rcx, [rbp+3Fh+var_A8]
0x1800648fa  lea     rdx, [rbp+3Fh+var_B0]
0x1800648fe  call    ?CopyXmlDoc@@YAJPEAUIXMLDOMNode@@AEAV?$CComPtr@UIXMLDOMDocument2@@@ATL@@@Z; CopyXmlDoc(IXMLDOMNode *,ATL::CComPtr<IXMLDOMDocument2> &)
0x180064903  mov     ebx, eax
0x180064905  test    eax, eax
0x180064907  jnz     short loc_180064951
0x180064909  mov     eax, [rbp+3Fh+arg_38]
0x18006490f  mov     r8, r12; unsigned __int16 *
0x180064912  mov     r9, [rbp+3Fh+var_B0]; struct IXMLDOMDocument2 *
0x180064916  mov     edx, r13d; unsigned int
0x180064919  mov     [rsp+100h+var_B8], r14; unsigned int *
0x18006491e  mov     ecx, r15d; unsigned int
0x180064921  mov     [rsp+100h+var_C0], rsi; unsigned __int8 **
0x180064926  mov     [rsp+100h+var_C8], eax; unsigned int
0x18006492a  mov     rax, [rbp+3Fh+arg_30]
0x18006492e  mov     [rsp+100h+var_D0], rax; unsigned __int8 *
0x180064933  mov     eax, [rbp+3Fh+arg_28]
0x180064936  mov     [rsp+100h+var_D8], eax; unsigned int
0x18006493a  mov     rax, [rbp+3Fh+arg_20]
0x18006493e  mov     [rsp+100h+var_E0], rax; unsigned __int8 *
0x180064943  call    ?EapCreateUserPropertiesInternal@@YAKKKPEBGPEAUIXMLDOMDocument2@@PEAEK2KPEAPEAEPEAK@Z; EapCreateUserPropertiesInternal(ulong,ulong,ushort const *,IXMLDOMDocument2 *,uchar *,ulong,uchar *,ulong,uchar * *,ulong *)
0x180064948  mov     ebx, eax
0x18006494a  jmp     short loc_180064951
0x18006494c  mov     ebx, 0A0h
0x180064951  xor     edx, edx; int
0x180064953  xor     ecx, ecx; int
0x180064955  call    ?EapTlsInitialize2@@YAKHH@Z; EapTlsInitialize2(int,int)
0x18006495a  lea     rcx, [rbp+3Fh+var_B0]
0x18006495e  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180064963  lea     rcx, [rbp+3Fh+var_A8]
0x180064967  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18006496c  lea     r11, [rsp+100h+var_38]
0x180064974  mov     eax, ebx
0x180064976  movaps  xmm6, xmmword ptr [r11-18h]
0x18006497b  movaps  xmm7, xmmword ptr [r11-28h]
0x180064980  mov     rsp, r11
0x180064983  pop     r15
0x180064985  pop     r14
0x180064987  pop     r13
0x180064989  pop     r12
0x18006498b  pop     rdi
0x18006498c  pop     rsi
0x18006498d  pop     rbx
0x18006498e  pop     rbp
0x18006498f  retn
```
