# EditPage::Initialize(IXMLDOMDocument2 *)

- ea: `0x14002bdd0`
- end: `0x14002c4bd`
- name: `?Initialize@EditPage@@UEAAJPEAUIXMLDOMDocument2@@@Z`
- size: `1773`
- prototype: `__int64 __fastcall(EditPage *__hidden this, struct IXMLDOMDocument2 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x140001d54`
- `0x140020420`
- `0x140021628`
- `0x140021974`
- `0x14002bdd0`
- `0x14002c4d0`
- `0x1400310d8`
- `0x14004270c`
- `0x140044700`
- `0x140063010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14002c496`
- `KERNEL32!HeapFree` at `0x14002c496`
- `KERNEL32!GetProcessHeap` at `0x14002c482`
- `KERNEL32!GetProcessHeap` at `0x14002c482`
- `msvcrt!_wcsicmp` at `0x14002bf09`
- `msvcrt!_wcsicmp` at `0x14002c160`
- `msvcrt!_wcsicmp` at `0x14002c186`
- `msvcrt!_wcsicmp` at `0x14002c389`
- `msvcrt!_wcsicmp` at `0x14002c3af`
- `msvcrt!_wcsicmp` at `0x14002bf09`
- `msvcrt!_wcsicmp` at `0x14002c160`
- `msvcrt!_wcsicmp` at `0x14002c186`
- `msvcrt!_wcsicmp` at `0x14002c389`
- `msvcrt!_wcsicmp` at `0x14002c3af`
- `OLEAUT32!__imp_SysAllocString` at `0x14002c0a3`
- `OLEAUT32!__imp_SysAllocString` at `0x14002c1d2`
- `OLEAUT32!__imp_SysAllocString` at `0x14002c27f`
- `OLEAUT32!__imp_SysAllocString` at `0x14002c2e3`
- `OLEAUT32!__imp_SysAllocString` at `0x14002c32c`
- `OLEAUT32!__imp_SysAllocString` at `0x14002c0a3`
- `OLEAUT32!__imp_SysAllocString` at `0x14002c1d2`
- `OLEAUT32!__imp_SysAllocString` at `0x14002c27f`
- `OLEAUT32!__imp_SysAllocString` at `0x14002c2e3`
- `OLEAUT32!__imp_SysAllocString` at `0x14002c32c`
- `OLEAUT32!__imp_SysFreeString` at `0x14002bf23`
- `OLEAUT32!__imp_SysFreeString` at `0x14002c08d`
- `OLEAUT32!__imp_SysFreeString` at `0x14002c26c`
- `OLEAUT32!__imp_SysFreeString` at `0x14002c319`
- `OLEAUT32!__imp_SysFreeString` at `0x14002c440`
- `OLEAUT32!__imp_SysFreeString` at `0x14002c458`
- `OLEAUT32!__imp_SysFreeString` at `0x14002c46d`
- `OLEAUT32!__imp_SysFreeString` at `0x14002bf23`
- `OLEAUT32!__imp_SysFreeString` at `0x14002c08d`
- `OLEAUT32!__imp_SysFreeString` at `0x14002c26c`
- `OLEAUT32!__imp_SysFreeString` at `0x14002c319`
- `OLEAUT32!__imp_SysFreeString` at `0x14002c440`
- `OLEAUT32!__imp_SysFreeString` at `0x14002c458`
- `OLEAUT32!__imp_SysFreeString` at `0x14002c46d`
- `OLEAUT32!__imp_VariantInit` at `0x14002be26`
- `OLEAUT32!__imp_VariantInit` at `0x14002be26`
- `OLEAUT32!__imp_VariantClear` at `0x14002c25d`
- `OLEAUT32!__imp_VariantClear` at `0x14002c30a`
- `OLEAUT32!__imp_VariantClear` at `0x14002c3c9`
- `OLEAUT32!__imp_VariantClear` at `0x14002c25d`
- `OLEAUT32!__imp_VariantClear` at `0x14002c30a`
- `OLEAUT32!__imp_VariantClear` at `0x14002c3c9`

