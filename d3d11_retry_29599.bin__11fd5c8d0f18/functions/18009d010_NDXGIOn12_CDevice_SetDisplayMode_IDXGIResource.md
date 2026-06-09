# NDXGIOn12::CDevice::SetDisplayMode(IDXGIResource *)

- ea: `0x18009d010`
- end: `0x18009d3df`
- name: `?SetDisplayMode@CDevice@NDXGIOn12@@UEAAJPEAUIDXGIResource@@@Z`
- size: `975`
- prototype: `__int64 __fastcall(NDXGIOn12::CDevice *__hidden this, struct IDXGIResource *)`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x180009660`
- `0x18001e2a0`
- `0x18002bd20`
- `0x18002d0f0`
- `0x18002e160`
- `0x180034550`
- `0x180043d64`
- `0x18009d010`
- `0x18009d94c`
- `0x18009da0c`
- `0x18009f7e8`
- `0x1800a9d20`
- `0x1801cb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009d208`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009d208`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009d248`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009d2f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009d374`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009d248`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009d2f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009d374`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009d201`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009d26d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009d201`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009d26d`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall NDXGIOn12::CDevice::SetDisplayMode(NDXGIOn12::CDevice *this, struct IDXGIResource *a2)
{
  unsigned __int64 v5; // r14
  int v6; // ebx
  __int64 v7; // rdi
  void (__fastcall *v8)(__int64, __int64); // rbx
  __int64 v9; // rax
  _QWORD *v10; // rbx
  __int64 (*v11)(void); // rax
  int v12; // r15d
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // [rsp+30h] [rbp-F8h] BYREF
  __int64 v19; // [rsp+38h] [rbp-F0h] BYREF
  int v20; // [rsp+40h] [rbp-E8h] BYREF
  __int64 v21; // [rsp+48h] [rbp-E0h] BYREF
  PSRWLOCK SRWLock; // [rsp+50h] [rbp-D8h]
  unsigned __int64 v23; // [rsp+58h] [rbp-D0h]
  DWORD CurrentThreadId; // [rsp+60h] [rbp-C8h]
  _OWORD *v25; // [rsp+68h] [rbp-C0h]
  unsigned __int64 v26; // [rsp+70h] [rbp-B8h]
  char *v27; // [rsp+78h] [rbp-B0h]
  _QWORD *v28; // [rsp+80h] [rbp-A8h]
  _BYTE v29[40]; // [rsp+90h] [rbp-98h] BYREF
  _OWORD v30[3]; // [rsp+B8h] [rbp-70h] BYREF
  __int64 v31; // [rsp+E8h] [rbp-40h] BYREF

  if ( !(*(unsigned int (__fastcall **)(NDXGIOn12::CDevice *))(*(_QWORD *)this + 328LL))(this) )
    return 2147500033LL;
  v5 = ((unsigned __int64)this + 32) & -(__int64)(this != (NDXGIOn12::CDevice *)16);
  v23 = v5;
  CLockOwnerChild<CDevice,0>::UCAddUse(v5);
  v26 = v5;
  v18 = 0;
  (***((void (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 259))(
    *((_QWORD *)this + 259),
    &GUID_36871736_2446_4858_8473_99bd44555307,
    &v18);
  v19 = 0;
  v6 = ((__int64 (__fastcall *)(struct IDXGIResource *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
         a2,
         &GUID_79d2046c_22ef_451b_9e74_2245d9c760ea,
         &v19);
  if ( v6 >= 0 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 152LL))(v18);
    v7 = v18;
    v8 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v18 + 160LL);
    v9 = (*(__int64 (__fastcall **)(struct IDXGIResourceVtbl *))a2[17].lpVtbl->QueryInterface)(a2[17].lpVtbl);
    v8(v7, v9);
    memset(v30, 0, sizeof(v30));
    v31 = 0;
    v21 = 44;
    v6 = (*(__int64 (__fastcall **)(__int64, char *, __int64 *))(*(_QWORD *)v19 + 32LL))(v19, (char *)v30 + 8, &v21);
    if ( v6 >= 0 )
    {
      v20 = 4;
      v6 = ((__int64 (__fastcall *)(struct IDXGIResource *, void *, int *, char *))a2->lpVtbl->GetPrivateData)(
             a2,
             &unk_1801FA990,
             &v20,
             (char *)&v31 + 4);
      if ( v6 >= 0 )
      {
        CDevCtxInterface::CDevCtxInterface(
          (CDevCtxInterface *)v29,
          *(struct CContext **)(*((_QWORD *)this + 7) + 1080LL),
          1,
          0,
          0);
        NDXGI::CDevice::AcquireResource(this, a2);
        if ( *((int *)this + 308) >= 0 )
        {
          SRWLock = (PSRWLOCK)((char *)this + 1400);
          v27 = (char *)this + 1400;
          AcquireSRWLockExclusive((PSRWLOCK)this + 175);
          CurrentThreadId = GetCurrentThreadId();
          v25 = v30;
          try
          {
            std::_Hash<std::_Umap_traits<unsigned long,NDXGI::CDevice::SSetDisplayModeCBThreadLocalData *,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,NDXGI::CDevice::SSetDisplayModeCBThreadLocalData *>>,0>>::emplace<std::pair<unsigned long,NDXGI::CDevice::SSetDisplayModeCBThreadLocalData *>>();
            v10 = v28;
            if ( this != (NDXGIOn12::CDevice *)-1400LL )
              ReleaseSRWLockExclusive((PSRWLOCK)this + 175);
            v11 = (__int64 (*)(void))*((_QWORD *)this + 263);
          }
          catch ( std::bad_alloc )
          {
            if ( SRWLock )
              ReleaseSRWLockExclusive(SRWLock);
            CDevCtxInterface::~CDevCtxInterface((CDevCtxInterface *)v29);
            v6 = -2147024882;
            v5 = v23;
            goto LABEL_33;
          }
          v12 = v11();
          AcquireSRWLockExclusive((PSRWLOCK)this + 175);
          v13 = std::_Conditionally_enabled_hash<unsigned long,1>::operator()(v10 + 2);
          v14 = 2 * (v13 & *((_QWORD *)this + 182));
          v15 = *((_QWORD *)this + 179);
          if ( *(_QWORD **)(v15 + 16 * (v13 & *((_QWORD *)this + 182)) + 8) == v10 )
          {
            if ( *(_QWORD **)(v15 + 16 * (v13 & *((_QWORD *)this + 182))) == v10 )
            {
              v16 = *((_QWORD *)this + 177);
              *(_QWORD *)(v15 + 8 * v14) = v16;
            }
            else
            {
              v16 = v10[1];
            }
            *(_QWORD *)(v15 + 8 * v14 + 8) = v16;
          }
          else if ( *(_QWORD **)(v15 + 16 * (v13 & *((_QWORD *)this + 182))) == v10 )
          {
            *(_QWORD *)(v15 + 16 * (v13 & *((_QWORD *)this + 182))) = *v10;
          }
          v17 = *v10;
          --*((_QWORD *)this + 178);
          *(_QWORD *)v10[1] = v17;
          *(_QWORD *)(v17 + 8) = v10[1];
          std::_Deallocate<16>(v10, 32);
          if ( this != (NDXGIOn12::CDevice *)-1400LL )
            ReleaseSRWLockExclusive((PSRWLOCK)this + 175);
          if ( v12 == -2147467259 || v12 == -2147024882 )
          {
            v6 = v30[0];
            goto LABEL_29;
          }
          if ( v12 != -2005530512 )
          {
            if ( v12 )
            {
              NDXGI::CDevice::DriverInternalError((NDXGIOn12::CDevice *)((char *)this - 16), v12);
              goto LABEL_25;
            }
            v6 = v30[0];
            if ( LODWORD(v30[0]) != -2005530512 )
              goto LABEL_29;
          }
          v6 = -2005270523;
          (*(void (__fastcall **)(NDXGIOn12::CDevice *, __int64))(*(_QWORD *)this + 264LL))(this, 2289696773LL);
          goto LABEL_29;
        }
LABEL_25:
        v6 = -2005270523;
LABEL_29:
        CDevCtxInterface::~CDevCtxInterface((CDevCtxInterface *)v29);
      }
    }
  }
LABEL_33:
  ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(&v19);
  ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(&v18);
  CLockOwnerChild<CDevice,0>::UCReleaseUse(v5);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18009d010  mov     [rsp+arg_10], rbx
0x18009d015  mov     [rsp+arg_18], rsi
0x18009d01a  push    rdi
0x18009d01b  push    r12
0x18009d01d  push    r13
0x18009d01f  push    r14
0x18009d021  push    r15
0x18009d023  sub     rsp, 100h
0x18009d02a  mov     rax, cs:__security_cookie
0x18009d031  xor     rax, rsp
0x18009d034  mov     [rsp+128h+var_38], rax
0x18009d03c  mov     r15, rdx
0x18009d03f  mov     rsi, rcx
0x18009d042  mov     rax, [rcx]
0x18009d045  mov     rax, [rax+148h]
0x18009d04c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d051  test    eax, eax
0x18009d053  jnz     short loc_18009D05F
0x18009d055  mov     eax, 80004001h
0x18009d05a  jmp     loc_18009D3B2
0x18009d05f  lea     r12, [rsi-10h]
0x18009d063  mov     rax, r12
0x18009d066  lea     rcx, [rsi+20h]
0x18009d06a  neg     rax
0x18009d06d  sbb     r14, r14
0x18009d070  and     r14, rcx
0x18009d073  mov     [rsp+128h+var_D0], r14
0x18009d078  mov     rcx, r14
0x18009d07b  call    ?UCAddUse@?$CLockOwnerChild@VCDevice@@$0A@@@QEAAKXZ; CLockOwnerChild<CDevice,0>::UCAddUse(void)
0x18009d080  mov     [rsp+128h+var_B8], r14
0x18009d085  mov     [rsp+128h+var_F8], 0
0x18009d08e  mov     rcx, [rsi+818h]
0x18009d095  mov     rax, [rcx]
0x18009d098  lea     r8, [rsp+128h+var_F8]
0x18009d09d  lea     rdx, _GUID_36871736_2446_4858_8473_99bd44555307
0x18009d0a4  mov     rax, [rax]
0x18009d0a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d0ac  mov     [rsp+128h+var_F0], 0
0x18009d0b5  mov     rax, [r15]
0x18009d0b8  lea     r8, [rsp+128h+var_F0]
0x18009d0bd  lea     rdx, _GUID_79d2046c_22ef_451b_9e74_2245d9c760ea
0x18009d0c4  mov     rcx, r15
0x18009d0c7  mov     rax, [rax]
0x18009d0ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d0cf  mov     ebx, eax
0x18009d0d1  test    eax, eax
0x18009d0d3  js      loc_18009D392
0x18009d0d9  mov     rcx, [rsp+128h+var_F8]
0x18009d0de  mov     rax, [rcx]
0x18009d0e1  mov     rax, [rax+98h]
0x18009d0e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d0ed  mov     rdi, [rsp+128h+var_F8]
0x18009d0f2  mov     rax, [rdi]
0x18009d0f5  mov     rbx, [rax+0A0h]
0x18009d0fc  mov     rdx, [r15+88h]
0x18009d103  mov     rcx, [rdx]
0x18009d106  mov     rax, [rcx]
0x18009d109  mov     rcx, rdx
0x18009d10c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d111  mov     rdx, rax
0x18009d114  mov     rcx, rdi
0x18009d117  mov     rax, rbx
0x18009d11a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d11f  mov     r13, rax
0x18009d122  xorps   xmm0, xmm0
0x18009d125  xor     eax, eax
0x18009d127  movups  [rsp+128h+var_70], xmm0
0x18009d12f  movups  [rsp+128h+var_60], xmm0
0x18009d137  movups  [rsp+128h+var_50], xmm0
0x18009d13f  mov     [rsp+128h+var_40], rax
0x18009d147  mov     [rsp+128h+var_E0], 2Ch ; ','
0x18009d150  mov     r9, [rsp+128h+var_F0]
0x18009d155  mov     rcx, [r9]
0x18009d158  mov     rax, [rcx+20h]
0x18009d15c  lea     r8, [rsp+128h+var_E0]
0x18009d161  lea     rdx, [rsp+128h+var_70+8]
0x18009d169  mov     rcx, r9
0x18009d16c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d171  mov     ebx, eax
0x18009d173  test    eax, eax
0x18009d175  js      loc_18009D392
0x18009d17b  mov     [rsp+128h+var_E8], 4
0x18009d183  mov     rax, [r15]
0x18009d186  lea     r9, [rsp+128h+var_40+4]
0x18009d18e  lea     r8, [rsp+128h+var_E8]
0x18009d193  lea     rdx, unk_1801FA990
0x18009d19a  mov     rcx, r15
0x18009d19d  mov     rax, [rax+28h]
0x18009d1a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d1a6  mov     ebx, eax
0x18009d1a8  test    eax, eax
0x18009d1aa  js      loc_18009D392
0x18009d1b0  mov     rdx, [rsi+38h]
0x18009d1b4  mov     [rsp+128h+var_108], 0; bool
0x18009d1b9  xor     r9d, r9d; bool
0x18009d1bc  mov     r8b, 1; bool
0x18009d1bf  mov     rdx, [rdx+438h]; struct CContext *
0x18009d1c6  lea     rcx, [rsp+128h+var_98]; this
0x18009d1ce  call    ??$?0VCContext@@@CDevCtxInterface@@QEAA@PEAVCContext@@_N11@Z; CDevCtxInterface::CDevCtxInterface(CContext *,bool,bool,bool)
0x18009d1d3  nop
0x18009d1d4  mov     rdx, r15; struct IDXGIResource *
0x18009d1d7  mov     rcx, rsi; this
0x18009d1da  call    ?AcquireResource@CDevice@NDXGI@@UEAAXPEAUIDXGIResource@@@Z; NDXGI::CDevice::AcquireResource(IDXGIResource *)
0x18009d1df  mov     eax, [rsi+4D0h]
0x18009d1e5  test    eax, eax
0x18009d1e7  js      loc_18009D323
0x18009d1ed  lea     rdi, [rsi+578h]
0x18009d1f4  mov     [rsp+128h+SRWLock], rdi
0x18009d1f9  mov     [rsp+128h+var_B0], rdi
0x18009d1fe  mov     rcx, rdi; SRWLock
0x18009d201  call    cs:__imp_AcquireSRWLockExclusive
0x18009d207  nop
0x18009d208  call    cs:__imp_GetCurrentThreadId
0x18009d20e  mov     [rsp+128h+var_C8], eax
0x18009d212  lea     rax, [rsp+128h+var_70]
0x18009d21a  mov     [rsp+128h+var_C0], rax
0x18009d21f  lea     rcx, [rsi+580h]
0x18009d226  lea     r8, [rsp+128h+var_C8]
0x18009d22b  lea     rdx, [rsp+128h+var_A8]
0x18009d233  call    ??$emplace@U?$pair@KPEAUSSetDisplayModeCBThreadLocalData@CDevice@NDXGI@@@std@@@?$_Hash@V?$_Umap_traits@KPEAUSSetDisplayModeCBThreadLocalData@CDevice@NDXGI@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@V?$allocator@U?$pair@$$CBKPEAUSSetDisplayModeCBThreadLocalData@CDevice@NDXGI@@@std@@@5@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKPEAUSSetDisplayModeCBThreadLocalData@CDevice@NDXGI@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@KPEAUSSetDisplayModeCBThreadLocalData@CDevice@NDXGI@@@1@@Z; std::_Hash<std::_Umap_traits<ulong,NDXGI::CDevice::SSetDisplayModeCBThreadLocalData *,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,NDXGI::CDevice::SSetDisplayModeCBThreadLocalData *>>,0>>::emplace<std::pair<ulong,NDXGI::CDevice::SSetDisplayModeCBThreadLocalData *>>(std::pair<ulong,NDXGI::CDevice::SSetDisplayModeCBThreadLocalData *> &&)
0x18009d238  mov     rbx, [rsp+128h+var_A8]
0x18009d240  test    rdi, rdi
0x18009d243  jz      short loc_18009D24E
0x18009d245  mov     rcx, rdi; SRWLock
0x18009d248  call    cs:__imp_ReleaseSRWLockExclusive
0x18009d24e  mov     r8, [rsi+80h]
0x18009d255  mov     rdx, r12
0x18009d258  mov     rcx, r13
0x18009d25b  mov     rax, [rsi+838h]
0x18009d262  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d267  mov     r15d, eax
0x18009d26a  mov     rcx, rdi; SRWLock
0x18009d26d  call    cs:__imp_AcquireSRWLockExclusive
0x18009d273  lea     rcx, [rbx+10h]
0x18009d277  call    ??R?$_Conditionally_enabled_hash@K$00@std@@SA_KAEBK@Z; std::_Conditionally_enabled_hash<ulong,1>::operator()(ulong const &)
0x18009d27c  mov     rcx, [rsi+5B0h]
0x18009d283  and     rcx, rax
0x18009d286  add     rcx, rcx
0x18009d289  mov     rdx, [rsi+598h]
0x18009d290  cmp     [rdx+rcx*8+8], rbx
0x18009d295  jnz     short loc_18009D2B5
0x18009d297  cmp     [rdx+rcx*8], rbx
0x18009d29b  jnz     short loc_18009D2AA
0x18009d29d  mov     rax, [rsi+588h]
0x18009d2a4  mov     [rdx+rcx*8], rax
0x18009d2a8  jmp     short loc_18009D2AE
0x18009d2aa  mov     rax, [rbx+8]
0x18009d2ae  mov     [rdx+rcx*8+8], rax
0x18009d2b3  jmp     short loc_18009D2C2
0x18009d2b5  cmp     [rdx+rcx*8], rbx
0x18009d2b9  jnz     short loc_18009D2C2
0x18009d2bb  mov     rax, [rbx]
0x18009d2be  mov     [rdx+rcx*8], rax
0x18009d2c2  mov     rcx, [rbx]
0x18009d2c5  dec     qword ptr [rsi+590h]
0x18009d2cc  mov     rax, [rbx+8]
0x18009d2d0  mov     [rax], rcx
0x18009d2d3  mov     rax, [rbx+8]
0x18009d2d7  mov     [rcx+8], rax
0x18009d2db  mov     edx, 20h ; ' '
0x18009d2e0  mov     rcx, rbx
0x18009d2e3  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18009d2e8  test    rdi, rdi
0x18009d2eb  jz      short loc_18009D2F6
0x18009d2ed  mov     rcx, rdi; SRWLock
0x18009d2f0  call    cs:__imp_ReleaseSRWLockExclusive
0x18009d2f6  mov     ecx, 80004005h
0x18009d2fb  cmp     r15d, ecx
0x18009d2fe  jz      short loc_18009D354
0x18009d300  cmp     r15d, 8007000Eh
0x18009d307  jz      short loc_18009D354
0x18009d309  mov     eax, 88760870h
0x18009d30e  cmp     r15d, eax
0x18009d311  jz      short loc_18009D339
0x18009d313  test    r15d, r15d
0x18009d316  jz      short loc_18009D32A
0x18009d318  mov     edx, r15d; int
0x18009d31b  mov     rcx, r12; this
0x18009d31e  call    ?DriverInternalError@CDevice@NDXGI@@QEAAXJ@Z; NDXGI::CDevice::DriverInternalError(long)
0x18009d323  mov     ebx, 887A0005h
0x18009d328  jmp     short loc_18009D35B
0x18009d32a  mov     ebx, dword ptr [rsp+128h+var_70]
0x18009d331  cmp     ebx, ecx
0x18009d333  jz      short loc_18009D35B
0x18009d335  cmp     ebx, eax
0x18009d337  jnz     short loc_18009D35B
0x18009d339  mov     ebx, 887A0005h
0x18009d33e  mov     rax, [rsi]
0x18009d341  mov     edx, ebx
0x18009d343  mov     rcx, rsi
0x18009d346  mov     rax, [rax+108h]
0x18009d34d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d352  jmp     short loc_18009D35B
0x18009d354  mov     ebx, dword ptr [rsp+128h+var_70]
0x18009d35b  lea     rcx, [rsp+128h+var_98]; this
0x18009d363  call    ??1CDevCtxInterface@@QEAA@XZ; CDevCtxInterface::~CDevCtxInterface(void)
0x18009d368  jmp     short loc_18009D392
0x18009d36a  mov     rcx, [rsp+128h+SRWLock]; SRWLock
0x18009d36f  test    rcx, rcx
0x18009d372  jz      short loc_18009D37B
0x18009d374  call    cs:__imp_ReleaseSRWLockExclusive
0x18009d37a  nop
0x18009d37b  lea     rcx, [rsp+128h+var_98]; this
0x18009d383  call    ??1CDevCtxInterface@@QEAA@XZ; CDevCtxInterface::~CDevCtxInterface(void)
0x18009d388  mov     ebx, 8007000Eh
0x18009d38d  mov     r14, [rsp+128h+var_D0]
0x18009d392  lea     rcx, [rsp+128h+var_F0]
0x18009d397  call    ??1?$CComPtrBase@UIDXGIFactory4@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(void)
0x18009d39c  nop
0x18009d39d  lea     rcx, [rsp+128h+var_F8]
0x18009d3a2  call    ??1?$CComPtrBase@UIDXGIFactory4@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(void)
0x18009d3a7  nop
0x18009d3a8  mov     rcx, r14
0x18009d3ab  call    ?UCReleaseUse@?$CLockOwnerChild@VCDevice@@$0A@@@QEAAKXZ; CLockOwnerChild<CDevice,0>::UCReleaseUse(void)
0x18009d3b0  mov     eax, ebx
0x18009d3b2  mov     rcx, [rsp+128h+var_38]
0x18009d3ba  xor     rcx, rsp; StackCookie
0x18009d3bd  call    __security_check_cookie
0x18009d3c2  lea     r11, [rsp+128h+var_28]
0x18009d3ca  mov     rbx, [r11+40h]
0x18009d3ce  mov     rsi, [r11+48h]
0x18009d3d2  mov     rsp, r11
0x18009d3d5  pop     r15
0x18009d3d7  pop     r14
0x18009d3d9  pop     r13
0x18009d3db  pop     r12
0x18009d3dd  pop     rdi
0x18009d3de  retn
```
