# EtwEventWriteTransfer

- ea: `0x180085fe0`
- end: `0x18008631e`
- name: `EtwEventWriteTransfer`
- size: `830`
- prototype: `__int64 __fastcall(__int64, __int64, _GUID *, __int128 *, unsigned int, __int64)`
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x180013540`
- `0x180039580`
- `0x180047760`
- `0x1800853a8`
- `0x180089760`
- `0x180096a70`
- `0x1800a11d0`
- `0x1801041e0`
- `0x180117520`

## callees

- `0x1800369a0`
- `0x180085fe0`
- `0x1800866c0`
- `0x18015ee80`
- `0x180162000`

## pseudocode

```c
__int64 __fastcall EtwEventWriteTransfer(__int64 a1, __int64 a2, _GUID *a3, __int128 *a4, unsigned int a5, __int64 a6)
{
  __int64 v9; // rdx
  __int64 v10; // r9
  unsigned __int64 v12; // r8
  __int64 v13; // rbx
  unsigned int v14; // r9d
  unsigned __int8 v15; // al
  char v16; // si
  unsigned __int8 v17; // al
  _GUID ActivityId; // xmm0
  __int128 v19; // xmm0
  NTSTATUS v20; // eax
  unsigned int i; // edx
  __int64 v22; // rax
  __int64 v23; // r8
  _OWORD v24[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v25; // [rsp+70h] [rbp-90h]
  __int128 v26; // [rsp+80h] [rbp-80h]
  _GUID v27; // [rsp+90h] [rbp-70h]
  __int128 v28; // [rsp+A0h] [rbp-60h]
  __int128 v29; // [rsp+B0h] [rbp-50h]
  __int64 v30; // [rsp+C0h] [rbp-40h]
  __int128 v31; // [rsp+D0h] [rbp-30h] BYREF
  _OWORD v32[7]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v33; // [rsp+150h] [rbp+50h]

  v30 = 0;
  v33 = 0;
  memset(v24, 0, sizeof(v24));
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v31 = 0;
  memset(v32, 0, sizeof(v32));
  if ( a2 )
  {
    DWORD2(v25) = *(_DWORD *)a2;
    BYTE12(v25) = *(_BYTE *)(a2 + 4);
    *(_WORD *)((char *)&v25 + 13) = *(_WORD *)(a2 + 5);
    HIBYTE(v25) = *(_BYTE *)(a2 + 7);
    *(_QWORD *)&v26 = *(_QWORD *)(a2 + 8);
    v9 = ((unsigned int)a1 >> 1) & 7;
    v10 = qword_1801C62B0[v9];
    if ( ((v10 != 0 && (unsigned int)a1 >> 4 < dword_1801930E0[v9]) & (unsigned __int8)a1) == 0 )
      return 6;
    v12 = (unsigned __int64)(unsigned int)a1 >> 4;
    v13 = 0;
    if ( (*(_QWORD *)(v10 + 8 * v12) & 1) == 0 )
      v13 = *(_QWORD *)(v10 + 8 * v12);
    if ( !v13 || WORD2(a1) != *(_WORD *)(v13 + 84) )
      return 6;
    v14 = 0;
    if ( *(_BYTE *)(v13 + 236)
      && ((v15 = *(_BYTE *)(v13 + 237), BYTE12(v25) <= v15) || !v15)
      && ((*(_BYTE *)(v13 + 232) & 0x40) != 0 && !(_QWORD)v26
       || ((unsigned __int64)v26 & *(_QWORD *)(v13 + 224)) != 0
       && ((unsigned __int64)v26 & *(_QWORD *)(v13 + 216)) == *(_QWORD *)(v13 + 216)) )
    {
      v16 = 1;
      v14 = EtwpWriteToPrivateBuffers((_BYTE *)v13, (_OWORD *)a2, 0, 0, 0, a3, a4, a5, a6, (__int64)&v31);
      if ( v14 )
      {
LABEL_28:
        for ( i = 0; i < (unsigned int)v33; ++i )
        {
          v22 = 2LL * i;
          v23 = *(_QWORD *)&v32[v22 - 1];
          if ( v14 )
            *(_WORD *)(*((_QWORD *)&v31 + 4 * i + 1) + 2LL) = -16371;
          _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)&v32[v22] + 12LL));
          _InterlockedDecrement((volatile signed __int32 *)(16LL * *(unsigned int *)(v23 + 20) + EtwpLoggerArray + 8));
        }
        return v14;
      }
    }
    else
    {
      v16 = 0;
    }
    if ( *(_BYTE *)(v13 + 116) )
    {
      v17 = *(_BYTE *)(v13 + 117);
      if ( (BYTE12(v25) <= v17 || !v17)
        && ((*(_BYTE *)(v13 + 112) & 0x40) != 0 && !(_QWORD)v26
         || ((unsigned __int64)v26 & *(_QWORD *)(v13 + 104)) != 0
         && ((unsigned __int64)v26 & *(_QWORD *)(v13 + 96)) == *(_QWORD *)(v13 + 96)) )
      {
        DWORD1(v28) = a5;
        DWORD1(v24[0]) = 0;
        *((_QWORD *)&v28 + 1) = a6;
        if ( a3 )
          ActivityId = *a3;
        else
          ActivityId = NtCurrentTeb()->ActivityId;
        LOBYTE(v28) = 0;
        v27 = ActivityId;
        if ( a4 )
        {
          v19 = *a4;
          LOBYTE(v28) = 1;
          v29 = v19;
        }
        WORD1(v28) = 0;
        LODWORD(v30) = 0;
        v20 = NtTraceEvent(*(_QWORD *)(v13 + 88), 768, 120, v24);
        if ( v20 )
          v14 = RtlNtStatusToDosError(v20);
        else
          v14 = 0;
      }
    }
    if ( !v16 )
      return v14;
    goto LABEL_28;
  }
  return 87;
}

