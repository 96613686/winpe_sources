# CPubDocFile::Commit(ulong)

- ea: `0x18000745c`
- end: `0x180007edc`
- name: `?Commit@CPubDocFile@@QEAAJK@Z`
- size: `2688`
- prototype: `__int64 __fastcall(CPubDocFile *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `24`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006d80`
- `0x180007310`

## callees

- `0x180005080`
- `0x18000576c`
- `0x180005cf8`
- `0x1800061b0`
- `0x180006718`
- `0x180006a7c`
- `0x180006f34`
- `0x180007210`
- `0x18000745c`
- `0x180007ee4`
- `0x180008a38`
- `0x18000c378`
- `0x18001b4c4`
- `0x18001bb24`
- `0x180036734`
- `0x1800373b4`
- `0x180039158`
- `0x1800397c4`
- `0x18003ab9c`
- `0x180040d28`
- `0x180042800`
- `0x180043100`
- `0x180060ef0`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180007810`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180007810`

## pseudocode

```c
__int64 __fastcall CPubDocFile::Commit(CPubDocFile *this, unsigned int a2)
{
  unsigned int v4; // r12d
  unsigned int v5; // r15d
  int TOD; // edi
  __int64 v7; // rdx
  CMStream *v8; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rdx
  CMStream *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rsi
  __int64 v20; // rdx
  PTSetMember *v21; // rsi
  unsigned int *v22; // rdx
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int16 v25; // ax
  __int64 v26; // rax
  int v27; // eax
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // rdx
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // rdx
  CMStream *v34; // rcx
  __int64 v35; // rdx
  PTSetMember *v36; // rsi
  __int64 v37; // rdx
  __int64 v38; // rcx
  __int64 v39; // rdx
  __int64 v40; // rdx
  CPubDocFile *v41; // rcx
  __int64 v42; // rcx
  __int64 v43; // rdx
  __int64 v44; // rcx
  __int64 v45; // rdx
  __int64 v46; // rcx
  __int64 v47; // rdx
  __int64 v48; // rcx
  unsigned __int64 v49; // rdx
  __int64 v50; // r8
  __int64 v51; // rcx
  __int64 v52; // r8
  unsigned __int64 v53; // rdx
  __int64 v54; // rcx
  __int64 v55; // rdx
  __int64 v56; // rdx
  CMStream *v57; // rcx
  __int64 v58; // r8
  __int64 v59; // rcx
  __int64 v60; // rdx
  __int64 v61; // rcx
  __int64 v62; // rdx
  CPubDocFile *v63; // rcx
  unsigned int v64; // [rsp+20h] [rbp-A9h] BYREF
  unsigned int v65; // [rsp+24h] [rbp-A5h] BYREF
  struct _FILETIME FileTime; // [rsp+28h] [rbp-A1h] BYREF
  _BYTE v67[16]; // [rsp+30h] [rbp-99h] BYREF
  unsigned __int64 v68; // [rsp+40h] [rbp-89h]
  _BYTE v69[16]; // [rsp+80h] [rbp-49h] BYREF
  unsigned __int64 v70; // [rsp+90h] [rbp-39h]

  FileTime = 0;
  v65 = 0;
  v64 = 0;
  v4 = 0;
  v5 = 0;
  memset_0(v67, 0, 0x50u);
  memset_0(v69, 0, 0x50u);
  if ( (*((_BYTE *)this + 20) & 0x20) != 0 )
    return (unsigned int)-2147286782;
  if ( *((char *)this + 20) >= 0 )
    return (unsigned int)-2147287035;
  if ( (*((_BYTE *)this + 138) & 1) != 0 )
  {
    TOD = DfGetTOD(&FileTime);
    if ( TOD < 0 )
      return (unsigned int)TOD;
    v10 = *((_QWORD *)this + 15);
    v11 = v10 ? v10 + *(_QWORD *)NtCurrentTeb()->ReservedForOle : 0LL;
    TOD = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))PTimeEntry::SetTime)(v11, 1, FileTime);
    if ( TOD < 0 )
      return (unsigned int)TOD;
  }
  if ( (*((_DWORD *)this + 5) & 0x40000) != 0 && (a2 & 1) != 0 )
    return (unsigned int)-2147286785;
  TOD = CPubDocFile::FlushBufferedData(this, 0);
  if ( TOD < 0 )
    return (unsigned int)TOD;
  if ( (*((_BYTE *)this + 20) & 2) != 0 )
  {
    if ( *((_WORD *)this + 68) != 1 )
      goto LABEL_37;
    v12 = *((_QWORD *)this + 20);
    if ( v12 )
      v13 = v12 + *(_QWORD *)NtCurrentTeb()->ReservedForOle;
    else
      v13 = 0;
    if ( (*(_BYTE *)(v13 + 80) & 4) != 0 )
    {
      if ( v12 )
        v42 = v12 + *(_QWORD *)NtCurrentTeb()->ReservedForOle;
      else
        v42 = 0;
      TOD = StgpWaitForAccessLocks(*(struct ILockBytes **)(v42 + 48), 0x80u, &v65);
      if ( TOD < 0 )
        return (unsigned int)TOD;
      v4 = v65;
    }
    v14 = *((_QWORD *)this + 18);
    if ( v14 )
      v15 = (CMStream *)(v14 + *(_QWORD *)NtCurrentTeb()->ReservedForOle);
    else
      v15 = 0;
    TOD = CMStream::BeginCopyOnWrite(v15, a2);
    if ( TOD < 0 )
    {
LABEL_83:
      if ( v4 )
      {
        v37 = *((_QWORD *)this + 20);
        if ( v37 )
          v38 = v37 + *(_QWORD *)NtCurrentTeb()->ReservedForOle;
        else
          v38 = 0;
        StgpReleaseAccessLocks(*(struct ILockBytes **)(v38 + 48), 0x80u, v4);
      }
      return (unsigned int)TOD;
    }
    if ( (a2 & 1) == 0 || (TOD = CPubDocFile::PrepareForOverwrite(this), TOD >= 0) )
    {
      if ( (*((_DWORD *)this + 5) & 0x40004) == 0 )
        goto LABEL_37;
      if ( *((_DWORD *)this + 38) == -1 )
      {
        if ( (a2 & 2) != 0 )
        {
          v16 = *((_QWORD *)this + 20);
          v17 = v16 ? v16 + *(_QWORD *)NtCurrentTeb()->ReservedForOle : 0LL;
          if ( !(unsigned int)DllIsMultiStream(*(struct ILockBytes **)(v17 + 48)) )
            goto LABEL_36;
        }
        goto LABEL_37;
      }
      v43 = *((_QWORD *)this + 20);
      if ( v43 )
        v44 = v43 + *(_QWORD *)NtCurrentTeb()->ReservedForOle;
      else
        v44 = 0;
      TOD = DllGetCommitSig(*(struct ILockBytes **)(v44 + 48), &v64);
      if ( TOD >= 0 )
      {
        v5 = v64;
        if ( (a2 & 2) != 0 && v64 != *((_DWORD *)this + 38) )
        {
LABEL_36:
          TOD = -2147286783;
          goto LABEL_82;
        }
LABEL_37:
        v18 = *((_QWORD *)this + 13);
        if ( v18 )
          goto LABEL_65;
        v19 = 0;
        while ( v19 )
        {
          if ( *(_WORD *)(v19 + 94) == 1 )
          {
            v27 = CWrappedDocFile::BeginCommit((CWrappedDocFile *)(v19 - 16), v18);
          }
          else
          {
            if ( *(_WORD *)(v19 + 94) != 2 )
            {
              TOD = -2147287039;
              goto LABEL_80;
            }
            v27 = CTransactedStream::BeginCommit((CTransactedStream *)(v19 - 16), v18);
          }
          TOD = v27;
          if ( v27 < 0 )
            goto LABEL_80;
          v18 = *(_QWORD *)(v19 + 8);
          if ( v18 )
LABEL_65:
            v19 = v18 + *(_QWORD *)NtCurrentTeb()->ReservedForOle;
          else
            v19 = 0;
        }
        if ( (*((_BYTE *)this + 20) & 4) == 0 )
          goto LABEL_176;
        v45 = *((_QWORD *)this + 20);
        v46 = v45 ? v45 + *(_QWORD *)NtCurrentTeb()->ReservedForOle : 0LL;
        TOD = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(v46 + 32) + 72LL))(*(_QWORD *)(v46 + 32), v67);
        if ( TOD >= 0 )
        {
          v47 = *((_QWORD *)this + 20);
          v48 = v47 ? v47 + *(_QWORD *)NtCurrentTeb()->ReservedForOle : 0LL;
          TOD = (*(__int64 (__fastcall **)(_QWORD, _BYTE *, __int64))(**(_QWORD **)(v48 + 48) + 72LL))(
                  *(_QWORD *)(v48 + 48),
                  v69,
                  1);
          if ( TOD >= 0 )
          {
            v49 = v68;
            if ( v68 <= v70
              || ((v50 = *((_QWORD *)this + 20)) == 0
                ? (v51 = 0)
                : (v49 = v68, v51 = v50 + *(_QWORD *)NtCurrentTeb()->ReservedForOle),
                  TOD = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64))(**(_QWORD **)(v51 + 48) + 48LL))(
                          *(_QWORD *)(v51 + 48),
                          v49),
                  TOD >= 0) )
            {
LABEL_176:
              if ( *((_WORD *)this + 68) != 1
                || ((v33 = *((_QWORD *)this + 18)) == 0
                  ? (v34 = 0)
                  : (v34 = (CMStream *)(v33 + *(_QWORD *)NtCurrentTeb()->ReservedForOle)),
                    TOD = CMStream::EndCopyOnWrite(v34, a2, 8u),
                    TOD >= 0) )
              {
                v20 = *((_QWORD *)this + 13);
                if ( v20 )
                {
                  v21 = (PTSetMember *)(v20 + *(_QWORD *)NtCurrentTeb()->ReservedForOle);
                  if ( v21 )
                  {
                    while ( 1 )
                    {
                      v39 = *((_QWORD *)v21 + 1);
                      if ( !v39 )
                        break;
                      if ( v39 + *(_QWORD *)NtCurrentTeb()->ReservedForOle )
                      {
                        v21 = (PTSetMember *)(v39 + *(_QWORD *)NtCurrentTeb()->ReservedForOle);
                        if ( v21 )
                          continue;
                      }
                      if ( !v21 )
                        goto LABEL_44;
                      goto LABEL_101;
                    }
                    do
                    {
LABEL_101:
                      PTSetMember::EndCommit(v21, 8u);
                      if ( !*(_QWORD *)v21 )
                        break;
                      v21 = (PTSetMember *)(*(_QWORD *)v21 + *(_QWORD *)NtCurrentTeb()->ReservedForOle);
                    }
                    while ( v21 );
                  }
                }
LABEL_44:
                CPubDocFile::RemoveUnnecessaryXSMembers(this);
                if ( (a2 & 8) != 0 )
                  TOD = CPubDocFile::Consolidate(this, a2);
                if ( (*((_BYTE *)this + 20) & 4) != 0 )
                {
                  v28 = *((_QWORD *)this + 20);
                  if ( v28 )
                    v29 = v28 + *(_QWORD *)NtCurrentTeb()->ReservedForOle;
                  else
                    v29 = 0;
                  if ( v28 )
                    v30 = *(_QWORD *)NtCurrentTeb()->ReservedForOle + v28;
                  else
                    v30 = 0;
                  CPubDocFile::CopyLStreamToLStream(
                    this,
                    *(struct ILockBytes **)(v30 + 32),
                    *(struct ILockBytes **)(v29 + 48));
                  v31 = *((_QWORD *)this + 20);
                  if ( v31 )
                    v32 = v31 + *(_QWORD *)NtCurrentTeb()->ReservedForOle;
                  else
                    v32 = 0;
                  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v32 + 48) + 40LL))(*(_QWORD *)(v32 + 48));
                }
                if ( (*((_DWORD *)this + 5) & 0x40004) != 0 )
                {
                  v22 = (unsigned int *)((char *)this + 152);
                  if ( *((_DWORD *)this + 38) == -1 )
                  {
                    v58 = *((_QWORD *)this + 20);
                    if ( v58 )
                      v59 = v58 + *(_QWORD *)NtCurrentTeb()->ReservedForOle;
                    else
                      v59 = 0;
                    DllGetCommitSig(*(struct ILockBytes **)(v59 + 48), v22);
                  }
                  else
                  {
                    *v22 = v5 + 1;
                    v23 = *((_QWORD *)this + 20);
                    if ( v23 )
                      v24 = v23 + *(_QWORD *)NtCurrentTeb()->ReservedForOle;
                    else
                      v24 = 0;
                    DllSetCommitSig(*(struct ILockBytes **)(v24 + 48), v5 + 1);
                  }
                }
                if ( v4 )
                {
                  v60 = *((_QWORD *)this + 20);
                  if ( v60 )
                    v61 = v60 + *(_QWORD *)NtCurrentTeb()->ReservedForOle;
                  else
                    v61 = 0;
                  StgpReleaseAccessLocks(*(struct ILockBytes **)(v61 + 48), 0x80u, v4);
                }
                v25 = *((_WORD *)this + 69);
                if ( (v25 & 1) != 0 )
                {
                  if ( !(unsigned int)CPubDocFile::IsRoot(this) )
                  {
                    v62 = *((_QWORD *)this + 14);
                    if ( v62 )
                      v63 = (CPubDocFile *)(v62 + *(_QWORD *)NtCurrentTeb()->ReservedForOle);
                    else
                      v63 = 0;
                    CPubDocFile::SetDirty(v63);
                  }
                  v25 = *((_WORD *)this + 69) & 0xFFFE;
                }
                *((_WORD *)this + 69) = v25 & 0xFFFD;
                v26 = *(_QWORD *)this - *(_QWORD *)&GUID_33c83c10_d239_4c83_98b3_9f2621c2df7f.Data1;
                if ( *(_QWORD *)this == *(_QWORD *)&GUID_33c83c10_d239_4c83_98b3_9f2621c2df7f.Data1 )
                  v26 = *((_QWORD *)this + 1) - *(_QWORD *)GUID_33c83c10_d239_4c83_98b3_9f2621c2df7f.Data4;
                if ( !v26 && (*((_DWORD *)this + 5) & 0x4002) == 0x4002 )
                  GetSystemTimeAsFileTime((LPFILETIME)this + 23);
                return (unsigned int)TOD;
              }
              if ( (*((_BYTE *)this + 20) & 4) != 0 )
              {
                v53 = v70;
                if ( v68 > v70 )
                {
                  v52 = *((_QWORD *)this + 20);
                  if ( v52 )
                  {
                    v53 = v70;
                    v54 = v52 + *(_QWORD *)NtCurrentTeb()->ReservedForOle;
                  }
                  else
                  {
                    v54 = 0;
                  }
                  (*(void (__fastcall **)(_QWORD, unsigned __int64))(**(_QWORD **)(v54 + 48) + 48LL))(
                    *(_QWORD *)(v54 + 48),
                    v53);
                }
              }
            }
          }
        }
LABEL_80:
        v35 = *((_QWORD *)this + 13);
        if ( v35 )
        {
          v36 = (PTSetMember *)(v35 + *(_QWORD *)NtCurrentTeb()->ReservedForOle);
          if ( v36 )
          {
            while ( 1 )
            {
              v55 = *((_QWORD *)v36 + 1);
              if ( !v55 )
                break;
              if ( v55 + *(_QWORD *)NtCurrentTeb()->ReservedForOle )
              {
                v36 = (PTSetMember *)(v55 + *(_QWORD *)NtCurrentTeb()->ReservedForOle);
                if ( v36 )
                  continue;
              }
              if ( !v36 )
                goto LABEL_82;
              goto LABEL_140;
            }
            do
            {
LABEL_140:
              PTSetMember::EndCommit(v36, 0);
              if ( !*(_QWORD *)v36 )
                break;
              v36 = (PTSetMember *)(*(_QWORD *)v36 + *(_QWORD *)NtCurrentTeb()->ReservedForOle);
            }
            while ( v36 );
          }
        }
      }
    }
LABEL_82:
    if ( *((_WORD *)this + 68) == 1 )
    {
      v56 = *((_QWORD *)this + 18);
      if ( v56 )
        v57 = (CMStream *)(v56 + *(_QWORD *)NtCurrentTeb()->ReservedForOle);
      else
        v57 = 0;
      CMStream::EndCopyOnWrite(v57, a2, 0);
    }
    goto LABEL_83;
  }
  if ( (*((_BYTE *)this + 138) & 1) != 0 )
  {
    if ( !(unsigned int)CPubDocFile::IsRoot(this) )
    {
      v40 = *((_QWORD *)this + 14);
      if ( v40 )
        v41 = (CPubDocFile *)(v40 + *(_QWORD *)NtCurrentTeb()->ReservedForOle);
      else
        v41 = 0;
      CPubDocFile::SetDirty(v41);
    }
    *((_WORD *)this + 69) &= ~1u;
  }
  if ( !*((_WORD *)this + 68) )
  {
    if ( (a2 & 8) != 0 )
      CPubDocFile::Consolidate(this, a2);
    v7 = *((_QWORD *)this + 18);
    v8 = v7 ? (CMStream *)(v7 + *(_QWORD *)NtCurrentTeb()->ReservedForOle) : 0LL;
    TOD = CMStream::Flush(v8, ((a2 >> 2) & 1) == 0);
    if ( TOD < 0 )
      return (unsigned int)TOD;
  }
  return 0;
}

```

