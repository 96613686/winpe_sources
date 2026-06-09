# CIsolationFile::Open(ushort const *)

- ea: `0x14002851c`
- end: `0x14002863a`
- name: `?Open@CIsolationFile@@QEAAJPEBG@Z`
- size: `286`
- prototype: `int(CIsolationFile *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1400283cc`

## callees

- `0x140001020`
- `0x14000fea0`
- `0x14002851c`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x14002857f`
- `KERNEL32!CreateFileW` at `0x14002857f`
- `KERNEL32!CloseHandle` at `0x1400285b9`
- `KERNEL32!CloseHandle` at `0x1400285b9`
- `KERNEL32!GetFileSizeEx` at `0x1400285b0`
- `KERNEL32!GetFileSizeEx` at `0x1400285b0`
- `KERNEL32!GetPrivateProfileSectionW` at `0x1400285f8`
- `KERNEL32!GetPrivateProfileSectionW` at `0x1400285f8`
- `KERNEL32!GetLastError` at `0x140028591`
- `KERNEL32!GetLastError` at `0x140028591`

## pseudocode

```c
__int64 __fastcall CIsolationFile::Open(CIsolationFile *this, const unsigned __int16 *a2)
{
  WCHAR **v2; // rdi
  __int64 result; // rax
  HANDLE FileW; // rax
  void *v6; // rbx
  signed int LastError; // ecx
  DWORD LowPart; // ebx
  WCHAR *v9; // rax
  DWORD PrivateProfileSectionW; // eax
  LARGE_INTEGER FileSize; // [rsp+40h] [rbp-18h] BYREF

  v2 = (WCHAR **)qword_14009DBC0;
  if ( *(_QWORD *)qword_14009DBC0 )
    return 2147500037LL;
  FileW = CreateFileW(a2, 0x80000000, 1u, 0, 3u, 0x8000080u, 0);
  v6 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    result = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      return (unsigned int)LastError;
  }
  else
  {
    GetFileSizeEx(FileW, &FileSize);
    CloseHandle(v6);
    if ( FileSize.HighPart <= 0 )
    {
      LowPart = FileSize.LowPart;
      v9 = (WCHAR *)operator new[](saturated_mul(FileSize.LowPart, 2u));
      *v2 = v9;
      PrivateProfileSectionW = GetPrivateProfileSectionW(L"Info", v9, LowPart, a2);
      if ( PrivateProfileSectionW )
        return PrivateProfileSectionW >= LowPart - 1 ? 0x8007000D : 0;
      else
        return 2147942413LL;
    }
    else
    {
      return 2147942487LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14002851c  mov     [rsp+arg_0], rbx
0x140028521  mov     [rsp+arg_10], rsi
0x140028526  mov     [rsp+arg_18], rdi
0x14002852b  push    r14
0x14002852d  sub     rsp, 50h
0x140028531  mov     rax, cs:__security_cookie
0x140028538  xor     rax, rsp
0x14002853b  mov     [rsp+58h+var_10], rax
0x140028540  mov     rdi, cs:qword_14009DBC0
0x140028547  mov     rsi, rdx
0x14002854a  cmp     qword ptr [rdi], 0
0x14002854e  jz      short loc_14002855A
0x140028550  mov     eax, 80004005h
0x140028555  jmp     loc_140028617
0x14002855a  and     [rsp+58h+var_28], 0
0x140028560  xor     r9d, r9d; lpSecurityAttributes
0x140028563  mov     [rsp+58h+dwFlagsAndAttributes], 8000080h; dwFlagsAndAttributes
0x14002856b  mov     edx, 80000000h; dwDesiredAccess
0x140028570  mov     rcx, rsi; lpFileName
0x140028573  mov     [rsp+58h+dwCreationDisposition], 3; dwCreationDisposition
0x14002857b  lea     r8d, [r9+1]; dwShareMode
0x14002857f  call    cs:__imp_CreateFileW
0x140028585  or      r14, 0FFFFFFFFFFFFFFFFh
0x140028589  mov     rbx, rax
0x14002858c  cmp     rax, r14
0x14002858f  jnz     short loc_1400285A8
0x140028591  call    cs:__imp_GetLastError
0x140028597  mov     ecx, eax
0x140028599  movzx   eax, ax
0x14002859c  or      eax, 80070000h
0x1400285a1  test    ecx, ecx
0x1400285a3  cmovle  eax, ecx
0x1400285a6  jmp     short loc_140028617
0x1400285a8  lea     rdx, [rsp+58h+FileSize]; lpFileSize
0x1400285ad  mov     rcx, rbx; hFile
0x1400285b0  call    cs:__imp_GetFileSizeEx
0x1400285b6  mov     rcx, rbx; hObject
0x1400285b9  call    cs:__imp_CloseHandle
0x1400285bf  cmp     dword ptr [rsp+58h+FileSize+4], 0
0x1400285c4  jle     short loc_1400285CD
0x1400285c6  mov     eax, 80070057h
0x1400285cb  jmp     short loc_140028617
0x1400285cd  mov     ebx, dword ptr [rsp+58h+FileSize]
0x1400285d1  mov     eax, 2
0x1400285d6  mul     rbx
0x1400285d9  cmovb   rax, r14
0x1400285dd  mov     rcx, rax; unsigned __int64
0x1400285e0  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1400285e5  mov     r9, rsi; lpFileName
0x1400285e8  mov     [rdi], rax
0x1400285eb  mov     r8d, ebx; nSize
0x1400285ee  lea     rcx, AppName; "Info"
0x1400285f5  mov     rdx, rax; lpReturnedString
0x1400285f8  call    cs:__imp_GetPrivateProfileSectionW
0x1400285fe  test    eax, eax
0x140028600  jz      short loc_140028612
0x140028602  lea     ecx, [rbx-1]
0x140028605  cmp     eax, ecx
0x140028607  sbb     eax, eax
0x140028609  not     eax
0x14002860b  and     eax, 8007000Dh
0x140028610  jmp     short loc_140028617
0x140028612  mov     eax, 8007000Dh
0x140028617  mov     rcx, [rsp+58h+var_10]
0x14002861c  xor     rcx, rsp; StackCookie
0x14002861f  call    __security_check_cookie
0x140028624  mov     rbx, [rsp+58h+arg_0]
0x140028629  mov     rsi, [rsp+58h+arg_10]
0x14002862e  mov     rdi, [rsp+58h+arg_18]
0x140028633  add     rsp, 50h
0x140028637  pop     r14
0x140028639  retn
```
