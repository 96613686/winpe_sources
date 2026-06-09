# _write_nolock

- ea: `0x18000fb8c`
- end: `0x18000fe9e`
- name: `_write_nolock`
- size: `786`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, installer_update`

## callers

- `0x18000fa64`

## callees

- `0x180005ac0`
- `0x1800063f4`
- `0x180006780`
- `0x18000d590`
- `0x18000f1ac`
- `0x18000f6a4`
- `0x18000f7b8`
- `0x18000f8e0`
- `0x18000fb8c`
- `0x18000ff44`
- `0x180010b00`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000fd39`
- `KERNEL32!GetLastError` at `0x18000fdf6`
- `KERNEL32!GetLastError` at `0x18000fd39`
- `KERNEL32!GetLastError` at `0x18000fdf6`
- `KERNEL32!WriteFile` at `0x18000fdec`
- `KERNEL32!WriteFile` at `0x18000fdec`
- `KERNEL32!GetConsoleMode` at `0x18000fcb4`
- `KERNEL32!GetConsoleMode` at `0x18000fcb4`

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
0x18000fb8c  push    rbp
0x18000fb8e  push    rbx
0x18000fb8f  push    rsi
0x18000fb90  push    rdi
0x18000fb91  push    r12
0x18000fb93  push    r13
0x18000fb95  push    r14
0x18000fb97  push    r15
0x18000fb99  mov     rbp, rsp
0x18000fb9c  sub     rsp, 78h
0x18000fba0  xor     r14d, r14d
0x18000fba3  mov     r12d, r8d
0x18000fba6  movsxd  r15, ecx
0x18000fba9  mov     rbx, r9
0x18000fbac  mov     rsi, rdx
0x18000fbaf  test    r8d, r8d
0x18000fbb2  jz      loc_18000FE8B
0x18000fbb8  test    rdx, rdx
0x18000fbbb  jnz     short loc_18000FBF4
0x18000fbbd  mov     byte ptr [r9+38h], 1
0x18000fbc2  xor     r8d, r8d; FileName
0x18000fbc5  mov     [r9+34h], r14d
0x18000fbc9  xor     edx, edx; FunctionName
0x18000fbcb  mov     byte ptr [r9+30h], 1
0x18000fbd0  xor     ecx, ecx; Expression
0x18000fbd2  mov     dword ptr [r9+2Ch], 16h
0x18000fbda  xor     r9d, r9d; LineNo
0x18000fbdd  mov     qword ptr [rsp+78h+dwErrCode], rbx; dwErrCode
0x18000fbe2  mov     [rsp+78h+lpOverlapped], r14; uintptr_t
0x18000fbe7  call    _invalid_parameter_internal
0x18000fbec  or      eax, 0FFFFFFFFh
0x18000fbef  jmp     loc_18000FE8D
0x18000fbf4  mov     eax, r15d
0x18000fbf7  lea     rdx, __pioinfo
0x18000fbfe  and     eax, 3Fh
0x18000fc01  mov     rcx, r15
0x18000fc04  sar     rcx, 6
0x18000fc08  mov     [rbp+var_40], rcx
0x18000fc0c  lea     r13, [rax+rax*8]
0x18000fc10  mov     rdx, [rdx+rcx*8]
0x18000fc14  mov     al, [rdx+r13*8+39h]
0x18000fc19  mov     byte ptr [rbp+var_48], al
0x18000fc1c  dec     al
0x18000fc1e  cmp     al, 1
0x18000fc20  ja      short loc_18000FC28
0x18000fc22  test    r12b, 1
0x18000fc26  jnz     short loc_18000FBBD
0x18000fc28  test    byte ptr [rdx+r13*8+38h], 20h
0x18000fc2e  jz      short loc_18000FC3E
0x18000fc30  xor     edx, edx
0x18000fc32  mov     ecx, r15d
0x18000fc35  lea     r8d, [rdx+2]
0x18000fc39  call    _lseeki64_nolock_internal
0x18000fc3e  mov     ecx, r15d; FileHandle
0x18000fc41  mov     qword ptr [rbp+var_38], r14
0x18000fc45  mov     edi, r14d
0x18000fc48  call    _isatty
0x18000fc4d  mov     rdx, [rbp+var_40]
0x18000fc51  lea     r8, __pioinfo
0x18000fc58  test    eax, eax
0x18000fc5a  jz      loc_18000FD72
0x18000fc60  mov     rax, [r8+rdx*8]
0x18000fc64  cmp     [rax+r13*8+38h], dil
0x18000fc69  jge     loc_18000FD72
0x18000fc6f  cmp     [rbx+28h], dil
0x18000fc73  jnz     short loc_18000FC88
0x18000fc75  mov     rcx, rbx; this
0x18000fc78  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x18000fc7d  mov     rdx, [rbp+var_40]
0x18000fc81  lea     r8, __pioinfo
0x18000fc88  mov     rax, [rbx+18h]
0x18000fc8c  cmp     [rax+138h], rdi
0x18000fc93  jnz     short loc_18000FCA4
0x18000fc95  mov     rax, [r8+rdx*8]
0x18000fc99  cmp     [rax+r13*8+39h], dil
0x18000fc9e  jz      loc_18000FD72
0x18000fca4  mov     rcx, [r8+rdx*8]
0x18000fca8  lea     rdx, [rbp+Mode]; lpMode
0x18000fcac  mov     [rbp+Mode], edi
0x18000fcaf  mov     rcx, [rcx+r13*8+28h]; hConsoleHandle
0x18000fcb4  call    cs:__imp_GetConsoleMode
0x18000fcba  test    eax, eax
0x18000fcbc  jz      loc_18000FD67
0x18000fcc2  movsx   ecx, byte ptr [rbp+var_48]
0x18000fcc6  test    ecx, ecx
0x18000fcc8  jz      short loc_18000FD43
0x18000fcca  sub     ecx, 1
0x18000fccd  jz      short loc_18000FCD8
0x18000fccf  cmp     ecx, 1
0x18000fcd2  jnz     loc_18000FE11
0x18000fcd8  xor     r15d, r15d
0x18000fcdb  add     r12, rsi
0x18000fcde  mov     rdi, rsi
0x18000fce1  cmp     rsi, r12
0x18000fce4  jnb     short loc_18000FD2B
0x18000fce6  movzx   eax, word ptr [rdi]
0x18000fce9  movzx   ecx, ax; Character
0x18000fcec  mov     [rbp+var_48], ax
0x18000fcf0  call    _putwch_nolock
0x18000fcf5  movzx   ecx, [rbp+var_48]
0x18000fcf9  cmp     ax, cx
0x18000fcfc  jnz     short loc_18000FD39
0x18000fcfe  add     r15d, 2
0x18000fd02  cmp     cx, 0Ah
0x18000fd06  jnz     short loc_18000FD22
0x18000fd08  mov     ecx, 0Dh; Character
0x18000fd0d  call    _putwch_nolock
0x18000fd12  mov     ecx, 0Dh
0x18000fd17  cmp     ax, cx
0x18000fd1a  jnz     short loc_18000FD39
0x18000fd1c  inc     r15d
0x18000fd1f  inc     r14d
0x18000fd22  add     rdi, 2
0x18000fd26  cmp     rdi, r12
0x18000fd29  jb      short loc_18000FCE6
0x18000fd2b  xor     edi, edi
0x18000fd2d  mov     [rbp+var_38], edi
0x18000fd30  mov     [rbp+var_38+4], r15d
0x18000fd34  jmp     loc_18000FE11
0x18000fd39  call    cs:__imp_GetLastError
0x18000fd3f  mov     edi, eax
0x18000fd41  jmp     short loc_18000FD2D
0x18000fd43  mov     r9d, r12d
0x18000fd46  mov     [rsp+78h+lpOverlapped], rbx
0x18000fd4b  mov     r8, rsi
0x18000fd4e  lea     rcx, [rbp+NumberOfBytesWritten]
0x18000fd52  mov     edx, r15d
0x18000fd55  call    write_double_translated_ansi_nolock
0x18000fd5a  movsd   xmm0, qword ptr [rax]
0x18000fd5e  mov     r14d, [rax+8]
0x18000fd62  jmp     loc_18000FE08
0x18000fd67  mov     rdx, [rbp+var_40]
0x18000fd6b  lea     r8, __pioinfo
0x18000fd72  mov     rcx, [r8+rdx*8]
0x18000fd76  cmp     [rcx+r13*8+38h], dil
0x18000fd7b  jge     short loc_18000FDCF
0x18000fd7d  movsx   ecx, byte ptr [rbp+var_48]
0x18000fd81  test    ecx, ecx
0x18000fd83  jz      short loc_18000FDBB
0x18000fd85  sub     ecx, 1
0x18000fd88  jz      short loc_18000FDA7
0x18000fd8a  cmp     ecx, 1
0x18000fd8d  jnz     loc_18000FE1C
0x18000fd93  mov     r9d, r12d
0x18000fd96  lea     rcx, [rbp+NumberOfBytesWritten]
0x18000fd9a  mov     r8, rsi
0x18000fd9d  mov     edx, r15d
0x18000fda0  call    write_text_utf16le_nolock
0x18000fda5  jmp     short loc_18000FD5A
0x18000fda7  mov     r9d, r12d
0x18000fdaa  lea     rcx, [rbp+NumberOfBytesWritten]
0x18000fdae  mov     r8, rsi
0x18000fdb1  mov     edx, r15d
0x18000fdb4  call    write_text_utf8_nolock
0x18000fdb9  jmp     short loc_18000FD5A
0x18000fdbb  mov     r9d, r12d
0x18000fdbe  lea     rcx, [rbp+NumberOfBytesWritten]
0x18000fdc2  mov     r8, rsi
0x18000fdc5  mov     edx, r15d
0x18000fdc8  call    write_text_ansi_nolock
0x18000fdcd  jmp     short loc_18000FD5A
0x18000fdcf  mov     rcx, [rcx+r13*8+28h]; hFile
0x18000fdd4  lea     r9, [rbp+NumberOfBytesWritten+4]; lpNumberOfBytesWritten
0x18000fdd8  xor     eax, eax
0x18000fdda  mov     r8d, r12d; nNumberOfBytesToWrite
0x18000fddd  mov     rdx, rsi; lpBuffer
0x18000fde0  mov     qword ptr [rbp+NumberOfBytesWritten], rax
0x18000fde4  mov     [rbp+var_20], eax
0x18000fde7  mov     [rsp+78h+lpOverlapped], rax; lpOverlapped
0x18000fdec  call    cs:__imp_WriteFile
0x18000fdf2  test    eax, eax
0x18000fdf4  jnz     short loc_18000FDFF
0x18000fdf6  call    cs:__imp_GetLastError
0x18000fdfc  mov     [rbp+NumberOfBytesWritten], eax
0x18000fdff  movsd   xmm0, qword ptr [rbp+NumberOfBytesWritten]
0x18000fe04  mov     r14d, [rbp+var_20]
0x18000fe08  movd    edi, xmm0
0x18000fe0c  movsd   qword ptr [rbp+var_38], xmm0
0x18000fe11  mov     rdx, [rbp+var_40]
0x18000fe15  lea     r8, __pioinfo
0x18000fe1c  mov     rax, qword ptr [rbp+var_38]
0x18000fe20  shr     rax, 20h
0x18000fe24  test    eax, eax
0x18000fe26  jnz     short loc_18000FE83
0x18000fe28  test    edi, edi
0x18000fe2a  jz      short loc_18000FE57
0x18000fe2c  cmp     edi, 5
0x18000fe2f  jnz     short loc_18000FE48
0x18000fe31  mov     byte ptr [rbx+30h], 1
0x18000fe35  mov     dword ptr [rbx+2Ch], 9
0x18000fe3c  mov     byte ptr [rbx+38h], 1
0x18000fe40  mov     [rbx+34h], edi
0x18000fe43  jmp     loc_18000FBEC
0x18000fe48  mov     rdx, rbx
0x18000fe4b  mov     ecx, edi
0x18000fe4d  call    __acrt_errno_map_os_error_ptd
0x18000fe52  jmp     loc_18000FBEC
0x18000fe57  mov     rax, [r8+rdx*8]
0x18000fe5b  test    byte ptr [rax+r13*8+38h], 40h
0x18000fe61  jz      short loc_18000FE68
0x18000fe63  cmp     byte ptr [rsi], 1Ah
0x18000fe66  jz      short loc_18000FE8B
0x18000fe68  mov     byte ptr [rbx+30h], 1
0x18000fe6c  mov     dword ptr [rbx+2Ch], 1Ch
0x18000fe73  mov     byte ptr [rbx+38h], 1
0x18000fe77  mov     dword ptr [rbx+34h], 0
0x18000fe7e  jmp     loc_18000FBEC
0x18000fe83  mov     eax, [rbp+var_38+4]
0x18000fe86  sub     eax, r14d
0x18000fe89  jmp     short loc_18000FE8D
0x18000fe8b  xor     eax, eax
0x18000fe8d  add     rsp, 78h
0x18000fe91  pop     r15
0x18000fe93  pop     r14
0x18000fe95  pop     r13
0x18000fe97  pop     r12
0x18000fe99  pop     rdi
0x18000fe9a  pop     rsi
0x18000fe9b  pop     rbx
0x18000fe9c  pop     rbp
0x18000fe9d  retn
```
