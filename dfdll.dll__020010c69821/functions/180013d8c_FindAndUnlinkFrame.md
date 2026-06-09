# _FindAndUnlinkFrame

- ea: `0x180013d8c`
- end: `0x180013ddf`
- name: `_FindAndUnlinkFrame`
- size: `83`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180016150`

## callees

- `0x180013d8c`
- `0x180014c30`
- `0x1800183f4`

## pseudocode

```c
__int64 __fastcall FindAndUnlinkFrame(__int64 a1)
{
  __int64 v2; // rdx
  __int64 v3; // rbx
  __int64 result; // rax

  if ( a1 != *(_QWORD *)(_vcrt_getptd() + 88) || (v2 = *(_QWORD *)(_vcrt_getptd() + 88)) == 0 )
LABEL_7:
    abort();
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
0x180013d8c  mov     [rsp+arg_0], rbx
0x180013d91  push    rdi
0x180013d92  sub     rsp, 20h
0x180013d96  mov     rdi, rcx
0x180013d99  call    __vcrt_getptd
0x180013d9e  cmp     rdi, [rax+58h]
0x180013da2  jnz     short loc_180013DD9
0x180013da4  call    __vcrt_getptd
0x180013da9  mov     rdx, [rax+58h]
0x180013dad  test    rdx, rdx
0x180013db0  jz      short loc_180013DD9
0x180013db2  mov     rbx, [rdx+8]
0x180013db6  cmp     rdi, rdx
0x180013db9  jz      short loc_180013DC5
0x180013dbb  mov     rdx, rbx
0x180013dbe  test    rbx, rbx
0x180013dc1  jz      short loc_180013DD9
0x180013dc3  jmp     short loc_180013DB2
0x180013dc5  call    __vcrt_getptd
0x180013dca  mov     [rax+58h], rbx
0x180013dce  mov     rbx, [rsp+28h+arg_0]
0x180013dd3  add     rsp, 20h
0x180013dd7  pop     rdi
0x180013dd8  retn
0x180013dd9  call    abort
```
