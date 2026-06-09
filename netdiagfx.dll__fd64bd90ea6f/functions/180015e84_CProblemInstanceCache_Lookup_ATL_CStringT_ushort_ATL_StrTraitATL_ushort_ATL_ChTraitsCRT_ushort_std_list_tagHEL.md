# CProblemInstanceCache::Lookup(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,std::list<tagHELPER_ATTRIBUTE,std::allocator<tagHELPER_ATTRIBUTE>> const *,_GUID,tagLIFE_TIME,unsigned __int64)

- ea: `0x180015e84`
- end: `0x1800160a2`
- name: `?Lookup@CProblemInstanceCache@@QEAAPEAVProblemInstance@@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBV?$list@UtagHELPER_ATTRIBUTE@@V?$allocator@UtagHELPER_ATTRIBUTE@@@std@@@std@@U_GUID@@UtagLIFE_TIME@@_K@Z`
- size: `542`
- prototype: `__int64 __fastcall(int, int, int, int, FILETIME *lpFileTime2)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180013724`

## callees

- `0x180001ff4`
- `0x18000579c`
- `0x180006d58`
- `0x18000bca0`
- `0x18000c42c`
- `0x180011950`
- `0x180014e54`
- `0x1800152e0`
- `0x180015e30`
- `0x180015e84`
- `0x180016414`
- `0x18001b3a8`
- `0x18002c840`
- `0x18002f010`

## import_xrefs

- `KERNEL32!CompareFileTime` at `0x180015f80`
- `KERNEL32!CompareFileTime` at `0x180015f9f`
- `KERNEL32!CompareFileTime` at `0x180015f80`
- `KERNEL32!CompareFileTime` at `0x180015f9f`

## string_xrefs

- `0x180015fe8`: `Cache Hit for HelperClass: %s`
- `0x180016034`: `Cache Miss for HelperClass: %s`

## pseudocode

```c
FILETIME *__fastcall CProblemInstanceCache::Lookup(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        _QWORD *a4,
        FILETIME *lpFileTime2)
{
  void *v9; // rax
  __int64 v10; // rax
  CProblemInstanceKey *v11; // rsi
  char v12; // r15
  char v13; // al
  unsigned __int64 v14; // rdx
  FILETIME *v15; // rdi
  __int64 v16; // rax
  __int64 v17; // rsi
  ProblemInstance *v18; // rbx
  ProblemInstance *v19; // rbx
  ProblemInstance *v21; // [rsp+30h] [rbp-20h] BYREF
  unsigned __int64 v22; // [rsp+38h] [rbp-18h] BYREF
  __int64 v23; // [rsp+40h] [rbp-10h]

  v23 = a3;
  v21 = 0;
  ATL::CFileTime::GetTickCount((struct _FILETIME *)&v22);
  v9 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v9 || (v10 = CProblemInstanceKey::CProblemInstanceKey(v9, a2, a3), (v11 = (CProblemInstanceKey *)v10) == 0) )
  {
LABEL_22:
    v15 = 0;
    goto LABEL_23;
  }
  v12 = 0;
  v13 = ATL::CAtlMap<CProblemInstanceKey,ProblemInstance *,ATL::CElementTraits<CProblemInstanceKey>,ATL::CElementTraits<ProblemInstance *>>::Lookup(
          a1,
          v10,
          &v21);
  v15 = (FILETIME *)v21;
  if ( v13 )
  {
    v14 = *((_QWORD *)v21 + 8);
    if ( v22 <= v14 )
      goto LABEL_9;
    v16 = *((_QWORD *)v21 + 34) - *a4;
    if ( !v16 )
      v16 = *((_QWORD *)v21 + 35) - a4[1];
    if ( v16 )
    {
      ATL::CAtlMap<CProblemInstanceKey,ProblemInstance *,ATL::CElementTraits<CProblemInstanceKey>,ATL::CElementTraits<ProblemInstance *>>::RemoveKey(
        a1,
        v11);
      ProblemInstance::Dereference((ProblemInstance *)v15);
    }
    else
    {
LABEL_9:
      v12 = 1;
      if ( lpFileTime2->dwHighDateTime && CompareFileTime((const FILETIME *)v21 + 6, lpFileTime2) > 0 )
        v15[6] = *lpFileTime2;
      if ( lpFileTime2[1].dwHighDateTime && CompareFileTime(lpFileTime2 + 1, v15 + 7) > 0 )
        v15[7] = lpFileTime2[1];
    }
  }
  CProblemInstanceKey::`scalar deleting destructor'(v11, v14);
  v17 = 0;
  if ( NetworkDiagnosticsEngine::Instance() )
    v17 = *(_QWORD *)NetworkDiagnosticsEngine::Instance();
  if ( !v12 )
  {
    if ( v17 )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v21);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        (__int64)&v21,
        (__int64)L"Cache Miss for HelperClass: %s",
        *a2);
      v19 = v21;
      (*(void (__fastcall **)(__int64, __int64, ProblemInstance *, __int64))(*(_QWORD *)v17 + 112LL))(v17, 4, v21, v23);
      ATL::CStringData::Release((ProblemInstance *)((char *)v19 - 24));
    }
    goto LABEL_22;
  }
  if ( v17 )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v21);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      (__int64)&v21,
      (__int64)L"Cache Hit for HelperClass: %s",
      *a2);
    v18 = v21;
    (*(void (__fastcall **)(__int64, __int64, ProblemInstance *, __int64))(*(_QWORD *)v17 + 112LL))(v17, 4, v21, v23);
    ATL::CStringData::Release((ProblemInstance *)((char *)v18 - 24));
  }
