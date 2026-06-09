# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x180009410`
- end: `0x180009488`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x180009410`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000943f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000943f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000945b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000945b`

## string_xrefs

- `0x180009438`: `kernelbase.dll`

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
0x180009410  push    rbx
0x180009412  push    rbp
0x180009413  push    rsi
0x180009414  push    rdi
0x180009415  sub     rsp, 28h
0x180009419  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x180009420  mov     dil, r8b
0x180009423  mov     esi, edx
0x180009425  mov     ebp, ecx
0x180009427  test    rbx, rbx
0x18000942a  jnz     short loc_180009470
0x18000942c  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180009433  test    rax, rax
0x180009436  jnz     short loc_180009451
0x180009438  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000943f  call    cs:__imp_GetModuleHandleW
0x180009445  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000944c  test    rax, rax
0x18000944f  jz      short loc_180009464
0x180009451  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x180009458  mov     rcx, rax; hModule
0x18000945b  call    cs:__imp_GetProcAddress
0x180009461  mov     rbx, rax
0x180009464  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x18000946b  test    rbx, rbx
0x18000946e  jz      short loc_18000947F
0x180009470  mov     r8b, dil
0x180009473  mov     edx, esi
0x180009475  mov     ecx, ebp
0x180009477  mov     rax, rbx
0x18000947a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000947f  add     rsp, 28h
0x180009483  pop     rdi
0x180009484  pop     rsi
0x180009485  pop     rbp
0x180009486  pop     rbx
0x180009487  retn
```
