# HyperVInfo::GetIsVDI(void)

- ea: `0x180033430`
- end: `0x1800334df`
- name: `?GetIsVDI@HyperVInfo@@AEBAHXZ`
- size: `175`
- prototype: `__int64 __fastcall(HyperVInfo *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001daf0`
- `0x18001dcc8`
- `0x180033430`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180033451`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180033451`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180033477`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180033477`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800334c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800334c5`

## string_xrefs

- `0x18003344a`: `slc.dll`
- `0x180033487`: `Virtualization-DesktopAccess`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_BOOL8 __fastcall HyperVInfo::GetIsVDI(HyperVInfo *this)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  BOOL v3; // ebx
  signed int LastError; // eax
  int v6; // edx
  unsigned int v7; // r8d
  const int *v8; // [rsp+20h] [rbp-18h] BYREF
  HMODULE v9; // [rsp+28h] [rbp-10h]
  int v10; // [rsp+48h] [rbp+10h] BYREF

  v10 = 0;
  Library = LoadLibraryExW(L"slc.dll", 0, 0x800u);
  v8 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  v9 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "SLGetWindowsInformationDWORD");
    if ( ProcAddress )
      ((void (__fastcall *)(const wchar_t *, int *))ProcAddress)(L"Virtualization-DesktopAccess", &v10);
  }
  v3 = v10 == 1;
  v8 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  if ( v9 && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v8) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v6, v7);
    JUMPOUT(0x1800334DELL);
  }
  return v3;
}

```

## disassembly

```asm
0x180033430  mov     [rsp+arg_0], rbx
0x180033435  push    rdi
0x180033436  sub     rsp, 30h
0x18003343a  mov     [rsp+38h+arg_8], 0
0x180033442  xor     edx, edx; hFile
0x180033444  mov     r8d, 800h; dwFlags
0x18003344a  lea     rcx, aSlcDll; "slc.dll"
0x180033451  call    cs:__imp_LoadLibraryExW
0x180033457  lea     rdi, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x18003345e  mov     [rsp+38h+var_18], rdi
0x180033463  mov     [rsp+38h+var_10], rax
0x180033468  test    rax, rax
0x18003346b  jz      short loc_180033493
0x18003346d  lea     rdx, aSlgetwindowsin; "SLGetWindowsInformationDWORD"
0x180033474  mov     rcx, rax; hModule
0x180033477  call    cs:__imp_GetProcAddress
0x18003347d  test    rax, rax
0x180033480  jz      short loc_180033493
0x180033482  lea     rdx, [rsp+38h+arg_8]
0x180033487  lea     rcx, aVirtualization; "Virtualization-DesktopAccess"
0x18003348e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033493  xor     ebx, ebx
0x180033495  cmp     [rsp+38h+arg_8], 1
0x18003349a  setz    bl
0x18003349d  mov     [rsp+38h+var_18], rdi
0x1800334a2  cmp     [rsp+38h+var_10], 0
0x1800334a8  jz      short loc_1800334B8
0x1800334aa  lea     rcx, [rsp+38h+var_18]
0x1800334af  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x1800334b4  test    al, al
0x1800334b6  jz      short loc_1800334C5
0x1800334b8  mov     eax, ebx
0x1800334ba  mov     rbx, [rsp+38h+arg_0]
0x1800334bf  add     rsp, 30h
0x1800334c3  pop     rdi
0x1800334c4  retn
0x1800334c5  call    cs:__imp_GetLastError
0x1800334cb  test    eax, eax
0x1800334cd  jle     short loc_1800334D7
0x1800334cf  movzx   eax, ax
0x1800334d2  or      eax, 80070000h
0x1800334d7  mov     ecx, eax; this
0x1800334d9  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
