# UpdateCloudAPCacheNodes(_CloudAPCache *,_tagCacheNodeIdentifier *,_CREDENTIAL_KEY *,_AP_BLOB *,_tagCacheDataFuncs *)

- ea: `0x1800223a0`
- end: `0x180022978`
- name: `?UpdateCloudAPCacheNodes@@YAJPEAU_CloudAPCache@@PEAU_tagCacheNodeIdentifier@@PEAU_CREDENTIAL_KEY@@PEAU_AP_BLOB@@PEAU_tagCacheDataFuncs@@@Z`
- size: `1496`
- prototype: `__int64 __usercall@<rax>(struct _CloudAPCache *@<rcx>, struct _tagCacheNodeIdentifier *@<rdx>, struct _CREDENTIAL_KEY *@<r8>, struct _AP_BLOB *@<r9>, struct _tagCacheDataFuncs *)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x18002223c`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x1800223a0`
- `0x180022a70`
- `0x180022f40`
- `0x1800293c0`
- `0x18003f220`
- `0x18005fe44`
- `0x180064104`
- `0x18007f9f0`

## string_xrefs

- `0x180022408`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x180022537`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x18002266a`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x1800226af`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x1800226e6`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x180022720`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x180022757`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x180022790`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x180022910`: `FIDOGetCredentialIDFromCacheData`
- `0x1800228b5`: `RemoveCloudAPCacheNode`
- `0x180022772`: `UpdateCloudAPCacheNode`

## pseudocode

```c
__int64 __fastcall UpdateCloudAPCacheNodes(
        struct _CloudAPCache *a1,
        struct _tagCacheNodeIdentifier *a2,
        struct _CREDENTIAL_KEY *a3,
        struct _AP_BLOB *a4,
        struct _tagCacheDataFuncs *a5)
{
  void *v5; // rsi
  _DWORD *v6; // r12
  struct _CloudAPCache *v7; // rbx
  __int64 v8; // rcx
  unsigned int updated; // ebx
  const char *v11; // r9
  const char *v12; // rax
  bool v13; // zf
  __int64 i; // r13
  __int64 v15; // rax
  __int64 v16; // rdi
  int v17; // r14d
  unsigned int v18; // r9d
  int v19; // eax
  const char *v20; // rax
  __int64 v21; // r8
  const char *v22; // r9
  const char *v23; // rax
  const char *v24; // rax
  int v25; // r9d
  __int64 v26; // r8
  __int64 v27; // rax
  unsigned int v28; // r12d
  __int64 v29; // rcx
  __int64 v30; // r15
  __int64 v31; // rdx
  int v32; // ebx
  const char *v33; // rax
  int v34; // ebx
  const char *v35; // rax
  const char *v36; // rax
  int v38[2]; // [rsp+20h] [rbp-60h]
  int v39[2]; // [rsp+20h] [rbp-60h]
  const char *v40; // [rsp+28h] [rbp-58h]
  int v41[2]; // [rsp+30h] [rbp-50h]
  size_t Size; // [rsp+50h] [rbp-30h] BYREF
  __int64 v43; // [rsp+58h] [rbp-28h]
  unsigned int v44; // [rsp+60h] [rbp-20h]
  void *Buf1; // [rsp+68h] [rbp-18h] BYREF
  _DWORD *Memory; // [rsp+70h] [rbp-10h]

