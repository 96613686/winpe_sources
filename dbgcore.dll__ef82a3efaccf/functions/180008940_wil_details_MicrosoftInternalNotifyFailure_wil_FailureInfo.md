# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180008940`
- end: `0x180008a5c`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `284`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008940`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800089f9`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800089f9`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x1800089dd`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x1800089dd`

## string_xrefs

- `0x1800089d6`: `kernelbase.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::MicrosoftInternalNotifyFailure(wil::details *this, struct wil::FailureInfo *a2)
{
  FARPROC ProcAddress; // rdi
  HMODULE ModuleHandleW; // rax
  _DWORD v5[2]; // [rsp+28h] [rbp-38h] BYREF
  __int64 v6; // [rsp+30h] [rbp-30h]
  char v7; // [rsp+38h] [rbp-28h]
  char v8; // [rsp+39h] [rbp-27h]
  __int16 v9; // [rsp+3Ah] [rbp-26h]
  int v10; // [rsp+3Ch] [rbp-24h]
  __int16 v11; // [rsp+40h] [rbp-20h]
  __int16 v12; // [rsp+42h] [rbp-1Eh]
  int v13; // [rsp+44h] [rbp-1Ch]
  __int64 v14; // [rsp+48h] [rbp-18h]
  __int64 v15; // [rsp+50h] [rbp-10h]
  __int64 v16; // [rsp+70h] [rbp+10h] BYREF

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
0x180008940  mov     rax, rsp
0x180008943  push    rbp
0x180008944  mov     rbp, rsp
0x180008947  sub     rsp, 60h
0x18000894b  mov     [rbp+var_40], 0FFFFFFFFFFFFFFFEh
0x180008953  mov     [rax+10h], rbx
0x180008957  mov     [rax+18h], rdi
0x18000895b  mov     rbx, rcx
0x18000895e  mov     [rbp+var_34], 0
0x180008965  mov     [rbp+var_27], 0
0x180008969  mov     [rbp+var_24], 0
0x180008970  xor     eax, eax
0x180008972  mov     [rbp+var_1E], ax
0x180008976  mov     eax, [rcx+8]
0x180008979  mov     [rbp+var_38], eax
0x18000897c  mov     rax, [rcx+18h]
0x180008980  mov     [rbp+var_30], rax
0x180008984  mov     al, [rcx]
0x180008986  mov     [rbp+var_28], al
0x180008989  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x180008990  mov     [rbp+var_26], ax
0x180008994  movzx   eax, word ptr [rcx+40h]
0x180008998  mov     [rbp+var_20], ax
0x18000899c  mov     [rbp+var_1C], 0
0x1800089a3  mov     rax, [rcx+38h]
0x1800089a7  mov     [rbp+var_18], rax
0x1800089ab  mov     rax, [rcx+80h]
0x1800089b2  mov     [rbp+var_10], rax
0x1800089b6  mov     [rbp+arg_0], 0
0x1800089be  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x1800089c5  test    rdi, rdi
0x1800089c8  jnz     short loc_180008A0E
0x1800089ca  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800089d1  test    rax, rax
0x1800089d4  jnz     short loc_1800089EF
0x1800089d6  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800089dd  call    cs:__imp_GetModuleHandleW
0x1800089e3  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800089ea  test    rax, rax
0x1800089ed  jz      short loc_180008A02
0x1800089ef  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x1800089f6  mov     rcx, rax; hModule
0x1800089f9  call    cs:__imp_GetProcAddress
0x1800089ff  mov     rdi, rax
0x180008a02  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x180008a09  test    rdi, rdi
0x180008a0c  jz      short loc_180008A21
0x180008a0e  lea     r8, [rbp+arg_0]
0x180008a12  lea     rdx, [rbp+var_38]
0x180008a16  xor     ecx, ecx
0x180008a18  mov     rax, rdi
0x180008a1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a20  nop
0x180008a21  mov     eax, dword ptr [rbp+arg_0]
0x180008a24  mov     [rbx+10h], eax
0x180008a27  movzx   ecx, byte ptr [rbp+arg_0+4]
0x180008a2b  sub     ecx, 1
0x180008a2e  jz      short loc_180008A46
0x180008a30  sub     ecx, 1
0x180008a33  jz      short loc_180008A40
0x180008a35  cmp     ecx, 1
0x180008a38  jnz     short loc_180008A4A
0x180008a3a  or      dword ptr [rbx+4], 4
0x180008a3e  jmp     short loc_180008A4A
0x180008a40  or      dword ptr [rbx+4], 2
0x180008a44  jmp     short loc_180008A4A
0x180008a46  or      dword ptr [rbx+4], 1
0x180008a4a  lea     r11, [rsp+60h+var_s0]
0x180008a4f  mov     rbx, [r11+18h]
0x180008a53  mov     rdi, [r11+20h]
0x180008a57  mov     rsp, r11
0x180008a5a  pop     rbp
0x180008a5b  retn
```
