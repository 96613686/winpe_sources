# AllocateInteractiveProfileHelper<_KERB_INTERACTIVE_PROFILE_WOW64>(void * *,bool,bool,bool,_APPLUGIN_USER_INFO *,_ApPluginPkg *,_USER_CACHE_ENTRY *,_KERB_INTERACTIVE_PROFILE_WOW64 * *,_KERB_INTERACTIVE_PROFILE_WOW64 * *,ulong *)

- ea: `0x18001d010`
- end: `0x18001d6ae`
- name: `??$AllocateInteractiveProfileHelper@U_KERB_INTERACTIVE_PROFILE_WOW64@@@@YAJPEAPEAX_N11PEAU_APPLUGIN_USER_INFO@@PEAU_ApPluginPkg@@PEAU_USER_CACHE_ENTRY@@PEAPEAU_KERB_INTERACTIVE_PROFILE_WOW64@@5PEAK@Z`
- size: `1694`
- prototype: `__int64 __fastcall(__int64, char, char, char, __int64, __int64, __int64, _QWORD *, union _LARGE_INTEGER **, _DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011960`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x18001d010`
- `0x180051ab4`
- `0x180081010`

## string_xrefs

- `0x18001d0c6`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18001d1cc`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18001d224`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18001d300`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18001d378`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18001d3e7`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18001d454`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18001d4bc`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18001d527`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18001d5ae`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18001d609`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18001d5c9`: `CopyToClientBuffer`

## pseudocode

