# I_UrlCacheReadCryptBlobArray

- ea: `0x180007dc0`
- end: `0x180008328`
- name: `I_UrlCacheReadCryptBlobArray`
- size: `1384`
- prototype: `_QWORD *__fastcall(_WORD *Src, void *, __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180008df0`
- `0x18000fe44`

## callees

- `0x1800033a0`
- `0x180003f00`
- `0x180004180`
- `0x1800042e0`
- `0x1800068b0`
- `0x1800070d0`
- `0x180007dc0`
- `0x18000e2f0`
- `0x1800174fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000827a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800082cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000827a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800082cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800082be`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000830b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000831d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800082be`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000830b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000831d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180007fa6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800081a6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180007fa6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800081a6`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180008061`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180008061`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800082a3`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800082f1`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800082a3`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800082f1`

## pseudocode

```c
_QWORD *__fastcall I_UrlCacheReadCryptBlobArray(_WORD *Src, void *a2, __int64 a3)
{
  _QWORD *v5; // r13
  __int64 v6; // rbp
  __int64 v7; // r12
  __int64 v8; // rbx
  __int64 v9; // r15
  char *v10; // r14
  HANDLE FileW; // rdi
  void *v12; // r15
  __int16 v14; // cx
  unsigned __int64 v15; // rax
  __int64 j; // rbx
  __int64 v17; // rax
  __int64 v18; // rsi
  DWORD v19; // r14d
  __int64 k; // rdx
  unsigned int v21; // eax
  SIZE_T v22; // rcx
  __int64 v23; // rax
  __int64 v24; // r12
  __int64 v25; // rbx
  unsigned int v26; // r8d
  __int64 v27; // r9
  __int64 v28; // rdx
  int v29; // eax
  __int64 v30; // rcx
  __int64 v31; // rax
  DWORD v32; // ecx
  size_t v33; // rdi
  __int64 v34; // rdi
  _WORD *v35; // rbx
  __int128 v36; // xmm6
  __int128 v37; // xmm7
  __int128 v38; // xmm8
  __int128 v39; // xmm9
  __int16 v40; // cx
  __int64 v41; // rax
  __int64 i; // r15
  char *v43; // r14
  DWORD LastError; // eax
  DWORD v45; // eax
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-F8h] BYREF
  void *Srca; // [rsp+48h] [rbp-F0h]
  __int64 v48; // [rsp+50h] [rbp-E8h]
  __int64 v49; // [rsp+58h] [rbp-E0h] BYREF
  _OWORD v50[4]; // [rsp+60h] [rbp-D8h] BYREF
  __int16 v51; // [rsp+A0h] [rbp-98h]

  Srca = a2;
  v5 = 0;
  v48 = 0;
  NumberOfBytesRead = 0;
  v6 = 0;
  I_UrlCacheGetUrlFileName(a3, v50);
  v7 = -1;
  if ( Src )
  {
    v8 = -1;
    do
      ++v8;
    while ( Src[v8] );
  }
  else
  {
    LODWORD(v8) = 0;
  }
  if ( a2 )
  {
    v9 = -1;
    do
      ++v9;
    while ( *((_WORD *)a2 + v9) );
  }
  else
  {
    LODWORD(v9) = 0;
  }
  v10 = (char *)PkiNonzeroAlloc(2LL * (unsigned int)(v8 + v9 + 42));
  if ( !v10 )
  {
    PkiFree(0);
LABEL_8:
    FileW = 0;
LABEL_9:
    v12 = 0;
    goto LABEL_10;
  }
  v49 = (unsigned int)v8;
  v33 = 2LL * (unsigned int)v8;
  memcpy_0(v10, Src, v33);
  *(_OWORD *)&v10[v33] = *(_OWORD *)L"MetaData";
  *(_WORD *)&v10[v33 + 16] = aMetadata[8];
  v34 = v49;
  *(_WORD *)&v10[2 * (unsigned int)(v8 + 8)] = 92;
  v35 = Srca;
  if ( (_DWORD)v9 )
    memcpy_0(&v10[2 * v34 + 18], Srca, 2LL * (unsigned int)v9);
  v36 = v50[0];
  v37 = v50[1];
  v38 = v50[2];
  v39 = v50[3];
  v40 = v51;
  v41 = v34 + (unsigned int)v9;
  *(_OWORD *)&v10[2 * v41 + 18] = v50[0];
  *(_OWORD *)&v10[2 * v41 + 34] = v37;
  *(_OWORD *)&v10[2 * v41 + 50] = v38;
  *(_OWORD *)&v10[2 * v41 + 66] = v39;
  *(_WORD *)&v10[2 * v41 + 82] = v40;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    FileW = CreateFileW((LPCWSTR)v10, 0x80000000, 1u, 0, 3u, 0x80u, 0);
    if ( FileW != (HANDLE)-1LL )
      break;
    LastError = GetLastError();
    if ( LastError == 32 )
    {
      if ( (unsigned int)i >= 6 )
        goto LABEL_62;
    }
    else
    {
      if ( LastError != 5 )
      {
        if ( LastError == 3 )
          LastError = 2;
LABEL_62:
        SetLastError(LastError);
        FileW = 0;
        break;
      }
      if ( (_DWORD)i )
        goto LABEL_62;
    }
    Sleep(*((_DWORD *)qword_18001B4D0 + i));
  }
  PkiFree(v10);
  if ( !FileW )
    goto LABEL_9;
  if ( Src )
  {
    v6 = -1;
    do
      ++v6;
    while ( Src[v6] );
  }
  if ( v35 )
  {
    do
      ++v7;
    while ( v35[v7] );
  }
  else
  {
    LODWORD(v7) = 0;
  }
  v43 = (char *)PkiNonzeroAlloc(2LL * (unsigned int)(v6 + v7 + 41));
  if ( !v43 )
  {
    PkiFree(0);
    v6 = 0;
LABEL_47:
    I_UrlCacheCloseHandle(FileW);
    goto LABEL_8;
  }
  memcpy_0(v43, Src, 2LL * (unsigned int)v6);
  *(_OWORD *)&v43[2 * (unsigned int)v6] = *(_OWORD *)L"Content";
  *(_WORD *)&v43[2 * (unsigned int)(v6 + 7)] = 92;
  if ( (_DWORD)v7 )
    memcpy_0(&v43[2 * (unsigned int)v6 + 16], Srca, 2LL * (unsigned int)v7);
  v14 = v51;
  v15 = (unsigned int)v6 + (unsigned __int64)(unsigned int)v7;
  *(_OWORD *)&v43[2 * v15 + 16] = v36;
  *(_OWORD *)&v43[2 * v15 + 32] = v37;
  *(_OWORD *)&v43[2 * v15 + 48] = v38;
  *(_OWORD *)&v43[2 * v15 + 64] = v39;
  *(_WORD *)&v43[2 * v15 + 80] = v14;
  for ( j = 0; ; j = (unsigned int)(j + 1) )
  {
    v6 = (__int64)CreateFileW((LPCWSTR)v43, 0x80000000, 1u, 0, 3u, 0x80u, 0);
    if ( v6 != -1 )
      break;
    v45 = GetLastError();
    if ( v45 == 32 )
    {
      if ( (unsigned int)j >= 6 )
        goto LABEL_71;
    }
    else
    {
      if ( v45 != 5 )
      {
        if ( v45 == 3 )
          v45 = 2;
LABEL_71:
        SetLastError(v45);
        v6 = 0;
        break;
      }
      if ( (_DWORD)j )
        goto LABEL_71;
    }
    Sleep(*((_DWORD *)qword_18001B4D0 + j));
  }
  PkiFree(v43);
  if ( !v6 )
    goto LABEL_47;
  v17 = I_UrlCacheReadAndValidateMetaDataFile(FileW, (__int64)&v49);
  v12 = (void *)v17;
  if ( !v17 )
  {
LABEL_10:
    if ( !v6 )
      goto LABEL_11;
    goto LABEL_31;
  }
  v18 = *(unsigned int *)(v17 + 8);
  if ( (unsigned int)v18 > 0xFFFFFF )
    goto LABEL_72;
  v19 = 0;
  for ( k = 0; (unsigned int)k < (unsigned int)v18; k = (unsigned int)(k + 1) )
  {
    v32 = v19;
    v19 += *(_DWORD *)(v48 + 4 * k);
    if ( v19 < v32 )
      goto LABEL_72;
  }
  v21 = 16 * (v18 + 1);
  v22 = v21 + v19;
  if ( (unsigned int)v22 < v21 )
  {
LABEL_72:
    SetLastError(0x216u);
    goto LABEL_10;
  }
  v23 = PkiZeroAlloc(v22);
  v5 = (_QWORD *)v23;
  if ( !v23 )
    goto LABEL_10;
  v24 = v23 + 16;
  v25 = v23 + 16 + 16 * v18;
  if ( v19
    && (!ReadFile((HANDLE)v6, (LPVOID)(v23 + 16 + 16 * v18), v19, &NumberOfBytesRead, 0) || v19 != NumberOfBytesRead) )
  {
    PkiFree(v5);
    v5 = 0;
    goto LABEL_10;
  }
  v26 = 0;
  *(_DWORD *)v5 = v18;
  v5[1] = v24;
  if ( (_DWORD)v18 )
  {
    v27 = v48;
    v28 = 0;
    do
    {
      v29 = *(_DWORD *)(v27 + 4 * v28);
      v30 = 2 * v28;
      ++v26;
      *(_QWORD *)(v24 + 8 * v30 + 8) = v25;
      *(_DWORD *)(v24 + 8 * v30) = v29;
      v31 = *(unsigned int *)(v27 + 4 * v28++);
      v25 += v31;
    }
    while ( v26 < (unsigned int)v18 );
  }
LABEL_31:
  I_UrlCacheCloseHandle((HANDLE)v6);
LABEL_11:
  if ( FileW )
    I_UrlCacheCloseHandle(FileW);
  PkiFree(v12);
  return v5;
}

```

