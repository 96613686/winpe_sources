# wil::details::FeatureImpl<__WilFeatureTraits_Feature_BitLocker_Block_Backup_DeviceEncryption>::GetCachedFeatureEnabledState(void)

- ea: `0x1800261fc`
- end: `0x1800263a2`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_BitLocker_Block_Backup_DeviceEncryption@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `422`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180028b70`
- `0x180029040`

## callees

- `0x1800086f8`
- `0x18000bb98`
- `0x18002331c`
- `0x1800261fc`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_BitLocker_Block_Backup_DeviceEncryption>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // ebp
  int *v6; // r9
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  unsigned int v8; // r8d
  int v9; // ebx
  int v10; // eax
  unsigned int v11; // ebx
  char v12; // cl
  int v13; // eax
  int v14; // eax
  int v15; // ebx
  signed __int32 v16; // eax
  bool v17; // zf
  signed __int32 v18; // edx
  int v19; // r8d
  int v20; // r9d
  signed __int32 v21; // ecx
  wil::details *v23; // [rsp+40h] [rbp+8h] BYREF

  v23 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_BitLocker_Block_Backup_DeviceEncryption__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_BitLocker_Block_Backup_DeviceEncryption__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v23) = 0;
  v5 = v4;
  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState(
                          (wil::details *)0x3751BB3,
                          0,
                          (enum FEATURE_CHANGE_TIME)&v23,
                          v6);
  v8 = FeatureEnabledState & 0xFFFFFF3F;
  v9 = 8 * (FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3)))));
  if ( (FeatureEnabledState & 0xFFFFFF3F) != 0 )
  {
    v10 = 0;
    if ( v8 == 2 )
      v10 = 64;
  }
  else
  {
    v10 = 64;
  }
  v11 = v10 | v9;
  if ( (v11 & 0x400) != 0 && v11 >= 0x800 )
  {
    v12 = 1;
    v13 = v11 & 0x40;
  }
  else
  {
    v13 = v11 & 0x40;
    if ( (v11 & 0x40) != 0 )
    {
LABEL_14:
      v14 = 1;
      goto LABEL_15;
    }
    v12 = 0;
  }
  if ( v13 && v12 )
    goto LABEL_14;
  v14 = 0;
LABEL_15:
  v15 = v14 | v11;
  if ( !v5 )
    LODWORD(v23) = 0;
  v16 = *(_DWORD *)a2;
  do
  {
    v17 = (_DWORD)v23 == 0;
    v18 = v16;
    *(_DWORD *)a2 = v16;
    if ( v17 || (v16 & 2) != 0 )
    {
      v19 = v16;
    }
    else
    {
      v19 = v16
          ^ ((unsigned __int16)v16
           ^ (unsigned __int16)v15)
          & 0x180
          ^ (v15
           ^ v16
           ^ ((unsigned __int16)v16
            ^ (unsigned __int16)v15)
           & 0x180)
          & 0x40
          ^ ((unsigned __int8)v15
           ^ (unsigned __int8)(v16 ^ (v16 ^ v15) & 0x80 ^ (v15 ^ v16 ^ (v16 ^ v15) & 0x80) & 0x40))
          & 1
          ^ ((unsigned __int16)v15
           ^ (unsigned __int16)(v16
                              ^ (v16
                               ^ v15)
                              & 0x180
                              ^ (v15
                               ^ v16
                               ^ (v16
                                ^ v15)
                               & 0x180)
                              & 0x40
                              ^ ((unsigned __int8)v15
                               ^ (unsigned __int8)(v16 ^ (v16 ^ v15) & 0x80 ^ (v15 ^ v16 ^ (v16 ^ v15) & 0x80) & 0x40))
                              & 1))
          & 0x800
          | 2;
      *(_DWORD *)a2 = v19;
    }
    v20 = v16 & 4;
    if ( (v16 & 4) != 0 )
    {
      v21 = v19;
    }
    else
    {
      v21 = v19 ^ (v19 ^ v15) & 0x400 | 4;
      *(_DWORD *)a2 = v21;
    }
    v16 = _InterlockedCompareExchange(
            (volatile signed __int32 *)Feature_BitLocker_Block_Backup_DeviceEncryption__descriptor,
            v21,
            v16);
  }
  while ( v18 != v16 );
  if ( !v20 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
      Feature_BitLocker_Block_Backup_DeviceEncryption__descriptor,
      0,
      v5);
  if ( (*(_BYTE *)a2 & 2) == 0 )
    *(_DWORD *)a2 ^= ((unsigned __int16)v15
                    ^ (unsigned __int16)*(_DWORD *)a2)
                   & 0x180
                   ^ (v15
                    ^ *(_DWORD *)a2
                    ^ ((unsigned __int16)v15
                     ^ (unsigned __int16)*(_DWORD *)a2)
                    & 0x180)
                   & 0x40
                   ^ ((unsigned __int8)v15
                    ^ *(_BYTE *)a2
                    ^ ((unsigned __int8)v15
                     ^ (unsigned __int8)*(_DWORD *)a2)
                    & 0x80
                    ^ ((unsigned __int8)v15
                     ^ *(_BYTE *)a2
                     ^ ((unsigned __int8)v15
                      ^ (unsigned __int8)*(_DWORD *)a2)
                     & 0x80)
                    & 0x40)
                   & 1
                   ^ ((unsigned __int16)v15
                    ^ *(_WORD *)a2
                    ^ ((unsigned __int16)v15
                     ^ (unsigned __int16)*(_DWORD *)a2)
                    & 0x180
                    ^ ((unsigned __int16)v15
                     ^ *(_WORD *)a2
                     ^ ((unsigned __int16)v15
                      ^ (unsigned __int16)*(_DWORD *)a2)
                     & 0x180)
                    & 0x40
                    ^ ((unsigned __int8)v15
                     ^ *(_BYTE *)a2
                     ^ ((unsigned __int8)v15
                      ^ (unsigned __int8)*(_DWORD *)a2)
                     & 0x80
                     ^ ((unsigned __int8)v15
                      ^ *(_BYTE *)a2
                      ^ ((unsigned __int8)v15
                       ^ (unsigned __int8)*(_DWORD *)a2)
                      & 0x80)
                     & 0x40)
                    & 1)
                   & 0x800;
  return a2;
}

```

