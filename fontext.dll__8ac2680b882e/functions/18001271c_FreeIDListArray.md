# FreeIDListArray

- ea: `0x18001271c`
- end: `0x18001275f`
- name: `FreeIDListArray`
- size: `67`
- prototype: `void __stdcall(LPITEMIDLIST *ppidls, UINT cItems)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800116b8`
- `0x18002c828`

## callees

- `0x18001271c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001273a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001273a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012758`

## pseudocode

```c
void __stdcall FreeIDListArray(LPITEMIDLIST *ppidls, UINT cItems)
{
  __int64 i; // rbx

  for ( i = 0; (unsigned int)i < cItems; i = (unsigned int)(i + 1) )
    CoTaskMemFree(ppidls[i]);
  CoTaskMemFree(ppidls);
}

```

## disassembly

```asm
0x18001271c  mov     [rsp+arg_0], rbx
0x180012721  mov     [rsp+arg_8], rsi
0x180012726  push    rdi
0x180012727  sub     rsp, 20h
0x18001272b  xor     ebx, ebx
0x18001272d  mov     esi, edx
0x18001272f  mov     rdi, rcx
0x180012732  test    edx, edx
0x180012734  jz      short loc_180012746
0x180012736  mov     rcx, [rdi+rbx*8]; pv
0x18001273a  call    cs:__imp_CoTaskMemFree
0x180012740  inc     ebx
0x180012742  cmp     ebx, esi
0x180012744  jb      short loc_180012736
0x180012746  mov     rcx, rdi
0x180012749  mov     rbx, [rsp+28h+arg_0]
0x18001274e  mov     rsi, [rsp+28h+arg_8]
0x180012753  add     rsp, 20h
0x180012757  pop     rdi
0x180012758  jmp     cs:__imp_CoTaskMemFree
```
