# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x18000798c`
- end: `0x180007a6e`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `226`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180009fc0`

## callees

- `0x180005a90`
- `0x18000798c`
- `0x180009970`
- `0x18000ad24`

## pseudocode

```c
bool __fastcall wil::details::IsFeatureConfigured(
        wil::details *a1,
        unsigned int a2,
        unsigned __int8 a3,
        int a4,
        _DWORD *a5)
{
  int v5; // edi
  __int64 *v7; // rbx
  __int64 v9; // r9
  unsigned int v11; // r14d
  __int64 v12; // r9
  int v13; // eax
  __int64 v14; // rdx
  bool v15; // di
  char v16; // r8
  unsigned int v17; // [rsp+68h] [rbp+20h] BYREF

  v5 = a3;
  v7 = &`wil::details::IsFeatureConfigured'::`2'::machineStoreProbe;
  if ( a4 )
    v7 = &`wil::details::IsFeatureConfigured'::`2'::userStoreProbe;
  v9 = *(unsigned int *)v7;
  if ( (*(_DWORD *)v7 & 3) == 2 )
    return 0;
  if ( (v9 & 2) != 0 )
    return (unsigned int)wil_QueryFeatureState((__int64)a1, a2, a3, v9, 0, a5) != 0;
  v17 = 1;
  v11 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  v13 = wil_QueryFeatureState((__int64)a1, a2, v5, v12, &v17, a5);
  v14 = v17;
  v15 = v13 != 0;
  v16 = _InterlockedExchange((volatile __int32 *)v7, (v17 != 0) + 6);
  if ( !(_DWORD)v14 && (v16 & 4) == 0 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(v7, v14, v11);
  return v15;
}

```

## disassembly

```asm
0x18000798c  mov     [rsp+arg_0], rbx
0x180007991  mov     [rsp+arg_8], rbp
0x180007996  push    rsi
0x180007997  push    rdi
0x180007998  push    r14
0x18000799a  sub     rsp, 30h
0x18000799e  test    r9d, r9d
0x1800079a1  movzx   edi, r8b
0x1800079a5  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x1800079ac  mov     esi, edx
0x1800079ae  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x1800079b5  mov     rbp, rcx
0x1800079b8  cmovnz  rbx, rax
0x1800079bc  mov     r9d, [rbx]
0x1800079bf  mov     eax, r9d
0x1800079c2  and     al, 3
0x1800079c4  cmp     al, 2
0x1800079c6  jnz     short loc_1800079CF
0x1800079c8  xor     al, al
0x1800079ca  jmp     loc_180007A5B
0x1800079cf  test    r9b, 2
0x1800079d3  jnz     short loc_180007A3B
0x1800079d5  mov     [rsp+48h+arg_18], 1
0x1800079dd  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800079e2  mov     rcx, [rsp+48h+arg_20]
0x1800079e7  mov     r14d, eax
0x1800079ea  mov     [rsp+48h+var_20], rcx
0x1800079ef  lea     rax, [rsp+48h+arg_18]
0x1800079f4  mov     rcx, rbp
0x1800079f7  mov     [rsp+48h+var_28], rax
0x1800079fc  mov     r8d, edi
0x1800079ff  mov     edx, esi
0x180007a01  call    wil_QueryFeatureState
0x180007a06  mov     edx, [rsp+48h+arg_18]
0x180007a0a  test    eax, eax
0x180007a0c  mov     ecx, edx
0x180007a0e  setnz   dil
0x180007a12  neg     ecx
0x180007a14  sbb     r8d, r8d
0x180007a17  neg     r8d
0x180007a1a  add     r8d, 6
0x180007a1e  xchg    r8d, [rbx]
0x180007a21  test    edx, edx
0x180007a23  jnz     short loc_180007A36
0x180007a25  test    r8b, 4
0x180007a29  jnz     short loc_180007A36
0x180007a2b  mov     r8d, r14d
0x180007a2e  mov     rcx, rbx
0x180007a31  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180007a36  mov     al, dil
0x180007a39  jmp     short loc_180007A5B
0x180007a3b  mov     rax, [rsp+48h+arg_20]
0x180007a40  mov     r8d, edi
0x180007a43  mov     [rsp+48h+var_20], rax
0x180007a48  mov     [rsp+48h+var_28], 0
0x180007a51  call    wil_QueryFeatureState
0x180007a56  test    eax, eax
0x180007a58  setnz   al
0x180007a5b  mov     rbx, [rsp+48h+arg_0]
0x180007a60  mov     rbp, [rsp+48h+arg_8]
0x180007a65  add     rsp, 30h
0x180007a69  pop     r14
0x180007a6b  pop     rdi
0x180007a6c  pop     rsi
0x180007a6d  retn
```
