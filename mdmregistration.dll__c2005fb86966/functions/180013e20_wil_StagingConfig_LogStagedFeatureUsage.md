# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x180013e20`
- end: `0x180013ea5`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `133`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x180013e20`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180013e4f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180013e4f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013e71`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013e71`

## string_xrefs

- `0x180013e48`: `kernelbase.dll`

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
0x180013e20  push    rbx
0x180013e22  push    rbp
0x180013e23  push    rsi
0x180013e24  push    rdi
0x180013e25  sub     rsp, 28h
0x180013e29  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x180013e30  mov     dil, r8b
0x180013e33  mov     esi, edx
0x180013e35  mov     ebp, ecx
0x180013e37  test    rbx, rbx
0x180013e3a  jnz     short loc_180013E8C
0x180013e3c  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180013e43  test    rax, rax
0x180013e46  jnz     short loc_180013E67
0x180013e48  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180013e4f  call    cs:__imp_GetModuleHandleW
0x180013e56  nop     dword ptr [rax+rax+00h]
0x180013e5b  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180013e62  test    rax, rax
0x180013e65  jz      short loc_180013E80
0x180013e67  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x180013e6e  mov     rcx, rax; hModule
0x180013e71  call    cs:__imp_GetProcAddress
0x180013e78  nop     dword ptr [rax+rax+00h]
0x180013e7d  mov     rbx, rax
0x180013e80  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x180013e87  test    rbx, rbx
0x180013e8a  jz      short loc_180013E9B
0x180013e8c  mov     r8b, dil
0x180013e8f  mov     edx, esi
0x180013e91  mov     ecx, ebp
0x180013e93  mov     rax, rbx
0x180013e96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e9b  add     rsp, 28h
0x180013e9f  pop     rdi
0x180013ea0  pop     rsi
0x180013ea1  pop     rbp
0x180013ea2  pop     rbx
0x180013ea3  retn
```