LABEL_23:
  ATL::CStringData::Release((ATL::CStringData *)(*a2 - 24LL));
  return v15;
}

```

## disassembly

```asm
0x180015e84  mov     [rsp-38h+arg_18], rbx
0x180015e89  push    rbp
0x180015e8a  push    rsi
0x180015e8b  push    rdi
0x180015e8c  push    r12
0x180015e8e  push    r13
0x180015e90  push    r14
0x180015e92  push    r15
0x180015e94  mov     rbp, rsp
0x180015e97  sub     rsp, 50h
0x180015e9b  mov     rax, cs:__security_cookie
0x180015ea2  xor     rax, rsp
0x180015ea5  mov     [rbp+var_8], rax
0x180015ea9  mov     r14, r9
0x180015eac  mov     rdi, r8
0x180015eaf  mov     [rbp+var_10], r8
0x180015eb3  mov     r12, rdx
0x180015eb6  mov     r13, rcx
0x180015eb9  mov     rbx, [rbp+lpFileTime2]
0x180015ebd  mov     [rbp+var_20], 0
0x180015ec5  lea     rcx, [rbp+var_18]
0x180015ec9  call    ?GetTickCount@CFileTime@ATL@@SA?AV12@XZ; ATL::CFileTime::GetTickCount(void)
0x180015ece  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180015ed5  mov     ecx, 18h; unsigned __int64
0x180015eda  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180015edf  test    rax, rax
0x180015ee2  jz      loc_18001606C
0x180015ee8  mov     r8, rdi
0x180015eeb  mov     rdx, r12
0x180015eee  mov     rcx, rax
0x180015ef1  call    ??0CProblemInstanceKey@@QEAA@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBV?$list@UtagHELPER_ATTRIBUTE@@V?$allocator@UtagHELPER_ATTRIBUTE@@@std@@@std@@@Z; CProblemInstanceKey::CProblemInstanceKey(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,std::list<tagHELPER_ATTRIBUTE> const *)
0x180015ef6  mov     rsi, rax
0x180015ef9  test    rax, rax
0x180015efc  jz      loc_18001606C
0x180015f02  xor     r15b, r15b
0x180015f05  lea     r8, [rbp+var_20]
0x180015f09  mov     rdx, rax
0x180015f0c  mov     rcx, r13
0x180015f0f  call    ?Lookup@?$CAtlMap@VCProblemInstanceKey@@PEAVProblemInstance@@V?$CElementTraits@VCProblemInstanceKey@@@ATL@@V?$CElementTraits@PEAVProblemInstance@@@4@@ATL@@QEBA_NAEBVCProblemInstanceKey@@AEAPEAVProblemInstance@@@Z; ATL::CAtlMap<CProblemInstanceKey,ProblemInstance *,ATL::CElementTraits<CProblemInstanceKey>,ATL::CElementTraits<ProblemInstance *>>::Lookup(CProblemInstanceKey const &,ProblemInstance * &)
0x180015f14  mov     rdi, [rbp+var_20]
0x180015f18  test    al, al
0x180015f1a  jz      loc_180015FB1
0x180015f20  mov     edx, [rdi+44h]
0x180015f23  shl     rdx, 20h
0x180015f27  mov     eax, [rdi+40h]
0x180015f2a  or      rdx, rax
0x180015f2d  mov     ecx, dword ptr [rbp+var_18+4]
0x180015f30  shl     rcx, 20h
0x180015f34  mov     eax, dword ptr [rbp+var_18]
0x180015f37  or      rcx, rax
0x180015f3a  cmp     rcx, rdx
0x180015f3d  jbe     short loc_180015F70
0x180015f3f  mov     rax, [rdi+110h]
0x180015f46  sub     rax, [r14]
0x180015f49  jnz     short loc_180015F56
0x180015f4b  mov     rax, [rdi+118h]
0x180015f52  sub     rax, [r14+8]
0x180015f56  test    rax, rax
0x180015f59  jz      short loc_180015F70
0x180015f5b  mov     rdx, rsi
0x180015f5e  mov     rcx, r13
0x180015f61  call    ?RemoveKey@?$CAtlMap@VCProblemInstanceKey@@PEAVProblemInstance@@V?$CElementTraits@VCProblemInstanceKey@@@ATL@@V?$CElementTraits@PEAVProblemInstance@@@4@@ATL@@QEAA_NAEBVCProblemInstanceKey@@@Z; ATL::CAtlMap<CProblemInstanceKey,ProblemInstance *,ATL::CElementTraits<CProblemInstanceKey>,ATL::CElementTraits<ProblemInstance *>>::RemoveKey(CProblemInstanceKey const &)
0x180015f66  mov     rcx, rdi; this
0x180015f69  call    ?Dereference@ProblemInstance@@QEAAJXZ; ProblemInstance::Dereference(void)
0x180015f6e  jmp     short loc_180015FB1
0x180015f70  mov     r15b, 1
0x180015f73  cmp     dword ptr [rbx+4], 0
0x180015f77  jz      short loc_180015F91
0x180015f79  mov     rdx, rbx; lpFileTime2
0x180015f7c  lea     rcx, [rdi+30h]; lpFileTime1
0x180015f80  call    cs:__imp_CompareFileTime
0x180015f86  test    eax, eax
0x180015f88  jle     short loc_180015F91
0x180015f8a  mov     rax, [rbx]
0x180015f8d  mov     [rdi+30h], rax
0x180015f91  cmp     dword ptr [rbx+0Ch], 0
0x180015f95  jz      short loc_180015FB1
0x180015f97  lea     rdx, [rdi+38h]; lpFileTime2
0x180015f9b  lea     rcx, [rbx+8]; lpFileTime1
0x180015f9f  call    cs:__imp_CompareFileTime
0x180015fa5  test    eax, eax
0x180015fa7  jle     short loc_180015FB1
0x180015fa9  mov     rax, [rbx+8]
0x180015fad  mov     [rdi+38h], rax
0x180015fb1  mov     rcx, rsi; this
0x180015fb4  call    ??_GCProblemInstanceKey@@QEAAPEAXI@Z; CProblemInstanceKey::`scalar deleting destructor'(uint)
0x180015fb9  xor     esi, esi
0x180015fbb  call    ?Instance@NetworkDiagnosticsEngine@@SAPEAV1@XZ; NetworkDiagnosticsEngine::Instance(void)
0x180015fc0  test    rax, rax
0x180015fc3  jz      short loc_180015FCD
0x180015fc5  call    ?Instance@NetworkDiagnosticsEngine@@SAPEAV1@XZ; NetworkDiagnosticsEngine::Instance(void)
0x180015fca  mov     rsi, [rax]
0x180015fcd  test    r15b, r15b
0x180015fd0  jz      short loc_180016022
0x180015fd2  test    rsi, rsi
0x180015fd5  jz      loc_18001606E
0x180015fdb  lea     rcx, [rbp+var_20]
0x180015fdf  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180015fe4  mov     r8, [r12]
0x180015fe8  lea     rdx, aCacheHitForHel; "Cache Hit for HelperClass: %s"
0x180015fef  lea     rcx, [rbp+var_20]
0x180015ff3  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180015ff8  mov     rax, [rsi]
0x180015ffb  mov     r9, [rbp+var_10]
0x180015fff  mov     rbx, [rbp+var_20]
0x180016003  mov     r8, rbx
0x180016006  mov     edx, 4
0x18001600b  mov     rcx, rsi
0x18001600e  mov     rax, [rax+70h]
0x180016012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016017  lea     rcx, [rbx-18h]; this
0x18001601b  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180016020  jmp     short loc_18001606E
0x180016022  test    rsi, rsi
0x180016025  jz      short loc_18001606C
0x180016027  lea     rcx, [rbp+var_20]
0x18001602b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180016030  mov     r8, [r12]
0x180016034  lea     rdx, aCacheMissForHe; "Cache Miss for HelperClass: %s"
0x18001603b  lea     rcx, [rbp+var_20]
0x18001603f  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180016044  mov     rax, [rsi]
0x180016047  mov     r9, [rbp+var_10]
0x18001604b  mov     rbx, [rbp+var_20]
0x18001604f  mov     r8, rbx
0x180016052  mov     edx, 4
0x180016057  mov     rcx, rsi
0x18001605a  mov     rax, [rax+70h]
0x18001605e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016063  lea     rcx, [rbx-18h]; this
0x180016067  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001606c  xor     edi, edi
0x18001606e  mov     rcx, [r12]
0x180016072  sub     rcx, 18h; this
0x180016076  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001607b  mov     rax, rdi
0x18001607e  mov     rcx, [rbp+var_8]
0x180016082  xor     rcx, rsp; StackCookie
0x180016085  call    __security_check_cookie
0x18001608a  mov     rbx, [rsp+50h+arg_18]
0x180016092  add     rsp, 50h
0x180016096  pop     r15
0x180016098  pop     r14
0x18001609a  pop     r13
0x18001609c  pop     r12
0x18001609e  pop     rdi
0x18001609f  pop     rsi
0x1800160a0  pop     rbp
0x1800160a1  retn
```
