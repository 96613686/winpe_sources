# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180004800`
- end: `0x18000491e`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `286`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004800`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004894`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004894`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800048b6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800048b6`

## string_xrefs

- `0x18000488d`: `kernelbase.dll`

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
0x180004800  mov     [rsp-8+arg_8], rbx
0x180004805  mov     [rsp-8+arg_10], rdi
0x18000480a  push    rbp
0x18000480b  mov     rbp, rsp
0x18000480e  sub     rsp, 50h
0x180004812  mov     rbx, rcx
0x180004815  mov     [rbp+var_2C], 0
0x18000481c  mov     [rbp+var_1F], 0
0x180004820  mov     [rbp+var_1C], 0
0x180004827  xor     eax, eax
0x180004829  mov     [rbp+var_16], ax
0x18000482d  mov     eax, [rcx+8]
0x180004830  mov     [rbp+var_30], eax
0x180004833  mov     rax, [rcx+18h]
0x180004837  mov     [rbp+var_28], rax
0x18000483b  mov     al, [rcx]
0x18000483d  mov     [rbp+var_20], al
0x180004840  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x180004847  mov     [rbp+var_1E], ax
0x18000484b  movzx   eax, word ptr [rcx+40h]
0x18000484f  mov     [rbp+var_18], ax
0x180004853  mov     [rbp+var_14], 0
0x18000485a  mov     rax, [rcx+38h]
0x18000485e  mov     [rbp+var_10], rax
0x180004862  mov     rax, [rcx+80h]
0x180004869  mov     [rbp+var_8], rax
0x18000486d  mov     [rbp+arg_0], 0
0x180004875  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x18000487c  test    rdi, rdi
0x18000487f  jnz     short loc_1800048D1
0x180004881  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180004888  test    rax, rax
0x18000488b  jnz     short loc_1800048AC
0x18000488d  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180004894  call    cs:__imp_GetModuleHandleW
0x18000489b  nop     dword ptr [rax+rax+00h]
0x1800048a0  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800048a7  test    rax, rax
0x1800048aa  jz      short loc_1800048C5
0x1800048ac  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x1800048b3  mov     rcx, rax; hModule
0x1800048b6  call    cs:__imp_GetProcAddress
0x1800048bd  nop     dword ptr [rax+rax+00h]
0x1800048c2  mov     rdi, rax
0x1800048c5  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x1800048cc  test    rdi, rdi
0x1800048cf  jz      short loc_1800048E4
0x1800048d1  lea     r8, [rbp+arg_0]
0x1800048d5  lea     rdx, [rbp+var_30]
0x1800048d9  xor     ecx, ecx
0x1800048db  mov     rax, rdi
0x1800048de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048e3  nop
0x1800048e4  mov     eax, dword ptr [rbp+arg_0]
0x1800048e7  mov     [rbx+10h], eax
0x1800048ea  movzx   ecx, byte ptr [rbp+arg_0+4]
0x1800048ee  sub     ecx, 1
0x1800048f1  jz      short loc_180004909
0x1800048f3  sub     ecx, 1
0x1800048f6  jz      short loc_180004903
0x1800048f8  cmp     ecx, 1
0x1800048fb  jnz     short loc_18000490D
0x1800048fd  or      dword ptr [rbx+4], 4
0x180004901  jmp     short loc_18000490D
0x180004903  or      dword ptr [rbx+4], 2
0x180004907  jmp     short loc_18000490D
0x180004909  or      dword ptr [rbx+4], 1
0x18000490d  mov     rbx, [rsp+50h+arg_8]
0x180004912  mov     rdi, [rsp+50h+arg_10]
0x180004917  add     rsp, 50h
0x18000491b  pop     rbp
0x18000491c  retn
```
