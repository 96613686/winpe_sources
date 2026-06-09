# _CILogRead::ReadNext_::_1_::catch$1

- ea: `0x180012f2e`
- end: `0x180012fba`
- name: `_CILogRead::ReadNext_::_1_::catch$1`
- size: `140`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180001300`
- `0x18000d160`
- `0x180012f2e`

## pseudocode

```c
__int64 __fastcall CILogRead::ReadNext_::_1_::catch_1(__int64 a1, __int64 a2)
{
  _WORD *v3; // rax
  __int64 v4; // rbx
  __int64 v5; // rax

  **(_DWORD **)(a2 + 224) = 0;
  v3 = *(_WORD **)(a2 + 232);
  if ( v3 )
    *v3 = 0;
  v4 = *(_QWORD *)(a2 + 208);
  v5 = *(_QWORD *)(v4 + 8);
  if ( *(_QWORD *)(v5 + 584) )
    operator delete(*(void **)(v5 + 584));
  *(_QWORD *)(*(_QWORD *)(v4 + 8) + 544LL) = 0;
  CReadMap::ReleaseAndSet((CReadMap *)(*(_QWORD *)(v4 + 8) + 352LL), 0, 0);
  *(_DWORD *)(a2 + 64) = *(_DWORD *)(a2 + 128);
  return 0;
}

```

## disassembly

```asm
0x180012f2e  mov     [rsp+arg_8], rdx
0x180012f33  push    rbx
0x180012f34  push    rbp
0x180012f35  sub     rsp, 48h
0x180012f39  mov     rbp, rdx
0x180012f3c  mov     rax, [rbp+0E0h]
0x180012f43  mov     dword ptr [rax], 0
0x180012f49  mov     rax, [rbp+0E8h]
0x180012f50  test    rax, rax
0x180012f53  jz      short loc_180012F5A
0x180012f55  xor     ecx, ecx
0x180012f57  mov     [rax], cx
0x180012f5a  mov     rbx, [rbp+0D0h]
0x180012f61  mov     rax, [rbx+8]
0x180012f65  cmp     qword ptr [rax+248h], 0
0x180012f6d  jz      short loc_180012F7B
0x180012f6f  mov     rcx, [rax+248h]; Block
0x180012f76  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012f7b  mov     rax, [rbx+8]
0x180012f7f  mov     qword ptr [rax+220h], 0
0x180012f8a  mov     rcx, [rbx+8]
0x180012f8e  add     rcx, 160h; this
0x180012f95  xor     r8d, r8d; unsigned int
0x180012f98  xor     edx, edx; unsigned int
0x180012f9a  call    ?ReleaseAndSet@CReadMap@@QEAAHKK@Z; CReadMap::ReleaseAndSet(ulong,ulong)
0x180012f9f  mov     eax, [rbp+80h]
0x180012fa5  mov     [rbp+40h], eax
0x180012fa8  mov     rax, 0
0x180012fb2  add     rsp, 48h
0x180012fb6  pop     rbp
0x180012fb7  pop     rbx
0x180012fb8  retn
```
