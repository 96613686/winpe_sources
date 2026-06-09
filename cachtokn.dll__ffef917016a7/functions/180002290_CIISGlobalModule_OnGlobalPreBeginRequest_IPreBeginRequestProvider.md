# CIISGlobalModule::OnGlobalPreBeginRequest(IPreBeginRequestProvider *)

- ea: `0x180002290`
- end: `0x18000229a`
- name: `?OnGlobalPreBeginRequest@CIISGlobalModule@@UEAA?AW4GLOBAL_NOTIFICATION_STATUS@@PEAVIPreBeginRequestProvider@@@Z`
- size: `10`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180001280`

## pseudocode

```c
__int64 __fastcall CIISGlobalModule::OnGlobalPreBeginRequest(__int64 a1, __int64 *a2)
{
  return GlobalDoWork(256, a2);
}

```

## disassembly

```asm
0x180002290  mov     ecx, 100h
0x180002295  jmp     ?GlobalDoWork@@YA?AW4GLOBAL_NOTIFICATION_STATUS@@KPEAVIHttpEventProvider@@@Z; GlobalDoWork(ulong,IHttpEventProvider *)
```
