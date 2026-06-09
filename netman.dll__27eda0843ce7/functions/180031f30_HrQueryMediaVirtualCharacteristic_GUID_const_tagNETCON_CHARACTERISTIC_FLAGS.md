# HrQueryMediaVirtualCharacteristic(_GUID const &,tagNETCON_CHARACTERISTIC_FLAGS &)

- ea: `0x180031f30`
- end: `0x180032023`
- name: `?HrQueryMediaVirtualCharacteristic@@YAJAEBU_GUID@@AEAW4tagNETCON_CHARACTERISTIC_FLAGS@@@Z`
- size: `243`
- prototype: `__int64 __fastcall(const struct _GUID *, enum tagNETCON_CHARACTERISTIC_FLAGS *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180024978`

## callees

- `0x180001710`
- `0x18003060c`
- `0x180031f30`
- `0x180036010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180031fd3`
- `KERNEL32!FreeLibrary` at `0x180031ff9`
- `KERNEL32!FreeLibrary` at `0x180031fd3`
- `KERNEL32!FreeLibrary` at `0x180031ff9`
- `KERNEL32!LoadLibraryExW` at `0x180031fa3`
- `KERNEL32!LoadLibraryExW` at `0x180031fa3`
- `KERNEL32!GetProcAddress` at `0x180031fbb`
- `KERNEL32!GetProcAddress` at `0x180031fbb`

## string_xrefs

- `0x180031f51`: `wlanapi.dll`

## pseudocode

```c
__int64 __fastcall HrQueryMediaVirtualCharacteristic(const struct _GUID *a1, enum tagNETCON_CHARACTERISTIC_FLAGS *a2)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rsi
  HMODULE v6; // rdi
  int Win32Error; // ebx
  WCHAR LibFileName[12]; // [rsp+20h] [rbp-68h] BYREF
  CHAR ProcName[40]; // [rsp+38h] [rbp-50h] BYREF

  wcscpy(LibFileName, L"wlanapi.dll");
  ProcName[32] = aQuerynetconvir[32];
  *a2 = NCCF_NONE;
  qmemcpy(ProcName, "QueryNetconVirtualCharacteristic", 32);
  Library = LoadLibraryExW(LibFileName, 0, 0);
  ProcAddress = 0;
  v6 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, ProcName);
    if ( ProcAddress )
    {
LABEL_6:
      Win32Error = ((__int64 (__fastcall *)(const struct _GUID *, enum tagNETCON_CHARACTERISTIC_FLAGS *))ProcAddress)(
                     a1,
                     a2);
      FreeLibrary(v6);
      return (unsigned int)Win32Error;
    }
    Win32Error = HrFromLastWin32Error();
    FreeLibrary(v6);
  }
  else
  {
    Win32Error = HrFromLastWin32Error();
  }
  if ( Win32Error >= 0 )
    goto LABEL_6;
  return (unsigned int)Win32Error;
}

```

## disassembly

```asm
0x180031f30  mov     [rsp+arg_10], rbx
0x180031f35  mov     [rsp+arg_18], rbp
0x180031f3a  push    rsi
0x180031f3b  push    rdi
0x180031f3c  push    r14
0x180031f3e  sub     rsp, 70h
0x180031f42  mov     rax, cs:__security_cookie
0x180031f49  xor     rax, rsp
0x180031f4c  mov     [rsp+88h+var_28], rax
0x180031f51  movups  xmm0, xmmword ptr cs:aWlanapiDll; "wlanapi.dll"
0x180031f58  mov     r14, rdx
0x180031f5b  mov     al, byte ptr cs:aQuerynetconvir+20h; ""
0x180031f61  movsd   xmm1, qword ptr cs:aWlanapiDll+10h; "dll"
0x180031f69  mov     rbp, rcx
0x180031f6c  movups  xmmword ptr [rsp+88h+LibFileName], xmm0
0x180031f71  xor     r8d, r8d; dwFlags
0x180031f74  lea     rcx, [rsp+88h+LibFileName]; lpLibFileName
0x180031f79  movups  xmm0, xmmword ptr cs:aQuerynetconvir; "QueryNetconVirtualCharacteristic"
0x180031f80  mov     [rsp+88h+var_30], al
0x180031f84  movsd   [rsp+88h+var_58], xmm1
0x180031f8a  movups  xmm1, xmmword ptr cs:aQuerynetconvir+10h; "alCharacteristic"
0x180031f91  mov     dword ptr [rdx], 0
0x180031f97  xor     edx, edx; hFile
0x180031f99  movups  xmmword ptr [rsp+88h+ProcName], xmm0
0x180031f9e  movups  [rsp+88h+var_40], xmm1
0x180031fa3  call    cs:__imp_LoadLibraryExW
0x180031fa9  xor     esi, esi
0x180031fab  mov     rdi, rax
0x180031fae  test    rax, rax
0x180031fb1  jz      short loc_180031FDB
0x180031fb3  lea     rdx, [rsp+88h+ProcName]; lpProcName
0x180031fb8  mov     rcx, rax; hModule
0x180031fbb  call    cs:__imp_GetProcAddress
0x180031fc1  mov     rsi, rax
0x180031fc4  test    rax, rax
0x180031fc7  jnz     short loc_180031FE6
0x180031fc9  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180031fce  mov     rcx, rdi; hLibModule
0x180031fd1  mov     ebx, eax
0x180031fd3  call    cs:__imp_FreeLibrary
0x180031fd9  jmp     short loc_180031FE2
0x180031fdb  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180031fe0  mov     ebx, eax
0x180031fe2  test    ebx, ebx
0x180031fe4  js      short loc_180031FFF
0x180031fe6  mov     rdx, r14
0x180031fe9  mov     rcx, rbp
0x180031fec  mov     rax, rsi
0x180031fef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031ff4  mov     rcx, rdi; hLibModule
0x180031ff7  mov     ebx, eax
0x180031ff9  call    cs:__imp_FreeLibrary
0x180031fff  mov     eax, ebx
0x180032001  mov     rcx, [rsp+88h+var_28]
0x180032006  xor     rcx, rsp; StackCookie
0x180032009  call    __security_check_cookie
0x18003200e  lea     r11, [rsp+88h+var_18]
0x180032013  mov     rbx, [r11+30h]
0x180032017  mov     rbp, [r11+38h]
0x18003201b  mov     rsp, r11
0x18003201e  pop     r14
0x180032020  pop     rdi
0x180032021  pop     rsi
0x180032022  retn
```
