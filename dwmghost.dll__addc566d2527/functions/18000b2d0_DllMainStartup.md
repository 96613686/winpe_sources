# _DllMainStartup

- ea: `0x18000b2d0`
- end: `0x18000b334`
- name: `_DllMainStartup`
- size: `100`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180002644`
- `0x18000b2d0`

## pseudocode

```c
BOOL __stdcall DllMainStartup(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  BOOL v3; // r9d

  v3 = 1;
  if ( !fdwReason )
  {
    if ( !g_fAlwaysDetach && lpReserved )
      return v3;
    if ( avalonutil_proc_attached <= 0 )
      return 0;
    --avalonutil_proc_attached;
    fdwReason = 0;
    return DllMainCRTStartup(hinstDLL, fdwReason, lpReserved);
  }
  if ( fdwReason == 1 )
  {
    ++avalonutil_proc_attached;
    fdwReason = 1;
    return DllMainCRTStartup(hinstDLL, fdwReason, lpReserved);
  }
  if ( fdwReason - 2 <= 1 )
    return DllMainCRTStartup(hinstDLL, fdwReason, lpReserved);
  return v3;
}

```

## disassembly

```asm
0x18000b2d0  sub     rsp, 28h
0x18000b2d4  mov     r9d, 1
0x18000b2da  mov     eax, edx
0x18000b2dc  test    edx, edx
0x18000b2de  jz      short loc_18000B2FD
0x18000b2e0  sub     eax, r9d
0x18000b2e3  jz      short loc_18000B2F1
0x18000b2e5  sub     eax, r9d
0x18000b2e8  jz      short loc_18000B324
0x18000b2ea  cmp     eax, r9d
0x18000b2ed  jnz     short loc_18000B32C
0x18000b2ef  jmp     short loc_18000B324
0x18000b2f1  add     cs:avalonutil_proc_attached, r9d
0x18000b2f8  mov     edx, r9d
0x18000b2fb  jmp     short loc_18000B324
0x18000b2fd  cmp     cs:g_fAlwaysDetach, 0
0x18000b304  jnz     short loc_18000B30B
0x18000b306  test    r8, r8
0x18000b309  jnz     short loc_18000B32C
0x18000b30b  mov     eax, cs:avalonutil_proc_attached
0x18000b311  test    eax, eax
0x18000b313  jg      short loc_18000B319
0x18000b315  xor     eax, eax
0x18000b317  jmp     short loc_18000B32F
0x18000b319  sub     eax, r9d
0x18000b31c  mov     cs:avalonutil_proc_attached, eax
0x18000b322  xor     edx, edx; fdwReason
0x18000b324  call    _DllMainCRTStartup
0x18000b329  mov     r9d, eax
0x18000b32c  mov     eax, r9d
0x18000b32f  add     rsp, 28h
0x18000b333  retn
```
