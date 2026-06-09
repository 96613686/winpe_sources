# dllmain_raw

- ea: `0x10012ae7`
- end: `0x10012b14`
- name: `dllmain_raw`
- size: `45`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x100129d8`

## callees

- `0x10012ae7`
- `0x100130b0`

## pseudocode

```c
int __stdcall dllmain_raw(int a1, int a2, int a3)
{
  if ( _pRawDllMain )
    return _pRawDllMain(_pRawDllMain, a1, a2, a3);
  else
    return 1;
}

```

## disassembly

```asm
0x10012ae7  mov     edi, edi
0x10012ae9  push    ebp
0x10012aea  mov     ebp, esp
0x10012aec  push    esi
0x10012aed  mov     esi, ds:__pRawDllMain
0x10012af3  test    esi, esi
0x10012af5  jnz     short loc_10012AFC
0x10012af7  xor     eax, eax
0x10012af9  inc     eax
0x10012afa  jmp     short loc_10012B0F
0x10012afc  push    [ebp+arg_8]
0x10012aff  mov     ecx, esi
0x10012b01  push    [ebp+arg_4]
0x10012b04  push    [ebp+arg_0]
0x10012b07  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10012b0d  call    esi ; __pRawDllMain
0x10012b0f  pop     esi
0x10012b10  pop     ebp
0x10012b11  retn    0Ch
```
