# RTSecurityContextBase::SetInternalCryptoProvider(void)

- ea: `0x18001762c`
- end: `0x1800176cd`
- name: `?SetInternalCryptoProvider@RTSecurityContextBase@@AEAAHXZ`
- size: `161`
- prototype: `__int64 __fastcall(RTSecurityContextBase *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180016f9c`

## callees

- `0x180013bbc`
- `0x18001762c`

## import_xrefs

- `ADVAPI32!CryptAcquireContextW` at `0x1800176b0`
- `ADVAPI32!CryptAcquireContextW` at `0x1800176b0`
- `KERNEL32!LeaveCriticalSection` at `0x180017690`
- `KERNEL32!LeaveCriticalSection` at `0x1800176bb`
- `KERNEL32!LeaveCriticalSection` at `0x180017690`
- `KERNEL32!LeaveCriticalSection` at `0x1800176bb`

## string_xrefs

- `0x180017653`: `MSMQ_SERVICE`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RTSecurityContextBase::SetInternalCryptoProvider(RTSecurityContextBase *this)
{
  int v1; // eax
  HCRYPTPROV *v2; // rbx
  const WCHAR *v3; // rdi
  DWORD dwFlags; // esi
  unsigned int v6; // ebx

  v1 = *((_DWORD *)this + 10);
  v2 = &RTSecurityContextBase::s_hInternalCertLocalSystemCryptoProvider;
  if ( !v1 )
    v2 = &RTSecurityContextBase::s_hInternalCertCryptoProvider;
  v3 = L"MSMQ_SERVICE";
  if ( !v1 )
    v3 = L"MSMQ";
  dwFlags = v1 != 0 ? 0x20 : 0;
  if ( *v2 )
    return 1;
  CCriticalSection::Lock((CCriticalSection *)&RTSecurityContextBase::s_cryptoProviderCS);
  if ( *v2 )
  {
    LeaveCriticalSection(&RTSecurityContextBase::s_cryptoProviderCS);
    return 1;
  }
  v6 = CryptAcquireContextW(v2, v3, L"Microsoft Enhanced RSA and AES Cryptographic Provider", 0x18u, dwFlags);
  LeaveCriticalSection(&RTSecurityContextBase::s_cryptoProviderCS);
  return v6;
}

```

## disassembly

```asm
0x18001762c  push    rbx
0x18001762e  push    rbp
0x18001762f  push    rsi
0x180017630  push    rdi
0x180017631  sub     rsp, 38h
0x180017635  mov     eax, [rcx+28h]
0x180017638  lea     rcx, ?s_hInternalCertCryptoProvider@RTSecurityContextBase@@0_KA; unsigned __int64 RTSecurityContextBase::s_hInternalCertCryptoProvider
0x18001763f  lea     rbx, ?s_hInternalCertLocalSystemCryptoProvider@RTSecurityContextBase@@0_KA; unsigned __int64 RTSecurityContextBase::s_hInternalCertLocalSystemCryptoProvider
0x180017646  test    eax, eax
0x180017648  cmovz   rbx, rcx
0x18001764c  lea     rcx, szContainer; "MSMQ"
0x180017653  lea     rdi, aMsmqService; "MSMQ_SERVICE"
0x18001765a  cmovz   rdi, rcx
0x18001765e  neg     eax
0x180017660  sbb     esi, esi
0x180017662  and     esi, 20h
0x180017665  cmp     qword ptr [rbx], 0
0x180017669  jz      short loc_180017672
0x18001766b  mov     eax, 1
0x180017670  jmp     short loc_1800176C4
0x180017672  lea     rbp, ?s_cryptoProviderCS@RTSecurityContextBase@@0VCCriticalSection@@A; CCriticalSection RTSecurityContextBase::s_cryptoProviderCS
0x180017679  mov     [rsp+58h+arg_0], rbp
0x18001767e  mov     rcx, rbp; this
0x180017681  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x180017686  nop
0x180017687  cmp     qword ptr [rbx], 0
0x18001768b  jz      short loc_180017699
0x18001768d  mov     rcx, rbp; lpCriticalSection
0x180017690  call    cs:__imp_LeaveCriticalSection
0x180017696  nop
0x180017697  jmp     short loc_18001766B
0x180017699  mov     [rsp+58h+dwFlags], esi; dwFlags
0x18001769d  mov     r9d, 18h; dwProvType
0x1800176a3  lea     r8, aMicrosoftEnhan; "Microsoft Enhanced RSA and AES Cryptogr"...
0x1800176aa  mov     rdx, rdi; szContainer
0x1800176ad  mov     rcx, rbx; phProv
0x1800176b0  call    cs:__imp_CryptAcquireContextW
0x1800176b6  mov     ebx, eax
0x1800176b8  mov     rcx, rbp; lpCriticalSection
0x1800176bb  call    cs:__imp_LeaveCriticalSection
0x1800176c1  nop
0x1800176c2  mov     eax, ebx
0x1800176c4  add     rsp, 38h
0x1800176c8  pop     rdi
0x1800176c9  pop     rsi
0x1800176ca  pop     rbp
0x1800176cb  pop     rbx
0x1800176cc  retn
```
