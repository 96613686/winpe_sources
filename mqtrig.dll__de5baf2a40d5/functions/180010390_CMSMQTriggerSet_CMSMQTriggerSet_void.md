# CMSMQTriggerSet::CMSMQTriggerSet(void)

- ea: `0x180010390`
- end: `0x18001046a`
- name: `??0CMSMQTriggerSet@@QEAA@XZ`
- size: `218`
- prototype: `CMSMQTriggerSet *__fastcall(CMSMQTriggerSet *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000e0e4`
- `0x18000e488`

## callees

- `0x180003984`
- `0x180005740`

## import_xrefs

- `ATL!__imp_AtlComPtrAssign` at `0x180010432`
- `ATL!__imp_AtlComPtrAssign` at `0x180010432`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CMSMQTriggerSet *__fastcall CMSMQTriggerSet::CMSMQTriggerSet(CMSMQTriggerSet *this)
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
  _bstr_t::operator=((char *)this + 1120, L"MSMQTriggerSet");
  *((_BYTE *)this + 80) = 0;
  return this;
}

```

## disassembly

```asm
0x180010390  mov     [rsp+arg_10], rbx
0x180010395  mov     [rsp+arg_18], rsi
0x18001039a  mov     [rsp+arg_0], rcx
0x18001039f  push    rdi
0x1800103a0  sub     rsp, 20h
0x1800103a4  mov     rsi, rcx
0x1800103a7  mov     dword ptr [rcx+10h], 0
0x1800103ae  xorps   xmm0, xmm0
0x1800103b1  xor     eax, eax
0x1800103b3  movups  xmmword ptr [rcx+18h], xmm0
0x1800103b7  movups  xmmword ptr [rcx+28h], xmm0
0x1800103bb  mov     [rcx+38h], rax
0x1800103bf  mov     [rcx+40h], al
0x1800103c2  mov     [rcx+48h], rax
0x1800103c6  mov     [rcx+460h], rax
0x1800103cd  mov     [rcx+488h], rax
0x1800103d4  mov     [rcx+490h], rax
0x1800103db  mov     [rcx+498h], rax
0x1800103e2  movups  xmmword ptr [rcx+468h], xmm0
0x1800103e9  movups  xmmword ptr [rcx+478h], xmm0
0x1800103f0  lea     rdi, [rcx+4A0h]
0x1800103f7  mov     [rdi], rax
0x1800103fa  lea     rbx, [rcx+4A8h]
0x180010401  call    ?_Buynode@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@V?$R@VCRuntimeTriggerInfo@@@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@V?$R@VCRuntimeTriggerInfo@@@@@std@@@2@$0A@@std@@@std@@IEAAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@V?$R@VCRuntimeTriggerInfo@@@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@V?$R@VCRuntimeTriggerInfo@@@@@std@@@2@$0A@@std@@@2@XZ; std::_Tree<std::_Tmap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>,R<CRuntimeTriggerInfo>,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70> const,R<CRuntimeTriggerInfo>>>,0>>::_Buynode(void)
0x180010406  mov     [rbx+8], rax
0x18001040a  mov     byte ptr [rax+49h], 1
0x18001040e  mov     rax, [rbx+8]
0x180010412  mov     [rax+8], rax
0x180010416  mov     rax, [rbx+8]
0x18001041a  mov     [rax], rax
0x18001041d  mov     rax, [rbx+8]
0x180010421  mov     [rax+10h], rax
0x180010425  mov     qword ptr [rbx+10h], 0
0x18001042d  xor     edx, edx
0x18001042f  mov     rcx, rdi
0x180010432  call    cs:__imp_AtlComPtrAssign
0x180010438  mov     qword ptr [rsi+58h], 0
0x180010440  lea     rcx, [rsi+460h]
0x180010447  lea     rdx, aMsmqtriggerset; "MSMQTriggerSet"
0x18001044e  call    ??4_bstr_t@@QEAAAEAV0@PEB_W@Z; _bstr_t::operator=(wchar_t const *)
0x180010453  mov     byte ptr [rsi+50h], 0
0x180010457  mov     rax, rsi
0x18001045a  mov     rbx, [rsp+28h+arg_10]
0x18001045f  mov     rsi, [rsp+28h+arg_18]
0x180010464  add     rsp, 20h
0x180010468  pop     rdi
0x180010469  retn
```
