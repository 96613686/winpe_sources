# Microsoft::Basix::Dct::SmilesV3::SetInitialPrimaryOutLink(void)

- ea: `0x18027c814`
- end: `0x18027d3c4`
- name: `?SetInitialPrimaryOutLink@SmilesV3@Dct@Basix@Microsoft@@AEAA_NXZ`
- size: `2992`
- prototype: `bool __fastcall(Microsoft::Basix::Dct::SmilesV3 *__hidden this)`
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180261ba0`

## callees

- `0x180008f80`
- `0x18000d9c0`
- `0x180015bb8`
- `0x180017380`
- `0x180018b94`
- `0x18001902c`
- `0x1800191b4`
- `0x18001c258`
- `0x18001db78`
- `0x180024760`
- `0x180028100`
- `0x18002a8f4`
- `0x1800448dc`
- `0x18004e1dc`
- `0x1800c3524`
- `0x1800d621c`
- `0x1800dcae4`
- `0x1801d43a4`
- `0x180250a78`
- `0x18027c814`
- `0x18032f050`
- `0x18032f0b0`
- `0x180330b40`
- `0x180375c40`

## string_xrefs

- `0x18027d05b`: `LinkSwitch`
- `0x18027c8d1`: `matching inLink which is bidirectional normal`
- `0x18027c9c9`: `arbitrary link which is bidirectional normal`
- `0x18027ca64`: `arbitrary link which is inbound normal`
- `0x18027cb72`: `smiles: initially Set primary outLink to %s: (%d)0x%llx, className('%s')`
- `0x18027d04f`: `SetInitialPrimaryOutLink`
- `0x18027d27c`: `smiles: initially Set primary outLink failed with links side=%d`

## pseudocode

```c
// Hidden C++ exception states: #wind=63
char __fastcall Microsoft::Basix::Dct::SmilesV3::SetInitialPrimaryOutLink(Microsoft::Basix::Dct::SmilesV3 *this)
{
  char v2; // r12
  __int64 *v3; // r14
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // r15
  volatile signed __int32 *v7; // r14
  __m128i v8; // xmm1
  __int64 v9; // rsi
  __int64 *v10; // rax
  __int64 v11; // rcx
  volatile signed __int32 *v12; // rbx
  __int64 v13; // rbx
  __int64 v14; // rsi
  int v15; // r9d
  int v16; // ebx
  __int128 *v17; // rdi
  volatile signed __int32 *v18; // rbx
  __int64 v19; // rbx
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rdx
  __int64 v29; // rdx
  __int128 *v30; // rbx
  __int64 v31; // rax
  __int64 v32; // rdx
  __int64 v33; // rdx
  __int64 v34; // rdx
  __int64 v35; // rax
  __int64 v36; // rdx
  volatile signed __int32 *v37; // rbx
  __int64 v38; // rbx
  volatile signed __int32 *v39; // rbx
  char *v41; // [rsp+20h] [rbp-E0h]
  char *Str; // [rsp+28h] [rbp-D8h]
  char v43; // [rsp+50h] [rbp-B0h]
  __m128i v44; // [rsp+60h] [rbp-A0h] BYREF
  __int64 *v45; // [rsp+70h] [rbp-90h]
  __int128 v46; // [rsp+78h] [rbp-88h] BYREF
  __int128 v47; // [rsp+88h] [rbp-78h]
  _OWORD v48[2]; // [rsp+98h] [rbp-68h] BYREF
  _OWORD v49[2]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v50[32]; // [rsp+D8h] [rbp-28h] BYREF
  _OWORD v51[2]; // [rsp+F8h] [rbp-8h] BYREF
  _OWORD v52[2]; // [rsp+118h] [rbp+18h] BYREF
  _OWORD v53[2]; // [rsp+138h] [rbp+38h] BYREF
  _OWORD v54[2]; // [rsp+158h] [rbp+58h] BYREF
  _OWORD v55[2]; // [rsp+178h] [rbp+78h] BYREF
  _OWORD v56[2]; // [rsp+198h] [rbp+98h] BYREF
  _OWORD v57[2]; // [rsp+1B8h] [rbp+B8h] BYREF
  _OWORD v58[2]; // [rsp+1D8h] [rbp+D8h] BYREF
  _OWORD v59[2]; // [rsp+1F8h] [rbp+F8h] BYREF
  __int64 *v60; // [rsp+218h] [rbp+118h]
  _BYTE v61[32]; // [rsp+220h] [rbp+120h] BYREF
  _BYTE v62[32]; // [rsp+240h] [rbp+140h] BYREF
  __int64 v63[4]; // [rsp+260h] [rbp+160h] BYREF
  __int64 v64[4]; // [rsp+280h] [rbp+180h] BYREF
  __int64 v65[4]; // [rsp+2A0h] [rbp+1A0h] BYREF
  _BYTE v66[32]; // [rsp+2C0h] [rbp+1C0h] BYREF
  _BYTE v67[32]; // [rsp+2E0h] [rbp+1E0h] BYREF
  _BYTE v68[32]; // [rsp+300h] [rbp+200h] BYREF
  _BYTE v69[32]; // [rsp+320h] [rbp+220h] BYREF
  _BYTE v70[32]; // [rsp+340h] [rbp+240h] BYREF
  _BYTE v71[32]; // [rsp+360h] [rbp+260h] BYREF
  _BYTE v72[32]; // [rsp+380h] [rbp+280h] BYREF
  _BYTE v73[32]; // [rsp+3A0h] [rbp+2A0h] BYREF
  _BYTE v74[32]; // [rsp+3C0h] [rbp+2C0h] BYREF
  _BYTE v75[32]; // [rsp+3E0h] [rbp+2E0h] BYREF
  _BYTE v76[32]; // [rsp+400h] [rbp+300h] BYREF
  _BYTE v77[32]; // [rsp+420h] [rbp+320h] BYREF
  __m128i pExceptionObject; // [rsp+440h] [rbp+340h] BYREF
  _OWORD v79[2]; // [rsp+460h] [rbp+360h] BYREF
  __int128 v80; // [rsp+480h] [rbp+380h] BYREF
  __m128i si128; // [rsp+490h] [rbp+390h]

  v2 = 0;
  if ( !(unsigned __int8)std::operator==<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>>(
                           *((_QWORD *)this + 227),
                           0) )
    return v2;
  v80 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v80) = 0;
  v44 = 0;
  v3 = (__int64 *)*((_QWORD *)this + 228);
  v4 = *v3;
  if ( !*v3 || *(_DWORD *)(v4 + 280) || *(_DWORD *)(v4 + 284) )
  {
    v8 = _mm_load_si128(&v44);
    v7 = (volatile signed __int32 *)_mm_srli_si128(v8, 8).m128i_u64[0];
    v6 = v8.m128i_i64[0];
    goto LABEL_10;
  }
  v5 = v3[1];
  if ( v5 )
    _InterlockedIncrement((volatile signed __int32 *)(v5 + 8));
  v44.m128i_i64[0] = *v3;
  v6 = v44.m128i_i64[0];
  v7 = (volatile signed __int32 *)v3[1];
  v44.m128i_i64[1] = (__int64)v7;
  std::string::assign(&v80, "matching inLink which is bidirectional normal");
  if ( !v44.m128i_i64[0] )
  {
LABEL_10:
    v79[0] = 0;
    Microsoft::Basix::Containers::IterationSafeStore<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>,std::equal_to<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>>>::iterator::iterator(
      v79,
      (char *)this + 1528);
    pExceptionObject = 0;
    while ( 1 )
    {
      v9 = *(_QWORD *)&v79[0];
      if ( !*(_QWORD *)&v79[0] )
        break;
      v10 = (__int64 *)*((_QWORD *)&v79[0] + 1);
      if ( !*(_QWORD *)(**((_QWORD **)&v79[0] + 1) + 280LL) )
      {
        v11 = *(_QWORD *)(*((_QWORD *)&v79[0] + 1) + 8LL);
        if ( v11 )
          _InterlockedIncrement((volatile signed __int32 *)(v11 + 8));
        v6 = *v10;
        v44.m128i_i64[0] = *v10;
        v12 = v7;
        v7 = (volatile signed __int32 *)v10[1];
        v44.m128i_i64[1] = (__int64)v7;
        if ( v12 )
        {
          if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
            if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
          }
        }
        std::string::assign(&v80, "arbitrary link which is bidirectional normal");
        break;
      }
      Microsoft::Basix::Containers::IterationSafeStore<std::weak_ptr<Microsoft::Basix::Instrumentation::IActivityListener>,Microsoft::Basix::Algorithm::owner_equals<std::weak_ptr<Microsoft::Basix::Instrumentation::IActivityListener>>>::iterator::operator++(v79);
    }
    if ( v9
      && _InterlockedExchangeAdd(
           (volatile signed __int32 *)(*(__int64 (__fastcall **)(__int64))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)(v9 + 80),
           0xFFFFFFFF) == -1 )
    {
      std::runtime_error::runtime_error((std::runtime_error *)&pExceptionObject, "Unbalanced endIteration()");
      throw (std::runtime_error *)&pExceptionObject;
    }
  }
  if ( v6 )
    goto LABEL_32;
  v79[0] = 0;
  Microsoft::Basix::Containers::IterationSafeStore<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>,std::equal_to<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>>>::iterator::iterator(
    v79,
    (char *)this + 1528);
  pExceptionObject = 0;
  while ( 1 )
  {
    v13 = *(_QWORD *)&v79[0];
    if ( !*(_QWORD *)&v79[0] )
      break;
    if ( !*(_DWORD *)(**((_QWORD **)&v79[0] + 1) + 280LL) )
    {
      std::shared_ptr<Microsoft::RdpNano::RendezvousSource::RendezvousContext>::operator=(
        &v44,
        *((_QWORD *)&v79[0] + 1));
      std::string::assign(&v80, "arbitrary link which is inbound normal");
      v7 = (volatile signed __int32 *)v44.m128i_i64[1];
      v6 = v44.m128i_i64[0];
      break;
    }
    Microsoft::Basix::Containers::IterationSafeStore<std::weak_ptr<Microsoft::Basix::Instrumentation::IActivityListener>,Microsoft::Basix::Algorithm::owner_equals<std::weak_ptr<Microsoft::Basix::Instrumentation::IActivityListener>>>::iterator::operator++(v79);
  }
  if ( v13
    && _InterlockedExchangeAdd(
         (volatile signed __int32 *)(*(__int64 (__fastcall **)(__int64))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)(v13 + 80),
         0xFFFFFFFF) == -1 )
  {
    std::runtime_error::runtime_error((std::runtime_error *)&pExceptionObject, "Unbalanced endIteration()");
    throw (std::runtime_error *)&pExceptionObject;
  }
  if ( v6 )
  {
LABEL_32:
    pExceptionObject = 0;
    if ( v7 )
      _InterlockedIncrement(v7 + 2);
    pExceptionObject = v44;
    if ( (unsigned __int8)Microsoft::Basix::Dct::Smiles<Microsoft::Basix::Dct::LinkDataDisabled>::ChangePrimary(
                            this,
                            &pExceptionObject,
                            0) )
    {
      v79[0] = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v79);
      if ( *(_QWORD *)&v79[0] && *(_BYTE *)(*(_QWORD *)&v79[0] + 128LL) )
      {
        v45 = (__int64 *)v50;
        v14 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(v6 + 104) + 104LL))(*(_QWORD *)(v6 + 104), v50);
        v16 = *(_DWORD *)(v6 + 152);
        v17 = &v80;
        if ( si128.m128i_i64[1] > 0xFuLL )
          LODWORD(v17) = v80;
        memset(&pExceptionObject, 0, 32);
        std::string::_Construct<1,char const *>(
          &pExceptionObject,
          "smiles: initially Set primary outLink to %s: (%d)0x%llx, className('%s')",
          (const char *)0x48,
          v15,
          v41,
          Str);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,char const *,unsigned int,Microsoft::Basix::Dct::LinkDataV3 *,std::string>(
          (unsigned int)v79,
          (unsigned int)"BASIX_DCT",
          (unsigned int)&pExceptionObject,
          (_DWORD)v17,
          v16,
          v6,
          v14);
        std::string::_Tidy_deallocate(&pExceptionObject);
      }
      v18 = (volatile signed __int32 *)*((_QWORD *)&v79[0] + 1);
      if ( *((_QWORD *)&v79[0] + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v79[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
          if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
        }
      }
      pExceptionObject = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(&pExceptionObject);
      if ( pExceptionObject.m128i_i64[0] && *(_BYTE *)(pExceptionObject.m128i_i64[0] + 128) )
      {
        v45 = v63;
        v46 = 0;
        v47 = 0;
        std::string::_Construct<1,char const *>(&v46, "\"", 1);
        v19 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(v6 + 104) + 104LL))(*(_QWORD *)(v6 + 104), v77);
        memset(v49, 0, sizeof(v49));
        std::string::_Construct<1,char const *>(v49, "\"", 1);
        memset(v48, 0, sizeof(v48));
        std::string::_Construct<1,char const *>(v48, ":", 1);
        memset(v59, 0, sizeof(v59));
        std::string::_Construct<1,char const *>(v59, "\"", 1);
        memset(v58, 0, sizeof(v58));
        std::string::_Construct<1,char const *>(v58, "\"", 1);
        v20 = std::operator+<char>(v76, v58, "channelName");
        LOBYTE(v21) = v43;
        std::string::string(v50, v21, v20, v59);
        LOBYTE(v22) = v43;
        std::string::string(v62, v22, v50, v48);
        LOBYTE(v23) = v43;
        std::string::string(v61, v23, v62, v49);
        LOBYTE(v24) = v43;
        std::string::string(v72, v24, v61, v19);
        LOBYTE(v25) = v43;
        std::string::string(v63, v25, v72, &v46);
        v60 = v64;
        std::_Integral_to_string<char,unsigned int>(v71, *(unsigned int *)(v6 + 152));
        memset(v57, 0, sizeof(v57));
        std::string::_Construct<1,char const *>(v57, ":", 1);
        memset(v56, 0, sizeof(v56));
        std::string::_Construct<1,char const *>(v56, "\"", 1);
        memset(v55, 0, sizeof(v55));
        std::string::_Construct<1,char const *>(v55, "\"", 1);
        v26 = std::operator+<char>(v75, v55, "id");
        LOBYTE(v27) = v43;
        std::string::string(v70, v27, v26, v56);
        LOBYTE(v28) = v43;
        std::string::string(v69, v28, v70, v57);
        LOBYTE(v29) = v43;
        std::string::string(v64, v29, v69, v71);
        memset(v54, 0, sizeof(v54));
        std::string::_Construct<1,char const *>(v54, "\"", 1);
        v30 = &v80;
        if ( si128.m128i_i64[1] > 0xFuLL )
          v30 = (__int128 *)v80;
        memset(v53, 0, sizeof(v53));
        std::string::_Construct<1,char const *>(v53, "\"", 1);
        memset(v52, 0, sizeof(v52));
        std::string::_Construct<1,char const *>(v52, ":", 1);
        memset(v79, 0, sizeof(v79));
        std::string::_Construct<1,char const *>(v79, "\"", 1);
        memset(v51, 0, sizeof(v51));
        std::string::_Construct<1,char const *>(v51, "\"", 1);
        v31 = std::operator+<char>(v74, v51, "source");
        LOBYTE(v32) = v43;
        std::string::string(v68, v32, v31, v79);
        LOBYTE(v33) = v43;
        std::string::string(v67, v33, v68, v52);
        LOBYTE(v34) = v43;
        std::string::string(v66, v34, v67, v53);
        v35 = std::operator+<char>(v73, v66, v30);
        LOBYTE(v36) = v43;
        std::string::string(v65, v36, v35, v54);
        Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string,std::string,std::string>(
          (int)&pExceptionObject,
          (int)"RD_CHECKPOINT",
          0,
          (int)"Smiles",
          "LinkSwitch",
          "SetInitialPrimaryOutLink",
          (__int64)v65,
          (__int64)v64,
          (__int64)v63);
        std::string::_Tidy_deallocate(v73);
        std::string::_Tidy_deallocate(v66);
        std::string::_Tidy_deallocate(v67);
        std::string::_Tidy_deallocate(v68);
        std::string::_Tidy_deallocate(v74);
        std::string::_Tidy_deallocate(v51);
        std::string::_Tidy_deallocate(v79);
        std::string::_Tidy_deallocate(v52);
        std::string::_Tidy_deallocate(v53);
        std::string::_Tidy_deallocate(v54);
        std::string::_Tidy_deallocate(v69);
        std::string::_Tidy_deallocate(v70);
        std::string::_Tidy_deallocate(v75);
        std::string::_Tidy_deallocate(v55);
        std::string::_Tidy_deallocate(v56);
        std::string::_Tidy_deallocate(v57);
        std::string::_Tidy_deallocate(v71);
        std::string::_Tidy_deallocate(v72);
        std::string::_Tidy_deallocate(v61);
        std::string::_Tidy_deallocate(v62);
        std::string::_Tidy_deallocate(v50);
        std::string::_Tidy_deallocate(v76);
        std::string::_Tidy_deallocate(v58);
        std::string::_Tidy_deallocate(v59);
        std::string::_Tidy_deallocate(v48);
        std::string::_Tidy_deallocate(v49);
        std::string::_Tidy_deallocate(v77);
        std::string::_Tidy_deallocate(&v46);
      }
      v37 = (volatile signed __int32 *)pExceptionObject.m128i_i64[1];
      if ( pExceptionObject.m128i_i64[1] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(pExceptionObject.m128i_i64[1] + 8), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v37)(v37);
          if ( _InterlockedExchangeAdd(v37 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v37 + 8LL))(v37);
        }
      }
      v2 = 1;
    }
  }
  else
  {
    pExceptionObject = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(&pExceptionObject);
    if ( pExceptionObject.m128i_i64[0] && *(_BYTE *)(pExceptionObject.m128i_i64[0] + 128) )
    {
      v38 = Microsoft::Basix::Containers::IterationSafeStore<std::shared_ptr<Microsoft::Basix::Dct::LinkDataDisabled>,std::equal_to<std::shared_ptr<Microsoft::Basix::Dct::LinkDataDisabled>>>::size((char *)this + 1528);
      v46 = 0;
      v47 = 0;
      std::string::_Construct<1,char const *>(
        &v46,
        "smiles: initially Set primary outLink failed with links side=%d",
        63);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,unsigned __int64>(
        &pExceptionObject,
        "BASIX_DCT",
        &v46,
        v38);
      std::string::_Tidy_deallocate(&v46);
    }
    v39 = (volatile signed __int32 *)pExceptionObject.m128i_i64[1];
    if ( pExceptionObject.m128i_i64[1] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(pExceptionObject.m128i_i64[1] + 8), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v39)(v39);
        if ( _InterlockedExchangeAdd(v39 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v39 + 8LL))(v39);
      }
    }
  }
  if ( v7 )
  {
    if ( _InterlockedExchangeAdd(v7 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
      if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
    }
  }
  std::string::_Tidy_deallocate(&v80);
  return v2;
}

