# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x140007a20`
- end: `0x140007af9`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details *, __int64, unsigned __int8, int, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140009ae0`

## callees

- `0x140007508`
- `0x140007a20`
- `0x1400096d0`
- `0x14000ad18`

## pseudocode

```c
bool __fastcall wil::details::IsFeatureConfigured(wil::details *a1, __int64 a2, unsigned __int8 a3, int a4, _DWORD *a5)
{
  unsigned int v5; // edi
  unsigned int v6; // esi
  __int64 *v7; // rbx
  unsigned int v10; // eax
  unsigned int v11; // r14d
  int v12; // eax
  __int64 v13; // rdx
  bool v14; // di
  char v15; // r8
  unsigned int v16; // [rsp+58h] [rbp+20h] BYREF

  v5 = a3;
  v6 = a2;
  v7 = &`wil::details::IsFeatureConfigured'::`2'::machineStoreProbe;
  if ( a4 )
    v7 = &`wil::details::IsFeatureConfigured'::`2'::userStoreProbe;
  if ( (*(_DWORD *)v7 & 3) == 2 )
    return 0;
  if ( (*(_DWORD *)v7 & 2) != 0 )
  {
    *a5 = 1;
    return (unsigned int)wil_RtlStagingConfig_QueryFeatureState(a1, a2, a3, 0) != 0;
  }
  else
  {
    v10 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    v16 = 0;
    v11 = v10;
    *a5 = 1;
    v12 = wil_RtlStagingConfig_QueryFeatureState(a1, v6, v5, &v16);
    v13 = v16;
    v14 = v12 != 0;
    v15 = _InterlockedExchange((volatile __int32 *)v7, (v16 != 0) + 6);
    if ( !(_DWORD)v13 && (v15 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(v7, v13, v11);
    return v14;
  }
}

```

## disassembly

```asm
0x140007a20  mov     [rsp+arg_0], rbx
0x140007a25  mov     [rsp+arg_8], rbp
0x140007a2a  push    rsi
0x140007a2b  push    rdi
0x140007a2c  push    r14
0x140007a2e  sub     rsp, 20h
0x140007a32  test    r9d, r9d
0x140007a35  movzx   edi, r8b
0x140007a39  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x140007a40  mov     esi, edx
0x140007a42  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x140007a49  mov     rbp, rcx
0x140007a4c  cmovnz  rbx, rax
0x140007a50  mov     r9d, [rbx]
0x140007a53  mov     eax, r9d
0x140007a56  and     al, 3
0x140007a58  cmp     al, 2
0x140007a5a  jnz     short loc_140007A63
0x140007a5c  xor     al, al
0x140007a5e  jmp     loc_140007AE6
0x140007a63  test    r9b, 2
0x140007a67  jnz     short loc_140007ACB
0x140007a69  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140007a6e  mov     rcx, [rsp+38h+arg_20]
0x140007a73  lea     r9, [rsp+38h+arg_18]
0x140007a78  mov     r8d, edi
0x140007a7b  mov     [rsp+38h+arg_18], 0
0x140007a83  mov     edx, esi
0x140007a85  mov     r14d, eax
0x140007a88  mov     dword ptr [rcx], 1
0x140007a8e  mov     rcx, rbp
0x140007a91  call    wil_RtlStagingConfig_QueryFeatureState
0x140007a96  mov     edx, [rsp+38h+arg_18]
0x140007a9a  test    eax, eax
0x140007a9c  mov     ecx, edx
0x140007a9e  setnz   dil
0x140007aa2  neg     ecx
0x140007aa4  sbb     r8d, r8d
0x140007aa7  neg     r8d
0x140007aaa  add     r8d, 6
0x140007aae  xchg    r8d, [rbx]
0x140007ab1  test    edx, edx
0x140007ab3  jnz     short loc_140007AC6
0x140007ab5  test    r8b, 4
0x140007ab9  jnz     short loc_140007AC6
0x140007abb  mov     r8d, r14d
0x140007abe  mov     rcx, rbx
0x140007ac1  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140007ac6  mov     al, dil
0x140007ac9  jmp     short loc_140007AE6
0x140007acb  mov     rax, [rsp+38h+arg_20]
0x140007ad0  mov     r8d, edi
0x140007ad3  xor     r9d, r9d
0x140007ad6  mov     dword ptr [rax], 1
0x140007adc  call    wil_RtlStagingConfig_QueryFeatureState
0x140007ae1  test    eax, eax
0x140007ae3  setnz   al
0x140007ae6  mov     rbx, [rsp+38h+arg_0]
0x140007aeb  mov     rbp, [rsp+38h+arg_8]
0x140007af0  add     rsp, 20h
0x140007af4  pop     r14
0x140007af6  pop     rdi
0x140007af7  pop     rsi
0x140007af8  retn
```
