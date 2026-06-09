# SecMakeSPN

- ea: `0x180022740`
- end: `0x18002278e`
- name: `SecMakeSPN`
- size: `78`
- prototype: `NTSTATUS __stdcall(PUNICODE_STRING ServiceClass, PUNICODE_STRING ServiceName, PUNICODE_STRING InstanceName, USHORT InstancePort, PUNICODE_STRING Referrer, PUNICODE_STRING Spn, PULONG Length, BOOLEAN Allocate)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180022800`

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
0x180022740  mov     r11, rsp
0x180022743  sub     rsp, 58h
0x180022747  mov     al, [rsp+58h+Allocate]
0x18002274e  mov     [rsp+58h+IsTargetInfoMarshaled], 1; IsTargetInfoMarshaled
0x180022753  mov     [rsp+58h+var_18], al; Allocate
0x180022757  mov     rax, [rsp+58h+Length]
0x18002275f  mov     [r11-20h], rax
0x180022763  mov     rax, [rsp+58h+Spn]
0x18002276b  mov     [r11-28h], rax
0x18002276f  mov     rax, [rsp+58h+Referrer]
0x180022777  mov     qword ptr [r11-30h], 0
0x18002277f  mov     [r11-38h], rax
0x180022783  call    SecMakeSPNEx2
0x180022788  add     rsp, 58h
0x18002278c  retn
```
