# NDXGI::CDevice::CreateContextVirtual2(D3DWDDM2_0DDICB_CREATECONTEXTVIRTUAL *)

- ea: `0x18005a904`
- end: `0x18005acb7`
- name: `?CreateContextVirtual2@CDevice@NDXGI@@QEAAJPEAUD3DWDDM2_0DDICB_CREATECONTEXTVIRTUAL@@@Z`
- size: `947`
- prototype: `__int64 __fastcall(NDXGI::CDevice *__hidden this, struct D3DWDDM2_0DDICB_CREATECONTEXTVIRTUAL *)`
- caller_count: `2`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180059b70`
- `0x1801ac650`

## callees

- `0x180022400`
- `0x180022630`
- `0x1800229a0`
- `0x18005a904`
- `0x18005acc0`
- `0x18005acf8`
- `0x18005ad48`
- `0x18005ae00`
- `0x18005aeb8`
- `0x18005aee8`
- `0x18005b100`
- `0x18005b17c`
- `0x18005b214`
- `0x18009d94c`
- `0x1801cb010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18005ac93`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18005ac93`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005aa74`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005aa74`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005aa56`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005aa56`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005a9e3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005a9e3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005ab4f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005ac36`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005ac57`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005ab4f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005ac36`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005ac57`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005a9cd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005a9cd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005ab40`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005ac25`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005ac46`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005ab40`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005ac25`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005ac46`

## string_xrefs

