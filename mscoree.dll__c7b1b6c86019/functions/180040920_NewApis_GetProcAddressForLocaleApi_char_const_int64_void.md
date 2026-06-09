# NewApis::GetProcAddressForLocaleApi(char const *,__int64 (*)(void))

- ea: `0x180040920`
- end: `0x180040a19`
- name: `?GetProcAddressForLocaleApi@NewApis@@YAP6A_JXZPEBDP6A_JXZ@Z`
- size: `249`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName, const char *, __int64 (*)(void)))(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180040b30`
- `0x180040c68`

## callees

- `0x180002710`
- `0x180040920`
- `0x180041ac0`
- `0x180045030`

## import_xrefs

- `KERNEL32!GetVersionExW` at `0x18004096f`
- `KERNEL32!GetVersionExW` at `0x18004096f`
- `KERNEL32!GetProcAddress` at `0x1800409c7`
- `KERNEL32!GetProcAddress` at `0x1800409ea`
- `KERNEL32!GetProcAddress` at `0x1800409c7`
- `KERNEL32!GetProcAddress` at `0x1800409ea`
- `KERNEL32!GetModuleHandleW` at `0x1800409d9`
- `KERNEL32!GetModuleHandleW` at `0x1800409d9`

## string_xrefs

- `0x1800409ac`: `culture.dll`

## pseudocode

```c
FARPROC __fastcall NewApis::GetProcAddressForLocaleApi(LPCSTR lpProcName, const char *a2, __int64 (*a3)(void))
{
  int v3; // eax
  HMODULE v6; // rcx
  FARPROC result; // rax
  HMODULE ModuleHandleW; // rax
  struct _OSVERSIONINFOW VersionInformation; // [rsp+20h] [rbp-138h] BYREF

  v3 = `NewApis::IsWindows7Platform'::`2'::isRunningOnWindows7;
  if ( `NewApis::IsWindows7Platform'::`2'::isRunningOnWindows7 == -1 )
  {
    memset_thunk_772440563353939046(&VersionInformation.dwMajorVersion, 0, 0x110u);
    VersionInformation.dwOSVersionInfoSize = 276;
    GetVersionExW(&VersionInformation);
    v3 = VersionInformation.dwPlatformId == 2 && VersionInformation.dwMajorVersion >= 7;
    `NewApis::IsWindows7Platform'::`2'::isRunningOnWindows7 = v3;
  }
  if ( v3 == 1
    || (v6 = hModule) == 0
    && (LoadLibraryShim_0((wchar_t *)L"culture.dll", 0, (__int64)a3, &hModule), (v6 = hModule) == 0)
    || (result = GetProcAddress(v6, lpProcName)) == 0 )
  {
    ModuleHandleW = GetModuleHandleW(L"kernel32");
    if ( !ModuleHandleW )
      return (FARPROC)a2;
    result = GetProcAddress(ModuleHandleW, lpProcName);
    if ( !result )
      return (FARPROC)a2;
  }
  return result;
}

```

## disassembly

```asm
0x180040920  mov     [rsp+arg_8], rbx
0x180040925  push    rdi
0x180040926  sub     rsp, 150h
0x18004092d  mov     rax, cs:__security_cookie
0x180040934  xor     rax, rsp
0x180040937  mov     [rsp+158h+var_18], rax
0x18004093f  mov     eax, cs:?isRunningOnWindows7@?1??IsWindows7Platform@NewApis@@YAHXZ@4HA; int `NewApis::IsWindows7Platform(void)'::`2'::isRunningOnWindows7
0x180040945  mov     rbx, rdx
0x180040948  mov     rdi, rcx
0x18004094b  cmp     eax, 0FFFFFFFFh
0x18004094e  jnz     short loc_180040992
0x180040950  xor     edx, edx; Val
0x180040952  lea     rcx, [rsp+158h+VersionInformation.dwMajorVersion]; void *
0x180040957  mov     r8d, 110h; Size
0x18004095d  call    memset$thunk$772440563353939046
0x180040962  lea     rcx, [rsp+158h+VersionInformation]; lpVersionInformation
0x180040967  mov     [rsp+158h+VersionInformation.dwOSVersionInfoSize], 114h
0x18004096f  call    cs:__imp_GetVersionExW
0x180040975  cmp     [rsp+158h+VersionInformation.dwPlatformId], 2
0x18004097a  jnz     short loc_18004098A
0x18004097c  cmp     [rsp+158h+VersionInformation.dwMajorVersion], 7
0x180040981  jb      short loc_18004098A
0x180040983  mov     eax, 1
0x180040988  jmp     short loc_18004098C
0x18004098a  xor     eax, eax
0x18004098c  mov     cs:?isRunningOnWindows7@?1??IsWindows7Platform@NewApis@@YAHXZ@4HA, eax; int `NewApis::IsWindows7Platform(void)'::`2'::isRunningOnWindows7
0x180040992  cmp     eax, 1
0x180040995  jz      short loc_1800409D2
0x180040997  mov     rcx, cs:hModule
0x18004099e  test    rcx, rcx
0x1800409a1  jnz     short loc_1800409C4
0x1800409a3  lea     r9, hModule
0x1800409aa  xor     edx, edx; wchar_t *
0x1800409ac  lea     rcx, aCultureDll; "culture.dll"
0x1800409b3  call    LoadLibraryShim_0
0x1800409b8  mov     rcx, cs:hModule; hModule
0x1800409bf  test    rcx, rcx
0x1800409c2  jz      short loc_1800409D2
0x1800409c4  mov     rdx, rdi; lpProcName
0x1800409c7  call    cs:__imp_GetProcAddress
0x1800409cd  test    rax, rax
0x1800409d0  jnz     short loc_1800409F8
0x1800409d2  lea     rcx, aKernel32; "kernel32"
0x1800409d9  call    cs:__imp_GetModuleHandleW
0x1800409df  test    rax, rax
0x1800409e2  jz      short loc_1800409F5
0x1800409e4  mov     rdx, rdi; lpProcName
0x1800409e7  mov     rcx, rax; hModule
0x1800409ea  call    cs:__imp_GetProcAddress
0x1800409f0  test    rax, rax
0x1800409f3  jnz     short loc_1800409F8
0x1800409f5  mov     rax, rbx
0x1800409f8  mov     rcx, [rsp+158h+var_18]
0x180040a00  xor     rcx, rsp; StackCookie
0x180040a03  call    __security_check_cookie
0x180040a08  mov     rbx, [rsp+158h+arg_8]
0x180040a10  add     rsp, 150h
0x180040a17  pop     rdi
0x180040a18  retn
```
