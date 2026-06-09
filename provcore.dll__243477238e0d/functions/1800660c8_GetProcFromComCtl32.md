# _GetProcFromComCtl32

- ea: `0x1800660c8`
- end: `0x180066108`
- name: `_GetProcFromComCtl32`
- size: `64`
- prototype: `void __fastcall(__int64 (**ppfn)(...), const char *ppfn)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180066028`

## callees

- `0x180065fb4`
- `0x1800660c8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800660f9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800660f9`

## string_xrefs

- `0x1800660f2`: `TaskDialogIndirect`

## pseudocode

```c
void __fastcall GetProcFromComCtl32(__int64 (**ppfn)(...), const char *a2)
{
  HMODULE v3; // rcx
  __int64 (*ProcAddress)(...); // rax

  v3 = g_hinstCC;
  if ( g_hinstCC || (DelayLoadCC(0), (v3 = g_hinstCC) != 0) )
    ProcAddress = (__int64 (*)(...))GetProcAddress(v3, "TaskDialogIndirect");
  else
    ProcAddress = 0;
  *ppfn = ProcAddress;
}

```

## disassembly

```asm
0x1800660c8  push    rbx
0x1800660ca  sub     rsp, 20h
0x1800660ce  mov     rbx, ppfn
0x1800660d1  mov     ppfn, cs:g_hinstCC; hModule
0x1800660d8  test    ppfn, ppfn
0x1800660db  jnz     short loc_1800660F2
0x1800660dd  call    DelayLoadCC
0x1800660e2  mov     ppfn, cs:g_hinstCC
0x1800660e9  test    ppfn, ppfn
0x1800660ec  jnz     short loc_1800660F2
0x1800660ee  xor     eax, eax
0x1800660f0  jmp     short loc_1800660FF
0x1800660f2  lea     rdx, ProcName; "TaskDialogIndirect"
0x1800660f9  call    cs:__imp_GetProcAddress
0x1800660ff  mov     [rbx], rax
0x180066102  add     rsp, 20h
0x180066106  pop     rbx
0x180066107  retn
```
