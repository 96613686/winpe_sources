# CWbemContext::UnmarshalInterface(IStream *,_GUID const &,void * *)

- ea: `0x1800168d0`
- end: `0x180016ed6`
- name: `?UnmarshalInterface@CWbemContext@@UEAAJPEAUIStream@@AEBU_GUID@@PEAPEAX@Z`
- size: `1542`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, struct IStream *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x180016354`
- `0x1800163a4`
- `0x1800168d0`
- `0x180016edc`
- `0x180017860`
- `0x180037120`
- `0x1800388c0`
- `0x18006fa4c`
- `0x180091972`
- `0x1800919b0`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180016bb1`
- `wbemcomn!GetMemLogObject` at `0x180016bee`
- `wbemcomn!GetMemLogObject` at `0x180016c28`
- `wbemcomn!GetMemLogObject` at `0x180016c56`
- `wbemcomn!GetMemLogObject` at `0x180016cb0`
- `wbemcomn!GetMemLogObject` at `0x180016cf0`
- `wbemcomn!GetMemLogObject` at `0x180016d39`
- `wbemcomn!GetMemLogObject` at `0x180016ddb`
- `wbemcomn!GetMemLogObject` at `0x180016e56`
- `wbemcomn!GetMemLogObject` at `0x180016bb1`
- `wbemcomn!GetMemLogObject` at `0x180016bee`
- `wbemcomn!GetMemLogObject` at `0x180016c28`
- `wbemcomn!GetMemLogObject` at `0x180016c56`
- `wbemcomn!GetMemLogObject` at `0x180016cb0`
- `wbemcomn!GetMemLogObject` at `0x180016cf0`
- `wbemcomn!GetMemLogObject` at `0x180016d39`
- `wbemcomn!GetMemLogObject` at `0x180016ddb`
- `wbemcomn!GetMemLogObject` at `0x180016e56`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180016b42`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180016b42`
- `wbemcomn!?Add@CFlexArray@@QEAAHPEAX@Z` at `0x180016b30`
- `wbemcomn!?Add@CFlexArray@@QEAAHPEAX@Z` at `0x180016b30`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180016b75`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180016ba4`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180016c1b`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180016b75`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180016ba4`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180016c1b`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x180016910`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x180016910`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180016bbd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180016bf9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180016c34`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180016c61`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180016cbb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180016cfe`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180016d49`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180016de9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180016e64`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180016bbd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180016bf9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180016c34`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180016c61`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180016cbb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180016cfe`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180016d49`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180016de9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180016e64`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180016a25`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180016a25`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180016a42`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180016af8`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180016a42`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180016af8`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CWbemContext::UnmarshalInterface(
        struct _RTL_CRITICAL_SECTION *this,
        struct IStream *a2,
        const struct _GUID *a3,
        void **a4)
{
  int v6; // ebx
  unsigned int v7; // ebx
  int v8; // edi
  unsigned int v9; // ebx
  unsigned int v10; // edi
  void *v11; // rdx
  int v12; // r14d
  unsigned int i; // edi
  CWbemContext::CContextObj *v14; // rax
  CWbemContext::CContextObj *v15; // rbx
  unsigned int v16; // edx
  CMemoryLog *MemLogObject; // rax
  CWbemRefreshingSvc *v19; // r10
  __int64 v20; // rdx
  CMemoryLog *v21; // rax
  CMemoryLog *v22; // rax
  CMemoryLog *v23; // rax
  CWbemRefreshingSvc *v24; // rax
  __int64 v25; // rdx
  __int64 v26; // r9
  CMemoryLog *v27; // rax
  CMemoryLog *v28; // rax
  CWbemRefreshingSvc *v29; // rax
  __int64 v30; // rdx
  CMemoryLog *v31; // rax
  __int64 v32; // rcx
  CMemoryLog *v33; // rax
  CMemoryLog *v34; // rax
  CMemoryLog *v35; // rax
  _com_error *v36; // rbx
  CMemoryLog *v37; // rax
  __int64 v38; // [rsp+0h] [rbp-118h] BYREF
  int v39; // [rsp+30h] [rbp-E8h] BYREF
  CWbemContext::CContextObj *v40; // [rsp+38h] [rbp-E0h] BYREF
  unsigned int v41; // [rsp+40h] [rbp-D8h] BYREF
  _BYTE v42[8]; // [rsp+48h] [rbp-D0h] BYREF
  int pExceptionObject; // [rsp+50h] [rbp-C8h] BYREF
  unsigned int v44; // [rsp+54h] [rbp-C4h] BYREF
  __int64 v45; // [rsp+58h] [rbp-C0h] BYREF
  CWbemContext::CContextObj *v46; // [rsp+60h] [rbp-B8h]
  void **v47; // [rsp+68h] [rbp-B0h]
  const struct _GUID *v48; // [rsp+70h] [rbp-A8h]
  _com_error *v49; // [rsp+78h] [rbp-A0h] BYREF
  _BYTE v50[16]; // [rsp+80h] [rbp-98h] BYREF
  unsigned int v51; // [rsp+90h] [rbp-88h]

  v47 = a4;
  v48 = a3;
  CInCritSec::CInCritSec((CInCritSec *)v42, this + 4);
  memset_0(v50, 0, 0x50u);
  v6 = ((__int64 (__fastcall *)(struct IStream *, _BYTE *, _QWORD))a2->lpVtbl->Stat)(a2, v50, 0);
  if ( v6 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v6);
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_26;
    }
    v20 = 88;
    goto LABEL_40;
  }
  v45 = 0;
  v6 = ((__int64 (__fastcall *)(struct IStream *, _QWORD, __int64, __int64 *))a2->lpVtbl->Seek)(a2, 0, 1, &v45);
  if ( v6 < 0 )
  {
    v27 = GetMemLogObject();
    CMemoryLog::Write(v27, v6);
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_26;
    }
    v20 = 89;
