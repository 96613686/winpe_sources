# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x14000adc0`
- end: `0x14000ae17`
- name: `?RtlDllShutdownInProgress@details@wil@@YAEXZ`
- size: `87`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x14000adc0`
- `0x140019010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000adfa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000adfa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000ade3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000ade3`

## string_xrefs

- `0x14000addc`: `ntdll.dll`
- `0x14000adf0`: `RtlDllShutdownInProgress`

## pseudocode

```c
FARPROC __fastcall wil::details::RtlDllShutdownInProgress(wil::details *this)
{
  FARPROC result; // rax
  HMODULE ModuleHandleW; // rax

  result = (FARPROC)`wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress;
  if ( `wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress )
    return (FARPROC)((__int64 (__fastcall *)(wil::details *))result)(this);
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  result = GetProcAddress(ModuleHandleW, "RtlDllShutdownInProgress");
  `wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress = (__int64)result;
  if ( result )
    return (FARPROC)((__int64 (__fastcall *)(wil::details *))result)(this);
  return result;
}

```

## disassembly

```asm
0x14000adc0  sub     rsp, 28h
0x14000adc4  mov     rax, cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA
0x14000adcb  test    rax, rax
0x14000adce  jnz     short loc_14000AE0C
0x14000add0  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000add7  test    rax, rax
0x14000adda  jnz     short loc_14000ADF0
0x14000addc  lea     rcx, ModuleName; "ntdll.dll"
0x14000ade3  call    cs:__imp_GetModuleHandleW
0x14000ade9  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000adf0  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x14000adf7  mov     rcx, rax; hModule
0x14000adfa  call    cs:__imp_GetProcAddress
0x14000ae00  mov     cs:?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YAEXZ@4P6AEX_EEA, rax
0x14000ae07  test    rax, rax
0x14000ae0a  jz      short loc_14000AE12
0x14000ae0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ae11  nop
0x14000ae12  add     rsp, 28h
0x14000ae16  retn
```
