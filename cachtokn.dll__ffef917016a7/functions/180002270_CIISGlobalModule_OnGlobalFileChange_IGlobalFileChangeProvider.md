# CIISGlobalModule::OnGlobalFileChange(IGlobalFileChangeProvider *)

- ea: `0x180002270`
- end: `0x18000227a`
- name: `?OnGlobalFileChange@CIISGlobalModule@@UEAA?AW4GLOBAL_NOTIFICATION_STATUS@@PEAVIGlobalFileChangeProvider@@@Z`
- size: `10`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180001280`

## pseudocode

```c
__int64 __fastcall CIISGlobalModule::OnGlobalFileChange(__int64 a1, __int64 *a2)
{
  return GlobalDoWork(128, a2);
}

```

## disassembly

```asm
0x180002270  mov     ecx, 80h
0x180002275  jmp     ?GlobalDoWork@@YA?AW4GLOBAL_NOTIFICATION_STATUS@@KPEAVIHttpEventProvider@@@Z; GlobalDoWork(ulong,IHttpEventProvider *)
```
