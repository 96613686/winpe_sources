# Microsoft::Windows::Performance::CEventSourceHandler::WriteManifestFile(ushort const *,char const *,ulong)

- ea: `0x18001df84`
- end: `0x18001e02b`
- name: `?WriteManifestFile@CEventSourceHandler@Performance@Windows@Microsoft@@AEAAJPEBGPEBDK@Z`
- size: `167`
- prototype: `int(Microsoft::Windows::Performance::CEventSourceHandler *__hidden this, const unsigned __int16 *, const char *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001b2d4`

## callees

- `0x18001df84`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dfcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e002`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dfcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e002`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e01a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e01a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001dfbd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001dfbd`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001dff8`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001dff8`

## pseudocode

```c
int __fastcall Microsoft::Windows::Performance::CEventSourceHandler::WriteManifestFile(
        Microsoft::Windows::Performance::CEventSourceHandler *this,
        const unsigned __int16 *a2,
        const char *a3,
        DWORD a4)
{
  HANDLE FileW; // rax
  void *v7; // rdi
  int result; // eax
  unsigned int v9; // ebx
  signed int LastError; // eax
  Microsoft::Windows::Performance::CEventSourceHandler *NumberOfBytesWritten; // [rsp+70h] [rbp+8h] BYREF

  NumberOfBytesWritten = this;
  FileW = CreateFileW(a2, 0x40000000u, 0, 0, 2u, 0x80u, 0);
  v7 = FileW;
  if ( FileW )
  {
    v9 = 0;
    LODWORD(NumberOfBytesWritten) = 0;
    if ( !WriteFile(FileW, a3, a4, (LPDWORD)&NumberOfBytesWritten, 0) )
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
    }
    CloseHandle(v7);
    return v9;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18001df84  mov     rax, rsp
0x18001df87  mov     [rax+8], rcx
0x18001df8b  push    rbx
0x18001df8c  push    rbp
0x18001df8d  push    rsi
0x18001df8e  push    rdi
0x18001df8f  sub     rsp, 48h
0x18001df93  mov     qword ptr [rax-38h], 0
0x18001df9b  mov     esi, r9d
0x18001df9e  mov     rbp, r8
0x18001dfa1  mov     dword ptr [rax-40h], 80h
0x18001dfa8  mov     rcx, rdx; lpFileName
0x18001dfab  mov     dword ptr [rax-48h], 2
0x18001dfb2  xor     r9d, r9d; lpSecurityAttributes
0x18001dfb5  xor     r8d, r8d; dwShareMode
0x18001dfb8  mov     edx, 40000000h; dwDesiredAccess
0x18001dfbd  call    cs:__imp_CreateFileW
0x18001dfc3  mov     rdi, rax
0x18001dfc6  test    rax, rax
0x18001dfc9  jnz     short loc_18001DFDF
0x18001dfcb  call    cs:__imp_GetLastError
0x18001dfd1  test    eax, eax
0x18001dfd3  jle     short loc_18001E022
0x18001dfd5  movzx   eax, ax
0x18001dfd8  or      eax, 80070000h
0x18001dfdd  jmp     short loc_18001E022
0x18001dfdf  xor     ebx, ebx
0x18001dfe1  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001dfe6  mov     r8d, esi; nNumberOfBytesToWrite
0x18001dfe9  mov     dword ptr [rsp+68h+NumberOfBytesWritten], ebx
0x18001dfed  mov     rdx, rbp; lpBuffer
0x18001dff0  mov     [rsp+68h+lpOverlapped], rbx; lpOverlapped
0x18001dff5  mov     rcx, rdi; hFile
0x18001dff8  call    cs:__imp_WriteFile
0x18001dffe  test    eax, eax
0x18001e000  jnz     short loc_18001E017
0x18001e002  call    cs:__imp_GetLastError
0x18001e008  mov     ebx, eax
0x18001e00a  test    eax, eax
0x18001e00c  jle     short loc_18001E017
0x18001e00e  movzx   ebx, ax
0x18001e011  or      ebx, 80070000h
0x18001e017  mov     rcx, rdi; hObject
0x18001e01a  call    cs:__imp_CloseHandle
0x18001e020  mov     eax, ebx
0x18001e022  add     rsp, 48h
0x18001e026  pop     rdi
0x18001e027  pop     rsi
0x18001e028  pop     rbp
0x18001e029  pop     rbx
0x18001e02a  retn
```
