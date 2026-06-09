# Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::AllocSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>(UMRDP_EVENT_TYPE,uint)

- ea: `0x180015ad8`
- end: `0x180015cd0`
- name: `??$AllocSharedBufEvent@UUMRDP_CREATE_SURFACE_EVENT_EX@@@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@AEAA?AV?$shared_ptr@V?$CRdpSharedBufEvent@UUMRDP_CREATE_SURFACE_EVENT_EX@@@Umrdp@Avenc@Rdp@@@std@@W4UMRDP_EVENT_TYPE@@I@Z`
- size: `504`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18001935c`

## callees

- `0x1800065a4`
- `0x180007018`
- `0x18000b07c`
- `0x1800146bc`
- `0x180015ad8`
- `0x180017ec4`
- `0x180019a04`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180015b1b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180015b1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015b8d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015b8d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180015b83`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180015b83`

## string_xrefs

- `0x180015b58`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\umrdpprocessor\updatechannel.cpp`
- `0x180015ba8`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\umrdpprocessor\updatechannel.cpp`

## pseudocode

```c
_QWORD *__fastcall Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::AllocSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>(
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
           0xB4u,
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
  memset_0(v20, 0, 0xB4u);
  LOBYTE(v17) = 0;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x130,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\updatechannel.cpp",
    (const char *)0x80004005LL,
    v17,
    (bool)"Event buffer size is smaller than event header",
    v18);
  *(_DWORD *)v6 = 19;
  *((_DWORD *)v6 + 1) = 180;
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
0x180015ad8  push    rbx
0x180015ada  push    rsi
0x180015adb  push    rdi
0x180015adc  push    r14
0x180015ade  sub     rsp, 48h
0x180015ae2  xor     ebx, ebx
0x180015ae4  mov     rsi, rdx
0x180015ae7  mov     [rsp+68h+arg_0], rbx
0x180015aec  mov     rdi, rcx
0x180015aef  mov     rcx, [rdi+68h]; this
0x180015af3  lea     r8, [rsp+68h+arg_0]; unsigned __int8 **
0x180015af8  mov     edx, 0B4h; unsigned int
0x180015afd  call    ?AllocateBuffer@CTSSharedBufferProducer@Modern@Rdp@@QEAAJIPEAPEAE@Z; Rdp::Modern::CTSSharedBufferProducer::AllocateBuffer(uint,uchar * *)
0x180015b02  mov     r14, [rsp+68h+arg_0]
0x180015b07  test    eax, eax
0x180015b09  jns     short loc_180015B37
0x180015b0b  mov     rcx, rdi
0x180015b0e  call    ?WaitForUpdateBufferAvailable@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@AEAA_NXZ; Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::WaitForUpdateBufferAvailable(void)
0x180015b13  test    al, al
0x180015b15  jnz     short loc_180015B2E
0x180015b17  mov     rcx, [rdi+70h]; hEvent
0x180015b1b  call    cs:__imp_SetEvent
0x180015b21  mov     rcx, [rsp+68h]; this
0x180015b26  test    eax, eax
0x180015b28  jz      loc_180015CC5
0x180015b2e  inc     ebx
0x180015b30  cmp     ebx, 8
0x180015b33  jb      short loc_180015AEF
0x180015b35  jmp     short loc_180015B97
0x180015b37  xor     edx, edx; Val
0x180015b39  mov     r8d, 0B4h; Size
0x180015b3f  mov     rcx, r14; void *
0x180015b42  call    memset_0
0x180015b47  mov     rcx, [rsp+68h]; this
0x180015b4c  lea     rax, aEventBufferSiz; "Event buffer size is smaller than event"...
0x180015b53  mov     qword ptr [rsp+68h+var_40], rax; bool
0x180015b58  lea     r8, aOnecoreuapTerm_36; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180015b5f  mov     r9d, 80004005h; char *
0x180015b65  mov     byte ptr [rsp+68h+var_48], 0; int
0x180015b6a  mov     edx, 130h; void *
0x180015b6f  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180015b74  mov     dword ptr [r14], 13h
0x180015b7b  mov     dword ptr [r14+4], 0B4h
0x180015b83  call    cs:__imp_GetCurrentProcessId
0x180015b89  mov     [r14+0Ch], eax
0x180015b8d  call    cs:__imp_GetCurrentThreadId
0x180015b93  mov     [r14+8], eax
0x180015b97  mov     rcx, [rsp+68h]; this
0x180015b9c  lea     rdx, aFailedToAlloca_0; "Failed to allocate shared buffer event"
0x180015ba3  mov     qword ptr [rsp+68h+var_40], rdx; bool
0x180015ba8  lea     r8, aOnecoreuapTerm_36; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180015baf  cmp     ebx, 8
0x180015bb2  mov     r9d, 800705B4h; char *
0x180015bb8  mov     edx, 138h; void *
0x180015bbd  setz    al
0x180015bc0  mov     byte ptr [rsp+68h+var_48], al; int
0x180015bc4  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180015bc9  mov     ecx, 28h ; '('; Size
0x180015bce  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180015bd3  mov     [rsp+68h+arg_0], rax
0x180015bd8  lea     rcx, ??_7?$_Ref_count_obj2@V?$CRdpSharedBufEvent@UUMRDP_CREATE_SURFACE_EVENT_EX@@@Umrdp@Avenc@Rdp@@@std@@6B@; const std::_Ref_count_obj2<Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>>::`vftable'
0x180015bdf  xorps   xmm0, xmm0
0x180015be2  movups  xmmword ptr [rax], xmm0
0x180015be5  mov     [rax], rcx
0x180015be8  lea     rcx, [rax+10h]
0x180015bec  mov     dword ptr [rax+8], 1
0x180015bf3  mov     dword ptr [rax+0Ch], 1
0x180015bfa  mov     qword ptr [rcx], 0
0x180015c01  mov     qword ptr [rcx+8], 0
0x180015c09  mov     [rcx+10h], r14
0x180015c0d  mov     [rsi], rcx
0x180015c10  mov     [rsi+8], rax
0x180015c14  test    rcx, rcx
0x180015c17  jz      loc_180015CB8
0x180015c1d  mov     rdx, [rcx+8]
0x180015c21  test    rdx, rdx
0x180015c24  jz      short loc_180015C30
0x180015c26  cmp     dword ptr [rdx+8], 0
0x180015c2a  jnz     loc_180015CB8
0x180015c30  lock inc dword ptr [rax+8]
0x180015c34  mov     rbx, [rsi+8]
0x180015c38  xor     eax, eax
0x180015c3a  xor     r8d, r8d
0x180015c3d  test    rbx, rbx
0x180015c40  jz      short loc_180015C4C
0x180015c42  mov     rax, rcx
0x180015c45  mov     r8, rbx
0x180015c48  lock inc dword ptr [rbx+0Ch]
0x180015c4c  mov     rdx, [rcx+8]
0x180015c50  or      r14d, 0FFFFFFFFh
0x180015c54  mov     [rcx], rax
0x180015c57  mov     [rcx+8], r8
0x180015c5b  test    rdx, rdx
0x180015c5e  jz      short loc_180015C7C
0x180015c60  mov     eax, r14d
0x180015c63  lock xadd [rdx+0Ch], eax
0x180015c68  add     eax, r14d
0x180015c6b  jnz     short loc_180015C7C
0x180015c6d  mov     rax, [rdx]
0x180015c70  mov     rcx, rdx
0x180015c73  mov     rax, [rax+8]
0x180015c77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c7c  test    rbx, rbx
0x180015c7f  jz      short loc_180015CB8
0x180015c81  mov     eax, r14d
0x180015c84  lock xadd [rbx+8], eax
0x180015c89  add     eax, r14d
0x180015c8c  jnz     short loc_180015CB8
0x180015c8e  mov     rax, [rbx]
0x180015c91  mov     rcx, rbx
0x180015c94  mov     rax, [rax]
0x180015c97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c9c  mov     eax, r14d
0x180015c9f  lock xadd [rbx+0Ch], eax
0x180015ca4  add     eax, r14d
0x180015ca7  jnz     short loc_180015CB8
0x180015ca9  mov     rax, [rbx]
0x180015cac  mov     rcx, rbx
0x180015caf  mov     rax, [rax+8]
0x180015cb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015cb8  mov     rax, rsi
0x180015cbb  add     rsp, 48h
0x180015cbf  pop     r14
0x180015cc1  pop     rdi
0x180015cc2  pop     rsi
0x180015cc3  pop     rbx
0x180015cc4  retn
0x180015cc5  mov     edx, 0A01h; void *
0x180015cca  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
