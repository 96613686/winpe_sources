# SADatGetData(ushort const *,ulong,uchar * const,void * *)

- ea: `0x180019bb0`
- end: `0x180019ce9`
- name: `?SADatGetData@@YAJPEBGKQEAEPEAPEAX@Z`
- size: `313`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, unsigned __int8 *const, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180019cf0`

## callees

- `0x180019bb0`
- `0x180019d4c`
- `0x18001aa9a`
- `0x18001aac0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019c31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019c75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019c31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019c75`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180019c22`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180019c22`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180019c6b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180019c6b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019cbc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019cbc`

## pseudocode

```c
signed int __fastcall SADatGetData(const unsigned __int16 *a1, __int64 a2, unsigned __int8 *const a3, void **a4)
{
  unsigned __int64 v6; // r8
  HANDLE FileW; // rax
  void *v8; // rdi
  signed int result; // eax
  signed int LastError; // eax
  signed int v11; // ebx
  int v12; // ecx
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-238h] BYREF
  WCHAR FileName[264]; // [rsp+50h] [rbp-228h] BYREF

  memset_0(FileName, 0, 0x20Au);
  SADatPath(a1, FileName, v6);
  FileW = CreateFileW(FileName, 0x80000000, 3u, 0, 3u, 2u, 0);
  v8 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  NumberOfBytesRead = 0;
  if ( !ReadFile(FileW, a3, 6u, &NumberOfBytesRead, 0) )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    if ( v11 < 0 )
      goto LABEL_15;
    goto LABEL_12;
  }
  if ( NumberOfBytesRead == 6 )
  {
    v11 = 0;
LABEL_12:
    v12 = v11;
    if ( (unsigned __int8)(a3[4] - 1) > 1u )
      v12 = -2147418113;
    v11 = v12;
    goto LABEL_15;
  }
  v11 = -2147418113;
LABEL_15:
  if ( v8 )
    CloseHandle(v8);
  return v11;
}

```

## disassembly

```asm
0x180019bb0  mov     [rsp+arg_8], rbx
0x180019bb5  mov     [rsp+arg_18], rsi
0x180019bba  push    rdi
0x180019bbb  sub     rsp, 270h
0x180019bc2  mov     rax, cs:__security_cookie
0x180019bc9  xor     rax, rsp
0x180019bcc  mov     [rsp+278h+var_18], rax
0x180019bd4  mov     rsi, r8
0x180019bd7  mov     rbx, rcx
0x180019bda  mov     r8d, 20Ah; Size
0x180019be0  lea     rcx, [rsp+278h+FileName]; void *
0x180019be5  xor     edx, edx; Val
0x180019be7  call    memset_0
0x180019bec  lea     rdx, [rsp+278h+FileName]; unsigned __int16 *
0x180019bf1  mov     rcx, rbx; unsigned __int16 *
0x180019bf4  call    ?SADatPath@@YAXPEBGPEAG_K@Z; SADatPath(ushort const *,ushort *,unsigned __int64)
0x180019bf9  mov     r8d, 3; dwShareMode
0x180019bff  mov     [rsp+278h+hTemplateFile], 0; hTemplateFile
0x180019c08  mov     [rsp+278h+dwFlagsAndAttributes], 2; dwFlagsAndAttributes
0x180019c10  lea     rcx, [rsp+278h+FileName]; lpFileName
0x180019c15  xor     r9d, r9d; lpSecurityAttributes
0x180019c18  mov     [rsp+278h+dwCreationDisposition], r8d; dwCreationDisposition
0x180019c1d  mov     edx, 80000000h; dwDesiredAccess
0x180019c22  call    cs:__imp_CreateFileW
0x180019c28  mov     rdi, rax
0x180019c2b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180019c2f  jnz     short loc_180019C49
0x180019c31  call    cs:__imp_GetLastError
0x180019c37  test    eax, eax
0x180019c39  jle     loc_180019CC4
0x180019c3f  movzx   eax, ax
0x180019c42  or      eax, 80070000h
0x180019c47  jmp     short loc_180019CC4
0x180019c49  lea     r9, [rsp+278h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180019c4e  mov     [rsp+278h+NumberOfBytesRead], 0
0x180019c56  mov     r8d, 6; nNumberOfBytesToRead
0x180019c5c  mov     qword ptr [rsp+278h+dwCreationDisposition], 0; lpOverlapped
0x180019c65  mov     rdx, rsi; lpBuffer
0x180019c68  mov     rcx, rdi; hFile
0x180019c6b  call    cs:__imp_ReadFile
0x180019c71  test    eax, eax
0x180019c73  jnz     short loc_180019C90
0x180019c75  call    cs:__imp_GetLastError
0x180019c7b  mov     ebx, eax
0x180019c7d  test    eax, eax
0x180019c7f  jle     short loc_180019C8A
0x180019c81  movzx   ebx, ax
0x180019c84  or      ebx, 80070000h
0x180019c8a  test    ebx, ebx
0x180019c8c  js      short loc_180019CB4
0x180019c8e  jmp     short loc_180019CA0
0x180019c90  cmp     [rsp+278h+NumberOfBytesRead], 6
0x180019c95  jz      short loc_180019C9E
0x180019c97  mov     ebx, 8000FFFFh
0x180019c9c  jmp     short loc_180019CB4
0x180019c9e  xor     ebx, ebx
0x180019ca0  mov     dl, [rsi+4]
0x180019ca3  mov     ecx, ebx
0x180019ca5  mov     ebx, 8000FFFFh
0x180019caa  dec     dl
0x180019cac  cmp     dl, 1
0x180019caf  cmova   ecx, ebx
0x180019cb2  mov     ebx, ecx
0x180019cb4  test    rdi, rdi
0x180019cb7  jz      short loc_180019CC2
0x180019cb9  mov     rcx, rdi; hObject
0x180019cbc  call    cs:__imp_CloseHandle
0x180019cc2  mov     eax, ebx
0x180019cc4  mov     rcx, [rsp+278h+var_18]
0x180019ccc  xor     rcx, rsp; StackCookie
0x180019ccf  call    __security_check_cookie
0x180019cd4  lea     r11, [rsp+278h+var_8]
0x180019cdc  mov     rbx, [r11+18h]
0x180019ce0  mov     rsi, [r11+28h]
0x180019ce4  mov     rsp, r11
0x180019ce7  pop     rdi
0x180019ce8  retn
```
