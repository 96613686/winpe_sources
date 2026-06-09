# CRepository::Logon(__MIDL___MIDL_itf_reposit_0001_0003_0002 *,ulong,ulong,IWmiDbSession * *,IWmiDbHandle * *)

- ea: `0x18003b630`
- end: `0x18003b9b1`
- name: `?Logon@CRepository@@UEAAJPEAU__MIDL___MIDL_itf_reposit_0001_0003_0002@@KKPEAPEAUIWmiDbSession@@PEAPEAUIWmiDbHandle@@@Z`
- size: `897`
- prototype: `__int64 __usercall@<rax>(CRepository *__hidden this@<rcx>, struct __MIDL___MIDL_itf_reposit_0001_0003_0002 *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, struct IWmiDbSession **, struct IWmiDbHandle **)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x1800161e0`
- `0x180023170`
- `0x180027580`
- `0x1800296d0`
- `0x18003b064`
- `0x18003b630`
- `0x180048010`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003b754`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003b824`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003b754`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003b824`
- `wbemcomn!GetMemLogObject` at `0x18003b685`
- `wbemcomn!GetMemLogObject` at `0x18003b6fe`
- `wbemcomn!GetMemLogObject` at `0x18003b7b7`
- `wbemcomn!GetMemLogObject` at `0x18003b84f`
- `wbemcomn!GetMemLogObject` at `0x18003b8d4`
- `wbemcomn!GetMemLogObject` at `0x18003b685`
- `wbemcomn!GetMemLogObject` at `0x18003b6fe`
- `wbemcomn!GetMemLogObject` at `0x18003b7b7`
- `wbemcomn!GetMemLogObject` at `0x18003b84f`
- `wbemcomn!GetMemLogObject` at `0x18003b8d4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003b695`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003b709`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003b7c7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003b85f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003b8df`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003b695`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003b709`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003b7c7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003b85f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003b8df`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CRepository::Logon(
        struct CLifeControl **this,
        struct __MIDL___MIDL_itf_reposit_0001_0003_0002 *a2,
        __int64 a3,
        __int64 a4,
        struct IWmiDbSession **a5,
        struct IWmiDbHandle **a6)
{
  CMemoryLog *MemLogObject; // rax
  unsigned int v9; // ebx
  CVarObjHeap *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  CMemoryLog *v14; // rax
  struct IWmiDbSession *v15; // rbx
  struct CLifeControl *v16; // rcx
  CMemoryLog *v17; // rax
  int v18; // edi
  CNamespaceHandle *v19; // rax
  CNamespaceHandle *v20; // rsi
  CMemoryLog *v21; // rax
  CMemoryLog *v22; // rax
  char v23[8]; // [rsp+28h] [rbp-40h] BYREF
  struct CLifeControl **v24; // [rsp+30h] [rbp-38h]
  __int64 (__fastcall *v25)(); // [rsp+38h] [rbp-30h]
  int v26; // [rsp+40h] [rbp-28h]

  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, WPP_53e1474670223052d7bc731b72ed24d6_Traceguids);
  }
  if ( !a2 )
  {
    MemLogObject = GetMemLogObject();
    v9 = -2147217407;
    CMemoryLog::Write(MemLogObject, -2147217407);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v9;
    }
    v11 = 62;
    v12 = 2147749889LL;
LABEL_10:
    WPP_SF_d(*((_QWORD *)v10 + 2), v11, WPP_53e1474670223052d7bc731b72ed24d6_Traceguids, v12);
    return v9;
  }
  if ( g_dwSecTlsIndex == -1 )
    g_dwSecTlsIndex = *(_DWORD *)(*((_QWORD *)a2 + 1) + 24LL);
  if ( !g_Glob )
  {
    v9 = CRepository::Initialize(this);
    if ( (v9 & 0x80000000) != 0 )
    {
      v14 = GetMemLogObject();
      CMemoryLog::Write(v14, v9);
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return v9;
      }
      v11 = 63;
      v12 = v9;
      goto LABEL_10;
    }
  }
  v23[0] = 0;
  v24 = this;
  v25 =  CRepository::`vcall'{48,{flat}};
  v26 = 0;
  v15 = (struct IWmiDbSession *)CWin32DefaultArena::WbemMemAlloc(0xB0u);
  if ( v15 )
  {
    v16 = this[2];
    *(_QWORD *)v15 = &CUnkBase<IWmiDbSessionEx,&_GUID const IID_IWmiDbSessionEx>::`vftable';
    *((_DWORD *)v15 + 2) = 0;
    *((_QWORD *)v15 + 2) = v16;
    if ( v16 )
      (**(void (__fastcall ***)(struct CLifeControl *, struct IWmiDbSession *))v16)(v16, v15);
    *(_QWORD *)v15 = &CSession::`vftable';
    CEventCollector::CEventCollector((struct IWmiDbSession *)((char *)v15 + 24));
    *((_BYTE *)v15 + 168) = 0;
  }
  else
  {
    v15 = 0;
  }
  if ( v15 )
  {
    (*(void (__fastcall **)(struct IWmiDbSession *))(*(_QWORD *)v15 + 8LL))(v15);
    v19 = (CNamespaceHandle *)CWin32DefaultArena::WbemMemAlloc(0x70u);
    if ( v19 )
      v20 = CNamespaceHandle::CNamespaceHandle(v19, this[2], (struct CRepository *)this);
    else
      v20 = 0;
    if ( v20 )
    {
      (*(void (__fastcall **)(CNamespaceHandle *))(*(_QWORD *)v20 + 8LL))(v20);
      v18 = CNamespaceHandle::Initialize(v20, &qword_18004AEE0, 0);
      if ( v18 >= 0 )
      {
        *a6 = v20;
        (*(void (__fastcall **)(CNamespaceHandle *))(*(_QWORD *)v20 + 8LL))(v20);
        *a5 = v15;
        (*(void (__fastcall **)(struct IWmiDbSession *))(*(_QWORD *)v15 + 8LL))(v15);
        v23[0] = 1;
        (*(void (__fastcall **)(CNamespaceHandle *))(*(_QWORD *)v20 + 16LL))(v20);
        (*(void (__fastcall **)(struct IWmiDbSession *))(*(_QWORD *)v15 + 16LL))(v15);
        v18 = 0;
      }
      else
      {
        v22 = GetMemLogObject();
        CMemoryLog::Write(v22, v18);
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            66,
            WPP_53e1474670223052d7bc731b72ed24d6_Traceguids,
            (unsigned int)v18);
        }
        (*(void (__fastcall **)(CNamespaceHandle *))(*(_QWORD *)v20 + 16LL))(v20);
        (*(void (__fastcall **)(struct IWmiDbSession *))(*(_QWORD *)v15 + 16LL))(v15);
      }
    }
    else
    {
      v21 = GetMemLogObject();
      v18 = -2147217402;
      CMemoryLog::Write(v21, -2147217402);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, WPP_53e1474670223052d7bc731b72ed24d6_Traceguids, 2147749894LL);
      }
      (*(void (__fastcall **)(struct IWmiDbSession *))(*(_QWORD *)v15 + 16LL))(v15);
    }
  }
  else
  {
    v17 = GetMemLogObject();
    v18 = -2147217402;
    CMemoryLog::Write(v17, -2147217402);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, WPP_53e1474670223052d7bc731b72ed24d6_Traceguids, 2147749894LL);
    }
  }
  ObjScopeGuardImpl1<CBTreeFile,unsigned long (CBTreeFile::*)(unsigned long),int>::~ObjScopeGuardImpl1<CBTreeFile,unsigned long (CBTreeFile::*)(unsigned long),int>((__int64)v23);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x18003b630  mov     [rsp+arg_0], rbx
