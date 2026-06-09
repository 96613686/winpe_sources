# PnpCleanVerifyDriverStoreIntegrity

- ea: `0x1800073e4`
- end: `0x180007490`
- name: `PnpCleanVerifyDriverStoreIntegrity`
- size: `172`
- prototype: `__int64 __fastcall(void (__fastcall *)(__int64, __int64, __int64, const char *, DWORD), __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006dc4`

## callees

- `0x1800073e4`
- `0x18000a010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000740b`
- `KERNEL32!GetLastError` at `0x180007449`
- `KERNEL32!GetLastError` at `0x18000740b`
- `KERNEL32!GetLastError` at `0x180007449`
- `KERNEL32!GetProcAddress` at `0x18000743e`
- `KERNEL32!GetProcAddress` at `0x18000743e`
- `KERNEL32!GetModuleHandleW` at `0x180007400`
- `KERNEL32!GetModuleHandleW` at `0x180007400`

## string_xrefs

- `0x1800073f9`: `drvstore.dll`

## pseudocode

```c
__int64 __fastcall PnpCleanVerifyDriverStoreIntegrity(
        void (__fastcall *a1)(__int64, __int64, __int64, const char *, DWORD),
        __int64 a2)
{
  HMODULE ModuleHandleW; // rax
  DWORD LastError; // eax
  const char *v6; // r9
  DWORD v7; // ebx
  FARPROC ProcAddress; // rax

  ModuleHandleW = GetModuleHandleW(L"drvstore.dll");
  if ( ModuleHandleW )
  {
    ProcAddress = GetProcAddress(ModuleHandleW, "DriverStoreVerifyIntegrityW");
    if ( ProcAddress )
      return ((unsigned int (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD, _QWORD, _QWORD))ProcAddress)(
               0,
               0,
               258,
               0,
               0,
               0);
    LastError = GetLastError();
    v6 = "Unable to load integrity routine for driver store integrity check, Err = 0x%lx";
  }
  else
  {
    LastError = GetLastError();
    v6 = "Unable to load module for driver store integrity check, Err = 0x%lx";
  }
  v7 = LastError;
  a1(a2, 2, 1, v6, LastError);
  return v7;
}

```

## disassembly

```asm
0x1800073e4  mov     [rsp+arg_0], rbx
0x1800073e9  mov     [rsp+arg_8], rsi
0x1800073ee  push    rdi
0x1800073ef  sub     rsp, 40h
0x1800073f3  mov     rsi, rcx
0x1800073f6  mov     rdi, rdx
0x1800073f9  lea     rcx, aDrvstoreDll_0; "drvstore.dll"
0x180007400  call    cs:__imp_GetModuleHandleW
0x180007406  test    rax, rax
0x180007409  jnz     short loc_180007434
0x18000740b  call    cs:__imp_GetLastError
0x180007411  lea     r9, aUnableToLoadMo; "Unable to load module for driver store "...
0x180007418  mov     edx, 2
0x18000741d  mov     dword ptr [rsp+48h+var_28], eax
0x180007421  mov     ebx, eax
0x180007423  mov     rcx, rdi
0x180007426  mov     rax, rsi
0x180007429  lea     r8d, [rdx-1]
0x18000742d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007432  jmp     short loc_18000747E
0x180007434  lea     rdx, aDriverstorever; "DriverStoreVerifyIntegrityW"
0x18000743b  mov     rcx, rax; hModule
0x18000743e  call    cs:__imp_GetProcAddress
0x180007444  test    rax, rax
0x180007447  jnz     short loc_180007458
0x180007449  call    cs:__imp_GetLastError
0x18000744f  lea     r9, aUnableToLoadIn; "Unable to load integrity routine for dr"...
0x180007456  jmp     short loc_180007418
0x180007458  mov     [rsp+48h+var_20], 0
0x180007461  xor     r9d, r9d
0x180007464  xor     edx, edx
0x180007466  mov     [rsp+48h+var_28], 0
0x18000746f  xor     ecx, ecx
0x180007471  mov     r8d, 102h
0x180007477  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000747c  mov     ebx, eax
0x18000747e  mov     rsi, [rsp+48h+arg_8]
0x180007483  mov     eax, ebx
0x180007485  mov     rbx, [rsp+48h+arg_0]
0x18000748a  add     rsp, 40h
0x18000748e  pop     rdi
0x18000748f  retn
```
