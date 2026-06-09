# Microsoft::RdpNano::IceRestartAgent::IceRestartThread(void)

- ea: `0x180115ad8`
- end: `0x180116231`
- name: `?IceRestartThread@IceRestartAgent@RdpNano@Microsoft@@AEAAXXZ`
- size: `1881`
- prototype: `void __fastcall(Microsoft::RdpNano::IceRestartAgent *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180115750`

## callees

- `0x18000d9c0`
- `0x180015bb8`
- `0x1800187a8`
- `0x180018ea4`
- `0x18001902c`
- `0x18001ab4c`
- `0x1800334a8`
- `0x180037188`
- `0x1801002ac`
- `0x1801007d0`
- `0x18011557c`
- `0x180115ad8`
- `0x18031215c`
- `0x180312164`
- `0x180312404`
- `0x180313560`
- `0x18032f050`
- `0x18032f0b0`
- `0x180375c40`

## string_xrefs

- `0x1801160f3`: `IceRestartAgentThread: Starting ICE from pending start.`
- `0x180116027`: `IceRestartAgentThread: ICE started successfully.`
- `0x180115df7`: `IceRestartAgentThread: Start ICE restart timer.`
- `0x180115f5e`: `IceRestartAgentThread: Stop ICE restart timer.`
- `0x180115d13`: `IceRestartAgentThread: Stopping ICE for restart.`
- `0x180115c3d`: `Microsoft::RdpNano::IceRestartAgent::IceRestartThread`
- `0x180115c51`: `C:\__w\1\s\rdnanolib\rdnano\IceRestartAgent.cpp`
- `0x180115c2c`: `IceRestartAgentThread: Unexpected ICE source state: %d.\n    %s(%d): %s()`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
void __fastcall Microsoft::RdpNano::IceRestartAgent::IceRestartThread(Microsoft::RdpNano::IceRestartAgent *this)
{
  struct _Mtx_internal_imp_t *v2; // r13
  char *v3; // rbx
  char *v4; // rdi
  int v5; // r13d
  int v6; // eax
  int *v7; // rcx
  int *v8; // rdx
  int v9; // esi
  int v10; // edx
  const char *v11; // r9
  int v12; // ebx
  char v13; // bl
  char v14; // di
  volatile signed __int32 *v15; // rsi
  volatile signed __int32 *v16; // rbx
  volatile signed __int32 *v17; // rbx
  __int64 v18; // rax
  volatile signed __int32 *v19; // rbx
  volatile signed __int32 *v20; // rbx
  volatile signed __int32 *v21; // rbx
  volatile signed __int32 *v22; // rbx
  struct _Mtx_internal_imp_t *v23; // r12
  int v24; // [rsp+20h] [rbp-69h]
  const char *v25; // [rsp+28h] [rbp-61h]
  __int128 v26; // [rsp+40h] [rbp-49h] BYREF
  __int128 v27; // [rsp+50h] [rbp-39h]
  __int128 v28; // [rsp+60h] [rbp-29h]
  __int128 v29; // [rsp+70h] [rbp-19h] BYREF
  __int64 v30; // [rsp+80h] [rbp-9h] BYREF
  _BYTE v31[8]; // [rsp+88h] [rbp-1h] BYREF
  volatile signed __int32 *v32; // [rsp+90h] [rbp+7h]
  __int128 v33; // [rsp+98h] [rbp+Fh] BYREF
  int v34; // [rsp+A8h] [rbp+1Fh]
  int v35; // [rsp+ACh] [rbp+23h]
  int v36; // [rsp+B0h] [rbp+27h]

  v35 = 0;
  v36 = 0;
  v34 = 0;
  v28 = 0;
  v2 = (Microsoft::RdpNano::IceRestartAgent *)((char *)this + 56);
  for ( BYTE8(v28) = 0; ; BYTE8(v28) = 0 )
  {
    *(_QWORD *)&v28 = v2;
    v23 = v2;
    if ( Mtx_lock(v2) )
      std::_Throw_Cpp_error(5);
    if ( *((_DWORD *)v2 + 19) == 0x7FFFFFFF )
    {
      *((_DWORD *)v2 + 19) = 2147483646;
      std::_Throw_Cpp_error(6);
    }
    BYTE8(v28) = 1;
    v3 = (char *)this + 208;
    v4 = (char *)this + 212;
    v5 = v35;
    while ( 1 )
    {
      v6 = *((_DWORD *)this + 54);
      v7 = (int *)v3;
      v8 = (int *)((char *)this + 212);
      if ( v6 != v34 )
        break;
      v3 = (char *)this + 208;
      v7 = (int *)((char *)this + 208);
      v8 = (int *)v4;
      if ( *((_DWORD *)this + 52) != v5 )
        break;
      v4 = (char *)this + 212;
      v8 = (int *)((char *)this + 212);
      if ( *((_DWORD *)this + 53) != v36 )
        break;
      Cnd_wait((Microsoft::RdpNano::IceRestartAgent *)((char *)this + 136), v23);
    }
    v34 = *((_DWORD *)this + 54);
    v2 = (Microsoft::RdpNano::IceRestartAgent *)((char *)this + 56);
    if ( v6 == 6 )
      break;
    v9 = *v7;
    v35 = *v7;
    v10 = *v8;
    v36 = v10;
    switch ( v6 )
    {
      case 1:
        v13 = 0;
        v14 = 0;
        if ( v10 )
        {
          v33 = 0;
          Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v33);
          if ( (_QWORD)v33 && *(_BYTE *)(v33 + 128) )
          {
            v26 = 0;
            v27 = 0;
            std::string::_Construct<1,char const *>(&v26, "IceRestartAgentThread: Starting ICE from pending start.", 55);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(
              &v33,
              "RDPNANO",
              &v26);
            std::string::_Tidy_deallocate(&v26);
          }
          v22 = (volatile signed __int32 *)*((_QWORD *)&v33 + 1);
          if ( *((_QWORD *)&v33 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v33 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
              if ( !_InterlockedDecrement(v22 + 3) )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
            }
          }
          *((_DWORD *)this + 54) = 2;
          v14 = 1;
          v13 = 0;
        }
        break;
      case 2:
        if ( v9 )
        {
          v33 = 0;
          Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v33);
          if ( (_QWORD)v33 && *(_BYTE *)(v33 + 128) )
          {
            v26 = 0;
            v27 = 0;
            std::string::_Construct<1,char const *>(&v26, "IceRestartAgentThread: ICE started successfully.", 48);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(
              &v33,
              "RDPNANO",
              &v26);
            std::string::_Tidy_deallocate(&v26);
          }
          v21 = (volatile signed __int32 *)*((_QWORD *)&v33 + 1);
          if ( *((_QWORD *)&v33 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v33 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
              if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
            }
          }
          *((_DWORD *)this + 54) = 3;
        }
        goto LABEL_62;
      case 3:
        if ( v9 )
        {
          if ( (*(unsigned int (__fastcall **)(char *))(*((_QWORD *)this + 2) + 8LL))((char *)this + 16) == 1 )
          {
            v33 = 0;
            Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v33);
            if ( (_QWORD)v33 && *(_BYTE *)(v33 + 128) )
            {
              v26 = 0;
              v27 = 0;
              std::string::_Construct<1,char const *>(&v26, "IceRestartAgentThread: Stop ICE restart timer.", 46);
              Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(
                &v33,
                "RDPNANO",
                &v26);
              std::string::_Tidy_deallocate(&v26);
            }
            v20 = (volatile signed __int32 *)*((_QWORD *)&v33 + 1);
            if ( *((_QWORD *)&v33 + 1) )
            {
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v33 + 1) + 8LL), 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
                if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
              }
            }
            (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 3) + 8LL))(*((_QWORD *)this + 3), 0);
          }
        }
        else if ( (*(unsigned int (__fastcall **)(char *))(*((_QWORD *)this + 2) + 8LL))((char *)this + 16) != 1 )
        {
          v33 = 0;
          Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v33);
          if ( (_QWORD)v33 && *(_BYTE *)(v33 + 128) )
          {
            v26 = 0;
            v27 = 0;
            std::string::_Construct<1,char const *>(&v26, "IceRestartAgentThread: Start ICE restart timer.", 47);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(
              &v33,
              "RDPNANO",
              &v26);
            std::string::_Tidy_deallocate(&v26);
          }
          v17 = (volatile signed __int32 *)*((_QWORD *)&v33 + 1);
          if ( *((_QWORD *)&v33 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v33 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
              if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
            }
          }
          v18 = Microsoft::Basix::SharedFromThisVirtualBase::GetSharedPtr<Microsoft::Basix::ITimerCallback>(
                  (char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 8,
                  v31);
          v29 = 0;
          if ( *(_QWORD *)(v18 + 8) )
          {
            v29 = *(_OWORD *)v18;
            _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v29 + 1) + 12LL));
          }
          v30 = 17000;
          Microsoft::Basix::Timer::Setup((char *)this + 16, &v30, &v29);
          v19 = v32;
          if ( v32 )
          {
            if ( !_InterlockedDecrement(v32 + 2) )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
              if ( !_InterlockedDecrement(v19 + 3) )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
            }
          }
        }
