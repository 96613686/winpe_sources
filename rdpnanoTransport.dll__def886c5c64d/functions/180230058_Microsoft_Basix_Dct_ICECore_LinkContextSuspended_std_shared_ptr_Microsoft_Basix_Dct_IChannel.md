# Microsoft::Basix::Dct::ICECore::LinkContextSuspended(std::shared_ptr<Microsoft::Basix::Dct::IChannel>)

- ea: `0x180230058`
- end: `0x180230ad6`
- name: `?LinkContextSuspended@ICECore@Dct@Basix@Microsoft@@QEAAXV?$shared_ptr@VIChannel@Dct@Basix@Microsoft@@@std@@@Z`
- size: `2686`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `broker_com_uri`

## callers

- `0x1800fda40`

## callees

- `0x18000d9c0`
- `0x180015bb8`
- `0x180017380`
- `0x180018b94`
- `0x180018ea4`
- `0x18001902c`
- `0x1800191b4`
- `0x18001db78`
- `0x180024760`
- `0x1800c3bc8`
- `0x1800c408c`
- `0x1800f30dc`
- `0x1801a5dc8`
- `0x1801c9d28`
- `0x180203c08`
- `0x18020b6b8`
- `0x18021b170`
- `0x18021b1e8`
- `0x18021fe58`
- `0x180230058`
- `0x18023d500`
- `0x18032f050`
- `0x18032f0b0`
- `0x180375c40`

## string_xrefs

- `0x18023011b`: `Microsoft::Basix::Dct::ICECore::LinkContextSuspended`
- `0x180230107`: `ICELinkContextSuspended: context = %p. Type casting link context to ICECore::LinkContext returned null.\n    %s(%d): %s()`
- `0x1802301e7`: `LinkContextSuspended: context = %p. duplicate state change! ignore`
- `0x180230319`: `CheckPoint.ICELinkContextSuspended: context = %p, dor=%d`
- `0x180230414`: `ICECore::LinkContextSuspended: current DoR is enough for target DoR, ignore: m_degreeOfRedundency=%d, m_targetDoR=%d`
- `0x1802304ff`: `ICECore::LinkContextSuspended: localCandidate(%p) is a TURN and already cloned, ignore`
- `0x180230620`: `ICECore::LinkContextSuspended: localCandidate(%p) is not a TURN but remote is a TURN, skip`
- `0x1802308c1`: `New Clones due to link suspend`

## pseudocode

