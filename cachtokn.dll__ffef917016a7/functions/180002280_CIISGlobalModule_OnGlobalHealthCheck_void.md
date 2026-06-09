# CIISGlobalModule::OnGlobalHealthCheck(void)

- ea: `0x180002280`
- end: `0x18000228a`
- name: `?OnGlobalHealthCheck@CIISGlobalModule@@UEAA?AW4GLOBAL_NOTIFICATION_STATUS@@XZ`
- size: `10`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180001280`

## pseudocode

```c
__int64 CIISGlobalModule::OnGlobalHealthCheck()
{
  return GlobalDoWork(32, 0);
}

```

## disassembly

```asm
0x180002280  xor     edx, edx
0x180002282  lea     ecx, [rdx+20h]
0x180002285  jmp     ?GlobalDoWork@@YA?AW4GLOBAL_NOTIFICATION_STATUS@@KPEAVIHttpEventProvider@@@Z; GlobalDoWork(ulong,IHttpEventProvider *)
```
