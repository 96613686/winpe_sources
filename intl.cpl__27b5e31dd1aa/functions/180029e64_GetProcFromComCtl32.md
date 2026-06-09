# _GetProcFromComCtl32

- ea: `0x180029e64`
- end: `0x180029eac`
- name: `_GetProcFromComCtl32`
- size: `72`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800299f4`
- `0x180029a88`
- `0x180029adc`
- `0x180029b28`
- `0x180029b74`
- `0x180029bc8`
- `0x180029c84`
- `0x180029cd4`
- `0x180029d60`
- `0x180029dfc`

## callees

- `0x180029c34`
- `0x180029e64`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180029e98`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180029e98`

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
0x180029e64  mov     [rsp+arg_0], rbx
0x180029e69  push    rdi
0x180029e6a  sub     rsp, 20h
0x180029e6e  mov     rbx, rcx
0x180029e71  mov     rdi, rdx
0x180029e74  mov     rcx, cs:g_hinstCC; hModule
0x180029e7b  test    rcx, rcx
0x180029e7e  jnz     short loc_180029E95
0x180029e80  call    DelayLoadCC
0x180029e85  mov     rcx, cs:g_hinstCC
0x180029e8c  test    rcx, rcx
0x180029e8f  jnz     short loc_180029E95
0x180029e91  xor     eax, eax
0x180029e93  jmp     short loc_180029E9E
0x180029e95  mov     rdx, rdi; lpProcName
0x180029e98  call    cs:__imp_GetProcAddress
0x180029e9e  mov     [rbx], rax
0x180029ea1  mov     rbx, [rsp+28h+arg_0]
0x180029ea6  add     rsp, 20h
0x180029eaa  pop     rdi
0x180029eab  retn
```
