# CIISGlobalModule::OnGlobalCacheCleanup(void)

- ea: `0x180001d80`
- end: `0x180001d8a`
- name: `?OnGlobalCacheCleanup@CIISGlobalModule@@UEAA?AW4GLOBAL_NOTIFICATION_STATUS@@XZ`
- size: `10`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180001010`

## pseudocode

```c
__int64 CIISGlobalModule::OnGlobalCacheCleanup()
{
  return GlobalDoWork((void *)4, 0);
}

```

## disassembly

```asm
0x180001d80  xor     edx, edx
0x180001d82  lea     ecx, [rdx+4]
0x180001d85  jmp     ?GlobalDoWork@@YA?AW4GLOBAL_NOTIFICATION_STATUS@@KPEAVIHttpEventProvider@@@Z; GlobalDoWork(ulong,IHttpEventProvider *)
```
