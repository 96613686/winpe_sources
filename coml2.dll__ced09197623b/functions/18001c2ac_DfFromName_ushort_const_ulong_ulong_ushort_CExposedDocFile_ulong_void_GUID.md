# DfFromName(ushort const *,ulong,ulong,ushort * *,CExposedDocFile * *,ulong *,void *,_GUID *)

- ea: `0x18001c2ac`
- end: `0x18001c996`
- name: `?DfFromName@@YAJPEBGKKPEAPEAGPEAPEAVCExposedDocFile@@PEAKPEAXPEAU_GUID@@@Z`
- size: `1770`
- prototype: `int(const unsigned __int16 *, unsigned int, unsigned int, unsigned __int16 **, struct CExposedDocFile **, unsigned int *, void *, struct _GUID *)`
- caller_count: `2`
- callee_count: `22`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18001f7e0`
- `0x180039a04`

## callees

- `0x18000cdd8`
- `0x180018680`
- `0x180018914`
- `0x18001b89c`
- `0x18001bf68`
- `0x18001c268`
- `0x18001c2ac`
- `0x18001c99c`
- `0x18001d820`
- `0x18001d8d8`
- `0x18001daa0`
- `0x18001db94`
- `0x18001defc`
- `0x18001e0f8`
- `0x18001efe8`
- `0x18001f080`
- `0x180020178`
- `0x18002db70`
- `0x18002f2e0`
- `0x180035e0c`
- `0x18004bbe0`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001c411`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001c411`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c4f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c6f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c4f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c6f7`

## pseudocode

