# _write_nolock

- ea: `0x18001d7b0`
- end: `0x18001da91`
- name: `_write_nolock`
- size: `737`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops`

## callers

- `0x18001d6c4`

## callees

- `0x1800189e4`
- `0x180019450`
- `0x180019500`
- `0x180019550`
- `0x180019570`
- `0x18001c9c4`
- `0x18001d124`
- `0x18001d32c`
- `0x18001d434`
- `0x18001d550`
- `0x18001d7b0`
- `0x18001e0e8`
- `0x18001e1e0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001d933`
- `KERNEL32!GetLastError` at `0x18001d9ea`
- `KERNEL32!GetLastError` at `0x18001d933`
- `KERNEL32!GetLastError` at `0x18001d9ea`
- `KERNEL32!GetConsoleMode` at `0x18001d8b8`
- `KERNEL32!GetConsoleMode` at `0x18001d8b8`
- `KERNEL32!WriteFile` at `0x18001d9e0`
- `KERNEL32!WriteFile` at `0x18001d9e0`

## pseudocode

```c
__int64 __fastcall write_nolock(unsigned int a1, const char *a2, unsigned int a3)
{
  DWORD v3; // edi
  __int64 v4; // r15
  __int64 v8; // r13
  unsigned __int64 v9; // r14
  __int64 v10; // rcx
  char v11; // bl
  const char *v12; // r12
  DWORD v13; // ebx
  wchar_t *v14; // r15
  wchar_t v15; // r13
  __int64 v16; // rax
  __int64 v17; // xmm0_8
  __int64 v18; // rcx
  void *v19; // rcx
  DWORD NumberOfBytesWritten[4]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v21; // [rsp+40h] [rbp-20h]
  __int64 v22; // [rsp+50h] [rbp-10h]
  DWORD Mode; // [rsp+58h] [rbp-8h] BYREF

  v3 = 0;
  v4 = a3;
  if ( !a3 )
    return 0;
  if ( !a2
    || (v8 = (__int64)(int)a1 >> 6,
        v9 = (unsigned __int64)(a1 & 0x3F) << 6,
        v22 = v8,
        v10 = _pioinfo[v8],
        v11 = *(_BYTE *)(v10 + v9 + 57),
        (unsigned __int8)(v11 - 1) <= 1u)
    && (a3 & 1) != 0 )
  {
    *_doserrno() = 0;
    *errno() = 22;
    invalid_parameter_noinfo();
    return 0xFFFFFFFFLL;
  }
  if ( (*(_BYTE *)(v10 + v9 + 56) & 0x20) != 0 )
    lseeki64_nolock(a1, 0, 2);
  v21 = 0;
  if ( isatty(a1)
    && *(char *)(_pioinfo[v8] + v9 + 56) < 0
    && (*(_QWORD *)(*(_QWORD *)(_acrt_getptd() + 144) + 312LL) || *(_BYTE *)(_pioinfo[v8] + v9 + 57))
    && GetConsoleMode(*(HANDLE *)(_pioinfo[v8] + v9 + 40), &Mode) )
  {
    if ( v11 )
    {
      if ( (unsigned __int8)(v11 - 1) > 1u )
        goto LABEL_40;
      NumberOfBytesWritten[0] = 0;
      v12 = &a2[v4];
      v13 = 0;
      v14 = (wchar_t *)a2;
      NumberOfBytesWritten[1] = 0;
      if ( a2 < v12 )
      {
        while ( 1 )
        {
          v15 = *v14;
          if ( putwch_nolock(*v14) != v15 )
            break;
          v13 += 2;
          NumberOfBytesWritten[1] = v13;
          if ( v15 == 10 )
          {
            if ( putwch_nolock(0xDu) != 13 )
              break;
            NumberOfBytesWritten[1] = ++v13;
            ++v3;
          }
          if ( ++v14 >= (wchar_t *)v12 )
            goto LABEL_25;
        }
        NumberOfBytesWritten[0] = GetLastError();
LABEL_25:
        v8 = v22;
      }
      goto LABEL_38;
    }
    v16 = write_double_translated_ansi_nolock((__int64)NumberOfBytesWritten, a1, a2, v4);
  }
  else
  {
    v18 = _pioinfo[v8];
    if ( *(char *)(v18 + v9 + 56) >= 0 )
    {
      v19 = *(void **)(v18 + v9 + 40);
      memset(NumberOfBytesWritten, 0, 12);
      if ( !WriteFile(v19, a2, v4, &NumberOfBytesWritten[1], 0) )
        NumberOfBytesWritten[0] = GetLastError();
      v3 = NumberOfBytesWritten[2];
LABEL_38:
      v17 = *(_QWORD *)NumberOfBytesWritten;
      goto LABEL_39;
    }
    if ( v11 )
    {
      if ( v11 == 1 )
      {
        v16 = write_text_utf8_nolock(NumberOfBytesWritten, a1, a2, (unsigned int)v4);
      }
      else
      {
        if ( v11 != 2 )
          goto LABEL_40;
        v16 = write_text_utf16le_nolock(NumberOfBytesWritten, a1, a2, (unsigned int)v4);
      }
    }
    else
    {
      v16 = write_text_ansi_nolock(NumberOfBytesWritten, a1, a2, (unsigned int)v4);
    }
  }
  v17 = *(_QWORD *)v16;
  v3 = *(_DWORD *)(v16 + 8);
LABEL_39:
  v21 = v17;
LABEL_40:
  if ( !HIDWORD(v21) )
  {
    if ( (_DWORD)v21 )
    {
      if ( (_DWORD)v21 == 5 )
      {
        *errno() = 9;
        *_doserrno() = 5;
      }
      else
      {
        _acrt_errno_map_os_error((unsigned int)v21);
      }
    }
    else
    {
      if ( (*(_BYTE *)(_pioinfo[v8] + v9 + 56) & 0x40) != 0 && *a2 == 26 )
        return 0;
      *errno() = 28;
      *_doserrno() = 0;
    }
    return 0xFFFFFFFFLL;
  }
  return HIDWORD(v21) - v3;
}

