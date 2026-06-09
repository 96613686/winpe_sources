# SHActivateContext

- ea: `0x18000c82c`
- end: `0x18000c895`
- name: `SHActivateContext`
- size: `105`
- prototype: `BOOL __fastcall(ULONG_PTR *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000642c`
- `0x18000bda0`
- `0x18000c9a8`

## callees

- `0x18000c82c`
- `0x18000c89c`

## import_xrefs

- `KERNEL32!ActivateActCtx` at `0x18000c88e`

## pseudocode

```c
BOOL __fastcall SHActivateContext(ULONG_PTR *a1)
{
  HANDLE v2; // rcx

  *a1 = 0;
  v2 = g_hActCtx;
  if ( g_hActCtx != (HANDLE)-1LL )
    return ActivateActCtx(v2, a1);
  if ( !hModule )
    return 1;
  if ( hModule == (HMODULE)-1LL )
    return 0;
  SHFusionInitializeFromModuleID(hModule);
  v2 = g_hActCtx;
  return g_hActCtx == (HANDLE)-1LL || ActivateActCtx(v2, a1);
}

```

## disassembly

```asm
0x18000c82c  push    rbx
0x18000c82e  sub     rsp, 20h
0x18000c832  mov     rbx, rcx
0x18000c835  mov     qword ptr [rcx], 0
0x18000c83c  mov     rcx, cs:g_hActCtx
0x18000c843  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000c847  jnz     short loc_18000C886
0x18000c849  mov     rcx, cs:hModule; hModule
0x18000c850  test    rcx, rcx
0x18000c853  jz      short loc_18000C87B
0x18000c855  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000c859  jnz     short loc_18000C863
0x18000c85b  xor     eax, eax
0x18000c85d  add     rsp, 20h
0x18000c861  pop     rbx
0x18000c862  retn
0x18000c863  mov     edx, cs:dword_180014864
0x18000c869  call    SHFusionInitializeFromModuleID
0x18000c86e  mov     rcx, cs:g_hActCtx
0x18000c875  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000c879  jnz     short loc_18000C886
0x18000c87b  mov     eax, 1
0x18000c880  add     rsp, 20h
0x18000c884  pop     rbx
0x18000c885  retn
0x18000c886  mov     rdx, rbx
0x18000c889  add     rsp, 20h
0x18000c88d  pop     rbx
0x18000c88e  jmp     cs:__imp_ActivateActCtx
```
