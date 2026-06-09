# SuppressUnsafeExtensionPolicy

- ea: `0x1800940a4`
- end: `0x18009415d`
- name: `SuppressUnsafeExtensionPolicy`
- size: `185`
- prototype: `void()`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800525d0`

## callees

- `0x1800940a4`
- `0x180098010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800940e9`
- `KERNEL32!GetProcAddress` at `0x18009412a`
- `KERNEL32!GetProcAddress` at `0x1800940e9`
- `KERNEL32!GetProcAddress` at `0x18009412a`
- `KERNEL32!GetModuleHandleW` at `0x1800940cb`
- `KERNEL32!GetModuleHandleW` at `0x1800940cb`

## string_xrefs

- `0x1800940c4`: `api-ms-win-core-processthreads-l1-1-2.dll`

## pseudocode

```c
void SuppressUnsafeExtensionPolicy()
{
  HMODULE ModuleHandleW; // rax
  HMODULE v1; // rbx
  FARPROC ProcAddress; // rax
  FARPROC v3; // rax
  __int64 v4; // [rsp+30h] [rbp+8h] BYREF

  v4 = 0;
  if ( !g_fUnsafeExtensionPolicySuppressed )
  {
    ModuleHandleW = GetModuleHandleW(L"api-ms-win-core-processthreads-l1-1-2.dll");
    v1 = ModuleHandleW;
    if ( ModuleHandleW )
    {
      ProcAddress = GetProcAddress(ModuleHandleW, "QueryProtectedPolicy");
      if ( ProcAddress )
      {
        if ( ((unsigned int (__fastcall *)(__int64 *, __int64 *))ProcAddress)(PPID_ProhibitUnsafeExtensions, &v4)
          && v4 == 2 )
        {
          v4 = 1;
          v3 = GetProcAddress(v1, "SetProtectedPolicy");
          if ( v3 )
            ((void (__fastcall *)(__int64 *, __int64, _QWORD))v3)(PPID_ProhibitUnsafeExtensions, v4, 0);
        }
      }
    }
    g_fUnsafeExtensionPolicySuppressed = 1;
  }
}

```

## disassembly

```asm
0x1800940a4  mov     [rsp+arg_0], rcx
0x1800940a9  push    rbx
0x1800940aa  sub     rsp, 20h
0x1800940ae  cmp     cs:?g_fUnsafeExtensionPolicySuppressed@@3_NA, 0; bool g_fUnsafeExtensionPolicySuppressed
0x1800940b5  mov     [rsp+28h+arg_0], 0
0x1800940be  jnz     loc_180094156
0x1800940c4  lea     rcx, ModuleName; "api-ms-win-core-processthreads-l1-1-2.d"...
0x1800940cb  call    cs:__imp_GetModuleHandleW
0x1800940d2  nop     dword ptr [rax+rax+00h]
0x1800940d7  mov     rbx, rax
0x1800940da  test    rax, rax
0x1800940dd  jz      short loc_18009414F
0x1800940df  lea     rdx, aQueryprotected; "QueryProtectedPolicy"
0x1800940e6  mov     rcx, rax; hModule
0x1800940e9  call    cs:__imp_GetProcAddress
0x1800940f0  nop     dword ptr [rax+rax+00h]
0x1800940f5  test    rax, rax
0x1800940f8  jz      short loc_18009414F
0x1800940fa  lea     rdx, [rsp+28h+arg_0]
0x1800940ff  lea     rcx, PPID_ProhibitUnsafeExtensions
0x180094106  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009410b  test    eax, eax
0x18009410d  jz      short loc_18009414F
0x18009410f  cmp     [rsp+28h+arg_0], 2
0x180094115  jnz     short loc_18009414F
0x180094117  lea     rdx, aSetprotectedpo; "SetProtectedPolicy"
0x18009411e  mov     [rsp+28h+arg_0], 1
0x180094127  mov     rcx, rbx; hModule
0x18009412a  call    cs:__imp_GetProcAddress
0x180094131  nop     dword ptr [rax+rax+00h]
0x180094136  test    rax, rax
0x180094139  jz      short loc_18009414F
0x18009413b  mov     rdx, [rsp+28h+arg_0]
0x180094140  lea     rcx, PPID_ProhibitUnsafeExtensions
0x180094147  xor     r8d, r8d
0x18009414a  call    rax
0x18009414c  nop     dword ptr [rax]
0x18009414f  mov     cs:?g_fUnsafeExtensionPolicySuppressed@@3_NA, 1; bool g_fUnsafeExtensionPolicySuppressed
0x180094156  add     rsp, 20h
0x18009415a  pop     rbx
0x18009415b  retn
```
