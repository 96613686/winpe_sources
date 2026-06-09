# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180005cf0`
- end: `0x180005e01`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `273`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005cf0`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005d84`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005d84`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005da0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005da0`

## string_xrefs

- `0x180005d7d`: `kernelbase.dll`

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
0x180005cf0  mov     [rsp-8+arg_8], rbx
0x180005cf5  mov     [rsp-8+arg_10], rdi
0x180005cfa  push    rbp
0x180005cfb  mov     rbp, rsp
0x180005cfe  sub     rsp, 50h
0x180005d02  mov     rbx, rcx
0x180005d05  mov     [rbp+var_2C], 0
0x180005d0c  mov     [rbp+var_1F], 0
0x180005d10  mov     [rbp+var_1C], 0
0x180005d17  xor     eax, eax
0x180005d19  mov     [rbp+var_16], ax
0x180005d1d  mov     eax, [rcx+8]
0x180005d20  mov     [rbp+var_30], eax
0x180005d23  mov     rax, [rcx+18h]
0x180005d27  mov     [rbp+var_28], rax
0x180005d2b  mov     al, [rcx]
0x180005d2d  mov     [rbp+var_20], al
0x180005d30  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x180005d37  mov     [rbp+var_1E], ax
0x180005d3b  movzx   eax, word ptr [rcx+40h]
0x180005d3f  mov     [rbp+var_18], ax
0x180005d43  mov     [rbp+var_14], 0
0x180005d4a  mov     rax, [rcx+38h]
0x180005d4e  mov     [rbp+var_10], rax
0x180005d52  mov     rax, [rcx+80h]
0x180005d59  mov     [rbp+var_8], rax
0x180005d5d  mov     [rbp+arg_0], 0
0x180005d65  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x180005d6c  test    rdi, rdi
0x180005d6f  jnz     short loc_180005DB5
0x180005d71  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180005d78  test    rax, rax
0x180005d7b  jnz     short loc_180005D96
0x180005d7d  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180005d84  call    cs:__imp_GetModuleHandleW
0x180005d8a  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180005d91  test    rax, rax
0x180005d94  jz      short loc_180005DA9
0x180005d96  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x180005d9d  mov     rcx, rax; hModule
0x180005da0  call    cs:__imp_GetProcAddress
0x180005da6  mov     rdi, rax
0x180005da9  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x180005db0  test    rdi, rdi
0x180005db3  jz      short loc_180005DC8
0x180005db5  lea     r8, [rbp+arg_0]
0x180005db9  lea     rdx, [rbp+var_30]
0x180005dbd  xor     ecx, ecx
0x180005dbf  mov     rax, rdi
0x180005dc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005dc7  nop
0x180005dc8  mov     eax, dword ptr [rbp+arg_0]
0x180005dcb  mov     [rbx+10h], eax
0x180005dce  movzx   ecx, byte ptr [rbp+arg_0+4]
0x180005dd2  sub     ecx, 1
0x180005dd5  jz      short loc_180005DED
0x180005dd7  sub     ecx, 1
0x180005dda  jz      short loc_180005DE7
0x180005ddc  cmp     ecx, 1
0x180005ddf  jnz     short loc_180005DF1
0x180005de1  or      dword ptr [rbx+4], 4
0x180005de5  jmp     short loc_180005DF1
0x180005de7  or      dword ptr [rbx+4], 2
0x180005deb  jmp     short loc_180005DF1
0x180005ded  or      dword ptr [rbx+4], 1
0x180005df1  mov     rbx, [rsp+50h+arg_8]
0x180005df6  mov     rdi, [rsp+50h+arg_10]
0x180005dfb  add     rsp, 50h
0x180005dff  pop     rbp
0x180005e00  retn
```