- `0x18005abfe`: `Invalid context type passed to CreateContextVirtual2CB`
- `0x18005ac80`: `Reserved flags given to CreateContextVirtual2CB`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall NDXGI::CDevice::CreateContextVirtual2(
        NDXGI::CDevice *this,
        struct D3DWDDM2_0DDICB_CREATECONTEXTVIRTUAL *a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v6; // rcx
  int v7; // r8d
  __int64 v8; // r12
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rdx
  int v12; // eax
  __int64 v13; // rax
  NDXGI::CContext *v14; // r13
  __int64 v15; // rcx
  __int64 v16; // r12
  _QWORD **v17; // r12
  _QWORD **i; // r15
  __int64 v20; // r9
  __int64 v21; // r15
  char *v22; // r8
  RTL_SRWLOCK *SRWLock; // [rsp+40h] [rbp-F8h]
  RTL_SRWLOCK *v24; // [rsp+48h] [rbp-F0h]
  _DWORD v25[4]; // [rsp+50h] [rbp-E8h] BYREF
  __int64 v26; // [rsp+60h] [rbp-D8h]
  int v27; // [rsp+68h] [rbp-D0h]
  __int64 v28; // [rsp+6Ch] [rbp-CCh]
  int v29; // [rsp+74h] [rbp-C4h]
  _com_error *v30; // [rsp+78h] [rbp-C0h] BYREF
  _BYTE v31[88]; // [rsp+80h] [rbp-B8h] BYREF
  __int64 v32; // [rsp+D8h] [rbp-60h]
  __int64 v34; // [rsp+148h] [rbp+10h] BYREF
  __int64 v35; // [rsp+150h] [rbp+18h]
  NDXGI::CContext *v36; // [rsp+158h] [rbp+20h] BYREF

  *((_QWORD *)a2 + 4) = 0;
  if ( (*((_DWORD *)a2 + 3) & 0xFFFFFFE0) != 0 )
  {
    v22 = "Invalid context type passed to CreateContextVirtual2CB";
LABEL_16:
    CModule::RecordJournal((CModule *)&g_Module, -2147024809, v22, a4, 1);
    return 2147942487LL;
  }
  if ( *((_DWORD *)a2 + 2) >= 0x80u && *((_QWORD *)this + 113) > 0x1000300000000uLL )
  {
    v22 = "Reserved flags given to CreateContextVirtual2CB";
    goto LABEL_16;
  }
  if ( !(unsigned __int8)NDXGI::CDevice::CheckContextType() )
  {
    OutputDebugStringA(
      "If caps indicate that D3DWDDM2_0DDI_IMAGE_FUNCTIONS are supported, D3DWDDM2_0DDI_CONTEXTTYPE_IMAGE is a mutually e"
      "xclusive context type.\n");
    return 2147942487LL;
  }
  v28 = 0;
  v29 = 0;
  v25[0] = *(_DWORD *)(v6 + 104);
  v25[1] = *(_DWORD *)a2;
  v25[2] = *((_DWORD *)a2 + 1);
  v25[3] = v7;
  v26 = *((_QWORD *)a2 + 2);
  v27 = *((_DWORD *)a2 + 6);
  v28 = 11
      - (unsigned int)(((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(v6 + 72) + 16LL) + 304LL))(*(_QWORD *)(v6 + 72) + 16LL)
                      & 0xC0000000) != 0);
  v8 = *((_QWORD *)this + 12);
  v24 = (RTL_SRWLOCK *)((char *)this + 1032);
  AcquireSRWLockExclusive((PSRWLOCK)this + 129);
  SRWLock = (RTL_SRWLOCK *)((char *)this + 1184);
  AcquireSRWLockShared((PSRWLOCK)this + 148);
  v9 = NDXGI::CContext::CContext((NDXGI::CContext *)v31);
  try
  {
    std::list<NDXGI::CContext>::push_back((char *)this + 1040, v9);
    std::_List_node<NDXGI::CHwQueue,void *>::_Free_non_head<std::allocator<std::_List_node<NDXGI::CHwQueue,void *>>>(
      v10,
      v32);
    std::_Deallocate<16>(v32, 64);
    v35 = *(_QWORD *)(*((_QWORD *)this + 130) + 8LL);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1056));
    std::vector<unsigned int>::reserve((char *)this + 1096, *((_QWORD *)this + 131));
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1056));
    v12 = CallAndLogImpl<long (*)(_D3DKMT_CREATECONTEXTVIRTUAL *),_D3DKMT_CREATECONTEXTVIRTUAL *>(
            *(_QWORD *)(v8 + 688),
            v11,
            v25);
    LODWORD(v34) = NDXGI::CDevice::NTStatusToHResult(this, v12);
    ThrowFailure(v34);
    v13 = NDXGI::CContext::CContext(v31, this, v25, *((unsigned int *)a2 + 3));
    v14 = (NDXGI::CContext *)(v35 + 16);
    NDXGI::CContext::operator=(v35 + 16, v13);
    std::_List_node<NDXGI::CHwQueue,void *>::_Free_non_head<std::allocator<std::_List_node<NDXGI::CHwQueue,void *>>>(
      v15,
      v32);
    std::_Deallocate<16>(v32, 64);
    *((_QWORD *)a2 + 4) = v35 + 16;
    v36 = v14;
    v16 = *((_QWORD *)this + 151);
    v21 = *((_QWORD *)this + 150);
  }
  catch ( std::bad_alloc )
  {
    if ( v35 != *((_QWORD *)this + 130) )
      std::list<NDXGI::CContext>::erase((char *)this + 1040, &v34);
    if ( this != (NDXGI::CDevice *)-1184LL )
      ReleaseSRWLockShared(SRWLock);
    if ( this != (NDXGI::CDevice *)-1032LL )
      ReleaseSRWLockExclusive(v24);
    return 2147942414LL;
  }
  catch ( _com_error *v30 )
  {
    if ( v35 != *((_QWORD *)this + 130) )
      std::list<NDXGI::CContext>::erase((char *)this + 1040, &v34);
    LODWORD(v34) = *((_DWORD *)v30 + 2);
    if ( this != (NDXGI::CDevice *)-1184LL )
      ReleaseSRWLockShared(SRWLock);
    if ( this != (NDXGI::CDevice *)-1032LL )
      ReleaseSRWLockExclusive(v24);
    return (unsigned int)v34;
  }
  while ( v21 != v16 )
  {
    (*(void (__fastcall **)(NDXGI::CDevice *, _QWORD, _QWORD, _QWORD, _QWORD, int, NDXGI::CContext **))(*(_QWORD *)this + 344LL))(
      this,
      *(unsigned int *)(*(_QWORD *)v21 + 12LL),
      0,
      0,
      **(_QWORD **)(*(_QWORD *)v21 + 24LL),
      1,
      &v36);
    v21 += 8;
  }
  v17 = (_QWORD **)*((_QWORD *)this + 154);
  for ( i = (_QWORD **)*((_QWORD *)this + 153); i != v17; ++i )
  {
    LOBYTE(v20) = *((_BYTE *)*i + 20);
    (*(void (__fastcall **)(NDXGI::CDevice *, _QWORD, _QWORD, __int64, _QWORD, int, NDXGI::CContext **))(*(_QWORD *)this + 344LL))(
      this,
      **i,
      *((unsigned int *)*i + 4),
      v20,
      (*i)[1],
      1,
      &v36);
  }
  *((_BYTE *)this + 899) |= *((_DWORD *)a2 + 3) == 16;
  NDXGI::CContext::QueryEngineType(v14);
  if ( this != (NDXGI::CDevice *)-1184LL )
    ReleaseSRWLockShared((PSRWLOCK)this + 148);
  if ( this != (NDXGI::CDevice *)-1032LL )
    ReleaseSRWLockExclusive((PSRWLOCK)this + 129);
  return (unsigned int)v34;
}

