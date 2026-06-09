# RootCause::CreateResolutionsFromXml(IXMLDOMNode *)

- ea: `0x14005d144`
- end: `0x14005d82c`
- name: `?CreateResolutionsFromXml@RootCause@@QEAAJPEAUIXMLDOMNode@@@Z`
- size: `1768`
- prototype: `__int64 __fastcall(RootCause *this, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting`

## callers

- `0x140057954`

## callees

- `0x140001d54`
- `0x140020420`
- `0x14005b038`
- `0x14005b190`
- `0x14005b6e4`
- `0x14005d144`
- `0x14005e86c`
- `0x14005e970`
- `0x14005ea0c`
- `0x14005eaa8`
- `0x140063010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x14005d221`
- `KERNEL32!HeapAlloc` at `0x14005d221`
- `KERNEL32!GetProcessHeap` at `0x14005d20a`
- `KERNEL32!GetProcessHeap` at `0x14005d20a`
- `msvcrt!_wcsicmp` at `0x14005d433`
- `msvcrt!_wcsicmp` at `0x14005d478`
- `msvcrt!_wcsicmp` at `0x14005d4d8`
- `msvcrt!_wcsicmp` at `0x14005d433`
- `msvcrt!_wcsicmp` at `0x14005d478`
- `msvcrt!_wcsicmp` at `0x14005d4d8`
- `OLEAUT32!__imp_SysFreeString` at `0x14005d57f`
- `OLEAUT32!__imp_SysFreeString` at `0x14005d598`
- `OLEAUT32!__imp_SysFreeString` at `0x14005d5b1`
- `OLEAUT32!__imp_SysFreeString` at `0x14005d5ca`
- `OLEAUT32!__imp_SysFreeString` at `0x14005d5e3`
- `OLEAUT32!__imp_SysFreeString` at `0x14005d5fc`
- `OLEAUT32!__imp_SysFreeString` at `0x14005d615`
- `OLEAUT32!__imp_SysFreeString` at `0x14005d76c`
- `OLEAUT32!__imp_SysFreeString` at `0x14005d785`
- `OLEAUT32!__imp_SysFreeString` at `0x14005d79e`
- `OLEAUT32!__imp_SysFreeString` at `0x14005d7b7`
- `OLEAUT32!__imp_SysFreeString` at `0x14005d7d0`
- `OLEAUT32!__imp_SysFreeString` at `0x14005d7e9`
- `OLEAUT32!__imp_SysFreeString` at `0x14005d802`
- `OLEAUT32!__imp_SysFreeString` at `0x14005d57f`
- `OLEAUT32!__imp_SysFreeString` at `0x14005d598`
- `OLEAUT32!__imp_SysFreeString` at `0x14005d5b1`
- `OLEAUT32!__imp_SysFreeString` at `0x14005d5ca`
- `OLEAUT32!__imp_SysFreeString` at `0x14005d5e3`
- `OLEAUT32!__imp_SysFreeString` at `0x14005d5fc`
- `OLEAUT32!__imp_SysFreeString` at `0x14005d615`
- `OLEAUT32!__imp_SysFreeString` at `0x14005d76c`
- `OLEAUT32!__imp_SysFreeString` at `0x14005d785`
- `OLEAUT32!__imp_SysFreeString` at `0x14005d79e`
- `OLEAUT32!__imp_SysFreeString` at `0x14005d7b7`
- `OLEAUT32!__imp_SysFreeString` at `0x14005d7d0`
- `OLEAUT32!__imp_SysFreeString` at `0x14005d7e9`
- `OLEAUT32!__imp_SysFreeString` at `0x14005d802`

## string_xrefs

- `0x14005d517`: `./ExtensionPoint`
- `0x14005d1c8`: `RootCause::CreateResolutionsFromXml`
- `0x14005d6c7`: `RootCause::CreateResolutionsFromXml`
- `0x14005d708`: `RootCause::CreateResolutionsFromXml`

## pseudocode

