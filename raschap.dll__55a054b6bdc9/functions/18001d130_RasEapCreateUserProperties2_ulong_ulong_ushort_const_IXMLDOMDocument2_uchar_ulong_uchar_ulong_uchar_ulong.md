# RasEapCreateUserProperties2(ulong,ulong,ushort const *,IXMLDOMDocument2 *,uchar *,ulong,uchar *,ulong,uchar * *,ulong *)

- ea: `0x18001d130`
- end: `0x18001d327`
- name: `?RasEapCreateUserProperties2@@YAKKKPEBGPEAUIXMLDOMDocument2@@PEAEK2KPEAPEAEPEAK@Z`
- size: `503`
- prototype: `unsigned int(unsigned int, unsigned int, const unsigned __int16 *, struct IXMLDOMDocument2 *, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003ad0`
- `0x180003bd0`
- `0x180004690`
- `0x18000e500`
- `0x18001227c`
- `0x18001256c`
- `0x18001cbe4`
- `0x18001d130`
- `0x180027010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001d25d`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d2a5`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d25d`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d2a5`
- `OLEAUT32!__imp_VariantClear` at `0x18001d268`
- `OLEAUT32!__imp_VariantClear` at `0x18001d268`

## string_xrefs

- `0x18001d211`: `xmlns:eapuserpropertiesv1='http://www.microsoft.com/provisioning/EapUserPropertiesV1' xmlns:baseeapuserpropertiesv1='http://www.microsoft.com/provisioning/BaseEapUserPropertiesV1'`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall RasEapCreateUserProperties2(
        unsigned int a1,
        unsigned int a2,
        const unsigned __int16 *a3,
        struct IXMLDOMDocument2 *a4,
        struct _EAPMSCHAPv2_CONN_PROPERTIES *a5,
        unsigned int a6,
        unsigned __int8 *a7,
        unsigned int a8,
        struct _EAPMSCHAPv2_USER_PROPERTIES **a9,
        unsigned int *a10)
{
  _QWORD *v13; // rcx
  unsigned int UserProperties; // ebx
  HRESULT (__stdcall *setProperty)(IXMLDOMDocument2 *, BSTR, VARIANT); // rbx
  __int128 v16; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  _QWORD *v18; // rax
  HRESULT (__stdcall *selectSingleNode)(IXMLDOMDocument2 *, BSTR, IXMLDOMNode **); // rbx
  _QWORD *v20; // rax
  const unsigned __int16 *v21; // rdx
  struct _EAPMSCHAPv2_USER_PROPERTIES *v23; // [rsp+30h] [rbp-99h]
  unsigned int v24; // [rsp+38h] [rbp-91h]
  struct IXMLDOMDocument2 *v25; // [rsp+58h] [rbp-71h] BYREF
  __int64 v26; // [rsp+60h] [rbp-69h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp-61h] BYREF
  VARIANTARG pvarg; // [rsp+70h] [rbp-59h] BYREF
  __int128 v29; // [rsp+88h] [rbp-41h] BYREF
  IRecordInfo *v30; // [rsp+98h] [rbp-31h]

  v26 = 0;
  v25 = 0;
  DebuggingInit(1);
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_47d2ae5abdbe322473422603828ba620_Traceguids, a1);
    v13 = WPP_GLOBAL_Control;
  }
  if ( a1 == 26 )
  {
    if ( a9 && a10 && a4 )
    {
      *a9 = 0;
      *a10 = 0;
      setProperty = a4->lpVtbl->setProperty;
      pvarg.vt = 0;
      ATL::CComVariant::operator=(
        &pvarg,
        L"xmlns:eapuserpropertiesv1='http://www.microsoft.com/provisioning/EapUserPropertiesV1' xmlns:baseeapuserpropertie"
         "sv1='http://www.microsoft.com/provisioning/BaseEapUserPropertiesV1'");
      v16 = *(_OWORD *)&pvarg.vt;
      pRecInfo = pvarg.pRecInfo;
      v18 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"SelectionNamespaces");
      v29 = v16;
      v30 = pRecInfo;
      UserProperties = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, _QWORD, __int128 *))setProperty)(
                         a4,
                         *v18,
                         &v29);
      SysFreeString(bstrString);
      VariantClear(&pvarg);
      if ( !UserProperties )
      {
        selectSingleNode = a4->lpVtbl->selectSingleNode;
        v20 = (_QWORD *)ATL::CComBSTR::CComBSTR(
                          (ATL::CComBSTR *)&bstrString,
                          L"//eapuserpropertiesv1:User[1]/baseeapuserpropertiesv1:Eap[1]");
        UserProperties = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, _QWORD, __int64 *))selectSingleNode)(
                           a4,
                           *v20,
                           &v26);
        SysFreeString(bstrString);
        if ( !UserProperties )
        {
          UserProperties = CopyXmlDoc(v26, (LPVOID *)&v25);
          if ( !UserProperties )
            UserProperties = MsChapV2CreateUserProperties(a2, v21, v25, a5, a6, v23, v24, a9, a10);
        }
      }
    }
    else
    {
      UserProperties = 160;
    }
  }
  else
  {
    if ( v13 != &WPP_GLOBAL_Control )
      WPP_SF_d(v13[2], 20, WPP_47d2ae5abdbe322473422603828ba620_Traceguids, a1);
    UserProperties = 50;
  }
  DebuggingInit(0);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v25);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v26);
  return UserProperties;
}

```

