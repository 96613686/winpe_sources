# CInteractionContextWrapper::_UpdateInteractionOutput(INTERACTION_CONTEXT_OUTPUT const *,InteractionOutput *)

- ea: `0x1801fd17c`
- end: `0x1801fd555`
- name: `?_UpdateInteractionOutput@CInteractionContextWrapper@@AEAAXPEBUINTERACTION_CONTEXT_OUTPUT@@PEAUInteractionOutput@@@Z`
- size: `985`
- prototype: `void(CInteractionContextWrapper *__hidden this, const struct INTERACTION_CONTEXT_OUTPUT *, struct InteractionOutput *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1801e5ffc`
- `0x18027ace0`

## callees

- `0x1800dced4`
- `0x18018fba8`
- `0x1801bcadc`
- `0x1801f2b50`
- `0x1801fd17c`
- `0x1802284b0`

## import_xrefs

- `win32u!NtDCompositionGetFrameStatistics` at `0x1801fd312`
- `win32u!NtDCompositionGetFrameStatistics` at `0x1801fd312`
- `NInput!__imp_OutputPredictionInteractionContext` at `0x1801fd37f`
- `NInput!__imp_OutputPredictionInteractionContext` at `0x1801fd37f`

## pseudocode

```c
void __fastcall CInteractionContextWrapper::_UpdateInteractionOutput(
        CInteractionContextWrapper *this,
        const struct INTERACTION_CONTEXT_OUTPUT *a2,
        struct InteractionOutput *a3)
{
  int v6; // ecx
  float v7; // xmm0_4
  float v8; // xmm6_4
  float v9; // xmm7_4
  const struct DEVICE_INFO *v10; // rax
  const struct tagRECT *v11; // r15
  const struct MANIPULATION_TRANSFORM *v12; // r14
  __int64 v13; // r8
  __int64 v14; // r9
  int v15; // eax
  const struct MANIPULATION_TRANSFORM *v16; // rcx
  int v17; // r8d
  int v18; // r9d
  int v19; // ecx
  float v20; // [rsp+B8h] [rbp-80h] BYREF
  float v21; // [rsp+BCh] [rbp-7Ch] BYREF
  int v22; // [rsp+C0h] [rbp-78h] BYREF
  int v23; // [rsp+C4h] [rbp-74h] BYREF
  int v24; // [rsp+C8h] [rbp-70h] BYREF
  int v25; // [rsp+CCh] [rbp-6Ch] BYREF
  int v26; // [rsp+D0h] [rbp-68h] BYREF
  float v27; // [rsp+D4h] [rbp-64h] BYREF
  float v28; // [rsp+D8h] [rbp-60h] BYREF
  int v29; // [rsp+DCh] [rbp-5Ch] BYREF
  int v30; // [rsp+E0h] [rbp-58h] BYREF
  int v31; // [rsp+E4h] [rbp-54h] BYREF
  int v32; // [rsp+E8h] [rbp-50h] BYREF
  int v33; // [rsp+ECh] [rbp-4Ch] BYREF
  int v34; // [rsp+F0h] [rbp-48h] BYREF
  int v35; // [rsp+F4h] [rbp-44h] BYREF
  CInteractionContextWrapper *v36; // [rsp+F8h] [rbp-40h] BYREF
  __int128 v37; // [rsp+100h] [rbp-38h] BYREF
  int v38; // [rsp+110h] [rbp-28h]
  __int128 v39; // [rsp+118h] [rbp-20h] BYREF
  __int128 v40; // [rsp+128h] [rbp-10h]
  __int64 v41; // [rsp+138h] [rbp+0h]

  *((_DWORD *)a3 + 10) = *((_DWORD *)a2 + 3);
  *((_DWORD *)a3 + 11) = *((_DWORD *)a2 + 4);
  v6 = *(_DWORD *)a2;
  if ( ((*(_DWORD *)a2 - 1) & 0xFFFFFFFC) == 0 && v6 != 3 )
  {
    *(_DWORD *)a3 = v6;
    *((_DWORD *)a3 + 1) = *((_DWORD *)a2 + 1);
    if ( *(_DWORD *)a2 == 1 )
    {
      if ( *((_DWORD *)a2 + 19) == 2 )
      {
        if ( *((float *)a2 + 10) == 0.0 )
        {
          if ( *((float *)a2 + 11) != 0.0 )
            *((_DWORD *)a3 + 5) = 2;
        }
        else
        {
          *((_DWORD *)a3 + 5) = 1;
        }
      }
      else if ( *((_DWORD *)a2 + 19) == 1 )
      {
        *((_DWORD *)a3 + 5) = 0;
      }
      *((float *)a3 + 2) = *((float *)a2 + 5) + *((float *)a3 + 2);
      *((float *)a3 + 3) = *((float *)a2 + 6) + *((float *)a3 + 3);
      v7 = *((float *)a2 + 7);
      if ( v7 != 0.0 )
        *((float *)a3 + 4) = v7 * *((float *)a3 + 4);
      *((_DWORD *)a3 + 6) = *((_DWORD *)a2 + 15);
      *((_DWORD *)a3 + 7) = *((_DWORD *)a2 + 16);
      *((_DWORD *)a3 + 8) = *((_DWORD *)a2 + 17);
      *((_DWORD *)a3 + 9) = 0;
      *((_DWORD *)a3 + 12) = *((_DWORD *)a2 + 12);
      *((_DWORD *)a3 + 13) = *((_DWORD *)a2 + 13);
    }
  }
  v8 = *((float *)a3 + 2);
  v9 = *((float *)a3 + 3);
  v20 = v8;
  v21 = v9;
  v37 = 0;
  v38 = 0;
  if ( !CCommonRegistryData::m_fDisableInteractionOutputPrediction
    && !CCommonRegistryData::m_cForceDisableInteractionOutputPrediction
    && (*((_DWORD *)this + 58) & 0x180000) == 0 )
  {
    v10 = CPointerDeviceCache::Query(*((void **)this + 30));
    v11 = (const struct tagRECT *)(((unsigned __int64)v10 + 16) & -(__int64)(*((_BYTE *)v10 + 48) != 0));
    v41 = 0;
    v39 = 0;
    v40 = 0;
    if ( (int)NtDCompositionGetFrameStatistics(&v39, 0) >= 0 )
    {
      v12 = 0;
      if ( *(_DWORD *)a2 == 1 )
      {
        v13 = 1000 * (__int64)v40 / *((_QWORD *)&v40 + 1);
        v14 = 1000 * (__int64)v39 / *((_QWORD *)&v40 + 1);
        if ( v13 || v14 || 1000 * v41 / *((_QWORD *)&v40 + 1) )
        {
          v15 = OutputPredictionInteractionContext(
                  *((_QWORD *)this + 2),
                  1000,
                  v13,
                  v14,
                  1000 * v41 / *((_QWORD *)&v40 + 1),
                  &v37);
          v16 = (const struct MANIPULATION_TRANSFORM *)&v37;
          if ( v15 < 0 )
            v16 = 0;
          v12 = v16;
        }
      }
      CInteractionContextTransformHelper::CalculatePrediction(
        (CInteractionContextWrapper *)((char *)this + 328),
        a2,
        v12,
        v11,
        *((_DWORD *)this + 79),
        *((float *)a3 + 2),
        *((float *)a3 + 3),
        &v20,
        &v21);
      v8 = v20;
      v9 = v21;
    }
  }
  if ( (unsigned int)dword_1803B9858 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1803B9858, 2) )
  {
    v19 = *((_DWORD *)a3 + 4);
    v21 = *((float *)a3 + 11);
    v20 = *((float *)a3 + 10);
    v22 = *((_DWORD *)a3 + 9);
    v23 = *((_DWORD *)a3 + 8);
    v24 = *((_DWORD *)a3 + 7);
    v25 = *((_DWORD *)a3 + 6);
    v29 = DWORD1(v37);
    v30 = v37;
    v31 = *((_DWORD *)a2 + 11);
    v32 = *((_DWORD *)a2 + 10);
    v34 = *((_DWORD *)a3 + 3);
    v35 = *((_DWORD *)a3 + 2);
    v27 = v9;
    v28 = v8;
    v26 = v19;
    v33 = v19;
    v36 = this;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v19,
      (unsigned int)byte_1803966FB,
      v17,
      v18,
      (__int64)&v36,
      (__int64)&v35,
      (__int64)&v34,
      (__int64)&v33,
      (__int64)&v32,
      (__int64)&v31,
      (__int64)&v30,
      (__int64)&v29,
      (__int64)&v28,
      (__int64)&v27,
      (__int64)&v26,
      (__int64)&v25,
      (__int64)&v24,
      (__int64)&v23,
      (__int64)&v22,
      (__int64)&v20,
      (__int64)&v21);
  }
  *((float *)a3 + 2) = v8;
  *((float *)a3 + 3) = v9;
}

```

