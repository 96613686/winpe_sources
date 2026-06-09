# SecMakeSPN

- ea: `0x180022790`
- end: `0x1800227de`
- name: `SecMakeSPN`
- size: `78`
- prototype: `NTSTATUS __stdcall(PUNICODE_STRING ServiceClass, PUNICODE_STRING ServiceName, PUNICODE_STRING InstanceName, USHORT InstancePort, PUNICODE_STRING Referrer, PUNICODE_STRING Spn, PULONG Length, BOOLEAN Allocate)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180022850`

## pseudocode

```c
NTSTATUS __stdcall SecMakeSPN(
        PUNICODE_STRING ServiceClass,
        PUNICODE_STRING ServiceName,
        PUNICODE_STRING InstanceName,
        USHORT InstancePort,
        PUNICODE_STRING Referrer,
        PUNICODE_STRING Spn,
        PULONG Length,
        BOOLEAN Allocate)
{
  return SecMakeSPNEx2(ServiceClass, ServiceName, InstanceName, InstancePort, Referrer, 0, Spn, Length, Allocate, 1u);
}

```

## disassembly

```asm
0x180022790  mov     r11, rsp
0x180022793  sub     rsp, 58h
0x180022797  mov     al, [rsp+58h+Allocate]
0x18002279e  mov     [rsp+58h+IsTargetInfoMarshaled], 1; IsTargetInfoMarshaled
0x1800227a3  mov     [rsp+58h+var_18], al; Allocate
0x1800227a7  mov     rax, [rsp+58h+Length]
0x1800227af  mov     [r11-20h], rax
0x1800227b3  mov     rax, [rsp+58h+Spn]
0x1800227bb  mov     [r11-28h], rax
0x1800227bf  mov     rax, [rsp+58h+Referrer]
0x1800227c7  mov     qword ptr [r11-30h], 0
0x1800227cf  mov     [r11-38h], rax
0x1800227d3  call    SecMakeSPNEx2
0x1800227d8  add     rsp, 58h
0x1800227dc  retn
```
