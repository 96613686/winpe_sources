# RegisterUpdateNotify

- ea: `0x180010a7c`
- end: `0x180010b62`
- name: `RegisterUpdateNotify`
- size: `230`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callers

- `0x18000f330`

## callees

- `0x18000a52c`
- `0x180010a7c`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180010aea`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180010aea`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180010abc`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180010abc`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x180010b16`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x180010b16`

## pseudocode

```c
int __fastcall RegisterUpdateNotify(_QWORD *a1)
{
  HANDLE FileMappingW; // rax
  int i; // ebx
  HWND v4; // rcx
  __int64 v5; // rdx

  LODWORD(FileMappingW) = IsIsWindowPresent();
  if ( (_BYTE)FileMappingW )
  {
    FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, 0x320u, L"MSACM Chooser File Mapping");
    a1[14] = FileMappingW;
    a1[13] = 0;
    if ( FileMappingW )
    {
      FileMappingW = MapViewOfFile(FileMappingW, 0xF001Fu, 0, 0, 0);
      a1[13] = FileMappingW;
      if ( FileMappingW )
      {
        for ( i = 0; i < 100; ++i )
        {
          v4 = *(HWND *)(a1[13] + 8LL * i);
          if ( v4 )
          {
            if ( v4 != (HWND)a1[2] )
            {
              LODWORD(FileMappingW) = IsWindow(v4);
              if ( (_DWORD)FileMappingW )
                continue;
            }
          }
          FileMappingW = (HANDLE)a1[2];
          *(_QWORD *)(a1[13] + 8LL * i) = FileMappingW;
          break;
        }
        while ( ++i < 100 )
        {
          v5 = a1[13];
          FileMappingW = (HANDLE)a1[2];
          if ( *(HANDLE *)(v5 + 8LL * i) == FileMappingW )
            *(_QWORD *)(v5 + 8LL * i) = 0;
        }
      }
    }
  }
  return (int)FileMappingW;
}

```

## disassembly

```asm
0x180010a7c  mov     [rsp+arg_0], rbx
0x180010a81  mov     [rsp+arg_8], rsi
0x180010a86  push    rdi
0x180010a87  sub     rsp, 30h
0x180010a8b  mov     rdi, rcx
0x180010a8e  call    IsIsWindowPresent
0x180010a93  test    al, al
0x180010a95  jz      loc_180010B52
0x180010a9b  xor     r9d, r9d; dwMaximumSizeHigh
0x180010a9e  lea     rax, gszChooserFileMapping; "MSACM Chooser File Mapping"
0x180010aa5  mov     [rsp+38h+lpName], rax; lpName
0x180010aaa  xor     edx, edx; lpFileMappingAttributes
0x180010aac  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x180010ab0  mov     [rsp+38h+dwMaximumSizeLow], 320h; dwMaximumSizeLow
0x180010ab8  lea     r8d, [r9+4]; flProtect
0x180010abc  call    cs:__imp_CreateFileMappingW
0x180010ac2  mov     [rdi+70h], rax
0x180010ac6  mov     qword ptr [rdi+68h], 0
0x180010ace  test    rax, rax
0x180010ad1  jz      short loc_180010B52
0x180010ad3  xor     r9d, r9d; dwFileOffsetLow
0x180010ad6  mov     qword ptr [rsp+38h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x180010adf  xor     r8d, r8d; dwFileOffsetHigh
0x180010ae2  mov     edx, 0F001Fh; dwDesiredAccess
0x180010ae7  mov     rcx, rax; hFileMappingObject
0x180010aea  call    cs:__imp_MapViewOfFile
0x180010af0  mov     [rdi+68h], rax
0x180010af4  test    rax, rax
0x180010af7  jz      short loc_180010B52
0x180010af9  xor     ebx, ebx
0x180010afb  cmp     ebx, 64h ; 'd'
0x180010afe  jge     short loc_180010B4B
0x180010b00  mov     rax, [rdi+68h]
0x180010b04  movsxd  rsi, ebx
0x180010b07  mov     rcx, [rax+rsi*8]; hWnd
0x180010b0b  test    rcx, rcx
0x180010b0e  jz      short loc_180010B24
0x180010b10  cmp     rcx, [rdi+10h]
0x180010b14  jz      short loc_180010B24
0x180010b16  call    cs:__imp_IsWindow
0x180010b1c  test    eax, eax
0x180010b1e  jz      short loc_180010B24
0x180010b20  inc     ebx
0x180010b22  jmp     short loc_180010AFB
0x180010b24  mov     rcx, [rdi+68h]
0x180010b28  mov     rax, [rdi+10h]
0x180010b2c  mov     [rcx+rsi*8], rax
0x180010b30  jmp     short loc_180010B4B
0x180010b32  mov     rdx, [rdi+68h]
0x180010b36  mov     rax, [rdi+10h]
0x180010b3a  movsxd  rcx, ebx
0x180010b3d  cmp     [rdx+rcx*8], rax
0x180010b41  jnz     short loc_180010B4B
0x180010b43  mov     qword ptr [rdx+rcx*8], 0
0x180010b4b  inc     ebx
0x180010b4d  cmp     ebx, 64h ; 'd'
0x180010b50  jl      short loc_180010B32
0x180010b52  mov     rbx, [rsp+38h+arg_0]
0x180010b57  mov     rsi, [rsp+38h+arg_8]
0x180010b5c  add     rsp, 30h
0x180010b60  pop     rdi
0x180010b61  retn
```
