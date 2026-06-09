# _GetProcFromComCtl32

- ea: `0x180026fa0`
- end: `0x180026fe8`
- name: `_GetProcFromComCtl32`
- size: `72`
- prototype: ``
- caller_count: `19`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180026838`
- `0x180026884`
- `0x1800268d8`
- `0x180026924`
- `0x18002698c`
- `0x1800269f4`
- `0x180026a4c`
- `0x180026ab8`
- `0x180026b34`
- `0x180026b88`
- `0x180026bd4`
- `0x180026c3c`
- `0x180026ca0`
- `0x180026cf4`
- `0x180026d60`
- `0x180026e14`
- `0x180026e64`
- `0x180026ef0`
- `0x180026f48`

## callees

- `0x180026dc4`
- `0x180026fa0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180026fd4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180026fd4`

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
0x180026fa0  mov     [rsp+arg_0], rbx
0x180026fa5  push    rdi
0x180026fa6  sub     rsp, 20h
0x180026faa  mov     rbx, rcx
0x180026fad  mov     rdi, rdx
0x180026fb0  mov     rcx, cs:g_hinstCC; hModule
0x180026fb7  test    rcx, rcx
0x180026fba  jnz     short loc_180026FD1
0x180026fbc  call    DelayLoadCC
0x180026fc1  mov     rcx, cs:g_hinstCC
0x180026fc8  test    rcx, rcx
0x180026fcb  jnz     short loc_180026FD1
0x180026fcd  xor     eax, eax
0x180026fcf  jmp     short loc_180026FDA
0x180026fd1  mov     rdx, rdi; lpProcName
0x180026fd4  call    cs:__imp_GetProcAddress
0x180026fda  mov     [rbx], rax
0x180026fdd  mov     rbx, [rsp+28h+arg_0]
0x180026fe2  add     rsp, 20h
0x180026fe6  pop     rdi
0x180026fe7  retn
```
