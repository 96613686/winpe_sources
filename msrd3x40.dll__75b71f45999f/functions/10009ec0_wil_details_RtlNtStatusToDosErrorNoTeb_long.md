# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x10009ec0`
- end: `0x10009f51`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YGKJ@Z`
- size: `145`
- prototype: `unsigned int __stdcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x10009ec0`
- `0x1000eb60`
- `0x1005e3b0`
- `0x1005f064`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x10009f0e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x10009f0e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x10009efd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x10009efd`

## string_xrefs

- `0x10009ef8`: `ntdll.dll`

## pseudocode

```c
FARPROC __stdcall wil::details::RtlNtStatusToDosErrorNoTeb(wil::details *this, int a2)
{
  int (__thiscall *v2)(_DWORD, _DWORD); // esi
  HMODULE ModuleHandleW; // eax
  FARPROC result; // eax

  v2 = (int (__thiscall *)(_DWORD, _DWORD))`wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb;
  if ( `wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb )
    return (FARPROC)v2(v2, this);
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  result = GetProcAddress(ModuleHandleW, "RtlNtStatusToDosErrorNoTeb");
  v2 = (int (__thiscall *)(_DWORD, _DWORD))result;
  `wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb = (int)result;
  if ( result )
    return (FARPROC)v2(v2, this);
  return result;
}

```

## disassembly

```asm
0x10009ec0  mov     edi, edi
0x10009ec2  push    ebp
0x10009ec3  mov     ebp, esp
0x10009ec5  push    0FFFFFFFFh
0x10009ec7  push    offset ??1PageDescBlocks@@QAE@XZ_SEH
0x10009ecc  mov     eax, large fs:0
0x10009ed2  push    eax
0x10009ed3  push    esi
0x10009ed4  mov     eax, ___security_cookie
0x10009ed9  xor     eax, ebp
0x10009edb  push    eax; unsigned int
0x10009edc  lea     eax, [ebp+var_C]
0x10009edf  mov     large fs:0, eax
0x10009ee5  mov     esi, ?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YGKJ@Z@4P6GKJ@_EA
0x10009eeb  test    esi, esi
0x10009eed  jnz     short loc_10009F32
0x10009eef  mov     eax, ?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YGPAUHINSTANCE__@@XZ@4PAU2@A; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x10009ef4  test    eax, eax
0x10009ef6  jnz     short loc_10009F08
0x10009ef8  push    offset ModuleName; "ntdll.dll"
0x10009efd  call    ds:__imp__GetModuleHandleW@4; GetModuleHandleW(x)
0x10009f03  mov     ?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YGPAUHINSTANCE__@@XZ@4PAU2@A, eax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x10009f08  push    offset aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x10009f0d  push    eax; hModule
0x10009f0e  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x10009f14  mov     esi, eax
0x10009f16  mov     ?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YGKJ@Z@4P6GKJ@_EA, esi
0x10009f1c  test    esi, esi
0x10009f1e  jnz     short loc_10009F32
0x10009f20  mov     ecx, [ebp+var_C]
0x10009f23  mov     large fs:0, ecx
0x10009f2a  pop     ecx
0x10009f2b  pop     esi
0x10009f2c  mov     esp, ebp
0x10009f2e  pop     ebp
0x10009f2f  retn    4
0x10009f32  push    [ebp+this]; void *
0x10009f35  mov     ecx, esi
0x10009f37  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10009f3d  call    esi ; ?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YGKJ@Z@4P6GKJ@_EA
0x10009f3f  mov     ecx, [ebp+var_C]
0x10009f42  mov     large fs:0, ecx
0x10009f49  pop     ecx
0x10009f4a  pop     esi
0x10009f4b  mov     esp, ebp
0x10009f4d  pop     ebp
0x10009f4e  retn    4
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
