# EngineCallback::LoadInteractionDetails(ushort *,ushort * *,_INTERACTION_DETAILS *)

- ea: `0x140026f84`
- end: `0x1400274e8`
- name: `?LoadInteractionDetails@EngineCallback@@AEAAJPEAGPEAPEAGPEAU_INTERACTION_DETAILS@@@Z`
- size: `1380`
- prototype: `int(EngineCallback *__hidden this, unsigned __int16 *, unsigned __int16 **, struct _INTERACTION_DETAILS *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140026cb0`

## callees

- `0x140020420`
- `0x1400210f0`
- `0x140021974`
- `0x140026f84`
- `0x140063010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1400271d2`
- `msvcrt!_wcsicmp` at `0x1400271ff`
- `msvcrt!_wcsicmp` at `0x1400272a3`
- `msvcrt!_wcsicmp` at `0x1400273e8`
- `msvcrt!_wcsicmp` at `0x1400271d2`
- `msvcrt!_wcsicmp` at `0x1400271ff`
- `msvcrt!_wcsicmp` at `0x1400272a3`
- `msvcrt!_wcsicmp` at `0x1400273e8`
- `OLEAUT32!__imp_SysFreeString` at `0x1400273a9`
- `OLEAUT32!__imp_SysFreeString` at `0x1400274af`
- `OLEAUT32!__imp_SysFreeString` at `0x1400274c8`
- `OLEAUT32!__imp_SysFreeString` at `0x1400273a9`
- `OLEAUT32!__imp_SysFreeString` at `0x1400274af`
- `OLEAUT32!__imp_SysFreeString` at `0x1400274c8`

## string_xrefs

- `0x1400270bb`: `./ExtensionPoint/NoUI`
- `0x140027104`: `./ExtensionPoint/NoCache`
- `0x1400271f8`: `SecurityBoundarySafe`
- `0x14002721e`: `./ExtensionPoint/PackageLocations`
- `0x1400272e1`: `./ExtensionPoint/Disconnected`
- `0x140027346`: `./ExtensionPoint/SupportKey`
- `0x140027424`: `./ExtensionPoint/RemoteUpload`

## pseudocode

