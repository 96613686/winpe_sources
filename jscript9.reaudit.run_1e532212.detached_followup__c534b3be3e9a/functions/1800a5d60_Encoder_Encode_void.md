# Encoder::Encode(void)

- ea: `0x1800a5d60`
- end: `0x1800a688a`
- name: `?Encode@Encoder@@QEAAXXZ`
- size: `2858`
- prototype: `void __fastcall(Encoder *__hidden this)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800ca898`

## callees

- `0x180082510`
- `0x1800a0530`
- `0x1800a2258`
- `0x1800a558c`
- `0x1800a5c6c`
- `0x1800a5d28`
- `0x1800a5d60`
- `0x1800a6890`
- `0x1800a7b94`
- `0x1800a81d8`
- `0x1800a81fc`
- `0x1800ee930`
- `0x180102e18`
- `0x1801088cc`
- `0x18016fb18`
- `0x1801810c8`
- `0x1801a0e70`
- `0x1801aa060`
- `0x1801aa070`
- `0x1801c989b`
- `0x180320d80`
- `0x180341b51`
- `0x18035e010`

## import_xrefs

- `msvcrt!free` at `0x1800a6462`
- `msvcrt!free` at `0x1800a6462`
- `msvcrt!memcpy_s` at `0x1800a623a`
- `msvcrt!memcpy_s` at `0x1800a623a`
- `KERNEL32!FlushInstructionCache` at `0x1800a6297`
- `KERNEL32!FlushInstructionCache` at `0x1800a6297`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Encoder::Encode(Encode *this)
{
  Encode *v1; // r13
  __int64 v2; // rdx
  __int64 v3; // rcx
  unsigned int v4; // ecx
  _QWORD *i; // rax
  unsigned __int8 *v6; // r14
  unsigned __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rbx
  __int64 v10; // rcx
  __int64 v11; // rdi
  char v12; // al
  IR::Instr *v13; // r12
  char v14; // si
  IR::Instr *v15; // rbx
  __int64 v16; // rsi
  _BYTE *v17; // r14
  int Op; // r9d
  __int64 v19; // r11
  char v20; // r8
  _BYTE *v21; // rdx
  __int64 v22; // r10
  char v23; // r8
  int v24; // r8d
  struct BailOutInfo *BailOutInfo; // rax
  struct BailOutInfo *v26; // r8
  __int64 v27; // rcx
  __int64 v28; // r10
  __int64 v29; // rdx
  int j; // r9d
  int *k; // r10
  unsigned int v32; // eax
  bool v33; // zf
  int v34; // edx
  int v35; // r11d
  __int64 v36; // rax
  EmitBufferManager *v37; // rdi
  SIZE_T v38; // r15
  unsigned __int8 *v39; // r10
  __int64 *m; // r8
  __int64 v41; // r9
  int v42; // ecx
  char *v43; // r12
  __int64 v44; // r14
  char *v45; // rsi
  rsize_t v46; // rdi
  char *v47; // r13
  __int64 v48; // rdx
  size_t v49; // r8
  __int64 v50; // rax
  __int64 v51; // rdx
  __int64 v52; // r14
  __int64 v53; // rsi
  __int64 v54; // rax
  unsigned int v55; // esi
  __int64 v56; // rax
  __int64 v57; // r14
  __int64 v58; // rax
  __int64 v59; // rbx
  char *v60; // rdi
  struct Js::EntryPointInfo *v61; // rax
  unsigned __int8 *v62; // rdx
  _QWORD *v63; // rcx
  _QWORD *v64; // rbx
  __int64 v65; // rcx
  __int64 v66; // r8
  __int64 v67; // rdx
  const struct Func *TopFunc; // rax
  unsigned int v69; // r14d
  const struct Func *v70; // rax
  Js::FunctionBody *v71; // r13
  unsigned int v72; // r15d
  struct Js::EntryPointInfo *EntryPointInfo; // rax
  __int64 v74; // rsi
  char *v75; // rdi
  int v76; // ecx
  int v77; // r8d
  int v78; // edi
  __int64 v79; // rbx
  __int64 v80; // rcx
  unsigned __int64 v81; // r15
  int v82; // ebx
  __int64 v83; // rcx
  _DWORD *v84; // rax
  rsize_t v85; // rdi
  char v86; // [rsp+30h] [rbp-D0h]
  unsigned int v87; // [rsp+34h] [rbp-CCh]
  unsigned int v88; // [rsp+38h] [rbp-C8h] BYREF
  rsize_t SourceSize; // [rsp+40h] [rbp-C0h] BYREF
  __m128i si128; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v91; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int8 *v92; // [rsp+68h] [rbp-98h] BYREF
  __int64 v93; // [rsp+70h] [rbp-90h]
  Js::FunctionBody *v94; // [rsp+78h] [rbp-88h]
  __int64 v95; // [rsp+80h] [rbp-80h]
  __int64 v96; // [rsp+88h] [rbp-78h]
  SIZE_T dwSize; // [rsp+98h] [rbp-68h]
  LPCVOID lpBaseAddress; // [rsp+A0h] [rbp-60h]
  _QWORD v99[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v100; // [rsp+C0h] [rbp-40h]
  void *Block; // [rsp+D0h] [rbp-30h]
  __int64 v102; // [rsp+D8h] [rbp-28h]
  __int64 v103; // [rsp+E0h] [rbp-20h]
  char v104; // [rsp+E8h] [rbp-18h]
  __int64 v105; // [rsp+F0h] [rbp-10h]
  __int64 v106; // [rsp+F8h] [rbp-8h]
  int v107; // [rsp+100h] [rbp+0h]
  __int64 v108; // [rsp+108h] [rbp+8h]
  __int64 v109; // [rsp+110h] [rbp+10h]

  v109 = -2;
  v1 = this;
  v2 = *(_QWORD *)this;
  v3 = *(_QWORD *)(**(_QWORD **)this + 40LL);
  v99[0] = Js::Throw::OutOfMemory;
  v99[1] = 0;
  v100 = 0;
  Block = 0;
  v102 = v3;
  v103 = 0;
  v104 = 0;
  v105 = 0;
  v106 = 0;
  v107 = 0;
  v108 = 0;
  *((_QWORD *)v1 + 9) = v99;
  v4 = 0;
  for ( i = *(_QWORD **)(v2 + 80); i; i = (_QWORD *)*i )
    ++v4;
  v6 = (unsigned __int8 *)v1 + 8;
  v92 = (unsigned __int8 *)v1 + 8;
  *((_QWORD *)v1 + 3) = v1;
  *((_QWORD *)v1 + 5) = 0;
  v7 = 12LL * v4;
  if ( v7 >= 0x100000000LL )
    Math::DefaultOverflowPolicy();
  *((_DWORD *)v1 + 16) = v7;
  if ( (_DWORD)v7 )
    v8 = (__int64)ArenaAllocator::Alloc(*((ArenaAllocator **)v1 + 9), (unsigned __int64 *)(unsigned int)v7);
  else
    v8 = 8;
  *((_QWORD *)v1 + 6) = v8;
  *((_QWORD *)v1 + 7) = v8;
  v9 = *(_QWORD *)v1;
  v10 = *(_QWORD *)(*(_QWORD *)v1 + 8LL);
  v96 = v10;
  LODWORD(v11) = -1;
  v93 = 0xFFFFFFFFLL;
  v12 = *(_BYTE *)(v10 + 56);
  if ( v12 )
  {
    if ( v12 == 1 )
    {
      v94 = *(Js::FunctionBody **)(v10 + 40);
      v11 = (__int64)(*(_QWORD *)(v10 + 88) - *(_QWORD *)(*((_QWORD *)v94 + 38) + 32LL)) >> 5;
      v93 = v11;
    }
    else
    {
      v94 = 0;
    }
  }
  else
  {
    v94 = *(Js::FunctionBody **)(v10 + 40);
  }
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v13 = 0;
  v87 = 0;
  v14 = 0;
  v86 = 0;
  v15 = *(IR::Instr **)(v9 + 80);
  while ( v15 )
  {
    if ( (unsigned int)(v8 - *((_DWORD *)v1 + 12) + 12) >= *((_DWORD *)v1 + 16) )
      goto LABEL_31;
    if ( *((_BYTE *)v15 + 28) != 8 )
    {
      if ( !v13 || *((_WORD *)v15 + 12) != 686 && (*((_BYTE *)v15 + 26) & 8) == 0 )
      {
LABEL_16:
        if ( *((char *)v15 + 26) < 0 )
        {
          BailOutInfo = IR::Instr::GetBailOutInfo(v15);
          v26 = BailOutInfo;
          v27 = *((_QWORD *)BailOutInfo + 1);
          if ( v27 )
          {
            v28 = *(_QWORD *)v1;
            v29 = *((_QWORD *)BailOutInfo + 20);
            for ( j = *(_DWORD *)(*(_QWORD *)v1 + 176LL) + 16; *(_QWORD *)(v27 + 8); v29 = *(_QWORD *)(v29 + 264) )
            {
              *(_DWORD *)(v27 + 112) = *(_DWORD *)(v29 + 200) - j;
              v27 = *(_QWORD *)(v27 + 8);
            }
            if ( *((_DWORD *)BailOutInfo + 20) )
            {
              if ( *(_BYTE *)(v28 + 287) )
              {
                for ( k = (int *)**((_QWORD **)BailOutInfo + 18); k; k = (int *)*((_QWORD *)k + 1) )
                {
                  v32 = k[1];
                  v88 = 0;
                  v33 = !_BitScanForward((unsigned int *)&v34, v32);
                  if ( !v33 )
                  {
                    v35 = *k;
                    if ( v34 != -1 )
                    {
                      do
                      {
                        v32 &= ~(1 << v34);
                        *(_DWORD *)(*((_QWORD *)v26 + 17) + 4LL * (unsigned int)(v35 + v34)) -= j;
                        v88 = 0;
                        v33 = !_BitScanForward((unsigned int *)&v34, v32);
                      }
                      while ( !v33 && v34 != -1 );
                    }
                  }
                }
              }
            }
          }
        }
        if ( (*((_BYTE *)v15 + 26) & 8) != 0 )
        {
          v65 = 0;
          v66 = *((_QWORD *)v15 + 6);
          v67 = *(unsigned int *)(v66 + 16);
          if ( v67 == (*(_DWORD *)(v66 + 16) & 0xF) )
            v65 = v67 | (16LL * (unsigned int)(*((_DWORD *)v1 + 14) - *((_DWORD *)v1 + 12)));
          *(_QWORD *)(v66 + 16) = v65;
        }
        v11 = EncoderMD::Encode((EncoderMD *)v6, v15, *((unsigned __int8 **)v1 + 7), *((unsigned __int8 **)v1 + 6));
        if ( !v14 )
          goto LABEL_19;
        v16 = *(_QWORD *)v1;
        v17 = (_BYTE *)(*(_QWORD *)v1 + 137LL);
        if ( !*(_QWORD *)(*(_QWORD *)v1 + 120LL) )
          *(_QWORD *)(v16 + 120) = ArenaAllocator::Alloc(
                                     *(ArenaAllocator **)(v16 + 128),
                                     (unsigned __int64 *)(2LL * (unsigned __int8)*v17 + 16));
        Op = PrologEncoderMD::GetOp(v15);
        v20 = *(_BYTE *)(v16 + 138);
        v21 = (_BYTE *)(v16 + 136);
        if ( !v20 )
          *v21 = *v17;
        *(_BYTE *)(v16 + 138) = v20 + v11;
        if ( !(_BYTE)Op )
        {
          v22 = v19 + 2 * ((unsigned __int8)--*v21 + 8LL);
          v23 = *(_BYTE *)(*((_QWORD *)v15 + 6) + 36LL) - 1;
          goto LABEL_27;
        }
        v22 = 0;
        v23 = 0;
        if ( Op != 1 )
        {
          if ( Op == 2 )
          {
            v22 = v19 + 2 * ((unsigned __int8)--*v21 + 8LL);
            v23 = ((unsigned __int8)(*(_DWORD *)(*((_QWORD *)v15 + 7) + 16LL) - 8) >> 3) & 0xF;
            goto LABEL_27;
          }
          if ( Op == 8 )
          {
            *(_BYTE *)(v16 + 136) -= 2;
            TopFunc = Func::GetTopFunc(*((Func **)v15 + 2));
            v23 = *(_BYTE *)(*((_QWORD *)v15 + 6) + 36LL) - 17;
            *(_WORD *)(v22 + 2) = (unsigned int)(*((_DWORD *)TopFunc + 27)
                                               + *((_DWORD *)TopFunc + 28)
                                               + *(_DWORD *)(*((_QWORD *)v15 + 5) + 32LL)) >> 4;
            goto LABEL_27;
          }
          if ( Op != 255 )
          {
LABEL_27:
            *(_BYTE *)v22 = *(_BYTE *)(v16 + 138);
            *(_BYTE *)(v22 + 1) = Op & 0xF | (16 * v23);
          }
          v6 = (unsigned __int8 *)v1 + 8;
          v14 = v86;
LABEL_19:
          *((_QWORD *)v1 + 7) += v11;
          LODWORD(v8) = *((_DWORD *)v1 + 14);
          LODWORD(v11) = v93;
          goto LABEL_20;
        }
        v81 = *(int *)(*((_QWORD *)v15 + 7) + 16LL);
        if ( v81 <= 0x7FF8 )
        {
          *v21 -= 2;
          v22 = v19 + 2 * ((unsigned __int8)*v21 + 8LL);
          *(_BYTE *)(v22 + 1) ^= (*(_BYTE *)(v22 + 1) ^ Op) & 0xF;
          *(_WORD *)(v22 + 2) = v81 >> 3;
        }
        else
        {
          *v21 -= 3;
          v22 = v19 + 2 * ((unsigned __int8)*v21 + 8LL);
          v23 = 1;
          *(_BYTE *)(v22 + 1) ^= (*(_BYTE *)(v22 + 1) ^ Op) & 0xF;
          *(_DWORD *)(v22 + 2) = v81;
        }
        goto LABEL_27;
      }
      v69 = *(_DWORD *)(*((_QWORD *)Func::GetTopFunc(*((Func **)v13 + 2)) + 1) + 72LL);
      v70 = Func::GetTopFunc(*((Func **)v13 + 2));
      v71 = (Js::FunctionBody *)*((_QWORD *)v70 + 32);
      v72 = *((_DWORD *)v13 + 16);
      if ( (_DWORD)v11 == -1 )
      {
        EntryPointInfo = Js::FunctionBody::TryGetEntryPointInfo(*((Js::FunctionBody **)v70 + 32), v69);
        v74 = 0xFFFFFFFFLL;
      }
      else
      {
        v74 = (unsigned int)v11;
        EntryPointInfo = (struct Js::EntryPointInfo *)JsUtil::List<HostScriptContext *,ArenaAllocator,0,Js::CopyRemovePolicy,DefaultComparer>::Item(
                                                        *(_QWORD *)(32LL * (unsigned int)v11
                                                                  + *(_QWORD *)(*((_QWORD *)v71 + 38) + 32LL)),
                                                        v69);
      }
      v75 = (char *)*((_QWORD *)EntryPointInfo + 5);
      if ( v75 )
      {
        if ( si128.m128i_i32[1] == v72 )
        {
LABEL_91:
          v13 = 0;
          v1 = this;
          v14 = v86;
          v6 = v92;
          goto LABEL_16;
        }
      }
      else
      {
        if ( v72 == -1 )
          goto LABEL_91;
        v75 = HeapAllocator::Alloc((HeapAllocator *)HeapAllocator::Instance, 0x18u);
        *(_QWORD *)v75 = 0;
        *((_QWORD *)v75 + 1) = 0;
        *((_DWORD *)v75 + 4) = 0;
        if ( (_DWORD)v93 == -1 )
          *((_QWORD *)Js::FunctionBody::TryGetEntryPointInfo(v71, v69) + 5) = v75;
        else
          *(_QWORD *)(JsUtil::List<HostScriptContext *,ArenaAllocator,0,Js::CopyRemovePolicy,DefaultComparer>::Item(
                        *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v71 + 38) + 32LL) + 32 * v74),
                        v69)
                    + 40) = v75;
      }
      v91 = __PAIR64__(v87, v72);
      Js::SmallSpanSequence::RecordARange(
        (Js::SmallSpanSequence *)v75,
        (struct Js::SmallSpanSequenceIter *)&si128,
        (struct Js::StatementData *)&v91);
      goto LABEL_91;
    }
    v24 = *((unsigned __int16 *)v15 + 12);
    if ( v24 == 624 )
    {
      v87 = v8 - *((_DWORD *)v1 + 12);
      v13 = v15;
      goto LABEL_16;
    }
    v77 = v24 - 676;
    if ( v77 )
    {
      if ( v77 == 1 )
      {
        v14 = 0;
        v86 = 0;
        v15 = *(IR::Instr **)v15;
      }
      else
      {
LABEL_20:
        v15 = *(IR::Instr **)v15;
      }
    }
    else
    {
      v14 = 1;
      v86 = 1;
      v15 = *(IR::Instr **)v15;
    }
  }
  v92 = 0;
  v95 = *((_QWORD *)v1 + 7) - *((_QWORD *)v1 + 6);
  v36 = *(_QWORD *)v1;
  v37 = (EmitBufferManager *)(*(_QWORD *)(*(_QWORD *)v1 + 72LL) + 96LL);
  v91 = (unsigned __int64)v37;
  v38 = (unsigned int)v95;
  SourceSize = (unsigned int)v95;
  si128.m128i_i64[0] = (__int64)EmitBufferManager::AllocateBuffer(
                                  v37,
                                  (unsigned int)v95,
                                  &v92,
                                  0,
                                  1u,
                                  2 * (*(unsigned __int8 *)(v36 + 137) + 2));
  v39 = v92;
  if ( !v92 )
    Js::Throw::OutOfMemory();
  for ( m = (__int64 *)*((_QWORD *)v6 + 4); m; m = (__int64 *)*m )
  {
    v41 = m[2];
    v42 = *((_DWORD *)m + 2);
    if ( v42 )
    {
      v76 = v42 - 1;
      if ( v76 )
      {
        if ( v76 == 1 )
          *(_QWORD *)v41 = &v39[*(_QWORD *)(*(_QWORD *)v41 + 120LL) - *(_QWORD *)(*((_QWORD *)v6 + 2) + 48LL)];
      }
      else
      {
        *(_DWORD *)v41 += *(_DWORD *)(*((_QWORD *)v6 + 2) + 48LL) - v41 - (_DWORD)v39 - 4;
      }
    }
    else
    {
      *(_DWORD *)v41 = *(_DWORD *)(m[3] + 120) - v41 - 4;
    }
  }
  v43 = (char *)*((_QWORD *)v1 + 6);
  v44 = *(_QWORD *)v37;
  v45 = (char *)(*(_QWORD *)(*(_QWORD *)v37 + 8LL) + *(_QWORD *)(**(_QWORD **)v37 + 16LL));
  lpBaseAddress = v45;
  dwSize = v38;
  while ( v38 )
  {
    v46 = 4096 - ((unsigned __int16)v45 & 0xFFFu);
    if ( SourceSize <= v46 )
      v46 = SourceSize;
    if ( CustomHeap::Heap::ProtectAllocationInternal(
           (CustomHeap::Heap *)(v91 + 24),
           *(struct CustomHeap::Allocation **)v44,
           v45,
           0x40u,
           &v88,
           0x10u) )
    {
      v47 = v45;
      v38 = SourceSize;
      if ( v46 )
      {
        memcpy_s(v45, (unsigned int)(*(_DWORD *)(v44 + 16) - *(_DWORD *)(v44 + 8)), v43, v46);
        v45 += v46;
        v43 += v46;
        *(_QWORD *)(v44 + 8) += v46;
        v38 -= v46;
        SourceSize = v38;
      }
      if ( CustomHeap::Heap::ProtectAllocationInternal(
             (CustomHeap::Heap *)(v91 + 24),
             *(struct CustomHeap::Allocation **)v44,
             v47,
             0x10u,
             &v88,
             0x40u) )
      {
        continue;
      }
    }
    goto LABEL_62;
  }
  FlushInstructionCache(hProcess, lpBaseAddress, dwSize);
