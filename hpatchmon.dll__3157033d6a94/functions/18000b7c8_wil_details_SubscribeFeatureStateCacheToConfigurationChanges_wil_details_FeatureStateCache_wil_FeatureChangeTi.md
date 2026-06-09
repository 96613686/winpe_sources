# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x18000b7c8`
- end: `0x18000b8cc`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `260`
- prototype: `void __fastcall(volatile signed __int32 *, unsigned int, int)`
- caller_count: `12`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180005e44`
- `0x180005fc4`
- `0x1800060a4`
- `0x180006184`
- `0x180007700`
- `0x180012398`
- `0x18001256c`
- `0x1800126e0`
- `0x180012854`
- `0x1800129c8`
- `0x180012aa8`
- `0x180012b88`

## callees

- `0x180002b62`
- `0x180002be8`
- `0x18000b7c8`
- `0x18000c80c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b859`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b883`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b859`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b883`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b7f4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b7f4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b8b6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b8b6`

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
      || a3 != dword_18001E6BC
      || (*(_QWORD *)&v12 = a2,
          *((_QWORD *)&v12 + 1) = a1,
          !wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_18001E6E0, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
      goto LABEL_13;
    }
    v8 = (qword_18001E6F0 - (_QWORD)qword_18001E6E8) & -(__int64)((unsigned __int64)qword_18001E6E8 < qword_18001E6F0);
    if ( qword_18001E6E8 )
    {
      if ( v8 >= 0x10 )
      {
        *(_OWORD *)qword_18001E6E8 = v12;
LABEL_11:
        qword_18001E6E8 = (char *)qword_18001E6E8 + 16;
LABEL_13:
        ReleaseSRWLockExclusive(&SRWLock);
        return;
      }
      memset_0(qword_18001E6E8, 0, v8);
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
0x18000b7c8  mov     [rsp+arg_0], rbx
0x18000b7cd  mov     [rsp+arg_8], rsi
0x18000b7d2  push    rdi
0x18000b7d3  sub     rsp, 30h
0x18000b7d7  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000b7dd  mov     esi, r8d
0x18000b7e0  mov     ebx, edx
0x18000b7e2  mov     rdi, rcx
0x18000b7e5  test    eax, eax
0x18000b7e7  jz      loc_18000B8BC
0x18000b7ed  lea     rcx, SRWLock; SRWLock
0x18000b7f4  call    cs:__imp_AcquireSRWLockExclusive
0x18000b7fa  mov     eax, cs:dword_18001E6BC
0x18000b800  test    esi, esi
0x18000b802  jz      loc_18000B89E
0x18000b808  cmp     esi, eax
0x18000b80a  jnz     loc_18000B89E
0x18000b810  mov     edx, 10h; unsigned __int64
0x18000b815  mov     dword ptr [rsp+38h+var_18+4], 0
0x18000b81d  lea     rcx, qword_18001E6E0; this
0x18000b824  mov     dword ptr [rsp+38h+var_18], ebx
0x18000b828  mov     qword ptr [rsp+38h+var_18+8], rdi
0x18000b82d  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000b832  test    al, al
0x18000b834  jz      short loc_18000B89E
0x18000b836  mov     r9, cs:qword_18001E6E8
0x18000b83d  mov     rax, cs:qword_18001E6F0
0x18000b844  sub     rax, r9
0x18000b847  cmp     r9, cs:qword_18001E6F0
0x18000b84e  sbb     r8, r8
0x18000b851  and     r8, rax; Size
0x18000b854  test    r9, r9
0x18000b857  jnz     short loc_18000B867
0x18000b859  call    cs:__imp__o__errno
0x18000b85f  mov     dword ptr [rax], 16h
0x18000b865  jmp     short loc_18000B88F
0x18000b867  cmp     r8, 10h
0x18000b86b  jb      short loc_18000B879
0x18000b86d  movups  xmm0, [rsp+38h+var_18]
0x18000b872  movdqu  xmmword ptr [r9], xmm0
0x18000b877  jmp     short loc_18000B894
0x18000b879  xor     edx, edx; Val
0x18000b87b  mov     rcx, r9; void *
0x18000b87e  call    memset_0
0x18000b883  call    cs:__imp__o__errno
0x18000b889  mov     dword ptr [rax], 22h ; '"'
0x18000b88f  call    _invalid_parameter_noinfo
0x18000b894  add     cs:qword_18001E6E8, 10h
0x18000b89c  jmp     short loc_18000B8AF
0x18000b89e  neg     ebx
0x18000b8a0  sbb     eax, eax
0x18000b8a2  and     eax, 83Ah
0x18000b8a7  add     eax, 0FFFFF7C1h
0x18000b8ac  lock and [rdi], eax
0x18000b8af  lea     rcx, SRWLock; SRWLock
0x18000b8b6  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b8bc  mov     rbx, [rsp+38h+arg_0]
0x18000b8c1  mov     rsi, [rsp+38h+arg_8]
0x18000b8c6  add     rsp, 30h
0x18000b8ca  pop     rdi
0x18000b8cb  retn
```
