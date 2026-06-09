# ValidateAuthIdEx2(_SEC_WINNT_AUTH_IDENTITY_EX2 *,ushort * *,ushort * *,ushort * *)

- ea: `0x18000d000`
- end: `0x18000d776`
- name: `?ValidateAuthIdEx2@@YAJPEAU_SEC_WINNT_AUTH_IDENTITY_EX2@@PEAPEAG11@Z`
- size: `1910`
- prototype: `int(struct _SEC_WINNT_AUTH_IDENTITY_EX2 *, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180026ec0`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x18000b9b0`
- `0x18000d000`
- `0x18007f9fc`
- `0x180081010`

## string_xrefs

- `0x18000d4e9`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18000d598`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18000d33f`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18000d38d`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18000d3f8`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18000d44a`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18000d523`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18000d52f`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18000d5cb`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18000d5f8`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18000d62c`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18000d665`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18000d69e`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18000d6d7`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18000d710`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`

## pseudocode

```c
__int64 __fastcall ValidateAuthIdEx2(
        struct _SEC_WINNT_AUTH_IDENTITY_EX2 *a1,
        unsigned __int16 **a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4)
{
  unsigned __int16 *v8; // rdi
  unsigned int Version; // eax
  unsigned int cbHeaderLength; // eax
  unsigned int cbStructureLength; // ecx
  unsigned int v12; // r10d
  __int64 DomainOffset; // r9
  size_t DomainLength; // rsi
  unsigned int UserOffset; // edx
  unsigned int UserLength; // r8d
  __int64 PackedCredentialsOffset; // rdx
  unsigned int PackedCredentialsLength; // r8d
  unsigned int PackageListOffset; // eax
  unsigned int PackageListLength; // r10d
  unsigned __int16 v21; // cx
  __int64 v22; // rax
  unsigned int v23; // edx
  unsigned int v24; // r8d
  char *v25; // r12
  void *v26; // rax
  _WORD *v27; // rsi
  size_t v28; // rbx
  void *v29; // rax
  unsigned int v30; // ebx
  const char *v31; // r9
  const char *v33; // r9
  char v34; // dl
  const char *v35; // r8
  bool v36; // zf
  const char *v37; // r9
  char v38; // al
  const char *v39; // rdx
  bool v40; // zf
  char v41; // al
  const char *v42; // rdx
  bool v43; // zf
  char v44; // al
  const char *v45; // rdx
  bool v46; // zf
  char v47; // al
  const char *v48; // r8
  bool v49; // zf
  const char *v50; // rax
  int v51; // r8d
  __int64 v52; // r10
  const char *v53; // rax
  int v54; // r8d
  __int64 v55; // r10
  const char *v56; // r9
  __int64 v57; // [rsp+20h] [rbp-68h]
  const char *v58; // [rsp+28h] [rbp-60h]
  __int128 v59; // [rsp+40h] [rbp-48h]
  __int128 v60; // [rsp+50h] [rbp-38h]
  unsigned __int16 *v61; // [rsp+90h] [rbp+8h] BYREF

  v61 = 0;
  *a4 = 0;
  v8 = 0;
  v60 = 0;
  *a2 = 0;
  v59 = 0;
  Version = a1->Version;
  *a3 = 0;
  if ( Version != 513 )
  {
    v30 = -1073741811;
    v33 = "";
    while ( 1 )
    {
      v34 = *(v33 - 1);
      v35 = v33--;
      v36 = v34 == 92;
      if ( v34 == 92 )
        break;
      if ( v33 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
      {
        v36 = v34 == 92;
        break;
      }
    }
    if ( v36 )
      v33 = v35;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%u", 3221225485LL, v33, 253, "invalid version", Version);
    goto LABEL_51;
  }
  cbHeaderLength = a1->cbHeaderLength;
  if ( cbHeaderLength < 0x30
    || (cbStructureLength = a1->cbStructureLength, v12 = cbHeaderLength, cbStructureLength < cbHeaderLength) )
  {
    v30 = -1073741811;
    v31 = "";
    while ( 1 )
    {
      v41 = *(v31 - 1);
      v42 = v31--;
      v43 = v41 == 92;
      if ( v41 == 92 )
        break;
      if ( v31 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
      {
        v43 = v41 == 92;
        break;
      }
    }
    if ( v43 )
      v31 = v42;
    v58 = "Invalid lengths";
    LODWORD(v57) = 260;
    goto LABEL_50;
  }
  DomainOffset = a1->DomainOffset;
  if ( (_DWORD)DomainOffset && (unsigned int)DomainOffset < cbHeaderLength
    || (unsigned int)DomainOffset > cbStructureLength
    || (DomainLength = a1->DomainLength, (unsigned int)DomainLength >= cbStructureLength)
    || (DomainLength & 1) != 0
    || cbStructureLength - (unsigned int)DomainLength < (unsigned int)DomainOffset )
  {
    v30 = -1073741811;
    v31 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    v58 = "Bad domain data";
    LODWORD(v57) = 271;
    goto LABEL_50;
  }
  UserOffset = a1->UserOffset;
  if ( UserOffset && UserOffset < cbHeaderLength
    || UserOffset > cbStructureLength
    || (UserLength = a1->UserLength, UserLength >= cbStructureLength)
    || (UserLength & 1) != 0
    || cbStructureLength - UserLength < UserOffset )
  {
    v30 = -1073741811;
    v31 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    v58 = "Bad user data";
    LODWORD(v57) = 281;
    goto LABEL_50;
  }
  PackedCredentialsOffset = a1->PackedCredentialsOffset;
  if ( (_DWORD)PackedCredentialsOffset && (unsigned int)PackedCredentialsOffset < cbHeaderLength
    || (unsigned int)PackedCredentialsOffset > cbStructureLength
    || (PackedCredentialsLength = a1->PackedCredentialsLength, PackedCredentialsLength >= cbStructureLength)
    || !(_WORD)PackedCredentialsLength
    || cbStructureLength - PackedCredentialsLength < (unsigned int)PackedCredentialsOffset )
  {
    v30 = -1073741811;
    v31 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    v58 = "Bad packed credentials";
    LODWORD(v57) = 291;
    goto LABEL_50;
  }
  PackageListOffset = a1->PackageListOffset;
  if ( PackageListOffset && PackageListOffset < v12
    || PackageListOffset > cbStructureLength
    || (PackageListLength = a1->PackageListLength, PackageListLength >= cbStructureLength)
    || cbStructureLength - PackageListLength < PackageListOffset )
  {
    v30 = -1073741811;
    v31 = "";
    while ( 1 )
    {
      v44 = *(v31 - 1);
      v45 = v31--;
      v46 = v44 == 92;
      if ( v44 == 92 )
        break;
      if ( v31 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
      {
        v46 = v44 == 92;
        break;
      }
    }
    if ( v46 )
      v31 = v45;
    v58 = "Bad package list";
    LODWORD(v57) = 300;
    goto LABEL_50;
  }
  if ( PackedCredentialsLength < 0x1C
    || (v21 = *(_WORD *)((char *)&a1->Version + PackedCredentialsOffset), v22 = a1->PackedCredentialsOffset, v21 < 0x1Cu)
    || (v23 = *(unsigned __int16 *)((char *)&a1->Version + PackedCredentialsOffset + 2),
        (unsigned __int16)v23 > (unsigned __int16)PackedCredentialsLength)
    || v21 > (unsigned __int16)v23 )
  {
    v30 = -1073741811;
    v31 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    v58 = "Bad packed credentials data";
    LODWORD(v57) = 313;
    goto LABEL_50;
  }
  v24 = *(unsigned int *)((char *)&a1->DomainOffset + v22) + *(unsigned __int16 *)((char *)&a1->DomainLength + v22);
  if ( v24 < *(unsigned int *)((char *)&a1->DomainOffset + v22) || v24 > v23 )
  {
    v30 = -1073741811;
    v31 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    v58 = "Bad auth data";
    LODWORD(v57) = 324;
    goto LABEL_50;
  }
  v25 = (char *)a1 + DomainOffset;
  if ( (struct _SEC_WINNT_AUTH_IDENTITY_EX2 *)((char *)a1 + DomainOffset) && (_WORD)DomainLength )
  {
    if ( (DomainLength & 1) != 0 )
    {
      v30 = -1073741811;
    }
    else
    {
      v26 = (void *)((__int64 (__fastcall *)(_QWORD))g_pLsaFunctionTable->AllocateLsaHeap)((unsigned __int16)(DomainLength + 2));
      *((_QWORD *)&v60 + 1) = v26;
      if ( v26 )
      {
        memcpy_0(v26, v25, DomainLength);
        goto LABEL_37;
      }
      v30 = -1073741801;
    }
    v50 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v30, v50, v51, v52, &Class);
    v31 = "";
    while ( 1 )
    {
      v47 = *(v31 - 1);
      v48 = v31--;
      v49 = v47 == 92;
      if ( v47 == 92 )
        break;
      if ( v31 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
      {
        v49 = v47 == 92;
        break;
      }
    }
    v58 = "DuplicateString";
    if ( v49 )
      v31 = v48;
    LODWORD(v57) = 335;
    goto LABEL_50;
  }
LABEL_37:
  v27 = (_WORD *)((char *)a1 + a1->UserOffset);
  v28 = a1->UserLength;
  if ( (_WORD)v28 && *v27 == 64 )
  {
    v30 = -1073741811;
    v31 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    v58 = "Bad user name";
    LODWORD(v57) = 346;
LABEL_50:
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v30, v31, v57, v58, &Class);
    goto LABEL_51;
  }
  if ( !v27 || !(_WORD)v28 )
    goto LABEL_44;
  if ( (v28 & 1) != 0 )
  {
    v30 = -1073741811;
    goto LABEL_98;
  }
  v29 = (void *)((__int64 (__fastcall *)(_QWORD))g_pLsaFunctionTable->AllocateLsaHeap)((unsigned __int16)(v28 + 2));
  *((_QWORD *)&v59 + 1) = v29;
  if ( !v29 )
  {
    v30 = -1073741801;
LABEL_98:
    v53 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v30, v53, v54, v55, &Class);
    v31 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    v58 = "DuplicateString";
    LODWORD(v57) = 352;
    goto LABEL_50;
  }
  memcpy_0(v29, v27, v28);
LABEL_44:
  v30 = DuplicateString(*((const unsigned __int16 **)&v59 + 1), 0, &v61);
  if ( v30 )
  {
    v37 = "";
    while ( 1 )
    {
      v38 = *(v37 - 1);
      v39 = v37--;
      v40 = v38 == 92;
      if ( v38 == 92 )
        break;
      if ( v37 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
      {
        v40 = v38 == 92;
        break;
      }
    }
    if ( v40 )
      v37 = v39;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v30, v37, 358, "DuplicateString", &Class);
  }
  else
  {
    v30 = DuplicateString(*((const unsigned __int16 **)&v59 + 1), 1, a4);
    if ( !v30 )
    {
      *a3 = v61;
      *a2 = (unsigned __int16 *)*((_QWORD *)&v60 + 1);
      goto LABEL_53;
    }
    v56 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v30, v56, 365, "DuplicateString", &Class);
  }
  v8 = v61;
LABEL_51:
  if ( *((_QWORD *)&v60 + 1) )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
LABEL_53:
  if ( *((_QWORD *)&v59 + 1) )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( v8 )
    ((void (__fastcall *)(unsigned __int16 *))g_pLsaFunctionTable->FreeLsaHeap)(v8);
  return v30;
}

```

