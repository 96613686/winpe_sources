# __scrt_is_managed_app

- ea: `0x140001748`
- end: `0x14000179a`
- name: `__scrt_is_managed_app`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140001180`

## callees

- `0x140001748`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000174e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000174e`

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
0x140001748  sub     rsp, 28h
0x14000174c  xor     ecx, ecx; lpModuleName
0x14000174e  call    cs:__imp_GetModuleHandleW
0x140001754  test    rax, rax
0x140001757  jz      short loc_140001793
0x140001759  mov     ecx, 5A4Dh
0x14000175e  cmp     [rax], cx
0x140001761  jnz     short loc_140001793
0x140001763  movsxd  rcx, dword ptr [rax+3Ch]
0x140001767  cmp     dword ptr [rcx+rax], 4550h
0x14000176e  jnz     short loc_140001793
0x140001770  mov     edx, 20Bh
0x140001775  cmp     [rcx+rax+18h], dx
0x14000177a  jnz     short loc_140001793
0x14000177c  cmp     dword ptr [rcx+rax+84h], 0Eh
0x140001784  jbe     short loc_140001793
0x140001786  cmp     dword ptr [rcx+rax+0F8h], 0
0x14000178e  setnz   al
0x140001791  jmp     short loc_140001795
0x140001793  xor     al, al
0x140001795  add     rsp, 28h
0x140001799  retn
```
