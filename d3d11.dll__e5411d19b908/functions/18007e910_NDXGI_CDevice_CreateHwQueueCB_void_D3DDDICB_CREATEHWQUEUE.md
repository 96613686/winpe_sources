# NDXGI::CDevice::CreateHwQueueCB(void *,_D3DDDICB_CREATEHWQUEUE *)

- ea: `0x18007e910`
- end: `0x18007ebd7`
- name: `?CreateHwQueueCB@CDevice@NDXGI@@KAJPEAXPEAU_D3DDDICB_CREATEHWQUEUE@@@Z`
- size: `711`
- prototype: `__int64 __fastcall(NDXGI::CDevice *this, struct _D3DDDICB_CREATEHWQUEUE *)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x18000bad0`
- `0x180022400`
- `0x180022630`
- `0x1800229a0`
- `0x180023028`
- `0x18007e910`
- `0x18007ebe0`
- `0x18007ec28`
- `0x18007eca0`
- `0x18007ed2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18007e99e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18007e99e`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18007e9cd`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18007ea45`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18007e9cd`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18007ea45`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007eb0c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007eb88`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007eba6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007eb0c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007eb88`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007eba6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007e985`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007e985`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18007eafd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18007eb77`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18007eb95`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18007eafd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18007eb77`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18007eb95`
- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTCreateHwQueue` at `0x18007ea10`

## string_xrefs

- `0x18007eb2d`: `Reserved flags given to CreateHwQueueCB`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall NDXGI::CDevice::CreateHwQueueCB(
        RTL_SRWLOCK *this,
        struct _D3DDDICB_CREATEHWQUEUE *a2,
        __int64 a3,
        __int64 a4)
{
  unsigned int v6; // ecx
  __int64 v7; // r13
  __int64 v8; // rdx
  int v9; // eax
  unsigned int v10; // r12d
  char *Ptr; // r15
  char *i; // rsi
  unsigned int **v13; // r15
  unsigned int **v14; // rsi
  unsigned int v16; // [rsp+20h] [rbp-B8h]
  RTL_SRWLOCK *v17; // [rsp+30h] [rbp-A8h]
  _com_error *v18; // [rsp+38h] [rbp-A0h] BYREF
  __int128 v19; // [rsp+40h] [rbp-98h] BYREF
  __int128 v20; // [rsp+50h] [rbp-88h]
  __int128 v21; // [rsp+60h] [rbp-78h]
  __int64 v22; // [rsp+70h] [rbp-68h] BYREF
  int v23; // [rsp+78h] [rbp-60h]
  RTL_SRWLOCK SRWLock; // [rsp+80h] [rbp-58h] BYREF
  _BYTE v25[80]; // [rsp+88h] [rbp-50h] BYREF
  __int64 v26; // [rsp+E0h] [rbp+8h] BYREF
  struct NDXGI::CHwQueue *v27; // [rsp+E8h] [rbp+10h] BYREF
  __int64 v28; // [rsp+F0h] [rbp+18h]
  PSRWLOCK v29; // [rsp+F8h] [rbp+20h]

  *((_QWORD *)a2 + 3) = 0;
  v6 = *((_DWORD *)a2 + 2);
  if ( v6 >= 0x80 )
  {
    CModule::RecordJournal((CModule *)&g_Module, -2147024809, "Reserved flags given to CreateHwQueueCB", a4, 1);
    return 2147942487LL;
  }
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v7 = *(_QWORD *)a2;
  v28 = v7;
  LODWORD(v19) = *(_DWORD *)(v7 + 8);
  DWORD1(v19) = v6;
  *(_QWORD *)&v20 = *((_QWORD *)a2 + 2);
  DWORD2(v19) = *((_DWORD *)a2 + 3);
  v17 = (RTL_SRWLOCK *)(v7 + 80);
  AcquireSRWLockExclusive((PSRWLOCK)(v7 + 80));
  v29 = this + 148;
  AcquireSRWLockShared(this + 148);
  v22 = 0;
  v23 = 0;
  InitializeSRWLock(&SRWLock);
  std::vector<CCommandList *>::vector<CCommandList *>(v25);
  try
  {
    std::list<NDXGI::CHwQueue>::push_back(v7 + 88, &v22);
    std::vector<NDXGI::CHwQueue::DeferredWaiter>::_Tidy(v25);
    v26 = *(_QWORD *)(*(_QWORD *)(v7 + 88) + 8LL);
    v9 = CallAndLogImpl<long (*)(_D3DKMT_CREATEHWQUEUE *),_D3DKMT_CREATEHWQUEUE *>(D3DKMTCreateHwQueue, v8, &v19);
    v10 = NDXGI::CDevice::NTStatusToHResult((NDXGI::CDevice *)this, v9);
    ThrowFailure(v10);
    v22 = v7;
    v23 = DWORD2(v20);
    InitializeSRWLock(&SRWLock);
    std::vector<CCommandList *>::vector<CCommandList *>(v25);
    NDXGI::CHwQueue::operator=(v26 + 16, &v22);
    std::vector<NDXGI::CHwQueue::DeferredWaiter>::_Tidy(v25);
    *((_QWORD *)a2 + 3) = v26 + 16;
    *((_DWORD *)a2 + 8) = HIDWORD(v20);
    *(_OWORD *)((char *)a2 + 40) = v21;
    *((_DWORD *)a2 + 2) = DWORD1(v19);
    v27 = (struct NDXGI::CHwQueue *)(v26 + 16);
    Ptr = (char *)this[151].Ptr;
    for ( i = (char *)this[150].Ptr; i != Ptr; i += 8 )
      NDXGI::CDevice::WaitForFenceImpl(
        (NDXGI::CDevice *)this,
        *(_DWORD *)(*(_QWORD *)i + 12LL),
        **(_QWORD **)(*(_QWORD *)i + 24LL),
        0,
        v16,
        &v27);
    v13 = (unsigned int **)this[154].Ptr;
    v14 = (unsigned int **)this[153].Ptr;
  }
  catch ( std::bad_alloc )
  {
    if ( v26 != *(_QWORD *)(v28 + 88) )
      std::list<NDXGI::CHwQueue>::erase(v28 + 88, &v26);
    if ( v29 )
      ReleaseSRWLockShared(v29);
    if ( v7 != -80 )
      ReleaseSRWLockExclusive(v17);
    return 2147942414LL;
  }
  catch ( _com_error *v18 )
  {
    if ( v26 != *(_QWORD *)(v28 + 88) )
      std::list<NDXGI::CHwQueue>::erase(v28 + 88, &v26);
    LODWORD(v26) = *((_DWORD *)v18 + 2);
    if ( v29 )
      ReleaseSRWLockShared(v29);
    if ( v7 != -80 )
      ReleaseSRWLockExclusive(v17);
    return (unsigned int)v26;
  }
  while ( v14 != v13 )
  {
    NDXGI::CDevice::WaitForFenceImpl(
      (NDXGI::CDevice *)this,
      **v14,
      *((_QWORD *)*v14 + 1),
      *((_BYTE *)*v14 + 20),
      v16,
      &v27);
    ++v14;
  }
  if ( this != (RTL_SRWLOCK *)-1184LL )
    ReleaseSRWLockShared(this + 148);
  if ( v7 != -80 )
    ReleaseSRWLockExclusive((PSRWLOCK)(v7 + 80));
  return v10;
}

```

