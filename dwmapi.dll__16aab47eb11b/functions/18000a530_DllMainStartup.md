# _DllMainStartup

- ea: `0x18000a530`
- end: `0x18000a594`
- name: `_DllMainStartup`
- size: `100`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000a530`
- `0x18000d794`

## pseudocode

```c
BOOL __stdcall DllMainStartup(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  BOOL v3; // r9d

  v3 = 1;
  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      ++avalonutil_proc_attached;
      fdwReason = 1;
    }
    else if ( fdwReason - 2 >= 2 )
    {
      return v3;
    }
  }
  else
  {
    if ( !g_fAlwaysDetach && lpReserved )
      return v3;
    if ( avalonutil_proc_attached <= 0 )
      return 0;
    --avalonutil_proc_attached;
    fdwReason = 0;
  }
  return DllMainCRTStartup(hinstDLL, fdwReason, lpReserved);
}

```

## disassembly

```asm
0x18000a530  sub     rsp, 28h
0x18000a534  mov     r9d, 1
0x18000a53a  mov     eax, edx
0x18000a53c  test    edx, edx
0x18000a53e  jz      short loc_18000A55D
0x18000a540  sub     eax, r9d
0x18000a543  jz      short loc_18000A551
0x18000a545  sub     eax, r9d
0x18000a548  jz      short loc_18000A584
0x18000a54a  cmp     eax, r9d
0x18000a54d  jz      short loc_18000A584
0x18000a54f  jmp     short loc_18000A58C
0x18000a551  add     cs:avalonutil_proc_attached, r9d
0x18000a558  mov     edx, r9d
0x18000a55b  jmp     short loc_18000A584
0x18000a55d  cmp     cs:g_fAlwaysDetach, 0
0x18000a564  jnz     short loc_18000A56B
0x18000a566  test    r8, r8
0x18000a569  jnz     short loc_18000A58C
0x18000a56b  mov     eax, cs:avalonutil_proc_attached
0x18000a571  test    eax, eax
0x18000a573  jg      short loc_18000A579
0x18000a575  xor     eax, eax
0x18000a577  jmp     short loc_18000A58F
0x18000a579  sub     eax, r9d
0x18000a57c  mov     cs:avalonutil_proc_attached, eax
0x18000a582  xor     edx, edx; fdwReason
0x18000a584  call    _DllMainCRTStartup
0x18000a589  mov     r9d, eax
0x18000a58c  mov     eax, r9d
0x18000a58f  add     rsp, 28h
0x18000a593  retn
```
