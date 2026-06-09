# ReleaseDpaMember(void *,void *)

- ea: `0x18001bfc0`
- end: `0x18001bfd4`
- name: `?ReleaseDpaMember@@YAHPEAX0@Z`
- size: `20`
- prototype: `__int64 __fastcall(void *, void *)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bfc4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bfc4`

## pseudocode

```c
__int64 __fastcall ReleaseDpaMember(void *a1, void *a2)
{
  CoTaskMemFree(a1);
  return 1;
}

```

## disassembly

```asm
0x18001bfc0  sub     rsp, 28h
0x18001bfc4  call    cs:__imp_CoTaskMemFree
0x18001bfca  mov     eax, 1
0x18001bfcf  add     rsp, 28h
0x18001bfd3  retn
```
