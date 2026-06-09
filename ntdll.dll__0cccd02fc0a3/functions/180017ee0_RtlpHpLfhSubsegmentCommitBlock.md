# RtlpHpLfhSubsegmentCommitBlock

- ea: `0x180017ee0`
- end: `0x180018390`
- name: `RtlpHpLfhSubsegmentCommitBlock`
- size: `1200`
- prototype: ``
- caller_count: `5`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180039580`
- `0x180089760`
- `0x180096a70`
- `0x1800a11d0`
- `0x1800d3bac`

## callees

- `0x180017e90`
- `0x180017ee0`
- `0x1800183a0`
- `0x180031200`
- `0x180071890`
- `0x1800e4a94`
- `0x18016f020`

## pseudocode

```c
__int64 __fastcall RtlpHpLfhSubsegmentCommitBlock(unsigned __int64 a1, unsigned __int64 a2, unsigned int a3)
{
  char v3; // cl
  unsigned int v4; // ebp
  __int64 v5; // rax
  unsigned int v6; // r14d
  int v7; // r15d
  __int64 v8; // r8
  signed __int16 *v10; // rbx
  int v11; // esi
  int v12; // r13d
  signed __int16 *v13; // r12
  unsigned __int64 v14; // r14
  signed __int16 v15; // ax
  signed __int16 v16; // tt
  unsigned int v17; // r14d
  unsigned __int64 v18; // r10
  signed __int64 v19; // rcx
  unsigned __int64 v21; // rcx
  __int64 v22; // rbp
  char v23; // cl
  unsigned int v24; // esi
  unsigned int v25; // r15d
  int v26; // eax
  signed __int64 v27; // rcx
  unsigned int v28; // ebx
  bool v29; // sf
  __int64 v30; // rax
  unsigned __int64 v31; // r10
  __int64 v32; // rdx
  _WORD *v33; // r8
  __int64 v34; // rbx
  int v35; // eax
  int v36; // edx
  _WORD *v37; // r9
  int v38; // eax
  __int16 v39; // tt
  char v40; // al
  __int64 v41; // r14
  char *v42; // rax
  int v43; // r8d
  char *v44; // rdx
  signed __int16 v45; // cx
  signed __int64 v46; // rcx
  unsigned __int64 v47; // rcx
  int v48; // [rsp+30h] [rbp-58h]
  unsigned int v50; // [rsp+98h] [rbp+10h]
  int v51; // [rsp+A0h] [rbp+18h] BYREF
  unsigned int v52; // [rsp+A8h] [rbp+20h]

  v3 = *(_BYTE *)(a2 + 38);
  v4 = a3 - 1;
  v5 = *(unsigned __int8 *)(a2 + 24);
  v6 = a3 >> 12;
  v7 = 0;
  v51 = 0;
  v8 = a3 >> 12 >> v3;
  v52 = v6;
  v10 = (signed __int16 *)(a2 + 8 * v5 + 2 * v8);
  _m_prefetchw(v10);
  v11 = 0;
  v12 = -1;
  v48 = 0;
  v50 = (((unsigned __int16)qword_1801C5EC8 ^ (unsigned __int16)(a2 >> 12) ^ *(unsigned __int16 *)(a2 + 40)) + v4) >> 12;
  v13 = &v10[(v50 >> v3) - (unsigned int)v8 + 1];
  if ( v10 >= v13 )
    return 0;
  v14 = a2 + 8 * v5;
  do
  {
    while ( 1 )
    {
      v15 = *v10;
      while ( v15 > 0 )
      {
        v16 = v15;
        v15 = _InterlockedCompareExchange16(v10, v15 + 1, v15);
        if ( v16 == v15 )
          goto LABEL_6;
      }
      if ( v7 )
        break;
      v7 = 1;
      RtlAcquireSRWLockExclusive(a2 + 56);
    }
    if ( v15 )
    {
      ++v11;
      v22 = (__int64)((__int64)v10 - v14) >> 1;
      v48 = v22;
      if ( v12 == -1 )
        v12 = v22;
    }
    else
    {
      --v11;
    }
    *v10 = v15 + 1;
LABEL_6:
    ++v10;
  }
  while ( v10 < v13 );
  v17 = v52;
  v18 = a1;
  if ( v11 )
  {
    v19 = (v11 << 12 << *(_BYTE *)(a2 + 38)) / 4096;
    _InterlockedAdd64((volatile signed __int64 *)(*(__int16 *)(a1 + 66) + a1 + 24), v19);
    if ( v19 > 0 )
    {
      v21 = (unsigned __int64)*(unsigned __int16 *)(a2 + 44) << 6;
      if ( !*(_BYTE *)(v21 + a1 + 92) )
      {
        *(_BYTE *)(v21 + a1 + 92) = 1;
        if ( !(_DWORD)qword_1801C6280
          && qword_1801C6270
          && !byte_1801CA908
          && !_InterlockedCompareExchange((volatile signed __int32 *)&qword_1801C6280, 1, 0) )
        {
          TpSetTimerEx(qword_1801C6270, &qword_1801C6278, 0, 1000);
          if ( (RtlpHpHeapFeatures & 0x10) != 0 )
            RtlpHpTlLogGCScheduled();
          v18 = a1;
        }
      }
    }
  }
  if ( v12 == -1 )
  {
    if ( v7 )
      RtlReleaseSRWLockExclusive(a2 + 56);
    return 0;
  }
  v23 = *(_BYTE *)(a2 + 38);
  v24 = v12 << 12 << v23;
  v25 = (v48 - v12 + 1) << 12 << v23;
  v26 = ((__int64 (__fastcall *)(_QWORD, unsigned __int64, _QWORD, int *))(v18
                                                                         ^ RtlpHpHeapGlobals
                                                                         ^ *(_QWORD *)(v18 + 24)))(
          *(_QWORD *)v18,
          a2 + v24,
          v25,
          &v51);
  LODWORD(v27) = *(unsigned __int8 *)(a2 + 38);
  v28 = v26;
  v29 = v26 < 0;
  v30 = *(unsigned __int8 *)(a2 + 24);
  if ( !v29 )
  {
    v31 = a2 + 8 * v30;
    v32 = v24 >> 12 >> v27;
    v33 = (_WORD *)(v31 + 2 * v32);
    _m_prefetchw(v33);
    LODWORD(v34) = -1;
    v35 = ((v25 + v24 - 1) >> 12 >> v27) - v32;
    v36 = 0;
    v37 = &v33[v35 + 1];
    if ( v33 >= v37 )
      goto LABEL_38;
    do
    {
      v38 = (unsigned __int16)*v33;
      while ( (__int16)v38 > 0 )
      {
        LODWORD(v27) = v38 + 1;
        v39 = v38;
        LOWORD(v38) = _InterlockedCompareExchange16(v33, v38 + 1, v38);
        if ( v39 == (_WORD)v38 )
          goto LABEL_34;
      }
      if ( (_WORD)v38 )
      {
        ++v36;
        if ( (_DWORD)v34 == -1 )
          v34 = (__int64)((__int64)v33 - v31) >> 1;
      }
      else
      {
        --v36;
      }
      *v33 = v38 + 1;
LABEL_34:
      ++v33;
    }
    while ( v33 < v37 );
    if ( v36 )
    {
      v27 = (v36 << 12 << *(_BYTE *)(a2 + 38)) / 4096;
      _InterlockedAdd64((volatile signed __int64 *)(*(__int16 *)(a1 + 66) + a1 + 24), v27);
      if ( v27 > 0 )
      {
        v27 = (unsigned __int64)*(unsigned __int16 *)(a2 + 44) << 6;
        if ( !*(_BYTE *)(v27 + a1 + 92) )
        {
          *(_BYTE *)(v27 + a1 + 92) = 1;
          if ( !(_DWORD)qword_1801C6280 )
          {
            LODWORD(v27) = qword_1801C6270;
            if ( qword_1801C6270 )
            {
              if ( !byte_1801CA908 && !_InterlockedCompareExchange((volatile signed __int32 *)&qword_1801C6280, 1, 0) )
              {
                TpSetTimerEx(qword_1801C6270, &qword_1801C6278, 0, 1000);
                if ( (RtlpHpHeapFeatures & 0x10) != 0 )
                  RtlpHpTlLogGCScheduled();
              }
            }
          }
        }
      }
    }
    if ( (_DWORD)v34 == -1 )
LABEL_38:
      RtlReleaseSRWLockExclusive(a2 + 56);
    v40 = 3;
    if ( !v51 )
      v40 = 2;
    RtlpHpLfhSubsegmentPrefetchRange(v27, a2, v24, v25, v40);
    return 0;
  }
  v41 = v17 >> v27;
  v42 = (char *)(a2 + 2 * (v41 + 4 * v30));
  _m_prefetchw(v42);
  v43 = 0;
  v44 = &v42[2 * ((v50 >> v27) - (unsigned int)v41) + 2];
  if ( v42 < v44 )
  {
    do
    {
      v45 = _InterlockedDecrement16((volatile signed __int16 *)v42);
      if ( v45 )
      {
        if ( v45 == -1 )
          --v43;
      }
      else
      {
        ++v43;
      }
      v42 += 2;
    }
    while ( v42 < v44 );
    if ( v43 )
    {
      v46 = (v43 << 12 << *(_BYTE *)(a2 + 38)) / 4096;
      _InterlockedAdd64((volatile signed __int64 *)(*(__int16 *)(a1 + 66) + a1 + 24), v46);
      if ( v46 > 0 )
      {
        v47 = (unsigned __int64)*(unsigned __int16 *)(a2 + 44) << 6;
        if ( !*(_BYTE *)(v47 + a1 + 92) )
        {
          *(_BYTE *)(v47 + a1 + 92) = 1;
          if ( !(_DWORD)qword_1801C6280 )
          {
            if ( qword_1801C6270 )
            {
              if ( !byte_1801CA908 && !_InterlockedCompareExchange((volatile signed __int32 *)&qword_1801C6280, 1, 0) )
              {
                TpSetTimerEx(qword_1801C6270, &qword_1801C6278, 0, 1000);
                if ( (RtlpHpHeapFeatures & 0x10) != 0 )
                  RtlpHpTlLogGCScheduled();
              }
            }
          }
        }
      }
    }
  }
  RtlReleaseSRWLockExclusive(a2 + 56);
  return v28;
}

