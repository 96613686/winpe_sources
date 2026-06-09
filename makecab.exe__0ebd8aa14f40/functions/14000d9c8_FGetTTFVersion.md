# FGetTTFVersion

- ea: `0x14000d9c8`
- end: `0x14000dcf0`
- name: `FGetTTFVersion`
- size: `808`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140009c24`

## callees

- `0x140001508`
- `0x14000d9c8`
- `0x14000e450`

## import_xrefs

- `msvcrt!_lseek` at `0x14000db39`
- `msvcrt!_lseek` at `0x14000dc3a`
- `msvcrt!_lseek` at `0x14000db39`
- `msvcrt!_lseek` at `0x14000dc3a`
- `msvcrt!_open` at `0x14000da6b`
- `msvcrt!_open` at `0x14000da6b`
- `msvcrt!_close` at `0x14000dae1`
- `msvcrt!_close` at `0x14000dc85`
- `msvcrt!_close` at `0x14000dae1`
- `msvcrt!_close` at `0x14000dc85`
- `msvcrt!_read` at `0x14000da86`
- `msvcrt!_read` at `0x14000dac3`
- `msvcrt!_read` at `0x14000db50`
- `msvcrt!_read` at `0x14000db81`
- `msvcrt!_read` at `0x14000dc68`
- `msvcrt!_read` at `0x14000da86`
- `msvcrt!_read` at `0x14000dac3`
- `msvcrt!_read` at `0x14000db50`
- `msvcrt!_read` at `0x14000db81`
- `msvcrt!_read` at `0x14000dc68`
- `msvcrt!atol` at `0x14000dca8`
- `msvcrt!atol` at `0x14000dcd0`
- `msvcrt!atol` at `0x14000dca8`
- `msvcrt!atol` at `0x14000dcd0`
- `msvcrt!strspn` at `0x14000dcbd`
- `msvcrt!strspn` at `0x14000dcbd`
- `msvcrt!_stricmp` at `0x14000da55`
- `msvcrt!_stricmp` at `0x14000da55`
- `msvcrt!strpbrk` at `0x14000dc97`
- `msvcrt!strpbrk` at `0x14000dc97`

## pseudocode

```c
__int64 __fastcall FGetTTFVersion(__int64 a1, _DWORD *a2)
{
  unsigned __int64 v3; // rax
  int v4; // eax
  int v5; // edi
  unsigned int v6; // ebx
  unsigned int v7; // esi
  unsigned int v9; // ebx
  int v10; // ebx
  int v11; // r15d
  __int16 v12; // si
  int v13; // ebx
  __int64 v14; // rbx
  char *v15; // rax
  const char *v16; // rbx
  int v17; // edi
  size_t v18; // rax
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int16 v20; // [rsp+24h] [rbp-DCh]
  __int64 v21; // [rsp+28h] [rbp-D8h] BYREF
  int v22; // [rsp+30h] [rbp-D0h]
  __int128 v23; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE DstBuf[40]; // [rsp+48h] [rbp-B8h] BYREF
  char Str[256]; // [rsp+70h] [rbp-90h] BYREF

  v19 = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  memset(DstBuf, 0, 28);
  v23 = 0;
  if ( a2 )
  {
    v3 = -1;
    do
      ++v3;
    while ( pszDest[v3] );
    if ( v3 >= 5 && !_stricmp(".TTF", &pszDest[v3 - 4]) )
    {
      v4 = _open(pszDest, 0x8000);
      v5 = v4;
      if ( v4 != -1 )
      {
        if ( _read(v4, DstBuf, 0xCu) == 12 )
        {
          v6 = 0;
          v7 = DstBuf[5] | (unsigned __int16)(DstBuf[4] << 8);
          if ( v7 )
          {
            while ( v6 < 0x28 && _read(v5, &v23, 0x10u) == 16 )
            {
              if ( (_DWORD)v23 == 1701667182 )
              {
                v9 = ((WORD4(v23) & 0xFF00 | (DWORD2(v23) << 16)) << 8)
                   | ((HIWORD(DWORD2(v23)) | DWORD2(v23) & 0xFF0000u) >> 8);
                if ( _lseek(v5, v9, 0) == v9 && _read(v5, &v19, 6u) == 6 )
                {
                  v10 = HIBYTE(HIWORD(v19)) | (unsigned __int16)(BYTE2(v19) << 8);
                  if ( v10 )
                  {
                    while ( _read(v5, &v21, 0xCu) == 12 )
                    {
                      if ( (BYTE1(v21) | (unsigned __int16)((unsigned __int8)v21 << 8)) == 1
                        && (HIBYTE(HIWORD(v21)) | (unsigned __int16)(BYTE6(v21) << 8)) == 5 )
                      {
                        v11 = BYTE1(v22);
                        v12 = (unsigned __int8)v22;
                        v13 = (HIBYTE(HIWORD(v22)) | (unsigned __int16)(BYTE2(v22) << 8))
                            + (HIBYTE(v20) | (unsigned __int16)((unsigned __int8)v20 << 8))
                            + (((WORD4(v23) & 0xFF00 | (DWORD2(v23) << 16)) << 8)
                             | ((HIWORD(DWORD2(v23)) | DWORD2(v23) & 0xFF0000u) >> 8));
                        if ( _lseek(v5, v13, 0) != v13 )
                          goto LABEL_13;
                        v14 = v11 | (unsigned int)(unsigned __int16)(v12 << 8);
                        if ( (unsigned int)v14 > 0xFF || _read(v5, Str, v14) != (_DWORD)v14 )
                          goto LABEL_13;
                        Str[v14] = 0;
                        _close(v5);
                        v15 = strpbrk(Str, "0123456789");
                        v16 = v15;
                        if ( v15 )
                        {
                          v17 = atol(v15) << 16;
                          v18 = strspn(v16, "0123456789");
                          if ( v16[v18] == 46 )
                            LODWORD(v15) = v17 + (unsigned __int16)atol(&v16[v18 + 1]);
                          else
                            LODWORD(v15) = v17;
                        }
                        *a2 = (_DWORD)v15;
                        return 1;
                      }
                      if ( !--v10 )
                        goto LABEL_13;
                    }
                  }
                }
                break;
              }
              if ( ++v6 >= v7 )
                break;
            }
          }
        }
LABEL_13:
        _close(v5);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14000d9c8  push    rbp
0x14000d9ca  push    rbx
0x14000d9cb  push    rsi
0x14000d9cc  push    rdi
0x14000d9cd  push    r12
0x14000d9cf  push    r13
0x14000d9d1  push    r14
0x14000d9d3  push    r15
0x14000d9d5  lea     rbp, [rsp-88h]
0x14000d9dd  sub     rsp, 188h
0x14000d9e4  mov     rax, cs:__security_cookie
0x14000d9eb  xor     rax, rsp
0x14000d9ee  mov     [rbp+0C0h+var_50], rax
0x14000d9f2  xor     eax, eax
0x14000d9f4  xorps   xmm0, xmm0
0x14000d9f7  mov     [rsp+1C0h+var_1A0], eax
0x14000d9fb  mov     r14, rdx
0x14000d9fe  mov     [rsp+1C0h+var_19C], ax
0x14000da03  mov     [rsp+1C0h+var_198], rax
0x14000da08  mov     [rsp+1C0h+var_190], eax
0x14000da0c  movups  xmmword ptr [rsp+1C0h+DstBuf], xmm0
0x14000da11  movups  xmmword ptr [rsp+1C0h+DstBuf+0Ch], xmm0
0x14000da16  movups  [rsp+1C0h+var_188], xmm0
0x14000da1b  test    rdx, rdx
0x14000da1e  jz      loc_14000DAE7
0x14000da24  lea     rbx, pszDest
0x14000da2b  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000da2f  inc     rax
0x14000da32  cmp     byte ptr [rbx+rax], 0
0x14000da36  jnz     short loc_14000DA2F
0x14000da38  mov     r13d, 5
0x14000da3e  cmp     rax, r13
0x14000da41  jb      loc_14000DAE7
0x14000da47  lea     rdx, [rbx-4]
0x14000da4b  add     rdx, rax; String2
0x14000da4e  lea     rcx, aTtf; ".TTF"
0x14000da55  call    cs:__imp__stricmp
0x14000da5b  test    eax, eax
0x14000da5d  jnz     loc_14000DAE7
0x14000da63  mov     edx, 8000h; OpenFlag
0x14000da68  mov     rcx, rbx; FileName
0x14000da6b  call    cs:__imp__open
0x14000da71  mov     edi, eax
0x14000da73  cmp     eax, 0FFFFFFFFh
0x14000da76  jz      short loc_14000DAE7
0x14000da78  lea     r15d, [r13+7]
0x14000da7c  mov     ecx, eax; FileHandle
0x14000da7e  mov     r8d, r15d; MaxCharCount
0x14000da81  lea     rdx, [rsp+1C0h+DstBuf]; DstBuf
0x14000da86  call    cs:__imp__read
0x14000da8c  cmp     eax, r15d
0x14000da8f  jnz     short loc_14000DADF
0x14000da91  movzx   ecx, [rsp+1C0h+DstBuf+4]
0x14000da96  lea     ebx, [r13-5]
0x14000da9a  movzx   eax, word ptr [rsp+1C0h+DstBuf+4]
0x14000da9f  shl     cx, 8
0x14000daa3  movzx   esi, cx
0x14000daa6  shr     eax, 8
0x14000daa9  or      esi, eax
0x14000daab  jbe     short loc_14000DADF
0x14000daad  lea     r12d, [r13-4]
0x14000dab1  cmp     ebx, 28h ; '('
0x14000dab4  jnb     short loc_14000DADF
0x14000dab6  mov     r8d, 10h; MaxCharCount
0x14000dabc  lea     rdx, [rsp+1C0h+var_188]; DstBuf
0x14000dac1  mov     ecx, edi; FileHandle
0x14000dac3  call    cs:__imp__read
0x14000dac9  cmp     eax, 10h
0x14000dacc  jnz     short loc_14000DADF
0x14000dace  cmp     dword ptr [rsp+1C0h+var_188], 656D616Eh
0x14000dad6  jz      short loc_14000DB09
0x14000dad8  add     ebx, r12d
0x14000dadb  cmp     ebx, esi
0x14000dadd  jb      short loc_14000DAB1
0x14000dadf  mov     ecx, edi; FileHandle
0x14000dae1  call    cs:__imp__close
0x14000dae7  xor     eax, eax
0x14000dae9  mov     rcx, [rbp+0C0h+var_50]
0x14000daed  xor     rcx, rsp; StackCookie
0x14000daf0  call    __security_check_cookie
0x14000daf5  add     rsp, 188h
0x14000dafc  pop     r15
0x14000dafe  pop     r14
0x14000db00  pop     r13
0x14000db02  pop     r12
0x14000db04  pop     rdi
0x14000db05  pop     rsi
0x14000db06  pop     rbx
0x14000db07  pop     rbp
0x14000db08  retn
0x14000db09  mov     ecx, dword ptr [rsp+1C0h+var_188+8]
0x14000db0d  mov     esi, 0FF0000h
0x14000db12  mov     ebx, ecx
0x14000db14  mov     eax, ecx
0x14000db16  shr     eax, 10h
0x14000db19  and     ebx, esi
0x14000db1b  or      ebx, eax
0x14000db1d  xor     r8d, r8d; Origin
0x14000db20  mov     eax, ecx
0x14000db22  shr     ebx, 8
0x14000db25  shl     eax, 10h
0x14000db28  and     ecx, 0FF00h
0x14000db2e  or      eax, ecx
0x14000db30  mov     ecx, edi; FileHandle
0x14000db32  shl     eax, 8
0x14000db35  or      ebx, eax
0x14000db37  mov     edx, ebx; Offset
0x14000db39  call    cs:__imp__lseek
0x14000db3f  cmp     eax, ebx
0x14000db41  jnz     short loc_14000DADF
0x14000db43  mov     r8d, 6; MaxCharCount
0x14000db49  lea     rdx, [rsp+1C0h+var_1A0]; DstBuf
0x14000db4e  mov     ecx, edi; FileHandle
0x14000db50  call    cs:__imp__read
0x14000db56  cmp     eax, 6
0x14000db59  jnz     short loc_14000DADF
0x14000db5b  movzx   eax, byte ptr [rsp+1C0h+var_1A0+2]
0x14000db60  shl     ax, 8
0x14000db64  movzx   ebx, ax
0x14000db67  movzx   eax, word ptr [rsp+1C0h+var_1A0+2]
0x14000db6c  shr     eax, 8
0x14000db6f  or      ebx, eax
0x14000db71  jz      loc_14000DADF
0x14000db77  mov     r8d, r15d; MaxCharCount
0x14000db7a  lea     rdx, [rsp+1C0h+var_198]; DstBuf
0x14000db7f  mov     ecx, edi; FileHandle
0x14000db81  call    cs:__imp__read
0x14000db87  cmp     eax, r15d
0x14000db8a  jnz     loc_14000DADF
0x14000db90  movzx   ecx, byte ptr [rsp+1C0h+var_198]
0x14000db95  movzx   eax, word ptr [rsp+1C0h+var_198]
0x14000db9a  shl     cx, 8
0x14000db9e  shr     ax, 8
0x14000dba2  or      cx, ax
0x14000dba5  cmp     cx, r12w
0x14000dba9  jnz     short loc_14000DBC6
0x14000dbab  movzx   ecx, byte ptr [rsp+1C0h+var_198+6]
0x14000dbb0  movzx   eax, word ptr [rsp+1C0h+var_198+6]
0x14000dbb5  shl     cx, 8
0x14000dbb9  shr     ax, 8
0x14000dbbd  or      cx, ax
0x14000dbc0  cmp     cx, r13w
0x14000dbc4  jz      short loc_14000DBD0
0x14000dbc6  add     ebx, 0FFFFFFFFh
0x14000dbc9  jnz     short loc_14000DB77
0x14000dbcb  jmp     loc_14000DADF
0x14000dbd0  mov     ecx, dword ptr [rsp+1C0h+var_188+8]
0x14000dbd4  xor     r8d, r8d; Origin
0x14000dbd7  movzx   r15d, word ptr [rsp+1C0h+var_190]
0x14000dbdd  mov     ebx, ecx
0x14000dbdf  mov     eax, ecx
0x14000dbe1  shr     r15d, 8
0x14000dbe5  shr     eax, 10h
0x14000dbe8  and     ebx, esi
0x14000dbea  movzx   esi, byte ptr [rsp+1C0h+var_190]
0x14000dbef  or      ebx, eax
0x14000dbf1  mov     eax, ecx
0x14000dbf3  shr     ebx, 8
0x14000dbf6  shl     eax, 10h
0x14000dbf9  and     ecx, 0FF00h
0x14000dbff  or      eax, ecx
0x14000dc01  shl     eax, 8
0x14000dc04  or      ebx, eax
0x14000dc06  movzx   eax, byte ptr [rsp+1C0h+var_19C]
0x14000dc0b  shl     ax, 8
0x14000dc0f  movzx   ecx, ax
0x14000dc12  movzx   eax, [rsp+1C0h+var_19C]
0x14000dc17  shr     eax, 8
0x14000dc1a  or      ecx, eax
0x14000dc1c  movzx   eax, byte ptr [rsp+1C0h+var_190+2]
0x14000dc21  add     ebx, ecx
0x14000dc23  shl     ax, 8
0x14000dc27  movzx   ecx, ax
0x14000dc2a  movzx   eax, word ptr [rsp+1C0h+var_190+2]
0x14000dc2f  shr     eax, 8
0x14000dc32  or      ecx, eax
0x14000dc34  add     ebx, ecx
0x14000dc36  mov     ecx, edi; FileHandle
0x14000dc38  mov     edx, ebx; Offset
0x14000dc3a  call    cs:__imp__lseek
0x14000dc40  cmp     eax, ebx
0x14000dc42  jnz     loc_14000DADF
0x14000dc48  shl     si, 8
0x14000dc4c  movzx   ebx, si
0x14000dc4f  or      ebx, r15d
0x14000dc52  cmp     ebx, 0FFh
0x14000dc58  ja      loc_14000DADF
0x14000dc5e  mov     r8d, ebx; MaxCharCount
0x14000dc61  lea     rdx, [rsp+1C0h+Str]; DstBuf
0x14000dc66  mov     ecx, edi; FileHandle
0x14000dc68  call    cs:__imp__read
0x14000dc6e  cmp     eax, ebx
0x14000dc70  jnz     loc_14000DADF
0x14000dc76  cmp     ebx, 100h
0x14000dc7c  jnb     short loc_14000DCEA
0x14000dc7e  mov     ecx, edi; FileHandle
0x14000dc80  mov     [rsp+rbx+1C0h+Str], 0
0x14000dc85  call    cs:__imp__close
0x14000dc8b  lea     rdx, a0123456789; "0123456789"
0x14000dc92  lea     rcx, [rsp+1C0h+Str]; Str
0x14000dc97  call    cs:__imp_strpbrk
0x14000dc9d  mov     rbx, rax
0x14000dca0  test    rax, rax
0x14000dca3  jz      short loc_14000DCDF
0x14000dca5  mov     rcx, rbx; String
0x14000dca8  call    cs:__imp_atol
0x14000dcae  lea     rdx, a0123456789; "0123456789"
0x14000dcb5  mov     rcx, rbx; Str
0x14000dcb8  mov     edi, eax
0x14000dcba  shl     edi, 10h
0x14000dcbd  call    cs:__imp_strspn
0x14000dcc3  cmp     byte ptr [rax+rbx], 2Eh ; '.'
0x14000dcc7  jnz     short loc_14000DCDD
0x14000dcc9  lea     rcx, [rax+1]
0x14000dccd  add     rcx, rbx; String
0x14000dcd0  call    cs:__imp_atol
0x14000dcd6  movzx   eax, ax
0x14000dcd9  add     eax, edi
0x14000dcdb  jmp     short loc_14000DCDF
0x14000dcdd  mov     eax, edi
0x14000dcdf  mov     [r14], eax
0x14000dce2  mov     eax, r12d
0x14000dce5  jmp     loc_14000DAE9
0x14000dcea  call    __report_rangecheckfailure
```