```

## disassembly

```asm
0x18005a904  mov     [rsp+arg_0], rcx
0x18005a909  push    rbx
0x18005a90a  push    rsi
0x18005a90b  push    rdi
0x18005a90c  push    r12
0x18005a90e  push    r13
0x18005a910  push    r14
0x18005a912  push    r15
0x18005a914  sub     rsp, 100h
0x18005a91b  mov     r14, rdx
0x18005a91e  mov     rsi, rcx
0x18005a921  mov     qword ptr [rdx+20h], 0
0x18005a929  mov     edx, [rdx+0Ch]
0x18005a92c  test    edx, 0FFFFFFE0h
0x18005a932  jnz     loc_18005ABFE
0x18005a938  mov     r8d, [r14+8]
0x18005a93c  cmp     r8d, 80h
0x18005a943  jnb     loc_18005AC69
0x18005a949  call    ?CheckContextType@CDevice@NDXGI@@QEAA_NW4D3DWDDM2_0DDI_CONTEXTTYPE_FLAG@@@Z; NDXGI::CDevice::CheckContextType(D3DWDDM2_0DDI_CONTEXTTYPE_FLAG)
0x18005a94e  test    al, al
0x18005a950  jz      loc_18005AC8C
0x18005a956  mov     [rsp+138h+var_CC], 0
0x18005a95f  mov     [rsp+138h+var_C4], 0
0x18005a967  mov     eax, [rcx+68h]
0x18005a96a  mov     [rsp+138h+var_E8], eax
0x18005a96e  mov     eax, [r14]
0x18005a971  mov     [rsp+138h+var_E4], eax
0x18005a975  mov     eax, [r14+4]
0x18005a979  mov     [rsp+138h+var_E0], eax
0x18005a97d  mov     [rsp+138h+var_DC], r8d
0x18005a982  mov     rax, [r14+10h]
0x18005a986  mov     [rsp+138h+var_D8], rax
0x18005a98b  mov     eax, [r14+18h]
0x18005a98f  mov     [rsp+138h+var_D0], eax
0x18005a993  mov     rcx, [rcx+48h]
0x18005a997  add     rcx, 10h
0x18005a99b  mov     rax, [rcx]
0x18005a99e  mov     rax, [rax+130h]
0x18005a9a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a9aa  and     eax, 0C0000000h
0x18005a9af  neg     eax
0x18005a9b1  sbb     eax, eax
0x18005a9b3  add     eax, 0Bh
0x18005a9b6  mov     dword ptr [rsp+138h+var_CC], eax
0x18005a9ba  mov     r12, [rsi+60h]
0x18005a9be  lea     rbx, [rsi+408h]
0x18005a9c5  mov     [rsp+138h+var_F0], rbx
0x18005a9ca  mov     rcx, rbx; SRWLock
0x18005a9cd  call    cs:__imp_AcquireSRWLockExclusive
0x18005a9d3  nop
0x18005a9d4  lea     rdi, [rsi+4A0h]
0x18005a9db  mov     [rsp+138h+SRWLock], rdi
0x18005a9e0  mov     rcx, rdi; SRWLock
0x18005a9e3  call    cs:__imp_AcquireSRWLockShared
0x18005a9e9  nop
0x18005a9ea  lea     r15, [rsi+410h]
0x18005a9f1  mov     rax, [r15]
0x18005a9f4  mov     [rsp+138h+arg_10], rax
0x18005a9fc  lea     rcx, [rsp+138h+var_B8]; this
0x18005aa04  call    ??0CContext@NDXGI@@QEAA@XZ; NDXGI::CContext::CContext(void)
0x18005aa09  nop
0x18005aa0a  mov     rdx, rax
0x18005aa0d  mov     rcx, r15
0x18005aa10  call    ?push_back@?$list@VCContext@NDXGI@@V?$allocator@VCContext@NDXGI@@@std@@@std@@QEAAX$$QEAVCContext@NDXGI@@@Z; std::list<NDXGI::CContext>::push_back(NDXGI::CContext &&)
0x18005aa15  nop
0x18005aa16  mov     rdx, [rsp+138h+var_60]
0x18005aa1e  call    ??$_Free_non_head@V?$allocator@U?$_List_node@VCHwQueue@NDXGI@@PEAX@std@@@std@@@?$_List_node@VCHwQueue@NDXGI@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@VCHwQueue@NDXGI@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<NDXGI::CHwQueue,void *>::_Free_non_head<std::allocator<std::_List_node<NDXGI::CHwQueue,void *>>>(std::allocator<std::_List_node<NDXGI::CHwQueue,void *>> &,std::_List_node<NDXGI::CHwQueue,void *> *)
0x18005aa23  mov     edx, 40h ; '@'
0x18005aa28  mov     rcx, [rsp+138h+var_60]
0x18005aa30  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18005aa35  mov     rax, [r15]
0x18005aa38  mov     r13, [rax+8]
0x18005aa3c  mov     [rsp+138h+arg_10], r13
0x18005aa44  lea     r15, [rsi+420h]
0x18005aa4b  mov     [rsp+138h+arg_8], r15
0x18005aa53  mov     rcx, r15; lpCriticalSection
0x18005aa56  call    cs:__imp_EnterCriticalSection
0x18005aa5c  nop
0x18005aa5d  lea     rcx, [rsi+448h]
0x18005aa64  mov     rdx, [rsi+418h]
0x18005aa6b  call    ?reserve@?$vector@IV?$allocator@I@std@@@std@@QEAAX_K@Z; std::vector<uint>::reserve(unsigned __int64)
0x18005aa70  nop
0x18005aa71  mov     rcx, r15; lpCriticalSection
0x18005aa74  call    cs:__imp_LeaveCriticalSection
0x18005aa7a  lea     r8, [rsp+138h+var_E8]
0x18005aa7f  mov     rcx, [r12+2B0h]
0x18005aa87  call    ??$CallAndLogImpl@P6AJPEAU_D3DKMT_CREATECONTEXTVIRTUAL@@@ZPEAU1@@@YAJP6AJPEAU_D3DKMT_CREATECONTEXTVIRTUAL@@@ZPEBD0@Z; CallAndLogImpl<long (*)(_D3DKMT_CREATECONTEXTVIRTUAL *),_D3DKMT_CREATECONTEXTVIRTUAL *>(long (*)(_D3DKMT_CREATECONTEXTVIRTUAL *),char const *,_D3DKMT_CREATECONTEXTVIRTUAL *)
0x18005aa8c  mov     edx, eax; int
0x18005aa8e  mov     rcx, rsi; this
0x18005aa91  call    ?NTStatusToHResult@CDevice@NDXGI@@QEAAJJ@Z; NDXGI::CDevice::NTStatusToHResult(long)
0x18005aa96  mov     dword ptr [rsp+138h+arg_8], eax
0x18005aa9d  mov     ecx, eax; int
0x18005aa9f  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18005aaa4  mov     r9d, [r14+0Ch]
0x18005aaa8  lea     r8, [rsp+138h+var_E8]
0x18005aaad  mov     rdx, rsi
0x18005aab0  lea     rcx, [rsp+138h+var_B8]
0x18005aab8  call    ??0CContext@NDXGI@@QEAA@PEAVCDevice@1@AEBU_D3DKMT_CREATECONTEXTVIRTUAL@@W4D3DWDDM2_0DDI_CONTEXTTYPE_FLAG@@@Z; NDXGI::CContext::CContext(NDXGI::CDevice *,_D3DKMT_CREATECONTEXTVIRTUAL const &,D3DWDDM2_0DDI_CONTEXTTYPE_FLAG)
0x18005aabd  add     r13, 10h
0x18005aac1  mov     rdx, rax
0x18005aac4  mov     rcx, r13
0x18005aac7  call    ??4CContext@NDXGI@@QEAAAEAV01@$$QEAV01@@Z; NDXGI::CContext::operator=(NDXGI::CContext &&)
0x18005aacc  mov     rdx, [rsp+138h+var_60]
0x18005aad4  call    ??$_Free_non_head@V?$allocator@U?$_List_node@VCHwQueue@NDXGI@@PEAX@std@@@std@@@?$_List_node@VCHwQueue@NDXGI@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@VCHwQueue@NDXGI@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<NDXGI::CHwQueue,void *>::_Free_non_head<std::allocator<std::_List_node<NDXGI::CHwQueue,void *>>>(std::allocator<std::_List_node<NDXGI::CHwQueue,void *>> &,std::_List_node<NDXGI::CHwQueue,void *> *)
0x18005aad9  mov     edx, 40h ; '@'
0x18005aade  mov     rcx, [rsp+138h+var_60]
0x18005aae6  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18005aaeb  mov     [r14+20h], r13
0x18005aaef  mov     [rsp+138h+arg_18], r13
0x18005aaf7  mov     r12, [rsi+4B8h]
0x18005aafe  mov     r15, [rsi+4B0h]
0x18005ab05  cmp     r15, r12
0x18005ab08  jnz     short loc_18005AB6F
0x18005ab0a  mov     r12, [rsi+4D0h]
0x18005ab11  mov     r15, [rsi+4C8h]
0x18005ab18  cmp     r15, r12
0x18005ab1b  jnz     loc_18005ABB7
0x18005ab21  cmp     dword ptr [r14+0Ch], 10h
0x18005ab26  setz    al
0x18005ab29  or      [rsi+383h], al
0x18005ab2f  mov     rcx, r13; this
0x18005ab32  call    ?QueryEngineType@CContext@NDXGI@@QEAAXXZ; NDXGI::CContext::QueryEngineType(void)
0x18005ab37  nop
0x18005ab38  test    rdi, rdi
0x18005ab3b  jz      short loc_18005AB47
0x18005ab3d  mov     rcx, rdi; SRWLock
0x18005ab40  call    cs:__imp_ReleaseSRWLockShared
0x18005ab46  nop
0x18005ab47  test    rbx, rbx
0x18005ab4a  jz      short loc_18005AB55
0x18005ab4c  mov     rcx, rbx; SRWLock
0x18005ab4f  call    cs:__imp_ReleaseSRWLockExclusive
0x18005ab55  mov     eax, dword ptr [rsp+138h+arg_8]
0x18005ab5c  add     rsp, 100h
0x18005ab63  pop     r15
0x18005ab65  pop     r14
0x18005ab67  pop     r13
0x18005ab69  pop     r12
0x18005ab6b  pop     rdi
0x18005ab6c  pop     rsi
0x18005ab6d  pop     rbx
0x18005ab6e  retn
0x18005ab6f  mov     rax, [r15]
0x18005ab72  mov     rcx, [rsi]
0x18005ab75  mov     r8, [rax+18h]
0x18005ab79  mov     edx, [rax+0Ch]
0x18005ab7c  mov     rax, [rcx+158h]
0x18005ab83  lea     rcx, [rsp+138h+arg_18]
0x18005ab8b  mov     [rsp+138h+var_108], rcx
0x18005ab90  mov     [rsp+138h+var_110], 1
0x18005ab98  mov     rcx, [r8]
0x18005ab9b  mov     qword ptr [rsp+138h+var_118], rcx
0x18005aba0  xor     r9d, r9d
0x18005aba3  xor     r8d, r8d
0x18005aba6  mov     rcx, rsi
0x18005aba9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005abae  add     r15, 8
0x18005abb2  jmp     loc_18005AB05
0x18005abb7  mov     rdx, [r15]
0x18005abba  mov     rax, [rsi]
0x18005abbd  lea     rcx, [rsp+138h+arg_18]
0x18005abc5  mov     [rsp+138h+var_108], rcx
0x18005abca  mov     [rsp+138h+var_110], 1
0x18005abd2  mov     rcx, [rdx+8]
0x18005abd6  mov     qword ptr [rsp+138h+var_118], rcx
0x18005abdb  mov     r9b, [rdx+14h]
0x18005abdf  mov     r8d, [rdx+10h]
0x18005abe3  mov     rdx, [rdx]
0x18005abe6  mov     rcx, rsi
0x18005abe9  mov     rax, [rax+158h]
0x18005abf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005abf5  add     r15, 8
0x18005abf9  jmp     loc_18005AB18
0x18005abfe  lea     r8, aInvalidContext; "Invalid context type passed to CreateCo"...
0x18005ac05  mov     [rsp+138h+var_118], 1; bool
0x18005ac0a  mov     edx, 80070057h; unsigned int
0x18005ac0f  lea     rcx, ?g_Module@@3VCModule@@A; this
0x18005ac16  call    ?RecordJournal@CModule@@QEAAXIPEBD_N1@Z; CModule::RecordJournal(uint,char const *,bool,bool)
0x18005ac1b  mov     eax, 80070057h
0x18005ac20  jmp     loc_18005AB5C
0x18005ac25  call    cs:__imp_ReleaseSRWLockShared
0x18005ac2b  nop
0x18005ac2c  mov     rcx, [rsp+138h+var_F0]; SRWLock
0x18005ac31  test    rcx, rcx
0x18005ac34  jz      short loc_18005AC3C
0x18005ac36  call    cs:__imp_ReleaseSRWLockExclusive
0x18005ac3c  mov     eax, 8007000Eh
0x18005ac41  jmp     loc_18005AB5C
0x18005ac46  call    cs:__imp_ReleaseSRWLockShared
0x18005ac4c  nop
0x18005ac4d  mov     rcx, [rsp+138h+var_F0]; SRWLock
0x18005ac52  test    rcx, rcx
0x18005ac55  jz      short loc_18005AC5D
0x18005ac57  call    cs:__imp_ReleaseSRWLockExclusive
0x18005ac5d  mov     eax, dword ptr [rsp+138h+arg_8]
0x18005ac64  jmp     loc_18005AB5C
0x18005ac69  mov     rax, 1000300000000h
0x18005ac73  cmp     [rcx+388h], rax
0x18005ac7a  jbe     loc_18005A949
0x18005ac80  lea     r8, aReservedFlagsG_5; "Reserved flags given to CreateContextVi"...
0x18005ac87  jmp     loc_18005AC05
0x18005ac8c  lea     rcx, OutputString; "If caps indicate that D3DWDDM2_0DDI_IMA"...
0x18005ac93  call    cs:__imp_OutputDebugStringA
0x18005ac99  jmp     short loc_18005AC1B
0x18005ac9b  mov     rcx, [rsp+138h+SRWLock]; SRWLock
0x18005aca0  test    rcx, rcx
0x18005aca3  jz      short loc_18005AC2C
0x18005aca5  jmp     loc_18005AC25
0x18005acaa  mov     rcx, [rsp+138h+SRWLock]; SRWLock
0x18005acaf  test    rcx, rcx
0x18005acb2  jz      short loc_18005AC4D
0x18005acb4  jmp     short loc_18005AC46
```
