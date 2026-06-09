# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180005640`
- end: `0x18000575e`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `286`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005640`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800056f6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800056f6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800056d4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800056d4`

## string_xrefs

- `0x1800056cd`: `kernelbase.dll`

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
0x180005640  mov     [rsp-8+arg_8], rbx
0x180005645  mov     [rsp-8+arg_10], rdi
0x18000564a  push    rbp
0x18000564b  mov     rbp, rsp
0x18000564e  sub     rsp, 50h
0x180005652  mov     rbx, rcx
0x180005655  mov     [rbp+var_2C], 0
0x18000565c  mov     [rbp+var_1F], 0
0x180005660  mov     [rbp+var_1C], 0
0x180005667  xor     eax, eax
0x180005669  mov     [rbp+var_16], ax
0x18000566d  mov     eax, [rcx+8]
0x180005670  mov     [rbp+var_30], eax
0x180005673  mov     rax, [rcx+18h]
0x180005677  mov     [rbp+var_28], rax
0x18000567b  mov     al, [rcx]
0x18000567d  mov     [rbp+var_20], al
0x180005680  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x180005687  mov     [rbp+var_1E], ax
0x18000568b  movzx   eax, word ptr [rcx+40h]
0x18000568f  mov     [rbp+var_18], ax
0x180005693  mov     [rbp+var_14], 0
0x18000569a  mov     rax, [rcx+38h]
0x18000569e  mov     [rbp+var_10], rax
0x1800056a2  mov     rax, [rcx+80h]
0x1800056a9  mov     [rbp+var_8], rax
0x1800056ad  mov     [rbp+arg_0], 0
0x1800056b5  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x1800056bc  test    rdi, rdi
0x1800056bf  jnz     short loc_180005711
0x1800056c1  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800056c8  test    rax, rax
0x1800056cb  jnz     short loc_1800056EC
0x1800056cd  lea     rcx, ModuleName; "kernelbase.dll"
0x1800056d4  call    cs:__imp_GetModuleHandleW
0x1800056db  nop     dword ptr [rax+rax+00h]
0x1800056e0  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800056e7  test    rax, rax
0x1800056ea  jz      short loc_180005705
0x1800056ec  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x1800056f3  mov     rcx, rax; hModule
0x1800056f6  call    cs:__imp_GetProcAddress
0x1800056fd  nop     dword ptr [rax+rax+00h]
0x180005702  mov     rdi, rax
0x180005705  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x18000570c  test    rdi, rdi
0x18000570f  jz      short loc_180005724
0x180005711  lea     r8, [rbp+arg_0]
0x180005715  lea     rdx, [rbp+var_30]
0x180005719  xor     ecx, ecx
0x18000571b  mov     rax, rdi
0x18000571e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005723  nop
0x180005724  mov     eax, dword ptr [rbp+arg_0]
0x180005727  mov     [rbx+10h], eax
0x18000572a  movzx   ecx, byte ptr [rbp+arg_0+4]
0x18000572e  sub     ecx, 1
0x180005731  jz      short loc_180005749
0x180005733  sub     ecx, 1
0x180005736  jz      short loc_180005743
0x180005738  cmp     ecx, 1
0x18000573b  jnz     short loc_18000574D
0x18000573d  or      dword ptr [rbx+4], 4
0x180005741  jmp     short loc_18000574D
0x180005743  or      dword ptr [rbx+4], 2
0x180005747  jmp     short loc_18000574D
0x180005749  or      dword ptr [rbx+4], 1
0x18000574d  mov     rbx, [rsp+50h+arg_8]
0x180005752  mov     rdi, [rsp+50h+arg_10]
0x180005757  add     rsp, 50h
0x18000575b  pop     rbp
0x18000575c  retn
```
