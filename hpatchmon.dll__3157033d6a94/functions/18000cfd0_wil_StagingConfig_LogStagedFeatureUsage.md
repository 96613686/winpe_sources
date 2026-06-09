# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x18000cfd0`
- end: `0x18000d048`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: `HMODULE __fastcall(unsigned int, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x18000cfd0`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000cfff`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000cfff`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d01b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d01b`

## string_xrefs

- `0x18000cff8`: `kernelbase.dll`

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
0x18000cfd0  push    rbx
0x18000cfd2  push    rbp
0x18000cfd3  push    rsi
0x18000cfd4  push    rdi
0x18000cfd5  sub     rsp, 28h
0x18000cfd9  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x18000cfe0  mov     dil, r8b
0x18000cfe3  mov     esi, edx
0x18000cfe5  mov     ebp, ecx
0x18000cfe7  test    rbx, rbx
0x18000cfea  jnz     short loc_18000D030
0x18000cfec  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000cff3  test    rax, rax
0x18000cff6  jnz     short loc_18000D011
0x18000cff8  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000cfff  call    cs:__imp_GetModuleHandleW
0x18000d005  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000d00c  test    rax, rax
0x18000d00f  jz      short loc_18000D024
0x18000d011  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x18000d018  mov     rcx, rax; hModule
0x18000d01b  call    cs:__imp_GetProcAddress
0x18000d021  mov     rbx, rax
0x18000d024  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x18000d02b  test    rbx, rbx
0x18000d02e  jz      short loc_18000D03F
0x18000d030  mov     r8b, dil
0x18000d033  mov     edx, esi
0x18000d035  mov     ecx, ebp
0x18000d037  mov     rax, rbx
0x18000d03a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d03f  add     rsp, 28h
0x18000d043  pop     rdi
0x18000d044  pop     rsi
0x18000d045  pop     rbp
0x18000d046  pop     rbx
0x18000d047  retn
```
