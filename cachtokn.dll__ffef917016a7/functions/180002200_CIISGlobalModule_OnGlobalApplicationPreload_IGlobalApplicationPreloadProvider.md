# CIISGlobalModule::OnGlobalApplicationPreload(IGlobalApplicationPreloadProvider *)

- ea: `0x180002200`
- end: `0x18000220a`
- name: `?OnGlobalApplicationPreload@CIISGlobalModule@@UEAA?AW4GLOBAL_NOTIFICATION_STATUS@@PEAVIGlobalApplicationPreloadProvider@@@Z`
- size: `10`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180001280`

## pseudocode

```c
__int64 __fastcall CIISGlobalModule::OnGlobalApplicationPreload(__int64 a1, __int64 *a2)
{
  return GlobalDoWork(0x10000, a2);
}

```

## disassembly

```asm
0x180002200  mov     ecx, 10000h
0x180002205  jmp     ?GlobalDoWork@@YA?AW4GLOBAL_NOTIFICATION_STATUS@@KPEAVIHttpEventProvider@@@Z; GlobalDoWork(ulong,IHttpEventProvider *)
```
