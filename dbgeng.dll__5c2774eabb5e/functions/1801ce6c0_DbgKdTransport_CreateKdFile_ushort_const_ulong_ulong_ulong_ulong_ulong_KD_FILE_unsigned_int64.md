# DbgKdTransport::CreateKdFile(ushort const *,ulong,ulong,ulong,ulong,ulong,KD_FILE * *,unsigned __int64 *)

- ea: `0x1801ce6c0`
- end: `0x1801ce940`
- name: `?CreateKdFile@DbgKdTransport@@QEAAJPEBGKKKKKPEAPEAUKD_FILE@@PEA_K@Z`
- size: `640`
- prototype: `__int64 __usercall@<rax>(DbgKdTransport *__hidden this@<rcx>, const unsigned __int16 *Src@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, DWORD dwShareMode, unsigned int, LONG DistanceToMoveHigh, struct KD_FILE **, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1801cecd4`

## callees

- `0x1800727b8`
- `0x1800f13ec`
- `0x1800f16fc`
- `0x1801ce6c0`
- `0x1801ce98c`
- `0x1804da880`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1801ce6f9`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1801ce6f9`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1801ce73f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1801ce73f`
- `api-ms-win-crt-string-l1-1-0!_wcslwr` at `0x1801ce722`
- `api-ms-win-crt-string-l1-1-0!_wcslwr` at `0x1801ce722`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ce828`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ce900`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ce828`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ce900`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801ce83c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801ce83c`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1801ce815`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1801ce815`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801ce7df`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801ce7df`

## pseudocode

```c
__int64 __fastcall DbgKdTransport::CreateKdFile(
        DbgKdTransport *this,
        const unsigned __int16 *Src,
        int a3,
        DWORD a4,
        DWORD dwShareMode,
        unsigned int a6,
        LONG DistanceToMoveHigh,
        struct KD_FILE **a8,
        unsigned __int64 *a9)
{
  __int64 v9; // rax
  size_t v14; // rdi
  wchar_t *v15; // rax
  wchar_t *v16; // rbx
  struct KD_FILE_ASSOC *KdFileAssoc; // r14
  _QWORD *v18; // rdi
  DWORD v19; // edx
  unsigned int v20; // ebx
  DWORD dwCreationDisposition; // eax
  char *FileW; // rax
  DWORD v23; // eax
  __int64 v24; // rbx
  __int64 result; // rax
  __int64 v26; // rcx
  unsigned __int64 *v27; // rbx
  _QWORD *v28; // rax
  __int64 v29; // rdx
  DWORD LastError; // ecx

  v9 = -1;
  do
    ++v9;
  while ( Src[v9] );
  v14 = (unsigned int)(2 * v9 + 2);
  v15 = (wchar_t *)malloc(v14);
  v16 = v15;
  if ( !v15 )
    return 3221225495LL;
  memmove(v15, Src, (unsigned int)v14);
  _wcslwr(v16);
  KdFileAssoc = DbgKdTransport::FindKdFileAssoc(this, v16);
  free(v16);
  if ( !KdFileAssoc )
    return 3221225487LL;
  v18 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v18 )
    return 3221225495LL;
  v19 = (a3 << 31) | 0x40000000;
  if ( (a3 & 2) == 0 )
    v19 = a3 << 31;
  switch ( a6 )
  {
    case 1u:
      dwCreationDisposition = 3;
      break;
    case 2u:
      dwCreationDisposition = 1;
      break;
    case 3u:
      dwCreationDisposition = 4;
      break;
    case 5u:
      dwCreationDisposition = 2;
      break;
    default:
      v20 = -1073741811;
LABEL_21:
      operator delete(v18, (const struct std::nothrow_t *)0x20);
      return v20;
  }
  FileW = (char *)CreateFileW(*((LPCWSTR *)KdFileAssoc + 3), v19, dwShareMode, 0, dwCreationDisposition, a4, 0);
  v18[2] = FileW;
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    operator delete(v18, (const struct std::nothrow_t *)0x20);
    LastError = GetLastError();
    if ( LastError != 2 )
    {
      result = 3221225506LL;
      if ( LastError != 5 )
        return 3221225473LL;
      return result;
    }
    return 3221225487LL;
  }
  DistanceToMoveHigh = 0;
  v23 = SetFilePointer((HANDLE)v18[2], 0, &DistanceToMoveHigh, 2u);
  v24 = v23;
  if ( v23 == -1 && GetLastError() )
  {
    CloseHandle((HANDLE)v18[2]);
    v20 = -1073741823;
    goto LABEL_21;
  }
  v26 = v24 | ((__int64)DistanceToMoveHigh << 32);
  v27 = a9;
  *a9 = v26;
  dprintf(L"KDFILES: Replacing '%ws' with '%s'.", Src, *((_QWORD *)KdFileAssoc + 3));
  if ( *v27 )
    dprintf(L"  File size %dKB.", (*v27 + 1023) >> 10);
  dprintf(L"\n");
  v28 = (_QWORD *)((char *)this + 616);
  v18[3] = 1816552523;
  v29 = *((_QWORD *)this + 77);
  if ( *(DbgKdTransport **)(v29 + 8) != (DbgKdTransport *)((char *)this + 616) )
    __fastfail(3u);
  v18[1] = v28;
  *v18 = v29;
  *(_QWORD *)(v29 + 8) = v18;
  *v28 = v18;
  *a8 = (struct KD_FILE *)v18;
  return 0;
}

```

