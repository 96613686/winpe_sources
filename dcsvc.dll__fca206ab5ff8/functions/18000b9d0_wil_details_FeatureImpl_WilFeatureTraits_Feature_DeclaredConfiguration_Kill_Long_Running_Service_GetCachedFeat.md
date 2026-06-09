# wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_Kill_Long_Running_Service>::GetCachedFeatureEnabledState(void)

- ea: `0x18000b9d0`
- end: `0x18000bb8b`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_Kill_Long_Running_Service@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `443`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000beac`
- `0x18000c52c`

## callees

- `0x180004f98`
- `0x180009138`
- `0x18000b9d0`
- `0x180013010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_Kill_Long_Running_Service>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
  __int64 (__fastcall *v5)(__int64, _QWORD, wil::details **); // rax
  int v6; // edx
  int v7; // eax
  int v8; // ebx
  char v9; // al
  int v10; // eax
  int v11; // ebx
  signed __int32 v12; // eax
  bool v13; // zf
  signed __int32 v14; // edx
  int v15; // r8d
  int v16; // r9d
  signed __int32 v17; // ecx
  wil::details *v19; // [rsp+40h] [rbp+8h] BYREF

  v19 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_DeclaredConfiguration_Kill_Long_Running_Service__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_DeclaredConfiguration_Kill_Long_Running_Service__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v19) = 0;
  v5 = (__int64 (__fastcall *)(__int64, _QWORD, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  v6 = 0;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, _QWORD, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(56698136, 0, &v19);
  }
  if ( (v6 & 0xFFFFFF3F) != 0 )
  {
    v7 = 0;
    if ( (v6 & 0xFFFFFF3F) == 2 )
      v7 = 64;
  }
  else
  {
    v7 = 64;
  }
  v8 = v7 | (8 * (v6 & 0x80 | (4 * (v6 & 0x40 | (4 * (v6 & 3))))));
  if ( (v8 & 0xC00) == 0xC00 )
  {
    v9 = 1;
  }
  else
  {
    if ( (v8 & 0x40) != 0 )
    {
LABEL_16:
      v10 = 1;
      goto LABEL_17;
    }
    v9 = 0;
  }
  if ( (v8 & 0x40) != 0 && v9 )
    goto LABEL_16;
  v10 = 0;
LABEL_17:
  v11 = v10 | v8;
  if ( !v4 )
    LODWORD(v19) = 0;
  v12 = *(_DWORD *)a2;
  do
  {
    v13 = (_DWORD)v19 == 0;
    v14 = v12;
    *(_DWORD *)a2 = v12;
    if ( v13 || (v12 & 2) != 0 )
    {
      v15 = v12;
    }
    else
    {
      v15 = v12
          ^ ((unsigned __int16)v12
           ^ (unsigned __int16)v11)
          & 0x180
          ^ (v11
           ^ v12
           ^ ((unsigned __int16)v12
            ^ (unsigned __int16)v11)
           & 0x180)
          & 0x40
          ^ ((unsigned __int8)v11
           ^ (unsigned __int8)(v12 ^ (v12 ^ v11) & 0x80 ^ (v11 ^ v12 ^ (v12 ^ v11) & 0x80) & 0x40))
          & 1
          ^ ((unsigned __int16)v11
           ^ (unsigned __int16)(v12
                              ^ (v12
                               ^ v11)
                              & 0x180
                              ^ (v11
                               ^ v12
                               ^ (v12
                                ^ v11)
                               & 0x180)
                              & 0x40
                              ^ ((unsigned __int8)v11
                               ^ (unsigned __int8)(v12 ^ (v12 ^ v11) & 0x80 ^ (v11 ^ v12 ^ (v12 ^ v11) & 0x80) & 0x40))
                              & 1))
          & 0x800
          | 2;
      *(_DWORD *)a2 = v15;
    }
    v16 = v12 & 4;
    if ( (v12 & 4) != 0 )
    {
      v17 = v15;
    }
    else
    {
      v17 = v15 ^ ((unsigned __int16)v15 ^ (unsigned __int16)v11) & 0x400 | 4;
      *(_DWORD *)a2 = v17;
    }
    v12 = _InterlockedCompareExchange(
            (volatile signed __int32 *)Feature_DeclaredConfiguration_Kill_Long_Running_Service__descriptor,
            v17,
            v12);
  }
  while ( v14 != v12 );
  if ( !v16 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
      Feature_DeclaredConfiguration_Kill_Long_Running_Service__descriptor,
      0,
      v4);
  if ( (*(_BYTE *)a2 & 2) == 0 )
    *(_DWORD *)a2 ^= ((unsigned __int16)v11
                    ^ (unsigned __int16)*(_DWORD *)a2)
                   & 0x180
                   ^ (v11
                    ^ *(_DWORD *)a2
                    ^ ((unsigned __int16)v11
                     ^ (unsigned __int16)*(_DWORD *)a2)
                    & 0x180)
                   & 0x40
                   ^ ((unsigned __int8)v11
                    ^ *(_BYTE *)a2
                    ^ ((unsigned __int8)v11
                     ^ (unsigned __int8)*(_DWORD *)a2)
                    & 0x80
                    ^ ((unsigned __int8)v11
                     ^ *(_BYTE *)a2
                     ^ ((unsigned __int8)v11
                      ^ (unsigned __int8)*(_DWORD *)a2)
                     & 0x80)
                    & 0x40)
                   & 1
                   ^ ((unsigned __int16)v11
                    ^ *(_WORD *)a2
                    ^ ((unsigned __int16)v11
                     ^ (unsigned __int16)*(_DWORD *)a2)
                    & 0x180
                    ^ ((unsigned __int16)v11
                     ^ *(_WORD *)a2
                     ^ ((unsigned __int16)v11
                      ^ (unsigned __int16)*(_DWORD *)a2)
                     & 0x180)
                    & 0x40
                    ^ ((unsigned __int8)v11
                     ^ *(_BYTE *)a2
                     ^ ((unsigned __int8)v11
                      ^ (unsigned __int8)*(_DWORD *)a2)
                     & 0x80
                     ^ ((unsigned __int8)v11
                      ^ *(_BYTE *)a2
                      ^ ((unsigned __int8)v11
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
0x18000b9d0  mov     [rsp+arg_8], rbx
0x18000b9d5  mov     [rsp+arg_10], rbp
0x18000b9da  mov     [rsp+arg_0], rcx
0x18000b9df  push    rsi
0x18000b9e0  push    rdi
0x18000b9e1  push    r15
0x18000b9e3  sub     rsp, 20h
0x18000b9e7  mov     rsi, cs:Feature_DeclaredConfiguration_Kill_Long_Running_Service__descriptor
0x18000b9ee  mov     rdi, rdx
0x18000b9f1  mov     qword ptr [rdx], 0
0x18000b9f8  mov     eax, [rsi]
0x18000b9fa  mov     [rdx], eax
0x18000b9fc  and     eax, 6
0x18000b9ff  cmp     al, 6
0x18000ba01  jz      loc_18000BB75
0x18000ba07  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000ba0c  mov     ebp, eax
0x18000ba0e  mov     dword ptr [rsp+38h+arg_0], 0
0x18000ba16  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000ba1d  xor     edx, edx
0x18000ba1f  test    rax, rax
0x18000ba22  jnz     short loc_18000BA30
0x18000ba24  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000ba2b  test    rax, rax
0x18000ba2e  jz      short loc_18000BA41
0x18000ba30  lea     r8, [rsp+38h+arg_0]
0x18000ba35  mov     ecx, 3612518h
0x18000ba3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba3f  mov     edx, eax
0x18000ba41  mov     r8d, edx
0x18000ba44  mov     eax, edx
0x18000ba46  and     r8d, 0FFFFFF3Fh
0x18000ba4d  and     edx, 80h
0x18000ba53  mov     ecx, r8d
0x18000ba56  mov     r15d, 40h ; '@'
0x18000ba5c  and     ecx, 3
0x18000ba5f  and     eax, r15d
0x18000ba62  shl     ecx, 2
0x18000ba65  or      ecx, eax
0x18000ba67  shl     ecx, 2
0x18000ba6a  or      ecx, edx
0x18000ba6c  lea     ebx, ds:0[rcx*8]
0x18000ba73  test    r8d, r8d
0x18000ba76  jnz     short loc_18000BA7D
0x18000ba78  mov     eax, r15d
0x18000ba7b  jmp     short loc_18000BA87
0x18000ba7d  xor     eax, eax
0x18000ba7f  cmp     r8d, 2
0x18000ba83  cmovz   eax, r15d
0x18000ba87  or      ebx, eax
0x18000ba89  mov     edx, 0C00h
0x18000ba8e  mov     ecx, ebx
0x18000ba90  mov     eax, ebx
0x18000ba92  and     ecx, r15d
0x18000ba95  and     eax, edx
0x18000ba97  cmp     eax, edx
0x18000ba99  jnz     short loc_18000BA9F
0x18000ba9b  mov     al, 1
0x18000ba9d  jmp     short loc_18000BAA5
0x18000ba9f  test    ecx, ecx
0x18000baa1  jnz     short loc_18000BAB1
0x18000baa3  xor     al, al
0x18000baa5  test    ecx, ecx
0x18000baa7  jz      short loc_18000BAAD
0x18000baa9  test    al, al
0x18000baab  jnz     short loc_18000BAB1
0x18000baad  xor     eax, eax
0x18000baaf  jmp     short loc_18000BAB6
0x18000bab1  mov     eax, 1
0x18000bab6  or      ebx, eax
0x18000bab8  test    ebp, ebp
0x18000baba  jnz     short loc_18000BAC0
0x18000babc  mov     dword ptr [rsp+38h+arg_0], ebp
0x18000bac0  mov     eax, [rdi]
0x18000bac2  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000bac7  mov     edx, eax
0x18000bac9  mov     [rdi], eax
0x18000bacb  jz      short loc_18000BB08
0x18000bacd  test    dl, 2
0x18000bad0  jnz     short loc_18000BB08
0x18000bad2  mov     eax, ebx
0x18000bad4  xor     eax, edx
0x18000bad6  and     eax, 180h
0x18000badb  xor     eax, edx
0x18000badd  mov     ecx, eax
0x18000badf  xor     ecx, ebx
0x18000bae1  and     ecx, r15d
0x18000bae4  xor     ecx, eax
0x18000bae6  mov     eax, ecx
0x18000bae8  xor     eax, ebx
0x18000baea  and     eax, 1
0x18000baed  xor     eax, ecx
0x18000baef  mov     r8d, eax
0x18000baf2  xor     r8d, ebx
0x18000baf5  and     r8d, 800h
0x18000bafc  xor     r8d, eax
0x18000baff  or      r8d, 2
0x18000bb03  mov     [rdi], r8d
0x18000bb06  jmp     short loc_18000BB0B
0x18000bb08  mov     r8d, edx
0x18000bb0b  mov     r9d, edx
0x18000bb0e  and     r9d, 4
0x18000bb12  jnz     short loc_18000BB29
0x18000bb14  mov     ecx, ebx
0x18000bb16  xor     ecx, r8d
0x18000bb19  and     ecx, 400h
0x18000bb1f  xor     ecx, r8d
0x18000bb22  or      ecx, 4
0x18000bb25  mov     [rdi], ecx
0x18000bb27  jmp     short loc_18000BB2C
0x18000bb29  mov     ecx, r8d
0x18000bb2c  mov     eax, edx
0x18000bb2e  lock cmpxchg [rsi], ecx
0x18000bb32  jnz     short loc_18000BAC2
0x18000bb34  test    r9d, r9d
0x18000bb37  jnz     short loc_18000BB46
0x18000bb39  mov     r8d, ebp
0x18000bb3c  xor     edx, edx
0x18000bb3e  mov     rcx, rsi
0x18000bb41  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000bb46  test    byte ptr [rdi], 2
0x18000bb49  jnz     short loc_18000BB75
0x18000bb4b  mov     eax, [rdi]
0x18000bb4d  xor     eax, ebx
0x18000bb4f  and     eax, 180h
0x18000bb54  xor     eax, [rdi]
0x18000bb56  mov     ecx, eax
0x18000bb58  xor     ecx, ebx
0x18000bb5a  and     ecx, r15d
0x18000bb5d  xor     ecx, eax
0x18000bb5f  mov     edx, ecx
0x18000bb61  xor     edx, ebx
0x18000bb63  and     edx, 1
0x18000bb66  xor     edx, ecx
0x18000bb68  mov     eax, edx
0x18000bb6a  xor     eax, ebx
0x18000bb6c  and     eax, 800h
0x18000bb71  xor     eax, edx
0x18000bb73  mov     [rdi], eax
0x18000bb75  mov     rbx, [rsp+38h+arg_8]
0x18000bb7a  mov     rax, rdi
0x18000bb7d  mov     rbp, [rsp+38h+arg_10]
0x18000bb82  add     rsp, 20h
0x18000bb86  pop     r15
0x18000bb88  pop     rdi
0x18000bb89  pop     rsi
0x18000bb8a  retn
```
