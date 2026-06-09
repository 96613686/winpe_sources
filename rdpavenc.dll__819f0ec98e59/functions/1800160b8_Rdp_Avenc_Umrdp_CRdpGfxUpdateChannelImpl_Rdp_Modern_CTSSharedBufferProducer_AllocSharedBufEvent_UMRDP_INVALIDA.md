# Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::AllocSharedBufEvent<UMRDP_INVALIDATE_RECT_EVENT>(UMRDP_EVENT_TYPE,uint)

- ea: `0x1800160b8`
- end: `0x1800162ae`
- name: `??$AllocSharedBufEvent@UUMRDP_INVALIDATE_RECT_EVENT@@@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@AEAA?AV?$shared_ptr@V?$CRdpSharedBufEvent@UUMRDP_INVALIDATE_RECT_EVENT@@@Umrdp@Avenc@Rdp@@@std@@W4UMRDP_EVENT_TYPE@@I@Z`
- size: `502`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180018dc8`

## callees

- `0x1800065a4`
- `0x180007018`
- `0x18000b07c`
- `0x1800146bc`
- `0x1800160b8`
- `0x180017ec4`
- `0x180019a04`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800160fb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800160fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001616b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001616b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180016161`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180016161`

## string_xrefs

- `0x180016136`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\umrdpprocessor\updatechannel.cpp`
- `0x180016186`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\umrdpprocessor\updatechannel.cpp`

## pseudocode

```c
_QWORD *__fastcall Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::AllocSharedBufEvent<UMRDP_INVALIDATE_RECT_EVENT>(
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
           0x44u,
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
  memset_0(v20, 0, 0x44u);
  LOBYTE(v17) = 0;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x130,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\updatechannel.cpp",
    (const char *)0x80004005LL,
    v17,
    (bool)"Event buffer size is smaller than event header",
    v18);
  *(_DWORD *)v6 = 0;
  *((_DWORD *)v6 + 1) = 68;
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
0x1800160b8  push    rbx
0x1800160ba  push    rsi
0x1800160bb  push    rdi
0x1800160bc  push    r14
0x1800160be  sub     rsp, 48h
0x1800160c2  xor     ebx, ebx
0x1800160c4  mov     rsi, rdx
0x1800160c7  mov     [rsp+68h+arg_0], rbx
0x1800160cc  mov     rdi, rcx
0x1800160cf  mov     rcx, [rdi+68h]; this
0x1800160d3  lea     r8, [rsp+68h+arg_0]; unsigned __int8 **
0x1800160d8  mov     edx, 44h ; 'D'; unsigned int
0x1800160dd  call    ?AllocateBuffer@CTSSharedBufferProducer@Modern@Rdp@@QEAAJIPEAPEAE@Z; Rdp::Modern::CTSSharedBufferProducer::AllocateBuffer(uint,uchar * *)
0x1800160e2  mov     r14, [rsp+68h+arg_0]
0x1800160e7  test    eax, eax
0x1800160e9  jns     short loc_180016117
0x1800160eb  mov     rcx, rdi
0x1800160ee  call    ?WaitForUpdateBufferAvailable@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@AEAA_NXZ; Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::WaitForUpdateBufferAvailable(void)
0x1800160f3  test    al, al
0x1800160f5  jnz     short loc_18001610E
0x1800160f7  mov     rcx, [rdi+70h]; hEvent
0x1800160fb  call    cs:__imp_SetEvent
0x180016101  mov     rcx, [rsp+68h]; this
0x180016106  test    eax, eax
0x180016108  jz      loc_1800162A3
0x18001610e  inc     ebx
0x180016110  cmp     ebx, 8
0x180016113  jb      short loc_1800160CF
0x180016115  jmp     short loc_180016175
0x180016117  xor     edx, edx; Val
0x180016119  mov     rcx, r14; void *
0x18001611c  lea     r8d, [rdx+44h]; Size
0x180016120  call    memset_0
0x180016125  mov     rcx, [rsp+68h]; this
0x18001612a  lea     rax, aEventBufferSiz; "Event buffer size is smaller than event"...
0x180016131  mov     qword ptr [rsp+68h+var_40], rax; bool
0x180016136  lea     r8, aOnecoreuapTerm_36; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18001613d  mov     r9d, 80004005h; char *
0x180016143  mov     byte ptr [rsp+68h+var_48], 0; int
0x180016148  mov     edx, 130h; void *
0x18001614d  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180016152  mov     dword ptr [r14], 0
0x180016159  mov     dword ptr [r14+4], 44h ; 'D'
0x180016161  call    cs:__imp_GetCurrentProcessId
0x180016167  mov     [r14+0Ch], eax
0x18001616b  call    cs:__imp_GetCurrentThreadId
0x180016171  mov     [r14+8], eax
0x180016175  mov     rcx, [rsp+68h]; this
0x18001617a  lea     rdx, aFailedToAlloca_0; "Failed to allocate shared buffer event"
0x180016181  mov     qword ptr [rsp+68h+var_40], rdx; bool
0x180016186  lea     r8, aOnecoreuapTerm_36; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18001618d  cmp     ebx, 8
0x180016190  mov     r9d, 800705B4h; char *
0x180016196  mov     edx, 138h; void *
0x18001619b  setz    al
0x18001619e  mov     byte ptr [rsp+68h+var_48], al; int
0x1800161a2  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1800161a7  mov     ecx, 28h ; '('; Size
0x1800161ac  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800161b1  mov     [rsp+68h+arg_0], rax
0x1800161b6  lea     rcx, ??_7?$_Ref_count_obj2@V?$CRdpSharedBufEvent@UUMRDP_CREATE_SURFACE_EVENT_EX@@@Umrdp@Avenc@Rdp@@@std@@6B@; const std::_Ref_count_obj2<Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>>::`vftable'
0x1800161bd  xorps   xmm0, xmm0
0x1800161c0  movups  xmmword ptr [rax], xmm0
0x1800161c3  mov     [rax], rcx
0x1800161c6  lea     rcx, [rax+10h]
0x1800161ca  mov     dword ptr [rax+8], 1
0x1800161d1  mov     dword ptr [rax+0Ch], 1
0x1800161d8  mov     qword ptr [rcx], 0
0x1800161df  mov     qword ptr [rcx+8], 0
0x1800161e7  mov     [rcx+10h], r14
0x1800161eb  mov     [rsi], rcx
0x1800161ee  mov     [rsi+8], rax
0x1800161f2  test    rcx, rcx
0x1800161f5  jz      loc_180016296
0x1800161fb  mov     rdx, [rcx+8]
0x1800161ff  test    rdx, rdx
0x180016202  jz      short loc_18001620E
0x180016204  cmp     dword ptr [rdx+8], 0
0x180016208  jnz     loc_180016296
0x18001620e  lock inc dword ptr [rax+8]
0x180016212  mov     rbx, [rsi+8]
0x180016216  xor     eax, eax
0x180016218  xor     r8d, r8d
0x18001621b  test    rbx, rbx
0x18001621e  jz      short loc_18001622A
0x180016220  mov     rax, rcx
0x180016223  mov     r8, rbx
0x180016226  lock inc dword ptr [rbx+0Ch]
0x18001622a  mov     rdx, [rcx+8]
0x18001622e  or      r14d, 0FFFFFFFFh
0x180016232  mov     [rcx], rax
0x180016235  mov     [rcx+8], r8
0x180016239  test    rdx, rdx
0x18001623c  jz      short loc_18001625A
0x18001623e  mov     eax, r14d
0x180016241  lock xadd [rdx+0Ch], eax
0x180016246  add     eax, r14d
0x180016249  jnz     short loc_18001625A
0x18001624b  mov     rax, [rdx]
0x18001624e  mov     rcx, rdx
0x180016251  mov     rax, [rax+8]
0x180016255  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001625a  test    rbx, rbx
0x18001625d  jz      short loc_180016296
0x18001625f  mov     eax, r14d
0x180016262  lock xadd [rbx+8], eax
0x180016267  add     eax, r14d
0x18001626a  jnz     short loc_180016296
0x18001626c  mov     rax, [rbx]
0x18001626f  mov     rcx, rbx
0x180016272  mov     rax, [rax]
0x180016275  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001627a  mov     eax, r14d
0x18001627d  lock xadd [rbx+0Ch], eax
0x180016282  add     eax, r14d
0x180016285  jnz     short loc_180016296
0x180016287  mov     rax, [rbx]
0x18001628a  mov     rcx, rbx
0x18001628d  mov     rax, [rax+8]
0x180016291  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016296  mov     rax, rsi
0x180016299  add     rsp, 48h
0x18001629d  pop     r14
0x18001629f  pop     rdi
0x1800162a0  pop     rsi
0x1800162a1  pop     rbx
0x1800162a2  retn
0x1800162a3  mov     edx, 0A01h; void *
0x1800162a8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
