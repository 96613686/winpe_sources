# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180005db0`
- end: `0x180005ec1`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `273`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005db0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005e60`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005e60`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005e44`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005e44`

## string_xrefs

- `0x180005e3d`: `kernelbase.dll`

## pseudocode

```c
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
0x180005db0  mov     [rsp-8+arg_8], rbx
0x180005db5  mov     [rsp-8+arg_10], rdi
0x180005dba  push    rbp
0x180005dbb  mov     rbp, rsp
0x180005dbe  sub     rsp, 50h
0x180005dc2  mov     rbx, rcx
0x180005dc5  mov     [rbp+var_2C], 0
0x180005dcc  mov     [rbp+var_1F], 0
0x180005dd0  mov     [rbp+var_1C], 0
0x180005dd7  xor     eax, eax
0x180005dd9  mov     [rbp+var_16], ax
0x180005ddd  mov     eax, [rcx+8]
0x180005de0  mov     [rbp+var_30], eax
0x180005de3  mov     rax, [rcx+18h]
0x180005de7  mov     [rbp+var_28], rax
0x180005deb  mov     al, [rcx]
0x180005ded  mov     [rbp+var_20], al
0x180005df0  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x180005df7  mov     [rbp+var_1E], ax
0x180005dfb  movzx   eax, word ptr [rcx+40h]
0x180005dff  mov     [rbp+var_18], ax
0x180005e03  mov     [rbp+var_14], 0
0x180005e0a  mov     rax, [rcx+38h]
0x180005e0e  mov     [rbp+var_10], rax
0x180005e12  mov     rax, [rcx+80h]
0x180005e19  mov     [rbp+var_8], rax
0x180005e1d  mov     [rbp+arg_0], 0
0x180005e25  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x180005e2c  test    rdi, rdi
0x180005e2f  jnz     short loc_180005E75
0x180005e31  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180005e38  test    rax, rax
0x180005e3b  jnz     short loc_180005E56
0x180005e3d  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180005e44  call    cs:__imp_GetModuleHandleW
0x180005e4a  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180005e51  test    rax, rax
0x180005e54  jz      short loc_180005E69
0x180005e56  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x180005e5d  mov     rcx, rax; hModule
0x180005e60  call    cs:__imp_GetProcAddress
0x180005e66  mov     rdi, rax
0x180005e69  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x180005e70  test    rdi, rdi
0x180005e73  jz      short loc_180005E88
0x180005e75  lea     r8, [rbp+arg_0]
0x180005e79  lea     rdx, [rbp+var_30]
0x180005e7d  xor     ecx, ecx
0x180005e7f  mov     rax, rdi
0x180005e82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e87  nop
0x180005e88  mov     eax, dword ptr [rbp+arg_0]
0x180005e8b  mov     [rbx+10h], eax
0x180005e8e  movzx   ecx, byte ptr [rbp+arg_0+4]
0x180005e92  sub     ecx, 1
0x180005e95  jz      short loc_180005EAD
0x180005e97  sub     ecx, 1
0x180005e9a  jz      short loc_180005EA7
0x180005e9c  cmp     ecx, 1
0x180005e9f  jnz     short loc_180005EB1
0x180005ea1  or      dword ptr [rbx+4], 4
0x180005ea5  jmp     short loc_180005EB1
0x180005ea7  or      dword ptr [rbx+4], 2
0x180005eab  jmp     short loc_180005EB1
0x180005ead  or      dword ptr [rbx+4], 1
0x180005eb1  mov     rbx, [rsp+50h+arg_8]
0x180005eb6  mov     rdi, [rsp+50h+arg_10]
0x180005ebb  add     rsp, 50h
0x180005ebf  pop     rbp
0x180005ec0  retn
```
