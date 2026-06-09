# AddRawCacheNode(_CloudAPCache *,_tagCacheNodeIdentifier *,uchar *,ulong)

- ea: `0x18005f208`
- end: `0x18005f5c8`
- name: `?AddRawCacheNode@@YAJPEAU_CloudAPCache@@PEAU_tagCacheNodeIdentifier@@PEAEK@Z`
- size: `960`
- prototype: `__int64 __fastcall(struct _CloudAPCache *, const void **, unsigned __int8 *, unsigned int)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x180039090`
- `0x180059a8c`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x180022f40`
- `0x1800293c0`
- `0x18002f59c`
- `0x180043158`
- `0x18005f208`
- `0x18005f5d0`
- `0x18007f9fc`

## string_xrefs

- `0x18005f288`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x18005f2db`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x18005f398`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x18005f426`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x18005f46e`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x18005f4bc`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x18005f509`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x18005f532`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x18005f3b6`: `The cache has no room for more nodes`
- `0x18005f4dc`: `cache nodes == 0`
- `0x18005f524`: `GetCloudAPRawCacheNode`

## pseudocode

```c
__int64 __fastcall AddRawCacheNode(struct _CloudAPCache *a1, const void **a2, unsigned __int8 *a3, unsigned int a4)
{
  size_t v4; // rsi
  unsigned int v5; // r15d
  _BYTE *v9; // rbx
  SIZE_T v10; // rcx
  void *Memory; // rax
  unsigned int v12; // esi
  const char *v13; // rax
  __int64 v14; // r8
  const char *v15; // r10
  __int64 v16; // r11
  int v17; // edx
  const char *v18; // rcx
  void *v19; // rax
  int CloudAPRawCacheNode; // eax
  _OWORD *v21; // rbx
  unsigned int v22; // edx
  __int64 v23; // r9
  unsigned int v24; // esi
  unsigned int v25; // ecx
  int v26; // r8d
  unsigned int i; // esi
  __int64 v28; // r8
  __int64 v29; // rcx
  __int64 v30; // rdx
  unsigned int v31; // eax
  _BYTE *v32; // rax
  void *v33; // rcx
  __int128 v34; // xmm1
  _BYTE *v35; // rcx
  __int64 j; // rax
  __int64 v38; // [rsp+20h] [rbp-40h]
  __int128 v39; // [rsp+40h] [rbp-20h] BYREF
  __int128 v40; // [rsp+50h] [rbp-10h]
  _OWORD *v41; // [rsp+90h] [rbp+30h] BYREF

  v4 = a4;
  v5 = 0;
  v41 = 0;
  v39 = 0;
  v40 = 0;
  if ( a1 && a2 && a3 && a4 )
  {
    v9 = 0;
    v10 = *((unsigned int *)a2 + 1);
    LODWORD(v39) = *(_DWORD *)a2;
    DWORD1(v39) = v10;
    Memory = AllocateMemory(v10);
    *((_QWORD *)&v39 + 1) = Memory;
    if ( !Memory )
    {
      v12 = -1073741801;
      v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
      v17 = 3442;
LABEL_7:
      v18 = "AllocateMemory";
      goto LABEL_42;
    }
    memcpy_0(Memory, a2[1], *((unsigned int *)a2 + 1));
    LODWORD(v40) = v4;
    v19 = AllocateMemory((unsigned int)v4);
    *((_QWORD *)&v40 + 1) = v19;
    if ( !v19 )
    {
      v12 = -1073741801;
      v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
      v17 = 3451;
      goto LABEL_7;
    }
    memcpy_0(v19, a3, v4);
    CloudAPRawCacheNode = GetCloudAPRawCacheNode(a1, *(unsigned int *)a2, a2[1], *((unsigned int *)a2 + 1), &v41);
    v12 = CloudAPRawCacheNode;
    if ( CloudAPRawCacheNode >= 0 )
    {
      v21 = v41;
      FreeCloudAPCacheNodeContents(v41);
LABEL_39:
      v34 = v40;
      *v21 = v39;
      v21[1] = v34;
      return v12;
    }
    if ( CloudAPRawCacheNode == -1073741275 )
    {
      v22 = *((_DWORD *)a1 + 5);
      if ( v22 < 0x11 )
      {
        v5 = v22 + 1;
        v32 = AllocateMemory(32 * (v22 + 1));
        v9 = v32;
        if ( !v32 )
        {
          v12 = -1073741801;
          v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
          v17 = 3525;
          goto LABEL_7;
        }
        if ( memcpy_s_0(v32, 32LL * v5, *((const void *const *)a1 + 3), 32LL * *((unsigned int *)a1 + 5)) )
        {
          v12 = -1073741595;
          v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
          v17 = 3536;
          v18 = "memcpy_s";
          goto LABEL_42;
        }
        v33 = (void *)*((_QWORD *)a1 + 3);
        if ( v33 )
          FreeMemory(v33);
        *((_QWORD *)a1 + 3) = v9;
        v31 = v5;
        *((_DWORD *)a1 + 5) = v5;
      }
      else
      {
        v23 = *((_QWORD *)a1 + 3);
        v24 = 18;
        v25 = 0;
        while ( 1 )
        {
          v26 = *(_DWORD *)(32LL * v25 + v23);
          if ( ((v26 - 1) & 0xFFFFFFFC) != 0 || v26 == 2 )
          {
            if ( v24 == 18 )
              v24 = v25;
            if ( v26 == *(_DWORD *)a2 )
              break;
          }
          if ( ++v25 >= v22 )
            goto LABEL_23;
        }
        v24 = v25;
LABEL_23:
        if ( v24 > 0x11 )
        {
          v12 = -1073741789;
          v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
          v17 = 3501;
          v18 = "The cache has no room for more nodes";
          goto LABEL_42;
        }
        FreeCloudAPCacheNodeContents(v23 + 32LL * v24);
        for ( i = v24 + 1; ; ++i )
        {
          v31 = *((_DWORD *)a1 + 5);
          if ( i >= v31 )
            break;
          v28 = *((_QWORD *)a1 + 3);
          v29 = 32LL * (i - 1);
          v30 = 32LL * i;
          *(_OWORD *)(v29 + v28) = *(_OWORD *)(v30 + v28);
          *(_OWORD *)(v29 + v28 + 16) = *(_OWORD *)(v30 + v28 + 16);
        }
      }
      if ( v31 )
      {
        v21 = (_OWORD *)(*((_QWORD *)a1 + 3) + 32LL * (v31 - 1));
        v12 = 0;
        goto LABEL_39;
      }
      v9 = 0;
      v12 = -1073741595;
      v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
      v17 = 3554;
      v18 = "cache nodes == 0";
    }
    else
    {
      v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
      v17 = 3563;
      v18 = "GetCloudAPRawCacheNode";
    }
  }
  else
  {
    v12 = -1073741811;
    v9 = 0;
    v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
    v17 = 3431;
    v18 = "InvalidArgs";
  }
LABEL_42:
  LODWORD(v38) = v17;
  WPPTraceLogA(v16, v15, v14, v13, v38, v18, &Class);
  FreeCloudAPCacheNodeContents(&v39);
  if ( v9 )
  {
    v35 = v9;
    for ( j = 32LL * v5; j; --j )
      *v35++ = 0;
    FreeMemory(v9);
  }
  return v12;
}

