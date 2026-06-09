# SendSessionCompletionRoutine

- ea: `0x1400253e0`
- end: `0x140025426`
- name: `SendSessionCompletionRoutine`
- size: `70`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140006878`
- `0x1400253e0`
- `0x140030f80`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x140025406`
- `ntoskrnl!IoFreeMdl` at `0x140025406`

## pseudocode

```c
__int64 __fastcall SendSessionCompletionRoutine(__int64 a1, __int64 a2)
{
  void (__fastcall *v2)(_QWORD, _QWORD, _QWORD); // rax

  v2 = *(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(a2 + 88);
  if ( v2 )
    v2(*(_QWORD *)(a2 + 96), *(unsigned int *)(a2 + 48), *(unsigned int *)(a2 + 56));
  IoFreeMdl(*(PMDL *)(a2 + 8));
  NbtFreeIrp((PIRP)a2);
  return 3221225494LL;
}

```

## disassembly

```asm
0x1400253e0  push    rbx
0x1400253e2  sub     rsp, 20h
0x1400253e6  mov     rax, [rdx+58h]
0x1400253ea  mov     rbx, rdx
0x1400253ed  test    rax, rax
0x1400253f0  jz      short loc_140025402
0x1400253f2  mov     r8d, [rdx+38h]
0x1400253f6  mov     edx, [rdx+30h]
0x1400253f9  mov     rcx, [rbx+60h]
0x1400253fd  call    _guard_dispatch_icall
0x140025402  mov     rcx, [rbx+8]; Mdl
0x140025406  call    cs:__imp_IoFreeMdl
0x14002540d  nop     dword ptr [rax+rax+00h]
0x140025412  mov     rcx, rbx; Irp
0x140025415  call    NbtFreeIrp
0x14002541a  mov     eax, 0C0000016h
0x14002541f  add     rsp, 20h
0x140025423  pop     rbx
0x140025424  retn
```
