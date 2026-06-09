# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x18002a1f0`
- end: `0x18002a26a`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `122`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x18002a1f0`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a23c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a23c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002a220`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002a220`

## string_xrefs

- `0x18002a219`: `kernelbase.dll`

## pseudocode

```c
HMODULE __fastcall wil_StagingConfig_LogStagedFeatureUsage(unsigned int a1, unsigned int a2, unsigned __int8 a3)
{
  __int64 (__fastcall *v3)(_QWORD, _QWORD, _QWORD); // rbx
  HMODULE result; // rax

  v3 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))g_wil_details_pfnLogStagedFeatureUsage;
  if ( g_wil_details_pfnLogStagedFeatureUsage )
    return (HMODULE)v3(a1, a2, a3);
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
    return (HMODULE)v3(a1, a2, a3);
  return result;
}

```

## disassembly

```asm
0x18002a1f0  push    rbx
0x18002a1f2  push    rbp
0x18002a1f3  push    rsi
0x18002a1f4  push    rdi
0x18002a1f5  sub     rsp, 28h
0x18002a1f9  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x18002a200  movzx   edi, r8b
0x18002a204  mov     esi, edx
0x18002a206  mov     ebp, ecx
0x18002a208  test    rbx, rbx
0x18002a20b  jnz     short loc_18002A251
0x18002a20d  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18002a214  test    rax, rax
0x18002a217  jnz     short loc_18002A232
0x18002a219  lea     rcx, ModuleName; "kernelbase.dll"
0x18002a220  call    cs:__imp_GetModuleHandleW
0x18002a226  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18002a22d  test    rax, rax
0x18002a230  jz      short loc_18002A245
0x18002a232  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x18002a239  mov     rcx, rax; hModule
0x18002a23c  call    cs:__imp_GetProcAddress
0x18002a242  mov     rbx, rax
0x18002a245  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x18002a24c  test    rbx, rbx
0x18002a24f  jz      short loc_18002A261
0x18002a251  movzx   r8d, dil
0x18002a255  mov     edx, esi
0x18002a257  mov     ecx, ebp
0x18002a259  mov     rax, rbx
0x18002a25c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a261  add     rsp, 28h
0x18002a265  pop     rdi
0x18002a266  pop     rsi
0x18002a267  pop     rbp
0x18002a268  pop     rbx
0x18002a269  retn
```
