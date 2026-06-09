# _Microsoft::RdpNano::RdpSideTransport::GetDctChannelExceptionCode_::_1_::catch$171

- ea: `0x1803889b7`
- end: `0x18038912d`
- name: `_Microsoft::RdpNano::RdpSideTransport::GetDctChannelExceptionCode_::_1_::catch$171`
- size: `1910`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000d9c0`
- `0x180015bb8`
- `0x18001902c`
- `0x180024760`
- `0x1800de94c`
- `0x1802ea074`
- `0x18032f050`
- `0x180375c40`
- `0x1803889b7`

## string_xrefs

- `0x180388f06`: `E_RDPNANO_DCT_PACKET_WRITE_INCOMPLETE:`
- `0x180388e47`: `E_RDPNANO_DCT_DUMMY_PACKET_WRITE_2_WINSOCK_FAILED:`
- `0x180388cc9`: `E_RDPNANO_DCT_PACKET_WRITE_THREAD_HANG:`
- `0x180388d88`: `E_RDPNANO_TRANSPORT_READ_HANG:`
- `0x180388a47`: `RdpSideTransport::GetDctChannelExceptionCode DCTException error code (source = %d): %d %s`

## pseudocode

```c
__int64 __fastcall Microsoft::RdpNano::RdpSideTransport::GetDctChannelExceptionCode_::_1_::catch_171(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rsi
  int v4; // ebx
  __int64 v5; // rax
  __int64 *Description; // rax
  int v7; // r9d
  __int64 v8; // rdi
  volatile signed __int32 *v9; // rdi
  __int64 v10; // rcx
  int v11; // ebx
  int v12; // ebx
  int v13; // ebx
  int v14; // ebx
  int v15; // ebx
  __int64 v16; // rbx
  __int64 v17; // rdx
  _OWORD *v18; // rbx
  __int64 v19; // rbx
  __int64 v20; // rdx
  _OWORD *v21; // rbx
  __int64 v22; // rbx
  __int64 v23; // rdx
  _OWORD *v24; // rbx
  __int64 v25; // rbx
  __int64 v26; // rdx
  _OWORD *v27; // rbx
  __int64 v28; // rbx
  __int64 v29; // rdx
  _OWORD *v30; // rbx
  __int64 v31; // rbx
  __int64 v32; // rdx
  _OWORD *v33; // rbx
  __int64 v34; // rbx
  __int64 v35; // rdx
  _OWORD *v36; // rbx
  __int64 v37; // rbx
  __int64 v38; // rdx
  _OWORD *v39; // rbx
  const char *v41; // [rsp+20h] [rbp-38h]

  v3 = *(_QWORD *)(a2 + 512);
  v4 = *(_DWORD *)(v3 + 128);
  *(_OWORD *)(a2 + 576) = 0;
  Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(a2 + 576);
  v5 = *(_QWORD *)(a2 + 576);
  if ( v5 && *(_BYTE *)(v5 + 128) )
  {
    Description = (__int64 *)Microsoft::Basix::Exception::CreateDescription(a2 + 88, v3);
    v8 = (__int64)Description;
    if ( (unsigned __int64)Description[3] > 0xF )
      v8 = *Description;
    *(_OWORD *)(a2 + 56) = 0;
    *(_QWORD *)(a2 + 72) = 0;
    *(_QWORD *)(a2 + 80) = 0;
    std::string::_Construct<1,char const *>(
      a2 + 56,
      "RdpSideTransport::GetDctChannelExceptionCode DCTException error code (source = %d): %d %s",
      89,
      v7,
      v41);
    Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,unsigned int,unsigned int,char const *>(
      a2 + 576,
      (unsigned int)"RDPNANO",
      a2 + 56,
      *(unsigned __int8 *)(a2 + 48),
      v4,
      v8);
    std::string::_Tidy_deallocate(a2 + 56);
    std::string::_Tidy_deallocate(a2 + 88);
  }
  v9 = *(volatile signed __int32 **)(a2 + 584);
  if ( v9 )
  {
    if ( _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
      if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
    }
  }
  v10 = a2 + 88;
  if ( v4 )
  {
    v11 = v4 - 1;
    if ( v11 )
    {
      v12 = v11 - 1;
      if ( v12 )
      {
        v13 = v12 - 1;
        if ( v13 )
        {
          v14 = v13 - 1;
          if ( v14 )
          {
            v15 = v14 - 1;
            if ( v15 )
            {
              if ( v15 == 1 )
              {
                *(_DWORD *)(a2 + 576) = -1950863625;
                v19 = Microsoft::Basix::Exception::CreateDescription(v10, v3);
                *(_OWORD *)(a2 + 56) = 0;
                *(_QWORD *)(a2 + 72) = 0;
                *(_QWORD *)(a2 + 80) = 0;
                std::string::_Construct<1,char const *>(a2 + 56, "E_RDPNANO_NETWORK_DROP:", 23);
                LOBYTE(v20) = *(_BYTE *)(a2 + 48);
                std::string::string(a2 + 184, v20, a2 + 56, v19);
                v21 = *(_OWORD **)(a2 + 560);
                if ( v21 != (_OWORD *)(a2 + 184) )
                {
                  std::string::_Tidy_deallocate(*(_QWORD *)(a2 + 560));
                  *v21 = *(_OWORD *)(a2 + 184);
                  v21[1] = *(_OWORD *)(a2 + 200);
                  *(_QWORD *)(a2 + 200) = 0;
                  *(_QWORD *)(a2 + 208) = 15;
                  *(_BYTE *)(a2 + 184) = 0;
                }
                std::string::_Tidy_deallocate(a2 + 184);
                std::string::_Tidy_deallocate(a2 + 56);
              }
              else
              {
                *(_DWORD *)(a2 + 576) = -1950744577;
                v16 = Microsoft::Basix::Exception::CreateDescription(v10, v3);
                *(_OWORD *)(a2 + 56) = 0;
                *(_QWORD *)(a2 + 72) = 0;
                *(_QWORD *)(a2 + 80) = 0;
                std::string::_Construct<1,char const *>(a2 + 56, "E_RDPNANO_SOURCE_UNEXPECTED_ERROR:", 34);
                LOBYTE(v17) = *(_BYTE *)(a2 + 48);
                std::string::string(a2 + 152, v17, a2 + 56, v16);
                v18 = *(_OWORD **)(a2 + 560);
                if ( v18 != (_OWORD *)(a2 + 152) )
                {
                  std::string::_Tidy_deallocate(*(_QWORD *)(a2 + 560));
                  *v18 = *(_OWORD *)(a2 + 152);
                  v18[1] = *(_OWORD *)(a2 + 168);
                  *(_QWORD *)(a2 + 168) = 0;
                  *(_QWORD *)(a2 + 176) = 15;
                  *(_BYTE *)(a2 + 152) = 0;
                }
                std::string::_Tidy_deallocate(a2 + 152);
                std::string::_Tidy_deallocate(a2 + 56);
              }
            }
            else
            {
              *(_DWORD *)(a2 + 576) = -1950863601;
              v22 = Microsoft::Basix::Exception::CreateDescription(v10, v3);
              *(_OWORD *)(a2 + 56) = 0;
              *(_QWORD *)(a2 + 72) = 0;
              *(_QWORD *)(a2 + 80) = 0;
              std::string::_Construct<1,char const *>(a2 + 56, "E_RDPNANO_DCT_PACKET_WRITE_THREAD_HANG:", 39);
              LOBYTE(v23) = *(_BYTE *)(a2 + 48);
              std::string::string(a2 + 216, v23, a2 + 56, v22);
              v24 = *(_OWORD **)(a2 + 560);
              if ( v24 != (_OWORD *)(a2 + 216) )
              {
                std::string::_Tidy_deallocate(*(_QWORD *)(a2 + 560));
                *v24 = *(_OWORD *)(a2 + 216);
                v24[1] = *(_OWORD *)(a2 + 232);
                *(_QWORD *)(a2 + 232) = 0;
                *(_QWORD *)(a2 + 240) = 15;
                *(_BYTE *)(a2 + 216) = 0;
              }
              std::string::_Tidy_deallocate(a2 + 216);
              std::string::_Tidy_deallocate(a2 + 56);
            }
          }
          else
          {
            *(_DWORD *)(a2 + 576) = -1950863623;
            v25 = Microsoft::Basix::Exception::CreateDescription(v10, v3);
            *(_OWORD *)(a2 + 56) = 0;
            *(_QWORD *)(a2 + 72) = 0;
            *(_QWORD *)(a2 + 80) = 0;
            std::string::_Construct<1,char const *>(a2 + 56, "E_RDPNANO_TRANSPORT_READ_HANG:", 30);
            LOBYTE(v26) = *(_BYTE *)(a2 + 48);
            std::string::string(a2 + 248, v26, a2 + 56, v25);
            v27 = *(_OWORD **)(a2 + 560);
            if ( v27 != (_OWORD *)(a2 + 248) )
            {
              std::string::_Tidy_deallocate(*(_QWORD *)(a2 + 560));
              *v27 = *(_OWORD *)(a2 + 248);
              v27[1] = *(_OWORD *)(a2 + 264);
              *(_QWORD *)(a2 + 264) = 0;
              *(_QWORD *)(a2 + 272) = 15;
              *(_BYTE *)(a2 + 248) = 0;
            }
            std::string::_Tidy_deallocate(a2 + 248);
            std::string::_Tidy_deallocate(a2 + 56);
          }
        }
        else
        {
          *(_DWORD *)(a2 + 576) = -1950874478;
          v28 = Microsoft::Basix::Exception::CreateDescription(v10, v3);
          *(_OWORD *)(a2 + 56) = 0;
          *(_QWORD *)(a2 + 72) = 0;
          *(_QWORD *)(a2 + 80) = 0;
          std::string::_Construct<1,char const *>(a2 + 56, "E_RDPNANO_DCT_DUMMY_PACKET_WRITE_2_WINSOCK_FAILED:", 50);
          LOBYTE(v29) = *(_BYTE *)(a2 + 48);
          std::string::string(a2 + 280, v29, a2 + 56, v28);
          v30 = *(_OWORD **)(a2 + 560);
          if ( v30 != (_OWORD *)(a2 + 280) )
          {
            std::string::_Tidy_deallocate(*(_QWORD *)(a2 + 560));
            *v30 = *(_OWORD *)(a2 + 280);
            v30[1] = *(_OWORD *)(a2 + 296);
            *(_QWORD *)(a2 + 296) = 0;
            *(_QWORD *)(a2 + 304) = 15;
            *(_BYTE *)(a2 + 280) = 0;
          }
          std::string::_Tidy_deallocate(a2 + 280);
          std::string::_Tidy_deallocate(a2 + 56);
        }
      }
      else
      {
        *(_DWORD *)(a2 + 576) = -1950874652;
        v31 = Microsoft::Basix::Exception::CreateDescription(v10, v3);
        *(_OWORD *)(a2 + 56) = 0;
        *(_QWORD *)(a2 + 72) = 0;
        *(_QWORD *)(a2 + 80) = 0;
        std::string::_Construct<1,char const *>(a2 + 56, "E_RDPNANO_DCT_PACKET_WRITE_INCOMPLETE:", 38);
        LOBYTE(v32) = *(_BYTE *)(a2 + 48);
        std::string::string(a2 + 312, v32, a2 + 56, v31);
        v33 = *(_OWORD **)(a2 + 560);
        if ( v33 != (_OWORD *)(a2 + 312) )
        {
          std::string::_Tidy_deallocate(*(_QWORD *)(a2 + 560));
          *v33 = *(_OWORD *)(a2 + 312);
          v33[1] = *(_OWORD *)(a2 + 328);
          *(_QWORD *)(a2 + 328) = 0;
          *(_QWORD *)(a2 + 336) = 15;
          *(_BYTE *)(a2 + 312) = 0;
        }
        std::string::_Tidy_deallocate(a2 + 312);
        std::string::_Tidy_deallocate(a2 + 56);
      }
    }
    else
    {
      *(_DWORD *)(a2 + 576) = -1950863646;
      v34 = Microsoft::Basix::Exception::CreateDescription(v10, v3);
      *(_OWORD *)(a2 + 56) = 0;
      *(_QWORD *)(a2 + 72) = 0;
      *(_QWORD *)(a2 + 80) = 0;
      std::string::_Construct<1,char const *>(a2 + 56, "E_RDPNANO_RELIABILITY_CONTROLLER_TIMEOUT:", 41);
      LOBYTE(v35) = *(_BYTE *)(a2 + 48);
      std::string::string(a2 + 344, v35, a2 + 56, v34);
      v36 = *(_OWORD **)(a2 + 560);
      if ( v36 != (_OWORD *)(a2 + 344) )
      {
        std::string::_Tidy_deallocate(*(_QWORD *)(a2 + 560));
        *v36 = *(_OWORD *)(a2 + 344);
        v36[1] = *(_OWORD *)(a2 + 360);
        *(_QWORD *)(a2 + 360) = 0;
        *(_QWORD *)(a2 + 368) = 15;
        *(_BYTE *)(a2 + 344) = 0;
      }
      std::string::_Tidy_deallocate(a2 + 344);
      std::string::_Tidy_deallocate(a2 + 56);
    }
  }
  else
  {
    *(_DWORD *)(a2 + 576) = -1950874533;
    v37 = Microsoft::Basix::Exception::CreateDescription(v10, v3);
    *(_OWORD *)(a2 + 56) = 0;
    *(_QWORD *)(a2 + 72) = 0;
    *(_QWORD *)(a2 + 80) = 0;
    std::string::_Construct<1,char const *>(a2 + 56, "E_RDPNANO_TURN_SERVER_DOWN:", 27);
    LOBYTE(v38) = *(_BYTE *)(a2 + 48);
    std::string::string(a2 + 376, v38, a2 + 56, v37);
    v39 = *(_OWORD **)(a2 + 560);
    if ( v39 != (_OWORD *)(a2 + 376) )
    {
      std::string::_Tidy_deallocate(*(_QWORD *)(a2 + 560));
      *v39 = *(_OWORD *)(a2 + 376);
      v39[1] = *(_OWORD *)(a2 + 392);
      *(_QWORD *)(a2 + 392) = 0;
      *(_QWORD *)(a2 + 400) = 15;
      *(_BYTE *)(a2 + 376) = 0;
    }
    std::string::_Tidy_deallocate(a2 + 376);
    std::string::_Tidy_deallocate(a2 + 56);
  }
  std::string::_Tidy_deallocate(a2 + 88);
  return 0;
}

