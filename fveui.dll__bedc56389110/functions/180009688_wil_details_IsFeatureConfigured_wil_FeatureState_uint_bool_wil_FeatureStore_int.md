# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x180009688`
- end: `0x180009761`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details *, __int64, unsigned __int8, int, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000c470`

## callees

- `0x1800086f8`
- `0x180009688`
- `0x18000bb98`
- `0x18000e778`

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
0x180009688  mov     [rsp+arg_0], rbx
0x18000968d  mov     [rsp+arg_8], rbp
0x180009692  push    rsi
0x180009693  push    rdi
0x180009694  push    r14
0x180009696  sub     rsp, 20h
0x18000969a  test    r9d, r9d
0x18000969d  movzx   edi, r8b
0x1800096a1  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x1800096a8  mov     esi, edx
0x1800096aa  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x1800096b1  mov     rbp, rcx
0x1800096b4  cmovnz  rbx, rax
0x1800096b8  mov     r9d, [rbx]
0x1800096bb  mov     eax, r9d
0x1800096be  and     al, 3
0x1800096c0  cmp     al, 2
0x1800096c2  jnz     short loc_1800096CB
0x1800096c4  xor     al, al
0x1800096c6  jmp     loc_18000974E
0x1800096cb  test    r9b, 2
0x1800096cf  jnz     short loc_180009733
0x1800096d1  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800096d6  mov     rcx, [rsp+38h+arg_20]
0x1800096db  lea     r9, [rsp+38h+arg_18]
0x1800096e0  mov     r8d, edi
0x1800096e3  mov     [rsp+38h+arg_18], 0
0x1800096eb  mov     edx, esi
0x1800096ed  mov     r14d, eax
0x1800096f0  mov     dword ptr [rcx], 1
0x1800096f6  mov     rcx, rbp
0x1800096f9  call    wil_RtlStagingConfig_QueryFeatureState
0x1800096fe  mov     edx, [rsp+38h+arg_18]
0x180009702  test    eax, eax
0x180009704  mov     ecx, edx
0x180009706  setnz   dil
0x18000970a  neg     ecx
0x18000970c  sbb     r8d, r8d
0x18000970f  neg     r8d
0x180009712  add     r8d, 6
0x180009716  xchg    r8d, [rbx]
0x180009719  test    edx, edx
0x18000971b  jnz     short loc_18000972E
0x18000971d  test    r8b, 4
0x180009721  jnz     short loc_18000972E
0x180009723  mov     r8d, r14d
0x180009726  mov     rcx, rbx
0x180009729  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000972e  mov     al, dil
0x180009731  jmp     short loc_18000974E
0x180009733  mov     rax, [rsp+38h+arg_20]
0x180009738  mov     r8d, edi
0x18000973b  xor     r9d, r9d
0x18000973e  mov     dword ptr [rax], 1
0x180009744  call    wil_RtlStagingConfig_QueryFeatureState
0x180009749  test    eax, eax
0x18000974b  setnz   al
0x18000974e  mov     rbx, [rsp+38h+arg_0]
0x180009753  mov     rbp, [rsp+38h+arg_8]
0x180009758  add     rsp, 20h
0x18000975c  pop     r14
0x18000975e  pop     rdi
0x18000975f  pop     rsi
0x180009760  retn
```
