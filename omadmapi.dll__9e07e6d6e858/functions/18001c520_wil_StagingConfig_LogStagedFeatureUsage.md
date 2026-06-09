# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x18001c520`
- end: `0x18001c5a5`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `133`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x18001c520`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001c54f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001c54f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001c571`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001c571`

## string_xrefs

- `0x18001c548`: `kernelbase.dll`

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
0x18001c520  push    rbx
0x18001c522  push    rbp
0x18001c523  push    rsi
0x18001c524  push    rdi
0x18001c525  sub     rsp, 28h
0x18001c529  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x18001c530  mov     dil, r8b
0x18001c533  mov     esi, edx
0x18001c535  mov     ebp, ecx
0x18001c537  test    rbx, rbx
0x18001c53a  jnz     short loc_18001C58C
0x18001c53c  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18001c543  test    rax, rax
0x18001c546  jnz     short loc_18001C567
0x18001c548  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001c54f  call    cs:__imp_GetModuleHandleW
0x18001c556  nop     dword ptr [rax+rax+00h]
0x18001c55b  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18001c562  test    rax, rax
0x18001c565  jz      short loc_18001C580
0x18001c567  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x18001c56e  mov     rcx, rax; hModule
0x18001c571  call    cs:__imp_GetProcAddress
0x18001c578  nop     dword ptr [rax+rax+00h]
0x18001c57d  mov     rbx, rax
0x18001c580  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x18001c587  test    rbx, rbx
0x18001c58a  jz      short loc_18001C59B
0x18001c58c  mov     r8b, dil
0x18001c58f  mov     edx, esi
0x18001c591  mov     ecx, ebp
0x18001c593  mov     rax, rbx
0x18001c596  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c59b  add     rsp, 28h
0x18001c59f  pop     rdi
0x18001c5a0  pop     rsi
0x18001c5a1  pop     rbp
0x18001c5a2  pop     rbx
0x18001c5a3  retn
```