```c
__int64 __fastcall DfFromName(
        const unsigned __int16 *a1,
        unsigned int a2,
        unsigned int a3,
        unsigned __int16 **a4,
        struct CExposedDocFile **a5,
        unsigned int *a6,
        void *a7,
        struct IMalloc *a8)
{
  struct CSmAllocator *TlsSmAllocator; // rax
  struct IMalloc *v12; // rdx
  int inited; // edi
  _WORD *v14; // rsi
  CFileStream *v15; // rax
  struct IMalloc *v16; // r12
  CFileStream *v17; // rax
  CFileStream *v18; // rbx
  int v19; // eax
  struct IMalloc *v20; // rdx
  unsigned int v21; // edi
  __int64 v22; // rax
  __int64 (__fastcall *v23)(CFileStream *, _QWORD, _WORD *, _QWORD, __int64 *); // rax
  int v24; // eax
  char v25; // r13
  CSmAllocator *v26; // rax
  struct CSmAllocator *v27; // rax
  unsigned __int16 v29; // ax
  struct CGlobalFileStream *v30; // rcx
  struct CSmAllocator *v31; // rax
  unsigned __int8 *v32; // rcx
  struct CSharedMemoryBlock *v33; // r13
  struct IMalloc *const v34; // rdx
  CFileStream *v35; // rax
  CFileStream *v36; // rax
  CFileStream *v37; // r14
  struct CGlobalFileStream *v38; // rdx
  struct CSmAllocator *v39; // rax
  unsigned __int8 *v40; // r8
  int v41; // ecx
  CSmAllocator *v42; // rax
  struct CSmAllocator *v43; // rax
  CPerContext *v44; // rax
  CPerContext *v45; // rax
  CPerContext *v46; // r14
  unsigned int v47; // edx
  struct CSmAllocator *v48; // rax
  struct CSmAllocator *v49; // rax
  __int64 v50; // rcx
  struct CSmAllocator *v51; // rdx
  __int64 v52; // r8
  int v53; // eax
  int v54; // ecx
  struct CSmAllocator *v55; // rax
  CSmAllocator *v56; // rax
  __int64 v57; // r8
  __int64 v58; // rcx
  __int64 v59; // [rsp+48h] [rbp-C0h] BYREF
  unsigned int v60[2]; // [rsp+50h] [rbp-B8h]
  struct IMalloc *v61; // [rsp+58h] [rbp-B0h] BYREF
  unsigned __int8 *v62; // [rsp+60h] [rbp-A8h]
  unsigned __int64 v63; // [rsp+68h] [rbp-A0h] BYREF
  struct CGlobalFileStream *v64[3]; // [rsp+70h] [rbp-98h] BYREF
  _BYTE v65[8]; // [rsp+88h] [rbp-80h] BYREF
  __int64 v66; // [rsp+90h] [rbp-78h]
  __int128 v67; // [rsp+98h] [rbp-70h]
  __int64 v68; // [rsp+A8h] [rbp-60h]
  int v69; // [rsp+B0h] [rbp-58h]
  __int64 v70; // [rsp+B8h] [rbp-50h]
  int v71; // [rsp+C0h] [rbp-48h]
  __int64 v72; // [rsp+C8h] [rbp-40h]
  __int64 v73; // [rsp+D0h] [rbp-38h]
  __int64 v74; // [rsp+D8h] [rbp-30h]
  __int64 v75; // [rsp+E0h] [rbp-28h]
  __int64 v76; // [rsp+E8h] [rbp-20h]
  int v77; // [rsp+F0h] [rbp-18h]
  __int128 v78; // [rsp+F8h] [rbp-10h]
  int v79; // [rsp+108h] [rbp+0h]
  unsigned int v80; // [rsp+160h] [rbp+58h]

  v80 = a2;
  a8 = 0;
  v66 = 0;
  v72 = 0;
  v78 = 0;
  TlsSmAllocator = GetTlsSmAllocator();
  v75 = *((_QWORD *)TlsSmAllocator + 1);
  v76 = *((_QWORD *)TlsSmAllocator + 2);
  v77 = *((_DWORD *)TlsSmAllocator + 9);
  v68 = 0;
  v67 = 0;
  v69 = 0;
  v71 = 1;
  v70 = 0;
  v73 = 0;
  v74 = -1;
  v79 = 0;
  inited = DfCreateSharedAllocator(&a8, a2 & 0x80000);
  if ( inited < 0 )
    goto LABEL_24;
  v14 = 0;
  v15 = (CFileStream *)CMallocBased::operator new(0x78u, v12);
  v16 = a8;
  if ( !v15 || (v17 = CFileStream::CFileStream(v15, a8), (v18 = v17) == 0) )
  {
    inited = -2147287032;
LABEL_22:
    v26 = GetTlsSmAllocator();
    CSmAllocator::Uninit(v26);
    v27 = GetTlsSmAllocator();
    *((_QWORD *)v27 + 1) = 0;
    *((_QWORD *)v27 + 2) = 0;
    *((_QWORD *)v27 + 4) = 0;
    *(_QWORD *)NtCurrentTeb()->ReservedForOle = 0;
    *((_QWORD *)v27 + 3) = 0;
    ((void (__fastcall *)(struct IMalloc *))v16->lpVtbl->Release)(v16);
    if ( v14 )
      CoTaskMemFree(v14);
    goto LABEL_24;
  }
  inited = CFileStream::InitGlobal(v17, a3 & 0xFFFFFBFC, a2);
  if ( inited < 0 )
    goto LABEL_21;
  v19 = CFileStream::InitWorker(v18, a1, 0, a7);
  inited = v19;
  if ( v19 < 0 || (a3 & 4) == 0 && a1 )
  {
    LODWORD(a8) = 0;
    if ( v19 == -2147286960 )
    {
      if ( (a3 & 0x403) == 0 )
        goto LABEL_21;
      *(_DWORD *)(*((_QWORD *)v18 + 6) + 36LL) = a3 & 0xFFFFFBF8;
      inited = CFileStream::InitWorker(v18, a1, 0, a7);
      LODWORD(a8) = 0;
    }
    if ( inited >= 0 )
      goto LABEL_10;
LABEL_21:
    (*(void (__fastcall **)(CFileStream *))(*(_QWORD *)v18 + 16LL))(v18);
    goto LABEL_22;
  }
  LODWORD(a8) = 1;
LABEL_10:
  if ( (a3 & 4) != 0 )
    goto LABEL_38;
  if ( (a3 & 0x200) != 0 )
    v21 = (*(__int64 (__fastcall **)(__int64))(*((_QWORD *)v18 + 1) + 56LL))((__int64)v18 + 8);
  else
    v21 = 512;
  v14 = CoTaskMemAlloc(v21);
  if ( !v14 )
    goto LABEL_49;
  v22 = *(_QWORD *)v18;
  *(_QWORD *)v60 = 0;
  v23 = *(__int64 (__fastcall **)(CFileStream *, _QWORD, _WORD *, _QWORD, __int64 *))(v22 + 24);
  LODWORD(v59) = 0;
  inited = v23(v18, 0, v14, v21, &v59);
  if ( inited < 0 )
  {
LABEL_18:
    v25 = v80;
LABEL_19:
    if ( (_DWORD)a8 || (a3 & 4) != 0 && (v25 & 2) == 0 )
      CFileStream::Delete(v18);
    goto LABEL_21;
  }
  if ( (unsigned int)v59 < 0x200 || (v24 = CMSFHeader::Validate((CMSFHeader *)v14), inited = v24, v24 == -2147286789) )
  {
    inited = -2147286960;
    goto LABEL_18;
  }
  if ( v24 < 0 )
    goto LABEL_18;
  v29 = v14[15];
  if ( v29 > 9u )
  {
    v30 = (struct CGlobalFileStream *)*((_QWORD *)v18 + 6);
    v80 |= 0x80000u;
    a3 |= (v29 & 0xF) << 12;
    v61 = 0;
    v64[0] = v30;
    v31 = GetTlsSmAllocator();
    v32 = (unsigned __int8 *)*((_QWORD *)v31 + 2);
    v33 = (struct CSharedMemoryBlock *)*((_QWORD *)v31 + 1);
    LODWORD(v31) = *((_DWORD *)v31 + 9);
    v62 = v32;
    v60[0] = (unsigned int)v31;
    inited = DfCreateSharedAllocator(&v61, 1);
    if ( inited >= 0 )
    {
      ((void (__fastcall *)(struct IMalloc *))v16->lpVtbl->Release)(v16);
      v16 = v61;
      v35 = (CFileStream *)CMallocBased::operator new(0x78u, v34);
      if ( v35 && (v36 = CFileStream::CFileStream(v35, v16), (v37 = v36) != 0) )
      {
        inited = CFileStream::InitGlobal(v36, a3 & 0xFFFFFBFC, v80);
        if ( inited >= 0 )
        {
          v38 = v64[0];
          *((_QWORD *)v37 + 8) = *((_QWORD *)v18 + 8);
          *((_QWORD *)v37 + 12) = *((_QWORD *)v18 + 12);
          *((_QWORD *)v37 + 13) = *((_QWORD *)v18 + 13);
          *((_DWORD *)v37 + 28) = *((_DWORD *)v18 + 28);
          *((_QWORD *)v18 + 8) = -1;
          *((_QWORD *)v18 + 12) = 0;
          *((_QWORD *)v18 + 13) = 0;
          *((_DWORD *)v18 + 28) = 0;
          CGlobalFileStream::InitFromGlobalFileStream(*((CGlobalFileStream **)v37 + 6), v38);
          v39 = GetTlsSmAllocator();
          v40 = v62;
          *((_QWORD *)v39 + 1) = v33;
          *((_QWORD *)v39 + 2) = v40;
          if ( v33 )
            v41 = *((_DWORD *)v33 + 4) - 24;
          else
            v41 = 0;
          *((_DWORD *)v39 + 9) = v60[0];
          *((_DWORD *)v39 + 8) = v41;
          *(_QWORD *)NtCurrentTeb()->ReservedForOle = v40;
          *((_QWORD *)v39 + 3) = 0;
          v42 = GetTlsSmAllocator();
          CSmAllocator::Uninit(v42);
          v43 = GetTlsSmAllocator();
          v18 = v37;
          *((_QWORD *)v43 + 1) = 0;
          *((_QWORD *)v43 + 2) = 0;
          *((_QWORD *)v43 + 4) = 0;
          *(_QWORD *)NtCurrentTeb()->ReservedForOle = 0;
          *((_QWORD *)v43 + 3) = 0;
          goto LABEL_35;
        }
        (*(void (__fastcall **)(CFileStream *))(*(_QWORD *)v37 + 16LL))(v37);
      }
      else
      {
        inited = -2147287032;
      }
    }
    v56 = GetTlsSmAllocator();
    CSmAllocator::SetState(v56, v33, v62, v60[0], 0, 0);
    goto LABEL_18;
  }
LABEL_35:
  v63 = 0;
  inited = (*(__int64 (__fastcall **)(__int64, unsigned __int64 *))(*((_QWORD *)v18 + 1) + 48LL))(
             (__int64)v18 + 8,
             &v63);
  if ( inited < 0 )
    goto LABEL_18;
  inited = CMSFHeader::CheckSectorsAgainstFileSize((CMSFHeader *)v14, v63, 0);
  if ( inited < 0 )
    goto LABEL_18;
  CoTaskMemFree(v14);
LABEL_38:
  v44 = (CPerContext *)CMallocBased::operator new(0x88u, v20);
  if ( !v44 || (v45 = CPerContext::CPerContext(v44, v16), (v46 = v45) == 0) )
  {
    v14 = 0;
LABEL_49:
    inited = -2147287032;
    goto LABEL_18;
  }
  inited = CPerContext::InitNewContext(v45, (a3 >> 2) & 1);
  if ( inited < 0 )
  {
    v14 = 0;
    CPerContext::`scalar deleting destructor'(v46, v47);
    goto LABEL_18;
  }
  v48 = GetTlsSmAllocator();
  v75 = *((_QWORD *)v48 + 1);
  v76 = *((_QWORD *)v48 + 2);
  v77 = *((_DWORD *)v48 + 9);
  v49 = GetTlsSmAllocator();
  v50 = v75;
  v51 = v49;
  v52 = v76;
  v53 = v77;
  *((_QWORD *)v51 + 1) = v75;
  *((_QWORD *)v51 + 2) = v52;
  if ( v50 )
    v54 = *(_DWORD *)(v50 + 16) - 24;
  else
    v54 = 0;
  *((_DWORD *)v51 + 8) = v54;
  *((_DWORD *)v51 + 9) = v53;
  *(_QWORD *)NtCurrentTeb()->ReservedForOle = v52;
  *((_QWORD *)v51 + 3) = v65;
  CSafeMultiHeap::CSafeMultiHeap((CSafeMultiHeap *)v64, v46);
  v25 = v80;
  inited = DfFromLB(v46, (struct ILockBytes *)v18, 1, v80, a3, a4, a5);
  CPerContext::Release(v46);
  if ( inited < 0 )
  {
    CSafeMultiHeap::~CSafeMultiHeap((CSafeMultiHeap *)v64);
    v14 = 0;
    goto LABEL_19;
  }
  if ( a6 )
  {
    v57 = *(_QWORD *)(*((_QWORD *)*a5 + 20) + 144LL);
    if ( v57 )
      v58 = v57 + *(_QWORD *)NtCurrentTeb()->ReservedForOle;
    else
      v58 = 0;
    *a6 = *(unsigned __int16 *)(v58 + 1424);
  }
  CSafeMultiHeap::~CSafeMultiHeap((CSafeMultiHeap *)v64);
  v55 = GetTlsSmAllocator();
  *((_QWORD *)v55 + 1) = 0;
  *((_QWORD *)v55 + 2) = 0;
  *((_QWORD *)v55 + 4) = 0;
  *(_QWORD *)NtCurrentTeb()->ReservedForOle = 0;
  *((_QWORD *)v55 + 3) = 0;
  ((void (__fastcall *)(struct IMalloc *))v16->lpVtbl->Release)(v16);