```c
__int64 __fastcall EngineCallback::LoadInteractionDetails(
        EngineCallback *this,
        unsigned __int16 *a2,
        const wchar_t **a3,
        struct _INTERACTION_DETAILS *a4)
{
  int v6; // eax
  struct IXMLDOMDocument2 *v7; // r12
  unsigned int v8; // ebx
  int RootNode; // eax
  struct IXMLDOMElement *v10; // r14
  int v11; // r9d
  BSTR bstrString; // [rsp+30h] [rbp-28h] BYREF
  wchar_t *String1; // [rsp+38h] [rbp-20h] BYREF
  struct IXMLDOMDocument2 *v15; // [rsp+40h] [rbp-18h] BYREF
  struct IXMLDOMElement *v16; // [rsp+48h] [rbp-10h] BYREF
  __int64 v17; // [rsp+A0h] [rbp+48h] BYREF

  v15 = 0;
  v16 = 0;
  v17 = 0;
  String1 = 0;
  bstrString = 0;
  v6 = DwzXmlCreate(a2, (LPVOID *)&v15);
  v7 = v15;
  v8 = v6;
  if ( v6 < 0 )
  {
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "EngineCallback::LoadInteractionDetails", 440, v6);
    goto LABEL_81;
  }
  RootNode = DwzXmlGetRootNode(v15, &v16);
  v10 = v16;
  v8 = RootNode;
  if ( RootNode < 0 )
  {
    v11 = 443;
LABEL_5:
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "EngineCallback::LoadInteractionDetails", v11, RootNode);
    goto LABEL_79;
  }
  RootNode = ((__int64 (__fastcall *)(struct IXMLDOMElement *, const unsigned __int16 *, __int64 *))v16->lpVtbl->selectSingleNode)(
               v16,
               L"./ID",
               &v17);
  v8 = RootNode;
  if ( RootNode < 0 )
  {
    v11 = 449;
    goto LABEL_5;
  }
  if ( RootNode == 1 )
  {
    v11 = 452;
LABEL_10:
    RootNode = -2147467259;
    v8 = -2147467259;
    goto LABEL_5;
  }
  RootNode = (*(__int64 (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v17 + 208LL))(v17, a3);
  v8 = RootNode;
  if ( RootNode < 0 )
  {
    v11 = 456;
    goto LABEL_5;
  }
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  RootNode = ((__int64 (__fastcall *)(struct IXMLDOMElement *, const wchar_t *, __int64 *))v10->lpVtbl->selectSingleNode)(
               v10,
               L"./ExtensionPoint/NoUI",
               &v17);
  v8 = RootNode;
  if ( RootNode < 0 )
  {
    v11 = 463;
    goto LABEL_5;
  }
  if ( !RootNode )
    *((_DWORD *)a4 + 1) = 1;
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  RootNode = ((__int64 (__fastcall *)(struct IXMLDOMElement *, const wchar_t *, __int64 *))v10->lpVtbl->selectSingleNode)(
               v10,
               L"./ExtensionPoint/NoCache",
               &v17);
  v8 = RootNode;
  if ( RootNode < 0 )
  {
    v11 = 470;
    goto LABEL_5;
  }
  if ( !RootNode )
    *((_DWORD *)a4 + 7) = 1;
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  RootNode = ((__int64 (__fastcall *)(struct IXMLDOMElement *, const wchar_t *, __int64 *))v10->lpVtbl->selectSingleNode)(
               v10,
               L"./Dynamic",
               &v17);
  v8 = RootNode;
  if ( RootNode < 0 )
  {
    v11 = 482;
    goto LABEL_5;
  }
  if ( RootNode == 1 )
  {
    v11 = 485;
    goto LABEL_10;
  }
  RootNode = (*(__int64 (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v17 + 208LL))(v17, &String1);
  v8 = RootNode;
  if ( RootNode < 0 )
  {
    v11 = 492;
    goto LABEL_5;
  }
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  if ( !_wcsicmp(String1, L"true") )
    *(_DWORD *)a4 = 0;
  if ( *((_QWORD *)Config + 16) && !_wcsicmp(*a3, L"SecurityBoundarySafe") )
  {
    *((_DWORD *)a4 + 6) = 1;
    goto LABEL_79;
  }
  RootNode = ((__int64 (__fastcall *)(struct IXMLDOMElement *, const wchar_t *, __int64 *))v10->lpVtbl->selectSingleNode)(
               v10,
               L"./ExtensionPoint/PackageLocations",
               &v17);
  v8 = RootNode;
  if ( RootNode < 0 )
  {
    v11 = 512;
    goto LABEL_5;
  }
  if ( !RootNode && (unsigned int)(*((_DWORD *)Config + 66) - 1) <= 2 )
  {
    if ( v17 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      v17 = 0;
    }
    RootNode = ((__int64 (__fastcall *)(struct IXMLDOMElement *, BSTR *))v10->lpVtbl->get_nodeName)(v10, &bstrString);
    v8 = RootNode;
    if ( RootNode < 0 )
    {
      v11 = 517;
      goto LABEL_5;
    }
    if ( !_wcsicmp(bstrString, L"TextInteraction") )
    {
      *((_DWORD *)a4 + 2) = 1;
LABEL_50:
      *(_DWORD *)a4 = 0;
      *((_DWORD *)a4 + 1) = 1;
      goto LABEL_79;
    }
  }
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  RootNode = ((__int64 (__fastcall *)(struct IXMLDOMElement *, const wchar_t *, __int64 *))v10->lpVtbl->selectSingleNode)(
               v10,
               L"./ExtensionPoint/Disconnected",
               &v17);
  v8 = RootNode;
  if ( RootNode < 0 )
  {
    v11 = 534;
    goto LABEL_5;
  }
  if ( RootNode || (unsigned int)(*((_DWORD *)Config + 66) - 1) > 2 )
  {
    if ( v17 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      v17 = 0;
    }
    RootNode = ((__int64 (__fastcall *)(struct IXMLDOMElement *, const wchar_t *, __int64 *))v10->lpVtbl->selectSingleNode)(
                 v10,
                 L"./ExtensionPoint/SupportKey",
                 &v17);
    v8 = RootNode;
    if ( RootNode < 0 )
    {
      v11 = 546;
      goto LABEL_5;
    }
    if ( RootNode || (unsigned int)(*((_DWORD *)Config + 66) - 1) > 2 )
      goto LABEL_72;
    if ( v17 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      v17 = 0;
    }
    if ( bstrString )
    {
      SysFreeString(bstrString);
      bstrString = 0;
    }
    RootNode = ((__int64 (__fastcall *)(struct IXMLDOMElement *, BSTR *))v10->lpVtbl->get_nodeName)(v10, &bstrString);
    v8 = RootNode;
    if ( RootNode < 0 )
    {
      v11 = 552;
      goto LABEL_5;
    }
    if ( _wcsicmp(bstrString, L"TextInteraction") )
    {
LABEL_72:
      if ( v17 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
        v17 = 0;
      }
      RootNode = ((__int64 (__fastcall *)(struct IXMLDOMElement *, const wchar_t *, __int64 *))v10->lpVtbl->selectSingleNode)(
                   v10,
                   L"./ExtensionPoint/RemoteUpload",
                   &v17);
      v8 = RootNode;
      if ( RootNode >= 0 )
      {
        if ( !RootNode && (unsigned int)(*((_DWORD *)Config + 66) - 1) <= 2 )
          *((_DWORD *)a4 + 4) = 1;
        goto LABEL_79;
      }
      v11 = 570;
      goto LABEL_5;
    }
    *((_DWORD *)a4 + 2) = 0;
    *((_DWORD *)a4 + 3) = 1;
    goto LABEL_50;
  }
  *((_DWORD *)a4 + 5) = 1;
LABEL_79:
  if ( v10 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v10->lpVtbl->Release)(v10);
LABEL_81:
  if ( v7 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v7->lpVtbl->Release)(v7);
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  if ( String1 )
  {
    SysFreeString(String1);
    String1 = 0;
  }
  if ( bstrString )
    SysFreeString(bstrString);
  return v8;
}

```

