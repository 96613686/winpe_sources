# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180006300`
- end: `0x180006410`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `272`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006300`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006394`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006394`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800063b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800063b0`

## string_xrefs

- `0x18000638d`: `kernelbase.dll`

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
0x180006300  mov     [rsp-8+arg_8], rbx
0x180006305  mov     [rsp-8+arg_10], rdi
0x18000630a  push    rbp
0x18000630b  mov     rbp, rsp
0x18000630e  sub     rsp, 50h
0x180006312  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x180006319  xor     eax, eax
0x18000631b  mov     [rbp+var_16], ax
0x18000631f  mov     rbx, rcx
0x180006322  mov     eax, [rcx+8]
0x180006325  mov     [rbp+var_30], eax
0x180006328  mov     rax, [rcx+18h]
0x18000632c  mov     [rbp+var_28], rax
0x180006330  mov     al, [rcx]
0x180006332  mov     [rbp+var_20], al
0x180006335  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x18000633c  mov     [rbp+var_1E], ax
0x180006340  movzx   eax, word ptr [rcx+40h]
0x180006344  mov     [rbp+var_18], ax
0x180006348  mov     rax, [rcx+38h]
0x18000634c  mov     [rbp+var_10], rax
0x180006350  mov     rax, [rcx+80h]
0x180006357  mov     [rbp+var_8], rax
0x18000635b  mov     [rbp+var_2C], 0
0x180006362  mov     [rbp+var_1F], 0
0x180006366  mov     [rbp+var_1C], 0
0x18000636d  mov     [rbp+var_14], 0
0x180006374  mov     [rbp+arg_0], 0
0x18000637c  test    rdi, rdi
0x18000637f  jnz     short loc_1800063C5
0x180006381  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180006388  test    rax, rax
0x18000638b  jnz     short loc_1800063A6
0x18000638d  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180006394  call    cs:__imp_GetModuleHandleW
0x18000639a  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800063a1  test    rax, rax
0x1800063a4  jz      short loc_1800063B9
0x1800063a6  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x1800063ad  mov     rcx, rax; hModule
0x1800063b0  call    cs:__imp_GetProcAddress
0x1800063b6  mov     rdi, rax
0x1800063b9  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x1800063c0  test    rdi, rdi
0x1800063c3  jz      short loc_1800063D7
0x1800063c5  lea     r8, [rbp+arg_0]
0x1800063c9  xor     ecx, ecx
0x1800063cb  lea     rdx, [rbp+var_30]
0x1800063cf  mov     rax, rdi
0x1800063d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063d7  movzx   ecx, byte ptr [rbp+arg_0+4]
0x1800063db  mov     eax, dword ptr [rbp+arg_0]
0x1800063de  mov     [rbx+10h], eax
0x1800063e1  sub     ecx, 1
0x1800063e4  jz      short loc_1800063FC
0x1800063e6  sub     ecx, 1
0x1800063e9  jz      short loc_1800063F6
0x1800063eb  cmp     ecx, 1
0x1800063ee  jnz     short loc_180006400
0x1800063f0  or      dword ptr [rbx+4], 4
0x1800063f4  jmp     short loc_180006400
0x1800063f6  or      dword ptr [rbx+4], 2
0x1800063fa  jmp     short loc_180006400
0x1800063fc  or      dword ptr [rbx+4], 1
0x180006400  mov     rbx, [rsp+50h+arg_8]
0x180006405  mov     rdi, [rsp+50h+arg_10]
0x18000640a  add     rsp, 50h
0x18000640e  pop     rbp
0x18000640f  retn
```
