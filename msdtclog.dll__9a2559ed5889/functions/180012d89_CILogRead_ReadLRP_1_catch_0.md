# _CILogRead::ReadLRP_::_1_::catch$0

- ea: `0x180012d89`
- end: `0x180012e06`
- name: `_CILogRead::ReadLRP_::_1_::catch$0`
- size: `125`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180001300`
- `0x18000d160`
- `0x180012d89`

## pseudocode

```c
__int64 __fastcall CILogRead::ReadLRP_::_1_::catch_0(__int64 a1, __int64 a2)
{
  _WORD *v3; // rax
  __int64 v4; // rbx
  __int64 v5; // rax

  **(_DWORD **)(a2 + 176) = 0;
  v3 = *(_WORD **)(a2 + 184);
  if ( v3 )
    *v3 = 0;
  v4 = *(_QWORD *)(a2 + 160);
  v5 = *(_QWORD *)(v4 + 8);
  if ( *(_QWORD *)(v5 + 584) )
    operator delete(*(void **)(v5 + 584));
  CReadMap::ReleaseAndSet((CReadMap *)(*(_QWORD *)(v4 + 8) + 352LL), 0, 0);
  *(_DWORD *)(a2 + 160) = *(_DWORD *)(a2 + 68);
  return 0;
}

```

## disassembly

```asm
0x180012d89  mov     [rsp+arg_8], rdx
0x180012d8e  push    rbx
0x180012d8f  push    rbp
0x180012d90  sub     rsp, 48h
0x180012d94  mov     rbp, rdx
0x180012d97  mov     rax, [rbp+0B0h]
0x180012d9e  mov     dword ptr [rax], 0
0x180012da4  mov     rax, [rbp+0B8h]
0x180012dab  test    rax, rax
0x180012dae  jz      short loc_180012DB5
0x180012db0  xor     ecx, ecx
0x180012db2  mov     [rax], cx
0x180012db5  mov     rbx, [rbp+0A0h]
0x180012dbc  mov     rax, [rbx+8]
0x180012dc0  cmp     qword ptr [rax+248h], 0
0x180012dc8  jz      short loc_180012DD6
0x180012dca  mov     rcx, [rax+248h]; Block
0x180012dd1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012dd6  mov     rcx, [rbx+8]
0x180012dda  add     rcx, 160h; this
0x180012de1  xor     r8d, r8d; unsigned int
0x180012de4  xor     edx, edx; unsigned int
0x180012de6  call    ?ReleaseAndSet@CReadMap@@QEAAHKK@Z; CReadMap::ReleaseAndSet(ulong,ulong)
0x180012deb  mov     eax, [rbp+44h]
0x180012dee  mov     [rbp+0A0h], eax
0x180012df4  mov     rax, 0
0x180012dfe  add     rsp, 48h
0x180012e02  pop     rbp
0x180012e03  pop     rbx
0x180012e04  retn
```
