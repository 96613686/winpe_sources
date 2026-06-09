# CCharFormat::Apply(CCharFormat const *,ulong,ulong)

- ea: `0x180006a70`
- end: `0x180006eee`
- name: `?Apply@CCharFormat@@QEAAJPEBV1@KK@Z`
- size: `1150`
- prototype: `__int64 __fastcall(CCharFormat *__hidden this, const struct CCharFormat *, unsigned int, unsigned int)`
- caller_count: `4`
- callee_count: `11`
- tags: ``

## callers

- `0x180005510`
- `0x180027794`
- `0x18002b0dc`
- `0x18002ca08`

## callees

- `0x180005070`
- `0x180006a70`
- `0x18001aa0c`
- `0x18001e2e0`
- `0x18002c900`
- `0x18003e56c`
- `0x18003ed60`
- `0x180052568`
- `0x1800904d0`
- `0x180090610`
- `0x1800906a4`

## import_xrefs

- `KERNEL32!GetThreadLocale` at `0x180006dc4`
- `KERNEL32!GetThreadLocale` at `0x180006dc4`

## pseudocode

```c
__int64 __fastcall CCharFormat::Apply(CCharFormat *this, const struct CCharFormat *a2, int a3, int a4)
{
  __int16 v5; // bp
  unsigned int v8; // r10d
  char v10; // r14
  int v11; // r9d
  int v12; // r8d
  int v13; // ecx
  __int16 v14; // ax
  int v15; // eax
  unsigned __int8 v16; // dl
  unsigned __int8 v17; // r8
  int v18; // ecx
  const unsigned __int16 *FontName; // rax
  unsigned __int16 ThreadLocale; // ax
  int v21; // r14d
  unsigned __int8 CharSet; // al
  int v23; // edx
  unsigned __int16 v24; // ax
  char v25; // cl
  unsigned __int8 v26; // al
  __int16 v27; // [rsp+60h] [rbp+8h] BYREF
  unsigned int v28; // [rsp+70h] [rbp+18h] BYREF
  unsigned __int8 v29; // [rsp+78h] [rbp+20h] BYREF

  v5 = a4;
  *(_DWORD *)this &= ~(a3 & 0x44037FFF);
  v8 = ~(a4 & 0xBBFC0000) & (*(_DWORD *)this | *(_DWORD *)a2 & a3 & 0x44037FFF);
  *(_DWORD *)this = v8;
  *(_DWORD *)this = v8 | *(_DWORD *)a2 & a4 & 0xBBFC0000;
  if ( (a3 & 1) != 0 )
  {
    v14 = 700;
    if ( (*(_BYTE *)a2 & 1) == 0 )
      v14 = 400;
    *((_WORD *)this + 8) = v14;
  }
  if ( (a3 & 0x40000000) != 0 )
    *((_DWORD *)this + 3) = *((_DWORD *)a2 + 3);
  if ( (a3 & 0xBFFFFFC0) != 0 )
  {
    v10 = 0;
    if ( a3 < 0 )
    {
      v15 = *((__int16 *)a2 + 4);
      if ( (a4 & 0x4000) != 0 )
        LOWORD(v15) = GetUsableFontHeight(*((__int16 *)this + 4), v15);
      *((_WORD *)this + 4) = v15;
    }
    if ( (a3 & 0x10000000) != 0 )
      *((_WORD *)this + 5) = *((_WORD *)a2 + 5);
    if ( (a3 & 0x8000000) == 0 || (int)CW32System::ScriptIndexFromCharSet(*((_BYTE *)a2 + 4)) < 0 )
      goto LABEL_25;
    if ( (v5 & 0x1100) == 0 )
    {
      v12 = *((unsigned __int8 *)this + 4);
      if ( (v5 & 0x2000) != 0 )
      {
        if ( (_BYTE)v11 )
        {
          if ( v12 == 128
            || v12 == 129
            || v12 == 130
            || v12 == 134
            || v12 == 136
            || (_BYTE)v12 == 2
            || (_BYTE)v12 == 0xFF
            || (*(_DWORD *)this & 0x40000) != 0 )
          {
            goto LABEL_25;
          }
        }
        else if ( (unsigned int)(v12 - 177) > 1 )
        {
LABEL_25:
          if ( (v5 & 0x500) == 0x500 )
          {
            v16 = *((_BYTE *)a2 + 4);
            v17 = *((_BYTE *)this + 4);
            if ( v17 != v16 && a3 < 0 )
              *((_WORD *)this + 4) = CW32System::GetPreferredFontHeight(
                                       (v5 & 0x200) != 0,
                                       v16,
                                       v17,
                                       *((_WORD *)this + 4));
          }
          if ( (a3 & 0x20000000) != 0 )
          {
            *((_BYTE *)this + 5) = *((_BYTE *)a2 + 5);
            v18 = *((__int16 *)a2 + 3);
            *((_WORD *)this + 3) = *((_WORD *)a2 + 3);
            FontName = GetFontName(v18);
            if ( FontName )
              LOWORD(FontName) = *FontName;
            if ( v10 || (_WORD)FontName )
            {
              if ( (GetCharFlags((unsigned __int16)FontName, 0) & 0x1E000000) != 0
                && *((unsigned __int8 *)this + 4) != 128
                && *((unsigned __int8 *)this + 4) != 129
                && *((unsigned __int8 *)this + 4) != 130
                && *((unsigned __int8 *)this + 4) != 134
                && *((unsigned __int8 *)this + 4) != 136 )
              {
                v13 = *((__int16 *)this + 3);
                v28 = 0;
                if ( (unsigned int)GetFontSignatureFromFace(v13, &v28) )
                {
                  if ( (v28 & 0x1E0000) != 0 )
                    *((_BYTE *)this + 4) = CW32System::GetFirstAvailCharSet(v28 & 0x1E0000);
                }
              }
            }
            else
            {
              ThreadLocale = GetThreadLocale();
              v21 = CW32System::ConvertLanguageIDtoCodePage(ThreadLocale);
              v27 = 0;
              LOBYTE(v28) = 0;
              v29 = 0;
              if ( CW32System::GetPreferredFontInfo(v21, 0, 0, &v27, (unsigned __int8 *)&v28, &v29) )
              {
                CharSet = CW32System::GetCharSet(v21, 0);
                v23 = (unsigned __int8)v28;
                *((_BYTE *)this + 4) = CharSet;
                *((_WORD *)this + 3) = v27;
                if ( a3 >= 0 || *((__int16 *)this + 4) < 20 * v23 )
                  *((_WORD *)this + 4) = 20 * v23;
                *((_BYTE *)this + 5) = v29;
              }
            }
          }
          if ( (a3 & 0x7FFFFC0) != 0 && (v5 & 0x8000) == 0 )
          {
            if ( (a3 & 0x400001) == 0x400000 )
            {
              v24 = *((_WORD *)a2 + 8);
              *(_DWORD *)this |= 1u;
              *((_WORD *)this + 8) = v24;
              if ( v24 < 0x227u )
                *(_DWORD *)this &= ~1u;
            }
            if ( (a3 & 0x4000000) != 0 )
              *((_DWORD *)this + 5) = *((_DWORD *)a2 + 5);
            if ( (a3 & 0x2000000) != 0 )
              *((_DWORD *)this + 6) = *((_DWORD *)a2 + 6);
            if ( (a3 & 0x200000) != 0 )
              *((_WORD *)this + 9) = *((_WORD *)a2 + 9);
            if ( (a3 & 0x100000) != 0 )
              *((_WORD *)this + 15) = *((_WORD *)a2 + 15);
            if ( (a3 & 0x80000) != 0 )
              *((_WORD *)this + 14) = *((_WORD *)a2 + 14);
            if ( (a3 & 0x800000) != 0 )
            {
              v25 = *((_BYTE *)a2 + 32);
              *((_BYTE *)this + 32) = v25;
              if ( (a3 & 4) == 0 )
              {
                *(_DWORD *)this &= ~4u;
                if ( v25 )
                  *(_DWORD *)this |= 4u;
              }
            }
            if ( (a3 & 0x40000) != 0 )
            {
              v26 = *((_BYTE *)a2 + 33);
              if ( v26 <= 0x12u )
                *((_BYTE *)this + 33) = v26;
            }
            if ( (a3 & 0x8000) != 0 )
              *((_BYTE *)this + 34) = *((_BYTE *)a2 + 34);
          }
          goto LABEL_5;
        }
      }
      else if ( (unsigned int)(v12 - 177) <= 1 != (unsigned int)(v11 - 177) <= 1
             && (_BYTE)v11 != 2
             && (_BYTE)v11 != 0xFF )
      {
        goto LABEL_25;
      }
    }
    v10 = 1;
    *((_BYTE *)this + 4) = v11;
    goto LABEL_25;
  }
LABEL_5:
  if ( (v5 & 0x2000) != 0 )
    *((_WORD *)this + 18) = *((_WORD *)a2 + 18);
  return 0;
}

```