```c
__int64 __fastcall AllocateInteractiveProfileHelper<_KERB_INTERACTIVE_PROFILE_WOW64>(
        __int64 a1,
        char a2,
        char a3,
        char a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        _QWORD *a8,
        union _LARGE_INTEGER **a9,
        _DWORD *a10)
{
  unsigned __int16 *v10; // rax
  _DWORD *v11; // rbx
  __int64 v12; // r14
  union _LARGE_INTEGER *v13; // rdi
  unsigned int v14; // ebx
  const char *v15; // r9
  const char *v16; // rax
  bool v17; // zf
  __int64 v18; // r10
  __int64 v19; // rdx
  __int64 v20; // rcx
  int v21; // r11d
  int v22; // ecx
  int v23; // r9d
  int v24; // r8d
  int v25; // edx
  unsigned int v26; // eax
  const char *v27; // r9
  const char *v28; // r9
  const char *v29; // r9
  union _LARGE_INTEGER *v30; // rsi
  const char *v31; // r9
  __int64 v32; // rcx
  const char *v33; // r9
  const char *v34; // r9
  const char *v35; // r9
  const char *v36; // r9
  const char *v37; // r9
  __int64 v38; // rax
  const char *v39; // r9
  size_t Size; // [rsp+20h] [rbp-48h]
  size_t Sizea; // [rsp+20h] [rbp-48h]
  size_t Sizeb; // [rsp+20h] [rbp-48h]
  int v44; // [rsp+44h] [rbp-24h] BYREF
  __int64 v45; // [rsp+48h] [rbp-20h] BYREF
  _QWORD v46[3]; // [rsp+50h] [rbp-18h] BYREF

  v10 = 0;
  v11 = a10;
  v12 = a1;
  *a8 = 0;
  v13 = 0;
  *a9 = 0;
  *a10 = 0;
  v17 = (*(_BYTE *)(a6 + 160) & 1) == 0;
  v44 = 0;
  v46[0] = 0;
  v45 = 0;
  if ( v17 )
    goto LABEL_11;
  v14 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, __int64 *, int *))g_pLsaIdProvHostFunctionTable + 4))(
          *(_QWORD *)(a6 + 16),
          *(_QWORD *)(a7 + 96),
          0,
          10,
          &v45,
          &v44);
  if ( !v14 )
  {
    v10 = (unsigned __int16 *)v45;
    v11 = a10;
LABEL_11:
    v18 = -1;
    v19 = *(_QWORD *)(a5 + 40);
    if ( v19 )
    {
      v20 = -1;
      do
        ++v20;
      while ( *(_WORD *)(v19 + 2 * v20) );
      v21 = v20 + 1;
    }
    else
    {
      v21 = 0;
    }
    if ( v10 )
      v22 = v10[4] + 4;
    else
      v22 = 2;
    if ( v10 )
      v23 = v10[12] + 2;
    else
      v23 = 0;
    if ( v10 )
      v24 = v10[20] + 2;
    else
      v24 = 0;
    if ( v10 )
      v25 = v10[28] + 2;
    else
      v25 = 0;
    do
      ++v18;
    while ( *(&g_awchComputerName + v18) );
    v26 = v25 + v24 + v23 + v22 + 2 * (v18 + v21);
    if ( v26 + 112 < v26 )
    {
      *v11 = -1;
      v14 = -1073741675;
      v39 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      LODWORD(Size) = 5021;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225621LL, v39, Size, "RtlDWordAdd", &Class);
      goto LABEL_70;
    }
    *v11 = v26 + 112;
    v13 = (union _LARGE_INTEGER *)((__int64 (*)(void))g_pLsaFunctionTable->AllocateLsaHeap)();
    if ( !v13 )
    {
      v14 = -1073741801;
      v27 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      LODWORD(Size) = 5027;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v27, Size, "AllocateLsaHeap", &Class);
      goto LABEL_70;
    }
    v14 = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD *))g_pLsaFunctionTable->AllocateClientBuffer)(
            v12,
            (unsigned int)*v11,
            v46);
    if ( v14 )
    {
      v28 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      LODWORD(Size) = 5036;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v14, v28, Size, "AllocateClientBuffer", &Class);
      goto LABEL_70;
    }
    v13->LowPart = 2;
    v13[1] = g_TimeNever;
    v13[3] = g_TimeForever;
    v13[4] = g_TimeNever;
    v13[5] = g_TimeForever;
    v13[2] = g_TimeForever;
    if ( (*(_DWORD *)(a6 + 160) & 0x40) == 0 || *(_QWORD *)(a5 + 104) == g_TimeNever.QuadPart )
    {
      v13[6] = g_TimeForever;
    }
    else
    {
      v13[6].LowPart = *(_DWORD *)(a5 + 104);
      v13[6].HighPart = *(_DWORD *)(a5 + 108);
    }
    if ( *(_QWORD *)(a5 + 40) && (v14 = PutClientString<_STRING32>(&v13[14], *(_QWORD *)(a5 + 40))) != 0 )
    {
      v29 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      LODWORD(Sizea) = 5078;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v14, v29, Sizea, "PutClientString", &Class);
    }
    else
    {
      v30 = v13 + 14;
      v14 = PutClientString<_STRING32>(&v13[14], (size_t)&g_awchComputerName);
      if ( !v14 )
      {
        v32 = v45;
        if ( v45 )
        {
          if ( *(_WORD *)(v45 + 8) )
          {
            v14 = PutClientString<_STRING32>(v30, *(_QWORD *)(v45 + 16));
            if ( v14 )
            {
              v33 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
              LODWORD(Sizeb) = 5105;
              WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v14, v33, Sizeb, "PutClientString", &Class);
              goto LABEL_41;
            }
            v32 = v45;
          }
          if ( *(_WORD *)(v32 + 24) )
          {
            v14 = PutClientString<_STRING32>(v30, *(_QWORD *)(v32 + 32));
            if ( v14 )
            {
              v34 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
              LODWORD(Sizeb) = 5119;
              WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v14, v34, Sizeb, "PutClientString", &Class);
              goto LABEL_41;
            }
            v32 = v45;
          }
          if ( *(_WORD *)(v32 + 40) )
          {
            v14 = PutClientString<_STRING32>(v30, *(_QWORD *)(v32 + 48));
            if ( v14 )
            {
              v35 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
              LODWORD(Sizeb) = 5133;
              WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v14, v35, Sizeb, "PutClientString", &Class);
              goto LABEL_41;
            }
            v32 = v45;
          }
          if ( *(_WORD *)(v32 + 56) )
          {
            v14 = PutClientString<_STRING32>(v30, *(_QWORD *)(v32 + 64));
            if ( v14 )
            {
              v36 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
              LODWORD(Sizeb) = 5147;
              WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v14, v36, Sizeb, "PutClientString", &Class);
              goto LABEL_41;
            }
          }
        }
        if ( a3 )
          v13[13].LowPart = 4;
        if ( a2 )
          v13[13].LowPart |= 0x8000u;
        if ( a4 )
          v13[13].LowPart |= 0x20000u;
        v12 = a1;
        v14 = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, union _LARGE_INTEGER *))g_pLsaFunctionTable->CopyToClientBuffer)(
                a1,
                (unsigned int)*a10,
                v46[0],
                v13);
        if ( v14 )
        {
          v37 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          LODWORD(Sizeb) = 5178;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v14, v37, Sizeb, "CopyToClientBuffer", &Class);
        }
        else
        {
          v38 = v46[0];
          v14 = 0;
          v46[0] = 0;
          *a8 = v38;
          *a9 = v13;
          v13 = 0;
        }
        goto LABEL_70;
      }
      v31 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      LODWORD(Sizeb) = 5090;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v14, v31, Sizeb, "PutClientString", &Class);
    }
LABEL_41:
    v12 = a1;
    goto LABEL_70;
  }
  v15 = "";
  while ( 1 )
  {
    v16 = v15--;
    v17 = *v15 == 92;
    if ( *v15 == 92 )
      break;
    if ( v15 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
    {
      v17 = *v15 == 92;
      break;
    }
  }
  if ( v17 )
    v15 = v16;
  LODWORD(Size) = 5001;
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v14, v15, Size, "LookUpUserInfo(LIIC_ProfileProperties)", &Class);
LABEL_70:
  if ( v46[0] )
    ((void (__fastcall *)(__int64))g_pLsaFunctionTable->FreeClientBuffer)(v12);
  if ( v13 )
    ((void (__fastcall *)(union _LARGE_INTEGER *))g_pLsaFunctionTable->FreeLsaHeap)(v13);
  if ( v45 )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  return v14;
}

```

