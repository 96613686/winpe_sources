# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x18000a2a0`
- end: `0x18000a33c`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `156`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x18000a2a0`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a2da`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a2da`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a2fc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a2fc`

## string_xrefs

- `0x18000a2d3`: `kernelbase.dll`

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
0x18000a2a0  mov     [rsp+arg_0], rbx
0x18000a2a5  mov     [rsp+arg_8], rbp
0x18000a2aa  mov     [rsp+arg_10], rsi
0x18000a2af  push    rdi
0x18000a2b0  sub     rsp, 20h
0x18000a2b4  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x18000a2bb  mov     dil, r8b
0x18000a2be  mov     esi, edx
0x18000a2c0  mov     ebp, ecx
0x18000a2c2  test    rbx, rbx
0x18000a2c5  jnz     short loc_18000A317
0x18000a2c7  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000a2ce  test    rax, rax
0x18000a2d1  jnz     short loc_18000A2F2
0x18000a2d3  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000a2da  call    cs:__imp_GetModuleHandleW
0x18000a2e1  nop     dword ptr [rax+rax+00h]
0x18000a2e6  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000a2ed  test    rax, rax
0x18000a2f0  jz      short loc_18000A30B
0x18000a2f2  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x18000a2f9  mov     rcx, rax; hModule
0x18000a2fc  call    cs:__imp_GetProcAddress
0x18000a303  nop     dword ptr [rax+rax+00h]
0x18000a308  mov     rbx, rax
0x18000a30b  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x18000a312  test    rbx, rbx
0x18000a315  jz      short loc_18000A326
0x18000a317  mov     r8b, dil
0x18000a31a  mov     edx, esi
0x18000a31c  mov     ecx, ebp
0x18000a31e  mov     rax, rbx
0x18000a321  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a326  mov     rbx, [rsp+28h+arg_0]
0x18000a32b  mov     rbp, [rsp+28h+arg_8]
0x18000a330  mov     rsi, [rsp+28h+arg_10]
0x18000a335  add     rsp, 20h
0x18000a339  pop     rdi
0x18000a33a  retn
```
