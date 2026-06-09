# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x180011ae0`
- end: `0x180011b58`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x180011ae0`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011b2b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011b2b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180011b0f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180011b0f`

## string_xrefs

- `0x180011b08`: `kernelbase.dll`

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
0x180011ae0  push    rbx
0x180011ae2  push    rbp
0x180011ae3  push    rsi
0x180011ae4  push    rdi
0x180011ae5  sub     rsp, 28h
0x180011ae9  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x180011af0  mov     dil, r8b
0x180011af3  mov     esi, edx
0x180011af5  mov     ebp, ecx
0x180011af7  test    rbx, rbx
0x180011afa  jnz     short loc_180011B40
0x180011afc  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180011b03  test    rax, rax
0x180011b06  jnz     short loc_180011B21
0x180011b08  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180011b0f  call    cs:__imp_GetModuleHandleW
0x180011b15  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180011b1c  test    rax, rax
0x180011b1f  jz      short loc_180011B34
0x180011b21  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x180011b28  mov     rcx, rax; hModule
0x180011b2b  call    cs:__imp_GetProcAddress
0x180011b31  mov     rbx, rax
0x180011b34  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x180011b3b  test    rbx, rbx
0x180011b3e  jz      short loc_180011B4F
0x180011b40  mov     r8b, dil
0x180011b43  mov     edx, esi
0x180011b45  mov     ecx, ebp
0x180011b47  mov     rax, rbx
0x180011b4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b4f  add     rsp, 28h
0x180011b53  pop     rdi
0x180011b54  pop     rsi
0x180011b55  pop     rbp
0x180011b56  pop     rbx
0x180011b57  retn
```
