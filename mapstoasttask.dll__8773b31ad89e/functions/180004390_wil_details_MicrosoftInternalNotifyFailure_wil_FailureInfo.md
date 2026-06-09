# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180004390`
- end: `0x1800044a1`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `273`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004390`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004424`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004424`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004440`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004440`

## string_xrefs

- `0x18000441d`: `kernelbase.dll`

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
0x180004390  mov     [rsp-8+arg_8], rbx
0x180004395  mov     [rsp-8+arg_10], rdi
0x18000439a  push    rbp
0x18000439b  mov     rbp, rsp
0x18000439e  sub     rsp, 50h
0x1800043a2  mov     rbx, rcx
0x1800043a5  mov     [rbp+var_2C], 0
0x1800043ac  mov     [rbp+var_1F], 0
0x1800043b0  mov     [rbp+var_1C], 0
0x1800043b7  xor     eax, eax
0x1800043b9  mov     [rbp+var_16], ax
0x1800043bd  mov     eax, [rcx+8]
0x1800043c0  mov     [rbp+var_30], eax
0x1800043c3  mov     rax, [rcx+18h]
0x1800043c7  mov     [rbp+var_28], rax
0x1800043cb  mov     al, [rcx]
0x1800043cd  mov     [rbp+var_20], al
0x1800043d0  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x1800043d7  mov     [rbp+var_1E], ax
0x1800043db  movzx   eax, word ptr [rcx+40h]
0x1800043df  mov     [rbp+var_18], ax
0x1800043e3  mov     [rbp+var_14], 0
0x1800043ea  mov     rax, [rcx+38h]
0x1800043ee  mov     [rbp+var_10], rax
0x1800043f2  mov     rax, [rcx+80h]
0x1800043f9  mov     [rbp+var_8], rax
0x1800043fd  mov     [rbp+arg_0], 0
0x180004405  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x18000440c  test    rdi, rdi
0x18000440f  jnz     short loc_180004455
0x180004411  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180004418  test    rax, rax
0x18000441b  jnz     short loc_180004436
0x18000441d  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180004424  call    cs:__imp_GetModuleHandleW
0x18000442a  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180004431  test    rax, rax
0x180004434  jz      short loc_180004449
0x180004436  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x18000443d  mov     rcx, rax; hModule
0x180004440  call    cs:__imp_GetProcAddress
0x180004446  mov     rdi, rax
0x180004449  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x180004450  test    rdi, rdi
0x180004453  jz      short loc_180004468
0x180004455  lea     r8, [rbp+arg_0]
0x180004459  lea     rdx, [rbp+var_30]
0x18000445d  xor     ecx, ecx
0x18000445f  mov     rax, rdi
0x180004462  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004467  nop
0x180004468  mov     eax, dword ptr [rbp+arg_0]
0x18000446b  mov     [rbx+10h], eax
0x18000446e  movzx   ecx, byte ptr [rbp+arg_0+4]
0x180004472  sub     ecx, 1
0x180004475  jz      short loc_18000448D
0x180004477  sub     ecx, 1
0x18000447a  jz      short loc_180004487
0x18000447c  cmp     ecx, 1
0x18000447f  jnz     short loc_180004491
0x180004481  or      dword ptr [rbx+4], 4
0x180004485  jmp     short loc_180004491
0x180004487  or      dword ptr [rbx+4], 2
0x18000448b  jmp     short loc_180004491
0x18000448d  or      dword ptr [rbx+4], 1
0x180004491  mov     rbx, [rsp+50h+arg_8]
0x180004496  mov     rdi, [rsp+50h+arg_10]
0x18000449b  add     rsp, 50h
0x18000449f  pop     rbp
0x1800044a0  retn
```
