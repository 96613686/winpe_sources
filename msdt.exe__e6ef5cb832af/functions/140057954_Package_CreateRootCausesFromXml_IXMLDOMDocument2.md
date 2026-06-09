# Package::CreateRootCausesFromXml(IXMLDOMDocument2 *)

- ea: `0x140057954`
- end: `0x1400582fc`
- name: `?CreateRootCausesFromXml@Package@@AEAAJPEAUIXMLDOMDocument2@@@Z`
- size: `2472`
- prototype: `__int64 __fastcall(PackageCollection **this, struct IXMLDOMDocument2 *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1400591ac`

## callees

- `0x140001d54`
- `0x140020420`
- `0x14005583c`
- `0x14005784c`
- `0x140057954`
- `0x140058304`
- `0x140058674`
- `0x1400589b8`
- `0x14005b038`
- `0x14005b190`
- `0x14005b6e4`
- `0x14005d144`
- `0x14005ddec`
- `0x14005de88`
- `0x14005df90`
- `0x14005e02c`
- `0x14005e0c8`
- `0x140063010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x140057a38`
- `KERNEL32!HeapAlloc` at `0x140057a81`
- `KERNEL32!HeapAlloc` at `0x140057a38`
- `KERNEL32!HeapAlloc` at `0x140057a81`
- `KERNEL32!HeapFree` at `0x1400582ad`
- `KERNEL32!HeapFree` at `0x1400582d2`
- `KERNEL32!HeapFree` at `0x1400582ad`
- `KERNEL32!HeapFree` at `0x1400582d2`
- `KERNEL32!GetProcessHeap` at `0x140057a21`
- `KERNEL32!GetProcessHeap` at `0x140057a6a`
- `KERNEL32!GetProcessHeap` at `0x140058299`
- `KERNEL32!GetProcessHeap` at `0x1400582be`
- `KERNEL32!GetProcessHeap` at `0x140057a21`
- `KERNEL32!GetProcessHeap` at `0x140057a6a`
- `KERNEL32!GetProcessHeap` at `0x140058299`
- `KERNEL32!GetProcessHeap` at `0x1400582be`
- `msvcrt!_wcsicmp` at `0x140057c69`
- `msvcrt!_wcsicmp` at `0x140057c88`
- `msvcrt!_wcsicmp` at `0x140057d86`
- `msvcrt!_wcsicmp` at `0x140057c69`
- `msvcrt!_wcsicmp` at `0x140057c88`
- `msvcrt!_wcsicmp` at `0x140057d86`
- `OLEAUT32!__imp_SysFreeString` at `0x140057af7`
- `OLEAUT32!__imp_SysFreeString` at `0x140057b10`
- `OLEAUT32!__imp_SysFreeString` at `0x140057b29`
- `OLEAUT32!__imp_SysFreeString` at `0x140057b42`
- `OLEAUT32!__imp_SysFreeString` at `0x140057b5b`
- `OLEAUT32!__imp_SysFreeString` at `0x140057b74`
- `OLEAUT32!__imp_SysFreeString` at `0x140057e37`
- `OLEAUT32!__imp_SysFreeString` at `0x140058185`
- `OLEAUT32!__imp_SysFreeString` at `0x1400581a2`
- `OLEAUT32!__imp_SysFreeString` at `0x1400581bf`
- `OLEAUT32!__imp_SysFreeString` at `0x1400581dc`
- `OLEAUT32!__imp_SysFreeString` at `0x1400581f9`
- `OLEAUT32!__imp_SysFreeString` at `0x140058216`
- `OLEAUT32!__imp_SysFreeString` at `0x140057af7`
- `OLEAUT32!__imp_SysFreeString` at `0x140057b10`
- `OLEAUT32!__imp_SysFreeString` at `0x140057b29`
- `OLEAUT32!__imp_SysFreeString` at `0x140057b42`
- `OLEAUT32!__imp_SysFreeString` at `0x140057b5b`
- `OLEAUT32!__imp_SysFreeString` at `0x140057b74`
- `OLEAUT32!__imp_SysFreeString` at `0x140057e37`
- `OLEAUT32!__imp_SysFreeString` at `0x140058185`
- `OLEAUT32!__imp_SysFreeString` at `0x1400581a2`
- `OLEAUT32!__imp_SysFreeString` at `0x1400581bf`
- `OLEAUT32!__imp_SysFreeString` at `0x1400581dc`
- `OLEAUT32!__imp_SysFreeString` at `0x1400581f9`
- `OLEAUT32!__imp_SysFreeString` at `0x140058216`

## string_xrefs

- `0x1400579dd`: `Package::CreateRootCausesFromXml`
- `0x140057fba`: `Package::CreateRootCausesFromXml`
- `0x140058003`: `Package::CreateRootCausesFromXml`
- `0x140058028`: `Package::CreateRootCausesFromXml`
- `0x140058066`: `Package::CreateRootCausesFromXml`
- `0x1400580a8`: `Package::CreateRootCausesFromXml`
- `0x1400580f3`: `Package::CreateRootCausesFromXml`
- `0x140058131`: `Package::CreateRootCausesFromXml`
- `0x140057e6f`: `./ExtensionPoint`

