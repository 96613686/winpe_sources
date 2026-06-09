# QuicCryptoTlsReadExtensions

- ea: `0x140020e98`
- end: `0x140021152`
- name: `QuicCryptoTlsReadExtensions`
- size: `698`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned __int8 *, unsigned __int16, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140020d30`

## callees

- `0x14000db70`
- `0x140020e98`
- `0x14003ec10`
- `0x1400494ec`

## string_xrefs

- `0x140021107`: `Parse error. ReadTlsExt #1`
- `0x1400210f5`: `Parse error. ReadTlsExt #2`
- `0x14002107b`: `Duplicate SNI extension present`
- `0x1400210d1`: `Duplicate ALPN extension present`
- `0x140020ff8`: `Duplicate QUIC TP extension present`
- `0x1400210e3`: `Duplicate QUIC (draft) TP extension present`
- `0x140021119`: `No QUIC TP extension present`
- `0x1400210bf`: `Parse error. ReadTlsAlpn #1`
- `0x1400210ad`: `Parse error. ReadTlsAlpn #2`
- `0x140021094`: `Parse error. ReadTlsAlpn #3`

## pseudocode

```c
__int64 __fastcall QuicCryptoTlsReadExtensions(
        unsigned __int64 a1,
        unsigned __int8 *a2,
        unsigned __int16 a3,
        __int64 a4)
{
  unsigned __int16 v4; // r14
  __int64 v7; // rbx
  char v8; // r13
  char v9; // r12
  char v10; // bp
  __int16 v11; // si
  __int16 v12; // dx
  __int16 v13; // ax
  unsigned __int8 *v14; // rdi
  unsigned __int16 v15; // si
  unsigned __int16 v16; // r14
  __int64 result; // rax
  unsigned __int8 *v18; // rdx
  __int64 v19; // rax
  const char *v20; // r9

  v4 = a3;
  v7 = a1;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  if ( a3 )
  {
    while ( 1 )
    {
      if ( v4 < 4u )
      {
        if ( (byte_14005C48B & 4) == 0 )
          return 3221225485LL;
        v20 = "Parse error. ReadTlsExt #1";
        goto LABEL_47;
      }
      a1 = 256;
      v11 = a2[2] << 8;
      v12 = a2[1] + (*a2 << 8);
      v13 = a2[3];
      v14 = a2 + 4;
      v15 = v13 + v11;
      v16 = v4 - 4;
      if ( v16 < v15 )
      {
        if ( (byte_14005C48B & 4) == 0 )
          return 3221225485LL;
        v20 = "Parse error. ReadTlsExt #2";
        goto LABEL_47;
      }
      if ( v12 )
      {
        if ( v12 == 16 )
        {
          if ( v9 )
          {
            if ( (byte_14005C48B & 4) == 0 )
              return 3221225485LL;
            v20 = "Duplicate ALPN extension present";
          }
          else if ( v15 < 4u )
          {
            if ( (byte_14005C48B & 4) == 0 )
              return 3221225485LL;
            v20 = "Parse error. ReadTlsAlpn #1";
          }
          else
          {
            a1 = v14[1] + 2LL + ((unsigned __int64)*v14 << 8);
            if ( v15 == a1 )
            {
              a1 = v15;
              v18 = v14 + 2;
              LOWORD(a1) = v15 - 2;
              *(_QWORD *)(a4 + 48) = v14 + 2;
              *(_WORD *)(a4 + 28) = v15 - 2;
              while ( 1 )
              {
                LOWORD(a1) = a1 - 1;
                if ( !(_WORD)a1 )
                  break;
                v19 = *v18;
                if ( (unsigned __int16)a1 < (unsigned __int16)v19 )
                  break;
                v18 += v19 + 1;
                LOWORD(a1) = a1 - v19;
                if ( !(_WORD)a1 )
                {
                  v9 = 1;
                  goto LABEL_26;
                }
              }
              if ( (byte_14005C48B & 4) != 0 )
              {
                v20 = "Parse error. ReadTlsAlpn #3";
                goto LABEL_47;
              }
              return 3221225485LL;
            }
            if ( (byte_14005C48B & 4) == 0 )
              return 3221225485LL;
            v20 = "Parse error. ReadTlsAlpn #2";
          }
LABEL_47:
          McTemplateU0ps_EtwWriteTransfer(a1, QuicConnError, v7, v20);
          return 3221225485LL;
        }
        if ( *(_DWORD *)(v7 + 3636) == 486539519 )
        {
          if ( v12 == -91 )
          {
            if ( v10 )
            {
              if ( (byte_14005C48B & 4) == 0 )
                return 3221225485LL;
              v20 = "Duplicate QUIC (draft) TP extension present";
              goto LABEL_47;
            }
            goto LABEL_24;
          }
        }
        else if ( v12 == 57 )
        {
          if ( v10 )
          {
            if ( (byte_14005C48B & 4) == 0 )
              return 3221225485LL;
            v20 = "Duplicate QUIC TP extension present";
            goto LABEL_47;
          }
LABEL_24:
          if ( !QuicCryptoTlsDecodeTransportParameters(v7, 0, (__int64)v14, v15, (char *)(v7 + 1624)) )
            return 3221225485LL;
          v10 = 1;
        }
      }
      else
      {
        if ( v8 )
        {
          if ( (byte_14005C48B & 4) == 0 )
            return 3221225485LL;
          v20 = "Duplicate SNI extension present";
          goto LABEL_47;
        }
        result = QuicCryptoTlsReadSniExtension(v7, v14, v15, a4);
        if ( (int)result < 0 )
          return result;
        v8 = 1;
      }
LABEL_26:
      a2 = &v14[v15];
      v4 = v16 - v15;
      if ( !v4 )
      {
        if ( !v10 )
          break;
        return 0;
      }
    }
  }
  if ( (byte_14005C48B & 4) != 0 )
  {
    v20 = "No QUIC TP extension present";
    goto LABEL_47;
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x140020e98  mov     [rsp+arg_0], rbx
0x140020e9d  mov     [rsp+arg_8], rbp
0x140020ea2  mov     [rsp+arg_10], rsi
0x140020ea7  push    rdi
0x140020ea8  push    r12
0x140020eaa  push    r13
0x140020eac  push    r14
0x140020eae  push    r15
0x140020eb0  sub     rsp, 30h
0x140020eb4  movzx   r14d, r8w
0x140020eb8  mov     r15, r9
0x140020ebb  xor     r9d, r9d
0x140020ebe  mov     rdi, rdx
0x140020ec1  mov     rbx, rcx
0x140020ec4  mov     r13b, r9b
0x140020ec7  mov     r12b, r9b
0x140020eca  mov     bpl, r9b
0x140020ecd  lea     r8d, [r9+4]
0x140020ed1  test    r14w, r14w
0x140020ed5  jz      loc_140021110
0x140020edb  mov     r10d, 100h
0x140020ee1  cmp     r14w, r8w
0x140020ee5  jb      loc_1400210FE
0x140020eeb  movzx   eax, byte ptr [rdi+1]
0x140020eef  movzx   edx, byte ptr [rdi]
0x140020ef2  movzx   esi, byte ptr [rdi+2]
0x140020ef6  movzx   ecx, r10w
0x140020efa  imul    edx, ecx
0x140020efd  movzx   ecx, r10w
0x140020f01  imul    esi, ecx
0x140020f04  add     dx, ax
0x140020f07  movzx   eax, byte ptr [rdi+3]
0x140020f0b  add     rdi, r8
0x140020f0e  add     si, ax
0x140020f11  mov     eax, 0FFFCh
0x140020f16  add     r14w, ax
0x140020f1a  cmp     r14w, si
0x140020f1e  jb      loc_1400210EC
0x140020f24  test    dx, dx
0x140020f27  jnz     short loc_140020F57
0x140020f29  test    r13b, r13b
0x140020f2c  jnz     loc_14002106E
0x140020f32  mov     r9, r15
0x140020f35  movzx   r8d, si
0x140020f39  mov     rdx, rdi
0x140020f3c  mov     rcx, rbx
0x140020f3f  call    QuicCryptoTlsReadSniExtension
0x140020f44  xor     r9d, r9d
0x140020f47  test    eax, eax
0x140020f49  js      loc_140021134
0x140020f4f  mov     r13b, 1
0x140020f52  jmp     loc_140021042
0x140020f57  cmp     dx, 10h
0x140020f5b  jnz     short loc_140020FD4
0x140020f5d  test    r12b, r12b
0x140020f60  jnz     loc_1400210C8
0x140020f66  cmp     si, r8w
0x140020f6a  jb      loc_1400210B6
0x140020f70  movzx   ecx, byte ptr [rdi]
0x140020f73  movzx   eax, byte ptr [rdi+1]
0x140020f77  add     rax, 2
0x140020f7b  shl     rcx, 8
0x140020f7f  add     rcx, rax
0x140020f82  movzx   eax, si
0x140020f85  cmp     rax, rcx
0x140020f88  jnz     loc_1400210A0
0x140020f8e  movzx   ecx, si
0x140020f91  lea     rdx, [rdi+2]
0x140020f95  sub     cx, 2
0x140020f99  mov     [r15+30h], rdx
0x140020f9d  mov     [r15+1Ch], cx
0x140020fa2  jz      short loc_140020FCF
0x140020fa4  mov     eax, 0FFFFh
0x140020fa9  add     cx, ax
0x140020fac  cmp     cx, 1
0x140020fb0  jb      loc_140021087
0x140020fb6  movzx   eax, byte ptr [rdx]
0x140020fb9  cmp     cx, ax
0x140020fbc  jb      loc_140021087
0x140020fc2  lea     rdx, [rdx+1]
0x140020fc6  lea     rdx, [rdx+rax]
0x140020fca  sub     cx, ax
0x140020fcd  jnz     short loc_140020FA4
0x140020fcf  mov     r12b, 1
0x140020fd2  jmp     short loc_14002104E
0x140020fd4  cmp     dword ptr [rbx+0E34h], 1D0000FFh
0x140020fde  jz      short loc_140021004
0x140020fe0  cmp     dx, 39h ; '9'
0x140020fe4  jnz     short loc_14002104E
0x140020fe6  test    bpl, bpl
0x140020fe9  jz      short loc_140021017
0x140020feb  test    cs:byte_14005C48B, r8b
0x140020ff2  jz      loc_14002112F
0x140020ff8  lea     r9, aDuplicateQuicT_0; "Duplicate QUIC TP extension present"
0x140020fff  jmp     loc_140021120
0x140021004  mov     eax, 0FFA5h
0x140021009  cmp     dx, ax
0x14002100c  jnz     short loc_14002104E
0x14002100e  test    bpl, bpl
0x140021011  jnz     loc_1400210DA
0x140021017  lea     rax, [rbx+658h]
0x14002101e  movzx   r9d, si; int
0x140021022  mov     r8, rdi; int
0x140021025  mov     [rsp+58h+var_38], rax; void *
0x14002102a  xor     edx, edx; int
0x14002102c  mov     rcx, rbx; int
0x14002102f  call    QuicCryptoTlsDecodeTransportParameters
0x140021034  xor     r9d, r9d
0x140021037  test    al, al
0x140021039  jz      loc_14002112F
0x14002103f  mov     bpl, 1
0x140021042  mov     r8d, 4
0x140021048  mov     r10d, 100h
0x14002104e  movzx   eax, si
0x140021051  add     rdi, rax
0x140021054  sub     r14w, si
0x140021058  jnz     loc_140020EE1
0x14002105e  test    bpl, bpl
0x140021061  jz      loc_140021110
0x140021067  xor     eax, eax
0x140021069  jmp     loc_140021134
0x14002106e  test    cs:byte_14005C48B, r8b
0x140021075  jz      loc_14002112F
0x14002107b  lea     r9, aDuplicateSniEx; "Duplicate SNI extension present"
0x140021082  jmp     loc_140021120
0x140021087  test    cs:byte_14005C48B, r8b
0x14002108e  jz      loc_14002112F
0x140021094  lea     r9, aParseErrorRead_0; "Parse error. ReadTlsAlpn #3"
0x14002109b  jmp     loc_140021120
0x1400210a0  test    cs:byte_14005C48B, r8b
0x1400210a7  jz      loc_14002112F
0x1400210ad  lea     r9, aParseErrorRead_3; "Parse error. ReadTlsAlpn #2"
0x1400210b4  jmp     short loc_140021120
0x1400210b6  test    cs:byte_14005C48B, r8b
0x1400210bd  jz      short loc_14002112F
0x1400210bf  lea     r9, aParseErrorRead_7; "Parse error. ReadTlsAlpn #1"
0x1400210c6  jmp     short loc_140021120
0x1400210c8  test    cs:byte_14005C48B, r8b
0x1400210cf  jz      short loc_14002112F
0x1400210d1  lea     r9, aDuplicateAlpnE; "Duplicate ALPN extension present"
0x1400210d8  jmp     short loc_140021120
0x1400210da  test    cs:byte_14005C48B, r8b
0x1400210e1  jz      short loc_14002112F
0x1400210e3  lea     r9, aDuplicateQuicD; "Duplicate QUIC (draft) TP extension pre"...
0x1400210ea  jmp     short loc_140021120
0x1400210ec  test    cs:byte_14005C48B, r8b
0x1400210f3  jz      short loc_14002112F
0x1400210f5  lea     r9, aParseErrorRead_1; "Parse error. ReadTlsExt #2"
0x1400210fc  jmp     short loc_140021120
0x1400210fe  test    cs:byte_14005C48B, r8b
0x140021105  jz      short loc_14002112F
0x140021107  lea     r9, aParseErrorRead_14; "Parse error. ReadTlsExt #1"
0x14002110e  jmp     short loc_140021120
0x140021110  test    cs:byte_14005C48B, r8b
0x140021117  jz      short loc_14002112F
0x140021119  lea     r9, aNoQuicTpExtens; "No QUIC TP extension present"
0x140021120  mov     r8, rbx
0x140021123  lea     rdx, QuicConnError
0x14002112a  call    McTemplateU0ps_EtwWriteTransfer
0x14002112f  mov     eax, 0C000000Dh
0x140021134  mov     rbx, [rsp+58h+arg_0]
0x140021139  mov     rbp, [rsp+58h+arg_8]
0x14002113e  mov     rsi, [rsp+58h+arg_10]
0x140021143  add     rsp, 30h
0x140021147  pop     r15
0x140021149  pop     r14
0x14002114b  pop     r13
0x14002114d  pop     r12
0x14002114f  pop     rdi
0x140021150  retn
```