```

## disassembly

```asm
0x180085fe0  push    rbp
0x180085fe2  push    rdi
0x180085fe3  push    r12
0x180085fe5  push    r15
0x180085fe7  lea     rbp, [rsp-88h]
0x180085fef  sub     rsp, 188h
0x180085ff6  mov     rax, cs:__security_cookie
0x180085ffd  xor     rax, rsp
0x180086000  mov     [rbp+0A0h+var_40], rax
0x180086004  mov     r12, [rbp+0A0h+arg_28]
0x18008600b  xorps   xmm1, xmm1
0x18008600e  xorps   xmm0, xmm0
0x180086011  xor     eax, eax
0x180086013  mov     [rbp+0A0h+var_E0], rax
0x180086017  mov     rdi, r9
0x18008601a  mov     [rbp+0A0h+var_50], rax
0x18008601e  mov     r15, r8
0x180086021  mov     r11, rdx
0x180086024  mov     r10, rcx
0x180086027  movups  [rsp+1A0h+var_150], xmm0
0x18008602c  movups  [rsp+1A0h+var_140], xmm0
0x180086031  movups  [rsp+1A0h+var_130], xmm0
0x180086036  movups  [rbp+0A0h+var_120], xmm0
0x18008603a  movups  [rbp+0A0h+var_110], xmm0
0x18008603e  movups  [rbp+0A0h+var_100], xmm0
0x180086042  movups  [rbp+0A0h+var_F0], xmm0
0x180086046  movups  [rbp+0A0h+var_D0], xmm1
0x18008604a  movups  [rbp+0A0h+var_C0], xmm1
0x18008604e  movups  [rbp+0A0h+var_B0], xmm1
0x180086052  movups  [rbp+0A0h+var_A0], xmm1
0x180086056  movups  [rbp+0A0h+var_90], xmm1
0x18008605a  movups  [rbp+0A0h+var_80], xmm1
0x18008605e  movups  [rbp+0A0h+var_70], xmm1
0x180086062  movups  [rbp+0A0h+var_60], xmm1
0x180086066  test    rdx, rdx
0x180086069  jz      loc_180086305
0x18008606f  mov     eax, [rdx]
0x180086071  xor     ecx, ecx
0x180086073  mov     dword ptr [rsp+1A0h+var_130+8], eax
0x180086077  movzx   eax, byte ptr [rdx+4]
0x18008607b  mov     byte ptr [rsp+1A0h+var_130+0Ch], al
0x18008607f  movzx   eax, word ptr [rdx+5]
0x180086083  mov     word ptr [rsp+1A0h+var_130+0Dh], ax
0x180086088  movzx   eax, byte ptr [rdx+7]
0x18008608c  mov     byte ptr [rsp+1A0h+var_130+0Fh], al
0x180086090  mov     rax, [rdx+8]
0x180086094  mov     qword ptr [rbp+0A0h+var_120], rax
0x180086098  mov     eax, r10d
0x18008609b  shr     eax, 4
0x18008609e  mov     edx, r10d
0x1800860a1  shr     rdx, 1
0x1800860a4  and     edx, 7
0x1800860a7  mov     [rsp+1A0h+var_20], rbx
0x1800860af  lea     rbx, cs:180000000h
0x1800860b6  mov     r8d, r10d
0x1800860b9  mov     r9, rva qword_1801C62B0[rbx+rdx*8]
0x1800860c1  cmp     eax, ds:rva dword_1801930E0[rbx+rdx*4]
0x1800860c8  setb    cl
0x1800860cb  xor     eax, eax
0x1800860cd  test    r9, r9
0x1800860d0  setnz   al
0x1800860d3  and     ecx, eax
0x1800860d5  test    r10d, ecx
0x1800860d8  jnz     short loc_180086102
0x1800860da  mov     eax, 6
0x1800860df  mov     rbx, [rsp+1A0h+var_20]
0x1800860e7  mov     rcx, [rbp+0A0h+var_40]
0x1800860eb  xor     rcx, rsp; StackCookie
0x1800860ee  call    __security_check_cookie
0x1800860f3  add     rsp, 188h
0x1800860fa  pop     r15
0x1800860fc  pop     r12
0x1800860fe  pop     rdi
0x1800860ff  pop     rbp
0x180086100  retn
0x180086102  shr     r8, 4
0x180086106  mov     ebx, 0
0x18008610b  mov     rax, [r9+r8*8]
0x18008610f  test    al, 1
0x180086111  cmovz   rbx, rax
0x180086115  test    rbx, rbx
0x180086118  jz      short loc_1800860DA
0x18008611a  shr     r10, 20h
0x18008611e  cmp     r10w, [rbx+54h]
0x180086123  jnz     short loc_1800860DA
0x180086125  mov     [rsp+1A0h+var_30], r14
0x18008612d  xor     r9d, r9d
0x180086130  mov     r14d, [rbp+0A0h+arg_20]
0x180086137  mov     [rsp+1A0h+var_28], rsi
0x18008613f  cmp     [rbx+0ECh], r9b
0x180086146  jz      short loc_18008618E
0x180086148  movzx   eax, byte ptr [rbx+0EDh]
0x18008614f  cmp     byte ptr [rsp+1A0h+var_130+0Ch], al
0x180086153  ja      loc_1800862E2
0x180086159  test    byte ptr [rbx+0E8h], 40h
0x180086160  mov     rdx, qword ptr [rbp+0A0h+var_120]
0x180086164  jz      short loc_18008616F
0x180086166  test    rdx, rdx
0x180086169  jz      loc_18008629D
0x18008616f  test    [rbx+0E0h], rdx
0x180086176  jz      short loc_18008618E
0x180086178  mov     rcx, [rbx+0D8h]
0x18008617f  mov     rax, rcx
0x180086182  and     rax, rdx
0x180086185  cmp     rax, rcx
0x180086188  jz      loc_18008629D
0x18008618e  xor     sil, sil
0x180086191  cmp     byte ptr [rbx+74h], 0
0x180086195  jz      loc_180086237
0x18008619b  movzx   eax, byte ptr [rbx+75h]
0x18008619f  cmp     byte ptr [rsp+1A0h+var_130+0Ch], al
0x1800861a3  ja      loc_1800862EF
0x1800861a9  test    byte ptr [rbx+70h], 40h
0x1800861ad  mov     rdx, qword ptr [rbp+0A0h+var_120]
0x1800861b1  jz      short loc_1800861B8
0x1800861b3  test    rdx, rdx
0x1800861b6  jz      short loc_1800861CB
0x1800861b8  test    [rbx+68h], rdx
0x1800861bc  jz      short loc_180086237
0x1800861be  mov     rax, [rbx+60h]
0x1800861c2  and     rax, rdx
0x1800861c5  cmp     rax, [rbx+60h]
0x1800861c9  jnz     short loc_180086237
0x1800861cb  xor     eax, eax
0x1800861cd  mov     dword ptr [rbp+0A0h+var_100+4], r14d
0x1800861d1  mov     dword ptr [rsp+1A0h+var_150+4], eax
0x1800861d5  mov     qword ptr [rbp+0A0h+var_100+8], r12
0x1800861d9  test    r15, r15
0x1800861dc  jnz     loc_1800862FC
0x1800861e2  mov     rax, gs:30h
0x1800861eb  movups  xmm0, xmmword ptr [rax+1710h]
0x1800861f2  mov     byte ptr [rbp+0A0h+var_100], 0
0x1800861f6  movups  [rbp+0A0h+var_110], xmm0
0x1800861fa  test    rdi, rdi
0x1800861fd  jz      short loc_18008620A
0x1800861ff  movups  xmm0, xmmword ptr [rdi]
0x180086202  mov     byte ptr [rbp+0A0h+var_100], 1
0x180086206  movups  [rbp+0A0h+var_F0], xmm0
0x18008620a  xor     eax, eax
0x18008620c  lea     r9, [rsp+1A0h+var_150]
0x180086211  mov     word ptr [rbp+0A0h+var_100+2], ax
0x180086215  mov     edx, 300h
0x18008621a  mov     dword ptr [rbp+0A0h+var_E0], eax
0x18008621d  mov     r8d, 78h ; 'x'
0x180086223  mov     rcx, [rbx+58h]
0x180086227  call    NtTraceEvent
0x18008622c  test    eax, eax
0x18008622e  jnz     loc_18008630F
0x180086234  xor     r9d, r9d
0x180086237  test    sil, sil
0x18008623a  jz      short loc_180086285
0x18008623c  xor     edx, edx
0x18008623e  cmp     dword ptr [rbp+0A0h+var_50], edx
0x180086241  jbe     short loc_180086285
0x180086243  mov     eax, edx
0x180086245  shl     rax, 5
0x180086249  mov     r8, qword ptr [rbp+rax+0A0h+var_D0]
0x18008624e  test    r9d, r9d
0x180086251  jz      short loc_18008625E
0x180086253  mov     rcx, qword ptr [rbp+rax+0A0h+var_D0+8]
0x180086258  mov     word ptr [rcx+2], 0C00Dh
0x18008625e  lea     rcx, [rbp+0A0h+var_C0]
0x180086262  inc     edx
0x180086264  mov     rcx, [rcx+rax]
0x180086268  lock dec dword ptr [rcx+0Ch]
0x18008626c  mov     ecx, [r8+14h]
0x180086270  mov     rax, cs:EtwpLoggerArray
0x180086277  shl     rcx, 4
0x18008627b  lock dec dword ptr [rcx+rax+8]
0x180086280  cmp     edx, dword ptr [rbp+0A0h+var_50]
0x180086283  jb      short loc_180086243
0x180086285  mov     rsi, [rsp+1A0h+var_28]
0x18008628d  mov     eax, r9d
0x180086290  mov     r14, [rsp+1A0h+var_30]
0x180086298  jmp     loc_1800860DF
0x18008629d  lea     rcx, [rbp+0A0h+var_D0]
0x1800862a1  xor     eax, eax
0x1800862a3  mov     [rsp+1A0h+var_158], rcx
0x1800862a8  xor     r8d, r8d
0x1800862ab  mov     [rsp+1A0h+var_160], r12
0x1800862b0  mov     rdx, r11
0x1800862b3  mov     [rsp+1A0h+var_168], r14d
0x1800862b8  mov     rcx, rbx
0x1800862bb  mov     [rsp+1A0h+var_170], rdi
0x1800862c0  mov     sil, 1
0x1800862c3  mov     [rsp+1A0h+var_178], r15
0x1800862c8  mov     [rsp+1A0h+var_180], ax
0x1800862cd  call    EtwpWriteToPrivateBuffers
0x1800862d2  mov     r9d, eax
0x1800862d5  test    eax, eax
0x1800862d7  jnz     loc_18008623C
0x1800862dd  jmp     loc_180086191
0x1800862e2  test    al, al
0x1800862e4  jnz     loc_18008618E
0x1800862ea  jmp     loc_180086159
0x1800862ef  test    al, al
0x1800862f1  jnz     loc_180086237
0x1800862f7  jmp     loc_1800861A9
0x1800862fc  movups  xmm0, xmmword ptr [r15]
0x180086300  jmp     loc_1800861F2
0x180086305  mov     eax, 57h ; 'W'
0x18008630a  jmp     loc_1800860E7
0x18008630f  mov     ecx, eax; Status
0x180086311  call    RtlNtStatusToDosError
0x180086316  mov     r9d, eax
0x180086319  jmp     loc_180086237
```
