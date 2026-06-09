# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x18001df48`
- end: `0x18001e05a`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `274`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b79c`
- `0x18001e0b4`

## callees

- `0x18001df48`
- `0x18001e0b4`
- `0x180027c80`

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
0x18001df48  mov     [rsp+arg_10], rbx
0x18001df4d  mov     [rsp+arg_18], rbp
0x18001df52  push    rsi
0x18001df53  push    rdi
0x18001df54  push    r12
0x18001df56  push    r14
0x18001df58  push    r15
0x18001df5a  sub     rsp, 20h
0x18001df5e  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x18001df65  xor     r14d, r14d
0x18001df68  mov     [rsp+48h+arg_0], r14d
0x18001df6d  mov     r15, r8
0x18001df70  mov     [rsp+48h+arg_8], rdx
0x18001df75  mov     rbx, rdx
0x18001df78  mov     r12, rcx
0x18001df7b  test    rax, rax
0x18001df7e  jz      short loc_18001DF88
0x18001df80  call    _guard_dispatch_icall
0x18001df85  mov     r14d, eax
0x18001df88  lea     rdx, [rsp+48h+arg_0]
0x18001df8d  mov     rcx, r15
0x18001df90  call    wil_details_GetCurrentFeatureEnabledState
0x18001df95  cmp     byte ptr [r15+1Ch], 0
0x18001df9a  mov     rdi, rax
0x18001df9d  jnz     short loc_18001DFAC
0x18001df9f  mov     ecx, r14d
0x18001dfa2  neg     ecx
0x18001dfa4  sbb     ebp, ebp
0x18001dfa6  and     ebp, [rsp+48h+arg_0]
0x18001dfaa  jmp     short loc_18001DFB0
0x18001dfac  mov     ebp, [rsp+48h+arg_0]
0x18001dfb0  mov     dword ptr [rsp+48h+arg_8], ebx
0x18001dfb4  mov     esi, ebx
0x18001dfb6  test    ebp, ebp
0x18001dfb8  jz      short loc_18001DFD9
0x18001dfba  mov     dword ptr [rsp+48h+arg_8], ebx
0x18001dfbe  test    bl, 2
0x18001dfc1  jnz     short loc_18001DFD9
0x18001dfc3  and     esi, 0FFFFF63Eh
0x18001dfc9  mov     eax, edi
0x18001dfcb  and     eax, 9C1h
0x18001dfd0  or      esi, eax
0x18001dfd2  or      esi, 2
0x18001dfd5  mov     dword ptr [rsp+48h+arg_8], esi
0x18001dfd9  mov     edx, ebx
0x18001dfdb  and     edx, 4
0x18001dfde  jnz     short loc_18001DFF9
0x18001dfe0  mov     eax, esi
0x18001dfe2  mov     ecx, edi
0x18001dfe4  and     ecx, 400h
0x18001dfea  btr     eax, 0Ah
0x18001dfee  mov     esi, ecx
0x18001dff0  or      esi, eax
0x18001dff2  or      esi, 4
0x18001dff5  mov     dword ptr [rsp+48h+arg_8], esi
0x18001dff9  mov     eax, ebx
0x18001dffb  lock cmpxchg [r12], esi
0x18001e001  jz      short loc_18001E007
0x18001e003  mov     ebx, eax
0x18001e005  jmp     short loc_18001DFB0
0x18001e007  test    edx, edx
0x18001e009  jnz     short loc_18001E027
0x18001e00b  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x18001e012  test    rax, rax
0x18001e015  jz      short loc_18001E027
0x18001e017  movzx   edx, byte ptr [r15+1Ch]
0x18001e01c  mov     r8d, r14d
0x18001e01f  mov     rcx, r12
0x18001e022  call    _guard_dispatch_icall
0x18001e027  test    ebp, ebp
0x18001e029  jnz     short loc_18001E03D
0x18001e02b  and     esi, 0FFFFF63Eh
0x18001e031  and     edi, 9C1h
0x18001e037  or      esi, edi
0x18001e039  mov     dword ptr [rsp+48h+arg_8], esi
0x18001e03d  mov     rax, [rsp+48h+arg_8]
0x18001e042  mov     rbx, [rsp+48h+arg_10]
0x18001e047  mov     rbp, [rsp+48h+arg_18]
0x18001e04c  add     rsp, 20h
0x18001e050  pop     r15
0x18001e052  pop     r14
0x18001e054  pop     r12
0x18001e056  pop     rdi
0x18001e057  pop     rsi
0x18001e058  retn
```
