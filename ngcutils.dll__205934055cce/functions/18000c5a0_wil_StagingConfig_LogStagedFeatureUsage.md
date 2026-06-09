# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x18000c5a0`
- end: `0x18000c618`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x18000c5a0`
- `0x180061010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c5cf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c5cf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c5eb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c5eb`

## string_xrefs

- `0x18000c5c8`: `kernelbase.dll`

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
0x18000c5a0  push    rbx
0x18000c5a2  push    rbp
0x18000c5a3  push    rsi
0x18000c5a4  push    rdi
0x18000c5a5  sub     rsp, 28h
0x18000c5a9  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x18000c5b0  mov     dil, r8b
0x18000c5b3  mov     esi, edx
0x18000c5b5  mov     ebp, ecx
0x18000c5b7  test    rbx, rbx
0x18000c5ba  jnz     short loc_18000C600
0x18000c5bc  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000c5c3  test    rax, rax
0x18000c5c6  jnz     short loc_18000C5E1
0x18000c5c8  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000c5cf  call    cs:__imp_GetModuleHandleW
0x18000c5d5  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000c5dc  test    rax, rax
0x18000c5df  jz      short loc_18000C5F4
0x18000c5e1  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x18000c5e8  mov     rcx, rax; hModule
0x18000c5eb  call    cs:__imp_GetProcAddress
0x18000c5f1  mov     rbx, rax
0x18000c5f4  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x18000c5fb  test    rbx, rbx
0x18000c5fe  jz      short loc_18000C60F
0x18000c600  mov     r8b, dil
0x18000c603  mov     edx, esi
0x18000c605  mov     ecx, ebp
0x18000c607  mov     rax, rbx
0x18000c60a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c60f  add     rsp, 28h
0x18000c613  pop     rdi
0x18000c614  pop     rsi
0x18000c615  pop     rbp
0x18000c616  pop     rbx
0x18000c617  retn
```
