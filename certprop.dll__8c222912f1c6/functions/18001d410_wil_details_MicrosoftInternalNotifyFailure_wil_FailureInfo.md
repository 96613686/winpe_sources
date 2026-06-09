# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x18001d410`
- end: `0x18001d521`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `273`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001d410`
- `0x180026010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001d4a4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001d4a4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d4c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d4c0`

## string_xrefs

- `0x18001d49d`: `kernelbase.dll`

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
0x18001d410  mov     [rsp-8+arg_8], rbx
0x18001d415  mov     [rsp-8+arg_10], rdi
0x18001d41a  push    rbp
0x18001d41b  mov     rbp, rsp
0x18001d41e  sub     rsp, 50h
0x18001d422  mov     rbx, rcx
0x18001d425  mov     [rbp+var_2C], 0
0x18001d42c  mov     [rbp+var_1F], 0
0x18001d430  mov     [rbp+var_1C], 0
0x18001d437  xor     eax, eax
0x18001d439  mov     [rbp+var_16], ax
0x18001d43d  mov     eax, [rcx+8]
0x18001d440  mov     [rbp+var_30], eax
0x18001d443  mov     rax, [rcx+18h]
0x18001d447  mov     [rbp+var_28], rax
0x18001d44b  mov     al, [rcx]
0x18001d44d  mov     [rbp+var_20], al
0x18001d450  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x18001d457  mov     [rbp+var_1E], ax
0x18001d45b  movzx   eax, word ptr [rcx+40h]
0x18001d45f  mov     [rbp+var_18], ax
0x18001d463  mov     [rbp+var_14], 0
0x18001d46a  mov     rax, [rcx+38h]
0x18001d46e  mov     [rbp+var_10], rax
0x18001d472  mov     rax, [rcx+80h]
0x18001d479  mov     [rbp+var_8], rax
0x18001d47d  mov     [rbp+arg_0], 0
0x18001d485  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x18001d48c  test    rdi, rdi
0x18001d48f  jnz     short loc_18001D4D5
0x18001d491  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18001d498  test    rax, rax
0x18001d49b  jnz     short loc_18001D4B6
0x18001d49d  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001d4a4  call    cs:__imp_GetModuleHandleW
0x18001d4aa  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18001d4b1  test    rax, rax
0x18001d4b4  jz      short loc_18001D4C9
0x18001d4b6  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x18001d4bd  mov     rcx, rax; hModule
0x18001d4c0  call    cs:__imp_GetProcAddress
0x18001d4c6  mov     rdi, rax
0x18001d4c9  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x18001d4d0  test    rdi, rdi
0x18001d4d3  jz      short loc_18001D4E8
0x18001d4d5  lea     r8, [rbp+arg_0]
0x18001d4d9  lea     rdx, [rbp+var_30]
0x18001d4dd  xor     ecx, ecx
0x18001d4df  mov     rax, rdi
0x18001d4e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d4e7  nop
0x18001d4e8  mov     eax, dword ptr [rbp+arg_0]
0x18001d4eb  mov     [rbx+10h], eax
0x18001d4ee  movzx   ecx, byte ptr [rbp+arg_0+4]
0x18001d4f2  sub     ecx, 1
0x18001d4f5  jz      short loc_18001D50D
0x18001d4f7  sub     ecx, 1
0x18001d4fa  jz      short loc_18001D507
0x18001d4fc  cmp     ecx, 1
0x18001d4ff  jnz     short loc_18001D511
0x18001d501  or      dword ptr [rbx+4], 4
0x18001d505  jmp     short loc_18001D511
0x18001d507  or      dword ptr [rbx+4], 2
0x18001d50b  jmp     short loc_18001D511
0x18001d50d  or      dword ptr [rbx+4], 1
0x18001d511  mov     rbx, [rsp+50h+arg_8]
0x18001d516  mov     rdi, [rsp+50h+arg_10]
0x18001d51b  add     rsp, 50h
0x18001d51f  pop     rbp
0x18001d520  retn
```
