# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180006d10`
- end: `0x180006e21`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `273`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006d10`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006da4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006da4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006dc0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006dc0`

## string_xrefs

- `0x180006d9d`: `kernelbase.dll`

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
0x180006d10  mov     [rsp-8+arg_8], rbx
0x180006d15  mov     [rsp-8+arg_10], rdi
0x180006d1a  push    rbp
0x180006d1b  mov     rbp, rsp
0x180006d1e  sub     rsp, 50h
0x180006d22  mov     rbx, rcx
0x180006d25  mov     [rbp+var_2C], 0
0x180006d2c  mov     [rbp+var_1F], 0
0x180006d30  mov     [rbp+var_1C], 0
0x180006d37  xor     eax, eax
0x180006d39  mov     [rbp+var_16], ax
0x180006d3d  mov     eax, [rcx+8]
0x180006d40  mov     [rbp+var_30], eax
0x180006d43  mov     rax, [rcx+18h]
0x180006d47  mov     [rbp+var_28], rax
0x180006d4b  mov     al, [rcx]
0x180006d4d  mov     [rbp+var_20], al
0x180006d50  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x180006d57  mov     [rbp+var_1E], ax
0x180006d5b  movzx   eax, word ptr [rcx+40h]
0x180006d5f  mov     [rbp+var_18], ax
0x180006d63  mov     [rbp+var_14], 0
0x180006d6a  mov     rax, [rcx+38h]
0x180006d6e  mov     [rbp+var_10], rax
0x180006d72  mov     rax, [rcx+80h]
0x180006d79  mov     [rbp+var_8], rax
0x180006d7d  mov     [rbp+arg_0], 0
0x180006d85  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x180006d8c  test    rdi, rdi
0x180006d8f  jnz     short loc_180006DD5
0x180006d91  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180006d98  test    rax, rax
0x180006d9b  jnz     short loc_180006DB6
0x180006d9d  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180006da4  call    cs:__imp_GetModuleHandleW
0x180006daa  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180006db1  test    rax, rax
0x180006db4  jz      short loc_180006DC9
0x180006db6  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x180006dbd  mov     rcx, rax; hModule
0x180006dc0  call    cs:__imp_GetProcAddress
0x180006dc6  mov     rdi, rax
0x180006dc9  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x180006dd0  test    rdi, rdi
0x180006dd3  jz      short loc_180006DE8
0x180006dd5  lea     r8, [rbp+arg_0]
0x180006dd9  lea     rdx, [rbp+var_30]
0x180006ddd  xor     ecx, ecx
0x180006ddf  mov     rax, rdi
0x180006de2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006de7  nop
0x180006de8  mov     eax, dword ptr [rbp+arg_0]
0x180006deb  mov     [rbx+10h], eax
0x180006dee  movzx   ecx, byte ptr [rbp+arg_0+4]
0x180006df2  sub     ecx, 1
0x180006df5  jz      short loc_180006E0D
0x180006df7  sub     ecx, 1
0x180006dfa  jz      short loc_180006E07
0x180006dfc  cmp     ecx, 1
0x180006dff  jnz     short loc_180006E11
0x180006e01  or      dword ptr [rbx+4], 4
0x180006e05  jmp     short loc_180006E11
0x180006e07  or      dword ptr [rbx+4], 2
0x180006e0b  jmp     short loc_180006E11
0x180006e0d  or      dword ptr [rbx+4], 1
0x180006e11  mov     rbx, [rsp+50h+arg_8]
0x180006e16  mov     rdi, [rsp+50h+arg_10]
0x180006e1b  add     rsp, 50h
0x180006e1f  pop     rbp
0x180006e20  retn
```
