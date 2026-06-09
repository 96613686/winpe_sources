# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x180012500`
- end: `0x180012578`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x180012500`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001252f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001252f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001254b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001254b`

## string_xrefs

- `0x180012528`: `kernelbase.dll`

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
0x180012500  push    rbx
0x180012502  push    rbp
0x180012503  push    rsi
0x180012504  push    rdi
0x180012505  sub     rsp, 28h
0x180012509  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x180012510  mov     dil, r8b
0x180012513  mov     esi, edx
0x180012515  mov     ebp, ecx
0x180012517  test    rbx, rbx
0x18001251a  jnz     short loc_180012560
0x18001251c  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180012523  test    rax, rax
0x180012526  jnz     short loc_180012541
0x180012528  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001252f  call    cs:__imp_GetModuleHandleW
0x180012535  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18001253c  test    rax, rax
0x18001253f  jz      short loc_180012554
0x180012541  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x180012548  mov     rcx, rax; hModule
0x18001254b  call    cs:__imp_GetProcAddress
0x180012551  mov     rbx, rax
0x180012554  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x18001255b  test    rbx, rbx
0x18001255e  jz      short loc_18001256F
0x180012560  mov     r8b, dil
0x180012563  mov     edx, esi
0x180012565  mov     ecx, ebp
0x180012567  mov     rax, rbx
0x18001256a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001256f  add     rsp, 28h
0x180012573  pop     rdi
0x180012574  pop     rsi
0x180012575  pop     rbp
0x180012576  pop     rbx
0x180012577  retn
```
