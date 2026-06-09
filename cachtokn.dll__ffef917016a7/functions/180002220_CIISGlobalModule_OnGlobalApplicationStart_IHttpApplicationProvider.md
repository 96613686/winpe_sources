# CIISGlobalModule::OnGlobalApplicationStart(IHttpApplicationProvider *)

- ea: `0x180002220`
- end: `0x18000222a`
- name: `?OnGlobalApplicationStart@CIISGlobalModule@@UEAA?AW4GLOBAL_NOTIFICATION_STATUS@@PEAVIHttpApplicationProvider@@@Z`
- size: `10`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180001280`

## pseudocode

```c
__int64 __fastcall CIISGlobalModule::OnGlobalApplicationStart(__int64 a1, __int64 *a2)
{
  return GlobalDoWork(512, a2);
}

```

## disassembly

```asm
0x180002220  mov     ecx, 200h
0x180002225  jmp     ?GlobalDoWork@@YA?AW4GLOBAL_NOTIFICATION_STATUS@@KPEAVIHttpEventProvider@@@Z; GlobalDoWork(ulong,IHttpEventProvider *)
```
