# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x140015250`
- end: `0x140015360`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `272`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140015250`
- `0x140019010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140015300`
- `KERNEL32!GetProcAddress` at `0x140015300`
- `KERNEL32!GetModuleHandleW` at `0x1400152e4`
- `KERNEL32!GetModuleHandleW` at `0x1400152e4`

## string_xrefs

- `0x1400152dd`: `kernelbase.dll`

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
0x140015250  mov     [rsp-8+arg_8], rbx
0x140015255  mov     [rsp-8+arg_10], rdi
0x14001525a  push    rbp
0x14001525b  mov     rbp, rsp
0x14001525e  sub     rsp, 50h
0x140015262  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x140015269  xor     eax, eax
0x14001526b  mov     [rbp+var_16], ax
0x14001526f  mov     rbx, rcx
0x140015272  mov     eax, [rcx+8]
0x140015275  mov     [rbp+var_30], eax
0x140015278  mov     rax, [rcx+18h]
0x14001527c  mov     [rbp+var_28], rax
0x140015280  mov     al, [rcx]
0x140015282  mov     [rbp+var_20], al
0x140015285  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x14001528c  mov     [rbp+var_1E], ax
0x140015290  movzx   eax, word ptr [rcx+40h]
0x140015294  mov     [rbp+var_18], ax
0x140015298  mov     rax, [rcx+38h]
0x14001529c  mov     [rbp+var_10], rax
0x1400152a0  mov     rax, [rcx+80h]
0x1400152a7  mov     [rbp+var_8], rax
0x1400152ab  mov     [rbp+var_2C], 0
0x1400152b2  mov     [rbp+var_1F], 0
0x1400152b6  mov     [rbp+var_1C], 0
0x1400152bd  mov     [rbp+var_14], 0
0x1400152c4  mov     [rbp+arg_0], 0
0x1400152cc  test    rdi, rdi
0x1400152cf  jnz     short loc_140015315
0x1400152d1  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1400152d8  test    rax, rax
0x1400152db  jnz     short loc_1400152F6
0x1400152dd  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1400152e4  call    cs:__imp_GetModuleHandleW
0x1400152ea  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1400152f1  test    rax, rax
0x1400152f4  jz      short loc_140015309
0x1400152f6  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x1400152fd  mov     rcx, rax; hModule
0x140015300  call    cs:__imp_GetProcAddress
0x140015306  mov     rdi, rax
0x140015309  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x140015310  test    rdi, rdi
0x140015313  jz      short loc_140015327
0x140015315  lea     r8, [rbp+arg_0]
0x140015319  xor     ecx, ecx
0x14001531b  lea     rdx, [rbp+var_30]
0x14001531f  mov     rax, rdi
0x140015322  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015327  movzx   ecx, byte ptr [rbp+arg_0+4]
0x14001532b  mov     eax, dword ptr [rbp+arg_0]
0x14001532e  mov     [rbx+10h], eax
0x140015331  sub     ecx, 1
0x140015334  jz      short loc_14001534C
0x140015336  sub     ecx, 1
0x140015339  jz      short loc_140015346
0x14001533b  cmp     ecx, 1
0x14001533e  jnz     short loc_140015350
0x140015340  or      dword ptr [rbx+4], 4
0x140015344  jmp     short loc_140015350
0x140015346  or      dword ptr [rbx+4], 2
0x14001534a  jmp     short loc_140015350
0x14001534c  or      dword ptr [rbx+4], 1
0x140015350  mov     rbx, [rsp+50h+arg_8]
0x140015355  mov     rdi, [rsp+50h+arg_10]
0x14001535a  add     rsp, 50h
0x14001535e  pop     rbp
0x14001535f  retn
```