## pseudocode

```c
__int64 __fastcall Package::CreateRootCausesFromXml(PackageCollection **this, struct IXMLDOMDocument2 *a2)
{
  Package *v2; // r15
  struct RootCause **v3; // r13
  struct RootCause **v4; // r12
  unsigned int v5; // r14d
  struct IXMLDOMNode *v6; // rsi
  int Nodes; // eax
  unsigned int v8; // ebx
  int v9; // r9d
  SIZE_T v10; // rbx
  HANDLE ProcessHeap; // rax
  SIZE_T v12; // rbx
  HANDLE v13; // rax
  struct RootCause **v14; // rax
  Package *v15; // rcx
  signed int v16; // r8d
  signed int v17; // eax
  int v18; // eax
  int NodeText; // eax
  int v20; // eax
  struct RootCause **v21; // r14
  int v22; // r15d
  _QWORD *v23; // rbx
  __int64 v24; // r12
  PackageCollection **v25; // rax
  __int64 v26; // rcx
  int v27; // eax
  int v28; // eax
  int v29; // eax
  struct RootCause *v30; // rax
  int v31; // eax
  bool v32; // zf
  int updated; // eax
  int v34; // eax
  int v35; // eax
  int v36; // eax
  int v37; // eax
  int v38; // eax
  int ResolutionsFromXml; // eax
  int v40; // r9d
  int v41; // eax
  Package *v42; // rcx
  int v43; // eax
  int v44; // eax
  int v45; // eax
  __int64 v46; // rsi
  struct RootCause *v47; // rcx
  __int64 i; // rsi
  struct RootCause *v49; // rcx
  HANDLE v50; // rax
  HANDLE v51; // rax
  int v53; // [rsp+20h] [rbp-59h]
  struct RootCause **v54; // [rsp+30h] [rbp-49h]
  unsigned int v55; // [rsp+38h] [rbp-41h]
  struct IXMLDOMNode *v56; // [rsp+40h] [rbp-39h] BYREF
  BSTR v57; // [rsp+48h] [rbp-31h] BYREF
  unsigned int v58; // [rsp+50h] [rbp-29h] BYREF
  unsigned int v59; // [rsp+54h] [rbp-25h] BYREF
  signed int v60; // [rsp+58h] [rbp-21h]
  BSTR bstrString; // [rsp+60h] [rbp-19h] BYREF
  BSTR String1; // [rsp+68h] [rbp-11h] BYREF
  BSTR v63; // [rsp+70h] [rbp-9h] BYREF
  BSTR v64; // [rsp+78h] [rbp-1h] BYREF
  BSTR v65; // [rsp+80h] [rbp+7h] BYREF
  int v66; // [rsp+88h] [rbp+Fh] BYREF
  struct IXMLDOMNode *v67; // [rsp+90h] [rbp+17h] BYREF
  struct IXMLDOMNodeList *v68; // [rsp+98h] [rbp+1Fh] BYREF
  unsigned int v70; // [rsp+F0h] [rbp+77h]
  unsigned int v71; // [rsp+F8h] [rbp+7Fh] BYREF

  v2 = (Package *)this;
  v70 = 0;
  v55 = 0;
  v68 = 0;
  v3 = 0;
  v67 = 0;
  v4 = 0;
  v56 = 0;
  v5 = 0;
  bstrString = 0;
  v6 = 0;
  v63 = 0;
  v64 = 0;
  String1 = 0;
  v65 = 0;
  v57 = 0;
  v66 = 0;
  v71 = 0;
  Nodes = MetXmlGetNodes(L"/Rootcauses/Rootcause", a2, 0, &v68);
  v8 = Nodes;
  if ( Nodes < 0 )
  {
    v9 = 1516;
LABEL_3:
    v53 = Nodes;
LABEL_4:
    SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "Package::CreateRootCausesFromXml", v9, v53);
    goto LABEL_103;
  }
  Nodes = ((__int64 (__fastcall *)(struct IXMLDOMNodeList *, unsigned int *))v68->lpVtbl->get_length)(v68, &v71);
  v8 = Nodes;
  if ( Nodes < 0 )
  {
    v9 = 1519;
    goto LABEL_3;
  }
  v10 = 8LL * (int)v71;
  ProcessHeap = GetProcessHeap();
  v3 = (struct RootCause **)HeapAlloc(ProcessHeap, 8u, v10);
  if ( !v3 )
  {
    v9 = 1525;
    v8 = -2147024882;
    v53 = -2147024882;
    goto LABEL_4;
  }
  v12 = 8LL * (int)v71;
  v13 = GetProcessHeap();
  v14 = (struct RootCause **)HeapAlloc(v13, 8u, v12);
  v16 = v71;
  v4 = v14;
  v54 = v14;
  v70 = v71;
  v55 = v71;
  v59 = v71;
  v17 = 0;
  v58 = v71;
  while ( 1 )
  {
    v60 = v17;
    if ( v17 >= v16 )
      break;
    if ( v6 )
    {
      ((void (__fastcall *)(struct IXMLDOMNode *))v6->lpVtbl->Release)(v6);
      v67 = 0;
    }
    if ( v56 )
    {
      ((void (__fastcall *)(struct IXMLDOMNode *))v56->lpVtbl->Release)(v56);
      v56 = 0;
    }
    if ( bstrString )
    {
      SysFreeString(bstrString);
      bstrString = 0;
    }
    if ( v63 )
    {
      SysFreeString(v63);
      v63 = 0;
    }
    if ( v64 )
    {
      SysFreeString(v64);
      v64 = 0;
    }
    if ( String1 )
    {
      SysFreeString(String1);
      String1 = 0;
    }
    if ( v65 )
    {
      SysFreeString(v65);
      v65 = 0;
    }
    if ( v57 )
    {
      SysFreeString(v57);
      v57 = 0;
    }
    v18 = MetXmlNextNode(v68, &v67);
    v8 = v18;
    if ( v18 < 0 )
    {
      SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "Package::CreateRootCausesFromXml", 1549, v18);
      v6 = v67;
      goto LABEL_90;
    }
    v6 = v67;
    NodeText = MetXmlGetNodeText(L"./ID", 0, v67, &bstrString);
    v8 = NodeText;
    if ( NodeText < 0 )
    {
      v40 = 1552;
LABEL_88:
      SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "Package::CreateRootCausesFromXml", v40, NodeText);
LABEL_90:
      v5 = v70;
      goto LABEL_101;
    }
    NodeText = MetXmlGetNodeText(L"./Status", 0, v6, &String1);
    v8 = NodeText;
    if ( NodeText < 0 )
    {
      v40 = 1555;
      goto LABEL_88;
    }
    NodeText = MetXmlGetNodeText(L"./DisplayInformation/Name", 0, v6, &v63);
    v8 = NodeText;
    if ( NodeText < 0 )
    {
      v40 = 1558;
      goto LABEL_88;
    }
    NodeText = MetXmlGetNodeText(L"./DisplayInformation/Description", 0, v6, &v64);
    v8 = NodeText;
    if ( NodeText < 0 )
    {
      v40 = 1561;
      goto LABEL_88;
    }
    NodeText = MetXmlGetNodeText(L"./Verifiable", 0, v6, &v65);
    v8 = NodeText;
    if ( NodeText < 0 )
    {
      v40 = 1564;
      goto LABEL_88;
    }
    NodeText = Package::BlockListed(v2, bstrString, &v66);
    v8 = NodeText;
    if ( NodeText < 0 )
    {
      v40 = 1567;
      goto LABEL_88;
    }
    if ( !v66 && _wcsicmp(String1, L"Not Checked") )
    {
      v20 = _wcsicmp(String1, L"Not Detected");
      v21 = v3;
      if ( !v20 )
        v21 = v4;
      v22 = v20 != 0 ? 1 : 4;
      v23 = operator new(0x60u);
      if ( v23 )
      {
        v23[1] = 0;
        *v23 = &RootCause::`vftable';
        v23[2] = 0;
        *((_DWORD *)v23 + 6) = 1;
        v23[4] = 0;
        v23[5] = 0;
        v23[6] = 0;
        v23[7] = 0;
        *((_DWORD *)v23 + 16) = 0;
        v23[9] = 0;
        *((_DWORD *)v23 + 20) = 0;
        v23[11] = 0;
      }
      else
      {
        v23 = 0;
      }
      v24 = v60;
      v21[v60] = (struct RootCause *)v23;
      if ( !v23 )
      {
        v8 = -2147024882;
        SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "Package::CreateRootCausesFromXml", 1595, -2147024882);
        goto LABEL_81;
      }
      v25 = this;
      if ( !this )
      {
        v8 = -2147024809;
        SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "RootCause::set_Package", 804, -2147024809);
        SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "Package::CreateRootCausesFromXml", 1598, -2147024809);
        goto LABEL_81;
      }
      v26 = v23[11];
      if ( v26 )
      {
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v26 + 16LL))(v26, 0);
        v25 = this;
      }
      v23[11] = v25;
      v27 = RootCause::set_ID(v21[v24], bstrString);
      v8 = v27;
      if ( v27 < 0 )
      {
        SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "Package::CreateRootCausesFromXml", 1601, v27);
        goto LABEL_81;
      }
      v28 = RootCause::set_Name(v21[v24], v63);
      v8 = v28;
      if ( v28 < 0 )
      {
        SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "Package::CreateRootCausesFromXml", 1604, v28);
        goto LABEL_81;
      }
      v29 = RootCause::set_Description(v21[v24], v64);
      v8 = v29;
      if ( v29 < 0 )
      {
        SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "Package::CreateRootCausesFromXml", 1607, v29);
        goto LABEL_81;
      }
      if ( v21 == v3 && !_wcsicmp(v65, L"false") )
        v22 = 3;
      v30 = v21[v24];
      if ( *((_DWORD *)v30 + 16) != 3 )
        *((_DWORD *)v30 + 16) = v22;
      v31 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, const unsigned __int16 *, struct IXMLDOMNode **))v6->lpVtbl->selectSingleNode)(
              v6,
              L"./Parameters",
              &v56);
      v8 = v31;
      if ( v31 < 0 )
      {
        SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "Package::CreateRootCausesFromXml", 1617, v31);
        goto LABEL_81;
      }
      v32 = v22 == 4;
      v2 = (Package *)this;
      if ( !v32 )
      {
        updated = PackageCollection::UpdateAnswers(this[2], (struct Package *)this, v56);
        v8 = updated;
        if ( updated < 0 )
        {
          SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "Package::CreateRootCausesFromXml", 1625, updated);
LABEL_81:
          v4 = v54;
          goto LABEL_90;
        }
      }
      v34 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))v56->lpVtbl->get_xml)(v56, &v57);
      v8 = v34;
      if ( v34 < 0 )
      {
        SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "Package::CreateRootCausesFromXml", 1632, v34);
        goto LABEL_81;
      }
      v35 = RootCause::set_ContextParametersXML(v21[v24], v57);
      v8 = v35;
      if ( v35 < 0 )
      {
        SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "Package::CreateRootCausesFromXml", 1635, v35);
        goto LABEL_81;
      }
      if ( v57 )
      {
        SysFreeString(v57);
        v57 = 0;
      }
      if ( v56 )
      {
        ((void (__fastcall *)(struct IXMLDOMNode *))v56->lpVtbl->Release)(v56);
        v56 = 0;
      }
      v36 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, const wchar_t *, struct IXMLDOMNode **))v6->lpVtbl->selectSingleNode)(
              v6,
              L"./ExtensionPoint",
              &v56);
      v8 = v36;
      if ( v36 < 0 )
      {
        SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "Package::CreateRootCausesFromXml", 1641, v36);
        goto LABEL_81;
      }
      v37 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))v56->lpVtbl->get_xml)(v56, &v57);
      v8 = v37;
      if ( v37 < 0 )
      {
        SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "Package::CreateRootCausesFromXml", 1644, v37);
        goto LABEL_81;
      }
      v38 = RootCause::set_ExtensionXML(v21[v24], v57);
      v8 = v38;
      if ( v38 < 0 )
      {
        SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "Package::CreateRootCausesFromXml", 1647, v38);
        goto LABEL_81;
      }
      ResolutionsFromXml = RootCause::CreateResolutionsFromXml(v21[v24], v6);
      v8 = ResolutionsFromXml;
      if ( ResolutionsFromXml < 0 )
      {
        SdpDebugPrint(
          1u,
          "Met ERROR: %s:%d - hr = 0x%08X\n",
          "Package::CreateRootCausesFromXml",
          1650,
          ResolutionsFromXml);
        goto LABEL_81;
      }
      v4 = v54;
    }
    v16 = v71;
    v17 = v60 + 1;
  }
  v41 = Package::FlattenArray(v15, v3, v16, &v58);
  v8 = v41;
  if ( v41 < 0 )
  {
    SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "Package::CreateRootCausesFromXml", 1658, v41);
    v5 = v58;
    v70 = v58;
    goto LABEL_101;
  }
  v43 = Package::FlattenArray(v42, v4, v71, &v59);
  v8 = v43;
  if ( v43 < 0 )
  {
    SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "Package::CreateRootCausesFromXml", 1661, v43);
    v5 = v58;
    v70 = v58;
