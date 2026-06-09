# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180007480`
- end: `0x180007591`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `273`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007480`
- `0x18000b010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180007530`
- `KERNEL32!GetProcAddress` at `0x180007530`
- `KERNEL32!GetModuleHandleW` at `0x180007514`
- `KERNEL32!GetModuleHandleW` at `0x180007514`

## string_xrefs

- `0x18000750d`: `kernelbase.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::MicrosoftInternalNotifyFailure(wil::details *this, struct wil::FailureInfo *a2)
{
  FARPROC ProcAddress; // rdi
  HMODULE ModuleHandleW; // rax
  _DWORD v5[2]; // [rsp+20h] [rbp-30h] BYREF
  __int64 v6; // [rsp+28h] [rbp-28h]
  char v7; // [rsp+30h] [rbp-20h]
  char v8; // [rsp+31h] [rbp-1Fh]
  __int16 v9; // [rsp+32h] [rbp-1Eh]
  int v10; // [rsp+34h] [rbp-1Ch]
  __int16 v11; // [rsp+38h] [rbp-18h]
  __int16 v12; // [rsp+3Ah] [rbp-16h]
  int v13; // [rsp+3Ch] [rbp-14h]
  __int64 v14; // [rsp+40h] [rbp-10h]
  __int64 v15; // [rsp+48h] [rbp-8h]
  __int64 v16; // [rsp+60h] [rbp+10h] BYREF

  v5[1] = 0;
  v8 = 0;
  v10 = 0;
  v12 = 0;
  v5[0] = *((_DWORD *)this + 2);
  v6 = *((_QWORD *)this + 3);
  v7 = *(_BYTE *)this;
  v9 = wil::g_moduleFailureReportFlags;
  v11 = *((_WORD *)this + 32);
  v13 = 0;
  v14 = *((_QWORD *)this + 7);
  v15 = *((_QWORD *)this + 16);
  v16 = 0;
  ProcAddress = (FARPROC)`wil::details::WilFailureNotifyWatchers'::`2'::s_pfnFailureNotifyWatchers;
  if ( `wil::details::WilFailureNotifyWatchers'::`2'::s_pfnFailureNotifyWatchers )
    goto LABEL_6;
  ModuleHandleW = `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle;
  if ( `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle
    || (ModuleHandleW = GetModuleHandleW(L"kernelbase.dll"),
        (`wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle = ModuleHandleW) != 0) )
  {
    ProcAddress = GetProcAddress(ModuleHandleW, "WilFailureNotifyWatchers");
  }
  `wil::details::WilFailureNotifyWatchers'::`2'::s_pfnFailureNotifyWatchers = (__int64)ProcAddress;
  if ( ProcAddress )
LABEL_6:
    ((void (__fastcall *)(_QWORD, _DWORD *, __int64 *))ProcAddress)(0, v5, &v16);
  *((_DWORD *)this + 4) = v16;
  switch ( BYTE4(v16) )
  {
    case 1u:
      *((_DWORD *)this + 1) |= 1u;
      break;
    case 2u:
      *((_DWORD *)this + 1) |= 2u;
      break;
    case 3u:
      *((_DWORD *)this + 1) |= 4u;
      break;
  }
}

```

## disassembly

```asm
0x180007480  mov     [rsp-8+arg_8], rbx
0x180007485  mov     [rsp-8+arg_10], rdi
0x18000748a  push    rbp
0x18000748b  mov     rbp, rsp
0x18000748e  sub     rsp, 50h
0x180007492  mov     rbx, rcx
0x180007495  mov     [rbp+var_2C], 0
0x18000749c  mov     [rbp+var_1F], 0
0x1800074a0  mov     [rbp+var_1C], 0
0x1800074a7  xor     eax, eax
0x1800074a9  mov     [rbp+var_16], ax
0x1800074ad  mov     eax, [rcx+8]
0x1800074b0  mov     [rbp+var_30], eax
0x1800074b3  mov     rax, [rcx+18h]
0x1800074b7  mov     [rbp+var_28], rax
0x1800074bb  mov     al, [rcx]
0x1800074bd  mov     [rbp+var_20], al
0x1800074c0  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x1800074c7  mov     [rbp+var_1E], ax
0x1800074cb  movzx   eax, word ptr [rcx+40h]
0x1800074cf  mov     [rbp+var_18], ax
0x1800074d3  mov     [rbp+var_14], 0
0x1800074da  mov     rax, [rcx+38h]
0x1800074de  mov     [rbp+var_10], rax
0x1800074e2  mov     rax, [rcx+80h]
0x1800074e9  mov     [rbp+var_8], rax
0x1800074ed  mov     [rbp+arg_0], 0
0x1800074f5  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x1800074fc  test    rdi, rdi
0x1800074ff  jnz     short loc_180007545
0x180007501  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180007508  test    rax, rax
0x18000750b  jnz     short loc_180007526
0x18000750d  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180007514  call    cs:__imp_GetModuleHandleW
0x18000751a  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180007521  test    rax, rax
0x180007524  jz      short loc_180007539
0x180007526  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x18000752d  mov     rcx, rax; hModule
0x180007530  call    cs:__imp_GetProcAddress
0x180007536  mov     rdi, rax
0x180007539  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x180007540  test    rdi, rdi
0x180007543  jz      short loc_180007558
0x180007545  lea     r8, [rbp+arg_0]
0x180007549  lea     rdx, [rbp+var_30]
0x18000754d  xor     ecx, ecx
0x18000754f  mov     rax, rdi
0x180007552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007557  nop
0x180007558  mov     eax, dword ptr [rbp+arg_0]
0x18000755b  mov     [rbx+10h], eax
0x18000755e  movzx   ecx, byte ptr [rbp+arg_0+4]
0x180007562  sub     ecx, 1
0x180007565  jz      short loc_18000757D
0x180007567  sub     ecx, 1
0x18000756a  jz      short loc_180007577
0x18000756c  cmp     ecx, 1
0x18000756f  jnz     short loc_180007581
0x180007571  or      dword ptr [rbx+4], 4
0x180007575  jmp     short loc_180007581
0x180007577  or      dword ptr [rbx+4], 2
0x18000757b  jmp     short loc_180007581
0x18000757d  or      dword ptr [rbx+4], 1
0x180007581  mov     rbx, [rsp+50h+arg_8]
0x180007586  mov     rdi, [rsp+50h+arg_10]
0x18000758b  add     rsp, 50h
0x18000758f  pop     rbp
0x180007590  retn
```
