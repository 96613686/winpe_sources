# _FindAndUnlinkFrame

- ea: `0x180019348`
- end: `0x18001939b`
- name: `_FindAndUnlinkFrame`
- size: `83`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18001a650`

## callees

- `0x1800150f8`
- `0x180019348`
- `0x1800194ec`

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
0x180019348  mov     [rsp+arg_0], rbx
0x18001934d  push    rdi
0x18001934e  sub     rsp, 20h
0x180019352  mov     rdi, rcx
0x180019355  call    __vcrt_getptd
0x18001935a  cmp     rdi, [rax+58h]
0x18001935e  jnz     short loc_180019395
0x180019360  call    __vcrt_getptd
0x180019365  mov     rdx, [rax+58h]
0x180019369  test    rdx, rdx
0x18001936c  jz      short loc_180019395
0x18001936e  mov     rbx, [rdx+8]
0x180019372  cmp     rdi, rdx
0x180019375  jz      short loc_180019381
0x180019377  mov     rdx, rbx
0x18001937a  test    rbx, rbx
0x18001937d  jz      short loc_180019395
0x18001937f  jmp     short loc_18001936E
0x180019381  call    __vcrt_getptd
0x180019386  mov     [rax+58h], rbx
0x18001938a  mov     rbx, [rsp+28h+arg_0]
0x18001938f  add     rsp, 20h
0x180019393  pop     rdi
0x180019394  retn
0x180019395  call    abort
```
