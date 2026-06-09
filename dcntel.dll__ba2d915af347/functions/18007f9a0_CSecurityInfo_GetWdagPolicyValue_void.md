# CSecurityInfo::GetWdagPolicyValue(void)

- ea: `0x18007f9a0`
- end: `0x18007facc`
- name: `?GetWdagPolicyValue@CSecurityInfo@@QEBAHXZ`
- size: `300`
- prototype: `__int64 __fastcall(CSecurityInfo *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18001daf0`
- `0x18001dcc8`
- `0x18007f9a0`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18007f9c1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18007f9c1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007f9ed`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007f9ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007fa7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007fa98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007fab2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007fa7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007fa98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007fab2`

## string_xrefs

- `0x18007f9ba`: `policymanager.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSecurityInfo::GetWdagPolicyValue(CSecurityInfo *this)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  unsigned int v4; // ebx
  signed int v5; // eax
  int v6; // edx
  unsigned int v7; // r8d
  signed int LastError; // eax
  int v9; // edx
  unsigned int v10; // r8d
  signed int v11; // eax
  int v12; // edx
  unsigned int v13; // r8d
  const int *v14; // [rsp+20h] [rbp-10h] BYREF
  HMODULE v15; // [rsp+28h] [rbp-8h]
  unsigned int v16; // [rsp+48h] [rbp+18h] BYREF

  Library = LoadLibraryExW(L"policymanager.dll", 0, 0x800u);
  v14 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  v15 = Library;
  if ( !Library )
    return 0xFFFFFFFFLL;
  ProcAddress = GetProcAddress(Library, "PolicyManager_GetPolicyInt");
  if ( !ProcAddress )
  {
    v14 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
    if ( v15 && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v14) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v9, v10);
      __debugbreak();
    }
    return 0xFFFFFFFFLL;
  }
  v16 = 0;
  if ( ((int (__fastcall *)(const wchar_t *, const wchar_t *, unsigned int *))ProcAddress)(
         L"AppHVSI",
         L"AllowAppHVSI",
         &v16) < 0 )
  {
    v14 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
    if ( v15 && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v14) )
    {
      v11 = GetLastError();
      if ( v11 > 0 )
        v11 = (unsigned __int16)v11 | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v11, v12, v13);
      JUMPOUT(0x18007FACBLL);
    }
    return 0xFFFFFFFFLL;
  }
  v4 = v16;
  v14 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  if ( v15 && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v14) )
  {
    v5 = GetLastError();
    if ( v5 > 0 )
      v5 = (unsigned __int16)v5 | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v5, v6, v7);
    __debugbreak();
  }
  return v4;
}

```

## disassembly

```asm
0x18007f9a0  mov     [rsp-8+arg_0], rbx
0x18007f9a5  mov     [rsp-8+arg_10], rsi
0x18007f9aa  push    rbp
0x18007f9ab  mov     rbp, rsp
0x18007f9ae  sub     rsp, 30h
0x18007f9b2  xor     edx, edx; hFile
0x18007f9b4  mov     r8d, 800h; dwFlags
0x18007f9ba  lea     rcx, aPolicymanagerD; "policymanager.dll"
0x18007f9c1  call    cs:__imp_LoadLibraryExW
0x18007f9c7  lea     rsi, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x18007f9ce  mov     [rbp+var_10], rsi
0x18007f9d2  mov     [rbp+var_8], rax
0x18007f9d6  test    rax, rax
0x18007f9d9  jnz     short loc_18007F9E3
0x18007f9db  or      eax, 0FFFFFFFFh
0x18007f9de  jmp     loc_18007FA6E
0x18007f9e3  lea     rdx, aPolicymanagerG_2; "PolicyManager_GetPolicyInt"
0x18007f9ea  mov     rcx, rax; hModule
0x18007f9ed  call    cs:__imp_GetProcAddress
0x18007f9f3  test    rax, rax
0x18007f9f6  jnz     short loc_18007FA15
0x18007f9f8  mov     [rbp+var_10], rsi
0x18007f9fc  cmp     [rbp+var_8], rax
0x18007fa00  jz      short loc_18007F9DB
0x18007fa02  lea     rcx, [rbp+var_10]
0x18007fa06  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x18007fa0b  test    al, al
0x18007fa0d  jz      loc_18007FA98
0x18007fa13  jmp     short loc_18007F9DB
0x18007fa15  mov     [rbp+arg_8], 0
0x18007fa1c  lea     r8, [rbp+arg_8]
0x18007fa20  lea     rdx, aAllowapphvsi; "AllowAppHVSI"
0x18007fa27  lea     rcx, aApphvsi; "AppHVSI"
0x18007fa2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007fa33  test    eax, eax
0x18007fa35  jns     short loc_18007FA51
0x18007fa37  mov     [rbp+var_10], rsi
0x18007fa3b  cmp     [rbp+var_8], 0
0x18007fa40  jz      short loc_18007F9DB
0x18007fa42  lea     rcx, [rbp+var_10]
0x18007fa46  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x18007fa4b  test    al, al
0x18007fa4d  jz      short loc_18007FAB2
0x18007fa4f  jmp     short loc_18007F9DB
0x18007fa51  mov     ebx, [rbp+arg_8]
0x18007fa54  mov     [rbp+var_10], rsi
0x18007fa58  cmp     [rbp+var_8], 0
0x18007fa5d  jz      short loc_18007FA6C
0x18007fa5f  lea     rcx, [rbp+var_10]
0x18007fa63  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x18007fa68  test    al, al
0x18007fa6a  jz      short loc_18007FA7E
0x18007fa6c  mov     eax, ebx
0x18007fa6e  mov     rbx, [rsp+30h+arg_0]
0x18007fa73  mov     rsi, [rsp+30h+arg_10]
0x18007fa78  add     rsp, 30h
0x18007fa7c  pop     rbp
0x18007fa7d  retn
0x18007fa7e  call    cs:__imp_GetLastError
0x18007fa84  test    eax, eax
0x18007fa86  jle     short loc_18007FA90
0x18007fa88  movzx   eax, ax
0x18007fa8b  or      eax, 80070000h
0x18007fa90  mov     ecx, eax; this
0x18007fa92  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18007fa97  int     3; Trap to Debugger
0x18007fa98  call    cs:__imp_GetLastError
0x18007fa9e  test    eax, eax
0x18007faa0  jle     short loc_18007FAAA
0x18007faa2  movzx   eax, ax
0x18007faa5  or      eax, 80070000h
0x18007faaa  mov     ecx, eax; this
0x18007faac  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18007fab1  int     3; Trap to Debugger
0x18007fab2  call    cs:__imp_GetLastError
0x18007fab8  test    eax, eax
0x18007faba  jle     short loc_18007FAC4
0x18007fabc  movzx   eax, ax
0x18007fabf  or      eax, 80070000h
0x18007fac4  mov     ecx, eax; this
0x18007fac6  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
