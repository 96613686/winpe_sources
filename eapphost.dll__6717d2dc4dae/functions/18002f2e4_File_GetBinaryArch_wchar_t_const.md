# File::GetBinaryArch(wchar_t const *)

- ea: `0x18002f2e4`
- end: `0x18002f4af`
- name: `?GetBinaryArch@File@@CA?AW4ArchType@ArchValue@1@PEB_W@Z`
- size: `459`
- prototype: `__int64 __fastcall(const WCHAR *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18001c0fc`

## callees

- `0x18002f2e4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002f32a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002f32a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f489`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f497`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f489`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f497`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002f36a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002f36a`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18002f3bd`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18002f3bd`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18002f47b`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18002f47b`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18002f395`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18002f395`

## pseudocode

```c
__int64 __fastcall File::GetBinaryArch(const WCHAR *a1)
{
  unsigned int v2; // ebx
  HMODULE v3; // r14
  HMODULE v4; // rdi
  void *v5; // rsi
  void *v6; // r15
  HMODULE ModuleHandleW; // rax
  BOOL v8; // r13d
  HANDLE FileW; // rax
  HANDLE FileMappingW; // rax
  HMODULE v11; // rax
  __int64 v12; // rax

  v2 = -1;
  v3 = 0;
  v4 = 0;
  v5 = 0;
  if ( a1 )
  {
    v8 = 0;
    FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
    v6 = FileW;
    if ( FileW != (HANDLE)-1LL )
    {
      FileMappingW = CreateFileMappingW(FileW, 0, 2u, 0, 0, 0);
      v5 = FileMappingW;
      if ( FileMappingW )
      {
        v11 = (HMODULE)MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
        v4 = v11;
        if ( v11 )
        {
          v3 = v11;
          v8 = 1;
        }
      }
    }
  }
  else
  {
    v6 = 0;
    ModuleHandleW = GetModuleHandleW(0);
    if ( ModuleHandleW )
      v3 = ModuleHandleW;
    v8 = ModuleHandleW != 0;
  }
  if ( v8 && *(_WORD *)v3 == 23117 )
  {
    v12 = *((int *)v3 + 15);
    if ( *(_DWORD *)((char *)v3 + v12) == 17744 )
    {
      switch ( *(_WORD *)((char *)v3 + v12 + 4) )
      {
        case 0x14C:
          v2 = 0;
          break;
        case 0x1C4:
          v2 = 3;
          break;
        case 0x200:
          v2 = 1;
          break;
        default:
          if ( *(unsigned __int16 *)((char *)v3 + v12 + 4) == 34404 )
          {
            v2 = 2;
          }
          else if ( *(unsigned __int16 *)((char *)v3 + v12 + 4) == 43620 )
          {
            v2 = 4;
          }
          break;
      }
    }
  }
  if ( a1 )
  {
    if ( v4 )
      UnmapViewOfFile(v4);
    if ( v5 )
      CloseHandle(v5);
    if ( v6 )
      CloseHandle(v6);
  }
  return v2;
}

```

## disassembly

