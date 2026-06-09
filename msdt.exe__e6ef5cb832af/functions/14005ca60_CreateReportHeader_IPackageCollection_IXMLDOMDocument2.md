# CreateReportHeader(IPackageCollection *,IXMLDOMDocument2 *)

- ea: `0x14005ca60`
- end: `0x14005cfbb`
- name: `?CreateReportHeader@@YAJPEAVIPackageCollection@@PEAUIXMLDOMDocument2@@@Z`
- size: `1371`
- prototype: `int(struct IPackageCollection *, struct IXMLDOMDocument2 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x14005c7b0`

## callees

- `0x140020420`
- `0x14005ab14`
- `0x14005acac`
- `0x14005b2c0`
- `0x14005b7c0`
- `0x14005bb48`
- `0x14005ca60`
- `0x14005eb44`
- `0x140063010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14005cd24`
- `OLEAUT32!__imp_SysFreeString` at `0x14005ce23`
- `OLEAUT32!__imp_SysFreeString` at `0x14005cf58`
- `OLEAUT32!__imp_SysFreeString` at `0x14005cd24`
- `OLEAUT32!__imp_SysFreeString` at `0x14005ce23`
- `OLEAUT32!__imp_SysFreeString` at `0x14005cf58`

## string_xrefs

- `0x14005cac1`: `CreateReportHeader`
- `0x14005cbb9`: `CreateReportHeader`
- `0x14005cbf2`: `CreateReportHeader`
- `0x14005cc86`: `CreateReportHeader`
- `0x14005ccc8`: `CreateReportHeader`
- `0x14005cda5`: `CreateReportHeader`
- `0x14005cf34`: `CreateReportHeader`
- `0x14005ccb0`: `sdiageng.dll`
- `0x14005cdd3`: `sdiageng.dll`
- `0x14005ceb2`: `sdiageng.dll`

## pseudocode

