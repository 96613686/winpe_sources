# wil::details::FeatureImpl<__WilFeatureTraits_Feature_57054134>::GetCachedFeatureEnabledState(void)

- ea: `0x18000c384`
- end: `0x18000c45d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_57054134@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800104b8`
- `0x180015724`
- `0x18001ddb0`

## callees

- `0x18000ad30`
- `0x18000c384`
- `0x18000c9c0`
- `0x1800135a0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_57054134>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_57054134__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_57054134__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_57054134>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_57054134__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_57054134__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18000c384  mov     [rsp+arg_10], rbx
0x18000c389  mov     [rsp+arg_0], rcx
0x18000c38e  push    rbp
0x18000c38f  push    rsi
0x18000c390  push    rdi
0x18000c391  sub     rsp, 20h
0x18000c395  mov     rsi, cs:Feature_57054134__descriptor
0x18000c39c  mov     rdi, rdx
0x18000c39f  mov     qword ptr [rdx], 0
0x18000c3a6  mov     eax, [rsi]
0x18000c3a8  mov     [rdx], eax
0x18000c3aa  and     eax, 6
0x18000c3ad  cmp     al, 6
0x18000c3af  jz      loc_18000C44D
0x18000c3b5  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000c3ba  lea     r8, [rsp+38h+arg_0]
0x18000c3bf  mov     dword ptr [rsp+38h+arg_0], 0
0x18000c3c7  lea     rdx, [rsp+38h+arg_8]
0x18000c3cc  mov     ebp, eax
0x18000c3ce  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_57054134@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57054134>::GetCurrentFeatureEnabledState(int *)
0x18000c3d3  mov     eax, [rdi]
0x18000c3d5  mov     rbx, [rsp+38h+arg_8]
0x18000c3da  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000c3df  mov     edx, eax
0x18000c3e1  mov     [rdi], eax
0x18000c3e3  mov     ecx, eax
0x18000c3e5  jz      short loc_18000C400
0x18000c3e7  test    dl, 2
0x18000c3ea  jnz     short loc_18000C400
0x18000c3ec  and     ecx, 0FFFFF63Eh
0x18000c3f2  mov     eax, ebx
0x18000c3f4  and     eax, 9C1h
0x18000c3f9  or      ecx, eax
0x18000c3fb  or      ecx, 2
0x18000c3fe  mov     [rdi], ecx
0x18000c400  mov     r8d, edx
0x18000c403  and     r8d, 4
0x18000c407  jnz     short loc_18000C41B
0x18000c409  btr     ecx, 0Ah
0x18000c40d  mov     eax, ebx
0x18000c40f  and     eax, 400h
0x18000c414  or      ecx, eax
0x18000c416  or      ecx, 4
0x18000c419  mov     [rdi], ecx
0x18000c41b  mov     eax, edx
0x18000c41d  lock cmpxchg [rsi], ecx
0x18000c421  jnz     short loc_18000C3DA
0x18000c423  test    r8d, r8d
0x18000c426  jnz     short loc_18000C438
0x18000c428  mov     r8d, ebp
0x18000c42b  mov     edx, 3
0x18000c430  mov     rcx, rsi
0x18000c433  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000c438  mov     eax, [rdi]
0x18000c43a  test    al, 2
0x18000c43c  jnz     short loc_18000C44D
0x18000c43e  and     eax, 0FFFFF63Eh
0x18000c443  and     ebx, 9C1h
0x18000c449  or      eax, ebx
0x18000c44b  mov     [rdi], eax
0x18000c44d  mov     rbx, [rsp+38h+arg_10]
0x18000c452  mov     rax, rdi
0x18000c455  add     rsp, 20h
0x18000c459  pop     rdi
0x18000c45a  pop     rsi
0x18000c45b  pop     rbp
0x18000c45c  retn
```
