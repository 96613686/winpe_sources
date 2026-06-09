# NDXGI::CDevice::CreateContext2(D3DWDDM2_0DDICB_CREATECONTEXT *)

- ea: `0x1800591d8`
- end: `0x180059619`
- name: `?CreateContext2@CDevice@NDXGI@@QEAAJPEAUD3DWDDM2_0DDICB_CREATECONTEXT@@@Z`
- size: `1089`
- prototype: `__int64 __fastcall(NDXGI::CDevice *__hidden this, struct D3DWDDM2_0DDICB_CREATECONTEXT *)`
- caller_count: `2`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x180059080`
- `0x18013e690`

## callees

- `0x180022400`
- `0x180022630`
- `0x1800229a0`
- `0x180059140`
- `0x1800591d8`
- `0x18005acc0`
- `0x18005acf8`
- `0x18005ae00`
- `0x18005aeb8`
- `0x18005b100`
- `0x18005b17c`
- `0x18005b214`
- `0x18005c048`
- `0x18009d94c`
- `0x1800aa9a8`
- `0x1801cb010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800592a3`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800592a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800593cf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800593cf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800593b1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800593b1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005933f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005933f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800595a8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800595d2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800595fa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800595a8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800595d2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800595fa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180059329`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180059329`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180059599`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800595c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800595e9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180059599`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800595c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800595e9`

## string_xrefs

