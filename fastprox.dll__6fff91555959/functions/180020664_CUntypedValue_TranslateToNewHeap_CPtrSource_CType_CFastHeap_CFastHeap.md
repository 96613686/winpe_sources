# CUntypedValue::TranslateToNewHeap(CPtrSource *,CType,CFastHeap *,CFastHeap *)

- ea: `0x180020664`
- end: `0x180020bd6`
- name: `?TranslateToNewHeap@CUntypedValue@@SAHPEAVCPtrSource@@VCType@@PEAVCFastHeap@@2@Z`
- size: `1394`
- prototype: `__int64 __fastcall(__int64 (__fastcall ***)(_QWORD), __int16, struct CFastHeap *, CFastHeap *)`
- caller_count: `8`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180021cb0`
- `0x180022cd0`
- `0x1800281c0`
- `0x180029980`
- `0x1800312d0`
- `0x18004ccb0`
- `0x180051540`
- `0x18005d568`

## callees

- `0x1800088d0`
- `0x18001f5d0`
- `0x180020664`
- `0x180021820`
- `0x180021c90`
- `0x180021d10`
- `0x180035b08`
- `0x18006fa4c`
- `0x18006fa66`
- `0x180071c50`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180020a8b`
- `wbemcomn!GetMemLogObject` at `0x180020ac7`
- `wbemcomn!GetMemLogObject` at `0x180020aff`
- `wbemcomn!GetMemLogObject` at `0x180020a8b`
- `wbemcomn!GetMemLogObject` at `0x180020ac7`
- `wbemcomn!GetMemLogObject` at `0x180020aff`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180020a99`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180020ad5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180020b0d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180020a99`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180020ad5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180020b0d`

## pseudocode

```c
__int64 __fastcall CUntypedValue::TranslateToNewHeap(
        __int64 (__fastcall ***a1)(_QWORD),
        __int16 a2,
        struct CFastHeap *a3,
        CFastHeap *a4)
{
  int v5; // ebx
  unsigned int *v8; // rax
  __int64 v9; // rbx
  __int64 v10; // r13
  unsigned int Length; // eax
  _DWORD *v12; // r12
  size_t v13; // r15
  int v14; // ecx
  __int64 v15; // rcx
  unsigned int v16; // r9d
  _DWORD *v18; // rax
  _DWORD *v19; // r12
  _DWORD *v20; // rdi
  size_t v21; // rbx
  int v22; // ecx
  __int64 v23; // rcx
  unsigned int v24; // edi
  unsigned __int8 *v25; // rax
  __int64 v26; // r12
  unsigned int v27; // eax
  _DWORD *v28; // r15
  int v29; // ecx
  int v30; // r13d
  __int64 v31; // rcx
  unsigned int v32; // r15d
  unsigned int (__fastcall ***v33)(_QWORD, unsigned __int8 *, __int64, _QWORD); // r13
  unsigned __int8 *Start; // rax
  int v35; // r8d
  __int64 v36; // r8
  unsigned int v37; // r12d
  _DWORD *v38; // rax
  unsigned int (__fastcall ***v39)(_QWORD, unsigned __int8 *, _QWORD, _QWORD); // r15
  unsigned int v40; // r13d
  unsigned __int8 *v41; // rax
  int v42; // r8d
  _DWORD *v43; // rax
  unsigned __int8 *v44; // rax
  int v45; // r8d
  __int64 v46; // r8
  unsigned int v47; // r15d
  _DWORD *v48; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v50; // rax
  CMemoryLog *v51; // rax
  __int64 (__fastcall **v52[2])(_QWORD); // [rsp+38h] [rbp-20h] BYREF
  unsigned int v53; // [rsp+48h] [rbp-10h]
  unsigned int pExceptionObject; // [rsp+A8h] [rbp+50h] BYREF

  v5 = a2 & 0xFFF;
  if ( (a2 & 0x2000) == 0 )
  {
    if ( v5 == 8 || (unsigned int)(v5 - 101) <= 1 )
    {
      v8 = (unsigned int *)(**a1)(a1);
      v9 = *v8;
      if ( !CFastHeap::IsFakeAddress(*v8) )
      {
        if ( (unsigned int)v9 > *(_DWORD *)(*((_QWORD *)a3 + 1) + 4LL) )
          throw (CX_Exception *)&pExceptionObject;
        v10 = (unsigned int)v9;
        Length = CCompressedString::GetLength((CCompressedString *)(v9 + *(_QWORD *)a3));
        v12 = (_DWORD *)*((_QWORD *)a4 + 1);
        v13 = (int)Length;
        v14 = v12[1];
        if ( *v12 - v14 < Length )
        {
          v33 = (unsigned int (__fastcall ***)(_QWORD, unsigned __int8 *, __int64, _QWORD))*((_QWORD *)a4 + 4);
          if ( !v33 )
          {
            MemLogObject = GetMemLogObject();
            CMemoryLog::Write(MemLogObject, -2);
            if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_s(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                13,
                WPP_5079cb25a27f37742ccdcc8b2574b31c_Traceguids,
                "CX_Exception()");
            }
            throw (CX_Exception *)&pExceptionObject;
          }
          pExceptionObject = Length + v14 + 32;
          Start = CFastHeap::GetStart(a4);
          v35 = 4;
          if ( v12 != (_DWORD *)((char *)a4 + 16) )
            v35 = 12;
          v36 = (unsigned int)(*v12 + v35);
          v37 = pExceptionObject;
          if ( !(**v33)(v33, Start, v36, pExceptionObject) )
            return 0;
          v38 = (_DWORD *)*((_QWORD *)a4 + 1);
          v10 = v9;
          *v38 += v37;
          if ( *((CFastHeap **)a4 + 1) == (CFastHeap *)((char *)a4 + 16) )
            *(_DWORD *)(*(_QWORD *)a4 - 4LL) = *v38 | 0x80000000;
        }
        v15 = *((_QWORD *)a4 + 1);
        v16 = *(_DWORD *)(v15 + 4);
        *(_DWORD *)(v15 + 4) = v16 + v13;
        if ( (unsigned int)v9 > *(_DWORD *)(*((_QWORD *)a3 + 1) + 4LL) )
          throw (CX_Exception *)&pExceptionObject;
        if ( v16 > *(_DWORD *)(*((_QWORD *)a4 + 1) + 4LL) )
          throw (CX_Exception *)&pExceptionObject;
        LODWORD(v9) = v16;
        memcpy_0((void *)(*(_QWORD *)a4 + v16), (const void *)(v10 + *(_QWORD *)a3), v13);
      }
      *(_DWORD *)(**a1)(a1) = v9;
    }
    else if ( v5 == 13 )
    {
      v18 = (_DWORD *)(**a1)(a1);
      if ( *v18 > *(_DWORD *)(*((_QWORD *)a3 + 1) + 4LL) )
        throw (CX_Exception *)&pExceptionObject;
      v19 = (_DWORD *)(*(_QWORD *)a3 + (unsigned int)*v18);
      v20 = (_DWORD *)*((_QWORD *)a4 + 1);
      v21 = (unsigned int)(*v19 + 4);
      v22 = v20[1];
      if ( *v20 - v22 >= (unsigned int)v21 )
        goto LABEL_15;
      v39 = (unsigned int (__fastcall ***)(_QWORD, unsigned __int8 *, _QWORD, _QWORD))*((_QWORD *)a4 + 4);
      if ( !v39 )
      {
        v50 = GetMemLogObject();
        CMemoryLog::Write(v50, -2);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            13,
            WPP_5079cb25a27f37742ccdcc8b2574b31c_Traceguids,
            "CX_Exception()");
        }
        throw (CX_Exception *)&pExceptionObject;
      }
      v40 = v21 + v22 + 32;
      v41 = CFastHeap::GetStart(a4);
      v42 = 4;
      if ( v20 != (_DWORD *)((char *)a4 + 16) )
        v42 = 12;
      if ( (**v39)(v39, v41, (unsigned int)(*v20 + v42), v40) )
      {
        v43 = (_DWORD *)*((_QWORD *)a4 + 1);
        *v43 += v40;
        if ( *((CFastHeap **)a4 + 1) == (CFastHeap *)((char *)a4 + 16) )
          *(_DWORD *)(*(_QWORD *)a4 - 4LL) = *v43 | 0x80000000;
LABEL_15:
        v23 = *((_QWORD *)a4 + 1);
        v24 = *(_DWORD *)(v23 + 4);
        *(_DWORD *)(v23 + 4) = v24 + v21;
        v25 = CFastHeap::ResolveHeapPointer(a4, v24);
        memcpy_0(v25, v19, v21);
        *(_DWORD *)(**a1)(a1) = v24;
        return 1;
      }
      return 0;
    }
    return 1;
  }
  v26 = *(unsigned int *)(**a1)(a1);
  if ( (unsigned int)v26 > *(_DWORD *)(*((_QWORD *)a3 + 1) + 4LL) )
    throw (CX_Exception *)&pExceptionObject;
  v27 = CType::GetLength(v5);
  v28 = (_DWORD *)*((_QWORD *)a4 + 1);
  v29 = v28[1];
  v30 = *(_DWORD *)(v26 + *(_QWORD *)a3) * v27 + 4;
  if ( *v28 - v29 < (unsigned int)v30 )
  {
    if ( !*((_QWORD *)a4 + 4) )
    {
      v51 = GetMemLogObject();
      CMemoryLog::Write(v51, -2);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          WPP_5079cb25a27f37742ccdcc8b2574b31c_Traceguids,
          "CX_Exception()");
      }
      throw (CX_Exception *)&pExceptionObject;
    }
    pExceptionObject = v30 + v29 + 32;
    v44 = CFastHeap::GetStart(a4);
    v45 = 4;
    if ( v28 != (_DWORD *)((char *)a4 + 16) )
      v45 = 12;
    v46 = (unsigned int)(*v28 + v45);
    v47 = pExceptionObject;
    if ( !(***((unsigned int (__fastcall ****)(_QWORD, unsigned __int8 *, __int64, _QWORD))a4 + 4))(
            *((_QWORD *)a4 + 4),
            v44,
            v46,
            pExceptionObject) )
      return 0;
    v48 = (_DWORD *)*((_QWORD *)a4 + 1);
    *v48 += v47;
    if ( *((CFastHeap **)a4 + 1) == (CFastHeap *)((char *)a4 + 16) )
      *(_DWORD *)(*(_QWORD *)a4 - 4LL) = *v48 | 0x80000000;
  }
  v31 = *((_QWORD *)a4 + 1);
  v32 = *(_DWORD *)(v31 + 4);
  *(_DWORD *)(v31 + 4) = v32 + v30;
  if ( (unsigned int)v26 > *(_DWORD *)(*((_QWORD *)a3 + 1) + 4LL) )
    throw (CX_Exception *)&pExceptionObject;
  if ( v32 > *(_DWORD *)(*((_QWORD *)a4 + 1) + 4LL) )
    throw (CX_Exception *)&pExceptionObject;
  memcpy_0((void *)(*(_QWORD *)a4 + v32), (const void *)(*(_QWORD *)a3 + v26), v30);
  v52[1] = (__int64 (__fastcall **)(_QWORD))a4;
  v52[0] = (__int64 (__fastcall **)(_QWORD))&CHeapPtr::`vftable';
  v53 = v32;
  if ( (unsigned int)CUntypedArray::TranslateToNewHeap(v52, v5, a3, a4) )
  {
    *(_DWORD *)(**a1)(a1) = v32;
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180020664  push    rbp
0x180020666  push    rbx
0x180020667  push    rsi
0x180020668  push    rdi
0x180020669  push    r12
0x18002066b  push    r13
0x18002066d  push    r14
0x18002066f  push    r15
0x180020671  mov     rbp, rsp
0x180020674  sub     rsp, 58h
0x180020678  mov     ebx, edx
0x18002067a  mov     rsi, r9
0x18002067d  and     ebx, 0FFFh
0x180020683  mov     rdi, r8
0x180020686  mov     r14, rcx
0x180020689  bt      edx, 0Dh
0x18002068d  jb      loc_1800207D6
0x180020693  cmp     ebx, 8
0x180020696  jnz     loc_180020751
0x18002069c  mov     rax, [rcx]
0x18002069f  mov     rax, [rax]
0x1800206a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800206a7  mov     ebx, [rax]
0x1800206a9  mov     ecx, ebx; unsigned int
0x1800206ab  call    ?IsFakeAddress@CFastHeap@@SA_NK@Z; CFastHeap::IsFakeAddress(ulong)
0x1800206b0  test    al, al
0x1800206b2  jnz     short loc_18002072B
0x1800206b4  mov     rax, [rdi+8]
0x1800206b8  cmp     ebx, [rax+4]
0x1800206bb  ja      loc_180020A0D
0x1800206c1  mov     rcx, [rdi]
0x1800206c4  mov     r13d, ebx
0x1800206c7  add     rcx, rbx; this
0x1800206ca  call    ?GetLength@CCompressedString@@QEBAHXZ; CCompressedString::GetLength(void)
0x1800206cf  mov     r12, [rsi+8]
0x1800206d3  movsxd  r15, eax
0x1800206d6  mov     eax, [r12]
0x1800206da  mov     ecx, [r12+4]
0x1800206df  sub     eax, ecx
0x1800206e1  cmp     eax, r15d
0x1800206e4  jb      loc_18002089F
0x1800206ea  mov     rcx, [rsi+8]
0x1800206ee  mov     r9d, [rcx+4]
0x1800206f2  lea     eax, [r9+r15]
0x1800206f6  mov     [rcx+4], eax
0x1800206f9  mov     rax, [rdi+8]
0x1800206fd  cmp     ebx, [rax+4]
0x180020700  ja      loc_180020A1E
0x180020706  mov     rax, [rsi+8]
0x18002070a  cmp     r9d, [rax+4]
0x18002070e  ja      loc_180020A2F
0x180020714  mov     rdx, [rdi]
0x180020717  mov     ecx, r9d
0x18002071a  add     rcx, [rsi]; void *
0x18002071d  add     rdx, r13; Src
0x180020720  mov     r8, r15; Size
0x180020723  mov     ebx, r9d
0x180020726  call    memcpy_0
0x18002072b  mov     rcx, [r14]
0x18002072e  mov     rax, [rcx]
0x180020731  mov     rcx, r14
0x180020734  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020739  mov     [rax], ebx
0x18002073b  mov     eax, 1
0x180020740  add     rsp, 58h
0x180020744  pop     r15
0x180020746  pop     r14
0x180020748  pop     r13
0x18002074a  pop     r12
0x18002074c  pop     rdi
0x18002074d  pop     rsi
0x18002074e  pop     rbx
0x18002074f  pop     rbp
0x180020750  retn
0x180020751  lea     eax, [rbx-65h]
0x180020754  cmp     eax, 1
0x180020757  jbe     loc_18002069C
0x18002075d  cmp     ebx, 0Dh
0x180020760  jnz     short loc_18002073B
0x180020762  mov     rax, [rcx]
0x180020765  mov     rax, [rax]
0x180020768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002076d  mov     ecx, [rax]
0x18002076f  mov     rax, [rdi+8]
0x180020773  cmp     ecx, [rax+4]
0x180020776  ja      loc_180020A40
0x18002077c  mov     r12d, ecx
0x18002077f  add     r12, [rdi]
0x180020782  mov     rdi, [rsi+8]
0x180020786  mov     ebx, [r12]
0x18002078a  mov     eax, [rdi]
0x18002078c  add     ebx, 4
0x18002078f  mov     ecx, [rdi+4]
0x180020792  sub     eax, ecx
0x180020794  cmp     eax, ebx
0x180020796  jb      loc_180020920
0x18002079c  mov     rcx, [rsi+8]
0x1800207a0  mov     edi, [rcx+4]
0x1800207a3  mov     edx, edi; unsigned int
0x1800207a5  lea     eax, [rdi+rbx]
0x1800207a8  mov     [rcx+4], eax
0x1800207ab  mov     rcx, rsi; this
0x1800207ae  call    ?ResolveHeapPointer@CFastHeap@@QEAAPEAEK@Z; CFastHeap::ResolveHeapPointer(ulong)
0x1800207b3  mov     rcx, rax; void *
0x1800207b6  mov     r8, rbx; Size
0x1800207b9  mov     rdx, r12; Src
0x1800207bc  call    memcpy_0
0x1800207c1  mov     rax, [r14]
0x1800207c4  mov     rcx, r14
0x1800207c7  mov     rax, [rax]
0x1800207ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800207cf  mov     [rax], edi
0x1800207d1  jmp     loc_18002073B
0x1800207d6  mov     rax, [rcx]
0x1800207d9  mov     rax, [rax]
0x1800207dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800207e1  mov     r12d, [rax]
0x1800207e4  mov     rax, [rdi+8]
0x1800207e8  cmp     r12d, [rax+4]
0x1800207ec  ja      loc_180020A58
0x1800207f2  mov     ecx, ebx; unsigned int
0x1800207f4  call    ?GetLength@CType@@SAKK@Z; CType::GetLength(ulong)
0x1800207f9  mov     r15, [rsi+8]
0x1800207fd  mov     r13d, eax
0x180020800  mov     rax, [rdi]
0x180020803  mov     ecx, [r15+4]
0x180020807  imul    r13d, [r12+rax]
0x18002080c  mov     eax, [r15]
0x18002080f  sub     eax, ecx
0x180020811  add     r13d, 4
0x180020815  cmp     eax, r13d
0x180020818  jb      loc_180020996
0x18002081e  mov     rcx, [rsi+8]
0x180020822  mov     r15d, [rcx+4]
0x180020826  lea     eax, [r15+r13]
0x18002082a  mov     [rcx+4], eax
0x18002082d  mov     rax, [rdi+8]
0x180020831  cmp     r12d, [rax+4]
0x180020835  ja      loc_180020A69
0x18002083b  mov     rax, [rsi+8]
0x18002083f  cmp     r15d, [rax+4]
0x180020843  ja      loc_180020A7A
0x180020849  mov     rdx, r12
0x18002084c  movsxd  r8, r13d; Size
0x18002084f  add     rdx, [rdi]; Src
0x180020852  mov     ecx, r15d
0x180020855  add     rcx, [rsi]; void *
0x180020858  call    memcpy_0
0x18002085d  lea     rax, ??_7CHeapPtr@@6B@; const CHeapPtr::`vftable'
0x180020864  mov     [rbp+var_18], rsi
0x180020868  mov     r9, rsi
0x18002086b  mov     [rbp+var_20], rax
0x18002086f  mov     r8, rdi
0x180020872  mov     [rbp+var_10], r15d
0x180020876  mov     edx, ebx
0x180020878  lea     rcx, [rbp+var_20]
0x18002087c  call    ?TranslateToNewHeap@CUntypedArray@@SAHPEAVCPtrSource@@VCType@@PEAVCFastHeap@@2@Z; CUntypedArray::TranslateToNewHeap(CPtrSource *,CType,CFastHeap *,CFastHeap *)
0x180020881  test    eax, eax
0x180020883  jz      loc_180020A51
0x180020889  mov     rax, [r14]
0x18002088c  mov     rcx, r14
0x18002088f  mov     rax, [rax]
0x180020892  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020897  mov     [rax], r15d
0x18002089a  jmp     loc_18002073B
0x18002089f  mov     r13, [rsi+20h]
0x1800208a3  test    r13, r13
0x1800208a6  jz      loc_180020A8B
0x1800208ac  lea     eax, [rcx+20h]
0x1800208af  mov     rcx, rsi; this
0x1800208b2  add     eax, r15d
0x1800208b5  mov     [rbp+pExceptionObject], eax
0x1800208b8  call    ?GetStart@CFastHeap@@QEAAPEAEXZ; CFastHeap::GetStart(void)
0x1800208bd  mov     r8d, 4
0x1800208c3  lea     rcx, [rsi+10h]
0x1800208c7  cmp     r12, rcx
0x1800208ca  mov     rdx, rax
0x1800208cd  mov     rax, [r13+0]
0x1800208d1  mov     rcx, r13
0x1800208d4  lea     r9d, [r8+8]
0x1800208d8  cmovnz  r8d, r9d
0x1800208dc  add     r8d, [r12]
0x1800208e0  mov     r12d, [rbp+pExceptionObject]
0x1800208e4  mov     r9d, r12d
0x1800208e7  mov     rax, [rax]
0x1800208ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800208ef  test    eax, eax
0x1800208f1  jz      loc_180020A51
0x1800208f7  mov     rax, [rsi+8]
0x1800208fb  mov     r13, rbx
0x1800208fe  add     [rax], r12d
0x180020901  mov     ecx, [rax]
0x180020903  lea     rax, [rsi+10h]
0x180020907  cmp     [rsi+8], rax
0x18002090b  jnz     loc_1800206EA
0x180020911  mov     rax, [rsi]
0x180020914  bts     ecx, 1Fh
0x180020918  mov     [rax-4], ecx
0x18002091b  jmp     loc_1800206EA
0x180020920  mov     r15, [rsi+20h]
0x180020924  test    r15, r15
0x180020927  jz      loc_180020AC7
0x18002092d  lea     r13d, [rcx+20h]
0x180020931  mov     rcx, rsi; this
0x180020934  add     r13d, ebx
0x180020937  call    ?GetStart@CFastHeap@@QEAAPEAEXZ; CFastHeap::GetStart(void)
0x18002093c  mov     r8d, 4
0x180020942  lea     rcx, [rsi+10h]
0x180020946  mov     rdx, rax
0x180020949  cmp     rdi, rcx
0x18002094c  mov     rax, [r15]
0x18002094f  mov     rcx, r15
0x180020952  lea     r9d, [r8+8]
0x180020956  cmovnz  r8d, r9d
0x18002095a  mov     r9d, r13d
0x18002095d  add     r8d, [rdi]
0x180020960  mov     rax, [rax]
0x180020963  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020968  test    eax, eax
0x18002096a  jz      loc_180020A51
0x180020970  mov     rax, [rsi+8]
0x180020974  add     [rax], r13d
0x180020977  mov     ecx, [rax]
0x180020979  lea     rax, [rsi+10h]
0x18002097d  cmp     [rsi+8], rax
0x180020981  jnz     loc_18002079C
0x180020987  mov     rax, [rsi]
0x18002098a  bts     ecx, 1Fh
0x18002098e  mov     [rax-4], ecx
0x180020991  jmp     loc_18002079C
0x180020996  cmp     qword ptr [rsi+20h], 0
0x18002099b  jz      loc_180020AFF
0x1800209a1  lea     eax, [rcx+20h]
0x1800209a4  mov     rcx, rsi; this
0x1800209a7  add     eax, r13d
0x1800209aa  mov     [rbp+pExceptionObject], eax
0x1800209ad  call    ?GetStart@CFastHeap@@QEAAPEAEXZ; CFastHeap::GetStart(void)
0x1800209b2  mov     rcx, [rsi+20h]
0x1800209b6  lea     r10, [rsi+10h]
0x1800209ba  mov     r8d, 4
0x1800209c0  cmp     r15, r10
0x1800209c3  mov     rdx, rax
0x1800209c6  mov     rax, [rcx]
0x1800209c9  lea     r9d, [r8+8]
0x1800209cd  cmovnz  r8d, r9d
0x1800209d1  add     r8d, [r15]
0x1800209d4  mov     r15d, [rbp+pExceptionObject]
0x1800209d8  mov     r9d, r15d
0x1800209db  mov     rax, [rax]
0x1800209de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800209e3  test    eax, eax
0x1800209e5  jz      short loc_180020A51
0x1800209e7  mov     rax, [rsi+8]
0x1800209eb  add     [rax], r15d
0x1800209ee  mov     ecx, [rax]
0x1800209f0  lea     rax, [rsi+10h]
0x1800209f4  cmp     [rsi+8], rax
0x1800209f8  jnz     loc_18002081E
0x1800209fe  mov     rax, [rsi]
0x180020a01  bts     ecx, 1Fh
0x180020a05  mov     [rax-4], ecx
0x180020a08  jmp     loc_18002081E
0x180020a0d  lea     rdx, _TI1?AVCX_Exception@@; pThrowInfo
0x180020a14  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180020a18  call    _CxxThrowException_0
0x180020a1e  lea     rdx, _TI1?AVCX_Exception@@; pThrowInfo
0x180020a25  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180020a29  call    _CxxThrowException_0
0x180020a2f  lea     rdx, _TI1?AVCX_Exception@@; pThrowInfo
0x180020a36  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180020a3a  call    _CxxThrowException_0
0x180020a40  lea     rdx, _TI1?AVCX_Exception@@; pThrowInfo
0x180020a47  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180020a4b  call    _CxxThrowException_0
0x180020a51  xor     eax, eax
0x180020a53  jmp     loc_180020740
0x180020a58  lea     rdx, _TI1?AVCX_Exception@@; pThrowInfo
0x180020a5f  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180020a63  call    _CxxThrowException_0
0x180020a69  lea     rdx, _TI1?AVCX_Exception@@; pThrowInfo
0x180020a70  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180020a74  call    _CxxThrowException_0
0x180020a7a  lea     rdx, _TI1?AVCX_Exception@@; pThrowInfo
0x180020a81  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180020a85  call    _CxxThrowException_0
0x180020a8b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180020a91  mov     rcx, rax
0x180020a94  mov     edx, 0FFFFFFFEh
0x180020a99  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180020a9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180020aa6  lea     rax, WPP_GLOBAL_Control
0x180020aad  cmp     rcx, rax
0x180020ab0  jnz     loc_180020B37
0x180020ab6  lea     rdx, _TI1?AVCX_Exception@@; pThrowInfo
0x180020abd  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180020ac1  call    _CxxThrowException_0
0x180020ac7  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180020acd  mov     rcx, rax
0x180020ad0  mov     edx, 0FFFFFFFEh
0x180020ad5  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
  ... truncated ...
```
