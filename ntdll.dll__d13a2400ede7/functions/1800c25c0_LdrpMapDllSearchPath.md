# LdrpMapDllSearchPath

- ea: `0x1800c25c0`
- end: `0x1800c29ba`
- name: `LdrpMapDllSearchPath`
- size: `1018`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180025688`
- `0x1800c20bc`

## callees

- `0x180017e90`
- `0x1800183a0`
- `0x18001d490`
- `0x180027434`
- `0x18002782c`
- `0x180028ac0`
- `0x18002b9f0`
- `0x18006f100`
- `0x180070814`
- `0x18007b1a0`
- `0x1800c0e80`
- `0x1800c25c0`
- `0x1800c29c0`
- `0x1800c2f9c`
- `0x1800c3088`
- `0x1800c358c`
- `0x180162810`
- `0x18016f030`

## pseudocode

```c
__int64 __fastcall LdrpMapDllSearchPath(__int64 ArgList)
{
  __int64 v2; // r9
  __int64 v3; // r13
  volatile signed __int32 *v4; // rdi
  int v5; // r14d
  __int64 *v6; // r12
  int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  int LoadedDllByNameLockHeld; // ebx
  int v13; // eax
  int v14; // edi
  int v15; // r15d
  __int64 *v16; // rdx
  __int64 v17; // r8
  __int128 v19; // xmm1
  __int64 v20; // r8
  __int64 *v21; // r14
  __int64 *i; // rbx
  __int64 v23; // rcx
  bool v24; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v25; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v26[2]; // [rsp+58h] [rbp-A8h] BYREF
  volatile signed __int32 *v27; // [rsp+68h] [rbp-98h] BYREF
  __int64 v28[2]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v29; // [rsp+80h] [rbp-80h] BYREF
  __int64 v30[16]; // [rsp+90h] [rbp-70h] BYREF
  UNICODE_STRING v31; // [rsp+110h] [rbp+10h] BYREF
  _WORD v32[128]; // [rsp+120h] [rbp+20h] BYREF

  *(_OWORD *)v28 = 0;
  memset_thunk_772440563353939046(v30, 0, 0x80u);
  memset_thunk_772440563353939046(&v31, 0, 0x110u);
  v2 = *(_QWORD *)(ArgList + 48);
  v3 = *(_QWORD *)(ArgList + 56);
  v4 = 0;
  v31.Buffer = v32;
  v24 = 0;
  v5 = 0;
  *(_DWORD *)&v31.Length = 0x1000000;
  v32[0] = 0;
  v25 = 0;
  v29 = 0;
  *(_OWORD *)v26 = 0;
  if ( v2 && (v20 = *(unsigned int *)(v2 + 280), (((LdrpPolicyBits & 4) != 0 ? 32512 : 31488) & (unsigned int)v20) != 0) )
  {
    LdrpInitializeDllPath(*(int **)(v2 + 80), v20 & ((-(__int64)((LdrpPolicyBits & 4) != 0) & 0x400) + 31488) | 1, v30);
    v6 = v30;
  }
  else
  {
    v6 = *(__int64 **)(ArgList + 16);
  }
  while ( 1 )
  {
    v7 = LdrpSearchPath(
           (unsigned __int16 *)ArgList,
           (__int64)v6,
           (*(_DWORD *)(ArgList + 32) & 8) != 0,
           (__int16 **)&v29,
           (__m128i *)&v31,
           (__int64)v28,
           (unsigned __int16 *)v26,
           &v24,
           (__int64)&v25);
    LoadedDllByNameLockHeld = v7;
    if ( v24 )
    {
      v9 = *(_DWORD *)(v3 + 104) | 1u;
      *(_DWORD *)(v3 + 104) = v9;
    }
    if ( v7 == -1073741515 )
      break;
    if ( v7 < 0 )
      goto LABEL_19;
LABEL_9:
    if ( !*(_QWORD *)(ArgList + 176) )
    {
      LoadedDllByNameLockHeld = LdrpAppCompatRedirect(
                                  ArgList,
                                  (unsigned int)v26,
                                  (unsigned int)v28,
                                  (unsigned int)&v31,
                                  v7);
      if ( LoadedDllByNameLockHeld < 0 )
        goto LABEL_19;
      if ( (*(_DWORD *)(ArgList + 32) & 0x10000) != 0 )
        v25 |= 1u;
      v13 = LdrpHashUnicodeString(v28);
      *(_DWORD *)(v3 + 264) = v13;
      v14 = *(_DWORD *)(ArgList + 32);
      v15 = v13;
      v27 = 0;
      RtlAcquireSRWLockExclusive(LdrpModuleDatatableLock);
      v16 = v26;
      if ( (v14 & 0x20) != 0 )
        LODWORD(v16) = 0;
      LoadedDllByNameLockHeld = LdrpFindLoadedDllByNameLockHeld(
                                  (unsigned int)v28,
                                  (_DWORD)v16,
                                  v14,
                                  (unsigned int)&v27,
                                  v15);
      if ( LoadedDllByNameLockHeld == -1073741515 && (v14 & 8) != 0 )
      {
        v21 = &LdrpHashTable[2 * (v15 & 0x1F)];
        for ( i = (__int64 *)*v21; ; i = (__int64 *)*i )
        {
          if ( i == v21 )
          {
            v4 = v27;
            LoadedDllByNameLockHeld = -1073741515;
            goto LABEL_18;
          }
          v4 = (volatile signed __int32 *)(i - 14);
          if ( v15 == *((_DWORD *)i + 38) )
          {
            LOBYTE(v17) = 1;
            if ( (unsigned __int8)RtlEqualUnicodeString(v26, v4 + 18, v17) )
              break;
          }
        }
        v23 = *((_QWORD *)v4 + 19);
        if ( *(_DWORD *)(v23 + 24) != -1 && (*(_DWORD *)(*(_QWORD *)v23 - 56LL) & 0x20) == 0 )
          _InterlockedIncrement(v4 + 69);
        LoadedDllByNameLockHeld = 0;
        *((_DWORD *)v4 + 26) |= 1u;
      }
      else
      {
        v4 = v27;
      }
LABEL_18:
      RtlReleaseSRWLockExclusive(LdrpModuleDatatableLock);
      if ( LoadedDllByNameLockHeld != -1073741515 )
        goto LABEL_19;
    }
    LdrpFreeUnicodeString(v3 + 72);
    v19 = *(_OWORD *)v28;
    *(_OWORD *)(v3 + 72) = *(_OWORD *)v26;
    *(_OWORD *)(v3 + 88) = v19;
    *(_OWORD *)v26 = 0;
    LoadedDllByNameLockHeld = LdrpMapDllNtFileName(ArgList, &v31);
    if ( LoadedDllByNameLockHeld != 1073741838 )
      goto LABEL_19;
    v5 = 1;
    if ( v32 != v31.Buffer )
      RtlpSysVolFree(v31.Buffer);
    *(_DWORD *)&v31.Length = 0x1000000;
    v31.Buffer = v32;
    v32[0] = 0;
  }
  if ( !v5 )
    goto LABEL_9;
  LoadedDllByNameLockHeld = -1073741701;
LABEL_19:
  if ( v4 )
  {
    LdrpLoadContextReplaceModule(ArgList, v4);
  }
  else if ( (unsigned __int8)LdrpIsSecurityEtwLoggingEnabled(v9, v8, v10, v11) )
  {
    LdrpLogEtwDllSearchResults(v25, ArgList);
  }
  if ( v32 != v31.Buffer )
    RtlpSysVolFree(v31.Buffer);
  v31.Buffer = v32;
  *(_DWORD *)&v31.Length = 0x1000000;
  v32[0] = 0;
  if ( v26[1] )
  {
    RtlpSysVolFree(v26[1]);
    v26[1] = 0;
  }
  LODWORD(v26[0]) = 0;
  LdrpReleaseDllPath(v30);
  return (unsigned int)LoadedDllByNameLockHeld;
}

