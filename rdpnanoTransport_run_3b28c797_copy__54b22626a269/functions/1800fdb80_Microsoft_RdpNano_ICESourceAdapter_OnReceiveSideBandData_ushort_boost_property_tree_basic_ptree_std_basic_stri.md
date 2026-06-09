# Microsoft::RdpNano::ICESourceAdapter::OnReceiveSideBandData(ushort,boost::property_tree::basic_ptree<std::basic_string<char,std::char_traits<char>,std::allocator<char>>,boost::any,std::less<std::basic_string<char,std::char_traits<char>,std::allocator<char>>>> const &)

- ea: `0x1800fdb80`
- end: `0x1800fe7c5`
- name: `?OnReceiveSideBandData@ICESourceAdapter@RdpNano@Microsoft@@QEAAXGAEBV?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@Z`
- size: `3141`
- prototype: ``
- caller_count: `6`
- callee_count: `22`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800cab00`
- `0x1800d19a0`
- `0x1800e1a60`
- `0x1800e6990`
- `0x1800ee790`
- `0x1800efd68`

## callees

- `0x18000d9c0`
- `0x180015bb8`
- `0x180017380`
- `0x180018b94`
- `0x18001902c`
- `0x1800191b4`
- `0x18001979c`
- `0x18001acb8`
- `0x18001bd48`
- `0x18001dad8`
- `0x180024760`
- `0x180029d20`
- `0x1800c3524`
- `0x1800f3798`
- `0x1800f3d04`
- `0x1800fa064`
- `0x1800fdb80`
- `0x180233308`
- `0x180233af0`
- `0x18032f050`
- `0x18032f0b0`
- `0x180375c40`

## string_xrefs

- `0x1800fe1d5`: `SideBandData`
- `0x1800fe6af`: `SideBandData`
- `0x1800fdd3a`: `ICESourceAdapter::OnReceiveSideBandData(): packet for IceInitialCandidates type received again with same content, epoch=%d, m_epoch=%d`
- `0x1800fe398`: `ICESourceAdapter::OnReceiveSideBandData(): packet for IceInitialCandidates type received again with different content, epoch=%d, m_epoch=%d`
- `0x1800fde0c`: `ICESourceAdapter::OnReceiveSideBandData() type=%d, epoch=%d, m_epoch=%d`
- `0x1800fe1c9`: `ReceivedSideBandData`
- `0x1800fe6a3`: `ReceivedSideBandData`
- `0x1800fdc51`: `ICESourceAdapter::OnReceiveSideBandData(): packet from different epoches for IceInitialCandidates type, epoch=%d, m_epoch=%d`
- `0x1800fe480`: `ICESourceAdapter::OnReceiveSideBandData(): packet from an expired epoch, drop it: type=%d, epoch=%d, current epoch=%d`
- `0x1800fe50d`: `ICESourceAdapter::OnReceiveSideBandData() type=%d`

## pseudocode

```c
// Hidden C++ exception states: #wind=58
void __fastcall Microsoft::RdpNano::ICESourceAdapter::OnReceiveSideBandData(__int64 a1, __int16 a2, __int64 a3)
{
  unsigned int v5; // r14d
  int v6; // ecx
  unsigned __int8 v7; // r15
  int v8; // r9d
  char v9; // bl
  volatile signed __int32 *v10; // rbx
  __int64 v11; // rdx
  __int64 v12; // rax
  int v13; // r9d
  char v14; // bl
  volatile signed __int32 *v15; // rbx
  int v16; // r9d
  char v17; // bl
  volatile signed __int32 *v18; // rbx
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rdx
  __int64 v22; // rdx
  __int64 v23; // rax
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int64 v26; // rdx
  __int64 v27; // rax
  __int64 v28; // rdx
  __int64 v29; // rdx
  __int64 v30; // rdx
  volatile signed __int32 *v31; // rbx
  int v32; // r9d
  char v33; // bl
  int v34; // r9d
  char v35; // bl
  volatile signed __int32 *v36; // rbx
  __int64 v37; // rax
  __int64 v38; // rdx
  __int64 v39; // rdx
  __int64 v40; // rdx
  volatile signed __int32 *v41; // rbx
  int v42; // [rsp+20h] [rbp-E0h]
  char v43; // [rsp+50h] [rbp-B0h]
  __int128 v44; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v45; // [rsp+68h] [rbp-98h]
  __int128 v46; // [rsp+78h] [rbp-88h] BYREF
  __int128 v47; // [rsp+88h] [rbp-78h]
  __int128 v48; // [rsp+98h] [rbp-68h] BYREF
  __int128 v49; // [rsp+A8h] [rbp-58h]
  __int64 *v50; // [rsp+B8h] [rbp-48h]
  _BYTE v51[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v52[32]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v53[32]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v54[4]; // [rsp+120h] [rbp+20h] BYREF
  _OWORD v55[2]; // [rsp+140h] [rbp+40h] BYREF
  _OWORD v56[2]; // [rsp+160h] [rbp+60h] BYREF
  _OWORD v57[2]; // [rsp+180h] [rbp+80h] BYREF
  _OWORD v58[2]; // [rsp+1A0h] [rbp+A0h] BYREF
  _OWORD v59[2]; // [rsp+1C0h] [rbp+C0h] BYREF
  __int64 *v60; // [rsp+1E0h] [rbp+E0h]
  _BYTE v61[32]; // [rsp+1E8h] [rbp+E8h] BYREF
  __int64 v62[4]; // [rsp+208h] [rbp+108h] BYREF
  __int64 v63[4]; // [rsp+228h] [rbp+128h] BYREF
  __int64 v64[4]; // [rsp+248h] [rbp+148h] BYREF
  _BYTE v65[32]; // [rsp+268h] [rbp+168h] BYREF
  _BYTE v66[32]; // [rsp+288h] [rbp+188h] BYREF
  _BYTE v67[32]; // [rsp+2A8h] [rbp+1A8h] BYREF
  _BYTE v68[32]; // [rsp+2C8h] [rbp+1C8h] BYREF
  _BYTE v69[32]; // [rsp+2E8h] [rbp+1E8h] BYREF
  _BYTE v70[32]; // [rsp+308h] [rbp+208h] BYREF
  _BYTE v71[32]; // [rsp+328h] [rbp+228h] BYREF
  int v72[4]; // [rsp+348h] [rbp+248h] BYREF
  __int128 v73; // [rsp+358h] [rbp+258h]
  _OWORD v74[2]; // [rsp+368h] [rbp+268h] BYREF

  v5 = HIBYTE(a2) & 3;
  v6 = *(_BYTE *)(a1 + 327) & 3;
  v7 = a2 & 0xF;
  if ( (a2 & 0xF) != 0 )
  {
    *(_OWORD *)v72 = 0;
    if ( v6 != v5 )
    {
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(v72);
      if ( *(_QWORD *)v72 && *(_BYTE *)(*(_QWORD *)v72 + 128LL) )
      {
        v35 = *(_BYTE *)(a1 + 327);
        v44 = 0;
        v45 = 0;
        std::string::_Construct<1,char const *>(
          &v44,
          "ICESourceAdapter::OnReceiveSideBandData(): packet from an expired epoch, drop it: type=%d, epoch=%d, current epoch=%d",
          117,
          v34,
          v42);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,int,int,int>(
          (unsigned int)v72,
          (unsigned int)"RDPNANO",
          (unsigned int)&v44,
          v7,
          v5,
          v35);
        std::string::_Tidy_deallocate(&v44);
      }
      v10 = *(volatile signed __int32 **)&v72[2];
LABEL_46:
      if ( !v10 )
        return;
      goto LABEL_38;
    }
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v72);
    if ( *(_QWORD *)v72 && *(_BYTE *)(*(_QWORD *)v72 + 128LL) )
    {
      v44 = 0;
      v45 = 0;
      std::string::_Construct<1,char const *>(&v44, "ICESourceAdapter::OnReceiveSideBandData() type=%d", 49);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,int>(
        v72,
        "RDPNANO",
        &v44,
        v7);
      std::string::_Tidy_deallocate(&v44);
    }
    v36 = *(volatile signed __int32 **)&v72[2];
    if ( *(_QWORD *)&v72[2] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v72[2] + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v36)(v36);
        if ( _InterlockedExchangeAdd(v36 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v36 + 8LL))(v36);
      }
    }
    *(_OWORD *)v72 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v72);
    if ( *(_QWORD *)v72 && *(_BYTE *)(*(_QWORD *)v72 + 128LL) )
    {
      std::_Integral_to_string<char,int>(v51, v7);
      v46 = 0;
      v47 = 0;
      std::string::_Construct<1,char const *>(&v46, ":", 1);
      v48 = 0;
      v49 = 0;
      std::string::_Construct<1,char const *>(&v48, "\"", 1);
      v44 = 0;
      v45 = 0;
      std::string::_Construct<1,char const *>(&v44, "\"", 1);
      v37 = std::operator+<char>(v61, &v44, "type");
      LOBYTE(v38) = v43;
      std::string::string(v52, v38, v37, &v48);
      LOBYTE(v39) = v43;
      std::string::string(v53, v39, v52, &v46);
      LOBYTE(v40) = v43;
      std::string::string(v54, v40, v53, v51);
      Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string>(
        (int)v72,
        (int)"RD_CHECKPOINT",
        0,
        (int)"ICESourceAdapter",
        "SideBandData",
        "ReceivedSideBandData",
        (__int64)v54);
      std::string::_Tidy_deallocate(v53);
      std::string::_Tidy_deallocate(v52);
      std::string::_Tidy_deallocate(v61);
      std::string::_Tidy_deallocate(&v44);
      std::string::_Tidy_deallocate(&v48);
      std::string::_Tidy_deallocate(&v46);
      std::string::_Tidy_deallocate(v51);
    }
    v41 = *(volatile signed __int32 **)&v72[2];
    if ( *(_QWORD *)&v72[2] )
    {
      if ( !_InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)&v72[2] + 8LL)) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v41)(v41);
        if ( !_InterlockedDecrement(v41 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v41 + 8LL))(v41);
      }
    }
    if ( v7 == 1 )
    {
      Microsoft::Basix::Dct::ICECore::OnCloneInfoReceived(*(_QWORD *)(a1 + 168) + 64LL, a3);
    }
    else if ( v7 == 2 )
    {
      Microsoft::Basix::Dct::ICECore::OnCloneControlReceived(*(_QWORD *)(a1 + 168) + 64LL, a3);
    }
  }
  else
  {
    if ( v6 != v5 && v5 != v6 + 1 && ((a2 & 0x300) != 0 || v6 != 3) )
    {
      v74[0] = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(v74);
      if ( *(_QWORD *)&v74[0] && *(_BYTE *)(*(_QWORD *)&v74[0] + 128LL) )
      {
        v9 = *(_BYTE *)(a1 + 327);
        *(_OWORD *)v72 = 0;
        v73 = 0;
        std::string::_Construct<1,char const *>(
          v72,
          "ICESourceAdapter::OnReceiveSideBandData(): packet from different epoches for IceInitialCandidates type, epoch=%d, m_epoch=%d",
          124,
          v8);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,int,int>(
          (unsigned int)v74,
          (unsigned int)"RDPNANO",
          (unsigned int)v72,
          v5,
          v9);
        std::string::_Tidy_deallocate(v72);
      }
      v10 = (volatile signed __int32 *)*((_QWORD *)&v74[0] + 1);
      goto LABEL_46;
    }
    v11 = *(_QWORD *)(a1 + 192);
    if ( !*(_QWORD *)((v11 & -(__int64)(v11 != -17)) + 0x18) )
      goto LABEL_19;
    v12 = *(_QWORD *)((*(_QWORD *)(a3 + 8) & -(__int64)(*(_QWORD *)(a3 + 8) != -17)) + 0x18);
    v74[0] = 0;
    if ( *(_QWORD *)((v11 & -(__int64)(v11 != -17)) + 0x18) == v12 )
    {
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(v74);
      if ( *(_QWORD *)&v74[0] && *(_BYTE *)(*(_QWORD *)&v74[0] + 128LL) )
      {
        v14 = *(_BYTE *)(a1 + 327);
        *(_OWORD *)v72 = 0;
        v73 = 0;
        std::string::_Construct<1,char const *>(
          v72,
          "ICESourceAdapter::OnReceiveSideBandData(): packet for IceInitialCandidates type received again with same conte"
          "nt, epoch=%d, m_epoch=%d",
          134,
          v13);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,int,int>(
          (unsigned int)v74,
          (unsigned int)"RDPNANO",
          (unsigned int)v72,
          v5,
          v14);
        std::string::_Tidy_deallocate(v72);
      }
      v15 = (volatile signed __int32 *)*((_QWORD *)&v74[0] + 1);
      if ( *((_QWORD *)&v74[0] + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v74[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
          if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
        }
      }
LABEL_19:
      v74[0] = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v74);
      if ( *(_QWORD *)&v74[0] && *(_BYTE *)(*(_QWORD *)&v74[0] + 128LL) )
      {
        v17 = *(_BYTE *)(a1 + 327);
        *(_OWORD *)v72 = 0;
        v73 = 0;
        std::string::_Construct<1,char const *>(
          v72,
          "ICESourceAdapter::OnReceiveSideBandData() type=%d, epoch=%d, m_epoch=%d",
          71,
          v16,
          v42);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,int,int,int>(
          (unsigned int)v74,
          (unsigned int)"RDPNANO",
          (unsigned int)v72,
          0,
          v5,
          v17);
        std::string::_Tidy_deallocate(v72);
      }
      v18 = (volatile signed __int32 *)*((_QWORD *)&v74[0] + 1);
      if ( *((_QWORD *)&v74[0] + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v74[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
          if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
        }
      }
      *(_OWORD *)v72 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v72);
      if ( *(_QWORD *)v72 && *(_BYTE *)(*(_QWORD *)v72 + 128LL) )
      {
        v50 = v62;
        std::_Integral_to_string<char,int>(v54, *(unsigned __int8 *)(a1 + 327));
        v44 = 0;
        v45 = 0;
        std::string::_Construct<1,char const *>(&v44, ":", 1);
        v48 = 0;
        v49 = 0;
        std::string::_Construct<1,char const *>(&v48, "\"", 1);
        v46 = 0;
        v47 = 0;
        std::string::_Construct<1,char const *>(&v46, "\"", 1);
        v19 = std::operator+<char>(v61, &v46, "current Epoch");
        LOBYTE(v20) = v43;
        std::string::string(v53, v20, v19, &v48);
        LOBYTE(v21) = v43;
        std::string::string(v52, v21, v53, &v44);
        LOBYTE(v22) = v43;
        std::string::string(v62, v22, v52, v54);
        v60 = v63;
        std::_Integral_to_string<char,int>(v51, v5);
        memset(v59, 0, sizeof(v59));
        std::string::_Construct<1,char const *>(v59, ":", 1);
        memset(v58, 0, sizeof(v58));
        std::string::_Construct<1,char const *>(v58, "\"", 1);
        memset(v57, 0, sizeof(v57));
        std::string::_Construct<1,char const *>(v57, "\"", 1);
        v23 = std::operator+<char>(v71, v57, "newEpoch");
        LOBYTE(v24) = v43;
        std::string::string(v69, v24, v23, v58);
        LOBYTE(v25) = v43;
        std::string::string(v68, v25, v69, v59);
        LOBYTE(v26) = v43;
        std::string::string(v63, v26, v68, v51);
        std::_Integral_to_string<char,int>(v67, 0);
        memset(v56, 0, sizeof(v56));
        std::string::_Construct<1,char const *>(v56, ":", 1);
        memset(v74, 0, sizeof(v74));
        std::string::_Construct<1,char const *>(v74, "\"", 1);
        memset(v55, 0, sizeof(v55));
        std::string::_Construct<1,char const *>(v55, "\"", 1);
        v27 = std::operator+<char>(v70, v55, "type");
        LOBYTE(v28) = v43;
        std::string::string(v66, v28, v27, v74);
        LOBYTE(v29) = v43;
        std::string::string(v65, v29, v66, v56);
        LOBYTE(v30) = v43;
        std::string::string(v64, v30, v65, v67);
        Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string,std::string,std::string>(
          (int)v72,
          (int)"RD_CHECKPOINT",
          0,
          (int)"ICESourceAdapter",
          "SideBandData",
          "ReceivedSideBandData",
          (__int64)v64,
          (__int64)v63,
          (__int64)v62);
        std::string::_Tidy_deallocate(v65);
        std::string::_Tidy_deallocate(v66);
        std::string::_Tidy_deallocate(v70);
        std::string::_Tidy_deallocate(v55);
        std::string::_Tidy_deallocate(v74);
        std::string::_Tidy_deallocate(v56);
        std::string::_Tidy_deallocate(v67);
        std::string::_Tidy_deallocate(v68);
        std::string::_Tidy_deallocate(v69);
        std::string::_Tidy_deallocate(v71);
        std::string::_Tidy_deallocate(v57);
        std::string::_Tidy_deallocate(v58);
        std::string::_Tidy_deallocate(v59);
        std::string::_Tidy_deallocate(v51);
        std::string::_Tidy_deallocate(v52);
        std::string::_Tidy_deallocate(v53);
        std::string::_Tidy_deallocate(v61);
        std::string::_Tidy_deallocate(&v46);
        std::string::_Tidy_deallocate(&v48);
        std::string::_Tidy_deallocate(&v44);
        std::string::_Tidy_deallocate(v54);
      }
      v31 = *(volatile signed __int32 **)&v72[2];
      if ( *(_QWORD *)&v72[2] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v72[2] + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v31)(v31);
          if ( _InterlockedExchangeAdd(v31 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v31 + 8LL))(v31);
        }
      }
      boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::operator=(a1 + 184);
      *(_BYTE *)(a1 + 217) = 1;
      Microsoft::RdpNano::ICESourceAdapter::CheckBeginHandshake((Microsoft::RdpNano::ICESourceAdapter *)a1);
      return;
    }
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(v74);
    if ( *(_QWORD *)&v74[0] && *(_BYTE *)(*(_QWORD *)&v74[0] + 128LL) )
    {
      v33 = *(_BYTE *)(a1 + 327);
      *(_OWORD *)v72 = 0;
      v73 = 0;
      std::string::_Construct<1,char const *>(
        v72,
        "ICESourceAdapter::OnReceiveSideBandData(): packet for IceInitialCandidates type received again with different co"
        "ntent, epoch=%d, m_epoch=%d",
        139,
        v32);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,int,int>(
        (unsigned int)v74,
        (unsigned int)"RDPNANO",
        (unsigned int)v72,
        v5,
        v33);
      std::string::_Tidy_deallocate(v72);
    }
    v10 = (volatile signed __int32 *)*((_QWORD *)&v74[0] + 1);
    if ( *((_QWORD *)&v74[0] + 1) )
    {
LABEL_38:
      if ( !_InterlockedDecrement(v10 + 2) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
        if ( !_InterlockedDecrement(v10 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
      }
    }
  }
}

