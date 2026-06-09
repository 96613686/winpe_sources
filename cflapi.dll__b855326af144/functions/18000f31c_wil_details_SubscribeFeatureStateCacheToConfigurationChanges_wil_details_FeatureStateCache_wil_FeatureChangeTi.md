# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x18000f31c`
- end: `0x18000f420`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `260`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000a11c`
- `0x18000a3d0`

## callees

- `0x180002ea2`
- `0x180002ef8`
- `0x18000f31c`
- `0x18000fc94`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f3ad`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f3d7`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f3ad`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f3d7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f40a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f40a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f348`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f348`

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
      || a3 != dword_18003F504
      || (*(_QWORD *)&v12 = a2,
          *((_QWORD *)&v12 + 1) = a1,
          !wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_18003F528, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
      goto LABEL_13;
    }
    v8 = (qword_18003F538 - (_QWORD)qword_18003F530) & -(__int64)((unsigned __int64)qword_18003F530 < qword_18003F538);
    if ( qword_18003F530 )
    {
      if ( v8 >= 0x10 )
      {
        *(_OWORD *)qword_18003F530 = v12;
LABEL_11:
        qword_18003F530 = (char *)qword_18003F530 + 16;
LABEL_13:
        ReleaseSRWLockExclusive(&SRWLock);
        return;
      }
      memset_0(qword_18003F530, 0, v8);
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
0x18000f31c  mov     [rsp+arg_0], rbx
0x18000f321  mov     [rsp+arg_8], rsi
0x18000f326  push    rdi
0x18000f327  sub     rsp, 30h
0x18000f32b  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000f331  mov     esi, r8d
0x18000f334  mov     ebx, edx
0x18000f336  mov     rdi, rcx
0x18000f339  test    eax, eax
0x18000f33b  jz      loc_18000F410
0x18000f341  lea     rcx, SRWLock; SRWLock
0x18000f348  call    cs:__imp_AcquireSRWLockExclusive
0x18000f34e  mov     eax, cs:dword_18003F504
0x18000f354  test    esi, esi
0x18000f356  jz      loc_18000F3F2
0x18000f35c  cmp     esi, eax
0x18000f35e  jnz     loc_18000F3F2
0x18000f364  mov     edx, 10h; unsigned __int64
0x18000f369  mov     dword ptr [rsp+38h+var_18+4], 0
0x18000f371  lea     rcx, qword_18003F528; this
0x18000f378  mov     dword ptr [rsp+38h+var_18], ebx
0x18000f37c  mov     qword ptr [rsp+38h+var_18+8], rdi
0x18000f381  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000f386  test    al, al
0x18000f388  jz      short loc_18000F3F2
0x18000f38a  mov     r9, cs:qword_18003F530
0x18000f391  mov     rax, cs:qword_18003F538
0x18000f398  sub     rax, r9
0x18000f39b  cmp     r9, cs:qword_18003F538
0x18000f3a2  sbb     r8, r8
0x18000f3a5  and     r8, rax; Size
0x18000f3a8  test    r9, r9
0x18000f3ab  jnz     short loc_18000F3BB
0x18000f3ad  call    cs:__imp__o__errno
0x18000f3b3  mov     dword ptr [rax], 16h
0x18000f3b9  jmp     short loc_18000F3E3
0x18000f3bb  cmp     r8, 10h
0x18000f3bf  jb      short loc_18000F3CD
0x18000f3c1  movups  xmm0, [rsp+38h+var_18]
0x18000f3c6  movdqu  xmmword ptr [r9], xmm0
0x18000f3cb  jmp     short loc_18000F3E8
0x18000f3cd  xor     edx, edx; Val
0x18000f3cf  mov     rcx, r9; void *
0x18000f3d2  call    memset_0
0x18000f3d7  call    cs:__imp__o__errno
0x18000f3dd  mov     dword ptr [rax], 22h ; '"'
0x18000f3e3  call    _invalid_parameter_noinfo
0x18000f3e8  add     cs:qword_18003F530, 10h
0x18000f3f0  jmp     short loc_18000F403
0x18000f3f2  neg     ebx
0x18000f3f4  sbb     eax, eax
0x18000f3f6  and     eax, 83Ah
0x18000f3fb  add     eax, 0FFFFF7C1h
0x18000f400  lock and [rdi], eax
0x18000f403  lea     rcx, SRWLock; SRWLock
0x18000f40a  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f410  mov     rbx, [rsp+38h+arg_0]
0x18000f415  mov     rsi, [rsp+38h+arg_8]
0x18000f41a  add     rsp, 30h
0x18000f41e  pop     rdi
0x18000f41f  retn
```
