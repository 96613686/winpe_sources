# _GetProcFromComCtl32

- ea: `0x18000fac4`
- end: `0x18000fb0c`
- name: `_GetProcFromComCtl32`
- size: `72`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800101a0`
- `0x1800131f0`

## callees

- `0x18000fa74`
- `0x18000fac4`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000faf8`
- `KERNEL32!GetProcAddress` at `0x18000faf8`

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
0x18000fac4  mov     [rsp+arg_0], rbx
0x18000fac9  push    rdi
0x18000faca  sub     rsp, 20h
0x18000face  mov     rbx, rcx
0x18000fad1  mov     rdi, rdx
0x18000fad4  mov     rcx, cs:g_hinstCC; hModule
0x18000fadb  test    rcx, rcx
0x18000fade  jnz     short loc_18000FAF5
0x18000fae0  call    DelayLoadCC
0x18000fae5  mov     rcx, cs:g_hinstCC
0x18000faec  test    rcx, rcx
0x18000faef  jnz     short loc_18000FAF5
0x18000faf1  xor     eax, eax
0x18000faf3  jmp     short loc_18000FAFE
0x18000faf5  mov     rdx, rdi; lpProcName
0x18000faf8  call    cs:__imp_GetProcAddress
0x18000fafe  mov     [rbx], rax
0x18000fb01  mov     rbx, [rsp+28h+arg_0]
0x18000fb06  add     rsp, 20h
0x18000fb0a  pop     rdi
0x18000fb0b  retn
```
