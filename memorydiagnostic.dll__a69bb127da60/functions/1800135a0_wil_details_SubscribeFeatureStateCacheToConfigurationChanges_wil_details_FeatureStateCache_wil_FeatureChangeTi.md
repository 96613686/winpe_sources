# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x1800135a0`
- end: `0x1800136a4`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `260`
- prototype: `void __fastcall(volatile signed __int32 *, unsigned int, int)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000c384`
- `0x18000c464`
- `0x18000c544`
- `0x18000c6c4`
- `0x18000dbf4`

## callees

- `0x1800038c6`
- `0x180003940`
- `0x1800135a0`
- `0x180015d60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180013631`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001365b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180013631`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001365b`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800135cc`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800135cc`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001368e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001368e`

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
      || a3 != dword_18002F4B4
      || (*(_QWORD *)&v12 = a2,
          *((_QWORD *)&v12 + 1) = a1,
          !wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_18002F4D8, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
      goto LABEL_13;
    }
    v8 = (qword_18002F4E8 - (_QWORD)qword_18002F4E0) & -(__int64)((unsigned __int64)qword_18002F4E0 < qword_18002F4E8);
    if ( qword_18002F4E0 )
    {
      if ( v8 >= 0x10 )
      {
        *(_OWORD *)qword_18002F4E0 = v12;
LABEL_11:
        qword_18002F4E0 = (char *)qword_18002F4E0 + 16;
LABEL_13:
        ReleaseSRWLockExclusive(&SRWLock);
        return;
      }
      memset_0(qword_18002F4E0, 0, v8);
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
0x1800135a0  mov     [rsp+arg_0], rbx
0x1800135a5  mov     [rsp+arg_8], rsi
0x1800135aa  push    rdi
0x1800135ab  sub     rsp, 30h
0x1800135af  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800135b5  mov     esi, r8d
0x1800135b8  mov     ebx, edx
0x1800135ba  mov     rdi, rcx
0x1800135bd  test    eax, eax
0x1800135bf  jz      loc_180013694
0x1800135c5  lea     rcx, SRWLock; SRWLock
0x1800135cc  call    cs:__imp_AcquireSRWLockExclusive
0x1800135d2  mov     eax, cs:dword_18002F4B4
0x1800135d8  test    esi, esi
0x1800135da  jz      loc_180013676
0x1800135e0  cmp     esi, eax
0x1800135e2  jnz     loc_180013676
0x1800135e8  mov     edx, 10h; unsigned __int64
0x1800135ed  mov     dword ptr [rsp+38h+var_18+4], 0
0x1800135f5  lea     rcx, qword_18002F4D8; this
0x1800135fc  mov     dword ptr [rsp+38h+var_18], ebx
0x180013600  mov     qword ptr [rsp+38h+var_18+8], rdi
0x180013605  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18001360a  test    al, al
0x18001360c  jz      short loc_180013676
0x18001360e  mov     r9, cs:qword_18002F4E0
0x180013615  mov     rax, cs:qword_18002F4E8
0x18001361c  sub     rax, r9
0x18001361f  cmp     r9, cs:qword_18002F4E8
0x180013626  sbb     r8, r8
0x180013629  and     r8, rax; Size
0x18001362c  test    r9, r9
0x18001362f  jnz     short loc_18001363F
0x180013631  call    cs:__imp__o__errno
0x180013637  mov     dword ptr [rax], 16h
0x18001363d  jmp     short loc_180013667
0x18001363f  cmp     r8, 10h
0x180013643  jb      short loc_180013651
0x180013645  movups  xmm0, [rsp+38h+var_18]
0x18001364a  movdqu  xmmword ptr [r9], xmm0
0x18001364f  jmp     short loc_18001366C
0x180013651  xor     edx, edx; Val
0x180013653  mov     rcx, r9; void *
0x180013656  call    memset_0
0x18001365b  call    cs:__imp__o__errno
0x180013661  mov     dword ptr [rax], 22h ; '"'
0x180013667  call    _invalid_parameter_noinfo
0x18001366c  add     cs:qword_18002F4E0, 10h
0x180013674  jmp     short loc_180013687
0x180013676  neg     ebx
0x180013678  sbb     eax, eax
0x18001367a  and     eax, 83Ah
0x18001367f  add     eax, 0FFFFF7C1h
0x180013684  lock and [rdi], eax
0x180013687  lea     rcx, SRWLock; SRWLock
0x18001368e  call    cs:__imp_ReleaseSRWLockExclusive
0x180013694  mov     rbx, [rsp+38h+arg_0]
0x180013699  mov     rsi, [rsp+38h+arg_8]
0x18001369e  add     rsp, 30h
0x1800136a2  pop     rdi
0x1800136a3  retn
```
