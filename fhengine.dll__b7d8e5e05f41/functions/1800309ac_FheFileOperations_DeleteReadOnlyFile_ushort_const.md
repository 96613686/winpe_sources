# FheFileOperations::DeleteReadOnlyFile(ushort const *)

- ea: `0x1800309ac`
- end: `0x180030aa4`
- name: `?DeleteReadOnlyFile@FheFileOperations@@YAJPEBG@Z`
- size: `248`
- prototype: `__int64 __fastcall(const WCHAR *this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180012b44`
- `0x180030790`
- `0x180030b88`

## callees

- `0x1800309ac`
- `0x180031680`

## import_xrefs

- `KERNEL32!SetFileInformationByHandle` at `0x180030a2b`
- `KERNEL32!SetFileInformationByHandle` at `0x180030a45`
- `KERNEL32!SetFileInformationByHandle` at `0x180030a2b`
- `KERNEL32!SetFileInformationByHandle` at `0x180030a45`
- `KERNEL32!GetLastError` at `0x180030a4f`
- `KERNEL32!GetLastError` at `0x180030a6f`
- `KERNEL32!GetLastError` at `0x180030a4f`
- `KERNEL32!GetLastError` at `0x180030a6f`
- `KERNEL32!CloseHandle` at `0x180030a67`
- `KERNEL32!CloseHandle` at `0x180030a67`
- `KERNEL32!CreateFileW` at `0x1800309ed`
- `KERNEL32!CreateFileW` at `0x1800309ed`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=3
__int64 __fastcall FheFileOperations::DeleteReadOnlyFile(const WCHAR *this, const unsigned __int16 *a2)
{
  HANDLE FileW; // rax
  void *v3; // rdi
  unsigned int v4; // ebx
  signed int v5; // eax
  signed int LastError; // eax
  char v8[8]; // [rsp+40h] [rbp-48h] BYREF
  _OWORD FileInformation[2]; // [rsp+48h] [rbp-40h] BYREF
  __int64 v10; // [rsp+68h] [rbp-20h]

  FileW = CreateFileW(this, 0x10100u, 7u, 0, 3u, 0x200080u, 0);
  v3 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    v4 = 0;
    v10 = 128;
    memset(FileInformation, 0, sizeof(FileInformation));
    SetFileInformationByHandle(FileW, FileBasicInfo, FileInformation, 0x28u);
    v8[0] = 1;
    if ( !SetFileInformationByHandle(v3, FileDispositionInfo, v8, 1u) )
    {
      v5 = GetLastError();
      v4 = v5;
      if ( v5 > 0 )
        v4 = (unsigned __int16)v5 | 0x80070000;
    }
    CloseHandle(v3);
  }
  return v4;
}

```

## disassembly

```asm
0x1800309ac  mov     [rsp+arg_8], rbx
0x1800309b1  push    rdi
0x1800309b2  sub     rsp, 80h
0x1800309b9  mov     rax, cs:__security_cookie
0x1800309c0  xor     rax, rsp
0x1800309c3  mov     [rsp+88h+var_18], rax
0x1800309c8  xor     r9d, r9d; lpSecurityAttributes
0x1800309cb  mov     [rsp+88h+hTemplateFile], 0; hTemplateFile
0x1800309d4  mov     [rsp+88h+dwFlagsAndAttributes], 200080h; dwFlagsAndAttributes
0x1800309dc  mov     edx, 10100h; dwDesiredAccess
0x1800309e1  mov     [rsp+88h+dwCreationDisposition], 3; dwCreationDisposition
0x1800309e9  lea     r8d, [r9+7]; dwShareMode
0x1800309ed  call    cs:__imp_CreateFileW
0x1800309f3  mov     rdi, rax
0x1800309f6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800309fa  jz      short loc_180030A6F
0x1800309fc  xor     ebx, ebx
0x1800309fe  mov     [rsp+88h+var_20], 80h
0x180030a07  xorps   xmm0, xmm0
0x180030a0a  mov     [rsp+88h+var_48], bl
0x180030a0e  xorps   xmm1, xmm1
0x180030a11  lea     r8, [rsp+88h+FileInformation]; lpFileInformation
0x180030a16  xor     edx, edx; FileInformationClass
0x180030a18  mov     rcx, rax; hFile
0x180030a1b  lea     r9d, [rbx+28h]; dwBufferSize
0x180030a1f  movdqu  [rsp+88h+FileInformation], xmm0
0x180030a25  movdqu  [rsp+88h+var_30], xmm1
0x180030a2b  call    cs:__imp_SetFileInformationByHandle
0x180030a31  lea     r9d, [rbx+1]; dwBufferSize
0x180030a35  mov     [rsp+88h+var_48], 1
0x180030a3a  lea     r8, [rsp+88h+var_48]; lpFileInformation
0x180030a3f  mov     rcx, rdi; hFile
0x180030a42  lea     edx, [rbx+4]; FileInformationClass
0x180030a45  call    cs:__imp_SetFileInformationByHandle
0x180030a4b  test    eax, eax
0x180030a4d  jnz     short loc_180030A64
0x180030a4f  call    cs:__imp_GetLastError
0x180030a55  mov     ebx, eax
0x180030a57  test    eax, eax
0x180030a59  jle     short loc_180030A64
0x180030a5b  movzx   ebx, ax
0x180030a5e  or      ebx, 80070000h
0x180030a64  mov     rcx, rdi; hObject
0x180030a67  call    cs:__imp_CloseHandle
0x180030a6d  jmp     short loc_180030A84
0x180030a6f  call    cs:__imp_GetLastError
0x180030a75  mov     ebx, eax
0x180030a77  test    eax, eax
0x180030a79  jle     short loc_180030A84
0x180030a7b  movzx   ebx, ax
0x180030a7e  or      ebx, 80070000h
0x180030a84  mov     eax, ebx
0x180030a86  mov     rcx, [rsp+88h+var_18]
0x180030a8b  xor     rcx, rsp; StackCookie
0x180030a8e  call    __security_check_cookie
0x180030a93  mov     rbx, [rsp+88h+arg_8]
0x180030a9b  add     rsp, 80h
0x180030aa2  pop     rdi
0x180030aa3  retn
```
