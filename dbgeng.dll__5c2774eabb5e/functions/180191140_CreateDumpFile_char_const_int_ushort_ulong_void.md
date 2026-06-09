# CreateDumpFile(char const *,int,ushort *,ulong,void * *)

- ea: `0x180191140`
- end: `0x1801912f2`
- name: `?CreateDumpFile@@YAJPEBDHPEAGKPEAPEAX@Z`
- size: `434`
- prototype: `int(const char *, int, unsigned __int16 *, unsigned int, void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x1801922c8`
- `0x180192dd0`

## callees

- `0x180073230`
- `0x180191140`
- `0x1801939e8`
- `0x180193e70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801912a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801912a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1801911bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1801911f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1801911bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1801911f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801912c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801912c6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18019126f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18019126f`

## pseudocode

```c
__int64 __fastcall CreateDumpFile(const char *a1, int a2, unsigned __int16 *a3, unsigned int a4, void **a5)
{
  unsigned int v5; // ebx
  __int64 FileW; // rdi
  unsigned __int16 *TemporaryPath; // r12
  unsigned int i; // esi
  int v11; // eax
  DWORD v12; // r8d
  signed int LastError; // eax

  v5 = 0;
  if ( a1 && a3 && a4 && a5 )
  {
    FileW = -1;
    GetFileName(a1);
    TemporaryPath = GetTemporaryPath();
    for ( i = 0; i < 0xA; ++i )
    {
      if ( TemporaryPath && *TemporaryPath )
      {
        GetCurrentProcessId();
        v11 = PrintStringW(a3, a4, (wchar_t *)L"%s\\%08x%x_%hs");
      }
      else
      {
        GetCurrentProcessId();
        v11 = PrintStringW(a3, a4, (wchar_t *)L"%08x%x_%hs");
      }
      v5 = 0;
      if ( !v11 )
        return (unsigned int)-2147467259;
      v12 = 7;
      if ( (char *)hFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        v12 = dwShareMode;
      FileW = (__int64)CreateFileW(a3, 0xC0000000, v12, 0, 1u, a2 != 0 ? 67109120 : 128, 0);
      if ( FileW != -1 )
        goto LABEL_21;
      ++g_CabTmpSequence;
    }
    if ( i != 10 )
    {
LABEL_21:
      *a5 = (void *)FileW;
      return v5;
    }
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v5;
}

```

## disassembly

