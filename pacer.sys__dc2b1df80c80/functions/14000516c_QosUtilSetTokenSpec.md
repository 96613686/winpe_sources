# QosUtilSetTokenSpec

- ea: `0x14000516c`
- end: `0x1400051c5`
- name: `QosUtilSetTokenSpec`
- size: `89`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140004c58`
- `0x1400120f8`

## callees

- `0x14000516c`

## pseudocode

```c
__int64 __fastcall QosUtilSetTokenSpec(__int64 *a1, __int64 *a2, char a3)
{
  __int64 v3; // rax
  __int64 result; // rax

  v3 = a2[1];
  if ( a3 )
  {
    if ( v3 == -1 )
    {
      *a1 = 0;
      a1[1] = 0x7FFFFFFFFFFFFFFFLL;
    }
    else
    {
      *a1 = v3;
      a1[1] = a2[1];
    }
  }
  else
  {
    if ( v3 == -1 )
      v3 = 0x7FFFFFFFFFFFFFFFLL;
    a1[1] = v3;
    if ( *a1 > v3 )
      *a1 = v3;
  }
  result = *a2;
  a1[2] = *a2;
  return result;
}

```

## disassembly

```asm
0x14000516c  mov     rax, [rdx+8]
0x140005170  test    r8b, r8b
0x140005173  jnz     short loc_140005195
0x140005175  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140005179  mov     r8, 7FFFFFFFFFFFFFFFh
0x140005183  cmovz   rax, r8
0x140005187  mov     [rcx+8], rax
0x14000518b  cmp     [rcx], rax
0x14000518e  jle     short loc_1400051BD
0x140005190  mov     [rcx], rax
0x140005193  jmp     short loc_1400051BD
0x140005195  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140005199  jnz     short loc_1400051B2
0x14000519b  mov     r8, 7FFFFFFFFFFFFFFFh
0x1400051a5  mov     qword ptr [rcx], 0
0x1400051ac  mov     [rcx+8], r8
0x1400051b0  jmp     short loc_1400051BD
0x1400051b2  mov     [rcx], rax
0x1400051b5  mov     rax, [rdx+8]
0x1400051b9  mov     [rcx+8], rax
0x1400051bd  mov     rax, [rdx]
0x1400051c0  mov     [rcx+10h], rax
0x1400051c4  retn
```