0x18003b635  mov     [rsp+arg_10], rsi
0x18003b63a  push    rdi
0x18003b63b  push    r12
0x18003b63d  push    r15
0x18003b63f  sub     rsp, 50h
0x18003b643  mov     rbx, rdx
0x18003b646  mov     rdi, rcx
0x18003b649  lea     r12, WPP_GLOBAL_Control
0x18003b650  lea     r15, WPP_53e1474670223052d7bc731b72ed24d6_Traceguids
0x18003b657  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b65e  cmp     rcx, r12
0x18003b661  jz      short loc_18003B680
0x18003b663  test    byte ptr [rcx+1Ch], 1
0x18003b667  jz      short loc_18003B680
0x18003b669  cmp     byte ptr [rcx+19h], 5
0x18003b66d  jb      short loc_18003B680
0x18003b66f  mov     edx, 3Dh ; '='
0x18003b674  mov     r8, r15
0x18003b677  mov     rcx, [rcx+10h]
0x18003b67b  call    WPP_SF_
0x18003b680  test    rbx, rbx
0x18003b683  jnz     short loc_18003B6D1
0x18003b685  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003b68b  mov     ebx, 80041001h
0x18003b690  mov     edx, ebx
0x18003b692  mov     rcx, rax
0x18003b695  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003b69b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b6a2  cmp     rcx, r12
0x18003b6a5  jz      short loc_18003B6CA
0x18003b6a7  test    byte ptr [rcx+1Ch], 1
0x18003b6ab  jz      short loc_18003B6CA
0x18003b6ad  cmp     byte ptr [rcx+19h], 2
0x18003b6b1  jb      short loc_18003B6CA
0x18003b6b3  mov     edx, 3Eh ; '>'
0x18003b6b8  mov     r9d, 80041001h
0x18003b6be  mov     r8, r15
0x18003b6c1  mov     rcx, [rcx+10h]
0x18003b6c5  call    WPP_SF_d
0x18003b6ca  mov     eax, ebx
0x18003b6cc  jmp     loc_18003B99B
0x18003b6d1  cmp     cs:?g_dwSecTlsIndex@@3KA, 0FFFFFFFFh; ulong g_dwSecTlsIndex
0x18003b6d8  jnz     short loc_18003B6E7
0x18003b6da  mov     rax, [rbx+8]
0x18003b6de  mov     ecx, [rax+18h]
0x18003b6e1  mov     cs:?g_dwSecTlsIndex@@3KA, ecx; ulong g_dwSecTlsIndex
0x18003b6e7  cmp     cs:?g_Glob@@3VCGlobals@@A, 0; CGlobals g_Glob
0x18003b6ee  jnz     short loc_18003B731
0x18003b6f0  mov     rcx, rdi; this
0x18003b6f3  call    ?Initialize@CRepository@@IEAAJXZ; CRepository::Initialize(void)
0x18003b6f8  mov     ebx, eax
0x18003b6fa  test    eax, eax
0x18003b6fc  jns     short loc_18003B731
0x18003b6fe  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003b704  mov     edx, ebx
0x18003b706  mov     rcx, rax
0x18003b709  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003b70f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b716  cmp     rcx, r12
0x18003b719  jz      short loc_18003B6CA
0x18003b71b  test    byte ptr [rcx+1Ch], 1
0x18003b71f  jz      short loc_18003B6CA
0x18003b721  cmp     byte ptr [rcx+19h], 2
0x18003b725  jb      short loc_18003B6CA
0x18003b727  mov     edx, 3Fh ; '?'
0x18003b72c  mov     r9d, ebx
0x18003b72f  jmp     short loc_18003B6BE
0x18003b731  mov     [rsp+68h+var_40], 0
0x18003b736  mov     [rsp+68h+var_38], rdi
0x18003b73b  lea     rax, ??_9CRepository@@$BDA@AA; [thunk]: CRepository::`vcall'{48,{flat}}
0x18003b742  mov     [rsp+68h+var_30], rax
0x18003b747  mov     [rsp+68h+var_28], 0
0x18003b74f  mov     ecx, 0B0h
0x18003b754  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18003b75a  mov     rbx, rax
0x18003b75d  mov     [rsp+68h+arg_8], rax
0x18003b762  test    rax, rax
0x18003b765  jz      short loc_18003B7B0
0x18003b767  mov     rcx, [rdi+10h]
0x18003b76b  lea     rax, ??_7?$CUnkBase@UIWmiDbSessionEx@@$1?IID_IWmiDbSessionEx@@3U_GUID@@B@@6B@; const CUnkBase<IWmiDbSessionEx,&_GUID const IID_IWmiDbSessionEx>::`vftable'
0x18003b772  mov     [rbx], rax
0x18003b775  mov     dword ptr [rbx+8], 0
0x18003b77c  mov     [rbx+10h], rcx
0x18003b780  test    rcx, rcx
0x18003b783  jz      short loc_18003B794
0x18003b785  mov     rax, [rcx]
0x18003b788  mov     rdx, rbx
0x18003b78b  mov     rax, [rax]
0x18003b78e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b793  nop
0x18003b794  lea     rax, ??_7CSession@@6B@; const CSession::`vftable'
0x18003b79b  mov     [rbx], rax
0x18003b79e  lea     rcx, [rbx+18h]; this
0x18003b7a2  call    ??0CEventCollector@@QEAA@XZ; CEventCollector::CEventCollector(void)
0x18003b7a7  mov     byte ptr [rbx+0A8h], 0
0x18003b7ae  jmp     short loc_18003B7B2
0x18003b7b0  xor     ebx, ebx
0x18003b7b2  test    rbx, rbx
0x18003b7b5  jnz     short loc_18003B80B
0x18003b7b7  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003b7bd  mov     edi, 80041006h
0x18003b7c2  mov     edx, edi
0x18003b7c4  mov     rcx, rax
0x18003b7c7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003b7cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b7d4  cmp     rcx, r12
0x18003b7d7  jz      loc_18003B98F
0x18003b7dd  test    byte ptr [rcx+1Ch], 1
0x18003b7e1  jz      loc_18003B98F
0x18003b7e7  cmp     byte ptr [rcx+19h], 2
0x18003b7eb  jb      loc_18003B98F
0x18003b7f1  lea     edx, [rbx+40h]
0x18003b7f4  mov     r9d, 80041006h
0x18003b7fa  mov     r8, r15
0x18003b7fd  mov     rcx, [rcx+10h]
0x18003b801  call    WPP_SF_d
0x18003b806  jmp     loc_18003B98F
0x18003b80b  mov     rax, [rbx]
0x18003b80e  mov     rcx, rbx
0x18003b811  mov     rax, [rax+8]
0x18003b815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b81a  mov     [rsp+68h+arg_8], rbx
0x18003b81f  mov     ecx, 70h ; 'p'
0x18003b824  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18003b82a  mov     [rsp+68h+var_48], rax
0x18003b82f  test    rax, rax
0x18003b832  jz      short loc_18003B848
0x18003b834  mov     r8, rdi; struct CRepository *
0x18003b837  mov     rdx, [rdi+10h]; struct CLifeControl *
0x18003b83b  mov     rcx, rax; this
0x18003b83e  call    ??0CNamespaceHandle@@QEAA@PEAVCLifeControl@@PEAVCRepository@@@Z; CNamespaceHandle::CNamespaceHandle(CLifeControl *,CRepository *)
0x18003b843  mov     rsi, rax
0x18003b846  jmp     short loc_18003B84A
0x18003b848  xor     esi, esi
0x18003b84a  test    rsi, rsi
0x18003b84d  jnz     short loc_18003B8A8
0x18003b84f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003b855  mov     edi, 80041006h
0x18003b85a  mov     edx, edi
0x18003b85c  mov     rcx, rax
0x18003b85f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003b865  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b86c  cmp     rcx, r12
0x18003b86f  jz      short loc_18003B893
0x18003b871  test    byte ptr [rcx+1Ch], 1
0x18003b875  jz      short loc_18003B893
0x18003b877  cmp     byte ptr [rcx+19h], 2
0x18003b87b  jb      short loc_18003B893
0x18003b87d  lea     edx, [rsi+41h]
0x18003b880  mov     r9d, 80041006h
0x18003b886  mov     r8, r15
0x18003b889  mov     rcx, [rcx+10h]
0x18003b88d  call    WPP_SF_d
0x18003b892  nop
0x18003b893  mov     rax, [rbx]
0x18003b896  mov     rcx, rbx
0x18003b899  mov     rax, [rax+10h]
0x18003b89d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b8a2  nop
0x18003b8a3  jmp     loc_18003B98F
0x18003b8a8  mov     rax, [rsi]
0x18003b8ab  mov     rcx, rsi
0x18003b8ae  mov     rax, [rax+8]
0x18003b8b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b8b7  mov     [rsp+68h+var_48], rsi
0x18003b8bc  xor     r8d, r8d; unsigned __int16 *
0x18003b8bf  lea     rdx, qword_18004AEE0; unsigned __int16 *
0x18003b8c6  mov     rcx, rsi; this
0x18003b8c9  call    ?Initialize@CNamespaceHandle@@QEAAJPEBG0@Z; CNamespaceHandle::Initialize(ushort const *,ushort const *)
0x18003b8ce  mov     edi, eax
0x18003b8d0  test    eax, eax
0x18003b8d2  jns     short loc_18003B934
0x18003b8d4  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003b8da  mov     edx, edi
0x18003b8dc  mov     rcx, rax
0x18003b8df  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003b8e5  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b8ec  cmp     rcx, r12
0x18003b8ef  jz      short loc_18003B912
0x18003b8f1  test    byte ptr [rcx+1Ch], 1
0x18003b8f5  jz      short loc_18003B912
0x18003b8f7  cmp     byte ptr [rcx+19h], 2
0x18003b8fb  jb      short loc_18003B912
0x18003b8fd  mov     edx, 42h ; 'B'
0x18003b902  mov     r9d, edi
0x18003b905  mov     r8, r15
0x18003b908  mov     rcx, [rcx+10h]
0x18003b90c  call    WPP_SF_d
0x18003b911  nop
0x18003b912  mov     rax, [rsi]
0x18003b915  mov     rcx, rsi
0x18003b918  mov     rax, [rax+10h]
0x18003b91c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b921  nop
0x18003b922  mov     rax, [rbx]
0x18003b925  mov     rcx, rbx
0x18003b928  mov     rax, [rax+10h]
0x18003b92c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b931  nop
0x18003b932  jmp     short loc_18003B98F
0x18003b934  mov     rax, [rsp+68h+arg_28]
0x18003b93c  mov     [rax], rsi
0x18003b93f  mov     rax, [rsi]
0x18003b942  mov     rcx, rsi
0x18003b945  mov     rax, [rax+8]
0x18003b949  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b94e  mov     rax, [rsp+68h+arg_20]
0x18003b956  mov     [rax], rbx
0x18003b959  mov     rax, [rbx]
0x18003b95c  mov     rcx, rbx
0x18003b95f  mov     rax, [rax+8]
0x18003b963  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b968  mov     [rsp+68h+var_40], 1
0x18003b96d  mov     rax, [rsi]
0x18003b970  mov     rcx, rsi
0x18003b973  mov     rax, [rax+10h]
0x18003b977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b97c  nop
0x18003b97d  mov     rax, [rbx]
0x18003b980  mov     rcx, rbx
0x18003b983  mov     rax, [rax+10h]
0x18003b987  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b98c  nop
0x18003b98d  xor     edi, edi
0x18003b98f  lea     rcx, [rsp+68h+var_40]
0x18003b994  call    ??1?$ObjScopeGuardImpl1@VCBTreeFile@@P81@EAAKK@ZH@@QEAA@XZ; ObjScopeGuardImpl1<CBTreeFile,ulong (CBTreeFile::*)(ulong),int>::~ObjScopeGuardImpl1<CBTreeFile,ulong (CBTreeFile::*)(ulong),int>(void)
0x18003b999  mov     eax, edi
0x18003b99b  lea     r11, [rsp+68h+var_18]
0x18003b9a0  mov     rbx, [r11+20h]
0x18003b9a4  mov     rsi, [r11+30h]
0x18003b9a8  mov     rsp, r11
0x18003b9ab  pop     r15
0x18003b9ad  pop     r12
0x18003b9af  pop     rdi
0x18003b9b0  retn
```
