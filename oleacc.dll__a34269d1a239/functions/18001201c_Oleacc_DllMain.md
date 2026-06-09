# Oleacc_DllMain

- ea: `0x18001201c`
- end: `0x180012285`
- name: `Oleacc_DllMain`
- size: `617`
- prototype: `__int64 __fastcall(HMODULE hLibModule)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001d580`

## callees

- `0x180010a2c`
- `0x18001201c`
- `0x18001228c`
- `0x18001e4c0`
- `0x18001efc4`
- `0x180049010`

## import_xrefs

- `ntdll!EtwRegisterTraceGuidsW` at `0x18001227a`
- `ntdll!EtwRegisterTraceGuidsW` at `0x18001227a`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180012086`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180012086`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180012185`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180012185`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180012172`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180012172`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800120d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800120f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012111`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800120d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800120f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012111`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800120b5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180012200`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800120b5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180012200`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180012169`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180012169`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800121d3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800121d3`

## string_xrefs

- `0x18001217a`: `OLEACCRC.DLL`
- `0x1800120c7`: `EventWrite`
- `0x1800120ae`: `advapi32.dll`
- `0x1800121f9`: `api-ms-win-eventing-provider-l1-1-0.dll`

## pseudocode

```c
__int64 __fastcall Oleacc_DllMain(HMODULE hLibModule, int a2)
{
  int v3; // esi
  HMODULE ModuleHandleW; // rdi
  __int64 result; // rax
  _QWORD v6[2]; // [rsp+40h] [rbp-148h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+50h] [rbp-138h] BYREF

  if ( a2 != 1 )
  {
    if ( !a2 )
    {
      UninitOleacc();
      DeleteCriticalSection(&g_OutstandingObjectTableCritSect);
      McGenEventTracingUnregister2();
    }
    return 1;
  }
  if ( !Microsoft_Windows_OLEACC_Context )
  {
    memset_0(&VersionInformation, 0, sizeof(VersionInformation));
    if ( McGenTracingSupportInit )
      goto LABEL_13;
    VersionInformation.dwOSVersionInfoSize = 276;
    v3 = 0;
    if ( !GetVersionExW(&VersionInformation) )
      goto LABEL_8;
    McGenPreVista = VersionInformation.dwMajorVersion < 6;
    if ( VersionInformation.dwMajorVersion > 6
      || VersionInformation.dwMajorVersion == 6 && VersionInformation.dwMinorVersion > 1 )
    {
      v3 = 1;
    }
    if ( VersionInformation.dwMajorVersion >= 6 )
    {
LABEL_8:
      ModuleHandleW = GetModuleHandleW(L"advapi32.dll");
      if ( ModuleHandleW || v3 && (ModuleHandleW = GetModuleHandleW(L"api-ms-win-eventing-provider-l1-1-0.dll")) != 0 )
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
    if ( McGenPreVista )
    {
      Microsoft_Windows_OLEACC_Context = (__int64)&Microsoft_Windows_OLEACC_Context;
      v6[0] = Microsoft_Windows_OLEACC;
      v6[1] = 0;
      ((void (__fastcall *)(__int64 (__fastcall *)(), __int64 *, __int64 *, __int64, _QWORD *, _QWORD, _QWORD, __int64 *))EtwRegisterTraceGuidsW)(
        McGenControlCallback,
        &Microsoft_Windows_OLEACC_Context,
        Microsoft_Windows_OLEACC,
        1,
        v6,
        0,
        0,
        &Microsoft_Windows_OLEACC_Context);
    }
    else
    {
      ((void (__fastcall *)(__int64 *, __int64 (__fastcall *)(int, int, int, int, __int64, int, __int64), __int64 *, __int64 *))PfnEventRegister)(
        Microsoft_Windows_OLEACC,
        McGenControlCallbackV2,
        &Microsoft_Windows_OLEACC_Context,
        &Microsoft_Windows_OLEACC_Context);
    }
  }
  InitializeCriticalSection(&g_OutstandingObjectTableCritSect);
  DisableThreadLibraryCalls(hLibModule);
  result = (__int64)LoadLibraryExW(L"OLEACCRC.DLL", 0, 2u);
  hinstResDll = (HINSTANCE)result;
  if ( result )
    return 1;
  return result;
}

```

## disassembly

```asm
0x18001201c  mov     [rsp+arg_8], rbp
0x180012021  mov     [rsp+arg_10], rsi
0x180012026  push    rdi
0x180012027  sub     rsp, 180h
0x18001202e  mov     rax, cs:__security_cookie
0x180012035  xor     rax, rsp
0x180012038  mov     [rsp+188h+var_18], rax
0x180012040  mov     rbp, rcx
0x180012043  cmp     edx, 1
0x180012046  jnz     loc_1800121BC
0x18001204c  cmp     cs:Microsoft_Windows_OLEACC_Context, 0
0x180012054  jnz     loc_180012162
0x18001205a  mov     edi, 114h
0x18001205f  lea     rcx, [rsp+188h+VersionInformation]; void *
0x180012064  mov     r8d, edi; Size
0x180012067  xor     edx, edx; Val
0x180012069  call    memset_0
0x18001206e  cmp     cs:McGenTracingSupportInit, 0
0x180012075  jnz     loc_18001212E
0x18001207b  lea     rcx, [rsp+188h+VersionInformation]; lpVersionInformation
0x180012080  mov     [rsp+188h+VersionInformation.dwOSVersionInfoSize], edi
0x180012084  xor     esi, esi
0x180012086  call    cs:__imp_GetVersionExW
0x18001208c  test    eax, eax
0x18001208e  jz      short loc_1800120AE
0x180012090  cmp     [rsp+188h+VersionInformation.dwMajorVersion], 6
0x180012095  setb    cl
0x180012098  mov     cs:McGenPreVista, cl
0x18001209e  ja      loc_1800121EB
0x1800120a4  jz      loc_1800121E0
0x1800120aa  test    cl, cl
0x1800120ac  jnz     short loc_180012127
0x1800120ae  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x1800120b5  call    cs:__imp_GetModuleHandleW
0x1800120bb  mov     rdi, rax
0x1800120be  test    rax, rax
0x1800120c1  jz      loc_1800121F5
0x1800120c7  lea     rdx, aEventwrite; "EventWrite"
0x1800120ce  mov     rcx, rdi; hModule
0x1800120d1  call    cs:__imp_GetProcAddress
0x1800120d7  mov     cs:PfnEventWrite, rax
0x1800120de  test    rax, rax
0x1800120e1  jz      loc_180012221
0x1800120e7  lea     rdx, aEventregister; "EventRegister"
0x1800120ee  mov     rcx, rdi; hModule
0x1800120f1  call    cs:__imp_GetProcAddress
0x1800120f7  mov     cs:PfnEventRegister, rax
0x1800120fe  test    rax, rax
0x180012101  jz      loc_180012213
0x180012107  lea     rdx, aEventunregiste; "EventUnregister"
0x18001210e  mov     rcx, rdi; hModule
0x180012111  call    cs:__imp_GetProcAddress
0x180012117  mov     cs:PfnEventUnregister, rax
0x18001211e  test    rax, rax
0x180012121  jz      loc_180012213
0x180012127  mov     cs:McGenTracingSupportInit, 1
0x18001212e  cmp     cs:McGenPreVista, 0
0x180012135  lea     rdx, Microsoft_Windows_OLEACC_Context
0x18001213c  jnz     loc_18001222D
0x180012142  mov     rax, cs:PfnEventRegister
0x180012149  lea     rcx, Microsoft_Windows_OLEACC
0x180012150  mov     r9, rdx
0x180012153  mov     r8, rdx
0x180012156  lea     rdx, McGenControlCallbackV2
0x18001215d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012162  lea     rcx, ?g_OutstandingObjectTableCritSect@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180012169  call    cs:__imp_InitializeCriticalSection
0x18001216f  mov     rcx, rbp; hLibModule
0x180012172  call    cs:__imp_DisableThreadLibraryCalls
0x180012178  xor     edx, edx; hFile
0x18001217a  lea     rcx, aOleaccrcDll; "OLEACCRC.DLL"
0x180012181  lea     r8d, [rdx+2]; dwFlags
0x180012185  call    cs:__imp_LoadLibraryExW
0x18001218b  mov     cs:?hinstResDll@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * hinstResDll
0x180012192  test    rax, rax
0x180012195  jnz     short loc_1800121C0
0x180012197  mov     rcx, [rsp+188h+var_18]
0x18001219f  xor     rcx, rsp; StackCookie
0x1800121a2  call    __security_check_cookie
0x1800121a7  lea     r11, [rsp+188h+var_8]
0x1800121af  mov     rbp, [r11+18h]
0x1800121b3  mov     rsi, [r11+20h]
0x1800121b7  mov     rsp, r11
0x1800121ba  pop     rdi
0x1800121bb  retn
0x1800121bc  test    edx, edx
0x1800121be  jz      short loc_1800121C7
0x1800121c0  mov     eax, 1
0x1800121c5  jmp     short loc_180012197
0x1800121c7  call    UninitOleacc
0x1800121cc  lea     rcx, ?g_OutstandingObjectTableCritSect@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800121d3  call    cs:__imp_DeleteCriticalSection
0x1800121d9  call    McGenEventTracingUnregister2
0x1800121de  jmp     short loc_1800121C0
0x1800121e0  cmp     [rsp+188h+VersionInformation.dwMinorVersion], 1
0x1800121e5  jbe     loc_1800120AA
0x1800121eb  mov     esi, 1
0x1800121f0  jmp     loc_1800120AA
0x1800121f5  test    esi, esi
0x1800121f7  jz      short loc_180012221
0x1800121f9  lea     rcx, aApiMsWinEventi; "api-ms-win-eventing-provider-l1-1-0.dll"
0x180012200  call    cs:__imp_GetModuleHandleW
0x180012206  mov     rdi, rax
0x180012209  test    rax, rax
0x18001220c  jz      short loc_180012221
0x18001220e  jmp     loc_1800120C7
0x180012213  lea     rax, McGenEventTracingRegister
0x18001221a  mov     cs:PfnEventRegister, rax
0x180012221  mov     cs:McGenPreVista, 1
0x180012228  jmp     loc_180012127
0x18001222d  mov     [rsp+188h+var_150], rdx
0x180012232  lea     rax, Microsoft_Windows_OLEACC
0x180012239  mov     [rsp+188h+var_158], 0
0x180012242  lea     rcx, [rsp+188h+var_148]
0x180012247  mov     [rsp+188h+var_160], 0
0x180012250  mov     r9d, 1
0x180012256  mov     [rsp+188h+var_168], rcx
0x18001225b  mov     r8, rax
0x18001225e  lea     rcx, McGenControlCallback
0x180012265  mov     cs:Microsoft_Windows_OLEACC_Context, rdx
0x18001226c  mov     [rsp+188h+var_148], rax
0x180012271  mov     [rsp+188h+var_140], 0
0x18001227a  call    cs:__imp_EtwRegisterTraceGuidsW
0x180012280  jmp     loc_180012162
```
