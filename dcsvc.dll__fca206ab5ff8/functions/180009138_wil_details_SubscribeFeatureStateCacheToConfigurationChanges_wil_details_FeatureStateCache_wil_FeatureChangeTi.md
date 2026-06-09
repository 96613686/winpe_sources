# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180009138`
- end: `0x18000923c`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `260`
- prototype: `void __fastcall(volatile signed __int32 *, unsigned int, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180006210`
- `0x18000b9d0`

## callees

- `0x180002666`
- `0x1800026c8`
- `0x180009138`
- `0x18000a270`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800091c9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800091f3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800091c9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800091f3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009226`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009226`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009164`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009164`

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
      || a3 != dword_18001B584
      || (*(_QWORD *)&v12 = a2,
          *((_QWORD *)&v12 + 1) = a1,
          !wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_18001B5A8, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
      goto LABEL_13;
    }
    v8 = (qword_18001B5B8 - (_QWORD)qword_18001B5B0) & -(__int64)((unsigned __int64)qword_18001B5B0 < qword_18001B5B8);
    if ( qword_18001B5B0 )
    {
      if ( v8 >= 0x10 )
      {
        *(_OWORD *)qword_18001B5B0 = v12;
LABEL_11:
        qword_18001B5B0 = (char *)qword_18001B5B0 + 16;
LABEL_13:
        ReleaseSRWLockExclusive(&SRWLock);
        return;
      }
      memset_0(qword_18001B5B0, 0, v8);
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
0x180009138  mov     [rsp+arg_0], rbx
0x18000913d  mov     [rsp+arg_8], rsi
0x180009142  push    rdi
0x180009143  sub     rsp, 30h
0x180009147  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000914d  mov     esi, r8d
0x180009150  mov     ebx, edx
0x180009152  mov     rdi, rcx
0x180009155  test    eax, eax
0x180009157  jz      loc_18000922C
0x18000915d  lea     rcx, SRWLock; SRWLock
0x180009164  call    cs:__imp_AcquireSRWLockExclusive
0x18000916a  mov     eax, cs:dword_18001B584
0x180009170  test    esi, esi
0x180009172  jz      loc_18000920E
0x180009178  cmp     esi, eax
0x18000917a  jnz     loc_18000920E
0x180009180  mov     edx, 10h; unsigned __int64
0x180009185  mov     dword ptr [rsp+38h+var_18+4], 0
0x18000918d  lea     rcx, qword_18001B5A8; this
0x180009194  mov     dword ptr [rsp+38h+var_18], ebx
0x180009198  mov     qword ptr [rsp+38h+var_18+8], rdi
0x18000919d  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800091a2  test    al, al
0x1800091a4  jz      short loc_18000920E
0x1800091a6  mov     r9, cs:qword_18001B5B0
0x1800091ad  mov     rax, cs:qword_18001B5B8
0x1800091b4  sub     rax, r9
0x1800091b7  cmp     r9, cs:qword_18001B5B8
0x1800091be  sbb     r8, r8
0x1800091c1  and     r8, rax; Size
0x1800091c4  test    r9, r9
0x1800091c7  jnz     short loc_1800091D7
0x1800091c9  call    cs:__imp__o__errno
0x1800091cf  mov     dword ptr [rax], 16h
0x1800091d5  jmp     short loc_1800091FF
0x1800091d7  cmp     r8, 10h
0x1800091db  jb      short loc_1800091E9
0x1800091dd  movups  xmm0, [rsp+38h+var_18]
0x1800091e2  movdqu  xmmword ptr [r9], xmm0
0x1800091e7  jmp     short loc_180009204
0x1800091e9  xor     edx, edx; Val
0x1800091eb  mov     rcx, r9; void *
0x1800091ee  call    memset_0
0x1800091f3  call    cs:__imp__o__errno
0x1800091f9  mov     dword ptr [rax], 22h ; '"'
0x1800091ff  call    _invalid_parameter_noinfo
0x180009204  add     cs:qword_18001B5B0, 10h
0x18000920c  jmp     short loc_18000921F
0x18000920e  neg     ebx
0x180009210  sbb     eax, eax
0x180009212  and     eax, 83Ah
0x180009217  add     eax, 0FFFFF7C1h
0x18000921c  lock and [rdi], eax
0x18000921f  lea     rcx, SRWLock; SRWLock
0x180009226  call    cs:__imp_ReleaseSRWLockExclusive
0x18000922c  mov     rbx, [rsp+38h+arg_0]
0x180009231  mov     rsi, [rsp+38h+arg_8]
0x180009236  add     rsp, 30h
0x18000923a  pop     rdi
0x18000923b  retn
```
