# _wopenfile

- ea: `0x18005da6c`
- end: `0x18005ddc3`
- name: `_wopenfile`
- size: `855`
- prototype: `__int64 __fastcall(wchar_t *FileName)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18004f1d0`
- `0x18004f2f8`

## callees

- `0x180007f00`
- `0x1800231d0`
- `0x18002f050`
- `0x18005da6c`
- `0x18005ffb0`
- `0x180061da0`

## pseudocode

```c
__int64 __fastcall wopenfile(wchar_t *FileName, _WORD *a2, int a3, __int64 a4)
{
  __int16 v6; // ax
  _WORD *v7; // rbx
  __int64 result; // rax
  unsigned int v10; // edi
  int v11; // esi
  unsigned int v12; // esi
  const wchar_t *v13; // rbx
  int v14; // r9d
  int v15; // r10d
  int v16; // r11d
  int v17; // r8d
  unsigned int v18; // ecx
  unsigned int v19; // ecx
  unsigned int v20; // ecx
  unsigned int v21; // ecx
  unsigned int v22; // ecx
  unsigned int v23; // ecx
  int v24; // edx
  int v25; // ecx
  int v26; // eax
  char v27; // cl
  bool v28; // zf
  unsigned int v29; // ecx
  unsigned int v30; // ecx
  unsigned int v31; // ecx
  unsigned int v32; // ecx
  int v33; // eax
  int v34; // ecx
  unsigned int v35; // eax
  int v36; // eax
  __int16 v37; // cx
  int v38; // eax
  const wchar_t *i; // rbx
  int FileHandle; // [rsp+88h] [rbp+10h] BYREF

  FileHandle = 0;
  v6 = *a2;
  v7 = a2;
  while ( v6 == 32 )
    v6 = *++v7;
  switch ( v6 )
  {
    case 'a':
      v10 = 265;
      break;
    case 'r':
      v10 = 0;
      v11 = 1;
      goto LABEL_13;
    case 'w':
      v10 = 769;
      break;
    default:
      goto LABEL_7;
  }
  v11 = 2;
LABEL_13:
  v12 = commode | v11;
  v13 = v7 + 1;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 1;
  if ( !*v13 )
    goto LABEL_84;
  while ( v17 )
  {
    v18 = *v13;
    if ( v18 > 0x53 )
    {
      v29 = v18 - 84;
      if ( v29 )
      {
        v30 = v29 - 14;
        if ( !v30 )
        {
          v33 = v10 | 0x8000;
          goto LABEL_57;
        }
        v31 = v30 - 1;
        if ( v31 )
        {
          v32 = v31 - 11;
          if ( v32 )
          {
            if ( v32 != 6 )
              goto LABEL_7;
            v33 = v10 | 0x4000;
LABEL_57:
            v37 = v10;
            if ( (v10 & 0xC000) == 0 )
              v10 = v33;
            v28 = (v37 & 0xC000) == 0;
LABEL_60:
            v38 = 0;
            if ( v28 )
              v38 = v17;
            v17 = v38;
            goto LABEL_66;
          }
          v24 = v14;
          v34 = v14;
          if ( !v14 )
            v14 = 1;
          v35 = v12 & 0xFFFFBFFF;
        }
        else
        {
          v24 = v14;
          v34 = v14;
          if ( !v14 )
            v14 = 1;
          v35 = v12 | 0x4000;
        }
        if ( !v34 )
          v12 = v35;
        goto LABEL_53;
      }
      if ( (v10 & 0x1000) == 0 )
      {
        v10 |= 0x1000u;
        goto LABEL_66;
      }
      goto LABEL_64;
    }
    if ( v18 == 83 )
    {
      v24 = v15;
      v25 = v15;
      if ( !v15 )
        v15 = 1;
      v26 = v10 | 0x20;
      goto LABEL_36;
    }
    v19 = v18 - 32;
    if ( v19 )
    {
      v20 = v19 - 11;
      if ( v20 )
      {
        v21 = v20 - 1;
        if ( !v21 )
        {
          v16 = 1;
LABEL_64:
          v17 = 0;
          goto LABEL_66;
        }
        v22 = v21 - 24;
        if ( !v22 )
        {
          v27 = v10;
          if ( (v10 & 0x40) == 0 )
            v10 |= 0x40u;
          v28 = (v27 & 0x40) == 0;
          goto LABEL_60;
        }
        v23 = v22 - 10;
        if ( v23 )
        {
          if ( v23 != 4 )
            goto LABEL_7;
          v24 = v15;
          v25 = v15;
          if ( !v15 )
            v15 = 1;
          v26 = v10 | 0x10;
LABEL_36:
          if ( !v25 )
            v10 = v26;
LABEL_53:
          v36 = 0;
          if ( !v24 )
            v36 = v17;
          v17 = v36;
          goto LABEL_66;
        }
        v10 |= 0x80u;
      }
      else
      {
        if ( (v10 & 2) != 0 )
          goto LABEL_64;
        v10 = v10 & 0xFFFFFFFC | 2;
        v12 = v12 & 0xFFFFFF7C | 0x80;
      }
    }
LABEL_66:
    if ( !*++v13 )
      break;
  }
  if ( !v16 )
    goto LABEL_84;
  while ( *v13 == 32 )
    ++v13;
  if ( wcsncmp(L"ccs", v13, 3u) )
    goto LABEL_7;
  for ( i = v13 + 3; *i == 32; ++i )
    ;
  if ( *i != 61 )
    goto LABEL_7;
  do
    ++i;
  while ( *i == 32 );
  if ( !wcsnicmp(i, L"UTF-8", 5u) )
  {
    v13 = i + 5;
    v10 |= 0x40000u;
    goto LABEL_84;
  }
  if ( !wcsnicmp(i, L"UTF-16LE", 8u) )
  {
    v13 = i + 8;
    v10 |= 0x20000u;
    goto LABEL_84;
  }
  if ( wcsnicmp(i, L"UNICODE", 7u) )
    goto LABEL_7;
  v13 = i + 7;
  v10 |= 0x10000u;
LABEL_84:
  while ( *v13 == 32 )
    ++v13;
  if ( *v13 )
  {
LABEL_7:
    *errno() = 22;
    invalid_parameter(0, 0, 0, 0, 0);
  }
  if ( wsopen_s(&FileHandle, FileName, v10, a3, 384) )
    return 0;
  *(_DWORD *)(a4 + 28) = FileHandle;
  result = a4;
  *(_DWORD *)(a4 + 24) = v12;
  *(_DWORD *)(a4 + 8) = 0;
  *(_QWORD *)a4 = 0;
  *(_QWORD *)(a4 + 16) = 0;
  *(_QWORD *)(a4 + 40) = 0;
  return result;
}

```

