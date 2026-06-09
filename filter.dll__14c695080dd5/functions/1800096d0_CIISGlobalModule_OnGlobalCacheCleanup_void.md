# CIISGlobalModule::OnGlobalCacheCleanup(void)

- ea: `0x1800096d0`
- end: `0x1800096da`
- name: `?OnGlobalCacheCleanup@CIISGlobalModule@@UEAA?AW4GLOBAL_NOTIFICATION_STATUS@@XZ`
- size: `10`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002fc0`

## pseudocode

```c
__int64 CIISGlobalModule::OnGlobalCacheCleanup()
{
  return GlobalDoWork(4, 0);
}

```

## disassembly

```asm
0x1800096d0  xor     edx, edx
0x1800096d2  lea     ecx, [rdx+4]
0x1800096d5  jmp     ?GlobalDoWork@@YA?AW4GLOBAL_NOTIFICATION_STATUS@@KPEAVIHttpEventProvider@@@Z; GlobalDoWork(ulong,IHttpEventProvider *)
```
