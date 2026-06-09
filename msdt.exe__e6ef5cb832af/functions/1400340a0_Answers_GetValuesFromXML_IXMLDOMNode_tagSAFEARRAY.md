# Answers::GetValuesFromXML(IXMLDOMNode *,tagSAFEARRAY * *)

- ea: `0x1400340a0`
- end: `0x1400342c3`
- name: `?GetValuesFromXML@Answers@@IEAAJPEAUIXMLDOMNode@@PEAPEAUtagSAFEARRAY@@@Z`
- size: `547`
- prototype: `__int64 __fastcall(Answers *__hidden this, struct IXMLDOMNode *, struct tagSAFEARRAY **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140033be0`

## callees

- `0x140020420`
- `0x140021c1c`
- `0x1400340a0`
- `0x140063010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1400341d8`
- `OLEAUT32!__imp_SysFreeString` at `0x14003425b`
- `OLEAUT32!__imp_SysFreeString` at `0x1400341d8`
- `OLEAUT32!__imp_SysFreeString` at `0x14003425b`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x140034148`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x140034148`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x140034277`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x140034277`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1400341bd`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1400341bd`

## string_xrefs

- `0x1400340f4`: `Answers::GetValuesFromXML`
- `0x14003422e`: `Answers::GetValuesFromXML`

## pseudocode

```c
__int64 __fastcall Answers::GetValuesFromXML(Answers *this, struct IXMLDOMNode *a2, struct tagSAFEARRAY **a3)
{
  struct IXMLDOMNodeVtbl *lpVtbl; // rax
  struct IXMLDOMNode *v4; // rsi
  HRESULT (__stdcall *get_childNodes)(IXMLDOMNode *, IXMLDOMNodeList **); // rax
  SAFEARRAY *v7; // r14
  HRESULT v8; // eax
  unsigned int v9; // ebx
  int v10; // r9d
  signed int v11; // eax
  int v12; // eax
  struct IXMLDOMNodeList *v14; // [rsp+30h] [rbp-20h] BYREF
  struct IXMLDOMNode *v15; // [rsp+38h] [rbp-18h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+40h] [rbp-10h] BYREF
  Answers *rgIndices; // [rsp+80h] [rbp+30h] BYREF
  signed int v18; // [rsp+88h] [rbp+38h] BYREF
  void *pv; // [rsp+98h] [rbp+48h] BYREF

  rgIndices = this;
  lpVtbl = a2->lpVtbl;
  v4 = 0;
  v14 = 0;
  v15 = 0;
  v18 = 0;
  get_childNodes = lpVtbl->get_childNodes;
  v7 = 0;
  LODWORD(rgIndices) = 0;
  pv = 0;
  v8 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, struct IXMLDOMNodeList **))get_childNodes)(a2, &v14);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 669;
LABEL_3:
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Answers::GetValuesFromXML", v10, v8);
    goto LABEL_21;
  }
  v8 = ((__int64 (__fastcall *)(struct IXMLDOMNodeList *, signed int *))v14->lpVtbl->get_length)(v14, &v18);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 672;
    goto LABEL_3;
  }
  rgsabound.lLbound = 0;
  rgsabound.cElements = v18;
  v7 = SafeArrayCreate(8u, 1u, &rgsabound);
  if ( v7 )
  {
    LODWORD(rgIndices) = 0;
    v11 = 0;
    while ( v11 < v18 )
    {
      v12 = DwzXmlNextNode(v14, &v15);
      v9 = v12;
      if ( v12 < 0 )
      {
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Answers::GetValuesFromXML", 685, v12);
        v4 = v15;
        goto LABEL_21;
      }
      v4 = v15;
      v8 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, void **))v15->lpVtbl->get_text)(v15, &pv);
      v9 = v8;
      if ( v8 < 0 )
      {
        v10 = 688;
        goto LABEL_3;
      }
      v8 = SafeArrayPutElement(v7, (LONG *)&rgIndices, pv);
      v9 = v8;
      if ( v8 < 0 )
      {
        v10 = 691;
        goto LABEL_3;
      }
      if ( pv )
      {
        SysFreeString((BSTR)pv);
        pv = 0;
      }
      ((void (__fastcall *)(struct IXMLDOMNode *))v4->lpVtbl->Release)(v4);
      v4 = 0;
      v11 = (_DWORD)rgIndices + 1;
      v15 = 0;
      LODWORD(rgIndices) = (_DWORD)rgIndices + 1;
    }
    *a3 = v7;
    v7 = 0;
  }
  else
  {
    v9 = -2147024882;
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Answers::GetValuesFromXML", 681, -2147024882);
  }
LABEL_21:
  if ( pv )
  {
    SysFreeString((BSTR)pv);
    pv = 0;
  }
  if ( v7 )
    SafeArrayDestroy(v7);
  if ( v14 )
  {
    ((void (__fastcall *)(struct IXMLDOMNodeList *))v14->lpVtbl->Release)(v14);
    v14 = 0;
  }
  if ( v4 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v4->lpVtbl->Release)(v4);
  return v9;
}

```

