# std::list<_CEventSource<CComObjectObserver>::ObserverData,std::allocator<_CEventSource<CComObjectObserver>::ObserverData>>::~list<_CEventSource<CComObjectObserver>::ObserverData,std::allocator<_CEventSource<CComObjectObserver>::ObserverData>>(void)

- ea: `0x180007908`
- end: `0x180007925`
- name: `??1?$list@UObserverData@?$_CEventSource@VCComObjectObserver@@@@V?$allocator@UObserverData@?$_CEventSource@VCComObjectObserver@@@@@std@@@std@@QEAA@XZ`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180005590`

## callees

- `0x18000792c`

## import_xrefs

- `MFC42u!__imp_??3@YAXPEAX@Z` at `0x18000791e`

## pseudocode

```c
void __fastcall std::list<_CEventSource<CComObjectObserver>::ObserverData,std::allocator<_CEventSource<CComObjectObserver>::ObserverData>>::~list<_CEventSource<CComObjectObserver>::ObserverData,std::allocator<_CEventSource<CComObjectObserver>::ObserverData>>(
        void **a1)
{
  std::list<_CEventSource<CComObjectObserver>::ObserverData,std::allocator<_CEventSource<CComObjectObserver>::ObserverData>>::clear((__int64)a1);
  operator delete(*a1);
}

```

## disassembly

```asm
0x180007908  push    rbx
0x18000790a  sub     rsp, 20h
0x18000790e  mov     rbx, rcx
0x180007911  call    ?clear@?$list@UObserverData@?$_CEventSource@VCComObjectObserver@@@@V?$allocator@UObserverData@?$_CEventSource@VCComObjectObserver@@@@@std@@@std@@QEAAXXZ; std::list<_CEventSource<CComObjectObserver>::ObserverData,std::allocator<_CEventSource<CComObjectObserver>::ObserverData>>::clear(void)
0x180007916  mov     rcx, [rbx]
0x180007919  add     rsp, 20h
0x18000791d  pop     rbx
0x18000791e  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
