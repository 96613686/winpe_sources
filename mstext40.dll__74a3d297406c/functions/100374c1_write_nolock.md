# __write_nolock

- ea: `0x100374c1`
- end: `0x10037d26`
- name: `__write_nolock`
- size: `2149`
- prototype: `int __cdecl(int, int, DWORD nNumberOfBytesToWrite)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops`

## callers

- `0x100373d2`

## callees

- `0x1002b81a`
- `0x1002cce0`
- `0x1002d6a8`
- `0x1002d6bb`
- `0x1002d6dc`
- `0x1002f09b`
- `0x10030870`
- `0x100320b7`
- `0x1003737e`
- `0x100374c1`
- `0x10037e22`
- `0x1003816b`
- `0x1003bd7f`

## import_xrefs

- `KERNEL32!WriteFile` at `0x1003779d`
- `KERNEL32!WriteFile` at `0x100377fc`
- `KERNEL32!WriteFile` at `0x100379d6`
- `KERNEL32!WriteFile` at `0x10037aeb`
- `KERNEL32!WriteFile` at `0x10037c2a`
- `KERNEL32!WriteFile` at `0x10037cac`
- `KERNEL32!WriteFile` at `0x1003779d`
- `KERNEL32!WriteFile` at `0x100377fc`
- `KERNEL32!WriteFile` at `0x100379d6`
- `KERNEL32!WriteFile` at `0x10037aeb`
- `KERNEL32!WriteFile` at `0x10037c2a`
- `KERNEL32!WriteFile` at `0x10037cac`
- `KERNEL32!GetLastError` at `0x100378f7`
- `KERNEL32!GetLastError` at `0x10037c52`
- `KERNEL32!GetLastError` at `0x100378f7`
- `KERNEL32!GetLastError` at `0x10037c52`
- `KERNEL32!GetConsoleCP` at `0x10037626`
- `KERNEL32!GetConsoleCP` at `0x10037626`
- `KERNEL32!GetConsoleMode` at `0x10037608`
- `KERNEL32!GetConsoleMode` at `0x10037608`
- `KERNEL32!WideCharToMultiByte` at `0x10037765`
- `KERNEL32!WideCharToMultiByte` at `0x10037bd7`
- `KERNEL32!WideCharToMultiByte` at `0x10037765`
- `KERNEL32!WideCharToMultiByte` at `0x10037bd7`

## pseudocode

