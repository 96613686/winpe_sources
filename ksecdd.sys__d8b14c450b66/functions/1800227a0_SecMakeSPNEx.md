# SecMakeSPNEx

- ea: `0x1800227a0`
- end: `0x1800227f2`
- name: `SecMakeSPNEx`
- size: `82`
- prototype: `NTSTATUS __stdcall(PUNICODE_STRING ServiceClass, PUNICODE_STRING ServiceName, PUNICODE_STRING InstanceName, USHORT InstancePort, PUNICODE_STRING Referrer, PUNICODE_STRING TargetInfo, PUNICODE_STRING Spn, PULONG Length, BOOLEAN Allocate)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180022800`

## pseudocode

```c
NTSTATUS __stdcall SecMakeSPNEx(
        PUNICODE_STRING ServiceClass,
        PUNICODE_STRING ServiceName,
        PUNICODE_STRING InstanceName,
        USHORT InstancePort,
        PUNICODE_STRING Referrer,
        PUNICODE_STRING TargetInfo,
        PUNICODE_STRING Spn,
        PULONG Length,
        BOOLEAN Allocate)
{
  return SecMakeSPNEx2(
           ServiceClass,
           ServiceName,
           InstanceName,
           InstancePort,
           Referrer,
           TargetInfo,
           Spn,
           Length,
           Allocate,
           1u);
}

```

## disassembly

```asm
0x1800227a0  mov     r11, rsp
0x1800227a3  sub     rsp, 58h
0x1800227a7  mov     al, [rsp+58h+Allocate]
0x1800227ae  mov     [rsp+58h+IsTargetInfoMarshaled], 1; IsTargetInfoMarshaled
0x1800227b3  mov     [rsp+58h+var_18], al; Allocate
0x1800227b7  mov     rax, [rsp+58h+Length]
0x1800227bf  mov     [r11-20h], rax
0x1800227c3  mov     rax, [rsp+58h+Spn]
0x1800227cb  mov     [r11-28h], rax
0x1800227cf  mov     rax, [rsp+58h+TargetInfo]
0x1800227d7  mov     [r11-30h], rax
0x1800227db  mov     rax, [rsp+58h+Referrer]
0x1800227e3  mov     [r11-38h], rax
0x1800227e7  call    SecMakeSPNEx2
0x1800227ec  add     rsp, 58h
0x1800227f0  retn
```
