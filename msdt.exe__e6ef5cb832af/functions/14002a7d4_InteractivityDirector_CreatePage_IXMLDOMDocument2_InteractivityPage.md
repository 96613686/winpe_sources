# InteractivityDirector::CreatePage(IXMLDOMDocument2 *,InteractivityPage * *)

- ea: `0x14002a7d4`
- end: `0x14002ac8b`
- name: `?CreatePage@InteractivityDirector@@SAJPEAUIXMLDOMDocument2@@PEAPEAVInteractivityPage@@@Z`
- size: `1207`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *, struct InteractivityPage **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000f1a0`

## callees

- `0x14001ccc0`
- `0x14001d480`
- `0x140020420`
- `0x140021770`
- `0x140021974`
- `0x14002a7d4`
- `0x140063010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x14002a8d1`
- `msvcrt!_wcsicmp` at `0x14002a976`
- `msvcrt!_wcsicmp` at `0x14002a9cc`
- `msvcrt!_wcsicmp` at `0x14002aaa2`
- `msvcrt!_wcsicmp` at `0x14002aae4`
- `msvcrt!_wcsicmp` at `0x14002ab04`
- `msvcrt!_wcsicmp` at `0x14002a8d1`
- `msvcrt!_wcsicmp` at `0x14002a976`
- `msvcrt!_wcsicmp` at `0x14002a9cc`
- `msvcrt!_wcsicmp` at `0x14002aaa2`
- `msvcrt!_wcsicmp` at `0x14002aae4`
- `msvcrt!_wcsicmp` at `0x14002ab04`
- `OLEAUT32!__imp_SysFreeString` at `0x14002ac4b`
- `OLEAUT32!__imp_SysFreeString` at `0x14002ac64`
- `OLEAUT32!__imp_SysFreeString` at `0x14002ac4b`
- `OLEAUT32!__imp_SysFreeString` at `0x14002ac64`

## string_xrefs

- `0x14002a82f`: `InteractivityDirector::CreatePage`
- `0x14002ab30`: `InteractivityDirector::CreatePage`
- `0x14002abd4`: `InteractivityDirector::CreatePage`
- `0x14002a8fc`: `./ExtensionPoint/CommandLinks`
- `0x14002a9e7`: `./ExtensionPoint/Eula`
- `0x14002aa3e`: `./ExtensionPoint/EditMode`

## pseudocode

```c
__int64 __fastcall InteractivityDirector::CreatePage(struct IXMLDOMDocument2 *a1, struct InteractivityPage **a2)
{
  int RootNode; // eax
  struct IXMLDOMNode *v4; // r15
  unsigned int v5; // ebx
  int v6; // r9d
  int Nodes; // eax
  struct IXMLDOMNodeList *v8; // r12
  int v9; // r9d
  int v10; // eax
  unsigned int v11; // esi
  int v12; // r14d
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  struct InteractivityPage *v17; // rax
  wchar_t *String1; // [rsp+30h] [rbp-40h] BYREF
  struct InteractivityPage *v20; // [rsp+38h] [rbp-38h] BYREF
  __int64 v21; // [rsp+40h] [rbp-30h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-28h] BYREF
  struct IXMLDOMNode *v23; // [rsp+50h] [rbp-20h] BYREF
  struct IXMLDOMNodeList *v24; // [rsp+58h] [rbp-18h] BYREF
  struct PageManager *v25; // [rsp+60h] [rbp-10h] BYREF
  int v27; // [rsp+C0h] [rbp+50h] BYREF
  __int64 v28; // [rsp+C8h] [rbp+58h] BYREF

  v28 = 0;
  v21 = 0;
  v23 = 0;
  v24 = 0;
  v27 = 0;
  String1 = 0;
  bstrString = 0;
  v20 = 0;
  v25 = 0;
  RootNode = DwzXmlGetRootNode(a1, (struct IXMLDOMElement **)&v23);
  v4 = v23;
  v5 = RootNode;
  if ( RootNode < 0 )
  {
    v6 = 108;
LABEL_3:
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "InteractivityDirector::CreatePage", v6, RootNode);
    goto LABEL_65;
  }
  RootNode = ((__int64 (__fastcall *)(struct IXMLDOMNode *, wchar_t **))v23->lpVtbl->get_nodeName)(v23, &String1);
  v5 = RootNode;
  if ( RootNode < 0 )
  {
    v6 = 111;
    goto LABEL_3;
  }
  Nodes = DwzXmlGetNodes(L"./Choices/Choice", 0, v4, &v24);
  v8 = v24;
  v5 = Nodes;
  if ( Nodes < 0 )
  {
    v9 = 117;
LABEL_53:
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "InteractivityDirector::CreatePage", v9, Nodes);
    goto LABEL_63;
  }
  Nodes = ((__int64 (__fastcall *)(struct IXMLDOMNodeList *, int *))v24->lpVtbl->get_length)(v24, &v27);
  v5 = Nodes;
  if ( Nodes < 0 )
  {
    v9 = 120;
    goto LABEL_53;
  }
  if ( !_wcsicmp(String1, L"SingleResponseInteraction") )
  {
    if ( v27 <= 0 )
    {
      if ( v27 <= 4 )
      {
        v5 = -2147418113;
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "InteractivityDirector::CreatePage", 145, -2147418113);
        goto LABEL_63;
      }
    }
    else if ( v27 <= 4 )
    {
      v10 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, const wchar_t *, __int64 *))v4->lpVtbl->selectSingleNode)(
              v4,
              L"./ExtensionPoint/CommandLinks",
              &v21);
      v5 = v10;
      if ( v10 < 0 )
      {
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "InteractivityDirector::CreatePage", 132, v10);
        goto LABEL_63;
      }
      if ( v10 == 1 || (unsigned int)(v27 - 2) > 1 )
        v11 = 45;
      else
        v11 = 46;
      goto LABEL_21;
    }
    v11 = 50;
