# _wfdopen

- ea: `0x18004ef30`
- end: `0x18004f12b`
- name: `_wfdopen`
- size: `507`
- prototype: `FILE *__cdecl(int FileHandle, const wchar_t *Mode)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18004f410`

## callees

- `0x180007f00`
- `0x18002f050`
- `0x1800405e4`
- `0x18004ef30`
- `0x180057034`

## pseudocode

```c
FILE *__cdecl wfdopen(int FileHandle, const wchar_t *Mode)
{
  const wchar_t *v2; // r8
  unsigned __int64 v3; // rsi
  unsigned __int64 v4; // rdx
  __int64 v5; // rcx
  wchar_t v6; // ax
  int v7; // ebx
  __int64 v8; // r9
  unsigned int v9; // r10d
  unsigned int v10; // r11d
  unsigned int v11; // ebx
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  FILE *v16; // rax
  FILE *v17; // rdi

  v2 = Mode;
  v3 = FileHandle;
  if ( !Mode )
    goto LABEL_2;
  if ( FileHandle == -2 )
  {
    *errno() = 9;
    return 0;
  }
  if ( FileHandle < 0
    || FileHandle >= (unsigned int)nhandle
    || (v4 = (unsigned __int64)FileHandle >> 5,
        v5 = 56LL * (FileHandle & 0x1F),
        (*(_BYTE *)(_pioinfo[v3 >> 5] + v5 + 8) & 1) == 0) )
  {
    *errno() = 9;
LABEL_54:
    invalid_parameter(0, 0, 0, 0, 0);
  }
  while ( 1 )
  {
    v6 = *v2;
    if ( *v2 != 32 )
      break;
    ++v2;
  }
  if ( v6 != 97 )
  {
    if ( v6 == 114 )
    {
      v7 = 1;
      goto LABEL_15;
    }
    if ( v6 != 119 )
    {
LABEL_2:
      *errno() = 22;
      goto LABEL_54;
    }
  }
  v7 = 2;
LABEL_15:
  v8 = 1;
  v9 = 0;
  v10 = 0;
  v11 = commode | v7;
  while ( *++v2 && (_DWORD)v8 )
  {
    v5 = (unsigned int)*v2 - 32;
    if ( *v2 != 32 )
    {
      v5 = (unsigned int)*v2 - 43;
      switch ( *v2 )
      {
        case '+':
          if ( (v11 & 0x80u) == 0 )
            v11 = v11 & 0xFFFFFF7C | 0x80;
          else
            v8 = 0;
          break;
        case 'b':
          goto LABEL_24;
        case 'c':
          v4 = v9;
          v5 = v9;
          if ( !v9 )
            v9 = 1;
          v15 = 0;
          if ( !(_DWORD)v5 )
            v15 = v8;
          v8 = v15;
          v14 = v11 | 0x4000;
LABEL_34:
          if ( !(_DWORD)v4 )
            v11 = v14;
          break;
        case 'n':
          v4 = v9;
          v5 = v9;
          if ( !v9 )
            v9 = 1;
          v13 = 0;
          if ( !(_DWORD)v5 )
            v13 = v8;
          v8 = v13;
          v14 = v11 & 0xFFFFBFFF;
          goto LABEL_34;
        case 't':
LABEL_24:
          v5 = v10;
          if ( !v10 )
            v10 = 1;
          v12 = 0;
          if ( !(_DWORD)v5 )
            v12 = v8;
          v8 = v12;
          break;
        default:
          goto LABEL_2;
      }
    }
  }
  while ( *v2 == 32 )
    ++v2;
  if ( *v2 )
    goto LABEL_2;
  v16 = (FILE *)getstream(v5, v4, v2, v8);
  v17 = v16;
  if ( v16 )
  {
    v16->_flag = v11;
    v16->_file = v3;
    unlock_file(v16);
    return v17;
  }
  else
  {
    *errno() = 24;
    return 0;
  }
}

```

