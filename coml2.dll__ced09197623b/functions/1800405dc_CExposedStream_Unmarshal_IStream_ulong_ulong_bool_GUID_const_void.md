# CExposedStream::Unmarshal(IStream *,ulong,ulong,bool,_GUID const &,void * *)

- ea: `0x1800405dc`
- end: `0x180040c8e`
- name: `?Unmarshal@CExposedStream@@SAJPEAUIStream@@KK_NAEBU_GUID@@PEAPEAX@Z`
- size: `1714`
- prototype: `__int64 __usercall@<rax>(LPSTREAM pStm@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, bool@<r9b>, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003eee0`

## callees

- `0x180018680`
- `0x180018770`
- `0x180019e20`
- `0x18001b840`
- `0x18001b89c`
- `0x18001c268`
- `0x18001d820`
- `0x18001e0f8`
- `0x18001e17c`
- `0x18001efe8`
- `0x18001fbb4`
- `0x1800209c0`
- `0x18002db70`
- `0x18002dbd0`
- `0x1800405dc`
- `0x180042800`
- `0x18004a6b8`
- `0x18004a7b4`
- `0x18004a830`
- `0x18004ba24`
- `0x18004ca84`
- `0x18004cdec`
- `0x18004d1d0`
- `0x18004d230`
- `0x180061410`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004096e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004096e`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x180040673`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x180040673`

## pseudocode

```c
__int64 __fastcall CExposedStream::Unmarshal(
        LPSTREAM pStm,
        int a2,
        int a3,
        char a4,
        const struct _GUID *Buf1,
        void **a6)
{
  __int64 v10; // rax
  __int64 (__fastcall *v11)(LPSTREAM, __int64, __int64, _QWORD); // rax
  int v12; // edi
  __int64 v13; // rdx
  void *v14; // r12
  struct CSmAllocator *TlsSmAllocator; // rax
  struct CPerContext **v16; // rdx
  const void *v17; // rcx
  struct CSmAllocator *v18; // rax
  const void *v19; // rcx
  struct CGlobalContext *v20; // rdx
  __int64 v21; // r8
  struct _TEB *v22; // rax
  struct CPerContext *v23; // rsi
  void *v24; // r14
  unsigned __int64 v25; // rcx
  __int64 v26; // rbx
  __int64 v27; // rbx
  struct CSmAllocator *v28; // rax
  struct IMalloc *v29; // rdx
  __int64 v30; // rcx
  DWORD CurrentProcessId; // eax
  struct CMarshalList *Marshal; // rax
  CExposedStream *v33; // rbx
  _QWORD *v34; // rcx
  CExposedStream *v35; // rax
  struct CSeekPointer *v36; // r9
  struct CDFBasis *v37; // r8
  struct CPubStream *v38; // rdx
  unsigned int v39; // edx
  CMarshalList *v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // rcx
  struct CPerContext **v43; // rdx
  CSmAllocator *v44; // rax
  CSmAllocator *v45; // rax
  CSmAllocator *v46; // rax
  CSmAllocator *v47; // rax
  int v49; // [rsp+30h] [rbp-D0h] BYREF
  struct CPerContext *v50; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v52; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v53[144]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v54; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v55; // [rsp+F8h] [rbp-8h]
  __int64 v56; // [rsp+100h] [rbp+0h]
  __int64 v57; // [rsp+108h] [rbp+8h] BYREF
  __int64 v58; // [rsp+110h] [rbp+10h] BYREF
  __int64 v59; // [rsp+118h] [rbp+18h] BYREF
  __int128 v60; // [rsp+120h] [rbp+20h]
  __int64 v61; // [rsp+130h] [rbp+30h]

  v50 = 0;
  ppv = 0;
  v49 = 0;
  v54 = 0;
  v52 = 0;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  v58 = 0;
  v59 = 0;
  v60 = 0;
  v61 = 0;
  CPerContext::CPerContext((CPerContext *)v53, 0);
  CoUnmarshalInterface(pStm, &IID_IStream, &ppv);
  v10 = *(_QWORD *)pStm;
  if ( a2 >= 0 )
  {
    v11 = *(__int64 (__fastcall **)(LPSTREAM, __int64, __int64, _QWORD))(v10 + 40);
    v50 = (struct CPerContext *)68;
    v12 = v11(pStm, 68, 1, 0);
    if ( v12 < 0 )
      goto LABEL_85;
    goto LABEL_3;
  }
  v12 = (*(__int64 (__fastcall **)(LPSTREAM, __int64 *, __int64, int *))(v10 + 24))(pStm, &v54, 112, &v49);
  if ( v12 < 0 )
    goto LABEL_85;
  if ( v49 != 112 )
  {
    v12 = -2147287010;
    goto LABEL_85;
  }
  if ( a4 )
  {
LABEL_3:
    v12 = -2147287039;
    goto LABEL_85;
  }
  v12 = UnmarshalSharedMemory((const struct SDfMarshalPacket *)&v54, v13, a3, (struct CPerContext *)v53);
  if ( v12 < 0 )
  {
LABEL_85:
    if ( ppv )
    {
      *a6 = ppv;
      v12 = 0;
    }
    goto LABEL_87;
  }
  v14 = *(void **)NtCurrentTeb()->ReservedForOle;
  TlsSmAllocator = GetTlsSmAllocator();
  if ( !(*(unsigned __int8 (__fastcall **)(struct CSmAllocator *, __int64, __int64))(*(_QWORD *)TlsSmAllocator + 72LL))(
          TlsSmAllocator,
          v55,
          168)
    || (!v55 ? (v17 = 0) : (v17 = (const void *)(*(_QWORD *)NtCurrentTeb()->ReservedForOle + v55)),
        memcmp_0(v17, &GUID_ab8fc07c_9ca5_4cb4_80f9_f0811ff49894, 0x10u)
     || !(unsigned __int8)BasedPtr<CGlobalContext>::VerifyOnUnmarshal<CGlobalContext>(&v59)
     || !(unsigned __int8)BasedPtr<CDFBasis>::VerifyOnUnmarshal<CDFBasis>(&v58)
     || (v18 = GetTlsSmAllocator(),
         !(*(unsigned __int8 (__fastcall **)(struct CSmAllocator *, __int64, __int64))(*(_QWORD *)v18 + 72LL))(
            v18,
            v56,
            32))
     || (!v56 ? (v19 = 0) : (v19 = (const void *)(*(_QWORD *)NtCurrentTeb()->ReservedForOle + v56)),
         memcmp_0(v19, &GUID_56401fd1_cf16_4404_9dd0_d642080d23eb, 0x10u))) )
  {
    v12 = -2147024891;
    goto LABEL_84;
  }
  if ( v59 )
    v20 = (struct CGlobalContext *)(v59 + *(_QWORD *)NtCurrentTeb()->ReservedForOle);
  else
    v20 = 0;
  v12 = CDfMutex::Init((CDfMutex *)&v52, v20, 0);
  if ( v12 < 0 )
    goto LABEL_84;
  v12 = CDfMutex::Take((CDfMutex *)&v52, 0xFFFFFFFF);
  if ( v12 < 0 )
    goto LABEL_84;
  v12 = UnmarshalContext((const struct SDfMarshalPacket *)&v54, &v50, v21, 0, 0);
  if ( v12 < 0 )
  {
LABEL_82:
    CDfMutex::Release((CDfMutex *)&v52);
LABEL_84:
    CPerContext::SetThreadAllocatorState((CPerContext *)v53, v16);
    v46 = GetTlsSmAllocator();
    CSmAllocator::Uninit(v46);
    v47 = GetTlsSmAllocator();
    CSmAllocator::SetState(v47, 0, 0, 0, 0, 0);
    goto LABEL_85;
  }
  v22 = NtCurrentTeb();
  v23 = v50;
  if ( (unsigned int)gs_iSharedHeaps > 0x80 )
    goto LABEL_80;
  v24 = *(void **)v22->ReservedForOle;
  if ( v57 )
    v25 = *(_QWORD *)NtCurrentTeb()->ReservedForOle + v57;
  else
    v25 = 0;
  v26 = (v25 - 64) & ((unsigned __int128)-(__int128)v25 >> 64);
  if ( v26 )
    v27 = v26 - *(_QWORD *)NtCurrentTeb()->ReservedForOle;
  else
    v27 = 0;
  v28 = GetTlsSmAllocator();
  if ( !(*(unsigned __int8 (__fastcall **)(struct CSmAllocator *, __int64, __int64))(*(_QWORD *)v28 + 72LL))(
          v28,
          v27,
          152) )
    goto LABEL_46;
  v30 = v27 ? v27 + *(_QWORD *)NtCurrentTeb()->ReservedForOle : 0LL;
  if ( memcmp_0((const void *)(v30 + 64), &GUID_04a45d68_dba8_467d_9aed_e762432212f9, 0x10u) )
    goto LABEL_46;
  if ( v27 )
    v27 += *(_QWORD *)NtCurrentTeb()->ReservedForOle;
  CurrentProcessId = GetCurrentProcessId();
  Marshal = CMarshalList::FindMarshal((CMarshalList *)(v27 + 64), CurrentProcessId, v24);
  v33 = (CExposedStream *)(((unsigned __int64)Marshal - 64) & -(__int64)(Marshal != 0));
  if ( !v33 )
  {
LABEL_46:
    v35 = (CExposedStream *)CMallocBased::operator new(0x98u, v29);
    if ( v35 )
    {
      v33 = CExposedStream::CExposedStream(v35);
      if ( v33 )
      {
        if ( v56 )
          v36 = (struct CSeekPointer *)(*(_QWORD *)NtCurrentTeb()->ReservedForOle + v56);
        else
          v36 = 0;
        if ( v58 )
          v37 = (struct CDFBasis *)(*(_QWORD *)NtCurrentTeb()->ReservedForOle + v58);
        else
          v37 = 0;
        if ( v55 )
          v38 = (struct CPubStream *)(v55 + *(_QWORD *)NtCurrentTeb()->ReservedForOle);
        else
          v38 = 0;
        v12 = CExposedStream::Init(v33, v38, v37, v23, v36);
        if ( v12 >= 0 )
        {
          if ( v57
            && v57 + *(_QWORD *)NtCurrentTeb()->ReservedForOle
            && (unsigned __int8)BasedPtr<CMarshalList>::VerifyOnUnmarshal<CMarshalList>(&v57) )
          {
            if ( v57 )
              v40 = (CMarshalList *)(*(_QWORD *)NtCurrentTeb()->ReservedForOle + v57);
            else
              v40 = 0;
            CMarshalList::AddMarshal(v40, (CExposedStream *)((char *)v33 + 64));
          }
          if ( v55 )
            v41 = *(_QWORD *)NtCurrentTeb()->ReservedForOle + v55;
          else
            v41 = 0;
          _InterlockedIncrement((volatile signed __int32 *)(v41 + 124));
          if ( v56 )
            v42 = *(_QWORD *)NtCurrentTeb()->ReservedForOle + v56;
          else
            v42 = 0;
          _InterlockedIncrement((volatile signed __int32 *)(v42 + 24));
          goto LABEL_73;
        }
        CExposedStream::`scalar deleting destructor'(v33, v39);
        goto LABEL_81;
      }
    }
LABEL_80:
    v12 = -2147287032;
LABEL_81:
    CPerContext::Release(v23);
    goto LABEL_82;
  }
  if ( v58 )
    v34 = (_QWORD *)(*(_QWORD *)NtCurrentTeb()->ReservedForOle + v58);
  else
    v34 = 0;
  v34[4] = *((_QWORD *)v23 + 2);
  v34[5] = *((_QWORD *)v23 + 3);
  v34[6] = *((_QWORD *)v23 + 4);
  (*(void (__fastcall **)(CExposedStream *))(*(_QWORD *)v33 + 8LL))(v33);
  CPerContext::Release(v23);
LABEL_73:
  if ( !memcmp_0(Buf1, &GUID_0000000c_0000_0000_c000_000000000046, 0x10u) )
  {
    *a6 = v33;
  }
  else
  {
    v12 = (**(__int64 (__fastcall ***)(CExposedStream *, const struct _GUID *, void **))v33)(v33, Buf1, a6);
    (*(void (__fastcall **)(CExposedStream *))(*(_QWORD *)v33 + 16LL))(v33);
  }
  CDfMutex::Release((CDfMutex *)&v52);
  if ( v14 != v24 )
  {
    CPerContext::SetThreadAllocatorState((CPerContext *)v53, v43);
    v44 = GetTlsSmAllocator();
    CSmAllocator::Uninit(v44);
  }
  v45 = GetTlsSmAllocator();
  CSmAllocator::SetState(v45, 0, 0, 0, 0, 0);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
LABEL_87:
  CPerContext::~CPerContext((CPerContext *)v53);
  CDfMutex::~CDfMutex((CDfMutex *)&v52);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800405dc  push    rbp
0x1800405de  push    rbx
0x1800405df  push    rsi
0x1800405e0  push    rdi
0x1800405e1  push    r12
0x1800405e3  push    r13
0x1800405e5  push    r14
0x1800405e7  push    r15
0x1800405e9  lea     rbp, [rsp-78h]
0x1800405ee  sub     rsp, 178h
0x1800405f5  mov     rax, cs:__security_cookie
0x1800405fc  xor     rax, rsp
0x1800405ff  mov     [rbp+0B0h+var_50], rax
0x180040603  mov     r13, [rbp+0B0h+Buf1]
0x18004060a  xor     r12d, r12d
0x18004060d  mov     r15, [rbp+0B0h+arg_28]
0x180040614  xorps   xmm0, xmm0
0x180040617  mov     ebx, edx
0x180040619  mov     [rsp+1B0h+var_178], r12
0x18004061e  mov     rdi, rcx
0x180040621  mov     [rsp+1B0h+ppv], r12
0x180040626  xor     edx, edx; struct IMalloc *
0x180040628  mov     [rsp+1B0h+var_180], r12d
0x18004062d  lea     rcx, [rsp+1B0h+var_150]; this
0x180040632  mov     [rbp+0B0h+var_C0], r12
0x180040636  movdqu  [rsp+1B0h+var_168], xmm0
0x18004063c  mov     [rbp+0B0h+var_B8], r12
0x180040640  mov     sil, r9b
0x180040643  mov     [rbp+0B0h+var_B0], r12
0x180040647  mov     r14d, r8d
0x18004064a  mov     [rbp+0B0h+var_A8], r12
0x18004064e  mov     [rbp+0B0h+var_A0], r12
0x180040652  mov     [rbp+0B0h+var_98], r12
0x180040656  movdqa  [rbp+0B0h+var_90], xmm0
0x18004065b  mov     [rbp+0B0h+var_80], r12
0x18004065f  call    ??0CPerContext@@QEAA@PEAUIMalloc@@@Z; CPerContext::CPerContext(IMalloc *)
0x180040664  lea     r8, [rsp+1B0h+ppv]; ppv
0x180040669  mov     rcx, rdi; pStm
0x18004066c  lea     rdx, IID_IStream; riid
0x180040673  call    cs:__imp_CoUnmarshalInterface
0x180040679  mov     rax, [rdi]
0x18004067c  mov     rcx, rdi
0x18004067f  test    ebx, ebx
0x180040681  js      short loc_1800406B6
0x180040683  mov     rax, [rax+28h]
0x180040687  lea     r8d, [r12+1]
0x18004068c  mov     [rsp+1B0h+var_178], 44h ; 'D'
0x180040695  xor     r9d, r9d
0x180040698  mov     rdx, [rsp+1B0h+var_178]
0x18004069d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800406a2  mov     edi, eax
0x1800406a4  test    eax, eax
0x1800406a6  js      loc_180040C49
0x1800406ac  mov     edi, 80030001h
0x1800406b1  jmp     loc_180040C49
0x1800406b6  mov     rax, [rax+18h]
0x1800406ba  lea     r9, [rsp+1B0h+var_180]
0x1800406bf  mov     r8d, 70h ; 'p'
0x1800406c5  lea     rdx, [rbp+0B0h+var_C0]
0x1800406c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800406ce  mov     edi, eax
0x1800406d0  test    eax, eax
0x1800406d2  js      loc_180040C49
0x1800406d8  cmp     [rsp+1B0h+var_180], 70h ; 'p'
0x1800406dd  jz      short loc_1800406E9
0x1800406df  mov     edi, 8003001Eh
0x1800406e4  jmp     loc_180040C49
0x1800406e9  test    sil, sil
0x1800406ec  jnz     short loc_1800406AC
0x1800406ee  lea     r9, [rsp+1B0h+var_150]; struct CPerContext *
0x1800406f3  mov     r8d, r14d; unsigned int
0x1800406f6  lea     rcx, [rbp+0B0h+var_C0]; struct SDfMarshalPacket *
0x1800406fa  call    ?UnmarshalSharedMemory@@YAJPEBUSDfMarshalPacket@@KKPEAVCPerContext@@@Z; UnmarshalSharedMemory(SDfMarshalPacket const *,ulong,ulong,CPerContext *)
0x1800406ff  mov     edi, eax
0x180040701  test    eax, eax
0x180040703  js      loc_180040C49
0x180040709  mov     rax, gs:30h
0x180040712  mov     rcx, [rax+1758h]
0x180040719  mov     r12, [rcx]
0x18004071c  call    ?GetTlsSmAllocator@@YAAEAVCSmAllocator@@XZ; GetTlsSmAllocator(void)
0x180040721  mov     rdx, [rbp+0B0h+var_B8]
0x180040725  mov     r9, rax
0x180040728  mov     r8d, 0A8h
0x18004072e  mov     rcx, [rax]
0x180040731  mov     rax, [rcx+48h]
0x180040735  mov     rcx, r9
0x180040738  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004073d  test    al, al
0x18004073f  jz      loc_180040C06
0x180040745  cmp     [rbp+0B0h+var_B8], 0
0x18004074a  jz      short loc_180040768
0x18004074c  mov     rax, gs:30h
0x180040755  mov     rcx, [rax+1758h]
0x18004075c  mov     rdx, [rcx]
0x18004075f  mov     rcx, [rbp+0B0h+var_B8]
0x180040763  add     rcx, rdx
0x180040766  jmp     short loc_18004076A
0x180040768  xor     ecx, ecx; Buf1
0x18004076a  mov     ebx, 10h
0x18004076f  lea     rdx, _GUID_ab8fc07c_9ca5_4cb4_80f9_f0811ff49894; Buf2
0x180040776  mov     r8d, ebx; Size
0x180040779  call    memcmp_0
0x18004077e  test    eax, eax
0x180040780  jnz     loc_180040C06
0x180040786  lea     rcx, [rbp+0B0h+var_98]
0x18004078a  call    ??$VerifyOnUnmarshal@VCGlobalContext@@@?$BasedPtr@VCGlobalContext@@@@QEBA_NXZ; BasedPtr<CGlobalContext>::VerifyOnUnmarshal<CGlobalContext>(void)
0x18004078f  test    al, al
0x180040791  jz      loc_180040C06
0x180040797  lea     rcx, [rbp+0B0h+var_A0]
0x18004079b  call    ??$VerifyOnUnmarshal@VCDFBasis@@@?$BasedPtr@VCDFBasis@@@@QEBA_NXZ; BasedPtr<CDFBasis>::VerifyOnUnmarshal<CDFBasis>(void)
0x1800407a0  test    al, al
0x1800407a2  jz      loc_180040C06
0x1800407a8  call    ?GetTlsSmAllocator@@YAAEAVCSmAllocator@@XZ; GetTlsSmAllocator(void)
0x1800407ad  mov     rdx, [rbp+0B0h+var_B0]
0x1800407b1  lea     r8d, [rbx+10h]
0x1800407b5  mov     r9, rax
0x1800407b8  mov     rcx, [rax]
0x1800407bb  mov     rax, [rcx+48h]
0x1800407bf  mov     rcx, r9
0x1800407c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800407c7  test    al, al
0x1800407c9  jz      loc_180040C06
0x1800407cf  cmp     [rbp+0B0h+var_B0], 0
0x1800407d4  jz      short loc_1800407F2
0x1800407d6  mov     rax, gs:30h
0x1800407df  mov     rcx, [rax+1758h]
0x1800407e6  mov     rdx, [rcx]
0x1800407e9  mov     rcx, [rbp+0B0h+var_B0]
0x1800407ed  add     rcx, rdx
0x1800407f0  jmp     short loc_1800407F4
0x1800407f2  xor     ecx, ecx; Buf1
0x1800407f4  mov     r8, rbx; Size
0x1800407f7  lea     rdx, _GUID_56401fd1_cf16_4404_9dd0_d642080d23eb; Buf2
0x1800407fe  call    memcmp_0
0x180040803  test    eax, eax
0x180040805  jnz     loc_180040C06
0x18004080b  cmp     [rbp+0B0h+var_98], 0
0x180040810  jz      short loc_18004082B
0x180040812  mov     rax, gs:30h
0x18004081b  mov     rcx, [rax+1758h]
0x180040822  mov     rdx, [rcx]
0x180040825  add     rdx, [rbp+0B0h+var_98]
0x180040829  jmp     short loc_18004082D
0x18004082b  xor     edx, edx; struct CGlobalContext *
0x18004082d  xor     r8d, r8d; int
0x180040830  lea     rcx, [rsp+1B0h+var_168]; this
0x180040835  call    ?Init@CDfMutex@@QEAAJPEAVCGlobalContext@@H@Z; CDfMutex::Init(CGlobalContext *,int)
0x18004083a  mov     edi, eax
0x18004083c  test    eax, eax
0x18004083e  js      loc_180040C0B
0x180040844  or      edx, 0FFFFFFFFh; unsigned int
0x180040847  lea     rcx, [rsp+1B0h+var_168]; this
0x18004084c  call    ?Take@CDfMutex@@QEAAJK@Z; CDfMutex::Take(ulong)
0x180040851  mov     edi, eax
0x180040853  test    eax, eax
0x180040855  js      loc_180040C0B
0x18004085b  xor     r9d, r9d; int
0x18004085e  mov     dword ptr [rsp+1B0h+var_190], 0; int
0x180040866  lea     rdx, [rsp+1B0h+var_178]; struct CPerContext **
0x18004086b  lea     rcx, [rbp+0B0h+var_C0]; struct SDfMarshalPacket *
0x18004086f  call    ?UnmarshalContext@@YAJPEBUSDfMarshalPacket@@PEAPEAVCPerContext@@KHH@Z; UnmarshalContext(SDfMarshalPacket const *,CPerContext * *,ulong,int,int)
0x180040874  mov     edi, eax
0x180040876  test    eax, eax
0x180040878  js      loc_180040BFA
0x18004087e  mov     rax, gs:30h
0x180040887  cmp     cs:?gs_iSharedHeaps@@3HA, 80h; int gs_iSharedHeaps
0x180040891  mov     rsi, [rsp+1B0h+var_178]
0x180040896  ja      loc_180040BED
0x18004089c  cmp     [rbp+0B0h+var_A8], 0
0x1800408a1  mov     rax, [rax+1758h]
0x1800408a8  mov     r14, [rax]
0x1800408ab  jz      short loc_1800408C9
0x1800408ad  mov     rax, gs:30h
0x1800408b6  mov     rcx, [rax+1758h]
0x1800408bd  mov     rdx, [rcx]
0x1800408c0  mov     rcx, [rbp+0B0h+var_A8]
0x1800408c4  add     rcx, rdx
0x1800408c7  jmp     short loc_1800408CB
0x1800408c9  xor     ecx, ecx
0x1800408cb  lea     rax, [rcx-40h]
0x1800408cf  neg     rcx
0x1800408d2  sbb     rbx, rbx
0x1800408d5  and     rbx, rax
0x1800408d8  jz      short loc_1800408EF
0x1800408da  mov     rax, gs:30h
0x1800408e3  mov     rcx, [rax+1758h]
0x1800408ea  sub     rbx, [rcx]
0x1800408ed  jmp     short loc_1800408F1
0x1800408ef  xor     ebx, ebx
0x1800408f1  call    ?GetTlsSmAllocator@@YAAEAVCSmAllocator@@XZ; GetTlsSmAllocator(void)
0x1800408f6  mov     r9, rax
0x1800408f9  mov     r8d, 98h
0x1800408ff  mov     rdx, rbx
0x180040902  mov     rcx, [rax]
0x180040905  mov     rax, [rcx+48h]
0x180040909  mov     rcx, r9
0x18004090c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040911  test    al, al
0x180040913  jz      loc_1800409EC
0x180040919  test    rbx, rbx
0x18004091c  jz      short loc_180040936
0x18004091e  mov     rax, gs:30h
0x180040927  mov     rcx, [rax+1758h]
0x18004092e  mov     rcx, [rcx]
0x180040931  add     rcx, rbx
0x180040934  jmp     short loc_180040938
0x180040936  xor     ecx, ecx
0x180040938  add     rcx, 40h ; '@'; Buf1
0x18004093c  lea     rdx, _GUID_04a45d68_dba8_467d_9aed_e762432212f9; Buf2
0x180040943  mov     r8d, 10h; Size
0x180040949  call    memcmp_0
0x18004094e  test    eax, eax
0x180040950  jnz     loc_1800409EC
0x180040956  test    rbx, rbx
0x180040959  jz      short loc_18004096E
0x18004095b  mov     rax, gs:30h
0x180040964  mov     rcx, [rax+1758h]
0x18004096b  add     rbx, [rcx]
0x18004096e  call    cs:__imp_GetCurrentProcessId
0x180040974  lea     rcx, [rbx+40h]; this
0x180040978  mov     r8, r14; void *
0x18004097b  mov     edx, eax; unsigned int
0x18004097d  call    ?FindMarshal@CMarshalList@@QEBAPEAV1@KPEAX@Z; CMarshalList::FindMarshal(ulong,void *)
0x180040982  lea     rcx, [rax-40h]
0x180040986  neg     rax
0x180040989  sbb     rbx, rbx
0x18004098c  and     rbx, rcx
0x18004098f  jz      short loc_1800409EC
0x180040991  cmp     [rbp+0B0h+var_A0], 0
0x180040996  jz      short loc_1800409B4
0x180040998  mov     rax, gs:30h
0x1800409a1  mov     rcx, [rax+1758h]
0x1800409a8  mov     rdx, [rcx]
0x1800409ab  mov     rcx, [rbp+0B0h+var_A0]
0x1800409af  add     rcx, rdx
0x1800409b2  jmp     short loc_1800409B6
0x1800409b4  xor     ecx, ecx
0x1800409b6  mov     rax, [rsi+10h]
0x1800409ba  mov     [rcx+20h], rax
0x1800409be  mov     rax, [rsi+18h]
0x1800409c2  mov     [rcx+28h], rax
0x1800409c6  mov     rax, [rsi+20h]
0x1800409ca  mov     [rcx+30h], rax
0x1800409ce  mov     rcx, rbx
0x1800409d1  mov     rax, [rbx]
0x1800409d4  mov     rax, [rax+8]
0x1800409d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800409dd  mov     rcx, rsi; this
0x1800409e0  call    ?Release@CPerContext@@QEAAJXZ; CPerContext::Release(void)
0x1800409e5  xor     esi, esi
0x1800409e7  jmp     loc_180040B4D
0x1800409ec  mov     ecx, 98h; unsigned __int64
0x1800409f1  call    ??2CMallocBased@@SAPEAX_KQEAUIMalloc@@@Z; CMallocBased::operator new(unsigned __int64,IMalloc * const)
0x1800409f6  test    rax, rax
0x1800409f9  jz      loc_180040BED
0x1800409ff  mov     rcx, rax; this
0x180040a02  call    ??0CExposedStream@@QEAA@XZ; CExposedStream::CExposedStream(void)
0x180040a07  xor     r10d, r10d
0x180040a0a  mov     rbx, rax
0x180040a0d  test    rax, rax
0x180040a10  jz      loc_180040BED
0x180040a16  cmp     [rbp+0B0h+var_B0], r10
0x180040a1a  jz      short loc_180040A35
0x180040a1c  mov     rax, gs:30h
0x180040a25  mov     r9, [rbp+0B0h+var_B0]
0x180040a29  mov     rcx, [rax+1758h]
0x180040a30  add     r9, [rcx]
0x180040a33  jmp     short loc_180040A38
0x180040a35  mov     r9, r10
0x180040a38  cmp     [rbp+0B0h+var_A0], r10
0x180040a3c  jz      short loc_180040A57
0x180040a3e  mov     rax, gs:30h
0x180040a47  mov     r8, [rbp+0B0h+var_A0]
0x180040a4b  mov     rcx, [rax+1758h]
0x180040a52  add     r8, [rcx]
0x180040a55  jmp     short loc_180040A5A
0x180040a57  mov     r8, r10; struct CDFBasis *
0x180040a5a  cmp     [rbp+0B0h+var_B8], r10
0x180040a5e  jz      short loc_180040A79
0x180040a60  mov     rax, gs:30h
0x180040a69  mov     rcx, [rax+1758h]
0x180040a70  mov     rdx, [rcx]
0x180040a73  add     rdx, [rbp+0B0h+var_B8]
0x180040a77  jmp     short loc_180040A7C
0x180040a79  mov     rdx, r10; struct CPubStream *
0x180040a7c  mov     [rsp+1B0h+var_190], r9; struct CSeekPointer *
0x180040a81  mov     rcx, rbx; this
0x180040a84  mov     r9, rsi; struct CPerContext *
0x180040a87  call    ?Init@CExposedStream@@QEAAJPEAVCPubStream@@PEAVCDFBasis@@PEAVCPerContext@@PEAVCSeekPointer@@@Z; CExposedStream::Init(CPubStream *,CDFBasis *,CPerContext *,CSeekPointer *)
0x180040a8c  mov     edi, eax
0x180040a8e  test    eax, eax
0x180040a90  jns     short loc_180040A9F
0x180040a92  mov     rcx, rbx; this
0x180040a95  call    ??_GCExposedStream@@QEAAPEAXI@Z; CExposedStream::`scalar deleting destructor'(uint)
0x180040a9a  jmp     loc_180040BF2
0x180040a9f  xor     esi, esi
0x180040aa1  cmp     [rbp+0B0h+var_A8], rsi
0x180040aa5  jz      short loc_180040AFB
0x180040aa7  mov     rax, gs:30h
0x180040ab0  mov     rcx, [rax+1758h]
  ... truncated ...
```
