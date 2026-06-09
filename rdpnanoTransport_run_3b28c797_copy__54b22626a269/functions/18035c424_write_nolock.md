# _write_nolock

- ea: `0x18035c424`
- end: `0x18035c753`
- name: `_write_nolock`
- size: `815`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, installer_update`

## callers

- `0x18035c304`

## callees

- `0x18033eff4`
- `0x18033f210`
- `0x180343580`
- `0x18035bad8`
- `0x18035bf6c`
- `0x18035c074`
- `0x18035c190`
- `0x18035c424`
- `0x18035c804`
- `0x18036403c`
- `0x18036484c`

## import_xrefs

- `KERNEL32!GetConsoleMode` at `0x18035c542`
- `KERNEL32!GetConsoleMode` at `0x18035c542`
- `KERNEL32!GetLastError` at `0x18035c5d4`
- `KERNEL32!GetLastError` at `0x18035c6a4`
- `KERNEL32!GetLastError` at `0x18035c5d4`
- `KERNEL32!GetLastError` at `0x18035c6a4`
- `KERNEL32!WriteFile` at `0x18035c69a`
- `KERNEL32!WriteFile` at `0x18035c69a`

## pseudocode

```c
__int64 __fastcall write_nolock(int a1, _BYTE *a2, unsigned int a3, __int64 a4)
{
  int v4; // edi
  __int64 v5; // r14
  __int64 v6; // r13
  __int64 v10; // rax
  __int64 v11; // r12
  __int64 v12; // r15
  __int64 v13; // rcx
  wchar_t *v14; // r12
  wchar_t *v15; // r15
  DWORD v16; // r14d
  __int64 v17; // rax
  __int64 v18; // xmm0_8
  __int64 v19; // rdx
  void *v20; // rcx
  char v21; // [rsp+30h] [rbp-38h]
  wchar_t v22; // [rsp+30h] [rbp-38h]
  DWORD NumberOfBytesWritten[2]; // [rsp+38h] [rbp-30h] BYREF
  int v24; // [rsp+40h] [rbp-28h]
  __int64 v25; // [rsp+48h] [rbp-20h]
  DWORD Mode[4]; // [rsp+58h] [rbp-10h] BYREF

  v4 = 0;
  v5 = a3;
  v6 = a1;
  if ( !a3 )
    return 0;
  if ( !a2
    || (v10 = a1 & 0x3F,
        v11 = (__int64)a1 >> 6,
        v12 = 9 * v10,
        v13 = _pioinfo[v11],
        v21 = *(_BYTE *)(v13 + 72 * v10 + 57),
        (unsigned __int8)(v21 - 1) <= 1u)
    && (a3 & 1) != 0 )
  {
    *(_BYTE *)(a4 + 56) = 1;
    *(_DWORD *)(a4 + 52) = 0;
    *(_BYTE *)(a4 + 48) = 1;
    *(_DWORD *)(a4 + 44) = 22;
    invalid_parameter_internal(0, 0, 0, 0, 0, (__crt_cached_ptd_host *)a4);
    return 0xFFFFFFFFLL;
  }
  if ( (*(_BYTE *)(v13 + 72 * v10 + 56) & 0x20) != 0 )
    lseeki64_nolock_internal((unsigned int)v6, 0, 2);
  v25 = 0;
  if ( !isatty(v6) || *(char *)(_pioinfo[v11] + 8 * v12 + 56) >= 0 )
    goto LABEL_29;
  if ( !*(_BYTE *)(a4 + 40) )
    __crt_cached_ptd_host::update_locale_slow((__crt_cached_ptd_host *)a4);
  if ( !*(_QWORD *)(*(_QWORD *)(a4 + 24) + 312LL) && !*(_BYTE *)(_pioinfo[v11] + 8 * v12 + 57)
    || (Mode[0] = 0, !GetConsoleMode(*(HANDLE *)(_pioinfo[v11] + 8 * v12 + 40), Mode)) )
  {
LABEL_29:
    v19 = _pioinfo[v6 >> 6];
    if ( *(char *)(v19 + 72 * (v6 & 0x3F) + 56) >= 0 )
    {
      v20 = *(void **)(v19 + 72 * (v6 & 0x3F) + 40);
      *(_QWORD *)NumberOfBytesWritten = 0;
      v24 = 0;
      if ( !WriteFile(v20, a2, v5, &NumberOfBytesWritten[1], 0) )
        NumberOfBytesWritten[0] = GetLastError();
      v4 = v24;
LABEL_39:
      v18 = *(_QWORD *)NumberOfBytesWritten;
      goto LABEL_40;
    }
    if ( v21 )
    {
      if ( v21 == 1 )
      {
        v17 = write_text_utf8_nolock(NumberOfBytesWritten, (unsigned int)v6, a2, (unsigned int)v5);
      }
      else
      {
        if ( v21 != 2 )
          goto LABEL_41;
        v17 = write_text_utf16le_nolock(NumberOfBytesWritten, (unsigned int)v6, a2, (unsigned int)v5);
      }
    }
    else
    {
      v17 = write_text_ansi_nolock(NumberOfBytesWritten, (unsigned int)v6, a2, (unsigned int)v5);
    }
LABEL_28:
    v18 = *(_QWORD *)v17;
    v4 = *(_DWORD *)(v17 + 8);
LABEL_40:
    v25 = v18;
    goto LABEL_41;
  }
  if ( !v21 )
  {
    v17 = write_double_translated_ansi_nolock((__int64)NumberOfBytesWritten, v6, a2, v5, a4);
    goto LABEL_28;
  }
  if ( (unsigned int)(v21 - 1) <= 1 )
  {
    v14 = (wchar_t *)&a2[v5];
    *(_QWORD *)NumberOfBytesWritten = 0;
    v15 = (wchar_t *)a2;
    if ( a2 < &a2[v5] )
    {
      v16 = NumberOfBytesWritten[1];
      while ( 1 )
      {
        v22 = *v15;
        if ( putwch_nolock(*v15) != v22 )
          break;
        v16 += 2;
        NumberOfBytesWritten[1] = v16;
        if ( v22 == 10 )
        {
          if ( putwch_nolock(0xDu) != 13 )
            break;
          NumberOfBytesWritten[1] = ++v16;
          ++v4;
        }
        if ( ++v15 >= v14 )
          goto LABEL_39;
      }
      NumberOfBytesWritten[0] = GetLastError();
    }
    goto LABEL_39;
  }
LABEL_41:
  if ( HIDWORD(v25) )
    return (unsigned int)(HIDWORD(v25) - v4);
  if ( (_DWORD)v25 )
  {
    if ( (_DWORD)v25 == 5 )
    {
      *(_BYTE *)(a4 + 48) = 1;
      *(_DWORD *)(a4 + 44) = 9;
      *(_BYTE *)(a4 + 56) = 1;
      *(_DWORD *)(a4 + 52) = 5;
    }
    else
    {
      _acrt_errno_map_os_error_ptd((unsigned int)v25, a4, _pioinfo);
    }
    return 0xFFFFFFFFLL;
  }
  if ( (*(_BYTE *)(_pioinfo[v6 >> 6] + 72 * (v6 & 0x3F) + 56) & 0x40) == 0 || *a2 != 26 )
  {
    *(_DWORD *)(a4 + 52) = 0;
    *(_BYTE *)(a4 + 48) = 1;
    *(_DWORD *)(a4 + 44) = 28;
    *(_BYTE *)(a4 + 56) = 1;
    return 0xFFFFFFFFLL;
  }
  return 0;
}

