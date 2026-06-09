# VarCreateList

- ea: `0x14000dec0`
- end: `0x14000df0f`
- name: `VarCreateList`
- size: `79`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140001cf0`
- `0x140007934`

## callees

- `0x140008620`
- `0x14000dec0`

## import_xrefs

- `msvcrt!malloc` at `0x14000dece`
- `msvcrt!malloc` at `0x14000dece`

## string_xrefs

- `0x14000ded9`: `attempting to create a variable list`

## pseudocode

```c
_QWORD *__fastcall VarCreateList(__int64 a1)
{
  _QWORD *result; // rax

  result = malloc(0x10u);
  if ( result )
  {
    *result = 0;
    result[1] = 0;
  }
  else
  {
    ErrSet(a1, "Out of memory: %1", "%s", "attempting to create a variable list");
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000dec0  push    rbx
0x14000dec2  sub     rsp, 20h
0x14000dec6  mov     rbx, rcx
0x14000dec9  mov     ecx, 10h; Size
0x14000dece  call    cs:__imp_malloc
0x14000ded4  test    rax, rax
0x14000ded7  jnz     short loc_14000DEFA
0x14000ded9  lea     r9, aAttemptingToCr; "attempting to create a variable list"
0x14000dee0  mov     rcx, rbx
0x14000dee3  lea     r8, aS_4; "%s"
0x14000deea  lea     rdx, aOutOfMemory1_0; "Out of memory: %1"
0x14000def1  call    ErrSet
0x14000def6  xor     eax, eax
0x14000def8  jmp     short loc_14000DF09
0x14000defa  mov     qword ptr [rax], 0
0x14000df01  mov     qword ptr [rax+8], 0
0x14000df09  add     rsp, 20h
0x14000df0d  pop     rbx
0x14000df0e  retn
```
