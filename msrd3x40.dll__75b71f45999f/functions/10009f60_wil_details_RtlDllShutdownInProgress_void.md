# wil::details::RtlDllShutdownInProgress(void)

- ea: `0x10009f60`
- end: `0x10009fec`
- name: `?RtlDllShutdownInProgress@details@wil@@YGEXZ`
- size: `140`
- prototype: `unsigned __int8(wil::details *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x10009f60`
- `0x1000eb60`
- `0x1005e3b0`
- `0x1005f064`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x10009fae`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x10009fae`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x10009f9d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x10009f9d`

## string_xrefs

- `0x10009f98`: `ntdll.dll`
- `0x10009fa8`: `RtlDllShutdownInProgress`

## pseudocode

```c
unsigned __int8 wil::details::RtlDllShutdownInProgress()
{
  BOOLEAN (__stdcall *RtlDllShutdownInProgress)(); // esi
  HMODULE ModuleHandleW; // eax

  RtlDllShutdownInProgress = (BOOLEAN (__stdcall *)())`wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress;
  if ( `wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress )
    return ((int (__thiscall *)(BOOLEAN (__stdcall *)()))RtlDllShutdownInProgress)(RtlDllShutdownInProgress);
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  RtlDllShutdownInProgress = (BOOLEAN (__stdcall *)())GetProcAddress(ModuleHandleW, "RtlDllShutdownInProgress");
  `wil::details::RtlDllShutdownInProgress'::`2'::s_pfnRtlDllShutdownInProgress = (int)RtlDllShutdownInProgress;
  if ( RtlDllShutdownInProgress )
    return ((int (__thiscall *)(BOOLEAN (__stdcall *)()))RtlDllShutdownInProgress)(RtlDllShutdownInProgress);
  else
    return 0;
}

```

## disassembly

```asm
0x10009f60  mov     edi, edi
0x10009f62  push    ebp
0x10009f63  mov     ebp, esp
0x10009f65  push    0FFFFFFFFh
0x10009f67  push    offset ??1PageDescBlocks@@QAE@XZ_SEH
0x10009f6c  mov     eax, large fs:0
0x10009f72  push    eax
0x10009f73  push    esi; unsigned int
0x10009f74  mov     eax, ___security_cookie
0x10009f79  xor     eax, ebp
0x10009f7b  push    eax; void *
0x10009f7c  lea     eax, [ebp+var_C]
0x10009f7f  mov     large fs:0, eax
0x10009f85  mov     esi, ?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YGEXZ@4P6GEX_EA
0x10009f8b  test    esi, esi
0x10009f8d  jnz     short loc_10009FD2
0x10009f8f  mov     eax, ?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YGPAUHINSTANCE__@@XZ@4PAU2@A; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x10009f94  test    eax, eax
0x10009f96  jnz     short loc_10009FA8
0x10009f98  push    offset ModuleName; "ntdll.dll"
0x10009f9d  call    ds:__imp__GetModuleHandleW@4; GetModuleHandleW(x)
0x10009fa3  mov     ?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YGPAUHINSTANCE__@@XZ@4PAU2@A, eax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x10009fa8  push    offset aRtldllshutdown; "RtlDllShutdownInProgress"
0x10009fad  push    eax; hModule
0x10009fae  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x10009fb4  mov     esi, eax
0x10009fb6  mov     ?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YGEXZ@4P6GEX_EA, esi
0x10009fbc  test    esi, esi
0x10009fbe  jnz     short loc_10009FD2
0x10009fc0  xor     al, al
0x10009fc2  mov     ecx, [ebp+var_C]
0x10009fc5  mov     large fs:0, ecx
0x10009fcc  pop     ecx
0x10009fcd  pop     esi
0x10009fce  mov     esp, ebp
0x10009fd0  pop     ebp
0x10009fd1  retn
0x10009fd2  mov     ecx, esi
0x10009fd4  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10009fda  call    esi ; ?s_pfnRtlDllShutdownInProgress@?1??RtlDllShutdownInProgress@details@wil@@YGEXZ@4P6GEX_EA
0x10009fdc  mov     ecx, [ebp+var_C]
0x10009fdf  mov     large fs:0, ecx
0x10009fe6  pop     ecx
0x10009fe7  pop     esi
0x10009fe8  mov     esp, ebp
0x10009fea  pop     ebp
0x10009feb  retn
0x1005f630  nop
0x1005f631  nop
0x1005f632  mov     edx, [esp-4+arg_4]
0x1005f636  lea     eax, [edx+0Ch]
0x1005f639  mov     ecx, [edx-8]
0x1005f63c  xor     ecx, eax; StackCookie
0x1005f63e  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1005f643  mov     eax, offset stru_10062AB0
0x1005f648  jmp     ___CxxFrameHandler3
```