LABEL_40:
    WPP_SF_d(*((_QWORD *)v19 + 2), v20, WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids, (unsigned int)v6);
LABEL_26:
    CInCritSec::~CInCritSec((CInCritSec *)v42);
    return (unsigned int)v6;
  }
  v7 = *(_DWORD *)SafeInt<unsigned long>::MixedSizeSubtraction<unsigned long>(&v40, v51, (unsigned int)v45);
  if ( v7 > *(_DWORD *)&g_ContextLimit )
    goto LABEL_27;
  v39 = 0;
  v8 = ((__int64 (__fastcall *)(struct IStream *, LONG *, __int64, int *))a2->lpVtbl->Read)(
         a2,
         &this[3].LockCount,
         4,
         &v39);
  if ( v8 < 0 )
  {
    v23 = GetMemLogObject();
    CMemoryLog::Write(v23, v8);
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_33;
    }
    v25 = 90;
    v26 = (unsigned int)v8;
    goto LABEL_53;
  }
  if ( v39 != 4 )
  {
    v28 = GetMemLogObject();
    CMemoryLog::Write(v28, -2147217397);
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_71;
    }
    v30 = 91;
    goto LABEL_70;
  }
  v9 = *(_DWORD *)SafeInt<unsigned long>::MixedSizeSubtraction<unsigned __int64>(&v40, v7, 4);
  if ( !this[3].LockCount )
    goto LABEL_13;
  LODWORD(v40) = this[3].LockCount;
  SafeInt<unsigned long>::operator*=<unsigned __int64>(&v40, 16);
  v10 = (unsigned int)v40;
  if ( (unsigned int)v40 > v9 )
  {
LABEL_27:
    CInCritSec::~CInCritSec((CInCritSec *)v42);
    return 2147500037LL;
  }
  CWin32DefaultArena::WbemMemFree(this[3].OwningThread);
  v11 = CWin32DefaultArena::WbemMemAlloc(saturated_mul((unsigned int)this[3].LockCount, 0x10u));
  this[3].OwningThread = v11;
  if ( !v11 )
  {
    v31 = GetMemLogObject();
    v8 = -2147217402;
    CMemoryLog::Write(v31, -2147217402);
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_33;
    }
    v25 = 92;
    v26 = 2147749894LL;
