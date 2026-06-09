# McGenEventTracingRegister

- ea: `0x180017ed0`
- end: `0x1800180e8`
- name: `McGenEventTracingRegister`
- size: `536`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180017ed0`
- `0x18001e4c0`
- `0x18001efc4`
- `0x180049010`

## import_xrefs

- `ntdll!EtwRegisterTraceGuidsW` at `0x1800180d3`
- `ntdll!EtwRegisterTraceGuidsW` at `0x1800180d3`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180017f3e`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180017f3e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180017f89`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180017fa9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180017fc9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180017f89`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180017fa9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180017fc9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180017f6d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001805f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180017f6d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001805f`

## string_xrefs

- `0x180017f7f`: `EventWrite`
- `0x180017f66`: `advapi32.dll`
- `0x180018058`: `api-ms-win-eventing-provider-l1-1-0.dll`

## pseudocode

```c
__int64 __fastcall McGenEventTracingRegister(__int64 a1, __int64 (__fastcall *a2)(), __int64 a3, _QWORD *a4)
{
  __int64 result; // rax
  int v9; // edi
  HMODULE ModuleHandleW; // rbx
  __int64 (__fastcall *v11)(); // rcx
  _QWORD v12[2]; // [rsp+40h] [rbp-178h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+50h] [rbp-168h] BYREF

  if ( !a4 )
    return 87;
  result = 0;
  if ( *a4 )
    return result;
  memset_0(&VersionInformation, 0, sizeof(VersionInformation));
  if ( McGenTracingSupportInit )
    goto LABEL_13;
  VersionInformation.dwOSVersionInfoSize = 276;
  v9 = 0;
  if ( !GetVersionExW(&VersionInformation) )
    goto LABEL_8;
  McGenPreVista = VersionInformation.dwMajorVersion < 6;
  if ( VersionInformation.dwMajorVersion > 6
    || VersionInformation.dwMajorVersion == 6 && VersionInformation.dwMinorVersion > 1 )
  {
    v9 = 1;
  }
  if ( VersionInformation.dwMajorVersion >= 6 )
  {
LABEL_8:
    ModuleHandleW = GetModuleHandleW(L"advapi32.dll");
    if ( ModuleHandleW || v9 && (ModuleHandleW = GetModuleHandleW(L"api-ms-win-eventing-provider-l1-1-0.dll")) != 0 )
    {
      PfnEventWrite = (__int64)GetProcAddress(ModuleHandleW, "EventWrite");
      if ( PfnEventWrite )
      {
        PfnEventRegister = GetProcAddress(ModuleHandleW, "EventRegister");
        if ( PfnEventRegister )
        {
          PfnEventUnregister = (__int64)GetProcAddress(ModuleHandleW, "EventUnregister");
          if ( PfnEventUnregister )
            goto LABEL_12;
        }
        PfnEventRegister = McGenEventTracingRegister;
      }
    }
    McGenPreVista = 1;
  }
LABEL_12:
  McGenTracingSupportInit = 1;
LABEL_13:
  if ( !McGenPreVista )
    return PfnEventRegister();
  if ( !a3 )
    return 87;
  v11 = McGenControlCallback;
  if ( a2 )
    v11 = a2;
  *a4 = a3;
  v12[0] = a1;
  v12[1] = 0;
  return ((__int64 (__fastcall *)(__int64 (__fastcall *)(), __int64, __int64, __int64, _QWORD *, _QWORD, _QWORD, __int64))EtwRegisterTraceGuidsW)(
           v11,
           a3,
           a1,
           1,
           v12,
           0,
           0,
           a3);
}

