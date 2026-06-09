# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x14000f734`
- end: `0x14000f9a9`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `629`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000f734`
- `0x14000f9f4`

## callees

- `0x14000f0d4`
- `0x14000f734`
- `0x140034010`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState(
        volatile signed __int32 *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  signed __int32 v5; // ebx
  volatile signed __int32 *v6; // r14
  unsigned int v7; // edx
  int v8; // ebp
  bool v9; // cf
  bool v10; // zf
  int v11; // eax
  int v12; // eax
  int v13; // ecx
  int v14; // edi
  int v15; // r12d
  unsigned int ***v16; // r14
  BOOL v17; // esi
  unsigned int **v18; // rcx
  char v19; // al
  unsigned int v20; // edi
  int v21; // ebp
  signed __int32 v22; // esi
  signed __int32 v23; // eax
  __int64 v25; // [rsp+30h] [rbp-68h]
  __int128 v26; // [rsp+38h] [rbp-60h] BYREF
  __int64 v27; // [rsp+48h] [rbp-50h]
  int v29; // [rsp+A8h] [rbp+10h] BYREF
  int v30; // [rsp+B0h] [rbp+18h]
  __int64 v31; // [rsp+B8h] [rbp+20h]

  v31 = a2;
  v29 = 0;
  v5 = a2;
  v30 = 0;
  v6 = a1;
  if ( g_wil_details_ensureSubscribedToFeatureConfigurationChanges )
    v30 = g_wil_details_ensureSubscribedToFeatureConfigurationChanges();
  v7 = *(_DWORD *)(a3 + 24);
  v8 = 1;
  v9 = *(_BYTE *)(a3 + 28) == 2;
  v10 = *(_BYTE *)(a3 + 28) == 3;
  v26 = 0;
  v27 = 0;
  v11 = wil_QueryFeatureState((__int64)&v26, v7, v9 | (unsigned __int8)v10, a4, 0, &v29);
  v12 = (unsigned __int8)v26 & (unsigned __int8)-(v11 != 0) & 3;
  if ( v12 )
  {
    v13 = 0;
    if ( (_DWORD)v26 == 2 )
      v13 = 64;
  }
  else
  {
    v13 = *(_BYTE *)(a3 + 31) != 0 ? 0x40 : 0;
  }
  v14 = v13 | ((_DWORD)v27 != 0 ? 0x400 : 0) | (HIDWORD(v27) != 0 ? 0x800 : 0) | (v12 << 7);
  if ( (v13 & 0xC00 | ((_DWORD)v27 != 0 ? 0x400 : 0) | (HIDWORD(v27) != 0 ? 0x800 : 0) | (v12 << 7) & 0xC00) == 0xC00 )
  {
    v15 = 1;
  }
  else
  {
    v15 = 0;
    if ( (v13 & 0x40) == 0 )
    {
      v17 = 0;
      goto LABEL_26;
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
        v25 = **v18;
        if ( (v25 & 2) != 0 )
          v19 = **v18;
        else
          v19 = wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState(*v18, v25, v18);
        v17 = (v19 & 1) != 0;
        ++v16;
        if ( (v19 & 1) == 0 )
          break;
      }
    }
  }
  v6 = a1;
  if ( v15 && !v17 )
    v14 &= ~0x400u;
LABEL_26:
  if ( (v14 & 0x40) == 0 || !v17 )
    v8 = 0;
  v20 = v8 | v14 & 0xFFFFFFFE;
  if ( *(_BYTE *)(a3 + 28) )
    v21 = v29;
  else
    v21 = v30 != 0 ? v29 : 0;
  while ( 1 )
  {
    LODWORD(v31) = v5;
    v22 = v5;
    if ( v21 )
    {
      LODWORD(v31) = v5;
      if ( (v5 & 2) == 0 )
      {
        v22 = v5 ^ (v5 ^ v20) & 0x9C1 | 2;
        LODWORD(v31) = v22;
      }
    }
    if ( (v5 & 4) == 0 )
    {
      v22 = v22 ^ ((unsigned __int16)v22 ^ (unsigned __int16)v20) & 0x400 | 4;
      LODWORD(v31) = v22;
    }
    v23 = _InterlockedCompareExchange(v6, v22, v5);
    if ( v5 == v23 )
      break;
    v5 = v23;
  }
  if ( (v5 & 4) == 0 && g_wil_details_subscribeFeatureStateCacheToConfigurationChanges )
    g_wil_details_subscribeFeatureStateCacheToConfigurationChanges(v6, *(unsigned __int8 *)(a3 + 28));
  if ( !v21 )
    LODWORD(v31) = v22 ^ (v22 ^ v20) & 0x9C1;
  return v31;
}

```

## disassembly

