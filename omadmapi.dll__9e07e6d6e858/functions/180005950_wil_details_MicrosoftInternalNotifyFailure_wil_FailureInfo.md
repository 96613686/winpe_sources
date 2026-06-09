# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180005950`
- end: `0x180005a6e`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `286`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005950`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800059e4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800059e4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005a06`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005a06`

## string_xrefs

- `0x1800059dd`: `kernelbase.dll`

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
0x180005950  mov     [rsp-8+arg_8], rbx
0x180005955  mov     [rsp-8+arg_10], rdi
0x18000595a  push    rbp
0x18000595b  mov     rbp, rsp
0x18000595e  sub     rsp, 50h
0x180005962  mov     rbx, rcx
0x180005965  mov     [rbp+var_2C], 0
0x18000596c  mov     [rbp+var_1F], 0
0x180005970  mov     [rbp+var_1C], 0
0x180005977  xor     eax, eax
0x180005979  mov     [rbp+var_16], ax
0x18000597d  mov     eax, [rcx+8]
0x180005980  mov     [rbp+var_30], eax
0x180005983  mov     rax, [rcx+18h]
0x180005987  mov     [rbp+var_28], rax
0x18000598b  mov     al, [rcx]
0x18000598d  mov     [rbp+var_20], al
0x180005990  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x180005997  mov     [rbp+var_1E], ax
0x18000599b  movzx   eax, word ptr [rcx+40h]
0x18000599f  mov     [rbp+var_18], ax
0x1800059a3  mov     [rbp+var_14], 0
0x1800059aa  mov     rax, [rcx+38h]
0x1800059ae  mov     [rbp+var_10], rax
0x1800059b2  mov     rax, [rcx+80h]
0x1800059b9  mov     [rbp+var_8], rax
0x1800059bd  mov     [rbp+arg_0], 0
0x1800059c5  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x1800059cc  test    rdi, rdi
0x1800059cf  jnz     short loc_180005A21
0x1800059d1  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800059d8  test    rax, rax
0x1800059db  jnz     short loc_1800059FC
0x1800059dd  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800059e4  call    cs:__imp_GetModuleHandleW
0x1800059eb  nop     dword ptr [rax+rax+00h]
0x1800059f0  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800059f7  test    rax, rax
0x1800059fa  jz      short loc_180005A15
0x1800059fc  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x180005a03  mov     rcx, rax; hModule
0x180005a06  call    cs:__imp_GetProcAddress
0x180005a0d  nop     dword ptr [rax+rax+00h]
0x180005a12  mov     rdi, rax
0x180005a15  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x180005a1c  test    rdi, rdi
0x180005a1f  jz      short loc_180005A34
0x180005a21  lea     r8, [rbp+arg_0]
0x180005a25  lea     rdx, [rbp+var_30]
0x180005a29  xor     ecx, ecx
0x180005a2b  mov     rax, rdi
0x180005a2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a33  nop
0x180005a34  mov     eax, dword ptr [rbp+arg_0]
0x180005a37  mov     [rbx+10h], eax
0x180005a3a  movzx   ecx, byte ptr [rbp+arg_0+4]
0x180005a3e  sub     ecx, 1
0x180005a41  jz      short loc_180005A59
0x180005a43  sub     ecx, 1
0x180005a46  jz      short loc_180005A53
0x180005a48  cmp     ecx, 1
0x180005a4b  jnz     short loc_180005A5D
0x180005a4d  or      dword ptr [rbx+4], 4
0x180005a51  jmp     short loc_180005A5D
0x180005a53  or      dword ptr [rbx+4], 2
0x180005a57  jmp     short loc_180005A5D
0x180005a59  or      dword ptr [rbx+4], 1
0x180005a5d  mov     rbx, [rsp+50h+arg_8]
0x180005a62  mov     rdi, [rsp+50h+arg_10]
0x180005a67  add     rsp, 50h
0x180005a6b  pop     rbp
0x180005a6c  retn
```
