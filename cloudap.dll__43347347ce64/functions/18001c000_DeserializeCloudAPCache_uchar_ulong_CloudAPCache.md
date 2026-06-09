# DeserializeCloudAPCache(uchar *,ulong,_CloudAPCache * *)

- ea: `0x18001c000`
- end: `0x18001c58a`
- name: `?DeserializeCloudAPCache@@YAJPEAEKPEAPEAU_CloudAPCache@@@Z`
- size: `1418`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned int, struct _CloudAPCache **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x18000fb70`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x18000fd50`
- `0x18001c000`
- `0x18001c590`
- `0x18001c9d0`
- `0x18007f9f0`
- `0x180081010`

## import_xrefs

- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18001c0e7`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18001c0e7`
- `bcrypt!BCryptGetProperty` at `0x18001c0b6`
- `bcrypt!BCryptGetProperty` at `0x18001c0b6`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18001c073`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18001c073`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c375`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c375`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c505`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c505`

## string_xrefs

- `0x18001c237`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x18001c28f`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x18001c2c3`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x18001c30e`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x18001c380`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x18001c3b1`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x18001c47c`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x18001c4c2`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x18001c510`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x18001c549`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cloudapcache.cpp`
- `0x18001c3e5`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cryptoutility.cpp`
- `0x18001c40f`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cryptoutility.cpp`
- `0x18001c452`: `onecore\ds\ext\cloudap\libs\cloudapcache\lib\cryptoutility.cpp`
- `0x18001c25f`: `GetBufferChecksumSize`
- `0x18001c1b9`: `CreateBufferChecksum`
- `0x18001c2ee`: `CreateBufferChecksum`
- `0x18001c3f9`: `BCryptOpenAlgorithmProvider`
- `0x18001c564`: `Deserialize<CloudAPCache>`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DeserializeCloudAPCache(unsigned __int8 *a1, unsigned int a2, struct _CloudAPCache **a3)
{
  unsigned __int64 v3; // rsi
  unsigned int v6; // ebp
  unsigned int Property; // ebx
  const unsigned __int16 *v8; // rcx
  struct _CloudAPCache *v9; // rbx
  unsigned int v10; // r12d
  int BufferChecksum; // eax
  void *v12; // r15
  unsigned int v13; // esi
  struct _CloudAPCache *v14; // rax
  const char *v15; // r9
  const char *v17; // r9
  char v18; // cl
  const char *v19; // rdx
  bool v20; // zf
  char v21; // cl
  const char *v22; // rdx
  bool v23; // zf
  char v24; // cl
  const char *v25; // r9
  char v26; // cl
  const char *v27; // rdx
  bool v28; // zf
  const char *v29; // r9
  const char *v30; // r9
  const char *v31; // r9
  const char *v32; // r9
  const char *v33; // r9
  const char *v34; // rax
  const char *v35; // r9
  const char *v36; // r9
  const char *v37; // r9
  ULONG *pcbResult; // [rsp+20h] [rbp-78h]
  ULONG *pcbResulta; // [rsp+20h] [rbp-78h]
  size_t Size; // [rsp+40h] [rbp-58h] BYREF
  BCRYPT_HANDLE hObject; // [rsp+48h] [rbp-50h] BYREF
  void *Buf1; // [rsp+50h] [rbp-48h] BYREF
  ULONG v43; // [rsp+A0h] [rbp+8h] BYREF
  unsigned int pbOutput; // [rsp+B8h] [rbp+20h] BYREF

  v3 = a2;
  Buf1 = 0;
  LODWORD(Size) = 0;
  if ( !a1 || !a3 )
  {
    v25 = "";
    while ( 1 )
    {
      v26 = *(v25 - 1);
      v27 = v25--;
      v28 = v26 == 92;
      if ( v26 == 92 )
        break;
      if ( v25 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
      {
        v28 = v26 == 92;
        break;
      }
    }
    if ( v28 )
      v25 = v27;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v25, 380, "InvalidArgs", &Class);
    return 3221225485LL;
  }
  *a3 = 0;
  if ( a2 < 4 )
  {
    v29 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v29, 389, "InvalidArg:cbSerializedBuffer", &Class);
    return 3221225485LL;
  }
  if ( *(_DWORD *)a1 != 2 )
  {
    v30 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v30, 396, "InvalidArg:serializedBufferVersion", &Class);
    return 3221225485LL;
  }
  hObject = 0;
  v6 = 0;
  pbOutput = 0;
  v43 = 0;
  Property = BCryptOpenAlgorithmProvider(&hObject, L"SHA256", 0, 0);
  if ( Property )
  {
    v31 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cryptoutility.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", Property, v31, 667, "BCryptOpenAlgorithmProvider", &Class);
  }
  else
  {
    Property = BCryptGetProperty(hObject, L"HashDigestLength", (PUCHAR)&pbOutput, 4u, &v43, 0);
    if ( Property )
    {
      v33 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cryptoutility.cpp");
      LODWORD(pcbResult) = 677;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", Property, v33, pcbResult, "BCryptGetProperty", &Class);
    }
    else if ( v43 == 4 )
    {
      v6 = pbOutput;
    }
    else
    {
      Property = -1073741595;
      v32 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cryptoutility.cpp");
      LODWORD(pcbResult) = 682;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225701LL, v32, pcbResult, "BCryptGetProperty", &Class);
    }
  }
  if ( hObject )
    BCryptCloseAlgorithmProvider(hObject, 0);
  if ( !Property )
  {
    v8 = (const unsigned __int16 *)(v6 + 4LL);
    if ( v3 < (unsigned __int64)v8 )
    {
      v34 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
      LODWORD(pcbResult) = 412;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v34, pcbResult, "InvalidArg:cbSerializedBuffer", &Class);
      return 3221225485LL;
    }
    v9 = 0;
    v10 = v3 - v6 - 4;
    BufferChecksum = CreateBufferChecksum(v8, &a1[v6 + 4], v10, (unsigned __int8 **)&Buf1, (unsigned int *)&Size);
    v12 = Buf1;
    v13 = BufferChecksum;
    if ( BufferChecksum )
    {
      v15 = "";
      while ( 1 )
      {
        v21 = *(v15 - 1);
        v22 = v15--;
        v23 = v21 == 92;
        if ( v21 == 92 )
          break;
        if ( v15 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
        {
          v23 = v21 == 92;
          break;
        }
      }
      LODWORD(pcbResulta) = 426;
    }
    else
    {
      if ( (_DWORD)Size == v6 )
      {
        if ( !memcmp_0(Buf1, a1 + 4, (unsigned int)Size) )
        {
          if ( g_pLsaFunctionTable )
            v14 = (struct _CloudAPCache *)((__int64 (__fastcall *)(__int64))g_pLsaFunctionTable->AllocateLsaHeap)(32);
          else
            v14 = (struct _CloudAPCache *)LocalAlloc(0x40u, 0x20u);
          v9 = v14;
          if ( v14 )
          {
            v13 = Deserialize<_CloudAPCache>(&a1[v6 + 4], v10);
            if ( v13 )
            {
              v37 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
              LODWORD(pcbResulta) = 456;
              WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v13, v37, pcbResulta, "Deserialize<CloudAPCache>", &Class);
            }
            else
            {
              *a3 = v9;
              v9 = 0;
            }
          }
          else
          {
            v13 = -1073741801;
            v36 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
            LODWORD(pcbResulta) = 448;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v36, pcbResulta, "AllocateMemory", &Class);
          }
        }
        else
        {
          v13 = -1073740688;
          v35 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp");
          LODWORD(pcbResulta) = 440;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221226608LL, v35, pcbResulta, "memcmp", &Class);
        }
