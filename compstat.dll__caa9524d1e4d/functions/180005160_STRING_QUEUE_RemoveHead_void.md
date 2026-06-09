# STRING_QUEUE::RemoveHead(void)

- ea: `0x180005160`
- end: `0x180005189`
- name: `?RemoveHead@STRING_QUEUE@@QEAAPEAVSTRING_QUEUE_ITEM@@XZ`
- size: `41`
- prototype: `struct STRING_QUEUE_ITEM *__fastcall(STRING_QUEUE *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180004d40`
- `0x180004d70`
- `0x180008120`

## callees

- `0x180005160`

## pseudocode

```c
struct STRING_QUEUE_ITEM *__fastcall STRING_QUEUE::RemoveHead(STRING_QUEUE *this)
{
  struct STRING_QUEUE_ITEM *result; // rax
  STRING_QUEUE *v2; // rdx

  result = *(struct STRING_QUEUE_ITEM **)this;
  if ( *(STRING_QUEUE **)this == this )
    return 0;
  if ( *((STRING_QUEUE **)result + 1) != this
    || (v2 = *(STRING_QUEUE **)result, *(struct STRING_QUEUE_ITEM **)(*(_QWORD *)result + 8LL) != result) )
  {
    __fastfail(3u);
  }
  *(_QWORD *)this = v2;
  *((_QWORD *)v2 + 1) = this;
  return result;
}

```

## disassembly

```asm
0x180005160  mov     rax, [rcx]
0x180005163  cmp     rax, rcx
0x180005166  jz      short loc_18000517F
0x180005168  cmp     [rax+8], rcx
0x18000516c  jnz     short loc_180005182
0x18000516e  mov     rdx, [rax]
0x180005171  cmp     [rdx+8], rax
0x180005175  jnz     short loc_180005182
0x180005177  mov     [rcx], rdx
0x18000517a  mov     [rdx+8], rcx
0x18000517e  retn
0x18000517f  xor     eax, eax
0x180005181  retn
0x180005182  mov     ecx, 3
0x180005187  int     29h; Win8: RtlFailFast(ecx)
```