```

## disassembly

```asm
0x1800c25c0  push    rbp
0x1800c25c2  push    rbx
0x1800c25c3  push    rsi
0x1800c25c4  push    rdi
0x1800c25c5  push    r12
0x1800c25c7  push    r13
0x1800c25c9  push    r14
0x1800c25cb  push    r15
0x1800c25cd  lea     rbp, [rsp-138h]
0x1800c25d5  sub     rsp, 238h
0x1800c25dc  mov     rax, cs:__security_cookie
0x1800c25e3  xor     rax, rsp
0x1800c25e6  mov     [rbp+170h+var_50], rax
0x1800c25ed  mov     rsi, rcx
0x1800c25f0  xorps   xmm0, xmm0
0x1800c25f3  lea     rcx, [rbp+170h+var_1E0]; void *
0x1800c25f7  xor     edx, edx; Val
0x1800c25f9  mov     r8d, 80h; Size
0x1800c25ff  movups  xmmword ptr [rsp+270h+var_200], xmm0
0x1800c2604  call    memset$thunk$772440563353939046
0x1800c2609  xor     edx, edx; Val
0x1800c260b  lea     rcx, [rbp+170h+var_160]; void *
0x1800c260f  mov     r8d, 110h; Size
0x1800c2615  call    memset$thunk$772440563353939046
0x1800c261a  mov     r9, [rsi+30h]
0x1800c261e  lea     rax, [rbp+170h+var_150]
0x1800c2622  mov     r13, [rsi+38h]
0x1800c2626  xor     edi, edi
0x1800c2628  xorps   xmm0, xmm0
0x1800c262b  mov     [rbp+170h+var_158], rax
0x1800c262f  xor     eax, eax
0x1800c2631  mov     byte ptr [rsp+270h+var_220], dil
0x1800c2636  xor     r14d, r14d
0x1800c2639  mov     dword ptr [rbp+170h+var_160], 1000000h
0x1800c2640  mov     [rbp+170h+var_150], ax
0x1800c2644  mov     r15d, 100h
0x1800c264a  mov     dword ptr [rsp+270h+var_220+4], eax
0x1800c264e  movups  [rbp+170h+var_1F0], xmm0
0x1800c2652  movups  xmmword ptr [rsp+270h+var_218], xmm0
0x1800c2657  test    r9, r9
0x1800c265a  jnz     loc_1800C28A5
0x1800c2660  mov     r12, [rsi+10h]
0x1800c2664  mov     r8d, [rsi+20h]
0x1800c2668  lea     rax, [rsp+270h+var_220+4]
0x1800c266d  mov     [rsp+270h+var_230], rax; __int64
0x1800c2672  lea     r9, [rbp+170h+var_1F0]
0x1800c2676  lea     rax, [rsp+270h+var_220]
0x1800c267b  shr     r8d, 3
0x1800c267f  mov     [rsp+270h+var_238], rax; __int64
0x1800c2684  and     r8b, 1
0x1800c2688  lea     rax, [rsp+270h+var_218]
0x1800c268d  mov     rdx, r12
0x1800c2690  mov     [rsp+270h+var_240], rax; __int64
0x1800c2695  mov     rcx, rsi; ArgList
0x1800c2698  lea     rax, [rsp+270h+var_200]
0x1800c269d  mov     [rsp+270h+var_248], rax; __int64
0x1800c26a2  lea     rax, [rbp+170h+var_160]
0x1800c26a6  mov     [rsp+270h+var_250], rax; __int64
0x1800c26ab  call    LdrpSearchPath
0x1800c26b0  cmp     byte ptr [rsp+270h+var_220], 0
0x1800c26b5  mov     ebx, eax
0x1800c26b7  jnz     loc_1800C28FC
0x1800c26bd  cmp     eax, 0C0000135h
0x1800c26c2  jz      short loc_1800C26CE
0x1800c26c4  test    eax, eax
0x1800c26c6  js      loc_1800C279B
0x1800c26cc  jmp     short loc_1800C26D7
0x1800c26ce  test    r14d, r14d
0x1800c26d1  jnz     loc_1800C29B0
0x1800c26d7  cmp     qword ptr [rsi+0B0h], 0
0x1800c26df  jnz     loc_1800C2833
0x1800c26e5  lea     r9, [rbp+170h+var_160]
0x1800c26e9  mov     dword ptr [rsp+270h+var_250], eax
0x1800c26ed  lea     r8, [rsp+270h+var_200]
0x1800c26f2  mov     rcx, rsi
0x1800c26f5  lea     rdx, [rsp+270h+var_218]
0x1800c26fa  call    LdrpAppCompatRedirect
0x1800c26ff  mov     ebx, eax
0x1800c2701  test    eax, eax
0x1800c2703  js      loc_1800C279B
0x1800c2709  test    dword ptr [rsi+20h], 10000h
0x1800c2710  jnz     loc_1800C29A6
0x1800c2716  lea     rcx, [rsp+270h+var_200]
0x1800c271b  call    LdrpHashUnicodeString
0x1800c2720  mov     [r13+108h], eax
0x1800c2727  lea     rcx, LdrpModuleDatatableLock
0x1800c272e  mov     edi, [rsi+20h]
0x1800c2731  mov     r15d, eax
0x1800c2734  mov     [rsp+270h+var_208], 0
0x1800c273d  call    RtlAcquireSRWLockExclusive
0x1800c2742  mov     ecx, 0
0x1800c2747  mov     dword ptr [rsp+270h+var_250], r15d
0x1800c274c  test    dil, 20h
0x1800c2750  lea     rdx, [rsp+270h+var_218]
0x1800c2755  lea     r9, [rsp+270h+var_208]
0x1800c275a  mov     r8d, edi
0x1800c275d  cmovnz  rdx, rcx
0x1800c2761  lea     rcx, [rsp+270h+var_200]
0x1800c2766  call    LdrpFindLoadedDllByNameLockHeld
0x1800c276b  mov     ebx, eax
0x1800c276d  cmp     eax, 0C0000135h
0x1800c2772  jnz     short loc_1800C277E
0x1800c2774  test    dil, 8
0x1800c2778  jnz     loc_1800C291C
0x1800c277e  mov     rdi, [rsp+270h+var_208]
0x1800c2783  lea     rcx, LdrpModuleDatatableLock
0x1800c278a  call    RtlReleaseSRWLockExclusive
0x1800c278f  cmp     ebx, 0C0000135h
0x1800c2795  jz      loc_1800C282D
0x1800c279b  test    rdi, rdi
0x1800c279e  jnz     loc_1800C290C
0x1800c27a4  call    LdrpIsSecurityEtwLoggingEnabled
0x1800c27a9  test    al, al
0x1800c27ab  jz      short loc_1800C27B9
0x1800c27ad  mov     ecx, dword ptr [rsp+270h+var_220+4]
0x1800c27b1  mov     rdx, rsi
0x1800c27b4  call    LdrpLogEtwDllSearchResults
0x1800c27b9  mov     rcx, [rbp+170h+var_158]
0x1800c27bd  lea     rax, [rbp+170h+var_150]
0x1800c27c1  cmp     rax, rcx
0x1800c27c4  jz      short loc_1800C27CB
0x1800c27c6  call    RtlpSysVolFree
0x1800c27cb  mov     rcx, [rsp+270h+var_218+8]
0x1800c27d0  lea     rax, [rbp+170h+var_150]
0x1800c27d4  mov     [rbp+170h+var_158], rax
0x1800c27d8  xor     eax, eax
0x1800c27da  mov     dword ptr [rbp+170h+var_160], 1000000h
0x1800c27e1  mov     [rbp+170h+var_150], ax
0x1800c27e5  test    rcx, rcx
0x1800c27e8  jz      short loc_1800C27F8
0x1800c27ea  call    RtlpSysVolFree
0x1800c27ef  mov     [rsp+270h+var_218+8], 0
0x1800c27f8  xor     eax, eax
0x1800c27fa  lea     rcx, [rbp+170h+var_1E0]
0x1800c27fe  mov     dword ptr [rsp+270h+var_218], eax
0x1800c2802  call    LdrpReleaseDllPath
0x1800c2807  mov     eax, ebx
0x1800c2809  mov     rcx, [rbp+170h+var_50]
0x1800c2810  xor     rcx, rsp; StackCookie
0x1800c2813  call    __security_check_cookie
0x1800c2818  add     rsp, 238h
0x1800c281f  pop     r15
0x1800c2821  pop     r14
0x1800c2823  pop     r13
0x1800c2825  pop     r12
0x1800c2827  pop     rdi
0x1800c2828  pop     rsi
0x1800c2829  pop     rbx
0x1800c282a  pop     rbp
0x1800c282b  retn
0x1800c282d  mov     r15d, 100h
0x1800c2833  lea     rcx, [r13+48h]
0x1800c2837  call    LdrpFreeUnicodeString
0x1800c283c  movups  xmm0, xmmword ptr [rsp+270h+var_218]
0x1800c2841  lea     rdx, [rbp+170h+var_160]
0x1800c2845  mov     rcx, rsi
0x1800c2848  movups  xmm1, xmmword ptr [rsp+270h+var_200]
0x1800c284d  movdqu  xmmword ptr [r13+48h], xmm0
0x1800c2853  xorps   xmm0, xmm0
0x1800c2856  movdqu  xmmword ptr [r13+58h], xmm1
0x1800c285c  movups  xmmword ptr [rsp+270h+var_218], xmm0
0x1800c2861  call    LdrpMapDllNtFileName
0x1800c2866  mov     ebx, eax
0x1800c2868  cmp     eax, 4000000Eh
0x1800c286d  jnz     loc_1800C279B
0x1800c2873  mov     rcx, [rbp+170h+var_158]
0x1800c2877  lea     rax, [rbp+170h+var_150]
0x1800c287b  mov     r14d, 1
0x1800c2881  cmp     rax, rcx
0x1800c2884  jz      short loc_1800C288B
0x1800c2886  call    RtlpSysVolFree
0x1800c288b  lea     rax, [rbp+170h+var_150]
0x1800c288f  mov     dword ptr [rbp+170h+var_160], 1000000h
0x1800c2896  mov     [rbp+170h+var_158], rax
0x1800c289a  xor     eax, eax
0x1800c289c  mov     [rbp+170h+var_150], ax
0x1800c28a0  jmp     loc_1800C2664
0x1800c28a5  mov     edx, cs:LdrpPolicyBits
0x1800c28ab  mov     r10d, 7B00h
0x1800c28b1  mov     r8d, [r9+118h]
0x1800c28b8  and     edx, 4
0x1800c28bb  mov     eax, edx
0x1800c28bd  neg     eax
0x1800c28bf  mov     eax, 400h
0x1800c28c4  sbb     ecx, ecx
0x1800c28c6  and     ecx, eax
0x1800c28c8  add     ecx, r10d
0x1800c28cb  test    r8d, ecx
0x1800c28ce  jz      loc_1800C2660
0x1800c28d4  mov     rcx, [r9+50h]
0x1800c28d8  neg     edx
0x1800c28da  sbb     rdx, rdx
0x1800c28dd  and     rdx, rax
0x1800c28e0  add     rdx, r10
0x1800c28e3  and     rdx, r8
0x1800c28e6  lea     r8, [rbp+170h+var_1E0]
0x1800c28ea  or      rdx, 1
0x1800c28ee  call    LdrpInitializeDllPath
0x1800c28f3  lea     r12, [rbp+170h+var_1E0]
0x1800c28f7  jmp     loc_1800C2664
0x1800c28fc  mov     ecx, [r13+68h]
0x1800c2900  or      ecx, 1
0x1800c2903  mov     [r13+68h], ecx
0x1800c2907  jmp     loc_1800C26BD
0x1800c290c  mov     rdx, rdi
0x1800c290f  mov     rcx, rsi
0x1800c2912  call    LdrpLoadContextReplaceModule
0x1800c2917  jmp     loc_1800C27B9
0x1800c291c  mov     r14d, r15d
0x1800c291f  lea     rcx, LdrpHashTable
0x1800c2926  and     r14d, 1Fh
0x1800c292a  shl     r14, 4
0x1800c292e  add     r14, rcx
0x1800c2931  xor     al, al
0x1800c2933  mov     rbx, [r14]
0x1800c2936  cmp     rbx, r14
0x1800c2939  jz      short loc_1800C2993
0x1800c293b  lea     rdi, [rbx-70h]
0x1800c293f  cmp     r15d, [rdi+108h]
0x1800c2946  jz      short loc_1800C294D
0x1800c2948  mov     rbx, [rbx]
0x1800c294b  jmp     short loc_1800C2936
0x1800c294d  lea     rdx, [rdi+48h]
0x1800c2951  mov     r8b, 1
0x1800c2954  lea     rcx, [rsp+270h+var_218]
0x1800c2959  call    RtlEqualUnicodeString
0x1800c295e  test    al, al
0x1800c2960  jz      short loc_1800C2948
0x1800c2962  mov     rcx, [rdi+98h]
0x1800c2969  mov     eax, [rcx+18h]
0x1800c296c  cmp     eax, 0FFFFFFFFh
0x1800c296f  jz      short loc_1800C2983
0x1800c2971  mov     rax, [rcx]
0x1800c2974  mov     ecx, [rax-38h]
0x1800c2977  test    cl, 20h
0x1800c297a  jnz     short loc_1800C2983
0x1800c297c  lock inc dword ptr [rdi+114h]
0x1800c2983  mov     eax, [rdi+68h]
0x1800c2986  xor     ebx, ebx
0x1800c2988  or      eax, 1
0x1800c298b  mov     [rdi+68h], eax
0x1800c298e  jmp     loc_1800C2783
0x1800c2993  mov     rdi, [rsp+270h+var_208]
0x1800c2998  test    al, al
0x1800c299a  jnz     short loc_1800C2983
0x1800c299c  mov     ebx, 0C0000135h
0x1800c29a1  jmp     loc_1800C2783
0x1800c29a6  or      dword ptr [rsp+270h+var_220+4], 1
0x1800c29ab  jmp     loc_1800C2716
0x1800c29b0  mov     ebx, 0C000007Bh
0x1800c29b5  jmp     loc_1800C279B
```
