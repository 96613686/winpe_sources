# wil::details::FeatureImpl<__WilFeatureTraits_Feature_BitLocker_BackupToPDR>::GetCachedFeatureEnabledState(void)

- ea: `0x18002611c`
- end: `0x1800261f5`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_BitLocker_BackupToPDR@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180028ae4`
- `0x180029004`

## callees

- `0x1800086f8`
- `0x18000bb98`
- `0x18002611c`
- `0x180026fc8`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_BitLocker_BackupToPDR>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // ebp
  __int64 v6; // rcx
  signed __int32 v7; // eax
  __int16 v8; // bx
  bool v9; // zf
  signed __int32 v10; // edx
  unsigned int v11; // ecx
  wil::details *v13; // [rsp+40h] [rbp+8h] BYREF
  __int64 v14; // [rsp+48h] [rbp+10h] BYREF

  v13 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_BitLocker_BackupToPDR__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_BitLocker_BackupToPDR__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_BitLocker_BackupToPDR>::GetCurrentFeatureEnabledState(
      v6,
      &v14,
      &v13);
    v7 = *(_DWORD *)a2;
    v8 = v14;
    do
    {
      v9 = (_DWORD)v13 == 0;
      v10 = v7;
      *(_DWORD *)a2 = v7;
      v11 = v7;
      if ( !v9 && (v7 & 2) == 0 )
      {
        v11 = v8 & 0x9C1 | v7 & 0xFFFFF63E | 2;
        *(_DWORD *)a2 = v11;
      }
      if ( (v7 & 4) == 0 )
      {
        v11 = v8 & 0x400 | v11 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v11;
      }
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_BitLocker_BackupToPDR__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_BitLocker_BackupToPDR__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18002611c  mov     [rsp+arg_10], rbx
0x180026121  mov     [rsp+arg_0], rcx
0x180026126  push    rbp
0x180026127  push    rsi
0x180026128  push    rdi
0x180026129  sub     rsp, 20h
0x18002612d  mov     rsi, cs:Feature_BitLocker_BackupToPDR__descriptor
0x180026134  mov     rdi, rdx
0x180026137  mov     qword ptr [rdx], 0
0x18002613e  mov     eax, [rsi]
0x180026140  mov     [rdx], eax
0x180026142  and     eax, 6
0x180026145  cmp     al, 6
0x180026147  jz      loc_1800261E5
0x18002614d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180026152  lea     r8, [rsp+38h+arg_0]
0x180026157  mov     dword ptr [rsp+38h+arg_0], 0
0x18002615f  lea     rdx, [rsp+38h+arg_8]
0x180026164  mov     ebp, eax
0x180026166  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_BitLocker_BackupToPDR@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BitLocker_BackupToPDR>::GetCurrentFeatureEnabledState(int *)
0x18002616b  mov     eax, [rdi]
0x18002616d  mov     rbx, [rsp+38h+arg_8]
0x180026172  cmp     dword ptr [rsp+38h+arg_0], 0
0x180026177  mov     edx, eax
0x180026179  mov     [rdi], eax
0x18002617b  mov     ecx, eax
0x18002617d  jz      short loc_180026198
0x18002617f  test    dl, 2
0x180026182  jnz     short loc_180026198
0x180026184  and     ecx, 0FFFFF63Eh
0x18002618a  mov     eax, ebx
0x18002618c  and     eax, 9C1h
0x180026191  or      ecx, eax
0x180026193  or      ecx, 2
0x180026196  mov     [rdi], ecx
0x180026198  mov     r8d, edx
0x18002619b  and     r8d, 4
0x18002619f  jnz     short loc_1800261B3
0x1800261a1  btr     ecx, 0Ah
0x1800261a5  mov     eax, ebx
0x1800261a7  and     eax, 400h
0x1800261ac  or      ecx, eax
0x1800261ae  or      ecx, 4
0x1800261b1  mov     [rdi], ecx
0x1800261b3  mov     eax, edx
0x1800261b5  lock cmpxchg [rsi], ecx
0x1800261b9  jnz     short loc_180026172
0x1800261bb  test    r8d, r8d
0x1800261be  jnz     short loc_1800261D0
0x1800261c0  mov     r8d, ebp
0x1800261c3  mov     edx, 3
0x1800261c8  mov     rcx, rsi
0x1800261cb  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800261d0  mov     eax, [rdi]
0x1800261d2  test    al, 2
0x1800261d4  jnz     short loc_1800261E5
0x1800261d6  and     eax, 0FFFFF63Eh
0x1800261db  and     ebx, 9C1h
0x1800261e1  or      eax, ebx
0x1800261e3  mov     [rdi], eax
0x1800261e5  mov     rbx, [rsp+38h+arg_10]
0x1800261ea  mov     rax, rdi
0x1800261ed  add     rsp, 20h
0x1800261f1  pop     rdi
0x1800261f2  pop     rsi
0x1800261f3  pop     rbp
0x1800261f4  retn
```