## disassembly

```asm
0x18000d000  mov     rax, rsp
0x18000d003  push    rbx
0x18000d004  push    rdi
0x18000d005  sub     rsp, 78h
0x18000d009  mov     [rax+10h], rbp
0x18000d00d  xorps   xmm0, xmm0
0x18000d010  mov     [rax+18h], rsi
0x18000d014  xorps   xmm1, xmm1
0x18000d017  mov     [rax+20h], r12
0x18000d01b  mov     rbp, r9
0x18000d01e  mov     [rax-18h], r13
0x18000d022  mov     rbx, rcx
0x18000d025  xor     r13d, r13d
0x18000d028  mov     [rax-20h], r14
0x18000d02c  mov     [rax-28h], r15
0x18000d030  mov     r14, r8
0x18000d033  mov     [rax+8], r13
0x18000d037  mov     r15, rdx
0x18000d03a  mov     [r9], r13
0x18000d03d  mov     edi, r13d
0x18000d040  movups  xmmword ptr [rax-38h], xmm0
0x18000d044  mov     [rdx], r13
0x18000d047  movups  xmmword ptr [rax-48h], xmm1
0x18000d04b  mov     eax, [rcx]
0x18000d04d  mov     [r8], r13
0x18000d050  cmp     eax, 201h
0x18000d055  jnz     loc_18000D333
0x18000d05b  movzx   eax, word ptr [rcx+4]
0x18000d05f  cmp     eax, 30h ; '0'
0x18000d062  jb      loc_18000D3EC
0x18000d068  mov     ecx, [rcx+8]
0x18000d06b  mov     r10d, eax
0x18000d06e  cmp     ecx, eax
0x18000d070  jb      loc_18000D3EC
0x18000d076  mov     r9d, [rbx+14h]
0x18000d07a  test    r9d, r9d
0x18000d07d  jz      short loc_18000D088
0x18000d07f  cmp     r9d, eax
0x18000d082  jb      loc_18000D710
0x18000d088  cmp     r9d, ecx
0x18000d08b  ja      loc_18000D710
0x18000d091  movzx   esi, word ptr [rbx+18h]
0x18000d095  cmp     esi, ecx
0x18000d097  jnb     loc_18000D710
0x18000d09d  test    sil, 1
0x18000d0a1  jnz     loc_18000D710
0x18000d0a7  mov     eax, ecx
0x18000d0a9  sub     eax, esi
0x18000d0ab  cmp     eax, r9d
0x18000d0ae  jb      loc_18000D710
0x18000d0b4  mov     edx, [rbx+0Ch]
0x18000d0b7  test    edx, edx
0x18000d0b9  jz      short loc_18000D0C4
0x18000d0bb  cmp     edx, r10d
0x18000d0be  jb      loc_18000D6D7
0x18000d0c4  cmp     edx, ecx
0x18000d0c6  ja      loc_18000D6D7
0x18000d0cc  movzx   r8d, word ptr [rbx+10h]
0x18000d0d1  cmp     r8d, ecx
0x18000d0d4  jnb     loc_18000D6D7
0x18000d0da  test    r8b, 1
0x18000d0de  jnz     loc_18000D6D7
0x18000d0e4  mov     eax, ecx
0x18000d0e6  sub     eax, r8d
0x18000d0e9  cmp     eax, edx
0x18000d0eb  jb      loc_18000D6D7
0x18000d0f1  mov     edx, [rbx+1Ch]
0x18000d0f4  test    edx, edx
0x18000d0f6  jz      short loc_18000D101
0x18000d0f8  cmp     edx, r10d
0x18000d0fb  jb      loc_18000D69E
0x18000d101  cmp     edx, ecx
0x18000d103  ja      loc_18000D69E
0x18000d109  movzx   r8d, word ptr [rbx+20h]
0x18000d10e  cmp     r8d, ecx
0x18000d111  jnb     loc_18000D69E
0x18000d117  test    r8w, r8w
0x18000d11b  jz      loc_18000D69E
0x18000d121  mov     eax, ecx
0x18000d123  sub     eax, r8d
0x18000d126  cmp     eax, edx
0x18000d128  jb      loc_18000D69E
0x18000d12e  mov     eax, [rbx+28h]
0x18000d131  test    eax, eax
0x18000d133  jnz     loc_18000D4AF
0x18000d139  cmp     eax, ecx
0x18000d13b  ja      loc_18000D43E
0x18000d141  movzx   r10d, word ptr [rbx+2Ch]
0x18000d146  cmp     r10d, ecx
0x18000d149  jnb     loc_18000D43E
0x18000d14f  sub     ecx, r10d
0x18000d152  cmp     ecx, eax
0x18000d154  jb      loc_18000D43E
0x18000d15a  cmp     r8d, 1Ch
0x18000d15e  jb      loc_18000D665
0x18000d164  movzx   ecx, word ptr [rdx+rbx]
0x18000d168  mov     rax, rdx
0x18000d16b  cmp     cx, 1Ch
0x18000d16f  jb      loc_18000D665
0x18000d175  movzx   edx, word ptr [rdx+rbx+2]
0x18000d17a  cmp     dx, r8w
0x18000d17e  ja      loc_18000D665
0x18000d184  cmp     cx, dx
0x18000d187  ja      loc_18000D665
0x18000d18d  movzx   r8d, word ptr [rax+rbx+18h]
0x18000d193  add     r8d, [rax+rbx+14h]
0x18000d198  cmp     r8d, [rax+rbx+14h]
0x18000d19d  jb      loc_18000D62C
0x18000d1a3  cmp     r8d, edx
0x18000d1a6  ja      loc_18000D62C
0x18000d1ac  mov     r12, r9
0x18000d1af  add     r12, rbx
0x18000d1b2  jz      short loc_18000D1F6
0x18000d1b4  cmp     r13w, si
0x18000d1b8  jz      short loc_18000D1F6
0x18000d1ba  test    sil, 1
0x18000d1be  jnz     loc_18000D4CD
0x18000d1c4  lea     eax, [rsi+2]
0x18000d1c7  movzx   ecx, ax
0x18000d1ca  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18000d1d1  mov     rax, [rax+28h]
0x18000d1d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1da  mov     [rsp+88h+var_30], rax
0x18000d1df  test    rax, rax
0x18000d1e2  jz      loc_18000D4B9
0x18000d1e8  mov     r8, rsi; Size
0x18000d1eb  mov     rdx, r12; Src
0x18000d1ee  mov     rcx, rax; void *
0x18000d1f1  call    memcpy_0
0x18000d1f6  mov     esi, [rbx+0Ch]
0x18000d1f9  add     rsi, rbx
0x18000d1fc  movzx   ebx, word ptr [rbx+10h]
0x18000d200  test    bx, bx
0x18000d203  jz      short loc_18000D20F
0x18000d205  cmp     word ptr [rsi], 40h ; '@'
0x18000d209  jz      loc_18000D52F
0x18000d20f  test    rsi, rsi
0x18000d212  jz      short loc_18000D255
0x18000d214  cmp     r13w, bx
0x18000d218  jz      short loc_18000D255
0x18000d21a  test    bl, 1
0x18000d21d  jnz     loc_18000D57C
0x18000d223  lea     eax, [rbx+2]
0x18000d226  movzx   ecx, ax
0x18000d229  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18000d230  mov     rax, [rax+28h]
0x18000d234  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d239  mov     [rsp+88h+Src], rax
0x18000d23e  test    rax, rax
0x18000d241  jz      loc_18000D568
0x18000d247  mov     r8, rbx; Size
0x18000d24a  mov     rdx, rsi; Src
0x18000d24d  mov     rcx, rax; void *
0x18000d250  call    memcpy_0
0x18000d255  mov     rcx, [rsp+88h+Src]; Src
0x18000d25a  lea     r8, [rsp+88h+arg_0]; unsigned __int16 **
0x18000d262  xor     edx, edx; int
0x18000d264  call    ?DuplicateString@@YAJPEBGHPEAPEAG@Z; DuplicateString(ushort const *,int,ushort * *)
0x18000d269  mov     ebx, eax
0x18000d26b  test    eax, eax
0x18000d26d  jnz     loc_18000D386
0x18000d273  mov     rcx, [rsp+88h+Src]; Src
0x18000d278  mov     r8, rbp; unsigned __int16 **
0x18000d27b  mov     edx, 1; int
0x18000d280  call    ?DuplicateString@@YAJPEBGHPEAPEAG@Z; DuplicateString(ushort const *,int,ushort * *)
0x18000d285  mov     ebx, eax
0x18000d287  test    eax, eax
0x18000d289  jnz     loc_18000D5F8
0x18000d28f  mov     rax, [rsp+88h+arg_0]
0x18000d297  mov     [r14], rax
0x18000d29a  mov     rax, [rsp+88h+var_30]
0x18000d29f  mov     [r15], rax
0x18000d2a2  jmp     short loc_18000D2E0
0x18000d2a4  mov     [rsp+88h+var_58], rsi
0x18000d2a9  lea     rax, aDuplicatestrin_1; "DuplicateString"
0x18000d2b0  mov     [rsp+88h+var_60], rax
0x18000d2b5  cmovz   r9, r8
0x18000d2b9  mov     dword ptr [rsp+88h+var_68], 14Fh
0x18000d2c1  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000d2c8  mov     r8d, ebx
0x18000d2cb  xor     ecx, ecx
0x18000d2cd  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000d2d2  mov     rcx, [rsp+88h+var_30]
0x18000d2d7  test    rcx, rcx
0x18000d2da  jnz     loc_18000D749
0x18000d2e0  mov     rcx, [rsp+88h+Src]
0x18000d2e5  mov     r15, [rsp+88h+var_28]
0x18000d2ea  mov     r14, [rsp+88h+var_20]
0x18000d2ef  mov     r13, [rsp+88h+var_18]
0x18000d2f4  mov     r12, [rsp+88h+arg_18]
0x18000d2fc  mov     rsi, [rsp+88h+arg_10]
0x18000d304  mov     rbp, [rsp+88h+arg_8]
0x18000d30c  test    rcx, rcx
0x18000d30f  jz      short loc_18000D321
0x18000d311  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18000d318  mov     rax, [rax+30h]
0x18000d31c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d321  test    rdi, rdi
0x18000d324  jnz     loc_18000D75E
0x18000d32a  mov     eax, ebx
0x18000d32c  add     rsp, 78h
0x18000d330  pop     rdi
0x18000d331  pop     rbx
0x18000d332  retn
0x18000d333  mov     ebx, 0C000000Dh
0x18000d338  lea     r9, aOnecoreDsExtCl_6+27h; ""
0x18000d33f  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18000d346  movzx   edx, byte ptr [r9-1]
0x18000d34b  mov     r8, r9
0x18000d34e  dec     r9
0x18000d351  cmp     dl, 5Ch ; '\'
0x18000d354  jz      short loc_18000D35E
0x18000d356  cmp     r9, rcx
0x18000d359  ja      short loc_18000D346
0x18000d35b  cmp     dl, 5Ch ; '\'
0x18000d35e  mov     dword ptr [rsp+88h+var_58], eax
0x18000d362  lea     rdx, a0x08xSUSU; "0x%08x %s:%u : %s:%u"
0x18000d369  lea     rax, aInvalidVersion; "invalid version"
0x18000d370  cmovz   r9, r8
0x18000d374  mov     [rsp+88h+var_60], rax
0x18000d379  mov     dword ptr [rsp+88h+var_68], 0FDh
0x18000d381  jmp     loc_18000D2C8
0x18000d386  lea     r9, aOnecoreDsExtCl_6+27h; ""
0x18000d38d  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18000d394  movzx   eax, byte ptr [r9-1]
0x18000d399  mov     rdx, r9
0x18000d39c  dec     r9
0x18000d39f  cmp     al, 5Ch ; '\'
0x18000d3a1  jz      short loc_18000D3AA
0x18000d3a3  cmp     r9, rcx
0x18000d3a6  ja      short loc_18000D394
0x18000d3a8  cmp     al, 5Ch ; '\'
0x18000d3aa  lea     rsi, Class
0x18000d3b1  cmovz   r9, rdx
0x18000d3b5  mov     [rsp+88h+var_58], rsi
0x18000d3ba  lea     rax, aDuplicatestrin_1; "DuplicateString"
0x18000d3c1  mov     [rsp+88h+var_60], rax
0x18000d3c6  mov     dword ptr [rsp+88h+var_68], 166h
0x18000d3ce  mov     r8d, ebx
0x18000d3d1  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000d3d8  xor     ecx, ecx
0x18000d3da  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000d3df  mov     rdi, [rsp+88h+arg_0]
0x18000d3e7  jmp     loc_18000D2D2
0x18000d3ec  mov     ebx, 0C000000Dh
0x18000d3f1  lea     r9, aOnecoreDsExtCl_6+27h; ""
0x18000d3f8  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18000d3ff  movzx   eax, byte ptr [r9-1]
0x18000d404  mov     rdx, r9
0x18000d407  dec     r9
0x18000d40a  cmp     al, 5Ch ; '\'
0x18000d40c  jz      short loc_18000D415
0x18000d40e  cmp     r9, rcx
0x18000d411  ja      short loc_18000D3FF
0x18000d413  cmp     al, 5Ch ; '\'
0x18000d415  lea     rsi, Class
0x18000d41c  cmovz   r9, rdx
0x18000d420  mov     [rsp+88h+var_58], rsi
0x18000d425  lea     rax, aInvalidLengths; "Invalid lengths"
0x18000d42c  mov     [rsp+88h+var_60], rax
0x18000d431  mov     dword ptr [rsp+88h+var_68], 104h
0x18000d439  jmp     loc_18000D2C1
0x18000d43e  mov     ebx, 0C000000Dh
0x18000d443  lea     r9, aOnecoreDsExtCl_6+27h; ""
0x18000d44a  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18000d451  movzx   eax, byte ptr [r9-1]
0x18000d456  mov     rdx, r9
0x18000d459  dec     r9
0x18000d45c  cmp     al, 5Ch ; '\'
0x18000d45e  jz      short loc_18000D467
0x18000d460  cmp     r9, rcx
0x18000d463  ja      short loc_18000D451
0x18000d465  cmp     al, 5Ch ; '\'
0x18000d467  lea     rsi, Class
0x18000d46e  cmovz   r9, rdx
0x18000d472  mov     [rsp+88h+var_58], rsi
0x18000d477  lea     rax, aBadPackageList; "Bad package list"
0x18000d47e  mov     [rsp+88h+var_60], rax
0x18000d483  mov     dword ptr [rsp+88h+var_68], 12Ch
0x18000d48b  jmp     loc_18000D2C1
0x18000d490  movzx   eax, byte ptr [r9-1]
0x18000d495  mov     r8, r9
0x18000d498  dec     r9
0x18000d49b  cmp     al, 5Ch ; '\'
0x18000d49d  jz      loc_18000D2A4
0x18000d4a3  cmp     r9, rcx
0x18000d4a6  ja      short loc_18000D490
0x18000d4a8  cmp     al, 5Ch ; '\'
0x18000d4aa  jmp     loc_18000D2A4
0x18000d4af  cmp     eax, r10d
0x18000d4b2  jb      short loc_18000D43E
0x18000d4b4  jmp     loc_18000D139
0x18000d4b9  mov     ebx, 0C0000017h
0x18000d4be  lea     r10, aAllocatelsahea_3; "AllocateLsaHeap"
0x18000d4c5  mov     r8d, 10Bh
0x18000d4cb  jmp     short loc_18000D4DF
0x18000d4cd  mov     ebx, 0C000000Dh
0x18000d4d2  lea     r10, aMalformedSourc; "Malformed source string"
0x18000d4d9  mov     r8d, 102h
0x18000d4df  lea     rsi, Class
  ... truncated ...
```