## disassembly

```asm
0x18004ef30  mov     [rsp+arg_0], rbx
0x18004ef35  mov     [rsp+arg_10], rsi
0x18004ef3a  push    rdi
0x18004ef3b  push    r14
0x18004ef3d  push    r15
0x18004ef3f  sub     rsp, 30h
0x18004ef43  mov     r8, rdx
0x18004ef46  movsxd  rsi, ecx
0x18004ef49  xor     r14d, r14d
0x18004ef4c  test    rdx, rdx
0x18004ef4f  jnz     short loc_18004EF61
0x18004ef51  call    _errno
0x18004ef56  mov     dword ptr [rax], 16h
0x18004ef5c  jmp     loc_18004F101
0x18004ef61  cmp     esi, 0FFFFFFFEh
0x18004ef64  jnz     short loc_18004EF76
0x18004ef66  call    _errno
0x18004ef6b  mov     dword ptr [rax], 9
0x18004ef71  jmp     loc_18004F115
0x18004ef76  test    ecx, ecx
0x18004ef78  js      loc_18004F0F6
0x18004ef7e  cmp     esi, cs:_nhandle
0x18004ef84  jnb     loc_18004F0F6
0x18004ef8a  mov     rdx, rsi
0x18004ef8d  shr     rdx, 5
0x18004ef91  lea     r9, __pioinfo
0x18004ef98  mov     eax, esi
0x18004ef9a  and     eax, 1Fh
0x18004ef9d  imul    rcx, rax, 38h ; '8'
0x18004efa1  mov     rax, [r9+rdx*8]
0x18004efa5  mov     r15d, 1
0x18004efab  test    [rax+rcx+8], r15b
0x18004efb0  jz      loc_18004F0F6
0x18004efb6  lea     edi, [r15+1Fh]
0x18004efba  jmp     short loc_18004EFC0
0x18004efbc  add     r8, 2
0x18004efc0  movzx   eax, word ptr [r8]
0x18004efc4  cmp     ax, di
0x18004efc7  jz      short loc_18004EFBC
0x18004efc9  cmp     ax, 61h ; 'a'
0x18004efcd  jz      short loc_18004EFDF
0x18004efcf  cmp     ax, 72h ; 'r'
0x18004efd3  jz      short loc_18004EFF8
0x18004efd5  cmp     ax, 77h ; 'w'
0x18004efd9  jnz     loc_18004EF51
0x18004efdf  mov     ebx, 2
0x18004efe4  mov     r9d, r15d
0x18004efe7  mov     r10d, r14d
0x18004efea  mov     r11d, r14d
0x18004efed  or      ebx, cs:_commode
0x18004eff3  jmp     loc_18004F09E
0x18004eff8  mov     ebx, r15d
0x18004effb  jmp     short loc_18004EFE4
0x18004effd  test    r9d, r9d
0x18004f000  jz      loc_18004F0B2
0x18004f006  movzx   ecx, word ptr [r8]
0x18004f00a  sub     ecx, edi
0x18004f00c  jz      loc_18004F09E
0x18004f012  sub     ecx, 0Bh
0x18004f015  jz      short loc_18004F08E
0x18004f017  sub     ecx, 37h ; '7'
0x18004f01a  jz      short loc_18004F02F
0x18004f01c  sub     ecx, r15d
0x18004f01f  jz      short loc_18004F06D
0x18004f021  sub     ecx, 0Bh
0x18004f024  jz      short loc_18004F047
0x18004f026  cmp     ecx, 6
0x18004f029  jnz     loc_18004EF51
0x18004f02f  mov     ecx, r11d
0x18004f032  test    r11d, r11d
0x18004f035  cmovz   r11d, r15d
0x18004f039  mov     eax, r14d
0x18004f03c  test    ecx, ecx
0x18004f03e  cmovz   eax, r9d
0x18004f042  mov     r9d, eax
0x18004f045  jmp     short loc_18004F09E
0x18004f047  mov     edx, r10d
0x18004f04a  mov     ecx, r10d
0x18004f04d  test    r10d, r10d
0x18004f050  cmovz   r10d, r15d
0x18004f054  mov     eax, r14d
0x18004f057  test    ecx, ecx
0x18004f059  cmovz   eax, r9d
0x18004f05d  mov     r9d, eax
0x18004f060  mov     eax, ebx
0x18004f062  btr     eax, 0Eh
0x18004f066  test    edx, edx
0x18004f068  cmovz   ebx, eax
0x18004f06b  jmp     short loc_18004F09E
0x18004f06d  mov     edx, r10d
0x18004f070  mov     ecx, r10d
0x18004f073  test    r10d, r10d
0x18004f076  cmovz   r10d, r15d
0x18004f07a  mov     eax, r14d
0x18004f07d  test    ecx, ecx
0x18004f07f  cmovz   eax, r9d
0x18004f083  mov     r9d, eax
0x18004f086  mov     eax, ebx
0x18004f088  bts     eax, 0Eh
0x18004f08c  jmp     short loc_18004F066
0x18004f08e  test    bl, bl
0x18004f090  jns     short loc_18004F097
0x18004f092  mov     r9d, r14d
0x18004f095  jmp     short loc_18004F09E
0x18004f097  and     ebx, 0FFFFFFFCh
0x18004f09a  bts     ebx, 7
0x18004f09e  add     r8, 2
0x18004f0a2  cmp     [r8], r14w
0x18004f0a6  jnz     loc_18004EFFD
0x18004f0ac  jmp     short loc_18004F0B2
0x18004f0ae  lea     r8, [r8+2]
0x18004f0b2  movzx   eax, word ptr [r8]
0x18004f0b6  cmp     ax, di
0x18004f0b9  jz      short loc_18004F0AE
0x18004f0bb  test    ax, ax
0x18004f0be  jnz     loc_18004EF51
0x18004f0c4  call    _getstream
0x18004f0c9  mov     rdi, rax
0x18004f0cc  mov     [rsp+48h+arg_8], rax
0x18004f0d1  test    rax, rax
0x18004f0d4  jnz     short loc_18004F0E3
0x18004f0d6  call    _errno
0x18004f0db  mov     dword ptr [rax], 18h
0x18004f0e1  jmp     short loc_18004F115
0x18004f0e3  mov     [rax+18h], ebx
0x18004f0e6  mov     [rax+1Ch], esi
0x18004f0e9  mov     rcx, rdi; Stream
0x18004f0ec  call    _unlock_file
0x18004f0f1  mov     rax, rdi
0x18004f0f4  jmp     short loc_18004F117
0x18004f0f6  call    _errno
0x18004f0fb  mov     dword ptr [rax], 9
0x18004f101  mov     [rsp+48h+Reserved], r14; Reserved
0x18004f106  xor     r9d, r9d; LineNo
0x18004f109  xor     r8d, r8d; FileName
0x18004f10c  xor     edx, edx; FunctionName
0x18004f10e  xor     ecx, ecx; Expression
0x18004f110  call    _invalid_parameter
0x18004f115  xor     eax, eax
0x18004f117  mov     rbx, [rsp+48h+arg_0]
0x18004f11c  mov     rsi, [rsp+48h+arg_10]
0x18004f121  add     rsp, 30h
0x18004f125  pop     r15
0x18004f127  pop     r14
0x18004f129  pop     rdi
0x18004f12a  retn
0x18007befc  push    rbp
0x18007befe  sub     rsp, 30h
0x18007bf02  mov     rbp, rdx
0x18007bf05  mov     rcx, [rbp+58h]; Stream
0x18007bf09  add     rsp, 30h
0x18007bf0d  pop     rbp
0x18007bf0e  jmp     _unlock_file
```
