# ApplyPatchToFileExA

- ea: `0x180003060`
- end: `0x1800031ab`
- name: `ApplyPatchToFileExA`
- size: `331`
- prototype: `BOOL __stdcall(LPCSTR PatchFileName, LPCSTR OldFileName, LPCSTR NewFileName, ULONG ApplyOptionFlags, PPATCH_PROGRESS_CALLBACK ProgressCallback, PVOID CallbackContext)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callers

- `0x180001ce0`
- `0x180004850`

## callees

- `0x180002720`
- `0x180003060`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800030b3`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800030e6`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x180003127`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800030b3`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800030e6`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x180003127`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x18000317b`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x18000317b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000316a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003184`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003192`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000316a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003184`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003192`

## pseudocode

```c
BOOL __stdcall ApplyPatchToFileExA(
        LPCSTR PatchFileName,
        LPCSTR OldFileName,
        LPCSTR NewFileName,
        ULONG ApplyOptionFlags,
        PPATCH_PROGRESS_CALLBACK ProgressCallback,
        PVOID CallbackContext)
{
  __int64 FileA; // rbx
  BOOL v11; // ebp
  HANDLE v12; // r14
  __int64 v13; // rdi

  FileA = -1;
  if ( OldFileName )
  {
    FileA = (__int64)CreateFileA(OldFileName, 0x80000000, 3u, 0, 3u, 0x8000000u, 0);
    if ( FileA == -1 )
      return 0;
  }
  v11 = 0;
  v12 = CreateFileA(PatchFileName, 0x80000000, 3u, 0, 3u, 0x8000000u, 0);
  if ( v12 != (HANDLE)-1LL )
  {
    v13 = -1;
    if ( (ApplyOptionFlags & 4) != 0
      || (v13 = (__int64)CreateFileA(NewFileName, 0xC0000000, 1u, 0, 2u, 0x80u, 0), v13 != -1) )
    {
      v11 = ApplyPatchToFileByHandlesEx(
              v12,
              (HANDLE)FileA,
              (HANDLE)v13,
              ApplyOptionFlags,
              ProgressCallback,
              CallbackContext);
      if ( v13 != -1 )
        CloseHandle((HANDLE)v13);
      if ( !v11 && (ApplyOptionFlags & 4) == 0 )
        DeleteFileA(NewFileName);
    }
    CloseHandle(v12);
  }
  if ( FileA != -1 )
    CloseHandle((HANDLE)FileA);
  return v11;
}

```

## disassembly