```

## disassembly

```asm
0x18001d7b0  mov     [rsp-38h+arg_18], rbx
0x18001d7b5  push    rbp
0x18001d7b6  push    rsi
0x18001d7b7  push    rdi
0x18001d7b8  push    r12
0x18001d7ba  push    r13
0x18001d7bc  push    r14
0x18001d7be  push    r15
0x18001d7c0  mov     rbp, rsp
0x18001d7c3  sub     rsp, 60h
0x18001d7c7  xor     edi, edi
0x18001d7c9  mov     r15d, r8d
0x18001d7cc  movsxd  r12, ecx
0x18001d7cf  mov     rsi, rdx
0x18001d7d2  test    r8d, r8d
0x18001d7d5  jnz     short loc_18001D7DE
0x18001d7d7  xor     eax, eax
0x18001d7d9  jmp     loc_18001DA79
0x18001d7de  test    rdx, rdx
0x18001d7e1  jnz     short loc_18001D802
0x18001d7e3  call    __doserrno
0x18001d7e8  mov     [rax], edi
0x18001d7ea  call    _errno
0x18001d7ef  mov     dword ptr [rax], 16h
0x18001d7f5  call    _invalid_parameter_noinfo
0x18001d7fa  or      eax, 0FFFFFFFFh
0x18001d7fd  jmp     loc_18001DA79
0x18001d802  mov     r14, r12
0x18001d805  lea     rax, __pioinfo
0x18001d80c  and     r14d, 3Fh
0x18001d810  mov     r13, r12
0x18001d813  sar     r13, 6
0x18001d817  shl     r14, 6
0x18001d81b  mov     [rbp+var_10], r13
0x18001d81f  mov     rcx, [rax+r13*8]
0x18001d823  mov     bl, [rcx+r14+39h]
0x18001d828  lea     eax, [rbx-1]
0x18001d82b  cmp     al, 1
0x18001d82d  ja      short loc_18001D838
0x18001d82f  mov     eax, r15d
0x18001d832  not     eax
0x18001d834  test    al, 1
0x18001d836  jz      short loc_18001D7E3
0x18001d838  test    byte ptr [rcx+r14+38h], 20h
0x18001d83e  jz      short loc_18001D84E
0x18001d840  xor     edx, edx
0x18001d842  mov     ecx, r12d
0x18001d845  lea     r8d, [rdx+2]
0x18001d849  call    _lseeki64_nolock
0x18001d84e  mov     ecx, r12d; FileHandle
0x18001d851  mov     [rbp+var_20], rdi
0x18001d855  call    _isatty
0x18001d85a  test    eax, eax
0x18001d85c  jz      loc_18001D963
0x18001d862  lea     rax, __pioinfo
0x18001d869  mov     rax, [rax+r13*8]
0x18001d86d  test    byte ptr [rax+r14+38h], 80h
0x18001d873  jz      loc_18001D963
0x18001d879  call    __acrt_getptd
0x18001d87e  mov     rcx, [rax+90h]
0x18001d885  cmp     [rcx+138h], rdi
0x18001d88c  jnz     short loc_18001D8A4
0x18001d88e  lea     rax, __pioinfo
0x18001d895  mov     rax, [rax+r13*8]
0x18001d899  cmp     [rax+r14+39h], dil
0x18001d89e  jz      loc_18001D963
0x18001d8a4  lea     rax, __pioinfo
0x18001d8ab  mov     rcx, [rax+r13*8]
0x18001d8af  lea     rdx, [rbp+Mode]; lpMode
0x18001d8b3  mov     rcx, [rcx+r14+28h]; hConsoleHandle
0x18001d8b8  call    cs:__imp_GetConsoleMode
0x18001d8be  test    eax, eax
0x18001d8c0  jz      loc_18001D963
0x18001d8c6  test    bl, bl
0x18001d8c8  jz      short loc_18001D945
0x18001d8ca  dec     bl
0x18001d8cc  cmp     bl, 1
0x18001d8cf  ja      loc_18001DA00
0x18001d8d5  and     [rbp+NumberOfBytesWritten], edi
0x18001d8d8  lea     r12, [rsi+r15]
0x18001d8dc  xor     ebx, ebx
0x18001d8de  mov     r15, rsi
0x18001d8e1  mov     [rbp+NumberOfBytesWritten+4], ebx
0x18001d8e4  cmp     rsi, r12
0x18001d8e7  jnb     loc_18001D9F6
0x18001d8ed  movzx   r13d, word ptr [r15]
0x18001d8f1  movzx   ecx, r13w; Character
0x18001d8f5  call    _putwch_nolock
0x18001d8fa  cmp     ax, r13w
0x18001d8fe  jnz     short loc_18001D933
0x18001d900  add     ebx, 2
0x18001d903  mov     [rbp+NumberOfBytesWritten+4], ebx
0x18001d906  cmp     r13w, 0Ah
0x18001d90b  jnz     short loc_18001D928
0x18001d90d  mov     r13d, 0Dh
0x18001d913  mov     ecx, r13d; Character
0x18001d916  call    _putwch_nolock
0x18001d91b  cmp     ax, r13w
0x18001d91f  jnz     short loc_18001D933
0x18001d921  inc     ebx
0x18001d923  mov     [rbp+NumberOfBytesWritten+4], ebx
0x18001d926  inc     edi
0x18001d928  add     r15, 2
0x18001d92c  cmp     r15, r12
0x18001d92f  jnb     short loc_18001D93C
0x18001d931  jmp     short loc_18001D8ED
0x18001d933  call    cs:__imp_GetLastError
0x18001d939  mov     [rbp+NumberOfBytesWritten], eax
0x18001d93c  mov     r13, [rbp+var_10]
0x18001d940  jmp     loc_18001D9F6
0x18001d945  mov     r9d, r15d
0x18001d948  lea     rcx, [rbp+NumberOfBytesWritten]
0x18001d94c  mov     r8, rsi
0x18001d94f  mov     edx, r12d
0x18001d952  call    write_double_translated_ansi_nolock
0x18001d957  movsd   xmm0, qword ptr [rax]
0x18001d95b  mov     edi, [rax+8]
0x18001d95e  jmp     loc_18001D9FB
0x18001d963  lea     rax, __pioinfo
0x18001d96a  mov     rcx, [rax+r13*8]
0x18001d96e  test    byte ptr [rcx+r14+38h], 80h
0x18001d974  jz      short loc_18001D9C3
0x18001d976  movsx   ecx, bl
0x18001d979  test    bl, bl
0x18001d97b  jz      short loc_18001D9AF
0x18001d97d  sub     ecx, 1
0x18001d980  jz      short loc_18001D99B
0x18001d982  cmp     ecx, 1
0x18001d985  jnz     short loc_18001DA00
0x18001d987  mov     r9d, r15d
0x18001d98a  lea     rcx, [rbp+NumberOfBytesWritten]
0x18001d98e  mov     r8, rsi
0x18001d991  mov     edx, r12d
0x18001d994  call    write_text_utf16le_nolock
0x18001d999  jmp     short loc_18001D957
0x18001d99b  mov     r9d, r15d
0x18001d99e  lea     rcx, [rbp+NumberOfBytesWritten]
0x18001d9a2  mov     r8, rsi
0x18001d9a5  mov     edx, r12d
0x18001d9a8  call    write_text_utf8_nolock
0x18001d9ad  jmp     short loc_18001D957
0x18001d9af  mov     r9d, r15d
0x18001d9b2  lea     rcx, [rbp+NumberOfBytesWritten]
0x18001d9b6  mov     r8, rsi
0x18001d9b9  mov     edx, r12d
0x18001d9bc  call    write_text_ansi_nolock
0x18001d9c1  jmp     short loc_18001D957
0x18001d9c3  mov     rcx, [rcx+r14+28h]; hFile
0x18001d9c8  lea     r9, [rbp+NumberOfBytesWritten+4]; lpNumberOfBytesWritten
0x18001d9cc  and     [rbp+NumberOfBytesWritten], edi
0x18001d9cf  xor     eax, eax
0x18001d9d1  and     [rsp+60h+var_40], rax
0x18001d9d6  mov     r8d, r15d; nNumberOfBytesToWrite
0x18001d9d9  mov     rdx, rsi; lpBuffer
0x18001d9dc  mov     qword ptr [rbp+NumberOfBytesWritten+4], rax
0x18001d9e0  call    cs:__imp_WriteFile
0x18001d9e6  test    eax, eax
0x18001d9e8  jnz     short loc_18001D9F3
0x18001d9ea  call    cs:__imp_GetLastError
0x18001d9f0  mov     [rbp+NumberOfBytesWritten], eax
0x18001d9f3  mov     edi, [rbp+NumberOfBytesWritten+8]
0x18001d9f6  movsd   xmm0, qword ptr [rbp+NumberOfBytesWritten]
0x18001d9fb  movsd   [rbp+var_20], xmm0
0x18001da00  mov     rax, [rbp+var_20]
0x18001da04  shr     rax, 20h
0x18001da08  test    eax, eax
0x18001da0a  jnz     short loc_18001DA74
0x18001da0c  mov     eax, dword ptr [rbp+var_20]
0x18001da0f  test    eax, eax
0x18001da11  jz      short loc_18001DA40
0x18001da13  cmp     eax, 5
0x18001da16  jnz     short loc_18001DA33
0x18001da18  call    _errno
0x18001da1d  mov     dword ptr [rax], 9
0x18001da23  call    __doserrno
0x18001da28  mov     dword ptr [rax], 5
0x18001da2e  jmp     loc_18001D7FA
0x18001da33  mov     ecx, dword ptr [rbp+var_20]
0x18001da36  call    __acrt_errno_map_os_error
0x18001da3b  jmp     loc_18001D7FA
0x18001da40  lea     rax, __pioinfo
0x18001da47  mov     rax, [rax+r13*8]
0x18001da4b  test    byte ptr [rax+r14+38h], 40h
0x18001da51  jz      short loc_18001DA5C
0x18001da53  cmp     byte ptr [rsi], 1Ah
0x18001da56  jz      loc_18001D7D7
0x18001da5c  call    _errno
0x18001da61  mov     dword ptr [rax], 1Ch
0x18001da67  call    __doserrno
0x18001da6c  and     dword ptr [rax], 0
0x18001da6f  jmp     loc_18001D7FA
0x18001da74  mov     eax, dword ptr [rbp+var_20+4]
0x18001da77  sub     eax, edi
0x18001da79  mov     rbx, [rsp+60h+arg_18]
0x18001da81  add     rsp, 60h
0x18001da85  pop     r15
0x18001da87  pop     r14
0x18001da89  pop     r13
0x18001da8b  pop     r12
0x18001da8d  pop     rdi
0x18001da8e  pop     rsi
0x18001da8f  pop     rbp
0x18001da90  retn
```
