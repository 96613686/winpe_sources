# MsiGetSystemDirectory(ushort *,uint,int)

- ea: `0x1400095e4`
- end: `0x140009694`
- name: `?MsiGetSystemDirectory@@YAIPEAGIH@Z`
- size: `176`
- prototype: `unsigned int __fastcall(unsigned __int16 *, unsigned int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x14000953c`

## callees

- `0x1400095e4`
- `0x14000a010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x14000966f`
- `KERNEL32!SetLastError` at `0x14000966f`
- `KERNEL32!GetLastError` at `0x140009632`
- `KERNEL32!GetLastError` at `0x14000965c`
- `KERNEL32!GetLastError` at `0x140009632`
- `KERNEL32!GetLastError` at `0x14000965c`
- `KERNEL32!LoadLibraryW` at `0x14000960f`
- `KERNEL32!LoadLibraryW` at `0x14000960f`
- `KERNEL32!GetProcAddress` at `0x140009627`
- `KERNEL32!GetProcAddress` at `0x140009627`
- `KERNEL32!FreeLibrary` at `0x140009667`
- `KERNEL32!FreeLibrary` at `0x140009667`
- `KERNEL32!GetSystemDirectoryW` at `0x14000967e`
- `KERNEL32!GetSystemDirectoryW` at `0x14000967e`

## string_xrefs

- `0x14000961d`: `GetSystemWow64DirectoryW`
- `0x140009608`: `kernel32.dll`

## pseudocode

```c
unsigned int __fastcall MsiGetSystemDirectory(unsigned __int16 *a1)
{
  HMODULE LibraryW; // rax
  HMODULE v3; // rsi
  FARPROC ProcAddress; // rax
  DWORD LastError; // eax
  int v6; // edi
  int v7; // eax
  DWORD v8; // ebx

  if ( g_fWoW || !g_fWinNT64 )
  {
    LODWORD(LibraryW) = GetSystemDirectoryW(a1, 0x105u);
    return (unsigned int)LibraryW;
  }
  LibraryW = LoadLibraryW(L"kernel32.dll");
  v3 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "GetSystemWow64DirectoryW");
    if ( ProcAddress )
    {
      v7 = ((__int64 (__fastcall *)(unsigned __int16 *, __int64))ProcAddress)(a1, 261);
      v8 = 0;
      v6 = v7;
      if ( (unsigned int)(v7 - 1) <= 0x104 || v7 )
        goto LABEL_10;
      LastError = GetLastError();
    }
    else
    {
      LastError = GetLastError();
      v6 = 0;
    }
    v8 = LastError;
LABEL_10:
    FreeLibrary(v3);
    SetLastError(v8);
    LODWORD(LibraryW) = v6;
  }
  return (unsigned int)LibraryW;
}

```

## disassembly

```asm
0x1400095e4  mov     [rsp+arg_0], rbx
0x1400095e9  mov     [rsp+arg_8], rsi
0x1400095ee  push    rdi
0x1400095ef  sub     rsp, 20h
0x1400095f3  cmp     cs:?g_fWoW@@3_NA, 0; bool g_fWoW
0x1400095fa  mov     rbx, rcx
0x1400095fd  jnz     short loc_140009679
0x1400095ff  cmp     cs:?g_fWinNT64@@3_NA, 0; bool g_fWinNT64
0x140009606  jz      short loc_140009679
0x140009608  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x14000960f  call    cs:__imp_LoadLibraryW
0x140009615  mov     rsi, rax
0x140009618  test    rax, rax
0x14000961b  jz      short loc_140009684
0x14000961d  lea     rdx, aGetsystemwow64; "GetSystemWow64DirectoryW"
0x140009624  mov     rcx, rsi; hModule
0x140009627  call    cs:__imp_GetProcAddress
0x14000962d  test    rax, rax
0x140009630  jnz     short loc_14000963C
0x140009632  call    cs:__imp_GetLastError
0x140009638  xor     edi, edi
0x14000963a  jmp     short loc_140009662
0x14000963c  mov     edx, 105h
0x140009641  mov     rcx, rbx
0x140009644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009649  xor     ebx, ebx
0x14000964b  mov     edi, eax
0x14000964d  lea     ecx, [rax-1]
0x140009650  cmp     ecx, 104h
0x140009656  jbe     short loc_140009664
0x140009658  test    eax, eax
0x14000965a  jnz     short loc_140009664
0x14000965c  call    cs:__imp_GetLastError
0x140009662  mov     ebx, eax
0x140009664  mov     rcx, rsi; hLibModule
0x140009667  call    cs:__imp_FreeLibrary
0x14000966d  mov     ecx, ebx; dwErrCode
0x14000966f  call    cs:__imp_SetLastError
0x140009675  mov     eax, edi
0x140009677  jmp     short loc_140009684
0x140009679  mov     edx, 105h; uSize
0x14000967e  call    cs:__imp_GetSystemDirectoryW
0x140009684  mov     rbx, [rsp+28h+arg_0]
0x140009689  mov     rsi, [rsp+28h+arg_8]
0x14000968e  add     rsp, 20h
0x140009692  pop     rdi
0x140009693  retn
```
