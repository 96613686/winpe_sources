# std::sys::stdio::windows::write_valid_utf8_to_console

- ea: `0x1800d7440`
- end: `0x1800d76c0`
- name: `std::sys::stdio::windows::write_valid_utf8_to_console`
- size: `640`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800d7060`

## callees

- `0x1800d7440`
- `0x180225390`
- `0x1803168c1`
- `0x180316940`
- `0x180316a30`

## import_xrefs

- `kernel32!GetLastError` at `0x1800d753e`
- `kernel32!GetLastError` at `0x1800d7600`
- `kernel32!GetLastError` at `0x1800d753e`
- `kernel32!GetLastError` at `0x1800d7600`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800d748f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800d748f`
- `api-ms-win-core-console-l1-1-0!WriteConsoleW` at `0x1800d74cf`
- `api-ms-win-core-console-l1-1-0!WriteConsoleW` at `0x1800d7534`
- `api-ms-win-core-console-l1-1-0!WriteConsoleW` at `0x1800d74cf`
- `api-ms-win-core-console-l1-1-0!WriteConsoleW` at `0x1800d7534`

## pseudocode

```c
__int64 __fastcall std::sys::stdio::windows::write_valid_utf8_to_console(void *a1, const CHAR *a2, unsigned __int64 a3)
{
  __int64 v3; // rsi
  signed int v5; // eax
  unsigned __int64 v6; // r14
  unsigned __int64 v7; // rbx
  WCHAR *v8; // rdx
  __int64 v9; // rbx
  unsigned __int64 v10; // rax
  __int64 v11; // rsi
  unsigned int v12; // ecx
  __int64 v13; // rdx
  WCHAR WideCharStr[4096]; // [rsp+30h] [rbp-50h] BYREF
  DWORD NumberOfCharsWritten[2]; // [rsp+2030h] [rbp+1FB0h] BYREF
  __int64 v17; // [rsp+2038h] [rbp+1FB8h]
  __int64 v18; // [rsp+2040h] [rbp+1FC0h]
  __int128 v19; // [rsp+2048h] [rbp+1FC8h]

  LODWORD(v3) = a3;
  if ( a3 >= 0x1001 )
  {
    v3 = 4096;
    while ( a2[v3] <= -65 )
    {
      if ( a2[v3 - 1] > -65 )
      {
        LODWORD(v3) = v3 - 1;
        break;
      }
      if ( a2[v3 - 2] > -65 )
      {
        LODWORD(v3) = v3 - 2;
        break;
      }
      if ( a2[v3 - 3] > -65 )
      {
        LODWORD(v3) = v3 - 3;
        break;
      }
      v3 -= 4;
      if ( !v3 )
      {
        LODWORD(v3) = 0;
        break;
      }
    }
  }
  v5 = MultiByteToWideChar(0xFDE9u, 8u, a2, v3, WideCharStr, 4096);
  if ( !v5 )
  {
    *(_QWORD *)NumberOfCharsWritten = &off_180343BE0;
    v17 = 1;
    v18 = 8;
    v19 = 0;
    core::panicking::panic_fmt(NumberOfCharsWritten, &off_180343BF0);
  }
  v6 = v5;
  if ( (unsigned int)v5 >= 0x1001 )
    core::slice::index::slice_end_index_len_fail(v5, 4096, &off_180343C08);
  NumberOfCharsWritten[0] = 0;
  if ( WriteConsoleW(a1, WideCharStr, v5, NumberOfCharsWritten, 0) )
  {
    v7 = NumberOfCharsWritten[0];
    if ( v6 != NumberOfCharsWritten[0] )
    {
      if ( v6 <= NumberOfCharsWritten[0] )
        core::panicking::panic_bounds_check(NumberOfCharsWritten[0], v6, &off_180343C20);
      if ( (unsigned __int16)(WideCharStr[NumberOfCharsWritten[0]] + 8978) < 0x312u )
      {
        v8 = &WideCharStr[NumberOfCharsWritten[0]];
        NumberOfCharsWritten[0] = 0;
        if ( !WriteConsoleW(a1, v8, 1u, NumberOfCharsWritten, 0) )
          GetLastError();
        ++v7;
      }
      if ( v7 > v6 )
        core::slice::index::slice_end_index_len_fail(v7, v6, &off_180343C38);
      if ( v7 )
      {
        v9 = 2 * v7;
        v10 = 0;
        v11 = 0;
        do
        {
          v12 = WideCharStr[v10 / 2];
          v13 = 1;
          if ( v12 >= 0x80 )
          {
            v13 = 2;
            if ( (unsigned __int16)v12 >= 0x800u )
              v13 = 2LL * ((unsigned __int16)(v12 + 8978) >= 0x312u) + 1;
          }
          v11 += v13;
          v10 += 2LL;
        }
        while ( v9 != v10 );
      }
    }
    return 0;
  }
  else
  {
    GetLastError();
    return 1;
  }
}

```

