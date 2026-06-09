# Microsoft::Basix::WinUtils::WinSockObj::~WinSockObj(void)

- ea: `0x18012ebd0`
- end: `0x18012ed1a`
- name: `??1WinSockObj@WinUtils@Basix@Microsoft@@QEAA@XZ`
- size: `330`
- prototype: `void __fastcall(Microsoft::Basix::WinUtils::WinSockObj *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180133260`

## callees

- `0x18000d9c0`
- `0x180015bb8`
- `0x18012b3e0`
- `0x18012b568`
- `0x18012ebd0`
- `0x1802ee5d4`
- `0x18032f050`
- `0x18032f0b0`
- `0x180375c40`

## import_xrefs

- `WS2_32!__imp_closesocket` at `0x18012ebfc`
- `WS2_32!__imp_closesocket` at `0x18012ebfc`
- `WS2_32!__imp_WSAGetLastError` at `0x18012ec0a`
- `WS2_32!__imp_WSAGetLastError` at `0x18012ec0a`
- `WS2_32!__imp_WSACleanup` at `0x18012ecf5`
- `WS2_32!__imp_WSACleanup` at `0x18012ecf5`

## pseudocode

```c
void __fastcall Microsoft::Basix::WinUtils::WinSockObj::~WinSockObj(Microsoft::Basix::WinUtils::WinSockObj *this)
{
  int Error; // ebx
  const char *v3; // r9
  volatile signed __int32 *v4; // rbx
  int v5; // [rsp+20h] [rbp-68h]
  const char *v6; // [rsp+28h] [rbp-60h]
  _OWORD v7[2]; // [rsp+40h] [rbp-48h] BYREF
  __int128 v8; // [rsp+60h] [rbp-28h] BYREF

  if ( closesocket(*((_QWORD *)this + 51)) )
  {
    Error = WSAGetLastError();
    v8 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCritical>(&v8);
    if ( (_QWORD)v8 && *(_BYTE *)(v8 + 128) )
    {
      memset(v7, 0, sizeof(v7));
      std::string::_Construct<1,char const *>(
        v7,
        "Error closing socket WSAGetLastError = (%d).\n    %s(%d): %s()",
        61,
        v3,
        v5,
        v6);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceCritical,int,char const *,int,char const *>(
        (unsigned int)&v8,
        (unsigned int)"BASIX",
        (unsigned int)v7,
        Error,
        (__int64)"C:\\__w\\1\\s\\src\\libbasix-network\\publicinc\\libbasix/winutils/winsockutils.h",
        107,
        (__int64)"Microsoft::Basix::WinUtils::WinSockObj::~WinSockObj");
      std::string::_Tidy_deallocate(v7);
    }
    v4 = (volatile signed __int32 *)*((_QWORD *)&v8 + 1);
    if ( *((_QWORD *)&v8 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v8 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v4)(v4);
        if ( _InterlockedExchangeAdd(v4 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
      }
    }
    Microsoft::Basix::Instrumentation::TraceManager::Abort();
  }
  *((_QWORD *)this + 51) = -1;
  WSACleanup();
}

```

## disassembly

