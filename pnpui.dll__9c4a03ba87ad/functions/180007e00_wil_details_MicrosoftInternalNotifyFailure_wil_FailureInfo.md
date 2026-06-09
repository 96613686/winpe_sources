# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180007e00`
- end: `0x180007f10`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `272`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007e00`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007eb0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007eb0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007e94`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007e94`

## string_xrefs

- `0x180007e8d`: `kernelbase.dll`

## pseudocode

```c
void __fastcall wil::details::MicrosoftInternalNotifyFailure(wil::details *this, struct wil::FailureInfo *a2)
{
  FARPROC ProcAddress; // rdi
  HMODULE ModuleHandleW; // rax
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  _DWORD v8[2]; // [rsp+20h] [rbp-30h] BYREF
  __int64 v9; // [rsp+28h] [rbp-28h]
  char v10; // [rsp+30h] [rbp-20h]
  char v11; // [rsp+31h] [rbp-1Fh]
  __int16 v12; // [rsp+32h] [rbp-1Eh]
  int v13; // [rsp+34h] [rbp-1Ch]
  __int16 v14; // [rsp+38h] [rbp-18h]
  __int16 v15; // [rsp+3Ah] [rbp-16h]
  int v16; // [rsp+3Ch] [rbp-14h]
  __int64 v17; // [rsp+40h] [rbp-10h]
  __int64 v18; // [rsp+48h] [rbp-8h]
  __int64 v19; // [rsp+60h] [rbp+10h] BYREF

  ProcAddress = (FARPROC)`wil::details::WilFailureNotifyWatchers'::`2'::s_pfnFailureNotifyWatchers;
  v15 = 0;
  v8[0] = *((_DWORD *)this + 2);
  v9 = *((_QWORD *)this + 3);
  v10 = *(_BYTE *)this;
  v12 = wil::g_moduleFailureReportFlags;
  v14 = *((_WORD *)this + 32);
  v17 = *((_QWORD *)this + 7);
  v18 = *((_QWORD *)this + 16);
  v8[1] = 0;
  v11 = 0;
  v13 = 0;
  v16 = 0;
  v19 = 0;
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
    ((void (__fastcall *)(_QWORD, _DWORD *, __int64 *))ProcAddress)(0, v8, &v19);
  v5 = BYTE4(v19);
  *((_DWORD *)this + 4) = v19;
  v6 = v5 - 1;
  if ( v6 )
  {
    v7 = v6 - 1;
    if ( v7 )
    {
      if ( v7 == 1 )
        *((_DWORD *)this + 1) |= 4u;
    }
    else
    {
      *((_DWORD *)this + 1) |= 2u;
    }
  }
  else
  {
    *((_DWORD *)this + 1) |= 1u;
  }
}

```

## disassembly

```asm
0x180007e00  mov     [rsp-8+arg_8], rbx
0x180007e05  mov     [rsp-8+arg_10], rdi
0x180007e0a  push    rbp
0x180007e0b  mov     rbp, rsp
0x180007e0e  sub     rsp, 50h
0x180007e12  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x180007e19  xor     eax, eax
0x180007e1b  mov     [rbp+var_16], ax
0x180007e1f  mov     rbx, rcx
0x180007e22  mov     eax, [rcx+8]
0x180007e25  mov     [rbp+var_30], eax
0x180007e28  mov     rax, [rcx+18h]
0x180007e2c  mov     [rbp+var_28], rax
0x180007e30  mov     al, [rcx]
0x180007e32  mov     [rbp+var_20], al
0x180007e35  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x180007e3c  mov     [rbp+var_1E], ax
0x180007e40  movzx   eax, word ptr [rcx+40h]
0x180007e44  mov     [rbp+var_18], ax
0x180007e48  mov     rax, [rcx+38h]
0x180007e4c  mov     [rbp+var_10], rax
0x180007e50  mov     rax, [rcx+80h]
0x180007e57  mov     [rbp+var_8], rax
0x180007e5b  mov     [rbp+var_2C], 0
0x180007e62  mov     [rbp+var_1F], 0
0x180007e66  mov     [rbp+var_1C], 0
0x180007e6d  mov     [rbp+var_14], 0
0x180007e74  mov     [rbp+arg_0], 0
0x180007e7c  test    rdi, rdi
0x180007e7f  jnz     short loc_180007EC5
0x180007e81  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180007e88  test    rax, rax
0x180007e8b  jnz     short loc_180007EA6
0x180007e8d  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180007e94  call    cs:__imp_GetModuleHandleW
0x180007e9a  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180007ea1  test    rax, rax
0x180007ea4  jz      short loc_180007EB9
0x180007ea6  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x180007ead  mov     rcx, rax; hModule
0x180007eb0  call    cs:__imp_GetProcAddress
0x180007eb6  mov     rdi, rax
0x180007eb9  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x180007ec0  test    rdi, rdi
0x180007ec3  jz      short loc_180007ED7
0x180007ec5  lea     r8, [rbp+arg_0]
0x180007ec9  xor     ecx, ecx
0x180007ecb  lea     rdx, [rbp+var_30]
0x180007ecf  mov     rax, rdi
0x180007ed2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ed7  movzx   ecx, byte ptr [rbp+arg_0+4]
0x180007edb  mov     eax, dword ptr [rbp+arg_0]
0x180007ede  mov     [rbx+10h], eax
0x180007ee1  sub     ecx, 1
0x180007ee4  jz      short loc_180007EFC
0x180007ee6  sub     ecx, 1
0x180007ee9  jz      short loc_180007EF6
0x180007eeb  cmp     ecx, 1
0x180007eee  jnz     short loc_180007F00
0x180007ef0  or      dword ptr [rbx+4], 4
0x180007ef4  jmp     short loc_180007F00
0x180007ef6  or      dword ptr [rbx+4], 2
0x180007efa  jmp     short loc_180007F00
0x180007efc  or      dword ptr [rbx+4], 1
0x180007f00  mov     rbx, [rsp+50h+arg_8]
0x180007f05  mov     rdi, [rsp+50h+arg_10]
0x180007f0a  add     rsp, 50h
0x180007f0e  pop     rbp
0x180007f0f  retn
```
