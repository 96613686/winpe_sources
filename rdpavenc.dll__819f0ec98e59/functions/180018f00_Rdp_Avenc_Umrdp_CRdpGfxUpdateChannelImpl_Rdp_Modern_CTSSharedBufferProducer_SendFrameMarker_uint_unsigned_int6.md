# Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::SendFrameMarker(uint,unsigned __int64)

- ea: `0x180018f00`
- end: `0x180019018`
- name: `?SendFrameMarker@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@QEAAXI_K@Z`
- size: `280`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800123a0`
- `0x180020b44`

## callees

- `0x1800080cc`
- `0x18000b07c`
- `0x1800156d0`
- `0x180015ec8`
- `0x180018108`
- `0x1800188e4`
- `0x18001893c`
- `0x180018f00`
- `0x1800199cc`
- `0x180019c04`
- `0x18007d7a4`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180018f61`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180018f61`

## string_xrefs

- `0x180019006`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\umrdpprocessor\updatechannel.cpp`
- `0x180018ffa`: `Failed to commit event %d to shared memory`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
signed __int32 __fastcall Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::SendFrameMarker(
        __int64 a1,
        int a2,
        __int64 a3)
{
  __int64 v6; // rdi
  __int64 v7; // rbx
  int v8; // edi
  signed __int32 result; // eax
  unsigned int v10; // r8d
  const char *v11; // r9
  volatile signed __int32 *v12; // rbx
  __int64 v13; // rax
  int v14; // ebx
  __int64 v15; // rcx
  unsigned __int8 *Header; // rax
  Rdp::Modern::CTSSharedBufferProducer *v17; // rcx
  unsigned int v18; // eax
  char *v19; // [rsp+28h] [rbp-40h]
  __int64 v20; // [rsp+30h] [rbp-38h] BYREF
  volatile signed __int32 *v21; // [rsp+38h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  if ( !*(_BYTE *)(a1 + 144) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::AllocSharedBufEvent<UMRDP_FRAME_MARKER_EVENT>(
    a1,
    &v20);
  v6 = v20;
  v7 = *(_QWORD *)(v20 + 16);
  *(_DWORD *)(v7 + 24) = a2;
  *(_QWORD *)(v7 + 16) = a3;
  *(_QWORD *)(v7 + 28) = Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::GetTimeHNS();
  v8 = Rdp::Modern::CTSSharedBufferProducer::CommitBuffer(
         *(Rdp::Modern::CTSSharedBufferProducer **)(a1 + 104),
         *(unsigned __int8 **)(v6 + 16));
  if ( v8 < 0 )
  {
    v13 = std::shared_ptr<Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>>::operator-><Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>,0>(&v20);
    v14 = *(_DWORD *)Rdp::Avenc::Umrdp::CRdpSharedBufEvent<tagUMRDP_MAP_CURSOR_BUFFER_EVENT>::getHeader(v13);
    Header = (unsigned __int8 *)Rdp::Avenc::Umrdp::CRdpSharedBufEvent<tagUMRDP_MAP_CURSOR_BUFFER_EVENT>::getHeader(v15);
    Rdp::Modern::CTSSharedBufferProducer::FreeBuffer(v17, Header);
    v18 = wil::verify_hresult<long>((unsigned int)v8);
    LODWORD(v19) = v14;
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x14D,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\updatechannel.cpp",
      (const char *)v18,
      (int)"Failed to commit event %d to shared memory",
      v19);
  }
  result = SetEvent(*(HANDLE *)(a1 + 112));
  if ( !result )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v10, v11);
  v12 = v21;
  if ( v21 )
  {
    result = _InterlockedDecrement(v21 + 2);
    if ( !result )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
      result = _InterlockedDecrement(v12 + 3);
      if ( !result )
        return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180018f00  push    rbx
0x180018f02  push    rbp
0x180018f03  push    rsi
0x180018f04  push    rdi
0x180018f05  push    r14
0x180018f07  sub     rsp, 40h
0x180018f0b  mov     rbp, r8
0x180018f0e  mov     r14d, edx
0x180018f11  mov     rsi, rcx
0x180018f14  cmp     byte ptr [rcx+90h], 0
0x180018f1b  jnz     short loc_180018F22
0x180018f1d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180018f22  lea     rdx, [rsp+68h+var_38]
0x180018f27  mov     rcx, rsi
0x180018f2a  call    ??$AllocSharedBufEvent@UUMRDP_FRAME_MARKER_EVENT@@@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@AEAA?AV?$shared_ptr@V?$CRdpSharedBufEvent@UUMRDP_FRAME_MARKER_EVENT@@@Umrdp@Avenc@Rdp@@@std@@W4UMRDP_EVENT_TYPE@@I@Z; Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::AllocSharedBufEvent<UMRDP_FRAME_MARKER_EVENT>(UMRDP_EVENT_TYPE,uint)
0x180018f2f  nop
0x180018f30  mov     rdi, [rsp+68h+var_38]
0x180018f35  mov     rbx, [rdi+10h]
0x180018f39  mov     [rbx+18h], r14d
0x180018f3d  mov     [rbx+10h], rbp
0x180018f41  call    ?GetTimeHNS@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@AEAA_JXZ; Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::GetTimeHNS(void)
0x180018f46  mov     [rbx+1Ch], rax
0x180018f4a  mov     rdx, [rdi+10h]; unsigned __int8 *
0x180018f4e  mov     rcx, [rsi+68h]; this
0x180018f52  call    ?CommitBuffer@CTSSharedBufferProducer@Modern@Rdp@@QEAAJPEAE@Z; Rdp::Modern::CTSSharedBufferProducer::CommitBuffer(uchar *)
0x180018f57  mov     edi, eax
0x180018f59  test    eax, eax
0x180018f5b  js      short loc_180018FC6
0x180018f5d  mov     rcx, [rsi+70h]; hEvent
0x180018f61  call    cs:__imp_SetEvent
0x180018f67  mov     rcx, [rsp+68h]; this
0x180018f6c  test    eax, eax
0x180018f6e  jz      short loc_180018FBB
0x180018f70  mov     rbx, [rsp+68h+var_30]
0x180018f75  test    rbx, rbx
0x180018f78  jz      short loc_180018FB0
0x180018f7a  or      edi, 0FFFFFFFFh
0x180018f7d  mov     eax, edi
0x180018f7f  lock xadd [rbx+8], eax
0x180018f84  add     eax, edi
0x180018f86  jnz     short loc_180018FB0
0x180018f88  mov     rax, [rbx]
0x180018f8b  mov     rcx, rbx
0x180018f8e  mov     rax, [rax]
0x180018f91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f96  mov     eax, edi
0x180018f98  lock xadd [rbx+0Ch], eax
0x180018f9d  add     eax, edi
0x180018f9f  jnz     short loc_180018FB0
0x180018fa1  mov     rax, [rbx]
0x180018fa4  mov     rcx, rbx
0x180018fa7  mov     rax, [rax+8]
0x180018fab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018fb0  add     rsp, 40h
0x180018fb4  pop     r14
0x180018fb6  pop     rdi
0x180018fb7  pop     rsi
0x180018fb8  pop     rbp
0x180018fb9  pop     rbx
0x180018fba  retn
0x180018fbb  mov     edx, 0A01h; void *
0x180018fc0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180018fc6  lea     rcx, [rsp+68h+var_38]
0x180018fcb  call    ??$?CV?$CRdpSharedBufEvent@UUMRDP_CREATE_SURFACE_EVENT_EX@@@Umrdp@Avenc@Rdp@@$0A@@?$shared_ptr@V?$CRdpSharedBufEvent@UUMRDP_CREATE_SURFACE_EVENT_EX@@@Umrdp@Avenc@Rdp@@@std@@QEBAPEAV?$CRdpSharedBufEvent@UUMRDP_CREATE_SURFACE_EVENT_EX@@@Umrdp@Avenc@Rdp@@XZ; std::shared_ptr<Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>>::operator-><Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>,0>(void)
0x180018fd0  mov     rcx, rax
0x180018fd3  call    ?getHeader@?$CRdpSharedBufEvent@UtagUMRDP_MAP_CURSOR_BUFFER_EVENT@@@Umrdp@Avenc@Rdp@@QEAAPEAUUMRDP_EVENT_HEADER@@XZ; Rdp::Avenc::Umrdp::CRdpSharedBufEvent<tagUMRDP_MAP_CURSOR_BUFFER_EVENT>::getHeader(void)
0x180018fd8  mov     ebx, [rax]
0x180018fda  call    ?getHeader@?$CRdpSharedBufEvent@UtagUMRDP_MAP_CURSOR_BUFFER_EVENT@@@Umrdp@Avenc@Rdp@@QEAAPEAUUMRDP_EVENT_HEADER@@XZ; Rdp::Avenc::Umrdp::CRdpSharedBufEvent<tagUMRDP_MAP_CURSOR_BUFFER_EVENT>::getHeader(void)
0x180018fdf  mov     rdx, rax; unsigned __int8 *
0x180018fe2  call    ?FreeBuffer@CTSSharedBufferProducer@Modern@Rdp@@QEAAJPEAE@Z; Rdp::Modern::CTSSharedBufferProducer::FreeBuffer(uchar *)
0x180018fe7  mov     ecx, edi
0x180018fe9  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180018fee  mov     r9d, eax; char *
0x180018ff1  mov     rcx, [rsp+68h]; this
0x180018ff6  mov     dword ptr [rsp+68h+var_40], ebx; char *
0x180018ffa  lea     rax, aFailedToCommit; "Failed to commit event %d to shared mem"...
0x180019001  mov     qword ptr [rsp+68h+var_48], rax; int
0x180019006  lea     r8, aOnecoreuapTerm_36; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18001900d  mov     edx, 14Dh; void *
0x180019012  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