```

## disassembly

```asm
0x180017ed0  push    rbx
0x180017ed2  push    rbp
0x180017ed3  push    rsi
0x180017ed4  push    rdi
0x180017ed5  push    r14
0x180017ed7  push    r15
0x180017ed9  sub     rsp, 188h
0x180017ee0  mov     rax, cs:__security_cookie
0x180017ee7  xor     rax, rsp
0x180017eea  mov     [rsp+1B8h+var_48], rax
0x180017ef2  mov     r14, r9
0x180017ef5  mov     rsi, r8
0x180017ef8  mov     rbp, rdx
0x180017efb  mov     r15, rcx
0x180017efe  test    r9, r9
0x180017f01  jz      loc_1800180DE
0x180017f07  xor     eax, eax
0x180017f09  cmp     [r9], rax
0x180017f0c  jnz     loc_180018016
0x180017f12  mov     ebx, 114h
0x180017f17  lea     rcx, [rsp+1B8h+VersionInformation]; void *
0x180017f1c  mov     r8d, ebx; Size
0x180017f1f  xor     edx, edx; Val
0x180017f21  call    memset_0
0x180017f26  cmp     cs:McGenTracingSupportInit, 0
0x180017f2d  jnz     loc_180017FE6
0x180017f33  lea     rcx, [rsp+1B8h+VersionInformation]; lpVersionInformation
0x180017f38  mov     [rsp+1B8h+VersionInformation.dwOSVersionInfoSize], ebx
0x180017f3c  xor     edi, edi
0x180017f3e  call    cs:__imp_GetVersionExW
0x180017f44  test    eax, eax
0x180017f46  jz      short loc_180017F66
0x180017f48  cmp     [rsp+1B8h+VersionInformation.dwMajorVersion], 6
0x180017f4d  setb    cl
0x180017f50  mov     cs:McGenPreVista, cl
0x180017f56  ja      loc_18001804A
0x180017f5c  jz      loc_18001803F
0x180017f62  test    cl, cl
0x180017f64  jnz     short loc_180017FDF
0x180017f66  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x180017f6d  call    cs:__imp_GetModuleHandleW
0x180017f73  mov     rbx, rax
0x180017f76  test    rax, rax
0x180017f79  jz      loc_180018054
0x180017f7f  lea     rdx, aEventwrite; "EventWrite"
0x180017f86  mov     rcx, rbx; hModule
0x180017f89  call    cs:__imp_GetProcAddress
0x180017f8f  mov     cs:PfnEventWrite, rax
0x180017f96  test    rax, rax
0x180017f99  jz      loc_180018036
0x180017f9f  lea     rdx, aEventregister; "EventRegister"
0x180017fa6  mov     rcx, rbx; hModule
0x180017fa9  call    cs:__imp_GetProcAddress
0x180017faf  mov     cs:PfnEventRegister, rax
0x180017fb6  test    rax, rax
0x180017fb9  jz      loc_180018072
0x180017fbf  lea     rdx, aEventunregiste; "EventUnregister"
0x180017fc6  mov     rcx, rbx; hModule
0x180017fc9  call    cs:__imp_GetProcAddress
0x180017fcf  mov     cs:PfnEventUnregister, rax
0x180017fd6  test    rax, rax
0x180017fd9  jz      loc_180018072
0x180017fdf  mov     cs:McGenTracingSupportInit, 1
0x180017fe6  cmp     cs:McGenPreVista, 0
0x180017fed  jnz     loc_180018082
0x180017ff3  mov     rax, cs:PfnEventRegister
0x180017ffa  lea     rdx, McGenControlCallbackV2
0x180018001  test    rbp, rbp
0x180018004  mov     r9, r14
0x180018007  mov     r8, rsi
0x18001800a  mov     rcx, r15
0x18001800d  cmovnz  rdx, rbp
0x180018011  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018016  mov     rcx, [rsp+1B8h+var_48]
0x18001801e  xor     rcx, rsp; StackCookie
0x180018021  call    __security_check_cookie
0x180018026  add     rsp, 188h
0x18001802d  pop     r15
0x18001802f  pop     r14
0x180018031  pop     rdi
0x180018032  pop     rsi
0x180018033  pop     rbp
0x180018034  pop     rbx
0x180018035  retn
0x180018036  mov     cs:McGenPreVista, 1
0x18001803d  jmp     short loc_180017FDF
0x18001803f  cmp     [rsp+1B8h+VersionInformation.dwMinorVersion], 1
0x180018044  jbe     loc_180017F62
0x18001804a  mov     edi, 1
0x18001804f  jmp     loc_180017F62
0x180018054  test    edi, edi
0x180018056  jz      short loc_180018036
0x180018058  lea     rcx, aApiMsWinEventi; "api-ms-win-eventing-provider-l1-1-0.dll"
0x18001805f  call    cs:__imp_GetModuleHandleW
0x180018065  mov     rbx, rax
0x180018068  test    rax, rax
0x18001806b  jz      short loc_180018036
0x18001806d  jmp     loc_180017F7F
0x180018072  lea     rax, McGenEventTracingRegister
0x180018079  mov     cs:PfnEventRegister, rax
0x180018080  jmp     short loc_180018036
0x180018082  test    rsi, rsi
0x180018085  jz      short loc_1800180DE
0x180018087  mov     [rsp+1B8h+var_180], rsi
0x18001808c  lea     rax, [rsp+1B8h+var_178]
0x180018091  test    rbp, rbp
0x180018094  mov     [rsp+1B8h+var_188], 0
0x18001809d  lea     rcx, McGenControlCallback
0x1800180a4  mov     [rsp+1B8h+var_190], 0
0x1800180ad  cmovnz  rcx, rbp
0x1800180b1  mov     [r14], rsi
0x1800180b4  mov     r9d, 1
0x1800180ba  mov     [rsp+1B8h+var_178], r15
0x1800180bf  mov     r8, r15
0x1800180c2  mov     [rsp+1B8h+var_170], 0
0x1800180cb  mov     rdx, rsi
0x1800180ce  mov     [rsp+1B8h+var_198], rax
0x1800180d3  call    cs:__imp_EtwRegisterTraceGuidsW
0x1800180d9  jmp     loc_180018016
0x1800180de  mov     eax, 57h ; 'W'
0x1800180e3  jmp     loc_180018016
```
