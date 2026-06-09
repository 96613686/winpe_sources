# UpdateTokenInCacheNodeData

- ea: `0x180029098`
- end: `0x180029392`
- name: `UpdateTokenInCacheNodeData`
- size: `762`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x18005fe44`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x180028dec`
- `0x180029098`
- `0x1800293f0`
- `0x180029464`
- `0x180081010`

## string_xrefs

- `0x18002913c`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x180029197`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x180029206`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x180029259`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x1800292e7`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x180029168`: `pFnDisassembleCacheData`
- `0x180029221`: `pFnDisassembleCacheData`
- `0x180029302`: `CreateCacheNodeDataBuffer`
- `0x1800291b2`: `DeserializeCacheNodeData`
- `0x180029274`: `pFnAssembleCacheData`

## pseudocode

```c
__int64 __fastcall UpdateTokenInCacheNodeData(
        int a1,
        __int64 *a2,
        __int64 a3,
        int a4,
        unsigned int *a5,
        unsigned int a6,
        __int64 a7,
        unsigned int a8,
        int a9,
        __int64 a10,
        _QWORD *a11,
        _DWORD *a12)
{
  __int64 v13; // rcx
  __int64 (__fastcall *v14)(__int64, __int128 *, __int128 *, __int128 *); // rax
  unsigned int CacheNodeDataBuffer; // ebx
  const char *v16; // r9
  const char *v17; // rax
  bool v18; // zf
  const char *v19; // r9
  __int64 v20; // rcx
  __int64 (__fastcall *v21)(__int64, __int128 *, _OWORD *, __int128 *); // rax
  const char *v22; // r9
  const char *v23; // r9
  const char *v24; // r9
  void (__fastcall *v25)(__int128 *); // rax
  __int128 v27; // [rsp+40h] [rbp-91h] BYREF
  __int128 v28; // [rsp+50h] [rbp-81h] BYREF
  __int128 v29; // [rsp+60h] [rbp-71h] BYREF
  __int128 v30; // [rsp+70h] [rbp-61h] BYREF
  __int128 v31; // [rsp+80h] [rbp-51h] BYREF
  __int128 v32; // [rsp+90h] [rbp-41h]
  __int64 v33; // [rsp+A0h] [rbp-31h]
  __int128 v34; // [rsp+A8h] [rbp-29h] BYREF
  _OWORD v35[5]; // [rsp+B8h] [rbp-19h] BYREF

  v33 = 0;
  v27 = 0;
  *a11 = 0;
  v29 = 0;
  v34 = 0;
  *a12 = 0;
  v35[0] = 0;
  v30 = 0;
  v28 = 0;
  v31 = 0;
  v32 = 0;
  if ( a1
    || (v13 = *a2,
        v14 = (__int64 (__fastcall *)(__int64, __int128 *, __int128 *, __int128 *))a2[2],
        LODWORD(v27) = a4,
        *((_QWORD *)&v27 + 1) = a3,
        (CacheNodeDataBuffer = v14(v13, &v27, &v29, &v34)) == 0) )
  {
    CacheNodeDataBuffer = DeserializeCacheNodeData(a5, a6, (__int64)&v31);
    if ( CacheNodeDataBuffer )
    {
      v19 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", CacheNodeDataBuffer, v19, 2283, "DeserializeCacheNodeData", &Class);
    }
    else
    {
      if ( !a1 )
      {
        v20 = *a2;
        v21 = (__int64 (__fastcall *)(__int64, __int128 *, _OWORD *, __int128 *))a2[2];
        LODWORD(v27) = DWORD2(v32);
        *((_QWORD *)&v27 + 1) = v33;
        CacheNodeDataBuffer = v21(v20, &v27, v35, &v30);
        if ( CacheNodeDataBuffer )
        {
          v22 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", CacheNodeDataBuffer, v22, 2296, "pFnDisassembleCacheData", &Class);
          goto LABEL_19;
        }
        CacheNodeDataBuffer = ((__int64 (__fastcall *)(_QWORD, __int128 *, __int128 *, __int128 *))a2[1])(
                                *a2,
                                &v29,
                                &v30,
                                &v28);
        if ( CacheNodeDataBuffer )
        {
          v23 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", CacheNodeDataBuffer, v23, 2303, "pFnAssembleCacheData", &Class);
          goto LABEL_19;
        }
      }
      DWORD2(v31) |= a9;
      CacheNodeDataBuffer = CreateCacheNodeDataBuffer(a7, a8, DWORD2(v31));
      if ( CacheNodeDataBuffer )
      {
        v24 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", CacheNodeDataBuffer, v24, 2327, "CreateCacheNodeDataBuffer", &Class);
      }
    }
  }
  else
  {
    v16 = "";
    while ( 1 )
    {
      v17 = v16--;
      v18 = *v16 == 92;
      if ( *v16 == 92 )
        break;
      if ( v16 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
      {
        v18 = *v16 == 92;
        break;
      }
    }
    if ( v18 )
      v16 = v17;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", CacheNodeDataBuffer, v16, 2276, "pFnDisassembleCacheData", &Class);
  }
LABEL_19:
  if ( a2 )
  {
    v25 = (void (__fastcall *)(__int128 *))a2[3];
    if ( v25 )
    {
      v25(&v29);
      ((void (__fastcall *)(__int128 *))a2[3])(&v34);
      ((void (__fastcall *)(_OWORD *))a2[3])(v35);
      ((void (__fastcall *)(__int128 *))a2[3])(&v30);
      ((void (__fastcall *)(__int128 *))a2[3])(&v28);
    }
  }
  FreeCloudAPCacheNodeDataContents((struct _CloudAPCacheNodeData2 *)&v31);
  return CacheNodeDataBuffer;
}

```

## disassembly

```asm
0x180029098  mov     [rsp-8+arg_0], ecx
0x18002909c  push    rbp
0x18002909d  push    rbx
0x18002909e  push    rsi
0x18002909f  push    rdi
0x1800290a0  push    r12
0x1800290a2  push    r13
0x1800290a4  push    r14
0x1800290a6  push    r15
0x1800290a8  lea     rbp, [rsp-7]
0x1800290ad  sub     rsp, 0D8h
0x1800290b4  xorps   xmm0, xmm0
0x1800290b7  mov     eax, ecx
0x1800290b9  xor     ecx, ecx
0x1800290bb  xorps   xmm1, xmm1
0x1800290be  mov     [rbp+3Fh+var_70], rcx
0x1800290c2  mov     esi, r9d
0x1800290c5  mov     rcx, [rbp+3Fh+arg_50]
0x1800290cc  mov     r14, r8
0x1800290cf  mov     rdi, rdx
0x1800290d2  movups  [rsp+110h+var_D0], xmm0
0x1800290d7  mov     qword ptr [rcx], 0
0x1800290de  mov     rcx, [rbp+3Fh+arg_58]
0x1800290e5  movups  [rbp+3Fh+var_B0], xmm1
0x1800290e9  movups  [rbp+3Fh+var_68], xmm0
0x1800290ed  mov     dword ptr [rcx], 0
0x1800290f3  movups  [rbp+3Fh+var_58], xmm1
0x1800290f7  movups  [rbp+3Fh+var_A0], xmm0
0x1800290fb  movups  [rsp+110h+var_C0], xmm1
0x180029100  movups  [rbp+3Fh+var_90], xmm0
0x180029104  movups  [rbp+3Fh+var_80], xmm0
0x180029108  test    eax, eax
0x18002910a  jnz     short loc_180029181
0x18002910c  mov     rcx, [rdi]
0x18002910f  lea     rdx, [rsp+110h+var_D0]
0x180029114  mov     rax, [rdi+10h]
0x180029118  mov     dword ptr [rsp+110h+var_D0], r9d
0x18002911d  lea     r9, [rbp+3Fh+var_68]
0x180029121  mov     qword ptr [rsp+110h+var_D0+8], r8
0x180029126  lea     r8, [rbp+3Fh+var_B0]
0x18002912a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002912f  mov     ebx, eax
0x180029131  test    eax, eax
0x180029133  jz      short loc_180029181
0x180029135  lea     r9, aOnecoreDsExtCl_2+3Dh; ""
0x18002913c  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x180029143  mov     rax, r9
0x180029146  dec     r9
0x180029149  cmp     byte ptr [r9], 5Ch ; '\'
0x18002914d  jz      short loc_180029158
0x18002914f  cmp     r9, rcx
0x180029152  ja      short loc_180029143
0x180029154  cmp     byte ptr [r9], 5Ch ; '\'
0x180029158  cmovz   r9, rax
0x18002915c  lea     rax, Class
0x180029163  mov     [rsp+110h+var_E0], rax
0x180029168  lea     rax, aPfndisassemble; "pFnDisassembleCacheData"
0x18002916f  mov     [rsp+110h+var_E8], rax
0x180029174  mov     [rsp+110h+var_F0], 8E4h
0x18002917c  jmp     loc_180029316
0x180029181  mov     edx, [rbp+3Fh+arg_28]
0x180029184  lea     r8, [rbp+3Fh+var_90]
0x180029188  mov     rcx, [rbp+3Fh+arg_20]
0x18002918c  call    DeserializeCacheNodeData
0x180029191  mov     ebx, eax
0x180029193  test    eax, eax
0x180029195  jz      short loc_1800291CB
0x180029197  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18002919e  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800291a3  mov     r9, rax
0x1800291a6  lea     rax, Class
0x1800291ad  mov     [rsp+110h+var_E0], rax
0x1800291b2  lea     rax, aDeserializecac; "DeserializeCacheNodeData"
0x1800291b9  mov     [rsp+110h+var_E8], rax
0x1800291be  mov     [rsp+110h+var_F0], 8EBh
0x1800291c6  jmp     loc_180029316
0x1800291cb  cmp     [rbp+3Fh+arg_0], 0
0x1800291cf  mov     r12, [rbp+3Fh+var_70]
0x1800291d3  mov     r13d, dword ptr [rbp+3Fh+var_80+8]
0x1800291d7  jnz     loc_180029295
0x1800291dd  mov     rcx, [rdi]
0x1800291e0  lea     r9, [rbp+3Fh+var_A0]
0x1800291e4  mov     rax, [rdi+10h]
0x1800291e8  lea     r8, [rbp+3Fh+var_58]
0x1800291ec  lea     rdx, [rsp+110h+var_D0]
0x1800291f1  mov     dword ptr [rsp+110h+var_D0], r13d
0x1800291f6  mov     qword ptr [rsp+110h+var_D0+8], r12
0x1800291fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029200  mov     ebx, eax
0x180029202  test    eax, eax
0x180029204  jz      short loc_18002923A
0x180029206  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18002920d  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180029212  mov     r9, rax
0x180029215  lea     rax, Class
0x18002921c  mov     [rsp+110h+var_E0], rax
0x180029221  lea     rax, aPfndisassemble; "pFnDisassembleCacheData"
0x180029228  mov     [rsp+110h+var_E8], rax
0x18002922d  mov     [rsp+110h+var_F0], 8F8h
0x180029235  jmp     loc_180029316
0x18002923a  mov     rcx, [rdi]
0x18002923d  lea     r9, [rsp+110h+var_C0]
0x180029242  mov     rax, [rdi+8]
0x180029246  lea     r8, [rbp+3Fh+var_A0]
0x18002924a  lea     rdx, [rbp+3Fh+var_B0]
0x18002924e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029253  mov     ebx, eax
0x180029255  test    eax, eax
0x180029257  jz      short loc_18002928D
0x180029259  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x180029260  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180029265  mov     r9, rax
0x180029268  lea     rax, Class
0x18002926f  mov     [rsp+110h+var_E0], rax
0x180029274  lea     rax, aPfnassemblecac; "pFnAssembleCacheData"
0x18002927b  mov     [rsp+110h+var_E8], rax
0x180029280  mov     [rsp+110h+var_F0], 8FFh
0x180029288  jmp     loc_180029316
0x18002928d  mov     esi, dword ptr [rsp+110h+var_C0]
0x180029291  mov     r14, qword ptr [rbp+3Fh+var_C0+8]
0x180029295  test    r14, r14
0x180029298  jz      short loc_18002929E
0x18002929a  test    esi, esi
0x18002929c  jnz     short loc_1800292A4
0x18002929e  mov     r14, r12
0x1800292a1  mov     esi, r13d
0x1800292a4  mov     r8d, dword ptr [rbp+3Fh+var_90+8]
0x1800292a8  mov     r9, r14
0x1800292ab  mov     rax, [rbp+3Fh+arg_58]
0x1800292b2  or      r8d, [rbp+3Fh+arg_40]
0x1800292b9  mov     edx, [rbp+3Fh+arg_38]
0x1800292bf  mov     rcx, [rbp+3Fh+arg_30]
0x1800292c3  mov     [rsp+110h+var_E0], rax
0x1800292c8  mov     rax, [rbp+3Fh+arg_50]
0x1800292cf  mov     [rsp+110h+var_E8], rax
0x1800292d4  mov     [rsp+110h+var_F0], esi
0x1800292d8  mov     dword ptr [rbp+3Fh+var_90+8], r8d
0x1800292dc  call    CreateCacheNodeDataBuffer
0x1800292e1  mov     ebx, eax
0x1800292e3  test    eax, eax
0x1800292e5  jz      short loc_180029327
0x1800292e7  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x1800292ee  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800292f3  mov     r9, rax
0x1800292f6  lea     rax, Class
0x1800292fd  mov     [rsp+110h+var_E0], rax
0x180029302  lea     rax, aCreatecachenod; "CreateCacheNodeDataBuffer"
0x180029309  mov     [rsp+110h+var_E8], rax
0x18002930e  mov     [rsp+110h+var_F0], 917h
0x180029316  mov     r8d, ebx
0x180029319  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180029320  xor     ecx, ecx
0x180029322  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180029327  test    rdi, rdi
0x18002932a  jz      short loc_180029373
0x18002932c  mov     rax, [rdi+18h]
0x180029330  test    rax, rax
0x180029333  jz      short loc_180029373
0x180029335  lea     rcx, [rbp+3Fh+var_B0]
0x180029339  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002933e  mov     rax, [rdi+18h]
0x180029342  lea     rcx, [rbp+3Fh+var_68]
0x180029346  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002934b  mov     rax, [rdi+18h]
0x18002934f  lea     rcx, [rbp+3Fh+var_58]
0x180029353  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029358  mov     rax, [rdi+18h]
0x18002935c  lea     rcx, [rbp+3Fh+var_A0]
0x180029360  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029365  mov     rax, [rdi+18h]
0x180029369  lea     rcx, [rsp+110h+var_C0]
0x18002936e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029373  lea     rcx, [rbp+3Fh+var_90]; struct _CloudAPCacheNodeData2 *
0x180029377  call    ?FreeCloudAPCacheNodeDataContents@@YAXPEAU_CloudAPCacheNodeData2@@@Z; FreeCloudAPCacheNodeDataContents(_CloudAPCacheNodeData2 *)
0x18002937c  mov     eax, ebx
0x18002937e  add     rsp, 0D8h
0x180029385  pop     r15
0x180029387  pop     r14
0x180029389  pop     r13
0x18002938b  pop     r12
0x18002938d  pop     rdi
0x18002938e  pop     rsi
0x18002938f  pop     rbx
0x180029390  pop     rbp
0x180029391  retn
```
