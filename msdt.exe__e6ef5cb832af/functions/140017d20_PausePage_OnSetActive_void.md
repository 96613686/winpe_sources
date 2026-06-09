# PausePage::OnSetActive(void)

- ea: `0x140017d20`
- end: `0x140017ee0`
- name: `?OnSetActive@PausePage@@MEAA_JXZ`
- size: `448`
- prototype: `__int64 __fastcall(PausePage *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x140017d20`
- `0x140018678`
- `0x140020420`
- `0x140030080`
- `0x140063010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x140017e08`
- `OLEAUT32!__imp_SysAllocString` at `0x140017e27`
- `OLEAUT32!__imp_SysAllocString` at `0x140017e46`
- `OLEAUT32!__imp_SysAllocString` at `0x140017e08`
- `OLEAUT32!__imp_SysAllocString` at `0x140017e27`
- `OLEAUT32!__imp_SysAllocString` at `0x140017e46`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x140017ec5`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x140017ec5`
- `DUI70!?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ` at `0x140017d38`
- `DUI70!?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ` at `0x140017d38`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x140017d56`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x140017d56`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PausePage::OnSetActive(struct IXMLDOMNode **this)
{
  int v2; // eax
  int v3; // r9d
  const OLECHAR **v4; // rcx
  __int64 v5; // r8
  LinkAndRTFExtension *v6; // rcx
  DirectUI::Element *Element; // [rsp+30h] [rbp-10h]
  unsigned int v9; // [rsp+38h] [rbp-8h] BYREF
  __int64 v10; // [rsp+50h] [rbp+10h] BYREF

  v10 = 0;
  Element = DirectUI::TaskPage::GetElement((DirectUI::TaskPage *)this);
  v9 = 0;
  DirectUI::Element::StartDefer(Element, &v9);
  v2 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64 *))this[24]->lpVtbl->GetTypeInfo)(this[24], &v10);
  if ( v2 < 0 )
  {
    v3 = 2054;
LABEL_3:
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "PausePage::OnSetActive", v3, v2);
    goto LABEL_14;
  }
  v2 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, char *))this[24]->lpVtbl->get_nodeName)(
         this[24],
         (char *)this + 112);
  if ( v2 < 0 )
  {
    v3 = 2060;
    goto LABEL_3;
  }
  v2 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, char *))this[24]->lpVtbl->get_nodeValue)(
         this[24],
         (char *)this + 120);
  if ( v2 < 0 )
  {
    v3 = 2063;
    goto LABEL_3;
  }
  if ( v10 )
  {
    v4 = *(const OLECHAR ***)(v10 + 24);
    if ( v4 )
    {
      this[16] = (struct IXMLDOMNode *)SysAllocString(*v4);
      this[17] = (struct IXMLDOMNode *)SysAllocString(*(const OLECHAR **)(*(_QWORD *)(v10 + 24) + 8LL));
      this[18] = (struct IXMLDOMNode *)SysAllocString(*(const OLECHAR **)(*(_QWORD *)(v10 + 24) + 16LL));
      v5 = v10;
      this[20] = *(struct IXMLDOMNode **)(*(_QWORD *)(v10 + 24) + 24LL);
      LinkAndRTFExtension::SetParamNode(*(LinkAndRTFExtension **)(v5 + 24), 0);
      *((_DWORD *)this + 46) = *(_DWORD *)(*(_QWORD *)(v10 + 24) + 32LL);
    }
  }
  InteractivityTextPage::OnSetActive((InteractivityTextPage *)this);
  if ( v10 )
  {
    v6 = *(LinkAndRTFExtension **)(v10 + 24);
    if ( v6 )
    {
      LinkAndRTFExtension::SetParamNode(v6, this[20]);
      *(_QWORD *)(v10 + 24) = 0;
    }
  }
LABEL_14:
  if ( v9 )
    DirectUI::Element::EndDefer(Element, v9);
  return 0;
}

