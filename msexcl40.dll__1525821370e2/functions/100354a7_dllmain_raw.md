# dllmain_raw

- ea: `0x100354a7`
- end: `0x100354d4`
- name: `dllmain_raw`
- size: `45`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x10035398`

## callees

- `0x100354a7`
- `0x10035b40`

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
0x100354a7  mov     edi, edi
0x100354a9  push    ebp
0x100354aa  mov     ebp, esp
0x100354ac  push    esi
0x100354ad  mov     esi, ds:__pRawDllMain
0x100354b3  test    esi, esi
0x100354b5  jnz     short loc_100354BC
0x100354b7  xor     eax, eax
0x100354b9  inc     eax
0x100354ba  jmp     short loc_100354CF
0x100354bc  push    [ebp+arg_8]
0x100354bf  mov     ecx, esi
0x100354c1  push    [ebp+arg_4]
0x100354c4  push    [ebp+arg_0]
0x100354c7  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x100354cd  call    esi ; __pRawDllMain
0x100354cf  pop     esi
0x100354d0  pop     ebp
0x100354d1  retn    0Ch
```
