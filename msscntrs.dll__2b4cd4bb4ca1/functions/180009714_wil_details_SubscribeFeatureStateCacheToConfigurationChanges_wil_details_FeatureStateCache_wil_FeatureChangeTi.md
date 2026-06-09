# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180009714`
- end: `0x180009818`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `260`
- prototype: `void __fastcall(volatile signed __int32 *, unsigned int, int)`
- caller_count: `18`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180006d28`
- `0x18000c984`
- `0x18000ca64`
- `0x18000cc34`
- `0x18000cd14`
- `0x18000ce88`
- `0x18000cffc`
- `0x18000d170`
- `0x18000d2e4`
- `0x18000d464`
- `0x1800124a8`
- `0x18001267c`
- `0x1800127f0`
- `0x1800128d0`
- `0x1800129b0`
- `0x180012a90`
- `0x180012b70`
- `0x180012c50`

## callees

- `0x1800032b2`
- `0x180003320`
- `0x180009714`
- `0x18000a54c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800097a5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800097cf`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800097a5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800097cf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009740`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009740`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009802`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009802`

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
      || a3 != dword_180021C74
      || (*(_QWORD *)&v12 = a2,
          *((_QWORD *)&v12 + 1) = a1,
          !wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_180021C98, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
      goto LABEL_13;
    }
    v8 = (qword_180021CA8 - (_QWORD)qword_180021CA0) & -(__int64)((unsigned __int64)qword_180021CA0 < qword_180021CA8);
    if ( qword_180021CA0 )
    {
      if ( v8 >= 0x10 )
      {
        *(_OWORD *)qword_180021CA0 = v12;
LABEL_11:
        qword_180021CA0 = (char *)qword_180021CA0 + 16;
LABEL_13:
        ReleaseSRWLockExclusive(&SRWLock);
        return;
      }
      memset_0(qword_180021CA0, 0, v8);
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
0x180009714  mov     [rsp+arg_0], rbx
0x180009719  mov     [rsp+arg_8], rsi
0x18000971e  push    rdi
0x18000971f  sub     rsp, 30h
0x180009723  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180009729  mov     esi, r8d
0x18000972c  mov     ebx, edx
0x18000972e  mov     rdi, rcx
0x180009731  test    eax, eax
0x180009733  jz      loc_180009808
0x180009739  lea     rcx, SRWLock; SRWLock
0x180009740  call    cs:__imp_AcquireSRWLockExclusive
0x180009746  mov     eax, cs:dword_180021C74
0x18000974c  test    esi, esi
0x18000974e  jz      loc_1800097EA
0x180009754  cmp     esi, eax
0x180009756  jnz     loc_1800097EA
0x18000975c  mov     edx, 10h; unsigned __int64
0x180009761  mov     dword ptr [rsp+38h+var_18+4], 0
0x180009769  lea     rcx, qword_180021C98; this
0x180009770  mov     dword ptr [rsp+38h+var_18], ebx
0x180009774  mov     qword ptr [rsp+38h+var_18+8], rdi
0x180009779  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000977e  test    al, al
0x180009780  jz      short loc_1800097EA
0x180009782  mov     r9, cs:qword_180021CA0
0x180009789  mov     rax, cs:qword_180021CA8
0x180009790  sub     rax, r9
0x180009793  cmp     r9, cs:qword_180021CA8
0x18000979a  sbb     r8, r8
0x18000979d  and     r8, rax; Size
0x1800097a0  test    r9, r9
0x1800097a3  jnz     short loc_1800097B3
0x1800097a5  call    cs:__imp__o__errno
0x1800097ab  mov     dword ptr [rax], 16h
0x1800097b1  jmp     short loc_1800097DB
0x1800097b3  cmp     r8, 10h
0x1800097b7  jb      short loc_1800097C5
0x1800097b9  movups  xmm0, [rsp+38h+var_18]
0x1800097be  movdqu  xmmword ptr [r9], xmm0
0x1800097c3  jmp     short loc_1800097E0
0x1800097c5  xor     edx, edx; Val
0x1800097c7  mov     rcx, r9; void *
0x1800097ca  call    memset_0
0x1800097cf  call    cs:__imp__o__errno
0x1800097d5  mov     dword ptr [rax], 22h ; '"'
0x1800097db  call    _invalid_parameter_noinfo
0x1800097e0  add     cs:qword_180021CA0, 10h
0x1800097e8  jmp     short loc_1800097FB
0x1800097ea  neg     ebx
0x1800097ec  sbb     eax, eax
0x1800097ee  and     eax, 83Ah
0x1800097f3  add     eax, 0FFFFF7C1h
0x1800097f8  lock and [rdi], eax
0x1800097fb  lea     rcx, SRWLock; SRWLock
0x180009802  call    cs:__imp_ReleaseSRWLockExclusive
0x180009808  mov     rbx, [rsp+38h+arg_0]
0x18000980d  mov     rsi, [rsp+38h+arg_8]
0x180009812  add     rsp, 30h
0x180009816  pop     rdi
0x180009817  retn
```
