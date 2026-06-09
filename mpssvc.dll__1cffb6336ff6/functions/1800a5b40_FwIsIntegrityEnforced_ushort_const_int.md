# FwIsIntegrityEnforced(ushort const *,int *)

- ea: `0x1800a5b40`
- end: `0x1800a5d24`
- name: `?FwIsIntegrityEnforced@@YAJPEBGPEAH@Z`
- size: `484`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800a5d2c`

## callees

- `0x18000af3c`
- `0x1800a5b40`
- `0x1800a619c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5b84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5c02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5c63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5ca8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5b84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5c02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5c63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5ca8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a5b73`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a5b73`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800a5cff`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800a5cff`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800a5bf4`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800a5bf4`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800a5c55`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800a5c55`
- `fwbase!FwCloseHandle` at `0x1800a5d08`
- `fwbase!FwCloseHandle` at `0x1800a5d11`
- `fwbase!FwCloseHandle` at `0x1800a5d08`
- `fwbase!FwCloseHandle` at `0x1800a5d11`

## pseudocode

```c
__int64 __fastcall FwIsIntegrityEnforced(const unsigned __int16 *a1, int *a2)
{
  HANDLE FileW; // rax
  HANDLE v4; // rbp
  HANDLE v5; // rsi
  signed int LastError; // eax
  unsigned int v7; // ebx
  __int64 v8; // rcx
  __int64 v9; // rdx
  HANDLE FileMappingW; // rax
  signed int v11; // eax
  const void *v12; // rax
  const void *v13; // rdi
  signed int v14; // eax
  __int64 v15; // rax
  signed int v16; // eax

  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x8000000u, 0);
  v4 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    v5 = 0;
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    v8 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v9 = 31;
LABEL_7:
      WPP_SF_d(*(_QWORD *)(v8 + 16), v9, WPP_8b2bb7d61c06371ab4f9e7ad4a862a27_Traceguids, v7);
    }
  }
  else
  {
    FileMappingW = CreateFileMappingW(FileW, 0, 2u, 0, 0, 0);
    v5 = FileMappingW;
    if ( FileMappingW )
    {
      v12 = MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
      v13 = v12;
      if ( v12 )
      {
        v15 = RtlpImageNtHeader(v12);
        if ( v15 )
        {
          v7 = 0;
          *a2 = *(unsigned __int8 *)(v15 + 94) >> 7;
        }
        else
        {
          v16 = GetLastError();
          v7 = v16;
          if ( v16 > 0 )
            v7 = (unsigned __int16)v16 | 0x80070000;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 34, WPP_8b2bb7d61c06371ab4f9e7ad4a862a27_Traceguids, v7);
        }
        UnmapViewOfFile(v13);
      }
      else
      {
        v14 = GetLastError();
        v7 = v14;
        if ( v14 > 0 )
          v7 = (unsigned __int16)v14 | 0x80070000;
        v8 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          v9 = 33;
          goto LABEL_7;
        }
      }
    }
    else
    {
      v11 = GetLastError();
      v7 = v11;
      if ( v11 > 0 )
        v7 = (unsigned __int16)v11 | 0x80070000;
      v8 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v9 = 32;
        goto LABEL_7;
      }
    }
  }
  FwCloseHandle(v5);
  FwCloseHandle(v4);
  return v7;
}

```

## disassembly

