# I_UrlCacheReadAndValidateMetaDataFile

- ea: `0x1800077b0`
- end: `0x180007a33`
- name: `I_UrlCacheReadAndValidateMetaDataFile`
- size: `643`
- prototype: `__int64 __usercall@<rax>(HANDLE hFile@<rcx>, __int64)`
- caller_count: `7`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180001154`
- `0x180001460`
- `0x180002460`
- `0x180003274`
- `0x180004b40`
- `0x1800052d0`
- `0x180006d40`

## callees

- `0x180005980`
- `0x1800077b0`
- `0x18000a990`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800079f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800079f7`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800077e8`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800077e8`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000781c`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180007889`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800078ee`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000781c`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180007889`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800078ee`

## pseudocode

```c
_DWORD *__fastcall I_UrlCacheReadAndValidateMetaDataFile(HANDLE hFile, _QWORD *a2, _QWORD *a3, _DWORD *a4, _QWORD *a5)
{
  char *v5; // r15
  _DWORD *v7; // rbx
  DWORD v8; // edi
  DWORD FileSize; // esi
  DWORD v13; // esi
  _DWORD *v14; // rax
  DWORD v15; // ecx
  unsigned int v16; // edx
  unsigned int v17; // edx
  int v18; // ecx
  unsigned int v19; // r9d
  unsigned int v20; // r9d
  _DWORD *v21; // r11
  char *v22; // r10
  int v23; // edx
  DWORD NumberOfBytesRead; // [rsp+78h] [rbp+10h] BYREF
  unsigned int Buffer; // [rsp+80h] [rbp+18h] BYREF

  v5 = 0;
  Buffer = 0;
  v7 = 0;
  NumberOfBytesRead = 0;
  v8 = 0;
  FileSize = GetFileSize(hFile, 0);
  if ( FileSize - 4 <= 0xFFFFFB )
  {
    if ( !ReadFile(hFile, &Buffer, 4u, &NumberOfBytesRead, 0) || NumberOfBytesRead != 4 )
      goto LABEL_37;
    if ( (Buffer == 112 || Buffer == 24 || Buffer == 72) && Buffer <= FileSize )
    {
      v13 = FileSize - Buffer;
      v8 = v13;
      v14 = (_DWORD *)PkiZeroAlloc(v13 + 112LL);
      v7 = v14;
      if ( !v14 )
        goto LABEL_36;
      *v14 = 112;
      if ( !ReadFile(hFile, v14 + 1, Buffer - 4, &NumberOfBytesRead, 0) || Buffer - 4LL != NumberOfBytesRead )
        goto LABEL_41;
      if ( Buffer <= 0x50 )
      {
        v7[6] = 40;
        v7[16] = 16;
        v7[20] = 32;
LABEL_13:
        if ( v13 && (!ReadFile(hFile, v7 + 28, v13, &NumberOfBytesRead, 0) || v13 != NumberOfBytesRead) )
          goto LABEL_41;
        v15 = v7[2];
        if ( v15 <= v13 >> 2 )
        {
          v16 = v7[3];
          if ( (v16 & 1) == 0 )
          {
            v17 = v16 >> 1;
            if ( v17 )
            {
              v18 = 4 * v15;
              if ( v17 <= (v13 - v18) >> 1 )
              {
                v5 = (char *)v7 + (unsigned int)(v18 + 112);
                *(_WORD *)&v5[2 * v17 - 2] = 0;
                v19 = v7[25];
                if ( (v19 & 1) == 0 )
                {
                  v20 = v19 >> 1;
                  v21 = v7 + 28;
                  v22 = 0;
                  if ( !v20 )
                    goto LABEL_24;
                  v23 = 2 * v17;
                  if ( v20 <= (v13 - v18 - v23) >> 1 )
                  {
                    v22 = (char *)v7 + (unsigned int)(v18 + 112 + v23);
                    *(_WORD *)&v22[2 * v20 - 2] = 0;
                    goto LABEL_24;
                  }
                }
                v5 = 0;
              }
            }
          }
        }
        goto LABEL_35;
      }
      if ( v7[6] == 40 && v7[16] == 16 && v7[20] == 32 )
        goto LABEL_13;
    }
  }
LABEL_35:
  SetLastError(0x80092003);
LABEL_36:
  if ( v7 )
  {
LABEL_41:
    operator delete(v7);
    v7 = 0;
  }
LABEL_37:
  v21 = 0;
  v22 = 0;
LABEL_24:
  if ( a2 )
    *a2 = v21;
  if ( a3 )
    *a3 = v5;
  if ( a5 )
    *a5 = v22;
  if ( a4 )
    *a4 = v8 + 112;
  return v7;
}

```