```

## disassembly

```asm
0x180017ee0  mov     [rsp+arg_0], rcx
0x180017ee5  push    rbx
0x180017ee6  push    rbp
0x180017ee7  push    rsi
0x180017ee8  push    rdi
0x180017ee9  push    r12
0x180017eeb  push    r13
0x180017eed  push    r14
0x180017eef  push    r15
0x180017ef1  sub     rsp, 48h
0x180017ef5  movzx   ecx, byte ptr [rdx+26h]
0x180017ef9  lea     ebp, [r8-1]
0x180017efd  movzx   eax, byte ptr [rdx+18h]
0x180017f01  mov     r14d, r8d
0x180017f04  shr     r14d, 0Ch
0x180017f08  xor     r15d, r15d
0x180017f0b  mov     r8d, r14d
0x180017f0e  mov     [rsp+88h+arg_10], 0
0x180017f19  shr     r8d, cl
0x180017f1c  mov     rdi, rdx
0x180017f1f  lea     r10, [rdx+rax*8]
0x180017f23  mov     [rsp+88h+arg_18], r14d
0x180017f2b  lea     rbx, [r10+r8*2]
0x180017f2f  prefetchw byte ptr [rbx]
0x180017f32  movzx   edx, word ptr [rdx+28h]
0x180017f36  mov     rax, rdi
0x180017f39  shr     rax, 0Ch
0x180017f3d  xor     esi, esi
0x180017f3f  movzx   eax, ax
0x180017f42  mov     r13d, 0FFFFFFFFh
0x180017f48  xor     edx, eax
0x180017f4a  mov     [rsp+88h+var_58], r15d
0x180017f4f  movzx   eax, word ptr cs:qword_1801C5EC8
0x180017f56  xor     edx, eax
0x180017f58  add     ebp, edx
0x180017f5a  shr     ebp, 0Ch
0x180017f5d  mov     eax, ebp
0x180017f5f  mov     [rsp+88h+arg_8], ebp
0x180017f66  shr     eax, cl
0x180017f68  sub     eax, r8d
0x180017f6b  inc     eax
0x180017f6d  lea     r12, [rbx+rax*2]
0x180017f71  cmp     rbx, r12
0x180017f74  jnb     loc_180017FFF
0x180017f7a  mov     r14, r10
0x180017f7d  mov     r8d, 1
0x180017f83  movzx   eax, word ptr [rbx]
0x180017f86  test    ax, ax
0x180017f89  jle     loc_180018084
0x180017f8f  lea     ecx, [rax+1]
0x180017f92  lock cmpxchg [rbx], cx
0x180017f97  jnz     short loc_180017F86
0x180017f99  add     rbx, 2
0x180017f9d  cmp     rbx, r12
0x180017fa0  jb      short loc_180017F83
0x180017fa2  mov     ebp, [rsp+88h+arg_8]
0x180017fa9  mov     r14d, [rsp+88h+arg_18]
0x180017fb1  mov     r10, [rsp+88h+arg_0]
0x180017fb9  test    esi, esi
0x180017fbb  jz      short loc_180017FE7
0x180017fbd  movzx   ecx, byte ptr [rdi+26h]
0x180017fc1  shl     esi, 0Ch
0x180017fc4  shl     esi, cl
0x180017fc6  mov     eax, esi
0x180017fc8  cdq
0x180017fc9  and     edx, 0FFFh
0x180017fcf  add     eax, edx
0x180017fd1  sar     eax, 0Ch
0x180017fd4  movsxd  rcx, eax
0x180017fd7  movsx   rax, word ptr [r10+42h]
0x180017fdc  lock add [rax+r10+18h], rcx
0x180017fe2  test    rcx, rcx
0x180017fe5  jg      short loc_180018013
0x180017fe7  cmp     r13d, 0FFFFFFFFh
0x180017feb  jnz     loc_1800180C6
0x180017ff1  test    r15d, r15d
0x180017ff4  jz      short loc_180017FFF
0x180017ff6  lea     rcx, [rdi+38h]
0x180017ffa  call    RtlReleaseSRWLockExclusive
0x180017fff  xor     eax, eax
0x180018001  add     rsp, 48h
0x180018005  pop     r15
0x180018007  pop     r14
0x180018009  pop     r13
0x18001800b  pop     r12
0x18001800d  pop     rdi
0x18001800e  pop     rsi
0x18001800f  pop     rbp
0x180018010  pop     rbx
0x180018011  retn
0x180018013  movzx   ecx, word ptr [rdi+2Ch]
0x180018017  shl     rcx, 6
0x18001801b  movzx   eax, byte ptr [rcx+r10+5Ch]
0x180018021  test    al, al
0x180018023  jnz     short loc_180017FE7
0x180018025  mov     byte ptr [rcx+r10+5Ch], 1
0x18001802b  mov     eax, dword ptr cs:qword_1801C6280
0x180018031  test    eax, eax
0x180018033  jnz     short loc_180017FE7
0x180018035  mov     rcx, cs:qword_1801C6270
0x18001803c  test    rcx, rcx
0x18001803f  jz      short loc_180017FE7
0x180018041  cmp     cs:byte_1801CA908, al
0x180018047  jnz     short loc_180017FE7
0x180018049  lock cmpxchg dword ptr cs:qword_1801C6280, r8d
0x180018052  jnz     short loc_180017FE7
0x180018054  mov     r9d, 3E8h
0x18001805a  lea     rdx, qword_1801C6278
0x180018061  xor     r8d, r8d
0x180018064  call    TpSetTimerEx
0x180018069  test    cs:RtlpHpHeapFeatures, 10h
0x180018070  jz      short loc_180018077
0x180018072  call    RtlpHpTlLogGCScheduled
0x180018077  mov     r10, [rsp+88h+arg_0]
0x18001807f  jmp     loc_180017FE7
0x180018084  test    r15d, r15d
0x180018087  jz      short loc_18001809B
0x180018089  test    ax, ax
0x18001808c  jnz     short loc_1800180AC
0x18001808e  dec     esi
0x180018090  inc     ax
0x180018093  mov     [rbx], ax
0x180018096  jmp     loc_180017F99
0x18001809b  lea     rcx, [rdi+38h]
0x18001809f  mov     r15d, r8d
0x1800180a2  call    RtlAcquireSRWLockExclusive
0x1800180a7  jmp     loc_180017F7D
0x1800180ac  mov     rbp, rbx
0x1800180af  inc     esi
0x1800180b1  sub     rbp, r14
0x1800180b4  sar     rbp, 1
0x1800180b7  cmp     r13d, 0FFFFFFFFh
0x1800180bb  mov     qword ptr [rsp+88h+var_58], rbp
0x1800180c0  cmovz   r13d, ebp
0x1800180c4  jmp     short loc_180018090
0x1800180c6  movzx   ecx, byte ptr [rdi+26h]
0x1800180ca  lea     r9, [rsp+88h+arg_10]
0x1800180d2  mov     r15, qword ptr [rsp+88h+var_58]
0x1800180d7  mov     eax, r13d
0x1800180da  shl     eax, 0Ch
0x1800180dd  sub     r15d, r13d
0x1800180e0  shl     eax, cl
0x1800180e2  inc     r15d
0x1800180e5  mov     esi, eax
0x1800180e7  shl     r15d, 0Ch
0x1800180eb  shl     r15d, cl
0x1800180ee  mov     rcx, [r10]
0x1800180f1  lea     rdx, [rdi+rax]
0x1800180f5  mov     rax, [r10+18h]
0x1800180f9  mov     r8d, r15d
0x1800180fc  xor     rax, cs:RtlpHpHeapGlobals
0x180018103  xor     rax, r10
0x180018106  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001810b  movzx   ecx, byte ptr [rdi+26h]
0x18001810f  mov     ebx, eax
0x180018111  test    eax, eax
0x180018113  movzx   eax, byte ptr [rdi+18h]
0x180018117  js      loc_180018261
0x18001811d  mov     edx, esi
0x18001811f  lea     r10, [rdi+rax*8]
0x180018123  shr     edx, 0Ch
0x180018126  shr     edx, cl
0x180018128  lea     r8, [r10+rdx*2]
0x18001812c  prefetchw byte ptr [r8]
0x180018130  lea     eax, [rsi-1]
0x180018133  mov     ebx, 0FFFFFFFFh
0x180018138  add     eax, r15d
0x18001813b  shr     eax, 0Ch
0x18001813e  shr     eax, cl
0x180018140  sub     eax, edx
0x180018142  xor     edx, edx
0x180018144  inc     eax
0x180018146  lea     r9, [r8+rax*2]
0x18001814a  cmp     r8, r9
0x18001814d  jnb     short loc_1800181AB
0x18001814f  movzx   eax, word ptr [r8]
0x180018153  test    ax, ax
0x180018156  jle     loc_18001824D
0x18001815c  lea     ecx, [rax+1]
0x18001815f  lock cmpxchg [r8], cx
0x180018165  jnz     short loc_180018153
0x180018167  add     r8, 2
0x18001816b  cmp     r8, r9
0x18001816e  jb      short loc_18001814F
0x180018170  test    edx, edx
0x180018172  jz      short loc_1800181A6
0x180018174  movzx   ecx, byte ptr [rdi+26h]
0x180018178  shl     edx, 0Ch
0x18001817b  shl     edx, cl
0x18001817d  mov     eax, edx
0x18001817f  cdq
0x180018180  and     edx, 0FFFh
0x180018186  add     eax, edx
0x180018188  mov     rdx, [rsp+88h+arg_0]
0x180018190  sar     eax, 0Ch
0x180018193  movsxd  rcx, eax
0x180018196  movsx   rax, word ptr [rdx+42h]
0x18001819b  lock add [rax+rdx+18h], rcx
0x1800181a1  test    rcx, rcx
0x1800181a4  jg      short loc_1800181DE
0x1800181a6  cmp     ebx, 0FFFFFFFFh
0x1800181a9  jnz     short loc_1800181B4
0x1800181ab  lea     rcx, [rdi+38h]
0x1800181af  call    RtlReleaseSRWLockExclusive
0x1800181b4  cmp     [rsp+88h+arg_10], 0
0x1800181bc  mov     eax, 3
0x1800181c1  jz      loc_180018386
0x1800181c7  mov     r9d, r15d
0x1800181ca  mov     [rsp+88h+var_68], eax
0x1800181ce  mov     r8d, esi
0x1800181d1  mov     rdx, rdi
0x1800181d4  call    RtlpHpLfhSubsegmentPrefetchRange
0x1800181d9  jmp     loc_180017FFF
0x1800181de  movzx   ecx, word ptr [rdi+2Ch]
0x1800181e2  shl     rcx, 6
0x1800181e6  movzx   eax, byte ptr [rcx+rdx+5Ch]
0x1800181eb  test    al, al
0x1800181ed  jnz     short loc_1800181A6
0x1800181ef  mov     byte ptr [rcx+rdx+5Ch], 1
0x1800181f4  mov     eax, dword ptr cs:qword_1801C6280
0x1800181fa  test    eax, eax
0x1800181fc  jnz     short loc_1800181A6
0x1800181fe  mov     rcx, cs:qword_1801C6270
0x180018205  test    rcx, rcx
0x180018208  jz      short loc_1800181A6
0x18001820a  cmp     cs:byte_1801CA908, al
0x180018210  jnz     short loc_1800181A6
0x180018212  mov     edx, 1
0x180018217  lock cmpxchg dword ptr cs:qword_1801C6280, edx
0x18001821f  jnz     short loc_1800181A6
0x180018221  mov     r9d, 3E8h
0x180018227  lea     rdx, qword_1801C6278
0x18001822e  xor     r8d, r8d
0x180018231  call    TpSetTimerEx
0x180018236  test    cs:RtlpHpHeapFeatures, 10h
0x18001823d  jz      loc_1800181A6
0x180018243  call    RtlpHpTlLogGCScheduled
0x180018248  jmp     loc_1800181A6
0x18001824d  jnz     loc_18001836D
0x180018253  dec     edx
0x180018255  inc     ax
0x180018258  mov     [r8], ax
0x18001825c  jmp     loc_180018167
0x180018261  shr     r14d, cl
0x180018264  lea     rax, [r14+rax*4]
0x180018268  lea     rax, [rdi+rax*2]
0x18001826c  prefetchw byte ptr [rax]
0x18001826f  shr     ebp, cl
0x180018271  xor     r8d, r8d
0x180018274  sub     ebp, r14d
0x180018277  inc     ebp
0x180018279  lea     rdx, [rax+rbp*2]
0x18001827d  cmp     rax, rdx
0x180018280  jnb     short loc_1800182AD
0x180018282  mov     ecx, 0FFFFFFFFh
0x180018287  lock xadd [rax], cx
0x18001828c  sub     cx, 1
0x180018290  jz      loc_180018365
0x180018296  cmp     cx, 0FFFFh
0x18001829a  jnz     short loc_18001829F
0x18001829c  dec     r8d
0x18001829f  add     rax, 2
0x1800182a3  cmp     rax, rdx
0x1800182a6  jb      short loc_180018282
0x1800182a8  test    r8d, r8d
0x1800182ab  jnz     short loc_1800182BD
0x1800182ad  lea     rcx, [rdi+38h]
0x1800182b1  call    RtlReleaseSRWLockExclusive
0x1800182b6  mov     eax, ebx
0x1800182b8  jmp     loc_180018001
0x1800182bd  movzx   ecx, byte ptr [rdi+26h]
0x1800182c1  shl     r8d, 0Ch
0x1800182c5  shl     r8d, cl
0x1800182c8  mov     eax, r8d
0x1800182cb  cdq
0x1800182cc  and     edx, 0FFFh
0x1800182d2  add     eax, edx
0x1800182d4  mov     rdx, [rsp+88h+arg_0]
0x1800182dc  sar     eax, 0Ch
0x1800182df  movsxd  rcx, eax
0x1800182e2  movsx   rax, word ptr [rdx+42h]
0x1800182e7  lock add [rax+rdx+18h], rcx
0x1800182ed  test    rcx, rcx
0x1800182f0  jle     short loc_1800182AD
0x1800182f2  movzx   ecx, word ptr [rdi+2Ch]
0x1800182f6  shl     rcx, 6
0x1800182fa  movzx   eax, byte ptr [rcx+rdx+5Ch]
0x1800182ff  test    al, al
0x180018301  jnz     short loc_1800182AD
0x180018303  mov     byte ptr [rcx+rdx+5Ch], 1
0x180018308  mov     eax, dword ptr cs:qword_1801C6280
0x18001830e  test    eax, eax
0x180018310  jnz     short loc_1800182AD
0x180018312  mov     rcx, cs:qword_1801C6270
0x180018319  test    rcx, rcx
0x18001831c  jz      short loc_1800182AD
0x18001831e  cmp     cs:byte_1801CA908, al
0x180018324  jnz     short loc_1800182AD
0x180018326  mov     edx, 1
0x18001832b  lock cmpxchg dword ptr cs:qword_1801C6280, edx
  ... truncated ...
```
