# Microsoft::Basix::Dct::ICECore::LinkContextRemoved(std::shared_ptr<Microsoft::Basix::Dct::IChannel>)

- ea: `0x18022f760`
- end: `0x180230057`
- name: `?LinkContextRemoved@ICECore@Dct@Basix@Microsoft@@QEAAXV?$shared_ptr@VIChannel@Dct@Basix@Microsoft@@@std@@@Z`
- size: `2295`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x1800fd9a0`

## callees

- `0x18000d9c0`
- `0x180015bb8`
- `0x180017380`
- `0x180018b94`
- `0x18001902c`
- `0x1800191b4`
- `0x18001db78`
- `0x180024760`
- `0x1800c3bc8`
- `0x1800c408c`
- `0x1800f30dc`
- `0x1801a5dc8`
- `0x180203c08`
- `0x18020b6b8`
- `0x18021b170`
- `0x18021b1e8`
- `0x18021fe58`
- `0x18022f760`
- `0x18023d500`
- `0x18032f050`
- `0x18032f0b0`
- `0x180375c40`

## string_xrefs

- `0x18022f7ee`: `CheckPoint.ICELinkContextRemoved(): context=%p`
- `0x18022f909`: `LinkContextRemoved: context = %p. duplicate state change! ignore`
- `0x18022fa89`: `CheckPoint.ICELinkContextRemoved(): context=%p, final dor after adjustment:%d`
- `0x18022fb7a`: `CheckPoint.ICELinkContextRemoved(): start clone to compensate for the reduction of DoR: m_degreeOfRedundency=%d, m_targetDoR=%d`
- `0x18022fe1d`: `New Clones due to link removal`

## pseudocode

```c
// Hidden C++ exception states: #wind=34
void __fastcall Microsoft::Basix::Dct::ICECore::LinkContextRemoved(__int64 a1, _QWORD *a2)
{
  __int64 v4; // rbx
  volatile signed __int32 *v5; // rbx
  __int64 v6; // rdi
  __int32 v7; // ebx
  __int64 v8; // rbx
  volatile signed __int32 *v9; // rbx
  Microsoft::Basix::Dct::ICE::Candidate *v10; // rcx
  Microsoft::Basix::Dct::ICE::Candidate *v11; // rcx
  volatile signed __int32 *v12; // rbx
  int v13; // r9d
  int v14; // ebx
  __int64 v15; // rdi
  volatile signed __int32 *v16; // rbx
  int v17; // r9d
  int v18; // ebx
  int v19; // edi
  volatile signed __int32 *v20; // rbx
  __int64 v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int64 v24; // rdx
  __int64 v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // rdx
  volatile signed __int32 *v29; // rbx
  volatile signed __int32 *v30; // rbx
  volatile signed __int32 *v31; // rbx
  volatile signed __int32 *v32; // rbx
  char v33; // [rsp+40h] [rbp-C0h]
  _OWORD v34[2]; // [rsp+48h] [rbp-B8h] BYREF
  _OWORD v35[2]; // [rsp+68h] [rbp-98h] BYREF
  _OWORD v36[2]; // [rsp+88h] [rbp-78h] BYREF
  _OWORD v37[2]; // [rsp+A8h] [rbp-58h] BYREF
  _OWORD v38[2]; // [rsp+C8h] [rbp-38h] BYREF
  _OWORD v39[2]; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD *v40; // [rsp+108h] [rbp+8h]
  __int64 v41[4]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v42[4]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v43[32]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v44[32]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v45[32]; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v46[32]; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v47[32]; // [rsp+1D0h] [rbp+D0h] BYREF
  _BYTE v48[32]; // [rsp+1F0h] [rbp+F0h] BYREF
  _BYTE v49[32]; // [rsp+210h] [rbp+110h] BYREF
  _BYTE v50[32]; // [rsp+230h] [rbp+130h] BYREF
  _OWORD v51[2]; // [rsp+250h] [rbp+150h] BYREF
  int v52[4]; // [rsp+270h] [rbp+170h] BYREF
  __int128 v53; // [rsp+280h] [rbp+180h]
  __int64 *v54; // [rsp+290h] [rbp+190h] BYREF

  v40 = a2;
  if ( !*a2 )
    goto LABEL_59;
  v51[0] = 0;
  Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v51);
  if ( *(_QWORD *)&v51[0] && *(_BYTE *)(*(_QWORD *)&v51[0] + 128LL) )
  {
    v4 = *a2;
    memset(v34, 0, sizeof(v34));
    std::string::_Construct<1,char const *>(v34, "CheckPoint.ICELinkContextRemoved(): context=%p", (const void *)0x2E);
    Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,Microsoft::Basix::Dct::ISmilesLink *>(
      v51,
      "BASIX_DCT",
      v34,
      v4);
    std::string::_Tidy_deallocate(v34);
  }
  v5 = (volatile signed __int32 *)*((_QWORD *)&v51[0] + 1);
  if ( *((_QWORD *)&v51[0] + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v51[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v5)(v5);
      if ( _InterlockedExchangeAdd(v5 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
    }
  }
  v34[0] = 0;
  std::dynamic_pointer_cast<Microsoft::Basix::Dct::ICECore::LinkContext,Microsoft::Basix::Dct::IChannel>(v34);
  v6 = *(_QWORD *)&v34[0];
  if ( *(_QWORD *)&v34[0] )
  {
    LODWORD(v54) = 2;
    v7 = ((__int64 (__fastcall *)(__int64 **))boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data4)(&v54);
    if ( _InterlockedExchange(
           (volatile __int32 *)(*(__int64 (__fastcall **)(__int64))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)(v6 + 1508),
           v7) == 2 )
    {
      v51[0] = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(v51);
      if ( *(_QWORD *)&v51[0] && *(_BYTE *)(*(_QWORD *)&v51[0] + 128LL) )
      {
        v8 = *a2;
        *(_OWORD *)v52 = 0;
        v53 = 0;
        std::string::_Construct<1,char const *>(
          v52,
          "LinkContextRemoved: context = %p. duplicate state change! ignore",
          (const void *)0x40);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,Microsoft::Basix::Dct::detail::BasicStateManagement *>(
          v51,
          "BASIX_DCT",
          v52,
          v8);
        std::string::_Tidy_deallocate(v52);
      }
      v9 = (volatile signed __int32 *)*((_QWORD *)&v51[0] + 1);
      if ( *((_QWORD *)&v51[0] + 1) )
      {
        if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v51[0] + 1) + 8LL)) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
          if ( !_InterlockedDecrement(v9 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
        }
      }
      goto LABEL_55;
    }
    v10 = *(Microsoft::Basix::Dct::ICE::Candidate **)(v6 + 1408);
    if ( *(_DWORD *)(*(_QWORD *)(v6 + 1392) + 228LL) == 3 )
      Microsoft::Basix::Dct::ICE::Candidate::AdjustRelayLink(v10, -1);
    else
      Microsoft::Basix::Dct::ICE::Candidate::AdjustNonRelayLink(v10, -1);
    v11 = *(Microsoft::Basix::Dct::ICE::Candidate **)(v6 + 1392);
    if ( *(_DWORD *)(*(_QWORD *)(v6 + 1408) + 228LL) == 3 )
      Microsoft::Basix::Dct::ICE::Candidate::AdjustRelayLink(v11, -1);
    else
      Microsoft::Basix::Dct::ICE::Candidate::AdjustNonRelayLink(v11, -1);
    Microsoft::Basix::Dct::ICECore::ComputeDegreeOfRedundency(a1, v52);
    v12 = *(volatile signed __int32 **)&v52[2];
    if ( *(_QWORD *)&v52[2] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v52[2] + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
        if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
      }
    }
    v51[0] = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v51);
    if ( *(_QWORD *)&v51[0] && *(_BYTE *)(*(_QWORD *)&v51[0] + 128LL) )
    {
      v14 = *(_DWORD *)(a1 + 9060);
      v15 = *a2;
      *(_OWORD *)v52 = 0;
      v53 = 0;
      std::string::_Construct<1,char const *>(
        v52,
        "CheckPoint.ICELinkContextRemoved(): context=%p, final dor after adjustment:%d",
        (const void *)0x4D,
        v13);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,Microsoft::Basix::Dct::IChannel *,unsigned int>(
        (unsigned int)v51,
        (unsigned int)"BASIX_DCT",
        (unsigned int)v52,
        v15,
        v14);
      std::string::_Tidy_deallocate(v52);
    }
    v16 = (volatile signed __int32 *)*((_QWORD *)&v51[0] + 1);
    if ( *((_QWORD *)&v51[0] + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v51[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
        if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
      }
    }
    if ( *(_DWORD *)(a1 + 9060) < *(_DWORD *)(a1 + 9068) )
    {
      v51[0] = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v51);
      if ( *(_QWORD *)&v51[0] && *(_BYTE *)(*(_QWORD *)&v51[0] + 128LL) )
      {
        v18 = *(_DWORD *)(a1 + 9068);
        v19 = *(_DWORD *)(a1 + 9060);
        *(_OWORD *)v52 = 0;
        v53 = 0;
        std::string::_Construct<1,char const *>(
          v52,
          "CheckPoint.ICELinkContextRemoved(): start clone to compensate for the reduction of DoR: m_degreeOfRedundency=%"
          "d, m_targetDoR=%d",
          127,
          v17);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,unsigned int,unsigned int>(
          (unsigned int)v51,
          (unsigned int)"BASIX_DCT",
          (unsigned int)v52,
          v19,
          v18);
        std::string::_Tidy_deallocate(v52);
      }
      v20 = (volatile signed __int32 *)*((_QWORD *)&v51[0] + 1);
      if ( *((_QWORD *)&v51[0] + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v51[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
          if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
        }
      }
      *(_OWORD *)v52 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v52);
      if ( *(_QWORD *)v52 && *(_BYTE *)(*(_QWORD *)v52 + 128LL) )
      {
        v54 = v41;
        std::_Integral_to_string<char,unsigned int>(v48, *(unsigned int *)(a1 + 9068));
        memset(v39, 0, sizeof(v39));
        std::string::_Construct<1,char const *>(v39, ":", 1);
        memset(v38, 0, sizeof(v38));
        std::string::_Construct<1,char const *>(v38, "\"", 1);
        memset(v37, 0, sizeof(v37));
        std::string::_Construct<1,char const *>(v37, "\"", 1);
        v21 = std::operator+<char>(v50, v37, "IceTargetDoR");
        LOBYTE(v22) = v33;
        std::string::string(v47, v22, v21, v38);
        LOBYTE(v23) = v33;
        std::string::string(v46, v23, v47, v39);
        LOBYTE(v24) = v33;
        std::string::string(v41, v24, v46, v48);
        std::_Integral_to_string<char,unsigned int>(v45, *(unsigned int *)(a1 + 9060));
        memset(v36, 0, sizeof(v36));
        std::string::_Construct<1,char const *>(v36, ":", 1);
        memset(v51, 0, sizeof(v51));
        std::string::_Construct<1,char const *>(v51, "\"", 1);
        memset(v35, 0, sizeof(v35));
        std::string::_Construct<1,char const *>(v35, "\"", 1);
        v25 = std::operator+<char>(v49, v35, "IceDoR");
        LOBYTE(v26) = v33;
        std::string::string(v44, v26, v25, v51);
        LOBYTE(v27) = v33;
        std::string::string(v43, v27, v44, v36);
        LOBYTE(v28) = v33;
        std::string::string(v42, v28, v43, v45);
        Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string,std::string>(
          (int)v52,
          (int)"RD_CHECKPOINT",
          0,
          (int)"ICECore",
          "Clone",
          "New Clones due to link removal",
          (__int64)v42,
          (__int64)v41);
        std::string::_Tidy_deallocate(v43);
        std::string::_Tidy_deallocate(v44);
        std::string::_Tidy_deallocate(v49);
        std::string::_Tidy_deallocate(v35);
        std::string::_Tidy_deallocate(v51);
        std::string::_Tidy_deallocate(v36);
        std::string::_Tidy_deallocate(v45);
        std::string::_Tidy_deallocate(v46);
        std::string::_Tidy_deallocate(v47);
        std::string::_Tidy_deallocate(v50);
        std::string::_Tidy_deallocate(v37);
        std::string::_Tidy_deallocate(v38);
        std::string::_Tidy_deallocate(v39);
        std::string::_Tidy_deallocate(v48);
      }
      v29 = *(volatile signed __int32 **)&v52[2];
      if ( *(_QWORD *)&v52[2] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v52[2] + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v29)(v29);
          if ( _InterlockedExchangeAdd(v29 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29 + 8LL))(v29);
        }
      }
      *(_OWORD *)v52 = 0;
      Microsoft::Basix::Dct::ICECore::ScheduleClone(a1, v52);
      v30 = *(volatile signed __int32 **)&v52[2];
      if ( *(_QWORD *)&v52[2] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v52[2] + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v30)(v30);
          if ( _InterlockedExchangeAdd(v30 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v30 + 8LL))(v30);
        }
      }
    }
  }
  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 16LL))(*a2);
