# wil::details::FeatureImpl<__WilFeatureTraits_Feature_EapServerTls13>::GetCachedVariantState(void)

- ea: `0x18001bbec`
- end: `0x18001bd6f`
- name: `?GetCachedVariantState@?$FeatureImpl@U__WilFeatureTraits_Feature_EapServerTls13@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `387`
- prototype: `__int64 *__fastcall(wil::details *, signed __int64 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001dffc`
- `0x180023aac`

## callees

- `0x180009e0c`
- `0x18000bbb0`
- `0x18001bbec`
- `0x180023c34`
- `0x180033010`

## pseudocode

```c
__int64 *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_EapServerTls13>::GetCachedVariantState(
        wil::details *a1,
        signed __int64 *a2)
{
  __int64 v3; // rax
  unsigned int v4; // r15d
  __int64 (__fastcall *v5)(__int64, __int64, int *, wil::details **, int *); // rax
  int v6; // esi
  int v7; // ebx
  int v8; // r9d
  __int64 v9; // r8
  signed __int64 v10; // rax
  signed __int64 v11; // r10
  int v12; // eax
  int v13; // eax
  bool v14; // zf
  wil::details *v16; // [rsp+60h] [rbp+30h] BYREF
  int v17; // [rsp+68h] [rbp+38h] BYREF
  int v18; // [rsp+70h] [rbp+40h] BYREF

  v16 = a1;
  v3 = *Feature_EapServerTls13__descriptor;
  *a2 = *Feature_EapServerTls13__descriptor;
  if ( (v3 & 0xC) == 0xC )
    return a2;
  v18 = 0;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v16) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, int *, wil::details **, int *))g_wil_details_internalGetFeatureVariant;
  v17 = 0;
  if ( g_wil_details_internalGetFeatureVariant
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, int *, wil::details **, int *))g_wil_details_apiGetFeatureVariant) != 0 )
  {
    v6 = v5(60520429, 3, &v17, &v16, &v18);
  }
  else
  {
    v6 = 0;
  }
  v7 = ((_DWORD)v16 != 0 ? 0x400 : 0) | (16 * (v6 & 0x80));
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl'::`2'::impl) )
    goto LABEL_11;
  if ( (v6 & 0xFFFFFE7F) == 0 )
  {
    v8 = 0;
    v7 |= 0x1000u;
    goto LABEL_12;
  }
  v7 ^= (v6 & 0x3F) << 12;
  if ( (v6 & 0x100) != 0 )
    v8 = v17;
  else
LABEL_11:
    v8 = 0;
LABEL_12:
  v9 = *a2;
  v10 = *a2;
  v11 = *a2;
  while ( 1 )
  {
    *(_DWORD *)a2 = v9;
    *((_DWORD *)a2 + 1) = HIDWORD(v10);
    if ( (v9 & 8) != 0 )
    {
      v13 = v9;
    }
    else
    {
      v12 = v18;
      *((_DWORD *)a2 + 1) = v8;
      v13 = ((v12 != 0 ? 8 : 0) | (v9 ^ (v7 ^ v9) & 0x3F000) & 0xFFFFFFF7)
          ^ ((unsigned __int16)v7
           ^ ((v12 != 0 ? 8 : 0)
            | ((unsigned __int16)v9 ^ ((unsigned __int16)v7 ^ (unsigned __int16)v9) & 0xF000) & 0xFFF7))
          & 0x800;
      *(_DWORD *)a2 = v13;
    }
    if ( (v9 & 4) == 0 )
      *(_DWORD *)a2 = v13 ^ ((unsigned __int16)v13 ^ (unsigned __int16)v7) & 0x400 | 4;
    v10 = _InterlockedCompareExchange64(Feature_EapServerTls13__descriptor, *a2, v11);
    v14 = v11 == v10;
    v11 = v10;
    if ( v14 )
      break;
    LODWORD(v9) = v10;
  }
  if ( (v9 & 4) == 0 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_EapServerTls13__descriptor, 3, v4);
  return a2;
}

