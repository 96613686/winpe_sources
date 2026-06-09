# CountAndCopyAddrs

- ea: `0x14001e800`
- end: `0x14001e835`
- name: `CountAndCopyAddrs`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140018a64`

## callees

- `0x14001e800`

## pseudocode

```c
__int64 __fastcall CountAndCopyAddrs(int *a1, __int64 a2, unsigned int *a3)
{
  unsigned int v3; // r9d
  int v4; // r10d
  __int64 result; // rax

  v3 = *a3;
  if ( a1 )
  {
    while ( 1 )
    {
      v4 = *a1;
      if ( *a1 == -1 )
        break;
      if ( v4 )
      {
        if ( a2 )
        {
          result = v3;
          *(_DWORD *)(a2 + 4LL * v3) = v4;
        }
        ++v3;
      }
      ++a1;
    }
  }
  *a3 = v3;
  return result;
}

```

## disassembly

```asm
0x14001e800  mov     r9d, [r8]
0x14001e803  test    rcx, rcx
0x14001e806  jnz     short loc_14001E80D
0x14001e808  mov     [r8], r9d
0x14001e80b  retn
0x14001e80d  or      r11d, 0FFFFFFFFh
0x14001e811  mov     r10d, [rcx]
0x14001e814  cmp     r10d, r11d
0x14001e817  jz      short loc_14001E808
0x14001e819  test    r10d, r10d
0x14001e81c  jz      short loc_14001E826
0x14001e81e  test    rdx, rdx
0x14001e821  jnz     short loc_14001E82C
0x14001e823  inc     r9d
0x14001e826  add     rcx, 4
0x14001e82a  jmp     short loc_14001E811
0x14001e82c  mov     eax, r9d
0x14001e82f  mov     [rdx+rax*4], r10d
0x14001e833  jmp     short loc_14001E823
```
