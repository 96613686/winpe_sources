# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x1400130d4`
- end: `0x1400131d8`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `260`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140010754`
- `0x140034280`

## callees

- `0x140003a6e`
- `0x140003b28`
- `0x1400130d4`
- `0x140013f7c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140013165`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14001318f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140013165`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14001318f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400131c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400131c2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140013100`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140013100`

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
      || a3 != dword_1400758A4
      || (*(_QWORD *)&v12 = a2,
          *((_QWORD *)&v12 + 1) = a1,
          !wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_1400758C8, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
      goto LABEL_13;
    }
    v8 = (qword_1400758D8 - (_QWORD)qword_1400758D0) & -(__int64)((unsigned __int64)qword_1400758D0 < qword_1400758D8);
    if ( qword_1400758D0 )
    {
      if ( v8 >= 0x10 )
      {
        *(_OWORD *)qword_1400758D0 = v12;
LABEL_11:
        qword_1400758D0 = (char *)qword_1400758D0 + 16;
LABEL_13:
        ReleaseSRWLockExclusive(&SRWLock);
        return;
      }
      memset_0(qword_1400758D0, 0, v8);
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
0x1400130d4  mov     [rsp+arg_0], rbx
0x1400130d9  mov     [rsp+arg_8], rsi
0x1400130de  push    rdi
0x1400130df  sub     rsp, 30h
0x1400130e3  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1400130e9  mov     esi, r8d
0x1400130ec  mov     ebx, edx
0x1400130ee  mov     rdi, rcx
0x1400130f1  test    eax, eax
0x1400130f3  jz      loc_1400131C8
0x1400130f9  lea     rcx, SRWLock; SRWLock
0x140013100  call    cs:__imp_AcquireSRWLockExclusive
0x140013106  mov     eax, cs:dword_1400758A4
0x14001310c  test    esi, esi
0x14001310e  jz      loc_1400131AA
0x140013114  cmp     esi, eax
0x140013116  jnz     loc_1400131AA
0x14001311c  mov     edx, 10h; unsigned __int64
0x140013121  mov     dword ptr [rsp+38h+var_18+4], 0
0x140013129  lea     rcx, qword_1400758C8; this
0x140013130  mov     dword ptr [rsp+38h+var_18], ebx
0x140013134  mov     qword ptr [rsp+38h+var_18+8], rdi
0x140013139  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x14001313e  test    al, al
0x140013140  jz      short loc_1400131AA
0x140013142  mov     r9, cs:qword_1400758D0
0x140013149  mov     rax, cs:qword_1400758D8
0x140013150  sub     rax, r9
0x140013153  cmp     r9, cs:qword_1400758D8
0x14001315a  sbb     r8, r8
0x14001315d  and     r8, rax; Size
0x140013160  test    r9, r9
0x140013163  jnz     short loc_140013173
0x140013165  call    cs:__imp__o__errno
0x14001316b  mov     dword ptr [rax], 16h
0x140013171  jmp     short loc_14001319B
0x140013173  cmp     r8, 10h
0x140013177  jb      short loc_140013185
0x140013179  movups  xmm0, [rsp+38h+var_18]
0x14001317e  movdqu  xmmword ptr [r9], xmm0
0x140013183  jmp     short loc_1400131A0
0x140013185  xor     edx, edx; Val
0x140013187  mov     rcx, r9; void *
0x14001318a  call    memset_0
0x14001318f  call    cs:__imp__o__errno
0x140013195  mov     dword ptr [rax], 22h ; '"'
0x14001319b  call    _invalid_parameter_noinfo
0x1400131a0  add     cs:qword_1400758D0, 10h
0x1400131a8  jmp     short loc_1400131BB
0x1400131aa  neg     ebx
0x1400131ac  sbb     eax, eax
0x1400131ae  and     eax, 83Ah
0x1400131b3  add     eax, 0FFFFF7C1h
0x1400131b8  lock and [rdi], eax
0x1400131bb  lea     rcx, SRWLock; SRWLock
0x1400131c2  call    cs:__imp_ReleaseSRWLockExclusive
0x1400131c8  mov     rbx, [rsp+38h+arg_0]
0x1400131cd  mov     rsi, [rsp+38h+arg_8]
0x1400131d2  add     rsp, 30h
0x1400131d6  pop     rdi
0x1400131d7  retn
```
