# _write_nolock

- ea: `0x18001cc4c`
- end: `0x18001cf5e`
- name: `_write_nolock`
- size: `786`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, installer_update`

## callers

- `0x18001cb24`

## callees

- `0x180014e3c`
- `0x180015080`
- `0x180018020`
- `0x18001bd80`
- `0x18001c26c`
- `0x18001c764`
- `0x18001c878`
- `0x18001c9a0`
- `0x18001cc4c`
- `0x18001d004`
- `0x18001d33c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cdf9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ceb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cdf9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ceb6`
- `api-ms-win-core-console-l1-1-0!GetConsoleMode` at `0x18001cd74`
- `api-ms-win-core-console-l1-1-0!GetConsoleMode` at `0x18001cd74`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001ceac`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001ceac`

## pseudocode

```c
__int64 __fastcall write_nolock(unsigned int a1, wchar_t *a2, unsigned int a3, __int64 dwErrCode)
{
  int v4; // r14d
  __int64 v5; // r12
  __int64 v10; // rax
  __int64 v11; // r13
  __int64 v12; // rdx
  DWORD LastError; // edi
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int32 v17; // r15d
  wchar_t *v18; // r12
  wchar_t *v19; // rdi
  unsigned __int64 *v20; // rax
  __m128i v21; // xmm0
  __int64 v22; // rcx
  void *v23; // rcx
  char v24; // [rsp+30h] [rbp-48h]
  wchar_t v25; // [rsp+30h] [rbp-48h]
  __int64 v26; // [rsp+38h] [rbp-40h]
  __int32 v27; // [rsp+44h] [rbp-34h]
  DWORD NumberOfBytesWritten[2]; // [rsp+50h] [rbp-28h] BYREF
  int v29; // [rsp+58h] [rbp-20h]
  DWORD Mode[6]; // [rsp+60h] [rbp-18h] BYREF

  v4 = 0;
  v5 = a3;
  if ( !a3 )
    return 0;
  if ( !a2
    || (v10 = a1 & 0x3F,
        v26 = (__int64)(int)a1 >> 6,
        v11 = 9 * v10,
        v12 = _pioinfo[v26],
        v24 = *(_BYTE *)(v12 + 72 * v10 + 57),
        (unsigned __int8)(v24 - 1) <= 1u)
    && (a3 & 1) != 0 )
  {
    *(_BYTE *)(dwErrCode + 56) = 1;
    *(_DWORD *)(dwErrCode + 52) = 0;
    *(_BYTE *)(dwErrCode + 48) = 1;
    *(_DWORD *)(dwErrCode + 44) = 22;
    invalid_parameter_internal(0, 0, 0, 0, 0, dwErrCode);
    return 0xFFFFFFFFLL;
  }
  if ( (*(_BYTE *)(v12 + 72 * v10 + 56) & 0x20) != 0 )
    lseeki64_nolock_internal(a1, 0, 2);
  v27 = 0;
  LastError = 0;
  v14 = isatty(a1);
  v15 = v26;
  if ( v14 && *(char *)(_pioinfo[v26] + 8 * v11 + 56) < 0 )
  {
    if ( !*(_BYTE *)(dwErrCode + 40) )
    {
      __crt_cached_ptd_host::update_locale_slow((__crt_cached_ptd_host *)dwErrCode);
      v15 = v26;
    }
    if ( *(_QWORD *)(*(_QWORD *)(dwErrCode + 24) + 312LL) || *(_BYTE *)(_pioinfo[v15] + 8 * v11 + 57) )
    {
      v16 = _pioinfo[v15];
      Mode[0] = 0;
      if ( GetConsoleMode(*(HANDLE *)(v16 + 8 * v11 + 40), Mode) )
      {
        if ( v24 )
        {
          if ( (unsigned int)(v24 - 1) <= 1 )
          {
            v17 = 0;
            v18 = (wchar_t *)((char *)a2 + v5);
            v19 = a2;
            if ( a2 >= v18 )
            {
LABEL_24:
              LastError = 0;
            }
            else
            {
              while ( 1 )
              {
                v25 = *v19;
                if ( putwch_nolock(*v19) != v25 )
                  break;
                v17 += 2;
                if ( v25 == 10 )
                {
                  if ( putwch_nolock(0xDu) != 13 )
                    break;
                  ++v17;
                  ++v4;
                }
                if ( ++v19 >= v18 )
                  goto LABEL_24;
              }
              LastError = GetLastError();
            }
            v27 = v17;
          }
          goto LABEL_41;
        }
        v20 = (unsigned __int64 *)write_double_translated_ansi_nolock(
                                    (__int64)NumberOfBytesWritten,
                                    a1,
                                    a2,
                                    v5,
                                    dwErrCode);
        goto LABEL_28;
      }
      v15 = v26;
    }
  }
  v22 = _pioinfo[v15];
  if ( *(char *)(v22 + 8 * v11 + 56) >= 0 )
  {
    v23 = *(void **)(v22 + 8 * v11 + 40);
    *(_QWORD *)NumberOfBytesWritten = 0;
    v29 = 0;
    if ( !WriteFile(v23, a2, v5, &NumberOfBytesWritten[1], 0) )
      NumberOfBytesWritten[0] = GetLastError();
    v21 = (__m128i)*(unsigned __int64 *)NumberOfBytesWritten;
    v4 = v29;
    goto LABEL_40;
  }
  switch ( v24 )
  {
    case 0:
      v20 = (unsigned __int64 *)write_text_ansi_nolock(NumberOfBytesWritten, a1, a2, (unsigned int)v5);
      goto LABEL_28;
    case 1:
      v20 = (unsigned __int64 *)write_text_utf8_nolock(NumberOfBytesWritten, a1, a2, (unsigned int)v5);
      goto LABEL_28;
    case 2:
      v20 = (unsigned __int64 *)write_text_utf16le_nolock(NumberOfBytesWritten, a1, a2, (unsigned int)v5);
LABEL_28:
      v21 = (__m128i)*v20;
      v4 = *((_DWORD *)v20 + 2);
LABEL_40:
      LastError = _mm_cvtsi128_si32(v21);
      v27 = v21.m128i_i32[1];
LABEL_41:
      v15 = v26;
      break;
  }
  if ( v27 )
    return (unsigned int)(v27 - v4);
  if ( LastError )
  {
    if ( LastError == 5 )
    {
      *(_BYTE *)(dwErrCode + 48) = 1;
      *(_DWORD *)(dwErrCode + 44) = 9;
      *(_BYTE *)(dwErrCode + 56) = 1;
      *(_DWORD *)(dwErrCode + 52) = 5;
    }
    else
    {
      _acrt_errno_map_os_error_ptd(LastError, dwErrCode, _pioinfo);
    }
    return 0xFFFFFFFFLL;
  }
  if ( (*(_BYTE *)(_pioinfo[v15] + 8 * v11 + 56) & 0x40) == 0 || *(_BYTE *)a2 != 26 )
  {
    *(_BYTE *)(dwErrCode + 48) = 1;
    *(_DWORD *)(dwErrCode + 44) = 28;
    *(_BYTE *)(dwErrCode + 56) = 1;
    *(_DWORD *)(dwErrCode + 52) = 0;
    return 0xFFFFFFFFLL;
  }
  return 0;
}

