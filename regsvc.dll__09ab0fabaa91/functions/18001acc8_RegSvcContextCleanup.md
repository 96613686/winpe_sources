# RegSvcContextCleanup

- ea: `0x18001acc8`
- end: `0x18001acec`
- name: `RegSvcContextCleanup`
- size: `36`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180019290`
- `0x1800199a0`
- `0x18001a410`
- `0x18001a710`
- `0x18001aad0`

## callees

- `0x18001acc8`
- `0x18001acf4`

## import_xrefs

- `ntdll!NtClose` at `0x18001acd9`
- `ntdll!NtClose` at `0x18001acd9`

## pseudocode

```c
__int64 __fastcall RegSvcContextCleanup(void **a1)
{
  void *v2; // rcx

  v2 = *a1;
  if ( v2 )
    NtClose(v2);
  return RegSvcContextFree(a1);
}

```

## disassembly

```asm
0x18001acc8  push    rbx
0x18001acca  sub     rsp, 20h
0x18001acce  mov     rbx, rcx
0x18001acd1  mov     rcx, [rcx]; Handle
0x18001acd4  test    rcx, rcx
0x18001acd7  jz      short loc_18001ACDF
0x18001acd9  call    cs:__imp_NtClose
0x18001acdf  mov     rcx, rbx
0x18001ace2  add     rsp, 20h
0x18001ace6  pop     rbx
0x18001ace7  jmp     RegSvcContextFree
```
