# CWbemContext::CWbemContext(CWbemContext const &,ulong)

- ea: `0x1800381dc`
- end: `0x18003854d`
- name: `??0CWbemContext@@QEAA@AEBV0@K@Z`
- size: `881`
- prototype: `CWbemContext *__fastcall(CWbemContext *__hidden this, const struct CWbemContext *, unsigned int)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180037cb0`
- `0x180037e10`

## callees

- `0x180035b08`
- `0x1800381dc`
- `0x180038554`
- `0x1800385b8`
- `0x1800388c0`
- `0x180038ad4`
- `0x18006fa4c`
- `0x18006fa66`
- `0x18009e010`

## import_xrefs

- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x1800382af`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x1800382af`
- `wbemcomn!GetMemLogObject` at `0x1800383d6`
- `wbemcomn!GetMemLogObject` at `0x180038471`
- `wbemcomn!GetMemLogObject` at `0x1800384ec`
- `wbemcomn!GetMemLogObject` at `0x1800383d6`
- `wbemcomn!GetMemLogObject` at `0x180038471`
- `wbemcomn!GetMemLogObject` at `0x1800384ec`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180038274`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18003831d`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180038274`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18003831d`
- `wbemcomn!?Add@CFlexArray@@QEAAHPEAX@Z` at `0x18003830b`
- `wbemcomn!?Add@CFlexArray@@QEAAHPEAX@Z` at `0x18003830b`
- `wbemcomn!??0CCritSec@@QEAA@XZ` at `0x18003825e`
- `wbemcomn!??0CCritSec@@QEAA@XZ` at `0x18003825e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800383e4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003847f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800384fa`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800383e4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003847f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800384fa`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180038291`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180038369`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180038291`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180038369`
- `OLEAUT32!__imp_VariantInit` at `0x1800382cf`
- `OLEAUT32!__imp_VariantInit` at `0x1800382cf`
- `OLEAUT32!__imp_VariantCopy` at `0x1800382e8`
- `OLEAUT32!__imp_VariantCopy` at `0x1800382e8`

## pseudocode

```c
CWbemContext *__fastcall CWbemContext::CWbemContext(CWbemContext *this, const struct CWbemContext *a2, unsigned int a3)
{
  unsigned int v3; // r12d
  const struct CWbemContext *v4; // r13
  CWbemContext *v5; // rsi
  int i; // r15d
  char *v7; // r14
  char *v8; // rbx
  HRESULT v9; // eax
  struct IErrorInfo *v10; // rdx
  int v11; // ecx
  char *v12; // rdx
  unsigned int v13; // eax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v16; // rax
  CMemoryLog *v17; // rax
  char pExceptionObject; // [rsp+20h] [rbp-58h] BYREF
  char v19; // [rsp+21h] [rbp-57h] BYREF
  char v20; // [rsp+22h] [rbp-56h] BYREF
  int v21; // [rsp+24h] [rbp-54h] BYREF
  BSTR *v22; // [rsp+30h] [rbp-48h]
  char *v23; // [rsp+38h] [rbp-40h]

  v3 = a3;
  v4 = a2;
  v5 = this;
  *(_QWORD *)this = &CWbemContext::`vftable'{for `IWbemContext'};
  *((_QWORD *)this + 1) = &CWbemContext::`vftable'{for `IMarshal'};
  *((_QWORD *)this + 2) = &CWbemContext::`vftable'{for `IWbemCausalityAccess'};
  *((_DWORD *)this + 6) = 0;
  *((_DWORD *)this + 7) = -1;
  *((_QWORD *)this + 4) = *((_QWORD *)a2 + 4);
  CUniquePointerArray<CWbemContext::CContextObj>::CUniquePointerArray<CWbemContext::CContextObj>((char *)this + 40);
  *((_QWORD *)v5 + 19) = 0;
  *((_DWORD *)v5 + 40) = 0;
  CCritSec::CCritSec((CWbemContext *)((char *)v5 + 168));
  for ( i = 0; i < CFlexArray::Size((const struct CWbemContext *)((char *)v4 + 40)); ++i )
  {
    v22 = 0;
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v7 = (char *)CWin32DefaultArena::WbemMemAlloc(0x28u);
      v23 = v7;
      if ( v7 )
      {
        v8 = (char *)CFlexArray::GetAt((const struct CWbemContext *)((char *)v4 + 40), i);
        clone(v7, *(_QWORD *)v8);
        *((_DWORD *)v7 + 2) = *((_DWORD *)v8 + 2);
        VariantInit((VARIANTARG *)(v7 + 16));
        if ( *((_WORD *)v8 + 8) == 36 )
        {
          MemLogObject = GetMemLogObject();
          CMemoryLog::Write(MemLogObject, -2);
          if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_s(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              38,
              WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids,
              "CX_MemoryException()");
          }
          throw (CX_MemoryException *)&pExceptionObject;
        }
        v9 = VariantCopy((VARIANTARG *)(v7 + 16), (const VARIANTARG *)(v8 + 16));
        if ( v9 < 0 )
          _com_raise_error(v9, v10);
      }
      else
      {
        v7 = 0;
      }
      v22 = (BSTR *)v7;
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &CX_MemoryException `RTTI Type Descriptor', 0) )
      {
        if ( v22 )
          CWbemContext::CContextObj::`scalar deleting destructor'(v22);
        v22 = 0;
        v5 = this;
        v3 = a3;
        v4 = a2;
        v7 = 0;
        __eh34_try_continuation(0, &CX_MemoryException `RTTI Type Descriptor', &loc_18003843F);
      }
    }
    if ( !v7 )
      goto LABEL_25;
    if ( CFlexArray::Add((CWbemContext *)((char *)v5 + 40), v7) || !CFlexArray::Size((CWbemContext *)((char *)v5 + 40)) )
    {
      CWbemContext::CContextObj::`scalar deleting destructor'((BSTR *)v7);
LABEL_25:
      v16 = GetMemLogObject();
      CMemoryLog::Write(v16, -2);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          48,
          WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids,
          "CX_MemoryException()");
      }
      throw (CX_MemoryException *)&v19;
    }
  }
  v11 = *((_DWORD *)v4 + 34);
  if ( ~v11 < v3 )
  {
    v21 = 534;
    throw (SafeIntException *)&v21;
  }
  *((_DWORD *)v5 + 34) = v11 + v3;
  v12 = (char *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v11 + v3, 0x10u));
  *((_QWORD *)v5 + 18) = v12;
  if ( !v12 )
  {
    v17 = GetMemLogObject();
    CMemoryLog::Write(v17, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        49,
        WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&v20;
  }
  v13 = *((_DWORD *)v4 + 34);
  if ( v13 )
    memcpy_0(&v12[16 * v3], *((const void **)v4 + 18), 16LL * v13);
  (***((void (__fastcall ****)(_QWORD, CWbemContext *))v5 + 4))(*((_QWORD *)v5 + 4), v5);
  return v5;
}

