# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x18000b4f0`
- end: `0x18000b568`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x18000b4f0`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b51f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b51f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b53b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b53b`

## string_xrefs

- `0x18000b518`: `kernelbase.dll`

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
0x18000b4f0  push    rbx
0x18000b4f2  push    rbp
0x18000b4f3  push    rsi
0x18000b4f4  push    rdi
0x18000b4f5  sub     rsp, 28h
0x18000b4f9  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x18000b500  mov     dil, r8b
0x18000b503  mov     esi, edx
0x18000b505  mov     ebp, ecx
0x18000b507  test    rbx, rbx
0x18000b50a  jnz     short loc_18000B550
0x18000b50c  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000b513  test    rax, rax
0x18000b516  jnz     short loc_18000B531
0x18000b518  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000b51f  call    cs:__imp_GetModuleHandleW
0x18000b525  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000b52c  test    rax, rax
0x18000b52f  jz      short loc_18000B544
0x18000b531  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x18000b538  mov     rcx, rax; hModule
0x18000b53b  call    cs:__imp_GetProcAddress
0x18000b541  mov     rbx, rax
0x18000b544  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x18000b54b  test    rbx, rbx
0x18000b54e  jz      short loc_18000B55F
0x18000b550  mov     r8b, dil
0x18000b553  mov     edx, esi
0x18000b555  mov     ecx, ebp
0x18000b557  mov     rax, rbx
0x18000b55a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b55f  add     rsp, 28h
0x18000b563  pop     rdi
0x18000b564  pop     rsi
0x18000b565  pop     rbp
0x18000b566  pop     rbx
0x18000b567  retn
```