```

## disassembly

```asm
0x1803889b7  mov     [rsp+arg_8], rdx
0x1803889bc  push    rbx
0x1803889bd  push    rbp
0x1803889be  push    rsi
0x1803889bf  push    rdi
0x1803889c0  mov     eax, 38h
0x1803889c5  call    _alloca_probe
0x1803889ca  sub     rsp, rax
0x1803889cd  mov     rbp, rdx
0x1803889d0  mov     rsi, [rbp+200h]
0x1803889d7  mov     ebx, [rsi+80h]
0x1803889dd  xorps   xmm0, xmm0
0x1803889e0  movups  xmmword ptr [rbp+240h], xmm0
0x1803889e7  lea     rcx, [rbp+240h]
0x1803889ee  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x1803889f3  nop
0x1803889f4  mov     rax, [rbp+240h]
0x1803889fb  test    rax, rax
0x1803889fe  jz      loc_180388A92
0x180388a04  cmp     byte ptr [rax+80h], 0
0x180388a0b  jz      loc_180388A92
0x180388a11  mov     rdx, rsi
0x180388a14  lea     rcx, [rbp+58h]
0x180388a18  call    ?CreateDescription@Exception@Basix@Microsoft@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBVexception@5@@Z; Microsoft::Basix::Exception::CreateDescription(std::exception const &)
0x180388a1d  mov     rdi, rax
0x180388a20  cmp     qword ptr [rax+18h], 0Fh
0x180388a25  jbe     short loc_180388A2A
0x180388a27  mov     rdi, [rax]
0x180388a2a  xorps   xmm0, xmm0
0x180388a2d  movups  xmmword ptr [rbp+38h], xmm0
0x180388a31  mov     qword ptr [rbp+48h], 0
0x180388a39  mov     qword ptr [rbp+50h], 0
0x180388a41  mov     r8d, 59h ; 'Y'
0x180388a47  lea     rdx, aRdpsidetranspo_17; "RdpSideTransport::GetDctChannelExceptio"...
0x180388a4e  lea     rcx, [rbp+38h]
0x180388a52  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180388a57  nop
0x180388a58  movzx   r9d, byte ptr [rbp+30h]
0x180388a5d  mov     [rsp+58h+var_30], rdi
0x180388a62  mov     dword ptr [rsp+58h+var_38], ebx
0x180388a66  lea     r8, [rbp+38h]
0x180388a6a  lea     rdx, aRdpnano; "RDPNANO"
0x180388a71  lea     rcx, [rbp+240h]
0x180388a78  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@IIPEBD@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@II1@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,uint,uint,char const *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &,uint,uint,char const *)
0x180388a7d  nop
0x180388a7e  lea     rcx, [rbp+38h]
0x180388a82  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180388a87  nop
0x180388a88  lea     rcx, [rbp+58h]
0x180388a8c  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180388a91  nop
0x180388a92  mov     rdi, [rbp+248h]
0x180388a99  test    rdi, rdi
0x180388a9c  jz      short loc_180388AD7
0x180388a9e  or      eax, 0FFFFFFFFh
0x180388aa1  lock xadd [rdi+8], eax
0x180388aa6  cmp     eax, 1
0x180388aa9  jnz     short loc_180388AD7
0x180388aab  mov     rax, [rdi]
0x180388aae  mov     rcx, rdi
0x180388ab1  mov     rax, [rax]
0x180388ab4  call    cs:__guard_dispatch_icall_fptr
0x180388aba  or      eax, 0FFFFFFFFh
0x180388abd  lock xadd [rdi+0Ch], eax
0x180388ac2  cmp     eax, 1
0x180388ac5  jnz     short loc_180388AD7
0x180388ac7  mov     rax, [rdi]
0x180388aca  mov     rcx, rdi
0x180388acd  mov     rax, [rax+8]
0x180388ad1  call    cs:__guard_dispatch_icall_fptr
0x180388ad7  mov     rdx, rsi
0x180388ada  lea     rcx, [rbp+58h]
0x180388ade  test    ebx, ebx
0x180388ae0  jz      loc_180389055
0x180388ae6  sub     ebx, 1
0x180388ae9  jz      loc_180388F96
0x180388aef  sub     ebx, 1
0x180388af2  jz      loc_180388ED7
0x180388af8  sub     ebx, 1
0x180388afb  jz      loc_180388E18
0x180388b01  sub     ebx, 1
0x180388b04  jz      loc_180388D59
0x180388b0a  sub     ebx, 1
0x180388b0d  jz      loc_180388C9A
0x180388b13  cmp     ebx, 1
0x180388b16  jz      loc_180388BDB
0x180388b1c  mov     dword ptr [rbp+240h], 8BB9FFFFh
0x180388b26  call    ?CreateDescription@Exception@Basix@Microsoft@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBVexception@5@@Z; Microsoft::Basix::Exception::CreateDescription(std::exception const &)
0x180388b2b  mov     rbx, rax
0x180388b2e  xorps   xmm0, xmm0
0x180388b31  movups  xmmword ptr [rbp+38h], xmm0
0x180388b35  mov     qword ptr [rbp+48h], 0
0x180388b3d  mov     qword ptr [rbp+50h], 0
0x180388b45  mov     r8d, 22h ; '"'
0x180388b4b  lea     rdx, aERdpnanoSource_2; "E_RDPNANO_SOURCE_UNEXPECTED_ERROR:"
0x180388b52  lea     rcx, [rbp+38h]
0x180388b56  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180388b5b  nop
0x180388b5c  mov     r9, rbx
0x180388b5f  lea     r8, [rbp+38h]
0x180388b63  mov     dl, [rbp+30h]
0x180388b66  lea     rcx, [rbp+98h]
0x180388b6d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x180388b72  lea     rax, [rbp+98h]
0x180388b79  mov     rbx, [rbp+230h]
0x180388b80  cmp     rbx, rax
0x180388b83  jz      short loc_180388BBF
0x180388b85  mov     rcx, rbx
0x180388b88  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180388b8d  movups  xmm0, xmmword ptr [rbp+98h]
0x180388b94  movups  xmmword ptr [rbx], xmm0
0x180388b97  movups  xmm1, xmmword ptr [rbp+0A8h]
0x180388b9e  movups  xmmword ptr [rbx+10h], xmm1
0x180388ba2  mov     qword ptr [rbp+0A8h], 0
0x180388bad  mov     qword ptr [rbp+0B0h], 0Fh
0x180388bb8  mov     byte ptr [rbp+98h], 0
0x180388bbf  lea     rcx, [rbp+98h]
0x180388bc6  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180388bcb  nop
0x180388bcc  lea     rcx, [rbp+38h]
0x180388bd0  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180388bd5  nop
0x180388bd6  jmp     loc_18038910F
0x180388bdb  mov     dword ptr [rbp+240h], 8BB82EF7h
0x180388be5  call    ?CreateDescription@Exception@Basix@Microsoft@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBVexception@5@@Z; Microsoft::Basix::Exception::CreateDescription(std::exception const &)
0x180388bea  mov     rbx, rax
0x180388bed  xorps   xmm0, xmm0
0x180388bf0  movups  xmmword ptr [rbp+38h], xmm0
0x180388bf4  mov     qword ptr [rbp+48h], 0
0x180388bfc  mov     qword ptr [rbp+50h], 0
0x180388c04  mov     r8d, 17h
0x180388c0a  lea     rdx, aERdpnanoNetwor; "E_RDPNANO_NETWORK_DROP:"
0x180388c11  lea     rcx, [rbp+38h]
0x180388c15  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180388c1a  nop
0x180388c1b  mov     r9, rbx
0x180388c1e  lea     r8, [rbp+38h]
0x180388c22  mov     dl, [rbp+30h]
0x180388c25  lea     rcx, [rbp+0B8h]
0x180388c2c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x180388c31  lea     rax, [rbp+0B8h]
0x180388c38  mov     rbx, [rbp+230h]
0x180388c3f  cmp     rbx, rax
0x180388c42  jz      short loc_180388C7E
0x180388c44  mov     rcx, rbx
0x180388c47  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180388c4c  movups  xmm0, xmmword ptr [rbp+0B8h]
0x180388c53  movups  xmmword ptr [rbx], xmm0
0x180388c56  movups  xmm1, xmmword ptr [rbp+0C8h]
0x180388c5d  movups  xmmword ptr [rbx+10h], xmm1
0x180388c61  mov     qword ptr [rbp+0C8h], 0
0x180388c6c  mov     qword ptr [rbp+0D0h], 0Fh
0x180388c77  mov     byte ptr [rbp+0B8h], 0
0x180388c7e  lea     rcx, [rbp+0B8h]
0x180388c85  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180388c8a  nop
0x180388c8b  lea     rcx, [rbp+38h]
0x180388c8f  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180388c94  nop
0x180388c95  jmp     loc_18038910F
0x180388c9a  mov     dword ptr [rbp+240h], 8BB82F0Fh
0x180388ca4  call    ?CreateDescription@Exception@Basix@Microsoft@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBVexception@5@@Z; Microsoft::Basix::Exception::CreateDescription(std::exception const &)
0x180388ca9  mov     rbx, rax
0x180388cac  xorps   xmm0, xmm0
0x180388caf  movups  xmmword ptr [rbp+38h], xmm0
0x180388cb3  mov     qword ptr [rbp+48h], 0
0x180388cbb  mov     qword ptr [rbp+50h], 0
0x180388cc3  mov     r8d, 27h ; '''
0x180388cc9  lea     rdx, aERdpnanoDctPac; "E_RDPNANO_DCT_PACKET_WRITE_THREAD_HANG:"
0x180388cd0  lea     rcx, [rbp+38h]
0x180388cd4  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180388cd9  nop
0x180388cda  mov     r9, rbx
0x180388cdd  lea     r8, [rbp+38h]
0x180388ce1  mov     dl, [rbp+30h]
0x180388ce4  lea     rcx, [rbp+0D8h]
0x180388ceb  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x180388cf0  lea     rax, [rbp+0D8h]
0x180388cf7  mov     rbx, [rbp+230h]
0x180388cfe  cmp     rbx, rax
0x180388d01  jz      short loc_180388D3D
0x180388d03  mov     rcx, rbx
0x180388d06  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180388d0b  movups  xmm0, xmmword ptr [rbp+0D8h]
0x180388d12  movups  xmmword ptr [rbx], xmm0
0x180388d15  movups  xmm1, xmmword ptr [rbp+0E8h]
0x180388d1c  movups  xmmword ptr [rbx+10h], xmm1
0x180388d20  mov     qword ptr [rbp+0E8h], 0
0x180388d2b  mov     qword ptr [rbp+0F0h], 0Fh
0x180388d36  mov     byte ptr [rbp+0D8h], 0
0x180388d3d  lea     rcx, [rbp+0D8h]
0x180388d44  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180388d49  nop
0x180388d4a  lea     rcx, [rbp+38h]
0x180388d4e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180388d53  nop
0x180388d54  jmp     loc_18038910F
0x180388d59  mov     dword ptr [rbp+240h], 8BB82EF9h
0x180388d63  call    ?CreateDescription@Exception@Basix@Microsoft@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBVexception@5@@Z; Microsoft::Basix::Exception::CreateDescription(std::exception const &)
0x180388d68  mov     rbx, rax
0x180388d6b  xorps   xmm0, xmm0
0x180388d6e  movups  xmmword ptr [rbp+38h], xmm0
0x180388d72  mov     qword ptr [rbp+48h], 0
0x180388d7a  mov     qword ptr [rbp+50h], 0
0x180388d82  mov     r8d, 1Eh
0x180388d88  lea     rdx, aERdpnanoTransp; "E_RDPNANO_TRANSPORT_READ_HANG:"
0x180388d8f  lea     rcx, [rbp+38h]
0x180388d93  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180388d98  nop
0x180388d99  mov     r9, rbx
0x180388d9c  lea     r8, [rbp+38h]
0x180388da0  mov     dl, [rbp+30h]
0x180388da3  lea     rcx, [rbp+0F8h]
0x180388daa  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x180388daf  lea     rax, [rbp+0F8h]
0x180388db6  mov     rbx, [rbp+230h]
0x180388dbd  cmp     rbx, rax
0x180388dc0  jz      short loc_180388DFC
0x180388dc2  mov     rcx, rbx
0x180388dc5  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180388dca  movups  xmm0, xmmword ptr [rbp+0F8h]
0x180388dd1  movups  xmmword ptr [rbx], xmm0
0x180388dd4  movups  xmm1, xmmword ptr [rbp+108h]
0x180388ddb  movups  xmmword ptr [rbx+10h], xmm1
0x180388ddf  mov     qword ptr [rbp+108h], 0
0x180388dea  mov     qword ptr [rbp+110h], 0Fh
0x180388df5  mov     byte ptr [rbp+0F8h], 0
0x180388dfc  lea     rcx, [rbp+0F8h]
0x180388e03  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180388e08  nop
0x180388e09  lea     rcx, [rbp+38h]
0x180388e0d  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180388e12  nop
0x180388e13  jmp     loc_18038910F
0x180388e18  mov     dword ptr [rbp+240h], 8BB80492h
0x180388e22  call    ?CreateDescription@Exception@Basix@Microsoft@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBVexception@5@@Z; Microsoft::Basix::Exception::CreateDescription(std::exception const &)
0x180388e27  mov     rbx, rax
0x180388e2a  xorps   xmm0, xmm0
0x180388e2d  movups  xmmword ptr [rbp+38h], xmm0
0x180388e31  mov     qword ptr [rbp+48h], 0
0x180388e39  mov     qword ptr [rbp+50h], 0
0x180388e41  mov     r8d, 32h ; '2'
0x180388e47  lea     rdx, aERdpnanoDctDum; "E_RDPNANO_DCT_DUMMY_PACKET_WRITE_2_WINS"...
0x180388e4e  lea     rcx, [rbp+38h]
0x180388e52  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180388e57  nop
0x180388e58  mov     r9, rbx
0x180388e5b  lea     r8, [rbp+38h]
0x180388e5f  mov     dl, [rbp+30h]
0x180388e62  lea     rcx, [rbp+118h]
0x180388e69  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x180388e6e  lea     rax, [rbp+118h]
0x180388e75  mov     rbx, [rbp+230h]
0x180388e7c  cmp     rbx, rax
0x180388e7f  jz      short loc_180388EBB
0x180388e81  mov     rcx, rbx
0x180388e84  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180388e89  movups  xmm0, xmmword ptr [rbp+118h]
0x180388e90  movups  xmmword ptr [rbx], xmm0
0x180388e93  movups  xmm1, xmmword ptr [rbp+128h]
0x180388e9a  movups  xmmword ptr [rbx+10h], xmm1
0x180388e9e  mov     qword ptr [rbp+128h], 0
0x180388ea9  mov     qword ptr [rbp+130h], 0Fh
0x180388eb4  mov     byte ptr [rbp+118h], 0
0x180388ebb  lea     rcx, [rbp+118h]
0x180388ec2  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180388ec7  nop
0x180388ec8  lea     rcx, [rbp+38h]
0x180388ecc  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180388ed1  nop
0x180388ed2  jmp     loc_18038910F
0x180388ed7  mov     dword ptr [rbp+240h], 8BB803E4h
0x180388ee1  call    ?CreateDescription@Exception@Basix@Microsoft@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBVexception@5@@Z; Microsoft::Basix::Exception::CreateDescription(std::exception const &)
0x180388ee6  mov     rbx, rax
0x180388ee9  xorps   xmm0, xmm0
0x180388eec  movups  xmmword ptr [rbp+38h], xmm0
0x180388ef0  mov     qword ptr [rbp+48h], 0
0x180388ef8  mov     qword ptr [rbp+50h], 0
0x180388f00  mov     r8d, 26h ; '&'
0x180388f06  lea     rdx, aERdpnanoDctPac_0; "E_RDPNANO_DCT_PACKET_WRITE_INCOMPLETE:"
0x180388f0d  lea     rcx, [rbp+38h]
0x180388f11  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180388f16  nop
0x180388f17  mov     r9, rbx
0x180388f1a  lea     r8, [rbp+38h]
0x180388f1e  mov     dl, [rbp+30h]
0x180388f21  lea     rcx, [rbp+138h]
0x180388f28  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x180388f2d  lea     rax, [rbp+138h]
0x180388f34  mov     rbx, [rbp+230h]
0x180388f3b  cmp     rbx, rax
0x180388f3e  jz      short loc_180388F7A
0x180388f40  mov     rcx, rbx
0x180388f43  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180388f48  movups  xmm0, xmmword ptr [rbp+138h]
0x180388f4f  movups  xmmword ptr [rbx], xmm0
0x180388f52  movups  xmm1, xmmword ptr [rbp+148h]
0x180388f59  movups  xmmword ptr [rbx+10h], xmm1
0x180388f5d  mov     qword ptr [rbp+148h], 0
0x180388f68  mov     qword ptr [rbp+150h], 0Fh
  ... truncated ...
```
