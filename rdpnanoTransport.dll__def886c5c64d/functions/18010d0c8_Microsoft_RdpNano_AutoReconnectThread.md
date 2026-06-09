# Microsoft::RdpNano::AutoReconnectThread

- ea: `0x18010d0c8`
- end: `0x18010d6b0`
- name: `Microsoft::RdpNano::AutoReconnectThread`
- size: `1512`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x180107090`

## callees

- `0x18000d9c0`
- `0x180015bb8`
- `0x18001902c`
- `0x1800191b4`
- `0x18001ae64`
- `0x18001bed4`
- `0x180106038`
- `0x1801066f8`
- `0x180109088`
- `0x18010d0c8`
- `0x18010db30`
- `0x18010de4c`
- `0x1801b3120`
- `0x18032f050`
- `0x18032f0b0`
- `0x180375c40`

## string_xrefs

- `0x18010d194`: `AutoReconnectThread: DoR==0, calling CreateChannel (retry=%u/%u)`
- `0x18010d2cf`: `AutoReconnectThread: DoR=%u > 0, clearing reconnecting flag`
- `0x18010d3a7`: `AutoReconnectThread: source expired (weak_ptr lock failed) at retry=%u`
- `0x18010d49b`: `AutoReconnectThread: TIMEOUT after %u retries, closing Rendezvous`
- `0x18010d5ac`: `AutoReconnectThread: exiting, source=%s reconnecting=%s`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
signed __int32 __fastcall Microsoft::RdpNano::AutoReconnectThread(__int64 a1, unsigned int a2)
{
  unsigned int v4; // r15d
  __int64 v5; // rdx
  signed __int32 v6; // eax
  signed __int32 v7; // ett
  Microsoft::RdpNano::RendezvousSource *v8; // rsi
  volatile signed __int32 *v9; // rdi
  unsigned int v10; // ebx
  int v11; // r9d
  volatile signed __int32 *v12; // rbx
  __int64 v13; // rdx
  signed __int32 v14; // eax
  volatile signed __int32 *v15; // rbx
  char v16; // bl
  signed __int32 result; // eax
  volatile signed __int32 *v18; // rbx
  signed __int32 v19; // ett
  Microsoft::RdpNano::RendezvousSource *v20; // rsi
  volatile signed __int32 *v21; // rbx
  const char *v22; // r9
  const char *v23; // r15
  const char *v24; // rbx
  volatile signed __int32 *v25; // rcx
  Microsoft::RdpNano::RendezvousSource *v26[2]; // [rsp+30h] [rbp-39h] BYREF
  __int128 v27; // [rsp+40h] [rbp-29h] BYREF
  __int128 v28; // [rsp+50h] [rbp-19h]
  __int64 v29; // [rsp+60h] [rbp-9h]
  _BYTE v30[8]; // [rsp+68h] [rbp-1h] BYREF
  __int128 v31; // [rsp+70h] [rbp+7h] BYREF

  v29 = a1;
  v4 = 0;
  if ( a2 )
  {
    _mm_lfence();
    while ( 1 )
    {
      *(_OWORD *)v26 = 0;
      v5 = *(_QWORD *)(a1 + 8);
      if ( v5 )
      {
        v6 = *(_DWORD *)(v5 + 8);
        while ( v6 )
        {
          v7 = v6;
          v6 = _InterlockedCompareExchange((volatile signed __int32 *)(v5 + 8), v6 + 1, v6);
          if ( v7 == v6 )
          {
            v8 = *(Microsoft::RdpNano::RendezvousSource **)a1;
            v26[0] = *(Microsoft::RdpNano::RendezvousSource **)a1;
            v9 = *(volatile signed __int32 **)(a1 + 8);
            v26[1] = (Microsoft::RdpNano::RendezvousSource *)v9;
            goto LABEL_8;
          }
        }
      }
      v8 = v26[0];
      v9 = (volatile signed __int32 *)v26[1];
LABEL_8:
      if ( !v8 )
        break;
      v10 = Microsoft::RdpNano::RendezvousSource::ComputeDegreeOfRedundancy(v8);
      v31 = 0;
      if ( v10 )
      {
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v31);
        if ( (_QWORD)v31 && *(_BYTE *)(v31 + 128) )
        {
          v27 = 0;
          v28 = 0;
          std::string::_Construct<1,char const *>(
            &v27,
            "AutoReconnectThread: DoR=%u > 0, clearing reconnecting flag",
            59);
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,unsigned int>(
            &v31,
            "RENDEZVOUS",
            &v27,
            v10);
          std::string::_Tidy_deallocate(&v27);
        }
        v15 = (volatile signed __int32 *)*((_QWORD *)&v31 + 1);
        if ( *((_QWORD *)&v31 + 1) )
        {
          if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v31 + 1) + 8LL)) )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
            if ( !_InterlockedDecrement(v15 + 3) )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
          }
        }
        v30[0] = 0;
        v16 = ((__int64 (__fastcall *)(_BYTE *))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data2)(v30);
        *(_BYTE *)(*(__int64 (__fastcall **)(__int64))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)((__int64)v8 + 658) = v16;
        result = Microsoft::RdpNano::RendezvousSource::ComputeDegreeOfRedundancy(v8);
        goto LABEL_67;
      }
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(&v31);
      if ( (_QWORD)v31 && *(_BYTE *)(v31 + 128) != (_BYTE)v10 )
      {
        v27 = 0;
        v28 = 0;
        std::string::_Construct<1,char const *>(
          &v27,
          "AutoReconnectThread: DoR==0, calling CreateChannel (retry=%u/%u)",
          v10 + 64,
          v11);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,unsigned int,unsigned int>(
          (unsigned int)&v31,
          (unsigned int)"RENDEZVOUS",
          (unsigned int)&v27,
          v4,
          a2);
        std::string::_Tidy_deallocate(&v27);
      }
      v12 = (volatile signed __int32 *)*((_QWORD *)&v31 + 1);
      if ( *((_QWORD *)&v31 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v31 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
          if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
        }
      }
      Microsoft::RdpNano::RendezvousSource::CreateChannel(v8);
      ++v4;
      if ( v9 )
      {
        if ( !_InterlockedDecrement(v9 + 2) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
          if ( !_InterlockedDecrement(v9 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
        }
      }
      v26[0] = (Microsoft::RdpNano::RendezvousSource *)5;
      std::this_thread::sleep_for<__int64,std::ratio<1,1>>(v26);
      if ( v4 >= a2 )
        goto LABEL_22;
    }
    v31 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(&v31);
    result = v31;
    if ( (_QWORD)v31 && *(_BYTE *)(v31 + 128) )
    {
      v27 = 0;
      v28 = 0;
      std::string::_Construct<1,char const *>(
        &v27,
        "AutoReconnectThread: source expired (weak_ptr lock failed) at retry=%u",
        70);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,unsigned long>(
        &v31,
        "RENDEZVOUS",
        &v27,
        v4);
      result = std::string::_Tidy_deallocate(&v27);
    }
    v18 = (volatile signed __int32 *)*((_QWORD *)&v31 + 1);
    if ( *((_QWORD *)&v31 + 1) )
    {
      result = _InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v31 + 1) + 8LL));
      if ( !result )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
        result = _InterlockedDecrement(v18 + 3);
        if ( !result )
          goto LABEL_66;
      }
    }
  }
  else
  {
LABEL_22:
    *(_OWORD *)v26 = 0;
    v13 = *(_QWORD *)(a1 + 8);
    if ( v13 )
    {
      v14 = *(_DWORD *)(v13 + 8);
      while ( v14 )
      {
        v19 = v14;
        v14 = _InterlockedCompareExchange((volatile signed __int32 *)(v13 + 8), v14 + 1, v14);
        if ( v19 == v14 )
        {
          v20 = *(Microsoft::RdpNano::RendezvousSource **)a1;
          v26[0] = *(Microsoft::RdpNano::RendezvousSource **)a1;
          v9 = *(volatile signed __int32 **)(a1 + 8);
          v26[1] = (Microsoft::RdpNano::RendezvousSource *)v9;
          goto LABEL_44;
        }
      }
    }
    v20 = v26[0];
    v9 = (volatile signed __int32 *)v26[1];
LABEL_44:
    if ( v20
      && *(_BYTE *)(*(__int64 (__fastcall **)(__int64))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)((__int64)v20 + 658) )
    {
      v31 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(&v31);
      if ( (_QWORD)v31 && *(_BYTE *)(v31 + 128) )
      {
        v27 = 0;
        v28 = 0;
        std::string::_Construct<1,char const *>(
          &v27,
          "AutoReconnectThread: TIMEOUT after %u retries, closing Rendezvous",
          65);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,unsigned long>(
          &v31,
          "RENDEZVOUS",
          &v27,
          a2);
        std::string::_Tidy_deallocate(&v27);
      }
      v21 = (volatile signed __int32 *)*((_QWORD *)&v31 + 1);
      if ( *((_QWORD *)&v31 + 1) )
      {
        if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v31 + 1) + 8LL)) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
          if ( !_InterlockedDecrement(v21 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
        }
      }
      result = Microsoft::Basix::Dct::IChannelSourceImplNoProp::Close(v20);
    }
    else
    {
      v31 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v31);
      result = v31;
      if ( (_QWORD)v31 && *(_BYTE *)(v31 + 128) )
      {
        if ( !v20
          || (v23 = "true",
              !*(_BYTE *)(*(__int64 (__fastcall **)(__int64))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)((__int64)v20 + 658)) )
        {
          v23 = "false";
        }
        v24 = "expired";
        if ( v20 )
          v24 = "alive";
        v27 = 0;
        v28 = 0;
        std::string::_Construct<1,char const *>(
          &v27,
          "AutoReconnectThread: exiting, source=%s reconnecting=%s",
          (const char *)0x37,
          v22);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,char const *,char const *>(
          (unsigned int)&v31,
          (unsigned int)"RENDEZVOUS",
          (unsigned int)&v27,
          (_DWORD)v24,
          (__int64)v23);
        result = std::string::_Tidy_deallocate(&v27);
      }
      v18 = (volatile signed __int32 *)*((_QWORD *)&v31 + 1);
      if ( *((_QWORD *)&v31 + 1) )
      {
        result = _InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v31 + 1) + 8LL));
        if ( !result )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
          result = _InterlockedDecrement(v18 + 3);
          if ( !result )
LABEL_66:
            result = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
        }
      }
    }
  }
LABEL_67:
  if ( v9 )
  {
    result = _InterlockedDecrement(v9 + 2);
    if ( !result )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
      result = _InterlockedDecrement(v9 + 3);
      if ( !result )
        result = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
    }
  }
  v25 = *(volatile signed __int32 **)(a1 + 8);
  if ( v25 )
  {
    result = _InterlockedDecrement(v25 + 3);
    if ( !result )
      return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
  }
  return result;
}

```

