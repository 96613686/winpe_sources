# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x180021adc`
- end: `0x180021d14`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `568`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180021adc`
- `0x180021d70`

## callees

- `0x18001a748`
- `0x180021adc`
- `0x180024010`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState(
        volatile signed __int32 *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  signed __int32 v5; // ebx
  volatile signed __int32 *v6; // r15
  unsigned int v7; // edx
  int v8; // r14d
  bool v9; // cf
  bool v10; // zf
  int v11; // eax
  int v12; // eax
  int v13; // ecx
  int v14; // edi
  int v15; // eax
  unsigned int ***v16; // r15
  BOOL v17; // esi
  unsigned int **v18; // rcx
  char v19; // al
  __int64 v20; // r8
  unsigned int v21; // edi
  signed __int32 v22; // ecx
  signed __int32 v23; // eax
  signed __int32 v24; // ecx
  signed __int32 v25; // esi
  __int64 v27; // [rsp+30h] [rbp-38h]
  __int64 v28; // [rsp+38h] [rbp-30h]
  __int128 v29; // [rsp+40h] [rbp-28h] BYREF
  __int64 v30; // [rsp+50h] [rbp-18h]
  int v32; // [rsp+B8h] [rbp+50h] BYREF
  unsigned int v33; // [rsp+C0h] [rbp+58h]
  int v34; // [rsp+C8h] [rbp+60h]

  v33 = 0;
  v32 = 0;
  HIDWORD(v28) = HIDWORD(a2);
  v5 = a2;
  v6 = a1;
  if ( g_wil_details_ensureSubscribedToFeatureConfigurationChanges )
    v33 = g_wil_details_ensureSubscribedToFeatureConfigurationChanges();
  v7 = *(_DWORD *)(a3 + 24);
  v8 = 1;
  v9 = *(_BYTE *)(a3 + 28) == 2;
  v10 = *(_BYTE *)(a3 + 28) == 3;
  v29 = 0;
  v30 = 0;
  v11 = wil_QueryFeatureState((__int64)&v29, v7, v9 | (unsigned __int8)v10, a4, 0, &v32);
  v12 = (unsigned __int8)v29 & (unsigned __int8)-(v11 != 0) & 3;
  v13 = ((_DWORD)v30 != 0 ? 0x400 : 0) | (HIDWORD(v30) != 0 ? 0x800 : 0) | (v12 << 7);
  if ( v12 )
  {
    v15 = 0;
    if ( (_DWORD)v29 == 2 )
      v15 = 64;
    v14 = v15 | v13;
  }
  else
  {
    v14 = v13 | (*(_BYTE *)(a3 + 31) != 0 ? 0x40 : 0);
  }
  if ( (v14 & 0xC00) == 0xC00 )
  {
    v34 = 1;
  }
  else
  {
    v34 = 0;
    if ( (v14 & 0x40) == 0 )
    {
LABEL_28:
      v8 = 0;
      goto LABEL_29;
    }
  }
  v16 = *(unsigned int ****)(a3 + 32);
  v17 = 1;
  if ( v16 )
  {
    while ( 1 )
    {
      v18 = *v16;
      if ( !*v16 )
        break;
      if ( *((_BYTE *)v18 + 30) || *((_BYTE *)v18 + 29) )
      {
        if ( !*((_BYTE *)v18 + 31) )
        {
          v17 = 0;
          break;
        }
        v17 = 1;
        ++v16;
      }
      else
      {
        v27 = **v18;
        if ( (v27 & 2) != 0 )
          v19 = **v18;
        else
          v19 = wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState(*v18, v27, v18);
        v17 = (v19 & 1) != 0;
        ++v16;
        if ( (v19 & 1) == 0 )
          break;
      }
    }
  }
  v6 = a1;
  if ( v34 && !v17 )
    v14 &= ~0x400u;
  if ( (v14 & 0x40) == 0 || !v17 )
    goto LABEL_28;
LABEL_29:
  v20 = v33;
  v21 = v8 | v14 & 0xFFFFFFFE;
  if ( !*(_BYTE *)(a3 + 28) )
    v32 = v33 != 0 ? v32 : 0;
  v22 = v5;
  LOBYTE(v23) = v5;
  while ( 1 )
  {
    v24 = v22 | 0x40000;
    LODWORD(v28) = v24;
    if ( v32 && (v23 & 2) == 0 )
    {
      v24 = (v21 ^ v24) & 0x9C1 ^ v24 | 2;
      LODWORD(v28) = v24;
    }
    if ( (v5 & 4) == 0 )
    {
      v24 = v24 ^ ((unsigned __int16)v21 ^ (unsigned __int16)v24) & 0x400 | 4;
      LODWORD(v28) = v24;
    }
    v25 = v24;
    v23 = _InterlockedCompareExchange(v6, v24, v5);
    v22 = v23;
    if ( v5 == v23 )
      break;
    v5 = v23;
  }
  if ( (v5 & 4) == 0 && g_wil_details_subscribeFeatureStateCacheToConfigurationChanges )
    g_wil_details_subscribeFeatureStateCacheToConfigurationChanges(v6, *(unsigned __int8 *)(a3 + 28), v20);
  if ( !v32 )
    LODWORD(v28) = v25 ^ (v25 ^ v21) & 0x9C1;
  return v28;
}

```

