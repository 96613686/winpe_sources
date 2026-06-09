# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180008dc0`
- end: `0x180008ec4`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `260`
- prototype: `void __fastcall(volatile signed __int32 *, unsigned int, int)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000612c`
- `0x18000af50`
- `0x18000b124`
- `0x18000b2a4`

## callees

- `0x18000288a`
- `0x1800028dc`
- `0x180008dc0`
- `0x180009ba0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008e51`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008e7b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008e51`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008e7b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008dec`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008dec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008eae`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008eae`

## pseudocode

```c
void __fastcall wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        volatile signed __int32 *a1,
        unsigned int a2,
        int a3)
{
  __int64 v6; // rdx
  __int64 v7; // rcx
  size_t v8; // r8
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int128 v12; // [rsp+20h] [rbp-18h]

  if ( wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !a3
      || a3 != dword_180020774
      || (*(_QWORD *)&v12 = a2,
          *((_QWORD *)&v12 + 1) = a1,
          !wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_180020798, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
      goto LABEL_13;
    }
    v8 = (qword_1800207A8 - (_QWORD)qword_1800207A0) & -(__int64)((unsigned __int64)qword_1800207A0 < qword_1800207A8);
    if ( qword_1800207A0 )
    {
      if ( v8 >= 0x10 )
      {
        *(_OWORD *)qword_1800207A0 = v12;
LABEL_11:
        qword_1800207A0 = (char *)qword_1800207A0 + 16;
LABEL_13:
        ReleaseSRWLockExclusive(&SRWLock);
        return;
      }
      memset_0(qword_1800207A0, 0, v8);
      *(_DWORD *)_o__errno(v10, v9, v11) = 34;
    }
    else
    {
      *(_DWORD *)_o__errno(v7, v6, v8) = 22;
    }
    invalid_parameter_noinfo();
    goto LABEL_11;
  }
}

```

## disassembly

```asm
0x180008dc0  mov     [rsp+arg_0], rbx
0x180008dc5  mov     [rsp+arg_8], rsi
0x180008dca  push    rdi
0x180008dcb  sub     rsp, 30h
0x180008dcf  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180008dd5  mov     esi, r8d
0x180008dd8  mov     ebx, edx
0x180008dda  mov     rdi, rcx
0x180008ddd  test    eax, eax
0x180008ddf  jz      loc_180008EB4
0x180008de5  lea     rcx, SRWLock; SRWLock
0x180008dec  call    cs:__imp_AcquireSRWLockExclusive
0x180008df2  mov     eax, cs:dword_180020774
0x180008df8  test    esi, esi
0x180008dfa  jz      loc_180008E96
0x180008e00  cmp     esi, eax
0x180008e02  jnz     loc_180008E96
0x180008e08  mov     edx, 10h; unsigned __int64
0x180008e0d  mov     dword ptr [rsp+38h+var_18+4], 0
0x180008e15  lea     rcx, qword_180020798; this
0x180008e1c  mov     dword ptr [rsp+38h+var_18], ebx
0x180008e20  mov     qword ptr [rsp+38h+var_18+8], rdi
0x180008e25  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180008e2a  test    al, al
0x180008e2c  jz      short loc_180008E96
0x180008e2e  mov     r9, cs:qword_1800207A0
0x180008e35  mov     rax, cs:qword_1800207A8
0x180008e3c  sub     rax, r9
0x180008e3f  cmp     r9, cs:qword_1800207A8
0x180008e46  sbb     r8, r8
0x180008e49  and     r8, rax; Size
0x180008e4c  test    r9, r9
0x180008e4f  jnz     short loc_180008E5F
0x180008e51  call    cs:__imp__o__errno
0x180008e57  mov     dword ptr [rax], 16h
0x180008e5d  jmp     short loc_180008E87
0x180008e5f  cmp     r8, 10h
0x180008e63  jb      short loc_180008E71
0x180008e65  movups  xmm0, [rsp+38h+var_18]
0x180008e6a  movdqu  xmmword ptr [r9], xmm0
0x180008e6f  jmp     short loc_180008E8C
0x180008e71  xor     edx, edx; Val
0x180008e73  mov     rcx, r9; void *
0x180008e76  call    memset_0
0x180008e7b  call    cs:__imp__o__errno
0x180008e81  mov     dword ptr [rax], 22h ; '"'
0x180008e87  call    _invalid_parameter_noinfo
0x180008e8c  add     cs:qword_1800207A0, 10h
0x180008e94  jmp     short loc_180008EA7
0x180008e96  neg     ebx
0x180008e98  sbb     eax, eax
0x180008e9a  and     eax, 83Ah
0x180008e9f  add     eax, 0FFFFF7C1h
0x180008ea4  lock and [rdi], eax
0x180008ea7  lea     rcx, SRWLock; SRWLock
0x180008eae  call    cs:__imp_ReleaseSRWLockExclusive
0x180008eb4  mov     rbx, [rsp+38h+arg_0]
0x180008eb9  mov     rsi, [rsp+38h+arg_8]
0x180008ebe  add     rsp, 30h
0x180008ec2  pop     rdi
0x180008ec3  retn
```