## disassembly

```asm
0x18010d0c8  mov     [rsp-8+arg_10], rbx
0x18010d0cd  push    rbp
0x18010d0ce  push    rsi
0x18010d0cf  push    rdi
0x18010d0d0  push    r12
0x18010d0d2  push    r13
0x18010d0d4  push    r14
0x18010d0d6  push    r15
0x18010d0d8  lea     rbp, [rsp-27h]
0x18010d0dd  mov     eax, 90h
0x18010d0e2  call    _alloca_probe
0x18010d0e7  sub     rsp, rax
0x18010d0ea  mov     rax, cs:__security_cookie
0x18010d0f1  xor     rax, rsp
0x18010d0f4  mov     [rbp+57h+var_40], rax
0x18010d0f8  mov     r12d, edx
0x18010d0fb  mov     r14, rcx
0x18010d0fe  mov     [rbp+57h+var_60], rcx
0x18010d102  xor     r15d, r15d
0x18010d105  or      r13d, 0FFFFFFFFh
0x18010d109  test    edx, edx
0x18010d10b  jz      loc_18010D271
0x18010d111  lfence
0x18010d114  xorps   xmm1, xmm1
0x18010d117  movdqu  xmmword ptr [rbp+57h+var_90], xmm1
0x18010d11c  mov     rdx, [r14+8]
0x18010d120  test    rdx, rdx
0x18010d123  jz      short loc_18010D13C
0x18010d125  mov     eax, [rdx+8]
0x18010d128  jmp     short loc_18010D138
0x18010d12a  lea     ecx, [rax+1]
0x18010d12d  lock cmpxchg [rdx+8], ecx
0x18010d132  jz      loc_18010D28E
0x18010d138  test    eax, eax
0x18010d13a  jnz     short loc_18010D12A
0x18010d13c  mov     rsi, [rbp+57h+var_90]
0x18010d140  mov     rdi, [rbp+57h+var_90+8]
0x18010d144  test    rsi, rsi
0x18010d147  jz      loc_18010D36F
0x18010d14d  mov     rcx, rsi; this
0x18010d150  call    ?ComputeDegreeOfRedundancy@RendezvousSource@RdpNano@Microsoft@@QEAAIXZ; Microsoft::RdpNano::RendezvousSource::ComputeDegreeOfRedundancy(void)
0x18010d155  mov     ebx, eax
0x18010d157  xorps   xmm0, xmm0
0x18010d15a  lea     rcx, [rbp+57h+var_50]
0x18010d15e  movups  [rbp+57h+var_50], xmm0
0x18010d162  test    eax, eax
0x18010d164  jnz     loc_18010D2A2
0x18010d16a  call    ??$SelectEvent@VTraceWarning@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(void)
0x18010d16f  nop
0x18010d170  mov     rax, qword ptr [rbp+57h+var_50]
0x18010d174  test    rax, rax
0x18010d177  jz      short loc_18010D1CC
0x18010d179  cmp     [rax+80h], bl
0x18010d17f  jz      short loc_18010D1CC
0x18010d181  xorps   xmm0, xmm0
0x18010d184  movups  [rbp+57h+var_80], xmm0
0x18010d188  xorps   xmm1, xmm1
0x18010d18b  movdqu  [rbp+57h+var_70], xmm1
0x18010d190  lea     r8d, [rbx+40h]
0x18010d194  lea     rdx, aAutoreconnectt_8; "AutoReconnectThread: DoR==0, calling Cr"...
0x18010d19b  lea     rcx, [rbp+57h+var_80]
0x18010d19f  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18010d1a4  nop
0x18010d1a5  mov     dword ptr [rsp+0C0h+var_A0], r12d
0x18010d1aa  mov     r9d, r15d
0x18010d1ad  lea     r8, [rbp+57h+var_80]
0x18010d1b1  lea     rdx, aRendezvous_1; "RENDEZVOUS"
0x18010d1b8  lea     rcx, [rbp+57h+var_50]
0x18010d1bc  call    ??$TraceMessage@VTraceWarning@Basix@Microsoft@@II@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@II@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,uint,uint>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>> const &,char const *,std::string const &,uint,uint)
0x18010d1c1  nop
0x18010d1c2  lea     rcx, [rbp+57h+var_80]
0x18010d1c6  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18010d1cb  nop
0x18010d1cc  mov     rbx, qword ptr [rbp+57h+var_50+8]
0x18010d1d0  test    rbx, rbx
0x18010d1d3  jz      short loc_18010D20E
0x18010d1d5  mov     eax, r13d
0x18010d1d8  lock xadd [rbx+8], eax
0x18010d1dd  add     eax, r13d
0x18010d1e0  jnz     short loc_18010D20E
0x18010d1e2  mov     rax, [rbx]
0x18010d1e5  mov     rcx, rbx
0x18010d1e8  mov     rax, [rax]
0x18010d1eb  call    cs:__guard_dispatch_icall_fptr
0x18010d1f1  mov     eax, r13d
0x18010d1f4  lock xadd [rbx+0Ch], eax
0x18010d1f9  add     eax, r13d
0x18010d1fc  jnz     short loc_18010D20E
0x18010d1fe  mov     rax, [rbx]
0x18010d201  mov     rcx, rbx
0x18010d204  mov     rax, [rax+8]
0x18010d208  call    cs:__guard_dispatch_icall_fptr
0x18010d20e  mov     rcx, rsi; this
0x18010d211  call    ?CreateChannel@RendezvousSource@RdpNano@Microsoft@@QEAAXXZ; Microsoft::RdpNano::RendezvousSource::CreateChannel(void)
0x18010d216  inc     r15d
0x18010d219  test    rdi, rdi
0x18010d21c  jz      short loc_18010D257
0x18010d21e  mov     eax, r13d
0x18010d221  lock xadd [rdi+8], eax
0x18010d226  add     eax, r13d
0x18010d229  jnz     short loc_18010D257
0x18010d22b  mov     rax, [rdi]
0x18010d22e  mov     rcx, rdi
0x18010d231  mov     rax, [rax]
0x18010d234  call    cs:__guard_dispatch_icall_fptr
0x18010d23a  mov     eax, r13d
0x18010d23d  lock xadd [rdi+0Ch], eax
0x18010d242  add     eax, r13d
0x18010d245  jnz     short loc_18010D257
0x18010d247  mov     rax, [rdi]
0x18010d24a  mov     rcx, rdi
0x18010d24d  mov     rax, [rax+8]
0x18010d251  call    cs:__guard_dispatch_icall_fptr
0x18010d257  mov     [rbp+57h+var_90], 5
0x18010d25f  lea     rcx, [rbp+57h+var_90]
0x18010d263  call    ??$sleep_for@_JU?$ratio@$00$00@std@@@this_thread@std@@YAXAEBV?$duration@_JU?$ratio@$00$00@std@@@chrono@1@@Z; std::this_thread::sleep_for<__int64,std::ratio<1,1>>(std::chrono::duration<__int64,std::ratio<1,1>> const &)
0x18010d268  cmp     r15d, r12d
0x18010d26b  jb      loc_18010D114
0x18010d271  xorps   xmm1, xmm1
0x18010d274  movdqu  xmmword ptr [rbp+57h+var_90], xmm1
0x18010d279  mov     rdx, [r14+8]
0x18010d27d  test    rdx, rdx
0x18010d280  jz      loc_18010D43B
0x18010d286  mov     eax, [rdx+8]
0x18010d289  jmp     loc_18010D437
0x18010d28e  mov     rsi, [r14]
0x18010d291  mov     [rbp+57h+var_90], rsi
0x18010d295  mov     rdi, [r14+8]
0x18010d299  mov     [rbp+57h+var_90+8], rdi
0x18010d29d  jmp     loc_18010D144
0x18010d2a2  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x18010d2a7  nop
0x18010d2a8  mov     rax, qword ptr [rbp+57h+var_50]
0x18010d2ac  test    rax, rax
0x18010d2af  jz      short loc_18010D302
0x18010d2b1  cmp     byte ptr [rax+80h], 0
0x18010d2b8  jz      short loc_18010D302
0x18010d2ba  xorps   xmm0, xmm0
0x18010d2bd  movups  [rbp+57h+var_80], xmm0
0x18010d2c1  xorps   xmm1, xmm1
0x18010d2c4  movdqu  [rbp+57h+var_70], xmm1
0x18010d2c9  mov     r8d, 3Bh ; ';'
0x18010d2cf  lea     rdx, aAutoreconnectt_3; "AutoReconnectThread: DoR=%u > 0, cleari"...
0x18010d2d6  lea     rcx, [rbp+57h+var_80]
0x18010d2da  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18010d2df  nop
0x18010d2e0  mov     r9d, ebx
0x18010d2e3  lea     r8, [rbp+57h+var_80]
0x18010d2e7  lea     rdx, aRendezvous_1; "RENDEZVOUS"
0x18010d2ee  lea     rcx, [rbp+57h+var_50]
0x18010d2f2  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@I@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@I@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,uint>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &,uint)
0x18010d2f7  nop
0x18010d2f8  lea     rcx, [rbp+57h+var_80]
0x18010d2fc  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18010d301  nop
0x18010d302  mov     rbx, qword ptr [rbp+57h+var_50+8]
0x18010d306  test    rbx, rbx
0x18010d309  jz      short loc_18010D344
0x18010d30b  mov     eax, r13d
0x18010d30e  lock xadd [rbx+8], eax
0x18010d313  add     eax, r13d
0x18010d316  jnz     short loc_18010D344
0x18010d318  mov     rax, [rbx]
0x18010d31b  mov     rcx, rbx
0x18010d31e  mov     rax, [rax]
0x18010d321  call    cs:__guard_dispatch_icall_fptr
0x18010d327  mov     eax, r13d
0x18010d32a  lock xadd [rbx+0Ch], eax
0x18010d32f  add     eax, r13d
0x18010d332  jnz     short loc_18010D344
0x18010d334  mov     rax, [rbx]
0x18010d337  mov     rcx, rbx
0x18010d33a  mov     rax, [rax+8]
0x18010d33e  call    cs:__guard_dispatch_icall_fptr
0x18010d344  mov     [rbp+57h+var_58], 0
0x18010d348  lea     rcx, [rbp+57h+var_58]
0x18010d34c  call    near ptr ??$launder@USecurityCookieHash@RdpNano@Microsoft@@@core@boost@@YAPEAUSecurityCookieHash@RdpNano@Microsoft@@PEAU234@@Z.Data2; boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>(Microsoft::RdpNano::SecurityCookieHash *)
0x18010d351  mov     bl, al
0x18010d353  lea     rcx, [rsi+292h]
0x18010d35a  call    near ptr ??$launder@USecurityCookieHash@RdpNano@Microsoft@@@core@boost@@YAPEAUSecurityCookieHash@RdpNano@Microsoft@@PEAU234@@Z.Data1; boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>(Microsoft::RdpNano::SecurityCookieHash *)
0x18010d35f  xchg    bl, [rax]
0x18010d361  mov     rcx, rsi; this
0x18010d364  call    ?ComputeDegreeOfRedundancy@RendezvousSource@RdpNano@Microsoft@@QEAAIXZ; Microsoft::RdpNano::RendezvousSource::ComputeDegreeOfRedundancy(void)
0x18010d369  nop
0x18010d36a  jmp     loc_18010D627
0x18010d36f  xorps   xmm0, xmm0
0x18010d372  movups  [rbp+57h+var_50], xmm0
0x18010d376  lea     rcx, [rbp+57h+var_50]
0x18010d37a  call    ??$SelectEvent@VTraceWarning@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(void)
0x18010d37f  nop
0x18010d380  mov     rax, qword ptr [rbp+57h+var_50]
0x18010d384  test    rax, rax
0x18010d387  jz      short loc_18010D3DA
0x18010d389  cmp     byte ptr [rax+80h], 0
0x18010d390  jz      short loc_18010D3DA
0x18010d392  xorps   xmm0, xmm0
0x18010d395  movups  [rbp+57h+var_80], xmm0
0x18010d399  xorps   xmm1, xmm1
0x18010d39c  movdqu  [rbp+57h+var_70], xmm1
0x18010d3a1  mov     r8d, 46h ; 'F'
0x18010d3a7  lea     rdx, aAutoreconnectt_0; "AutoReconnectThread: source expired (we"...
0x18010d3ae  lea     rcx, [rbp+57h+var_80]
0x18010d3b2  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18010d3b7  nop
0x18010d3b8  mov     r9d, r15d
0x18010d3bb  lea     r8, [rbp+57h+var_80]
0x18010d3bf  lea     rdx, aRendezvous_1; "RENDEZVOUS"
0x18010d3c6  lea     rcx, [rbp+57h+var_50]
0x18010d3ca  call    ??$TraceMessage@VTraceWarning@Basix@Microsoft@@K@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@K@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,ulong>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>> const &,char const *,std::string const &,ulong)
0x18010d3cf  nop
0x18010d3d0  lea     rcx, [rbp+57h+var_80]
0x18010d3d4  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18010d3d9  nop
0x18010d3da  mov     rbx, qword ptr [rbp+57h+var_50+8]
0x18010d3de  test    rbx, rbx
0x18010d3e1  jz      short loc_18010D36A
0x18010d3e3  mov     eax, r13d
0x18010d3e6  lock xadd [rbx+8], eax
0x18010d3eb  add     eax, r13d
0x18010d3ee  jnz     loc_18010D36A
0x18010d3f4  mov     rax, [rbx]
0x18010d3f7  mov     rcx, rbx
0x18010d3fa  mov     rax, [rax]
0x18010d3fd  call    cs:__guard_dispatch_icall_fptr
0x18010d403  mov     eax, r13d
0x18010d406  lock xadd [rbx+0Ch], eax
0x18010d40b  add     eax, r13d
0x18010d40e  jnz     loc_18010D36A
0x18010d414  mov     rax, [rbx]
0x18010d417  mov     rcx, rbx
0x18010d41a  mov     rax, [rax+8]
0x18010d41e  call    cs:__guard_dispatch_icall_fptr
0x18010d424  jmp     loc_18010D36A
0x18010d429  lea     ecx, [rax+1]
0x18010d42c  lock cmpxchg [rdx+8], ecx
0x18010d431  jz      loc_18010D51D
0x18010d437  test    eax, eax
0x18010d439  jnz     short loc_18010D429
0x18010d43b  mov     rsi, [rbp+57h+var_90]
0x18010d43f  mov     rdi, [rbp+57h+var_90+8]
0x18010d443  test    rsi, rsi
0x18010d446  jz      loc_18010D531
0x18010d44c  lea     rcx, [rsi+292h]
0x18010d453  call    near ptr ??$launder@USecurityCookieHash@RdpNano@Microsoft@@@core@boost@@YAPEAUSecurityCookieHash@RdpNano@Microsoft@@PEAU234@@Z.Data1; boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>(Microsoft::RdpNano::SecurityCookieHash *)
0x18010d458  mov     cl, [rax]
0x18010d45a  nop
0x18010d45b  test    cl, cl
0x18010d45d  jz      loc_18010D531
0x18010d463  xorps   xmm0, xmm0
0x18010d466  movups  [rbp+57h+var_50], xmm0
0x18010d46a  lea     rcx, [rbp+57h+var_50]
0x18010d46e  call    ??$SelectEvent@VTraceWarning@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(void)
0x18010d473  nop
0x18010d474  mov     rax, qword ptr [rbp+57h+var_50]
0x18010d478  test    rax, rax
0x18010d47b  jz      short loc_18010D4CE
0x18010d47d  cmp     byte ptr [rax+80h], 0
0x18010d484  jz      short loc_18010D4CE
0x18010d486  xorps   xmm0, xmm0
0x18010d489  movups  [rbp+57h+var_80], xmm0
0x18010d48d  xorps   xmm1, xmm1
0x18010d490  movdqu  [rbp+57h+var_70], xmm1
0x18010d495  mov     r8d, 41h ; 'A'
0x18010d49b  lea     rdx, aAutoreconnectt_4; "AutoReconnectThread: TIMEOUT after %u r"...
0x18010d4a2  lea     rcx, [rbp+57h+var_80]
0x18010d4a6  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18010d4ab  nop
0x18010d4ac  mov     r9d, r12d
0x18010d4af  lea     r8, [rbp+57h+var_80]
0x18010d4b3  lea     rdx, aRendezvous_1; "RENDEZVOUS"
0x18010d4ba  lea     rcx, [rbp+57h+var_50]
0x18010d4be  call    ??$TraceMessage@VTraceWarning@Basix@Microsoft@@K@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@K@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,ulong>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>> const &,char const *,std::string const &,ulong)
0x18010d4c3  nop
0x18010d4c4  lea     rcx, [rbp+57h+var_80]
0x18010d4c8  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18010d4cd  nop
0x18010d4ce  mov     rbx, qword ptr [rbp+57h+var_50+8]
0x18010d4d2  test    rbx, rbx
0x18010d4d5  jz      short loc_18010D510
0x18010d4d7  mov     eax, r13d
0x18010d4da  lock xadd [rbx+8], eax
0x18010d4df  add     eax, r13d
0x18010d4e2  jnz     short loc_18010D510
0x18010d4e4  mov     rax, [rbx]
0x18010d4e7  mov     rcx, rbx
0x18010d4ea  mov     rax, [rax]
0x18010d4ed  call    cs:__guard_dispatch_icall_fptr
0x18010d4f3  mov     eax, r13d
0x18010d4f6  lock xadd [rbx+0Ch], eax
0x18010d4fb  add     eax, r13d
0x18010d4fe  jnz     short loc_18010D510
0x18010d500  mov     rax, [rbx]
0x18010d503  mov     rcx, rbx
0x18010d506  mov     rax, [rax+8]
0x18010d50a  call    cs:__guard_dispatch_icall_fptr
0x18010d510  mov     rcx, rsi
0x18010d513  call    ?Close@IChannelSourceImplNoProp@Dct@Basix@Microsoft@@UEAA?AW4State@BasicStateManagement@detail@234@XZ; Microsoft::Basix::Dct::IChannelSourceImplNoProp::Close(void)
0x18010d518  jmp     loc_18010D627
0x18010d51d  mov     rsi, [r14]
0x18010d520  mov     [rbp+57h+var_90], rsi
  ... truncated ...
```