- `0x180059258`: `Reserved flags given to CreateContextCb`
- `0x18005928a`: `Invalid context type passed to CreateContext2Cb`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall NDXGI::CDevice::CreateContext2(
        NDXGI::CDevice *this,
        struct D3DWDDM2_0DDICB_CREATECONTEXT *a2,
        __int64 a3,
        __int64 a4)
{
  unsigned int v6; // ebx
  char *v7; // r8
  __int64 v9; // rcx
  __int64 v10; // rdx
  int v11; // eax
  __int64 v12; // rax
  NDXGI::CContext *v13; // r13
  __int64 v14; // rcx
  __int64 v15; // r9
  __int64 i; // r12
  _QWORD **j; // r12
  __int64 v18; // [rsp+40h] [rbp-138h]
  _QWORD **v19; // [rsp+40h] [rbp-138h]
  RTL_SRWLOCK *SRWLock; // [rsp+48h] [rbp-130h]
  RTL_SRWLOCK *v21; // [rsp+50h] [rbp-128h]
  _DWORD v22[4]; // [rsp+60h] [rbp-118h] BYREF
  __int64 v23; // [rsp+70h] [rbp-108h]
  int v24; // [rsp+78h] [rbp-100h]
  int v25; // [rsp+7Ch] [rbp-FCh]
  __int64 v26; // [rsp+88h] [rbp-F0h]
  int v27; // [rsp+90h] [rbp-E8h]
  __int64 v28; // [rsp+98h] [rbp-E0h]
  int v29; // [rsp+A0h] [rbp-D8h]
  __int64 v30; // [rsp+A8h] [rbp-D0h]
  int v31; // [rsp+B0h] [rbp-C8h]
  __int64 v32; // [rsp+B8h] [rbp-C0h]
  _com_error *v33; // [rsp+C0h] [rbp-B8h] BYREF
  _BYTE v34[88]; // [rsp+C8h] [rbp-B0h] BYREF
  __int64 v35; // [rsp+120h] [rbp-58h]
  NDXGI::CDevice *v36; // [rsp+180h] [rbp+8h] BYREF
  __int64 v37; // [rsp+188h] [rbp+10h]
  __int64 v38; // [rsp+190h] [rbp+18h]
  NDXGI::CContext *v39; // [rsp+198h] [rbp+20h] BYREF

  v36 = this;
  *((_QWORD *)a2 + 4) = 0;
  *((_QWORD *)a2 + 5) = 0;
  *((_DWORD *)a2 + 12) = 0;
  *((_QWORD *)a2 + 7) = 0;
  *((_DWORD *)a2 + 16) = 0;
  *((_QWORD *)a2 + 9) = 0;
  *((_DWORD *)a2 + 20) = 0;
  if ( *((_BYTE *)this + 897) )
    *((_QWORD *)a2 + 11) = 0;
  v6 = *((_DWORD *)a2 + 2);
  if ( v6 >= 0x80 && *((_QWORD *)this + 113) > 0x1000300000000uLL )
  {
    v7 = "Reserved flags given to CreateContextCb";
LABEL_6:
    CModule::RecordJournal((CModule *)&g_Module, -2147024809, v7, a4, 1);
    return 2147942487LL;
  }
  if ( (*((_DWORD *)a2 + 3) & 0xFFFFFFE0) != 0 )
  {
    v7 = "Invalid context type passed to CreateContext2Cb";
    goto LABEL_6;
  }
  if ( !(unsigned __int8)NDXGI::CDevice::CheckContextType() )
  {
    OutputDebugStringA(
      "If caps indicate that D3DWDDM2_0DDI_IMAGE_FUNCTIONS are supported, D3DWDDM2_0DDI_CONTEXTTYPE_IMAGE is a mutually e"
      "xclusive context type.\n");
    return 2147942487LL;
  }
  memset_0(v22, 0, 0x60u);
  v22[0] = *((_DWORD *)this + 26);
  v22[1] = *(_DWORD *)a2;
  v22[2] = *((_DWORD *)a2 + 1);
  v22[3] = v6;
  v23 = *((_QWORD *)a2 + 2);
  v24 = *((_DWORD *)a2 + 6);
  v25 = 11
      - (((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)this + 9) + 16LL) + 304LL))(*((_QWORD *)this + 9) + 16LL)
        & 0xC0000000) != 0);
  v37 = *((_QWORD *)this + 12);
  v21 = (RTL_SRWLOCK *)((char *)this + 1032);
  AcquireSRWLockExclusive((PSRWLOCK)this + 129);
  SRWLock = (RTL_SRWLOCK *)((char *)this + 1184);
  AcquireSRWLockShared((PSRWLOCK)this + 148);
  NDXGI::CContext::CContext((NDXGI::CContext *)v34);
  try
  {
    std::list<NDXGI::CContext>::push_back();
    std::_List_node<NDXGI::CHwQueue,void *>::_Free_non_head<std::allocator<std::_List_node<NDXGI::CHwQueue,void *>>>(
      v9,
      v35);
    std::_Deallocate<16>(v35, 64);
    v38 = *(_QWORD *)(*((_QWORD *)this + 130) + 8LL);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1056));
    std::vector<unsigned int>::reserve((char *)this + 1096, *((_QWORD *)this + 131));
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1056));
    v11 = CallAndLogImpl<long (*)(_D3DKMT_CREATECONTEXT *),_D3DKMT_CREATECONTEXT *>(*(_QWORD *)(v37 + 264), v10, v22);
    LODWORD(v37) = NDXGI::CDevice::NTStatusToHResult(this, v11);
    ThrowFailure(v37);
    v12 = NDXGI::CContext::CContext(v34, this, v22, *((unsigned int *)a2 + 3));
    v13 = (NDXGI::CContext *)(v38 + 16);
    NDXGI::CContext::operator=(v38 + 16, v12);
    std::_List_node<NDXGI::CHwQueue,void *>::_Free_non_head<std::allocator<std::_List_node<NDXGI::CHwQueue,void *>>>(
      v14,
      v35);
    std::_Deallocate<16>(v35, 64);
    *((_QWORD *)a2 + 4) = v38 + 16;
    *((_QWORD *)a2 + 5) = v26;
    *((_DWORD *)a2 + 12) = v27;
    *((_QWORD *)a2 + 7) = v28;
    *((_DWORD *)a2 + 16) = v29;
    *((_QWORD *)a2 + 9) = v30;
    *((_DWORD *)a2 + 20) = v31;
    if ( *((_BYTE *)this + 897) )
      *((_QWORD *)a2 + 11) = v32;
    v39 = v13;
    v18 = *((_QWORD *)this + 151);
    for ( i = *((_QWORD *)this + 150); i != v18; i += 8 )
      (*(void (__fastcall **)(NDXGI::CDevice *, _QWORD, _QWORD, _QWORD, _QWORD, int, NDXGI::CContext **))(*(_QWORD *)this + 344LL))(
        this,
        *(unsigned int *)(*(_QWORD *)i + 12LL),
        0,
        0,
        **(_QWORD **)(*(_QWORD *)i + 24LL),
        1,
        &v39);
    v19 = (_QWORD **)*((_QWORD *)this + 154);
    for ( j = (_QWORD **)*((_QWORD *)this + 153); j != v19; ++j )
    {
      LOBYTE(v15) = *((_BYTE *)*j + 20);
      (*(void (__fastcall **)(NDXGI::CDevice *, _QWORD, _QWORD, __int64, _QWORD, int, NDXGI::CContext **))(*(_QWORD *)this + 344LL))(
        this,
        **j,
        *((unsigned int *)*j + 4),
        v15,
        (*j)[1],
        1,
        &v39);
    }
    *((_BYTE *)this + 899) |= *((_DWORD *)a2 + 3) == 16;
    NDXGI::CContext::QueryEngineType(v13);
  }
  catch ( std::bad_alloc )
  {
    if ( v38 != *((_QWORD *)v36 + 130) )
      std::list<NDXGI::CContext>::erase((char *)v36 + 1040, &v36);
    if ( this != (NDXGI::CDevice *)-1184LL )
      ReleaseSRWLockShared(SRWLock);
    if ( this != (NDXGI::CDevice *)-1032LL )
      ReleaseSRWLockExclusive(v21);
    return 2147942414LL;
  }
  catch ( _com_error *v33 )
  {
    if ( v38 != *((_QWORD *)v36 + 130) )
      std::list<NDXGI::CContext>::erase((char *)v36 + 1040, &v36);
    LODWORD(v36) = *((_DWORD *)v33 + 2);
    if ( this != (NDXGI::CDevice *)-1184LL )
      ReleaseSRWLockShared(SRWLock);
    if ( this != (NDXGI::CDevice *)-1032LL )
      ReleaseSRWLockExclusive(v21);
    return (unsigned int)v36;
  }
  if ( this != (NDXGI::CDevice *)-1184LL )
    ReleaseSRWLockShared((PSRWLOCK)this + 148);
  if ( this != (NDXGI::CDevice *)-1032LL )
    ReleaseSRWLockExclusive((PSRWLOCK)this + 129);
  return (unsigned int)v37;
}

