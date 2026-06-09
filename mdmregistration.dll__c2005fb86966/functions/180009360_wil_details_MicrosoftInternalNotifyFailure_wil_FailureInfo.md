# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180009360`
- end: `0x18000947e`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `286`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180009360`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800093f4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800093f4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009416`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009416`

## string_xrefs

- `0x1800093ed`: `kernelbase.dll`

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
0x180009360  mov     [rsp-8+arg_8], rbx
0x180009365  mov     [rsp-8+arg_10], rdi
0x18000936a  push    rbp
0x18000936b  mov     rbp, rsp
0x18000936e  sub     rsp, 50h
0x180009372  mov     rbx, rcx
0x180009375  mov     [rbp+var_2C], 0
0x18000937c  mov     [rbp+var_1F], 0
0x180009380  mov     [rbp+var_1C], 0
0x180009387  xor     eax, eax
0x180009389  mov     [rbp+var_16], ax
0x18000938d  mov     eax, [rcx+8]
0x180009390  mov     [rbp+var_30], eax
0x180009393  mov     rax, [rcx+18h]
0x180009397  mov     [rbp+var_28], rax
0x18000939b  mov     al, [rcx]
0x18000939d  mov     [rbp+var_20], al
0x1800093a0  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x1800093a7  mov     [rbp+var_1E], ax
0x1800093ab  movzx   eax, word ptr [rcx+40h]
0x1800093af  mov     [rbp+var_18], ax
0x1800093b3  mov     [rbp+var_14], 0
0x1800093ba  mov     rax, [rcx+38h]
0x1800093be  mov     [rbp+var_10], rax
0x1800093c2  mov     rax, [rcx+80h]
0x1800093c9  mov     [rbp+var_8], rax
0x1800093cd  mov     [rbp+arg_0], 0
0x1800093d5  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x1800093dc  test    rdi, rdi
0x1800093df  jnz     short loc_180009431
0x1800093e1  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800093e8  test    rax, rax
0x1800093eb  jnz     short loc_18000940C
0x1800093ed  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800093f4  call    cs:__imp_GetModuleHandleW
0x1800093fb  nop     dword ptr [rax+rax+00h]
0x180009400  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180009407  test    rax, rax
0x18000940a  jz      short loc_180009425
0x18000940c  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x180009413  mov     rcx, rax; hModule
0x180009416  call    cs:__imp_GetProcAddress
0x18000941d  nop     dword ptr [rax+rax+00h]
0x180009422  mov     rdi, rax
0x180009425  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x18000942c  test    rdi, rdi
0x18000942f  jz      short loc_180009444
0x180009431  lea     r8, [rbp+arg_0]
0x180009435  lea     rdx, [rbp+var_30]
0x180009439  xor     ecx, ecx
0x18000943b  mov     rax, rdi
0x18000943e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009443  nop
0x180009444  mov     eax, dword ptr [rbp+arg_0]
0x180009447  mov     [rbx+10h], eax
0x18000944a  movzx   ecx, byte ptr [rbp+arg_0+4]
0x18000944e  sub     ecx, 1
0x180009451  jz      short loc_180009469
0x180009453  sub     ecx, 1
0x180009456  jz      short loc_180009463
0x180009458  cmp     ecx, 1
0x18000945b  jnz     short loc_18000946D
0x18000945d  or      dword ptr [rbx+4], 4
0x180009461  jmp     short loc_18000946D
0x180009463  or      dword ptr [rbx+4], 2
0x180009467  jmp     short loc_18000946D
0x180009469  or      dword ptr [rbx+4], 1
0x18000946d  mov     rbx, [rsp+50h+arg_8]
0x180009472  mov     rdi, [rsp+50h+arg_10]
0x180009477  add     rsp, 50h
0x18000947b  pop     rbp
0x18000947c  retn
```
