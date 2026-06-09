# CspGetNodeMapEntryForURI(CspNodeMapBase const *,IConfigManager2URI *)

- ea: `0x180010f8c`
- end: `0x180010ff5`
- name: `?CspGetNodeMapEntryForURI@@YAPEBUCSP_NODEMAP_ENTRY@@PEBVCspNodeMapBase@@PEAUIConfigManager2URI@@@Z`
- size: `105`
- prototype: `const struct CSP_NODEMAP_ENTRY *__fastcall(const struct CspNodeMapBase *, struct IConfigManager2URI *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a8f0`
- `0x18000ebc0`
- `0x180010590`

## callees

- `0x180010f8c`
- `0x180010ffc`
- `0x180038010`

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
0x180010f8c  mov     [rsp+arg_0], rbx
0x180010f91  mov     [rsp+arg_8], rsi
0x180010f96  push    rdi
0x180010f97  sub     rsp, 20h
0x180010f9b  mov     rdi, rdx
0x180010f9e  mov     rbx, rcx
0x180010fa1  test    rcx, rcx
0x180010fa4  jz      short loc_180010FE2
0x180010fa6  test    rdx, rdx
0x180010fa9  jz      short loc_180010FE2
0x180010fab  mov     rax, [rcx]
0x180010fae  mov     rax, [rax+8]
0x180010fb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010fb7  mov     rsi, rax
0x180010fba  test    rax, rax
0x180010fbd  jz      short loc_180010FE2
0x180010fbf  mov     rcx, [rbx]
0x180010fc2  mov     rax, [rcx+10h]
0x180010fc6  mov     rcx, rbx
0x180010fc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010fce  cmp     eax, 0FFFFFFFFh
0x180010fd1  jz      short loc_180010FE2
0x180010fd3  mov     r8, rdi
0x180010fd6  mov     edx, eax
0x180010fd8  mov     rcx, rsi
0x180010fdb  call    CspGetNodeMapEntryFromNodeMap
0x180010fe0  jmp     short loc_180010FE4
0x180010fe2  xor     eax, eax
0x180010fe4  mov     rbx, [rsp+28h+arg_0]
0x180010fe9  mov     rsi, [rsp+28h+arg_8]
0x180010fee  add     rsp, 20h
0x180010ff2  pop     rdi
0x180010ff3  retn
```