LABEL_62:
  v48 = *(_QWORD *)this;
  *(_BYTE *)(*(_QWORD *)(*(_QWORD *)this + 120LL) + 12LL) = *(_BYTE *)(*(_QWORD *)(*(_QWORD *)this + 120LL) + 12LL)
                                                          & 0xF8
                                                          | 1;
  *(_BYTE *)(*(_QWORD *)(v48 + 120) + 12LL) &= 7u;
  *(_BYTE *)(*(_QWORD *)(v48 + 120) + 13LL) = *(_BYTE *)(v48 + 138);
  *(_BYTE *)(*(_QWORD *)(v48 + 120) + 14LL) = *(_BYTE *)(v48 + 137);
  *(_BYTE *)(*(_QWORD *)(v48 + 120) + 15LL) &= 0xF0u;
  *(_BYTE *)(*(_QWORD *)(v48 + 120) + 15LL) &= 0xFu;
  v49 = 2LL * *(unsigned __int8 *)(*(_QWORD *)this + 137LL) + 4;
  if ( v49 > 0x48 )
  {
LABEL_31:
    Js::Throw::FatalInternalError();
    __debugbreak();
  }
  memcpy_0(
    *(void **)(*(_QWORD *)si128.m128i_i64[0] + 32LL),
    (const void *)(*(_QWORD *)(*(_QWORD *)this + 120LL) + 12LL),
    v49);
  v50 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)this + 8LL) + 24LL))(*(_QWORD *)(*(_QWORD *)this + 8LL));
  v52 = *(_QWORD *)(*(_QWORD *)this + 48LL);
  v53 = v50 + 152;
  if ( v52 )
  {
    v78 = *(_DWORD *)(v52 + 24) - *(_DWORD *)(v52 + 32);
    v79 = AllocateArray<HeapAllocator,void *,0>(*(_QWORD *)this, HeapAllocator::AllocZero, v78);
    v88 = 0;
    si128.m128i_i64[0] = v79;
    si128.m128i_i64[1] = (__int64)&v88;
    JsUtil::BaseDictionary_void___void___ArenaAllocator_DictionarySizePolicy_PowerOf2Policy_2_2_1_4__DefaultComparer_JsUtil::SimpleHashedEntry_::MapEntryUntil__lambda_6fc46352c1545828c6514f192560d184___(
      v52,
      &si128);
    v80 = *(_QWORD *)v53;
    *(_QWORD *)(v80 + 16) = v79;
    *(_DWORD *)(v80 + 8) = v78;
  }
  v54 = *(_QWORD *)(*(_QWORD *)this + 56LL);
  if ( v54 )
  {
    v82 = *(_DWORD *)(v54 + 24) - *(_DWORD *)(v54 + 32);
    if ( v82 > 0 )
    {
      v83 = (unsigned int)(*(_DWORD *)(*(_QWORD *)(*(_QWORD *)this + 64LL) + 24LL)
                         - *(_DWORD *)(*(_QWORD *)(*(_QWORD *)this + 64LL) + 32LL));
      v84 = (_DWORD *)operator new<HeapAllocator>(v83, v51, HeapAllocator::AllocZero, 8 * (v82 + 2LL) * (int)v83);
      v85 = (rsize_t)v84;
      si128.m128i_i64[0] = (__int64)v84;
      if ( v84 )
        *v84 = -1;
      else
        v85 = 0;
      SourceSize = v85;
      si128.m128i_i64[0] = __PAIR64__(HIDWORD(v96), v82);
      si128.m128i_i64[1] = (__int64)&SourceSize;
      JsUtil::BaseDictionary_int_JsUtil::BaseDictionary_Js::Type___Js::JitTypePropertyGuard___ArenaAllocator_DictionarySizePolicy_PowerOf2Policy_2_2_1_4__DefaultComparer_JsUtil::SimpleDictionaryEntry____ArenaAllocator_DictionarySizePolicy_PowerOf2Policy_2_2_1_4__DefaultComparer_JsUtil::SimpleDictionaryEntry_::Map__lambda_1f9bb5058fc00c4e3aa60e1757976f5b___(
        *(_QWORD *)(*(_QWORD *)this + 64LL),
        &si128);
      *(_DWORD *)SourceSize = -1;
      *(_DWORD *)(*(_QWORD *)v53 + 24LL) = v82;
      *(_QWORD *)(*(_QWORD *)v53 + 32LL) = v85;
    }
  }
  *(_BYTE *)(*(_QWORD *)v53 + 41LL) = 1;
  v55 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)this + 8LL) + 72LL);
  v56 = *(_QWORD *)(*(_QWORD *)this + 336LL);
  v57 = *(_QWORD *)(v56 + 16);
  *(_QWORD *)(v56 + 16) = 0;
  *(_QWORD *)(v56 + 24) = 0;
  *(_DWORD *)(v56 + 32) = 0;
  v58 = *(_QWORD *)this;
  do
  {
    v59 = v58;
    v58 = *(_QWORD *)(v58 + 264);
  }
  while ( v58 );
  v60 = 0;
  if ( *(_QWORD *)(v59 + 328) )
  {
    v60 = HeapAllocator::Alloc((HeapAllocator *)HeapAllocator::Instance, 8u);
    *(_QWORD *)v60 = *(_QWORD *)(v59 + 328);
    *(_QWORD *)(v59 + 328) = 0;
  }
  if ( (_DWORD)v93 == -1 )
    v61 = Js::FunctionBody::TryGetEntryPointInfo(v94, v55);
  else
    v61 = (struct Js::EntryPointInfo *)JsUtil::List<HostScriptContext *,ArenaAllocator,0,Js::CopyRemovePolicy,DefaultComparer>::Item(
                                         *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v94 + 38) + 32LL) + 32LL
                                                                                               * (unsigned int)v93),
                                         v55);
  v62 = v92;
  *((_QWORD *)v61 + 8) = v92;
  *((_QWORD *)v61 + 9) = v95;
  *((_QWORD *)v61 + 6) = v60;
  *((_QWORD *)v61 + 7) = v57;
  *((_BYTE *)v61 + 120) = 2;
  if ( *(_QWORD *)v91 )
    *(_QWORD *)(*(_QWORD *)v91 + 8LL) = *(_QWORD *)(*(_QWORD *)v91 + 16LL);
  *(_QWORD *)(v96 + 64) = v62;
  if ( !*(_BYTE *)(v102 + 116) )
    ArenaAllocatorBase<InPlaceFreeListPolicy>::ReleasePageMemory(v99);
  v63 = Block;
  if ( Block )
  {
    do
    {
      v64 = (_QWORD *)*v63;
      if ( v63[1] != -16 )
        free(v63);
      v63 = v64;
    }
    while ( v64 );
  }
}

