# AslLogpAppendLog(ushort const *,char const *,unsigned __int64,uchar,uchar)

- ea: `0x180015020`
- end: `0x180015155`
- name: `?AslLogpAppendLog@@YAJPEBGPEBD_KEE@Z`
- size: `309`
- prototype: `int(const unsigned __int16 *, const char *, unsigned __int64, unsigned __int8, unsigned __int8)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800152dc`

## callees

- `0x180015020`
- `0x180015e60`
- `0x1800191f0`

## import_xrefs

- `KERNEL32!GetLocalTime` at `0x1800150a9`
- `KERNEL32!GetLocalTime` at `0x1800150a9`
- `KERNEL32!WriteFile` at `0x1800150ff`
- `KERNEL32!WriteFile` at `0x18001511b`
- `KERNEL32!WriteFile` at `0x1800150ff`
- `KERNEL32!WriteFile` at `0x18001511b`
- `KERNEL32!CloseHandle` at `0x180015131`
- `KERNEL32!CloseHandle` at `0x180015131`
- `KERNEL32!CreateFileW` at `0x180015073`
- `KERNEL32!CreateFileW` at `0x180015073`

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
0x180015020  mov     [rsp-18h+arg_18], rbx
0x180015025  push    rbp
0x180015026  push    rsi
0x180015027  push    rdi
0x180015028  mov     rbp, rsp
0x18001502b  sub     rsp, 70h
0x18001502f  mov     rax, cs:__security_cookie
0x180015036  xor     rax, rsp
0x180015039  mov     [rbp+var_8], rax
0x18001503d  neg     r9b
0x180015040  mov     [rsp+70h+hTemplateFile], 0; hTemplateFile
0x180015049  mov     rbx, rdx
0x18001504c  mov     [rbp+NumberOfBytesWritten], 0
0x180015053  sbb     eax, eax
0x180015055  mov     edx, 4; dwDesiredAccess
0x18001505a  not     eax
0x18001505c  mov     rsi, r8
0x18001505f  and     eax, 80000000h
0x180015064  xor     r9d, r9d; lpSecurityAttributes
0x180015067  mov     [rsp+70h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x18001506b  lea     r8d, [rdx-3]; dwShareMode
0x18001506f  mov     [rsp+70h+dwCreationDisposition], edx; dwCreationDisposition
0x180015073  call    cs:__imp_CreateFileW
0x180015079  mov     rdi, rax
0x18001507c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180015080  jnz     short loc_18001508C
0x180015082  mov     ebx, 0C0000022h
0x180015087  jmp     loc_180015137
0x18001508c  cmp     [rbp+arg_20], 0
0x180015090  jz      short loc_180015105
0x180015092  xor     eax, eax
0x180015094  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x180015098  xorps   xmm0, xmm0
0x18001509b  mov     [rbp+Buffer], rax
0x18001509f  mov     [rbp+var_10], eax
0x1800150a2  mov     [rbp+var_C], al
0x1800150a5  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x1800150a9  call    cs:__imp_GetLocalTime
0x1800150af  movzx   ecx, [rbp+SystemTime.wSecond]
0x1800150b3  lea     r8, a02d02d02d03d; "%02d:%02d:%02d.%03d"
0x1800150ba  movzx   edx, [rbp+SystemTime.wMinute]
0x1800150be  movzx   eax, [rbp+SystemTime.wMilliseconds]
0x1800150c2  movzx   r9d, [rbp+SystemTime.wHour]
0x1800150c7  mov     dword ptr [rsp+70h+hTemplateFile], eax
0x1800150cb  mov     [rsp+70h+dwFlagsAndAttributes], ecx
0x1800150cf  lea     rcx, [rbp+Buffer]; char *
0x1800150d3  mov     [rsp+70h+dwCreationDisposition], edx
0x1800150d7  mov     edx, 0Dh; unsigned __int64
0x1800150dc  call    ?RtlStringCchPrintfA@@YAJPEAD_KPEBDZZ; RtlStringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800150e1  test    eax, eax
0x1800150e3  js      short loc_180015105
0x1800150e5  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800150e9  mov     qword ptr [rsp+70h+dwCreationDisposition], 0; lpOverlapped
0x1800150f2  mov     r8d, 0Dh; nNumberOfBytesToWrite
0x1800150f8  lea     rdx, [rbp+Buffer]; lpBuffer
0x1800150fc  mov     rcx, rdi; hFile
0x1800150ff  call    cs:__imp_WriteFile
0x180015105  mov     r8d, esi; nNumberOfBytesToWrite
0x180015108  mov     qword ptr [rsp+70h+dwCreationDisposition], 0; lpOverlapped
0x180015111  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180015115  mov     rdx, rbx; lpBuffer
0x180015118  mov     rcx, rdi; hFile
0x18001511b  call    cs:__imp_WriteFile
0x180015121  neg     eax
0x180015123  mov     ebx, 0C0000022h
0x180015128  sbb     ecx, ecx
0x18001512a  not     ecx
0x18001512c  and     ebx, ecx
0x18001512e  mov     rcx, rdi; hObject
0x180015131  call    cs:__imp_CloseHandle
0x180015137  mov     eax, ebx
0x180015139  mov     rcx, [rbp+var_8]
0x18001513d  xor     rcx, rsp; StackCookie
0x180015140  call    __security_check_cookie
0x180015145  mov     rbx, [rsp+70h+arg_18]
0x18001514d  add     rsp, 70h
0x180015151  pop     rdi
0x180015152  pop     rsi
0x180015153  pop     rbp
0x180015154  retn
```
