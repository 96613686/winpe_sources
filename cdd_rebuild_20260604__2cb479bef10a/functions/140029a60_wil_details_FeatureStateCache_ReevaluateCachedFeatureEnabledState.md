# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x140029a60`
- end: `0x140029b73`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `275`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140029528`
- `0x140032734`

## callees

- `0x140029a60`
- `0x140029bd0`
- `0x1400372d0`

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
0x140029a60  mov     [rsp+arg_10], rbx
0x140029a65  mov     [rsp+arg_18], rbp
0x140029a6a  push    rsi
0x140029a6b  push    rdi
0x140029a6c  push    r12
0x140029a6e  push    r14
0x140029a70  push    r15
0x140029a72  sub     rsp, 20h
0x140029a76  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x140029a7d  xor     r14d, r14d
0x140029a80  mov     [rsp+48h+arg_0], r14d
0x140029a85  mov     r15, r8
0x140029a88  mov     [rsp+48h+arg_8], rdx
0x140029a8d  mov     rdi, rdx
0x140029a90  mov     r12, rcx
0x140029a93  test    rax, rax
0x140029a96  jz      short loc_140029AA0
0x140029a98  call    _guard_dispatch_icall
0x140029a9d  mov     r14d, eax
0x140029aa0  lea     rdx, [rsp+48h+arg_0]
0x140029aa5  mov     rcx, r15
0x140029aa8  call    wil_details_GetCurrentFeatureEnabledState
0x140029aad  cmp     byte ptr [r15+1Ch], 0
0x140029ab2  mov     rbx, rax
0x140029ab5  jnz     short loc_140029AC4
0x140029ab7  mov     ecx, r14d
0x140029aba  neg     ecx
0x140029abc  sbb     ebp, ebp
0x140029abe  and     ebp, [rsp+48h+arg_0]
0x140029ac2  jmp     short loc_140029AC8
0x140029ac4  mov     ebp, [rsp+48h+arg_0]
0x140029ac8  mov     dword ptr [rsp+48h+arg_8], edi
0x140029acc  mov     esi, edi
0x140029ace  test    ebp, ebp
0x140029ad0  jz      short loc_140029AF2
0x140029ad2  mov     dword ptr [rsp+48h+arg_8], edi
0x140029ad6  test    dil, 2
0x140029ada  jnz     short loc_140029AF2
0x140029adc  and     esi, 0FFFFF63Eh
0x140029ae2  mov     eax, ebx
0x140029ae4  and     eax, 9C1h
0x140029ae9  or      esi, eax
0x140029aeb  or      esi, 2
0x140029aee  mov     dword ptr [rsp+48h+arg_8], esi
0x140029af2  mov     edx, edi
0x140029af4  and     edx, 4
0x140029af7  jnz     short loc_140029B12
0x140029af9  mov     eax, esi
0x140029afb  mov     ecx, ebx
0x140029afd  and     ecx, 400h
0x140029b03  btr     eax, 0Ah
0x140029b07  mov     esi, ecx
0x140029b09  or      esi, eax
0x140029b0b  or      esi, 4
0x140029b0e  mov     dword ptr [rsp+48h+arg_8], esi
0x140029b12  mov     eax, edi
0x140029b14  lock cmpxchg [r12], esi
0x140029b1a  jz      short loc_140029B20
0x140029b1c  mov     edi, eax
0x140029b1e  jmp     short loc_140029AC8
0x140029b20  test    edx, edx
0x140029b22  jnz     short loc_140029B40
0x140029b24  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x140029b2b  test    rax, rax
0x140029b2e  jz      short loc_140029B40
0x140029b30  movzx   edx, byte ptr [r15+1Ch]
0x140029b35  mov     r8d, r14d
0x140029b38  mov     rcx, r12
0x140029b3b  call    _guard_dispatch_icall
0x140029b40  test    ebp, ebp
0x140029b42  jnz     short loc_140029B56
0x140029b44  and     ebx, 9C1h
0x140029b4a  and     esi, 0FFFFF63Eh
0x140029b50  or      ebx, esi
0x140029b52  mov     dword ptr [rsp+48h+arg_8], ebx
0x140029b56  mov     rax, [rsp+48h+arg_8]
0x140029b5b  mov     rbx, [rsp+48h+arg_10]
0x140029b60  mov     rbp, [rsp+48h+arg_18]
0x140029b65  add     rsp, 20h
0x140029b69  pop     r15
0x140029b6b  pop     r14
0x140029b6d  pop     r12
0x140029b6f  pop     rdi
0x140029b70  pop     rsi
0x140029b71  retn
```
