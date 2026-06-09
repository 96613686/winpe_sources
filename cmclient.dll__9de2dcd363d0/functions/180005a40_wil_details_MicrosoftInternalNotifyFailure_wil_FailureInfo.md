# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180005a40`
- end: `0x180005b51`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `273`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005a40`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005af0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005af0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005ad4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005ad4`

## string_xrefs

- `0x180005acd`: `kernelbase.dll`

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
0x180005a40  mov     [rsp-8+arg_8], rbx
0x180005a45  mov     [rsp-8+arg_10], rdi
0x180005a4a  push    rbp
0x180005a4b  mov     rbp, rsp
0x180005a4e  sub     rsp, 50h
0x180005a52  mov     rbx, rcx
0x180005a55  mov     [rbp+var_2C], 0
0x180005a5c  mov     [rbp+var_1F], 0
0x180005a60  mov     [rbp+var_1C], 0
0x180005a67  xor     eax, eax
0x180005a69  mov     [rbp+var_16], ax
0x180005a6d  mov     eax, [rcx+8]
0x180005a70  mov     [rbp+var_30], eax
0x180005a73  mov     rax, [rcx+18h]
0x180005a77  mov     [rbp+var_28], rax
0x180005a7b  mov     al, [rcx]
0x180005a7d  mov     [rbp+var_20], al
0x180005a80  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x180005a87  mov     [rbp+var_1E], ax
0x180005a8b  movzx   eax, word ptr [rcx+40h]
0x180005a8f  mov     [rbp+var_18], ax
0x180005a93  mov     [rbp+var_14], 0
0x180005a9a  mov     rax, [rcx+38h]
0x180005a9e  mov     [rbp+var_10], rax
0x180005aa2  mov     rax, [rcx+80h]
0x180005aa9  mov     [rbp+var_8], rax
0x180005aad  mov     [rbp+arg_0], 0
0x180005ab5  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x180005abc  test    rdi, rdi
0x180005abf  jnz     short loc_180005B05
0x180005ac1  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180005ac8  test    rax, rax
0x180005acb  jnz     short loc_180005AE6
0x180005acd  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180005ad4  call    cs:__imp_GetModuleHandleW
0x180005ada  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180005ae1  test    rax, rax
0x180005ae4  jz      short loc_180005AF9
0x180005ae6  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x180005aed  mov     rcx, rax; hModule
0x180005af0  call    cs:__imp_GetProcAddress
0x180005af6  mov     rdi, rax
0x180005af9  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x180005b00  test    rdi, rdi
0x180005b03  jz      short loc_180005B18
0x180005b05  lea     r8, [rbp+arg_0]
0x180005b09  lea     rdx, [rbp+var_30]
0x180005b0d  xor     ecx, ecx
0x180005b0f  mov     rax, rdi
0x180005b12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b17  nop
0x180005b18  mov     eax, dword ptr [rbp+arg_0]
0x180005b1b  mov     [rbx+10h], eax
0x180005b1e  movzx   ecx, byte ptr [rbp+arg_0+4]
0x180005b22  sub     ecx, 1
0x180005b25  jz      short loc_180005B3D
0x180005b27  sub     ecx, 1
0x180005b2a  jz      short loc_180005B37
0x180005b2c  cmp     ecx, 1
0x180005b2f  jnz     short loc_180005B41
0x180005b31  or      dword ptr [rbx+4], 4
0x180005b35  jmp     short loc_180005B41
0x180005b37  or      dword ptr [rbx+4], 2
0x180005b3b  jmp     short loc_180005B41
0x180005b3d  or      dword ptr [rbx+4], 1
0x180005b41  mov     rbx, [rsp+50h+arg_8]
0x180005b46  mov     rdi, [rsp+50h+arg_10]
0x180005b4b  add     rsp, 50h
0x180005b4f  pop     rbp
0x180005b50  retn
```
