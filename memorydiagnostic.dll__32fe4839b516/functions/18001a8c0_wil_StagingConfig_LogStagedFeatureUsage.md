# wil_StagingConfig_LogStagedFeatureUsage

- ea: `0x18001a8c0`
- end: `0x18001a95c`
- name: `wil_StagingConfig_LogStagedFeatureUsage`
- size: `156`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x18001a8c0`
- `0x180024010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18001a8fa`
- `KERNEL32!GetModuleHandleW` at `0x18001a8fa`
- `KERNEL32!GetProcAddress` at `0x18001a91c`
- `KERNEL32!GetProcAddress` at `0x18001a91c`

## string_xrefs

- `0x18001a8f3`: `kernelbase.dll`

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
0x18001a8c0  mov     [rsp+arg_0], rbx
0x18001a8c5  mov     [rsp+arg_8], rbp
0x18001a8ca  mov     [rsp+arg_10], rsi
0x18001a8cf  push    rdi
0x18001a8d0  sub     rsp, 20h
0x18001a8d4  mov     rbx, cs:g_wil_details_pfnLogStagedFeatureUsage
0x18001a8db  mov     dil, r8b
0x18001a8de  mov     esi, edx
0x18001a8e0  mov     ebp, ecx
0x18001a8e2  test    rbx, rbx
0x18001a8e5  jnz     short loc_18001A937
0x18001a8e7  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18001a8ee  test    rax, rax
0x18001a8f1  jnz     short loc_18001A912
0x18001a8f3  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001a8fa  call    cs:__imp_GetModuleHandleW
0x18001a901  nop     dword ptr [rax+rax+00h]
0x18001a906  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18001a90d  test    rax, rax
0x18001a910  jz      short loc_18001A92B
0x18001a912  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x18001a919  mov     rcx, rax; hModule
0x18001a91c  call    cs:__imp_GetProcAddress
0x18001a923  nop     dword ptr [rax+rax+00h]
0x18001a928  mov     rbx, rax
0x18001a92b  mov     cs:g_wil_details_pfnLogStagedFeatureUsage, rbx
0x18001a932  test    rbx, rbx
0x18001a935  jz      short loc_18001A946
0x18001a937  mov     r8b, dil
0x18001a93a  mov     edx, esi
0x18001a93c  mov     ecx, ebp
0x18001a93e  mov     rax, rbx
0x18001a941  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a946  mov     rbx, [rsp+28h+arg_0]
0x18001a94b  mov     rbp, [rsp+28h+arg_8]
0x18001a950  mov     rsi, [rsp+28h+arg_10]
0x18001a955  add     rsp, 20h
0x18001a959  pop     rdi
0x18001a95a  retn
```
