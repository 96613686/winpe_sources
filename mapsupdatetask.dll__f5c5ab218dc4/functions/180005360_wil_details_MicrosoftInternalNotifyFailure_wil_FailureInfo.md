# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180005360`
- end: `0x180005471`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `273`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005360`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005410`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005410`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800053f4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800053f4`

## string_xrefs

- `0x1800053ed`: `kernelbase.dll`

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
0x180005360  mov     [rsp-8+arg_8], rbx
0x180005365  mov     [rsp-8+arg_10], rdi
0x18000536a  push    rbp
0x18000536b  mov     rbp, rsp
0x18000536e  sub     rsp, 50h
0x180005372  mov     rbx, rcx
0x180005375  mov     [rbp+var_2C], 0
0x18000537c  mov     [rbp+var_1F], 0
0x180005380  mov     [rbp+var_1C], 0
0x180005387  xor     eax, eax
0x180005389  mov     [rbp+var_16], ax
0x18000538d  mov     eax, [rcx+8]
0x180005390  mov     [rbp+var_30], eax
0x180005393  mov     rax, [rcx+18h]
0x180005397  mov     [rbp+var_28], rax
0x18000539b  mov     al, [rcx]
0x18000539d  mov     [rbp+var_20], al
0x1800053a0  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x1800053a7  mov     [rbp+var_1E], ax
0x1800053ab  movzx   eax, word ptr [rcx+40h]
0x1800053af  mov     [rbp+var_18], ax
0x1800053b3  mov     [rbp+var_14], 0
0x1800053ba  mov     rax, [rcx+38h]
0x1800053be  mov     [rbp+var_10], rax
0x1800053c2  mov     rax, [rcx+80h]
0x1800053c9  mov     [rbp+var_8], rax
0x1800053cd  mov     [rbp+arg_0], 0
0x1800053d5  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x1800053dc  test    rdi, rdi
0x1800053df  jnz     short loc_180005425
0x1800053e1  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800053e8  test    rax, rax
0x1800053eb  jnz     short loc_180005406
0x1800053ed  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800053f4  call    cs:__imp_GetModuleHandleW
0x1800053fa  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180005401  test    rax, rax
0x180005404  jz      short loc_180005419
0x180005406  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x18000540d  mov     rcx, rax; hModule
0x180005410  call    cs:__imp_GetProcAddress
0x180005416  mov     rdi, rax
0x180005419  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x180005420  test    rdi, rdi
0x180005423  jz      short loc_180005438
0x180005425  lea     r8, [rbp+arg_0]
0x180005429  lea     rdx, [rbp+var_30]
0x18000542d  xor     ecx, ecx
0x18000542f  mov     rax, rdi
0x180005432  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005437  nop
0x180005438  mov     eax, dword ptr [rbp+arg_0]
0x18000543b  mov     [rbx+10h], eax
0x18000543e  movzx   ecx, byte ptr [rbp+arg_0+4]
0x180005442  sub     ecx, 1
0x180005445  jz      short loc_18000545D
0x180005447  sub     ecx, 1
0x18000544a  jz      short loc_180005457
0x18000544c  cmp     ecx, 1
0x18000544f  jnz     short loc_180005461
0x180005451  or      dword ptr [rbx+4], 4
0x180005455  jmp     short loc_180005461
0x180005457  or      dword ptr [rbx+4], 2
0x18000545b  jmp     short loc_180005461
0x18000545d  or      dword ptr [rbx+4], 1
0x180005461  mov     rbx, [rsp+50h+arg_8]
0x180005466  mov     rdi, [rsp+50h+arg_10]
0x18000546b  add     rsp, 50h
0x18000546f  pop     rbp
0x180005470  retn
```
