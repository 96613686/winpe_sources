# COsInfo::GetDeveloperUnlock(void)

- ea: `0x180056a90`
- end: `0x180056bb5`
- name: `?GetDeveloperUnlock@COsInfo@@QEBAIXZ`
- size: `293`
- prototype: `unsigned int __fastcall(COsInfo *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18001daf0`
- `0x18001dcc8`
- `0x180056a90`
- `0x1800d2e3c`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180056ac5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180056ac5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180056aed`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180056b01`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180056aed`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180056b01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056b9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056b9b`

## string_xrefs

- `0x180056abe`: `api-ms-win-appmodel-unlock-l1-1-0.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall COsInfo::GetDeveloperUnlock(COsInfo *this)
{
  unsigned int v1; // ebx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rsi
  FARPROC v4; // rax
  int (__fastcall *v5)(BOOL *); // rdi
  int RegistryKeyDWORDOrDefault; // eax
  BOOL v7; // eax
  signed int LastError; // eax
  int v10; // edx
  unsigned int v11; // r8d
  const int *v12; // [rsp+20h] [rbp-10h] BYREF
  HMODULE hModule; // [rsp+28h] [rbp-8h]
  BOOL v14; // [rsp+58h] [rbp+28h] BYREF
  int v15; // [rsp+60h] [rbp+30h] BYREF

  v1 = -1;
  v15 = 0;
  v14 = 0;
  Library = LoadLibraryExW(L"api-ms-win-appmodel-unlock-l1-1-0.dll", 0, 0x800u);
  v12 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  hModule = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "IsDeveloperModeEnabled");
    v4 = GetProcAddress(hModule, "IsDeveloperModePolicyApplied");
    v5 = (int (__fastcall *)(BOOL *))v4;
    if ( ProcAddress )
    {
      if ( v4 && ((int (__fastcall *)(int *))ProcAddress)(&v15) >= 0 && v5(&v14) >= 0 )
      {
        RegistryKeyDWORDOrDefault = Utils::GetRegistryKeyDWORDOrDefault(
                                      L"SOFTWARE\\Policies\\Microsoft\\Windows\\Appx",
                                      L"AllowDevelopmentWithoutDevLicense",
                                      0xFFFFFFFF);
        v1 = 1;
        v7 = v14 && RegistryKeyDWORDOrDefault == 1;
        v14 = v7;
        if ( !v15 && !v7 )
          v1 = 0;
      }
    }
  }
  v12 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  if ( hModule && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v12) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v10, v11);
    JUMPOUT(0x180056BB4LL);
  }
  return v1;
}

```

## disassembly

```asm
0x180056a90  mov     [rsp-18h+arg_0], rbx
0x180056a95  mov     [rsp-18h+arg_18], rsi
0x180056a9a  push    rbp
0x180056a9b  push    rdi
0x180056a9c  push    r15
0x180056a9e  mov     rbp, rsp
0x180056aa1  sub     rsp, 30h
0x180056aa5  or      ebx, 0FFFFFFFFh
0x180056aa8  mov     [rbp+arg_10], 0
0x180056aaf  mov     [rbp+arg_8], 0
0x180056ab6  xor     edx, edx; hFile
0x180056ab8  mov     r8d, 800h; dwFlags
0x180056abe  lea     rcx, aApiMsWinAppmod; "api-ms-win-appmodel-unlock-l1-1-0.dll"
0x180056ac5  call    cs:__imp_LoadLibraryExW
0x180056acb  lea     r15, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x180056ad2  mov     [rbp+var_10], r15
0x180056ad6  mov     [rbp+hModule], rax
0x180056ada  test    rax, rax
0x180056add  jz      loc_180056B6E
0x180056ae3  lea     rdx, aIsdevelopermod_0; "IsDeveloperModeEnabled"
0x180056aea  mov     rcx, rax; hModule
0x180056aed  call    cs:__imp_GetProcAddress
0x180056af3  mov     rsi, rax
0x180056af6  lea     rdx, aIsdevelopermod; "IsDeveloperModePolicyApplied"
0x180056afd  mov     rcx, [rbp+hModule]; hModule
0x180056b01  call    cs:__imp_GetProcAddress
0x180056b07  mov     rdi, rax
0x180056b0a  test    rsi, rsi
0x180056b0d  jz      short loc_180056B6E
0x180056b0f  test    rax, rax
0x180056b12  jz      short loc_180056B6E
0x180056b14  lea     rcx, [rbp+arg_10]
0x180056b18  mov     rax, rsi
0x180056b1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056b20  test    eax, eax
0x180056b22  js      short loc_180056B6E
0x180056b24  lea     rcx, [rbp+arg_8]
0x180056b28  mov     rax, rdi
0x180056b2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056b30  test    eax, eax
0x180056b32  js      short loc_180056B6E
0x180056b34  mov     r8d, ebx; unsigned int
0x180056b37  lea     rdx, aAllowdevelopme; "AllowDevelopmentWithoutDevLicense"
0x180056b3e  lea     rcx, aSoftwarePolici_2; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x180056b45  call    ?GetRegistryKeyDWORDOrDefault@Utils@@SAKPEBG0K@Z; Utils::GetRegistryKeyDWORDOrDefault(ushort const *,ushort const *,ulong)
0x180056b4a  mov     ebx, 1
0x180056b4f  cmp     [rbp+arg_8], 0
0x180056b53  jz      short loc_180056B5D
0x180056b55  cmp     eax, ebx
0x180056b57  jnz     short loc_180056B5D
0x180056b59  mov     eax, ebx
0x180056b5b  jmp     short loc_180056B5F
0x180056b5d  xor     eax, eax
0x180056b5f  mov     [rbp+arg_8], eax
0x180056b62  cmp     [rbp+arg_10], 0
0x180056b66  jnz     short loc_180056B6E
0x180056b68  test    eax, eax
0x180056b6a  jnz     short loc_180056B6E
0x180056b6c  xor     ebx, ebx
0x180056b6e  mov     [rbp+var_10], r15
0x180056b72  cmp     [rbp+hModule], 0
0x180056b77  jz      short loc_180056B86
0x180056b79  lea     rcx, [rbp+var_10]
0x180056b7d  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x180056b82  test    al, al
0x180056b84  jz      short loc_180056B9B
0x180056b86  mov     eax, ebx
0x180056b88  mov     rbx, [rsp+30h+arg_0]
0x180056b8d  mov     rsi, [rsp+30h+arg_18]
0x180056b92  add     rsp, 30h
0x180056b96  pop     r15
0x180056b98  pop     rdi
0x180056b99  pop     rbp
0x180056b9a  retn
0x180056b9b  call    cs:__imp_GetLastError
0x180056ba1  test    eax, eax
0x180056ba3  jle     short loc_180056BAD
0x180056ba5  movzx   eax, ax
0x180056ba8  or      eax, 80070000h
0x180056bad  mov     ecx, eax; this
0x180056baf  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
