# GetModuleInfo(char *,unsigned __int64 *,unsigned __int64 *)

- ea: `0x18001153c`
- end: `0x180011641`
- name: `?GetModuleInfo@@YA_NPEADPEA_K1@Z`
- size: `261`
- prototype: `bool __fastcall(char *, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180011648`

## callees

- `0x18000b410`
- `0x18000de10`
- `0x18001153c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x180011572`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x180011572`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800115df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800115df`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800115b8`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800115b8`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800115d1`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800115d1`

## pseudocode

```c
char __fastcall GetModuleInfo(char *a1, unsigned __int64 *a2, unsigned __int64 *a3)
{
  DWORD ModuleFileNameA; // r14d
  HANDLE FileA; // rax
  void *v9; // rsi
  unsigned __int64 v10; // rcx
  bool v11; // cf
  CHAR Filename[272]; // [rsp+40h] [rbp-148h] BYREF

  ModuleFileNameA = GetModuleFileNameA(0, Filename, 0x104u);
  if ( !ModuleFileNameA )
    return 0;
  Filename[260] = 0;
  FileA = CreateFileA(Filename, 0x80000000, 7u, 0, 3u, 0x80u, 0);
  v9 = FileA;
  if ( FileA == (HANDLE)-1LL )
  {
    if ( a3 )
      *a3 = 0;
  }
  else
  {
    if ( a3 )
      *a3 = GetFileSize(FileA, 0);
    CloseHandle(v9);
  }
  if ( a2 )
  {
    v10 = ModuleFileNameA + 1;
    if ( a1 )
    {
      v11 = *a2 < v10;
      *a2 = v10;
      if ( v11 )
        return 0;
      StringCchCopyA(a1, (unsigned int)v10, Filename);
    }
    else
    {
      *a2 = v10;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18001153c  push    rbx
0x18001153e  push    rbp
0x18001153f  push    rsi
0x180011540  push    rdi
0x180011541  push    r14
0x180011543  sub     rsp, 160h
0x18001154a  mov     rax, cs:__security_cookie
0x180011551  xor     rax, rsp
0x180011554  mov     [rsp+188h+var_38], rax
0x18001155c  mov     rdi, r8
0x18001155f  mov     rbx, rdx
0x180011562  mov     rbp, rcx
0x180011565  lea     rdx, [rsp+188h+Filename]; lpFilename
0x18001156a  mov     r8d, 104h; nSize
0x180011570  xor     ecx, ecx; hModule
0x180011572  call    cs:__imp_GetModuleFileNameA
0x180011578  mov     r14d, eax
0x18001157b  test    eax, eax
0x18001157d  jnz     short loc_180011586
0x18001157f  xor     al, al
0x180011581  jmp     loc_180011623
0x180011586  xor     r9d, r9d; lpSecurityAttributes
0x180011589  mov     [rsp+188h+hTemplateFile], 0; hTemplateFile
0x180011592  mov     [rsp+188h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18001159a  lea     rcx, [rsp+188h+Filename]; lpFileName
0x18001159f  mov     edx, 80000000h; dwDesiredAccess
0x1800115a4  mov     [rsp+188h+var_44], 0
0x1800115ac  mov     [rsp+188h+dwCreationDisposition], 3; dwCreationDisposition
0x1800115b4  lea     r8d, [r9+7]; dwShareMode
0x1800115b8  call    cs:__imp_CreateFileA
0x1800115be  mov     rsi, rax
0x1800115c1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800115c5  jz      short loc_1800115E7
0x1800115c7  test    rdi, rdi
0x1800115ca  jz      short loc_1800115DC
0x1800115cc  xor     edx, edx; lpFileSizeHigh
0x1800115ce  mov     rcx, rax; hFile
0x1800115d1  call    cs:__imp_GetFileSize
0x1800115d7  mov     ecx, eax
0x1800115d9  mov     [rdi], rcx
0x1800115dc  mov     rcx, rsi; hObject
0x1800115df  call    cs:__imp_CloseHandle
0x1800115e5  jmp     short loc_1800115F3
0x1800115e7  test    rdi, rdi
0x1800115ea  jz      short loc_1800115F3
0x1800115ec  mov     qword ptr [rdi], 0
0x1800115f3  test    rbx, rbx
0x1800115f6  jz      short loc_180011621
0x1800115f8  lea     ecx, [r14+1]
0x1800115fc  test    rbp, rbp
0x1800115ff  jz      short loc_18001161E
0x180011601  cmp     [rbx], rcx
0x180011604  mov     [rbx], rcx
0x180011607  jb      loc_18001157F
0x18001160d  mov     edx, ecx; unsigned __int64
0x18001160f  lea     r8, [rsp+188h+Filename]; char *
0x180011614  mov     rcx, rbp; char *
0x180011617  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18001161c  jmp     short loc_180011621
0x18001161e  mov     [rbx], rcx
0x180011621  mov     al, 1
0x180011623  mov     rcx, [rsp+188h+var_38]
0x18001162b  xor     rcx, rsp; StackCookie
0x18001162e  call    __security_check_cookie
0x180011633  add     rsp, 160h
0x18001163a  pop     r14
0x18001163c  pop     rdi
0x18001163d  pop     rsi
0x18001163e  pop     rbp
0x18001163f  pop     rbx
0x180011640  retn
```
