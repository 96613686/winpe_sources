# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180005110`
- end: `0x180005246`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `310`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001540`
- `0x180005110`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800051d7`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800051d7`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x1800051bb`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x1800051bb`

## string_xrefs

- `0x1800051b4`: `kernelbase.dll`

## pseudocode

```c
void __fastcall wil::details::MicrosoftInternalNotifyFailure(wil::details *this, struct wil::FailureInfo *a2)
{
  FARPROC ProcAddress; // rdi
  HMODULE ModuleHandleW; // rax
  _DWORD v5[2]; // [rsp+28h] [rbp-48h] BYREF
  __int64 v6; // [rsp+30h] [rbp-40h]
  char v7; // [rsp+38h] [rbp-38h]
  char v8; // [rsp+39h] [rbp-37h]
  __int16 v9; // [rsp+3Ah] [rbp-36h]
  int v10; // [rsp+3Ch] [rbp-34h]
  __int16 v11; // [rsp+40h] [rbp-30h]
  __int16 v12; // [rsp+42h] [rbp-2Eh]
  int v13; // [rsp+44h] [rbp-2Ch]
  __int64 v14; // [rsp+48h] [rbp-28h]
  __int64 v15; // [rsp+50h] [rbp-20h]
  __int64 v16; // [rsp+58h] [rbp-18h] BYREF

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
0x180005110  mov     rax, rsp
0x180005113  push    rbp
0x180005114  mov     rbp, rsp
0x180005117  sub     rsp, 70h
0x18000511b  mov     [rbp+var_50], 0FFFFFFFFFFFFFFFEh
0x180005123  mov     [rax+10h], rbx
0x180005127  mov     [rax+18h], rdi
0x18000512b  mov     rax, cs:__security_cookie
0x180005132  xor     rax, rsp
0x180005135  mov     [rbp+var_10], rax
0x180005139  mov     rbx, rcx
0x18000513c  mov     [rbp+var_44], 0
0x180005143  mov     [rbp+var_37], 0
0x180005147  mov     [rbp+var_34], 0
0x18000514e  xor     eax, eax
0x180005150  mov     [rbp+var_2E], ax
0x180005154  mov     eax, [rcx+8]
0x180005157  mov     [rbp+var_48], eax
0x18000515a  mov     rax, [rcx+18h]
0x18000515e  mov     [rbp+var_40], rax
0x180005162  mov     al, [rcx]
0x180005164  mov     [rbp+var_38], al
0x180005167  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x18000516e  mov     [rbp+var_36], ax
0x180005172  movzx   eax, word ptr [rcx+40h]
0x180005176  mov     [rbp+var_30], ax
0x18000517a  mov     [rbp+var_2C], 0
0x180005181  mov     rax, [rcx+38h]
0x180005185  mov     [rbp+var_28], rax
0x180005189  mov     rax, [rcx+80h]
0x180005190  mov     [rbp+var_20], rax
0x180005194  mov     [rbp+var_18], 0
0x18000519c  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x1800051a3  test    rdi, rdi
0x1800051a6  jnz     short loc_1800051EC
0x1800051a8  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800051af  test    rax, rax
0x1800051b2  jnz     short loc_1800051CD
0x1800051b4  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800051bb  call    cs:__imp_GetModuleHandleW
0x1800051c1  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800051c8  test    rax, rax
0x1800051cb  jz      short loc_1800051E0
0x1800051cd  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x1800051d4  mov     rcx, rax; hModule
0x1800051d7  call    cs:__imp_GetProcAddress
0x1800051dd  mov     rdi, rax
0x1800051e0  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x1800051e7  test    rdi, rdi
0x1800051ea  jz      short loc_1800051FF
0x1800051ec  lea     r8, [rbp+var_18]
0x1800051f0  lea     rdx, [rbp+var_48]
0x1800051f4  xor     ecx, ecx
0x1800051f6  mov     rax, rdi
0x1800051f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051fe  nop
0x1800051ff  mov     eax, dword ptr [rbp+var_18]
0x180005202  mov     [rbx+10h], eax
0x180005205  movzx   ecx, byte ptr [rbp+var_18+4]
0x180005209  sub     ecx, 1
0x18000520c  jz      short loc_180005224
0x18000520e  sub     ecx, 1
0x180005211  jz      short loc_18000521E
0x180005213  cmp     ecx, 1
0x180005216  jnz     short loc_180005228
0x180005218  or      dword ptr [rbx+4], 4
0x18000521c  jmp     short loc_180005228
0x18000521e  or      dword ptr [rbx+4], 2
0x180005222  jmp     short loc_180005228
0x180005224  or      dword ptr [rbx+4], 1
0x180005228  mov     rcx, [rbp+var_10]
0x18000522c  xor     rcx, rsp; StackCookie
0x18000522f  call    __security_check_cookie
0x180005234  lea     r11, [rsp+70h+var_s0]
0x180005239  mov     rbx, [r11+18h]
0x18000523d  mov     rdi, [r11+20h]
0x180005241  mov     rsp, r11
0x180005244  pop     rbp
0x180005245  retn
```
