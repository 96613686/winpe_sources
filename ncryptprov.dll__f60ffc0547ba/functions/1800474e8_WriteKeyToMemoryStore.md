# WriteKeyToMemoryStore

- ea: `0x1800474e8`
- end: `0x180047a9a`
- name: `WriteKeyToMemoryStore`
- size: `1458`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18005038c`

## callees

- `0x18000af80`
- `0x18000d3d0`
- `0x18000def0`
- `0x1800128ac`
- `0x1800138f4`
- `0x1800202c4`
- `0x180021c70`
- `0x180023ef8`
- `0x1800398b0`
- `0x1800469e0`
- `0x18004722c`
- `0x1800474e8`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180047767`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180047767`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180047a2e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180047a2e`

## string_xrefs

- `0x180047537`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`
- `0x180047619`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`

## pseudocode

```c
__int64 __fastcall WriteKeyToMemoryStore(__int64 a1)
{
  void *v1; // r12
  int v2; // r13d
  _BYTE *v4; // r15
  unsigned int KeyInMemoryStore; // ebx
  __int64 v6; // r9
  __int64 v7; // rcx
  __int64 v8; // rdi
  _BYTE *v9; // rax
  int v10; // eax
  signed __int64 v11; // rsi
  unsigned int v12; // eax
  __int64 v13; // r9
  __int64 v14; // rcx
  size_t v15; // rbx
  void *v16; // rax
  void *v17; // rdx
  unsigned __int8 *v18; // rdi
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rcx
  signed __int64 v22; // rsi
  signed __int64 v23; // rsi
  signed __int64 v24; // rsi
  __int64 v25; // rsi
  __int64 v26; // rsi
  __int64 v27; // rsi
  __int64 v28; // rcx
  __int64 v29; // rbx
  char *v30; // r8
  char i; // cl
  unsigned __int64 v32; // rcx
  char v33; // dl
  __int64 v34; // rdi
  __int64 v35; // r10
  __int64 v36; // rsi
  _QWORD *v37; // r9
  __int64 v38; // rdx
  __int64 v39; // rcx
  __int64 v40; // rcx
  int v41; // eax
  __int64 v42; // rcx
  __int64 v43; // rdx
  __int64 v44; // rcx
  size_t Size; // [rsp+70h] [rbp+40h] BYREF
  void *Src; // [rsp+78h] [rbp+48h] BYREF
  size_t pcbLength; // [rsp+80h] [rbp+50h] BYREF

  v1 = 0;
  v2 = 0;
  Src = 0;
  LODWORD(Size) = 0;
  pcbLength = 0;
  if ( (unsigned int)g_ephemeralKeyTable >= 0x2000 )
  {
    v4 = 0;
    KeyInMemoryStore = 223;
    v6 = 1999;
LABEL_3:
    v7 = KeyInMemoryStore;
LABEL_4:
    DebugTraceError(v7, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c", v6);
    goto LABEL_65;
  }
  v8 = 200;
  v9 = (_BYTE *)SafeAllocaAllocateFromHeap(200);
  v4 = v9;
  if ( !v9 )
  {
    KeyInMemoryStore = 8;
    v6 = 2007;
    goto LABEL_3;
  }
  do
  {
    *v9++ = 0;
    --v8;
  }
  while ( v8 );
  v10 = StringCbLengthW(*(STRSAFE_PCNZWCH *)(a1 + 8), 0xFFFFFFFE, &pcbLength);
  KeyInMemoryStore = v10;
  if ( v10 < 0 )
  {
    v6 = 2016;
LABEL_10:
    v7 = (unsigned int)v10;
    goto LABEL_4;
  }
  v11 = pcbLength;
  if ( pcbLength + 2 > 0x9E )
  {
    KeyInMemoryStore = 87;
    v6 = 2023;
    goto LABEL_3;
  }
  memcpy_0(v4 + 24, *(const void **)(a1 + 8), pcbLength + 2);
  if ( !*(_QWORD *)(a1 + 240) )
  {
    v10 = ProtectPrivateKey(a1, (int)a1 + 240, (int)a1 + 248);
    KeyInMemoryStore = v10;
    if ( v10 )
    {
      v6 = 2042;
      goto LABEL_10;
    }
  }
  UpdateLastModifiedProperty(a1);
  v12 = SerializeKeyForStorage(a1, &Src, &Size);
  KeyInMemoryStore = v12;
  if ( v12 )
  {
    v13 = 2061;
    v14 = v12;
LABEL_18:
    DebugTraceError(v14, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c", v13);
    v1 = Src;
    goto LABEL_65;
  }
  v15 = (unsigned int)Size;
  v16 = (void *)SafeAllocaAllocateFromHeap((unsigned int)Size);
  *((_QWORD *)v4 + 23) = v16;
  if ( !v16 )
  {
    KeyInMemoryStore = 8;
    v13 = 2069;
    v14 = 8;
    goto LABEL_18;
  }
  v1 = Src;
  v17 = Src;
  *((_DWORD *)v4 + 48) = v15;
  memcpy_0(v16, v17, v15);
  v18 = *(unsigned __int8 **)(a1 + 8);
  v19 = 314159;
  while ( v11 >= 8 )
  {
    v20 = v18[7];
    v21 = 37
        * (v18[6]
         + 37 * (v18[5] + 37 * (v18[4] + 37 * (v18[3] + 37 * (v18[2] + 37 * (v18[1] + 37 * (*v18 + 37 * v19)))))));
    v18 += 8;
    v19 = v20 + v21;
    v11 -= 8LL;
  }
  v22 = v11 - 1;
  if ( v22 )
  {
    v23 = v22 - 1;
    if ( v23 )
    {
      v24 = v23 - 1;
      if ( v24 )
      {
        v25 = v24 - 1;
        if ( v25 )
        {
          v26 = v25 - 1;
          if ( v26 )
          {
            v27 = v26 - 1;
            if ( v27 )
            {
              if ( v27 != 1 )
                goto LABEL_38;
              v19 = *v18++ + 37 * v19;
            }
            v19 = *v18++ + 37 * v19;
          }
          v19 = *v18++ + 37 * v19;
        }
        v19 = *v18++ + 37 * v19;
      }
      v19 = *v18++ + 37 * v19;
    }
    v19 = *v18++ + 37 * v19;
  }
  v19 = *v18 + 37 * v19;
LABEL_38:
  *((_QWORD *)v4 + 1) = v19;
  RtlAcquireSRWLockExclusive(g_ephemeralKeyTableLock);
  v28 = (unsigned int)dword_18007A894 >> 5;
  LODWORD(pcbLength) = 0;
  LODWORD(Src) = 1;
  if ( g_ephemeralKeyTable < (unsigned int)(2 * v28) || (int)RtlULongLongToULong(2 * v28, &pcbLength) < 0 )
    goto LABEL_60;
  v29 = (unsigned int)pcbLength;
  if ( (unsigned int)pcbLength < 4 )
    v29 = 4;
  v30 = (char *)SafeAllocaAllocateFromHeap(8LL * (unsigned int)v29);
  if ( v30 )
  {
    if ( (((_DWORD)v29 - 1) & (unsigned int)v29) != 0 )
    {
      for ( i = -1; (_DWORD)v29; LODWORD(v29) = (unsigned int)v29 >> 1 )
        ++i;
      v29 = (unsigned int)(1 << i);
    }
    if ( (unsigned int)v29 > 0x4000000 )
      v29 = 0x4000000;
    v32 = (unsigned int)v29;
    if ( v30 > &v30[8 * v29] )
      v32 = 0;
    if ( v32 )
      memset64(v30, (unsigned __int64)&g_ephemeralKeyTable + 1, v32);
    v33 = dword_18007A894;
    v34 = 0;
    v35 = -1LL << (dword_18007A894 & 0x1F);
    if ( (dword_18007A894 & 0xFFFFFFE0) != 0 )
    {
      do
      {
        v36 = qword_18007A898;
        while ( 1 )
        {
          v37 = *(_QWORD **)(v36 + 8 * v34);
          if ( ((unsigned __int8)v37 & 1) != 0 )
            break;
          *(_QWORD *)(v36 + 8 * v34) = *v37;
          pcbLength = v35 & v37[1];
          v38 = ((_DWORD)v29 - 1)
              & (HIBYTE(pcbLength)
               + 37
               * (BYTE6(pcbLength)
                + 37
                * (BYTE5(pcbLength)
                 + 37
                 * (BYTE4(pcbLength)
                  + 37
                  * (BYTE3(pcbLength)
                   + 37
                   * (BYTE2(pcbLength)
                    + 37 * (BYTE1(pcbLength) + 37 * ((unsigned int)(unsigned __int8)pcbLength + 11623883))))))));
          *v37 = *(_QWORD *)&v30[8 * v38];
          *(_QWORD *)&v30[8 * v38] = v37;
        }
        v33 = dword_18007A894;
        v34 = (unsigned int)(v34 + 1);
      }
      while ( (unsigned int)v34 < (unsigned int)dword_18007A894 >> 5 );
    }
    v39 = qword_18007A898;
    qword_18007A898 = (__int64)v30;
    dword_18007A894 = v33 & 0x1F | (32 * v29);
    if ( v39 )
      MSCryptFree(v39);
    goto LABEL_60;
  }
  if ( (dword_18007A894 & 0xFFFFFFE0) != 0 )
  {
LABEL_60:
    KeyInMemoryStore = FindKeyInMemoryStore(a1, 0, 0);
    if ( KeyInMemoryStore == -2146893811 )
    {
      v40 = *(_QWORD *)(a1 + 224);
      KeyInMemoryStore = 0;
      if ( v40 )
        MSCryptFree(v40);
      v41 = Size;
      *(_QWORD *)(a1 + 224) = v1;
      v1 = 0;
      *(_DWORD *)(a1 + 232) = v41;
      _InterlockedIncrement64((volatile signed __int64 *)v4 + 2);
      Size = *((_QWORD *)v4 + 1) & (-1LL << (dword_18007A894 & 0x1F));
      v42 = qword_18007A898;
      v43 = (((unsigned int)dword_18007A894 >> 5) - 1)
          & (HIBYTE(Size)
           + 37
           * (BYTE6(Size)
            + 37
            * (BYTE5(Size)
             + 37
             * (BYTE4(Size)
              + 37 * (BYTE3(Size) + 37 * (BYTE2(Size) + 37 * (BYTE1(Size) + 37 * ((unsigned __int8)Size + 11623883))))))));
      *(_QWORD *)v4 = *(_QWORD *)(qword_18007A898 + 8 * v43);
      *(_QWORD *)(v42 + 8 * v43) = v4;
      ++g_ephemeralKeyTable;
      *(_QWORD *)(a1 + 576) = v4;
      v4 = 0;
    }
    goto LABEL_64;
  }
  KeyInMemoryStore = 8;
LABEL_64:
  v2 = (int)Src;
LABEL_65:
  EtwLogNCryptKeyWrite(
    *(_QWORD *)(a1 + 56),
    *(_QWORD *)(a1 + 8),
    (__int64)L"Memory store",
    *(_DWORD *)(a1 + 564),
    0,
    KeyInMemoryStore);
  if ( v2 == 1 )
    RtlReleaseSRWLockExclusive(g_ephemeralKeyTableLock);
  if ( v4 )
  {
    v44 = *((_QWORD *)v4 + 23);
    if ( v44 )
      MSCryptFree(v44);
    MSCryptFree(v4);
  }
  if ( v1 )
    MSCryptFree(v1);
  return KeyInMemoryStore;
}

```

