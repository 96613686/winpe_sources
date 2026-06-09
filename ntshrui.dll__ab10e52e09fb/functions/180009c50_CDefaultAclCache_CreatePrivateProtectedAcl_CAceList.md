# CDefaultAclCache::_CreatePrivateProtectedAcl(CAceList * *)

- ea: `0x180009c50`
- end: `0x18000a427`
- name: `?_CreatePrivateProtectedAcl@CDefaultAclCache@@AEAAJPEAPEAVCAceList@@@Z`
- size: `2007`
- prototype: `__int64 __fastcall(CDefaultAclCache *__hidden this, struct CAceList **)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180009a40`
- `0x180009c00`

## callees

- `0x1800098dc`
- `0x180009c50`
- `0x18000a430`
- `0x18000bc00`
- `0x18000d1f0`
- `0x18000f4b0`
- `0x18000f7a0`
- `0x18000f7f0`
- `0x18000f840`
- `0x1800259bc`
- `0x180034090`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a254`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a289`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a254`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a289`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180009e54`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000a07c`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180009e54`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000a07c`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180009fa4`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000a1c6`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180009fa4`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000a1c6`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180009ddd`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000a010`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180009ddd`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000a010`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180009eb9`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000a0d4`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180009eb9`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000a0d4`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180009e3a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180009e83`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000a067`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000a09e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180009e3a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180009e83`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000a067`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000a09e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009e97`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009f83`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a0b7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a1a5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009e97`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009f83`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a0b7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a1a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009d45`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009d56`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a185`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a1eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a2d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a2f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009d45`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009d56`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a185`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a1eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a2d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a2f5`
- `ntdll!RtlMapGenericMask` at `0x180009ef8`
- `ntdll!RtlMapGenericMask` at `0x18000a110`
- `ntdll!RtlMapGenericMask` at `0x180009ef8`
- `ntdll!RtlMapGenericMask` at `0x18000a110`

## pseudocode

```c
__int64 __fastcall CDefaultAclCache::_CreatePrivateProtectedAcl(CDefaultAclCache *this, struct CAceList **a2)
{
  __int64 v2; // rbx
  int CurrentUserSid; // ebx
  CAce *v5; // rax
  CAceList *v6; // rsi
  unsigned int v7; // edx
  int v8; // ebp
  CAceList *v9; // rax
  CAceList *v10; // rsi
  HLOCAL v12; // r13
  int *v13; // rax
  int v14; // r14d
  FARPROC ProcAddress; // rax
  int i; // ebx
  __int64 v17; // rbp
  __int64 v18; // rbp
  CAce *v19; // rax
  unsigned int v20; // edx
  CAce *v21; // r14
  __int16 LengthSid; // ax
  HLOCAL v23; // rcx
  __int16 v24; // r13
  unsigned int v25; // edx
  HLOCAL v26; // rax
  char v27; // cl
  unsigned int v28; // eax
  unsigned int (__fastcall *v29)(__int64, __int64, CAce *); // rax
  __int64 v30; // rbx
  HLOCAL v31; // rax
  void *v32; // rbp
  int *v33; // rax
  int v34; // r13d
  FARPROC v35; // rax
  int j; // ebx
  __int64 v37; // r14
  __int64 v38; // r14
  _QWORD *v39; // rax
  _QWORD *v40; // r14
  __int16 v41; // ax
  __int16 v42; // r12
  unsigned int v43; // edx
  HLOCAL v44; // rax
  char v45; // al
  unsigned int v46; // eax
  unsigned int (__fastcall *v47)(__int64, __int64, _QWORD *); // rax
  __int64 v48; // rbx
  HLOCAL v49; // rax
  void *v50; // rdi
  HLOCAL v51; // rcx
  unsigned int v52; // edx
  __int64 v53; // rcx
  __int64 v54; // rcx
  __int64 v55; // rcx
  HLOCAL v56; // [rsp+20h] [rbp-48h]
  CAce *nDestinationSidLength; // [rsp+70h] [rbp+8h] BYREF
  HLOCAL v58; // [rsp+80h] [rbp+18h]
  HLOCAL hMem; // [rsp+88h] [rbp+20h] BYREF

  v2 = *((_QWORD *)this + 7);
  if ( v2 )
  {
    v8 = -2147024882;
    *a2 = 0;
    v9 = (CAceList *)operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
    nDestinationSidLength = v9;
    v10 = v9;
    if ( v9 )
    {
      *(_QWORD *)v9 = 0;
      *((_QWORD *)v9 + 1) = 0;
      *((_QWORD *)v9 + 2) = 0;
      *((_QWORD *)v9 + 3) = 1;
      v8 = CAceList::_Init(v9);
      if ( v8 < 0
        || (v8 = CAceList::_CloneDpa(v53, v10, v2), v8 < 0)
        || (v8 = CAceList::_CloneDpa(v54, (char *)v10 + 8, v2 + 8), v8 < 0)
        || (v8 = CAceList::_CloneDpa(v55, (char *)v10 + 16, v2 + 16), v8 < 0) )
      {
        CAceList::`scalar deleting destructor'(v10, v52);
      }
      else
      {
        *a2 = v10;
      }
    }
    return (unsigned int)v8;
  }
  CurrentUserSid = -2147024882;
  v5 = (CAce *)operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
  nDestinationSidLength = v5;
  v6 = v5;
  if ( !v5 )
    return (unsigned int)CurrentUserSid;
  *(_QWORD *)v5 = 0;
  *((_QWORD *)v5 + 1) = 0;
  *((_QWORD *)v5 + 2) = 0;
  *((_QWORD *)v5 + 3) = 1;
  CurrentUserSid = CAceList::_Init(v5);
  if ( CurrentUserSid < 0 )
  {
LABEL_6:
    CAceList::`scalar deleting destructor'(v6, v7);
    return (unsigned int)CurrentUserSid;
  }
  hMem = 0;
  CurrentUserSid = GetCurrentUserSid(&hMem);
  if ( CurrentUserSid < 0 )
  {
LABEL_5:
    if ( !v6 )
      return (unsigned int)CurrentUserSid;
    goto LABEL_6;
  }
  v13 = (int *)*((_QWORD *)v6 + 1);
  v12 = hMem;
  if ( v13 )
    v14 = *v13;
  else
    v14 = 0;
  ProcAddress = (FARPROC)qword_180095A20;
  for ( i = 0; i < v14; ++i )
  {
    v17 = *((_QWORD *)v6 + 1);
    if ( ProcAddress == (FARPROC)-1LL )
    {
      if ( !g_hinstCC )
      {
        DelayLoadCC();
        if ( !g_hinstCC )
        {
          ProcAddress = 0;
          qword_180095A20 = 0;
LABEL_92:
          v18 = 0;
          goto LABEL_21;
        }
      }
      ProcAddress = GetProcAddress(g_hinstCC, (LPCSTR)0x14C);
      qword_180095A20 = (__int64 (__fastcall *)(_QWORD, _QWORD))ProcAddress;
    }
    if ( !ProcAddress )
      goto LABEL_92;
    v18 = ((__int64 (__fastcall *)(__int64, _QWORD))ProcAddress)(v17, i);
    ProcAddress = (FARPROC)qword_180095A20;
LABEL_21:
    if ( !*(_DWORD *)(v18 + 24) && *(_BYTE *)(v18 + 1) == 3 )
    {
      if ( EqualSid(*(PSID *)(v18 + 8), v12) )
      {
        *(_DWORD *)(v18 + 4) = 2032127;
        goto LABEL_43;
      }
      ProcAddress = (FARPROC)qword_180095A20;
    }
  }
  CurrentUserSid = -2147024882;
  v19 = (CAce *)operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
  nDestinationSidLength = v19;
  v21 = v19;
  if ( !v19 )
    goto LABEL_11;
  *(_QWORD *)v19 = 0x80000;
  *((_QWORD *)v19 + 1) = 0;
  *((_QWORD *)v19 + 2) = 0;
  *((_QWORD *)v19 + 3) = 0;
  if ( !v12 )
  {
    CurrentUserSid = -2147024809;
    CAce::`scalar deleting destructor'(v19, v20);
    goto LABEL_11;
  }
  LengthSid = GetLengthSid(v12);
  v23 = hMem;
  CurrentUserSid = -2147024809;
  v24 = LengthSid;
  *((_QWORD *)v21 + 1) = 0;
  if ( !IsValidSid(v23) )
    goto LABEL_29;
  LODWORD(nDestinationSidLength) = GetLengthSid(hMem);
  CurrentUserSid = -2147024882;
  v26 = LocalAlloc(0x40u, (unsigned int)nDestinationSidLength);
  v58 = v26;
  if ( !v26 )
    goto LABEL_29;
  if ( !CopySid((DWORD)nDestinationSidLength, v26, hMem) )
  {
    CurrentUserSid = ResultFromKnownLastError();
    if ( CurrentUserSid >= 0 )
      goto LABEL_34;
    LocalFree(v58);
    goto LABEL_30;
  }
  CurrentUserSid = 0;
LABEL_34:
  *((_QWORD *)v21 + 1) = v58;
  *(_WORD *)v21 = 768;
  *((_WORD *)v21 + 1) = v24 + 8;
  *((_DWORD *)v21 + 1) = 2032127;
  RtlMapGenericMask((PACCESS_MASK)v21 + 1, (PGENERIC_MAPPING)&GenericMapping);
  v27 = *(_BYTE *)v21;
  v28 = 0x80000000;
  *((_DWORD *)v21 + 7) = 0x80000000;
  if ( !v27 || v27 == 9 )
  {
    *((_DWORD *)v21 + 7) = -2147483647;
    v28 = -2147483647;
  }
  if ( (*((_BYTE *)v21 + 1) & 0x10) != 0 )
  {
    *((_DWORD *)v21 + 7) = v28 | 0x20;
    goto LABEL_38;
  }
LABEL_29:
  if ( CurrentUserSid < 0 )
  {
LABEL_30:
    v12 = hMem;
    CAce::`scalar deleting destructor'(v21, v25);
    goto LABEL_11;
  }
LABEL_38:
  v29 = (unsigned int (__fastcall *)(__int64, __int64, CAce *))qword_1800959F8;
  v30 = *((_QWORD *)v6 + 1);
  if ( qword_1800959F8 == -1 )
  {
    GetProcFromComCtl32(&qword_1800959F8, 334);
    v29 = (unsigned int (__fastcall *)(__int64, __int64, CAce *))qword_1800959F8;
  }
  if ( !v29 || v29(v30, 0x7FFFFFFF, v21) == -1 )
  {
    CurrentUserSid = -2147024882;
    if ( v21 )
      CAce::`scalar deleting destructor'(v21, v25);
    goto LABEL_10;
  }
  v12 = hMem;
LABEL_43:
  LODWORD(nDestinationSidLength) = 68;
  v31 = LocalAlloc(0x40u, 0x44u);
  v32 = v31;
  if ( !v31 )
  {
    CurrentUserSid = -2147024882;
    goto LABEL_108;
  }
  if ( !CreateWellKnownSid(WinLocalSystemSid, 0, v31, (DWORD *)&nDestinationSidLength) )
  {
    CurrentUserSid = ResultFromKnownLastError();
    if ( CurrentUserSid < 0 )
    {
LABEL_108:
      v51 = v12;
LABEL_78:
      LocalFree(v51);
      goto LABEL_5;
    }
  }
  v33 = (int *)*((_QWORD *)v6 + 1);
  if ( v33 )
    v34 = *v33;
  else
    v34 = 0;
  v35 = (FARPROC)qword_180095A20;
  for ( j = 0; j < v34; ++j )
  {
    v37 = *((_QWORD *)v6 + 1);
    if ( v35 == (FARPROC)-1LL )
    {
      if ( !g_hinstCC )
      {
        DelayLoadCC();
        if ( !g_hinstCC )
        {
          v35 = 0;
          qword_180095A20 = 0;
LABEL_94:
          v38 = 0;
          goto LABEL_52;
        }
      }
      v35 = GetProcAddress(g_hinstCC, (LPCSTR)0x14C);
      qword_180095A20 = (__int64 (__fastcall *)(_QWORD, _QWORD))v35;
    }
    if ( !v35 )
      goto LABEL_94;
    v38 = ((__int64 (__fastcall *)(__int64, _QWORD))v35)(v37, j);
    v35 = (FARPROC)qword_180095A20;
LABEL_52:
    if ( !*(_DWORD *)(v38 + 24) && *(_BYTE *)(v38 + 1) == 3 )
    {
      if ( EqualSid(*(PSID *)(v38 + 8), v32) )
      {
        CurrentUserSid = 0;
        *(_DWORD *)(v38 + 4) = 2032127;
        goto LABEL_73;
      }
      v35 = (FARPROC)qword_180095A20;
    }
  }
  CurrentUserSid = -2147024882;
  v39 = operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
  v58 = v39;
  v40 = v39;
  if ( !v39 )
    goto LABEL_73;
  *v39 = 0x80000;
  v39[1] = 0;
  v39[2] = 0;
  v39[3] = 0;
  v41 = GetLengthSid(v32);
  v40[1] = 0;
  v42 = v41;
  CurrentUserSid = -2147024809;
  if ( !IsValidSid(v32) )
    goto LABEL_59;
  LODWORD(v58) = GetLengthSid(v32);
  CurrentUserSid = -2147024882;
  v44 = LocalAlloc(0x40u, (unsigned int)v58);
  v56 = v44;
  if ( !v44 )
    goto LABEL_59;
  if ( !CopySid((DWORD)v58, v44, v32) )
  {
    CurrentUserSid = ResultFromKnownLastError();
    if ( CurrentUserSid >= 0 )
      goto LABEL_64;
    LocalFree(v56);
    goto LABEL_60;
  }
  CurrentUserSid = 0;
LABEL_64:
  v40[1] = v56;
  *(_WORD *)v40 = 768;
  *((_WORD *)v40 + 1) = v42 + 8;
  *((_DWORD *)v40 + 1) = 2032127;
  RtlMapGenericMask((PACCESS_MASK)v40 + 1, (PGENERIC_MAPPING)&GenericMapping);
  v45 = *(_BYTE *)v40;
  *((_DWORD *)v40 + 7) = 0x80000000;
  if ( !v45 || v45 == 9 )
  {
    *((_DWORD *)v40 + 7) = -2147483647;
    v46 = -2147483647;
  }
  else
  {
    v46 = 0x80000000;
  }
  if ( (*((_BYTE *)v40 + 1) & 0x10) == 0 )
  {
LABEL_59:
    if ( CurrentUserSid >= 0 )
      goto LABEL_68;
    goto LABEL_60;
  }
  *((_DWORD *)v40 + 7) = v46 | 0x20;
LABEL_68:
  v47 = (unsigned int (__fastcall *)(__int64, __int64, _QWORD *))qword_1800959F8;
  v48 = *((_QWORD *)v6 + 1);
  if ( qword_1800959F8 == -1 )
  {
    GetProcFromComCtl32(&qword_1800959F8, 334);
    v47 = (unsigned int (__fastcall *)(__int64, __int64, _QWORD *))qword_1800959F8;
  }
  if ( v47 && v47(v48, 0x7FFFFFFF, v40) != -1 )
  {
    CurrentUserSid = 0;
    goto LABEL_73;
  }
  CurrentUserSid = -2147024882;
  if ( v40 )
LABEL_60:
    CAce::`scalar deleting destructor'((CAce *)v40, v43);
LABEL_73:
  LocalFree(v32);
  if ( CurrentUserSid >= 0 )
  {
    LODWORD(nDestinationSidLength) = 68;
    v49 = LocalAlloc(0x40u, 0x44u);
    v50 = v49;
    if ( !v49 )
    {
      CurrentUserSid = -2147024882;
      goto LABEL_77;
    }
    if ( !CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, v49, (DWORD *)&nDestinationSidLength) )
    {
      CurrentUserSid = ResultFromKnownLastError();
      if ( CurrentUserSid < 0 )
      {
LABEL_77:
        v51 = hMem;
        goto LABEL_78;
      }
    }
    CurrentUserSid = CAceList::SetExplicitAllowAce(v6, v50, 0x1F01FFu, 3u);
    LocalFree(v50);
  }
LABEL_10:
  v12 = hMem;
LABEL_11:
  LocalFree(v12);
  if ( CurrentUserSid < 0 )
    goto LABEL_5;
  *a2 = v6;
  return (unsigned int)CurrentUserSid;
}

```

## disassembly

```asm
0x180009c50  push    rbx
0x180009c52  push    rbp
0x180009c53  push    rsi
0x180009c54  push    rdi
0x180009c55  push    r12
0x180009c57  push    r14
0x180009c59  push    r15
0x180009c5b  sub     rsp, 30h
0x180009c5f  mov     rbx, [rcx+38h]
0x180009c63  mov     r15, rdx
0x180009c66  mov     ecx, 20h ; ' '; unsigned __int64
0x180009c6b  test    rbx, rbx
0x180009c6e  jnz     loc_180009CF4
0x180009c74  mov     r12d, 8007000Eh
0x180009c7a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009c81  mov     ebx, r12d
0x180009c84  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180009c89  mov     [rsp+68h+nDestinationSidLength], rax
0x180009c8e  mov     rsi, rax
0x180009c91  test    rax, rax
0x180009c94  jz      loc_180009D68
0x180009c9a  xor     edi, edi
0x180009c9c  mov     rcx, rax; this
0x180009c9f  mov     [rax], rdi
0x180009ca2  mov     [rax+8], rdi
0x180009ca6  mov     [rax+10h], rdi
0x180009caa  mov     qword ptr [rax+18h], 1
0x180009cb2  call    ?_Init@CAceList@@AEAAJXZ; CAceList::_Init(void)
0x180009cb7  mov     ebx, eax
0x180009cb9  test    eax, eax
0x180009cbb  js      loc_18000A3AD
0x180009cc1  lea     rcx, [rsp+68h+hMem]; void **
0x180009cc9  mov     [rsp+68h+arg_8], r13
0x180009cce  mov     [rsp+68h+hMem], rdi
0x180009cd6  call    ?GetCurrentUserSid@@YAJPEAPEAX@Z; GetCurrentUserSid(void * *)
0x180009cdb  mov     ebx, eax
0x180009cdd  test    eax, eax
0x180009cdf  jns     loc_180009D79
0x180009ce5  test    rsi, rsi
0x180009ce8  jz      short loc_180009D63
0x180009cea  mov     rcx, rsi; this
0x180009ced  call    ??_GCAceList@@QEAAPEAXI@Z; CAceList::`scalar deleting destructor'(uint)
0x180009cf2  jmp     short loc_180009D63
0x180009cf4  xor     edi, edi
0x180009cf6  mov     ebp, 8007000Eh
0x180009cfb  mov     [rdx], rdi
0x180009cfe  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009d05  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180009d0a  mov     [rsp+68h+nDestinationSidLength], rax
0x180009d0f  mov     rsi, rax
0x180009d12  test    rax, rax
0x180009d15  jnz     loc_18000A3BA
0x180009d1b  mov     eax, ebp
0x180009d1d  add     rsp, 30h
0x180009d21  pop     r15
0x180009d23  pop     r14
0x180009d25  pop     r12
0x180009d27  pop     rdi
0x180009d28  pop     rsi
0x180009d29  pop     rbp
0x180009d2a  pop     rbx
0x180009d2b  retn
0x180009d2c  mov     r9b, 3; unsigned __int8
0x180009d2f  mov     r8d, 1F01FFh; unsigned int
0x180009d35  mov     rdx, rdi; void *
0x180009d38  mov     rcx, rsi; this
0x180009d3b  call    ?SetExplicitAllowAce@CAceList@@QEAAJPEAXKE@Z; CAceList::SetExplicitAllowAce(void *,ulong,uchar)
0x180009d40  mov     rcx, rdi; hMem
0x180009d43  mov     ebx, eax
0x180009d45  call    cs:__imp_LocalFree
0x180009d4b  mov     r13, [rsp+68h+hMem]
0x180009d53  mov     rcx, r13; hMem
0x180009d56  call    cs:__imp_LocalFree
0x180009d5c  test    ebx, ebx
0x180009d5e  js      short loc_180009CE5
0x180009d60  mov     [r15], rsi
0x180009d63  mov     r13, [rsp+68h+arg_8]
0x180009d68  mov     eax, ebx
0x180009d6a  add     rsp, 30h
0x180009d6e  pop     r15
0x180009d70  pop     r14
0x180009d72  pop     r12
0x180009d74  pop     rdi
0x180009d75  pop     rsi
0x180009d76  pop     rbp
0x180009d77  pop     rbx
0x180009d78  retn
0x180009d79  mov     rax, [rsi+8]
0x180009d7d  mov     r13, [rsp+68h+hMem]
0x180009d85  test    rax, rax
0x180009d88  jz      loc_18000A312
0x180009d8e  mov     r14d, [rax]
0x180009d91  mov     rax, cs:qword_180095A20
0x180009d98  mov     ebx, edi
0x180009d9a  cmp     ebx, r14d
0x180009d9d  jge     short loc_180009DF6
0x180009d9f  mov     rbp, [rsi+8]
0x180009da3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180009da7  jz      loc_18000A231
0x180009dad  test    rax, rax
0x180009db0  jz      loc_18000A2A5
0x180009db6  movsxd  rdx, ebx
0x180009db9  mov     rcx, rbp
0x180009dbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009dc1  mov     rbp, rax
0x180009dc4  mov     rax, cs:qword_180095A20
0x180009dcb  cmp     [rbp+18h], edi
0x180009dce  jnz     short loc_180009DF2
0x180009dd0  cmp     byte ptr [rbp+1], 3
0x180009dd4  jnz     short loc_180009DF2
0x180009dd6  mov     rcx, [rbp+8]; pSid1
0x180009dda  mov     rdx, r13; pSid2
0x180009ddd  call    cs:__imp_EqualSid
0x180009de3  test    eax, eax
0x180009de5  jnz     loc_18000A216
0x180009deb  mov     rax, cs:qword_180095A20
0x180009df2  inc     ebx
0x180009df4  jmp     short loc_180009D9A
0x180009df6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009dfd  mov     ecx, 20h ; ' '; unsigned __int64
0x180009e02  mov     ebx, r12d
0x180009e05  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180009e0a  mov     [rsp+68h+nDestinationSidLength], rax
0x180009e0f  mov     r14, rax
0x180009e12  test    rax, rax
0x180009e15  jz      loc_180009D53
0x180009e1b  mov     qword ptr [rax], 80000h
0x180009e22  mov     [rax+8], rdi
0x180009e26  mov     [rax+10h], rdi
0x180009e2a  mov     [rax+18h], rdi
0x180009e2e  test    r13, r13
0x180009e31  jz      loc_18000A300
0x180009e37  mov     rcx, r13; pSid
0x180009e3a  call    cs:__imp_GetLengthSid
0x180009e40  mov     rcx, [rsp+68h+hMem]; pSid
0x180009e48  mov     ebx, 80070057h
0x180009e4d  mov     r13d, eax
0x180009e50  mov     [r14+8], rdi
0x180009e54  call    cs:__imp_IsValidSid
0x180009e5a  test    eax, eax
0x180009e5c  jnz     short loc_180009E7B
0x180009e5e  test    ebx, ebx
0x180009e60  jns     loc_180009F32
0x180009e66  mov     r13, [rsp+68h+hMem]
0x180009e6e  mov     rcx, r14; this
0x180009e71  call    ??_GCAce@@QEAAPEAXI@Z; CAce::`scalar deleting destructor'(uint)
0x180009e76  jmp     loc_180009D53
0x180009e7b  mov     rcx, [rsp+68h+hMem]; pSid
0x180009e83  call    cs:__imp_GetLengthSid
0x180009e89  mov     edx, eax; uBytes
0x180009e8b  mov     ecx, 40h ; '@'; uFlags
0x180009e90  mov     dword ptr [rsp+68h+nDestinationSidLength], eax
0x180009e94  mov     ebx, r12d
0x180009e97  call    cs:__imp_LocalAlloc
0x180009e9d  mov     [rsp+68h+arg_10], rax
0x180009ea5  test    rax, rax
0x180009ea8  jz      short loc_180009E5E
0x180009eaa  mov     r8, [rsp+68h+hMem]; pSourceSid
0x180009eb2  mov     rdx, rax; pDestinationSid
0x180009eb5  mov     ecx, dword ptr [rsp+68h+nDestinationSidLength]; nDestinationSidLength
0x180009eb9  call    cs:__imp_CopySid
0x180009ebf  test    eax, eax
0x180009ec1  jz      loc_18000A2BF
0x180009ec7  mov     ebx, edi
0x180009ec9  mov     rcx, [rsp+68h+arg_10]
0x180009ed1  lea     rdx, GenericMapping; GenericMapping
0x180009ed8  mov     [r14+8], rcx
0x180009edc  add     r13w, 8
0x180009ee1  lea     rcx, [r14+4]; AccessMask
0x180009ee5  mov     word ptr [r14], 300h
0x180009eeb  mov     [r14+2], r13w
0x180009ef0  mov     dword ptr [r14+4], 1F01FFh
0x180009ef8  call    cs:__imp_RtlMapGenericMask
0x180009efe  movzx   ecx, byte ptr [r14]
0x180009f02  mov     eax, 80000000h
0x180009f07  mov     [r14+1Ch], eax
0x180009f0b  test    cl, cl
0x180009f0d  jnz     loc_18000A1F6
0x180009f13  mov     dword ptr [r14+1Ch], 80000001h
0x180009f1b  mov     eax, 80000001h
0x180009f20  test    byte ptr [r14+1], 10h
0x180009f25  jz      loc_180009E5E
0x180009f2b  or      eax, 20h
0x180009f2e  mov     [r14+1Ch], eax
0x180009f32  mov     rax, cs:qword_1800959F8
0x180009f39  mov     rbx, [rsi+8]
0x180009f3d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180009f41  jz      loc_18000A31A
0x180009f47  test    rax, rax
0x180009f4a  jz      loc_18000A394
0x180009f50  mov     r8, r14
0x180009f53  mov     edx, 7FFFFFFFh
0x180009f58  mov     rcx, rbx
0x180009f5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f60  cmp     eax, 0FFFFFFFFh
0x180009f63  jz      loc_18000A394
0x180009f69  mov     r13, [rsp+68h+hMem]
0x180009f71  mov     edx, 44h ; 'D'; uBytes
0x180009f76  mov     dword ptr [rsp+68h+nDestinationSidLength], 44h ; 'D'
0x180009f7e  mov     ecx, 40h ; '@'; uFlags
0x180009f83  call    cs:__imp_LocalAlloc
0x180009f89  mov     rbp, rax
0x180009f8c  test    rax, rax
0x180009f8f  jz      loc_18000A389
0x180009f95  lea     r9, [rsp+68h+nDestinationSidLength]; cbSid
0x180009f9a  mov     r8, rax; pSid
0x180009f9d  xor     edx, edx; DomainSid
0x180009f9f  mov     ecx, 16h; WellKnownSidType
0x180009fa4  call    cs:__imp_CreateWellKnownSid
0x180009faa  test    eax, eax
0x180009fac  jz      loc_18000A337
0x180009fb2  mov     rax, [rsi+8]
0x180009fb6  test    rax, rax
0x180009fb9  jz      loc_18000A347
0x180009fbf  mov     r13d, [rax]
0x180009fc2  mov     rax, cs:qword_180095A20
0x180009fc9  mov     ebx, edi
0x180009fcb  cmp     ebx, r13d
0x180009fce  jge     short loc_18000A029
0x180009fd0  mov     r14, [rsi+8]
0x180009fd4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180009fd8  jz      loc_18000A266
0x180009fde  test    rax, rax
0x180009fe1  jz      loc_18000A2B7
0x180009fe7  movsxd  rdx, ebx
0x180009fea  mov     rcx, r14
0x180009fed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ff2  mov     r14, rax
0x180009ff5  mov     rax, cs:qword_180095A20
0x180009ffc  cmp     [r14+18h], edi
0x18000a000  jnz     short loc_18000A025
0x18000a002  cmp     byte ptr [r14+1], 3
0x18000a007  jnz     short loc_18000A025
0x18000a009  mov     rcx, [r14+8]; pSid1
0x18000a00d  mov     rdx, rbp; pSid2
0x18000a010  call    cs:__imp_EqualSid
0x18000a016  test    eax, eax
0x18000a018  jnz     loc_18000A222
0x18000a01e  mov     rax, cs:qword_180095A20
0x18000a025  inc     ebx
0x18000a027  jmp     short loc_180009FCB
0x18000a029  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a030  mov     ecx, 20h ; ' '; unsigned __int64
0x18000a035  mov     ebx, r12d
0x18000a038  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000a03d  mov     [rsp+68h+arg_10], rax
0x18000a045  mov     r14, rax
0x18000a048  test    rax, rax
0x18000a04b  jz      loc_18000A182
0x18000a051  mov     rcx, rbp; pSid
0x18000a054  mov     qword ptr [rax], 80000h
0x18000a05b  mov     [rax+8], rdi
0x18000a05f  mov     [rax+10h], rdi
0x18000a063  mov     [rax+18h], rdi
0x18000a067  call    cs:__imp_GetLengthSid
0x18000a06d  mov     rcx, rbp; pSid
0x18000a070  mov     [r14+8], rdi
0x18000a074  mov     r12d, eax
0x18000a077  mov     ebx, 80070057h
0x18000a07c  call    cs:__imp_IsValidSid
0x18000a082  test    eax, eax
0x18000a084  jnz     short loc_18000A09B
0x18000a086  test    ebx, ebx
0x18000a088  jns     loc_18000A149
0x18000a08e  mov     rcx, r14; this
0x18000a091  call    ??_GCAce@@QEAAPEAXI@Z; CAce::`scalar deleting destructor'(uint)
0x18000a096  jmp     loc_18000A182
0x18000a09b  mov     rcx, rbp; pSid
0x18000a09e  call    cs:__imp_GetLengthSid
0x18000a0a4  mov     edx, eax; uBytes
0x18000a0a6  mov     ecx, 40h ; '@'; uFlags
0x18000a0ab  mov     dword ptr [rsp+68h+arg_10], eax
0x18000a0b2  mov     ebx, 8007000Eh
0x18000a0b7  call    cs:__imp_LocalAlloc
0x18000a0bd  mov     [rsp+68h+var_48], rax
0x18000a0c2  test    rax, rax
0x18000a0c5  jz      short loc_18000A086
0x18000a0c7  mov     ecx, dword ptr [rsp+68h+arg_10]; nDestinationSidLength
0x18000a0ce  mov     r8, rbp; pSourceSid
0x18000a0d1  mov     rdx, rax; pDestinationSid
0x18000a0d4  call    cs:__imp_CopySid
0x18000a0da  test    eax, eax
0x18000a0dc  jz      loc_18000A2E1
0x18000a0e2  mov     ebx, edi
0x18000a0e4  mov     rcx, [rsp+68h+var_48]
0x18000a0e9  lea     rdx, GenericMapping; GenericMapping
0x18000a0f0  mov     [r14+8], rcx
0x18000a0f4  add     r12w, 8
0x18000a0f9  lea     rcx, [r14+4]; AccessMask
0x18000a0fd  mov     word ptr [r14], 300h
0x18000a103  mov     [r14+2], r12w
0x18000a108  mov     dword ptr [r14+4], 1F01FFh
0x18000a110  call    cs:__imp_RtlMapGenericMask
0x18000a116  movzx   eax, byte ptr [r14]
0x18000a11a  mov     dword ptr [r14+1Ch], 80000000h
0x18000a122  test    al, al
0x18000a124  jnz     loc_18000A204
0x18000a12a  mov     dword ptr [r14+1Ch], 80000001h
0x18000a132  mov     eax, 80000001h
0x18000a137  test    byte ptr [r14+1], 10h
  ... truncated ...
```
