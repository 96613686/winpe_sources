# __read_nolock

- ea: `0x181616e0`
- end: `0x18161a90`
- name: `__read_nolock`
- size: `944`
- prototype: `unsigned int __cdecl(int FileHandle, LPWSTR lpWideCharStr, unsigned int)`
- caller_count: `4`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x181615cc`
- `0x181658c0`
- `0x18167780`
- `0x18167be2`

## callees

- `0x181405a5`
- `0x18140679`
- `0x1814069c`
- `0x181406af`
- `0x181513fa`
- `0x18151434`
- `0x1815cb87`
- `0x18160e83`
- `0x1816124b`
- `0x181613fa`
- `0x18161551`
- `0x181616e0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18161997`
- `KERNEL32!GetLastError` at `0x18161a39`
- `KERNEL32!GetLastError` at `0x18161997`
- `KERNEL32!GetLastError` at `0x18161a39`
- `KERNEL32!ReadFile` at `0x181619d5`
- `KERNEL32!ReadFile` at `0x181619d5`
- `KERNEL32!GetConsoleMode` at `0x1816196b`
- `KERNEL32!GetConsoleMode` at `0x1816196b`
- `KERNEL32!ReadConsoleW` at `0x1816198d`
- `KERNEL32!ReadConsoleW` at `0x1816198d`

## pseudocode

```c
unsigned int __cdecl _read_nolock(int FileHandle, LPWSTR lpWideCharStr, unsigned int a3)
{
  int v3; // edi
  int v4; // eax
  char v5; // dl
  DWORD v6; // ecx
  void *v7; // esi
  wchar_t *v8; // edx
  size_t v9; // eax
  DWORD v10; // eax
  int v11; // ecx
  int v12; // eax
  int v13; // edx
  int v14; // edi
  int v15; // ebx
  char v16; // al
  int v17; // ebx
  _BYTE *v18; // edx
  DWORD v19; // ecx
  bool v20; // zf
  char v21; // al
  int v22; // ebx
  _BYTE *v23; // edx
  DWORD v24; // ecx
  int v25; // eax
  char v26; // al
  int v27; // eax
  DWORD LastError; // eax
  unsigned int v29; // edi
  unsigned int v31; // ecx
  unsigned int v32; // eax
  unsigned int v33; // [esp-8h] [ebp-38h]
  DWORD Mode; // [esp+8h] [ebp-28h] BYREF
  wchar_t *v35; // [esp+Ch] [ebp-24h]
  int v36; // [esp+10h] [ebp-20h]
  DWORD NumberOfCharsRead; // [esp+14h] [ebp-1Ch] BYREF
  HANDLE hConsoleHandle; // [esp+18h] [ebp-18h]
  LPVOID lpBuffer; // [esp+1Ch] [ebp-14h]
  int v40; // [esp+20h] [ebp-10h]
  DWORD nNumberOfBytesToRead; // [esp+24h] [ebp-Ch]
  int v42; // [esp+28h] [ebp-8h]
  char v43; // [esp+2Fh] [ebp-1h]

  if ( FileHandle != -2 )
  {
    if ( FileHandle >= 0
      && FileHandle < (unsigned int)dword_181ED590
      && (v3 = 56 * (FileHandle & 0x3F),
          v42 = FileHandle >> 6,
          v4 = (int)*(&lpCriticalSection + (FileHandle >> 6)),
          v40 = v3,
          v36 = 1,
          v5 = *(_BYTE *)(v4 + v3 + 40),
          (v5 & 1) != 0) )
    {
      v6 = a3;
      if ( a3 <= 0x7FFFFFFF )
      {
        if ( !a3 || (v5 & 2) != 0 )
          return 0;
        if ( lpWideCharStr )
        {
          hConsoleHandle = *(HANDLE *)(v4 + v3 + 24);
          v43 = *(_BYTE *)(v4 + v3 + 41);
          v7 = 0;
          if ( v43 == 1 )
          {
            if ( (a3 & 1) == 0 )
            {
              v9 = 4;
              nNumberOfBytesToRead = 4;
              if ( a3 >> 1 >= 4 )
              {
                v9 = a3 >> 1;
                nNumberOfBytesToRead = a3 >> 1;
              }
              v7 = _malloc_base(v9);
              _free_base(0);
              _free_base(0);
              lpBuffer = v7;
              if ( v7 )
              {
                v10 = _lseeki64_nolock(FileHandle, 0, 1u);
                v11 = (int)*(&lpCriticalSection + v42);
                *(_DWORD *)(v3 + v11 + 32) = v10;
                v12 = v42;
                *(_DWORD *)(v3 + v11 + 36) = v13;
                v8 = (wchar_t *)v7;
                v6 = nNumberOfBytesToRead;
                v4 = (int)*(&lpCriticalSection + v12);
                goto LABEL_23;
              }
              *_errno() = 12;
              *__doserrno() = 8;
LABEL_40:
              v29 = -1;
LABEL_41:
              _free_base(v7);
              return v29;
            }
          }
          else
          {
            if ( v43 != 2 )
            {
              v8 = lpWideCharStr;
              nNumberOfBytesToRead = a3;
              lpBuffer = lpWideCharStr;
LABEL_23:
              v14 = 0;
              v35 = v8;
              v15 = FileHandle;
              if ( (*(_BYTE *)(v40 + v4 + 40) & 0x48) != 0 )
              {
                v16 = *(_BYTE *)(v40 + v4 + 42);
                v15 = FileHandle;
                if ( v16 != 10 )
                {
                  if ( v6 )
                  {
                    v17 = v40;
                    v14 = 1;
                    *(_BYTE *)v8 = v16;
                    v18 = (char *)v8 + 1;
                    v19 = v6 - 1;
                    v20 = v43 == 0;
                    lpBuffer = v18;
                    nNumberOfBytesToRead = v19;
                    *((_BYTE *)&(*(&lpCriticalSection + v42))[1].LockSemaphore + v17 + 2) = 10;
                    v15 = FileHandle;
                    if ( !v20 )
                    {
                      v21 = *((_BYTE *)&(*(&lpCriticalSection + v42))[1].LockSemaphore + v40 + 3);
                      v15 = FileHandle;
                      if ( v21 != 10 )
                      {
                        if ( v19 )
                        {
                          v22 = v40;
                          *v18 = v21;
                          v23 = v18 + 1;
                          v24 = v19 - 1;
                          v20 = v43 == 1;
                          lpBuffer = v23;
                          v25 = (int)*(&lpCriticalSection + v42);
                          v14 = 2;
                          nNumberOfBytesToRead = v24;
                          *(_BYTE *)(v22 + v25 + 43) = 10;
                          v15 = FileHandle;
                          if ( v20 )
                          {
                            v26 = *((_BYTE *)&(*(&lpCriticalSection + v42))[1].SpinCount + v40);
                            v15 = FileHandle;
                            if ( v26 != 10 )
                            {
                              if ( v24 )
                              {
                                *v23 = v26;
                                nNumberOfBytesToRead = v24 - 1;
                                v27 = (int)*(&lpCriticalSection + v42);
                                lpBuffer = v23 + 1;
                                v14 = 3;
                                *(_BYTE *)(v40 + v27 + 44) = 10;
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
              if ( _isatty(v15)
                && *((char *)&(*(&lpCriticalSection + v42))[1].LockSemaphore + v40) < 0
                && GetConsoleMode(hConsoleHandle, &Mode) )
              {
                if ( v43 == 2 )
                {
                  if ( !ReadConsoleW(hConsoleHandle, lpBuffer, nNumberOfBytesToRead >> 1, &NumberOfCharsRead, 0) )
                  {
                    LastError = GetLastError();
LABEL_39:
                    __acrt_errno_map_os_error(LastError);
                    goto LABEL_40;
                  }
                  v31 = a3;
                  v29 = v14 + 2 * NumberOfCharsRead;
                  goto LABEL_47;
                }
              }
              else
              {
                LOBYTE(v36) = 0;
              }
              if ( !ReadFile(hConsoleHandle, lpBuffer, nNumberOfBytesToRead, &NumberOfCharsRead, 0)
                || (v31 = a3, NumberOfCharsRead > a3) )
              {
                LastError = GetLastError();
                if ( LastError == 5 )
                {
                  *_errno() = 9;
                  *__doserrno() = 5;
                  goto LABEL_40;
                }
                if ( LastError == 109 )
                {
                  v29 = 0;
                  goto LABEL_41;
                }
                goto LABEL_39;
              }
              v29 = NumberOfCharsRead + v14;
LABEL_47:
              if ( *((char *)&(*(&lpCriticalSection + v42))[1].LockSemaphore + v40) < 0 )
              {
                if ( v43 == 2 )
                {
                  v33 = v29 >> 1;
                  if ( (_BYTE)v36 )
                    v32 = translate_utf16_from_console_nolock(v15, v35, v33);
                  else
                    v32 = translate_text_mode_nolock<wchar_t>(v15, (char *)v35, v33);
                }
                else
                {
                  v32 = translate_ansi_or_utf8_nolock(v15, (LPCCH)lpBuffer, v29, lpWideCharStr, v31 >> 1);
                }
                v29 = v32;
              }
              goto LABEL_41;
            }
            if ( (a3 & 1) == 0 )
            {
              v8 = lpWideCharStr;
              nNumberOfBytesToRead = a3;
              lpBuffer = lpWideCharStr;
              v4 = (int)*(&lpCriticalSection + v42);
              goto LABEL_23;
            }
          }
          *__doserrno() = 0;
          *_errno() = 22;
          _invalid_parameter_noinfo();
          goto LABEL_40;
        }
      }
      *__doserrno() = 0;
      *_errno() = 22;
    }
    else
    {
      *__doserrno() = 0;
      *_errno() = 9;
    }
    _invalid_parameter_noinfo();
    return -1;
  }
  *__doserrno() = 0;
  *_errno() = 9;
  return -1;
}

```

## disassembly

```asm
0x181616e0  mov     edi, edi
0x181616e2  push    ebp
0x181616e3  mov     ebp, esp
0x181616e5  sub     esp, 28h
0x181616e8  push    ebx
0x181616e9  mov     ebx, [ebp+FileHandle]
0x181616ec  push    edi
0x181616ed  cmp     ebx, 0FFFFFFFEh
0x181616f0  jnz     short loc_1816170A
0x181616f2  call    ___doserrno
0x181616f7  and     dword ptr [eax], 0
0x181616fa  call    __errno
0x181616ff  mov     dword ptr [eax], 9
0x18161705  jmp     loc_18161A89
0x1816170a  test    ebx, ebx
0x1816170c  js      loc_18161A71
0x18161712  cmp     ebx, dword_181ED590
0x18161718  jnb     loc_18161A71
0x1816171e  mov     eax, ebx
0x18161720  mov     ecx, ebx
0x18161722  sar     ecx, 6
0x18161725  and     eax, 3Fh
0x18161728  imul    edi, eax, 38h ; '8'
0x1816172b  mov     [ebp+var_8], ecx
0x1816172e  mov     eax, lpCriticalSection[ecx*4]
0x18161735  xor     ecx, ecx
0x18161737  inc     ecx
0x18161738  mov     [ebp+var_10], edi
0x1816173b  mov     [ebp+var_20], ecx
0x1816173e  mov     dl, [eax+edi+28h]
0x18161742  test    cl, dl
0x18161744  jz      loc_18161A71
0x1816174a  mov     ecx, [ebp+arg_8]
0x1816174d  cmp     ecx, 7FFFFFFFh
0x18161753  jbe     short loc_1816176D
0x18161755  call    ___doserrno
0x1816175a  and     dword ptr [eax], 0
0x1816175d  call    __errno
0x18161762  mov     dword ptr [eax], 16h
0x18161768  jmp     loc_18161A84
0x1816176d  test    ecx, ecx
0x1816176f  jz      loc_18161A6D
0x18161775  test    dl, 2
0x18161778  jnz     loc_18161A6D
0x1816177e  cmp     [ebp+lpWideCharStr], 0
0x18161782  jz      short loc_18161755
0x18161784  mov     edx, [eax+edi+18h]
0x18161788  mov     [ebp+hConsoleHandle], edx
0x1816178b  mov     dl, [eax+edi+29h]
0x1816178f  mov     [ebp+var_1], dl
0x18161792  push    esi
0x18161793  movsx   edx, dl
0x18161796  xor     esi, esi
0x18161798  sub     edx, 1
0x1816179b  jz      short loc_181617EC
0x1816179d  sub     edx, 1
0x181617a0  jz      short loc_181617B0
0x181617a2  mov     edx, [ebp+lpWideCharStr]
0x181617a5  mov     [ebp+nNumberOfBytesToRead], ecx
0x181617a8  mov     [ebp+lpBuffer], edx
0x181617ab  jmp     loc_18161870
0x181617b0  mov     eax, ecx
0x181617b2  not     eax
0x181617b4  test    al, 1
0x181617b6  jnz     short loc_181617D4
0x181617b8  call    ___doserrno
0x181617bd  and     [eax], esi
0x181617bf  call    __errno
0x181617c4  mov     dword ptr [eax], 16h
0x181617ca  call    __invalid_parameter_noinfo
0x181617cf  jmp     loc_181619A4
0x181617d4  mov     edi, [ebp+var_8]
0x181617d7  mov     edx, [ebp+lpWideCharStr]
0x181617da  mov     [ebp+nNumberOfBytesToRead], ecx
0x181617dd  mov     [ebp+lpBuffer], edx
0x181617e0  mov     eax, lpCriticalSection[edi*4]
0x181617e7  jmp     loc_18161870
0x181617ec  mov     eax, ecx
0x181617ee  not     eax
0x181617f0  test    al, 1
0x181617f2  jz      short loc_181617B8
0x181617f4  push    4
0x181617f6  pop     eax
0x181617f7  shr     ecx, 1
0x181617f9  mov     [ebp+nNumberOfBytesToRead], eax
0x181617fc  cmp     ecx, eax
0x181617fe  jb      short loc_18161805
0x18161800  mov     eax, ecx
0x18161802  mov     [ebp+nNumberOfBytesToRead], ecx
0x18161805  push    eax; Size
0x18161806  call    __malloc_base
0x1816180b  push    0; Block
0x1816180d  mov     esi, eax
0x1816180f  call    __free_base
0x18161814  push    0; Block
0x18161816  call    __free_base
0x1816181b  add     esp, 0Ch
0x1816181e  mov     [ebp+lpBuffer], esi
0x18161821  test    esi, esi
0x18161823  jnz     short loc_18161840
0x18161825  call    __errno
0x1816182a  mov     dword ptr [eax], 0Ch
0x18161830  call    ___doserrno
0x18161835  mov     dword ptr [eax], 8
0x1816183b  jmp     loc_181619A4
0x18161840  push    1; dwMoveMethod
0x18161842  push    0
0x18161844  push    0; liDistanceToMove
0x18161846  push    ebx; FileHandle
0x18161847  call    __lseeki64_nolock
0x1816184c  mov     ecx, [ebp+var_8]
0x1816184f  add     esp, 10h
0x18161852  mov     ecx, lpCriticalSection[ecx*4]
0x18161859  mov     [edi+ecx+20h], eax
0x1816185d  mov     eax, [ebp+var_8]
0x18161860  mov     [edi+ecx+24h], edx
0x18161864  mov     edx, esi
0x18161866  mov     ecx, [ebp+nNumberOfBytesToRead]
0x18161869  mov     eax, lpCriticalSection[eax*4]
0x18161870  mov     ebx, [ebp+var_10]
0x18161873  xor     edi, edi
0x18161875  mov     [ebp+var_24], edx
0x18161878  test    byte ptr [ebx+eax+28h], 48h
0x1816187d  mov     ebx, [ebp+FileHandle]
0x18161880  jz      loc_18161945
0x18161886  mov     ebx, [ebp+var_10]
0x18161889  mov     al, [ebx+eax+2Ah]
0x1816188d  mov     ebx, [ebp+FileHandle]
0x18161890  cmp     al, 0Ah
0x18161892  jz      loc_18161945
0x18161898  test    ecx, ecx
0x1816189a  jz      loc_18161945
0x181618a0  mov     ebx, [ebp+var_10]
0x181618a3  inc     edi
0x181618a4  mov     [edx], al
0x181618a6  inc     edx
0x181618a7  mov     eax, [ebp+var_8]
0x181618aa  dec     ecx
0x181618ab  cmp     [ebp+var_1], 0
0x181618af  mov     [ebp+lpBuffer], edx
0x181618b2  mov     [ebp+nNumberOfBytesToRead], ecx
0x181618b5  mov     eax, lpCriticalSection[eax*4]
0x181618bc  mov     byte ptr [ebx+eax+2Ah], 0Ah
0x181618c1  mov     ebx, [ebp+FileHandle]
0x181618c4  jz      short loc_18161945
0x181618c6  mov     eax, [ebp+var_8]
0x181618c9  mov     ebx, [ebp+var_10]
0x181618cc  mov     eax, lpCriticalSection[eax*4]
0x181618d3  mov     al, [ebx+eax+2Bh]
0x181618d7  mov     ebx, [ebp+FileHandle]
0x181618da  cmp     al, 0Ah
0x181618dc  jz      short loc_18161945
0x181618de  test    ecx, ecx
0x181618e0  jz      short loc_18161945
0x181618e2  mov     ebx, [ebp+var_10]
0x181618e5  mov     [edx], al
0x181618e7  inc     edx
0x181618e8  mov     eax, [ebp+var_8]
0x181618eb  dec     ecx
0x181618ec  cmp     [ebp+var_1], 1
0x181618f0  push    2
0x181618f2  mov     [ebp+lpBuffer], edx
0x181618f5  mov     eax, lpCriticalSection[eax*4]
0x181618fc  pop     edi
0x181618fd  mov     [ebp+nNumberOfBytesToRead], ecx
0x18161900  mov     byte ptr [ebx+eax+2Bh], 0Ah
0x18161905  mov     ebx, [ebp+FileHandle]
0x18161908  jnz     short loc_18161945
0x1816190a  mov     eax, [ebp+var_8]
0x1816190d  mov     ebx, [ebp+var_10]
0x18161910  mov     eax, lpCriticalSection[eax*4]
0x18161917  mov     al, [ebx+eax+2Ch]
0x1816191b  mov     ebx, [ebp+FileHandle]
0x1816191e  cmp     al, 0Ah
0x18161920  jz      short loc_18161945
0x18161922  test    ecx, ecx
0x18161924  jz      short loc_18161945
0x18161926  mov     [edx], al
0x18161928  inc     edx
0x18161929  mov     eax, [ebp+var_8]
0x1816192c  dec     ecx
0x1816192d  mov     [ebp+nNumberOfBytesToRead], ecx
0x18161930  mov     ecx, [ebp+var_10]
0x18161933  push    3
0x18161935  mov     eax, lpCriticalSection[eax*4]
0x1816193c  mov     [ebp+lpBuffer], edx
0x1816193f  pop     edi
0x18161940  mov     byte ptr [ecx+eax+2Ch], 0Ah
0x18161945  push    ebx; FileHandle
0x18161946  call    __isatty
0x1816194b  pop     ecx
0x1816194c  test    eax, eax
0x1816194e  jz      short loc_181619C1
0x18161950  mov     eax, [ebp+var_8]
0x18161953  mov     ecx, [ebp+var_10]
0x18161956  mov     eax, lpCriticalSection[eax*4]
0x1816195d  cmp     byte ptr [ecx+eax+28h], 0
0x18161962  jge     short loc_181619C1
0x18161964  lea     eax, [ebp+Mode]
0x18161967  push    eax; lpMode
0x18161968  push    [ebp+hConsoleHandle]; hConsoleHandle
0x1816196b  call    ds:GetConsoleMode
0x18161971  test    eax, eax
0x18161973  jz      short loc_181619C1
0x18161975  cmp     [ebp+var_1], 2
0x18161979  jnz     short loc_181619C5
0x1816197b  push    0; pInputControl
0x1816197d  lea     eax, [ebp+NumberOfCharsRead]
0x18161980  push    eax; lpNumberOfCharsRead
0x18161981  mov     eax, [ebp+nNumberOfBytesToRead]
0x18161984  shr     eax, 1
0x18161986  push    eax; nNumberOfCharsToRead
0x18161987  push    [ebp+lpBuffer]; lpBuffer
0x1816198a  push    [ebp+hConsoleHandle]; hConsoleInput
0x1816198d  call    ds:ReadConsoleW
0x18161993  test    eax, eax
0x18161995  jnz     short loc_181619B6
0x18161997  call    ds:GetLastError
0x1816199d  push    eax
0x1816199e  call    ___acrt_errno_map_os_error
0x181619a3  pop     ecx
0x181619a4  or      edi, 0FFFFFFFFh
0x181619a7  push    esi; Block
0x181619a8  call    __free_base
0x181619ad  pop     ecx
0x181619ae  mov     eax, edi
0x181619b0  pop     esi
0x181619b1  jmp     loc_18161A8C
0x181619b6  mov     eax, [ebp+NumberOfCharsRead]
0x181619b9  mov     ecx, [ebp+arg_8]
0x181619bc  lea     edi, [edi+eax*2]
0x181619bf  jmp     short loc_181619EA
0x181619c1  mov     byte ptr [ebp+var_20], 0
0x181619c5  push    0; lpOverlapped
0x181619c7  lea     eax, [ebp+NumberOfCharsRead]
0x181619ca  push    eax; lpNumberOfBytesRead
0x181619cb  mov     eax, [ebp+nNumberOfBytesToRead]
0x181619ce  push    eax; nNumberOfBytesToRead
0x181619cf  push    [ebp+lpBuffer]; lpBuffer
0x181619d2  push    [ebp+hConsoleHandle]; hFile
0x181619d5  call    ds:ReadFile
0x181619db  test    eax, eax
0x181619dd  jz      short loc_18161A39
0x181619df  mov     ecx, [ebp+arg_8]
0x181619e2  cmp     [ebp+NumberOfCharsRead], ecx
0x181619e5  ja      short loc_18161A39
0x181619e7  add     edi, [ebp+NumberOfCharsRead]
0x181619ea  mov     eax, [ebp+var_8]
0x181619ed  mov     edx, [ebp+var_10]
0x181619f0  mov     eax, lpCriticalSection[eax*4]
0x181619f7  cmp     byte ptr [edx+eax+28h], 0
0x181619fc  jge     short loc_181619A7
0x181619fe  cmp     [ebp+var_1], 2
0x18161a02  jz      short loc_18161A1B
0x18161a04  shr     ecx, 1
0x18161a06  push    ecx; cchWideChar
0x18161a07  push    [ebp+lpWideCharStr]; lpWideCharStr
0x18161a0a  push    edi; unsigned int
0x18161a0b  push    [ebp+lpBuffer]; lpMultiByteStr
0x18161a0e  push    ebx; FileHandle
0x18161a0f  call    ?translate_ansi_or_utf8_nolock@@YAHHQADIQA_WI@Z
0x18161a14  add     esp, 14h
0x18161a17  mov     edi, eax
0x18161a19  jmp     short loc_181619A7
0x18161a1b  shr     edi, 1
0x18161a1d  cmp     byte ptr [ebp+var_20], 0
0x18161a21  push    edi; int
0x18161a22  push    [ebp+var_24]; int
0x18161a25  push    ebx; FileHandle
0x18161a26  jz      short loc_18161A32
0x18161a28  call    ?translate_utf16_from_console_nolock@@YAHHQA_WI@Z
0x18161a2d  add     esp, 0Ch
0x18161a30  jmp     short loc_18161A17
0x18161a32  call    ??$translate_text_mode_nolock@_W@@YAHHQA_WI@Z
0x18161a37  jmp     short loc_18161A2D
0x18161a39  call    ds:GetLastError
0x18161a3f  push    5
0x18161a41  pop     edi
0x18161a42  cmp     eax, edi
0x18161a44  jnz     short loc_18161A5D
0x18161a46  call    __errno
0x18161a4b  mov     dword ptr [eax], 9
0x18161a51  call    ___doserrno
0x18161a56  mov     [eax], edi
0x18161a58  jmp     loc_181619A4
0x18161a5d  cmp     eax, 6Dh ; 'm'
0x18161a60  jnz     loc_1816199D
0x18161a66  xor     edi, edi
0x18161a68  jmp     loc_181619A7
0x18161a6d  xor     eax, eax
0x18161a6f  jmp     short loc_18161A8C
0x18161a71  call    ___doserrno
0x18161a76  and     dword ptr [eax], 0
0x18161a79  call    __errno
0x18161a7e  mov     dword ptr [eax], 9
0x18161a84  call    __invalid_parameter_noinfo
0x18161a89  or      eax, 0FFFFFFFFh
0x18161a8c  pop     edi
0x18161a8d  pop     ebx
0x18161a8e  leave
  ... truncated ...
```
