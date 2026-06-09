# GetComObjectEventSource(void)

- ea: `0x180013190`
- end: `0x180013215`
- name: `?GetComObjectEventSource@@YAAEAV?$CEventSource@VCComObjectObserver@@VCVoid@@V2@V2@V2@@@XZ`
- size: `133`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000a0f4`
- `0x18000a1c8`
- `0x18000a238`
- `0x180013190`
- `0x1800133a4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void *GetComObjectEventSource()
{
  if ( dword_18002F928 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_18002F928);
    if ( dword_18002F928 == -1 )
    {
      qword_18002B408 = std::_List_alloc<0,std::_List_base_types<_CEventSource<CComObjectObserver>::ObserverData,std::allocator<_CEventSource<CComObjectObserver>::ObserverData>>>::_Buynode0();
      dword_18002B418 = 0;
      off_18002B400 = &CEventSource<CComObjectObserver,CVoid,CVoid,CVoid,CVoid>::`vftable';
      atexit(GetComObjectEventSource_::_2_::_dynamic_atexit_destructor_for__evSource__);
      Init_thread_footer(&dword_18002F928);
    }
  }
  return &off_18002B400;
}

```

## disassembly

```asm
0x180013190  sub     rsp, 28h
0x180013194  mov     ecx, cs:_tls_index
0x18001319a  mov     rax, gs:58h
0x1800131a3  mov     edx, 4
0x1800131a8  mov     rax, [rax+rcx*8]
0x1800131ac  mov     eax, [rdx+rax]
0x1800131af  cmp     cs:dword_18002F928, eax
0x1800131b5  jle     short loc_180013209
0x1800131b7  lea     rcx, dword_18002F928
0x1800131be  call    _Init_thread_header
0x1800131c3  cmp     cs:dword_18002F928, 0FFFFFFFFh
0x1800131ca  jnz     short loc_180013209
0x1800131cc  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@UObserverData@?$_CEventSource@VCComObjectObserver@@@@V?$allocator@UObserverData@?$_CEventSource@VCComObjectObserver@@@@@std@@@std@@@std@@QEAAPEAU?$_List_node@UObserverData@?$_CEventSource@VCComObjectObserver@@@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<_CEventSource<CComObjectObserver>::ObserverData,std::allocator<_CEventSource<CComObjectObserver>::ObserverData>>>::_Buynode0(std::_List_node<_CEventSource<CComObjectObserver>::ObserverData,void *> *,std::_List_node<_CEventSource<CComObjectObserver>::ObserverData,void *> *)
0x1800131d1  mov     cs:qword_18002B408, rax
0x1800131d8  mov     cs:dword_18002B418, 0
0x1800131e2  lea     rax, ??_7?$CEventSource@VCComObjectObserver@@VCVoid@@V2@V2@V2@@@6B@; const CEventSource<CComObjectObserver,CVoid,CVoid,CVoid,CVoid>::`vftable'
0x1800131e9  mov     cs:off_18002B400, rax
0x1800131f0  lea     rcx, _GetComObjectEventSource____2____dynamic_atexit_destructor_for__evSource__; void (__cdecl *)()
0x1800131f7  call    atexit
0x1800131fc  nop
0x1800131fd  lea     rcx, dword_18002F928
0x180013204  call    _Init_thread_footer
0x180013209  lea     rax, off_18002B400
0x180013210  add     rsp, 28h
0x180013214  retn
```