```c
int __cdecl _write_nolock(int a1, const void *a2, DWORD nNumberOfBytesToWrite)
{
  int v3; // eax
  DWORD v4; // esi
  DWORD v5; // edi
  int v7; // ecx
  int v8; // edx
  char v9; // bl
  UINT ConsoleCP; // eax
  wchar_t v11; // cx
  char *v12; // eax
  DWORD v13; // edx
  CHAR v14; // dl
  int v15; // eax
  int v16; // eax
  char *v17; // eax
  DWORD v18; // eax
  int v19; // ecx
  wint_t v20; // ax
  wint_t v21; // ax
  int v22; // ebx
  int v23; // edx
  int v24; // ecx
  CHAR *v25; // edx
  CHAR *v26; // edi
  DWORD v27; // eax
  int v28; // ecx
  signed int v29; // edi
  char *v30; // ecx
  CHAR *v31; // ebx
  DWORD v32; // eax
  unsigned int i; // edx
  __int16 v34; // di
  signed int v35; // ebx
  BOOL v36; // eax
  WCHAR *v37; // eax
  WCHAR *v38; // edi
  DWORD v39; // ecx
  unsigned int j; // edx
  WCHAR v41; // si
  int v42; // eax
  signed int v43; // ecx
  DWORD LastError; // eax
  UINT CodePage; // [esp+8h] [ebp-1AF0h]
  DWORD Mode; // [esp+10h] [ebp-1AE8h] BYREF
  CHAR v47; // [esp+17h] [ebp-1AE1h]
  DWORD NumberOfBytesWritten; // [esp+18h] [ebp-1AE0h] BYREF
  int v49; // [esp+1Ch] [ebp-1ADCh]
  int v50; // [esp+20h] [ebp-1AD8h]
  char *SrcCh; // [esp+24h] [ebp-1AD4h]
  LPCVOID lpBuffer; // [esp+28h] [ebp-1AD0h]
  wchar_t DstCh[2]; // [esp+2Ch] [ebp-1ACCh] BYREF
  int FileHandle; // [esp+30h] [ebp-1AC8h] BYREF
  int v55; // [esp+34h] [ebp-1AC4h]
  int v56; // [esp+38h] [ebp-1AC0h]
  int v57; // [esp+3Ch] [ebp-1ABCh]
  WCHAR WideCharStr[854]; // [esp+40h] [ebp-1AB8h] BYREF
  CHAR Buffer[1704]; // [esp+6ECh] [ebp-140Ch] BYREF
  CHAR v60[3416]; // [esp+D94h] [ebp-D64h] BYREF
  CHAR MultiByteStr[8]; // [esp+1AECh] [ebp-Ch] BYREF

  v57 = 0;
  v3 = a1;
  v4 = 0;
  FileHandle = a1;
  v5 = 0;
  lpBuffer = a2;
  v56 = 0;
  if ( !nNumberOfBytesToWrite )
    return 0;
  if ( !a2 )
  {
    *__doserrno() = 0;
    *_errno() = 22;
    _invalid_parameter_noinfo();
    return -1;
  }
  v7 = (a1 & 0x1F) << 6;
  v50 = a1 >> 5;
  v8 = __pioinfo[a1 >> 5];
  v49 = v7;
  v9 = (char)(2 * *(_BYTE *)(v7 + v8 + 36)) >> 1;
  if ( v9 == 2 || v9 == 1 )
  {
    if ( (nNumberOfBytesToWrite & 1) != 0 )
    {
      *__doserrno() = 0;
      *_errno() = 22;
      _invalid_parameter_noinfo();
      return -1;
    }
    v3 = FileHandle;
  }
  if ( (*(_BYTE *)(v7 + v8 + 4) & 0x20) != 0 )
    _lseeki64_nolock(v3, 0, 2u);
  if ( !_isatty(FileHandle)
    || *(char *)(v49 + __pioinfo[v50] + 4) >= 0
    || (v55 = *(_DWORD *)(*(_DWORD *)(_getptd() + 108) + 168) == 0,
        !GetConsoleMode(*(HANDLE *)(v49 + __pioinfo[v50]), &Mode))
    || v55 && !v9 )
  {
    v24 = __pioinfo[v50];
    if ( *(char *)(v49 + v24 + 4) >= 0 )
    {
      if ( WriteFile(*(HANDLE *)(v49 + v24), lpBuffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0) )
      {
        v4 = NumberOfBytesWritten;
        v5 = 0;
        goto LABEL_62;
      }
    }
    else
    {
      v25 = (CHAR *)lpBuffer;
      *(_DWORD *)DstCh = 0;
      if ( v9 )
      {
        v30 = (char *)lpBuffer;
        if ( v9 == 2 )
        {
          while ( 1 )
          {
            Mode = 0;
            v31 = Buffer;
            v32 = v30 - v25;
            for ( i = 0; i < 0x13FE; i += 2 )
            {
              if ( v32 >= nNumberOfBytesToWrite )
                break;
              v34 = *(_WORD *)v30;
              v32 += 2;
              v30 += 2;
              if ( v34 == 10 )
              {
                v57 += 2;
                *(_WORD *)v31 = 13;
                v31 += 2;
                i += 2;
              }
              *(_WORD *)v31 = v34;
              v31 += 2;
            }
            v55 = (int)v30;
            v35 = v31 - Buffer;
            v36 = WriteFile(*(HANDLE *)(v49 + __pioinfo[v50]), Buffer, v35, &NumberOfBytesWritten, 0);
            v4 = v56;
            v5 = *(_DWORD *)DstCh;
            if ( !v36 )
              break;
            v4 = NumberOfBytesWritten + v56;
            v56 += NumberOfBytesWritten;
            if ( (int)NumberOfBytesWritten >= v35 )
            {
              v30 = (char *)v55;
              v25 = (CHAR *)lpBuffer;
              if ( v55 - (int)lpBuffer < nNumberOfBytesToWrite )
                continue;
            }
            goto LABEL_62;
          }
        }
        else
        {
          FileHandle = (int)lpBuffer;
          while ( 1 )
          {
            Mode = 0;
            v37 = WideCharStr;
            v38 = (WCHAR *)FileHandle;
            v39 = v30 - v25;
            for ( j = 0; j < 0x6A8; j += 2 )
            {
              if ( v39 >= nNumberOfBytesToWrite )
                break;
              v41 = *v38;
              v39 += 2;
              FileHandle = (int)++v38;
              if ( v41 == 10 )
              {
                *v37++ = 13;
                v38 = (WCHAR *)FileHandle;
                j += 2;
              }
              *v37++ = v41;
            }
            v42 = WideCharToMultiByte(0xFDE9u, 0, WideCharStr, v37 - WideCharStr, v60, 3413, 0, 0);
            v4 = v56;
            v5 = *(_DWORD *)DstCh;
            v55 = v42;
            if ( !v42 )
              break;
            v43 = 0;
            v56 = 0;
            while ( WriteFile(*(HANDLE *)(v49 + __pioinfo[v50]), &v60[v43], v42 - v43, &NumberOfBytesWritten, 0) )
            {
              v43 = NumberOfBytesWritten + v56;
              v42 = v55;
              v56 = v43;
              if ( v55 <= v43 )
                goto LABEL_89;
            }
            LastError = GetLastError();
            v43 = v56;
            v5 = LastError;
            v42 = v55;
            *(_DWORD *)DstCh = v5;
LABEL_89:
            if ( v42 <= v43 )
            {
              v30 = (char *)FileHandle;
              v25 = (CHAR *)lpBuffer;
              v4 = FileHandle - (_DWORD)lpBuffer;
              v56 = FileHandle - (_DWORD)lpBuffer;
              if ( FileHandle - (int)lpBuffer < nNumberOfBytesToWrite )
                continue;
            }
            goto LABEL_62;
          }
        }
      }
      else
      {
        FileHandle = (int)lpBuffer;
        while ( 1 )
        {
          v26 = Buffer;
          v55 = 0;
          v27 = v25 - (_BYTE *)lpBuffer;
          do
          {
            if ( v27 >= nNumberOfBytesToWrite )
              break;
            ++v27;
            v47 = *v25;
            FileHandle = (int)(v25 + 1);
            v28 = v55;
            if ( v47 == 10 )
            {
              ++v57;
              *v26++ = 13;
              ++v28;
            }
            *v26++ = v47;
            v25 = (CHAR *)FileHandle;
            v55 = v28 + 1;
          }
          while ( (unsigned int)(v28 + 1) < 0x13FF );
          v29 = v26 - Buffer;
          if ( !WriteFile(*(HANDLE *)(v49 + __pioinfo[v50]), Buffer, v29, &NumberOfBytesWritten, 0) )
            break;
          v4 += NumberOfBytesWritten;
          if ( (int)NumberOfBytesWritten >= v29 )
          {
            v25 = (CHAR *)FileHandle;
            if ( FileHandle - (int)lpBuffer < nNumberOfBytesToWrite )
              continue;
          }
          v5 = *(_DWORD *)DstCh;
          goto LABEL_62;
        }
      }
    }
LABEL_49:
    v5 = GetLastError();
    goto LABEL_62;
  }
  ConsoleCP = GetConsoleCP();
  v11 = 0;
  FileHandle = 0;
  CodePage = ConsoleCP;
  *(_DWORD *)DstCh = 0;
  SrcCh = (char *)lpBuffer;
  v12 = (char *)lpBuffer;
  v13 = 0;
  v56 = 0;
  while ( 1 )
  {
    v55 = 0;
    if ( !v9 )
      break;
    if ( v9 == 1 || v9 == 2 )
    {
      v11 = *(_WORD *)v12;
      *(_DWORD *)DstCh = *(unsigned __int16 *)v12;
      v12 += 2;
      v55 = v11 == 10;
      v13 = v56 + 2;
      SrcCh = v12;
      v56 += 2;
    }
    if ( v9 != 1 && v9 != 2 )
      goto LABEL_46;
    v20 = _putwch_nolock(v11);
    v11 = DstCh[0];
    if ( v20 != DstCh[0] )
      goto LABEL_49;
    v4 += 2;
    if ( v55 )
    {
      wcscpy(DstCh, L"\r");
      v21 = _putwch_nolock(0xDu);
      v11 = DstCh[0];
      if ( v21 != DstCh[0] )
        goto LABEL_49;
      ++v4;
      ++v57;
    }
LABEL_45:
    v13 = v56;
    v12 = SrcCh;
LABEL_46:
    if ( v13 >= nNumberOfBytesToWrite )
      goto LABEL_62;
  }
  v14 = *v12;
  Mode = *v12 == 10;
  v15 = __pioinfo[v50];
  v55 = v15;
  if ( *(_DWORD *)(v49 + v15 + 56) )
  {
    MultiByteStr[0] = *(_BYTE *)(v49 + v15 + 52);
    MultiByteStr[1] = v14;
    *(_DWORD *)(v49 + v55 + 56) = 0;
    v16 = mbtowc(DstCh, MultiByteStr, 2u);
LABEL_26:
    if ( v16 == -1 )
      goto LABEL_62;
    v17 = SrcCh;
    goto LABEL_28;
  }
  if ( !isleadbyte(v14) )
  {
    v16 = mbtowc(DstCh, SrcCh, 1u);
    goto LABEL_26;
  }
  if ( nNumberOfBytesToWrite + (_BYTE *)lpBuffer - SrcCh > 1 )
  {
    if ( mbtowc(DstCh, SrcCh, 2u) == -1 )
      goto LABEL_62;
    v17 = SrcCh + 1;
    ++v56;
LABEL_28:
    ++v56;
    SrcCh = v17 + 1;
    v18 = WideCharToMultiByte(CodePage, 0, DstCh, 1, MultiByteStr, 5, 0, 0);
    v55 = v18;
    if ( !v18 )
      goto LABEL_62;
    if ( !WriteFile(*(HANDLE *)(v49 + __pioinfo[v50]), MultiByteStr, v18, (LPDWORD)&FileHandle, 0) )
      goto LABEL_49;
    v19 = v57;
    v4 = v57 + v56;
    if ( FileHandle < v55 )
      goto LABEL_63;
    if ( Mode )
    {
      MultiByteStr[0] = 13;
      if ( !WriteFile(*(HANDLE *)(v49 + __pioinfo[v50]), MultiByteStr, 1u, (LPDWORD)&FileHandle, 0) )
        goto LABEL_49;
      if ( FileHandle < 1 )
        goto LABEL_62;
      ++v57;
      ++v4;
    }
    v11 = DstCh[0];
    goto LABEL_45;
  }
  v22 = v50;
  ++v4;
  v23 = v49;
  *(_BYTE *)(v49 + __pioinfo[v50] + 52) = *SrcCh;
  *(_DWORD *)(v23 + __pioinfo[v22] + 56) = 1;
LABEL_62:
  v19 = v57;
LABEL_63:
  if ( v4 )
    return v4 - v19;
  if ( v5 )
  {
    if ( v5 == 5 )
    {
      *_errno() = 9;
      *__doserrno() = 5;
    }
    else
    {
      _dosmaperr(v5);
    }
    return -1;
  }
  else
  {
    if ( (*(_BYTE *)(v49 + __pioinfo[v50] + 4) & 0x40) == 0 || *(_BYTE *)lpBuffer != 26 )
    {
      *_errno() = 28;
      *__doserrno() = 0;
      return -1;
    }
    return 0;
  }
}

```

