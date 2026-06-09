# DllMain

- ea: `0x18000a9e4`
- end: `0x18000aa4a`
- name: `DllMain`
- size: `102`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800013a4`

## callees

- `0x18000a9e4`
- `0x18000c89c`

## import_xrefs

- `KERNEL32!ReleaseActCtx` at `0x18000aa1a`
- `KERNEL32!ReleaseActCtx` at `0x18000aa1a`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      g_hinst = hinstDLL;
      return SHFusionInitializeFromModuleID(hinstDLL) != 0;
    }
  }
  else
  {
    if ( g_hActCtx != (HANDLE)-1LL )
    {
      ReleaseActCtx(g_hActCtx);
      g_hActCtx = (HANDLE)-1LL;
    }
    if ( hModule )
      hModule = (HMODULE)-1LL;
  }
  return 1;
}

```

## disassembly

```asm
0x18000a9e4  sub     rsp, 28h
0x18000a9e8  test    edx, edx
0x18000a9ea  jz      short loc_18000AA0D
0x18000a9ec  cmp     edx, 1
0x18000a9ef  jnz     short loc_18000AA40
0x18000a9f1  mov     edx, 7Bh ; '{'
0x18000a9f6  mov     cs:?g_hinst@@3PEAUHINSTANCE__@@EA, rcx; HINSTANCE__ * g_hinst
0x18000a9fd  call    SHFusionInitializeFromModuleID
0x18000aa02  xor     ecx, ecx
0x18000aa04  test    eax, eax
0x18000aa06  setnz   cl
0x18000aa09  mov     eax, ecx
0x18000aa0b  jmp     short loc_18000AA45
0x18000aa0d  mov     rcx, cs:g_hActCtx; hActCtx
0x18000aa14  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000aa18  jz      short loc_18000AA2B
0x18000aa1a  call    cs:__imp_ReleaseActCtx
0x18000aa20  mov     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x18000aa2b  cmp     cs:hModule, 0
0x18000aa33  jz      short loc_18000AA40
0x18000aa35  mov     cs:hModule, 0FFFFFFFFFFFFFFFFh
0x18000aa40  mov     eax, 1
0x18000aa45  add     rsp, 28h
0x18000aa49  retn
```
