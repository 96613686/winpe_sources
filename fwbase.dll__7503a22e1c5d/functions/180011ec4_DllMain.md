# DllMain

- ea: `0x180011ec4`
- end: `0x180011f24`
- name: `DllMain`
- size: `96`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18001e034`

## callees

- `0x180011ec4`
- `0x180011f2c`
- `0x180011fd0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180011ecd`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180011ecd`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  if ( fdwReason == 1 )
  {
    DisableThreadLibraryCalls(hinstDLL);
    qword_18003C570 = 1;
    qword_18003C568 = 0;
    WPP_MAIN_CB = 0;
    WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_FwBase;
    WPP_GLOBAL_Control = &WPP_MAIN_CB;
    WppInitUm();
  }
  else if ( !fdwReason )
  {
    WppCleanupUm(hinstDLL, fdwReason, lpvReserved);
  }
  return 1;
}

```

## disassembly

```asm
0x180011ec4  sub     rsp, 28h
0x180011ec8  cmp     edx, 1
0x180011ecb  jnz     short loc_180011F19
0x180011ecd  call    cs:__imp_DisableThreadLibraryCalls
0x180011ed3  xor     eax, eax
0x180011ed5  mov     cs:qword_18003C570, 1
0x180011ee0  mov     cs:qword_18003C568, rax
0x180011ee7  mov     cs:WPP_MAIN_CB, rax
0x180011eee  lea     rax, WPP_ThisDir_CTLGUID_FwBase
0x180011ef5  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x180011efc  lea     rax, WPP_MAIN_CB
0x180011f03  mov     cs:WPP_GLOBAL_Control, rax
0x180011f0a  call    WppInitUm
0x180011f0f  mov     eax, 1
0x180011f14  add     rsp, 28h
0x180011f18  retn
0x180011f19  test    edx, edx
0x180011f1b  jnz     short loc_180011F0F
0x180011f1d  call    WppCleanupUm
0x180011f22  jmp     short loc_180011F0F
```