## disassembly

```asm
0x18001d010  mov     rax, rsp
0x18001d013  mov     [rax+20h], r9b
0x18001d017  mov     [rax+18h], r8b
0x18001d01b  mov     [rax+10h], dl
0x18001d01e  mov     [rax+8], rcx
0x18001d022  push    rbp
0x18001d023  push    rbx
0x18001d024  push    rsi
0x18001d025  push    rdi
0x18001d026  push    r12
0x18001d028  push    r13
0x18001d02a  push    r14
0x18001d02c  push    r15
0x18001d02e  mov     rbp, rsp
0x18001d031  sub     rsp, 68h
0x18001d035  mov     r9, [rbp+arg_38]
0x18001d03c  xor     r15d, r15d
0x18001d03f  mov     rdx, [rbp+arg_40]
0x18001d046  mov     eax, r15d
0x18001d049  mov     rbx, [rbp+arg_48]
0x18001d050  mov     r14, rcx
0x18001d053  mov     r13, [rbp+arg_28]
0x18001d057  mov     r12d, r15d
0x18001d05a  mov     [r9], r15
0x18001d05d  mov     edi, r15d
0x18001d060  mov     [rdx], r15
0x18001d063  mov     [rbx], r15d
0x18001d066  test    byte ptr [r13+0A0h], 1
0x18001d06e  mov     [rbp+var_28], r15d
0x18001d072  mov     [rbp+var_24], r15d
0x18001d076  mov     [rbp+var_18], r15
0x18001d07a  mov     [rbp+var_20], rax
0x18001d07e  jz      loc_18001D116
0x18001d084  mov     rax, cs:?g_pLsaIdProvHostFunctionTable@@3PEAU_LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE@@EA; _LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE * g_pLsaIdProvHostFunctionTable
0x18001d08b  lea     rcx, [rbp+var_24]
0x18001d08f  mov     rdx, [rbp+arg_30]
0x18001d093  lea     r9d, [r15+0Ah]
0x18001d097  mov     [rsp+68h+var_40], rcx
0x18001d09c  xor     r8d, r8d
0x18001d09f  lea     rcx, [rbp+var_20]
0x18001d0a3  mov     rax, [rax+20h]
0x18001d0a7  mov     rdx, [rdx+60h]
0x18001d0ab  mov     [rsp+68h+Size], rcx
0x18001d0b0  mov     rcx, [r13+10h]
0x18001d0b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d0b9  mov     ebx, eax
0x18001d0bb  test    eax, eax
0x18001d0bd  jz      short loc_18001D10B
0x18001d0bf  lea     r9, aOnecoreDsExtCl_6+27h; ""
0x18001d0c6  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18001d0cd  mov     rax, r9
0x18001d0d0  dec     r9
0x18001d0d3  cmp     byte ptr [r9], 5Ch ; '\'
0x18001d0d7  jz      short loc_18001D0E2
0x18001d0d9  cmp     r9, rcx
0x18001d0dc  ja      short loc_18001D0CD
0x18001d0de  cmp     byte ptr [r9], 5Ch ; '\'
0x18001d0e2  cmovz   r9, rax
0x18001d0e6  lea     rax, Class
0x18001d0ed  mov     [rsp+68h+var_38], rax
0x18001d0f2  lea     rax, aLookupuserinfo_0; "LookUpUserInfo(LIIC_ProfileProperties)"
0x18001d0f9  mov     [rsp+68h+var_40], rax
0x18001d0fe  mov     dword ptr [rsp+68h+Size], 1389h
0x18001d106  jmp     loc_18001D63D
0x18001d10b  mov     rax, [rbp+var_20]
0x18001d10f  mov     rbx, [rbp+arg_48]
0x18001d116  mov     rsi, [rbp+arg_20]
0x18001d11a  or      r10, 0FFFFFFFFFFFFFFFFh
0x18001d11e  mov     rdx, [rsi+28h]
0x18001d122  test    rdx, rdx
0x18001d125  jz      short loc_18001D13A
0x18001d127  mov     rcx, r10
0x18001d12a  inc     rcx
0x18001d12d  cmp     [rdx+rcx*2], r15w
0x18001d132  jnz     short loc_18001D12A
0x18001d134  lea     r11, [rcx+1]
0x18001d138  jmp     short loc_18001D13D
0x18001d13a  mov     r11, r15
0x18001d13d  test    rax, rax
0x18001d140  jz      short loc_18001D14B
0x18001d142  movzx   ecx, word ptr [rax+8]
0x18001d146  add     ecx, 4
0x18001d149  jmp     short loc_18001D150
0x18001d14b  mov     ecx, 2
0x18001d150  test    rax, rax
0x18001d153  jz      short loc_18001D160
0x18001d155  movzx   r9d, word ptr [rax+18h]
0x18001d15a  add     r9d, 2
0x18001d15e  jmp     short loc_18001D163
0x18001d160  mov     r9d, r15d
0x18001d163  test    rax, rax
0x18001d166  jz      short loc_18001D173
0x18001d168  movzx   r8d, word ptr [rax+28h]
0x18001d16d  add     r8d, 2
0x18001d171  jmp     short loc_18001D176
0x18001d173  mov     r8d, r15d
0x18001d176  test    rax, rax
0x18001d179  jz      short loc_18001D184
0x18001d17b  movzx   edx, word ptr [rax+38h]
0x18001d17f  add     edx, 2
0x18001d182  jmp     short loc_18001D187
0x18001d184  mov     edx, r15d
0x18001d187  lea     rax, ?g_awchComputerName@@3PAGA; ushort near * g_awchComputerName
0x18001d18e  inc     r10
0x18001d191  cmp     [rax+r10*2], r15w
0x18001d196  jnz     short loc_18001D18E
0x18001d198  lea     eax, [r10+r11]
0x18001d19c  lea     eax, [rcx+rax*2]
0x18001d19f  add     eax, r9d
0x18001d1a2  add     eax, r8d
0x18001d1a5  add     eax, edx
0x18001d1a7  lea     ecx, [rax+70h]
0x18001d1aa  cmp     ecx, eax
0x18001d1ac  jb      loc_18001D603
0x18001d1b2  mov     [rbx], ecx
0x18001d1b4  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18001d1bb  mov     rax, [rax+28h]
0x18001d1bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d1c4  mov     rdi, rax
0x18001d1c7  test    rax, rax
0x18001d1ca  jnz     short loc_18001D205
0x18001d1cc  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18001d1d3  mov     ebx, 0C0000017h
0x18001d1d8  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001d1dd  mov     r9, rax
0x18001d1e0  lea     rax, Class
0x18001d1e7  mov     [rsp+68h+var_38], rax
0x18001d1ec  lea     rax, aAllocatelsahea_3; "AllocateLsaHeap"
0x18001d1f3  mov     [rsp+68h+var_40], rax
0x18001d1f8  mov     dword ptr [rsp+68h+Size], 13A3h
0x18001d200  jmp     loc_18001D63D
0x18001d205  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18001d20c  lea     r8, [rbp+var_18]
0x18001d210  mov     edx, [rbx]
0x18001d212  mov     rcx, r14
0x18001d215  mov     rax, [rax+38h]
0x18001d219  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d21e  mov     ebx, eax
0x18001d220  test    eax, eax
0x18001d222  jz      short loc_18001D258
0x18001d224  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18001d22b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001d230  mov     r9, rax
0x18001d233  lea     rax, Class
0x18001d23a  mov     [rsp+68h+var_38], rax
0x18001d23f  lea     rax, aAllocateclient; "AllocateClientBuffer"
0x18001d246  mov     [rsp+68h+var_40], rax
0x18001d24b  mov     dword ptr [rsp+68h+Size], 13ACh
0x18001d253  jmp     loc_18001D63D
0x18001d258  mov     r15, [rbp+var_18]
0x18001d25c  lea     r14, [rdi+70h]
0x18001d260  mov     dword ptr [rdi], 2
0x18001d266  sub     r15, rdi
0x18001d269  mov     rax, cs:?g_TimeNever@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER g_TimeNever
0x18001d270  mov     [rdi+8], rax
0x18001d274  mov     rax, cs:?g_TimeForever@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER g_TimeForever
0x18001d27b  mov     [rdi+18h], rax
0x18001d27f  mov     rax, cs:?g_TimeNever@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER g_TimeNever
0x18001d286  mov     [rdi+20h], rax
0x18001d28a  mov     rax, cs:?g_TimeForever@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER g_TimeForever
0x18001d291  mov     [rdi+28h], rax
0x18001d295  mov     rax, cs:?g_TimeForever@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER g_TimeForever
0x18001d29c  mov     [rdi+10h], rax
0x18001d2a0  mov     eax, [r13+0A0h]
0x18001d2a7  test    al, 40h
0x18001d2a9  jz      short loc_18001D2CE
0x18001d2ab  mov     edx, [rsi+68h]
0x18001d2ae  lea     rcx, [rsi+6Ch]
0x18001d2b2  cmp     edx, dword ptr cs:?g_TimeNever@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER g_TimeNever
0x18001d2b8  jnz     short loc_18001D2C4
0x18001d2ba  mov     eax, dword ptr cs:?g_TimeNever@@3T_LARGE_INTEGER@@A+4; _LARGE_INTEGER g_TimeNever
0x18001d2c0  cmp     [rcx], eax
0x18001d2c2  jz      short loc_18001D2CE
0x18001d2c4  mov     [rdi+30h], edx
0x18001d2c7  mov     eax, [rcx]
0x18001d2c9  mov     [rdi+34h], eax
0x18001d2cc  jmp     short loc_18001D2D9
0x18001d2ce  mov     rax, cs:?g_TimeForever@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER g_TimeForever
0x18001d2d5  mov     [rdi+30h], rax
0x18001d2d9  mov     rax, [rsi+28h]
0x18001d2dd  test    rax, rax
0x18001d2e0  jz      short loc_18001D34D
0x18001d2e2  lea     r9, [rdi+48h]
0x18001d2e6  mov     [rsp+68h+Size], rax; Size
0x18001d2eb  mov     r8, r15
0x18001d2ee  lea     rdx, [rbp+var_28]
0x18001d2f2  mov     rcx, r14; void *
0x18001d2f5  call    ??$PutClientString@U_STRING32@@@@YAJPEAEPEAK_JPEAU_STRING32@@PEBG@Z; PutClientString<_STRING32>(uchar *,ulong *,__int64,_STRING32 *,ushort const *)
0x18001d2fa  mov     ebx, eax
0x18001d2fc  test    eax, eax
0x18001d2fe  jz      short loc_18001D349
0x18001d300  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18001d307  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001d30c  mov     r9, rax
0x18001d30f  lea     rax, Class
0x18001d316  mov     [rsp+68h+var_38], rax
0x18001d31b  lea     rax, aPutclientstrin_1; "PutClientString"
0x18001d322  mov     [rsp+68h+var_40], rax
0x18001d327  mov     dword ptr [rsp+68h+Size], 13D6h
0x18001d32f  mov     r8d, ebx
0x18001d332  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18001d339  xor     ecx, ecx
0x18001d33b  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18001d340  mov     r14, [rbp+arg_0]
0x18001d344  jmp     loc_18001D64E
0x18001d349  mov     r12d, [rbp+var_28]
0x18001d34d  lea     rax, ?g_awchComputerName@@3PAGA; ushort near * g_awchComputerName
0x18001d354  mov     esi, r12d
0x18001d357  add     rsi, r14
0x18001d35a  mov     [rsp+68h+Size], rax; Size
0x18001d35f  mov     rcx, rsi; void *
0x18001d362  lea     r9, [rdi+60h]
0x18001d366  mov     r8, r15
0x18001d369  lea     rdx, [rbp+var_28]
0x18001d36d  call    ??$PutClientString@U_STRING32@@@@YAJPEAEPEAK_JPEAU_STRING32@@PEBG@Z; PutClientString<_STRING32>(uchar *,ulong *,__int64,_STRING32 *,ushort const *)
0x18001d372  mov     ebx, eax
0x18001d374  test    eax, eax
0x18001d376  jz      short loc_18001D3A9
0x18001d378  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18001d37f  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001d384  mov     r9, rax
0x18001d387  lea     rax, Class
0x18001d38e  mov     [rsp+68h+var_38], rax
0x18001d393  lea     rax, aPutclientstrin_1; "PutClientString"
0x18001d39a  mov     [rsp+68h+var_40], rax
0x18001d39f  mov     dword ptr [rsp+68h+Size], 13E2h
0x18001d3a7  jmp     short loc_18001D32F
0x18001d3a9  mov     rcx, [rbp+var_20]
0x18001d3ad  test    rcx, rcx
0x18001d3b0  jz      loc_18001D55B
0x18001d3b6  mov     r14d, [rbp+var_28]
0x18001d3ba  xor     eax, eax
0x18001d3bc  add     r14, rsi
0x18001d3bf  cmp     ax, [rcx+8]
0x18001d3c3  jz      short loc_18001D427
0x18001d3c5  mov     rax, [rcx+10h]
0x18001d3c9  lea     r9, [rdi+50h]
0x18001d3cd  mov     rcx, r14; void *
0x18001d3d0  mov     [rsp+68h+Size], rax; Size
0x18001d3d5  mov     r8, r15
0x18001d3d8  lea     rdx, [rbp+var_28]
0x18001d3dc  call    ??$PutClientString@U_STRING32@@@@YAJPEAEPEAK_JPEAU_STRING32@@PEBG@Z; PutClientString<_STRING32>(uchar *,ulong *,__int64,_STRING32 *,ushort const *)
0x18001d3e1  mov     ebx, eax
0x18001d3e3  test    eax, eax
0x18001d3e5  jz      short loc_18001D41B
0x18001d3e7  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18001d3ee  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001d3f3  mov     r9, rax
0x18001d3f6  lea     rax, Class
0x18001d3fd  mov     [rsp+68h+var_38], rax
0x18001d402  lea     rax, aPutclientstrin_1; "PutClientString"
0x18001d409  mov     [rsp+68h+var_40], rax
0x18001d40e  mov     dword ptr [rsp+68h+Size], 13F1h
0x18001d416  jmp     loc_18001D32F
0x18001d41b  mov     esi, [rbp+var_28]
0x18001d41e  mov     rcx, [rbp+var_20]
0x18001d422  add     rsi, r14
0x18001d425  jmp     short loc_18001D42A
0x18001d427  mov     rsi, r14
0x18001d42a  xor     eax, eax
0x18001d42c  cmp     ax, [rcx+18h]
0x18001d430  jz      short loc_18001D492
0x18001d432  mov     rax, [rcx+20h]
0x18001d436  lea     r9, [rdi+38h]
0x18001d43a  mov     rcx, rsi; void *
0x18001d43d  mov     [rsp+68h+Size], rax; Size
0x18001d442  mov     r8, r15
0x18001d445  lea     rdx, [rbp+var_28]
0x18001d449  call    ??$PutClientString@U_STRING32@@@@YAJPEAEPEAK_JPEAU_STRING32@@PEBG@Z; PutClientString<_STRING32>(uchar *,ulong *,__int64,_STRING32 *,ushort const *)
0x18001d44e  mov     ebx, eax
0x18001d450  test    eax, eax
0x18001d452  jz      short loc_18001D488
0x18001d454  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18001d45b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001d460  mov     r9, rax
0x18001d463  lea     rax, Class
0x18001d46a  mov     [rsp+68h+var_38], rax
0x18001d46f  lea     rax, aPutclientstrin_1; "PutClientString"
0x18001d476  mov     [rsp+68h+var_40], rax
0x18001d47b  mov     dword ptr [rsp+68h+Size], 13FFh
0x18001d483  jmp     loc_18001D32F
0x18001d488  mov     eax, [rbp+var_28]
0x18001d48b  mov     rcx, [rbp+var_20]
0x18001d48f  add     rsi, rax
0x18001d492  xor     eax, eax
0x18001d494  cmp     ax, [rcx+28h]
0x18001d498  jz      short loc_18001D4FA
0x18001d49a  mov     rax, [rcx+30h]
0x18001d49e  lea     r9, [rdi+40h]
0x18001d4a2  mov     rcx, rsi; void *
0x18001d4a5  mov     [rsp+68h+Size], rax; Size
0x18001d4aa  mov     r8, r15
0x18001d4ad  lea     rdx, [rbp+var_28]
0x18001d4b1  call    ??$PutClientString@U_STRING32@@@@YAJPEAEPEAK_JPEAU_STRING32@@PEBG@Z; PutClientString<_STRING32>(uchar *,ulong *,__int64,_STRING32 *,ushort const *)
0x18001d4b6  mov     ebx, eax
0x18001d4b8  test    eax, eax
0x18001d4ba  jz      short loc_18001D4F0
0x18001d4bc  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18001d4c3  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001d4c8  mov     r9, rax
  ... truncated ...
```