## disassembly

```asm
0x180007dc0  mov     r11, rsp
0x180007dc3  push    rdi
0x180007dc4  push    r13
0x180007dc6  push    r15
0x180007dc8  sub     rsp, 120h
0x180007dcf  mov     rax, cs:__security_cookie
0x180007dd6  xor     rax, rsp
0x180007dd9  mov     [rsp+138h+var_88], rax
0x180007de1  mov     [r11+20h], rbx
0x180007de5  mov     rdi, rdx
0x180007de8  mov     [r11-20h], rbp
0x180007dec  mov     [r11-28h], rsi
0x180007df0  mov     rsi, rcx
0x180007df3  mov     [r11-30h], r12
0x180007df7  mov     rcx, r8
0x180007dfa  mov     [r11-38h], r14
0x180007dfe  xor     r14d, r14d
0x180007e01  mov     [rsp+138h+Src], rdx
0x180007e06  mov     r13d, r14d
0x180007e09  lea     rdx, [rsp+138h+var_D8]
0x180007e0e  mov     [rsp+138h+var_E8], r14
0x180007e13  mov     [rsp+138h+NumberOfBytesRead], r14d
0x180007e18  mov     ebp, r14d
0x180007e1b  call    I_UrlCacheGetUrlFileName
0x180007e20  mov     r12, 0FFFFFFFFFFFFFFFFh
0x180007e27  test    rsi, rsi
0x180007e2a  jz      loc_180008272
0x180007e30  mov     rbx, r12
0x180007e33  inc     rbx
0x180007e36  cmp     [rsi+rbx*2], bp
0x180007e3a  jnz     short loc_180007E33
0x180007e3c  test    rdi, rdi
0x180007e3f  jnz     loc_180008251
0x180007e45  mov     r15d, r14d
0x180007e48  movaps  [rsp+138h+var_48], xmm6
0x180007e50  lea     ecx, [r15+2Ah]
0x180007e54  movaps  [rsp+138h+var_58], xmm7
0x180007e5c  add     ecx, ebx
0x180007e5e  movaps  [rsp+138h+var_68], xmm8
0x180007e67  add     rcx, rcx; uBytes
0x180007e6a  movaps  [rsp+138h+var_78], xmm9
0x180007e73  call    PkiNonzeroAlloc
0x180007e78  mov     r14, rax
0x180007e7b  mov     rcx, rax; hMem
0x180007e7e  test    rax, rax
0x180007e81  jnz     loc_1800080E1
0x180007e87  call    PkiFree
0x180007e8c  xor     edi, edi
0x180007e8e  xor     r15d, r15d
0x180007e91  test    rbp, rbp
0x180007e94  jnz     loc_1800080AD
0x180007e9a  movaps  xmm9, [rsp+138h+var_78]
0x180007ea3  movaps  xmm8, [rsp+138h+var_68]
0x180007eac  movaps  xmm7, [rsp+138h+var_58]
0x180007eb4  movaps  xmm6, [rsp+138h+var_48]
0x180007ebc  mov     r14, [rsp+138h+var_38]
0x180007ec4  mov     r12, [rsp+138h+var_30]
0x180007ecc  mov     rsi, [rsp+138h+var_28]
0x180007ed4  mov     rbp, [rsp+138h+var_20]
0x180007edc  mov     rbx, [rsp+138h+arg_18]
0x180007ee4  test    rdi, rdi
0x180007ee7  jz      short loc_180007EF1
0x180007ee9  mov     rcx, rdi; hObject
0x180007eec  call    I_UrlCacheCloseHandle
0x180007ef1  mov     rcx, r15; hMem
0x180007ef4  call    PkiFree
0x180007ef9  mov     rax, r13
0x180007efc  mov     rcx, [rsp+138h+var_88]
0x180007f04  xor     rcx, rsp; StackCookie
0x180007f07  call    __security_check_cookie
0x180007f0c  add     rsp, 120h
0x180007f13  pop     r15
0x180007f15  pop     r13
0x180007f17  pop     rdi
0x180007f18  retn
0x180007f19  mov     r15d, ebp
0x180007f1c  mov     rdx, rsi; Src
0x180007f1f  lea     rbx, [r15+r15]
0x180007f23  mov     r8, rbx; Size
0x180007f26  call    memcpy_0
0x180007f2b  lea     eax, [rbp+7]
0x180007f2e  movups  xmm0, xmmword ptr cs:aContent; "Content"
0x180007f35  movups  xmmword ptr [rbx+r14], xmm0
0x180007f3a  mov     word ptr [r14+rax*2], 5Ch ; '\'
0x180007f41  test    r12d, r12d
0x180007f44  jnz     loc_180008234
0x180007f4a  movzx   ecx, [rsp+138h+var_98]
0x180007f52  mov     eax, r12d
0x180007f55  add     rax, r15
0x180007f58  movups  xmmword ptr [r14+rax*2+10h], xmm6
0x180007f5e  movups  xmmword ptr [r14+rax*2+20h], xmm7
0x180007f64  movups  xmmword ptr [r14+rax*2+30h], xmm8
0x180007f6a  movups  xmmword ptr [r14+rax*2+40h], xmm9
0x180007f70  mov     [r14+rax*2+50h], cx
0x180007f76  xor     ebx, ebx
0x180007f78  nop     dword ptr [rax+rax+00000000h]
0x180007f80  mov     [rsp+138h+hTemplateFile], r13; hTemplateFile
0x180007f85  xor     r9d, r9d; lpSecurityAttributes
0x180007f88  mov     [rsp+138h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180007f90  mov     edx, 80000000h; dwDesiredAccess
0x180007f95  mov     r8d, 1; dwShareMode
0x180007f9b  mov     [rsp+138h+dwCreationDisposition], 3; dwCreationDisposition
0x180007fa3  mov     rcx, r14; lpFileName
0x180007fa6  call    cs:__imp_CreateFileW
0x180007fac  mov     rbp, rax
0x180007faf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180007fb3  jz      loc_1800082CB
0x180007fb9  mov     rcx, r14; hMem
0x180007fbc  call    PkiFree
0x180007fc1  test    rbp, rbp
0x180007fc4  jz      loc_18000820C
0x180007fca  lea     rax, [rsp+138h+var_E0]
0x180007fcf  xor     r9d, r9d
0x180007fd2  xor     r8d, r8d
0x180007fd5  mov     qword ptr [rsp+138h+dwCreationDisposition], rax; __int64
0x180007fda  lea     rdx, [rsp+138h+var_E8]
0x180007fdf  mov     rcx, rdi; hFile
0x180007fe2  call    I_UrlCacheReadAndValidateMetaDataFile
0x180007fe7  mov     r15, rax
0x180007fea  test    rax, rax
0x180007fed  jz      loc_180007E91
0x180007ff3  mov     esi, [rax+8]
0x180007ff6  cmp     esi, 0FFFFFFh
0x180007ffc  ja      loc_180008318
0x180008002  mov     r8, [rsp+138h+var_E8]
0x180008007  xor     r14d, r14d
0x18000800a  xor     edx, edx
0x18000800c  cmp     edx, esi
0x18000800e  jb      loc_1800080BA
0x180008014  lea     eax, [rsi+1]
0x180008017  shl     eax, 4
0x18000801a  lea     ecx, [rax+r14]; uBytes
0x18000801e  cmp     ecx, eax
0x180008020  jb      loc_180008318
0x180008026  call    PkiZeroAlloc
0x18000802b  mov     r13, rax
0x18000802e  test    rax, rax
0x180008031  jz      loc_180007E91
0x180008037  mov     rbx, rsi
0x18000803a  lea     r12, [rax+10h]
0x18000803e  shl     rbx, 4
0x180008042  add     rbx, r12
0x180008045  test    r14d, r14d
0x180008048  jz      short loc_180008072
0x18000804a  lea     r9, [rsp+138h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18000804f  mov     qword ptr [rsp+138h+dwCreationDisposition], 0; lpOverlapped
0x180008058  mov     r8d, r14d; nNumberOfBytesToRead
0x18000805b  mov     rdx, rbx; lpBuffer
0x18000805e  mov     rcx, rbp; hFile
0x180008061  call    cs:__imp_ReadFile
0x180008067  test    eax, eax
0x180008069  jz      short loc_1800080D1
0x18000806b  cmp     r14d, [rsp+138h+NumberOfBytesRead]
0x180008070  jnz     short loc_1800080D1
0x180008072  xor     r8d, r8d
0x180008075  mov     [r13+0], esi
0x180008079  mov     [r13+8], r12
0x18000807d  test    esi, esi
0x18000807f  jz      short loc_1800080AD
0x180008081  mov     r9, [rsp+138h+var_E8]
0x180008086  xor     edx, edx
0x180008088  mov     eax, [r9+rdx*4]
0x18000808c  mov     rcx, rdx
0x18000808f  add     rcx, rcx
0x180008092  inc     r8d
0x180008095  mov     [r12+rcx*8+8], rbx
0x18000809a  mov     [r12+rcx*8], eax
0x18000809e  mov     eax, [r9+rdx*4]
0x1800080a2  inc     rdx
0x1800080a5  add     rbx, rax
0x1800080a8  cmp     r8d, esi
0x1800080ab  jb      short loc_180008088
0x1800080ad  mov     rcx, rbp; hObject
0x1800080b0  call    I_UrlCacheCloseHandle
0x1800080b5  jmp     loc_180007E9A
0x1800080ba  mov     ecx, r14d
0x1800080bd  add     r14d, [r8+rdx*4]
0x1800080c1  cmp     r14d, ecx
0x1800080c4  jb      loc_180008318
0x1800080ca  inc     edx
0x1800080cc  jmp     loc_18000800C
0x1800080d1  mov     rcx, r13; hMem
0x1800080d4  call    PkiFree
0x1800080d9  xor     r13d, r13d
0x1800080dc  jmp     loc_180007E91
0x1800080e1  mov     eax, ebx
0x1800080e3  mov     rdx, rsi; Src
0x1800080e6  mov     [rsp+138h+var_E0], rax
0x1800080eb  lea     rdi, [rax+rax]
0x1800080ef  mov     r8, rdi; Size
0x1800080f2  call    memcpy_0
0x1800080f7  movups  xmm0, xmmword ptr cs:aMetadata; "MetaData"
0x1800080fe  add     ebx, 8
0x180008101  movups  xmmword ptr [rdi+r14], xmm0
0x180008106  movzx   eax, word ptr cs:aMetadata+10h; ""
0x18000810d  mov     [rdi+r14+10h], ax
0x180008113  mov     rdi, [rsp+138h+var_E0]
0x180008118  mov     word ptr [r14+rbx*2], 5Ch ; '\'
0x18000811f  mov     rbx, [rsp+138h+Src]
0x180008124  test    r15d, r15d
0x180008127  jnz     loc_180008219
0x18000812d  movaps  xmm6, [rsp+138h+var_D8]
0x180008132  movaps  xmm7, [rsp+138h+var_C8]
0x180008137  movaps  xmm8, [rsp+138h+var_B8]
0x180008140  movaps  xmm9, [rsp+138h+var_A8]
0x180008149  movzx   ecx, [rsp+138h+var_98]
0x180008151  mov     eax, r15d
0x180008154  add     rax, rdi
0x180008157  movups  xmmword ptr [r14+rax*2+12h], xmm6
0x18000815d  movups  xmmword ptr [r14+rax*2+22h], xmm7
0x180008163  movups  xmmword ptr [r14+rax*2+32h], xmm8
0x180008169  movups  xmmword ptr [r14+rax*2+42h], xmm9
0x18000816f  mov     [r14+rax*2+52h], cx
0x180008175  xor     r15d, r15d
0x180008178  nop     dword ptr [rax+rax+00000000h]
0x180008180  mov     [rsp+138h+hTemplateFile], rbp; hTemplateFile
0x180008185  xor     r9d, r9d; lpSecurityAttributes
0x180008188  mov     [rsp+138h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180008190  mov     edx, 80000000h; dwDesiredAccess
0x180008195  mov     r8d, 1; dwShareMode
0x18000819b  mov     [rsp+138h+dwCreationDisposition], 3; dwCreationDisposition
0x1800081a3  mov     rcx, r14; lpFileName
0x1800081a6  call    cs:__imp_CreateFileW
0x1800081ac  mov     rdi, rax
0x1800081af  cmp     rax, r12
0x1800081b2  jz      loc_18000827A
0x1800081b8  mov     rcx, r14; hMem
0x1800081bb  call    PkiFree
0x1800081c0  test    rdi, rdi
0x1800081c3  jz      loc_180007E8E
0x1800081c9  test    rsi, rsi
0x1800081cc  jz      short loc_1800081DB
0x1800081ce  mov     rbp, r12
0x1800081d1  inc     rbp
0x1800081d4  cmp     [rsi+rbp*2], r13w
0x1800081d9  jnz     short loc_1800081D1
0x1800081db  test    rbx, rbx
0x1800081de  jnz     loc_180008263
0x1800081e4  xor     r12d, r12d
0x1800081e7  lea     ecx, [r12+29h]
0x1800081ec  add     ecx, ebp
0x1800081ee  add     rcx, rcx; uBytes
0x1800081f1  call    PkiNonzeroAlloc
0x1800081f6  mov     r14, rax
0x1800081f9  mov     rcx, rax; hMem
0x1800081fc  test    rax, rax
0x1800081ff  jnz     loc_180007F19
0x180008205  call    PkiFree
0x18000820a  xor     ebp, ebp
0x18000820c  mov     rcx, rdi; hObject
0x18000820f  call    I_UrlCacheCloseHandle
0x180008214  jmp     loc_180007E8C
0x180008219  mov     r8d, r15d
0x18000821c  lea     rcx, [rdi+9]
0x180008220  add     r8, r8; Size
0x180008223  lea     rcx, [r14+rcx*2]; void *
0x180008227  mov     rdx, rbx; Src
0x18000822a  call    memcpy_0
0x18000822f  jmp     loc_18000812D
0x180008234  mov     rdx, [rsp+138h+Src]; Src
0x180008239  lea     rcx, [r15+8]
0x18000823d  mov     r8d, r12d
0x180008240  lea     rcx, [r14+rcx*2]; void *
0x180008244  add     r8, r8; Size
0x180008247  call    memcpy_0
0x18000824c  jmp     loc_180007F4A
0x180008251  mov     r15, r12
0x180008254  inc     r15
0x180008257  cmp     [rdi+r15*2], bp
0x18000825c  jnz     short loc_180008254
0x18000825e  jmp     loc_180007E48
0x180008263  inc     r12
0x180008266  cmp     [rbx+r12*2], r13w
0x18000826b  jnz     short loc_180008263
0x18000826d  jmp     loc_1800081E7
0x180008272  mov     ebx, r14d
0x180008275  jmp     loc_180007E3C
0x18000827a  call    cs:__imp_GetLastError
0x180008280  cmp     eax, 20h ; ' '
0x180008283  jnz     short loc_18000828D
0x180008285  cmp     r15d, 6
0x180008289  jb      short loc_180008298
0x18000828b  jmp     short loc_1800082BC
0x18000828d  cmp     eax, 5
0x180008290  jnz     short loc_1800082B1
0x180008292  cmp     r15d, 1
0x180008296  jnb     short loc_1800082BC
0x180008298  lea     rax, qword_18001B4D0
0x18000829f  mov     ecx, [rax+r15*4]; dwMilliseconds
0x1800082a3  call    cs:__imp_Sleep
0x1800082a9  inc     r15d
0x1800082ac  jmp     loc_180008180
0x1800082b1  cmp     eax, 3
0x1800082b4  mov     ecx, 2
0x1800082b9  cmovz   eax, ecx
0x1800082bc  mov     ecx, eax; dwErrCode
0x1800082be  call    cs:__imp_SetLastError
0x1800082c4  xor     edi, edi
0x1800082c6  jmp     loc_1800081B8
0x1800082cb  call    cs:__imp_GetLastError
  ... truncated ...
```