  v5 = 0;
  v6 = 0;
  v7 = a1;
  Memory = 0;
  v8 = *((unsigned int *)a1 + 5);
  Buf1 = 0;
  LODWORD(Size) = 0;
  v44 = v8;
  if ( (_DWORD)v8 )
  {
    Memory = AllocateMemory((unsigned int)(4 * v8));
    v6 = Memory;
    if ( !Memory )
    {
      updated = -1073741801;
      v11 = "";
      while ( 1 )
      {
        v12 = v11--;
        v13 = *v11 == 92;
        if ( *v11 == 92 )
          break;
        if ( v11 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
        {
          v13 = *v11 == 92;
          break;
        }
      }
      if ( v13 )
        v11 = v12;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v11, 2781, "AllocateMemory", &Class);
      return updated;
    }
  }
  for ( i = 0; (unsigned int)i < *((_DWORD *)v7 + 5); i = (unsigned int)(i + 1) )
  {
    v6[i] = 0;
    v43 = (__int64)&v6[i];
    if ( !*((_QWORD *)a5 + 1) || !*((_QWORD *)a5 + 2) || !*((_QWORD *)a5 + 3) )
    {
      v16 = 32LL * (unsigned int)i;
LABEL_38:
      v17 = 1;
      goto LABEL_39;
    }
    v15 = *((_QWORD *)v7 + 3);
    v16 = 32LL * (unsigned int)i;
    if ( *(_DWORD *)(v16 + v15) == 2 || *(_DWORD *)(v16 + v15) == 3 )
      goto LABEL_38;
    v17 = 0;
    if ( a2 )
    {
      v18 = *(_DWORD *)a2;
      if ( *(_DWORD *)(v16 + v15) == *(_DWORD *)a2 )
      {
        if ( v18 <= 6 )
        {
          v19 = 90;
          if ( _bittest(&v19, v18) )
            goto LABEL_38;
        }
        if ( v18 == 7 )
        {
          if ( !*((_QWORD *)a2 + 1) )
          {
            updated = -1073741595;
            v22 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
            v40 = "NodeIdentifier CredentialID cannot be NULL for FIDO";
            v38[0] = 2844;
LABEL_42:
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v21, v22, *(_QWORD *)v38, v40, &Class);
            goto LABEL_71;
          }
          if ( v5 )
          {
            FreeMemory(v5);
            Buf1 = 0;
          }
          updated = FIDOGetCredentialIDFromCacheData(
                      *(unsigned __int8 **)(v16 + *((_QWORD *)v7 + 3) + 8),
                      *(_DWORD *)(v16 + *((_QWORD *)v7 + 3) + 4),
                      (unsigned __int8 **)&Buf1,
                      (unsigned int *)&Size);
          if ( updated )
          {
            v20 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
            v38[0] = 2858;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", updated, v20, *(_QWORD *)v38, "PKGetPublicKey", &Class);
LABEL_27:
            v5 = Buf1;
            goto LABEL_71;
          }
        }
        else
        {
          if ( v18 != 5 )
          {
            updated = -1073741595;
            v24 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
            v41[0] = v25;
            v38[0] = 2902;
            WPPTraceLogA(
              0,
              "0x%08x %s:%u : %s:%u",
              v26,
              v24,
              *(_QWORD *)v38,
              "Unknown Node Type(Code Bug)",
              *(_QWORD *)v41);
            goto LABEL_71;
          }
          if ( !*((_QWORD *)a2 + 1) )
          {
            updated = -1073741595;
            v22 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
            v40 = "NodeIdentifier Public key cannot be NULL for NGC";
            v38[0] = 2875;
            goto LABEL_42;
          }
          if ( v5 )
          {
            FreeMemory(v5);
            Buf1 = 0;
          }
          updated = PKGetPublicKey(
                      v8,
                      *(_QWORD *)(v16 + *((_QWORD *)v7 + 3) + 8),
                      *(unsigned int *)(v16 + *((_QWORD *)v7 + 3) + 4),
                      &Buf1,
                      &Size);
          if ( updated )
          {
            v23 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
            v39[0] = 2890;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", updated, v23, *(_QWORD *)v39, "PKGetPublicKey", &Class);
            goto LABEL_27;
          }
        }
        v5 = Buf1;
        if ( (_DWORD)Size == *((_DWORD *)a2 + 1) && !memcmp_0(Buf1, *((const void **)a2 + 1), (unsigned int)Size) )
          v17 = 1;
        v7 = a1;
      }
    }
LABEL_39:
    updated = UpdateCloudAPCacheNode(
                (unsigned int *)(v16 + *((_QWORD *)v7 + 3)),
                (unsigned int *)a3,
                0,
                *((_QWORD *)a4 + 1),
                *(_DWORD *)a4,
                v17,
                0,
                0,
                a5,
                (_DWORD *)v43);
    if ( updated )
    {
      v22 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
      v40 = "UpdateCloudAPCacheNode";
      v21 = updated;
      v38[0] = 2920;
      goto LABEL_42;
    }
    v7 = a1;
  }
  v27 = 0;
  v28 = 0;
  while ( 2 )
  {
    LODWORD(v43) = v27;
    if ( (unsigned int)v27 < v44 && v28 < *((_DWORD *)v7 + 5) )
    {
      if ( Memory[v27] )
      {
        if ( v5 )
        {
          FreeMemory(v5);
          v5 = 0;
          Buf1 = 0;
        }
        v29 = *((_QWORD *)v7 + 3);
        v30 = 32LL * v28;
        LODWORD(Size) = 0;
        if ( *(_DWORD *)(v30 + v29) == 7 )
        {
          updated = FIDOGetCredentialIDFromCacheData(
                      *(unsigned __int8 **)(v30 + v29 + 8),
                      *(_DWORD *)(v30 + v29 + 4),
                      (unsigned __int8 **)&Buf1,
                      (unsigned int *)&Size);
          if ( updated )
          {
            v36 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
            v38[0] = 2943;
            WPPTraceLogA(
              0,
              "0x%08x %s:%u : %s:%ws",
              updated,
              v36,
              *(_QWORD *)v38,
              "FIDOGetCredentialIDFromCacheData",
              &Class);
            v5 = Buf1;
            goto LABEL_70;
          }
          v5 = Buf1;
          v7 = a1;
        }
        v31 = *((_QWORD *)v7 + 3);
        if ( *(_DWORD *)(v30 + v31) == 5 )
        {
          v32 = PKGetPublicKey(v29, *(_QWORD *)(v30 + v31 + 8), *(unsigned int *)(v30 + v31 + 4), &Buf1, &Size);
          if ( v32 )
          {
            v33 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
            v38[0] = 2953;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", (unsigned int)v32, v33, *(_QWORD *)v38, "PKGetPublicKey", &Class);
          }
          v5 = Buf1;
          if ( v32 >= 0 )
          {
            v7 = a1;
            goto LABEL_62;
          }
LABEL_64:
          ++v28;
        }
        else
        {
LABEL_62:
          v34 = RemoveCloudAPCacheNode(v7, *(_DWORD *)(v30 + *((_QWORD *)v7 + 3)), (unsigned __int8 *)v5, Size);
          if ( v34 )
          {
            v35 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
            v38[0] = 2963;
            WPPTraceLogA(
              0,
              "0x%08x %s:%u : %s:%ws",
              (unsigned int)v34,
              v35,
              *(_QWORD *)v38,
              "RemoveCloudAPCacheNode",
              &Class);
            if ( v34 < 0 )
              goto LABEL_64;
          }
        }
        v7 = a1;
      }
      else
      {
        ++v28;
      }
      v27 = (unsigned int)(v43 + 1);
      continue;
    }
    break;
  }
  updated = 0;
