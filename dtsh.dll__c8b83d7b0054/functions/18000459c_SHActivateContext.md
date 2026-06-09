# SHActivateContext

- ea: `0x18000459c`
- end: `0x1800045fe`
- name: `SHActivateContext`
- size: `98`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003b00`
- `0x18000471c`

## callees

- `0x18000459c`
- `0x180004604`

## import_xrefs

- `KERNEL32!ActivateActCtx` at `0x1800045f7`

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
  if ( hModule == g_hActCtx )
    return 0;
  SHFusionInitializeFromModuleID();
  v2 = g_hActCtx;
  return g_hActCtx == (HANDLE)-1LL || ActivateActCtx(v2, a1);
}

```

## disassembly

```asm
0x18000459c  push    rbx
0x18000459e  sub     rsp, 20h
0x1800045a2  mov     rbx, rcx
0x1800045a5  mov     qword ptr [rcx], 0
0x1800045ac  mov     rcx, cs:g_hActCtx
0x1800045b3  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800045b7  jnz     short loc_1800045EF
0x1800045b9  mov     rax, cs:hModule
0x1800045c0  test    rax, rax
0x1800045c3  jz      short loc_1800045E4
0x1800045c5  cmp     rax, rcx
0x1800045c8  jnz     short loc_1800045D2
0x1800045ca  xor     eax, eax
0x1800045cc  add     rsp, 20h
0x1800045d0  pop     rbx
0x1800045d1  retn
0x1800045d2  call    SHFusionInitializeFromModuleID
0x1800045d7  mov     rcx, cs:g_hActCtx
0x1800045de  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800045e2  jnz     short loc_1800045EF
0x1800045e4  mov     eax, 1
0x1800045e9  add     rsp, 20h
0x1800045ed  pop     rbx
0x1800045ee  retn
0x1800045ef  mov     rdx, rbx
0x1800045f2  add     rsp, 20h
0x1800045f6  pop     rbx
0x1800045f7  jmp     cs:__imp_ActivateActCtx
```
