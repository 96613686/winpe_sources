# CS_PathXtraOrig

- ea: `0x140059594`
- end: `0x1400595c6`
- name: `CS_PathXtraOrig`
- size: `50`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14006ab90`
- `0x14006b0cc`

## callees

- `0x140059594`
- `0x1400595cc`

## pseudocode

```c
_WORD *__fastcall CS_PathXtraOrig(__int64 a1, int a2)
{
  _WORD *result; // rax

  for ( result = (_WORD *)CS_PathXtraCross(a1, a2);
        (*result & 0x800) != 0;
        result = (_WORD *)CS_PathXtraCross((__int64)result, a2) )
  {
    ;
  }
  return result;
}

```

## disassembly

```asm
0x140059594  mov     [rsp+arg_0], rbx
0x140059599  push    rdi
0x14005959a  sub     rsp, 20h
0x14005959e  mov     ebx, edx
0x1400595a0  call    CS_PathXtraCross
0x1400595a5  mov     edi, 800h
0x1400595aa  test    [rax], di
0x1400595ad  jnz     short loc_1400595BA
0x1400595af  mov     rbx, [rsp+28h+arg_0]
0x1400595b4  add     rsp, 20h
0x1400595b8  pop     rdi
0x1400595b9  retn
0x1400595ba  mov     edx, ebx
0x1400595bc  mov     rcx, rax
0x1400595bf  call    CS_PathXtraCross
0x1400595c4  jmp     short loc_1400595AA
```