## disassembly

```asm
0x1800d7440  push    rbp
0x1800d7441  push    r14
0x1800d7443  push    rsi
0x1800d7444  push    rdi
0x1800d7445  push    rbx
0x1800d7446  mov     eax, 2060h
0x1800d744b  call    _alloca_probe
0x1800d7450  sub     rsp, rax
0x1800d7453  lea     rbp, [rsp+80h]
0x1800d745b  mov     rsi, r8
0x1800d745e  mov     r8, rdx; lpMultiByteStr
0x1800d7461  mov     rdi, rcx
0x1800d7464  cmp     rsi, 1001h
0x1800d746b  jnb     loc_1800D75C2
0x1800d7471  lea     rax, [rbp+2000h+WideCharStr]
0x1800d7475  mov     [rsp+2080h+lpWideCharStr], rax; lpWideCharStr
0x1800d747a  mov     [rsp+2080h+cchWideChar], 1000h; cchWideChar
0x1800d7482  mov     ecx, 0FDE9h; CodePage
0x1800d7487  mov     edx, 8; dwFlags
0x1800d748c  mov     r9d, esi; cbMultiByte
0x1800d748f  call    cs:__imp_MultiByteToWideChar
0x1800d7495  test    eax, eax
0x1800d7497  jz      loc_1800D7646
0x1800d749d  movsxd  r14, eax
0x1800d74a0  cmp     eax, 1001h
0x1800d74a5  jnb     loc_1800D7687
0x1800d74ab  mov     [rbp+2000h+NumberOfCharsWritten], 0
0x1800d74b5  mov     [rsp+2080h+lpWideCharStr], 0; lpReserved
0x1800d74be  lea     rdx, [rbp+2000h+WideCharStr]; lpBuffer
0x1800d74c2  lea     r9, [rbp+2000h+NumberOfCharsWritten]; lpNumberOfCharsWritten
0x1800d74c9  mov     rcx, rdi; hConsoleOutput
0x1800d74cc  mov     r8d, eax; nNumberOfCharsToWrite
0x1800d74cf  call    cs:__imp_WriteConsoleW
0x1800d74d5  test    eax, eax
0x1800d74d7  jz      loc_1800D7600
0x1800d74dd  mov     ebx, [rbp+2000h+NumberOfCharsWritten]
0x1800d74e3  cmp     r14, rbx
0x1800d74e6  jz      loc_1800D7619
0x1800d74ec  jbe     loc_1800D76AD
0x1800d74f2  movzx   eax, [rbp+rbx*2+2000h+WideCharStr]
0x1800d74f7  add     eax, 2312h
0x1800d74fc  movzx   eax, ax
0x1800d74ff  cmp     eax, 312h
0x1800d7504  jnb     short loc_1800D7547
0x1800d7506  lea     rdx, ds:0FFFFFFFFFFFFFFB0h[rbx*2]
0x1800d750e  add     rdx, rbp; lpBuffer
0x1800d7511  mov     [rbp+2000h+NumberOfCharsWritten], 0
0x1800d751b  mov     [rsp+2080h+lpWideCharStr], 0; lpReserved
0x1800d7524  lea     r9, [rbp+2000h+NumberOfCharsWritten]; lpNumberOfCharsWritten
0x1800d752b  mov     rcx, rdi; hConsoleOutput
0x1800d752e  mov     r8d, 1; nNumberOfCharsToWrite
0x1800d7534  call    cs:__imp_WriteConsoleW
0x1800d753a  test    eax, eax
0x1800d753c  jnz     short loc_1800D7544
0x1800d753e  call    cs:__imp_GetLastError
0x1800d7544  inc     rbx
0x1800d7547  cmp     rbx, r14
0x1800d754a  ja      loc_1800D769B
0x1800d7550  test    rbx, rbx
0x1800d7553  jz      loc_1800D7617
0x1800d7559  add     rbx, rbx
0x1800d755c  xor     eax, eax
0x1800d755e  xor     esi, esi
0x1800d7560  jmp     short loc_1800D7580
0x1800d7570  add     rsi, rdx
0x1800d7573  add     rax, 2
0x1800d7577  cmp     rbx, rax
0x1800d757a  jz      loc_1800D7619
0x1800d7580  movzx   ecx, [rbp+rax+2000h+WideCharStr]
0x1800d7585  mov     edx, 1
0x1800d758a  cmp     ecx, 80h
0x1800d7590  jb      short loc_1800D7570
0x1800d7592  movzx   r8d, cx
0x1800d7596  mov     edx, 2
0x1800d759b  cmp     r8d, 800h
0x1800d75a2  jb      short loc_1800D7570
0x1800d75a4  add     ecx, 2312h
0x1800d75aa  movzx   ecx, cx
0x1800d75ad  xor     edx, edx
0x1800d75af  cmp     ecx, 312h
0x1800d75b5  setnb   dl
0x1800d75b8  lea     rdx, ds:1[rdx*2]
0x1800d75c0  jmp     short loc_1800D7570
0x1800d75c2  mov     esi, 1000h
0x1800d75c7  nop     word ptr [rax+rax+00000000h]
0x1800d75d0  cmp     byte ptr [r8+rsi], 0BFh
0x1800d75d5  jg      loc_1800D7471
0x1800d75db  cmp     byte ptr [r8+rsi-1], 0BFh
0x1800d75e1  jg      short loc_1800D762C
0x1800d75e3  cmp     byte ptr [r8+rsi-2], 0BFh
0x1800d75e9  jg      short loc_1800D7634
0x1800d75eb  cmp     byte ptr [r8+rsi-3], 0BFh
0x1800d75f1  jg      short loc_1800D763D
0x1800d75f3  add     rsi, 0FFFFFFFFFFFFFFFCh
0x1800d75f7  jnz     short loc_1800D75D0
0x1800d75f9  xor     esi, esi
0x1800d75fb  jmp     loc_1800D7471
0x1800d7600  call    cs:__imp_GetLastError
0x1800d7606  mov     esi, eax
0x1800d7608  shl     rsi, 20h
0x1800d760c  or      rsi, 2
0x1800d7610  mov     eax, 1
0x1800d7615  jmp     short loc_1800D761B
0x1800d7617  xor     esi, esi
0x1800d7619  xor     eax, eax
0x1800d761b  mov     rdx, rsi
0x1800d761e  add     rsp, 2060h
0x1800d7625  pop     rbx
0x1800d7626  pop     rdi
0x1800d7627  pop     rsi
0x1800d7628  pop     r14
0x1800d762a  pop     rbp
0x1800d762b  retn
0x1800d762c  dec     rsi
0x1800d762f  jmp     loc_1800D7471
0x1800d7634  add     rsi, 0FFFFFFFFFFFFFFFEh
0x1800d7638  jmp     loc_1800D7471
0x1800d763d  add     rsi, 0FFFFFFFFFFFFFFFDh
0x1800d7641  jmp     loc_1800D7471
0x1800d7646  lea     rax, off_180343BE0; "Unexpected error in MultiByteToWideChar"...
0x1800d764d  mov     qword ptr [rbp+2000h+NumberOfCharsWritten], rax
0x1800d7654  mov     [rbp+2000h+var_48], 1
0x1800d765f  mov     [rbp+2000h+var_40], 8
0x1800d766a  xorps   xmm0, xmm0
0x1800d766d  movups  [rbp+2000h+var_38], xmm0
0x1800d7674  lea     rdx, off_180343BF0; "library\\std\\src\\sys\\stdio\\windows."...
0x1800d767b  lea     rcx, [rbp+2000h+NumberOfCharsWritten]
0x1800d7682  call    core__panicking__panic_fmt
0x1800d7687  lea     r8, off_180343C08; "library\\std\\src\\sys\\stdio\\windows."...
0x1800d768e  mov     edx, 1000h
0x1800d7693  mov     rcx, r14
0x1800d7696  call    core__slice__index__slice_end_index_len_fail
0x1800d769b  lea     r8, off_180343C38; "library\\std\\src\\sys\\stdio\\windows."...
0x1800d76a2  mov     rcx, rbx
0x1800d76a5  mov     rdx, r14
0x1800d76a8  call    core__slice__index__slice_end_index_len_fail
0x1800d76ad  lea     r8, off_180343C20; "library\\std\\src\\sys\\stdio\\windows."...
0x1800d76b4  mov     rcx, rbx
0x1800d76b7  mov     rdx, r14
0x1800d76ba  call    core__panicking__panic_bounds_check
```
