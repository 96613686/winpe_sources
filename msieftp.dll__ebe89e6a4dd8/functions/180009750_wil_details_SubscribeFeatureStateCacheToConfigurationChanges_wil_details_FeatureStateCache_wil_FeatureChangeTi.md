# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180009750`
- end: `0x180009854`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `260`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180005a14`
- `0x180005af4`
- `0x180005cc8`
- `0x180006d58`

## callees

- `0x180002b1a`
- `0x180002b60`
- `0x180009750`
- `0x18000a570`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800097e1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000980b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800097e1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000980b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000977c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000977c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000983e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000983e`

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
      || a3 != dword_180032634
      || (*(_QWORD *)&v12 = a2,
          *((_QWORD *)&v12 + 1) = a1,
          !wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_180032658, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
      goto LABEL_13;
    }
    v8 = (qword_180032668 - (_QWORD)qword_180032660) & -(__int64)((unsigned __int64)qword_180032660 < qword_180032668);
    if ( qword_180032660 )
    {
      if ( v8 >= 0x10 )
      {
        *(_OWORD *)qword_180032660 = v12;
LABEL_11:
        qword_180032660 = (char *)qword_180032660 + 16;
LABEL_13:
        ReleaseSRWLockExclusive(&SRWLock);
        return;
      }
      memset_0(qword_180032660, 0, v8);
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
0x180009750  mov     [rsp+arg_0], rbx
0x180009755  mov     [rsp+arg_8], rsi
0x18000975a  push    rdi
0x18000975b  sub     rsp, 30h
0x18000975f  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180009765  mov     esi, r8d
0x180009768  mov     ebx, edx
0x18000976a  mov     rdi, rcx
0x18000976d  test    eax, eax
0x18000976f  jz      loc_180009844
0x180009775  lea     rcx, SRWLock; SRWLock
0x18000977c  call    cs:__imp_AcquireSRWLockExclusive
0x180009782  mov     eax, cs:dword_180032634
0x180009788  test    esi, esi
0x18000978a  jz      loc_180009826
0x180009790  cmp     esi, eax
0x180009792  jnz     loc_180009826
0x180009798  mov     edx, 10h; unsigned __int64
0x18000979d  mov     dword ptr [rsp+38h+var_18+4], 0
0x1800097a5  lea     rcx, qword_180032658; this
0x1800097ac  mov     dword ptr [rsp+38h+var_18], ebx
0x1800097b0  mov     qword ptr [rsp+38h+var_18+8], rdi
0x1800097b5  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800097ba  test    al, al
0x1800097bc  jz      short loc_180009826
0x1800097be  mov     r9, cs:qword_180032660
0x1800097c5  mov     rax, cs:qword_180032668
0x1800097cc  sub     rax, r9
0x1800097cf  cmp     r9, cs:qword_180032668
0x1800097d6  sbb     r8, r8
0x1800097d9  and     r8, rax; Size
0x1800097dc  test    r9, r9
0x1800097df  jnz     short loc_1800097EF
0x1800097e1  call    cs:__imp__o__errno
0x1800097e7  mov     dword ptr [rax], 16h
0x1800097ed  jmp     short loc_180009817
0x1800097ef  cmp     r8, 10h
0x1800097f3  jb      short loc_180009801
0x1800097f5  movups  xmm0, [rsp+38h+var_18]
0x1800097fa  movdqu  xmmword ptr [r9], xmm0
0x1800097ff  jmp     short loc_18000981C
0x180009801  xor     edx, edx; Val
0x180009803  mov     rcx, r9; void *
0x180009806  call    memset_0
0x18000980b  call    cs:__imp__o__errno
0x180009811  mov     dword ptr [rax], 22h ; '"'
0x180009817  call    _invalid_parameter_noinfo
0x18000981c  add     cs:qword_180032660, 10h
0x180009824  jmp     short loc_180009837
0x180009826  neg     ebx
0x180009828  sbb     eax, eax
0x18000982a  and     eax, 83Ah
0x18000982f  add     eax, 0FFFFF7C1h
0x180009834  lock and [rdi], eax
0x180009837  lea     rcx, SRWLock; SRWLock
0x18000983e  call    cs:__imp_ReleaseSRWLockExclusive
0x180009844  mov     rbx, [rsp+38h+arg_0]
0x180009849  mov     rsi, [rsp+38h+arg_8]
0x18000984e  add     rsp, 30h
0x180009852  pop     rdi
0x180009853  retn
```