```c
__int64 __fastcall CreateReportHeader(struct IPackageCollection *a1, struct IXMLDOMDocument2 *a2)
{
  __int64 v2; // rax
  __int64 (__fastcall *v4)(struct IPackageCollection *, __int64 *); // rax
  int v5; // eax
  unsigned int v6; // ebx
  int v7; // r9d
  int v8; // eax
  struct IXMLDOMDocument2 *v9; // r15
  int RootNode; // eax
  struct IXMLDOMElement *v11; // r14
  int v12; // r9d
  const unsigned __int16 *v13; // rdx
  const unsigned __int16 *v14; // r9
  int v15; // eax
  struct IXMLDOMElement *v16; // rdi
  int v17; // eax
  int v18; // r9d
  OLECHAR *v19; // rsi
  int v20; // eax
  int v21; // r9d
  const unsigned __int16 *v22; // rdx
  const unsigned __int16 *v23; // r9
  int v24; // eax
  int v25; // r9d
  const unsigned __int16 *v26; // rdx
  const unsigned __int16 *v27; // r9
  struct IXMLDOMDocument2 *v29; // [rsp+30h] [rbp-40h] BYREF
  struct IXMLDOMElement *v30; // [rsp+38h] [rbp-38h] BYREF
  unsigned __int16 *v31; // [rsp+40h] [rbp-30h] BYREF
  unsigned __int16 *v32; // [rsp+48h] [rbp-28h] BYREF
  unsigned __int16 *v33; // [rsp+50h] [rbp-20h] BYREF
  unsigned __int16 *v34; // [rsp+58h] [rbp-18h] BYREF
  unsigned __int16 *v35; // [rsp+60h] [rbp-10h] BYREF
  struct IXMLDOMElement *v36; // [rsp+B0h] [rbp+40h] BYREF
  BSTR bstrString; // [rsp+C0h] [rbp+50h] BYREF
  __int64 v38; // [rsp+C8h] [rbp+58h] BYREF

  v2 = *(_QWORD *)a1;
  v29 = 0;
  v30 = 0;
  v36 = 0;
  v4 = *(__int64 (__fastcall **)(struct IPackageCollection *, __int64 *))(v2 + 80);
  bstrString = 0;
  v31 = 0;
  v32 = 0;
  v35 = 0;
  v33 = 0;
  v34 = 0;
  v38 = 0;
  v5 = v4(a1, &v38);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 211;
LABEL_3:
    SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "CreateReportHeader", v7, v5);
    return v6;
  }
  v5 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v38 + 40LL))(v38, &v35);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 214;
    goto LABEL_3;
  }
  v5 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v38 + 24LL))(v38, &v31);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 217;
    goto LABEL_3;
  }
  v5 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v38 + 32LL))(v38, &v32);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 220;
    goto LABEL_3;
  }
  v5 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v38 + 56LL))(v38, &v33);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 223;
    goto LABEL_3;
  }
  v5 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v38 + 48LL))(v38, &v34);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 226;
    goto LABEL_3;
  }
  v8 = MetXmlCreate((OLECHAR *)L"<MetaPackageInformation />", (LPVOID *)&v29);
  v9 = v29;
  v6 = v8;
  if ( v8 >= 0 )
  {
    RootNode = MetXmlGetRootNode(v29, &v30);
    v11 = v30;
    v6 = RootNode;
    if ( RootNode < 0 )
    {
      v12 = 235;
LABEL_18:
      SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "CreateReportHeader", v12, RootNode);
LABEL_64:
      if ( v11 )
        ((void (__fastcall *)(struct IXMLDOMElement *))v11->lpVtbl->Release)(v11);
      goto LABEL_66;
    }
    RootNode = MetXmlSetAttribute(v30, L"id", v31);
    v6 = RootNode;
    if ( RootNode < 0 )
    {
      v12 = 238;
      goto LABEL_18;
    }
    RootNode = MetXmlSetAttribute(v11, L"name", v32);
    v6 = RootNode;
    if ( RootNode < 0 )
    {
      v12 = 241;
      goto LABEL_18;
    }
    v15 = MetXmlCreateElement(v9, v13, v33, v14, L"Version", &v36);
    v6 = v15;
    if ( v15 < 0 )
    {
      SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "CreateReportHeader", 253, v15);
      v16 = v36;
LABEL_62:
      if ( v16 )
        ((void (__fastcall *)(struct IXMLDOMElement *))v16->lpVtbl->Release)(v16);
      goto LABEL_64;
    }
    v17 = MetLoadResourceString(L"sdiageng.dll", 0x77u, &bstrString);
    v6 = v17;
    if ( v17 < 0 )
    {
      v18 = 256;
LABEL_27:
      SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "CreateReportHeader", v18, v17);
      v16 = v36;
      v19 = bstrString;
      goto LABEL_60;
    }
    v19 = bstrString;
    v16 = v36;
    v20 = MetXmlSetAttribute(v36, L"name", bstrString);
    v6 = v20;
    if ( v20 < 0 )
    {
      v21 = 259;
      goto LABEL_59;
    }
    if ( v19 )
    {
      SysFreeString(v19);
      v19 = 0;
      bstrString = 0;
    }
    v20 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, struct IXMLDOMElement *, _QWORD))v11->lpVtbl->appendChild)(
            v11,
            v16,
            0);
    v6 = v20;
    if ( v20 < 0 )
    {
      v21 = 264;
      goto LABEL_59;
    }
    if ( v16 )
    {
      ((void (__fastcall *)(struct IXMLDOMElement *))v16->lpVtbl->Release)(v16);
      v36 = 0;
    }
    v24 = MetXmlCreateElement(v9, v22, v34, v23, L"Publisher", &v36);
    v6 = v24;
    if ( v24 >= 0 )
    {
      v17 = MetLoadResourceString(L"sdiageng.dll", 0x75u, &bstrString);
      v6 = v17;
      if ( v17 < 0 )
      {
        v18 = 281;
        goto LABEL_27;
      }
      v19 = bstrString;
      v16 = v36;
      v20 = MetXmlSetAttribute(v36, L"name", bstrString);
      v6 = v20;
      if ( v20 < 0 )
      {
        v21 = 284;
        goto LABEL_59;
      }
      if ( v19 )
      {
        SysFreeString(v19);
        v19 = 0;
        bstrString = 0;
      }
      v20 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, struct IXMLDOMElement *, _QWORD))v11->lpVtbl->appendChild)(
              v11,
              v16,
              0);
      v6 = v20;
      if ( v20 < 0 )
      {
        v21 = 289;
        goto LABEL_59;
      }
      if ( v16 )
      {
        ((void (__fastcall *)(struct IXMLDOMElement *))v16->lpVtbl->Release)(v16);
        v36 = 0;
      }
      v24 = MetXmlCreateElement(v9, v26, v35, v27, L"Description", &v36);
      v6 = v24;
      if ( v24 >= 0 )
      {
        v17 = MetLoadResourceString(L"sdiageng.dll", 0x76u, &bstrString);
        v6 = v17;
        if ( v17 < 0 )
        {
          v18 = 306;
          goto LABEL_27;
        }
        v19 = bstrString;
        v16 = v36;
        v20 = MetXmlSetAttribute(v36, L"name", bstrString);
        v6 = v20;
        if ( v20 >= 0 )
        {
          v20 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, struct IXMLDOMElement *, _QWORD))v11->lpVtbl->appendChild)(
                  v11,
                  v16,
                  0);
          v6 = v20;
          if ( v20 >= 0 )
          {
            v20 = SdpAddMetaPackageHeader(a2, v9);
            v6 = v20;
            if ( v20 >= 0 )
              goto LABEL_60;
            v21 = 315;
          }
          else
          {
            v21 = 312;
          }
        }
        else
        {
          v21 = 309;
        }
LABEL_59:
        SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "CreateReportHeader", v21, v20);
LABEL_60:
        if ( v19 )
          SysFreeString(v19);
        goto LABEL_62;
      }
      v25 = 303;
    }
    else
    {
      v25 = 278;
    }
    SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "CreateReportHeader", v25, v24);
    v16 = v36;
    goto LABEL_60;
  }
  SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "CreateReportHeader", 229, v8);
LABEL_66:
  if ( v9 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v9->lpVtbl->Release)(v9);
  return v6;
}

```

