# Hns::Client::RpcHelper::GetRpcClient(void)

- ea: `0x18000b8c4`
- end: `0x18000ba7e`
- name: `?GetRpcClient@RpcHelper@Client@Hns@@YA?AV?$shared_ptr@VRpcClient@Rpc@@@std@@XZ`
- size: `442`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `13`
- callee_count: `6`
- tags: ``

## callers

- `0x1800020dc`
- `0x180002188`
- `0x180002254`
- `0x180002314`
- `0x180002978`
- `0x180002ad4`
- `0x180002c38`
- `0x180002f88`
- `0x180007d00`
- `0x180008560`
- `0x180009290`
- `0x180009730`
- `0x18000a608`

## callees

- `0x180001600`
- `0x180001a0c`
- `0x18000b560`
- `0x18000b7f0`
- `0x18000b8c4`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b974`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b974`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ba4a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ba4a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b93c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b94a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b93c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b94a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000b8f5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000b8f5`

## pseudocode

```c
_QWORD *__fastcall Hns::Client::RpcHelper::GetRpcClient(_QWORD *a1)
{
  __int64 v2; // rax
  volatile signed __int32 *v3; // rdi
  unsigned int v5; // [rsp+40h] [rbp-38h]
  __int128 v6; // [rsp+48h] [rbp-30h] BYREF
  __int64 v7; // [rsp+58h] [rbp-20h]
  __int64 v8; // [rsp+60h] [rbp-18h]

  AcquireSRWLockShared(&Hns::Client::RpcHelper::g_RpcClientLock);
  if ( Hns::Client::RpcHelper::g_RpcClient )
  {
    *a1 = 0;
    a1[1] = 0;
    if ( qword_180018508 )
      _InterlockedIncrement((volatile signed __int32 *)(qword_180018508 + 8));
    *a1 = Hns::Client::RpcHelper::g_RpcClient;
    a1[1] = qword_180018508;
    ReleaseSRWLockShared(&Hns::Client::RpcHelper::g_RpcClientLock);
  }
  else
  {
    ReleaseSRWLockShared(&Hns::Client::RpcHelper::g_RpcClientLock);
    v6 = 0;
    v7 = 0;
    v8 = 7;
    LOWORD(v6) = 0;
    AcquireSRWLockExclusive(&Hns::Client::RpcHelper::g_RpcClientLock);
    v5 = (unsigned int)operator new(0xB0u);
    v2 = std::_Ref_count_obj2<Rpc::RpcClient>::_Ref_count_obj2<Rpc::RpcClient>(
           v5,
           (unsigned int)&HnsRpc_v1_0_c_ifspec,
           (unsigned int)&v6,
           (unsigned int)&v6,
           (__int64)&Rpc::c_LRpcEndpoint,
           (__int64)&v6);
    Hns::Client::RpcHelper::g_RpcClient = v2 + 16;
    v3 = (volatile signed __int32 *)qword_180018508;
    qword_180018508 = v2;
    if ( v3 )
    {
      if ( _InterlockedExchangeAdd(v3 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v3)(v3);
        if ( _InterlockedExchangeAdd(v3 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v3 + 8LL))(v3);
      }
    }
    *a1 = 0;
    a1[1] = 0;
    if ( qword_180018508 )
      _InterlockedIncrement((volatile signed __int32 *)(qword_180018508 + 8));
    *a1 = Hns::Client::RpcHelper::g_RpcClient;
    a1[1] = qword_180018508;
    ReleaseSRWLockExclusive(&Hns::Client::RpcHelper::g_RpcClientLock);
    std::wstring::~wstring(&v6);
  }
  return a1;
}

