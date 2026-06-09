# CspGetNodeMapEntryForURI(CspNodeMapBase const *,IConfigManager2URI *)

- ea: `0x180009d7c`
- end: `0x180009de4`
- name: `?CspGetNodeMapEntryForURI@@YAPEBUCSP_NODEMAP_ENTRY@@PEBVCspNodeMapBase@@PEAUIConfigManager2URI@@@Z`
- size: `104`
- prototype: `const struct CSP_NODEMAP_ENTRY *__fastcall(const struct CspNodeMapBase *, struct IConfigManager2URI *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008160`
- `0x180009080`
- `0x180009910`

## callees

- `0x180009d7c`
- `0x180009dec`
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
0x180009d7c  mov     [rsp+arg_0], rbx
0x180009d81  mov     [rsp+arg_8], rsi
0x180009d86  push    rdi
0x180009d87  sub     rsp, 20h
0x180009d8b  mov     rdi, rdx
0x180009d8e  mov     rbx, rcx
0x180009d91  test    rcx, rcx
0x180009d94  jz      short loc_180009DD2
0x180009d96  test    rdx, rdx
0x180009d99  jz      short loc_180009DD2
0x180009d9b  mov     rax, [rcx]
0x180009d9e  mov     rax, [rax+8]
0x180009da2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009da7  mov     rsi, rax
0x180009daa  test    rax, rax
0x180009dad  jz      short loc_180009DD2
0x180009daf  mov     rcx, [rbx]
0x180009db2  mov     rax, [rcx+10h]
0x180009db6  mov     rcx, rbx
0x180009db9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009dbe  cmp     eax, 0FFFFFFFFh
0x180009dc1  jz      short loc_180009DD2
0x180009dc3  mov     r8, rdi
0x180009dc6  mov     edx, eax
0x180009dc8  mov     rcx, rsi
0x180009dcb  call    CspGetNodeMapEntryFromNodeMap
0x180009dd0  jmp     short loc_180009DD4
0x180009dd2  xor     eax, eax
0x180009dd4  mov     rbx, [rsp+28h+arg_0]
0x180009dd9  mov     rsi, [rsp+28h+arg_8]
0x180009dde  add     rsp, 20h
0x180009de2  pop     rdi
0x180009de3  retn
```