## disassembly

```asm
0x1800261fc  mov     [rsp+arg_8], rbx
0x180026201  mov     [rsp+arg_10], rbp
0x180026206  mov     [rsp+arg_0], rcx
0x18002620b  push    rsi
0x18002620c  push    rdi
0x18002620d  push    r15
0x18002620f  sub     rsp, 20h
0x180026213  mov     rsi, cs:Feature_BitLocker_Block_Backup_DeviceEncryption__descriptor
0x18002621a  mov     rdi, rdx
0x18002621d  mov     qword ptr [rdx], 0
0x180026224  mov     eax, [rsi]
0x180026226  mov     [rdx], eax
0x180026228  and     eax, 6
0x18002622b  cmp     al, 6
0x18002622d  jz      loc_18002638C
0x180026233  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180026238  lea     r8, [rsp+38h+arg_0]; enum FEATURE_CHANGE_TIME
0x18002623d  mov     dword ptr [rsp+38h+arg_0], 0
0x180026245  xor     edx, edx; unsigned int
0x180026247  mov     ecx, 3751BB3h; this
0x18002624c  mov     ebp, eax
0x18002624e  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180026253  mov     r8d, eax
0x180026256  mov     ecx, eax
0x180026258  and     r8d, 0FFFFFF3Fh
0x18002625f  and     eax, 80h
0x180026264  mov     edx, r8d
0x180026267  mov     r15d, 40h ; '@'
0x18002626d  and     edx, 3
0x180026270  and     ecx, r15d
0x180026273  shl     edx, 2
0x180026276  or      edx, ecx
0x180026278  shl     edx, 2
0x18002627b  or      edx, eax
0x18002627d  lea     ebx, ds:0[rdx*8]
0x180026284  test    r8d, r8d
0x180026287  jnz     short loc_18002628E
0x180026289  mov     eax, r15d
0x18002628c  jmp     short loc_180026298
0x18002628e  xor     eax, eax
0x180026290  cmp     r8d, 2
0x180026294  cmovz   eax, r15d
0x180026298  or      ebx, eax
0x18002629a  mov     r10d, 400h
0x1800262a0  test    r10d, ebx
0x1800262a3  jz      short loc_1800262B6
0x1800262a5  cmp     ebx, 800h
0x1800262ab  jb      short loc_1800262B6
0x1800262ad  mov     eax, ebx
0x1800262af  mov     cl, 1
0x1800262b1  and     eax, r15d
0x1800262b4  jmp     short loc_1800262BF
0x1800262b6  mov     eax, ebx
0x1800262b8  and     eax, r15d
0x1800262bb  jnz     short loc_1800262CB
0x1800262bd  xor     cl, cl
0x1800262bf  test    eax, eax
0x1800262c1  jz      short loc_1800262C7
0x1800262c3  test    cl, cl
0x1800262c5  jnz     short loc_1800262CB
0x1800262c7  xor     eax, eax
0x1800262c9  jmp     short loc_1800262D0
0x1800262cb  mov     eax, 1
0x1800262d0  or      ebx, eax
0x1800262d2  test    ebp, ebp
0x1800262d4  jnz     short loc_1800262DA
0x1800262d6  mov     dword ptr [rsp+38h+arg_0], ebp
0x1800262da  mov     eax, [rdi]
0x1800262dc  cmp     dword ptr [rsp+38h+arg_0], 0
0x1800262e1  mov     edx, eax
0x1800262e3  mov     [rdi], eax
0x1800262e5  jz      short loc_180026322
0x1800262e7  test    dl, 2
0x1800262ea  jnz     short loc_180026322
0x1800262ec  mov     eax, ebx
0x1800262ee  xor     eax, edx
0x1800262f0  and     eax, 180h
0x1800262f5  xor     eax, edx
0x1800262f7  mov     ecx, eax
0x1800262f9  xor     ecx, ebx
0x1800262fb  and     ecx, r15d
0x1800262fe  xor     ecx, eax
0x180026300  mov     eax, ecx
0x180026302  xor     eax, ebx
0x180026304  and     eax, 1
0x180026307  xor     eax, ecx
0x180026309  mov     r8d, eax
0x18002630c  xor     r8d, ebx
0x18002630f  and     r8d, 800h
0x180026316  xor     r8d, eax
0x180026319  or      r8d, 2
0x18002631d  mov     [rdi], r8d
0x180026320  jmp     short loc_180026325
0x180026322  mov     r8d, edx
0x180026325  mov     r9d, edx
0x180026328  and     r9d, 4
0x18002632c  jnz     short loc_180026340
0x18002632e  mov     ecx, ebx
0x180026330  xor     ecx, r8d
0x180026333  and     ecx, r10d
0x180026336  xor     ecx, r8d
0x180026339  or      ecx, 4
0x18002633c  mov     [rdi], ecx
0x18002633e  jmp     short loc_180026343
0x180026340  mov     ecx, r8d
0x180026343  mov     eax, edx
0x180026345  lock cmpxchg [rsi], ecx
0x180026349  jnz     short loc_1800262DC
0x18002634b  test    r9d, r9d
0x18002634e  jnz     short loc_18002635D
0x180026350  mov     r8d, ebp
0x180026353  xor     edx, edx
0x180026355  mov     rcx, rsi
0x180026358  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18002635d  test    byte ptr [rdi], 2
0x180026360  jnz     short loc_18002638C
0x180026362  mov     eax, [rdi]
0x180026364  xor     eax, ebx
0x180026366  and     eax, 180h
0x18002636b  xor     eax, [rdi]
0x18002636d  mov     ecx, eax
0x18002636f  xor     ecx, ebx
0x180026371  and     ecx, r15d
0x180026374  xor     ecx, eax
0x180026376  mov     edx, ecx
0x180026378  xor     edx, ebx
0x18002637a  and     edx, 1
0x18002637d  xor     edx, ecx
0x18002637f  mov     eax, edx
0x180026381  xor     eax, ebx
0x180026383  and     eax, 800h
0x180026388  xor     eax, edx
0x18002638a  mov     [rdi], eax
0x18002638c  mov     rbx, [rsp+38h+arg_8]
0x180026391  mov     rax, rdi
0x180026394  mov     rbp, [rsp+38h+arg_10]
0x180026399  add     rsp, 20h
0x18002639d  pop     r15
0x18002639f  pop     rdi
0x1800263a0  pop     rsi
0x1800263a1  retn
```
