# CExposedDocFile::Unmarshal(IStream *,ulong,ulong,bool,_GUID const &,void * *)

- ea: `0x18003b588`
- end: `0x18003bbb8`
- name: `?Unmarshal@CExposedDocFile@@SAJPEAUIStream@@KK_NAEBU_GUID@@PEAPEAX@Z`
- size: `1584`
- prototype: `__int64 __usercall@<rax>(LPSTREAM pStm@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, bool@<r9b>, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `28`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003eee0`

## callees

- `0x180018680`
- `0x18001b840`
- `0x18001b89c`
- `0x18001bb24`
- `0x18001c268`
- `0x18001d820`
- `0x18001e0f8`
- `0x18001e17c`
- `0x18001efe8`
- `0x18001fbb4`
- `0x18002db70`
- `0x18002dbd0`
- `0x18002e5d8`
- `0x18003b588`
- `0x180042800`
- `0x18004a6b8`
- `0x18004a734`
- `0x18004a7b4`
- `0x18004a830`
- `0x18004a8c8`
- `0x18004a960`
- `0x18004ba24`
- `0x18004ca84`
- `0x18004cdec`
- `0x18004d1d0`
- `0x18004d230`
- `0x180061410`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003bbab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003bbab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003b8de`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003b8de`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x18003b61f`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x18003b61f`

## pseudocode

