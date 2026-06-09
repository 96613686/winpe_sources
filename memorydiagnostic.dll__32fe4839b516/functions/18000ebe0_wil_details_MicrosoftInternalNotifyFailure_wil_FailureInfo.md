# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x18000ebe0`
- end: `0x18000ecfa`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `282`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000ebe0`
- `0x180024010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000ec6b`
- `KERNEL32!GetModuleHandleW` at `0x18000ec6b`
- `KERNEL32!GetProcAddress` at `0x18000ec8d`
- `KERNEL32!GetProcAddress` at `0x18000ec8d`

## string_xrefs

- `0x18000ec64`: `kernelbase.dll`

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
  ProcAddress = 0;
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
0x18000ebe0  mov     [rsp-8+arg_8], rbx
0x18000ebe5  mov     [rsp-8+arg_10], rsi
0x18000ebea  mov     [rsp-8+arg_18], rdi
0x18000ebef  push    rbp
0x18000ebf0  mov     rbp, rsp
0x18000ebf3  sub     rsp, 50h
0x18000ebf7  mov     rbx, rcx
0x18000ebfa  xor     esi, esi
0x18000ebfc  mov     [rbp+var_2C], esi
0x18000ebff  mov     [rbp+var_1F], sil
0x18000ec03  mov     [rbp+var_1C], esi
0x18000ec06  mov     [rbp+var_16], si
0x18000ec0a  mov     eax, [rcx+8]
0x18000ec0d  mov     [rbp+var_30], eax
0x18000ec10  mov     rax, [rcx+18h]
0x18000ec14  mov     [rbp+var_28], rax
0x18000ec18  mov     al, [rcx]
0x18000ec1a  mov     [rbp+var_20], al
0x18000ec1d  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x18000ec24  mov     [rbp+var_1E], ax
0x18000ec28  movzx   eax, word ptr [rcx+40h]
0x18000ec2c  mov     [rbp+var_18], ax
0x18000ec30  mov     [rbp+var_14], esi
0x18000ec33  mov     rax, [rcx+38h]
0x18000ec37  mov     [rbp+var_10], rax
0x18000ec3b  mov     rax, [rcx+80h]
0x18000ec42  mov     [rbp+var_8], rax
0x18000ec46  mov     [rbp+arg_0], rsi
0x18000ec4a  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x18000ec51  test    rdi, rdi
0x18000ec54  jnz     short loc_18000ECA8
0x18000ec56  mov     edi, esi
0x18000ec58  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000ec5f  test    rax, rax
0x18000ec62  jnz     short loc_18000EC83
0x18000ec64  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000ec6b  call    cs:__imp_GetModuleHandleW
0x18000ec72  nop     dword ptr [rax+rax+00h]
0x18000ec77  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000ec7e  test    rax, rax
0x18000ec81  jz      short loc_18000EC9C
0x18000ec83  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x18000ec8a  mov     rcx, rax; hModule
0x18000ec8d  call    cs:__imp_GetProcAddress
0x18000ec94  nop     dword ptr [rax+rax+00h]
0x18000ec99  mov     rdi, rax
0x18000ec9c  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x18000eca3  test    rdi, rdi
0x18000eca6  jz      short loc_18000ECBB
0x18000eca8  lea     r8, [rbp+arg_0]
0x18000ecac  lea     rdx, [rbp+var_30]
0x18000ecb0  xor     ecx, ecx
0x18000ecb2  mov     rax, rdi
0x18000ecb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ecba  nop
0x18000ecbb  mov     eax, dword ptr [rbp+arg_0]
0x18000ecbe  mov     [rbx+10h], eax
0x18000ecc1  movzx   ecx, byte ptr [rbp+arg_0+4]
0x18000ecc5  sub     ecx, 1
0x18000ecc8  jz      short loc_18000ECE0
0x18000ecca  sub     ecx, 1
0x18000eccd  jz      short loc_18000ECDA
0x18000eccf  cmp     ecx, 1
0x18000ecd2  jnz     short loc_18000ECE4
0x18000ecd4  or      dword ptr [rbx+4], 4
0x18000ecd8  jmp     short loc_18000ECE4
0x18000ecda  or      dword ptr [rbx+4], 2
0x18000ecde  jmp     short loc_18000ECE4
0x18000ece0  or      dword ptr [rbx+4], 1
0x18000ece4  mov     rbx, [rsp+50h+arg_8]
0x18000ece9  mov     rsi, [rsp+50h+arg_10]
0x18000ecee  mov     rdi, [rsp+50h+arg_18]
0x18000ecf3  add     rsp, 50h
0x18000ecf7  pop     rbp
0x18000ecf8  retn
```
