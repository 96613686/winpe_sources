# Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::SendMonitorLayoutUpdate<std::map<Rdp::Avenc::IMonitorContext *,wil::com_ptr_t<Rdp::Avenc::Umrdp::CMonitorContext,wil::err_exception_policy>,std::less<Rdp::Avenc::IMonitorContext *>,std::allocator<std::pair<Rdp::Avenc::IMonitorContext * const,wil::com_ptr_t<Rdp::Avenc::Umrdp::CMonitorContext,wil::err_exception_policy>>>>>(std::map<Rdp::Avenc::IMonitorContext *,wil::com_ptr_t<Rdp::Avenc::Umrdp::CMonitorContext,wil::err_exception_policy>,std::less<Rdp::Avenc::IMonitorContext *>,std::allocator<std::pair<Rdp::Avenc::IMonitorContext * const,wil::com_ptr_t<Rdp::Avenc::Umrdp::CMonitorContext,wil::err_exception_policy>>>> const &)

- ea: `0x18001709c`
- end: `0x180017333`
- name: `??$SendMonitorLayoutUpdate@V?$map@PEAUIMonitorContext@Avenc@Rdp@@V?$com_ptr_t@VCMonitorContext@Umrdp@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@U?$less@PEAUIMonitorContext@Avenc@Rdp@@@std@@V?$allocator@U?$pair@QEAUIMonitorContext@Avenc@Rdp@@V?$com_ptr_t@VCMonitorContext@Umrdp@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@7@@std@@@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@QEAAXAEBV?$map@PEAUIMonitorContext@Avenc@Rdp@@V?$com_ptr_t@VCMonitorContext@Umrdp@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@U?$less@PEAUIMonitorContext@Avenc@Rdp@@@std@@V?$allocator@U?$pair@QEAUIMonitorContext@Avenc@Rdp@@V?$com_ptr_t@VCMonitorContext@Umrdp@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@7@@std@@@Z`
- size: `663`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180011d40`

## callees

- `0x1800080cc`
- `0x18000b07c`
- `0x1800146bc`
- `0x1800156d0`
- `0x18001669c`
- `0x18001709c`
- `0x180018108`
- `0x1800188e4`
- `0x1800199cc`
- `0x180019c04`
- `0x18007d7a4`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001727c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001727c`

## string_xrefs