## disassembly

```asm
0x100374c1  push    ebp
0x100374c2  mov     ebp, esp
0x100374c4  mov     eax, 1AF0h
0x100374c9  call    __chkstk
0x100374ce  mov     eax, ___security_cookie
0x100374d3  xor     eax, ebp
0x100374d5  mov     [ebp+var_4], eax
0x100374d8  and     [ebp+var_1ABC], 0
0x100374df  mov     eax, [ebp+arg_0]
0x100374e2  mov     ecx, [ebp+arg_4]
0x100374e5  push    esi
0x100374e6  xor     esi, esi
0x100374e8  mov     [ebp+FileHandle], eax
0x100374ee  push    edi
0x100374ef  xor     edi, edi
0x100374f1  mov     [ebp+lpBuffer], ecx
0x100374f7  mov     [ebp+var_1AC0], esi
0x100374fd  cmp     [ebp+nNumberOfBytesToWrite], esi
0x10037500  jnz     short loc_10037509
0x10037502  xor     eax, eax
0x10037504  jmp     loc_10037D16
0x10037509  test    ecx, ecx
0x1003750b  jnz     short loc_1003752C
0x1003750d  call    ___doserrno
0x10037512  and     [eax], esi
0x10037514  call    __errno
0x10037519  mov     dword ptr [eax], 16h
0x1003751f  call    __invalid_parameter_noinfo
0x10037524  or      eax, 0FFFFFFFFh
0x10037527  jmp     loc_10037D16
0x1003752c  mov     edx, eax
0x1003752e  mov     ecx, eax
0x10037530  sar     edx, 5
0x10037533  and     ecx, 1Fh
0x10037536  shl     ecx, 6
0x10037539  mov     [ebp+var_1AD8], edx
0x1003753f  push    ebx
0x10037540  mov     edx, ___pioinfo[edx*4]
0x10037547  mov     [ebp+var_1ADC], ecx
0x1003754d  mov     bl, [ecx+edx+24h]
0x10037551  add     bl, bl
0x10037553  sar     bl, 1
0x10037555  cmp     bl, 2
0x10037558  jz      short loc_1003755F
0x1003755a  cmp     bl, 1
0x1003755d  jnz     short loc_1003758A
0x1003755f  mov     eax, [ebp+nNumberOfBytesToWrite]
0x10037562  not     eax
0x10037564  test    al, 1
0x10037566  jnz     short loc_10037584
0x10037568  call    ___doserrno
0x1003756d  and     [eax], esi
0x1003756f  call    __errno
0x10037574  mov     dword ptr [eax], 16h
0x1003757a  call    __invalid_parameter_noinfo
0x1003757f  jmp     loc_10037D0C
0x10037584  mov     eax, [ebp+FileHandle]
0x1003758a  test    byte ptr [ecx+edx+4], 20h
0x1003758f  jz      short loc_100375A0
0x10037591  push    2; dwMoveMethod
0x10037593  push    0
0x10037595  push    0; liDistanceToMove
0x10037597  push    eax; FileHandle
0x10037598  call    __lseeki64_nolock
0x1003759d  add     esp, 10h
0x100375a0  push    [ebp+FileHandle]; FileHandle
0x100375a6  call    __isatty
0x100375ab  pop     ecx
0x100375ac  test    eax, eax
0x100375ae  jz      loc_10037904
0x100375b4  mov     eax, [ebp+var_1AD8]
0x100375ba  mov     ecx, [ebp+var_1ADC]
0x100375c0  mov     eax, ___pioinfo[eax*4]
0x100375c7  test    byte ptr [ecx+eax+4], 80h
0x100375cc  jz      loc_10037904
0x100375d2  call    __getptd
0x100375d7  xor     ecx, ecx
0x100375d9  mov     eax, [eax+6Ch]
0x100375dc  cmp     [eax+0A8h], ecx
0x100375e2  lea     eax, [ebp+Mode]
0x100375e8  push    eax; lpMode
0x100375e9  mov     eax, [ebp+var_1AD8]
0x100375ef  setz    cl
0x100375f2  mov     [ebp+var_1AC4], ecx
0x100375f8  mov     ecx, [ebp+var_1ADC]
0x100375fe  mov     eax, ___pioinfo[eax*4]
0x10037605  push    dword ptr [ecx+eax]; hConsoleHandle
0x10037608  call    ds:__imp__GetConsoleMode@8
0x1003760e  test    eax, eax
0x10037610  jz      loc_10037904
0x10037616  cmp     [ebp+var_1AC4], esi
0x1003761c  jz      short loc_10037626
0x1003761e  test    bl, bl
0x10037620  jz      loc_10037904
0x10037626  call    ds:__imp__GetConsoleCP@0
0x1003762c  mov     edx, [ebp+lpBuffer]
0x10037632  xor     ecx, ecx
0x10037634  and     [ebp+FileHandle], ecx
0x1003763a  mov     [ebp+CodePage], eax
0x10037640  mov     dword ptr [ebp+DstCh], ecx
0x10037646  mov     [ebp+SrcCh], edx
0x1003764c  cmp     [ebp+nNumberOfBytesToWrite], ecx
0x1003764f  jbe     loc_10037CD6
0x10037655  mov     eax, [ebp+SrcCh]
0x1003765b  xor     edx, edx
0x1003765d  mov     [ebp+var_1AC0], edx
0x10037663  mov     [ebp+var_1AEC], 0Ah
0x1003766d  and     [ebp+var_1AC4], edi
0x10037673  test    bl, bl
0x10037675  jnz     loc_10037829
0x1003767b  mov     dl, [eax]
0x1003767d  xor     eax, eax
0x1003767f  mov     ecx, [ebp+var_1ADC]
0x10037685  cmp     dl, 0Ah
0x10037688  setz    al
0x1003768b  mov     [ebp+Mode], eax
0x10037691  mov     eax, [ebp+var_1AD8]
0x10037697  mov     eax, ___pioinfo[eax*4]
0x1003769e  mov     [ebp+var_1AC4], eax
0x100376a4  cmp     [ecx+eax+38h], edi
0x100376a8  jz      short loc_100376C6
0x100376aa  mov     al, [ecx+eax+34h]
0x100376ae  mov     [ebp+MultiByteStr], al
0x100376b1  mov     eax, [ebp+var_1AC4]
0x100376b7  mov     [ebp+var_B], dl
0x100376ba  push    2
0x100376bc  and     [ecx+eax+38h], edi
0x100376c0  lea     eax, [ebp+MultiByteStr]
0x100376c3  push    eax
0x100376c4  jmp     short loc_10037720
0x100376c6  movsx   eax, dl
0x100376c9  push    eax; C
0x100376ca  call    _isleadbyte
0x100376cf  pop     ecx
0x100376d0  test    eax, eax
0x100376d2  jz      short loc_10037718
0x100376d4  mov     eax, [ebp+lpBuffer]
0x100376da  mov     edx, [ebp+SrcCh]
0x100376e0  sub     eax, edx
0x100376e2  add     eax, [ebp+nNumberOfBytesToWrite]
0x100376e5  cmp     eax, 1
0x100376e8  jbe     loc_100378C9
0x100376ee  push    2; SrcSizeInBytes
0x100376f0  push    edx; SrcCh
0x100376f1  lea     eax, [ebp+DstCh]
0x100376f7  push    eax; DstCh
0x100376f8  call    _mbtowc
0x100376fd  add     esp, 0Ch
0x10037700  cmp     eax, 0FFFFFFFFh
0x10037703  jz      loc_10037A0E
0x10037709  mov     eax, [ebp+SrcCh]
0x1003770f  inc     eax
0x10037710  inc     [ebp+var_1AC0]
0x10037716  jmp     short loc_1003773E
0x10037718  push    1; SrcSizeInBytes
0x1003771a  push    [ebp+SrcCh]; SrcCh
0x10037720  lea     eax, [ebp+DstCh]
0x10037726  push    eax; DstCh
0x10037727  call    _mbtowc
0x1003772c  add     esp, 0Ch
0x1003772f  cmp     eax, 0FFFFFFFFh
0x10037732  jz      loc_10037A0E
0x10037738  mov     eax, [ebp+SrcCh]
0x1003773e  xor     ecx, ecx
0x10037740  inc     eax
0x10037741  inc     [ebp+var_1AC0]
0x10037747  push    ecx; lpUsedDefaultChar
0x10037748  push    ecx; lpDefaultChar
0x10037749  push    5; cbMultiByte
0x1003774b  mov     [ebp+SrcCh], eax
0x10037751  lea     eax, [ebp+MultiByteStr]
0x10037754  push    eax; lpMultiByteStr
0x10037755  push    1; cchWideChar
0x10037757  lea     eax, [ebp+DstCh]
0x1003775d  push    eax; lpWideCharStr
0x1003775e  push    ecx; dwFlags
0x1003775f  push    [ebp+CodePage]; CodePage
0x10037765  call    ds:__imp__WideCharToMultiByte@32
0x1003776b  mov     [ebp+var_1AC4], eax
0x10037771  test    eax, eax
0x10037773  jz      loc_10037A0E
0x10037779  push    0; lpOverlapped
0x1003777b  lea     ecx, [ebp+FileHandle]
0x10037781  push    ecx; lpNumberOfBytesWritten
0x10037782  mov     ecx, [ebp+var_1ADC]
0x10037788  push    eax; nNumberOfBytesToWrite
0x10037789  lea     eax, [ebp+MultiByteStr]
0x1003778c  push    eax; lpBuffer
0x1003778d  mov     eax, [ebp+var_1AD8]
0x10037793  mov     eax, ___pioinfo[eax*4]
0x1003779a  push    dword ptr [ecx+eax]; hFile
0x1003779d  call    ds:__imp__WriteFile@20
0x100377a3  test    eax, eax
0x100377a5  jz      loc_100378F7
0x100377ab  mov     esi, [ebp+var_1AC0]
0x100377b1  mov     ecx, [ebp+var_1ABC]
0x100377b7  add     esi, ecx
0x100377b9  mov     eax, [ebp+var_1AC4]
0x100377bf  cmp     [ebp+FileHandle], eax
0x100377c5  jl      loc_10037A14
0x100377cb  cmp     [ebp+Mode], edi
0x100377d1  jz      short loc_1003781E
0x100377d3  mov     ecx, [ebp+var_1ADC]
0x100377d9  lea     eax, [ebp+FileHandle]
0x100377df  push    0; lpOverlapped
0x100377e1  push    eax; lpNumberOfBytesWritten
0x100377e2  push    1; nNumberOfBytesToWrite
0x100377e4  lea     eax, [ebp+MultiByteStr]
0x100377e7  mov     [ebp+MultiByteStr], 0Dh
0x100377eb  push    eax; lpBuffer
0x100377ec  mov     eax, [ebp+var_1AD8]
0x100377f2  mov     eax, ___pioinfo[eax*4]
0x100377f9  push    dword ptr [ecx+eax]; hFile
0x100377fc  call    ds:__imp__WriteFile@20
0x10037802  test    eax, eax
0x10037804  jz      loc_100378F7
0x1003780a  cmp     [ebp+FileHandle], 1
0x10037811  jl      loc_10037A0E
0x10037817  inc     [ebp+var_1ABC]
0x1003781d  inc     esi
0x1003781e  mov     ecx, dword ptr [ebp+DstCh]
0x10037824  jmp     loc_100378AF
0x10037829  cmp     bl, 1
0x1003782c  jz      short loc_10037833
0x1003782e  cmp     bl, 2
0x10037831  jnz     short loc_10037866
0x10037833  movzx   ecx, word ptr [eax]
0x10037836  xor     edx, edx
0x10037838  cmp     cx, word ptr [ebp+var_1AEC]
0x1003783f  mov     dword ptr [ebp+DstCh], ecx
0x10037845  setz    dl
0x10037848  add     eax, 2
0x1003784b  mov     [ebp+var_1AC4], edx
0x10037851  mov     edx, [ebp+var_1AC0]
0x10037857  add     edx, 2
0x1003785a  mov     [ebp+SrcCh], eax
0x10037860  mov     [ebp+var_1AC0], edx
0x10037866  cmp     bl, 1
0x10037869  jz      short loc_10037870
0x1003786b  cmp     bl, 2
0x1003786e  jnz     short loc_100378BB
0x10037870  push    ecx; Character
0x10037871  call    __putwch_nolock
0x10037876  pop     ecx
0x10037877  mov     ecx, dword ptr [ebp+DstCh]
0x1003787d  cmp     ax, cx
0x10037880  jnz     short loc_100378F7
0x10037882  add     esi, 2
0x10037885  cmp     [ebp+var_1AC4], edi
0x1003788b  jz      short loc_100378AF
0x1003788d  push    0Dh
0x1003788f  pop     eax
0x10037890  push    eax; Character
0x10037891  mov     dword ptr [ebp+DstCh], eax
0x10037897  call    __putwch_nolock
0x1003789c  pop     ecx
0x1003789d  mov     ecx, dword ptr [ebp+DstCh]
0x100378a3  cmp     ax, cx
0x100378a6  jnz     short loc_100378F7
0x100378a8  inc     esi
0x100378a9  inc     [ebp+var_1ABC]
0x100378af  mov     edx, [ebp+var_1AC0]
0x100378b5  mov     eax, [ebp+SrcCh]
0x100378bb  cmp     edx, [ebp+nNumberOfBytesToWrite]
0x100378be  jb      loc_1003766D
0x100378c4  jmp     loc_10037A0E
0x100378c9  mov     ebx, [ebp+var_1AD8]
0x100378cf  inc     esi
0x100378d0  mov     al, [edx]
0x100378d2  mov     edx, [ebp+var_1ADC]
0x100378d8  mov     ecx, ___pioinfo[ebx*4]
0x100378df  mov     [edx+ecx+34h], al
0x100378e3  mov     eax, ___pioinfo[ebx*4]
0x100378ea  mov     dword ptr [edx+eax+38h], 1
0x100378f2  jmp     loc_10037A0E
0x100378f7  call    ds:__imp__GetLastError@0
0x100378fd  mov     edi, eax
0x100378ff  jmp     loc_10037A0E
0x10037904  mov     eax, [ebp+var_1AD8]
0x1003790a  mov     ecx, ___pioinfo[eax*4]
0x10037911  mov     eax, [ebp+var_1ADC]
0x10037917  test    byte ptr [eax+ecx+4], 80h
0x1003791c  jz      loc_10037C97
0x10037922  mov     edx, [ebp+lpBuffer]
0x10037928  xor     edi, edi
0x1003792a  mov     dword ptr [ebp+DstCh], edi
0x10037930  test    bl, bl
0x10037932  jnz     loc_10037A46
0x10037938  mov     ebx, [ebp+nNumberOfBytesToWrite]
0x1003793b  mov     [ebp+FileHandle], edx
0x10037941  test    ebx, ebx
0x10037943  jz      loc_10037CD6
0x10037949  xor     ecx, ecx
0x1003794b  lea     edi, [ebp+Buffer]
0x10037951  mov     eax, edx
0x10037953  mov     [ebp+var_1AC4], ecx
0x10037959  sub     eax, [ebp+lpBuffer]
0x1003795f  cmp     eax, ebx
0x10037961  jnb     short loc_100379A7
0x10037963  mov     cl, [edx]
  ... truncated ...
```
