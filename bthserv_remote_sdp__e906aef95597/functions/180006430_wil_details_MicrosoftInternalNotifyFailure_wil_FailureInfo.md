# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180006430`
- end: `0x18000654a`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `282`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006430`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800064bb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800064bb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800064dd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800064dd`

## string_xrefs

- `0x1800064b4`: `kernelbase.dll`

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
  ProcAddress = 0;
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
0x180006430  mov     [rsp-8+arg_8], rbx
0x180006435  mov     [rsp-8+arg_10], rsi
0x18000643a  mov     [rsp-8+arg_18], rdi
0x18000643f  push    rbp
0x180006440  mov     rbp, rsp
0x180006443  sub     rsp, 50h
0x180006447  mov     rbx, rcx
0x18000644a  xor     esi, esi
0x18000644c  mov     [rbp+var_2C], esi
0x18000644f  mov     [rbp+var_1F], sil
0x180006453  mov     [rbp+var_1C], esi
0x180006456  mov     [rbp+var_16], si
0x18000645a  mov     eax, [rcx+8]
0x18000645d  mov     [rbp+var_30], eax
0x180006460  mov     rax, [rcx+18h]
0x180006464  mov     [rbp+var_28], rax
0x180006468  mov     al, [rcx]
0x18000646a  mov     [rbp+var_20], al
0x18000646d  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x180006474  mov     [rbp+var_1E], ax
0x180006478  movzx   eax, word ptr [rcx+40h]
0x18000647c  mov     [rbp+var_18], ax
0x180006480  mov     [rbp+var_14], esi
0x180006483  mov     rax, [rcx+38h]
0x180006487  mov     [rbp+var_10], rax
0x18000648b  mov     rax, [rcx+80h]
0x180006492  mov     [rbp+var_8], rax
0x180006496  mov     [rbp+arg_0], rsi
0x18000649a  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x1800064a1  test    rdi, rdi
0x1800064a4  jnz     short loc_1800064F8
0x1800064a6  mov     edi, esi
0x1800064a8  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800064af  test    rax, rax
0x1800064b2  jnz     short loc_1800064D3
0x1800064b4  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800064bb  call    cs:__imp_GetModuleHandleW
0x1800064c2  nop     dword ptr [rax+rax+00h]
0x1800064c7  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800064ce  test    rax, rax
0x1800064d1  jz      short loc_1800064EC
0x1800064d3  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x1800064da  mov     rcx, rax; hModule
0x1800064dd  call    cs:__imp_GetProcAddress
0x1800064e4  nop     dword ptr [rax+rax+00h]
0x1800064e9  mov     rdi, rax
0x1800064ec  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x1800064f3  test    rdi, rdi
0x1800064f6  jz      short loc_18000650B
0x1800064f8  lea     r8, [rbp+arg_0]
0x1800064fc  lea     rdx, [rbp+var_30]
0x180006500  xor     ecx, ecx
0x180006502  mov     rax, rdi
0x180006505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000650a  nop
0x18000650b  mov     eax, dword ptr [rbp+arg_0]
0x18000650e  mov     [rbx+10h], eax
0x180006511  movzx   ecx, byte ptr [rbp+arg_0+4]
0x180006515  sub     ecx, 1
0x180006518  jz      short loc_180006530
0x18000651a  sub     ecx, 1
0x18000651d  jz      short loc_18000652A
0x18000651f  cmp     ecx, 1
0x180006522  jnz     short loc_180006534
0x180006524  or      dword ptr [rbx+4], 4
0x180006528  jmp     short loc_180006534
0x18000652a  or      dword ptr [rbx+4], 2
0x18000652e  jmp     short loc_180006534
0x180006530  or      dword ptr [rbx+4], 1
0x180006534  mov     rbx, [rsp+50h+arg_8]
0x180006539  mov     rsi, [rsp+50h+arg_10]
0x18000653e  mov     rdi, [rsp+50h+arg_18]
0x180006543  add     rsp, 50h
0x180006547  pop     rbp
0x180006548  retn
```