```asm
0x14000f734  mov     rax, rsp
0x14000f737  mov     [rax+8], rcx
0x14000f73b  push    rbx
0x14000f73c  push    rbp
0x14000f73d  push    rsi
0x14000f73e  push    rdi
0x14000f73f  push    r12
0x14000f741  push    r13
0x14000f743  push    r14
0x14000f745  push    r15
0x14000f747  sub     rsp, 58h
0x14000f74b  xor     edi, edi
0x14000f74d  mov     [rsp+98h+arg_18], rdx
0x14000f755  mov     [rax+10h], edi
0x14000f758  mov     r13, r8
0x14000f75b  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x14000f762  mov     rbx, rdx
0x14000f765  mov     [rsp+98h+arg_10], edi
0x14000f76c  mov     r14, rcx
0x14000f76f  test    rax, rax
0x14000f772  jz      short loc_14000F780
0x14000f774  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f779  mov     [rsp+98h+arg_10], eax
0x14000f780  mov     cl, [r13+1Ch]
0x14000f784  mov     r8d, edi
0x14000f787  mov     edx, [r13+18h]
0x14000f78b  sub     cl, 2
0x14000f78e  xorps   xmm0, xmm0
0x14000f791  mov     ebp, 1
0x14000f796  cmp     cl, bpl
0x14000f799  lea     rcx, [rsp+98h+var_60]
0x14000f79e  movups  [rsp+98h+var_60], xmm0
0x14000f7a3  setbe   r8b
0x14000f7a7  xor     eax, eax
0x14000f7a9  mov     [rsp+98h+var_50], rax
0x14000f7ae  lea     rax, [rsp+98h+arg_8]
0x14000f7b6  mov     [rsp+98h+var_70], rax
0x14000f7bb  mov     [rsp+98h+var_78], rdi
0x14000f7c0  call    wil_QueryFeatureState
0x14000f7c5  mov     ecx, dword ptr [rsp+98h+var_50]
0x14000f7c9  lea     r15d, [rbp+3Fh]
0x14000f7cd  neg     ecx
0x14000f7cf  mov     ecx, dword ptr [rsp+98h+var_50+4]
0x14000f7d3  sbb     edx, edx
0x14000f7d5  and     edx, 400h
0x14000f7db  neg     ecx
0x14000f7dd  sbb     r8d, r8d
0x14000f7e0  and     r8d, 800h
0x14000f7e7  or      r8d, edx
0x14000f7ea  neg     eax
0x14000f7ec  sbb     eax, eax
0x14000f7ee  and     eax, dword ptr [rsp+98h+var_60]
0x14000f7f2  and     eax, 3
0x14000f7f5  mov     edi, eax
0x14000f7f7  shl     edi, 7
0x14000f7fa  or      edi, r8d
0x14000f7fd  test    eax, eax
0x14000f7ff  jnz     short loc_14000F80E
0x14000f801  mov     al, [r13+1Fh]
0x14000f805  neg     al
0x14000f807  sbb     ecx, ecx
0x14000f809  and     ecx, r15d
0x14000f80c  jmp     short loc_14000F819
0x14000f80e  xor     ecx, ecx
0x14000f810  cmp     dword ptr [rsp+98h+var_60], 2
0x14000f815  cmovz   ecx, r15d
0x14000f819  or      edi, ecx
0x14000f81b  mov     ecx, 0C00h
0x14000f820  mov     eax, edi
0x14000f822  and     eax, ecx
0x14000f824  cmp     eax, ecx
0x14000f826  jnz     short loc_14000F82D
0x14000f828  mov     r12d, ebp
0x14000f82b  jmp     short loc_14000F839
0x14000f82d  xor     r12d, r12d
0x14000f830  test    r15b, dil
0x14000f833  jz      loc_14000F8CA
0x14000f839  mov     r14, [r13+20h]
0x14000f83d  mov     esi, ebp
0x14000f83f  test    r14, r14
0x14000f842  jz      short loc_14000F8B3
0x14000f844  mov     rcx, [r14]
0x14000f847  test    rcx, rcx
0x14000f84a  jz      short loc_14000F8B3
0x14000f84c  cmp     byte ptr [rcx+1Eh], 0
0x14000f850  jnz     short loc_14000F89F
0x14000f852  cmp     byte ptr [rcx+1Dh], 0
0x14000f856  jnz     short loc_14000F89F
0x14000f858  mov     r9, [rcx]
0x14000f85b  mov     [rsp+98h+var_68], 0
0x14000f864  mov     eax, [r9]
0x14000f867  mov     dword ptr [rsp+98h+var_68], eax
0x14000f86b  test    al, 2
0x14000f86d  jz      short loc_14000F876
0x14000f86f  mov     rax, [rsp+98h+var_68]
0x14000f874  jmp     short loc_14000F886
0x14000f876  mov     rdx, [rsp+98h+var_68]
0x14000f87b  mov     r8, rcx
0x14000f87e  mov     rcx, r9
0x14000f881  call    wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState
0x14000f886  test    esi, esi
0x14000f888  jz      short loc_14000F893
0x14000f88a  test    bpl, al
0x14000f88d  jz      short loc_14000F893
0x14000f88f  mov     esi, ebp
0x14000f891  jmp     short loc_14000F895
0x14000f893  xor     esi, esi
0x14000f895  add     r14, 8
0x14000f899  test    esi, esi
0x14000f89b  jnz     short loc_14000F844
0x14000f89d  jmp     short loc_14000F8B3
0x14000f89f  test    esi, esi
0x14000f8a1  jz      short loc_14000F8B1
0x14000f8a3  cmp     byte ptr [rcx+1Fh], 0
0x14000f8a7  jz      short loc_14000F8B1
0x14000f8a9  mov     esi, ebp
0x14000f8ab  add     r14, 8
0x14000f8af  jmp     short loc_14000F844
0x14000f8b1  xor     esi, esi
0x14000f8b3  mov     r14, [rsp+98h+arg_0]
0x14000f8bb  test    r12d, r12d
0x14000f8be  jz      short loc_14000F8CC
0x14000f8c0  test    esi, esi
0x14000f8c2  jnz     short loc_14000F8CC
0x14000f8c4  btr     edi, 0Ah
0x14000f8c8  jmp     short loc_14000F8CC
0x14000f8ca  xor     esi, esi
0x14000f8cc  test    r15b, dil
0x14000f8cf  jz      short loc_14000F8D5
0x14000f8d1  test    esi, esi
0x14000f8d3  jnz     short loc_14000F8D7
0x14000f8d5  xor     ebp, ebp
0x14000f8d7  mov     r8d, [rsp+98h+arg_10]
0x14000f8df  and     edi, 0FFFFFFFEh
0x14000f8e2  or      edi, ebp
0x14000f8e4  cmp     byte ptr [r13+1Ch], 0
0x14000f8e9  jnz     short loc_14000F8FB
0x14000f8eb  mov     eax, r8d
0x14000f8ee  neg     eax
0x14000f8f0  sbb     ebp, ebp
0x14000f8f2  and     ebp, [rsp+98h+arg_8]
0x14000f8f9  jmp     short loc_14000F902
0x14000f8fb  mov     ebp, [rsp+98h+arg_8]
0x14000f902  mov     r15d, 9C1h
0x14000f908  mov     dword ptr [rsp+98h+arg_18], ebx
0x14000f90f  mov     esi, ebx
0x14000f911  test    ebp, ebp
0x14000f913  jz      short loc_14000F934
0x14000f915  mov     dword ptr [rsp+98h+arg_18], ebx
0x14000f91c  test    bl, 2
0x14000f91f  jnz     short loc_14000F934
0x14000f921  mov     esi, edi
0x14000f923  xor     esi, ebx
0x14000f925  and     esi, r15d
0x14000f928  xor     esi, ebx
0x14000f92a  or      esi, 2
0x14000f92d  mov     dword ptr [rsp+98h+arg_18], esi
0x14000f934  mov     ecx, ebx
0x14000f936  and     ecx, 4
0x14000f939  jnz     short loc_14000F953
0x14000f93b  mov     eax, esi
0x14000f93d  mov     esi, edi
0x14000f93f  xor     esi, eax
0x14000f941  and     esi, 400h
0x14000f947  xor     esi, eax
0x14000f949  or      esi, 4
0x14000f94c  mov     dword ptr [rsp+98h+arg_18], esi
0x14000f953  mov     eax, ebx
0x14000f955  lock cmpxchg [r14], esi
0x14000f95a  jz      short loc_14000F960
0x14000f95c  mov     ebx, eax
0x14000f95e  jmp     short loc_14000F908
0x14000f960  test    ecx, ecx
0x14000f962  jnz     short loc_14000F97D
0x14000f964  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x14000f96b  test    rax, rax
0x14000f96e  jz      short loc_14000F97D
0x14000f970  movzx   edx, byte ptr [r13+1Ch]
0x14000f975  mov     rcx, r14
0x14000f978  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f97d  test    ebp, ebp
0x14000f97f  jnz     short loc_14000F98F
0x14000f981  xor     edi, esi
0x14000f983  and     edi, r15d
0x14000f986  xor     edi, esi
0x14000f988  mov     dword ptr [rsp+98h+arg_18], edi
0x14000f98f  mov     rax, [rsp+98h+arg_18]
0x14000f997  add     rsp, 58h
0x14000f99b  pop     r15
0x14000f99d  pop     r14
0x14000f99f  pop     r13
0x14000f9a1  pop     r12
0x14000f9a3  pop     rdi
0x14000f9a4  pop     rsi
0x14000f9a5  pop     rbp
0x14000f9a6  pop     rbx
0x14000f9a7  retn
```
