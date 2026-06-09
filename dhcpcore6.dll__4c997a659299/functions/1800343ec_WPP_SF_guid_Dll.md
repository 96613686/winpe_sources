# WPP_SF__guid_Dll

- ea: `0x1800343ec`
- end: `0x180034452`
- name: `WPP_SF__guid_Dll`
- size: `102`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180008440`

## callees

- `0x180017a20`

## pseudocode

```c
ULONG WPP_SF__guid_Dll()
{
  return FastWppTraceMessage(1025, 0x11u, (ULONGLONG)WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids);
}

```

## disassembly

```asm
0x1800343ec  mov     r11, rsp
0x1800343ef  sub     rsp, 78h
0x1800343f3  mov     qword ptr [r11-20h], 0
0x1800343fb  lea     rax, [r11+38h]
0x1800343ff  mov     edx, 11h
0x180034404  mov     [rsp+78h+var_18], 4D4h
0x18003440c  mov     r10d, 401h
0x180034412  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x180034419  lea     ecx, [rdx-0Dh]
0x18003441c  mov     [r11-28h], rcx
0x180034420  mov     [r11-30h], rax
0x180034424  lea     rax, [r11+30h]
0x180034428  mov     [r11-38h], rcx
0x18003442c  mov     [r11-40h], rax
0x180034430  lea     rax, [r11-18h]
0x180034434  mov     [r11-48h], rcx
0x180034438  mov     ecx, r10d
0x18003443b  mov     [r11-50h], rax
0x18003443f  mov     qword ptr [r11-58h], 10h
0x180034447  call    FastWppTraceMessage
0x18003444c  add     rsp, 78h
0x180034450  retn
```