```asm
0x180191140  mov     [rsp+arg_8], edx
0x180191144  push    rbx
0x180191145  push    rbp
0x180191146  push    rsi
0x180191147  push    rdi
0x180191148  push    r12
0x18019114a  push    r13
0x18019114c  push    r14
0x18019114e  push    r15
0x180191150  sub     rsp, 48h
0x180191154  xor     ebx, ebx
0x180191156  mov     r15d, r9d
0x180191159  mov     rbp, r8
0x18019115c  test    rcx, rcx
0x18019115f  jz      loc_1801912D9
0x180191165  test    r8, r8
0x180191168  jz      loc_1801912D9
0x18019116e  test    r9d, r9d
0x180191171  jz      loc_1801912D9
0x180191177  mov     r14, [rsp+88h+arg_20]
0x18019117f  test    r14, r14
0x180191182  jz      loc_1801912D9
0x180191188  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18019118c  call    ?GetFileName@@YAPEBDPEBD@Z; GetFileName(char const *)
0x180191191  mov     r13, rax
0x180191194  call    ?GetTemporaryPath@@YAPEAGXZ; GetTemporaryPath(void)
0x180191199  mov     r12, rax
0x18019119c  mov     esi, ebx
0x18019119e  mov     eax, cs:?g_CabTmpSequence@@3KA; ulong g_CabTmpSequence
0x1801911a4  cmp     esi, 0Ah
0x1801911a7  jnb     loc_1801912A0
0x1801911ad  test    r12, r12
0x1801911b0  jz      short loc_1801911EF
0x1801911b2  cmp     [r12], bx
0x1801911b7  jz      short loc_1801911EF
0x1801911b9  lea     eax, [rax+rax*4]
0x1801911bc  lea     ebx, [rsi+rax*2]
0x1801911bf  call    cs:__imp_GetCurrentProcessId
0x1801911c6  nop     dword ptr [rax+rax+00h]
0x1801911cb  mov     [rsp+88h+hTemplateFile], r13
0x1801911d0  lea     r8, aS08xXHs; "%s\\%08x%x_%hs"
0x1801911d7  mov     [rsp+88h+dwFlagsAndAttributes], ebx
0x1801911db  mov     r9, r12
0x1801911de  mov     edx, r15d; BufferCount
0x1801911e1  mov     [rsp+88h+dwCreationDisposition], eax
0x1801911e5  mov     rcx, rbp; Buffer
0x1801911e8  call    PrintStringW
0x1801911ed  jmp     short loc_18019121F
0x1801911ef  lea     eax, [rax+rax*4]
0x1801911f2  lea     ebx, [rsi+rax*2]
0x1801911f5  call    cs:__imp_GetCurrentProcessId
0x1801911fc  nop     dword ptr [rax+rax+00h]
0x180191201  mov     qword ptr [rsp+88h+dwFlagsAndAttributes], r13
0x180191206  lea     r8, a08xXHs; "%08x%x_%hs"
0x18019120d  mov     r9d, eax
0x180191210  mov     [rsp+88h+dwCreationDisposition], ebx
0x180191214  mov     edx, r15d; BufferCount
0x180191217  mov     rcx, rbp; Buffer
0x18019121a  call    PrintStringW
0x18019121f  xor     ebx, ebx
0x180191221  test    eax, eax
0x180191223  jz      short loc_180191299
0x180191225  mov     eax, [rsp+88h+arg_8]
0x18019122c  lea     r8d, [rbx+7]
0x180191230  neg     eax
0x180191232  mov     [rsp+88h+hTemplateFile], rbx; hTemplateFile
0x180191237  mov     rax, cs:hFile
0x18019123e  mov     edx, 0C0000000h; dwDesiredAccess
0x180191243  sbb     ecx, ecx
0x180191245  and     ecx, 4000080h
0x18019124b  sub     ecx, 0FFFFFF80h
0x18019124e  mov     [rsp+88h+dwFlagsAndAttributes], ecx; dwFlagsAndAttributes
0x180191252  dec     rax
0x180191255  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180191259  mov     [rsp+88h+dwCreationDisposition], 1; dwCreationDisposition
0x180191261  mov     rcx, rbp; lpFileName
0x180191264  cmovbe  r8d, cs:dwShareMode; dwShareMode
0x18019126c  xor     r9d, r9d; lpSecurityAttributes
0x18019126f  call    cs:__imp_CreateFileW
0x180191276  nop     dword ptr [rax+rax+00h]
0x18019127b  mov     rdi, rax
0x18019127e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180191282  jnz     short loc_1801912D4
0x180191284  mov     eax, cs:?g_CabTmpSequence@@3KA; ulong g_CabTmpSequence
0x18019128a  inc     eax
0x18019128c  mov     cs:?g_CabTmpSequence@@3KA, eax; ulong g_CabTmpSequence
0x180191292  inc     esi
0x180191294  jmp     loc_1801911A4
0x180191299  mov     ebx, 80004005h
0x18019129e  jmp     short loc_1801912DE
0x1801912a0  jnz     short loc_1801912D4
0x1801912a2  call    cs:__imp_GetLastError
0x1801912a9  nop     dword ptr [rax+rax+00h]
0x1801912ae  mov     ebx, eax
0x1801912b0  test    eax, eax
0x1801912b2  jle     short loc_1801912BD
0x1801912b4  movzx   ebx, ax
0x1801912b7  or      ebx, 80070000h
0x1801912bd  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1801912c1  jz      short loc_1801912DE
0x1801912c3  mov     rcx, rdi; hObject
0x1801912c6  call    cs:__imp_CloseHandle
0x1801912cd  nop     dword ptr [rax+rax+00h]
0x1801912d2  jmp     short loc_1801912DE
0x1801912d4  mov     [r14], rdi
0x1801912d7  jmp     short loc_1801912DE
0x1801912d9  mov     ebx, 80070057h
0x1801912de  mov     eax, ebx
0x1801912e0  add     rsp, 48h
0x1801912e4  pop     r15
0x1801912e6  pop     r14
0x1801912e8  pop     r13
0x1801912ea  pop     r12
0x1801912ec  pop     rdi
0x1801912ed  pop     rsi
0x1801912ee  pop     rbp
0x1801912ef  pop     rbx
0x1801912f0  retn
```
