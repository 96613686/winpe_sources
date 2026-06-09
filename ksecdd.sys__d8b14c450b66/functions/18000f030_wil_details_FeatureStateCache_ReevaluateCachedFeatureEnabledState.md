# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x18000f030`
- end: `0x18000f143`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `275`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f190`
- `0x18000f2e0`

## callees

- `0x18000f030`
- `0x18000f190`
- `0x180010920`

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
0x18000f030  mov     [rsp+arg_10], rbx
0x18000f035  mov     [rsp+arg_18], rbp
0x18000f03a  push    rsi
0x18000f03b  push    rdi
0x18000f03c  push    r12
0x18000f03e  push    r14
0x18000f040  push    r15
0x18000f042  sub     rsp, 20h
0x18000f046  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x18000f04d  xor     r14d, r14d
0x18000f050  mov     [rsp+48h+arg_0], r14d
0x18000f055  mov     r15, r8
0x18000f058  mov     [rsp+48h+arg_8], rdx
0x18000f05d  mov     rdi, rdx
0x18000f060  mov     r12, rcx
0x18000f063  test    rax, rax
0x18000f066  jz      short loc_18000F070
0x18000f068  call    _guard_dispatch_icall
0x18000f06d  mov     r14d, eax
0x18000f070  lea     rdx, [rsp+48h+arg_0]
0x18000f075  mov     rcx, r15
0x18000f078  call    wil_details_GetCurrentFeatureEnabledState
0x18000f07d  cmp     byte ptr [r15+1Ch], 0
0x18000f082  mov     rbx, rax
0x18000f085  jnz     short loc_18000F094
0x18000f087  mov     ecx, r14d
0x18000f08a  neg     ecx
0x18000f08c  sbb     ebp, ebp
0x18000f08e  and     ebp, [rsp+48h+arg_0]
0x18000f092  jmp     short loc_18000F098
0x18000f094  mov     ebp, [rsp+48h+arg_0]
0x18000f098  mov     dword ptr [rsp+48h+arg_8], edi
0x18000f09c  mov     esi, edi
0x18000f09e  test    ebp, ebp
0x18000f0a0  jz      short loc_18000F0C2
0x18000f0a2  mov     dword ptr [rsp+48h+arg_8], edi
0x18000f0a6  test    dil, 2
0x18000f0aa  jnz     short loc_18000F0C2
0x18000f0ac  and     esi, 0FFFFF63Eh
0x18000f0b2  mov     eax, ebx
0x18000f0b4  and     eax, 9C1h
0x18000f0b9  or      esi, eax
0x18000f0bb  or      esi, 2
0x18000f0be  mov     dword ptr [rsp+48h+arg_8], esi
0x18000f0c2  mov     edx, edi
0x18000f0c4  and     edx, 4
0x18000f0c7  jnz     short loc_18000F0E2
0x18000f0c9  mov     eax, esi
0x18000f0cb  mov     ecx, ebx
0x18000f0cd  and     ecx, 400h
0x18000f0d3  btr     eax, 0Ah
0x18000f0d7  mov     esi, ecx
0x18000f0d9  or      esi, eax
0x18000f0db  or      esi, 4
0x18000f0de  mov     dword ptr [rsp+48h+arg_8], esi
0x18000f0e2  mov     eax, edi
0x18000f0e4  lock cmpxchg [r12], esi
0x18000f0ea  jz      short loc_18000F0F0
0x18000f0ec  mov     edi, eax
0x18000f0ee  jmp     short loc_18000F098
0x18000f0f0  test    edx, edx
0x18000f0f2  jnz     short loc_18000F110
0x18000f0f4  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x18000f0fb  test    rax, rax
0x18000f0fe  jz      short loc_18000F110
0x18000f100  movzx   edx, byte ptr [r15+1Ch]
0x18000f105  mov     r8d, r14d
0x18000f108  mov     rcx, r12
0x18000f10b  call    _guard_dispatch_icall
0x18000f110  test    ebp, ebp
0x18000f112  jnz     short loc_18000F126
0x18000f114  and     ebx, 9C1h
0x18000f11a  and     esi, 0FFFFF63Eh
0x18000f120  or      ebx, esi
0x18000f122  mov     dword ptr [rsp+48h+arg_8], ebx
0x18000f126  mov     rax, [rsp+48h+arg_8]
0x18000f12b  mov     rbx, [rsp+48h+arg_10]
0x18000f130  mov     rbp, [rsp+48h+arg_18]
0x18000f135  add     rsp, 20h
0x18000f139  pop     r15
0x18000f13b  pop     r14
0x18000f13d  pop     r12
0x18000f13f  pop     rdi
0x18000f140  pop     rsi
0x18000f141  retn
```
