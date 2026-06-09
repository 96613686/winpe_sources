# isolib_GetSxsDllFunctionPointer(char const *,__int64 (*&)(void))

- ea: `0x1800124a4`
- end: `0x18001252f`
- name: `?isolib_GetSxsDllFunctionPointer@@YA_NPEBDAEAP6A_JXZ@Z`
- size: `139`
- prototype: `bool __fastcall(LPCSTR lpProcName, __int64 (**)(void))`
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012240`
- `0x1800122a0`
- `0x180012310`
- `0x180012360`
- `0x1800123d0`
- `0x180012440`

## callees

- `0x1800124a4`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x1800124ff`
- `KERNEL32!FreeLibrary` at `0x1800124ff`
- `KERNEL32!GetProcAddress` at `0x180012514`
- `KERNEL32!GetProcAddress` at `0x180012514`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableA` at `0x1800124c7`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableA` at `0x1800124c7`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x1800124e4`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x1800124e4`

## string_xrefs

- `0x1800124dd`: `sxs.dll`

## pseudocode

```c
bool __fastcall isolib_GetSxsDllFunctionPointer(LPCSTR lpProcName, __int64 (**a2)(void))
{
  HMODULE v4; // rcx
  HMODULE LibraryA; // rax

  *a2 = 0;
  if ( GetEnvironmentVariableA("isolation_delegation", 0, 0) )
  {
    v4 = hModule;
    if ( hModule )
      goto LABEL_7;
    LibraryA = LoadLibraryA("sxs.dll");
    if ( LibraryA && _InterlockedCompareExchange64((volatile signed __int64 *)&hModule, (signed __int64)LibraryA, 0) )
      FreeLibrary(LibraryA);
    v4 = hModule;
    if ( hModule )
LABEL_7:
      *a2 = GetProcAddress(v4, lpProcName);
  }
  return *a2 != 0;
}

```

## disassembly

```asm
0x1800124a4  mov     [rsp+arg_0], rbx
0x1800124a9  push    rdi
0x1800124aa  sub     rsp, 20h
0x1800124ae  mov     rbx, rdx
0x1800124b1  mov     qword ptr [rdx], 0
0x1800124b8  mov     rdi, rcx
0x1800124bb  xor     edx, edx; lpBuffer
0x1800124bd  lea     rcx, Name; "isolation_delegation"
0x1800124c4  xor     r8d, r8d; nSize
0x1800124c7  call    cs:__imp_GetEnvironmentVariableA
0x1800124cd  test    eax, eax
0x1800124cf  jz      short loc_18001251D
0x1800124d1  mov     rcx, cs:hModule
0x1800124d8  test    rcx, rcx
0x1800124db  jnz     short loc_180012511
0x1800124dd  lea     rcx, aSxsDll; "sxs.dll"
0x1800124e4  call    cs:__imp_LoadLibraryA
0x1800124ea  mov     rcx, rax; hLibModule
0x1800124ed  test    rax, rax
0x1800124f0  jz      short loc_180012505
0x1800124f2  xor     eax, eax
0x1800124f4  lock cmpxchg cs:hModule, rcx
0x1800124fd  jz      short loc_180012505
0x1800124ff  call    cs:__imp_FreeLibrary
0x180012505  mov     rcx, cs:hModule; hModule
0x18001250c  test    rcx, rcx
0x18001250f  jz      short loc_18001251D
0x180012511  mov     rdx, rdi; lpProcName
0x180012514  call    cs:__imp_GetProcAddress
0x18001251a  mov     [rbx], rax
0x18001251d  cmp     qword ptr [rbx], 0
0x180012521  mov     rbx, [rsp+28h+arg_0]
0x180012526  setnz   al
0x180012529  add     rsp, 20h
0x18001252d  pop     rdi
0x18001252e  retn
```
