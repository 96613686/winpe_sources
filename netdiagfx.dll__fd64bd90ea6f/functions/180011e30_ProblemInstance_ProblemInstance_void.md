# ProblemInstance::~ProblemInstance(void)

- ea: `0x180011e30`
- end: `0x18001217a`
- name: `??1ProblemInstance@@QEAA@XZ`
- size: `842`
- prototype: `void __fastcall(ProblemInstance *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800117e8`

## callees

- `0x180005ff8`
- `0x180006d58`
- `0x180008db8`
- `0x180009328`
- `0x18000bda4`
- `0x1800100e8`
- `0x180011e30`
- `0x180012180`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011e7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011ea2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011eed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011ef8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011f24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011f60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011f6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011f97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011fd9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011fe4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012010`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012052`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001205d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001208b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011e7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011ea2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011eed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011ef8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011f24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011f60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011f6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011f97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011fd9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011fe4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012010`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012052`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001205d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001208b`

## pseudocode

```c
void __fastcall ProblemInstance::~ProblemInstance(ProblemInstance *this)
{
  __m128i **v2; // rbx
  __m128i *v3; // rbx
  __m128i **v4; // rcx
  __m128i v5; // xmm6
  __m128i v6; // xmm7
  int v7; // eax
  __int64 v8; // rcx
  unsigned int i; // ebp
  __int64 v10; // rdi
  __int64 v11; // rbx
  unsigned int j; // ebp
  __int64 v13; // rdi
  __int64 v14; // rbx
  unsigned int k; // ebp
  __int64 v16; // rdi
  __int64 v17; // rbx
  unsigned int m; // ebp
  __int64 v19; // rdi
  __int64 v20; // rbx
  __int64 v21; // rcx
  unsigned int v22; // edx
  ProtectedNetDiagHelper *v23; // rcx

  v2 = (__m128i **)*((_QWORD *)this + 5);
  if ( v2 && v2[1] )
  {
    v3 = *v2;
    while ( 1 )
    {
      while ( 1 )
      {
        v3 = (__m128i *)v3->m128i_i64[0];
        v4 = (__m128i **)*((_QWORD *)this + 5);
        if ( v3 == *v4 )
        {
          std::list<ProblemNode *>::clear(v4);
          goto LABEL_10;
        }
        v5 = v3[1];
        v6 = v3[2];
        CoTaskMemFree((LPVOID)v3[1].m128i_i64[0]);
        v7 = _mm_cvtsi128_si32(_mm_srli_si128(v5, 8));
        if ( v7 != 10 )
          break;
LABEL_8:
        CoTaskMemFree((LPVOID)v6.m128i_i64[0]);
      }
      if ( v7 == 14 )
      {
        v6.m128i_i64[0] = _mm_srli_si128(v6, 8).m128i_u64[0];
        goto LABEL_8;
      }
    }
  }
LABEL_10:
  v8 = *((_QWORD *)this + 5);
  if ( v8 )
    std::list<tagHELPER_ATTRIBUTE>::`scalar deleting destructor'(v8);
  *((_QWORD *)this + 5) = 0;
  if ( *((_QWORD *)this + 38) )
  {
    for ( i = 0; (unsigned __int64)i < *((_QWORD *)this + 16); ++i )
    {
      v10 = 32LL * i;
      v11 = *((_QWORD *)this + 38);
      CoTaskMemFree(*(LPVOID *)(v10 + v11));
      CoTaskMemFree(*(LPVOID *)(v10 + v11 + 8));
      FreeHelperAttributes(*(struct tagHELPER_ATTRIBUTE **)(v10 + v11 + 24), *(_DWORD *)(v10 + v11 + 16), 1);
    }
    CoTaskMemFree(*((LPVOID *)this + 38));
  }
  *((_QWORD *)this + 38) = 0;
  std::list<ProblemNode *>::clear((char *)this + 120);
  if ( *((_QWORD *)this + 39) )
  {
    for ( j = 0; (unsigned __int64)j < *((_QWORD *)this + 18); ++j )
    {
      v13 = 32LL * j;
      v14 = *((_QWORD *)this + 39);
      CoTaskMemFree(*(LPVOID *)(v13 + v14));
      CoTaskMemFree(*(LPVOID *)(v13 + v14 + 8));
      FreeHelperAttributes(*(struct tagHELPER_ATTRIBUTE **)(v13 + v14 + 24), *(_DWORD *)(v13 + v14 + 16), 1);
    }
    CoTaskMemFree(*((LPVOID *)this + 39));
  }
  *((_QWORD *)this + 39) = 0;
  std::list<ProblemNode *>::clear((char *)this + 136);
  if ( *((_QWORD *)this + 40) )
  {
    for ( k = 0; (unsigned __int64)k < *((_QWORD *)this + 20); ++k )
    {
      v16 = 32LL * k;
      v17 = *((_QWORD *)this + 40);
      CoTaskMemFree(*(LPVOID *)(v16 + v17));
      CoTaskMemFree(*(LPVOID *)(v16 + v17 + 8));
      FreeHelperAttributes(*(struct tagHELPER_ATTRIBUTE **)(v16 + v17 + 24), *(_DWORD *)(v16 + v17 + 16), 1);
    }
    CoTaskMemFree(*((LPVOID *)this + 40));
  }
  *((_QWORD *)this + 40) = 0;
  std::list<ProblemNode *>::clear((char *)this + 152);
  if ( *((_QWORD *)this + 41) )
  {
    for ( m = 0; (unsigned __int64)m < *((_QWORD *)this + 22); ++m )
    {
      v19 = 32LL * m;
      v20 = *((_QWORD *)this + 41);
      CoTaskMemFree(*(LPVOID *)(v19 + v20));
      CoTaskMemFree(*(LPVOID *)(v19 + v20 + 8));
      FreeHelperAttributes(*(struct tagHELPER_ATTRIBUTE **)(v19 + v20 + 24), *(_DWORD *)(v19 + v20 + 16), 1);
    }
    CoTaskMemFree(*((LPVOID *)this + 41));
  }
  *((_QWORD *)this + 41) = 0;
  std::list<ProblemNode *>::clear((char *)this + 168);
  FreeRepairInfos(*((struct tagRepairInfo **)this + 14), *((_DWORD *)this + 26), 1);
  *((_QWORD *)this + 14) = 0;
  *((_DWORD *)this + 26) = 0;
  v21 = *((_QWORD *)this + 9);
  if ( v21 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 136LL))(v21);
    v23 = (ProtectedNetDiagHelper *)*((_QWORD *)this + 9);
    if ( v23 )
      ProtectedNetDiagHelper::`scalar deleting destructor'(v23, v22);
    *((_QWORD *)this + 9) = 0;
  }
  std::list<ProblemNode *>::~list<ProblemNode *>((void **)this + 21);
  std::list<ProblemNode *>::~list<ProblemNode *>((void **)this + 19);
  std::list<ProblemNode *>::~list<ProblemNode *>((void **)this + 17);
  std::list<ProblemNode *>::~list<ProblemNode *>((void **)this + 15);
  ATL::CStringData::Release((ATL::CStringData *)(*((_QWORD *)this + 11) - 24LL));
  ATL::CStringData::Release((ATL::CStringData *)(*((_QWORD *)this + 10) - 24LL));
  ATL::CStringData::Release((ATL::CStringData *)(*((_QWORD *)this + 3) - 24LL));
  ATL::CStringData::Release((ATL::CStringData *)(*((_QWORD *)this + 2) - 24LL));
  ATL::CStringData::Release((ATL::CStringData *)(*((_QWORD *)this + 1) - 24LL));
  ATL::CStringData::Release((ATL::CStringData *)(*(_QWORD *)this - 24LL));
}