```c
__int64 __fastcall RootCause::CreateResolutionsFromXml(RootCause *this, struct IXMLDOMNode *a2)
{
  struct IXMLDOMNode *v3; // rsi
  int Nodes; // eax
  struct IXMLDOMNodeList *v5; // r13
  unsigned int v6; // edi
  int v7; // r9d
  __int64 v8; // rax
  SIZE_T v9; // rbx
  HANDLE ProcessHeap; // rax
  LPVOID v11; // rax
  int i; // r12d
  int v13; // eax
  _QWORD *v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rdx
  BSTR bstrString; // [rsp+30h] [rbp-50h] BYREF
  BSTR v19; // [rsp+38h] [rbp-48h] BYREF
  BSTR v20; // [rsp+40h] [rbp-40h] BYREF
  wchar_t *String1; // [rsp+48h] [rbp-38h] BYREF
  BSTR v22; // [rsp+50h] [rbp-30h] BYREF
  BSTR v23; // [rsp+58h] [rbp-28h] BYREF
  BSTR v24; // [rsp+60h] [rbp-20h] BYREF
  struct IXMLDOMNode *v25; // [rsp+68h] [rbp-18h] BYREF
  struct IXMLDOMNodeList *v26; // [rsp+70h] [rbp-10h] BYREF
  int v27; // [rsp+D0h] [rbp+50h] BYREF
  __int64 v28; // [rsp+D8h] [rbp+58h] BYREF

  v26 = 0;
  v25 = 0;
  v28 = 0;
  bstrString = 0;
  v3 = 0;
  v19 = 0;
  v20 = 0;
  v22 = 0;
  String1 = 0;
  v23 = 0;
  v24 = 0;
  v27 = 0;
  Nodes = MetXmlGetNodes(L"./Resolutions/Resolution", 0, a2, &v26);
  v5 = v26;
  v6 = Nodes;
  if ( Nodes < 0 )
  {
    v7 = 853;
LABEL_3:
    SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "RootCause::CreateResolutionsFromXml", v7, Nodes);
    goto LABEL_75;
  }
  Nodes = ((__int64 (__fastcall *)(struct IXMLDOMNodeList *, int *))v26->lpVtbl->get_length)(v26, &v27);
  v6 = Nodes;
  if ( Nodes < 0 )
  {
    v7 = 856;
    goto LABEL_3;
  }
  v8 = v27;
  *((_DWORD *)this + 20) = v27;
  v9 = 8 * v8;
  ProcessHeap = GetProcessHeap();
  v11 = HeapAlloc(ProcessHeap, 8u, v9);
  *((_QWORD *)this + 9) = v11;
  if ( !v11 )
  {
    Nodes = -2147024882;
    v7 = 861;
    v6 = -2147024882;
    goto LABEL_3;
  }
  for ( i = 0; i < v27; ++i )
  {
    if ( v3 )
    {
      ((void (__fastcall *)(struct IXMLDOMNode *))v3->lpVtbl->Release)(v3);
      v25 = 0;
    }
    if ( v28 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      v28 = 0;
    }
    v13 = MetXmlNextNode(v5, &v25);
    v6 = v13;
    if ( v13 < 0 )
    {
      SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "RootCause::CreateResolutionsFromXml", 871, v13);
      v3 = v25;
      break;
    }
    v3 = v25;
    Nodes = MetXmlGetNodeText(L"./ID", 0, v25, &bstrString);
    v6 = Nodes;
    if ( Nodes < 0 )
    {
      v7 = 874;
      goto LABEL_3;
    }
    Nodes = MetXmlGetNodeText(L"./DisplayInformation/Name", 0, v3, &v19);
    v6 = Nodes;
    if ( Nodes < 0 )
    {
      v7 = 877;
      goto LABEL_3;
    }
    Nodes = MetXmlGetNodeText(L"./DisplayInformation/Description", 0, v3, &v20);
    v6 = Nodes;
    if ( Nodes < 0 )
    {
      v7 = 880;
      goto LABEL_3;
    }
    v14 = operator new(0x60u);
    if ( v14 )
    {
      v14[1] = 0;
      *v14 = &Resolution::`vftable';
      v14[2] = 0;
      *((_DWORD *)v14 + 6) = 1;
      v14[4] = 0;
      v14[5] = 0;
      v14[6] = 0;
      v14[7] = 0;
      v14[8] = 0;
      v14[9] = 0;
      v14[10] = 0;
      *((_DWORD *)v14 + 22) = 0;
    }
    else
    {
      v14 = 0;
    }
    *(_QWORD *)(*((_QWORD *)this + 9) + 8LL * i) = v14;
    v15 = *(_QWORD *)(*((_QWORD *)this + 9) + 8LL * i);
    if ( !v15 )
    {
      Nodes = -2147024882;
      v7 = 886;
      v6 = -2147024882;
      goto LABEL_3;
    }
    *(_QWORD *)(v15 + 72) = this;
    v16 = *((_QWORD *)this + 11);
    if ( !v16 )
    {
      v6 = -2147024809;
      SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "Resolution::set_Package", 813, -2147024809);
      SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "RootCause::CreateResolutionsFromXml", 892, -2147024809);
      break;
    }
    *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 9) + 8LL * i) + 80LL) = v16;
    Nodes = Resolution::set_ID(*(Resolution **)(*((_QWORD *)this + 9) + 8LL * i), bstrString);
    v6 = Nodes;
    if ( Nodes < 0 )
    {
      v7 = 895;
      goto LABEL_3;
    }
    Nodes = Resolution::set_Name(*(Resolution **)(*((_QWORD *)this + 9) + 8LL * i), v19);
    v6 = Nodes;
    if ( Nodes < 0 )
    {
      v7 = 898;
      goto LABEL_3;
    }
    Nodes = Resolution::set_Description(*(Resolution **)(*((_QWORD *)this + 9) + 8LL * i), v20);
    v6 = Nodes;
    if ( Nodes < 0 )
    {
      v7 = 901;
      goto LABEL_3;
    }
    Nodes = ((__int64 (__fastcall *)(struct IXMLDOMNode *, const wchar_t *, __int64 *))v3->lpVtbl->selectSingleNode)(
              v3,
              L"./Script/RequiresInteractivity",
              &v28);
    v6 = Nodes;
    if ( Nodes )
    {
      if ( Nodes == 1 )
      {
        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 9) + 8LL * i) + 68LL) = 1;
      }
      else if ( Nodes < 0 )
      {
        v7 = 934;
        goto LABEL_3;
      }
    }
    else
    {
      Nodes = (*(__int64 (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v28 + 208LL))(v28, &String1);
      v6 = Nodes;
      if ( Nodes < 0 )
      {
        v7 = 913;
        goto LABEL_3;
      }
      if ( !_wcsicmp(String1, L"true") )
        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 9) + 8LL * i) + 64LL) = 1;
      Nodes = MetXmlGetNodeText(L"./Script/RequiresElevation", 0, v3, &v23);
      v6 = Nodes;
      if ( Nodes < 0 )
      {
        v7 = 924;
        goto LABEL_3;
      }
      if ( !_wcsicmp(v23, L"true") )
        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 9) + 8LL * i) + 56LL) = 1;
    }
    Nodes = MetXmlGetNodeText(L"./RequiresConsent", 0, v3, &v22);
    v6 = Nodes;
    if ( Nodes < 0 )
    {
      v7 = 940;
      goto LABEL_3;
    }
    if ( !_wcsicmp(v22, L"true") )
      *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 9) + 8LL * i) + 60LL) = 1;
    if ( v28 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      v28 = 0;
    }
    Nodes = ((__int64 (__fastcall *)(struct IXMLDOMNode *, const wchar_t *, __int64 *))v3->lpVtbl->selectSingleNode)(
              v3,
              L"./ExtensionPoint",
              &v28);
    v6 = Nodes;
    if ( Nodes < 0 )
    {
      v7 = 950;
      goto LABEL_3;
    }
    Nodes = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v28 + 272LL))(v28, &v24);
    v6 = Nodes;
    if ( Nodes < 0 )
    {
      v7 = 953;
      goto LABEL_3;
    }
    Nodes = Resolution::set_ExtensionXML(*(Resolution **)(*((_QWORD *)this + 9) + 8LL * i), v24);
    v6 = Nodes;
    if ( Nodes < 0 )
    {
      v7 = 956;
      goto LABEL_3;
    }
    if ( bstrString )
    {
      SysFreeString(bstrString);
      bstrString = 0;
    }
    if ( v19 )
    {
      SysFreeString(v19);
      v19 = 0;
    }
    if ( v20 )
    {
      SysFreeString(v20);
      v20 = 0;
    }
    if ( String1 )
    {
      SysFreeString(String1);
      String1 = 0;
    }
    if ( v22 )
    {
      SysFreeString(v22);
      v22 = 0;
    }
    if ( v23 )
    {
      SysFreeString(v23);
      v23 = 0;
    }
    if ( v24 )
    {
      SysFreeString(v24);
      v24 = 0;
    }
  }
