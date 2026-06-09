# CPageFile::FreePage(ulong,ulong)

- ea: `0x180019fec`
- end: `0x18001a4d0`
- name: `?FreePage@CPageFile@@QEAAKKK@Z`
- size: `1252`
- prototype: `__int64 __fastcall(CPageFile *this, int, unsigned int)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180011904`
- `0x1800141f0`

## callees

- `0x1800012b8`
- `0x18000f2ac`
- `0x180019fec`
- `0x18001a4d8`
- `0x18001a51c`
- `0x18001b434`
- `0x180024854`
- `0x180024d8c`
- `0x18003d184`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18001a017`
- `wbemcomn!GetMemLogObject` at `0x18001a096`
- `wbemcomn!GetMemLogObject` at `0x18001a101`
- `wbemcomn!GetMemLogObject` at `0x18001a017`
- `wbemcomn!GetMemLogObject` at `0x18001a096`
- `wbemcomn!GetMemLogObject` at `0x18001a101`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001a027`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001a0a6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001a111`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001a027`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001a0a6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001a111`

## pseudocode

```c
__int64 __fastcall CPageFile::FreePage(CPageFile *this, int a2, unsigned int a3)
{
  CMemoryLog *MemLogObject; // rax
  unsigned int v5; // ebx
  CVarObjHeap *v6; // rcx
  __int64 v7; // rdx
  __int64; // rax
  __int64 v9; // rcx
  CMemoryLog *v10; // rax
  __int64 v11; // r13
  int v12; // edi
  CMemoryLog *v13; // rax
  unsigned __int64 v14; // rdx
  unsigned __int64 v15; // rdx
  unsigned __int64 v16; // rdx
  unsigned __int64 v17; // rdx
  CMemoryLog *v18; // rax
  __m128i v19; // [rsp+20h] [rbp-48h] BYREF
  __int64 v20; // [rsp+30h] [rbp-38h]
  int v21; // [rsp+78h] [rbp+10h] BYREF
  unsigned int v22; // [rsp+80h] [rbp+18h] BYREF

  v22 = a3;
  v21 = a2;
  if ( !*((_DWORD *)this + 49) )
  {
    MemLogObject = GetMemLogObject();
    v5 = 4317;
    CMemoryLog::Write(MemLogObject, 4317);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v7 = 70;
LABEL_6:
    WPP_SF_d(*((_QWORD *)v6 + 2), v7, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids, v5);
LABEL_7:
     = v5;
    goto LABEL_52;
  }
  v9 = *((_QWORD *)this + 41);
  if ( a3 >= 0xAAAAAAAAAAAAAAABuLL * ((*((_QWORD *)this + 42) - v9) >> 3) )
  {
    v10 = GetMemLogObject();
    v5 = 87;
    CMemoryLog::Write(v10, 87);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v7 = 71;
    goto LABEL_6;
  }
  v11 = 3LL * a3;
  v19 = *(__m128i *)(v9 + 24LL * a3);
  v20 = *(_QWORD *)(v9 + 24LL * a3 + 16);
  v12 = _mm_cvtsi128_si32(v19);
  if ( v12 == -1 )
  {
    CRepositoryCorruption::SetRepositoryCorrupted(2, 0, 0);
    v13 = GetMemLogObject();
    CMemoryLog::Write(v13, 4317);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids, 4317);
    }
     = 4317;
    goto LABEL_52;
  }
  std::vector<unsigned long,wbem_allocator<unsigned long>>::reserve(
    (char *)this + 400,
    ((__int64)(*((_QWORD *)this + 51) - *((_QWORD *)this + 50)) >> 2) + 1);
  v14 = ((__int64)(*((_QWORD *)this + 51) - *((_QWORD *)this + 50)) >> 2) + 1;
  if ( (__int64)(*((_QWORD *)this + 38) - *((_QWORD *)this + 37)) >> 2 > v14 )
    v14 = (__int64)(*((_QWORD *)this + 38) - *((_QWORD *)this + 37)) >> 2;
  std::vector<unsigned long,wbem_allocator<unsigned long>>::reserve((char *)this + 296, v14);
  if ( v12 >= 0 )
  {
    if ( (v12 & 0x40000000) != 0 )
    {
      std::vector<PageMapEntry,wbem_allocator<PageMapEntry>>::reserve(
        (char *)this + 432,
        0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)this + 55) - *((_QWORD *)this + 54)) >> 3) + 1);
      goto LABEL_34;
    }
    std::vector<unsigned long,wbem_allocator<unsigned long>>::reserve(
      (char *)this + 352,
      0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)this + 55) - *((_QWORD *)this + 54)) >> 3)
    + ((__int64)(*((_QWORD *)this + 45) - *((_QWORD *)this + 44)) >> 2)
    + 1);
    std::vector<unsigned long,wbem_allocator<unsigned long>>::reserve(
      (char *)this + 376,
      0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)this + 55) - *((_QWORD *)this + 54)) >> 3)
    + ((__int64)(*((_QWORD *)this + 45) - *((_QWORD *)this + 44)) >> 2)
    + 1);
    v17 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)this + 55) - *((_QWORD *)this + 54)) >> 3)
        + ((__int64)(*((_QWORD *)this + 45) - *((_QWORD *)this + 44)) >> 2)
        + 1;
    if ( (__int64)(*((_QWORD *)this + 32) - *((_QWORD *)this + 31)) >> 2 > v17 )
      v17 = (__int64)(*((_QWORD *)this + 32) - *((_QWORD *)this + 31)) >> 2;
    std::vector<unsigned long,wbem_allocator<unsigned long>>::reserve((char *)this + 248, v17);
    v16 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)this + 55) - *((_QWORD *)this + 54)) >> 3)
        + ((__int64)(*((_QWORD *)this + 45) - *((_QWORD *)this + 44)) >> 2)
        + 1;
    if ( (__int64)(*((_QWORD *)this + 32) - *((_QWORD *)this + 31)) >> 2 > v16 )
      v16 = (__int64)(*((_QWORD *)this + 32) - *((_QWORD *)this + 31)) >> 2;
  }
  else
  {
    std::vector<unsigned long,wbem_allocator<unsigned long>>::reserve(
      (char *)this + 352,
      0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)this + 55) - *((_QWORD *)this + 54)) >> 3)
    + ((__int64)(*((_QWORD *)this + 45) - *((_QWORD *)this + 44)) >> 2)
    + 1);
    std::vector<unsigned long,wbem_allocator<unsigned long>>::reserve(
      (char *)this + 376,
      0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)this + 55) - *((_QWORD *)this + 54)) >> 3)
    + ((__int64)(*((_QWORD *)this + 45) - *((_QWORD *)this + 44)) >> 2)
    + 1);
    v15 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)this + 55) - *((_QWORD *)this + 54)) >> 3)
        + ((__int64)(*((_QWORD *)this + 45) - *((_QWORD *)this + 44)) >> 2)
        + 1;
    if ( (__int64)(*((_QWORD *)this + 32) - *((_QWORD *)this + 31)) >> 2 > v15 )
      v15 = (__int64)(*((_QWORD *)this + 32) - *((_QWORD *)this + 31)) >> 2;
    std::vector<unsigned long,wbem_allocator<unsigned long>>::reserve((char *)this + 248, v15);
    v16 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)this + 55) - *((_QWORD *)this + 54)) >> 3)
        + ((__int64)(*((_QWORD *)this + 45) - *((_QWORD *)this + 44)) >> 2)
        + 1;
    if ( (__int64)(*((_QWORD *)this + 32) - *((_QWORD *)this + 31)) >> 2 > v16 )
      v16 = (__int64)(*((_QWORD *)this + 32) - *((_QWORD *)this + 31)) >> 2;
  }
  std::vector<unsigned long,wbem_allocator<unsigned long>>::reserve((char *)this + 272, v16);
