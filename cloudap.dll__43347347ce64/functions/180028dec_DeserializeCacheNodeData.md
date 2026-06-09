# DeserializeCacheNodeData

- ea: `0x180028dec`
- end: `0x180029090`
- name: `DeserializeCacheNodeData`
- size: `676`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180029098`
- `0x1800609fc`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x180022f40`
- `0x180028dec`
- `0x1800293f0`
- `0x180043158`

## string_xrefs

- `0x180028e1e`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x180028e65`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x180028eab`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x180028f0c`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x180028f47`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x180028f8d`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x180028fd3`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x180029011`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x180029036`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x180028e8d`: `Cache node doesnt have version`
- `0x180028e39`: `Cache node is of invalid length`
- `0x180028ec6`: `Cache node doesnt have flags`
- `0x180028f27`: `Overflow:cbCredKey > cbCacheNodeData`

## pseudocode

```c
__int64 __fastcall DeserializeCacheNodeData(unsigned int *a1, unsigned int a2, __int64 a3)
{
  unsigned int v4; // esi
  unsigned int *v5; // r14
  unsigned int v6; // esi
  const char *v7; // rax
  __int64 v8; // r8
  const char *v9; // r10
  int v10; // edx
  const char *v11; // rcx
  const char *v12; // r9
  const char *v13; // rax
  unsigned int v14; // esi
  int v15; // edx
  int v16; // ecx
  SIZE_T v17; // rcx
  HLOCAL Memory; // rax
  char *v19; // r14
  __int64 v20; // rbp
  SIZE_T v21; // rcx
  HLOCAL v22; // rax
  int v24; // [rsp+20h] [rbp-48h]

  *(_OWORD *)a3 = 0;
  v4 = a2;
  v5 = a1;
  *(_OWORD *)(a3 + 16) = 0;
  *(_QWORD *)(a3 + 32) = 0;
  if ( a2 < 4 )
  {
    v6 = -1073281680;
    v7 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
    v10 = 2096;
    v11 = "Cache node is of invalid length";
LABEL_29:
    v12 = v7;
LABEL_30:
    v24 = v10;
    WPPTraceLogA(0, v9, v8, v12, v24, v11, &Class);
    FreeCloudAPCacheNodeDataContents((struct _CloudAPCacheNodeData2 *)a3);
    return v6;
  }
  if ( *a1 )
  {
    v16 = 1;
    v15 = 1;
  }
  else
  {
    if ( a2 - 4 < 4 )
    {
      v8 = 3221685616LL;
      v12 = "";
      v6 = -1073281680;
      do
        v13 = v12--;
      while ( *v12 != 92 && v12 > "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" );
      v9 = "0x%08x %s:%u : %s:%ws";
      v10 = 2109;
      v11 = "Cache node doesnt have version";
      if ( *v12 == 92 )
        v12 = v13;
      goto LABEL_30;
    }
    v14 = a2 - 8;
    if ( a2 - 8 < 4 )
    {
      v6 = -1073281680;
      v7 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
      v10 = 2120;
      v11 = "Cache node doesnt have flags";
      goto LABEL_29;
    }
    v15 = a1[2];
    v5 = a1 + 3;
    v16 = a1[1];
    v4 = v14 - 4;
  }
  *(_DWORD *)(a3 + 4) = v16;
  *(_DWORD *)(a3 + 8) = v15;
  v17 = *v5;
  *(_DWORD *)(a3 + 12) = v17;
  if ( (int)v17 + 4 < (unsigned int)v17 )
  {
    v6 = -1073741675;
    v7 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
    v10 = 2137;
    v11 = "RtlDWordAdd";
    goto LABEL_29;
  }
  if ( (int)v17 + 4 > v4 )
  {
    v6 = -2147483643;
    v7 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
    v10 = 2144;
    v11 = "Overflow:cbCredKey > cbCacheNodeData";
    goto LABEL_29;
  }
  Memory = AllocateMemory(v17);
  *(_QWORD *)(a3 + 16) = Memory;
  if ( !Memory )
  {
    v6 = -1073741801;
    v7 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
    v10 = 2151;
LABEL_20:
    v11 = "AllocateMemory";
    goto LABEL_29;
  }
  v19 = (char *)(v5 + 1);
  if ( memcpy_s_0(Memory, *(unsigned int *)(a3 + 12), v19, *(unsigned int *)(a3 + 12)) )
  {
    v6 = -1073741595;
    v7 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
    v10 = 2165;
LABEL_23:
    v11 = "memcpy_s";
    goto LABEL_29;
  }
  v20 = *(unsigned int *)(a3 + 12);
  v21 = v4 - (unsigned int)v20 - 4;
  *(_DWORD *)(a3 + 24) = v21;
  v22 = AllocateMemory(v21);
  *(_QWORD *)(a3 + 32) = v22;
  if ( !v22 )
  {
    v6 = -1073741801;
    v7 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
    v10 = 2177;
    goto LABEL_20;
  }
  v6 = 0;
  if ( memcpy_s_0(v22, *(unsigned int *)(a3 + 24), &v19[v20], *(unsigned int *)(a3 + 24)) )
  {
    v6 = -1073741595;
    v7 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
    v10 = 2187;
    goto LABEL_23;
  }
  return v6;
}

