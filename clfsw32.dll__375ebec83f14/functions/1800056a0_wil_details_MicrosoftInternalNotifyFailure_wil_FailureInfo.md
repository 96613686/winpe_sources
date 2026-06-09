# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x1800056a0`
- end: `0x1800057bd`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `285`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800056a0`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005756`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005756`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005734`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005734`

## string_xrefs

- `0x18000572d`: `kernelbase.dll`

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
0x1800056a0  mov     [rsp-8+arg_8], rbx
0x1800056a5  mov     [rsp-8+arg_10], rdi
0x1800056aa  push    rbp
0x1800056ab  mov     rbp, rsp
0x1800056ae  sub     rsp, 50h
0x1800056b2  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x1800056b9  xor     eax, eax
0x1800056bb  mov     [rbp+var_16], ax
0x1800056bf  mov     rbx, rcx
0x1800056c2  mov     eax, [rcx+8]
0x1800056c5  mov     [rbp+var_30], eax
0x1800056c8  mov     rax, [rcx+18h]
0x1800056cc  mov     [rbp+var_28], rax
0x1800056d0  mov     al, [rcx]
0x1800056d2  mov     [rbp+var_20], al
0x1800056d5  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x1800056dc  mov     [rbp+var_1E], ax
0x1800056e0  movzx   eax, word ptr [rcx+40h]
0x1800056e4  mov     [rbp+var_18], ax
0x1800056e8  mov     rax, [rcx+38h]
0x1800056ec  mov     [rbp+var_10], rax
0x1800056f0  mov     rax, [rcx+80h]
0x1800056f7  mov     [rbp+var_8], rax
0x1800056fb  mov     [rbp+var_2C], 0
0x180005702  mov     [rbp+var_1F], 0
0x180005706  mov     [rbp+var_1C], 0
0x18000570d  mov     [rbp+var_14], 0
0x180005714  mov     [rbp+arg_0], 0
0x18000571c  test    rdi, rdi
0x18000571f  jnz     short loc_180005771
0x180005721  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180005728  test    rax, rax
0x18000572b  jnz     short loc_18000574C
0x18000572d  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180005734  call    cs:__imp_GetModuleHandleW
0x18000573b  nop     dword ptr [rax+rax+00h]
0x180005740  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180005747  test    rax, rax
0x18000574a  jz      short loc_180005765
0x18000574c  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x180005753  mov     rcx, rax; hModule
0x180005756  call    cs:__imp_GetProcAddress
0x18000575d  nop     dword ptr [rax+rax+00h]
0x180005762  mov     rdi, rax
0x180005765  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x18000576c  test    rdi, rdi
0x18000576f  jz      short loc_180005783
0x180005771  lea     r8, [rbp+arg_0]
0x180005775  xor     ecx, ecx
0x180005777  lea     rdx, [rbp+var_30]
0x18000577b  mov     rax, rdi
0x18000577e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005783  movzx   ecx, byte ptr [rbp+arg_0+4]
0x180005787  mov     eax, dword ptr [rbp+arg_0]
0x18000578a  mov     [rbx+10h], eax
0x18000578d  sub     ecx, 1
0x180005790  jz      short loc_1800057A8
0x180005792  sub     ecx, 1
0x180005795  jz      short loc_1800057A2
0x180005797  cmp     ecx, 1
0x18000579a  jnz     short loc_1800057AC
0x18000579c  or      dword ptr [rbx+4], 4
0x1800057a0  jmp     short loc_1800057AC
0x1800057a2  or      dword ptr [rbx+4], 2
0x1800057a6  jmp     short loc_1800057AC
0x1800057a8  or      dword ptr [rbx+4], 1
0x1800057ac  mov     rbx, [rsp+50h+arg_8]
0x1800057b1  mov     rdi, [rsp+50h+arg_10]
0x1800057b6  add     rsp, 50h
0x1800057ba  pop     rbp
0x1800057bb  retn
```
