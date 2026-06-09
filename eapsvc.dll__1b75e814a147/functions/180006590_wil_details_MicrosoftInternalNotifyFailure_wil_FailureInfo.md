# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180006590`
- end: `0x1800066a1`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `273`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006590`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006640`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006640`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006624`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006624`

## string_xrefs

- `0x18000661d`: `kernelbase.dll`

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
0x180006590  mov     [rsp-8+arg_8], rbx
0x180006595  mov     [rsp-8+arg_10], rdi
0x18000659a  push    rbp
0x18000659b  mov     rbp, rsp
0x18000659e  sub     rsp, 50h
0x1800065a2  mov     rbx, rcx
0x1800065a5  mov     [rbp+var_2C], 0
0x1800065ac  mov     [rbp+var_1F], 0
0x1800065b0  mov     [rbp+var_1C], 0
0x1800065b7  xor     eax, eax
0x1800065b9  mov     [rbp+var_16], ax
0x1800065bd  mov     eax, [rcx+8]
0x1800065c0  mov     [rbp+var_30], eax
0x1800065c3  mov     rax, [rcx+18h]
0x1800065c7  mov     [rbp+var_28], rax
0x1800065cb  mov     al, [rcx]
0x1800065cd  mov     [rbp+var_20], al
0x1800065d0  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x1800065d7  mov     [rbp+var_1E], ax
0x1800065db  movzx   eax, word ptr [rcx+40h]
0x1800065df  mov     [rbp+var_18], ax
0x1800065e3  mov     [rbp+var_14], 0
0x1800065ea  mov     rax, [rcx+38h]
0x1800065ee  mov     [rbp+var_10], rax
0x1800065f2  mov     rax, [rcx+80h]
0x1800065f9  mov     [rbp+var_8], rax
0x1800065fd  mov     [rbp+arg_0], 0
0x180006605  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x18000660c  test    rdi, rdi
0x18000660f  jnz     short loc_180006655
0x180006611  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180006618  test    rax, rax
0x18000661b  jnz     short loc_180006636
0x18000661d  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180006624  call    cs:__imp_GetModuleHandleW
0x18000662a  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180006631  test    rax, rax
0x180006634  jz      short loc_180006649
0x180006636  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x18000663d  mov     rcx, rax; hModule
0x180006640  call    cs:__imp_GetProcAddress
0x180006646  mov     rdi, rax
0x180006649  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x180006650  test    rdi, rdi
0x180006653  jz      short loc_180006668
0x180006655  lea     r8, [rbp+arg_0]
0x180006659  lea     rdx, [rbp+var_30]
0x18000665d  xor     ecx, ecx
0x18000665f  mov     rax, rdi
0x180006662  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006667  nop
0x180006668  mov     eax, dword ptr [rbp+arg_0]
0x18000666b  mov     [rbx+10h], eax
0x18000666e  movzx   ecx, byte ptr [rbp+arg_0+4]
0x180006672  sub     ecx, 1
0x180006675  jz      short loc_18000668D
0x180006677  sub     ecx, 1
0x18000667a  jz      short loc_180006687
0x18000667c  cmp     ecx, 1
0x18000667f  jnz     short loc_180006691
0x180006681  or      dword ptr [rbx+4], 4
0x180006685  jmp     short loc_180006691
0x180006687  or      dword ptr [rbx+4], 2
0x18000668b  jmp     short loc_180006691
0x18000668d  or      dword ptr [rbx+4], 1
0x180006691  mov     rbx, [rsp+50h+arg_8]
0x180006696  mov     rdi, [rsp+50h+arg_10]
0x18000669b  add     rsp, 50h
0x18000669f  pop     rbp
0x1800066a0  retn
```
