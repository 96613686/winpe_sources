# CRTFRead::ReadFontName(_textfont *,int,STATE *)

- ea: `0x18007b10c`
- end: `0x18007b3a6`
- name: `?ReadFontName@CRTFRead@@AEAAXPEAU_textfont@@HPEAUSTATE@@@Z`
- size: `666`
- prototype: `void __fastcall(CRTFRead *__hidden this, struct _textfont *, int, struct STATE *)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180002740`
- `0x18007e2a0`

## callees

- `0x18001c1d4`
- `0x18001e170`
- `0x18001e3e0`
- `0x18002cad4`
- `0x180038730`
- `0x18003e56c`
- `0x180040b68`
- `0x1800426c8`
- `0x18004a2b0`
- `0x18007b10c`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18007b30a`
- `msvcrt!wcscpy_s` at `0x18007b30a`

## pseudocode

```c
void __fastcall CRTFRead::ReadFontName(CRTFRead *this, struct _textfont *a2, int a3, struct STATE *a4)
{
  WCHAR *v5; // rdi
  struct _textfont *v7; // rbx
  int v9; // eax
  bool v10; // zf
  char *v11; // rdx
  int v12; // r13d
  char v13; // cl
  int v14; // r8d
  unsigned int v15; // esi
  const char *v16; // r8
  int v17; // eax
  WCHAR v18; // r11
  __int64 v19; // r10
  CRTFRead *v20; // rcx
  unsigned __int16 *v21; // r11
  unsigned __int8 v22; // r8
  const unsigned __int16 **v23; // rdx
  int i; // edi
  unsigned __int8 v25; // r8
  int v26; // eax
  const wchar_t **v27; // r8
  __int16 CodePage; // ax
  int v29; // ecx
  unsigned __int16 *v30; // [rsp+40h] [rbp-38h] BYREF
  int v31; // [rsp+88h] [rbp+10h] BYREF

  if ( a2 )
  {
    v5 = (WCHAR *)((char *)a2 + 6);
    v7 = a2;
    v9 = 31;
    if ( !*((_WORD *)a2 + 3) )
      goto LABEL_7;
    while ( 1 )
    {
      v10 = v9 == 0;
      if ( v9 <= 0 )
        break;
      ++v5;
      --v9;
      if ( !*v5 )
      {
        v10 = v9 == 0;
        break;
      }
    }
    if ( !v10 )
    {
LABEL_7:
      v11 = (char *)*((_QWORD *)this + 17);
      v12 = 0;
      v13 = *v11;
      if ( *v11 )
      {
        v14 = v9;
        while ( v13 != 59 && v14 )
        {
          ++v11;
          --v14;
          v13 = *v11;
          if ( *v11 == 40 )
          {
            v12 = 1;
          }
          else if ( !v13 )
          {
            break;
          }
        }
      }
      *v11 = 0;
      v15 = *((_DWORD *)a4 + 3);
      if ( v15 == 42 )
        v15 = *((_DWORD *)this + 147);
      v16 = (const char *)*((_QWORD *)this + 17);
      v31 = 0;
      v17 = CW32System::MBTWC(v15, (unsigned int)v11, v16, -1, v5, v9, &v31);
      v18 = 0;
      v19 = v17;
      if ( v17 <= 0 || !v31 || a3 )
      {
        if ( *((_BYTE *)v7 + 2) == 1
          && v15 - 932 <= 0x12
          && (unsigned int)CW32System::GetTrailBytesCount(**((_BYTE **)this + 17), v15) )
        {
          *((_BYTE *)v7 + 2) = CW32System::GetCharSet(v15, 0);
        }
        if ( (int)v19 <= 0 )
        {
LABEL_26:
          if ( v7 == CArrayBase::Elem(this, 0) )
          {
            v7 = CRTFRead::SelectCurrentFont(v20, *((__int16 *)this + 238));
            v21 = 0;
          }
          v22 = *((_BYTE *)v7 + 2);
          v30 = v21;
          if ( v22 && (*((_BYTE *)a4 + 4) & 4) != 0 )
          {
            if ( !CRTFConverter::FindTaggedFont(v20, (const unsigned __int16 *)v7 + 3, v22, &v30) )
            {
              *((_DWORD *)a4 + 1) &= ~4u;
              *((_WORD *)v7 + 3) = 0;
            }
          }
          else
          {
            v23 = (const unsigned __int16 **)CRTFConverter::_rgtfi;
            if ( CRTFConverter::_rgtfi )
            {
              for ( i = (int)v21; i < CRTFConverter::_ctfi; ++i )
              {
                v25 = *((_BYTE *)v7 + 2);
                if ( v25 <= 1u || LOBYTE(v23[3 * i + 2]) == v25 )
                {
                  v26 = CW32System::lstrcmpi((const unsigned __int16 *)v7 + 3, v23[3 * i + 1]);
                  LODWORD(v21) = 0;
                  if ( !v26 )
                  {
                    v27 = (const wchar_t **)CRTFConverter::_rgtfi;
                    *((_BYTE *)v7 + 2) = *((_BYTE *)CRTFConverter::_rgtfi + 24 * i + 16);
                    wcscpy_s((wchar_t *)v7 + 3, 0x20u, v27[3 * i]);
                    CodePage = CW32System::GetCodePage(*((_BYTE *)v7 + 2));
                    *((_WORD *)v7 + 36) = CodePage;
                    STATE::SetCodePage(a4, CodePage);
                    return;
                  }
                  v23 = (const unsigned __int16 **)CRTFConverter::_rgtfi;
                }
              }
            }
            if ( v12 && v31 == (_DWORD)v21 )
            {
              v29 = (int)v21;
              if ( *((_WORD *)v7 + 3) != (_WORD)v21 )
              {
                do
                {
                  if ( *((_WORD *)v7 + v29 + 3) == 40 )
                    break;
                  ++v29;
                }
                while ( *((_WORD *)v7 + v29 + 3) != (_WORD)v21 );
              }
              if ( *((_WORD *)v7 + v29 + 3) != (_WORD)v21 && v29 > 0 )
              {
                do
                {
                  if ( *((_WORD *)v7 + (unsigned int)v29 + 2) != 32 )
                    break;
                  --v29;
                }
                while ( v29 > 0 );
                *((_WORD *)v7 + v29 + 3) = (_WORD)v21;
              }
            }
          }
          return;
        }
      }
      else
      {
        *((_BYTE *)v7 + 74) = 1;
      }
      v5[v19] = v18;
      goto LABEL_26;
    }
  }
}

