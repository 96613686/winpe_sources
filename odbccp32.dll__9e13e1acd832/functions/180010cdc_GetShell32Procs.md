# GetShell32Procs

- ea: `0x180010cdc`
- end: `0x180010db9`
- name: `GetShell32Procs`
- size: `221`
- prototype: `FARPROC __fastcall(LPCSTR lpProcName, const WCHAR *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001085c`
- `0x1800109f4`

## callees

- `0x180010cdc`
- `0x180014ae0`

## import_xrefs

- `USER32!MessageBoxW` at `0x180010d8c`
- `USER32!MessageBoxW` at `0x180010d8c`
- `USER32!LoadStringW` at `0x180010d54`
- `USER32!LoadStringW` at `0x180010d76`
- `USER32!LoadStringW` at `0x180010d54`
- `USER32!LoadStringW` at `0x180010d76`
- `KERNEL32!LoadLibraryExW` at `0x180010d15`
- `KERNEL32!LoadLibraryExW` at `0x180010d15`
- `KERNEL32!FreeLibrary` at `0x180010d37`
- `KERNEL32!FreeLibrary` at `0x180010d37`
- `KERNEL32!GetProcAddress` at `0x180010d29`
- `KERNEL32!GetProcAddress` at `0x180010d29`

## string_xrefs

- `0x180010d08`: `shell32.dll`

## pseudocode

```c
FARPROC __fastcall GetShell32Procs(LPCSTR lpProcName, const WCHAR *a2)
{
  HMODULE Library; // rax
  HMODULE v5; // rbx
  FARPROC result; // rax
  const WCHAR *v7; // r8
  WCHAR Buffer[512]; // [rsp+20h] [rbp-418h] BYREF

  Library = LoadLibraryExW(L"shell32.dll", 0, 0x800u);
  v5 = Library;
  if ( Library )
  {
    result = GetProcAddress(Library, lpProcName);
    if ( result )
      return result;
    FreeLibrary(v5);
    LoadStringW(g_hResDLL, 0x6F0u, Buffer, 512);
    v7 = a2;
  }
  else
  {
    LoadStringW(g_hResDLL, 0x6EFu, Buffer, 512);
    v7 = 0;
  }
  MessageBoxW(0, Buffer, v7, 0x40u);
  return 0;
}

```

## disassembly

```asm
0x180010cdc  mov     [rsp+arg_10], rbx
0x180010ce1  mov     [rsp+arg_18], rsi
0x180010ce6  push    rdi
0x180010ce7  sub     rsp, 430h
0x180010cee  mov     rax, cs:__security_cookie
0x180010cf5  xor     rax, rsp
0x180010cf8  mov     [rsp+438h+var_18], rax
0x180010d00  mov     rsi, rdx
0x180010d03  mov     rdi, rcx
0x180010d06  xor     edx, edx; hFile
0x180010d08  lea     rcx, LibFileName; "shell32.dll"
0x180010d0f  mov     r8d, 800h; dwFlags
0x180010d15  call    cs:__imp_LoadLibraryExW
0x180010d1b  mov     rbx, rax
0x180010d1e  test    rax, rax
0x180010d21  jz      short loc_180010D5F
0x180010d23  mov     rdx, rdi; lpProcName
0x180010d26  mov     rcx, rax; hModule
0x180010d29  call    cs:__imp_GetProcAddress
0x180010d2f  test    rax, rax
0x180010d32  jnz     short loc_180010D94
0x180010d34  mov     rcx, rbx; hLibModule
0x180010d37  call    cs:__imp_FreeLibrary
0x180010d3d  mov     rcx, cs:g_hResDLL; hInstance
0x180010d44  lea     r8, [rsp+438h+Buffer]; lpBuffer
0x180010d49  mov     r9d, 200h; cchBufferMax
0x180010d4f  mov     edx, 6F0h; uID
0x180010d54  call    cs:__imp_LoadStringW
0x180010d5a  mov     r8, rsi
0x180010d5d  jmp     short loc_180010D7F
0x180010d5f  mov     rcx, cs:g_hResDLL; hInstance
0x180010d66  lea     r8, [rsp+438h+Buffer]; lpBuffer
0x180010d6b  mov     r9d, 200h; cchBufferMax
0x180010d71  mov     edx, 6EFh; uID
0x180010d76  call    cs:__imp_LoadStringW
0x180010d7c  xor     r8d, r8d; lpCaption
0x180010d7f  mov     r9d, 40h ; '@'; uType
0x180010d85  lea     rdx, [rsp+438h+Buffer]; lpText
0x180010d8a  xor     ecx, ecx; hWnd
0x180010d8c  call    cs:__imp_MessageBoxW
0x180010d92  xor     eax, eax
0x180010d94  mov     rcx, [rsp+438h+var_18]
0x180010d9c  xor     rcx, rsp; StackCookie
0x180010d9f  call    __security_check_cookie
0x180010da4  lea     r11, [rsp+438h+var_8]
0x180010dac  mov     rbx, [r11+20h]
0x180010db0  mov     rsi, [r11+28h]
0x180010db4  mov     rsp, r11
0x180010db7  pop     rdi
0x180010db8  retn
```
