# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x140004580`
- end: `0x14000469e`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `286`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140004580`
- `0x14000a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140004614`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140004614`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140004636`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140004636`

## string_xrefs

- `0x14000460d`: `kernelbase.dll`

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
0x140004580  mov     [rsp-8+arg_8], rbx
0x140004585  mov     [rsp-8+arg_10], rdi
0x14000458a  push    rbp
0x14000458b  mov     rbp, rsp
0x14000458e  sub     rsp, 50h
0x140004592  mov     rbx, rcx
0x140004595  mov     [rbp+var_2C], 0
0x14000459c  mov     [rbp+var_1F], 0
0x1400045a0  mov     [rbp+var_1C], 0
0x1400045a7  xor     eax, eax
0x1400045a9  mov     [rbp+var_16], ax
0x1400045ad  mov     eax, [rcx+8]
0x1400045b0  mov     [rbp+var_30], eax
0x1400045b3  mov     rax, [rcx+18h]
0x1400045b7  mov     [rbp+var_28], rax
0x1400045bb  mov     al, [rcx]
0x1400045bd  mov     [rbp+var_20], al
0x1400045c0  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x1400045c7  mov     [rbp+var_1E], ax
0x1400045cb  movzx   eax, word ptr [rcx+40h]
0x1400045cf  mov     [rbp+var_18], ax
0x1400045d3  mov     [rbp+var_14], 0
0x1400045da  mov     rax, [rcx+38h]
0x1400045de  mov     [rbp+var_10], rax
0x1400045e2  mov     rax, [rcx+80h]
0x1400045e9  mov     [rbp+var_8], rax
0x1400045ed  mov     [rbp+arg_0], 0
0x1400045f5  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x1400045fc  test    rdi, rdi
0x1400045ff  jnz     short loc_140004651
0x140004601  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140004608  test    rax, rax
0x14000460b  jnz     short loc_14000462C
0x14000460d  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x140004614  call    cs:__imp_GetModuleHandleW
0x14000461b  nop     dword ptr [rax+rax+00h]
0x140004620  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140004627  test    rax, rax
0x14000462a  jz      short loc_140004645
0x14000462c  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x140004633  mov     rcx, rax; hModule
0x140004636  call    cs:__imp_GetProcAddress
0x14000463d  nop     dword ptr [rax+rax+00h]
0x140004642  mov     rdi, rax
0x140004645  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x14000464c  test    rdi, rdi
0x14000464f  jz      short loc_140004664
0x140004651  lea     r8, [rbp+arg_0]
0x140004655  lea     rdx, [rbp+var_30]
0x140004659  xor     ecx, ecx
0x14000465b  mov     rax, rdi
0x14000465e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004663  nop
0x140004664  mov     eax, dword ptr [rbp+arg_0]
0x140004667  mov     [rbx+10h], eax
0x14000466a  movzx   ecx, byte ptr [rbp+arg_0+4]
0x14000466e  sub     ecx, 1
0x140004671  jz      short loc_140004689
0x140004673  sub     ecx, 1
0x140004676  jz      short loc_140004683
0x140004678  cmp     ecx, 1
0x14000467b  jnz     short loc_14000468D
0x14000467d  or      dword ptr [rbx+4], 4
0x140004681  jmp     short loc_14000468D
0x140004683  or      dword ptr [rbx+4], 2
0x140004687  jmp     short loc_14000468D
0x140004689  or      dword ptr [rbx+4], 1
0x14000468d  mov     rbx, [rsp+50h+arg_8]
0x140004692  mov     rdi, [rsp+50h+arg_10]
0x140004697  add     rsp, 50h
0x14000469b  pop     rbp
0x14000469c  retn
```
