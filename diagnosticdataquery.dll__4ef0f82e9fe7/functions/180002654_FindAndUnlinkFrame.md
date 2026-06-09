# _FindAndUnlinkFrame

- ea: `0x180002654`
- end: `0x1800026a7`
- name: `_FindAndUnlinkFrame`
- size: `83`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800042e0`

## callees

- `0x180002654`
- `0x180002e18`
- `0x180005152`

## pseudocode

```c
__int64 __fastcall FindAndUnlinkFrame(__int64 a1)
{
  __int64 v2; // rdx
  __int64 v3; // rbx
  __int64 result; // rax

  if ( a1 != *(_QWORD *)(_vcrt_getptd() + 88) || (v2 = *(_QWORD *)(_vcrt_getptd() + 88)) == 0 )
LABEL_7:
    abort_0();
  while ( 1 )
  {
    v3 = *(_QWORD *)(v2 + 8);
    if ( a1 == v2 )
      break;
    v2 = *(_QWORD *)(v2 + 8);
    if ( !v3 )
      goto LABEL_7;
  }
  result = _vcrt_getptd();
  *(_QWORD *)(result + 88) = v3;
  return result;
}

```

## disassembly

```asm
0x180002654  mov     [rsp+arg_0], rbx
0x180002659  push    rdi
0x18000265a  sub     rsp, 20h
0x18000265e  mov     rdi, rcx
0x180002661  call    __vcrt_getptd
0x180002666  cmp     rdi, [rax+58h]
0x18000266a  jnz     short loc_1800026A1
0x18000266c  call    __vcrt_getptd
0x180002671  mov     rdx, [rax+58h]
0x180002675  test    rdx, rdx
0x180002678  jz      short loc_1800026A1
0x18000267a  mov     rbx, [rdx+8]
0x18000267e  cmp     rdi, rdx
0x180002681  jz      short loc_18000268D
0x180002683  mov     rdx, rbx
0x180002686  test    rbx, rbx
0x180002689  jz      short loc_1800026A1
0x18000268b  jmp     short loc_18000267A
0x18000268d  call    __vcrt_getptd
0x180002692  mov     [rax+58h], rbx
0x180002696  mov     rbx, [rsp+28h+arg_0]
0x18000269b  add     rsp, 20h
0x18000269f  pop     rdi
0x1800026a0  retn
0x1800026a1  call    abort_0
```
