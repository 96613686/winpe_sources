# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x18000ae90`
- end: `0x18000af08`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x18000ae90`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000aedb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000aedb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000aebf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000aebf`

## string_xrefs

- `0x18000aeb8`: `kernelbase.dll`

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
0x18000ae90  push    rbx
0x18000ae92  push    rbp
0x18000ae93  push    rsi
0x18000ae94  push    rdi
0x18000ae95  sub     rsp, 28h
0x18000ae99  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x18000aea0  mov     dil, r8b
0x18000aea3  mov     esi, edx
0x18000aea5  mov     ebp, ecx
0x18000aea7  test    rbx, rbx
0x18000aeaa  jnz     short loc_18000AEF0
0x18000aeac  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000aeb3  test    rax, rax
0x18000aeb6  jnz     short loc_18000AED1
0x18000aeb8  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000aebf  call    cs:__imp_GetModuleHandleW
0x18000aec5  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000aecc  test    rax, rax
0x18000aecf  jz      short loc_18000AEE4
0x18000aed1  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x18000aed8  mov     rcx, rax; hModule
0x18000aedb  call    cs:__imp_GetProcAddress
0x18000aee1  mov     rbx, rax
0x18000aee4  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x18000aeeb  test    rbx, rbx
0x18000aeee  jz      short loc_18000AEFF
0x18000aef0  mov     r8b, dil
0x18000aef3  mov     edx, esi
0x18000aef5  mov     ecx, ebp
0x18000aef7  mov     rax, rbx
0x18000aefa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aeff  add     rsp, 28h
0x18000af03  pop     rdi
0x18000af04  pop     rsi
0x18000af05  pop     rbp
0x18000af06  pop     rbx
0x18000af07  retn
```
