# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x18000cc80`
- end: `0x18000ccf8`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x18000cc80`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ccaf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ccaf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cccb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cccb`

## string_xrefs

- `0x18000cca8`: `kernelbase.dll`

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
0x18000cc80  push    rbx
0x18000cc82  push    rbp
0x18000cc83  push    rsi
0x18000cc84  push    rdi
0x18000cc85  sub     rsp, 28h
0x18000cc89  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x18000cc90  mov     dil, r8b
0x18000cc93  mov     esi, edx
0x18000cc95  mov     ebp, ecx
0x18000cc97  test    rbx, rbx
0x18000cc9a  jnz     short loc_18000CCE0
0x18000cc9c  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000cca3  test    rax, rax
0x18000cca6  jnz     short loc_18000CCC1
0x18000cca8  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000ccaf  call    cs:__imp_GetModuleHandleW
0x18000ccb5  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000ccbc  test    rax, rax
0x18000ccbf  jz      short loc_18000CCD4
0x18000ccc1  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x18000ccc8  mov     rcx, rax; hModule
0x18000cccb  call    cs:__imp_GetProcAddress
0x18000ccd1  mov     rbx, rax
0x18000ccd4  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x18000ccdb  test    rbx, rbx
0x18000ccde  jz      short loc_18000CCEF
0x18000cce0  mov     r8b, dil
0x18000cce3  mov     edx, esi
0x18000cce5  mov     ecx, ebp
0x18000cce7  mov     rax, rbx
0x18000ccea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ccef  add     rsp, 28h
0x18000ccf3  pop     rdi
0x18000ccf4  pop     rsi
0x18000ccf5  pop     rbp
0x18000ccf6  pop     rbx
0x18000ccf7  retn
```