```

## disassembly

```asm
0x18001cc4c  push    rbp
0x18001cc4e  push    rbx
0x18001cc4f  push    rsi
0x18001cc50  push    rdi
0x18001cc51  push    r12
0x18001cc53  push    r13
0x18001cc55  push    r14
0x18001cc57  push    r15
0x18001cc59  mov     rbp, rsp
0x18001cc5c  sub     rsp, 78h
0x18001cc60  xor     r14d, r14d
0x18001cc63  mov     r12d, r8d
0x18001cc66  movsxd  r15, ecx
0x18001cc69  mov     rbx, r9
0x18001cc6c  mov     rsi, rdx
0x18001cc6f  test    r8d, r8d
0x18001cc72  jz      loc_18001CF4B
0x18001cc78  test    rdx, rdx
0x18001cc7b  jnz     short loc_18001CCB4
0x18001cc7d  mov     byte ptr [r9+38h], 1
0x18001cc82  xor     r8d, r8d; FileName
0x18001cc85  mov     [r9+34h], r14d
0x18001cc89  xor     edx, edx; FunctionName
0x18001cc8b  mov     byte ptr [r9+30h], 1
0x18001cc90  xor     ecx, ecx; Expression
0x18001cc92  mov     dword ptr [r9+2Ch], 16h
0x18001cc9a  xor     r9d, r9d; LineNo
0x18001cc9d  mov     qword ptr [rsp+78h+dwErrCode], rbx; dwErrCode
0x18001cca2  mov     [rsp+78h+lpOverlapped], r14; uintptr_t
0x18001cca7  call    _invalid_parameter_internal
0x18001ccac  or      eax, 0FFFFFFFFh
0x18001ccaf  jmp     loc_18001CF4D
0x18001ccb4  mov     eax, r15d
0x18001ccb7  lea     rdx, __pioinfo
0x18001ccbe  and     eax, 3Fh
0x18001ccc1  mov     rcx, r15
0x18001ccc4  sar     rcx, 6
0x18001ccc8  mov     [rbp+var_40], rcx
0x18001cccc  lea     r13, [rax+rax*8]
0x18001ccd0  mov     rdx, [rdx+rcx*8]
0x18001ccd4  mov     al, [rdx+r13*8+39h]
0x18001ccd9  mov     byte ptr [rbp+var_48], al
0x18001ccdc  dec     al
0x18001ccde  cmp     al, 1
0x18001cce0  ja      short loc_18001CCE8
0x18001cce2  test    r12b, 1
0x18001cce6  jnz     short loc_18001CC7D
0x18001cce8  test    byte ptr [rdx+r13*8+38h], 20h
0x18001ccee  jz      short loc_18001CCFE
0x18001ccf0  xor     edx, edx
0x18001ccf2  mov     ecx, r15d
0x18001ccf5  lea     r8d, [rdx+2]
0x18001ccf9  call    _lseeki64_nolock_internal
0x18001ccfe  mov     ecx, r15d; FileHandle
0x18001cd01  mov     qword ptr [rbp+var_38], r14
0x18001cd05  mov     edi, r14d
0x18001cd08  call    _isatty
0x18001cd0d  mov     rdx, [rbp+var_40]
0x18001cd11  lea     r8, __pioinfo
0x18001cd18  test    eax, eax
0x18001cd1a  jz      loc_18001CE32
0x18001cd20  mov     rax, [r8+rdx*8]
0x18001cd24  cmp     [rax+r13*8+38h], dil
0x18001cd29  jge     loc_18001CE32
0x18001cd2f  cmp     [rbx+28h], dil
0x18001cd33  jnz     short loc_18001CD48
0x18001cd35  mov     rcx, rbx; this
0x18001cd38  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x18001cd3d  mov     rdx, [rbp+var_40]
0x18001cd41  lea     r8, __pioinfo
0x18001cd48  mov     rax, [rbx+18h]
0x18001cd4c  cmp     [rax+138h], rdi
0x18001cd53  jnz     short loc_18001CD64
0x18001cd55  mov     rax, [r8+rdx*8]
0x18001cd59  cmp     [rax+r13*8+39h], dil
0x18001cd5e  jz      loc_18001CE32
0x18001cd64  mov     rcx, [r8+rdx*8]
0x18001cd68  lea     rdx, [rbp+Mode]; lpMode
0x18001cd6c  mov     [rbp+Mode], edi
0x18001cd6f  mov     rcx, [rcx+r13*8+28h]; hConsoleHandle
0x18001cd74  call    cs:__imp_GetConsoleMode
0x18001cd7a  test    eax, eax
0x18001cd7c  jz      loc_18001CE27
0x18001cd82  movsx   ecx, byte ptr [rbp+var_48]
0x18001cd86  test    ecx, ecx
0x18001cd88  jz      short loc_18001CE03
0x18001cd8a  sub     ecx, 1
0x18001cd8d  jz      short loc_18001CD98
0x18001cd8f  cmp     ecx, 1
0x18001cd92  jnz     loc_18001CED1
0x18001cd98  xor     r15d, r15d
0x18001cd9b  add     r12, rsi
0x18001cd9e  mov     rdi, rsi
0x18001cda1  cmp     rsi, r12
0x18001cda4  jnb     short loc_18001CDEB
0x18001cda6  movzx   eax, word ptr [rdi]
0x18001cda9  movzx   ecx, ax; Character
0x18001cdac  mov     [rbp+var_48], ax
0x18001cdb0  call    _putwch_nolock
0x18001cdb5  movzx   ecx, [rbp+var_48]
0x18001cdb9  cmp     ax, cx
0x18001cdbc  jnz     short loc_18001CDF9
0x18001cdbe  add     r15d, 2
0x18001cdc2  cmp     cx, 0Ah
0x18001cdc6  jnz     short loc_18001CDE2
0x18001cdc8  mov     ecx, 0Dh; Character
0x18001cdcd  call    _putwch_nolock
0x18001cdd2  mov     ecx, 0Dh
0x18001cdd7  cmp     ax, cx
0x18001cdda  jnz     short loc_18001CDF9
0x18001cddc  inc     r15d
0x18001cddf  inc     r14d
0x18001cde2  add     rdi, 2
0x18001cde6  cmp     rdi, r12
0x18001cde9  jb      short loc_18001CDA6
0x18001cdeb  xor     edi, edi
0x18001cded  mov     [rbp+var_38], edi
0x18001cdf0  mov     [rbp+var_38+4], r15d
0x18001cdf4  jmp     loc_18001CED1
0x18001cdf9  call    cs:__imp_GetLastError
0x18001cdff  mov     edi, eax
0x18001ce01  jmp     short loc_18001CDED
0x18001ce03  mov     r9d, r12d
0x18001ce06  mov     [rsp+78h+lpOverlapped], rbx
0x18001ce0b  mov     r8, rsi
0x18001ce0e  lea     rcx, [rbp+NumberOfBytesWritten]
0x18001ce12  mov     edx, r15d
0x18001ce15  call    write_double_translated_ansi_nolock
0x18001ce1a  movsd   xmm0, qword ptr [rax]
0x18001ce1e  mov     r14d, [rax+8]
0x18001ce22  jmp     loc_18001CEC8
0x18001ce27  mov     rdx, [rbp+var_40]
0x18001ce2b  lea     r8, __pioinfo
0x18001ce32  mov     rcx, [r8+rdx*8]
0x18001ce36  cmp     [rcx+r13*8+38h], dil
0x18001ce3b  jge     short loc_18001CE8F
0x18001ce3d  movsx   ecx, byte ptr [rbp+var_48]
0x18001ce41  test    ecx, ecx
0x18001ce43  jz      short loc_18001CE7B
0x18001ce45  sub     ecx, 1
0x18001ce48  jz      short loc_18001CE67
0x18001ce4a  cmp     ecx, 1
0x18001ce4d  jnz     loc_18001CEDC
0x18001ce53  mov     r9d, r12d
0x18001ce56  lea     rcx, [rbp+NumberOfBytesWritten]
0x18001ce5a  mov     r8, rsi
0x18001ce5d  mov     edx, r15d
0x18001ce60  call    write_text_utf16le_nolock
0x18001ce65  jmp     short loc_18001CE1A
0x18001ce67  mov     r9d, r12d
0x18001ce6a  lea     rcx, [rbp+NumberOfBytesWritten]
0x18001ce6e  mov     r8, rsi
0x18001ce71  mov     edx, r15d
0x18001ce74  call    write_text_utf8_nolock
0x18001ce79  jmp     short loc_18001CE1A
0x18001ce7b  mov     r9d, r12d
0x18001ce7e  lea     rcx, [rbp+NumberOfBytesWritten]
0x18001ce82  mov     r8, rsi
0x18001ce85  mov     edx, r15d
0x18001ce88  call    write_text_ansi_nolock
0x18001ce8d  jmp     short loc_18001CE1A
0x18001ce8f  mov     rcx, [rcx+r13*8+28h]; hFile
0x18001ce94  lea     r9, [rbp+NumberOfBytesWritten+4]; lpNumberOfBytesWritten
0x18001ce98  xor     eax, eax
0x18001ce9a  mov     r8d, r12d; nNumberOfBytesToWrite
0x18001ce9d  mov     rdx, rsi; lpBuffer
0x18001cea0  mov     qword ptr [rbp+NumberOfBytesWritten], rax
0x18001cea4  mov     [rbp+var_20], eax
0x18001cea7  mov     [rsp+78h+lpOverlapped], rax; lpOverlapped
0x18001ceac  call    cs:__imp_WriteFile
0x18001ceb2  test    eax, eax
0x18001ceb4  jnz     short loc_18001CEBF
0x18001ceb6  call    cs:__imp_GetLastError
0x18001cebc  mov     [rbp+NumberOfBytesWritten], eax
0x18001cebf  movsd   xmm0, qword ptr [rbp+NumberOfBytesWritten]
0x18001cec4  mov     r14d, [rbp+var_20]
0x18001cec8  movd    edi, xmm0
0x18001cecc  movsd   qword ptr [rbp+var_38], xmm0
0x18001ced1  mov     rdx, [rbp+var_40]
0x18001ced5  lea     r8, __pioinfo
0x18001cedc  mov     rax, qword ptr [rbp+var_38]
0x18001cee0  shr     rax, 20h
0x18001cee4  test    eax, eax
0x18001cee6  jnz     short loc_18001CF43
0x18001cee8  test    edi, edi
0x18001ceea  jz      short loc_18001CF17
0x18001ceec  cmp     edi, 5
0x18001ceef  jnz     short loc_18001CF08
0x18001cef1  mov     byte ptr [rbx+30h], 1
0x18001cef5  mov     dword ptr [rbx+2Ch], 9
0x18001cefc  mov     byte ptr [rbx+38h], 1
0x18001cf00  mov     [rbx+34h], edi
0x18001cf03  jmp     loc_18001CCAC
0x18001cf08  mov     rdx, rbx
0x18001cf0b  mov     ecx, edi
0x18001cf0d  call    __acrt_errno_map_os_error_ptd
0x18001cf12  jmp     loc_18001CCAC
0x18001cf17  mov     rax, [r8+rdx*8]
0x18001cf1b  test    byte ptr [rax+r13*8+38h], 40h
0x18001cf21  jz      short loc_18001CF28
0x18001cf23  cmp     byte ptr [rsi], 1Ah
0x18001cf26  jz      short loc_18001CF4B
0x18001cf28  mov     byte ptr [rbx+30h], 1
0x18001cf2c  mov     dword ptr [rbx+2Ch], 1Ch
0x18001cf33  mov     byte ptr [rbx+38h], 1
0x18001cf37  mov     dword ptr [rbx+34h], 0
0x18001cf3e  jmp     loc_18001CCAC
0x18001cf43  mov     eax, [rbp+var_38+4]
0x18001cf46  sub     eax, r14d
0x18001cf49  jmp     short loc_18001CF4D
0x18001cf4b  xor     eax, eax
0x18001cf4d  add     rsp, 78h
0x18001cf51  pop     r15
0x18001cf53  pop     r14
0x18001cf55  pop     r13
0x18001cf57  pop     r12
0x18001cf59  pop     rdi
0x18001cf5a  pop     rsi
0x18001cf5b  pop     rbx
0x18001cf5c  pop     rbp
0x18001cf5d  retn
```
