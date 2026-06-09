# AslAnsiStringFree

- ea: `0x140009648`
- end: `0x140009697`
- name: `AslAnsiStringFree`
- size: `79`
- prototype: `BOOLEAN __fastcall(__int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140006308`
- `0x140006460`
- `0x140006cb4`

## callees

- `0x14000233f`
- `0x140009648`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x140009685`
- `ntdll!RtlFreeHeap` at `0x140009685`

## pseudocode

```c
BOOLEAN __fastcall AslAnsiStringFree(__int64 a1)
{
  void *v2; // rcx
  BOOLEAN result; // al
  void *v4; // r8

  if ( a1 )
  {
    v2 = *(void **)(a1 + 8);
    if ( v2 )
    {
      result = (unsigned __int8)memset_0(v2, 66, *(unsigned __int16 *)(a1 + 2));
      v4 = *(void **)(a1 + 8);
      if ( v4 )
        result = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
    }
    *(_OWORD *)a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x140009648  test    rcx, rcx
0x14000964b  jz      short locret_140009696
0x14000964d  push    rbx
0x14000964e  sub     rsp, 20h
0x140009652  mov     rbx, rcx
0x140009655  mov     rcx, [rcx+8]; void *
0x140009659  test    rcx, rcx
0x14000965c  jz      short loc_14000968B
0x14000965e  movzx   r8d, word ptr [rbx+2]; Size
0x140009663  mov     edx, 42h ; 'B'; Val
0x140009668  call    memset_0
0x14000966d  mov     r8, [rbx+8]; P
0x140009671  test    r8, r8
0x140009674  jz      short loc_14000968B
0x140009676  mov     rcx, gs:60h
0x14000967f  xor     edx, edx; Flags
0x140009681  mov     rcx, [rcx+30h]; HeapHandle
0x140009685  call    cs:__imp_RtlFreeHeap
0x14000968b  xorps   xmm0, xmm0
0x14000968e  movups  xmmword ptr [rbx], xmm0
0x140009691  add     rsp, 20h
0x140009695  pop     rbx
0x140009696  retn
```
