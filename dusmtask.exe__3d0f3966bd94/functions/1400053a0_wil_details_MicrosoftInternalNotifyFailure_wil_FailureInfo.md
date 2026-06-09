# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x1400053a0`
- end: `0x1400054cd`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `301`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001470`
- `0x1400053a0`
- `0x140008010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140005442`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140005442`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000545e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000545e`

## string_xrefs

- `0x14000543b`: `kernelbase.dll`

## pseudocode

```c
void __fastcall wil::details::MicrosoftInternalNotifyFailure(wil::details *this, struct wil::FailureInfo *a2)
{
  FARPROC ProcAddress; // rdi
  HMODULE ModuleHandleW; // rax
  _DWORD v5[2]; // [rsp+20h] [rbp-40h] BYREF
  __int64 v6; // [rsp+28h] [rbp-38h]
  char v7; // [rsp+30h] [rbp-30h]
  char v8; // [rsp+31h] [rbp-2Fh]
  __int16 v9; // [rsp+32h] [rbp-2Eh]
  int v10; // [rsp+34h] [rbp-2Ch]
  __int16 v11; // [rsp+38h] [rbp-28h]
  __int16 v12; // [rsp+3Ah] [rbp-26h]
  int v13; // [rsp+3Ch] [rbp-24h]
  __int64 v14; // [rsp+40h] [rbp-20h]
  __int64 v15; // [rsp+48h] [rbp-18h]
  __int64 v16; // [rsp+50h] [rbp-10h] BYREF

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
0x1400053a0  mov     [rsp-8+arg_8], rbx
0x1400053a5  mov     [rsp-8+arg_10], rdi
0x1400053aa  push    rbp
0x1400053ab  mov     rbp, rsp
0x1400053ae  sub     rsp, 60h
0x1400053b2  mov     rax, cs:__security_cookie
0x1400053b9  xor     rax, rsp
0x1400053bc  mov     [rbp+var_8], rax
0x1400053c0  mov     rbx, rcx
0x1400053c3  mov     [rbp+var_3C], 0
0x1400053ca  mov     [rbp+var_2F], 0
0x1400053ce  mov     [rbp+var_2C], 0
0x1400053d5  xor     eax, eax
0x1400053d7  mov     [rbp+var_26], ax
0x1400053db  mov     eax, [rcx+8]
0x1400053de  mov     [rbp+var_40], eax
0x1400053e1  mov     rax, [rcx+18h]
0x1400053e5  mov     [rbp+var_38], rax
0x1400053e9  mov     al, [rcx]
0x1400053eb  mov     [rbp+var_30], al
0x1400053ee  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x1400053f5  mov     [rbp+var_2E], ax
0x1400053f9  movzx   eax, word ptr [rcx+40h]
0x1400053fd  mov     [rbp+var_28], ax
0x140005401  mov     [rbp+var_24], 0
0x140005408  mov     rax, [rcx+38h]
0x14000540c  mov     [rbp+var_20], rax
0x140005410  mov     rax, [rcx+80h]
0x140005417  mov     [rbp+var_18], rax
0x14000541b  mov     [rbp+var_10], 0
0x140005423  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x14000542a  test    rdi, rdi
0x14000542d  jnz     short loc_140005473
0x14000542f  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140005436  test    rax, rax
0x140005439  jnz     short loc_140005454
0x14000543b  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x140005442  call    cs:__imp_GetModuleHandleW
0x140005448  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x14000544f  test    rax, rax
0x140005452  jz      short loc_140005467
0x140005454  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x14000545b  mov     rcx, rax; hModule
0x14000545e  call    cs:__imp_GetProcAddress
0x140005464  mov     rdi, rax
0x140005467  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x14000546e  test    rdi, rdi
0x140005471  jz      short loc_140005486
0x140005473  lea     r8, [rbp+var_10]
0x140005477  lea     rdx, [rbp+var_40]
0x14000547b  xor     ecx, ecx
0x14000547d  mov     rax, rdi
0x140005480  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005485  nop
0x140005486  mov     eax, dword ptr [rbp+var_10]
0x140005489  mov     [rbx+10h], eax
0x14000548c  movzx   ecx, byte ptr [rbp+var_10+4]
0x140005490  sub     ecx, 1
0x140005493  jz      short loc_1400054AB
0x140005495  sub     ecx, 1
0x140005498  jz      short loc_1400054A5
0x14000549a  cmp     ecx, 1
0x14000549d  jnz     short loc_1400054AF
0x14000549f  or      dword ptr [rbx+4], 4
0x1400054a3  jmp     short loc_1400054AF
0x1400054a5  or      dword ptr [rbx+4], 2
0x1400054a9  jmp     short loc_1400054AF
0x1400054ab  or      dword ptr [rbx+4], 1
0x1400054af  mov     rcx, [rbp+var_8]
0x1400054b3  xor     rcx, rsp; StackCookie
0x1400054b6  call    __security_check_cookie
0x1400054bb  lea     r11, [rsp+60h+var_s0]
0x1400054c0  mov     rbx, [r11+18h]
0x1400054c4  mov     rdi, [r11+20h]
0x1400054c8  mov     rsp, r11
0x1400054cb  pop     rbp
0x1400054cc  retn
```
