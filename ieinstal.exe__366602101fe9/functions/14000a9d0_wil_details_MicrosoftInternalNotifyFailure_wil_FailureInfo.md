# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x14000a9d0`
- end: `0x14000aaed`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `285`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000a9d0`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000aa86`
- `KERNEL32!GetProcAddress` at `0x14000aa86`
- `KERNEL32!GetModuleHandleW` at `0x14000aa64`
- `KERNEL32!GetModuleHandleW` at `0x14000aa64`

## string_xrefs

- `0x14000aa5d`: `kernelbase.dll`

## pseudocode

```c
void __fastcall wil::details::MicrosoftInternalNotifyFailure(wil::details *this, struct wil::FailureInfo *a2)
{
  FARPROC ProcAddress; // rdi
  HMODULE ModuleHandleW; // rax
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  _DWORD v8[2]; // [rsp+20h] [rbp-30h] BYREF
  __int64 v9; // [rsp+28h] [rbp-28h]
  char v10; // [rsp+30h] [rbp-20h]
  char v11; // [rsp+31h] [rbp-1Fh]
  __int16 v12; // [rsp+32h] [rbp-1Eh]
  int v13; // [rsp+34h] [rbp-1Ch]
  __int16 v14; // [rsp+38h] [rbp-18h]
  __int16 v15; // [rsp+3Ah] [rbp-16h]
  int v16; // [rsp+3Ch] [rbp-14h]
  __int64 v17; // [rsp+40h] [rbp-10h]
  __int64 v18; // [rsp+48h] [rbp-8h]
  __int64 v19; // [rsp+60h] [rbp+10h] BYREF

  ProcAddress = (FARPROC)`wil::details::WilFailureNotifyWatchers'::`2'::s_pfnFailureNotifyWatchers;
  v15 = 0;
  v8[0] = *((_DWORD *)this + 2);
  v9 = *((_QWORD *)this + 3);
  v10 = *(_BYTE *)this;
  v12 = wil::g_moduleFailureReportFlags;
  v14 = *((_WORD *)this + 32);
  v17 = *((_QWORD *)this + 7);
  v18 = *((_QWORD *)this + 16);
  v8[1] = 0;
  v11 = 0;
  v13 = 0;
  v16 = 0;
  v19 = 0;
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
    ((void (__fastcall *)(_QWORD, _DWORD *, __int64 *))ProcAddress)(0, v8, &v19);
  v5 = BYTE4(v19);
  *((_DWORD *)this + 4) = v19;
  v6 = v5 - 1;
  if ( v6 )
  {
    v7 = v6 - 1;
    if ( v7 )
    {
      if ( v7 == 1 )
        *((_DWORD *)this + 1) |= 4u;
    }
    else
    {
      *((_DWORD *)this + 1) |= 2u;
    }
  }
  else
  {
    *((_DWORD *)this + 1) |= 1u;
  }
}

```

## disassembly

```asm
0x14000a9d0  mov     [rsp-8+arg_8], rbx
0x14000a9d5  mov     [rsp-8+arg_10], rdi
0x14000a9da  push    rbp
0x14000a9db  mov     rbp, rsp
0x14000a9de  sub     rsp, 50h
0x14000a9e2  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x14000a9e9  xor     eax, eax
0x14000a9eb  mov     [rbp+var_16], ax
0x14000a9ef  mov     rbx, rcx
0x14000a9f2  mov     eax, [rcx+8]
0x14000a9f5  mov     [rbp+var_30], eax
0x14000a9f8  mov     rax, [rcx+18h]
0x14000a9fc  mov     [rbp+var_28], rax
0x14000aa00  mov     al, [rcx]
0x14000aa02  mov     [rbp+var_20], al
0x14000aa05  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x14000aa0c  mov     [rbp+var_1E], ax
0x14000aa10  movzx   eax, word ptr [rcx+40h]
0x14000aa14  mov     [rbp+var_18], ax
0x14000aa18  mov     rax, [rcx+38h]
0x14000aa1c  mov     [rbp+var_10], rax
0x14000aa20  mov     rax, [rcx+80h]
0x14000aa27  mov     [rbp+var_8], rax
0x14000aa2b  mov     [rbp+var_2C], 0
0x14000aa32  mov     [rbp+var_1F], 0
0x14000aa36  mov     [rbp+var_1C], 0
0x14000aa3d  mov     [rbp+var_14], 0
0x14000aa44  mov     [rbp+arg_0], 0
0x14000aa4c  test    rdi, rdi
0x14000aa4f  jnz     short loc_14000AAA1
0x14000aa51  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x14000aa58  test    rax, rax
0x14000aa5b  jnz     short loc_14000AA7C
0x14000aa5d  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000aa64  call    cs:__imp_GetModuleHandleW
0x14000aa6b  nop     dword ptr [rax+rax+00h]
0x14000aa70  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x14000aa77  test    rax, rax
0x14000aa7a  jz      short loc_14000AA95
0x14000aa7c  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x14000aa83  mov     rcx, rax; hModule
0x14000aa86  call    cs:__imp_GetProcAddress
0x14000aa8d  nop     dword ptr [rax+rax+00h]
0x14000aa92  mov     rdi, rax
0x14000aa95  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x14000aa9c  test    rdi, rdi
0x14000aa9f  jz      short loc_14000AAB3
0x14000aaa1  lea     r8, [rbp+arg_0]
0x14000aaa5  xor     ecx, ecx
0x14000aaa7  lea     rdx, [rbp+var_30]
0x14000aaab  mov     rax, rdi
0x14000aaae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aab3  movzx   ecx, byte ptr [rbp+arg_0+4]
0x14000aab7  mov     eax, dword ptr [rbp+arg_0]
0x14000aaba  mov     [rbx+10h], eax
0x14000aabd  sub     ecx, 1
0x14000aac0  jz      short loc_14000AAD8
0x14000aac2  sub     ecx, 1
0x14000aac5  jz      short loc_14000AAD2
0x14000aac7  cmp     ecx, 1
0x14000aaca  jnz     short loc_14000AADC
0x14000aacc  or      dword ptr [rbx+4], 4
0x14000aad0  jmp     short loc_14000AADC
0x14000aad2  or      dword ptr [rbx+4], 2
0x14000aad6  jmp     short loc_14000AADC
0x14000aad8  or      dword ptr [rbx+4], 1
0x14000aadc  mov     rbx, [rsp+50h+arg_8]
0x14000aae1  mov     rdi, [rsp+50h+arg_10]
0x14000aae6  add     rsp, 50h
0x14000aaea  pop     rbp
0x14000aaeb  retn
```