```

## disassembly

```asm
0x180011e30  mov     rax, rsp
0x180011e33  push    rbx
0x180011e34  push    rbp
0x180011e35  push    rsi
0x180011e36  push    rdi
0x180011e37  push    r12
0x180011e39  push    r13
0x180011e3b  push    r14
0x180011e3d  push    r15
0x180011e3f  sub     rsp, 0D8h
0x180011e46  movaps  xmmword ptr [rax-58h], xmm6
0x180011e4a  movaps  xmmword ptr [rax-68h], xmm7
0x180011e4e  mov     rsi, rcx
0x180011e51  mov     rbx, [rcx+28h]
0x180011e55  xor     r13d, r13d
0x180011e58  test    rbx, rbx
0x180011e5b  jz      short loc_180011EAF
0x180011e5d  cmp     [rbx+8], r13
0x180011e61  jz      short loc_180011EAF
0x180011e63  mov     rbx, [rbx]
0x180011e66  mov     rbx, [rbx]
0x180011e69  mov     rcx, [rsi+28h]
0x180011e6d  cmp     rbx, [rcx]
0x180011e70  jz      short loc_180011EAA
0x180011e72  movups  xmm6, xmmword ptr [rbx+10h]
0x180011e76  movups  xmm7, xmmword ptr [rbx+20h]
0x180011e7a  movq    rcx, xmm6; pv
0x180011e7f  call    cs:__imp_CoTaskMemFree
0x180011e85  psrldq  xmm6, 8
0x180011e8a  movd    eax, xmm6
0x180011e8e  cmp     eax, 0Ah
0x180011e91  jz      short loc_180011E9D
0x180011e93  cmp     eax, 0Eh
0x180011e96  jnz     short loc_180011E66
0x180011e98  psrldq  xmm7, 8
0x180011e9d  movq    rcx, xmm7; pv
0x180011ea2  call    cs:__imp_CoTaskMemFree
0x180011ea8  jmp     short loc_180011E66
0x180011eaa  call    ?clear@?$list@PEAVProblemNode@@V?$allocator@PEAVProblemNode@@@std@@@std@@QEAAXXZ; std::list<ProblemNode *>::clear(void)
0x180011eaf  mov     rcx, [rsi+28h]
0x180011eb3  test    rcx, rcx
0x180011eb6  jz      short loc_180011EBD
0x180011eb8  call    ??_G?$list@UtagHELPER_ATTRIBUTE@@V?$allocator@UtagHELPER_ATTRIBUTE@@@std@@@std@@QEAAPEAXI@Z; std::list<tagHELPER_ATTRIBUTE>::`scalar deleting destructor'(uint)
0x180011ebd  mov     [rsi+28h], r13
0x180011ec1  mov     r14d, 1
0x180011ec7  cmp     [rsi+130h], r13
0x180011ece  jz      short loc_180011F2A
0x180011ed0  mov     ebp, r13d
0x180011ed3  cmp     [rsi+80h], r13
0x180011eda  jbe     short loc_180011F1D
0x180011edc  mov     edi, ebp
0x180011ede  shl     rdi, 5
0x180011ee2  mov     rbx, [rsi+130h]
0x180011ee9  mov     rcx, [rdi+rbx]; pv
0x180011eed  call    cs:__imp_CoTaskMemFree
0x180011ef3  mov     rcx, [rdi+rbx+8]; pv
0x180011ef8  call    cs:__imp_CoTaskMemFree
0x180011efe  mov     r8d, r14d; int
0x180011f01  mov     edx, [rdi+rbx+10h]; unsigned int
0x180011f05  mov     rcx, [rdi+rbx+18h]; pv
0x180011f0a  call    ?FreeHelperAttributes@@YAXPEAUtagHELPER_ATTRIBUTE@@KH@Z; FreeHelperAttributes(tagHELPER_ATTRIBUTE *,ulong,int)
0x180011f0f  add     ebp, r14d
0x180011f12  mov     eax, ebp
0x180011f14  cmp     rax, [rsi+80h]
0x180011f1b  jb      short loc_180011EDC
0x180011f1d  mov     rcx, [rsi+130h]; pv
0x180011f24  call    cs:__imp_CoTaskMemFree
0x180011f2a  mov     [rsi+130h], r13
0x180011f31  lea     rcx, [rsi+78h]
0x180011f35  call    ?clear@?$list@PEAVProblemNode@@V?$allocator@PEAVProblemNode@@@std@@@std@@QEAAXXZ; std::list<ProblemNode *>::clear(void)
0x180011f3a  cmp     [rsi+138h], r13
0x180011f41  jz      short loc_180011F9D
0x180011f43  mov     ebp, r13d
0x180011f46  cmp     [rsi+90h], r13
0x180011f4d  jbe     short loc_180011F90
0x180011f4f  mov     edi, ebp
0x180011f51  shl     rdi, 5
0x180011f55  mov     rbx, [rsi+138h]
0x180011f5c  mov     rcx, [rdi+rbx]; pv
0x180011f60  call    cs:__imp_CoTaskMemFree
0x180011f66  mov     rcx, [rdi+rbx+8]; pv
0x180011f6b  call    cs:__imp_CoTaskMemFree
0x180011f71  mov     r8d, r14d; int
0x180011f74  mov     edx, [rdi+rbx+10h]; unsigned int
0x180011f78  mov     rcx, [rdi+rbx+18h]; pv
0x180011f7d  call    ?FreeHelperAttributes@@YAXPEAUtagHELPER_ATTRIBUTE@@KH@Z; FreeHelperAttributes(tagHELPER_ATTRIBUTE *,ulong,int)
0x180011f82  add     ebp, r14d
0x180011f85  mov     eax, ebp
0x180011f87  cmp     rax, [rsi+90h]
0x180011f8e  jb      short loc_180011F4F
0x180011f90  mov     rcx, [rsi+138h]; pv
0x180011f97  call    cs:__imp_CoTaskMemFree
0x180011f9d  mov     [rsi+138h], r13
0x180011fa4  lea     r15, [rsi+88h]
0x180011fab  mov     rcx, r15
0x180011fae  call    ?clear@?$list@PEAVProblemNode@@V?$allocator@PEAVProblemNode@@@std@@@std@@QEAAXXZ; std::list<ProblemNode *>::clear(void)
0x180011fb3  cmp     [rsi+140h], r13
0x180011fba  jz      short loc_180012016
0x180011fbc  mov     ebp, r13d
0x180011fbf  cmp     [rsi+0A0h], r13
0x180011fc6  jbe     short loc_180012009
0x180011fc8  mov     edi, ebp
0x180011fca  shl     rdi, 5
0x180011fce  mov     rbx, [rsi+140h]
0x180011fd5  mov     rcx, [rdi+rbx]; pv
0x180011fd9  call    cs:__imp_CoTaskMemFree
0x180011fdf  mov     rcx, [rdi+rbx+8]; pv
0x180011fe4  call    cs:__imp_CoTaskMemFree
0x180011fea  mov     r8d, r14d; int
0x180011fed  mov     edx, [rdi+rbx+10h]; unsigned int
0x180011ff1  mov     rcx, [rdi+rbx+18h]; pv
0x180011ff6  call    ?FreeHelperAttributes@@YAXPEAUtagHELPER_ATTRIBUTE@@KH@Z; FreeHelperAttributes(tagHELPER_ATTRIBUTE *,ulong,int)
0x180011ffb  add     ebp, r14d
0x180011ffe  mov     eax, ebp
0x180012000  cmp     rax, [rsi+0A0h]
0x180012007  jb      short loc_180011FC8
0x180012009  mov     rcx, [rsi+140h]; pv
0x180012010  call    cs:__imp_CoTaskMemFree
0x180012016  mov     [rsi+140h], r13
0x18001201d  lea     r14, [rsi+98h]
0x180012024  mov     rcx, r14
0x180012027  call    ?clear@?$list@PEAVProblemNode@@V?$allocator@PEAVProblemNode@@@std@@@std@@QEAAXXZ; std::list<ProblemNode *>::clear(void)
0x18001202c  cmp     [rsi+148h], r13
0x180012033  jz      short loc_180012091
0x180012035  mov     ebp, r13d
0x180012038  cmp     [rsi+0B0h], r13
0x18001203f  jbe     short loc_180012084
0x180012041  mov     edi, ebp
0x180012043  shl     rdi, 5
0x180012047  mov     rbx, [rsi+148h]
0x18001204e  mov     rcx, [rdi+rbx]; pv
0x180012052  call    cs:__imp_CoTaskMemFree
0x180012058  mov     rcx, [rdi+rbx+8]; pv
0x18001205d  call    cs:__imp_CoTaskMemFree
0x180012063  mov     r8d, 1; int
0x180012069  mov     edx, [rdi+rbx+10h]; unsigned int
0x18001206d  mov     rcx, [rdi+rbx+18h]; pv
0x180012072  call    ?FreeHelperAttributes@@YAXPEAUtagHELPER_ATTRIBUTE@@KH@Z; FreeHelperAttributes(tagHELPER_ATTRIBUTE *,ulong,int)
0x180012077  inc     ebp
0x180012079  mov     eax, ebp
0x18001207b  cmp     rax, [rsi+0B0h]
0x180012082  jb      short loc_180012041
0x180012084  mov     rcx, [rsi+148h]; pv
0x18001208b  call    cs:__imp_CoTaskMemFree
0x180012091  mov     [rsi+148h], r13
0x180012098  lea     rbx, [rsi+0A8h]
0x18001209f  mov     rcx, rbx
0x1800120a2  call    ?clear@?$list@PEAVProblemNode@@V?$allocator@PEAVProblemNode@@@std@@@std@@QEAAXXZ; std::list<ProblemNode *>::clear(void)
0x1800120a7  mov     r8d, 1; int
0x1800120ad  mov     edx, [rsi+68h]; unsigned int
0x1800120b0  mov     rcx, [rsi+70h]; pv
0x1800120b4  call    ?FreeRepairInfos@@YAXPEAUtagRepairInfo@@KH@Z; FreeRepairInfos(tagRepairInfo *,ulong,int)
0x1800120b9  mov     [rsi+70h], r13
0x1800120bd  mov     [rsi+68h], r13d
0x1800120c1  mov     rcx, [rsi+48h]
0x1800120c5  test    rcx, rcx
0x1800120c8  jz      short loc_1800120EB
0x1800120ca  mov     rax, [rcx]
0x1800120cd  mov     rax, [rax+88h]
0x1800120d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120d9  mov     rcx, [rsi+48h]; this
0x1800120dd  test    rcx, rcx
0x1800120e0  jz      short loc_1800120E7
0x1800120e2  call    ??_GProtectedNetDiagHelper@@QEAAPEAXI@Z; ProtectedNetDiagHelper::`scalar deleting destructor'(uint)
0x1800120e7  mov     [rsi+48h], r13
0x1800120eb  mov     rcx, rbx
0x1800120ee  call    ??1?$list@PEAVProblemNode@@V?$allocator@PEAVProblemNode@@@std@@@std@@QEAA@XZ; std::list<ProblemNode *>::~list<ProblemNode *>(void)
0x1800120f3  mov     rcx, r14
0x1800120f6  call    ??1?$list@PEAVProblemNode@@V?$allocator@PEAVProblemNode@@@std@@@std@@QEAA@XZ; std::list<ProblemNode *>::~list<ProblemNode *>(void)
0x1800120fb  mov     rcx, r15
0x1800120fe  call    ??1?$list@PEAVProblemNode@@V?$allocator@PEAVProblemNode@@@std@@@std@@QEAA@XZ; std::list<ProblemNode *>::~list<ProblemNode *>(void)
0x180012103  lea     rcx, [rsi+78h]
0x180012107  call    ??1?$list@PEAVProblemNode@@V?$allocator@PEAVProblemNode@@@std@@@std@@QEAA@XZ; std::list<ProblemNode *>::~list<ProblemNode *>(void)
0x18001210c  mov     rcx, [rsi+58h]
0x180012110  sub     rcx, 18h; this
0x180012114  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180012119  mov     rcx, [rsi+50h]
0x18001211d  sub     rcx, 18h; this
0x180012121  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180012126  mov     rcx, [rsi+18h]
0x18001212a  sub     rcx, 18h; this
0x18001212e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180012133  mov     rcx, [rsi+10h]
0x180012137  sub     rcx, 18h; this
0x18001213b  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180012140  mov     rcx, [rsi+8]
0x180012144  sub     rcx, 18h; this
0x180012148  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001214d  mov     rcx, [rsi]
0x180012150  sub     rcx, 18h; this
0x180012154  lea     r11, [rsp+118h+var_40]
0x18001215c  movaps  xmm6, xmmword ptr [r11-18h]
0x180012161  movaps  xmm7, xmmword ptr [r11-28h]
0x180012166  mov     rsp, r11
0x180012169  pop     r15
0x18001216b  pop     r14
0x18001216d  pop     r13
0x18001216f  pop     r12
0x180012171  pop     rdi
0x180012172  pop     rsi
0x180012173  pop     rbp
0x180012174  pop     rbx
0x180012175  jmp     ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
```
