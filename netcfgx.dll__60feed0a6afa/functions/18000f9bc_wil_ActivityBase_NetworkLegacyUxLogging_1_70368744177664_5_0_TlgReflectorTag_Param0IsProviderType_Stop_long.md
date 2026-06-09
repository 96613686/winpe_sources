# wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x18000f9bc`
- end: `0x18000fb8a`
- name: `?Stop@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `462`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000da34`

## callees

- `0x1800018dc`
- `0x180001f90`
- `0x180002a40`
- `0x18000df94`
- `0x18000e970`
- `0x18000f9bc`
- `0x180010210`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000fa1b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000fa1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fa72`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fafe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fa72`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fafe`

## string_xrefs

- `0x18000fb19`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        __int64 a1,
        int a2)
{
  __int64 v4; // rax
  int v5; // edi
  int v6; // edi
  __int64 result; // rax
  __int64 v8; // rdi
  __int64 v9; // rbx
  __int64 *v10; // rcx
  const struct wil::FailureInfo *v11; // rdx
  DWORD CurrentThreadId; // [rsp+30h] [rbp-D0h] BYREF
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v14; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v15[32]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 *v16; // [rsp+70h] [rbp-90h]
  __int64 v17; // [rsp+78h] [rbp-88h]
  PSRWLOCK *p_SRWLock; // [rsp+80h] [rbp-80h]
  __int64 v19; // [rsp+88h] [rbp-78h]
  DWORD *p_CurrentThreadId; // [rsp+90h] [rbp-70h]
  __int64 v21; // [rsp+98h] [rbp-68h]
  void *retaddr; // [rsp+128h] [rbp+28h]

  wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v4 = *(_QWORD *)(a1 + 272);
  v5 = *(_DWORD *)(v4 + 248);
  if ( v5 < 1 )
  {
    memset_0(v15, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v15, v11);
  }
  if ( *(int *)(v4 + 72) >= 0 )
    *(_DWORD *)(v4 + 72) = a2;
  v6 = v5 - 1;
  *(_DWORD *)(v4 + 248) = v6;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v6 )
  {
    result = (__int64)NetworkLegacyUxLogging::Provider();
    v8 = result;
    if ( *(_DWORD *)result > 5u )
    {
      result = *(_QWORD *)(result + 24);
      if ( (*(_QWORD *)(v8 + 16) & 0x400000000000LL) != 0 && (result & 0x400000000000LL) == result )
      {
        CurrentThreadId = GetCurrentThreadId();
        LODWORD(SRWLock) = a2;
        v14 = 0x1000000;
        p_CurrentThreadId = &CurrentThreadId;
        v21 = 4;
        p_SRWLock = &SRWLock;
        v19 = 4;
        v16 = &v14;
        v17 = 8;
        result = tlgWriteTransfer_EventWriteTransfer(v8, byte_180015EC5, *(_QWORD *)(a1 + 272) + 8LL, 0, 5, v15);
      }
    }
  }
  else
  {
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  }
  if ( *(_DWORD *)(a1 + 312) )
  {
    v9 = a1 + 288;
    if ( *(_DWORD *)(v9 + 24) != GetCurrentThreadId() )
    {
      if ( wil::details::g_pfnReportFatalUsageError )
        wil::details::g_pfnReportFatalUsageError(
          "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
          retaddr);
    }
    *(_DWORD *)(v9 + 24) = 0;
    v10 = *(__int64 **)v9;
    while ( 1 )
    {
      result = *v10;
      if ( !*v10 )
        break;
      if ( result == v9 )
      {
        result = *(_QWORD *)(v9 + 16);
        *v10 = result;
        break;
      }
      v10 = (__int64 *)(result + 16);
      *(_QWORD *)v9 = result + 16;
    }
    *(_QWORD *)v9 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000f9bc  push    rbp
0x18000f9be  push    rbx
0x18000f9bf  push    rsi
0x18000f9c0  push    rdi
0x18000f9c1  lea     rbp, [rsp-8]
0x18000f9c6  sub     rsp, 108h
0x18000f9cd  mov     rax, cs:__security_cookie
0x18000f9d4  xor     rax, rsp
0x18000f9d7  mov     [rbp+20h+var_30], rax
0x18000f9db  mov     esi, edx
0x18000f9dd  mov     rbx, rcx
0x18000f9e0  lea     rdx, [rsp+120h+SRWLock]
0x18000f9e5  call    ?LockExclusive@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000f9ea  mov     rax, [rbx+110h]
0x18000f9f1  mov     edi, [rax+0F8h]
0x18000f9f7  cmp     edi, 1
0x18000f9fa  jl      loc_18000FB6D
0x18000fa00  cmp     dword ptr [rax+48h], 0
0x18000fa04  jl      short loc_18000FA09
0x18000fa06  mov     [rax+48h], esi
0x18000fa09  dec     edi
0x18000fa0b  mov     [rax+0F8h], edi
0x18000fa11  mov     rcx, [rsp+120h+SRWLock]; SRWLock
0x18000fa16  test    rcx, rcx
0x18000fa19  jz      short loc_18000FA21
0x18000fa1b  call    cs:__imp_ReleaseSRWLockExclusive
0x18000fa21  test    edi, edi
0x18000fa23  jnz     short loc_18000FA39
0x18000fa25  mov     rax, [rbx]
0x18000fa28  mov     rcx, rbx
0x18000fa2b  mov     rax, [rax+8]
0x18000fa2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa34  jmp     loc_18000FAEE
0x18000fa39  call    ?Provider@NetworkLegacyUxLogging@@SAPEBU_tlgProvider_t@@XZ; NetworkLegacyUxLogging::Provider(void)
0x18000fa3e  mov     rdi, rax
0x18000fa41  mov     ecx, [rax]
0x18000fa43  cmp     ecx, 5
0x18000fa46  jbe     loc_18000FAEE
0x18000fa4c  mov     rax, [rax+18h]
0x18000fa50  mov     rcx, [rdi+10h]
0x18000fa54  mov     rdx, 400000000000h
0x18000fa5e  test    rdx, rcx
0x18000fa61  jz      loc_18000FAEE
0x18000fa67  mov     rcx, rax
0x18000fa6a  and     rcx, rdx
0x18000fa6d  cmp     rcx, rax
0x18000fa70  jnz     short loc_18000FAEE
0x18000fa72  call    cs:__imp_GetCurrentThreadId
0x18000fa78  mov     [rsp+120h+var_F0], eax
0x18000fa7c  mov     dword ptr [rsp+120h+SRWLock], esi
0x18000fa80  mov     [rsp+120h+var_E0], 1000000h
0x18000fa89  lea     rax, [rsp+120h+var_F0]
0x18000fa8e  mov     [rbp+20h+var_90], rax
0x18000fa92  mov     [rbp+20h+var_88], 4
0x18000fa9a  lea     rax, [rsp+120h+SRWLock]
0x18000fa9f  mov     [rbp+20h+var_A0], rax
0x18000faa3  mov     [rbp+20h+var_98], 4
0x18000faab  lea     rax, [rsp+120h+var_E0]
0x18000fab0  mov     [rsp+120h+var_B0], rax
0x18000fab5  mov     [rsp+120h+var_A8], 8
0x18000fabe  mov     r8, [rbx+110h]
0x18000fac5  add     r8, 8
0x18000fac9  lea     rax, [rsp+120h+var_D0]
0x18000face  mov     [rsp+120h+var_F8], rax
0x18000fad3  mov     [rsp+120h+var_100], 5
0x18000fadb  xor     r9d, r9d
0x18000fade  lea     rdx, byte_180015EC5
0x18000fae5  mov     rcx, rdi
0x18000fae8  call    _tlgWriteTransfer_EventWriteTransfer
0x18000faed  nop
0x18000faee  cmp     dword ptr [rbx+138h], 0
0x18000faf5  jz      short loc_18000FB55
0x18000faf7  add     rbx, 120h
0x18000fafe  call    cs:__imp_GetCurrentThreadId
0x18000fb04  cmp     [rbx+18h], eax
0x18000fb07  jz      short loc_18000FB25
0x18000fb09  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18000fb10  test    rax, rax
0x18000fb13  jz      short loc_18000FB25
0x18000fb15  mov     rdx, [rbp+28h]
0x18000fb19  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18000fb20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb25  mov     dword ptr [rbx+18h], 0
0x18000fb2c  mov     rcx, [rbx]
0x18000fb2f  jmp     short loc_18000FB3D
0x18000fb31  cmp     rax, rbx
0x18000fb34  jz      short loc_18000FB47
0x18000fb36  lea     rcx, [rax+10h]
0x18000fb3a  mov     [rbx], rcx
0x18000fb3d  mov     rax, [rcx]
0x18000fb40  test    rax, rax
0x18000fb43  jnz     short loc_18000FB31
0x18000fb45  jmp     short loc_18000FB4E
0x18000fb47  mov     rax, [rbx+10h]
0x18000fb4b  mov     [rcx], rax
0x18000fb4e  mov     qword ptr [rbx], 0
0x18000fb55  mov     rcx, [rbp+20h+var_30]
0x18000fb59  xor     rcx, rsp; StackCookie
0x18000fb5c  call    __security_check_cookie
0x18000fb61  add     rsp, 108h
0x18000fb68  pop     rdi
0x18000fb69  pop     rsi
0x18000fb6a  pop     rbx
0x18000fb6b  pop     rbp
0x18000fb6c  retn
0x18000fb6d  xor     edx, edx; Val
0x18000fb6f  mov     r8d, 98h; Size
0x18000fb75  lea     rcx, [rsp+120h+var_D0]; void *
0x18000fb7a  call    memset_0
0x18000fb7f  lea     rcx, [rsp+120h+var_D0]; this
0x18000fb84  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
