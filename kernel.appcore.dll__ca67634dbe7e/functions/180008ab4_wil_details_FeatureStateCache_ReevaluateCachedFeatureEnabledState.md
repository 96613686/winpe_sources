# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x180008ab4`
- end: `0x180008bc5`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `273`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005dc4`
- `0x18000854c`

## callees

- `0x180008ab4`
- `0x180008c20`
- `0x18000a010`

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
0x180008ab4  mov     [rsp+arg_10], rbx
0x180008ab9  mov     [rsp+arg_18], rbp
0x180008abe  push    rsi
0x180008abf  push    rdi
0x180008ac0  push    r12
0x180008ac2  push    r14
0x180008ac4  push    r15
0x180008ac6  sub     rsp, 20h
0x180008aca  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x180008ad1  xor     r14d, r14d
0x180008ad4  mov     [rsp+48h+arg_0], r14d
0x180008ad9  mov     r15, r8
0x180008adc  mov     [rsp+48h+arg_8], rdx
0x180008ae1  mov     rbx, rdx
0x180008ae4  mov     r12, rcx
0x180008ae7  test    rax, rax
0x180008aea  jz      short loc_180008AF4
0x180008aec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008af1  mov     r14d, eax
0x180008af4  lea     rdx, [rsp+48h+arg_0]
0x180008af9  mov     rcx, r15
0x180008afc  call    wil_details_GetCurrentFeatureEnabledState
0x180008b01  cmp     byte ptr [r15+1Ch], 0
0x180008b06  mov     rdi, rax
0x180008b09  jnz     short loc_180008B18
0x180008b0b  mov     ecx, r14d
0x180008b0e  neg     ecx
0x180008b10  sbb     ebp, ebp
0x180008b12  and     ebp, [rsp+48h+arg_0]
0x180008b16  jmp     short loc_180008B1C
0x180008b18  mov     ebp, [rsp+48h+arg_0]
0x180008b1c  mov     dword ptr [rsp+48h+arg_8], ebx
0x180008b20  mov     esi, ebx
0x180008b22  test    ebp, ebp
0x180008b24  jz      short loc_180008B45
0x180008b26  mov     dword ptr [rsp+48h+arg_8], ebx
0x180008b2a  test    bl, 2
0x180008b2d  jnz     short loc_180008B45
0x180008b2f  and     esi, 0FFFFF63Eh
0x180008b35  mov     eax, edi
0x180008b37  and     eax, 9C1h
0x180008b3c  or      esi, eax
0x180008b3e  or      esi, 2
0x180008b41  mov     dword ptr [rsp+48h+arg_8], esi
0x180008b45  mov     edx, ebx
0x180008b47  and     edx, 4
0x180008b4a  jnz     short loc_180008B65
0x180008b4c  mov     eax, esi
0x180008b4e  mov     ecx, edi
0x180008b50  and     ecx, 400h
0x180008b56  btr     eax, 0Ah
0x180008b5a  mov     esi, ecx
0x180008b5c  or      esi, eax
0x180008b5e  or      esi, 4
0x180008b61  mov     dword ptr [rsp+48h+arg_8], esi
0x180008b65  mov     eax, ebx
0x180008b67  lock cmpxchg [r12], esi
0x180008b6d  jz      short loc_180008B73
0x180008b6f  mov     ebx, eax
0x180008b71  jmp     short loc_180008B1C
0x180008b73  test    edx, edx
0x180008b75  jnz     short loc_180008B93
0x180008b77  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x180008b7e  test    rax, rax
0x180008b81  jz      short loc_180008B93
0x180008b83  movzx   edx, byte ptr [r15+1Ch]
0x180008b88  mov     r8d, r14d
0x180008b8b  mov     rcx, r12
0x180008b8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b93  test    ebp, ebp
0x180008b95  jnz     short loc_180008BA9
0x180008b97  and     esi, 0FFFFF63Eh
0x180008b9d  and     edi, 9C1h
0x180008ba3  or      esi, edi
0x180008ba5  mov     dword ptr [rsp+48h+arg_8], esi
0x180008ba9  mov     rax, [rsp+48h+arg_8]
0x180008bae  mov     rbx, [rsp+48h+arg_10]
0x180008bb3  mov     rbp, [rsp+48h+arg_18]
0x180008bb8  add     rsp, 20h
0x180008bbc  pop     r15
0x180008bbe  pop     r14
0x180008bc0  pop     r12
0x180008bc2  pop     rdi
0x180008bc3  pop     rsi
0x180008bc4  retn
```
