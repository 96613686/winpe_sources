# CsrpFreeSecurityContext

- ea: `0x1800084e0`
- end: `0x18000852b`
- name: `CsrpFreeSecurityContext`
- size: `75`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800073d0`
- `0x1800095c0`

## callees

- `0x1800084e0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800084f5`
- `ntdll!RtlFreeHeap` at `0x1800084f5`
- `ntdll!RtlFreeHeap` at `0x180008518`

## pseudocode

```c
BOOLEAN __fastcall CsrpFreeSecurityContext(__int64 a1)
{
  BOOLEAN result; // al
  void *v3; // r8

  result = RtlFreeHeap(CsrHeap, 0, *(PVOID *)a1);
  v3 = *(void **)(a1 + 8);
  if ( v3 )
    return RtlFreeHeap(CsrHeap, 0, v3);
  return result;
}

```

## disassembly

```asm
0x1800084e0  push    rbx
0x1800084e2  sub     rsp, 20h
0x1800084e6  mov     r8, [rcx]; BaseAddress
0x1800084e9  mov     rbx, rcx
0x1800084ec  mov     rcx, cs:CsrHeap; HeapHandle
0x1800084f3  xor     edx, edx; Flags
0x1800084f5  call    cs:__imp_RtlFreeHeap
0x1800084fc  nop     dword ptr [rax+rax+00h]
0x180008501  mov     r8, [rbx+8]
0x180008505  test    r8, r8
0x180008508  jz      short loc_180008524
0x18000850a  mov     rcx, cs:CsrHeap
0x180008511  xor     edx, edx
0x180008513  add     rsp, 20h
0x180008517  pop     rbx
0x180008518  jmp     cs:__imp_RtlFreeHeap
0x180008524  add     rsp, 20h
0x180008528  pop     rbx
0x180008529  retn
```