LABEL_53:
    v32 = *((_QWORD *)v24 + 2);
    goto LABEL_54;
  }
  v12 = ((__int64 (__fastcall *)(struct IStream *, void *, _QWORD, int *))a2->lpVtbl->Read)(a2, v11, v10, &v39);
  if ( v12 >= 0 )
  {
    if ( v39 != v10 )
    {
      v33 = GetMemLogObject();
      CMemoryLog::Write(v33, -2147217397);
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_71;
      }
      v30 = 94;
      goto LABEL_70;
    }
    if ( v9 < v10 )
    {
      pExceptionObject = 534;
      throw (SafeIntException *)&pExceptionObject;
    }
    v9 -= v10;
LABEL_13:
    v41 = 0;
    v8 = ((__int64 (__fastcall *)(struct IStream *, unsigned int *, __int64, int *))a2->lpVtbl->Read)(a2, &v41, 4, &v39);
    if ( v8 >= 0 )
    {
      if ( v39 == 4 )
      {
        v44 = *(_DWORD *)SafeInt<unsigned long>::MixedSizeSubtraction<unsigned __int64>(&v40, v9, 4);
        for ( i = 0; ; ++i )
        {
          if ( i >= v41 )
          {
            v6 = (*(__int64 (__fastcall **)(ULONG_PTR *, const struct _GUID *, void **))this[-1].SpinCount)(
                   &this[-1].SpinCount,
                   v48,
                   v47);
            goto LABEL_26;
          }
          v46 = 0;
          if ( __eh34_try(-1, 0) )
          {
            __eh34_scope_strut(0);
            v14 = (CWbemContext::CContextObj *)CWin32DefaultArena::WbemMemAlloc(0x28u);
            v40 = v14;
            if ( v14 )
              v15 = (CWbemContext::CContextObj *)((_QWORD (__stdcall *)(CWbemContext::CContextObj *, struct IStream *, unsigned int *))CWbemContext::CContextObj::CContextObj)(
                                                   v14,
                                                   a2,
                                                   &v44);
            else
              v15 = 0;
            v46 = v15;
          }
          if ( __eh34_catch(0) )
          {
            if ( __eh34_catch_type(0, &CX_MemoryException `RTTI Type Descriptor', 0) )
            {
              if ( v46 )
                CWbemContext::CContextObj::`scalar deleting destructor'(v46, (unsigned int)&v38);
              v35 = GetMemLogObject();
              CMemoryLog::Write(v35, -2147217402);
              if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  97,
                  WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids,
                  2147749894LL);
              }
              v8 = -2147217402;
              __eh34_try_continuation(0, &CX_MemoryException `RTTI Type Descriptor', &loc_180016EC2);
              goto LABEL_33;
            }
            if ( __eh34_catch_type(0, &_com_error `RTTI Type Descriptor', &v49) )
            {
              v36 = v49;
              if ( *((int *)v49 + 2) < 0 )
              {
                v37 = GetMemLogObject();
                CMemoryLog::Write(v37, *((_DWORD *)v36 + 2));
              }
              if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  98,
                  WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids,
                  *((unsigned int *)v36 + 2));
              }
              LODWORD(v40) = *((_DWORD *)v36 + 2);
              v8 = (int)v40;
              __eh34_try_continuation(0, &_com_error `RTTI Type Descriptor', &loc_180016ECC);
              goto LABEL_33;
            }
          }
          if ( !v15 )
            goto LABEL_27;
          if ( CFlexArray::Add((CFlexArray *)&this->SpinCount, v15) || !CFlexArray::Size((CFlexArray *)&this->SpinCount) )
          {
            CWbemContext::CContextObj::`scalar deleting destructor'(v15, v16);
            goto LABEL_27;
          }
        }
      }
      v34 = GetMemLogObject();
      CMemoryLog::Write(v34, -2147217397);
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_71:
        v8 = -2147217397;
        goto LABEL_33;
      }
      v30 = 96;
LABEL_70:
      WPP_SF_d(*((_QWORD *)v29 + 2), v30, WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids, 2147749899LL);
      goto LABEL_71;
    }
    v21 = GetMemLogObject();
    CMemoryLog::Write(v21, v8);
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_33;
    }
    v25 = 95;
    v26 = (unsigned int)v8;
    v32 = *((_QWORD *)WPP_GLOBAL_Control + 2);