## disassembly

```asm
0x18005da6c  mov     rax, rsp
0x18005da6f  push    rbx
0x18005da70  push    rbp
0x18005da71  push    rsi
0x18005da72  push    rdi
0x18005da73  push    r12
0x18005da75  push    r13
0x18005da77  push    r14
0x18005da79  push    r15
0x18005da7b  sub     rsp, 38h
0x18005da7f  xor     r12d, r12d
0x18005da82  mov     r14, r9
0x18005da85  mov     [rax+10h], r12d
0x18005da89  mov     ebp, r8d
0x18005da8c  movzx   eax, word ptr [rdx]
0x18005da8f  mov     rbx, rdx
0x18005da92  mov     r15, rcx
0x18005da95  lea     r13d, [r12+20h]
0x18005da9a  jmp     short loc_18005DAA3
0x18005da9c  add     rbx, 2
0x18005daa0  movzx   eax, word ptr [rbx]
0x18005daa3  cmp     ax, r13w
0x18005daa7  jz      short loc_18005DA9C
0x18005daa9  mov     edx, 1
0x18005daae  cmp     ax, 61h ; 'a'
0x18005dab2  jz      short loc_18005DAF4
0x18005dab4  cmp     ax, 72h ; 'r'
0x18005dab8  jz      short loc_18005DAED
0x18005daba  cmp     ax, 77h ; 'w'
0x18005dabe  jz      short loc_18005DAE6
0x18005dac0  call    _errno
0x18005dac5  xor     r9d, r9d; LineNo
0x18005dac8  mov     [rsp+78h+Reserved], r12; Reserved
0x18005dacd  xor     r8d, r8d; FileName
0x18005dad0  xor     edx, edx; FunctionName
0x18005dad2  xor     ecx, ecx; Expression
0x18005dad4  mov     dword ptr [rax], 16h
0x18005dada  call    _invalid_parameter
0x18005dadf  xor     eax, eax
0x18005dae1  jmp     loc_18005DDB2
0x18005dae6  mov     edi, 301h
0x18005daeb  jmp     short loc_18005DAF9
0x18005daed  mov     edi, r12d
0x18005daf0  mov     esi, edx
0x18005daf2  jmp     short loc_18005DAFE
0x18005daf4  mov     edi, 109h
0x18005daf9  mov     esi, 2
0x18005dafe  or      esi, cs:_commode
0x18005db04  add     rbx, 2
0x18005db08  mov     r9d, r12d
0x18005db0b  mov     r10d, r12d
0x18005db0e  mov     r11d, r12d
0x18005db11  mov     r8d, edx
0x18005db14  cmp     [rbx], r12w
0x18005db18  jz      loc_18005DD59
0x18005db1e  test    r8d, r8d
0x18005db21  jz      loc_18005DC8F
0x18005db27  movzx   ecx, word ptr [rbx]
0x18005db2a  cmp     ecx, 53h ; 'S'
0x18005db2d  ja      loc_18005DBDC
0x18005db33  jz      loc_18005DBBE
0x18005db39  sub     ecx, r13d
0x18005db3c  jz      loc_18005DC81
0x18005db42  sub     ecx, 0Bh
0x18005db45  jz      short loc_18005DBA2
0x18005db47  sub     ecx, 1
0x18005db4a  jz      short loc_18005DB9A
0x18005db4c  sub     ecx, 18h
0x18005db4f  jz      short loc_18005DB81
0x18005db51  sub     ecx, 0Ah
0x18005db54  jz      short loc_18005DB78
0x18005db56  cmp     ecx, 4
0x18005db59  jnz     loc_18005DAC0
0x18005db5f  test    r10d, r10d
0x18005db62  mov     eax, 1
0x18005db67  mov     edx, r10d
0x18005db6a  mov     ecx, r10d
0x18005db6d  cmovz   r10d, eax
0x18005db71  mov     eax, edi
0x18005db73  or      eax, 10h
0x18005db76  jmp     short loc_18005DBD5
0x18005db78  bts     edi, 7
0x18005db7c  jmp     loc_18005DC81
0x18005db81  mov     eax, edi
0x18005db83  mov     ecx, edi
0x18005db85  or      eax, 40h
0x18005db88  bt      edi, 6
0x18005db8c  cmovnb  edi, eax
0x18005db8f  test    ecx, 40h
0x18005db95  jmp     loc_18005DC66
0x18005db9a  mov     r11d, edx
0x18005db9d  jmp     loc_18005DC78
0x18005dba2  test    dil, 2
0x18005dba6  jnz     loc_18005DC78
0x18005dbac  and     edi, 0FFFFFFFEh
0x18005dbaf  and     esi, 0FFFFFFFCh
0x18005dbb2  or      edi, 2
0x18005dbb5  bts     esi, 7
0x18005dbb9  jmp     loc_18005DC81
0x18005dbbe  test    r10d, r10d
0x18005dbc1  mov     eax, 1
0x18005dbc6  mov     edx, r10d
0x18005dbc9  mov     ecx, r10d
0x18005dbcc  cmovz   r10d, eax
0x18005dbd0  mov     eax, edi
0x18005dbd2  or      eax, r13d
0x18005dbd5  test    ecx, ecx
0x18005dbd7  cmovz   edi, eax
0x18005dbda  jmp     short loc_18005DC3C
0x18005dbdc  sub     ecx, 54h ; 'T'
0x18005dbdf  jz      loc_18005DC72
0x18005dbe5  sub     ecx, 0Eh
0x18005dbe8  jz      short loc_18005DC4F
0x18005dbea  sub     ecx, 1
0x18005dbed  jz      short loc_18005DC1F
0x18005dbef  sub     ecx, 0Bh
0x18005dbf2  jz      short loc_18005DC05
0x18005dbf4  cmp     ecx, 6
0x18005dbf7  jnz     loc_18005DAC0
0x18005dbfd  mov     eax, edi
0x18005dbff  bts     eax, 0Eh
0x18005dc03  jmp     short loc_18005DC55
0x18005dc05  test    r9d, r9d
0x18005dc08  mov     eax, 1
0x18005dc0d  mov     edx, r9d
0x18005dc10  mov     ecx, r9d
0x18005dc13  cmovz   r9d, eax
0x18005dc17  mov     eax, esi
0x18005dc19  btr     eax, 0Eh
0x18005dc1d  jmp     short loc_18005DC37
0x18005dc1f  test    r9d, r9d
0x18005dc22  mov     eax, 1
0x18005dc27  mov     edx, r9d
0x18005dc2a  mov     ecx, r9d
0x18005dc2d  cmovz   r9d, eax
0x18005dc31  mov     eax, esi
0x18005dc33  bts     eax, 0Eh
0x18005dc37  test    ecx, ecx
0x18005dc39  cmovz   esi, eax
0x18005dc3c  test    edx, edx
0x18005dc3e  mov     eax, r12d
0x18005dc41  mov     edx, 1
0x18005dc46  cmovz   eax, r8d
0x18005dc4a  mov     r8d, eax
0x18005dc4d  jmp     short loc_18005DC81
0x18005dc4f  mov     eax, edi
0x18005dc51  bts     eax, 0Fh
0x18005dc55  test    edi, 0C000h
0x18005dc5b  mov     ecx, edi
0x18005dc5d  cmovz   edi, eax
0x18005dc60  test    ecx, 0C000h
0x18005dc66  mov     eax, r12d
0x18005dc69  cmovz   eax, r8d
0x18005dc6d  mov     r8d, eax
0x18005dc70  jmp     short loc_18005DC81
0x18005dc72  bt      edi, 0Ch
0x18005dc76  jnb     short loc_18005DC7D
0x18005dc78  mov     r8d, r12d
0x18005dc7b  jmp     short loc_18005DC81
0x18005dc7d  bts     edi, 0Ch
0x18005dc81  add     rbx, 2
0x18005dc85  cmp     [rbx], r12w
0x18005dc89  jnz     loc_18005DB1E
0x18005dc8f  test    r11d, r11d
0x18005dc92  jz      loc_18005DD59
0x18005dc98  jmp     short loc_18005DC9E
0x18005dc9a  add     rbx, 2
0x18005dc9e  cmp     [rbx], r13w
0x18005dca2  jz      short loc_18005DC9A
0x18005dca4  mov     r8d, 3; MaxCount
0x18005dcaa  lea     rcx, aCcs; "ccs"
0x18005dcb1  mov     rdx, rbx; String2
0x18005dcb4  call    wcsncmp
0x18005dcb9  test    eax, eax
0x18005dcbb  jnz     loc_18005DAC0
0x18005dcc1  add     rbx, 6
0x18005dcc5  jmp     short loc_18005DCCB
0x18005dcc7  add     rbx, 2
0x18005dccb  movzx   eax, word ptr [rbx]
0x18005dcce  cmp     ax, r13w
0x18005dcd2  jz      short loc_18005DCC7
0x18005dcd4  cmp     ax, 3Dh ; '='
0x18005dcd8  jnz     loc_18005DAC0
0x18005dcde  add     rbx, 2
0x18005dce2  cmp     [rbx], r13w
0x18005dce6  jz      short loc_18005DCDE
0x18005dce8  mov     r8d, 5; MaxCount
0x18005dcee  lea     rdx, aUtf8_0; "UTF-8"
0x18005dcf5  mov     rcx, rbx; String1
0x18005dcf8  call    _wcsnicmp
0x18005dcfd  test    eax, eax
0x18005dcff  jnz     short loc_18005DD0B
0x18005dd01  add     rbx, 0Ah
0x18005dd05  bts     edi, 12h
0x18005dd09  jmp     short loc_18005DD59
0x18005dd0b  mov     r8d, 8; MaxCount
0x18005dd11  lea     rdx, aUtf16le_0; "UTF-16LE"
0x18005dd18  mov     rcx, rbx; String1
0x18005dd1b  call    _wcsnicmp
0x18005dd20  test    eax, eax
0x18005dd22  jnz     short loc_18005DD2E
0x18005dd24  add     rbx, 10h
0x18005dd28  bts     edi, 11h
0x18005dd2c  jmp     short loc_18005DD59
0x18005dd2e  mov     r8d, 7; MaxCount
0x18005dd34  lea     rdx, aUnicode_0; "UNICODE"
0x18005dd3b  mov     rcx, rbx; String1
0x18005dd3e  call    _wcsnicmp
0x18005dd43  test    eax, eax
0x18005dd45  jnz     loc_18005DAC0
0x18005dd4b  add     rbx, 0Eh
0x18005dd4f  bts     edi, 10h
0x18005dd53  jmp     short loc_18005DD59
0x18005dd55  lea     rbx, [rbx+2]
0x18005dd59  movzx   eax, word ptr [rbx]
0x18005dd5c  cmp     ax, r13w
0x18005dd60  jz      short loc_18005DD55
0x18005dd62  test    ax, ax
0x18005dd65  jnz     loc_18005DAC0
0x18005dd6b  mov     r9d, ebp; ShareFlag
0x18005dd6e  mov     dword ptr [rsp+78h+Reserved], 180h; PermissionFlag
0x18005dd76  mov     r8d, edi; OpenFlag
0x18005dd79  lea     rcx, [rsp+78h+FileHandle]; FileHandle
0x18005dd81  mov     rdx, r15; FileName
0x18005dd84  call    _wsopen_s
0x18005dd89  test    eax, eax
0x18005dd8b  jnz     loc_18005DADF
0x18005dd91  mov     eax, [rsp+78h+FileHandle]
0x18005dd98  mov     [r14+1Ch], eax
0x18005dd9c  mov     rax, r14
0x18005dd9f  mov     [r14+18h], esi
0x18005dda3  mov     [r14+8], r12d
0x18005dda7  mov     [r14], r12
0x18005ddaa  mov     [r14+10h], r12
0x18005ddae  mov     [r14+28h], r12
0x18005ddb2  add     rsp, 38h
0x18005ddb6  pop     r15
0x18005ddb8  pop     r14
0x18005ddba  pop     r13
0x18005ddbc  pop     r12
0x18005ddbe  pop     rdi
0x18005ddbf  pop     rsi
0x18005ddc0  pop     rbp
0x18005ddc1  pop     rbx
0x18005ddc2  retn
```
