# CircularLog::CheckForLogReset(int)

- ea: `0x18003a740`
- end: `0x18003a8d1`
- name: `?CheckForLogReset@CircularLog@@IEAAXH@Z`
- size: `401`
- prototype: `void __fastcall(CircularLog *__hidden this, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18003a1e8`
- `0x18003a414`

## callees

- `0x18003069c`
- `0x180030d84`
- `0x1800364c0`
- `0x18003a684`
- `0x18003a740`
- `0x18003dc30`

## import_xrefs

- `KERNEL32!MoveFileExW` at `0x18003a83d`
- `KERNEL32!MoveFileExW` at `0x18003a83d`
- `KERNEL32!GetFileAttributesExW` at `0x18003a7d4`
- `KERNEL32!GetFileAttributesExW` at `0x18003a7d4`
- `KERNEL32!CloseHandle` at `0x18003a85b`
- `KERNEL32!CloseHandle` at `0x18003a87d`
- `KERNEL32!CloseHandle` at `0x18003a8a1`
- `KERNEL32!CloseHandle` at `0x18003a85b`
- `KERNEL32!CloseHandle` at `0x18003a87d`
- `KERNEL32!CloseHandle` at `0x18003a8a1`
- `KERNEL32!GetLastError` at `0x18003a847`
- `KERNEL32!GetLastError` at `0x18003a847`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall CircularLog::CheckForLogReset(CircularLog *this, int a2)
{
  int v3; // edi
  CircularLog *v4; // rcx
  int v5; // edx
  const WCHAR *v6; // rbx
  int v7; // edx
  void **v8; // [rsp+20h] [rbp-40h] BYREF
  HANDLE hObject; // [rsp+28h] [rbp-38h]
  _BYTE FileInformation[28]; // [rsp+30h] [rbp-30h] BYREF
  unsigned int v11; // [rsp+4Ch] [rbp-14h]
  unsigned int v12; // [rsp+50h] [rbp-10h]

  if ( dword_18006F2B8 )
  {
    v3 = 0;
    while ( 1 )
    {
      v8 = &FileLockHolder::`vftable';
      hObject = (HANDLE)-1LL;
      SString::ConvertToUnicode((SString *)&dword_18006F2A0);
      if ( (int)FileLockHolder::AcquireNoThrow((FileLockHolder *)&v8, qword_18006F2B0, 0, 0) < 0 )
        break;
      if ( a2 )
      {
        SString::ConvertToUnicode((SString *)&qword_18006F258);
        if ( !GetFileAttributesExW(lpFileName, GetFileExInfoStandard, FileInformation) )
          break;
        v5 = (v12 | ((unsigned __int64)v11 << 32)) > (unsigned int)dword_18006F2B8;
      }
      else
      {
        v5 = CircularLog::CheckLogHeader(v4);
      }
      if ( !v5 )
        break;
      SString::ConvertToUnicode((SString *)&dword_18006F288);
      v6 = lpNewFileName;
      SString::ConvertToUnicode((SString *)&qword_18006F258);
      if ( MoveFileExW(lpFileName, v6, 3u) || GetLastError() != 32 )
        break;
      if ( hObject != (HANDLE)-1LL )
      {
        CloseHandle(hObject);
        hObject = (HANDLE)-1LL;
      }
      ClrSleepEx(0x64u, v7);
      v8 = &FileLockHolder::`vftable';
      if ( hObject != (HANDLE)-1LL )
      {
        CloseHandle(hObject);
        hObject = (HANDLE)-1LL;
      }
      if ( ++v3 >= 10 )
        return;
    }
    v8 = &FileLockHolder::`vftable';
    if ( hObject != (HANDLE)-1LL )
      CloseHandle(hObject);
  }
}

```

## disassembly

```asm
0x18003a740  mov     [rsp-18h+arg_0], rbx
0x18003a745  mov     [rsp-18h+arg_8], rsi
0x18003a74a  mov     [rsp-18h+arg_10], rdi
0x18003a74f  push    rbp
0x18003a750  push    r14
0x18003a752  push    r15
0x18003a754  mov     rbp, rsp
0x18003a757  sub     rsp, 60h
0x18003a75b  mov     rax, cs:__security_cookie
0x18003a762  xor     rax, rsp
0x18003a765  mov     [rbp+var_8], rax
0x18003a769  mov     esi, edx
0x18003a76b  cmp     cs:dword_18006F2B8, 0
0x18003a772  jz      loc_18003A8AB
0x18003a778  xor     edi, edi
0x18003a77a  lea     r15, ??_7FileLockHolder@@6B@; const FileLockHolder::`vftable'
0x18003a781  or      r14, 0FFFFFFFFFFFFFFFFh
0x18003a785  mov     [rbp+var_40], r15
0x18003a789  mov     [rbp+hObject], r14
0x18003a78d  lea     rcx, dword_18006F2A0; this
0x18003a794  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18003a799  xor     r9d, r9d; int *
0x18003a79c  xor     r8d, r8d; void *
0x18003a79f  mov     rdx, cs:qword_18006F2B0; unsigned __int16 *
0x18003a7a6  lea     rcx, [rbp+var_40]; this
0x18003a7aa  call    ?AcquireNoThrow@FileLockHolder@@QEAAJPEBGPEAXPEAH@Z; FileLockHolder::AcquireNoThrow(ushort const *,void *,int *)
0x18003a7af  test    eax, eax
0x18003a7b1  js      loc_18003A894
0x18003a7b7  test    esi, esi
0x18003a7b9  jz      short loc_18003A7FF
0x18003a7bb  lea     rcx, qword_18006F258; this
0x18003a7c2  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18003a7c7  lea     r8, [rbp+FileInformation]; lpFileInformation
0x18003a7cb  xor     edx, edx; fInfoLevelId
0x18003a7cd  mov     rcx, cs:lpFileName; lpFileName
0x18003a7d4  call    cs:__imp_GetFileAttributesExW
0x18003a7da  test    eax, eax
0x18003a7dc  jz      loc_18003A894
0x18003a7e2  mov     ecx, [rbp+var_14]
0x18003a7e5  shl     rcx, 20h
0x18003a7e9  mov     eax, [rbp+var_10]
0x18003a7ec  or      rcx, rax
0x18003a7ef  mov     eax, cs:dword_18006F2B8
0x18003a7f5  xor     edx, edx
0x18003a7f7  cmp     rcx, rax
0x18003a7fa  setnbe  dl
0x18003a7fd  jmp     short loc_18003A806
0x18003a7ff  call    ?CheckLogHeader@CircularLog@@IEAAHXZ; CircularLog::CheckLogHeader(void)
0x18003a804  mov     edx, eax
0x18003a806  test    edx, edx
0x18003a808  jz      loc_18003A894
0x18003a80e  lea     rcx, dword_18006F288; this
0x18003a815  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18003a81a  mov     rbx, cs:lpNewFileName
0x18003a821  lea     rcx, qword_18006F258; this
0x18003a828  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18003a82d  mov     r8d, 3; dwFlags
0x18003a833  mov     rdx, rbx; lpNewFileName
0x18003a836  mov     rcx, cs:lpFileName; lpExistingFileName
0x18003a83d  call    cs:__imp_MoveFileExW
0x18003a843  test    eax, eax
0x18003a845  jnz     short loc_18003A894
0x18003a847  call    cs:__imp_GetLastError
0x18003a84d  cmp     eax, 20h ; ' '
0x18003a850  jnz     short loc_18003A894
0x18003a852  mov     rcx, [rbp+hObject]; hObject
0x18003a856  cmp     rcx, r14
0x18003a859  jz      short loc_18003A865
0x18003a85b  call    cs:__imp_CloseHandle
0x18003a861  mov     [rbp+hObject], r14
0x18003a865  mov     ecx, 64h ; 'd'; unsigned int
0x18003a86a  call    ?ClrSleepEx@@YAKKH@Z; ClrSleepEx(ulong,int)
0x18003a86f  nop
0x18003a870  mov     [rbp+var_40], r15
0x18003a874  mov     rcx, [rbp+hObject]; hObject
0x18003a878  cmp     rcx, r14
0x18003a87b  jz      short loc_18003A887
0x18003a87d  call    cs:__imp_CloseHandle
0x18003a883  mov     [rbp+hObject], r14
0x18003a887  inc     edi
0x18003a889  cmp     edi, 0Ah
0x18003a88c  jl      loc_18003A785
0x18003a892  jmp     short loc_18003A8AB
0x18003a894  mov     [rbp+var_40], r15
0x18003a898  mov     rcx, [rbp+hObject]; hObject
0x18003a89c  cmp     rcx, r14
0x18003a89f  jz      short loc_18003A8AB
0x18003a8a1  call    cs:__imp_CloseHandle
0x18003a8a7  mov     [rbp+hObject], r14
0x18003a8ab  mov     rcx, [rbp+var_8]
0x18003a8af  xor     rcx, rsp; StackCookie
0x18003a8b2  call    __security_check_cookie
0x18003a8b7  lea     r11, [rsp+60h+var_s0]
0x18003a8bc  mov     rbx, [r11+20h]
0x18003a8c0  mov     rsi, [r11+28h]
0x18003a8c4  mov     rdi, [r11+30h]
0x18003a8c8  mov     rsp, r11
0x18003a8cb  pop     r15
0x18003a8cd  pop     r14
0x18003a8cf  pop     rbp
0x18003a8d0  retn
```
