# utl::unique_ptr<Kerb3961::MutableBinary [0],utl::default_delete<Kerb3961::MutableBinary [0]>>::~unique_ptr<Kerb3961::MutableBinary [0],utl::default_delete<Kerb3961::MutableBinary [0]>>(void)

- ea: `0x140007534`
- end: `0x140007554`
- name: `??1?$unique_ptr@$$BY0A@UMutableBinary@Kerb3961@@U?$default_delete@$$BY0A@UMutableBinary@Kerb3961@@@utl@@@utl@@QEAA@XZ`
- size: `32`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140007600`
- `0x1400078f8`

## callees

- `0x140007534`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140007542`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007542`

## pseudocode

```c
void __fastcall utl::unique_ptr<Kerb3961::MutableBinary [0],utl::default_delete<Kerb3961::MutableBinary [0]>>::~unique_ptr<Kerb3961::MutableBinary [0],utl::default_delete<Kerb3961::MutableBinary [0]>>(
        void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    ExFreePoolWithTag(v1, 0);
}

```

## disassembly

```asm
0x140007534  sub     rsp, 28h
0x140007538  mov     rcx, [rcx]; P
0x14000753b  test    rcx, rcx
0x14000753e  jz      short loc_14000754E
0x140007540  xor     edx, edx; Tag
0x140007542  call    cs:__imp_ExFreePoolWithTag
0x140007549  nop     dword ptr [rax+rax+00h]
0x14000754e  add     rsp, 28h
0x140007552  retn
```
