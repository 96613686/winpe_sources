# OSInfo::GetGenuineState(void)

- ea: `0x180056cb0`
- end: `0x180056de4`
- name: `?GetGenuineState@OSInfo@@QEBAIXZ`
- size: `308`
- prototype: `unsigned int __fastcall(OSInfo *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001daf0`
- `0x18001dcc8`
- `0x180056cb0`
- `0x180056dec`
- `0x1800cd1fc`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180056ceb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180056ceb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180056d14`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180056d14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056d96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056db0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056dca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056d96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056db0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056dca`

## string_xrefs

- `0x180056ce4`: `slwga.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OSInfo::GetGenuineState(OSInfo *this)
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
  if ( SystemRequirements::IsWindowsCore() )
    return COsInfo::GetGenuineState_WindowsCore();
  Library = LoadLibraryExW(L"slwga.dll", 0, 0x800u);
  v14 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  v15 = Library;
  if ( !Library )
    return 0xFFFFFFFFLL;
  ProcAddress = GetProcAddress(Library, "SLIsGenuineLocal");
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
  if ( ((int (__fastcall *)(const GUID *, unsigned int *, _QWORD))ProcAddress)(&WINDOWS_SLID, &v16, 0) < 0 )
  {
    v14 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
    if ( v15 && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v14) )
    {
      v11 = GetLastError();
      if ( v11 > 0 )
        v11 = (unsigned __int16)v11 | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v11, v12, v13);
      JUMPOUT(0x180056DE3LL);
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
0x180056cb0  mov     [rsp-8+arg_0], rbx
0x180056cb5  mov     [rsp-8+arg_10], rsi
0x180056cba  push    rbp
0x180056cbb  mov     rbp, rsp
0x180056cbe  sub     rsp, 30h
0x180056cc2  mov     [rbp+arg_8], 0
0x180056cc9  call    ?IsWindowsCore@SystemRequirements@@SA_NXZ; SystemRequirements::IsWindowsCore(void)
0x180056cce  test    al, al
0x180056cd0  jz      short loc_180056CDC
0x180056cd2  call    ?GetGenuineState_WindowsCore@COsInfo@@CAIXZ; COsInfo::GetGenuineState_WindowsCore(void)
0x180056cd7  jmp     loc_180056D86
0x180056cdc  xor     edx, edx; hFile
0x180056cde  mov     r8d, 800h; dwFlags
0x180056ce4  lea     rcx, aSlwgaDll; "slwga.dll"
0x180056ceb  call    cs:__imp_LoadLibraryExW
0x180056cf1  lea     rsi, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x180056cf8  mov     [rbp+var_10], rsi
0x180056cfc  mov     [rbp+var_8], rax
0x180056d00  test    rax, rax
0x180056d03  jnz     short loc_180056D0A
0x180056d05  or      eax, 0FFFFFFFFh
0x180056d08  jmp     short loc_180056D86
0x180056d0a  lea     rdx, aSlisgenuineloc; "SLIsGenuineLocal"
0x180056d11  mov     rcx, rax; hModule
0x180056d14  call    cs:__imp_GetProcAddress
0x180056d1a  test    rax, rax
0x180056d1d  jnz     short loc_180056D38
0x180056d1f  mov     [rbp+var_10], rsi
0x180056d23  cmp     [rbp+var_8], rax
0x180056d27  jz      short loc_180056D05
0x180056d29  lea     rcx, [rbp+var_10]
0x180056d2d  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x180056d32  test    al, al
0x180056d34  jz      short loc_180056DB0
0x180056d36  jmp     short loc_180056D05
0x180056d38  xor     r8d, r8d
0x180056d3b  lea     rdx, [rbp+arg_8]
0x180056d3f  lea     rcx, WINDOWS_SLID
0x180056d46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056d4b  test    eax, eax
0x180056d4d  jns     short loc_180056D69
0x180056d4f  mov     [rbp+var_10], rsi
0x180056d53  cmp     [rbp+var_8], 0
0x180056d58  jz      short loc_180056D05
0x180056d5a  lea     rcx, [rbp+var_10]
0x180056d5e  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x180056d63  test    al, al
0x180056d65  jz      short loc_180056DCA
0x180056d67  jmp     short loc_180056D05
0x180056d69  mov     ebx, [rbp+arg_8]
0x180056d6c  mov     [rbp+var_10], rsi
0x180056d70  cmp     [rbp+var_8], 0
0x180056d75  jz      short loc_180056D84
0x180056d77  lea     rcx, [rbp+var_10]
0x180056d7b  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x180056d80  test    al, al
0x180056d82  jz      short loc_180056D96
0x180056d84  mov     eax, ebx
0x180056d86  mov     rbx, [rsp+30h+arg_0]
0x180056d8b  mov     rsi, [rsp+30h+arg_10]
0x180056d90  add     rsp, 30h
0x180056d94  pop     rbp
0x180056d95  retn
0x180056d96  call    cs:__imp_GetLastError
0x180056d9c  test    eax, eax
0x180056d9e  jle     short loc_180056DA8
0x180056da0  movzx   eax, ax
0x180056da3  or      eax, 80070000h
0x180056da8  mov     ecx, eax; this
0x180056daa  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180056daf  int     3; Trap to Debugger
0x180056db0  call    cs:__imp_GetLastError
0x180056db6  test    eax, eax
0x180056db8  jle     short loc_180056DC2
0x180056dba  movzx   eax, ax
0x180056dbd  or      eax, 80070000h
0x180056dc2  mov     ecx, eax; this
0x180056dc4  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180056dc9  int     3; Trap to Debugger
0x180056dca  call    cs:__imp_GetLastError
0x180056dd0  test    eax, eax
0x180056dd2  jle     short loc_180056DDC
0x180056dd4  movzx   eax, ax
0x180056dd7  or      eax, 80070000h
0x180056ddc  mov     ecx, eax; this
0x180056dde  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
