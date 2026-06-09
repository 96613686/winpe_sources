# s_SSCatDBSendSmartAppControlSwitchEnforceToast

- ea: `0x180016bb0`
- end: `0x180016c30`
- name: `s_SSCatDBSendSmartAppControlSwitchEnforceToast`
- size: `128`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callees

- `0x18000ad10`
- `0x180016bb0`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016bf3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016bf3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180016bd1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180016bd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016be1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016be1`

## string_xrefs

- `0x180016bc4`: `wldp.dll`

## pseudocode

```c
__int64 __fastcall s_SSCatDBSendSmartAppControlSwitchEnforceToast(__int64 a1)
{
  unsigned int v1; // ebx
  HMODULE Library; // rax
  signed int LastError; // eax
  __int64 (*ProcAddress)(void); // rax
  HMODULE v6; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 )
  {
    Library = LoadLibraryExW(L"wldp.dll", 0, 0x800u);
    v6 = Library;
    if ( Library && (ProcAddress = GetProcAddress(Library, "WldpSendSmartAppControlSwitchEnforceToast")) != 0 )
    {
      v1 = 0;
      LastError = ProcAddress();
      if ( LastError >= 0 )
        goto LABEL_9;
      v1 = (unsigned __int16)LastError;
      if ( (LastError & 0x1FFF0000) == 0x70000 )
        goto LABEL_9;
    }
    else
    {
      LastError = GetLastError();
    }
    v1 = LastError;
LABEL_9:
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v6);
    return v1;
  }
  return 160;
}

```

## disassembly

```asm
0x180016bb0  push    rbx
0x180016bb2  sub     rsp, 20h
0x180016bb6  test    rcx, rcx
0x180016bb9  jnz     short loc_180016BC2
0x180016bbb  mov     ebx, 0A0h
0x180016bc0  jmp     short loc_180016C28
0x180016bc2  xor     edx, edx; hFile
0x180016bc4  lea     rcx, aWldpDll; "wldp.dll"
0x180016bcb  mov     r8d, 800h; dwFlags
0x180016bd1  call    cs:__imp_LoadLibraryExW
0x180016bd7  mov     [rsp+28h+arg_0], rax
0x180016bdc  test    rax, rax
0x180016bdf  jnz     short loc_180016BE9
0x180016be1  call    cs:__imp_GetLastError
0x180016be7  jmp     short loc_180016C1C
0x180016be9  lea     rdx, aWldpsendsmarta; "WldpSendSmartAppControlSwitchEnforceToa"...
0x180016bf0  mov     rcx, rax; hModule
0x180016bf3  call    cs:__imp_GetProcAddress
0x180016bf9  test    rax, rax
0x180016bfc  jz      short loc_180016BE1
0x180016bfe  xor     ebx, ebx
0x180016c00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c05  test    eax, eax
0x180016c07  jns     short loc_180016C1E
0x180016c09  mov     ecx, eax
0x180016c0b  movzx   ebx, ax
0x180016c0e  and     ecx, 1FFF0000h
0x180016c14  cmp     ecx, 70000h
0x180016c1a  jz      short loc_180016C1E
0x180016c1c  mov     ebx, eax
0x180016c1e  lea     rcx, [rsp+28h+arg_0]
0x180016c23  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180016c28  mov     eax, ebx
0x180016c2a  add     rsp, 20h
0x180016c2e  pop     rbx
0x180016c2f  retn
```
