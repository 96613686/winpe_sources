# Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::AllocSharedBufEvent<tagUMRDP_MAP_CURSOR_BUFFER_EVENT>(UMRDP_EVENT_TYPE,uint)

- ea: `0x180016a9c`
- end: `0x180016c94`
- name: `??$AllocSharedBufEvent@UtagUMRDP_MAP_CURSOR_BUFFER_EVENT@@@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@AEAA?AV?$shared_ptr@V?$CRdpSharedBufEvent@UtagUMRDP_MAP_CURSOR_BUFFER_EVENT@@@Umrdp@Avenc@Rdp@@@std@@W4UMRDP_EVENT_TYPE@@I@Z`
- size: `504`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1800184dc`

## callees

- `0x1800065a4`
- `0x180007018`
- `0x18000b07c`
- `0x1800146bc`
- `0x180016a9c`
- `0x180017ec4`
- `0x180019a04`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180016adf`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180016adf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016b51`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016b51`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180016b47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180016b47`

## string_xrefs

- `0x180016b1c`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\umrdpprocessor\updatechannel.cpp`
- `0x180016b6c`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\umrdpprocessor\updatechannel.cpp`

## pseudocode

```c
_QWORD *__fastcall Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::AllocSharedBufEvent<tagUMRDP_MAP_CURSOR_BUFFER_EVENT>(
        __int64 a1,
        _QWORD *a2)
{
  int v2; // ebx
  int v5; // eax
  unsigned __int8 *v6; // r14
  unsigned int v7; // r8d
  const char *v8; // r9
  char *v9; // rax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  volatile signed __int32 *v12; // rbx
  _QWORD *v13; // rax
  __int64 v14; // r8
  volatile signed __int32 *v15; // rdx
  int v17; // [rsp+20h] [rbp-48h]
  const char *v18; // [rsp+30h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  unsigned __int8 *v20; // [rsp+70h] [rbp+8h] BYREF

  v2 = 0;
  v20 = 0;
  while ( 1 )
  {
    v5 = Rdp::Modern::CTSSharedBufferProducer::AllocateBuffer(
           *(Rdp::Modern::CTSSharedBufferProducer **)(a1 + 104),
           0x94u,
           &v20);
    v6 = v20;
    if ( v5 >= 0 )
      break;
    if ( !(unsigned __int8)Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::WaitForUpdateBufferAvailable(a1)
      && !SetEvent(*(HANDLE *)(a1 + 112)) )
    {
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v7, v8);
    }
    if ( (unsigned int)++v2 >= 8 )
      goto LABEL_8;
  }
  memset_0(v20, 0, 0x94u);
  LOBYTE(v17) = 0;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x130,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\updatechannel.cpp",
    (const char *)0x80004005LL,
    v17,
    (bool)"Event buffer size is smaller than event header",
    v18);
  *(_DWORD *)v6 = 20;
  *((_DWORD *)v6 + 1) = 148;
  *((_DWORD *)v6 + 3) = GetCurrentProcessId();
  *((_DWORD *)v6 + 2) = GetCurrentThreadId();
LABEL_8:
  LOBYTE(v17) = v2 == 8;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x138,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\updatechannel.cpp",
    (const char *)0x800705B4LL,
    v17,
    (bool)"Failed to allocate shared buffer event",
    v18);
  v9 = (char *)operator new(0x28u);
  v20 = (unsigned __int8 *)v9;
  *(_OWORD *)v9 = 0;
  *(_QWORD *)v9 = &std::_Ref_count_obj2<Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>>::`vftable';
  v10 = v9 + 16;
  *((_DWORD *)v9 + 2) = 1;
  *((_DWORD *)v9 + 3) = 1;
  *((_QWORD *)v9 + 2) = 0;
  *((_QWORD *)v9 + 3) = 0;
  *((_QWORD *)v9 + 4) = v6;
  *a2 = v9 + 16;
  a2[1] = v9;
  if ( v9 != (char *)-16LL )
  {
    v11 = *((_QWORD *)v9 + 3);
    if ( !v11 || !*(_DWORD *)(v11 + 8) )
    {
      _InterlockedIncrement((volatile signed __int32 *)v9 + 2);
      v12 = (volatile signed __int32 *)a2[1];
      v13 = 0;
      v14 = 0;
      if ( v12 )
      {
        v13 = v10;
        v14 = a2[1];
        _InterlockedIncrement(v12 + 3);
      }
      v15 = (volatile signed __int32 *)v10[1];
      *v10 = v13;
      v10[1] = v14;
      if ( v15 && _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
      if ( v12 )
      {
        if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
          if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
        }
      }
    }
  }
  return a2;
}

```