LABEL_70:
  v6 = Memory;
LABEL_71:
  if ( v5 )
    FreeMemory(v5);
  if ( v6 )
    FreeMemory(v6);
  return updated;
}

```

## disassembly

```asm
0x1800223a0  mov     rax, rsp
0x1800223a3  mov     [rax+10h], rbx
0x1800223a7  mov     [rax+20h], r9
0x1800223ab  mov     [rax+18h], r8
0x1800223af  mov     [rax+8], rcx
0x1800223b3  push    rbp
0x1800223b4  push    rsi
0x1800223b5  push    rdi
0x1800223b6  push    r12
0x1800223b8  push    r13
0x1800223ba  push    r14
0x1800223bc  push    r15
0x1800223be  mov     rbp, rsp
0x1800223c1  sub     rsp, 80h
0x1800223c8  xor     esi, esi
0x1800223ca  xor     r12d, r12d
0x1800223cd  mov     rbx, rcx
0x1800223d0  mov     [rbp+var_10], r12
0x1800223d4  mov     ecx, [rcx+14h]
0x1800223d7  mov     r15, rdx
0x1800223da  mov     [rbp+Buf1], rsi
0x1800223de  mov     dword ptr [rbp+Size], esi
0x1800223e1  mov     [rbp+var_20], ecx
0x1800223e4  test    ecx, ecx
0x1800223e6  jz      short loc_18002245E
0x1800223e8  shl     ecx, 2; uBytes
0x1800223eb  call    ?AllocateMemory@@YAPEAXK@Z; AllocateMemory(ulong)
0x1800223f0  mov     [rbp+var_10], rax
0x1800223f4  mov     r12, rax
0x1800223f7  test    rax, rax
0x1800223fa  jnz     short loc_18002245E
0x1800223fc  mov     ebx, 0C0000017h
0x180022401  lea     r9, aOnecoreDsExtCl_2+3Dh; ""
0x180022408  lea     rdi, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18002240f  mov     rax, r9
0x180022412  dec     r9
0x180022415  cmp     byte ptr [r9], 5Ch ; '\'
0x180022419  jz      short loc_180022424
0x18002241b  cmp     r9, rdi
0x18002241e  ja      short loc_18002240F
0x180022420  cmp     byte ptr [r9], 5Ch ; '\'
0x180022424  cmovz   r9, rax
0x180022428  lea     r14, Class
0x18002242f  lea     rax, aAllocatememory; "AllocateMemory"
0x180022436  mov     qword ptr [rsp+80h+var_50], r14
0x18002243b  mov     qword ptr [rsp+80h+var_58], rax
0x180022440  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180022447  mov     r8d, ebx
0x18002244a  mov     [rsp+80h+var_60], 0ADDh
0x180022452  xor     ecx, ecx
0x180022454  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180022459  jmp     loc_18002295B
0x18002245e  xor     r13d, r13d
0x180022461  lea     edx, [r13+1]
0x180022465  cmp     r13d, [rbx+14h]
0x180022469  jnb     loc_18002278E
0x18002246f  lea     rax, [r12+r13*4]
0x180022473  mov     edi, r13d
0x180022476  mov     dword ptr [rax], 0
0x18002247c  mov     [rbp+var_28], rax
0x180022480  mov     rax, [rbp+arg_20]
0x180022484  cmp     qword ptr [rax+8], 0
0x180022489  jz      loc_1800225FC
0x18002248f  cmp     qword ptr [rax+10h], 0
0x180022494  jz      loc_1800225FC
0x18002249a  cmp     qword ptr [rax+18h], 0
0x18002249f  jz      loc_1800225FC
0x1800224a5  mov     rax, [rbx+18h]
0x1800224a9  shl     rdi, 5
0x1800224ad  cmp     dword ptr [rdi+rax], 2
0x1800224b1  jz      loc_180022600
0x1800224b7  cmp     dword ptr [rdi+rax], 3
0x1800224bb  jz      loc_180022600
0x1800224c1  xor     r14d, r14d
0x1800224c4  test    r15, r15
0x1800224c7  jz      loc_180022603
0x1800224cd  mov     r9d, [r15]
0x1800224d0  cmp     [rdi+rax], r9d
0x1800224d4  jnz     loc_180022603
0x1800224da  cmp     r9d, 6
0x1800224de  ja      short loc_1800224EE
0x1800224e0  lea     eax, [r14+5Ah]
0x1800224e4  bt      eax, r9d
0x1800224e8  jb      loc_180022600
0x1800224ee  cmp     r9d, 7
0x1800224f2  jnz     loc_180022580
0x1800224f8  cmp     [r15+8], r14
0x1800224fc  jz      loc_180022664
0x180022502  test    rsi, rsi
0x180022505  jz      short loc_180022513
0x180022507  mov     rcx, rsi; void *
0x18002250a  call    ?FreeMemory@@YAXPEAX@Z; FreeMemory(void *)
0x18002250f  mov     [rbp+Buf1], r14
0x180022513  mov     rcx, [rbx+18h]
0x180022517  lea     r9, [rbp+Size]; unsigned int *
0x18002251b  lea     r8, [rbp+Buf1]; unsigned __int8 **
0x18002251f  mov     edx, [rdi+rcx+4]; unsigned int
0x180022523  mov     rcx, [rdi+rcx+8]; unsigned __int8 *
0x180022528  call    ?FIDOGetCredentialIDFromCacheData@@YAJPEAEKPEAPEAEPEAK@Z; FIDOGetCredentialIDFromCacheData(uchar *,ulong,uchar * *,ulong *)
0x18002252d  mov     ebx, eax
0x18002252f  test    eax, eax
0x180022531  jz      loc_1800225CF
0x180022537  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18002253e  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180022543  lea     r14, Class
0x18002254a  mov     qword ptr [rsp+80h+var_50], r14
0x18002254f  lea     r13, aPkgetpublickey; "PKGetPublicKey"
0x180022556  mov     qword ptr [rsp+80h+var_58], r13
0x18002255b  mov     [rsp+80h+var_60], 0B2Ah
0x180022563  mov     r9, rax
0x180022566  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18002256d  mov     r8d, ebx
0x180022570  xor     ecx, ecx
0x180022572  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180022577  mov     rsi, [rbp+Buf1]
0x18002257b  jmp     loc_180022941
0x180022580  cmp     r9d, 5
0x180022584  jnz     loc_18002271A
0x18002258a  cmp     [r15+8], r14
0x18002258e  jz      loc_1800226E0
0x180022594  test    rsi, rsi
0x180022597  jz      short loc_1800225A5
0x180022599  mov     rcx, rsi; void *
0x18002259c  call    ?FreeMemory@@YAXPEAX@Z; FreeMemory(void *)
0x1800225a1  mov     [rbp+Buf1], r14
0x1800225a5  mov     rdx, [rbx+18h]
0x1800225a9  lea     rax, [rbp+Size]
0x1800225ad  lea     r9, [rbp+Buf1]
0x1800225b1  mov     qword ptr [rsp+80h+var_60], rax
0x1800225b6  mov     r8d, [rdi+rdx+4]
0x1800225bb  mov     rdx, [rdi+rdx+8]
0x1800225c0  call    ?PKGetPublicKey@@YAJW4PKCredType@@PEAEKPEAPEAEPEAK@Z; PKGetPublicKey(PKCredType,uchar *,ulong,uchar * *,ulong *)
0x1800225c5  mov     ebx, eax
0x1800225c7  test    eax, eax
0x1800225c9  jnz     loc_1800226AF
0x1800225cf  mov     eax, dword ptr [rbp+Size]
0x1800225d2  mov     rsi, [rbp+Buf1]
0x1800225d6  cmp     eax, [r15+4]
0x1800225da  jnz     short loc_1800225F6
0x1800225dc  mov     rdx, [r15+8]; Buf2
0x1800225e0  mov     r8d, eax; Size
0x1800225e3  mov     rcx, rsi; Buf1
0x1800225e6  call    memcmp_0
0x1800225eb  test    eax, eax
0x1800225ed  mov     eax, 1
0x1800225f2  cmovz   r14d, eax
0x1800225f6  mov     rbx, [rbp+arg_0]
0x1800225fa  jmp     short loc_180022603
0x1800225fc  shl     rdi, 5
0x180022600  mov     r14d, edx
0x180022603  mov     rcx, [rbx+18h]
0x180022607  xor     r8d, r8d; int
0x18002260a  mov     rax, [rbp+var_28]
0x18002260e  add     rcx, rdi; int
0x180022611  mov     rdi, [rbp+arg_18]
0x180022615  mov     rdx, qword ptr [rbp+arg_10]; int
0x180022619  mov     [rsp+80h+var_38], rax; __int64
0x18002261e  mov     rax, [rbp+arg_20]
0x180022622  mov     r9, [rdi+8]; int
0x180022626  mov     [rsp+80h+var_40], rax; __int64
0x18002262b  mov     eax, [rdi]
0x18002262d  mov     [rsp+80h+var_48], 0; ULONG
0x180022635  mov     [rsp+80h+var_50], 0; int
0x18002263d  mov     [rsp+80h+var_58], r14d; int
0x180022642  mov     [rsp+80h+var_60], eax; int
0x180022646  call    UpdateCloudAPCacheNode
0x18002264b  mov     ebx, eax
0x18002264d  test    eax, eax
0x18002264f  jnz     loc_180022757
0x180022655  mov     rbx, [rbp+arg_0]
0x180022659  lea     edx, [rax+1]
0x18002265c  add     r13d, edx
0x18002265f  jmp     loc_180022465
0x180022664  mov     r8d, 0C00000E5h
0x18002266a  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x180022671  mov     ebx, r8d
0x180022674  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180022679  mov     r9, rax
0x18002267c  lea     r14, Class
0x180022683  mov     qword ptr [rsp+80h+var_50], r14
0x180022688  lea     rax, aNodeidentifier; "NodeIdentifier CredentialID cannot be N"...
0x18002268f  mov     qword ptr [rsp+80h+var_58], rax
0x180022694  mov     [rsp+80h+var_60], 0B1Ch
0x18002269c  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x1800226a3  xor     ecx, ecx
0x1800226a5  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x1800226aa  jmp     loc_180022941
0x1800226af  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x1800226b6  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800226bb  lea     r14, Class
0x1800226c2  mov     qword ptr [rsp+80h+var_50], r14
0x1800226c7  lea     r13, aPkgetpublickey; "PKGetPublicKey"
0x1800226ce  mov     qword ptr [rsp+80h+var_58], r13
0x1800226d3  mov     [rsp+80h+var_60], 0B4Ah
0x1800226db  jmp     loc_180022563
0x1800226e0  mov     r8d, 0C00000E5h
0x1800226e6  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x1800226ed  mov     ebx, r8d
0x1800226f0  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800226f5  mov     r9, rax
0x1800226f8  lea     r14, Class
0x1800226ff  mov     qword ptr [rsp+80h+var_50], r14
0x180022704  lea     rax, aNodeidentifier_0; "NodeIdentifier Public key cannot be NUL"...
0x18002270b  mov     qword ptr [rsp+80h+var_58], rax
0x180022710  mov     [rsp+80h+var_60], 0B3Bh
0x180022718  jmp     short loc_18002269C
0x18002271a  mov     r8d, 0C00000E5h
0x180022720  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x180022727  mov     ebx, r8d
0x18002272a  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002272f  mov     [rsp+80h+var_50], r9d
0x180022734  lea     rcx, aUnknownNodeTyp; "Unknown Node Type(Code Bug)"
0x18002273b  mov     qword ptr [rsp+80h+var_58], rcx
0x180022740  lea     rdx, a0x08xSUSU; "0x%08x %s:%u : %s:%u"
0x180022747  mov     [rsp+80h+var_60], 0B56h
0x18002274f  mov     r9, rax
0x180022752  jmp     loc_1800226A3
0x180022757  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18002275e  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180022763  mov     r9, rax
0x180022766  lea     r14, Class
0x18002276d  mov     qword ptr [rsp+80h+var_50], r14
0x180022772  lea     rax, aUpdatecloudapc_0; "UpdateCloudAPCacheNode"
0x180022779  mov     qword ptr [rsp+80h+var_58], rax
0x18002277e  mov     r8d, ebx
0x180022781  mov     [rsp+80h+var_60], 0B68h
0x180022789  jmp     loc_18002269C
0x18002278e  xor     eax, eax
0x180022790  lea     rdi, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x180022797  xor     r12d, r12d
0x18002279a  lea     r14, Class
0x1800227a1  lea     r13, aPkgetpublickey; "PKGetPublicKey"
0x1800227a8  mov     dword ptr [rbp+var_28], eax
0x1800227ab  cmp     eax, [rbp+var_20]
0x1800227ae  jnb     loc_18002293B
0x1800227b4  cmp     r12d, [rbx+14h]
0x1800227b8  jnb     loc_18002293B
0x1800227be  mov     rcx, [rbp+var_10]
0x1800227c2  cmp     dword ptr [rcx+rax*4], 0
0x1800227c6  jz      loc_1800228E8
0x1800227cc  test    rsi, rsi
0x1800227cf  jz      short loc_1800227DF
0x1800227d1  mov     rcx, rsi; void *
0x1800227d4  call    ?FreeMemory@@YAXPEAX@Z; FreeMemory(void *)
0x1800227d9  xor     esi, esi
0x1800227db  mov     [rbp+Buf1], rsi
0x1800227df  mov     rcx, [rbx+18h]
0x1800227e3  mov     r15d, r12d
0x1800227e6  shl     r15, 5
0x1800227ea  mov     dword ptr [rbp+Size], 0
0x1800227f1  cmp     dword ptr [r15+rcx], 7
0x1800227f6  jnz     short loc_180022821
0x1800227f8  mov     edx, [r15+rcx+4]; unsigned int
0x1800227fd  lea     r9, [rbp+Size]; unsigned int *
0x180022801  mov     rcx, [r15+rcx+8]; unsigned __int8 *
0x180022806  lea     r8, [rbp+Buf1]; unsigned __int8 **
0x18002280a  call    ?FIDOGetCredentialIDFromCacheData@@YAJPEAEKPEAPEAEPEAK@Z; FIDOGetCredentialIDFromCacheData(uchar *,ulong,uchar * *,ulong *)
0x18002280f  mov     ebx, eax
0x180022811  test    eax, eax
0x180022813  jnz     loc_180022900
0x180022819  mov     rsi, [rbp+Buf1]
0x18002281d  mov     rbx, [rbp+arg_0]
0x180022821  mov     rdx, [rbx+18h]
0x180022825  cmp     dword ptr [r15+rdx], 5
0x18002282a  jnz     short loc_180022888
0x18002282c  mov     r8d, [r15+rdx+4]
0x180022831  lea     rax, [rbp+Size]
0x180022835  mov     rdx, [r15+rdx+8]
0x18002283a  lea     r9, [rbp+Buf1]
0x18002283e  mov     qword ptr [rsp+80h+var_60], rax
0x180022843  call    ?PKGetPublicKey@@YAJW4PKCredType@@PEAEKPEAPEAEPEAK@Z; PKGetPublicKey(PKCredType,uchar *,ulong,uchar * *,ulong *)
0x180022848  mov     ebx, eax
0x18002284a  test    eax, eax
0x18002284c  jz      short loc_18002287C
0x18002284e  mov     rcx, rdi; char *
0x180022851  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180022856  mov     qword ptr [rsp+80h+var_50], r14
0x18002285b  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180022862  mov     r9, rax
0x180022865  mov     qword ptr [rsp+80h+var_58], r13
0x18002286a  mov     r8d, ebx
0x18002286d  mov     [rsp+80h+var_60], 0B89h
0x180022875  xor     ecx, ecx
0x180022877  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18002287c  mov     rsi, [rbp+Buf1]
0x180022880  test    ebx, ebx
0x180022882  js      short loc_1800228DE
0x180022884  mov     rbx, [rbp+arg_0]
0x180022888  mov     rdx, [rbx+18h]
0x18002288c  mov     r8, rsi; unsigned __int8 *
0x18002288f  mov     r9d, dword ptr [rbp+Size]; unsigned int
0x180022893  mov     rcx, rbx; struct _CloudAPCache *
0x180022896  mov     edx, [r15+rdx]; unsigned int
0x18002289a  call    ?RemoveCloudAPCacheNode@@YAJPEAU_CloudAPCache@@KPEAEK@Z; RemoveCloudAPCacheNode(_CloudAPCache *,ulong,uchar *,ulong)
0x18002289f  mov     ebx, eax
0x1800228a1  test    eax, eax
0x1800228a3  jz      short loc_1800228ED
0x1800228a5  mov     rcx, rdi; char *
0x1800228a8  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800228ad  mov     r9, rax
  ... truncated ...
```
