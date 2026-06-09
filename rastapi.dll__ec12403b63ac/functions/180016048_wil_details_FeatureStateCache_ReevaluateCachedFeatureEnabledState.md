# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x180016048`
- end: `0x18001615a`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `274`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800161a4`
- `0x1800163f0`

## callees

- `0x180016048`
- `0x1800161a4`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState(
        volatile signed __int32 *a1,
        __int64 a2,
        __int64 a3)
{
  unsigned int v3; // r14d
  signed __int32 v5; // edi
  __int16 CurrentFeatureEnabledState; // bx
  int v8; // ebp
  unsigned int v9; // esi
  signed __int32 v10; // eax
  int v12; // [rsp+50h] [rbp+8h] BYREF
  __int64 v13; // [rsp+58h] [rbp+10h]

  v3 = 0;
  v12 = 0;
  v13 = a2;
  v5 = a2;
  if ( g_wil_details_ensureSubscribedToFeatureConfigurationChanges )
    v3 = g_wil_details_ensureSubscribedToFeatureConfigurationChanges();
  CurrentFeatureEnabledState = wil_details_GetCurrentFeatureEnabledState(a3, &v12);
  if ( *(_BYTE *)(a3 + 28) )
    v8 = v12;
  else
    v8 = v3 != 0 ? v12 : 0;
  while ( 1 )
  {
    LODWORD(v13) = v5;
    v9 = v5;
    if ( v8 )
    {
      LODWORD(v13) = v5;
      if ( (v5 & 2) == 0 )
      {
        v9 = CurrentFeatureEnabledState & 0x9C1 | v5 & 0xFFFFF63E | 2;
        LODWORD(v13) = v9;
      }
    }
    if ( (v5 & 4) == 0 )
    {
      v9 = v9 & 0xFFFFFBFF | CurrentFeatureEnabledState & 0x400 | 4;
      LODWORD(v13) = v9;
    }
    v10 = _InterlockedCompareExchange(a1, v9, v5);
    if ( v5 == v10 )
      break;
    v5 = v10;
  }
  if ( (v5 & 4) == 0 && g_wil_details_subscribeFeatureStateCacheToConfigurationChanges )
    g_wil_details_subscribeFeatureStateCacheToConfigurationChanges(a1, *(unsigned __int8 *)(a3 + 28), v3);
  if ( !v8 )
    LODWORD(v13) = v9 & 0xFFFFF63E | CurrentFeatureEnabledState & 0x9C1;
  return v13;
}

```

## disassembly

```asm
0x180016048  mov     [rsp+arg_10], rbx
0x18001604d  mov     [rsp+arg_18], rbp
0x180016052  push    rsi
0x180016053  push    rdi
0x180016054  push    r12
0x180016056  push    r14
0x180016058  push    r15
0x18001605a  sub     rsp, 20h
0x18001605e  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x180016065  xor     r14d, r14d
0x180016068  mov     [rsp+48h+arg_0], r14d
0x18001606d  mov     r15, r8
0x180016070  mov     [rsp+48h+arg_8], rdx
0x180016075  mov     rdi, rdx
0x180016078  mov     r12, rcx
0x18001607b  test    rax, rax
0x18001607e  jz      short loc_180016088
0x180016080  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016085  mov     r14d, eax
0x180016088  lea     rdx, [rsp+48h+arg_0]
0x18001608d  mov     rcx, r15
0x180016090  call    wil_details_GetCurrentFeatureEnabledState
0x180016095  cmp     byte ptr [r15+1Ch], 0
0x18001609a  mov     rbx, rax
0x18001609d  jnz     short loc_1800160AC
0x18001609f  mov     ecx, r14d
0x1800160a2  neg     ecx
0x1800160a4  sbb     ebp, ebp
0x1800160a6  and     ebp, [rsp+48h+arg_0]
0x1800160aa  jmp     short loc_1800160B0
0x1800160ac  mov     ebp, [rsp+48h+arg_0]
0x1800160b0  mov     dword ptr [rsp+48h+arg_8], edi
0x1800160b4  mov     esi, edi
0x1800160b6  test    ebp, ebp
0x1800160b8  jz      short loc_1800160DA
0x1800160ba  mov     dword ptr [rsp+48h+arg_8], edi
0x1800160be  test    dil, 2
0x1800160c2  jnz     short loc_1800160DA
0x1800160c4  and     esi, 0FFFFF63Eh
0x1800160ca  mov     eax, ebx
0x1800160cc  and     eax, 9C1h
0x1800160d1  or      esi, eax
0x1800160d3  or      esi, 2
0x1800160d6  mov     dword ptr [rsp+48h+arg_8], esi
0x1800160da  mov     edx, edi
0x1800160dc  and     edx, 4
0x1800160df  jnz     short loc_1800160FA
0x1800160e1  mov     eax, esi
0x1800160e3  mov     ecx, ebx
0x1800160e5  and     ecx, 400h
0x1800160eb  btr     eax, 0Ah
0x1800160ef  mov     esi, ecx
0x1800160f1  or      esi, eax
0x1800160f3  or      esi, 4
0x1800160f6  mov     dword ptr [rsp+48h+arg_8], esi
0x1800160fa  mov     eax, edi
0x1800160fc  lock cmpxchg [r12], esi
0x180016102  jz      short loc_180016108
0x180016104  mov     edi, eax
0x180016106  jmp     short loc_1800160B0
0x180016108  test    edx, edx
0x18001610a  jnz     short loc_180016128
0x18001610c  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x180016113  test    rax, rax
0x180016116  jz      short loc_180016128
0x180016118  movzx   edx, byte ptr [r15+1Ch]
0x18001611d  mov     r8d, r14d
0x180016120  mov     rcx, r12
0x180016123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016128  test    ebp, ebp
0x18001612a  jnz     short loc_18001613E
0x18001612c  and     ebx, 9C1h
0x180016132  and     esi, 0FFFFF63Eh
0x180016138  or      ebx, esi
0x18001613a  mov     dword ptr [rsp+48h+arg_8], ebx
0x18001613e  mov     rax, [rsp+48h+arg_8]
0x180016143  mov     rbx, [rsp+48h+arg_10]
0x180016148  mov     rbp, [rsp+48h+arg_18]
0x18001614d  add     rsp, 20h
0x180016151  pop     r15
0x180016153  pop     r14
0x180016155  pop     r12
0x180016157  pop     rdi
0x180016158  pop     rsi
0x180016159  retn
```
