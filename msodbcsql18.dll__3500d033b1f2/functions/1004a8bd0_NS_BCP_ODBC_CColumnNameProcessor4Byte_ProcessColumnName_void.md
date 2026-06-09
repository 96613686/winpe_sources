# NS_BCP_ODBC::CColumnNameProcessor4Byte::ProcessColumnName(void)

- ea: `0x1004a8bd0`
- end: `0x1004a8e87`
- name: `?ProcessColumnName@CColumnNameProcessor4Byte@NS_BCP_ODBC@@UEAAFXZ`
- size: `695`
- prototype: `__int16 __fastcall(NS_BCP_ODBC::CColumnNameProcessor4Byte *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x100412efc`
- `0x1004a8bd0`
- `0x1004af970`
- `0x1005212b4`
- `0x100546a7c`

## import_xrefs

- `KERNEL32!SetFilePointer` at `0x1004a8df8`
- `KERNEL32!SetFilePointer` at `0x1004a8df8`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x1004a8d3c`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x1004a8d3c`

## pseudocode

```c
__int64 __fastcall NS_BCP_ODBC::CColumnNameProcessor4Byte::ProcessColumnName(
        NS_BCP_ODBC::CColumnNameProcessor4Byte *this)
{
  unsigned __int16 v1; // bx
  unsigned __int8 *v2; // r15
  int v4; // esi
  char v5; // cl
  int v6; // ebp
  int v7; // ebp
  char v8; // cl
  __int64 v9; // rdx
  __int64 v10; // rcx

  v1 = 0;
  v2 = (unsigned __int8 *)this + 40;
  *((_DWORD *)this + 3) = 0;
  while ( 1 )
  {
    if ( (unsigned __int16)bcpRead(*((struct tagDBC **)this + 2), *((struct BCPFILE **)this + 3), 1u, v2) )
    {
      v1 = -1;
      if ( (bidGblFlags & 2) == 0 )
        return v1;
      v9 = 1305609;
      goto LABEL_46;
    }
    v4 = 1;
    v5 = *v2;
    if ( *((_DWORD *)this + 8) == 65001 )
      break;
    if ( (unsigned __int8)(v5 + 0x80) <= 0x7Eu )
    {
      if ( (unsigned __int16)bcpRead(
                               *((struct tagDBC **)this + 2),
                               *((struct BCPFILE **)this + 3),
                               1u,
                               (unsigned __int8 *)this + 41) )
      {
        v1 = -1;
        if ( (bidGblFlags & 2) == 0 )
          return v1;
        v9 = 1328137;
        goto LABEL_46;
      }
      v8 = *((_BYTE *)this + 41);
      if ( (unsigned __int8)(v8 - 64) <= 0x3Eu || (unsigned __int8)(v8 + 0x80) <= 0x7Eu )
      {
        v4 = 2;
      }
      else
      {
        if ( (unsigned __int8)(v8 - 48) > 9u )
        {
          v1 = -1;
          if ( (bidGblFlags & 2) == 0 )
            return v1;
          v9 = 1347593;
          goto LABEL_46;
        }
        if ( (unsigned __int16)bcpRead(
                                 *((struct tagDBC **)this + 2),
                                 *((struct BCPFILE **)this + 3),
                                 1u,
                                 (unsigned __int8 *)this + 42) )
        {
          v1 = -1;
          if ( (bidGblFlags & 2) == 0 )
            return v1;
          v9 = 1338377;
          goto LABEL_46;
        }
        if ( (unsigned __int16)bcpRead(
                                 *((struct tagDBC **)this + 2),
                                 *((struct BCPFILE **)this + 3),
                                 1u,
                                 (unsigned __int8 *)this + 43) )
        {
          v1 = -1;
          if ( (bidGblFlags & 2) == 0 )
            return v1;
          v9 = 1341449;
          goto LABEL_46;
        }
        v4 = 4;
      }
    }
LABEL_21:
    if ( !SystemLocale::FastAsciiMultiByteToWideChar(*((_DWORD *)this + 8), (LPCCH)v2, v4, (LPWSTR)this + 4, 1u, 0, 0) )
    {
      v1 = -1;
      if ( (bidGblFlags & 2) == 0 )
        return v1;
      v9 = 1358857;
      goto LABEL_46;
    }
    if ( iswspace(*((_WORD *)this + 4)) )
    {
      v10 = *((_QWORD *)this + 3);
      if ( *(_DWORD *)(v10 + 64) )
        *(_QWORD *)(v10 + 56) -= v4;
      else
        SetFilePointer(*(HANDLE *)v10, -v4, 0, 1u);
LABEL_38:
      if ( *((_DWORD *)this + 3) && *((int *)this + 3) <= 129 )
      {
LABEL_47:
        if ( (bidGblFlags & 2) != 0 )
          return (unsigned __int16)_bidx_SNACOdbc_ErrCode(0, 0x150809u, v1);
        return v1;
      }
      v1 = -1;
      if ( (bidGblFlags & 2) == 0 )
        return v1;
      v9 = 1375241;
LABEL_46:
      bidTraceMark(0, v9);
      goto LABEL_47;
    }
    if ( (int)++*((_DWORD *)this + 3) > 129 )
      goto LABEL_38;
  }
  if ( (v5 & 0xC0) != 0xC0 || v5 >= 0 )
    goto LABEL_21;
  v6 = ((v5 & 0xF0) != 0xE0) + 3;
  if ( (v5 & 0xE0) == 0xC0 )
    v6 = 2;
  v7 = v6 - 1;
  while ( !(unsigned __int16)bcpRead(
                               *((struct tagDBC **)this + 2),
                               *((struct BCPFILE **)this + 3),
                               1u,
                               (unsigned __int8 *)this + v4 + 40) )
  {
    ++v4;
    if ( !--v7 )
      goto LABEL_21;
  }
  v1 = -1;
  if ( (bidGblFlags & 2) != 0 )
  {
    v9 = 1318921;
    goto LABEL_46;
  }
  return v1;
}

```

