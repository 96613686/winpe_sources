# Utils::GetTpmVersion(void)

- ea: `0x1800d3474`
- end: `0x1800d360c`
- name: `?GetTpmVersion@Utils@@SAHXZ`
- size: `408`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003c3c0`
- `0x18003cb10`
- `0x1800bbdd0`

## callees

- `0x180008dc0`
- `0x18001daf0`
- `0x18001dcc8`
- `0x18002a690`
- `0x1800d3474`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800d34c4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800d34c4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d34ec`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d34ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d35a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d35be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d35d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d35f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d35a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d35be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d35d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d35f2`

## string_xrefs

- `0x1800d34bd`: `Tbs.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Utils::GetTpmVersion(__int64 a1, __int64 a2, unsigned __int16 a3)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  int v5; // eax
  unsigned int v6; // ebx
  signed int v8; // eax
  int v9; // edx
  unsigned int v10; // r8d
  signed int v11; // eax
  int v12; // edx
  unsigned int v13; // r8d
  signed int LastError; // eax
  int v15; // edx
  unsigned int v16; // r8d
  signed int v17; // eax
  int v18; // edx
  unsigned int v19; // r8d
  const int *v20; // [rsp+20h] [rbp-30h] BYREF
  HMODULE v21; // [rsp+28h] [rbp-28h]
  __int128 v22; // [rsp+30h] [rbp-20h] BYREF

  if ( !IsWindowsVersionOrGreater(6u, 2u, a3) )
    return 0xFFFFFFFFLL;
  v22 = 0;
  LODWORD(v22) = 2;
  Library = LoadLibraryExW(L"Tbs.dll", 0, 0x800u);
  v20 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  v21 = Library;
  if ( !Library )
    return 0xFFFFFFFFLL;
  ProcAddress = GetProcAddress(Library, "Tbsi_GetDeviceInfo");
  if ( !ProcAddress )
  {
    v20 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
    if ( v21 && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v20) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v15, v16);
      __debugbreak();
    }
    return 0xFFFFFFFFLL;
  }
  v5 = ((__int64 (__fastcall *)(__int64, __int128 *))ProcAddress)(16, &v22);
  if ( !v5 )
  {
    v6 = DWORD1(v22);
    if ( DWORD1(v22) )
    {
      v20 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
      if ( v21 && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v20) )
      {
        v17 = GetLastError();
        if ( v17 > 0 )
          v17 = (unsigned __int16)v17 | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v17, v18, v19);
        JUMPOUT(0x1800D360BLL);
      }
      return v6;
    }
    goto LABEL_13;
  }
  if ( v5 != -2144845809 )
  {
LABEL_13:
    v20 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
    if ( v21 && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v20) )
    {
      v11 = GetLastError();
      if ( v11 > 0 )
        v11 = (unsigned __int16)v11 | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v11, v12, v13);
      __debugbreak();
    }
    return 0xFFFFFFFFLL;
  }
  v20 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  if ( v21 && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v20) )
  {
    v8 = GetLastError();
    if ( v8 > 0 )
      v8 = (unsigned __int16)v8 | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v8, v9, v10);
    __debugbreak();
  }
  return 0;
}

