# CMSMQRuleSet::CMSMQRuleSet(void)

- ea: `0x18000a130`
- end: `0x18000a20a`
- name: `??0CMSMQRuleSet@@QEAA@XZ`
- size: `218`
- prototype: `CMSMQRuleSet *__fastcall(CMSMQRuleSet *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000e388`

## callees

- `0x180003984`
- `0x180005740`

## import_xrefs

- `ATL!__imp_AtlComPtrAssign` at `0x18000a1d2`
- `ATL!__imp_AtlComPtrAssign` at `0x18000a1d2`

## pseudocode

```c
CMSMQRuleSet *__fastcall CMSMQRuleSet::CMSMQRuleSet(CMSMQRuleSet *this)
{
  char *v2; // rdi
  char *v3; // rbx
  __int64 v4; // rax

  *((_DWORD *)this + 4) = 0;
  *(_OWORD *)((char *)this + 24) = 0;
  *(_OWORD *)((char *)this + 40) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_BYTE *)this + 64) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 140) = 0;
  *((_QWORD *)this + 145) = 0;
  *((_QWORD *)this + 146) = 0;
  *((_QWORD *)this + 147) = 0;
  *(_OWORD *)((char *)this + 1128) = 0;
  *(_OWORD *)((char *)this + 1144) = 0;
  v2 = (char *)this + 1184;
  *((_QWORD *)this + 148) = 0;
  v3 = (char *)this + 1192;
  v4 = std::_Tree<std::_Tmap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>,R<CRuntimeTriggerInfo>,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70> const,R<CRuntimeTriggerInfo>>>,0>>::_Buynode();
  *((_QWORD *)v3 + 1) = v4;
  *(_BYTE *)(v4 + 73) = 1;
  *(_QWORD *)(*((_QWORD *)v3 + 1) + 8LL) = *((_QWORD *)v3 + 1);
  **((_QWORD **)v3 + 1) = *((_QWORD *)v3 + 1);
  *(_QWORD *)(*((_QWORD *)v3 + 1) + 16LL) = *((_QWORD *)v3 + 1);
  *((_QWORD *)v3 + 2) = 0;
  AtlComPtrAssign(v2, 0);
  *((_QWORD *)this + 11) = 0;
  _bstr_t::operator=((char *)this + 1120, L"MSMQRuleSet");
  *((_BYTE *)this + 80) = 0;
  return this;
}

```

## disassembly

```asm
0x18000a130  mov     [rsp+arg_10], rbx
0x18000a135  mov     [rsp+arg_18], rsi
0x18000a13a  mov     [rsp+arg_0], rcx
0x18000a13f  push    rdi
0x18000a140  sub     rsp, 20h
0x18000a144  mov     rsi, rcx
0x18000a147  mov     dword ptr [rcx+10h], 0
0x18000a14e  xorps   xmm0, xmm0
0x18000a151  xor     eax, eax
0x18000a153  movups  xmmword ptr [rcx+18h], xmm0
0x18000a157  movups  xmmword ptr [rcx+28h], xmm0
0x18000a15b  mov     [rcx+38h], rax
0x18000a15f  mov     [rcx+40h], al
0x18000a162  mov     [rcx+48h], rax
0x18000a166  mov     [rcx+460h], rax
0x18000a16d  mov     [rcx+488h], rax
0x18000a174  mov     [rcx+490h], rax
0x18000a17b  mov     [rcx+498h], rax
0x18000a182  movups  xmmword ptr [rcx+468h], xmm0
0x18000a189  movups  xmmword ptr [rcx+478h], xmm0
0x18000a190  lea     rdi, [rcx+4A0h]
0x18000a197  mov     [rdi], rax
0x18000a19a  lea     rbx, [rcx+4A8h]
0x18000a1a1  call    ?_Buynode@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@V?$R@VCRuntimeTriggerInfo@@@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@V?$R@VCRuntimeTriggerInfo@@@@@std@@@2@$0A@@std@@@std@@IEAAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@V?$R@VCRuntimeTriggerInfo@@@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@V?$R@VCRuntimeTriggerInfo@@@@@std@@@2@$0A@@std@@@2@XZ; std::_Tree<std::_Tmap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>,R<CRuntimeTriggerInfo>,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70> const,R<CRuntimeTriggerInfo>>>,0>>::_Buynode(void)
0x18000a1a6  mov     [rbx+8], rax
0x18000a1aa  mov     byte ptr [rax+49h], 1
0x18000a1ae  mov     rax, [rbx+8]
0x18000a1b2  mov     [rax+8], rax
0x18000a1b6  mov     rax, [rbx+8]
0x18000a1ba  mov     [rax], rax
0x18000a1bd  mov     rax, [rbx+8]
0x18000a1c1  mov     [rax+10h], rax
0x18000a1c5  mov     qword ptr [rbx+10h], 0
0x18000a1cd  xor     edx, edx
0x18000a1cf  mov     rcx, rdi
0x18000a1d2  call    cs:__imp_AtlComPtrAssign
0x18000a1d8  mov     qword ptr [rsi+58h], 0
0x18000a1e0  lea     rcx, [rsi+460h]
0x18000a1e7  lea     rdx, aMsmqruleset; "MSMQRuleSet"
0x18000a1ee  call    ??4_bstr_t@@QEAAAEAV0@PEB_W@Z; _bstr_t::operator=(wchar_t const *)
0x18000a1f3  mov     byte ptr [rsi+50h], 0
0x18000a1f7  mov     rax, rsi
0x18000a1fa  mov     rbx, [rsp+28h+arg_10]
0x18000a1ff  mov     rsi, [rsp+28h+arg_18]
0x18000a204  add     rsp, 20h
0x18000a208  pop     rdi
0x18000a209  retn
```
