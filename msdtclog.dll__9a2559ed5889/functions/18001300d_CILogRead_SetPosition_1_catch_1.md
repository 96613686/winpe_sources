# _CILogRead::SetPosition_::_1_::catch$1

- ea: `0x18001300d`
- end: `0x180013054`
- name: `_CILogRead::SetPosition_::_1_::catch$1`
- size: `71`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000d160`
- `0x18001300d`

## pseudocode

```c
__int64 __fastcall CILogRead::SetPosition_::_1_::catch_1(__int64 a1, __int64 a2)
{
  int v3; // ebx

  v3 = *(_DWORD *)(a2 + 52);
  if ( v3 == -2147479510 )
    CReadMap::ReleaseAndSet((CReadMap *)(*(_QWORD *)(*(_QWORD *)(a2 + 80) + 8LL) + 352LL), 0, 0);
  *(_DWORD *)(a2 + 80) = v3;
  return 0;
}

```

## disassembly

```asm
0x18001300d  mov     [rsp+arg_8], rdx
0x180013012  push    rbx
0x180013013  push    rbp
0x180013014  sub     rsp, 38h
0x180013018  mov     rbp, rdx
0x18001301b  mov     ebx, [rbp+34h]
0x18001301e  cmp     ebx, 8000102Ah
0x180013024  jnz     short loc_18001303F
0x180013026  mov     rax, [rbp+50h]
0x18001302a  mov     rcx, [rax+8]
0x18001302e  add     rcx, 160h; this
0x180013035  xor     r8d, r8d; unsigned int
0x180013038  xor     edx, edx; unsigned int
0x18001303a  call    ?ReleaseAndSet@CReadMap@@QEAAHKK@Z; CReadMap::ReleaseAndSet(ulong,ulong)
0x18001303f  mov     [rbp+50h], ebx
0x180013042  mov     rax, 0
0x18001304c  add     rsp, 38h
0x180013050  pop     rbp
0x180013051  pop     rbx
0x180013052  retn
```