## string_xrefs

- `0x14002bfcb`: `./ExtensionPoint/Default`
- `0x14002c100`: `./ExtensionPoint/Browse`
- `0x14002c159`: `Computer`
- `0x14002c278`: `FilterExtension`

## pseudocode

```c
__int64 __fastcall EditPage::Initialize(EditPage *this, struct IXMLDOMDocument2 *a2)
{
  struct IXMLDOMNode *v3; // r12
  OLECHAR *v4; // r15
  OLECHAR *v5; // r13
  int Node; // eax
  unsigned int v8; // ebx
  int v9; // r9d
  int RootNode; // eax
  BSTR *v11; // r14
  int v12; // edi
  _QWORD *v13; // rax
  int ResourceString; // eax
  const unsigned __int16 **v15; // r14
  int v16; // eax
  BSTR v17; // rax
  __int64 (__fastcall ***v18)(_QWORD, GUID *, __int64 *); // rcx
  BSTR v19; // rax
  __int64 v20; // r14
  __int64 v21; // rax
  BSTR v22; // rax
  BSTR v23; // rax
  BSTR v24; // rax
  HANDLE ProcessHeap; // rax
  int v27; // [rsp+20h] [rbp-50h]
  wchar_t *String1; // [rsp+30h] [rbp-40h] BYREF
  __int64 (__fastcall ***v29)(_QWORD, GUID *, _QWORD *); // [rsp+38h] [rbp-38h] BYREF
  BSTR bstrString; // [rsp+40h] [rbp-30h] BYREF
  struct IXMLDOMNode *v31; // [rsp+48h] [rbp-28h] BYREF
  OLECHAR *psz; // [rsp+50h] [rbp-20h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-18h] BYREF
  struct IXMLDOMNode *v34; // [rsp+C0h] [rbp+50h] BYREF
  __int64 v35; // [rsp+C8h] [rbp+58h] BYREF

  v34 = 0;
  v29 = 0;
  v35 = 0;
  v3 = 0;
  v31 = 0;
  String1 = 0;
  v4 = 0;
  bstrString = 0;
  v5 = 0;
  psz = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  Node = InteractivityPage::Initialize(this, a2);
  v8 = Node;
  if ( Node < 0 )
  {
    v9 = 1265;
LABEL_3:
    v27 = Node;
LABEL_4:
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "EditPage::Initialize", v9, v27);
    goto LABEL_81;
  }
  RootNode = DwzXmlGetRootNode(a2, (struct IXMLDOMElement **)&v31);
  v8 = RootNode;
  if ( RootNode < 0 )
  {
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "EditPage::Initialize", 1268, RootNode);
    v3 = v31;
    goto LABEL_81;
  }
  v3 = v31;
  Node = DwzXmlGetNode(L"./RegularExpression", 0, v31, &v34);
  v8 = Node;
  if ( Node < 0 )
  {
    v9 = 1271;
    goto LABEL_3;
  }
  v11 = (BSTR *)((char *)this + 184);
  Node = ((__int64 (__fastcall *)(struct IXMLDOMNode *, char *))v34->lpVtbl->get_text)(v34, (char *)this + 184);
  v8 = Node;
  if ( Node < 0 )
  {
    v9 = 1274;
    goto LABEL_3;
  }
  if ( !_wcsicmp(*v11, &word_14006B9B8) && *v11 )
  {
    SysFreeString(*v11);
    *v11 = 0;
  }
  v12 = 1;
  if ( *v11 )
  {
    v13 = operator new(0x38u);
    if ( v13 )
    {
      v13[1] = 0;
      v13[2] = 0;
      v13[3] = 0;
      *((_DWORD *)v13 + 8) = 0;
      v13[5] = 0;
      *((_DWORD *)v13 + 12) = 1;
      *(_DWORD *)v13 = 0;
    }
    else
    {
      v13 = 0;
    }
    *((_QWORD *)this + 27) = v13;
    if ( !v13 )
    {
      v9 = 1283;
LABEL_20:
      ResourceString = -2147024882;
      v8 = -2147024882;
LABEL_21:
      v27 = ResourceString;
      goto LABEL_4;
    }
    if ( (unsigned int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Parse(v13, *v11) )
    {
      v8 = -2147467259;
      v9 = 1287;
      v27 = -2147467259;
      goto LABEL_4;
    }
  }
  if ( v34 )
  {
    ((void (__fastcall *)(struct IXMLDOMNode *))v34->lpVtbl->Release)(v34);
    v34 = 0;
  }
  ResourceString = ((__int64 (__fastcall *)(struct IXMLDOMNode *, const wchar_t *, struct IXMLDOMNode **))v3->lpVtbl->selectSingleNode)(
                     v3,
                     L"./ExtensionPoint/Default",
                     &v34);
  v8 = ResourceString;
  if ( ResourceString < 0 )
  {
    v9 = 1297;
    goto LABEL_21;
  }
  if ( !ResourceString )
  {
    ResourceString = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))v34->lpVtbl->get_text)(v34, &bstrString);
    v8 = ResourceString;
    if ( ResourceString < 0 )
    {
      v9 = 1301;
      goto LABEL_21;
    }
    v15 = (const unsigned __int16 **)((char *)this + 192);
    ResourceString = DwzTryLoadResourceString(bstrString, (unsigned __int16 **)this + 24);
    v8 = ResourceString;
    if ( ResourceString < 0 )
    {
      v9 = 1304;
      goto LABEL_21;
    }
    v16 = DwzSubstituteXmlParameters(&psz, *v15, *((struct IXMLDOMNode **)this + 20));
    v8 = v16;
    if ( v16 < 0 )
    {
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "EditPage::Initialize", 1310, v16);
      v5 = psz;
      goto LABEL_81;
    }
    if ( *v15 )
    {
      SysFreeString((BSTR)*v15);
      *v15 = 0;
    }
    v5 = psz;
    v17 = SysAllocString(psz);
    *v15 = v17;
    if ( !v17 )
    {
      v9 = 1314;
      goto LABEL_20;
    }
  }
  if ( v34 )
  {
    ((void (__fastcall *)(struct IXMLDOMNode *))v34->lpVtbl->Release)(v34);
    v34 = 0;
  }
  if ( (*(unsigned int (__fastcall **)(EditPage *))(*(_QWORD *)this + 264LL))(this) )
  {
    ResourceString = ((__int64 (__fastcall *)(struct IXMLDOMNode *, const wchar_t *, _QWORD *))v3->lpVtbl->selectSingleNode)(
                       v3,
                       L"./ExtensionPoint/Browse",
                       &v29);
    v8 = ResourceString;
    if ( ResourceString < 0 )
    {
      v9 = 1323;
      goto LABEL_21;
    }
    if ( !ResourceString )
    {
      ResourceString = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *), wchar_t **))(*v29)[26])(
                         v29,
                         &String1);
      v8 = ResourceString;
      if ( ResourceString < 0 )
      {
        v9 = 1330;
        goto LABEL_21;
      }
      if ( _wcsicmp(String1, L"Computer") )
      {
        if ( _wcsicmp(String1, L"File") )
        {
          if ( !_wcsicmp(String1, L"Folder") )
            *((_DWORD *)this + 58) = 1;
        }
        else
        {
          v18 = v29;
          *((_DWORD *)this + 56) = 1;
          ResourceString = (**v18)(v18, &IID_IXMLDOMElement, &v35);
          v8 = ResourceString;
          if ( ResourceString < 0 )
          {
            v9 = 1340;
            goto LABEL_21;
          }
          v19 = SysAllocString(L"FilterText");
          v4 = v19;
          if ( !v19 )
          {
            v9 = 1343;
            goto LABEL_20;
          }
          ResourceString = (*(__int64 (__fastcall **)(__int64, BSTR, VARIANTARG *))(*(_QWORD *)v35 + 352LL))(
                             v35,
                             v19,
                             &pvarg);
          v8 = ResourceString;
          if ( ResourceString < 0 )
          {
            v9 = 1346;
            goto LABEL_21;
          }
          v20 = -1;
          if ( pvarg.llVal )
          {
            v21 = -1;
            do
              ++v21;
            while ( *(_WORD *)(pvarg.llVal + 2 * v21) );
            if ( v21 )
            {
              ResourceString = DwzTryLoadResourceString(pvarg.bstrVal, (unsigned __int16 **)this + 26);
              v8 = ResourceString;
              if ( ResourceString < 0 )
              {
                v9 = 1355;
                goto LABEL_21;
              }
            }
          }
          VariantClear(&pvarg);
          SysFreeString(v4);
          v22 = SysAllocString(L"FilterExtension");
          v4 = v22;
          if ( !v22 )
          {
            v9 = 1362;
            goto LABEL_20;
          }
          ResourceString = (*(__int64 (__fastcall **)(__int64, BSTR, VARIANTARG *))(*(_QWORD *)v35 + 352LL))(
                             v35,
                             v22,
                             &pvarg);
          v8 = ResourceString;
          if ( ResourceString < 0 )
          {
            v9 = 1365;
            goto LABEL_21;
          }
          if ( pvarg.llVal )
          {
            do
              ++v20;
            while ( *(_WORD *)(pvarg.llVal + 2 * v20) );
            if ( v20 )
            {
              v23 = SysAllocString(pvarg.bstrVal);
              *((_QWORD *)this + 25) = v23;
              if ( !v23 )
              {
                v9 = 1372;
                goto LABEL_20;
              }
            }
          }
          VariantClear(&pvarg);
          SysFreeString(v4);
          v24 = SysAllocString(L"FileMustExist");
          v4 = v24;
          if ( !v24 )
          {
            v9 = 1382;
            goto LABEL_20;
          }
          ResourceString = (*(__int64 (__fastcall **)(__int64, BSTR, VARIANTARG *))(*(_QWORD *)v35 + 352LL))(
                             v35,
                             v24,
                             &pvarg);
          v8 = ResourceString;
          if ( ResourceString < 0 )
          {
            v9 = 1385;
            goto LABEL_21;
          }
          if ( !pvarg.llVal || _wcsicmp(pvarg.bstrVal, L"TRUE") )
            v12 = 0;
          *((_DWORD *)this + 59) = v12;
        }
      }
      else
      {
        *((_DWORD *)this + 57) = 1;
      }
    }
  }
LABEL_81:
  VariantClear(&pvarg);
  if ( v34 )
  {
    ((void (__fastcall *)(struct IXMLDOMNode *))v34->lpVtbl->Release)(v34);
    v34 = 0;
  }
  if ( v29 )
  {
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v29)[2])(v29);
    v29 = 0;
  }
  if ( v35 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    v35 = 0;
  }
  if ( v3 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v3->lpVtbl->Release)(v3);
  if ( String1 )
  {
    SysFreeString(String1);
    String1 = 0;
  }
  if ( v4 )
    SysFreeString(v4);
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v5 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v5);
  }
  return v8;
}

```

