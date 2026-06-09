# AslLogpAppendLog(ushort const *,char const *,unsigned __int64,uchar,uchar)

- ea: `0x180012538`
- end: `0x18001266c`
- name: `?AslLogpAppendLog@@YAJPEBGPEBD_KEE@Z`
- size: `308`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const char *, DWORD, char, unsigned __int8)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800127f4`

## callees

- `0x180002bf0`
- `0x180003a20`
- `0x180012538`
- `0x180012cd4`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800125c1`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800125c1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001258b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001258b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180012617`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180012633`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180012617`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180012633`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180012538  mov     [rsp-18h+arg_18], rbx
0x18001253d  push    rbp
0x18001253e  push    rsi
0x18001253f  push    rdi
0x180012540  mov     rbp, rsp
0x180012543  sub     rsp, 70h
0x180012547  mov     rax, cs:__security_cookie
0x18001254e  xor     rax, rsp
0x180012551  mov     [rbp+var_8], rax
0x180012555  neg     r9b
0x180012558  mov     [rsp+70h+hTemplateFile], 0; hTemplateFile
0x180012561  mov     rbx, rdx
0x180012564  mov     [rbp+NumberOfBytesWritten], 0
0x18001256b  sbb     eax, eax
0x18001256d  mov     edx, 4; dwDesiredAccess
0x180012572  not     eax
0x180012574  mov     rsi, r8
0x180012577  and     eax, 80000000h
0x18001257c  xor     r9d, r9d; lpSecurityAttributes
0x18001257f  mov     [rsp+70h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x180012583  lea     r8d, [rdx-3]; dwShareMode
0x180012587  mov     [rsp+70h+dwCreationDisposition], edx; dwCreationDisposition
0x18001258b  call    cs:__imp_CreateFileW
0x180012591  mov     rdi, rax
0x180012594  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180012598  jnz     short loc_1800125A4
0x18001259a  mov     ebx, 0C0000022h
0x18001259f  jmp     loc_18001264E
0x1800125a4  cmp     [rbp+arg_20], 0
0x1800125a8  jz      short loc_18001261D
0x1800125aa  xor     eax, eax
0x1800125ac  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x1800125b0  xorps   xmm0, xmm0
0x1800125b3  mov     [rbp+Buffer], rax
0x1800125b7  mov     [rbp+var_10], eax
0x1800125ba  mov     [rbp+var_C], al
0x1800125bd  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x1800125c1  call    cs:__imp_GetLocalTime
0x1800125c7  movzx   ecx, [rbp+SystemTime.wSecond]
0x1800125cb  lea     r8, a02d02d02d03d; "%02d:%02d:%02d.%03d"
0x1800125d2  movzx   edx, [rbp+SystemTime.wMinute]
0x1800125d6  movzx   eax, [rbp+SystemTime.wMilliseconds]
0x1800125da  movzx   r9d, [rbp+SystemTime.wHour]
0x1800125df  mov     dword ptr [rsp+70h+hTemplateFile], eax
0x1800125e3  mov     [rsp+70h+dwFlagsAndAttributes], ecx
0x1800125e7  lea     rcx, [rbp+Buffer]; char *
0x1800125eb  mov     [rsp+70h+dwCreationDisposition], edx
0x1800125ef  mov     edx, 0Dh; unsigned __int64
0x1800125f4  call    ?RtlStringCchPrintfA@@YAJPEAD_KPEBDZZ; RtlStringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800125f9  test    eax, eax
0x1800125fb  js      short loc_18001261D
0x1800125fd  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180012601  mov     qword ptr [rsp+70h+dwCreationDisposition], 0; lpOverlapped
0x18001260a  mov     r8d, 0Dh; nNumberOfBytesToWrite
0x180012610  lea     rdx, [rbp+Buffer]; lpBuffer
0x180012614  mov     rcx, rdi; hFile
0x180012617  call    cs:__imp_WriteFile
0x18001261d  mov     r8d, esi; nNumberOfBytesToWrite
0x180012620  mov     qword ptr [rsp+70h+dwCreationDisposition], 0; lpOverlapped
0x180012629  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001262d  mov     rdx, rbx; lpBuffer
0x180012630  mov     rcx, rdi; hFile
0x180012633  call    cs:__imp_WriteFile
0x180012639  neg     eax
0x18001263b  mov     ebx, 0C0000022h
0x180012640  sbb     ecx, ecx
0x180012642  not     ecx
0x180012644  and     ebx, ecx
0x180012646  mov     rcx, rdi; hObject
0x180012649  call    CloseHandle_0
0x18001264e  mov     eax, ebx
0x180012650  mov     rcx, [rbp+var_8]
0x180012654  xor     rcx, rsp; StackCookie
0x180012657  call    __security_check_cookie
0x18001265c  mov     rbx, [rsp+70h+arg_18]
0x180012664  add     rsp, 70h
0x180012668  pop     rdi
0x180012669  pop     rsi
0x18001266a  pop     rbp
0x18001266b  retn
```
