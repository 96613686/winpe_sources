# CIISGlobalModule::OnGlobalFileChange(IGlobalFileChangeProvider *)

- ea: `0x1800028a0`
- end: `0x1800028d4`
- name: `?OnGlobalFileChange@CIISGlobalModule@@UEAA?AW4GLOBAL_NOTIFICATION_STATUS@@PEAVIGlobalFileChangeProvider@@@Z`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800028a0`
- `0x180004010`

## import_xrefs

- `iisutil!?DeletePath@TREE_HASH_TABLE@@QEAAXPEBG@Z` at `0x1800028c7`
- `iisutil!?DeletePath@TREE_HASH_TABLE@@QEAAXPEBG@Z` at `0x1800028c7`

## pseudocode

```c
__int64 __fastcall CIISGlobalModule::OnGlobalFileChange(__int64 a1, __int64 a2)
{
  const unsigned __int16 *v2; // rax

  if ( g_pFileCache )
  {
    v2 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
    TREE_HASH_TABLE::DeletePath((TREE_HASH_TABLE *)g_pFileCache, v2);
  }
  return 0;
}

```

## disassembly

```asm
0x1800028a0  sub     rsp, 28h
0x1800028a4  cmp     cs:?g_pFileCache@@3PEAVFILE_CACHE@@EA, 0; FILE_CACHE * g_pFileCache
0x1800028ac  jz      short loc_1800028CD
0x1800028ae  mov     rax, [rdx]
0x1800028b1  mov     rcx, rdx
0x1800028b4  mov     rax, [rax+8]
0x1800028b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028bd  mov     rcx, cs:?g_pFileCache@@3PEAVFILE_CACHE@@EA; FILE_CACHE * g_pFileCache
0x1800028c4  mov     rdx, rax
0x1800028c7  call    cs:__imp_?DeletePath@TREE_HASH_TABLE@@QEAAXPEBG@Z; TREE_HASH_TABLE::DeletePath(ushort const *)
0x1800028cd  xor     eax, eax
0x1800028cf  add     rsp, 28h
0x1800028d3  retn
```
