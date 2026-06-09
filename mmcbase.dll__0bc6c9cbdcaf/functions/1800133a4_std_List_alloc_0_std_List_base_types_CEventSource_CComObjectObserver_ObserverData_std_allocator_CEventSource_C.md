# std::_List_alloc<0,std::_List_base_types<_CEventSource<CComObjectObserver>::ObserverData,std::allocator<_CEventSource<CComObjectObserver>::ObserverData>>>::_Buynode0(std::_List_node<_CEventSource<CComObjectObserver>::ObserverData,void *> *,std::_List_node<_CEventSource<CComObjectObserver>::ObserverData,void *> *)

- ea: `0x1800133a4`
- end: `0x1800133d4`
- name: `?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@UObserverData@?$_CEventSource@VCComObjectObserver@@@@V?$allocator@UObserverData@?$_CEventSource@VCComObjectObserver@@@@@std@@@std@@@std@@QEAAPEAU?$_List_node@UObserverData@?$_CEventSource@VCComObjectObserver@@@@PEAX@2@PEAU32@0@Z`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180013190`

## callees

- `0x180009928`
- `0x1800133a4`

## import_xrefs

- `MFC42u!__imp_??2@YAPEAX_K@Z` at `0x1800133b2`
- `MFC42u!__imp_??2@YAPEAX_K@Z` at `0x1800133b2`

## pseudocode

```c
_QWORD *std::_List_alloc<0,std::_List_base_types<_CEventSource<CComObjectObserver>::ObserverData,std::allocator<_CEventSource<CComObjectObserver>::ObserverData>>>::_Buynode0()
{
  _QWORD *result; // rax

  result = operator new(0x20u);
  if ( !result )
    std::_Xbad_alloc();
  try
  {
    *result = result;
    result[1] = result;
  }
  catch ( ... )
  {
    operator delete(result);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x1800133a4  mov     [rsp+arg_10], r8
0x1800133a9  sub     rsp, 28h
0x1800133ad  mov     ecx, 20h ; ' '
0x1800133b2  call    cs:__imp_??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800133b8  mov     [rsp+28h+arg_10], rax
0x1800133bd  test    rax, rax
0x1800133c0  jnz     short loc_1800133C8
0x1800133c2  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x1800133c8  mov     [rax], rax
0x1800133cb  mov     [rax+8], rax
0x1800133cf  add     rsp, 28h
0x1800133d3  retn
```
