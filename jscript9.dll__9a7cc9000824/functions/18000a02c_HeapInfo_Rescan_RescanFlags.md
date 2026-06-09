# HeapInfo::Rescan(RescanFlags)

- ea: `0x18000a02c`
- end: `0x18000a6e8`
- name: `?Rescan@HeapInfo@@QEAAIW4RescanFlags@@@Z`
- size: `1724`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: ``

## callers

- `0x18000954c`
- `0x1800096a0`

## callees

- `0x180009808`
- `0x180009d80`
- `0x18000a02c`
- `0x18000a6f0`
- `0x18000a7f0`
- `0x18000aaa4`
- `0x18000ad60`
- `0x18000ae10`
- `0x18000b100`
- `0x18000b238`
- `0x18025a618`
- `0x18025a684`

## import_xrefs

- `KERNEL32!ResetWriteWatch` at `0x18000a365`
- `KERNEL32!ResetWriteWatch` at `0x18000a396`
- `KERNEL32!ResetWriteWatch` at `0x18000a365`
- `KERNEL32!ResetWriteWatch` at `0x18000a396`
- `KERNEL32!GetWriteWatch` at `0x18000a18f`
- `KERNEL32!GetWriteWatch` at `0x18000a251`
- `KERNEL32!GetWriteWatch` at `0x18000a18f`
- `KERNEL32!GetWriteWatch` at `0x18000a251`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HeapInfo::Rescan(__int64 a1, unsigned int a2)
{
  unsigned int v2; // r15d
  __int64 v3; // rax
  __int64 v4; // rax
  __int64 v5; // r13
  __int64 v6; // rsi
  __int64 v7; // r14
  __int64 v8; // rbx
  int v9; // edi
  __int64 v10; // r8
  int v11; // ecx
  _BYTE *v12; // r12
  __int64 v13; // rbx
  __int64 v14; // rcx
  DWORD v15; // eax
  PVOID *v16; // rdi
  __int64 v17; // rbx
  _BYTE *v18; // rdi
  int v19; // eax
  int v20; // ebx
  int v21; // eax
  int v22; // r12d
  __int64 i; // rbx
  int v24; // ebx
  int v25; // ebx
  int v27; // eax
  unsigned int v28; // r13d
  char *v29; // r9
  __int64 v30; // rdi
  unsigned int v31; // r15d
  unsigned int v32; // r14d
  __int64 v33; // rax
  __int64 v34; // rax
  _QWORD *v35; // rdx
  _QWORD *v36; // rcx
  char v37; // al
  int v38; // eax
  int v39; // eax
  unsigned int v40; // r15d
  char *v41; // r9
  __int64 v42; // rdi
  unsigned int v43; // r12d
  int v44; // r13d
  unsigned int v45; // r14d
  __int64 v46; // rax
  __int64 v47; // rax
  _QWORD *v48; // rdx
  _QWORD *v49; // rcx
  char v50; // al
  int v51; // eax
  _QWORD *Chunk; // rax
  _QWORD *v53; // rax
  bool v54; // al
  int v55; // ebx
  DWORD lpdwGranularity; // [rsp+30h] [rbp-50h] BYREF
  __int64 v57; // [rsp+38h] [rbp-48h]
  PVOID Addresses; // [rsp+40h] [rbp-40h] BYREF
  DWORD dwGranularity[2]; // [rsp+48h] [rbp-38h] BYREF
  _BYTE *v60; // [rsp+50h] [rbp-30h]
  ULONG_PTR dwCount; // [rsp+58h] [rbp-28h] BYREF
  int v62; // [rsp+60h] [rbp-20h]
  int v63; // [rsp+64h] [rbp-1Ch]
  __int64 v64; // [rsp+68h] [rbp-18h]
  __int64 v65; // [rsp+70h] [rbp-10h]
  __int64 v66; // [rsp+78h] [rbp-8h]

  v66 = -2;
  v2 = a2;
  v62 = 0;
  v3 = 0;
  v65 = 0;
  do
  {
    v4 = 304 * v3;
    v5 = v4 + a1 + 88;
    v64 = v5;
    v6 = *(_QWORD *)(a1 + 56);
    v7 = a1 + v4;
    v8 = *(_QWORD *)(a1 + v4 + 384);
    v9 = 0;
    while ( v8 )
    {
      if ( (unsigned __int8)SmallNormalHeapBlock::NeedRescanObjects(v8, v6, v2) )
      {
        SmallNormalHeapBucketBase<SmallFinalizableHeapBlock>::RescanObjects<1,1>(
          (SmallFinalizableHeapBlock *)v8,
          (struct Recycler *)v6);
LABEL_3:
        ++v9;
        goto LABEL_4;
      }
      if ( *(_BYTE *)(v8 + 120) )
        goto LABEL_3;
LABEL_4:
      v8 = *(_QWORD *)(v8 + 32);
    }
    v63 = v9 + SmallNormalHeapBucketBase<SmallFinalizableHeapBlock>::Rescan(v7 + 280, v6, v2);
    v11 = *(_DWORD *)v6 & 0x2001;
    v12 = (_BYTE *)(v6 + 12901);
    v60 = (_BYTE *)(v6 + 12901);
    if ( v11 != 8193 )
    {
      if ( *v12 )
        v60 = (_BYTE *)(v6 + 12901);
      else
        HeapBucketT<SmallLeafHeapBlock>::PrepareSweep(v5 + 104);
    }
    if ( (*(_DWORD *)v6 & 0x2001) != 0x2001 && !*v12 )
      HeapBucketT<SmallNormalHeapBlock>::PrepareSweep(v5);
    v13 = *(_QWORD *)(v5 + 72);
    v14 = 0;
    v57 = 0;
    if ( !v13 )
      goto LABEL_29;
    v15 = v2 & 1;
    lpdwGranularity = v15;
    do
    {
      if ( v15 )
      {
        *(_BYTE *)(v13 + 120) = 0;
      }
      else if ( *(_BYTE *)(v13 + 120) )
      {
        if ( (v2 & 2) != 0 )
        {
          ResetWriteWatch(*(LPVOID *)(v13 + 8), 0x1000u);
LABEL_24:
          v14 = v57;
          goto LABEL_25;
        }
        goto LABEL_25;
      }
      if ( !*(_WORD *)(v13 + 80) )
        goto LABEL_25;
      if ( !*(_BYTE *)(v13 + 25) )
      {
        if ( *v12 )
          goto LABEL_25;
        dwCount = 1;
        dwGranularity[0] = 4096;
        Addresses = 0;
        v16 = (PVOID *)(v13 + 8);
        if ( GetWriteWatch((v2 >> 1) & 1, *(PVOID *)(v13 + 8), 0x1000u, &Addresses, &dwCount, dwGranularity) || dwCount )
        {
          v14 = v57;
          goto LABEL_55;
        }
        goto LABEL_24;
      }
      if ( !*(_BYTE *)(v6 + 12888) )
      {
        *(_BYTE *)(v13 + 25) = 0;
        v16 = (PVOID *)(v13 + 8);
LABEL_55:
        *(_BYTE *)(v13 + 120) = 1;
        v27 = *(unsigned __int16 *)(v13 + 74);
        v28 = *(unsigned __int16 *)(v13 + 80);
        v29 = (char *)*v16;
        Addresses = *v16;
        v30 = *(unsigned __int16 *)(v13 + 72);
        if ( v28 == v27 )
        {
          v54 = Recycler::AddMark((Recycler *)v6, v29, (unsigned int)(v27 * v30));
          v14 = v57;
          if ( !v54 )
          {
            *(_BYTE *)(v13 + 25) = 1;
            *(_BYTE *)(v6 + 12888) = 1;
          }
        }
        else
        {
          v31 = 0;
          v10 = 0;
          dwGranularity[0] = 0;
          v32 = 0;
          if ( v28 )
          {
            while ( 1 )
            {
              v33 = *(_QWORD *)(v13 + 8 * ((unsigned __int64)v32 >> 6) + 88);
              if ( _bittest64(&v33, v32 & 0x3F) )
                break;
LABEL_65:
              v10 = (unsigned int)(v10 + 1);
              dwGranularity[0] = v10;
              v32 += (unsigned int)v30 >> 5;
              if ( v31 >= v28 )
              {
                v12 = v60;
                v2 = a2;
                v14 = v57;
                goto LABEL_26;
              }
            }
            v34 = *(_QWORD *)(v6 + 12680);
            v35 = *(_QWORD **)(v34 + 16);
            v36 = v35 + 2;
            if ( (unsigned __int64)(v35 + 2) <= *(_QWORD *)(v34 + 24) )
            {
              *(_QWORD *)(v34 + 16) = v36;
              goto LABEL_60;
            }
            Chunk = *(_QWORD **)(v6 + 12688);
            if ( Chunk )
            {
              *(_QWORD *)(v6 + 12688) = 0;
LABEL_85:
              *Chunk = *(_QWORD *)(v6 + 12680);
              Chunk[2] = Chunk + 6;
              *(_QWORD *)(v6 + 12680) = Chunk;
              v35 = Chunk + 4;
LABEL_60:
              if ( v35 )
              {
                *v35 = &v29[(unsigned int)(v30 * v10)];
                v35[1] = v30;
                v37 = 1;
LABEL_62:
                if ( v37 )
                {
                  v38 = 1;
                }
                else
                {
                  *(_BYTE *)(v13 + 25) = 1;
                  *(_BYTE *)(v6 + 12888) = 1;
                  v38 = *(unsigned __int16 *)(v13 + 74) + 1;
                }
                v31 += v38;
                goto LABEL_65;
              }
            }
            else
            {
              Chunk = (_QWORD *)PageStackBase<Recycler::MarkCandidate>::CreateChunk(v36, v6 + 12712, v10);
              if ( Chunk )
              {
                LODWORD(v10) = dwGranularity[0];
                v29 = (char *)Addresses;
                goto LABEL_85;
              }
            }
            v37 = 0;
            LODWORD(v10) = dwGranularity[0];
            v29 = (char *)Addresses;
            goto LABEL_62;
          }
          v2 = a2;
        }
LABEL_26:
        v57 = ++v14;
        goto LABEL_27;
      }
LABEL_25:
      if ( *(_BYTE *)(v13 + 120) )
        goto LABEL_26;
LABEL_27:
      v13 = *(_QWORD *)(v13 + 32);
      v15 = lpdwGranularity;
    }
    while ( v13 );
    v5 = v64;
LABEL_29:
    v17 = *(_QWORD *)(v5 + 80);
    v18 = 0;
    v60 = 0;
    if ( !v17 )
      goto LABEL_42;
    v19 = v2 & 1;
    LODWORD(dwCount) = v19;
    do
    {
      if ( v19 )
      {
        *(_BYTE *)(v17 + 120) = 0;
      }
      else if ( *(_BYTE *)(v17 + 120) )
      {
        if ( (v2 & 2) != 0 )
          ResetWriteWatch(*(LPVOID *)(v17 + 8), 0x1000u);
LABEL_38:
        if ( !*(_BYTE *)(v17 + 120) )
          goto LABEL_40;
        goto LABEL_39;
      }
      if ( !*(_WORD *)(v17 + 80) )
        goto LABEL_38;
      if ( *(_BYTE *)(v17 + 25) )
      {
        if ( *(_BYTE *)(v6 + 12888) )
          goto LABEL_38;
        *(_BYTE *)(v17 + 25) = 0;
      }
      else
      {
        if ( *(_BYTE *)(v6 + 12901) )
          goto LABEL_38;
        Addresses = (PVOID)1;
        lpdwGranularity = 4096;
        *(_QWORD *)dwGranularity = 0;
        if ( !GetWriteWatch(
                (v2 >> 1) & 1,
                *(PVOID *)(v17 + 8),
                0x1000u,
                (PVOID *)dwGranularity,
                (ULONG_PTR *)&Addresses,
                &lpdwGranularity)
          && !Addresses )
        {
          goto LABEL_38;
        }
      }
      *(_BYTE *)(v17 + 120) = 1;
      v39 = *(unsigned __int16 *)(v17 + 74);
      v40 = *(unsigned __int16 *)(v17 + 80);
      v41 = *(char **)(v17 + 8);
      Addresses = v41;
      v42 = *(unsigned __int16 *)(v17 + 72);
      if ( v40 == v39 )
      {
        if ( !Recycler::AddMark((Recycler *)v6, v41, (unsigned int)(v39 * v42)) )
        {
          *(_BYTE *)(v17 + 25) = 1;
          *(_BYTE *)(v6 + 12888) = 1;
        }
      }
      else
      {
        lpdwGranularity = (unsigned int)v42 >> 5;
        v43 = 0;
        v44 = 0;
        v45 = 0;
        if ( v40 )
        {
          while ( 1 )
          {
            v46 = *(_QWORD *)(v17 + 8 * ((unsigned __int64)v45 >> 6) + 88);
            if ( _bittest64(&v46, v45 & 0x3F) )
              break;
LABEL_77:
            ++v44;
            v45 += lpdwGranularity;
            if ( v43 >= v40 )
              goto LABEL_78;
          }
          v47 = *(_QWORD *)(v6 + 12680);
          v48 = *(_QWORD **)(v47 + 16);
          v49 = v48 + 2;
          if ( (unsigned __int64)(v48 + 2) > *(_QWORD *)(v47 + 24) )
          {
            v53 = *(_QWORD **)(v6 + 12688);
            if ( v53 )
            {
              *(_QWORD *)(v6 + 12688) = 0;
            }
            else
            {
              v53 = (_QWORD *)PageStackBase<Recycler::MarkCandidate>::CreateChunk(v49, v6 + 12712, v10);
              if ( !v53 )
                goto LABEL_103;
              v41 = (char *)Addresses;
            }
            *v53 = *(_QWORD *)(v6 + 12680);
            v53[2] = v53 + 6;
            *(_QWORD *)(v6 + 12680) = v53;
            v48 = v53 + 4;
          }
          else
          {
            *(_QWORD *)(v47 + 16) = v49;
          }
          if ( v48 )
          {
            *v48 = &v41[(unsigned int)(v42 * v44)];
            v48[1] = v42;
            v50 = 1;
LABEL_74:
            if ( v50 )
            {
              v51 = 1;
            }
            else
            {
              *(_BYTE *)(v17 + 25) = 1;
              *(_BYTE *)(v6 + 12888) = 1;
              v51 = *(unsigned __int16 *)(v17 + 74) + 1;
            }
            v43 += v51;
            goto LABEL_77;
          }
LABEL_103:
          v50 = 0;
          v41 = (char *)Addresses;
          goto LABEL_74;
        }
      }
LABEL_78:
      v18 = v60;
      v2 = a2;
LABEL_39:
      v60 = ++v18;
LABEL_40:
      v17 = *(_QWORD *)(v17 + 32);
      v19 = dwCount;
    }
    while ( v17 );
    v5 = v64;
LABEL_42:
    if ( *(_BYTE *)(v6 + 12903) )
    {
      v20 = (_DWORD)v18 + v57;
      v55 = SmallNormalHeapBucketBase<SmallNormalHeapBlock>::RescanHeapBlockList<1,0>(*(SmallNormalHeapBlock **)(v5 + 88))
          + v20;
      v21 = v55
          + SmallNormalHeapBucketBase<SmallNormalHeapBlock>::RescanHeapBlockList<1,0>(*(SmallNormalHeapBlock **)(v5 + 96));
    }
    else
    {
      v21 = (_DWORD)v18 + v57;
    }
    v22 = v63 + v21 + v62;
    v62 = v22;
    v3 = v65 + 1;
    v65 = v3;
  }
  while ( v3 != 32 );
  for ( i = 0; i != 32; ++i )
    v22 += LargeHeapBucket::Rescan(a1 + 8 * (i + 8 * i + 1227), v2);
  v24 = LargeHeapBucket::Rescan(a1 + 12120, v2) + v22;
  v25 = SmallNormalHeapBucketBase<SmallNormalHeapBlock>::RescanHeapBlockList<0,0>(
          *(_QWORD *)(a1 + 72),
          *(_QWORD *)(a1 + 56),
          v2)
      + v24;
  return v25
       + (unsigned int)SmallNormalHeapBucketBase<SmallFinalizableHeapBlock>::RescanHeapBlockList<0,0>(*(SmallFinalizableHeapBlock **)(a1 + 80));
}

