# CCmstpLua::DeleteDesktopIcon(ushort const *)

- ea: `0x180001c60`
- end: `0x180001d67`
- name: `?DeleteDesktopIcon@CCmstpLua@@UEAAJPEBG@Z`
- size: `263`
- prototype: `signed int __fastcall(CCmstpLua *this, WCHAR *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180001c60`
- `0x1800026b6`
- `0x1800026e0`

## import_xrefs

- `KERNEL32!SetFileAttributesW` at `0x180001ceb`
- `KERNEL32!SetFileAttributesW` at `0x180001ceb`
- `KERNEL32!GetLastError` at `0x180001d31`
- `KERNEL32!GetLastError` at `0x180001d31`
- `SHELL32!SHFileOperationW` at `0x180001d2b`
- `SHELL32!SHFileOperationW` at `0x180001d2b`

## pseudocode

```c
signed int __fastcall CCmstpLua::DeleteDesktopIcon(CCmstpLua *this, WCHAR *a2)
{
  __int64 v3; // rcx
  WCHAR *v4; // rax
  __int64 v5; // r8
  WCHAR *v6; // rcx
  signed int result; // eax
  _SHFILEOPSTRUCTW FileOp; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR FileName[264]; // [rsp+60h] [rbp-A0h] BYREF

  memset_0(FileName, 0, 0x20Cu);
  v3 = 2147483646;
  v4 = FileName;
  v5 = 262;
  do
  {
    if ( !v3 )
      break;
    if ( !*a2 )
      break;
    *v4++ = *a2++;
    --v3;
    --v5;
  }
  while ( v5 );
  v6 = v4 - 1;
  if ( v5 )
    v6 = v4;
  *v6 = 0;
  SetFileAttributesW(FileName, 0x80u);
  memset(&FileOp.pTo, 0, 32);
  FileOp.pFrom = FileName;
  *(_OWORD *)&FileOp.hwnd = 0;
  FileOp.wFunc = 3;
  FileOp.fFlags = 20;
  SHFileOperationW(&FileOp);
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180001c60  mov     [rsp-8+arg_0], rbx
0x180001c65  mov     [rsp-8+arg_8], rdi
0x180001c6a  push    rbp
0x180001c6b  lea     rbp, [rsp-180h]
0x180001c73  sub     rsp, 280h
0x180001c7a  mov     rax, cs:__security_cookie
0x180001c81  xor     rax, rsp
0x180001c84  mov     [rbp+180h+var_10], rax
0x180001c8b  mov     rbx, rdx
0x180001c8e  lea     rcx, [rsp+280h+FileName]; void *
0x180001c93  xor     edx, edx; Val
0x180001c95  mov     r8d, 20Ch; Size
0x180001c9b  call    memset_0
0x180001ca0  mov     ecx, 7FFFFFFEh
0x180001ca5  lea     rax, [rsp+280h+FileName]
0x180001caa  mov     r8d, 106h
0x180001cb0  xor     edi, edi
0x180001cb2  test    rcx, rcx
0x180001cb5  jz      short loc_180001CD3
0x180001cb7  movzx   edx, word ptr [rbx]
0x180001cba  test    dx, dx
0x180001cbd  jz      short loc_180001CD3
0x180001cbf  mov     [rax], dx
0x180001cc2  add     rbx, 2
0x180001cc6  add     rax, 2
0x180001cca  dec     rcx
0x180001ccd  sub     r8, 1
0x180001cd1  jnz     short loc_180001CB2
0x180001cd3  test    r8, r8
0x180001cd6  lea     rcx, [rax-2]
0x180001cda  mov     edx, 80h; dwFileAttributes
0x180001cdf  cmovnz  rcx, rax
0x180001ce3  mov     [rcx], di
0x180001ce6  lea     rcx, [rsp+280h+FileName]; lpFileName
0x180001ceb  call    cs:__imp_SetFileAttributesW
0x180001cf1  xor     eax, eax
0x180001cf3  lea     rcx, [rsp+280h+FileOp]; lpFileOp
0x180001cf8  xorps   xmm0, xmm0
0x180001cfb  mov     [rsp+280h+FileOp.lpszProgressTitle], rax
0x180001d00  lea     rax, [rsp+280h+FileName]
0x180001d05  movups  xmmword ptr [rsp+280h+FileOp.pFrom], xmm0
0x180001d0a  mov     [rsp+280h+FileOp.pFrom], rax
0x180001d0f  mov     eax, 14h
0x180001d14  movups  xmmword ptr [rsp+280h+FileOp.hwnd], xmm0
0x180001d19  mov     [rsp+280h+FileOp.wFunc], 3
0x180001d21  movups  xmmword ptr [rsp+280h+FileOp.fFlags], xmm0
0x180001d26  mov     [rsp+280h+FileOp.fFlags], ax
0x180001d2b  call    cs:__imp_SHFileOperationW
0x180001d31  call    cs:__imp_GetLastError
0x180001d37  test    eax, eax
0x180001d39  jle     short loc_180001D43
0x180001d3b  movzx   eax, ax
0x180001d3e  or      eax, 80070000h
0x180001d43  mov     rcx, [rbp+180h+var_10]
0x180001d4a  xor     rcx, rsp; StackCookie
0x180001d4d  call    __security_check_cookie
0x180001d52  lea     r11, [rsp+280h+var_s0]
0x180001d5a  mov     rbx, [r11+10h]
0x180001d5e  mov     rdi, [r11+18h]
0x180001d62  mov     rsp, r11
0x180001d65  pop     rbp
0x180001d66  retn
```
