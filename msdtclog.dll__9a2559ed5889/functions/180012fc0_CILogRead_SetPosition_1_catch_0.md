# _CILogRead::SetPosition_::_1_::catch$0

- ea: `0x180012fc0`
- end: `0x180013007`
- name: `_CILogRead::SetPosition_::_1_::catch$0`
- size: `71`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000d160`
- `0x180012fc0`

## pseudocode

```c
__int64 __fastcall CILogRead::SetPosition_::_1_::catch_0(__int64 a1, __int64 a2)
{
  int v3; // ebx

  v3 = *(_DWORD *)(a2 + 48);
  if ( v3 == -2147479510 )
    CReadMap::ReleaseAndSet((CReadMap *)(*(_QWORD *)(*(_QWORD *)(a2 + 80) + 8LL) + 352LL), 0, 0);
  *(_DWORD *)(a2 + 80) = v3;
  return 0;
}

```

## disassembly

```asm
0x180012fc0  mov     [rsp+arg_8], rdx
0x180012fc5  push    rbx
0x180012fc6  push    rbp
0x180012fc7  sub     rsp, 38h
0x180012fcb  mov     rbp, rdx
0x180012fce  mov     ebx, [rbp+30h]
0x180012fd1  cmp     ebx, 8000102Ah
0x180012fd7  jnz     short loc_180012FF2
0x180012fd9  mov     rax, [rbp+50h]
0x180012fdd  mov     rcx, [rax+8]
0x180012fe1  add     rcx, 160h; this
0x180012fe8  xor     r8d, r8d; unsigned int
0x180012feb  xor     edx, edx; unsigned int
0x180012fed  call    ?ReleaseAndSet@CReadMap@@QEAAHKK@Z; CReadMap::ReleaseAndSet(ulong,ulong)
0x180012ff2  mov     [rbp+50h], ebx
0x180012ff5  mov     rax, 0
0x180012fff  add     rsp, 38h
0x180013003  pop     rbp
0x180013004  pop     rbx
0x180013005  retn
```
