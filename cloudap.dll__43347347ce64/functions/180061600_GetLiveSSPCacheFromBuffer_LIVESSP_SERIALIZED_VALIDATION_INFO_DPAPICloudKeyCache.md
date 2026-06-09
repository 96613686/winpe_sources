# GetLiveSSPCacheFromBuffer(LIVESSP_SERIALIZED_VALIDATION_INFO *,_DPAPICloudKeyCache * *)

- ea: `0x180061600`
- end: `0x1800619ee`
- name: `?GetLiveSSPCacheFromBuffer@@YAJPEAULIVESSP_SERIALIZED_VALIDATION_INFO@@PEAPEAU_DPAPICloudKeyCache@@@Z`
- size: `1006`
- prototype: `__int64 __fastcall(struct LIVESSP_SERIALIZED_VALIDATION_INFO *, struct _DPAPICloudKeyCache **)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x18005f95c`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x18001c590`
- `0x180022f40`
- `0x1800293c0`
- `0x18002b090`
- `0x180060b00`
- `0x180061248`
- `0x180061600`
- `0x18007f9f0`

## string_xrefs

- `0x180061719`: `GetBufferChecksumSize`
- `0x1800617d1`: `CreateBufferChecksum`
- `0x18006182d`: `CreateBufferChecksum`
- `0x18006165f`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\livessputility.cpp`
- `0x1800616b7`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\livessputility.cpp`
- `0x1800616fe`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\livessputility.cpp`
- `0x18006174b`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\livessputility.cpp`
- `0x1800617b3`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\livessputility.cpp`
- `0x18006180f`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\livessputility.cpp`
- `0x180061869`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\livessputility.cpp`
- `0x1800618b2`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\livessputility.cpp`
- `0x180061903`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\livessputility.cpp`
- `0x18006193b`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\livessputility.cpp`
- `0x18006197a`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\livessputility.cpp`
- `0x18006195b`: `Serialized LiveSSP buffer does not contain a cache`
- `0x18006167d`: `InvalidArg:pSerializedLiveSSPBuffer->cbLiveSSPCache`
- `0x180061769`: `InvalidArg:pSerializedLiveSSPBuffer->cbLiveSSPCache`
- `0x1800616d5`: `InvalidArg:serializedCacheVersion`
- `0x18006191e`: `Deserialize<DPAPICloudKeyCache>`

## pseudocode

