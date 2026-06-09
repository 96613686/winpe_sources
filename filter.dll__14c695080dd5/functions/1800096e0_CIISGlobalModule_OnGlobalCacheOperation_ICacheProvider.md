# CIISGlobalModule::OnGlobalCacheOperation(ICacheProvider *)

- ea: `0x1800096e0`
- end: `0x1800096ea`
- name: `?OnGlobalCacheOperation@CIISGlobalModule@@UEAA?AW4GLOBAL_NOTIFICATION_STATUS@@PEAVICacheProvider@@@Z`
- size: `10`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002fc0`

## pseudocode

```c
__int64 __fastcall CIISGlobalModule::OnGlobalCacheOperation(__int64 a1, __int64 a2)
{
  return GlobalDoWork(16, a2);
}

```

## disassembly

```asm
0x1800096e0  mov     ecx, 10h
0x1800096e5  jmp     ?GlobalDoWork@@YA?AW4GLOBAL_NOTIFICATION_STATUS@@KPEAVIHttpEventProvider@@@Z; GlobalDoWork(ulong,IHttpEventProvider *)
```