LABEL_62:
        v13 = 0;
LABEL_63:
        v14 = 0;
        break;
      case 4:
        v33 = 0;
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v33);
        if ( (_QWORD)v33 && *(_BYTE *)(v33 + 128) )
        {
          v26 = 0;
          v27 = 0;
          std::string::_Construct<1,char const *>(&v26, "IceRestartAgentThread: Stopping ICE for restart.", 48);
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(
            &v33,
            "RDPNANO",
            &v26);
          std::string::_Tidy_deallocate(&v26);
        }
        v16 = (volatile signed __int32 *)*((_QWORD *)&v33 + 1);
        if ( *((_QWORD *)&v33 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v33 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
            if ( !_InterlockedDecrement(v16 + 3) )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
          }
        }
        *((_DWORD *)this + 54) = 5;
        v13 = 1;
        goto LABEL_63;
      case 5:
        goto LABEL_62;
      default:
        v33 = 0;
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v33);
        if ( (_QWORD)v33 && *(_BYTE *)(v33 + 128) )
        {
          v12 = *((_DWORD *)this + 54);
          v26 = 0;
          v27 = 0;
          std::string::_Construct<1,char const *>(
            &v26,
            "IceRestartAgentThread: Unexpected ICE source state: %d.\n    %s(%d): %s()",
            72,
            v11,
            v24,
            v25);
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,int,char const *,int,char const *>(
            (unsigned int)&v33,
            (unsigned int)"RDPNANO",
            (unsigned int)&v26,
            v12,
            (__int64)"C:\\__w\\1\\s\\rdnanolib\\rdnano\\IceRestartAgent.cpp",
            168,
            (__int64)"Microsoft::RdpNano::IceRestartAgent::IceRestartThread");
          std::string::_Tidy_deallocate(&v26);
        }
        v13 = 0;
        v14 = 0;
        v15 = (volatile signed __int32 *)*((_QWORD *)&v33 + 1);
        if ( *((_QWORD *)&v33 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v33 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
            if ( !_InterlockedDecrement(v15 + 3) )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
          }
        }
        break;
    }
    if ( !v23 )
      std::_Throw_system_error(1);
    Mtx_unlock(v23);
    BYTE8(v28) = 0;
    if ( v13 )
      Microsoft::RdpNano::ICESourceAdapter::Stop(*((Microsoft::RdpNano::ICESourceAdapter **)this + 28));
    if ( v14 )
      Microsoft::RdpNano::ICESourceAdapter::Start(*((Microsoft::RdpNano::ICESourceAdapter **)this + 28));
    v28 = 0;
  }
  Mtx_unlock(v23);
}