```

## disassembly

```asm
0x18027c814  mov     [rsp-8+arg_8], rbx
0x18027c819  mov     [rsp-8+arg_10], rsi
0x18027c81e  push    rbp
0x18027c81f  push    rdi
0x18027c820  push    r12
0x18027c822  push    r14
0x18027c824  push    r15
0x18027c826  lea     rbp, [rsp-3B0h]
0x18027c82e  mov     eax, 4B0h
0x18027c833  call    _alloca_probe
0x18027c838  sub     rsp, rax
0x18027c83b  mov     rax, cs:__security_cookie
0x18027c842  xor     rax, rsp
0x18027c845  mov     [rbp+3D0h+var_30], rax
0x18027c84c  mov     rdi, rcx
0x18027c84f  xor     r12b, r12b
0x18027c852  xor     edx, edx
0x18027c854  mov     rcx, [rcx+718h]
0x18027c85b  call    ??$?8V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@YA_NAEBV?$shared_ptr@V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@0@$$T@Z; std::operator==<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>> const &,std::nullptr_t)
0x18027c860  test    al, al
0x18027c862  jz      loc_18027D348
0x18027c868  xorps   xmm0, xmm0
0x18027c86b  movups  [rbp+3D0h+var_50], xmm0
0x18027c872  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x18027c87a  movdqu  [rbp+3D0h+var_40], xmm1
0x18027c882  mov     byte ptr [rbp+3D0h+var_50], r12b
0x18027c889  xorps   xmm1, xmm1
0x18027c88c  movdqa  [rsp+4D0h+var_470], xmm1
0x18027c892  mov     r14, [rdi+720h]
0x18027c899  mov     rax, [r14]
0x18027c89c  test    rax, rax
0x18027c89f  jz      short loc_18027C8EE
0x18027c8a1  cmp     dword ptr [rax+118h], 0
0x18027c8a8  jnz     short loc_18027C8EE
0x18027c8aa  cmp     dword ptr [rax+11Ch], 0
0x18027c8b1  jnz     short loc_18027C8EE
0x18027c8b3  mov     rax, [r14+8]
0x18027c8b7  test    rax, rax
0x18027c8ba  jz      short loc_18027C8C0
0x18027c8bc  lock inc dword ptr [rax+8]
0x18027c8c0  mov     r15, [r14]
0x18027c8c3  mov     qword ptr [rsp+4D0h+var_470], r15
0x18027c8c8  mov     r14, [r14+8]
0x18027c8cc  mov     qword ptr [rsp+4D0h+var_470+8], r14
0x18027c8d1  lea     rdx, aMatchingInlink; "matching inLink which is bidirectional "...
0x18027c8d8  lea     rcx, [rbp+3D0h+var_50]
0x18027c8df  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD@Z; std::string::assign(char const * const)
0x18027c8e4  test    r15, r15
0x18027c8e7  jz      short loc_18027C907
0x18027c8e9  jmp     loc_18027C9FB
0x18027c8ee  movdqa  xmm1, [rsp+4D0h+var_470]
0x18027c8f4  movdqa  xmm0, xmm1
0x18027c8f8  psrldq  xmm0, 8
0x18027c8fd  movq    r14, xmm0
0x18027c902  movq    r15, xmm1
0x18027c907  xorps   xmm0, xmm0
0x18027c90a  movups  [rbp+3D0h+var_70], xmm0
0x18027c911  lea     rdx, [rdi+5F8h]
0x18027c918  lea     rcx, [rbp+3D0h+var_70]
0x18027c91f  call    ??0iterator@?$IterationSafeStore@V?$shared_ptr@VTransport@FailoverBridge@Dct@Basix@Microsoft@@@std@@U?$equal_to@V?$shared_ptr@VTransport@FailoverBridge@Dct@Basix@Microsoft@@@std@@@2@@Containers@Basix@Microsoft@@QEAA@PEBV1234@@Z; Microsoft::Basix::Containers::IterationSafeStore<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>,std::equal_to<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>>>::iterator::iterator(Microsoft::Basix::Containers::IterationSafeStore<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>,std::equal_to<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>>> const *)
0x18027c924  nop
0x18027c925  xorps   xmm1, xmm1
0x18027c928  movdqu  [rbp+3D0h+pExceptionObject], xmm1
0x18027c930  mov     rsi, qword ptr [rbp+3D0h+var_70]
0x18027c937  test    rsi, rsi
0x18027c93a  jz      loc_18027C9DD
0x18027c940  mov     rax, qword ptr [rbp+3D0h+var_70+8]
0x18027c947  mov     rcx, [rax]
0x18027c94a  cmp     dword ptr [rcx+11Ch], 0
0x18027c951  jnz     short loc_18027C95C
0x18027c953  cmp     dword ptr [rcx+118h], 0
0x18027c95a  jz      short loc_18027C96A
0x18027c95c  lea     rcx, [rbp+3D0h+var_70]
0x18027c963  call    ??Eiterator@?$IterationSafeStore@V?$weak_ptr@VIActivityListener@Instrumentation@Basix@Microsoft@@@std@@U?$owner_equals@V?$weak_ptr@VIActivityListener@Instrumentation@Basix@Microsoft@@@std@@@Algorithm@Basix@Microsoft@@@Containers@Basix@Microsoft@@QEAAAEAV01234@XZ; Microsoft::Basix::Containers::IterationSafeStore<std::weak_ptr<Microsoft::Basix::Instrumentation::IActivityListener>,Microsoft::Basix::Algorithm::owner_equals<std::weak_ptr<Microsoft::Basix::Instrumentation::IActivityListener>>>::iterator::operator++(void)
0x18027c968  jmp     short loc_18027C930
0x18027c96a  mov     rcx, [rax+8]
0x18027c96e  test    rcx, rcx
0x18027c971  jz      short loc_18027C977
0x18027c973  lock inc dword ptr [rcx+8]
0x18027c977  mov     r15, [rax]
0x18027c97a  mov     qword ptr [rsp+4D0h+var_470], r15
0x18027c97f  mov     rbx, r14
0x18027c982  mov     r14, [rax+8]
0x18027c986  mov     qword ptr [rsp+4D0h+var_470+8], r14
0x18027c98b  test    rbx, rbx
0x18027c98e  jz      short loc_18027C9C9
0x18027c990  or      eax, 0FFFFFFFFh
0x18027c993  lock xadd [rbx+8], eax
0x18027c998  cmp     eax, 1
0x18027c99b  jnz     short loc_18027C9C9
0x18027c99d  mov     rax, [rbx]
0x18027c9a0  mov     rcx, rbx
0x18027c9a3  mov     rax, [rax]
0x18027c9a6  call    cs:__guard_dispatch_icall_fptr
0x18027c9ac  or      eax, 0FFFFFFFFh
0x18027c9af  lock xadd [rbx+0Ch], eax
0x18027c9b4  cmp     eax, 1
0x18027c9b7  jnz     short loc_18027C9C9
0x18027c9b9  mov     rax, [rbx]
0x18027c9bc  mov     rcx, rbx
0x18027c9bf  mov     rax, [rax+8]
0x18027c9c3  call    cs:__guard_dispatch_icall_fptr
0x18027c9c9  lea     rdx, aArbitraryLinkW_0; "arbitrary link which is bidirectional n"...
0x18027c9d0  lea     rcx, [rbp+3D0h+var_50]
0x18027c9d7  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD@Z; std::string::assign(char const * const)
0x18027c9dc  nop
0x18027c9dd  test    rsi, rsi
0x18027c9e0  jz      short loc_18027C9FB
0x18027c9e2  lea     rcx, [rsi+50h]
0x18027c9e6  call    near ptr ??$launder@USecurityCookieHash@RdpNano@Microsoft@@@core@boost@@YAPEAUSecurityCookieHash@RdpNano@Microsoft@@PEAU234@@Z.Data1; boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>(Microsoft::RdpNano::SecurityCookieHash *)
0x18027c9eb  or      ecx, 0FFFFFFFFh
0x18027c9ee  lock xadd [rax], ecx
0x18027c9f2  cmp     ecx, 0FFFFFFFFh
0x18027c9f5  jz      loc_18027D39D
0x18027c9fb  test    r15, r15
0x18027c9fe  jnz     loc_18027CAA8
0x18027ca04  xorps   xmm0, xmm0
0x18027ca07  movups  [rbp+3D0h+var_70], xmm0
0x18027ca0e  lea     rdx, [rdi+5F8h]
0x18027ca15  lea     rcx, [rbp+3D0h+var_70]
0x18027ca1c  call    ??0iterator@?$IterationSafeStore@V?$shared_ptr@VTransport@FailoverBridge@Dct@Basix@Microsoft@@@std@@U?$equal_to@V?$shared_ptr@VTransport@FailoverBridge@Dct@Basix@Microsoft@@@std@@@2@@Containers@Basix@Microsoft@@QEAA@PEBV1234@@Z; Microsoft::Basix::Containers::IterationSafeStore<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>,std::equal_to<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>>>::iterator::iterator(Microsoft::Basix::Containers::IterationSafeStore<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>,std::equal_to<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>>> const *)
0x18027ca21  nop
0x18027ca22  xorps   xmm1, xmm1
0x18027ca25  movdqu  [rbp+3D0h+pExceptionObject], xmm1
0x18027ca2d  mov     rbx, qword ptr [rbp+3D0h+var_70]
0x18027ca34  test    rbx, rbx
0x18027ca37  jz      short loc_18027CA81
0x18027ca39  mov     rdx, qword ptr [rbp+3D0h+var_70+8]
0x18027ca40  mov     rax, [rdx]
0x18027ca43  cmp     dword ptr [rax+118h], 0
0x18027ca4a  jz      short loc_18027CA5A
0x18027ca4c  lea     rcx, [rbp+3D0h+var_70]
0x18027ca53  call    ??Eiterator@?$IterationSafeStore@V?$weak_ptr@VIActivityListener@Instrumentation@Basix@Microsoft@@@std@@U?$owner_equals@V?$weak_ptr@VIActivityListener@Instrumentation@Basix@Microsoft@@@std@@@Algorithm@Basix@Microsoft@@@Containers@Basix@Microsoft@@QEAAAEAV01234@XZ; Microsoft::Basix::Containers::IterationSafeStore<std::weak_ptr<Microsoft::Basix::Instrumentation::IActivityListener>,Microsoft::Basix::Algorithm::owner_equals<std::weak_ptr<Microsoft::Basix::Instrumentation::IActivityListener>>>::iterator::operator++(void)
0x18027ca58  jmp     short loc_18027CA2D
0x18027ca5a  lea     rcx, [rsp+4D0h+var_470]
0x18027ca5f  call    ??4?$shared_ptr@VRendezvousContext@RendezvousSource@RdpNano@Microsoft@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Microsoft::RdpNano::RendezvousSource::RendezvousContext>::operator=(std::shared_ptr<Microsoft::RdpNano::RendezvousSource::RendezvousContext> const &)
0x18027ca64  lea     rdx, aArbitraryLinkW; "arbitrary link which is inbound normal"
0x18027ca6b  lea     rcx, [rbp+3D0h+var_50]
0x18027ca72  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD@Z; std::string::assign(char const * const)
0x18027ca77  mov     r14, qword ptr [rsp+4D0h+var_470+8]
0x18027ca7c  mov     r15, qword ptr [rsp+4D0h+var_470]
0x18027ca81  test    rbx, rbx
0x18027ca84  jz      short loc_18027CA9F
0x18027ca86  lea     rcx, [rbx+50h]
0x18027ca8a  call    near ptr ??$launder@USecurityCookieHash@RdpNano@Microsoft@@@core@boost@@YAPEAUSecurityCookieHash@RdpNano@Microsoft@@PEAU234@@Z.Data1; boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>(Microsoft::RdpNano::SecurityCookieHash *)
0x18027ca8f  or      ecx, 0FFFFFFFFh
0x18027ca92  lock xadd [rax], ecx
0x18027ca96  cmp     ecx, 0FFFFFFFFh
0x18027ca99  jz      loc_18027D376
0x18027ca9f  test    r15, r15
0x18027caa2  jz      loc_18027D22B
0x18027caa8  xorps   xmm0, xmm0
0x18027caab  movdqa  [rbp+3D0h+pExceptionObject], xmm0
0x18027cab3  test    r14, r14
0x18027cab6  jz      short loc_18027CABD
0x18027cab8  lock inc dword ptr [r14+8]
0x18027cabd  movaps  xmm0, [rsp+4D0h+var_470]
0x18027cac2  movdqa  [rbp+3D0h+pExceptionObject], xmm0
0x18027caca  xor     r8d, r8d
0x18027cacd  lea     rdx, [rbp+3D0h+pExceptionObject]
0x18027cad4  mov     rcx, rdi
0x18027cad7  call    ?ChangePrimary@?$Smiles@VLinkDataDisabled@Dct@Basix@Microsoft@@@Dct@Basix@Microsoft@@IEAA_NV?$shared_ptr@VLinkDataDisabled@Dct@Basix@Microsoft@@@std@@W4Direction@LinkData@234@@Z; Microsoft::Basix::Dct::Smiles<Microsoft::Basix::Dct::LinkDataDisabled>::ChangePrimary(std::shared_ptr<Microsoft::Basix::Dct::LinkDataDisabled>,Microsoft::Basix::Dct::LinkData::Direction)
0x18027cadc  test    al, al
0x18027cade  jz      loc_18027D2FB
0x18027cae4  xorps   xmm0, xmm0
0x18027cae7  movups  [rbp+3D0h+var_70], xmm0
0x18027caee  lea     rcx, [rbp+3D0h+var_70]
0x18027caf5  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x18027cafa  nop
0x18027cafb  mov     rax, qword ptr [rbp+3D0h+var_70]
0x18027cb02  test    rax, rax
0x18027cb05  jz      loc_18027CBBF
0x18027cb0b  cmp     byte ptr [rax+80h], 0
0x18027cb12  jz      loc_18027CBBF
0x18027cb18  lea     rax, [rbp+3D0h+var_3F8]
0x18027cb1c  mov     [rsp+4D0h+var_460], rax
0x18027cb21  mov     rcx, [r15+68h]
0x18027cb25  mov     rax, [rcx]
0x18027cb28  lea     rdx, [rbp+3D0h+var_3F8]
0x18027cb2c  mov     rax, [rax+68h]
0x18027cb30  call    cs:__guard_dispatch_icall_fptr
0x18027cb36  mov     rsi, rax
0x18027cb39  mov     ebx, [r15+98h]
0x18027cb40  lea     rdi, [rbp+3D0h+var_50]
0x18027cb47  cmp     qword ptr [rbp+3D0h+var_40+8], 0Fh
0x18027cb4f  cmova   rdi, qword ptr [rbp+3D0h+var_50]
0x18027cb57  xorps   xmm0, xmm0
0x18027cb5a  movups  [rbp+3D0h+pExceptionObject], xmm0
0x18027cb61  xorps   xmm1, xmm1
0x18027cb64  movdqu  [rbp+3D0h+var_80], xmm1
0x18027cb6c  mov     r8d, 48h ; 'H'
0x18027cb72  lea     rdx, aSmilesInitiall_0; "smiles: initially Set primary outLink t"...
0x18027cb79  lea     rcx, [rbp+3D0h+pExceptionObject]
0x18027cb80  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18027cb85  nop
0x18027cb86  mov     [rsp+4D0h+var_4A0], rsi
0x18027cb8b  mov     [rsp+4D0h+Str], r15
0x18027cb90  mov     dword ptr [rsp+4D0h+var_4B0], ebx
0x18027cb94  mov     r9, rdi
0x18027cb97  lea     r8, [rbp+3D0h+pExceptionObject]
0x18027cb9e  lea     rdx, aBasixDct; "BASIX_DCT"
0x18027cba5  lea     rcx, [rbp+3D0h+var_70]
0x18027cbac  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@PEBDIPEAVLinkDataV3@Dct@23@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@1IPEAVLinkDataV3@Dct@23@V65@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,char const *,uint,Microsoft::Basix::Dct::LinkDataV3 *,std::string>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &,char const *,uint,Microsoft::Basix::Dct::LinkDataV3 *,std::string)
0x18027cbb1  nop
0x18027cbb2  lea     rcx, [rbp+3D0h+pExceptionObject]
0x18027cbb9  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18027cbbe  nop
0x18027cbbf  mov     rbx, qword ptr [rbp+3D0h+var_70+8]
0x18027cbc6  or      r12d, 0FFFFFFFFh
0x18027cbca  test    rbx, rbx
0x18027cbcd  jz      short loc_18027CC08
0x18027cbcf  mov     eax, r12d
0x18027cbd2  lock xadd [rbx+8], eax
0x18027cbd7  add     eax, r12d
0x18027cbda  jnz     short loc_18027CC08
0x18027cbdc  mov     rax, [rbx]
0x18027cbdf  mov     rcx, rbx
0x18027cbe2  mov     rax, [rax]
0x18027cbe5  call    cs:__guard_dispatch_icall_fptr
0x18027cbeb  mov     eax, r12d
0x18027cbee  lock xadd [rbx+0Ch], eax
0x18027cbf3  add     eax, r12d
0x18027cbf6  jnz     short loc_18027CC08
0x18027cbf8  mov     rax, [rbx]
0x18027cbfb  mov     rcx, rbx
0x18027cbfe  mov     rax, [rax+8]
0x18027cc02  call    cs:__guard_dispatch_icall_fptr
0x18027cc08  xorps   xmm0, xmm0
0x18027cc0b  movups  [rbp+3D0h+pExceptionObject], xmm0
0x18027cc12  lea     rcx, [rbp+3D0h+pExceptionObject]
0x18027cc19  call    ??$SelectEvent@VTraceCheckpoint@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(void)
0x18027cc1e  nop
0x18027cc1f  mov     rax, qword ptr [rbp+3D0h+pExceptionObject]
0x18027cc26  test    rax, rax
0x18027cc29  jz      loc_18027D1D8
0x18027cc2f  cmp     byte ptr [rax+80h], 0
0x18027cc36  jz      loc_18027D1D8
0x18027cc3c  lea     rax, [rbp+3D0h+var_270]
0x18027cc43  mov     [rsp+4D0h+var_460], rax
0x18027cc48  xorps   xmm0, xmm0
0x18027cc4b  movups  [rsp+4D0h+var_458], xmm0
0x18027cc50  xorps   xmm1, xmm1
0x18027cc53  movdqu  [rbp+3D0h+var_448], xmm1
0x18027cc58  mov     edi, 1
0x18027cc5d  mov     r8d, edi
0x18027cc60  lea     rsi, asc_1803D71C8; "\""
0x18027cc67  mov     rdx, rsi
0x18027cc6a  lea     rcx, [rsp+4D0h+var_458]
0x18027cc6f  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18027cc74  nop
0x18027cc75  mov     rcx, [r15+68h]
0x18027cc79  mov     rax, [rcx]
0x18027cc7c  lea     rdx, [rbp+3D0h+var_B0]
0x18027cc83  mov     rax, [rax+68h]
0x18027cc87  call    cs:__guard_dispatch_icall_fptr
0x18027cc8d  mov     rbx, rax
0x18027cc90  xorps   xmm0, xmm0
0x18027cc93  movups  [rbp+3D0h+var_418], xmm0
0x18027cc97  xorps   xmm1, xmm1
0x18027cc9a  movdqu  [rbp+3D0h+var_408], xmm1
0x18027cc9f  mov     r8d, edi
0x18027cca2  mov     rdx, rsi
0x18027cca5  lea     rcx, [rbp+3D0h+var_418]
0x18027cca9  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18027ccae  nop
0x18027ccaf  xorps   xmm0, xmm0
0x18027ccb2  movups  [rbp+3D0h+var_438], xmm0
0x18027ccb6  xorps   xmm1, xmm1
0x18027ccb9  movdqu  [rbp+3D0h+var_428], xmm1
0x18027ccbe  mov     r8d, edi
0x18027ccc1  lea     rdi, asc_1803D71C4; ":"
0x18027ccc8  mov     rdx, rdi
0x18027cccb  lea     rcx, [rbp+3D0h+var_438]
0x18027cccf  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18027ccd4  nop
0x18027ccd5  xorps   xmm0, xmm0
0x18027ccd8  movups  [rbp+3D0h+var_2D8], xmm0
0x18027ccdf  xorps   xmm1, xmm1
0x18027cce2  movdqu  [rbp+3D0h+var_2C8], xmm1
0x18027ccea  mov     r8d, 1
0x18027ccf0  mov     rdx, rsi
0x18027ccf3  lea     rcx, [rbp+3D0h+var_2D8]
0x18027ccfa  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18027ccff  nop
0x18027cd00  xorps   xmm0, xmm0
0x18027cd03  movups  [rbp+3D0h+var_2F8], xmm0
0x18027cd0a  xorps   xmm1, xmm1
0x18027cd0d  movdqu  [rbp+3D0h+var_2E8], xmm1
0x18027cd15  mov     r8d, 1
0x18027cd1b  mov     rdx, rsi
0x18027cd1e  lea     rcx, [rbp+3D0h+var_2F8]
0x18027cd25  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18027cd2a  nop
0x18027cd2b  lea     r8, aChannelname; "channelName"
0x18027cd32  lea     rdx, [rbp+3D0h+var_2F8]
0x18027cd39  lea     rcx, [rbp+3D0h+var_D0]
0x18027cd40  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x18027cd45  nop
0x18027cd46  lea     r9, [rbp+3D0h+var_2D8]
0x18027cd4d  mov     r8, rax
  ... truncated ...
```
