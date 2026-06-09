# VmbusTlServiceDestructor

- ea: `0x140009650`
- end: `0x140009694`
- name: `VmbusTlServiceDestructor`
- size: `68`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x140009650`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140009667`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009681`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009667`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009681`

## pseudocode

```c
void __fastcall VmbusTlServiceDestructor(__int64 a1)
{
  void *v2; // rcx
  void *v3; // rcx

  v2 = *(void **)(a1 + 136);
  if ( v2 )
    ExFreePoolWithTag(v2, 0);
  v3 = *(void **)(a1 + 144);
  if ( v3 )
    ExFreePoolWithTag(v3, 0);
}

```

## disassembly

```asm
0x140009650  push    rbx
0x140009652  sub     rsp, 20h
0x140009656  mov     rbx, rcx
0x140009659  mov     rcx, [rcx+88h]; P
0x140009660  test    rcx, rcx
0x140009663  jz      short loc_140009673
0x140009665  xor     edx, edx; Tag
0x140009667  call    cs:__imp_ExFreePoolWithTag
0x14000966e  nop     dword ptr [rax+rax+00h]
0x140009673  mov     rcx, [rbx+90h]; P
0x14000967a  test    rcx, rcx
0x14000967d  jz      short loc_14000968D
0x14000967f  xor     edx, edx; Tag
0x140009681  call    cs:__imp_ExFreePoolWithTag
0x140009688  nop     dword ptr [rax+rax+00h]
0x14000968d  add     rsp, 20h
0x140009691  pop     rbx
0x140009692  retn
```
