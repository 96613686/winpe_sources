# utl::unique_ptr<_KERB_STORED_CREDENTIAL,KerberosCryptoPolicy::StoredCredDeleter>::~unique_ptr<_KERB_STORED_CREDENTIAL,KerberosCryptoPolicy::StoredCredDeleter>(void)

- ea: `0x140007584`
- end: `0x1400075ad`
- name: `??1?$unique_ptr@U_KERB_STORED_CREDENTIAL@@UStoredCredDeleter@KerberosCryptoPolicy@@@utl@@QEAA@XZ`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1400075b4`

## callees

- `0x140007584`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000759b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000759b`

## pseudocode

```c
void __fastcall utl::unique_ptr<_KERB_STORED_CREDENTIAL,KerberosCryptoPolicy::StoredCredDeleter>::~unique_ptr<_KERB_STORED_CREDENTIAL,KerberosCryptoPolicy::StoredCredDeleter>(
        __int64 a1)
{
  if ( *(_QWORD *)(a1 + 8) )
  {
    if ( *(_BYTE *)a1 )
      ExFreePoolWithTag(*(PVOID *)(a1 + 8), 0);
  }
}

```

## disassembly

```asm
0x140007584  sub     rsp, 28h
0x140007588  mov     rax, [rcx+8]
0x14000758c  test    rax, rax
0x14000758f  jz      short loc_1400075A7
0x140007591  cmp     byte ptr [rcx], 0
0x140007594  jz      short loc_1400075A7
0x140007596  xor     edx, edx; Tag
0x140007598  mov     rcx, rax; P
0x14000759b  call    cs:__imp_ExFreePoolWithTag
0x1400075a2  nop     dword ptr [rax+rax+00h]
0x1400075a7  add     rsp, 28h
0x1400075ab  retn
```