LABEL_34:
  *(_DWORD *)(*((_QWORD *)this + 41) + 8 * v11) = -1;
  std::vector<unsigned long,wbem_allocator<unsigned long>>::push_back((char *)this + 400, &v22);
  if ( v12 == -2 )
    goto LABEL_49;
  if ( __eh34_try(-1, 2) )
  {
    __eh34_scope_strut(2);
    if ( v12 < 0 )
    {
      v12 &= 0x3FFFFFFFu;
      v21 = v12;
      std::vector<unsigned long,wbem_allocator<unsigned long>>::push_back((char *)this + 352, &v21);
      std::vector<unsigned long,wbem_allocator<unsigned long>>::push_back((char *)this + 376, &qword_18004B1F8);
    }
    else
    {
      if ( (v12 & 0x40000000) != 0 )
      {
        v19.m128i_i32[0] = v12 & 0x3FFFFFFF;
        std::vector<PageMapEntry,wbem_allocator<PageMapEntry>>::push_back((char *)this + 432, &v19);
        goto LABEL_49;
      }
      v21 = v12 & 0x3FFFFFFF;
      std::vector<unsigned long,wbem_allocator<unsigned long>>::push_back((char *)this + 352, &v21);
      std::vector<unsigned long,wbem_allocator<unsigned long>>::push_back((char *)this + 376, &FREE_PAGE_AGE_INIT_VALUE);
    }
    CPageCache::Discard((CPageFile *)((char *)this + 64), v12);
  }
  if ( __eh34_catch(2) )
  {
    if ( __eh34_catch_type(2, &CX_MemoryException `RTTI Type Descriptor', 0) )
    {
      v18 = GetMemLogObject();
      CMemoryLog::Write(v18, 14);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids, 14);
      }
       = 14;
      __eh34_try_continuation(2, &CX_MemoryException `RTTI Type Descriptor', &loc_18001A4AE);
LABEL_52:
      ;
    }
  }
LABEL_49:
   = 0;
  goto LABEL_52;
}

