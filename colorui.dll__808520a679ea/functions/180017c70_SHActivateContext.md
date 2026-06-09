# SHActivateContext

- ea: `0x180017c70`
- end: `0x180017cd2`
- name: `SHActivateContext`
- size: `98`
- prototype: `BOOL __fastcall(ULONG_PTR *)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ca3c`
- `0x18000d338`
- `0x180017df0`
- `0x180017e4c`
- `0x180017eb8`
- `0x1800181b8`
- `0x18001822c`

## callees

- `0x180017c70`
- `0x180017cd8`

## import_xrefs

- `KERNEL32!ActivateActCtx` at `0x180017ccb`

## pseudocode

```c
BOOL __fastcall SHActivateContext(ULONG_PTR *a1)
{
  void *v2; // rcx

  *a1 = 0;
  v2 = (void *)g_hActCtx;
  if ( g_hActCtx != -1 )
    return ActivateActCtx(v2, a1);
  if ( !hModule )
    return 1;
  if ( hModule == (HMODULE)g_hActCtx )
    return 0;
  SHFusionInitializeFromModuleID();
  v2 = (void *)g_hActCtx;
  return g_hActCtx == -1 || ActivateActCtx(v2, a1);
}

```

## disassembly

```asm
0x180017c70  push    rbx
0x180017c72  sub     rsp, 20h
0x180017c76  mov     rbx, rcx
0x180017c79  mov     qword ptr [rcx], 0
0x180017c80  mov     rcx, cs:g_hActCtx
0x180017c87  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180017c8b  jnz     short loc_180017CC3
0x180017c8d  mov     rax, cs:hModule
0x180017c94  test    rax, rax
0x180017c97  jz      short loc_180017CB8
0x180017c99  cmp     rax, rcx
0x180017c9c  jnz     short loc_180017CA6
0x180017c9e  xor     eax, eax
0x180017ca0  add     rsp, 20h
0x180017ca4  pop     rbx
0x180017ca5  retn
0x180017ca6  call    SHFusionInitializeFromModuleID
0x180017cab  mov     rcx, cs:g_hActCtx
0x180017cb2  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180017cb6  jnz     short loc_180017CC3
0x180017cb8  mov     eax, 1
0x180017cbd  add     rsp, 20h
0x180017cc1  pop     rbx
0x180017cc2  retn
0x180017cc3  mov     rdx, rbx
0x180017cc6  add     rsp, 20h
0x180017cca  pop     rbx
0x180017ccb  jmp     cs:__imp_ActivateActCtx
```
