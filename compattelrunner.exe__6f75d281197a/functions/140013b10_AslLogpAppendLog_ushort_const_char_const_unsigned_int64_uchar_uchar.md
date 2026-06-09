# AslLogpAppendLog(ushort const *,char const *,unsigned __int64,uchar,uchar)

- ea: `0x140013b10`
- end: `0x140013c45`
- name: `?AslLogpAppendLog@@YAJPEBGPEBD_KEE@Z`
- size: `309`
- prototype: `int(const unsigned __int16 *, const char *, unsigned __int64, unsigned __int8, unsigned __int8)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140013dcc`

## callees

- `0x140001ba0`
- `0x1400113b4`
- `0x140013b10`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140013c21`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140013c21`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140013b63`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140013b63`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140013bef`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140013c0b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140013bef`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140013c0b`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x140013b99`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x140013b99`

## pseudocode

```c
__int64 __fastcall AslLogpAppendLog(const unsigned __int16 *a1, const char *a2, DWORD a3, char a4, unsigned __int8 a5)
{
  HANDLE FileW; // rdi
  unsigned int v8; // ebx
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-30h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+48h] [rbp-28h] BYREF
  __int64 Buffer; // [rsp+58h] [rbp-18h] BYREF
  int v13; // [rsp+60h] [rbp-10h]
  char v14; // [rsp+64h] [rbp-Ch]

  NumberOfBytesWritten = 0;
  FileW = CreateFileW(a1, 4u, 1u, 0, 4u, a4 == 0 ? 0x80000000 : 0, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    return (unsigned int)-1073741790;
  }
  else
  {
    if ( a5 )
    {
      Buffer = 0;
      v13 = 0;
      v14 = 0;
      SystemTime = 0;
      GetLocalTime(&SystemTime);
      if ( (int)RtlStringCchPrintfA(
                  (char *)&Buffer,
                  0xDu,
                  "%02d:%02d:%02d.%03d",
                  SystemTime.wHour,
                  SystemTime.wMinute,
                  SystemTime.wSecond,
                  SystemTime.wMilliseconds) >= 0 )
        WriteFile(FileW, &Buffer, 0xDu, &NumberOfBytesWritten, 0);
    }
    v8 = !WriteFile(FileW, a2, a3, &NumberOfBytesWritten, 0) ? 0xC0000022 : 0;
    CloseHandle(FileW);
  }
  return v8;
}

```

## disassembly

```asm
0x140013b10  mov     [rsp-18h+arg_18], rbx
0x140013b15  push    rbp
0x140013b16  push    rsi
0x140013b17  push    rdi
0x140013b18  mov     rbp, rsp
0x140013b1b  sub     rsp, 70h
0x140013b1f  mov     rax, cs:__security_cookie
0x140013b26  xor     rax, rsp
0x140013b29  mov     [rbp+var_8], rax
0x140013b2d  neg     r9b
0x140013b30  mov     [rsp+70h+hTemplateFile], 0; hTemplateFile
0x140013b39  mov     rbx, rdx
0x140013b3c  mov     [rbp+NumberOfBytesWritten], 0
0x140013b43  sbb     eax, eax
0x140013b45  mov     edx, 4; dwDesiredAccess
0x140013b4a  not     eax
0x140013b4c  mov     rsi, r8
0x140013b4f  and     eax, 80000000h
0x140013b54  xor     r9d, r9d; lpSecurityAttributes
0x140013b57  mov     [rsp+70h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x140013b5b  lea     r8d, [rdx-3]; dwShareMode
0x140013b5f  mov     [rsp+70h+dwCreationDisposition], edx; dwCreationDisposition
0x140013b63  call    cs:__imp_CreateFileW
0x140013b69  mov     rdi, rax
0x140013b6c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140013b70  jnz     short loc_140013B7C
0x140013b72  mov     ebx, 0C0000022h
0x140013b77  jmp     loc_140013C27
0x140013b7c  cmp     [rbp+arg_20], 0
0x140013b80  jz      short loc_140013BF5
0x140013b82  xor     eax, eax
0x140013b84  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x140013b88  xorps   xmm0, xmm0
0x140013b8b  mov     [rbp+Buffer], rax
0x140013b8f  mov     [rbp+var_10], eax
0x140013b92  mov     [rbp+var_C], al
0x140013b95  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x140013b99  call    cs:__imp_GetLocalTime
0x140013b9f  movzx   ecx, [rbp+SystemTime.wSecond]
0x140013ba3  lea     r8, a02d02d02d03d; "%02d:%02d:%02d.%03d"
0x140013baa  movzx   edx, [rbp+SystemTime.wMinute]
0x140013bae  movzx   eax, [rbp+SystemTime.wMilliseconds]
0x140013bb2  movzx   r9d, [rbp+SystemTime.wHour]
0x140013bb7  mov     dword ptr [rsp+70h+hTemplateFile], eax
0x140013bbb  mov     [rsp+70h+dwFlagsAndAttributes], ecx
0x140013bbf  lea     rcx, [rbp+Buffer]; char *
0x140013bc3  mov     [rsp+70h+dwCreationDisposition], edx
0x140013bc7  mov     edx, 0Dh; unsigned __int64
0x140013bcc  call    ?RtlStringCchPrintfA@@YAJPEAD_KPEBDZZ; RtlStringCchPrintfA(char *,unsigned __int64,char const *,...)
0x140013bd1  test    eax, eax
0x140013bd3  js      short loc_140013BF5
0x140013bd5  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140013bd9  mov     qword ptr [rsp+70h+dwCreationDisposition], 0; lpOverlapped
0x140013be2  mov     r8d, 0Dh; nNumberOfBytesToWrite
0x140013be8  lea     rdx, [rbp+Buffer]; lpBuffer
0x140013bec  mov     rcx, rdi; hFile
0x140013bef  call    cs:__imp_WriteFile
0x140013bf5  mov     r8d, esi; nNumberOfBytesToWrite
0x140013bf8  mov     qword ptr [rsp+70h+dwCreationDisposition], 0; lpOverlapped
0x140013c01  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140013c05  mov     rdx, rbx; lpBuffer
0x140013c08  mov     rcx, rdi; hFile
0x140013c0b  call    cs:__imp_WriteFile
0x140013c11  neg     eax
0x140013c13  mov     ebx, 0C0000022h
0x140013c18  sbb     ecx, ecx
0x140013c1a  not     ecx
0x140013c1c  and     ebx, ecx
0x140013c1e  mov     rcx, rdi; hObject
0x140013c21  call    cs:__imp_CloseHandle
0x140013c27  mov     eax, ebx
0x140013c29  mov     rcx, [rbp+var_8]
0x140013c2d  xor     rcx, rsp; StackCookie
0x140013c30  call    __security_check_cookie
0x140013c35  mov     rbx, [rsp+70h+arg_18]
0x140013c3d  add     rsp, 70h
0x140013c41  pop     rdi
0x140013c42  pop     rsi
0x140013c43  pop     rbp
0x140013c44  retn
```
