# CGhostWindow::AddWarningText(void)

- ea: `0x1800060e0`
- end: `0x18000619c`
- name: `?AddWarningText@CGhostWindow@@AEAAHXZ`
- size: `188`
- prototype: `__int64 __fastcall(CGhostWindow *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180007190`

## callees

- `0x180001190`
- `0x1800051b0`
- `0x1800060e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180006143`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180006143`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006127`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006127`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowTextW` at `0x180006116`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowTextW` at `0x180006116`
- `ext-ms-win-ntuser-window-l1-1-0!SetWindowTextW` at `0x180006171`
- `ext-ms-win-ntuser-window-l1-1-0!SetWindowTextW` at `0x180006171`

## string_xrefs

- `0x180006120`: `user32.dll`

## pseudocode

```c
__int64 __fastcall CGhostWindow::AddWarningText(CGhostWindow *this)
{
  HMODULE ModuleHandleW; // rax
  WCHAR String[256]; // [rsp+20h] [rbp-418h] BYREF
  WCHAR Buffer[256]; // [rsp+220h] [rbp-218h] BYREF

  if ( !*((_DWORD *)this + 56) )
  {
    if ( GetWindowTextW(*((HWND *)this + 6), String, 256) )
    {
      ModuleHandleW = GetModuleHandleW(L"user32.dll");
      if ( LoadStringW(ModuleHandleW, 0x2EEu, Buffer, 256) )
      {
        if ( (int)StringCchCatW(String, 0x100u, Buffer) >= 0 )
          *((_DWORD *)this + 56) = SetWindowTextW(*((HWND *)this + 6), String);
      }
    }
  }
  return *((unsigned int *)this + 56);
}

```

## disassembly

```asm
0x1800060e0  push    rbx
0x1800060e2  sub     rsp, 430h
0x1800060e9  mov     rax, cs:__security_cookie
0x1800060f0  xor     rax, rsp
0x1800060f3  mov     [rsp+438h+var_18], rax
0x1800060fb  cmp     dword ptr [rcx+0E0h], 0
0x180006102  mov     rbx, rcx
0x180006105  jnz     short loc_18000617D
0x180006107  mov     rcx, [rcx+30h]; hWnd
0x18000610b  lea     rdx, [rsp+438h+String]; lpString
0x180006110  mov     r8d, 100h; nMaxCount
0x180006116  call    cs:__imp_GetWindowTextW
0x18000611c  test    eax, eax
0x18000611e  jz      short loc_18000617D
0x180006120  lea     rcx, LibFileName; "user32.dll"
0x180006127  call    cs:__imp_GetModuleHandleW
0x18000612d  mov     r9d, 100h; cchBufferMax
0x180006133  lea     r8, [rsp+438h+Buffer]; lpBuffer
0x18000613b  mov     rcx, rax; hInstance
0x18000613e  mov     edx, 2EEh; uID
0x180006143  call    cs:__imp_LoadStringW
0x180006149  test    eax, eax
0x18000614b  jz      short loc_18000617D
0x18000614d  lea     r8, [rsp+438h+Buffer]; unsigned __int16 *
0x180006155  mov     edx, 100h; unsigned __int64
0x18000615a  lea     rcx, [rsp+438h+String]; unsigned __int16 *
0x18000615f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006164  test    eax, eax
0x180006166  js      short loc_18000617D
0x180006168  mov     rcx, [rbx+30h]; hWnd
0x18000616c  lea     rdx, [rsp+438h+String]; lpString
0x180006171  call    cs:__imp_SetWindowTextW
0x180006177  mov     [rbx+0E0h], eax
0x18000617d  mov     eax, [rbx+0E0h]
0x180006183  mov     rcx, [rsp+438h+var_18]
0x18000618b  xor     rcx, rsp; StackCookie
0x18000618e  call    __security_check_cookie
0x180006193  add     rsp, 430h
0x18000619a  pop     rbx
0x18000619b  retn
```