```

## disassembly

```asm
0x180019fec  mov     rax, rsp
0x180019fef  mov     [rax+8], rbx
0x180019ff3  mov     [rax+20h], rsi
0x180019ff7  mov     [rax+18h], r8d
0x180019ffb  mov     [rax+10h], edx
0x180019ffe  push    rdi
0x180019fff  push    r12
0x18001a001  push    r13
0x18001a003  push    r14
0x18001a005  push    r15
0x18001a007  sub     rsp, 40h
0x18001a00b  mov     rbx, rcx
0x18001a00e  cmp     dword ptr [rcx+0C4h], 0
0x18001a015  jnz     short loc_18001A06B
0x18001a017  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001a01d  mov     ebx, 10DDh
0x18001a022  mov     edx, ebx
0x18001a024  mov     rcx, rax
0x18001a027  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001a02d  lea     rax, WPP_GLOBAL_Control
0x18001a034  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a03b  cmp     rcx, rax
0x18001a03e  jz      short loc_18001A064
0x18001a040  test    byte ptr [rcx+1Ch], 1
0x18001a044  jz      short loc_18001A064
0x18001a046  cmp     byte ptr [rcx+19h], 2
0x18001a04a  jb      short loc_18001A064
0x18001a04c  mov     edx, 46h ; 'F'
0x18001a051  mov     r9d, ebx
0x18001a054  lea     r8, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids
0x18001a05b  mov     rcx, [rcx+10h]
0x18001a05f  call    WPP_SF_d
0x18001a064  mov     eax, ebx
0x18001a066  jmp     loc_18001A4B5
0x18001a06b  mov     rcx, [rcx+148h]
0x18001a072  mov     edx, r8d
0x18001a075  mov     rax, [rbx+150h]
0x18001a07c  sub     rax, rcx
0x18001a07f  sar     rax, 3
0x18001a083  mov     r14, 0AAAAAAAAAAAAAAABh
0x18001a08d  imul    rax, r14
0x18001a091  cmp     rdx, rax
0x18001a094  jb      short loc_18001A0D0
0x18001a096  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001a09c  mov     ebx, 57h ; 'W'
0x18001a0a1  mov     edx, ebx
0x18001a0a3  mov     rcx, rax
0x18001a0a6  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001a0ac  lea     rax, WPP_GLOBAL_Control
0x18001a0b3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a0ba  cmp     rcx, rax
0x18001a0bd  jz      short loc_18001A064
0x18001a0bf  test    byte ptr [rcx+1Ch], 1
0x18001a0c3  jz      short loc_18001A064
0x18001a0c5  cmp     byte ptr [rcx+19h], 2
0x18001a0c9  jb      short loc_18001A064
0x18001a0cb  lea     edx, [rbx-10h]
0x18001a0ce  jmp     short loc_18001A051
0x18001a0d0  lea     r13, [rdx+rdx*2]
0x18001a0d4  movups  xmm1, xmmword ptr [rcx+r13*8]
0x18001a0d9  movups  [rsp+68h+var_48], xmm1
0x18001a0de  movsd   xmm0, qword ptr [rcx+r13*8+10h]
0x18001a0e5  movsd   [rsp+68h+var_38], xmm0
0x18001a0eb  movd    edi, xmm1
0x18001a0ef  cmp     edi, 0FFFFFFFFh
0x18001a0f2  jnz     short loc_18001A155
0x18001a0f4  xor     r8d, r8d; unsigned int
0x18001a0f7  xor     edx, edx; bool
0x18001a0f9  lea     ecx, [rdx+2]; int
0x18001a0fc  call    ?SetRepositoryCorrupted@CRepositoryCorruption@@SAJJ_NK@Z; CRepositoryCorruption::SetRepositoryCorrupted(long,bool,ulong)
0x18001a101  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001a107  mov     ebx, 10DDh
0x18001a10c  mov     edx, ebx
0x18001a10e  mov     rcx, rax
0x18001a111  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001a117  lea     rax, WPP_GLOBAL_Control
0x18001a11e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a125  cmp     rcx, rax
0x18001a128  jz      short loc_18001A14E
0x18001a12a  test    byte ptr [rcx+1Ch], 1
0x18001a12e  jz      short loc_18001A14E
0x18001a130  cmp     byte ptr [rcx+19h], 2
0x18001a134  jb      short loc_18001A14E
0x18001a136  mov     edx, 48h ; 'H'
0x18001a13b  mov     r9d, ebx
0x18001a13e  lea     r8, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids
0x18001a145  mov     rcx, [rcx+10h]
0x18001a149  call    WPP_SF_d
0x18001a14e  mov     eax, ebx
0x18001a150  jmp     loc_18001A4B5
0x18001a155  lea     r15, [rbx+190h]
0x18001a15c  mov     rdx, [r15+8]
0x18001a160  sub     rdx, [r15]
0x18001a163  sar     rdx, 2
0x18001a167  inc     rdx
0x18001a16a  mov     rcx, r15
0x18001a16d  call    ?reserve@?$vector@KV?$wbem_allocator@K@@@std@@QEAAX_K@Z; std::vector<ulong,wbem_allocator<ulong>>::reserve(unsigned __int64)
0x18001a172  lea     rcx, [rbx+128h]
0x18001a179  mov     rdx, [r15+8]
0x18001a17d  sub     rdx, [r15]
0x18001a180  sar     rdx, 2
0x18001a184  inc     rdx
0x18001a187  mov     rax, [rcx+8]
0x18001a18b  sub     rax, [rcx]
0x18001a18e  sar     rax, 2
0x18001a192  cmp     rax, rdx
0x18001a195  cmova   rdx, rax
0x18001a199  call    ?reserve@?$vector@KV?$wbem_allocator@K@@@std@@QEAAX_K@Z; std::vector<ulong,wbem_allocator<ulong>>::reserve(unsigned __int64)
0x18001a19e  mov     r12d, edi
0x18001a1a1  and     r12d, 80000000h
0x18001a1a8  lea     rsi, [rbx+1B0h]
0x18001a1af  jz      loc_18001A2C0
0x18001a1b5  lea     r14, [rbx+160h]
0x18001a1bc  mov     rcx, [rsi+8]
0x18001a1c0  sub     rcx, [rsi]
0x18001a1c3  sar     rcx, 3
0x18001a1c7  mov     rax, 0AAAAAAAAAAAAAAABh
0x18001a1d1  imul    rcx, rax
0x18001a1d5  mov     rdx, [r14+8]
0x18001a1d9  sub     rdx, [r14]
0x18001a1dc  sar     rdx, 2
0x18001a1e0  inc     rdx
0x18001a1e3  add     rdx, rcx
0x18001a1e6  mov     rcx, r14
0x18001a1e9  call    ?reserve@?$vector@KV?$wbem_allocator@K@@@std@@QEAAX_K@Z; std::vector<ulong,wbem_allocator<ulong>>::reserve(unsigned __int64)
0x18001a1ee  mov     rcx, [rsi+8]
0x18001a1f2  sub     rcx, [rsi]
0x18001a1f5  sar     rcx, 3
0x18001a1f9  mov     rax, 0AAAAAAAAAAAAAAABh
0x18001a203  imul    rcx, rax
0x18001a207  mov     rdx, [r14+8]
0x18001a20b  sub     rdx, [r14]
0x18001a20e  sar     rdx, 2
0x18001a212  inc     rdx
0x18001a215  add     rdx, rcx
0x18001a218  lea     rcx, [rbx+178h]
0x18001a21f  call    ?reserve@?$vector@KV?$wbem_allocator@K@@@std@@QEAAX_K@Z; std::vector<ulong,wbem_allocator<ulong>>::reserve(unsigned __int64)
0x18001a224  lea     r8, [rbx+0F8h]
0x18001a22b  mov     rcx, [rsi+8]
0x18001a22f  sub     rcx, [rsi]
0x18001a232  sar     rcx, 3
0x18001a236  mov     rax, 0AAAAAAAAAAAAAAABh
0x18001a240  imul    rcx, rax
0x18001a244  mov     rdx, [r14+8]
0x18001a248  sub     rdx, [r14]
0x18001a24b  sar     rdx, 2
0x18001a24f  inc     rdx
0x18001a252  add     rdx, rcx
0x18001a255  mov     rax, [r8+8]
0x18001a259  sub     rax, [r8]
0x18001a25c  sar     rax, 2
0x18001a260  cmp     rax, rdx
0x18001a263  cmova   rdx, rax
0x18001a267  mov     rcx, r8
0x18001a26a  call    ?reserve@?$vector@KV?$wbem_allocator@K@@@std@@QEAAX_K@Z; std::vector<ulong,wbem_allocator<ulong>>::reserve(unsigned __int64)
0x18001a26f  mov     rcx, [rsi+8]
0x18001a273  sub     rcx, [rsi]
0x18001a276  sar     rcx, 3
0x18001a27a  mov     rax, 0AAAAAAAAAAAAAAABh
0x18001a284  imul    rcx, rax
0x18001a288  mov     rdx, [r14+8]
0x18001a28c  sub     rdx, [r14]
0x18001a28f  sar     rdx, 2
0x18001a293  inc     rdx
0x18001a296  add     rdx, rcx
0x18001a299  lea     rcx, [rbx+0F8h]
0x18001a2a0  mov     rax, [rcx+8]
0x18001a2a4  sub     rax, [rcx]
0x18001a2a7  sar     rax, 2
0x18001a2ab  cmp     rax, rdx
0x18001a2ae  cmova   rdx, rax
0x18001a2b2  lea     rcx, [rbx+110h]
0x18001a2b9  call    ?reserve@?$vector@KV?$wbem_allocator@K@@@std@@QEAAX_K@Z; std::vector<ulong,wbem_allocator<ulong>>::reserve(unsigned __int64)
0x18001a2be  jmp     short loc_18001A2E0
0x18001a2c0  bt      edi, 1Eh
0x18001a2c4  jnb     short loc_18001A2E5
0x18001a2c6  mov     rdx, [rsi+8]
0x18001a2ca  sub     rdx, [rsi]
0x18001a2cd  sar     rdx, 3
0x18001a2d1  imul    rdx, r14
0x18001a2d5  inc     rdx
0x18001a2d8  mov     rcx, rsi
0x18001a2db  call    ?reserve@?$vector@UPageMapEntry@@V?$wbem_allocator@UPageMapEntry@@@@@std@@QEAAX_K@Z; std::vector<PageMapEntry,wbem_allocator<PageMapEntry>>::reserve(unsigned __int64)
0x18001a2e0  jmp     loc_18001A3EE
0x18001a2e5  lea     r14, [rbx+160h]
0x18001a2ec  mov     rcx, [rsi+8]
0x18001a2f0  sub     rcx, [rsi]
0x18001a2f3  sar     rcx, 3
0x18001a2f7  mov     rax, 0AAAAAAAAAAAAAAABh
0x18001a301  imul    rcx, rax
0x18001a305  mov     rdx, [r14+8]
0x18001a309  sub     rdx, [r14]
0x18001a30c  sar     rdx, 2
0x18001a310  inc     rdx
0x18001a313  add     rdx, rcx
0x18001a316  mov     rcx, r14
0x18001a319  call    ?reserve@?$vector@KV?$wbem_allocator@K@@@std@@QEAAX_K@Z; std::vector<ulong,wbem_allocator<ulong>>::reserve(unsigned __int64)
0x18001a31e  mov     rcx, [rsi+8]
0x18001a322  sub     rcx, [rsi]
0x18001a325  sar     rcx, 3
0x18001a329  mov     rax, 0AAAAAAAAAAAAAAABh
0x18001a333  imul    rcx, rax
0x18001a337  mov     rdx, [r14+8]
0x18001a33b  sub     rdx, [r14]
0x18001a33e  sar     rdx, 2
0x18001a342  inc     rdx
0x18001a345  add     rdx, rcx
0x18001a348  lea     rcx, [rbx+178h]
0x18001a34f  call    ?reserve@?$vector@KV?$wbem_allocator@K@@@std@@QEAAX_K@Z; std::vector<ulong,wbem_allocator<ulong>>::reserve(unsigned __int64)
0x18001a354  lea     r8, [rbx+0F8h]
0x18001a35b  mov     rcx, [rsi+8]
0x18001a35f  sub     rcx, [rsi]
0x18001a362  sar     rcx, 3
0x18001a366  mov     rax, 0AAAAAAAAAAAAAAABh
0x18001a370  imul    rcx, rax
0x18001a374  mov     rdx, [r14+8]
0x18001a378  sub     rdx, [r14]
0x18001a37b  sar     rdx, 2
0x18001a37f  inc     rdx
0x18001a382  add     rdx, rcx
0x18001a385  mov     rax, [r8+8]
0x18001a389  sub     rax, [r8]
0x18001a38c  sar     rax, 2
0x18001a390  cmp     rax, rdx
0x18001a393  cmova   rdx, rax
0x18001a397  mov     rcx, r8
0x18001a39a  call    ?reserve@?$vector@KV?$wbem_allocator@K@@@std@@QEAAX_K@Z; std::vector<ulong,wbem_allocator<ulong>>::reserve(unsigned __int64)
0x18001a39f  mov     rcx, [rsi+8]
0x18001a3a3  sub     rcx, [rsi]
0x18001a3a6  sar     rcx, 3
0x18001a3aa  mov     rax, 0AAAAAAAAAAAAAAABh
0x18001a3b4  imul    rcx, rax
0x18001a3b8  mov     rdx, [r14+8]
0x18001a3bc  sub     rdx, [r14]
0x18001a3bf  sar     rdx, 2
0x18001a3c3  inc     rdx
0x18001a3c6  add     rdx, rcx
0x18001a3c9  lea     rcx, [rbx+0F8h]
0x18001a3d0  mov     rax, [rcx+8]
0x18001a3d4  sub     rax, [rcx]
0x18001a3d7  sar     rax, 2
0x18001a3db  cmp     rax, rdx
0x18001a3de  cmova   rdx, rax
0x18001a3e2  lea     rcx, [rbx+110h]
0x18001a3e9  call    ?reserve@?$vector@KV?$wbem_allocator@K@@@std@@QEAAX_K@Z; std::vector<ulong,wbem_allocator<ulong>>::reserve(unsigned __int64)
0x18001a3ee  mov     rax, [rbx+148h]
0x18001a3f5  mov     dword ptr [rax+r13*8], 0FFFFFFFFh
0x18001a3fd  lea     rdx, [rsp+68h+arg_10]
0x18001a405  mov     rcx, r15
0x18001a408  call    ?push_back@?$vector@KV?$wbem_allocator@K@@@std@@QEAAXAEBK@Z; std::vector<ulong,wbem_allocator<ulong>>::push_back(ulong const &)
0x18001a40d  nop
0x18001a40e  cmp     edi, 0FFFFFFFEh
0x18001a411  jnz     short loc_18001A41A
0x18001a413  xor     eax, eax
0x18001a415  jmp     loc_18001A4B5
0x18001a41a  test    r12d, r12d
0x18001a41d  jz      short loc_18001A44F
0x18001a41f  and     edi, 3FFFFFFFh
0x18001a425  mov     [rsp+68h+arg_8], edi
0x18001a429  lea     rcx, [rbx+160h]
0x18001a430  lea     rdx, [rsp+68h+arg_8]
0x18001a435  call    ?push_back@?$vector@KV?$wbem_allocator@K@@@std@@QEAAX$$QEAK@Z; std::vector<ulong,wbem_allocator<ulong>>::push_back(ulong &&)
0x18001a43a  lea     rcx, [rbx+178h]
0x18001a441  lea     rdx, qword_18004B1F8
0x18001a448  call    ?push_back@?$vector@KV?$wbem_allocator@K@@@std@@QEAAXAEBK@Z; std::vector<ulong,wbem_allocator<ulong>>::push_back(ulong const &)
0x18001a44d  jmp     short loc_18001A49D
0x18001a44f  bt      edi, 1Eh
0x18001a453  jnb     short loc_18001A46E
0x18001a455  and     edi, 3FFFFFFFh
0x18001a45b  mov     dword ptr [rsp+68h+var_48], edi
0x18001a45f  lea     rdx, [rsp+68h+var_48]
0x18001a464  mov     rcx, rsi
0x18001a467  call    ?push_back@?$vector@UPageMapEntry@@V?$wbem_allocator@UPageMapEntry@@@@@std@@QEAAXAEBUPageMapEntry@@@Z; std::vector<PageMapEntry,wbem_allocator<PageMapEntry>>::push_back(PageMapEntry const &)
0x18001a46c  jmp     short loc_18001A4A9
0x18001a46e  mov     eax, edi
0x18001a470  and     eax, 3FFFFFFFh
0x18001a475  mov     [rsp+68h+arg_8], eax
0x18001a479  lea     rcx, [rbx+160h]
0x18001a480  lea     rdx, [rsp+68h+arg_8]
0x18001a485  call    ?push_back@?$vector@KV?$wbem_allocator@K@@@std@@QEAAX$$QEAK@Z; std::vector<ulong,wbem_allocator<ulong>>::push_back(ulong &&)
0x18001a48a  lea     rcx, [rbx+178h]
0x18001a491  lea     rdx, ?FREE_PAGE_AGE_INIT_VALUE@@3KA; ulong FREE_PAGE_AGE_INIT_VALUE
0x18001a498  call    ?push_back@?$vector@KV?$wbem_allocator@K@@@std@@QEAAXAEBK@Z; std::vector<ulong,wbem_allocator<ulong>>::push_back(ulong const &)
0x18001a49d  mov     edx, edi; unsigned int
0x18001a49f  lea     rcx, [rbx+40h]; this
0x18001a4a3  call    ?Discard@CPageCache@@QEAAKK@Z; CPageCache::Discard(ulong)
0x18001a4a8  nop
0x18001a4a9  jmp     loc_18001A413
0x18001a4ae  jmp     short $+2
0x18001a4b0  mov     eax, 0Eh
0x18001a4b5  lea     r11, [rsp+68h+var_28]
0x18001a4ba  mov     rbx, [r11+30h]
0x18001a4be  mov     rsi, [r11+48h]
0x18001a4c2  mov     rsp, r11
0x18001a4c5  pop     r15
0x18001a4c7  pop     r14
0x18001a4c9  pop     r13
0x18001a4cb  pop     r12
0x18001a4cd  pop     rdi
0x18001a4ce  retn
  ... truncated ...
```
