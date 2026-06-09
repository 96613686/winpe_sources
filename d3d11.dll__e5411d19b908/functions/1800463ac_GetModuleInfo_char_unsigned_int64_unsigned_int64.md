# GetModuleInfo(char *,unsigned __int64 *,unsigned __int64 *)

- ea: `0x1800463ac`
- end: `0x18004649e`
- name: `?GetModuleInfo@@YA_NPEADPEA_K1@Z`
- size: `242`
- prototype: `bool __fastcall(char *, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800462b0`

## callees

- `0x1800463ac`
- `0x180046878`
- `0x1800a9d20`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x1800463e2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x1800463e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004644b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004644b`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18004643d`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18004643d`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x180046424`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x180046424`

## pseudocode

```c
char __fastcall GetModuleInfo(char *a1, unsigned __int64 *a2, unsigned __int64 *a3)
{
  DWORD ModuleFileNameA; // ebp
  HANDLE FileA; // rax
  void *v8; // rdi
  unsigned __int64 v9; // rcx
  bool v10; // cf
  CHAR Filename[272]; // [rsp+40h] [rbp-148h] BYREF

  ModuleFileNameA = GetModuleFileNameA(0, Filename, 0x104u);
  if ( ModuleFileNameA )
  {
    Filename[260] = 0;
    FileA = CreateFileA(Filename, 0x80000000, 7u, 0, 3u, 0x80u, 0);
    v8 = FileA;
    if ( FileA != (HANDLE)-1LL )
    {
      if ( a3 )
        *a3 = GetFileSize(FileA, 0);
      CloseHandle(v8);
      if ( !a2 )
        return 1;
      v9 = ModuleFileNameA + 1;
      if ( !a1 )
      {
        *a2 = v9;
        return 1;
      }
      v10 = *a2 < v9;
      *a2 = v9;
      if ( !v10 )
      {
        StringCchCopyA(a1, (unsigned int)v9, Filename);
        return 1;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800463ac  push    rbx
0x1800463ae  push    rbp
0x1800463af  push    rsi
0x1800463b0  push    rdi
0x1800463b1  push    r14
0x1800463b3  sub     rsp, 160h
0x1800463ba  mov     rax, cs:__security_cookie
0x1800463c1  xor     rax, rsp
0x1800463c4  mov     [rsp+188h+var_38], rax
0x1800463cc  mov     r14, r8
0x1800463cf  mov     rbx, rdx
0x1800463d2  mov     rsi, rcx
0x1800463d5  lea     rdx, [rsp+188h+Filename]; lpFilename
0x1800463da  mov     r8d, 104h; nSize
0x1800463e0  xor     ecx, ecx; hModule
0x1800463e2  call    cs:__imp_GetModuleFileNameA
0x1800463e8  mov     ebp, eax
0x1800463ea  test    eax, eax
0x1800463ec  jz      loc_180046495
0x1800463f2  xor     r9d, r9d; lpSecurityAttributes
0x1800463f5  mov     [rsp+188h+hTemplateFile], 0; hTemplateFile
0x1800463fe  mov     [rsp+188h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180046406  lea     rcx, [rsp+188h+Filename]; lpFileName
0x18004640b  mov     edx, 80000000h; dwDesiredAccess
0x180046410  mov     [rsp+188h+var_44], 0
0x180046418  mov     [rsp+188h+dwCreationDisposition], 3; dwCreationDisposition
0x180046420  lea     r8d, [r9+7]; dwShareMode
0x180046424  call    cs:__imp_CreateFileA
0x18004642a  mov     rdi, rax
0x18004642d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180046431  jz      short loc_180046495
0x180046433  test    r14, r14
0x180046436  jz      short loc_180046448
0x180046438  xor     edx, edx; lpFileSizeHigh
0x18004643a  mov     rcx, rax; hFile
0x18004643d  call    cs:__imp_GetFileSize
0x180046443  mov     ecx, eax
0x180046445  mov     [r14], rcx
0x180046448  mov     rcx, rdi; hObject
0x18004644b  call    cs:__imp_CloseHandle
0x180046451  test    rbx, rbx
0x180046454  jz      short loc_180046475
0x180046456  lea     ecx, [rbp+1]
0x180046459  test    rsi, rsi
0x18004645c  jz      short loc_180046499
0x18004645e  cmp     [rbx], rcx
0x180046461  mov     [rbx], rcx
0x180046464  jb      short loc_180046495
0x180046466  mov     edx, ecx; unsigned __int64
0x180046468  lea     r8, [rsp+188h+Filename]; char *
0x18004646d  mov     rcx, rsi; char *
0x180046470  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180046475  mov     al, 1
0x180046477  mov     rcx, [rsp+188h+var_38]
0x18004647f  xor     rcx, rsp; StackCookie
0x180046482  call    __security_check_cookie
0x180046487  add     rsp, 160h
0x18004648e  pop     r14
0x180046490  pop     rdi
0x180046491  pop     rsi
0x180046492  pop     rbp
0x180046493  pop     rbx
0x180046494  retn
0x180046495  xor     al, al
0x180046497  jmp     short loc_180046477
0x180046499  mov     [rbx], rcx
0x18004649c  jmp     short loc_180046475
```
