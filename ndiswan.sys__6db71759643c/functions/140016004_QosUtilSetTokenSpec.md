# QosUtilSetTokenSpec

- ea: `0x140016004`
- end: `0x14001605d`
- name: `QosUtilSetTokenSpec`
- size: `89`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140014434`
- `0x14001554c`

## callees

- `0x140016004`

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
0x140016004  mov     rax, [rdx+8]
0x140016008  test    r8b, r8b
0x14001600b  jnz     short loc_14001602D
0x14001600d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140016011  mov     r8, 7FFFFFFFFFFFFFFFh
0x14001601b  cmovz   rax, r8
0x14001601f  mov     [rcx+8], rax
0x140016023  cmp     [rcx], rax
0x140016026  jle     short loc_140016055
0x140016028  mov     [rcx], rax
0x14001602b  jmp     short loc_140016055
0x14001602d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140016031  jnz     short loc_14001604A
0x140016033  mov     r8, 7FFFFFFFFFFFFFFFh
0x14001603d  mov     qword ptr [rcx], 0
0x140016044  mov     [rcx+8], r8
0x140016048  jmp     short loc_140016055
0x14001604a  mov     [rcx], rax
0x14001604d  mov     rax, [rdx+8]
0x140016051  mov     [rcx+8], rax
0x140016055  mov     rax, [rdx]
0x140016058  mov     [rcx+10h], rax
0x14001605c  retn
```
