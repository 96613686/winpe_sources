# InitSearchPaths(void)

- ea: `0x1400040c8`
- end: `0x14000411f`
- name: `?InitSearchPaths@@YAXXZ`
- size: `87`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400014e4`

## callees

- `0x1400040c8`
- `0x1400052b0`
- `0x140006010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1400040f8`
- `KERNEL32!GetProcAddress` at `0x1400040f8`
- `KERNEL32!SetDllDirectoryW` at `0x140004114`
- `KERNEL32!SetDllDirectoryW` at `0x140004114`
- `KERNEL32!GetModuleHandleW` at `0x1400040e3`
- `KERNEL32!GetModuleHandleW` at `0x1400040e3`

## string_xrefs

- `0x1400040dc`: `kernel32.dll`
- `0x1400040ee`: `SetSearchPathMode`

## pseudocode

```c
void InitSearchPaths(void)
{
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax

  if ( !(unsigned int)CFeatureControlKey::_CoInternetIsFeatureEnabledInternal((CFeatureControlKey *)&FCK::FEATURE_ENABLESAFESEARCHPATH_KB963027) )
  {
    ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
    if ( ModuleHandleW )
    {
      ProcAddress = GetProcAddress(ModuleHandleW, "SetSearchPathMode");
      if ( ProcAddress )
        ((void (__fastcall *)(__int64))ProcAddress)(1);
    }
    SetDllDirectoryW(&PathName);
  }
}

```

## disassembly

```asm
0x1400040c8  sub     rsp, 28h
0x1400040cc  lea     rcx, ?FEATURE_ENABLESAFESEARCHPATH_KB963027@FCK@@3VCFeatureControlKey@@A; this
0x1400040d3  call    ?_CoInternetIsFeatureEnabledInternal@CFeatureControlKey@@QEAAJXZ; CFeatureControlKey::_CoInternetIsFeatureEnabledInternal(void)
0x1400040d8  test    eax, eax
0x1400040da  jnz     short loc_14000411A
0x1400040dc  lea     rcx, ModuleName; "kernel32.dll"
0x1400040e3  call    cs:__imp_GetModuleHandleW
0x1400040e9  test    rax, rax
0x1400040ec  jz      short loc_14000410D
0x1400040ee  lea     rdx, ProcName; "SetSearchPathMode"
0x1400040f5  mov     rcx, rax; hModule
0x1400040f8  call    cs:__imp_GetProcAddress
0x1400040fe  test    rax, rax
0x140004101  jz      short loc_14000410D
0x140004103  mov     ecx, 1
0x140004108  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000410d  lea     rcx, PathName; lpPathName
0x140004114  call    cs:__imp_SetDllDirectoryW
0x14000411a  add     rsp, 28h
0x14000411e  retn
```
