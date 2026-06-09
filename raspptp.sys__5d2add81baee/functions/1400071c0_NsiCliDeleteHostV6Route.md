# NsiCliDeleteHostV6Route

- ea: `0x1400071c0`
- end: `0x1400071d7`
- name: `NsiCliDeleteHostV6Route`
- size: `23`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001c1a0`

## callees

- `0x1400070f0`

## pseudocode

```c
__int64 __fastcall NsiCliDeleteHostV6Route(__int64 a1)
{
  return NsiCliDeleteHostRouteHelper(0x17u, a1);
}

```

## disassembly

```asm
0x1400071c0  sub     rsp, 28h
0x1400071c4  mov     rdx, rcx
0x1400071c7  mov     ecx, 17h
0x1400071cc  call    NsiCliDeleteHostRouteHelper
0x1400071d1  add     rsp, 28h
0x1400071d5  retn
```
