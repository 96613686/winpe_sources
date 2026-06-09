# LoadSecurity

- ea: `0x1800995ac`
- end: `0x180099650`
- name: `LoadSecurity`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800993f8`

## callees

- `0x180098a74`
- `0x1800995ac`
- `0x1800cd010`

## import_xrefs

- `KERNEL32!LoadLibraryA` at `0x1800995d1`
- `KERNEL32!LoadLibraryA` at `0x1800995d1`
- `KERNEL32!GetProcAddress` at `0x1800995ed`
- `KERNEL32!GetProcAddress` at `0x1800995ed`
- `KERNEL32!GetLastError` at `0x180099612`
- `KERNEL32!GetLastError` at `0x180099612`
- `KERNEL32!FreeLibrary` at `0x18009962a`
- `KERNEL32!FreeLibrary` at `0x18009962a`
- `KERNEL32!LeaveCriticalSection` at `0x180099642`
- `KERNEL32!LeaveCriticalSection` at `0x180099642`
- `KERNEL32!EnterCriticalSection` at `0x1800995bb`
- `KERNEL32!EnterCriticalSection` at `0x1800995bb`

## string_xrefs

- `0x1800995e3`: `InitSecurityInterfaceA`

## pseudocode

```c
__int64 LoadSecurity()
{
  DWORD LastError; // ebx
  HMODULE LibraryA; // rax
  __int64 (*ProcAddress)(void); // rax

  LastError = 0;
  EnterCriticalSection(&CriticalSection);
  if ( !hLibModule )
  {
    LibraryA = LoadLibraryA("schannel");
    hLibModule = LibraryA;
    if ( !LibraryA
      || (ProcAddress = GetProcAddress(LibraryA, "InitSecurityInterfaceA")) == 0
      || (g_pSecFuncTable = ProcAddress()) == 0
      || !(unsigned int)SecurityPkgInitialize() )
    {
      LastError = GetLastError();
      if ( LastError && hLibModule )
      {
        FreeLibrary(hLibModule);
        hLibModule = 0;
      }
    }
  }
  LeaveCriticalSection(&CriticalSection);
  return LastError;
}

```

## disassembly

```asm
0x1800995ac  push    rbx
0x1800995ae  sub     rsp, 20h
0x1800995b2  lea     rcx, CriticalSection; lpCriticalSection
0x1800995b9  xor     ebx, ebx
0x1800995bb  call    cs:__imp_EnterCriticalSection
0x1800995c1  cmp     cs:hLibModule, rbx
0x1800995c8  jnz     short loc_18009963B
0x1800995ca  lea     rcx, aSchannel; "schannel"
0x1800995d1  call    cs:__imp_LoadLibraryA
0x1800995d7  mov     cs:hLibModule, rax
0x1800995de  test    rax, rax
0x1800995e1  jz      short loc_180099612
0x1800995e3  lea     rdx, aInitsecurityin; "InitSecurityInterfaceA"
0x1800995ea  mov     rcx, rax; hModule
0x1800995ed  call    cs:__imp_GetProcAddress
0x1800995f3  test    rax, rax
0x1800995f6  jz      short loc_180099612
0x1800995f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800995fd  mov     cs:g_pSecFuncTable, rax
0x180099604  test    rax, rax
0x180099607  jz      short loc_180099612
0x180099609  call    ?SecurityPkgInitialize@@YAHXZ; SecurityPkgInitialize(void)
0x18009960e  test    eax, eax
0x180099610  jnz     short loc_18009963B
0x180099612  call    cs:__imp_GetLastError
0x180099618  mov     ebx, eax
0x18009961a  test    eax, eax
0x18009961c  jz      short loc_18009963B
0x18009961e  mov     rcx, cs:hLibModule; hLibModule
0x180099625  test    rcx, rcx
0x180099628  jz      short loc_18009963B
0x18009962a  call    cs:__imp_FreeLibrary
0x180099630  mov     cs:hLibModule, 0
0x18009963b  lea     rcx, CriticalSection; lpCriticalSection
0x180099642  call    cs:__imp_LeaveCriticalSection
0x180099648  mov     eax, ebx
0x18009964a  add     rsp, 20h
0x18009964e  pop     rbx
0x18009964f  retn
```
