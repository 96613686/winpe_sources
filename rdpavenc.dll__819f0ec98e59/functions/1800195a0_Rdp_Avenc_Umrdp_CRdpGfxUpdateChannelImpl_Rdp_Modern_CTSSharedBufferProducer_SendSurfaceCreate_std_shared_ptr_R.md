# Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::SendSurfaceCreate(std::shared_ptr<Rdp::Avenc::Umrdp::CRdpSharedTextureSurface> const &)

- ea: `0x1800195a0`
- end: `0x180019768`
- name: `?SendSurfaceCreate@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@QEAAXAEBV?$shared_ptr@VCRdpSharedTextureSurface@Umrdp@Avenc@Rdp@@@std@@@Z`
- size: `456`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180020930`

## callees

- `0x1800080cc`
- `0x18000b07c`
- `0x1800156d0`
- `0x1800158e4`
- `0x1800162b4`
- `0x180016e98`
- `0x180018108`
- `0x1800188e4`
- `0x1800195a0`
- `0x1800199cc`
- `0x180019c04`
- `0x18007d7a4`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180019631`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180019631`

## string_xrefs

- `0x180019756`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\umrdpprocessor\updatechannel.cpp`
- `0x18001974a`: `Failed to commit event %d to shared memory`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::SendSurfaceCreate(
        __int64 a1,
        __int64 a2)
{
  __int64 v4; // r8
  __int64 v5; // rdx
  int v6; // esi
  unsigned int v7; // r8d
  const char *v8; // r9
  __int64 v9; // rdx
  __int64 result; // rax
  volatile signed __int32 *v11; // rbx
  volatile signed __int32 *v12; // rbx
  __int64 v13; // rax
  int v14; // ebx
  __int64 v15; // rcx
  unsigned __int8 *Header; // rax
  Rdp::Modern::CTSSharedBufferProducer *v17; // rcx
  unsigned int v18; // eax
  char *v19; // [rsp+28h] [rbp-30h]
  __int64 v20; // [rsp+30h] [rbp-28h] BYREF
  volatile signed __int32 *v21; // [rsp+38h] [rbp-20h]
  __int64 v22; // [rsp+40h] [rbp-18h] BYREF
  volatile signed __int32 *v23; // [rsp+48h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( !*(_BYTE *)(a1 + 144) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::AllocSharedBufEvent<UMRDP_CREATE_SURFACE_DXTEXTURE_EVENT>(
    a1,
    &v22);
  v4 = v22;
  v5 = *(_QWORD *)(v22 + 16);
  *(_DWORD *)(v5 + 16) = *(_DWORD *)(*(_QWORD *)a2 + 76LL);
  *(_DWORD *)(v5 + 20) = *(_DWORD *)(*(_QWORD *)a2 + 72LL);
  *(_QWORD *)(v5 + 24) = *(_QWORD *)(*(_QWORD *)a2 + 64LL);
  *(_QWORD *)(v5 + 32) = *(_QWORD *)(*(_QWORD *)a2 + 128LL);
  *(_QWORD *)(v5 + 40) = 0;
  *(_DWORD *)(v5 + 48) = *(_DWORD *)(*(_QWORD *)a2 + 84LL);
  v6 = Rdp::Modern::CTSSharedBufferProducer::CommitBuffer(
         *(Rdp::Modern::CTSSharedBufferProducer **)(a1 + 104),
         *(unsigned __int8 **)(v4 + 16));
  if ( v6 < 0 )
  {
    v13 = std::shared_ptr<Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>>::operator-><Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>,0>(&v22);
    v14 = *(_DWORD *)Rdp::Avenc::Umrdp::CRdpSharedBufEvent<tagUMRDP_MAP_CURSOR_BUFFER_EVENT>::getHeader(v13);
    Header = (unsigned __int8 *)Rdp::Avenc::Umrdp::CRdpSharedBufEvent<tagUMRDP_MAP_CURSOR_BUFFER_EVENT>::getHeader(v15);
    Rdp::Modern::CTSSharedBufferProducer::FreeBuffer(v17, Header);
    v18 = wil::verify_hresult<long>((unsigned int)v6);
    LODWORD(v19) = v14;
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x14D,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\updatechannel.cpp",
      (const char *)v18,
      (int)"Failed to commit event %d to shared memory",
      v19);
  }
  if ( !SetEvent(*(HANDLE *)(a1 + 112)) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v7, v8);
  Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::AllocSharedBufEvent<UMRDP_MAP_SURFACE_TO_MONITOR_EVENT>(
    a1,
    &v20);
  v9 = *(_QWORD *)(v20 + 16);
  *(_DWORD *)(v9 + 16) = *(_DWORD *)(*(_QWORD *)a2 + 56LL);
  *(_QWORD *)(v9 + 20) = *(_QWORD *)(*(_QWORD *)a2 + 64LL);
  result = Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::CommitSharedBufferEvent<UMRDP_MAP_SURFACE_TO_MONITOR_EVENT>(
             a1,
             &v20);
  v11 = v21;
  if ( v21 )
  {
    result = (unsigned int)_InterlockedDecrement(v21 + 2);
    if ( !(_DWORD)result )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
      result = (unsigned int)_InterlockedDecrement(v11 + 3);
      if ( !(_DWORD)result )
        result = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
    }
  }
  v12 = v23;
  if ( v23 )
  {
    result = (unsigned int)_InterlockedDecrement(v23 + 2);
    if ( !(_DWORD)result )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
      result = (unsigned int)_InterlockedDecrement(v12 + 3);
      if ( !(_DWORD)result )
        return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800195a0  mov     [rsp+arg_0], rbx
0x1800195a5  mov     [rsp+arg_8], rsi
0x1800195aa  push    rdi
0x1800195ab  sub     rsp, 50h
0x1800195af  mov     rdi, rdx
0x1800195b2  mov     rbx, rcx
0x1800195b5  cmp     byte ptr [rcx+90h], 0
0x1800195bc  jnz     short loc_1800195C3
0x1800195be  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800195c3  lea     rdx, [rsp+58h+var_18]
0x1800195c8  mov     rcx, rbx
0x1800195cb  call    ??$AllocSharedBufEvent@UUMRDP_CREATE_SURFACE_DXTEXTURE_EVENT@@@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@AEAA?AV?$shared_ptr@V?$CRdpSharedBufEvent@UUMRDP_CREATE_SURFACE_DXTEXTURE_EVENT@@@Umrdp@Avenc@Rdp@@@std@@W4UMRDP_EVENT_TYPE@@I@Z; Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::AllocSharedBufEvent<UMRDP_CREATE_SURFACE_DXTEXTURE_EVENT>(UMRDP_EVENT_TYPE,uint)
0x1800195d0  nop
0x1800195d1  mov     r8, [rsp+58h+var_18]
0x1800195d6  mov     rdx, [r8+10h]
0x1800195da  mov     rax, [rdi]
0x1800195dd  mov     ecx, [rax+4Ch]
0x1800195e0  mov     [rdx+10h], ecx
0x1800195e3  mov     rax, [rdi]
0x1800195e6  mov     ecx, [rax+48h]
0x1800195e9  mov     [rdx+14h], ecx
0x1800195ec  mov     rax, [rdi]
0x1800195ef  mov     rcx, [rax+40h]
0x1800195f3  mov     [rdx+18h], rcx
0x1800195f7  mov     rax, [rdi]
0x1800195fa  mov     rcx, [rax+80h]
0x180019601  mov     [rdx+20h], rcx
0x180019605  mov     qword ptr [rdx+28h], 0
0x18001960d  mov     rax, [rdi]
0x180019610  mov     ecx, [rax+54h]
0x180019613  mov     [rdx+30h], ecx
0x180019616  mov     rdx, [r8+10h]; unsigned __int8 *
0x18001961a  mov     rcx, [rbx+68h]; this
0x18001961e  call    ?CommitBuffer@CTSSharedBufferProducer@Modern@Rdp@@QEAAJPEAE@Z; Rdp::Modern::CTSSharedBufferProducer::CommitBuffer(uchar *)
0x180019623  mov     esi, eax
0x180019625  test    eax, eax
0x180019627  js      loc_180019716
0x18001962d  mov     rcx, [rbx+70h]; hEvent
0x180019631  call    cs:__imp_SetEvent
0x180019637  mov     rcx, [rsp+58h]; this
0x18001963c  test    eax, eax
0x18001963e  jz      loc_18001970B
0x180019644  lea     rdx, [rsp+58h+var_28]
0x180019649  mov     rcx, rbx
0x18001964c  call    ??$AllocSharedBufEvent@UUMRDP_MAP_SURFACE_TO_MONITOR_EVENT@@@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@AEAA?AV?$shared_ptr@V?$CRdpSharedBufEvent@UUMRDP_MAP_SURFACE_TO_MONITOR_EVENT@@@Umrdp@Avenc@Rdp@@@std@@W4UMRDP_EVENT_TYPE@@I@Z; Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::AllocSharedBufEvent<UMRDP_MAP_SURFACE_TO_MONITOR_EVENT>(UMRDP_EVENT_TYPE,uint)
0x180019651  nop
0x180019652  mov     rax, [rsp+58h+var_28]
0x180019657  mov     rdx, [rax+10h]
0x18001965b  mov     rax, [rdi]
0x18001965e  mov     ecx, [rax+38h]
0x180019661  mov     [rdx+10h], ecx
0x180019664  mov     rax, [rdi]
0x180019667  mov     rcx, [rax+40h]
0x18001966b  mov     [rdx+14h], rcx
0x18001966f  lea     rdx, [rsp+58h+var_28]
0x180019674  mov     rcx, rbx
0x180019677  call    ??$CommitSharedBufferEvent@UUMRDP_MAP_SURFACE_TO_MONITOR_EVENT@@@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@AEAAXAEBV?$shared_ptr@V?$CRdpSharedBufEvent@UUMRDP_MAP_SURFACE_TO_MONITOR_EVENT@@@Umrdp@Avenc@Rdp@@@std@@@Z; Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::CommitSharedBufferEvent<UMRDP_MAP_SURFACE_TO_MONITOR_EVENT>(std::shared_ptr<Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_MAP_SURFACE_TO_MONITOR_EVENT>> const &)
0x18001967c  nop
0x18001967d  or      edi, 0FFFFFFFFh
0x180019680  mov     rbx, [rsp+58h+var_20]
0x180019685  test    rbx, rbx
0x180019688  jz      short loc_1800196BE
0x18001968a  mov     eax, edi
0x18001968c  lock xadd [rbx+8], eax
0x180019691  add     eax, edi
0x180019693  jnz     short loc_1800196BE
0x180019695  mov     rax, [rbx]
0x180019698  mov     rcx, rbx
0x18001969b  mov     rax, [rax]
0x18001969e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800196a3  mov     eax, edi
0x1800196a5  lock xadd [rbx+0Ch], eax
0x1800196aa  add     eax, edi
0x1800196ac  jnz     short loc_1800196BE
0x1800196ae  mov     rax, [rbx]
0x1800196b1  mov     rcx, rbx
0x1800196b4  mov     rax, [rax+8]
0x1800196b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800196bd  nop
0x1800196be  mov     rbx, [rsp+58h+var_10]
0x1800196c3  test    rbx, rbx
0x1800196c6  jz      short loc_1800196FB
0x1800196c8  mov     eax, edi
0x1800196ca  lock xadd [rbx+8], eax
0x1800196cf  add     eax, edi
0x1800196d1  jnz     short loc_1800196FB
0x1800196d3  mov     rax, [rbx]
0x1800196d6  mov     rcx, rbx
0x1800196d9  mov     rax, [rax]
0x1800196dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800196e1  mov     eax, edi
0x1800196e3  lock xadd [rbx+0Ch], eax
0x1800196e8  add     eax, edi
0x1800196ea  jnz     short loc_1800196FB
0x1800196ec  mov     rax, [rbx]
0x1800196ef  mov     rcx, rbx
0x1800196f2  mov     rax, [rax+8]
0x1800196f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800196fb  mov     rbx, [rsp+58h+arg_0]
0x180019700  mov     rsi, [rsp+58h+arg_8]
0x180019705  add     rsp, 50h
0x180019709  pop     rdi
0x18001970a  retn
0x18001970b  mov     edx, 0A01h; void *
0x180019710  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180019716  lea     rcx, [rsp+58h+var_18]
0x18001971b  call    ??$?CV?$CRdpSharedBufEvent@UUMRDP_CREATE_SURFACE_EVENT_EX@@@Umrdp@Avenc@Rdp@@$0A@@?$shared_ptr@V?$CRdpSharedBufEvent@UUMRDP_CREATE_SURFACE_EVENT_EX@@@Umrdp@Avenc@Rdp@@@std@@QEBAPEAV?$CRdpSharedBufEvent@UUMRDP_CREATE_SURFACE_EVENT_EX@@@Umrdp@Avenc@Rdp@@XZ; std::shared_ptr<Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>>::operator-><Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>,0>(void)
0x180019720  mov     rcx, rax
0x180019723  call    ?getHeader@?$CRdpSharedBufEvent@UtagUMRDP_MAP_CURSOR_BUFFER_EVENT@@@Umrdp@Avenc@Rdp@@QEAAPEAUUMRDP_EVENT_HEADER@@XZ; Rdp::Avenc::Umrdp::CRdpSharedBufEvent<tagUMRDP_MAP_CURSOR_BUFFER_EVENT>::getHeader(void)
0x180019728  mov     ebx, [rax]
0x18001972a  call    ?getHeader@?$CRdpSharedBufEvent@UtagUMRDP_MAP_CURSOR_BUFFER_EVENT@@@Umrdp@Avenc@Rdp@@QEAAPEAUUMRDP_EVENT_HEADER@@XZ; Rdp::Avenc::Umrdp::CRdpSharedBufEvent<tagUMRDP_MAP_CURSOR_BUFFER_EVENT>::getHeader(void)
0x18001972f  mov     rdx, rax; unsigned __int8 *
0x180019732  call    ?FreeBuffer@CTSSharedBufferProducer@Modern@Rdp@@QEAAJPEAE@Z; Rdp::Modern::CTSSharedBufferProducer::FreeBuffer(uchar *)
0x180019737  mov     ecx, esi
0x180019739  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18001973e  mov     r9d, eax; char *
0x180019741  mov     rcx, [rsp+58h]; this
0x180019746  mov     dword ptr [rsp+58h+var_30], ebx; char *
0x18001974a  lea     rax, aFailedToCommit; "Failed to commit event %d to shared mem"...
0x180019751  mov     qword ptr [rsp+58h+var_38], rax; int
0x180019756  lea     r8, aOnecoreuapTerm_36; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18001975d  mov     edx, 14Dh; void *
0x180019762  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
