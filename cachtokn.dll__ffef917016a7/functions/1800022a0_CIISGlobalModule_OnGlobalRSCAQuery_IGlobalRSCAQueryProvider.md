# CIISGlobalModule::OnGlobalRSCAQuery(IGlobalRSCAQueryProvider *)

- ea: `0x1800022a0`
- end: `0x1800022aa`
- name: `?OnGlobalRSCAQuery@CIISGlobalModule@@UEAA?AW4GLOBAL_NOTIFICATION_STATUS@@PEAVIGlobalRSCAQueryProvider@@@Z`
- size: `10`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180001280`

## pseudocode

```c
__int64 __fastcall CIISGlobalModule::OnGlobalRSCAQuery(__int64 a1, __int64 *a2)
{
  return GlobalDoWork(4096, a2);
}

```

## disassembly

```asm
0x1800022a0  mov     ecx, 1000h
0x1800022a5  jmp     ?GlobalDoWork@@YA?AW4GLOBAL_NOTIFICATION_STATUS@@KPEAVIHttpEventProvider@@@Z; GlobalDoWork(ulong,IHttpEventProvider *)
```
