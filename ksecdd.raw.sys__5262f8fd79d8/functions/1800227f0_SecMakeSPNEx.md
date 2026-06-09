# SecMakeSPNEx

- ea: `0x1800227f0`
- end: `0x180022842`
- name: `SecMakeSPNEx`
- size: `82`
- prototype: `NTSTATUS __stdcall(PUNICODE_STRING ServiceClass, PUNICODE_STRING ServiceName, PUNICODE_STRING InstanceName, USHORT InstancePort, PUNICODE_STRING Referrer, PUNICODE_STRING TargetInfo, PUNICODE_STRING Spn, PULONG Length, BOOLEAN Allocate)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180022850`

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
0x1800227f0  mov     r11, rsp
0x1800227f3  sub     rsp, 58h
0x1800227f7  mov     al, [rsp+58h+Allocate]
0x1800227fe  mov     [rsp+58h+IsTargetInfoMarshaled], 1; IsTargetInfoMarshaled
0x180022803  mov     [rsp+58h+var_18], al; Allocate
0x180022807  mov     rax, [rsp+58h+Length]
0x18002280f  mov     [r11-20h], rax
0x180022813  mov     rax, [rsp+58h+Spn]
0x18002281b  mov     [r11-28h], rax
0x18002281f  mov     rax, [rsp+58h+TargetInfo]
0x180022827  mov     [r11-30h], rax
0x18002282b  mov     rax, [rsp+58h+Referrer]
0x180022833  mov     [r11-38h], rax
0x180022837  call    SecMakeSPNEx2
0x18002283c  add     rsp, 58h
0x180022840  retn
```
