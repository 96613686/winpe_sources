# EtwEventWriteTransfer

- ea: `0x180092440`
- end: `0x18009277e`
- name: `EtwEventWriteTransfer`
- size: `830`
- prototype: ``
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x180013540`
- `0x180047a10`
- `0x180047de0`
- `0x180064360`
- `0x180091808`
- `0x180095bc0`
- `0x1800a2840`
- `0x1800a9ba0`
- `0x180105010`

## callees

- `0x180035b00`
- `0x180092440`
- `0x180092b20`
- `0x18015f690`
- `0x180162810`

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
    v10 = qword_1801C62A0[v9];
    if ( ((v10 != 0 && (unsigned int)a1 >> 4 < dword_1801934D0[v9]) & (unsigned __int8)a1) == 0 )
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
0x180092440  push    rbp
0x180092442  push    rdi
0x180092443  push    r12
0x180092445  push    r15
0x180092447  lea     rbp, [rsp-88h]
0x18009244f  sub     rsp, 188h
0x180092456  mov     rax, cs:__security_cookie
0x18009245d  xor     rax, rsp
0x180092460  mov     [rbp+0A0h+var_40], rax
0x180092464  mov     r12, [rbp+0A0h+arg_28]
0x18009246b  xorps   xmm1, xmm1
0x18009246e  xorps   xmm0, xmm0
0x180092471  xor     eax, eax
0x180092473  mov     [rbp+0A0h+var_E0], rax
0x180092477  mov     rdi, r9
0x18009247a  mov     [rbp+0A0h+var_50], rax
0x18009247e  mov     r15, r8
0x180092481  mov     r11, rdx
0x180092484  mov     r10, rcx
0x180092487  movups  [rsp+1A0h+var_150], xmm0
0x18009248c  movups  [rsp+1A0h+var_140], xmm0
0x180092491  movups  [rsp+1A0h+var_130], xmm0
0x180092496  movups  [rbp+0A0h+var_120], xmm0
0x18009249a  movups  [rbp+0A0h+var_110], xmm0
0x18009249e  movups  [rbp+0A0h+var_100], xmm0
0x1800924a2  movups  [rbp+0A0h+var_F0], xmm0
0x1800924a6  movups  [rbp+0A0h+var_D0], xmm1
0x1800924aa  movups  [rbp+0A0h+var_C0], xmm1
0x1800924ae  movups  [rbp+0A0h+var_B0], xmm1
0x1800924b2  movups  [rbp+0A0h+var_A0], xmm1
0x1800924b6  movups  [rbp+0A0h+var_90], xmm1
0x1800924ba  movups  [rbp+0A0h+var_80], xmm1
0x1800924be  movups  [rbp+0A0h+var_70], xmm1
0x1800924c2  movups  [rbp+0A0h+var_60], xmm1
0x1800924c6  test    rdx, rdx
0x1800924c9  jz      loc_180092765
0x1800924cf  mov     eax, [rdx]
0x1800924d1  xor     ecx, ecx
0x1800924d3  mov     dword ptr [rsp+1A0h+var_130+8], eax
0x1800924d7  movzx   eax, byte ptr [rdx+4]
0x1800924db  mov     byte ptr [rsp+1A0h+var_130+0Ch], al
0x1800924df  movzx   eax, word ptr [rdx+5]
0x1800924e3  mov     word ptr [rsp+1A0h+var_130+0Dh], ax
0x1800924e8  movzx   eax, byte ptr [rdx+7]
0x1800924ec  mov     byte ptr [rsp+1A0h+var_130+0Fh], al
0x1800924f0  mov     rax, [rdx+8]
0x1800924f4  mov     qword ptr [rbp+0A0h+var_120], rax
0x1800924f8  mov     eax, r10d
0x1800924fb  shr     eax, 4
0x1800924fe  mov     edx, r10d
0x180092501  shr     rdx, 1
0x180092504  and     edx, 7
0x180092507  mov     [rsp+1A0h+var_20], rbx
0x18009250f  lea     rbx, cs:180000000h
0x180092516  mov     r8d, r10d
0x180092519  mov     r9, rva qword_1801C62A0[rbx+rdx*8]
0x180092521  cmp     eax, ds:rva dword_1801934D0[rbx+rdx*4]
0x180092528  setb    cl
0x18009252b  xor     eax, eax
0x18009252d  test    r9, r9
0x180092530  setnz   al
0x180092533  and     ecx, eax
0x180092535  test    r10d, ecx
0x180092538  jnz     short loc_180092562
0x18009253a  mov     eax, 6
0x18009253f  mov     rbx, [rsp+1A0h+var_20]
0x180092547  mov     rcx, [rbp+0A0h+var_40]
0x18009254b  xor     rcx, rsp; StackCookie
0x18009254e  call    __security_check_cookie
0x180092553  add     rsp, 188h
0x18009255a  pop     r15
0x18009255c  pop     r12
0x18009255e  pop     rdi
0x18009255f  pop     rbp
0x180092560  retn
0x180092562  shr     r8, 4
0x180092566  mov     ebx, 0
0x18009256b  mov     rax, [r9+r8*8]
0x18009256f  test    al, 1
0x180092571  cmovz   rbx, rax
0x180092575  test    rbx, rbx
0x180092578  jz      short loc_18009253A
0x18009257a  shr     r10, 20h
0x18009257e  cmp     r10w, [rbx+54h]
0x180092583  jnz     short loc_18009253A
0x180092585  mov     [rsp+1A0h+var_30], r14
0x18009258d  xor     r9d, r9d
0x180092590  mov     r14d, [rbp+0A0h+arg_20]
0x180092597  mov     [rsp+1A0h+var_28], rsi
0x18009259f  cmp     [rbx+0ECh], r9b
0x1800925a6  jz      short loc_1800925EE
0x1800925a8  movzx   eax, byte ptr [rbx+0EDh]
0x1800925af  cmp     byte ptr [rsp+1A0h+var_130+0Ch], al
0x1800925b3  ja      loc_180092742
0x1800925b9  test    byte ptr [rbx+0E8h], 40h
0x1800925c0  mov     rdx, qword ptr [rbp+0A0h+var_120]
0x1800925c4  jz      short loc_1800925CF
0x1800925c6  test    rdx, rdx
0x1800925c9  jz      loc_1800926FD
0x1800925cf  test    [rbx+0E0h], rdx
0x1800925d6  jz      short loc_1800925EE
0x1800925d8  mov     rcx, [rbx+0D8h]
0x1800925df  mov     rax, rcx
0x1800925e2  and     rax, rdx
0x1800925e5  cmp     rax, rcx
0x1800925e8  jz      loc_1800926FD
0x1800925ee  xor     sil, sil
0x1800925f1  cmp     byte ptr [rbx+74h], 0
0x1800925f5  jz      loc_180092697
0x1800925fb  movzx   eax, byte ptr [rbx+75h]
0x1800925ff  cmp     byte ptr [rsp+1A0h+var_130+0Ch], al
0x180092603  ja      loc_18009274F
0x180092609  test    byte ptr [rbx+70h], 40h
0x18009260d  mov     rdx, qword ptr [rbp+0A0h+var_120]
0x180092611  jz      short loc_180092618
0x180092613  test    rdx, rdx
0x180092616  jz      short loc_18009262B
0x180092618  test    [rbx+68h], rdx
0x18009261c  jz      short loc_180092697
0x18009261e  mov     rax, [rbx+60h]
0x180092622  and     rax, rdx
0x180092625  cmp     rax, [rbx+60h]
0x180092629  jnz     short loc_180092697
0x18009262b  xor     eax, eax
0x18009262d  mov     dword ptr [rbp+0A0h+var_100+4], r14d
0x180092631  mov     dword ptr [rsp+1A0h+var_150+4], eax
0x180092635  mov     qword ptr [rbp+0A0h+var_100+8], r12
0x180092639  test    r15, r15
0x18009263c  jnz     loc_18009275C
0x180092642  mov     rax, gs:30h
0x18009264b  movups  xmm0, xmmword ptr [rax+1710h]
0x180092652  mov     byte ptr [rbp+0A0h+var_100], 0
0x180092656  movups  [rbp+0A0h+var_110], xmm0
0x18009265a  test    rdi, rdi
0x18009265d  jz      short loc_18009266A
0x18009265f  movups  xmm0, xmmword ptr [rdi]
0x180092662  mov     byte ptr [rbp+0A0h+var_100], 1
0x180092666  movups  [rbp+0A0h+var_F0], xmm0
0x18009266a  xor     eax, eax
0x18009266c  lea     r9, [rsp+1A0h+var_150]
0x180092671  mov     word ptr [rbp+0A0h+var_100+2], ax
0x180092675  mov     edx, 300h
0x18009267a  mov     dword ptr [rbp+0A0h+var_E0], eax
0x18009267d  mov     r8d, 78h ; 'x'
0x180092683  mov     rcx, [rbx+58h]
0x180092687  call    NtTraceEvent
0x18009268c  test    eax, eax
0x18009268e  jnz     loc_18009276F
0x180092694  xor     r9d, r9d
0x180092697  test    sil, sil
0x18009269a  jz      short loc_1800926E5
0x18009269c  xor     edx, edx
0x18009269e  cmp     dword ptr [rbp+0A0h+var_50], edx
0x1800926a1  jbe     short loc_1800926E5
0x1800926a3  mov     eax, edx
0x1800926a5  shl     rax, 5
0x1800926a9  mov     r8, qword ptr [rbp+rax+0A0h+var_D0]
0x1800926ae  test    r9d, r9d
0x1800926b1  jz      short loc_1800926BE
0x1800926b3  mov     rcx, qword ptr [rbp+rax+0A0h+var_D0+8]
0x1800926b8  mov     word ptr [rcx+2], 0C00Dh
0x1800926be  lea     rcx, [rbp+0A0h+var_C0]
0x1800926c2  inc     edx
0x1800926c4  mov     rcx, [rcx+rax]
0x1800926c8  lock dec dword ptr [rcx+0Ch]
0x1800926cc  mov     ecx, [r8+14h]
0x1800926d0  mov     rax, cs:EtwpLoggerArray
0x1800926d7  shl     rcx, 4
0x1800926db  lock dec dword ptr [rcx+rax+8]
0x1800926e0  cmp     edx, dword ptr [rbp+0A0h+var_50]
0x1800926e3  jb      short loc_1800926A3
0x1800926e5  mov     rsi, [rsp+1A0h+var_28]
0x1800926ed  mov     eax, r9d
0x1800926f0  mov     r14, [rsp+1A0h+var_30]
0x1800926f8  jmp     loc_18009253F
0x1800926fd  lea     rcx, [rbp+0A0h+var_D0]
0x180092701  xor     eax, eax
0x180092703  mov     [rsp+1A0h+var_158], rcx
0x180092708  xor     r8d, r8d
0x18009270b  mov     [rsp+1A0h+var_160], r12
0x180092710  mov     rdx, r11
0x180092713  mov     [rsp+1A0h+var_168], r14d
0x180092718  mov     rcx, rbx
0x18009271b  mov     [rsp+1A0h+var_170], rdi
0x180092720  mov     sil, 1
0x180092723  mov     [rsp+1A0h+var_178], r15
0x180092728  mov     [rsp+1A0h+var_180], ax
0x18009272d  call    EtwpWriteToPrivateBuffers
0x180092732  mov     r9d, eax
0x180092735  test    eax, eax
0x180092737  jnz     loc_18009269C
0x18009273d  jmp     loc_1800925F1
0x180092742  test    al, al
0x180092744  jnz     loc_1800925EE
0x18009274a  jmp     loc_1800925B9
0x18009274f  test    al, al
0x180092751  jnz     loc_180092697
0x180092757  jmp     loc_180092609
0x18009275c  movups  xmm0, xmmword ptr [r15]
0x180092760  jmp     loc_180092652
0x180092765  mov     eax, 57h ; 'W'
0x18009276a  jmp     loc_180092547
0x18009276f  mov     ecx, eax; Status
0x180092771  call    RtlNtStatusToDosError
0x180092776  mov     r9d, eax
0x180092779  jmp     loc_180092697
```
