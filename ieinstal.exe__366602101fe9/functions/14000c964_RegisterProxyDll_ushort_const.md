# RegisterProxyDll(ushort const *)

- ea: `0x14000c964`
- end: `0x14000ca0a`
- name: `?RegisterProxyDll@@YAJPEBG@Z`
- size: `166`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000ca10`

## callees

- `0x14000c964`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000c99b`
- `KERNEL32!GetProcAddress` at `0x14000c99b`
- `KERNEL32!FreeLibrary` at `0x14000c9d3`
- `KERNEL32!FreeLibrary` at `0x14000c9d3`
- `KERNEL32!LoadLibraryExW` at `0x14000c97d`
- `KERNEL32!LoadLibraryExW` at `0x14000c97d`
- `KERNEL32!GetLastError` at `0x14000c9b5`
- `KERNEL32!GetLastError` at `0x14000c9e1`
- `KERNEL32!GetLastError` at `0x14000c9b5`
- `KERNEL32!GetLastError` at `0x14000c9e1`

## string_xrefs

- `0x14000c970`: `actxprxy.dll`
- `0x14000c991`: `DllRegisterServer`

## pseudocode

```c
__int64 __fastcall RegisterProxyDll(const unsigned __int16 *a1)
{
  HMODULE Library; // rax
  HMODULE v2; // rdi
  __int64 (*ProcAddress)(void); // rax
  unsigned int v4; // ebx
  signed int LastError; // eax
  signed int v6; // eax

  Library = LoadLibraryExW(L"actxprxy.dll", 0, 0x1000u);
  v2 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "DllRegisterServer");
    if ( ProcAddress )
    {
      v4 = ProcAddress();
    }
    else
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
    }
    FreeLibrary(v2);
  }
  else
  {
    v6 = GetLastError();
    v4 = v6;
    if ( v6 > 0 )
      return (unsigned __int16)v6 | 0x80070000;
  }
  return v4;
}

```

## disassembly

```asm
0x14000c964  mov     [rsp+arg_0], rbx
0x14000c969  push    rdi
0x14000c96a  sub     rsp, 20h
0x14000c96e  xor     edx, edx; hFile
0x14000c970  lea     rcx, aActxprxyDll; "actxprxy.dll"
0x14000c977  mov     r8d, 1000h; dwFlags
0x14000c97d  call    cs:__imp_LoadLibraryExW
0x14000c984  nop     dword ptr [rax+rax+00h]
0x14000c989  mov     rdi, rax
0x14000c98c  test    rax, rax
0x14000c98f  jz      short loc_14000C9E1
0x14000c991  lea     rdx, aDllregisterser; "DllRegisterServer"
0x14000c998  mov     rcx, rax; hModule
0x14000c99b  call    cs:__imp_GetProcAddress
0x14000c9a2  nop     dword ptr [rax+rax+00h]
0x14000c9a7  test    rax, rax
0x14000c9aa  jz      short loc_14000C9B5
0x14000c9ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c9b1  mov     ebx, eax
0x14000c9b3  jmp     short loc_14000C9D0
0x14000c9b5  call    cs:__imp_GetLastError
0x14000c9bc  nop     dword ptr [rax+rax+00h]
0x14000c9c1  mov     ebx, eax
0x14000c9c3  test    eax, eax
0x14000c9c5  jle     short loc_14000C9D0
0x14000c9c7  movzx   ebx, ax
0x14000c9ca  or      ebx, 80070000h
0x14000c9d0  mov     rcx, rdi; hLibModule
0x14000c9d3  call    cs:__imp_FreeLibrary
0x14000c9da  nop     dword ptr [rax+rax+00h]
0x14000c9df  jmp     short loc_14000C9FC
0x14000c9e1  call    cs:__imp_GetLastError
0x14000c9e8  nop     dword ptr [rax+rax+00h]
0x14000c9ed  mov     ebx, eax
0x14000c9ef  test    eax, eax
0x14000c9f1  jle     short loc_14000C9FC
0x14000c9f3  movzx   ebx, ax
0x14000c9f6  or      ebx, 80070000h
0x14000c9fc  mov     eax, ebx
0x14000c9fe  mov     rbx, [rsp+28h+arg_0]
0x14000ca03  add     rsp, 20h
0x14000ca07  pop     rdi
0x14000ca08  retn
```
