# CFileStream::SetTime(WHICHTIME,_FILETIME)

- ea: `0x180005ac8`
- end: `0x180005b22`
- name: `?SetTime@CFileStream@@QEAAJW4WHICHTIME@@U_FILETIME@@@Z`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800062c8`

## callees

- `0x180005ac8`
- `0x180026bc4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b11`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x180005af1`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x180005af1`

## pseudocode

```c
__int64 __fastcall CFileStream::SetTime(__int64 a1, int a2, FILETIME a3)
{
  unsigned int v3; // ebx
  FILETIME *v4; // r8
  FILETIME *p_LastWriteTime; // r9
  FILETIME *v6; // rax
  DWORD LastError; // eax
  FILETIME LastWriteTime; // [rsp+40h] [rbp+18h] BYREF

  LastWriteTime = a3;
  v3 = 0;
  v4 = 0;
  p_LastWriteTime = 0;
  if ( a2 )
  {
    v6 = 0;
    if ( a2 == 1 )
      p_LastWriteTime = &LastWriteTime;
    else
      v4 = &LastWriteTime;
  }
  else
  {
    v6 = &LastWriteTime;
  }
  if ( !SetFileTime(*(HANDLE *)(a1 + 64), v6, v4, p_LastWriteTime) )
  {
    LastError = GetLastError();
    return (unsigned int)Win32ErrorToScode(LastError);
  }
  return v3;
}

```

## disassembly

```asm
0x180005ac8  mov     qword ptr [rsp+LastWriteTime.dwLowDateTime], r8
0x180005acd  push    rbx
0x180005ace  sub     rsp, 20h
0x180005ad2  xor     ebx, ebx
0x180005ad4  xor     r8d, r8d; lpLastAccessTime
0x180005ad7  xor     r9d, r9d
0x180005ada  test    edx, edx
0x180005adc  jz      short loc_180005B03
0x180005ade  xor     eax, eax
0x180005ae0  cmp     edx, 1
0x180005ae3  jnz     short loc_180005B0A
0x180005ae5  lea     r9, [rsp+28h+LastWriteTime]; lpLastWriteTime
0x180005aea  mov     rcx, [rcx+40h]; hFile
0x180005aee  mov     rdx, rax; lpCreationTime
0x180005af1  call    cs:__imp_SetFileTime
0x180005af7  test    eax, eax
0x180005af9  jz      short loc_180005B11
0x180005afb  mov     eax, ebx
0x180005afd  add     rsp, 20h
0x180005b01  pop     rbx
0x180005b02  retn
0x180005b03  lea     rax, [rsp+28h+LastWriteTime]
0x180005b08  jmp     short loc_180005AEA
0x180005b0a  lea     r8, [rsp+28h+LastWriteTime]
0x180005b0f  jmp     short loc_180005AEA
0x180005b11  call    cs:__imp_GetLastError
0x180005b17  mov     ecx, eax; unsigned int
0x180005b19  call    ?Win32ErrorToScode@@YAJK@Z; Win32ErrorToScode(ulong)
0x180005b1e  mov     ebx, eax
0x180005b20  jmp     short loc_180005AFB
```