```

## disassembly

```asm
0x180028dec  push    rbx
0x180028dee  push    rbp
0x180028def  push    rsi
0x180028df0  push    rdi
0x180028df1  push    r14
0x180028df3  sub     rsp, 40h
0x180028df7  xorps   xmm0, xmm0
0x180028dfa  xor     eax, eax
0x180028dfc  movups  xmmword ptr [r8], xmm0
0x180028e00  xor     ebx, ebx
0x180028e02  mov     rdi, r8
0x180028e05  mov     esi, edx
0x180028e07  mov     r14, rcx
0x180028e0a  movups  xmmword ptr [r8+10h], xmm0
0x180028e0f  mov     [r8+20h], rax
0x180028e13  cmp     edx, 4
0x180028e16  jnb     short loc_180028E45
0x180028e18  mov     r8d, 0C0070570h
0x180028e1e  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x180028e25  mov     esi, r8d
0x180028e28  lea     r10, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180028e2f  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180028e34  mov     edx, 830h
0x180028e39  lea     rcx, aCacheNodeIsOfI; "Cache node is of invalid length"
0x180028e40  jmp     loc_180029058
0x180028e45  cmp     [rcx], ebx
0x180028e47  jnz     loc_180028EE2
0x180028e4d  add     esi, 0FFFFFFFCh
0x180028e50  cmp     esi, 4
0x180028e53  jnb     short loc_180028E9D
0x180028e55  mov     r8d, 0C0070570h
0x180028e5b  lea     r9, aOnecoreDsExtCl_2+3Dh; ""
0x180028e62  mov     esi, r8d
0x180028e65  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x180028e6c  mov     rax, r9
0x180028e6f  dec     r9
0x180028e72  cmp     byte ptr [r9], 5Ch ; '\'
0x180028e76  jz      short loc_180028E7D
0x180028e78  cmp     r9, rcx
0x180028e7b  ja      short loc_180028E6C
0x180028e7d  cmp     byte ptr [r9], 5Ch ; '\'
0x180028e81  lea     r10, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180028e88  mov     edx, 83Dh
0x180028e8d  lea     rcx, aCacheNodeDoesn_0; "Cache node doesnt have version"
0x180028e94  cmovz   r9, rax
0x180028e98  jmp     loc_18002905B
0x180028e9d  add     esi, 0FFFFFFFCh
0x180028ea0  cmp     esi, 4
0x180028ea3  jnb     short loc_180028ED2
0x180028ea5  mov     r8d, 0C0070570h
0x180028eab  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x180028eb2  mov     esi, r8d
0x180028eb5  lea     r10, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180028ebc  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180028ec1  mov     edx, 848h
0x180028ec6  lea     rcx, aCacheNodeDoesn; "Cache node doesnt have flags"
0x180028ecd  jmp     loc_180029058
0x180028ed2  mov     edx, [r14+8]
0x180028ed6  add     r14, 0Ch
0x180028eda  mov     ecx, [rcx+4]
0x180028edd  add     esi, 0FFFFFFFCh
0x180028ee0  jmp     short loc_180028EE9
0x180028ee2  mov     ecx, 1
0x180028ee7  mov     edx, ecx
0x180028ee9  mov     [r8+4], ecx
0x180028eed  mov     [r8+8], edx
0x180028ef1  mov     ecx, [r14]; uBytes
0x180028ef4  mov     [r8+0Ch], ecx
0x180028ef8  lea     eax, [rcx+4]
0x180028efb  cmp     eax, ecx
0x180028efd  jb      loc_180029031
0x180028f03  cmp     eax, esi
0x180028f05  jbe     short loc_180028F33
0x180028f07  mov     esi, 80000005h
0x180028f0c  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x180028f13  mov     r8d, esi
0x180028f16  lea     r10, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180028f1d  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180028f22  mov     edx, 860h
0x180028f27  lea     rcx, aOverflowCbcred; "Overflow:cbCredKey > cbCacheNodeData"
0x180028f2e  jmp     loc_180029058
0x180028f33  call    ?AllocateMemory@@YAPEAXK@Z; AllocateMemory(ulong)
0x180028f38  mov     [rdi+10h], rax
0x180028f3c  test    rax, rax
0x180028f3f  jnz     short loc_180028F6E
0x180028f41  mov     r8d, 0C0000017h
0x180028f47  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x180028f4e  mov     esi, r8d
0x180028f51  lea     r10, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180028f58  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180028f5d  mov     edx, 867h
0x180028f62  lea     rcx, aAllocatememory; "AllocateMemory"
0x180028f69  jmp     loc_180029058
0x180028f6e  mov     edx, [rdi+0Ch]; DestinationSize
0x180028f71  add     r14, 4
0x180028f75  mov     r9d, edx; SourceSize
0x180028f78  mov     r8, r14; Source
0x180028f7b  mov     rcx, rax; Destination
0x180028f7e  call    memcpy_s_0
0x180028f83  test    eax, eax
0x180028f85  jz      short loc_180028FB4
0x180028f87  mov     r8d, 0C00000E5h
0x180028f8d  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x180028f94  mov     esi, r8d
0x180028f97  lea     r10, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180028f9e  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180028fa3  mov     edx, 875h
0x180028fa8  lea     rcx, aMemcpyS; "memcpy_s"
0x180028faf  jmp     loc_180029058
0x180028fb4  mov     ebp, [rdi+0Ch]
0x180028fb7  sub     esi, ebp
0x180028fb9  lea     ecx, [rsi-4]; uBytes
0x180028fbc  mov     [rdi+18h], ecx
0x180028fbf  call    ?AllocateMemory@@YAPEAXK@Z; AllocateMemory(ulong)
0x180028fc4  mov     [rdi+20h], rax
0x180028fc8  test    rax, rax
0x180028fcb  jnz     short loc_180028FF3
0x180028fcd  mov     r8d, 0C0000017h
0x180028fd3  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x180028fda  mov     esi, r8d
0x180028fdd  lea     r10, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180028fe4  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180028fe9  mov     edx, 881h
0x180028fee  jmp     loc_180028F62
0x180028ff3  mov     edx, [rdi+18h]; DestinationSize
0x180028ff6  lea     r8, [r14+rbp]; Source
0x180028ffa  mov     r9d, edx; SourceSize
0x180028ffd  mov     rcx, rax; Destination
0x180029000  mov     esi, ebx
0x180029002  call    memcpy_s_0
0x180029007  test    eax, eax
0x180029009  jz      short loc_180029083
0x18002900b  mov     r8d, 0C00000E5h
0x180029011  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x180029018  mov     esi, r8d
0x18002901b  lea     r10, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180029022  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180029027  mov     edx, 88Bh
0x18002902c  jmp     loc_180028FA8
0x180029031  mov     esi, 0C0000095h
0x180029036  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18002903d  mov     r8d, esi
0x180029040  lea     r10, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180029047  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002904c  mov     edx, 859h
0x180029051  lea     rcx, aRtldwordadd; "RtlDWordAdd"
0x180029058  mov     r9, rax
0x18002905b  lea     rax, Class
0x180029062  mov     [rsp+68h+var_38], rax
0x180029067  mov     [rsp+68h+var_40], rcx
0x18002906c  mov     rcx, rbx
0x18002906f  mov     [rsp+68h+var_48], edx
0x180029073  mov     rdx, r10
0x180029076  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18002907b  mov     rcx, rdi; struct _CloudAPCacheNodeData2 *
0x18002907e  call    ?FreeCloudAPCacheNodeDataContents@@YAXPEAU_CloudAPCacheNodeData2@@@Z; FreeCloudAPCacheNodeDataContents(_CloudAPCacheNodeData2 *)
0x180029083  mov     eax, esi
0x180029085  add     rsp, 40h
0x180029089  pop     r14
0x18002908b  pop     rdi
0x18002908c  pop     rsi
0x18002908d  pop     rbp
0x18002908e  pop     rbx
0x18002908f  retn
```
