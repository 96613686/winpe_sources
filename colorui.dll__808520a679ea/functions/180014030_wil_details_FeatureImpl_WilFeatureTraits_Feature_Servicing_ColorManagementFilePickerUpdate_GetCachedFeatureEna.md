# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ColorManagementFilePickerUpdate>::GetCachedFeatureEnabledState(void)

- ea: `0x180014030`
- end: `0x180014109`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_ColorManagementFilePickerUpdate@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800161a4`

## callees

- `0x1800054b4`
- `0x18000a080`
- `0x180014030`
- `0x180014320`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ColorManagementFilePickerUpdate>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Servicing_ColorManagementFilePickerUpdate__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Servicing_ColorManagementFilePickerUpdate__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ColorManagementFilePickerUpdate>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange(
             (volatile signed __int32 *)Feature_Servicing_ColorManagementFilePickerUpdate__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        Feature_Servicing_ColorManagementFilePickerUpdate__descriptor,
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
0x180014030  mov     [rsp+arg_10], rbx
0x180014035  mov     [rsp+arg_0], rcx
0x18001403a  push    rbp
0x18001403b  push    rsi
0x18001403c  push    rdi
0x18001403d  sub     rsp, 20h
0x180014041  mov     rsi, cs:Feature_Servicing_ColorManagementFilePickerUpdate__descriptor
0x180014048  mov     rdi, rdx
0x18001404b  mov     qword ptr [rdx], 0
0x180014052  mov     eax, [rsi]
0x180014054  mov     [rdx], eax
0x180014056  and     eax, 6
0x180014059  cmp     al, 6
0x18001405b  jz      loc_1800140F9
0x180014061  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180014066  lea     r8, [rsp+38h+arg_0]
0x18001406b  mov     dword ptr [rsp+38h+arg_0], 0
0x180014073  lea     rdx, [rsp+38h+arg_8]
0x180014078  mov     ebp, eax
0x18001407a  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_ColorManagementFilePickerUpdate@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ColorManagementFilePickerUpdate>::GetCurrentFeatureEnabledState(int *)
0x18001407f  mov     eax, [rdi]
0x180014081  mov     rbx, [rsp+38h+arg_8]
0x180014086  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001408b  mov     edx, eax
0x18001408d  mov     [rdi], eax
0x18001408f  mov     ecx, eax
0x180014091  jz      short loc_1800140AC
0x180014093  test    dl, 2
0x180014096  jnz     short loc_1800140AC
0x180014098  and     ecx, 0FFFFF63Eh
0x18001409e  mov     eax, ebx
0x1800140a0  and     eax, 9C1h
0x1800140a5  or      ecx, eax
0x1800140a7  or      ecx, 2
0x1800140aa  mov     [rdi], ecx
0x1800140ac  mov     r8d, edx
0x1800140af  and     r8d, 4
0x1800140b3  jnz     short loc_1800140C7
0x1800140b5  btr     ecx, 0Ah
0x1800140b9  mov     eax, ebx
0x1800140bb  and     eax, 400h
0x1800140c0  or      ecx, eax
0x1800140c2  or      ecx, 4
0x1800140c5  mov     [rdi], ecx
0x1800140c7  mov     eax, edx
0x1800140c9  lock cmpxchg [rsi], ecx
0x1800140cd  jnz     short loc_180014086
0x1800140cf  test    r8d, r8d
0x1800140d2  jnz     short loc_1800140E4
0x1800140d4  mov     r8d, ebp
0x1800140d7  mov     edx, 3
0x1800140dc  mov     rcx, rsi
0x1800140df  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800140e4  mov     eax, [rdi]
0x1800140e6  test    al, 2
0x1800140e8  jnz     short loc_1800140F9
0x1800140ea  and     eax, 0FFFFF63Eh
0x1800140ef  and     ebx, 9C1h
0x1800140f5  or      eax, ebx
0x1800140f7  mov     [rdi], eax
0x1800140f9  mov     rbx, [rsp+38h+arg_10]
0x1800140fe  mov     rax, rdi
0x180014101  add     rsp, 20h
0x180014105  pop     rdi
0x180014106  pop     rsi
0x180014107  pop     rbp
0x180014108  retn
```
