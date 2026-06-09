# AslAnsiStringFree

- ea: `0x180005334`
- end: `0x180005385`
- name: `AslAnsiStringFree`
- size: `81`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800033c0`
- `0x180003560`
- `0x180009e80`

## callees

- `0x180005334`
- `0x18000bffe`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000537d`
- `ntdll!RtlFreeHeap` at `0x18000537d`

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
0x180005334  test    rcx, rcx
0x180005337  jz      short locret_180005355
0x180005339  push    rbx
0x18000533a  sub     rsp, 20h
0x18000533e  mov     rbx, rcx
0x180005341  mov     rcx, [rcx+8]; void *
0x180005345  test    rcx, rcx
0x180005348  jnz     short loc_180005356
0x18000534a  xorps   xmm0, xmm0
0x18000534d  movups  xmmword ptr [rbx], xmm0
0x180005350  add     rsp, 20h
0x180005354  pop     rbx
0x180005355  retn
0x180005356  movzx   r8d, word ptr [rbx+2]; Size
0x18000535b  mov     edx, 42h ; 'B'; Val
0x180005360  call    memset_0
0x180005365  mov     r8, [rbx+8]; P
0x180005369  test    r8, r8
0x18000536c  jz      short loc_18000534A
0x18000536e  mov     rcx, gs:60h
0x180005377  xor     edx, edx; Flags
0x180005379  mov     rcx, [rcx+30h]; HeapHandle
0x18000537d  call    cs:__imp_RtlFreeHeap
0x180005383  jmp     short loc_18000534A
```