```

## disassembly

```asm
0x180115ad8  mov     rax, rsp
0x180115adb  mov     [rax+10h], rbx
0x180115adf  mov     [rax+18h], rsi
0x180115ae3  mov     [rax+20h], rdi
0x180115ae7  push    rbp
0x180115ae8  push    r12
0x180115aea  push    r13
0x180115aec  push    r14
0x180115aee  push    r15
0x180115af0  lea     rbp, [rax-5Fh]
0x180115af4  mov     eax, 0C0h
0x180115af9  call    _alloca_probe
0x180115afe  sub     rsp, rax
0x180115b01  mov     rax, cs:__security_cookie
0x180115b08  xor     rax, rsp
0x180115b0b  mov     [rbp+57h+var_28], rax
0x180115b0f  mov     r14, rcx
0x180115b12  xor     esi, esi
0x180115b14  mov     [rbp+57h+var_34], esi
0x180115b17  mov     [rbp+57h+var_30], esi
0x180115b1a  xor     r15d, r15d
0x180115b1d  mov     [rbp+57h+var_38], r15d
0x180115b21  xorps   xmm0, xmm0
0x180115b24  movups  [rbp+57h+var_80], xmm0
0x180115b28  lea     r13, [rcx+38h]
0x180115b2c  mov     byte ptr [rbp+57h+var_80+8], sil
0x180115b30  jmp     loc_1801161BB
0x180115b35  cmp     dword ptr [r13+4Ch], 7FFFFFFFh
0x180115b3d  jz      loc_18011621E
0x180115b43  mov     byte ptr [rbp+57h+var_80+8], 1
0x180115b47  lea     rbx, [r14+0D0h]
0x180115b4e  lea     rsi, [r14+0D4h]
0x180115b55  mov     rdi, rsi
0x180115b58  mov     r13d, [rbp+57h+var_34]
0x180115b5c  mov     eax, [r14+0D8h]
0x180115b63  mov     rcx, rbx
0x180115b66  mov     rdx, rsi
0x180115b69  cmp     eax, [rbp+57h+var_38]
0x180115b6c  jnz     short loc_180115BA4
0x180115b6e  lea     rbx, [r14+0D0h]
0x180115b75  mov     rcx, rbx
0x180115b78  mov     rdx, rdi
0x180115b7b  cmp     [rbx], r13d
0x180115b7e  jnz     short loc_180115BA4
0x180115b80  lea     rdi, [r14+0D4h]
0x180115b87  mov     rdx, rdi
0x180115b8a  mov     r8d, [rbp+57h+var_30]
0x180115b8e  cmp     [rdi], r8d
0x180115b91  jnz     short loc_180115BA4
0x180115b93  mov     rdx, r12; _Mtx_t
0x180115b96  lea     rcx, [r14+88h]; _Cnd_t
0x180115b9d  call    _Cnd_wait
0x180115ba2  jmp     short loc_180115B5C
0x180115ba4  mov     [rbp+57h+var_38], eax
0x180115ba7  cmp     eax, 6
0x180115baa  lea     r13, [r14+38h]
0x180115bae  jz      loc_1801161D3
0x180115bb4  mov     esi, [rcx]
0x180115bb6  mov     [rbp+57h+var_34], esi
0x180115bb9  mov     edx, [rdx]
0x180115bbb  mov     [rbp+57h+var_30], edx
0x180115bbe  mov     ecx, eax
0x180115bc0  sub     ecx, 1
0x180115bc3  jz      loc_1801160AE
0x180115bc9  sub     ecx, 1
0x180115bcc  jz      loc_180115FE7
0x180115bd2  sub     ecx, 1
0x180115bd5  jz      loc_180115D9B
0x180115bdb  sub     ecx, 1
0x180115bde  jz      loc_180115CDB
0x180115be4  cmp     ecx, 1
0x180115be7  jz      loc_1801160A4
0x180115bed  xorps   xmm0, xmm0
0x180115bf0  movups  [rbp+57h+var_48], xmm0
0x180115bf4  lea     rcx, [rbp+57h+var_48]
0x180115bf8  call    ??$SelectEvent@VTraceError@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(void)
0x180115bfd  nop
0x180115bfe  mov     rax, qword ptr [rbp+57h+var_48]
0x180115c02  test    rax, rax
0x180115c05  jz      short loc_180115C7F
0x180115c07  cmp     byte ptr [rax+80h], 0
0x180115c0e  jz      short loc_180115C7F
0x180115c10  mov     ebx, [r14+0D8h]
0x180115c17  xorps   xmm0, xmm0
0x180115c1a  movups  [rbp+57h+var_A0], xmm0
0x180115c1e  xorps   xmm1, xmm1
0x180115c21  movdqu  [rbp+57h+var_90], xmm1
0x180115c26  mov     r8d, 48h ; 'H'
0x180115c2c  lea     rdx, aIcerestartagen_2; "IceRestartAgentThread: Unexpected ICE s"...
0x180115c33  lea     rcx, [rbp+57h+var_A0]
0x180115c37  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180115c3c  nop
0x180115c3d  lea     rax, aMicrosoftRdpna; "Microsoft::RdpNano::IceRestartAgent::Ic"...
0x180115c44  mov     [rsp+0E0h+var_B0], rax
0x180115c49  mov     dword ptr [rsp+0E0h+var_B8], 0A8h
0x180115c51  lea     rax, aCW1SRdnanolibR_3; "C:\\__w\\1\\s\\rdnanolib\\rdnano\\IceRe"...
0x180115c58  mov     qword ptr [rsp+0E0h+var_C0], rax
0x180115c5d  mov     r9d, ebx
0x180115c60  lea     r8, [rbp+57h+var_A0]
0x180115c64  lea     rdx, aRdpnano; "RDPNANO"
0x180115c6b  lea     rcx, [rbp+57h+var_48]
0x180115c6f  call    ??$TraceMessage@VTraceError@Basix@Microsoft@@HPEBDHPEBD@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@H1H1@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,int,char const *,int,char const *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceError>> const &,char const *,std::string const &,int,char const *,int,char const *)
0x180115c74  nop
0x180115c75  lea     rcx, [rbp+57h+var_A0]
0x180115c79  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180115c7e  nop
0x180115c7f  xor     bl, bl
0x180115c81  xor     dil, dil
0x180115c84  mov     rsi, qword ptr [rbp+57h+var_48+8]
0x180115c88  test    rsi, rsi
0x180115c8b  jz      loc_180116179
0x180115c91  or      r15d, 0FFFFFFFFh
0x180115c95  mov     eax, r15d
0x180115c98  lock xadd [rsi+8], eax
0x180115c9d  add     eax, r15d
0x180115ca0  jnz     loc_180116179
0x180115ca6  mov     rax, [rsi]
0x180115ca9  mov     rcx, rsi
0x180115cac  mov     rax, [rax]
0x180115caf  call    cs:__guard_dispatch_icall_fptr
0x180115cb5  mov     eax, r15d
0x180115cb8  lock xadd [rsi+0Ch], eax
0x180115cbd  add     eax, r15d
0x180115cc0  jnz     loc_180116179
0x180115cc6  mov     rax, [rsi]
0x180115cc9  mov     rcx, rsi
0x180115ccc  mov     rax, [rax+8]
0x180115cd0  call    cs:__guard_dispatch_icall_fptr
0x180115cd6  jmp     loc_180116179
0x180115cdb  xorps   xmm0, xmm0
0x180115cde  movups  [rbp+57h+var_48], xmm0
0x180115ce2  lea     rcx, [rbp+57h+var_48]
0x180115ce6  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x180115ceb  nop
0x180115cec  mov     rax, qword ptr [rbp+57h+var_48]
0x180115cf0  test    rax, rax
0x180115cf3  jz      short loc_180115D43
0x180115cf5  cmp     byte ptr [rax+80h], 0
0x180115cfc  jz      short loc_180115D43
0x180115cfe  xorps   xmm0, xmm0
0x180115d01  movups  [rbp+57h+var_A0], xmm0
0x180115d05  xorps   xmm1, xmm1
0x180115d08  movdqu  [rbp+57h+var_90], xmm1
0x180115d0d  mov     r8d, 30h ; '0'
0x180115d13  lea     rdx, aIcerestartagen_3; "IceRestartAgentThread: Stopping ICE for"...
0x180115d1a  lea     rcx, [rbp+57h+var_A0]
0x180115d1e  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180115d23  nop
0x180115d24  lea     r8, [rbp+57h+var_A0]
0x180115d28  lea     rdx, aRdpnano; "RDPNANO"
0x180115d2f  lea     rcx, [rbp+57h+var_48]
0x180115d33  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@$$V@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &)
0x180115d38  nop
0x180115d39  lea     rcx, [rbp+57h+var_A0]
0x180115d3d  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180115d42  nop
0x180115d43  mov     rbx, qword ptr [rbp+57h+var_48+8]
0x180115d47  test    rbx, rbx
0x180115d4a  jz      short loc_180115D89
0x180115d4c  or      r15d, 0FFFFFFFFh
0x180115d50  mov     eax, r15d
0x180115d53  lock xadd [rbx+8], eax
0x180115d58  add     eax, r15d
0x180115d5b  jnz     short loc_180115D89
0x180115d5d  mov     rax, [rbx]
0x180115d60  mov     rcx, rbx
0x180115d63  mov     rax, [rax]
0x180115d66  call    cs:__guard_dispatch_icall_fptr
0x180115d6c  mov     eax, r15d
0x180115d6f  lock xadd [rbx+0Ch], eax
0x180115d74  add     eax, r15d
0x180115d77  jnz     short loc_180115D89
0x180115d79  mov     rax, [rbx]
0x180115d7c  mov     rcx, rbx
0x180115d7f  mov     rax, [rax+8]
0x180115d83  call    cs:__guard_dispatch_icall_fptr
0x180115d89  mov     dword ptr [r14+0D8h], 5
0x180115d94  mov     bl, 1
0x180115d96  jmp     loc_1801160A6
0x180115d9b  test    esi, esi
0x180115d9d  jnz     loc_180115F0B
0x180115da3  lea     rdi, [r14+10h]
0x180115da7  mov     rax, [rdi]
0x180115daa  mov     rcx, rdi
0x180115dad  mov     rax, [rax+8]
0x180115db1  call    cs:__guard_dispatch_icall_fptr
0x180115db7  nop
0x180115db8  cmp     eax, 1
0x180115dbb  jz      loc_1801160A4
0x180115dc1  xorps   xmm0, xmm0
0x180115dc4  movups  [rbp+57h+var_48], xmm0
0x180115dc8  lea     rcx, [rbp+57h+var_48]
0x180115dcc  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x180115dd1  nop
0x180115dd2  mov     rax, qword ptr [rbp+57h+var_48]
0x180115dd6  test    rax, rax
0x180115dd9  jz      short loc_180115E27
0x180115ddb  cmp     [rax+80h], sil
0x180115de2  jz      short loc_180115E27
0x180115de4  xorps   xmm0, xmm0
0x180115de7  movups  [rbp+57h+var_A0], xmm0
0x180115deb  xorps   xmm1, xmm1
0x180115dee  movdqu  [rbp+57h+var_90], xmm1
0x180115df3  lea     r8d, [rsi+2Fh]
0x180115df7  lea     rdx, aIcerestartagen_0; "IceRestartAgentThread: Start ICE restar"...
0x180115dfe  lea     rcx, [rbp+57h+var_A0]
0x180115e02  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180115e07  nop
0x180115e08  lea     r8, [rbp+57h+var_A0]
0x180115e0c  lea     rdx, aRdpnano; "RDPNANO"
0x180115e13  lea     rcx, [rbp+57h+var_48]
0x180115e17  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@$$V@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &)
0x180115e1c  nop
0x180115e1d  lea     rcx, [rbp+57h+var_A0]
0x180115e21  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180115e26  nop
0x180115e27  mov     rbx, qword ptr [rbp+57h+var_48+8]
0x180115e2b  or      esi, 0FFFFFFFFh
0x180115e2e  test    rbx, rbx
0x180115e31  jz      short loc_180115E68
0x180115e33  mov     eax, esi
0x180115e35  lock xadd [rbx+8], eax
0x180115e3a  add     eax, esi
0x180115e3c  jnz     short loc_180115E68
0x180115e3e  mov     rax, [rbx]
0x180115e41  mov     rcx, rbx
0x180115e44  mov     rax, [rax]
0x180115e47  call    cs:__guard_dispatch_icall_fptr
0x180115e4d  mov     eax, esi
0x180115e4f  lock xadd [rbx+0Ch], eax
0x180115e54  add     eax, esi
0x180115e56  jnz     short loc_180115E68
0x180115e58  mov     rax, [rbx]
0x180115e5b  mov     rcx, rbx
0x180115e5e  mov     rax, [rax+8]
0x180115e62  call    cs:__guard_dispatch_icall_fptr
0x180115e68  mov     rax, [r14+8]
0x180115e6c  movsxd  rcx, dword ptr [rax+4]
0x180115e70  add     rcx, 8
0x180115e74  add     rcx, r14
0x180115e77  lea     rdx, [rbp+57h+var_58]
0x180115e7b  call    ??$GetSharedPtr@VITimerCallback@Basix@Microsoft@@@SharedFromThisVirtualBase@Basix@Microsoft@@QEAA?AV?$shared_ptr@VITimerCallback@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::SharedFromThisVirtualBase::GetSharedPtr<Microsoft::Basix::ITimerCallback>(void)
0x180115e80  nop
0x180115e81  xorps   xmm0, xmm0
0x180115e84  movdqu  [rbp+57h+var_70], xmm0
0x180115e89  cmp     qword ptr [rax+8], 0
0x180115e8e  jz      short loc_180115EA3
0x180115e90  mov     rcx, [rax]
0x180115e93  mov     qword ptr [rbp+57h+var_70], rcx
0x180115e97  mov     rax, [rax+8]
0x180115e9b  mov     qword ptr [rbp+57h+var_70+8], rax
0x180115e9f  lock inc dword ptr [rax+0Ch]
0x180115ea3  mov     [rbp+57h+var_60], 4268h
0x180115eab  lea     r8, [rbp+57h+var_70]
0x180115eaf  lea     rdx, [rbp+57h+var_60]
0x180115eb3  mov     rcx, rdi
0x180115eb6  call    ?Setup@Timer@Basix@Microsoft@@QEAAXAEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@std@@V?$weak_ptr@VITimerCallback@Basix@Microsoft@@@6@@Z; Microsoft::Basix::Timer::Setup(std::chrono::duration<__int64,std::ratio<1,1000>> const &,std::weak_ptr<Microsoft::Basix::ITimerCallback>)
0x180115ebb  nop
0x180115ebc  mov     rbx, [rbp+57h+var_50]
0x180115ec0  test    rbx, rbx
0x180115ec3  jz      loc_1801160A4
0x180115ec9  mov     eax, esi
0x180115ecb  lock xadd [rbx+8], eax
0x180115ed0  add     eax, esi
0x180115ed2  jnz     loc_1801160A4
0x180115ed8  mov     rax, [rbx]
0x180115edb  mov     rcx, rbx
0x180115ede  mov     rax, [rax]
0x180115ee1  call    cs:__guard_dispatch_icall_fptr
0x180115ee7  mov     eax, esi
0x180115ee9  lock xadd [rbx+0Ch], eax
0x180115eee  add     eax, esi
0x180115ef0  jnz     loc_1801160A4
0x180115ef6  mov     rax, [rbx]
0x180115ef9  mov     rcx, rbx
0x180115efc  mov     rax, [rax+8]
0x180115f00  call    cs:__guard_dispatch_icall_fptr
0x180115f06  jmp     loc_1801160A4
0x180115f0b  lea     rcx, [r14+10h]
0x180115f0f  mov     rax, [rcx]
0x180115f12  mov     rax, [rax+8]
0x180115f16  call    cs:__guard_dispatch_icall_fptr
0x180115f1c  nop
0x180115f1d  cmp     eax, 1
0x180115f20  jnz     loc_1801160A4
0x180115f26  xorps   xmm0, xmm0
0x180115f29  movups  [rbp+57h+var_48], xmm0
0x180115f2d  lea     rcx, [rbp+57h+var_48]
0x180115f31  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x180115f36  nop
0x180115f37  mov     rax, qword ptr [rbp+57h+var_48]
0x180115f3b  test    rax, rax
0x180115f3e  jz      short loc_180115F8E
0x180115f40  cmp     byte ptr [rax+80h], 0
0x180115f47  jz      short loc_180115F8E
0x180115f49  xorps   xmm0, xmm0
0x180115f4c  movups  [rbp+57h+var_A0], xmm0
0x180115f50  xorps   xmm1, xmm1
0x180115f53  movdqu  [rbp+57h+var_90], xmm1
0x180115f58  mov     r8d, 2Eh ; '.'
  ... truncated ...
```
