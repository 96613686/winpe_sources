# CIISGlobalModule::OnGlobalApplicationStop(IHttpApplicationProvider *)

- ea: `0x180002230`
- end: `0x18000223a`
- name: `?OnGlobalApplicationStop@CIISGlobalModule@@UEAA?AW4GLOBAL_NOTIFICATION_STATUS@@PEAVIHttpApplicationProvider@@@Z`
- size: `10`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180001280`

## pseudocode

```c
__int64 __fastcall CIISGlobalModule::OnGlobalApplicationStop(__int64 a1, __int64 *a2)
{
  return GlobalDoWork(2048, a2);
}

```

## disassembly

```asm
0x180002230  mov     ecx, 800h
0x180002235  jmp     ?GlobalDoWork@@YA?AW4GLOBAL_NOTIFICATION_STATUS@@KPEAVIHttpEventProvider@@@Z; GlobalDoWork(ulong,IHttpEventProvider *)
```
