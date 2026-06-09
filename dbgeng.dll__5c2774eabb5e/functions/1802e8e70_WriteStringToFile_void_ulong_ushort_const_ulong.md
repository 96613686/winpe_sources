# WriteStringToFile(void *,ulong,ushort const *,ulong)

- ea: `0x1802e8e70`
- end: `0x1802e9048`
- name: `?WriteStringToFile@@YAXPEAXKPEBGK@Z`
- size: `472`
- prototype: `void __fastcall(HANDLE hFile, unsigned int, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180094e40`
- `0x1802e57d0`

## callees

- `0x18007cf9c`
- `0x18007d308`
- `0x180094838`
- `0x1800f0f40`
- `0x1802e8e70`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1802e8ed8`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1802e8f02`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1802e8f38`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1802e8fb7`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1802e8fe1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1802e9011`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1802e8ed8`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1802e8f02`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1802e8f38`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1802e8fb7`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1802e8fe1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1802e9011`

## pseudocode

```c
void __fastcall WriteStringToFile(HANDLE hFile, char a2, const unsigned __int16 *a3, int a4)
{
  int v4; // ebx
  int v7; // r8d
  const unsigned __int16 *v8; // rax
  const unsigned __int16 *v9; // r14
  const WCHAR *v10; // r10
  _BYTE *v11; // rdx
  DWORD v12; // r8d
  _BYTE *i; // rax
  _BYTE *v14; // r14
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-D0h] BYREF
  LPCVOID lpBuffer; // [rsp+40h] [rbp-C0h] BYREF
  int v17; // [rsp+4Ch] [rbp-B4h]
  char v18; // [rsp+58h] [rbp-A8h] BYREF

  NumberOfBytesWritten = 0;
  v4 = a4;
  if ( (a2 & 2) == 0 )
  {
    DbsDynamicString<char>::DbsDynamicString<char>((unsigned int)&lpBuffer, (unsigned int)&v18, 256, a4, 1);
    if ( v10 )
    {
      if ( !DbsDynamicString<char>::CopyStr((DbsDynamicBuffer *)&lpBuffer, v10, -1) )
      {
LABEL_19:
        DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(&lpBuffer);
        return;
      }
      v11 = 0;
      if ( v17 )
        v11 = lpBuffer;
    }
    else
    {
      v11 = 0;
    }
    v12 = 0;
    for ( i = v11; v4; --v4 )
    {
      v14 = i + 1;
      if ( *i == 10 )
      {
        WriteFile(hFile, v11, v12, &NumberOfBytesWritten, 0);
        WriteFile(hFile, "\r\n", 2u, &NumberOfBytesWritten, 0);
        v12 = 0;
        v11 = v14;
      }
      else
      {
        ++v12;
      }
      i = v14;
    }
    WriteFile(hFile, v11, v12, &NumberOfBytesWritten, 0);
    goto LABEL_19;
  }
  v7 = 0;
  v8 = a3;
  if ( a4 )
  {
    do
    {
      v9 = v8 + 1;
      if ( *v8 == 10 )
      {
        WriteFile(hFile, a3, 2 * v7, &NumberOfBytesWritten, 0);
        WriteFile(hFile, L"\r\n", 4u, &NumberOfBytesWritten, 0);
        v7 = 0;
        a3 = v9;
      }
      else
      {
        ++v7;
      }
      v8 = v9;
      --v4;
    }
    while ( v4 );
  }
  WriteFile(hFile, a3, 2 * v7, &NumberOfBytesWritten, 0);
}

```

## disassembly

