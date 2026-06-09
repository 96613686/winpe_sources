# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x1800231f0`
- end: `0x180023309`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `281`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800231f0`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002329d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002329d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002327b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002327b`

## string_xrefs

- `0x180023274`: `kernelbase.dll`

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
  v15 = 0;
  v16 = 0;
  v19 = 0;
  if ( `wil::details::WilFailureNotifyWatchers'::`2'::s_pfnFailureNotifyWatchers )
    goto LABEL_6;
  ModuleHandleW = `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle;
  ProcAddress = 0;
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
0x1800231f0  mov     [rsp-8+arg_8], rbx
0x1800231f5  mov     [rsp-8+arg_10], rsi
0x1800231fa  mov     [rsp-8+arg_18], rdi
0x1800231ff  push    rbp
0x180023200  mov     rbp, rsp
0x180023203  sub     rsp, 50h
0x180023207  mov     eax, [rcx+8]
0x18002320a  xor     esi, esi
0x18002320c  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x180023213  mov     rbx, rcx
0x180023216  mov     [rbp+var_30], eax
0x180023219  mov     rax, [rcx+18h]
0x18002321d  mov     [rbp+var_28], rax
0x180023221  mov     al, [rcx]
0x180023223  mov     [rbp+var_20], al
0x180023226  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x18002322d  mov     [rbp+var_1E], ax
0x180023231  movzx   eax, word ptr [rcx+40h]
0x180023235  mov     [rbp+var_18], ax
0x180023239  mov     rax, [rcx+38h]
0x18002323d  mov     [rbp+var_10], rax
0x180023241  mov     rax, [rcx+80h]
0x180023248  mov     [rbp+var_8], rax
0x18002324c  mov     [rbp+var_2C], esi
0x18002324f  mov     [rbp+var_1F], sil
0x180023253  mov     [rbp+var_1C], esi
0x180023256  mov     [rbp+var_16], si
0x18002325a  mov     [rbp+var_14], esi
0x18002325d  mov     [rbp+arg_0], rsi
0x180023261  test    rdi, rdi
0x180023264  jnz     short loc_1800232B8
0x180023266  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18002326d  mov     edi, esi
0x18002326f  test    rax, rax
0x180023272  jnz     short loc_180023293
0x180023274  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18002327b  call    cs:__imp_GetModuleHandleW
0x180023282  nop     dword ptr [rax+rax+00h]
0x180023287  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18002328e  test    rax, rax
0x180023291  jz      short loc_1800232AC
0x180023293  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x18002329a  mov     rcx, rax; hModule
0x18002329d  call    cs:__imp_GetProcAddress
0x1800232a4  nop     dword ptr [rax+rax+00h]
0x1800232a9  mov     rdi, rax
0x1800232ac  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x1800232b3  test    rdi, rdi
0x1800232b6  jz      short loc_1800232CA
0x1800232b8  lea     r8, [rbp+arg_0]
0x1800232bc  xor     ecx, ecx
0x1800232be  lea     rdx, [rbp+var_30]
0x1800232c2  mov     rax, rdi
0x1800232c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800232ca  movzx   ecx, byte ptr [rbp+arg_0+4]
0x1800232ce  mov     eax, dword ptr [rbp+arg_0]
0x1800232d1  mov     [rbx+10h], eax
0x1800232d4  sub     ecx, 1
0x1800232d7  jz      short loc_1800232EF
0x1800232d9  sub     ecx, 1
0x1800232dc  jz      short loc_1800232E9
0x1800232de  cmp     ecx, 1
0x1800232e1  jnz     short loc_1800232F3
0x1800232e3  or      dword ptr [rbx+4], 4
0x1800232e7  jmp     short loc_1800232F3
0x1800232e9  or      dword ptr [rbx+4], 2
0x1800232ed  jmp     short loc_1800232F3
0x1800232ef  or      dword ptr [rbx+4], 1
0x1800232f3  mov     rbx, [rsp+50h+arg_8]
0x1800232f8  mov     rsi, [rsp+50h+arg_10]
0x1800232fd  mov     rdi, [rsp+50h+arg_18]
0x180023302  add     rsp, 50h
0x180023306  pop     rbp
0x180023307  retn
```
