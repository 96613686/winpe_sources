# __scrt_is_managed_app

- ea: `0x1400024a8`
- end: `0x1400024fa`
- name: `__scrt_is_managed_app`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140001f00`

## callees

- `0x1400024a8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400024ae`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400024ae`

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
0x1400024a8  sub     rsp, 28h
0x1400024ac  xor     ecx, ecx; lpModuleName
0x1400024ae  call    cs:__imp_GetModuleHandleW
0x1400024b4  test    rax, rax
0x1400024b7  jz      short loc_1400024F3
0x1400024b9  mov     ecx, 5A4Dh
0x1400024be  cmp     [rax], cx
0x1400024c1  jnz     short loc_1400024F3
0x1400024c3  movsxd  rcx, dword ptr [rax+3Ch]
0x1400024c7  cmp     dword ptr [rcx+rax], 4550h
0x1400024ce  jnz     short loc_1400024F3
0x1400024d0  mov     edx, 20Bh
0x1400024d5  cmp     [rcx+rax+18h], dx
0x1400024da  jnz     short loc_1400024F3
0x1400024dc  cmp     dword ptr [rcx+rax+84h], 0Eh
0x1400024e4  jbe     short loc_1400024F3
0x1400024e6  cmp     dword ptr [rcx+rax+0F8h], 0
0x1400024ee  setnz   al
0x1400024f1  jmp     short loc_1400024F5
0x1400024f3  xor     al, al
0x1400024f5  add     rsp, 28h
0x1400024f9  retn
```
