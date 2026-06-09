# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x18000ae10`
- end: `0x18000ae88`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: `HMODULE __fastcall(unsigned int, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x18000ae10`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ae5b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ae5b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ae3f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ae3f`

## string_xrefs

- `0x18000ae38`: `kernelbase.dll`

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
0x18000ae10  push    rbx
0x18000ae12  push    rbp
0x18000ae13  push    rsi
0x18000ae14  push    rdi
0x18000ae15  sub     rsp, 28h
0x18000ae19  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x18000ae20  mov     dil, r8b
0x18000ae23  mov     esi, edx
0x18000ae25  mov     ebp, ecx
0x18000ae27  test    rbx, rbx
0x18000ae2a  jnz     short loc_18000AE70
0x18000ae2c  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000ae33  test    rax, rax
0x18000ae36  jnz     short loc_18000AE51
0x18000ae38  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000ae3f  call    cs:__imp_GetModuleHandleW
0x18000ae45  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000ae4c  test    rax, rax
0x18000ae4f  jz      short loc_18000AE64
0x18000ae51  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x18000ae58  mov     rcx, rax; hModule
0x18000ae5b  call    cs:__imp_GetProcAddress
0x18000ae61  mov     rbx, rax
0x18000ae64  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x18000ae6b  test    rbx, rbx
0x18000ae6e  jz      short loc_18000AE7F
0x18000ae70  mov     r8b, dil
0x18000ae73  mov     edx, esi
0x18000ae75  mov     ecx, ebp
0x18000ae77  mov     rax, rbx
0x18000ae7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae7f  add     rsp, 28h
0x18000ae83  pop     rdi
0x18000ae84  pop     rsi
0x18000ae85  pop     rbp
0x18000ae86  pop     rbx
0x18000ae87  retn
```