LABEL_21:
    v12 = 0;
    goto LABEL_51;
  }
  v12 = 0;
  if ( !_wcsicmp(String1, L"MultipleResponseInteraction") )
  {
    if ( v27 <= 0 )
    {
      if ( v27 <= 4 )
      {
        v5 = -2147418113;
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "InteractivityDirector::CreatePage", 162, -2147418113);
        goto LABEL_63;
      }
    }
    else if ( v27 <= 4 )
    {
      v11 = 47;
      goto LABEL_51;
    }
    v11 = 50;
    v12 = 1;
LABEL_51:
    Nodes = PageManager::Instance(&v25);
    v5 = Nodes;
    if ( Nodes >= 0 )
    {
      Nodes = PageManager::TypeToPage(v25, v11, &v20);
      v5 = Nodes;
      if ( Nodes >= 0 )
      {
        if ( v11 == 50 )
          *((_DWORD *)v20 + 46) = v12 == 0;
        v16 = (*(__int64 (__fastcall **)(struct InteractivityPage *, struct IXMLDOMDocument2 *))(*(_QWORD *)v20 + 232LL))(
                v20,
                a1);
        v5 = v16;
        if ( v16 >= 0 )
        {
          v17 = v20;
          v20 = 0;
          *a2 = v17;
        }
        else
        {
          SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "InteractivityDirector::CreatePage", 217, v16);
        }
        goto LABEL_63;
      }
      v9 = 207;
    }
    else
    {
      v9 = 204;
    }
    goto LABEL_53;
  }
  if ( !_wcsicmp(String1, L"TextInteraction") )
  {
    v13 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, const wchar_t *, __int64 *))v4->lpVtbl->selectSingleNode)(
            v4,
            L"./ExtensionPoint/Eula",
            &v28);
    v5 = v13;
    if ( v13 < 0 )
    {
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "InteractivityDirector::CreatePage", 169, v13);
      goto LABEL_63;
    }
    if ( v13 )
    {
      if ( v28 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
        v28 = 0;
      }
      v14 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, const wchar_t *, __int64 *))v4->lpVtbl->selectSingleNode)(
              v4,
              L"./ExtensionPoint/EditMode",
              &v28);
      v5 = v14;
      if ( v14 < 0 )
      {
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "InteractivityDirector::CreatePage", 177, v14);
        goto LABEL_63;
      }
      if ( !v14 )
      {
        v15 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v28 + 208LL))(v28, &bstrString);
        v5 = v15;
        if ( v15 < 0 )
        {
          SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "InteractivityDirector::CreatePage", 184, v15);
          goto LABEL_63;
        }
        if ( !_wcsicmp(bstrString, L"Multi") )
          v12 = 1;
      }
      if ( v28 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
        v28 = 0;
      }
      v11 = 49 - (v12 != 0);
    }
    else
    {
      v11 = 51;
    }
    goto LABEL_51;
  }
  if ( !_wcsicmp(String1, L"PauseInteraction") )
  {
    v11 = 52;
    goto LABEL_51;
  }
  if ( !_wcsicmp(String1, L"LaunchUIInteraction") )
  {
    v11 = 53;
    goto LABEL_51;
  }
  v5 = -2147024809;
  SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "InteractivityDirector::CreatePage", 200, -2147024809);
