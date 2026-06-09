# GetVersion

- ea: `0x180006e74`
- end: `0x180006f0f`
- name: `GetVersion`
- size: `155`
- prototype: `DWORD __stdcall()`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180006f18`

## callees

- `0x1800015b0`
- `0x180006e74`
- `0x1800070cc`
- `0x18001a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006ea6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006ea6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180006ee8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180006ee8`

## string_xrefs

- `0x180006e9c`: `DllGetVersion`

## pseudocode

```c
DWORD __stdcall GetVersion()
{
  DWORD v0; // ebx
  HMODULE LibraryW; // rax
  HMODULE v2; // rdi
  FARPROC ProcAddress; // rax
  int v5; // [rsp+20h] [rbp-28h] BYREF
  __int128 v6; // [rsp+24h] [rbp-24h]

  v0 = 0;
  LibraryW = IsolationAwareLoadLibraryW();
  v2 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "DllGetVersion");
    if ( ProcAddress )
    {
      v5 = 20;
      v6 = 0;
      if ( ((int (__fastcall *)(int *))ProcAddress)(&v5) >= 0 )
        v0 = WORD2(v6) | ((unsigned __int16)v6 << 16);
    }
    FreeLibrary(v2);
  }
  return v0;
}

```

## disassembly

```asm
0x180006e74  mov     [rsp+arg_0], rbx
0x180006e79  push    rdi
0x180006e7a  sub     rsp, 40h
0x180006e7e  mov     rax, cs:__security_cookie
0x180006e85  xor     rax, rsp
0x180006e88  mov     [rsp+48h+var_10], rax
0x180006e8d  xor     ebx, ebx
0x180006e8f  call    IsolationAwareLoadLibraryW
0x180006e94  mov     rdi, rax
0x180006e97  test    rax, rax
0x180006e9a  jz      short loc_180006EF4
0x180006e9c  lea     rdx, aDllgetversion; "DllGetVersion"
0x180006ea3  mov     rcx, rax; hModule
0x180006ea6  call    cs:__imp_GetProcAddress
0x180006ead  nop     dword ptr [rax+rax+00h]
0x180006eb2  test    rax, rax
0x180006eb5  jz      short loc_180006EE5
0x180006eb7  xorps   xmm0, xmm0
0x180006eba  mov     [rsp+48h+var_28], 14h
0x180006ec2  lea     rcx, [rsp+48h+var_28]
0x180006ec7  movdqu  [rsp+48h+var_24], xmm0
0x180006ecd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ed2  test    eax, eax
0x180006ed4  js      short loc_180006EE5
0x180006ed6  movzx   ebx, word ptr [rsp+48h+var_24]
0x180006edb  movzx   ecx, word ptr [rsp+48h+var_24+4]
0x180006ee0  shl     ebx, 10h
0x180006ee3  or      ebx, ecx
0x180006ee5  mov     rcx, rdi; hLibModule
0x180006ee8  call    cs:__imp_FreeLibrary
0x180006eef  nop     dword ptr [rax+rax+00h]
0x180006ef4  mov     eax, ebx
0x180006ef6  mov     rcx, [rsp+48h+var_10]
0x180006efb  xor     rcx, rsp; StackCookie
0x180006efe  call    __security_check_cookie
0x180006f03  mov     rbx, [rsp+48h+arg_0]
0x180006f08  add     rsp, 40h
0x180006f0c  pop     rdi
0x180006f0d  retn
```
