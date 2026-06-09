# Is64BitMachine(void)

- ea: `0x180002e64`
- end: `0x180002ec0`
- name: `?Is64BitMachine@@YAHXZ`
- size: `92`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800018e0`
- `0x180001a20`

## callees

- `0x180002e64`
- `0x180003650`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180002e91`
- `KERNEL32!GetLastError` at `0x180002e91`
- `KERNEL32!GetSystemWow64DirectoryW` at `0x180002e87`
- `KERNEL32!GetSystemWow64DirectoryW` at `0x180002e87`

## pseudocode

```c
_BOOL8 Is64BitMachine(void)
{
  WCHAR Buffer[264]; // [rsp+20h] [rbp-228h] BYREF

  return GetSystemWow64DirectoryW(Buffer, 0x104u) || GetLastError() != 120;
}

```

## disassembly

```asm
0x180002e64  sub     rsp, 248h
0x180002e6b  mov     rax, cs:__security_cookie
0x180002e72  xor     rax, rsp
0x180002e75  mov     [rsp+248h+var_18], rax
0x180002e7d  mov     edx, 104h; uSize
0x180002e82  lea     rcx, [rsp+248h+Buffer]; lpBuffer
0x180002e87  call    cs:__imp_GetSystemWow64DirectoryW
0x180002e8d  test    eax, eax
0x180002e8f  jnz     short loc_180002EA3
0x180002e91  call    cs:__imp_GetLastError
0x180002e97  xor     ecx, ecx
0x180002e99  cmp     eax, 78h ; 'x'
0x180002e9c  setnz   cl
0x180002e9f  mov     eax, ecx
0x180002ea1  jmp     short loc_180002EA8
0x180002ea3  mov     eax, 1
0x180002ea8  mov     rcx, [rsp+248h+var_18]
0x180002eb0  xor     rcx, rsp; StackCookie
0x180002eb3  call    __security_check_cookie
0x180002eb8  add     rsp, 248h
0x180002ebf  retn
```
