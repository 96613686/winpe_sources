# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x18002046c`
- end: `0x1800206e0`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `628`
- prototype: `__int64 __fastcall(volatile signed __int32 *, __int64, __int64, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002046c`
- `0x18002072c`

## callees

- `0x180019780`
- `0x18002046c`
- `0x180023010`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState(
        volatile signed __int32 *a1,
        __int64 a2,
        __int64 a3,
        int a4)
{
  signed __int32 v5; // ebx
  volatile signed __int32 *v6; // r14
  int v7; // edx
  int v8; // ebp
  bool v9; // cf
  bool v10; // zf
  int FeatureState; // eax
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
  FeatureState = wil_QueryFeatureState((unsigned int)&v26, v7, v9 | (unsigned __int8)v10, a4, 0, (__int64)&v29);
  v12 = (unsigned __int8)v26 & (unsigned __int8)-(FeatureState != 0) & 3;
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
0x18002046c  mov     rax, rsp
0x18002046f  mov     [rax+8], rcx
0x180020473  push    rbx
0x180020474  push    rbp
0x180020475  push    rsi
0x180020476  push    rdi
0x180020477  push    r12
0x180020479  push    r13
0x18002047b  push    r14
0x18002047d  push    r15
0x18002047f  sub     rsp, 58h
0x180020483  xor     edi, edi
0x180020485  mov     [rsp+98h+arg_18], rdx
0x18002048d  mov     [rax+10h], edi
0x180020490  mov     r13, r8
0x180020493  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x18002049a  mov     rbx, rdx
0x18002049d  mov     [rsp+98h+arg_10], edi
0x1800204a4  mov     r14, rcx
0x1800204a7  test    rax, rax
0x1800204aa  jz      short loc_1800204B8
0x1800204ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800204b1  mov     [rsp+98h+arg_10], eax
0x1800204b8  mov     cl, [r13+1Ch]
0x1800204bc  mov     r8d, edi
0x1800204bf  mov     edx, [r13+18h]
0x1800204c3  sub     cl, 2
0x1800204c6  xorps   xmm0, xmm0
0x1800204c9  mov     ebp, 1
0x1800204ce  cmp     cl, bpl
0x1800204d1  lea     rcx, [rsp+98h+var_60]
0x1800204d6  movups  [rsp+98h+var_60], xmm0
0x1800204db  setbe   r8b
0x1800204df  xor     eax, eax
0x1800204e1  mov     [rsp+98h+var_50], rax
0x1800204e6  lea     rax, [rsp+98h+arg_8]
0x1800204ee  mov     [rsp+98h+var_70], rax
0x1800204f3  mov     [rsp+98h+var_78], rdi
0x1800204f8  call    wil_QueryFeatureState
0x1800204fd  mov     ecx, dword ptr [rsp+98h+var_50]
0x180020501  lea     r15d, [rbp+3Fh]
0x180020505  neg     ecx
0x180020507  mov     ecx, dword ptr [rsp+98h+var_50+4]
0x18002050b  sbb     edx, edx
0x18002050d  and     edx, 400h
0x180020513  neg     ecx
0x180020515  sbb     r8d, r8d
0x180020518  and     r8d, 800h
0x18002051f  or      r8d, edx
0x180020522  neg     eax
0x180020524  sbb     eax, eax
0x180020526  and     eax, dword ptr [rsp+98h+var_60]
0x18002052a  and     eax, 3
0x18002052d  mov     edi, eax
0x18002052f  shl     edi, 7
0x180020532  or      edi, r8d
0x180020535  test    eax, eax
0x180020537  jnz     short loc_180020546
0x180020539  mov     al, [r13+1Fh]
0x18002053d  neg     al
0x18002053f  sbb     ecx, ecx
0x180020541  and     ecx, r15d
0x180020544  jmp     short loc_180020551
0x180020546  xor     ecx, ecx
0x180020548  cmp     dword ptr [rsp+98h+var_60], 2
0x18002054d  cmovz   ecx, r15d
0x180020551  or      edi, ecx
0x180020553  mov     ecx, 0C00h
0x180020558  mov     eax, edi
0x18002055a  and     eax, ecx
0x18002055c  cmp     eax, ecx
0x18002055e  jnz     short loc_180020565
0x180020560  mov     r12d, ebp
0x180020563  jmp     short loc_180020571
0x180020565  xor     r12d, r12d
0x180020568  test    r15b, dil
0x18002056b  jz      loc_180020602
0x180020571  mov     r14, [r13+20h]
0x180020575  mov     esi, ebp
0x180020577  test    r14, r14
0x18002057a  jz      short loc_1800205EB
0x18002057c  mov     rcx, [r14]
0x18002057f  test    rcx, rcx
0x180020582  jz      short loc_1800205EB
0x180020584  cmp     byte ptr [rcx+1Eh], 0
0x180020588  jnz     short loc_1800205D7
0x18002058a  cmp     byte ptr [rcx+1Dh], 0
0x18002058e  jnz     short loc_1800205D7
0x180020590  mov     r9, [rcx]
0x180020593  mov     [rsp+98h+var_68], 0
0x18002059c  mov     eax, [r9]
0x18002059f  mov     dword ptr [rsp+98h+var_68], eax
0x1800205a3  test    al, 2
0x1800205a5  jz      short loc_1800205AE
0x1800205a7  mov     rax, [rsp+98h+var_68]
0x1800205ac  jmp     short loc_1800205BE
0x1800205ae  mov     rdx, [rsp+98h+var_68]
0x1800205b3  mov     r8, rcx
0x1800205b6  mov     rcx, r9
0x1800205b9  call    wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState
0x1800205be  test    esi, esi
0x1800205c0  jz      short loc_1800205CB
0x1800205c2  test    bpl, al
0x1800205c5  jz      short loc_1800205CB
0x1800205c7  mov     esi, ebp
0x1800205c9  jmp     short loc_1800205CD
0x1800205cb  xor     esi, esi
0x1800205cd  add     r14, 8
0x1800205d1  test    esi, esi
0x1800205d3  jnz     short loc_18002057C
0x1800205d5  jmp     short loc_1800205EB
0x1800205d7  test    esi, esi
0x1800205d9  jz      short loc_1800205E9
0x1800205db  cmp     byte ptr [rcx+1Fh], 0
0x1800205df  jz      short loc_1800205E9
0x1800205e1  mov     esi, ebp
0x1800205e3  add     r14, 8
0x1800205e7  jmp     short loc_18002057C
0x1800205e9  xor     esi, esi
0x1800205eb  mov     r14, [rsp+98h+arg_0]
0x1800205f3  test    r12d, r12d
0x1800205f6  jz      short loc_180020604
0x1800205f8  test    esi, esi
0x1800205fa  jnz     short loc_180020604
0x1800205fc  btr     edi, 0Ah
0x180020600  jmp     short loc_180020604
0x180020602  xor     esi, esi
0x180020604  test    r15b, dil
0x180020607  jz      short loc_18002060D
0x180020609  test    esi, esi
0x18002060b  jnz     short loc_18002060F
0x18002060d  xor     ebp, ebp
0x18002060f  mov     r8d, [rsp+98h+arg_10]
0x180020617  and     edi, 0FFFFFFFEh
0x18002061a  or      edi, ebp
0x18002061c  cmp     byte ptr [r13+1Ch], 0
0x180020621  jnz     short loc_180020633
0x180020623  mov     eax, r8d
0x180020626  neg     eax
0x180020628  sbb     ebp, ebp
0x18002062a  and     ebp, [rsp+98h+arg_8]
0x180020631  jmp     short loc_18002063A
0x180020633  mov     ebp, [rsp+98h+arg_8]
0x18002063a  mov     r15d, 9C1h
0x180020640  mov     dword ptr [rsp+98h+arg_18], ebx
0x180020647  mov     esi, ebx
0x180020649  test    ebp, ebp
0x18002064b  jz      short loc_18002066C
0x18002064d  mov     dword ptr [rsp+98h+arg_18], ebx
0x180020654  test    bl, 2
0x180020657  jnz     short loc_18002066C
0x180020659  mov     esi, edi
0x18002065b  xor     esi, ebx
0x18002065d  and     esi, r15d
0x180020660  xor     esi, ebx
0x180020662  or      esi, 2
0x180020665  mov     dword ptr [rsp+98h+arg_18], esi
0x18002066c  mov     ecx, ebx
0x18002066e  and     ecx, 4
0x180020671  jnz     short loc_18002068B
0x180020673  mov     eax, esi
0x180020675  mov     esi, edi
0x180020677  xor     esi, eax
0x180020679  and     esi, 400h
0x18002067f  xor     esi, eax
0x180020681  or      esi, 4
0x180020684  mov     dword ptr [rsp+98h+arg_18], esi
0x18002068b  mov     eax, ebx
0x18002068d  lock cmpxchg [r14], esi
0x180020692  jz      short loc_180020698
0x180020694  mov     ebx, eax
0x180020696  jmp     short loc_180020640
0x180020698  test    ecx, ecx
0x18002069a  jnz     short loc_1800206B5
0x18002069c  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x1800206a3  test    rax, rax
0x1800206a6  jz      short loc_1800206B5
0x1800206a8  movzx   edx, byte ptr [r13+1Ch]
0x1800206ad  mov     rcx, r14
0x1800206b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800206b5  test    ebp, ebp
0x1800206b7  jnz     short loc_1800206C7
0x1800206b9  xor     edi, esi
0x1800206bb  and     edi, r15d
0x1800206be  xor     edi, esi
0x1800206c0  mov     dword ptr [rsp+98h+arg_18], edi
0x1800206c7  mov     rax, [rsp+98h+arg_18]
0x1800206cf  add     rsp, 58h
0x1800206d3  pop     r15
0x1800206d5  pop     r14
0x1800206d7  pop     r13
0x1800206d9  pop     r12
0x1800206db  pop     rdi
0x1800206dc  pop     rsi
0x1800206dd  pop     rbp
0x1800206de  pop     rbx
0x1800206df  retn
```