LABEL_63:
  if ( v8 )
    ((void (__fastcall *)(struct IXMLDOMNodeList *))v8->lpVtbl->Release)(v8);
LABEL_65:
  if ( v28 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    v28 = 0;
  }
  if ( v21 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    v21 = 0;
  }
  if ( v4 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v4->lpVtbl->Release)(v4);
  if ( String1 )
  {
    SysFreeString(String1);
    String1 = 0;
  }
  if ( bstrString )
    SysFreeString(bstrString);
  return v5;
}

```

## disassembly

```asm
0x14002a7d4  mov     [rsp-38h+arg_0], rbx
0x14002a7d9  mov     [rsp-38h+arg_8], rdx
0x14002a7de  push    rbp
0x14002a7df  push    rsi
0x14002a7e0  push    rdi
0x14002a7e1  push    r12
0x14002a7e3  push    r13
0x14002a7e5  push    r14
0x14002a7e7  push    r15
0x14002a7e9  mov     rbp, rsp
0x14002a7ec  sub     rsp, 70h
0x14002a7f0  xor     esi, esi
0x14002a7f2  lea     rdx, [rbp+var_20]; struct IXMLDOMElement **
0x14002a7f6  mov     [rbp+arg_18], rsi
0x14002a7fa  mov     r13, rcx
0x14002a7fd  mov     [rbp+var_30], rsi
0x14002a801  mov     [rbp+var_20], rsi
0x14002a805  mov     [rbp+var_18], rsi
0x14002a809  mov     [rbp+arg_10], esi
0x14002a80c  mov     [rbp+String1], rsi
0x14002a810  mov     [rbp+bstrString], rsi
0x14002a814  mov     [rbp+var_38], rsi
0x14002a818  mov     [rbp+var_10], rsi
0x14002a81c  call    ?DwzXmlGetRootNode@@YAJPEAUIXMLDOMDocument2@@PEAPEAUIXMLDOMElement@@@Z; DwzXmlGetRootNode(IXMLDOMDocument2 *,IXMLDOMElement * *)
0x14002a821  mov     r15, [rbp+var_20]
0x14002a825  mov     ebx, eax
0x14002a827  test    eax, eax
0x14002a829  jns     short loc_14002A850
0x14002a82b  lea     r9d, [rsi+6Ch]
0x14002a82f  lea     r8, aInteractivityd; "InteractivityDirector::CreatePage"
0x14002a836  mov     [rsp+70h+var_50], eax
0x14002a83a  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14002a841  mov     ecx, 1; Level
0x14002a846  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14002a84b  jmp     loc_14002ABFC
0x14002a850  mov     rax, [r15]
0x14002a853  lea     rdx, [rbp+String1]
0x14002a857  mov     rcx, r15
0x14002a85a  mov     rax, [rax+38h]
0x14002a85e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a863  mov     ebx, eax
0x14002a865  test    eax, eax
0x14002a867  jns     short loc_14002A871
0x14002a869  mov     r9d, 6Fh ; 'o'
0x14002a86f  jmp     short loc_14002A82F
0x14002a871  lea     r9, [rbp+var_18]; struct IXMLDOMNodeList **
0x14002a875  mov     r8, r15; struct IXMLDOMNode *
0x14002a878  xor     edx, edx; struct IXMLDOMDocument2 *
0x14002a87a  lea     rcx, aChoicesChoice; "./Choices/Choice"
0x14002a881  call    ?DwzXmlGetNodes@@YAJPEBGPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAUIXMLDOMNodeList@@@Z; DwzXmlGetNodes(ushort const *,IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNodeList * *)
0x14002a886  mov     r12, [rbp+var_18]
0x14002a88a  mov     ebx, eax
0x14002a88c  test    eax, eax
0x14002a88e  jns     short loc_14002A8A4
0x14002a890  mov     r9d, 75h ; 'u'
0x14002a896  mov     [rsp+70h+var_50], eax
0x14002a89a  mov     ecx, 1
0x14002a89f  jmp     loc_14002ABD4
0x14002a8a4  mov     rax, [r12]
0x14002a8a8  lea     rdx, [rbp+arg_10]
0x14002a8ac  mov     rcx, r12
0x14002a8af  mov     rax, [rax+40h]
0x14002a8b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a8b8  mov     ebx, eax
0x14002a8ba  test    eax, eax
0x14002a8bc  jns     short loc_14002A8C6
0x14002a8be  mov     r9d, 78h ; 'x'
0x14002a8c4  jmp     short loc_14002A896
0x14002a8c6  mov     rcx, [rbp+String1]; String1
0x14002a8ca  lea     rdx, aSingleresponse; "SingleResponseInteraction"
0x14002a8d1  call    cs:__imp__wcsicmp
0x14002a8d8  nop     dword ptr [rax+rax+00h]
0x14002a8dd  mov     edi, 1
0x14002a8e2  lea     ebx, [rdi+31h]
0x14002a8e5  test    eax, eax
0x14002a8e7  jnz     short loc_14002A968
0x14002a8e9  mov     eax, [rbp+arg_10]
0x14002a8ec  test    eax, eax
0x14002a8ee  jle     short loc_14002A943
0x14002a8f0  cmp     eax, 4
0x14002a8f3  jg      short loc_14002A948
0x14002a8f5  mov     rax, [r15]
0x14002a8f8  lea     r8, [rbp+var_30]
0x14002a8fc  lea     rdx, aExtensionpoint_4; "./ExtensionPoint/CommandLinks"
0x14002a903  mov     rcx, r15
0x14002a906  mov     rax, [rax+128h]
0x14002a90d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a912  mov     ebx, eax
0x14002a914  test    eax, eax
0x14002a916  jns     short loc_14002A927
0x14002a918  mov     [rsp+70h+var_50], eax
0x14002a91c  mov     r9d, 84h
0x14002a922  jmp     loc_14002ABD2
0x14002a927  cmp     eax, edi
0x14002a929  jz      short loc_14002A93C
0x14002a92b  mov     eax, [rbp+arg_10]
0x14002a92e  add     eax, 0FFFFFFFEh
0x14002a931  cmp     eax, edi
0x14002a933  ja      short loc_14002A93C
0x14002a935  mov     esi, 2Eh ; '.'
0x14002a93a  jmp     short loc_14002A94A
0x14002a93c  mov     esi, 2Dh ; '-'
0x14002a941  jmp     short loc_14002A94A
0x14002a943  cmp     eax, 4
0x14002a946  jle     short loc_14002A952
0x14002a948  mov     esi, ebx
0x14002a94a  xor     r14d, r14d
0x14002a94d  jmp     loc_14002AB1B
0x14002a952  mov     eax, 8000FFFFh
0x14002a957  mov     r9d, 91h
0x14002a95d  mov     ebx, eax
0x14002a95f  mov     [rsp+70h+var_50], eax
0x14002a963  jmp     loc_14002ABD2
0x14002a968  mov     rcx, [rbp+String1]; String1
0x14002a96c  lea     rdx, aMultiplerespon; "MultipleResponseInteraction"
0x14002a973  mov     r14d, esi
0x14002a976  call    cs:__imp__wcsicmp
0x14002a97d  nop     dword ptr [rax+rax+00h]
0x14002a982  test    eax, eax
0x14002a984  jnz     short loc_14002A9C1
0x14002a986  mov     eax, [rbp+arg_10]
0x14002a989  test    eax, eax
0x14002a98b  jle     short loc_14002A99C
0x14002a98d  cmp     eax, 4
0x14002a990  jg      short loc_14002A9A1
0x14002a992  mov     esi, 2Fh ; '/'
0x14002a997  jmp     loc_14002AB1B
0x14002a99c  cmp     eax, 4
0x14002a99f  jle     short loc_14002A9AB
0x14002a9a1  mov     esi, ebx
0x14002a9a3  mov     r14d, edi
0x14002a9a6  jmp     loc_14002AB1B
0x14002a9ab  mov     eax, 8000FFFFh
0x14002a9b0  mov     r9d, 0A2h
0x14002a9b6  mov     ebx, eax
0x14002a9b8  mov     [rsp+70h+var_50], eax
0x14002a9bc  jmp     loc_14002ABD2
0x14002a9c1  mov     rcx, [rbp+String1]; String1
0x14002a9c5  lea     rdx, aTextinteractio; "TextInteraction"
0x14002a9cc  call    cs:__imp__wcsicmp
0x14002a9d3  nop     dword ptr [rax+rax+00h]
0x14002a9d8  test    eax, eax
0x14002a9da  jnz     loc_14002AAD9
0x14002a9e0  mov     rax, [r15]
0x14002a9e3  lea     r8, [rbp+arg_18]
0x14002a9e7  lea     rdx, aExtensionpoint; "./ExtensionPoint/Eula"
0x14002a9ee  mov     rcx, r15
0x14002a9f1  mov     rax, [rax+128h]
0x14002a9f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a9fd  mov     ebx, eax
0x14002a9ff  test    eax, eax
0x14002aa01  jns     short loc_14002AA12
0x14002aa03  mov     [rsp+70h+var_50], eax
0x14002aa07  mov     r9d, 0A9h
0x14002aa0d  jmp     loc_14002ABD2
0x14002aa12  jnz     short loc_14002AA1E
0x14002aa14  mov     esi, 33h ; '3'
0x14002aa19  jmp     loc_14002AB1B
0x14002aa1e  mov     rcx, [rbp+arg_18]
0x14002aa22  test    rcx, rcx
0x14002aa25  jz      short loc_14002AA37
0x14002aa27  mov     rax, [rcx]
0x14002aa2a  mov     rax, [rax+10h]
0x14002aa2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002aa33  mov     [rbp+arg_18], rsi
0x14002aa37  mov     rax, [r15]
0x14002aa3a  lea     r8, [rbp+arg_18]
0x14002aa3e  lea     rdx, aExtensionpoint_13; "./ExtensionPoint/EditMode"
0x14002aa45  mov     rcx, r15
0x14002aa48  mov     rax, [rax+128h]
0x14002aa4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002aa54  mov     ebx, eax
0x14002aa56  test    eax, eax
0x14002aa58  jns     short loc_14002AA69
0x14002aa5a  mov     [rsp+70h+var_50], eax
0x14002aa5e  mov     r9d, 0B1h
0x14002aa64  jmp     loc_14002ABD2
0x14002aa69  jnz     short loc_14002AAB4
0x14002aa6b  mov     rcx, [rbp+arg_18]
0x14002aa6f  lea     rdx, [rbp+bstrString]
0x14002aa73  mov     rax, [rcx]
0x14002aa76  mov     rax, [rax+0D0h]
0x14002aa7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002aa82  mov     ebx, eax
0x14002aa84  test    eax, eax
0x14002aa86  jns     short loc_14002AA97
0x14002aa88  mov     [rsp+70h+var_50], eax
0x14002aa8c  mov     r9d, 0B8h
0x14002aa92  jmp     loc_14002ABD2
0x14002aa97  mov     rcx, [rbp+bstrString]; String1
0x14002aa9b  lea     rdx, aMulti; "Multi"
0x14002aaa2  call    cs:__imp__wcsicmp
0x14002aaa9  nop     dword ptr [rax+rax+00h]
0x14002aaae  test    eax, eax
0x14002aab0  cmovz   r14d, edi
0x14002aab4  mov     rcx, [rbp+arg_18]
0x14002aab8  test    rcx, rcx
0x14002aabb  jz      short loc_14002AACD
0x14002aabd  mov     rax, [rcx]
0x14002aac0  mov     rax, [rax+10h]
0x14002aac4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002aac9  mov     [rbp+arg_18], rsi
0x14002aacd  mov     eax, r14d
0x14002aad0  neg     eax
0x14002aad2  sbb     esi, esi
0x14002aad4  add     esi, 31h ; '1'
0x14002aad7  jmp     short loc_14002AB1B
0x14002aad9  mov     rcx, [rbp+String1]; String1
0x14002aadd  lea     rdx, aPauseinteracti; "PauseInteraction"
0x14002aae4  call    cs:__imp__wcsicmp
0x14002aaeb  nop     dword ptr [rax+rax+00h]
0x14002aaf0  test    eax, eax
0x14002aaf2  jnz     short loc_14002AAF9
0x14002aaf4  lea     esi, [rax+34h]
0x14002aaf7  jmp     short loc_14002AB1B
0x14002aaf9  mov     rcx, [rbp+String1]; String1
0x14002aafd  lea     rdx, aLaunchuiintera; "LaunchUIInteraction"
0x14002ab04  call    cs:__imp__wcsicmp
0x14002ab0b  nop     dword ptr [rax+rax+00h]
0x14002ab10  test    eax, eax
0x14002ab12  jnz     loc_14002ABC3
0x14002ab18  lea     esi, [rax+35h]
0x14002ab1b  lea     rcx, [rbp+var_10]; struct PageManager **
0x14002ab1f  call    ?Instance@PageManager@@SAJPEAPEAV1@@Z; PageManager::Instance(PageManager * *)
0x14002ab24  mov     ebx, eax
0x14002ab26  test    eax, eax
0x14002ab28  jns     short loc_14002AB50
0x14002ab2a  mov     r9d, 0CCh
0x14002ab30  lea     r8, aInteractivityd; "InteractivityDirector::CreatePage"
0x14002ab37  mov     [rsp+70h+var_50], eax
0x14002ab3b  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14002ab42  mov     ecx, edi; Level
0x14002ab44  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14002ab49  xor     esi, esi
0x14002ab4b  jmp     loc_14002ABE7
0x14002ab50  mov     rcx, [rbp+var_10]
0x14002ab54  lea     r8, [rbp+var_38]
0x14002ab58  mov     edx, esi
0x14002ab5a  call    ?TypeToPage@PageManager@@QEAAJW4_PAGETYPE@@PEAPEAVWizardPage@@@Z; PageManager::TypeToPage(_PAGETYPE,WizardPage * *)
0x14002ab5f  mov     ebx, eax
0x14002ab61  test    eax, eax
0x14002ab63  jns     short loc_14002AB6D
0x14002ab65  mov     r9d, 0CFh
0x14002ab6b  jmp     short loc_14002AB30
0x14002ab6d  cmp     esi, 32h ; '2'
0x14002ab70  jnz     short loc_14002AB88
0x14002ab72  mov     rax, [rbp+var_38]
0x14002ab76  xor     esi, esi
0x14002ab78  mov     ecx, esi
0x14002ab7a  test    r14d, r14d
0x14002ab7d  setz    cl
0x14002ab80  mov     [rax+0B8h], ecx
0x14002ab86  jmp     short loc_14002AB8A
0x14002ab88  xor     esi, esi
0x14002ab8a  mov     rcx, [rbp+var_38]
0x14002ab8e  mov     rdx, r13
0x14002ab91  mov     rax, [rcx]
0x14002ab94  mov     rax, [rax+0E8h]
0x14002ab9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002aba0  mov     ebx, eax
0x14002aba2  test    eax, eax
0x14002aba4  jns     short loc_14002ABB2
0x14002aba6  mov     [rsp+70h+var_50], eax
0x14002abaa  mov     r9d, 0D9h
0x14002abb0  jmp     short loc_14002ABD2
0x14002abb2  mov     rax, [rbp+var_38]
0x14002abb6  mov     rcx, [rbp+arg_8]
0x14002abba  mov     [rbp+var_38], rsi
0x14002abbe  mov     [rcx], rax
0x14002abc1  jmp     short loc_14002ABE7
0x14002abc3  mov     ebx, 80070057h
0x14002abc8  mov     r9d, 0C8h
0x14002abce  mov     [rsp+70h+var_50], ebx
0x14002abd2  mov     ecx, edi; Level
0x14002abd4  lea     r8, aInteractivityd; "InteractivityDirector::CreatePage"
0x14002abdb  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14002abe2  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14002abe7  test    r12, r12
0x14002abea  jz      short loc_14002ABFC
0x14002abec  mov     rax, [r12]
0x14002abf0  mov     rcx, r12
0x14002abf3  mov     rax, [rax+10h]
0x14002abf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002abfc  mov     rcx, [rbp+arg_18]
0x14002ac00  test    rcx, rcx
0x14002ac03  jz      short loc_14002AC15
0x14002ac05  mov     rax, [rcx]
0x14002ac08  mov     rax, [rax+10h]
0x14002ac0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ac11  mov     [rbp+arg_18], rsi
0x14002ac15  mov     rcx, [rbp+var_30]
0x14002ac19  test    rcx, rcx
0x14002ac1c  jz      short loc_14002AC2E
0x14002ac1e  mov     rax, [rcx]
0x14002ac21  mov     rax, [rax+10h]
0x14002ac25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ac2a  mov     [rbp+var_30], rsi
0x14002ac2e  test    r15, r15
0x14002ac31  jz      short loc_14002AC42
0x14002ac33  mov     rax, [r15]
  ... truncated ...
```