## disassembly

```asm
0x1800474e8  mov     [rsp-38h+arg_18], rbx
0x1800474ed  push    rbp
0x1800474ee  push    rsi
0x1800474ef  push    rdi
0x1800474f0  push    r12
0x1800474f2  push    r13
0x1800474f4  push    r14
0x1800474f6  push    r15
0x1800474f8  mov     rbp, rsp
0x1800474fb  sub     rsp, 30h
0x1800474ff  xor     r12d, r12d
0x180047502  xor     r13d, r13d
0x180047505  cmp     cs:g_ephemeralKeyTable, 2000h
0x18004750f  mov     r14, rcx
0x180047512  mov     [rbp+Src], r12
0x180047516  mov     dword ptr [rbp+Size], r12d
0x18004751a  mov     [rbp+pcbLength], r12
0x18004751e  jb      short loc_180047548
0x180047520  xor     r15d, r15d
0x180047523  mov     ebx, 0DFh
0x180047528  mov     r9d, 7CFh
0x18004752e  mov     ecx, ebx
0x180047530  lea     rdx, aStatus; "Status"
0x180047537  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004753e  call    DebugTraceError
0x180047543  jmp     loc_1800479FA
0x180047548  mov     edi, 0C8h
0x18004754d  mov     ecx, edi
0x18004754f  call    SafeAllocaAllocateFromHeap
0x180047554  mov     r15, rax
0x180047557  test    rax, rax
0x18004755a  jnz     short loc_180047567
0x18004755c  lea     ebx, [rax+8]
0x18004755f  mov     r9d, 7D7h
0x180047565  jmp     short loc_18004752E
0x180047567  mov     [rax], r12b
0x18004756a  inc     rax
0x18004756d  sub     rdi, 1
0x180047571  jnz     short loc_180047567
0x180047573  mov     rcx, [r14+8]; psz
0x180047577  lea     r8, [rbp+pcbLength]; pcbLength
0x18004757b  mov     edx, 0FFFFFFFEh; cbMax
0x180047580  call    StringCbLengthW
0x180047585  mov     ebx, eax
0x180047587  test    eax, eax
0x180047589  jns     short loc_180047595
0x18004758b  mov     r9d, 7E0h
0x180047591  mov     ecx, eax
0x180047593  jmp     short loc_180047530
0x180047595  mov     rsi, [rbp+pcbLength]
0x180047599  lea     r8, [rsi+2]; Size
0x18004759d  cmp     r8, 9Eh
0x1800475a4  jbe     short loc_1800475B6
0x1800475a6  mov     ebx, 57h ; 'W'
0x1800475ab  mov     r9d, 7E7h
0x1800475b1  jmp     loc_18004752E
0x1800475b6  mov     rdx, [r14+8]; Src
0x1800475ba  lea     rcx, [r15+18h]; void *
0x1800475be  call    memcpy_0
0x1800475c3  lea     rdx, [r14+0F0h]
0x1800475ca  cmp     [rdx], r12
0x1800475cd  jnz     short loc_1800475EC
0x1800475cf  lea     r8, [r14+0F8h]
0x1800475d6  mov     rcx, r14
0x1800475d9  call    ProtectPrivateKey
0x1800475de  mov     ebx, eax
0x1800475e0  test    eax, eax
0x1800475e2  jz      short loc_1800475EC
0x1800475e4  mov     r9d, 7FAh
0x1800475ea  jmp     short loc_180047591
0x1800475ec  mov     rcx, r14
0x1800475ef  call    UpdateLastModifiedProperty
0x1800475f4  lea     r8, [rbp+Size]
0x1800475f8  mov     rcx, r14
0x1800475fb  lea     rdx, [rbp+Src]
0x1800475ff  call    SerializeKeyForStorage
0x180047604  mov     ebx, eax
0x180047606  test    eax, eax
0x180047608  jz      short loc_18004762E
0x18004760a  mov     r9d, 80Dh
0x180047610  mov     ecx, eax
0x180047612  lea     rdx, aStatus; "Status"
0x180047619  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180047620  call    DebugTraceError
0x180047625  mov     r12, [rbp+Src]
0x180047629  jmp     loc_1800479FA
0x18004762e  mov     ebx, dword ptr [rbp+Size]
0x180047631  mov     ecx, ebx
0x180047633  call    SafeAllocaAllocateFromHeap
0x180047638  mov     [r15+0B8h], rax
0x18004763f  test    rax, rax
0x180047642  jnz     short loc_180047651
0x180047644  lea     ebx, [rax+8]
0x180047647  mov     r9d, 815h
0x18004764d  mov     ecx, ebx
0x18004764f  jmp     short loc_180047612
0x180047651  mov     r12, [rbp+Src]
0x180047655  mov     r8, rbx; Size
0x180047658  mov     rdx, r12; Src
0x18004765b  mov     [r15+0C0h], ebx
0x180047662  mov     rcx, rax; void *
0x180047665  call    memcpy_0
0x18004766a  mov     rdi, [r14+8]
0x18004766e  mov     ecx, 4CB2Fh
0x180047673  jmp     short loc_1800476D4
0x180047675  movzx   eax, byte ptr [rdi]
0x180047678  imul    rcx, 25h ; '%'
0x18004767c  add     rcx, rax
0x18004767f  movzx   eax, byte ptr [rdi+1]
0x180047683  imul    rdx, rcx, 25h ; '%'
0x180047687  add     rdx, rax
0x18004768a  movzx   eax, byte ptr [rdi+2]
0x18004768e  imul    rcx, rdx, 25h ; '%'
0x180047692  add     rcx, rax
0x180047695  movzx   eax, byte ptr [rdi+3]
0x180047699  imul    rdx, rcx, 25h ; '%'
0x18004769d  add     rdx, rax
0x1800476a0  movzx   eax, byte ptr [rdi+4]
0x1800476a4  imul    rcx, rdx, 25h ; '%'
0x1800476a8  add     rcx, rax
0x1800476ab  movzx   eax, byte ptr [rdi+5]
0x1800476af  imul    rdx, rcx, 25h ; '%'
0x1800476b3  add     rdx, rax
0x1800476b6  movzx   eax, byte ptr [rdi+6]
0x1800476ba  imul    rcx, rdx, 25h ; '%'
0x1800476be  add     rcx, rax
0x1800476c1  movzx   eax, byte ptr [rdi+7]
0x1800476c5  imul    rcx, 25h ; '%'
0x1800476c9  add     rdi, 8
0x1800476cd  add     rcx, rax
0x1800476d0  sub     rsi, 8
0x1800476d4  cmp     rsi, 8
0x1800476d8  jge     short loc_180047675
0x1800476da  sub     rsi, 1
0x1800476de  jz      short loc_180047752
0x1800476e0  sub     rsi, 1
0x1800476e4  jz      short loc_180047745
0x1800476e6  sub     rsi, 1
0x1800476ea  jz      short loc_180047738
0x1800476ec  sub     rsi, 1
0x1800476f0  jz      short loc_18004772B
0x1800476f2  sub     rsi, 1
0x1800476f6  jz      short loc_18004771E
0x1800476f8  sub     rsi, 1
0x1800476fc  jz      short loc_180047711
0x1800476fe  cmp     rsi, 1
0x180047702  jnz     short loc_18004775C
0x180047704  movzx   eax, byte ptr [rdi]
0x180047707  imul    rcx, 25h ; '%'
0x18004770b  add     rcx, rax
0x18004770e  inc     rdi
0x180047711  movzx   eax, byte ptr [rdi]
0x180047714  imul    rcx, 25h ; '%'
0x180047718  add     rcx, rax
0x18004771b  inc     rdi
0x18004771e  movzx   eax, byte ptr [rdi]
0x180047721  imul    rcx, 25h ; '%'
0x180047725  add     rcx, rax
0x180047728  inc     rdi
0x18004772b  movzx   eax, byte ptr [rdi]
0x18004772e  imul    rcx, 25h ; '%'
0x180047732  add     rcx, rax
0x180047735  inc     rdi
0x180047738  movzx   eax, byte ptr [rdi]
0x18004773b  imul    rcx, 25h ; '%'
0x18004773f  add     rcx, rax
0x180047742  inc     rdi
0x180047745  movzx   eax, byte ptr [rdi]
0x180047748  imul    rcx, 25h ; '%'
0x18004774c  add     rcx, rax
0x18004774f  inc     rdi
0x180047752  movzx   eax, byte ptr [rdi]
0x180047755  imul    rcx, 25h ; '%'
0x180047759  add     rcx, rax
0x18004775c  mov     [r15+8], rcx
0x180047760  lea     rcx, g_ephemeralKeyTableLock
0x180047767  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18004776e  nop     dword ptr [rax+rax+00h]
0x180047773  mov     ecx, cs:dword_18007A894
0x180047779  shr     ecx, 5
0x18004777c  mov     dword ptr [rbp+pcbLength], r13d
0x180047780  or      r13, 0FFFFFFFFFFFFFFFFh
0x180047784  mov     dword ptr [rbp+Src], 1
0x18004778b  lea     eax, [rcx+rcx]
0x18004778e  cmp     cs:g_ephemeralKeyTable, eax
0x180047794  jb      loc_180047914
0x18004779a  add     rcx, rcx
0x18004779d  lea     rdx, [rbp+pcbLength]
0x1800477a1  call    RtlULongLongToULong
0x1800477a6  test    eax, eax
0x1800477a8  js      loc_180047914
0x1800477ae  mov     ebx, dword ptr [rbp+pcbLength]
0x1800477b1  lea     eax, [r13+5]
0x1800477b5  cmp     ebx, eax
0x1800477b7  cmovb   ebx, eax
0x1800477ba  mov     ecx, ebx
0x1800477bc  shl     rcx, 3
0x1800477c0  call    SafeAllocaAllocateFromHeap
0x1800477c5  mov     r8, rax
0x1800477c8  test    rax, rax
0x1800477cb  jz      loc_180047A80
0x1800477d1  lea     ecx, [rbx-1]
0x1800477d4  test    ebx, ecx
0x1800477d6  jz      short loc_1800477EC
0x1800477d8  or      ecx, 0FFFFFFFFh
0x1800477db  test    ebx, ebx
0x1800477dd  jz      short loc_1800477E5
0x1800477df  inc     ecx
0x1800477e1  shr     ebx, 1
0x1800477e3  jnz     short loc_1800477DF
0x1800477e5  mov     ebx, 1
0x1800477ea  shl     ebx, cl
0x1800477ec  mov     eax, 4000000h
0x1800477f1  cmp     ebx, eax
0x1800477f3  cmova   ebx, eax
0x1800477f6  xor     edx, edx
0x1800477f8  lea     rax, g_ephemeralKeyTable
0x1800477ff  mov     ecx, ebx
0x180047801  or      rax, 1
0x180047805  lea     rdi, [r8+rbx*8]
0x180047809  cmp     r8, rdi
0x18004780c  cmova   ecx, edx
0x18004780f  test    rcx, rcx
0x180047812  jz      short loc_18004781A
0x180047814  mov     rdi, r8
0x180047817  rep stosq
0x18004781a  mov     edx, cs:dword_18007A894
0x180047820  mov     r10, r13
0x180047823  mov     ecx, edx
0x180047825  xor     edi, edi
0x180047827  and     ecx, 1Fh
0x18004782a  shl     r10, cl
0x18004782d  test    edx, 0FFFFFFE0h
0x180047833  jbe     loc_1800478EE
0x180047839  mov     rsi, cs:qword_18007A898
0x180047840  mov     r9, [rsi+rdi*8]
0x180047844  test    r9b, 1
0x180047848  jnz     loc_1800478D9
0x18004784e  mov     rax, [r9]
0x180047851  lea     rdx, [rbp+pcbLength]
0x180047855  mov     [rsi+rdi*8], rax
0x180047859  mov     rax, [r9+8]
0x18004785d  and     rax, r10
0x180047860  mov     [rbp+pcbLength], rax
0x180047864  movzx   eax, byte ptr [rdx]
0x180047867  add     eax, 0B15DCBh
0x18004786c  imul    ecx, eax, 25h ; '%'
0x18004786f  movzx   eax, byte ptr [rdx+1]
0x180047873  add     ecx, eax
0x180047875  lea     rax, [rbp+pcbLength]
0x180047879  movzx   eax, byte ptr [rax+2]
0x18004787d  imul    edx, ecx, 25h ; '%'
0x180047880  add     edx, eax
0x180047882  lea     rax, [rbp+pcbLength]
0x180047886  movzx   eax, byte ptr [rax+3]
0x18004788a  imul    ecx, edx, 25h ; '%'
0x18004788d  add     ecx, eax
0x18004788f  lea     rax, [rbp+pcbLength]
0x180047893  movzx   eax, byte ptr [rax+4]
0x180047897  imul    edx, ecx, 25h ; '%'
0x18004789a  add     edx, eax
0x18004789c  lea     rax, [rbp+pcbLength]
0x1800478a0  movzx   eax, byte ptr [rax+5]
0x1800478a4  imul    ecx, edx, 25h ; '%'
0x1800478a7  add     ecx, eax
0x1800478a9  lea     rax, [rbp+pcbLength]
0x1800478ad  movzx   eax, byte ptr [rax+6]
0x1800478b1  imul    edx, ecx, 25h ; '%'
0x1800478b4  lea     ecx, [rbx-1]
0x1800478b7  add     edx, eax
0x1800478b9  lea     rax, [rbp+pcbLength]
0x1800478bd  movzx   eax, byte ptr [rax+7]
0x1800478c1  imul    edx, 25h ; '%'
0x1800478c4  add     edx, eax
0x1800478c6  and     rdx, rcx
0x1800478c9  mov     rax, [r8+rdx*8]
0x1800478cd  mov     [r9], rax
0x1800478d0  mov     [r8+rdx*8], r9
0x1800478d4  jmp     loc_180047840
0x1800478d9  mov     edx, cs:dword_18007A894
0x1800478df  inc     edi
0x1800478e1  mov     eax, edx
0x1800478e3  shr     eax, 5
0x1800478e6  cmp     edi, eax
0x1800478e8  jb      loc_180047839
0x1800478ee  mov     rcx, cs:qword_18007A898
0x1800478f5  and     edx, 1Fh
0x1800478f8  shl     ebx, 5
0x1800478fb  or      ebx, edx
0x1800478fd  mov     cs:qword_18007A898, r8
0x180047904  mov     cs:dword_18007A894, ebx
0x18004790a  test    rcx, rcx
0x18004790d  jz      short loc_180047914
0x18004790f  call    MSCryptFree
0x180047914  xor     r8d, r8d
0x180047917  xor     edx, edx
0x180047919  mov     rcx, r14
0x18004791c  call    FindKeyInMemoryStore
0x180047921  mov     ebx, eax
0x180047923  cmp     eax, 8009000Dh
  ... truncated ...
```
