# HistoryFileRemoveSupportKey(void)

- ea: `0x1400433c8`
- end: `0x140043691`
- name: `?HistoryFileRemoveSupportKey@@YAJXZ`
- size: `713`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x14003dad0`

## callees

- `0x1400070b0`
- `0x140020220`
- `0x140020420`
- `0x140021770`
- `0x140021a54`
- `0x1400433c8`
- `0x140063010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x14004341d`
- `KERNEL32!HeapAlloc` at `0x14004341d`
- `KERNEL32!HeapFree` at `0x140043677`
- `KERNEL32!HeapFree` at `0x140043677`
- `KERNEL32!GetProcessHeap` at `0x140043406`
- `KERNEL32!GetProcessHeap` at `0x140043663`
- `KERNEL32!GetProcessHeap` at `0x140043406`
- `KERNEL32!GetProcessHeap` at `0x140043663`
- `OLEAUT32!__imp_VariantInit` at `0x1400433fa`
- `OLEAUT32!__imp_VariantInit` at `0x1400433fa`
- `OLEAUT32!__imp_VariantClear` at `0x14004360d`
- `OLEAUT32!__imp_VariantClear` at `0x14004360d`

## string_xrefs

- `0x140043448`: `results.xml`
- `0x140043499`: `HistoryFileRemoveSupportKey`
- `0x1400434e4`: `HistoryFileRemoveSupportKey`
- `0x1400435f1`: `HistoryFileRemoveSupportKey`

## pseudocode

```c
__int64 HistoryFileRemoveSupportKey(void)
{
  struct IXMLDOMDocument2 *v0; // rsi
  struct IXMLDOMNodeList *v1; // rdi
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v3; // r14
  unsigned int v4; // ebx
  int v5; // r9d
  int v6; // eax
  int v7; // eax
  int Nodes; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  HRESULT (__stdcall *save)(IXMLDOMDocument2 *, VARIANT); // rax
  int v14; // eax
  HANDLE v15; // rax
  VARIANTARG pvarg; // [rsp+30h] [rbp-40h] BYREF
  VARIANTARG v18; // [rsp+50h] [rbp-20h] BYREF
  int v19; // [rsp+A0h] [rbp+30h] BYREF
  __int64 v20; // [rsp+A8h] [rbp+38h] BYREF
  struct IXMLDOMDocument2 *v21; // [rsp+B0h] [rbp+40h] BYREF
  struct IXMLDOMNodeList *v22; // [rsp+B8h] [rbp+48h] BYREF

  v0 = 0;
  v21 = 0;
  v20 = 0;
  v1 = 0;
  v19 = 0;
  v22 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  ProcessHeap = GetProcessHeap();
  v3 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 0x208u);
  if ( !v3 )
  {
    v4 = -2147024882;
    v5 = 444;
LABEL_21:
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "HistoryFileRemoveSupportKey", v5, v4);
    goto LABEL_22;
  }
  v6 = StringCchPrintfW(v3, 0x104u, L"%s\\%s", g_HistoryDirectory, L"results.xml");
  v4 = v6;
  if ( v6 < 0 )
  {
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "HistoryFileRemoveSupportKey", 452, v6);
    goto LABEL_22;
  }
  v7 = DwzXmlLoad(v3, (LPVOID *)&v21);
  v4 = v7;
  if ( v7 < 0 )
  {
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "HistoryFileRemoveSupportKey", 455, v7);
    v0 = v21;
    goto LABEL_22;
  }
  v0 = v21;
  Nodes = DwzXmlGetNodes(L"/DiagnosticResults/SupportKey", v21, 0, &v22);
  v4 = Nodes;
  if ( Nodes < 0 )
  {
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "HistoryFileRemoveSupportKey", 462, Nodes);
    v1 = v22;
    goto LABEL_22;
  }
  v1 = v22;
  v9 = ((__int64 (__fastcall *)(struct IXMLDOMNodeList *, int *))v22->lpVtbl->get_length)(v22, &v19);
  v4 = v9;
  if ( v9 < 0 )
  {
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "HistoryFileRemoveSupportKey", 465, v9);
    goto LABEL_22;
  }
  v10 = ((__int64 (__fastcall *)(struct IXMLDOMNodeList *, GUID *, __int64 *))v1->lpVtbl->QueryInterface)(
          v1,
          &IID_IXMLDOMSelection,
          &v20);
  v4 = v10;
  if ( v10 < 0 )
  {
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "HistoryFileRemoveSupportKey", 470, v10);
    goto LABEL_22;
  }
  if ( v19 != 1 )
  {
    v4 = -2147467259;
    v5 = 477;
    goto LABEL_21;
  }
  v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v20 + 152LL))(v20);
  v4 = v11;
  if ( v11 >= 0 )
  {
    v12 = AssignVariantString(&pvarg, v3);
    v4 = v12;
    if ( v12 >= 0 )
    {
      save = v0->lpVtbl->save;
      v18 = pvarg;
      v14 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, VARIANTARG *))save)(v0, &v18);
      v4 = v14;
      if ( v14 < 0 )
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "HistoryFileRemoveSupportKey", 487, v14);
    }
    else
    {
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "HistoryFileRemoveSupportKey", 481, v12);
    }
  }
  else
  {
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "HistoryFileRemoveSupportKey", 474, v11);
  }