```asm
0x180003060  push    rbx
0x180003062  push    rbp
0x180003063  push    rsi
0x180003064  push    rdi
0x180003065  push    r12
0x180003067  push    r13
0x180003069  push    r14
0x18000306b  push    r15
0x18000306d  sub     rsp, 48h
0x180003071  or      r13, 0FFFFFFFFFFFFFFFFh
0x180003075  mov     r12d, r9d
0x180003078  mov     r15, r8
0x18000307b  mov     rax, rdx
0x18000307e  mov     rdi, rcx
0x180003081  mov     rbx, r13
0x180003084  mov     r14d, 8000000h
0x18000308a  lea     esi, [r13+4]
0x18000308e  test    rdx, rdx
0x180003091  jz      short loc_1800030C8
0x180003093  mov     [rsp+88h+hTemplateFile], 0; hTemplateFile
0x18000309c  xor     r9d, r9d; lpSecurityAttributes
0x18000309f  mov     [rsp+88h+dwFlagsAndAttributes], r14d; dwFlagsAndAttributes
0x1800030a4  mov     r8d, esi; dwShareMode
0x1800030a7  mov     edx, 80000000h; dwDesiredAccess
0x1800030ac  mov     [rsp+88h+dwCreationDisposition], esi; dwCreationDisposition
0x1800030b0  mov     rcx, rax; lpFileName
0x1800030b3  call    cs:__imp_CreateFileA
0x1800030b9  mov     rbx, rax
0x1800030bc  cmp     rax, r13
0x1800030bf  jnz     short loc_1800030C8
0x1800030c1  xor     eax, eax
0x1800030c3  jmp     loc_18000319A
0x1800030c8  xor     ebp, ebp
0x1800030ca  xor     r9d, r9d; lpSecurityAttributes
0x1800030cd  mov     [rsp+88h+hTemplateFile], rbp; hTemplateFile
0x1800030d2  mov     r8d, esi; dwShareMode
0x1800030d5  mov     [rsp+88h+dwFlagsAndAttributes], r14d; dwFlagsAndAttributes
0x1800030da  mov     edx, 80000000h; dwDesiredAccess
0x1800030df  mov     rcx, rdi; lpFileName
0x1800030e2  mov     [rsp+88h+dwCreationDisposition], esi; dwCreationDisposition
0x1800030e6  call    cs:__imp_CreateFileA
0x1800030ec  mov     r14, rax
0x1800030ef  cmp     rax, r13
0x1800030f2  jz      loc_18000318A
0x1800030f8  mov     esi, r12d
0x1800030fb  mov     rdi, r13
0x1800030fe  and     esi, 4
0x180003101  jnz     short loc_180003135
0x180003103  mov     [rsp+88h+hTemplateFile], rbp; hTemplateFile
0x180003108  lea     r8d, [rbp+1]; dwShareMode
0x18000310c  mov     [rsp+88h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180003114  xor     r9d, r9d; lpSecurityAttributes
0x180003117  mov     edx, 0C0000000h; dwDesiredAccess
0x18000311c  mov     [rsp+88h+dwCreationDisposition], 2; dwCreationDisposition
0x180003124  mov     rcx, r15; lpFileName
0x180003127  call    cs:__imp_CreateFileA
0x18000312d  mov     rdi, rax
0x180003130  cmp     rax, r13
0x180003133  jz      short loc_180003181
0x180003135  mov     rcx, [rsp+88h+CallbackContext]
0x18000313d  mov     r9d, r12d; ApplyOptionFlags
0x180003140  mov     qword ptr [rsp+88h+dwFlagsAndAttributes], rcx; CallbackContext
0x180003145  mov     r8, rdi; NewFileHandle
0x180003148  mov     rcx, [rsp+88h+ProgressCallback]
0x180003150  mov     rdx, rbx; OldFileHandle
0x180003153  mov     qword ptr [rsp+88h+dwCreationDisposition], rcx; ProgressCallback
0x180003158  mov     rcx, r14; PatchFileHandle
0x18000315b  call    ApplyPatchToFileByHandlesEx
0x180003160  mov     ebp, eax
0x180003162  cmp     rdi, r13
0x180003165  jz      short loc_180003170
0x180003167  mov     rcx, rdi; hObject
0x18000316a  call    cs:__imp_CloseHandle
0x180003170  test    ebp, ebp
0x180003172  jnz     short loc_180003181
0x180003174  test    esi, esi
0x180003176  jnz     short loc_180003181
0x180003178  mov     rcx, r15; lpFileName
0x18000317b  call    cs:__imp_DeleteFileA
0x180003181  mov     rcx, r14; hObject
0x180003184  call    cs:__imp_CloseHandle
0x18000318a  cmp     rbx, r13
0x18000318d  jz      short loc_180003198
0x18000318f  mov     rcx, rbx; hObject
0x180003192  call    cs:__imp_CloseHandle
0x180003198  mov     eax, ebp
0x18000319a  add     rsp, 48h
0x18000319e  pop     r15
0x1800031a0  pop     r14
0x1800031a2  pop     r13
0x1800031a4  pop     r12
0x1800031a6  pop     rdi
0x1800031a7  pop     rsi
0x1800031a8  pop     rbp
0x1800031a9  pop     rbx
0x1800031aa  retn
```