```

## disassembly

```asm
0x18007b10c  test    rdx, rdx
0x18007b10f  jz      locret_18007B3A4
0x18007b115  mov     [rsp+arg_0], rbx
0x18007b11a  mov     [rsp+arg_10], rbp
0x18007b11f  push    rsi
0x18007b120  push    rdi
0x18007b121  push    r12
0x18007b123  push    r13
0x18007b125  push    r14
0x18007b127  sub     rsp, 50h
0x18007b12b  mov     r14, r9
0x18007b12e  lea     rdi, [rdx+6]
0x18007b132  xor     r9d, r9d
0x18007b135  mov     r12d, r8d
0x18007b138  mov     rbx, rdx
0x18007b13b  mov     rbp, rcx
0x18007b13e  lea     eax, [r9+1Fh]
0x18007b142  cmp     [rdi], r9w
0x18007b146  jz      short loc_18007B160
0x18007b148  test    eax, eax
0x18007b14a  jle     short loc_18007B15A
0x18007b14c  add     rdi, 2
0x18007b150  dec     eax
0x18007b152  cmp     [rdi], r9w
0x18007b156  jnz     short loc_18007B148
0x18007b158  test    eax, eax
0x18007b15a  jz      loc_18007B38C
0x18007b160  mov     rdx, [rcx+88h]
0x18007b167  mov     r13d, r9d
0x18007b16a  mov     cl, [rdx]
0x18007b16c  test    cl, cl
0x18007b16e  jz      short loc_18007B196
0x18007b170  mov     r8d, eax
0x18007b173  cmp     cl, 3Bh ; ';'
0x18007b176  jz      short loc_18007B196
0x18007b178  test    r8d, r8d
0x18007b17b  jz      short loc_18007B196
0x18007b17d  inc     rdx; unsigned int
0x18007b180  dec     r8d
0x18007b183  mov     cl, [rdx]
0x18007b185  cmp     cl, 28h ; '('
0x18007b188  jnz     short loc_18007B192
0x18007b18a  mov     r13d, 1
0x18007b190  jmp     short loc_18007B173
0x18007b192  test    cl, cl
0x18007b194  jnz     short loc_18007B173
0x18007b196  mov     [rdx], r9b
0x18007b199  mov     esi, [r14+0Ch]
0x18007b19d  cmp     esi, 2Ah ; '*'
0x18007b1a0  jnz     short loc_18007B1A8
0x18007b1a2  mov     esi, [rbp+24Ch]
0x18007b1a8  mov     r8, [rbp+88h]; char *
0x18007b1af  lea     rcx, [rsp+78h+arg_8]
0x18007b1b7  mov     [rsp+78h+var_48], rcx; int *
0x18007b1bc  mov     ecx, esi; int
0x18007b1be  mov     [rsp+78h+arg_8], r9d
0x18007b1c6  or      r9d, 0FFFFFFFFh; int
0x18007b1ca  mov     [rsp+78h+var_50], eax; int
0x18007b1ce  mov     [rsp+78h+var_58], rdi; LPWSTR
0x18007b1d3  call    ?MBTWC@CW32System@@SAHHKPEBDHPEAGHPEAH@Z; CW32System::MBTWC(int,ulong,char const *,int,ushort *,int,int *)
0x18007b1d8  xor     r11d, r11d
0x18007b1db  movsxd  r10, eax
0x18007b1de  test    eax, eax
0x18007b1e0  jle     short loc_18007B1F7
0x18007b1e2  cmp     [rsp+78h+arg_8], r11d
0x18007b1ea  jz      short loc_18007B1F7
0x18007b1ec  test    r12d, r12d
0x18007b1ef  jnz     short loc_18007B1F7
0x18007b1f1  mov     byte ptr [rbx+4Ah], 1
0x18007b1f5  jmp     short loc_18007B22D
0x18007b1f7  cmp     byte ptr [rbx+2], 1
0x18007b1fb  jnz     short loc_18007B228
0x18007b1fd  lea     eax, [rsi-3A4h]
0x18007b203  cmp     eax, 12h
0x18007b206  ja      short loc_18007B228
0x18007b208  mov     rcx, [rbp+88h]
0x18007b20f  mov     edx, esi; unsigned int
0x18007b211  mov     cl, [rcx]; unsigned __int8
0x18007b213  call    ?GetTrailBytesCount@CW32System@@SAHEI@Z; CW32System::GetTrailBytesCount(uchar,uint)
0x18007b218  test    eax, eax
0x18007b21a  jz      short loc_18007B228
0x18007b21c  xor     edx, edx; int *
0x18007b21e  mov     ecx, esi; int
0x18007b220  call    ?GetCharSet@CW32System@@SAEHPEAH@Z; CW32System::GetCharSet(int,int *)
0x18007b225  mov     [rbx+2], al
0x18007b228  test    r10d, r10d
0x18007b22b  jle     short loc_18007B232
0x18007b22d  mov     [rdi+r10*2], r11w
0x18007b232  xor     edx, edx; int
0x18007b234  mov     rcx, rbp; this
0x18007b237  call    ?Elem@CArrayBase@@QEBAPEAXJ@Z; CArrayBase::Elem(long)
0x18007b23c  cmp     rbx, rax
0x18007b23f  jnz     short loc_18007B253
0x18007b241  movsx   edx, word ptr [rbp+1DCh]; int
0x18007b248  call    ?SelectCurrentFont@CRTFRead@@AEAAPEAU_textfont@@H@Z; CRTFRead::SelectCurrentFont(int)
0x18007b24d  mov     rbx, rax
0x18007b250  xor     r11d, r11d
0x18007b253  mov     r8b, [rbx+2]; unsigned __int8
0x18007b257  mov     [rsp+78h+var_38], r11
0x18007b25c  test    r8b, r8b
0x18007b25f  jz      short loc_18007B290
0x18007b261  test    byte ptr [r14+4], 4
0x18007b266  jz      short loc_18007B290
0x18007b268  lea     r9, [rsp+78h+var_38]; unsigned __int16 **
0x18007b26d  lea     rdx, [rbx+6]; unsigned __int16 *
0x18007b271  call    ?FindTaggedFont@CRTFConverter@@IEAAHPEBGEPEAPEAG@Z; CRTFConverter::FindTaggedFont(ushort const *,uchar,ushort * *)
0x18007b276  xor     r9d, r9d
0x18007b279  test    eax, eax
0x18007b27b  jnz     loc_18007B38C
0x18007b281  and     dword ptr [r14+4], 0FFFFFFFBh
0x18007b286  mov     [rbx+6], r9w
0x18007b28b  jmp     loc_18007B38C
0x18007b290  mov     rdx, cs:?_rgtfi@CRTFConverter@@1PEAU_tfi@@EA; _tfi * CRTFConverter::_rgtfi
0x18007b297  test    rdx, rdx
0x18007b29a  jz      loc_18007B32F
0x18007b2a0  mov     edi, r11d
0x18007b2a3  cmp     edi, cs:?_ctfi@CRTFConverter@@1HA; int CRTFConverter::_ctfi
0x18007b2a9  jge     loc_18007B32F
0x18007b2af  mov     r8b, [rbx+2]
0x18007b2b3  cmp     r8b, 1
0x18007b2b7  jbe     short loc_18007B2C7
0x18007b2b9  movsxd  rax, edi
0x18007b2bc  lea     rcx, [rax+rax*2]
0x18007b2c0  cmp     [rdx+rcx*8+10h], r8b
0x18007b2c5  jnz     short loc_18007B2EA
0x18007b2c7  movsxd  rax, edi
0x18007b2ca  lea     rcx, [rbx+6]; unsigned __int16 *
0x18007b2ce  lea     rsi, [rax+rax*2]
0x18007b2d2  mov     rdx, [rdx+rsi*8+8]; unsigned __int16 *
0x18007b2d7  call    ?lstrcmpi@CW32System@@SAHPEBG0@Z; CW32System::lstrcmpi(ushort const *,ushort const *)
0x18007b2dc  xor     r11d, r11d
0x18007b2df  test    eax, eax
0x18007b2e1  jz      short loc_18007B2EE
0x18007b2e3  mov     rdx, cs:?_rgtfi@CRTFConverter@@1PEAU_tfi@@EA; _tfi * CRTFConverter::_rgtfi
0x18007b2ea  inc     edi
0x18007b2ec  jmp     short loc_18007B2A3
0x18007b2ee  mov     r8, cs:?_rgtfi@CRTFConverter@@1PEAU_tfi@@EA; _tfi * CRTFConverter::_rgtfi
0x18007b2f5  lea     rcx, [rbx+6]; Destination
0x18007b2f9  mov     edx, 20h ; ' '; SizeInWords
0x18007b2fe  mov     al, [r8+rsi*8+10h]
0x18007b303  mov     [rbx+2], al
0x18007b306  mov     r8, [r8+rsi*8]; Source
0x18007b30a  call    cs:__imp_wcscpy_s
0x18007b311  nop     dword ptr [rax+rax+00h]
0x18007b316  mov     cl, [rbx+2]; unsigned __int8
0x18007b319  call    ?GetCodePage@CW32System@@SAHE@Z; CW32System::GetCodePage(uchar)
0x18007b31e  movsx   edx, ax; int
0x18007b321  mov     rcx, r14; this
0x18007b324  mov     [rbx+48h], ax
0x18007b328  call    ?SetCodePage@STATE@@QEAAXJ@Z; STATE::SetCodePage(long)
0x18007b32d  jmp     short loc_18007B38C
0x18007b32f  test    r13d, r13d
0x18007b332  jz      short loc_18007B38C
0x18007b334  cmp     [rsp+78h+arg_8], r11d
0x18007b33c  jnz     short loc_18007B38C
0x18007b33e  mov     ecx, r11d
0x18007b341  cmp     [rbx+6], r11w
0x18007b346  jz      short loc_18007B360
0x18007b348  movsxd  rax, ecx
0x18007b34b  cmp     word ptr [rbx+rax*2+6], 28h ; '('
0x18007b351  jz      short loc_18007B360
0x18007b353  inc     ecx
0x18007b355  movsxd  rax, ecx
0x18007b358  cmp     [rbx+rax*2+6], r11w
0x18007b35e  jnz     short loc_18007B348
0x18007b360  movsxd  rax, ecx
0x18007b363  cmp     [rbx+rax*2+6], r11w
0x18007b369  jz      short loc_18007B38C
0x18007b36b  test    ecx, ecx
0x18007b36d  jle     short loc_18007B38C
0x18007b36f  mov     edx, 20h ; ' '
0x18007b374  mov     eax, ecx
0x18007b376  cmp     [rbx+rax*2+4], dx
0x18007b37b  jnz     short loc_18007B383
0x18007b37d  dec     ecx
0x18007b37f  test    ecx, ecx
0x18007b381  jg      short loc_18007B374
0x18007b383  movsxd  rcx, ecx
0x18007b386  mov     [rbx+rcx*2+6], r11w
0x18007b38c  lea     r11, [rsp+78h+var_28]
0x18007b391  mov     rbx, [r11+30h]
0x18007b395  mov     rbp, [r11+40h]
0x18007b399  mov     rsp, r11
0x18007b39c  pop     r14
0x18007b39e  pop     r13
0x18007b3a0  pop     r12
0x18007b3a2  pop     rdi
0x18007b3a3  pop     rsi
0x18007b3a4  retn
```
