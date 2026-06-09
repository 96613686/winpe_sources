# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180025a20`
- end: `0x180025b43`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `291`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001e1d0`
- `0x180025a20`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025ad6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025ad6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180025aba`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180025aba`

## string_xrefs

- `0x180025ab3`: `kernelbase.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::MicrosoftInternalNotifyFailure(wil::details *this, struct wil::FailureInfo *a2)
{
  FARPROC ProcAddress; // rdi
  HMODULE ModuleHandleW; // rax
  _DWORD v5[2]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v6; // [rsp+28h] [rbp-40h]
  char v7; // [rsp+30h] [rbp-38h]
  char v8; // [rsp+31h] [rbp-37h]
  __int16 v9; // [rsp+32h] [rbp-36h]
  int v10; // [rsp+34h] [rbp-34h]
  __int16 v11; // [rsp+38h] [rbp-30h]
  __int16 v12; // [rsp+3Ah] [rbp-2Eh]
  int v13; // [rsp+3Ch] [rbp-2Ch]
  __int64 v14; // [rsp+40h] [rbp-28h]
  __int64 v15; // [rsp+48h] [rbp-20h]
  __int64 v16; // [rsp+50h] [rbp-18h] BYREF

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
    || (ProcAddress = 0,
        ModuleHandleW = GetModuleHandleW(L"kernelbase.dll"),
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
0x180025a20  mov     [rsp+arg_8], rbx
0x180025a25  push    rdi
0x180025a26  sub     rsp, 60h
0x180025a2a  mov     rax, cs:__security_cookie
0x180025a31  xor     rax, rsp
0x180025a34  mov     [rsp+68h+var_10], rax
0x180025a39  mov     rbx, rcx
0x180025a3c  xor     ecx, ecx
0x180025a3e  mov     [rsp+68h+var_44], ecx
0x180025a42  mov     [rsp+68h+var_37], cl
0x180025a46  mov     [rsp+68h+var_34], ecx
0x180025a4a  mov     [rsp+68h+var_2E], cx
0x180025a4f  mov     eax, [rbx+8]
0x180025a52  mov     [rsp+68h+var_48], eax
0x180025a56  mov     rax, [rbx+18h]
0x180025a5a  mov     [rsp+68h+var_40], rax
0x180025a5f  movzx   eax, byte ptr [rbx]
0x180025a62  mov     [rsp+68h+var_38], al
0x180025a66  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x180025a6d  mov     [rsp+68h+var_36], ax
0x180025a72  movzx   eax, word ptr [rbx+40h]
0x180025a76  mov     [rsp+68h+var_30], ax
0x180025a7b  mov     [rsp+68h+var_2C], ecx
0x180025a7f  mov     rax, [rbx+38h]
0x180025a83  mov     [rsp+68h+var_28], rax
0x180025a88  mov     rax, [rbx+80h]
0x180025a8f  mov     [rsp+68h+var_20], rax
0x180025a94  mov     [rsp+68h+var_18], rcx
0x180025a99  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x180025aa0  test    rdi, rdi
0x180025aa3  jnz     short loc_180025AEB
0x180025aa5  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180025aac  test    rax, rax
0x180025aaf  jnz     short loc_180025ACC
0x180025ab1  mov     edi, ecx
0x180025ab3  lea     rcx, ModuleName; "kernelbase.dll"
0x180025aba  call    cs:__imp_GetModuleHandleW
0x180025ac0  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180025ac7  test    rax, rax
0x180025aca  jz      short loc_180025ADF
0x180025acc  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x180025ad3  mov     rcx, rax; hModule
0x180025ad6  call    cs:__imp_GetProcAddress
0x180025adc  mov     rdi, rax
0x180025adf  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x180025ae6  test    rdi, rdi
0x180025ae9  jz      short loc_180025B00
0x180025aeb  lea     r8, [rsp+68h+var_18]
0x180025af0  lea     rdx, [rsp+68h+var_48]
0x180025af5  xor     ecx, ecx
0x180025af7  mov     rax, rdi
0x180025afa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025aff  nop
0x180025b00  mov     eax, dword ptr [rsp+68h+var_18]
0x180025b04  mov     [rbx+10h], eax
0x180025b07  movzx   ecx, byte ptr [rsp+68h+var_18+4]
0x180025b0c  sub     ecx, 1
0x180025b0f  jz      short loc_180025B27
0x180025b11  sub     ecx, 1
0x180025b14  jz      short loc_180025B21
0x180025b16  cmp     ecx, 1
0x180025b19  jnz     short loc_180025B2B
0x180025b1b  or      dword ptr [rbx+4], 4
0x180025b1f  jmp     short loc_180025B2B
0x180025b21  or      dword ptr [rbx+4], 2
0x180025b25  jmp     short loc_180025B2B
0x180025b27  or      dword ptr [rbx+4], 1
0x180025b2b  mov     rcx, [rsp+68h+var_10]
0x180025b30  xor     rcx, rsp; StackCookie
0x180025b33  call    __security_check_cookie
0x180025b38  mov     rbx, [rsp+68h+arg_8]
0x180025b3d  add     rsp, 60h
0x180025b41  pop     rdi
0x180025b42  retn
```
