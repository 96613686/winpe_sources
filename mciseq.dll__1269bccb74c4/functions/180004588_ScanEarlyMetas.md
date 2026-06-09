# ScanEarlyMetas

- ea: `0x180004588`
- end: `0x180004845`
- name: `ScanEarlyMetas`
- size: `701`
- prototype: `__int64 __fastcall(_DWORD *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180005a1c`

## callees

- `0x180003f18`
- `0x180003f68`
- `0x180003fdc`
- `0x180004430`
- `0x180004588`
- `0x180004fa4`
- `0x1800058bc`

## pseudocode

```c
__int64 __fastcall ScanEarlyMetas(_DWORD *a1, __int64 a2)
{
  __int64 v2; // rbx
  __int64 v4; // rdx
  int v5; // ebp
  int v6; // ecx
  __int64 Status; // rdx
  __int64 v8; // r8
  __int64 v9; // rcx
  char v10; // si
  unsigned __int8 v11; // al
  unsigned __int8 v13; // al
  int VarLen; // eax
  bool v15; // cf
  unsigned int v16; // eax
  __int64 v17; // rbx
  __int64 v18; // rax

  v2 = a2;
  if ( !a2 )
  {
    v4 = qword_18000A628[2 * (unsigned int)a1[18]];
    v2 = (v4 + 16) & -(__int64)(v4 != 0);
    *(_BYTE *)(v2 + 12) = 0;
    *(_DWORD *)(v2 + 8) = 0;
  }
  while ( 1 )
  {
    v5 = *(_DWORD *)(v2 + 4);
    *(_QWORD *)(v2 + 40) = *(_QWORD *)(v2 + 24);
    v6 = GetVarLen(v2) + v5;
    *(_DWORD *)(v2 + 4) = v6;
    if ( *(_DWORD *)v2 )
    {
LABEL_54:
      if ( !v2 )
        return 1;
      goto LABEL_55;
    }
    if ( (unsigned int)(*(_DWORD *)(v2 + 8) + v6) >= 0x7FFFFFFF )
      goto LABEL_45;
    Status = (unsigned __int8)GetStatus(v2);
    if ( *(_DWORD *)v2 )
      goto LABEL_54;
    if ( (unsigned __int8)Status < 0x80u )
      goto LABEL_60;
    if ( (unsigned __int8)Status > 0xF8u )
    {
      if ( (_DWORD)Status == 249
        || (_DWORD)Status == 250
        || (_DWORD)Status == 251
        || (_DWORD)Status == 252
        || (v9 = (unsigned int)(Status - 253), (unsigned int)v9 < 2) )
      {
LABEL_60:
        a1[524] &= ~1u;
        return 1;
      }
      if ( (_BYTE)Status == 0xFF )
      {
        if ( !(unsigned int)HandleMetaEvent((__int64)a1, v2, 4) )
          return 0;
        goto LABEL_45;
      }
    }
    else
    {
      if ( (_BYTE)Status == 0xF8 )
        goto LABEL_60;
      switch ( (_DWORD)Status )
      {
        case 0xF1:
          goto LABEL_60;
        case 0xF2:
          goto LABEL_60;
        case 0xF3:
          goto LABEL_60;
        case 0xF4:
          goto LABEL_60;
      }
      v9 = (unsigned int)(Status - 245);
      if ( (unsigned int)v9 < 2 )
        goto LABEL_60;
    }
    v10 = Status & 0xF;
    if ( (Status & 0xF0) == 0xC0 )
    {
      v11 = LookByte(v2);
      if ( !*(_DWORD *)v2 )
        ++*(_QWORD *)(v2 + 24);
      if ( v11 < 0x80u )
      {
        if ( *(_DWORD *)v2 )
          goto LABEL_54;
        *((_WORD *)a1 + v11 + 98) |= 1 << v10;
      }
LABEL_45:
      if ( *(_DWORD *)v2 )
        goto LABEL_54;
      goto LABEL_46;
    }
    if ( (Status & 0xF0) == 0x90 && (v10 == 15 || v10 == 9) )
    {
      v13 = LookByte(v2);
      if ( !*(_DWORD *)v2 )
        ++*(_QWORD *)(v2 + 24);
      if ( v13 < 0x80u )
      {
        if ( *(_DWORD *)v2 )
          goto LABEL_54;
        *((_WORD *)a1 + v13 + 226) |= 1 << v10;
        LookByte(v2);
        if ( *(_DWORD *)v2 )
          goto LABEL_54;
        ++*(_QWORD *)(v2 + 24);
      }
      goto LABEL_45;
    }
    if ( (_BYTE)Status == 0xF0 || (_BYTE)Status == 0xF7 )
    {
      VarLen = GetVarLen(v2);
    }
    else
    {
      LOBYTE(v9) = Status;
      VarLen = MIDILength(v9, Status, v8) - 1;
    }
    if ( *(_DWORD *)v2 )
      goto LABEL_54;
    if ( !VarLen )
      goto LABEL_45;
    SkipBytes(v2, VarLen);
    if ( *(_DWORD *)v2 )
    {
      *(_DWORD *)v2 = 279;
      goto LABEL_45;
    }
LABEL_46:
    if ( !*(_DWORD *)(v2 + 56) )
    {
      *(_DWORD *)(v2 + 8) += *(_DWORD *)(v2 + 4);
      v15 = *(_DWORD *)(v2 + 8) < 0x7FFFFFFFu;
      *(_DWORD *)(v2 + 4) = 0;
      if ( v15 )
        continue;
    }
    if ( *(_DWORD *)v2 )
      goto LABEL_54;
    v16 = *(_DWORD *)(v2 + 8);
    if ( v16 > a1[4] )
      a1[4] = v16;
    v17 = *(_QWORD *)(v2 - 16);
    if ( !v17 )
      return 1;
    v2 = v17 + 16;
    if ( !v2 )
      return 1;
    *(_BYTE *)(v2 + 12) = 0;
    *(_DWORD *)(v2 + 8) = 0;
LABEL_55:
    if ( *(_DWORD *)v2 )
      break;
  }
  if ( *(_DWORD *)v2 == 350 )
  {
    v18 = *(_QWORD *)(v2 + 40);
    if ( !v18 )
      return 0;
    *(_QWORD *)(v2 + 24) = v18;
    *(_DWORD *)(v2 + 4) = v5;
    *(_DWORD *)v2 = 273;
  }
  return 1;
}

```

