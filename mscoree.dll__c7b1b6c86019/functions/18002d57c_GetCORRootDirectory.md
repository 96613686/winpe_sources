# GetCORRootDirectory

- ea: `0x18002d57c`
- end: `0x18002d651`
- name: `GetCORRootDirectory`
- size: `213`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180006ff0`

## callees

- `0x18000d614`
- `0x18002d57c`
- `0x180041ac0`
- `0x180041ec0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002d5c7`
- `KERNEL32!GetLastError` at `0x18002d5c7`
- `KERNEL32!GetWindowsDirectoryW` at `0x18002d5bd`
- `KERNEL32!GetWindowsDirectoryW` at `0x18002d5bd`

## pseudocode

```c
signed int __fastcall GetCORRootDirectory(void *a1, unsigned int a2, unsigned int *a3)
{
  signed int result; // eax
  __int64 v7; // rax
  unsigned int v8; // eax
  int v9; // ebx
  wchar_t Buffer[264]; // [rsp+20h] [rbp-238h] BYREF

  if ( !a3 )
    return -2147467261;
  if ( GetWindowsDirectoryW(Buffer, 0x104u) )
  {
    wcscat_s(Buffer, 0x104u, L"\\Microsoft.NET");
    v7 = -1;
    do
      ++v7;
    while ( Buffer[v7] );
    v8 = v7 + 1;
    *a3 = v8;
    if ( v8 > a2 || !a1 )
      return -2147024774;
    v9 = 0;
    memmove(a1, Buffer, 2LL * v8);
    return v9;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18002d57c  mov     [rsp+arg_8], rbx
0x18002d581  push    rbp
0x18002d582  push    rsi
0x18002d583  push    rdi
0x18002d584  sub     rsp, 240h
0x18002d58b  mov     rax, cs:__security_cookie
0x18002d592  xor     rax, rsp
0x18002d595  mov     [rsp+258h+var_28], rax
0x18002d59d  xor     ebp, ebp
0x18002d59f  mov     rbx, r8
0x18002d5a2  mov     esi, edx
0x18002d5a4  mov     rdi, rcx
0x18002d5a7  test    r8, r8
0x18002d5aa  jnz     short loc_18002D5B3
0x18002d5ac  mov     eax, 80004003h
0x18002d5b1  jmp     short loc_18002D62E
0x18002d5b3  mov     edx, 104h; uSize
0x18002d5b8  lea     rcx, [rsp+258h+Buffer]; lpBuffer
0x18002d5bd  call    cs:__imp_GetWindowsDirectoryW
0x18002d5c3  test    eax, eax
0x18002d5c5  jnz     short loc_18002D5DB
0x18002d5c7  call    cs:__imp_GetLastError
0x18002d5cd  test    eax, eax
0x18002d5cf  jle     short loc_18002D62E
0x18002d5d1  movzx   eax, ax
0x18002d5d4  or      eax, 80070000h
0x18002d5d9  jmp     short loc_18002D62E
0x18002d5db  lea     r8, aMicrosoftNet; "\\Microsoft.NET"
0x18002d5e2  mov     edx, 104h; SizeInWords
0x18002d5e7  lea     rcx, [rsp+258h+Buffer]; Destination
0x18002d5ec  call    wcscat_s
0x18002d5f1  lea     rcx, [rsp+258h+Buffer]
0x18002d5f6  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002d5fa  inc     rax
0x18002d5fd  cmp     [rcx+rax*2], bp
0x18002d601  jnz     short loc_18002D5FA
0x18002d603  inc     eax
0x18002d605  mov     [rbx], eax
0x18002d607  cmp     eax, esi
0x18002d609  ja      short loc_18002D627
0x18002d60b  test    rdi, rdi
0x18002d60e  jz      short loc_18002D627
0x18002d610  mov     r8d, eax
0x18002d613  lea     rdx, [rsp+258h+Buffer]; Src
0x18002d618  add     r8, r8; Size
0x18002d61b  mov     rcx, rdi; void *
0x18002d61e  mov     ebx, ebp
0x18002d620  call    memmove
0x18002d625  jmp     short loc_18002D62C
0x18002d627  mov     ebx, 8007007Ah
0x18002d62c  mov     eax, ebx
0x18002d62e  mov     rcx, [rsp+258h+var_28]
0x18002d636  xor     rcx, rsp; StackCookie
0x18002d639  call    __security_check_cookie
0x18002d63e  mov     rbx, [rsp+258h+arg_8]
0x18002d646  add     rsp, 240h
0x18002d64d  pop     rdi
0x18002d64e  pop     rsi
0x18002d64f  pop     rbp
0x18002d650  retn
```