LABEL_55:
  v31 = (volatile signed __int32 *)*((_QWORD *)&v34[0] + 1);
  if ( *((_QWORD *)&v34[0] + 1) )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v34[0] + 1) + 8LL)) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v31)(v31);
      if ( !_InterlockedDecrement(v31 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v31 + 8LL))(v31);
    }
  }
LABEL_59:
  v32 = (volatile signed __int32 *)a2[1];
  if ( v32 && !_InterlockedDecrement(v32 + 2) )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v32)(v32);
    if ( !_InterlockedDecrement(v32 + 3) )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v32 + 8LL))(v32);
  }
}

```

## disassembly

```asm
0x18022f760  mov     [rsp-8+arg_10], rbx
0x18022f765  push    rbp
0x18022f766  push    rsi
0x18022f767  push    rdi
0x18022f768  push    r14
0x18022f76a  push    r15
0x18022f76c  lea     rbp, [rsp-1A0h]
0x18022f774  mov     eax, 2A0h
0x18022f779  call    _alloca_probe
0x18022f77e  sub     rsp, rax
0x18022f781  mov     rax, cs:__security_cookie
0x18022f788  xor     rax, rsp
0x18022f78b  mov     [rbp+1C0h+var_28], rax
0x18022f792  mov     rsi, rdx
0x18022f795  mov     r14, rcx
0x18022f798  mov     [rbp+1C0h+var_1B8], rdx
0x18022f79c  or      r15d, 0FFFFFFFFh
0x18022f7a0  cmp     qword ptr [rdx], 0
0x18022f7a4  jz      loc_18022FFEF
0x18022f7aa  xorps   xmm0, xmm0
0x18022f7ad  movups  [rbp+1C0h+var_70], xmm0
0x18022f7b4  lea     rcx, [rbp+1C0h+var_70]
0x18022f7bb  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x18022f7c0  nop
0x18022f7c1  mov     rax, qword ptr [rbp+1C0h+var_70]
0x18022f7c8  test    rax, rax
0x18022f7cb  jz      short loc_18022F827
0x18022f7cd  cmp     byte ptr [rax+80h], 0
0x18022f7d4  jz      short loc_18022F827
0x18022f7d6  mov     rbx, [rsi]
0x18022f7d9  xorps   xmm0, xmm0
0x18022f7dc  movups  [rsp+2C0h+var_278], xmm0
0x18022f7e1  xorps   xmm1, xmm1
0x18022f7e4  movdqu  [rsp+2C0h+var_268], xmm1
0x18022f7ea  lea     r8d, [r15+2Fh]
0x18022f7ee  lea     rdx, aCheckpointIcel_1; "CheckPoint.ICELinkContextRemoved(): con"...
0x18022f7f5  lea     rcx, [rsp+2C0h+var_278]
0x18022f7fa  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18022f7ff  nop
0x18022f800  mov     r9, rbx
0x18022f803  lea     r8, [rsp+2C0h+var_278]
0x18022f808  lea     rdx, aBasixDct; "BASIX_DCT"
0x18022f80f  lea     rcx, [rbp+1C0h+var_70]
0x18022f816  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@PEAVISmilesLink@Dct@23@@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@PEAVISmilesLink@Dct@23@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,Microsoft::Basix::Dct::ISmilesLink *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &,Microsoft::Basix::Dct::ISmilesLink *)
0x18022f81b  nop
0x18022f81c  lea     rcx, [rsp+2C0h+var_278]
0x18022f821  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18022f826  nop
0x18022f827  mov     rbx, qword ptr [rbp+1C0h+var_70+8]
0x18022f82e  test    rbx, rbx
0x18022f831  jz      short loc_18022F86C
0x18022f833  mov     eax, r15d
0x18022f836  lock xadd [rbx+8], eax
0x18022f83b  add     eax, r15d
0x18022f83e  jnz     short loc_18022F86C
0x18022f840  mov     rax, [rbx]
0x18022f843  mov     rcx, rbx
0x18022f846  mov     rax, [rax]
0x18022f849  call    cs:__guard_dispatch_icall_fptr
0x18022f84f  mov     eax, r15d
0x18022f852  lock xadd [rbx+0Ch], eax
0x18022f857  add     eax, r15d
0x18022f85a  jnz     short loc_18022F86C
0x18022f85c  mov     rax, [rbx]
0x18022f85f  mov     rcx, rbx
0x18022f862  mov     rax, [rax+8]
0x18022f866  call    cs:__guard_dispatch_icall_fptr
0x18022f86c  xorps   xmm0, xmm0
0x18022f86f  movups  [rsp+2C0h+var_278], xmm0
0x18022f874  mov     rdx, rsi
0x18022f877  lea     rcx, [rsp+2C0h+var_278]
0x18022f87c  call    ??$dynamic_pointer_cast@VLinkContext@ICECore@Dct@Basix@Microsoft@@VIChannel@345@@std@@YA?AV?$shared_ptr@VLinkContext@ICECore@Dct@Basix@Microsoft@@@0@AEBV?$shared_ptr@VIChannel@Dct@Basix@Microsoft@@@0@@Z; std::dynamic_pointer_cast<Microsoft::Basix::Dct::ICECore::LinkContext,Microsoft::Basix::Dct::IChannel>(std::shared_ptr<Microsoft::Basix::Dct::IChannel> const &)
0x18022f881  nop
0x18022f882  mov     rdi, qword ptr [rsp+2C0h+var_278]
0x18022f887  test    rdi, rdi
0x18022f88a  jz      loc_18022FF9A
0x18022f890  mov     dword ptr [rbp+1C0h+var_30], 2
0x18022f89a  lea     rcx, [rbp+1C0h+var_30]
0x18022f8a1  call    near ptr ??$launder@USecurityCookieHash@RdpNano@Microsoft@@@core@boost@@YAPEAUSecurityCookieHash@RdpNano@Microsoft@@PEAU234@@Z.Data4; boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>(Microsoft::RdpNano::SecurityCookieHash *)
0x18022f8a6  mov     ebx, eax
0x18022f8a8  lea     rcx, [rdi+5E4h]
0x18022f8af  call    near ptr ??$launder@USecurityCookieHash@RdpNano@Microsoft@@@core@boost@@YAPEAUSecurityCookieHash@RdpNano@Microsoft@@PEAU234@@Z.Data1; boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>(Microsoft::RdpNano::SecurityCookieHash *)
0x18022f8b4  xchg    ebx, [rax]
0x18022f8b6  cmp     ebx, 2
0x18022f8b9  jnz     loc_18022F998
0x18022f8bf  xorps   xmm0, xmm0
0x18022f8c2  movups  [rbp+1C0h+var_70], xmm0
0x18022f8c9  lea     rcx, [rbp+1C0h+var_70]
0x18022f8d0  call    ??$SelectEvent@VTraceWarning@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(void)
0x18022f8d5  nop
0x18022f8d6  mov     rax, qword ptr [rbp+1C0h+var_70]
0x18022f8dd  test    rax, rax
0x18022f8e0  jz      short loc_18022F948
0x18022f8e2  cmp     byte ptr [rax+80h], 0
0x18022f8e9  jz      short loc_18022F948
0x18022f8eb  mov     rbx, [rsi]
0x18022f8ee  xorps   xmm0, xmm0
0x18022f8f1  movups  xmmword ptr [rbp+1C0h+var_50], xmm0
0x18022f8f8  xorps   xmm1, xmm1
0x18022f8fb  movdqu  [rbp+1C0h+var_40], xmm1
0x18022f903  mov     r8d, 40h ; '@'
0x18022f909  lea     rdx, aLinkcontextrem; "LinkContextRemoved: context = %p. dupli"...
0x18022f910  lea     rcx, [rbp+1C0h+var_50]
0x18022f917  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18022f91c  nop
0x18022f91d  mov     r9, rbx
0x18022f920  lea     r8, [rbp+1C0h+var_50]
0x18022f927  lea     rdx, aBasixDct; "BASIX_DCT"
0x18022f92e  lea     rcx, [rbp+1C0h+var_70]
0x18022f935  call    ??$TraceMessage@VTraceWarning@Basix@Microsoft@@PEAVBasicStateManagement@detail@Dct@23@@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@PEAVBasicStateManagement@detail@Dct@23@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,Microsoft::Basix::Dct::detail::BasicStateManagement *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>> const &,char const *,std::string const &,Microsoft::Basix::Dct::detail::BasicStateManagement *)
0x18022f93a  nop
0x18022f93b  lea     rcx, [rbp+1C0h+var_50]
0x18022f942  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18022f947  nop
0x18022f948  mov     rbx, qword ptr [rbp+1C0h+var_70+8]
0x18022f94f  test    rbx, rbx
0x18022f952  jz      loc_18022FFAB
0x18022f958  mov     eax, r15d
0x18022f95b  lock xadd [rbx+8], eax
0x18022f960  add     eax, r15d
0x18022f963  jnz     loc_18022FFAB
0x18022f969  mov     rax, [rbx]
0x18022f96c  mov     rcx, rbx
0x18022f96f  mov     rax, [rax]
0x18022f972  call    cs:__guard_dispatch_icall_fptr
0x18022f978  mov     eax, r15d
0x18022f97b  lock xadd [rbx+0Ch], eax
0x18022f980  add     eax, r15d
0x18022f983  jnz     loc_18022FFAB
0x18022f989  mov     rax, [rbx]
0x18022f98c  mov     rcx, rbx
0x18022f98f  mov     rax, [rax+8]
0x18022f993  jmp     loc_18022FFA4
0x18022f998  mov     rcx, [rdi+580h]; this
0x18022f99f  mov     rax, [rdi+570h]
0x18022f9a6  mov     edx, r15d; int
0x18022f9a9  cmp     dword ptr [rax+0E4h], 3
0x18022f9b0  jnz     short loc_18022F9B9
0x18022f9b2  call    ?AdjustRelayLink@Candidate@ICE@Dct@Basix@Microsoft@@QEAAIH@Z; Microsoft::Basix::Dct::ICE::Candidate::AdjustRelayLink(int)
0x18022f9b7  jmp     short loc_18022F9BE
0x18022f9b9  call    ?AdjustNonRelayLink@Candidate@ICE@Dct@Basix@Microsoft@@QEAAIH@Z; Microsoft::Basix::Dct::ICE::Candidate::AdjustNonRelayLink(int)
0x18022f9be  mov     rcx, [rdi+570h]; this
0x18022f9c5  mov     rax, [rdi+580h]
0x18022f9cc  mov     edx, r15d; int
0x18022f9cf  cmp     dword ptr [rax+0E4h], 3
0x18022f9d6  jnz     short loc_18022F9DF
0x18022f9d8  call    ?AdjustRelayLink@Candidate@ICE@Dct@Basix@Microsoft@@QEAAIH@Z; Microsoft::Basix::Dct::ICE::Candidate::AdjustRelayLink(int)
0x18022f9dd  jmp     short loc_18022F9E4
0x18022f9df  call    ?AdjustNonRelayLink@Candidate@ICE@Dct@Basix@Microsoft@@QEAAIH@Z; Microsoft::Basix::Dct::ICE::Candidate::AdjustNonRelayLink(int)
0x18022f9e4  lea     rdx, [rbp+1C0h+var_50]
0x18022f9eb  mov     rcx, r14
0x18022f9ee  call    ?ComputeDegreeOfRedundency@ICECore@Dct@Basix@Microsoft@@QEAA?AV?$shared_ptr@VTurnServer@CandidateBase@ICECore@Dct@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Dct::ICECore::ComputeDegreeOfRedundency(void)
0x18022f9f3  mov     rbx, qword ptr [rbp+1C0h+var_50+8]
0x18022f9fa  test    rbx, rbx
0x18022f9fd  jz      short loc_18022FA38
0x18022f9ff  mov     eax, r15d
0x18022fa02  lock xadd [rbx+8], eax
0x18022fa07  add     eax, r15d
0x18022fa0a  jnz     short loc_18022FA38
0x18022fa0c  mov     rax, [rbx]
0x18022fa0f  mov     rcx, rbx
0x18022fa12  mov     rax, [rax]
0x18022fa15  call    cs:__guard_dispatch_icall_fptr
0x18022fa1b  mov     eax, r15d
0x18022fa1e  lock xadd [rbx+0Ch], eax
0x18022fa23  add     eax, r15d
0x18022fa26  jnz     short loc_18022FA38
0x18022fa28  mov     rax, [rbx]
0x18022fa2b  mov     rcx, rbx
0x18022fa2e  mov     rax, [rax+8]
0x18022fa32  call    cs:__guard_dispatch_icall_fptr
0x18022fa38  xorps   xmm0, xmm0
0x18022fa3b  movups  [rbp+1C0h+var_70], xmm0
0x18022fa42  lea     rcx, [rbp+1C0h+var_70]
0x18022fa49  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x18022fa4e  nop
0x18022fa4f  mov     rax, qword ptr [rbp+1C0h+var_70]
0x18022fa56  test    rax, rax
0x18022fa59  jz      short loc_18022FACC
0x18022fa5b  cmp     byte ptr [rax+80h], 0
0x18022fa62  jz      short loc_18022FACC
0x18022fa64  mov     ebx, [r14+2364h]
0x18022fa6b  mov     rdi, [rsi]
0x18022fa6e  xorps   xmm0, xmm0
0x18022fa71  movups  xmmword ptr [rbp+1C0h+var_50], xmm0
0x18022fa78  xorps   xmm1, xmm1
0x18022fa7b  movdqu  [rbp+1C0h+var_40], xmm1
0x18022fa83  mov     r8d, 4Dh ; 'M'
0x18022fa89  lea     rdx, aCheckpointIcel_2; "CheckPoint.ICELinkContextRemoved(): con"...
0x18022fa90  lea     rcx, [rbp+1C0h+var_50]
0x18022fa97  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18022fa9c  nop
0x18022fa9d  mov     dword ptr [rsp+2C0h+var_2A0], ebx
0x18022faa1  mov     r9, rdi
0x18022faa4  lea     r8, [rbp+1C0h+var_50]
0x18022faab  lea     rdx, aBasixDct; "BASIX_DCT"
0x18022fab2  lea     rcx, [rbp+1C0h+var_70]
0x18022fab9  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@PEAVIChannel@Dct@23@I@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@PEAVIChannel@Dct@23@I@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,Microsoft::Basix::Dct::IChannel *,uint>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &,Microsoft::Basix::Dct::IChannel *,uint)
0x18022fabe  nop
0x18022fabf  lea     rcx, [rbp+1C0h+var_50]
0x18022fac6  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18022facb  nop
0x18022facc  mov     rbx, qword ptr [rbp+1C0h+var_70+8]
0x18022fad3  test    rbx, rbx
0x18022fad6  jz      short loc_18022FB11
0x18022fad8  mov     eax, r15d
0x18022fadb  lock xadd [rbx+8], eax
0x18022fae0  add     eax, r15d
0x18022fae3  jnz     short loc_18022FB11
0x18022fae5  mov     rax, [rbx]
0x18022fae8  mov     rcx, rbx
0x18022faeb  mov     rax, [rax]
0x18022faee  call    cs:__guard_dispatch_icall_fptr
0x18022faf4  mov     eax, r15d
0x18022faf7  lock xadd [rbx+0Ch], eax
0x18022fafc  add     eax, r15d
0x18022faff  jnz     short loc_18022FB11
0x18022fb01  mov     rax, [rbx]
0x18022fb04  mov     rcx, rbx
0x18022fb07  mov     rax, [rax+8]
0x18022fb0b  call    cs:__guard_dispatch_icall_fptr
0x18022fb11  mov     eax, [r14+236Ch]
0x18022fb18  cmp     [r14+2364h], eax
0x18022fb1f  jnb     loc_18022FF9A
0x18022fb25  xorps   xmm0, xmm0
0x18022fb28  movups  [rbp+1C0h+var_70], xmm0
0x18022fb2f  lea     rcx, [rbp+1C0h+var_70]
0x18022fb36  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x18022fb3b  nop
0x18022fb3c  mov     rax, qword ptr [rbp+1C0h+var_70]
0x18022fb43  test    rax, rax
0x18022fb46  jz      short loc_18022FBBD
0x18022fb48  cmp     byte ptr [rax+80h], 0
0x18022fb4f  jz      short loc_18022FBBD
0x18022fb51  mov     ebx, [r14+236Ch]
0x18022fb58  mov     edi, [r14+2364h]
0x18022fb5f  xorps   xmm0, xmm0
0x18022fb62  movups  xmmword ptr [rbp+1C0h+var_50], xmm0
0x18022fb69  xorps   xmm1, xmm1
0x18022fb6c  movdqu  [rbp+1C0h+var_40], xmm1
0x18022fb74  mov     r8d, 7Fh
0x18022fb7a  lea     rdx, aCheckpointIcel; "CheckPoint.ICELinkContextRemoved(): sta"...
0x18022fb81  lea     rcx, [rbp+1C0h+var_50]
0x18022fb88  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18022fb8d  nop
0x18022fb8e  mov     dword ptr [rsp+2C0h+var_2A0], ebx
0x18022fb92  mov     r9d, edi
0x18022fb95  lea     r8, [rbp+1C0h+var_50]
0x18022fb9c  lea     rdx, aBasixDct; "BASIX_DCT"
0x18022fba3  lea     rcx, [rbp+1C0h+var_70]
0x18022fbaa  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@II@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@II@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,uint,uint>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &,uint,uint)
0x18022fbaf  nop
0x18022fbb0  lea     rcx, [rbp+1C0h+var_50]
0x18022fbb7  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18022fbbc  nop
0x18022fbbd  mov     rbx, qword ptr [rbp+1C0h+var_70+8]
0x18022fbc4  test    rbx, rbx
0x18022fbc7  jz      short loc_18022FC02
0x18022fbc9  mov     eax, r15d
0x18022fbcc  lock xadd [rbx+8], eax
0x18022fbd1  add     eax, r15d
0x18022fbd4  jnz     short loc_18022FC02
0x18022fbd6  mov     rax, [rbx]
0x18022fbd9  mov     rcx, rbx
0x18022fbdc  mov     rax, [rax]
0x18022fbdf  call    cs:__guard_dispatch_icall_fptr
0x18022fbe5  mov     eax, r15d
0x18022fbe8  lock xadd [rbx+0Ch], eax
0x18022fbed  add     eax, r15d
0x18022fbf0  jnz     short loc_18022FC02
0x18022fbf2  mov     rax, [rbx]
0x18022fbf5  mov     rcx, rbx
0x18022fbf8  mov     rax, [rax+8]
0x18022fbfc  call    cs:__guard_dispatch_icall_fptr
0x18022fc02  xorps   xmm0, xmm0
0x18022fc05  movups  xmmword ptr [rbp+1C0h+var_50], xmm0
0x18022fc0c  lea     rcx, [rbp+1C0h+var_50]
0x18022fc13  call    ??$SelectEvent@VTraceCheckpoint@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(void)
0x18022fc18  nop
0x18022fc19  mov     rax, qword ptr [rbp+1C0h+var_50]
0x18022fc20  test    rax, rax
0x18022fc23  jz      loc_18022FEF5
0x18022fc29  cmp     byte ptr [rax+80h], 0
0x18022fc30  jz      loc_18022FEF5
0x18022fc36  lea     rax, [rbp+1C0h+var_1B0]
0x18022fc3a  mov     [rbp+1C0h+var_30], rax
0x18022fc41  mov     edx, [r14+236Ch]
0x18022fc48  lea     rcx, [rbp+1C0h+var_D0]
0x18022fc4f  call    ??$_Integral_to_string@DI@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@I@Z; std::_Integral_to_string<char,uint>(uint)
0x18022fc54  nop
0x18022fc55  xorps   xmm0, xmm0
0x18022fc58  movups  [rbp+1C0h+var_1D8], xmm0
0x18022fc5c  xorps   xmm1, xmm1
0x18022fc5f  movdqu  [rbp+1C0h+var_1C8], xmm1
0x18022fc64  mov     edi, 1
0x18022fc69  mov     r8d, edi
0x18022fc6c  lea     rdx, asc_1803D71C4; ":"
0x18022fc73  lea     rcx, [rbp+1C0h+var_1D8]
0x18022fc77  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18022fc7c  nop
  ... truncated ...
```
