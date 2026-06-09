# DoDerefProtocolCBWork

- ea: `0x140010f40`
- end: `0x140010f73`
- name: `DoDerefProtocolCBWork`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14002a83c`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140010f58`
- `ntoskrnl!KeSetEvent` at `0x140010f58`

## pseudocode

```c
__int64 __fastcall DoDerefProtocolCBWork(__int64 a1)
{
  _QWORD *v1; // rbx

  v1 = (_QWORD *)(a1 - 24);
  KeSetEvent((PRKEVENT)(a1 - 24 + 304), 1, 0);
  return RemoveProtocolCBFromBundle(v1);
}

```

## disassembly

```asm
0x140010f40  push    rbx
0x140010f42  sub     rsp, 20h
0x140010f46  xor     r8d, r8d; Wait
0x140010f49  lea     rbx, [rcx-18h]
0x140010f4d  lea     rcx, [rbx+130h]; Event
0x140010f54  lea     edx, [r8+1]; Increment
0x140010f58  call    cs:__imp_KeSetEvent
0x140010f5f  nop     dword ptr [rax+rax+00h]
0x140010f64  mov     rcx, rbx
0x140010f67  call    RemoveProtocolCBFromBundle
0x140010f6c  add     rsp, 20h
0x140010f70  pop     rbx
0x140010f71  retn
```
