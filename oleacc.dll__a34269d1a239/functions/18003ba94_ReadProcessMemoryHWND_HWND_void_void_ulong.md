# ReadProcessMemoryHWND(HWND__ *,void *,void *,ulong)

- ea: `0x18003ba94`
- end: `0x18003bb38`
- name: `?ReadProcessMemoryHWND@@YAHPEAUHWND__@@PEAX1K@Z`
- size: `164`
- prototype: `int(HWND, void *, void *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18003c500`

## callees

- `0x18003ba94`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18003bace`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18003bace`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18003bafe`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18003bafe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003bb1c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003bb1c`
- `USER32!GetWindowThreadProcessId` at `0x18003bab9`
- `USER32!GetWindowThreadProcessId` at `0x18003bab9`

## pseudocode

```c
_BOOL8 __fastcall ReadProcessMemoryHWND(HWND a1, void *a2, void *a3)
{
  HANDLE v5; // rdi
  BOOL v6; // ebx
  SIZE_T NumberOfBytesRead[3]; // [rsp+30h] [rbp-18h] BYREF
  DWORD dwProcessId; // [rsp+68h] [rbp+20h] BYREF

  dwProcessId = 0;
  GetWindowThreadProcessId(a1, &dwProcessId);
  if ( !dwProcessId )
    return 0;
  v5 = OpenProcess(0x10u, 0, dwProcessId);
  if ( !v5 )
    return 0;
  NumberOfBytesRead[0] = 0;
  v6 = ReadProcessMemory(v5, a2, a3, 8u, NumberOfBytesRead) && NumberOfBytesRead[0] == 8;
  CloseHandle(v5);
  return v6;
}

```

## disassembly

```asm
0x18003ba94  mov     rax, rsp
0x18003ba97  mov     [rax+8], rbx
0x18003ba9b  mov     [rax+10h], rsi
0x18003ba9f  mov     [rax+20h], r9d
0x18003baa3  push    rdi
0x18003baa4  sub     rsp, 40h
0x18003baa8  mov     rsi, rdx
0x18003baab  mov     dword ptr [rax+20h], 0
0x18003bab2  lea     rdx, [rax+20h]; lpdwProcessId
0x18003bab6  mov     rbx, r8
0x18003bab9  call    cs:__imp_GetWindowThreadProcessId
0x18003babf  mov     r8d, [rsp+48h+dwProcessId]; dwProcessId
0x18003bac4  test    r8d, r8d
0x18003bac7  jz      short loc_18003BB26
0x18003bac9  xor     edx, edx; bInheritHandle
0x18003bacb  lea     ecx, [rdx+10h]; dwDesiredAccess
0x18003bace  call    cs:__imp_OpenProcess
0x18003bad4  mov     rdi, rax
0x18003bad7  test    rax, rax
0x18003bada  jz      short loc_18003BB26
0x18003badc  lea     rax, [rsp+48h+NumberOfBytesRead]
0x18003bae1  mov     [rsp+48h+NumberOfBytesRead], 0
0x18003baea  mov     r9d, 8; nSize
0x18003baf0  mov     [rsp+48h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x18003baf5  mov     r8, rbx; lpBuffer
0x18003baf8  mov     rdx, rsi; lpBaseAddress
0x18003bafb  mov     rcx, rdi; hProcess
0x18003bafe  call    cs:__imp_ReadProcessMemory
0x18003bb04  test    eax, eax
0x18003bb06  jz      short loc_18003BB17
0x18003bb08  cmp     [rsp+48h+NumberOfBytesRead], 8
0x18003bb0e  jnz     short loc_18003BB17
0x18003bb10  mov     ebx, 1
0x18003bb15  jmp     short loc_18003BB19
0x18003bb17  xor     ebx, ebx
0x18003bb19  mov     rcx, rdi; hObject
0x18003bb1c  call    cs:__imp_CloseHandle
0x18003bb22  mov     eax, ebx
0x18003bb24  jmp     short loc_18003BB28
0x18003bb26  xor     eax, eax
0x18003bb28  mov     rbx, [rsp+48h+arg_0]
0x18003bb2d  mov     rsi, [rsp+48h+arg_8]
0x18003bb32  add     rsp, 40h
0x18003bb36  pop     rdi
0x18003bb37  retn
```
