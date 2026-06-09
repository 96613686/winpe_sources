# StgOpenStorageOnILockBytes

- ea: `0x18001eaa0`
- end: `0x18001eeae`
- name: `StgOpenStorageOnILockBytes`
- size: `1038`
- prototype: `HRESULT __stdcall(ILockBytes *plkbyt, IStorage *pstgPriority, DWORD grfMode, SNB snbExclude, DWORD reserved, IStorage **ppstgOpen)`
- caller_count: `3`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x18003d950`
- `0x18004fc90`
- `0x180058f18`

## callees

- `0x180015258`
- `0x180018680`
- `0x180018914`
- `0x18001b89c`
- `0x18001bf68`
- `0x18001c99c`
- `0x18001d820`
- `0x18001d8d8`
- `0x18001e0f8`
- `0x18001eaa0`
- `0x18001eeb4`
- `0x18001eef0`
- `0x18001efe8`
- `0x18001f080`
- `0x18001faf0`
- `0x180020178`
- `0x180060478`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-private-l1-1-0!InternalTlsAllocData` at `0x18001ed8d`
- `api-ms-win-core-com-private-l1-1-0!InternalTlsAllocData` at `0x18001ed8d`

## pseudocode

```c
HRESULT __stdcall StgOpenStorageOnILockBytes(
        ILockBytes *plkbyt,
        IStorage *pstgPriority,
        DWORD grfMode,
        SNB snbExclude,
        DWORD reserved,
        IStorage **ppstgOpen)
{
  struct CExposedDocFile *v6; // rdi
  struct CSmAllocator *TlsSmAllocator; // rax
  HRESULT inited; // ebx
  struct ILockBytesVtbl *lpVtbl; // rax
  struct CSmAllocator *v14; // rax
  struct CSmAllocator *v15; // rax
  __int64 v16; // r8
  struct CSmAllocator *v17; // rdx
  int v18; // ecx
  __int64 v19; // rax
  int v20; // eax
  CPerContext *v21; // rax
  struct IMalloc *v22; // r12
  CPerContext *v23; // rax
  struct CPerContext *v24; // r14
  unsigned int v25; // edx
  unsigned int v26; // eax
  bool v27; // sf
  struct CPerContext *v29; // rbx
  unsigned int v30; // eax
  __int64 v31; // r10
  struct _GUID *v32; // [rsp+38h] [rbp-C8h]
  struct CExposedDocFile *v33; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v34[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v35; // [rsp+58h] [rbp-A8h] BYREF
  struct IMalloc *v36; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v37[8]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v38; // [rsp+78h] [rbp-88h]
  __int128 v39; // [rsp+80h] [rbp-80h]
  __int64 v40; // [rsp+90h] [rbp-70h]
  int v41; // [rsp+98h] [rbp-68h]
  __int64 v42; // [rsp+A0h] [rbp-60h]
  int v43; // [rsp+A8h] [rbp-58h]
  __int64 v44; // [rsp+B0h] [rbp-50h]
  __int64 v45; // [rsp+B8h] [rbp-48h]
  __int64 v46; // [rsp+C0h] [rbp-40h]
  __int64 v47; // [rsp+C8h] [rbp-38h]
  __int64 v48; // [rsp+D0h] [rbp-30h]
  int v49; // [rsp+D8h] [rbp-28h]
  __int128 v50; // [rsp+E0h] [rbp-20h]
  int v51; // [rsp+F0h] [rbp-10h]

  v36 = 0;
  v6 = 0;
  v33 = 0;
  v38 = 0;
  v44 = 0;
  v50 = 0;
  TlsSmAllocator = GetTlsSmAllocator();
  v47 = *((_QWORD *)TlsSmAllocator + 1);
  v48 = *((_QWORD *)TlsSmAllocator + 2);
  v49 = *((_DWORD *)TlsSmAllocator + 9);
  v40 = 0;
  v39 = 0;
  v41 = 0;
  v43 = 1;
  v42 = 0;
  v45 = 0;
  v46 = -1;
  v51 = 0;
  if ( !ppstgOpen
    || (*ppstgOpen = 0, !(unsigned int)IsValidStgInterface(plkbyt))
    || pstgPriority && !(unsigned int)IsValidStgInterface(pstgPriority) )
  {
    inited = -2147287031;
    goto LABEL_22;
  }
  inited = VerifyPerms(grfMode, 1);
  if ( inited < 0 )
    goto LABEL_22;
  if ( (grfMode & 0x21000) != 0 )
  {
    inited = -2147286785;
    goto LABEL_22;
  }
  if ( (grfMode & 0x4000000) != 0 )
  {
    inited = -2147287039;
    goto LABEL_22;
  }
  if ( !snbExclude )
    goto LABEL_8;
  if ( (grfMode & 3) != 2 )
  {
    inited = -2147287035;
    goto LABEL_22;
  }
  inited = ValidateSNB(snbExclude);
  if ( inited >= 0 )
  {
LABEL_8:
    if ( reserved )
    {
      inited = -2147286953;
      goto LABEL_22;
    }
    if ( pstgPriority )
    {
      inited = ((__int64 (__fastcall *)(IStorage *))pstgPriority->lpVtbl->Release)(pstgPriority);
      if ( inited < 0 )
        goto LABEL_22;
    }
    v34[0] = NtCurrentTeb()->ReservedForOle;
    if ( !v34[0] )
    {
      inited = InternalTlsAllocData(v34);
      if ( inited < 0 )
        goto LABEL_22;
    }
    lpVtbl = plkbyt->lpVtbl;
    v35 = 0;
    if ( ((__int64 (__fastcall *)(ILockBytes *, GUID *, __int64 *))lpVtbl->QueryInterface)(
           plkbyt,
           &IID_IDfReserved1,
           &v35) >= 0
      && plkbyt[7].lpVtbl )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
      v29 = (struct CPerContext *)plkbyt[7].lpVtbl;
      CSafeMultiHeap::CSafeMultiHeap((CSafeMultiHeap *)v34, v29);
      Microsoft::WRL::ComPtr<CExposedDocFile>::InternalRelease(&v33);
      v30 = ModeToDFlags(grfMode);
      inited = DfFromLB(v29, plkbyt, 0, v30, *(_DWORD *)(v31 + 36), 0, &v33, v32);
      v27 = inited < 0;
LABEL_19:
      if ( v27 )
      {
        CSafeMultiHeap::~CSafeMultiHeap((CSafeMultiHeap *)v34);
        v6 = v33;
      }
      else
      {
        CSafeMultiHeap::~CSafeMultiHeap((CSafeMultiHeap *)v34);
        v6 = 0;
        *ppstgOpen = (IStorage *)v33;
        ((void (__fastcall *)(ILockBytes *))plkbyt->lpVtbl->AddRef)(plkbyt);
      }
      goto LABEL_22;
    }
    inited = DfCreateSharedAllocator(&v36, 1);
    if ( inited < 0 )
      goto LABEL_22;
    v14 = GetTlsSmAllocator();
    v47 = *((_QWORD *)v14 + 1);
    v48 = *((_QWORD *)v14 + 2);
    v49 = *((_DWORD *)v14 + 9);
    v15 = GetTlsSmAllocator();
    v16 = v48;
    v17 = v15;
    v18 = v49;
    v34[0] = v15;
    v19 = v47;
    *((_QWORD *)v17 + 1) = v47;
    *((_QWORD *)v17 + 2) = v16;
    if ( v19 )
      v20 = *(_DWORD *)(v19 + 16) - 24;
    else
      v20 = 0;
    *((_DWORD *)v17 + 8) = v20;
    *((_DWORD *)v17 + 9) = v18;
    *(_QWORD *)NtCurrentTeb()->ReservedForOle = v16;
    v34[1] = *((_QWORD *)v17 + 3);
    *((_QWORD *)v17 + 3) = v37;
    v21 = (CPerContext *)CMallocBased::operator new(0x88u, (struct IMalloc *const)v17);
    if ( v21 && (v22 = v36, v23 = CPerContext::CPerContext(v21, v36), (v24 = v23) != 0) )
    {
      inited = CPerContext::InitNewContext(v23, 0);
      if ( inited >= 0 )
      {
        Microsoft::WRL::ComPtr<CExposedDocFile>::InternalRelease(&v33);
        v26 = ModeToDFlags(grfMode);
        inited = DfFromLB(v24, plkbyt, 0, v26, 0, snbExclude, &v33, v32);
        ((void (__fastcall *)(struct IMalloc *))v22->lpVtbl->Release)(v22);
        CPerContext::Release(v24);
        v27 = inited < 0;
        goto LABEL_19;
      }
      CPerContext::`scalar deleting destructor'(v24, v25);
    }
    else
    {
      inited = -2147287032;
    }
    CSafeMultiHeap::~CSafeMultiHeap((CSafeMultiHeap *)v34);
  }
