# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180008250`
- end: `0x180008354`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `260`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180004b64`
- `0x180005890`

## callees

- `0x180001f32`
- `0x180001f88`
- `0x180008250`
- `0x180008f3c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800082e1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000830b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800082e1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000830b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000827c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000827c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000833e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000833e`

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
      || a3 != dword_18001237C
      || (*(_QWORD *)&v12 = a2,
          *((_QWORD *)&v12 + 1) = a1,
          !wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_1800123A0, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
      goto LABEL_13;
    }
    v8 = (qword_1800123B0 - (_QWORD)qword_1800123A8) & -(__int64)((unsigned __int64)qword_1800123A8 < qword_1800123B0);
    if ( qword_1800123A8 )
    {
      if ( v8 >= 0x10 )
      {
        *(_OWORD *)qword_1800123A8 = v12;
LABEL_11:
        qword_1800123A8 = (char *)qword_1800123A8 + 16;
LABEL_13:
        ReleaseSRWLockExclusive(&SRWLock);
        return;
      }
      memset_0(qword_1800123A8, 0, v8);
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
0x180008250  mov     [rsp+arg_0], rbx
0x180008255  mov     [rsp+arg_8], rsi
0x18000825a  push    rdi
0x18000825b  sub     rsp, 30h
0x18000825f  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180008265  mov     esi, r8d
0x180008268  mov     ebx, edx
0x18000826a  mov     rdi, rcx
0x18000826d  test    eax, eax
0x18000826f  jz      loc_180008344
0x180008275  lea     rcx, SRWLock; SRWLock
0x18000827c  call    cs:__imp_AcquireSRWLockExclusive
0x180008282  mov     eax, cs:dword_18001237C
0x180008288  test    esi, esi
0x18000828a  jz      loc_180008326
0x180008290  cmp     esi, eax
0x180008292  jnz     loc_180008326
0x180008298  mov     edx, 10h; unsigned __int64
0x18000829d  mov     dword ptr [rsp+38h+var_18+4], 0
0x1800082a5  lea     rcx, qword_1800123A0; this
0x1800082ac  mov     dword ptr [rsp+38h+var_18], ebx
0x1800082b0  mov     qword ptr [rsp+38h+var_18+8], rdi
0x1800082b5  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800082ba  test    al, al
0x1800082bc  jz      short loc_180008326
0x1800082be  mov     r9, cs:qword_1800123A8
0x1800082c5  mov     rax, cs:qword_1800123B0
0x1800082cc  sub     rax, r9
0x1800082cf  cmp     r9, cs:qword_1800123B0
0x1800082d6  sbb     r8, r8
0x1800082d9  and     r8, rax; Size
0x1800082dc  test    r9, r9
0x1800082df  jnz     short loc_1800082EF
0x1800082e1  call    cs:__imp__o__errno
0x1800082e7  mov     dword ptr [rax], 16h
0x1800082ed  jmp     short loc_180008317
0x1800082ef  cmp     r8, 10h
0x1800082f3  jb      short loc_180008301
0x1800082f5  movups  xmm0, [rsp+38h+var_18]
0x1800082fa  movdqu  xmmword ptr [r9], xmm0
0x1800082ff  jmp     short loc_18000831C
0x180008301  xor     edx, edx; Val
0x180008303  mov     rcx, r9; void *
0x180008306  call    memset_0
0x18000830b  call    cs:__imp__o__errno
0x180008311  mov     dword ptr [rax], 22h ; '"'
0x180008317  call    _invalid_parameter_noinfo
0x18000831c  add     cs:qword_1800123A8, 10h
0x180008324  jmp     short loc_180008337
0x180008326  neg     ebx
0x180008328  sbb     eax, eax
0x18000832a  and     eax, 83Ah
0x18000832f  add     eax, 0FFFFF7C1h
0x180008334  lock and [rdi], eax
0x180008337  lea     rcx, SRWLock; SRWLock
0x18000833e  call    cs:__imp_ReleaseSRWLockExclusive
0x180008344  mov     rbx, [rsp+38h+arg_0]
0x180008349  mov     rsi, [rsp+38h+arg_8]
0x18000834e  add     rsp, 30h
0x180008352  pop     rdi
0x180008353  retn
```