## disassembly

```asm
0x180021adc  mov     [rsp-40h+arg_0], rcx
0x180021ae1  push    rbp
0x180021ae2  push    rbx
0x180021ae3  push    rsi
0x180021ae4  push    rdi
0x180021ae5  push    r12
0x180021ae7  push    r13
0x180021ae9  push    r14
0x180021aeb  push    r15
0x180021aed  mov     rbp, rsp
0x180021af0  sub     rsp, 68h
0x180021af4  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x180021afb  xor     edi, edi
0x180021afd  mov     [rbp+arg_10], edi
0x180021b00  mov     r13, r8
0x180021b03  mov     [rbp+arg_8], edi
0x180021b06  mov     rbx, rdx
0x180021b09  mov     [rbp+var_30], rdx
0x180021b0d  mov     r15, rcx
0x180021b10  test    rax, rax
0x180021b13  jz      short loc_180021B1D
0x180021b15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021b1a  mov     [rbp+arg_10], eax
0x180021b1d  mov     cl, [r13+1Ch]
0x180021b21  mov     r8d, edi
0x180021b24  mov     edx, [r13+18h]
0x180021b28  sub     cl, 2
0x180021b2b  xorps   xmm0, xmm0
0x180021b2e  mov     r14d, 1
0x180021b34  cmp     cl, r14b
0x180021b37  lea     rcx, [rbp+var_28]
0x180021b3b  movups  [rbp+var_28], xmm0
0x180021b3f  setbe   r8b
0x180021b43  xor     eax, eax
0x180021b45  mov     [rbp+var_18], rax
0x180021b49  lea     rax, [rbp+arg_8]
0x180021b4d  mov     [rsp+68h+var_40], rax
0x180021b52  mov     [rsp+68h+var_48], rdi
0x180021b57  call    wil_QueryFeatureState
0x180021b5c  mov     ecx, dword ptr [rbp+var_18]
0x180021b5f  lea     r12d, [r14+3Fh]
0x180021b63  neg     ecx
0x180021b65  mov     ecx, dword ptr [rbp+var_18+4]
0x180021b68  sbb     edx, edx
0x180021b6a  and     edx, 400h
0x180021b70  neg     ecx
0x180021b72  sbb     r8d, r8d
0x180021b75  and     r8d, 800h
0x180021b7c  or      r8d, edx
0x180021b7f  neg     eax
0x180021b81  sbb     eax, eax
0x180021b83  xor     edx, edx
0x180021b85  and     eax, dword ptr [rbp+var_28]
0x180021b88  and     eax, 3
0x180021b8b  mov     ecx, eax
0x180021b8d  shl     ecx, 7
0x180021b90  or      ecx, r8d
0x180021b93  test    eax, eax
0x180021b95  jnz     short loc_180021BA6
0x180021b97  mov     al, [r13+1Fh]
0x180021b9b  neg     al
0x180021b9d  sbb     edi, edi
0x180021b9f  and     edi, r12d
0x180021ba2  or      edi, ecx
0x180021ba4  jmp     short loc_180021BB4
0x180021ba6  cmp     dword ptr [rbp+var_28], 2
0x180021baa  mov     eax, edx
0x180021bac  mov     edi, ecx
0x180021bae  cmovz   eax, r12d
0x180021bb2  or      edi, eax
0x180021bb4  mov     ecx, 0C00h
0x180021bb9  mov     eax, edi
0x180021bbb  and     eax, ecx
0x180021bbd  mov     esi, edx
0x180021bbf  cmp     eax, ecx
0x180021bc1  jnz     short loc_180021BC9
0x180021bc3  mov     [rbp+arg_18], r14d
0x180021bc7  jmp     short loc_180021BD5
0x180021bc9  mov     [rbp+arg_18], edx
0x180021bcc  test    r12b, dil
0x180021bcf  jz      loc_180021C61
0x180021bd5  mov     r15, [r13+20h]
0x180021bd9  mov     esi, r14d
0x180021bdc  test    r15, r15
0x180021bdf  jz      short loc_180021C47
0x180021be1  mov     rcx, [r15]
0x180021be4  test    rcx, rcx
0x180021be7  jz      short loc_180021C47
0x180021be9  cmp     [rcx+1Eh], dl
0x180021bec  jnz     short loc_180021C33
0x180021bee  cmp     [rcx+1Dh], dl
0x180021bf1  jnz     short loc_180021C33
0x180021bf3  mov     r9, [rcx]
0x180021bf6  mov     [rbp+var_38], rdx
0x180021bfa  mov     eax, [r9]
0x180021bfd  mov     dword ptr [rbp+var_38], eax
0x180021c00  test    al, 2
0x180021c02  jz      short loc_180021C0A
0x180021c04  mov     rax, [rbp+var_38]
0x180021c08  jmp     short loc_180021C1B
0x180021c0a  mov     rdx, [rbp+var_38]
0x180021c0e  mov     r8, rcx
0x180021c11  mov     rcx, r9
0x180021c14  call    wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState
0x180021c19  xor     edx, edx
0x180021c1b  test    esi, esi
0x180021c1d  jz      short loc_180021C27
0x180021c1f  mov     esi, r14d
0x180021c22  test    r14b, al
0x180021c25  jnz     short loc_180021C29
0x180021c27  mov     esi, edx
0x180021c29  add     r15, 8
0x180021c2d  test    esi, esi
0x180021c2f  jnz     short loc_180021BE1
0x180021c31  jmp     short loc_180021C47
0x180021c33  test    esi, esi
0x180021c35  jz      short loc_180021C45
0x180021c37  cmp     [rcx+1Fh], dl
0x180021c3a  jz      short loc_180021C45
0x180021c3c  mov     esi, r14d
0x180021c3f  add     r15, 8
0x180021c43  jmp     short loc_180021BE1
0x180021c45  mov     esi, edx
0x180021c47  mov     r15, [rbp+arg_0]
0x180021c4b  cmp     [rbp+arg_18], edx
0x180021c4e  jz      short loc_180021C58
0x180021c50  test    esi, esi
0x180021c52  jnz     short loc_180021C58
0x180021c54  btr     edi, 0Ah
0x180021c58  test    r12b, dil
0x180021c5b  jz      short loc_180021C61
0x180021c5d  test    esi, esi
0x180021c5f  jnz     short loc_180021C64
0x180021c61  mov     r14d, edx
0x180021c64  mov     r8d, [rbp+arg_10]
0x180021c68  and     edi, 0FFFFFFFEh
0x180021c6b  or      edi, r14d
0x180021c6e  cmp     [r13+1Ch], dl
0x180021c72  jnz     short loc_180021C7E
0x180021c74  mov     eax, r8d
0x180021c77  neg     eax
0x180021c79  sbb     ecx, ecx
0x180021c7b  and     [rbp+arg_8], ecx
0x180021c7e  mov     ecx, ebx
0x180021c80  mov     eax, ebx
0x180021c82  mov     r14d, 9C1h
0x180021c88  bts     ecx, 12h
0x180021c8c  mov     dword ptr [rbp+var_30], ecx
0x180021c8f  cmp     [rbp+arg_8], edx
0x180021c92  jz      short loc_180021CA7
0x180021c94  test    al, 2
0x180021c96  jnz     short loc_180021CA7
0x180021c98  mov     eax, ecx
0x180021c9a  xor     eax, edi
0x180021c9c  and     eax, r14d
0x180021c9f  xor     ecx, eax
0x180021ca1  or      ecx, 2
0x180021ca4  mov     dword ptr [rbp+var_30], ecx
0x180021ca7  mov     eax, ecx
0x180021ca9  test    bl, 4
0x180021cac  jnz     short loc_180021CBE
0x180021cae  xor     ecx, edi
0x180021cb0  and     ecx, 400h
0x180021cb6  xor     ecx, eax
0x180021cb8  or      ecx, 4
0x180021cbb  mov     dword ptr [rbp+var_30], ecx
0x180021cbe  mov     esi, ecx
0x180021cc0  mov     eax, ebx
0x180021cc2  lock cmpxchg [r15], ecx
0x180021cc7  mov     ecx, eax
0x180021cc9  jz      short loc_180021CCF
0x180021ccb  mov     ebx, eax
0x180021ccd  jmp     short loc_180021C88
0x180021ccf  test    bl, 4
0x180021cd2  jnz     short loc_180021CEF
0x180021cd4  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x180021cdb  test    rax, rax
0x180021cde  jz      short loc_180021CEF
0x180021ce0  movzx   edx, byte ptr [r13+1Ch]
0x180021ce5  mov     rcx, r15
0x180021ce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ced  xor     edx, edx
0x180021cef  cmp     [rbp+arg_8], edx
0x180021cf2  jnz     short loc_180021CFE
0x180021cf4  xor     edi, esi
0x180021cf6  and     edi, r14d
0x180021cf9  xor     edi, esi
0x180021cfb  mov     dword ptr [rbp+var_30], edi
0x180021cfe  mov     rax, [rbp+var_30]
0x180021d02  add     rsp, 68h
0x180021d06  pop     r15
0x180021d08  pop     r14
0x180021d0a  pop     r13
0x180021d0c  pop     r12
0x180021d0e  pop     rdi
0x180021d0f  pop     rsi
0x180021d10  pop     rbx
0x180021d11  pop     rbp
0x180021d12  retn
```
