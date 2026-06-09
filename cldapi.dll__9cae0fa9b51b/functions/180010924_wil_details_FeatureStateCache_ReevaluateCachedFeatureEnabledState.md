# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x180010924`
- end: `0x180010a36`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `274`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010a80`
- `0x180010cb4`

## callees

- `0x180010924`
- `0x180010a80`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState(
        volatile signed __int32 *a1,
        __int64 a2,
        __int64 a3)
{
  unsigned int v3; // r14d
  signed __int32 v5; // ebx
  __int16 CurrentFeatureEnabledState; // di
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
    LODWORD(v13) = CurrentFeatureEnabledState & 0x9C1 | v9 & 0xFFFFF63E;
  return v13;
}

```

## disassembly

```asm
0x180010924  mov     [rsp+arg_10], rbx
0x180010929  mov     [rsp+arg_18], rbp
0x18001092e  push    rsi
0x18001092f  push    rdi
0x180010930  push    r12
0x180010932  push    r14
0x180010934  push    r15
0x180010936  sub     rsp, 20h
0x18001093a  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x180010941  xor     r14d, r14d
0x180010944  mov     [rsp+48h+arg_0], r14d
0x180010949  mov     r15, r8
0x18001094c  mov     [rsp+48h+arg_8], rdx
0x180010951  mov     rbx, rdx
0x180010954  mov     r12, rcx
0x180010957  test    rax, rax
0x18001095a  jz      short loc_180010964
0x18001095c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010961  mov     r14d, eax
0x180010964  lea     rdx, [rsp+48h+arg_0]
0x180010969  mov     rcx, r15
0x18001096c  call    wil_details_GetCurrentFeatureEnabledState
0x180010971  cmp     byte ptr [r15+1Ch], 0
0x180010976  mov     rdi, rax
0x180010979  jnz     short loc_180010988
0x18001097b  mov     ecx, r14d
0x18001097e  neg     ecx
0x180010980  sbb     ebp, ebp
0x180010982  and     ebp, [rsp+48h+arg_0]
0x180010986  jmp     short loc_18001098C
0x180010988  mov     ebp, [rsp+48h+arg_0]
0x18001098c  mov     dword ptr [rsp+48h+arg_8], ebx
0x180010990  mov     esi, ebx
0x180010992  test    ebp, ebp
0x180010994  jz      short loc_1800109B5
0x180010996  mov     dword ptr [rsp+48h+arg_8], ebx
0x18001099a  test    bl, 2
0x18001099d  jnz     short loc_1800109B5
0x18001099f  and     esi, 0FFFFF63Eh
0x1800109a5  mov     eax, edi
0x1800109a7  and     eax, 9C1h
0x1800109ac  or      esi, eax
0x1800109ae  or      esi, 2
0x1800109b1  mov     dword ptr [rsp+48h+arg_8], esi
0x1800109b5  mov     edx, ebx
0x1800109b7  and     edx, 4
0x1800109ba  jnz     short loc_1800109D5
0x1800109bc  mov     eax, esi
0x1800109be  mov     ecx, edi
0x1800109c0  and     ecx, 400h
0x1800109c6  btr     eax, 0Ah
0x1800109ca  mov     esi, ecx
0x1800109cc  or      esi, eax
0x1800109ce  or      esi, 4
0x1800109d1  mov     dword ptr [rsp+48h+arg_8], esi
0x1800109d5  mov     eax, ebx
0x1800109d7  lock cmpxchg [r12], esi
0x1800109dd  jz      short loc_1800109E3
0x1800109df  mov     ebx, eax
0x1800109e1  jmp     short loc_18001098C
0x1800109e3  test    edx, edx
0x1800109e5  jnz     short loc_180010A03
0x1800109e7  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x1800109ee  test    rax, rax
0x1800109f1  jz      short loc_180010A03
0x1800109f3  movzx   edx, byte ptr [r15+1Ch]
0x1800109f8  mov     r8d, r14d
0x1800109fb  mov     rcx, r12
0x1800109fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a03  test    ebp, ebp
0x180010a05  jnz     short loc_180010A19
0x180010a07  and     esi, 0FFFFF63Eh
0x180010a0d  and     edi, 9C1h
0x180010a13  or      esi, edi
0x180010a15  mov     dword ptr [rsp+48h+arg_8], esi
0x180010a19  mov     rax, [rsp+48h+arg_8]
0x180010a1e  mov     rbx, [rsp+48h+arg_10]
0x180010a23  mov     rbp, [rsp+48h+arg_18]
0x180010a28  add     rsp, 20h
0x180010a2c  pop     r15
0x180010a2e  pop     r14
0x180010a30  pop     r12
0x180010a32  pop     rdi
0x180010a33  pop     rsi
0x180010a34  retn
```
