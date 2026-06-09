# CMapsToastTaskHandler::CreateToastXml(ushort const *,ushort const *,Windows::Data::Xml::Dom::IXmlDocument * *)

- ea: `0x180002ed4`
- end: `0x1800033e5`
- name: `?CreateToastXml@CMapsToastTaskHandler@@AEAAJPEBG0PEAPEAUIXmlDocument@Dom@Xml@Data@Windows@@@Z`
- size: `1297`
- prototype: `__int64 __fastcall(CMapsToastTaskHandler *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct Windows::Data::Xml::Dom::IXmlDocument **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000574c`

## callees

- `0x1800015b0`
- `0x180002ed4`
- `0x180004adc`
- `0x1800053e0`
- `0x180009534`
- `0x18000a010`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagation` at `0x180002fe9`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180002fe9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180002f35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000307c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180003176`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180003211`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000323b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000328b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800032b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180002f35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000307c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180003176`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180003211`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000323b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000328b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800032b3`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180002f70`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180002f70`

## string_xrefs

- `0x180002fe2`: `CMapsToastTaskHandler::CreateToastXml`
- `0x18000320a`: `protocol`
- `0x180002f2e`: `Windows.Data.Xml.Dom.XmlDocument`

## pseudocode

```c
__int64 __fastcall CMapsToastTaskHandler::CreateToastXml(
        CMapsToastTaskHandler *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct Windows::Data::Xml::Dom::IXmlDocument **a4)
{
  HRESULT v8; // eax
  int v9; // edx
  unsigned int v10; // r8d
  int v11; // esi
  struct Windows::Data::Xml::Dom::IXmlDocument *v12; // rbx
  int v13; // r8d
  int v14; // ecx
  unsigned int v15; // ebx
  __int64 (__fastcall *v16)(struct Windows::Data::Xml::Dom::IXmlDocument *, GUID *, _QWORD **); // rsi
  _QWORD *v17; // rcx
  int v18; // eax
  unsigned int v19; // r8d
  _QWORD *v20; // rbx
  __int64 v21; // rsi
  unsigned __int64 v22; // rdx
  HRESULT v23; // eax
  int v24; // edx
  unsigned int v25; // r8d
  struct Windows::Data::Xml::Dom::IXmlDocument *v26; // rbx
  __int64 (__fastcall *v27)(struct Windows::Data::Xml::Dom::IXmlDocument *, GUID *, _QWORD **); // rsi
  _QWORD *v28; // rcx
  _QWORD *v29; // rbx
  __int64 v30; // rsi
  __int64 (__fastcall ***v31)(_QWORD, _QWORD, _QWORD); // rcx
  HRESULT v32; // eax
  int v33; // edx
  unsigned int v34; // r8d
  __int64 (__fastcall ***v35)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v36)(_QWORD, GUID *, _QWORD **); // rsi
  _QWORD *v37; // rcx
  _QWORD *v38; // rbx
  __int64 v39; // r14
  HRESULT v40; // eax
  int v41; // edx
  unsigned int v42; // r8d
  HSTRING v43; // rsi
  HRESULT v44; // eax
  int v45; // edx
  unsigned int v46; // r8d
  _QWORD *v47; // rbx
  __int64 v48; // r14
  HRESULT v49; // eax
  int v50; // edx
  unsigned int v51; // r8d
  HSTRING v52; // rsi
  HRESULT v53; // eax
  int v54; // edx
  unsigned int v55; // r8d
  struct Windows::Data::Xml::Dom::IXmlDocument *v56; // rax
  _QWORD *v57; // rcx
  _QWORD *v58; // rcx
  __int64 (__fastcall ***v59)(_QWORD, _QWORD, _QWORD); // rcx
  _QWORD *v60; // rcx
  struct Windows::Data::Xml::Dom::IXmlDocument *v61; // rcx
  struct Windows::Data::Xml::Dom::IXmlDocument *v63; // [rsp+20h] [rbp-69h] BYREF
  _QWORD *v64; // [rsp+28h] [rbp-61h] BYREF
  _QWORD *v65; // [rsp+30h] [rbp-59h] BYREF
  __int64 (__fastcall ***v66)(_QWORD, GUID *, _QWORD **); // [rsp+38h] [rbp-51h] BYREF
  _QWORD *v67; // [rsp+40h] [rbp-49h] BYREF
  struct Windows::Data::Xml::Dom::IXmlDocument *v68; // [rsp+48h] [rbp-41h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-39h] BYREF
  HSTRING string; // [rsp+68h] [rbp-21h] BYREF
  HSTRING_HEADER v71; // [rsp+70h] [rbp-19h] BYREF
  HSTRING v72; // [rsp+88h] [rbp-1h] BYREF

  v63 = 0;
  v67 = 0;
  v66 = 0;
  v64 = 0;
  v65 = 0;
  string = 0;
  v8 = WindowsCreateStringReference(L"Windows.Data.Xml.Dom.XmlDocument", 0x20u, &hstringHeader, &string);
  if ( v8 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v8, v9, v10);
    __debugbreak();
  }
  v63 = 0;
  v68 = 0;
  v11 = RoActivateInstance(string, &v68);
  if ( v11 >= 0 )
  {
    if ( !memcmp_0(&GUID_f7f3a506_1e87_42d6_bcfb_b8c809fa5494, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      v12 = v68;
      v63 = v68;
      goto LABEL_7;
    }
    v11 = (**(__int64 (__fastcall ***)(struct Windows::Data::Xml::Dom::IXmlDocument *, GUID *, struct Windows::Data::Xml::Dom::IXmlDocument **))v68)(
            v68,
            &GUID_f7f3a506_1e87_42d6_bcfb_b8c809fa5494,
            &v63);
    (*(void (__fastcall **)(struct Windows::Data::Xml::Dom::IXmlDocument *))(*(_QWORD *)v68 + 16LL))(v68);
  }
  v12 = v63;
LABEL_7:
  if ( v11 < 0 )
  {
    v13 = 407;
    v14 = v11;
LABEL_9:
    v15 = ZTraceReportPropagation(v14, "CMapsToastTaskHandler::CreateToastXml", v13, this);
    goto LABEL_48;
  }
  v16 = **(__int64 (__fastcall ***)(struct Windows::Data::Xml::Dom::IXmlDocument *, GUID *, _QWORD **))v12;
  v17 = v67;
  if ( v67 )
  {
    v67 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v17 + 16LL))(v17);
  }
  v18 = v16(v12, &GUID_6cd0e74e_ee65_4489_9ebf_ca43e87ba637, &v67);
  if ( v18 < 0 )
  {
    v13 = 408;
LABEL_14:
    v14 = v18;
    goto LABEL_9;
  }
  v20 = v67;
  v21 = *v67;
  string = 0;
  v22 = -1;
  do
    ++v22;
  while ( aToastVisualBin[v22] );
  if ( v22 > 0xFFFFFFFF )
  {
LABEL_60:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v22, v19);
    __debugbreak();
  }
  if ( (int)v22 + 1 < (unsigned int)v22 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v22, v19);
    __debugbreak();
  }
  v23 = WindowsCreateStringReference(
          L"<toast>     <visual>         <binding template=\"ToastGeneric\">             <text id=\"1\"></text>           "
           "  <text id=\"2\"></text>         </binding>     </visual> </toast>",
          v22,
          &hstringHeader,
          &string);
  if ( v23 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v23, v24, v25);
    __debugbreak();
  }
  v18 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING))(v21 + 48))(v20, string);
  if ( v18 < 0 )
  {
    v13 = 411;
    goto LABEL_14;
  }
  v18 = CMapsToastTaskHandler::SetTemplateText(this, v63, a2, 1u);
  if ( v18 < 0 )
  {
    v13 = 414;
    goto LABEL_14;
  }
  v18 = CMapsToastTaskHandler::SetTemplateText(this, v63, a3, 2u);
  if ( v18 < 0 )
  {
    v13 = 415;
    goto LABEL_14;
  }
  v26 = v63;
  v27 = **(__int64 (__fastcall ***)(struct Windows::Data::Xml::Dom::IXmlDocument *, GUID *, _QWORD **))v63;
  v28 = v65;
  if ( v65 )
  {
    v65 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v28 + 16LL))(v28);
  }
  v18 = v27(v26, &GUID_63dbba8b_d0db_4fe1_b745_f9433afdc25b, &v65);
  if ( v18 < 0 )
  {
    v13 = 418;
    goto LABEL_14;
  }
  v29 = v65;
  v30 = *v65;
  v31 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v66;
  if ( v66 )
  {
    v66 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v31)[2])(v31);
  }
  string = 0;
  v32 = WindowsCreateStringReference(L"/toast", 6u, &hstringHeader, &string);
  if ( v32 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v32, v33, v34);
    __debugbreak();
  }
  v18 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, _QWORD))(v30 + 48))(v29, string, &v66);
  if ( v18 < 0 )
  {
    v13 = 419;
    goto LABEL_14;
  }
  v35 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v66;
  v36 = **v66;
  v37 = v64;
  if ( v64 )
  {
    v64 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v37 + 16LL))(v37);
  }
  v18 = v36(v35, &GUID_2dfb8a1f_6b10_4ef8_9f83_efcce8faec37, &v64);
  if ( v18 < 0 )
  {
    v13 = 420;
    goto LABEL_14;
  }
  v38 = v64;
  v39 = *v64;
  string = 0;
  v40 = WindowsCreateStringReference(L"protocol", 8u, &hstringHeader, &string);
  if ( v40 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v40, v41, v42);
    goto LABEL_66;
  }
  v43 = string;
  v72 = 0;
  v44 = WindowsCreateStringReference(L"activationType", 0xEu, &v71, &v72);
  if ( v44 < 0 )
  {
LABEL_66:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v44, v45, v46);
    goto LABEL_67;
  }
  v18 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, HSTRING))(v39 + 64))(v38, v72, v43);
  if ( v18 < 0 )
  {
    v13 = 423;
    goto LABEL_14;
  }
  v47 = v64;
  v48 = *v64;
  v72 = 0;
  v49 = WindowsCreateStringReference(L"ms-settings:maps", 0x10u, &v71, &v72);
  if ( v49 < 0 )
  {
LABEL_67:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v49, v50, v51);
    JUMPOUT(0x1800033E4LL);
  }
  v52 = v72;
  string = 0;
  v53 = WindowsCreateStringReference(L"launch", 6u, &hstringHeader, &string);
  if ( v53 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v53, v54, v55);
    goto LABEL_60;
  }
  v18 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, HSTRING))(v48 + 64))(v47, string, v52);
  if ( v18 < 0 )
  {
    v13 = 426;
    goto LABEL_14;
  }
  v15 = 0;
  v56 = v63;
  v63 = 0;
  *a4 = v56;
LABEL_48:
  v57 = v65;
  if ( v65 )
  {
    v65 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v57 + 16LL))(v57);
  }
  v58 = v64;
  if ( v64 )
  {
    v64 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v58 + 16LL))(v58);
  }
  v59 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v66;
  if ( v66 )
  {
    v66 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v59)[2])(v59);
  }
  v60 = v67;
  if ( v67 )
  {
    v67 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v60 + 16LL))(v60);
  }
  v61 = v63;
  if ( v63 )
  {
    v63 = 0;
    (*(void (__fastcall **)(struct Windows::Data::Xml::Dom::IXmlDocument *))(*(_QWORD *)v61 + 16LL))(v61);
  }
  return v15;
}

```