```

## disassembly

```asm
0x1800591d8  mov     [rsp+arg_0], rcx
0x1800591dd  push    rbx
0x1800591de  push    rdi
0x1800591df  push    r12
0x1800591e1  push    r13
0x1800591e3  push    r14
0x1800591e5  push    r15
0x1800591e7  sub     rsp, 148h
0x1800591ee  mov     r15, rdx
0x1800591f1  mov     r14, rcx
0x1800591f4  mov     qword ptr [rdx+20h], 0
0x1800591fc  mov     qword ptr [rdx+28h], 0
0x180059204  mov     dword ptr [rdx+30h], 0
0x18005920b  mov     qword ptr [rdx+38h], 0
0x180059213  mov     dword ptr [rdx+40h], 0
0x18005921a  mov     qword ptr [rdx+48h], 0
0x180059222  mov     dword ptr [rdx+50h], 0
0x180059229  cmp     byte ptr [rcx+381h], 0
0x180059230  jz      short loc_18005923A
0x180059232  mov     qword ptr [rdx+58h], 0
0x18005923a  mov     ebx, [rdx+8]
0x18005923d  cmp     ebx, 80h
0x180059243  jb      short loc_18005927F
0x180059245  mov     rax, 1000300000000h
0x18005924f  cmp     [rcx+388h], rax
0x180059256  jbe     short loc_18005927F
0x180059258  lea     r8, aReservedFlagsG_7; "Reserved flags given to CreateContextCb"
0x18005925f  mov     [rsp+178h+var_158], 1; bool
0x180059264  mov     edx, 80070057h; unsigned int
0x180059269  lea     rcx, ?g_Module@@3VCModule@@A; this
0x180059270  call    ?RecordJournal@CModule@@QEAAXIPEBD_N1@Z; CModule::RecordJournal(uint,char const *,bool,bool)
0x180059275  mov     eax, 80070057h
0x18005927a  jmp     loc_180059607
0x18005927f  mov     edx, [rdx+0Ch]
0x180059282  test    edx, 0FFFFFFE0h
0x180059288  jz      short loc_180059293
0x18005928a  lea     r8, aInvalidContext_0; "Invalid context type passed to CreateCo"...
0x180059291  jmp     short loc_18005925F
0x180059293  call    ?CheckContextType@CDevice@NDXGI@@QEAA_NW4D3DWDDM2_0DDI_CONTEXTTYPE_FLAG@@@Z; NDXGI::CDevice::CheckContextType(D3DWDDM2_0DDI_CONTEXTTYPE_FLAG)
0x180059298  test    al, al
0x18005929a  jnz     short loc_1800592AB
0x18005929c  lea     rcx, OutputString; "If caps indicate that D3DWDDM2_0DDI_IMA"...
0x1800592a3  call    cs:__imp_OutputDebugStringA
0x1800592a9  jmp     short loc_180059275
0x1800592ab  xor     edx, edx; Val
0x1800592ad  lea     r8d, [rdx+60h]; Size
0x1800592b1  lea     rcx, [rsp+178h+var_118]; void *
0x1800592b6  call    memset_0
0x1800592bb  mov     eax, [r14+68h]
0x1800592bf  mov     [rsp+178h+var_118], eax
0x1800592c3  mov     eax, [r15]
0x1800592c6  mov     [rsp+178h+var_114], eax
0x1800592ca  mov     eax, [r15+4]
0x1800592ce  mov     [rsp+178h+var_110], eax
0x1800592d2  mov     [rsp+178h+var_10C], ebx
0x1800592d6  mov     rax, [r15+10h]
0x1800592da  mov     [rsp+178h+var_108], rax
0x1800592df  mov     eax, [r15+18h]
0x1800592e3  mov     [rsp+178h+var_100], eax
0x1800592e7  mov     rcx, [r14+48h]
0x1800592eb  add     rcx, 10h
0x1800592ef  mov     rax, [rcx]
0x1800592f2  mov     rax, [rax+130h]
0x1800592f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800592fe  and     eax, 0C0000000h
0x180059303  neg     eax
0x180059305  sbb     eax, eax
0x180059307  add     eax, 0Bh
0x18005930a  mov     [rsp+178h+var_FC], eax
0x18005930e  mov     rax, [r14+60h]
0x180059312  mov     [rsp+178h+arg_8], rax
0x18005931a  lea     rbx, [r14+408h]
0x180059321  mov     [rsp+178h+var_128], rbx
0x180059326  mov     rcx, rbx; SRWLock
0x180059329  call    cs:__imp_AcquireSRWLockExclusive
0x18005932f  nop
0x180059330  lea     rdi, [r14+4A0h]
0x180059337  mov     [rsp+178h+SRWLock], rdi
0x18005933c  mov     rcx, rdi; SRWLock
0x18005933f  call    cs:__imp_AcquireSRWLockShared
0x180059345  nop
0x180059346  lea     r12, [r14+410h]
0x18005934d  mov     rax, [r12]
0x180059351  mov     [rsp+178h+arg_10], rax
0x180059359  lea     rcx, [rsp+178h+var_B0]; this
0x180059361  call    ??0CContext@NDXGI@@QEAA@XZ; NDXGI::CContext::CContext(void)
0x180059366  nop
0x180059367  mov     rdx, rax
0x18005936a  mov     rcx, r12
0x18005936d  call    ?push_back@?$list@VCContext@NDXGI@@V?$allocator@VCContext@NDXGI@@@std@@@std@@QEAAX$$QEAVCContext@NDXGI@@@Z; std::list<NDXGI::CContext>::push_back(NDXGI::CContext &&)
0x180059372  nop
0x180059373  mov     rdx, [rsp+178h+var_58]
0x18005937b  call    ??$_Free_non_head@V?$allocator@U?$_List_node@VCHwQueue@NDXGI@@PEAX@std@@@std@@@?$_List_node@VCHwQueue@NDXGI@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@VCHwQueue@NDXGI@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<NDXGI::CHwQueue,void *>::_Free_non_head<std::allocator<std::_List_node<NDXGI::CHwQueue,void *>>>(std::allocator<std::_List_node<NDXGI::CHwQueue,void *>> &,std::_List_node<NDXGI::CHwQueue,void *> *)
0x180059380  mov     edx, 40h ; '@'
0x180059385  mov     rcx, [rsp+178h+var_58]
0x18005938d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180059392  mov     rax, [r12]
0x180059396  mov     r13, [rax+8]
0x18005939a  mov     [rsp+178h+arg_10], r13
0x1800593a2  lea     r12, [r14+420h]
0x1800593a9  mov     [rsp+178h+var_138], r12
0x1800593ae  mov     rcx, r12; lpCriticalSection
0x1800593b1  call    cs:__imp_EnterCriticalSection
0x1800593b7  nop
0x1800593b8  lea     rcx, [r14+448h]
0x1800593bf  mov     rdx, [r14+418h]
0x1800593c6  call    ?reserve@?$vector@IV?$allocator@I@std@@@std@@QEAAX_K@Z; std::vector<uint>::reserve(unsigned __int64)
0x1800593cb  nop
0x1800593cc  mov     rcx, r12; lpCriticalSection
0x1800593cf  call    cs:__imp_LeaveCriticalSection
0x1800593d5  lea     r8, [rsp+178h+var_118]
0x1800593da  mov     rcx, [rsp+178h+arg_8]
0x1800593e2  mov     rcx, [rcx+108h]
0x1800593e9  call    ??$CallAndLogImpl@P6AJPEAU_D3DKMT_CREATECONTEXT@@@ZPEAU1@@@YAJP6AJPEAU_D3DKMT_CREATECONTEXT@@@ZPEBD0@Z; CallAndLogImpl<long (*)(_D3DKMT_CREATECONTEXT *),_D3DKMT_CREATECONTEXT *>(long (*)(_D3DKMT_CREATECONTEXT *),char const *,_D3DKMT_CREATECONTEXT *)
0x1800593ee  mov     edx, eax; int
0x1800593f0  mov     rcx, r14; this
0x1800593f3  call    ?NTStatusToHResult@CDevice@NDXGI@@QEAAJJ@Z; NDXGI::CDevice::NTStatusToHResult(long)
0x1800593f8  mov     dword ptr [rsp+178h+arg_8], eax
0x1800593ff  mov     ecx, eax; int
0x180059401  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180059406  mov     r9d, [r15+0Ch]
0x18005940a  lea     r8, [rsp+178h+var_118]
0x18005940f  mov     rdx, r14
0x180059412  lea     rcx, [rsp+178h+var_B0]
0x18005941a  call    ??0CContext@NDXGI@@QEAA@PEAVCDevice@1@AEBU_D3DKMT_CREATECONTEXT@@W4D3DWDDM2_0DDI_CONTEXTTYPE_FLAG@@@Z; NDXGI::CContext::CContext(NDXGI::CDevice *,_D3DKMT_CREATECONTEXT const &,D3DWDDM2_0DDI_CONTEXTTYPE_FLAG)
0x18005941f  add     r13, 10h
0x180059423  mov     rdx, rax
0x180059426  mov     rcx, r13
0x180059429  call    ??4CContext@NDXGI@@QEAAAEAV01@$$QEAV01@@Z; NDXGI::CContext::operator=(NDXGI::CContext &&)
0x18005942e  mov     rdx, [rsp+178h+var_58]
0x180059436  call    ??$_Free_non_head@V?$allocator@U?$_List_node@VCHwQueue@NDXGI@@PEAX@std@@@std@@@?$_List_node@VCHwQueue@NDXGI@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@VCHwQueue@NDXGI@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<NDXGI::CHwQueue,void *>::_Free_non_head<std::allocator<std::_List_node<NDXGI::CHwQueue,void *>>>(std::allocator<std::_List_node<NDXGI::CHwQueue,void *>> &,std::_List_node<NDXGI::CHwQueue,void *> *)
0x18005943b  mov     edx, 40h ; '@'
0x180059440  mov     rcx, [rsp+178h+var_58]
0x180059448  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18005944d  mov     [r15+20h], r13
0x180059451  mov     rax, [rsp+178h+var_F0]
0x180059459  mov     [r15+28h], rax
0x18005945d  mov     eax, [rsp+178h+var_E8]
0x180059464  mov     [r15+30h], eax
0x180059468  mov     rax, [rsp+178h+var_E0]
0x180059470  mov     [r15+38h], rax
0x180059474  mov     eax, [rsp+178h+var_D8]
0x18005947b  mov     [r15+40h], eax
0x18005947f  mov     rax, [rsp+178h+var_D0]
0x180059487  mov     [r15+48h], rax
0x18005948b  mov     eax, [rsp+178h+var_C8]
0x180059492  mov     [r15+50h], eax
0x180059496  cmp     byte ptr [r14+381h], 0
0x18005949e  jz      short loc_1800594AC
0x1800594a0  mov     rax, [rsp+178h+var_C0]
0x1800594a8  mov     [r15+58h], rax
0x1800594ac  mov     [rsp+178h+arg_18], r13
0x1800594b4  mov     rax, [r14+4B8h]
0x1800594bb  mov     [rsp+178h+var_138], rax
0x1800594c0  mov     r12, [r14+4B0h]
0x1800594c7  cmp     r12, rax
0x1800594ca  jz      short loc_180059517
0x1800594cc  mov     rax, [r12]
0x1800594d0  mov     rcx, [r14]
0x1800594d3  mov     r8, [rax+18h]
0x1800594d7  mov     edx, [rax+0Ch]
0x1800594da  mov     rax, [rcx+158h]
0x1800594e1  lea     rcx, [rsp+178h+arg_18]
0x1800594e9  mov     [rsp+178h+var_148], rcx
0x1800594ee  mov     [rsp+178h+var_150], 1
0x1800594f6  mov     rcx, [r8]
0x1800594f9  mov     qword ptr [rsp+178h+var_158], rcx
0x1800594fe  xor     r9d, r9d
0x180059501  xor     r8d, r8d
0x180059504  mov     rcx, r14
0x180059507  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005950c  add     r12, 8
0x180059510  cmp     r12, [rsp+178h+var_138]
0x180059515  jnz     short loc_1800594CC
0x180059517  mov     rax, [r14+4D0h]
0x18005951e  mov     [rsp+178h+var_138], rax
0x180059523  mov     r12, [r14+4C8h]
0x18005952a  cmp     r12, rax
0x18005952d  jz      short loc_180059579
0x18005952f  mov     rdx, [r12]
0x180059533  mov     rax, [r14]
0x180059536  lea     rcx, [rsp+178h+arg_18]
0x18005953e  mov     [rsp+178h+var_148], rcx
0x180059543  mov     [rsp+178h+var_150], 1
0x18005954b  mov     rcx, [rdx+8]
0x18005954f  mov     qword ptr [rsp+178h+var_158], rcx
0x180059554  mov     r9b, [rdx+14h]
0x180059558  mov     r8d, [rdx+10h]
0x18005955c  mov     rdx, [rdx]
0x18005955f  mov     rcx, r14
0x180059562  mov     rax, [rax+158h]
0x180059569  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005956e  add     r12, 8
0x180059572  cmp     r12, [rsp+178h+var_138]
0x180059577  jnz     short loc_18005952F
0x180059579  cmp     dword ptr [r15+0Ch], 10h
0x18005957e  setz    al
0x180059581  or      [r14+383h], al
0x180059588  mov     rcx, r13; this
0x18005958b  call    ?QueryEngineType@CContext@NDXGI@@QEAAXXZ; NDXGI::CContext::QueryEngineType(void)
0x180059590  nop
0x180059591  test    rdi, rdi
0x180059594  jz      short loc_1800595A0
0x180059596  mov     rcx, rdi; SRWLock
0x180059599  call    cs:__imp_ReleaseSRWLockShared
0x18005959f  nop
0x1800595a0  test    rbx, rbx
0x1800595a3  jz      short loc_1800595AE
0x1800595a5  mov     rcx, rbx; SRWLock
0x1800595a8  call    cs:__imp_ReleaseSRWLockExclusive
0x1800595ae  mov     eax, dword ptr [rsp+178h+arg_8]
0x1800595b5  jmp     short loc_180059607
0x1800595b7  mov     rcx, [rsp+178h+SRWLock]; SRWLock
0x1800595bc  test    rcx, rcx
0x1800595bf  jz      short loc_1800595C8
0x1800595c1  call    cs:__imp_ReleaseSRWLockShared
0x1800595c7  nop
0x1800595c8  mov     rcx, [rsp+178h+var_128]; SRWLock
0x1800595cd  test    rcx, rcx
0x1800595d0  jz      short loc_1800595D8
0x1800595d2  call    cs:__imp_ReleaseSRWLockExclusive
0x1800595d8  mov     eax, 8007000Eh
0x1800595dd  jmp     short loc_180059607
0x1800595df  mov     rcx, [rsp+178h+SRWLock]; SRWLock
0x1800595e4  test    rcx, rcx
0x1800595e7  jz      short loc_1800595F0
0x1800595e9  call    cs:__imp_ReleaseSRWLockShared
0x1800595ef  nop
0x1800595f0  mov     rcx, [rsp+178h+var_128]; SRWLock
0x1800595f5  test    rcx, rcx
0x1800595f8  jz      short loc_180059600
0x1800595fa  call    cs:__imp_ReleaseSRWLockExclusive
0x180059600  mov     eax, dword ptr [rsp+178h+arg_0]
0x180059607  add     rsp, 148h
0x18005960e  pop     r15
0x180059610  pop     r14
0x180059612  pop     r13
0x180059614  pop     r12
0x180059616  pop     rdi
0x180059617  pop     rbx
0x180059618  retn
```