```asm
0x18012ebd0  mov     [rsp+arg_8], rbx
0x18012ebd5  push    rdi
0x18012ebd6  mov     eax, 80h
0x18012ebdb  call    _alloca_probe
0x18012ebe0  sub     rsp, rax
0x18012ebe3  mov     rax, cs:__security_cookie
0x18012ebea  xor     rax, rsp
0x18012ebed  mov     [rsp+88h+var_18], rax
0x18012ebf2  mov     rdi, rcx
0x18012ebf5  mov     rcx, [rcx+198h]; s
0x18012ebfc  call    cs:__imp_closesocket
0x18012ec02  test    eax, eax
0x18012ec04  jz      loc_18012ECEA
0x18012ec0a  call    cs:__imp_WSAGetLastError
0x18012ec10  mov     ebx, eax
0x18012ec12  xorps   xmm0, xmm0
0x18012ec15  movups  [rsp+88h+var_28], xmm0
0x18012ec1a  lea     rcx, [rsp+88h+var_28]
0x18012ec1f  call    ??$SelectEvent@VTraceCritical@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceCritical@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCritical>(void)
0x18012ec24  mov     rcx, qword ptr [rsp+88h+var_28]
0x18012ec29  test    rcx, rcx
0x18012ec2c  jz      short loc_18012ECA2
0x18012ec2e  cmp     byte ptr [rcx+80h], 0
0x18012ec35  jz      short loc_18012ECA2
0x18012ec37  xorps   xmm0, xmm0
0x18012ec3a  movups  [rsp+88h+var_48], xmm0
0x18012ec3f  xorps   xmm1, xmm1
0x18012ec42  movdqu  [rsp+88h+var_38], xmm1
0x18012ec48  mov     r8d, 3Dh ; '='
0x18012ec4e  lea     rdx, aErrorClosingSo; "Error closing socket WSAGetLastError = "...
0x18012ec55  lea     rcx, [rsp+88h+var_48]
0x18012ec5a  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18012ec5f  lea     rax, aMicrosoftBasix_278; "Microsoft::Basix::WinUtils::WinSockObj:"...
0x18012ec66  mov     [rsp+88h+var_58], rax
0x18012ec6b  mov     dword ptr [rsp+88h+var_60], 6Bh ; 'k'
0x18012ec73  lea     rax, aCW1SSrcLibbasi_23; "C:\\__w\\1\\s\\src\\libbasix-network\\p"...
0x18012ec7a  mov     [rsp+88h+var_68], rax
0x18012ec7f  mov     r9d, ebx
0x18012ec82  lea     r8, [rsp+88h+var_48]
0x18012ec87  lea     rdx, aBasix; "BASIX"
0x18012ec8e  lea     rcx, [rsp+88h+var_28]
0x18012ec93  call    ??$TraceMessage@VTraceCritical@Basix@Microsoft@@HPEBDHPEBD@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceCritical@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@H1H1@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceCritical,int,char const *,int,char const *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCritical>> const &,char const *,std::string const &,int,char const *,int,char const *)
0x18012ec98  lea     rcx, [rsp+88h+var_48]
0x18012ec9d  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18012eca2  mov     rbx, qword ptr [rsp+88h+var_28+8]
0x18012eca7  test    rbx, rbx
0x18012ecaa  jz      short loc_18012ECE5
0x18012ecac  or      eax, 0FFFFFFFFh
0x18012ecaf  lock xadd [rbx+8], eax
0x18012ecb4  cmp     eax, 1
0x18012ecb7  jnz     short loc_18012ECE5
0x18012ecb9  mov     rax, [rbx]
0x18012ecbc  mov     rcx, rbx
0x18012ecbf  mov     rax, [rax]
0x18012ecc2  call    cs:__guard_dispatch_icall_fptr
0x18012ecc8  or      eax, 0FFFFFFFFh
0x18012eccb  lock xadd [rbx+0Ch], eax
0x18012ecd0  cmp     eax, 1
0x18012ecd3  jnz     short loc_18012ECE5
0x18012ecd5  mov     rax, [rbx]
0x18012ecd8  mov     rcx, rbx
0x18012ecdb  mov     rax, [rax+8]
0x18012ecdf  call    cs:__guard_dispatch_icall_fptr
0x18012ece5  call    ?Abort@TraceManager@Instrumentation@Basix@Microsoft@@SAXXZ; Microsoft::Basix::Instrumentation::TraceManager::Abort(void)
0x18012ecea  mov     qword ptr [rdi+198h], 0FFFFFFFFFFFFFFFFh
0x18012ecf5  call    cs:__imp_WSACleanup
0x18012ecfb  nop
0x18012ecfc  mov     rcx, [rsp+88h+var_18]
0x18012ed01  xor     rcx, rsp; StackCookie
0x18012ed04  call    __security_check_cookie
0x18012ed09  mov     rbx, [rsp+88h+arg_8]
0x18012ed11  add     rsp, 80h
0x18012ed18  pop     rdi
0x18012ed19  retn
```