LABEL_25:
        if ( v12 )
        {
          if ( g_pLsaFunctionTable )
            ((void (__fastcall *)(void *))g_pLsaFunctionTable->FreeLsaHeap)(v12);
          else
            LocalFree(v12);
        }
        if ( v9 )
          FreeCloudAPCache(v9);
        return v13;
      }
      v13 = -1073740688;
      v15 = "";
      while ( 1 )
      {
        v24 = *(v15 - 1);
        v22 = v15--;
        v23 = v24 == 92;
        if ( v24 == 92 )
          break;
        if ( v15 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
        {
          v23 = v24 == 92;
          break;
        }
      }
      LODWORD(pcbResulta) = 431;
    }
    if ( v23 )
      v15 = v22;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v13, v15, pcbResulta, "CreateBufferChecksum", &Class);
    goto LABEL_25;
  }
  v17 = "";
  while ( 1 )
  {
    v18 = *(v17 - 1);
    v19 = v17--;
    v20 = v18 == 92;
    if ( v18 == 92 )
      break;
    if ( v17 <= "onecore\\ds\\ext\\cloudap\\libs\\cloudapcache\\lib\\cloudapcache.cpp" )
    {
      v20 = v18 == 92;
      break;
    }
  }
  if ( v20 )
    v17 = v19;
  LODWORD(pcbResult) = 403;
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", Property, v17, pcbResult, "GetBufferChecksumSize", &Class);
  return Property;
}

