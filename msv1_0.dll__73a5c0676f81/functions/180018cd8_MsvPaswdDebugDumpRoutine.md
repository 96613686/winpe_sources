# MsvPaswdDebugDumpRoutine

- ea: `0x180018cd8`
- end: `0x180018e66`
- name: `MsvPaswdDebugDumpRoutine`
- size: `398`
- prototype: `__int64 __fastcall(char *Format, va_list ArgList)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180034ecc`

## callees

- `0x180018cd8`
- `0x18002fb50`
- `0x18002fb90`
- `0x18002fba0`
- `0x180030980`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180018d9d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180018d9d`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180018dcf`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180018dcf`

## pseudocode

```c
void __fastcall MsvPaswdDebugDumpRoutine(char *Format, va_list ArgList)
{
  unsigned int v4; // ebx
  int v5; // eax
  __int64 v6; // rcx
  __int64 v7; // r8
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-C0h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+48h] [rbp-B8h] BYREF
  char Buffer[2064]; // [rsp+60h] [rbp-A0h] BYREF

  SystemTime = 0;
  NumberOfBytesWritten = 0;
  if ( MsvPaswdLogFile )
  {
    v4 = 0;
    Buffer[2048] = 0;
    if ( dword_180086474 )
    {
      GetLocalTime(&SystemTime);
      v4 = sprintf_s(
             Buffer,
             0x801u,
             "%02u/%02u %02u:%02u:%02u ",
             SystemTime.wMonth,
             SystemTime.wDay,
             SystemTime.wHour,
             SystemTime.wMinute,
             SystemTime.wSecond);
    }
    v5 = vsnprintf_s(&Buffer[v4], 2049LL - v4, 2046LL - v4, Format, ArgList);
    v6 = v5 + v4;
    if ( v5 < 0 )
      v6 = v4;
    if ( !(_DWORD)v6 || Buffer[(unsigned int)(v6 - 1)] != 10 )
    {
      dword_180086474 = 0;
      LODWORD(v7) = v6;
LABEL_8:
      WriteFile(MsvPaswdLogFile, Buffer, v7, &NumberOfBytesWritten, 0);
      return;
    }
    v7 = (unsigned int)(v6 + 1);
    dword_180086474 = 1;
    if ( (unsigned int)v7 < 0x801 )
    {
      Buffer[(unsigned int)(v6 - 1)] = 13;
      Buffer[v6] = 10;
      if ( (unsigned int)v7 >= 0x801uLL )
        _report_rangecheckfailure();
      Buffer[v7] = 0;
      goto LABEL_8;
    }
  }
}

