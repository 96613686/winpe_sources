# GlobalDoWork(ulong,IHttpEventProvider *)

- ea: `0x180001010`
- end: `0x180001072`
- name: `?GlobalDoWork@@YA?AW4GLOBAL_NOTIFICATION_STATUS@@KPEAVIHttpEventProvider@@@Z`
- size: `98`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001d80`
- `0x180001d90`

## callees

- `0x180001010`
- `0x1800010a0`
- `0x180003010`

## import_xrefs

- `iisutil!?Clear@TREE_HASH_TABLE@@QEAAXXZ` at `0x180001068`
- `iisutil!?Clear@TREE_HASH_TABLE@@QEAAXXZ` at `0x180001068`
- `iisutil!?DeletePath@TREE_HASH_TABLE@@QEAAXPEBG@Z` at `0x180001054`
- `iisutil!?DeletePath@TREE_HASH_TABLE@@QEAAXPEBG@Z` at `0x180001054`

## pseudocode

```c
__int64 __fastcall GlobalDoWork(void *a1, __int64 *a2)
{
  const unsigned __int16 *v3; // rax

  switch ( (_DWORD)a1 )
  {
    case 0x10:
      if ( g_pUriCache )
        return W3_URL_INFO_CACHE::DoCacheOperation(a1, a2);
      break;
    case 4:
      if ( g_pUriCache )
        TREE_HASH_TABLE::Clear((TREE_HASH_TABLE *)g_pUriCache);
      break;
    case 0x40:
      v3 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64 *))(*a2 + 8))(a2);
      TREE_HASH_TABLE::DeletePath((TREE_HASH_TABLE *)g_pUriCache, v3);
      break;
  }
  return 0;
}

```

## disassembly

```asm
0x180001010  sub     rsp, 28h
0x180001014  cmp     ecx, 10h
0x180001017  jnz     short loc_180001031
0x180001019  cmp     cs:?g_pUriCache@@3PEAVW3_URL_INFO_CACHE@@EA, 0; W3_URL_INFO_CACHE * g_pUriCache
0x180001021  jz      short loc_18000106E
0x180001023  add     rsp, 28h
0x180001027  jmp     ?DoCacheOperation@W3_URL_INFO_CACHE@@QEAA?AW4GLOBAL_NOTIFICATION_STATUS@@PEAVICacheProvider@@@Z; W3_URL_INFO_CACHE::DoCacheOperation(ICacheProvider *)
0x18000102c  add     rsp, 28h
0x180001030  retn
0x180001031  cmp     ecx, 4
0x180001034  jz      short loc_18000105C
0x180001036  cmp     ecx, 40h ; '@'
0x180001039  jnz     short loc_18000106E
0x18000103b  mov     rax, [rdx]
0x18000103e  mov     rcx, rdx
0x180001041  mov     rax, [rax+8]
0x180001045  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000104a  mov     rcx, cs:?g_pUriCache@@3PEAVW3_URL_INFO_CACHE@@EA; W3_URL_INFO_CACHE * g_pUriCache
0x180001051  mov     rdx, rax
0x180001054  call    cs:__imp_?DeletePath@TREE_HASH_TABLE@@QEAAXPEBG@Z; TREE_HASH_TABLE::DeletePath(ushort const *)
0x18000105a  jmp     short loc_18000106E
0x18000105c  mov     rcx, cs:?g_pUriCache@@3PEAVW3_URL_INFO_CACHE@@EA; W3_URL_INFO_CACHE * g_pUriCache
0x180001063  test    rcx, rcx
0x180001066  jz      short loc_18000106E
0x180001068  call    cs:__imp_?Clear@TREE_HASH_TABLE@@QEAAXXZ; TREE_HASH_TABLE::Clear(void)
0x18000106e  xor     eax, eax
0x180001070  jmp     short loc_18000102C
```
