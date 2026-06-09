# CRTFRead::ReadFontName(_textfont *,int,STATE *)

- ea: `0x180078d58`
- end: `0x180078fe7`
- name: `?ReadFontName@CRTFRead@@AEAAXPEAU_textfont@@HPEAUSTATE@@@Z`
- size: `655`
- prototype: `void __fastcall(CRTFRead *__hidden this, struct _textfont *, int, struct STATE *)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1800026c0`
- `0x18007bf38`

## callees

- `0x180027f70`
- `0x180029bd0`
- `0x18002a144`
- `0x18002a16c`
- `0x180031e80`
- `0x180037760`
- `0x18003dc58`
- `0x18004180c`
- `0x180049148`
- `0x180078d58`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180078f52`
- `msvcrt!wcscpy_s` at `0x180078f52`

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
0x180078d58  test    rdx, rdx
0x180078d5b  jz      locret_180078FE6
0x180078d61  mov     [rsp+arg_0], rbx
0x180078d66  mov     [rsp+arg_10], rbp
0x180078d6b  push    rsi
0x180078d6c  push    rdi
0x180078d6d  push    r12
0x180078d6f  push    r13
0x180078d71  push    r14
0x180078d73  sub     rsp, 50h
0x180078d77  mov     r14, r9
0x180078d7a  lea     rdi, [rdx+6]
0x180078d7e  xor     r9d, r9d
0x180078d81  mov     r12d, r8d
0x180078d84  mov     rbx, rdx
0x180078d87  mov     rbp, rcx
0x180078d8a  lea     eax, [r9+1Fh]
0x180078d8e  cmp     [rdi], r9w
0x180078d92  jz      short loc_180078DAC
0x180078d94  test    eax, eax
0x180078d96  jle     short loc_180078DA6
0x180078d98  add     rdi, 2
0x180078d9c  dec     eax
0x180078d9e  cmp     [rdi], r9w
0x180078da2  jnz     short loc_180078D94
0x180078da4  test    eax, eax
0x180078da6  jz      loc_180078FCE
0x180078dac  mov     rdx, [rcx+88h]
0x180078db3  mov     r13d, r9d
0x180078db6  mov     cl, [rdx]
0x180078db8  test    cl, cl
0x180078dba  jz      short loc_180078DE2
0x180078dbc  mov     r8d, eax
0x180078dbf  cmp     cl, 3Bh ; ';'
0x180078dc2  jz      short loc_180078DE2
0x180078dc4  test    r8d, r8d
0x180078dc7  jz      short loc_180078DE2
0x180078dc9  inc     rdx; unsigned int
0x180078dcc  dec     r8d
0x180078dcf  mov     cl, [rdx]
0x180078dd1  cmp     cl, 28h ; '('
0x180078dd4  jnz     short loc_180078DDE
0x180078dd6  mov     r13d, 1
0x180078ddc  jmp     short loc_180078DBF
0x180078dde  test    cl, cl
0x180078de0  jnz     short loc_180078DBF
0x180078de2  mov     [rdx], r9b
0x180078de5  mov     esi, [r14+0Ch]
0x180078de9  cmp     esi, 2Ah ; '*'
0x180078dec  jnz     short loc_180078DF4
0x180078dee  mov     esi, [rbp+24Ch]
0x180078df4  mov     r8, [rbp+88h]; char *
0x180078dfb  lea     rcx, [rsp+78h+arg_8]
0x180078e03  mov     [rsp+78h+var_48], rcx; int *
0x180078e08  mov     ecx, esi; int
0x180078e0a  mov     [rsp+78h+arg_8], r9d
0x180078e12  or      r9d, 0FFFFFFFFh; int
0x180078e16  mov     [rsp+78h+var_50], eax; int
0x180078e1a  mov     [rsp+78h+var_58], rdi; LPWSTR
0x180078e1f  call    ?MBTWC@CW32System@@SAHHKPEBDHPEAGHPEAH@Z; CW32System::MBTWC(int,ulong,char const *,int,ushort *,int,int *)
0x180078e24  xor     r11d, r11d
0x180078e27  movsxd  r10, eax
0x180078e2a  test    eax, eax
0x180078e2c  jle     short loc_180078E43
0x180078e2e  cmp     [rsp+78h+arg_8], r11d
0x180078e36  jz      short loc_180078E43
0x180078e38  test    r12d, r12d
0x180078e3b  jnz     short loc_180078E43
0x180078e3d  mov     byte ptr [rbx+4Ah], 1
0x180078e41  jmp     short loc_180078E79
0x180078e43  cmp     byte ptr [rbx+2], 1
0x180078e47  jnz     short loc_180078E74
0x180078e49  lea     eax, [rsi-3A4h]
0x180078e4f  cmp     eax, 12h
0x180078e52  ja      short loc_180078E74
0x180078e54  mov     rcx, [rbp+88h]
0x180078e5b  mov     edx, esi; unsigned int
0x180078e5d  mov     cl, [rcx]; unsigned __int8
0x180078e5f  call    ?GetTrailBytesCount@CW32System@@SAHEI@Z; CW32System::GetTrailBytesCount(uchar,uint)
0x180078e64  test    eax, eax
0x180078e66  jz      short loc_180078E74
0x180078e68  xor     edx, edx; int *
0x180078e6a  mov     ecx, esi; int
0x180078e6c  call    ?GetCharSet@CW32System@@SAEHPEAH@Z; CW32System::GetCharSet(int,int *)
0x180078e71  mov     [rbx+2], al
0x180078e74  test    r10d, r10d
0x180078e77  jle     short loc_180078E7E
0x180078e79  mov     [rdi+r10*2], r11w
0x180078e7e  xor     edx, edx; int
0x180078e80  mov     rcx, rbp; this
0x180078e83  call    ?Elem@CArrayBase@@QEBAPEAXJ@Z; CArrayBase::Elem(long)
0x180078e88  cmp     rbx, rax
0x180078e8b  jnz     short loc_180078E9F
0x180078e8d  movsx   edx, word ptr [rbp+1DCh]; int
0x180078e94  call    ?SelectCurrentFont@CRTFRead@@AEAAPEAU_textfont@@H@Z; CRTFRead::SelectCurrentFont(int)
0x180078e99  mov     rbx, rax
0x180078e9c  xor     r11d, r11d
0x180078e9f  mov     r8b, [rbx+2]; unsigned __int8
0x180078ea3  mov     [rsp+78h+var_38], r11
0x180078ea8  test    r8b, r8b
0x180078eab  jz      short loc_180078EDC
0x180078ead  test    byte ptr [r14+4], 4
0x180078eb2  jz      short loc_180078EDC
0x180078eb4  lea     r9, [rsp+78h+var_38]; unsigned __int16 **
0x180078eb9  lea     rdx, [rbx+6]; unsigned __int16 *
0x180078ebd  call    ?FindTaggedFont@CRTFConverter@@IEAAHPEBGEPEAPEAG@Z; CRTFConverter::FindTaggedFont(ushort const *,uchar,ushort * *)
0x180078ec2  xor     r9d, r9d
0x180078ec5  test    eax, eax
0x180078ec7  jnz     loc_180078FCE
0x180078ecd  and     dword ptr [r14+4], 0FFFFFFFBh
0x180078ed2  mov     [rbx+6], r9w
0x180078ed7  jmp     loc_180078FCE
0x180078edc  mov     rdx, cs:?_rgtfi@CRTFConverter@@1PEAU_tfi@@EA; _tfi * CRTFConverter::_rgtfi
0x180078ee3  test    rdx, rdx
0x180078ee6  jz      loc_180078F71
0x180078eec  mov     edi, r11d
0x180078eef  cmp     edi, cs:?_ctfi@CRTFConverter@@1HA; int CRTFConverter::_ctfi
0x180078ef5  jge     short loc_180078F71
0x180078ef7  mov     r8b, [rbx+2]
0x180078efb  cmp     r8b, 1
0x180078eff  jbe     short loc_180078F0F
0x180078f01  movsxd  rax, edi
0x180078f04  lea     rcx, [rax+rax*2]
0x180078f08  cmp     [rdx+rcx*8+10h], r8b
0x180078f0d  jnz     short loc_180078F32
0x180078f0f  movsxd  rax, edi
0x180078f12  lea     rcx, [rbx+6]; unsigned __int16 *
0x180078f16  lea     rsi, [rax+rax*2]
0x180078f1a  mov     rdx, [rdx+rsi*8+8]; unsigned __int16 *
0x180078f1f  call    ?lstrcmpi@CW32System@@SAHPEBG0@Z; CW32System::lstrcmpi(ushort const *,ushort const *)
0x180078f24  xor     r11d, r11d
0x180078f27  test    eax, eax
0x180078f29  jz      short loc_180078F36
0x180078f2b  mov     rdx, cs:?_rgtfi@CRTFConverter@@1PEAU_tfi@@EA; _tfi * CRTFConverter::_rgtfi
0x180078f32  inc     edi
0x180078f34  jmp     short loc_180078EEF
0x180078f36  mov     r8, cs:?_rgtfi@CRTFConverter@@1PEAU_tfi@@EA; _tfi * CRTFConverter::_rgtfi
0x180078f3d  lea     rcx, [rbx+6]; Destination
0x180078f41  mov     edx, 20h ; ' '; SizeInWords
0x180078f46  mov     al, [r8+rsi*8+10h]
0x180078f4b  mov     [rbx+2], al
0x180078f4e  mov     r8, [r8+rsi*8]; Source
0x180078f52  call    cs:__imp_wcscpy_s
0x180078f58  mov     cl, [rbx+2]; unsigned __int8
0x180078f5b  call    ?GetCodePage@CW32System@@SAHE@Z; CW32System::GetCodePage(uchar)
0x180078f60  movsx   edx, ax; int
0x180078f63  mov     rcx, r14; this
0x180078f66  mov     [rbx+48h], ax
0x180078f6a  call    ?SetCodePage@STATE@@QEAAXJ@Z; STATE::SetCodePage(long)
0x180078f6f  jmp     short loc_180078FCE
0x180078f71  test    r13d, r13d
0x180078f74  jz      short loc_180078FCE
0x180078f76  cmp     [rsp+78h+arg_8], r11d
0x180078f7e  jnz     short loc_180078FCE
0x180078f80  mov     ecx, r11d
0x180078f83  cmp     [rbx+6], r11w
0x180078f88  jz      short loc_180078FA2
0x180078f8a  movsxd  rax, ecx
0x180078f8d  cmp     word ptr [rbx+rax*2+6], 28h ; '('
0x180078f93  jz      short loc_180078FA2
0x180078f95  inc     ecx
0x180078f97  movsxd  rax, ecx
0x180078f9a  cmp     [rbx+rax*2+6], r11w
0x180078fa0  jnz     short loc_180078F8A
0x180078fa2  movsxd  rax, ecx
0x180078fa5  cmp     [rbx+rax*2+6], r11w
0x180078fab  jz      short loc_180078FCE
0x180078fad  test    ecx, ecx
0x180078faf  jle     short loc_180078FCE
0x180078fb1  mov     edx, 20h ; ' '
0x180078fb6  mov     eax, ecx
0x180078fb8  cmp     [rbx+rax*2+4], dx
0x180078fbd  jnz     short loc_180078FC5
0x180078fbf  dec     ecx
0x180078fc1  test    ecx, ecx
0x180078fc3  jg      short loc_180078FB6
0x180078fc5  movsxd  rcx, ecx
0x180078fc8  mov     [rbx+rcx*2+6], r11w
0x180078fce  lea     r11, [rsp+78h+var_28]
0x180078fd3  mov     rbx, [r11+30h]
0x180078fd7  mov     rbp, [r11+40h]
0x180078fdb  mov     rsp, r11
0x180078fde  pop     r14
0x180078fe0  pop     r13
0x180078fe2  pop     r12
0x180078fe4  pop     rdi
0x180078fe5  pop     rsi
0x180078fe6  retn
```
