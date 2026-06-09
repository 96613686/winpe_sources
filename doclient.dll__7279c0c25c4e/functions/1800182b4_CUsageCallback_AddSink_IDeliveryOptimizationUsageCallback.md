# CUsageCallback::AddSink(IDeliveryOptimizationUsageCallback *)

- ea: `0x1800182b4`
- end: `0x1800184dc`
- name: `?AddSink@CUsageCallback@@QEAAJPEAUIDeliveryOptimizationUsageCallback@@@Z`
- size: `552`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, IUnknown *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800169f0`

## callees

- `0x18000933c`
- `0x18000cea4`
- `0x1800182b4`
- `0x180018960`
- `0x18007e3cc`
- `0x180097c98`
- `0x1800f82f0`
- `0x180108e50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018397`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018415`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001847d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001848e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018397`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018415`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001847d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001848e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800182f4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800183f6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001842b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001845e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800182f4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800183f6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001842b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001845e`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001838d`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180018484`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001838d`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180018484`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18001831b`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18001831b`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180018364`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180018364`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x180018474`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x180018474`

## string_xrefs

- `0x1800184c9`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x18001837b`: `C:\__w\1\s\src\DeliveryOptimization\dll\UsageCallback.cpp`

## pseudocode

```c
__int64 __fastcall CUsageCallback::AddSink(RTL_SRWLOCK *this, IUnknown *a2)
{
  RTL_SRWLOCK *v4; // r14
  struct IDeliveryOptimizationUsageCallback **Ptr; // rax
  HRESULT v6; // eax
  HRESULT v7; // eax
  unsigned int v8; // esi
  const char *v9; // r9
  __int64 result; // rax
  _QWORD *v11; // rdx
  char *v12; // rsi
  volatile __int32 *v13; // rdi
  bool v14; // zf
  void *v15; // rcx
  DWORD dwAuthnLevel; // [rsp+20h] [rbp-68h]
  DWORD dwAuthnLevela; // [rsp+20h] [rbp-68h]
  IUnknown *v18; // [rsp+58h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v18 = a2;
  v4 = this + 6;
  AcquireSRWLockExclusive(this + 6);
  Ptr = (struct IDeliveryOptimizationUsageCallback **)this[3].Ptr;
  try
  {
    while ( Ptr != this[4].Ptr )
    {
      if ( *Ptr == (struct IDeliveryOptimizationUsageCallback *)a2 )
        goto LABEL_24;
      ++Ptr;
    }
    v6 = CoImpersonateClient();
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1262,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
        (const char *)(unsigned int)v6,
        dwAuthnLevel);
    v7 = CoSetProxyBlanket(a2, 0xFFFFFFFF, 0, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x20u);
    v8 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1D,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\UsageCallback.cpp",
        (const char *)(unsigned int)v7,
        dwAuthnLevela);
      CoRevertToSelf();
      ReleaseSRWLockExclusive(v4);
      return v8;
    }
    v11 = this[4].Ptr;
    if ( v11 == this[5].Ptr )
    {
      std::vector<Microsoft::WRL::ComPtr<IDeliveryOptimizationUsageCallback>>::_Emplace_reallocate<IDeliveryOptimizationUsageCallback * &>(
        &this[3],
        v11,
        &v18);
    }
    else
    {
      *v11 = a2;
      if ( a2 )
        ((void (__fastcall *)(IUnknown *))a2->lpVtbl->AddRef)(a2);
      this[4].Ptr = (char *)this[4].Ptr + 8;
    }
    if ( (PVOID)((char *)this[4].Ptr - (char *)this[3].Ptr) != (PVOID)8 )
      goto LABEL_23;
    v12 = (char *)this[1].Ptr;
    AcquireSRWLockExclusive((PSRWLOCK)v12 + 2);
    ++*((_DWORD *)v12 + 7);
    v13 = (volatile __int32 *)(v12 + 24);
    if ( *((_DWORD *)v12 + 7) == 1 )
      _InterlockedExchange(v13, 0);
    v18 = (IUnknown *)(v12 + 16);
    ReleaseSRWLockExclusive((PSRWLOCK)v12 + 2);
    if ( (int)CDeliveryOptimizationManager::WaitForInitAndCheckShutdown((CDeliveryOptimizationManager *)v12) >= 0 )
    {
      CCoreUsageNotifier::_SchedNotifyUsageStats(*(CCoreUsageNotifier **)(*((_QWORD *)v12 + 22) + 296LL), 0x1388u);
      AcquireSRWLockExclusive((PSRWLOCK)v12 + 2);
      v14 = (*((_DWORD *)v12 + 7))-- == 1;
      if ( v14 )
      {
        v15 = v12 + 24;
        *((_DWORD *)v12 + 6) = 1;
        goto LABEL_21;
      }
    }
    else
    {
      AcquireSRWLockExclusive((PSRWLOCK)v12 + 2);
      v14 = (*((_DWORD *)v12 + 7))-- == 1;
      if ( v14 )
      {
        *v13 = 1;
        v15 = v12 + 24;
LABEL_21:
        WakeByAddressAll(v15);
      }
    }
    ReleaseSRWLockExclusive((PSRWLOCK)v12 + 2);
LABEL_23:
    CoRevertToSelf();
LABEL_24:
    ReleaseSRWLockExclusive(v4);
    result = 0;
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x26,
                           (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\UsageCallback.cpp",
                           v9);
  }
  return result;
}

```

