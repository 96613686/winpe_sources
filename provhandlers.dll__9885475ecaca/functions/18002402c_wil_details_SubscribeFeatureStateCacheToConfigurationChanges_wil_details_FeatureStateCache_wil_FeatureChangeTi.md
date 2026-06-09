# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x18002402c`
- end: `0x1800240f7`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `203`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180017abc`
- `0x180018548`

## callees

- `0x18002402c`
- `0x180024b74`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800240ba`
- `msvcrt!memcpy_s` at `0x1800240ba`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180024058`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180024058`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800240e1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800240e1`

## pseudocode

```c
void __fastcall wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        volatile signed __int32 *a1,
        int a2,
        int a3)
{
  _DWORD Source[2]; // [rsp+20h] [rbp-18h] BYREF
  volatile signed __int32 *v7; // [rsp+28h] [rbp-10h]

  if ( wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&stru_180052628);
    if ( a3
      && a3 == dword_18005263C
      && (Source[1] = 0,
          Source[0] = a2,
          v7 = a1,
          wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_180052660, 0x10u)) )
    {
      memcpy_s(
        Destination,
        (qword_180052670 - (_QWORD)Destination) & -(__int64)((unsigned __int64)Destination < qword_180052670),
        Source,
        0x10u);
      Destination = (char *)Destination + 16;
    }
    else
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    ReleaseSRWLockExclusive(&stru_180052628);
  }
}

```

## disassembly

```asm
0x18002402c  mov     [rsp+arg_0], rbx
0x180024031  mov     [rsp+arg_8], rsi
0x180024036  push    rdi
0x180024037  sub     rsp, 30h
0x18002403b  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180024041  mov     esi, r8d
0x180024044  mov     ebx, edx
0x180024046  mov     rdi, rcx
0x180024049  test    eax, eax
0x18002404b  jz      loc_1800240E7
0x180024051  lea     rcx, stru_180052628; SRWLock
0x180024058  call    cs:__imp_AcquireSRWLockExclusive
0x18002405e  mov     eax, cs:dword_18005263C
0x180024064  test    esi, esi
0x180024066  jz      short loc_1800240C9
0x180024068  cmp     esi, eax
0x18002406a  jnz     short loc_1800240C9
0x18002406c  mov     esi, 10h
0x180024071  mov     [rsp+38h+var_14], 0
0x180024079  mov     edx, esi; unsigned __int64
0x18002407b  mov     [rsp+38h+Source], ebx
0x18002407f  lea     rcx, qword_180052660; this
0x180024086  mov     [rsp+38h+var_10], rdi
0x18002408b  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180024090  test    al, al
0x180024092  jz      short loc_1800240C9
0x180024094  mov     rcx, cs:Destination; Destination
0x18002409b  lea     r8, [rsp+38h+Source]; Source
0x1800240a0  mov     rax, cs:qword_180052670
0x1800240a7  mov     r9d, esi; SourceSize
0x1800240aa  sub     rax, rcx
0x1800240ad  cmp     rcx, cs:qword_180052670
0x1800240b4  sbb     rdx, rdx
0x1800240b7  and     rdx, rax; DestinationSize
0x1800240ba  call    cs:__imp_memcpy_s
0x1800240c0  add     cs:Destination, rsi
0x1800240c7  jmp     short loc_1800240DA
0x1800240c9  neg     ebx
0x1800240cb  sbb     eax, eax
0x1800240cd  and     eax, 83Ah
0x1800240d2  add     eax, 0FFFFF7C1h
0x1800240d7  lock and [rdi], eax
0x1800240da  lea     rcx, stru_180052628; SRWLock
0x1800240e1  call    cs:__imp_ReleaseSRWLockExclusive
0x1800240e7  mov     rbx, [rsp+38h+arg_0]
0x1800240ec  mov     rsi, [rsp+38h+arg_8]
0x1800240f1  add     rsp, 30h
0x1800240f5  pop     rdi
0x1800240f6  retn
```
