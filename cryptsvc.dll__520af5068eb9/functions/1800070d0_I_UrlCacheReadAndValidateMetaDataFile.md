# I_UrlCacheReadAndValidateMetaDataFile

- ea: `0x1800070d0`
- end: `0x18000735c`
- name: `I_UrlCacheReadAndValidateMetaDataFile`
- size: `652`
- prototype: `_DWORD *__fastcall(HANDLE hFile, _QWORD *, _QWORD *, _DWORD *, _QWORD *)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180004c90`
- `0x180005bd0`
- `0x180007370`
- `0x180007dc0`

## callees

- `0x1800068b0`
- `0x1800070d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007318`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007354`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007318`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007354`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000717a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000717a`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000713c`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800071af`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180007214`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000713c`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800071af`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180007214`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180007108`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180007108`

## pseudocode

```c
_DWORD *__fastcall I_UrlCacheReadAndValidateMetaDataFile(HANDLE hFile, _QWORD *a2, _QWORD *a3, _DWORD *a4, _QWORD *a5)
{
  _DWORD *v6; // rbx
  DWORD v7; // edi
  DWORD FileSize; // esi
  DWORD v12; // esi
  _DWORD *v13; // rax
  DWORD v14; // ecx
  unsigned int v15; // edx
  unsigned int v16; // edx
  int v17; // ecx
  DWORD v18; // r8d
  char *v19; // r10
  unsigned int v20; // r9d
  unsigned int v21; // r9d
  _DWORD *v22; // rbp
  char *v23; // rsi
  int v24; // edx
  DWORD NumberOfBytesRead; // [rsp+78h] [rbp+10h] BYREF
  unsigned int Buffer; // [rsp+80h] [rbp+18h] BYREF

  Buffer = 0;
  v6 = 0;
  NumberOfBytesRead = 0;
  v7 = 0;
  FileSize = GetFileSize(hFile, 0);
  if ( FileSize - 4 <= 0xFFFFFB )
  {
    if ( !ReadFile(hFile, &Buffer, 4u, &NumberOfBytesRead, 0) || NumberOfBytesRead != 4 )
      goto LABEL_35;
    if ( (Buffer == 112 || Buffer == 72 || Buffer == 24) && Buffer <= FileSize )
    {
      v12 = FileSize - Buffer;
      v7 = v12;
      v13 = LocalAlloc(0x40u, v12 + 112LL);
      v6 = v13;
      if ( !v13 )
      {
        SetLastError(0x8007000E);
        goto LABEL_35;
      }
      *v13 = 112;
      if ( !ReadFile(hFile, v13 + 1, Buffer - 4, &NumberOfBytesRead, 0) || Buffer - 4LL != NumberOfBytesRead )
        goto LABEL_36;
      if ( Buffer <= 0x50 )
      {
        v6[6] = 40;
        v6[16] = 16;
        v6[20] = 32;
      }
      else if ( v6[6] != 40 || v6[16] != 16 || v6[20] != 32 )
      {
        goto LABEL_34;
      }
      if ( v12 && (!ReadFile(hFile, v6 + 28, v12, &NumberOfBytesRead, 0) || v12 != NumberOfBytesRead) )
        goto LABEL_36;
      v14 = v6[2];
      if ( v14 <= v12 >> 2 )
      {
        v15 = v6[3];
        if ( (v15 & 1) == 0 )
        {
          v16 = v15 >> 1;
          if ( v16 )
          {
            v17 = 4 * v14;
            v18 = v12 - v17;
            if ( v16 <= (v12 - v17) >> 1 )
            {
              v19 = (char *)v6 + (unsigned int)(v17 + 112);
              *(_WORD *)&v19[2 * v16 - 2] = 0;
              v20 = v6[25];
              if ( (v20 & 1) == 0 )
              {
                v21 = v20 >> 1;
                v22 = v6 + 28;
                v23 = 0;
                if ( !v21 )
                  goto LABEL_24;
                v24 = 2 * v16;
                if ( v21 <= (v18 - v24) >> 1 )
                {
                  v23 = (char *)v6 + (unsigned int)(v17 + 112 + v24);
                  *(_WORD *)&v23[2 * v21 - 2] = 0;
                  goto LABEL_24;
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_34:
  SetLastError(0x80092003);
  if ( v6 )
  {
LABEL_36:
    PkiFree(v6);
    v6 = 0;
  }
LABEL_35:
  v22 = 0;
  v19 = 0;
  v23 = 0;
LABEL_24:
  if ( a2 )
    *a2 = v22;
  if ( a3 )
    *a3 = v19;
  if ( a5 )
    *a5 = v23;
  if ( a4 )
    *a4 = v7 + 112;
  return v6;
}

```

