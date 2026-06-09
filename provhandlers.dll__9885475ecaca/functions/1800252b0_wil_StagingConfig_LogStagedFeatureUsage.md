# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x1800252b0`
- end: `0x180025328`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x1800252b0`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800252df`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800252df`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800252fb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800252fb`

## string_xrefs

- `0x1800252d8`: `kernelbase.dll`

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
0x1800252b0  push    rbx
0x1800252b2  push    rbp
0x1800252b3  push    rsi
0x1800252b4  push    rdi
0x1800252b5  sub     rsp, 28h
0x1800252b9  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x1800252c0  mov     dil, r8b
0x1800252c3  mov     esi, edx
0x1800252c5  mov     ebp, ecx
0x1800252c7  test    rbx, rbx
0x1800252ca  jnz     short loc_180025310
0x1800252cc  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800252d3  test    rax, rax
0x1800252d6  jnz     short loc_1800252F1
0x1800252d8  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800252df  call    cs:__imp_GetModuleHandleW
0x1800252e5  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800252ec  test    rax, rax
0x1800252ef  jz      short loc_180025304
0x1800252f1  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x1800252f8  mov     rcx, rax; hModule
0x1800252fb  call    cs:__imp_GetProcAddress
0x180025301  mov     rbx, rax
0x180025304  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x18002530b  test    rbx, rbx
0x18002530e  jz      short loc_18002531F
0x180025310  mov     r8b, dil
0x180025313  mov     edx, esi
0x180025315  mov     ecx, ebp
0x180025317  mov     rax, rbx
0x18002531a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002531f  add     rsp, 28h
0x180025323  pop     rdi
0x180025324  pop     rsi
0x180025325  pop     rbp
0x180025326  pop     rbx
0x180025327  retn
```