LABEL_22:
  CPerContext::~CPerContext((CPerContext *)v37);
  if ( v6 )
    (*(void (__fastcall **)(struct CExposedDocFile *))(*(_QWORD *)v6 + 16LL))(v6);
  return inited;
}

```

## disassembly

```asm
0x18001eaa0  push    rbp
0x18001eaa2  push    rbx
0x18001eaa3  push    rsi
0x18001eaa4  push    rdi
0x18001eaa5  push    r12
0x18001eaa7  push    r13
0x18001eaa9  push    r14
0x18001eaab  push    r15
0x18001eaad  lea     rbp, [rsp-8]
0x18001eab2  sub     rsp, 108h
0x18001eab9  xor     r12d, r12d
0x18001eabc  xorps   xmm0, xmm0
0x18001eabf  mov     [rsp+140h+var_E0], r12
0x18001eac4  mov     edi, r12d
0x18001eac7  mov     [rsp+140h+var_100], r12
0x18001eacc  mov     r13, r9
0x18001eacf  mov     [rsp+140h+var_C8], r12
0x18001ead4  mov     r15d, r8d
0x18001ead7  mov     [rbp+40h+var_90], r12
0x18001eadb  mov     r14, rdx
0x18001eade  movdqa  [rbp+40h+var_60], xmm0
0x18001eae3  mov     rsi, rcx
0x18001eae6  call    ?GetTlsSmAllocator@@YAAEAVCSmAllocator@@XZ; GetTlsSmAllocator(void)
0x18001eaeb  xorps   xmm0, xmm0
0x18001eaee  lea     ebx, [r12+1]
0x18001eaf3  mov     r8, [rax+8]
0x18001eaf7  mov     [rbp+40h+var_78], r8
0x18001eafb  mov     rcx, [rax+10h]
0x18001eaff  mov     [rbp+40h+var_70], rcx
0x18001eb03  mov     eax, [rax+24h]
0x18001eb06  mov     [rbp+40h+var_68], eax
0x18001eb09  mov     rax, [rbp+40h+ppstgOpen]
0x18001eb0d  mov     [rbp+40h+var_B0], r12
0x18001eb11  movdqa  [rbp+40h+var_C0], xmm0
0x18001eb16  mov     [rbp+40h+var_A8], r12d
0x18001eb1a  mov     [rbp+40h+var_98], ebx
0x18001eb1d  mov     [rbp+40h+var_A0], r12
0x18001eb21  mov     [rbp+40h+var_88], r12
0x18001eb25  mov     [rbp+40h+var_80], 0FFFFFFFFFFFFFFFFh
0x18001eb2d  mov     [rbp+40h+var_50], r12d
0x18001eb31  test    rax, rax
0x18001eb34  jz      loc_18001ED35
0x18001eb3a  mov     rcx, rsi; void *
0x18001eb3d  mov     [rax], r12
0x18001eb40  call    ?IsValidStgInterface@@YAHPEAX@Z; IsValidStgInterface(void *)
0x18001eb45  test    eax, eax
0x18001eb47  jz      loc_18001ED35
0x18001eb4d  test    r14, r14
0x18001eb50  jnz     loc_18001EE26
0x18001eb56  mov     edx, ebx; int
0x18001eb58  mov     ecx, r15d; unsigned int
0x18001eb5b  call    ?VerifyPerms@@YAJKH@Z; VerifyPerms(ulong,int)
0x18001eb60  mov     ebx, eax
0x18001eb62  test    eax, eax
0x18001eb64  js      loc_18001ED3A
0x18001eb6a  test    r15d, 21000h
0x18001eb71  jnz     loc_18001EE3B
0x18001eb77  bt      r15d, 1Ah
0x18001eb7c  jb      loc_18001EE45
0x18001eb82  test    r13, r13
0x18001eb85  jnz     loc_18001EE4F
0x18001eb8b  cmp     [rbp+40h+reserved], r12d
0x18001eb8f  jnz     loc_18001EE79
0x18001eb95  test    r14, r14
0x18001eb98  jnz     loc_18001EE83
0x18001eb9e  mov     rax, gs:30h
0x18001eba7  mov     rcx, [rax+1758h]
0x18001ebae  mov     [rsp+140h+var_F8], rcx
0x18001ebb3  test    rcx, rcx
0x18001ebb6  jz      loc_18001ED88
0x18001ebbc  mov     rax, [rsi]
0x18001ebbf  lea     r8, [rsp+140h+var_E8]
0x18001ebc4  lea     rdx, IID_IDfReserved1
0x18001ebcb  mov     [rsp+140h+var_E8], r12
0x18001ebd0  mov     rcx, rsi
0x18001ebd3  mov     rax, [rax]
0x18001ebd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ebdb  test    eax, eax
0x18001ebdd  jns     loc_18001ED9F
0x18001ebe3  mov     edx, 1; int
0x18001ebe8  lea     rcx, [rsp+140h+var_E0]; struct IMalloc **
0x18001ebed  call    ?DfCreateSharedAllocator@@YAJPEAPEAUIMalloc@@H@Z; DfCreateSharedAllocator(IMalloc * *,int)
0x18001ebf2  mov     ebx, eax
0x18001ebf4  test    eax, eax
0x18001ebf6  js      loc_18001ED3A
0x18001ebfc  call    ?GetTlsSmAllocator@@YAAEAVCSmAllocator@@XZ; GetTlsSmAllocator(void)
0x18001ec01  mov     rcx, [rax+8]
0x18001ec05  mov     [rbp+40h+var_78], rcx
0x18001ec09  mov     rcx, [rax+10h]
0x18001ec0d  mov     [rbp+40h+var_70], rcx
0x18001ec11  mov     eax, [rax+24h]
0x18001ec14  mov     [rbp+40h+var_68], eax
0x18001ec17  call    ?GetTlsSmAllocator@@YAAEAVCSmAllocator@@XZ; GetTlsSmAllocator(void)
0x18001ec1c  mov     r8, [rbp+40h+var_70]
0x18001ec20  mov     rdx, rax; struct IMalloc *
0x18001ec23  mov     ecx, [rbp+40h+var_68]
0x18001ec26  mov     [rsp+140h+var_F8], rax
0x18001ec2b  mov     rax, [rbp+40h+var_78]
0x18001ec2f  mov     [rdx+8], rax
0x18001ec33  mov     [rdx+10h], r8
0x18001ec37  test    rax, rax
0x18001ec3a  jz      loc_18001ED74
0x18001ec40  mov     eax, [rax+10h]
0x18001ec43  sub     eax, 18h
0x18001ec46  mov     [rdx+20h], eax
0x18001ec49  mov     [rdx+24h], ecx
0x18001ec4c  mov     rax, gs:30h
0x18001ec55  mov     rcx, [rax+1758h]
0x18001ec5c  mov     [rcx], r8
0x18001ec5f  mov     ecx, 88h; unsigned __int64
0x18001ec64  mov     rax, [rdx+18h]
0x18001ec68  mov     [rsp+140h+var_F0], rax
0x18001ec6d  lea     rax, [rsp+140h+var_D0]
0x18001ec72  mov     [rdx+18h], rax
0x18001ec76  call    ??2CMallocBased@@SAPEAX_KQEAUIMalloc@@@Z; CMallocBased::operator new(unsigned __int64,IMalloc * const)
0x18001ec7b  test    rax, rax
0x18001ec7e  jz      loc_18001ED63
0x18001ec84  mov     r12, [rsp+140h+var_E0]
0x18001ec89  mov     rcx, rax; this
0x18001ec8c  mov     rdx, r12; struct IMalloc *
0x18001ec8f  call    ??0CPerContext@@QEAA@PEAUIMalloc@@@Z; CPerContext::CPerContext(IMalloc *)
0x18001ec94  mov     r14, rax
0x18001ec97  test    rax, rax
0x18001ec9a  jz      loc_18001ED63
0x18001eca0  xor     edx, edx; int
0x18001eca2  mov     rcx, rax; this
0x18001eca5  call    ?InitNewContext@CPerContext@@QEAAJH@Z; CPerContext::InitNewContext(int)
0x18001ecaa  mov     ebx, eax
0x18001ecac  test    eax, eax
0x18001ecae  js      loc_18001EEA1
0x18001ecb4  lea     rcx, [rsp+140h+var_100]
0x18001ecb9  call    ?InternalRelease@?$ComPtr@VCExposedDocFile@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CExposedDocFile>::InternalRelease(void)
0x18001ecbe  mov     ecx, r15d; unsigned int
0x18001ecc1  call    ?ModeToDFlags@@YAKK@Z; ModeToDFlags(ulong)
0x18001ecc6  mov     r9d, eax; unsigned int
0x18001ecc9  xor     r8d, r8d; int
0x18001eccc  lea     rax, [rsp+140h+var_100]
0x18001ecd1  mov     rdx, rsi; struct ILockBytes *
0x18001ecd4  mov     [rsp+140h+var_110], rax; struct CExposedDocFile **
0x18001ecd9  mov     rcx, r14; this
0x18001ecdc  mov     [rsp+140h+var_118], r13; unsigned __int16 **
0x18001ece1  mov     [rsp+140h+var_120], edi; unsigned int
0x18001ece5  call    ?DfFromLB@@YAJPEAVCPerContext@@PEAUILockBytes@@HKKPEAPEAGPEAPEAVCExposedDocFile@@PEAU_GUID@@@Z; DfFromLB(CPerContext *,ILockBytes *,int,ulong,ulong,ushort * *,CExposedDocFile * *,_GUID *)
0x18001ecea  mov     ebx, eax
0x18001ecec  mov     rcx, r12
0x18001ecef  mov     rax, [r12]
0x18001ecf3  mov     rax, [rax+10h]
0x18001ecf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ecfc  mov     rcx, r14; this
0x18001ecff  call    ?Release@CPerContext@@QEAAJXZ; CPerContext::Release(void)
0x18001ed04  xor     r12d, r12d
0x18001ed07  test    ebx, ebx
0x18001ed09  lea     rcx, [rsp+140h+var_F8]; this
0x18001ed0e  js      short loc_18001ED7C
0x18001ed10  call    ??1CSafeMultiHeap@@QEAA@XZ; CSafeMultiHeap::~CSafeMultiHeap(void)
0x18001ed15  mov     rcx, [rbp+40h+ppstgOpen]
0x18001ed19  mov     rdi, r12
0x18001ed1c  mov     rax, [rsp+140h+var_100]
0x18001ed21  mov     [rcx], rax
0x18001ed24  mov     rcx, rsi
0x18001ed27  mov     rax, [rsi]
0x18001ed2a  mov     rax, [rax+8]
0x18001ed2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed33  jmp     short loc_18001ED3A
0x18001ed35  mov     ebx, 80030009h
0x18001ed3a  lea     rcx, [rsp+140h+var_D0]; this
0x18001ed3f  call    ??1CPerContext@@QEAA@XZ; CPerContext::~CPerContext(void)
0x18001ed44  test    rdi, rdi
0x18001ed47  jnz     loc_18001EE12
0x18001ed4d  mov     eax, ebx
0x18001ed4f  add     rsp, 108h
0x18001ed56  pop     r15
0x18001ed58  pop     r14
0x18001ed5a  pop     r13
0x18001ed5c  pop     r12
0x18001ed5e  pop     rdi
0x18001ed5f  pop     rsi
0x18001ed60  pop     rbx
0x18001ed61  pop     rbp
0x18001ed62  retn
0x18001ed63  mov     ebx, 80030008h
0x18001ed68  lea     rcx, [rsp+140h+var_F8]; this
0x18001ed6d  call    ??1CSafeMultiHeap@@QEAA@XZ; CSafeMultiHeap::~CSafeMultiHeap(void)
0x18001ed72  jmp     short loc_18001ED3A
0x18001ed74  mov     eax, r12d
0x18001ed77  jmp     loc_18001EC46
0x18001ed7c  call    ??1CSafeMultiHeap@@QEAA@XZ; CSafeMultiHeap::~CSafeMultiHeap(void)
0x18001ed81  mov     rdi, [rsp+140h+var_100]
0x18001ed86  jmp     short loc_18001ED3A
0x18001ed88  lea     rcx, [rsp+140h+var_F8]
0x18001ed8d  call    cs:__imp_InternalTlsAllocData
0x18001ed93  mov     ebx, eax
0x18001ed95  test    eax, eax
0x18001ed97  jns     loc_18001EBBC
0x18001ed9d  jmp     short loc_18001ED3A
0x18001ed9f  cmp     [rsi+38h], r12
0x18001eda3  jz      loc_18001EBE3
0x18001eda9  mov     rcx, [rsp+140h+var_E8]
0x18001edae  mov     rax, [rcx]
0x18001edb1  mov     rax, [rax+10h]
0x18001edb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001edba  mov     rbx, [rsi+38h]
0x18001edbe  lea     rcx, [rsp+140h+var_F8]; this
0x18001edc3  mov     rdx, rbx; struct CPerContext *
0x18001edc6  call    ??0CSafeMultiHeap@@QEAA@PEAVCPerContext@@@Z; CSafeMultiHeap::CSafeMultiHeap(CPerContext *)
0x18001edcb  lea     rcx, [rsp+140h+var_100]
0x18001edd0  call    ?InternalRelease@?$ComPtr@VCExposedDocFile@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CExposedDocFile>::InternalRelease(void)
0x18001edd5  mov     r10, [rsi+30h]
0x18001edd9  mov     ecx, r15d; unsigned int
0x18001eddc  call    ?ModeToDFlags@@YAKK@Z; ModeToDFlags(ulong)
0x18001ede1  mov     r9d, eax; unsigned int
0x18001ede4  xor     r8d, r8d; int
0x18001ede7  lea     rax, [rsp+140h+var_100]
0x18001edec  mov     rdx, rsi; struct ILockBytes *
0x18001edef  mov     [rsp+140h+var_110], rax; struct CExposedDocFile **
0x18001edf4  mov     rcx, rbx; this
0x18001edf7  mov     eax, [r10+24h]
0x18001edfb  mov     [rsp+140h+var_118], r12; unsigned __int16 **
0x18001ee00  mov     [rsp+140h+var_120], eax; unsigned int
0x18001ee04  call    ?DfFromLB@@YAJPEAVCPerContext@@PEAUILockBytes@@HKKPEAPEAGPEAPEAVCExposedDocFile@@PEAU_GUID@@@Z; DfFromLB(CPerContext *,ILockBytes *,int,ulong,ulong,ushort * *,CExposedDocFile * *,_GUID *)
0x18001ee09  mov     ebx, eax
0x18001ee0b  test    eax, eax
0x18001ee0d  jmp     loc_18001ED09
0x18001ee12  mov     rax, [rdi]
0x18001ee15  mov     rcx, rdi
0x18001ee18  mov     rax, [rax+10h]
0x18001ee1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee21  jmp     loc_18001ED4D
0x18001ee26  mov     rcx, r14; void *
0x18001ee29  call    ?IsValidStgInterface@@YAHPEAX@Z; IsValidStgInterface(void *)
0x18001ee2e  test    eax, eax
0x18001ee30  jz      loc_18001ED35
0x18001ee36  jmp     loc_18001EB56
0x18001ee3b  mov     ebx, 800300FFh
0x18001ee40  jmp     loc_18001ED3A
0x18001ee45  mov     ebx, 80030001h
0x18001ee4a  jmp     loc_18001ED3A
0x18001ee4f  mov     eax, r15d
0x18001ee52  and     al, 3
0x18001ee54  cmp     al, 2
0x18001ee56  jz      short loc_18001EE62
0x18001ee58  mov     ebx, 80030005h
0x18001ee5d  jmp     loc_18001ED3A
0x18001ee62  mov     rcx, r13; unsigned __int16 **
0x18001ee65  call    ?ValidateSNB@@YAJPEAPEAG@Z; ValidateSNB(ushort * *)
0x18001ee6a  mov     ebx, eax
0x18001ee6c  test    eax, eax
0x18001ee6e  js      loc_18001ED3A
0x18001ee74  jmp     loc_18001EB8B
0x18001ee79  mov     ebx, 80030057h
0x18001ee7e  jmp     loc_18001ED3A
0x18001ee83  mov     rax, [r14]
0x18001ee86  mov     rcx, r14
0x18001ee89  mov     rax, [rax+10h]
0x18001ee8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee92  mov     ebx, eax
0x18001ee94  test    eax, eax
0x18001ee96  js      loc_18001ED3A
0x18001ee9c  jmp     loc_18001EB9E
0x18001eea1  mov     rcx, r14; this
0x18001eea4  call    ??_GCPerContext@@QEAAPEAXI@Z; CPerContext::`scalar deleting destructor'(uint)
0x18001eea9  jmp     loc_18001ED68
```