LABEL_95:
    v55 = v59;
    goto LABEL_101;
  }
  v5 = v58;
  v70 = v58;
  v44 = Package::MergeRootCauses(v2, v3, v58);
  v8 = v44;
  if ( v44 < 0 )
  {
    SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "Package::CreateRootCausesFromXml", 1664, v44);
    goto LABEL_95;
  }
  v55 = v59;
  v3 = 0;
  v45 = Package::MergeCheckedRootCauses(v2, v4, v59);
  v8 = v45;
  if ( v45 >= 0 )
    v4 = 0;
  else
    SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "Package::CreateRootCausesFromXml", 1669, v45);
LABEL_101:
  if ( v6 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v6->lpVtbl->Release)(v6);
LABEL_103:
  if ( v56 )
  {
    ((void (__fastcall *)(struct IXMLDOMNode *))v56->lpVtbl->Release)(v56);
    v56 = 0;
  }
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v63 )
  {
    SysFreeString(v63);
    v63 = 0;
  }
  if ( v64 )
  {
    SysFreeString(v64);
    v64 = 0;
  }
  if ( String1 )
  {
    SysFreeString(String1);
    String1 = 0;
  }
  if ( v65 )
  {
    SysFreeString(v65);
    v65 = 0;
  }
  if ( v57 )
  {
    SysFreeString(v57);
    v57 = 0;
  }
  if ( v3 )
  {
    v46 = 0;
    if ( v5 )
    {
      do
      {
        v47 = v3[v46];
        if ( v47 )
        {
          (*(void (__fastcall **)(struct RootCause *))(*(_QWORD *)v47 + 16LL))(v47);
          v3[v46] = 0;
        }
        v46 = (unsigned int)(v46 + 1);
      }
      while ( (unsigned int)v46 < v70 );
    }
  }
  if ( v4 )
  {
    for ( i = 0; (unsigned int)i < v55; i = (unsigned int)(i + 1) )
    {
      v49 = v4[i];
      if ( v49 )
      {
        (*(void (__fastcall **)(struct RootCause *))(*(_QWORD *)v49 + 16LL))(v49);
        v4[i] = 0;
      }
    }
  }
  if ( v3 )
  {
    v50 = GetProcessHeap();
    HeapFree(v50, 0, v3);
  }
  if ( v4 )
  {
    v51 = GetProcessHeap();
    HeapFree(v51, 0, v4);
  }
  return v8;
}

