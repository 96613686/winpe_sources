# DeleteInstance

- ea: `0x180008918`
- end: `0x18000895e`
- name: `DeleteInstance`
- size: `70`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180005990`
- `0x1800119c0`

## callees

- `0x180008918`
- `0x180008964`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008949`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008949`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000892a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008937`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000892a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008937`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008957`

## pseudocode

```c
HLOCAL __fastcall DeleteInstance(__int64 a1)
{
  HKEY v2; // rcx

  EmptyCustomFormats(a1);
  LocalFree(*(HLOCAL *)(a1 + 120));
  LocalFree(*(HLOCAL *)(a1 + 128));
  v2 = *(HKEY *)(a1 + 168);
  if ( v2 )
    RegCloseKey(v2);
  return LocalFree((HLOCAL)a1);
}

```

## disassembly

```asm
0x180008918  push    rbx
0x18000891a  sub     rsp, 20h
0x18000891e  mov     rbx, rcx
0x180008921  call    EmptyCustomFormats
0x180008926  mov     rcx, [rbx+78h]; hMem
0x18000892a  call    cs:__imp_LocalFree
0x180008930  mov     rcx, [rbx+80h]; hMem
0x180008937  call    cs:__imp_LocalFree
0x18000893d  mov     rcx, [rbx+0A8h]; hKey
0x180008944  test    rcx, rcx
0x180008947  jz      short loc_18000894F
0x180008949  call    cs:__imp_RegCloseKey
0x18000894f  mov     rcx, rbx
0x180008952  add     rsp, 20h
0x180008956  pop     rbx
0x180008957  jmp     cs:__imp_LocalFree
```
