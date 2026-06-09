# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(void)

- ea: `0x1400159c8`
- end: `0x140015af0`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `296`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140017730`
- `0x140017ff4`

## callees

- `0x14000a020`
- `0x140014c90`
- `0x1400159c8`
- `0x1400165d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140015a7d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140015a7d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140015ac5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140015ac5`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ValAccTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValAccTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValAccTest__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_140029DD8);
      if ( !v5
        || v5 != dword_140029DEC
        || (v14[0] = 3,
            v14[1] = Feature_ValAccTest__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_140029E10, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_ValAccTest__descriptor, 0xFFFFFFFB);
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
0x1400159c8  mov     [rsp+arg_10], rbx
0x1400159cd  mov     [rsp+arg_0], rcx
0x1400159d2  push    rbp
0x1400159d3  push    rsi
0x1400159d4  push    rdi
0x1400159d5  sub     rsp, 30h
0x1400159d9  mov     rsi, cs:Feature_ValAccTest__descriptor
0x1400159e0  mov     rdi, rdx
0x1400159e3  mov     qword ptr [rdx], 0
0x1400159ea  mov     eax, [rsi]
0x1400159ec  mov     [rdx], eax
0x1400159ee  and     eax, 6
0x1400159f1  cmp     al, 6
0x1400159f3  jz      loc_140015AE0
0x1400159f9  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1400159fe  lea     r8, [rsp+48h+arg_0]
0x140015a03  mov     dword ptr [rsp+48h+arg_0], 0
0x140015a0b  lea     rdx, [rsp+48h+arg_8]
0x140015a10  mov     ebp, eax
0x140015a12  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)
0x140015a17  mov     eax, [rdi]
0x140015a19  mov     rbx, [rsp+48h+arg_8]
0x140015a1e  cmp     dword ptr [rsp+48h+arg_0], 0
0x140015a23  mov     edx, eax
0x140015a25  mov     [rdi], eax
0x140015a27  mov     ecx, eax
0x140015a29  jz      short loc_140015A44
0x140015a2b  test    dl, 2
0x140015a2e  jnz     short loc_140015A44
0x140015a30  and     ecx, 0FFFFF63Eh
0x140015a36  mov     eax, ebx
0x140015a38  and     eax, 9C1h
0x140015a3d  or      ecx, eax
0x140015a3f  or      ecx, 2
0x140015a42  mov     [rdi], ecx
0x140015a44  mov     r8d, edx
0x140015a47  and     r8d, 4
0x140015a4b  jnz     short loc_140015A5F
0x140015a4d  btr     ecx, 0Ah
0x140015a51  mov     eax, ebx
0x140015a53  and     eax, 400h
0x140015a58  or      ecx, eax
0x140015a5a  or      ecx, 4
0x140015a5d  mov     [rdi], ecx
0x140015a5f  mov     eax, edx
0x140015a61  lock cmpxchg [rsi], ecx
0x140015a65  jnz     short loc_140015A1E
0x140015a67  test    r8d, r8d
0x140015a6a  jnz     short loc_140015ACB
0x140015a6c  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x140015a72  test    eax, eax
0x140015a74  jz      short loc_140015ACB
0x140015a76  lea     rcx, stru_140029DD8; SRWLock
0x140015a7d  call    cs:__imp_AcquireSRWLockExclusive
0x140015a83  mov     eax, cs:dword_140029DEC
0x140015a89  test    ebp, ebp
0x140015a8b  jz      short loc_140015ABA
0x140015a8d  cmp     ebp, eax
0x140015a8f  jnz     short loc_140015ABA
0x140015a91  mov     r8d, 10h; unsigned __int64
0x140015a97  mov     [rsp+48h+var_28], 3
0x140015aa0  lea     rdx, [rsp+48h+var_28]; void *
0x140015aa5  mov     [rsp+48h+var_20], rsi
0x140015aaa  lea     rcx, qword_140029E10; this
0x140015ab1  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x140015ab6  test    al, al
0x140015ab8  jnz     short loc_140015ABE
0x140015aba  lock and dword ptr [rsi], 0FFFFFFFBh
0x140015abe  lea     rcx, stru_140029DD8; SRWLock
0x140015ac5  call    cs:__imp_ReleaseSRWLockExclusive
0x140015acb  mov     eax, [rdi]
0x140015acd  test    al, 2
0x140015acf  jnz     short loc_140015AE0
0x140015ad1  and     eax, 0FFFFF63Eh
0x140015ad6  and     ebx, 9C1h
0x140015adc  or      eax, ebx
0x140015ade  mov     [rdi], eax
0x140015ae0  mov     rbx, [rsp+48h+arg_10]
0x140015ae5  mov     rax, rdi
0x140015ae8  add     rsp, 30h
0x140015aec  pop     rdi
0x140015aed  pop     rsi
0x140015aee  pop     rbp
0x140015aef  retn
```