## disassembly

```asm
0x140026f84  mov     [rsp-40h+arg_0], rcx
0x140026f89  push    rbp
0x140026f8a  push    rbx
0x140026f8b  push    rsi
0x140026f8c  push    rdi
0x140026f8d  push    r12
0x140026f8f  push    r13
0x140026f91  push    r14
0x140026f93  push    r15
0x140026f95  mov     rbp, rsp
0x140026f98  sub     rsp, 58h
0x140026f9c  xor     r13d, r13d
0x140026f9f  mov     rcx, rdx; psz
0x140026fa2  lea     rdx, [rbp+var_18]; struct IXMLDOMDocument2 **
0x140026fa6  mov     [rbp+var_18], r13
0x140026faa  mov     [rbp+var_10], r13
0x140026fae  mov     rsi, r9
0x140026fb1  mov     [rbp+arg_0], r13
0x140026fb5  mov     r15, r8
0x140026fb8  mov     [rbp+String1], r13
0x140026fbc  mov     [rbp+bstrString], r13
0x140026fc0  call    ?DwzXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; DwzXmlCreate(ushort const *,IXMLDOMDocument2 * *)
0x140026fc5  mov     r12, [rbp+var_18]
0x140026fc9  mov     ebx, eax
0x140026fcb  test    eax, eax
0x140026fcd  jns     short loc_140026FF5
0x140026fcf  mov     r9d, 1B8h
0x140026fd5  mov     [rsp+58h+var_38], eax
0x140026fd9  lea     r8, aEnginecallback_9; "EngineCallback::LoadInteractionDetails"
0x140026fe0  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140026fe7  lea     ecx, [r13+1]; Level
0x140026feb  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140026ff0  jmp     loc_140027478
0x140026ff5  lea     rdx, [rbp+var_10]; struct IXMLDOMElement **
0x140026ff9  mov     rcx, r12; struct IXMLDOMDocument2 *
0x140026ffc  call    ?DwzXmlGetRootNode@@YAJPEAUIXMLDOMDocument2@@PEAPEAUIXMLDOMElement@@@Z; DwzXmlGetRootNode(IXMLDOMDocument2 *,IXMLDOMElement * *)
0x140027001  mov     r14, [rbp+var_10]
0x140027005  mov     ebx, eax
0x140027007  test    eax, eax
0x140027009  jns     short loc_140027032
0x14002700b  mov     r9d, 1BBh
0x140027011  mov     ecx, 1; Level
0x140027016  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14002701d  mov     [rsp+58h+var_38], eax
0x140027021  lea     r8, aEnginecallback_9; "EngineCallback::LoadInteractionDetails"
0x140027028  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14002702d  jmp     loc_140027464
0x140027032  mov     rax, [r14]
0x140027035  lea     r8, [rbp+arg_0]
0x140027039  lea     rdx, aId_2; "./ID"
0x140027040  mov     rcx, r14
0x140027043  mov     rax, [rax+128h]
0x14002704a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002704f  mov     ebx, eax
0x140027051  test    eax, eax
0x140027053  jns     short loc_14002705D
0x140027055  mov     r9d, 1C1h
0x14002705b  jmp     short loc_140027011
0x14002705d  mov     edi, 1
0x140027062  cmp     eax, edi
0x140027064  jnz     short loc_140027077
0x140027066  mov     r9d, 1C4h
0x14002706c  mov     eax, 80004005h
0x140027071  mov     ebx, eax
0x140027073  mov     ecx, edi
0x140027075  jmp     short loc_140027016
0x140027077  mov     rcx, [rbp+arg_0]
0x14002707b  mov     rdx, r15
0x14002707e  mov     rax, [rcx]
0x140027081  mov     rax, [rax+0D0h]
0x140027088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002708d  mov     ebx, eax
0x14002708f  test    eax, eax
0x140027091  jns     short loc_14002709B
0x140027093  mov     r9d, 1C8h
0x140027099  jmp     short loc_140027073
0x14002709b  mov     rcx, [rbp+arg_0]
0x14002709f  test    rcx, rcx
0x1400270a2  jz      short loc_1400270B4
0x1400270a4  mov     rax, [rcx]
0x1400270a7  mov     rax, [rax+10h]
0x1400270ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400270b0  mov     [rbp+arg_0], r13
0x1400270b4  mov     rax, [r14]
0x1400270b7  lea     r8, [rbp+arg_0]
0x1400270bb  lea     rdx, aExtensionpoint_22; "./ExtensionPoint/NoUI"
0x1400270c2  mov     rcx, r14
0x1400270c5  mov     rax, [rax+128h]
0x1400270cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400270d1  mov     ebx, eax
0x1400270d3  test    eax, eax
0x1400270d5  jns     short loc_1400270DF
0x1400270d7  mov     r9d, 1CFh
0x1400270dd  jmp     short loc_140027073
0x1400270df  jnz     short loc_1400270E4
0x1400270e1  mov     [rsi+4], edi
0x1400270e4  mov     rcx, [rbp+arg_0]
0x1400270e8  test    rcx, rcx
0x1400270eb  jz      short loc_1400270FD
0x1400270ed  mov     rax, [rcx]
0x1400270f0  mov     rax, [rax+10h]
0x1400270f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400270f9  mov     [rbp+arg_0], r13
0x1400270fd  mov     rax, [r14]
0x140027100  lea     r8, [rbp+arg_0]
0x140027104  lea     rdx, aExtensionpoint_9; "./ExtensionPoint/NoCache"
0x14002710b  mov     rcx, r14
0x14002710e  mov     rax, [rax+128h]
0x140027115  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002711a  mov     ebx, eax
0x14002711c  test    eax, eax
0x14002711e  jns     short loc_14002712B
0x140027120  mov     r9d, 1D6h
0x140027126  jmp     loc_140027073
0x14002712b  jnz     short loc_140027130
0x14002712d  mov     [rsi+1Ch], edi
0x140027130  mov     rcx, [rbp+arg_0]
0x140027134  test    rcx, rcx
0x140027137  jz      short loc_140027149
0x140027139  mov     rax, [rcx]
0x14002713c  mov     rax, [rax+10h]
0x140027140  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027145  mov     [rbp+arg_0], r13
0x140027149  mov     rax, [r14]
0x14002714c  lea     r8, [rbp+arg_0]
0x140027150  lea     rdx, aDynamic; "./Dynamic"
0x140027157  mov     rcx, r14
0x14002715a  mov     rax, [rax+128h]
0x140027161  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027166  mov     ebx, eax
0x140027168  test    eax, eax
0x14002716a  jns     short loc_140027177
0x14002716c  mov     r9d, 1E2h
0x140027172  jmp     loc_140027073
0x140027177  cmp     eax, edi
0x140027179  jnz     short loc_140027186
0x14002717b  mov     r9d, 1E5h
0x140027181  jmp     loc_14002706C
0x140027186  mov     rcx, [rbp+arg_0]
0x14002718a  lea     rdx, [rbp+String1]
0x14002718e  mov     rax, [rcx]
0x140027191  mov     rax, [rax+0D0h]
0x140027198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002719d  mov     ebx, eax
0x14002719f  test    eax, eax
0x1400271a1  jns     short loc_1400271AE
0x1400271a3  mov     r9d, 1ECh
0x1400271a9  jmp     loc_140027073
0x1400271ae  mov     rcx, [rbp+arg_0]
0x1400271b2  test    rcx, rcx
0x1400271b5  jz      short loc_1400271C7
0x1400271b7  mov     rax, [rcx]
0x1400271ba  mov     rax, [rax+10h]
0x1400271be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400271c3  mov     [rbp+arg_0], r13
0x1400271c7  mov     rcx, [rbp+String1]; String1
0x1400271cb  lea     rdx, aTrue; "true"
0x1400271d2  call    cs:__imp__wcsicmp
0x1400271d9  nop     dword ptr [rax+rax+00h]
0x1400271de  test    eax, eax
0x1400271e0  jnz     short loc_1400271E5
0x1400271e2  mov     [rsi], r13d
0x1400271e5  mov     rax, cs:?Config@@3PEAVConfiguration@@EA; Configuration * Config
0x1400271ec  cmp     [rax+80h], r13
0x1400271f3  jz      short loc_140027217
0x1400271f5  mov     rcx, [r15]; String1
0x1400271f8  lea     rdx, aSecuritybounda; "SecurityBoundarySafe"
0x1400271ff  call    cs:__imp__wcsicmp
0x140027206  nop     dword ptr [rax+rax+00h]
0x14002720b  test    eax, eax
0x14002720d  jnz     short loc_140027217
0x14002720f  mov     [rsi+18h], edi
0x140027212  jmp     loc_140027464
0x140027217  mov     rax, [r14]
0x14002721a  lea     r8, [rbp+arg_0]
0x14002721e  lea     rdx, aExtensionpoint_6; "./ExtensionPoint/PackageLocations"
0x140027225  mov     rcx, r14
0x140027228  mov     rax, [rax+128h]
0x14002722f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027234  mov     ebx, eax
0x140027236  test    eax, eax
0x140027238  jns     short loc_140027245
0x14002723a  mov     r9d, 200h
0x140027240  jmp     loc_140027073
0x140027245  jnz     short loc_1400272C1
0x140027247  mov     rax, cs:?Config@@3PEAVConfiguration@@EA; Configuration * Config
0x14002724e  mov     ecx, [rax+108h]
0x140027254  sub     ecx, edi
0x140027256  cmp     ecx, 2
0x140027259  ja      short loc_1400272C1
0x14002725b  mov     rcx, [rbp+arg_0]
0x14002725f  test    rcx, rcx
0x140027262  jz      short loc_140027274
0x140027264  mov     rax, [rcx]
0x140027267  mov     rax, [rax+10h]
0x14002726b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027270  mov     [rbp+arg_0], r13
0x140027274  mov     rax, [r14]
0x140027277  lea     rdx, [rbp+bstrString]
0x14002727b  mov     rcx, r14
0x14002727e  mov     rax, [rax+38h]
0x140027282  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027287  mov     ebx, eax
0x140027289  test    eax, eax
0x14002728b  jns     short loc_140027298
0x14002728d  mov     r9d, 205h
0x140027293  jmp     loc_140027073
0x140027298  mov     rcx, [rbp+bstrString]; String1
0x14002729c  lea     rdx, aTextinteractio; "TextInteraction"
0x1400272a3  call    cs:__imp__wcsicmp
0x1400272aa  nop     dword ptr [rax+rax+00h]
0x1400272af  test    eax, eax
0x1400272b1  jnz     short loc_1400272C1
0x1400272b3  mov     [rsi+8], edi
0x1400272b6  mov     [rsi], r13d
0x1400272b9  mov     [rsi+4], edi
0x1400272bc  jmp     loc_140027464
0x1400272c1  mov     rcx, [rbp+arg_0]
0x1400272c5  test    rcx, rcx
0x1400272c8  jz      short loc_1400272DA
0x1400272ca  mov     rax, [rcx]
0x1400272cd  mov     rax, [rax+10h]
0x1400272d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400272d6  mov     [rbp+arg_0], r13
0x1400272da  mov     rax, [r14]
0x1400272dd  lea     r8, [rbp+arg_0]
0x1400272e1  lea     rdx, aExtensionpoint_1; "./ExtensionPoint/Disconnected"
0x1400272e8  mov     rcx, r14
0x1400272eb  mov     rax, [rax+128h]
0x1400272f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400272f7  mov     ebx, eax
0x1400272f9  test    eax, eax
0x1400272fb  jns     short loc_140027308
0x1400272fd  mov     r9d, 216h
0x140027303  jmp     loc_140027073
0x140027308  jnz     short loc_140027326
0x14002730a  mov     rax, cs:?Config@@3PEAVConfiguration@@EA; Configuration * Config
0x140027311  mov     ecx, [rax+108h]
0x140027317  sub     ecx, edi
0x140027319  cmp     ecx, 2
0x14002731c  ja      short loc_140027326
0x14002731e  mov     [rsi+14h], edi
0x140027321  jmp     loc_140027464
0x140027326  mov     rcx, [rbp+arg_0]
0x14002732a  test    rcx, rcx
0x14002732d  jz      short loc_14002733F
0x14002732f  mov     rax, [rcx]
0x140027332  mov     rax, [rax+10h]
0x140027336  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002733b  mov     [rbp+arg_0], r13
0x14002733f  mov     rax, [r14]
0x140027342  lea     r8, [rbp+arg_0]
0x140027346  lea     rdx, aExtensionpoint_19; "./ExtensionPoint/SupportKey"
0x14002734d  mov     rcx, r14
0x140027350  mov     rax, [rax+128h]
0x140027357  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002735c  mov     ebx, eax
0x14002735e  test    eax, eax
0x140027360  jns     short loc_14002736D
0x140027362  mov     r9d, 222h
0x140027368  jmp     loc_140027073
0x14002736d  jnz     loc_140027404
0x140027373  mov     rax, cs:?Config@@3PEAVConfiguration@@EA; Configuration * Config
0x14002737a  mov     ecx, [rax+108h]
0x140027380  sub     ecx, edi
0x140027382  cmp     ecx, 2
0x140027385  ja      short loc_140027404
0x140027387  mov     rcx, [rbp+arg_0]
0x14002738b  test    rcx, rcx
0x14002738e  jz      short loc_1400273A0
0x140027390  mov     rax, [rcx]
0x140027393  mov     rax, [rax+10h]
0x140027397  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002739c  mov     [rbp+arg_0], r13
0x1400273a0  mov     rcx, [rbp+bstrString]; bstrString
0x1400273a4  test    rcx, rcx
0x1400273a7  jz      short loc_1400273B9
0x1400273a9  call    cs:__imp_SysFreeString
0x1400273b0  nop     dword ptr [rax+rax+00h]
0x1400273b5  mov     [rbp+bstrString], r13
0x1400273b9  mov     rax, [r14]
0x1400273bc  lea     rdx, [rbp+bstrString]
0x1400273c0  mov     rcx, r14
0x1400273c3  mov     rax, [rax+38h]
0x1400273c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400273cc  mov     ebx, eax
0x1400273ce  test    eax, eax
0x1400273d0  jns     short loc_1400273DD
0x1400273d2  mov     r9d, 228h
0x1400273d8  jmp     loc_140027073
0x1400273dd  mov     rcx, [rbp+bstrString]; String1
0x1400273e1  lea     rdx, aTextinteractio; "TextInteraction"
0x1400273e8  call    cs:__imp__wcsicmp
0x1400273ef  nop     dword ptr [rax+rax+00h]
0x1400273f4  test    eax, eax
0x1400273f6  jnz     short loc_140027404
0x1400273f8  mov     [rsi+8], r13d
0x1400273fc  mov     [rsi+0Ch], edi
0x1400273ff  jmp     loc_1400272B6
0x140027404  mov     rcx, [rbp+arg_0]
  ... truncated ...
```
