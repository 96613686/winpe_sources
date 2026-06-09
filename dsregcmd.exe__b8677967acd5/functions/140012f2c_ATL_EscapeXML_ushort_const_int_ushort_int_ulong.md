# ATL::EscapeXML(ushort const *,int,ushort *,int,ulong)

- ea: `0x140012f2c`
- end: `0x140013272`
- name: `?EscapeXML@ATL@@YAHPEBGHPEAGHK@Z`
- size: `838`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int, char *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140013278`

## callees

- `0x140001b60`
- `0x14000274e`
- `0x140002814`
- `0x140002a30`
- `0x140005c58`
- `0x140012f2c`
- `0x140014038`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14001324b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14001324b`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall ATL::EscapeXML(const unsigned __int16 *a1, int a2, char *a3, int a4)
{
  int v6; // r15d
  const unsigned __int16 *v7; // r14
  unsigned int v8; // esi
  unsigned __int16 v9; // bp
  int v10; // edx
  int v11; // ecx
  unsigned __int16 v12; // ax
  size_t v13; // r8
  const wchar_t *v14; // r8
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  wchar_t Buffer[8]; // [rsp+20h] [rbp-58h] BYREF
  int v20; // [rsp+30h] [rbp-48h]

  v6 = a2;
  v7 = a1;
  if ( !a1 )
    ATL::AtlThrowImpl(0x80004005);
  v8 = 0;
  v9 = 0;
  if ( a2 )
  {
    while ( 1 )
    {
      v10 = *v7;
      if ( v10 == 34 )
        break;
      switch ( *v7 )
      {
        case '&':
          if ( a3 && a4 > 4 )
          {
            v13 = 2LL * a4;
            if ( v13 < 0xA )
            {
              memset_0(a3, 0, v13);
              *(_DWORD *)_o__errno(v17, v16, v18) = 34;
              invalid_parameter_noinfo();
              ATL::AtlThrowImpl(0x80070057);
            }
            *(_QWORD *)a3 = *(_QWORD *)"&\x00a\x00m\x00p\x00;";
            strcpy(a3 + 8, ";");
            a3 += 10;
          }
          v11 = 5;
          break;
        case '\'':
          goto LABEL_46;
        case '<':
        case '>':
          if ( a3 && a4 > 3 )
          {
            *(_WORD *)a3 = 38;
            v12 = 108;
            if ( *v7 != 60 )
              v12 = 103;
            *((_WORD *)a3 + 1) = v12;
            *((_DWORD *)a3 + 1) = 3866740;
            a3 += 8;
          }
          v11 = 4;
          break;
        default:
          if ( (unsigned __int16)(v10 + 10240) <= 0x3FFu )
          {
            if ( v9 )
            {
              if ( a3 && a4 > 7 )
              {
                swprintf_s(Buffer, 9u, L"&#x%04X;", v9);
                *(_OWORD *)a3 = *(_OWORD *)Buffer;
                a3 += 16;
                LOWORD(v10) = *v7;
              }
              v11 = 8;
            }
            else
            {
              v11 = 0;
            }
            v9 = v10;
            break;
          }
          if ( v9 )
          {
            if ( (unsigned __int16)(v10 + 9216) <= 0x3FFu )
            {
              if ( a3 && a4 > 9 )
              {
                swprintf_s(Buffer, 0xBu, L"&#x%06X;", v10 - 56613888 + (v9 << 10));
                *(_OWORD *)a3 = *(_OWORD *)Buffer;
                *((_DWORD *)a3 + 4) = v20;
                a3 += 20;
              }
              v11 = 10;
              v9 = 0;
              break;
            }
            if ( a3 && a4 > 7 )
            {
              swprintf_s(Buffer, 9u, L"&#x%04X;", v9);
              *(_OWORD *)a3 = *(_OWORD *)Buffer;
              a3 += 16;
            }
            v8 += 8;
            a4 -= 8;
            v9 = 0;
          }
          if ( (unsigned __int16)(*v7 - 32) > 0x5Eu )
          {
            if ( a3 && a4 > 7 )
            {
              swprintf_s(Buffer, 9u, L"&#x%04X;", *v7);
              *(_OWORD *)a3 = *(_OWORD *)Buffer;
              a3 += 16;
            }
            v11 = 8;
          }
          else
          {
            if ( a3 && a4 > 0 )
            {
              *(_WORD *)a3 = *v7;
              a3 += 2;
            }
            v11 = 1;
          }
          break;
      }
LABEL_52:
      a4 -= v11;
      v8 += v11;
      if ( !--v6 )
      {
        if ( v9 )
        {
          if ( (unsigned __int16)(v9 - 32) > 0x5Eu )
          {
            if ( a3 && a4 > 7 )
            {
              swprintf_s(Buffer, 9u, L"&#x%04X;", v9);
              *(_OWORD *)a3 = *(_OWORD *)Buffer;
            }
            a4 -= 8;
            v8 += 8;
          }
          else
          {
            if ( a3 && a4 > 0 )
              *(_WORD *)a3 = v9;
            --a4;
            ++v8;
          }
        }
        goto LABEL_64;
      }
      ++v7;
    }
LABEL_46:
    if ( a3 && a4 > 5 )
    {
      v14 = L"&apos;";
      if ( v10 != 39 )
        v14 = (const wchar_t *)L"&quot;";
      ATL::Checked::memcpy_s(
        (ATL::Checked *)a3,
        (void *)(2LL * a4),
        (unsigned __int64)v14,
        (const void *)0xC,
        *(unsigned __int64 *)Buffer);
      a3 += 12;
    }
    v11 = 6;
    goto LABEL_52;
  }
LABEL_64:
  if ( a3 && a4 < 0 )
    return 0;
  return v8;
}

