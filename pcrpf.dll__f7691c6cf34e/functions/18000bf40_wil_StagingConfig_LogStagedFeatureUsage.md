# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x18000bf40`
- end: `0x18000bfc5`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `133`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x18000bf40`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000bf91`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000bf91`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000bf6f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000bf6f`

## string_xrefs

- `0x18000bf68`: `kernelbase.dll`

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
0x18000bf40  push    rbx
0x18000bf42  push    rbp
0x18000bf43  push    rsi
0x18000bf44  push    rdi
0x18000bf45  sub     rsp, 28h
0x18000bf49  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x18000bf50  mov     dil, r8b
0x18000bf53  mov     esi, edx
0x18000bf55  mov     ebp, ecx
0x18000bf57  test    rbx, rbx
0x18000bf5a  jnz     short loc_18000BFAC
0x18000bf5c  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000bf63  test    rax, rax
0x18000bf66  jnz     short loc_18000BF87
0x18000bf68  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000bf6f  call    cs:__imp_GetModuleHandleW
0x18000bf76  nop     dword ptr [rax+rax+00h]
0x18000bf7b  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000bf82  test    rax, rax
0x18000bf85  jz      short loc_18000BFA0
0x18000bf87  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x18000bf8e  mov     rcx, rax; hModule
0x18000bf91  call    cs:__imp_GetProcAddress
0x18000bf98  nop     dword ptr [rax+rax+00h]
0x18000bf9d  mov     rbx, rax
0x18000bfa0  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x18000bfa7  test    rbx, rbx
0x18000bfaa  jz      short loc_18000BFBB
0x18000bfac  mov     r8b, dil
0x18000bfaf  mov     edx, esi
0x18000bfb1  mov     ecx, ebp
0x18000bfb3  mov     rax, rbx
0x18000bfb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfbb  add     rsp, 28h
0x18000bfbf  pop     rdi
0x18000bfc0  pop     rsi
0x18000bfc1  pop     rbp
0x18000bfc2  pop     rbx
0x18000bfc3  retn
```