```c
__int64 __fastcall CExposedDocFile::Unmarshal(
        LPSTREAM pStm,
        int a2,
        int a3,
        char a4,
        const struct _GUID *Buf1,
        void **a6)
{
  __int64 v10; // rax
  __int64 (__fastcall *v11)(LPSTREAM, __int64, __int64, _QWORD); // rax
  int v12; // ebx
  __int64 v13; // rdx
  void *v14; // r12
  struct CPerContext **v15; // rdx
  CPubDocFile *v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r8
  __int64 v19; // r8
  struct CGlobalContext *v20; // rdx
  CPubDocFile *v21; // rcx
  int IsRoot; // eax
  __int64 v23; // r8
  struct _TEB *v24; // rax
  struct CPerContext *v25; // rsi
  void *v26; // r14
  __int64 v27; // rcx
  __int64 v28; // rdi
  __int64 v29; // rdi
  struct IMalloc *v30; // rdx
  DWORD CurrentProcessId; // eax
  struct CMarshalList *Marshal; // rax
  CExposedDocFile *v33; // rdi
  _QWORD *v34; // rcx
  CExposedDocFile *v35; // r10
  struct CDFBasis *v36; // r8
  struct CPubDocFile *v37; // rdx
  CMarshalList *v38; // rcx
  __int64 v39; // rcx
  struct CPerContext **v40; // rdx
  CSmAllocator *TlsSmAllocator; // rax
  CSmAllocator *v42; // rax
  CSmAllocator *v44; // rax
  CSmAllocator *v45; // rax
  int v46; // [rsp+30h] [rbp-D0h] BYREF
  struct CPerContext *v47; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v49; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hObject[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v51[144]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v52[3]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v53; // [rsp+108h] [rbp+8h] BYREF
  __int64 v54; // [rsp+110h] [rbp+10h] BYREF
  __int64 v55; // [rsp+118h] [rbp+18h] BYREF
  __int128 v56; // [rsp+120h] [rbp+20h]
  __int64 v57; // [rsp+130h] [rbp+30h]

  v47 = 0;
  ppv = 0;
  v46 = 0;
  memset(v52, 0, sizeof(v52));
  *(_OWORD *)hObject = 0;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  CPerContext::CPerContext((CPerContext *)v51, 0);
  CoUnmarshalInterface(pStm, &IID_IStorage, &ppv);
  v10 = *(_QWORD *)pStm;
  if ( a2 >= 0 )
  {
    v11 = *(__int64 (__fastcall **)(LPSTREAM, __int64, __int64, _QWORD))(v10 + 40);
    v47 = (struct CPerContext *)68;
    v12 = v11(pStm, 68, 1, 0);
    if ( v12 < 0 )
      goto LABEL_77;
    goto LABEL_3;
  }
  v12 = (*(__int64 (__fastcall **)(LPSTREAM, _QWORD *, __int64, int *))(v10 + 24))(pStm, v52, 112, &v46);
  if ( v12 >= 0 )
  {
    if ( v46 != 112 )
    {
      v12 = -2147287010;
      goto LABEL_77;
    }
    if ( a4 )
    {
LABEL_3:
      v12 = -2147287039;
      goto LABEL_77;
    }
    v12 = UnmarshalSharedMemory((const struct SDfMarshalPacket *)v52, v13, a3, (struct CPerContext *)v51);
    if ( v12 >= 0 )
    {
      v14 = *(void **)NtCurrentTeb()->ReservedForOle;
      if ( (unsigned __int8)BasedPtr<CPubDocFile>::VerifyOnUnmarshal<CPubDocFile>(v52)
        && (unsigned __int8)BasedPtr<CGlobalContext>::VerifyOnUnmarshal<CGlobalContext>(&v55)
        && (unsigned __int8)BasedPtr<CDFBasis>::VerifyOnUnmarshal<CDFBasis>(&v54)
        && ((!v52[0] ? (v16 = 0) : (v16 = (CPubDocFile *)(v52[0] + *(_QWORD *)NtCurrentTeb()->ReservedForOle)),
             !(unsigned int)CPubDocFile::IsRoot(v16))
         || (!v17 || (v18 = v52[0] + *(_QWORD *)NtCurrentTeb()->ReservedForOle) == 0
           ? (v19 = 0)
           : (v19 = v18 - *(_QWORD *)NtCurrentTeb()->ReservedForOle),
             v49 = v19,
             (unsigned __int8)BasedPtr<CRootPubDocFile>::VerifyOnUnmarshal<CRootPubDocFile>(&v49))) )
      {
        if ( v55 )
          v20 = (struct CGlobalContext *)(v55 + *(_QWORD *)NtCurrentTeb()->ReservedForOle);
        else
          v20 = 0;
        v12 = CDfMutex::Init((CDfMutex *)hObject, v20, 0);
        if ( v12 >= 0 )
        {
          v12 = CDfMutex::Take((CDfMutex *)hObject, 0xFFFFFFFF);
          if ( v12 >= 0 )
          {
            v21 = (CPubDocFile *)v52[0];
            if ( v52[0] )
              v21 = (CPubDocFile *)v52[0];
            if ( v21 )
              v21 = (CPubDocFile *)(*(_QWORD *)NtCurrentTeb()->ReservedForOle + v52[0]);
            IsRoot = CPubDocFile::IsRoot(v21);
            v12 = UnmarshalContext((const struct SDfMarshalPacket *)v52, &v47, v23, IsRoot, v23);
            if ( v12 >= 0 )
            {
              v24 = NtCurrentTeb();
              v25 = v47;
              if ( (unsigned int)gs_iSharedHeaps <= 0x80 )
              {
                v26 = *(void **)v24->ReservedForOle;
                if ( v53 )
                  v27 = *(_QWORD *)NtCurrentTeb()->ReservedForOle + v53;
                else
                  v27 = 0;
                v28 = (v27 - 120) & -(__int64)(v27 != 0);
                if ( v28 )
                  v29 = v28 - *(_QWORD *)NtCurrentTeb()->ReservedForOle;
                else
                  v29 = 0;
                v49 = v29;
                if ( (unsigned __int8)BasedPtr<CExposedDocFile>::VerifyOnUnmarshal<CExposedDocFile>(&v49) )
                {
                  if ( v29 )
                    v29 += *(_QWORD *)NtCurrentTeb()->ReservedForOle;
                  CurrentProcessId = GetCurrentProcessId();
                  Marshal = CMarshalList::FindMarshal((CMarshalList *)(v29 + 120), CurrentProcessId, v26);
                  v33 = (CExposedDocFile *)(((unsigned __int64)Marshal - 120) & -(__int64)(Marshal != 0));
                  if ( v33 )
                  {
                    if ( v54 )
                      v34 = (_QWORD *)(*(_QWORD *)NtCurrentTeb()->ReservedForOle + v54);
                    else
                      v34 = 0;
                    v34[4] = *((_QWORD *)v25 + 2);
                    v34[5] = *((_QWORD *)v25 + 3);
                    v34[6] = *((_QWORD *)v25 + 4);
                    (*(void (__fastcall **)(CExposedDocFile *))(*(_QWORD *)v33 + 8LL))(v33);
                    CPerContext::Release(v25);
LABEL_65:
                    if ( !memcmp_0(Buf1, &GUID_0000000b_0000_0000_c000_000000000046, 0x10u) )
                    {
                      *a6 = v33;
                    }
                    else
                    {
                      v12 = (**(__int64 (__fastcall ***)(CExposedDocFile *, const struct _GUID *, void **))v33)(
                              v33,
                              Buf1,
                              a6);
                      (*(void (__fastcall **)(CExposedDocFile *))(*(_QWORD *)v33 + 16LL))(v33);
                    }
                    CDfMutex::Release((CDfMutex *)hObject);
                    if ( v14 != v26 )
                    {
                      CPerContext::SetThreadAllocatorState((CPerContext *)v51, v40);
                      TlsSmAllocator = GetTlsSmAllocator();
                      CSmAllocator::Uninit(TlsSmAllocator);
                    }
                    v42 = GetTlsSmAllocator();
                    CSmAllocator::SetState(v42, 0, 0, 0, 0, 0);
                    if ( ppv )
                      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
                    goto LABEL_72;
                  }
                }
                v35 = (CExposedDocFile *)CMallocBased::operator new(0x100u, v30);
                if ( v35 )
                {
                  v36 = v54 ? (struct CDFBasis *)(v54 + *(_QWORD *)NtCurrentTeb()->ReservedForOle) : 0LL;
                  v37 = v52[0] ? (struct CPubDocFile *)(v52[0] + *(_QWORD *)NtCurrentTeb()->ReservedForOle) : 0LL;
                  v33 = CExposedDocFile::CExposedDocFile(v35, v37, v36, v25);
                  if ( v33 )
                  {
                    if ( v53
                      && v53 + *(_QWORD *)NtCurrentTeb()->ReservedForOle
                      && (unsigned __int8)BasedPtr<CMarshalList>::VerifyOnUnmarshal<CMarshalList>(&v53) )
                    {
                      if ( v53 )
                        v38 = (CMarshalList *)(*(_QWORD *)NtCurrentTeb()->ReservedForOle + v53);
                      else
                        v38 = 0;
                      CMarshalList::AddMarshal(v38, (CExposedDocFile *)((char *)v33 + 120));
                    }
                    if ( v52[0] )
                      v39 = *(_QWORD *)NtCurrentTeb()->ReservedForOle + v52[0];
                    else
                      v39 = 0;
                    _InterlockedIncrement((volatile signed __int32 *)(v39 + 156));
                    goto LABEL_65;
                  }
                }
              }
              v12 = -2147287032;
              CPerContext::Release(v25);
            }
            CDfMutex::Release((CDfMutex *)hObject);
          }
        }
      }
      else
      {
        v12 = -2147024891;
      }
      CPerContext::SetThreadAllocatorState((CPerContext *)v51, v15);
      v44 = GetTlsSmAllocator();
      CSmAllocator::Uninit(v44);
      v45 = GetTlsSmAllocator();
      CSmAllocator::SetState(v45, 0, 0, 0, 0, 0);
    }
  }
LABEL_77:
  if ( !ppv )
  {
LABEL_72:
    CPerContext::~CPerContext((CPerContext *)v51);
    CDfMutex::~CDfMutex((CDfMutex *)hObject);
    return (unsigned int)v12;
  }
  *a6 = ppv;
  CPerContext::~CPerContext((CPerContext *)v51);
  if ( hObject[1] )
    CloseHandle(hObject[1]);
  return 0;
}

```

