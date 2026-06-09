# _anonymous_namespace_::Remover::Delete

- ea: `0x180018594`
- end: `0x18001865b`
- name: `_anonymous_namespace_::Remover::Delete`
- size: `199`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x180018900`

## callees

- `0x180018594`
- `0x180018834`
- `0x180018860`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800185c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800185f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018624`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800185c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800185f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018624`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800185b8`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800185ea`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800185b8`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800185ea`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800185dd`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18001861a`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800185dd`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18001861a`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::Remover::Delete(
        unsigned int (__fastcall **a1)(const WCHAR *),
        const WCHAR *a2,
        Common *a3)
{
  unsigned int v4; // ebx
  int v5; // edx
  DWORD LastError; // edi
  const struct _WIN32_FIND_DATAW *v9; // rdx

  v4 = 0;
  v5 = *(_DWORD *)a3;
  if ( (*(_DWORD *)a3 & 0x10) != 0 )
  {
    LastError = 0;
    if ( !RemoveDirectoryW(a2) )
    {
      LastError = GetLastError();
      if ( LastError == 5 )
      {
        v9 = (const struct _WIN32_FIND_DATAW *)*(unsigned int *)a3;
        if ( ((unsigned __int8)v9 & 1) != 0 )
        {
          if ( SetFileAttributesW(a2, (unsigned int)v9 & 0xFFFFFFFE) && RemoveDirectoryW(a2) )
            LastError = 0;
          else
            LastError = GetLastError();
        }
      }
    }
    v4 = Common::IsDirectoryReparsePointOpaque(a3, v9) + 1;
  }
  else if ( ((v5 & 1) == 0 || SetFileAttributesW(a2, v5 & 0xFFFFFFFE)) && (*a1)(a2) )
  {
    LastError = 0;
  }
  else
  {
    LastError = GetLastError();
  }
  return anonymous_namespace_::Remover::Report(a1, a2, v4, LastError);
}

```

## disassembly

```asm
0x180018594  push    rbx
0x180018596  push    rsi
0x180018597  push    rdi
0x180018598  push    r14
0x18001859a  push    r15
0x18001859c  sub     rsp, 20h
0x1800185a0  mov     rsi, rdx
0x1800185a3  xor     ebx, ebx
0x1800185a5  mov     edx, [r8]
0x1800185a8  mov     r14, r8
0x1800185ab  mov     r15, rcx
0x1800185ae  test    dl, 10h
0x1800185b1  jz      short loc_18001860F
0x1800185b3  mov     rcx, rsi; lpPathName
0x1800185b6  mov     edi, ebx
0x1800185b8  call    cs:__imp_RemoveDirectoryW
0x1800185be  test    eax, eax
0x1800185c0  jnz     short loc_180018600
0x1800185c2  call    cs:__imp_GetLastError
0x1800185c8  mov     edi, eax
0x1800185ca  cmp     eax, 5
0x1800185cd  jnz     short loc_180018600
0x1800185cf  mov     edx, [r14]
0x1800185d2  test    dl, 1
0x1800185d5  jz      short loc_180018600
0x1800185d7  and     edx, 0FFFFFFFEh; dwFileAttributes
0x1800185da  mov     rcx, rsi; lpFileName
0x1800185dd  call    cs:__imp_SetFileAttributesW
0x1800185e3  test    eax, eax
0x1800185e5  jz      short loc_1800185F8
0x1800185e7  mov     rcx, rsi; lpPathName
0x1800185ea  call    cs:__imp_RemoveDirectoryW
0x1800185f0  test    eax, eax
0x1800185f2  jz      short loc_1800185F8
0x1800185f4  mov     edi, ebx
0x1800185f6  jmp     short loc_180018600
0x1800185f8  call    cs:__imp_GetLastError
0x1800185fe  mov     edi, eax
0x180018600  mov     rcx, r14; this
0x180018603  call    ?IsDirectoryReparsePointOpaque@Common@@YA_NAEBU_WIN32_FIND_DATAW@@@Z; Common::IsDirectoryReparsePointOpaque(_WIN32_FIND_DATAW const &)
0x180018608  movzx   ebx, al
0x18001860b  inc     ebx
0x18001860d  jmp     short loc_18001863F
0x18001860f  test    dl, 1
0x180018612  jz      short loc_18001862E
0x180018614  and     edx, 0FFFFFFFEh; dwFileAttributes
0x180018617  mov     rcx, rsi; lpFileName
0x18001861a  call    cs:__imp_SetFileAttributesW
0x180018620  test    eax, eax
0x180018622  jnz     short loc_18001862E
0x180018624  call    cs:__imp_GetLastError
0x18001862a  mov     edi, eax
0x18001862c  jmp     short loc_18001863F
0x18001862e  mov     rax, [r15]
0x180018631  mov     rcx, rsi
0x180018634  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018639  test    eax, eax
0x18001863b  jz      short loc_180018624
0x18001863d  mov     edi, ebx
0x18001863f  mov     r9d, edi
0x180018642  mov     r8d, ebx
0x180018645  mov     rdx, rsi
0x180018648  mov     rcx, r15
0x18001864b  add     rsp, 20h
0x18001864f  pop     r15
0x180018651  pop     r14
0x180018653  pop     rdi
0x180018654  pop     rsi
0x180018655  pop     rbx
0x180018656  jmp     _anonymous_namespace___Remover__Report
```
