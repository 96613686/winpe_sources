# _GetProcFromComCtl32

- ea: `0x1800128e4`
- end: `0x18001292c`
- name: `_GetProcFromComCtl32`
- size: `72`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180012738`
- `0x180012784`
- `0x1800127d0`
- `0x180012828`

## callees

- `0x180012894`
- `0x1800128e4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012918`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012918`

## pseudocode

```c
FARPROC __fastcall GetProcFromComCtl32(FARPROC *a1, const CHAR *a2)
{
  HMODULE v4; // rcx
  FARPROC result; // rax

  v4 = g_hinstCC;
  if ( g_hinstCC || (DelayLoadCC(), (v4 = g_hinstCC) != 0) )
    result = GetProcAddress(v4, a2);
  else
    result = 0;
  *a1 = result;
  return result;
}

```

## disassembly

```asm
0x1800128e4  mov     [rsp+arg_0], rbx
0x1800128e9  push    rdi
0x1800128ea  sub     rsp, 20h
0x1800128ee  mov     rbx, rcx
0x1800128f1  mov     rdi, rdx
0x1800128f4  mov     rcx, cs:g_hinstCC; hModule
0x1800128fb  test    rcx, rcx
0x1800128fe  jnz     short loc_180012915
0x180012900  call    DelayLoadCC
0x180012905  mov     rcx, cs:g_hinstCC
0x18001290c  test    rcx, rcx
0x18001290f  jnz     short loc_180012915
0x180012911  xor     eax, eax
0x180012913  jmp     short loc_18001291E
0x180012915  mov     rdx, rdi; lpProcName
0x180012918  call    cs:__imp_GetProcAddress
0x18001291e  mov     [rbx], rax
0x180012921  mov     rbx, [rsp+28h+arg_0]
0x180012926  add     rsp, 20h
0x18001292a  pop     rdi
0x18001292b  retn
```
