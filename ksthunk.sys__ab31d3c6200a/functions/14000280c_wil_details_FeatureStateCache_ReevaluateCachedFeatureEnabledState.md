# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x14000280c`
- end: `0x140002a63`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `599`
- prototype: `__int64 __fastcall(volatile signed __int32 *, __int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000280c`
- `0x140002ac4`

## callees

- `0x14000280c`
- `0x140004110`
- `0x1400041f0`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140002883`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140002883`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState(
        volatile signed __int32 *a1,
        __int64 a2,
        __int64 a3)
{
  unsigned int v3; // r15d
  signed __int32 v5; // ebx
  char v7; // cl
  BOOL v8; // ebp
  bool v9; // cf
  bool v10; // zf
  __int64 v11; // rcx
  int v12; // eax
  int v13; // edx
  int v14; // ecx
  int v15; // r9d
  int v16; // r10d
  int v17; // eax
  int v18; // ecx
  unsigned int v19; // r8d
  int v20; // esi
  unsigned int ***v21; // rdi
  unsigned int **v22; // rcx
  unsigned __int8 v23; // al
  BOOL v24; // ecx
  unsigned int v25; // eax
  unsigned int v26; // esi
  signed __int32 v27; // edi
  signed __int32 v28; // eax
  __int64 v31; // [rsp+20h] [rbp-68h]
  __int64 v32; // [rsp+28h] [rbp-60h]
  __int64 v33; // [rsp+30h] [rbp-58h] BYREF
  __int64 v34; // [rsp+38h] [rbp-50h] BYREF
  int v35; // [rsp+40h] [rbp-48h]

  v3 = 0;
  v5 = a2;
  if ( g_wil_details_ensureSubscribedToFeatureConfigurationChanges )
    v3 = g_wil_details_ensureSubscribedToFeatureConfigurationChanges(a1);
  v7 = *(_BYTE *)(a3 + 28);
  v33 = 0;
  v7 -= 2;
  v8 = 1;
  v9 = v7 == 0;
  v10 = v7 == 1;
  v11 = *(unsigned int *)(a3 + 24);
  v34 = 0;
  v35 = 0;
  v12 = RtlQueryFeatureConfiguration(v11, !v9 && !v10, &v33, &v34, a2);
  if ( v12 )
  {
    v13 = 0;
    if ( v12 == 279 )
    {
      v14 = 1;
      v15 = 8 * (BYTE4(v34) & 0x80);
    }
    else
    {
      v14 = 0;
      v15 = 0;
    }
  }
  else
  {
    v13 = (HIDWORD(v34) >> 4) & 3;
    v14 = 1;
    v15 = 8 * (BYTE4(v34) & 0x80);
    if ( (v34 & 0x4000000000LL) != 0 )
    {
      v16 = 2048;
      goto LABEL_10;
    }
  }
  v16 = 0;
LABEL_10:
  v17 = v14 != 0 ? v13 : 0;
  if ( v17 )
  {
    v18 = 64;
    if ( v13 != 2 )
      v18 = 0;
  }
  else
  {
    v18 = *(_BYTE *)(a3 + 31) != 0 ? 0x40 : 0;
  }
  v19 = v18 | v16 | v15 | (v17 << 7);
  v20 = v19 | (v19 >> 6) & 1;
  if ( ((v19 >> 6) & 1) != 0 )
  {
    v21 = *(unsigned int ****)(a3 + 32);
    if ( v21 )
    {
      while ( (v20 & 1) != 0 )
      {
        v22 = *v21;
        if ( !*v21 )
          break;
        if ( *((_BYTE *)v22 + 30) || *((_BYTE *)v22 + 29) )
        {
          v25 = (v20 & 1) != 0 && *((_BYTE *)v22 + 31);
          v26 = v20 & 0xFFFFFFFE;
        }
        else
        {
          v32 = **v22;
          if ( (v32 & 2) != 0 )
            v23 = **v22;
          else
            v23 = wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState(*v22, v32, v22);
          v24 = (v23 & (unsigned __int8)v20 & 1) != 0;
          v25 = v20 & 0xFFFFFFFE;
          v26 = v24;
        }
        v20 = v25 | v26;
        ++v21;
      }
    }
  }
  if ( !*(_BYTE *)(a3 + 28) )
    v8 = v3 != 0;
  while ( 1 )
  {
    LODWORD(v31) = v5;
    v27 = v5;
    if ( v8 )
    {
      LODWORD(v31) = v5;
      if ( (v5 & 2) == 0 )
      {
        v27 = v5 ^ ((unsigned __int16)v5 ^ (unsigned __int16)v20) & 0x9C1 | 2;
        LODWORD(v31) = v27;
      }
    }
    if ( (v5 & 4) == 0 )
    {
      v27 = v27 ^ ((unsigned __int16)v20 ^ (unsigned __int16)v27) & 0x400 | 4;
      LODWORD(v31) = v27;
    }
    v28 = _InterlockedCompareExchange(a1, v27, v5);
    if ( v5 == v28 )
      break;
    v5 = v28;
  }
  if ( (v5 & 4) == 0 && g_wil_details_subscribeFeatureStateCacheToConfigurationChanges )
    g_wil_details_subscribeFeatureStateCacheToConfigurationChanges(a1, *(unsigned __int8 *)(a3 + 28), v3);
  if ( !v8 )
    LODWORD(v31) = v27 ^ ((unsigned __int16)v20 ^ (unsigned __int16)v27) & 0x9C1;
  return v31;
}

