# CStorage::Destroy(uint)

- ea: `0x180056e88`
- end: `0x18005712b`
- name: `?Destroy@CStorage@@QEAAXI@Z`
- size: `675`
- prototype: `void __fastcall(CStorage *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18004257c`

## callees

- `0x1800199b4`
- `0x180019c5c`
- `0x18001e260`
- `0x180022c94`
- `0x180054bdc`
- `0x180054c6c`
- `0x180056e88`
- `0x18009e50c`
- `0x1800a1c5c`
- `0x1800a1ea4`
- `0x1800c109c`
- `0x1800c1220`
- `0x1800f8314`
- `0x1800f8320`
- `0x180108e50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180056ea0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180056ea0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180057076`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180057076`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18005705e`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18005705e`

## string_xrefs

- `0x180056eba`: `_coreThread.IsCurrentThread()`
- `0x180056f14`: `CMemCachedPieces::LogStats`
- `0x180056f07`: `MemCachedPieces: cur_size: %zu, max_size: %u`
- `0x180056f8d`: `Swarm %s, Scheduling write completions for %zu pieces`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CStorage::Destroy(CStorage *this, int a2)
{
  __int64 v4; // rbx
  __int64 v5; // rcx
  CAsyncFile *v6; // rcx
  CAsyncFile *v7; // rbx
  __int64 v8; // rax
  const char *v9; // rcx
  __int64 *v10; // rbx
  __int64 v11; // rdi
  char *v12; // rax
  __int64 *v14; // rax
  __int64 *i; // rax
  unsigned int PieceCount; // ebx
  __int64 v17; // r8
  CBitField *v18; // rdi
  void (__fastcall ***v19)(_QWORD, __int64); // [rsp+30h] [rbp-38h] BYREF
  __int64 v20; // [rsp+38h] [rbp-30h] BYREF
  __int128 v21; // [rsp+40h] [rbp-28h]
  __int128 v22; // [rsp+50h] [rbp-18h]

  v4 = *((_QWORD *)this + 1);
  if ( *(_DWORD *)(v4 + 176) != GetCurrentThreadId() )
  {
    LogMessage(2u, "CStorage::Destroy", 0xB8u, "TelemetryAssert (%s): %s", "_coreThread.IsCurrentThread()", "Failed");
    DOTelemetryAssertTriggered(0xFFFFFFFF, 0xFFFFFFFF);
  }
  v5 = *((_QWORD *)this + 11);
  if ( v5 )
    LogMessage(
      4u,
      "CMemCachedPieces::LogStats",
      0x4Fu,
      "MemCachedPieces: cur_size: %zu, max_size: %u",
      *(_QWORD *)(v5 + 32),
      *(_DWORD *)(v5 + 80));
  v6 = (CAsyncFile *)*((_QWORD *)this + 6);
  if ( v6 )
  {
    CAsyncFile::Close(v6, 1);
    v7 = (CAsyncFile *)*((_QWORD *)this + 6);
    *((_QWORD *)this + 6) = 0;
    if ( v7 )
    {
      CAsyncFile::~CAsyncFile(v7);
      operator delete(v7);
    }
  }
  if ( a2 == 1 )
  {
    v8 = *((_QWORD *)this + 2);
    v9 = (const char *)(*(_QWORD *)(v8 + 352) + 272LL);
    if ( *(_QWORD *)(*(_QWORD *)(v8 + 352) + 296LL) > 0xFu )
      v9 = *(const char **)v9;
    LogMessage(
      4u,
      "CStorage::Destroy",
      0xCEu,
      "Swarm %s, Scheduling write completions for %zu pieces",
      v9,
      *((_QWORD *)this + 10));
    v10 = (__int64 *)**((_QWORD **)this + 9);
    while ( !*((_BYTE *)v10 + 25) )
    {
      v11 = *((_QWORD *)this + 1);
      *(_QWORD *)&v22 = this;
      DWORD2(v22) = *((_DWORD *)v10 + 7);
      v21 = (unsigned __int64)(v11 + 16);
      if ( (unsigned int)mtx_do_lock(v11 + 16) )
        std::_Throw_Cpp_error(5);
      if ( *(_DWORD *)(v11 + 92) == 0x7FFFFFFF )
      {
        *(_DWORD *)(v11 + 92) = 2147483646;
        std::_Throw_Cpp_error(6);
      }
      BYTE8(v21) = 1;
      v20 = 0;
      v12 = (char *)operator new(0x20u);
      *(_OWORD *)(v12 + 8) = v22;
      *(_QWORD *)v12 = ___7__CTaskImpl_V_lambda_1___P___Destroy_CStorage__QEAAXI_Z__CTaskQueue__6B_;
      *((_QWORD *)v12 + 3) = this;
      v19 = (void (__fastcall ***)(_QWORD, __int64))v12;
      CTaskQueue::_Add(v11, &v19, &v20);
      if ( v19 )
        (**v19)(v19, 1);
      WakeAllConditionVariable((PCONDITION_VARIABLE)(v11 + 104));
      if ( (*(_DWORD *)(v11 + 92))-- == 1 )
      {
        *(_DWORD *)(v11 + 88) = -1;
        ReleaseSRWLockExclusive((PSRWLOCK)(v11 + 32));
      }
      v14 = (__int64 *)v10[2];
      if ( *((_BYTE *)v14 + 25) )
      {
        for ( i = (__int64 *)v10[1]; !*((_BYTE *)i + 25) && v10 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v10 = i;
        v10 = i;
      }
      else
      {
        do
        {
          v10 = v14;
          v14 = (__int64 *)*v14;
        }
        while ( !*((_BYTE *)v14 + 25) );
      }
    }
    goto LABEL_28;
  }
  if ( a2 )
  {
LABEL_28:
    PieceCount = CMetaInfo::GetPieceCount(*(CMetaInfo **)(*((_QWORD *)this + 2) + 40LL));
    v18 = (CBitField *)(v17 + 144);
    CBitField::operator|=((CBitField *)(v17 + 192), (CBitField *)(v17 + 144));
    CBitField::_SetBuf(v18, PieceCount, 0);
  }
  CSwarmPersistence::PersistStorage(*(CSwarmPersistence **)this, 1);
}

```

