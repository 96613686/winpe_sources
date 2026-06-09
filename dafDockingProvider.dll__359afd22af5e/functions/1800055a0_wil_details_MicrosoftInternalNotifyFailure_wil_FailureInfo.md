# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x1800055a0`
- end: `0x1800056b1`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `273`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800055a0`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005650`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005650`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005634`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005634`

## string_xrefs

- `0x18000562d`: `kernelbase.dll`

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
0x1800055a0  mov     [rsp-8+arg_8], rbx
0x1800055a5  mov     [rsp-8+arg_10], rdi
0x1800055aa  push    rbp
0x1800055ab  mov     rbp, rsp
0x1800055ae  sub     rsp, 50h
0x1800055b2  mov     rbx, rcx
0x1800055b5  mov     [rbp+var_2C], 0
0x1800055bc  mov     [rbp+var_1F], 0
0x1800055c0  mov     [rbp+var_1C], 0
0x1800055c7  xor     eax, eax
0x1800055c9  mov     [rbp+var_16], ax
0x1800055cd  mov     eax, [rcx+8]
0x1800055d0  mov     [rbp+var_30], eax
0x1800055d3  mov     rax, [rcx+18h]
0x1800055d7  mov     [rbp+var_28], rax
0x1800055db  mov     al, [rcx]
0x1800055dd  mov     [rbp+var_20], al
0x1800055e0  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x1800055e7  mov     [rbp+var_1E], ax
0x1800055eb  movzx   eax, word ptr [rcx+40h]
0x1800055ef  mov     [rbp+var_18], ax
0x1800055f3  mov     [rbp+var_14], 0
0x1800055fa  mov     rax, [rcx+38h]
0x1800055fe  mov     [rbp+var_10], rax
0x180005602  mov     rax, [rcx+80h]
0x180005609  mov     [rbp+var_8], rax
0x18000560d  mov     [rbp+arg_0], 0
0x180005615  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x18000561c  test    rdi, rdi
0x18000561f  jnz     short loc_180005665
0x180005621  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180005628  test    rax, rax
0x18000562b  jnz     short loc_180005646
0x18000562d  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180005634  call    cs:__imp_GetModuleHandleW
0x18000563a  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180005641  test    rax, rax
0x180005644  jz      short loc_180005659
0x180005646  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x18000564d  mov     rcx, rax; hModule
0x180005650  call    cs:__imp_GetProcAddress
0x180005656  mov     rdi, rax
0x180005659  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x180005660  test    rdi, rdi
0x180005663  jz      short loc_180005678
0x180005665  lea     r8, [rbp+arg_0]
0x180005669  lea     rdx, [rbp+var_30]
0x18000566d  xor     ecx, ecx
0x18000566f  mov     rax, rdi
0x180005672  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005677  nop
0x180005678  mov     eax, dword ptr [rbp+arg_0]
0x18000567b  mov     [rbx+10h], eax
0x18000567e  movzx   ecx, byte ptr [rbp+arg_0+4]
0x180005682  sub     ecx, 1
0x180005685  jz      short loc_18000569D
0x180005687  sub     ecx, 1
0x18000568a  jz      short loc_180005697
0x18000568c  cmp     ecx, 1
0x18000568f  jnz     short loc_1800056A1
0x180005691  or      dword ptr [rbx+4], 4
0x180005695  jmp     short loc_1800056A1
0x180005697  or      dword ptr [rbx+4], 2
0x18000569b  jmp     short loc_1800056A1
0x18000569d  or      dword ptr [rbx+4], 1
0x1800056a1  mov     rbx, [rsp+50h+arg_8]
0x1800056a6  mov     rdi, [rsp+50h+arg_10]
0x1800056ab  add     rsp, 50h
0x1800056af  pop     rbp
0x1800056b0  retn
```