## disassembly

```asm
0x18007e910  push    rbx
0x18007e912  push    rsi
0x18007e913  push    rdi
0x18007e914  push    r12
0x18007e916  push    r13
0x18007e918  push    r14
0x18007e91a  push    r15
0x18007e91c  sub     rsp, 0A0h
0x18007e923  mov     r15, rdx
0x18007e926  mov     r14, rcx
0x18007e929  mov     qword ptr [rdx+18h], 0
0x18007e931  mov     ecx, [rdx+8]
0x18007e934  cmp     ecx, 80h
0x18007e93a  jnb     loc_18007EB28
0x18007e940  xorps   xmm0, xmm0
0x18007e943  movups  [rsp+0D8h+var_98], xmm0
0x18007e948  movups  [rsp+0D8h+var_88], xmm0
0x18007e94d  movups  [rsp+0D8h+var_78], xmm0
0x18007e952  mov     r13, [rdx]
0x18007e955  mov     [rsp+0D8h+arg_10], r13
0x18007e95d  mov     eax, [r13+8]
0x18007e961  mov     dword ptr [rsp+0D8h+var_98], eax
0x18007e965  mov     dword ptr [rsp+0D8h+var_98+4], ecx
0x18007e969  mov     rax, [rdx+10h]
0x18007e96d  mov     qword ptr [rsp+0D8h+var_88], rax
0x18007e972  mov     eax, [rdx+0Ch]
0x18007e975  mov     dword ptr [rsp+0D8h+var_98+8], eax
0x18007e979  lea     rbx, [r13+50h]
0x18007e97d  mov     [rsp+0D8h+var_A8], rbx
0x18007e982  mov     rcx, rbx; SRWLock
0x18007e985  call    cs:__imp_AcquireSRWLockExclusive
0x18007e98b  nop
0x18007e98c  lea     rdi, [r14+4A0h]
0x18007e993  mov     [rsp+0D8h+arg_18], rdi
0x18007e99b  mov     rcx, rdi; SRWLock
0x18007e99e  call    cs:__imp_AcquireSRWLockShared
0x18007e9a4  nop
0x18007e9a5  lea     rsi, [r13+58h]
0x18007e9a9  mov     rax, [rsi]
0x18007e9ac  mov     [rsp+0D8h+arg_0], rax
0x18007e9b4  mov     [rsp+0D8h+var_68], 0
0x18007e9bd  mov     [rsp+0D8h+var_60], 0
0x18007e9c5  lea     rcx, [rsp+0D8h+SRWLock]; SRWLock
0x18007e9cd  call    cs:__imp_InitializeSRWLock
0x18007e9d3  lea     rcx, [rsp+0D8h+var_50]; void *
0x18007e9db  call    ??0?$vector@PEAVCCommandList@@V?$allocator@PEAVCCommandList@@@std@@@std@@QEAA@XZ; std::vector<CCommandList *>::vector<CCommandList *>(void)
0x18007e9e0  nop
0x18007e9e1  lea     rdx, [rsp+0D8h+var_68]
0x18007e9e6  mov     rcx, rsi
0x18007e9e9  call    ?push_back@?$list@VCHwQueue@NDXGI@@V?$allocator@VCHwQueue@NDXGI@@@std@@@std@@QEAAX$$QEAVCHwQueue@NDXGI@@@Z; std::list<NDXGI::CHwQueue>::push_back(NDXGI::CHwQueue &&)
0x18007e9ee  nop
0x18007e9ef  lea     rcx, [rsp+0D8h+var_50]
0x18007e9f7  call    ?_Tidy@?$vector@UDeferredWaiter@CHwQueue@NDXGI@@V?$allocator@UDeferredWaiter@CHwQueue@NDXGI@@@std@@@std@@AEAAXXZ; std::vector<NDXGI::CHwQueue::DeferredWaiter>::_Tidy(void)
0x18007e9fc  mov     rax, [rsi]
0x18007e9ff  mov     rsi, [rax+8]
0x18007ea03  mov     [rsp+0D8h+arg_0], rsi
0x18007ea0b  lea     r8, [rsp+0D8h+var_98]
0x18007ea10  mov     rcx, cs:__imp_D3DKMTCreateHwQueue
0x18007ea17  call    ??$CallAndLogImpl@P6AJPEAU_D3DKMT_CREATEHWQUEUE@@@ZPEAU1@@@YAJP6AJPEAU_D3DKMT_CREATEHWQUEUE@@@ZPEBD0@Z; CallAndLogImpl<long (*)(_D3DKMT_CREATEHWQUEUE *),_D3DKMT_CREATEHWQUEUE *>(long (*)(_D3DKMT_CREATEHWQUEUE *),char const *,_D3DKMT_CREATEHWQUEUE *)
0x18007ea1c  mov     edx, eax; int
0x18007ea1e  mov     rcx, r14; this
0x18007ea21  call    ?NTStatusToHResult@CDevice@NDXGI@@QEAAJJ@Z; NDXGI::CDevice::NTStatusToHResult(long)
0x18007ea26  mov     r12d, eax
0x18007ea29  mov     ecx, eax; int
0x18007ea2b  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18007ea30  mov     [rsp+0D8h+var_68], r13
0x18007ea35  mov     ecx, dword ptr [rsp+0D8h+var_88+8]
0x18007ea39  mov     [rsp+0D8h+var_60], ecx
0x18007ea3d  lea     rcx, [rsp+0D8h+SRWLock]; SRWLock
0x18007ea45  call    cs:__imp_InitializeSRWLock
0x18007ea4b  lea     rcx, [rsp+0D8h+var_50]; void *
0x18007ea53  call    ??0?$vector@PEAVCCommandList@@V?$allocator@PEAVCCommandList@@@std@@@std@@QEAA@XZ; std::vector<CCommandList *>::vector<CCommandList *>(void)
0x18007ea58  add     rsi, 10h
0x18007ea5c  lea     rdx, [rsp+0D8h+var_68]
0x18007ea61  mov     rcx, rsi
0x18007ea64  call    ??4CHwQueue@NDXGI@@QEAAAEAV01@$$QEAV01@@Z; NDXGI::CHwQueue::operator=(NDXGI::CHwQueue &&)
0x18007ea69  lea     rcx, [rsp+0D8h+var_50]
0x18007ea71  call    ?_Tidy@?$vector@UDeferredWaiter@CHwQueue@NDXGI@@V?$allocator@UDeferredWaiter@CHwQueue@NDXGI@@@std@@@std@@AEAAXXZ; std::vector<NDXGI::CHwQueue::DeferredWaiter>::_Tidy(void)
0x18007ea76  mov     [r15+18h], rsi
0x18007ea7a  mov     eax, dword ptr [rsp+0D8h+var_88+0Ch]
0x18007ea7e  mov     [r15+20h], eax
0x18007ea82  mov     rax, qword ptr [rsp+0D8h+var_78]
0x18007ea87  mov     [r15+28h], rax
0x18007ea8b  mov     rax, qword ptr [rsp+0D8h+var_78+8]
0x18007ea90  mov     [r15+30h], rax
0x18007ea94  mov     eax, dword ptr [rsp+0D8h+var_98+4]
0x18007ea98  mov     [r15+8], eax
0x18007ea9c  mov     [rsp+0D8h+arg_8], rsi
0x18007eaa4  mov     r15, [r14+4B8h]
0x18007eaab  mov     rsi, [r14+4B0h]
0x18007eab2  jmp     short loc_18007EADD
0x18007eab4  mov     rdx, [rsi]
0x18007eab7  mov     r8, [rdx+18h]
0x18007eabb  lea     rax, [rsp+0D8h+arg_8]
0x18007eac3  mov     [rsp+0D8h+var_B0], rax; struct NDXGI::CHwQueue **
0x18007eac8  xor     r9d, r9d; bool
0x18007eacb  mov     r8, [r8]; unsigned __int64
0x18007eace  mov     edx, [rdx+0Ch]; unsigned int
0x18007ead1  mov     rcx, r14; this
0x18007ead4  call    ?WaitForFenceImpl@CDevice@NDXGI@@QEAAJI_K_NIPEBQEAVCHwQueue@2@@Z; NDXGI::CDevice::WaitForFenceImpl(uint,unsigned __int64,bool,uint,NDXGI::CHwQueue * const *)
0x18007ead9  add     rsi, 8
0x18007eadd  cmp     rsi, r15
0x18007eae0  jnz     short loc_18007EAB4
0x18007eae2  mov     r15, [r14+4D0h]
0x18007eae9  mov     rsi, [r14+4C8h]
0x18007eaf0  cmp     rsi, r15
0x18007eaf3  jnz     short loc_18007EB4C
0x18007eaf5  test    rdi, rdi
0x18007eaf8  jz      short loc_18007EB04
0x18007eafa  mov     rcx, rdi; SRWLock
0x18007eafd  call    cs:__imp_ReleaseSRWLockShared
0x18007eb03  nop
0x18007eb04  test    rbx, rbx
0x18007eb07  jz      short loc_18007EB12
0x18007eb09  mov     rcx, rbx; SRWLock
0x18007eb0c  call    cs:__imp_ReleaseSRWLockExclusive
0x18007eb12  mov     eax, r12d
0x18007eb15  add     rsp, 0A0h
0x18007eb1c  pop     r15
0x18007eb1e  pop     r14
0x18007eb20  pop     r13
0x18007eb22  pop     r12
0x18007eb24  pop     rdi
0x18007eb25  pop     rsi
0x18007eb26  pop     rbx
0x18007eb27  retn
0x18007eb28  mov     [rsp+0D8h+var_B8], 1; bool
0x18007eb2d  lea     r8, aReservedFlagsG_8; "Reserved flags given to CreateHwQueueCB"
0x18007eb34  mov     edx, 80070057h; unsigned int
0x18007eb39  lea     rcx, ?g_Module@@3VCModule@@A; this
0x18007eb40  call    ?RecordJournal@CModule@@QEAAXIPEBD_N1@Z; CModule::RecordJournal(uint,char const *,bool,bool)
0x18007eb45  mov     eax, 80070057h
0x18007eb4a  jmp     short loc_18007EB15
0x18007eb4c  mov     rdx, [rsi]
0x18007eb4f  lea     rax, [rsp+0D8h+arg_8]
0x18007eb57  mov     [rsp+0D8h+var_B0], rax; struct NDXGI::CHwQueue **
0x18007eb5c  mov     r9b, [rdx+14h]; bool
0x18007eb60  mov     r8, [rdx+8]; unsigned __int64
0x18007eb64  mov     edx, [rdx]; unsigned int
0x18007eb66  mov     rcx, r14; this
0x18007eb69  call    ?WaitForFenceImpl@CDevice@NDXGI@@QEAAJI_K_NIPEBQEAVCHwQueue@2@@Z; NDXGI::CDevice::WaitForFenceImpl(uint,unsigned __int64,bool,uint,NDXGI::CHwQueue * const *)
0x18007eb6e  add     rsi, 8
0x18007eb72  jmp     loc_18007EAF0
0x18007eb77  call    cs:__imp_ReleaseSRWLockShared
0x18007eb7d  nop
0x18007eb7e  mov     rcx, [rsp+0D8h+var_A8]; SRWLock
0x18007eb83  test    rcx, rcx
0x18007eb86  jz      short loc_18007EB8E
0x18007eb88  call    cs:__imp_ReleaseSRWLockExclusive
0x18007eb8e  mov     eax, 8007000Eh
0x18007eb93  jmp     short loc_18007EB15
0x18007eb95  call    cs:__imp_ReleaseSRWLockShared
0x18007eb9b  nop
0x18007eb9c  mov     rcx, [rsp+0D8h+var_A8]; SRWLock
0x18007eba1  test    rcx, rcx
0x18007eba4  jz      short loc_18007EBAC
0x18007eba6  call    cs:__imp_ReleaseSRWLockExclusive
0x18007ebac  mov     eax, dword ptr [rsp+0D8h+arg_0]
0x18007ebb3  jmp     loc_18007EB15
0x18007ebb8  mov     rcx, [rsp+0D8h+arg_18]; SRWLock
0x18007ebc0  test    rcx, rcx
0x18007ebc3  jz      short loc_18007EB7E
0x18007ebc5  jmp     short loc_18007EB77
0x18007ebc7  mov     rcx, [rsp+0D8h+arg_18]; SRWLock
0x18007ebcf  test    rcx, rcx
0x18007ebd2  jz      short loc_18007EB9C
0x18007ebd4  jmp     short loc_18007EB95
```
