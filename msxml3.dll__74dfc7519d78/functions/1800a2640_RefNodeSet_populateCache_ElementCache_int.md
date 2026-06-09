# RefNodeSet::populateCache(ElementCache *,int)

- ea: `0x1800a2640`
- end: `0x1800a2a2a`
- name: `?populateCache@RefNodeSet@@MEAAXPEAVElementCache@@H@Z`
- size: `1002`
- prototype: `void(RefNodeSet *__hidden this, struct ElementCache *, int)`
- caller_count: `0`
- callee_count: `20`
- tags: ``

## callees

- `0x180012000`
- `0x18001434c`
- `0x18003462c`
- `0x18003f5d8`
- `0x1800417e8`
- `0x18004aca4`
- `0x18004c430`
- `0x180052318`
- `0x18005258c`
- `0x18005e9e8`
- `0x18005f9b8`
- `0x180064034`
- `0x18006d790`
- `0x1800980d8`
- `0x180098210`
- `0x1800982d0`
- `0x1800a2248`
- `0x1800a2640`
- `0x1800ecb4c`
- `0x180107010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x1800a293a`
- `msvcrt!_resetstkoflw` at `0x1800a293a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a298d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a298d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800a2928`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800a29cb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800a2928`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800a29cb`

## pseudocode

```c
void __fastcall RefNodeSet::populateCache(RefNodeSet *this, struct ElementCache *a2)
{
  struct Name *v4; // r12
  struct IUnknown **v5; // r15
  __int64 v6; // rax
  __int64 v7; // rcx
  __int64 v8; // rax
  void *v9; // rax
  Document **v10; // r13
  __int64 v11; // rax
  __int64 v12; // rsi
  void *v13; // rax
  __int64 v14; // r8
  void *v15; // rax
  int v16; // r14d
  unsigned __int16 *v17; // rsi
  unsigned __int16 *v18; // rax
  struct Element *v19; // rax
  struct Element *v20; // r12
  struct Path *PathFromRoot; // rax
  int v22; // [rsp+38h] [rbp-80h] BYREF
  char v23; // [rsp+3Ch] [rbp-7Ch]
  void *v24; // [rsp+40h] [rbp-78h]
  _QWORD v25[2]; // [rsp+48h] [rbp-70h] BYREF
  unsigned __int16 *v26; // [rsp+58h] [rbp-60h]
  int v27; // [rsp+68h] [rbp-50h] BYREF
  char v28; // [rsp+6Ch] [rbp-4Ch]
  unsigned int v29; // [rsp+D8h] [rbp+20h] BYREF

  v4 = 0;
  v27 = 0;
  v28 = 0;
  v5 = (struct IUnknown **)((char *)this + 88);
  if ( !*((_QWORD *)this + 11) && !*((_QWORD *)this + 8) )
  {
    v22 = 0;
    v23 = 0;
    if ( !(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 136LL))(*((_QWORD *)this + 7)) )
    {
      ElementCache::doneCaching(a2);
      OperandValue::clear((OperandValue *)&v22);
      goto LABEL_5;
    }
    v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 56LL))(*((_QWORD *)this + 1));
    v25[0] = v6;
    v7 = *(_QWORD *)(v6 + 24) + 8LL;
    if ( !*(_QWORD *)(v6 + 40) )
      *(_QWORD *)(v6 + 40) = v7;
    ++*(_DWORD *)(v6 + 32);
    v25[1] = v7;
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, int *))(**(_QWORD **)(*((_QWORD *)this + 6) + 64LL) + 184LL))(
      *(_QWORD *)(*((_QWORD *)this + 6) + 64LL),
      *((_QWORD *)this + 1),
      *((_QWORD *)this + 7),
      &v22);
    if ( (unsigned int)(v22 - 6) > 1 )
    {
      OperandValue::convertTo(&v22, *((_QWORD *)this + 1), 5, &v22, *(_DWORD *)(*((_QWORD *)this + 6) + 24LL));
      v8 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 136LL))(*((_QWORD *)this + 7));
      v9 = (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 400LL))(v8);
      assign((struct IUnknown **)this + 10, v9);
      assign(v5, v24);
    }
    else
    {
      *((_QWORD *)this + 8) = v24;
      ScopedCleanup::clearMark((ScopedCleanup *)v25);
    }
    ScopedCleanup::~ScopedCleanup((ScopedCleanup *)v25);
    OperandValue::clear((OperandValue *)&v22);
  }
  ElementCache::startCaching((struct IUnknown **)a2);
  v10 = (Document **)((char *)this + 80);
  while ( 1 )
  {
    if ( !*v5 )
    {
      v11 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 136LL))(*((_QWORD *)this + 8));
      v12 = v11;
      if ( !v11 )
        break;
      v13 = (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 400LL))(v11);
      assign((struct IUnknown **)this + 10, v13);
      LOBYTE(v14) = 1;
      v15 = (void *)(*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)this + 1) + 32LL))(
                      *((_QWORD *)this + 1),
                      v12,
                      v14);
      assign(v5, v15);
    }
    ParseNames::ParseNames((ParseNames *)v25, (struct NamespaceMgr *)(*v10)[31].lpVtbl, (struct String *)*v5, 0);
    v16 = 0;
    v17 = v26;
    while ( 1 )
    {
      v29 = 0;
      v18 = (unsigned __int16 *)ParseNames::parseNameListThrow(v17, &v29, 0);
      v17 = v18;
      v26 = v18;
      if ( v18 )
      {
        v4 = Name::create(0, v18, v29, 0);
        v17 += v29;
        v26 = v17;
      }
      if ( !v4 )
        break;
      if ( v16 >= *((_DWORD *)this + 18) )
      {
        v19 = (struct Element *)Document::nodeFromID(*v10, v4);
        v20 = v19;
        if ( v19 )
        {
          PathFromRoot = QueryHelper::getPathFromRoot(v19, 0);
          ElementCache::addCachedElement((struct IUnknown **)a2, v20, PathFromRoot);
        }
        ++*((_DWORD *)this + 18);
      }
      ++v16;
      v4 = 0;
    }
    *((_DWORD *)this + 18) = 0;
    if ( !*((_QWORD *)this + 8) )
      break;
    assign(v5, 0);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 144LL))(*((_QWORD *)this + 8));
  }
  ElementCache::doneCaching(a2);
  ElementCache::sortAndRemoveDuplicates(a2);
LABEL_5:
  OperandValue::clear((OperandValue *)&v27);
}

```

