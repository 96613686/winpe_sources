# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x18000916c`
- end: `0x180009245`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details *, __int64, unsigned __int8, int, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000be20`

## callees

- `0x1800084a8`
- `0x18000916c`
- `0x18000b604`
- `0x18000d574`

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
0x18000916c  mov     [rsp+arg_0], rbx
0x180009171  mov     [rsp+arg_8], rbp
0x180009176  push    rsi
0x180009177  push    rdi
0x180009178  push    r14
0x18000917a  sub     rsp, 20h
0x18000917e  test    r9d, r9d
0x180009181  movzx   edi, r8b
0x180009185  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x18000918c  mov     esi, edx
0x18000918e  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x180009195  mov     rbp, rcx
0x180009198  cmovnz  rbx, rax
0x18000919c  mov     r9d, [rbx]
0x18000919f  mov     eax, r9d
0x1800091a2  and     al, 3
0x1800091a4  cmp     al, 2
0x1800091a6  jnz     short loc_1800091AF
0x1800091a8  xor     al, al
0x1800091aa  jmp     loc_180009232
0x1800091af  test    r9b, 2
0x1800091b3  jnz     short loc_180009217
0x1800091b5  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800091ba  mov     rcx, [rsp+38h+arg_20]
0x1800091bf  lea     r9, [rsp+38h+arg_18]
0x1800091c4  mov     r8d, edi
0x1800091c7  mov     [rsp+38h+arg_18], 0
0x1800091cf  mov     edx, esi
0x1800091d1  mov     r14d, eax
0x1800091d4  mov     dword ptr [rcx], 1
0x1800091da  mov     rcx, rbp
0x1800091dd  call    wil_RtlStagingConfig_QueryFeatureState
0x1800091e2  mov     edx, [rsp+38h+arg_18]
0x1800091e6  test    eax, eax
0x1800091e8  mov     ecx, edx
0x1800091ea  setnz   dil
0x1800091ee  neg     ecx
0x1800091f0  sbb     r8d, r8d
0x1800091f3  neg     r8d
0x1800091f6  add     r8d, 6
0x1800091fa  xchg    r8d, [rbx]
0x1800091fd  test    edx, edx
0x1800091ff  jnz     short loc_180009212
0x180009201  test    r8b, 4
0x180009205  jnz     short loc_180009212
0x180009207  mov     r8d, r14d
0x18000920a  mov     rcx, rbx
0x18000920d  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180009212  mov     al, dil
0x180009215  jmp     short loc_180009232
0x180009217  mov     rax, [rsp+38h+arg_20]
0x18000921c  mov     r8d, edi
0x18000921f  xor     r9d, r9d
0x180009222  mov     dword ptr [rax], 1
0x180009228  call    wil_RtlStagingConfig_QueryFeatureState
0x18000922d  test    eax, eax
0x18000922f  setnz   al
0x180009232  mov     rbx, [rsp+38h+arg_0]
0x180009237  mov     rbp, [rsp+38h+arg_8]
0x18000923c  add     rsp, 20h
0x180009240  pop     r14
0x180009242  pop     rdi
0x180009243  pop     rsi
0x180009244  retn
```
