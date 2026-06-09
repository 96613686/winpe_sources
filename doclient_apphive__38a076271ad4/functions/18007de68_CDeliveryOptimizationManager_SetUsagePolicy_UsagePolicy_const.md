# CDeliveryOptimizationManager::SetUsagePolicy(UsagePolicy const &)

- ea: `0x18007de68`
- end: `0x18007dfea`
- name: `?SetUsagePolicy@CDeliveryOptimizationManager@@QEAAJAEBUUsagePolicy@@@Z`
- size: `386`
- prototype: `__int64 __fastcall(CDeliveryOptimizationManager *__hidden this, const struct UsagePolicy *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180016b70`

## callees

- `0x18000933c`
- `0x18000cea4`
- `0x18002b73c`
- `0x18007de68`
- `0x18007e3cc`
- `0x1800ac64c`
- `0x1800d82e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007dea9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007dee0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007df5a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007dfad`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007dea9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007dee0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007df5a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007dfad`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007de89`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007dec2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007df3b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007df8e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007de89`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007dec2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007df3b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007df8e`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18007df0e`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18007df0e`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18007deee`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18007deee`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18007ded7`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18007df51`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18007dfa4`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18007ded7`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18007df51`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18007dfa4`

## string_xrefs

- `0x18007dfd7`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDeliveryOptimizationManager::SetUsagePolicy(
        CDeliveryOptimizationManager *this,
        const struct UsagePolicy *a2)
{
  char *v4; // rbx
  volatile __int32 *v5; // rdi
  int v6; // r14d
  bool v7; // zf
  __int64 result; // rax
  HRESULT v9; // eax
  bool v10; // di
  const char *v11; // r9
  unsigned int v12; // edi
  int v13; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v4 = (char *)this + 16;
  AcquireSRWLockExclusive((PSRWLOCK)this + 2);
  ++*((_DWORD *)v4 + 3);
  v5 = (volatile __int32 *)(v4 + 8);
  if ( *((_DWORD *)v4 + 3) == 1 )
    _InterlockedExchange(v5, 0);
  ReleaseSRWLockExclusive((PSRWLOCK)v4);
  v6 = CDeliveryOptimizationManager::WaitForInitAndCheckShutdown(this);
  if ( v6 >= 0 )
  {
    v9 = CoImpersonateClient();
    try
    {
      if ( v9 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1262,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
          (const char *)(unsigned int)v9,
          v13);
      LOBYTE(v13) = 1;
      v10 = IsAdminToken(retaddr);
      CoRevertToSelf();
      if ( v10 )
      {
        v12 = CGlobalConfigManager::SetUsagePolicy(*((CGlobalConfigManager **)this + 7), a2);
        if ( v12 )
        {
          if ( v12 == 1 )
            v12 = 0;
        }
        else
        {
          CCore::OnUsagePolicyChange(*((CCore **)this + 22));
        }
        AcquireSRWLockExclusive((PSRWLOCK)v4);
        v7 = (*((_DWORD *)v4 + 3))-- == 1;
        if ( v7 )
        {
          *((_DWORD *)v4 + 2) = 1;
          WakeByAddressAll(v4 + 8);
        }
        ReleaseSRWLockExclusive((PSRWLOCK)v4);
        result = v12;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x13E,
          (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\DeliveryOptimizationMgr.cpp",
          (const char *)0x80070005LL,
          v13);
        AcquireSRWLockExclusive((PSRWLOCK)v4);
        v7 = (*((_DWORD *)v4 + 3))-- == 1;
        if ( v7 )
        {
          *((_DWORD *)v4 + 2) = 1;
          WakeByAddressAll(v4 + 8);
        }
        ReleaseSRWLockExclusive((PSRWLOCK)v4);
        result = 2147942405LL;
      }
    }
    catch ( std::bad_alloc )
    {
      return 2147942414LL;
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x14B,
                             (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\DeliveryOptimizationMgr.cpp",
                             v11);
    }
  }
  else
  {
    AcquireSRWLockExclusive((PSRWLOCK)v4);
    v7 = (*((_DWORD *)v4 + 3))-- == 1;
    if ( v7 )
    {
      *v5 = 1;
      WakeByAddressAll(v4 + 8);
    }
    ReleaseSRWLockExclusive((PSRWLOCK)v4);
    return (unsigned int)v6;
  }
  return result;
}

