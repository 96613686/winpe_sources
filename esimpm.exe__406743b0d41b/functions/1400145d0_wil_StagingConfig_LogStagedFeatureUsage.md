# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x1400145d0`
- end: `0x140014648`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x1400145d0`
- `0x14003e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001461b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001461b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400145ff`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400145ff`

## string_xrefs

- `0x1400145f8`: `kernelbase.dll`

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
0x1400145d0  push    rbx
0x1400145d2  push    rbp
0x1400145d3  push    rsi
0x1400145d4  push    rdi
0x1400145d5  sub     rsp, 28h
0x1400145d9  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x1400145e0  mov     dil, r8b
0x1400145e3  mov     esi, edx
0x1400145e5  mov     ebp, ecx
0x1400145e7  test    rbx, rbx
0x1400145ea  jnz     short loc_140014630
0x1400145ec  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1400145f3  test    rax, rax
0x1400145f6  jnz     short loc_140014611
0x1400145f8  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1400145ff  call    cs:__imp_GetModuleHandleW
0x140014605  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x14001460c  test    rax, rax
0x14001460f  jz      short loc_140014624
0x140014611  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x140014618  mov     rcx, rax; hModule
0x14001461b  call    cs:__imp_GetProcAddress
0x140014621  mov     rbx, rax
0x140014624  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x14001462b  test    rbx, rbx
0x14001462e  jz      short loc_14001463F
0x140014630  mov     r8b, dil
0x140014633  mov     edx, esi
0x140014635  mov     ecx, ebp
0x140014637  mov     rax, rbx
0x14001463a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001463f  add     rsp, 28h
0x140014643  pop     rdi
0x140014644  pop     rsi
0x140014645  pop     rbp
0x140014646  pop     rbx
0x140014647  retn
```
