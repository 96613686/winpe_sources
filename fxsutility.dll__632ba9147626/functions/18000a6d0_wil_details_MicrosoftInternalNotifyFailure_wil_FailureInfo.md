# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x18000a6d0`
- end: `0x18000a7e1`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `273`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000a6d0`
- `0x180017010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000a764`
- `KERNEL32!GetModuleHandleW` at `0x18000a764`
- `KERNEL32!GetProcAddress` at `0x18000a780`
- `KERNEL32!GetProcAddress` at `0x18000a780`

## string_xrefs

- `0x18000a75d`: `kernelbase.dll`

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
0x18000a6d0  mov     [rsp-8+arg_8], rbx
0x18000a6d5  mov     [rsp-8+arg_10], rdi
0x18000a6da  push    rbp
0x18000a6db  mov     rbp, rsp
0x18000a6de  sub     rsp, 50h
0x18000a6e2  mov     rbx, rcx
0x18000a6e5  mov     [rbp+var_2C], 0
0x18000a6ec  mov     [rbp+var_1F], 0
0x18000a6f0  mov     [rbp+var_1C], 0
0x18000a6f7  xor     eax, eax
0x18000a6f9  mov     [rbp+var_16], ax
0x18000a6fd  mov     eax, [rcx+8]
0x18000a700  mov     [rbp+var_30], eax
0x18000a703  mov     rax, [rcx+18h]
0x18000a707  mov     [rbp+var_28], rax
0x18000a70b  mov     al, [rcx]
0x18000a70d  mov     [rbp+var_20], al
0x18000a710  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x18000a717  mov     [rbp+var_1E], ax
0x18000a71b  movzx   eax, word ptr [rcx+40h]
0x18000a71f  mov     [rbp+var_18], ax
0x18000a723  mov     [rbp+var_14], 0
0x18000a72a  mov     rax, [rcx+38h]
0x18000a72e  mov     [rbp+var_10], rax
0x18000a732  mov     rax, [rcx+80h]
0x18000a739  mov     [rbp+var_8], rax
0x18000a73d  mov     [rbp+arg_0], 0
0x18000a745  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x18000a74c  test    rdi, rdi
0x18000a74f  jnz     short loc_18000A795
0x18000a751  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000a758  test    rax, rax
0x18000a75b  jnz     short loc_18000A776
0x18000a75d  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000a764  call    cs:__imp_GetModuleHandleW
0x18000a76a  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000a771  test    rax, rax
0x18000a774  jz      short loc_18000A789
0x18000a776  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x18000a77d  mov     rcx, rax; hModule
0x18000a780  call    cs:__imp_GetProcAddress
0x18000a786  mov     rdi, rax
0x18000a789  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x18000a790  test    rdi, rdi
0x18000a793  jz      short loc_18000A7A8
0x18000a795  lea     r8, [rbp+arg_0]
0x18000a799  lea     rdx, [rbp+var_30]
0x18000a79d  xor     ecx, ecx
0x18000a79f  mov     rax, rdi
0x18000a7a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7a7  nop
0x18000a7a8  mov     eax, dword ptr [rbp+arg_0]
0x18000a7ab  mov     [rbx+10h], eax
0x18000a7ae  movzx   ecx, byte ptr [rbp+arg_0+4]
0x18000a7b2  sub     ecx, 1
0x18000a7b5  jz      short loc_18000A7CD
0x18000a7b7  sub     ecx, 1
0x18000a7ba  jz      short loc_18000A7C7
0x18000a7bc  cmp     ecx, 1
0x18000a7bf  jnz     short loc_18000A7D1
0x18000a7c1  or      dword ptr [rbx+4], 4
0x18000a7c5  jmp     short loc_18000A7D1
0x18000a7c7  or      dword ptr [rbx+4], 2
0x18000a7cb  jmp     short loc_18000A7D1
0x18000a7cd  or      dword ptr [rbx+4], 1
0x18000a7d1  mov     rbx, [rsp+50h+arg_8]
0x18000a7d6  mov     rdi, [rsp+50h+arg_10]
0x18000a7db  add     rsp, 50h
0x18000a7df  pop     rbp
0x18000a7e0  retn
```
