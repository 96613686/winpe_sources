# DllCanUnloadNow

- ea: `0x18002d0e4`
- end: `0x18002d12e`
- name: `DllCanUnloadNow`
- size: `74`
- prototype: `HRESULT __stdcall()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180007b40`

## callees

- `0x18002d0e4`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18002d105`
- `KERNEL32!GetProcAddress` at `0x18002d105`

## string_xrefs

- `0x18002d0fe`: `DllCanUnloadNowInternal`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  struct ModuleList *v0; // rbx
  unsigned int (*ProcAddress)(void); // rax

  v0 = g_pLoadedModules;
  if ( g_pLoadedModules )
  {
    while ( v0 )
    {
      ProcAddress = (unsigned int (*)(void))GetProcAddress(*(HMODULE *)v0, "DllCanUnloadNowInternal");
      if ( !ProcAddress || ProcAddress() )
        return 1;
      v0 = (struct ModuleList *)*((_QWORD *)v0 + 1);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18002d0e4  push    rbx
0x18002d0e6  sub     rsp, 20h
0x18002d0ea  mov     rbx, cs:?g_pLoadedModules@@3PEAUModuleList@@EA; ModuleList * g_pLoadedModules
0x18002d0f1  test    rbx, rbx
0x18002d0f4  jz      short loc_18002D126
0x18002d0f6  test    rbx, rbx
0x18002d0f9  jz      short loc_18002D126
0x18002d0fb  mov     rcx, [rbx]; hModule
0x18002d0fe  lea     rdx, aDllcanunloadno_1; "DllCanUnloadNowInternal"
0x18002d105  call    cs:__imp_GetProcAddress
0x18002d10b  test    rax, rax
0x18002d10e  jz      short loc_18002D11F
0x18002d110  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d115  test    eax, eax
0x18002d117  jnz     short loc_18002D11F
0x18002d119  mov     rbx, [rbx+8]
0x18002d11d  jmp     short loc_18002D0F6
0x18002d11f  mov     eax, 1
0x18002d124  jmp     short loc_18002D128
0x18002d126  xor     eax, eax
0x18002d128  add     rsp, 20h
0x18002d12c  pop     rbx
0x18002d12d  retn
```