## disassembly

```asm
0x18000745c  push    rbp
0x18000745e  push    rbx
0x18000745f  push    rsi
0x180007460  push    rdi
0x180007461  push    r12
0x180007463  push    r13
0x180007465  push    r14
0x180007467  push    r15
0x180007469  lea     rbp, [rsp-1Fh]
0x18000746e  sub     rsp, 0E8h
0x180007475  mov     rax, cs:__security_cookie
0x18000747c  xor     rax, rsp
0x18000747f  mov     [rbp+57h+var_50], rax
0x180007483  xor     r13d, r13d
0x180007486  mov     r14d, edx
0x180007489  mov     rbx, rcx
0x18000748c  mov     qword ptr [rsp+120h+FileTime.dwLowDateTime], r13
0x180007491  xor     edx, edx; Val
0x180007493  mov     [rsp+120h+var_FC], r13d
0x180007498  lea     rcx, [rsp+120h+var_F0]; void *
0x18000749d  mov     [rsp+120h+var_100], r13d
0x1800074a2  lea     edi, [r13+50h]
0x1800074a6  mov     r12d, r13d
0x1800074a9  mov     r8d, edi; Size
0x1800074ac  mov     r15d, r13d
0x1800074af  call    memset_0
0x1800074b4  mov     r8d, edi; Size
0x1800074b7  lea     rcx, [rbp+57h+var_A0]; void *
0x1800074bb  xor     edx, edx; Val
0x1800074bd  call    memset_0
0x1800074c2  mov     esi, r14d
0x1800074c5  lea     eax, [rdi-4Fh]
0x1800074c8  shr     esi, 2
0x1800074cb  not     esi
0x1800074cd  and     esi, eax
0x1800074cf  test    byte ptr [rbx+14h], 20h
0x1800074d3  jnz     loc_180007E1E
0x1800074d9  test    byte ptr [rbx+14h], 80h
0x1800074dd  jz      loc_180007E28
0x1800074e3  test    [rbx+8Ah], al
0x1800074e9  jnz     loc_180007594
0x1800074ef  test    dword ptr [rbx+14h], 40000h
0x1800074f6  jnz     loc_180007E32
0x1800074fc  xor     edx, edx; int
0x1800074fe  mov     rcx, rbx; this
0x180007501  call    ?FlushBufferedData@CPubDocFile@@QEAAJH@Z; CPubDocFile::FlushBufferedData(int)
0x180007506  mov     edi, eax
0x180007508  test    eax, eax
0x18000750a  js      short loc_18000756E
0x18000750c  test    byte ptr [rbx+14h], 2
0x180007510  jnz     loc_1800075E6
0x180007516  mov     eax, 1
0x18000751b  test    [rbx+8Ah], al
0x180007521  jnz     loc_18000781B
0x180007527  cmp     [rbx+88h], r13w
0x18000752f  jnz     short loc_180007590
0x180007531  test    r14b, 8
0x180007535  jnz     loc_180007E45
0x18000753b  mov     rdx, [rbx+90h]
0x180007542  test    rdx, rdx
0x180007545  jz      loc_180007A0D
0x18000754b  mov     rax, gs:30h
0x180007554  mov     rcx, [rax+1758h]
0x18000755b  mov     rcx, [rcx]
0x18000755e  add     rcx, rdx; this
0x180007561  mov     edx, esi; int
0x180007563  call    ?Flush@CMStream@@QEAAJH@Z; CMStream::Flush(int)
0x180007568  mov     edi, eax
0x18000756a  test    eax, eax
0x18000756c  jns     short loc_180007590
0x18000756e  mov     eax, edi
0x180007570  mov     rcx, [rbp+57h+var_50]
0x180007574  xor     rcx, rsp; StackCookie
0x180007577  call    __security_check_cookie
0x18000757c  add     rsp, 0E8h
0x180007583  pop     r15
0x180007585  pop     r14
0x180007587  pop     r13
0x180007589  pop     r12
0x18000758b  pop     rdi
0x18000758c  pop     rsi
0x18000758d  pop     rbx
0x18000758e  pop     rbp
0x18000758f  retn
0x180007590  xor     eax, eax
0x180007592  jmp     short loc_180007570
0x180007594  lea     rcx, [rsp+120h+FileTime]; lpFileTime
0x180007599  call    ?DfGetTOD@@YAJPEAU_FILETIME@@@Z; DfGetTOD(_FILETIME *)
0x18000759e  mov     edi, eax
0x1800075a0  test    eax, eax
0x1800075a2  js      short loc_18000756E
0x1800075a4  mov     rdx, [rbx+78h]
0x1800075a8  test    rdx, rdx
0x1800075ab  jz      loc_180007A1D
0x1800075b1  mov     rax, gs:30h
0x1800075ba  mov     rcx, [rax+1758h]
0x1800075c1  mov     rcx, [rcx]
0x1800075c4  add     rcx, rdx
0x1800075c7  mov     r8, qword ptr [rsp+120h+FileTime.dwLowDateTime]
0x1800075cc  mov     edx, 1
0x1800075d1  call    ?SetTime@PTimeEntry@@QEAAJW4WHICHTIME@@U_FILETIME@@@Z; PTimeEntry::SetTime(WHICHTIME,_FILETIME)
0x1800075d6  mov     edi, eax
0x1800075d8  test    eax, eax
0x1800075da  js      short loc_18000756E
0x1800075dc  mov     eax, 1
0x1800075e1  jmp     loc_1800074EF
0x1800075e6  mov     r8d, 1
0x1800075ec  cmp     [rbx+88h], r8w
0x1800075f4  jnz     loc_1800076E2
0x1800075fa  mov     rdx, [rbx+0A0h]
0x180007601  test    rdx, rdx
0x180007604  jz      loc_180007A25
0x18000760a  mov     rax, gs:30h
0x180007613  mov     rcx, [rax+1758h]
0x18000761a  mov     rcx, [rcx]
0x18000761d  add     rcx, rdx
0x180007620  test    byte ptr [rcx+50h], 4
0x180007624  jnz     loc_180007B04
0x18000762a  mov     rdx, [rbx+90h]
0x180007631  test    rdx, rdx
0x180007634  jz      loc_180007A15
0x18000763a  mov     rax, gs:30h
0x180007643  mov     rcx, [rax+1758h]
0x18000764a  mov     rcx, [rcx]
0x18000764d  add     rcx, rdx; this
0x180007650  mov     edx, r14d; unsigned int
0x180007653  call    ?BeginCopyOnWrite@CMStream@@QEAAJK@Z; CMStream::BeginCopyOnWrite(ulong)
0x180007658  mov     edi, eax
0x18000765a  test    eax, eax
0x18000765c  js      loc_1800079C8
0x180007662  mov     r8d, 1
0x180007668  test    r8b, r14b
0x18000766b  jz      short loc_180007685
0x18000766d  mov     rcx, rbx; this
0x180007670  call    ?PrepareForOverwrite@CPubDocFile@@IEAAJXZ; CPubDocFile::PrepareForOverwrite(void)
0x180007675  mov     edi, eax
0x180007677  test    eax, eax
0x180007679  js      loc_1800079B6
0x18000767f  mov     r8d, 1
0x180007685  test    dword ptr [rbx+14h], 40004h
0x18000768c  jz      short loc_1800076E2
0x18000768e  cmp     dword ptr [rbx+98h], 0FFFFFFFFh
0x180007695  jnz     loc_180007B53
0x18000769b  test    r14b, 2
0x18000769f  jz      short loc_1800076E2
0x1800076a1  mov     rdx, [rbx+0A0h]
0x1800076a8  test    rdx, rdx
0x1800076ab  jz      loc_180007B4B
0x1800076b1  mov     rax, gs:30h
0x1800076ba  mov     rcx, [rax+1758h]
0x1800076c1  mov     rcx, [rcx]
0x1800076c4  add     rcx, rdx
0x1800076c7  mov     rcx, [rcx+30h]; struct ILockBytes *
0x1800076cb  call    ?DllIsMultiStream@@YAJPEAUILockBytes@@@Z; DllIsMultiStream(ILockBytes *)
0x1800076d0  test    eax, eax
0x1800076d2  jnz     loc_180007BA5
0x1800076d8  mov     edi, 80030101h
0x1800076dd  jmp     loc_1800079B6
0x1800076e2  mov     rdx, [rbx+68h]; unsigned int
0x1800076e6  test    rdx, rdx
0x1800076e9  jnz     loc_180007888
0x1800076ef  mov     rsi, r13
0x1800076f2  test    rsi, rsi
0x1800076f5  jnz     loc_18000783C
0x1800076fb  test    byte ptr [rbx+14h], 4
0x1800076ff  jnz     loc_180007BB5
0x180007705  mov     esi, 1
0x18000770a  cmp     [rbx+88h], si
0x180007711  jz      loc_180007949
0x180007717  mov     rdx, [rbx+68h]
0x18000771b  test    rdx, rdx
0x18000771e  jz      short loc_180007741
0x180007720  mov     rax, gs:30h
0x180007729  mov     rcx, [rax+1758h]
0x180007730  mov     rsi, [rcx]
0x180007733  add     rsi, rdx
0x180007736  jnz     loc_180007A5D
0x18000773c  mov     esi, 1
0x180007741  mov     rcx, rbx; this
0x180007744  call    ?RemoveUnnecessaryXSMembers@CPubDocFile@@QEAAXXZ; CPubDocFile::RemoveUnnecessaryXSMembers(void)
0x180007749  test    r14b, 8
0x18000774d  jnz     loc_180007EB5
0x180007753  test    byte ptr [rbx+14h], 4
0x180007757  jnz     loc_1800078A3
0x18000775d  test    dword ptr [rbx+14h], 40004h
0x180007764  jz      short loc_1800077AF
0x180007766  lea     rdx, [rbx+98h]; unsigned int *
0x18000776d  cmp     dword ptr [rdx], 0FFFFFFFFh
0x180007770  jz      loc_180007D6F
0x180007776  lea     r8d, [r15+1]
0x18000777a  mov     [rdx], r8d
0x18000777d  mov     rdx, [rbx+0A0h]
0x180007784  test    rdx, rdx
0x180007787  jz      loc_180007A55
0x18000778d  mov     rax, gs:30h
0x180007796  mov     rcx, [rax+1758h]
0x18000779d  mov     rcx, [rcx]
0x1800077a0  add     rcx, rdx
0x1800077a3  mov     rcx, [rcx+30h]; struct ILockBytes *
0x1800077a7  mov     edx, r8d; unsigned int
0x1800077aa  call    ?DllSetCommitSig@@YAJPEAUILockBytes@@K@Z; DllSetCommitSig(ILockBytes *,ulong)
0x1800077af  test    r12d, r12d
0x1800077b2  jnz     loc_180007DA4
0x1800077b8  movzx   eax, word ptr [rbx+8Ah]
0x1800077bf  test    sil, al
0x1800077c2  jnz     loc_180007EC7
0x1800077c8  mov     ecx, 0FFFDh
0x1800077cd  and     ax, cx
0x1800077d0  mov     [rbx+8Ah], ax
0x1800077d7  mov     rax, [rbx]
0x1800077da  sub     rax, qword ptr cs:_GUID_33c83c10_d239_4c83_98b3_9f2621c2df7f.Data1
0x1800077e1  jnz     short loc_1800077EE
0x1800077e3  mov     rax, [rbx+8]
0x1800077e7  sub     rax, qword ptr cs:_GUID_33c83c10_d239_4c83_98b3_9f2621c2df7f.Data4
0x1800077ee  test    rax, rax
0x1800077f1  jnz     loc_18000756E
0x1800077f7  mov     eax, [rbx+14h]
0x1800077fa  mov     ecx, 4002h
0x1800077ff  and     eax, ecx
0x180007801  cmp     eax, ecx
0x180007803  jnz     loc_18000756E
0x180007809  lea     rcx, [rbx+0B8h]; lpSystemTimeAsFileTime
0x180007810  call    cs:__imp_GetSystemTimeAsFileTime
0x180007816  jmp     loc_18000756E
0x18000781b  mov     rcx, rbx; this
0x18000781e  call    ?IsRoot@CPubDocFile@@QEBAHXZ; CPubDocFile::IsRoot(void)
0x180007823  test    eax, eax
0x180007825  jz      loc_180007AD6
0x18000782b  mov     ecx, 0FFFEh
0x180007830  and     [rbx+8Ah], cx
0x180007837  jmp     loc_180007527
0x18000783c  cmp     [rsi+5Eh], r8w
0x180007841  jnz     loc_180007930
0x180007847  lea     rcx, [rsi-10h]; this
0x18000784b  call    ?BeginCommit@CWrappedDocFile@@QEAAJK@Z; CWrappedDocFile::BeginCommit(ulong)
0x180007850  mov     edi, eax
0x180007852  test    eax, eax
0x180007854  js      loc_180007991
0x18000785a  mov     rdx, [rsi+8]
0x18000785e  test    rdx, rdx
0x180007861  jz      loc_180007A2D
0x180007867  mov     rax, gs:30h
0x180007870  mov     rcx, [rax+1758h]
0x180007877  mov     rsi, [rcx]
0x18000787a  add     rsi, rdx
0x18000787d  mov     r8d, 1
0x180007883  jmp     loc_1800076F2
0x180007888  mov     rax, gs:30h
0x180007891  mov     rcx, [rax+1758h]
0x180007898  mov     rsi, [rcx]
0x18000789b  add     rsi, rdx
0x18000789e  jmp     loc_1800076F2
0x1800078a3  mov     rdx, [rbx+0A0h]
0x1800078aa  test    rdx, rdx
0x1800078ad  jz      loc_180007A3D
0x1800078b3  mov     rax, gs:30h
0x1800078bc  mov     rcx, [rax+1758h]
0x1800078c3  mov     rcx, [rcx]
0x1800078c6  add     rcx, rdx
0x1800078c9  mov     r8, [rcx+30h]; struct ILockBytes *
0x1800078cd  test    rdx, rdx
0x1800078d0  jz      loc_180007A45
0x1800078d6  mov     rax, gs:30h
0x1800078df  mov     rcx, [rax+1758h]
0x1800078e6  add     rdx, [rcx]
0x1800078e9  mov     rdx, [rdx+20h]; struct ILockBytes *
0x1800078ed  mov     rcx, rbx; this
0x1800078f0  call    ?CopyLStreamToLStream@CPubDocFile@@IEAAJPEAUILockBytes@@0@Z; CPubDocFile::CopyLStreamToLStream(ILockBytes *,ILockBytes *)
0x1800078f5  mov     rdx, [rbx+0A0h]
0x1800078fc  test    rdx, rdx
0x1800078ff  jz      loc_180007A4D
0x180007905  mov     rax, gs:30h
0x18000790e  mov     rcx, [rax+1758h]
0x180007915  mov     rcx, [rcx]
0x180007918  add     rcx, rdx
0x18000791b  mov     rcx, [rcx+30h]
0x18000791f  mov     rax, [rcx]
0x180007922  mov     rax, [rax+28h]
0x180007926  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000792b  jmp     loc_18000775D
0x180007930  cmp     word ptr [rsi+5Eh], 2
0x180007935  jnz     loc_180007E55
0x18000793b  lea     rcx, [rsi-10h]; this
0x18000793f  call    ?BeginCommit@CTransactedStream@@QEAAJK@Z; CTransactedStream::BeginCommit(ulong)
0x180007944  jmp     loc_180007850
0x180007949  mov     rdx, [rbx+90h]
0x180007950  test    rdx, rdx
0x180007953  jz      loc_180007A35
0x180007959  mov     rax, gs:30h
0x180007962  mov     rcx, [rax+1758h]
0x180007969  mov     rcx, [rcx]
0x18000796c  add     rcx, rdx; this
0x18000796f  mov     r8d, 8; unsigned int
0x180007975  mov     edx, r14d; unsigned int
0x180007978  call    ?EndCopyOnWrite@CMStream@@QEAAJKK@Z; CMStream::EndCopyOnWrite(ulong,ulong)
0x18000797d  mov     edi, eax
0x18000797f  test    eax, eax
0x180007981  jns     loc_180007717
0x180007987  test    byte ptr [rbx+14h], 4
0x18000798b  jnz     loc_180007E5F
  ... truncated ...
```
