# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x18000aa90`
- end: `0x18000ab08`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x18000aa90`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000aabf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000aabf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000aadb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000aadb`

## string_xrefs

- `0x18000aab8`: `kernelbase.dll`

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
0x18000aa90  push    rbx
0x18000aa92  push    rbp
0x18000aa93  push    rsi
0x18000aa94  push    rdi
0x18000aa95  sub     rsp, 28h
0x18000aa99  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x18000aaa0  mov     dil, r8b
0x18000aaa3  mov     esi, edx
0x18000aaa5  mov     ebp, ecx
0x18000aaa7  test    rbx, rbx
0x18000aaaa  jnz     short loc_18000AAF0
0x18000aaac  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000aab3  test    rax, rax
0x18000aab6  jnz     short loc_18000AAD1
0x18000aab8  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000aabf  call    cs:__imp_GetModuleHandleW
0x18000aac5  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000aacc  test    rax, rax
0x18000aacf  jz      short loc_18000AAE4
0x18000aad1  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x18000aad8  mov     rcx, rax; hModule
0x18000aadb  call    cs:__imp_GetProcAddress
0x18000aae1  mov     rbx, rax
0x18000aae4  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x18000aaeb  test    rbx, rbx
0x18000aaee  jz      short loc_18000AAFF
0x18000aaf0  mov     r8b, dil
0x18000aaf3  mov     edx, esi
0x18000aaf5  mov     ecx, ebp
0x18000aaf7  mov     rax, rbx
0x18000aafa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aaff  add     rsp, 28h
0x18000ab03  pop     rdi
0x18000ab04  pop     rsi
0x18000ab05  pop     rbp
0x18000ab06  pop     rbx
0x18000ab07  retn
```
