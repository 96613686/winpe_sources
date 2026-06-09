# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180006330`
- end: `0x180006441`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `273`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006330`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800063c4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800063c4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800063e0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800063e0`

## string_xrefs

- `0x1800063bd`: `kernelbase.dll`

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
0x180006330  mov     [rsp-8+arg_8], rbx
0x180006335  mov     [rsp-8+arg_10], rdi
0x18000633a  push    rbp
0x18000633b  mov     rbp, rsp
0x18000633e  sub     rsp, 50h
0x180006342  mov     rbx, rcx
0x180006345  mov     [rbp+var_2C], 0
0x18000634c  mov     [rbp+var_1F], 0
0x180006350  mov     [rbp+var_1C], 0
0x180006357  xor     eax, eax
0x180006359  mov     [rbp+var_16], ax
0x18000635d  mov     eax, [rcx+8]
0x180006360  mov     [rbp+var_30], eax
0x180006363  mov     rax, [rcx+18h]
0x180006367  mov     [rbp+var_28], rax
0x18000636b  mov     al, [rcx]
0x18000636d  mov     [rbp+var_20], al
0x180006370  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x180006377  mov     [rbp+var_1E], ax
0x18000637b  movzx   eax, word ptr [rcx+40h]
0x18000637f  mov     [rbp+var_18], ax
0x180006383  mov     [rbp+var_14], 0
0x18000638a  mov     rax, [rcx+38h]
0x18000638e  mov     [rbp+var_10], rax
0x180006392  mov     rax, [rcx+80h]
0x180006399  mov     [rbp+var_8], rax
0x18000639d  mov     [rbp+arg_0], 0
0x1800063a5  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x1800063ac  test    rdi, rdi
0x1800063af  jnz     short loc_1800063F5
0x1800063b1  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800063b8  test    rax, rax
0x1800063bb  jnz     short loc_1800063D6
0x1800063bd  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800063c4  call    cs:__imp_GetModuleHandleW
0x1800063ca  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800063d1  test    rax, rax
0x1800063d4  jz      short loc_1800063E9
0x1800063d6  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x1800063dd  mov     rcx, rax; hModule
0x1800063e0  call    cs:__imp_GetProcAddress
0x1800063e6  mov     rdi, rax
0x1800063e9  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x1800063f0  test    rdi, rdi
0x1800063f3  jz      short loc_180006408
0x1800063f5  lea     r8, [rbp+arg_0]
0x1800063f9  lea     rdx, [rbp+var_30]
0x1800063fd  xor     ecx, ecx
0x1800063ff  mov     rax, rdi
0x180006402  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006407  nop
0x180006408  mov     eax, dword ptr [rbp+arg_0]
0x18000640b  mov     [rbx+10h], eax
0x18000640e  movzx   ecx, byte ptr [rbp+arg_0+4]
0x180006412  sub     ecx, 1
0x180006415  jz      short loc_18000642D
0x180006417  sub     ecx, 1
0x18000641a  jz      short loc_180006427
0x18000641c  cmp     ecx, 1
0x18000641f  jnz     short loc_180006431
0x180006421  or      dword ptr [rbx+4], 4
0x180006425  jmp     short loc_180006431
0x180006427  or      dword ptr [rbx+4], 2
0x18000642b  jmp     short loc_180006431
0x18000642d  or      dword ptr [rbx+4], 1
0x180006431  mov     rbx, [rsp+50h+arg_8]
0x180006436  mov     rdi, [rsp+50h+arg_10]
0x18000643b  add     rsp, 50h
0x18000643f  pop     rbp
0x180006440  retn
```