## disassembly

```asm
0x1800a2640  mov     rax, rsp
0x1800a2643  mov     [rax+10h], rdx
0x1800a2647  mov     [rax+8], rcx
0x1800a264b  push    rbx
0x1800a264c  push    rsi
0x1800a264d  push    rdi
0x1800a264e  push    r12
0x1800a2650  push    r13
0x1800a2652  push    r14
0x1800a2654  push    r15
0x1800a2656  sub     rsp, 80h
0x1800a265d  mov     rdi, rdx
0x1800a2660  mov     rbx, rcx
0x1800a2663  xor     r12d, r12d
0x1800a2666  mov     [rax-50h], r12d
0x1800a266a  mov     [rax-4Ch], r12b
0x1800a266e  lea     r15, [rcx+58h]
0x1800a2672  cmp     [r15], r12
0x1800a2675  jnz     loc_1800A27C1
0x1800a267b  cmp     [rcx+40h], r12
0x1800a267f  jnz     loc_1800A27C1
0x1800a2685  mov     [rax-80h], r12d
0x1800a2689  mov     [rax-7Ch], r12b
0x1800a268d  mov     rcx, [rcx+38h]
0x1800a2691  mov     rax, [rcx]
0x1800a2694  mov     rax, [rax+88h]
0x1800a269b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a26a0  test    rax, rax
0x1800a26a3  jnz     short loc_1800A26D4
0x1800a26a5  mov     rcx, rdi; this
0x1800a26a8  call    ?doneCaching@ElementCache@@QEAAXXZ; ElementCache::doneCaching(void)
0x1800a26ad  lea     rcx, [rsp+0B8h+var_80]; this
0x1800a26b2  call    ?clear@OperandValue@@QEAAXXZ; OperandValue::clear(void)
0x1800a26b7  lea     rcx, [rsp+0B8h+var_50]; this
0x1800a26bc  call    ?clear@OperandValue@@QEAAXXZ; OperandValue::clear(void)
0x1800a26c1  add     rsp, 80h
0x1800a26c8  pop     r15
0x1800a26ca  pop     r14
0x1800a26cc  pop     r13
0x1800a26ce  pop     r12
0x1800a26d0  pop     rdi
0x1800a26d1  pop     rsi
0x1800a26d2  pop     rbx
0x1800a26d3  retn
0x1800a26d4  mov     rcx, [rbx+8]
0x1800a26d8  mov     rax, [rcx]
0x1800a26db  mov     rax, [rax+38h]
0x1800a26df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a26e4  mov     [rsp+0B8h+var_70], rax
0x1800a26e9  mov     rcx, [rax+18h]
0x1800a26ed  add     rcx, 8
0x1800a26f1  cmp     [rax+28h], r12
0x1800a26f5  jnz     short loc_1800A26FB
0x1800a26f7  mov     [rax+28h], rcx
0x1800a26fb  inc     dword ptr [rax+20h]
0x1800a26fe  mov     [rsp+0B8h+var_68], rcx
0x1800a2703  mov     rax, [rbx+30h]
0x1800a2707  mov     rcx, [rax+40h]
0x1800a270b  mov     rax, [rcx]
0x1800a270e  lea     r9, [rsp+0B8h+var_80]
0x1800a2713  mov     r8, [rbx+38h]
0x1800a2717  mov     rdx, [rbx+8]
0x1800a271b  mov     rax, [rax+0B8h]
0x1800a2722  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2727  mov     eax, [rsp+0B8h+var_80]
0x1800a272b  add     eax, 0FFFFFFFAh
0x1800a272e  cmp     eax, 1
0x1800a2731  ja      short loc_1800A2748
0x1800a2733  mov     rax, [rsp+0B8h+var_78]
0x1800a2738  mov     [rbx+40h], rax
0x1800a273c  lea     rcx, [rsp+0B8h+var_70]; this
0x1800a2741  call    ?clearMark@ScopedCleanup@@QEAAXXZ; ScopedCleanup::clearMark(void)
0x1800a2746  jmp     short loc_1800A27AD
0x1800a2748  mov     rax, [rbx+30h]
0x1800a274c  mov     ecx, [rax+18h]
0x1800a274f  mov     [rsp+0B8h+var_98], ecx
0x1800a2753  lea     r9, [rsp+0B8h+var_80]
0x1800a2758  mov     r8d, 5
0x1800a275e  mov     rdx, [rbx+8]
0x1800a2762  lea     rcx, [rsp+0B8h+var_80]
0x1800a2767  call    ?convertTo@OperandValue@@QEAAXPEAVQueryContext@@W4Type@1@PEAV1@K@Z; OperandValue::convertTo(QueryContext *,OperandValue::Type,OperandValue *,ulong)
0x1800a276c  mov     rcx, [rbx+38h]
0x1800a2770  mov     rax, [rcx]
0x1800a2773  mov     rax, [rax+88h]
0x1800a277a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a277f  mov     rdx, rax
0x1800a2782  mov     rcx, [rax]
0x1800a2785  mov     rax, [rcx+190h]
0x1800a278c  mov     rcx, rdx
0x1800a278f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2794  lea     rcx, [rbx+50h]; struct IUnknown **
0x1800a2798  mov     rdx, rax; void *
0x1800a279b  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800a27a0  mov     rdx, [rsp+0B8h+var_78]; void *
0x1800a27a5  mov     rcx, r15; struct IUnknown **
0x1800a27a8  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800a27ad  lea     rcx, [rsp+0B8h+var_70]; this
0x1800a27b2  call    ??1ScopedCleanup@@QEAA@XZ; ScopedCleanup::~ScopedCleanup(void)
0x1800a27b7  lea     rcx, [rsp+0B8h+var_80]; this
0x1800a27bc  call    ?clear@OperandValue@@QEAAXXZ; OperandValue::clear(void)
0x1800a27c1  mov     rcx, rdi; this
0x1800a27c4  call    ?startCaching@ElementCache@@QEAAXXZ; ElementCache::startCaching(void)
0x1800a27c9  lea     r13, [rbx+50h]
0x1800a27cd  cmp     [r15], r12
0x1800a27d0  jnz     short loc_1800A2830
0x1800a27d2  mov     rcx, [rbx+40h]
0x1800a27d6  mov     rax, [rcx]
0x1800a27d9  mov     rax, [rax+88h]
0x1800a27e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a27e5  mov     rsi, rax
0x1800a27e8  test    rax, rax
0x1800a27eb  jz      loc_1800A2A0F
0x1800a27f1  mov     rcx, [rax]
0x1800a27f4  mov     rax, [rcx+190h]
0x1800a27fb  mov     rcx, rsi
0x1800a27fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2803  mov     rdx, rax; void *
0x1800a2806  mov     rcx, r13; struct IUnknown **
0x1800a2809  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800a280e  mov     rcx, [rbx+8]
0x1800a2812  mov     rax, [rcx]
0x1800a2815  mov     r8b, 1
0x1800a2818  mov     rdx, rsi
0x1800a281b  mov     rax, [rax+20h]
0x1800a281f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2824  mov     rdx, rax; void *
0x1800a2827  mov     rcx, r15; struct IUnknown **
0x1800a282a  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800a282f  nop
0x1800a2830  mov     rdx, [r13+0]
0x1800a2834  xor     r9d, r9d; bool
0x1800a2837  mov     r8, [r15]; struct String *
0x1800a283a  mov     rdx, [rdx+0F8h]; struct NamespaceMgr *
0x1800a2841  lea     rcx, [rsp+0B8h+var_70]; this
0x1800a2846  call    ??0ParseNames@@QEAA@PEAVNamespaceMgr@@PEAVString@@_N@Z; ParseNames::ParseNames(NamespaceMgr *,String *,bool)
0x1800a284b  mov     r14d, r12d
0x1800a284e  mov     [rsp+0B8h+var_88], r12d
0x1800a2853  mov     rsi, [rsp+0B8h+var_60]
0x1800a2858  mov     [rsp+0B8h+arg_18], r12d
0x1800a2860  xor     r8d, r8d; unsigned int *
0x1800a2863  lea     rdx, [rsp+0B8h+arg_18]; unsigned int *
0x1800a286b  mov     rcx, rsi; unsigned __int16 *
0x1800a286e  call    ?parseNameListThrow@ParseNames@@SAPEBGPEBGPEAK1@Z; ParseNames::parseNameListThrow(ushort const *,ulong *,ulong *)
0x1800a2873  mov     rsi, rax
0x1800a2876  mov     [rsp+0B8h+var_60], rax
0x1800a287b  test    rax, rax
0x1800a287e  jz      short loc_1800A28A8
0x1800a2880  xor     r9d, r9d; struct Atom *
0x1800a2883  mov     r8d, [rsp+0B8h+arg_18]; int
0x1800a288b  mov     rdx, rax; unsigned __int16 *
0x1800a288e  xor     ecx, ecx; struct String *
0x1800a2890  call    ?create@Name@@KAPEAV1@PEAVString@@PEBGHPEAVAtom@@@Z; Name::create(String *,ushort const *,int,Atom *)
0x1800a2895  mov     r12, rax
0x1800a2898  mov     ecx, [rsp+0B8h+arg_18]
0x1800a289f  lea     rsi, [rsi+rcx*2]
0x1800a28a3  mov     [rsp+0B8h+var_60], rsi
0x1800a28a8  test    r12, r12
0x1800a28ab  jz      short loc_1800A28F2
0x1800a28ad  cmp     r14d, [rbx+48h]
0x1800a28b1  jl      short loc_1800A28E2
0x1800a28b3  mov     rdx, r12; struct Name *
0x1800a28b6  mov     rcx, [r13+0]; this
0x1800a28ba  call    ?nodeFromID@Document@@QEAAPEAVNode@@PEAVName@@@Z; Document::nodeFromID(Name *)
0x1800a28bf  mov     r12, rax
0x1800a28c2  test    rax, rax
0x1800a28c5  jz      short loc_1800A28DF
0x1800a28c7  xor     edx, edx; struct Path *
0x1800a28c9  mov     rcx, rax; struct Element *
0x1800a28cc  call    ?getPathFromRoot@QueryHelper@@SAPEAVPath@@PEAVElement@@PEAV2@@Z; QueryHelper::getPathFromRoot(Element *,Path *)
0x1800a28d1  mov     r8, rax; struct Path *
0x1800a28d4  mov     rdx, r12; struct Element *
0x1800a28d7  mov     rcx, rdi; this
0x1800a28da  call    ?addCachedElement@ElementCache@@QEAAXPEAVElement@@PEAVPath@@@Z; ElementCache::addCachedElement(Element *,Path *)
0x1800a28df  inc     dword ptr [rbx+48h]
0x1800a28e2  inc     r14d
0x1800a28e5  mov     [rsp+0B8h+var_88], r14d
0x1800a28ea  xor     r12d, r12d
0x1800a28ed  jmp     loc_1800A2858
0x1800a28f2  mov     [rbx+48h], r12d
0x1800a28f6  cmp     [rbx+40h], r12
0x1800a28fa  jz      loc_1800A2A0F
0x1800a2900  xor     edx, edx; void *
0x1800a2902  mov     rcx, r15; struct IUnknown **
0x1800a2905  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800a290a  mov     rcx, [rbx+40h]
0x1800a290e  mov     rax, [rcx]
0x1800a2911  mov     rax, [rax+90h]
0x1800a2918  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a291d  jmp     loc_1800A27CD
0x1800a2922  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x1800a2928  call    cs:__imp_TlsGetValue
0x1800a292e  mov     rbx, rax
0x1800a2931  cmp     dword ptr [rax+54h], 0C00000FDh
0x1800a2938  jnz     short loc_1800A29B3
0x1800a293a  call    cs:__imp__resetstkoflw
0x1800a2940  test    eax, eax
0x1800a2942  jnz     short loc_1800A2995
0x1800a2944  mov     rcx, cs:?g_pMutexGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexGC
0x1800a294b  test    rcx, rcx
0x1800a294e  jz      short loc_1800A2962
0x1800a2950  cmp     [rcx+50h], rbx
0x1800a2954  jnz     short loc_1800A2962
0x1800a2956  mov     rax, [rcx]
0x1800a2959  mov     rax, [rax+20h]
0x1800a295d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2962  mov     rcx, cs:?g_pMutexFullGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexFullGC
0x1800a2969  test    rcx, rcx
0x1800a296c  jz      short loc_1800A2980
0x1800a296e  cmp     [rcx+50h], rbx
0x1800a2972  jnz     short loc_1800A2980
0x1800a2974  mov     rax, [rcx]
0x1800a2977  mov     rax, [rax+20h]
0x1800a297b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2980  xor     r9d, r9d; lpArguments
0x1800a2983  xor     r8d, r8d; nNumberOfArguments
0x1800a2986  xor     edx, edx; dwExceptionFlags
0x1800a2988  mov     ecx, 0C00000FDh; dwExceptionCode
0x1800a298d  call    cs:__imp_RaiseException
0x1800a2993  jmp     short loc_1800A29B3
0x1800a2995  mov     rax, [rbx+60h]
0x1800a2999  mov     [rbx+68h], rax
0x1800a299d  lea     rax, ?s_cexpOutOfStack@Exception@@2V_CodebaseException@@B; _CodebaseException const Exception::s_cexpOutOfStack
0x1800a29a4  mov     [rbx+60h], rax
0x1800a29a8  mov     dword ptr [rbx+54h], 800703E9h
0x1800a29af  mov     byte ptr [rbx+78h], 0
0x1800a29b3  mov     rax, [rsp+0B8h+arg_0]
0x1800a29bb  mov     rcx, [rax+30h]
0x1800a29bf  cmp     dword ptr [rcx+18h], 2
0x1800a29c3  jnz     short loc_1800A2A24
0x1800a29c5  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x1800a29cb  call    cs:__imp_TlsGetValue
0x1800a29d1  mov     rcx, [rax+60h]; struct Exception *
0x1800a29d5  call    ?setErrorInfo@_dispatchImpl@@SAPEAVException@@PEAV2@@Z; _dispatchImpl::setErrorInfo(Exception *)
0x1800a29da  mov     rdx, rax
0x1800a29dd  mov     rcx, [rax]
0x1800a29e0  mov     rax, [rcx+80h]
0x1800a29e7  mov     rcx, rdx
0x1800a29ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a29ef  test    eax, 0C00CE000h
0x1800a29f4  jnz     short loc_1800A2A24
0x1800a29f6  mov     rdi, [rsp+0B8h+arg_8]
0x1800a29fe  mov     rcx, rdi; this
0x1800a2a01  call    ?clearCache@ElementCache@@QEAAXXZ; ElementCache::clearCache(void)
0x1800a2a06  mov     rcx, rdi; this
0x1800a2a09  call    ?startCaching@ElementCache@@QEAAXXZ; ElementCache::startCaching(void)
0x1800a2a0e  nop
0x1800a2a0f  mov     rcx, rdi; this
0x1800a2a12  call    ?doneCaching@ElementCache@@QEAAXXZ; ElementCache::doneCaching(void)
0x1800a2a17  mov     rcx, rdi; this
0x1800a2a1a  call    ?sortAndRemoveDuplicates@ElementCache@@QEAAXXZ; ElementCache::sortAndRemoveDuplicates(void)
0x1800a2a1f  jmp     loc_1800A26B7
0x1800a2a24  call    ?throwAgain@Exception@@SAXXZ; Exception::throwAgain(void)
0x180103974  push    rbp
0x180103976  sub     rsp, 30h
0x18010397a  mov     rbp, rdx
0x18010397d  xor     edx, edx; bool
0x18010397f  call    ?fillException@Exception@@SAHPEAU_EXCEPTION_POINTERS@@_N@Z
0x180103984  nop
0x180103985  add     rsp, 30h
0x180103989  pop     rbp
0x18010398a  retn
```