```

## disassembly

```asm
0x140012f2c  push    rbx
0x140012f2e  push    rbp
0x140012f2f  push    rsi
0x140012f30  push    rdi
0x140012f31  push    r12
0x140012f33  push    r14
0x140012f35  push    r15
0x140012f37  sub     rsp, 40h
0x140012f3b  mov     rax, cs:__security_cookie
0x140012f42  xor     rax, rsp
0x140012f45  mov     [rsp+78h+var_40], rax
0x140012f4a  mov     edi, r9d
0x140012f4d  mov     rbx, r8
0x140012f50  mov     r15d, edx
0x140012f53  mov     r14, rcx
0x140012f56  xor     r12d, r12d
0x140012f59  test    rcx, rcx
0x140012f5c  jz      loc_140013267
0x140012f62  mov     esi, r12d
0x140012f65  mov     ebp, r12d
0x140012f68  test    edx, edx
0x140012f6a  jz      loc_140013218
0x140012f70  mov     r8d, 3FFh
0x140012f76  movzx   edx, word ptr [r14]
0x140012f7a  mov     ecx, edx
0x140012f7c  sub     ecx, 22h ; '"'
0x140012f7f  jz      loc_140013176
0x140012f85  sub     ecx, 4
0x140012f88  jz      loc_14001313A
0x140012f8e  sub     ecx, 1
0x140012f91  jz      loc_140013176
0x140012f97  sub     ecx, 15h
0x140012f9a  jz      loc_140013104
0x140012fa0  cmp     ecx, 2
0x140012fa3  jz      loc_140013104
0x140012fa9  mov     eax, 2800h
0x140012fae  add     eax, edx
0x140012fb0  cmp     ax, r8w
0x140012fb4  ja      short loc_140013002
0x140012fb6  test    bp, bp
0x140012fb9  jz      short loc_140012FF7
0x140012fbb  test    rbx, rbx
0x140012fbe  jz      short loc_140012FF0
0x140012fc0  cmp     edi, 7
0x140012fc3  jle     short loc_140012FF0
0x140012fc5  movzx   r9d, bp
0x140012fc9  lea     r8, aX04x; "&#x%04X;"
0x140012fd0  mov     edx, 9; BufferCount
0x140012fd5  lea     rcx, [rsp+78h+Buffer]; Buffer
0x140012fda  call    swprintf_s
0x140012fdf  movups  xmm0, xmmword ptr [rsp+78h+Buffer]
0x140012fe4  movdqu  xmmword ptr [rbx], xmm0
0x140012fe8  add     rbx, 10h
0x140012fec  movzx   edx, word ptr [r14]
0x140012ff0  mov     ecx, 8
0x140012ff5  jmp     short loc_140012FFA
0x140012ff7  mov     ecx, r12d
0x140012ffa  movzx   ebp, dx
0x140012ffd  jmp     loc_1400131B2
0x140013002  test    bp, bp
0x140013005  jz      loc_1400130A3
0x14001300b  mov     eax, 2400h
0x140013010  add     eax, edx
0x140013012  cmp     ax, r8w
0x140013016  ja      short loc_140013069
0x140013018  test    rbx, rbx
0x14001301b  jz      short loc_14001305C
0x14001301d  cmp     edi, 9
0x140013020  jle     short loc_14001305C
0x140013022  movzx   r9d, bp
0x140013026  shl     r9d, 0Ah
0x14001302a  add     edx, 0FCA02400h
0x140013030  add     r9d, edx
0x140013033  lea     r8, aX06x; "&#x%06X;"
0x14001303a  mov     edx, 0Bh; BufferCount
0x14001303f  lea     rcx, [rsp+78h+Buffer]; Buffer
0x140013044  call    swprintf_s
0x140013049  movups  xmm0, xmmword ptr [rsp+78h+Buffer]
0x14001304e  movups  xmmword ptr [rbx], xmm0
0x140013051  mov     eax, [rsp+78h+var_48]
0x140013055  mov     [rbx+10h], eax
0x140013058  add     rbx, 14h
0x14001305c  mov     ecx, 0Ah
0x140013061  mov     ebp, r12d
0x140013064  jmp     loc_1400131B2
0x140013069  test    rbx, rbx
0x14001306c  jz      short loc_14001309A
0x14001306e  cmp     edi, 7
0x140013071  jle     short loc_14001309A
0x140013073  movzx   r9d, bp
0x140013077  lea     r8, aX04x; "&#x%04X;"
0x14001307e  mov     edx, 9; BufferCount
0x140013083  lea     rcx, [rsp+78h+Buffer]; Buffer
0x140013088  call    swprintf_s
0x14001308d  movups  xmm0, xmmword ptr [rsp+78h+Buffer]
0x140013092  movdqu  xmmword ptr [rbx], xmm0
0x140013096  add     rbx, 10h
0x14001309a  add     esi, 8
0x14001309d  sub     edi, 8
0x1400130a0  mov     ebp, r12d
0x1400130a3  movzx   ecx, word ptr [r14]
0x1400130a7  lea     eax, [rcx-20h]
0x1400130aa  cmp     ax, 5Eh ; '^'
0x1400130ae  ja      short loc_1400130CA
0x1400130b0  test    rbx, rbx
0x1400130b3  jz      short loc_1400130C0
0x1400130b5  test    edi, edi
0x1400130b7  jle     short loc_1400130C0
0x1400130b9  mov     [rbx], cx
0x1400130bc  add     rbx, 2
0x1400130c0  mov     ecx, 1
0x1400130c5  jmp     loc_1400131B2
0x1400130ca  test    rbx, rbx
0x1400130cd  jz      short loc_1400130FA
0x1400130cf  cmp     edi, 7
0x1400130d2  jle     short loc_1400130FA
0x1400130d4  mov     r9d, ecx
0x1400130d7  lea     r8, aX04x; "&#x%04X;"
0x1400130de  mov     edx, 9; BufferCount
0x1400130e3  lea     rcx, [rsp+78h+Buffer]; Buffer
0x1400130e8  call    swprintf_s
0x1400130ed  movups  xmm0, xmmword ptr [rsp+78h+Buffer]
0x1400130f2  movdqu  xmmword ptr [rbx], xmm0
0x1400130f6  add     rbx, 10h
0x1400130fa  mov     ecx, 8
0x1400130ff  jmp     loc_1400131B2
0x140013104  test    rbx, rbx
0x140013107  jz      short loc_140013133
0x140013109  cmp     edi, 3
0x14001310c  jle     short loc_140013133
0x14001310e  mov     word ptr [rbx], 26h ; '&'
0x140013113  mov     eax, 6Ch ; 'l'
0x140013118  lea     ecx, [rax-5]
0x14001311b  cmp     word ptr [r14], 3Ch ; '<'
0x140013120  cmovnz  ax, cx
0x140013124  mov     [rbx+2], ax
0x140013128  mov     dword ptr [rbx+4], 3B0074h
0x14001312f  add     rbx, 8
0x140013133  mov     ecx, 4
0x140013138  jmp     short loc_1400131B2
0x14001313a  test    rbx, rbx
0x14001313d  jz      short loc_14001316F
0x14001313f  cmp     edi, 4
0x140013142  jle     short loc_14001316F
0x140013144  movsxd  r8, edi
0x140013147  add     r8, r8; Size
0x14001314a  cmp     r8, 0Ah
0x14001314e  jb      loc_140013241
0x140013154  movsd   xmm0, qword ptr cs:?s_chBase64EncodingTable@?1??Base64Encode@ATL@@YAHPEBEHPEADPEAHK@Z@4QBDB+40h; "&\x00a\x00m\x00p\x00;"
0x14001315c  movsd   qword ptr [rbx], xmm0
0x140013160  movzx   eax, word ptr cs:?s_chBase64EncodingTable@?1??Base64Encode@ATL@@YAHPEBEHPEADPEAHK@Z@4QBDB+48h; ";"
0x140013167  mov     [rbx+8], ax
0x14001316b  add     rbx, 0Ah
0x14001316f  mov     ecx, 5
0x140013174  jmp     short loc_1400131B2
0x140013176  test    rbx, rbx
0x140013179  jz      short loc_1400131AD
0x14001317b  cmp     edi, 5
0x14001317e  jle     short loc_1400131AD
0x140013180  lea     rax, aQuot; "&quot;"
0x140013187  lea     r8, aApos; "&apos;"
0x14001318e  cmp     edx, 27h ; '''
0x140013191  cmovnz  r8, rax; unsigned __int64
0x140013195  movsxd  rdx, edi
0x140013198  add     rdx, rdx; void *
0x14001319b  mov     r9d, 0Ch; void *
0x1400131a1  mov     rcx, rbx; this
0x1400131a4  call    ?memcpy_s@Checked@ATL@@YAXPEAX_KPEBX1@Z; ATL::Checked::memcpy_s(void *,unsigned __int64,void const *,unsigned __int64)
0x1400131a9  add     rbx, 0Ch
0x1400131ad  mov     ecx, 6
0x1400131b2  sub     edi, ecx
0x1400131b4  add     esi, ecx
0x1400131b6  sub     r15d, 1
0x1400131ba  jz      short loc_1400131C5
0x1400131bc  add     r14, 2
0x1400131c0  jmp     loc_140012F70
0x1400131c5  test    bp, bp
0x1400131c8  jz      short loc_140013218
0x1400131ca  lea     eax, [rbp-20h]
0x1400131cd  cmp     ax, 5Eh ; '^'
0x1400131d1  ja      short loc_1400131E5
0x1400131d3  test    rbx, rbx
0x1400131d6  jz      short loc_1400131DF
0x1400131d8  test    edi, edi
0x1400131da  jle     short loc_1400131DF
0x1400131dc  mov     [rbx], bp
0x1400131df  dec     edi
0x1400131e1  inc     esi
0x1400131e3  jmp     short loc_140013218
0x1400131e5  test    rbx, rbx
0x1400131e8  jz      short loc_140013212
0x1400131ea  cmp     edi, 7
0x1400131ed  jle     short loc_140013212
0x1400131ef  movzx   r9d, bp
0x1400131f3  lea     r8, aX04x; "&#x%04X;"
0x1400131fa  mov     edx, 9; BufferCount
0x1400131ff  lea     rcx, [rsp+78h+Buffer]; Buffer
0x140013204  call    swprintf_s
0x140013209  movups  xmm0, xmmword ptr [rsp+78h+Buffer]
0x14001320e  movdqu  xmmword ptr [rbx], xmm0
0x140013212  sub     edi, 8
0x140013215  add     esi, 8
0x140013218  test    rbx, rbx
0x14001321b  jz      short loc_140013223
0x14001321d  test    edi, edi
0x14001321f  cmovs   esi, r12d
0x140013223  mov     eax, esi
0x140013225  mov     rcx, [rsp+78h+var_40]
0x14001322a  xor     rcx, rsp; StackCookie
0x14001322d  call    __security_check_cookie
0x140013232  add     rsp, 40h
0x140013236  pop     r15
0x140013238  pop     r14
0x14001323a  pop     r12
0x14001323c  pop     rdi
0x14001323d  pop     rsi
0x14001323e  pop     rbp
0x14001323f  pop     rbx
0x140013240  retn
0x140013241  xor     edx, edx; Val
0x140013243  mov     rcx, rbx; void *
0x140013246  call    memset_0
0x14001324b  call    cs:__imp__o__errno
0x140013251  mov     dword ptr [rax], 22h ; '"'
0x140013257  call    _invalid_parameter_noinfo
0x14001325c  mov     ecx, 80070057h; unsigned int
0x140013261  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140013267  mov     ecx, 80004005h; unsigned int
0x14001326c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
