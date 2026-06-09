# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x180009660`
- end: `0x1800096d8`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x180009660`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000968f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000968f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800096ab`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800096ab`

## string_xrefs

- `0x180009688`: `kernelbase.dll`

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
0x180009660  push    rbx
0x180009662  push    rbp
0x180009663  push    rsi
0x180009664  push    rdi
0x180009665  sub     rsp, 28h
0x180009669  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x180009670  mov     dil, r8b
0x180009673  mov     esi, edx
0x180009675  mov     ebp, ecx
0x180009677  test    rbx, rbx
0x18000967a  jnz     short loc_1800096C0
0x18000967c  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180009683  test    rax, rax
0x180009686  jnz     short loc_1800096A1
0x180009688  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000968f  call    cs:__imp_GetModuleHandleW
0x180009695  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000969c  test    rax, rax
0x18000969f  jz      short loc_1800096B4
0x1800096a1  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x1800096a8  mov     rcx, rax; hModule
0x1800096ab  call    cs:__imp_GetProcAddress
0x1800096b1  mov     rbx, rax
0x1800096b4  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x1800096bb  test    rbx, rbx
0x1800096be  jz      short loc_1800096CF
0x1800096c0  mov     r8b, dil
0x1800096c3  mov     edx, esi
0x1800096c5  mov     ecx, ebp
0x1800096c7  mov     rax, rbx
0x1800096ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096cf  add     rsp, 28h
0x1800096d3  pop     rdi
0x1800096d4  pop     rsi
0x1800096d5  pop     rbp
0x1800096d6  pop     rbx
0x1800096d7  retn
```
