# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x14000e100`
- end: `0x14000e185`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `133`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x14000e100`
- `0x140069010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000e151`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000e151`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000e12f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000e12f`

## string_xrefs

- `0x14000e128`: `kernelbase.dll`

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
0x14000e100  push    rbx
0x14000e102  push    rbp
0x14000e103  push    rsi
0x14000e104  push    rdi
0x14000e105  sub     rsp, 28h
0x14000e109  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x14000e110  mov     dil, r8b
0x14000e113  mov     esi, edx
0x14000e115  mov     ebp, ecx
0x14000e117  test    rbx, rbx
0x14000e11a  jnz     short loc_14000E16C
0x14000e11c  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x14000e123  test    rax, rax
0x14000e126  jnz     short loc_14000E147
0x14000e128  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000e12f  call    cs:__imp_GetModuleHandleW
0x14000e136  nop     dword ptr [rax+rax+00h]
0x14000e13b  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x14000e142  test    rax, rax
0x14000e145  jz      short loc_14000E160
0x14000e147  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x14000e14e  mov     rcx, rax; hModule
0x14000e151  call    cs:__imp_GetProcAddress
0x14000e158  nop     dword ptr [rax+rax+00h]
0x14000e15d  mov     rbx, rax
0x14000e160  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x14000e167  test    rbx, rbx
0x14000e16a  jz      short loc_14000E17B
0x14000e16c  mov     r8b, dil
0x14000e16f  mov     edx, esi
0x14000e171  mov     ecx, ebp
0x14000e173  mov     rax, rbx
0x14000e176  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e17b  add     rsp, 28h
0x14000e17f  pop     rdi
0x14000e180  pop     rsi
0x14000e181  pop     rbp
0x14000e182  pop     rbx
0x14000e183  retn
```
