# _GetProcFromComCtl32

- ea: `0x1800183e4`
- end: `0x18001842c`
- name: `_GetProcFromComCtl32`
- size: `72`
- prototype: `FARPROC __fastcall(FARPROC *, const CHAR *)`
- caller_count: `10`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180017eb8`
- `0x180017f54`
- `0x180017fa8`
- `0x180017ff4`
- `0x180018040`
- `0x1800180a4`
- `0x180018168`
- `0x1800182a0`
- `0x1800182f0`
- `0x18001837c`

## callees

- `0x180018110`
- `0x1800183e4`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180018418`
- `KERNEL32!GetProcAddress` at `0x180018418`

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
0x1800183e4  mov     [rsp+arg_0], rbx
0x1800183e9  push    rdi
0x1800183ea  sub     rsp, 20h
0x1800183ee  mov     rbx, rcx
0x1800183f1  mov     rdi, rdx
0x1800183f4  mov     rcx, cs:g_hinstCC; hModule
0x1800183fb  test    rcx, rcx
0x1800183fe  jnz     short loc_180018415
0x180018400  call    DelayLoadCC
0x180018405  mov     rcx, cs:g_hinstCC
0x18001840c  test    rcx, rcx
0x18001840f  jnz     short loc_180018415
0x180018411  xor     eax, eax
0x180018413  jmp     short loc_18001841E
0x180018415  mov     rdx, rdi; lpProcName
0x180018418  call    cs:__imp_GetProcAddress
0x18001841e  mov     [rbx], rax
0x180018421  mov     rbx, [rsp+28h+arg_0]
0x180018426  add     rsp, 20h
0x18001842a  pop     rdi
0x18001842b  retn
```