```asm
0x18002f2e4  mov     [rsp+arg_0], rcx
0x18002f2e9  push    rbx
0x18002f2ea  push    rsi
0x18002f2eb  push    rdi
0x18002f2ec  push    r12
0x18002f2ee  push    r13
0x18002f2f0  push    r14
0x18002f2f2  push    r15
0x18002f2f4  sub     rsp, 50h
0x18002f2f8  mov     r12, rcx
0x18002f2fb  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002f2ff  mov     [rsp+88h+var_48], ebx
0x18002f303  xor     r14d, r14d
0x18002f306  xor     edi, edi
0x18002f308  mov     [rsp+88h+arg_8], rdi
0x18002f310  xor     esi, esi
0x18002f312  mov     [rsp+88h+arg_18], rsi
0x18002f31a  test    rcx, rcx
0x18002f31d  jnz     short loc_18002F346
0x18002f31f  xor     r15d, r15d
0x18002f322  mov     [rsp+88h+arg_10], r15
0x18002f32a  call    cs:__imp_GetModuleHandleW
0x18002f330  test    rax, rax
0x18002f333  cmovnz  r14, rax
0x18002f337  xor     r13d, r13d
0x18002f33a  test    rax, rax
0x18002f33d  setnz   r13b
0x18002f341  jmp     loc_18002F3DC
0x18002f346  xor     r13d, r13d
0x18002f349  mov     [rsp+88h+hTemplateFile], rsi; hTemplateFile
0x18002f34e  mov     [rsp+88h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002f356  mov     [rsp+88h+dwCreationDisposition], 3; dwCreationDisposition
0x18002f35e  xor     r9d, r9d; lpSecurityAttributes
0x18002f361  mov     edx, 80000000h; dwDesiredAccess
0x18002f366  lea     r8d, [r13+1]; dwShareMode
0x18002f36a  call    cs:__imp_CreateFileW
0x18002f370  mov     r15, rax
0x18002f373  mov     [rsp+88h+arg_10], rax
0x18002f37b  cmp     rax, rbx
0x18002f37e  jz      short loc_18002F3DC
0x18002f380  mov     qword ptr [rsp+88h+dwFlagsAndAttributes], rsi; lpName
0x18002f385  mov     [rsp+88h+dwCreationDisposition], esi; dwMaximumSizeLow
0x18002f389  xor     r9d, r9d; dwMaximumSizeHigh
0x18002f38c  xor     edx, edx; lpFileMappingAttributes
0x18002f38e  lea     r8d, [r13+2]; flProtect
0x18002f392  mov     rcx, rax; hFile
0x18002f395  call    cs:__imp_CreateFileMappingW
0x18002f39b  mov     rsi, rax
0x18002f39e  mov     [rsp+88h+arg_18], rax
0x18002f3a6  test    rax, rax
0x18002f3a9  jz      short loc_18002F3DC
0x18002f3ab  mov     qword ptr [rsp+88h+dwCreationDisposition], rdi; dwNumberOfBytesToMap
0x18002f3b0  xor     r9d, r9d; dwFileOffsetLow
0x18002f3b3  xor     r8d, r8d; dwFileOffsetHigh
0x18002f3b6  lea     edx, [r13+4]; dwDesiredAccess
0x18002f3ba  mov     rcx, rax; hFileMappingObject
0x18002f3bd  call    cs:__imp_MapViewOfFile
0x18002f3c3  mov     rdi, rax
0x18002f3c6  mov     [rsp+88h+arg_8], rax
0x18002f3ce  test    rax, rax
0x18002f3d1  jz      short loc_18002F3DC
0x18002f3d3  mov     r14, rax
0x18002f3d6  mov     r13d, 1
0x18002f3dc  cmp     r13d, 1
0x18002f3e0  jnz     loc_18002F46E
0x18002f3e6  mov     eax, 5A4Dh
0x18002f3eb  cmp     [r14], ax
0x18002f3ef  jnz     short loc_18002F448
0x18002f3f1  movsxd  rax, dword ptr [r14+3Ch]
0x18002f3f5  cmp     dword ptr [rax+r14], 4550h
0x18002f3fd  jnz     short loc_18002F448
0x18002f3ff  movzx   ecx, word ptr [rax+r14+4]
0x18002f405  sub     ecx, 14Ch
0x18002f40b  jz      short loc_18002F442
0x18002f40d  sub     ecx, 78h ; 'x'
0x18002f410  jz      short loc_18002F43B
0x18002f412  sub     ecx, 3Ch ; '<'
0x18002f415  jz      short loc_18002F434
0x18002f417  sub     ecx, 8464h
0x18002f41d  jz      short loc_18002F42D
0x18002f41f  cmp     ecx, 2400h
0x18002f425  jnz     short loc_18002F448
0x18002f427  lea     ebx, [r13+3]
0x18002f42b  jmp     short loc_18002F444
0x18002f42d  mov     ebx, 2
0x18002f432  jmp     short loc_18002F444
0x18002f434  mov     ebx, 1
0x18002f439  jmp     short loc_18002F444
0x18002f43b  mov     ebx, 3
0x18002f440  jmp     short loc_18002F444
0x18002f442  xor     ebx, ebx
0x18002f444  mov     [rsp+88h+var_48], ebx
0x18002f448  jmp     short loc_18002F46E
0x18002f44a  mov     r12, [rsp+88h+arg_0]
0x18002f452  mov     ebx, [rsp+88h+var_48]
0x18002f456  mov     rdi, [rsp+88h+arg_8]
0x18002f45e  mov     r15, [rsp+88h+arg_10]
0x18002f466  mov     rsi, [rsp+88h+arg_18]
0x18002f46e  test    r12, r12
0x18002f471  jz      short loc_18002F49D
0x18002f473  test    rdi, rdi
0x18002f476  jz      short loc_18002F481
0x18002f478  mov     rcx, rdi; lpBaseAddress
0x18002f47b  call    cs:__imp_UnmapViewOfFile
0x18002f481  test    rsi, rsi
0x18002f484  jz      short loc_18002F48F
0x18002f486  mov     rcx, rsi; hObject
0x18002f489  call    cs:__imp_CloseHandle
0x18002f48f  test    r15, r15
0x18002f492  jz      short loc_18002F49D
0x18002f494  mov     rcx, r15; hObject
0x18002f497  call    cs:__imp_CloseHandle
0x18002f49d  mov     eax, ebx
0x18002f49f  add     rsp, 50h
0x18002f4a3  pop     r15
0x18002f4a5  pop     r14
0x18002f4a7  pop     r13
0x18002f4a9  pop     r12
0x18002f4ab  pop     rdi
0x18002f4ac  pop     rsi
0x18002f4ad  pop     rbx
0x18002f4ae  retn
```