## disassembly

```asm
0x1801ce6c0  push    rbx
0x1801ce6c2  push    rbp
0x1801ce6c3  push    rsi
0x1801ce6c4  push    rdi
0x1801ce6c5  push    r12
0x1801ce6c7  push    r13
0x1801ce6c9  push    r14
0x1801ce6cb  push    r15
0x1801ce6cd  sub     rsp, 48h
0x1801ce6d1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801ce6d5  mov     r12d, r9d
0x1801ce6d8  xor     r13d, r13d
0x1801ce6db  mov     esi, r8d
0x1801ce6de  mov     rbp, rdx
0x1801ce6e1  mov     r15, rcx
0x1801ce6e4  inc     rax
0x1801ce6e7  cmp     [rdx+rax*2], r13w
0x1801ce6ec  jnz     short loc_1801CE6E4
0x1801ce6ee  lea     eax, ds:2[rax*2]
0x1801ce6f5  mov     ecx, eax; Size
0x1801ce6f7  mov     edi, eax
0x1801ce6f9  call    cs:__imp_malloc
0x1801ce700  nop     dword ptr [rax+rax+00h]
0x1801ce705  mov     rbx, rax
0x1801ce708  test    rax, rax
0x1801ce70b  jz      loc_1801CE929
0x1801ce711  mov     r8d, edi; Size
0x1801ce714  mov     rdx, rbp; Src
0x1801ce717  mov     rcx, rax; void *
0x1801ce71a  call    memmove
0x1801ce71f  mov     rcx, rbx; String
0x1801ce722  call    cs:__imp__wcslwr
0x1801ce729  nop     dword ptr [rax+rax+00h]
0x1801ce72e  mov     rdx, rbx; unsigned __int16 *
0x1801ce731  mov     rcx, r15; this
0x1801ce734  call    ?FindKdFileAssoc@DbgKdTransport@@AEAAPEAUKD_FILE_ASSOC@@PEBG@Z; DbgKdTransport::FindKdFileAssoc(ushort const *)
0x1801ce739  mov     rcx, rbx; Block
0x1801ce73c  mov     r14, rax
0x1801ce73f  call    cs:__imp_free
0x1801ce746  nop     dword ptr [rax+rax+00h]
0x1801ce74b  test    r14, r14
0x1801ce74e  jz      loc_1801CE922
0x1801ce754  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1801ce75b  mov     ecx, 20h ; ' '; unsigned __int64
0x1801ce760  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1801ce765  mov     rdi, rax
0x1801ce768  test    rax, rax
0x1801ce76b  jz      loc_1801CE929
0x1801ce771  mov     eax, [rsp+88h+arg_28]
0x1801ce778  mov     ecx, esi
0x1801ce77a  shl     ecx, 1Fh
0x1801ce77d  mov     ebx, 2
0x1801ce782  mov     edx, ecx
0x1801ce784  bts     edx, 1Eh
0x1801ce788  test    bl, sil
0x1801ce78b  lea     esi, [rbx+1]
0x1801ce78e  cmovz   edx, ecx; dwDesiredAccess
0x1801ce791  sub     eax, 1
0x1801ce794  jz      short loc_1801CE7C0
0x1801ce796  sub     eax, 1
0x1801ce799  jz      short loc_1801CE7B9
0x1801ce79b  sub     eax, 1
0x1801ce79e  jz      short loc_1801CE7B2
0x1801ce7a0  cmp     eax, ebx
0x1801ce7a2  jz      short loc_1801CE7AE
0x1801ce7a4  mov     ebx, 0C000000Dh
0x1801ce7a9  jmp     loc_1801CE84D
0x1801ce7ae  mov     eax, ebx
0x1801ce7b0  jmp     short loc_1801CE7C2
0x1801ce7b2  mov     eax, 4
0x1801ce7b7  jmp     short loc_1801CE7C2
0x1801ce7b9  mov     eax, 1
0x1801ce7be  jmp     short loc_1801CE7C2
0x1801ce7c0  mov     eax, esi
0x1801ce7c2  mov     r8d, [rsp+88h+dwShareMode]; dwShareMode
0x1801ce7ca  xor     r9d, r9d; lpSecurityAttributes
0x1801ce7cd  mov     rcx, [r14+18h]; lpFileName
0x1801ce7d1  mov     [rsp+88h+hTemplateFile], r13; hTemplateFile
0x1801ce7d6  mov     [rsp+88h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x1801ce7db  mov     [rsp+88h+dwCreationDisposition], eax; dwCreationDisposition
0x1801ce7df  call    cs:__imp_CreateFileW
0x1801ce7e6  nop     dword ptr [rax+rax+00h]
0x1801ce7eb  mov     [rdi+10h], rax
0x1801ce7ef  dec     rax
0x1801ce7f2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801ce7f6  ja      loc_1801CE8F3
0x1801ce7fc  mov     [rsp+88h+DistanceToMoveHigh], r13d
0x1801ce804  lea     r8, [rsp+88h+DistanceToMoveHigh]; lpDistanceToMoveHigh
0x1801ce80c  mov     rcx, [rdi+10h]; hFile
0x1801ce810  mov     r9d, ebx; dwMoveMethod
0x1801ce813  xor     edx, edx; lDistanceToMove
0x1801ce815  call    cs:__imp_SetFilePointer
0x1801ce81c  nop     dword ptr [rax+rax+00h]
0x1801ce821  mov     ebx, eax
0x1801ce823  cmp     eax, 0FFFFFFFFh
0x1801ce826  jnz     short loc_1801CE861
0x1801ce828  call    cs:__imp_GetLastError
0x1801ce82f  nop     dword ptr [rax+rax+00h]
0x1801ce834  test    eax, eax
0x1801ce836  jz      short loc_1801CE861
0x1801ce838  mov     rcx, [rdi+10h]; hObject
0x1801ce83c  call    cs:__imp_CloseHandle
0x1801ce843  nop     dword ptr [rax+rax+00h]
0x1801ce848  mov     ebx, 0C0000001h
0x1801ce84d  mov     edx, 20h ; ' '; struct std::nothrow_t *
0x1801ce852  mov     rcx, rdi; void *
0x1801ce855  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801ce85a  mov     eax, ebx
0x1801ce85c  jmp     loc_1801CE92E
0x1801ce861  movsxd  rcx, [rsp+88h+DistanceToMoveHigh]
0x1801ce869  mov     rdx, rbp
0x1801ce86c  shl     rcx, 20h
0x1801ce870  or      rcx, rbx
0x1801ce873  mov     rbx, [rsp+88h+arg_40]
0x1801ce87b  mov     [rbx], rcx
0x1801ce87e  lea     rcx, aKdfilesReplaci; "KDFILES: Replacing '%ws' with '%s'."
0x1801ce885  mov     r8, [r14+18h]
0x1801ce889  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1801ce88e  mov     rdx, [rbx]
0x1801ce891  test    rdx, rdx
0x1801ce894  jz      short loc_1801CE8AD
0x1801ce896  add     rdx, 3FFh
0x1801ce89d  lea     rcx, aFileSizeDkb; "  File size %dKB."
0x1801ce8a4  shr     rdx, 0Ah
0x1801ce8a8  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1801ce8ad  lea     rcx, asc_1805BAA38; "\n"
0x1801ce8b4  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1801ce8b9  lea     rax, [r15+268h]
0x1801ce8c0  mov     qword ptr [rdi+18h], 6C46644Bh
0x1801ce8c8  mov     rdx, [rax]
0x1801ce8cb  cmp     [rdx+8], rax
0x1801ce8cf  jz      short loc_1801CE8D6
0x1801ce8d1  mov     rcx, rsi
0x1801ce8d4  int     29h; Win8: RtlFailFast(ecx)
0x1801ce8d6  mov     [rdi+8], rax
0x1801ce8da  mov     [rdi], rdx
0x1801ce8dd  mov     [rdx+8], rdi
0x1801ce8e1  mov     [rax], rdi
0x1801ce8e4  mov     rax, [rsp+88h+arg_38]
0x1801ce8ec  mov     [rax], rdi
0x1801ce8ef  xor     eax, eax
0x1801ce8f1  jmp     short loc_1801CE92E
0x1801ce8f3  mov     edx, 20h ; ' '; struct std::nothrow_t *
0x1801ce8f8  mov     rcx, rdi; void *
0x1801ce8fb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801ce900  call    cs:__imp_GetLastError
0x1801ce907  nop     dword ptr [rax+rax+00h]
0x1801ce90c  mov     ecx, eax
0x1801ce90e  cmp     eax, ebx
0x1801ce910  jz      short loc_1801CE922
0x1801ce912  mov     eax, 0C0000022h
0x1801ce917  cmp     ecx, 5
0x1801ce91a  lea     ebx, [rax-21h]
0x1801ce91d  cmovnz  eax, ebx
0x1801ce920  jmp     short loc_1801CE92E
0x1801ce922  mov     eax, 0C000000Fh
0x1801ce927  jmp     short loc_1801CE92E
0x1801ce929  mov     eax, 0C0000017h
0x1801ce92e  add     rsp, 48h
0x1801ce932  pop     r15
0x1801ce934  pop     r14
0x1801ce936  pop     r13
0x1801ce938  pop     r12
0x1801ce93a  pop     rdi
0x1801ce93b  pop     rsi
0x1801ce93c  pop     rbp
0x1801ce93d  pop     rbx
0x1801ce93e  retn
```