## disassembly

```asm
0x180002ed4  push    rbp
0x180002ed6  push    rbx
0x180002ed7  push    rsi
0x180002ed8  push    rdi
0x180002ed9  push    r12
0x180002edb  push    r13
0x180002edd  push    r14
0x180002edf  push    r15
0x180002ee1  lea     rbp, [rsp-1Fh]
0x180002ee6  sub     rsp, 0A8h
0x180002eed  mov     rax, cs:__security_cookie
0x180002ef4  xor     rax, rsp
0x180002ef7  mov     [rbp+57h+var_50], rax
0x180002efb  mov     r12, r9
0x180002efe  mov     r15, r8
0x180002f01  mov     r14, rdx
0x180002f04  mov     rdi, rcx
0x180002f07  xor     r13d, r13d
0x180002f0a  mov     [rbp+57h+var_C0], r13
0x180002f0e  mov     [rbp+57h+var_A0], r13
0x180002f12  mov     [rbp+57h+var_A8], r13
0x180002f16  mov     [rbp+57h+var_B8], r13
0x180002f1a  mov     [rbp+57h+var_B0], r13
0x180002f1e  mov     [rbp+57h+string], r13
0x180002f22  lea     r9, [rbp+57h+string]; string
0x180002f26  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180002f2a  lea     edx, [r13+20h]; length
0x180002f2e  lea     rcx, ?RuntimeClass_Windows_Data_Xml_Dom_XmlDocument@@3QBGB; "Windows.Data.Xml.Dom.XmlDocument"
0x180002f35  call    cs:__imp_WindowsCreateStringReference
0x180002f3b  test    eax, eax
0x180002f3d  js      loc_1800033AA
0x180002f43  mov     rbx, [rbp+57h+string]
0x180002f47  mov     rcx, [rbp+57h+var_C0]
0x180002f4b  test    rcx, rcx
0x180002f4e  jz      short loc_180002F61
0x180002f50  mov     [rbp+57h+var_C0], r13
0x180002f54  mov     rax, [rcx]
0x180002f57  mov     rax, [rax+10h]
0x180002f5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f60  nop
0x180002f61  mov     [rbp+57h+var_C0], r13
0x180002f65  mov     [rbp+57h+var_98], r13
0x180002f69  lea     rdx, [rbp+57h+var_98]
0x180002f6d  mov     rcx, rbx
0x180002f70  call    cs:__imp_RoActivateInstance
0x180002f76  mov     esi, eax
0x180002f78  test    eax, eax
0x180002f7a  js      short loc_180002FCF
0x180002f7c  mov     r8d, 10h; Size
0x180002f82  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x180002f89  lea     rcx, _GUID_f7f3a506_1e87_42d6_bcfb_b8c809fa5494; Buf1
0x180002f90  call    memcmp_0
0x180002f95  test    eax, eax
0x180002f97  jnz     short loc_180002FA3
0x180002f99  mov     rbx, [rbp+57h+var_98]
0x180002f9d  mov     [rbp+57h+var_C0], rbx
0x180002fa1  jmp     short loc_180002FD3
0x180002fa3  mov     rcx, [rbp+57h+var_98]
0x180002fa7  mov     rax, [rcx]
0x180002faa  lea     r8, [rbp+57h+var_C0]
0x180002fae  lea     rdx, _GUID_f7f3a506_1e87_42d6_bcfb_b8c809fa5494
0x180002fb5  mov     rax, [rax]
0x180002fb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fbd  mov     esi, eax
0x180002fbf  mov     rcx, [rbp+57h+var_98]
0x180002fc3  mov     rax, [rcx]
0x180002fc6  mov     rax, [rax+10h]
0x180002fca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fcf  mov     rbx, [rbp+57h+var_C0]
0x180002fd3  test    esi, esi
0x180002fd5  jns     short loc_180002FF6
0x180002fd7  mov     r8d, 197h
0x180002fdd  mov     ecx, esi
0x180002fdf  mov     r9, rdi
0x180002fe2  lea     rdx, aCmapstoasttask_8; "CMapsToastTaskHandler::CreateToastXml"
0x180002fe9  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x180002fef  mov     ebx, eax
0x180002ff1  jmp     loc_1800032F3
0x180002ff6  mov     rax, [rbx]
0x180002ff9  mov     rsi, [rax]
0x180002ffc  mov     rcx, [rbp+57h+var_A0]
0x180003000  test    rcx, rcx
0x180003003  jz      short loc_180003016
0x180003005  mov     [rbp+57h+var_A0], r13
0x180003009  mov     rdx, [rcx]
0x18000300c  mov     rax, [rdx+10h]
0x180003010  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003015  nop
0x180003016  lea     r8, [rbp+57h+var_A0]
0x18000301a  lea     rdx, _GUID_6cd0e74e_ee65_4489_9ebf_ca43e87ba637
0x180003021  mov     rcx, rbx
0x180003024  mov     rax, rsi
0x180003027  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000302c  nop
0x18000302d  test    eax, eax
0x18000302f  jns     short loc_18000303B
0x180003031  mov     r8d, 198h
0x180003037  mov     ecx, eax
0x180003039  jmp     short loc_180002FDF
0x18000303b  mov     rbx, [rbp+57h+var_A0]
0x18000303f  mov     rsi, [rbx]
0x180003042  mov     [rbp+57h+string], r13
0x180003046  mov     rcx, cs:sourceString; sourceString
0x18000304d  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180003051  inc     rdx; int
0x180003054  cmp     [rcx+rdx*2], r13w
0x180003059  jnz     short loc_180003051
0x18000305b  mov     eax, 0FFFFFFFFh
0x180003060  cmp     rdx, rax
0x180003063  ja      loc_18000339F
0x180003069  lea     eax, [rdx+1]
0x18000306c  cmp     eax, edx
0x18000306e  jb      loc_1800033B2
0x180003074  lea     r9, [rbp+57h+string]; string
0x180003078  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18000307c  call    cs:__imp_WindowsCreateStringReference
0x180003082  test    eax, eax
0x180003084  js      loc_1800033BD
0x18000308a  mov     rdx, [rbp+57h+string]
0x18000308e  mov     rcx, rbx
0x180003091  mov     rax, [rsi+30h]
0x180003095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000309a  nop
0x18000309b  test    eax, eax
0x18000309d  jns     short loc_1800030A7
0x18000309f  mov     r8d, 19Bh
0x1800030a5  jmp     short loc_180003037
0x1800030a7  mov     r9d, 1; unsigned int
0x1800030ad  mov     r8, r14; unsigned __int16 *
0x1800030b0  mov     rdx, [rbp+57h+var_C0]; struct Windows::Data::Xml::Dom::IXmlDocument *
0x1800030b4  mov     rcx, rdi; this
0x1800030b7  call    ?SetTemplateText@CMapsToastTaskHandler@@AEAAJPEAUIXmlDocument@Dom@Xml@Data@Windows@@PEBGI@Z; CMapsToastTaskHandler::SetTemplateText(Windows::Data::Xml::Dom::IXmlDocument *,ushort const *,uint)
0x1800030bc  test    eax, eax
0x1800030be  jns     short loc_1800030CB
0x1800030c0  mov     r8d, 19Eh
0x1800030c6  jmp     loc_180003037
0x1800030cb  mov     r9d, 2; unsigned int
0x1800030d1  mov     r8, r15; unsigned __int16 *
0x1800030d4  mov     rdx, [rbp+57h+var_C0]; struct Windows::Data::Xml::Dom::IXmlDocument *
0x1800030d8  mov     rcx, rdi; this
0x1800030db  call    ?SetTemplateText@CMapsToastTaskHandler@@AEAAJPEAUIXmlDocument@Dom@Xml@Data@Windows@@PEBGI@Z; CMapsToastTaskHandler::SetTemplateText(Windows::Data::Xml::Dom::IXmlDocument *,ushort const *,uint)
0x1800030e0  test    eax, eax
0x1800030e2  jns     short loc_1800030EF
0x1800030e4  mov     r8d, 19Fh
0x1800030ea  jmp     loc_180003037
0x1800030ef  mov     rbx, [rbp+57h+var_C0]
0x1800030f3  mov     rax, [rbx]
0x1800030f6  mov     rsi, [rax]
0x1800030f9  mov     rcx, [rbp+57h+var_B0]
0x1800030fd  test    rcx, rcx
0x180003100  jz      short loc_180003113
0x180003102  mov     [rbp+57h+var_B0], r13
0x180003106  mov     rdx, [rcx]
0x180003109  mov     rax, [rdx+10h]
0x18000310d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003112  nop
0x180003113  lea     r8, [rbp+57h+var_B0]
0x180003117  lea     rdx, _GUID_63dbba8b_d0db_4fe1_b745_f9433afdc25b
0x18000311e  mov     rcx, rbx
0x180003121  mov     rax, rsi
0x180003124  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003129  nop
0x18000312a  test    eax, eax
0x18000312c  jns     short loc_180003139
0x18000312e  mov     r8d, 1A2h
0x180003134  jmp     loc_180003037
0x180003139  mov     rbx, [rbp+57h+var_B0]
0x18000313d  mov     rsi, [rbx]
0x180003140  mov     rcx, [rbp+57h+var_A8]
0x180003144  test    rcx, rcx
0x180003147  jz      short loc_18000315A
0x180003149  mov     [rbp+57h+var_A8], r13
0x18000314d  mov     rax, [rcx]
0x180003150  mov     rax, [rax+10h]
0x180003154  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003159  nop
0x18000315a  mov     [rbp+57h+string], r13
0x18000315e  lea     r9, [rbp+57h+string]; string
0x180003162  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180003166  mov     r15d, 6
0x18000316c  mov     edx, r15d; length
0x18000316f  lea     rcx, aToast; "/toast"
0x180003176  call    cs:__imp_WindowsCreateStringReference
0x18000317c  test    eax, eax
0x18000317e  js      loc_1800033C5
0x180003184  lea     r8, [rbp+57h+var_A8]
0x180003188  mov     rdx, [rbp+57h+string]
0x18000318c  mov     rcx, rbx
0x18000318f  mov     rax, [rsi+30h]
0x180003193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003198  nop
0x180003199  test    eax, eax
0x18000319b  jns     short loc_1800031A8
0x18000319d  mov     r8d, 1A3h
0x1800031a3  jmp     loc_180003037
0x1800031a8  mov     rbx, [rbp+57h+var_A8]
0x1800031ac  mov     rax, [rbx]
0x1800031af  mov     rsi, [rax]
0x1800031b2  mov     rcx, [rbp+57h+var_B8]
0x1800031b6  test    rcx, rcx
0x1800031b9  jz      short loc_1800031CC
0x1800031bb  mov     [rbp+57h+var_B8], r13
0x1800031bf  mov     rdx, [rcx]
0x1800031c2  mov     rax, [rdx+10h]
0x1800031c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031cb  nop
0x1800031cc  lea     r8, [rbp+57h+var_B8]
0x1800031d0  lea     rdx, _GUID_2dfb8a1f_6b10_4ef8_9f83_efcce8faec37
0x1800031d7  mov     rcx, rbx
0x1800031da  mov     rax, rsi
0x1800031dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031e2  nop
0x1800031e3  test    eax, eax
0x1800031e5  jns     short loc_1800031F2
0x1800031e7  mov     r8d, 1A4h
0x1800031ed  jmp     loc_180003037
0x1800031f2  mov     rbx, [rbp+57h+var_B8]
0x1800031f6  mov     r14, [rbx]
0x1800031f9  mov     [rbp+57h+string], r13
0x1800031fd  lea     r9, [rbp+57h+string]; string
0x180003201  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180003205  mov     edx, 8; length
0x18000320a  lea     rcx, aProtocol; "protocol"
0x180003211  call    cs:__imp_WindowsCreateStringReference
0x180003217  test    eax, eax
0x180003219  js      loc_1800033CD
0x18000321f  mov     rsi, [rbp+57h+string]
0x180003223  mov     [rbp+57h+var_58], r13
0x180003227  lea     r9, [rbp+57h+var_58]; string
0x18000322b  lea     r8, [rbp+57h+var_70]; hstringHeader
0x18000322f  mov     edx, 0Eh; length
0x180003234  lea     rcx, aActivationtype; "activationType"
0x18000323b  call    cs:__imp_WindowsCreateStringReference
0x180003241  test    eax, eax
0x180003243  js      loc_1800033D5
0x180003249  mov     r8, rsi
0x18000324c  mov     rdx, [rbp+57h+var_58]
0x180003250  mov     rcx, rbx
0x180003253  mov     rax, [r14+40h]
0x180003257  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000325c  nop
0x18000325d  test    eax, eax
0x18000325f  jns     short loc_18000326C
0x180003261  mov     r8d, 1A7h
0x180003267  jmp     loc_180003037
0x18000326c  mov     rbx, [rbp+57h+var_B8]
0x180003270  mov     r14, [rbx]
0x180003273  mov     [rbp+57h+var_58], r13
0x180003277  lea     r9, [rbp+57h+var_58]; string
0x18000327b  lea     r8, [rbp+57h+var_70]; hstringHeader
0x18000327f  mov     edx, 10h; length
0x180003284  lea     rcx, aMsSettingsMaps; "ms-settings:maps"
0x18000328b  call    cs:__imp_WindowsCreateStringReference
0x180003291  test    eax, eax
0x180003293  js      loc_1800033DD
0x180003299  mov     rsi, [rbp+57h+var_58]
0x18000329d  mov     [rbp+57h+string], r13
0x1800032a1  lea     r9, [rbp+57h+string]; string
0x1800032a5  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800032a9  mov     edx, r15d; length
0x1800032ac  lea     rcx, aLaunch; "launch"
0x1800032b3  call    cs:__imp_WindowsCreateStringReference
0x1800032b9  test    eax, eax
0x1800032bb  js      loc_180003397
0x1800032c1  mov     r8, rsi
0x1800032c4  mov     rdx, [rbp+57h+string]
0x1800032c8  mov     rcx, rbx
0x1800032cb  mov     rax, [r14+40h]
0x1800032cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032d4  nop
0x1800032d5  test    eax, eax
0x1800032d7  jns     short loc_1800032E4
0x1800032d9  mov     r8d, 1AAh
0x1800032df  jmp     loc_180003037
0x1800032e4  mov     ebx, r13d
0x1800032e7  mov     rax, [rbp+57h+var_C0]
0x1800032eb  mov     [rbp+57h+var_C0], r13
0x1800032ef  mov     [r12], rax
0x1800032f3  mov     rcx, [rbp+57h+var_B0]
0x1800032f7  test    rcx, rcx
0x1800032fa  jz      short loc_18000330D
0x1800032fc  mov     [rbp+57h+var_B0], r13
0x180003300  mov     rax, [rcx]
0x180003303  mov     rax, [rax+10h]
0x180003307  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000330c  nop
0x18000330d  mov     rcx, [rbp+57h+var_B8]
0x180003311  test    rcx, rcx
0x180003314  jz      short loc_180003327
0x180003316  mov     [rbp+57h+var_B8], r13
0x18000331a  mov     rax, [rcx]
0x18000331d  mov     rax, [rax+10h]
0x180003321  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003326  nop
0x180003327  mov     rcx, [rbp+57h+var_A8]
0x18000332b  test    rcx, rcx
0x18000332e  jz      short loc_180003341
0x180003330  mov     [rbp+57h+var_A8], r13
0x180003334  mov     rax, [rcx]
0x180003337  mov     rax, [rax+10h]
  ... truncated ...
```
