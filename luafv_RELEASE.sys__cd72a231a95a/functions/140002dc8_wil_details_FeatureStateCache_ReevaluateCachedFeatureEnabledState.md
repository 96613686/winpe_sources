# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x140002dc8`
- end: `0x140002eda`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `274`
- prototype: `__int64 __fastcall(volatile signed __int32 *, __int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140001b8c`
- `0x140002f34`

## callees

- `0x140002dc8`
- `0x140002f34`
- `0x140005c90`

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
0x140002dc8  mov     [rsp+arg_10], rbx
0x140002dcd  mov     [rsp+arg_18], rbp
0x140002dd2  push    rsi
0x140002dd3  push    rdi
0x140002dd4  push    r12
0x140002dd6  push    r14
0x140002dd8  push    r15
0x140002dda  sub     rsp, 20h
0x140002dde  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x140002de5  xor     r14d, r14d
0x140002de8  mov     [rsp+48h+arg_0], r14d
0x140002ded  mov     r15, r8
0x140002df0  mov     [rsp+48h+arg_8], rdx
0x140002df5  mov     rbx, rdx
0x140002df8  mov     r12, rcx
0x140002dfb  test    rax, rax
0x140002dfe  jz      short loc_140002E08
0x140002e00  call    _guard_dispatch_icall
0x140002e05  mov     r14d, eax
0x140002e08  lea     rdx, [rsp+48h+arg_0]
0x140002e0d  mov     rcx, r15
0x140002e10  call    wil_details_GetCurrentFeatureEnabledState
0x140002e15  cmp     byte ptr [r15+1Ch], 0
0x140002e1a  mov     rdi, rax
0x140002e1d  jnz     short loc_140002E2C
0x140002e1f  mov     ecx, r14d
0x140002e22  neg     ecx
0x140002e24  sbb     ebp, ebp
0x140002e26  and     ebp, [rsp+48h+arg_0]
0x140002e2a  jmp     short loc_140002E30
0x140002e2c  mov     ebp, [rsp+48h+arg_0]
0x140002e30  mov     dword ptr [rsp+48h+arg_8], ebx
0x140002e34  mov     esi, ebx
0x140002e36  test    ebp, ebp
0x140002e38  jz      short loc_140002E59
0x140002e3a  mov     dword ptr [rsp+48h+arg_8], ebx
0x140002e3e  test    bl, 2
0x140002e41  jnz     short loc_140002E59
0x140002e43  and     esi, 0FFFFF63Eh
0x140002e49  mov     eax, edi
0x140002e4b  and     eax, 9C1h
0x140002e50  or      esi, eax
0x140002e52  or      esi, 2
0x140002e55  mov     dword ptr [rsp+48h+arg_8], esi
0x140002e59  mov     edx, ebx
0x140002e5b  and     edx, 4
0x140002e5e  jnz     short loc_140002E79
0x140002e60  mov     eax, esi
0x140002e62  mov     ecx, edi
0x140002e64  and     ecx, 400h
0x140002e6a  btr     eax, 0Ah
0x140002e6e  mov     esi, ecx
0x140002e70  or      esi, eax
0x140002e72  or      esi, 4
0x140002e75  mov     dword ptr [rsp+48h+arg_8], esi
0x140002e79  mov     eax, ebx
0x140002e7b  lock cmpxchg [r12], esi
0x140002e81  jz      short loc_140002E87
0x140002e83  mov     ebx, eax
0x140002e85  jmp     short loc_140002E30
0x140002e87  test    edx, edx
0x140002e89  jnz     short loc_140002EA7
0x140002e8b  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x140002e92  test    rax, rax
0x140002e95  jz      short loc_140002EA7
0x140002e97  movzx   edx, byte ptr [r15+1Ch]
0x140002e9c  mov     r8d, r14d
0x140002e9f  mov     rcx, r12
0x140002ea2  call    _guard_dispatch_icall
0x140002ea7  test    ebp, ebp
0x140002ea9  jnz     short loc_140002EBD
0x140002eab  and     esi, 0FFFFF63Eh
0x140002eb1  and     edi, 9C1h
0x140002eb7  or      esi, edi
0x140002eb9  mov     dword ptr [rsp+48h+arg_8], esi
0x140002ebd  mov     rax, [rsp+48h+arg_8]
0x140002ec2  mov     rbx, [rsp+48h+arg_10]
0x140002ec7  mov     rbp, [rsp+48h+arg_18]
0x140002ecc  add     rsp, 20h
0x140002ed0  pop     r15
0x140002ed2  pop     r14
0x140002ed4  pop     r12
0x140002ed6  pop     rdi
0x140002ed7  pop     rsi
0x140002ed8  retn
```
