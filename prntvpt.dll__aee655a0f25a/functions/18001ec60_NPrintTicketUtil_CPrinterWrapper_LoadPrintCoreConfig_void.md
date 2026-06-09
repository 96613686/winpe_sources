# NPrintTicketUtil::CPrinterWrapper::LoadPrintCoreConfig(void)

- ea: `0x18001ec60`
- end: `0x18001ecdd`
- name: `?LoadPrintCoreConfig@CPrinterWrapper@NPrintTicketUtil@@AEAAKXZ`
- size: `125`
- prototype: `unsigned int __fastcall(NPrintTicketUtil::CPrinterWrapper *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x18000a560`

## callees

- `0x18001ec60`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001ecac`
- `KERNEL32!GetLastError` at `0x18001ecc8`
- `KERNEL32!GetLastError` at `0x18001ecac`
- `KERNEL32!GetLastError` at `0x18001ecc8`
- `KERNEL32!GetProcAddress` at `0x18001ec9d`
- `KERNEL32!GetProcAddress` at `0x18001ec9d`
- `KERNEL32!LoadLibraryExW` at `0x18001ec84`
- `KERNEL32!LoadLibraryExW` at `0x18001ec84`
- `KERNEL32!FreeLibrary` at `0x18001ecb8`
- `KERNEL32!FreeLibrary` at `0x18001ecb8`

## string_xrefs

- `0x18001ec77`: `PrintCoreConfig.dll`

## pseudocode

```c
__int64 __fastcall NPrintTicketUtil::CPrinterWrapper::LoadPrintCoreConfig(NPrintTicketUtil::CPrinterWrapper *this)
{
  DWORD LastError; // ebx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax

  LastError = 0;
  if ( !*((_QWORD *)this + 6) )
  {
    Library = LoadLibraryExW(L"PrintCoreConfig.dll", 0, 0x800u);
    *((_QWORD *)this + 5) = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "PTGetDeviceCapability");
      *((_QWORD *)this + 6) = ProcAddress;
      if ( !ProcAddress )
      {
        LastError = GetLastError();
        FreeLibrary(*((HMODULE *)this + 5));
        *((_QWORD *)this + 5) = 0;
      }
    }
    else
    {
      return GetLastError();
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x18001ec60  mov     [rsp+arg_0], rbx
0x18001ec65  push    rdi
0x18001ec66  sub     rsp, 20h
0x18001ec6a  xor     ebx, ebx
0x18001ec6c  mov     rdi, rcx
0x18001ec6f  cmp     [rcx+30h], rbx
0x18001ec73  jnz     short loc_18001ECD0
0x18001ec75  xor     edx, edx; hFile
0x18001ec77  lea     rcx, aPrintcoreconfi; "PrintCoreConfig.dll"
0x18001ec7e  mov     r8d, 800h; dwFlags
0x18001ec84  call    cs:__imp_LoadLibraryExW
0x18001ec8a  mov     [rdi+28h], rax
0x18001ec8e  test    rax, rax
0x18001ec91  jz      short loc_18001ECC8
0x18001ec93  lea     rdx, aPtgetdevicecap; "PTGetDeviceCapability"
0x18001ec9a  mov     rcx, rax; hModule
0x18001ec9d  call    cs:__imp_GetProcAddress
0x18001eca3  mov     [rdi+30h], rax
0x18001eca7  test    rax, rax
0x18001ecaa  jnz     short loc_18001ECD0
0x18001ecac  call    cs:__imp_GetLastError
0x18001ecb2  mov     rcx, [rdi+28h]; hLibModule
0x18001ecb6  mov     ebx, eax
0x18001ecb8  call    cs:__imp_FreeLibrary
0x18001ecbe  mov     qword ptr [rdi+28h], 0
0x18001ecc6  jmp     short loc_18001ECD0
0x18001ecc8  call    cs:__imp_GetLastError
0x18001ecce  mov     ebx, eax
0x18001ecd0  mov     eax, ebx
0x18001ecd2  mov     rbx, [rsp+28h+arg_0]
0x18001ecd7  add     rsp, 20h
0x18001ecdb  pop     rdi
0x18001ecdc  retn
```