```

## disassembly

```asm
0x18001c000  mov     rax, rsp
0x18001c003  push    rsi
0x18001c004  push    rdi
0x18001c005  push    r12
0x18001c007  push    r14
0x18001c009  sub     rsp, 78h
0x18001c00d  xor     r12d, r12d
0x18001c010  mov     esi, edx
0x18001c012  mov     [rax-48h], r12
0x18001c016  mov     r14, r8
0x18001c019  mov     [rax-58h], r12d
0x18001c01d  mov     rdi, rcx
0x18001c020  test    rcx, rcx
0x18001c023  jz      loc_18001C307
0x18001c029  test    r8, r8
0x18001c02c  jz      loc_18001C307
0x18001c032  mov     [r8], r12
0x18001c035  cmp     esi, 4
0x18001c038  jb      loc_18001C380
0x18001c03e  cmp     dword ptr [rcx], 2
0x18001c041  jnz     loc_18001C3B1
0x18001c047  mov     [rax+10h], rbx
0x18001c04b  lea     rdx, pszAlgId; "SHA256"
0x18001c052  mov     [rax-28h], rbp
0x18001c056  lea     rcx, [rax-50h]; phAlgorithm
0x18001c05a  xor     r9d, r9d; dwFlags
0x18001c05d  mov     [rax-38h], r15
0x18001c061  xor     r8d, r8d; pszImplementation
0x18001c064  mov     [rax-50h], r12
0x18001c068  mov     ebp, r12d
0x18001c06b  mov     [rax+20h], r12d
0x18001c06f  mov     [rax+8], r12d
0x18001c073  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18001c079  lea     r15, Class
0x18001c080  mov     ebx, eax
0x18001c082  test    eax, eax
0x18001c084  jnz     loc_18001C3E5
0x18001c08a  mov     rcx, [rsp+98h+hObject]; hObject
0x18001c08f  lea     rax, [rsp+98h+arg_0]
0x18001c097  mov     [rsp+98h+dwFlags], r12d; dwFlags
0x18001c09c  lea     r8, [rsp+98h+pbOutput]; pbOutput
0x18001c0a4  mov     r9d, 4; cbOutput
0x18001c0aa  mov     [rsp+98h+pcbResult], rax; pcbResult
0x18001c0af  lea     rdx, pszProperty; "HashDigestLength"
0x18001c0b6  call    cs:__imp_BCryptGetProperty
0x18001c0bc  mov     ebx, eax
0x18001c0be  test    eax, eax
0x18001c0c0  jnz     loc_18001C452
0x18001c0c6  cmp     [rsp+98h+arg_0], 4
0x18001c0ce  jnz     loc_18001C40F
0x18001c0d4  mov     ebp, [rsp+98h+pbOutput]
0x18001c0db  mov     rcx, [rsp+98h+hObject]; hAlgorithm
0x18001c0e0  test    rcx, rcx
0x18001c0e3  jz      short loc_18001C0ED
0x18001c0e5  xor     edx, edx; dwFlags
0x18001c0e7  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18001c0ed  test    ebx, ebx
0x18001c0ef  jnz     loc_18001C230
0x18001c0f5  mov     edx, ebp
0x18001c0f7  lea     rcx, [rdx+4]; unsigned __int16 *
0x18001c0fb  cmp     rsi, rcx
0x18001c0fe  jb      loc_18001C47C
0x18001c104  lea     rax, [rsp+98h+Size]
0x18001c109  mov     [rsp+98h+var_30], r13
0x18001c10e  lea     r13, [rdx+rdi]
0x18001c112  mov     [rsp+98h+pcbResult], rax; unsigned int *
0x18001c117  sub     esi, ebp
0x18001c119  lea     r9, [rsp+98h+Buf1]; unsigned __int8 **
0x18001c11e  mov     rbx, r12
0x18001c121  lea     rdx, [r13+4]; unsigned __int8 *
0x18001c125  lea     r12d, [rsi-4]
0x18001c129  mov     r8d, r12d; unsigned int
0x18001c12c  call    ?CreateBufferChecksum@@YAJPEBGPEAEKPEAPEAEPEAK@Z; CreateBufferChecksum(ushort const *,uchar *,ulong,uchar * *,ulong *)
0x18001c131  mov     r15, [rsp+98h+Buf1]
0x18001c136  mov     esi, eax
0x18001c138  test    eax, eax
0x18001c13a  jnz     loc_18001C288
0x18001c140  mov     eax, dword ptr [rsp+98h+Size]
0x18001c144  cmp     eax, ebp
0x18001c146  jnz     loc_18001C2B7
0x18001c14c  mov     r8d, eax; Size
0x18001c14f  lea     rdx, [rdi+4]; Buf2
0x18001c153  mov     rcx, r15; Buf1
0x18001c156  call    memcmp_0
0x18001c15b  test    eax, eax
0x18001c15d  jnz     loc_18001C4C2
0x18001c163  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18001c16a  test    rax, rax
0x18001c16d  jz      loc_18001C4FB
0x18001c173  mov     rax, [rax+28h]
0x18001c177  mov     ecx, 20h ; ' '
0x18001c17c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c181  mov     rbx, rax
0x18001c184  test    rax, rax
0x18001c187  jz      loc_18001C510
0x18001c18d  mov     r9, rax
0x18001c190  lea     rcx, [r13+4]; Source
0x18001c194  mov     edx, r12d; SourceSize
0x18001c197  call    ??$Deserialize@U_CloudAPCache@@@@YAJPEAEKP6AXPEAX1@ZPEAU_CloudAPCache@@@Z; Deserialize<_CloudAPCache>(uchar *,ulong,void (*)(void *,void *),_CloudAPCache *)
0x18001c19c  mov     esi, eax
0x18001c19e  test    eax, eax
0x18001c1a0  jnz     loc_18001C549
0x18001c1a6  mov     [r14], rbx
0x18001c1a9  xor     ebx, ebx
0x18001c1ab  jmp     short loc_18001C1E2
0x18001c1ad  lea     rax, Class
0x18001c1b4  mov     [rsp+98h+var_68], rax
0x18001c1b9  lea     rax, aCreatebufferch; "CreateBufferChecksum"
0x18001c1c0  mov     qword ptr [rsp+98h+dwFlags], rax
0x18001c1c5  mov     dword ptr [rsp+98h+pcbResult], 1AAh
0x18001c1cd  cmovz   r9, rdx
0x18001c1d1  mov     r8d, esi
0x18001c1d4  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18001c1db  xor     ecx, ecx
0x18001c1dd  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18001c1e2  mov     r13, [rsp+98h+var_30]
0x18001c1e7  test    r15, r15
0x18001c1ea  jz      short loc_18001C208
0x18001c1ec  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18001c1f3  mov     rcx, r15; hMem
0x18001c1f6  test    rax, rax
0x18001c1f9  jz      loc_18001C375
0x18001c1ff  mov     rax, [rax+30h]
0x18001c203  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c208  test    rbx, rbx
0x18001c20b  jnz     loc_18001C57D
0x18001c211  mov     eax, esi
0x18001c213  mov     rbp, [rsp+98h+var_28]
0x18001c218  mov     rbx, [rsp+98h+arg_8]
0x18001c220  mov     r15, [rsp+98h+var_38]
0x18001c225  add     rsp, 78h
0x18001c229  pop     r14
0x18001c22b  pop     r12
0x18001c22d  pop     rdi
0x18001c22e  pop     rsi
0x18001c22f  retn
0x18001c230  lea     r9, aOnecoreDsExtCl_2+3Dh; ""
0x18001c237  lea     rax, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18001c23e  movzx   ecx, byte ptr [r9-1]
0x18001c243  mov     rdx, r9
0x18001c246  dec     r9
0x18001c249  cmp     cl, 5Ch ; '\'
0x18001c24c  jz      short loc_18001C256
0x18001c24e  cmp     r9, rax
0x18001c251  ja      short loc_18001C23E
0x18001c253  cmp     cl, 5Ch ; '\'
0x18001c256  cmovz   r9, rdx
0x18001c25a  mov     [rsp+98h+var_68], r15
0x18001c25f  lea     rax, aGetbuffercheck; "GetBufferChecksumSize"
0x18001c266  mov     r8d, ebx
0x18001c269  mov     qword ptr [rsp+98h+dwFlags], rax
0x18001c26e  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18001c275  xor     ecx, ecx
0x18001c277  mov     dword ptr [rsp+98h+pcbResult], 193h
0x18001c27f  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18001c284  mov     eax, ebx
0x18001c286  jmp     short loc_18001C213
0x18001c288  lea     r9, aOnecoreDsExtCl_2+3Dh; ""
0x18001c28f  lea     rax, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18001c296  movzx   ecx, byte ptr [r9-1]
0x18001c29b  mov     rdx, r9
0x18001c29e  dec     r9
0x18001c2a1  cmp     cl, 5Ch ; '\'
0x18001c2a4  jz      loc_18001C1AD
0x18001c2aa  cmp     r9, rax
0x18001c2ad  ja      short loc_18001C296
0x18001c2af  cmp     cl, 5Ch ; '\'
0x18001c2b2  jmp     loc_18001C1AD
0x18001c2b7  mov     esi, 0C0000470h
0x18001c2bc  lea     r9, aOnecoreDsExtCl_2+3Dh; ""
0x18001c2c3  lea     rax, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18001c2ca  movzx   ecx, byte ptr [r9-1]
0x18001c2cf  mov     rdx, r9
0x18001c2d2  dec     r9
0x18001c2d5  cmp     cl, 5Ch ; '\'
0x18001c2d8  jz      short loc_18001C2E2
0x18001c2da  cmp     r9, rax
0x18001c2dd  ja      short loc_18001C2CA
0x18001c2df  cmp     cl, 5Ch ; '\'
0x18001c2e2  lea     rax, Class
0x18001c2e9  mov     [rsp+98h+var_68], rax
0x18001c2ee  lea     rax, aCreatebufferch; "CreateBufferChecksum"
0x18001c2f5  mov     qword ptr [rsp+98h+dwFlags], rax
0x18001c2fa  mov     dword ptr [rsp+98h+pcbResult], 1AFh
0x18001c302  jmp     loc_18001C1CD
0x18001c307  lea     r9, aOnecoreDsExtCl_2+3Dh; ""
0x18001c30e  lea     rax, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18001c315  movzx   ecx, byte ptr [r9-1]
0x18001c31a  mov     rdx, r9
0x18001c31d  dec     r9
0x18001c320  cmp     cl, 5Ch ; '\'
0x18001c323  jz      short loc_18001C32D
0x18001c325  cmp     r9, rax
0x18001c328  ja      short loc_18001C315
0x18001c32a  cmp     cl, 5Ch ; '\'
0x18001c32d  lea     rax, Class
0x18001c334  cmovz   r9, rdx
0x18001c338  mov     [rsp+98h+var_68], rax
0x18001c33d  lea     rax, aInvalidargs; "InvalidArgs"
0x18001c344  mov     qword ptr [rsp+98h+dwFlags], rax
0x18001c349  mov     dword ptr [rsp+98h+pcbResult], 17Ch
0x18001c351  mov     r8d, 0C000000Dh
0x18001c357  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18001c35e  xor     ecx, ecx
0x18001c360  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18001c365  mov     eax, 0C000000Dh
0x18001c36a  add     rsp, 78h
0x18001c36e  pop     r14
0x18001c370  pop     r12
0x18001c372  pop     rdi
0x18001c373  pop     rsi
0x18001c374  retn
0x18001c375  call    cs:__imp_LocalFree
0x18001c37b  jmp     loc_18001C208
0x18001c380  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18001c387  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001c38c  mov     r9, rax
0x18001c38f  lea     rax, Class
0x18001c396  mov     [rsp+98h+var_68], rax
0x18001c39b  lea     rax, aInvalidargCbse; "InvalidArg:cbSerializedBuffer"
0x18001c3a2  mov     qword ptr [rsp+98h+dwFlags], rax
0x18001c3a7  mov     dword ptr [rsp+98h+pcbResult], 185h
0x18001c3af  jmp     short loc_18001C351
0x18001c3b1  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18001c3b8  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001c3bd  mov     r9, rax
0x18001c3c0  lea     rax, Class
0x18001c3c7  mov     [rsp+98h+var_68], rax
0x18001c3cc  lea     rax, aInvalidargSeri; "InvalidArg:serializedBufferVersion"
0x18001c3d3  mov     qword ptr [rsp+98h+dwFlags], rax
0x18001c3d8  mov     dword ptr [rsp+98h+pcbResult], 18Ch
0x18001c3e0  jmp     loc_18001C351
0x18001c3e5  lea     rcx, aOnecoreDsExtCl_3; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18001c3ec  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001c3f1  mov     [rsp+98h+var_68], r15
0x18001c3f6  mov     r9, rax
0x18001c3f9  lea     rax, aBcryptopenalgo_0; "BCryptOpenAlgorithmProvider"
0x18001c400  mov     qword ptr [rsp+98h+dwFlags], rax
0x18001c405  mov     dword ptr [rsp+98h+pcbResult], 29Bh
0x18001c40d  jmp     short loc_18001C43C
0x18001c40f  lea     rcx, aOnecoreDsExtCl_3; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18001c416  mov     ebx, 0C00000E5h
0x18001c41b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001c420  mov     [rsp+98h+var_68], r15
0x18001c425  mov     r9, rax
0x18001c428  lea     rax, aBcryptgetprope; "BCryptGetProperty"
0x18001c42f  mov     qword ptr [rsp+98h+dwFlags], rax
0x18001c434  mov     dword ptr [rsp+98h+pcbResult], 2AAh
0x18001c43c  mov     r8d, ebx
0x18001c43f  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18001c446  xor     ecx, ecx
0x18001c448  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18001c44d  jmp     loc_18001C0DB
0x18001c452  lea     rcx, aOnecoreDsExtCl_3; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18001c459  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001c45e  mov     [rsp+98h+var_68], r15
0x18001c463  mov     r9, rax
0x18001c466  lea     rax, aBcryptgetprope; "BCryptGetProperty"
0x18001c46d  mov     qword ptr [rsp+98h+dwFlags], rax
0x18001c472  mov     dword ptr [rsp+98h+pcbResult], 2A5h
0x18001c47a  jmp     short loc_18001C43C
0x18001c47c  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18001c483  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001c488  mov     r9, rax
0x18001c48b  mov     [rsp+98h+var_68], r15
0x18001c490  lea     rax, aInvalidargCbse; "InvalidArg:cbSerializedBuffer"
0x18001c497  mov     r8d, 0C000000Dh
0x18001c49d  mov     qword ptr [rsp+98h+dwFlags], rax
0x18001c4a2  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18001c4a9  xor     ecx, ecx
0x18001c4ab  mov     dword ptr [rsp+98h+pcbResult], 19Ch
0x18001c4b3  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18001c4b8  mov     eax, 0C000000Dh
0x18001c4bd  jmp     loc_18001C213
0x18001c4c2  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18001c4c9  mov     esi, 0C0000470h
0x18001c4ce  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001c4d3  mov     r9, rax
0x18001c4d6  lea     rax, Class
0x18001c4dd  mov     [rsp+98h+var_68], rax
0x18001c4e2  lea     rax, aMemcmp; "memcmp"
0x18001c4e9  mov     qword ptr [rsp+98h+dwFlags], rax
0x18001c4ee  mov     dword ptr [rsp+98h+pcbResult], 1B8h
0x18001c4f6  jmp     loc_18001C1D1
0x18001c4fb  mov     edx, 20h ; ' '; uBytes
0x18001c500  mov     ecx, 40h ; '@'; uFlags
0x18001c505  call    cs:__imp_LocalAlloc
0x18001c50b  jmp     loc_18001C181
0x18001c510  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18001c517  mov     esi, 0C0000017h
0x18001c51c  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001c521  mov     r9, rax
0x18001c524  lea     rax, Class
0x18001c52b  mov     [rsp+98h+var_68], rax
0x18001c530  lea     rax, aAllocatememory; "AllocateMemory"
0x18001c537  mov     qword ptr [rsp+98h+dwFlags], rax
0x18001c53c  mov     dword ptr [rsp+98h+pcbResult], 1C0h
0x18001c544  jmp     loc_18001C1D1
0x18001c549  lea     rcx, aOnecoreDsExtCl_2; "onecore\\ds\\ext\\cloudap\\libs\\clouda"...
0x18001c550  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
  ... truncated ...
```
