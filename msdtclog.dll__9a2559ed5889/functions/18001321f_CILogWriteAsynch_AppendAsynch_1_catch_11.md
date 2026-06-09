# _CILogWriteAsynch::AppendAsynch_::_1_::catch$11

- ea: `0x18001321f`
- end: `0x180013291`
- name: `_CILogWriteAsynch::AppendAsynch_::_1_::catch$11`
- size: `114`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180015010`

## pseudocode

```c
__int64 __fastcall CILogWriteAsynch::AppendAsynch_::_1_::catch_11(__int64 a1, __int64 a2)
{
  __int64 v3; // rbx

  *(_DWORD *)(a2 + 64) = *(_DWORD *)(a2 + 68);
  *(_QWORD *)(a2 + 80) = 0;
  v3 = *(_QWORD *)(a2 + 160);
  (**(void (__fastcall ***)(__int64))(v3 + 32))(v3 + 32);
  *(_DWORD *)(*(_QWORD *)(v3 + 152) + 24LL * *(unsigned int *)(a2 + 168) + 16) = 0;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(v3 + 32) + 8LL))(v3 + 32);
  return 0;
}

```

## disassembly

```asm
0x18001321f  mov     [rsp+arg_8], rdx
0x180013224  push    rbx
0x180013225  push    rbp
0x180013226  push    rdi
0x180013227  sub     rsp, 40h
0x18001322b  mov     rbp, rdx
0x18001322e  mov     eax, [rbp+44h]
0x180013231  mov     [rbp+40h], eax
0x180013234  mov     qword ptr [rbp+50h], 0
0x18001323c  mov     rbx, [rbp+0A0h]
0x180013243  lea     rdi, [rbx+20h]
0x180013247  mov     rax, [rdi]
0x18001324a  mov     rcx, rdi
0x18001324d  mov     rax, [rax]
0x180013250  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013255  mov     eax, [rbp+0A8h]
0x18001325b  lea     rdx, [rax+rax*2]
0x18001325f  mov     rax, [rbx+98h]
0x180013266  mov     dword ptr [rax+rdx*8+10h], 0
0x18001326e  mov     rax, [rdi]
0x180013271  mov     rcx, rdi
0x180013274  mov     rax, [rax+8]
0x180013278  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001327d  nop
0x18001327e  mov     rax, 0
0x180013288  add     rsp, 40h
0x18001328c  pop     rdi
0x18001328d  pop     rbp
0x18001328e  pop     rbx
0x18001328f  retn
```
