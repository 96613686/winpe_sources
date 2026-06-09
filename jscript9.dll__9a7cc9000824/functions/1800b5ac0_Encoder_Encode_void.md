# Encoder::Encode(void)

- ea: `0x1800b5ac0`
- end: `0x1800b6601`
- name: `?Encode@Encoder@@QEAAXXZ`
- size: `2881`
- prototype: `void __fastcall(Encode *this)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800401d4`

## callees

- `0x180093860`
- `0x1800b0280`
- `0x1800b1fbc`
- `0x1800b52c8`
- `0x1800b59d0`
- `0x1800b5a8c`
- `0x1800b5ac0`
- `0x1800b6610`
- `0x1800b7928`
- `0x1800b7f78`
- `0x1800b7f9c`
- `0x18010c8a0`
- `0x180129848`
- `0x18012fb54`
- `0x180170bf8`
- `0x180181818`
- `0x1801a31a4`
- `0x1801acd80`
- `0x1801acd90`
- `0x1801cc26b`
- `0x180326bc8`
- `0x180347f69`
- `0x180364010`

## import_xrefs

- `msvcrt!free` at `0x1800b61d2`
- `msvcrt!free` at `0x1800b61d2`
- `msvcrt!memcpy_s` at `0x1800b5f9a`
- `msvcrt!memcpy_s` at `0x1800b5f9a`
- `KERNEL32!FlushInstructionCache` at `0x1800b5ffd`
- `KERNEL32!FlushInstructionCache` at `0x1800b5ffd`

## pseudocode

