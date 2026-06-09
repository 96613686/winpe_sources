# KsecSetDeviceSecurity

- ea: `0x180020f30`
- end: `0x180020f52`
- name: `KsecSetDeviceSecurity`
- size: `34`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18002b078`

## import_xrefs

- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x180020f40`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x180020f40`

## pseudocode

```c
__int64 __fastcall KsecSetDeviceSecurity(__int64 a1)
{
  return ObSetSecurityObjectByPointer(a1, 31, g_HardCodedSd);
}

```

## disassembly

```asm
0x180020f30  sub     rsp, 28h
0x180020f34  lea     r8, g_HardCodedSd
0x180020f3b  mov     edx, 1Fh
0x180020f40  call    cs:__imp_ObSetSecurityObjectByPointer
0x180020f47  nop     dword ptr [rax+rax+00h]
0x180020f4c  add     rsp, 28h
0x180020f50  retn
```
