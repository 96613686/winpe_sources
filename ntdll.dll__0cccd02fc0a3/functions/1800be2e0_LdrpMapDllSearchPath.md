# LdrpMapDllSearchPath

- ea: `0x1800be2e0`
- end: `0x1800be6da`
- name: `LdrpMapDllSearchPath`
- size: `1018`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180025698`
- `0x1800bdddc`

## callees

- `0x180017e90`
- `0x1800183a0`
- `0x18001d490`
- `0x180027550`
- `0x18002793c`
- `0x180028bd0`
- `0x18002c6f0`
- `0x180052720`
- `0x180053e34`
- `0x18005e7c0`
- `0x1800bcba0`
- `0x1800be2e0`
- `0x1800be6e0`
- `0x1800becbc`
- `0x1800beda8`
- `0x1800bf2ac`
- `0x180162000`
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
      RtlAcquireSRWLockExclusive(&LdrpModuleDatatableLock);
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
      RtlReleaseSRWLockExclusive(&LdrpModuleDatatableLock);
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
0x1800be2e0  push    rbp
0x1800be2e2  push    rbx
0x1800be2e3  push    rsi
0x1800be2e4  push    rdi
0x1800be2e5  push    r12
0x1800be2e7  push    r13
0x1800be2e9  push    r14
0x1800be2eb  push    r15
0x1800be2ed  lea     rbp, [rsp-138h]
0x1800be2f5  sub     rsp, 238h
0x1800be2fc  mov     rax, cs:__security_cookie
0x1800be303  xor     rax, rsp
0x1800be306  mov     [rbp+170h+var_50], rax
0x1800be30d  mov     rsi, rcx
0x1800be310  xorps   xmm0, xmm0
0x1800be313  lea     rcx, [rbp+170h+var_1E0]; void *
0x1800be317  xor     edx, edx; Val
0x1800be319  mov     r8d, 80h; Size
0x1800be31f  movups  xmmword ptr [rsp+270h+var_200], xmm0
0x1800be324  call    memset$thunk$772440563353939046
0x1800be329  xor     edx, edx; Val
0x1800be32b  lea     rcx, [rbp+170h+var_160]; void *
0x1800be32f  mov     r8d, 110h; Size
0x1800be335  call    memset$thunk$772440563353939046
0x1800be33a  mov     r9, [rsi+30h]
0x1800be33e  lea     rax, [rbp+170h+var_150]
0x1800be342  mov     r13, [rsi+38h]
0x1800be346  xor     edi, edi
0x1800be348  xorps   xmm0, xmm0
0x1800be34b  mov     [rbp+170h+var_158], rax
0x1800be34f  xor     eax, eax
0x1800be351  mov     byte ptr [rsp+270h+var_220], dil
0x1800be356  xor     r14d, r14d
0x1800be359  mov     dword ptr [rbp+170h+var_160], 1000000h
0x1800be360  mov     [rbp+170h+var_150], ax
0x1800be364  mov     r15d, 100h
0x1800be36a  mov     dword ptr [rsp+270h+var_220+4], eax
0x1800be36e  movups  [rbp+170h+var_1F0], xmm0
0x1800be372  movups  xmmword ptr [rsp+270h+var_218], xmm0
0x1800be377  test    r9, r9
0x1800be37a  jnz     loc_1800BE5C5
0x1800be380  mov     r12, [rsi+10h]
0x1800be384  mov     r8d, [rsi+20h]
0x1800be388  lea     rax, [rsp+270h+var_220+4]
0x1800be38d  mov     [rsp+270h+var_230], rax; __int64
0x1800be392  lea     r9, [rbp+170h+var_1F0]
0x1800be396  lea     rax, [rsp+270h+var_220]
0x1800be39b  shr     r8d, 3
0x1800be39f  mov     [rsp+270h+var_238], rax; __int64
0x1800be3a4  and     r8b, 1
0x1800be3a8  lea     rax, [rsp+270h+var_218]
0x1800be3ad  mov     rdx, r12
0x1800be3b0  mov     [rsp+270h+var_240], rax; __int64
0x1800be3b5  mov     rcx, rsi; ArgList
0x1800be3b8  lea     rax, [rsp+270h+var_200]
0x1800be3bd  mov     [rsp+270h+var_248], rax; __int64
0x1800be3c2  lea     rax, [rbp+170h+var_160]
0x1800be3c6  mov     [rsp+270h+var_250], rax; __int64
0x1800be3cb  call    LdrpSearchPath
0x1800be3d0  cmp     byte ptr [rsp+270h+var_220], 0
0x1800be3d5  mov     ebx, eax
0x1800be3d7  jnz     loc_1800BE61C
0x1800be3dd  cmp     eax, 0C0000135h
0x1800be3e2  jz      short loc_1800BE3EE
0x1800be3e4  test    eax, eax
0x1800be3e6  js      loc_1800BE4BB
0x1800be3ec  jmp     short loc_1800BE3F7
0x1800be3ee  test    r14d, r14d
0x1800be3f1  jnz     loc_1800BE6D0
0x1800be3f7  cmp     qword ptr [rsi+0B0h], 0
0x1800be3ff  jnz     loc_1800BE553
0x1800be405  lea     r9, [rbp+170h+var_160]
0x1800be409  mov     dword ptr [rsp+270h+var_250], eax
0x1800be40d  lea     r8, [rsp+270h+var_200]
0x1800be412  mov     rcx, rsi
0x1800be415  lea     rdx, [rsp+270h+var_218]
0x1800be41a  call    LdrpAppCompatRedirect
0x1800be41f  mov     ebx, eax
0x1800be421  test    eax, eax
0x1800be423  js      loc_1800BE4BB
0x1800be429  test    dword ptr [rsi+20h], 10000h
0x1800be430  jnz     loc_1800BE6C6
0x1800be436  lea     rcx, [rsp+270h+var_200]
0x1800be43b  call    LdrpHashUnicodeString
0x1800be440  mov     [r13+108h], eax
0x1800be447  lea     rcx, LdrpModuleDatatableLock
0x1800be44e  mov     edi, [rsi+20h]
0x1800be451  mov     r15d, eax
0x1800be454  mov     [rsp+270h+var_208], 0
0x1800be45d  call    RtlAcquireSRWLockExclusive
0x1800be462  mov     ecx, 0
0x1800be467  mov     dword ptr [rsp+270h+var_250], r15d
0x1800be46c  test    dil, 20h
0x1800be470  lea     rdx, [rsp+270h+var_218]
0x1800be475  lea     r9, [rsp+270h+var_208]
0x1800be47a  mov     r8d, edi
0x1800be47d  cmovnz  rdx, rcx
0x1800be481  lea     rcx, [rsp+270h+var_200]
0x1800be486  call    LdrpFindLoadedDllByNameLockHeld
0x1800be48b  mov     ebx, eax
0x1800be48d  cmp     eax, 0C0000135h
0x1800be492  jnz     short loc_1800BE49E
0x1800be494  test    dil, 8
0x1800be498  jnz     loc_1800BE63C
0x1800be49e  mov     rdi, [rsp+270h+var_208]
0x1800be4a3  lea     rcx, LdrpModuleDatatableLock
0x1800be4aa  call    RtlReleaseSRWLockExclusive
0x1800be4af  cmp     ebx, 0C0000135h
0x1800be4b5  jz      loc_1800BE54D
0x1800be4bb  test    rdi, rdi
0x1800be4be  jnz     loc_1800BE62C
0x1800be4c4  call    LdrpIsSecurityEtwLoggingEnabled
0x1800be4c9  test    al, al
0x1800be4cb  jz      short loc_1800BE4D9
0x1800be4cd  mov     ecx, dword ptr [rsp+270h+var_220+4]
0x1800be4d1  mov     rdx, rsi
0x1800be4d4  call    LdrpLogEtwDllSearchResults
0x1800be4d9  mov     rcx, [rbp+170h+var_158]
0x1800be4dd  lea     rax, [rbp+170h+var_150]
0x1800be4e1  cmp     rax, rcx
0x1800be4e4  jz      short loc_1800BE4EB
0x1800be4e6  call    RtlpSysVolFree
0x1800be4eb  mov     rcx, [rsp+270h+var_218+8]
0x1800be4f0  lea     rax, [rbp+170h+var_150]
0x1800be4f4  mov     [rbp+170h+var_158], rax
0x1800be4f8  xor     eax, eax
0x1800be4fa  mov     dword ptr [rbp+170h+var_160], 1000000h
0x1800be501  mov     [rbp+170h+var_150], ax
0x1800be505  test    rcx, rcx
0x1800be508  jz      short loc_1800BE518
0x1800be50a  call    RtlpSysVolFree
0x1800be50f  mov     [rsp+270h+var_218+8], 0
0x1800be518  xor     eax, eax
0x1800be51a  lea     rcx, [rbp+170h+var_1E0]
0x1800be51e  mov     dword ptr [rsp+270h+var_218], eax
0x1800be522  call    LdrpReleaseDllPath
0x1800be527  mov     eax, ebx
0x1800be529  mov     rcx, [rbp+170h+var_50]
0x1800be530  xor     rcx, rsp; StackCookie
0x1800be533  call    __security_check_cookie
0x1800be538  add     rsp, 238h
0x1800be53f  pop     r15
0x1800be541  pop     r14
0x1800be543  pop     r13
0x1800be545  pop     r12
0x1800be547  pop     rdi
0x1800be548  pop     rsi
0x1800be549  pop     rbx
0x1800be54a  pop     rbp
0x1800be54b  retn
0x1800be54d  mov     r15d, 100h
0x1800be553  lea     rcx, [r13+48h]
0x1800be557  call    LdrpFreeUnicodeString
0x1800be55c  movups  xmm0, xmmword ptr [rsp+270h+var_218]
0x1800be561  lea     rdx, [rbp+170h+var_160]
0x1800be565  mov     rcx, rsi
0x1800be568  movups  xmm1, xmmword ptr [rsp+270h+var_200]
0x1800be56d  movdqu  xmmword ptr [r13+48h], xmm0
0x1800be573  xorps   xmm0, xmm0
0x1800be576  movdqu  xmmword ptr [r13+58h], xmm1
0x1800be57c  movups  xmmword ptr [rsp+270h+var_218], xmm0
0x1800be581  call    LdrpMapDllNtFileName
0x1800be586  mov     ebx, eax
0x1800be588  cmp     eax, 4000000Eh
0x1800be58d  jnz     loc_1800BE4BB
0x1800be593  mov     rcx, [rbp+170h+var_158]
0x1800be597  lea     rax, [rbp+170h+var_150]
0x1800be59b  mov     r14d, 1
0x1800be5a1  cmp     rax, rcx
0x1800be5a4  jz      short loc_1800BE5AB
0x1800be5a6  call    RtlpSysVolFree
0x1800be5ab  lea     rax, [rbp+170h+var_150]
0x1800be5af  mov     dword ptr [rbp+170h+var_160], 1000000h
0x1800be5b6  mov     [rbp+170h+var_158], rax
0x1800be5ba  xor     eax, eax
0x1800be5bc  mov     [rbp+170h+var_150], ax
0x1800be5c0  jmp     loc_1800BE384
0x1800be5c5  mov     edx, cs:LdrpPolicyBits
0x1800be5cb  mov     r10d, 7B00h
0x1800be5d1  mov     r8d, [r9+118h]
0x1800be5d8  and     edx, 4
0x1800be5db  mov     eax, edx
0x1800be5dd  neg     eax
0x1800be5df  mov     eax, 400h
0x1800be5e4  sbb     ecx, ecx
0x1800be5e6  and     ecx, eax
0x1800be5e8  add     ecx, r10d
0x1800be5eb  test    r8d, ecx
0x1800be5ee  jz      loc_1800BE380
0x1800be5f4  mov     rcx, [r9+50h]
0x1800be5f8  neg     edx
0x1800be5fa  sbb     rdx, rdx
0x1800be5fd  and     rdx, rax
0x1800be600  add     rdx, r10
0x1800be603  and     rdx, r8
0x1800be606  lea     r8, [rbp+170h+var_1E0]
0x1800be60a  or      rdx, 1
0x1800be60e  call    LdrpInitializeDllPath
0x1800be613  lea     r12, [rbp+170h+var_1E0]
0x1800be617  jmp     loc_1800BE384
0x1800be61c  mov     ecx, [r13+68h]
0x1800be620  or      ecx, 1
0x1800be623  mov     [r13+68h], ecx
0x1800be627  jmp     loc_1800BE3DD
0x1800be62c  mov     rdx, rdi
0x1800be62f  mov     rcx, rsi
0x1800be632  call    LdrpLoadContextReplaceModule
0x1800be637  jmp     loc_1800BE4D9
0x1800be63c  mov     r14d, r15d
0x1800be63f  lea     rcx, LdrpHashTable
0x1800be646  and     r14d, 1Fh
0x1800be64a  shl     r14, 4
0x1800be64e  add     r14, rcx
0x1800be651  xor     al, al
0x1800be653  mov     rbx, [r14]
0x1800be656  cmp     rbx, r14
0x1800be659  jz      short loc_1800BE6B3
0x1800be65b  lea     rdi, [rbx-70h]
0x1800be65f  cmp     r15d, [rdi+108h]
0x1800be666  jz      short loc_1800BE66D
0x1800be668  mov     rbx, [rbx]
0x1800be66b  jmp     short loc_1800BE656
0x1800be66d  lea     rdx, [rdi+48h]
0x1800be671  mov     r8b, 1
0x1800be674  lea     rcx, [rsp+270h+var_218]
0x1800be679  call    RtlEqualUnicodeString
0x1800be67e  test    al, al
0x1800be680  jz      short loc_1800BE668
0x1800be682  mov     rcx, [rdi+98h]
0x1800be689  mov     eax, [rcx+18h]
0x1800be68c  cmp     eax, 0FFFFFFFFh
0x1800be68f  jz      short loc_1800BE6A3
0x1800be691  mov     rax, [rcx]
0x1800be694  mov     ecx, [rax-38h]
0x1800be697  test    cl, 20h
0x1800be69a  jnz     short loc_1800BE6A3
0x1800be69c  lock inc dword ptr [rdi+114h]
0x1800be6a3  mov     eax, [rdi+68h]
0x1800be6a6  xor     ebx, ebx
0x1800be6a8  or      eax, 1
0x1800be6ab  mov     [rdi+68h], eax
0x1800be6ae  jmp     loc_1800BE4A3
0x1800be6b3  mov     rdi, [rsp+270h+var_208]
0x1800be6b8  test    al, al
0x1800be6ba  jnz     short loc_1800BE6A3
0x1800be6bc  mov     ebx, 0C0000135h
0x1800be6c1  jmp     loc_1800BE4A3
0x1800be6c6  or      dword ptr [rsp+270h+var_220+4], 1
0x1800be6cb  jmp     loc_1800BE436
0x1800be6d0  mov     ebx, 0C000007Bh
0x1800be6d5  jmp     loc_1800BE4BB
```
