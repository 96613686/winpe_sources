# SerializeCloudAPCache(_CloudAPCache *,uchar * *,ulong *)

- ea: `0x18002e3e0`
- end: `0x18002e7be`
- name: `?SerializeCloudAPCache@@YAJPEAU_CloudAPCache@@PEAPEAEPEAK@Z`
- size: `990`
- prototype: `__int64 __fastcall(struct _CloudAPCache *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000ed04`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x18001c590`
- `0x180022f40`
- `0x1800293c0`
- `0x18002e3e0`
- `0x18002f150`
- `0x180043158`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e6e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e6e7`

## string_xrefs

- `0x18002e459`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x18002e4cf`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x18002e554`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x18002e5ba`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x18002e607`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x18002e660`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x18002e759`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x18002e50d`: `CreateBufferChecksum`
- `0x18002e480`: `Serialize<CloudAPCache>`

## pseudocode

```c
__int64 __fastcall SerializeCloudAPCache(struct _CloudAPCache *a1, unsigned __int8 **a2, unsigned int *a3)
{
  unsigned __int8 *v5; // rdi
  unsigned int v6; // r12d
  HLOCAL v7; // rsi
  const unsigned __int16 *v8; // rcx
  unsigned int BufferChecksum; // ebx
  const char *v10; // rax
  unsigned int v11; // ebp
  const char *v12; // r9
  char v13; // al
  const char *v14; // rdx
  bool v15; // zf
  rsize_t v16; // r13
  unsigned int v17; // ebp
  unsigned __int8 *Memory; // rax
  const char *v19; // r9
  const char *v20; // r9
  const char *v21; // r9
  const char *v22; // r9
  __int64 v23; // rdx
  _BYTE *v24; // rax
  __int64 v25; // rcx
  unsigned __int8 *v26; // rax
  const char *v28; // r9
  char v29; // dl
  const char *v30; // r8
  bool v31; // zf
  unsigned int *v32; // [rsp+20h] [rbp-68h]
  unsigned int *v33; // [rsp+20h] [rbp-68h]
  void *Source; // [rsp+40h] [rbp-48h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-40h]
  rsize_t v36; // [rsp+90h] [rbp+8h] BYREF
  rsize_t SourceSize; // [rsp+A8h] [rbp+20h] BYREF

  hMem = 0;
  LODWORD(v36) = 0;
  Source = 0;
  LODWORD(SourceSize) = 0;
  if ( a1 && a2 && a3 )
  {
    v5 = 0;
    v6 = 0;
    *a2 = 0;
    *a3 = 0;
    v7 = hMem;
    BufferChecksum = Serialize<_CloudAPCache>(a1, (__int64)&v36);
    if ( BufferChecksum )
    {
      v10 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
      LODWORD(v32) = 259;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", BufferChecksum, v10, v32, "Serialize<CloudAPCache>", &Class);
    }
    else
    {
      v11 = v36;
      BufferChecksum = CreateBufferChecksum(
                         v8,
                         (unsigned __int8 *)hMem,
                         v36,
                         (unsigned __int8 **)&Source,
                         (unsigned int *)&SourceSize);
      if ( BufferChecksum )
      {
        v12 = "";
        while ( 1 )
        {
          v13 = *(v12 - 1);
          v14 = v12--;
          v15 = v13 == 92;
          if ( v13 == 92 )
            break;
          if ( v12 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
          {
            v15 = v13 == 92;
            break;
          }
        }
        if ( v15 )
          v12 = v14;
        LODWORD(v33) = 268;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", BufferChecksum, v12, v33, "CreateBufferChecksum", &Class);
        goto LABEL_25;
      }
      v16 = (unsigned int)SourceSize;
      v17 = SourceSize + v11;
      v6 = v17 + 4;
      Memory = (unsigned __int8 *)AllocateMemory(v17 + 4);
      v5 = Memory;
      if ( Memory )
      {
        if ( memcpy_s_0(Memory, v6, &c_cloudAPCacheBufferVersion, 4u) )
        {
          BufferChecksum = -1073741595;
          v20 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
          LODWORD(v33) = 295;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225701LL, v20, v33, "memcpy_s", &Class);
        }
        else if ( memcpy_s_0(v5 + 4, v17, Source, v16) )
        {
          BufferChecksum = -1073741595;
          v21 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
          LODWORD(v33) = 309;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225701LL, v21, v33, "memcpy_s", &Class);
        }
        else if ( memcpy_s_0(&v5[v16 + 4], v17 - (unsigned int)v16, v7, (unsigned int)v36) )
        {
          BufferChecksum = -1073741595;
          v22 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
          LODWORD(v33) = 323;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225701LL, v22, v33, "memcpy_s", &Class);
        }
        else
        {
          *a2 = v5;
          v5 = 0;
          *a3 = v6;
        }
      }
      else
      {
        BufferChecksum = -1073741801;
        v19 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
        LODWORD(v33) = 281;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v19, v33, "AllocateMemory", &Class);
      }
    }
    v11 = v36;
