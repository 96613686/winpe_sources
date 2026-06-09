# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x140005fe0`
- end: `0x1400060c3`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140009810`

## callees

- `0x140004d88`
- `0x140005fe0`
- `0x140008f34`
- `0x14000b0ac`

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
  int v11; // r14d
  __int64 v12; // r9
  int v13; // eax
  int v14; // edx
  bool v15; // di
  char v16; // r8
  int v17; // [rsp+68h] [rbp+20h] BYREF

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
  if ( !v14 && (v16 & 4) == 0 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges((volatile signed __int32 *)v7, 0, v11);
  return v15;
}

```

## disassembly

```asm
0x140005fe0  mov     [rsp+arg_0], rbx
0x140005fe5  mov     [rsp+arg_8], rbp
0x140005fea  push    rsi
0x140005feb  push    rdi
0x140005fec  push    r14
0x140005fee  sub     rsp, 30h
0x140005ff2  test    r9d, r9d
0x140005ff5  movzx   edi, r8b
0x140005ff9  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x140006000  mov     esi, edx
0x140006002  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x140006009  mov     rbp, rcx
0x14000600c  cmovnz  rbx, rax
0x140006010  mov     r9d, [rbx]
0x140006013  mov     eax, r9d
0x140006016  and     al, 3
0x140006018  cmp     al, 2
0x14000601a  jnz     short loc_140006023
0x14000601c  xor     al, al
0x14000601e  jmp     loc_1400060AF
0x140006023  test    r9b, 2
0x140006027  jnz     short loc_14000608F
0x140006029  mov     [rsp+48h+arg_18], 1
0x140006031  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140006036  mov     rcx, [rsp+48h+arg_20]
0x14000603b  mov     r14d, eax
0x14000603e  mov     [rsp+48h+var_20], rcx
0x140006043  lea     rax, [rsp+48h+arg_18]
0x140006048  mov     rcx, rbp
0x14000604b  mov     [rsp+48h+var_28], rax
0x140006050  mov     r8d, edi
0x140006053  mov     edx, esi
0x140006055  call    wil_QueryFeatureState
0x14000605a  mov     edx, [rsp+48h+arg_18]
0x14000605e  test    eax, eax
0x140006060  mov     ecx, edx
0x140006062  setnz   dil
0x140006066  neg     ecx
0x140006068  sbb     r8d, r8d
0x14000606b  neg     r8d
0x14000606e  add     r8d, 6
0x140006072  xchg    r8d, [rbx]
0x140006075  test    edx, edx
0x140006077  jnz     short loc_14000608A
0x140006079  test    r8b, 4
0x14000607d  jnz     short loc_14000608A
0x14000607f  mov     r8d, r14d
0x140006082  mov     rcx, rbx
0x140006085  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x14000608a  mov     al, dil
0x14000608d  jmp     short loc_1400060AF
0x14000608f  mov     rax, [rsp+48h+arg_20]
0x140006094  mov     r8d, edi
0x140006097  mov     [rsp+48h+var_20], rax
0x14000609c  mov     [rsp+48h+var_28], 0
0x1400060a5  call    wil_QueryFeatureState
0x1400060aa  test    eax, eax
0x1400060ac  setnz   al
0x1400060af  mov     rbx, [rsp+48h+arg_0]
0x1400060b4  mov     rbp, [rsp+48h+arg_8]
0x1400060b9  add     rsp, 30h
0x1400060bd  pop     r14
0x1400060bf  pop     rdi
0x1400060c0  pop     rsi
0x1400060c1  retn
```
