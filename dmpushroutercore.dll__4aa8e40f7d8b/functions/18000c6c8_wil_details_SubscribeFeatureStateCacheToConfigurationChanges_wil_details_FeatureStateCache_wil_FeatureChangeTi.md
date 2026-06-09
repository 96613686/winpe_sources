# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x18000c6c8`
- end: `0x18000c7cc`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `260`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180009c14`
- `0x180011060`
- `0x180031ec0`

## callees

- `0x180004346`
- `0x1800043a8`
- `0x18000c6c8`
- `0x18000d58c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000c759`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000c783`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000c759`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000c783`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c7b6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c7b6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c6f4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c6f4`

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
      || a3 != dword_180050884
      || (*(_QWORD *)&v12 = a2,
          *((_QWORD *)&v12 + 1) = a1,
          !wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_1800508A8, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
      goto LABEL_13;
    }
    v8 = (qword_1800508B8 - (_QWORD)qword_1800508B0) & -(__int64)((unsigned __int64)qword_1800508B0 < qword_1800508B8);
    if ( qword_1800508B0 )
    {
      if ( v8 >= 0x10 )
      {
        *(_OWORD *)qword_1800508B0 = v12;
LABEL_11:
        qword_1800508B0 = (char *)qword_1800508B0 + 16;
LABEL_13:
        ReleaseSRWLockExclusive(&SRWLock);
        return;
      }
      memset_0(qword_1800508B0, 0, v8);
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
0x18000c6c8  mov     [rsp+arg_0], rbx
0x18000c6cd  mov     [rsp+arg_8], rsi
0x18000c6d2  push    rdi
0x18000c6d3  sub     rsp, 30h
0x18000c6d7  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000c6dd  mov     esi, r8d
0x18000c6e0  mov     ebx, edx
0x18000c6e2  mov     rdi, rcx
0x18000c6e5  test    eax, eax
0x18000c6e7  jz      loc_18000C7BC
0x18000c6ed  lea     rcx, SRWLock; SRWLock
0x18000c6f4  call    cs:__imp_AcquireSRWLockExclusive
0x18000c6fa  mov     eax, cs:dword_180050884
0x18000c700  test    esi, esi
0x18000c702  jz      loc_18000C79E
0x18000c708  cmp     esi, eax
0x18000c70a  jnz     loc_18000C79E
0x18000c710  mov     edx, 10h; unsigned __int64
0x18000c715  mov     dword ptr [rsp+38h+var_18+4], 0
0x18000c71d  lea     rcx, qword_1800508A8; this
0x18000c724  mov     dword ptr [rsp+38h+var_18], ebx
0x18000c728  mov     qword ptr [rsp+38h+var_18+8], rdi
0x18000c72d  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000c732  test    al, al
0x18000c734  jz      short loc_18000C79E
0x18000c736  mov     r9, cs:qword_1800508B0
0x18000c73d  mov     rax, cs:qword_1800508B8
0x18000c744  sub     rax, r9
0x18000c747  cmp     r9, cs:qword_1800508B8
0x18000c74e  sbb     r8, r8
0x18000c751  and     r8, rax; Size
0x18000c754  test    r9, r9
0x18000c757  jnz     short loc_18000C767
0x18000c759  call    cs:__imp__o__errno
0x18000c75f  mov     dword ptr [rax], 16h
0x18000c765  jmp     short loc_18000C78F
0x18000c767  cmp     r8, 10h
0x18000c76b  jb      short loc_18000C779
0x18000c76d  movups  xmm0, [rsp+38h+var_18]
0x18000c772  movdqu  xmmword ptr [r9], xmm0
0x18000c777  jmp     short loc_18000C794
0x18000c779  xor     edx, edx; Val
0x18000c77b  mov     rcx, r9; void *
0x18000c77e  call    memset_0
0x18000c783  call    cs:__imp__o__errno
0x18000c789  mov     dword ptr [rax], 22h ; '"'
0x18000c78f  call    _invalid_parameter_noinfo
0x18000c794  add     cs:qword_1800508B0, 10h
0x18000c79c  jmp     short loc_18000C7AF
0x18000c79e  neg     ebx
0x18000c7a0  sbb     eax, eax
0x18000c7a2  and     eax, 83Ah
0x18000c7a7  add     eax, 0FFFFF7C1h
0x18000c7ac  lock and [rdi], eax
0x18000c7af  lea     rcx, SRWLock; SRWLock
0x18000c7b6  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c7bc  mov     rbx, [rsp+38h+arg_0]
0x18000c7c1  mov     rsi, [rsp+38h+arg_8]
0x18000c7c6  add     rsp, 30h
0x18000c7ca  pop     rdi
0x18000c7cb  retn
```
