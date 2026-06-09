# SuperclassGhosts

- ea: `0x18000a5e8`
- end: `0x18000a691`
- name: `SuperclassGhosts`
- size: `169`
- prototype: `__int64 __fastcall(LONG_PTR dwNewLong)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a6a0`

## callees

- `0x18000a5e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a652`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a652`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a669`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a67c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a669`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a67c`
- `USER32!SetClassLongPtrW` at `0x18000a663`
- `USER32!SetClassLongPtrW` at `0x18000a663`
- `ext-ms-win-ntuser-window-l1-1-0!CreateWindowExW` at `0x18000a642`
- `ext-ms-win-ntuser-window-l1-1-0!CreateWindowExW` at `0x18000a642`
- `ext-ms-win-ntuser-window-l1-1-0!DestroyWindow` at `0x18000a674`
- `ext-ms-win-ntuser-window-l1-1-0!DestroyWindow` at `0x18000a674`

## pseudocode

```c
__int64 __fastcall SuperclassGhosts(LONG_PTR dwNewLong)
{
  HWND Window; // rdi
  DWORD LastError; // ebx

  Window = CreateWindowExW(0, L"Ghost", L"Ghost", 0, 0, 0, 0, 0, 0, 0, 0, 0);
  if ( Window )
  {
    SetLastError(0);
    SetClassLongPtrW(Window, -24, dwNewLong);
    LastError = GetLastError();
    DestroyWindow(Window);
  }
  else
  {
    return GetLastError();
  }
  return LastError;
}

```

## disassembly

```asm
0x18000a5e8  mov     rax, rsp
0x18000a5eb  mov     [rax+8], rbx
0x18000a5ef  push    rdi
0x18000a5f0  sub     rsp, 60h
0x18000a5f4  mov     qword ptr [rax-10h], 0
0x18000a5fc  lea     rdx, ClassName; "Ghost"
0x18000a603  mov     qword ptr [rax-18h], 0
0x18000a60b  mov     rbx, rcx
0x18000a60e  mov     qword ptr [rax-20h], 0
0x18000a616  xor     r9d, r9d; dwStyle
0x18000a619  mov     qword ptr [rax-28h], 0
0x18000a621  mov     r8, rdx; lpWindowName
0x18000a624  mov     dword ptr [rax-30h], 0
0x18000a62b  xor     ecx, ecx; dwExStyle
0x18000a62d  mov     dword ptr [rax-38h], 0
0x18000a634  mov     dword ptr [rax-40h], 0
0x18000a63b  mov     dword ptr [rax-48h], 0
0x18000a642  call    cs:__imp_CreateWindowExW
0x18000a648  mov     rdi, rax
0x18000a64b  test    rax, rax
0x18000a64e  jz      short loc_18000A67C
0x18000a650  xor     ecx, ecx; dwErrCode
0x18000a652  call    cs:__imp_SetLastError
0x18000a658  mov     r8, rbx; dwNewLong
0x18000a65b  mov     edx, 0FFFFFFE8h; nIndex
0x18000a660  mov     rcx, rdi; hWnd
0x18000a663  call    cs:__imp_SetClassLongPtrW
0x18000a669  call    cs:__imp_GetLastError
0x18000a66f  mov     rcx, rdi; hWnd
0x18000a672  mov     ebx, eax
0x18000a674  call    cs:__imp_DestroyWindow
0x18000a67a  jmp     short loc_18000A684
0x18000a67c  call    cs:__imp_GetLastError
0x18000a682  mov     ebx, eax
0x18000a684  mov     eax, ebx
0x18000a686  mov     rbx, [rsp+68h+arg_0]
0x18000a68b  add     rsp, 60h
0x18000a68f  pop     rdi
0x18000a690  retn
```
