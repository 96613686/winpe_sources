# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180007710`
- end: `0x180007821`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `273`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007710`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800077c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800077c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800077a4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800077a4`

## string_xrefs

- `0x18000779d`: `kernelbase.dll`

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
0x180007710  mov     [rsp-8+arg_8], rbx
0x180007715  mov     [rsp-8+arg_10], rdi
0x18000771a  push    rbp
0x18000771b  mov     rbp, rsp
0x18000771e  sub     rsp, 50h
0x180007722  mov     rbx, rcx
0x180007725  mov     [rbp+var_2C], 0
0x18000772c  mov     [rbp+var_1F], 0
0x180007730  mov     [rbp+var_1C], 0
0x180007737  xor     eax, eax
0x180007739  mov     [rbp+var_16], ax
0x18000773d  mov     eax, [rcx+8]
0x180007740  mov     [rbp+var_30], eax
0x180007743  mov     rax, [rcx+18h]
0x180007747  mov     [rbp+var_28], rax
0x18000774b  mov     al, [rcx]
0x18000774d  mov     [rbp+var_20], al
0x180007750  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x180007757  mov     [rbp+var_1E], ax
0x18000775b  movzx   eax, word ptr [rcx+40h]
0x18000775f  mov     [rbp+var_18], ax
0x180007763  mov     [rbp+var_14], 0
0x18000776a  mov     rax, [rcx+38h]
0x18000776e  mov     [rbp+var_10], rax
0x180007772  mov     rax, [rcx+80h]
0x180007779  mov     [rbp+var_8], rax
0x18000777d  mov     [rbp+arg_0], 0
0x180007785  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x18000778c  test    rdi, rdi
0x18000778f  jnz     short loc_1800077D5
0x180007791  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180007798  test    rax, rax
0x18000779b  jnz     short loc_1800077B6
0x18000779d  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800077a4  call    cs:__imp_GetModuleHandleW
0x1800077aa  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800077b1  test    rax, rax
0x1800077b4  jz      short loc_1800077C9
0x1800077b6  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x1800077bd  mov     rcx, rax; hModule
0x1800077c0  call    cs:__imp_GetProcAddress
0x1800077c6  mov     rdi, rax
0x1800077c9  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x1800077d0  test    rdi, rdi
0x1800077d3  jz      short loc_1800077E8
0x1800077d5  lea     r8, [rbp+arg_0]
0x1800077d9  lea     rdx, [rbp+var_30]
0x1800077dd  xor     ecx, ecx
0x1800077df  mov     rax, rdi
0x1800077e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077e7  nop
0x1800077e8  mov     eax, dword ptr [rbp+arg_0]
0x1800077eb  mov     [rbx+10h], eax
0x1800077ee  movzx   ecx, byte ptr [rbp+arg_0+4]
0x1800077f2  sub     ecx, 1
0x1800077f5  jz      short loc_18000780D
0x1800077f7  sub     ecx, 1
0x1800077fa  jz      short loc_180007807
0x1800077fc  cmp     ecx, 1
0x1800077ff  jnz     short loc_180007811
0x180007801  or      dword ptr [rbx+4], 4
0x180007805  jmp     short loc_180007811
0x180007807  or      dword ptr [rbx+4], 2
0x18000780b  jmp     short loc_180007811
0x18000780d  or      dword ptr [rbx+4], 1
0x180007811  mov     rbx, [rsp+50h+arg_8]
0x180007816  mov     rdi, [rsp+50h+arg_10]
0x18000781b  add     rsp, 50h
0x18000781f  pop     rbp
0x180007820  retn
```