```asm
0x1802e8e70  mov     [rsp-8+arg_8], rbx
0x1802e8e75  push    rbp
0x1802e8e76  push    rsi
0x1802e8e77  push    r14
0x1802e8e79  lea     rbp, [rsp-70h]
0x1802e8e7e  sub     rsp, 170h
0x1802e8e85  mov     rax, cs:__security_cookie
0x1802e8e8c  xor     rax, rsp
0x1802e8e8f  mov     [rbp+80h+var_20], rax
0x1802e8e93  mov     [rsp+180h+NumberOfBytesWritten], 0
0x1802e8e9b  mov     ebx, r9d
0x1802e8e9e  mov     r10, r8
0x1802e8ea1  mov     rsi, rcx
0x1802e8ea4  test    dl, 2
0x1802e8ea7  jz      loc_1802E8F49
0x1802e8ead  xor     r8d, r8d
0x1802e8eb0  mov     rax, r10
0x1802e8eb3  test    ebx, ebx
0x1802e8eb5  jz      short loc_1802E8F21
0x1802e8eb7  cmp     word ptr [rax], 0Ah
0x1802e8ebb  lea     r14, [rax+2]
0x1802e8ebf  jnz     short loc_1802E8F16
0x1802e8ec1  add     r8d, r8d; nNumberOfBytesToWrite
0x1802e8ec4  mov     [rsp+180h+lpOverlapped], 0; lpOverlapped
0x1802e8ecd  lea     r9, [rsp+180h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1802e8ed2  mov     rdx, r10; lpBuffer
0x1802e8ed5  mov     rcx, rsi; hFile
0x1802e8ed8  call    cs:__imp_WriteFile
0x1802e8edf  nop     dword ptr [rax+rax+00h]
0x1802e8ee4  lea     r9, [rsp+180h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1802e8ee9  mov     [rsp+180h+lpOverlapped], 0; lpOverlapped
0x1802e8ef2  mov     r8d, 4; nNumberOfBytesToWrite
0x1802e8ef8  lea     rdx, asc_180661C5C; "\r\n"
0x1802e8eff  mov     rcx, rsi; hFile
0x1802e8f02  call    cs:__imp_WriteFile
0x1802e8f09  nop     dword ptr [rax+rax+00h]
0x1802e8f0e  xor     r8d, r8d
0x1802e8f11  mov     r10, r14
0x1802e8f14  jmp     short loc_1802E8F19
0x1802e8f16  inc     r8d
0x1802e8f19  mov     rax, r14
0x1802e8f1c  add     ebx, 0FFFFFFFFh
0x1802e8f1f  jnz     short loc_1802E8EB7
0x1802e8f21  add     r8d, r8d; nNumberOfBytesToWrite
0x1802e8f24  mov     [rsp+180h+lpOverlapped], 0; lpOverlapped
0x1802e8f2d  lea     r9, [rsp+180h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1802e8f32  mov     rdx, r10; lpBuffer
0x1802e8f35  mov     rcx, rsi; hFile
0x1802e8f38  call    cs:__imp_WriteFile
0x1802e8f3f  nop     dword ptr [rax+rax+00h]
0x1802e8f44  jmp     loc_1802E9027
0x1802e8f49  mov     r8d, 100h
0x1802e8f4f  mov     byte ptr [rsp+180h+lpOverlapped], 1
0x1802e8f54  lea     rdx, [rsp+180h+var_128]
0x1802e8f59  lea     rcx, [rsp+180h+lpBuffer]
0x1802e8f5e  call    ??0?$DbsDynamicString@D@@QEAA@PEADK_N1@Z; DbsDynamicString<char>::DbsDynamicString<char>(char *,ulong,bool,bool)
0x1802e8f63  test    r10, r10
0x1802e8f66  jnz     short loc_1802E8F6C
0x1802e8f68  xor     edx, edx
0x1802e8f6a  jmp     short loc_1802E8F93
0x1802e8f6c  or      r8d, 0FFFFFFFFh; cchWideChar
0x1802e8f70  lea     rcx, [rsp+180h+lpBuffer]; this
0x1802e8f75  mov     rdx, r10; lpWideCharStr
0x1802e8f78  call    ?CopyStr@?$DbsDynamicString@D@@QEAAPEADPEBGK@Z; DbsDynamicString<char>::CopyStr(ushort const *,ulong)
0x1802e8f7d  test    rax, rax
0x1802e8f80  jz      loc_1802E901D
0x1802e8f86  xor     edx, edx
0x1802e8f88  cmp     [rsp+180h+var_134], 1
0x1802e8f8d  cmovnb  rdx, [rsp+180h+lpBuffer]; lpBuffer
0x1802e8f93  xor     r8d, r8d; nNumberOfBytesToWrite
0x1802e8f96  mov     rax, rdx
0x1802e8f99  test    ebx, ebx
0x1802e8f9b  jz      short loc_1802E9000
0x1802e8f9d  cmp     byte ptr [rax], 0Ah
0x1802e8fa0  lea     r14, [rax+1]
0x1802e8fa4  jnz     short loc_1802E8FF5
0x1802e8fa6  lea     r9, [rsp+180h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1802e8fab  mov     [rsp+180h+lpOverlapped], 0; lpOverlapped
0x1802e8fb4  mov     rcx, rsi; hFile
0x1802e8fb7  call    cs:__imp_WriteFile
0x1802e8fbe  nop     dword ptr [rax+rax+00h]
0x1802e8fc3  lea     r9, [rsp+180h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1802e8fc8  mov     [rsp+180h+lpOverlapped], 0; lpOverlapped
0x1802e8fd1  mov     r8d, 2; nNumberOfBytesToWrite
0x1802e8fd7  lea     rdx, asc_180661C7C; "\r\n"
0x1802e8fde  mov     rcx, rsi; hFile
0x1802e8fe1  call    cs:__imp_WriteFile
0x1802e8fe8  nop     dword ptr [rax+rax+00h]
0x1802e8fed  xor     r8d, r8d
0x1802e8ff0  mov     rdx, r14
0x1802e8ff3  jmp     short loc_1802E8FF8
0x1802e8ff5  inc     r8d; nNumberOfBytesToWrite
0x1802e8ff8  mov     rax, r14
0x1802e8ffb  add     ebx, 0FFFFFFFFh
0x1802e8ffe  jnz     short loc_1802E8F9D
0x1802e9000  lea     r9, [rsp+180h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1802e9005  mov     [rsp+180h+lpOverlapped], 0; lpOverlapped
0x1802e900e  mov     rcx, rsi; hFile
0x1802e9011  call    cs:__imp_WriteFile
0x1802e9018  nop     dword ptr [rax+rax+00h]
0x1802e901d  lea     rcx, [rsp+180h+lpBuffer]
0x1802e9022  call    ??1?$DbsDynamicArray@UCODE_CHUNK@@@@QEAA@XZ; DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(void)
0x1802e9027  mov     rcx, [rbp+80h+var_20]
0x1802e902b  xor     rcx, rsp; StackCookie
0x1802e902e  call    __security_check_cookie
0x1802e9033  mov     rbx, [rsp+180h+arg_8]
0x1802e903b  add     rsp, 170h
0x1802e9042  pop     r14
0x1802e9044  pop     rsi
0x1802e9045  pop     rbp
0x1802e9046  retn
```
