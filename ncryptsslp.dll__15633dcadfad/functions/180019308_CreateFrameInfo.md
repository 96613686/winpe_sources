# _CreateFrameInfo

- ea: `0x180019308`
- end: `0x180019342`
- name: `_CreateFrameInfo`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001a650`

## callees

- `0x180019308`
- `0x1800194ec`

## pseudocode

```c
_QWORD *__fastcall CreateFrameInfo(_QWORD *a1, __int64 a2)
{
  __int64 v3; // rcx

  *a1 = a2;
  if ( (unsigned __int64)a1 >= *(_QWORD *)(_vcrt_getptd() + 88) )
    v3 = 0;
  else
    v3 = *(_QWORD *)(_vcrt_getptd() + 88);
  a1[1] = v3;
  *(_QWORD *)(_vcrt_getptd() + 88) = a1;
  return a1;
}

```

## disassembly

```asm
0x180019308  push    rbx
0x18001930a  sub     rsp, 20h
0x18001930e  mov     rbx, rcx
0x180019311  mov     [rcx], rdx
0x180019314  call    __vcrt_getptd
0x180019319  cmp     rbx, [rax+58h]
0x18001931d  jnb     short loc_18001932A
0x18001931f  call    __vcrt_getptd
0x180019324  mov     rcx, [rax+58h]
0x180019328  jmp     short loc_18001932C
0x18001932a  xor     ecx, ecx
0x18001932c  mov     [rbx+8], rcx
0x180019330  call    __vcrt_getptd
0x180019335  mov     [rax+58h], rbx
0x180019339  mov     rax, rbx
0x18001933c  add     rsp, 20h
0x180019340  pop     rbx
0x180019341  retn
```
