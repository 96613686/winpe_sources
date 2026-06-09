# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x180012940`
- end: `0x1800129b8`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `120`
- prototype: `HMODULE __fastcall(unsigned int, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x180012940`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001296f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001296f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001298b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001298b`

## string_xrefs

- `0x180012968`: `kernelbase.dll`

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
0x180012940  push    rbx
0x180012942  push    rbp
0x180012943  push    rsi
0x180012944  push    rdi
0x180012945  sub     rsp, 28h
0x180012949  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x180012950  mov     dil, r8b
0x180012953  mov     esi, edx
0x180012955  mov     ebp, ecx
0x180012957  test    rbx, rbx
0x18001295a  jnz     short loc_1800129A0
0x18001295c  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180012963  test    rax, rax
0x180012966  jnz     short loc_180012981
0x180012968  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001296f  call    cs:__imp_GetModuleHandleW
0x180012975  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18001297c  test    rax, rax
0x18001297f  jz      short loc_180012994
0x180012981  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x180012988  mov     rcx, rax; hModule
0x18001298b  call    cs:__imp_GetProcAddress
0x180012991  mov     rbx, rax
0x180012994  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x18001299b  test    rbx, rbx
0x18001299e  jz      short loc_1800129AF
0x1800129a0  mov     r8b, dil
0x1800129a3  mov     edx, esi
0x1800129a5  mov     ecx, ebp
0x1800129a7  mov     rax, rbx
0x1800129aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800129af  add     rsp, 28h
0x1800129b3  pop     rdi
0x1800129b4  pop     rsi
0x1800129b5  pop     rbp
0x1800129b6  pop     rbx
0x1800129b7  retn
```
