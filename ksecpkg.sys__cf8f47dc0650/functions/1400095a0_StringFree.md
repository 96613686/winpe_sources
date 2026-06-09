# StringFree

- ea: `0x1400095a0`
- end: `0x1400095cd`
- name: `StringFree`
- size: `45`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x140008af4`
- `0x140009208`
- `0x140009678`
- `0x140009bc4`
- `0x140009e7c`
- `0x14000a40c`
- `0x140028600`

## callees

- `0x140008ad0`
- `0x1400095a0`

## pseudocode

```c
__int64 __fastcall StringFree(__int64 a1)
{
  __int64 v2; // rcx

  if ( a1 )
  {
    v2 = *(_QWORD *)(a1 + 8);
    if ( v2 )
    {
      DigestFreeMemory(v2);
      *(_DWORD *)a1 = 0;
      *(_QWORD *)(a1 + 8) = 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1400095a0  push    rbx
0x1400095a2  sub     rsp, 20h
0x1400095a6  mov     rbx, rcx
0x1400095a9  test    rcx, rcx
0x1400095ac  jz      short loc_1400095C4
0x1400095ae  mov     rcx, [rcx+8]
0x1400095b2  test    rcx, rcx
0x1400095b5  jz      short loc_1400095C4
0x1400095b7  call    DigestFreeMemory
0x1400095bc  xor     eax, eax
0x1400095be  mov     [rbx], eax
0x1400095c0  mov     [rbx+8], rax
0x1400095c4  xor     eax, eax
0x1400095c6  add     rsp, 20h
0x1400095ca  pop     rbx
0x1400095cb  retn
```
