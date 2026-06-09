# WskGetLocalAddrIrpCompletion

- ea: `0x14001d4f0`
- end: `0x14001d565`
- name: `WskGetLocalAddrIrpCompletion`
- size: `117`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140007710`
- `0x14001d4f0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001d539`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d539`
- `ntoskrnl!IoFreeIrp` at `0x14001d548`
- `ntoskrnl!IoFreeIrp` at `0x14001d548`

## pseudocode

```c
__int64 __fastcall WskGetLocalAddrIrpCompletion(__int64 a1, IRP *a2, _QWORD *a3)
{
  ((void (__fastcall *)(_QWORD))*a3)(*(_QWORD *)(a3[1] + 8LL));
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a3[1] + 512LL), 0xFFFFFFFF) == 1 )
    (*(void (**)(void))(a3[1] + 520LL))();
  ExFreePoolWithTag(a3, 0);
  IoFreeIrp(a2);
  return 3221225494LL;
}

```

## disassembly

```asm
0x14001d4f0  mov     [rsp+arg_0], rbx
0x14001d4f5  push    rdi
0x14001d4f6  sub     rsp, 20h
0x14001d4fa  mov     rcx, [r8+8]
0x14001d4fe  mov     rbx, r8
0x14001d501  mov     rax, [r8]
0x14001d504  mov     rdi, rdx
0x14001d507  mov     rcx, [rcx+8]
0x14001d50b  call    _guard_dispatch_icall
0x14001d510  mov     rcx, [rbx+8]
0x14001d514  or      eax, 0FFFFFFFFh
0x14001d517  lock xadd [rcx+200h], eax
0x14001d51f  cmp     eax, 1
0x14001d522  jnz     short loc_14001D534
0x14001d524  mov     rcx, [rbx+8]
0x14001d528  mov     rax, [rcx+208h]
0x14001d52f  call    _guard_dispatch_icall
0x14001d534  xor     edx, edx; Tag
0x14001d536  mov     rcx, rbx; P
0x14001d539  call    cs:__imp_ExFreePoolWithTag
0x14001d540  nop     dword ptr [rax+rax+00h]
0x14001d545  mov     rcx, rdi; Irp
0x14001d548  call    cs:__imp_IoFreeIrp
0x14001d54f  nop     dword ptr [rax+rax+00h]
0x14001d554  mov     rbx, [rsp+28h+arg_0]
0x14001d559  mov     eax, 0C0000016h
0x14001d55e  add     rsp, 20h
0x14001d562  pop     rdi
0x14001d563  retn
```