LABEL_75:
  if ( v5 )
    ((void (__fastcall *)(struct IXMLDOMNodeList *))v5->lpVtbl->Release)(v5);
  if ( v3 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v3->lpVtbl->Release)(v3);
  if ( v28 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    v28 = 0;
  }
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v19 )
  {
    SysFreeString(v19);
    v19 = 0;
  }
  if ( v20 )
  {
    SysFreeString(v20);
    v20 = 0;
  }
  if ( String1 )
  {
    SysFreeString(String1);
    String1 = 0;
  }
  if ( v22 )
  {
    SysFreeString(v22);
    v22 = 0;
  }
  if ( v23 )
  {
    SysFreeString(v23);
    v23 = 0;
  }
  if ( v24 )
    SysFreeString(v24);
  return v6;
}

```

## disassembly

```asm
0x14005d144  mov     [rsp-38h+arg_0], rbx
0x14005d149  push    rbp
0x14005d14a  push    rsi
0x14005d14b  push    rdi
0x14005d14c  push    r12
0x14005d14e  push    r13
0x14005d150  push    r14
0x14005d152  push    r15
0x14005d154  mov     rbp, rsp
0x14005d157  sub     rsp, 80h
0x14005d15e  xor     r14d, r14d
0x14005d161  lea     r9, [rbp+var_10]; struct IXMLDOMNodeList **
0x14005d165  mov     r15, rcx
0x14005d168  mov     [rbp+var_10], r14
0x14005d16c  mov     r8, rdx; struct IXMLDOMNode *
0x14005d16f  mov     [rbp+var_18], r14
0x14005d173  xor     edx, edx; struct IXMLDOMDocument2 *
0x14005d175  mov     [rbp+arg_18], r14
0x14005d179  lea     rcx, aResolutionsRes; "./Resolutions/Resolution"
0x14005d180  mov     [rbp+bstrString], r14
0x14005d184  mov     esi, r14d
0x14005d187  mov     [rbp+var_48], r14
0x14005d18b  mov     [rbp+var_40], r14
0x14005d18f  mov     [rbp+var_30], r14
0x14005d193  mov     [rbp+String1], r14
0x14005d197  mov     [rbp+var_28], r14
0x14005d19b  mov     [rbp+var_20], r14
0x14005d19f  mov     [rbp+arg_10], r14d
0x14005d1a3  call    ?MetXmlGetNodes@@YAJPEBGPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAUIXMLDOMNodeList@@@Z; MetXmlGetNodes(ushort const *,IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNodeList * *)
0x14005d1a8  mov     r13, [rbp+var_10]
0x14005d1ac  mov     edi, eax
0x14005d1ae  test    eax, eax
0x14005d1b0  jns     short loc_14005D1D9
0x14005d1b2  mov     r9d, 355h
0x14005d1b8  mov     ecx, 1; Level
0x14005d1bd  lea     rdx, aMetErrorSDHr0x; "Met ERROR: %s:%d - hr = 0x%08X\n"
0x14005d1c4  mov     [rsp+80h+var_60], eax
0x14005d1c8  lea     r8, aRootcauseCreat; "RootCause::CreateResolutionsFromXml"
0x14005d1cf  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14005d1d4  jmp     loc_14005D721
0x14005d1d9  mov     rax, [r13+0]
0x14005d1dd  lea     rdx, [rbp+arg_10]
0x14005d1e1  mov     rcx, r13
0x14005d1e4  mov     rax, [rax+40h]
0x14005d1e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005d1ed  mov     edi, eax
0x14005d1ef  test    eax, eax
0x14005d1f1  jns     short loc_14005D1FB
0x14005d1f3  mov     r9d, 358h
0x14005d1f9  jmp     short loc_14005D1B8
0x14005d1fb  movsxd  rax, [rbp+arg_10]
0x14005d1ff  mov     rbx, rax
0x14005d202  mov     [r15+50h], eax
0x14005d206  shl     rbx, 3
0x14005d20a  call    cs:__imp_GetProcessHeap
0x14005d211  nop     dword ptr [rax+rax+00h]
0x14005d216  mov     r8, rbx; dwBytes
0x14005d219  mov     edx, 8; dwFlags
0x14005d21e  mov     rcx, rax; hHeap
0x14005d221  call    cs:__imp_HeapAlloc
0x14005d228  nop     dword ptr [rax+rax+00h]
0x14005d22d  mov     [r15+48h], rax
0x14005d231  test    rax, rax
0x14005d234  jnz     short loc_14005D248
0x14005d236  mov     eax, 8007000Eh
0x14005d23b  mov     r9d, 35Dh
0x14005d241  mov     edi, eax
0x14005d243  jmp     loc_14005D1B8
0x14005d248  mov     r12d, r14d
0x14005d24b  mov     ebx, 1
0x14005d250  cmp     r12d, [rbp+arg_10]
0x14005d254  jge     loc_14005D721
0x14005d25a  test    rsi, rsi
0x14005d25d  jz      short loc_14005D272
0x14005d25f  mov     rax, [rsi]
0x14005d262  mov     rcx, rsi
0x14005d265  mov     rax, [rax+10h]
0x14005d269  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005d26e  mov     [rbp+var_18], r14
0x14005d272  mov     rcx, [rbp+arg_18]
0x14005d276  test    rcx, rcx
0x14005d279  jz      short loc_14005D28B
0x14005d27b  mov     rax, [rcx]
0x14005d27e  mov     rax, [rax+10h]
0x14005d282  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005d287  mov     [rbp+arg_18], r14
0x14005d28b  lea     rdx, [rbp+var_18]; struct IXMLDOMNode **
0x14005d28f  mov     rcx, r13; struct IXMLDOMNodeList *
0x14005d292  call    ?MetXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; MetXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x14005d297  mov     edi, eax
0x14005d299  test    eax, eax
0x14005d29b  js      loc_14005D6FE
0x14005d2a1  mov     rsi, [rbp+var_18]
0x14005d2a5  lea     r9, [rbp+bstrString]; unsigned __int16 **
0x14005d2a9  mov     r8, rsi; struct IXMLDOMNode *
0x14005d2ac  lea     rcx, aId_2; "./ID"
0x14005d2b3  xor     edx, edx; struct IXMLDOMDocument2 *
0x14005d2b5  call    ?MetXmlGetNodeText@@YAJPEBGPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAG@Z; MetXmlGetNodeText(ushort const *,IXMLDOMDocument2 *,IXMLDOMNode *,ushort * *)
0x14005d2ba  mov     edi, eax
0x14005d2bc  test    eax, eax
0x14005d2be  js      loc_14005D6F1
0x14005d2c4  lea     r9, [rbp+var_48]; unsigned __int16 **
0x14005d2c8  mov     r8, rsi; struct IXMLDOMNode *
0x14005d2cb  xor     edx, edx; struct IXMLDOMDocument2 *
0x14005d2cd  lea     rcx, aDisplayinforma; "./DisplayInformation/Name"
0x14005d2d4  call    ?MetXmlGetNodeText@@YAJPEBGPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAG@Z; MetXmlGetNodeText(ushort const *,IXMLDOMDocument2 *,IXMLDOMNode *,ushort * *)
0x14005d2d9  mov     edi, eax
0x14005d2db  test    eax, eax
0x14005d2dd  js      loc_14005D6E9
0x14005d2e3  lea     r9, [rbp+var_40]; unsigned __int16 **
0x14005d2e7  mov     r8, rsi; struct IXMLDOMNode *
0x14005d2ea  xor     edx, edx; struct IXMLDOMDocument2 *
0x14005d2ec  lea     rcx, aDisplayinforma_0; "./DisplayInformation/Description"
0x14005d2f3  call    ?MetXmlGetNodeText@@YAJPEBGPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAG@Z; MetXmlGetNodeText(ushort const *,IXMLDOMDocument2 *,IXMLDOMNode *,ushort * *)
0x14005d2f8  mov     edi, eax
0x14005d2fa  test    eax, eax
0x14005d2fc  js      loc_14005D6E1
0x14005d302  mov     ecx, 60h ; '`'; Size
0x14005d307  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14005d30c  mov     rcx, rax
0x14005d30f  test    rax, rax
0x14005d312  jz      short loc_14005D353
0x14005d314  lea     rax, ??_7Resolution@@6B@; const Resolution::`vftable'
0x14005d31b  mov     [rcx+8], r14
0x14005d31f  mov     [rcx], rax
0x14005d322  mov     [rcx+10h], r14
0x14005d326  mov     [rcx+18h], ebx
0x14005d329  mov     [rcx+20h], r14
0x14005d32d  mov     [rcx+28h], r14
0x14005d331  mov     [rcx+30h], r14
0x14005d335  mov     qword ptr [rcx+38h], 0
0x14005d33d  mov     qword ptr [rcx+40h], 0
0x14005d345  mov     [rcx+48h], r14
0x14005d349  mov     [rcx+50h], r14
0x14005d34d  mov     [rcx+58h], r14d
0x14005d351  jmp     short loc_14005D356
0x14005d353  mov     rcx, r14
0x14005d356  mov     rax, [r15+48h]
0x14005d35a  movsxd  r14, r12d
0x14005d35d  mov     [rax+r14*8], rcx
0x14005d361  mov     rax, [r15+48h]
0x14005d365  mov     rcx, [rax+r14*8]
0x14005d369  test    rcx, rcx
0x14005d36c  jz      loc_14005D6B6
0x14005d372  mov     [rcx+48h], r15
0x14005d376  mov     rdx, [r15+58h]
0x14005d37a  test    rdx, rdx
0x14005d37d  jz      loc_14005D686
0x14005d383  mov     rax, [r15+48h]
0x14005d387  mov     rcx, [rax+r14*8]
0x14005d38b  mov     [rcx+50h], rdx
0x14005d38f  mov     rcx, [r15+48h]
0x14005d393  mov     rdx, [rbp+bstrString]; unsigned __int16 *
0x14005d397  mov     rcx, [rcx+r14*8]; this
0x14005d39b  call    ?set_ID@Resolution@@QEAAJPEBG@Z; Resolution::set_ID(ushort const *)
0x14005d3a0  mov     edi, eax
0x14005d3a2  test    eax, eax
0x14005d3a4  js      loc_14005D67E
0x14005d3aa  mov     rcx, [r15+48h]
0x14005d3ae  mov     rdx, [rbp+var_48]; unsigned __int16 *
0x14005d3b2  mov     rcx, [rcx+r14*8]; this
0x14005d3b6  call    ?set_Name@Resolution@@QEAAJPEBG@Z; Resolution::set_Name(ushort const *)
0x14005d3bb  mov     edi, eax
0x14005d3bd  test    eax, eax
0x14005d3bf  js      loc_14005D676
0x14005d3c5  mov     rcx, [r15+48h]
0x14005d3c9  mov     rdx, [rbp+var_40]; unsigned __int16 *
0x14005d3cd  mov     rcx, [rcx+r14*8]; this
0x14005d3d1  call    ?set_Description@Resolution@@QEAAJPEBG@Z; Resolution::set_Description(ushort const *)
0x14005d3d6  mov     edi, eax
0x14005d3d8  test    eax, eax
0x14005d3da  js      loc_14005D66E
0x14005d3e0  mov     rax, [rsi]
0x14005d3e3  lea     r8, [rbp+arg_18]
0x14005d3e7  lea     rdx, aScriptRequires_0; "./Script/RequiresInteractivity"
0x14005d3ee  mov     rcx, rsi
0x14005d3f1  mov     rax, [rax+128h]
0x14005d3f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005d3fd  mov     edi, eax
0x14005d3ff  test    eax, eax
0x14005d401  jnz     loc_14005D495
0x14005d407  mov     rcx, [rbp+arg_18]
0x14005d40b  lea     rdx, [rbp+String1]
0x14005d40f  mov     rax, [rcx]
0x14005d412  mov     rax, [rax+0D0h]
0x14005d419  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005d41e  mov     edi, eax
0x14005d420  test    eax, eax
0x14005d422  js      loc_14005D638
0x14005d428  mov     rcx, [rbp+String1]; String1
0x14005d42c  lea     rdx, aTrue; "true"
0x14005d433  call    cs:__imp__wcsicmp
0x14005d43a  nop     dword ptr [rax+rax+00h]
0x14005d43f  test    eax, eax
0x14005d441  jnz     short loc_14005D44E
0x14005d443  mov     rax, [r15+48h]
0x14005d447  mov     rcx, [rax+r14*8]
0x14005d44b  mov     [rcx+40h], ebx
0x14005d44e  lea     r9, [rbp+var_28]; unsigned __int16 **
0x14005d452  mov     r8, rsi; struct IXMLDOMNode *
0x14005d455  xor     edx, edx; struct IXMLDOMDocument2 *
0x14005d457  lea     rcx, aScriptRequires; "./Script/RequiresElevation"
0x14005d45e  call    ?MetXmlGetNodeText@@YAJPEBGPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAG@Z; MetXmlGetNodeText(ushort const *,IXMLDOMDocument2 *,IXMLDOMNode *,ushort * *)
0x14005d463  mov     edi, eax
0x14005d465  test    eax, eax
0x14005d467  js      loc_14005D62D
0x14005d46d  mov     rcx, [rbp+var_28]; String1
0x14005d471  lea     rdx, aTrue; "true"
0x14005d478  call    cs:__imp__wcsicmp
0x14005d47f  nop     dword ptr [rax+rax+00h]
0x14005d484  test    eax, eax
0x14005d486  jnz     short loc_14005D4AE
0x14005d488  mov     rax, [r15+48h]
0x14005d48c  mov     rcx, [rax+r14*8]
0x14005d490  mov     [rcx+38h], ebx
0x14005d493  jmp     short loc_14005D4AE
0x14005d495  cmp     eax, ebx
0x14005d497  jnz     short loc_14005D4A6
0x14005d499  mov     rax, [r15+48h]
0x14005d49d  mov     rcx, [rax+r14*8]
0x14005d4a1  mov     [rcx+44h], ebx
0x14005d4a4  jmp     short loc_14005D4AE
0x14005d4a6  test    eax, eax
0x14005d4a8  js      loc_14005D666
0x14005d4ae  lea     r9, [rbp+var_30]; unsigned __int16 **
0x14005d4b2  mov     r8, rsi; struct IXMLDOMNode *
0x14005d4b5  xor     edx, edx; struct IXMLDOMDocument2 *
0x14005d4b7  lea     rcx, aRequiresconsen; "./RequiresConsent"
0x14005d4be  call    ?MetXmlGetNodeText@@YAJPEBGPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAG@Z; MetXmlGetNodeText(ushort const *,IXMLDOMDocument2 *,IXMLDOMNode *,ushort * *)
0x14005d4c3  mov     edi, eax
0x14005d4c5  test    eax, eax
0x14005d4c7  js      loc_14005D65E
0x14005d4cd  mov     rcx, [rbp+var_30]; String1
0x14005d4d1  lea     rdx, aTrue; "true"
0x14005d4d8  call    cs:__imp__wcsicmp
0x14005d4df  nop     dword ptr [rax+rax+00h]
0x14005d4e4  test    eax, eax
0x14005d4e6  jnz     short loc_14005D4F3
0x14005d4e8  mov     rax, [r15+48h]
0x14005d4ec  mov     rcx, [rax+r14*8]
0x14005d4f0  mov     [rcx+3Ch], ebx
0x14005d4f3  mov     rcx, [rbp+arg_18]
0x14005d4f7  test    rcx, rcx
0x14005d4fa  jz      short loc_14005D510
0x14005d4fc  mov     rax, [rcx]
0x14005d4ff  mov     rax, [rax+10h]
0x14005d503  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005d508  mov     [rbp+arg_18], 0
0x14005d510  mov     rax, [rsi]
0x14005d513  lea     r8, [rbp+arg_18]
0x14005d517  lea     rdx, aExtensionpoint_17; "./ExtensionPoint"
0x14005d51e  mov     rcx, rsi
0x14005d521  mov     rax, [rax+128h]
0x14005d528  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005d52d  mov     edi, eax
0x14005d52f  test    eax, eax
0x14005d531  js      loc_14005D656
0x14005d537  mov     rcx, [rbp+arg_18]
0x14005d53b  lea     rdx, [rbp+var_20]
0x14005d53f  mov     rax, [rcx]
0x14005d542  mov     rax, [rax+110h]
0x14005d549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005d54e  mov     edi, eax
0x14005d550  test    eax, eax
0x14005d552  js      loc_14005D64E
0x14005d558  mov     rcx, [r15+48h]
0x14005d55c  mov     rdx, [rbp+var_20]; unsigned __int16 *
0x14005d560  mov     rcx, [rcx+r14*8]; this
0x14005d564  call    ?set_ExtensionXML@Resolution@@QEAAJPEBG@Z; Resolution::set_ExtensionXML(ushort const *)
0x14005d569  xor     r14d, r14d
0x14005d56c  mov     edi, eax
0x14005d56e  test    eax, eax
0x14005d570  js      loc_14005D643
0x14005d576  mov     rcx, [rbp+bstrString]; bstrString
0x14005d57a  test    rcx, rcx
0x14005d57d  jz      short loc_14005D58F
0x14005d57f  call    cs:__imp_SysFreeString
0x14005d586  nop     dword ptr [rax+rax+00h]
0x14005d58b  mov     [rbp+bstrString], r14
0x14005d58f  mov     rcx, [rbp+var_48]; bstrString
0x14005d593  test    rcx, rcx
0x14005d596  jz      short loc_14005D5A8
0x14005d598  call    cs:__imp_SysFreeString
0x14005d59f  nop     dword ptr [rax+rax+00h]
0x14005d5a4  mov     [rbp+var_48], r14
0x14005d5a8  mov     rcx, [rbp+var_40]; bstrString
0x14005d5ac  test    rcx, rcx
0x14005d5af  jz      short loc_14005D5C1
0x14005d5b1  call    cs:__imp_SysFreeString
0x14005d5b8  nop     dword ptr [rax+rax+00h]
0x14005d5bd  mov     [rbp+var_40], r14
0x14005d5c1  mov     rcx, [rbp+String1]; bstrString
0x14005d5c5  test    rcx, rcx
0x14005d5c8  jz      short loc_14005D5DA
0x14005d5ca  call    cs:__imp_SysFreeString
0x14005d5d1  nop     dword ptr [rax+rax+00h]
0x14005d5d6  mov     [rbp+String1], r14
0x14005d5da  mov     rcx, [rbp+var_30]; bstrString
0x14005d5de  test    rcx, rcx
0x14005d5e1  jz      short loc_14005D5F3
  ... truncated ...
```
