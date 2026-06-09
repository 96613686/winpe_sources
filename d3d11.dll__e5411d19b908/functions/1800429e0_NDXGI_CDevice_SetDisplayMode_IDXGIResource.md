# NDXGI::CDevice::SetDisplayMode(IDXGIResource *)

- ea: `0x1800429e0`
- end: `0x180042dc7`
- name: `?SetDisplayMode@CDevice@NDXGI@@UEAAJPEAUIDXGIResource@@@Z`
- size: `999`
- prototype: `__int64 __fastcall(NDXGI::CDevice *__hidden this, struct IDXGIResource *)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180009660`
- `0x18001e2a0`
- `0x18002bd20`
- `0x18002d0f0`
- `0x18002e160`
- `0x180034550`
- `0x1800429e0`
- `0x180042dd0`
- `0x180043d64`
- `0x18009f7e8`
- `0x1800a9d20`
- `0x1801cb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180042cc3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180042cc3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180042bf2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180042d03`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180042d5a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180042bf2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180042d03`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180042d5a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180042bd8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180042cbc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180042bd8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180042cbc`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall NDXGI::CDevice::SetDisplayMode(RTL_SRWLOCK *this, struct IDXGIResource *a2)
{
  RTL_SRWLOCK *v4; // rbx
  unsigned __int64 v5; // r13
  int v6; // ebx
  RTL_SRWLOCK *v7; // r14
  __int64 v8; // rbx
  int v9; // r12d
  DWORD CurrentThreadId; // eax
  _QWORD *v12; // [rsp+30h] [rbp-118h] BYREF
  int v13; // [rsp+38h] [rbp-110h] BYREF
  __int64 v14; // [rsp+40h] [rbp-108h] BYREF
  __int64 v15; // [rsp+48h] [rbp-100h] BYREF
  NDXGI::CDevice *v16; // [rsp+50h] [rbp-F8h]
  PSRWLOCK SRWLock; // [rsp+58h] [rbp-F0h]
  unsigned __int64 v18; // [rsp+60h] [rbp-E8h]
  DWORD v19; // [rsp+68h] [rbp-E0h] BYREF
  _OWORD *v20; // [rsp+70h] [rbp-D8h]
  unsigned __int64 v21; // [rsp+78h] [rbp-D0h]
  RTL_SRWLOCK *v22; // [rsp+80h] [rbp-C8h]
  __int64 v23; // [rsp+88h] [rbp-C0h] BYREF
  _BYTE v24[40]; // [rsp+98h] [rbp-B0h] BYREF
  PVOID Ptr; // [rsp+C0h] [rbp-88h] BYREF
  __int64 v26; // [rsp+C8h] [rbp-80h]
  __int64 v27; // [rsp+D0h] [rbp-78h]
  _OWORD v28[3]; // [rsp+D8h] [rbp-70h] BYREF
  __int64 v29; // [rsp+108h] [rbp-40h] BYREF

  v4 = this - 2;
  v16 = (NDXGI::CDevice *)&this[-2];
  v5 = (unsigned __int64)&this[4] & -(__int64)(this != (RTL_SRWLOCK *)16);
  v18 = v5;
  CLockOwnerChild<CDevice,0>::UCAddUse(v5);
  v21 = v5;
  v27 = 0;
  Ptr = v4[84].Ptr;
  v26 = 0;
  v12 = 0;
  v6 = ((__int64 (__fastcall *)(struct IDXGIResource *, GUID *, _QWORD **))a2->lpVtbl->QueryInterface)(
         a2,
         &GUID_79d2046c_22ef_451b_9e74_2245d9c760ea,
         &v12);
  if ( v6 < 0 )
  {
    if ( v12 )
      (*(void (__fastcall **)(_QWORD *))(*v12 + 16LL))(v12);
  }
  else
  {
    memset(v28, 0, sizeof(v28));
    v29 = 0;
    v15 = 44;
    v6 = (*(__int64 (__fastcall **)(_QWORD *, char *, __int64 *))(*v12 + 32LL))(v12, (char *)v28 + 8, &v15);
    if ( v6 < 0
      || (v13 = 4,
          v6 = ((__int64 (__fastcall *)(struct IDXGIResource *, __int64 *, int *, char *))a2->lpVtbl->GetPrivateData)(
                 a2,
                 qword_1801F4900,
                 &v13,
                 (char *)&v29 + 4),
          v6 < 0) )
    {
      ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(&v12);
      goto LABEL_17;
    }
    v14 = 0;
    v6 = (*(__int64 (__fastcall **)(_QWORD *, __int64 *))(*v12 + 24LL))(v12, &v14);
    if ( v6 >= 0 )
    {
      v26 = v14;
      CDevCtxInterface::CDevCtxInterface((CDevCtxInterface *)v24, *((struct CContext **)this[7].Ptr + 135), 1, 0, 0);
      NDXGI::CDevice::AcquireResource((NDXGI::CDevice *)this, a2);
      if ( SLODWORD(this[154].Ptr) < 0 )
        goto LABEL_35;
      v7 = this + 175;
      SRWLock = this + 175;
      if ( BYTE2(this[110].Ptr) )
      {
        v8 = 0;
        this[184].Ptr = v28;
LABEL_8:
        v9 = ((__int64 (__fastcall *)(PVOID *))this[85].Ptr)(&Ptr);
        if ( BYTE2(this[110].Ptr) )
        {
          this[184].Ptr = 0;
        }
        else
        {
          AcquireSRWLockExclusive(v7);
          std::_Hash<std::_Umap_traits<unsigned long,NDXGI::CDevice::SSetDisplayModeCBThreadLocalData *,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,NDXGI::CDevice::SSetDisplayModeCBThreadLocalData *>>,0>>::_Unchecked_erase(
            &this[176],
            v8);
          if ( v7 )
            ReleaseSRWLockExclusive(v7);
        }
        switch ( v9 )
        {
          case -2147467259:
          case -2147024882:
            v6 = v28[0];
            goto LABEL_15;
          case -2005530512:
LABEL_14:
            v6 = -2005270523;
            (*((void (__fastcall **)(RTL_SRWLOCK *, __int64))this->Ptr + 33))(this, 2289696773LL);
            goto LABEL_15;
          case 0:
            v6 = v28[0];
            if ( LODWORD(v28[0]) == -2005530512 )
              goto LABEL_14;
LABEL_15:
            CDevCtxInterface::~CDevCtxInterface((CDevCtxInterface *)v24);
            if ( v12 )
              (*(void (__fastcall **)(_QWORD *))(*v12 + 16LL))(v12);
            goto LABEL_17;
        }
        NDXGI::CDevice::DriverInternalError(v16, v9);
LABEL_35:
        v6 = -2005270523;
        goto LABEL_15;
      }
      v22 = this + 175;
      AcquireSRWLockExclusive(this + 175);
      CurrentThreadId = GetCurrentThreadId();
      try
      {
        v19 = CurrentThreadId;
        v20 = v28;
        std::_Hash<std::_Umap_traits<unsigned long,NDXGI::CDevice::SSetDisplayModeCBThreadLocalData *,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,NDXGI::CDevice::SSetDisplayModeCBThreadLocalData *>>,0>>::emplace<std::pair<unsigned long,NDXGI::CDevice::SSetDisplayModeCBThreadLocalData *>>(
          &this[176],
          &v23,
          &v19);
      }
      catch ( std::bad_alloc )
      {
        if ( SRWLock )
          ReleaseSRWLockExclusive(SRWLock);
        CDevCtxInterface::~CDevCtxInterface((CDevCtxInterface *)v24);
        ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(&v12);
        v6 = -2147024882;
        v5 = v18;
        goto LABEL_17;
      }
      v8 = v23;
      if ( this == (RTL_SRWLOCK *)-1400LL )
        v7 = 0;
      else
        ReleaseSRWLockExclusive(this + 175);
      goto LABEL_8;
    }
    if ( v12 )
      (*(void (__fastcall **)(_QWORD *, _QWORD))(*v12 + 16LL))(v12, *v12);
  }
LABEL_17:
  CLockOwnerChild<CDevice,0>::UCReleaseUse(v5);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800429e0  mov     [rsp+arg_10], rbx
0x1800429e5  mov     [rsp+arg_18], rsi
0x1800429ea  push    rdi
0x1800429eb  push    r12
0x1800429ed  push    r13
0x1800429ef  push    r14
0x1800429f1  push    r15
0x1800429f3  sub     rsp, 120h
0x1800429fa  mov     rax, cs:__security_cookie
0x180042a01  xor     rax, rsp
0x180042a04  mov     [rsp+148h+var_38], rax
0x180042a0c  mov     r14, rdx
0x180042a0f  mov     rsi, rcx
0x180042a12  lea     rbx, [rcx-10h]
0x180042a16  mov     [rsp+148h+var_F8], rbx
0x180042a1b  mov     rax, rbx
0x180042a1e  add     rcx, 20h ; ' '
0x180042a22  neg     rax
0x180042a25  sbb     r13, r13
0x180042a28  and     r13, rcx
0x180042a2b  mov     [rsp+148h+var_E8], r13
0x180042a30  mov     rcx, r13
0x180042a33  call    ?UCAddUse@?$CLockOwnerChild@VCDevice@@$0A@@@QEAAKXZ; CLockOwnerChild<CDevice,0>::UCAddUse(void)
0x180042a38  mov     [rsp+148h+var_D0], r13
0x180042a3d  xor     edi, edi
0x180042a3f  mov     [rsp+148h+var_78], rdi
0x180042a47  mov     rax, [rbx+2A0h]
0x180042a4e  mov     [rsp+148h+var_88], rax
0x180042a56  mov     [rsp+148h+var_80], rdi
0x180042a5e  mov     [rsp+148h+var_118], rdi
0x180042a63  mov     rax, [r14]
0x180042a66  lea     r8, [rsp+148h+var_118]
0x180042a6b  lea     rdx, _GUID_79d2046c_22ef_451b_9e74_2245d9c760ea
0x180042a72  mov     rcx, r14
0x180042a75  mov     rax, [rax]
0x180042a78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042a7d  mov     ebx, eax
0x180042a7f  test    eax, eax
0x180042a81  js      loc_180042D36
0x180042a87  xorps   xmm0, xmm0
0x180042a8a  xor     eax, eax
0x180042a8c  movups  [rsp+148h+var_70], xmm0
0x180042a94  movups  [rsp+148h+var_60], xmm0
0x180042a9c  movups  [rsp+148h+var_50], xmm0
0x180042aa4  mov     [rsp+148h+var_40], rax
0x180042aac  mov     [rsp+148h+var_100], 2Ch ; ','
0x180042ab5  mov     rcx, [rsp+148h+var_118]
0x180042aba  mov     rax, [rcx]
0x180042abd  lea     r8, [rsp+148h+var_100]
0x180042ac2  lea     rdx, [rsp+148h+var_70+8]
0x180042aca  mov     rax, [rax+20h]
0x180042ace  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042ad3  mov     ebx, eax
0x180042ad5  test    eax, eax
0x180042ad7  js      loc_180042D88
0x180042add  mov     [rsp+148h+var_110], 4
0x180042ae5  mov     rax, [r14]
0x180042ae8  lea     r9, [rsp+148h+var_40+4]
0x180042af0  lea     r8, [rsp+148h+var_110]
0x180042af5  lea     rdx, qword_1801F4900
0x180042afc  mov     rcx, r14
0x180042aff  mov     rax, [rax+28h]
0x180042b03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042b08  mov     ebx, eax
0x180042b0a  test    eax, eax
0x180042b0c  js      loc_180042D88
0x180042b12  mov     [rsp+148h+var_108], rdi
0x180042b17  mov     rcx, [rsp+148h+var_118]
0x180042b1c  mov     rax, [rcx]
0x180042b1f  lea     rdx, [rsp+148h+var_108]
0x180042b24  mov     rax, [rax+18h]
0x180042b28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042b2d  mov     ebx, eax
0x180042b2f  test    eax, eax
0x180042b31  js      loc_180042D0E
0x180042b37  mov     rax, [rsp+148h+var_108]
0x180042b3c  mov     [rsp+148h+var_80], rax
0x180042b44  mov     rdx, [rsi+38h]
0x180042b48  mov     [rsp+148h+var_128], dil; bool
0x180042b4d  xor     r9d, r9d; bool
0x180042b50  mov     r8b, 1; bool
0x180042b53  mov     rdx, [rdx+438h]; struct CContext *
0x180042b5a  lea     rcx, [rsp+148h+var_B0]; this
0x180042b62  call    ??$?0VCContext@@@CDevCtxInterface@@QEAA@PEAVCContext@@_N11@Z; CDevCtxInterface::CDevCtxInterface(CContext *,bool,bool,bool)
0x180042b67  nop
0x180042b68  mov     rdx, r14; struct IDXGIResource *
0x180042b6b  mov     rcx, rsi; this
0x180042b6e  call    ?AcquireResource@CDevice@NDXGI@@UEAAXPEAUIDXGIResource@@@Z; NDXGI::CDevice::AcquireResource(IDXGIResource *)
0x180042b73  mov     eax, [rsi+4D0h]
0x180042b79  test    eax, eax
0x180042b7b  js      loc_180042DA4
0x180042b81  lea     r14, [rsi+578h]
0x180042b88  mov     [rsp+148h+SRWLock], r14
0x180042b8d  cmp     [rsi+372h], dil
0x180042b94  jz      loc_180042CB1
0x180042b9a  mov     ebx, edi
0x180042b9c  lea     rax, [rsp+148h+var_70]
0x180042ba4  mov     [rsi+5C0h], rax
0x180042bab  mov     r15d, 580h
0x180042bb1  lea     rcx, [rsp+148h+var_88]
0x180042bb9  mov     rax, [rsi+2A8h]
0x180042bc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042bc5  mov     r12d, eax
0x180042bc8  cmp     [rsi+372h], dil
0x180042bcf  jnz     loc_180042D2A
0x180042bd5  mov     rcx, r14; SRWLock
0x180042bd8  call    cs:__imp_AcquireSRWLockExclusive
0x180042bde  lea     rcx, [r15+rsi]
0x180042be2  mov     rdx, rbx
0x180042be5  call    ?_Unchecked_erase@?$_Hash@V?$_Umap_traits@KPEAUSSetDisplayModeCBThreadLocalData@CDevice@NDXGI@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@V?$allocator@U?$pair@$$CBKPEAUSSetDisplayModeCBThreadLocalData@CDevice@NDXGI@@@std@@@5@$0A@@std@@@std@@AEAAPEAU?$_List_node@U?$pair@$$CBKPEAUSSetDisplayModeCBThreadLocalData@CDevice@NDXGI@@@std@@PEAX@2@PEAU32@@Z; std::_Hash<std::_Umap_traits<ulong,NDXGI::CDevice::SSetDisplayModeCBThreadLocalData *,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,NDXGI::CDevice::SSetDisplayModeCBThreadLocalData *>>,0>>::_Unchecked_erase(std::_List_node<std::pair<ulong const,NDXGI::CDevice::SSetDisplayModeCBThreadLocalData *>,void *> *)
0x180042bea  test    r14, r14
0x180042bed  jz      short loc_180042BF8
0x180042bef  mov     rcx, r14; SRWLock
0x180042bf2  call    cs:__imp_ReleaseSRWLockExclusive
0x180042bf8  mov     ecx, 80004005h
0x180042bfd  cmp     r12d, ecx
0x180042c00  jz      loc_180042DAE
0x180042c06  cmp     r12d, 8007000Eh
0x180042c0d  jz      loc_180042DAE
0x180042c13  mov     eax, 88760870h
0x180042c18  cmp     r12d, eax
0x180042c1b  jnz     short loc_180042C93
0x180042c1d  mov     ebx, 887A0005h
0x180042c22  mov     rax, [rsi]
0x180042c25  mov     edx, ebx
0x180042c27  mov     rcx, rsi
0x180042c2a  mov     rax, [rax+108h]
0x180042c31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042c36  nop
0x180042c37  lea     rcx, [rsp+148h+var_B0]; this
0x180042c3f  call    ??1CDevCtxInterface@@QEAA@XZ; CDevCtxInterface::~CDevCtxInterface(void)
0x180042c44  nop
0x180042c45  mov     rcx, [rsp+148h+var_118]
0x180042c4a  test    rcx, rcx
0x180042c4d  jz      short loc_180042C5C
0x180042c4f  mov     rax, [rcx]
0x180042c52  mov     rax, [rax+10h]
0x180042c56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042c5b  nop
0x180042c5c  mov     rcx, r13
0x180042c5f  call    ?UCReleaseUse@?$CLockOwnerChild@VCDevice@@$0A@@@QEAAKXZ; CLockOwnerChild<CDevice,0>::UCReleaseUse(void)
0x180042c64  mov     eax, ebx
0x180042c66  mov     rcx, [rsp+148h+var_38]
0x180042c6e  xor     rcx, rsp; StackCookie
0x180042c71  call    __security_check_cookie
0x180042c76  lea     r11, [rsp+148h+var_28]
0x180042c7e  mov     rbx, [r11+40h]
0x180042c82  mov     rsi, [r11+48h]
0x180042c86  mov     rsp, r11
0x180042c89  pop     r15
0x180042c8b  pop     r14
0x180042c8d  pop     r13
0x180042c8f  pop     r12
0x180042c91  pop     rdi
0x180042c92  retn
0x180042c93  test    r12d, r12d
0x180042c96  jnz     loc_180042D97
0x180042c9c  mov     ebx, dword ptr [rsp+148h+var_70]
0x180042ca3  cmp     ebx, ecx
0x180042ca5  jz      short loc_180042C37
0x180042ca7  cmp     ebx, eax
0x180042ca9  jz      loc_180042C1D
0x180042caf  jmp     short loc_180042C37
0x180042cb1  mov     [rsp+148h+var_C8], r14
0x180042cb9  mov     rcx, r14; SRWLock
0x180042cbc  call    cs:__imp_AcquireSRWLockExclusive
0x180042cc2  nop
0x180042cc3  call    cs:__imp_GetCurrentThreadId
0x180042cc9  mov     [rsp+148h+var_E0], eax
0x180042ccd  lea     rax, [rsp+148h+var_70]
0x180042cd5  mov     [rsp+148h+var_D8], rax
0x180042cda  lea     rcx, [rsi+580h]
0x180042ce1  lea     r8, [rsp+148h+var_E0]
0x180042ce6  lea     rdx, [rsp+148h+var_C0]
0x180042cee  call    ??$emplace@U?$pair@KPEAUSSetDisplayModeCBThreadLocalData@CDevice@NDXGI@@@std@@@?$_Hash@V?$_Umap_traits@KPEAUSSetDisplayModeCBThreadLocalData@CDevice@NDXGI@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@V?$allocator@U?$pair@$$CBKPEAUSSetDisplayModeCBThreadLocalData@CDevice@NDXGI@@@std@@@5@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKPEAUSSetDisplayModeCBThreadLocalData@CDevice@NDXGI@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@KPEAUSSetDisplayModeCBThreadLocalData@CDevice@NDXGI@@@1@@Z; std::_Hash<std::_Umap_traits<ulong,NDXGI::CDevice::SSetDisplayModeCBThreadLocalData *,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,NDXGI::CDevice::SSetDisplayModeCBThreadLocalData *>>,0>>::emplace<std::pair<ulong,NDXGI::CDevice::SSetDisplayModeCBThreadLocalData *>>(std::pair<ulong,NDXGI::CDevice::SSetDisplayModeCBThreadLocalData *> &&)
0x180042cf3  mov     rbx, [rsp+148h+var_C0]
0x180042cfb  test    r14, r14
0x180042cfe  jz      short loc_180042D52
0x180042d00  mov     rcx, r14; SRWLock
0x180042d03  call    cs:__imp_ReleaseSRWLockExclusive
0x180042d09  jmp     loc_180042BAB
0x180042d0e  mov     rcx, [rsp+148h+var_118]
0x180042d13  test    rcx, rcx
0x180042d16  jz      short loc_180042D25
0x180042d18  mov     rdx, [rcx]
0x180042d1b  mov     rax, [rdx+10h]
0x180042d1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042d24  nop
0x180042d25  jmp     loc_180042C5C
0x180042d2a  mov     [rsi+5C0h], rdi
0x180042d31  jmp     loc_180042BF8
0x180042d36  mov     rcx, [rsp+148h+var_118]
0x180042d3b  test    rcx, rcx
0x180042d3e  jz      short loc_180042D4D
0x180042d40  mov     rdx, [rcx]
0x180042d43  mov     rax, [rdx+10h]
0x180042d47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042d4c  nop
0x180042d4d  jmp     loc_180042C5C
0x180042d52  mov     r14, rdi
0x180042d55  jmp     loc_180042BAB
0x180042d5a  call    cs:__imp_ReleaseSRWLockExclusive
0x180042d60  nop
0x180042d61  lea     rcx, [rsp+148h+var_B0]; this
0x180042d69  call    ??1CDevCtxInterface@@QEAA@XZ; CDevCtxInterface::~CDevCtxInterface(void)
0x180042d6e  nop
0x180042d6f  lea     rcx, [rsp+148h+var_118]
0x180042d74  call    ??1?$CComPtrBase@UIDXGIFactory4@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(void)
0x180042d79  mov     ebx, 8007000Eh
0x180042d7e  mov     r13, [rsp+148h+var_E8]
0x180042d83  jmp     loc_180042C5C
0x180042d88  lea     rcx, [rsp+148h+var_118]
0x180042d8d  call    ??1?$CComPtrBase@UIDXGIFactory4@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(void)
0x180042d92  jmp     loc_180042C5C
0x180042d97  mov     edx, r12d; int
0x180042d9a  mov     rcx, [rsp+148h+var_F8]; this
0x180042d9f  call    ?DriverInternalError@CDevice@NDXGI@@QEAAXJ@Z; NDXGI::CDevice::DriverInternalError(long)
0x180042da4  mov     ebx, 887A0005h
0x180042da9  jmp     loc_180042C37
0x180042dae  mov     ebx, dword ptr [rsp+148h+var_70]
0x180042db5  jmp     loc_180042C37
0x180042dba  mov     rcx, [rsp+148h+SRWLock]; SRWLock
0x180042dbf  test    rcx, rcx
0x180042dc2  jz      short loc_180042D61
0x180042dc4  jmp     short loc_180042D5A
```