```c
__int64 __fastcall GetLiveSSPCacheFromBuffer(
        struct LIVESSP_SERIALIZED_VALIDATION_INFO *a1,
        struct _DPAPICloudKeyCache **a2)
{
  struct _DPAPICloudKeyCache *v3; // rdi
  void *v4; // rsi
  unsigned __int64 v5; // rsi
  unsigned int BufferChecksumSize; // ebx
  __int64 v7; // r8
  const char *v8; // r9
  _DWORD *v9; // r15
  const char *v10; // r9
  __int64 v11; // r8
  unsigned int v12; // ebp
  const unsigned __int16 *v13; // rcx
  const char *v14; // r9
  __int64 v15; // r8
  unsigned __int8 *v16; // r13
  ULONG v17; // r12d
  const char *v18; // r9
  const char *v19; // r9
  __int64 v20; // r8
  const char *v21; // r9
  __int64 v22; // r8
  struct _DPAPICloudKeyCache *Memory; // rax
  __int64 v24; // r8
  const char *v25; // r9
  __int64 v26; // r8
  unsigned int *v28; // [rsp+20h] [rbp-58h]
  int v29; // [rsp+20h] [rbp-58h]
  const char *v30; // [rsp+28h] [rbp-50h]
  const char *v31; // [rsp+28h] [rbp-50h]
  size_t Size; // [rsp+80h] [rbp+8h] BYREF
  unsigned int v33; // [rsp+90h] [rbp+18h] BYREF
  void *Buf1; // [rsp+98h] [rbp+20h] BYREF

  v33 = 0;
  v3 = 0;
  Buf1 = 0;
  v4 = 0;
  LODWORD(Size) = 0;
  if ( !a1 || !a2 )
  {
    BufferChecksumSize = -1073741811;
    v25 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\livessputility.cpp");
    v31 = "InvalidArg(s)";
    LODWORD(v28) = 165;
    goto LABEL_31;
  }
  *a2 = 0;
  if ( !*((_DWORD *)a1 + 12) || (v5 = *((unsigned int *)a1 + 13), !(_DWORD)v5) )
  {
    BufferChecksumSize = -1073741275;
    v8 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\livessputility.cpp");
    v30 = "Serialized LiveSSP buffer does not contain a cache";
    v29 = 175;
    goto LABEL_13;
  }
  if ( (unsigned int)v5 < 4 )
  {
    BufferChecksumSize = -1073741811;
    v8 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\livessputility.cpp");
    v30 = "InvalidArg:pSerializedLiveSSPBuffer->cbLiveSSPCache";
    v29 = 187;
LABEL_7:
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v7, v8, v29, v30, &Class);
    return BufferChecksumSize;
  }
  v9 = (_DWORD *)((char *)a1 + *((unsigned int *)a1 + 12));
  if ( *v9 != 1 )
  {
    BufferChecksumSize = -1073741811;
    v10 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\livessputility.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v11, v10, 194, "InvalidArg:serializedCacheVersion", &Class);
    return BufferChecksumSize;
  }
  BufferChecksumSize = GetBufferChecksumSize((const unsigned __int16 *)a1, &v33);
  if ( BufferChecksumSize )
  {
    v8 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\livessputility.cpp");
    v30 = "GetBufferChecksumSize";
    v29 = 201;
LABEL_13:
    v7 = BufferChecksumSize;
    goto LABEL_7;
  }
  v12 = v33;
  v13 = (const unsigned __int16 *)(v33 + 4LL);
  if ( v5 < (unsigned __int64)v13 )
  {
    BufferChecksumSize = -1073741811;
    v14 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\livessputility.cpp");
    WPPTraceLogA(
      0,
      "0x%08x %s:%u : %s:%ws",
      v15,
      v14,
      210,
      "InvalidArg:pSerializedLiveSSPBuffer->cbLiveSSPCache",
      &Class);
    return BufferChecksumSize;
  }
  v16 = (unsigned __int8 *)v9 + v33;
  v17 = v5 - v33 - 4;
  BufferChecksumSize = CreateBufferChecksum(v13, v16 + 4, v17, (unsigned __int8 **)&Buf1, (unsigned int *)&Size);
  if ( !BufferChecksumSize )
  {
    if ( (_DWORD)Size != v12 )
    {
      BufferChecksumSize = -1073740688;
      v19 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\livessputility.cpp");
      LODWORD(v28) = 228;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v20, v19, v28, "CreateBufferChecksum", &Class);
      goto LABEL_18;
    }
    v4 = Buf1;
    if ( memcmp_0(Buf1, v9 + 1, (unsigned int)Size) )
    {
      BufferChecksumSize = -1073740688;
      v21 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\livessputility.cpp");
      LODWORD(v28) = 237;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v22, v21, v28, "memcmp", &Class);
      goto LABEL_32;
    }
    Memory = (struct _DPAPICloudKeyCache *)AllocateMemory(0x20u);
    v3 = Memory;
    if ( Memory )
    {
      BufferChecksumSize = Deserialize<_DPAPICloudKeyCache>(v16 + 4, v17, v24, Memory);
      if ( !BufferChecksumSize )
      {
        *a2 = v3;
        v3 = 0;
        goto LABEL_32;
      }
      v25 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\livessputility.cpp");
      v31 = "Deserialize<DPAPICloudKeyCache>";
      LODWORD(v28) = 253;
    }
    else
    {
      BufferChecksumSize = -1073741801;
      v25 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\livessputility.cpp");
      v31 = "AllocateMemory";
      LODWORD(v28) = 245;
    }
    v26 = BufferChecksumSize;
LABEL_31:
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v26, v25, v28, v31, &Class);
    goto LABEL_32;
  }
  v18 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\livessputility.cpp");
  LODWORD(v28) = 223;
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", BufferChecksumSize, v18, v28, "CreateBufferChecksum", &Class);
LABEL_18:
  v4 = Buf1;
LABEL_32:
  if ( v4 )
    FreeMemory(v4);
  if ( v3 )
    FreeLiveSSPCache(v3);
  return BufferChecksumSize;
}

```