```

## disassembly

```asm
0x18001bbec  mov     [rsp-28h+arg_18], rbx
0x18001bbf1  mov     [rsp-28h+arg_0], rcx
0x18001bbf6  push    rbp
0x18001bbf7  push    rsi
0x18001bbf8  push    rdi
0x18001bbf9  push    r14
0x18001bbfb  push    r15
0x18001bbfd  mov     rbp, rsp
0x18001bc00  sub     rsp, 30h
0x18001bc04  mov     r14, cs:Feature_EapServerTls13__descriptor
0x18001bc0b  mov     rdi, rdx
0x18001bc0e  mov     rax, [r14]
0x18001bc11  mov     [rdx], rax
0x18001bc14  and     eax, 0Ch
0x18001bc17  cmp     al, 0Ch
0x18001bc19  jz      loc_18001BD5B
0x18001bc1f  mov     [rbp+arg_10], 0
0x18001bc26  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001bc2b  mov     r15d, eax
0x18001bc2e  mov     dword ptr [rbp+arg_0], 0
0x18001bc35  mov     rax, cs:g_wil_details_internalGetFeatureVariant
0x18001bc3c  mov     [rbp+arg_8], 0
0x18001bc43  test    rax, rax
0x18001bc46  jz      short loc_18001BC6C
0x18001bc48  lea     rcx, [rbp+arg_10]
0x18001bc4c  mov     edx, 3
0x18001bc51  mov     [rsp+30h+var_10], rcx
0x18001bc56  lea     r9, [rbp+arg_0]
0x18001bc5a  mov     ecx, 39B77EDh
0x18001bc5f  lea     r8, [rbp+arg_8]
0x18001bc63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc68  mov     esi, eax
0x18001bc6a  jmp     short loc_18001BC7A
0x18001bc6c  mov     rax, cs:g_wil_details_apiGetFeatureVariant
0x18001bc73  test    rax, rax
0x18001bc76  jnz     short loc_18001BC48
0x18001bc78  xor     esi, esi
0x18001bc7a  mov     eax, dword ptr [rbp+arg_0]
0x18001bc7d  mov     ebx, esi
0x18001bc7f  neg     eax
0x18001bc81  sbb     ecx, ecx
0x18001bc83  and     ebx, 80h
0x18001bc89  and     ecx, 400h
0x18001bc8f  shl     ebx, 4
0x18001bc92  or      ebx, ecx
0x18001bc94  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UxAccOptimization@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization> `wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl(void)'::`2'::impl
0x18001bc9b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(wil::ReportingKind)
0x18001bca0  test    al, al
0x18001bca2  jz      short loc_18001BCCA
0x18001bca4  mov     eax, esi
0x18001bca6  and     eax, 0FFFFFE7Fh
0x18001bcab  jnz     short loc_18001BCB6
0x18001bcad  xor     r9d, r9d
0x18001bcb0  bts     ebx, 0Ch
0x18001bcb4  jmp     short loc_18001BCCD
0x18001bcb6  and     eax, 3Fh
0x18001bcb9  shl     eax, 0Ch
0x18001bcbc  xor     ebx, eax
0x18001bcbe  bt      esi, 8
0x18001bcc2  jnb     short loc_18001BCCA
0x18001bcc4  mov     r9d, [rbp+arg_8]
0x18001bcc8  jmp     short loc_18001BCCD
0x18001bcca  xor     r9d, r9d
0x18001bccd  mov     r8, [rdi]
0x18001bcd0  mov     rax, r8
0x18001bcd3  mov     r10, r8
0x18001bcd6  shr     rax, 20h
0x18001bcda  mov     [rdi], r8d
0x18001bcdd  mov     [rdi+4], eax
0x18001bce0  test    r8b, 8
0x18001bce4  jnz     short loc_18001BD16
0x18001bce6  mov     eax, [rbp+arg_10]
0x18001bce9  mov     edx, r8d
0x18001bcec  xor     edx, ebx
0x18001bcee  mov     [rdi+4], r9d
0x18001bcf2  and     edx, 3F000h
0x18001bcf8  xor     edx, r8d
0x18001bcfb  neg     eax
0x18001bcfd  sbb     ecx, ecx
0x18001bcff  and     edx, 0FFFFFFF7h
0x18001bd02  and     ecx, 8
0x18001bd05  or      edx, ecx
0x18001bd07  mov     eax, edx
0x18001bd09  xor     eax, ebx
0x18001bd0b  and     eax, 800h
0x18001bd10  xor     eax, edx
0x18001bd12  mov     [rdi], eax
0x18001bd14  jmp     short loc_18001BD19
0x18001bd16  mov     eax, r8d
0x18001bd19  test    r8b, 4
0x18001bd1d  jnz     short loc_18001BD30
0x18001bd1f  mov     ecx, ebx
0x18001bd21  xor     ecx, eax
0x18001bd23  and     ecx, 400h
0x18001bd29  xor     ecx, eax
0x18001bd2b  or      ecx, 4
0x18001bd2e  mov     [rdi], ecx
0x18001bd30  mov     rcx, [rdi]
0x18001bd33  mov     rax, r10
0x18001bd36  lock cmpxchg [r14], rcx
0x18001bd3b  mov     r10, rax
0x18001bd3e  jz      short loc_18001BD45
0x18001bd40  mov     r8d, eax
0x18001bd43  jmp     short loc_18001BCD6
0x18001bd45  test    r8b, 4
0x18001bd49  jnz     short loc_18001BD5B
0x18001bd4b  mov     r8d, r15d
0x18001bd4e  mov     edx, 3
0x18001bd53  mov     rcx, r14
0x18001bd56  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001bd5b  mov     rbx, [rsp+30h+arg_18]
0x18001bd60  mov     rax, rdi
0x18001bd63  add     rsp, 30h
0x18001bd67  pop     r15
0x18001bd69  pop     r14
0x18001bd6b  pop     rdi
0x18001bd6c  pop     rsi
0x18001bd6d  pop     rbp
0x18001bd6e  retn
```
