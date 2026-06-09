# wil_StagingConfig_LogStagedFeatureUsage(x,x,x)

- ea: `0x1000a2f0`
- end: `0x1000a34d`
- name: `_wil_StagingConfig_LogStagedFeatureUsage@12`
- size: `93`
- prototype: `int __stdcall(void *, unsigned int, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x1000a2f0`
- `0x1000eb60`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1000a323`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1000a323`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1000a30e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1000a30e`

## string_xrefs

- `0x1000a309`: `kernelbase.dll`

## pseudocode

```c
HMODULE __stdcall wil_StagingConfig_LogStagedFeatureUsage(void *a1, unsigned int a2, int a3)
{
  int (__thiscall *v3)(_DWORD, _DWORD, _DWORD, _DWORD); // esi
  HMODULE result; // eax

  v3 = (int (__thiscall *)(_DWORD, _DWORD, _DWORD, _DWORD))g_wil_details_pfnLogStagedFeatureUsage;
  if ( g_wil_details_pfnLogStagedFeatureUsage )
    return (HMODULE)v3(v3, a1, a2, a3);
  result = `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle;
  if ( `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle
    || (result = GetModuleHandleW(L"kernelbase.dll"),
        (`wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle = result) != 0) )
  {
    result = (HMODULE)GetProcAddress(result, "LogStagedFeatureUsage");
    v3 = (int (__thiscall *)(_DWORD, _DWORD, _DWORD, _DWORD))result;
  }
  g_wil_details_pfnLogStagedFeatureUsage = (int)v3;
  if ( v3 )
    return (HMODULE)v3(v3, a1, a2, a3);
  return result;
}

```

## disassembly

```asm
0x1000a2f0  mov     edi, edi
0x1000a2f2  push    ebp
0x1000a2f3  mov     ebp, esp
0x1000a2f5  push    esi
0x1000a2f6  mov     esi, _g_wil_details_pfnLogStagedFeatureUsage
0x1000a2fc  test    esi, esi
0x1000a2fe  jnz     short loc_1000A335
0x1000a300  mov     eax, ?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YGP6GHXZPBD@Z@4PAUHINSTANCE__@@A; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1000a305  test    eax, eax
0x1000a307  jnz     short loc_1000A31D
0x1000a309  push    offset aKernelbaseDll; "kernelbase.dll"
0x1000a30e  call    ds:__imp__GetModuleHandleW@4; GetModuleHandleW(x)
0x1000a314  mov     ?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YGP6GHXZPBD@Z@4PAUHINSTANCE__@@A, eax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1000a319  test    eax, eax
0x1000a31b  jz      short loc_1000A32B
0x1000a31d  push    offset aLogstagedfeatu; "LogStagedFeatureUsage"
0x1000a322  push    eax; hModule
0x1000a323  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x1000a329  mov     esi, eax
0x1000a32b  mov     _g_wil_details_pfnLogStagedFeatureUsage, esi
0x1000a331  test    esi, esi
0x1000a333  jz      short loc_1000A348
0x1000a335  push    [ebp+arg_8]
0x1000a338  mov     ecx, esi
0x1000a33a  push    [ebp+arg_4]; unsigned int
0x1000a33d  push    [ebp+arg_0]; void *
0x1000a340  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1000a346  call    esi ; _g_wil_details_pfnLogStagedFeatureUsage
0x1000a348  pop     esi
0x1000a349  pop     ebp
0x1000a34a  retn    0Ch
```