LABEL_54:
    WPP_SF_d(v32, v25, WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids, v26);
    goto LABEL_33;
  }
  v22 = GetMemLogObject();
  CMemoryLog::Write(v22, v12);
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      93,
      WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids,
      (unsigned int)v12);
  }
  v8 = v12;
LABEL_33:
  CInCritSec::~CInCritSec((CInCritSec *)v42);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800168d0  push    rbx
0x1800168d2  push    rdi
0x1800168d3  push    r12
0x1800168d5  push    r13
0x1800168d7  push    r14
0x1800168d9  push    r15
0x1800168db  sub     rsp, 0E8h
0x1800168e2  mov     rax, cs:__security_cookie
0x1800168e9  xor     rax, rsp
0x1800168ec  mov     [rsp+118h+var_48], rax
0x1800168f4  mov     [rsp+118h+var_B0], r9
0x1800168f9  mov     [rsp+118h+var_A8], r8
0x1800168fe  mov     r15, rdx
0x180016901  mov     r13, rcx
0x180016904  lea     rdx, [rcx+0A0h]
0x18001690b  lea     rcx, [rsp+118h+var_D0]
0x180016910  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x180016916  nop
0x180016917  xor     edx, edx; Val
0x180016919  lea     r8d, [rdx+50h]; Size
0x18001691d  lea     rcx, [rsp+118h+var_98]; void *
0x180016925  call    memset_0
0x18001692a  mov     rax, [r15]
0x18001692d  xor     r8d, r8d
0x180016930  lea     rdx, [rsp+118h+var_98]
0x180016938  mov     rcx, r15
0x18001693b  mov     rax, [rax+60h]
0x18001693f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016944  mov     ebx, eax
0x180016946  test    eax, eax
0x180016948  js      loc_180016BB1
0x18001694e  xor     edx, edx
0x180016950  mov     [rsp+118h+var_C0], rdx
0x180016955  mov     rax, [r15]
0x180016958  lea     r9, [rsp+118h+var_C0]
0x18001695d  lea     r8d, [rdx+1]
0x180016961  mov     rcx, r15
0x180016964  mov     rax, [rax+28h]
0x180016968  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001696d  mov     ebx, eax
0x18001696f  test    eax, eax
0x180016971  js      loc_180016CB0
0x180016977  mov     r8d, dword ptr [rsp+118h+var_C0]
0x18001697c  mov     edx, [rsp+118h+var_88]
0x180016983  lea     rcx, [rsp+118h+var_E0]
0x180016988  call    ??$MixedSizeSubtraction@K@?$SafeInt@K@@CA?AV0@V0@K@Z; SafeInt<ulong>::MixedSizeSubtraction<ulong>(SafeInt<ulong>,ulong)
0x18001698d  mov     ebx, [rax]
0x18001698f  cmp     ebx, cs:?g_ContextLimit@@3KA; ulong g_ContextLimit
0x180016995  ja      loc_180016B9F
0x18001699b  mov     [rsp+118h+var_E8], 0
0x1800169a3  lea     r14, [r13+80h]
0x1800169aa  mov     rax, [r15]
0x1800169ad  lea     r9, [rsp+118h+var_E8]
0x1800169b2  mov     r12d, 4
0x1800169b8  mov     r8d, r12d
0x1800169bb  mov     rdx, r14
0x1800169be  mov     rcx, r15
0x1800169c1  mov     rax, [rax+18h]
0x1800169c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169ca  mov     edi, eax
0x1800169cc  test    eax, eax
0x1800169ce  js      loc_180016C56
0x1800169d4  cmp     [rsp+118h+var_E8], r12d
0x1800169d9  jnz     loc_180016CF0
0x1800169df  mov     r8d, r12d
0x1800169e2  mov     edx, ebx
0x1800169e4  lea     rcx, [rsp+118h+var_E0]
0x1800169e9  call    ??$MixedSizeSubtraction@_K@?$SafeInt@K@@CA?AV0@V0@_K@Z; SafeInt<ulong>::MixedSizeSubtraction<unsigned __int64>(SafeInt<ulong>,unsigned __int64)
0x1800169ee  mov     ebx, [rax]
0x1800169f0  mov     eax, [r13+80h]
0x1800169f7  test    eax, eax
0x1800169f9  jz      loc_180016A91
0x1800169ff  mov     dword ptr [rsp+118h+var_E0], eax
0x180016a03  lea     edx, [r12+0Ch]
0x180016a08  lea     rcx, [rsp+118h+var_E0]
0x180016a0d  call    ??$?X_K@?$SafeInt@K@@QEAAAEAV0@_K@Z; SafeInt<ulong>::operator*=<unsigned __int64>(unsigned __int64)
0x180016a12  mov     edi, dword ptr [rsp+118h+var_E0]
0x180016a16  cmp     edi, ebx
0x180016a18  ja      loc_180016B9F
0x180016a1e  mov     rcx, [r13+88h]
0x180016a25  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180016a2b  mov     ecx, [r14]
0x180016a2e  lea     eax, [r12+0Ch]
0x180016a33  mul     rcx
0x180016a36  lea     rcx, [r12-5]
0x180016a3b  cmovb   rax, rcx
0x180016a3f  mov     rcx, rax
0x180016a42  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180016a48  mov     rdx, rax
0x180016a4b  mov     [r13+88h], rax
0x180016a52  test    rax, rax
0x180016a55  jz      loc_180016D39
0x180016a5b  mov     rax, [r15]
0x180016a5e  lea     r9, [rsp+118h+var_E8]
0x180016a63  mov     r8d, edi
0x180016a66  mov     rcx, r15
0x180016a69  mov     rax, [rax+18h]
0x180016a6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a72  mov     r14d, eax
0x180016a75  test    eax, eax
0x180016a77  js      loc_180016C28
0x180016a7d  cmp     [rsp+118h+var_E8], edi
0x180016a81  jnz     loc_180016DDB
0x180016a87  cmp     ebx, edi
0x180016a89  jb      loc_180016E21
0x180016a8f  sub     ebx, edi
0x180016a91  mov     [rsp+118h+var_D8], 0
0x180016a99  mov     rax, [r15]
0x180016a9c  lea     r9, [rsp+118h+var_E8]
0x180016aa1  mov     r14, r12
0x180016aa4  mov     r8d, r14d
0x180016aa7  lea     rdx, [rsp+118h+var_D8]
0x180016aac  mov     rcx, r15
0x180016aaf  mov     rax, [rax+18h]
0x180016ab3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ab8  mov     edi, eax
0x180016aba  test    eax, eax
0x180016abc  js      loc_180016BEE
0x180016ac2  cmp     [rsp+118h+var_E8], r14d
0x180016ac7  jnz     loc_180016E56
0x180016acd  mov     r8, r12
0x180016ad0  mov     edx, ebx
0x180016ad2  lea     rcx, [rsp+118h+var_E0]
0x180016ad7  call    ??$MixedSizeSubtraction@_K@?$SafeInt@K@@CA?AV0@V0@_K@Z; SafeInt<ulong>::MixedSizeSubtraction<unsigned __int64>(SafeInt<ulong>,unsigned __int64)
0x180016adc  mov     ecx, [rax]
0x180016ade  mov     [rsp+118h+var_C4], ecx
0x180016ae2  xor     edi, edi
0x180016ae4  cmp     edi, [rsp+118h+var_D8]
0x180016ae8  jnb     short loc_180016B54
0x180016aea  mov     [rsp+118h+var_B8], 0
0x180016af3  mov     ecx, 28h ; '('
0x180016af8  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180016afe  mov     [rsp+118h+var_E0], rax
0x180016b03  test    rax, rax
0x180016b06  jz      loc_180016EAE
0x180016b0c  lea     r8, [rsp+118h+var_C4]; unsigned int *
0x180016b11  mov     rdx, r15; struct IStream *
0x180016b14  mov     rcx, rax; this
0x180016b17  call    ??0CContextObj@CWbemContext@@QEAA@PEAUIStream@@AEAK@Z; CWbemContext::CContextObj::CContextObj(IStream *,ulong &)
0x180016b1c  mov     rbx, rax
0x180016b1f  mov     [rsp+118h+var_B8], rbx
0x180016b24  test    rbx, rbx
0x180016b27  jz      short loc_180016B9F
0x180016b29  mov     rdx, rbx
0x180016b2c  lea     rcx, [r13+20h]
0x180016b30  call    cs:__imp_?Add@CFlexArray@@QEAAHPEAX@Z; CFlexArray::Add(void *)
0x180016b36  test    eax, eax
0x180016b38  jnz     loc_180016EB5
0x180016b3e  lea     rcx, [r13+20h]
0x180016b42  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x180016b48  test    eax, eax
0x180016b4a  jz      loc_180016EB5
0x180016b50  inc     edi
0x180016b52  jmp     short loc_180016AE4
0x180016b54  mov     rax, [r13-8]
0x180016b58  mov     r8, [rsp+118h+var_B0]
0x180016b5d  mov     rdx, [rsp+118h+var_A8]
0x180016b62  lea     rcx, [r13-8]
0x180016b66  mov     rax, [rax]
0x180016b69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b6e  mov     ebx, eax
0x180016b70  lea     rcx, [rsp+118h+var_D0]
0x180016b75  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x180016b7b  mov     eax, ebx
0x180016b7d  mov     rcx, [rsp+118h+var_48]
0x180016b85  xor     rcx, rsp; StackCookie
0x180016b88  call    __security_check_cookie
0x180016b8d  add     rsp, 0E8h
0x180016b94  pop     r15
0x180016b96  pop     r14
0x180016b98  pop     r13
0x180016b9a  pop     r12
0x180016b9c  pop     rdi
0x180016b9d  pop     rbx
0x180016b9e  retn
0x180016b9f  lea     rcx, [rsp+118h+var_D0]
0x180016ba4  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x180016baa  mov     eax, 80004005h
0x180016baf  jmp     short loc_180016B7D
0x180016bb1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180016bb7  nop
0x180016bb8  mov     edx, ebx
0x180016bba  mov     rcx, rax
0x180016bbd  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180016bc3  lea     rcx, WPP_GLOBAL_Control
0x180016bca  mov     r10, cs:WPP_GLOBAL_Control
0x180016bd1  cmp     r10, rcx
0x180016bd4  jz      short loc_180016B70
0x180016bd6  test    byte ptr [r10+1Ch], 1
0x180016bdb  jz      short loc_180016B70
0x180016bdd  cmp     byte ptr [r10+19h], 2
0x180016be2  jb      short loc_180016B70
0x180016be4  mov     edx, 58h ; 'X'
0x180016be9  jmp     loc_180016C98
0x180016bee  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180016bf4  mov     edx, edi
0x180016bf6  mov     rcx, rax
0x180016bf9  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180016bff  lea     rcx, WPP_GLOBAL_Control
0x180016c06  mov     r10, cs:WPP_GLOBAL_Control
0x180016c0d  cmp     r10, rcx
0x180016c10  jnz     loc_180016E3B
0x180016c16  lea     rcx, [rsp+118h+var_D0]
0x180016c1b  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x180016c21  mov     eax, edi
0x180016c23  jmp     loc_180016B7D
0x180016c28  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180016c2e  mov     edx, r14d
0x180016c31  mov     rcx, rax
0x180016c34  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180016c3a  lea     rcx, WPP_GLOBAL_Control
0x180016c41  mov     r10, cs:WPP_GLOBAL_Control
0x180016c48  cmp     r10, rcx
0x180016c4b  jnz     loc_180016DA8
0x180016c51  mov     edi, r14d
0x180016c54  jmp     short loc_180016C16
0x180016c56  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180016c5c  mov     edx, edi
0x180016c5e  mov     rcx, rax
0x180016c61  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180016c67  lea     rcx, WPP_GLOBAL_Control
0x180016c6e  mov     rax, cs:WPP_GLOBAL_Control
0x180016c75  cmp     rax, rcx
0x180016c78  jz      short loc_180016C16
0x180016c7a  test    byte ptr [rax+1Ch], 1
0x180016c7e  jz      short loc_180016C16
0x180016c80  cmp     byte ptr [rax+19h], 2
0x180016c84  jb      short loc_180016C16
0x180016c86  mov     edx, 5Ah ; 'Z'
0x180016c8b  mov     r9d, edi
0x180016c8e  jmp     loc_180016D85
0x180016c93  mov     edx, 59h ; 'Y'
0x180016c98  mov     r9d, ebx
0x180016c9b  lea     r8, WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids
0x180016ca2  mov     rcx, [r10+10h]
0x180016ca6  call    WPP_SF_d
0x180016cab  jmp     loc_180016B70
0x180016cb0  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180016cb6  mov     edx, ebx
0x180016cb8  mov     rcx, rax
0x180016cbb  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180016cc1  lea     rcx, WPP_GLOBAL_Control
0x180016cc8  mov     r10, cs:WPP_GLOBAL_Control
0x180016ccf  cmp     r10, rcx
0x180016cd2  jz      loc_180016B70
0x180016cd8  test    byte ptr [r10+1Ch], 1
0x180016cdd  jz      loc_180016B70
0x180016ce3  cmp     byte ptr [r10+19h], 2
0x180016ce8  jb      loc_180016B70
0x180016cee  jmp     short loc_180016C93
0x180016cf0  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180016cf6  mov     edx, 8004100Bh
0x180016cfb  mov     rcx, rax
0x180016cfe  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180016d04  lea     rcx, WPP_GLOBAL_Control
0x180016d0b  mov     rax, cs:WPP_GLOBAL_Control
0x180016d12  cmp     rax, rcx
0x180016d15  jz      loc_180016EA4
0x180016d1b  test    byte ptr [rax+1Ch], 1
0x180016d1f  jz      loc_180016EA4
0x180016d25  cmp     byte ptr [rax+19h], 2
0x180016d29  jb      loc_180016EA4
0x180016d2f  mov     edx, 5Bh ; '['
0x180016d34  jmp     loc_180016E8E
0x180016d39  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180016d3f  mov     edi, 80041006h
0x180016d44  mov     edx, edi
0x180016d46  mov     rcx, rax
0x180016d49  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180016d4f  lea     rcx, WPP_GLOBAL_Control
0x180016d56  mov     rax, cs:WPP_GLOBAL_Control
0x180016d5d  cmp     rax, rcx
0x180016d60  jz      loc_180016C16
0x180016d66  test    byte ptr [rax+1Ch], 1
0x180016d6a  jz      loc_180016C16
0x180016d70  cmp     byte ptr [rax+19h], 2
0x180016d74  jb      loc_180016C16
0x180016d7a  mov     edx, 5Ch ; '\'
0x180016d7f  mov     r9d, 80041006h
0x180016d85  mov     rcx, [rax+10h]
0x180016d89  jmp     short loc_180016D97
0x180016d8b  mov     edx, 5Fh ; '_'
0x180016d90  mov     r9d, edi
0x180016d93  mov     rcx, [r10+10h]
0x180016d97  lea     r8, WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids
0x180016d9e  call    WPP_SF_d
0x180016da3  jmp     loc_180016C16
0x180016da8  test    byte ptr [r10+1Ch], 1
0x180016dad  jz      loc_180016C51
0x180016db3  cmp     byte ptr [r10+19h], 2
0x180016db8  jb      loc_180016C51
0x180016dbe  mov     edx, 5Dh ; ']'
0x180016dc3  mov     r9d, r14d
0x180016dc6  lea     r8, WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids
0x180016dcd  mov     rcx, [r10+10h]
0x180016dd1  call    WPP_SF_d
0x180016dd6  jmp     loc_180016C51
0x180016ddb  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180016de1  mov     edx, 8004100Bh
0x180016de6  mov     rcx, rax
  ... truncated ...
```
