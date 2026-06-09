# CSyncConflictCountCache::_DestroyEntry(CSyncConflictCountCache::ENTRY *)

- ea: `0x18001e0e8`
- end: `0x18001e11a`
- name: `?_DestroyEntry@CSyncConflictCountCache@@AEAAXPEAUENTRY@1@@Z`
- size: `50`
- prototype: `void __fastcall(CSyncConflictCountCache *__hidden this, struct CSyncConflictCountCache::ENTRY *)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001ba54`
- `0x18001dee8`

## callees

- `0x18001e0e8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e0f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e102`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e0f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e102`

## pseudocode

```c
void __fastcall CSyncConflictCountCache::_DestroyEntry(CSyncConflictCountCache *this, LPVOID *a2)
{
  if ( a2 )
  {
    CoTaskMemFree(a2[1]);
    CoTaskMemFree(*a2);
    *(_OWORD *)a2 = 0;
    a2[2] = 0;
  }
}

```

## disassembly

```asm
0x18001e0e8  test    rdx, rdx
0x18001e0eb  jz      short locret_18001E119
0x18001e0ed  push    rbx
0x18001e0ee  sub     rsp, 20h
0x18001e0f2  mov     rcx, [rdx+8]; pv
0x18001e0f6  mov     rbx, rdx
0x18001e0f9  call    cs:__imp_CoTaskMemFree
0x18001e0ff  mov     rcx, [rbx]; pv
0x18001e102  call    cs:__imp_CoTaskMemFree
0x18001e108  xorps   xmm0, xmm0
0x18001e10b  xor     eax, eax
0x18001e10d  movups  xmmword ptr [rbx], xmm0
0x18001e110  mov     [rbx+10h], rax
0x18001e114  add     rsp, 20h
0x18001e118  pop     rbx
0x18001e119  retn
```