```

## disassembly

```asm
0x1800381dc  mov     [rsp+arg_10], r8d
0x1800381e1  mov     [rsp+arg_8], rdx
0x1800381e6  mov     [rsp+arg_0], rcx
0x1800381eb  push    rbx
0x1800381ec  push    rsi
0x1800381ed  push    r12
0x1800381ef  push    r13
0x1800381f1  push    r14
0x1800381f3  push    r15
0x1800381f5  sub     rsp, 48h
0x1800381f9  mov     r12d, r8d
0x1800381fc  mov     r13, rdx
0x1800381ff  mov     rsi, rcx
0x180038202  lea     rax, ??_7CWbemContext@@6BIWbemContext@@@; const CWbemContext::`vftable'{for `IWbemContext'}
0x180038209  mov     [rcx], rax
0x18003820c  lea     rax, ??_7CWbemContext@@6BIMarshal@@@; const CWbemContext::`vftable'{for `IMarshal'}
0x180038213  mov     [rcx+8], rax
0x180038217  lea     rax, ??_7CWbemContext@@6BIWbemCausalityAccess@@@; const CWbemContext::`vftable'{for `IWbemCausalityAccess'}
0x18003821e  mov     [rcx+10h], rax
0x180038222  mov     dword ptr [rcx+18h], 0
0x180038229  mov     dword ptr [rcx+1Ch], 0FFFFFFFFh
0x180038230  mov     rax, [rdx+20h]
0x180038234  mov     [rcx+20h], rax
0x180038238  add     rcx, 28h ; '('
0x18003823c  call    ??0?$CUniquePointerArray@UCContextObj@CWbemContext@@@@QEAA@XZ; CUniquePointerArray<CWbemContext::CContextObj>::CUniquePointerArray<CWbemContext::CContextObj>(void)
0x180038241  nop
0x180038242  mov     qword ptr [rsi+98h], 0
0x18003824d  mov     dword ptr [rsi+0A0h], 0
0x180038257  lea     rcx, [rsi+0A8h]
0x18003825e  call    cs:__imp_??0CCritSec@@QEAA@XZ; CCritSec::CCritSec(void)
0x180038264  nop
0x180038265  xor     r15d, r15d
0x180038268  mov     [rsp+78h+arg_18], r15d
0x180038270  lea     rcx, [r13+28h]
0x180038274  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x18003827a  cmp     r15d, eax
0x18003827d  jge     loc_180038333
0x180038283  mov     [rsp+78h+var_48], 0
0x18003828c  mov     ecx, 28h ; '('
0x180038291  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180038297  mov     r14, rax
0x18003829a  mov     [rsp+78h+var_40], rax
0x18003829f  test    rax, rax
0x1800382a2  jz      loc_180038437
0x1800382a8  mov     edx, r15d
0x1800382ab  lea     rcx, [r13+28h]
0x1800382af  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x1800382b5  mov     rbx, rax
0x1800382b8  mov     rdx, [rax]
0x1800382bb  mov     rcx, r14
0x1800382be  call    ?clone@@YA?AVauto_bstr@@PEBG@Z; clone(ushort const *)
0x1800382c3  nop
0x1800382c4  mov     ecx, [rbx+8]
0x1800382c7  mov     [r14+8], ecx
0x1800382cb  lea     rcx, [r14+10h]; pvarg
0x1800382cf  call    cs:__imp_VariantInit
0x1800382d5  nop
0x1800382d6  lea     rdx, [rbx+10h]; pvargSrc
0x1800382da  cmp     word ptr [rdx], 24h ; '$'
0x1800382de  jz      loc_1800383D6
0x1800382e4  lea     rcx, [r14+10h]; pvargDest
0x1800382e8  call    cs:__imp_VariantCopy
0x1800382ee  test    eax, eax
0x1800382f0  js      loc_1800383CF
0x1800382f6  mov     [rsp+78h+var_48], r14
0x1800382fb  test    r14, r14
0x1800382fe  jz      loc_180038471
0x180038304  mov     rdx, r14
0x180038307  lea     rcx, [rsi+28h]
0x18003830b  call    cs:__imp_?Add@CFlexArray@@QEAAHPEAX@Z; CFlexArray::Add(void *)
0x180038311  test    eax, eax
0x180038313  jnz     loc_180038469
0x180038319  lea     rcx, [rsi+28h]
0x18003831d  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x180038323  test    eax, eax
0x180038325  jz      loc_180038469
0x18003832b  inc     r15d
0x18003832e  jmp     loc_180038268
0x180038333  mov     ecx, [r13+88h]
0x18003833a  mov     eax, ecx
0x18003833c  not     eax
0x18003833e  cmp     eax, r12d
0x180038341  jb      loc_1800384D2
0x180038347  lea     eax, [rcx+r12]
0x18003834b  mov     [rsi+88h], eax
0x180038351  mov     ecx, eax
0x180038353  mov     eax, 10h
0x180038358  mul     rcx
0x18003835b  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180038362  cmovb   rax, rcx
0x180038366  mov     rcx, rax
0x180038369  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18003836f  mov     rdx, rax
0x180038372  mov     [rsi+90h], rax
0x180038379  test    rax, rax
0x18003837c  jz      loc_1800384EC
0x180038382  mov     eax, [r13+88h]
0x180038389  test    eax, eax
0x18003838b  jz      short loc_1800383AA
0x18003838d  mov     r8d, eax
0x180038390  shl     r8, 4; Size
0x180038394  mov     ecx, r12d
0x180038397  shl     rcx, 4
0x18003839b  add     rcx, rdx; void *
0x18003839e  mov     rdx, [r13+90h]; Src
0x1800383a5  call    memcpy_0
0x1800383aa  mov     rcx, [rsi+20h]
0x1800383ae  mov     rax, [rcx]
0x1800383b1  mov     rdx, rsi
0x1800383b4  mov     rax, [rax]
0x1800383b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800383bc  nop
0x1800383bd  mov     rax, rsi
0x1800383c0  add     rsp, 48h
0x1800383c4  pop     r15
0x1800383c6  pop     r14
0x1800383c8  pop     r13
0x1800383ca  pop     r12
0x1800383cc  pop     rsi
0x1800383cd  pop     rbx
0x1800383ce  retn
0x1800383cf  mov     ecx, eax; int
0x1800383d1  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x1800383d6  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800383dc  mov     edx, 0FFFFFFFEh
0x1800383e1  mov     rcx, rax
0x1800383e4  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800383ea  lea     rax, WPP_GLOBAL_Control
0x1800383f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800383f8  cmp     rcx, rax
0x1800383fb  jz      short loc_180038425
0x1800383fd  test    byte ptr [rcx+1Ch], 1
0x180038401  jz      short loc_180038425
0x180038403  cmp     byte ptr [rcx+19h], 2
0x180038407  jb      short loc_180038425
0x180038409  mov     edx, 26h ; '&'
0x18003840e  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x180038415  lea     r8, WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids
0x18003841c  mov     rcx, [rcx+10h]
0x180038420  call    WPP_SF_s
0x180038425  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x18003842c  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180038431  call    _CxxThrowException_0
0x180038437  xor     r14d, r14d
0x18003843a  jmp     loc_1800382F6
0x18003843f  mov     rsi, [rsp+78h+arg_0]
0x180038447  mov     r12d, [rsp+78h+arg_10]
0x18003844f  mov     r13, [rsp+78h+arg_8]
0x180038457  mov     r15d, [rsp+78h+arg_18]
0x18003845f  mov     r14, [rsp+78h+var_48]
0x180038464  jmp     loc_1800382FB
0x180038469  mov     rcx, r14; this
0x18003846c  call    ??_GCContextObj@CWbemContext@@QEAAPEAXI@Z; CWbemContext::CContextObj::`scalar deleting destructor'(uint)
0x180038471  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180038477  mov     edx, 0FFFFFFFEh
0x18003847c  mov     rcx, rax
0x18003847f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180038485  lea     rax, WPP_GLOBAL_Control
0x18003848c  mov     rcx, cs:WPP_GLOBAL_Control
0x180038493  cmp     rcx, rax
0x180038496  jz      short loc_1800384C0
0x180038498  test    byte ptr [rcx+1Ch], 1
0x18003849c  jz      short loc_1800384C0
0x18003849e  cmp     byte ptr [rcx+19h], 2
0x1800384a2  jb      short loc_1800384C0
0x1800384a4  mov     edx, 30h ; '0'
0x1800384a9  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800384b0  lea     r8, WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids
0x1800384b7  mov     rcx, [rcx+10h]
0x1800384bb  call    WPP_SF_s
0x1800384c0  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800384c7  lea     rcx, [rsp+78h+var_57]; pExceptionObject
0x1800384cc  call    _CxxThrowException_0
0x1800384d2  mov     [rsp+78h+var_54], 216h
0x1800384da  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x1800384e1  lea     rcx, [rsp+78h+var_54]; pExceptionObject
0x1800384e6  call    _CxxThrowException_0
0x1800384ec  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800384f2  mov     edx, 0FFFFFFFEh
0x1800384f7  mov     rcx, rax
0x1800384fa  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180038500  lea     rax, WPP_GLOBAL_Control
0x180038507  mov     rcx, cs:WPP_GLOBAL_Control
0x18003850e  cmp     rcx, rax
0x180038511  jz      short loc_18003853B
0x180038513  test    byte ptr [rcx+1Ch], 1
0x180038517  jz      short loc_18003853B
0x180038519  cmp     byte ptr [rcx+19h], 2
0x18003851d  jb      short loc_18003853B
0x18003851f  mov     edx, 31h ; '1'
0x180038524  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x18003852b  lea     r8, WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids
0x180038532  mov     rcx, [rcx+10h]
0x180038536  call    WPP_SF_s
0x18003853b  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x180038542  lea     rcx, [rsp+78h+var_56]; pExceptionObject
0x180038547  call    _CxxThrowException_0
```
