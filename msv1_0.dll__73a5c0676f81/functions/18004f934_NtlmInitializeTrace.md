# NtlmInitializeTrace

- ea: `0x18004f934`
- end: `0x18004fa32`
- name: `NtlmInitializeTrace`
- size: `254`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180048050`

## callees

- `0x18002ee7c`
- `0x18002fb50`
- `0x18004f934`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004f956`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004f956`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18004f96f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18004f96f`
- `ntdll!EtwRegisterTraceGuidsW` at `0x18004f9d7`
- `ntdll!EtwRegisterTraceGuidsW` at `0x18004f9d7`

## string_xrefs

- `0x18004f94f`: `msv1_0.dll`
- `0x18004f979`: `msv1_0.dll`

## pseudocode

```c
__int64 NtlmInitializeTrace()
{
  HMODULE ModuleHandleW; // rax
  unsigned int v1; // ebx
  wchar_t Filename[264]; // [rsp+40h] [rbp-228h] BYREF

  ModuleHandleW = GetModuleHandleW(L"msv1_0.dll");
  if ( !ModuleHandleW || !GetModuleFileNameW(ModuleHandleW, Filename, 0x104u) )
    wcscpy(Filename, L"msv1_0dll");
  v1 = ((__int64 (__fastcall *)(unsigned int (__fastcall *)(enum WMIDPREQUESTCODE, void *, unsigned int *, void *), _QWORD, __int64 *, __int64, struct _TRACE_GUID_REGISTRATION near **, wchar_t *, const wchar_t *, __int64 *))EtwRegisterTraceGuidsW)(
         NtlmTraceControlCallback,
         0,
         NtlmControlGuid,
         5,
         &NtlmTraceGuids,
         Filename,
         L"MofResource",
         &NtlmGlobalTraceRegistrationHandle);
  if ( v1 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_a7839f9fd5203de9ad40ce9c38ea7110_Traceguids, v1);
  return v1;
}

```

## disassembly

```asm
0x18004f934  push    rbx
0x18004f936  sub     rsp, 260h
0x18004f93d  mov     rax, cs:__security_cookie
0x18004f944  xor     rax, rsp
0x18004f947  mov     [rsp+268h+var_18], rax
0x18004f94f  lea     rcx, aMsv10Dll_0; "msv1_0.dll"
0x18004f956  call    cs:__imp_GetModuleHandleW
0x18004f95c  test    rax, rax
0x18004f95f  jz      short loc_18004F979
0x18004f961  mov     r8d, 104h; nSize
0x18004f967  lea     rdx, [rsp+268h+Filename]; lpFilename
0x18004f96c  mov     rcx, rax; hModule
0x18004f96f  call    cs:__imp_GetModuleFileNameW
0x18004f975  test    eax, eax
0x18004f977  jnz     short loc_18004F993
0x18004f979  movups  xmm0, xmmword ptr cs:aMsv10Dll_0; "msv1_0.dll"
0x18004f980  movsd   xmm1, qword ptr cs:aMsv10Dll_0+0Eh; "dll"
0x18004f988  movaps  xmmword ptr [rsp+268h+Filename], xmm0
0x18004f98d  movsd   qword ptr [rsp+268h+Filename+0Eh], xmm1
0x18004f993  lea     rax, NtlmGlobalTraceRegistrationHandle
0x18004f99a  mov     r9d, 5
0x18004f9a0  mov     [rsp+268h+var_230], rax
0x18004f9a5  lea     r8, NtlmControlGuid
0x18004f9ac  lea     rax, aMofresource; "MofResource"
0x18004f9b3  xor     edx, edx
0x18004f9b5  mov     [rsp+268h+var_238], rax
0x18004f9ba  lea     rcx, ?NtlmTraceControlCallback@@YAKW4WMIDPREQUESTCODE@@PEAXPEAK1@Z; NtlmTraceControlCallback(WMIDPREQUESTCODE,void *,ulong *,void *)
0x18004f9c1  lea     rax, [rsp+268h+Filename]
0x18004f9c6  mov     [rsp+268h+var_240], rax
0x18004f9cb  lea     rax, ?NtlmTraceGuids@@3PAU_TRACE_GUID_REGISTRATION@@A; _TRACE_GUID_REGISTRATION near * NtlmTraceGuids
0x18004f9d2  mov     [rsp+268h+var_248], rax
0x18004f9d7  call    cs:__imp_EtwRegisterTraceGuidsW
0x18004f9dd  mov     ebx, eax
0x18004f9df  test    eax, eax
0x18004f9e1  jz      short loc_18004FA17
0x18004f9e3  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f9ea  lea     rax, WPP_GLOBAL_Control
0x18004f9f1  cmp     rcx, rax
0x18004f9f4  jz      short loc_18004FA17
0x18004f9f6  test    dword ptr [rcx+1Ch], 100h
0x18004f9fd  jz      short loc_18004FA17
0x18004f9ff  mov     rcx, [rcx+10h]
0x18004fa03  lea     r8, WPP_a7839f9fd5203de9ad40ce9c38ea7110_Traceguids
0x18004fa0a  mov     edx, 0Ah
0x18004fa0f  mov     r9d, ebx
0x18004fa12  call    WPP_SF_d
0x18004fa17  mov     eax, ebx
0x18004fa19  mov     rcx, [rsp+268h+var_18]
0x18004fa21  xor     rcx, rsp; StackCookie
0x18004fa24  call    __security_check_cookie
0x18004fa29  add     rsp, 260h
0x18004fa30  pop     rbx
0x18004fa31  retn
```