```

## disassembly

```asm
0x140017d20  mov     [rsp-8+arg_8], rbx
0x140017d25  push    rbp
0x140017d26  mov     rbp, rsp
0x140017d29  sub     rsp, 40h
0x140017d2d  mov     rbx, rcx
0x140017d30  mov     [rbp+arg_0], 0
0x140017d38  call    cs:__imp_?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ; DirectUI::TaskPage::GetElement(void)
0x140017d3f  nop     dword ptr [rax+rax+00h]
0x140017d44  mov     [rbp+var_10], rax
0x140017d48  mov     [rbp+var_8], 0
0x140017d4f  lea     rdx, [rbp+var_8]
0x140017d53  mov     rcx, rax
0x140017d56  call    cs:__imp_?StartDefer@Element@DirectUI@@QEAAXPEAK@Z; DirectUI::Element::StartDefer(ulong *)
0x140017d5d  nop     dword ptr [rax+rax+00h]
0x140017d62  nop
0x140017d63  mov     rcx, [rbx+0C0h]
0x140017d6a  mov     rax, [rcx]
0x140017d6d  lea     rdx, [rbp+arg_0]
0x140017d71  mov     rax, [rax+20h]
0x140017d75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017d7a  test    eax, eax
0x140017d7c  jns     short loc_140017DA5
0x140017d7e  mov     r9d, 806h
0x140017d84  mov     [rsp+40h+var_20], eax
0x140017d88  lea     r8, aPausepageOnset; "PausePage::OnSetActive"
0x140017d8f  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140017d96  mov     ecx, 1; Level
0x140017d9b  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140017da0  jmp     loc_140017EBA
0x140017da5  mov     rcx, [rbx+0C0h]
0x140017dac  mov     rax, [rcx]
0x140017daf  lea     rdx, [rbx+70h]
0x140017db3  mov     rax, [rax+38h]
0x140017db7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017dbc  test    eax, eax
0x140017dbe  jns     short loc_140017DC8
0x140017dc0  mov     r9d, 80Ch
0x140017dc6  jmp     short loc_140017D84
0x140017dc8  mov     rcx, [rbx+0C0h]
0x140017dcf  mov     rax, [rcx]
0x140017dd2  lea     rdx, [rbx+78h]
0x140017dd6  mov     rax, [rax+40h]
0x140017dda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017ddf  test    eax, eax
0x140017de1  jns     short loc_140017DEB
0x140017de3  mov     r9d, 80Fh
0x140017de9  jmp     short loc_140017D84
0x140017deb  mov     rax, [rbp+arg_0]
0x140017def  test    rax, rax
0x140017df2  jz      loc_140017E88
0x140017df8  mov     rcx, [rax+18h]
0x140017dfc  test    rcx, rcx
0x140017dff  jz      loc_140017E88
0x140017e05  mov     rcx, [rcx]; psz
0x140017e08  call    cs:__imp_SysAllocString
0x140017e0f  nop     dword ptr [rax+rax+00h]
0x140017e14  mov     [rbx+80h], rax
0x140017e1b  mov     rax, [rbp+arg_0]
0x140017e1f  mov     rcx, [rax+18h]
0x140017e23  mov     rcx, [rcx+8]; psz
0x140017e27  call    cs:__imp_SysAllocString
0x140017e2e  nop     dword ptr [rax+rax+00h]
0x140017e33  mov     [rbx+88h], rax
0x140017e3a  mov     rax, [rbp+arg_0]
0x140017e3e  mov     rcx, [rax+18h]
0x140017e42  mov     rcx, [rcx+10h]; psz
0x140017e46  call    cs:__imp_SysAllocString
0x140017e4d  nop     dword ptr [rax+rax+00h]
0x140017e52  mov     [rbx+90h], rax
0x140017e59  mov     r8, [rbp+arg_0]
0x140017e5d  mov     rax, [r8+18h]
0x140017e61  mov     rcx, [rax+18h]
0x140017e65  mov     [rbx+0A0h], rcx
0x140017e6c  xor     edx, edx; struct IXMLDOMNode *
0x140017e6e  mov     rcx, [r8+18h]; this
0x140017e72  call    ?SetParamNode@LinkAndRTFExtension@@QEAAXPEAUIXMLDOMNode@@@Z; LinkAndRTFExtension::SetParamNode(IXMLDOMNode *)
0x140017e77  mov     rax, [rbp+arg_0]
0x140017e7b  mov     rcx, [rax+18h]
0x140017e7f  mov     eax, [rcx+20h]
0x140017e82  mov     [rbx+0B8h], eax
0x140017e88  mov     rcx, rbx; this
0x140017e8b  call    ?OnSetActive@InteractivityTextPage@@MEAA_JXZ; InteractivityTextPage::OnSetActive(void)
0x140017e90  mov     rax, [rbp+arg_0]
0x140017e94  test    rax, rax
0x140017e97  jz      short loc_140017EBA
0x140017e99  mov     rcx, [rax+18h]; this
0x140017e9d  test    rcx, rcx
0x140017ea0  jz      short loc_140017EBA
0x140017ea2  mov     rdx, [rbx+0A0h]; struct IXMLDOMNode *
0x140017ea9  call    ?SetParamNode@LinkAndRTFExtension@@QEAAXPEAUIXMLDOMNode@@@Z; LinkAndRTFExtension::SetParamNode(IXMLDOMNode *)
0x140017eae  mov     rax, [rbp+arg_0]
0x140017eb2  mov     qword ptr [rax+18h], 0
0x140017eba  mov     edx, [rbp+var_8]
0x140017ebd  test    edx, edx
0x140017ebf  jz      short loc_140017ED2
0x140017ec1  mov     rcx, [rbp+var_10]
0x140017ec5  call    cs:__imp_?EndDefer@Element@DirectUI@@QEAAXK@Z; DirectUI::Element::EndDefer(ulong)
0x140017ecc  nop     dword ptr [rax+rax+00h]
0x140017ed1  nop
0x140017ed2  xor     eax, eax
0x140017ed4  mov     rbx, [rsp+40h+arg_8]
0x140017ed9  add     rsp, 40h
0x140017edd  pop     rbp
0x140017ede  retn
```