```

## disassembly

```asm
0x180018cd8  mov     [rsp-8+arg_10], rbx
0x180018cdd  mov     [rsp-8+arg_18], rsi
0x180018ce2  push    rbp
0x180018ce3  push    rdi
0x180018ce4  push    r15
0x180018ce6  lea     rbp, [rsp-780h]
0x180018cee  sub     rsp, 880h
0x180018cf5  mov     rax, cs:__security_cookie
0x180018cfc  xor     rax, rsp
0x180018cff  mov     [rbp+790h+var_20], rax
0x180018d06  cmp     cs:MsvPaswdLogFile, 0
0x180018d0e  xorps   xmm0, xmm0
0x180018d11  movups  xmmword ptr [rsp+890h+SystemTime.wYear], xmm0
0x180018d16  mov     rsi, rdx
0x180018d19  mov     [rsp+890h+NumberOfBytesWritten], 0
0x180018d21  mov     rdi, rcx
0x180018d24  jz      short loc_180018DA3
0x180018d26  xor     ebx, ebx
0x180018d28  mov     r15d, 801h
0x180018d2e  cmp     cs:dword_180086474, ebx
0x180018d34  mov     [rbp+790h+var_30], bl
0x180018d3a  jnz     loc_180018DCA
0x180018d40  mov     ecx, ebx
0x180018d42  lea     rax, [rsp+890h+Buffer]
0x180018d47  mov     r8d, 7FEh
0x180018d4d  mov     [rsp+890h+ArgList], rsi; ArgList
0x180018d52  sub     r8, rcx; MaxCount
0x180018d55  mov     rdx, r15
0x180018d58  sub     rdx, rcx; BufferCount
0x180018d5b  mov     r9, rdi; Format
0x180018d5e  add     rcx, rax; Buffer
0x180018d61  call    _vsnprintf_s
0x180018d66  test    eax, eax
0x180018d68  lea     ecx, [rax+rbx]
0x180018d6b  cmovs   ecx, ebx
0x180018d6e  test    ecx, ecx
0x180018d70  jnz     loc_180018E50
0x180018d76  mov     cs:dword_180086474, 0
0x180018d80  mov     r8d, ecx; nNumberOfBytesToWrite
0x180018d83  mov     rcx, cs:MsvPaswdLogFile; hFile
0x180018d8a  lea     r9, [rsp+890h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180018d8f  lea     rdx, [rsp+890h+Buffer]; lpBuffer
0x180018d94  mov     [rsp+890h+ArgList], 0; lpOverlapped
0x180018d9d  call    cs:__imp_WriteFile
0x180018da3  mov     rcx, [rbp+790h+var_20]
0x180018daa  xor     rcx, rsp; StackCookie
0x180018dad  call    __security_check_cookie
0x180018db2  lea     r11, [rsp+890h+var_10]
0x180018dba  mov     rbx, [r11+30h]
0x180018dbe  mov     rsi, [r11+38h]
0x180018dc2  mov     rsp, r11
0x180018dc5  pop     r15
0x180018dc7  pop     rdi
0x180018dc8  pop     rbp
0x180018dc9  retn
0x180018dca  lea     rcx, [rsp+890h+SystemTime]; lpSystemTime
0x180018dcf  call    cs:__imp_GetLocalTime
0x180018dd5  movzx   ecx, [rsp+890h+SystemTime.wMinute]
0x180018dda  movzx   edx, [rsp+890h+SystemTime.wHour]
0x180018ddf  movzx   r8d, [rsp+890h+SystemTime.wDay]
0x180018de5  movzx   eax, [rsp+890h+SystemTime.wSecond]
0x180018dea  movzx   r9d, [rsp+890h+SystemTime.wMonth]
0x180018df0  mov     [rsp+890h+var_858], eax
0x180018df4  mov     [rsp+890h+var_860], ecx
0x180018df8  lea     rcx, [rsp+890h+Buffer]; Buffer
0x180018dfd  mov     [rsp+890h+var_868], edx
0x180018e01  mov     rdx, r15; BufferCount
0x180018e04  mov     dword ptr [rsp+890h+ArgList], r8d
0x180018e09  lea     r8, Format; "%02u/%02u %02u:%02u:%02u "
0x180018e10  call    sprintf_s
0x180018e15  mov     ebx, eax
0x180018e17  jmp     loc_180018D40
0x180018e1c  lea     r8d, [rcx+1]
0x180018e20  mov     cs:dword_180086474, 1
0x180018e2a  cmp     r8d, r15d
0x180018e2d  jnb     loc_180018DA3
0x180018e33  mov     [rsp+rax+890h+Buffer], 0Dh
0x180018e38  mov     eax, r8d
0x180018e3b  mov     [rsp+rcx+890h+Buffer], 0Ah
0x180018e40  cmp     rax, r15
0x180018e43  jnb     short loc_180018E60
0x180018e45  mov     [rsp+r8+890h+Buffer], 0
0x180018e4b  jmp     loc_180018D83
0x180018e50  lea     eax, [rcx-1]
0x180018e53  cmp     [rsp+rax+890h+Buffer], 0Ah
0x180018e58  jnz     loc_180018D76
0x180018e5e  jmp     short loc_180018E1C
0x180018e60  call    __report_rangecheckfailure
```
