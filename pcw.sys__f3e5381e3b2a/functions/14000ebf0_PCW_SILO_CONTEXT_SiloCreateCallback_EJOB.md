# PCW_SILO_CONTEXT::SiloCreateCallback(_EJOB *)

- ea: `0x14000ebf0`
- end: `0x14000ec96`
- name: `?SiloCreateCallback@PCW_SILO_CONTEXT@@CAJPEAU_EJOB@@@Z`
- size: `166`
- prototype: `__int64 __fastcall(struct _EJOB *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14000ebf0`

## import_xrefs

- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x14000ec4d`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x14000ec4d`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14000ec77`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14000ec77`
- `ntoskrnl!PsCreateSiloContext` at `0x14000ec23`
- `ntoskrnl!PsCreateSiloContext` at `0x14000ec23`
- `ntoskrnl!PsInsertPermanentSiloContext` at `0x14000ec61`
- `ntoskrnl!PsInsertPermanentSiloContext` at `0x14000ec61`

## pseudocode

```c
__int64 __fastcall PCW_SILO_CONTEXT::SiloCreateCallback(struct _EJOB *a1)
{
  int inserted; // ebx
  _QWORD *v3; // rdi
  unsigned int SiloMonitorContextSlot; // eax
  _QWORD *v6; // [rsp+48h] [rbp+10h] BYREF

  v6 = 0;
  inserted = PsCreateSiloContext(a1, 24, 1, PCW_SILO_CONTEXT::SiloContextCleanupCallback, &v6);
  if ( inserted >= 0 )
  {
    v3 = v6;
    *v6 = 0;
    *(_OWORD *)(v3 + 1) = 0;
    SiloMonitorContextSlot = PsGetSiloMonitorContextSlot(qword_1400114A0);
    inserted = PsInsertPermanentSiloContext(a1, SiloMonitorContextSlot, v3);
    if ( v3 )
      PsDereferenceSiloContext(v3);
  }
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x14000ebf0  mov     r11, rsp
0x14000ebf3  mov     [r11+8], rbx
0x14000ebf7  mov     [r11+18h], rsi
0x14000ebfb  push    rdi
0x14000ebfc  sub     rsp, 30h
0x14000ec00  mov     edx, 18h
0x14000ec05  mov     qword ptr [r11+10h], 0
0x14000ec0d  lea     rax, [r11+10h]
0x14000ec11  mov     rsi, rcx
0x14000ec14  lea     r9, ?SiloContextCleanupCallback@PCW_SILO_CONTEXT@@CAXPEAX@Z; PCW_SILO_CONTEXT::SiloContextCleanupCallback(void *)
0x14000ec1b  mov     [r11-18h], rax
0x14000ec1f  lea     r8d, [rdx-17h]
0x14000ec23  call    cs:__imp_PsCreateSiloContext
0x14000ec2a  nop     dword ptr [rax+rax+00h]
0x14000ec2f  mov     ebx, eax
0x14000ec31  test    eax, eax
0x14000ec33  js      short loc_14000EC83
0x14000ec35  mov     rdi, [rsp+38h+arg_8]
0x14000ec3a  xor     eax, eax
0x14000ec3c  xorps   xmm0, xmm0
0x14000ec3f  mov     [rdi], rax
0x14000ec42  movups  xmmword ptr [rdi+8], xmm0
0x14000ec46  mov     rcx, cs:qword_1400114A0
0x14000ec4d  call    cs:__imp_PsGetSiloMonitorContextSlot
0x14000ec54  nop     dword ptr [rax+rax+00h]
0x14000ec59  mov     r8, rdi
0x14000ec5c  mov     rcx, rsi
0x14000ec5f  mov     edx, eax
0x14000ec61  call    cs:__imp_PsInsertPermanentSiloContext
0x14000ec68  nop     dword ptr [rax+rax+00h]
0x14000ec6d  mov     ebx, eax
0x14000ec6f  test    rdi, rdi
0x14000ec72  jz      short loc_14000EC83
0x14000ec74  mov     rcx, rdi
0x14000ec77  call    cs:__imp_PsDereferenceSiloContext
0x14000ec7e  nop     dword ptr [rax+rax+00h]
0x14000ec83  mov     rsi, [rsp+38h+arg_10]
0x14000ec88  mov     eax, ebx
0x14000ec8a  mov     rbx, [rsp+38h+arg_0]
0x14000ec8f  add     rsp, 30h
0x14000ec93  pop     rdi
0x14000ec94  retn
```
