# AslLogpAppendLog(ushort const *,char const *,unsigned __int64,uchar,uchar)

- ea: `0x180069db4`
- end: `0x180069ee9`
- name: `?AslLogpAppendLog@@YAJPEBGPEBD_KEE@Z`
- size: `309`
- prototype: `int(const unsigned __int16 *, const char *, unsigned __int64, unsigned __int8, unsigned __int8)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18006a070`

## callees

- `0x180005e40`
- `0x180068990`
- `0x180069db4`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180069ec5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180069ec5`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180069e3d`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180069e3d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180069e07`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180069e07`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180069e93`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180069eaf`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180069e93`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180069eaf`

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
0x180069db4  mov     [rsp-18h+arg_18], rbx
0x180069db9  push    rbp
0x180069dba  push    rsi
0x180069dbb  push    rdi
0x180069dbc  mov     rbp, rsp
0x180069dbf  sub     rsp, 70h
0x180069dc3  mov     rax, cs:__security_cookie
0x180069dca  xor     rax, rsp
0x180069dcd  mov     [rbp+var_8], rax
0x180069dd1  neg     r9b
0x180069dd4  mov     [rsp+70h+hTemplateFile], 0; hTemplateFile
0x180069ddd  mov     rbx, rdx
0x180069de0  mov     [rbp+NumberOfBytesWritten], 0
0x180069de7  sbb     eax, eax
0x180069de9  mov     edx, 4; dwDesiredAccess
0x180069dee  not     eax
0x180069df0  mov     rsi, r8
0x180069df3  and     eax, 80000000h
0x180069df8  xor     r9d, r9d; lpSecurityAttributes
0x180069dfb  mov     [rsp+70h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x180069dff  lea     r8d, [rdx-3]; dwShareMode
0x180069e03  mov     [rsp+70h+dwCreationDisposition], edx; dwCreationDisposition
0x180069e07  call    cs:__imp_CreateFileW
0x180069e0d  mov     rdi, rax
0x180069e10  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180069e14  jnz     short loc_180069E20
0x180069e16  mov     ebx, 0C0000022h
0x180069e1b  jmp     loc_180069ECB
0x180069e20  cmp     [rbp+arg_20], 0
0x180069e24  jz      short loc_180069E99
0x180069e26  xor     eax, eax
0x180069e28  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x180069e2c  xorps   xmm0, xmm0
0x180069e2f  mov     [rbp+Buffer], rax
0x180069e33  mov     [rbp+var_10], eax
0x180069e36  mov     [rbp+var_C], al
0x180069e39  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x180069e3d  call    cs:__imp_GetLocalTime
0x180069e43  movzx   ecx, [rbp+SystemTime.wSecond]
0x180069e47  lea     r8, a02d02d02d03d; "%02d:%02d:%02d.%03d"
0x180069e4e  movzx   edx, [rbp+SystemTime.wMinute]
0x180069e52  movzx   eax, [rbp+SystemTime.wMilliseconds]
0x180069e56  movzx   r9d, [rbp+SystemTime.wHour]
0x180069e5b  mov     dword ptr [rsp+70h+hTemplateFile], eax
0x180069e5f  mov     [rsp+70h+dwFlagsAndAttributes], ecx
0x180069e63  lea     rcx, [rbp+Buffer]; char *
0x180069e67  mov     [rsp+70h+dwCreationDisposition], edx
0x180069e6b  mov     edx, 0Dh; unsigned __int64
0x180069e70  call    ?RtlStringCchPrintfA@@YAJPEAD_KPEBDZZ; RtlStringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180069e75  test    eax, eax
0x180069e77  js      short loc_180069E99
0x180069e79  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180069e7d  mov     qword ptr [rsp+70h+dwCreationDisposition], 0; lpOverlapped
0x180069e86  mov     r8d, 0Dh; nNumberOfBytesToWrite
0x180069e8c  lea     rdx, [rbp+Buffer]; lpBuffer
0x180069e90  mov     rcx, rdi; hFile
0x180069e93  call    cs:__imp_WriteFile
0x180069e99  mov     r8d, esi; nNumberOfBytesToWrite
0x180069e9c  mov     qword ptr [rsp+70h+dwCreationDisposition], 0; lpOverlapped
0x180069ea5  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180069ea9  mov     rdx, rbx; lpBuffer
0x180069eac  mov     rcx, rdi; hFile
0x180069eaf  call    cs:__imp_WriteFile
0x180069eb5  neg     eax
0x180069eb7  mov     ebx, 0C0000022h
0x180069ebc  sbb     ecx, ecx
0x180069ebe  not     ecx
0x180069ec0  and     ebx, ecx
0x180069ec2  mov     rcx, rdi; hObject
0x180069ec5  call    cs:__imp_CloseHandle
0x180069ecb  mov     eax, ebx
0x180069ecd  mov     rcx, [rbp+var_8]
0x180069ed1  xor     rcx, rsp; StackCookie
0x180069ed4  call    __security_check_cookie
0x180069ed9  mov     rbx, [rsp+70h+arg_18]
0x180069ee1  add     rsp, 70h
0x180069ee5  pop     rdi
0x180069ee6  pop     rsi
0x180069ee7  pop     rbp
0x180069ee8  retn
```
