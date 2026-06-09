# CMSMQPropertyBag::CMSMQPropertyBag(void)

- ea: `0x180002f08`
- end: `0x180002f7a`
- name: `??0CMSMQPropertyBag@@QEAA@XZ`
- size: `114`
- prototype: `CMSMQPropertyBag *__fastcall(CMSMQPropertyBag *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000df28`
- `0x18000e1cc`

## callees

- `0x180003984`

## import_xrefs

- `ATL!__imp_AtlComPtrAssign` at `0x180002f60`
- `ATL!__imp_AtlComPtrAssign` at `0x180002f60`

## pseudocode

```c
CMSMQPropertyBag *__fastcall CMSMQPropertyBag::CMSMQPropertyBag(CMSMQPropertyBag *this)
{
  __int64 v2; // rax

  *((_DWORD *)this + 4) = 0;
  *((_QWORD *)this + 3) = 0;
  v2 = std::_Tree<std::_Tmap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>,R<CRuntimeTriggerInfo>,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70> const,R<CRuntimeTriggerInfo>>>,0>>::_Buynode();
  *((_QWORD *)this + 5) = v2;
  *(_BYTE *)(v2 + 73) = 1;
  *(_QWORD *)(*((_QWORD *)this + 5) + 8LL) = *((_QWORD *)this + 5);
  **((_QWORD **)this + 5) = *((_QWORD *)this + 5);
  *(_QWORD *)(*((_QWORD *)this + 5) + 16LL) = *((_QWORD *)this + 5);
  *((_QWORD *)this + 6) = 0;
  AtlComPtrAssign((char *)this + 24, 0);
  return this;
}

```

## disassembly

```asm
0x180002f08  mov     [rsp+arg_10], rbx
0x180002f0d  mov     [rsp+arg_18], rsi
0x180002f12  mov     [rsp+arg_0], rcx
0x180002f17  push    rdi
0x180002f18  sub     rsp, 20h
0x180002f1c  mov     rsi, rcx
0x180002f1f  mov     dword ptr [rcx+10h], 0
0x180002f26  mov     qword ptr [rcx+18h], 0
0x180002f2e  call    ?_Buynode@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@V?$R@VCRuntimeTriggerInfo@@@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@V?$R@VCRuntimeTriggerInfo@@@@@std@@@2@$0A@@std@@@std@@IEAAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@V?$R@VCRuntimeTriggerInfo@@@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@V?$R@VCRuntimeTriggerInfo@@@@@std@@@2@$0A@@std@@@2@XZ; std::_Tree<std::_Tmap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>,R<CRuntimeTriggerInfo>,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70> const,R<CRuntimeTriggerInfo>>>,0>>::_Buynode(void)
0x180002f33  mov     [rsi+28h], rax
0x180002f37  mov     byte ptr [rax+49h], 1
0x180002f3b  mov     rax, [rsi+28h]
0x180002f3f  mov     [rax+8], rax
0x180002f43  mov     rax, [rsi+28h]
0x180002f47  mov     [rax], rax
0x180002f4a  mov     rax, [rsi+28h]
0x180002f4e  mov     [rax+10h], rax
0x180002f52  mov     qword ptr [rsi+30h], 0
0x180002f5a  xor     edx, edx
0x180002f5c  lea     rcx, [rsi+18h]
0x180002f60  call    cs:__imp_AtlComPtrAssign
0x180002f66  nop
0x180002f67  mov     rax, rsi
0x180002f6a  mov     rbx, [rsp+28h+arg_10]
0x180002f6f  mov     rsi, [rsp+28h+arg_18]
0x180002f74  add     rsp, 20h
0x180002f78  pop     rdi
0x180002f79  retn
```