## disassembly

```asm
0x180016a9c  push    rbx
0x180016a9e  push    rsi
0x180016a9f  push    rdi
0x180016aa0  push    r14
0x180016aa2  sub     rsp, 48h
0x180016aa6  xor     ebx, ebx
0x180016aa8  mov     rsi, rdx
0x180016aab  mov     [rsp+68h+arg_0], rbx
0x180016ab0  mov     rdi, rcx
0x180016ab3  mov     rcx, [rdi+68h]; this
0x180016ab7  lea     r8, [rsp+68h+arg_0]; unsigned __int8 **
0x180016abc  mov     edx, 94h; unsigned int
0x180016ac1  call    ?AllocateBuffer@CTSSharedBufferProducer@Modern@Rdp@@QEAAJIPEAPEAE@Z; Rdp::Modern::CTSSharedBufferProducer::AllocateBuffer(uint,uchar * *)
0x180016ac6  mov     r14, [rsp+68h+arg_0]
0x180016acb  test    eax, eax
0x180016acd  jns     short loc_180016AFB
0x180016acf  mov     rcx, rdi
0x180016ad2  call    ?WaitForUpdateBufferAvailable@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@AEAA_NXZ; Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::WaitForUpdateBufferAvailable(void)
0x180016ad7  test    al, al
0x180016ad9  jnz     short loc_180016AF2
0x180016adb  mov     rcx, [rdi+70h]; hEvent
0x180016adf  call    cs:__imp_SetEvent
0x180016ae5  mov     rcx, [rsp+68h]; this
0x180016aea  test    eax, eax
0x180016aec  jz      loc_180016C89
0x180016af2  inc     ebx
0x180016af4  cmp     ebx, 8
0x180016af7  jb      short loc_180016AB3
0x180016af9  jmp     short loc_180016B5B
0x180016afb  xor     edx, edx; Val
0x180016afd  mov     r8d, 94h; Size
0x180016b03  mov     rcx, r14; void *
0x180016b06  call    memset_0
0x180016b0b  mov     rcx, [rsp+68h]; this
0x180016b10  lea     rax, aEventBufferSiz; "Event buffer size is smaller than event"...
0x180016b17  mov     qword ptr [rsp+68h+var_40], rax; bool
0x180016b1c  lea     r8, aOnecoreuapTerm_36; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180016b23  mov     r9d, 80004005h; char *
0x180016b29  mov     byte ptr [rsp+68h+var_48], 0; int
0x180016b2e  mov     edx, 130h; void *
0x180016b33  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180016b38  mov     dword ptr [r14], 14h
0x180016b3f  mov     dword ptr [r14+4], 94h
0x180016b47  call    cs:__imp_GetCurrentProcessId
0x180016b4d  mov     [r14+0Ch], eax
0x180016b51  call    cs:__imp_GetCurrentThreadId
0x180016b57  mov     [r14+8], eax
0x180016b5b  mov     rcx, [rsp+68h]; this
0x180016b60  lea     rdx, aFailedToAlloca_0; "Failed to allocate shared buffer event"
0x180016b67  mov     qword ptr [rsp+68h+var_40], rdx; bool
0x180016b6c  lea     r8, aOnecoreuapTerm_36; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180016b73  cmp     ebx, 8
0x180016b76  mov     r9d, 800705B4h; char *
0x180016b7c  mov     edx, 138h; void *
0x180016b81  setz    al
0x180016b84  mov     byte ptr [rsp+68h+var_48], al; int
0x180016b88  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180016b8d  mov     ecx, 28h ; '('; Size
0x180016b92  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180016b97  mov     [rsp+68h+arg_0], rax
0x180016b9c  lea     rcx, ??_7?$_Ref_count_obj2@V?$CRdpSharedBufEvent@UUMRDP_CREATE_SURFACE_EVENT_EX@@@Umrdp@Avenc@Rdp@@@std@@6B@; const std::_Ref_count_obj2<Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>>::`vftable'
0x180016ba3  xorps   xmm0, xmm0
0x180016ba6  movups  xmmword ptr [rax], xmm0
0x180016ba9  mov     [rax], rcx
0x180016bac  lea     rcx, [rax+10h]
0x180016bb0  mov     dword ptr [rax+8], 1
0x180016bb7  mov     dword ptr [rax+0Ch], 1
0x180016bbe  mov     qword ptr [rcx], 0
0x180016bc5  mov     qword ptr [rcx+8], 0
0x180016bcd  mov     [rcx+10h], r14
0x180016bd1  mov     [rsi], rcx
0x180016bd4  mov     [rsi+8], rax
0x180016bd8  test    rcx, rcx
0x180016bdb  jz      loc_180016C7C
0x180016be1  mov     rdx, [rcx+8]
0x180016be5  test    rdx, rdx
0x180016be8  jz      short loc_180016BF4
0x180016bea  cmp     dword ptr [rdx+8], 0
0x180016bee  jnz     loc_180016C7C
0x180016bf4  lock inc dword ptr [rax+8]
0x180016bf8  mov     rbx, [rsi+8]
0x180016bfc  xor     eax, eax
0x180016bfe  xor     r8d, r8d
0x180016c01  test    rbx, rbx
0x180016c04  jz      short loc_180016C10
0x180016c06  mov     rax, rcx
0x180016c09  mov     r8, rbx
0x180016c0c  lock inc dword ptr [rbx+0Ch]
0x180016c10  mov     rdx, [rcx+8]
0x180016c14  or      r14d, 0FFFFFFFFh
0x180016c18  mov     [rcx], rax
0x180016c1b  mov     [rcx+8], r8
0x180016c1f  test    rdx, rdx
0x180016c22  jz      short loc_180016C40
0x180016c24  mov     eax, r14d
0x180016c27  lock xadd [rdx+0Ch], eax
0x180016c2c  add     eax, r14d
0x180016c2f  jnz     short loc_180016C40
0x180016c31  mov     rax, [rdx]
0x180016c34  mov     rcx, rdx
0x180016c37  mov     rax, [rax+8]
0x180016c3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c40  test    rbx, rbx
0x180016c43  jz      short loc_180016C7C
0x180016c45  mov     eax, r14d
0x180016c48  lock xadd [rbx+8], eax
0x180016c4d  add     eax, r14d
0x180016c50  jnz     short loc_180016C7C
0x180016c52  mov     rax, [rbx]
0x180016c55  mov     rcx, rbx
0x180016c58  mov     rax, [rax]
0x180016c5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c60  mov     eax, r14d
0x180016c63  lock xadd [rbx+0Ch], eax
0x180016c68  add     eax, r14d
0x180016c6b  jnz     short loc_180016C7C
0x180016c6d  mov     rax, [rbx]
0x180016c70  mov     rcx, rbx
0x180016c73  mov     rax, [rax+8]
0x180016c77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c7c  mov     rax, rsi
0x180016c7f  add     rsp, 48h
0x180016c83  pop     r14
0x180016c85  pop     rdi
0x180016c86  pop     rsi
0x180016c87  pop     rbx
0x180016c88  retn
0x180016c89  mov     edx, 0A01h; void *
0x180016c8e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
