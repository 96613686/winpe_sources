# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x18000c824`
- end: `0x18000ca98`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `628`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c824`
- `0x18000cae4`

## callees

- `0x18000ad24`
- `0x18000c824`
- `0x18000e010`

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
0x18000c824  mov     rax, rsp
0x18000c827  mov     [rax+8], rcx
0x18000c82b  push    rbx
0x18000c82c  push    rbp
0x18000c82d  push    rsi
0x18000c82e  push    rdi
0x18000c82f  push    r12
0x18000c831  push    r13
0x18000c833  push    r14
0x18000c835  push    r15
0x18000c837  sub     rsp, 58h
0x18000c83b  xor     edi, edi
0x18000c83d  mov     [rsp+98h+arg_18], rdx
0x18000c845  mov     [rax+10h], edi
0x18000c848  mov     r13, r8
0x18000c84b  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x18000c852  mov     rbx, rdx
0x18000c855  mov     [rsp+98h+arg_10], edi
0x18000c85c  mov     r14, rcx
0x18000c85f  test    rax, rax
0x18000c862  jz      short loc_18000C870
0x18000c864  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c869  mov     [rsp+98h+arg_10], eax
0x18000c870  mov     cl, [r13+1Ch]
0x18000c874  mov     r8d, edi
0x18000c877  mov     edx, [r13+18h]
0x18000c87b  sub     cl, 2
0x18000c87e  xorps   xmm0, xmm0
0x18000c881  mov     ebp, 1
0x18000c886  cmp     cl, bpl
0x18000c889  lea     rcx, [rsp+98h+var_60]
0x18000c88e  movups  [rsp+98h+var_60], xmm0
0x18000c893  setbe   r8b
0x18000c897  xor     eax, eax
0x18000c899  mov     [rsp+98h+var_50], rax
0x18000c89e  lea     rax, [rsp+98h+arg_8]
0x18000c8a6  mov     [rsp+98h+var_70], rax
0x18000c8ab  mov     [rsp+98h+var_78], rdi
0x18000c8b0  call    wil_QueryFeatureState
0x18000c8b5  mov     ecx, dword ptr [rsp+98h+var_50]
0x18000c8b9  lea     r15d, [rbp+3Fh]
0x18000c8bd  neg     ecx
0x18000c8bf  mov     ecx, dword ptr [rsp+98h+var_50+4]
0x18000c8c3  sbb     edx, edx
0x18000c8c5  and     edx, 400h
0x18000c8cb  neg     ecx
0x18000c8cd  sbb     r8d, r8d
0x18000c8d0  and     r8d, 800h
0x18000c8d7  or      r8d, edx
0x18000c8da  neg     eax
0x18000c8dc  sbb     eax, eax
0x18000c8de  and     eax, dword ptr [rsp+98h+var_60]
0x18000c8e2  and     eax, 3
0x18000c8e5  mov     edi, eax
0x18000c8e7  shl     edi, 7
0x18000c8ea  or      edi, r8d
0x18000c8ed  test    eax, eax
0x18000c8ef  jnz     short loc_18000C8FE
0x18000c8f1  mov     al, [r13+1Fh]
0x18000c8f5  neg     al
0x18000c8f7  sbb     ecx, ecx
0x18000c8f9  and     ecx, r15d
0x18000c8fc  jmp     short loc_18000C909
0x18000c8fe  xor     ecx, ecx
0x18000c900  cmp     dword ptr [rsp+98h+var_60], 2
0x18000c905  cmovz   ecx, r15d
0x18000c909  or      edi, ecx
0x18000c90b  mov     ecx, 0C00h
0x18000c910  mov     eax, edi
0x18000c912  and     eax, ecx
0x18000c914  cmp     eax, ecx
0x18000c916  jnz     short loc_18000C91D
0x18000c918  mov     r12d, ebp
0x18000c91b  jmp     short loc_18000C929
0x18000c91d  xor     r12d, r12d
0x18000c920  test    r15b, dil
0x18000c923  jz      loc_18000C9BA
0x18000c929  mov     r14, [r13+20h]
0x18000c92d  mov     esi, ebp
0x18000c92f  test    r14, r14
0x18000c932  jz      short loc_18000C9A3
0x18000c934  mov     rcx, [r14]
0x18000c937  test    rcx, rcx
0x18000c93a  jz      short loc_18000C9A3
0x18000c93c  cmp     byte ptr [rcx+1Eh], 0
0x18000c940  jnz     short loc_18000C98F
0x18000c942  cmp     byte ptr [rcx+1Dh], 0
0x18000c946  jnz     short loc_18000C98F
0x18000c948  mov     r9, [rcx]
0x18000c94b  mov     [rsp+98h+var_68], 0
0x18000c954  mov     eax, [r9]
0x18000c957  mov     dword ptr [rsp+98h+var_68], eax
0x18000c95b  test    al, 2
0x18000c95d  jz      short loc_18000C966
0x18000c95f  mov     rax, [rsp+98h+var_68]
0x18000c964  jmp     short loc_18000C976
0x18000c966  mov     rdx, [rsp+98h+var_68]
0x18000c96b  mov     r8, rcx
0x18000c96e  mov     rcx, r9
0x18000c971  call    wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState
0x18000c976  test    esi, esi
0x18000c978  jz      short loc_18000C983
0x18000c97a  test    bpl, al
0x18000c97d  jz      short loc_18000C983
0x18000c97f  mov     esi, ebp
0x18000c981  jmp     short loc_18000C985
0x18000c983  xor     esi, esi
0x18000c985  add     r14, 8
0x18000c989  test    esi, esi
0x18000c98b  jnz     short loc_18000C934
0x18000c98d  jmp     short loc_18000C9A3
0x18000c98f  test    esi, esi
0x18000c991  jz      short loc_18000C9A1
0x18000c993  cmp     byte ptr [rcx+1Fh], 0
0x18000c997  jz      short loc_18000C9A1
0x18000c999  mov     esi, ebp
0x18000c99b  add     r14, 8
0x18000c99f  jmp     short loc_18000C934
0x18000c9a1  xor     esi, esi
0x18000c9a3  mov     r14, [rsp+98h+arg_0]
0x18000c9ab  test    r12d, r12d
0x18000c9ae  jz      short loc_18000C9BC
0x18000c9b0  test    esi, esi
0x18000c9b2  jnz     short loc_18000C9BC
0x18000c9b4  btr     edi, 0Ah
0x18000c9b8  jmp     short loc_18000C9BC
0x18000c9ba  xor     esi, esi
0x18000c9bc  test    r15b, dil
0x18000c9bf  jz      short loc_18000C9C5
0x18000c9c1  test    esi, esi
0x18000c9c3  jnz     short loc_18000C9C7
0x18000c9c5  xor     ebp, ebp
0x18000c9c7  mov     r8d, [rsp+98h+arg_10]
0x18000c9cf  and     edi, 0FFFFFFFEh
0x18000c9d2  or      edi, ebp
0x18000c9d4  cmp     byte ptr [r13+1Ch], 0
0x18000c9d9  jnz     short loc_18000C9EB
0x18000c9db  mov     eax, r8d
0x18000c9de  neg     eax
0x18000c9e0  sbb     ebp, ebp
0x18000c9e2  and     ebp, [rsp+98h+arg_8]
0x18000c9e9  jmp     short loc_18000C9F2
0x18000c9eb  mov     ebp, [rsp+98h+arg_8]
0x18000c9f2  mov     r15d, 9C1h
0x18000c9f8  mov     dword ptr [rsp+98h+arg_18], ebx
0x18000c9ff  mov     esi, ebx
0x18000ca01  test    ebp, ebp
0x18000ca03  jz      short loc_18000CA24
0x18000ca05  mov     dword ptr [rsp+98h+arg_18], ebx
0x18000ca0c  test    bl, 2
0x18000ca0f  jnz     short loc_18000CA24
0x18000ca11  mov     esi, edi
0x18000ca13  xor     esi, ebx
0x18000ca15  and     esi, r15d
0x18000ca18  xor     esi, ebx
0x18000ca1a  or      esi, 2
0x18000ca1d  mov     dword ptr [rsp+98h+arg_18], esi
0x18000ca24  mov     ecx, ebx
0x18000ca26  and     ecx, 4
0x18000ca29  jnz     short loc_18000CA43
0x18000ca2b  mov     eax, esi
0x18000ca2d  mov     esi, edi
0x18000ca2f  xor     esi, eax
0x18000ca31  and     esi, 400h
0x18000ca37  xor     esi, eax
0x18000ca39  or      esi, 4
0x18000ca3c  mov     dword ptr [rsp+98h+arg_18], esi
0x18000ca43  mov     eax, ebx
0x18000ca45  lock cmpxchg [r14], esi
0x18000ca4a  jz      short loc_18000CA50
0x18000ca4c  mov     ebx, eax
0x18000ca4e  jmp     short loc_18000C9F8
0x18000ca50  test    ecx, ecx
0x18000ca52  jnz     short loc_18000CA6D
0x18000ca54  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x18000ca5b  test    rax, rax
0x18000ca5e  jz      short loc_18000CA6D
0x18000ca60  movzx   edx, byte ptr [r13+1Ch]
0x18000ca65  mov     rcx, r14
0x18000ca68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca6d  test    ebp, ebp
0x18000ca6f  jnz     short loc_18000CA7F
0x18000ca71  xor     edi, esi
0x18000ca73  and     edi, r15d
0x18000ca76  xor     edi, esi
0x18000ca78  mov     dword ptr [rsp+98h+arg_18], edi
0x18000ca7f  mov     rax, [rsp+98h+arg_18]
0x18000ca87  add     rsp, 58h
0x18000ca8b  pop     r15
0x18000ca8d  pop     r14
0x18000ca8f  pop     r13
0x18000ca91  pop     r12
0x18000ca93  pop     rdi
0x18000ca94  pop     rsi
0x18000ca95  pop     rbp
0x18000ca96  pop     rbx
0x18000ca97  retn
```
