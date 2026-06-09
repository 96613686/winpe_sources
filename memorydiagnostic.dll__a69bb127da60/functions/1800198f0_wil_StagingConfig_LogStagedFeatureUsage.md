# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x1800198f0`
- end: `0x180019968`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: `HMODULE __fastcall(unsigned int, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x1800198f0`
- `0x180023010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18001991f`
- `KERNEL32!GetModuleHandleW` at `0x18001991f`
- `KERNEL32!GetProcAddress` at `0x18001993b`
- `KERNEL32!GetProcAddress` at `0x18001993b`

## string_xrefs

- `0x180019918`: `kernelbase.dll`

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
0x1800198f0  push    rbx
0x1800198f2  push    rbp
0x1800198f3  push    rsi
0x1800198f4  push    rdi
0x1800198f5  sub     rsp, 28h
0x1800198f9  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x180019900  mov     dil, r8b
0x180019903  mov     esi, edx
0x180019905  mov     ebp, ecx
0x180019907  test    rbx, rbx
0x18001990a  jnz     short loc_180019950
0x18001990c  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180019913  test    rax, rax
0x180019916  jnz     short loc_180019931
0x180019918  lea     rcx, ModuleName; "kernelbase.dll"
0x18001991f  call    cs:__imp_GetModuleHandleW
0x180019925  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18001992c  test    rax, rax
0x18001992f  jz      short loc_180019944
0x180019931  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x180019938  mov     rcx, rax; hModule
0x18001993b  call    cs:__imp_GetProcAddress
0x180019941  mov     rbx, rax
0x180019944  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x18001994b  test    rbx, rbx
0x18001994e  jz      short loc_18001995F
0x180019950  mov     r8b, dil
0x180019953  mov     edx, esi
0x180019955  mov     ecx, ebp
0x180019957  mov     rax, rbx
0x18001995a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001995f  add     rsp, 28h
0x180019963  pop     rdi
0x180019964  pop     rsi
0x180019965  pop     rbp
0x180019966  pop     rbx
0x180019967  retn
```
