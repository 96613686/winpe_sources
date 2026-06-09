# CHtmlScanner::GetBlockOfChars(ulong,wchar_t *,ulong &,CToken &)

- ea: `0x180009fa0`
- end: `0x18000a36e`
- name: `?GetBlockOfChars@CHtmlScanner@@QEAAXKPEA_WAEAKAEAVCToken@@@Z`
- size: `974`
- prototype: `void __fastcall(CHtmlScanner *this, int, wchar_t *, const wchar_t *, struct CToken *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000b68c`
- `0x18000eac8`

## callees

- `0x180006768`
- `0x180006ad0`
- `0x1800074e0`
- `0x180009a90`
- `0x180009fa0`
- `0x18000a374`
- `0x18000abd0`

## pseudocode

```c
void __fastcall CHtmlScanner::GetBlockOfChars(
        CHtmlScanner *this,
        int a2,
        wchar_t *a3,
        const wchar_t *a4,
        struct CToken *a5)
{
  __int64 v9; // rdx
  __int64 v10; // rdi
  __int64 v11; // rcx
  wchar_t *v12; // rdx
  wchar_t Char; // ax
  __int64 v14; // rdx
  CSerialStream *v15; // rcx
  wchar_t v16; // si
  unsigned int v17; // r8d
  __int64 v18; // rax
  wchar_t v19; // cx
  wchar_t *v20; // rdx
  unsigned int i; // r12d
  wchar_t v22; // ax
  wchar_t v23; // [rsp+78h] [rbp+10h] BYREF

  *(_DWORD *)a4 = 0;
LABEL_2:
  while ( a2 )
  {
    v9 = *((_QWORD *)this + 1);
    if ( *(__int16 *)(v9 + 40) <= 0
      && *(_QWORD *)(v9 + 88) >= v9 + 2 * ((unsigned __int64)*(unsigned int *)(v9 + 84) + 21)
      && !*(_DWORD *)(v9 + 116)
      && *(_DWORD *)(v9 + 100) >= *(_DWORD *)(v9 + 104)
      && *(_DWORD *)(v9 + 96) == *(_DWORD *)(v9 + 296)
      && (unsigned int)CMmStreamConsecBuf::Eof((CMmStreamConsecBuf *)(v9 + 288)) )
    {
      *(_DWORD *)a5 = 2;
      break;
    }
    v10 = *((_QWORD *)this + 1);
    v11 = *(__int16 *)(v10 + 40);
    if ( (__int16)v11 > 0 )
    {
      *(_WORD *)(v10 + 40) = v11 - 1;
      v16 = *(_WORD *)(v10 + 2 * v11 - 2);
      goto LABEL_12;
    }
    v12 = *(wchar_t **)(v10 + 88);
    if ( (unsigned __int64)v12 < v10 + 2 * ((unsigned __int64)*(unsigned int *)(v10 + 84) + 21) )
    {
      v16 = *v12;
      *(_QWORD *)(v10 + 88) = v12 + 1;
      goto LABEL_12;
    }
    if ( !*(_DWORD *)(v10 + 116)
      && *(_DWORD *)(v10 + 100) >= *(_DWORD *)(v10 + 104)
      && *(_DWORD *)(v10 + 96) == *(_DWORD *)(v10 + 296)
      && (unsigned int)CMmStreamConsecBuf::Eof((CMmStreamConsecBuf *)(v10 + 288)) )
    {
      a3[(*(_DWORD *)a4)++] = -1;
      --a2;
    }
    else
    {
      Char = CMemoryMappedInputStream::GetChar((CMemoryMappedInputStream *)(v10 + 96), (__int64)v12, (__int64)a3, a4);
      v23 = Char;
      v16 = Char;
      if ( Char == 10 || Char == 13 )
      {
        v16 = 32;
        goto LABEL_12;
      }
      if ( Char == 38 )
      {
        *(_WORD *)(v10 + 42) = 38;
        for ( i = 1; i < 0x14; ++i )
        {
          if ( !*(_DWORD *)(v10 + 116)
            && *(_DWORD *)(v10 + 100) >= *(_DWORD *)(v10 + 104)
            && *(_DWORD *)(v10 + 96) == *(_DWORD *)(v10 + 296)
            && (unsigned int)CMmStreamConsecBuf::Eof((CMmStreamConsecBuf *)(v10 + 288)) )
          {
            if ( i == 1 )
            {
              a3[(*(_DWORD *)a4)++] = 38;
              --a2;
              goto LABEL_2;
            }
            --i;
            break;
          }
          v22 = CMemoryMappedInputStream::GetChar((CMemoryMappedInputStream *)(v10 + 96), v14, (__int64)a3, a4);
          v23 = v22;
          v16 = v22;
          if ( v22 == 10 || v22 == 13 )
          {
            v16 = 32;
            v23 = 32;
            *(_WORD *)(v10 + 2LL * i + 42) = 32;
          }
          else
          {
            *(_WORD *)(v10 + 2LL * i + 42) = v22;
            if ( v22 == 59 )
              goto LABEL_44;
            if ( v22 == 38 )
              break;
          }
        }
        if ( v16 != 59
          && (*(_DWORD *)(v10 + 116)
           || *(_DWORD *)(v10 + 100) < *(_DWORD *)(v10 + 104)
           || *(_DWORD *)(v10 + 96) != *(_DWORD *)(v10 + 296)
           || !(unsigned int)CMmStreamConsecBuf::Eof((CMmStreamConsecBuf *)(v10 + 288))) )
        {
          if ( v16 == 38 )
          {
            *(_DWORD *)(v10 + 116) = 1;
            *(_WORD *)(v10 + 120) = 38;
          }
          *(_DWORD *)(v10 + 84) = i;
          *(_QWORD *)(v10 + 88) = v10 + 44;
          a3[(*(_DWORD *)a4)++] = 38;
          --a2;
          continue;
        }
LABEL_44:
        if ( *(_WORD *)(v10 + 44) == 35
          && (unsigned int)CSerialStream::IsUnicodeNumber(v15, (const wchar_t *)(v10 + 46), i - 2, &v23) )
        {
          v16 = v23;
          goto LABEL_12;
        }
        if ( (unsigned int)LookupSpecialChar((const wchar_t *)(v10 + 44), i - 1, &v23) )
        {
          v16 = v23;
          goto LABEL_12;
        }
        *(_QWORD *)(v10 + 88) = v10 + 44;
        *(_DWORD *)(v10 + 84) = i + 1;
        a3[(*(_DWORD *)a4)++] = 38;
        --a2;
      }
      else
      {
LABEL_12:
        if ( v16 == 60 && (unsigned int)CHtmlScanner::Peek_ParseAsTag(this) )
        {
          CHtmlScanner::ScanTagName(this, a5);
          break;
        }
        a3[(*(_DWORD *)a4)++] = v16;
        --a2;
      }
    }
  }
  v17 = *(_DWORD *)a4;
  if ( *(_DWORD *)a4 )
  {
    v18 = 0;
    do
    {
      v19 = a3[v18];
      v20 = &a3[v18];
      switch ( v19 )
      {
        case 0xE800:
          *v20 = 60;
          break;
        case 0xE801:
          *v20 = 62;
          break;
        case 0xE802:
          *v20 = 34;
          break;
      }
      v18 = (unsigned int)(v18 + 1);
    }
    while ( (unsigned int)v18 < v17 );
  }
}

```

