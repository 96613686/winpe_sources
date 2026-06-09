# WnfSubscriberT<ulong>::~WnfSubscriberT<ulong>(void)

- ea: `0x18000d698`
- end: `0x18000d6f7`
- name: `??1?$WnfSubscriberT@K@@UEAA@XZ`
- size: `95`
- prototype: `int __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180034c9e`

## callees

- `0x18000d698`
- `0x18000d9f4`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d6cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d6eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d6cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d6eb`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000d6b4`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000d6b4`

## pseudocode

```c
int __fastcall WnfSubscriberT<unsigned long>::~WnfSubscriberT<unsigned long>(_QWORD *a1)
{
  void *v2; // rcx
  int result; // eax
  void *v4; // rcx

  *a1 = &WnfSubscriberT<unsigned long>::`vftable';
  if ( a1[2] )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion();
    a1[2] = 0;
  }
  v2 = (void *)a1[3];
  if ( v2 )
  {
    CloseHandle(v2);
    a1[3] = 0;
  }
  result = std::_Tree<std::_Tset_traits<std::shared_ptr<std::function<void (unsigned long const &)>>,std::less<std::shared_ptr<std::function<void (unsigned long const &)>>>,std::allocator<std::shared_ptr<std::function<void (unsigned long const &)>>>,0>>::~_Tree<std::_Tset_traits<std::shared_ptr<std::function<void (unsigned long const &)>>,std::less<std::shared_ptr<std::function<void (unsigned long const &)>>>,std::allocator<std::shared_ptr<std::function<void (unsigned long const &)>>>,0>>(a1 + 6);
  v4 = (void *)a1[3];
  if ( v4 )
    return CloseHandle(v4);
  return result;
}

```

## disassembly

```asm
0x18000d698  push    rbx
0x18000d69a  sub     rsp, 20h
0x18000d69e  lea     rax, ??_7?$WnfSubscriberT@K@@6B@; const WnfSubscriberT<ulong>::`vftable'
0x18000d6a5  mov     rbx, rcx
0x18000d6a8  mov     [rcx], rax
0x18000d6ab  mov     rcx, [rcx+10h]
0x18000d6af  test    rcx, rcx
0x18000d6b2  jz      short loc_18000D6C2
0x18000d6b4  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18000d6ba  mov     qword ptr [rbx+10h], 0
0x18000d6c2  mov     rcx, [rbx+18h]; hObject
0x18000d6c6  test    rcx, rcx
0x18000d6c9  jz      short loc_18000D6D9
0x18000d6cb  call    cs:__imp_CloseHandle
0x18000d6d1  mov     qword ptr [rbx+18h], 0
0x18000d6d9  lea     rcx, [rbx+30h]
0x18000d6dd  call    ??1?$_Tree@V?$_Tset_traits@V?$shared_ptr@V?$function@$$A6AXAEBK@Z@std@@@std@@U?$less@V?$shared_ptr@V?$function@$$A6AXAEBK@Z@std@@@std@@@2@V?$allocator@V?$shared_ptr@V?$function@$$A6AXAEBK@Z@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::shared_ptr<std::function<void (ulong const &)>>,std::less<std::shared_ptr<std::function<void (ulong const &)>>>,std::allocator<std::shared_ptr<std::function<void (ulong const &)>>>,0>>::~_Tree<std::_Tset_traits<std::shared_ptr<std::function<void (ulong const &)>>,std::less<std::shared_ptr<std::function<void (ulong const &)>>>,std::allocator<std::shared_ptr<std::function<void (ulong const &)>>>,0>>(void)
0x18000d6e2  mov     rcx, [rbx+18h]; hObject
0x18000d6e6  test    rcx, rcx
0x18000d6e9  jz      short loc_18000D6F1
0x18000d6eb  call    cs:__imp_CloseHandle
0x18000d6f1  add     rsp, 20h
0x18000d6f5  pop     rbx
0x18000d6f6  retn
```
