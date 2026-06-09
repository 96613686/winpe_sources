# operator==(BOID const &,BOID const &)

- ea: `0x140003f44`
- end: `0x140003f6b`
- name: `??8@YAHAEBUBOID@@0@Z`
- size: `39`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140003ecc`
- `0x140018b9c`
- `0x14001fbb4`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140003f4e`
- `ntoskrnl!RtlCompareMemory` at `0x140003f4e`

## pseudocode

```c
_BOOL8 __fastcall operator==(const void *a1, const void *a2)
{
  return RtlCompareMemory(a1, a2, 0x10u) == 16;
}

```

## disassembly

```asm
0x140003f44  sub     rsp, 28h
0x140003f48  mov     r8d, 10h; Length
0x140003f4e  call    cs:__imp_RtlCompareMemory
0x140003f55  nop     dword ptr [rax+rax+00h]
0x140003f5a  xor     ecx, ecx
0x140003f5c  cmp     rax, 10h
0x140003f60  setz    cl
0x140003f63  mov     eax, ecx
0x140003f65  add     rsp, 28h
0x140003f69  retn
```