```

## disassembly

```asm
0x1800d3474  mov     [rsp-8+arg_0], rbx
0x1800d3479  mov     [rsp-8+arg_8], rsi
0x1800d347e  push    rbp
0x1800d347f  mov     rbp, rsp
0x1800d3482  sub     rsp, 50h
0x1800d3486  mov     rax, cs:__security_cookie
0x1800d348d  xor     rax, rsp
0x1800d3490  mov     [rbp+var_10], rax
0x1800d3494  mov     ebx, 2
0x1800d3499  mov     edx, ebx; unsigned __int16
0x1800d349b  lea     ecx, [rbx+4]; unsigned __int16
0x1800d349e  call    ?IsWindowsVersionOrGreater@@YA_NGGG@Z; IsWindowsVersionOrGreater(ushort,ushort,ushort)
0x1800d34a3  test    al, al
0x1800d34a5  jz      loc_1800D3585
0x1800d34ab  xorps   xmm0, xmm0
0x1800d34ae  movups  [rbp+var_20], xmm0
0x1800d34b2  mov     dword ptr [rbp+var_20], ebx
0x1800d34b5  xor     edx, edx; hFile
0x1800d34b7  mov     r8d, 800h; dwFlags
0x1800d34bd  lea     rcx, aTbsDll; "Tbs.dll"
0x1800d34c4  call    cs:__imp_LoadLibraryExW
0x1800d34ca  lea     rsi, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x1800d34d1  mov     [rbp+var_30], rsi
0x1800d34d5  mov     [rbp+var_28], rax
0x1800d34d9  test    rax, rax
0x1800d34dc  jz      loc_1800D3585
0x1800d34e2  lea     rdx, aTbsiGetdevicei; "Tbsi_GetDeviceInfo"
0x1800d34e9  mov     rcx, rax; hModule
0x1800d34ec  call    cs:__imp_GetProcAddress
0x1800d34f2  test    rax, rax
0x1800d34f5  jz      short loc_1800D356B
0x1800d34f7  lea     rdx, [rbp+var_20]
0x1800d34fb  lea     ecx, [rbx+0Eh]
0x1800d34fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3503  test    eax, eax
0x1800d3505  jnz     short loc_1800D352E
0x1800d3507  mov     ebx, dword ptr [rbp+var_20+4]
0x1800d350a  test    ebx, ebx
0x1800d350c  jz      short loc_1800D3551
0x1800d350e  mov     [rbp+var_30], rsi
0x1800d3512  cmp     [rbp+var_28], 0
0x1800d3517  jz      short loc_1800D352A
0x1800d3519  lea     rcx, [rbp+var_30]
0x1800d351d  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x1800d3522  test    al, al
0x1800d3524  jz      loc_1800D35F2
0x1800d352a  mov     eax, ebx
0x1800d352c  jmp     short loc_1800D3588
0x1800d352e  cmp     eax, 8028400Fh
0x1800d3533  jnz     short loc_1800D3551
0x1800d3535  mov     [rbp+var_30], rsi
0x1800d3539  cmp     [rbp+var_28], 0
0x1800d353e  jz      short loc_1800D354D
0x1800d3540  lea     rcx, [rbp+var_30]
0x1800d3544  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x1800d3549  test    al, al
0x1800d354b  jz      short loc_1800D35A4
0x1800d354d  xor     eax, eax
0x1800d354f  jmp     short loc_1800D3588
0x1800d3551  mov     [rbp+var_30], rsi
0x1800d3555  cmp     [rbp+var_28], 0
0x1800d355a  jz      short loc_1800D3585
0x1800d355c  lea     rcx, [rbp+var_30]
0x1800d3560  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x1800d3565  test    al, al
0x1800d3567  jz      short loc_1800D35BE
0x1800d3569  jmp     short loc_1800D3585
0x1800d356b  mov     [rbp+var_30], rsi
0x1800d356f  cmp     [rbp+var_28], 0
0x1800d3574  jz      short loc_1800D3585
0x1800d3576  lea     rcx, [rbp+var_30]
0x1800d357a  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x1800d357f  test    al, al
0x1800d3581  jz      short loc_1800D35D8
0x1800d3583  jmp     short $+2
0x1800d3585  or      eax, 0FFFFFFFFh
0x1800d3588  mov     rcx, [rbp+var_10]
0x1800d358c  xor     rcx, rsp; StackCookie
0x1800d358f  call    __security_check_cookie
0x1800d3594  mov     rbx, [rsp+50h+arg_0]
0x1800d3599  mov     rsi, [rsp+50h+arg_8]
0x1800d359e  add     rsp, 50h
0x1800d35a2  pop     rbp
0x1800d35a3  retn
0x1800d35a4  call    cs:__imp_GetLastError
0x1800d35aa  test    eax, eax
0x1800d35ac  jle     short loc_1800D35B6
0x1800d35ae  movzx   eax, ax
0x1800d35b1  or      eax, 80070000h
0x1800d35b6  mov     ecx, eax; this
0x1800d35b8  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800d35bd  int     3; Trap to Debugger
0x1800d35be  call    cs:__imp_GetLastError
0x1800d35c4  test    eax, eax
0x1800d35c6  jle     short loc_1800D35D0
0x1800d35c8  movzx   eax, ax
0x1800d35cb  or      eax, 80070000h
0x1800d35d0  mov     ecx, eax; this
0x1800d35d2  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800d35d7  int     3; Trap to Debugger
0x1800d35d8  call    cs:__imp_GetLastError
0x1800d35de  test    eax, eax
0x1800d35e0  jle     short loc_1800D35EA
0x1800d35e2  movzx   eax, ax
0x1800d35e5  or      eax, 80070000h
0x1800d35ea  mov     ecx, eax; this
0x1800d35ec  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800d35f1  int     3; Trap to Debugger
0x1800d35f2  call    cs:__imp_GetLastError
0x1800d35f8  test    eax, eax
0x1800d35fa  jle     short loc_1800D3604
0x1800d35fc  movzx   eax, ax
0x1800d35ff  or      eax, 80070000h
0x1800d3604  mov     ecx, eax; this
0x1800d3606  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