## disassembly

```asm
0x180009fa0  push    rbx
0x180009fa2  push    rbp
0x180009fa3  push    rsi
0x180009fa4  push    rdi
0x180009fa5  push    r12
0x180009fa7  push    r13
0x180009fa9  push    r14
0x180009fab  push    r15
0x180009fad  sub     rsp, 28h
0x180009fb1  mov     r14, r9
0x180009fb4  mov     dword ptr [r9], 0
0x180009fbb  mov     rbx, r8
0x180009fbe  mov     r15d, edx
0x180009fc1  mov     r13, rcx
0x180009fc4  mov     r12d, 20h ; ' '
0x180009fca  test    r15d, r15d
0x180009fcd  jz      loc_18000A0D8
0x180009fd3  mov     rdx, [r13+8]
0x180009fd7  cmp     word ptr [rdx+28h], 0
0x180009fdc  jg      short loc_180009FF3
0x180009fde  mov     ecx, [rdx+54h]
0x180009fe1  add     rcx, 15h
0x180009fe5  lea     rcx, [rdx+rcx*2]
0x180009fe9  cmp     [rdx+58h], rcx
0x180009fed  jnb     loc_18000A076
0x180009ff3  mov     rdi, [r13+8]
0x180009ff7  movsx   rcx, word ptr [rdi+28h]
0x180009ffc  test    cx, cx
0x180009fff  jg      loc_18000A147
0x18000a005  mov     ecx, [rdi+54h]
0x18000a008  mov     rdx, [rdi+58h]
0x18000a00c  add     rcx, 15h
0x18000a010  lea     rcx, [rdi+rcx*2]
0x18000a014  cmp     rdx, rcx
0x18000a017  jb      loc_18000A158
0x18000a01d  cmp     dword ptr [rdi+74h], 0
0x18000a021  jnz     short loc_18000A02F
0x18000a023  mov     eax, [rdi+68h]
0x18000a026  cmp     [rdi+64h], eax
0x18000a029  jnb     loc_18000A168
0x18000a02f  lea     rcx, [rdi+60h]; this
0x18000a033  call    ?GetChar@CMemoryMappedInputStream@@QEAA_WXZ; CMemoryMappedInputStream::GetChar(void)
0x18000a038  mov     [rsp+68h+arg_8], ax
0x18000a03d  movzx   esi, ax
0x18000a040  cmp     ax, 0Ah
0x18000a044  jz      loc_18000A19F
0x18000a04a  cmp     ax, 0Dh
0x18000a04e  jz      loc_18000A19F
0x18000a054  cmp     ax, 26h ; '&'
0x18000a058  jz      loc_18000A1A8
0x18000a05e  cmp     si, 3Ch ; '<'
0x18000a062  jz      short loc_18000A0BC
0x18000a064  mov     eax, [r14]
0x18000a067  mov     [rbx+rax*2], si
0x18000a06b  inc     dword ptr [r14]
0x18000a06e  dec     r15d
0x18000a071  jmp     loc_180009FC4
0x18000a076  cmp     dword ptr [rdx+74h], 0
0x18000a07a  jnz     loc_180009FF3
0x18000a080  mov     eax, [rdx+68h]
0x18000a083  cmp     [rdx+64h], eax
0x18000a086  jb      loc_180009FF3
0x18000a08c  lea     rcx, [rdx+120h]; this
0x18000a093  mov     eax, [rcx+8]
0x18000a096  cmp     [rdx+60h], eax
0x18000a099  jnz     loc_180009FF3
0x18000a09f  call    ?Eof@CMmStreamConsecBuf@@QEAAHXZ; CMmStreamConsecBuf::Eof(void)
0x18000a0a4  test    eax, eax
0x18000a0a6  jz      loc_180009FF3
0x18000a0ac  mov     rax, [rsp+68h+arg_20]
0x18000a0b4  mov     dword ptr [rax], 2
0x18000a0ba  jmp     short loc_18000A0D8
0x18000a0bc  mov     rcx, r13; this
0x18000a0bf  call    ?Peek_ParseAsTag@CHtmlScanner@@QEAAHXZ; CHtmlScanner::Peek_ParseAsTag(void)
0x18000a0c4  test    eax, eax
0x18000a0c6  jz      short loc_18000A064
0x18000a0c8  mov     rdx, [rsp+68h+arg_20]; struct CToken *
0x18000a0d0  mov     rcx, r13; this
0x18000a0d3  call    ?ScanTagName@CHtmlScanner@@AEAAXAEAVCToken@@@Z; CHtmlScanner::ScanTagName(CToken &)
0x18000a0d8  mov     r8d, [r14]
0x18000a0db  test    r8d, r8d
0x18000a0de  jz      short loc_18000A121
0x18000a0e0  xor     eax, eax
0x18000a0e2  test    r8d, r8d
0x18000a0e5  jz      short loc_18000A121
0x18000a0e7  mov     r11d, 0E800h
0x18000a0ed  mov     r9d, 0E801h
0x18000a0f3  mov     r10d, 0E802h
0x18000a0f9  nop     dword ptr [rax+00000000h]
0x18000a100  movzx   ecx, word ptr [rbx+rax*2]
0x18000a104  lea     rdx, [rbx+rax*2]
0x18000a108  cmp     cx, r11w
0x18000a10c  jz      short loc_18000A139
0x18000a10e  cmp     cx, r9w
0x18000a112  jz      short loc_18000A140
0x18000a114  cmp     cx, r10w
0x18000a118  jz      short loc_18000A132
0x18000a11a  inc     eax
0x18000a11c  cmp     eax, r8d
0x18000a11f  jb      short loc_18000A100
0x18000a121  add     rsp, 28h
0x18000a125  pop     r15
0x18000a127  pop     r14
0x18000a129  pop     r13
0x18000a12b  pop     r12
0x18000a12d  pop     rdi
0x18000a12e  pop     rsi
0x18000a12f  pop     rbp
0x18000a130  pop     rbx
0x18000a131  retn
0x18000a132  mov     word ptr [rdx], 22h ; '"'
0x18000a137  jmp     short loc_18000A11A
0x18000a139  mov     word ptr [rdx], 3Ch ; '<'
0x18000a13e  jmp     short loc_18000A11A
0x18000a140  mov     word ptr [rdx], 3Eh ; '>'
0x18000a145  jmp     short loc_18000A11A
0x18000a147  lea     eax, [rcx-1]
0x18000a14a  mov     [rdi+28h], ax
0x18000a14e  movzx   esi, word ptr [rdi+rcx*2-2]
0x18000a153  jmp     loc_18000A05E
0x18000a158  movzx   esi, word ptr [rdx]
0x18000a15b  lea     rax, [rdx+2]
0x18000a15f  mov     [rdi+58h], rax
0x18000a163  jmp     loc_18000A05E
0x18000a168  lea     rcx, [rdi+120h]; this
0x18000a16f  mov     eax, [rcx+8]
0x18000a172  cmp     [rdi+60h], eax
0x18000a175  jnz     loc_18000A02F
0x18000a17b  call    ?Eof@CMmStreamConsecBuf@@QEAAHXZ; CMmStreamConsecBuf::Eof(void)
0x18000a180  test    eax, eax
0x18000a182  jz      loc_18000A02F
0x18000a188  mov     eax, [r14]
0x18000a18b  mov     esi, 0FFFFh
0x18000a190  mov     [rbx+rax*2], si
0x18000a194  inc     dword ptr [r14]
0x18000a197  dec     r15d
0x18000a19a  jmp     loc_180009FC4
0x18000a19f  movzx   esi, r12w
0x18000a1a3  jmp     loc_18000A05E
0x18000a1a8  mov     [rdi+2Ah], ax
0x18000a1ac  mov     r12d, 1
0x18000a1b2  cmp     r12d, 14h
0x18000a1b6  jnb     loc_18000A2DB
0x18000a1bc  cmp     dword ptr [rdi+74h], 0
0x18000a1c0  jnz     short loc_18000A1CE
0x18000a1c2  mov     eax, [rdi+68h]
0x18000a1c5  cmp     [rdi+64h], eax
0x18000a1c8  jnb     loc_18000A255
0x18000a1ce  lea     rcx, [rdi+60h]; this
0x18000a1d2  call    ?GetChar@CMemoryMappedInputStream@@QEAA_WXZ; CMemoryMappedInputStream::GetChar(void)
0x18000a1d7  mov     [rsp+68h+arg_8], ax
0x18000a1dc  movzx   esi, ax
0x18000a1df  cmp     ax, 0Ah
0x18000a1e3  jz      loc_18000A2A4
0x18000a1e9  cmp     ax, 0Dh
0x18000a1ed  jz      loc_18000A2A4
0x18000a1f3  mov     eax, r12d
0x18000a1f6  mov     [rdi+rax*2+2Ah], si
0x18000a1fb  cmp     si, 3Bh ; ';'
0x18000a1ff  jnz     loc_18000A296
0x18000a205  cmp     word ptr [rdi+2Ch], 23h ; '#'
0x18000a20a  lea     rsi, [rdi+2Ch]
0x18000a20e  jz      short loc_18000A234
0x18000a210  lea     edx, [r12-1]; unsigned int
0x18000a215  mov     rcx, rsi; Src
0x18000a218  lea     r8, [rsp+68h+arg_8]; wchar_t *
0x18000a21d  call    ?LookupSpecialChar@@YAHPEB_WKAEA_W@Z; LookupSpecialChar(wchar_t const *,ulong,wchar_t &)
0x18000a222  test    eax, eax
0x18000a224  jz      loc_18000A2B8
0x18000a22a  movzx   esi, [rsp+68h+arg_8]
0x18000a22f  jmp     loc_18000A05E
0x18000a234  lea     r8d, [r12-2]; unsigned int
0x18000a239  lea     rdx, [rdi+2Eh]; wchar_t *
0x18000a23d  lea     r9, [rsp+68h+arg_8]; wchar_t *
0x18000a242  call    ?IsUnicodeNumber@CSerialStream@@AEAAHPEB_WIAEA_W@Z; CSerialStream::IsUnicodeNumber(wchar_t const *,uint,wchar_t &)
0x18000a247  test    eax, eax
0x18000a249  jz      short loc_18000A210
0x18000a24b  movzx   esi, [rsp+68h+arg_8]
0x18000a250  jmp     loc_18000A05E
0x18000a255  lea     rcx, [rdi+120h]; this
0x18000a25c  mov     eax, [rcx+8]
0x18000a25f  cmp     [rdi+60h], eax
0x18000a262  jnz     loc_18000A1CE
0x18000a268  call    ?Eof@CMmStreamConsecBuf@@QEAAHXZ; CMmStreamConsecBuf::Eof(void)
0x18000a26d  test    eax, eax
0x18000a26f  jz      loc_18000A1CE
0x18000a275  cmp     r12d, 1
0x18000a279  jnz     loc_18000A366
0x18000a27f  mov     eax, [r14]
0x18000a282  mov     esi, 26h ; '&'
0x18000a287  mov     [rbx+rax*2], si
0x18000a28b  inc     dword ptr [r14]
0x18000a28e  dec     r15d
0x18000a291  jmp     loc_180009FC4
0x18000a296  cmp     si, 26h ; '&'
0x18000a29a  jz      short loc_18000A2DB
0x18000a29c  inc     r12d
0x18000a29f  jmp     loc_18000A1B2
0x18000a2a4  mov     esi, 20h ; ' '
0x18000a2a9  mov     eax, r12d
0x18000a2ac  mov     [rsp+68h+arg_8], si
0x18000a2b1  mov     [rdi+rax*2+2Ah], si
0x18000a2b6  jmp     short loc_18000A29C
0x18000a2b8  mov     [rdi+58h], rsi
0x18000a2bc  lea     eax, [r12+1]
0x18000a2c1  mov     [rdi+54h], eax
0x18000a2c4  mov     esi, 26h ; '&'
0x18000a2c9  mov     eax, [r14]
0x18000a2cc  mov     [rbx+rax*2], si
0x18000a2d0  inc     dword ptr [r14]
0x18000a2d3  dec     r15d
0x18000a2d6  jmp     loc_180009FC4
0x18000a2db  cmp     si, 3Bh ; ';'
0x18000a2df  jz      loc_18000A205
0x18000a2e5  cmp     dword ptr [rdi+74h], 0
0x18000a2e9  jnz     short loc_18000A2F3
0x18000a2eb  mov     eax, [rdi+68h]
0x18000a2ee  cmp     [rdi+64h], eax
0x18000a2f1  jnb     short loc_18000A349
0x18000a2f3  lea     rax, [rdi+2Ch]
0x18000a2f7  cmp     si, 26h ; '&'
0x18000a2fb  jnz     short loc_18000A32A
0x18000a2fd  mov     dword ptr [rdi+74h], 1
0x18000a304  mov     ecx, 26h ; '&'
0x18000a309  mov     [rdi+78h], cx
0x18000a30d  movzx   esi, cx
0x18000a310  mov     [rdi+54h], r12d
0x18000a314  mov     [rdi+58h], rax
0x18000a318  mov     eax, [r14]
0x18000a31b  mov     [rbx+rax*2], cx
0x18000a31f  inc     dword ptr [r14]
0x18000a322  dec     r15d
0x18000a325  jmp     loc_180009FC4
0x18000a32a  mov     [rdi+54h], r12d
0x18000a32e  mov     esi, 26h ; '&'
0x18000a333  mov     [rdi+58h], rax
0x18000a337  mov     eax, [r14]
0x18000a33a  mov     [rbx+rax*2], si
0x18000a33e  inc     dword ptr [r14]
0x18000a341  dec     r15d
0x18000a344  jmp     loc_180009FC4
0x18000a349  lea     rcx, [rdi+120h]; this
0x18000a350  mov     eax, [rcx+8]
0x18000a353  cmp     [rdi+60h], eax
0x18000a356  jnz     short loc_18000A2F3
0x18000a358  call    ?Eof@CMmStreamConsecBuf@@QEAAHXZ; CMmStreamConsecBuf::Eof(void)
0x18000a35d  test    eax, eax
0x18000a35f  jz      short loc_18000A2F3
0x18000a361  jmp     loc_18000A205
0x18000a366  dec     r12d
0x18000a369  jmp     loc_18000A2DB
```
