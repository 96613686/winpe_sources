# wistd::unique_ptr<void,wil::virtualalloc_deleter>::~unique_ptr<void,wil::virtualalloc_deleter>(void)

- ea: `0x180004370`
- end: `0x180004399`
- name: `??1?$unique_ptr@XUvirtualalloc_deleter@wil@@@wistd@@QEAA@XZ`
- size: `41`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18002b5f8`
- `0x18002b766`
- `0x18002b77c`
- `0x18002b792`
- `0x18002b7a8`

## callees

- `0x180004370`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18000438e`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18000438e`

## pseudocode

```c
int __fastcall wistd::unique_ptr<void,wil::virtualalloc_deleter>::~unique_ptr<void,wil::virtualalloc_deleter>(
        void **a1)
{
  void *v1; // rax

  v1 = *a1;
  *a1 = 0;
  if ( v1 )
    LODWORD(v1) = VirtualFree(v1, 0, 0x8000u);
  return (int)v1;
}

```

## disassembly

```asm
0x180004370  sub     rsp, 28h
0x180004374  mov     rax, [rcx]
0x180004377  mov     qword ptr [rcx], 0
0x18000437e  test    rax, rax
0x180004381  jz      short loc_180004394
0x180004383  xor     edx, edx; dwSize
0x180004385  mov     r8d, 8000h; dwFreeType
0x18000438b  mov     rcx, rax; lpAddress
0x18000438e  call    cs:__imp_VirtualFree
0x180004394  add     rsp, 28h
0x180004398  retn
```
