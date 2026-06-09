# CSearchQueryMapping::RemoveDuplicateDerivedFroms(CMFBaseStringT<ushort> *)

- ea: `0x18002ae60`
- end: `0x18002b54a`
- name: `?RemoveDuplicateDerivedFroms@CSearchQueryMapping@@KAJPEAV?$CMFBaseStringT@G@@@Z`
- size: `1770`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x1800290b4`

## callees

- `0x18000d9bc`
- `0x180011930`
- `0x1800125c4`
- `0x1800198d4`
- `0x18001bbe0`
- `0x18001bfc0`
- `0x18001c648`
- `0x18001d41c`
- `0x180028e90`
- `0x180028fb8`
- `0x18002ae60`
- `0x18002b550`
- `0x18002b5d8`
- `0x1800333e8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x18002af0d`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x18002af51`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x18002af95`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x18002afd9`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x18002b01d`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x18002b05d`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x18002af0d`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x18002af51`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x18002af95`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x18002afd9`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x18002b01d`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x18002b05d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002b1a1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002b1ee`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002b23c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002b280`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002b2ac`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002b2d8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002b1a1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002b1ee`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002b23c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002b280`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002b2ac`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002b2d8`

## pseudocode

```c
__int64 __fastcall CSearchQueryMapping::RemoveDuplicateDerivedFroms(__int64 a1, __int64 a2)
{
  __int64 v3; // rax
  __int64 v4; // r10
  int v5; // edi
  __int64 v6; // r8
  int v7; // r14d
  const WCHAR *v8; // rax
  int v9; // r8d
  __int64 v10; // rdx
  __int64 i; // r8
  int StringOrdinal; // r15d
  __int64 v13; // r8
  const WCHAR *v14; // rax
  int v15; // r8d
  __int64 v16; // rdx
  __int64 v17; // r8
  const WCHAR *v18; // rax
  int v19; // r8d
  __int64 v20; // rdx
  __int64 v21; // r8
  const WCHAR *v22; // rax
  int v23; // r8d
  __int64 v24; // rdx
  __int64 v25; // r8
  const WCHAR *v26; // rax
  int v27; // r8d
  __int64 v28; // rdx
  __int64 v29; // r8
  const WCHAR *v30; // rax
  int v31; // r8d
  int v32; // eax
  bool v33; // r13
  __int64 v34; // r12
  __int64 v35; // rdx
  __int64 v36; // r8
  const WCHAR *v37; // rsi
  const WCHAR *v38; // rax
  int v39; // r10d
  unsigned int v40; // edx
  unsigned int *v41; // rcx
  unsigned int *v42; // rcx
  unsigned int v43; // edx
  char v44; // r9
  unsigned int v45; // edx
  __int64 v46; // rdx
  bool v47; // zf
  char v48; // al
  char v49; // cl
  __int64 v50; // rax
  unsigned int v51; // esi
  __int64 v52; // rdi
  __int64 v53; // rdx
  __int64 v54; // rax
  __int64 v55; // r10
  bool v57; // [rsp+30h] [rbp-D0h]
  int v58[2]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v59[32]; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v60[100]; // [rsp+60h] [rbp-A0h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v3 = ((__int64 (*)(void))CMFBaseStringT<unsigned short>::PContents)();
    WPP_SF_S(*(_QWORD *)(v4 + 16), 10, &WPP_fa24657623f63b15ff5f99f822d0c274_Traceguids, v3);
  }
  v5 = 0;
  v6 = 0;
  v7 = 1;
  if ( *(int *)(a1 + 4) >= 0 )
    v6 = *(unsigned int *)(a1 + 8);
  v8 = (const WCHAR *)CMFBaseStringT<unsigned short>::PContents(a1, a2, v6);
  StringOrdinal = FindStringOrdinal(
                    0x200000u,
                    v8,
                    v9,
                    L"and (upnp:class derivedfrom \"object.item.imageItem\" or upnp:class derivedfrom \"object.item.audioItem\"))",
                    103,
                    1);
  if ( StringOrdinal == -1 )
  {
    v7 = 2;
    v13 = 0;
    if ( *(int *)(a1 + 4) >= 0 )
      v13 = *(unsigned int *)(a1 + 8);
    v14 = (const WCHAR *)CMFBaseStringT<unsigned short>::PContents(a1, v10, v13);
    StringOrdinal = FindStringOrdinal(
                      0x200000u,
                      v14,
                      v15,
                      L"and (upnp:class derivedfrom \"object.item.imageItem\" or upnp:class derivedfrom \"object.item.vide"
                       "oItem\" or upnp:class derivedfrom \"object.item.videoItem.videoBroadcast\"))",
                      168,
                      1);
    if ( StringOrdinal == -1 )
    {
      v7 = 3;
      v17 = 0;
      if ( *(int *)(a1 + 4) >= 0 )
        v17 = *(unsigned int *)(a1 + 8);
      v18 = (const WCHAR *)CMFBaseStringT<unsigned short>::PContents(a1, v16, v17);
      StringOrdinal = FindStringOrdinal(
                        0x200000u,
                        v18,
                        v19,
                        L"and (upnp:class derivedfrom \"object.item.audioItem\" or upnp:class derivedfrom \"object.item.vi"
                         "deoItem\" or upnp:class derivedfrom \"object.item.videoItem.videoBroadcast\"))",
                        168,
                        1);
      if ( StringOrdinal == -1 )
      {
        v7 = 4;
        v21 = 0;
        if ( *(int *)(a1 + 4) >= 0 )
          v21 = *(unsigned int *)(a1 + 8);
        v22 = (const WCHAR *)CMFBaseStringT<unsigned short>::PContents(a1, v20, v21);
        StringOrdinal = FindStringOrdinal(
                          0x200000u,
                          v22,
                          v23,
                          L"and upnp:class derivedfrom \"object.item.imageItem\")",
                          51,
                          1);
        if ( StringOrdinal == -1 )
        {
          v7 = 5;
          v25 = 0;
          if ( *(int *)(a1 + 4) >= 0 )
            v25 = *(unsigned int *)(a1 + 8);
          v26 = (const WCHAR *)CMFBaseStringT<unsigned short>::PContents(a1, v24, v25);
          StringOrdinal = FindStringOrdinal(
                            0x200000u,
                            v26,
                            v27,
                            L"and (upnp:class derivedfrom \"object.item.videoItem\" or upnp:class derivedfrom \"object.ite"
                             "m.videoItem.videoBroadcast\"))",
                            118,
                            1);
          if ( StringOrdinal == -1 )
          {
            v7 = 6;
            v29 = 0;
            if ( *(int *)(a1 + 4) >= 0 )
              v29 = *(unsigned int *)(a1 + 8);
            v30 = (const WCHAR *)CMFBaseStringT<unsigned short>::PContents(a1, v28, v29);
            StringOrdinal = FindStringOrdinal(
                              0x200000u,
                              v30,
                              v31,
                              L"and upnp:class derivedfrom \"object.item.audioItem\")",
                              51,
                              1);
            if ( StringOrdinal == -1 )
            {
              v7 = 0;
              StringOrdinal = 0;
              if ( *(int *)(a1 + 4) < 0 )
              {
LABEL_26:
                v32 = 0;
                goto LABEL_28;
              }
              StringOrdinal = *(_DWORD *)(a1 + 8);
            }
          }
        }
      }
    }
  }
  if ( *(int *)(a1 + 4) < 0 )
    goto LABEL_26;
  v32 = *(_DWORD *)(a1 + 8);
LABEL_28:
  if ( StringOrdinal >= v32 )
    goto LABEL_111;
  v57 = 0;
  v33 = 0;
  LODWORD(v34) = 0;
  memset_0(v60, 0, sizeof(v60));
  v37 = (const WCHAR *)CMFBaseStringT<unsigned short>::PContents(a1, v35, v36);
  v38 = &v37[StringOrdinal];
  *(_QWORD *)v58 = v38;
  while ( 1 )
  {
    v39 = -2147024809;
    if ( v37 >= v38 )
      break;
    if ( *v37 == 34 )
    {
      if ( !v57 )
        v33 = !v33;
    }
    else if ( *v37 == 39 )
    {
      if ( !v33 )
        v57 = !v57;
    }
    else if ( !v57 && !v33 )
    {
      if ( *v37 == 40 )
      {
        v34 = (unsigned int)(v34 + 1);
        if ( (_DWORD)v34 == 100 )
        {
          v44 = 1;
          goto LABEL_70;
        }
        v60[v34] = 0;
        goto LABEL_65;
      }
      if ( *v37 == 41 )
      {
        v40 = v60[(unsigned int)v34] & 0xF0;
        if ( (v60[(unsigned int)v34] & 2) == 0 )
          v40 = 240;
        if ( !v40 || !(_DWORD)v34 )
        {
          v44 = 0;
          v5 = -2147024809;
          goto LABEL_70;
        }
        LODWORD(v34) = v34 - 1;
        CSearchQueryMapping::SetConditionFlags(&v60[(unsigned int)v34], v40);
        goto LABEL_65;
      }
      if ( CompareStringOrdinal(v37, 3, L"and", 3, 1) == 2 )
      {
        v41 = &v60[(unsigned int)v34];
        *v41 &= ~1u;
        if ( (*(_BYTE *)v41 & 2) == 0 )
          CSearchQueryMapping::SetConditionFlags(v41, 0xF0u);
        v37 += 3;
      }
      else if ( CompareStringOrdinal(v37, 2, L"or", 2, 1) == 2 )
      {
        v42 = &v60[(unsigned int)v34];
        *v42 |= 1u;
        if ( (*(_BYTE *)v42 & 2) == 0 )
          CSearchQueryMapping::SetConditionFlags(v42, 0xF0u);
        v37 += 2;
      }
      else
      {
        if ( CompareStringOrdinal(v37, 46, L"upnp:class derivedfrom \"object.item.imageItem\"", 46, 1) == 2 )
        {
          v43 = 16;
        }
        else if ( CompareStringOrdinal(v37, 46, L"upnp:class derivedfrom \"object.item.audioItem\"", 46, 1) == 2 )
        {
          v43 = 32;
        }
        else
        {
          if ( CompareStringOrdinal(v37, 46, L"upnp:class derivedfrom \"object.item.videoItem\"", 46, 1) != 2 )
          {
            if ( CompareStringOrdinal(
                   v37,
                   61,
                   L"upnp:class derivedfrom \"object.item.videoItem.videoBroadcast\"",
                   61,
                   1) == 2 )
            {
              CSearchQueryMapping::SetConditionFlags(&v60[(unsigned int)v34], 0x80u);
              v37 += 60;
            }
            goto LABEL_65;
          }
          v43 = 64;
        }
        CSearchQueryMapping::SetConditionFlags(&v60[(unsigned int)v34], v43);
        v37 += 45;
      }
LABEL_65:
      v38 = *(const WCHAR **)v58;
    }
    ++v37;
  }
  v44 = 0;
LABEL_70:
  if ( v5 >= 0 )
  {
    for ( i = (unsigned int)v34; (_DWORD)i; CSearchQueryMapping::SetConditionFlags(&v60[(unsigned int)(i - 1)], v45) )
    {
      v45 = v60[(unsigned int)i] & 0xF0;
      if ( (v60[(unsigned int)i] & 2) == 0 )
        v45 = 240;
      if ( !v45 )
      {
        v5 = v39;
        break;
      }
    }
  }
  if ( !v7 )
  {
LABEL_89:
    v46 = 1;
    v48 = 0;
    goto LABEL_90;
  }
  v46 = 0;
  if ( v7 != 3 )
  {
    if ( v7 != 2 || (v60[0] & 0x20) != 0 )
      goto LABEL_84;
    goto LABEL_89;
  }
  if ( (v60[0] & 0x10) == 0 )
    goto LABEL_89;
LABEL_84:
  if ( v7 == 1 )
  {
    v47 = (v60[0] & 0xC0) == 0;
LABEL_88:
    if ( v47 )
      goto LABEL_89;
  }
  else if ( v7 == 4 )
  {
    v47 = (v60[0] & 0xE0) == 0;
    goto LABEL_88;
  }
  if ( v7 == 5 && (v60[0] & 0x30) == 0 )
  {
    v48 = 1;
    goto LABEL_90;
  }
  v48 = 0;
  if ( v7 != 6 || (v60[0] & 0xD0) != 0 )
LABEL_90:
    v49 = 0;
  else
    v49 = 1;
  if ( !v44 && v5 >= 0 && (unsigned __int8)v49 | (unsigned __int8)(v46 | v48) )
  {
    v50 = CMFBaseStringT<unsigned short>::PContents(a1, v46, (unsigned int)(StringOrdinal - 1));
    CMFBaseStringT<unsigned short>::CMFBaseStringT<unsigned short>(v59, v50);
    *(_QWORD *)(a1 + 4) = 0;
    v51 = 0;
    v5 = CMFBaseStringT<unsigned short>::Append(a1, v59);
    if ( v5 >= 0 )
    {
      while ( 1 )
      {
        if ( v51 >= (unsigned int)v34 )
          goto LABEL_110;
        v58[0] = -1;
        if ( (int)UIntPtrToLong(1u, v58) < 0 )
          goto LABEL_108;
        v5 = *(_DWORD *)(a1 + 4);
        if ( v5 >= 0 )
          break;
LABEL_109:
        ++v51;
        if ( v5 < 0 )
          goto LABEL_110;
      }
      v52 = v58[0];
      if ( v58[0] <= 0x4000000u )
      {
        if ( (int)CMFBaseStringT<unsigned short>::_EnsureSpace(a1, (unsigned int)(v58[0] + *(_DWORD *)(a1 + 8))) >= 0 )
        {
          memcpy_0((void *)(*(_QWORD *)(a1 + 16) + 2LL * *(int *)(a1 + 8)), L")", 2 * v52);
          CMFBaseStringT<unsigned short>::ReleaseBuffer(a1, (unsigned int)(v52 + *(_DWORD *)(a1 + 8)));
          v5 = 0;
        }
        else
        {
          v5 = *(_DWORD *)(a1 + 4);
        }
        goto LABEL_109;
      }
LABEL_108:
      v5 = -2147024785;
      *(_DWORD *)(a1 + 4) = -2147024785;
      goto LABEL_109;
    }
LABEL_110:
    CMFBaseStringT<unsigned short>::~CMFBaseStringT<unsigned short>(v59);
  }
LABEL_111:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v53 = ((v5 >> 31) & 0xFFFFFFFD) + 5;
    if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= (unsigned int)v53 )
    {
      v54 = CMFBaseStringT<unsigned short>::PContents(a1, v53, i);
      WPP_SF_dS(*(_QWORD *)(v55 + 16), 11, (unsigned int)&WPP_fa24657623f63b15ff5f99f822d0c274_Traceguids, v5, v54);
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002ae60  push    rbp
0x18002ae62  push    rbx
0x18002ae63  push    rsi
0x18002ae64  push    rdi
0x18002ae65  push    r12
0x18002ae67  push    r13
0x18002ae69  push    r14
0x18002ae6b  push    r15
0x18002ae6d  lea     rbp, [rsp-108h]
0x18002ae75  sub     rsp, 208h
0x18002ae7c  mov     rax, cs:__security_cookie
0x18002ae83  xor     rax, rsp
0x18002ae86  mov     [rbp+140h+var_50], rax
0x18002ae8d  mov     rbx, rcx
0x18002ae90  mov     r10, cs:WPP_GLOBAL_Control
0x18002ae97  lea     rax, WPP_GLOBAL_Control
0x18002ae9e  cmp     r10, rax
0x18002aea1  jz      short loc_18002AECE
0x18002aea3  test    byte ptr [r10+1Ch], 2
0x18002aea8  jz      short loc_18002AECE
0x18002aeaa  cmp     byte ptr [r10+19h], 5
0x18002aeaf  jb      short loc_18002AECE
0x18002aeb1  call    ?PContents@?$CMFBaseStringT@G@@QEBAPEBGXZ; CMFBaseStringT<ushort>::PContents(void)
0x18002aeb6  mov     rcx, [r10+10h]
0x18002aeba  lea     r8, WPP_fa24657623f63b15ff5f99f822d0c274_Traceguids
0x18002aec1  mov     r9, rax
0x18002aec4  mov     edx, 0Ah
0x18002aec9  call    WPP_SF_S
0x18002aece  xor     esi, esi
0x18002aed0  mov     edi, esi
0x18002aed2  mov     r8d, esi
0x18002aed5  lea     r12d, [rsi+1]
0x18002aed9  mov     r14d, r12d
0x18002aedc  cmp     [rbx+4], esi
0x18002aedf  jl      short loc_18002AEE5
0x18002aee1  mov     r8d, [rbx+8]
0x18002aee5  mov     rcx, rbx
0x18002aee8  call    ?PContents@?$CMFBaseStringT@G@@QEBAPEBGXZ; CMFBaseStringT<ushort>::PContents(void)
0x18002aeed  mov     r13d, 200000h
0x18002aef3  mov     [rsp+240h+bIgnoreCase], r12d; bIgnoreCase
0x18002aef8  mov     ecx, r13d; dwFindStringOrdinalFlags
0x18002aefb  mov     [rsp+240h+cchValue], 67h ; 'g'; cchValue
0x18002af03  lea     r9, StringValue; "and (upnp:class derivedfrom \"object.it"...
0x18002af0a  mov     rdx, rax; lpStringSource
0x18002af0d  call    cs:__imp_FindStringOrdinal
0x18002af13  mov     r15d, eax
0x18002af16  cmp     eax, 0FFFFFFFFh
0x18002af19  jnz     loc_18002B07A
0x18002af1f  lea     r14d, [rax+3]
0x18002af23  mov     r8d, esi
0x18002af26  cmp     [rbx+4], esi
0x18002af29  jl      short loc_18002AF2F
0x18002af2b  mov     r8d, [rbx+8]
0x18002af2f  mov     rcx, rbx
0x18002af32  call    ?PContents@?$CMFBaseStringT@G@@QEBAPEBGXZ; CMFBaseStringT<ushort>::PContents(void)
0x18002af37  mov     rdx, rax; lpStringSource
0x18002af3a  mov     [rsp+240h+bIgnoreCase], r12d; bIgnoreCase
0x18002af3f  lea     r9, aAndUpnpClassDe_4; "and (upnp:class derivedfrom \"object.it"...
0x18002af46  mov     [rsp+240h+cchValue], 0A8h; cchValue
0x18002af4e  mov     ecx, r13d; dwFindStringOrdinalFlags
0x18002af51  call    cs:__imp_FindStringOrdinal
0x18002af57  mov     r15d, eax
0x18002af5a  cmp     eax, 0FFFFFFFFh
0x18002af5d  jnz     loc_18002B07A
0x18002af63  lea     r14d, [rax+4]
0x18002af67  mov     r8d, esi
0x18002af6a  cmp     [rbx+4], esi
0x18002af6d  jl      short loc_18002AF73
0x18002af6f  mov     r8d, [rbx+8]
0x18002af73  mov     rcx, rbx
0x18002af76  call    ?PContents@?$CMFBaseStringT@G@@QEBAPEBGXZ; CMFBaseStringT<ushort>::PContents(void)
0x18002af7b  mov     rdx, rax; lpStringSource
0x18002af7e  mov     [rsp+240h+bIgnoreCase], r12d; bIgnoreCase
0x18002af83  lea     r9, aAndUpnpClassDe_3; "and (upnp:class derivedfrom \"object.it"...
0x18002af8a  mov     [rsp+240h+cchValue], 0A8h; cchValue
0x18002af92  mov     ecx, r13d; dwFindStringOrdinalFlags
0x18002af95  call    cs:__imp_FindStringOrdinal
0x18002af9b  mov     r15d, eax
0x18002af9e  cmp     eax, 0FFFFFFFFh
0x18002afa1  jnz     loc_18002B07A
0x18002afa7  lea     r14d, [rax+5]
0x18002afab  mov     r8d, esi
0x18002afae  cmp     [rbx+4], esi
0x18002afb1  jl      short loc_18002AFB7
0x18002afb3  mov     r8d, [rbx+8]
0x18002afb7  mov     rcx, rbx
0x18002afba  call    ?PContents@?$CMFBaseStringT@G@@QEBAPEBGXZ; CMFBaseStringT<ushort>::PContents(void)
0x18002afbf  mov     rdx, rax; lpStringSource
0x18002afc2  mov     [rsp+240h+bIgnoreCase], r12d; bIgnoreCase
0x18002afc7  lea     r9, aAndUpnpClassDe_1; "and upnp:class derivedfrom \"object.ite"...
0x18002afce  mov     [rsp+240h+cchValue], 33h ; '3'; cchValue
0x18002afd6  mov     ecx, r13d; dwFindStringOrdinalFlags
0x18002afd9  call    cs:__imp_FindStringOrdinal
0x18002afdf  mov     r15d, eax
0x18002afe2  cmp     eax, 0FFFFFFFFh
0x18002afe5  jnz     loc_18002B07A
0x18002afeb  lea     r14d, [rax+6]
0x18002afef  mov     r8d, esi
0x18002aff2  cmp     [rbx+4], esi
0x18002aff5  jl      short loc_18002AFFB
0x18002aff7  mov     r8d, [rbx+8]
0x18002affb  mov     rcx, rbx
0x18002affe  call    ?PContents@?$CMFBaseStringT@G@@QEBAPEBGXZ; CMFBaseStringT<ushort>::PContents(void)
0x18002b003  mov     rdx, rax; lpStringSource
0x18002b006  mov     [rsp+240h+bIgnoreCase], r12d; bIgnoreCase
0x18002b00b  lea     r9, aAndUpnpClassDe_0; "and (upnp:class derivedfrom \"object.it"...
0x18002b012  mov     [rsp+240h+cchValue], 76h ; 'v'; cchValue
0x18002b01a  mov     ecx, r13d; dwFindStringOrdinalFlags
0x18002b01d  call    cs:__imp_FindStringOrdinal
0x18002b023  mov     r15d, eax
0x18002b026  cmp     eax, 0FFFFFFFFh
0x18002b029  jnz     short loc_18002B07A
0x18002b02b  lea     r14d, [rax+7]
0x18002b02f  mov     r8d, esi
0x18002b032  cmp     [rbx+4], esi
0x18002b035  jl      short loc_18002B03B
0x18002b037  mov     r8d, [rbx+8]
0x18002b03b  mov     rcx, rbx
0x18002b03e  call    ?PContents@?$CMFBaseStringT@G@@QEBAPEBGXZ; CMFBaseStringT<ushort>::PContents(void)
0x18002b043  mov     rdx, rax; lpStringSource
0x18002b046  mov     [rsp+240h+bIgnoreCase], r12d; bIgnoreCase
0x18002b04b  lea     r9, aAndUpnpClassDe_2; "and upnp:class derivedfrom \"object.ite"...
0x18002b052  mov     [rsp+240h+cchValue], 33h ; '3'; cchValue
0x18002b05a  mov     ecx, r13d; dwFindStringOrdinalFlags
0x18002b05d  call    cs:__imp_FindStringOrdinal
0x18002b063  mov     r15d, eax
0x18002b066  cmp     eax, 0FFFFFFFFh
0x18002b069  jnz     short loc_18002B07A
0x18002b06b  mov     r14d, esi
0x18002b06e  mov     r15d, esi
0x18002b071  cmp     [rbx+4], esi
0x18002b074  jl      short loc_18002B07F
0x18002b076  mov     r15d, [rbx+8]
0x18002b07a  cmp     [rbx+4], esi
0x18002b07d  jge     short loc_18002B083
0x18002b07f  mov     eax, esi
0x18002b081  jmp     short loc_18002B086
0x18002b083  mov     eax, [rbx+8]
0x18002b086  cmp     r15d, eax
0x18002b089  jge     loc_18002B4D2
0x18002b08f  xor     edx, edx; Val
0x18002b091  mov     [rsp+240h+var_210], sil
0x18002b096  mov     r8d, 190h; Size
0x18002b09c  mov     [rsp+240h+var_20F], sil
0x18002b0a1  lea     rcx, [rsp+240h+var_1E0]; void *
0x18002b0a6  mov     r13b, sil
0x18002b0a9  mov     r12d, esi
0x18002b0ac  call    memset_0
0x18002b0b1  mov     rcx, rbx
0x18002b0b4  call    ?PContents@?$CMFBaseStringT@G@@QEBAPEBGXZ; CMFBaseStringT<ushort>::PContents(void)
0x18002b0b9  movsxd  rcx, r15d
0x18002b0bc  mov     rsi, rax
0x18002b0bf  lea     rax, [rax+rcx*2]
0x18002b0c3  mov     ecx, 0F0h
0x18002b0c8  mov     qword ptr [rsp+240h+var_208], rax
0x18002b0cd  mov     r10d, 80070057h
0x18002b0d3  cmp     rsi, rax
0x18002b0d6  jnb     loc_18002B31F
0x18002b0dc  cmp     word ptr [rsi], 22h ; '"'
0x18002b0e0  jnz     short loc_18002B0F9
0x18002b0e2  cmp     [rsp+240h+var_210], dil
0x18002b0e7  jnz     loc_18002B307
0x18002b0ed  test    r13b, r13b
0x18002b0f0  setz    r13b
0x18002b0f4  jmp     loc_18002B307
0x18002b0f9  cmp     word ptr [rsi], 27h ; '''
0x18002b0fd  jnz     short loc_18002B117
0x18002b0ff  test    r13b, r13b
0x18002b102  jnz     loc_18002B307
0x18002b108  cmp     [rsp+240h+var_210], dil
0x18002b10d  setz    [rsp+240h+var_210]
0x18002b112  jmp     loc_18002B307
0x18002b117  cmp     [rsp+240h+var_210], dil
0x18002b11c  jnz     loc_18002B307
0x18002b122  test    r13b, r13b
0x18002b125  jnz     loc_18002B307
0x18002b12b  cmp     word ptr [rsi], 28h ; '('
0x18002b12f  jnz     short loc_18002B148
0x18002b131  inc     r12d
0x18002b134  cmp     r12d, 64h ; 'd'
0x18002b138  jz      loc_18002B310
0x18002b13e  mov     [rsp+r12*4+240h+var_1E0], edi
0x18002b143  jmp     loc_18002B302
0x18002b148  cmp     word ptr [rsi], 29h ; ')'
0x18002b14c  jnz     short loc_18002B185
0x18002b14e  mov     eax, r12d
0x18002b151  mov     edx, [rsp+rax*4+240h+var_1E0]
0x18002b155  mov     eax, edx
0x18002b157  and     edx, ecx
0x18002b159  test    al, 2
0x18002b15b  cmovz   edx, ecx; unsigned int
0x18002b15e  test    edx, edx
0x18002b160  jz      loc_18002B315
0x18002b166  test    r12d, r12d
0x18002b169  jz      loc_18002B315
0x18002b16f  dec     r12d
0x18002b172  lea     rcx, [rsp+240h+var_1E0]
0x18002b177  lea     rcx, [rcx+r12*4]; unsigned int *
0x18002b17b  call    ?SetConditionFlags@CSearchQueryMapping@@KAXAEAKK@Z; CSearchQueryMapping::SetConditionFlags(ulong &,ulong)
0x18002b180  jmp     loc_18002B2FD
0x18002b185  mov     eax, 3
0x18002b18a  mov     [rsp+240h+cchValue], 1; bIgnoreCase
0x18002b192  mov     r9d, eax; cchCount2
0x18002b195  lea     r8, aAnd; "and"
0x18002b19c  mov     edx, eax; cchCount1
0x18002b19e  mov     rcx, rsi; lpString1
0x18002b1a1  call    cs:__imp_CompareStringOrdinal
0x18002b1a7  cmp     eax, 2
0x18002b1aa  jnz     short loc_18002B1D3
0x18002b1ac  mov     eax, r12d
0x18002b1af  lea     rcx, [rsp+240h+var_1E0]
0x18002b1b4  lea     rcx, [rcx+rax*4]; unsigned int *
0x18002b1b8  and     dword ptr [rcx], 0FFFFFFFEh
0x18002b1bb  test    byte ptr [rcx], 2
0x18002b1be  jnz     short loc_18002B1CA
0x18002b1c0  mov     edx, 0F0h; unsigned int
0x18002b1c5  call    ?SetConditionFlags@CSearchQueryMapping@@KAXAEAKK@Z; CSearchQueryMapping::SetConditionFlags(ulong &,ulong)
0x18002b1ca  add     rsi, 6
0x18002b1ce  jmp     loc_18002B2FD
0x18002b1d3  mov     r9d, 2; cchCount2
0x18002b1d9  mov     [rsp+240h+cchValue], 1; bIgnoreCase
0x18002b1e1  mov     edx, r9d; cchCount1
0x18002b1e4  lea     r8, aOr; "or"
0x18002b1eb  mov     rcx, rsi; lpString1
0x18002b1ee  call    cs:__imp_CompareStringOrdinal
0x18002b1f4  cmp     eax, 2
0x18002b1f7  jnz     short loc_18002B220
0x18002b1f9  mov     eax, r12d
0x18002b1fc  lea     rcx, [rsp+240h+var_1E0]
0x18002b201  lea     rcx, [rcx+rax*4]; unsigned int *
0x18002b205  or      dword ptr [rcx], 1
0x18002b208  test    byte ptr [rcx], 2
0x18002b20b  jnz     short loc_18002B217
0x18002b20d  mov     edx, 0F0h; unsigned int
0x18002b212  call    ?SetConditionFlags@CSearchQueryMapping@@KAXAEAKK@Z; CSearchQueryMapping::SetConditionFlags(ulong &,ulong)
0x18002b217  add     rsi, 4
0x18002b21b  jmp     loc_18002B2FD
0x18002b220  mov     eax, 2Eh ; '.'
0x18002b225  mov     [rsp+240h+cchValue], 1; bIgnoreCase
0x18002b22d  mov     r9d, eax; cchCount2
0x18002b230  lea     r8, aUpnpClassDeriv_7; "upnp:class derivedfrom \"object.item.im"...
0x18002b237  mov     edx, eax; cchCount1
0x18002b239  mov     rcx, rsi; lpString1
0x18002b23c  call    cs:__imp_CompareStringOrdinal
0x18002b242  cmp     eax, 2
0x18002b245  jnz     short loc_18002B264
0x18002b247  lea     edx, [rax+0Eh]; unsigned int
0x18002b24a  mov     eax, r12d
0x18002b24d  lea     rcx, [rsp+240h+var_1E0]
0x18002b252  lea     rcx, [rcx+rax*4]; unsigned int *
0x18002b256  call    ?SetConditionFlags@CSearchQueryMapping@@KAXAEAKK@Z; CSearchQueryMapping::SetConditionFlags(ulong &,ulong)
0x18002b25b  add     rsi, 5Ah ; 'Z'
0x18002b25f  jmp     loc_18002B2FD
0x18002b264  mov     eax, 2Eh ; '.'
0x18002b269  mov     [rsp+240h+cchValue], 1; bIgnoreCase
0x18002b271  mov     r9d, eax; cchCount2
0x18002b274  lea     r8, aUpnpClassDeriv_15; "upnp:class derivedfrom \"object.item.au"...
0x18002b27b  mov     edx, eax; cchCount1
0x18002b27d  mov     rcx, rsi; lpString1
0x18002b280  call    cs:__imp_CompareStringOrdinal
0x18002b286  cmp     eax, 2
0x18002b289  jnz     short loc_18002B290
0x18002b28b  lea     edx, [rax+1Eh]
0x18002b28e  jmp     short loc_18002B24A
0x18002b290  mov     eax, 2Eh ; '.'
0x18002b295  mov     [rsp+240h+cchValue], 1; bIgnoreCase
0x18002b29d  mov     r9d, eax; cchCount2
0x18002b2a0  lea     r8, aUpnpClassDeriv_5; "upnp:class derivedfrom \"object.item.vi"...
0x18002b2a7  mov     edx, eax; cchCount1
0x18002b2a9  mov     rcx, rsi; lpString1
0x18002b2ac  call    cs:__imp_CompareStringOrdinal
0x18002b2b2  cmp     eax, 2
0x18002b2b5  jnz     short loc_18002B2BC
0x18002b2b7  lea     edx, [rax+3Eh]
0x18002b2ba  jmp     short loc_18002B24A
0x18002b2bc  mov     eax, 3Dh ; '='
0x18002b2c1  mov     [rsp+240h+cchValue], 1; bIgnoreCase
0x18002b2c9  mov     r9d, eax; cchCount2
0x18002b2cc  lea     r8, aUpnpClassDeriv_12; "upnp:class derivedfrom \"object.item.vi"...
0x18002b2d3  mov     edx, eax; cchCount1
0x18002b2d5  mov     rcx, rsi; lpString1
0x18002b2d8  call    cs:__imp_CompareStringOrdinal
0x18002b2de  cmp     eax, 2
0x18002b2e1  jnz     short loc_18002B2FD
0x18002b2e3  mov     eax, r12d
0x18002b2e6  lea     rcx, [rsp+240h+var_1E0]
0x18002b2eb  mov     edx, 80h; unsigned int
0x18002b2f0  lea     rcx, [rcx+rax*4]; unsigned int *
0x18002b2f4  call    ?SetConditionFlags@CSearchQueryMapping@@KAXAEAKK@Z; CSearchQueryMapping::SetConditionFlags(ulong &,ulong)
0x18002b2f9  add     rsi, 78h ; 'x'
0x18002b2fd  mov     ecx, 0F0h
0x18002b302  mov     rax, qword ptr [rsp+240h+var_208]
0x18002b307  add     rsi, 2
0x18002b30b  jmp     loc_18002B0CD
0x18002b310  mov     r9b, 1
0x18002b313  jmp     short loc_18002B322
0x18002b315  mov     r9b, [rsp+240h+var_20F]
0x18002b31a  mov     edi, r10d
0x18002b31d  jmp     short loc_18002B322
0x18002b31f  mov     r9b, dil
  ... truncated ...
```
