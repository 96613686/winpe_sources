# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)

- ea: `0x140015af8`
- end: `0x140015c20`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `296`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400177b8`

## callees

- `0x14000a020`
- `0x140014c90`
- `0x140015af8`
- `0x1400166a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140015bad`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140015bad`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140015bf5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140015bf5`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // ebp
  __int64 v6; // rcx
  signed __int32 v7; // eax
  __int16 v8; // bx
  bool v9; // zf
  signed __int32 v10; // edx
  unsigned int v11; // ecx
  int v12; // r8d
  _QWORD v14[5]; // [rsp+20h] [rbp-28h] BYREF
  wil::details *v15; // [rsp+50h] [rbp+8h] BYREF
  __int64 v16; // [rsp+58h] [rbp+10h] BYREF

  v15 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_ValLabTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValLabTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
    v7 = *(_DWORD *)a2;
    v8 = v16;
    do
    {
      v9 = (_DWORD)v15 == 0;
      v10 = v7;
      *(_DWORD *)a2 = v7;
      v11 = v7;
      if ( !v9 && (v7 & 2) == 0 )
      {
        v11 = v8 & 0x9C1 | v7 & 0xFFFFF63E | 2;
        *(_DWORD *)a2 = v11;
      }
      v12 = v7 & 4;
      if ( (v7 & 4) == 0 )
      {
        v11 = v8 & 0x400 | v11 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v11;
      }
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValLabTest__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_140029DD8);
      if ( !v5
        || v5 != dword_140029DEC
        || (v14[0] = 3,
            v14[1] = Feature_ValLabTest__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_140029E10, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_ValLabTest__descriptor, 0xFFFFFFFB);
      }
      ReleaseSRWLockExclusive(&stru_140029DD8);
    }
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x140015af8  mov     [rsp+arg_10], rbx
0x140015afd  mov     [rsp+arg_0], rcx
0x140015b02  push    rbp
0x140015b03  push    rsi
0x140015b04  push    rdi
0x140015b05  sub     rsp, 30h
0x140015b09  mov     rsi, cs:Feature_ValLabTest__descriptor
0x140015b10  mov     rdi, rdx
0x140015b13  mov     qword ptr [rdx], 0
0x140015b1a  mov     eax, [rsi]
0x140015b1c  mov     [rdx], eax
0x140015b1e  and     eax, 6
0x140015b21  cmp     al, 6
0x140015b23  jz      loc_140015C10
0x140015b29  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140015b2e  lea     r8, [rsp+48h+arg_0]
0x140015b33  mov     dword ptr [rsp+48h+arg_0], 0
0x140015b3b  lea     rdx, [rsp+48h+arg_8]
0x140015b40  mov     ebp, eax
0x140015b42  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCurrentFeatureEnabledState(int *)
0x140015b47  mov     eax, [rdi]
0x140015b49  mov     rbx, [rsp+48h+arg_8]
0x140015b4e  cmp     dword ptr [rsp+48h+arg_0], 0
0x140015b53  mov     edx, eax
0x140015b55  mov     [rdi], eax
0x140015b57  mov     ecx, eax
0x140015b59  jz      short loc_140015B74
0x140015b5b  test    dl, 2
0x140015b5e  jnz     short loc_140015B74
0x140015b60  and     ecx, 0FFFFF63Eh
0x140015b66  mov     eax, ebx
0x140015b68  and     eax, 9C1h
0x140015b6d  or      ecx, eax
0x140015b6f  or      ecx, 2
0x140015b72  mov     [rdi], ecx
0x140015b74  mov     r8d, edx
0x140015b77  and     r8d, 4
0x140015b7b  jnz     short loc_140015B8F
0x140015b7d  btr     ecx, 0Ah
0x140015b81  mov     eax, ebx
0x140015b83  and     eax, 400h
0x140015b88  or      ecx, eax
0x140015b8a  or      ecx, 4
0x140015b8d  mov     [rdi], ecx
0x140015b8f  mov     eax, edx
0x140015b91  lock cmpxchg [rsi], ecx
0x140015b95  jnz     short loc_140015B4E
0x140015b97  test    r8d, r8d
0x140015b9a  jnz     short loc_140015BFB
0x140015b9c  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x140015ba2  test    eax, eax
0x140015ba4  jz      short loc_140015BFB
0x140015ba6  lea     rcx, stru_140029DD8; SRWLock
0x140015bad  call    cs:__imp_AcquireSRWLockExclusive
0x140015bb3  mov     eax, cs:dword_140029DEC
0x140015bb9  test    ebp, ebp
0x140015bbb  jz      short loc_140015BEA
0x140015bbd  cmp     ebp, eax
0x140015bbf  jnz     short loc_140015BEA
0x140015bc1  mov     r8d, 10h; unsigned __int64
0x140015bc7  mov     [rsp+48h+var_28], 3
0x140015bd0  lea     rdx, [rsp+48h+var_28]; void *
0x140015bd5  mov     [rsp+48h+var_20], rsi
0x140015bda  lea     rcx, qword_140029E10; this
0x140015be1  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x140015be6  test    al, al
0x140015be8  jnz     short loc_140015BEE
0x140015bea  lock and dword ptr [rsi], 0FFFFFFFBh
0x140015bee  lea     rcx, stru_140029DD8; SRWLock
0x140015bf5  call    cs:__imp_ReleaseSRWLockExclusive
0x140015bfb  mov     eax, [rdi]
0x140015bfd  test    al, 2
0x140015bff  jnz     short loc_140015C10
0x140015c01  and     eax, 0FFFFF63Eh
0x140015c06  and     ebx, 9C1h
0x140015c0c  or      eax, ebx
0x140015c0e  mov     [rdi], eax
0x140015c10  mov     rbx, [rsp+48h+arg_10]
0x140015c15  mov     rax, rdi
0x140015c18  add     rsp, 30h
0x140015c1c  pop     rdi
0x140015c1d  pop     rsi
0x140015c1e  pop     rbp
0x140015c1f  retn
```
