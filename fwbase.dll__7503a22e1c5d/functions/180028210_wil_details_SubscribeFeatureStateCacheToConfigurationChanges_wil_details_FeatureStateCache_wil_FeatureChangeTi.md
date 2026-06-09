# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180028210`
- end: `0x18002832a`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `282`
- prototype: ``
- caller_count: `7`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180023f10`
- `0x180024120`
- `0x180025030`
- `0x18002cef0`
- `0x18002d0d0`
- `0x18002d2e0`
- `0x18002d4e0`

## callees

- `0x18001eae6`
- `0x18001eb54`
- `0x180028210`
- `0x180029710`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800282a2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800282e0`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800282a2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800282e0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002823c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002823c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180028314`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180028314`

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
  unsigned int v12; // eax
  __int128 v13; // [rsp+20h] [rbp-18h]

  if ( wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( a3
      && a3 == dword_18003C42C
      && (*(_QWORD *)&v13 = a2,
          *((_QWORD *)&v13 + 1) = a1,
          wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_18003C450, 0x10u)) )
    {
      v8 = 0;
      if ( (unsigned __int64)qword_18003C458 < qword_18003C460 )
        v8 = qword_18003C460 - (_QWORD)qword_18003C458;
      if ( qword_18003C458 )
      {
        if ( v8 < 0x10 )
        {
          memset_0(qword_18003C458, 0, v8);
          *(_DWORD *)_o__errno(v10, v9, v11) = 34;
          invalid_parameter_noinfo();
        }
        else
        {
          *(_OWORD *)qword_18003C458 = v13;
        }
        qword_18003C458 = (char *)qword_18003C458 + 16;
      }
      else
      {
        *(_DWORD *)_o__errno(v7, v6, v8) = 22;
        invalid_parameter_noinfo();
        qword_18003C458 = (char *)qword_18003C458 + 16;
      }
    }
    else
    {
      v12 = -2111;
      if ( a2 )
        v12 = -5;
      _InterlockedAnd(a1, v12);
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
}

```

## disassembly

```asm
0x180028210  mov     [rsp+arg_10], rbx
0x180028215  mov     [rsp+arg_18], rsi
0x18002821a  push    rdi
0x18002821b  sub     rsp, 30h
0x18002821f  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180028225  mov     edi, r8d
0x180028228  mov     esi, edx
0x18002822a  mov     rbx, rcx
0x18002822d  test    eax, eax
0x18002822f  jz      loc_18002831A
0x180028235  lea     rcx, SRWLock; SRWLock
0x18002823c  call    cs:__imp_AcquireSRWLockExclusive
0x180028242  mov     eax, cs:dword_18003C42C
0x180028248  test    edi, edi
0x18002824a  jz      loc_1800282FB
0x180028250  cmp     edi, eax
0x180028252  jnz     loc_1800282FB
0x180028258  mov     edx, 10h; unsigned __int64
0x18002825d  mov     dword ptr [rsp+38h+var_18+4], 0
0x180028265  lea     rcx, qword_18003C450; this
0x18002826c  mov     dword ptr [rsp+38h+var_18], esi
0x180028270  mov     qword ptr [rsp+38h+var_18+8], rbx
0x180028275  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18002827a  test    al, al
0x18002827c  jz      short loc_1800282FB
0x18002827e  mov     r9, cs:qword_18003C458
0x180028285  xor     r8d, r8d
0x180028288  mov     rax, cs:qword_18003C460
0x18002828f  sub     rax, r9
0x180028292  cmp     r9, cs:qword_18003C460
0x180028299  cmovb   r8, rax; Size
0x18002829d  test    r9, r9
0x1800282a0  jnz     short loc_1800282BD
0x1800282a2  call    cs:__imp__o__errno
0x1800282a8  mov     dword ptr [rax], 16h
0x1800282ae  call    _invalid_parameter_noinfo
0x1800282b3  add     cs:qword_18003C458, 10h
0x1800282bb  jmp     short loc_18002830D
0x1800282bd  cmp     r8, 10h
0x1800282c1  jb      short loc_1800282D6
0x1800282c3  movups  xmm0, [rsp+38h+var_18]
0x1800282c8  movups  xmmword ptr [r9], xmm0
0x1800282cc  add     cs:qword_18003C458, 10h
0x1800282d4  jmp     short loc_18002830D
0x1800282d6  xor     edx, edx; Val
0x1800282d8  mov     rcx, r9; void *
0x1800282db  call    memset_0
0x1800282e0  call    cs:__imp__o__errno
0x1800282e6  mov     dword ptr [rax], 22h ; '"'
0x1800282ec  call    _invalid_parameter_noinfo
0x1800282f1  add     cs:qword_18003C458, 10h
0x1800282f9  jmp     short loc_18002830D
0x1800282fb  test    esi, esi
0x1800282fd  mov     eax, 0FFFFF7C1h
0x180028302  mov     edx, 0FFFFFFFBh
0x180028307  cmovnz  eax, edx
0x18002830a  lock and [rbx], eax
0x18002830d  lea     rcx, SRWLock; SRWLock
0x180028314  call    cs:__imp_ReleaseSRWLockExclusive
0x18002831a  mov     rbx, [rsp+38h+arg_10]
0x18002831f  mov     rsi, [rsp+38h+arg_18]
0x180028324  add     rsp, 30h
0x180028328  pop     rdi
0x180028329  retn
```