## disassembly

```asm
0x180004588  push    rbx
0x18000458a  push    rbp
0x18000458b  push    rsi
0x18000458c  push    rdi
0x18000458d  push    r14
0x18000458f  sub     rsp, 20h
0x180004593  xor     r14d, r14d
0x180004596  mov     rbx, rdx
0x180004599  mov     rdi, rcx
0x18000459c  test    rdx, rdx
0x18000459f  jnz     short loc_1800045C7
0x1800045a1  mov     eax, [rcx+48h]
0x1800045a4  lea     rdx, qword_18000A628
0x1800045ab  add     rax, rax
0x1800045ae  mov     rdx, [rdx+rax*8]
0x1800045b2  lea     rax, [rdx+10h]
0x1800045b6  neg     rdx
0x1800045b9  sbb     rbx, rbx
0x1800045bc  and     rbx, rax
0x1800045bf  mov     [rbx+0Ch], r14b
0x1800045c3  mov     [rbx+8], r14d
0x1800045c7  mov     rax, [rbx+18h]
0x1800045cb  mov     rcx, rbx
0x1800045ce  mov     ebp, [rbx+4]
0x1800045d1  mov     [rbx+28h], rax
0x1800045d5  call    GetVarLen
0x1800045da  lea     ecx, [rax+rbp]
0x1800045dd  mov     [rbx+4], ecx
0x1800045e0  cmp     [rbx], r14d
0x1800045e3  jnz     loc_1800047FC
0x1800045e9  add     ecx, [rbx+8]
0x1800045ec  cmp     ecx, 7FFFFFFFh
0x1800045f2  jnb     loc_1800047B1
0x1800045f8  mov     rcx, rbx
0x1800045fb  call    GetStatus
0x180004600  movzx   edx, al
0x180004603  cmp     [rbx], r14d
0x180004606  jnz     loc_1800047FC
0x18000460c  cmp     dl, 80h
0x18000460f  jb      loc_18000483C
0x180004615  cmp     dl, 0F8h
0x180004618  ja      loc_1800046B3
0x18000461e  jz      loc_18000483C
0x180004624  mov     ecx, edx
0x180004626  sub     ecx, 0F1h
0x18000462c  jz      loc_18000483C
0x180004632  sub     ecx, 1
0x180004635  jz      loc_18000483C
0x18000463b  sub     ecx, 1
0x18000463e  jz      loc_18000483C
0x180004644  sub     ecx, 1
0x180004647  jz      loc_18000483C
0x18000464d  sub     ecx, 1
0x180004650  jz      loc_18000483C
0x180004656  cmp     ecx, 1
0x180004659  jz      loc_18000483C
0x18000465f  mov     sil, dl
0x180004662  mov     al, dl
0x180004664  and     sil, 0Fh
0x180004668  and     al, 0F0h
0x18000466a  cmp     al, 0C0h
0x18000466c  jnz     loc_180004717
0x180004672  mov     rcx, rbx
0x180004675  call    LookByte
0x18000467a  cmp     [rbx], r14d
0x18000467d  jnz     short loc_180004683
0x18000467f  inc     qword ptr [rbx+18h]
0x180004683  cmp     al, 80h
0x180004685  jnb     loc_1800047B1
0x18000468b  cmp     [rbx], r14d
0x18000468e  jnz     loc_1800047FC
0x180004694  movzx   edx, al
0x180004697  movzx   eax, sil
0x18000469b  movzx   ecx, word ptr [rdi+rdx*2+0C4h]
0x1800046a3  bts     ecx, eax
0x1800046a6  mov     [rdi+rdx*2+0C4h], cx
0x1800046ae  jmp     loc_1800047B1
0x1800046b3  mov     ecx, edx
0x1800046b5  sub     ecx, 0F9h
0x1800046bb  jz      loc_18000483C
0x1800046c1  sub     ecx, 1
0x1800046c4  jz      loc_18000483C
0x1800046ca  sub     ecx, 1
0x1800046cd  jz      loc_18000483C
0x1800046d3  sub     ecx, 1
0x1800046d6  jz      loc_18000483C
0x1800046dc  sub     ecx, 1
0x1800046df  jz      loc_18000483C
0x1800046e5  cmp     ecx, 1
0x1800046e8  jz      loc_18000483C
0x1800046ee  cmp     dl, 0FFh
0x1800046f1  jnz     loc_18000465F
0x1800046f7  mov     r8d, 4
0x1800046fd  mov     rdx, rbx
0x180004700  mov     rcx, rdi
0x180004703  call    HandleMetaEvent
0x180004708  test    eax, eax
0x18000470a  jnz     loc_1800047B1
0x180004710  xor     eax, eax
0x180004712  jmp     loc_180004831
0x180004717  cmp     al, 90h
0x180004719  jnz     short loc_180004776
0x18000471b  cmp     sil, 0Fh
0x18000471f  jz      short loc_180004727
0x180004721  cmp     sil, 9
0x180004725  jnz     short loc_180004776
0x180004727  mov     rcx, rbx
0x18000472a  call    LookByte
0x18000472f  cmp     [rbx], r14d
0x180004732  jnz     short loc_180004738
0x180004734  inc     qword ptr [rbx+18h]
0x180004738  cmp     al, 80h
0x18000473a  jnb     short loc_1800047B1
0x18000473c  cmp     [rbx], r14d
0x18000473f  jnz     loc_1800047FC
0x180004745  movzx   edx, al
0x180004748  movzx   eax, sil
0x18000474c  movzx   ecx, word ptr [rdi+rdx*2+1C4h]
0x180004754  bts     ecx, eax
0x180004757  mov     [rdi+rdx*2+1C4h], cx
0x18000475f  mov     rcx, rbx
0x180004762  call    LookByte
0x180004767  cmp     [rbx], r14d
0x18000476a  jnz     loc_1800047FC
0x180004770  inc     qword ptr [rbx+18h]
0x180004774  jmp     short loc_1800047B1
0x180004776  cmp     dl, 0F0h
0x180004779  jz      short loc_18000478B
0x18000477b  cmp     dl, 0F7h
0x18000477e  jz      short loc_18000478B
0x180004780  mov     cl, dl
0x180004782  call    MIDILength
0x180004787  dec     eax
0x180004789  jmp     short loc_180004793
0x18000478b  mov     rcx, rbx
0x18000478e  call    GetVarLen
0x180004793  cmp     [rbx], r14d
0x180004796  jnz     short loc_1800047FC
0x180004798  test    eax, eax
0x18000479a  jz      short loc_1800047B1
0x18000479c  mov     edx, eax
0x18000479e  mov     rcx, rbx
0x1800047a1  call    SkipBytes
0x1800047a6  cmp     [rbx], r14d
0x1800047a9  jz      short loc_1800047B6
0x1800047ab  mov     dword ptr [rbx], 117h
0x1800047b1  cmp     [rbx], r14d
0x1800047b4  jnz     short loc_1800047FC
0x1800047b6  cmp     [rbx+38h], r14d
0x1800047ba  jnz     short loc_1800047D3
0x1800047bc  mov     eax, [rbx+4]
0x1800047bf  add     [rbx+8], eax
0x1800047c2  cmp     dword ptr [rbx+8], 7FFFFFFFh
0x1800047c9  mov     [rbx+4], r14d
0x1800047cd  jb      loc_1800045C7
0x1800047d3  cmp     [rbx], r14d
0x1800047d6  jnz     short loc_1800047FC
0x1800047d8  mov     eax, [rbx+8]
0x1800047db  cmp     eax, [rdi+10h]
0x1800047de  jbe     short loc_1800047E3
0x1800047e0  mov     [rdi+10h], eax
0x1800047e3  mov     rbx, [rbx-10h]
0x1800047e7  test    rbx, rbx
0x1800047ea  jz      short loc_18000482C
0x1800047ec  add     rbx, 10h
0x1800047f0  jz      short loc_18000482C
0x1800047f2  mov     [rbx+0Ch], r14b
0x1800047f6  mov     [rbx+8], r14d
0x1800047fa  jmp     short loc_180004801
0x1800047fc  test    rbx, rbx
0x1800047ff  jz      short loc_18000482C
0x180004801  cmp     [rbx], r14d
0x180004804  jz      loc_1800045C7
0x18000480a  cmp     dword ptr [rbx], 15Eh
0x180004810  jnz     short loc_18000482C
0x180004812  mov     rax, [rbx+28h]
0x180004816  test    rax, rax
0x180004819  jz      loc_180004710
0x18000481f  mov     [rbx+18h], rax
0x180004823  mov     [rbx+4], ebp
0x180004826  mov     dword ptr [rbx], 111h
0x18000482c  mov     eax, 1
0x180004831  add     rsp, 20h
0x180004835  pop     r14
0x180004837  pop     rdi
0x180004838  pop     rsi
0x180004839  pop     rbp
0x18000483a  pop     rbx
0x18000483b  retn
0x18000483c  and     dword ptr [rdi+830h], 0FFFFFFFEh
0x180004843  jmp     short loc_18000482C
```