LABEL_22:
  VariantClear(&pvarg);
  if ( v0 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v0->lpVtbl->Release)(v0);
  if ( v1 )
    ((void (__fastcall *)(struct IXMLDOMNodeList *))v1->lpVtbl->Release)(v1);
  if ( v20 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    v20 = 0;
  }
  if ( v3 )
  {
    v15 = GetProcessHeap();
    HeapFree(v15, 0, v3);
  }
  return v4;
}

```

## disassembly

```asm
0x1400433c8  push    rbp
0x1400433ca  push    rbx
0x1400433cb  push    rsi
0x1400433cc  push    rdi
0x1400433cd  push    r14
0x1400433cf  mov     rbp, rsp
0x1400433d2  sub     rsp, 70h
0x1400433d6  xor     esi, esi
0x1400433d8  lea     rcx, [rbp+pvarg]; pvarg
0x1400433dc  xorps   xmm0, xmm0
0x1400433df  mov     [rbp+arg_10], rsi
0x1400433e3  xor     eax, eax
0x1400433e5  mov     [rbp+arg_8], rsi
0x1400433e9  xor     edi, edi
0x1400433eb  mov     [rbp+arg_0], esi
0x1400433ee  mov     [rbp+arg_18], rdi
0x1400433f2  movups  xmmword ptr [rbp+pvarg], xmm0
0x1400433f6  mov     qword ptr [rbp+pvarg+10h], rax
0x1400433fa  call    cs:__imp_VariantInit
0x140043401  nop     dword ptr [rax+rax+00h]
0x140043406  call    cs:__imp_GetProcessHeap
0x14004340d  nop     dword ptr [rax+rax+00h]
0x140043412  xor     edx, edx; dwFlags
0x140043414  mov     r8d, 208h; dwBytes
0x14004341a  mov     rcx, rax; hHeap
0x14004341d  call    cs:__imp_HeapAlloc
0x140043424  nop     dword ptr [rax+rax+00h]
0x140043429  mov     r14, rax
0x14004342c  test    rax, rax
0x14004342f  jnz     short loc_140043441
0x140043431  mov     ebx, 8007000Eh
0x140043436  mov     r9d, 1BCh
0x14004343c  jmp     loc_1400435ED
0x140043441  mov     r9, cs:?g_HistoryDirectory@@3PEAGEA; ushort * g_HistoryDirectory
0x140043448  lea     rax, aResultsXml; "results.xml"
0x14004344f  lea     r8, aSS_1; "%s\\%s"
0x140043456  mov     [rsp+70h+var_50], rax
0x14004345b  mov     edx, 104h; unsigned __int64
0x140043460  mov     rcx, r14; unsigned __int16 *
0x140043463  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140043468  mov     ebx, eax
0x14004346a  test    eax, eax
0x14004346c  jns     short loc_14004347D
0x14004346e  mov     dword ptr [rsp+70h+var_50], eax
0x140043472  mov     r9d, 1C4h
0x140043478  jmp     loc_1400435F1
0x14004347d  lea     rdx, [rbp+arg_10]; struct IXMLDOMDocument2 **
0x140043481  mov     rcx, r14; psz
0x140043484  call    ?DwzXmlLoad@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; DwzXmlLoad(ushort const *,IXMLDOMDocument2 * *)
0x140043489  mov     ebx, eax
0x14004348b  test    eax, eax
0x14004348d  jns     short loc_1400434BA
0x14004348f  mov     r9d, 1C7h
0x140043495  mov     dword ptr [rsp+70h+var_50], eax
0x140043499  lea     r8, aHistoryfilerem; "HistoryFileRemoveSupportKey"
0x1400434a0  mov     ecx, 1; Level
0x1400434a5  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x1400434ac  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x1400434b1  mov     rsi, [rbp+arg_10]
0x1400434b5  jmp     loc_140043609
0x1400434ba  mov     rsi, [rbp+arg_10]
0x1400434be  lea     r9, [rbp+arg_18]; struct IXMLDOMNodeList **
0x1400434c2  mov     rdx, rsi; struct IXMLDOMDocument2 *
0x1400434c5  lea     rcx, aDiagnosticresu_0; "/DiagnosticResults/SupportKey"
0x1400434cc  xor     r8d, r8d; struct IXMLDOMNode *
0x1400434cf  call    ?DwzXmlGetNodes@@YAJPEBGPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAUIXMLDOMNodeList@@@Z; DwzXmlGetNodes(ushort const *,IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNodeList * *)
0x1400434d4  mov     ebx, eax
0x1400434d6  test    eax, eax
0x1400434d8  jns     short loc_140043505
0x1400434da  mov     r9d, 1CEh
0x1400434e0  mov     dword ptr [rsp+70h+var_50], eax
0x1400434e4  lea     r8, aHistoryfilerem; "HistoryFileRemoveSupportKey"
0x1400434eb  mov     ecx, 1; Level
0x1400434f0  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x1400434f7  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x1400434fc  mov     rdi, [rbp+arg_18]
0x140043500  jmp     loc_140043609
0x140043505  mov     rdi, [rbp+arg_18]
0x140043509  lea     rdx, [rbp+arg_0]
0x14004350d  mov     rcx, rdi
0x140043510  mov     rax, [rdi]
0x140043513  mov     rax, [rax+40h]
0x140043517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004351c  mov     ebx, eax
0x14004351e  test    eax, eax
0x140043520  jns     short loc_140043531
0x140043522  mov     dword ptr [rsp+70h+var_50], eax
0x140043526  mov     r9d, 1D1h
0x14004352c  jmp     loc_1400435F1
0x140043531  mov     rax, [rdi]
0x140043534  lea     r8, [rbp+arg_8]
0x140043538  lea     rdx, IID_IXMLDOMSelection
0x14004353f  mov     rcx, rdi
0x140043542  mov     rax, [rax]
0x140043545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004354a  mov     ebx, eax
0x14004354c  test    eax, eax
0x14004354e  jns     short loc_14004355F
0x140043550  mov     dword ptr [rsp+70h+var_50], eax
0x140043554  mov     r9d, 1D6h
0x14004355a  jmp     loc_1400435F1
0x14004355f  cmp     [rbp+arg_0], 1
0x140043563  jnz     short loc_1400435E2
0x140043565  mov     rcx, [rbp+arg_8]
0x140043569  mov     rax, [rcx]
0x14004356c  mov     rax, [rax+98h]
0x140043573  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140043578  mov     ebx, eax
0x14004357a  test    eax, eax
0x14004357c  jns     short loc_14004358A
0x14004357e  mov     dword ptr [rsp+70h+var_50], eax
0x140043582  mov     r9d, 1DAh
0x140043588  jmp     short loc_1400435F1
0x14004358a  mov     rdx, r14; unsigned __int16 *
0x14004358d  lea     rcx, [rbp+pvarg]; struct tagVARIANT *
0x140043591  call    ?AssignVariantString@@YAJPEAUtagVARIANT@@PEBG@Z; AssignVariantString(tagVARIANT *,ushort const *)
0x140043596  mov     ebx, eax
0x140043598  test    eax, eax
0x14004359a  jns     short loc_1400435A8
0x14004359c  mov     dword ptr [rsp+70h+var_50], eax
0x1400435a0  mov     r9d, 1E1h
0x1400435a6  jmp     short loc_1400435F1
0x1400435a8  mov     rax, [rsi]
0x1400435ab  lea     rdx, [rbp+var_20]
0x1400435af  movups  xmm0, xmmword ptr [rbp+pvarg]
0x1400435b3  mov     rcx, rsi
0x1400435b6  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x1400435bb  mov     rax, [rax+210h]
0x1400435c2  movaps  [rbp+var_20], xmm0
0x1400435c6  movsd   [rbp+var_10], xmm1
0x1400435cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400435d0  mov     ebx, eax
0x1400435d2  test    eax, eax
0x1400435d4  jns     short loc_140043609
0x1400435d6  mov     dword ptr [rsp+70h+var_50], eax
0x1400435da  mov     r9d, 1E7h
0x1400435e0  jmp     short loc_1400435F1
0x1400435e2  mov     ebx, 80004005h
0x1400435e7  mov     r9d, 1DDh
0x1400435ed  mov     dword ptr [rsp+70h+var_50], ebx
0x1400435f1  lea     r8, aHistoryfilerem; "HistoryFileRemoveSupportKey"
0x1400435f8  mov     ecx, 1; Level
0x1400435fd  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140043604  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140043609  lea     rcx, [rbp+pvarg]; pvarg
0x14004360d  call    cs:__imp_VariantClear
0x140043614  nop     dword ptr [rax+rax+00h]
0x140043619  test    rsi, rsi
0x14004361c  jz      short loc_14004362D
0x14004361e  mov     rax, [rsi]
0x140043621  mov     rcx, rsi
0x140043624  mov     rax, [rax+10h]
0x140043628  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004362d  test    rdi, rdi
0x140043630  jz      short loc_140043641
0x140043632  mov     rax, [rdi]
0x140043635  mov     rcx, rdi
0x140043638  mov     rax, [rax+10h]
0x14004363c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140043641  mov     rcx, [rbp+arg_8]
0x140043645  test    rcx, rcx
0x140043648  jz      short loc_14004365E
0x14004364a  mov     rax, [rcx]
0x14004364d  mov     rax, [rax+10h]
0x140043651  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140043656  mov     [rbp+arg_8], 0
0x14004365e  test    r14, r14
0x140043661  jz      short loc_140043683
0x140043663  call    cs:__imp_GetProcessHeap
0x14004366a  nop     dword ptr [rax+rax+00h]
0x14004366f  mov     r8, r14; lpMem
0x140043672  xor     edx, edx; dwFlags
0x140043674  mov     rcx, rax; hHeap
0x140043677  call    cs:__imp_HeapFree
0x14004367e  nop     dword ptr [rax+rax+00h]
0x140043683  mov     eax, ebx
0x140043685  add     rsp, 70h
0x140043689  pop     r14
0x14004368b  pop     rdi
0x14004368c  pop     rsi
0x14004368d  pop     rbx
0x14004368e  pop     rbp
0x14004368f  retn
```
