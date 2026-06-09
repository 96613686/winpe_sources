# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180004780`
- end: `0x180004891`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `273`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004780`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004814`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004814`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004830`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004830`

## string_xrefs

- `0x18000480d`: `kernelbase.dll`

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
0x180004780  mov     [rsp-8+arg_8], rbx
0x180004785  mov     [rsp-8+arg_10], rdi
0x18000478a  push    rbp
0x18000478b  mov     rbp, rsp
0x18000478e  sub     rsp, 50h
0x180004792  mov     rbx, rcx
0x180004795  mov     [rbp+var_2C], 0
0x18000479c  mov     [rbp+var_1F], 0
0x1800047a0  mov     [rbp+var_1C], 0
0x1800047a7  xor     eax, eax
0x1800047a9  mov     [rbp+var_16], ax
0x1800047ad  mov     eax, [rcx+8]
0x1800047b0  mov     [rbp+var_30], eax
0x1800047b3  mov     rax, [rcx+18h]
0x1800047b7  mov     [rbp+var_28], rax
0x1800047bb  mov     al, [rcx]
0x1800047bd  mov     [rbp+var_20], al
0x1800047c0  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x1800047c7  mov     [rbp+var_1E], ax
0x1800047cb  movzx   eax, word ptr [rcx+40h]
0x1800047cf  mov     [rbp+var_18], ax
0x1800047d3  mov     [rbp+var_14], 0
0x1800047da  mov     rax, [rcx+38h]
0x1800047de  mov     [rbp+var_10], rax
0x1800047e2  mov     rax, [rcx+80h]
0x1800047e9  mov     [rbp+var_8], rax
0x1800047ed  mov     [rbp+arg_0], 0
0x1800047f5  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x1800047fc  test    rdi, rdi
0x1800047ff  jnz     short loc_180004845
0x180004801  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180004808  test    rax, rax
0x18000480b  jnz     short loc_180004826
0x18000480d  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180004814  call    cs:__imp_GetModuleHandleW
0x18000481a  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180004821  test    rax, rax
0x180004824  jz      short loc_180004839
0x180004826  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x18000482d  mov     rcx, rax; hModule
0x180004830  call    cs:__imp_GetProcAddress
0x180004836  mov     rdi, rax
0x180004839  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x180004840  test    rdi, rdi
0x180004843  jz      short loc_180004858
0x180004845  lea     r8, [rbp+arg_0]
0x180004849  lea     rdx, [rbp+var_30]
0x18000484d  xor     ecx, ecx
0x18000484f  mov     rax, rdi
0x180004852  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004857  nop
0x180004858  mov     eax, dword ptr [rbp+arg_0]
0x18000485b  mov     [rbx+10h], eax
0x18000485e  movzx   ecx, byte ptr [rbp+arg_0+4]
0x180004862  sub     ecx, 1
0x180004865  jz      short loc_18000487D
0x180004867  sub     ecx, 1
0x18000486a  jz      short loc_180004877
0x18000486c  cmp     ecx, 1
0x18000486f  jnz     short loc_180004881
0x180004871  or      dword ptr [rbx+4], 4
0x180004875  jmp     short loc_180004881
0x180004877  or      dword ptr [rbx+4], 2
0x18000487b  jmp     short loc_180004881
0x18000487d  or      dword ptr [rbx+4], 1
0x180004881  mov     rbx, [rsp+50h+arg_8]
0x180004886  mov     rdi, [rsp+50h+arg_10]
0x18000488b  add     rsp, 50h
0x18000488f  pop     rbp
0x180004890  retn
```