```

## disassembly

```asm
0x14000280c  push    rbx
0x14000280e  push    rbp
0x14000280f  push    rsi
0x140002810  push    rdi
0x140002811  push    r12
0x140002813  push    r14
0x140002815  push    r15
0x140002817  sub     rsp, 50h
0x14000281b  mov     rax, cs:__security_cookie
0x140002822  xor     rax, rsp
0x140002825  mov     [rsp+88h+var_40], rax
0x14000282a  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x140002831  xor     r15d, r15d
0x140002834  mov     [rsp+88h+var_68], rdx
0x140002839  mov     r14, r8
0x14000283c  mov     rbx, rdx
0x14000283f  mov     r12, rcx
0x140002842  test    rax, rax
0x140002845  jz      short loc_14000284F
0x140002847  call    _guard_dispatch_icall
0x14000284c  mov     r15d, eax
0x14000284f  mov     cl, [r14+1Ch]
0x140002853  lea     r9, [rsp+88h+var_50]
0x140002858  xor     edx, edx
0x14000285a  mov     [rsp+88h+var_58], 0
0x140002863  sub     cl, 2
0x140002866  lea     r8, [rsp+88h+var_58]
0x14000286b  lea     ebp, [rdx+1]
0x14000286e  cmp     cl, bpl
0x140002871  mov     ecx, [r14+18h]
0x140002875  setnbe  dl
0x140002878  xor     eax, eax
0x14000287a  mov     [rsp+88h+var_50], rax
0x14000287f  mov     [rsp+88h+var_48], eax
0x140002883  call    cs:__imp_RtlQueryFeatureConfiguration
0x14000288a  nop     dword ptr [rax+rax+00h]
0x14000288f  test    eax, eax
0x140002891  jnz     short loc_1400028BD
0x140002893  mov     ecx, dword ptr [rsp+88h+var_50+4]
0x140002897  mov     edx, ecx
0x140002899  mov     eax, ecx
0x14000289b  shr     edx, 4
0x14000289e  and     eax, 80h
0x1400028a3  and     edx, 3
0x1400028a6  test    cl, 40h
0x1400028a9  mov     ecx, ebp
0x1400028ab  lea     r9d, ds:0[rax*8]
0x1400028b3  jz      short loc_1400028E0
0x1400028b5  mov     r10d, 800h
0x1400028bb  jmp     short loc_1400028E3
0x1400028bd  xor     edx, edx
0x1400028bf  cmp     eax, 117h
0x1400028c4  jnz     short loc_1400028DB
0x1400028c6  mov     eax, dword ptr [rsp+88h+var_50+4]
0x1400028ca  mov     ecx, ebp
0x1400028cc  and     eax, 80h
0x1400028d1  lea     r9d, ds:0[rax*8]
0x1400028d9  jmp     short loc_1400028E0
0x1400028db  xor     ecx, ecx
0x1400028dd  xor     r9d, r9d
0x1400028e0  xor     r10d, r10d
0x1400028e3  neg     ecx
0x1400028e5  sbb     eax, eax
0x1400028e7  and     eax, edx
0x1400028e9  mov     r8d, eax
0x1400028ec  shl     r8d, 7
0x1400028f0  or      r8d, r9d
0x1400028f3  or      r8d, r10d
0x1400028f6  test    eax, eax
0x1400028f8  jnz     short loc_140002907
0x1400028fa  mov     al, [r14+1Fh]
0x1400028fe  neg     al
0x140002900  sbb     ecx, ecx
0x140002902  and     ecx, 40h
0x140002905  jmp     short loc_140002914
0x140002907  xor     eax, eax
0x140002909  mov     ecx, 40h ; '@'
0x14000290e  cmp     edx, 2
0x140002911  cmovnz  ecx, eax
0x140002914  or      r8d, ecx
0x140002917  mov     eax, r8d
0x14000291a  shr     eax, 6
0x14000291d  and     eax, ebp
0x14000291f  mov     esi, eax
0x140002921  or      esi, r8d
0x140002924  test    eax, eax
0x140002926  jz      loc_1400029B0
0x14000292c  mov     rdi, [r14+20h]
0x140002930  test    rdi, rdi
0x140002933  jz      short loc_1400029B0
0x140002935  jmp     short loc_1400029AB
0x140002937  mov     rcx, [rdi]
0x14000293a  test    rcx, rcx
0x14000293d  jz      short loc_1400029B0
0x14000293f  cmp     byte ptr [rcx+1Eh], 0
0x140002943  jnz     short loc_140002991
0x140002945  cmp     byte ptr [rcx+1Dh], 0
0x140002949  jnz     short loc_140002991
0x14000294b  mov     r9, [rcx]
0x14000294e  mov     [rsp+88h+var_60], 0
0x140002957  mov     eax, [r9]
0x14000295a  mov     dword ptr [rsp+88h+var_60], eax
0x14000295e  test    al, 2
0x140002960  jz      short loc_140002969
0x140002962  mov     rax, [rsp+88h+var_60]
0x140002967  jmp     short loc_140002979
0x140002969  mov     rdx, [rsp+88h+var_60]
0x14000296e  mov     r8, rcx
0x140002971  mov     rcx, r9
0x140002974  call    wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState
0x140002979  mov     ecx, esi
0x14000297b  and     ecx, eax
0x14000297d  mov     eax, esi
0x14000297f  test    bpl, cl
0x140002982  mov     ecx, 0
0x140002987  setnz   cl
0x14000298a  and     eax, 0FFFFFFFEh
0x14000298d  mov     esi, ecx
0x14000298f  jmp     short loc_1400029A5
0x140002991  test    bpl, sil
0x140002994  jz      short loc_1400029A0
0x140002996  cmp     byte ptr [rcx+1Fh], 0
0x14000299a  jz      short loc_1400029A0
0x14000299c  mov     eax, ebp
0x14000299e  jmp     short loc_1400029A2
0x1400029a0  xor     eax, eax
0x1400029a2  and     esi, 0FFFFFFFEh
0x1400029a5  or      esi, eax
0x1400029a7  add     rdi, 8
0x1400029ab  test    bpl, sil
0x1400029ae  jnz     short loc_140002937
0x1400029b0  cmp     byte ptr [r14+1Ch], 0
0x1400029b5  jnz     short loc_1400029C0
0x1400029b7  mov     eax, r15d
0x1400029ba  neg     eax
0x1400029bc  sbb     ecx, ecx
0x1400029be  and     ebp, ecx
0x1400029c0  mov     dword ptr [rsp+88h+var_68], ebx
0x1400029c4  mov     edi, ebx
0x1400029c6  test    ebp, ebp
0x1400029c8  jz      short loc_1400029E6
0x1400029ca  mov     dword ptr [rsp+88h+var_68], ebx
0x1400029ce  test    bl, 2
0x1400029d1  jnz     short loc_1400029E6
0x1400029d3  mov     edi, esi
0x1400029d5  xor     edi, ebx
0x1400029d7  and     edi, 9C1h
0x1400029dd  xor     edi, ebx
0x1400029df  or      edi, 2
0x1400029e2  mov     dword ptr [rsp+88h+var_68], edi
0x1400029e6  mov     ecx, ebx
0x1400029e8  and     ecx, 4
0x1400029eb  jnz     short loc_140002A00
0x1400029ed  mov     eax, edi
0x1400029ef  xor     edi, esi
0x1400029f1  and     edi, 400h
0x1400029f7  xor     edi, eax
0x1400029f9  or      edi, 4
0x1400029fc  mov     dword ptr [rsp+88h+var_68], edi
0x140002a00  mov     eax, ebx
0x140002a02  lock cmpxchg [r12], edi
0x140002a08  jz      short loc_140002A0E
0x140002a0a  mov     ebx, eax
0x140002a0c  jmp     short loc_1400029C0
0x140002a0e  test    ecx, ecx
0x140002a10  jnz     short loc_140002A2E
0x140002a12  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x140002a19  test    rax, rax
0x140002a1c  jz      short loc_140002A2E
0x140002a1e  movzx   edx, byte ptr [r14+1Ch]
0x140002a23  mov     r8d, r15d
0x140002a26  mov     rcx, r12
0x140002a29  call    _guard_dispatch_icall
0x140002a2e  test    ebp, ebp
0x140002a30  jnz     short loc_140002A41
0x140002a32  mov     eax, edi
0x140002a34  xor     eax, esi
0x140002a36  and     eax, 9C1h
0x140002a3b  xor     eax, edi
0x140002a3d  mov     dword ptr [rsp+88h+var_68], eax
0x140002a41  mov     rax, [rsp+88h+var_68]
0x140002a46  mov     rcx, [rsp+88h+var_40]
0x140002a4b  xor     rcx, rsp; StackCookie
0x140002a4e  call    __security_check_cookie
0x140002a53  add     rsp, 50h
0x140002a57  pop     r15
0x140002a59  pop     r14
0x140002a5b  pop     r12
0x140002a5d  pop     rdi
0x140002a5e  pop     rsi
0x140002a5f  pop     rbp
0x140002a60  pop     rbx
0x140002a61  retn
```