## disassembly

```asm
0x1800070d0  mov     [rsp+arg_0], rbx
0x1800070d5  push    rbp
0x1800070d6  push    rsi
0x1800070d7  push    rdi
0x1800070d8  push    r12
0x1800070da  push    r13
0x1800070dc  push    r14
0x1800070de  push    r15
0x1800070e0  sub     rsp, 30h
0x1800070e4  xor     r13d, r13d
0x1800070e7  mov     r12, rdx
0x1800070ea  xor     edx, edx; lpFileSizeHigh
0x1800070ec  mov     [rsp+68h+Buffer], r13d
0x1800070f4  mov     ebx, r13d
0x1800070f7  mov     [rsp+68h+NumberOfBytesRead], r13d
0x1800070fc  mov     edi, r13d
0x1800070ff  mov     r14, r9
0x180007102  mov     r15, r8
0x180007105  mov     rbp, rcx
0x180007108  call    cs:__imp_GetFileSize
0x18000710e  mov     esi, eax
0x180007110  lea     r10d, [rax-4]
0x180007114  cmp     r10d, 0FFFFFBh
0x18000711b  ja      loc_180007313
0x180007121  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180007126  mov     [rsp+68h+lpOverlapped], r13; lpOverlapped
0x18000712b  mov     r8d, 4; nNumberOfBytesToRead
0x180007131  lea     rdx, [rsp+68h+Buffer]; lpBuffer
0x180007139  mov     rcx, rbp; hFile
0x18000713c  call    cs:__imp_ReadFile
0x180007142  test    eax, eax
0x180007144  jz      loc_180007323
0x18000714a  cmp     [rsp+68h+NumberOfBytesRead], 4
0x18000714f  jnz     loc_180007323
0x180007155  mov     eax, [rsp+68h+Buffer]
0x18000715c  cmp     eax, 70h ; 'p'
0x18000715f  jnz     loc_18000733B
0x180007165  cmp     eax, esi
0x180007167  ja      loc_180007313
0x18000716d  sub     esi, eax
0x18000716f  mov     ecx, 40h ; '@'; uFlags
0x180007174  mov     edi, esi
0x180007176  lea     rdx, [rsi+70h]; uBytes
0x18000717a  call    cs:__imp_LocalAlloc
0x180007180  mov     rbx, rax
0x180007183  test    rax, rax
0x180007186  jz      loc_18000734F
0x18000718c  mov     dword ptr [rax], 70h ; 'p'
0x180007192  lea     rdx, [rax+4]; lpBuffer
0x180007196  mov     r8d, [rsp+68h+Buffer]
0x18000719e  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800071a3  add     r8d, 0FFFFFFFCh; nNumberOfBytesToRead
0x1800071a7  mov     [rsp+68h+lpOverlapped], r13; lpOverlapped
0x1800071ac  mov     rcx, rbp; hFile
0x1800071af  call    cs:__imp_ReadFile
0x1800071b5  test    eax, eax
0x1800071b7  jz      loc_18000732E
0x1800071bd  mov     edx, [rsp+68h+Buffer]
0x1800071c4  mov     eax, [rsp+68h+NumberOfBytesRead]
0x1800071c8  lea     rcx, [rdx-4]
0x1800071cc  cmp     rcx, rax
0x1800071cf  jnz     loc_18000732E
0x1800071d5  cmp     edx, 50h ; 'P'
0x1800071d8  jbe     loc_1800072F9
0x1800071de  cmp     dword ptr [rbx+18h], 28h ; '('
0x1800071e2  jnz     loc_180007313
0x1800071e8  cmp     dword ptr [rbx+40h], 10h
0x1800071ec  jnz     loc_180007313
0x1800071f2  cmp     dword ptr [rbx+50h], 20h ; ' '
0x1800071f6  jnz     loc_180007313
0x1800071fc  test    esi, esi
0x1800071fe  jz      short loc_18000722C
0x180007200  lea     rdx, [rbx+70h]; lpBuffer
0x180007204  mov     [rsp+68h+lpOverlapped], r13; lpOverlapped
0x180007209  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18000720e  mov     r8d, edi; nNumberOfBytesToRead
0x180007211  mov     rcx, rbp; hFile
0x180007214  call    cs:__imp_ReadFile
0x18000721a  test    eax, eax
0x18000721c  jz      loc_18000732E
0x180007222  cmp     edi, [rsp+68h+NumberOfBytesRead]
0x180007226  jnz     loc_18000732E
0x18000722c  mov     ecx, [rbx+8]
0x18000722f  mov     eax, edi
0x180007231  shr     eax, 2
0x180007234  cmp     ecx, eax
0x180007236  ja      loc_180007313
0x18000723c  mov     edx, [rbx+0Ch]
0x18000723f  test    dl, 1
0x180007242  jnz     loc_180007313
0x180007248  shr     edx, 1
0x18000724a  jz      loc_180007313
0x180007250  lea     ecx, ds:0[rcx*4]
0x180007257  mov     r8d, edi
0x18000725a  sub     r8d, ecx
0x18000725d  mov     eax, r8d
0x180007260  shr     eax, 1
0x180007262  cmp     edx, eax
0x180007264  ja      loc_180007313
0x18000726a  lea     r11d, [rcx+70h]
0x18000726e  mov     r10d, r11d
0x180007271  lea     eax, [rdx-1]
0x180007274  add     r10, rbx
0x180007277  mov     [r10+rax*2], r13w
0x18000727c  mov     r9d, [rbx+64h]
0x180007280  test    r9b, 1
0x180007284  jnz     loc_180007313
0x18000728a  shr     r9d, 1
0x18000728d  lea     rbp, [rbx+70h]
0x180007291  mov     rsi, r13
0x180007294  jz      short loc_1800072B3
0x180007296  add     edx, edx
0x180007298  sub     r8d, edx
0x18000729b  shr     r8d, 1
0x18000729e  cmp     r9d, r8d
0x1800072a1  ja      short loc_180007313
0x1800072a3  lea     esi, [r11+rdx]
0x1800072a7  add     rsi, rbx
0x1800072aa  lea     eax, [r9-1]
0x1800072ae  mov     [rsi+rax*2], r13w
0x1800072b3  test    r12, r12
0x1800072b6  jz      short loc_1800072BC
0x1800072b8  mov     [r12], rbp
0x1800072bc  test    r15, r15
0x1800072bf  jz      short loc_1800072C4
0x1800072c1  mov     [r15], r10
0x1800072c4  mov     rax, [rsp+68h+arg_20]
0x1800072cc  test    rax, rax
0x1800072cf  jz      short loc_1800072D4
0x1800072d1  mov     [rax], rsi
0x1800072d4  test    r14, r14
0x1800072d7  jnz     short loc_1800072F1
0x1800072d9  mov     rax, rbx
0x1800072dc  mov     rbx, [rsp+68h+arg_0]
0x1800072e1  add     rsp, 30h
0x1800072e5  pop     r15
0x1800072e7  pop     r14
0x1800072e9  pop     r13
0x1800072eb  pop     r12
0x1800072ed  pop     rdi
0x1800072ee  pop     rsi
0x1800072ef  pop     rbp
0x1800072f0  retn
0x1800072f1  lea     eax, [rdi+70h]
0x1800072f4  mov     [r14], eax
0x1800072f7  jmp     short loc_1800072D9
0x1800072f9  mov     dword ptr [rbx+18h], 28h ; '('
0x180007300  mov     dword ptr [rbx+40h], 10h
0x180007307  mov     dword ptr [rbx+50h], 20h ; ' '
0x18000730e  jmp     loc_1800071FC
0x180007313  mov     ecx, 80092003h; dwErrCode
0x180007318  call    cs:__imp_SetLastError
0x18000731e  test    rbx, rbx
0x180007321  jnz     short loc_18000732E
0x180007323  mov     rbp, r13
0x180007326  mov     r10, r13
0x180007329  mov     rsi, r13
0x18000732c  jmp     short loc_1800072B3
0x18000732e  mov     rcx, rbx; hMem
0x180007331  call    PkiFree
0x180007336  mov     rbx, r13
0x180007339  jmp     short loc_180007323
0x18000733b  cmp     eax, 48h ; 'H'
0x18000733e  jz      loc_180007165
0x180007344  cmp     eax, 18h
0x180007347  jz      loc_180007165
0x18000734d  jmp     short loc_180007313
0x18000734f  mov     ecx, 8007000Eh; dwErrCode
0x180007354  call    cs:__imp_SetLastError
0x18000735a  jmp     short loc_180007323
```
