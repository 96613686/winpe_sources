# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x140008a50`
- end: `0x140008b61`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `273`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140008a50`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x140008ae4`
- `KERNEL32!GetModuleHandleW` at `0x140008ae4`
- `KERNEL32!GetProcAddress` at `0x140008b00`
- `KERNEL32!GetProcAddress` at `0x140008b00`

## string_xrefs

- `0x140008add`: `kernelbase.dll`

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
0x140008a50  mov     [rsp-8+arg_8], rbx
0x140008a55  mov     [rsp-8+arg_10], rdi
0x140008a5a  push    rbp
0x140008a5b  mov     rbp, rsp
0x140008a5e  sub     rsp, 50h
0x140008a62  mov     rbx, rcx
0x140008a65  mov     [rbp+var_2C], 0
0x140008a6c  mov     [rbp+var_1F], 0
0x140008a70  mov     [rbp+var_1C], 0
0x140008a77  xor     eax, eax
0x140008a79  mov     [rbp+var_16], ax
0x140008a7d  mov     eax, [rcx+8]
0x140008a80  mov     [rbp+var_30], eax
0x140008a83  mov     rax, [rcx+18h]
0x140008a87  mov     [rbp+var_28], rax
0x140008a8b  mov     al, [rcx]
0x140008a8d  mov     [rbp+var_20], al
0x140008a90  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x140008a97  mov     [rbp+var_1E], ax
0x140008a9b  movzx   eax, word ptr [rcx+40h]
0x140008a9f  mov     [rbp+var_18], ax
0x140008aa3  mov     [rbp+var_14], 0
0x140008aaa  mov     rax, [rcx+38h]
0x140008aae  mov     [rbp+var_10], rax
0x140008ab2  mov     rax, [rcx+80h]
0x140008ab9  mov     [rbp+var_8], rax
0x140008abd  mov     [rbp+arg_0], 0
0x140008ac5  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x140008acc  test    rdi, rdi
0x140008acf  jnz     short loc_140008B15
0x140008ad1  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140008ad8  test    rax, rax
0x140008adb  jnz     short loc_140008AF6
0x140008add  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x140008ae4  call    cs:__imp_GetModuleHandleW
0x140008aea  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140008af1  test    rax, rax
0x140008af4  jz      short loc_140008B09
0x140008af6  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x140008afd  mov     rcx, rax; hModule
0x140008b00  call    cs:__imp_GetProcAddress
0x140008b06  mov     rdi, rax
0x140008b09  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x140008b10  test    rdi, rdi
0x140008b13  jz      short loc_140008B28
0x140008b15  lea     r8, [rbp+arg_0]
0x140008b19  lea     rdx, [rbp+var_30]
0x140008b1d  xor     ecx, ecx
0x140008b1f  mov     rax, rdi
0x140008b22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008b27  nop
0x140008b28  mov     eax, dword ptr [rbp+arg_0]
0x140008b2b  mov     [rbx+10h], eax
0x140008b2e  movzx   ecx, byte ptr [rbp+arg_0+4]
0x140008b32  sub     ecx, 1
0x140008b35  jz      short loc_140008B4D
0x140008b37  sub     ecx, 1
0x140008b3a  jz      short loc_140008B47
0x140008b3c  cmp     ecx, 1
0x140008b3f  jnz     short loc_140008B51
0x140008b41  or      dword ptr [rbx+4], 4
0x140008b45  jmp     short loc_140008B51
0x140008b47  or      dword ptr [rbx+4], 2
0x140008b4b  jmp     short loc_140008B51
0x140008b4d  or      dword ptr [rbx+4], 1
0x140008b51  mov     rbx, [rsp+50h+arg_8]
0x140008b56  mov     rdi, [rsp+50h+arg_10]
0x140008b5b  add     rsp, 50h
0x140008b5f  pop     rbp
0x140008b60  retn
```
