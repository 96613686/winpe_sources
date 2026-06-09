# _CILogRead::ReadLRP_::_1_::catch$1

- ea: `0x180012e0c`
- end: `0x180012e89`
- name: `_CILogRead::ReadLRP_::_1_::catch$1`
- size: `125`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180001300`
- `0x18000d160`
- `0x180012e0c`

## pseudocode

```c
__int64 __fastcall CILogRead::ReadLRP_::_1_::catch_1(__int64 a1, __int64 a2)
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
  *(_DWORD *)(a2 + 160) = *(_DWORD *)(a2 + 72);
  return 0;
}

```

## disassembly

```asm
0x180012e0c  mov     [rsp+arg_8], rdx
0x180012e11  push    rbx
0x180012e12  push    rbp
0x180012e13  sub     rsp, 48h
0x180012e17  mov     rbp, rdx
0x180012e1a  mov     rax, [rbp+0B0h]
0x180012e21  mov     dword ptr [rax], 0
0x180012e27  mov     rax, [rbp+0B8h]
0x180012e2e  test    rax, rax
0x180012e31  jz      short loc_180012E38
0x180012e33  xor     ecx, ecx
0x180012e35  mov     [rax], cx
0x180012e38  mov     rbx, [rbp+0A0h]
0x180012e3f  mov     rax, [rbx+8]
0x180012e43  cmp     qword ptr [rax+248h], 0
0x180012e4b  jz      short loc_180012E59
0x180012e4d  mov     rcx, [rax+248h]; Block
0x180012e54  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012e59  mov     rcx, [rbx+8]
0x180012e5d  add     rcx, 160h; this
0x180012e64  xor     r8d, r8d; unsigned int
0x180012e67  xor     edx, edx; unsigned int
0x180012e69  call    ?ReleaseAndSet@CReadMap@@QEAAHKK@Z; CReadMap::ReleaseAndSet(ulong,ulong)
0x180012e6e  mov     eax, [rbp+48h]
0x180012e71  mov     [rbp+0A0h], eax
0x180012e77  mov     rax, 0
0x180012e81  add     rsp, 48h
0x180012e85  pop     rbp
0x180012e86  pop     rbx
0x180012e87  retn
```
