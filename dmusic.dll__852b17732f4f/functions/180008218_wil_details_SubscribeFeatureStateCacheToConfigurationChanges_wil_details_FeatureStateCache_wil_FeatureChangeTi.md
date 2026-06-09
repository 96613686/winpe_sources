# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180008218`
- end: `0x18000831c`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `260`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180005750`

## callees

- `0x18000214a`
- `0x1800021a8`
- `0x180008218`
- `0x18000900c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800082a9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800082d3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800082a9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800082d3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008244`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008244`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008306`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008306`

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
      || a3 != dword_18002A3CC
      || (*(_QWORD *)&v12 = a2,
          *((_QWORD *)&v12 + 1) = a1,
          !wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_18002A3F0, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
      goto LABEL_13;
    }
    v8 = (qword_18002A400 - (_QWORD)qword_18002A3F8) & -(__int64)((unsigned __int64)qword_18002A3F8 < qword_18002A400);
    if ( qword_18002A3F8 )
    {
      if ( v8 >= 0x10 )
      {
        *(_OWORD *)qword_18002A3F8 = v12;
LABEL_11:
        qword_18002A3F8 = (char *)qword_18002A3F8 + 16;
LABEL_13:
        ReleaseSRWLockExclusive(&SRWLock);
        return;
      }
      memset_0(qword_18002A3F8, 0, v8);
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
0x180008218  mov     [rsp+arg_0], rbx
0x18000821d  mov     [rsp+arg_8], rsi
0x180008222  push    rdi
0x180008223  sub     rsp, 30h
0x180008227  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000822d  mov     esi, r8d
0x180008230  mov     ebx, edx
0x180008232  mov     rdi, rcx
0x180008235  test    eax, eax
0x180008237  jz      loc_18000830C
0x18000823d  lea     rcx, SRWLock; SRWLock
0x180008244  call    cs:__imp_AcquireSRWLockExclusive
0x18000824a  mov     eax, cs:dword_18002A3CC
0x180008250  test    esi, esi
0x180008252  jz      loc_1800082EE
0x180008258  cmp     esi, eax
0x18000825a  jnz     loc_1800082EE
0x180008260  mov     edx, 10h; unsigned __int64
0x180008265  mov     dword ptr [rsp+38h+var_18+4], 0
0x18000826d  lea     rcx, qword_18002A3F0; this
0x180008274  mov     dword ptr [rsp+38h+var_18], ebx
0x180008278  mov     qword ptr [rsp+38h+var_18+8], rdi
0x18000827d  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180008282  test    al, al
0x180008284  jz      short loc_1800082EE
0x180008286  mov     r9, cs:qword_18002A3F8
0x18000828d  mov     rax, cs:qword_18002A400
0x180008294  sub     rax, r9
0x180008297  cmp     r9, cs:qword_18002A400
0x18000829e  sbb     r8, r8
0x1800082a1  and     r8, rax; Size
0x1800082a4  test    r9, r9
0x1800082a7  jnz     short loc_1800082B7
0x1800082a9  call    cs:__imp__o__errno
0x1800082af  mov     dword ptr [rax], 16h
0x1800082b5  jmp     short loc_1800082DF
0x1800082b7  cmp     r8, 10h
0x1800082bb  jb      short loc_1800082C9
0x1800082bd  movups  xmm0, [rsp+38h+var_18]
0x1800082c2  movdqu  xmmword ptr [r9], xmm0
0x1800082c7  jmp     short loc_1800082E4
0x1800082c9  xor     edx, edx; Val
0x1800082cb  mov     rcx, r9; void *
0x1800082ce  call    memset_0
0x1800082d3  call    cs:__imp__o__errno
0x1800082d9  mov     dword ptr [rax], 22h ; '"'
0x1800082df  call    _invalid_parameter_noinfo
0x1800082e4  add     cs:qword_18002A3F8, 10h
0x1800082ec  jmp     short loc_1800082FF
0x1800082ee  neg     ebx
0x1800082f0  sbb     eax, eax
0x1800082f2  and     eax, 83Ah
0x1800082f7  add     eax, 0FFFFF7C1h
0x1800082fc  lock and [rdi], eax
0x1800082ff  lea     rcx, SRWLock; SRWLock
0x180008306  call    cs:__imp_ReleaseSRWLockExclusive
0x18000830c  mov     rbx, [rsp+38h+arg_0]
0x180008311  mov     rsi, [rsp+38h+arg_8]
0x180008316  add     rsp, 30h
0x18000831a  pop     rdi
0x18000831b  retn
```
