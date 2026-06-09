# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x180022970`
- end: `0x1800229e8`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x180022970`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002299f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002299f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800229bb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800229bb`

## string_xrefs

- `0x180022998`: `kernelbase.dll`

## pseudocode

```c
HMODULE __fastcall wil_StagingConfig_LogStagedFeatureUsage(unsigned int a1, unsigned int a2, __int64 a3)
{
  __int64 (__fastcall *v3)(_QWORD, _QWORD, _QWORD); // rbx
  char v4; // di
  HMODULE result; // rax

  v3 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))g_wil_details_pfnLogStagedFeatureUsage;
  v4 = a3;
  if ( g_wil_details_pfnLogStagedFeatureUsage )
    goto LABEL_6;
  result = `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle;
  if ( `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle
    || (result = GetModuleHandleW(L"kernelbase.dll"),
        (`wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle = result) != 0) )
  {
    result = (HMODULE)GetProcAddress(result, "LogStagedFeatureUsage");
    v3 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))result;
  }
  g_wil_details_pfnLogStagedFeatureUsage = (__int64)v3;
  if ( v3 )
  {
LABEL_6:
    LOBYTE(a3) = v4;
    return (HMODULE)v3(a1, a2, a3);
  }
  return result;
}

```

## disassembly

```asm
0x180022970  push    rbx
0x180022972  push    rbp
0x180022973  push    rsi
0x180022974  push    rdi
0x180022975  sub     rsp, 28h
0x180022979  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x180022980  mov     dil, r8b
0x180022983  mov     esi, edx
0x180022985  mov     ebp, ecx
0x180022987  test    rbx, rbx
0x18002298a  jnz     short loc_1800229D0
0x18002298c  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180022993  test    rax, rax
0x180022996  jnz     short loc_1800229B1
0x180022998  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18002299f  call    cs:__imp_GetModuleHandleW
0x1800229a5  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800229ac  test    rax, rax
0x1800229af  jz      short loc_1800229C4
0x1800229b1  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x1800229b8  mov     rcx, rax; hModule
0x1800229bb  call    cs:__imp_GetProcAddress
0x1800229c1  mov     rbx, rax
0x1800229c4  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x1800229cb  test    rbx, rbx
0x1800229ce  jz      short loc_1800229DF
0x1800229d0  mov     r8b, dil
0x1800229d3  mov     edx, esi
0x1800229d5  mov     ecx, ebp
0x1800229d7  mov     rax, rbx
0x1800229da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800229df  add     rsp, 28h
0x1800229e3  pop     rdi
0x1800229e4  pop     rsi
0x1800229e5  pop     rbp
0x1800229e6  pop     rbx
0x1800229e7  retn
```
