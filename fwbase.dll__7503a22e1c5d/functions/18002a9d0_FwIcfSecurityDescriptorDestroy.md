# FwIcfSecurityDescriptorDestroy

- ea: `0x18002a9d0`
- end: `0x18002a9ed`
- name: `FwIcfSecurityDescriptorDestroy`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180004840`

## pseudocode

```c
void __fastcall FwIcfSecurityDescriptorDestroy(void **a1)
{
  FwFree(*a1);
  *(_OWORD *)a1 = 0;
}

```

## disassembly

```asm
0x18002a9d0  push    rbx
0x18002a9d2  sub     rsp, 20h
0x18002a9d6  mov     rbx, rcx
0x18002a9d9  mov     rcx, [rcx]
0x18002a9dc  call    FwFree
0x18002a9e1  xorps   xmm0, xmm0
0x18002a9e4  movups  xmmword ptr [rbx], xmm0
0x18002a9e7  add     rsp, 20h
0x18002a9eb  pop     rbx
0x18002a9ec  retn
```