```asm
0x1800a5b40  push    rbx
0x1800a5b42  push    rbp
0x1800a5b43  push    rsi
0x1800a5b44  push    rdi
0x1800a5b45  push    r14
0x1800a5b47  sub     rsp, 40h
0x1800a5b4b  xor     r9d, r9d; lpSecurityAttributes
0x1800a5b4e  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x1800a5b57  mov     r14, rdx
0x1800a5b5a  mov     [rsp+68h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x1800a5b62  mov     edx, 80000000h; dwDesiredAccess
0x1800a5b67  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x1800a5b6f  lea     r8d, [r9+1]; dwShareMode
0x1800a5b73  call    cs:__imp_CreateFileW
0x1800a5b79  mov     rbp, rax
0x1800a5b7c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800a5b80  jnz     short loc_1800A5BD7
0x1800a5b82  xor     esi, esi
0x1800a5b84  call    cs:__imp_GetLastError
0x1800a5b8a  mov     ebx, eax
0x1800a5b8c  test    eax, eax
0x1800a5b8e  jle     short loc_1800A5B99
0x1800a5b90  movzx   ebx, ax
0x1800a5b93  or      ebx, 80070000h
0x1800a5b99  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a5ba0  lea     rax, WPP_GLOBAL_Control
0x1800a5ba7  cmp     rcx, rax
0x1800a5baa  jz      loc_1800A5D05
0x1800a5bb0  test    byte ptr [rcx+1Ch], 1
0x1800a5bb4  jz      loc_1800A5D05
0x1800a5bba  mov     edx, 1Fh
0x1800a5bbf  mov     rcx, [rcx+10h]
0x1800a5bc3  lea     r8, WPP_8b2bb7d61c06371ab4f9e7ad4a862a27_Traceguids
0x1800a5bca  mov     r9d, ebx
0x1800a5bcd  call    WPP_SF_d
0x1800a5bd2  jmp     loc_1800A5D05
0x1800a5bd7  xor     r9d, r9d; dwMaximumSizeHigh
0x1800a5bda  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], 0; lpName
0x1800a5be3  xor     edx, edx; lpFileMappingAttributes
0x1800a5be5  mov     [rsp+68h+dwCreationDisposition], 0; dwMaximumSizeLow
0x1800a5bed  mov     rcx, rbp; hFile
0x1800a5bf0  lea     r8d, [r9+2]; flProtect
0x1800a5bf4  call    cs:__imp_CreateFileMappingW
0x1800a5bfa  mov     rsi, rax
0x1800a5bfd  test    rax, rax
0x1800a5c00  jnz     short loc_1800A5C3F
0x1800a5c02  call    cs:__imp_GetLastError
0x1800a5c08  mov     ebx, eax
0x1800a5c0a  test    eax, eax
0x1800a5c0c  jle     short loc_1800A5C17
0x1800a5c0e  movzx   ebx, ax
0x1800a5c11  or      ebx, 80070000h
0x1800a5c17  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a5c1e  lea     rax, WPP_GLOBAL_Control
0x1800a5c25  cmp     rcx, rax
0x1800a5c28  jz      loc_1800A5D05
0x1800a5c2e  test    byte ptr [rcx+1Ch], 1
0x1800a5c32  jz      loc_1800A5D05
0x1800a5c38  mov     edx, 20h ; ' '
0x1800a5c3d  jmp     short loc_1800A5BBF
0x1800a5c3f  xor     r9d, r9d; dwFileOffsetLow
0x1800a5c42  mov     qword ptr [rsp+68h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x1800a5c4b  xor     r8d, r8d; dwFileOffsetHigh
0x1800a5c4e  mov     rcx, rax; hFileMappingObject
0x1800a5c51  lea     edx, [r9+4]; dwDesiredAccess
0x1800a5c55  call    cs:__imp_MapViewOfFile
0x1800a5c5b  mov     rdi, rax
0x1800a5c5e  test    rax, rax
0x1800a5c61  jnz     short loc_1800A5C9B
0x1800a5c63  call    cs:__imp_GetLastError
0x1800a5c69  mov     ebx, eax
0x1800a5c6b  test    eax, eax
0x1800a5c6d  jle     short loc_1800A5C78
0x1800a5c6f  movzx   ebx, ax
0x1800a5c72  or      ebx, 80070000h
0x1800a5c78  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a5c7f  lea     rax, WPP_GLOBAL_Control
0x1800a5c86  cmp     rcx, rax
0x1800a5c89  jz      short loc_1800A5D05
0x1800a5c8b  test    byte ptr [rcx+1Ch], 1
0x1800a5c8f  jz      short loc_1800A5D05
0x1800a5c91  mov     edx, 21h ; '!'
0x1800a5c96  jmp     loc_1800A5BBF
0x1800a5c9b  mov     rcx, rdi
0x1800a5c9e  call    RtlpImageNtHeader
0x1800a5ca3  test    rax, rax
0x1800a5ca6  jnz     short loc_1800A5CF0
0x1800a5ca8  call    cs:__imp_GetLastError
0x1800a5cae  mov     ebx, eax
0x1800a5cb0  test    eax, eax
0x1800a5cb2  jle     short loc_1800A5CBD
0x1800a5cb4  movzx   ebx, ax
0x1800a5cb7  or      ebx, 80070000h
0x1800a5cbd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a5cc4  lea     rax, WPP_GLOBAL_Control
0x1800a5ccb  cmp     rcx, rax
0x1800a5cce  jz      short loc_1800A5CFC
0x1800a5cd0  test    byte ptr [rcx+1Ch], 1
0x1800a5cd4  jz      short loc_1800A5CFC
0x1800a5cd6  mov     rcx, [rcx+10h]
0x1800a5cda  lea     r8, WPP_8b2bb7d61c06371ab4f9e7ad4a862a27_Traceguids
0x1800a5ce1  mov     edx, 22h ; '"'
0x1800a5ce6  mov     r9d, ebx
0x1800a5ce9  call    WPP_SF_d
0x1800a5cee  jmp     short loc_1800A5CFC
0x1800a5cf0  movzx   ecx, byte ptr [rax+5Eh]
0x1800a5cf4  xor     ebx, ebx
0x1800a5cf6  shr     ecx, 7
0x1800a5cf9  mov     [r14], ecx
0x1800a5cfc  mov     rcx, rdi; lpBaseAddress
0x1800a5cff  call    cs:__imp_UnmapViewOfFile
0x1800a5d05  mov     rcx, rsi
0x1800a5d08  call    cs:__imp_FwCloseHandle
0x1800a5d0e  mov     rcx, rbp
0x1800a5d11  call    cs:__imp_FwCloseHandle
0x1800a5d17  mov     eax, ebx
0x1800a5d19  add     rsp, 40h
0x1800a5d1d  pop     r14
0x1800a5d1f  pop     rdi
0x1800a5d20  pop     rsi
0x1800a5d21  pop     rbp
0x1800a5d22  pop     rbx
0x1800a5d23  retn
```