```

## disassembly

```asm
0x18000a02c  mov     rax, rsp
0x18000a02f  mov     [rax+10h], edx
0x18000a032  mov     [rax+8], rcx
0x18000a036  push    rbp
0x18000a037  push    rsi
0x18000a038  push    rdi
0x18000a039  push    r12
0x18000a03b  push    r13
0x18000a03d  push    r14
0x18000a03f  push    r15
0x18000a041  mov     rbp, rsp
0x18000a044  sub     rsp, 80h
0x18000a04b  mov     [rbp+var_8], 0FFFFFFFFFFFFFFFEh
0x18000a053  mov     [rax+18h], rbx
0x18000a057  mov     r15d, [rbp+arg_8]
0x18000a05b  xor     r10d, r10d
0x18000a05e  mov     [rbp+var_20], r10d
0x18000a062  mov     eax, r10d
0x18000a065  mov     [rbp+var_10], rax
0x18000a069  imul    rax, 130h
0x18000a070  mov     rcx, [rbp+arg_0]
0x18000a074  lea     r13, [rcx+58h]
0x18000a078  add     r13, rax
0x18000a07b  mov     [rbp+var_18], r13
0x18000a07f  mov     rsi, [rcx+38h]
0x18000a083  lea     r14, [rcx+rax]
0x18000a087  mov     rbx, [r14+180h]
0x18000a08e  mov     rdi, r10
0x18000a091  jmp     short loc_18000A09A
0x18000a093  inc     rdi
0x18000a096  mov     rbx, [rbx+20h]
0x18000a09a  mov     r8d, r15d
0x18000a09d  mov     rdx, rsi
0x18000a0a0  test    rbx, rbx
0x18000a0a3  jz      short loc_18000A0BC
0x18000a0a5  mov     rcx, rbx
0x18000a0a8  call    ?NeedRescanObjects@SmallNormalHeapBlock@@QEAA_NPEAVRecycler@@W4RescanFlags@@@Z; SmallNormalHeapBlock::NeedRescanObjects(Recycler *,RescanFlags)
0x18000a0ad  test    al, al
0x18000a0af  jnz     loc_18000A692
0x18000a0b5  cmp     [rbx+78h], al
0x18000a0b8  jz      short loc_18000A096
0x18000a0ba  jmp     short loc_18000A093
0x18000a0bc  lea     rcx, [r14+118h]
0x18000a0c3  call    ?Rescan@?$SmallNormalHeapBucketBase@VSmallFinalizableHeapBlock@@@@IEAAIPEAVRecycler@@W4RescanFlags@@@Z; SmallNormalHeapBucketBase<SmallFinalizableHeapBlock>::Rescan(Recycler *,RescanFlags)
0x18000a0c8  add     eax, edi
0x18000a0ca  mov     [rbp+var_1C], eax
0x18000a0cd  mov     ecx, [rsi]
0x18000a0cf  mov     ebx, 2001h
0x18000a0d4  and     ecx, ebx
0x18000a0d6  lea     r12, [rsi+3265h]
0x18000a0dd  mov     [rbp+var_30], r12
0x18000a0e1  cmp     ecx, ebx
0x18000a0e3  jz      short loc_18000A0F9
0x18000a0e5  cmp     byte ptr [r12], 0
0x18000a0ea  jnz     loc_18000A689
0x18000a0f0  lea     rcx, [r13+68h]
0x18000a0f4  call    ?PrepareSweep@?$HeapBucketT@VSmallLeafHeapBlock@@@@QEAAXXZ; HeapBucketT<SmallLeafHeapBlock>::PrepareSweep(void)
0x18000a0f9  mov     eax, [rsi]
0x18000a0fb  and     eax, ebx
0x18000a0fd  cmp     eax, ebx
0x18000a0ff  jz      short loc_18000A110
0x18000a101  cmp     byte ptr [r12], 0
0x18000a106  jnz     short loc_18000A110
0x18000a108  mov     rcx, r13
0x18000a10b  call    ?PrepareSweep@?$HeapBucketT@VSmallNormalHeapBlock@@@@QEAAXXZ; HeapBucketT<SmallNormalHeapBlock>::PrepareSweep(void)
0x18000a110  mov     rbx, [r13+48h]
0x18000a114  xor     r10d, r10d
0x18000a117  mov     ecx, r10d
0x18000a11a  mov     [rbp+var_48], rcx
0x18000a11e  test    rbx, rbx
0x18000a121  jz      loc_18000A1D5
0x18000a127  mov     eax, r15d
0x18000a12a  and     eax, 1
0x18000a12d  mov     [rbp+var_50], eax
0x18000a130  test    eax, eax
0x18000a132  jz      loc_18000A348
0x18000a138  mov     [rbx+78h], r10b
0x18000a13c  cmp     [rbx+50h], r10w
0x18000a141  jz      short loc_18000A1B4
0x18000a143  cmp     [rbx+19h], r10b
0x18000a147  jnz     loc_18000A51E
0x18000a14d  cmp     [r12], r10b
0x18000a151  jnz     short loc_18000A1B4
0x18000a153  mov     [rbp+dwCount], 1
0x18000a15b  mov     edx, 1000h
0x18000a160  mov     [rbp+dwGranularity], edx
0x18000a163  mov     [rbp+Addresses], r10
0x18000a167  lea     rdi, [rbx+8]
0x18000a16b  mov     ecx, r15d
0x18000a16e  shr     ecx, 1
0x18000a170  and     ecx, 1; dwFlags
0x18000a173  lea     rax, [rbp+dwGranularity]
0x18000a177  mov     [rsp+80h+lpdwGranularity], rax; lpdwGranularity
0x18000a17c  lea     rax, [rbp+dwCount]
0x18000a180  mov     [rsp+80h+lpdwCount], rax; lpdwCount
0x18000a185  lea     r9, [rbp+Addresses]; lpAddresses
0x18000a189  mov     r8d, edx; dwRegionSize
0x18000a18c  mov     rdx, [rdi]; lpBaseAddress
0x18000a18f  call    cs:__imp_GetWriteWatch
0x18000a196  nop     dword ptr [rax+rax+00h]
0x18000a19b  xor     r10d, r10d
0x18000a19e  test    eax, eax
0x18000a1a0  jnz     loc_18000A3AA
0x18000a1a6  cmp     [rbp+dwCount], r10
0x18000a1aa  jnz     loc_18000A3AA
0x18000a1b0  mov     rcx, [rbp+var_48]
0x18000a1b4  cmp     [rbx+78h], r10b
0x18000a1b8  jz      short loc_18000A1C1
0x18000a1ba  inc     rcx
0x18000a1bd  mov     [rbp+var_48], rcx
0x18000a1c1  mov     rbx, [rbx+20h]
0x18000a1c5  test    rbx, rbx
0x18000a1c8  mov     eax, [rbp+var_50]
0x18000a1cb  jnz     loc_18000A130
0x18000a1d1  mov     r13, [rbp+var_18]
0x18000a1d5  mov     rbx, [r13+50h]
0x18000a1d9  mov     rdi, r10
0x18000a1dc  mov     [rbp+var_30], r10
0x18000a1e0  test    rbx, rbx
0x18000a1e3  jz      loc_18000A293
0x18000a1e9  mov     eax, r15d
0x18000a1ec  and     eax, 1
0x18000a1ef  mov     dword ptr [rbp+dwCount], eax
0x18000a1f2  test    eax, eax
0x18000a1f4  jz      loc_18000A379
0x18000a1fa  mov     [rbx+78h], r10b
0x18000a1fe  cmp     [rbx+50h], r10w
0x18000a203  jz      short loc_18000A272
0x18000a205  cmp     [rbx+19h], r10b
0x18000a209  jnz     loc_18000A538
0x18000a20f  cmp     [rsi+3265h], r10b
0x18000a216  jnz     short loc_18000A272
0x18000a218  mov     [rbp+Addresses], 1
0x18000a220  mov     edx, 1000h
0x18000a225  mov     [rbp+var_50], edx
0x18000a228  mov     qword ptr [rbp+dwGranularity], r10
0x18000a22c  mov     ecx, r15d
0x18000a22f  shr     ecx, 1
0x18000a231  and     ecx, 1; dwFlags
0x18000a234  lea     rax, [rbp+var_50]
0x18000a238  mov     [rsp+80h+lpdwGranularity], rax; lpdwGranularity
0x18000a23d  lea     rax, [rbp+Addresses]
0x18000a241  mov     [rsp+80h+lpdwCount], rax; lpdwCount
0x18000a246  lea     r9, [rbp+dwGranularity]; lpAddresses
0x18000a24a  mov     r8d, edx; dwRegionSize
0x18000a24d  mov     rdx, [rbx+8]; lpBaseAddress
0x18000a251  call    cs:__imp_GetWriteWatch
0x18000a258  nop     dword ptr [rax+rax+00h]
0x18000a25d  xor     r10d, r10d
0x18000a260  test    eax, eax
0x18000a262  jnz     loc_18000A46D
0x18000a268  cmp     [rbp+Addresses], r10
0x18000a26c  jnz     loc_18000A46D
0x18000a272  cmp     [rbx+78h], r10b
0x18000a276  jz      short loc_18000A27F
0x18000a278  inc     rdi
0x18000a27b  mov     [rbp+var_30], rdi
0x18000a27f  mov     rbx, [rbx+20h]
0x18000a283  test    rbx, rbx
0x18000a286  mov     eax, dword ptr [rbp+dwCount]
0x18000a289  jnz     loc_18000A1F2
0x18000a28f  mov     r13, [rbp+var_18]
0x18000a293  mov     rbx, [rbp+var_48]
0x18000a297  add     ebx, edi
0x18000a299  cmp     [rsi+3267h], r10b
0x18000a2a0  jnz     loc_18000A6BE
0x18000a2a6  mov     eax, ebx
0x18000a2a8  add     eax, [rbp+var_1C]
0x18000a2ab  mov     r12d, [rbp+var_20]
0x18000a2af  add     r12d, eax
0x18000a2b2  mov     [rbp+var_20], r12d
0x18000a2b6  mov     rax, [rbp+var_10]
0x18000a2ba  inc     rax
0x18000a2bd  mov     [rbp+var_10], rax
0x18000a2c1  cmp     rax, 20h ; ' '
0x18000a2c5  jnz     loc_18000A069
0x18000a2cb  mov     rbx, r10
0x18000a2ce  mov     rdi, [rbp+arg_0]
0x18000a2d2  lea     rax, ds:4CBh[rbx*8]
0x18000a2da  add     rax, rbx
0x18000a2dd  lea     rcx, [rdi+rax*8]
0x18000a2e1  mov     edx, r15d
0x18000a2e4  call    ?Rescan@LargeHeapBucket@@QEAAIW4RescanFlags@@@Z; LargeHeapBucket::Rescan(RescanFlags)
0x18000a2e9  add     r12d, eax
0x18000a2ec  inc     rbx
0x18000a2ef  cmp     rbx, 20h ; ' '
0x18000a2f3  jnz     short loc_18000A2D2
0x18000a2f5  lea     rcx, [rdi+2F58h]
0x18000a2fc  mov     edx, r15d
0x18000a2ff  call    ?Rescan@LargeHeapBucket@@QEAAIW4RescanFlags@@@Z; LargeHeapBucket::Rescan(RescanFlags)
0x18000a304  lea     ebx, [rax+r12]
0x18000a308  mov     r8d, r15d
0x18000a30b  mov     rdx, [rdi+38h]
0x18000a30f  mov     rcx, [rdi+48h]
0x18000a313  call    ??$RescanHeapBlockList@$0A@$0A@@?$SmallNormalHeapBucketBase@VSmallNormalHeapBlock@@@@KA_KPEAVSmallNormalHeapBlock@@PEAVRecycler@@W4RescanFlags@@@Z; SmallNormalHeapBucketBase<SmallNormalHeapBlock>::RescanHeapBlockList<0,0>(SmallNormalHeapBlock *,Recycler *,RescanFlags)
0x18000a318  add     ebx, eax
0x18000a31a  mov     r8d, r15d
0x18000a31d  mov     rdx, [rdi+38h]
0x18000a321  mov     rcx, [rdi+50h]; this
0x18000a325  call    ??$RescanHeapBlockList@$0A@$0A@@?$SmallNormalHeapBucketBase@VSmallFinalizableHeapBlock@@@@KA_KPEAVSmallFinalizableHeapBlock@@PEAVRecycler@@W4RescanFlags@@@Z; SmallNormalHeapBucketBase<SmallFinalizableHeapBlock>::RescanHeapBlockList<0,0>(SmallFinalizableHeapBlock *,Recycler *,RescanFlags)
0x18000a32a  add     eax, ebx
0x18000a32c  mov     rbx, [rsp+80h+arg_10]
0x18000a334  add     rsp, 80h
0x18000a33b  pop     r15
0x18000a33d  pop     r14
0x18000a33f  pop     r13
0x18000a341  pop     r12
0x18000a343  pop     rdi
0x18000a344  pop     rsi
0x18000a345  pop     rbp
0x18000a346  retn
0x18000a348  cmp     [rbx+78h], r10b
0x18000a34c  jz      loc_18000A13C
0x18000a352  test    r15b, 2
0x18000a356  jz      loc_18000A1B4
0x18000a35c  mov     edx, 1000h; dwRegionSize
0x18000a361  mov     rcx, [rbx+8]; lpBaseAddress
0x18000a365  call    cs:__imp_ResetWriteWatch
0x18000a36c  nop     dword ptr [rax+rax+00h]
0x18000a371  xor     r10d, r10d
0x18000a374  jmp     loc_18000A1B0
0x18000a379  cmp     [rbx+78h], r10b
0x18000a37d  jz      loc_18000A1FE
0x18000a383  test    r15b, 2
0x18000a387  jz      loc_18000A272
0x18000a38d  mov     edx, 1000h; dwRegionSize
0x18000a392  mov     rcx, [rbx+8]; lpBaseAddress
0x18000a396  call    cs:__imp_ResetWriteWatch
0x18000a39d  nop     dword ptr [rax+rax+00h]
0x18000a3a2  xor     r10d, r10d
0x18000a3a5  jmp     loc_18000A272
0x18000a3aa  mov     rcx, [rbp+var_48]
0x18000a3ae  mov     byte ptr [rbx+78h], 1
0x18000a3b2  movzx   eax, word ptr [rbx+4Ah]
0x18000a3b6  movzx   r13d, word ptr [rbx+50h]
0x18000a3bb  mov     r9, [rdi]
0x18000a3be  mov     [rbp+Addresses], r9
0x18000a3c2  movzx   edi, word ptr [rbx+48h]
0x18000a3c6  cmp     r13d, eax
0x18000a3c9  jz      loc_18000A601
0x18000a3cf  mov     eax, edi
0x18000a3d1  shr     eax, 5
0x18000a3d4  mov     r15d, r10d
0x18000a3d7  mov     r8d, r10d
0x18000a3da  mov     [rbp+dwGranularity], r10d
0x18000a3de  mov     r14d, r10d
0x18000a3e1  test    r13d, r13d
0x18000a3e4  jz      loc_18000A5F8
0x18000a3ea  mov     r12d, eax
0x18000a3ed  mov     ecx, r14d
0x18000a3f0  and     ecx, 3Fh
0x18000a3f3  mov     eax, r14d
0x18000a3f6  shr     rax, 6
0x18000a3fa  mov     rax, [rbx+rax*8+58h]
0x18000a3ff  bt      rax, rcx
0x18000a403  jnb     short loc_18000A44D
0x18000a405  mov     rax, [rsi+3188h]
0x18000a40c  mov     rdx, [rax+10h]
0x18000a410  lea     rcx, [rdx+10h]
0x18000a414  cmp     rcx, [rax+18h]
0x18000a418  ja      loc_18000A54E
0x18000a41e  mov     [rax+10h], rcx
0x18000a422  test    rdx, rdx
0x18000a425  jz      loc_18000A6A2
0x18000a42b  mov     ecx, r8d
0x18000a42e  imul    ecx, edi
0x18000a431  add     rcx, r9
0x18000a434  mov     [rdx], rcx
0x18000a437  mov     [rdx+8], rdi
0x18000a43b  mov     al, 1
0x18000a43d  test    al, al
0x18000a43f  jz      loc_18000A65D
0x18000a445  mov     eax, 1
0x18000a44a  add     r15d, eax
0x18000a44d  inc     r8d
0x18000a450  mov     [rbp+dwGranularity], r8d
0x18000a454  add     r14d, r12d
0x18000a457  cmp     r15d, r13d
0x18000a45a  jb      short loc_18000A3ED
0x18000a45c  mov     r12, [rbp+var_30]
0x18000a460  mov     r15d, [rbp+arg_8]
0x18000a464  mov     rcx, [rbp+var_48]
0x18000a468  jmp     loc_18000A1BA
0x18000a46d  mov     byte ptr [rbx+78h], 1
0x18000a471  movzx   eax, word ptr [rbx+4Ah]
0x18000a475  movzx   r15d, word ptr [rbx+50h]
0x18000a47a  mov     r9, [rbx+8]
0x18000a47e  mov     [rbp+Addresses], r9
0x18000a482  movzx   edi, word ptr [rbx+48h]
0x18000a486  cmp     r15d, eax
0x18000a489  jz      loc_18000A631
0x18000a48f  mov     eax, edi
0x18000a491  shr     eax, 5
0x18000a494  mov     [rbp+var_50], eax
0x18000a497  mov     r12d, r10d
0x18000a49a  mov     r13d, r10d
0x18000a49d  mov     r14d, r10d
0x18000a4a0  test    r15d, r15d
0x18000a4a3  jz      short loc_18000A511
0x18000a4a5  mov     ecx, r14d
  ... truncated ...
```
