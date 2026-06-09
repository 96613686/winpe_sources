# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180008220`
- end: `0x18000833e`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `286`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008220`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800082b4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800082b4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800082d6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800082d6`

## string_xrefs

- `0x1800082ad`: `kernelbase.dll`

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
0x180008220  mov     [rsp-8+arg_8], rbx
0x180008225  mov     [rsp-8+arg_10], rdi
0x18000822a  push    rbp
0x18000822b  mov     rbp, rsp
0x18000822e  sub     rsp, 50h
0x180008232  mov     rbx, rcx
0x180008235  mov     [rbp+var_2C], 0
0x18000823c  mov     [rbp+var_1F], 0
0x180008240  mov     [rbp+var_1C], 0
0x180008247  xor     eax, eax
0x180008249  mov     [rbp+var_16], ax
0x18000824d  mov     eax, [rcx+8]
0x180008250  mov     [rbp+var_30], eax
0x180008253  mov     rax, [rcx+18h]
0x180008257  mov     [rbp+var_28], rax
0x18000825b  mov     al, [rcx]
0x18000825d  mov     [rbp+var_20], al
0x180008260  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x180008267  mov     [rbp+var_1E], ax
0x18000826b  movzx   eax, word ptr [rcx+40h]
0x18000826f  mov     [rbp+var_18], ax
0x180008273  mov     [rbp+var_14], 0
0x18000827a  mov     rax, [rcx+38h]
0x18000827e  mov     [rbp+var_10], rax
0x180008282  mov     rax, [rcx+80h]
0x180008289  mov     [rbp+var_8], rax
0x18000828d  mov     [rbp+arg_0], 0
0x180008295  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x18000829c  test    rdi, rdi
0x18000829f  jnz     short loc_1800082F1
0x1800082a1  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800082a8  test    rax, rax
0x1800082ab  jnz     short loc_1800082CC
0x1800082ad  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800082b4  call    cs:__imp_GetModuleHandleW
0x1800082bb  nop     dword ptr [rax+rax+00h]
0x1800082c0  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800082c7  test    rax, rax
0x1800082ca  jz      short loc_1800082E5
0x1800082cc  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x1800082d3  mov     rcx, rax; hModule
0x1800082d6  call    cs:__imp_GetProcAddress
0x1800082dd  nop     dword ptr [rax+rax+00h]
0x1800082e2  mov     rdi, rax
0x1800082e5  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x1800082ec  test    rdi, rdi
0x1800082ef  jz      short loc_180008304
0x1800082f1  lea     r8, [rbp+arg_0]
0x1800082f5  lea     rdx, [rbp+var_30]
0x1800082f9  xor     ecx, ecx
0x1800082fb  mov     rax, rdi
0x1800082fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008303  nop
0x180008304  mov     eax, dword ptr [rbp+arg_0]
0x180008307  mov     [rbx+10h], eax
0x18000830a  movzx   ecx, byte ptr [rbp+arg_0+4]
0x18000830e  sub     ecx, 1
0x180008311  jz      short loc_180008329
0x180008313  sub     ecx, 1
0x180008316  jz      short loc_180008323
0x180008318  cmp     ecx, 1
0x18000831b  jnz     short loc_18000832D
0x18000831d  or      dword ptr [rbx+4], 4
0x180008321  jmp     short loc_18000832D
0x180008323  or      dword ptr [rbx+4], 2
0x180008327  jmp     short loc_18000832D
0x180008329  or      dword ptr [rbx+4], 1
0x18000832d  mov     rbx, [rsp+50h+arg_8]
0x180008332  mov     rdi, [rsp+50h+arg_10]
0x180008337  add     rsp, 50h
0x18000833b  pop     rbp
0x18000833c  retn
```