```

## disassembly

```asm
0x18000b8c4  mov     [rsp+arg_8], rbx
0x18000b8c9  mov     [rsp+arg_10], rdi
0x18000b8ce  push    r14
0x18000b8d0  sub     rsp, 70h
0x18000b8d4  mov     rax, cs:__security_cookie
0x18000b8db  xor     rax, rsp
0x18000b8de  mov     [rsp+78h+var_10], rax
0x18000b8e3  mov     rbx, rcx
0x18000b8e6  mov     [rsp+78h+var_40], rcx
0x18000b8eb  lea     r14, ?g_RpcClientLock@RpcHelper@Client@Hns@@3Vsrwlock@wil@@A; wil::srwlock Hns::Client::RpcHelper::g_RpcClientLock
0x18000b8f2  mov     rcx, r14; SRWLock
0x18000b8f5  call    cs:__imp_AcquireSRWLockShared
0x18000b8fb  cmp     cs:?g_RpcClient@RpcHelper@Client@Hns@@3V?$shared_ptr@VRpcClient@Rpc@@@std@@A, 0; std::shared_ptr<Rpc::RpcClient> Hns::Client::RpcHelper::g_RpcClient
0x18000b903  jz      short loc_18000B947
0x18000b905  mov     qword ptr [rbx], 0
0x18000b90c  mov     qword ptr [rbx+8], 0
0x18000b914  mov     rax, cs:qword_180018508
0x18000b91b  test    rax, rax
0x18000b91e  jz      short loc_18000B924
0x18000b920  lock inc dword ptr [rax+8]
0x18000b924  mov     rdx, cs:?g_RpcClient@RpcHelper@Client@Hns@@3V?$shared_ptr@VRpcClient@Rpc@@@std@@A; std::shared_ptr<Rpc::RpcClient> Hns::Client::RpcHelper::g_RpcClient
0x18000b92b  mov     [rbx], rdx
0x18000b92e  mov     rdx, cs:qword_180018508
0x18000b935  mov     [rbx+8], rdx
0x18000b939  mov     rcx, r14; SRWLock
0x18000b93c  call    cs:__imp_ReleaseSRWLockShared
0x18000b942  jmp     loc_18000BA5B
0x18000b947  mov     rcx, r14; SRWLock
0x18000b94a  call    cs:__imp_ReleaseSRWLockShared
0x18000b950  xorps   xmm0, xmm0
0x18000b953  movups  [rsp+78h+var_30], xmm0
0x18000b958  mov     [rsp+78h+var_20], 0
0x18000b961  mov     [rsp+78h+var_18], 7
0x18000b96a  xor     eax, eax
0x18000b96c  mov     word ptr [rsp+78h+var_30], ax
0x18000b971  mov     rcx, r14; SRWLock
0x18000b974  call    cs:__imp_AcquireSRWLockExclusive
0x18000b97a  mov     [rsp+78h+var_40], r14
0x18000b97f  mov     ecx, 0B0h; Size
0x18000b984  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b989  mov     [rsp+78h+var_38], rax
0x18000b98e  lea     rcx, [rsp+78h+var_30]
0x18000b993  mov     [rsp+78h+var_50], rcx
0x18000b998  lea     rcx, ?c_LRpcEndpoint@Rpc@@3QEBGEB; ushort const * const Rpc::c_LRpcEndpoint
0x18000b99f  mov     [rsp+78h+var_58], rcx
0x18000b9a4  lea     r9, [rsp+78h+var_30]
0x18000b9a9  lea     r8, [rsp+78h+var_30]
0x18000b9ae  lea     rdx, HnsRpc_v1_0_c_ifspec
0x18000b9b5  mov     rcx, rax
0x18000b9b8  call    ??$?0AEAPEAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV01@AEBQEBGAEAV01@@?$_Ref_count_obj2@VRpcClient@Rpc@@@std@@QEAA@AEAPEAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@1AEBQEBG1@Z; std::_Ref_count_obj2<Rpc::RpcClient>::_Ref_count_obj2<Rpc::RpcClient>(void * &,std::wstring &,std::wstring &,ushort const * const &,std::wstring &)
0x18000b9bd  nop
0x18000b9be  lea     rcx, [rax+10h]
0x18000b9c2  mov     cs:?g_RpcClient@RpcHelper@Client@Hns@@3V?$shared_ptr@VRpcClient@Rpc@@@std@@A, rcx; std::shared_ptr<Rpc::RpcClient> Hns::Client::RpcHelper::g_RpcClient
0x18000b9c9  mov     rdi, cs:qword_180018508
0x18000b9d0  mov     cs:qword_180018508, rax
0x18000b9d7  test    rdi, rdi
0x18000b9da  jz      short loc_18000BA13
0x18000b9dc  or      eax, 0FFFFFFFFh
0x18000b9df  lock xadd [rdi+8], eax
0x18000b9e4  cmp     eax, 1
0x18000b9e7  jnz     short loc_18000BA13
0x18000b9e9  mov     rax, [rdi]
0x18000b9ec  mov     rcx, rdi
0x18000b9ef  mov     rax, [rax]
0x18000b9f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9f7  or      eax, 0FFFFFFFFh
0x18000b9fa  lock xadd [rdi+0Ch], eax
0x18000b9ff  cmp     eax, 1
0x18000ba02  jnz     short loc_18000BA13
0x18000ba04  mov     rax, [rdi]
0x18000ba07  mov     rcx, rdi
0x18000ba0a  mov     rax, [rax+8]
0x18000ba0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba13  mov     qword ptr [rbx], 0
0x18000ba1a  mov     qword ptr [rbx+8], 0
0x18000ba22  mov     rax, cs:qword_180018508
0x18000ba29  test    rax, rax
0x18000ba2c  jz      short loc_18000BA32
0x18000ba2e  lock inc dword ptr [rax+8]
0x18000ba32  mov     rax, cs:?g_RpcClient@RpcHelper@Client@Hns@@3V?$shared_ptr@VRpcClient@Rpc@@@std@@A; std::shared_ptr<Rpc::RpcClient> Hns::Client::RpcHelper::g_RpcClient
0x18000ba39  mov     [rbx], rax
0x18000ba3c  mov     rax, cs:qword_180018508
0x18000ba43  mov     [rbx+8], rax
0x18000ba47  mov     rcx, r14; SRWLock
0x18000ba4a  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ba50  nop
0x18000ba51  lea     rcx, [rsp+78h+var_30]
0x18000ba56  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000ba5b  mov     rax, rbx
0x18000ba5e  mov     rcx, [rsp+78h+var_10]
0x18000ba63  xor     rcx, rsp; StackCookie
0x18000ba66  call    __security_check_cookie
0x18000ba6b  lea     r11, [rsp+78h+var_8]
0x18000ba70  mov     rbx, [r11+18h]
0x18000ba74  mov     rdi, [r11+20h]
0x18000ba78  mov     rsp, r11
0x18000ba7b  pop     r14
0x18000ba7d  retn
```
