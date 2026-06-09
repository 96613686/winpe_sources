# AllocateInteractiveProfileHelper<_KERB_INTERACTIVE_PROFILE>(void * *,bool,bool,bool,_APPLUGIN_USER_INFO *,_ApPluginPkg *,_USER_CACHE_ENTRY *,_KERB_INTERACTIVE_PROFILE * *,_KERB_INTERACTIVE_PROFILE * *,ulong *)

- ea: `0x18001d6c0`
- end: `0x18001e070`
- name: `??$AllocateInteractiveProfileHelper@U_KERB_INTERACTIVE_PROFILE@@@@YAJPEAPEAX_N11PEAU_APPLUGIN_USER_INFO@@PEAU_ApPluginPkg@@PEAU_USER_CACHE_ENTRY@@PEAPEAU_KERB_INTERACTIVE_PROFILE@@5PEAK@Z`
- size: `2480`
- prototype: `__int64 __fastcall(__int64, char, char, char, __int64, __int64, __int64, _QWORD *, __int64 *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011960`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x18000b850`
- `0x18001d6c0`
- `0x18007f9fc`
- `0x180081010`

## string_xrefs

- `0x18001d8a4`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18001d943`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18001da57`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18001daaf`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18001dc53`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18001dcb8`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18001dd4e`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18001ddde`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18001de49`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18001dec1`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18001def5`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18001df6c`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18001dfc8`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18001e012`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18001e02f`: `CopyToClientBuffer`

## pseudocode

```c
__int64 __fastcall AllocateInteractiveProfileHelper<_KERB_INTERACTIVE_PROFILE>(
        __int64 a1,
        char a2,
        char a3,
        char a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        _QWORD *a8,
        __int64 *a9,
        unsigned int *a10)
{
  __int64 v10; // rdi
  unsigned int *v11; // r14
  __int64 v12; // r12
  unsigned __int16 *v13; // r10
  __int64 v14; // r13
  __int64 v15; // rcx
  __int64 v16; // rax
  int v17; // r8d
  int v18; // edx
  __int64 v19; // rax
  unsigned int v20; // edx
  unsigned int v21; // edi
  __int64 v22; // r15
  __int64 v23; // rdi
  __int64 v24; // r15
  _WORD *v25; // rdx
  unsigned int v26; // edx
  __int64 v27; // rax
  unsigned __int64 v28; // rcx
  const char *v29; // rbx
  const char *v30; // r9
  char v31; // al
  const char *v32; // rcx
  const char *v33; // rax
  int v34; // ecx
  char v35; // al
  const char *v36; // rcx
  __int64 v37; // r10
  const char *v38; // rax
  int v39; // ecx
  char v40; // al
  const char *v41; // rcx
  bool v42; // zf
  __int64 v43; // r13
  char v45; // al
  const char *v46; // rcx
  bool v47; // zf
  __int64 v48; // rax
  unsigned __int64 v49; // rcx
  const char *v50; // rbx
  char v51; // al
  const char *v52; // rcx
  const char *v53; // rax
  int v54; // ecx
  char *v55; // rdi
  __int64 v56; // rbx
  int v57; // eax
  __int64 v58; // rcx
  char *v59; // r14
  __int16 v60; // ax
  __int64 v61; // rax
  char v62; // al
  const char *v63; // rcx
  _WORD *v64; // rdx
  unsigned __int64 v65; // rax
  const char *v66; // r9
  char v67; // al
  const char *v68; // rcx
  const char *v69; // rax
  int v70; // ecx
  char v71; // al
  const char *v72; // rcx
  char v73; // al
  const char *v74; // rcx
  bool v75; // zf
  __int64 v76; // rbx
  char v77; // al
  const char *v78; // rcx
  __int64 v79; // rbx
  char v80; // al
  const char *v81; // rcx
  char v82; // al
  const char *v83; // rcx
  void *Src; // [rsp+28h] [rbp-59h]
  int v85; // [rsp+48h] [rbp-39h] BYREF
  unsigned int v86; // [rsp+4Ch] [rbp-35h]
  __int64 v87; // [rsp+50h] [rbp-31h] BYREF
  __int64 v88; // [rsp+58h] [rbp-29h] BYREF
  unsigned int v93; // [rsp+E0h] [rbp+5Fh]

  v10 = a1;
  v11 = a10;
  v12 = 0;
  v86 = 0;
  v13 = 0;
  v85 = 0;
  v88 = 0;
  *a8 = 0;
  v87 = 0;
  *a9 = 0;
  *a10 = 0;
  if ( (*(_BYTE *)(a6 + 160) & 1) != 0 )
  {
    v21 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, __int64 *, int *))g_pLsaIdProvHostFunctionTable
           + 4))(
            *(_QWORD *)(a6 + 16),
            *(_QWORD *)(a7 + 96),
            0,
            10,
            &v87,
            &v85);
    if ( v21 )
    {
      v29 = "";
      while ( 1 )
      {
        v45 = *(v29 - 1);
        v46 = v29--;
        v47 = v45 == 92;
        if ( v45 == 92 )
          break;
        if ( v29 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
        {
          v47 = v45 == 92;
          break;
        }
      }
      if ( v47 )
        v29 = v46;
      v38 = "LookUpUserInfo(LIIC_ProfileProperties)";
      v39 = 5001;
      goto LABEL_39;
    }
    v13 = (unsigned __int16 *)v87;
    v10 = a1;
  }
  v14 = -1;
  v15 = *(_QWORD *)(a5 + 40);
  if ( v15 )
  {
    v16 = -1;
    do
      v42 = *(_WORD *)(v15 + 2 * v16++ + 2) == 0;
    while ( !v42 );
    v17 = v16 + 1;
  }
  else
  {
    v17 = 0;
  }
  if ( v13 )
    v18 = v13[12] + v13[20] + v13[28] + v13[4] + 10;
  else
    v18 = 2;
  v19 = -1;
  do
    ++v19;
  while ( *(&g_awchComputerName + v19) );
  v20 = v18 + 2 * (v17 + v19);
  if ( v20 + 160 < v20 )
  {
    *a10 = -1;
    v29 = "";
    v21 = -1073741675;
    while ( 1 )
    {
      v40 = *(v29 - 1);
      v41 = v29--;
      v42 = v40 == 92;
      if ( v40 == 92 )
        break;
      if ( v29 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
      {
        v42 = v40 == 92;
        break;
      }
    }
    if ( v42 )
      v29 = v41;
    v38 = "RtlDWordAdd";
    v39 = 5021;
    goto LABEL_39;
  }
  *a10 = v20 + 160;
  v12 = ((__int64 (*)(void))g_pLsaFunctionTable->AllocateLsaHeap)();
  if ( !v12 )
  {
    v21 = -1073741801;
    v29 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    v39 = 5027;
    v38 = "AllocateLsaHeap";
    goto LABEL_40;
  }
  v21 = ((__int64 (__fastcall *)(__int64, _QWORD, __int64 *))g_pLsaFunctionTable->AllocateClientBuffer)(v10, *a10, &v88);
  if ( v21 )
  {
    v29 = "";
    while ( 1 )
    {
      v73 = *(v29 - 1);
      v74 = v29--;
      v75 = v73 == 92;
      if ( v73 == 92 )
        break;
      if ( v29 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
      {
        v75 = v73 == 92;
        break;
      }
    }
    if ( v75 )
      v29 = v74;
    v38 = "AllocateClientBuffer";
    v39 = 5036;
LABEL_39:
    v37 = 0;
    goto LABEL_40;
  }
  v22 = v88;
  v23 = v12 + 160;
  *(_DWORD *)v12 = 2;
  v24 = v22 - v12;
  *(union _LARGE_INTEGER *)(v12 + 8) = g_TimeNever;
  *(union _LARGE_INTEGER *)(v12 + 24) = g_TimeForever;
  *(union _LARGE_INTEGER *)(v12 + 32) = g_TimeNever;
  *(union _LARGE_INTEGER *)(v12 + 40) = g_TimeForever;
  *(union _LARGE_INTEGER *)(v12 + 16) = g_TimeForever;
  if ( (*(_DWORD *)(a6 + 160) & 0x40) == 0 || *(_QWORD *)(a5 + 104) == g_TimeNever.QuadPart )
  {
    *(union _LARGE_INTEGER *)(v12 + 48) = g_TimeForever;
  }
  else
  {
    *(_DWORD *)(v12 + 48) = *(_DWORD *)(a5 + 104);
    *(_DWORD *)(v12 + 52) = *(_DWORD *)(a5 + 108);
  }
  v25 = *(_WORD **)(a5 + 40);
  if ( v25 )
  {
    v48 = -1;
    do
      ++v48;
    while ( v25[v48] );
    v49 = 2LL * (unsigned int)v48;
    if ( v49 <= 0xFFFFFFFF )
    {
      v76 = (unsigned int)v49;
      memcpy_0((void *)(v12 + 160), v25, (unsigned int)v49);
      *(_WORD *)(v12 + 88) = v76;
      *(_QWORD *)(v12 + 96) = v23 + v24;
      v26 = v76 + 2;
      *(_WORD *)(v76 + v23) = 0;
      if ( (int)v76 + 2 >= (unsigned int)v76 )
      {
        *(_WORD *)(v12 + 90) = v26;
        goto LABEL_17;
      }
      v50 = "";
      do
      {
        v77 = *(v50 - 1);
        v78 = v50--;
      }
      while ( v77 != 92 && v50 > "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" );
      v42 = v77 == 92;
      v53 = "RtlDWordAdd";
      if ( v42 )
        v50 = v78;
      v54 = 4949;
    }
    else
    {
      v50 = "";
      do
      {
        v51 = *(v50 - 1);
        v52 = v50--;
      }
      while ( v51 != 92 && v50 > "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" );
      v42 = v51 == 92;
      v53 = "RtlDWordMult";
      if ( v42 )
        v50 = v52;
      v54 = 4939;
    }
    v21 = -1073741675;
    LODWORD(Src) = v54;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225621LL, v50, Src, v53, &Class);
    v29 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    v39 = 5078;
    v38 = "PutClientString";
    goto LABEL_40;
  }
  v26 = v86;
LABEL_17:
  v27 = -1;
  do
    ++v27;
  while ( *(&g_awchComputerName + v27) );
  v28 = 2LL * (unsigned int)v27;
  if ( v28 > 0xFFFFFFFF )
  {
    v29 = "";
    v30 = "";
    do
    {
      v31 = *(v30 - 1);
      v32 = v30--;
    }
    while ( v31 != 92 && v30 > "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" );
    v42 = v31 == 92;
    v33 = "RtlDWordMult";
    if ( v42 )
      v30 = v32;
    v34 = 4939;
LABEL_26:
    v21 = -1073741675;
    LODWORD(Src) = v34;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225621LL, v30, Src, v33, &Class);
    do
    {
      v35 = *(v29 - 1);
      v36 = v29--;
    }
    while ( v35 != 92 && v29 > "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" );
    v37 = 0;
    v42 = v35 == 92;
    v38 = "PutClientString";
    if ( v42 )
      v29 = v36;
    v39 = 5090;
    goto LABEL_40;
  }
  v55 = (char *)(v26 + v23);
  v56 = (unsigned int)v28;
  memcpy_0(v55, &g_awchComputerName, (unsigned int)v28);
  *(_WORD *)(v12 + 136) = v56;
  *(_QWORD *)(v12 + 144) = &v55[v24];
  *(_WORD *)&v55[v56] = 0;
  v57 = v56 + 2;
  if ( (int)v56 + 2 < (unsigned int)v56 )
  {
    v29 = "";
    v30 = "";
    do
    {
      v62 = *(v30 - 1);
      v63 = v30--;
    }
    while ( v62 != 92 && v30 > "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" );
    v42 = v62 == 92;
    v33 = "RtlDWordAdd";
    if ( v42 )
      v30 = v63;
    v34 = 4949;
    goto LABEL_26;
  }
  *(_WORD *)(v12 + 138) = v57;
  v58 = v87;
  v93 = v56 + 2;
  if ( v87 )
  {
    v59 = &v55[v57];
    if ( *(_WORD *)(v87 + 8) )
    {
      v21 = PutClientString<_UNICODE_STRING>(v59, *(void **)(v87 + 16));
      if ( v21 )
      {
        v29 = "";
        do
        {
          v82 = *(v29 - 1);
          v83 = v29--;
        }
        while ( v82 != 92 && v29 > "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" );
        v37 = 0;
        v42 = v82 == 92;
        v38 = "PutClientString";
        if ( v42 )
          v29 = v83;
        v39 = 5105;
        goto LABEL_40;
      }
      v58 = v87;
      v59 += v93;
    }
    if ( *(_WORD *)(v58 + 24) )
    {
      v21 = PutClientString<_UNICODE_STRING>(v59, *(void **)(v58 + 32));
      if ( v21 )
      {
        v29 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
        v39 = 5119;
        v38 = "PutClientString";
        goto LABEL_40;
      }
      v58 = v87;
      v59 += v93;
    }
    if ( !*(_WORD *)(v58 + 40) )
      goto LABEL_72;
    v21 = PutClientString<_UNICODE_STRING>(v59, *(void **)(v58 + 48));
    if ( !v21 )
    {
      v58 = v87;
      v59 += v93;
LABEL_72:
      v60 = 0;
      if ( !*(_WORD *)(v58 + 56) )
      {
LABEL_73:
        v11 = a10;
        goto LABEL_74;
      }
      v64 = *(_WORD **)(v58 + 64);
      if ( v64 )
      {
        do
          ++v14;
        while ( v64[v14] );
        v65 = 2LL * (unsigned int)v14;
        if ( v65 > 0xFFFFFFFF )
        {
          v29 = "";
          v66 = "";
          do
          {
            v67 = *(v66 - 1);
            v68 = v66--;
          }
          while ( v67 != 92 && v66 > "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" );
          v42 = v67 == 92;
          v69 = "RtlDWordMult";
          if ( v42 )
            v66 = v68;
          v70 = 4939;
LABEL_99:
          v21 = -1073741675;
          LODWORD(Src) = v70;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225621LL, v66, Src, v69, &Class);
          do
          {
            v71 = *(v29 - 1);
            v72 = v29--;
          }
          while ( v71 != 92 && v29 > "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" );
          v37 = 0;
          v42 = v71 == 92;
          v38 = "PutClientString";
          if ( v42 )
            v29 = v72;
          v39 = 5147;
          goto LABEL_40;
        }
        v79 = (unsigned int)v65;
        memcpy_0(v59, v64, (unsigned int)v65);
        *(_WORD *)(v12 + 120) = v79;
        *(_QWORD *)(v12 + 128) = &v59[v24];
        *(_WORD *)&v59[v79] = 0;
        v60 = v79 + 2;
        if ( (int)v79 + 2 < (unsigned int)v79 )
        {
          v29 = "";
          v66 = "";
          do
          {
            v80 = *(v66 - 1);
            v81 = v66--;
          }
          while ( v80 != 92 && v66 > "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" );
          v42 = v80 == 92;
          v69 = "RtlDWordAdd";
          if ( v42 )
            v66 = v81;
          v70 = 4949;
          goto LABEL_99;
        }
      }
      else
      {
        *(_QWORD *)(v12 + 128) = 0;
        *(_WORD *)(v12 + 120) = 0;
      }
      *(_WORD *)(v12 + 122) = v60;
      goto LABEL_73;
    }
    v29 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    v39 = 5133;
    v38 = "PutClientString";
