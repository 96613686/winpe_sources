# CIISGlobalModule::OnGlobalPreBeginRequest(IPreBeginRequestProvider *)

- ea: `0x1800029b0`
- end: `0x1800029ba`
- name: `?OnGlobalPreBeginRequest@CIISGlobalModule@@UEAA?AW4GLOBAL_NOTIFICATION_STATUS@@PEAVIPreBeginRequestProvider@@@Z`
- size: `10`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002858`

## pseudocode

```c
__int64 __fastcall CIISGlobalModule::OnGlobalPreBeginRequest(__int64 a1, __int64 a2)
{
  return GlobalDoWork(256, a2);
}

```

## disassembly

```asm
0x1800029b0  mov     ecx, 100h
0x1800029b5  jmp     ?GlobalDoWork@@YA?AW4GLOBAL_NOTIFICATION_STATUS@@KPEAVIHttpEventProvider@@@Z; GlobalDoWork(ulong,IHttpEventProvider *)
```