## disassembly

```asm
0x1400340a0  mov     [rsp-28h+rgIndices], rcx
0x1400340a5  push    rbp
0x1400340a6  push    rbx
0x1400340a7  push    rsi
0x1400340a8  push    r14
0x1400340aa  push    r15
0x1400340ac  mov     rbp, rsp
0x1400340af  sub     rsp, 50h
0x1400340b3  mov     rax, [rdx]
0x1400340b6  xor     esi, esi
0x1400340b8  mov     rcx, rdx
0x1400340bb  mov     [rbp+var_20], 0
0x1400340c3  lea     rdx, [rbp+var_20]
0x1400340c7  mov     [rbp+var_18], rsi
0x1400340cb  mov     r15, r8
0x1400340ce  mov     [rbp+arg_8], esi
0x1400340d1  mov     rax, [rax+60h]
0x1400340d5  xor     r14d, r14d
0x1400340d8  mov     dword ptr [rbp+rgIndices], esi
0x1400340db  mov     [rbp+pv], rsi
0x1400340df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400340e4  mov     ebx, eax
0x1400340e6  test    eax, eax
0x1400340e8  jns     short loc_140034111
0x1400340ea  mov     r9d, 29Dh
0x1400340f0  mov     [rsp+50h+var_30], eax
0x1400340f4  lea     r8, aAnswersGetvalu; "Answers::GetValuesFromXML"
0x1400340fb  mov     ecx, 1; Level
0x140034100  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140034107  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14003410c  jmp     loc_140034252
0x140034111  mov     rcx, [rbp+var_20]
0x140034115  lea     rdx, [rbp+arg_8]
0x140034119  mov     rax, [rcx]
0x14003411c  mov     rax, [rax+40h]
0x140034120  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140034125  mov     ebx, eax
0x140034127  test    eax, eax
0x140034129  jns     short loc_140034133
0x14003412b  mov     r9d, 2A0h
0x140034131  jmp     short loc_1400340F0
0x140034133  mov     eax, [rbp+arg_8]
0x140034136  lea     r8, [rbp+rgsabound]; rgsabound
0x14003413a  mov     ecx, 8; vt
0x14003413f  mov     [rbp+rgsabound.lLbound], esi
0x140034142  mov     [rbp+rgsabound.cElements], eax
0x140034145  lea     edx, [rcx-7]; cDims
0x140034148  call    cs:__imp_SafeArrayCreate
0x14003414f  nop     dword ptr [rax+rax+00h]
0x140034154  mov     r14, rax
0x140034157  test    rax, rax
0x14003415a  jnz     short loc_14003416D
0x14003415c  mov     ebx, 8007000Eh
0x140034161  mov     r9d, 2A9h
0x140034167  mov     [rsp+50h+var_30], ebx
0x14003416b  jmp     short loc_1400340F4
0x14003416d  mov     dword ptr [rbp+rgIndices], esi
0x140034170  xor     eax, eax
0x140034172  cmp     eax, [rbp+arg_8]
0x140034175  jge     loc_14003424C
0x14003417b  mov     rcx, [rbp+var_20]; struct IXMLDOMNodeList *
0x14003417f  lea     rdx, [rbp+var_18]; struct IXMLDOMNode **
0x140034183  call    ?DwzXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; DwzXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x140034188  mov     ebx, eax
0x14003418a  test    eax, eax
0x14003418c  js      loc_140034224
0x140034192  mov     rsi, [rbp+var_18]
0x140034196  lea     rdx, [rbp+pv]
0x14003419a  mov     rcx, rsi
0x14003419d  mov     rax, [rsi]
0x1400341a0  mov     rax, [rax+0D0h]
0x1400341a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400341ac  mov     ebx, eax
0x1400341ae  test    eax, eax
0x1400341b0  js      short loc_140034219
0x1400341b2  mov     r8, [rbp+pv]; pv
0x1400341b6  lea     rdx, [rbp+rgIndices]; rgIndices
0x1400341ba  mov     rcx, r14; psa
0x1400341bd  call    cs:__imp_SafeArrayPutElement
0x1400341c4  nop     dword ptr [rax+rax+00h]
0x1400341c9  mov     ebx, eax
0x1400341cb  test    eax, eax
0x1400341cd  js      short loc_14003420E
0x1400341cf  mov     rcx, [rbp+pv]; bstrString
0x1400341d3  test    rcx, rcx
0x1400341d6  jz      short loc_1400341EC
0x1400341d8  call    cs:__imp_SysFreeString
0x1400341df  nop     dword ptr [rax+rax+00h]
0x1400341e4  mov     [rbp+pv], 0
0x1400341ec  mov     rax, [rsi]
0x1400341ef  mov     rcx, rsi
0x1400341f2  mov     rax, [rax+10h]
0x1400341f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400341fb  mov     eax, dword ptr [rbp+rgIndices]
0x1400341fe  xor     esi, esi
0x140034200  inc     eax
0x140034202  mov     [rbp+var_18], rsi
0x140034206  mov     dword ptr [rbp+rgIndices], eax
0x140034209  jmp     loc_140034172
0x14003420e  mov     r9d, 2B3h
0x140034214  jmp     loc_1400340F0
0x140034219  mov     r9d, 2B0h
0x14003421f  jmp     loc_1400340F0
0x140034224  mov     r9d, 2ADh
0x14003422a  mov     [rsp+50h+var_30], eax
0x14003422e  lea     r8, aAnswersGetvalu; "Answers::GetValuesFromXML"
0x140034235  mov     ecx, 1; Level
0x14003423a  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140034241  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140034246  mov     rsi, [rbp+var_18]
0x14003424a  jmp     short loc_140034252
0x14003424c  mov     [r15], r14
0x14003424f  xor     r14d, r14d
0x140034252  mov     rcx, [rbp+pv]; bstrString
0x140034256  test    rcx, rcx
0x140034259  jz      short loc_14003426F
0x14003425b  call    cs:__imp_SysFreeString
0x140034262  nop     dword ptr [rax+rax+00h]
0x140034267  mov     [rbp+pv], 0
0x14003426f  test    r14, r14
0x140034272  jz      short loc_140034283
0x140034274  mov     rcx, r14; psa
0x140034277  call    cs:__imp_SafeArrayDestroy
0x14003427e  nop     dword ptr [rax+rax+00h]
0x140034283  mov     rcx, [rbp+var_20]
0x140034287  test    rcx, rcx
0x14003428a  jz      short loc_1400342A0
0x14003428c  mov     rax, [rcx]
0x14003428f  mov     rax, [rax+10h]
0x140034293  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140034298  mov     [rbp+var_20], 0
0x1400342a0  test    rsi, rsi
0x1400342a3  jz      short loc_1400342B4
0x1400342a5  mov     rax, [rsi]
0x1400342a8  mov     rcx, rsi
0x1400342ab  mov     rax, [rax+10h]
0x1400342af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400342b4  mov     eax, ebx
0x1400342b6  add     rsp, 50h
0x1400342ba  pop     r15
0x1400342bc  pop     r14
0x1400342be  pop     rsi
0x1400342bf  pop     rbx
0x1400342c0  pop     rbp
0x1400342c1  retn
```