## disassembly

```asm
0x18001d130  mov     rax, rsp
0x18001d133  push    rbp
0x18001d134  push    rbx
0x18001d135  push    rsi
0x18001d136  push    rdi
0x18001d137  push    r14
0x18001d139  push    r15
0x18001d13b  lea     rbp, [rax-37h]
0x18001d13f  sub     rsp, 0C8h
0x18001d146  movaps  xmmword ptr [rax-48h], xmm6
0x18001d14a  movaps  xmmword ptr [rax-58h], xmm7
0x18001d14e  mov     r14, r9
0x18001d151  mov     r15d, edx
0x18001d154  mov     ebx, ecx
0x18001d156  mov     [rbp+2Fh+var_98], 0
0x18001d15e  mov     [rbp+2Fh+var_A0], 0
0x18001d166  mov     ecx, 1
0x18001d16b  call    DebuggingInit
0x18001d170  lea     rdi, WPP_GLOBAL_Control
0x18001d177  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d17e  cmp     rcx, rdi
0x18001d181  jz      short loc_18001D1A2
0x18001d183  mov     edx, 13h
0x18001d188  mov     r9d, ebx
0x18001d18b  lea     r8, WPP_47d2ae5abdbe322473422603828ba620_Traceguids
0x18001d192  mov     rcx, [rcx+10h]
0x18001d196  call    WPP_SF_d
0x18001d19b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d1a2  cmp     ebx, 1Ah
0x18001d1a5  jz      short loc_18001D1CE
0x18001d1a7  cmp     rcx, rdi
0x18001d1aa  jz      short loc_18001D1C4
0x18001d1ac  mov     edx, 14h
0x18001d1b1  mov     r9d, ebx
0x18001d1b4  lea     r8, WPP_47d2ae5abdbe322473422603828ba620_Traceguids
0x18001d1bb  mov     rcx, [rcx+10h]
0x18001d1bf  call    WPP_SF_d
0x18001d1c4  mov     ebx, 32h ; '2'
0x18001d1c9  jmp     loc_18001D2EC
0x18001d1ce  mov     rdi, [rbp+2Fh+arg_40]
0x18001d1d2  test    rdi, rdi
0x18001d1d5  jz      loc_18001D2E7
0x18001d1db  mov     rsi, [rbp+2Fh+arg_48]
0x18001d1e2  test    rsi, rsi
0x18001d1e5  jz      loc_18001D2E7
0x18001d1eb  test    r14, r14
0x18001d1ee  jz      loc_18001D2E7
0x18001d1f4  mov     qword ptr [rdi], 0
0x18001d1fb  mov     dword ptr [rsi], 0
0x18001d201  mov     rax, [r14]
0x18001d204  mov     rbx, [rax+280h]
0x18001d20b  xor     eax, eax
0x18001d20d  mov     word ptr [rbp+2Fh+pvarg], ax
0x18001d211  lea     rdx, aXmlnsEapuserpr; "xmlns:eapuserpropertiesv1='http://www.m"...
0x18001d218  lea     rcx, [rbp+2Fh+pvarg]
0x18001d21c  call    ??4CComVariant@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComVariant::operator=(ushort const *)
0x18001d221  nop
0x18001d222  movups  xmm6, xmmword ptr [rbp+2Fh+pvarg]
0x18001d226  movsd   xmm7, qword ptr [rbp+2Fh+pvarg+10h]
0x18001d22b  lea     rdx, aSelectionnames; "SelectionNamespaces"
0x18001d232  lea     rcx, [rbp+2Fh+bstrString]; this
0x18001d236  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18001d23b  nop
0x18001d23c  movaps  [rbp+2Fh+var_70], xmm6
0x18001d240  movsd   [rbp+2Fh+var_60], xmm7
0x18001d245  lea     r8, [rbp+2Fh+var_70]
0x18001d249  mov     rdx, [rax]
0x18001d24c  mov     rcx, r14
0x18001d24f  mov     rax, rbx
0x18001d252  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d257  mov     ebx, eax
0x18001d259  mov     rcx, [rbp+2Fh+bstrString]; bstrString
0x18001d25d  call    cs:__imp_SysFreeString
0x18001d263  nop
0x18001d264  lea     rcx, [rbp+2Fh+pvarg]; pvarg
0x18001d268  call    cs:__imp_VariantClear
0x18001d26e  test    ebx, ebx
0x18001d270  jnz     short loc_18001D2EC
0x18001d272  mov     rax, [r14]
0x18001d275  mov     rbx, [rax+128h]
0x18001d27c  lea     rdx, aEapuserpropert; "//eapuserpropertiesv1:User[1]/baseeapus"...
0x18001d283  lea     rcx, [rbp+2Fh+bstrString]; this
0x18001d287  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18001d28c  nop
0x18001d28d  lea     r8, [rbp+2Fh+var_98]
0x18001d291  mov     rdx, [rax]
0x18001d294  mov     rcx, r14
0x18001d297  mov     rax, rbx
0x18001d29a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d29f  mov     ebx, eax
0x18001d2a1  mov     rcx, [rbp+2Fh+bstrString]; bstrString
0x18001d2a5  call    cs:__imp_SysFreeString
0x18001d2ab  test    ebx, ebx
0x18001d2ad  jnz     short loc_18001D2EC
0x18001d2af  lea     rdx, [rbp+2Fh+var_A0]
0x18001d2b3  mov     rcx, [rbp+2Fh+var_98]
0x18001d2b7  call    ?CopyXmlDoc@@YAJPEAUIXMLDOMNode@@AEAV?$CComPtr@UIXMLDOMDocument2@@@ATL@@@Z; CopyXmlDoc(IXMLDOMNode *,ATL::CComPtr<IXMLDOMDocument2> &)
0x18001d2bc  mov     ebx, eax
0x18001d2be  test    eax, eax
0x18001d2c0  jnz     short loc_18001D2EC
0x18001d2c2  mov     [rsp+0F0h+var_B0], rsi; unsigned int *
0x18001d2c7  mov     [rsp+0F0h+var_B8], rdi; struct _EAPMSCHAPv2_USER_PROPERTIES **
0x18001d2cc  mov     eax, [rbp+2Fh+arg_28]
0x18001d2cf  mov     [rsp+0F0h+var_D0], eax; unsigned int
0x18001d2d3  mov     r9, [rbp+2Fh+arg_20]; struct _EAPMSCHAPv2_CONN_PROPERTIES *
0x18001d2d7  mov     r8, [rbp+2Fh+var_A0]; struct IXMLDOMDocument2 *
0x18001d2db  mov     ecx, r15d; unsigned int
0x18001d2de  call    ?MsChapV2CreateUserProperties@@YAKKPEBGPEAUIXMLDOMDocument2@@PEAU_EAPMSCHAPv2_CONN_PROPERTIES@@KPEAU_EAPMSCHAPv2_USER_PROPERTIES@@KPEAPEAU3@PEAK@Z; MsChapV2CreateUserProperties(ulong,ushort const *,IXMLDOMDocument2 *,_EAPMSCHAPv2_CONN_PROPERTIES *,ulong,_EAPMSCHAPv2_USER_PROPERTIES *,ulong,_EAPMSCHAPv2_USER_PROPERTIES * *,ulong *)
0x18001d2e3  mov     ebx, eax
0x18001d2e5  jmp     short loc_18001D2EC
0x18001d2e7  mov     ebx, 0A0h
0x18001d2ec  xor     ecx, ecx
0x18001d2ee  call    DebuggingInit
0x18001d2f3  nop
0x18001d2f4  lea     rcx, [rbp+2Fh+var_A0]
0x18001d2f8  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18001d2fd  nop
0x18001d2fe  lea     rcx, [rbp+2Fh+var_98]
0x18001d302  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18001d307  mov     eax, ebx
0x18001d309  lea     r11, [rsp+0F0h+var_28]
0x18001d311  movaps  xmm6, xmmword ptr [r11-18h]
0x18001d316  movaps  xmm7, xmmword ptr [r11-28h]
0x18001d31b  mov     rsp, r11
0x18001d31e  pop     r15
0x18001d320  pop     r14
0x18001d322  pop     rdi
0x18001d323  pop     rsi
0x18001d324  pop     rbx
0x18001d325  pop     rbp
0x18001d326  retn
```