```

## disassembly

```asm
0x1800fdb80  mov     [rsp-8+arg_18], rbx
0x1800fdb85  push    rbp
0x1800fdb86  push    rsi
0x1800fdb87  push    rdi
0x1800fdb88  push    r12
0x1800fdb8a  push    r13
0x1800fdb8c  push    r14
0x1800fdb8e  push    r15
0x1800fdb90  lea     rbp, [rsp-290h]
0x1800fdb98  mov     eax, 390h
0x1800fdb9d  call    _alloca_probe
0x1800fdba2  sub     rsp, rax
0x1800fdba5  mov     rax, cs:__security_cookie
0x1800fdbac  xor     rax, rsp
0x1800fdbaf  mov     [rbp+2C0h+var_38], rax
0x1800fdbb6  mov     r13, r8
0x1800fdbb9  mov     rsi, rcx
0x1800fdbbc  xor     r12d, r12d
0x1800fdbbf  mov     r15b, dl
0x1800fdbc2  shr     dx, 8
0x1800fdbc6  and     dl, 3
0x1800fdbc9  movzx   r14d, dl
0x1800fdbcd  movzx   ecx, byte ptr [rcx+147h]
0x1800fdbd4  and     ecx, 3
0x1800fdbd7  and     r15b, 0Fh
0x1800fdbdb  jnz     loc_1800FE42D
0x1800fdbe1  cmp     ecx, r14d
0x1800fdbe4  jz      loc_1800FDCA0
0x1800fdbea  lea     eax, [rcx+1]
0x1800fdbed  cmp     r14d, eax
0x1800fdbf0  jz      loc_1800FDCA0
0x1800fdbf6  test    dl, dl
0x1800fdbf8  jnz     short loc_1800FDC03
0x1800fdbfa  cmp     ecx, 3
0x1800fdbfd  jz      loc_1800FDCA0
0x1800fdc03  xorps   xmm0, xmm0
0x1800fdc06  movups  [rbp+2C0h+var_58], xmm0
0x1800fdc0d  lea     rcx, [rbp+2C0h+var_58]
0x1800fdc14  call    ??$SelectEvent@VTraceWarning@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(void)
0x1800fdc19  nop
0x1800fdc1a  mov     rax, qword ptr [rbp+2C0h+var_58]
0x1800fdc21  test    rax, rax
0x1800fdc24  jz      short loc_1800FDC94
0x1800fdc26  cmp     [rax+80h], r12b
0x1800fdc2d  jz      short loc_1800FDC94
0x1800fdc2f  movzx   ebx, byte ptr [rsi+147h]
0x1800fdc36  xorps   xmm0, xmm0
0x1800fdc39  movups  xmmword ptr [rbp+2C0h+var_78], xmm0
0x1800fdc40  xorps   xmm1, xmm1
0x1800fdc43  movdqu  [rbp+2C0h+var_68], xmm1
0x1800fdc4b  mov     r8d, 7Ch ; '|'
0x1800fdc51  lea     rdx, aIcesourceadapt_5; "ICESourceAdapter::OnReceiveSideBandData"...
0x1800fdc58  lea     rcx, [rbp+2C0h+var_78]
0x1800fdc5f  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800fdc64  nop
0x1800fdc65  mov     dword ptr [rsp+3C0h+var_3A0], ebx
0x1800fdc69  mov     r9d, r14d
0x1800fdc6c  lea     r8, [rbp+2C0h+var_78]
0x1800fdc73  lea     rdx, aRdpnano; "RDPNANO"
0x1800fdc7a  lea     rcx, [rbp+2C0h+var_58]
0x1800fdc81  call    ??$TraceMessage@VTraceWarning@Basix@Microsoft@@HH@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@HH@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,int,int>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>> const &,char const *,std::string const &,int,int)
0x1800fdc86  nop
0x1800fdc87  lea     rcx, [rbp+2C0h+var_78]
0x1800fdc8e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800fdc93  nop
0x1800fdc94  mov     rbx, qword ptr [rbp+2C0h+var_58+8]
0x1800fdc9b  jmp     loc_1800FE4CA
0x1800fdca0  mov     rdx, [rsi+0C0h]
0x1800fdca7  lea     r8, [rdx+11h]
0x1800fdcab  mov     rax, r8
0x1800fdcae  neg     rax
0x1800fdcb1  sbb     rcx, rcx
0x1800fdcb4  and     rcx, rdx
0x1800fdcb7  or      edi, 0FFFFFFFFh
0x1800fdcba  cmp     [rcx+18h], r12
0x1800fdcbe  jz      loc_1800FDDBE
0x1800fdcc4  mov     rcx, [r13+8]
0x1800fdcc8  lea     rax, [rcx+11h]
0x1800fdccc  neg     rax
0x1800fdccf  sbb     rax, rax
0x1800fdcd2  and     rax, rcx
0x1800fdcd5  neg     r8
0x1800fdcd8  sbb     rcx, rcx
0x1800fdcdb  and     rcx, rdx
0x1800fdcde  mov     rax, [rax+18h]
0x1800fdce2  xorps   xmm0, xmm0
0x1800fdce5  movups  [rbp+2C0h+var_58], xmm0
0x1800fdcec  cmp     [rcx+18h], rax
0x1800fdcf0  lea     rcx, [rbp+2C0h+var_58]
0x1800fdcf7  jnz     loc_1800FE35B
0x1800fdcfd  call    ??$SelectEvent@VTraceWarning@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(void)
0x1800fdd02  nop
0x1800fdd03  mov     rax, qword ptr [rbp+2C0h+var_58]
0x1800fdd0a  test    rax, rax
0x1800fdd0d  jz      short loc_1800FDD7D
0x1800fdd0f  cmp     [rax+80h], r12b
0x1800fdd16  jz      short loc_1800FDD7D
0x1800fdd18  movzx   ebx, byte ptr [rsi+147h]
0x1800fdd1f  xorps   xmm0, xmm0
0x1800fdd22  movups  xmmword ptr [rbp+2C0h+var_78], xmm0
0x1800fdd29  xorps   xmm1, xmm1
0x1800fdd2c  movdqu  [rbp+2C0h+var_68], xmm1
0x1800fdd34  mov     r8d, 86h
0x1800fdd3a  lea     rdx, aIcesourceadapt_1; "ICESourceAdapter::OnReceiveSideBandData"...
0x1800fdd41  lea     rcx, [rbp+2C0h+var_78]
0x1800fdd48  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800fdd4d  nop
0x1800fdd4e  mov     dword ptr [rsp+3C0h+var_3A0], ebx
0x1800fdd52  mov     r9d, r14d
0x1800fdd55  lea     r8, [rbp+2C0h+var_78]
0x1800fdd5c  lea     rdx, aRdpnano; "RDPNANO"
0x1800fdd63  lea     rcx, [rbp+2C0h+var_58]
0x1800fdd6a  call    ??$TraceMessage@VTraceWarning@Basix@Microsoft@@HH@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@HH@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,int,int>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>> const &,char const *,std::string const &,int,int)
0x1800fdd6f  nop
0x1800fdd70  lea     rcx, [rbp+2C0h+var_78]
0x1800fdd77  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800fdd7c  nop
0x1800fdd7d  mov     rbx, qword ptr [rbp+2C0h+var_58+8]
0x1800fdd84  test    rbx, rbx
0x1800fdd87  jz      short loc_1800FDDBE
0x1800fdd89  mov     eax, edi
0x1800fdd8b  lock xadd [rbx+8], eax
0x1800fdd90  add     eax, edi
0x1800fdd92  jnz     short loc_1800FDDBE
0x1800fdd94  mov     rax, [rbx]
0x1800fdd97  mov     rcx, rbx
0x1800fdd9a  mov     rax, [rax]
0x1800fdd9d  call    cs:__guard_dispatch_icall_fptr
0x1800fdda3  mov     eax, edi
0x1800fdda5  lock xadd [rbx+0Ch], eax
0x1800fddaa  add     eax, edi
0x1800fddac  jnz     short loc_1800FDDBE
0x1800fddae  mov     rax, [rbx]
0x1800fddb1  mov     rcx, rbx
0x1800fddb4  mov     rax, [rax+8]
0x1800fddb8  call    cs:__guard_dispatch_icall_fptr
0x1800fddbe  xorps   xmm0, xmm0
0x1800fddc1  movups  [rbp+2C0h+var_58], xmm0
0x1800fddc8  lea     rcx, [rbp+2C0h+var_58]
0x1800fddcf  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x1800fddd4  nop
0x1800fddd5  mov     rax, qword ptr [rbp+2C0h+var_58]
0x1800fdddc  test    rax, rax
0x1800fdddf  jz      short loc_1800FDE54
0x1800fdde1  cmp     [rax+80h], r12b
0x1800fdde8  jz      short loc_1800FDE54
0x1800fddea  movzx   ebx, byte ptr [rsi+147h]
0x1800fddf1  xorps   xmm0, xmm0
0x1800fddf4  movups  xmmword ptr [rbp+2C0h+var_78], xmm0
0x1800fddfb  xorps   xmm1, xmm1
0x1800fddfe  movdqu  [rbp+2C0h+var_68], xmm1
0x1800fde06  mov     r8d, 47h ; 'G'
0x1800fde0c  lea     rdx, aIcesourceadapt_7; "ICESourceAdapter::OnReceiveSideBandData"...
0x1800fde13  lea     rcx, [rbp+2C0h+var_78]
0x1800fde1a  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800fde1f  nop
0x1800fde20  mov     dword ptr [rsp+3C0h+Str], ebx
0x1800fde24  mov     dword ptr [rsp+3C0h+var_3A0], r14d
0x1800fde29  xor     r9d, r9d
0x1800fde2c  lea     r8, [rbp+2C0h+var_78]
0x1800fde33  lea     rdx, aRdpnano; "RDPNANO"
0x1800fde3a  lea     rcx, [rbp+2C0h+var_58]
0x1800fde41  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@HHH@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@HHH@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,int,int,int>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &,int,int,int)
0x1800fde46  nop
0x1800fde47  lea     rcx, [rbp+2C0h+var_78]
0x1800fde4e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800fde53  nop
0x1800fde54  mov     rbx, qword ptr [rbp+2C0h+var_58+8]
0x1800fde5b  test    rbx, rbx
0x1800fde5e  jz      short loc_1800FDE95
0x1800fde60  mov     eax, edi
0x1800fde62  lock xadd [rbx+8], eax
0x1800fde67  add     eax, edi
0x1800fde69  jnz     short loc_1800FDE95
0x1800fde6b  mov     rax, [rbx]
0x1800fde6e  mov     rcx, rbx
0x1800fde71  mov     rax, [rax]
0x1800fde74  call    cs:__guard_dispatch_icall_fptr
0x1800fde7a  mov     eax, edi
0x1800fde7c  lock xadd [rbx+0Ch], eax
0x1800fde81  add     eax, edi
0x1800fde83  jnz     short loc_1800FDE95
0x1800fde85  mov     rax, [rbx]
0x1800fde88  mov     rcx, rbx
0x1800fde8b  mov     rax, [rax+8]
0x1800fde8f  call    cs:__guard_dispatch_icall_fptr
0x1800fde95  xorps   xmm0, xmm0
0x1800fde98  movups  xmmword ptr [rbp+2C0h+var_78], xmm0
0x1800fde9f  lea     rcx, [rbp+2C0h+var_78]
0x1800fdea6  call    ??$SelectEvent@VTraceCheckpoint@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(void)
0x1800fdeab  nop
0x1800fdeac  mov     r12d, 1
0x1800fdeb2  mov     rax, qword ptr [rbp+2C0h+var_78]
0x1800fdeb9  test    rax, rax
0x1800fdebc  jz      loc_1800FE2F7
0x1800fdec2  cmp     byte ptr [rax+80h], 0
0x1800fdec9  jz      loc_1800FE2F7
0x1800fdecf  lea     rax, [rbp+2C0h+var_1B8]
0x1800fded6  mov     [rbp+2C0h+var_308], rax
0x1800fdeda  movzx   edx, byte ptr [rsi+147h]
0x1800fdee1  lea     rcx, [rbp+2C0h+var_2A0]
0x1800fdee5  call    ??$_Integral_to_string@DH@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@H@Z; std::_Integral_to_string<char,int>(int)
0x1800fdeea  nop
0x1800fdeeb  xorps   xmm0, xmm0
0x1800fdeee  movups  [rsp+3C0h+var_368], xmm0
0x1800fdef3  xorps   xmm1, xmm1
0x1800fdef6  movdqu  [rsp+3C0h+var_358], xmm1
0x1800fdefc  mov     r8d, r12d
0x1800fdeff  lea     rdx, asc_1803D71C4; ":"
0x1800fdf06  lea     rcx, [rsp+3C0h+var_368]
0x1800fdf0b  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800fdf10  nop
0x1800fdf11  xorps   xmm0, xmm0
0x1800fdf14  movups  [rbp+2C0h+var_328], xmm0
0x1800fdf18  xorps   xmm1, xmm1
0x1800fdf1b  movdqu  [rbp+2C0h+var_318], xmm1
0x1800fdf20  mov     r8d, r12d
0x1800fdf23  lea     rbx, asc_1803D71C8; "\""
0x1800fdf2a  mov     rdx, rbx
0x1800fdf2d  lea     rcx, [rbp+2C0h+var_328]
0x1800fdf31  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800fdf36  nop
0x1800fdf37  xorps   xmm0, xmm0
0x1800fdf3a  movups  [rsp+3C0h+var_348], xmm0
0x1800fdf3f  xorps   xmm1, xmm1
0x1800fdf42  movdqu  [rbp+2C0h+var_338], xmm1
0x1800fdf47  mov     r8d, r12d
0x1800fdf4a  mov     rdx, rbx
0x1800fdf4d  lea     rcx, [rsp+3C0h+var_348]
0x1800fdf52  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800fdf57  nop
0x1800fdf58  lea     r8, aCurrentEpoch; "current Epoch"
0x1800fdf5f  lea     rdx, [rsp+3C0h+var_348]
0x1800fdf64  lea     rcx, [rbp+2C0h+var_1D8]
0x1800fdf6b  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x1800fdf70  nop
0x1800fdf71  lea     r9, [rbp+2C0h+var_328]
0x1800fdf75  mov     r8, rax
0x1800fdf78  mov     dl, [rsp+3C0h+var_370]
0x1800fdf7c  lea     rcx, [rbp+2C0h+var_2C0]
0x1800fdf80  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x1800fdf85  nop
0x1800fdf86  lea     r9, [rsp+3C0h+var_368]
0x1800fdf8b  lea     r8, [rbp+2C0h+var_2C0]
0x1800fdf8f  mov     dl, [rsp+3C0h+var_370]
0x1800fdf93  lea     rcx, [rbp+2C0h+var_2E0]
0x1800fdf97  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x1800fdf9c  nop
0x1800fdf9d  lea     r9, [rbp+2C0h+var_2A0]
0x1800fdfa1  lea     r8, [rbp+2C0h+var_2E0]
0x1800fdfa5  mov     dl, [rsp+3C0h+var_370]
0x1800fdfa9  lea     rcx, [rbp+2C0h+var_1B8]
0x1800fdfb0  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x1800fdfb5  nop
0x1800fdfb6  lea     rax, [rbp+2C0h+var_198]
0x1800fdfbd  mov     [rbp+2C0h+var_1E0], rax
0x1800fdfc4  mov     edx, r14d
0x1800fdfc7  lea     rcx, [rbp+2C0h+var_300]
0x1800fdfcb  call    ??$_Integral_to_string@DH@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@H@Z; std::_Integral_to_string<char,int>(int)
0x1800fdfd0  nop
0x1800fdfd1  xorps   xmm0, xmm0
0x1800fdfd4  movups  [rbp+2C0h+var_200], xmm0
0x1800fdfdb  xorps   xmm1, xmm1
0x1800fdfde  movdqu  [rbp+2C0h+var_1F0], xmm1
0x1800fdfe6  mov     r8d, r12d
0x1800fdfe9  lea     rdx, asc_1803D71C4; ":"
0x1800fdff0  lea     rcx, [rbp+2C0h+var_200]
0x1800fdff7  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800fdffc  nop
0x1800fdffd  xorps   xmm0, xmm0
0x1800fe000  movups  [rbp+2C0h+var_220], xmm0
0x1800fe007  xorps   xmm1, xmm1
0x1800fe00a  movdqu  [rbp+2C0h+var_210], xmm1
0x1800fe012  mov     r8d, r12d
0x1800fe015  mov     rdx, rbx
0x1800fe018  lea     rcx, [rbp+2C0h+var_220]
0x1800fe01f  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800fe024  nop
0x1800fe025  xorps   xmm0, xmm0
0x1800fe028  movups  [rbp+2C0h+var_240], xmm0
0x1800fe02f  xorps   xmm1, xmm1
0x1800fe032  movdqu  [rbp+2C0h+var_230], xmm1
0x1800fe03a  mov     r8d, r12d
0x1800fe03d  mov     rdx, rbx
0x1800fe040  lea     rcx, [rbp+2C0h+var_240]
0x1800fe047  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800fe04c  nop
0x1800fe04d  lea     r8, aNewepoch; "newEpoch"
0x1800fe054  lea     rdx, [rbp+2C0h+var_240]
0x1800fe05b  lea     rcx, [rbp+2C0h+var_98]
0x1800fe062  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x1800fe067  nop
0x1800fe068  lea     r9, [rbp+2C0h+var_220]
0x1800fe06f  mov     r8, rax
0x1800fe072  mov     dl, [rsp+3C0h+var_370]
0x1800fe076  lea     rcx, [rbp+2C0h+var_D8]
0x1800fe07d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x1800fe082  nop
0x1800fe083  lea     r9, [rbp+2C0h+var_200]
0x1800fe08a  lea     r8, [rbp+2C0h+var_D8]
  ... truncated ...
```