```c
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
    v8 = (__int64)ArenaAllocator::Alloc(*((ArenaAllocator **)v1 + 9), (unsigned int)v7);
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
                                     2LL * (unsigned __int8)*v17 + 16);
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
0x1800b5ac0  mov     [rsp-8+arg_0], rcx
0x1800b5ac5  push    rbp
0x1800b5ac6  push    rbx
0x1800b5ac7  push    rsi
0x1800b5ac8  push    rdi
0x1800b5ac9  push    r12
0x1800b5acb  push    r13
0x1800b5acd  push    r14
0x1800b5acf  push    r15
0x1800b5ad1  lea     rbp, [rsp-28h]
0x1800b5ad6  sub     rsp, 128h
0x1800b5add  mov     [rbp+60h+var_50], 0FFFFFFFFFFFFFFFEh
0x1800b5ae5  mov     r13, [rbp+60h+arg_0]
0x1800b5ae9  mov     rdx, [r13+0]
0x1800b5aed  mov     rax, [rdx]
0x1800b5af0  mov     rcx, [rax+28h]
0x1800b5af4  lea     rax, ?OutOfMemory@Throw@Js@@SAXXZ; Js::Throw::OutOfMemory(void)
0x1800b5afb  mov     [rbp+60h+var_B0], rax
0x1800b5aff  xor     r15d, r15d
0x1800b5b02  mov     [rbp+60h+var_A8], r15
0x1800b5b06  xorps   xmm0, xmm0
0x1800b5b09  movdqa  [rbp+60h+var_A0], xmm0
0x1800b5b0e  mov     [rbp+60h+Block], r15
0x1800b5b12  mov     [rbp+60h+var_88], rcx
0x1800b5b16  mov     [rbp+60h+var_80], r15
0x1800b5b1a  mov     [rbp+60h+var_78], r15b
0x1800b5b1e  mov     [rbp+60h+var_70], r15
0x1800b5b22  mov     [rbp+60h+var_68], r15
0x1800b5b26  mov     [rbp+60h+var_60], r15d
0x1800b5b2a  mov     [rbp+60h+var_58], r15
0x1800b5b2e  lea     rax, [rbp+60h+var_B0]
0x1800b5b32  mov     [r13+48h], rax
0x1800b5b36  mov     ecx, r15d
0x1800b5b39  mov     rax, [rdx+50h]
0x1800b5b3d  test    rax, rax
0x1800b5b40  jz      short loc_1800B5B4C
0x1800b5b42  inc     ecx
0x1800b5b44  mov     rax, [rax]
0x1800b5b47  test    rax, rax
0x1800b5b4a  jnz     short loc_1800B5B42
0x1800b5b4c  lea     r14, [r13+8]
0x1800b5b50  mov     [rsp+160h+var_F8], r14
0x1800b5b55  mov     [r14+10h], r13
0x1800b5b59  mov     [r14+20h], r15
0x1800b5b5d  mov     eax, ecx
0x1800b5b5f  lea     rcx, [rax+rax*2]
0x1800b5b63  shl     rcx, 2
0x1800b5b67  mov     rax, 100000000h
0x1800b5b71  cmp     rcx, rax
0x1800b5b74  jb      short loc_1800B5B7B
0x1800b5b76  call    ?DefaultOverflowPolicy@Math@@SAXXZ; Math::DefaultOverflowPolicy(void)
0x1800b5b7b  mov     edx, ecx; unsigned __int64
0x1800b5b7d  mov     [r13+40h], edx
0x1800b5b81  test    ecx, ecx
0x1800b5b83  jz      loc_1800B6452
0x1800b5b89  mov     rcx, [r13+48h]; this
0x1800b5b8d  call    ?Alloc@ArenaAllocator@@QEAAPEAD_K@Z; ArenaAllocator::Alloc(unsigned __int64)
0x1800b5b92  mov     rdx, rax
0x1800b5b95  mov     [r13+30h], rdx
0x1800b5b99  mov     [r13+38h], rdx
0x1800b5b9d  mov     rbx, [r13+0]
0x1800b5ba1  mov     rcx, [rbx+8]
0x1800b5ba5  mov     [rbp+60h+var_D8], rcx
0x1800b5ba9  mov     edi, 0FFFFFFFFh
0x1800b5bae  mov     [rsp+160h+var_F0], rdi
0x1800b5bb3  movzx   eax, byte ptr [rcx+38h]
0x1800b5bb7  test    al, al
0x1800b5bb9  jnz     loc_1800B6360
0x1800b5bbf  mov     r8, [rcx+28h]
0x1800b5bc3  mov     [rsp+160h+var_E8], r8
0x1800b5bc8  movdqa  xmm0, cs:__xmm@000000000000000000000000ffffffff
0x1800b5bd0  movdqu  [rsp+160h+var_110], xmm0
0x1800b5bd6  mov     r12, r15
0x1800b5bd9  mov     [rsp+160h+var_12C], r15d
0x1800b5bde  xor     sil, sil
0x1800b5be1  mov     [rsp+160h+var_130], sil
0x1800b5be6  mov     rbx, [rbx+50h]
0x1800b5bea  mov     r8d, 2AEh
0x1800b5bf0  test    rbx, rbx
0x1800b5bf3  jz      loc_1800B5E5D
0x1800b5bf9  mov     ecx, edx
0x1800b5bfb  sub     ecx, [r13+30h]
0x1800b5bff  lea     eax, [rcx+0Ch]
0x1800b5c02  cmp     eax, [r13+40h]
0x1800b5c06  jnb     loc_1800B5D28
0x1800b5c0c  cmp     byte ptr [rbx+1Ch], 8
0x1800b5c10  jz      loc_1800B5D02
0x1800b5c16  test    r12, r12
0x1800b5c19  jz      short loc_1800B5C30
0x1800b5c1b  cmp     [rbx+18h], r8w
0x1800b5c20  jz      loc_1800B6281
0x1800b5c26  test    byte ptr [rbx+1Ah], 8
0x1800b5c2a  jnz     loc_1800B6281
0x1800b5c30  cmp     byte ptr [rbx+1Ah], 0
0x1800b5c34  jl      loc_1800B5D90
0x1800b5c3a  test    byte ptr [rbx+1Ah], 8
0x1800b5c3e  jnz     loc_1800B61FB
0x1800b5c44  mov     r9, [r13+30h]; unsigned __int8 *
0x1800b5c48  mov     r8, [r13+38h]; unsigned __int8 *
0x1800b5c4c  mov     rdx, rbx; struct IR::Instr *
0x1800b5c4f  mov     rcx, r14; this
0x1800b5c52  call    ?Encode@EncoderMD@@QEAA_JPEAVInstr@IR@@PEAE1@Z; EncoderMD::Encode(IR::Instr *,uchar *,uchar *)
0x1800b5c57  mov     rdi, rax
0x1800b5c5a  test    sil, sil
0x1800b5c5d  jnz     short loc_1800B5C74
0x1800b5c5f  add     [r13+38h], rdi
0x1800b5c63  mov     edx, [r13+38h]
0x1800b5c67  mov     rdi, [rsp+160h+var_F0]
0x1800b5c6c  mov     rbx, [rbx]
0x1800b5c6f  jmp     loc_1800B5BEA
0x1800b5c74  mov     rsi, [r13+0]
0x1800b5c78  mov     r11, [rsi+78h]
0x1800b5c7c  lea     r14, [rsi+89h]
0x1800b5c83  test    r11, r11
0x1800b5c86  jz      loc_1800B5D2E
0x1800b5c8c  mov     rcx, rbx; struct IR::Instr *
0x1800b5c8f  call    ?GetOp@PrologEncoderMD@@SAEPEAVInstr@IR@@@Z; PrologEncoderMD::GetOp(IR::Instr *)
0x1800b5c94  movzx   r9d, al
0x1800b5c98  movzx   r8d, byte ptr [rsi+8Ah]
0x1800b5ca0  lea     rdx, [rsi+88h]
0x1800b5ca7  test    r8b, r8b
0x1800b5caa  jz      short loc_1800B5D20
0x1800b5cac  lea     eax, [r8+rdi]
0x1800b5cb0  mov     [rsi+8Ah], al
0x1800b5cb6  mov     ecx, r9d
0x1800b5cb9  test    r9b, r9b
0x1800b5cbc  jnz     loc_1800B5D52
0x1800b5cc2  dec     byte ptr [rdx]
0x1800b5cc4  movzx   eax, byte ptr [rdx]
0x1800b5cc7  add     rax, 8
0x1800b5ccb  lea     r10, [r11+rax*2]
0x1800b5ccf  mov     rax, [rbx+30h]
0x1800b5cd3  movzx   r8d, byte ptr [rax+24h]
0x1800b5cd8  dec     r8b
0x1800b5cdb  movzx   eax, byte ptr [rsi+8Ah]
0x1800b5ce2  mov     [r10], al
0x1800b5ce5  shl     r8b, 4
0x1800b5ce9  and     r9b, 0Fh
0x1800b5ced  or      r8b, r9b
0x1800b5cf0  mov     [r10+1], r8b
0x1800b5cf4  lea     r14, [r13+8]
0x1800b5cf8  movzx   esi, [rsp+160h+var_130]
0x1800b5cfd  jmp     loc_1800B5C5F
0x1800b5d02  movzx   r8d, word ptr [rbx+18h]
0x1800b5d07  cmp     r8d, 270h
0x1800b5d0e  jnz     loc_1800B631C
0x1800b5d14  mov     [rsp+160h+var_12C], ecx
0x1800b5d18  mov     r12, rbx
0x1800b5d1b  jmp     loc_1800B5C30
0x1800b5d20  movzx   ecx, byte ptr [r14]
0x1800b5d24  mov     [rdx], cl
0x1800b5d26  jmp     short loc_1800B5CAC
0x1800b5d28  call    ?FatalInternalError@Throw@Js@@SAXXZ; Js::Throw::FatalInternalError(void)
0x1800b5d2d  int     3; Trap to Debugger
0x1800b5d2e  movzx   edx, byte ptr [r14]
0x1800b5d32  lea     rdx, ds:10h[rdx*2]; unsigned __int64
0x1800b5d3a  mov     rcx, [rsi+80h]; this
0x1800b5d41  call    ?Alloc@ArenaAllocator@@QEAAPEAD_K@Z; ArenaAllocator::Alloc(unsigned __int64)
0x1800b5d46  mov     r11, rax
0x1800b5d49  mov     [rsi+78h], rax
0x1800b5d4d  jmp     loc_1800B5C8C
0x1800b5d52  mov     r10, r15
0x1800b5d55  xor     r8b, r8b
0x1800b5d58  sub     ecx, 1
0x1800b5d5b  jz      loc_1800B64A0
0x1800b5d61  sub     ecx, 1
0x1800b5d64  jnz     loc_1800B6228
0x1800b5d6a  dec     byte ptr [rdx]
0x1800b5d6c  movzx   eax, byte ptr [rdx]
0x1800b5d6f  add     rax, 8
0x1800b5d73  lea     r10, [r11+rax*2]
0x1800b5d77  mov     rax, [rbx+38h]
0x1800b5d7b  mov     r8d, [rax+10h]
0x1800b5d7f  add     r8b, 0F8h
0x1800b5d83  shr     r8b, 3
0x1800b5d87  and     r8b, 0Fh
0x1800b5d8b  jmp     loc_1800B5CDB
0x1800b5d90  mov     rcx, rbx; this
0x1800b5d93  call    ?GetBailOutInfo@Instr@IR@@QEBAPEAVBailOutInfo@@XZ; IR::Instr::GetBailOutInfo(void)
0x1800b5d98  mov     r8, rax
0x1800b5d9b  mov     rcx, [rax+8]
0x1800b5d9f  test    rcx, rcx
0x1800b5da2  jz      loc_1800B5C3A
0x1800b5da8  mov     r10, [r13+0]
0x1800b5dac  mov     rdx, [rax+0A0h]
0x1800b5db3  mov     r9d, [r10+0B0h]
0x1800b5dba  add     r9d, 10h
0x1800b5dbe  cmp     qword ptr [rcx+8], 0
0x1800b5dc3  jz      short loc_1800B5DE3
0x1800b5dc5  mov     eax, [rdx+0C8h]
0x1800b5dcb  sub     eax, r9d
0x1800b5dce  mov     [rcx+70h], eax
0x1800b5dd1  mov     rcx, [rcx+8]
0x1800b5dd5  mov     rdx, [rdx+108h]
0x1800b5ddc  cmp     qword ptr [rcx+8], 0
0x1800b5de1  jnz     short loc_1800B5DC5
0x1800b5de3  cmp     dword ptr [r8+50h], 0
0x1800b5de8  jz      loc_1800B5C3A
0x1800b5dee  cmp     byte ptr [r10+11Fh], 0
0x1800b5df6  jz      loc_1800B5C3A
0x1800b5dfc  mov     rax, [r8+90h]
0x1800b5e03  mov     r10, [rax]
0x1800b5e06  test    r10, r10
0x1800b5e09  jz      loc_1800B5C3A
0x1800b5e0f  mov     eax, [r10+4]
0x1800b5e13  mov     [rsp+160h+var_128], r15d
0x1800b5e18  bsf     edx, eax
0x1800b5e1b  setnz   cl
0x1800b5e1e  test    cl, cl
0x1800b5e20  jz      short loc_1800B5E4F
0x1800b5e22  mov     r11d, [r10]
0x1800b5e25  cmp     edx, 0FFFFFFFFh
0x1800b5e28  jz      short loc_1800B5E4F
0x1800b5e2a  btr     eax, edx
0x1800b5e2d  add     edx, r11d
0x1800b5e30  mov     rcx, [r8+88h]
0x1800b5e37  sub     [rcx+rdx*4], r9d
0x1800b5e3b  mov     [rsp+160h+var_128], r15d
0x1800b5e40  bsf     edx, eax
0x1800b5e43  setnz   cl
0x1800b5e46  test    cl, cl
0x1800b5e48  jz      short loc_1800B5E4F
0x1800b5e4a  cmp     edx, 0FFFFFFFFh
0x1800b5e4d  jnz     short loc_1800B5E2A
0x1800b5e4f  mov     r10, [r10+8]
0x1800b5e53  test    r10, r10
0x1800b5e56  jnz     short loc_1800B5E0F
0x1800b5e58  jmp     loc_1800B5C3A
0x1800b5e5d  mov     [rsp+160h+var_F8], r15
0x1800b5e62  mov     rcx, [r13+38h]
0x1800b5e66  sub     rcx, [r13+30h]
0x1800b5e6a  mov     [rbp+60h+var_E0], rcx
0x1800b5e6e  mov     rax, [r13+0]
0x1800b5e72  mov     rdi, [rax+48h]
0x1800b5e76  add     rdi, 60h ; '`'
0x1800b5e7a  mov     [rsp+160h+var_100], rdi
0x1800b5e7f  mov     r15d, ecx
0x1800b5e82  mov     [rsp+160h+SourceSize], r15
0x1800b5e87  movzx   ecx, byte ptr [rax+89h]
0x1800b5e8e  add     cx, 2
0x1800b5e92  add     cx, cx
0x1800b5e95  mov     word ptr [rsp+160h+var_138], cx; unsigned __int16
0x1800b5e9a  mov     word ptr [rsp+160h+var_140], 1; unsigned __int16
0x1800b5ea1  xor     r9d, r9d; bool
0x1800b5ea4  lea     r8, [rsp+160h+var_F8]; unsigned __int8 **
0x1800b5ea9  mov     edx, r15d; unsigned __int64
0x1800b5eac  mov     rcx, rdi; this
0x1800b5eaf  call    ?AllocateBuffer@EmitBufferManager@@QEAAPEAUEmitBufferAllocation@@_KPEAPEAE_NGG@Z; EmitBufferManager::AllocateBuffer(unsigned __int64,uchar * *,bool,ushort,ushort)
0x1800b5eb4  mov     qword ptr [rsp+160h+var_110], rax
0x1800b5eb9  mov     r10, [rsp+160h+var_F8]
0x1800b5ebe  test    r10, r10
0x1800b5ec1  jz      loc_1800B650C
0x1800b5ec7  mov     r8, [r14+20h]
0x1800b5ecb  test    r8, r8
0x1800b5ece  jz      short loc_1800B5EF8
0x1800b5ed0  mov     r9, [r8+10h]
0x1800b5ed4  mov     ecx, [r8+8]
0x1800b5ed8  test    ecx, ecx
0x1800b5eda  jnz     loc_1800B62F0
0x1800b5ee0  mov     rax, [r8+18h]
0x1800b5ee4  mov     ecx, [rax+78h]
0x1800b5ee7  sub     ecx, r9d
0x1800b5eea  sub     ecx, 4
0x1800b5eed  mov     [r9], ecx
0x1800b5ef0  mov     r8, [r8]
0x1800b5ef3  test    r8, r8
0x1800b5ef6  jnz     short loc_1800B5ED0
0x1800b5ef8  xor     ebx, ebx
0x1800b5efa  mov     [rsp+160h+var_12C], ebx
0x1800b5efe  mov     r12, [r13+30h]
0x1800b5f02  mov     r14, [rdi]
0x1800b5f05  mov     rax, [r14]
0x1800b5f08  mov     rsi, [rax+10h]
0x1800b5f0c  add     rsi, [r14+8]
0x1800b5f10  mov     [rbp+60h+lpBaseAddress], rsi
0x1800b5f14  mov     [rbp+60h+dwSize], r15
0x1800b5f18  test    r15, r15
0x1800b5f1b  jz      loc_1800B5FEE
0x1800b5f21  mov     ecx, esi
0x1800b5f23  and     ecx, 0FFFh
0x1800b5f29  mov     eax, 1000h
0x1800b5f2e  sub     eax, ecx
0x1800b5f30  mov     r15d, eax
0x1800b5f33  mov     edi, eax
0x1800b5f35  cmp     [rsp+160h+SourceSize], r15
0x1800b5f3a  cmovbe  rdi, [rsp+160h+SourceSize]
0x1800b5f40  mov     rax, [rsp+160h+var_100]
0x1800b5f45  mov     [rsp+160h+var_138], 10h; unsigned int
0x1800b5f4d  lea     rcx, [rsp+160h+var_128]
0x1800b5f52  mov     [rsp+160h+var_140], rcx; unsigned int *
0x1800b5f57  mov     r9d, 40h ; '@'; unsigned int
0x1800b5f5d  mov     r8, rsi; char *
0x1800b5f60  mov     rdx, [r14]; struct CustomHeap::Allocation *
0x1800b5f63  lea     rcx, [rax+18h]; this
0x1800b5f67  call    ?ProtectAllocationInternal@Heap@CustomHeap@@AEAAHPEAUAllocation@2@PEADKPEAKK@Z; CustomHeap::Heap::ProtectAllocationInternal(CustomHeap::Allocation *,char *,ulong,ulong *,ulong)
0x1800b5f6c  test    eax, eax
0x1800b5f6e  jz      loc_1800B6009
0x1800b5f74  mov     r13, rsi
0x1800b5f77  test    ebx, ebx
0x1800b5f79  jnz     loc_1800B652A
  ... truncated ...
```