```

## disassembly

```asm
0x140057954  mov     [rsp-8+arg_8], rbx
0x140057959  mov     [rsp-8+arg_0], rcx
0x14005795e  push    rbp
0x14005795f  push    rsi
0x140057960  push    rdi
0x140057961  push    r12
0x140057963  push    r13
0x140057965  push    r14
0x140057967  push    r15
0x140057969  lea     rbp, [rsp-27h]
0x14005796e  sub     rsp, 0A0h
0x140057975  xor     edi, edi
0x140057977  lea     r9, [rbp+57h+var_38]; struct IXMLDOMNodeList **
0x14005797b  mov     r15, rcx
0x14005797e  mov     [rbp+57h+arg_10], edi
0x140057981  lea     rcx, aRootcausesRoot; "/Rootcauses/Rootcause"
0x140057988  mov     [rbp+57h+var_98], edi
0x14005798b  xor     r8d, r8d; struct IXMLDOMNode *
0x14005798e  mov     [rbp+57h+var_38], rdi
0x140057992  mov     r13d, edi
0x140057995  mov     [rbp+57h+var_40], rdi
0x140057999  mov     r12d, edi
0x14005799c  mov     [rbp+57h+var_90], rdi
0x1400579a0  mov     r14d, edi
0x1400579a3  mov     [rbp+57h+bstrString], rdi
0x1400579a7  mov     esi, edi
0x1400579a9  mov     [rbp+57h+var_60], rdi
0x1400579ad  mov     [rbp+57h+var_58], rdi
0x1400579b1  mov     [rbp+57h+String1], rdi
0x1400579b5  mov     [rbp+57h+var_50], rdi
0x1400579b9  mov     [rbp+57h+var_88], rdi
0x1400579bd  mov     [rbp+57h+var_48], edi
0x1400579c0  mov     [rbp+57h+arg_18], edi
0x1400579c3  call    ?MetXmlGetNodes@@YAJPEBGPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAUIXMLDOMNodeList@@@Z; MetXmlGetNodes(ushort const *,IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNodeList * *)
0x1400579c8  mov     ebx, eax
0x1400579ca  test    eax, eax
0x1400579cc  jns     short loc_1400579F7
0x1400579ce  mov     r9d, 5ECh
0x1400579d4  mov     [rsp+0D0h+var_B0], eax
0x1400579d8  mov     edi, 1
0x1400579dd  lea     r8, aPackageCreater; "Package::CreateRootCausesFromXml"
0x1400579e4  mov     ecx, edi; Level
0x1400579e6  lea     rdx, aMetErrorSDHr0x; "Met ERROR: %s:%d - hr = 0x%08X\n"
0x1400579ed  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x1400579f2  jmp     loc_14005815F
0x1400579f7  mov     rcx, [rbp+57h+var_38]
0x1400579fb  lea     rdx, [rbp+57h+arg_18]
0x1400579ff  mov     rax, [rcx]
0x140057a02  mov     rax, [rax+40h]
0x140057a06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140057a0b  mov     ebx, eax
0x140057a0d  test    eax, eax
0x140057a0f  jns     short loc_140057A19
0x140057a11  mov     r9d, 5EFh
0x140057a17  jmp     short loc_1400579D4
0x140057a19  movsxd  rbx, [rbp+57h+arg_18]
0x140057a1d  shl     rbx, 3
0x140057a21  call    cs:__imp_GetProcessHeap
0x140057a28  nop     dword ptr [rax+rax+00h]
0x140057a2d  mov     r8, rbx; dwBytes
0x140057a30  mov     edx, 8; dwFlags
0x140057a35  mov     rcx, rax; hHeap
0x140057a38  call    cs:__imp_HeapAlloc
0x140057a3f  nop     dword ptr [rax+rax+00h]
0x140057a44  mov     r13, rax
0x140057a47  test    rax, rax
0x140057a4a  jnz     short loc_140057A62
0x140057a4c  mov     ecx, 8007000Eh
0x140057a51  mov     r9d, 5F5h
0x140057a57  mov     ebx, ecx
0x140057a59  mov     [rsp+0D0h+var_B0], ecx
0x140057a5d  jmp     loc_1400579D8
0x140057a62  movsxd  rbx, [rbp+57h+arg_18]
0x140057a66  shl     rbx, 3
0x140057a6a  call    cs:__imp_GetProcessHeap
0x140057a71  nop     dword ptr [rax+rax+00h]
0x140057a76  mov     r8, rbx; dwBytes
0x140057a79  mov     edx, 8; dwFlags
0x140057a7e  mov     rcx, rax; hHeap
0x140057a81  call    cs:__imp_HeapAlloc
0x140057a88  nop     dword ptr [rax+rax+00h]
0x140057a8d  mov     r8d, [rbp+57h+arg_18]; unsigned int
0x140057a91  mov     edi, 1
0x140057a96  mov     r12, rax
0x140057a99  mov     [rbp+57h+var_A0], rax
0x140057a9d  mov     eax, r8d
0x140057aa0  mov     [rbp+57h+arg_10], r8d
0x140057aa4  mov     [rbp+57h+var_98], eax
0x140057aa7  mov     [rbp+57h+var_7C], eax
0x140057aaa  mov     eax, r14d
0x140057aad  mov     [rbp+57h+var_80], r8d
0x140057ab1  mov     [rbp+57h+var_78], eax
0x140057ab4  cmp     eax, r8d
0x140057ab7  jge     loc_14005804A
0x140057abd  test    rsi, rsi
0x140057ac0  jz      short loc_140057AD5
0x140057ac2  mov     rax, [rsi]
0x140057ac5  mov     rcx, rsi
0x140057ac8  mov     rax, [rax+10h]
0x140057acc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140057ad1  mov     [rbp+57h+var_40], r14
0x140057ad5  mov     rcx, [rbp+57h+var_90]
0x140057ad9  test    rcx, rcx
0x140057adc  jz      short loc_140057AEE
0x140057ade  mov     rax, [rcx]
0x140057ae1  mov     rax, [rax+10h]
0x140057ae5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140057aea  mov     [rbp+57h+var_90], r14
0x140057aee  mov     rcx, [rbp+57h+bstrString]; bstrString
0x140057af2  test    rcx, rcx
0x140057af5  jz      short loc_140057B07
0x140057af7  call    cs:__imp_SysFreeString
0x140057afe  nop     dword ptr [rax+rax+00h]
0x140057b03  mov     [rbp+57h+bstrString], r14
0x140057b07  mov     rcx, [rbp+57h+var_60]; bstrString
0x140057b0b  test    rcx, rcx
0x140057b0e  jz      short loc_140057B20
0x140057b10  call    cs:__imp_SysFreeString
0x140057b17  nop     dword ptr [rax+rax+00h]
0x140057b1c  mov     [rbp+57h+var_60], r14
0x140057b20  mov     rcx, [rbp+57h+var_58]; bstrString
0x140057b24  test    rcx, rcx
0x140057b27  jz      short loc_140057B39
0x140057b29  call    cs:__imp_SysFreeString
0x140057b30  nop     dword ptr [rax+rax+00h]
0x140057b35  mov     [rbp+57h+var_58], r14
0x140057b39  mov     rcx, [rbp+57h+String1]; bstrString
0x140057b3d  test    rcx, rcx
0x140057b40  jz      short loc_140057B52
0x140057b42  call    cs:__imp_SysFreeString
0x140057b49  nop     dword ptr [rax+rax+00h]
0x140057b4e  mov     [rbp+57h+String1], r14
0x140057b52  mov     rcx, [rbp+57h+var_50]; bstrString
0x140057b56  test    rcx, rcx
0x140057b59  jz      short loc_140057B6B
0x140057b5b  call    cs:__imp_SysFreeString
0x140057b62  nop     dword ptr [rax+rax+00h]
0x140057b67  mov     [rbp+57h+var_50], r14
0x140057b6b  mov     rcx, [rbp+57h+var_88]; bstrString
0x140057b6f  test    rcx, rcx
0x140057b72  jz      short loc_140057B84
0x140057b74  call    cs:__imp_SysFreeString
0x140057b7b  nop     dword ptr [rax+rax+00h]
0x140057b80  mov     [rbp+57h+var_88], r14
0x140057b84  mov     rcx, [rbp+57h+var_38]; struct IXMLDOMNodeList *
0x140057b88  lea     rdx, [rbp+57h+var_40]; struct IXMLDOMNode **
0x140057b8c  call    ?MetXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; MetXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x140057b91  mov     ebx, eax
0x140057b93  test    eax, eax
0x140057b95  js      loc_14005801E
0x140057b9b  mov     rsi, [rbp+57h+var_40]
0x140057b9f  lea     r9, [rbp+57h+bstrString]; unsigned __int16 **
0x140057ba3  mov     r8, rsi; struct IXMLDOMNode *
0x140057ba6  lea     rcx, aId_2; "./ID"
0x140057bad  xor     edx, edx; struct IXMLDOMDocument2 *
0x140057baf  call    ?MetXmlGetNodeText@@YAJPEBGPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAG@Z; MetXmlGetNodeText(ushort const *,IXMLDOMDocument2 *,IXMLDOMNode *,ushort * *)
0x140057bb4  mov     ebx, eax
0x140057bb6  test    eax, eax
0x140057bb8  js      loc_140057FFD
0x140057bbe  lea     r9, [rbp+57h+String1]; unsigned __int16 **
0x140057bc2  mov     r8, rsi; struct IXMLDOMNode *
0x140057bc5  xor     edx, edx; struct IXMLDOMDocument2 *
0x140057bc7  lea     rcx, aStatus; "./Status"
0x140057bce  call    ?MetXmlGetNodeText@@YAJPEBGPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAG@Z; MetXmlGetNodeText(ushort const *,IXMLDOMDocument2 *,IXMLDOMNode *,ushort * *)
0x140057bd3  mov     ebx, eax
0x140057bd5  test    eax, eax
0x140057bd7  js      loc_140057FF5
0x140057bdd  lea     r9, [rbp+57h+var_60]; unsigned __int16 **
0x140057be1  mov     r8, rsi; struct IXMLDOMNode *
0x140057be4  xor     edx, edx; struct IXMLDOMDocument2 *
0x140057be6  lea     rcx, aDisplayinforma; "./DisplayInformation/Name"
0x140057bed  call    ?MetXmlGetNodeText@@YAJPEBGPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAG@Z; MetXmlGetNodeText(ushort const *,IXMLDOMDocument2 *,IXMLDOMNode *,ushort * *)
0x140057bf2  mov     ebx, eax
0x140057bf4  test    eax, eax
0x140057bf6  js      loc_140057FED
0x140057bfc  lea     r9, [rbp+57h+var_58]; unsigned __int16 **
0x140057c00  mov     r8, rsi; struct IXMLDOMNode *
0x140057c03  xor     edx, edx; struct IXMLDOMDocument2 *
0x140057c05  lea     rcx, aDisplayinforma_0; "./DisplayInformation/Description"
0x140057c0c  call    ?MetXmlGetNodeText@@YAJPEBGPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAG@Z; MetXmlGetNodeText(ushort const *,IXMLDOMDocument2 *,IXMLDOMNode *,ushort * *)
0x140057c11  mov     ebx, eax
0x140057c13  test    eax, eax
0x140057c15  js      loc_140057FE5
0x140057c1b  lea     r9, [rbp+57h+var_50]; unsigned __int16 **
0x140057c1f  mov     r8, rsi; struct IXMLDOMNode *
0x140057c22  xor     edx, edx; struct IXMLDOMDocument2 *
0x140057c24  lea     rcx, aVerifiable; "./Verifiable"
0x140057c2b  call    ?MetXmlGetNodeText@@YAJPEBGPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAG@Z; MetXmlGetNodeText(ushort const *,IXMLDOMDocument2 *,IXMLDOMNode *,ushort * *)
0x140057c30  mov     ebx, eax
0x140057c32  test    eax, eax
0x140057c34  js      loc_140057FDD
0x140057c3a  mov     rdx, [rbp+57h+bstrString]; unsigned __int16 *
0x140057c3e  lea     r8, [rbp+57h+var_48]; int *
0x140057c42  mov     rcx, r15; this
0x140057c45  call    ?BlockListed@Package@@AEAAJPEBGPEAH@Z; Package::BlockListed(ushort const *,int *)
0x140057c4a  mov     ebx, eax
0x140057c4c  test    eax, eax
0x140057c4e  js      loc_140057FD5
0x140057c54  cmp     [rbp+57h+var_48], r14d
0x140057c58  jnz     loc_140057ED8
0x140057c5e  mov     rcx, [rbp+57h+String1]; String1
0x140057c62  lea     rdx, aNotChecked; "Not Checked"
0x140057c69  call    cs:__imp__wcsicmp
0x140057c70  nop     dword ptr [rax+rax+00h]
0x140057c75  test    eax, eax
0x140057c77  jz      loc_140057ED8
0x140057c7d  mov     rcx, [rbp+57h+String1]; String1
0x140057c81  lea     rdx, aNotDetected; "Not Detected"
0x140057c88  call    cs:__imp__wcsicmp
0x140057c8f  nop     dword ptr [rax+rax+00h]
0x140057c94  mov     r14, r13
0x140057c97  mov     ecx, 60h ; '`'; Size
0x140057c9c  test    eax, eax
0x140057c9e  cmovz   r14, r12
0x140057ca2  neg     eax
0x140057ca4  sbb     r15d, r15d
0x140057ca7  and     r15d, 0FFFFFFFDh
0x140057cab  add     r15d, 4
0x140057caf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140057cb4  xor     edx, edx
0x140057cb6  mov     rbx, rax
0x140057cb9  test    rax, rax
0x140057cbc  jz      short loc_140057CF3
0x140057cbe  lea     rax, ??_7RootCause@@6B@; const RootCause::`vftable'
0x140057cc5  mov     [rbx+8], rdx
0x140057cc9  mov     [rbx], rax
0x140057ccc  mov     [rbx+10h], rdx
0x140057cd0  mov     [rbx+18h], edi
0x140057cd3  mov     [rbx+20h], rdx
0x140057cd7  mov     [rbx+28h], rdx
0x140057cdb  mov     [rbx+30h], rdx
0x140057cdf  mov     [rbx+38h], rdx
0x140057ce3  mov     [rbx+40h], edx
0x140057ce6  mov     [rbx+48h], rdx
0x140057cea  mov     [rbx+50h], edx
0x140057ced  mov     [rbx+58h], rdx
0x140057cf1  jmp     short loc_140057CF6
0x140057cf3  mov     rbx, rdx
0x140057cf6  movsxd  r12, [rbp+57h+var_78]
0x140057cfa  mov     [r14+r12*8], rbx
0x140057cfe  test    rbx, rbx
0x140057d01  jz      loc_140057FA9
0x140057d07  mov     rax, [rbp+57h+arg_0]
0x140057d0b  test    rax, rax
0x140057d0e  jz      loc_140057F79
0x140057d14  mov     rcx, [rbx+58h]
0x140057d18  test    rcx, rcx
0x140057d1b  jz      short loc_140057D2D
0x140057d1d  mov     rax, [rcx]
0x140057d20  mov     rax, [rax+10h]
0x140057d24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140057d29  mov     rax, [rbp+57h+arg_0]
0x140057d2d  mov     [rbx+58h], rax
0x140057d31  mov     rdx, [rbp+57h+bstrString]; unsigned __int16 *
0x140057d35  mov     rcx, [r14+r12*8]; this
0x140057d39  call    ?set_ID@RootCause@@QEAAJPEBG@Z; RootCause::set_ID(ushort const *)
0x140057d3e  mov     ebx, eax
0x140057d40  test    eax, eax
0x140057d42  js      loc_140057F6D
0x140057d48  mov     rdx, [rbp+57h+var_60]; unsigned __int16 *
0x140057d4c  mov     rcx, [r14+r12*8]; this
0x140057d50  call    ?set_Name@RootCause@@QEAAJPEBG@Z; RootCause::set_Name(ushort const *)
0x140057d55  mov     ebx, eax
0x140057d57  test    eax, eax
0x140057d59  js      loc_140057F61
0x140057d5f  mov     rdx, [rbp+57h+var_58]; unsigned __int16 *
0x140057d63  mov     rcx, [r14+r12*8]; this
0x140057d67  call    ?set_Description@RootCause@@QEAAJPEBG@Z; RootCause::set_Description(ushort const *)
0x140057d6c  mov     ebx, eax
0x140057d6e  test    eax, eax
0x140057d70  js      loc_140057F55
0x140057d76  cmp     r14, r13
0x140057d79  jnz     short loc_140057D9D
0x140057d7b  mov     rcx, [rbp+57h+var_50]; String1
0x140057d7f  lea     rdx, aFalse; "false"
0x140057d86  call    cs:__imp__wcsicmp
0x140057d8d  nop     dword ptr [rax+rax+00h]
0x140057d92  test    eax, eax
0x140057d94  mov     eax, 3
0x140057d99  cmovz   r15d, eax
0x140057d9d  mov     rax, [r14+r12*8]
0x140057da1  cmp     dword ptr [rax+40h], 3
0x140057da5  jz      short loc_140057DAB
0x140057da7  mov     [rax+40h], r15d
0x140057dab  mov     rax, [rsi]
0x140057dae  lea     r8, [rbp+57h+var_90]
0x140057db2  lea     rdx, aParameters; "./Parameters"
0x140057db9  mov     rcx, rsi
0x140057dbc  mov     rax, [rax+128h]
0x140057dc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140057dc8  mov     ebx, eax
0x140057dca  test    eax, eax
0x140057dcc  js      loc_140057F49
0x140057dd2  cmp     r15d, 4
0x140057dd6  mov     r15, [rbp+57h+arg_0]
0x140057dda  jz      short loc_140057DF6
0x140057ddc  mov     r8, [rbp+57h+var_90]; struct IXMLDOMNode *
0x140057de0  mov     rdx, r15; struct Package *
0x140057de3  mov     rcx, [r15+10h]; this
0x140057de7  call    ?UpdateAnswers@PackageCollection@@QEAAJPEAVPackage@@PEAUIXMLDOMNode@@@Z; PackageCollection::UpdateAnswers(Package *,IXMLDOMNode *)
  ... truncated ...
```
