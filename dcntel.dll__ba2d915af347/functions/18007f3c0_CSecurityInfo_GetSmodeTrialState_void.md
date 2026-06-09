# CSecurityInfo::GetSmodeTrialState(void)

- ea: `0x18007f3c0`
- end: `0x18007f4d7`
- name: `?GetSmodeTrialState@CSecurityInfo@@QEBAIXZ`
- size: `279`
- prototype: `unsigned int __fastcall(CSecurityInfo *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001daf0`
- `0x18001dcc8`
- `0x18007f3c0`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18007f3e8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18007f3e8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007f411`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007f411`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f489`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f4a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f4bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f489`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f4a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f4bd`

## string_xrefs

- `0x18007f3e1`: `wldp.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSecurityInfo::GetSmodeTrialState(CSecurityInfo *this)
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

  v16 = 0;
  Library = LoadLibraryExW(L"wldp.dll", 0, 0x800u);
  v14 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  v15 = Library;
  if ( !Library )
    return 0xFFFFFFFFLL;
  ProcAddress = GetProcAddress(Library, "WldpQueryWindowsLockdownMode");
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
  if ( ((int (__fastcall *)(unsigned int *))ProcAddress)(&v16) < 0 )
  {
    v14 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
    if ( v15 && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v14) )
    {
      v11 = GetLastError();
      if ( v11 > 0 )
        v11 = (unsigned __int16)v11 | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v11, v12, v13);
      JUMPOUT(0x18007F4D6LL);
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
0x18007f3c0  mov     [rsp-8+arg_0], rbx
0x18007f3c5  mov     [rsp-8+arg_10], rsi
0x18007f3ca  push    rbp
0x18007f3cb  mov     rbp, rsp
0x18007f3ce  sub     rsp, 30h
0x18007f3d2  mov     [rbp+arg_8], 0
0x18007f3d9  xor     edx, edx; hFile
0x18007f3db  mov     r8d, 800h; dwFlags
0x18007f3e1  lea     rcx, aWldpDll_0; "wldp.dll"
0x18007f3e8  call    cs:__imp_LoadLibraryExW
0x18007f3ee  lea     rsi, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x18007f3f5  mov     [rbp+var_10], rsi
0x18007f3f9  mov     [rbp+var_8], rax
0x18007f3fd  test    rax, rax
0x18007f400  jnz     short loc_18007F407
0x18007f402  or      eax, 0FFFFFFFFh
0x18007f405  jmp     short loc_18007F479
0x18007f407  lea     rdx, aWldpquerywindo; "WldpQueryWindowsLockdownMode"
0x18007f40e  mov     rcx, rax; hModule
0x18007f411  call    cs:__imp_GetProcAddress
0x18007f417  test    rax, rax
0x18007f41a  jnz     short loc_18007F435
0x18007f41c  mov     [rbp+var_10], rsi
0x18007f420  cmp     [rbp+var_8], rax
0x18007f424  jz      short loc_18007F402
0x18007f426  lea     rcx, [rbp+var_10]
0x18007f42a  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x18007f42f  test    al, al
0x18007f431  jz      short loc_18007F4A3
0x18007f433  jmp     short loc_18007F402
0x18007f435  lea     rcx, [rbp+arg_8]
0x18007f439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f43e  test    eax, eax
0x18007f440  jns     short loc_18007F45C
0x18007f442  mov     [rbp+var_10], rsi
0x18007f446  cmp     [rbp+var_8], 0
0x18007f44b  jz      short loc_18007F402
0x18007f44d  lea     rcx, [rbp+var_10]
0x18007f451  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x18007f456  test    al, al
0x18007f458  jz      short loc_18007F4BD
0x18007f45a  jmp     short loc_18007F402
0x18007f45c  mov     ebx, [rbp+arg_8]
0x18007f45f  mov     [rbp+var_10], rsi
0x18007f463  cmp     [rbp+var_8], 0
0x18007f468  jz      short loc_18007F477
0x18007f46a  lea     rcx, [rbp+var_10]
0x18007f46e  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x18007f473  test    al, al
0x18007f475  jz      short loc_18007F489
0x18007f477  mov     eax, ebx
0x18007f479  mov     rbx, [rsp+30h+arg_0]
0x18007f47e  mov     rsi, [rsp+30h+arg_10]
0x18007f483  add     rsp, 30h
0x18007f487  pop     rbp
0x18007f488  retn
0x18007f489  call    cs:__imp_GetLastError
0x18007f48f  test    eax, eax
0x18007f491  jle     short loc_18007F49B
0x18007f493  movzx   eax, ax
0x18007f496  or      eax, 80070000h
0x18007f49b  mov     ecx, eax; this
0x18007f49d  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18007f4a2  int     3; Trap to Debugger
0x18007f4a3  call    cs:__imp_GetLastError
0x18007f4a9  test    eax, eax
0x18007f4ab  jle     short loc_18007F4B5
0x18007f4ad  movzx   eax, ax
0x18007f4b0  or      eax, 80070000h
0x18007f4b5  mov     ecx, eax; this
0x18007f4b7  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18007f4bc  int     3; Trap to Debugger
0x18007f4bd  call    cs:__imp_GetLastError
0x18007f4c3  test    eax, eax
0x18007f4c5  jle     short loc_18007F4CF
0x18007f4c7  movzx   eax, ax
0x18007f4ca  or      eax, 80070000h
0x18007f4cf  mov     ecx, eax; this
0x18007f4d1  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
