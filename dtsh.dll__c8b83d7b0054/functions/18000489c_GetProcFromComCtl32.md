# _GetProcFromComCtl32

- ea: `0x18000489c`
- end: `0x1800048e4`
- name: `_GetProcFromComCtl32`
- size: `72`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800047cc`
- `0x180004834`

## callees

- `0x18000477c`
- `0x18000489c`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800048d0`
- `KERNEL32!GetProcAddress` at `0x1800048d0`

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
0x18000489c  mov     [rsp+arg_0], rbx
0x1800048a1  push    rdi
0x1800048a2  sub     rsp, 20h
0x1800048a6  mov     rbx, rcx
0x1800048a9  mov     rdi, rdx
0x1800048ac  mov     rcx, cs:g_hinstCC; hModule
0x1800048b3  test    rcx, rcx
0x1800048b6  jnz     short loc_1800048CD
0x1800048b8  call    DelayLoadCC
0x1800048bd  mov     rcx, cs:g_hinstCC
0x1800048c4  test    rcx, rcx
0x1800048c7  jnz     short loc_1800048CD
0x1800048c9  xor     eax, eax
0x1800048cb  jmp     short loc_1800048D6
0x1800048cd  mov     rdx, rdi; lpProcName
0x1800048d0  call    cs:__imp_GetProcAddress
0x1800048d6  mov     [rbx], rax
0x1800048d9  mov     rbx, [rsp+28h+arg_0]
0x1800048de  add     rsp, 20h
0x1800048e2  pop     rdi
0x1800048e3  retn
```
