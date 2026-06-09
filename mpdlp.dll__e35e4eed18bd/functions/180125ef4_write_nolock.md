# _write_nolock

- ea: `0x180125ef4`
- end: `0x180126223`
- name: `_write_nolock`
- size: `815`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, installer_update`

## callers

- `0x180125dd4`
- `0x180135b50`

## callees

- `0x1801181d0`
- `0x180119350`
- `0x180119568`
- `0x180125510`
- `0x1801259a4`
- `0x180125aac`
- `0x180125bc8`
- `0x180125ef4`
- `0x180135ff0`
- `0x180135ff8`
- `0x180136078`

## import_xrefs

- `KERNEL32!WriteFile` at `0x18012616a`
- `KERNEL32!WriteFile` at `0x18012616a`
- `KERNEL32!GetLastError` at `0x1801260a4`
- `KERNEL32!GetLastError` at `0x180126174`
- `KERNEL32!GetLastError` at `0x1801260a4`
- `KERNEL32!GetLastError` at `0x180126174`
- `KERNEL32!GetConsoleMode` at `0x180126012`
- `KERNEL32!GetConsoleMode` at `0x180126012`

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
0x180125ef4  push    rbp
0x180125ef6  push    rbx
0x180125ef7  push    rsi
0x180125ef8  push    rdi
0x180125ef9  push    r12
0x180125efb  push    r13
0x180125efd  push    r14
0x180125eff  push    r15
0x180125f01  mov     rbp, rsp
0x180125f04  sub     rsp, 68h
0x180125f08  xor     edi, edi
0x180125f0a  mov     r14d, r8d
0x180125f0d  movsxd  r13, ecx
0x180125f10  mov     rbx, r9
0x180125f13  mov     rsi, rdx
0x180125f16  test    r8d, r8d
0x180125f19  jz      loc_180126210
0x180125f1f  test    rdx, rdx
0x180125f22  jnz     short loc_180125F5B
0x180125f24  mov     byte ptr [r9+38h], 1
0x180125f29  xor     r8d, r8d; FileName
0x180125f2c  mov     [r9+34h], edi
0x180125f30  xor     edx, edx; FunctionName
0x180125f32  mov     byte ptr [r9+30h], 1
0x180125f37  xor     ecx, ecx; Expression
0x180125f39  mov     dword ptr [r9+2Ch], 16h
0x180125f41  xor     r9d, r9d; LineNo
0x180125f44  mov     [rsp+68h+var_40], rbx; __crt_cached_ptd_host *
0x180125f49  mov     [rsp+68h+var_48], rdi; uintptr_t
0x180125f4e  call    _invalid_parameter_internal
0x180125f53  or      eax, 0FFFFFFFFh
0x180125f56  jmp     loc_180126212
0x180125f5b  mov     rax, r13
0x180125f5e  lea     rcx, __pioinfo
0x180125f65  and     eax, 3Fh
0x180125f68  mov     r12, r13
0x180125f6b  sar     r12, 6
0x180125f6f  lea     r15, [rax+rax*8]
0x180125f73  mov     rcx, [rcx+r12*8]
0x180125f77  mov     al, [rcx+r15*8+39h]
0x180125f7c  mov     byte ptr [rbp+var_38], al
0x180125f7f  dec     al
0x180125f81  cmp     al, 1
0x180125f83  ja      short loc_180125F8E
0x180125f85  mov     eax, r14d
0x180125f88  not     eax
0x180125f8a  test    al, 1
0x180125f8c  jz      short loc_180125F24
0x180125f8e  test    byte ptr [rcx+r15*8+38h], 20h
0x180125f94  jz      short loc_180125FA4
0x180125f96  xor     edx, edx
0x180125f98  mov     ecx, r13d
0x180125f9b  lea     r8d, [rdx+2]
0x180125f9f  call    _lseeki64_nolock_internal
0x180125fa4  mov     ecx, r13d; FileHandle
0x180125fa7  mov     [rbp+var_20], rdi
0x180125fab  call    _isatty
0x180125fb0  xor     ecx, ecx
0x180125fb2  lea     r8, __pioinfo
0x180125fb9  test    eax, eax
0x180125fbb  jz      loc_1801260DC
0x180125fc1  mov     rax, [r8+r12*8]
0x180125fc5  cmp     [rax+r15*8+38h], cl
0x180125fca  jge     loc_1801260DC
0x180125fd0  cmp     [rbx+28h], cl
0x180125fd3  jnz     short loc_180125FE6
0x180125fd5  mov     rcx, rbx; this
0x180125fd8  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x180125fdd  xor     ecx, ecx
0x180125fdf  lea     r8, __pioinfo
0x180125fe6  mov     rax, [rbx+18h]
0x180125fea  cmp     [rax+138h], rcx
0x180125ff1  jnz     short loc_180126002
0x180125ff3  mov     rax, [r8+r12*8]
0x180125ff7  cmp     [rax+r15*8+39h], cl
0x180125ffc  jz      loc_1801260DC
0x180126002  mov     [rbp+Mode], ecx
0x180126005  lea     rdx, [rbp+Mode]; lpMode
0x180126009  mov     rcx, [r8+r12*8]
0x18012600d  mov     rcx, [rcx+r15*8+28h]; hConsoleHandle
0x180126012  call    cs:__imp_GetConsoleMode
0x180126018  test    eax, eax
0x18012601a  jz      loc_1801260D5
0x180126020  movsx   ecx, byte ptr [rbp+var_38]
0x180126024  test    ecx, ecx
0x180126026  jz      loc_1801260B2
0x18012602c  sub     ecx, 1
0x18012602f  jz      short loc_18012603A
0x180126031  cmp     ecx, 1
0x180126034  jnz     loc_18012618A
0x18012603a  lea     r12, [rsi+r14]
0x18012603e  mov     qword ptr [rbp+NumberOfBytesWritten], rdi
0x180126042  mov     r15, rsi
0x180126045  cmp     rsi, r12
0x180126048  jnb     loc_180126180
0x18012604e  mov     r14d, [rbp+NumberOfBytesWritten+4]
0x180126052  movzx   eax, word ptr [r15]
0x180126056  movzx   ecx, ax; Character
0x180126059  mov     [rbp+var_38], ax
0x18012605d  call    _putwch_nolock
0x180126062  movzx   ecx, [rbp+var_38]
0x180126066  cmp     ax, cx
0x180126069  jnz     short loc_1801260A4
0x18012606b  add     r14d, 2
0x18012606f  mov     [rbp+NumberOfBytesWritten+4], r14d
0x180126073  cmp     cx, 0Ah
0x180126077  jnz     short loc_180126096
0x180126079  mov     ecx, 0Dh; Character
0x18012607e  call    _putwch_nolock
0x180126083  mov     ecx, 0Dh
0x180126088  cmp     ax, cx
0x18012608b  jnz     short loc_1801260A4
0x18012608d  inc     r14d
0x180126090  mov     [rbp+NumberOfBytesWritten+4], r14d
0x180126094  inc     edi
0x180126096  add     r15, 2
0x18012609a  cmp     r15, r12
0x18012609d  jb      short loc_180126052
0x18012609f  jmp     loc_180126180
0x1801260a4  call    cs:__imp_GetLastError
0x1801260aa  mov     [rbp+NumberOfBytesWritten], eax
0x1801260ad  jmp     loc_180126180
0x1801260b2  mov     r9d, r14d
0x1801260b5  mov     [rsp+68h+var_48], rbx
0x1801260ba  mov     r8, rsi
0x1801260bd  lea     rcx, [rbp+NumberOfBytesWritten]
0x1801260c1  mov     edx, r13d
0x1801260c4  call    write_double_translated_ansi_nolock
0x1801260c9  movsd   xmm0, qword ptr [rax]
0x1801260cd  mov     edi, [rax+8]
0x1801260d0  jmp     loc_180126185
0x1801260d5  lea     r8, __pioinfo
0x1801260dc  mov     rcx, r13
0x1801260df  mov     rax, r13
0x1801260e2  sar     rax, 6
0x1801260e6  and     ecx, 3Fh
0x1801260e9  mov     rdx, [r8+rax*8]
0x1801260ed  lea     rcx, [rcx+rcx*8]
0x1801260f1  cmp     [rdx+rcx*8+38h], dil
0x1801260f6  jge     short loc_18012614D
0x1801260f8  movsx   ecx, byte ptr [rbp+var_38]
0x1801260fc  test    ecx, ecx
0x1801260fe  jz      short loc_180126136
0x180126100  sub     ecx, 1
0x180126103  jz      short loc_180126122
0x180126105  cmp     ecx, 1
0x180126108  jnz     loc_180126191
0x18012610e  mov     r9d, r14d
0x180126111  lea     rcx, [rbp+NumberOfBytesWritten]
0x180126115  mov     r8, rsi
0x180126118  mov     edx, r13d
0x18012611b  call    write_text_utf16le_nolock
0x180126120  jmp     short loc_1801260C9
0x180126122  mov     r9d, r14d
0x180126125  lea     rcx, [rbp+NumberOfBytesWritten]
0x180126129  mov     r8, rsi
0x18012612c  mov     edx, r13d
0x18012612f  call    write_text_utf8_nolock
0x180126134  jmp     short loc_1801260C9
0x180126136  mov     r9d, r14d
0x180126139  lea     rcx, [rbp+NumberOfBytesWritten]
0x18012613d  mov     r8, rsi
0x180126140  mov     edx, r13d
0x180126143  call    write_text_ansi_nolock
0x180126148  jmp     loc_1801260C9
0x18012614d  mov     rcx, [rdx+rcx*8+28h]; hFile
0x180126152  lea     r9, [rbp+NumberOfBytesWritten+4]; lpNumberOfBytesWritten
0x180126156  xor     eax, eax
0x180126158  mov     rdx, rsi; lpBuffer
0x18012615b  and     [rsp+68h+var_48], rax
0x180126160  mov     r8d, r14d; nNumberOfBytesToWrite
0x180126163  mov     qword ptr [rbp+NumberOfBytesWritten], rax
0x180126167  mov     [rbp+var_28], eax
0x18012616a  call    cs:__imp_WriteFile
0x180126170  test    eax, eax
0x180126172  jnz     short loc_18012617D
0x180126174  call    cs:__imp_GetLastError
0x18012617a  mov     [rbp+NumberOfBytesWritten], eax
0x18012617d  mov     edi, [rbp+var_28]
0x180126180  movsd   xmm0, qword ptr [rbp+NumberOfBytesWritten]
0x180126185  movsd   [rbp+var_20], xmm0
0x18012618a  lea     r8, __pioinfo
0x180126191  mov     rax, [rbp+var_20]
0x180126195  shr     rax, 20h
0x180126199  test    eax, eax
0x18012619b  jnz     short loc_180126209
0x18012619d  mov     eax, dword ptr [rbp+var_20]
0x1801261a0  test    eax, eax
0x1801261a2  jz      short loc_1801261D0
0x1801261a4  cmp     eax, 5
0x1801261a7  jnz     short loc_1801261C0
0x1801261a9  mov     byte ptr [rbx+30h], 1
0x1801261ad  mov     dword ptr [rbx+2Ch], 9
0x1801261b4  mov     byte ptr [rbx+38h], 1
0x1801261b8  mov     [rbx+34h], eax
0x1801261bb  jmp     loc_180125F53
0x1801261c0  mov     ecx, dword ptr [rbp+var_20]
0x1801261c3  mov     rdx, rbx
0x1801261c6  call    __acrt_errno_map_os_error_ptd
0x1801261cb  jmp     loc_180125F53
0x1801261d0  mov     rcx, r13
0x1801261d3  mov     rax, r13
0x1801261d6  sar     rax, 6
0x1801261da  and     ecx, 3Fh
0x1801261dd  mov     rax, [r8+rax*8]
0x1801261e1  lea     rcx, [rcx+rcx*8]
0x1801261e5  test    byte ptr [rax+rcx*8+38h], 40h
0x1801261ea  jz      short loc_1801261F1
0x1801261ec  cmp     byte ptr [rsi], 1Ah
0x1801261ef  jz      short loc_180126210
0x1801261f1  and     dword ptr [rbx+34h], 0
0x1801261f5  mov     byte ptr [rbx+30h], 1
0x1801261f9  mov     dword ptr [rbx+2Ch], 1Ch
0x180126200  mov     byte ptr [rbx+38h], 1
0x180126204  jmp     loc_180125F53
0x180126209  mov     eax, dword ptr [rbp+var_20+4]
0x18012620c  sub     eax, edi
0x18012620e  jmp     short loc_180126212
0x180126210  xor     eax, eax
0x180126212  add     rsp, 68h
0x180126216  pop     r15
0x180126218  pop     r14
0x18012621a  pop     r13
0x18012621c  pop     r12
0x18012621e  pop     rdi
0x18012621f  pop     rsi
0x180126220  pop     rbx
0x180126221  pop     rbp
0x180126222  retn
```
