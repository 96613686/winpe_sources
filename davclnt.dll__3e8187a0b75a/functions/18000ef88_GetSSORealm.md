# GetSSORealm

- ea: `0x18000ef88`
- end: `0x18000f041`
- name: `GetSSORealm`
- size: `185`
- prototype: `__int64 __fastcall(LPBYTE lpData)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18001068c`

## callees

- `0x18000ef88`
- `0x1800102c0`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000efe5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000efe5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000eff8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000eff8`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000efcd`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000efcd`

## string_xrefs

- `0x18000efc6`: `wininet.dll`

## pseudocode

```c
__int64 __fastcall GetSSORealm(LPBYTE lpData)
{
  HMODULE LibraryW; // rax
  HMODULE v3; // rdi
  void (*ProcAddress)(void); // rax

  if ( !lpData )
    return 87;
  *(_WORD *)lpData = 0;
  if ( (unsigned int)ReadPassportRealmFromRegistry(lpData, HKEY_LOCAL_MACHINE)
    || (unsigned int)ReadPassportRealmFromRegistry(lpData, HKEY_CURRENT_USER) )
  {
    return 0;
  }
  LibraryW = LoadLibraryW(L"wininet.dll");
  v3 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = (void (*)(void))GetProcAddress(LibraryW, "ForceNexusLookup");
    if ( ProcAddress )
      ProcAddress();
    FreeLibrary(v3);
  }
  if ( (unsigned int)ReadPassportRealmFromRegistry(lpData, HKEY_LOCAL_MACHINE) )
    return 0;
  else
    return (unsigned int)ReadPassportRealmFromRegistry(lpData, HKEY_CURRENT_USER) == 0 ? 0x54F : 0;
}

```

## disassembly

```asm
0x18000ef88  mov     [rsp+arg_0], rbx
0x18000ef8d  push    rdi
0x18000ef8e  sub     rsp, 20h
0x18000ef92  mov     rbx, rcx
0x18000ef95  test    rcx, rcx
0x18000ef98  jz      loc_18000F031
0x18000ef9e  xor     eax, eax
0x18000efa0  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18000efa7  mov     [rcx], ax
0x18000efaa  call    ReadPassportRealmFromRegistry
0x18000efaf  test    eax, eax
0x18000efb1  jnz     short loc_18000F02D
0x18000efb3  mov     rdx, 0FFFFFFFF80000001h; hKey
0x18000efba  mov     rcx, rbx; lpData
0x18000efbd  call    ReadPassportRealmFromRegistry
0x18000efc2  test    eax, eax
0x18000efc4  jnz     short loc_18000F02D
0x18000efc6  lea     rcx, aWininetDll_0; "wininet.dll"
0x18000efcd  call    cs:__imp_LoadLibraryW
0x18000efd3  mov     rdi, rax
0x18000efd6  test    rax, rax
0x18000efd9  jz      short loc_18000EFFE
0x18000efdb  lea     rdx, aForcenexuslook; "ForceNexusLookup"
0x18000efe2  mov     rcx, rax; hModule
0x18000efe5  call    cs:__imp_GetProcAddress
0x18000efeb  test    rax, rax
0x18000efee  jz      short loc_18000EFF5
0x18000eff0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eff5  mov     rcx, rdi; hLibModule
0x18000eff8  call    cs:__imp_FreeLibrary
0x18000effe  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18000f005  mov     rcx, rbx; lpData
0x18000f008  call    ReadPassportRealmFromRegistry
0x18000f00d  test    eax, eax
0x18000f00f  jnz     short loc_18000F02D
0x18000f011  mov     rdx, 0FFFFFFFF80000001h; hKey
0x18000f018  mov     rcx, rbx; lpData
0x18000f01b  call    ReadPassportRealmFromRegistry
0x18000f020  neg     eax
0x18000f022  sbb     eax, eax
0x18000f024  not     eax
0x18000f026  and     eax, 54Fh
0x18000f02b  jmp     short loc_18000F036
0x18000f02d  xor     eax, eax
0x18000f02f  jmp     short loc_18000F036
0x18000f031  mov     eax, 57h ; 'W'
0x18000f036  mov     rbx, [rsp+28h+arg_0]
0x18000f03b  add     rsp, 20h
0x18000f03f  pop     rdi
0x18000f040  retn
```
