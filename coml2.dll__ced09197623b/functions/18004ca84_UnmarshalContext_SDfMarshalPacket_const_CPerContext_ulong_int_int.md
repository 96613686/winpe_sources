# UnmarshalContext(SDfMarshalPacket const *,CPerContext * *,ulong,int,int)

- ea: `0x18004ca84`
- end: `0x18004cde3`
- name: `?UnmarshalContext@@YAJPEBUSDfMarshalPacket@@PEAPEAVCPerContext@@KHH@Z`
- size: `863`
- prototype: `__int64 __fastcall(const struct SDfMarshalPacket *, struct CPerContext **, unsigned int, int, int)`
- caller_count: `2`
- callee_count: `18`
- tags: `authz_impersonation`

## callers

- `0x18003b588`
- `0x1800405dc`

## callees

- `0x180018680`
- `0x18001b89c`
- `0x18001d820`
- `0x18001efe8`
- `0x18001fbb4`
- `0x18001fd08`
- `0x18002db70`
- `0x180030c08`
- `0x180032790`
- `0x18003313c`
- `0x18003ec7c`
- `0x180042800`
- `0x18004ba24`
- `0x18004c638`
- `0x18004ca84`
- `0x18005d728`
- `0x18005fe08`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004cafc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004cb52`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004cba3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004cafc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004cb52`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004cba3`

## pseudocode

```c
__int64 __fastcall UnmarshalContext(
        const struct SDfMarshalPacket *a1,
        struct CPerContext **a2,
        __int64 a3,
        int a4,
        int a5)
{
  struct ILockBytes *v5; // rbx
  __int64 v6; // rdx
  struct CFileStream *v7; // r15
  struct ILockBytes *v8; // r14
  CPerContext *v9; // r12
  const struct SDfMarshalPacket *v10; // rdi
  __int64 v11; // r13
  DWORD CurrentProcessId; // eax
  struct CContext *v13; // rax
  struct CContext *v14; // rsi
  struct CPerContext **v15; // rdx
  CProcessSecret *v16; // rcx
  CSmAllocator *TlsSmAllocator; // rax
  DWORD v18; // eax
  struct CContext *v19; // rsi
  int v20; // edi
  CPerContext *v21; // rax
  CPerContext *v22; // rax
  int v23; // eax
  const struct SDfMarshalPacket *v24; // rbx
  int v25; // eax
  int v26; // eax
  unsigned int v28; // [rsp+30h] [rbp-81h] BYREF
  struct ILockBytes *v29; // [rsp+38h] [rbp-79h] BYREF
  struct CFileStream *v30; // [rsp+40h] [rbp-71h] BYREF
  int v31; // [rsp+48h] [rbp-69h]
  struct ILockBytes *v32; // [rsp+50h] [rbp-61h] BYREF
  const struct SDfMarshalPacket *v33; // [rsp+58h] [rbp-59h]
  struct CContext *v34; // [rsp+60h] [rbp-51h]
  struct CPerContext **v35; // [rsp+68h] [rbp-49h]
  struct _GUID v36; // [rsp+70h] [rbp-41h] BYREF
  unsigned __int16 v37[32]; // [rsp+80h] [rbp-31h] BYREF

  v5 = 0;
  v35 = a2;
  v6 = *((_QWORD *)a1 + 5);
  v7 = 0;
  v8 = 0;
  v31 = a4;
  v9 = 0;
  v33 = a1;
  v29 = 0;
  v10 = a1;
  v30 = 0;
  v32 = 0;
  v28 = 0;
  if ( v6 )
    v11 = v6 + *(_QWORD *)NtCurrentTeb()->ReservedForOle;
  else
    v11 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v13 = CContextList::_Find((CContextList *)v11, CurrentProcessId);
  v14 = v13;
  if ( v13 )
  {
    StringCchPrintfW(
      v37,
      0x20u,
      L"OleDfRoot%X%08lX",
      *(unsigned int *)(*((_QWORD *)v13 + 6) + 60LL),
      *(_DWORD *)(*((_QWORD *)v13 + 6) + 56LL));
    if ( !(unsigned int)CDfMutex::IsHandleValid((struct CContext *)((char *)v14 + 112), v37) )
    {
      *(_DWORD *)v14 = 0;
      v14 = 0;
    }
  }
  v34 = v14;
  if ( GetCurrentProcessId() == *((_DWORD *)v10 + 19)
    || (v36 = (struct _GUID)*((_OWORD *)v10 + 5), CProcessSecret::VerifyMatchingSecret(v16, &v36) >= 0) )
  {
    if ( v14 )
      goto LABEL_11;
  }
  else if ( v14 )
  {
    CPerContext::SetThreadAllocatorState(v14, v15);
    goto LABEL_11;
  }
  v21 = (CPerContext *)CMallocBased::operator new(0x88u, (struct IMalloc *const)v15);
  if ( v21 && (v22 = CPerContext::CPerContext(v21, *(struct IMalloc **)(v11 + 40)), (v9 = v22) != 0) )
  {
    v14 = v22;
    v20 = CDfMutex::Init((CPerContext *)((char *)v22 + 112), (struct CGlobalContext *)v11, 0);
    if ( v20 >= 0 )
    {
      *((_QWORD *)v14 + 6) = v11;
      ++*(_DWORD *)(v11 + 8);
      CContextList::Add(*((CContextList **)v14 + 6), v14);
      v10 = v33;
LABEL_11:
      TlsSmAllocator = GetTlsSmAllocator();
      CSmAllocator::SetState(
        TlsSmAllocator,
        *((struct CSharedMemoryBlock **)v14 + 11),
        *((unsigned __int8 **)v14 + 12),
        *((_DWORD *)v14 + 26),
        0,
        v14);
      v18 = GetCurrentProcessId();
      v19 = CContextList::_Find((CContextList *)v11, v18);
      if ( !v19 )
      {
        v20 = -2147286787;
LABEL_47:
        if ( v9 )
          CPerContext::Release(v9);
        if ( v8 )
          ((void (__fastcall *)(struct ILockBytes *))v8->lpVtbl->Release)(v8);
        if ( v7 )
          (*(void (__fastcall **)(struct CFileStream *))(*(_QWORD *)v7 + 16LL))(v7);
        if ( v5 )
          ((void (__fastcall *)(struct ILockBytes *))v5->lpVtbl->Release)(v5);
        return (unsigned int)v20;
      }
      v23 = CFileStream::Unmarshal(*((_QWORD *)v10 + 6), &v29);
      v24 = v33;
      v20 = v23;
      v25 = CFileStream::Unmarshal(*((_QWORD *)v33 + 7), &v30);
      if ( v20 >= 0 )
        v20 = v25;
      if ( a5 )
      {
        v26 = CFileStream::Unmarshal(*((_QWORD *)v24 + 8), &v32);
        v8 = v32;
        if ( v20 < 0 )
        {
LABEL_46:
          v7 = v30;
          v5 = v29;
          goto LABEL_47;
        }
        v20 = v26;
      }
      if ( v20 >= 0 )
      {
        if ( *((_QWORD *)v19 + 2) )
        {
          ((void (__fastcall *)(struct ILockBytes *))v29->lpVtbl->Release)(v29);
          v5 = 0;
        }
        else
        {
          v5 = v29;
        }
        if ( *((_QWORD *)v19 + 3) )
          (*(void (__fastcall **)(struct CFileStream *))(*(_QWORD *)v30 + 16LL))(v30);
        else
          v7 = v30;
        if ( v8 )
        {
          if ( *((_QWORD *)v19 + 4) )
          {
            ((void (__fastcall *)(struct ILockBytes *))v8->lpVtbl->Release)(v8);
            v8 = 0;
          }
        }
        else if ( v5 )
        {
          ((void (__fastcall *)(struct ILockBytes *))v5->lpVtbl->AddRef)(v5);
          v8 = v5;
        }
        if ( v34 )
        {
          if ( !*((_QWORD *)v19 + 2) )
            CPerContext::SetILBInfo(v19, v5, v7, v8, 0);
          _InterlockedIncrement((volatile signed __int32 *)v19 + 14);
        }
        else
        {
          if ( v31 )
          {
            if ( *(_DWORD *)(v11 + 32) )
            {
              v20 = StgpAcquireOpenLocks(v8, *(_DWORD *)(v11 + 36), 0, &v28);
              if ( v20 < 0 )
                goto LABEL_47;
            }
          }
          CPerContext::SetILBInfo(v19, v5, v7, v8, v28);
        }
        *v35 = v19;
        return 0;
      }
      goto LABEL_46;
    }
    CPerContext::Release(v9);
  }
  else
  {
    return (unsigned int)-2147287032;
  }
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x18004ca84  mov     [rsp-8+arg_10], rbx
0x18004ca89  push    rbp
0x18004ca8a  push    rsi
0x18004ca8b  push    rdi
0x18004ca8c  push    r12
0x18004ca8e  push    r13
0x18004ca90  push    r14
0x18004ca92  push    r15
0x18004ca94  lea     rbp, [rsp-1Fh]
0x18004ca99  sub     rsp, 0D0h
0x18004caa0  mov     rax, cs:__security_cookie
0x18004caa7  xor     rax, rsp
0x18004caaa  mov     [rbp+4Fh+var_40], rax
0x18004caae  xor     ebx, ebx
0x18004cab0  mov     [rbp+4Fh+var_98], rdx
0x18004cab4  mov     rdx, [rcx+28h]
0x18004cab8  xor     r15d, r15d
0x18004cabb  xor     r14d, r14d
0x18004cabe  mov     [rbp+4Fh+var_B8], r9d
0x18004cac2  xor     r12d, r12d
0x18004cac5  mov     [rbp+4Fh+var_A8], rcx
0x18004cac9  mov     [rbp+4Fh+var_C8], rbx
0x18004cacd  mov     rdi, rcx
0x18004cad0  mov     [rbp+4Fh+var_C0], r15
0x18004cad4  mov     [rbp+4Fh+var_B0], r14
0x18004cad8  mov     [rsp+100h+var_D0], ebx
0x18004cadc  test    rdx, rdx
0x18004cadf  jz      short loc_18004CAF9
0x18004cae1  mov     rax, gs:30h
0x18004caea  mov     rcx, [rax+1758h]
0x18004caf1  mov     r13, [rcx]
0x18004caf4  add     r13, rdx
0x18004caf7  jmp     short loc_18004CAFC
0x18004caf9  xor     r13d, r13d
0x18004cafc  call    cs:__imp_GetCurrentProcessId
0x18004cb02  mov     edx, eax; unsigned int
0x18004cb04  mov     rcx, r13; this
0x18004cb07  call    ?_Find@CContextList@@QEAAPEAVCContext@@K@Z; CContextList::_Find(ulong)
0x18004cb0c  mov     rsi, rax
0x18004cb0f  test    rax, rax
0x18004cb12  jz      short loc_18004CB4E
0x18004cb14  mov     r9, [rax+30h]
0x18004cb18  lea     r8, aOledfrootX08lx; "OleDfRoot%X%08lX"
0x18004cb1f  mov     edx, 20h ; ' '; unsigned __int64
0x18004cb24  mov     ecx, [r9+38h]
0x18004cb28  mov     r9d, [r9+3Ch]
0x18004cb2c  mov     dword ptr [rsp+100h+var_E0], ecx
0x18004cb30  lea     rcx, [rbp+4Fh+var_80]; unsigned __int16 *
0x18004cb34  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004cb39  lea     rcx, [rsi+70h]; this
0x18004cb3d  lea     rdx, [rbp+4Fh+var_80]; unsigned __int16 *
0x18004cb41  call    ?IsHandleValid@CDfMutex@@QEAAHPEBG@Z; CDfMutex::IsHandleValid(ushort const *)
0x18004cb46  test    eax, eax
0x18004cb48  jnz     short loc_18004CB4E
0x18004cb4a  mov     [rsi], ebx
0x18004cb4c  xor     esi, esi
0x18004cb4e  mov     [rbp+4Fh+var_A0], rsi
0x18004cb52  call    cs:__imp_GetCurrentProcessId
0x18004cb58  cmp     eax, [rdi+4Ch]
0x18004cb5b  jz      short loc_18004CBC5
0x18004cb5d  movups  xmm0, xmmword ptr [rdi+50h]
0x18004cb61  lea     rdx, [rbp+4Fh+var_90]; struct _GUID
0x18004cb65  movdqu  xmmword ptr [rbp+4Fh+var_90.Data1], xmm0
0x18004cb6a  call    ?VerifyMatchingSecret@CProcessSecret@@QEAAJU_GUID@@@Z; CProcessSecret::VerifyMatchingSecret(_GUID)
0x18004cb6f  test    eax, eax
0x18004cb71  jns     short loc_18004CBC5
0x18004cb73  test    rsi, rsi
0x18004cb76  jz      short loc_18004CBCA
0x18004cb78  mov     rcx, rsi; this
0x18004cb7b  call    ?SetThreadAllocatorState@CPerContext@@QEAAPEAVCSmAllocator@@PEAPEAV1@@Z; CPerContext::SetThreadAllocatorState(CPerContext * *)
0x18004cb80  call    ?GetTlsSmAllocator@@YAAEAVCSmAllocator@@XZ; GetTlsSmAllocator(void)
0x18004cb85  mov     r8, [rsi+60h]; unsigned __int8 *
0x18004cb89  mov     rcx, rax; this
0x18004cb8c  mov     rdx, [rsi+58h]; struct CSharedMemoryBlock *
0x18004cb90  mov     r9d, [rsi+68h]; unsigned int
0x18004cb94  mov     [rsp+100h+var_D8], rsi; struct CPerContext *
0x18004cb99  mov     [rsp+100h+var_E0], rbx; struct CPerContext **
0x18004cb9e  call    ?SetState@CSmAllocator@@QEAAXPEAVCSharedMemoryBlock@@PEAEKPEAPEAVCPerContext@@PEAV3@@Z; CSmAllocator::SetState(CSharedMemoryBlock *,uchar *,ulong,CPerContext * *,CPerContext *)
0x18004cba3  call    cs:__imp_GetCurrentProcessId
0x18004cba9  mov     edx, eax; unsigned int
0x18004cbab  mov     rcx, r13; this
0x18004cbae  call    ?_Find@CContextList@@QEAAPEAVCContext@@K@Z; CContextList::_Find(ulong)
0x18004cbb3  mov     rsi, rax
0x18004cbb6  test    rax, rax
0x18004cbb9  jnz     short loc_18004CC39
0x18004cbbb  mov     edi, 800300FDh
0x18004cbc0  jmp     loc_18004CD71
0x18004cbc5  test    rsi, rsi
0x18004cbc8  jnz     short loc_18004CB80
0x18004cbca  mov     ecx, 88h; unsigned __int64
0x18004cbcf  call    ??2CMallocBased@@SAPEAX_KQEAUIMalloc@@@Z; CMallocBased::operator new(unsigned __int64,IMalloc * const)
0x18004cbd4  test    rax, rax
0x18004cbd7  jz      short loc_18004CC2F
0x18004cbd9  mov     rdx, [r13+28h]; struct IMalloc *
0x18004cbdd  mov     rcx, rax; this
0x18004cbe0  call    ??0CPerContext@@QEAA@PEAUIMalloc@@@Z; CPerContext::CPerContext(IMalloc *)
0x18004cbe5  mov     r12, rax
0x18004cbe8  test    rax, rax
0x18004cbeb  jz      short loc_18004CC2F
0x18004cbed  lea     rcx, [rax+70h]; this
0x18004cbf1  xor     r8d, r8d; int
0x18004cbf4  mov     rdx, r13; struct CGlobalContext *
0x18004cbf7  mov     rsi, rax
0x18004cbfa  call    ?Init@CDfMutex@@QEAAJPEAVCGlobalContext@@H@Z; CDfMutex::Init(CGlobalContext *,int)
0x18004cbff  mov     edi, eax
0x18004cc01  test    eax, eax
0x18004cc03  js      short loc_18004CC22
0x18004cc05  mov     [rsi+30h], r13
0x18004cc09  mov     rdx, rsi; struct CContext *
0x18004cc0c  inc     dword ptr [r13+8]
0x18004cc10  mov     rcx, [rsi+30h]; this
0x18004cc14  call    ?Add@CContextList@@QEAAXPEAVCContext@@@Z; CContextList::Add(CContext *)
0x18004cc19  mov     rdi, [rbp+4Fh+var_A8]
0x18004cc1d  jmp     loc_18004CB80
0x18004cc22  mov     rcx, r12; this
0x18004cc25  call    ?Release@CPerContext@@QEAAJXZ; CPerContext::Release(void)
0x18004cc2a  jmp     loc_18004CDBA
0x18004cc2f  mov     edi, 80030008h
0x18004cc34  jmp     loc_18004CDBA
0x18004cc39  mov     rcx, [rdi+30h]
0x18004cc3d  lea     rdx, [rbp+4Fh+var_C8]
0x18004cc41  call    ?Unmarshal@CFileStream@@SAJV?$BasedPtr@VCGlobalFileStream@@@@PEAPEAXK@Z; CFileStream::Unmarshal(BasedPtr<CGlobalFileStream>,void * *,ulong)
0x18004cc46  mov     rbx, [rbp+4Fh+var_A8]
0x18004cc4a  lea     rdx, [rbp+4Fh+var_C0]
0x18004cc4e  mov     edi, eax
0x18004cc50  mov     rcx, [rbx+38h]
0x18004cc54  call    ?Unmarshal@CFileStream@@SAJV?$BasedPtr@VCGlobalFileStream@@@@PEAPEAXK@Z; CFileStream::Unmarshal(BasedPtr<CGlobalFileStream>,void * *,ulong)
0x18004cc59  test    edi, edi
0x18004cc5b  cmovns  edi, eax
0x18004cc5e  cmp     [rbp+4Fh+arg_20], r14d
0x18004cc62  jz      short loc_18004CC7F
0x18004cc64  mov     rcx, [rbx+40h]
0x18004cc68  lea     rdx, [rbp+4Fh+var_B0]
0x18004cc6c  call    ?Unmarshal@CFileStream@@SAJV?$BasedPtr@VCGlobalFileStream@@@@PEAPEAXK@Z; CFileStream::Unmarshal(BasedPtr<CGlobalFileStream>,void * *,ulong)
0x18004cc71  mov     r14, [rbp+4Fh+var_B0]
0x18004cc75  test    edi, edi
0x18004cc77  js      loc_18004CD69
0x18004cc7d  mov     edi, eax
0x18004cc7f  test    edi, edi
0x18004cc81  js      loc_18004CD69
0x18004cc87  xor     edi, edi
0x18004cc89  cmp     [rsi+10h], rdi
0x18004cc8d  jz      short loc_18004CCA3
0x18004cc8f  mov     rcx, [rbp+4Fh+var_C8]
0x18004cc93  mov     rax, [rcx]
0x18004cc96  mov     rax, [rax+10h]
0x18004cc9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cc9f  mov     ebx, edi
0x18004cca1  jmp     short loc_18004CCA7
0x18004cca3  mov     rbx, [rbp+4Fh+var_C8]
0x18004cca7  cmp     [rsi+18h], rdi
0x18004ccab  jz      short loc_18004CCBF
0x18004ccad  mov     rcx, [rbp+4Fh+var_C0]
0x18004ccb1  mov     rax, [rcx]
0x18004ccb4  mov     rax, [rax+10h]
0x18004ccb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ccbd  jmp     short loc_18004CCC3
0x18004ccbf  mov     r15, [rbp+4Fh+var_C0]
0x18004ccc3  test    r14, r14
0x18004ccc6  jz      short loc_18004CCE2
0x18004ccc8  cmp     [rsi+20h], rdi
0x18004cccc  jz      short loc_18004CCF9
0x18004ccce  mov     rax, [r14]
0x18004ccd1  mov     rcx, r14
0x18004ccd4  mov     rax, [rax+10h]
0x18004ccd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ccdd  mov     r14, rdi
0x18004cce0  jmp     short loc_18004CCF9
0x18004cce2  test    rbx, rbx
0x18004cce5  jz      short loc_18004CCF9
0x18004cce7  mov     rax, [rbx]
0x18004ccea  mov     rcx, rbx
0x18004cced  mov     rax, [rax+8]
0x18004ccf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ccf6  mov     r14, rbx
0x18004ccf9  cmp     [rbp+4Fh+var_A0], rdi
0x18004ccfd  jnz     short loc_18004CD3F
0x18004ccff  cmp     [rbp+4Fh+var_B8], edi
0x18004cd02  jz      short loc_18004CD24
0x18004cd04  cmp     [r13+20h], edi
0x18004cd08  jz      short loc_18004CD24
0x18004cd0a  mov     edx, [r13+24h]; unsigned int
0x18004cd0e  lea     r9, [rsp+100h+var_D0]; unsigned int *
0x18004cd13  xor     r8d, r8d; int
0x18004cd16  mov     rcx, r14; struct ILockBytes *
0x18004cd19  call    ?StgpAcquireOpenLocks@@YAJPEAUILockBytes@@KHPEAK@Z; StgpAcquireOpenLocks(ILockBytes *,ulong,int,ulong *)
0x18004cd1e  mov     edi, eax
0x18004cd20  test    eax, eax
0x18004cd22  js      short loc_18004CD71
0x18004cd24  mov     eax, [rsp+100h+var_D0]
0x18004cd28  mov     r9, r14; struct ILockBytes *
0x18004cd2b  mov     r8, r15; struct CFileStream *
0x18004cd2e  mov     dword ptr [rsp+100h+var_E0], eax; unsigned int
0x18004cd32  mov     rdx, rbx; struct ILockBytes *
0x18004cd35  mov     rcx, rsi; this
0x18004cd38  call    ?SetILBInfo@CPerContext@@QEAAXPEAUILockBytes@@PEAUCFileStream@@0K@Z; CPerContext::SetILBInfo(ILockBytes *,CFileStream *,ILockBytes *,ulong)
0x18004cd3d  jmp     short loc_18004CD5E
0x18004cd3f  cmp     [rsi+10h], rdi
0x18004cd43  jnz     short loc_18004CD5A
0x18004cd45  mov     r9, r14; struct ILockBytes *
0x18004cd48  mov     dword ptr [rsp+100h+var_E0], edi; unsigned int
0x18004cd4c  mov     r8, r15; struct CFileStream *
0x18004cd4f  mov     rdx, rbx; struct ILockBytes *
0x18004cd52  mov     rcx, rsi; this
0x18004cd55  call    ?SetILBInfo@CPerContext@@QEAAXPEAUILockBytes@@PEAUCFileStream@@0K@Z; CPerContext::SetILBInfo(ILockBytes *,CFileStream *,ILockBytes *,ulong)
0x18004cd5a  lock inc dword ptr [rsi+38h]
0x18004cd5e  mov     rax, [rbp+4Fh+var_98]
0x18004cd62  mov     [rax], rsi
0x18004cd65  xor     eax, eax
0x18004cd67  jmp     short loc_18004CDBC
0x18004cd69  mov     r15, [rbp+4Fh+var_C0]
0x18004cd6d  mov     rbx, [rbp+4Fh+var_C8]
0x18004cd71  test    r12, r12
0x18004cd74  jz      short loc_18004CD7E
0x18004cd76  mov     rcx, r12; this
0x18004cd79  call    ?Release@CPerContext@@QEAAJXZ; CPerContext::Release(void)
0x18004cd7e  test    r14, r14
0x18004cd81  jz      short loc_18004CD92
0x18004cd83  mov     rax, [r14]
0x18004cd86  mov     rcx, r14
0x18004cd89  mov     rax, [rax+10h]
0x18004cd8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cd92  test    r15, r15
0x18004cd95  jz      short loc_18004CDA6
0x18004cd97  mov     rax, [r15]
0x18004cd9a  mov     rcx, r15
0x18004cd9d  mov     rax, [rax+10h]
0x18004cda1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cda6  test    rbx, rbx
0x18004cda9  jz      short loc_18004CDBA
0x18004cdab  mov     rax, [rbx]
0x18004cdae  mov     rcx, rbx
0x18004cdb1  mov     rax, [rax+10h]
0x18004cdb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cdba  mov     eax, edi
0x18004cdbc  mov     rcx, [rbp+4Fh+var_40]
0x18004cdc0  xor     rcx, rsp; StackCookie
0x18004cdc3  call    __security_check_cookie
0x18004cdc8  mov     rbx, [rsp+100h+arg_10]
0x18004cdd0  add     rsp, 0D0h
0x18004cdd7  pop     r15
0x18004cdd9  pop     r14
0x18004cddb  pop     r13
0x18004cddd  pop     r12
0x18004cddf  pop     rdi
0x18004cde0  pop     rsi
0x18004cde1  pop     rbp
0x18004cde2  retn
```