## disassembly

```asm
0x180061600  mov     r11, rsp
0x180061603  mov     [r11+10h], rbx
0x180061607  push    rbp
0x180061608  push    rsi
0x180061609  push    rdi
0x18006160a  push    r12
0x18006160c  push    r13
0x18006160e  push    r14
0x180061610  push    r15
0x180061612  sub     rsp, 40h
0x180061616  xor     eax, eax
0x180061618  mov     r14, rdx
0x18006161b  mov     [r11+18h], eax
0x18006161f  mov     edi, eax
0x180061621  mov     [r11+20h], rax
0x180061625  mov     esi, eax
0x180061627  mov     [r11+8], eax
0x18006162b  test    rcx, rcx
0x18006162e  jz      loc_180061974
0x180061634  test    rdx, rdx
0x180061637  jz      loc_180061974
0x18006163d  mov     [rdx], rax
0x180061640  cmp     [rcx+30h], eax
0x180061643  jz      loc_18006193B
0x180061649  mov     esi, [rcx+34h]
0x18006164c  test    esi, esi
0x18006164e  jz      loc_18006193B
0x180061654  cmp     esi, 4
0x180061657  jnb     short loc_1800616A4
0x180061659  mov     r8d, 0C000000Dh
0x18006165f  lea     rcx, aOnecoreDsExtCl_15; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x180061666  mov     ebx, r8d
0x180061669  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18006166e  mov     r9, rax
0x180061671  lea     rax, Class
0x180061678  mov     [rsp+78h+var_48], rax
0x18006167d  lea     rax, aInvalidargPser; "InvalidArg:pSerializedLiveSSPBuffer->cb"...
0x180061684  mov     [rsp+78h+var_50], rax
0x180061689  mov     dword ptr [rsp+78h+var_58], 0BBh
0x180061691  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180061698  xor     ecx, ecx
0x18006169a  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18006169f  jmp     loc_1800619D4
0x1800616a4  mov     r15d, [rcx+30h]
0x1800616a8  add     r15, rcx
0x1800616ab  cmp     dword ptr [r15], 1
0x1800616af  jz      short loc_1800616EB
0x1800616b1  mov     r8d, 0C000000Dh
0x1800616b7  lea     rcx, aOnecoreDsExtCl_15; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x1800616be  mov     ebx, r8d
0x1800616c1  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800616c6  mov     r9, rax
0x1800616c9  lea     rax, Class
0x1800616d0  mov     [rsp+78h+var_48], rax
0x1800616d5  lea     rax, aInvalidargSeri_0; "InvalidArg:serializedCacheVersion"
0x1800616dc  mov     [rsp+78h+var_50], rax
0x1800616e1  mov     dword ptr [rsp+78h+var_58], 0C2h
0x1800616e9  jmp     short loc_180061691
0x1800616eb  lea     rdx, [rsp+78h+arg_10]; unsigned int *
0x1800616f3  call    ?GetBufferChecksumSize@@YAJPEBGPEAK@Z; GetBufferChecksumSize(ushort const *,ulong *)
0x1800616f8  mov     ebx, eax
0x1800616fa  test    eax, eax
0x1800616fc  jz      short loc_180061735
0x1800616fe  lea     rcx, aOnecoreDsExtCl_15; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x180061705  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18006170a  mov     r9, rax
0x18006170d  lea     rax, Class
0x180061714  mov     [rsp+78h+var_48], rax
0x180061719  lea     rax, aGetbuffercheck; "GetBufferChecksumSize"
0x180061720  mov     [rsp+78h+var_50], rax
0x180061725  mov     dword ptr [rsp+78h+var_58], 0C9h
0x18006172d  mov     r8d, ebx
0x180061730  jmp     loc_180061691
0x180061735  mov     ebp, [rsp+78h+arg_10]
0x18006173c  lea     rcx, [rbp+4]; unsigned __int16 *
0x180061740  cmp     rsi, rcx
0x180061743  jnb     short loc_180061782
0x180061745  mov     r8d, 0C000000Dh
0x18006174b  lea     rcx, aOnecoreDsExtCl_15; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x180061752  mov     ebx, r8d
0x180061755  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18006175a  mov     r9, rax
0x18006175d  lea     rax, Class
0x180061764  mov     [rsp+78h+var_48], rax
0x180061769  lea     rax, aInvalidargPser; "InvalidArg:pSerializedLiveSSPBuffer->cb"...
0x180061770  mov     [rsp+78h+var_50], rax
0x180061775  mov     dword ptr [rsp+78h+var_58], 0D2h
0x18006177d  jmp     loc_180061691
0x180061782  lea     rax, [rsp+78h+Size]
0x18006178a  sub     esi, ebp
0x18006178c  lea     r13, [r15+rbp]
0x180061790  mov     [rsp+78h+var_58], rax; unsigned int *
0x180061795  lea     r9, [rsp+78h+Buf1]; unsigned __int8 **
0x18006179d  lea     rdx, [r13+4]; unsigned __int8 *
0x1800617a1  lea     r12d, [rsi-4]
0x1800617a5  mov     r8d, r12d; unsigned int
0x1800617a8  call    ?CreateBufferChecksum@@YAJPEBGPEAEKPEAPEAEPEAK@Z; CreateBufferChecksum(ushort const *,uchar *,ulong,uchar * *,ulong *)
0x1800617ad  mov     ebx, eax
0x1800617af  test    eax, eax
0x1800617b1  jz      short loc_180061800
0x1800617b3  lea     rcx, aOnecoreDsExtCl_15; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x1800617ba  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800617bf  mov     r9, rax
0x1800617c2  mov     r8d, ebx
0x1800617c5  lea     rax, Class
0x1800617cc  mov     [rsp+78h+var_48], rax
0x1800617d1  lea     rax, aCreatebufferch; "CreateBufferChecksum"
0x1800617d8  mov     [rsp+78h+var_50], rax
0x1800617dd  mov     dword ptr [rsp+78h+var_58], 0DFh
0x1800617e5  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x1800617ec  xor     ecx, ecx
0x1800617ee  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x1800617f3  mov     rsi, [rsp+78h+Buf1]
0x1800617fb  jmp     loc_1800619BA
0x180061800  cmp     dword ptr [rsp+78h+Size], ebp
0x180061807  jz      short loc_180061843
0x180061809  mov     r8d, 0C0000470h
0x18006180f  lea     rcx, aOnecoreDsExtCl_15; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x180061816  mov     ebx, r8d
0x180061819  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18006181e  mov     r9, rax
0x180061821  lea     rax, Class
0x180061828  mov     [rsp+78h+var_48], rax
0x18006182d  lea     rax, aCreatebufferch; "CreateBufferChecksum"
0x180061834  mov     [rsp+78h+var_50], rax
0x180061839  mov     dword ptr [rsp+78h+var_58], 0E4h
0x180061841  jmp     short loc_1800617E5
0x180061843  mov     rsi, [rsp+78h+Buf1]
0x18006184b  lea     rdx, [r15+4]; Buf2
0x18006184f  mov     r8d, dword ptr [rsp+78h+Size]; Size
0x180061857  mov     rcx, rsi; Buf1
0x18006185a  call    memcmp_0
0x18006185f  test    eax, eax
0x180061861  jz      short loc_1800618A0
0x180061863  mov     r8d, 0C0000470h
0x180061869  lea     rcx, aOnecoreDsExtCl_15; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x180061870  mov     ebx, r8d
0x180061873  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180061878  mov     r9, rax
0x18006187b  lea     rax, Class
0x180061882  mov     [rsp+78h+var_48], rax
0x180061887  lea     rax, aMemcmp; "memcmp"
0x18006188e  mov     [rsp+78h+var_50], rax
0x180061893  mov     dword ptr [rsp+78h+var_58], 0EDh
0x18006189b  jmp     loc_1800619AC
0x1800618a0  mov     ecx, 20h ; ' '; uBytes
0x1800618a5  call    ?AllocateMemory@@YAPEAXK@Z; AllocateMemory(ulong)
0x1800618aa  mov     rdi, rax
0x1800618ad  test    rax, rax
0x1800618b0  jnz     short loc_1800618EE
0x1800618b2  lea     rcx, aOnecoreDsExtCl_15; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x1800618b9  mov     ebx, 0C0000017h
0x1800618be  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800618c3  mov     r9, rax
0x1800618c6  lea     rax, Class
0x1800618cd  mov     [rsp+78h+var_48], rax
0x1800618d2  lea     rax, aAllocatememory; "AllocateMemory"
0x1800618d9  mov     [rsp+78h+var_50], rax
0x1800618de  mov     dword ptr [rsp+78h+var_58], 0F5h
0x1800618e6  mov     r8d, ebx
0x1800618e9  jmp     loc_1800619AC
0x1800618ee  mov     r9, rdi
0x1800618f1  lea     rcx, [r13+4]; Source
0x1800618f5  mov     edx, r12d; BufferSize
0x1800618f8  call    ??$Deserialize@U_DPAPICloudKeyCache@@@@YAJPEAEKP6AXPEAX1@ZPEAU_DPAPICloudKeyCache@@@Z; Deserialize<_DPAPICloudKeyCache>(uchar *,ulong,void (*)(void *,void *),_DPAPICloudKeyCache *)
0x1800618fd  mov     ebx, eax
0x1800618ff  test    eax, eax
0x180061901  jz      short loc_180061934
0x180061903  lea     rcx, aOnecoreDsExtCl_15; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18006190a  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18006190f  mov     r9, rax
0x180061912  lea     rax, Class
0x180061919  mov     [rsp+78h+var_48], rax
0x18006191e  lea     rax, aDeserializeDpa; "Deserialize<DPAPICloudKeyCache>"
0x180061925  mov     [rsp+78h+var_50], rax
0x18006192a  mov     dword ptr [rsp+78h+var_58], 0FDh
0x180061932  jmp     short loc_1800618E6
0x180061934  mov     [r14], rdi
0x180061937  xor     edi, edi
0x180061939  jmp     short loc_1800619BA
0x18006193b  lea     rcx, aOnecoreDsExtCl_15; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x180061942  mov     ebx, 0C0000225h
0x180061947  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18006194c  mov     r9, rax
0x18006194f  lea     rax, Class
0x180061956  mov     [rsp+78h+var_48], rax
0x18006195b  lea     rax, aSerializedLive; "Serialized LiveSSP buffer does not cont"...
0x180061962  mov     [rsp+78h+var_50], rax
0x180061967  mov     dword ptr [rsp+78h+var_58], 0AFh
0x18006196f  jmp     loc_18006172D
0x180061974  mov     r8d, 0C000000Dh
0x18006197a  lea     rcx, aOnecoreDsExtCl_15; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x180061981  mov     ebx, r8d
0x180061984  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180061989  mov     r9, rax
0x18006198c  lea     rax, Class
0x180061993  mov     [rsp+78h+var_48], rax
0x180061998  lea     rax, aInvalidargS; "InvalidArg(s)"
0x18006199f  mov     [rsp+78h+var_50], rax
0x1800619a4  mov     dword ptr [rsp+78h+var_58], 0A5h
0x1800619ac  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x1800619b3  xor     ecx, ecx
0x1800619b5  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x1800619ba  test    rsi, rsi
0x1800619bd  jz      short loc_1800619C7
0x1800619bf  mov     rcx, rsi; void *
0x1800619c2  call    ?FreeMemory@@YAXPEAX@Z; FreeMemory(void *)
0x1800619c7  test    rdi, rdi
0x1800619ca  jz      short loc_1800619D4
0x1800619cc  mov     rcx, rdi; struct _DPAPICloudKeyCache *
0x1800619cf  call    ?FreeLiveSSPCache@@YAXPEAU_DPAPICloudKeyCache@@@Z; FreeLiveSSPCache(_DPAPICloudKeyCache *)
0x1800619d4  mov     eax, ebx
0x1800619d6  mov     rbx, [rsp+78h+arg_8]
0x1800619de  add     rsp, 40h
0x1800619e2  pop     r15
0x1800619e4  pop     r14
0x1800619e6  pop     r13
0x1800619e8  pop     r12
0x1800619ea  pop     rdi
0x1800619eb  pop     rsi
0x1800619ec  pop     rbp
0x1800619ed  retn
```