LABEL_24:
  CPerContext::~CPerContext((CPerContext *)v65);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18001c2ac  mov     rax, rsp
0x18001c2af  mov     [rax+8], rbx
0x18001c2b3  mov     [rax+20h], r9
0x18001c2b7  mov     [rax+10h], edx
0x18001c2ba  push    rbp
0x18001c2bb  push    rsi
0x18001c2bc  push    rdi
0x18001c2bd  push    r12
0x18001c2bf  push    r13
0x18001c2c1  push    r14
0x18001c2c3  push    r15
0x18001c2c5  lea     rbp, [rax-48h]
0x18001c2c9  sub     rsp, 110h
0x18001c2d0  xor     ebx, ebx
0x18001c2d2  xorps   xmm0, xmm0
0x18001c2d5  mov     [rbp+40h+arg_38], rbx
0x18001c2dc  mov     r15d, r8d
0x18001c2df  mov     [rbp+40h+var_B8], rbx
0x18001c2e3  mov     r14d, edx
0x18001c2e6  mov     [rbp+40h+var_80], rbx
0x18001c2ea  mov     r13, rcx
0x18001c2ed  movdqa  [rbp+40h+var_50], xmm0
0x18001c2f2  call    ?GetTlsSmAllocator@@YAAEAVCSmAllocator@@XZ; GetTlsSmAllocator(void)
0x18001c2f7  mov     edx, r14d
0x18001c2fa  lea     rcx, [rbp+40h+arg_38]; struct IMalloc **
0x18001c301  xorps   xmm0, xmm0
0x18001c304  and     edx, 80000h; int
0x18001c30a  mov     r10, [rax+8]
0x18001c30e  mov     [rbp+40h+var_68], r10
0x18001c312  mov     r8, [rax+10h]
0x18001c316  mov     [rbp+40h+var_60], r8
0x18001c31a  mov     eax, [rax+24h]
0x18001c31d  mov     [rbp+40h+var_58], eax
0x18001c320  mov     [rbp+40h+var_A0], rbx
0x18001c324  movdqa  [rbp+40h+var_B0], xmm0
0x18001c329  mov     [rbp+40h+var_98], ebx
0x18001c32c  mov     [rbp+40h+var_88], 1
0x18001c333  mov     [rbp+40h+var_90], rbx
0x18001c337  mov     [rbp+40h+var_78], rbx
0x18001c33b  mov     [rbp+40h+var_70], 0FFFFFFFFFFFFFFFFh
0x18001c343  mov     [rbp+40h+var_40], ebx
0x18001c346  call    ?DfCreateSharedAllocator@@YAJPEAPEAUIMalloc@@H@Z; DfCreateSharedAllocator(IMalloc * *,int)
0x18001c34b  mov     edi, eax
0x18001c34d  test    eax, eax
0x18001c34f  js      loc_18001C4FB
0x18001c355  lea     ecx, [rbx+78h]; unsigned __int64
0x18001c358  mov     esi, ebx
0x18001c35a  call    ??2CMallocBased@@SAPEAX_KQEAUIMalloc@@@Z; CMallocBased::operator new(unsigned __int64,IMalloc * const)
0x18001c35f  mov     r12, [rbp+40h+arg_38]
0x18001c366  test    rax, rax
0x18001c369  jz      loc_18001C521
0x18001c36f  mov     rdx, r12; struct IMalloc *
0x18001c372  mov     rcx, rax; this
0x18001c375  call    ??0CFileStream@@QEAA@QEAUIMalloc@@@Z; CFileStream::CFileStream(IMalloc * const)
0x18001c37a  mov     rbx, rax
0x18001c37d  test    rax, rax
0x18001c380  jz      loc_18001C521
0x18001c386  mov     edx, r15d
0x18001c389  mov     r8d, r14d; unsigned int
0x18001c38c  and     edx, 0FFFFFBFCh; unsigned int
0x18001c392  mov     rcx, rax; this
0x18001c395  call    ?InitGlobal@CFileStream@@QEAAJKK@Z; CFileStream::InitGlobal(ulong,ulong)
0x18001c39a  mov     edi, eax
0x18001c39c  test    eax, eax
0x18001c39e  js      loc_18001C497
0x18001c3a4  mov     r9, [rbp+40h+arg_30]; void *
0x18001c3ab  xor     r8d, r8d; unsigned int
0x18001c3ae  mov     rdx, r13; unsigned __int16 *
0x18001c3b1  mov     rcx, rbx; this
0x18001c3b4  call    ?InitWorker@CFileStream@@AEAAJPEBGKPEAX@Z; CFileStream::InitWorker(ushort const *,ulong,void *)
0x18001c3b9  mov     r14d, r15d
0x18001c3bc  mov     edi, eax
0x18001c3be  and     r14d, 4
0x18001c3c2  test    eax, eax
0x18001c3c4  js      short loc_18001C3D8
0x18001c3c6  test    r14d, r14d
0x18001c3c9  jnz     loc_18001C89F
0x18001c3cf  test    r13, r13
0x18001c3d2  jz      loc_18001C89F
0x18001c3d8  mov     dword ptr [rbp+40h+arg_38], esi
0x18001c3de  cmp     eax, 80030050h
0x18001c3e3  jz      loc_18001C8B1
0x18001c3e9  xor     r13d, r13d
0x18001c3ec  test    edi, edi
0x18001c3ee  js      loc_18001C497
0x18001c3f4  test    r14d, r14d
0x18001c3f7  jnz     loc_18001C6FD
0x18001c3fd  mov     r14d, 200h
0x18001c403  test    r14d, r15d
0x18001c406  jnz     loc_18001C933
0x18001c40c  mov     edi, r14d
0x18001c40f  mov     ecx, edi; cb
0x18001c411  call    cs:__imp_CoTaskMemAlloc
0x18001c417  mov     rsi, rax
0x18001c41a  test    rax, rax
0x18001c41d  jz      loc_18001C85F
0x18001c423  mov     rax, [rbx]
0x18001c426  lea     rcx, [rsp+140h+var_100]
0x18001c42b  mov     [rsp+140h+var_120], rcx
0x18001c430  mov     r9d, edi
0x18001c433  mov     qword ptr [rsp+140h+var_F8], 0
0x18001c43c  mov     r8, rsi
0x18001c43f  mov     rdx, qword ptr [rsp+140h+var_F8]
0x18001c444  mov     rcx, rbx
0x18001c447  mov     rax, [rax+18h]
0x18001c44b  mov     dword ptr [rsp+140h+var_100], r13d
0x18001c450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c455  mov     edi, eax
0x18001c457  test    eax, eax
0x18001c459  js      short loc_18001C47C
0x18001c45b  cmp     dword ptr [rsp+140h+var_100], r14d
0x18001c460  jb      short loc_18001C477
0x18001c462  mov     rcx, rsi; this
0x18001c465  call    ?Validate@CMSFHeader@@QEBAJXZ; CMSFHeader::Validate(void)
0x18001c46a  mov     edi, eax
0x18001c46c  cmp     eax, 800300FBh
0x18001c471  jnz     loc_18001C52B
0x18001c477  mov     edi, 80030050h
0x18001c47c  mov     r13d, [rbp+40h+arg_8]
0x18001c480  cmp     dword ptr [rbp+40h+arg_38], 0
0x18001c487  jnz     loc_18001C989
0x18001c48d  test    r15b, 4
0x18001c491  jnz     loc_18001C97F
0x18001c497  mov     rax, [rbx]
0x18001c49a  mov     rcx, rbx
0x18001c49d  mov     rax, [rax+10h]
0x18001c4a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c4a6  call    ?GetTlsSmAllocator@@YAAEAVCSmAllocator@@XZ; GetTlsSmAllocator(void)
0x18001c4ab  mov     rcx, rax; this
0x18001c4ae  call    ?Uninit@CSmAllocator@@QEAAJXZ; CSmAllocator::Uninit(void)
0x18001c4b3  call    ?GetTlsSmAllocator@@YAAEAVCSmAllocator@@XZ; GetTlsSmAllocator(void)
0x18001c4b8  xor     ebx, ebx
0x18001c4ba  mov     [rax+8], rbx
0x18001c4be  mov     [rax+10h], rbx
0x18001c4c2  mov     [rax+20h], rbx
0x18001c4c6  mov     rcx, gs:30h
0x18001c4cf  mov     rdx, [rcx+1758h]
0x18001c4d6  mov     rcx, r12
0x18001c4d9  mov     [rdx], rbx
0x18001c4dc  mov     [rax+18h], rbx
0x18001c4e0  mov     rax, [r12]
0x18001c4e4  mov     rax, [rax+10h]
0x18001c4e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c4ed  test    rsi, rsi
0x18001c4f0  jz      short loc_18001C4FB
0x18001c4f2  mov     rcx, rsi; pv
0x18001c4f5  call    cs:__imp_CoTaskMemFree
0x18001c4fb  lea     rcx, [rbp+40h+var_C0]; this
0x18001c4ff  call    ??1CPerContext@@QEAA@XZ; CPerContext::~CPerContext(void)
0x18001c504  mov     rbx, [rsp+140h+arg_0]
0x18001c50c  mov     eax, edi
0x18001c50e  add     rsp, 110h
0x18001c515  pop     r15
0x18001c517  pop     r14
0x18001c519  pop     r13
0x18001c51b  pop     r12
0x18001c51d  pop     rdi
0x18001c51e  pop     rsi
0x18001c51f  pop     rbp
0x18001c520  retn
0x18001c521  mov     edi, 80030008h
0x18001c526  jmp     loc_18001C4A6
0x18001c52b  test    eax, eax
0x18001c52d  js      loc_18001C47C
0x18001c533  movzx   eax, word ptr [rsi+1Eh]
0x18001c537  cmp     ax, 9
0x18001c53b  jbe     loc_18001C6B6
0x18001c541  mov     rcx, [rbx+30h]
0x18001c545  and     eax, 0Fh
0x18001c548  bts     [rbp+40h+arg_8], 13h
0x18001c54d  shl     eax, 0Ch
0x18001c550  or      r15d, eax
0x18001c553  mov     [rsp+140h+var_F0], r13
0x18001c558  mov     [rsp+140h+var_D8], rcx
0x18001c55d  call    ?GetTlsSmAllocator@@YAAEAVCSmAllocator@@XZ; GetTlsSmAllocator(void)
0x18001c562  mov     edx, 1; int
0x18001c567  mov     rcx, [rax+10h]
0x18001c56b  mov     r13, [rax+8]
0x18001c56f  mov     eax, [rax+24h]
0x18001c572  mov     [rsp+140h+var_E8], rcx
0x18001c577  lea     rcx, [rsp+140h+var_F0]; struct IMalloc **
0x18001c57c  mov     [rsp+140h+var_F8], eax
0x18001c580  call    ?DfCreateSharedAllocator@@YAJPEAPEAUIMalloc@@H@Z; DfCreateSharedAllocator(IMalloc * *,int)
0x18001c585  mov     edi, eax
0x18001c587  test    eax, eax
0x18001c589  js      loc_18001C86E
0x18001c58f  mov     rax, [r12]
0x18001c593  mov     rcx, r12
0x18001c596  mov     rax, [rax+10h]
0x18001c59a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c59f  mov     r12, [rsp+140h+var_F0]
0x18001c5a4  mov     ecx, 78h ; 'x'; unsigned __int64
0x18001c5a9  call    ??2CMallocBased@@SAPEAX_KQEAUIMalloc@@@Z; CMallocBased::operator new(unsigned __int64,IMalloc * const)
0x18001c5ae  test    rax, rax
0x18001c5b1  jz      loc_18001C869
0x18001c5b7  mov     rdx, r12; struct IMalloc *
0x18001c5ba  mov     rcx, rax; this
0x18001c5bd  call    ??0CFileStream@@QEAA@QEAUIMalloc@@@Z; CFileStream::CFileStream(IMalloc * const)
0x18001c5c2  mov     r14, rax
0x18001c5c5  test    rax, rax
0x18001c5c8  jz      loc_18001C869
0x18001c5ce  mov     r8d, [rbp+40h+arg_8]; unsigned int
0x18001c5d2  mov     edx, r15d
0x18001c5d5  and     edx, 0FFFFFBFCh; unsigned int
0x18001c5db  mov     rcx, rax; this
0x18001c5de  call    ?InitGlobal@CFileStream@@QEAAJKK@Z; CFileStream::InitGlobal(ulong,ulong)
0x18001c5e3  xor     ecx, ecx
0x18001c5e5  mov     edi, eax
0x18001c5e7  test    eax, eax
0x18001c5e9  js      loc_18001C94A
0x18001c5ef  mov     rax, [rbx+40h]
0x18001c5f3  mov     rdx, [rsp+140h+var_D8]; struct CGlobalFileStream *
0x18001c5f8  mov     [r14+40h], rax
0x18001c5fc  mov     rax, [rbx+60h]
0x18001c600  mov     [r14+60h], rax
0x18001c604  mov     rax, [rbx+68h]
0x18001c608  mov     [r14+68h], rax
0x18001c60c  mov     eax, [rbx+70h]
0x18001c60f  mov     [r14+70h], eax
0x18001c613  mov     qword ptr [rbx+40h], 0FFFFFFFFFFFFFFFFh
0x18001c61b  mov     [rbx+60h], rcx
0x18001c61f  mov     [rbx+68h], rcx
0x18001c623  mov     [rbx+70h], ecx
0x18001c626  mov     rcx, [r14+30h]; this
0x18001c62a  call    ?InitFromGlobalFileStream@CGlobalFileStream@@QEAAXPEAV1@@Z; CGlobalFileStream::InitFromGlobalFileStream(CGlobalFileStream *)
0x18001c62f  call    ?GetTlsSmAllocator@@YAAEAVCSmAllocator@@XZ; GetTlsSmAllocator(void)
0x18001c634  mov     r8, [rsp+140h+var_E8]
0x18001c639  mov     rdx, rax
0x18001c63c  mov     [rax+8], r13
0x18001c640  mov     [rax+10h], r8
0x18001c644  test    r13, r13
0x18001c647  jz      loc_18001C84C
0x18001c64d  mov     ecx, [r13+10h]
0x18001c651  sub     ecx, 18h
0x18001c654  xor     r13d, r13d
0x18001c657  mov     r9d, [rsp+140h+var_F8]
0x18001c65c  mov     [rax+24h], r9d
0x18001c660  mov     [rax+20h], ecx
0x18001c663  mov     rax, gs:30h
0x18001c66c  mov     rcx, [rax+1758h]
0x18001c673  mov     [rcx], r8
0x18001c676  mov     [rdx+18h], r13
0x18001c67a  call    ?GetTlsSmAllocator@@YAAEAVCSmAllocator@@XZ; GetTlsSmAllocator(void)
0x18001c67f  mov     rcx, rax; this
0x18001c682  call    ?Uninit@CSmAllocator@@QEAAJXZ; CSmAllocator::Uninit(void)
0x18001c687  call    ?GetTlsSmAllocator@@YAAEAVCSmAllocator@@XZ; GetTlsSmAllocator(void)
0x18001c68c  mov     rbx, r14
0x18001c68f  mov     [rax+8], r13
0x18001c693  mov     [rax+10h], r13
0x18001c697  mov     qword ptr [rax+20h], 0
0x18001c69f  mov     rcx, gs:30h
0x18001c6a8  mov     rdx, [rcx+1758h]
0x18001c6af  mov     [rdx], r13
0x18001c6b2  mov     [rax+18h], r13
0x18001c6b6  lea     rcx, [rbx+8]
0x18001c6ba  mov     [rsp+140h+var_E0], r13
0x18001c6bf  mov     rax, [rcx]
0x18001c6c2  lea     rdx, [rsp+140h+var_E0]
0x18001c6c7  mov     rax, [rax+30h]
0x18001c6cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c6d0  mov     edi, eax
0x18001c6d2  test    eax, eax
0x18001c6d4  js      loc_18001C47C
0x18001c6da  mov     rdx, [rsp+140h+var_E0]; unsigned __int64
0x18001c6df  xor     r8d, r8d; struct ILockBytes *
0x18001c6e2  mov     rcx, rsi; this
0x18001c6e5  call    ?CheckSectorsAgainstFileSize@CMSFHeader@@QEBAJ_KPEAUILockBytes@@@Z; CMSFHeader::CheckSectorsAgainstFileSize(unsigned __int64,ILockBytes *)
0x18001c6ea  mov     edi, eax
0x18001c6ec  test    eax, eax
0x18001c6ee  js      loc_18001C47C
0x18001c6f4  mov     rcx, rsi; pv
0x18001c6f7  call    cs:__imp_CoTaskMemFree
0x18001c6fd  mov     ecx, 88h; unsigned __int64
0x18001c702  call    ??2CMallocBased@@SAPEAX_KQEAUIMalloc@@@Z; CMallocBased::operator new(unsigned __int64,IMalloc * const)
0x18001c707  test    rax, rax
0x18001c70a  jz      loc_18001C85C
0x18001c710  mov     rdx, r12; struct IMalloc *
0x18001c713  mov     rcx, rax; this
0x18001c716  call    ??0CPerContext@@QEAA@PEAUIMalloc@@@Z; CPerContext::CPerContext(IMalloc *)
0x18001c71b  mov     r14, rax
0x18001c71e  test    rax, rax
0x18001c721  jz      loc_18001C85C
0x18001c727  mov     edx, r15d
0x18001c72a  mov     rcx, rax; this
0x18001c72d  shr     edx, 2
0x18001c730  and     edx, 1; int
0x18001c733  call    ?InitNewContext@CPerContext@@QEAAJH@Z; CPerContext::InitNewContext(int)
0x18001c738  mov     edi, eax
0x18001c73a  test    eax, eax
0x18001c73c  js      loc_18001C95E
0x18001c742  call    ?GetTlsSmAllocator@@YAAEAVCSmAllocator@@XZ; GetTlsSmAllocator(void)
0x18001c747  mov     rcx, [rax+8]
0x18001c74b  mov     [rbp+40h+var_68], rcx
0x18001c74f  mov     rcx, [rax+10h]
0x18001c753  mov     [rbp+40h+var_60], rcx
0x18001c757  mov     eax, [rax+24h]
0x18001c75a  mov     [rbp+40h+var_58], eax
0x18001c75d  call    ?GetTlsSmAllocator@@YAAEAVCSmAllocator@@XZ; GetTlsSmAllocator(void)
0x18001c762  mov     rcx, [rbp+40h+var_68]
0x18001c766  mov     rdx, rax
  ... truncated ...
```