```

## disassembly

```asm
0x18007de68  mov     [rsp+arg_10], rbx
0x18007de6d  push    rsi
0x18007de6e  push    rdi
0x18007de6f  push    r12
0x18007de71  push    r14
0x18007de73  push    r15
0x18007de75  sub     rsp, 30h
0x18007de79  mov     r15, rdx
0x18007de7c  mov     rsi, rcx
0x18007de7f  xor     r12d, r12d
0x18007de82  lea     rbx, [rcx+10h]
0x18007de86  mov     rcx, rbx; SRWLock
0x18007de89  call    cs:__imp_AcquireSRWLockExclusive
0x18007de8f  inc     dword ptr [rbx+0Ch]
0x18007de92  lea     rdi, [rbx+8]
0x18007de96  cmp     dword ptr [rbx+0Ch], 1
0x18007de9a  jnz     short loc_18007DEA1
0x18007de9c  mov     eax, r12d
0x18007de9f  xchg    eax, [rdi]
0x18007dea1  mov     [rsp+58h+var_30], rbx
0x18007dea6  mov     rcx, rbx; SRWLock
0x18007dea9  call    cs:__imp_ReleaseSRWLockExclusive
0x18007deaf  nop
0x18007deb0  mov     rcx, rsi; this
0x18007deb3  call    ?WaitForInitAndCheckShutdown@CDeliveryOptimizationManager@@QEBAJXZ; CDeliveryOptimizationManager::WaitForInitAndCheckShutdown(void)
0x18007deb8  mov     r14d, eax
0x18007debb  test    eax, eax
0x18007debd  jns     short loc_18007DEEE
0x18007debf  mov     rcx, rbx; SRWLock
0x18007dec2  call    cs:__imp_AcquireSRWLockExclusive
0x18007dec8  add     dword ptr [rbx+0Ch], 0FFFFFFFFh
0x18007decc  jnz     short loc_18007DEDD
0x18007dece  mov     dword ptr [rdi], 1
0x18007ded4  mov     rcx, rdi; Address
0x18007ded7  call    cs:__imp_WakeByAddressAll
0x18007dedd  mov     rcx, rbx; SRWLock
0x18007dee0  call    cs:__imp_ReleaseSRWLockExclusive
0x18007dee6  mov     eax, r14d
0x18007dee9  jmp     loc_18007DFC2
0x18007deee  call    cs:__imp_CoImpersonateClient
0x18007def4  mov     rcx, [rsp+58h]; this
0x18007def9  test    eax, eax
0x18007defb  js      loc_18007DFD4
0x18007df01  mov     byte ptr [rsp+58h+var_38], 1; int
0x18007df06  call    ?IsAdminToken@@YA_NPEAX@Z; IsAdminToken(void *)
0x18007df0b  mov     dil, al
0x18007df0e  call    cs:__imp_CoRevertToSelf
0x18007df14  test    dil, dil
0x18007df17  jnz     short loc_18007DF64
0x18007df19  mov     rcx, [rsp+58h]; this
0x18007df1e  mov     edi, 80070005h
0x18007df23  mov     r9d, edi; char *
0x18007df26  lea     r8, aCW1SSrcDeliver_49; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18007df2d  mov     edx, 13Eh; void *
0x18007df32  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007df37  nop
0x18007df38  mov     rcx, rbx; SRWLock
0x18007df3b  call    cs:__imp_AcquireSRWLockExclusive
0x18007df41  add     dword ptr [rbx+0Ch], 0FFFFFFFFh
0x18007df45  jnz     short loc_18007DF57
0x18007df47  lea     rcx, [rbx+8]; Address
0x18007df4b  mov     dword ptr [rcx], 1
0x18007df51  call    cs:__imp_WakeByAddressAll
0x18007df57  mov     rcx, rbx; SRWLock
0x18007df5a  call    cs:__imp_ReleaseSRWLockExclusive
0x18007df60  mov     eax, edi
0x18007df62  jmp     short loc_18007DFC2
0x18007df64  mov     rdx, r15; struct UsagePolicy *
0x18007df67  mov     rcx, [rsi+38h]; this
0x18007df6b  call    ?SetUsagePolicy@CGlobalConfigManager@@QEAAJPEBUUsagePolicy@@@Z; CGlobalConfigManager::SetUsagePolicy(UsagePolicy const *)
0x18007df70  mov     edi, eax
0x18007df72  test    eax, eax
0x18007df74  jnz     short loc_18007DF84
0x18007df76  mov     rcx, [rsi+0B0h]; this
0x18007df7d  call    ?OnUsagePolicyChange@CCore@@QEAAXXZ; CCore::OnUsagePolicyChange(void)
0x18007df82  jmp     short loc_18007DF8B
0x18007df84  cmp     edi, 1
0x18007df87  cmovz   edi, r12d
0x18007df8b  mov     rcx, rbx; SRWLock
0x18007df8e  call    cs:__imp_AcquireSRWLockExclusive
0x18007df94  add     dword ptr [rbx+0Ch], 0FFFFFFFFh
0x18007df98  jnz     short loc_18007DFAA
0x18007df9a  lea     rcx, [rbx+8]; Address
0x18007df9e  mov     dword ptr [rcx], 1
0x18007dfa4  call    cs:__imp_WakeByAddressAll
0x18007dfaa  mov     rcx, rbx; SRWLock
0x18007dfad  call    cs:__imp_ReleaseSRWLockExclusive
0x18007dfb3  mov     eax, edi
0x18007dfb5  jmp     short loc_18007DFC2
0x18007dfb7  mov     eax, 8007000Eh
0x18007dfbc  jmp     short loc_18007DFC2
0x18007dfbe  mov     eax, dword ptr [rsp+58h+var_30]
0x18007dfc2  mov     rbx, [rsp+58h+arg_10]
0x18007dfc7  add     rsp, 30h
0x18007dfcb  pop     r15
0x18007dfcd  pop     r14
0x18007dfcf  pop     r12
0x18007dfd1  pop     rdi
0x18007dfd2  pop     rsi
0x18007dfd3  retn
0x18007dfd4  mov     r9d, eax; char *
0x18007dfd7  lea     r8, aCW1SPackagesMi_3; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18007dfde  mov     edx, 1262h; void *
0x18007dfe3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