```

## disassembly

```asm
0x18005f208  mov     [rsp-28h+arg_8], rbx
0x18005f20d  mov     [rsp-28h+arg_10], rsi
0x18005f212  push    rbp
0x18005f213  push    rdi
0x18005f214  push    r12
0x18005f216  push    r14
0x18005f218  push    r15
0x18005f21a  mov     rbp, rsp
0x18005f21d  sub     rsp, 60h
0x18005f221  xorps   xmm0, xmm0
0x18005f224  mov     esi, r9d
0x18005f227  xor     r15d, r15d
0x18005f22a  mov     [rbp+arg_0], 0
0x18005f232  mov     r12, r8
0x18005f235  mov     r14, rdx
0x18005f238  mov     rdi, rcx
0x18005f23b  movups  [rbp+var_20], xmm0
0x18005f23f  movups  [rbp+var_10], xmm0
0x18005f243  test    rcx, rcx
0x18005f246  jz      loc_18005F52D
0x18005f24c  test    rdx, rdx
0x18005f24f  jz      loc_18005F52D
0x18005f255  test    r8, r8
0x18005f258  jz      loc_18005F52D
0x18005f25e  test    r9d, r9d
0x18005f261  jz      loc_18005F52D
0x18005f267  mov     eax, [rdx]
0x18005f269  xor     ebx, ebx
0x18005f26b  mov     ecx, [rdx+4]; uBytes
0x18005f26e  mov     dword ptr [rbp+var_20], eax
0x18005f271  mov     dword ptr [rbp+var_20+4], ecx
0x18005f274  call    ?AllocateMemory@@YAPEAXK@Z; AllocateMemory(ulong)
0x18005f279  mov     qword ptr [rbp+var_20+8], rax
0x18005f27d  test    rax, rax
0x18005f280  jnz     short loc_18005F2B2
0x18005f282  mov     r8d, 0C0000017h
0x18005f288  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18005f28f  xor     r11d, r11d
0x18005f292  lea     r10, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18005f299  mov     esi, r8d
0x18005f29c  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005f2a1  mov     edx, 0D72h
0x18005f2a6  lea     rcx, aAllocatememory; "AllocateMemory"
0x18005f2ad  jmp     loc_18005F559
0x18005f2b2  mov     r8d, [r14+4]; Size
0x18005f2b6  mov     rcx, rax; void *
0x18005f2b9  mov     rdx, [r14+8]; Src
0x18005f2bd  call    memcpy_0
0x18005f2c2  mov     ecx, esi; uBytes
0x18005f2c4  mov     dword ptr [rbp+var_10], esi
0x18005f2c7  call    ?AllocateMemory@@YAPEAXK@Z; AllocateMemory(ulong)
0x18005f2cc  mov     qword ptr [rbp+var_10+8], rax
0x18005f2d0  test    rax, rax
0x18005f2d3  jnz     short loc_18005F2FB
0x18005f2d5  mov     r8d, 0C0000017h
0x18005f2db  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18005f2e2  xor     r11d, r11d
0x18005f2e5  lea     r10, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18005f2ec  mov     esi, r8d
0x18005f2ef  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005f2f4  mov     edx, 0D7Bh
0x18005f2f9  jmp     short loc_18005F2A6
0x18005f2fb  mov     r8, rsi; Size
0x18005f2fe  mov     rdx, r12; Src
0x18005f301  mov     rcx, rax; void *
0x18005f304  call    memcpy_0
0x18005f309  mov     r9d, [r14+4]
0x18005f30d  lea     rax, [rbp+arg_0]
0x18005f311  mov     r8, [r14+8]
0x18005f315  mov     rcx, rdi
0x18005f318  mov     edx, [r14]
0x18005f31b  mov     [rsp+60h+var_40], rax
0x18005f320  call    GetCloudAPRawCacheNode
0x18005f325  mov     esi, eax
0x18005f327  test    eax, eax
0x18005f329  js      short loc_18005F33C
0x18005f32b  mov     rbx, [rbp+arg_0]
0x18005f32f  mov     rcx, rbx
0x18005f332  call    FreeCloudAPCacheNodeContents
0x18005f337  jmp     loc_18005F4F2
0x18005f33c  cmp     eax, 0C0000225h
0x18005f341  jnz     loc_18005F506
0x18005f347  mov     edx, [rdi+14h]
0x18005f34a  cmp     edx, 11h
0x18005f34d  jb      loc_18005F409
0x18005f353  mov     r9, [rdi+18h]
0x18005f357  mov     esi, 12h
0x18005f35c  xor     ecx, ecx
0x18005f35e  mov     eax, ecx
0x18005f360  shl     rax, 5
0x18005f364  mov     r8d, [rax+r9]
0x18005f368  lea     eax, [r8-1]
0x18005f36c  test    eax, 0FFFFFFFCh
0x18005f371  jnz     short loc_18005F379
0x18005f373  cmp     r8d, 2
0x18005f377  jnz     short loc_18005F384
0x18005f379  cmp     esi, 12h
0x18005f37c  cmovz   esi, ecx
0x18005f37f  cmp     r8d, [r14]
0x18005f382  jz      short loc_18005F38C
0x18005f384  inc     ecx
0x18005f386  cmp     ecx, edx
0x18005f388  jb      short loc_18005F35E
0x18005f38a  jmp     short loc_18005F38E
0x18005f38c  mov     esi, ecx
0x18005f38e  cmp     esi, 11h
0x18005f391  jbe     short loc_18005F3C2
0x18005f393  mov     esi, 0C0000023h
0x18005f398  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18005f39f  xor     r11d, r11d
0x18005f3a2  lea     r10, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18005f3a9  mov     r8d, esi
0x18005f3ac  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005f3b1  mov     edx, 0DADh
0x18005f3b6  lea     rcx, aTheCacheHasNoR; "The cache has no room for more nodes"
0x18005f3bd  jmp     loc_18005F559
0x18005f3c2  mov     ecx, esi
0x18005f3c4  shl     rcx, 5
0x18005f3c8  add     rcx, r9
0x18005f3cb  call    FreeCloudAPCacheNodeContents
0x18005f3d0  inc     esi
0x18005f3d2  jmp     short loc_18005F3FD
0x18005f3d4  mov     r8, [rdi+18h]
0x18005f3d8  lea     ecx, [rsi-1]
0x18005f3db  shl     rcx, 5
0x18005f3df  mov     edx, esi
0x18005f3e1  shl     rdx, 5
0x18005f3e5  inc     esi
0x18005f3e7  movups  xmm0, xmmword ptr [rdx+r8]
0x18005f3ec  movups  xmmword ptr [rcx+r8], xmm0
0x18005f3f1  movups  xmm1, xmmword ptr [rdx+r8+10h]
0x18005f3f7  movups  xmmword ptr [rcx+r8+10h], xmm1
0x18005f3fd  mov     eax, [rdi+14h]
0x18005f400  cmp     esi, eax
0x18005f402  jb      short loc_18005F3D4
0x18005f404  jmp     loc_18005F4B1
0x18005f409  lea     r15d, [rdx+1]
0x18005f40d  mov     ecx, r15d
0x18005f410  shl     ecx, 5; uBytes
0x18005f413  call    ?AllocateMemory@@YAPEAXK@Z; AllocateMemory(ulong)
0x18005f418  mov     rbx, rax
0x18005f41b  test    rax, rax
0x18005f41e  jnz     short loc_18005F449
0x18005f420  mov     r8d, 0C0000017h
0x18005f426  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18005f42d  xor     r11d, r11d
0x18005f430  lea     r10, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18005f437  mov     esi, r8d
0x18005f43a  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005f43f  mov     edx, 0DC5h
0x18005f444  jmp     loc_18005F2A6
0x18005f449  mov     r9d, [rdi+14h]
0x18005f44d  mov     rcx, rbx; Destination
0x18005f450  mov     r8, [rdi+18h]; Source
0x18005f454  mov     edx, r15d
0x18005f457  shl     r9, 5; SourceSize
0x18005f45b  shl     rdx, 5; DestinationSize
0x18005f45f  call    memcpy_s_0
0x18005f464  test    eax, eax
0x18005f466  jz      short loc_18005F498
0x18005f468  mov     r8d, 0C00000E5h
0x18005f46e  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18005f475  xor     r11d, r11d
0x18005f478  lea     r10, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18005f47f  mov     esi, r8d
0x18005f482  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005f487  mov     edx, 0DD0h
0x18005f48c  lea     rcx, aMemcpyS; "memcpy_s"
0x18005f493  jmp     loc_18005F559
0x18005f498  mov     rcx, [rdi+18h]; void *
0x18005f49c  test    rcx, rcx
0x18005f49f  jz      short loc_18005F4A6
0x18005f4a1  call    ?FreeMemory@@YAXPEAX@Z; FreeMemory(void *)
0x18005f4a6  mov     [rdi+18h], rbx
0x18005f4aa  mov     eax, r15d
0x18005f4ad  mov     [rdi+14h], r15d
0x18005f4b1  cmp     eax, 1
0x18005f4b4  jnb     short loc_18005F4E5
0x18005f4b6  mov     r8d, 0C00000E5h
0x18005f4bc  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18005f4c3  xor     ebx, ebx
0x18005f4c5  lea     r10, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18005f4cc  xor     r11d, r11d
0x18005f4cf  mov     esi, r8d
0x18005f4d2  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005f4d7  mov     edx, 0DE2h
0x18005f4dc  lea     rcx, aCacheNodes0; "cache nodes == 0"
0x18005f4e3  jmp     short loc_18005F559
0x18005f4e5  lea     ebx, [rax-1]
0x18005f4e8  shl     rbx, 5
0x18005f4ec  add     rbx, [rdi+18h]
0x18005f4f0  xor     esi, esi
0x18005f4f2  movups  xmm0, [rbp+var_20]
0x18005f4f6  movups  xmm1, [rbp+var_10]
0x18005f4fa  movups  xmmword ptr [rbx], xmm0
0x18005f4fd  movups  xmmword ptr [rbx+10h], xmm1
0x18005f501  jmp     loc_18005F5AD
0x18005f506  xor     r11d, r11d
0x18005f509  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18005f510  lea     r10, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18005f517  mov     r8d, eax
0x18005f51a  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005f51f  mov     edx, 0DEBh
0x18005f524  lea     rcx, aGetcloudaprawc; "GetCloudAPRawCacheNode"
0x18005f52b  jmp     short loc_18005F559
0x18005f52d  mov     esi, 0C000000Dh
0x18005f532  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18005f539  xor     ebx, ebx
0x18005f53b  lea     r10, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18005f542  xor     r11d, r11d
0x18005f545  mov     r8d, esi
0x18005f548  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005f54d  mov     edx, 0D67h
0x18005f552  lea     rcx, aInvalidargs; "InvalidArgs"
0x18005f559  mov     r9, rax
0x18005f55c  lea     rax, Class
0x18005f563  mov     [rsp+60h+var_30], rax
0x18005f568  mov     [rsp+60h+var_38], rcx
0x18005f56d  mov     rcx, r11
0x18005f570  mov     dword ptr [rsp+60h+var_40], edx
0x18005f574  mov     rdx, r10
0x18005f577  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18005f57c  lea     rcx, [rbp+var_20]
0x18005f580  call    FreeCloudAPCacheNodeContents
0x18005f585  test    rbx, rbx
0x18005f588  jz      short loc_18005F5AD
0x18005f58a  mov     eax, r15d
0x18005f58d  mov     rcx, rbx
0x18005f590  shl     rax, 5
0x18005f594  test    rax, rax
0x18005f597  jz      short loc_18005F5A5
0x18005f599  mov     byte ptr [rcx], 0
0x18005f59c  inc     rcx
0x18005f59f  sub     rax, 1
0x18005f5a3  jnz     short loc_18005F599
0x18005f5a5  mov     rcx, rbx; void *
0x18005f5a8  call    ?FreeMemory@@YAXPEAX@Z; FreeMemory(void *)
0x18005f5ad  lea     r11, [rsp+60h+var_s0]
0x18005f5b2  mov     eax, esi
0x18005f5b4  mov     rbx, [r11+38h]
0x18005f5b8  mov     rsi, [r11+40h]
0x18005f5bc  mov     rsp, r11
0x18005f5bf  pop     r15
0x18005f5c1  pop     r14
0x18005f5c3  pop     r12
0x18005f5c5  pop     rdi
0x18005f5c6  pop     rbp
0x18005f5c7  retn
```
