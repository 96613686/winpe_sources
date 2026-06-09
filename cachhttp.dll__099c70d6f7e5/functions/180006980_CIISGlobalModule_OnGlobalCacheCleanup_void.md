# CIISGlobalModule::OnGlobalCacheCleanup(void)

- ea: `0x180006980`
- end: `0x18000698a`
- name: `?OnGlobalCacheCleanup@CIISGlobalModule@@UEAA?AW4GLOBAL_NOTIFICATION_STATUS@@XZ`
- size: `10`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003d10`

## pseudocode

```c
__int64 CIISGlobalModule::OnGlobalCacheCleanup()
{
  return GlobalDoWork(4, 0);
}

```

## disassembly

```asm
0x180006980  xor     edx, edx
0x180006982  lea     ecx, [rdx+4]
0x180006985  jmp     ?GlobalDoWork@@YA?AW4GLOBAL_NOTIFICATION_STATUS@@KPEAVIHttpEventProvider@@@Z; GlobalDoWork(ulong,IHttpEventProvider *)
```