## disassembly

```asm
0x180006a70  push    rbx
0x180006a72  push    rsi
0x180006a73  sub     rsp, 48h
0x180006a77  mov     rbx, rcx
0x180006a7a  mov     [rsp+58h+arg_8], rbp
0x180006a7f  mov     r10d, r8d
0x180006a82  mov     [rsp+58h+var_18], rdi
0x180006a87  and     r10d, 44037FFFh
0x180006a8e  mov     ebp, r9d
0x180006a91  mov     eax, r10d
0x180006a94  mov     edi, r8d
0x180006a97  not     eax
0x180006a99  mov     rsi, rdx
0x180006a9c  and     [rcx], eax
0x180006a9e  mov     ecx, r9d
0x180006aa1  and     r10d, [rdx]
0x180006aa4  and     ecx, 0BBFC0000h
0x180006aaa  or      r10d, [rbx]
0x180006aad  mov     eax, ecx
0x180006aaf  not     eax
0x180006ab1  and     r10d, eax
0x180006ab4  mov     [rbx], r10d
0x180006ab7  and     ecx, [rdx]
0x180006ab9  or      ecx, r10d
0x180006abc  mov     [rbx], ecx
0x180006abe  test    r8b, 1
0x180006ac2  jnz     loc_180006CD1
0x180006ac8  bt      edi, 1Eh
0x180006acc  jnb     short loc_180006AD4
0x180006ace  mov     eax, [rdx+0Ch]
0x180006ad1  mov     [rbx+0Ch], eax
0x180006ad4  test    edi, 0BFFFFFC0h
0x180006ada  jnz     short loc_180006AFE
0x180006adc  mov     rdi, [rsp+58h+var_18]
0x180006ae1  bt      ebp, 0Dh
0x180006ae5  mov     rbp, [rsp+58h+arg_8]
0x180006aea  jnb     short loc_180006AF4
0x180006aec  movzx   eax, word ptr [rsi+24h]
0x180006af0  mov     [rbx+24h], ax
0x180006af4  xor     eax, eax
0x180006af6  add     rsp, 48h
0x180006afa  pop     rsi
0x180006afb  pop     rbx
0x180006afc  retn
0x180006afe  mov     [rsp+58h+var_20], r14
0x180006b03  xor     r14b, r14b
0x180006b06  test    edi, edi
0x180006b08  js      loc_180006CEB
0x180006b0e  bt      edi, 1Ch
0x180006b12  jb      loc_180006D13
0x180006b18  bt      edi, 1Bh
0x180006b1c  jnb     short loc_180006B8A
0x180006b1e  movzx   r9d, byte ptr [rsi+4]
0x180006b23  movzx   ecx, r9b; unsigned __int8
0x180006b27  call    ?ScriptIndexFromCharSet@CW32System@@SAJE@Z; CW32System::ScriptIndexFromCharSet(uchar)
0x180006b2c  test    eax, eax
0x180006b2e  js      short loc_180006B8A
0x180006b30  test    ebp, 1100h
0x180006b36  jnz     short loc_180006B83
0x180006b38  movzx   r8d, byte ptr [rbx+4]
0x180006b3d  bt      ebp, 0Dh
0x180006b41  jnb     loc_180006D20
0x180006b47  test    r9b, r9b
0x180006b4a  jz      loc_180006C33
0x180006b50  mov     ecx, r8d
0x180006b53  sub     ecx, 80h
0x180006b59  jz      short loc_180006B8A
0x180006b5b  sub     ecx, 1
0x180006b5e  jz      short loc_180006B8A
0x180006b60  sub     ecx, 1
0x180006b63  jz      short loc_180006B8A
0x180006b65  sub     ecx, 4
0x180006b68  jz      short loc_180006B8A
0x180006b6a  cmp     ecx, 2
0x180006b6d  jz      short loc_180006B8A
0x180006b6f  cmp     r8b, 2
0x180006b73  jz      short loc_180006B8A
0x180006b75  cmp     r8b, 0FFh
0x180006b79  jz      short loc_180006B8A
0x180006b7b  test    dword ptr [rbx], 40000h
0x180006b81  jnz     short loc_180006B8A
0x180006b83  mov     r14b, 1
0x180006b86  mov     [rbx+4], r9b
0x180006b8a  mov     eax, ebp
0x180006b8c  and     eax, 500h
0x180006b91  cmp     eax, 500h
0x180006b96  jz      loc_180006D5F
0x180006b9c  bt      edi, 1Dh
0x180006ba0  jb      loc_180006D94
0x180006ba6  mov     r14, [rsp+58h+var_20]
0x180006bab  test    edi, 7FFFFC0h
0x180006bb1  setnz   cl
0x180006bb4  bt      ebp, 0Fh
0x180006bb8  setnb   al
0x180006bbb  test    al, cl
0x180006bbd  jz      loc_180006ADC
0x180006bc3  mov     eax, edi
0x180006bc5  and     eax, 400001h
0x180006bca  cmp     eax, 400000h
0x180006bcf  jz      loc_180006E63
0x180006bd5  bt      edi, 1Ah
0x180006bd9  jb      loc_180006E84
0x180006bdf  bt      edi, 19h
0x180006be3  jnb     short loc_180006BEB
0x180006be5  mov     eax, [rsi+18h]
0x180006be8  mov     [rbx+18h], eax
0x180006beb  bt      edi, 15h
0x180006bef  jb      loc_180006E8F
0x180006bf5  bt      edi, 14h
0x180006bf9  jb      loc_180006E9C
0x180006bff  bt      edi, 13h
0x180006c03  jb      loc_180006EA9
0x180006c09  bt      edi, 17h
0x180006c0d  jb      loc_180006EB6
0x180006c13  bt      edi, 12h
0x180006c17  jb      loc_180006EDA
0x180006c1d  bt      edi, 0Fh
0x180006c21  jnb     loc_180006ADC
0x180006c27  movzx   eax, byte ptr [rsi+22h]
0x180006c2b  mov     [rbx+22h], al
0x180006c2e  jmp     loc_180006ADC
0x180006c33  lea     eax, [r8-0B1h]
0x180006c3a  cmp     eax, 1
0x180006c3d  ja      loc_180006B8A
0x180006c43  jmp     loc_180006B83
0x180006c48  movzx   ecx, byte ptr [rbx+4]
0x180006c4c  sub     ecx, 80h
0x180006c52  jz      loc_180006BA6
0x180006c58  sub     ecx, 1
0x180006c5b  jz      loc_180006BA6
0x180006c61  sub     ecx, 1
0x180006c64  jz      loc_180006BA6
0x180006c6a  sub     ecx, 4
0x180006c6d  jz      loc_180006BA6
0x180006c73  cmp     ecx, 2
0x180006c76  jz      loc_180006BA6
0x180006c7c  movsx   ecx, word ptr [rbx+6]; int
0x180006c80  lea     rdx, [rsp+58h+arg_10]; unsigned int *
0x180006c85  mov     [rsp+58h+arg_10], 0
0x180006c8d  call    ?GetFontSignatureFromFace@@YAKHPEAK@Z; GetFontSignatureFromFace(int,ulong *)
0x180006c92  test    eax, eax
0x180006c94  jz      loc_180006BA6
0x180006c9a  mov     ecx, [rsp+58h+arg_10]
0x180006c9e  and     ecx, 1E0000h; unsigned int
0x180006ca4  jz      loc_180006BA6
0x180006caa  call    ?GetFirstAvailCharSet@CW32System@@SAEK@Z; CW32System::GetFirstAvailCharSet(ulong)
0x180006caf  mov     [rbx+4], al
0x180006cb2  jmp     loc_180006BA6
0x180006cb7  movzx   ecx, ax; unsigned int
0x180006cba  xor     edx, edx; unsigned __int8
0x180006cbc  call    ?GetCharFlags@@YAKKE@Z; GetCharFlags(ulong,uchar)
0x180006cc1  test    eax, 1E000000h
0x180006cc6  jz      loc_180006BA6
0x180006ccc  jmp     loc_180006C48
0x180006cd1  test    byte ptr [rdx], 1
0x180006cd4  mov     eax, 2BCh
0x180006cd9  mov     ecx, 190h
0x180006cde  cmovz   ax, cx
0x180006ce2  mov     [rbx+10h], ax
0x180006ce6  jmp     loc_180006AC8
0x180006ceb  movsx   eax, word ptr [rdx+8]
0x180006cef  mov     [rsp+58h+var_28], r15
0x180006cf4  bt      ebp, 0Eh
0x180006cf8  jnb     short loc_180006D05
0x180006cfa  movsx   ecx, word ptr [rbx+8]; int
0x180006cfe  mov     edx, eax; int
0x180006d00  call    ?GetUsableFontHeight@@YAJJJ@Z; GetUsableFontHeight(long,long)
0x180006d05  mov     r15, [rsp+58h+var_28]
0x180006d0a  mov     [rbx+8], ax
0x180006d0e  jmp     loc_180006B0E
0x180006d13  movzx   eax, word ptr [rsi+0Ah]
0x180006d17  mov     [rbx+0Ah], ax
0x180006d1b  jmp     loc_180006B18
0x180006d20  xor     edx, edx
0x180006d22  lea     eax, [r9-0B1h]
0x180006d29  cmp     eax, 1
0x180006d2c  lea     eax, [r8-0B1h]
0x180006d33  setbe   dl
0x180006d36  xor     ecx, ecx
0x180006d38  cmp     eax, 1
0x180006d3b  setbe   cl
0x180006d3e  cmp     ecx, edx
0x180006d40  jz      loc_180006B83
0x180006d46  cmp     r9b, 2
0x180006d4a  jz      loc_180006B83
0x180006d50  cmp     r9b, 0FFh
0x180006d54  jnz     loc_180006B8A
0x180006d5a  jmp     loc_180006B83
0x180006d5f  movzx   edx, byte ptr [rsi+4]; unsigned __int8
0x180006d63  movzx   r8d, byte ptr [rbx+4]; unsigned __int8
0x180006d68  cmp     r8b, dl
0x180006d6b  jz      loc_180006B9C
0x180006d71  test    edi, edi
0x180006d73  jns     loc_180006B9C
0x180006d79  movzx   r9d, word ptr [rbx+8]; __int16
0x180006d7e  mov     ecx, ebp
0x180006d80  shr     ecx, 9
0x180006d83  and     cl, 1; bool
0x180006d86  call    ?GetPreferredFontHeight@CW32System@@SAF_NEEF@Z; CW32System::GetPreferredFontHeight(bool,uchar,uchar,short)
0x180006d8b  mov     [rbx+8], ax
0x180006d8f  jmp     loc_180006B9C
0x180006d94  movzx   eax, byte ptr [rsi+5]
0x180006d98  mov     [rbx+5], al
0x180006d9b  movsx   eax, word ptr [rsi+6]
0x180006d9f  mov     ecx, eax; int
0x180006da1  mov     [rbx+6], ax
0x180006da5  call    ?GetFontName@@YAPEBGJ@Z; GetFontName(long)
0x180006daa  test    rax, rax
0x180006dad  jz      short loc_180006DB2
0x180006daf  movzx   eax, word ptr [rax]
0x180006db2  test    r14b, r14b
0x180006db5  jnz     loc_180006CB7
0x180006dbb  test    ax, ax
0x180006dbe  jnz     loc_180006CB7
0x180006dc4  call    cs:__imp_GetThreadLocale
0x180006dcb  nop     dword ptr [rax+rax+00h]
0x180006dd0  mov     ecx, eax; unsigned __int16
0x180006dd2  call    ?ConvertLanguageIDtoCodePage@CW32System@@SAIG@Z; CW32System::ConvertLanguageIDtoCodePage(ushort)
0x180006dd7  xor     ecx, ecx
0x180006dd9  lea     r9, [rsp+58h+arg_0]; __int16 *
0x180006dde  mov     r14d, eax
0x180006de1  mov     [rsp+58h+arg_0], cx
0x180006de6  lea     rax, [rsp+58h+arg_18]
0x180006deb  mov     byte ptr [rsp+58h+arg_10], cl
0x180006def  mov     [rsp+58h+var_30], rax; unsigned __int8 *
0x180006df4  xor     r8d, r8d; bool
0x180006df7  lea     rax, [rsp+58h+arg_10]
0x180006dfc  mov     [rsp+58h+arg_18], cl
0x180006e00  xor     edx, edx; bool
0x180006e02  mov     [rsp+58h+var_38], rax; unsigned __int8 *
0x180006e07  mov     ecx, r14d; int
0x180006e0a  call    ?GetPreferredFontInfo@CW32System@@SA_NH_N0AEAFAEAE2@Z; CW32System::GetPreferredFontInfo(int,bool,bool,short &,uchar &,uchar &)
0x180006e0f  test    al, al
0x180006e11  jz      loc_180006BA6
0x180006e17  xor     edx, edx; int *
0x180006e19  mov     ecx, r14d; int
0x180006e1c  call    ?GetCharSet@CW32System@@SAEHPEAH@Z; CW32System::GetCharSet(int,int *)
0x180006e21  movzx   edx, byte ptr [rsp+58h+arg_10]
0x180006e26  mov     [rbx+4], al
0x180006e29  movzx   eax, [rsp+58h+arg_0]
0x180006e2e  mov     [rbx+6], ax
0x180006e32  test    edi, edi
0x180006e34  jns     short loc_180006E44
0x180006e36  movsx   eax, word ptr [rbx+8]
0x180006e3a  lea     ecx, [rdx+rdx*4]
0x180006e3d  shl     ecx, 2
0x180006e40  cmp     eax, ecx
0x180006e42  jge     short loc_180006E56
0x180006e44  movzx   eax, dx
0x180006e47  shl     ax, 2
0x180006e4b  lea     ecx, [rax+rdx]
0x180006e4e  shl     cx, 2
0x180006e52  mov     [rbx+8], cx
0x180006e56  movzx   eax, [rsp+58h+arg_18]
0x180006e5b  mov     [rbx+5], al
0x180006e5e  jmp     loc_180006BA6
0x180006e63  movzx   eax, word ptr [rsi+10h]
0x180006e67  mov     edx, 227h
0x180006e6c  or      dword ptr [rbx], 1
0x180006e6f  mov     [rbx+10h], ax
0x180006e73  cmp     ax, dx
0x180006e76  jnb     loc_180006BD5
0x180006e7c  and     dword ptr [rbx], 0FFFFFFFEh
0x180006e7f  jmp     loc_180006BD5
0x180006e84  mov     eax, [rsi+14h]
0x180006e87  mov     [rbx+14h], eax
0x180006e8a  jmp     loc_180006BDF
0x180006e8f  movzx   eax, word ptr [rsi+12h]
0x180006e93  mov     [rbx+12h], ax
0x180006e97  jmp     loc_180006BF5
0x180006e9c  movzx   eax, word ptr [rsi+1Eh]
0x180006ea0  mov     [rbx+1Eh], ax
0x180006ea4  jmp     loc_180006BFF
0x180006ea9  movzx   eax, word ptr [rsi+1Ch]
0x180006ead  mov     [rbx+1Ch], ax
0x180006eb1  jmp     loc_180006C09
0x180006eb6  movzx   ecx, byte ptr [rsi+20h]
0x180006eba  mov     [rbx+20h], cl
0x180006ebd  test    dil, 4
0x180006ec1  jnz     loc_180006C13
0x180006ec7  and     dword ptr [rbx], 0FFFFFFFBh
0x180006eca  test    cl, cl
0x180006ecc  jz      loc_180006C13
0x180006ed2  or      dword ptr [rbx], 4
0x180006ed5  jmp     loc_180006C13
0x180006eda  movzx   eax, byte ptr [rsi+21h]
0x180006ede  cmp     al, 12h
0x180006ee0  ja      loc_180006C1D
0x180006ee6  mov     [rbx+21h], al
0x180006ee9  jmp     loc_180006C1D
```
