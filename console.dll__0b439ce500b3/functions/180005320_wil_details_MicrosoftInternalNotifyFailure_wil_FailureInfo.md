# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180005320`
- end: `0x18000543e`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `286`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005320`
- `0x18001a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800053b4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800053b4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800053d6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800053d6`

## string_xrefs

- `0x1800053ad`: `kernelbase.dll`

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
0x180005320  mov     [rsp-8+arg_8], rbx
0x180005325  mov     [rsp-8+arg_10], rdi
0x18000532a  push    rbp
0x18000532b  mov     rbp, rsp
0x18000532e  sub     rsp, 50h
0x180005332  mov     rbx, rcx
0x180005335  mov     [rbp+var_2C], 0
0x18000533c  mov     [rbp+var_1F], 0
0x180005340  mov     [rbp+var_1C], 0
0x180005347  xor     eax, eax
0x180005349  mov     [rbp+var_16], ax
0x18000534d  mov     eax, [rcx+8]
0x180005350  mov     [rbp+var_30], eax
0x180005353  mov     rax, [rcx+18h]
0x180005357  mov     [rbp+var_28], rax
0x18000535b  mov     al, [rcx]
0x18000535d  mov     [rbp+var_20], al
0x180005360  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x180005367  mov     [rbp+var_1E], ax
0x18000536b  movzx   eax, word ptr [rcx+40h]
0x18000536f  mov     [rbp+var_18], ax
0x180005373  mov     [rbp+var_14], 0
0x18000537a  mov     rax, [rcx+38h]
0x18000537e  mov     [rbp+var_10], rax
0x180005382  mov     rax, [rcx+80h]
0x180005389  mov     [rbp+var_8], rax
0x18000538d  mov     [rbp+arg_0], 0
0x180005395  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x18000539c  test    rdi, rdi
0x18000539f  jnz     short loc_1800053F1
0x1800053a1  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800053a8  test    rax, rax
0x1800053ab  jnz     short loc_1800053CC
0x1800053ad  lea     rcx, ModuleName; "kernelbase.dll"
0x1800053b4  call    cs:__imp_GetModuleHandleW
0x1800053bb  nop     dword ptr [rax+rax+00h]
0x1800053c0  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800053c7  test    rax, rax
0x1800053ca  jz      short loc_1800053E5
0x1800053cc  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x1800053d3  mov     rcx, rax; hModule
0x1800053d6  call    cs:__imp_GetProcAddress
0x1800053dd  nop     dword ptr [rax+rax+00h]
0x1800053e2  mov     rdi, rax
0x1800053e5  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x1800053ec  test    rdi, rdi
0x1800053ef  jz      short loc_180005404
0x1800053f1  lea     r8, [rbp+arg_0]
0x1800053f5  lea     rdx, [rbp+var_30]
0x1800053f9  xor     ecx, ecx
0x1800053fb  mov     rax, rdi
0x1800053fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005403  nop
0x180005404  mov     eax, dword ptr [rbp+arg_0]
0x180005407  mov     [rbx+10h], eax
0x18000540a  movzx   ecx, byte ptr [rbp+arg_0+4]
0x18000540e  sub     ecx, 1
0x180005411  jz      short loc_180005429
0x180005413  sub     ecx, 1
0x180005416  jz      short loc_180005423
0x180005418  cmp     ecx, 1
0x18000541b  jnz     short loc_18000542D
0x18000541d  or      dword ptr [rbx+4], 4
0x180005421  jmp     short loc_18000542D
0x180005423  or      dword ptr [rbx+4], 2
0x180005427  jmp     short loc_18000542D
0x180005429  or      dword ptr [rbx+4], 1
0x18000542d  mov     rbx, [rsp+50h+arg_8]
0x180005432  mov     rdi, [rsp+50h+arg_10]
0x180005437  add     rsp, 50h
0x18000543b  pop     rbp
0x18000543c  retn
```