## disassembly

```asm
0x14005ca60  mov     [rsp-38h+arg_8], rbx
0x14005ca65  push    rbp
0x14005ca66  push    rsi
0x14005ca67  push    rdi
0x14005ca68  push    r12
0x14005ca6a  push    r13
0x14005ca6c  push    r14
0x14005ca6e  push    r15
0x14005ca70  mov     rbp, rsp
0x14005ca73  sub     rsp, 70h
0x14005ca77  mov     rax, [rcx]
0x14005ca7a  xor     r13d, r13d
0x14005ca7d  mov     r12, rdx
0x14005ca80  mov     [rbp+var_40], r13
0x14005ca84  lea     rdx, [rbp+arg_18]
0x14005ca88  mov     [rbp+var_38], r13
0x14005ca8c  mov     [rbp+arg_0], r13
0x14005ca90  mov     rax, [rax+50h]
0x14005ca94  mov     [rbp+bstrString], r13
0x14005ca98  mov     [rbp+var_30], r13
0x14005ca9c  mov     [rbp+var_28], r13
0x14005caa0  mov     [rbp+var_10], r13
0x14005caa4  mov     [rbp+var_20], r13
0x14005caa8  mov     [rbp+var_18], r13
0x14005caac  mov     [rbp+arg_18], r13
0x14005cab0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005cab5  mov     ebx, eax
0x14005cab7  test    eax, eax
0x14005cab9  jns     short loc_14005CAE2
0x14005cabb  mov     r9d, 0D3h
0x14005cac1  lea     r8, aCreatereporthe; "CreateReportHeader"
0x14005cac8  mov     dword ptr [rsp+70h+var_50], eax
0x14005cacc  lea     rdx, aMetErrorSDHr0x; "Met ERROR: %s:%d - hr = 0x%08X\n"
0x14005cad3  mov     ecx, 1; Level
0x14005cad8  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14005cadd  jmp     loc_14005CFA0
0x14005cae2  mov     rcx, [rbp+arg_18]
0x14005cae6  lea     rdx, [rbp+var_10]
0x14005caea  mov     rax, [rcx]
0x14005caed  mov     rax, [rax+28h]
0x14005caf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005caf6  mov     ebx, eax
0x14005caf8  test    eax, eax
0x14005cafa  jns     short loc_14005CB04
0x14005cafc  mov     r9d, 0D6h
0x14005cb02  jmp     short loc_14005CAC1
0x14005cb04  mov     rcx, [rbp+arg_18]
0x14005cb08  lea     rdx, [rbp+var_30]
0x14005cb0c  mov     rax, [rcx]
0x14005cb0f  mov     rax, [rax+18h]
0x14005cb13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005cb18  mov     ebx, eax
0x14005cb1a  test    eax, eax
0x14005cb1c  jns     short loc_14005CB26
0x14005cb1e  mov     r9d, 0D9h
0x14005cb24  jmp     short loc_14005CAC1
0x14005cb26  mov     rcx, [rbp+arg_18]
0x14005cb2a  lea     rdx, [rbp+var_28]
0x14005cb2e  mov     rax, [rcx]
0x14005cb31  mov     rax, [rax+20h]
0x14005cb35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005cb3a  mov     ebx, eax
0x14005cb3c  test    eax, eax
0x14005cb3e  jns     short loc_14005CB4B
0x14005cb40  mov     r9d, 0DCh
0x14005cb46  jmp     loc_14005CAC1
0x14005cb4b  mov     rcx, [rbp+arg_18]
0x14005cb4f  lea     rdx, [rbp+var_20]
0x14005cb53  mov     rax, [rcx]
0x14005cb56  mov     rax, [rax+38h]
0x14005cb5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005cb5f  mov     ebx, eax
0x14005cb61  test    eax, eax
0x14005cb63  jns     short loc_14005CB70
0x14005cb65  mov     r9d, 0DFh
0x14005cb6b  jmp     loc_14005CAC1
0x14005cb70  mov     rcx, [rbp+arg_18]
0x14005cb74  lea     rdx, [rbp+var_18]
0x14005cb78  mov     rax, [rcx]
0x14005cb7b  mov     rax, [rax+30h]
0x14005cb7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005cb84  mov     ebx, eax
0x14005cb86  test    eax, eax
0x14005cb88  jns     short loc_14005CB95
0x14005cb8a  mov     r9d, 0E2h
0x14005cb90  jmp     loc_14005CAC1
0x14005cb95  lea     rdx, [rbp+var_40]; struct IXMLDOMDocument2 **
0x14005cb99  lea     rcx, aMetapackageinf; "<MetaPackageInformation />"
0x14005cba0  call    ?MetXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; MetXmlCreate(ushort const *,IXMLDOMDocument2 * *)
0x14005cba5  mov     r15, [rbp+var_40]
0x14005cba9  mov     ebx, eax
0x14005cbab  test    eax, eax
0x14005cbad  jns     short loc_14005CBD6
0x14005cbaf  mov     r9d, 0E5h
0x14005cbb5  mov     dword ptr [rsp+70h+var_50], eax
0x14005cbb9  lea     r8, aCreatereporthe; "CreateReportHeader"
0x14005cbc0  mov     ecx, 1; Level
0x14005cbc5  lea     rdx, aMetErrorSDHr0x; "Met ERROR: %s:%d - hr = 0x%08X\n"
0x14005cbcc  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14005cbd1  jmp     loc_14005CF8C
0x14005cbd6  lea     rdx, [rbp+var_38]; struct IXMLDOMElement **
0x14005cbda  mov     rcx, r15; struct IXMLDOMDocument2 *
0x14005cbdd  call    ?MetXmlGetRootNode@@YAJPEAUIXMLDOMDocument2@@PEAPEAUIXMLDOMElement@@@Z; MetXmlGetRootNode(IXMLDOMDocument2 *,IXMLDOMElement * *)
0x14005cbe2  mov     r14, [rbp+var_38]
0x14005cbe6  mov     ebx, eax
0x14005cbe8  test    eax, eax
0x14005cbea  jns     short loc_14005CC13
0x14005cbec  mov     r9d, 0EBh
0x14005cbf2  lea     r8, aCreatereporthe; "CreateReportHeader"
0x14005cbf9  mov     dword ptr [rsp+70h+var_50], eax
0x14005cbfd  lea     rdx, aMetErrorSDHr0x; "Met ERROR: %s:%d - hr = 0x%08X\n"
0x14005cc04  mov     ecx, 1; Level
0x14005cc09  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14005cc0e  jmp     loc_14005CF78
0x14005cc13  mov     r8, [rbp+var_30]; unsigned __int16 *
0x14005cc17  lea     rdx, aId_1; "id"
0x14005cc1e  mov     rcx, r14; struct IXMLDOMElement *
0x14005cc21  call    ?MetXmlSetAttribute@@YAJPEAUIXMLDOMElement@@PEBG1@Z; MetXmlSetAttribute(IXMLDOMElement *,ushort const *,ushort const *)
0x14005cc26  mov     ebx, eax
0x14005cc28  test    eax, eax
0x14005cc2a  jns     short loc_14005CC34
0x14005cc2c  mov     r9d, 0EEh
0x14005cc32  jmp     short loc_14005CBF2
0x14005cc34  mov     r8, [rbp+var_28]; unsigned __int16 *
0x14005cc38  lea     rdx, aName_2; "name"
0x14005cc3f  mov     rcx, r14; struct IXMLDOMElement *
0x14005cc42  call    ?MetXmlSetAttribute@@YAJPEAUIXMLDOMElement@@PEBG1@Z; MetXmlSetAttribute(IXMLDOMElement *,ushort const *,ushort const *)
0x14005cc47  mov     ebx, eax
0x14005cc49  test    eax, eax
0x14005cc4b  jns     short loc_14005CC55
0x14005cc4d  mov     r9d, 0F1h
0x14005cc53  jmp     short loc_14005CBF2
0x14005cc55  mov     r8, [rbp+var_20]; unsigned __int16 *
0x14005cc59  lea     rax, [rbp+arg_0]
0x14005cc5d  mov     [rsp+70h+var_48], rax; struct IXMLDOMElement **
0x14005cc62  mov     rcx, r15; struct IXMLDOMDocument2 *
0x14005cc65  lea     rax, aVersion; "Version"
0x14005cc6c  mov     [rsp+70h+var_50], rax; unsigned __int16 *
0x14005cc71  call    ?MetXmlCreateElement@@YAJPEAUIXMLDOMDocument2@@PEBG111PEAPEAUIXMLDOMElement@@@Z; MetXmlCreateElement(IXMLDOMDocument2 *,ushort const *,ushort const *,ushort const *,ushort const *,IXMLDOMElement * *)
0x14005cc76  mov     ebx, eax
0x14005cc78  test    eax, eax
0x14005cc7a  jns     short loc_14005CCA7
0x14005cc7c  mov     r9d, 0FDh
0x14005cc82  mov     dword ptr [rsp+70h+var_50], eax
0x14005cc86  lea     r8, aCreatereporthe; "CreateReportHeader"
0x14005cc8d  mov     ecx, 1; Level
0x14005cc92  lea     rdx, aMetErrorSDHr0x; "Met ERROR: %s:%d - hr = 0x%08X\n"
0x14005cc99  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14005cc9e  mov     rdi, [rbp+arg_0]
0x14005cca2  jmp     loc_14005CF64
0x14005cca7  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x14005ccab  mov     edx, 77h ; 'w'; int
0x14005ccb0  lea     rcx, aSdiagengDll; "sdiageng.dll"
0x14005ccb7  call    ?MetLoadResourceString@@YAJPEBGHPEAPEAG@Z; MetLoadResourceString(ushort const *,int,ushort * *)
0x14005ccbc  mov     ebx, eax
0x14005ccbe  test    eax, eax
0x14005ccc0  jns     short loc_14005CCF1
0x14005ccc2  mov     r9d, 100h
0x14005ccc8  lea     r8, aCreatereporthe; "CreateReportHeader"
0x14005cccf  mov     dword ptr [rsp+70h+var_50], eax
0x14005ccd3  lea     rdx, aMetErrorSDHr0x; "Met ERROR: %s:%d - hr = 0x%08X\n"
0x14005ccda  mov     ecx, 1; Level
0x14005ccdf  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14005cce4  mov     rdi, [rbp+arg_0]
0x14005cce8  mov     rsi, [rbp+bstrString]
0x14005ccec  jmp     loc_14005CF50
0x14005ccf1  mov     rsi, [rbp+bstrString]
0x14005ccf5  lea     rdx, aName_2; "name"
0x14005ccfc  mov     rdi, [rbp+arg_0]
0x14005cd00  mov     r8, rsi; unsigned __int16 *
0x14005cd03  mov     rcx, rdi; struct IXMLDOMElement *
0x14005cd06  call    ?MetXmlSetAttribute@@YAJPEAUIXMLDOMElement@@PEBG1@Z; MetXmlSetAttribute(IXMLDOMElement *,ushort const *,ushort const *)
0x14005cd0b  mov     ebx, eax
0x14005cd0d  test    eax, eax
0x14005cd0f  jns     short loc_14005CD1C
0x14005cd11  mov     r9d, 103h
0x14005cd17  jmp     loc_14005CF34
0x14005cd1c  test    rsi, rsi
0x14005cd1f  jz      short loc_14005CD37
0x14005cd21  mov     rcx, rsi; bstrString
0x14005cd24  call    cs:__imp_SysFreeString
0x14005cd2b  nop     dword ptr [rax+rax+00h]
0x14005cd30  mov     rsi, r13
0x14005cd33  mov     [rbp+bstrString], r13
0x14005cd37  mov     rax, [r14]
0x14005cd3a  xor     r8d, r8d
0x14005cd3d  mov     rdx, rdi
0x14005cd40  mov     rcx, r14
0x14005cd43  mov     rax, [rax+0A8h]
0x14005cd4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005cd4f  mov     ebx, eax
0x14005cd51  test    eax, eax
0x14005cd53  jns     short loc_14005CD60
0x14005cd55  mov     r9d, 108h
0x14005cd5b  jmp     loc_14005CF34
0x14005cd60  test    rdi, rdi
0x14005cd63  jz      short loc_14005CD78
0x14005cd65  mov     rax, [rdi]
0x14005cd68  mov     rcx, rdi
0x14005cd6b  mov     rax, [rax+10h]
0x14005cd6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005cd74  mov     [rbp+arg_0], r13
0x14005cd78  mov     r8, [rbp+var_18]; unsigned __int16 *
0x14005cd7c  lea     rax, [rbp+arg_0]
0x14005cd80  mov     [rsp+70h+var_48], rax; struct IXMLDOMElement **
0x14005cd85  mov     rcx, r15; struct IXMLDOMDocument2 *
0x14005cd88  lea     rax, aPublisher; "Publisher"
0x14005cd8f  mov     [rsp+70h+var_50], rax; unsigned __int16 *
0x14005cd94  call    ?MetXmlCreateElement@@YAJPEAUIXMLDOMDocument2@@PEBG111PEAPEAUIXMLDOMElement@@@Z; MetXmlCreateElement(IXMLDOMDocument2 *,ushort const *,ushort const *,ushort const *,ushort const *,IXMLDOMElement * *)
0x14005cd99  mov     ebx, eax
0x14005cd9b  test    eax, eax
0x14005cd9d  jns     short loc_14005CDCA
0x14005cd9f  mov     r9d, 116h
0x14005cda5  lea     r8, aCreatereporthe; "CreateReportHeader"
0x14005cdac  mov     dword ptr [rsp+70h+var_50], eax
0x14005cdb0  lea     rdx, aMetErrorSDHr0x; "Met ERROR: %s:%d - hr = 0x%08X\n"
0x14005cdb7  mov     ecx, 1; Level
0x14005cdbc  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14005cdc1  mov     rdi, [rbp+arg_0]
0x14005cdc5  jmp     loc_14005CF50
0x14005cdca  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x14005cdce  mov     edx, 75h ; 'u'; int
0x14005cdd3  lea     rcx, aSdiagengDll; "sdiageng.dll"
0x14005cdda  call    ?MetLoadResourceString@@YAJPEBGHPEAPEAG@Z; MetLoadResourceString(ushort const *,int,ushort * *)
0x14005cddf  mov     ebx, eax
0x14005cde1  test    eax, eax
0x14005cde3  jns     short loc_14005CDF0
0x14005cde5  mov     r9d, 119h
0x14005cdeb  jmp     loc_14005CCC8
0x14005cdf0  mov     rsi, [rbp+bstrString]
0x14005cdf4  lea     rdx, aName_2; "name"
0x14005cdfb  mov     rdi, [rbp+arg_0]
0x14005cdff  mov     r8, rsi; unsigned __int16 *
0x14005ce02  mov     rcx, rdi; struct IXMLDOMElement *
0x14005ce05  call    ?MetXmlSetAttribute@@YAJPEAUIXMLDOMElement@@PEBG1@Z; MetXmlSetAttribute(IXMLDOMElement *,ushort const *,ushort const *)
0x14005ce0a  mov     ebx, eax
0x14005ce0c  test    eax, eax
0x14005ce0e  jns     short loc_14005CE1B
0x14005ce10  mov     r9d, 11Ch
0x14005ce16  jmp     loc_14005CF34
0x14005ce1b  test    rsi, rsi
0x14005ce1e  jz      short loc_14005CE36
0x14005ce20  mov     rcx, rsi; bstrString
0x14005ce23  call    cs:__imp_SysFreeString
0x14005ce2a  nop     dword ptr [rax+rax+00h]
0x14005ce2f  mov     rsi, r13
0x14005ce32  mov     [rbp+bstrString], r13
0x14005ce36  mov     rax, [r14]
0x14005ce39  xor     r8d, r8d
0x14005ce3c  mov     rdx, rdi
0x14005ce3f  mov     rcx, r14
0x14005ce42  mov     rax, [rax+0A8h]
0x14005ce49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005ce4e  mov     ebx, eax
0x14005ce50  test    eax, eax
0x14005ce52  jns     short loc_14005CE5F
0x14005ce54  mov     r9d, 121h
0x14005ce5a  jmp     loc_14005CF34
0x14005ce5f  test    rdi, rdi
0x14005ce62  jz      short loc_14005CE77
0x14005ce64  mov     rax, [rdi]
0x14005ce67  mov     rcx, rdi
0x14005ce6a  mov     rax, [rax+10h]
0x14005ce6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005ce73  mov     [rbp+arg_0], r13
0x14005ce77  mov     r8, [rbp+var_10]; unsigned __int16 *
0x14005ce7b  lea     rax, [rbp+arg_0]
0x14005ce7f  mov     [rsp+70h+var_48], rax; struct IXMLDOMElement **
0x14005ce84  mov     rcx, r15; struct IXMLDOMDocument2 *
0x14005ce87  lea     rax, aDescription; "Description"
0x14005ce8e  mov     [rsp+70h+var_50], rax; unsigned __int16 *
0x14005ce93  call    ?MetXmlCreateElement@@YAJPEAUIXMLDOMDocument2@@PEBG111PEAPEAUIXMLDOMElement@@@Z; MetXmlCreateElement(IXMLDOMDocument2 *,ushort const *,ushort const *,ushort const *,ushort const *,IXMLDOMElement * *)
0x14005ce98  mov     ebx, eax
0x14005ce9a  test    eax, eax
0x14005ce9c  jns     short loc_14005CEA9
0x14005ce9e  mov     r9d, 12Fh
0x14005cea4  jmp     loc_14005CDA5
0x14005cea9  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x14005cead  mov     edx, 76h ; 'v'; int
0x14005ceb2  lea     rcx, aSdiagengDll; "sdiageng.dll"
0x14005ceb9  call    ?MetLoadResourceString@@YAJPEBGHPEAPEAG@Z; MetLoadResourceString(ushort const *,int,ushort * *)
0x14005cebe  mov     ebx, eax
0x14005cec0  test    eax, eax
0x14005cec2  jns     short loc_14005CECF
0x14005cec4  mov     r9d, 132h
0x14005ceca  jmp     loc_14005CCC8
0x14005cecf  mov     rsi, [rbp+bstrString]
0x14005ced3  lea     rdx, aName_2; "name"
0x14005ceda  mov     rdi, [rbp+arg_0]
0x14005cede  mov     r8, rsi; unsigned __int16 *
0x14005cee1  mov     rcx, rdi; struct IXMLDOMElement *
0x14005cee4  call    ?MetXmlSetAttribute@@YAJPEAUIXMLDOMElement@@PEBG1@Z; MetXmlSetAttribute(IXMLDOMElement *,ushort const *,ushort const *)
0x14005cee9  mov     ebx, eax
0x14005ceeb  test    eax, eax
0x14005ceed  jns     short loc_14005CEF7
0x14005ceef  mov     r9d, 135h
0x14005cef5  jmp     short loc_14005CF34
0x14005cef7  mov     rax, [r14]
0x14005cefa  xor     r8d, r8d
0x14005cefd  mov     rdx, rdi
  ... truncated ...
```
