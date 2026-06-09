# _read_nolock

- ea: `0x180124f9c`
- end: `0x1801253fb`
- name: `_read_nolock`
- size: `1119`
- prototype: ``
- caller_count: `4`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x180123d0c`
- `0x1801241a0`
- `0x180124e7c`
- `0x1801277c4`

## callees

- `0x180119408`
- `0x180119540`
- `0x18011958c`
- `0x1801195b0`
- `0x180124950`
- `0x180124b4c`
- `0x180124f9c`
- `0x18012c990`
- `0x18012c9f0`
- `0x180135f54`
- `0x180135ff8`

## import_xrefs

- `KERNEL32!ReadFile` at `0x18012528d`
- `KERNEL32!ReadFile` at `0x18012528d`
- `KERNEL32!GetLastError` at `0x18012523e`
- `KERNEL32!GetLastError` at `0x18012538f`
- `KERNEL32!GetLastError` at `0x18012523e`
- `KERNEL32!GetLastError` at `0x18012538f`
- `KERNEL32!GetConsoleMode` at `0x1801251ff`
- `KERNEL32!GetConsoleMode` at `0x1801251ff`
- `KERNEL32!ReadConsoleW` at `0x180125234`
- `KERNEL32!ReadConsoleW` at `0x180125234`

## pseudocode

```c
__int64 __fastcall read_nolock(int a1, __int16 *a2, unsigned int a3)
{
  unsigned __int64 v4; // r12
  unsigned __int64 v5; // r8
  __int64 v6; // rax
  __int16 *v7; // rbx
  int v8; // r10d
  DWORD v9; // ebp
  __int16 *v10; // r15
  __int64 v11; // rax
  __int64 v12; // rax
  int v13; // edi
  char v14; // al
  char v15; // cl
  char v16; // cl
  DWORD LastError; // eax
  int v18; // edi
  unsigned __int64 v20; // rdx
  int v21; // eax
  unsigned __int64 v22; // r8
  __int16 *v23; // r10
  __int16 *v24; // rax
  __int16 *v25; // rdi
  unsigned __int64 v26; // r9
  __int16 v27; // cx
  __int64 v28; // r11
  DWORD Mode; // [rsp+30h] [rbp-68h] BYREF
  HANDLE hConsoleHandle; // [rsp+38h] [rbp-60h]
  unsigned __int64 v31; // [rsp+40h] [rbp-58h]
  __int64 v32; // [rsp+48h] [rbp-50h]
  __int16 *v33; // [rsp+50h] [rbp-48h]
  char v34; // [rsp+A0h] [rbp+8h]
  int v35; // [rsp+A8h] [rbp+10h]
  DWORD NumberOfCharsRead; // [rsp+B8h] [rbp+20h] BYREF

  v35 = (int)a2;
  v4 = a3;
  if ( a1 != -2 )
  {
    if ( a1 >= 0
      && a1 < (unsigned int)nhandle
      && (v32 = 1,
          v5 = (unsigned __int64)a1 >> 6,
          v31 = v5,
          v6 = _pioinfo[v5],
          (*(_BYTE *)(v6 + 72LL * (a1 & 0x3F) + 56) & 1) != 0) )
    {
      if ( (unsigned int)v4 <= 0x7FFFFFFF )
      {
        if ( !(_DWORD)v4 || (*(_BYTE *)(v6 + 72LL * (a1 & 0x3F) + 56) & 2) != 0 )
          return 0;
        if ( a2 )
        {
          v7 = 0;
          v8 = *(char *)(v6 + 72LL * (a1 & 0x3F) + 57);
          hConsoleHandle = *(HANDLE *)(v6 + 72LL * (a1 & 0x3F) + 40);
          v34 = v8;
          if ( v8 == 1 )
          {
            if ( (v4 & 1) != 0 )
            {
LABEL_14:
              *_doserrno() = 0;
              *errno() = 22;
              invalid_parameter_noinfo();
LABEL_38:
              v18 = -1;
              goto LABEL_39;
            }
            v9 = (unsigned int)v4 >> 1;
            if ( (unsigned int)v4 >> 1 < 4 )
              v9 = 4;
            v7 = (__int16 *)malloc_base(v9);
            free_base(0);
            free_base(0);
            v10 = v7;
            if ( !v7 )
            {
              *errno() = 12;
              *_doserrno() = 8;
              goto LABEL_38;
            }
            v11 = lseeki64_nolock((unsigned int)a1, 0, 1);
            v5 = v31;
            LOBYTE(v8) = v34;
            *(_QWORD *)(_pioinfo[v31] + 72LL * (a1 & 0x3F) + 48) = v11;
          }
          else
          {
            if ( v8 == 2 && (v4 & 1) != 0 )
              goto LABEL_14;
            v9 = v4;
            v10 = a2;
          }
          v12 = _pioinfo[v5];
          v13 = 0;
          v33 = v10;
          if ( (*(_BYTE *)(v12 + 72LL * (a1 & 0x3F) + 56) & 0x48) != 0 )
          {
            v14 = *(_BYTE *)(v12 + 72LL * (a1 & 0x3F) + 58);
            if ( v14 != 10 )
            {
              *(_BYTE *)v10 = v14;
              --v9;
              v10 = (__int16 *)((char *)v10 + 1);
              v13 = 1;
              *(_BYTE *)(_pioinfo[v5] + 72LL * (a1 & 0x3F) + 58) = 10;
              if ( (_BYTE)v8 )
              {
                v15 = *(_BYTE *)(_pioinfo[v5] + 72LL * (a1 & 0x3F) + 59);
                if ( v15 != 10 )
                {
                  if ( v9 )
                  {
                    *(_BYTE *)v10 = v15;
                    v13 = 2;
                    v10 = (__int16 *)((char *)v10 + 1);
                    --v9;
                    *(_BYTE *)(_pioinfo[v5] + 72LL * (a1 & 0x3F) + 59) = 10;
                    if ( (_BYTE)v8 == 1 )
                    {
                      v16 = *(_BYTE *)(_pioinfo[v5] + 72LL * (a1 & 0x3F) + 60);
                      if ( v16 != 10 )
                      {
                        if ( v9 )
                        {
                          *(_BYTE *)v10 = v16;
                          v13 = 3;
                          v10 = (__int16 *)((char *)v10 + 1);
                          --v9;
                          *(_BYTE *)(_pioinfo[v5] + 72LL * (a1 & 0x3F) + 60) = 10;
                        }
                      }
                    }
                  }
                }
              }
            }
          }
          Mode = 0;
          if ( isatty(a1)
            && *(char *)(_pioinfo[v31] + 72LL * (a1 & 0x3F) + 56) < 0
            && GetConsoleMode(hConsoleHandle, &Mode) )
          {
            if ( v34 == 2 )
            {
              NumberOfCharsRead = 0;
              if ( !ReadConsoleW(hConsoleHandle, v10, v9 >> 1, &NumberOfCharsRead, 0) )
              {
                LastError = GetLastError();
LABEL_37:
                _acrt_errno_map_os_error(LastError);
                goto LABEL_38;
              }
              v18 = v13 + 2 * NumberOfCharsRead;
              goto LABEL_45;
            }
          }
          else
          {
            LOBYTE(v32) = 0;
          }
          NumberOfCharsRead = 0;
          if ( !ReadFile(hConsoleHandle, v10, v9, &NumberOfCharsRead, 0) || NumberOfCharsRead > (unsigned int)v4 )
          {
            LastError = GetLastError();
            if ( LastError == 5 )
            {
              *errno() = 9;
              *_doserrno() = 5;
              goto LABEL_38;
            }
            if ( LastError == 109 )
            {
              v18 = 0;
              goto LABEL_39;
            }
            goto LABEL_37;
          }
          v18 = NumberOfCharsRead + v13;
LABEL_45:
          v20 = v31;
          if ( *(char *)(_pioinfo[v31] + 72LL * (a1 & 0x3F) + 56) < 0 )
          {
            if ( v34 == 2 )
            {
              v22 = (unsigned __int64)v18 >> 1;
              if ( (_BYTE)v32 )
              {
                v23 = v33;
                v24 = v33;
                v25 = v33;
                v26 = (unsigned __int64)&v33[v22];
                if ( (unsigned __int64)v33 < v26 )
                {
                  while ( 1 )
                  {
                    v27 = *v24;
                    if ( *v24 == 26 )
                      break;
                    if ( v27 == 13 && (unsigned __int64)(v24 + 1) < v26 && v24[1] == 10 )
                    {
                      v27 = 10;
                      v28 = 4;
                    }
                    else
                    {
                      v28 = 2;
                    }
                    v24 = (__int16 *)((char *)v24 + v28);
                    *v25++ = v27;
                    if ( (unsigned __int64)v24 >= v26 )
                      goto LABEL_60;
                  }
                  *(_BYTE *)(_pioinfo[v20] + 72LL * (a1 & 0x3F) + 56) |= 2u;
                }
LABEL_60:
                v18 = 2 * (v25 - v23);
                goto LABEL_39;
              }
              v21 = translate_text_mode_nolock_wchar_t_((unsigned int)a1, v33, v22);
            }
            else
            {
              v21 = translate_ansi_or_utf8_nolock(a1, (_DWORD)v10, v18, v35, v4 >> 1);
            }
            v18 = v21;
          }
LABEL_39:
          free_base(v7);
          return (unsigned int)v18;
        }
      }
      *_doserrno() = 0;
      *errno() = 22;
    }
    else
    {
      *_doserrno() = 0;
      *errno() = 9;
    }
    invalid_parameter_noinfo();
    return 0xFFFFFFFFLL;
  }
  *_doserrno() = 0;
  *errno() = 9;
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x180124f9c  mov     [rsp+arg_10], rbx
0x180124fa1  mov     [rsp+arg_8], rdx
0x180124fa6  push    rbp
0x180124fa7  push    rsi
0x180124fa8  push    rdi
0x180124fa9  push    r12
0x180124fab  push    r13
0x180124fad  push    r14
0x180124faf  push    r15
0x180124fb1  sub     rsp, 60h
0x180124fb5  movsxd  r13, ecx
0x180124fb8  mov     r9, rdx
0x180124fbb  mov     r12d, r8d
0x180124fbe  cmp     r13d, 0FFFFFFFEh
0x180124fc2  jnz     short loc_180124FDD
0x180124fc4  call    __doserrno
0x180124fc9  xor     esi, esi
0x180124fcb  mov     [rax], esi
0x180124fcd  call    _errno
0x180124fd2  mov     dword ptr [rax], 9
0x180124fd8  jmp     loc_1801253E0
0x180124fdd  xor     esi, esi
0x180124fdf  test    ecx, ecx
0x180124fe1  js      loc_1801253C9
0x180124fe7  cmp     r13d, cs:_nhandle
0x180124fee  jnb     loc_1801253C9
0x180124ff4  mov     rax, r13
0x180124ff7  lea     edx, [rsi+1]
0x180124ffa  and     eax, 3Fh
0x180124ffd  mov     [rsp+98h+var_50], rdx
0x180125002  mov     r8, r13
0x180125005  lea     r11, __pioinfo
0x18012500c  shr     r8, 6
0x180125010  mov     [rsp+98h+var_58], r8
0x180125015  lea     r14, [rax+rax*8]
0x180125019  mov     rax, [r11+r8*8]
0x18012501d  test    [rax+r14*8+38h], dl
0x180125022  jz      loc_1801253C9
0x180125028  cmp     r12d, 7FFFFFFFh
0x18012502f  jbe     short loc_180125048
0x180125031  call    __doserrno
0x180125036  mov     [rax], esi
0x180125038  call    _errno
0x18012503d  mov     dword ptr [rax], 16h
0x180125043  jmp     loc_1801253DB
0x180125048  test    r12d, r12d
0x18012504b  jz      loc_1801253C5
0x180125051  test    byte ptr [rax+r14*8+38h], 2
0x180125057  jnz     loc_1801253C5
0x18012505d  test    r9, r9
0x180125060  jz      short loc_180125031
0x180125062  mov     rcx, [rax+r14*8+28h]
0x180125067  mov     rbx, rsi
0x18012506a  movsx   r10d, byte ptr [rax+r14*8+39h]
0x180125070  mov     edi, 4
0x180125075  mov     [rsp+98h+hConsoleHandle], rcx
0x18012507a  mov     ecx, r10d
0x18012507d  mov     [rsp+98h+arg_0], r10b
0x180125085  sub     ecx, edx
0x180125087  jz      short loc_1801250BA
0x180125089  cmp     ecx, edx
0x18012508b  jnz     short loc_1801250B2
0x18012508d  mov     eax, r12d
0x180125090  not     eax
0x180125092  test    dl, al
0x180125094  jnz     short loc_1801250B2
0x180125096  call    __doserrno
0x18012509b  mov     [rax], esi
0x18012509d  call    _errno
0x1801250a2  mov     dword ptr [rax], 16h
0x1801250a8  call    _invalid_parameter_noinfo
0x1801250ad  jmp     loc_18012524B
0x1801250b2  mov     ebp, r12d
0x1801250b5  mov     r15, r9
0x1801250b8  jmp     short loc_180125138
0x1801250ba  mov     eax, r12d
0x1801250bd  not     eax
0x1801250bf  test    dl, al
0x1801250c1  jz      short loc_180125096
0x1801250c3  mov     ebp, r12d
0x1801250c6  shr     ebp, 1
0x1801250c8  cmp     ebp, edi
0x1801250ca  cmovb   ebp, edi
0x1801250cd  mov     ecx, ebp; Size
0x1801250cf  call    _malloc_base
0x1801250d4  xor     ecx, ecx; Block
0x1801250d6  mov     rbx, rax
0x1801250d9  call    _free_base
0x1801250de  xor     ecx, ecx; Block
0x1801250e0  call    _free_base
0x1801250e5  mov     r15, rbx
0x1801250e8  test    rbx, rbx
0x1801250eb  jnz     short loc_180125108
0x1801250ed  call    _errno
0x1801250f2  mov     dword ptr [rax], 0Ch
0x1801250f8  call    __doserrno
0x1801250fd  mov     dword ptr [rax], 8
0x180125103  jmp     loc_18012524B
0x180125108  xor     edx, edx
0x18012510a  mov     ecx, r13d
0x18012510d  lea     r8d, [rdx+1]
0x180125111  call    _lseeki64_nolock
0x180125116  mov     r8, [rsp+98h+var_58]
0x18012511b  lea     r11, __pioinfo
0x180125122  mov     r10b, [rsp+98h+arg_0]
0x18012512a  mov     edx, 1
0x18012512f  mov     rcx, [r11+r8*8]
0x180125133  mov     [rcx+r14*8+30h], rax
0x180125138  mov     rax, [r11+r8*8]
0x18012513c  mov     edi, esi
0x18012513e  mov     [rsp+98h+var_48], r15
0x180125143  mov     r9d, 0Ah
0x180125149  test    byte ptr [rax+r14*8+38h], 48h
0x18012514f  jz      short loc_1801251CA
0x180125151  mov     al, [rax+r14*8+3Ah]
0x180125156  cmp     al, r9b
0x180125159  jz      short loc_1801251CA
0x18012515b  test    ebp, ebp
0x18012515d  jz      short loc_1801251CA
0x18012515f  mov     [r15], al
0x180125162  dec     ebp
0x180125164  mov     rax, [r11+r8*8]
0x180125168  add     r15, rdx
0x18012516b  mov     edi, edx
0x18012516d  mov     [rax+r14*8+3Ah], r9b
0x180125172  test    r10b, r10b
0x180125175  jz      short loc_1801251CA
0x180125177  mov     rax, [r11+r8*8]
0x18012517b  mov     cl, [rax+r14*8+3Bh]
0x180125180  cmp     cl, r9b
0x180125183  jz      short loc_1801251CA
0x180125185  test    ebp, ebp
0x180125187  jz      short loc_1801251CA
0x180125189  mov     [r15], cl
0x18012518c  lea     edi, [r9-8]
0x180125190  mov     rax, [r11+r8*8]
0x180125194  add     r15, rdx
0x180125197  dec     ebp
0x180125199  mov     [rax+r14*8+3Bh], r9b
0x18012519e  cmp     r10b, dl
0x1801251a1  jnz     short loc_1801251CA
0x1801251a3  mov     rax, [r11+r8*8]
0x1801251a7  mov     cl, [rax+r14*8+3Ch]
0x1801251ac  cmp     cl, r9b
0x1801251af  jz      short loc_1801251CA
0x1801251b1  test    ebp, ebp
0x1801251b3  jz      short loc_1801251CA
0x1801251b5  mov     [r15], cl
0x1801251b8  lea     edi, [r9-7]
0x1801251bc  mov     rax, [r11+r8*8]
0x1801251c0  add     r15, rdx
0x1801251c3  dec     ebp
0x1801251c5  mov     [rax+r14*8+3Ch], r9b
0x1801251ca  mov     ecx, r13d; FileHandle
0x1801251cd  mov     [rsp+98h+Mode], esi
0x1801251d1  call    _isatty
0x1801251d6  test    eax, eax
0x1801251d8  jz      loc_180125269
0x1801251de  mov     rax, [rsp+98h+var_58]
0x1801251e3  lea     rcx, __pioinfo
0x1801251ea  mov     rax, [rcx+rax*8]
0x1801251ee  cmp     [rax+r14*8+38h], sil
0x1801251f3  jge     short loc_180125269
0x1801251f5  mov     rcx, [rsp+98h+hConsoleHandle]; hConsoleHandle
0x1801251fa  lea     rdx, [rsp+98h+Mode]; lpMode
0x1801251ff  call    cs:__imp_GetConsoleMode
0x180125205  test    eax, eax
0x180125207  jz      short loc_180125269
0x180125209  cmp     [rsp+98h+arg_0], 2
0x180125211  jnz     short loc_18012526E
0x180125213  mov     rcx, [rsp+98h+hConsoleHandle]; hConsoleInput
0x180125218  lea     r9, [rsp+98h+NumberOfCharsRead]; lpNumberOfCharsRead
0x180125220  shr     ebp, 1
0x180125222  mov     rdx, r15; lpBuffer
0x180125225  mov     r8d, ebp; nNumberOfCharsToRead
0x180125228  mov     [rsp+98h+NumberOfCharsRead], esi
0x18012522f  mov     [rsp+98h+pInputControl], rsi; pInputControl
0x180125234  call    cs:__imp_ReadConsoleW
0x18012523a  test    eax, eax
0x18012523c  jnz     short loc_18012525D
0x18012523e  call    cs:__imp_GetLastError
0x180125244  mov     ecx, eax
0x180125246  call    __acrt_errno_map_os_error
0x18012524b  or      edi, 0FFFFFFFFh
0x18012524e  mov     rcx, rbx; Block
0x180125251  call    _free_base
0x180125256  mov     eax, edi
0x180125258  jmp     loc_1801253E3
0x18012525d  mov     eax, [rsp+98h+NumberOfCharsRead]
0x180125264  lea     edi, [rdi+rax*2]
0x180125267  jmp     short loc_1801252B0
0x180125269  mov     byte ptr [rsp+98h+var_50], sil
0x18012526e  mov     rcx, [rsp+98h+hConsoleHandle]; hFile
0x180125273  lea     r9, [rsp+98h+NumberOfCharsRead]; lpNumberOfBytesRead
0x18012527b  mov     r8d, ebp; nNumberOfBytesToRead
0x18012527e  mov     [rsp+98h+NumberOfCharsRead], esi
0x180125285  mov     rdx, r15; lpBuffer
0x180125288  mov     [rsp+98h+pInputControl], rsi; lpOverlapped
0x18012528d  call    cs:__imp_ReadFile
0x180125293  test    eax, eax
0x180125295  jz      loc_18012538F
0x18012529b  cmp     [rsp+98h+NumberOfCharsRead], r12d
0x1801252a3  ja      loc_18012538F
0x1801252a9  add     edi, [rsp+98h+NumberOfCharsRead]
0x1801252b0  mov     rdx, [rsp+98h+var_58]
0x1801252b5  lea     r11, __pioinfo
0x1801252bc  mov     rax, [r11+rdx*8]
0x1801252c0  cmp     [rax+r14*8+38h], sil
0x1801252c5  jge     short loc_18012524E
0x1801252c7  cmp     [rsp+98h+arg_0], 2
0x1801252cf  movsxd  r8, edi
0x1801252d2  jz      short loc_1801252F9
0x1801252d4  mov     r9, [rsp+98h+arg_8]
0x1801252dc  mov     rax, r12
0x1801252df  shr     rax, 1
0x1801252e2  mov     rdx, r15
0x1801252e5  mov     ecx, r13d
0x1801252e8  mov     [rsp+98h+pInputControl], rax
0x1801252ed  call    translate_ansi_or_utf8_nolock
0x1801252f2  mov     edi, eax
0x1801252f4  jmp     loc_18012524E
0x1801252f9  shr     r8, 1
0x1801252fc  cmp     byte ptr [rsp+98h+var_50], sil
0x180125301  jz      short loc_18012537D
0x180125303  mov     r10, [rsp+98h+var_48]
0x180125308  mov     rax, r10
0x18012530b  mov     rdi, r10
0x18012530e  lea     r9, [r10+r8*2]
0x180125312  cmp     r10, r9
0x180125315  jnb     short loc_180125370
0x180125317  mov     esi, 0Ah
0x18012531c  movzx   ecx, word ptr [rax]
0x18012531f  cmp     cx, 1Ah
0x180125323  jz      short loc_18012535F
0x180125325  cmp     cx, 0Dh
0x180125329  jnz     short loc_180125345
0x18012532b  lea     r8, [rax+2]
0x18012532f  cmp     r8, r9
0x180125332  jnb     short loc_180125345
0x180125334  cmp     [r8], si
0x180125338  jnz     short loc_180125345
0x18012533a  movzx   ecx, si
0x18012533d  mov     r11d, 4
0x180125343  jmp     short loc_18012534B
0x180125345  mov     r11d, 2
0x18012534b  add     rax, r11
0x18012534e  mov     [rdi], cx
0x180125351  lea     r8, [rdi+2]
0x180125355  mov     rdi, r8
0x180125358  cmp     rax, r9
0x18012535b  jb      short loc_18012531C
0x18012535d  jmp     short loc_180125370
0x18012535f  lea     rcx, __pioinfo
0x180125366  mov     rax, [rcx+rdx*8]
0x18012536a  or      byte ptr [rax+r14*8+38h], 2
0x180125370  sub     rdi, r10
0x180125373  sar     rdi, 1
0x180125376  add     edi, edi
0x180125378  jmp     loc_18012524E
0x18012537d  mov     rdx, [rsp+98h+var_48]
0x180125382  mov     ecx, r13d
0x180125385  call    translate_text_mode_nolock_wchar_t_
0x18012538a  jmp     loc_1801252F2
0x18012538f  call    cs:__imp_GetLastError
0x180125395  cmp     eax, 5
0x180125398  jnz     short loc_1801253B5
0x18012539a  call    _errno
0x18012539f  mov     dword ptr [rax], 9
0x1801253a5  call    __doserrno
0x1801253aa  mov     dword ptr [rax], 5
0x1801253b0  jmp     loc_18012524B
0x1801253b5  cmp     eax, 6Dh ; 'm'
0x1801253b8  jnz     loc_180125244
0x1801253be  mov     edi, esi
0x1801253c0  jmp     loc_18012524E
0x1801253c5  xor     eax, eax
0x1801253c7  jmp     short loc_1801253E3
0x1801253c9  call    __doserrno
0x1801253ce  mov     [rax], esi
0x1801253d0  call    _errno
0x1801253d5  mov     dword ptr [rax], 9
0x1801253db  call    _invalid_parameter_noinfo
0x1801253e0  or      eax, 0FFFFFFFFh
0x1801253e3  mov     rbx, [rsp+98h+arg_10]
0x1801253eb  add     rsp, 60h
0x1801253ef  pop     r15
0x1801253f1  pop     r14
0x1801253f3  pop     r13
0x1801253f5  pop     r12
0x1801253f7  pop     rdi
0x1801253f8  pop     rsi
0x1801253f9  pop     rbp
0x1801253fa  retn
```
