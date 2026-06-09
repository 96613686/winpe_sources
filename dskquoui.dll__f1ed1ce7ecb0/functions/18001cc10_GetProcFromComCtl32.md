# _GetProcFromComCtl32

- ea: `0x18001cc10`
- end: `0x18001cc58`
- name: `_GetProcFromComCtl32`
- size: `72`
- prototype: ``
- caller_count: `18`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001c400`
- `0x18001c49c`
- `0x18001c4f0`
- `0x18001c544`
- `0x18001c590`
- `0x18001c5e8`
- `0x18001c644`
- `0x18001c6b0`
- `0x18001c718`
- `0x18001c76c`
- `0x18001c7b8`
- `0x18001c81c`
- `0x18001c8e0`
- `0x18001ca18`
- `0x18001ca80`
- `0x18001caec`
- `0x18001cb44`
- `0x18001cb84`

## callees

- `0x18001c888`
- `0x18001cc10`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001cc44`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001cc44`

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
0x18001cc10  mov     [rsp+arg_0], rbx
0x18001cc15  push    rdi
0x18001cc16  sub     rsp, 20h
0x18001cc1a  mov     rbx, rcx
0x18001cc1d  mov     rdi, rdx
0x18001cc20  mov     rcx, cs:g_hinstCC; hModule
0x18001cc27  test    rcx, rcx
0x18001cc2a  jnz     short loc_18001CC41
0x18001cc2c  call    DelayLoadCC
0x18001cc31  mov     rcx, cs:g_hinstCC
0x18001cc38  test    rcx, rcx
0x18001cc3b  jnz     short loc_18001CC41
0x18001cc3d  xor     eax, eax
0x18001cc3f  jmp     short loc_18001CC4A
0x18001cc41  mov     rdx, rdi; lpProcName
0x18001cc44  call    cs:__imp_GetProcAddress
0x18001cc4a  mov     [rbx], rax
0x18001cc4d  mov     rbx, [rsp+28h+arg_0]
0x18001cc52  add     rsp, 20h
0x18001cc56  pop     rdi
0x18001cc57  retn
```
