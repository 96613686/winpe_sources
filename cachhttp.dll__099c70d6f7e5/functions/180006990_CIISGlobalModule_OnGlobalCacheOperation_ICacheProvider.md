# CIISGlobalModule::OnGlobalCacheOperation(ICacheProvider *)

- ea: `0x180006990`
- end: `0x18000699a`
- name: `?OnGlobalCacheOperation@CIISGlobalModule@@UEAA?AW4GLOBAL_NOTIFICATION_STATUS@@PEAVICacheProvider@@@Z`
- size: `10`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003d10`

## pseudocode

```c
__int64 __fastcall CIISGlobalModule::OnGlobalCacheOperation(__int64 a1, __int64 a2)
{
  return GlobalDoWork(16, a2);
}

```

## disassembly

```asm
0x180006990  mov     ecx, 10h
0x180006995  jmp     ?GlobalDoWork@@YA?AW4GLOBAL_NOTIFICATION_STATUS@@KPEAVIHttpEventProvider@@@Z; GlobalDoWork(ulong,IHttpEventProvider *)
```
