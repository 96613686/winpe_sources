# _CILogRead::ReadNext_::_1_::catch$0

- ea: `0x180012e8f`
- end: `0x180012f28`
- name: `_CILogRead::ReadNext_::_1_::catch$0`
- size: `153`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180001300`
- `0x18000d160`
- `0x180012e8f`

## pseudocode

```c
__int64 __fastcall CILogRead::ReadNext_::_1_::catch_0(__int64 a1, __int64 a2)
{
  _WORD *v3; // rax
  __int64 v4; // rbx
  __int64 v5; // rax
  int v6; // eax

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
  v6 = *(_DWORD *)(a2 + 96);
  if ( v6 == -2147479510 )
    v6 = -2147479509;
  *(_DWORD *)(a2 + 96) = v6;
  *(_DWORD *)(a2 + 64) = v6;
  return 0;
}

```

## disassembly

```asm
0x180012e8f  mov     [rsp+arg_8], rdx
0x180012e94  push    rbx
0x180012e95  push    rbp
0x180012e96  sub     rsp, 48h
0x180012e9a  mov     rbp, rdx
0x180012e9d  mov     rax, [rbp+0E0h]
0x180012ea4  mov     dword ptr [rax], 0
0x180012eaa  mov     rax, [rbp+0E8h]
0x180012eb1  test    rax, rax
0x180012eb4  jz      short loc_180012EBB
0x180012eb6  xor     ecx, ecx
0x180012eb8  mov     [rax], cx
0x180012ebb  mov     rbx, [rbp+0D0h]
0x180012ec2  mov     rax, [rbx+8]
0x180012ec6  cmp     qword ptr [rax+248h], 0
0x180012ece  jz      short loc_180012EDC
0x180012ed0  mov     rcx, [rax+248h]; Block
0x180012ed7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012edc  mov     rax, [rbx+8]
0x180012ee0  mov     qword ptr [rax+220h], 0
0x180012eeb  mov     rcx, [rbx+8]
0x180012eef  add     rcx, 160h; this
0x180012ef6  xor     r8d, r8d; unsigned int
0x180012ef9  xor     edx, edx; unsigned int
0x180012efb  call    ?ReleaseAndSet@CReadMap@@QEAAHKK@Z; CReadMap::ReleaseAndSet(ulong,ulong)
0x180012f00  mov     eax, [rbp+60h]
0x180012f03  mov     ecx, 8000102Bh
0x180012f08  cmp     eax, 8000102Ah
0x180012f0d  cmovz   eax, ecx
0x180012f10  mov     [rbp+60h], eax
0x180012f13  mov     [rbp+40h], eax
0x180012f16  mov     rax, 0
0x180012f20  add     rsp, 48h
0x180012f24  pop     rbp
0x180012f25  pop     rbx
0x180012f26  retn
```