```

## disassembly

```asm
0x1800a5d60  mov     [rsp-8+arg_0], rcx
0x1800a5d65  push    rbp
0x1800a5d66  push    rbx
0x1800a5d67  push    rsi
0x1800a5d68  push    rdi
0x1800a5d69  push    r12
0x1800a5d6b  push    r13
0x1800a5d6d  push    r14
0x1800a5d6f  push    r15
0x1800a5d71  lea     rbp, [rsp-28h]
0x1800a5d76  sub     rsp, 128h
0x1800a5d7d  mov     [rbp+60h+var_50], 0FFFFFFFFFFFFFFFEh
0x1800a5d85  mov     r13, [rbp+60h+arg_0]
0x1800a5d89  mov     rdx, [r13+0]
0x1800a5d8d  mov     rax, [rdx]
0x1800a5d90  mov     rcx, [rax+28h]
0x1800a5d94  lea     rax, ?OutOfMemory@Throw@Js@@SAXXZ; Js::Throw::OutOfMemory(void)
0x1800a5d9b  mov     [rbp+60h+var_B0], rax
0x1800a5d9f  xor     r15d, r15d
0x1800a5da2  mov     [rbp+60h+var_A8], r15
0x1800a5da6  xorps   xmm0, xmm0
0x1800a5da9  movdqa  [rbp+60h+var_A0], xmm0
0x1800a5dae  mov     [rbp+60h+Block], r15
0x1800a5db2  mov     [rbp+60h+var_88], rcx
0x1800a5db6  mov     [rbp+60h+var_80], r15
0x1800a5dba  mov     [rbp+60h+var_78], r15b
0x1800a5dbe  mov     [rbp+60h+var_70], r15
0x1800a5dc2  mov     [rbp+60h+var_68], r15
0x1800a5dc6  mov     [rbp+60h+var_60], r15d
0x1800a5dca  mov     [rbp+60h+var_58], r15
0x1800a5dce  lea     rax, [rbp+60h+var_B0]
0x1800a5dd2  mov     [r13+48h], rax
0x1800a5dd6  mov     ecx, r15d
0x1800a5dd9  mov     rax, [rdx+50h]
0x1800a5ddd  test    rax, rax
0x1800a5de0  jz      short loc_1800A5DEC
0x1800a5de2  inc     ecx
0x1800a5de4  mov     rax, [rax]
0x1800a5de7  test    rax, rax
0x1800a5dea  jnz     short loc_1800A5DE2
0x1800a5dec  lea     r14, [r13+8]
0x1800a5df0  mov     [rsp+160h+var_F8], r14
0x1800a5df5  mov     [r14+10h], r13
0x1800a5df9  mov     [r14+20h], r15
0x1800a5dfd  mov     eax, ecx
0x1800a5dff  lea     rcx, [rax+rax*2]
0x1800a5e03  shl     rcx, 2
0x1800a5e07  mov     rax, 100000000h
0x1800a5e11  cmp     rcx, rax
0x1800a5e14  jb      short loc_1800A5E1B
0x1800a5e16  call    ?DefaultOverflowPolicy@Math@@SAXXZ; Math::DefaultOverflowPolicy(void)
0x1800a5e1b  mov     edx, ecx; unsigned __int64
0x1800a5e1d  mov     [r13+40h], edx
0x1800a5e21  test    ecx, ecx
0x1800a5e23  jz      loc_1800A66DB
0x1800a5e29  mov     rcx, [r13+48h]; this
0x1800a5e2d  call    ?Alloc@ArenaAllocator@@QEAAPEAD_K@Z; ArenaAllocator::Alloc(unsigned __int64)
0x1800a5e32  mov     rdx, rax
0x1800a5e35  mov     [r13+30h], rdx
0x1800a5e39  mov     [r13+38h], rdx
0x1800a5e3d  mov     rbx, [r13+0]
0x1800a5e41  mov     rcx, [rbx+8]
0x1800a5e45  mov     [rbp+60h+var_D8], rcx
0x1800a5e49  mov     edi, 0FFFFFFFFh
0x1800a5e4e  mov     [rsp+160h+var_F0], rdi
0x1800a5e53  movzx   eax, byte ptr [rcx+38h]
0x1800a5e57  test    al, al
0x1800a5e59  jnz     loc_1800A65E9
0x1800a5e5f  mov     r8, [rcx+28h]
0x1800a5e63  mov     [rsp+160h+var_E8], r8
0x1800a5e68  movdqa  xmm0, cs:__xmm@000000000000000000000000ffffffff
0x1800a5e70  movdqu  [rsp+160h+var_110], xmm0
0x1800a5e76  mov     r12, r15
0x1800a5e79  mov     [rsp+160h+var_12C], r15d
0x1800a5e7e  xor     sil, sil
0x1800a5e81  mov     [rsp+160h+var_130], sil
0x1800a5e86  mov     rbx, [rbx+50h]
0x1800a5e8a  mov     r8d, 2AEh
0x1800a5e90  test    rbx, rbx
0x1800a5e93  jz      loc_1800A60FD
0x1800a5e99  mov     ecx, edx
0x1800a5e9b  sub     ecx, [r13+30h]
0x1800a5e9f  lea     eax, [rcx+0Ch]
0x1800a5ea2  cmp     eax, [r13+40h]
0x1800a5ea6  jnb     loc_1800A5FC8
0x1800a5eac  cmp     byte ptr [rbx+1Ch], 8
0x1800a5eb0  jz      loc_1800A5FA2
0x1800a5eb6  test    r12, r12
0x1800a5eb9  jz      short loc_1800A5ED0
0x1800a5ebb  cmp     [rbx+18h], r8w
0x1800a5ec0  jz      loc_1800A650A
0x1800a5ec6  test    byte ptr [rbx+1Ah], 8
0x1800a5eca  jnz     loc_1800A650A
0x1800a5ed0  cmp     byte ptr [rbx+1Ah], 0
0x1800a5ed4  jl      loc_1800A6030
0x1800a5eda  test    byte ptr [rbx+1Ah], 8
0x1800a5ede  jnz     loc_1800A6484
0x1800a5ee4  mov     r9, [r13+30h]; unsigned __int8 *
0x1800a5ee8  mov     r8, [r13+38h]; unsigned __int8 *
0x1800a5eec  mov     rdx, rbx; struct IR::Instr *
0x1800a5eef  mov     rcx, r14; this
0x1800a5ef2  call    ?Encode@EncoderMD@@QEAA_JPEAVInstr@IR@@PEAE1@Z; EncoderMD::Encode(IR::Instr *,uchar *,uchar *)
0x1800a5ef7  mov     rdi, rax
0x1800a5efa  test    sil, sil
0x1800a5efd  jnz     short loc_1800A5F14
0x1800a5eff  add     [r13+38h], rdi
0x1800a5f03  mov     edx, [r13+38h]
0x1800a5f07  mov     rdi, [rsp+160h+var_F0]
0x1800a5f0c  mov     rbx, [rbx]
0x1800a5f0f  jmp     loc_1800A5E8A
0x1800a5f14  mov     rsi, [r13+0]
0x1800a5f18  mov     r11, [rsi+78h]
0x1800a5f1c  lea     r14, [rsi+89h]
0x1800a5f23  test    r11, r11
0x1800a5f26  jz      loc_1800A5FCE
0x1800a5f2c  mov     rcx, rbx; struct IR::Instr *
0x1800a5f2f  call    ?GetOp@PrologEncoderMD@@SAEPEAVInstr@IR@@@Z; PrologEncoderMD::GetOp(IR::Instr *)
0x1800a5f34  movzx   r9d, al
0x1800a5f38  movzx   r8d, byte ptr [rsi+8Ah]
0x1800a5f40  lea     rdx, [rsi+88h]
0x1800a5f47  test    r8b, r8b
0x1800a5f4a  jz      short loc_1800A5FC0
0x1800a5f4c  lea     eax, [r8+rdi]
0x1800a5f50  mov     [rsi+8Ah], al
0x1800a5f56  mov     ecx, r9d
0x1800a5f59  test    r9b, r9b
0x1800a5f5c  jnz     loc_1800A5FF2
0x1800a5f62  dec     byte ptr [rdx]
0x1800a5f64  movzx   eax, byte ptr [rdx]
0x1800a5f67  add     rax, 8
0x1800a5f6b  lea     r10, [r11+rax*2]
0x1800a5f6f  mov     rax, [rbx+30h]
0x1800a5f73  movzx   r8d, byte ptr [rax+24h]
0x1800a5f78  dec     r8b
0x1800a5f7b  movzx   eax, byte ptr [rsi+8Ah]
0x1800a5f82  mov     [r10], al
0x1800a5f85  shl     r8b, 4
0x1800a5f89  and     r9b, 0Fh
0x1800a5f8d  or      r8b, r9b
0x1800a5f90  mov     [r10+1], r8b
0x1800a5f94  lea     r14, [r13+8]
0x1800a5f98  movzx   esi, [rsp+160h+var_130]
0x1800a5f9d  jmp     loc_1800A5EFF
0x1800a5fa2  movzx   r8d, word ptr [rbx+18h]
0x1800a5fa7  cmp     r8d, 270h
0x1800a5fae  jnz     loc_1800A65A5
0x1800a5fb4  mov     [rsp+160h+var_12C], ecx
0x1800a5fb8  mov     r12, rbx
0x1800a5fbb  jmp     loc_1800A5ED0
0x1800a5fc0  movzx   ecx, byte ptr [r14]
0x1800a5fc4  mov     [rdx], cl
0x1800a5fc6  jmp     short loc_1800A5F4C
0x1800a5fc8  call    ?FatalInternalError@Throw@Js@@SAXXZ; Js::Throw::FatalInternalError(void)
0x1800a5fcd  int     3; Trap to Debugger
0x1800a5fce  movzx   edx, byte ptr [r14]
0x1800a5fd2  lea     rdx, ds:10h[rdx*2]; unsigned __int64
0x1800a5fda  mov     rcx, [rsi+80h]; this
0x1800a5fe1  call    ?Alloc@ArenaAllocator@@QEAAPEAD_K@Z; ArenaAllocator::Alloc(unsigned __int64)
0x1800a5fe6  mov     r11, rax
0x1800a5fe9  mov     [rsi+78h], rax
0x1800a5fed  jmp     loc_1800A5F2C
0x1800a5ff2  mov     r10, r15
0x1800a5ff5  xor     r8b, r8b
0x1800a5ff8  sub     ecx, 1
0x1800a5ffb  jz      loc_1800A6729
0x1800a6001  sub     ecx, 1
0x1800a6004  jnz     loc_1800A64B1
0x1800a600a  dec     byte ptr [rdx]
0x1800a600c  movzx   eax, byte ptr [rdx]
0x1800a600f  add     rax, 8
0x1800a6013  lea     r10, [r11+rax*2]
0x1800a6017  mov     rax, [rbx+38h]
0x1800a601b  mov     r8d, [rax+10h]
0x1800a601f  add     r8b, 0F8h
0x1800a6023  shr     r8b, 3
0x1800a6027  and     r8b, 0Fh
0x1800a602b  jmp     loc_1800A5F7B
0x1800a6030  mov     rcx, rbx; this
0x1800a6033  call    ?GetBailOutInfo@Instr@IR@@QEBAPEAVBailOutInfo@@XZ; IR::Instr::GetBailOutInfo(void)
0x1800a6038  mov     r8, rax
0x1800a603b  mov     rcx, [rax+8]
0x1800a603f  test    rcx, rcx
0x1800a6042  jz      loc_1800A5EDA
0x1800a6048  mov     r10, [r13+0]
0x1800a604c  mov     rdx, [rax+0A0h]
0x1800a6053  mov     r9d, [r10+0B0h]
0x1800a605a  add     r9d, 10h
0x1800a605e  cmp     qword ptr [rcx+8], 0
0x1800a6063  jz      short loc_1800A6083
0x1800a6065  mov     eax, [rdx+0C8h]
0x1800a606b  sub     eax, r9d
0x1800a606e  mov     [rcx+70h], eax
0x1800a6071  mov     rcx, [rcx+8]
0x1800a6075  mov     rdx, [rdx+108h]
0x1800a607c  cmp     qword ptr [rcx+8], 0
0x1800a6081  jnz     short loc_1800A6065
0x1800a6083  cmp     dword ptr [r8+50h], 0
0x1800a6088  jz      loc_1800A5EDA
0x1800a608e  cmp     byte ptr [r10+11Fh], 0
0x1800a6096  jz      loc_1800A5EDA
0x1800a609c  mov     rax, [r8+90h]
0x1800a60a3  mov     r10, [rax]
0x1800a60a6  test    r10, r10
0x1800a60a9  jz      loc_1800A5EDA
0x1800a60af  mov     eax, [r10+4]
0x1800a60b3  mov     [rsp+160h+var_128], r15d
0x1800a60b8  bsf     edx, eax
0x1800a60bb  setnz   cl
0x1800a60be  test    cl, cl
0x1800a60c0  jz      short loc_1800A60EF
0x1800a60c2  mov     r11d, [r10]
0x1800a60c5  cmp     edx, 0FFFFFFFFh
0x1800a60c8  jz      short loc_1800A60EF
0x1800a60ca  btr     eax, edx
0x1800a60cd  add     edx, r11d
0x1800a60d0  mov     rcx, [r8+88h]
0x1800a60d7  sub     [rcx+rdx*4], r9d
0x1800a60db  mov     [rsp+160h+var_128], r15d
0x1800a60e0  bsf     edx, eax
0x1800a60e3  setnz   cl
0x1800a60e6  test    cl, cl
0x1800a60e8  jz      short loc_1800A60EF
0x1800a60ea  cmp     edx, 0FFFFFFFFh
0x1800a60ed  jnz     short loc_1800A60CA
0x1800a60ef  mov     r10, [r10+8]
0x1800a60f3  test    r10, r10
0x1800a60f6  jnz     short loc_1800A60AF
0x1800a60f8  jmp     loc_1800A5EDA
0x1800a60fd  mov     [rsp+160h+var_F8], r15
0x1800a6102  mov     rcx, [r13+38h]
0x1800a6106  sub     rcx, [r13+30h]
0x1800a610a  mov     [rbp+60h+var_E0], rcx
0x1800a610e  mov     rax, [r13+0]
0x1800a6112  mov     rdi, [rax+48h]
0x1800a6116  add     rdi, 60h ; '`'
0x1800a611a  mov     [rsp+160h+var_100], rdi
0x1800a611f  mov     r15d, ecx
0x1800a6122  mov     [rsp+160h+SourceSize], r15
0x1800a6127  movzx   ecx, byte ptr [rax+89h]
0x1800a612e  add     cx, 2
0x1800a6132  add     cx, cx
0x1800a6135  mov     word ptr [rsp+160h+var_138], cx; unsigned __int16
0x1800a613a  mov     word ptr [rsp+160h+var_140], 1; unsigned __int16
0x1800a6141  xor     r9d, r9d; bool
0x1800a6144  lea     r8, [rsp+160h+var_F8]; unsigned __int8 **
0x1800a6149  mov     edx, r15d; unsigned __int64
0x1800a614c  mov     rcx, rdi; this
0x1800a614f  call    ?AllocateBuffer@EmitBufferManager@@QEAAPEAUEmitBufferAllocation@@_KPEAPEAE_NGG@Z; EmitBufferManager::AllocateBuffer(unsigned __int64,uchar * *,bool,ushort,ushort)
0x1800a6154  mov     qword ptr [rsp+160h+var_110], rax
0x1800a6159  mov     r10, [rsp+160h+var_F8]
0x1800a615e  test    r10, r10
0x1800a6161  jz      loc_1800A6795
0x1800a6167  mov     r8, [r14+20h]
0x1800a616b  test    r8, r8
0x1800a616e  jz      short loc_1800A6198
0x1800a6170  mov     r9, [r8+10h]
0x1800a6174  mov     ecx, [r8+8]
0x1800a6178  test    ecx, ecx
0x1800a617a  jnz     loc_1800A6579
0x1800a6180  mov     rax, [r8+18h]
0x1800a6184  mov     ecx, [rax+78h]
0x1800a6187  sub     ecx, r9d
0x1800a618a  sub     ecx, 4
0x1800a618d  mov     [r9], ecx
0x1800a6190  mov     r8, [r8]
0x1800a6193  test    r8, r8
0x1800a6196  jnz     short loc_1800A6170
0x1800a6198  xor     ebx, ebx
0x1800a619a  mov     [rsp+160h+var_12C], ebx
0x1800a619e  mov     r12, [r13+30h]
0x1800a61a2  mov     r14, [rdi]
0x1800a61a5  mov     rax, [r14]
0x1800a61a8  mov     rsi, [rax+10h]
0x1800a61ac  add     rsi, [r14+8]
0x1800a61b0  mov     [rbp+60h+lpBaseAddress], rsi
0x1800a61b4  mov     [rbp+60h+dwSize], r15
0x1800a61b8  test    r15, r15
0x1800a61bb  jz      loc_1800A6288
0x1800a61c1  mov     ecx, esi
0x1800a61c3  and     ecx, 0FFFh
0x1800a61c9  mov     eax, 1000h
0x1800a61ce  sub     eax, ecx
0x1800a61d0  mov     r15d, eax
0x1800a61d3  mov     edi, eax
0x1800a61d5  cmp     [rsp+160h+SourceSize], r15
0x1800a61da  cmovbe  rdi, [rsp+160h+SourceSize]
0x1800a61e0  mov     rax, [rsp+160h+var_100]
0x1800a61e5  mov     [rsp+160h+var_138], 10h; unsigned int
0x1800a61ed  lea     rcx, [rsp+160h+var_128]
0x1800a61f2  mov     [rsp+160h+var_140], rcx; unsigned int *
0x1800a61f7  mov     r9d, 40h ; '@'; unsigned int
0x1800a61fd  mov     r8, rsi; char *
0x1800a6200  mov     rdx, [r14]; struct CustomHeap::Allocation *
0x1800a6203  lea     rcx, [rax+18h]; this
0x1800a6207  call    ?ProtectAllocationInternal@Heap@CustomHeap@@AEAAHPEAUAllocation@2@PEADKPEAKK@Z; CustomHeap::Heap::ProtectAllocationInternal(CustomHeap::Allocation *,char *,ulong,ulong *,ulong)
0x1800a620c  test    eax, eax
0x1800a620e  jz      loc_1800A629D
0x1800a6214  mov     r13, rsi
0x1800a6217  test    ebx, ebx
0x1800a6219  jnz     loc_1800A67B3
  ... truncated ...
```
