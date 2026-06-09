# CircularLog::OpenFile(void)

- ea: `0x18003a8d4`
- end: `0x18003aad5`
- name: `?OpenFile@CircularLog@@IEAAPEAXXZ`
- size: `513`
- prototype: `__int64 __fastcall(CircularLog *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18003a414`

## callees

- `0x18003069c`
- `0x180030d84`
- `0x1800323e4`
- `0x18003a8d4`
- `0x18003dc30`

## import_xrefs

- `KERNEL32!WriteFile` at `0x18003aa29`
- `KERNEL32!WriteFile` at `0x18003aa8e`
- `KERNEL32!WriteFile` at `0x18003aa29`
- `KERNEL32!WriteFile` at `0x18003aa8e`
- `KERNEL32!CreateFileW` at `0x18003a93a`
- `KERNEL32!CreateFileW` at `0x18003a984`
- `KERNEL32!CreateFileW` at `0x18003a93a`
- `KERNEL32!CreateFileW` at `0x18003a984`
- `KERNEL32!GetFileSizeEx` at `0x18003a9e5`
- `KERNEL32!GetFileSizeEx` at `0x18003a9e5`
- `KERNEL32!CloseHandle` at `0x18003a9f2`
- `KERNEL32!CloseHandle` at `0x18003a9f2`
- `KERNEL32!GetLastError` at `0x18003a946`
- `KERNEL32!GetLastError` at `0x18003a993`
- `KERNEL32!GetLastError` at `0x18003a946`
- `KERNEL32!GetLastError` at `0x18003a993`
- `KERNEL32!HeapFree` at `0x18003aac7`
- `KERNEL32!HeapFree` at `0x18003aac7`
- `KERNEL32!GetProcessHeap` at `0x18003aab2`
- `KERNEL32!GetProcessHeap` at `0x18003aab2`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CircularLog::OpenFile(CircularLog *this)
{
  int v1; // edi
  __int64 result; // rax
  HANDLE FileW; // rax
  void *v4; // rbx
  int v5; // edx
  const char *UTF8; // rax
  void *v7; // rdi
  HANDLE ProcessHeap; // rax
  __int16 Buffer; // [rsp+48h] [rbp-C0h] BYREF
  char v10; // [rsp+4Ah] [rbp-BEh]
  unsigned int v11; // [rsp+4Ch] [rbp-BCh] BYREF
  DWORD NumberOfBytesWritten[2]; // [rsp+50h] [rbp-B8h] BYREF
  LARGE_INTEGER FileSize; // [rsp+58h] [rbp-B0h] BYREF
  int v14; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v15; // [rsp+6Ch] [rbp-9Ch]
  LPVOID lpMem; // [rsp+78h] [rbp-90h]
  __int16 v17; // [rsp+80h] [rbp-88h] BYREF

  v1 = 0;
  while ( 1 )
  {
    SString::ConvertToUnicode((SString *)&qword_18006F258);
    result = (__int64)CreateFileW(lpFileName, 4u, 3u, 0, 3u, 0x80u, 0);
    if ( result != -1 )
      break;
    if ( GetLastError() == 2 )
    {
      SString::ConvertToUnicode((SString *)&qword_18006F258);
      FileW = CreateFileW(lpFileName, 4u, 1u, 0, 4u, 0x80u, 0);
      v4 = FileW;
      if ( FileW != (HANDLE)-1LL )
      {
        if ( !GetFileSizeEx(FileW, &FileSize) )
        {
          CloseHandle(v4);
          return -1;
        }
        if ( !FileSize.QuadPart )
        {
          Buffer = -17425;
          v10 = -65;
          WriteFile(v4, &Buffer, 3u, NumberOfBytesWritten, 0);
          v15 = 256;
          lpMem = &v17;
          v14 = 2;
          v17 = 0;
          v11 = 0;
          UTF8 = SString::GetUTF8((SString *)&dword_18006F270, (struct SString::AbstractScratchBuffer *)&v14, &v11);
          WriteFile(v4, UTF8, v11 - 1, NumberOfBytesWritten, 0);
          if ( (v15 & 0x800000000LL) != 0 )
          {
            v7 = lpMem;
            if ( lpMem )
            {
              ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
              if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
              {
                ProcessHeap = GetProcessHeap();
                `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
              }
              HeapFree(ProcessHeap, 0, v7);
            }
          }
        }
        return (__int64)v4;
      }
    }
    if ( GetLastError() == 32 )
    {
      ClrSleepEx(0x64u, v5);
      if ( ++v1 < 10 )
        continue;
    }
    return -1;
  }
  return result;
}

```

## disassembly

```asm
0x18003a8d4  mov     rax, rsp
0x18003a8d7  mov     [rax+8], rbx
0x18003a8db  mov     [rax+10h], rsi
0x18003a8df  mov     [rax+18h], rdi
0x18003a8e3  push    rbp
0x18003a8e4  lea     rbp, [rax-98h]
0x18003a8eb  sub     rsp, 190h
0x18003a8f2  mov     rax, cs:__security_cookie
0x18003a8f9  xor     rax, rsp
0x18003a8fc  mov     [rbp+90h+var_10], rax
0x18003a903  xor     esi, esi
0x18003a905  mov     edi, esi
0x18003a907  lea     rcx, qword_18006F258; this
0x18003a90e  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18003a913  mov     [rsp+190h+hTemplateFile], rsi; hTemplateFile
0x18003a918  mov     [rsp+190h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18003a920  mov     [rsp+190h+dwCreationDisposition], 3; dwCreationDisposition
0x18003a928  xor     r9d, r9d; lpSecurityAttributes
0x18003a92b  lea     edx, [r9+4]; dwDesiredAccess
0x18003a92f  lea     r8d, [r9+3]; dwShareMode
0x18003a933  mov     rcx, cs:lpFileName; lpFileName
0x18003a93a  call    cs:__imp_CreateFileW
0x18003a940  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003a944  jnz     short loc_18003A9B5
0x18003a946  call    cs:__imp_GetLastError
0x18003a94c  cmp     eax, 2
0x18003a94f  jnz     short loc_18003A993
0x18003a951  lea     rcx, qword_18006F258; this
0x18003a958  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18003a95d  mov     [rsp+190h+hTemplateFile], rsi; hTemplateFile
0x18003a962  mov     [rsp+190h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18003a96a  mov     [rsp+190h+dwCreationDisposition], 4; dwCreationDisposition
0x18003a972  xor     r9d, r9d; lpSecurityAttributes
0x18003a975  lea     edx, [r9+4]; dwDesiredAccess
0x18003a979  lea     r8d, [r9+1]; dwShareMode
0x18003a97d  mov     rcx, cs:lpFileName; lpFileName
0x18003a984  call    cs:__imp_CreateFileW
0x18003a98a  mov     rbx, rax
0x18003a98d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003a991  jnz     short loc_18003A9DD
0x18003a993  call    cs:__imp_GetLastError
0x18003a999  cmp     eax, 20h ; ' '
0x18003a99c  jnz     short loc_18003A9B1
0x18003a99e  lea     ecx, [rax+44h]; unsigned int
0x18003a9a1  call    ?ClrSleepEx@@YAKKH@Z; ClrSleepEx(ulong,int)
0x18003a9a6  inc     edi
0x18003a9a8  cmp     edi, 0Ah
0x18003a9ab  jl      loc_18003A907
0x18003a9b1  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003a9b5  mov     rcx, [rbp+90h+var_10]
0x18003a9bc  xor     rcx, rsp; StackCookie
0x18003a9bf  call    __security_check_cookie
0x18003a9c4  lea     r11, [rsp+190h+var_s0]
0x18003a9cc  mov     rbx, [r11+10h]
0x18003a9d0  mov     rsi, [r11+18h]
0x18003a9d4  mov     rdi, [r11+20h]
0x18003a9d8  mov     rsp, r11
0x18003a9db  pop     rbp
0x18003a9dc  retn
0x18003a9dd  lea     rdx, [rsp+190h+FileSize]; lpFileSize
0x18003a9e2  mov     rcx, rbx; hFile
0x18003a9e5  call    cs:__imp_GetFileSizeEx
0x18003a9eb  test    eax, eax
0x18003a9ed  jnz     short loc_18003A9FA
0x18003a9ef  mov     rcx, rbx; hObject
0x18003a9f2  call    cs:__imp_CloseHandle
0x18003a9f8  jmp     short loc_18003A9B1
0x18003a9fa  cmp     qword ptr [rsp+190h+FileSize], rsi
0x18003a9ff  jnz     loc_18003AACD
0x18003aa05  mov     [rsp+190h+Buffer], 0BBEFh
0x18003aa0c  mov     [rsp+190h+var_14E], 0BFh
0x18003aa11  mov     qword ptr [rsp+190h+dwCreationDisposition], rsi; lpOverlapped
0x18003aa16  lea     r9, [rsp+190h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18003aa1b  mov     r8d, 3; nNumberOfBytesToWrite
0x18003aa21  lea     rdx, [rsp+190h+Buffer]; lpBuffer
0x18003aa26  mov     rcx, rbx; hFile
0x18003aa29  call    cs:__imp_WriteFile
0x18003aa2f  mov     qword ptr [rsp+190h+var_130], rsi
0x18003aa34  mov     qword ptr [rsp+64h], 100h
0x18003aa3d  mov     [rsp+190h+lpMem], rsi
0x18003aa42  lea     rax, [rsp+190h+var_118]
0x18003aa47  mov     [rsp+190h+lpMem], rax
0x18003aa4c  mov     [rsp+190h+var_130], 2
0x18003aa54  mov     rax, [rsp+190h+lpMem]
0x18003aa59  mov     [rax], si
0x18003aa5c  mov     [rsp+190h+var_14C], esi
0x18003aa60  lea     r8, [rsp+190h+var_14C]; unsigned int *
0x18003aa65  lea     rdx, [rsp+190h+var_130]; struct SString::AbstractScratchBuffer *
0x18003aa6a  lea     rcx, dword_18006F270; this
0x18003aa71  call    ?GetUTF8@SString@@QEBAPEBDAEAVAbstractScratchBuffer@1@PEAI@Z; SString::GetUTF8(SString::AbstractScratchBuffer &,uint *)
0x18003aa76  mov     r8d, [rsp+190h+var_14C]
0x18003aa7b  dec     r8d; nNumberOfBytesToWrite
0x18003aa7e  mov     qword ptr [rsp+190h+dwCreationDisposition], rsi; lpOverlapped
0x18003aa83  lea     r9, [rsp+190h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18003aa88  mov     rdx, rax; lpBuffer
0x18003aa8b  mov     rcx, rbx; hFile
0x18003aa8e  call    cs:__imp_WriteFile
0x18003aa94  nop
0x18003aa95  test    byte ptr [rsp+190h+var_128], 8
0x18003aa9a  jz      short loc_18003AACD
0x18003aa9c  mov     rdi, [rsp+190h+lpMem]
0x18003aaa1  test    rdi, rdi
0x18003aaa4  jz      short loc_18003AACD
0x18003aaa6  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18003aaad  test    rax, rax
0x18003aab0  jnz     short loc_18003AABF
0x18003aab2  call    cs:__imp_GetProcessHeap
0x18003aab8  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18003aabf  mov     r8, rdi; lpMem
0x18003aac2  xor     edx, edx; dwFlags
0x18003aac4  mov     rcx, rax; hHeap
0x18003aac7  call    cs:__imp_HeapFree
0x18003aacd  mov     rax, rbx
0x18003aad0  jmp     loc_18003A9B5
```
