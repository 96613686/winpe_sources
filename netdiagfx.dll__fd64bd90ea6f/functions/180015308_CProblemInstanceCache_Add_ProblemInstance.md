# CProblemInstanceCache::Add(ProblemInstance *)

- ea: `0x180015308`
- end: `0x1800154bf`
- name: `?Add@CProblemInstanceCache@@QEAA_NPEAVProblemInstance@@@Z`
- size: `439`
- prototype: `char __fastcall(CProblemInstanceCache *this, const FILETIME *)`
- caller_count: `3`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800121d0`
- `0x180012b44`
- `0x180013c3c`

## callees

- `0x180001ff4`
- `0x180005c18`
- `0x180014e54`
- `0x1800152e0`
- `0x180015308`
- `0x180015c00`
- `0x180015d90`
- `0x180015e30`
- `0x1800160a8`
- `0x18002c840`

## import_xrefs

- `KERNEL32!CompareFileTime` at `0x18001542a`
- `KERNEL32!CompareFileTime` at `0x18001545c`
- `KERNEL32!CompareFileTime` at `0x18001547f`
- `KERNEL32!CompareFileTime` at `0x18001542a`
- `KERNEL32!CompareFileTime` at `0x18001545c`
- `KERNEL32!CompareFileTime` at `0x18001547f`

## pseudocode

```c
char __fastcall CProblemInstanceCache::Add(CProblemInstanceCache *this, const FILETIME *a2)
{
  void *v4; // rax
  CProblemInstanceKey *v5; // rdi
  unsigned int v7; // edx
  __int64 Node; // rax
  const FILETIME *v9; // rsi
  __int64 v10; // [rsp+0h] [rbp-78h] BYREF
  unsigned int v11; // [rsp+30h] [rbp-48h] BYREF
  const FILETIME *v12; // [rsp+38h] [rbp-40h] BYREF
  CProblemInstanceKey *v13; // [rsp+40h] [rbp-38h]
  FILETIME FileTime2[2]; // [rsp+48h] [rbp-30h] BYREF

  v12 = 0;
  v4 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  FileTime2[0] = (FILETIME)v4;
  if ( v4 )
    v5 = (CProblemInstanceKey *)CProblemInstanceKey::CProblemInstanceKey(v4, a2, *(_QWORD *)&a2[5]);
  else
    v5 = 0;
  v13 = v5;
  if ( !v5 )
    return 0;
  if ( (unsigned __int8)ATL::CAtlMap<CProblemInstanceKey,ProblemInstance *,ATL::CElementTraits<CProblemInstanceKey>,ATL::CElementTraits<ProblemInstance *>>::Lookup(
                          this,
                          v5,
                          &v12) )
  {
    v9 = v12;
    if ( v12 != a2 && CompareFileTime(a2 + 8, v12 + 8) > 0 )
      v9[8] = a2[8];
    *(_OWORD *)&FileTime2[0].dwLowDateTime = *(_OWORD *)&a2[6].dwLowDateTime;
    if ( FileTime2[0].dwHighDateTime && CompareFileTime(v9 + 6, FileTime2) > 0 )
      v9[6] = FileTime2[0];
    if ( FileTime2[1].dwHighDateTime && CompareFileTime(&FileTime2[1], v9 + 7) > 0 )
      v9[7] = FileTime2[1];
  }
  else
  {
    LODWORD(v12) = 0;
    v11 = 0;
    FileTime2[0] = 0;
    Node = ATL::CAtlMap<CProblemInstanceKey,ProblemInstance *,ATL::CElementTraits<CProblemInstanceKey>,ATL::CElementTraits<ProblemInstance *>>::GetNode(
             this,
             v5,
             &v12,
             &v11,
             FileTime2);
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      if ( !Node )
      {
        if ( !*(_QWORD *)this
          && !(unsigned __int8)ATL::CAtlMap<_GUID,NetTrace::TraceProviderInfo,ATL::CElementTraits<_GUID>,ATL::CElementTraits<NetTrace::TraceProviderInfo>>::InitHashTable(
                                 this,
                                 *((unsigned int *)this + 4)) )
        {
          ATL::AtlThrowImpl(-2147024882);
        }
        Node = ATL::CAtlMap<CProblemInstanceKey,ProblemInstance *,ATL::CElementTraits<CProblemInstanceKey>,ATL::CElementTraits<ProblemInstance *>>::NewNode(
                 this,
                 v5,
                 (unsigned int)v12,
                 v11);
      }
      *(_QWORD *)(Node + 24) = a2;
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
      {
        CProblemInstanceKey::`scalar deleting destructor'(v13, (unsigned int)&v10);
        __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_180015413);
        return 0;
      }
    }
    _InterlockedIncrement((volatile signed __int32 *)&a2[37]);
  }
  CProblemInstanceKey::`scalar deleting destructor'(v5, v7);
  return 1;
}

```

## disassembly

```asm
0x180015308  mov     [rsp+arg_10], rbx
0x18001530d  mov     [rsp+arg_18], rsi
0x180015312  push    rdi
0x180015313  push    r14
0x180015315  push    r15
0x180015317  sub     rsp, 60h
0x18001531b  mov     rax, cs:__security_cookie
0x180015322  xor     rax, rsp
0x180015325  mov     [rsp+78h+var_20], rax
0x18001532a  mov     rbx, rdx
0x18001532d  mov     rsi, rcx
0x180015330  mov     [rsp+78h+var_40], 0
0x180015339  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180015340  mov     ecx, 18h; unsigned __int64
0x180015345  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001534a  mov     qword ptr [rsp+78h+FileTime2.dwLowDateTime], rax
0x18001534f  test    rax, rax
0x180015352  jz      short loc_180015368
0x180015354  mov     r8, [rbx+28h]
0x180015358  mov     rdx, rbx
0x18001535b  mov     rcx, rax
0x18001535e  call    ??0CProblemInstanceKey@@QEAA@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBV?$list@UtagHELPER_ATTRIBUTE@@V?$allocator@UtagHELPER_ATTRIBUTE@@@std@@@std@@@Z; CProblemInstanceKey::CProblemInstanceKey(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,std::list<tagHELPER_ATTRIBUTE> const *)
0x180015363  mov     rdi, rax
0x180015366  jmp     short loc_18001536A
0x180015368  xor     edi, edi
0x18001536a  mov     [rsp+78h+var_38], rdi
0x18001536f  test    rdi, rdi
0x180015372  jnz     short loc_18001537B
0x180015374  xor     al, al
0x180015376  jmp     loc_18001549C
0x18001537b  lea     r8, [rsp+78h+var_40]
0x180015380  mov     rdx, rdi
0x180015383  mov     rcx, rsi
0x180015386  call    ?Lookup@?$CAtlMap@VCProblemInstanceKey@@PEAVProblemInstance@@V?$CElementTraits@VCProblemInstanceKey@@@ATL@@V?$CElementTraits@PEAVProblemInstance@@@4@@ATL@@QEBA_NAEBVCProblemInstanceKey@@AEAPEAVProblemInstance@@@Z; ATL::CAtlMap<CProblemInstanceKey,ProblemInstance *,ATL::CElementTraits<CProblemInstanceKey>,ATL::CElementTraits<ProblemInstance *>>::Lookup(CProblemInstanceKey const &,ProblemInstance * &)
0x18001538b  test    al, al
0x18001538d  jnz     loc_180015418
0x180015393  mov     dword ptr [rsp+78h+var_40], 0
0x18001539b  mov     [rsp+78h+var_48], 0
0x1800153a3  mov     qword ptr [rsp+78h+FileTime2.dwLowDateTime], 0
0x1800153ac  lea     rax, [rsp+78h+FileTime2]
0x1800153b1  mov     [rsp+78h+var_58], rax
0x1800153b6  lea     r9, [rsp+78h+var_48]
0x1800153bb  lea     r8, [rsp+78h+var_40]
0x1800153c0  mov     rdx, rdi
0x1800153c3  mov     rcx, rsi
0x1800153c6  call    ?GetNode@?$CAtlMap@VCProblemInstanceKey@@PEAVProblemInstance@@V?$CElementTraits@VCProblemInstanceKey@@@ATL@@V?$CElementTraits@PEAVProblemInstance@@@4@@ATL@@AEBAPEAVCNode@12@AEBVCProblemInstanceKey@@AEAI1AEAPEAV312@@Z; ATL::CAtlMap<CProblemInstanceKey,ProblemInstance *,ATL::CElementTraits<CProblemInstanceKey>,ATL::CElementTraits<ProblemInstance *>>::GetNode(CProblemInstanceKey const &,uint &,uint &,ATL::CAtlMap<CProblemInstanceKey,ProblemInstance *,ATL::CElementTraits<CProblemInstanceKey>,ATL::CElementTraits<ProblemInstance *>>::CNode * &)
0x1800153cb  test    rax, rax
0x1800153ce  jnz     short loc_180015406
0x1800153d0  cmp     [rsi], rax
0x1800153d3  jnz     short loc_1800153F1
0x1800153d5  mov     r8b, 1
0x1800153d8  mov     edx, [rsi+10h]
0x1800153db  mov     rcx, rsi
0x1800153de  call    ?InitHashTable@?$CAtlMap@U_GUID@@UTraceProviderInfo@NetTrace@@V?$CElementTraits@U_GUID@@@ATL@@V?$CElementTraits@UTraceProviderInfo@NetTrace@@@5@@ATL@@QEAA_NI_N@Z; ATL::CAtlMap<_GUID,NetTrace::TraceProviderInfo,ATL::CElementTraits<_GUID>,ATL::CElementTraits<NetTrace::TraceProviderInfo>>::InitHashTable(uint,bool)
0x1800153e3  test    al, al
0x1800153e5  jnz     short loc_1800153F1
0x1800153e7  mov     ecx, 8007000Eh; int
0x1800153ec  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800153f1  mov     r9d, [rsp+78h+var_48]
0x1800153f6  mov     r8d, dword ptr [rsp+78h+var_40]
0x1800153fb  mov     rdx, rdi
0x1800153fe  mov     rcx, rsi
0x180015401  call    ?NewNode@?$CAtlMap@VCProblemInstanceKey@@PEAVProblemInstance@@V?$CElementTraits@VCProblemInstanceKey@@@ATL@@V?$CElementTraits@PEAVProblemInstance@@@4@@ATL@@AEAAPEAVCNode@12@AEBVCProblemInstanceKey@@II@Z; ATL::CAtlMap<CProblemInstanceKey,ProblemInstance *,ATL::CElementTraits<CProblemInstanceKey>,ATL::CElementTraits<ProblemInstance *>>::NewNode(CProblemInstanceKey const &,uint,uint)
0x180015406  mov     [rax+18h], rbx
0x18001540a  lock inc dword ptr [rbx+128h]
0x180015411  jmp     short loc_180015492
0x180015413  jmp     loc_180015374
0x180015418  mov     rsi, [rsp+78h+var_40]
0x18001541d  cmp     rsi, rbx
0x180015420  jz      short loc_18001543C
0x180015422  lea     rdx, [rsi+40h]; lpFileTime2
0x180015426  lea     rcx, [rbx+40h]; lpFileTime1
0x18001542a  call    cs:__imp_CompareFileTime
0x180015430  test    eax, eax
0x180015432  jle     short loc_18001543C
0x180015434  mov     rax, [rbx+40h]
0x180015438  mov     [rsi+40h], rax
0x18001543c  movups  xmm0, xmmword ptr [rbx+30h]
0x180015440  movdqu  xmmword ptr [rsp+78h+FileTime2.dwLowDateTime], xmm0
0x180015446  mov     rax, qword ptr [rsp+78h+FileTime2.dwLowDateTime]
0x18001544b  shr     rax, 20h
0x18001544f  test    eax, eax
0x180015451  jz      short loc_18001546F
0x180015453  lea     rdx, [rsp+78h+FileTime2]; lpFileTime2
0x180015458  lea     rcx, [rsi+30h]; lpFileTime1
0x18001545c  call    cs:__imp_CompareFileTime
0x180015462  test    eax, eax
0x180015464  jle     short loc_18001546F
0x180015466  mov     rax, qword ptr [rsp+78h+FileTime2.dwLowDateTime]
0x18001546b  mov     [rsi+30h], rax
0x18001546f  cmp     [rsp+78h+FileTime2.dwHighDateTime+8], 0
0x180015474  jz      short loc_180015492
0x180015476  lea     rdx, [rsi+38h]; lpFileTime2
0x18001547a  lea     rcx, [rsp+78h+FileTime2.dwLowDateTime+8]; lpFileTime1
0x18001547f  call    cs:__imp_CompareFileTime
0x180015485  test    eax, eax
0x180015487  jle     short loc_180015492
0x180015489  mov     rax, qword ptr [rsp+78h+FileTime2.dwLowDateTime+8]
0x18001548e  mov     [rsi+38h], rax
0x180015492  mov     rcx, rdi; this
0x180015495  call    ??_GCProblemInstanceKey@@QEAAPEAXI@Z; CProblemInstanceKey::`scalar deleting destructor'(uint)
0x18001549a  mov     al, 1
0x18001549c  mov     rcx, [rsp+78h+var_20]
0x1800154a1  xor     rcx, rsp; StackCookie
0x1800154a4  call    __security_check_cookie
0x1800154a9  lea     r11, [rsp+78h+var_18]
0x1800154ae  mov     rbx, [r11+30h]
0x1800154b2  mov     rsi, [r11+38h]
0x1800154b6  mov     rsp, r11
0x1800154b9  pop     r15
0x1800154bb  pop     r14
0x1800154bd  pop     rdi
0x1800154be  retn
```
