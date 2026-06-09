# AslLogpAppendLog(ushort const *,char const *,unsigned __int64,uchar,uchar)

- ea: `0x1400042c0`
- end: `0x1400043f4`
- name: `?AslLogpAppendLog@@YAJPEBGPEBD_KEE@Z`
- size: `308`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const char *, DWORD, char, unsigned __int8)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x14000457c`

## callees

- `0x1400023ae`
- `0x1400042c0`
- `0x140004a5c`
- `0x1400115f0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x140004349`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x140004349`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140004313`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140004313`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14000439f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400043bb`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14000439f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400043bb`

## pseudocode

```c
__int64 __fastcall AslLogpAppendLog(const unsigned __int16 *a1, const char *a2, DWORD a3, char a4, unsigned __int8 a5)
{
  HANDLE FileW; // rdi
  unsigned int v8; // ebx
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-30h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+48h] [rbp-28h] BYREF
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
    CloseHandle_0(FileW);
  }
  return v8;
}

```

## disassembly

```asm
0x1400042c0  mov     [rsp-18h+arg_18], rbx
0x1400042c5  push    rbp
0x1400042c6  push    rsi
0x1400042c7  push    rdi
0x1400042c8  mov     rbp, rsp
0x1400042cb  sub     rsp, 70h
0x1400042cf  mov     rax, cs:__security_cookie
0x1400042d6  xor     rax, rsp
0x1400042d9  mov     [rbp+var_8], rax
0x1400042dd  neg     r9b
0x1400042e0  mov     [rsp+70h+hTemplateFile], 0; hTemplateFile
0x1400042e9  mov     rbx, rdx
0x1400042ec  mov     [rbp+NumberOfBytesWritten], 0
0x1400042f3  sbb     eax, eax
0x1400042f5  mov     edx, 4; dwDesiredAccess
0x1400042fa  not     eax
0x1400042fc  mov     rsi, r8
0x1400042ff  and     eax, 80000000h
0x140004304  xor     r9d, r9d; lpSecurityAttributes
0x140004307  mov     [rsp+70h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x14000430b  lea     r8d, [rdx-3]; dwShareMode
0x14000430f  mov     [rsp+70h+dwCreationDisposition], edx; dwCreationDisposition
0x140004313  call    cs:__imp_CreateFileW
0x140004319  mov     rdi, rax
0x14000431c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140004320  jnz     short loc_14000432C
0x140004322  mov     ebx, 0C0000022h
0x140004327  jmp     loc_1400043D6
0x14000432c  cmp     [rbp+arg_20], 0
0x140004330  jz      short loc_1400043A5
0x140004332  xor     eax, eax
0x140004334  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x140004338  xorps   xmm0, xmm0
0x14000433b  mov     [rbp+Buffer], rax
0x14000433f  mov     [rbp+var_10], eax
0x140004342  mov     [rbp+var_C], al
0x140004345  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x140004349  call    cs:__imp_GetLocalTime
0x14000434f  movzx   ecx, [rbp+SystemTime.wSecond]
0x140004353  lea     r8, a02d02d02d03d; "%02d:%02d:%02d.%03d"
0x14000435a  movzx   edx, [rbp+SystemTime.wMinute]
0x14000435e  movzx   eax, [rbp+SystemTime.wMilliseconds]
0x140004362  movzx   r9d, [rbp+SystemTime.wHour]
0x140004367  mov     dword ptr [rsp+70h+hTemplateFile], eax
0x14000436b  mov     [rsp+70h+dwFlagsAndAttributes], ecx
0x14000436f  lea     rcx, [rbp+Buffer]; char *
0x140004373  mov     [rsp+70h+dwCreationDisposition], edx
0x140004377  mov     edx, 0Dh; unsigned __int64
0x14000437c  call    ?RtlStringCchPrintfA@@YAJPEAD_KPEBDZZ; RtlStringCchPrintfA(char *,unsigned __int64,char const *,...)
0x140004381  test    eax, eax
0x140004383  js      short loc_1400043A5
0x140004385  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140004389  mov     qword ptr [rsp+70h+dwCreationDisposition], 0; lpOverlapped
0x140004392  mov     r8d, 0Dh; nNumberOfBytesToWrite
0x140004398  lea     rdx, [rbp+Buffer]; lpBuffer
0x14000439c  mov     rcx, rdi; hFile
0x14000439f  call    cs:__imp_WriteFile
0x1400043a5  mov     r8d, esi; nNumberOfBytesToWrite
0x1400043a8  mov     qword ptr [rsp+70h+dwCreationDisposition], 0; lpOverlapped
0x1400043b1  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1400043b5  mov     rdx, rbx; lpBuffer
0x1400043b8  mov     rcx, rdi; hFile
0x1400043bb  call    cs:__imp_WriteFile
0x1400043c1  neg     eax
0x1400043c3  mov     ebx, 0C0000022h
0x1400043c8  sbb     ecx, ecx
0x1400043ca  not     ecx
0x1400043cc  and     ebx, ecx
0x1400043ce  mov     rcx, rdi; hObject
0x1400043d1  call    CloseHandle_0
0x1400043d6  mov     eax, ebx
0x1400043d8  mov     rcx, [rbp+var_8]
0x1400043dc  xor     rcx, rsp; StackCookie
0x1400043df  call    __security_check_cookie
0x1400043e4  mov     rbx, [rsp+70h+arg_18]
0x1400043ec  add     rsp, 70h
0x1400043f0  pop     rdi
0x1400043f1  pop     rsi
0x1400043f2  pop     rbp
0x1400043f3  retn
```
