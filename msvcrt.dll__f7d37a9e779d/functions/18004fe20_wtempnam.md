# _wtempnam

- ea: `0x18004fe20`
- end: `0x1800500c0`
- name: `_wtempnam`
- size: `672`
- prototype: `wchar_t *__cdecl(const wchar_t *Directory, const wchar_t *FilePrefix)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x1800500d0`

## callees

- `0x1800030b0`
- `0x180007f00`
- `0x180008e90`
- `0x18001d2b0`
- `0x18001d300`
- `0x18002f05c`
- `0x180030fac`
- `0x18003e6c0`
- `0x18003e790`
- `0x18003e8e0`
- `0x18004fe20`
- `0x1800618d0`

## pseudocode

```c
wchar_t *__cdecl wtempnam(const wchar_t *Directory, const wchar_t *FilePrefix)
{
  __int64 v5; // r14
  errno_t v6; // edi
  __int64 v7; // rsi
  __int64 v8; // rax
  size_t v9; // r12
  wchar_t *v10; // rax
  wchar_t *v11; // rdi
  __int64 v12; // rax
  __int64 v13; // rsi
  int v14; // r14d
  int v15; // ebx
  unsigned int v16; // ecx
  wchar_t *Buffer; // [rsp+70h] [rbp+18h] BYREF

  Buffer = 0;
  if ( !(unsigned int)mtinitlocknum(2) )
    return 0;
  LODWORD(v5) = 0;
  v6 = wdupenv_s(&Buffer, 0, L"TMP");
  if ( v6 == 22 )
    invoke_watson(0, 0, 0, 0, 0);
  if ( v6 || !Buffer || waccess_s(Buffer, 0) )
  {
    if ( !Directory || waccess_s(Directory, 0) )
    {
      Directory = L"\\";
      if ( waccess_s(L"\\", 0) )
        Directory = L".";
    }
  }
  else
  {
    Directory = Buffer;
  }
  v7 = -1;
  if ( FilePrefix )
  {
    v5 = -1;
    do
      ++v5;
    while ( FilePrefix[v5] );
  }
  v8 = -1;
  do
    ++v8;
  while ( Directory[v8] );
  v9 = (unsigned int)(v5 + v8 + 12);
  v10 = (wchar_t *)calloc(v9, 2u);
  v11 = v10;
  if ( v10 )
  {
    *v10 = 0;
    if ( wcscat_s(v10, (unsigned int)v9, Directory) )
      invoke_watson(0, 0, 0, 0, 0);
    v12 = -1;
    do
      ++v12;
    while ( Directory[v12] );
    if ( Directory[v12 - 1] != 92 && Directory[v12 - 1] != 47 && wcscat_s(v11, v9, L"\\") )
      invoke_watson(0, 0, 0, 0, 0);
    if ( FilePrefix && wcscat_s(v11, v9, FilePrefix) )
      invoke_watson(0, 0, 0, 0, 0);
    do
      ++v7;
    while ( v11[v7] );
    v13 = v7;
    lock(2);
    if ( old_pfxlen < (unsigned int)v5 )
      tempoff = 1;
    old_pfxlen = v5;
    v14 = tempoff;
    v15 = *errno();
    while ( 1 )
    {
      v16 = tempoff + 1;
      tempoff = v16;
      if ( v16 - v14 > 0x7FFFFFFF )
        break;
      if ( ultow_s(v16, &v11[v13], v9 - ((v13 * 2) >> 1), 10) )
        invoke_watson(0, 0, 0, 0, 0);
      *errno() = 0;
      if ( waccess_s(v11, 0) && *errno() != 13 )
      {
        *errno() = v15;
        goto LABEL_41;
      }
    }
    *errno() = v15;
    free(v11);
    v11 = 0;
LABEL_41:
    unlock(2);
  }
  free(Buffer);
  free(0);
  return v11;
}

```

## disassembly

