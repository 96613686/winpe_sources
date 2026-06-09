# basessp::BaseSSP::WSTFreeString(_UNICODE_STRING *)

- ea: `0x180006390`
- end: `0x1800063de`
- name: `?WSTFreeString@BaseSSP@basessp@@QEAAXPEAU_UNICODE_STRING@@@Z`
- size: `78`
- prototype: `void __fastcall(basessp::BaseSSP *__hidden this, struct _UNICODE_STRING *)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x180004404`
- `0x180005998`
- `0x180005bc0`
- `0x18000676c`
- `0x18000d334`
- `0x18000d388`
- `0x18001d92c`

## callees

- `0x180006390`
- `0x180020010`

## pseudocode

```c
void __fastcall basessp::BaseSSP::WSTFreeString(basessp::BaseSSP *this, struct _UNICODE_STRING *a2)
{
  void (*v3)(void); // rax

  if ( a2 && a2->Buffer )
  {
    if ( *((_DWORD *)this + 52) == 1 )
      v3 = *(void (**)(void))(*((_QWORD *)this + 30) + 392LL);
    else
      v3 = *(void (**)(void))(*((_QWORD *)this + 31) + 8LL);
    v3();
    *a2 = 0;
  }
}

```

## disassembly

```asm
0x180006390  test    rdx, rdx
0x180006393  jz      short locret_1800063D0
0x180006395  push    rbx
0x180006396  sub     rsp, 20h
0x18000639a  mov     rax, rcx
0x18000639d  mov     rbx, rdx
0x1800063a0  mov     rcx, [rdx+8]
0x1800063a4  test    rcx, rcx
0x1800063a7  jz      short loc_1800063CB
0x1800063a9  cmp     dword ptr [rax+0D0h], 1
0x1800063b0  jnz     short loc_1800063D1
0x1800063b2  mov     rax, [rax+0F0h]
0x1800063b9  mov     rax, [rax+188h]
0x1800063c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063c5  xorps   xmm0, xmm0
0x1800063c8  movups  xmmword ptr [rbx], xmm0
0x1800063cb  add     rsp, 20h
0x1800063cf  pop     rbx
0x1800063d0  retn
0x1800063d1  mov     rax, [rax+0F8h]
0x1800063d8  mov     rax, [rax+8]
0x1800063dc  jmp     short loc_1800063C0
```