## disassembly

```asm
0x1801fd17c  mov     rax, rsp
0x1801fd17f  mov     [rax+20h], rbx
0x1801fd183  push    rbp
0x1801fd184  push    rsi
0x1801fd185  push    rdi
0x1801fd186  push    r14
0x1801fd188  push    r15
0x1801fd18a  lea     rbp, [rax-58h]
0x1801fd18e  sub     rsp, 160h
0x1801fd195  movaps  xmmword ptr [rax-38h], xmm6
0x1801fd199  movaps  xmmword ptr [rax-48h], xmm7
0x1801fd19d  mov     rax, cs:__security_cookie
0x1801fd1a4  xor     rax, rsp
0x1801fd1a7  mov     [rbp+50h+var_48], rax
0x1801fd1ab  mov     eax, [rdx+0Ch]
0x1801fd1ae  mov     rsi, rcx
0x1801fd1b1  mov     [r8+28h], eax
0x1801fd1b5  mov     rbx, r8
0x1801fd1b8  mov     eax, [rdx+10h]
0x1801fd1bb  mov     rdi, rdx
0x1801fd1be  mov     [r8+2Ch], eax
0x1801fd1c2  mov     ecx, [rdx]
0x1801fd1c4  lea     eax, [rcx-1]
0x1801fd1c7  test    eax, 0FFFFFFFCh
0x1801fd1cc  jnz     loc_1801FD296
0x1801fd1d2  cmp     ecx, 3
0x1801fd1d5  jz      loc_1801FD296
0x1801fd1db  mov     [r8], ecx
0x1801fd1de  mov     eax, [rdx+4]
0x1801fd1e1  mov     [r8+4], eax
0x1801fd1e5  cmp     dword ptr [rdx], 1
0x1801fd1e8  jnz     loc_1801FD296
0x1801fd1ee  cmp     dword ptr [rdx+4Ch], 2
0x1801fd1f2  xorps   xmm2, xmm2
0x1801fd1f5  jnz     short loc_1801FD223
0x1801fd1f7  movss   xmm0, dword ptr [rdx+28h]
0x1801fd1fc  ucomiss xmm0, xmm2
0x1801fd1ff  jp      short loc_1801FD219
0x1801fd201  jnz     short loc_1801FD219
0x1801fd203  movss   xmm0, dword ptr [rdx+2Ch]
0x1801fd208  ucomiss xmm0, xmm2
0x1801fd20b  jp      short loc_1801FD20F
0x1801fd20d  jz      short loc_1801FD231
0x1801fd20f  mov     dword ptr [r8+14h], 2
0x1801fd217  jmp     short loc_1801FD231
0x1801fd219  mov     dword ptr [r8+14h], 1
0x1801fd221  jmp     short loc_1801FD231
0x1801fd223  cmp     dword ptr [rdx+4Ch], 1
0x1801fd227  jnz     short loc_1801FD231
0x1801fd229  mov     dword ptr [r8+14h], 0
0x1801fd231  movss   xmm0, dword ptr [rdx+14h]
0x1801fd236  addss   xmm0, dword ptr [r8+8]
0x1801fd23c  movss   dword ptr [r8+8], xmm0
0x1801fd242  movss   xmm1, dword ptr [rdx+18h]
0x1801fd247  addss   xmm1, dword ptr [r8+0Ch]
0x1801fd24d  movss   dword ptr [r8+0Ch], xmm1
0x1801fd253  movss   xmm0, dword ptr [rdx+1Ch]
0x1801fd258  ucomiss xmm0, xmm2
0x1801fd25b  jp      short loc_1801FD25F
0x1801fd25d  jz      short loc_1801FD26B
0x1801fd25f  mulss   xmm0, dword ptr [r8+10h]
0x1801fd265  movss   dword ptr [r8+10h], xmm0
0x1801fd26b  mov     eax, [rdx+3Ch]
0x1801fd26e  mov     [r8+18h], eax
0x1801fd272  mov     eax, [rdx+40h]
0x1801fd275  mov     [r8+1Ch], eax
0x1801fd279  mov     eax, [rdx+44h]
0x1801fd27c  mov     [r8+20h], eax
0x1801fd280  mov     dword ptr [r8+24h], 0
0x1801fd288  mov     eax, [rdx+30h]
0x1801fd28b  mov     [r8+30h], eax
0x1801fd28f  mov     eax, [rdx+34h]
0x1801fd292  mov     [r8+34h], eax
0x1801fd296  movss   xmm6, dword ptr [r8+8]
0x1801fd29c  xor     eax, eax
0x1801fd29e  cmp     cs:?m_fDisableInteractionOutputPrediction@CCommonRegistryData@@0HA, eax; int CCommonRegistryData::m_fDisableInteractionOutputPrediction
0x1801fd2a4  xorps   xmm0, xmm0
0x1801fd2a7  movss   xmm7, dword ptr [r8+0Ch]
0x1801fd2ad  movss   [rbp+50h+var_D0], xmm6
0x1801fd2b2  movss   [rbp+50h+var_CC], xmm7
0x1801fd2b7  movups  [rbp+50h+var_88], xmm0
0x1801fd2bb  mov     [rbp+50h+var_78], eax
0x1801fd2be  jnz     loc_1801FD3E3
0x1801fd2c4  cmp     cs:?m_cForceDisableInteractionOutputPrediction@CCommonRegistryData@@0IA, eax; uint CCommonRegistryData::m_cForceDisableInteractionOutputPrediction
0x1801fd2ca  ja      loc_1801FD3E3
0x1801fd2d0  test    dword ptr [rsi+0E8h], 180000h
0x1801fd2da  jnz     loc_1801FD3E3
0x1801fd2e0  mov     rcx, [rsi+0F0h]; void *
0x1801fd2e7  call    ?Query@CPointerDeviceCache@@SAAEBUDEVICE_INFO@@PEAX@Z; CPointerDeviceCache::Query(void *)
0x1801fd2ec  xorps   xmm0, xmm0
0x1801fd2ef  mov     cl, [rax+30h]
0x1801fd2f2  add     rax, 10h
0x1801fd2f6  neg     cl
0x1801fd2f8  lea     rcx, [rbp+50h+var_70]
0x1801fd2fc  sbb     r15, r15
0x1801fd2ff  xor     edx, edx
0x1801fd301  and     r15, rax
0x1801fd304  xor     eax, eax
0x1801fd306  mov     [rbp+50h+var_50], rax
0x1801fd30a  movups  [rbp+50h+var_70], xmm0
0x1801fd30e  movups  [rbp+50h+var_60], xmm0
0x1801fd312  call    cs:__imp_NtDCompositionGetFrameStatistics
0x1801fd318  test    eax, eax
0x1801fd31a  js      loc_1801FD3E3
0x1801fd320  xor     r14d, r14d
0x1801fd323  cmp     dword ptr [rdi], 1
0x1801fd326  jnz     short loc_1801FD392
0x1801fd328  mov     rcx, qword ptr [rbp+50h+var_60+8]
0x1801fd32c  imul    rax, qword ptr [rbp+50h+var_60], 3E8h
0x1801fd334  cqo
0x1801fd336  idiv    rcx
0x1801fd339  mov     r8, rax
0x1801fd33c  imul    rax, qword ptr [rbp+50h+var_70], 3E8h
0x1801fd344  cqo
0x1801fd346  idiv    rcx
0x1801fd349  mov     r9, rax
0x1801fd34c  imul    rax, [rbp+50h+var_50], 3E8h
0x1801fd354  cqo
0x1801fd356  idiv    rcx
0x1801fd359  test    r8, r8
0x1801fd35c  jnz     short loc_1801FD368
0x1801fd35e  test    r9, r9
0x1801fd361  jnz     short loc_1801FD368
0x1801fd363  test    rax, rax
0x1801fd366  jz      short loc_1801FD392
0x1801fd368  lea     rcx, [rbp+50h+var_88]
0x1801fd36c  mov     edx, 3E8h
0x1801fd371  mov     qword ptr [rsp+180h+var_158], rcx
0x1801fd376  mov     rcx, [rsi+10h]
0x1801fd37a  mov     qword ptr [rsp+180h+var_160], rax
0x1801fd37f  call    cs:__imp_OutputPredictionInteractionContext
0x1801fd385  test    eax, eax
0x1801fd387  lea     rcx, [rbp+50h+var_88]
0x1801fd38b  cmovs   rcx, r14
0x1801fd38f  mov     r14, rcx
0x1801fd392  movss   xmm0, dword ptr [rbx+0Ch]
0x1801fd397  lea     rax, [rbp+50h+var_CC]
0x1801fd39b  movss   xmm1, dword ptr [rbx+8]
0x1801fd3a0  lea     rcx, [rsi+148h]; this
0x1801fd3a7  mov     [rsp+180h+var_140], rax; float *
0x1801fd3ac  mov     r9, r15; struct tagRECT *
0x1801fd3af  lea     rax, [rbp+50h+var_D0]
0x1801fd3b3  mov     r8, r14; struct MANIPULATION_TRANSFORM *
0x1801fd3b6  mov     [rsp+180h+var_148], rax; float *
0x1801fd3bb  mov     rdx, rdi; struct INTERACTION_CONTEXT_OUTPUT *
0x1801fd3be  mov     eax, [rsi+13Ch]
0x1801fd3c4  movss   [rsp+180h+var_150], xmm0; float
0x1801fd3ca  movss   [rsp+180h+var_158], xmm1; float
0x1801fd3d0  mov     [rsp+180h+var_160], eax; unsigned int
0x1801fd3d4  call    ?CalculatePrediction@CInteractionContextTransformHelper@@QEAAXAEBUINTERACTION_CONTEXT_OUTPUT@@PEBUMANIPULATION_TRANSFORM@@PEBUtagRECT@@IMMPEAM3@Z; CInteractionContextTransformHelper::CalculatePrediction(INTERACTION_CONTEXT_OUTPUT const &,MANIPULATION_TRANSFORM const *,tagRECT const *,uint,float,float,float *,float *)
0x1801fd3d9  movss   xmm6, [rbp+50h+var_D0]
0x1801fd3de  movss   xmm7, [rbp+50h+var_CC]
0x1801fd3e3  mov     eax, cs:dword_1803B9858
0x1801fd3e9  cmp     eax, 4
0x1801fd3ec  jbe     loc_1801FD51E
0x1801fd3f2  mov     edx, 2
0x1801fd3f7  lea     rcx, dword_1803B9858
0x1801fd3fe  call    _tlgKeywordOn
0x1801fd403  test    al, al
0x1801fd405  jz      loc_1801FD51E
0x1801fd40b  mov     eax, [rbx+2Ch]
0x1801fd40e  lea     rdx, byte_1803966FB
0x1801fd415  mov     ecx, [rbx+10h]
0x1801fd418  mov     [rbp+50h+var_CC], eax
0x1801fd41b  mov     eax, [rbx+28h]
0x1801fd41e  mov     [rbp+50h+var_D0], eax
0x1801fd421  mov     eax, [rbx+24h]
0x1801fd424  mov     [rbp+50h+var_C8], eax
0x1801fd427  mov     eax, [rbx+20h]
0x1801fd42a  mov     [rbp+50h+var_C4], eax
0x1801fd42d  mov     eax, [rbx+1Ch]
0x1801fd430  mov     [rbp+50h+var_C0], eax
0x1801fd433  mov     eax, [rbx+18h]
0x1801fd436  mov     [rbp+50h+var_BC], eax
0x1801fd439  mov     eax, dword ptr [rbp+50h+var_88+4]
0x1801fd43c  mov     [rbp+50h+var_AC], eax
0x1801fd43f  mov     eax, dword ptr [rbp+50h+var_88]
0x1801fd442  mov     [rbp+50h+var_A8], eax
0x1801fd445  mov     eax, [rdi+2Ch]
0x1801fd448  mov     [rbp+50h+var_A4], eax
0x1801fd44b  mov     eax, [rdi+28h]
0x1801fd44e  mov     [rbp+50h+var_A0], eax
0x1801fd451  mov     eax, [rbx+0Ch]
0x1801fd454  mov     [rbp+50h+var_98], eax
0x1801fd457  mov     eax, [rbx+8]
0x1801fd45a  mov     [rbp+50h+var_94], eax
0x1801fd45d  lea     rax, [rbp+50h+var_CC]
0x1801fd461  mov     [rsp+180h+var_E0], rax
0x1801fd469  lea     rax, [rbp+50h+var_D0]
0x1801fd46d  mov     [rsp+180h+var_E8], rax
0x1801fd475  lea     rax, [rbp+50h+var_C8]
0x1801fd479  mov     [rsp+180h+var_F0], rax
0x1801fd481  lea     rax, [rbp+50h+var_C4]
0x1801fd485  mov     [rsp+180h+var_F8], rax
0x1801fd48d  lea     rax, [rbp+50h+var_C0]
0x1801fd491  mov     [rsp+180h+var_100], rax
0x1801fd499  lea     rax, [rbp+50h+var_BC]
0x1801fd49d  mov     [rsp+180h+var_108], rax
0x1801fd4a2  lea     rax, [rbp+50h+var_B8]
0x1801fd4a6  mov     [rsp+180h+var_110], rax
0x1801fd4ab  lea     rax, [rbp+50h+var_B4]
0x1801fd4af  mov     [rsp+180h+var_118], rax
0x1801fd4b4  lea     rax, [rbp+50h+var_B0]
0x1801fd4b8  mov     [rsp+180h+var_120], rax
0x1801fd4bd  lea     rax, [rbp+50h+var_AC]
0x1801fd4c1  mov     [rsp+180h+var_128], rax
0x1801fd4c6  lea     rax, [rbp+50h+var_A8]
0x1801fd4ca  mov     [rsp+180h+var_130], rax
0x1801fd4cf  lea     rax, [rbp+50h+var_A4]
0x1801fd4d3  mov     [rsp+180h+var_138], rax
0x1801fd4d8  lea     rax, [rbp+50h+var_A0]
0x1801fd4dc  mov     [rsp+180h+var_140], rax
0x1801fd4e1  lea     rax, [rbp+50h+var_9C]
0x1801fd4e5  mov     [rsp+180h+var_148], rax
0x1801fd4ea  lea     rax, [rbp+50h+var_98]
0x1801fd4ee  mov     qword ptr [rsp+180h+var_150], rax
0x1801fd4f3  lea     rax, [rbp+50h+var_94]
0x1801fd4f7  mov     qword ptr [rsp+180h+var_158], rax
0x1801fd4fc  lea     rax, [rbp+50h+var_90]
0x1801fd500  mov     qword ptr [rsp+180h+var_160], rax
0x1801fd505  movss   [rbp+50h+var_B4], xmm7
0x1801fd50a  movss   [rbp+50h+var_B0], xmm6
0x1801fd50f  mov     [rbp+50h+var_B8], ecx
0x1801fd512  mov     [rbp+50h+var_9C], ecx
0x1801fd515  mov     [rbp+50h+var_90], rsi
0x1801fd519  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@U2@U2@U2@U2@U2@U2@U2@U2@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@444444444444444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1801fd51e  movss   dword ptr [rbx+8], xmm6
0x1801fd523  movss   dword ptr [rbx+0Ch], xmm7
0x1801fd528  mov     rcx, [rbp+50h+var_48]
0x1801fd52c  xor     rcx, rsp; StackCookie
0x1801fd52f  call    __security_check_cookie
0x1801fd534  lea     r11, [rsp+180h+var_20]
0x1801fd53c  mov     rbx, [r11+48h]
0x1801fd540  movaps  xmm6, xmmword ptr [r11-10h]
0x1801fd545  movaps  xmm7, xmmword ptr [r11-20h]
0x1801fd54a  mov     rsp, r11
0x1801fd54d  pop     r15
0x1801fd54f  pop     r14
0x1801fd551  pop     rdi
0x1801fd552  pop     rsi
0x1801fd553  pop     rbp
0x1801fd554  retn
```