LABEL_25:
    if ( v7 )
    {
      v23 = v11;
      v24 = v7;
      if ( v11 )
      {
        do
        {
          *v24++ = 0;
          --v23;
        }
        while ( v23 );
      }
      if ( g_pLsaFunctionTable )
        ((void (__fastcall *)(HLOCAL, __int64))g_pLsaFunctionTable->FreeLsaHeap)(v7, v23);
      else
        LocalFree(v7);
    }
    if ( Source )
      FreeMemory(Source);
    if ( v5 )
    {
      v25 = v6;
      v26 = v5;
      if ( v6 )
      {
        do
        {
          *v26++ = 0;
          --v25;
        }
        while ( v25 );
      }
      FreeMemory(v5);
    }
    return BufferChecksum;
  }
  v28 = "";
  while ( 1 )
  {
    v29 = *(v28 - 1);
    v30 = v28--;
    v31 = v29 == 92;
    if ( v29 == 92 )
      break;
    if ( v28 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
    {
      v31 = v29 == 92;
      break;
    }
  }
  if ( v31 )
    v28 = v30;
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v28, 246, "InvalidArgs", &Class);
  return 3221225485LL;
}

```

## disassembly

```asm
0x18002e3e0  mov     r11, rsp
0x18002e3e3  push    r14
0x18002e3e5  push    r15
0x18002e3e7  sub     rsp, 78h
0x18002e3eb  xor     eax, eax
0x18002e3ed  mov     r14, r8
0x18002e3f0  mov     [r11-40h], rax
0x18002e3f4  mov     r15, rdx
0x18002e3f7  mov     [r11+8], eax
0x18002e3fb  mov     [r11-48h], rax
0x18002e3ff  mov     [r11+20h], eax
0x18002e403  test    rcx, rcx
0x18002e406  jz      loc_18002E752
0x18002e40c  test    rdx, rdx
0x18002e40f  jz      loc_18002E752
0x18002e415  test    r8, r8
0x18002e418  jz      loc_18002E752
0x18002e41e  mov     [r11+10h], rbx
0x18002e422  lea     r9, [r11-40h]
0x18002e426  mov     [r11-20h], rsi
0x18002e42a  mov     [r11-28h], rdi
0x18002e42e  mov     edi, eax
0x18002e430  mov     [r11-30h], r12
0x18002e434  mov     r12d, eax
0x18002e437  mov     [rdx], rax
0x18002e43a  mov     [r8], eax
0x18002e43d  lea     rax, [r11+8]
0x18002e441  mov     [r11-68h], rax
0x18002e445  mov     [r11-18h], rbp
0x18002e449  call    ??$Serialize@U_CloudAPCache@@@@YAJPEAU_CloudAPCache@@P6A_KPEAX1@ZP6AX11@ZPEAPEAEPEAK@Z; Serialize<_CloudAPCache>(_CloudAPCache *,unsigned __int64 (*)(void *,void *),void (*)(void *,void *),uchar * *,ulong *)
0x18002e44e  mov     rsi, [rsp+88h+hMem]
0x18002e453  mov     ebx, eax
0x18002e455  test    eax, eax
0x18002e457  jz      short loc_18002E49E
0x18002e459  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18002e460  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002e465  mov     r9, rax
0x18002e468  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18002e46f  lea     rax, Class
0x18002e476  mov     r8d, ebx
0x18002e479  mov     [rsp+88h+var_58], rax
0x18002e47e  xor     ecx, ecx
0x18002e480  lea     rax, aSerializeCloud; "Serialize<CloudAPCache>"
0x18002e487  mov     [rsp+88h+var_60], rax
0x18002e48c  mov     dword ptr [rsp+88h+var_68], 103h
0x18002e494  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18002e499  jmp     loc_18002E6A6
0x18002e49e  mov     ebp, dword ptr [rsp+88h+arg_0]
0x18002e4a5  lea     rax, [rsp+88h+SourceSize]
0x18002e4ad  mov     r8d, ebp; unsigned int
0x18002e4b0  mov     [rsp+88h+var_68], rax; unsigned int *
0x18002e4b5  lea     r9, [rsp+88h+Source]; unsigned __int8 **
0x18002e4ba  mov     rdx, rsi; unsigned __int8 *
0x18002e4bd  call    ?CreateBufferChecksum@@YAJPEBGPEAEKPEAPEAEPEAK@Z; CreateBufferChecksum(ushort const *,uchar *,ulong,uchar * *,ulong *)
0x18002e4c2  mov     ebx, eax
0x18002e4c4  test    eax, eax
0x18002e4c6  jz      short loc_18002E530
0x18002e4c8  lea     r9, aOnecoreDsExtCl_2+3Dh; ""
0x18002e4cf  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18002e4d6  nop     word ptr [rax+rax+00000000h]
0x18002e4e0  movzx   eax, byte ptr [r9-1]
0x18002e4e5  mov     rdx, r9
0x18002e4e8  dec     r9
0x18002e4eb  cmp     al, 5Ch ; '\'
0x18002e4ed  jz      short loc_18002E4F6
0x18002e4ef  cmp     r9, rcx
0x18002e4f2  ja      short loc_18002E4E0
0x18002e4f4  cmp     al, 5Ch ; '\'
0x18002e4f6  cmovz   r9, rdx
0x18002e4fa  lea     rax, Class
0x18002e501  mov     [rsp+88h+var_58], rax
0x18002e506  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18002e50d  lea     rax, aCreatebufferch; "CreateBufferChecksum"
0x18002e514  mov     r8d, ebx
0x18002e517  mov     [rsp+88h+var_60], rax
0x18002e51c  xor     ecx, ecx
0x18002e51e  mov     dword ptr [rsp+88h+var_68], 10Ch
0x18002e526  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18002e52b  jmp     loc_18002E6AD
0x18002e530  mov     [rsp+88h+var_38], r13
0x18002e535  mov     r13d, dword ptr [rsp+88h+SourceSize]
0x18002e53d  add     ebp, r13d
0x18002e540  lea     r12d, [rbp+4]
0x18002e544  mov     ecx, r12d; uBytes
0x18002e547  call    ?AllocateMemory@@YAPEAXK@Z; AllocateMemory(ulong)
0x18002e54c  mov     rdi, rax
0x18002e54f  test    rax, rax
0x18002e552  jnz     short loc_18002E59E
0x18002e554  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18002e55b  mov     ebx, 0C0000017h
0x18002e560  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002e565  mov     r9, rax
0x18002e568  lea     rax, Class
0x18002e56f  mov     [rsp+88h+var_58], rax
0x18002e574  lea     rax, aAllocatememory; "AllocateMemory"
0x18002e57b  mov     [rsp+88h+var_60], rax
0x18002e580  mov     dword ptr [rsp+88h+var_68], 119h
0x18002e588  mov     r8d, ebx
0x18002e58b  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18002e592  xor     ecx, ecx
0x18002e594  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18002e599  jmp     loc_18002E6A1
0x18002e59e  mov     edx, r12d; DestinationSize
0x18002e5a1  lea     r8, ?c_cloudAPCacheBufferVersion@@3KB; Source
0x18002e5a8  mov     r9d, 4; SourceSize
0x18002e5ae  mov     rcx, rdi; Destination
0x18002e5b1  call    memcpy_s_0
0x18002e5b6  test    eax, eax
0x18002e5b8  jz      short loc_18002E5F0
0x18002e5ba  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18002e5c1  mov     ebx, 0C00000E5h
0x18002e5c6  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002e5cb  mov     r9, rax
0x18002e5ce  lea     rax, Class
0x18002e5d5  mov     [rsp+88h+var_58], rax
0x18002e5da  lea     rax, aMemcpyS; "memcpy_s"
0x18002e5e1  mov     [rsp+88h+var_60], rax
0x18002e5e6  mov     dword ptr [rsp+88h+var_68], 127h
0x18002e5ee  jmp     short loc_18002E588
0x18002e5f0  mov     r8, [rsp+88h+Source]; Source
0x18002e5f5  lea     rcx, [rdi+4]; Destination
0x18002e5f9  mov     r9, r13; SourceSize
0x18002e5fc  mov     edx, ebp; DestinationSize
0x18002e5fe  call    memcpy_s_0
0x18002e603  test    eax, eax
0x18002e605  jz      short loc_18002E640
0x18002e607  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18002e60e  mov     ebx, 0C00000E5h
0x18002e613  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002e618  mov     r9, rax
0x18002e61b  lea     rax, Class
0x18002e622  mov     [rsp+88h+var_58], rax
0x18002e627  lea     rax, aMemcpyS; "memcpy_s"
0x18002e62e  mov     [rsp+88h+var_60], rax
0x18002e633  mov     dword ptr [rsp+88h+var_68], 135h
0x18002e63b  jmp     loc_18002E588
0x18002e640  mov     r9d, dword ptr [rsp+88h+arg_0]; SourceSize
0x18002e648  lea     rcx, [r13+4]
0x18002e64c  sub     ebp, r13d
0x18002e64f  add     rcx, rdi; Destination
0x18002e652  mov     edx, ebp; DestinationSize
0x18002e654  mov     r8, rsi; Source
0x18002e657  call    memcpy_s_0
0x18002e65c  test    eax, eax
0x18002e65e  jz      short loc_18002E699
0x18002e660  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18002e667  mov     ebx, 0C00000E5h
0x18002e66c  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002e671  mov     r9, rax
0x18002e674  lea     rax, Class
0x18002e67b  mov     [rsp+88h+var_58], rax
0x18002e680  lea     rax, aMemcpyS; "memcpy_s"
0x18002e687  mov     [rsp+88h+var_60], rax
0x18002e68c  mov     dword ptr [rsp+88h+var_68], 143h
0x18002e694  jmp     loc_18002E588
0x18002e699  mov     [r15], rdi
0x18002e69c  xor     edi, edi
0x18002e69e  mov     [r14], r12d
0x18002e6a1  mov     r13, [rsp+88h+var_38]
0x18002e6a6  mov     ebp, dword ptr [rsp+88h+arg_0]
0x18002e6ad  test    rsi, rsi
0x18002e6b0  jz      short loc_18002E6ED
0x18002e6b2  mov     edx, ebp
0x18002e6b4  mov     rax, rsi
0x18002e6b7  test    ebp, ebp
0x18002e6b9  jz      short loc_18002E6CD
0x18002e6bb  nop     dword ptr [rax+rax+00h]
0x18002e6c0  mov     byte ptr [rax], 0
0x18002e6c3  lea     rax, [rax+1]
0x18002e6c7  sub     rdx, 1
0x18002e6cb  jnz     short loc_18002E6C0
0x18002e6cd  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18002e6d4  mov     rcx, rsi; hMem
0x18002e6d7  test    rax, rax
0x18002e6da  jz      short loc_18002E6E7
0x18002e6dc  mov     rax, [rax+30h]
0x18002e6e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e6e5  jmp     short loc_18002E6ED
0x18002e6e7  call    cs:__imp_LocalFree
0x18002e6ed  mov     rcx, [rsp+88h+Source]; void *
0x18002e6f2  mov     rsi, [rsp+88h+var_20]
0x18002e6f7  mov     rbp, [rsp+88h+var_18]
0x18002e6fc  test    rcx, rcx
0x18002e6ff  jz      short loc_18002E706
0x18002e701  call    ?FreeMemory@@YAXPEAX@Z; FreeMemory(void *)
0x18002e706  test    rdi, rdi
0x18002e709  jz      short loc_18002E735
0x18002e70b  mov     ecx, r12d
0x18002e70e  mov     rax, rdi
0x18002e711  test    r12d, r12d
0x18002e714  jz      short loc_18002E72D
0x18002e716  nop     word ptr [rax+rax+00000000h]
0x18002e720  mov     byte ptr [rax], 0
0x18002e723  lea     rax, [rax+1]
0x18002e727  sub     rcx, 1
0x18002e72b  jnz     short loc_18002E720
0x18002e72d  mov     rcx, rdi; void *
0x18002e730  call    ?FreeMemory@@YAXPEAX@Z; FreeMemory(void *)
0x18002e735  mov     rdi, [rsp+88h+var_28]
0x18002e73a  mov     eax, ebx
0x18002e73c  mov     rbx, [rsp+88h+arg_8]
0x18002e744  mov     r12, [rsp+88h+var_30]
0x18002e749  add     rsp, 78h
0x18002e74d  pop     r15
0x18002e74f  pop     r14
0x18002e751  retn
0x18002e752  lea     r9, aOnecoreDsExtCl_2+3Dh; ""
0x18002e759  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18002e760  movzx   edx, byte ptr [r9-1]
0x18002e765  mov     r8, r9
0x18002e768  dec     r9
0x18002e76b  cmp     dl, 5Ch ; '\'
0x18002e76e  jz      short loc_18002E778
0x18002e770  cmp     r9, rcx
0x18002e773  ja      short loc_18002E760
0x18002e775  cmp     dl, 5Ch ; '\'
0x18002e778  cmovz   r9, r8
0x18002e77c  lea     rax, Class
0x18002e783  mov     [rsp+88h+var_58], rax
0x18002e788  lea     rcx, aInvalidargs; "InvalidArgs"
0x18002e78f  mov     [rsp+88h+var_60], rcx
0x18002e794  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18002e79b  xor     ecx, ecx
0x18002e79d  mov     dword ptr [rsp+88h+var_68], 0F6h
0x18002e7a5  mov     r8d, 0C000000Dh
0x18002e7ab  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18002e7b0  mov     eax, 0C000000Dh
0x18002e7b5  add     rsp, 78h
0x18002e7b9  pop     r15
0x18002e7bb  pop     r14
0x18002e7bd  retn
```