```asm
0x18004fe20  mov     [rsp+arg_0], rbx
0x18004fe25  mov     [rsp+arg_8], rsi
0x18004fe2a  push    rdi
0x18004fe2b  push    r12
0x18004fe2d  push    r13
0x18004fe2f  push    r14
0x18004fe31  push    r15
0x18004fe33  sub     rsp, 30h
0x18004fe37  mov     r15, rdx
0x18004fe3a  mov     rbx, rcx
0x18004fe3d  xor     r13d, r13d
0x18004fe40  mov     [rsp+58h+Buffer], r13
0x18004fe45  lea     ecx, [r13+2]
0x18004fe49  call    _mtinitlocknum
0x18004fe4e  test    eax, eax
0x18004fe50  jnz     short loc_18004FE59
0x18004fe52  xor     eax, eax
0x18004fe54  jmp     loc_1800500A8
0x18004fe59  mov     r14d, r13d
0x18004fe5c  lea     r8, aTmp; "TMP"
0x18004fe63  xor     edx, edx; BufferCount
0x18004fe65  lea     rcx, [rsp+58h+Buffer]; Buffer
0x18004fe6a  call    _wdupenv_s
0x18004fe6f  mov     edi, eax
0x18004fe71  cmp     eax, 16h
0x18004fe74  jnz     short loc_18004FE8A
0x18004fe76  mov     [rsp+58h+Reserved], r13; Reserved
0x18004fe7b  xor     r9d, r9d; LineNo
0x18004fe7e  xor     r8d, r8d; FileName
0x18004fe81  xor     edx, edx; FunctionName
0x18004fe83  xor     ecx, ecx; Expression
0x18004fe85  call    _invoke_watson
0x18004fe8a  test    edi, edi
0x18004fe8c  jnz     short loc_18004FEAA
0x18004fe8e  mov     rcx, [rsp+58h+Buffer]; FileName
0x18004fe93  test    rcx, rcx
0x18004fe96  jz      short loc_18004FEAA
0x18004fe98  xor     edx, edx; AccessMode
0x18004fe9a  call    _waccess_s
0x18004fe9f  test    eax, eax
0x18004fea1  jnz     short loc_18004FEAA
0x18004fea3  mov     rbx, [rsp+58h+Buffer]
0x18004fea8  jmp     short loc_18004FEDF
0x18004feaa  test    rbx, rbx
0x18004fead  jz      short loc_18004FEBD
0x18004feaf  xor     edx, edx; AccessMode
0x18004feb1  mov     rcx, rbx; FileName
0x18004feb4  call    _waccess_s
0x18004feb9  test    eax, eax
0x18004febb  jz      short loc_18004FEDF
0x18004febd  xor     edx, edx; AccessMode
0x18004febf  lea     rcx, asc_1800823EC; "\\"
0x18004fec6  call    _waccess_s
0x18004fecb  lea     rbx, asc_1800823EC; "\\"
0x18004fed2  lea     rcx, asc_180084CA8; "."
0x18004fed9  test    eax, eax
0x18004fedb  cmovnz  rbx, rcx
0x18004fedf  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18004fee3  test    r15, r15
0x18004fee6  jz      short loc_18004FEF5
0x18004fee8  mov     r14, rsi
0x18004feeb  inc     r14
0x18004feee  cmp     [r15+r14*2], r13w
0x18004fef3  jnz     short loc_18004FEEB
0x18004fef5  mov     rax, rsi
0x18004fef8  inc     rax
0x18004fefb  cmp     [rbx+rax*2], r13w
0x18004ff00  jnz     short loc_18004FEF8
0x18004ff02  add     eax, 0Ch
0x18004ff05  add     eax, r14d
0x18004ff08  mov     r12d, eax
0x18004ff0b  mov     edx, 2; Size
0x18004ff10  mov     ecx, eax; Count
0x18004ff12  call    calloc
0x18004ff17  mov     rdi, rax
0x18004ff1a  test    rax, rax
0x18004ff1d  jz      loc_180050094
0x18004ff23  mov     [rax], r13w
0x18004ff27  mov     r8, rbx; Source
0x18004ff2a  mov     edx, r12d; SizeInWords
0x18004ff2d  mov     rcx, rax; Destination
0x18004ff30  call    wcscat_s
0x18004ff35  test    eax, eax
0x18004ff37  jz      short loc_18004FF4D
0x18004ff39  mov     [rsp+58h+Reserved], r13; Reserved
0x18004ff3e  xor     r9d, r9d; LineNo
0x18004ff41  xor     r8d, r8d; FileName
0x18004ff44  xor     edx, edx; FunctionName
0x18004ff46  xor     ecx, ecx; Expression
0x18004ff48  call    _invoke_watson
0x18004ff4d  mov     rax, rsi
0x18004ff50  inc     rax
0x18004ff53  cmp     [rbx+rax*2], r13w
0x18004ff58  jnz     short loc_18004FF50
0x18004ff5a  cmp     word ptr [rbx+rax*2-2], 5Ch ; '\'
0x18004ff60  jz      short loc_18004FF94
0x18004ff62  cmp     word ptr [rbx+rax*2-2], 2Fh ; '/'
0x18004ff68  jz      short loc_18004FF94
0x18004ff6a  lea     r8, asc_1800823EC; "\\"
0x18004ff71  mov     rdx, r12; SizeInWords
0x18004ff74  mov     rcx, rdi; Destination
0x18004ff77  call    wcscat_s
0x18004ff7c  test    eax, eax
0x18004ff7e  jz      short loc_18004FF94
0x18004ff80  mov     [rsp+58h+Reserved], r13; Reserved
0x18004ff85  xor     r9d, r9d; LineNo
0x18004ff88  xor     r8d, r8d; FileName
0x18004ff8b  xor     edx, edx; FunctionName
0x18004ff8d  xor     ecx, ecx; Expression
0x18004ff8f  call    _invoke_watson
0x18004ff94  test    r15, r15
0x18004ff97  jz      short loc_18004FFBF
0x18004ff99  mov     r8, r15; Source
0x18004ff9c  mov     rdx, r12; SizeInWords
0x18004ff9f  mov     rcx, rdi; Destination
0x18004ffa2  call    wcscat_s
0x18004ffa7  test    eax, eax
0x18004ffa9  jz      short loc_18004FFBF
0x18004ffab  mov     [rsp+58h+Reserved], r13; Reserved
0x18004ffb0  xor     r9d, r9d; LineNo
0x18004ffb3  xor     r8d, r8d; FileName
0x18004ffb6  xor     edx, edx; FunctionName
0x18004ffb8  xor     ecx, ecx; Expression
0x18004ffba  call    _invoke_watson
0x18004ffbf  inc     rsi
0x18004ffc2  cmp     [rdi+rsi*2], r13w
0x18004ffc7  jnz     short loc_18004FFBF
0x18004ffc9  add     rsi, rsi
0x18004ffcc  lea     r15, [rsi+rdi]
0x18004ffd0  mov     ecx, 2
0x18004ffd5  call    _lock
0x18004ffda  nop
0x18004ffdb  cmp     cs:_old_pfxlen, r14d
0x18004ffe2  jnb     short loc_18004FFEE
0x18004ffe4  mov     cs:_tempoff, 1
0x18004ffee  mov     cs:_old_pfxlen, r14d
0x18004fff5  mov     r14d, cs:_tempoff
0x18004fffc  call    _errno
0x180050001  mov     ebx, [rax]
0x180050003  mov     ecx, cs:_tempoff
0x180050009  inc     ecx; Value
0x18005000b  mov     cs:_tempoff, ecx
0x180050011  mov     eax, ecx
0x180050013  sub     eax, r14d
0x180050016  cmp     eax, 7FFFFFFFh
0x18005001b  ja      short loc_180050078
0x18005001d  mov     rax, rsi
0x180050020  sar     rax, 1
0x180050023  mov     r8, r12
0x180050026  sub     r8, rax; BufferCount
0x180050029  mov     r9d, 0Ah; Radix
0x18005002f  mov     rdx, r15; Buffer
0x180050032  call    _ultow_s
0x180050037  test    eax, eax
0x180050039  jz      short loc_18005004F
0x18005003b  mov     [rsp+58h+Reserved], r13; Reserved
0x180050040  xor     r9d, r9d; LineNo
0x180050043  xor     r8d, r8d; FileName
0x180050046  xor     edx, edx; FunctionName
0x180050048  xor     ecx, ecx; Expression
0x18005004a  call    _invoke_watson
0x18005004f  call    _errno
0x180050054  mov     [rax], r13d
0x180050057  xor     edx, edx; AccessMode
0x180050059  mov     rcx, rdi; FileName
0x18005005c  call    _waccess_s
0x180050061  test    eax, eax
0x180050063  jz      short loc_180050003
0x180050065  call    _errno
0x18005006a  cmp     dword ptr [rax], 0Dh
0x18005006d  jz      short loc_180050003
0x18005006f  call    _errno
0x180050074  mov     [rax], ebx
0x180050076  jmp     short loc_18005008A
0x180050078  call    _errno
0x18005007d  mov     [rax], ebx
0x18005007f  mov     rcx, rdi; Block
0x180050082  call    free
0x180050087  mov     rdi, r13
0x18005008a  mov     ecx, 2
0x18005008f  call    _unlock
0x180050094  mov     rcx, [rsp+58h+Buffer]; Block
0x180050099  call    free
0x18005009e  xor     ecx, ecx; Block
0x1800500a0  call    free
0x1800500a5  mov     rax, rdi
0x1800500a8  mov     rbx, [rsp+58h+arg_0]
0x1800500ad  mov     rsi, [rsp+58h+arg_8]
0x1800500b2  add     rsp, 30h
0x1800500b6  pop     r15
0x1800500b8  pop     r14
0x1800500ba  pop     r13
0x1800500bc  pop     r12
0x1800500be  pop     rdi
0x1800500bf  retn
0x18007c006  push    rbp
0x18007c008  sub     rsp, 30h
0x18007c00c  mov     rbp, rdx
0x18007c00f  mov     ecx, 2
0x18007c014  call    _unlock
0x18007c019  nop
0x18007c01a  add     rsp, 30h
0x18007c01e  pop     rbp
0x18007c01f  retn
```
