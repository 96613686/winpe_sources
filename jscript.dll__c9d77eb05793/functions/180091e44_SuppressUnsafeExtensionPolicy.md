# SuppressUnsafeExtensionPolicy

- ea: `0x180091e44`
- end: `0x180091ee3`
- name: `SuppressUnsafeExtensionPolicy`
- size: `159`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180051880`

## callees

- `0x180091e44`
- `0x180096010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180091e7f`
- `KERNEL32!GetProcAddress` at `0x180091eba`
- `KERNEL32!GetProcAddress` at `0x180091e7f`
- `KERNEL32!GetProcAddress` at `0x180091eba`
- `KERNEL32!GetModuleHandleW` at `0x180091e67`
- `KERNEL32!GetModuleHandleW` at `0x180091e67`

## string_xrefs

- `0x180091e60`: `api-ms-win-core-processthreads-l1-1-2.dll`

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
0x180091e44  mov     [rsp+arg_0], rcx
0x180091e49  push    rbx
0x180091e4a  sub     rsp, 20h
0x180091e4e  cmp     cs:?g_fUnsafeExtensionPolicySuppressed@@3_NA, 0; bool g_fUnsafeExtensionPolicySuppressed
0x180091e55  mov     [rsp+28h+arg_0], 0
0x180091e5e  jnz     short loc_180091EDD
0x180091e60  lea     rcx, ModuleName; "api-ms-win-core-processthreads-l1-1-2.d"...
0x180091e67  call    cs:__imp_GetModuleHandleW
0x180091e6d  mov     rbx, rax
0x180091e70  test    rax, rax
0x180091e73  jz      short loc_180091ED6
0x180091e75  lea     rdx, aQueryprotected; "QueryProtectedPolicy"
0x180091e7c  mov     rcx, rax; hModule
0x180091e7f  call    cs:__imp_GetProcAddress
0x180091e85  test    rax, rax
0x180091e88  jz      short loc_180091ED6
0x180091e8a  lea     rdx, [rsp+28h+arg_0]
0x180091e8f  lea     rcx, PPID_ProhibitUnsafeExtensions
0x180091e96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091e9b  test    eax, eax
0x180091e9d  jz      short loc_180091ED6
0x180091e9f  cmp     [rsp+28h+arg_0], 2
0x180091ea5  jnz     short loc_180091ED6
0x180091ea7  lea     rdx, aSetprotectedpo; "SetProtectedPolicy"
0x180091eae  mov     [rsp+28h+arg_0], 1
0x180091eb7  mov     rcx, rbx; hModule
0x180091eba  call    cs:__imp_GetProcAddress
0x180091ec0  test    rax, rax
0x180091ec3  jz      short loc_180091ED6
0x180091ec5  mov     rdx, [rsp+28h+arg_0]
0x180091eca  lea     rcx, PPID_ProhibitUnsafeExtensions
0x180091ed1  xor     r8d, r8d
0x180091ed4  call    rax
0x180091ed6  mov     cs:?g_fUnsafeExtensionPolicySuppressed@@3_NA, 1; bool g_fUnsafeExtensionPolicySuppressed
0x180091edd  add     rsp, 20h
0x180091ee1  pop     rbx
0x180091ee2  retn
```
