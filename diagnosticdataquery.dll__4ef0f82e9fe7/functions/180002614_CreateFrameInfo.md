# _CreateFrameInfo

- ea: `0x180002614`
- end: `0x18000264e`
- name: `_CreateFrameInfo`
- size: `58`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800042e0`

## callees

- `0x180002614`
- `0x180002e18`

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
0x180002614  push    rbx
0x180002616  sub     rsp, 20h
0x18000261a  mov     rbx, rcx
0x18000261d  mov     [rcx], rdx
0x180002620  call    __vcrt_getptd
0x180002625  cmp     rbx, [rax+58h]
0x180002629  jnb     short loc_180002636
0x18000262b  call    __vcrt_getptd
0x180002630  mov     rcx, [rax+58h]
0x180002634  jmp     short loc_180002638
0x180002636  xor     ecx, ecx
0x180002638  mov     [rbx+8], rcx
0x18000263c  call    __vcrt_getptd
0x180002641  mov     [rax+58h], rbx
0x180002645  mov     rax, rbx
0x180002648  add     rsp, 20h
0x18000264c  pop     rbx
0x18000264d  retn
```
