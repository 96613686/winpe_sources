# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x18000bbb0`
- end: `0x18000bcb4`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `260`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000a374`
- `0x18001b5fc`
- `0x18001b7d0`
- `0x18001b950`
- `0x18001bb0c`
- `0x18001bbec`

## callees

- `0x180002b1a`
- `0x180002b78`
- `0x18000bbb0`
- `0x18000c544`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000bc41`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000bc6b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000bc41`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000bc6b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000bc9e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000bc9e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000bbdc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000bbdc`

## pseudocode

```c
void __fastcall wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        volatile signed __int32 *a1,
        unsigned int a2,
        int a3)
{
  __int64 v6; // rcx
  size_t v7; // r8
  __int64 v8; // rcx
  __int128 v9; // [rsp+20h] [rbp-18h]

  if ( wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !a3
      || a3 != dword_180043AB4
      || (*(_QWORD *)&v9 = a2,
          *((_QWORD *)&v9 + 1) = a1,
          !wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_180043AD8, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
      goto LABEL_13;
    }
    v7 = (qword_180043AE8 - (_QWORD)qword_180043AE0) & -(__int64)((unsigned __int64)qword_180043AE0 < qword_180043AE8);
    if ( qword_180043AE0 )
    {
      if ( v7 >= 0x10 )
      {
        *(_OWORD *)qword_180043AE0 = v9;
LABEL_11:
        qword_180043AE0 = (char *)qword_180043AE0 + 16;
LABEL_13:
        ReleaseSRWLockExclusive(&SRWLock);
        return;
      }
      memset_0(qword_180043AE0, 0, v7);
      *(_DWORD *)_o__errno(v8) = 34;
    }
    else
    {
      *(_DWORD *)_o__errno(v6) = 22;
    }
    invalid_parameter_noinfo();
    goto LABEL_11;
  }
}

```

## disassembly

```asm
0x18000bbb0  mov     [rsp+arg_0], rbx
0x18000bbb5  mov     [rsp+arg_8], rsi
0x18000bbba  push    rdi
0x18000bbbb  sub     rsp, 30h
0x18000bbbf  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000bbc5  mov     esi, r8d
0x18000bbc8  mov     ebx, edx
0x18000bbca  mov     rdi, rcx
0x18000bbcd  test    eax, eax
0x18000bbcf  jz      loc_18000BCA4
0x18000bbd5  lea     rcx, SRWLock; SRWLock
0x18000bbdc  call    cs:__imp_AcquireSRWLockExclusive
0x18000bbe2  mov     eax, cs:dword_180043AB4
0x18000bbe8  test    esi, esi
0x18000bbea  jz      loc_18000BC86
0x18000bbf0  cmp     esi, eax
0x18000bbf2  jnz     loc_18000BC86
0x18000bbf8  mov     edx, 10h; unsigned __int64
0x18000bbfd  mov     dword ptr [rsp+38h+var_18+4], 0
0x18000bc05  lea     rcx, qword_180043AD8; this
0x18000bc0c  mov     dword ptr [rsp+38h+var_18], ebx
0x18000bc10  mov     qword ptr [rsp+38h+var_18+8], rdi
0x18000bc15  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000bc1a  test    al, al
0x18000bc1c  jz      short loc_18000BC86
0x18000bc1e  mov     r9, cs:qword_180043AE0
0x18000bc25  mov     rax, cs:qword_180043AE8
0x18000bc2c  sub     rax, r9
0x18000bc2f  cmp     r9, cs:qword_180043AE8
0x18000bc36  sbb     r8, r8
0x18000bc39  and     r8, rax; Size
0x18000bc3c  test    r9, r9
0x18000bc3f  jnz     short loc_18000BC4F
0x18000bc41  call    cs:__imp__o__errno
0x18000bc47  mov     dword ptr [rax], 16h
0x18000bc4d  jmp     short loc_18000BC77
0x18000bc4f  cmp     r8, 10h
0x18000bc53  jb      short loc_18000BC61
0x18000bc55  movups  xmm0, [rsp+38h+var_18]
0x18000bc5a  movdqu  xmmword ptr [r9], xmm0
0x18000bc5f  jmp     short loc_18000BC7C
0x18000bc61  xor     edx, edx; Val
0x18000bc63  mov     rcx, r9; void *
0x18000bc66  call    memset_0
0x18000bc6b  call    cs:__imp__o__errno
0x18000bc71  mov     dword ptr [rax], 22h ; '"'
0x18000bc77  call    _invalid_parameter_noinfo
0x18000bc7c  add     cs:qword_180043AE0, 10h
0x18000bc84  jmp     short loc_18000BC97
0x18000bc86  neg     ebx
0x18000bc88  sbb     eax, eax
0x18000bc8a  and     eax, 83Ah
0x18000bc8f  add     eax, 0FFFFF7C1h
0x18000bc94  lock and [rdi], eax
0x18000bc97  lea     rcx, SRWLock; SRWLock
0x18000bc9e  call    cs:__imp_ReleaseSRWLockExclusive
0x18000bca4  mov     rbx, [rsp+38h+arg_0]
0x18000bca9  mov     rsi, [rsp+38h+arg_8]
0x18000bcae  add     rsp, 30h
0x18000bcb2  pop     rdi
0x18000bcb3  retn
```