## disassembly

```asm
0x14002bdd0  mov     [rsp-38h+arg_0], rbx
0x14002bdd5  push    rbp
0x14002bdd6  push    rsi
0x14002bdd7  push    rdi
0x14002bdd8  push    r12
0x14002bdda  push    r13
0x14002bddc  push    r14
0x14002bdde  push    r15
0x14002bde0  mov     rbp, rsp
0x14002bde3  sub     rsp, 70h
0x14002bde7  xor     r14d, r14d
0x14002bdea  mov     rsi, rcx
0x14002bded  xorps   xmm0, xmm0
0x14002bdf0  mov     [rbp+arg_10], r14
0x14002bdf4  xor     eax, eax
0x14002bdf6  mov     [rbp+var_38], r14
0x14002bdfa  lea     rcx, [rbp+pvarg]; pvarg
0x14002bdfe  mov     [rbp+arg_18], r14
0x14002be02  mov     r12d, r14d
0x14002be05  mov     [rbp+var_28], r14
0x14002be09  mov     [rbp+String1], r14
0x14002be0d  mov     r15d, r14d
0x14002be10  mov     [rbp+bstrString], r14
0x14002be14  mov     r13d, r14d
0x14002be17  mov     [rbp+psz], r14
0x14002be1b  mov     rdi, rdx
0x14002be1e  movups  xmmword ptr [rbp+pvarg], xmm0
0x14002be22  mov     qword ptr [rbp+pvarg+10h], rax
0x14002be26  call    cs:__imp_VariantInit
0x14002be2d  nop     dword ptr [rax+rax+00h]
0x14002be32  mov     rdx, rdi; struct IXMLDOMDocument2 *
0x14002be35  mov     rcx, rsi; this
0x14002be38  call    ?Initialize@InteractivityPage@@UEAAJPEAUIXMLDOMDocument2@@@Z; InteractivityPage::Initialize(IXMLDOMDocument2 *)
0x14002be3d  mov     ebx, eax
0x14002be3f  test    eax, eax
0x14002be41  jns     short loc_14002BE6A
0x14002be43  mov     r9d, 4F1h
0x14002be49  mov     [rsp+70h+var_50], eax
0x14002be4d  mov     ecx, 1; Level
0x14002be52  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14002be59  lea     r8, aEditpageInitia; "EditPage::Initialize"
0x14002be60  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14002be65  jmp     loc_14002C3C5
0x14002be6a  lea     rdx, [rbp+var_28]; struct IXMLDOMElement **
0x14002be6e  mov     rcx, rdi; struct IXMLDOMDocument2 *
0x14002be71  call    ?DwzXmlGetRootNode@@YAJPEAUIXMLDOMDocument2@@PEAPEAUIXMLDOMElement@@@Z; DwzXmlGetRootNode(IXMLDOMDocument2 *,IXMLDOMElement * *)
0x14002be76  mov     ebx, eax
0x14002be78  test    eax, eax
0x14002be7a  jns     short loc_14002BEA7
0x14002be7c  mov     r9d, 4F4h
0x14002be82  mov     [rsp+70h+var_50], eax
0x14002be86  lea     r8, aEditpageInitia; "EditPage::Initialize"
0x14002be8d  mov     ecx, 1; Level
0x14002be92  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14002be99  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14002be9e  mov     r12, [rbp+var_28]
0x14002bea2  jmp     loc_14002C3C5
0x14002bea7  mov     r12, [rbp+var_28]
0x14002beab  lea     r9, [rbp+arg_10]; struct IXMLDOMNode **
0x14002beaf  mov     r8, r12; struct IXMLDOMNode *
0x14002beb2  lea     rcx, aRegularexpress; "./RegularExpression"
0x14002beb9  xor     edx, edx; struct IXMLDOMDocument2 *
0x14002bebb  call    ?DwzXmlGetNode@@YAJPEBGPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAU2@@Z; DwzXmlGetNode(ushort const *,IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNode * *)
0x14002bec0  mov     ebx, eax
0x14002bec2  test    eax, eax
0x14002bec4  jns     short loc_14002BED1
0x14002bec6  mov     r9d, 4F7h
0x14002becc  jmp     loc_14002BE49
0x14002bed1  mov     rcx, [rbp+arg_10]
0x14002bed5  lea     r14, [rsi+0B8h]
0x14002bedc  mov     rdx, r14
0x14002bedf  mov     rax, [rcx]
0x14002bee2  mov     rax, [rax+0D0h]
0x14002bee9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002beee  mov     ebx, eax
0x14002bef0  test    eax, eax
0x14002bef2  jns     short loc_14002BEFF
0x14002bef4  mov     r9d, 4FAh
0x14002befa  jmp     loc_14002BE49
0x14002beff  mov     rcx, [r14]; String1
0x14002bf02  lea     rdx, word_14006B9B8; String2
0x14002bf09  call    cs:__imp__wcsicmp
0x14002bf10  nop     dword ptr [rax+rax+00h]
0x14002bf15  xor     ebx, ebx
0x14002bf17  test    eax, eax
0x14002bf19  jnz     short loc_14002BF32
0x14002bf1b  mov     rcx, [r14]; bstrString
0x14002bf1e  test    rcx, rcx
0x14002bf21  jz      short loc_14002BF32
0x14002bf23  call    cs:__imp_SysFreeString
0x14002bf2a  nop     dword ptr [rax+rax+00h]
0x14002bf2f  mov     [r14], rbx
0x14002bf32  mov     edi, 1
0x14002bf37  cmp     [r14], rbx
0x14002bf3a  jz      short loc_14002BFAA
0x14002bf3c  lea     ecx, [rdi+37h]; Size
0x14002bf3f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002bf44  test    rax, rax
0x14002bf47  jz      short loc_14002BF63
0x14002bf49  mov     [rax+8], rbx
0x14002bf4d  mov     [rax+10h], rbx
0x14002bf51  mov     [rax+18h], rbx
0x14002bf55  mov     [rax+20h], ebx
0x14002bf58  mov     [rax+28h], rbx
0x14002bf5c  mov     [rax+30h], edi
0x14002bf5f  mov     [rax], ebx
0x14002bf61  jmp     short loc_14002BF66
0x14002bf63  mov     rax, rbx
0x14002bf66  mov     [rsi+0D8h], rax
0x14002bf6d  test    rax, rax
0x14002bf70  jnz     short loc_14002BF8A
0x14002bf72  mov     r9d, 503h
0x14002bf78  mov     eax, 8007000Eh
0x14002bf7d  mov     ebx, eax
0x14002bf7f  mov     [rsp+70h+var_50], eax
0x14002bf83  mov     ecx, edi
0x14002bf85  jmp     loc_14002BE52
0x14002bf8a  mov     rdx, [r14]
0x14002bf8d  mov     rcx, rax
0x14002bf90  call    ?Parse@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@QEAA?AW4REParseError@2@PEBGH@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Parse(ushort const *,int)
0x14002bf95  test    eax, eax
0x14002bf97  jz      short loc_14002BFAA
0x14002bf99  mov     ebx, 80004005h
0x14002bf9e  mov     r9d, 507h
0x14002bfa4  mov     [rsp+70h+var_50], ebx
0x14002bfa8  jmp     short loc_14002BF83
0x14002bfaa  mov     rcx, [rbp+arg_10]
0x14002bfae  test    rcx, rcx
0x14002bfb1  jz      short loc_14002BFC3
0x14002bfb3  mov     rax, [rcx]
0x14002bfb6  mov     rax, [rax+10h]
0x14002bfba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002bfbf  mov     [rbp+arg_10], rbx
0x14002bfc3  mov     rax, [r12]
0x14002bfc7  lea     r8, [rbp+arg_10]
0x14002bfcb  lea     rdx, aExtensionpoint_11; "./ExtensionPoint/Default"
0x14002bfd2  mov     rcx, r12
0x14002bfd5  mov     rax, [rax+128h]
0x14002bfdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002bfe1  xor     r14d, r14d
0x14002bfe4  mov     ebx, eax
0x14002bfe6  test    eax, eax
0x14002bfe8  jns     short loc_14002BFF2
0x14002bfea  mov     r9d, 511h
0x14002bff0  jmp     short loc_14002BF7F
0x14002bff2  jnz     loc_14002C0C5
0x14002bff8  mov     rcx, [rbp+arg_10]
0x14002bffc  lea     rdx, [rbp+bstrString]
0x14002c000  mov     rax, [rcx]
0x14002c003  mov     rax, [rax+0D0h]
0x14002c00a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c00f  mov     ebx, eax
0x14002c011  test    eax, eax
0x14002c013  jns     short loc_14002C020
0x14002c015  mov     r9d, 515h
0x14002c01b  jmp     loc_14002BF7F
0x14002c020  mov     rcx, [rbp+bstrString]; psz
0x14002c024  lea     r14, [rsi+0C0h]
0x14002c02b  mov     rdx, r14; unsigned __int16 **
0x14002c02e  call    ?DwzTryLoadResourceString@@YAJPEBGPEAPEAG@Z; DwzTryLoadResourceString(ushort const *,ushort * *)
0x14002c033  mov     ebx, eax
0x14002c035  test    eax, eax
0x14002c037  jns     short loc_14002C044
0x14002c039  mov     r9d, 518h
0x14002c03f  jmp     loc_14002BF7F
0x14002c044  mov     r8, [rsi+0A0h]; struct IXMLDOMNode *
0x14002c04b  lea     rcx, [rbp+psz]; unsigned __int16 **
0x14002c04f  mov     rdx, [r14]; unsigned __int16 *
0x14002c052  call    ?DwzSubstituteXmlParameters@@YAJPEAPEAGPEBGPEAUIXMLDOMNode@@@Z; DwzSubstituteXmlParameters(ushort * *,ushort const *,IXMLDOMNode *)
0x14002c057  mov     ebx, eax
0x14002c059  test    eax, eax
0x14002c05b  jns     short loc_14002C085
0x14002c05d  mov     r9d, 51Eh
0x14002c063  mov     [rsp+70h+var_50], eax
0x14002c067  lea     r8, aEditpageInitia; "EditPage::Initialize"
0x14002c06e  mov     ecx, edi; Level
0x14002c070  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14002c077  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14002c07c  mov     r13, [rbp+psz]
0x14002c080  jmp     loc_14002C3C5
0x14002c085  mov     rcx, [r14]; bstrString
0x14002c088  test    rcx, rcx
0x14002c08b  jz      short loc_14002C09C
0x14002c08d  call    cs:__imp_SysFreeString
0x14002c094  nop     dword ptr [rax+rax+00h]
0x14002c099  mov     [r14], r13
0x14002c09c  mov     r13, [rbp+psz]
0x14002c0a0  mov     rcx, r13; psz
0x14002c0a3  call    cs:__imp_SysAllocString
0x14002c0aa  nop     dword ptr [rax+rax+00h]
0x14002c0af  mov     [r14], rax
0x14002c0b2  xor     r14d, r14d
0x14002c0b5  test    rax, rax
0x14002c0b8  jnz     short loc_14002C0C5
0x14002c0ba  mov     r9d, 522h
0x14002c0c0  jmp     loc_14002BF78
0x14002c0c5  mov     rcx, [rbp+arg_10]
0x14002c0c9  test    rcx, rcx
0x14002c0cc  jz      short loc_14002C0DE
0x14002c0ce  mov     rax, [rcx]
0x14002c0d1  mov     rax, [rax+10h]
0x14002c0d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c0da  mov     [rbp+arg_10], r14
0x14002c0de  mov     rax, [rsi]
0x14002c0e1  mov     rcx, rsi
0x14002c0e4  mov     rax, [rax+108h]
0x14002c0eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c0f0  test    eax, eax
0x14002c0f2  jz      loc_14002C3C5
0x14002c0f8  mov     rax, [r12]
0x14002c0fc  lea     r8, [rbp+var_38]
0x14002c100  lea     rdx, aExtensionpoint_3; "./ExtensionPoint/Browse"
0x14002c107  mov     rcx, r12
0x14002c10a  mov     rax, [rax+128h]
0x14002c111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c116  mov     ebx, eax
0x14002c118  test    eax, eax
0x14002c11a  jns     short loc_14002C127
0x14002c11c  mov     r9d, 52Bh
0x14002c122  jmp     loc_14002BF7F
0x14002c127  jnz     loc_14002C3C5
0x14002c12d  mov     rcx, [rbp+var_38]
0x14002c131  lea     rdx, [rbp+String1]
0x14002c135  mov     rax, [rcx]
0x14002c138  mov     rax, [rax+0D0h]
0x14002c13f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c144  mov     ebx, eax
0x14002c146  test    eax, eax
0x14002c148  jns     short loc_14002C155
0x14002c14a  mov     r9d, 532h
0x14002c150  jmp     loc_14002BF7F
0x14002c155  mov     rcx, [rbp+String1]; String1
0x14002c159  lea     rdx, aComputer; "Computer"
0x14002c160  call    cs:__imp__wcsicmp
0x14002c167  nop     dword ptr [rax+rax+00h]
0x14002c16c  test    eax, eax
0x14002c16e  jnz     short loc_14002C17B
0x14002c170  mov     [rsi+0E4h], edi
0x14002c176  jmp     loc_14002C3C5
0x14002c17b  mov     rcx, [rbp+String1]; String1
0x14002c17f  lea     rdx, aFile; "File"
0x14002c186  call    cs:__imp__wcsicmp
0x14002c18d  nop     dword ptr [rax+rax+00h]
0x14002c192  test    eax, eax
0x14002c194  jnz     loc_14002C3A4
0x14002c19a  mov     rcx, [rbp+var_38]
0x14002c19e  lea     r8, [rbp+arg_18]
0x14002c1a2  mov     [rsi+0E0h], edi
0x14002c1a8  lea     rdx, IID_IXMLDOMElement
0x14002c1af  mov     rax, [rcx]
0x14002c1b2  mov     rax, [rax]
0x14002c1b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c1ba  mov     ebx, eax
0x14002c1bc  test    eax, eax
0x14002c1be  jns     short loc_14002C1CB
0x14002c1c0  mov     r9d, 53Ch
0x14002c1c6  jmp     loc_14002BF7F
0x14002c1cb  lea     rcx, aFiltertext; "FilterText"
0x14002c1d2  call    cs:__imp_SysAllocString
0x14002c1d9  nop     dword ptr [rax+rax+00h]
0x14002c1de  mov     r15, rax
0x14002c1e1  test    rax, rax
0x14002c1e4  jnz     short loc_14002C1F1
0x14002c1e6  mov     r9d, 53Fh
0x14002c1ec  jmp     loc_14002BF78
0x14002c1f1  mov     rcx, [rbp+arg_18]
0x14002c1f5  lea     r8, [rbp+pvarg]
0x14002c1f9  mov     rdx, r15
0x14002c1fc  mov     rax, [rcx]
0x14002c1ff  mov     rax, [rax+160h]
0x14002c206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c20b  mov     ebx, eax
0x14002c20d  test    eax, eax
0x14002c20f  jns     short loc_14002C21C
0x14002c211  mov     r9d, 542h
0x14002c217  jmp     loc_14002BF7F
0x14002c21c  mov     rcx, qword ptr [rbp+pvarg+8]; psz
0x14002c220  or      r14, 0FFFFFFFFFFFFFFFFh
0x14002c224  xor     edx, edx
0x14002c226  test    rcx, rcx
0x14002c229  jz      short loc_14002C259
0x14002c22b  mov     rax, r14
0x14002c22e  inc     rax
0x14002c231  cmp     [rcx+rax*2], dx
0x14002c235  jnz     short loc_14002C22E
0x14002c237  test    rax, rax
0x14002c23a  jz      short loc_14002C259
0x14002c23c  lea     rdx, [rsi+0D0h]; unsigned __int16 **
0x14002c243  call    ?DwzTryLoadResourceString@@YAJPEBGPEAPEAG@Z; DwzTryLoadResourceString(ushort const *,ushort * *)
0x14002c248  mov     ebx, eax
0x14002c24a  test    eax, eax
0x14002c24c  jns     short loc_14002C259
0x14002c24e  mov     r9d, 54Bh
0x14002c254  jmp     loc_14002BF7F
0x14002c259  lea     rcx, [rbp+pvarg]; pvarg
0x14002c25d  call    cs:__imp_VariantClear
0x14002c264  nop     dword ptr [rax+rax+00h]
0x14002c269  mov     rcx, r15; bstrString
0x14002c26c  call    cs:__imp_SysFreeString
0x14002c273  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
