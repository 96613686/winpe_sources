# _CreateFrameInfo

- ea: `0x18000d7e8`
- end: `0x18000d835`
- name: `_CreateFrameInfo`
- size: `77`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c4c0`
- `0x1800166c0`

## callees

- `0x18000d7e8`
- `0x18003e048`

## pseudocode

```c
_QWORD *__fastcall CreateFrameInfo(_QWORD *a1, __int64 a2)
{
  __int64 v3; // rax
  __int64 v4; // rcx

  *a1 = a2;
  v3 = getptd();
  if ( (unsigned __int64)a1 >= *(_QWORD *)(v3 + 288) )
  {
    v4 = 0;
  }
  else
  {
    if ( !v3 )
      v3 = getptd();
    v4 = *(_QWORD *)(v3 + 288);
  }
  a1[1] = v4;
  if ( !v3 )
    v3 = getptd();
  *(_QWORD *)(v3 + 288) = a1;
  return a1;
}

```

## disassembly

```asm
0x18000d7e8  push    rbx
0x18000d7ea  sub     rsp, 20h
0x18000d7ee  mov     rbx, rcx
0x18000d7f1  mov     [rcx], rdx
0x18000d7f4  call    _getptd
0x18000d7f9  cmp     rbx, [rax+120h]
0x18000d800  jnb     short loc_18000D815
0x18000d802  test    rax, rax
0x18000d805  jnz     short loc_18000D80C
0x18000d807  call    _getptd
0x18000d80c  mov     rcx, [rax+120h]
0x18000d813  jmp     short loc_18000D817
0x18000d815  xor     ecx, ecx
0x18000d817  mov     [rbx+8], rcx
0x18000d81b  test    rax, rax
0x18000d81e  jnz     short loc_18000D825
0x18000d820  call    _getptd
0x18000d825  mov     [rax+120h], rbx
0x18000d82c  mov     rax, rbx
0x18000d82f  add     rsp, 20h
0x18000d833  pop     rbx
0x18000d834  retn
```