- `0x1800170e7`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\umrdpprocessor\updatechannel.cpp`
- `0x180017321`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\umrdpprocessor\updatechannel.cpp`
- `0x180017315`: `Failed to commit event %d to shared memory`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
signed __int32 __fastcall Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::SendMonitorLayoutUpdate<std::map<Rdp::Avenc::IMonitorContext *,wil::com_ptr_t<Rdp::Avenc::Umrdp::CMonitorContext,wil::err_exception_policy>>>(
        __int64 a1,
        __int64 **a2)
{
  __int64 v4; // r11
  __int64 v5; // r8
  __int64 *v6; // rax
  __int64 v7; // rcx
  __int64 v8; // r10
  __int64 v9; // r9
  __int64 v10; // rcx
  BOOL v11; // ecx
  __int64 **v12; // rdx
  __int64 *i; // rcx
  __int64 *j; // rdx
  int v15; // edi
  signed __int32 result; // eax
  unsigned int v17; // r8d
  const char *v18; // r9
  volatile signed __int32 *v19; // rbx
  __int64 v20; // rax
  int v21; // ebx
  __int64 v22; // rcx
  unsigned __int8 *Header; // rax
  Rdp::Modern::CTSSharedBufferProducer *v24; // rcx
  unsigned int v25; // eax
  int v26; // [rsp+20h] [rbp-38h]
  char *v27; // [rsp+28h] [rbp-30h]
  __int64 v28; // [rsp+40h] [rbp-18h] BYREF
  volatile signed __int32 *v29; // [rsp+48h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( !*(_BYTE *)(a1 + 144) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  LOBYTE(v26) = (unsigned __int64)a2[1] > 0x10;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x290,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\updatechannel.cpp",
    (const char *)0x80070057LL,
    v26,
    (bool)"Unsupported number of monitors: %zu",
    (const char *)a2[1]);
  *(_DWORD *)(a1 + 164) = *((_DWORD *)a2 + 2);
  *(_DWORD *)(a1 + 160) = 0;
  Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::AllocSharedBufEvent<UMRDP_UPDATE_MONITORLAYOUT_EVENT>(
    a1,
    &v28);
  v4 = v28;
  v5 = *(_QWORD *)(v28 + 16);
  *(_DWORD *)(v5 + 16) = *((_DWORD *)a2 + 2);
  v6 = (__int64 *)**a2;
  while ( !*((_BYTE *)v6 + 25) )
  {
    v7 = v6[5];
    v8 = *(unsigned int *)(v7 + 128);
    v9 = 5 * v8;
    *(_DWORD *)(v5 + 4 * v9 + 20) = *(_DWORD *)(v7 + 132);
    *(_DWORD *)(v5 + 4 * v9 + 24) = *(_DWORD *)(v6[5] + 136);
    *(_DWORD *)(v5 + 4 * v9 + 28) = *(_DWORD *)(v6[5] + 132) - 1 + *(_DWORD *)(v6[5] + 140);
    *(_DWORD *)(v5 + 4 * v9 + 32) = *(_DWORD *)(v6[5] + 136) - 1 + *(_DWORD *)(v6[5] + 144);
    v10 = v6[5];
    v11 = !*(_DWORD *)(v10 + 132) && !*(_DWORD *)(v10 + 136);
    *(_DWORD *)(v5 + 20 * v8 + 36) = v11;
    *(_DWORD *)(v5 + 20 * v8 + 340) = *(_DWORD *)(v6[5] + 152);
    *(_DWORD *)(v5 + 20 * v8 + 344) = *(_DWORD *)(v6[5] + 156);
    *(_DWORD *)(v5 + 20 * v8 + 348) = *(_DWORD *)(v6[5] + 160);
    *(_DWORD *)(v5 + 20 * v8 + 352) = *(_DWORD *)(v6[5] + 164);
    *(_DWORD *)(v5 + 20 * v8 + 356) = *(_DWORD *)(v6[5] + 168);
    v12 = (__int64 **)v6[2];
    if ( *((_BYTE *)v12 + 25) )
    {
      for ( i = (__int64 *)v6[1]; !*((_BYTE *)i + 25) && v6 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v6 = i;
      v6 = i;
    }
    else
    {
      v6 = (__int64 *)v6[2];
      for ( j = *v12; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v6 = j;
    }
  }
  v15 = Rdp::Modern::CTSSharedBufferProducer::CommitBuffer(
          *(Rdp::Modern::CTSSharedBufferProducer **)(a1 + 104),
          *(unsigned __int8 **)(v4 + 16));
  if ( v15 < 0 )
  {
    v20 = std::shared_ptr<Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>>::operator-><Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>,0>(&v28);
    v21 = *(_DWORD *)Rdp::Avenc::Umrdp::CRdpSharedBufEvent<tagUMRDP_MAP_CURSOR_BUFFER_EVENT>::getHeader(v20);
    Header = (unsigned __int8 *)Rdp::Avenc::Umrdp::CRdpSharedBufEvent<tagUMRDP_MAP_CURSOR_BUFFER_EVENT>::getHeader(v22);
    Rdp::Modern::CTSSharedBufferProducer::FreeBuffer(v24, Header);
    v25 = wil::verify_hresult<long>((unsigned int)v15);
    LODWORD(v27) = v21;
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x14D,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\updatechannel.cpp",
      (const char *)v25,
      (int)"Failed to commit event %d to shared memory",
      v27);
  }
  result = SetEvent(*(HANDLE *)(a1 + 112));
  if ( !result )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v17, v18);
  v19 = v29;
  if ( v29 )
  {
    result = _InterlockedDecrement(v29 + 2);
    if ( !result )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
      result = _InterlockedDecrement(v19 + 3);
      if ( !result )
        return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001709c  mov     [rsp+arg_0], rbx
0x1800170a1  push    rdi
0x1800170a2  sub     rsp, 50h
0x1800170a6  mov     rdi, rdx
0x1800170a9  mov     rbx, rcx
0x1800170ac  cmp     byte ptr [rcx+90h], 0
0x1800170b3  jnz     short loc_1800170BA
0x1800170b5  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800170ba  mov     rax, [rdi+8]
0x1800170be  cmp     rax, 10h
0x1800170c2  setnbe  r8b
0x1800170c6  mov     rcx, [rsp+58h]; this
0x1800170cb  mov     [rsp+58h+var_28], rax; char *
0x1800170d0  lea     rax, aUnsupportedNum; "Unsupported number of monitors: %zu"
0x1800170d7  mov     [rsp+58h+var_30], rax; bool
0x1800170dc  mov     byte ptr [rsp+58h+var_38], r8b; int
0x1800170e1  mov     r9d, 80070057h; char *
0x1800170e7  lea     r8, aOnecoreuapTerm_36; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x1800170ee  mov     edx, 290h; void *
0x1800170f3  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1800170f8  mov     eax, [rdi+8]
0x1800170fb  mov     [rbx+0A4h], eax
0x180017101  mov     dword ptr [rbx+0A0h], 0
0x18001710b  lea     rdx, [rsp+58h+var_18]
0x180017110  mov     rcx, rbx
0x180017113  call    ??$AllocSharedBufEvent@UUMRDP_UPDATE_MONITORLAYOUT_EVENT@@@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@AEAA?AV?$shared_ptr@V?$CRdpSharedBufEvent@UUMRDP_UPDATE_MONITORLAYOUT_EVENT@@@Umrdp@Avenc@Rdp@@@std@@W4UMRDP_EVENT_TYPE@@I@Z; Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::AllocSharedBufEvent<UMRDP_UPDATE_MONITORLAYOUT_EVENT>(UMRDP_EVENT_TYPE,uint)
0x180017118  nop
0x180017119  mov     r11, [rsp+58h+var_18]
0x18001711e  mov     r8, [r11+10h]
0x180017122  mov     eax, [rdi+8]
0x180017125  mov     [r8+10h], eax
0x180017129  mov     rax, [rdi]
0x18001712c  mov     rax, [rax]
0x18001712f  cmp     byte ptr [rax+19h], 0
0x180017133  jnz     loc_180017265
0x180017139  mov     rcx, [rax+28h]
0x18001713d  mov     r10d, [rcx+80h]
0x180017144  lea     r9, [r10+r10*4]
0x180017148  mov     ecx, [rcx+84h]
0x18001714e  mov     [r8+r9*4+14h], ecx
0x180017153  mov     rcx, [rax+28h]
0x180017157  mov     edx, [rcx+88h]
0x18001715d  mov     [r8+r9*4+18h], edx
0x180017162  mov     rcx, [rax+28h]
0x180017166  mov     edx, [rcx+8Ch]
0x18001716c  mov     ecx, [rcx+84h]
0x180017172  dec     ecx
0x180017174  add     edx, ecx
0x180017176  mov     [r8+r9*4+1Ch], edx
0x18001717b  mov     rcx, [rax+28h]
0x18001717f  mov     edx, [rcx+90h]
0x180017185  mov     ecx, [rcx+88h]
0x18001718b  dec     ecx
0x18001718d  add     edx, ecx
0x18001718f  mov     [r8+r9*4+20h], edx
0x180017194  mov     rcx, [rax+28h]
0x180017198  cmp     dword ptr [rcx+84h], 0
0x18001719f  jnz     short loc_1800171B1
0x1800171a1  cmp     dword ptr [rcx+88h], 0
0x1800171a8  jnz     short loc_1800171B1
0x1800171aa  mov     ecx, 1
0x1800171af  jmp     short loc_1800171B3
0x1800171b1  xor     ecx, ecx
0x1800171b3  mov     [r8+r9*4+24h], ecx
0x1800171b8  mov     rcx, [rax+28h]
0x1800171bc  lea     rdx, [r10+r10*4]
0x1800171c0  mov     ecx, [rcx+98h]
0x1800171c6  mov     [r8+rdx*4+154h], ecx
0x1800171ce  mov     rcx, [rax+28h]
0x1800171d2  mov     edx, [rcx+9Ch]
0x1800171d8  mov     [r8+r9*4+158h], edx
0x1800171e0  mov     rcx, [rax+28h]
0x1800171e4  mov     edx, [rcx+0A0h]
0x1800171ea  mov     [r8+r9*4+15Ch], edx
0x1800171f2  mov     rcx, [rax+28h]
0x1800171f6  mov     edx, [rcx+0A4h]
0x1800171fc  mov     [r8+r9*4+160h], edx
0x180017204  mov     rcx, [rax+28h]
0x180017208  mov     edx, [rcx+0A8h]
0x18001720e  mov     [r8+r9*4+164h], edx
0x180017216  mov     rdx, [rax+10h]
0x18001721a  cmp     byte ptr [rdx+19h], 0
0x18001721e  jz      short loc_180017241
0x180017220  mov     rcx, [rax+8]
0x180017224  jmp     short loc_180017233
0x180017226  cmp     rax, [rcx+10h]
0x18001722a  jnz     short loc_180017239
0x18001722c  mov     rax, rcx
0x18001722f  mov     rcx, [rcx+8]
0x180017233  cmp     byte ptr [rcx+19h], 0
0x180017237  jz      short loc_180017226
0x180017239  mov     rax, rcx
0x18001723c  jmp     loc_18001712F
0x180017241  mov     rax, rdx
0x180017244  mov     rdx, [rdx]
0x180017247  cmp     byte ptr [rdx+19h], 0
0x18001724b  jnz     loc_18001712F
0x180017251  mov     rax, rdx
0x180017254  mov     rcx, [rdx]
0x180017257  mov     rdx, rcx
0x18001725a  cmp     byte ptr [rcx+19h], 0
0x18001725e  jz      short loc_180017251
0x180017260  jmp     loc_18001712F
0x180017265  mov     rdx, [r11+10h]; unsigned __int8 *
0x180017269  mov     rcx, [rbx+68h]; this
0x18001726d  call    ?CommitBuffer@CTSSharedBufferProducer@Modern@Rdp@@QEAAJPEAE@Z; Rdp::Modern::CTSSharedBufferProducer::CommitBuffer(uchar *)
0x180017272  mov     edi, eax
0x180017274  test    eax, eax
0x180017276  js      short loc_1800172E1
0x180017278  mov     rcx, [rbx+70h]; hEvent
0x18001727c  call    cs:__imp_SetEvent
0x180017282  mov     rcx, [rsp+58h]; this
0x180017287  test    eax, eax
0x180017289  jz      short loc_1800172D6
0x18001728b  mov     rbx, [rsp+58h+var_10]
0x180017290  test    rbx, rbx
0x180017293  jz      short loc_1800172CB
0x180017295  or      edi, 0FFFFFFFFh
0x180017298  mov     eax, edi
0x18001729a  lock xadd [rbx+8], eax
0x18001729f  add     eax, edi
0x1800172a1  jnz     short loc_1800172CB
0x1800172a3  mov     rax, [rbx]
0x1800172a6  mov     rcx, rbx
0x1800172a9  mov     rax, [rax]
0x1800172ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800172b1  mov     eax, edi
0x1800172b3  lock xadd [rbx+0Ch], eax
0x1800172b8  add     eax, edi
0x1800172ba  jnz     short loc_1800172CB
0x1800172bc  mov     rax, [rbx]
0x1800172bf  mov     rcx, rbx
0x1800172c2  mov     rax, [rax+8]
0x1800172c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800172cb  mov     rbx, [rsp+58h+arg_0]
0x1800172d0  add     rsp, 50h
0x1800172d4  pop     rdi
0x1800172d5  retn
0x1800172d6  mov     edx, 0A01h; void *
0x1800172db  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800172e1  lea     rcx, [rsp+58h+var_18]
0x1800172e6  call    ??$?CV?$CRdpSharedBufEvent@UUMRDP_CREATE_SURFACE_EVENT_EX@@@Umrdp@Avenc@Rdp@@$0A@@?$shared_ptr@V?$CRdpSharedBufEvent@UUMRDP_CREATE_SURFACE_EVENT_EX@@@Umrdp@Avenc@Rdp@@@std@@QEBAPEAV?$CRdpSharedBufEvent@UUMRDP_CREATE_SURFACE_EVENT_EX@@@Umrdp@Avenc@Rdp@@XZ; std::shared_ptr<Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>>::operator-><Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>,0>(void)
0x1800172eb  mov     rcx, rax
0x1800172ee  call    ?getHeader@?$CRdpSharedBufEvent@UtagUMRDP_MAP_CURSOR_BUFFER_EVENT@@@Umrdp@Avenc@Rdp@@QEAAPEAUUMRDP_EVENT_HEADER@@XZ; Rdp::Avenc::Umrdp::CRdpSharedBufEvent<tagUMRDP_MAP_CURSOR_BUFFER_EVENT>::getHeader(void)
0x1800172f3  mov     ebx, [rax]
0x1800172f5  call    ?getHeader@?$CRdpSharedBufEvent@UtagUMRDP_MAP_CURSOR_BUFFER_EVENT@@@Umrdp@Avenc@Rdp@@QEAAPEAUUMRDP_EVENT_HEADER@@XZ; Rdp::Avenc::Umrdp::CRdpSharedBufEvent<tagUMRDP_MAP_CURSOR_BUFFER_EVENT>::getHeader(void)
0x1800172fa  mov     rdx, rax; unsigned __int8 *
0x1800172fd  call    ?FreeBuffer@CTSSharedBufferProducer@Modern@Rdp@@QEAAJPEAE@Z; Rdp::Modern::CTSSharedBufferProducer::FreeBuffer(uchar *)
0x180017302  mov     ecx, edi
0x180017304  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180017309  mov     r9d, eax; char *
0x18001730c  mov     rcx, [rsp+58h]; this
0x180017311  mov     dword ptr [rsp+58h+var_30], ebx; char *
0x180017315  lea     rax, aFailedToCommit; "Failed to commit event %d to shared mem"...
0x18001731c  mov     qword ptr [rsp+58h+var_38], rax; int
0x180017321  lea     r8, aOnecoreuapTerm_36; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180017328  mov     edx, 14Dh; void *
0x18001732d  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