## disassembly

```asm
0x1004a8bd0  mov     [rsp+arg_0], rbx
0x1004a8bd5  mov     [rsp+arg_8], rbp
0x1004a8bda  mov     [rsp+arg_10], rsi
0x1004a8bdf  push    rdi
0x1004a8be0  push    r12
0x1004a8be2  push    r13
0x1004a8be4  push    r14
0x1004a8be6  push    r15
0x1004a8be8  sub     rsp, 40h
0x1004a8bec  xor     ebx, ebx
0x1004a8bee  lea     r15, [rcx+28h]
0x1004a8bf2  mov     rdi, rcx
0x1004a8bf5  mov     [rcx+0Ch], ebx
0x1004a8bf8  lea     r13d, [rbx+1]
0x1004a8bfc  lea     r12d, [rbx+2]
0x1004a8c00  mov     rdx, [rdi+18h]; struct BCPFILE *
0x1004a8c04  mov     r9, r15; unsigned __int8 *
0x1004a8c07  mov     rcx, [rdi+10h]; struct tagDBC *
0x1004a8c0b  mov     r8d, r13d; unsigned int
0x1004a8c0e  call    ?bcpRead@@YAFPEAUtagDBC@@PEAUBCPFILE@@IPEAE@Z; bcpRead(tagDBC *,BCPFILE *,uint,uchar *)
0x1004a8c13  cmp     bx, ax
0x1004a8c16  jnz     loc_1004A8E32
0x1004a8c1c  cmp     dword ptr [rdi+20h], 0FDE9h
0x1004a8c23  mov     esi, r13d
0x1004a8c26  mov     cl, [r15]
0x1004a8c29  jnz     short loc_1004A8C8A
0x1004a8c2b  mov     al, cl
0x1004a8c2d  and     al, 0C0h
0x1004a8c2f  cmp     al, 0C0h
0x1004a8c31  jnz     loc_1004A8D0C
0x1004a8c37  test    cl, cl
0x1004a8c39  jns     loc_1004A8D0C
0x1004a8c3f  mov     al, cl
0x1004a8c41  mov     ebp, ebx
0x1004a8c43  and     al, 0E0h
0x1004a8c45  and     cl, 0F0h
0x1004a8c48  cmp     cl, 0E0h
0x1004a8c4b  setnz   bpl
0x1004a8c4f  add     ebp, 3
0x1004a8c52  cmp     al, 0C0h
0x1004a8c54  cmovz   ebp, r12d
0x1004a8c58  dec     ebp
0x1004a8c5a  mov     rdx, [rdi+18h]; struct BCPFILE *
0x1004a8c5e  mov     r8d, r13d; unsigned int
0x1004a8c61  mov     rcx, [rdi+10h]; struct tagDBC *
0x1004a8c65  movsxd  r9, esi
0x1004a8c68  add     r9, 28h ; '('
0x1004a8c6c  add     r9, rdi; unsigned __int8 *
0x1004a8c6f  call    ?bcpRead@@YAFPEAUtagDBC@@PEAUBCPFILE@@IPEAE@Z; bcpRead(tagDBC *,BCPFILE *,uint,uchar *)
0x1004a8c74  cmp     bx, ax
0x1004a8c77  jnz     loc_1004A8D60
0x1004a8c7d  add     esi, r13d
0x1004a8c80  add     ebp, 0FFFFFFFFh
0x1004a8c83  jnz     short loc_1004A8C5A
0x1004a8c85  jmp     loc_1004A8D0C
0x1004a8c8a  sub     cl, 80h
0x1004a8c8d  cmp     cl, 7Eh ; '~'
0x1004a8c90  ja      short loc_1004A8D0C
0x1004a8c92  mov     rdx, [rdi+18h]; struct BCPFILE *
0x1004a8c96  lea     r9, [rdi+29h]; unsigned __int8 *
0x1004a8c9a  mov     rcx, [rdi+10h]; struct tagDBC *
0x1004a8c9e  mov     r8d, r13d; unsigned int
0x1004a8ca1  call    ?bcpRead@@YAFPEAUtagDBC@@PEAUBCPFILE@@IPEAE@Z; bcpRead(tagDBC *,BCPFILE *,uint,uchar *)
0x1004a8ca6  cmp     bx, ax
0x1004a8ca9  jnz     loc_1004A8DC5
0x1004a8caf  mov     cl, [rdi+29h]
0x1004a8cb2  lea     eax, [rcx-40h]
0x1004a8cb5  cmp     al, 3Eh ; '>'
0x1004a8cb7  jbe     short loc_1004A8D09
0x1004a8cb9  lea     eax, [rcx-80h]
0x1004a8cbc  cmp     al, 7Eh ; '~'
0x1004a8cbe  jbe     short loc_1004A8D09
0x1004a8cc0  sub     cl, 30h ; '0'
0x1004a8cc3  cmp     cl, 9
0x1004a8cc6  ja      loc_1004A8DAE
0x1004a8ccc  mov     rdx, [rdi+18h]; struct BCPFILE *
0x1004a8cd0  lea     r9, [rdi+2Ah]; unsigned __int8 *
0x1004a8cd4  mov     rcx, [rdi+10h]; struct tagDBC *
0x1004a8cd8  mov     r8d, r13d; unsigned int
0x1004a8cdb  call    ?bcpRead@@YAFPEAUtagDBC@@PEAUBCPFILE@@IPEAE@Z; bcpRead(tagDBC *,BCPFILE *,uint,uchar *)
0x1004a8ce0  cmp     bx, ax
0x1004a8ce3  jnz     loc_1004A8D94
0x1004a8ce9  mov     rdx, [rdi+18h]; struct BCPFILE *
0x1004a8ced  lea     r9, [rdi+2Bh]; unsigned __int8 *
0x1004a8cf1  mov     rcx, [rdi+10h]; struct tagDBC *
0x1004a8cf5  mov     r8d, r13d; unsigned int
0x1004a8cf8  call    ?bcpRead@@YAFPEAUtagDBC@@PEAUBCPFILE@@IPEAE@Z; bcpRead(tagDBC *,BCPFILE *,uint,uchar *)
0x1004a8cfd  cmp     bx, ax
0x1004a8d00  jnz     short loc_1004A8D7A
0x1004a8d02  mov     esi, 4
0x1004a8d07  jmp     short loc_1004A8D0C
0x1004a8d09  mov     esi, r12d
0x1004a8d0c  mov     ecx, [rdi+20h]; CodePage
0x1004a8d0f  lea     r9, [rdi+8]; lpWideCharStr
0x1004a8d13  mov     [rsp+68h+var_38], bl; bool
0x1004a8d17  mov     rdx, r15; lpMultiByteStr
0x1004a8d1a  movsxd  rbp, esi
0x1004a8d1d  mov     r8, rbp; cbMultiByte
0x1004a8d20  mov     [rsp+68h+var_40], rbx; unsigned int *
0x1004a8d25  mov     [rsp+68h+var_48], r13; unsigned __int64
0x1004a8d2a  call    ?FastAsciiMultiByteToWideChar@SystemLocale@@CA_KIPEBD_JPEAG_KPEAK_N@Z; SystemLocale::FastAsciiMultiByteToWideChar(uint,char const *,__int64,ushort *,unsigned __int64,ulong *,bool)
0x1004a8d2f  test    rax, rax
0x1004a8d32  jz      loc_1004A8E1F
0x1004a8d38  movzx   ecx, word ptr [rdi+8]; C
0x1004a8d3c  call    cs:__imp_iswspace
0x1004a8d42  test    eax, eax
0x1004a8d44  jnz     loc_1004A8DDC
0x1004a8d4a  add     [rdi+0Ch], r13d
0x1004a8d4e  cmp     dword ptr [rdi+0Ch], 81h
0x1004a8d55  jg      loc_1004A8DFE
0x1004a8d5b  jmp     loc_1004A8C00
0x1004a8d60  or      ebx, 0FFFFFFFFh
0x1004a8d63  test    byte ptr cs:_bidGblFlags, r12b
0x1004a8d6a  jz      loc_1004A8E66
0x1004a8d70  mov     edx, 142009h
0x1004a8d75  jmp     loc_1004A8E43
0x1004a8d7a  or      ebx, 0FFFFFFFFh
0x1004a8d7d  test    byte ptr cs:_bidGblFlags, r12b
0x1004a8d84  jz      loc_1004A8E66
0x1004a8d8a  mov     edx, 147809h
0x1004a8d8f  jmp     loc_1004A8E43
0x1004a8d94  or      ebx, 0FFFFFFFFh
0x1004a8d97  test    byte ptr cs:_bidGblFlags, r12b
0x1004a8d9e  jz      loc_1004A8E66
0x1004a8da4  mov     edx, 146C09h
0x1004a8da9  jmp     loc_1004A8E43
0x1004a8dae  or      ebx, 0FFFFFFFFh
0x1004a8db1  test    byte ptr cs:_bidGblFlags, r12b
0x1004a8db8  jz      loc_1004A8E66
0x1004a8dbe  mov     edx, 149009h
0x1004a8dc3  jmp     short loc_1004A8E43
0x1004a8dc5  or      ebx, 0FFFFFFFFh
0x1004a8dc8  test    byte ptr cs:_bidGblFlags, r12b
0x1004a8dcf  jz      loc_1004A8E66
0x1004a8dd5  mov     edx, 144409h
0x1004a8dda  jmp     short loc_1004A8E43
0x1004a8ddc  mov     rcx, [rdi+18h]
0x1004a8de0  cmp     [rcx+40h], ebx
0x1004a8de3  jz      short loc_1004A8DEB
0x1004a8de5  sub     [rcx+38h], rbp
0x1004a8de9  jmp     short loc_1004A8DFE
0x1004a8deb  mov     rcx, [rcx]; hFile
0x1004a8dee  neg     esi
0x1004a8df0  mov     edx, esi; lDistanceToMove
0x1004a8df2  mov     r9d, r13d; dwMoveMethod
0x1004a8df5  xor     r8d, r8d; lpDistanceToMoveHigh
0x1004a8df8  call    cs:__imp_SetFilePointer
0x1004a8dfe  cmp     [rdi+0Ch], ebx
0x1004a8e01  jz      short loc_1004A8E0C
0x1004a8e03  cmp     dword ptr [rdi+0Ch], 81h
0x1004a8e0a  jle     short loc_1004A8E4A
0x1004a8e0c  or      ebx, 0FFFFFFFFh
0x1004a8e0f  test    byte ptr cs:_bidGblFlags, r12b
0x1004a8e16  jz      short loc_1004A8E66
0x1004a8e18  mov     edx, 14FC09h
0x1004a8e1d  jmp     short loc_1004A8E43
0x1004a8e1f  or      ebx, 0FFFFFFFFh
0x1004a8e22  test    byte ptr cs:_bidGblFlags, r12b
0x1004a8e29  jz      short loc_1004A8E66
0x1004a8e2b  mov     edx, 14BC09h
0x1004a8e30  jmp     short loc_1004A8E43
0x1004a8e32  or      ebx, 0FFFFFFFFh
0x1004a8e35  test    byte ptr cs:_bidGblFlags, r12b
0x1004a8e3c  jz      short loc_1004A8E66
0x1004a8e3e  mov     edx, 13EC09h
0x1004a8e43  xor     ecx, ecx
0x1004a8e45  call    _bidTraceMark
0x1004a8e4a  test    byte ptr cs:_bidGblFlags, r12b
0x1004a8e51  jz      short loc_1004A8E66
0x1004a8e53  movzx   r8d, bx; __int16
0x1004a8e57  mov     edx, 150809h; unsigned __int64
0x1004a8e5c  xor     ecx, ecx; unsigned __int64
0x1004a8e5e  call    ?_bidx_SNACOdbc_ErrCode@@YAF_K0F@Z; _bidx_SNACOdbc_ErrCode(unsigned __int64,unsigned __int64,short)
0x1004a8e63  movzx   ebx, ax
0x1004a8e66  lea     r11, [rsp+68h+var_28]
0x1004a8e6b  movzx   eax, bx
0x1004a8e6e  mov     rbx, [r11+30h]
0x1004a8e72  mov     rbp, [r11+38h]
0x1004a8e76  mov     rsi, [r11+40h]
0x1004a8e7a  mov     rsp, r11
0x1004a8e7d  pop     r15
0x1004a8e7f  pop     r14
0x1004a8e81  pop     r13
0x1004a8e83  pop     r12
0x1004a8e85  pop     rdi
0x1004a8e86  retn
```
