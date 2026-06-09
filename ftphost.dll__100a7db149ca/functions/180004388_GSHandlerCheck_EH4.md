# __GSHandlerCheck_EH4

- ea: `0x180004388`
- end: `0x1800043e9`
- name: `__GSHandlerCheck_EH4`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800019f8`
- `0x18000431c`
- `0x180004388`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheck_EH4(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rbx
  __int64 result; // rax

  v4 = *(_QWORD *)(a4 + 56);
  _GSHandlerCheckCommon(a2, a4);
  result = 1;
  if ( ((((*(_DWORD *)(a1 + 4) & 0x66) != 0) + 1) & *(_DWORD *)(v4 + 4)) != 0 )
    return _CxxFrameHandler4_0(a1, a2, a3, a4);
  return result;
}

```

## disassembly

```asm
0x180004388  push    rbx
0x18000438a  push    rbp
0x18000438b  push    rsi
0x18000438c  push    rdi
0x18000438d  push    r14
0x18000438f  sub     rsp, 20h
0x180004393  mov     rbx, [r9+38h]
0x180004397  mov     rsi, rdx
0x18000439a  mov     r14, r8
0x18000439d  mov     rbp, rcx
0x1800043a0  mov     rdx, r9
0x1800043a3  mov     rcx, rsi
0x1800043a6  mov     rdi, r9
0x1800043a9  lea     r8, [rbx+4]
0x1800043ad  call    __GSHandlerCheckCommon
0x1800043b2  mov     eax, [rbp+4]
0x1800043b5  and     al, 66h
0x1800043b7  neg     al
0x1800043b9  mov     eax, 1
0x1800043be  sbb     r9d, r9d
0x1800043c1  neg     r9d
0x1800043c4  add     r9d, eax
0x1800043c7  test    [rbx+4], r9d
0x1800043cb  jz      short loc_1800043DE
0x1800043cd  mov     r9, rdi
0x1800043d0  mov     r8, r14
0x1800043d3  mov     rdx, rsi
0x1800043d6  mov     rcx, rbp
0x1800043d9  call    __CxxFrameHandler4_0
0x1800043de  add     rsp, 20h
0x1800043e2  pop     r14
0x1800043e4  pop     rdi
0x1800043e5  pop     rsi
0x1800043e6  pop     rbp
0x1800043e7  pop     rbx
0x1800043e8  retn
```
