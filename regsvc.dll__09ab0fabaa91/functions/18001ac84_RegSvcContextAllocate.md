# RegSvcContextAllocate

- ea: `0x18001ac84`
- end: `0x18001acc1`
- name: `RegSvcContextAllocate`
- size: `61`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `10`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180019290`
- `0x1800199a0`
- `0x18001a2d0`
- `0x18001a410`
- `0x18001a5b0`
- `0x18001a710`
- `0x18001a8d0`
- `0x18001a9f0`
- `0x18001aa60`
- `0x18001aad0`

## callees

- `0x18001ac84`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18001aca3`
- `ntdll!RtlAllocateHeap` at `0x18001aca3`

## pseudocode

```c
__int64 __fastcall RegSvcContextAllocate(_QWORD *a1)
{
  PVOID Heap; // rdx
  __int64 result; // rax

  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x10u);
  if ( !Heap )
    return 14;
  result = 0;
  *a1 = Heap;
  return result;
}

```

## disassembly

```asm
0x18001ac84  push    rbx
0x18001ac86  sub     rsp, 20h
0x18001ac8a  mov     rbx, rcx
0x18001ac8d  mov     edx, 8; Flags
0x18001ac92  mov     rcx, gs:60h
0x18001ac9b  lea     r8d, [rdx+8]; Size
0x18001ac9f  mov     rcx, [rcx+30h]; HeapHandle
0x18001aca3  call    cs:__imp_RtlAllocateHeap
0x18001aca9  mov     rdx, rax
0x18001acac  test    rax, rax
0x18001acaf  jnz     short loc_18001ACB6
0x18001acb1  lea     eax, [rdx+0Eh]
0x18001acb4  jmp     short loc_18001ACBB
0x18001acb6  xor     eax, eax
0x18001acb8  mov     [rbx], rdx
0x18001acbb  add     rsp, 20h
0x18001acbf  pop     rbx
0x18001acc0  retn
```
