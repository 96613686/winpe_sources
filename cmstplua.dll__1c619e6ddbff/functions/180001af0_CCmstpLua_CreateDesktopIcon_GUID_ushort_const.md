# CCmstpLua::CreateDesktopIcon(_GUID,ushort const *)

- ea: `0x180001af0`
- end: `0x180001ba1`
- name: `?CreateDesktopIcon@CCmstpLua@@UEAAJU_GUID@@PEBG@Z`
- size: `177`
- prototype: `__int64 __fastcall(CCmstpLua *__hidden this, struct _GUID *__struct_ptr, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180001af0`
- `0x180002444`
- `0x180003010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180001b1f`
- `KERNEL32!GetLastError` at `0x180001b50`
- `KERNEL32!GetLastError` at `0x180001b1f`
- `KERNEL32!GetLastError` at `0x180001b50`
- `KERNEL32!GetProcAddress` at `0x180001b45`
- `KERNEL32!GetProcAddress` at `0x180001b45`
- `KERNEL32!FreeLibrary` at `0x180001b7c`
- `KERNEL32!FreeLibrary` at `0x180001b7c`
- `KERNEL32!LoadLibraryExW` at `0x180001b11`
- `KERNEL32!LoadLibraryExW` at `0x180001b11`

## string_xrefs

- `0x180001b02`: `netshell.dll`
- `0x180001b25`: `LoadLibrary failed in CreateDesktopIcon. GLE = %#x`
- `0x180001b3b`: `HrCreateDesktopIcon`
- `0x180001b56`: `GetProcAddress failed in CreateDesktopIcon. GLE = %#x`

## pseudocode

```c
__int64 __fastcall CCmstpLua::CreateDesktopIcon(CCmstpLua *this, struct _GUID *LastError, const unsigned __int16 *a3)
{
  HMODULE Library; // rax
  HMODULE v6; // rdi
  FARPROC ProcAddress; // rax

  Library = LoadLibraryExW(L"netshell.dll", 0, 0);
  v6 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "HrCreateDesktopIcon");
    if ( ProcAddress )
    {
      LODWORD(LastError) = ((__int64 (__fastcall *)(struct _GUID *, const unsigned __int16 *))ProcAddress)(
                             LastError,
                             a3);
    }
    else
    {
      LastError = (struct _GUID *)GetLastError();
      MyDbgPrintfW(0xFFFFFFFFLL, L"GetProcAddress failed in CreateDesktopIcon. GLE = %#x", LastError);
    }
    FreeLibrary(v6);
  }
  else
  {
    LastError = (struct _GUID *)GetLastError();
    MyDbgPrintfW(0xFFFFFFFFLL, L"LoadLibrary failed in CreateDesktopIcon. GLE = %#x", LastError);
  }
  if ( (int)LastError > 0 )
    LODWORD(LastError) = (unsigned __int16)LastError | 0x80070000;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180001af0  mov     [rsp+arg_0], rbx
0x180001af5  mov     [rsp+arg_18], rsi
0x180001afa  push    rdi
0x180001afb  sub     rsp, 20h
0x180001aff  mov     rsi, r8
0x180001b02  lea     rcx, LibFileName; "netshell.dll"
0x180001b09  mov     rbx, rdx
0x180001b0c  xor     r8d, r8d; dwFlags
0x180001b0f  xor     edx, edx; hFile
0x180001b11  call    cs:__imp_LoadLibraryExW
0x180001b17  mov     rdi, rax
0x180001b1a  test    rax, rax
0x180001b1d  jnz     short loc_180001B3B
0x180001b1f  call    cs:__imp_GetLastError
0x180001b25  lea     rdx, aLoadlibraryFai; "LoadLibrary failed in CreateDesktopIcon"...
0x180001b2c  or      ecx, 0FFFFFFFFh
0x180001b2f  mov     r8d, eax
0x180001b32  mov     ebx, eax
0x180001b34  call    MyDbgPrintfW
0x180001b39  jmp     short loc_180001B82
0x180001b3b  lea     rdx, ProcName; "HrCreateDesktopIcon"
0x180001b42  mov     rcx, rdi; hModule
0x180001b45  call    cs:__imp_GetProcAddress
0x180001b4b  test    rax, rax
0x180001b4e  jnz     short loc_180001B6C
0x180001b50  call    cs:__imp_GetLastError
0x180001b56  lea     rdx, aGetprocaddress_0; "GetProcAddress failed in CreateDesktopI"...
0x180001b5d  or      ecx, 0FFFFFFFFh
0x180001b60  mov     r8d, eax
0x180001b63  mov     ebx, eax
0x180001b65  call    MyDbgPrintfW
0x180001b6a  jmp     short loc_180001B79
0x180001b6c  mov     rdx, rsi
0x180001b6f  mov     rcx, rbx
0x180001b72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b77  mov     ebx, eax
0x180001b79  mov     rcx, rdi; hLibModule
0x180001b7c  call    cs:__imp_FreeLibrary
0x180001b82  test    ebx, ebx
0x180001b84  jle     short loc_180001B8F
0x180001b86  movzx   ebx, bx
0x180001b89  or      ebx, 80070000h
0x180001b8f  mov     rsi, [rsp+28h+arg_18]
0x180001b94  mov     eax, ebx
0x180001b96  mov     rbx, [rsp+28h+arg_0]
0x180001b9b  add     rsp, 20h
0x180001b9f  pop     rdi
0x180001ba0  retn
```
