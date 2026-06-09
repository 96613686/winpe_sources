# File::GetBinaryArch(wchar_t const *)

- ea: `0x1800123c8`
- end: `0x180012593`
- name: `?GetBinaryArch@File@@CA?AW4ArchType@ArchValue@1@PEB_W@Z`
- size: `459`
- prototype: `__int64 __fastcall(const WCHAR *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18002d96c`

## callees

- `0x1800123c8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001240e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001240e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001256d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001257b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001256d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001257b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001244e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001244e`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800124a1`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800124a1`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180012479`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180012479`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18001255f`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18001255f`

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
0x1800123c8  mov     [rsp+arg_0], rcx
0x1800123cd  push    rbx
0x1800123ce  push    rsi
0x1800123cf  push    rdi
0x1800123d0  push    r12
0x1800123d2  push    r13
0x1800123d4  push    r14
0x1800123d6  push    r15
0x1800123d8  sub     rsp, 50h
0x1800123dc  mov     r12, rcx
0x1800123df  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800123e3  mov     [rsp+88h+var_48], ebx
0x1800123e7  xor     r14d, r14d
0x1800123ea  xor     edi, edi
0x1800123ec  mov     [rsp+88h+arg_8], rdi
0x1800123f4  xor     esi, esi
0x1800123f6  mov     [rsp+88h+arg_18], rsi
0x1800123fe  test    rcx, rcx
0x180012401  jnz     short loc_18001242A
0x180012403  xor     r15d, r15d
0x180012406  mov     [rsp+88h+arg_10], r15
0x18001240e  call    cs:__imp_GetModuleHandleW
0x180012414  test    rax, rax
0x180012417  cmovnz  r14, rax
0x18001241b  xor     r13d, r13d
0x18001241e  test    rax, rax
0x180012421  setnz   r13b
0x180012425  jmp     loc_1800124C0
0x18001242a  xor     r13d, r13d
0x18001242d  mov     [rsp+88h+hTemplateFile], rsi; hTemplateFile
0x180012432  mov     [rsp+88h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18001243a  mov     [rsp+88h+dwCreationDisposition], 3; dwCreationDisposition
0x180012442  xor     r9d, r9d; lpSecurityAttributes
0x180012445  mov     edx, 80000000h; dwDesiredAccess
0x18001244a  lea     r8d, [r13+1]; dwShareMode
0x18001244e  call    cs:__imp_CreateFileW
0x180012454  mov     r15, rax
0x180012457  mov     [rsp+88h+arg_10], rax
0x18001245f  cmp     rax, rbx
0x180012462  jz      short loc_1800124C0
0x180012464  mov     qword ptr [rsp+88h+dwFlagsAndAttributes], rsi; lpName
0x180012469  mov     [rsp+88h+dwCreationDisposition], esi; dwMaximumSizeLow
0x18001246d  xor     r9d, r9d; dwMaximumSizeHigh
0x180012470  xor     edx, edx; lpFileMappingAttributes
0x180012472  lea     r8d, [r13+2]; flProtect
0x180012476  mov     rcx, rax; hFile
0x180012479  call    cs:__imp_CreateFileMappingW
0x18001247f  mov     rsi, rax
0x180012482  mov     [rsp+88h+arg_18], rax
0x18001248a  test    rax, rax
0x18001248d  jz      short loc_1800124C0
0x18001248f  mov     qword ptr [rsp+88h+dwCreationDisposition], rdi; dwNumberOfBytesToMap
0x180012494  xor     r9d, r9d; dwFileOffsetLow
0x180012497  xor     r8d, r8d; dwFileOffsetHigh
0x18001249a  lea     edx, [r13+4]; dwDesiredAccess
0x18001249e  mov     rcx, rax; hFileMappingObject
0x1800124a1  call    cs:__imp_MapViewOfFile
0x1800124a7  mov     rdi, rax
0x1800124aa  mov     [rsp+88h+arg_8], rax
0x1800124b2  test    rax, rax
0x1800124b5  jz      short loc_1800124C0
0x1800124b7  mov     r14, rax
0x1800124ba  mov     r13d, 1
0x1800124c0  cmp     r13d, 1
0x1800124c4  jnz     loc_180012552
0x1800124ca  mov     eax, 5A4Dh
0x1800124cf  cmp     [r14], ax
0x1800124d3  jnz     short loc_18001252C
0x1800124d5  movsxd  rax, dword ptr [r14+3Ch]
0x1800124d9  cmp     dword ptr [rax+r14], 4550h
0x1800124e1  jnz     short loc_18001252C
0x1800124e3  movzx   ecx, word ptr [rax+r14+4]
0x1800124e9  sub     ecx, 14Ch
0x1800124ef  jz      short loc_180012526
0x1800124f1  sub     ecx, 78h ; 'x'
0x1800124f4  jz      short loc_18001251F
0x1800124f6  sub     ecx, 3Ch ; '<'
0x1800124f9  jz      short loc_180012518
0x1800124fb  sub     ecx, 8464h
0x180012501  jz      short loc_180012511
0x180012503  cmp     ecx, 2400h
0x180012509  jnz     short loc_18001252C
0x18001250b  lea     ebx, [r13+3]
0x18001250f  jmp     short loc_180012528
0x180012511  mov     ebx, 2
0x180012516  jmp     short loc_180012528
0x180012518  mov     ebx, 1
0x18001251d  jmp     short loc_180012528
0x18001251f  mov     ebx, 3
0x180012524  jmp     short loc_180012528
0x180012526  xor     ebx, ebx
0x180012528  mov     [rsp+88h+var_48], ebx
0x18001252c  jmp     short loc_180012552
0x18001252e  mov     r12, [rsp+88h+arg_0]
0x180012536  mov     ebx, [rsp+88h+var_48]
0x18001253a  mov     rdi, [rsp+88h+arg_8]
0x180012542  mov     r15, [rsp+88h+arg_10]
0x18001254a  mov     rsi, [rsp+88h+arg_18]
0x180012552  test    r12, r12
0x180012555  jz      short loc_180012581
0x180012557  test    rdi, rdi
0x18001255a  jz      short loc_180012565
0x18001255c  mov     rcx, rdi; lpBaseAddress
0x18001255f  call    cs:__imp_UnmapViewOfFile
0x180012565  test    rsi, rsi
0x180012568  jz      short loc_180012573
0x18001256a  mov     rcx, rsi; hObject
0x18001256d  call    cs:__imp_CloseHandle
0x180012573  test    r15, r15
0x180012576  jz      short loc_180012581
0x180012578  mov     rcx, r15; hObject
0x18001257b  call    cs:__imp_CloseHandle
0x180012581  mov     eax, ebx
0x180012583  add     rsp, 50h
0x180012587  pop     r15
0x180012589  pop     r14
0x18001258b  pop     r13
0x18001258d  pop     r12
0x18001258f  pop     rdi
0x180012590  pop     rsi
0x180012591  pop     rbx
0x180012592  retn
```
