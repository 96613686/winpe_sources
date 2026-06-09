# TdiSendDatagramCompletion

- ea: `0x1400067e0`
- end: `0x140006870`
- name: `TdiSendDatagramCompletion`
- size: `144`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1400067e0`
- `0x140006878`
- `0x140006900`
- `0x140030f80`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x140006835`
- `ntoskrnl!IoFreeMdl` at `0x140006862`
- `ntoskrnl!IoFreeMdl` at `0x140006835`
- `ntoskrnl!IoFreeMdl` at `0x140006862`

## pseudocode

```c
__int64 __fastcall TdiSendDatagramCompletion(__int64 a1, __int64 a2, struct _MDL *a3)
{
  void (__fastcall *v3)(__int64, _QWORD, _QWORD); // rax
  __int64 v6; // rcx
  __int64 v7; // rbx

  v3 = *(void (__fastcall **)(__int64, _QWORD, _QWORD))(a2 + 88);
  if ( v3 )
  {
    v6 = *(_QWORD *)(a2 + 96);
    v7 = *(_QWORD *)(v6 + 32);
    v3(v6, *(unsigned int *)(a2 + 48), *(unsigned int *)(a2 + 56));
    NBT_DEREFERENCE_DEVICE(v7, 11);
  }
  if ( a3 )
    IoFreeMdl(a3);
  **(_QWORD **)(a2 + 8) = 0;
  IoFreeMdl(*(PMDL *)(a2 + 8));
  NbtFreeIrp((PIRP)a2);
  return 3221225494LL;
}

```

## disassembly

```asm
0x1400067e0  mov     [rsp+arg_0], rbx
0x1400067e5  mov     [rsp+arg_8], rsi
0x1400067ea  push    rdi
0x1400067eb  sub     rsp, 20h
0x1400067ef  mov     rax, [rdx+58h]
0x1400067f3  mov     rsi, r8
0x1400067f6  mov     rdi, rdx
0x1400067f9  test    rax, rax
0x1400067fc  jz      short loc_140006821
0x1400067fe  mov     rcx, [rdx+60h]
0x140006802  mov     r8d, [rdx+38h]
0x140006806  mov     edx, [rdx+30h]
0x140006809  mov     rbx, [rcx+20h]
0x14000680d  call    _guard_dispatch_icall
0x140006812  xor     r8d, r8d
0x140006815  mov     rcx, rbx
0x140006818  lea     edx, [r8+0Bh]
0x14000681c  call    NBT_DEREFERENCE_DEVICE
0x140006821  test    rsi, rsi
0x140006824  jnz     short loc_14000685F
0x140006826  mov     rax, [rdi+8]
0x14000682a  mov     qword ptr [rax], 0
0x140006831  mov     rcx, [rdi+8]; Mdl
0x140006835  call    cs:__imp_IoFreeMdl
0x14000683c  nop     dword ptr [rax+rax+00h]
0x140006841  mov     rcx, rdi; Irp
0x140006844  call    NbtFreeIrp
0x140006849  mov     rbx, [rsp+28h+arg_0]
0x14000684e  mov     eax, 0C0000016h
0x140006853  mov     rsi, [rsp+28h+arg_8]
0x140006858  add     rsp, 20h
0x14000685c  pop     rdi
0x14000685d  retn
0x14000685f  mov     rcx, rsi; Mdl
0x140006862  call    cs:__imp_IoFreeMdl
0x140006869  nop     dword ptr [rax+rax+00h]
0x14000686e  jmp     short loc_140006826
```