## disassembly

```asm
0x18003b588  push    rbp
0x18003b58a  push    rbx
0x18003b58b  push    rsi
0x18003b58c  push    rdi
0x18003b58d  push    r12
0x18003b58f  push    r13
0x18003b591  push    r14
0x18003b593  push    r15
0x18003b595  lea     rbp, [rsp-78h]
0x18003b59a  sub     rsp, 178h
0x18003b5a1  mov     rax, cs:__security_cookie
0x18003b5a8  xor     rax, rsp
0x18003b5ab  mov     [rbp+0B0h+var_50], rax
0x18003b5af  mov     r13, [rbp+0B0h+Buf1]
0x18003b5b6  xor     r12d, r12d
0x18003b5b9  mov     r15, [rbp+0B0h+arg_28]
0x18003b5c0  xorps   xmm0, xmm0
0x18003b5c3  mov     ebx, edx
0x18003b5c5  mov     [rsp+1B0h+var_178], r12
0x18003b5ca  mov     rdi, rcx
0x18003b5cd  mov     [rsp+1B0h+ppv], r12
0x18003b5d2  xor     edx, edx; struct IMalloc *
0x18003b5d4  mov     [rsp+1B0h+var_180], r12d
0x18003b5d9  lea     rcx, [rsp+1B0h+var_150]; this
0x18003b5de  mov     [rbp+0B0h+var_C0], r12
0x18003b5e2  movdqu  xmmword ptr [rsp+1B0h+hObject], xmm0
0x18003b5e8  mov     [rbp+0B0h+var_B8], r12
0x18003b5ec  mov     sil, r9b
0x18003b5ef  mov     [rbp+0B0h+var_B0], r12
0x18003b5f3  mov     r14d, r8d
0x18003b5f6  mov     [rbp+0B0h+var_A8], r12
0x18003b5fa  mov     [rbp+0B0h+var_A0], r12
0x18003b5fe  mov     [rbp+0B0h+var_98], r12
0x18003b602  movdqa  [rbp+0B0h+var_90], xmm0
0x18003b607  mov     [rbp+0B0h+var_80], r12
0x18003b60b  call    ??0CPerContext@@QEAA@PEAUIMalloc@@@Z; CPerContext::CPerContext(IMalloc *)
0x18003b610  lea     r8, [rsp+1B0h+ppv]; ppv
0x18003b615  mov     rcx, rdi; pStm
0x18003b618  lea     rdx, IID_IStorage; riid
0x18003b61f  call    cs:__imp_CoUnmarshalInterface
0x18003b625  mov     rax, [rdi]
0x18003b628  mov     rcx, rdi
0x18003b62b  test    ebx, ebx
0x18003b62d  js      short loc_18003B662
0x18003b62f  mov     rax, [rax+28h]
0x18003b633  lea     r8d, [r12+1]
0x18003b638  mov     [rsp+1B0h+var_178], 44h ; 'D'
0x18003b641  xor     r9d, r9d
0x18003b644  mov     rdx, [rsp+1B0h+var_178]
0x18003b649  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b64e  mov     ebx, eax
0x18003b650  test    eax, eax
0x18003b652  js      loc_18003BB86
0x18003b658  mov     ebx, 80030001h
0x18003b65d  jmp     loc_18003BB86
0x18003b662  mov     rax, [rax+18h]
0x18003b666  lea     r9, [rsp+1B0h+var_180]
0x18003b66b  mov     r8d, 70h ; 'p'
0x18003b671  lea     rdx, [rbp+0B0h+var_C0]
0x18003b675  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b67a  mov     ebx, eax
0x18003b67c  test    eax, eax
0x18003b67e  js      loc_18003BB86
0x18003b684  cmp     [rsp+1B0h+var_180], 70h ; 'p'
0x18003b689  jz      short loc_18003B695
0x18003b68b  mov     ebx, 8003001Eh
0x18003b690  jmp     loc_18003BB86
0x18003b695  test    sil, sil
0x18003b698  jnz     short loc_18003B658
0x18003b69a  lea     r9, [rsp+1B0h+var_150]; struct CPerContext *
0x18003b69f  mov     r8d, r14d; unsigned int
0x18003b6a2  lea     rcx, [rbp+0B0h+var_C0]; struct SDfMarshalPacket *
0x18003b6a6  call    ?UnmarshalSharedMemory@@YAJPEBUSDfMarshalPacket@@KKPEAVCPerContext@@@Z; UnmarshalSharedMemory(SDfMarshalPacket const *,ulong,ulong,CPerContext *)
0x18003b6ab  mov     ebx, eax
0x18003b6ad  test    eax, eax
0x18003b6af  js      loc_18003BB86
0x18003b6b5  mov     rax, gs:30h
0x18003b6be  mov     rcx, [rax+1758h]
0x18003b6c5  mov     r12, [rcx]
0x18003b6c8  lea     rcx, [rbp+0B0h+var_C0]
0x18003b6cc  call    ??$VerifyOnUnmarshal@VCPubDocFile@@@?$BasedPtr@VCPubDocFile@@@@QEBA_NXZ; BasedPtr<CPubDocFile>::VerifyOnUnmarshal<CPubDocFile>(void)
0x18003b6d1  test    al, al
0x18003b6d3  jz      loc_18003BB43
0x18003b6d9  lea     rcx, [rbp+0B0h+var_98]
0x18003b6dd  call    ??$VerifyOnUnmarshal@VCGlobalContext@@@?$BasedPtr@VCGlobalContext@@@@QEBA_NXZ; BasedPtr<CGlobalContext>::VerifyOnUnmarshal<CGlobalContext>(void)
0x18003b6e2  test    al, al
0x18003b6e4  jz      loc_18003BB43
0x18003b6ea  lea     rcx, [rbp+0B0h+var_A0]
0x18003b6ee  call    ??$VerifyOnUnmarshal@VCDFBasis@@@?$BasedPtr@VCDFBasis@@@@QEBA_NXZ; BasedPtr<CDFBasis>::VerifyOnUnmarshal<CDFBasis>(void)
0x18003b6f3  test    al, al
0x18003b6f5  jz      loc_18003BB43
0x18003b6fb  mov     r8, [rbp+0B0h+var_C0]
0x18003b6ff  test    r8, r8
0x18003b702  jz      short loc_18003B720
0x18003b704  mov     rax, gs:30h
0x18003b70d  mov     r8, [rbp+0B0h+var_C0]
0x18003b711  mov     rcx, [rax+1758h]
0x18003b718  mov     rcx, [rcx]
0x18003b71b  add     rcx, r8
0x18003b71e  jmp     short loc_18003B722
0x18003b720  xor     ecx, ecx; this
0x18003b722  call    ?IsRoot@CPubDocFile@@QEBAHXZ; CPubDocFile::IsRoot(void)
0x18003b727  test    eax, eax
0x18003b729  jz      short loc_18003B778
0x18003b72b  test    r8, r8
0x18003b72e  jz      short loc_18003B75E
0x18003b730  mov     rax, gs:30h
0x18003b739  mov     rcx, [rax+1758h]
0x18003b740  mov     r8, [rcx]
0x18003b743  add     r8, [rbp+0B0h+var_C0]
0x18003b747  jz      short loc_18003B75E
0x18003b749  mov     rax, gs:30h
0x18003b752  mov     rcx, [rax+1758h]
0x18003b759  sub     r8, [rcx]
0x18003b75c  jmp     short loc_18003B761
0x18003b75e  xor     r8d, r8d
0x18003b761  lea     rcx, [rsp+1B0h+var_168]
0x18003b766  mov     [rsp+1B0h+var_168], r8
0x18003b76b  call    ??$VerifyOnUnmarshal@VCRootPubDocFile@@@?$BasedPtr@VCRootPubDocFile@@@@QEBA_NXZ; BasedPtr<CRootPubDocFile>::VerifyOnUnmarshal<CRootPubDocFile>(void)
0x18003b770  test    al, al
0x18003b772  jz      loc_18003BB43
0x18003b778  cmp     [rbp+0B0h+var_98], 0
0x18003b77d  jz      short loc_18003B798
0x18003b77f  mov     rax, gs:30h
0x18003b788  mov     rcx, [rax+1758h]
0x18003b78f  mov     rdx, [rcx]
0x18003b792  add     rdx, [rbp+0B0h+var_98]
0x18003b796  jmp     short loc_18003B79A
0x18003b798  xor     edx, edx; struct CGlobalContext *
0x18003b79a  xor     r8d, r8d; int
0x18003b79d  lea     rcx, [rsp+1B0h+hObject]; this
0x18003b7a2  call    ?Init@CDfMutex@@QEAAJPEAVCGlobalContext@@H@Z; CDfMutex::Init(CGlobalContext *,int)
0x18003b7a7  mov     ebx, eax
0x18003b7a9  test    eax, eax
0x18003b7ab  js      loc_18003BB48
0x18003b7b1  or      edx, 0FFFFFFFFh; unsigned int
0x18003b7b4  lea     rcx, [rsp+1B0h+hObject]; this
0x18003b7b9  call    ?Take@CDfMutex@@QEAAJK@Z; CDfMutex::Take(ulong)
0x18003b7be  mov     ebx, eax
0x18003b7c0  test    eax, eax
0x18003b7c2  js      loc_18003BB48
0x18003b7c8  mov     rcx, [rbp+0B0h+var_C0]
0x18003b7cc  test    rcx, rcx
0x18003b7cf  jz      short loc_18003B7ED
0x18003b7d1  mov     rax, gs:30h
0x18003b7da  mov     rcx, [rax+1758h]
0x18003b7e1  mov     r8, [rcx]
0x18003b7e4  mov     rcx, [rbp+0B0h+var_C0]
0x18003b7e8  add     r8, rcx
0x18003b7eb  jmp     short loc_18003B7F0
0x18003b7ed  xor     r8d, r8d
0x18003b7f0  mov     r8d, [r8+14h]
0x18003b7f4  and     r8d, 4
0x18003b7f8  test    rcx, rcx
0x18003b7fb  jz      short loc_18003B817
0x18003b7fd  mov     rax, gs:30h
0x18003b806  mov     rcx, [rax+1758h]
0x18003b80d  mov     rdx, [rcx]
0x18003b810  mov     rcx, [rbp+0B0h+var_C0]
0x18003b814  add     rcx, rdx; this
0x18003b817  call    ?IsRoot@CPubDocFile@@QEBAHXZ; CPubDocFile::IsRoot(void)
0x18003b81c  mov     r9d, eax; int
0x18003b81f  mov     dword ptr [rsp+1B0h+var_190], r8d; int
0x18003b824  lea     rdx, [rsp+1B0h+var_178]; struct CPerContext **
0x18003b829  lea     rcx, [rbp+0B0h+var_C0]; struct SDfMarshalPacket *
0x18003b82d  call    ?UnmarshalContext@@YAJPEBUSDfMarshalPacket@@PEAPEAVCPerContext@@KHH@Z; UnmarshalContext(SDfMarshalPacket const *,CPerContext * *,ulong,int,int)
0x18003b832  mov     ebx, eax
0x18003b834  test    eax, eax
0x18003b836  js      loc_18003BB37
0x18003b83c  mov     rax, gs:30h
0x18003b845  cmp     cs:?gs_iSharedHeaps@@3HA, 80h; int gs_iSharedHeaps
0x18003b84f  mov     rsi, [rsp+1B0h+var_178]
0x18003b854  ja      loc_18003BB2A
0x18003b85a  cmp     [rbp+0B0h+var_A8], 0
0x18003b85f  mov     rax, [rax+1758h]
0x18003b866  mov     r14, [rax]
0x18003b869  jz      short loc_18003B887
0x18003b86b  mov     rax, gs:30h
0x18003b874  mov     rcx, [rax+1758h]
0x18003b87b  mov     rdx, [rcx]
0x18003b87e  mov     rcx, [rbp+0B0h+var_A8]
0x18003b882  add     rcx, rdx
0x18003b885  jmp     short loc_18003B889
0x18003b887  xor     ecx, ecx
0x18003b889  lea     rax, [rcx-78h]
0x18003b88d  neg     rcx
0x18003b890  sbb     rdi, rdi
0x18003b893  and     rdi, rax
0x18003b896  jz      short loc_18003B8AD
0x18003b898  mov     rax, gs:30h
0x18003b8a1  mov     rcx, [rax+1758h]
0x18003b8a8  sub     rdi, [rcx]
0x18003b8ab  jmp     short loc_18003B8AF
0x18003b8ad  xor     edi, edi
0x18003b8af  lea     rcx, [rsp+1B0h+var_168]
0x18003b8b4  mov     [rsp+1B0h+var_168], rdi
0x18003b8b9  call    ??$VerifyOnUnmarshal@VCExposedDocFile@@@?$BasedPtr@VCExposedDocFile@@@@QEBA_NXZ; BasedPtr<CExposedDocFile>::VerifyOnUnmarshal<CExposedDocFile>(void)
0x18003b8be  test    al, al
0x18003b8c0  jz      loc_18003B95C
0x18003b8c6  test    rdi, rdi
0x18003b8c9  jz      short loc_18003B8DE
0x18003b8cb  mov     rax, gs:30h
0x18003b8d4  mov     rcx, [rax+1758h]
0x18003b8db  add     rdi, [rcx]
0x18003b8de  call    cs:__imp_GetCurrentProcessId
0x18003b8e4  lea     rcx, [rdi+78h]; this
0x18003b8e8  mov     r8, r14; void *
0x18003b8eb  mov     edx, eax; unsigned int
0x18003b8ed  call    ?FindMarshal@CMarshalList@@QEBAPEAV1@KPEAX@Z; CMarshalList::FindMarshal(ulong,void *)
0x18003b8f2  lea     rcx, [rax-78h]
0x18003b8f6  neg     rax
0x18003b8f9  sbb     rdi, rdi
0x18003b8fc  and     rdi, rcx
0x18003b8ff  jz      short loc_18003B95C
0x18003b901  cmp     [rbp+0B0h+var_A0], 0
0x18003b906  jz      short loc_18003B924
0x18003b908  mov     rax, gs:30h
0x18003b911  mov     rcx, [rax+1758h]
0x18003b918  mov     rdx, [rcx]
0x18003b91b  mov     rcx, [rbp+0B0h+var_A0]
0x18003b91f  add     rcx, rdx
0x18003b922  jmp     short loc_18003B926
0x18003b924  xor     ecx, ecx
0x18003b926  mov     rax, [rsi+10h]
0x18003b92a  mov     [rcx+20h], rax
0x18003b92e  mov     rax, [rsi+18h]
0x18003b932  mov     [rcx+28h], rax
0x18003b936  mov     rax, [rsi+20h]
0x18003b93a  mov     [rcx+30h], rax
0x18003b93e  mov     rcx, rdi
0x18003b941  mov     rax, [rdi]
0x18003b944  mov     rax, [rax+8]
0x18003b948  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b94d  mov     rcx, rsi; this
0x18003b950  call    ?Release@CPerContext@@QEAAJXZ; CPerContext::Release(void)
0x18003b955  xor     esi, esi
0x18003b957  jmp     loc_18003BA56
0x18003b95c  mov     ecx, 100h; unsigned __int64
0x18003b961  call    ??2CMallocBased@@SAPEAX_KQEAUIMalloc@@@Z; CMallocBased::operator new(unsigned __int64,IMalloc * const)
0x18003b966  mov     r10, rax
0x18003b969  test    rax, rax
0x18003b96c  jz      loc_18003BB2A
0x18003b972  cmp     [rbp+0B0h+var_A0], 0
0x18003b977  jz      short loc_18003B992
0x18003b979  mov     rcx, gs:30h
0x18003b982  mov     rdx, [rcx+1758h]
0x18003b989  mov     r8, [rdx]
0x18003b98c  add     r8, [rbp+0B0h+var_A0]
0x18003b990  jmp     short loc_18003B995
0x18003b992  xor     r8d, r8d; struct CDFBasis *
0x18003b995  cmp     [rbp+0B0h+var_C0], 0
0x18003b99a  jz      short loc_18003B9B5
0x18003b99c  mov     rax, gs:30h
0x18003b9a5  mov     rcx, [rax+1758h]
0x18003b9ac  mov     rdx, [rcx]
0x18003b9af  add     rdx, [rbp+0B0h+var_C0]
0x18003b9b3  jmp     short loc_18003B9B7
0x18003b9b5  xor     edx, edx; struct CPubDocFile *
0x18003b9b7  mov     r9, rsi; struct CPerContext *
0x18003b9ba  mov     rcx, r10; this
0x18003b9bd  call    ??0CExposedDocFile@@QEAA@PEAVCPubDocFile@@PEAVCDFBasis@@PEAVCPerContext@@@Z; CExposedDocFile::CExposedDocFile(CPubDocFile *,CDFBasis *,CPerContext *)
0x18003b9c2  mov     rdi, rax
0x18003b9c5  test    rax, rax
0x18003b9c8  jz      loc_18003BB2A
0x18003b9ce  xor     esi, esi
0x18003b9d0  cmp     [rbp+0B0h+var_A8], rsi
0x18003b9d4  jz      short loc_18003BA2A
0x18003b9d6  mov     rax, gs:30h
0x18003b9df  mov     rcx, [rax+1758h]
0x18003b9e6  mov     rax, [rcx]
0x18003b9e9  add     rax, [rbp+0B0h+var_A8]
0x18003b9ed  jz      short loc_18003BA2A
0x18003b9ef  lea     rcx, [rbp+0B0h+var_A8]
0x18003b9f3  call    ??$VerifyOnUnmarshal@VCMarshalList@@@?$BasedPtr@VCMarshalList@@@@QEBA_NXZ; BasedPtr<CMarshalList>::VerifyOnUnmarshal<CMarshalList>(void)
0x18003b9f8  test    al, al
0x18003b9fa  jz      short loc_18003BA2A
0x18003b9fc  cmp     [rbp+0B0h+var_A8], rsi
0x18003ba00  jz      short loc_18003BA1E
0x18003ba02  mov     rax, gs:30h
0x18003ba0b  mov     rcx, [rax+1758h]
0x18003ba12  mov     rdx, [rcx]
0x18003ba15  mov     rcx, [rbp+0B0h+var_A8]
0x18003ba19  add     rcx, rdx
0x18003ba1c  jmp     short loc_18003BA21
0x18003ba1e  mov     rcx, rsi; this
0x18003ba21  lea     rdx, [rdi+78h]; struct CMarshalList *
0x18003ba25  call    ?AddMarshal@CMarshalList@@QEAAXPEAV1@@Z; CMarshalList::AddMarshal(CMarshalList *)
0x18003ba2a  cmp     [rbp+0B0h+var_C0], rsi
0x18003ba2e  jz      short loc_18003BA4C
0x18003ba30  mov     rax, gs:30h
0x18003ba39  mov     rcx, [rax+1758h]
0x18003ba40  mov     rdx, [rcx]
0x18003ba43  mov     rcx, [rbp+0B0h+var_C0]
0x18003ba47  add     rcx, rdx
0x18003ba4a  jmp     short loc_18003BA4F
0x18003ba4c  mov     rcx, rsi
0x18003ba4f  lock inc dword ptr [rcx+9Ch]
0x18003ba56  mov     r8d, 10h; Size
0x18003ba5c  lea     rdx, _GUID_0000000b_0000_0000_c000_000000000046; Buf2
0x18003ba63  mov     rcx, r13; Buf1
  ... truncated ...
```
