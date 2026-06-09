# _anonymous_namespace_::Remover::VisitorCallback

- ea: `0x1800b02b0`
- end: `0x1800b03d0`
- name: `_anonymous_namespace_::Remover::VisitorCallback`
- size: `288`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x1800b02b0`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b02e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b032f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0383`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b02e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b032f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0383`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800b02d5`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800b031b`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800b02d5`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800b031b`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800b0308`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800b0373`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800b0308`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800b0373`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::Remover::VisitorCallback(__int64 a1, const WCHAR *a2, int *a3)
{
  int v5; // edx
  DWORD LastError; // ebx
  unsigned int v8; // edi
  unsigned int (__fastcall *v9)(const WCHAR *, _QWORD, _QWORD, _QWORD); // rax

  v5 = *a3;
  if ( (*a3 & 0x10) != 0 )
  {
    LastError = 0;
    v8 = 1;
    if ( !RemoveDirectoryW(a2) )
    {
      LastError = GetLastError();
      if ( LastError == 5 && (*a3 & 1) != 0 )
      {
        if ( SetFileAttributesW(a2, *a3 & 0xFFFFFFFE) && RemoveDirectoryW(a2) )
          LastError = 0;
        else
          LastError = GetLastError();
      }
    }
    if ( (*a3 & 0x410) == 0x410 && a3[9] != -2147483624 && a3[9] != -1879044072 )
      v8 = 2;
  }
  else
  {
    if ( ((v5 & 1) == 0 || SetFileAttributesW(a2, v5 & 0xFFFFFFFE))
      && (*(unsigned int (__fastcall **)(const WCHAR *))a1)(a2) )
    {
      LastError = 0;
    }
    else
    {
      LastError = GetLastError();
    }
    v8 = 0;
  }
  v9 = *(unsigned int (__fastcall **)(const WCHAR *, _QWORD, _QWORD, _QWORD))(a1 + 8);
  if ( v9 )
    return v9(a2, v8, LastError, *(_QWORD *)(a1 + 16));
  return LastError;
}

```

## disassembly

```asm
0x1800b02b0  push    rbx
0x1800b02b2  push    rbp
0x1800b02b3  push    rsi
0x1800b02b4  push    rdi
0x1800b02b5  push    r14
0x1800b02b7  sub     rsp, 30h
0x1800b02bb  mov     rbp, rdx
0x1800b02be  mov     rsi, r8
0x1800b02c1  mov     edx, [r8]
0x1800b02c4  mov     r14, rcx
0x1800b02c7  test    dl, 10h
0x1800b02ca  jz      loc_1800B0363
0x1800b02d0  mov     rcx, rbp; lpPathName
0x1800b02d3  xor     ebx, ebx
0x1800b02d5  call    cs:__imp_RemoveDirectoryW
0x1800b02dc  nop     dword ptr [rax+rax+00h]
0x1800b02e1  lea     edi, [rbx+1]
0x1800b02e4  test    eax, eax
0x1800b02e6  jnz     short loc_1800B033D
0x1800b02e8  call    cs:__imp_GetLastError
0x1800b02ef  nop     dword ptr [rax+rax+00h]
0x1800b02f4  mov     ebx, eax
0x1800b02f6  cmp     eax, 5
0x1800b02f9  jnz     short loc_1800B033D
0x1800b02fb  mov     edx, [rsi]
0x1800b02fd  test    dil, dl
0x1800b0300  jz      short loc_1800B033D
0x1800b0302  and     edx, 0FFFFFFFEh; dwFileAttributes
0x1800b0305  mov     rcx, rbp; lpFileName
0x1800b0308  call    cs:__imp_SetFileAttributesW
0x1800b030f  nop     dword ptr [rax+rax+00h]
0x1800b0314  test    eax, eax
0x1800b0316  jz      short loc_1800B032F
0x1800b0318  mov     rcx, rbp; lpPathName
0x1800b031b  call    cs:__imp_RemoveDirectoryW
0x1800b0322  nop     dword ptr [rax+rax+00h]
0x1800b0327  test    eax, eax
0x1800b0329  jz      short loc_1800B032F
0x1800b032b  xor     ebx, ebx
0x1800b032d  jmp     short loc_1800B033D
0x1800b032f  call    cs:__imp_GetLastError
0x1800b0336  nop     dword ptr [rax+rax+00h]
0x1800b033b  mov     ebx, eax
0x1800b033d  mov     eax, [rsi]
0x1800b033f  mov     ecx, 410h
0x1800b0344  and     eax, ecx
0x1800b0346  cmp     eax, ecx
0x1800b0348  jnz     short loc_1800B03A6
0x1800b034a  cmp     dword ptr [rsi+24h], 80000018h
0x1800b0351  jz      short loc_1800B03A6
0x1800b0353  cmp     dword ptr [rsi+24h], 90001018h
0x1800b035a  jz      short loc_1800B03A6
0x1800b035c  mov     edi, 2
0x1800b0361  jmp     short loc_1800B03A6
0x1800b0363  mov     edi, 1
0x1800b0368  test    dil, dl
0x1800b036b  jz      short loc_1800B0393
0x1800b036d  and     edx, 0FFFFFFFEh; dwFileAttributes
0x1800b0370  mov     rcx, rbp; lpFileName
0x1800b0373  call    cs:__imp_SetFileAttributesW
0x1800b037a  nop     dword ptr [rax+rax+00h]
0x1800b037f  test    eax, eax
0x1800b0381  jnz     short loc_1800B0393
0x1800b0383  call    cs:__imp_GetLastError
0x1800b038a  nop     dword ptr [rax+rax+00h]
0x1800b038f  mov     ebx, eax
0x1800b0391  jmp     short loc_1800B03A4
0x1800b0393  mov     rax, [r14]
0x1800b0396  mov     rcx, rbp
0x1800b0399  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b039e  test    eax, eax
0x1800b03a0  jz      short loc_1800B0383
0x1800b03a2  xor     ebx, ebx
0x1800b03a4  xor     edi, edi
0x1800b03a6  mov     rax, [r14+8]
0x1800b03aa  test    rax, rax
0x1800b03ad  jz      short loc_1800B03C2
0x1800b03af  mov     r9, [r14+10h]
0x1800b03b3  mov     r8d, ebx
0x1800b03b6  mov     edx, edi
0x1800b03b8  mov     rcx, rbp
0x1800b03bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b03c0  mov     ebx, eax
0x1800b03c2  mov     eax, ebx
0x1800b03c4  add     rsp, 30h
0x1800b03c8  pop     r14
0x1800b03ca  pop     rdi
0x1800b03cb  pop     rsi
0x1800b03cc  pop     rbp
0x1800b03cd  pop     rbx
0x1800b03ce  retn
```
