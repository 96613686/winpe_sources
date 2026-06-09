# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180004470`
- end: `0x180004581`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `273`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004470`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004504`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004504`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004520`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004520`

## string_xrefs

- `0x1800044fd`: `kernelbase.dll`

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
0x180004470  mov     [rsp-8+arg_8], rbx
0x180004475  mov     [rsp-8+arg_10], rdi
0x18000447a  push    rbp
0x18000447b  mov     rbp, rsp
0x18000447e  sub     rsp, 50h
0x180004482  mov     rbx, rcx
0x180004485  mov     [rbp+var_2C], 0
0x18000448c  mov     [rbp+var_1F], 0
0x180004490  mov     [rbp+var_1C], 0
0x180004497  xor     eax, eax
0x180004499  mov     [rbp+var_16], ax
0x18000449d  mov     eax, [rcx+8]
0x1800044a0  mov     [rbp+var_30], eax
0x1800044a3  mov     rax, [rcx+18h]
0x1800044a7  mov     [rbp+var_28], rax
0x1800044ab  mov     al, [rcx]
0x1800044ad  mov     [rbp+var_20], al
0x1800044b0  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x1800044b7  mov     [rbp+var_1E], ax
0x1800044bb  movzx   eax, word ptr [rcx+40h]
0x1800044bf  mov     [rbp+var_18], ax
0x1800044c3  mov     [rbp+var_14], 0
0x1800044ca  mov     rax, [rcx+38h]
0x1800044ce  mov     [rbp+var_10], rax
0x1800044d2  mov     rax, [rcx+80h]
0x1800044d9  mov     [rbp+var_8], rax
0x1800044dd  mov     [rbp+arg_0], 0
0x1800044e5  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x1800044ec  test    rdi, rdi
0x1800044ef  jnz     short loc_180004535
0x1800044f1  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800044f8  test    rax, rax
0x1800044fb  jnz     short loc_180004516
0x1800044fd  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180004504  call    cs:__imp_GetModuleHandleW
0x18000450a  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180004511  test    rax, rax
0x180004514  jz      short loc_180004529
0x180004516  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x18000451d  mov     rcx, rax; hModule
0x180004520  call    cs:__imp_GetProcAddress
0x180004526  mov     rdi, rax
0x180004529  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x180004530  test    rdi, rdi
0x180004533  jz      short loc_180004548
0x180004535  lea     r8, [rbp+arg_0]
0x180004539  lea     rdx, [rbp+var_30]
0x18000453d  xor     ecx, ecx
0x18000453f  mov     rax, rdi
0x180004542  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004547  nop
0x180004548  mov     eax, dword ptr [rbp+arg_0]
0x18000454b  mov     [rbx+10h], eax
0x18000454e  movzx   ecx, byte ptr [rbp+arg_0+4]
0x180004552  sub     ecx, 1
0x180004555  jz      short loc_18000456D
0x180004557  sub     ecx, 1
0x18000455a  jz      short loc_180004567
0x18000455c  cmp     ecx, 1
0x18000455f  jnz     short loc_180004571
0x180004561  or      dword ptr [rbx+4], 4
0x180004565  jmp     short loc_180004571
0x180004567  or      dword ptr [rbx+4], 2
0x18000456b  jmp     short loc_180004571
0x18000456d  or      dword ptr [rbx+4], 1
0x180004571  mov     rbx, [rsp+50h+arg_8]
0x180004576  mov     rdi, [rsp+50h+arg_10]
0x18000457b  add     rsp, 50h
0x18000457f  pop     rbp
0x180004580  retn
```