LABEL_40:
    v43 = a1;
    goto LABEL_41;
  }
LABEL_74:
  if ( a3 )
    *(_DWORD *)(v12 + 152) = 4;
  if ( a2 )
    *(_DWORD *)(v12 + 152) |= 0x8000u;
  if ( a4 )
    *(_DWORD *)(v12 + 152) |= 0x20000u;
  v43 = a1;
  v21 = ((__int64 (__fastcall *)(__int64, _QWORD, __int64, __int64))g_pLsaFunctionTable->CopyToClientBuffer)(
          a1,
          *v11,
          v88,
          v12);
  if ( !v21 )
  {
    v61 = v88;
    v88 = 0;
    *a8 = v61;
    *a9 = v12;
    goto LABEL_45;
  }
  v29 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
  v38 = "CopyToClientBuffer";
  v39 = 5178;
LABEL_41:
  LODWORD(Src) = v39;
  WPPTraceLogA(v37, "0x%08x %s:%u : %s:%ws", v21, v29, Src, v38, &Class);
  if ( v88 )
    ((void (__fastcall *)(__int64))g_pLsaFunctionTable->FreeClientBuffer)(v43);
  if ( v12 )
    ((void (__fastcall *)(__int64))g_pLsaFunctionTable->FreeLsaHeap)(v12);
