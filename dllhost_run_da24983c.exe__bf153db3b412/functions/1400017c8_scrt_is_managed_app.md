# __scrt_is_managed_app

- ea: `0x1400017c8`
- end: `0x14000181a`
- name: `__scrt_is_managed_app`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400011d0`

## callees

- `0x1400017c8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400017ce`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400017ce`

## pseudocode

```c
bool _scrt_is_managed_app()
{
  HMODULE ModuleHandleW; // rax
  __int64 v1; // rcx
  bool result; // al

  ModuleHandleW = GetModuleHandleW(0);
  result = ModuleHandleW
        && *(_WORD *)ModuleHandleW == 23117
        && (v1 = *((int *)ModuleHandleW + 15), *(_DWORD *)((char *)ModuleHandleW + v1) == 17744)
        && *(_WORD *)((char *)ModuleHandleW + v1 + 24) == 523
        && *(_DWORD *)((char *)ModuleHandleW + v1 + 132) > 0xEu
        && *(_DWORD *)((char *)ModuleHandleW + v1 + 248) != 0;
  return result;
}

```

## disassembly

```asm
0x1400017c8  sub     rsp, 28h
0x1400017cc  xor     ecx, ecx; lpModuleName
0x1400017ce  call    cs:__imp_GetModuleHandleW
0x1400017d4  test    rax, rax
0x1400017d7  jz      short loc_140001813
0x1400017d9  mov     ecx, 5A4Dh
0x1400017de  cmp     [rax], cx
0x1400017e1  jnz     short loc_140001813
0x1400017e3  movsxd  rcx, dword ptr [rax+3Ch]
0x1400017e7  cmp     dword ptr [rcx+rax], 4550h
0x1400017ee  jnz     short loc_140001813
0x1400017f0  mov     edx, 20Bh
0x1400017f5  cmp     [rcx+rax+18h], dx
0x1400017fa  jnz     short loc_140001813
0x1400017fc  cmp     dword ptr [rcx+rax+84h], 0Eh
0x140001804  jbe     short loc_140001813
0x140001806  cmp     dword ptr [rcx+rax+0F8h], 0
0x14000180e  setnz   al
0x140001811  jmp     short loc_140001815
0x140001813  xor     al, al
0x140001815  add     rsp, 28h
0x140001819  retn
```
