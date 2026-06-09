# CConvertStr::Free(void)

- ea: `0x10032925`
- end: `0x10032950`
- name: `?Free@CConvertStr@@IAEXXZ`
- size: `43`
- prototype: `void __thiscall(CConvertStr *__hidden this)`
- caller_count: `24`
- callee_count: `1`
- tags: ``

## callers

- `0x1003291a`
- `0x10032aee`
- `0x10032b3c`
- `0x10032c26`
- `0x10032cb3`
- `0x10032d47`
- `0x10032deb`
- `0x10032ea8`
- `0x10032f10`
- `0x10032fa0`
- `0x1003306e`
- `0x100330d6`
- `0x100331da`
- `0x1003325b`
- `0x10033488`
- `0x100335a6`
- `0x1003363d`
- `0x100336a8`
- `0x1003379f`
- `0x10033823`
- `0x100338a0`
- `0x1003391f`
- `0x1003399e`
- `0x10033a09`

## callees

- `0x10032925`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10032943`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10032943`

## pseudocode

```c
void __thiscall CConvertStr::Free(void **this)
{
  if ( this[1] != this + 2 && *((_WORD *)this + 3) && *this != (void *)-1 )
    _free(this[1]);
  this[1] = 0;
}

```

## disassembly

```asm
0x10032925  mov     edi, edi
0x10032927  push    esi
0x10032928  mov     esi, ecx
0x1003292a  push    edi
0x1003292b  xor     edi, edi
0x1003292d  lea     eax, [esi+8]
0x10032930  cmp     [esi+4], eax
0x10032933  jz      short loc_1003294A
0x10032935  cmp     [esi+6], di
0x10032939  jz      short loc_1003294A
0x1003293b  cmp     dword ptr [esi], 0FFFFFFFFh
0x1003293e  jz      short loc_1003294A
0x10032940  push    dword ptr [esi+4]; Block
0x10032943  call    ds:__imp__free
0x10032949  pop     ecx
0x1003294a  mov     [esi+4], edi
0x1003294d  pop     edi
0x1003294e  pop     esi
0x1003294f  retn
```
