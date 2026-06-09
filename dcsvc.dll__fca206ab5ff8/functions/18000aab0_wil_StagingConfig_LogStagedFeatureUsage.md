# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x18000aab0`
- end: `0x18000ab28`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: `HMODULE __fastcall(unsigned int, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x18000aab0`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000aafb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000aafb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000aadf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000aadf`

## string_xrefs

- `0x18000aad8`: `kernelbase.dll`

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
0x18000aab0  push    rbx
0x18000aab2  push    rbp
0x18000aab3  push    rsi
0x18000aab4  push    rdi
0x18000aab5  sub     rsp, 28h
0x18000aab9  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x18000aac0  mov     dil, r8b
0x18000aac3  mov     esi, edx
0x18000aac5  mov     ebp, ecx
0x18000aac7  test    rbx, rbx
0x18000aaca  jnz     short loc_18000AB10
0x18000aacc  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000aad3  test    rax, rax
0x18000aad6  jnz     short loc_18000AAF1
0x18000aad8  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000aadf  call    cs:__imp_GetModuleHandleW
0x18000aae5  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000aaec  test    rax, rax
0x18000aaef  jz      short loc_18000AB04
0x18000aaf1  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x18000aaf8  mov     rcx, rax; hModule
0x18000aafb  call    cs:__imp_GetProcAddress
0x18000ab01  mov     rbx, rax
0x18000ab04  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x18000ab0b  test    rbx, rbx
0x18000ab0e  jz      short loc_18000AB1F
0x18000ab10  mov     r8b, dil
0x18000ab13  mov     edx, esi
0x18000ab15  mov     ecx, ebp
0x18000ab17  mov     rax, rbx
0x18000ab1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab1f  add     rsp, 28h
0x18000ab23  pop     rdi
0x18000ab24  pop     rsi
0x18000ab25  pop     rbp
0x18000ab26  pop     rbx
0x18000ab27  retn
```