## disassembly

```asm
0x180056e88  mov     [rsp+arg_8], rbx
0x180056e8d  mov     [rsp+arg_10], rsi
0x180056e92  push    rdi
0x180056e93  sub     rsp, 60h
0x180056e97  mov     edi, edx
0x180056e99  mov     rsi, rcx
0x180056e9c  mov     rbx, [rcx+8]
0x180056ea0  call    cs:__imp_GetCurrentThreadId
0x180056ea6  cmp     [rbx+0B0h], eax
0x180056eac  jz      short loc_180056EEE
0x180056eae  lea     rax, aFailed; "Failed"
0x180056eb5  mov     [rsp+68h+var_40], rax
0x180056eba  lea     rax, aCorethreadIscu_0; "_coreThread.IsCurrentThread()"
0x180056ec1  mov     [rsp+68h+var_48], rax
0x180056ec6  lea     r9, aTelemetryasser; "TelemetryAssert (%s): %s"
0x180056ecd  mov     r8d, 0B8h; unsigned int
0x180056ed3  lea     rdx, aCstorageDestro; "CStorage::Destroy"
0x180056eda  mov     ecx, 2; unsigned __int8
0x180056edf  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x180056ee4  or      ecx, 0FFFFFFFFh; unsigned int
0x180056ee7  mov     edx, ecx; unsigned int
0x180056ee9  call    ?DOTelemetryAssertTriggered@@YAXII@Z; DOTelemetryAssertTriggered(uint,uint)
0x180056eee  mov     rcx, [rsi+58h]
0x180056ef2  test    rcx, rcx
0x180056ef5  jz      short loc_180056F24
0x180056ef7  mov     eax, [rcx+50h]
0x180056efa  mov     dword ptr [rsp+68h+var_40], eax
0x180056efe  mov     rax, [rcx+20h]
0x180056f02  mov     [rsp+68h+var_48], rax
0x180056f07  lea     r9, aMemcachedpiece_0; "MemCachedPieces: cur_size: %zu, max_siz"...
0x180056f0e  mov     r8d, 4Fh ; 'O'; unsigned int
0x180056f14  lea     rdx, aCmemcachedpiec; "CMemCachedPieces::LogStats"
0x180056f1b  lea     ecx, [r8-4Bh]; unsigned __int8
0x180056f1f  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x180056f24  mov     rcx, [rsi+30h]; this
0x180056f28  test    rcx, rcx
0x180056f2b  jz      short loc_180056F5A
0x180056f2d  mov     dl, 1; bool
0x180056f2f  call    ?Close@CAsyncFile@@QEAAJ_N@Z; CAsyncFile::Close(bool)
0x180056f34  mov     rbx, [rsi+30h]
0x180056f38  mov     qword ptr [rsi+30h], 0
0x180056f40  test    rbx, rbx
0x180056f43  jz      short loc_180056F5A
0x180056f45  mov     rcx, rbx; this
0x180056f48  call    ??1CAsyncFile@@QEAA@XZ; CAsyncFile::~CAsyncFile(void)
0x180056f4d  mov     edx, 30h ; '0'
0x180056f52  mov     rcx, rbx; Block
0x180056f55  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180056f5a  cmp     edi, 1
0x180056f5d  jnz     loc_1800570BC
0x180056f63  mov     r8, [rsi+50h]
0x180056f67  mov     rax, [rsi+10h]
0x180056f6b  mov     rcx, [rax+160h]
0x180056f72  add     rcx, 110h
0x180056f79  cmp     qword ptr [rcx+18h], 0Fh
0x180056f7e  jbe     short loc_180056F83
0x180056f80  mov     rcx, [rcx]
0x180056f83  mov     [rsp+68h+var_40], r8
0x180056f88  mov     [rsp+68h+var_48], rcx
0x180056f8d  lea     r9, aSwarmSScheduli; "Swarm %s, Scheduling write completions "...
0x180056f94  mov     r8d, 0CEh; unsigned int
0x180056f9a  lea     rdx, aCstorageDestro; "CStorage::Destroy"
0x180056fa1  mov     ecx, 4; unsigned __int8
0x180056fa6  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x180056fab  mov     rbx, [rsi+48h]
0x180056faf  mov     rbx, [rbx]
0x180056fb2  jmp     loc_1800570B0
0x180056fb7  mov     rdi, [rsi+8]
0x180056fbb  mov     qword ptr [rsp+68h+var_18], rsi
0x180056fc0  mov     eax, [rbx+1Ch]
0x180056fc3  mov     dword ptr [rsp+68h+var_18+8], eax
0x180056fc7  xorps   xmm0, xmm0
0x180056fca  movups  [rsp+68h+var_28], xmm0
0x180056fcf  lea     rcx, [rdi+10h]
0x180056fd3  mov     qword ptr [rsp+68h+var_28], rcx
0x180056fd8  mov     byte ptr [rsp+68h+var_28+8], 0
0x180056fdd  call    mtx_do_lock
0x180056fe2  test    eax, eax
0x180056fe4  jnz     loc_180057110
0x180056fea  mov     eax, [rdi+5Ch]
0x180056fed  cmp     eax, 7FFFFFFFh
0x180056ff2  jz      loc_18005711B
0x180056ff8  mov     byte ptr [rsp+68h+var_28+8], 1
0x180056ffd  mov     [rsp+68h+var_30], 0
0x180057006  mov     ecx, 20h ; ' '; Size
0x18005700b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180057010  movups  xmm0, [rsp+68h+var_18]
0x180057015  movdqu  xmmword ptr [rax+8], xmm0
0x18005701a  lea     rcx, ??_7?$CTaskImpl@V_lambda_1_@?P@??Destroy@CStorage@@QEAAXI@Z@@CTaskQueue@@6B@; const CTaskQueue::CTaskImpl<`CStorage::Destroy(uint)'::`15'::_lambda_1_>::`vftable'
0x180057021  mov     [rax], rcx
0x180057024  mov     [rax+18h], rsi
0x180057028  mov     [rsp+68h+var_38], rax
0x18005702d  lea     r8, [rsp+68h+var_30]
0x180057032  lea     rdx, [rsp+68h+var_38]
0x180057037  mov     rcx, rdi
0x18005703a  call    ?_Add@CTaskQueue@@AEAAX$$QEAV?$unique_ptr@VTask@CTaskQueue@@U?$default_delete@VTask@CTaskQueue@@@std@@@std@@AEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@3@@Z; CTaskQueue::_Add(std::unique_ptr<CTaskQueue::Task> &&,std::chrono::duration<__int64,std::ratio<1,1000>> const &)
0x18005703f  nop
0x180057040  mov     rcx, [rsp+68h+var_38]
0x180057045  test    rcx, rcx
0x180057048  jz      short loc_18005705A
0x18005704a  mov     rax, [rcx]
0x18005704d  mov     edx, 1
0x180057052  mov     rax, [rax]
0x180057055  call    _guard_dispatch_icall
0x18005705a  lea     rcx, [rdi+68h]; ConditionVariable
0x18005705e  call    cs:__imp_WakeAllConditionVariable
0x180057064  nop
0x180057065  sub     dword ptr [rdi+5Ch], 1
0x180057069  jnz     short loc_18005707C
0x18005706b  mov     dword ptr [rdi+58h], 0FFFFFFFFh
0x180057072  lea     rcx, [rdi+20h]; SRWLock
0x180057076  call    cs:__imp_ReleaseSRWLockExclusive
0x18005707c  mov     rax, [rbx+10h]
0x180057080  cmp     byte ptr [rax+19h], 0
0x180057084  jz      short loc_1800570A4
0x180057086  mov     rax, [rbx+8]
0x18005708a  jmp     short loc_180057099
0x18005708c  cmp     rbx, [rax+10h]
0x180057090  jnz     short loc_18005709F
0x180057092  mov     rbx, rax
0x180057095  mov     rax, [rax+8]
0x180057099  cmp     byte ptr [rax+19h], 0
0x18005709d  jz      short loc_18005708C
0x18005709f  mov     rbx, rax
0x1800570a2  jmp     short loc_1800570B0
0x1800570a4  mov     rbx, rax
0x1800570a7  mov     rax, [rax]
0x1800570aa  cmp     byte ptr [rax+19h], 0
0x1800570ae  jz      short loc_1800570A4
0x1800570b0  cmp     byte ptr [rbx+19h], 0
0x1800570b4  jz      loc_180056FB7
0x1800570ba  jmp     short loc_1800570C0
0x1800570bc  test    edi, edi
0x1800570be  jz      short loc_1800570F5
0x1800570c0  mov     r8, [rsi]
0x1800570c3  mov     rcx, [rsi+10h]
0x1800570c7  mov     rcx, [rcx+28h]; this
0x1800570cb  call    ?GetPieceCount@CMetaInfo@@QEBAIXZ; CMetaInfo::GetPieceCount(void)
0x1800570d0  mov     ebx, eax
0x1800570d2  lea     rdi, [r8+90h]
0x1800570d9  lea     rcx, [r8+0C0h]; this
0x1800570e0  mov     rdx, rdi; CBitField *
0x1800570e3  call    ??_5CBitField@@QEAAAEAV0@AEBV0@@Z; CBitField::operator|=(CBitField const &)
0x1800570e8  mov     edx, ebx; unsigned __int64
0x1800570ea  xor     r8d, r8d; void *
0x1800570ed  mov     rcx, rdi; this
0x1800570f0  call    ?_SetBuf@CBitField@@AEAAX_KPEBX@Z; CBitField::_SetBuf(unsigned __int64,void const *)
0x1800570f5  mov     dl, 1; bool
0x1800570f7  mov     rcx, [rsi]; this
0x1800570fa  lea     r11, [rsp+68h+var_8]
0x1800570ff  mov     rbx, [r11+18h]
0x180057103  mov     rsi, [r11+20h]
0x180057107  mov     rsp, r11
0x18005710a  pop     rdi
0x18005710b  jmp     ?PersistStorage@CSwarmPersistence@@QEAAX_N@Z; CSwarmPersistence::PersistStorage(bool)
0x180057110  mov     ecx, 5; int
0x180057115  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18005711b  dec     eax
0x18005711d  mov     [rdi+5Ch], eax
0x180057120  mov     ecx, 6; int
0x180057125  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
