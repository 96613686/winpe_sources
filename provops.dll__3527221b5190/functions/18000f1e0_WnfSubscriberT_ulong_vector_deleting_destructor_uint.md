# WnfSubscriberT<ulong>::`vector deleting destructor'(uint)

- ea: `0x18000f1e0`
- end: `0x18000f25c`
- name: `??_E?$WnfSubscriberT@K@@UEAAPEAXI@Z`
- size: `124`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x18000d9f4`
- `0x18000f1e0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000f248`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f248`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f219`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f239`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f219`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f239`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000f202`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000f202`

## pseudocode

```c
_QWORD *__fastcall WnfSubscriberT<unsigned long>::`vector deleting destructor'(_QWORD *a1, char a2)
{
  void *v4; // rcx
  void *v5; // rcx

  *a1 = &WnfSubscriberT<unsigned long>::`vftable';
  if ( a1[2] )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion();
    a1[2] = 0;
  }
  v4 = (void *)a1[3];
  if ( v4 )
  {
    CloseHandle(v4);
    a1[3] = 0;
  }
  std::_Tree<std::_Tset_traits<std::shared_ptr<std::function<void (unsigned long const &)>>,std::less<std::shared_ptr<std::function<void (unsigned long const &)>>>,std::allocator<std::shared_ptr<std::function<void (unsigned long const &)>>>,0>>::~_Tree<std::_Tset_traits<std::shared_ptr<std::function<void (unsigned long const &)>>,std::less<std::shared_ptr<std::function<void (unsigned long const &)>>>,std::allocator<std::shared_ptr<std::function<void (unsigned long const &)>>>,0>>(a1 + 6);
  v5 = (void *)a1[3];
  if ( v5 )
    CloseHandle(v5);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x18000f1e0  mov     [rsp+arg_0], rbx
0x18000f1e5  push    rdi
0x18000f1e6  sub     rsp, 20h
0x18000f1ea  lea     rax, ??_7?$WnfSubscriberT@K@@6B@; const WnfSubscriberT<ulong>::`vftable'
0x18000f1f1  mov     rbx, rcx
0x18000f1f4  mov     [rcx], rax
0x18000f1f7  mov     edi, edx
0x18000f1f9  mov     rcx, [rcx+10h]
0x18000f1fd  test    rcx, rcx
0x18000f200  jz      short loc_18000F210
0x18000f202  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18000f208  mov     qword ptr [rbx+10h], 0
0x18000f210  mov     rcx, [rbx+18h]; hObject
0x18000f214  test    rcx, rcx
0x18000f217  jz      short loc_18000F227
0x18000f219  call    cs:__imp_CloseHandle
0x18000f21f  mov     qword ptr [rbx+18h], 0
0x18000f227  lea     rcx, [rbx+30h]
0x18000f22b  call    ??1?$_Tree@V?$_Tset_traits@V?$shared_ptr@V?$function@$$A6AXAEBK@Z@std@@@std@@U?$less@V?$shared_ptr@V?$function@$$A6AXAEBK@Z@std@@@std@@@2@V?$allocator@V?$shared_ptr@V?$function@$$A6AXAEBK@Z@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::shared_ptr<std::function<void (ulong const &)>>,std::less<std::shared_ptr<std::function<void (ulong const &)>>>,std::allocator<std::shared_ptr<std::function<void (ulong const &)>>>,0>>::~_Tree<std::_Tset_traits<std::shared_ptr<std::function<void (ulong const &)>>,std::less<std::shared_ptr<std::function<void (ulong const &)>>>,std::allocator<std::shared_ptr<std::function<void (ulong const &)>>>,0>>(void)
0x18000f230  mov     rcx, [rbx+18h]; hObject
0x18000f234  test    rcx, rcx
0x18000f237  jz      short loc_18000F23F
0x18000f239  call    cs:__imp_CloseHandle
0x18000f23f  test    dil, 1
0x18000f243  jz      short loc_18000F24E
0x18000f245  mov     rcx, rbx
0x18000f248  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000f24e  mov     rax, rbx
0x18000f251  mov     rbx, [rsp+28h+arg_0]
0x18000f256  add     rsp, 20h
0x18000f25a  pop     rdi
0x18000f25b  retn
```