## disassembly

```asm
0x1800182b4  mov     r11, rsp
0x1800182b7  mov     [r11+18h], rbx
0x1800182bb  mov     [r11+20h], rsi
0x1800182bf  push    rdi
0x1800182c0  push    r14
0x1800182c2  push    r15
0x1800182c4  sub     rsp, 70h
0x1800182c8  mov     rax, cs:__security_cookie
0x1800182cf  xor     rax, rsp
0x1800182d2  mov     [rsp+88h+var_28], rax
0x1800182d7  mov     rdi, rdx
0x1800182da  mov     r15, rcx
0x1800182dd  mov     [r11-30h], rdx
0x1800182e1  xorps   xmm0, xmm0
0x1800182e4  movups  [rsp+88h+var_40], xmm0
0x1800182e9  lea     r14, [rcx+30h]
0x1800182ed  mov     [r11-40h], r14
0x1800182f1  mov     rcx, r14; SRWLock
0x1800182f4  call    cs:__imp_AcquireSRWLockExclusive
0x1800182fa  mov     byte ptr [rsp+88h+var_40+8], 1
0x1800182ff  lea     rbx, [r15+18h]
0x180018303  mov     rax, [rbx]
0x180018306  jmp     short loc_180018315
0x180018308  cmp     [rax], rdi
0x18001830b  jz      loc_18001848B
0x180018311  add     rax, 8
0x180018315  cmp     rax, [r15+20h]
0x180018319  jnz     short loc_180018308
0x18001831b  call    cs:__imp_CoImpersonateClient
0x180018321  mov     rcx, [rsp+88h]; this
0x180018329  test    eax, eax
0x18001832b  js      loc_1800184C6
0x180018331  mov     [rsp+88h+var_44], 1
0x180018336  mov     [rsp+88h+dwCapabilities], 20h ; ' '; dwCapabilities
0x18001833e  mov     [rsp+88h+pAuthInfo], 0; pAuthInfo
0x180018347  mov     [rsp+88h+dwImpLevel], 3; dwImpLevel
0x18001834f  mov     [rsp+88h+dwAuthnLevel], 0; int
0x180018357  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18001835b  xor     r8d, r8d; dwAuthzSvc
0x18001835e  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x180018361  mov     rcx, rdi; pProxy
0x180018364  call    cs:__imp_CoSetProxyBlanket
0x18001836a  mov     esi, eax
0x18001836c  test    eax, eax
0x18001836e  jns     short loc_1800183A4
0x180018370  mov     rcx, [rsp+88h]; this
0x180018378  mov     r9d, eax; char *
0x18001837b  lea     r8, aCW1SSrcDeliver_62; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x180018382  mov     edx, 1Dh; void *
0x180018387  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001838c  nop
0x18001838d  call    cs:__imp_CoRevertToSelf
0x180018393  nop
0x180018394  mov     rcx, r14; SRWLock
0x180018397  call    cs:__imp_ReleaseSRWLockExclusive
0x18001839d  mov     eax, esi
0x18001839f  jmp     loc_1800184A3
0x1800183a4  mov     rdx, [rbx+8]
0x1800183a8  cmp     rdx, [rbx+10h]
0x1800183ac  jz      short loc_1800183CD
0x1800183ae  mov     [rdx], rdi
0x1800183b1  test    rdi, rdi
0x1800183b4  jz      short loc_1800183C6
0x1800183b6  mov     rax, [rdi]
0x1800183b9  mov     rcx, rdi
0x1800183bc  mov     rax, [rax+8]
0x1800183c0  call    _guard_dispatch_icall
0x1800183c5  nop
0x1800183c6  add     qword ptr [rbx+8], 8
0x1800183cb  jmp     short loc_1800183DA
0x1800183cd  lea     r8, [rsp+88h+var_30]
0x1800183d2  mov     rcx, rbx
0x1800183d5  call    ??$_Emplace_reallocate@AEAPEAUIDeliveryOptimizationUsageCallback@@@?$vector@V?$ComPtr@UIDeliveryOptimizationUsageCallback@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIDeliveryOptimizationUsageCallback@@@WRL@Microsoft@@@std@@@std@@AEAAPEAV?$ComPtr@UIDeliveryOptimizationUsageCallback@@@WRL@Microsoft@@QEAV234@AEAPEAUIDeliveryOptimizationUsageCallback@@@Z; std::vector<Microsoft::WRL::ComPtr<IDeliveryOptimizationUsageCallback>>::_Emplace_reallocate<IDeliveryOptimizationUsageCallback * &>(Microsoft::WRL::ComPtr<IDeliveryOptimizationUsageCallback> * const,IDeliveryOptimizationUsageCallback * &)
0x1800183da  mov     rax, [rbx+8]
0x1800183de  sub     rax, [rbx]
0x1800183e1  cmp     rax, 8
0x1800183e5  jnz     loc_180018484
0x1800183eb  mov     rsi, [r15+8]
0x1800183ef  lea     rbx, [rsi+10h]
0x1800183f3  mov     rcx, rbx; SRWLock
0x1800183f6  call    cs:__imp_AcquireSRWLockExclusive
0x1800183fc  inc     dword ptr [rbx+0Ch]
0x1800183ff  lea     rdi, [rbx+8]
0x180018403  cmp     dword ptr [rbx+0Ch], 1
0x180018407  jnz     short loc_18001840D
0x180018409  xor     eax, eax
0x18001840b  xchg    eax, [rdi]
0x18001840d  mov     [rsp+88h+var_30], rbx
0x180018412  mov     rcx, rbx; SRWLock
0x180018415  call    cs:__imp_ReleaseSRWLockExclusive
0x18001841b  nop
0x18001841c  mov     rcx, rsi; this
0x18001841f  call    ?WaitForInitAndCheckShutdown@CDeliveryOptimizationManager@@QEBAJXZ; CDeliveryOptimizationManager::WaitForInitAndCheckShutdown(void)
0x180018424  test    eax, eax
0x180018426  jns     short loc_180018442
0x180018428  mov     rcx, rbx; SRWLock
0x18001842b  call    cs:__imp_AcquireSRWLockExclusive
0x180018431  add     dword ptr [rbx+0Ch], 0FFFFFFFFh
0x180018435  jnz     short loc_18001847A
0x180018437  mov     dword ptr [rdi], 1
0x18001843d  mov     rcx, rdi
0x180018440  jmp     short loc_180018474
0x180018442  mov     rcx, [rsi+0B0h]
0x180018449  mov     edx, 1388h; unsigned int
0x18001844e  mov     rcx, [rcx+128h]; this
0x180018455  call    ?_SchedNotifyUsageStats@CCoreUsageNotifier@@AEAAXI@Z; CCoreUsageNotifier::_SchedNotifyUsageStats(uint)
0x18001845a  nop
0x18001845b  mov     rcx, rbx; SRWLock
0x18001845e  call    cs:__imp_AcquireSRWLockExclusive
0x180018464  add     dword ptr [rbx+0Ch], 0FFFFFFFFh
0x180018468  jnz     short loc_18001847A
0x18001846a  lea     rcx, [rbx+8]; Address
0x18001846e  mov     dword ptr [rcx], 1
0x180018474  call    cs:__imp_WakeByAddressAll
0x18001847a  mov     rcx, rbx; SRWLock
0x18001847d  call    cs:__imp_ReleaseSRWLockExclusive
0x180018483  nop
0x180018484  call    cs:__imp_CoRevertToSelf
0x18001848a  nop
0x18001848b  mov     rcx, r14; SRWLock
0x18001848e  call    cs:__imp_ReleaseSRWLockExclusive
0x180018494  xor     eax, eax
0x180018496  jmp     short loc_1800184A3
0x180018498  mov     eax, 8007000Eh
0x18001849d  jmp     short loc_1800184A3
0x18001849f  mov     eax, [rsp+88h+var_48]
0x1800184a3  mov     rcx, [rsp+88h+var_28]
0x1800184a8  xor     rcx, rsp; StackCookie
0x1800184ab  call    __security_check_cookie
0x1800184b0  lea     r11, [rsp+88h+var_18]
0x1800184b5  mov     rbx, [r11+30h]
0x1800184b9  mov     rsi, [r11+38h]
0x1800184bd  mov     rsp, r11
0x1800184c0  pop     r15
0x1800184c2  pop     r14
0x1800184c4  pop     rdi
0x1800184c5  retn
0x1800184c6  mov     r9d, eax; char *
0x1800184c9  lea     r8, aCW1SPackagesMi_3; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x1800184d0  mov     edx, 1262h; void *
0x1800184d5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
