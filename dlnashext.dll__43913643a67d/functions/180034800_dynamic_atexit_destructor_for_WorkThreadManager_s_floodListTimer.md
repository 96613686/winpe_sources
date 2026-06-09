# _dynamic_atexit_destructor_for__WorkThreadManager::s_floodListTimer__

- ea: `0x180034800`
- end: `0x18003481b`
- name: `_dynamic_atexit_destructor_for__WorkThreadManager::s_floodListTimer__`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180034800`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180034810`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180034810`

## pseudocode

```c
void dynamic_atexit_destructor_for__WorkThreadManager::s_floodListTimer__()
{
  if ( WorkThreadManager::s_floodListTimer )
    CloseThreadpoolTimer(WorkThreadManager::s_floodListTimer);
}

```

## disassembly

```asm
0x180034800  sub     rsp, 28h
0x180034804  mov     rcx, cs:?s_floodListTimer@WorkThreadManager@@0V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$01@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; pti
0x18003480b  test    rcx, rcx
0x18003480e  jz      short loc_180034816
0x180034810  call    cs:__imp_CloseThreadpoolTimer
0x180034816  add     rsp, 28h
0x18003481a  retn
```