## disassembly

```asm
0x1800077b0  mov     [rsp+arg_0], rbx
0x1800077b5  push    rbp
0x1800077b6  push    rsi
0x1800077b7  push    rdi
0x1800077b8  push    r12
0x1800077ba  push    r13
0x1800077bc  push    r14
0x1800077be  push    r15
0x1800077c0  sub     rsp, 30h
0x1800077c4  xor     r15d, r15d
0x1800077c7  mov     r14, rdx
0x1800077ca  xor     edx, edx; lpFileSizeHigh
0x1800077cc  mov     [rsp+68h+Buffer], r15d
0x1800077d4  mov     ebx, r15d
0x1800077d7  mov     [rsp+68h+NumberOfBytesRead], r15d
0x1800077dc  mov     edi, r15d
0x1800077df  mov     r12, r9
0x1800077e2  mov     r13, r8
0x1800077e5  mov     rbp, rcx
0x1800077e8  call    cs:__imp_GetFileSize
0x1800077ee  mov     esi, eax
0x1800077f0  lea     r10d, [rax-4]
0x1800077f4  cmp     r10d, 0FFFFFBh
0x1800077fb  ja      loc_1800079F2
0x180007801  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180007806  mov     [rsp+68h+lpOverlapped], r15; lpOverlapped
0x18000780b  mov     r8d, 4; nNumberOfBytesToRead
0x180007811  lea     rdx, [rsp+68h+Buffer]; lpBuffer
0x180007819  mov     rcx, rbp; hFile
0x18000781c  call    cs:__imp_ReadFile
0x180007822  test    eax, eax
0x180007824  jz      loc_180007A02
0x18000782a  cmp     [rsp+68h+NumberOfBytesRead], 4
0x18000782f  jnz     loc_180007A02
0x180007835  mov     eax, [rsp+68h+Buffer]
0x18000783c  cmp     eax, 70h ; 'p'
0x18000783f  jnz     loc_180007A0A
0x180007845  cmp     eax, esi
0x180007847  ja      loc_1800079F2
0x18000784d  sub     esi, eax
0x18000784f  mov     edi, esi
0x180007851  lea     rcx, [rsi+70h]; uBytes
0x180007855  call    PkiZeroAlloc
0x18000785a  mov     rbx, rax
0x18000785d  test    rax, rax
0x180007860  jz      loc_1800079FD
0x180007866  mov     dword ptr [rax], 70h ; 'p'
0x18000786c  lea     rdx, [rax+4]; lpBuffer
0x180007870  mov     r8d, [rsp+68h+Buffer]
0x180007878  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18000787d  add     r8d, 0FFFFFFFCh; nNumberOfBytesToRead
0x180007881  mov     [rsp+68h+lpOverlapped], r15; lpOverlapped
0x180007886  mov     rcx, rbp; hFile
0x180007889  call    cs:__imp_ReadFile
0x18000788f  test    eax, eax
0x180007891  jz      loc_180007A1D
0x180007897  mov     edx, [rsp+68h+Buffer]
0x18000789e  mov     eax, [rsp+68h+NumberOfBytesRead]
0x1800078a2  lea     rcx, [rdx-4]
0x1800078a6  cmp     rcx, rax
0x1800078a9  jnz     loc_180007A1D
0x1800078af  cmp     edx, 50h ; 'P'
0x1800078b2  jbe     loc_1800079D5
0x1800078b8  cmp     dword ptr [rbx+18h], 28h ; '('
0x1800078bc  jnz     loc_1800079F2
0x1800078c2  cmp     dword ptr [rbx+40h], 10h
0x1800078c6  jnz     loc_1800079F2
0x1800078cc  cmp     dword ptr [rbx+50h], 20h ; ' '
0x1800078d0  jnz     loc_1800079F2
0x1800078d6  test    esi, esi
0x1800078d8  jz      short loc_180007906
0x1800078da  lea     rdx, [rbx+70h]; lpBuffer
0x1800078de  mov     [rsp+68h+lpOverlapped], r15; lpOverlapped
0x1800078e3  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800078e8  mov     r8d, edi; nNumberOfBytesToRead
0x1800078eb  mov     rcx, rbp; hFile
0x1800078ee  call    cs:__imp_ReadFile
0x1800078f4  test    eax, eax
0x1800078f6  jz      loc_180007A1D
0x1800078fc  cmp     edi, [rsp+68h+NumberOfBytesRead]
0x180007900  jnz     loc_180007A1D
0x180007906  mov     ecx, [rbx+8]
0x180007909  mov     eax, edi
0x18000790b  shr     eax, 2
0x18000790e  cmp     ecx, eax
0x180007910  ja      loc_1800079F2
0x180007916  mov     edx, [rbx+0Ch]
0x180007919  test    dl, 1
0x18000791c  jnz     loc_1800079F2
0x180007922  shr     edx, 1
0x180007924  jz      loc_1800079F2
0x18000792a  lea     ecx, ds:0[rcx*4]
0x180007931  mov     r8d, edi
0x180007934  sub     r8d, ecx
0x180007937  mov     eax, r8d
0x18000793a  shr     eax, 1
0x18000793c  cmp     edx, eax
0x18000793e  ja      loc_1800079F2
0x180007944  lea     esi, [rcx+70h]
0x180007947  xor     eax, eax
0x180007949  mov     r15d, esi
0x18000794c  lea     ecx, [rdx-1]
0x18000794f  add     r15, rbx
0x180007952  mov     [r15+rcx*2], ax
0x180007957  mov     r9d, [rbx+64h]
0x18000795b  test    r9b, 1
0x18000795f  jnz     loc_1800079EF
0x180007965  shr     r9d, 1
0x180007968  lea     r11, [rbx+70h]
0x18000796c  mov     r10d, eax
0x18000796f  jz      short loc_18000798E
0x180007971  add     edx, edx
0x180007973  sub     r8d, edx
0x180007976  shr     r8d, 1
0x180007979  cmp     r9d, r8d
0x18000797c  ja      short loc_1800079EF
0x18000797e  lea     r10d, [rsi+rdx]
0x180007982  add     r10, rbx
0x180007985  lea     ecx, [r9-1]
0x180007989  mov     [r10+rcx*2], ax
0x18000798e  test    r14, r14
0x180007991  jz      short loc_180007996
0x180007993  mov     [r14], r11
0x180007996  test    r13, r13
0x180007999  jnz     loc_180007A2A
0x18000799f  mov     rax, [rsp+68h+arg_20]
0x1800079a7  test    rax, rax
0x1800079aa  jz      short loc_1800079AF
0x1800079ac  mov     [rax], r10
0x1800079af  test    r12, r12
0x1800079b2  jnz     short loc_1800079CC
0x1800079b4  mov     rax, rbx
0x1800079b7  mov     rbx, [rsp+68h+arg_0]
0x1800079bc  add     rsp, 30h
0x1800079c0  pop     r15
0x1800079c2  pop     r14
0x1800079c4  pop     r13
0x1800079c6  pop     r12
0x1800079c8  pop     rdi
0x1800079c9  pop     rsi
0x1800079ca  pop     rbp
0x1800079cb  retn
0x1800079cc  lea     eax, [rdi+70h]
0x1800079cf  mov     [r12], eax
0x1800079d3  jmp     short loc_1800079B4
0x1800079d5  mov     dword ptr [rbx+18h], 28h ; '('
0x1800079dc  mov     dword ptr [rbx+40h], 10h
0x1800079e3  mov     dword ptr [rbx+50h], 20h ; ' '
0x1800079ea  jmp     loc_1800078D6
0x1800079ef  xor     r15d, r15d
0x1800079f2  mov     ecx, 80092003h; dwErrCode
0x1800079f7  call    cs:__imp_SetLastError
0x1800079fd  test    rbx, rbx
0x180007a00  jnz     short loc_180007A1D
0x180007a02  mov     r11, r15
0x180007a05  xor     r10d, r10d
0x180007a08  jmp     short loc_18000798E
0x180007a0a  cmp     eax, 18h
0x180007a0d  jz      loc_180007845
0x180007a13  cmp     eax, 48h ; 'H'
0x180007a16  jnz     short loc_1800079F2
0x180007a18  jmp     loc_180007845
0x180007a1d  mov     rcx, rbx; hMem
0x180007a20  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007a25  mov     rbx, r15
0x180007a28  jmp     short loc_180007A02
0x180007a2a  mov     [r13+0], r15
0x180007a2e  jmp     loc_18000799F
```
