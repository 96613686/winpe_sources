# wil::details::FeatureImpl<__WilFeatureTraits_Feature_CD_MJPEG_MFT_Decoder>::GetCachedFeatureEnabledState(void)

- ea: `0x18001c9b4`
- end: `0x18001ca95`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CD_MJPEG_MFT_Decoder@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `225`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c990`

## callees

- `0x18001c9b4`
- `0x18003b30c`
- `0x18003b92c`
- `0x18003d6a0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_CD_MJPEG_MFT_Decoder>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  int v5; // ebp
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
  v3 = *(_DWORD *)Feature_CD_MJPEG_MFT_Decoder__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_CD_MJPEG_MFT_Decoder__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_CD_MJPEG_MFT_Decoder>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_CD_MJPEG_MFT_Decoder__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        (RTL_SRWLOCK *)&wil::details::g_enabledStateManager,
        (volatile signed __int32 *)Feature_CD_MJPEG_MFT_Decoder__descriptor,
        3,
        v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18001c9b4  mov     [rsp+arg_10], rbx
0x18001c9b9  mov     [rsp+arg_0], rcx
0x18001c9be  push    rbp
0x18001c9bf  push    rsi
0x18001c9c0  push    rdi
0x18001c9c1  sub     rsp, 20h
0x18001c9c5  mov     rsi, cs:Feature_CD_MJPEG_MFT_Decoder__descriptor
0x18001c9cc  mov     rdi, rdx
0x18001c9cf  mov     qword ptr [rdx], 0
0x18001c9d6  mov     eax, [rsi]
0x18001c9d8  mov     [rdx], eax
0x18001c9da  and     eax, 6
0x18001c9dd  cmp     al, 6
0x18001c9df  jz      loc_18001CA85
0x18001c9e5  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001c9ea  lea     r8, [rsp+38h+arg_0]
0x18001c9ef  mov     dword ptr [rsp+38h+arg_0], 0
0x18001c9f7  lea     rdx, [rsp+38h+arg_8]
0x18001c9fc  mov     ebp, eax
0x18001c9fe  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CD_MJPEG_MFT_Decoder@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CD_MJPEG_MFT_Decoder>::GetCurrentFeatureEnabledState(int *)
0x18001ca03  mov     eax, [rdi]
0x18001ca05  mov     rbx, [rsp+38h+arg_8]
0x18001ca0a  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001ca0f  mov     edx, eax
0x18001ca11  mov     [rdi], eax
0x18001ca13  mov     ecx, eax
0x18001ca15  jz      short loc_18001CA30
0x18001ca17  test    dl, 2
0x18001ca1a  jnz     short loc_18001CA30
0x18001ca1c  and     ecx, 0FFFFF63Eh
0x18001ca22  mov     eax, ebx
0x18001ca24  and     eax, 9C1h
0x18001ca29  or      ecx, eax
0x18001ca2b  or      ecx, 2
0x18001ca2e  mov     [rdi], ecx
0x18001ca30  mov     r8d, edx
0x18001ca33  and     r8d, 4
0x18001ca37  jnz     short loc_18001CA4B
0x18001ca39  btr     ecx, 0Ah
0x18001ca3d  mov     eax, ebx
0x18001ca3f  and     eax, 400h
0x18001ca44  or      ecx, eax
0x18001ca46  or      ecx, 4
0x18001ca49  mov     [rdi], ecx
0x18001ca4b  mov     eax, edx
0x18001ca4d  lock cmpxchg [rsi], ecx
0x18001ca51  jnz     short loc_18001CA0A
0x18001ca53  test    r8d, r8d
0x18001ca56  jnz     short loc_18001CA70
0x18001ca58  mov     r9d, ebp
0x18001ca5b  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18001ca62  mov     r8d, 3
0x18001ca68  mov     rdx, rsi
0x18001ca6b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001ca70  mov     eax, [rdi]
0x18001ca72  test    al, 2
0x18001ca74  jnz     short loc_18001CA85
0x18001ca76  and     eax, 0FFFFF63Eh
0x18001ca7b  and     ebx, 9C1h
0x18001ca81  or      eax, ebx
0x18001ca83  mov     [rdi], eax
0x18001ca85  mov     rbx, [rsp+38h+arg_10]
0x18001ca8a  mov     rax, rdi
0x18001ca8d  add     rsp, 20h
0x18001ca91  pop     rdi
0x18001ca92  pop     rsi
0x18001ca93  pop     rbp
0x18001ca94  retn
```
