# _write_nolock

- ea: `0x1800febf0`
- end: `0x1800feed1`
- name: `_write_nolock`
- size: `737`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops`

## callers

- `0x1800feb04`

## callees

- `0x1800f95bc`
- `0x1800f9a0c`
- `0x1800f9a5c`
- `0x1800f9a7c`
- `0x1800fc7c4`
- `0x1800fe564`
- `0x1800fe76c`
- `0x1800fe874`
- `0x1800fe990`
- `0x1800febf0`
- `0x180102a30`
- `0x1801035b8`
- `0x1801035c0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800fed73`
- `KERNEL32!GetLastError` at `0x1800fee2a`
- `KERNEL32!GetLastError` at `0x1800fed73`
- `KERNEL32!GetLastError` at `0x1800fee2a`
- `KERNEL32!WriteFile` at `0x1800fee20`
- `KERNEL32!WriteFile` at `0x1800fee20`
- `KERNEL32!GetConsoleMode` at `0x1800fecf8`
- `KERNEL32!GetConsoleMode` at `0x1800fecf8`

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
0x1800febf0  mov     [rsp-38h+arg_18], rbx
0x1800febf5  push    rbp
0x1800febf6  push    rsi
0x1800febf7  push    rdi
0x1800febf8  push    r12
0x1800febfa  push    r13
0x1800febfc  push    r14
0x1800febfe  push    r15
0x1800fec00  mov     rbp, rsp
0x1800fec03  sub     rsp, 60h
0x1800fec07  xor     edi, edi
0x1800fec09  mov     r15d, r8d
0x1800fec0c  movsxd  r12, ecx
0x1800fec0f  mov     rsi, rdx
0x1800fec12  test    r8d, r8d
0x1800fec15  jnz     short loc_1800FEC1E
0x1800fec17  xor     eax, eax
0x1800fec19  jmp     loc_1800FEEB9
0x1800fec1e  test    rdx, rdx
0x1800fec21  jnz     short loc_1800FEC42
0x1800fec23  call    __doserrno
0x1800fec28  mov     [rax], edi
0x1800fec2a  call    _errno
0x1800fec2f  mov     dword ptr [rax], 16h
0x1800fec35  call    _invalid_parameter_noinfo
0x1800fec3a  or      eax, 0FFFFFFFFh
0x1800fec3d  jmp     loc_1800FEEB9
0x1800fec42  mov     r14, r12
0x1800fec45  lea     rax, __pioinfo
0x1800fec4c  and     r14d, 3Fh
0x1800fec50  mov     r13, r12
0x1800fec53  sar     r13, 6
0x1800fec57  shl     r14, 6
0x1800fec5b  mov     [rbp+var_10], r13
0x1800fec5f  mov     rcx, [rax+r13*8]
0x1800fec63  mov     bl, [rcx+r14+39h]
0x1800fec68  lea     eax, [rbx-1]
0x1800fec6b  cmp     al, 1
0x1800fec6d  ja      short loc_1800FEC78
0x1800fec6f  mov     eax, r15d
0x1800fec72  not     eax
0x1800fec74  test    al, 1
0x1800fec76  jz      short loc_1800FEC23
0x1800fec78  test    byte ptr [rcx+r14+38h], 20h
0x1800fec7e  jz      short loc_1800FEC8E
0x1800fec80  xor     edx, edx
0x1800fec82  mov     ecx, r12d
0x1800fec85  lea     r8d, [rdx+2]
0x1800fec89  call    _lseeki64_nolock
0x1800fec8e  mov     ecx, r12d; FileHandle
0x1800fec91  mov     [rbp+var_20], rdi
0x1800fec95  call    _isatty
0x1800fec9a  test    eax, eax
0x1800fec9c  jz      loc_1800FEDA3
0x1800feca2  lea     rax, __pioinfo
0x1800feca9  mov     rax, [rax+r13*8]
0x1800fecad  test    byte ptr [rax+r14+38h], 80h
0x1800fecb3  jz      loc_1800FEDA3
0x1800fecb9  call    __acrt_getptd
0x1800fecbe  mov     rcx, [rax+90h]
0x1800fecc5  cmp     [rcx+138h], rdi
0x1800feccc  jnz     short loc_1800FECE4
0x1800fecce  lea     rax, __pioinfo
0x1800fecd5  mov     rax, [rax+r13*8]
0x1800fecd9  cmp     [rax+r14+39h], dil
0x1800fecde  jz      loc_1800FEDA3
0x1800fece4  lea     rax, __pioinfo
0x1800feceb  mov     rcx, [rax+r13*8]
0x1800fecef  lea     rdx, [rbp+Mode]; lpMode
0x1800fecf3  mov     rcx, [rcx+r14+28h]; hConsoleHandle
0x1800fecf8  call    cs:__imp_GetConsoleMode
0x1800fecfe  test    eax, eax
0x1800fed00  jz      loc_1800FEDA3
0x1800fed06  test    bl, bl
0x1800fed08  jz      short loc_1800FED85
0x1800fed0a  dec     bl
0x1800fed0c  cmp     bl, 1
0x1800fed0f  ja      loc_1800FEE40
0x1800fed15  and     [rbp+NumberOfBytesWritten], edi
0x1800fed18  lea     r12, [rsi+r15]
0x1800fed1c  xor     ebx, ebx
0x1800fed1e  mov     r15, rsi
0x1800fed21  mov     [rbp+NumberOfBytesWritten+4], ebx
0x1800fed24  cmp     rsi, r12
0x1800fed27  jnb     loc_1800FEE36
0x1800fed2d  movzx   r13d, word ptr [r15]
0x1800fed31  movzx   ecx, r13w; Character
0x1800fed35  call    _putwch_nolock
0x1800fed3a  cmp     ax, r13w
0x1800fed3e  jnz     short loc_1800FED73
0x1800fed40  add     ebx, 2
0x1800fed43  mov     [rbp+NumberOfBytesWritten+4], ebx
0x1800fed46  cmp     r13w, 0Ah
0x1800fed4b  jnz     short loc_1800FED68
0x1800fed4d  mov     r13d, 0Dh
0x1800fed53  mov     ecx, r13d; Character
0x1800fed56  call    _putwch_nolock
0x1800fed5b  cmp     ax, r13w
0x1800fed5f  jnz     short loc_1800FED73
0x1800fed61  inc     ebx
0x1800fed63  mov     [rbp+NumberOfBytesWritten+4], ebx
0x1800fed66  inc     edi
0x1800fed68  add     r15, 2
0x1800fed6c  cmp     r15, r12
0x1800fed6f  jnb     short loc_1800FED7C
0x1800fed71  jmp     short loc_1800FED2D
0x1800fed73  call    cs:__imp_GetLastError
0x1800fed79  mov     [rbp+NumberOfBytesWritten], eax
0x1800fed7c  mov     r13, [rbp+var_10]
0x1800fed80  jmp     loc_1800FEE36
0x1800fed85  mov     r9d, r15d
0x1800fed88  lea     rcx, [rbp+NumberOfBytesWritten]
0x1800fed8c  mov     r8, rsi
0x1800fed8f  mov     edx, r12d
0x1800fed92  call    write_double_translated_ansi_nolock
0x1800fed97  movsd   xmm0, qword ptr [rax]
0x1800fed9b  mov     edi, [rax+8]
0x1800fed9e  jmp     loc_1800FEE3B
0x1800feda3  lea     rax, __pioinfo
0x1800fedaa  mov     rcx, [rax+r13*8]
0x1800fedae  test    byte ptr [rcx+r14+38h], 80h
0x1800fedb4  jz      short loc_1800FEE03
0x1800fedb6  movsx   ecx, bl
0x1800fedb9  test    bl, bl
0x1800fedbb  jz      short loc_1800FEDEF
0x1800fedbd  sub     ecx, 1
0x1800fedc0  jz      short loc_1800FEDDB
0x1800fedc2  cmp     ecx, 1
0x1800fedc5  jnz     short loc_1800FEE40
0x1800fedc7  mov     r9d, r15d
0x1800fedca  lea     rcx, [rbp+NumberOfBytesWritten]
0x1800fedce  mov     r8, rsi
0x1800fedd1  mov     edx, r12d
0x1800fedd4  call    write_text_utf16le_nolock
0x1800fedd9  jmp     short loc_1800FED97
0x1800feddb  mov     r9d, r15d
0x1800fedde  lea     rcx, [rbp+NumberOfBytesWritten]
0x1800fede2  mov     r8, rsi
0x1800fede5  mov     edx, r12d
0x1800fede8  call    write_text_utf8_nolock
0x1800feded  jmp     short loc_1800FED97
0x1800fedef  mov     r9d, r15d
0x1800fedf2  lea     rcx, [rbp+NumberOfBytesWritten]
0x1800fedf6  mov     r8, rsi
0x1800fedf9  mov     edx, r12d
0x1800fedfc  call    write_text_ansi_nolock
0x1800fee01  jmp     short loc_1800FED97
0x1800fee03  mov     rcx, [rcx+r14+28h]; hFile
0x1800fee08  lea     r9, [rbp+NumberOfBytesWritten+4]; lpNumberOfBytesWritten
0x1800fee0c  and     [rbp+NumberOfBytesWritten], edi
0x1800fee0f  xor     eax, eax
0x1800fee11  and     [rsp+60h+var_40], rax
0x1800fee16  mov     r8d, r15d; nNumberOfBytesToWrite
0x1800fee19  mov     rdx, rsi; lpBuffer
0x1800fee1c  mov     qword ptr [rbp+NumberOfBytesWritten+4], rax
0x1800fee20  call    cs:__imp_WriteFile
0x1800fee26  test    eax, eax
0x1800fee28  jnz     short loc_1800FEE33
0x1800fee2a  call    cs:__imp_GetLastError
0x1800fee30  mov     [rbp+NumberOfBytesWritten], eax
0x1800fee33  mov     edi, [rbp+NumberOfBytesWritten+8]
0x1800fee36  movsd   xmm0, qword ptr [rbp+NumberOfBytesWritten]
0x1800fee3b  movsd   [rbp+var_20], xmm0
0x1800fee40  mov     rax, [rbp+var_20]
0x1800fee44  shr     rax, 20h
0x1800fee48  test    eax, eax
0x1800fee4a  jnz     short loc_1800FEEB4
0x1800fee4c  mov     eax, dword ptr [rbp+var_20]
0x1800fee4f  test    eax, eax
0x1800fee51  jz      short loc_1800FEE80
0x1800fee53  cmp     eax, 5
0x1800fee56  jnz     short loc_1800FEE73
0x1800fee58  call    _errno
0x1800fee5d  mov     dword ptr [rax], 9
0x1800fee63  call    __doserrno
0x1800fee68  mov     dword ptr [rax], 5
0x1800fee6e  jmp     loc_1800FEC3A
0x1800fee73  mov     ecx, dword ptr [rbp+var_20]
0x1800fee76  call    __acrt_errno_map_os_error
0x1800fee7b  jmp     loc_1800FEC3A
0x1800fee80  lea     rax, __pioinfo
0x1800fee87  mov     rax, [rax+r13*8]
0x1800fee8b  test    byte ptr [rax+r14+38h], 40h
0x1800fee91  jz      short loc_1800FEE9C
0x1800fee93  cmp     byte ptr [rsi], 1Ah
0x1800fee96  jz      loc_1800FEC17
0x1800fee9c  call    _errno
0x1800feea1  mov     dword ptr [rax], 1Ch
0x1800feea7  call    __doserrno
0x1800feeac  and     dword ptr [rax], 0
0x1800feeaf  jmp     loc_1800FEC3A
0x1800feeb4  mov     eax, dword ptr [rbp+var_20+4]
0x1800feeb7  sub     eax, edi
0x1800feeb9  mov     rbx, [rsp+60h+arg_18]
0x1800feec1  add     rsp, 60h
0x1800feec5  pop     r15
0x1800feec7  pop     r14
0x1800feec9  pop     r13
0x1800feecb  pop     r12
0x1800feecd  pop     rdi
0x1800feece  pop     rsi
0x1800feecf  pop     rbp
0x1800feed0  retn
```
