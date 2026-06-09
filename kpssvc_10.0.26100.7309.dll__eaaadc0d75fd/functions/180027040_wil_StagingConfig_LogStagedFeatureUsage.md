# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x180027040`
- end: `0x1800270dc`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `156`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x180027040`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002709c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002709c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002707a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002707a`

## string_xrefs

- `0x180027073`: `kernelbase.dll`

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
0x180027040  mov     [rsp+arg_0], rbx
0x180027045  mov     [rsp+arg_8], rbp
0x18002704a  mov     [rsp+arg_10], rsi
0x18002704f  push    rdi
0x180027050  sub     rsp, 20h
0x180027054  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x18002705b  mov     dil, r8b
0x18002705e  mov     esi, edx
0x180027060  mov     ebp, ecx
0x180027062  test    rbx, rbx
0x180027065  jnz     short loc_1800270B7
0x180027067  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18002706e  test    rax, rax
0x180027071  jnz     short loc_180027092
0x180027073  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18002707a  call    cs:__imp_GetModuleHandleW
0x180027081  nop     dword ptr [rax+rax+00h]
0x180027086  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18002708d  test    rax, rax
0x180027090  jz      short loc_1800270AB
0x180027092  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x180027099  mov     rcx, rax; hModule
0x18002709c  call    cs:__imp_GetProcAddress
0x1800270a3  nop     dword ptr [rax+rax+00h]
0x1800270a8  mov     rbx, rax
0x1800270ab  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x1800270b2  test    rbx, rbx
0x1800270b5  jz      short loc_1800270C6
0x1800270b7  mov     r8b, dil
0x1800270ba  mov     edx, esi
0x1800270bc  mov     ecx, ebp
0x1800270be  mov     rax, rbx
0x1800270c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800270c6  mov     rbx, [rsp+28h+arg_0]
0x1800270cb  mov     rbp, [rsp+28h+arg_8]
0x1800270d0  mov     rsi, [rsp+28h+arg_10]
0x1800270d5  add     rsp, 20h
0x1800270d9  pop     rdi
0x1800270da  retn
```