LABEL_45:
  if ( v87 )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  return v21;
}

```

## disassembly

```asm
0x18001d6c0  mov     rax, rsp
0x18001d6c3  mov     [rax+20h], r9b
0x18001d6c7  mov     [rax+18h], r8b
0x18001d6cb  mov     [rax+10h], dl
0x18001d6ce  mov     [rax+8], rcx
0x18001d6d2  push    rbp
0x18001d6d3  push    rdi
0x18001d6d4  lea     rbp, [rax-2Fh]
0x18001d6d8  sub     rsp, 98h
0x18001d6df  mov     [rax-18h], rbx
0x18001d6e3  mov     rdi, rcx
0x18001d6e6  mov     [rax-20h], rsi
0x18001d6ea  mov     rsi, [rbp+27h+arg_28]
0x18001d6ee  mov     [rax-28h], r12
0x18001d6f2  mov     [rax-30h], r13
0x18001d6f6  mov     [rax-38h], r14
0x18001d6fa  mov     r14, [rbp+27h+arg_48]
0x18001d6fe  mov     [rax-40h], r15
0x18001d702  xor     r15d, r15d
0x18001d705  mov     rax, [rbp+27h+arg_38]
0x18001d709  mov     r12d, r15d
0x18001d70c  mov     [rbp+27h+var_5C], r15d
0x18001d710  mov     r10d, r15d
0x18001d713  mov     [rbp+27h+var_60], r15d
0x18001d717  mov     [rbp+27h+var_50], r15
0x18001d71b  mov     [rax], r15
0x18001d71e  mov     rax, [rbp+27h+arg_40]
0x18001d722  mov     [rbp+27h+var_58], r15
0x18001d726  mov     [rax], r15
0x18001d729  mov     [r14], r15d
0x18001d72c  test    byte ptr [rsi+0A0h], 1
0x18001d733  jnz     loc_18001DA0F
0x18001d739  mov     rbx, [rbp+27h+arg_20]
0x18001d73d  mov     r13, 0FFFFFFFFFFFFFFFFh
0x18001d744  mov     rcx, [rbx+28h]
0x18001d748  test    rcx, rcx
0x18001d74b  jz      loc_18001DC34
0x18001d751  mov     rax, r13
0x18001d754  cmp     [rcx+rax*2+2], r12w
0x18001d75a  lea     rax, [rax+1]
0x18001d75e  jnz     short loc_18001D754
0x18001d760  lea     r8, [rax+1]
0x18001d764  test    r10, r10
0x18001d767  jz      loc_18001DA05
0x18001d76d  movzx   eax, word ptr [r10+28h]
0x18001d772  movzx   ecx, word ptr [r10+38h]
0x18001d777  movzx   edx, word ptr [r10+8]
0x18001d77c  add     ecx, eax
0x18001d77e  movzx   eax, word ptr [r10+18h]
0x18001d783  add     edx, 0Ah
0x18001d786  add     ecx, eax
0x18001d788  add     edx, ecx
0x18001d78a  lea     rcx, ?g_awchComputerName@@3PAGA; ushort near * g_awchComputerName
0x18001d791  mov     rax, r13
0x18001d794  inc     rax
0x18001d797  cmp     [rcx+rax*2], r12w
0x18001d79c  jnz     short loc_18001D794
0x18001d79e  add     eax, r8d
0x18001d7a1  lea     edx, [rdx+rax*2]
0x18001d7a4  lea     ecx, [rdx+0A0h]
0x18001d7aa  cmp     ecx, edx
0x18001d7ac  jb      loc_18001D930
0x18001d7b2  mov     [r14], ecx
0x18001d7b5  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18001d7bc  mov     rax, [rax+28h]
0x18001d7c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7c5  mov     r12, rax
0x18001d7c8  test    rax, rax
0x18001d7cb  jz      loc_18001DEF5
0x18001d7d1  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18001d7d8  lea     r8, [rbp+27h+var_50]
0x18001d7dc  mov     edx, [r14]
0x18001d7df  mov     rcx, rdi
0x18001d7e2  mov     rax, [rax+38h]
0x18001d7e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7eb  mov     edi, eax
0x18001d7ed  test    eax, eax
0x18001d7ef  jnz     loc_18001DD47
0x18001d7f5  mov     r15, [rbp+27h+var_50]
0x18001d7f9  lea     rdi, [r12+0A0h]
0x18001d801  mov     dword ptr [r12], 2
0x18001d809  sub     r15, r12
0x18001d80c  mov     rax, cs:?g_TimeNever@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER g_TimeNever
0x18001d813  mov     [r12+8], rax
0x18001d818  mov     rax, cs:?g_TimeForever@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER g_TimeForever
0x18001d81f  mov     [r12+18h], rax
0x18001d824  mov     rax, cs:?g_TimeNever@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER g_TimeNever
0x18001d82b  mov     [r12+20h], rax
0x18001d830  mov     rax, cs:?g_TimeForever@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER g_TimeForever
0x18001d837  mov     [r12+28h], rax
0x18001d83c  mov     rax, cs:?g_TimeForever@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER g_TimeForever
0x18001d843  mov     [r12+10h], rax
0x18001d848  mov     eax, [rsi+0A0h]
0x18001d84e  test    al, 40h
0x18001d850  jnz     loc_18001DDB3
0x18001d856  mov     rax, cs:?g_TimeForever@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER g_TimeForever
0x18001d85d  mov     [r12+30h], rax
0x18001d862  mov     rdx, [rbx+28h]; Src
0x18001d866  mov     esi, 0FFFFFFFFh
0x18001d86b  test    rdx, rdx
0x18001d86e  jnz     loc_18001DA88
0x18001d874  mov     edx, [rbp+27h+var_5C]
0x18001d877  mov     rax, r13
0x18001d87a  lea     r9, ?g_awchComputerName@@3PAGA; ushort near * g_awchComputerName
0x18001d881  inc     rax
0x18001d884  cmp     word ptr [r9+rax*2], 0
0x18001d88a  jnz     short loc_18001D881
0x18001d88c  mov     ecx, eax
0x18001d88e  add     rcx, rcx
0x18001d891  cmp     rcx, rsi
0x18001d894  jbe     loc_18001DB32
0x18001d89a  lea     rbx, aOnecoreDsExtCl_6+27h; ""
0x18001d8a1  mov     r9, rbx
0x18001d8a4  lea     rsi, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18001d8ab  movzx   eax, byte ptr [r9-1]
0x18001d8b0  mov     rcx, r9
0x18001d8b3  dec     r9
0x18001d8b6  cmp     al, 5Ch ; '\'
0x18001d8b8  jz      short loc_18001D8BF
0x18001d8ba  cmp     r9, rsi
0x18001d8bd  ja      short loc_18001D8AB
0x18001d8bf  xor     r10d, r10d
0x18001d8c2  cmp     al, 5Ch ; '\'
0x18001d8c4  lea     rax, aRtldwordmult; "RtlDWordMult"
0x18001d8cb  cmovz   r9, rcx
0x18001d8cf  mov     ecx, 134Bh
0x18001d8d4  lea     r15, Class
0x18001d8db  mov     edi, 0C0000095h
0x18001d8e0  mov     [rsp+30h], r15
0x18001d8e5  lea     r14, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18001d8ec  mov     [rsp+0A0h+var_78], rax
0x18001d8f1  mov     r11, r15
0x18001d8f4  mov     dword ptr [rsp+0A0h+Src], ecx
0x18001d8f8  mov     r8d, edi
0x18001d8fb  mov     rcx, r10
0x18001d8fe  mov     rdx, r14
0x18001d901  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18001d906  movzx   eax, byte ptr [rbx-1]
0x18001d90a  mov     rcx, rbx
0x18001d90d  dec     rbx
0x18001d910  cmp     al, 5Ch ; '\'
0x18001d912  jz      short loc_18001D919
0x18001d914  cmp     rbx, rsi
0x18001d917  ja      short loc_18001D906
0x18001d919  xor     r10d, r10d
0x18001d91c  cmp     al, 5Ch ; '\'
0x18001d91e  lea     rax, aPutclientstrin_1; "PutClientString"
0x18001d925  cmovz   rbx, rcx
0x18001d929  mov     ecx, 13E2h
0x18001d92e  jmp     short loc_18001D980
0x18001d930  mov     dword ptr [r14], 0FFFFFFFFh
0x18001d937  lea     rbx, aOnecoreDsExtCl_6+27h; ""
0x18001d93e  mov     edi, 0C0000095h
0x18001d943  lea     rsi, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18001d94a  movzx   eax, byte ptr [rbx-1]
0x18001d94e  mov     rcx, rbx
0x18001d951  dec     rbx
0x18001d954  cmp     al, 5Ch ; '\'
0x18001d956  jz      short loc_18001D95F
0x18001d958  cmp     rbx, rsi
0x18001d95b  ja      short loc_18001D94A
0x18001d95d  cmp     al, 5Ch ; '\'
0x18001d95f  cmovz   rbx, rcx
0x18001d963  lea     rax, aRtldwordadd; "RtlDWordAdd"
0x18001d96a  mov     ecx, 139Dh
0x18001d96f  mov     r10, r15
0x18001d972  lea     r14, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18001d979  lea     r15, Class
0x18001d980  mov     r13, [rbp+27h+arg_0]
0x18001d984  mov     [rsp+30h], r15
0x18001d989  mov     r9, rbx
0x18001d98c  mov     [rsp+0A0h+var_78], rax
0x18001d991  mov     r8d, edi
0x18001d994  mov     dword ptr [rsp+0A0h+Src], ecx
0x18001d998  mov     rdx, r14
0x18001d99b  mov     rcx, r10
0x18001d99e  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18001d9a3  mov     rdx, [rbp+27h+var_50]
0x18001d9a7  test    rdx, rdx
0x18001d9aa  jnz     loc_18001E040
0x18001d9b0  test    r12, r12
0x18001d9b3  jnz     loc_18001E058
0x18001d9b9  mov     rcx, [rbp+27h+var_58]
0x18001d9bd  mov     r15, [rsp+0A0h+var_38]
0x18001d9c2  mov     r14, [rsp+0A0h+var_30]
0x18001d9c7  mov     r13, [rsp+0A0h+var_28]
0x18001d9cc  mov     r12, [rsp+0A0h+var_20]
0x18001d9d4  mov     rsi, [rsp+0A0h+var_18]
0x18001d9dc  mov     rbx, [rsp+90h]
0x18001d9e4  test    rcx, rcx
0x18001d9e7  jz      short loc_18001D9F9
0x18001d9e9  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18001d9f0  mov     rax, [rax+30h]
0x18001d9f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d9f9  mov     eax, edi
0x18001d9fb  add     rsp, 98h
0x18001da02  pop     rdi
0x18001da03  pop     rbp
0x18001da04  retn
0x18001da05  mov     edx, 2
0x18001da0a  jmp     loc_18001D78A
0x18001da0f  mov     rax, cs:?g_pLsaIdProvHostFunctionTable@@3PEAU_LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE@@EA; _LSA_IDENTITY_PROVIDER_HOST_FUNCTION_TABLE * g_pLsaIdProvHostFunctionTable
0x18001da16  lea     rcx, [rbp+27h+var_60]
0x18001da1a  mov     rdx, [rbp+27h+arg_30]
0x18001da1e  mov     r9d, 0Ah
0x18001da24  mov     [rsp+0A0h+var_78], rcx
0x18001da29  xor     r8d, r8d
0x18001da2c  lea     rcx, [rbp+27h+var_58]
0x18001da30  mov     rax, [rax+20h]
0x18001da34  mov     rdx, [rdx+60h]
0x18001da38  mov     [rsp+0A0h+Src], rcx
0x18001da3d  mov     rcx, [rsi+10h]
0x18001da41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da46  mov     edi, eax
0x18001da48  test    eax, eax
0x18001da4a  jz      loc_18001DC3C
0x18001da50  lea     rbx, aOnecoreDsExtCl_6+27h; ""
0x18001da57  lea     rsi, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18001da5e  movzx   eax, byte ptr [rbx-1]
0x18001da62  mov     rcx, rbx
0x18001da65  dec     rbx
0x18001da68  cmp     al, 5Ch ; '\'
0x18001da6a  jz      short loc_18001DA73
0x18001da6c  cmp     rbx, rsi
0x18001da6f  ja      short loc_18001DA5E
0x18001da71  cmp     al, 5Ch ; '\'
0x18001da73  cmovz   rbx, rcx
0x18001da77  lea     rax, aLookupuserinfo_0; "LookUpUserInfo(LIIC_ProfileProperties)"
0x18001da7e  mov     ecx, 1389h
0x18001da83  jmp     loc_18001D96F
0x18001da88  mov     rax, r13
0x18001da8b  nop     dword ptr [rax+rax+00h]
0x18001da90  inc     rax
0x18001da93  cmp     word ptr [rdx+rax*2], 0
0x18001da98  jnz     short loc_18001DA90
0x18001da9a  mov     ecx, eax
0x18001da9c  add     rcx, rcx
0x18001da9f  cmp     rcx, rsi
0x18001daa2  jbe     loc_18001DD7F
0x18001daa8  lea     rbx, aOnecoreDsExtCl_6+27h; ""
0x18001daaf  lea     rsi, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18001dab6  movzx   eax, byte ptr [rbx-1]
0x18001daba  mov     rcx, rbx
0x18001dabd  dec     rbx
0x18001dac0  cmp     al, 5Ch ; '\'
0x18001dac2  jz      short loc_18001DAC9
0x18001dac4  cmp     rbx, rsi
0x18001dac7  ja      short loc_18001DAB6
0x18001dac9  xor     r10d, r10d
0x18001dacc  cmp     al, 5Ch ; '\'
0x18001dace  lea     rax, aRtldwordmult; "RtlDWordMult"
0x18001dad5  cmovz   rbx, rcx
0x18001dad9  mov     ecx, 134Bh
0x18001dade  lea     r15, Class
0x18001dae5  mov     edi, 0C0000095h
0x18001daea  mov     [rsp+30h], r15
0x18001daef  lea     r14, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18001daf6  mov     [rsp+0A0h+var_78], rax
0x18001dafb  mov     r9, r15
0x18001dafe  mov     dword ptr [rsp+0A0h+Src], ecx
0x18001db02  mov     r8d, edi
0x18001db05  mov     rcx, r10
0x18001db08  mov     rdx, r14
0x18001db0b  mov     r9, rbx
0x18001db0e  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18001db13  xor     r10d, r10d
0x18001db16  mov     rcx, rsi; char *
0x18001db19  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001db1e  mov     rbx, rax
0x18001db21  mov     ecx, 13D6h
0x18001db26  lea     rax, aPutclientstrin_1; "PutClientString"
0x18001db2d  jmp     loc_18001D980
0x18001db32  mov     eax, edx
0x18001db34  mov     rdx, r9; Src
0x18001db37  add     rdi, rax
0x18001db3a  mov     ebx, ecx
0x18001db3c  mov     r8d, ecx; Size
0x18001db3f  mov     rcx, rdi; void *
0x18001db42  call    memcpy_0
0x18001db47  lea     rax, [rdi+r15]
0x18001db4b  mov     [r12+88h], bx
0x18001db54  mov     [r12+90h], rax
0x18001db5c  xor     eax, eax
0x18001db5e  mov     [rbx+rdi], ax
0x18001db62  lea     eax, [rbx+2]
0x18001db65  cmp     eax, ebx
0x18001db67  jb      loc_18001DC49
0x18001db6d  mov     [r12+8Ah], ax
0x18001db76  mov     rcx, [rbp+27h+var_58]
0x18001db7a  mov     dword ptr [rbp+27h+arg_28], eax
0x18001db7d  test    rcx, rcx
0x18001db80  jz      short loc_18001DBBC
0x18001db82  mov     r14d, eax
0x18001db85  xor     eax, eax
0x18001db87  add     r14, rdi
0x18001db8a  cmp     ax, [rcx+8]
0x18001db8e  jnz     loc_18001DE97
0x18001db94  xor     eax, eax
0x18001db96  cmp     ax, [rcx+18h]
0x18001db9a  jnz     loc_18001DF46
  ... truncated ...
```
