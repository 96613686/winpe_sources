# CspGetNodeMapEntryForURI(CspNodeMapBase const *,IConfigManager2URI *)

- ea: `0x18000a240`
- end: `0x18000a2a9`
- name: `?CspGetNodeMapEntryForURI@@YAPEBUCSP_NODEMAP_ENTRY@@PEBVCspNodeMapBase@@PEAUIConfigManager2URI@@@Z`
- size: `105`
- prototype: `const struct CSP_NODEMAP_ENTRY *__fastcall(const struct CspNodeMapBase *, struct IConfigManager2URI *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008520`
- `0x1800094a0`
- `0x180009da0`

## callees

- `0x18000a240`
- `0x18000a2b0`
- `0x18000e010`

## pseudocode

```c
const struct CSP_NODEMAP_ENTRY *__fastcall CspGetNodeMapEntryForURI(
        const struct CspNodeMapBase *a1,
        struct IConfigManager2URI *a2)
{
  __int64 v4; // rsi
  unsigned int v5; // eax

  if ( a1
    && a2
    && (v4 = (*(__int64 (__fastcall **)(const struct CspNodeMapBase *))(*(_QWORD *)a1 + 8LL))(a1)) != 0
    && (v5 = (*(__int64 (__fastcall **)(const struct CspNodeMapBase *))(*(_QWORD *)a1 + 16LL))(a1), v5 != -1) )
  {
    return (const struct CSP_NODEMAP_ENTRY *)CspGetNodeMapEntryFromNodeMap(v4, v5, a2);
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x18000a240  mov     [rsp+arg_0], rbx
0x18000a245  mov     [rsp+arg_8], rsi
0x18000a24a  push    rdi
0x18000a24b  sub     rsp, 20h
0x18000a24f  mov     rdi, rdx
0x18000a252  mov     rbx, rcx
0x18000a255  test    rcx, rcx
0x18000a258  jz      short loc_18000A296
0x18000a25a  test    rdx, rdx
0x18000a25d  jz      short loc_18000A296
0x18000a25f  mov     rax, [rcx]
0x18000a262  mov     rax, [rax+8]
0x18000a266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a26b  mov     rsi, rax
0x18000a26e  test    rax, rax
0x18000a271  jz      short loc_18000A296
0x18000a273  mov     rcx, [rbx]
0x18000a276  mov     rax, [rcx+10h]
0x18000a27a  mov     rcx, rbx
0x18000a27d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a282  cmp     eax, 0FFFFFFFFh
0x18000a285  jz      short loc_18000A296
0x18000a287  mov     r8, rdi
0x18000a28a  mov     edx, eax
0x18000a28c  mov     rcx, rsi
0x18000a28f  call    CspGetNodeMapEntryFromNodeMap
0x18000a294  jmp     short loc_18000A298
0x18000a296  xor     eax, eax
0x18000a298  mov     rbx, [rsp+28h+arg_0]
0x18000a29d  mov     rsi, [rsp+28h+arg_8]
0x18000a2a2  add     rsp, 20h
0x18000a2a6  pop     rdi
0x18000a2a7  retn
```