```c
// Hidden C++ exception states: #wind=38
__int64 __fastcall Microsoft::Basix::Dct::ICECore::LinkContextSuspended(_DWORD *a1, _QWORD *a2)
{
  _QWORD *v4; // r14
  const char *v5; // r9
  __int64 result; // rax
  __int64 v7; // rbx
  __int32 v8; // ebx
  __int64 v9; // rbx
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
  __int64 v20; // rax
  __int64 v21; // rdi
  __int64 v22; // rbx
  volatile signed __int32 *v23; // rbx
  void (__fastcall **v24)(__int64); // rax
  __int64 v25; // rcx
  __int64 v26; // rbx
  volatile signed __int32 *v27; // rbx
  __int64 v28; // rax
  __int64 v29; // rdx
  __int64 v30; // rdx
  __int64 v31; // rdx
  __int64 v32; // rax
  __int64 v33; // rdx
  __int64 v34; // rdx
  __int64 v35; // rdx
  volatile signed __int32 *v36; // rbx
  __int64 v37; // rbx
  volatile signed __int32 *v38; // rbx
  volatile signed __int32 *v39; // rbx
  int v40; // [rsp+20h] [rbp-E0h]
  char *Str; // [rsp+28h] [rbp-D8h]
  char v42; // [rsp+40h] [rbp-C0h]
  __int128 v43; // [rsp+48h] [rbp-B8h] BYREF
  _OWORD v44[2]; // [rsp+58h] [rbp-A8h] BYREF
  _OWORD v45[2]; // [rsp+78h] [rbp-88h] BYREF
  _OWORD v46[2]; // [rsp+98h] [rbp-68h] BYREF
  _OWORD v47[2]; // [rsp+B8h] [rbp-48h] BYREF
  _OWORD v48[2]; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD *v49; // [rsp+F8h] [rbp-8h]
  __int64 v50[4]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v51[4]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v52[32]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v53[32]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v54[32]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v55[32]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v56[32]; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v57[32]; // [rsp+1E0h] [rbp+E0h] BYREF
  _BYTE v58[32]; // [rsp+200h] [rbp+100h] BYREF
  _BYTE v59[32]; // [rsp+220h] [rbp+120h] BYREF
  __int128 v60; // [rsp+240h] [rbp+140h] BYREF
  int v61[4]; // [rsp+250h] [rbp+150h] BYREF
  __int128 v62; // [rsp+260h] [rbp+160h]
  __int64 *v63; // [rsp+270h] [rbp+170h] BYREF
  _OWORD v64[2]; // [rsp+278h] [rbp+178h] BYREF

  v49 = a2;
  v43 = 0;
  std::dynamic_pointer_cast<Microsoft::Basix::Dct::ICECore::LinkContext,Microsoft::Basix::Dct::IChannel>(&v43);
  v4 = (_QWORD *)v43;
  if ( !(_QWORD)v43 )
  {
    v60 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v60);
    result = v60;
    if ( (_QWORD)v60 && *(_BYTE *)(v60 + 128) )
    {
      v7 = *a2;
      *(_OWORD *)v61 = 0;
      v62 = 0;
      std::string::_Construct<1,char const *>(
        v61,
        "ICELinkContextSuspended: context = %p. Type casting link context to ICECore::LinkContext returned null.\n"
        "    %s(%d): %s()",
        (const void *)0x78,
        v5,
        v40,
        Str);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,Microsoft::Basix::Dct::WebSocketDCT *,char const *,int,char const *>(
        (unsigned int)&v60,
        (unsigned int)"BASIX_DCT",
        (unsigned int)v61,
        v7,
        (__int64)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\icecore.cpp",
        142,
        (__int64)"Microsoft::Basix::Dct::ICECore::LinkContextSuspended");
      result = std::string::_Tidy_deallocate(v61);
    }
    goto LABEL_66;
  }
  LODWORD(v63) = 1;
  v8 = ((__int64 (__fastcall *)(__int64 **))boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data4)(&v63);
  if ( _InterlockedExchange(
         (volatile __int32 *)(*(__int64 (__fastcall **)(__int64))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)((__int64)v4 + 1508),
         v8) == 1 )
  {
    v60 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(&v60);
    result = v60;
    if ( (_QWORD)v60 && *(_BYTE *)(v60 + 128) )
    {
      v9 = *a2;
      *(_OWORD *)v61 = 0;
      v62 = 0;
      std::string::_Construct<1,char const *>(
        v61,
        "LinkContextSuspended: context = %p. duplicate state change! ignore",
        (const void *)0x42);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,Microsoft::Basix::Dct::detail::BasicStateManagement *>(
        &v60,
        "BASIX_DCT",
        v61,
        v9);
      result = std::string::_Tidy_deallocate(v61);
    }
    goto LABEL_66;
  }
  v10 = (Microsoft::Basix::Dct::ICE::Candidate *)v4[176];
  if ( *(_DWORD *)(v4[174] + 228LL) == 3 )
    Microsoft::Basix::Dct::ICE::Candidate::AdjustRelayLink(v10, -1);
  else
    Microsoft::Basix::Dct::ICE::Candidate::AdjustNonRelayLink(v10, -1);
  v11 = (Microsoft::Basix::Dct::ICE::Candidate *)v4[174];
  if ( *(_DWORD *)(v4[176] + 228LL) == 3 )
    Microsoft::Basix::Dct::ICE::Candidate::AdjustRelayLink(v11, -1);
  else
    Microsoft::Basix::Dct::ICE::Candidate::AdjustNonRelayLink(v11, -1);
  Microsoft::Basix::Dct::ICECore::ComputeDegreeOfRedundency(a1, v61);
  v12 = *(volatile signed __int32 **)&v61[2];
  if ( *(_QWORD *)&v61[2] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v61[2] + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
      if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
    }
  }
  v60 = 0;
  Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v60);
  result = v60;
  if ( (_QWORD)v60 && *(_BYTE *)(v60 + 128) )
  {
    v14 = a1[2265];
    v15 = *a2;
    *(_OWORD *)v61 = 0;
    v62 = 0;
    std::string::_Construct<1,char const *>(
      v61,
      "CheckPoint.ICELinkContextSuspended: context = %p, dor=%d",
      (const void *)0x38,
      v13);
    Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,Microsoft::Basix::Dct::IChannel *,unsigned int>(
      (unsigned int)&v60,
      (unsigned int)"BASIX_DCT",
      (unsigned int)v61,
      v15,
      v14);
    result = std::string::_Tidy_deallocate(v61);
  }
  v16 = (volatile signed __int32 *)*((_QWORD *)&v60 + 1);
  if ( *((_QWORD *)&v60 + 1) )
  {
    result = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v60 + 1) + 8LL));
    if ( !(_DWORD)result )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
      result = (unsigned int)_InterlockedDecrement(v16 + 3);
      if ( !(_DWORD)result )
        result = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
    }
  }
  if ( !a1[2270] )
    goto LABEL_71;
  if ( a1[2265] >= a1[2267] )
  {
    v60 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v60);
    result = v60;
    if ( (_QWORD)v60 && *(_BYTE *)(v60 + 128) )
    {
      v18 = a1[2267];
      v19 = a1[2265];
      *(_OWORD *)v61 = 0;
      v62 = 0;
      std::string::_Construct<1,char const *>(
        v61,
        "ICECore::LinkContextSuspended: current DoR is enough for target DoR, ignore: m_degreeOfRedundency=%d, m_targetDoR=%d",
        116,
        v17);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,unsigned int,unsigned int>(
        (unsigned int)&v60,
        (unsigned int)"BASIX_DCT",
        (unsigned int)v61,
        v19,
        v18);
      result = std::string::_Tidy_deallocate(v61);
    }
    goto LABEL_66;
  }
  v60 = 0;
  if ( *(_DWORD *)(v4[174] + 228LL) != 3 )
  {
    if ( *(_DWORD *)(v4[176] + 228LL) == 3 )
    {
      v64[0] = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v64);
      result = *(_QWORD *)&v64[0];
      if ( *(_QWORD *)&v64[0] && *(_BYTE *)(*(_QWORD *)&v64[0] + 128LL) )
      {
        v26 = v4[174];
        *(_OWORD *)v61 = 0;
        v62 = 0;
        std::string::_Construct<1,char const *>(
          v61,
          "ICECore::LinkContextSuspended: localCandidate(%p) is not a TURN but remote is a TURN, skip",
          (const void *)0x5A);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,Microsoft::Basix::Dct::ISmilesLink *>(
          v64,
          "BASIX_DCT",
          v61,
          v26);
        result = std::string::_Tidy_deallocate(v61);
      }
      v27 = (volatile signed __int32 *)*((_QWORD *)&v64[0] + 1);
      if ( *((_QWORD *)&v64[0] + 1) )
      {
        result = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v64[0] + 1) + 8LL));
        if ( !(_DWORD)result )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v27)(v27);
          result = (unsigned int)_InterlockedDecrement(v27 + 3);
          if ( !(_DWORD)result )
            result = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
        }
      }
      goto LABEL_71;
    }
    goto LABEL_58;
  }
  v20 = v4[175];
  if ( v20 )
    _InterlockedIncrement((volatile signed __int32 *)(v20 + 8));
  *(_QWORD *)&v60 = v4[174];
  v21 = v4[175];
  *((_QWORD *)&v60 + 1) = v21;
  if ( !*(_BYTE *)(v60 + 225) )
  {
LABEL_58:
    *(_OWORD *)v61 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v61);
    if ( *(_QWORD *)v61 && *(_BYTE *)(*(_QWORD *)v61 + 128LL) )
    {
      v63 = v50;
      std::_Integral_to_string<char,unsigned int>(v57, (unsigned int)a1[2267]);
      memset(v48, 0, sizeof(v48));
      std::string::_Construct<1,char const *>(v48, ":", 1);
      memset(v47, 0, sizeof(v47));
      std::string::_Construct<1,char const *>(v47, "\"", 1);
      memset(v46, 0, sizeof(v46));
      std::string::_Construct<1,char const *>(v46, "\"", 1);
      v28 = std::operator+<char>(v59, v46, "IceTargetDoR");
      LOBYTE(v29) = v42;
      std::string::string(v56, v29, v28, v47);
      LOBYTE(v30) = v42;
      std::string::string(v55, v30, v56, v48);
      LOBYTE(v31) = v42;
      std::string::string(v50, v31, v55, v57);
      std::_Integral_to_string<char,unsigned int>(v54, (unsigned int)a1[2265]);
      memset(v45, 0, sizeof(v45));
      std::string::_Construct<1,char const *>(v45, ":", 1);
      memset(v64, 0, sizeof(v64));
      std::string::_Construct<1,char const *>(v64, "\"", 1);
      memset(v44, 0, sizeof(v44));
      std::string::_Construct<1,char const *>(v44, "\"", 1);
      v32 = std::operator+<char>(v58, v44, "IceDoR");
      LOBYTE(v33) = v42;
      std::string::string(v53, v33, v32, v64);
      LOBYTE(v34) = v42;
      std::string::string(v52, v34, v53, v45);
      LOBYTE(v35) = v42;
      std::string::string(v51, v35, v52, v54);
      Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string,std::string>(
        (int)v61,
        (int)"RD_CHECKPOINT",
        0,
        (int)"ICECore",
        "Clone",
        "New Clones due to link suspend",
        (__int64)v51,
        (__int64)v50);
      std::string::_Tidy_deallocate(v52);
      std::string::_Tidy_deallocate(v53);
      std::string::_Tidy_deallocate(v58);
      std::string::_Tidy_deallocate(v44);
      std::string::_Tidy_deallocate(v64);
      std::string::_Tidy_deallocate(v45);
      std::string::_Tidy_deallocate(v54);
      std::string::_Tidy_deallocate(v55);
      std::string::_Tidy_deallocate(v56);
      std::string::_Tidy_deallocate(v59);
      std::string::_Tidy_deallocate(v46);
      std::string::_Tidy_deallocate(v47);
      std::string::_Tidy_deallocate(v48);
      std::string::_Tidy_deallocate(v57);
    }
    v36 = *(volatile signed __int32 **)&v61[2];
    if ( *(_QWORD *)&v61[2] )
    {
      if ( !_InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)&v61[2] + 8LL)) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v36)(v36);
        if ( !_InterlockedDecrement(v36 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v36 + 8LL))(v36);
      }
    }
    result = Microsoft::Basix::Dct::ICECore::ScheduleClone(a1, &v60);
LABEL_66:
    v37 = *((_QWORD *)&v60 + 1);
    if ( *((_QWORD *)&v60 + 1) )
    {
      result = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v60 + 1) + 8LL));
      if ( !(_DWORD)result )
      {
        (**(void (__fastcall ***)(__int64))v37)(v37);
        result = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)(v37 + 12));
        if ( !(_DWORD)result )
        {
          v24 = *(void (__fastcall ***)(__int64))v37;
          v25 = v37;
          goto LABEL_70;
        }
      }
    }
    goto LABEL_71;
  }
  v64[0] = 0;
  Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v64);
  result = *(_QWORD *)&v64[0];
  if ( *(_QWORD *)&v64[0] && *(_BYTE *)(*(_QWORD *)&v64[0] + 128LL) )
  {
    v22 = v4[174];
    *(_OWORD *)v61 = 0;
    v62 = 0;
    std::string::_Construct<1,char const *>(
      v61,
      "ICECore::LinkContextSuspended: localCandidate(%p) is a TURN and already cloned, ignore",
      (const void *)0x56);
    Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,Microsoft::Basix::Dct::ISmilesLink *>(
      v64,
      "BASIX_DCT",
      v61,
      v22);
    result = std::string::_Tidy_deallocate(v61);
  }
  v23 = (volatile signed __int32 *)*((_QWORD *)&v64[0] + 1);
  if ( *((_QWORD *)&v64[0] + 1) )
  {
    result = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v64[0] + 1) + 8LL));
    if ( !(_DWORD)result )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v23)(v23);
      result = (unsigned int)_InterlockedDecrement(v23 + 3);
      if ( !(_DWORD)result )
        result = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
    }
  }
  if ( v21 )
  {
    result = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)(v21 + 8));
    if ( !(_DWORD)result )
    {
      (**(void (__fastcall ***)(__int64))v21)(v21);
      result = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)(v21 + 12));
      if ( !(_DWORD)result )
      {
        v24 = *(void (__fastcall ***)(__int64))v21;
        v25 = v21;
LABEL_70:
        result = ((__int64 (__fastcall *)(__int64))v24[1])(v25);
      }
    }
  }
LABEL_71:
  v38 = (volatile signed __int32 *)*((_QWORD *)&v43 + 1);
  if ( *((_QWORD *)&v43 + 1) )
  {
    result = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v43 + 1) + 8LL));
    if ( !(_DWORD)result )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v38)(v38);
      result = (unsigned int)_InterlockedDecrement(v38 + 3);
      if ( !(_DWORD)result )
        result = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v38 + 8LL))(v38);
    }
  }
  v39 = (volatile signed __int32 *)a2[1];
  if ( v39 )
  {
    result = (unsigned int)_InterlockedDecrement(v39 + 2);
    if ( !(_DWORD)result )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v39)(v39);
      result = (unsigned int)_InterlockedDecrement(v39 + 3);
      if ( !(_DWORD)result )
        return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v39 + 8LL))(v39);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180230058  mov     [rsp-8+arg_10], rbx
0x18023005d  mov     [rsp-8+arg_18], rsi
0x180230062  push    rbp
0x180230063  push    rdi
0x180230064  push    r13
0x180230066  push    r14
0x180230068  push    r15
0x18023006a  lea     rbp, [rsp-1A0h]
0x180230072  mov     eax, 2A0h
0x180230077  call    _alloca_probe
0x18023007c  sub     rsp, rax
0x18023007f  mov     rax, cs:__security_cookie
0x180230086  xor     rax, rsp
0x180230089  mov     [rbp+1C0h+var_28], rax
0x180230090  mov     r15, rdx
0x180230093  mov     r13, rcx
0x180230096  mov     [rbp+1C0h+var_1C8], rdx
0x18023009a  xorps   xmm0, xmm0
0x18023009d  movups  [rsp+2C0h+var_278], xmm0
0x1802300a2  lea     rcx, [rsp+2C0h+var_278]
0x1802300a7  call    ??$dynamic_pointer_cast@VLinkContext@ICECore@Dct@Basix@Microsoft@@VIChannel@345@@std@@YA?AV?$shared_ptr@VLinkContext@ICECore@Dct@Basix@Microsoft@@@0@AEBV?$shared_ptr@VIChannel@Dct@Basix@Microsoft@@@0@@Z; std::dynamic_pointer_cast<Microsoft::Basix::Dct::ICECore::LinkContext,Microsoft::Basix::Dct::IChannel>(std::shared_ptr<Microsoft::Basix::Dct::IChannel> const &)
0x1802300ac  nop
0x1802300ad  mov     r14, qword ptr [rsp+2C0h+var_278]
0x1802300b2  test    r14, r14
0x1802300b5  jnz     loc_18023016E
0x1802300bb  xorps   xmm0, xmm0
0x1802300be  movups  [rbp+1C0h+var_80], xmm0
0x1802300c5  lea     rcx, [rbp+1C0h+var_80]
0x1802300cc  call    ??$SelectEvent@VTraceError@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(void)
0x1802300d1  nop
0x1802300d2  mov     rax, qword ptr [rbp+1C0h+var_80]
0x1802300d9  test    rax, rax
0x1802300dc  jz      loc_180230166
0x1802300e2  cmp     [rax+80h], r14b
0x1802300e9  jz      short loc_180230166
0x1802300eb  mov     rbx, [r15]
0x1802300ee  xorps   xmm0, xmm0
0x1802300f1  movups  xmmword ptr [rbp+1C0h+var_70], xmm0
0x1802300f8  xorps   xmm1, xmm1
0x1802300fb  movdqu  [rbp+1C0h+var_60], xmm1
0x180230103  lea     r8d, [r14+78h]
0x180230107  lea     rdx, aIcelinkcontext_0; "ICELinkContextSuspended: context = %p. "...
0x18023010e  lea     rcx, [rbp+1C0h+var_70]
0x180230115  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18023011a  nop
0x18023011b  lea     rax, aMicrosoftBasix_420; "Microsoft::Basix::Dct::ICECore::LinkCon"...
0x180230122  mov     [rsp+2C0h+var_290], rax
0x180230127  mov     dword ptr [rsp+2C0h+Str], 98Eh
0x18023012f  lea     rax, aCW1SSrcLibbasi_59; "C:\\__w\\1\\s\\src\\libbasix-network\\d"...
0x180230136  mov     [rsp+2C0h+var_2A0], rax
0x18023013b  mov     r9, rbx
0x18023013e  lea     r8, [rbp+1C0h+var_70]
0x180230145  lea     rdx, aBasixDct; "BASIX_DCT"
0x18023014c  lea     rcx, [rbp+1C0h+var_80]
0x180230153  call    ??$TraceMessage@VTraceError@Basix@Microsoft@@PEAVWebSocketDCT@Dct@23@PEBDHPEBD@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@PEAVWebSocketDCT@Dct@23@1H1@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,Microsoft::Basix::Dct::WebSocketDCT *,char const *,int,char const *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceError>> const &,char const *,std::string const &,Microsoft::Basix::Dct::WebSocketDCT *,char const *,int,char const *)
0x180230158  nop
0x180230159  lea     rcx, [rbp+1C0h+var_70]
0x180230160  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180230165  nop
0x180230166  or      esi, 0FFFFFFFFh
0x180230169  jmp     loc_1802309EB
0x18023016e  mov     dword ptr [rbp+1C0h+var_50], 1
0x180230178  lea     rcx, [rbp+1C0h+var_50]
0x18023017f  call    near ptr ??$launder@USecurityCookieHash@RdpNano@Microsoft@@@core@boost@@YAPEAUSecurityCookieHash@RdpNano@Microsoft@@PEAU234@@Z.Data4; boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>(Microsoft::RdpNano::SecurityCookieHash *)
0x180230184  mov     ebx, eax
0x180230186  lea     rcx, [r14+5E4h]
0x18023018d  call    near ptr ??$launder@USecurityCookieHash@RdpNano@Microsoft@@@core@boost@@YAPEAUSecurityCookieHash@RdpNano@Microsoft@@PEAU234@@Z.Data1; boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>(Microsoft::RdpNano::SecurityCookieHash *)
0x180230192  xchg    ebx, [rax]
0x180230194  cmp     ebx, 1
0x180230197  jnz     loc_18023022B
0x18023019d  xorps   xmm0, xmm0
0x1802301a0  movups  [rbp+1C0h+var_80], xmm0
0x1802301a7  lea     rcx, [rbp+1C0h+var_80]
0x1802301ae  call    ??$SelectEvent@VTraceWarning@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(void)
0x1802301b3  nop
0x1802301b4  mov     rax, qword ptr [rbp+1C0h+var_80]
0x1802301bb  test    rax, rax
0x1802301be  jz      short loc_180230226
0x1802301c0  cmp     byte ptr [rax+80h], 0
0x1802301c7  jz      short loc_180230226
0x1802301c9  mov     rbx, [r15]
0x1802301cc  xorps   xmm0, xmm0
0x1802301cf  movups  xmmword ptr [rbp+1C0h+var_70], xmm0
0x1802301d6  xorps   xmm1, xmm1
0x1802301d9  movdqu  [rbp+1C0h+var_60], xmm1
0x1802301e1  mov     r8d, 42h ; 'B'
0x1802301e7  lea     rdx, aLinkcontextsus; "LinkContextSuspended: context = %p. dup"...
0x1802301ee  lea     rcx, [rbp+1C0h+var_70]
0x1802301f5  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1802301fa  nop
0x1802301fb  mov     r9, rbx
0x1802301fe  lea     r8, [rbp+1C0h+var_70]
0x180230205  lea     rdx, aBasixDct; "BASIX_DCT"
0x18023020c  lea     rcx, [rbp+1C0h+var_80]
0x180230213  call    ??$TraceMessage@VTraceWarning@Basix@Microsoft@@PEAVBasicStateManagement@detail@Dct@23@@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@PEAVBasicStateManagement@detail@Dct@23@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,Microsoft::Basix::Dct::detail::BasicStateManagement *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>> const &,char const *,std::string const &,Microsoft::Basix::Dct::detail::BasicStateManagement *)
0x180230218  nop
0x180230219  lea     rcx, [rbp+1C0h+var_70]
0x180230220  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180230225  nop
0x180230226  jmp     loc_180230166
0x18023022b  mov     rcx, [r14+580h]; this
0x180230232  mov     rax, [r14+570h]
0x180230239  or      esi, 0FFFFFFFFh
0x18023023c  mov     edx, esi; int
0x18023023e  cmp     dword ptr [rax+0E4h], 3
0x180230245  jnz     short loc_18023024E
0x180230247  call    ?AdjustRelayLink@Candidate@ICE@Dct@Basix@Microsoft@@QEAAIH@Z; Microsoft::Basix::Dct::ICE::Candidate::AdjustRelayLink(int)
0x18023024c  jmp     short loc_180230253
0x18023024e  call    ?AdjustNonRelayLink@Candidate@ICE@Dct@Basix@Microsoft@@QEAAIH@Z; Microsoft::Basix::Dct::ICE::Candidate::AdjustNonRelayLink(int)
0x180230253  mov     rcx, [r14+570h]; this
0x18023025a  mov     rax, [r14+580h]
0x180230261  mov     edx, esi; int
0x180230263  cmp     dword ptr [rax+0E4h], 3
0x18023026a  jnz     short loc_180230273
0x18023026c  call    ?AdjustRelayLink@Candidate@ICE@Dct@Basix@Microsoft@@QEAAIH@Z; Microsoft::Basix::Dct::ICE::Candidate::AdjustRelayLink(int)
0x180230271  jmp     short loc_180230278
0x180230273  call    ?AdjustNonRelayLink@Candidate@ICE@Dct@Basix@Microsoft@@QEAAIH@Z; Microsoft::Basix::Dct::ICE::Candidate::AdjustNonRelayLink(int)
0x180230278  lea     rdx, [rbp+1C0h+var_70]
0x18023027f  mov     rcx, r13
0x180230282  call    ?ComputeDegreeOfRedundency@ICECore@Dct@Basix@Microsoft@@QEAA?AV?$shared_ptr@VTurnServer@CandidateBase@ICECore@Dct@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Dct::ICECore::ComputeDegreeOfRedundency(void)
0x180230287  mov     rbx, qword ptr [rbp+1C0h+var_70+8]
0x18023028e  test    rbx, rbx
0x180230291  jz      short loc_1802302C8
0x180230293  mov     eax, esi
0x180230295  lock xadd [rbx+8], eax
0x18023029a  add     eax, esi
0x18023029c  jnz     short loc_1802302C8
0x18023029e  mov     rax, [rbx]
0x1802302a1  mov     rcx, rbx
0x1802302a4  mov     rax, [rax]
0x1802302a7  call    cs:__guard_dispatch_icall_fptr
0x1802302ad  mov     eax, esi
0x1802302af  lock xadd [rbx+0Ch], eax
0x1802302b4  add     eax, esi
0x1802302b6  jnz     short loc_1802302C8
0x1802302b8  mov     rax, [rbx]
0x1802302bb  mov     rcx, rbx
0x1802302be  mov     rax, [rax+8]
0x1802302c2  call    cs:__guard_dispatch_icall_fptr
0x1802302c8  xorps   xmm0, xmm0
0x1802302cb  movups  [rbp+1C0h+var_80], xmm0
0x1802302d2  lea     rcx, [rbp+1C0h+var_80]
0x1802302d9  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x1802302de  nop
0x1802302df  mov     rax, qword ptr [rbp+1C0h+var_80]
0x1802302e6  test    rax, rax
0x1802302e9  jz      short loc_18023035C
0x1802302eb  cmp     byte ptr [rax+80h], 0
0x1802302f2  jz      short loc_18023035C
0x1802302f4  mov     ebx, [r13+2364h]
0x1802302fb  mov     rdi, [r15]
0x1802302fe  xorps   xmm0, xmm0
0x180230301  movups  xmmword ptr [rbp+1C0h+var_70], xmm0
0x180230308  xorps   xmm1, xmm1
0x18023030b  movdqu  [rbp+1C0h+var_60], xmm1
0x180230313  mov     r8d, 38h ; '8'
0x180230319  lea     rdx, aCheckpointIcel_0; "CheckPoint.ICELinkContextSuspended: con"...
0x180230320  lea     rcx, [rbp+1C0h+var_70]
0x180230327  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18023032c  nop
0x18023032d  mov     dword ptr [rsp+2C0h+var_2A0], ebx
0x180230331  mov     r9, rdi
0x180230334  lea     r8, [rbp+1C0h+var_70]
0x18023033b  lea     rdx, aBasixDct; "BASIX_DCT"
0x180230342  lea     rcx, [rbp+1C0h+var_80]
0x180230349  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@PEAVIChannel@Dct@23@I@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@PEAVIChannel@Dct@23@I@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,Microsoft::Basix::Dct::IChannel *,uint>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &,Microsoft::Basix::Dct::IChannel *,uint)
0x18023034e  nop
0x18023034f  lea     rcx, [rbp+1C0h+var_70]
0x180230356  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18023035b  nop
0x18023035c  mov     rbx, qword ptr [rbp+1C0h+var_80+8]
0x180230363  test    rbx, rbx
0x180230366  jz      short loc_18023039D
0x180230368  mov     eax, esi
0x18023036a  lock xadd [rbx+8], eax
0x18023036f  add     eax, esi
0x180230371  jnz     short loc_18023039D
0x180230373  mov     rax, [rbx]
0x180230376  mov     rcx, rbx
0x180230379  mov     rax, [rax]
0x18023037c  call    cs:__guard_dispatch_icall_fptr
0x180230382  mov     eax, esi
0x180230384  lock xadd [rbx+0Ch], eax
0x180230389  add     eax, esi
0x18023038b  jnz     short loc_18023039D
0x18023038d  mov     rax, [rbx]
0x180230390  mov     rcx, rbx
0x180230393  mov     rax, [rax+8]
0x180230397  call    cs:__guard_dispatch_icall_fptr
0x18023039d  cmp     dword ptr [r13+2378h], 0
0x1802303a5  jz      loc_180230A2D
0x1802303ab  mov     eax, [r13+236Ch]
0x1802303b2  xorps   xmm0, xmm0
0x1802303b5  cmp     [r13+2364h], eax
0x1802303bc  jb      loc_18023045C
0x1802303c2  movups  [rbp+1C0h+var_80], xmm0
0x1802303c9  lea     rcx, [rbp+1C0h+var_80]
0x1802303d0  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x1802303d5  nop
0x1802303d6  mov     rax, qword ptr [rbp+1C0h+var_80]
0x1802303dd  test    rax, rax
0x1802303e0  jz      short loc_180230457
0x1802303e2  cmp     byte ptr [rax+80h], 0
0x1802303e9  jz      short loc_180230457
0x1802303eb  mov     ebx, [r13+236Ch]
0x1802303f2  mov     edi, [r13+2364h]
0x1802303f9  xorps   xmm0, xmm0
0x1802303fc  movups  xmmword ptr [rbp+1C0h+var_70], xmm0
0x180230403  xorps   xmm1, xmm1
0x180230406  movdqu  [rbp+1C0h+var_60], xmm1
0x18023040e  mov     r8d, 74h ; 't'
0x180230414  lea     rdx, aIcecoreLinkcon_1; "ICECore::LinkContextSuspended: current "...
0x18023041b  lea     rcx, [rbp+1C0h+var_70]
0x180230422  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180230427  nop
0x180230428  mov     dword ptr [rsp+2C0h+var_2A0], ebx
0x18023042c  mov     r9d, edi
0x18023042f  lea     r8, [rbp+1C0h+var_70]
0x180230436  lea     rdx, aBasixDct; "BASIX_DCT"
0x18023043d  lea     rcx, [rbp+1C0h+var_80]
0x180230444  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@II@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@II@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,uint,uint>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &,uint,uint)
0x180230449  nop
0x18023044a  lea     rcx, [rbp+1C0h+var_70]
0x180230451  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180230456  nop
0x180230457  jmp     loc_1802309EB
0x18023045c  xorps   xmm1, xmm1
0x18023045f  movdqu  [rbp+1C0h+var_80], xmm1
0x180230467  mov     rax, [r14+570h]
0x18023046e  cmp     dword ptr [rax+0E4h], 3
0x180230475  jnz     loc_1802305C1
0x18023047b  mov     rax, [r14+578h]
0x180230482  test    rax, rax
0x180230485  jz      short loc_18023048B
0x180230487  lock inc dword ptr [rax+8]
0x18023048b  mov     rax, [r14+570h]
0x180230492  mov     qword ptr [rbp+1C0h+var_80], rax
0x180230499  mov     rdi, [r14+578h]
0x1802304a0  mov     qword ptr [rbp+1C0h+var_80+8], rdi
0x1802304a7  cmp     byte ptr [rax+0E1h], 0
0x1802304ae  jz      loc_1802306A6
0x1802304b4  movups  [rbp+1C0h+var_48], xmm0
0x1802304bb  lea     rcx, [rbp+1C0h+var_48]
0x1802304c2  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x1802304c7  nop
0x1802304c8  mov     rax, qword ptr [rbp+1C0h+var_48]
0x1802304cf  test    rax, rax
0x1802304d2  jz      short loc_18023053E
0x1802304d4  cmp     byte ptr [rax+80h], 0
0x1802304db  jz      short loc_18023053E
0x1802304dd  mov     rbx, [r14+570h]
0x1802304e4  xorps   xmm0, xmm0
0x1802304e7  movups  xmmword ptr [rbp+1C0h+var_70], xmm0
0x1802304ee  xorps   xmm1, xmm1
0x1802304f1  movdqu  [rbp+1C0h+var_60], xmm1
0x1802304f9  mov     r8d, 56h ; 'V'
0x1802304ff  lea     rdx, aIcecoreLinkcon_3; "ICECore::LinkContextSuspended: localCan"...
0x180230506  lea     rcx, [rbp+1C0h+var_70]
0x18023050d  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180230512  nop
0x180230513  mov     r9, rbx
0x180230516  lea     r8, [rbp+1C0h+var_70]
0x18023051d  lea     rdx, aBasixDct; "BASIX_DCT"
0x180230524  lea     rcx, [rbp+1C0h+var_48]
0x18023052b  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@PEAVISmilesLink@Dct@23@@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@PEAVISmilesLink@Dct@23@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,Microsoft::Basix::Dct::ISmilesLink *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &,Microsoft::Basix::Dct::ISmilesLink *)
0x180230530  nop
0x180230531  lea     rcx, [rbp+1C0h+var_70]
0x180230538  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18023053d  nop
0x18023053e  mov     rbx, qword ptr [rbp+1C0h+var_48+8]
0x180230545  test    rbx, rbx
0x180230548  jz      short loc_180230580
0x18023054a  mov     eax, esi
0x18023054c  lock xadd [rbx+8], eax
0x180230551  add     eax, esi
0x180230553  jnz     short loc_180230580
0x180230555  mov     rax, [rbx]
0x180230558  mov     rcx, rbx
0x18023055b  mov     rax, [rax]
0x18023055e  call    cs:__guard_dispatch_icall_fptr
0x180230564  mov     eax, esi
0x180230566  lock xadd [rbx+0Ch], eax
0x18023056b  add     eax, esi
0x18023056d  jnz     short loc_180230580
0x18023056f  mov     rax, [rbx]
0x180230572  mov     rcx, rbx
0x180230575  mov     rax, [rax+8]
0x180230579  call    cs:__guard_dispatch_icall_fptr
0x18023057f  nop
0x180230580  test    rdi, rdi
0x180230583  jz      loc_180230A2D
0x180230589  mov     eax, esi
0x18023058b  lock xadd [rdi+8], eax
0x180230590  add     eax, esi
0x180230592  jnz     loc_180230A2D
0x180230598  mov     rax, [rdi]
0x18023059b  mov     rcx, rdi
0x18023059e  mov     rax, [rax]
0x1802305a1  call    cs:__guard_dispatch_icall_fptr
0x1802305a7  mov     eax, esi
  ... truncated ...
```