```

## disassembly

```asm
0x18035c424  push    rbp
0x18035c426  push    rbx
0x18035c427  push    rsi
0x18035c428  push    rdi
0x18035c429  push    r12
0x18035c42b  push    r13
0x18035c42d  push    r14
0x18035c42f  push    r15
0x18035c431  mov     rbp, rsp
0x18035c434  sub     rsp, 68h
0x18035c438  xor     edi, edi
0x18035c43a  mov     r14d, r8d
0x18035c43d  movsxd  r13, ecx
0x18035c440  mov     rbx, r9
0x18035c443  mov     rsi, rdx
0x18035c446  test    r8d, r8d
0x18035c449  jz      loc_18035C740
0x18035c44f  test    rdx, rdx
0x18035c452  jnz     short loc_18035C48B
0x18035c454  mov     byte ptr [r9+38h], 1
0x18035c459  xor     r8d, r8d; FileName
0x18035c45c  mov     [r9+34h], edi
0x18035c460  xor     edx, edx; FunctionName
0x18035c462  mov     byte ptr [r9+30h], 1
0x18035c467  xor     ecx, ecx; Expression
0x18035c469  mov     dword ptr [r9+2Ch], 16h
0x18035c471  xor     r9d, r9d; LineNo
0x18035c474  mov     [rsp+68h+var_40], rbx; __crt_cached_ptd_host *
0x18035c479  mov     [rsp+68h+var_48], rdi; uintptr_t
0x18035c47e  call    _invalid_parameter_internal
0x18035c483  or      eax, 0FFFFFFFFh
0x18035c486  jmp     loc_18035C742
0x18035c48b  mov     rax, r13
0x18035c48e  lea     rcx, __pioinfo
0x18035c495  and     eax, 3Fh
0x18035c498  mov     r12, r13
0x18035c49b  sar     r12, 6
0x18035c49f  lea     r15, [rax+rax*8]
0x18035c4a3  mov     rcx, [rcx+r12*8]
0x18035c4a7  mov     al, [rcx+r15*8+39h]
0x18035c4ac  mov     byte ptr [rbp+var_38], al
0x18035c4af  dec     al
0x18035c4b1  cmp     al, 1
0x18035c4b3  ja      short loc_18035C4BE
0x18035c4b5  mov     eax, r14d
0x18035c4b8  not     eax
0x18035c4ba  test    al, 1
0x18035c4bc  jz      short loc_18035C454
0x18035c4be  test    byte ptr [rcx+r15*8+38h], 20h
0x18035c4c4  jz      short loc_18035C4D4
0x18035c4c6  xor     edx, edx
0x18035c4c8  mov     ecx, r13d
0x18035c4cb  lea     r8d, [rdx+2]
0x18035c4cf  call    _lseeki64_nolock_internal
0x18035c4d4  mov     ecx, r13d; FileHandle
0x18035c4d7  mov     [rbp+var_20], rdi
0x18035c4db  call    _isatty
0x18035c4e0  xor     ecx, ecx
0x18035c4e2  lea     r8, __pioinfo
0x18035c4e9  test    eax, eax
0x18035c4eb  jz      loc_18035C60C
0x18035c4f1  mov     rax, [r8+r12*8]
0x18035c4f5  cmp     [rax+r15*8+38h], cl
0x18035c4fa  jge     loc_18035C60C
0x18035c500  cmp     [rbx+28h], cl
0x18035c503  jnz     short loc_18035C516
0x18035c505  mov     rcx, rbx; this
0x18035c508  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x18035c50d  xor     ecx, ecx
0x18035c50f  lea     r8, __pioinfo
0x18035c516  mov     rax, [rbx+18h]
0x18035c51a  cmp     [rax+138h], rcx
0x18035c521  jnz     short loc_18035C532
0x18035c523  mov     rax, [r8+r12*8]
0x18035c527  cmp     [rax+r15*8+39h], cl
0x18035c52c  jz      loc_18035C60C
0x18035c532  mov     [rbp+Mode], ecx
0x18035c535  lea     rdx, [rbp+Mode]; lpMode
0x18035c539  mov     rcx, [r8+r12*8]
0x18035c53d  mov     rcx, [rcx+r15*8+28h]; hConsoleHandle
0x18035c542  call    cs:__imp_GetConsoleMode
0x18035c548  test    eax, eax
0x18035c54a  jz      loc_18035C605
0x18035c550  movsx   ecx, byte ptr [rbp+var_38]
0x18035c554  test    ecx, ecx
0x18035c556  jz      loc_18035C5E2
0x18035c55c  sub     ecx, 1
0x18035c55f  jz      short loc_18035C56A
0x18035c561  cmp     ecx, 1
0x18035c564  jnz     loc_18035C6BA
0x18035c56a  lea     r12, [rsi+r14]
0x18035c56e  mov     qword ptr [rbp+NumberOfBytesWritten], rdi
0x18035c572  mov     r15, rsi
0x18035c575  cmp     rsi, r12
0x18035c578  jnb     loc_18035C6B0
0x18035c57e  mov     r14d, [rbp+NumberOfBytesWritten+4]
0x18035c582  movzx   eax, word ptr [r15]
0x18035c586  movzx   ecx, ax; Character
0x18035c589  mov     [rbp+var_38], ax
0x18035c58d  call    _putwch_nolock
0x18035c592  movzx   ecx, [rbp+var_38]
0x18035c596  cmp     ax, cx
0x18035c599  jnz     short loc_18035C5D4
0x18035c59b  add     r14d, 2
0x18035c59f  mov     [rbp+NumberOfBytesWritten+4], r14d
0x18035c5a3  cmp     cx, 0Ah
0x18035c5a7  jnz     short loc_18035C5C6
0x18035c5a9  mov     ecx, 0Dh; Character
0x18035c5ae  call    _putwch_nolock
0x18035c5b3  mov     ecx, 0Dh
0x18035c5b8  cmp     ax, cx
0x18035c5bb  jnz     short loc_18035C5D4
0x18035c5bd  inc     r14d
0x18035c5c0  mov     [rbp+NumberOfBytesWritten+4], r14d
0x18035c5c4  inc     edi
0x18035c5c6  add     r15, 2
0x18035c5ca  cmp     r15, r12
0x18035c5cd  jb      short loc_18035C582
0x18035c5cf  jmp     loc_18035C6B0
0x18035c5d4  call    cs:__imp_GetLastError
0x18035c5da  mov     [rbp+NumberOfBytesWritten], eax
0x18035c5dd  jmp     loc_18035C6B0
0x18035c5e2  mov     r9d, r14d
0x18035c5e5  mov     [rsp+68h+var_48], rbx
0x18035c5ea  mov     r8, rsi
0x18035c5ed  lea     rcx, [rbp+NumberOfBytesWritten]
0x18035c5f1  mov     edx, r13d
0x18035c5f4  call    write_double_translated_ansi_nolock
0x18035c5f9  movsd   xmm0, qword ptr [rax]
0x18035c5fd  mov     edi, [rax+8]
0x18035c600  jmp     loc_18035C6B5
0x18035c605  lea     r8, __pioinfo
0x18035c60c  mov     rcx, r13
0x18035c60f  mov     rax, r13
0x18035c612  sar     rax, 6
0x18035c616  and     ecx, 3Fh
0x18035c619  mov     rdx, [r8+rax*8]
0x18035c61d  lea     rcx, [rcx+rcx*8]
0x18035c621  cmp     [rdx+rcx*8+38h], dil
0x18035c626  jge     short loc_18035C67D
0x18035c628  movsx   ecx, byte ptr [rbp+var_38]
0x18035c62c  test    ecx, ecx
0x18035c62e  jz      short loc_18035C666
0x18035c630  sub     ecx, 1
0x18035c633  jz      short loc_18035C652
0x18035c635  cmp     ecx, 1
0x18035c638  jnz     loc_18035C6C1
0x18035c63e  mov     r9d, r14d
0x18035c641  lea     rcx, [rbp+NumberOfBytesWritten]
0x18035c645  mov     r8, rsi
0x18035c648  mov     edx, r13d
0x18035c64b  call    write_text_utf16le_nolock
0x18035c650  jmp     short loc_18035C5F9
0x18035c652  mov     r9d, r14d
0x18035c655  lea     rcx, [rbp+NumberOfBytesWritten]
0x18035c659  mov     r8, rsi
0x18035c65c  mov     edx, r13d
0x18035c65f  call    write_text_utf8_nolock
0x18035c664  jmp     short loc_18035C5F9
0x18035c666  mov     r9d, r14d
0x18035c669  lea     rcx, [rbp+NumberOfBytesWritten]
0x18035c66d  mov     r8, rsi
0x18035c670  mov     edx, r13d
0x18035c673  call    write_text_ansi_nolock
0x18035c678  jmp     loc_18035C5F9
0x18035c67d  mov     rcx, [rdx+rcx*8+28h]; hFile
0x18035c682  lea     r9, [rbp+NumberOfBytesWritten+4]; lpNumberOfBytesWritten
0x18035c686  xor     eax, eax
0x18035c688  mov     rdx, rsi; lpBuffer
0x18035c68b  and     [rsp+68h+var_48], rax
0x18035c690  mov     r8d, r14d; nNumberOfBytesToWrite
0x18035c693  mov     qword ptr [rbp+NumberOfBytesWritten], rax
0x18035c697  mov     [rbp+var_28], eax
0x18035c69a  call    cs:__imp_WriteFile
0x18035c6a0  test    eax, eax
0x18035c6a2  jnz     short loc_18035C6AD
0x18035c6a4  call    cs:__imp_GetLastError
0x18035c6aa  mov     [rbp+NumberOfBytesWritten], eax
0x18035c6ad  mov     edi, [rbp+var_28]
0x18035c6b0  movsd   xmm0, qword ptr [rbp+NumberOfBytesWritten]
0x18035c6b5  movsd   [rbp+var_20], xmm0
0x18035c6ba  lea     r8, __pioinfo
0x18035c6c1  mov     rax, [rbp+var_20]
0x18035c6c5  shr     rax, 20h
0x18035c6c9  test    eax, eax
0x18035c6cb  jnz     short loc_18035C739
0x18035c6cd  mov     eax, dword ptr [rbp+var_20]
0x18035c6d0  test    eax, eax
0x18035c6d2  jz      short loc_18035C700
0x18035c6d4  cmp     eax, 5
0x18035c6d7  jnz     short loc_18035C6F0
0x18035c6d9  mov     byte ptr [rbx+30h], 1
0x18035c6dd  mov     dword ptr [rbx+2Ch], 9
0x18035c6e4  mov     byte ptr [rbx+38h], 1
0x18035c6e8  mov     [rbx+34h], eax
0x18035c6eb  jmp     loc_18035C483
0x18035c6f0  mov     ecx, dword ptr [rbp+var_20]
0x18035c6f3  mov     rdx, rbx
0x18035c6f6  call    __acrt_errno_map_os_error_ptd
0x18035c6fb  jmp     loc_18035C483
0x18035c700  mov     rcx, r13
0x18035c703  mov     rax, r13
0x18035c706  sar     rax, 6
0x18035c70a  and     ecx, 3Fh
0x18035c70d  mov     rax, [r8+rax*8]
0x18035c711  lea     rcx, [rcx+rcx*8]
0x18035c715  test    byte ptr [rax+rcx*8+38h], 40h
0x18035c71a  jz      short loc_18035C721
0x18035c71c  cmp     byte ptr [rsi], 1Ah
0x18035c71f  jz      short loc_18035C740
0x18035c721  and     dword ptr [rbx+34h], 0
0x18035c725  mov     byte ptr [rbx+30h], 1
0x18035c729  mov     dword ptr [rbx+2Ch], 1Ch
0x18035c730  mov     byte ptr [rbx+38h], 1
0x18035c734  jmp     loc_18035C483
0x18035c739  mov     eax, dword ptr [rbp+var_20+4]
0x18035c73c  sub     eax, edi
0x18035c73e  jmp     short loc_18035C742
0x18035c740  xor     eax, eax
0x18035c742  add     rsp, 68h
0x18035c746  pop     r15
0x18035c748  pop     r14
0x18035c74a  pop     r13
0x18035c74c  pop     r12
0x18035c74e  pop     rdi
0x18035c74f  pop     rsi
0x18035c750  pop     rbx
0x18035c751  pop     rbp
0x18035c752  retn
```
