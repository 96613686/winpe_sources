# DeleteFolderRecursively(ushort const *)

- ea: `0x1800029d4`
- end: `0x180002aea`
- name: `?DeleteFolderRecursively@@YAKPEBG@Z`
- size: `278`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180002af0`

## callees

- `0x1800029d4`
- `0x180003f78`
- `0x180004e1c`
- `0x180005486`
- `0x1800054b0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180002a30`
- `KERNEL32!CreateFileW` at `0x180002a30`
- `KERNEL32!CloseHandle` at `0x180002a43`
- `KERNEL32!CloseHandle` at `0x180002a43`
- `SHELL32!SHFileOperationW` at `0x180002aaf`
- `SHELL32!SHFileOperationW` at `0x180002aaf`

## pseudocode

```c
__int64 __fastcall DeleteFolderRecursively(const unsigned __int16 *a1)
{
  unsigned int v2; // ebx
  HANDLE FileW; // rax
  unsigned __int16 **v4; // r9
  int v5; // eax
  unsigned int v6; // eax
  __int64 v7; // r9
  unsigned __int64 *dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  _SHFILEOPSTRUCTW FileOp; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+80h] [rbp-80h] BYREF

  v2 = 0;
  if ( a1 )
  {
    if ( *a1 )
    {
      FileW = CreateFileW(a1, 0, 3u, 0, 3u, 0x2000080u, 0);
      if ( FileW != (HANDLE)-1LL )
      {
        CloseHandle(FileW);
        memset_0(pszDest, 0, 0x20Cu);
        v5 = StringCchCopyExW(pszDest, 0x105u, a1, v4, dwCreationDisposition, 0x100u);
        if ( v5 >= 0 )
        {
          FileOp.hwnd = 0;
          FileOp.pFrom = pszDest;
          *(_QWORD *)&FileOp.wFunc = 3;
          *(_OWORD *)&FileOp.hNameMappings = 0;
          FileOp.pTo = 0;
          *(_QWORD *)&FileOp.fFlags = 1044;
          v6 = SHFileOperationW(&FileOp);
          v2 = v6;
          if ( v6 )
            MyDbgPrintfW(0xFFFFFFFFLL, L"SHFileOperation Failed with error: %d", v6, v7);
        }
        else
        {
          return (unsigned __int16)v5;
        }
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1800029d4  push    rbp
0x1800029d6  push    rbx
0x1800029d7  push    rsi
0x1800029d8  push    rdi
0x1800029d9  lea     rbp, [rsp-1A8h]
0x1800029e1  sub     rsp, 2A8h
0x1800029e8  mov     rax, cs:__security_cookie
0x1800029ef  xor     rax, rsp
0x1800029f2  mov     [rbp+1C0h+var_30], rax
0x1800029f9  xor     esi, esi
0x1800029fb  mov     rdi, rcx
0x1800029fe  mov     ebx, esi
0x180002a00  test    rcx, rcx
0x180002a03  jz      loc_180002ACD
0x180002a09  cmp     [rcx], si
0x180002a0c  jz      loc_180002ACD
0x180002a12  mov     [rsp+2C0h+hTemplateFile], rsi; hTemplateFile
0x180002a17  lea     r8d, [rsi+3]; dwShareMode
0x180002a1b  mov     [rsp+2C0h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x180002a23  xor     r9d, r9d; lpSecurityAttributes
0x180002a26  xor     edx, edx; dwDesiredAccess
0x180002a28  mov     dword ptr [rsp+2C0h+dwCreationDisposition], 3; unsigned __int64 *
0x180002a30  call    cs:__imp_CreateFileW
0x180002a36  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180002a3a  jz      loc_180002ACD
0x180002a40  mov     rcx, rax; hObject
0x180002a43  call    cs:__imp_CloseHandle
0x180002a49  xor     edx, edx; Val
0x180002a4b  lea     rcx, [rbp+1C0h+pszDest]; void *
0x180002a4f  mov     r8d, 20Ch; Size
0x180002a55  call    memset_0
0x180002a5a  mov     r8, rdi; unsigned __int16 *
0x180002a5d  mov     [rsp+2C0h+dwFlagsAndAttributes], 100h; unsigned int
0x180002a65  mov     edx, 105h; unsigned __int64
0x180002a6a  lea     rcx, [rbp+1C0h+pszDest]; pszDest
0x180002a6e  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180002a73  test    eax, eax
0x180002a75  jns     short loc_180002A7C
0x180002a77  movzx   ebx, ax
0x180002a7a  jmp     short loc_180002ACD
0x180002a7c  lea     rax, [rbp+1C0h+pszDest]
0x180002a80  mov     [rsp+2C0h+FileOp.hwnd], rsi
0x180002a85  xorps   xmm0, xmm0
0x180002a88  mov     [rsp+2C0h+FileOp.pFrom], rax
0x180002a8d  lea     rcx, [rsp+2C0h+FileOp]; lpFileOp
0x180002a92  mov     qword ptr [rsp+2C0h+FileOp.wFunc], 3
0x180002a9b  movdqu  xmmword ptr [rsp+2C0h+FileOp.hNameMappings], xmm0
0x180002aa1  mov     [rsp+2C0h+FileOp.pTo], rsi
0x180002aa6  mov     qword ptr [rsp+2C0h+FileOp.fFlags], 414h
0x180002aaf  call    cs:__imp_SHFileOperationW
0x180002ab5  mov     ebx, eax
0x180002ab7  test    eax, eax
0x180002ab9  jz      short loc_180002ACD
0x180002abb  mov     r8d, eax
0x180002abe  lea     rdx, aShfileoperatio; "SHFileOperation Failed with error: %d"
0x180002ac5  or      ecx, 0FFFFFFFFh
0x180002ac8  call    MyDbgPrintfW
0x180002acd  mov     eax, ebx
0x180002acf  mov     rcx, [rbp+1C0h+var_30]
0x180002ad6  xor     rcx, rsp; StackCookie
0x180002ad9  call    __security_check_cookie
0x180002ade  add     rsp, 2A8h
0x180002ae5  pop     rdi
0x180002ae6  pop     rsi
0x180002ae7  pop     rbx
0x180002ae8  pop     rbp
0x180002ae9  retn
```
