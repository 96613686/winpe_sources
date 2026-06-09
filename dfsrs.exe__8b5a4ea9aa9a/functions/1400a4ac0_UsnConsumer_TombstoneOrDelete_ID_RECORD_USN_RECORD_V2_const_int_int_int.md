# UsnConsumer::TombstoneOrDelete(ID_RECORD &,USN_RECORD_V2 const &,int,int,int)

- ea: `0x1400a4ac0`
- end: `0x1400a5390`
- name: `?TombstoneOrDelete@UsnConsumer@@AEAAPEAVFrsStatus@@AEAVID_RECORD@@AEBUUSN_RECORD_V2@@HHH@Z`
- size: `2256`
- prototype: `struct FrsStatus *__usercall@<rax>(UsnConsumer *__hidden this@<rcx>, struct ID_RECORD *@<rdx>, const struct USN_RECORD_V2 *@<r8>, int@<r9d>, int, int)`
- caller_count: `3`
- callee_count: `14`
- tags: `loader_planting, installer_update`

## callers

- `0x1400a1490`
- `0x1400a32d4`
- `0x1400a48c4`

## callees

- `0x1400036a0`
- `0x14002a15c`
- `0x14002a6d0`
- `0x14002c1c0`
- `0x14006f224`
- `0x140088fd8`
- `0x140094f3c`
- `0x1400a033c`
- `0x1400a1d40`
- `0x1400a298c`
- `0x1400a4ac0`
- `0x1400a58c4`
- `0x1401b9494`
- `0x140223010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400a4c8e`
- `KERNEL32!GetCurrentThreadId` at `0x1400a4d7c`
- `KERNEL32!GetCurrentThreadId` at `0x1400a4ed0`
- `KERNEL32!GetCurrentThreadId` at `0x1400a4faf`
- `KERNEL32!GetCurrentThreadId` at `0x1400a5128`
- `KERNEL32!GetCurrentThreadId` at `0x1400a51d4`
- `KERNEL32!GetCurrentThreadId` at `0x1400a5309`
- `KERNEL32!GetCurrentThreadId` at `0x1400a4c8e`
- `KERNEL32!GetCurrentThreadId` at `0x1400a4d7c`
- `KERNEL32!GetCurrentThreadId` at `0x1400a4ed0`
- `KERNEL32!GetCurrentThreadId` at `0x1400a4faf`
- `KERNEL32!GetCurrentThreadId` at `0x1400a5128`
- `KERNEL32!GetCurrentThreadId` at `0x1400a51d4`
- `KERNEL32!GetCurrentThreadId` at `0x1400a5309`

## string_xrefs

- `0x1400a4cad`: `UsnConsumer::TombstoneOrDelete`
- `0x1400a4d9b`: `UsnConsumer::TombstoneOrDelete`
- `0x1400a4eef`: `UsnConsumer::TombstoneOrDelete`
- `0x1400a4fce`: `UsnConsumer::TombstoneOrDelete`
- `0x1400a5153`: `UsnConsumer::TombstoneOrDelete`
- `0x1400a51f6`: `UsnConsumer::TombstoneOrDelete`
- `0x1400a4c1f`: `UsnConsumer::TombstoneOrDelete`
- `0x1400a4e64`: `UsnConsumer::TombstoneOrDelete`
- `0x1400a4f44`: `ID record deleted from USN_RECORD:%?`

## pseudocode

```c
struct FrsStatus *__fastcall UsnConsumer::TombstoneOrDelete(
        UsnConsumer *this,
        struct ID_RECORD *a2,
        const struct USN_RECORD_V2 *a3,
        int a4,
        int a5,
        int a6)
{
  LARGE_INTEGER *p_TimeStamp; // rsi
  unsigned int FileNameLength; // edx
  int v12; // eax
  bool v13; // zf
  int v14; // ecx
  int v15; // eax
  int v16; // ebx
  unsigned int v17; // ecx
  USN v18; // rax
  struct _FILETIME *v19; // rcx
  unsigned int *v20; // rbx
  DWORD v21; // eax
  __int64 v22; // rcx
  __int64 v23; // rbx
  unsigned int *v24; // rbx
  DWORD v25; // eax
  __int64 v26; // rcx
  int v27; // eax
  unsigned __int64 v28; // rax
  unsigned int *v29; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v31; // rcx
  __int64 *v32; // rcx
  __int64 v33; // rax
  unsigned int *v34; // rbx
  DWORD v35; // eax
  __int64 v36; // rcx
  int v37; // edx
  USN Usn; // rax
  unsigned int *v39; // rbx
  __int64 v40; // rcx
  __int128 v41; // xmm0
  int v42; // ecx
  LPCRITICAL_SECTION v43; // rax
  unsigned int *v44; // rbx
  DWORD v45; // eax
  __int64 v46; // rcx
  int v48; // [rsp+30h] [rbp-D0h]
  DWORD v49; // [rsp+38h] [rbp-C8h]
  unsigned __int64 v50; // [rsp+40h] [rbp-C0h]
  DWORDLONG ParentFileReferenceNumber; // [rsp+50h] [rbp-B0h] BYREF
  int v52; // [rsp+58h] [rbp-A8h] BYREF
  DWORDLONG v53; // [rsp+60h] [rbp-A0h] BYREF
  int v54; // [rsp+68h] [rbp-98h]
  union _LARGE_INTEGER *v55; // [rsp+70h] [rbp-90h]
  __int64 v56; // [rsp+78h] [rbp-88h] BYREF
  __int128 v57; // [rsp+80h] [rbp-80h] BYREF
  const wchar_t *v58; // [rsp+90h] [rbp-70h]
  __int128 v59; // [rsp+98h] [rbp-68h] BYREF
  const wchar_t *v60; // [rsp+A8h] [rbp-58h]
  __int128 v61; // [rsp+B0h] [rbp-50h] BYREF
  const wchar_t *v62; // [rsp+C0h] [rbp-40h]
  _BYTE v63[48]; // [rsp+C8h] [rbp-38h] BYREF
  struct _GUID v64; // [rsp+F8h] [rbp-8h] BYREF
  struct _FILETIME v65; // [rsp+134h] [rbp+34h] BYREF
  __int64 v66; // [rsp+13Ch] [rbp+3Ch]
  int v67; // [rsp+148h] [rbp+48h]
  DWORDLONG v68; // [rsp+358h] [rbp+258h]
  DWORDLONG v69; // [rsp+360h] [rbp+260h]
  unsigned int v70; // [rsp+370h] [rbp+270h]

  v57 = 0;
  v58 = 0;
  v56 = 0;
  v52 = 0;
  if ( a5
    || (a3->FileAttributes & 0x10) != 0
    || (p_TimeStamp = &a3->TimeStamp,
        FileNameLength = a3->FileNameLength,
        ParentFileReferenceNumber = a3->ParentFileReferenceNumber,
        v55 = &a3->TimeStamp,
        !(unsigned int)UsnConsumer::UidTunnelCache::NameExists(
                         (char *)this + 192,
                         &ParentFileReferenceNumber,
                         &a3->TimeStamp,
                         a3->FileName,
                         FileNameLength >> 1,
                         1,
                         &v57,
                         &v56)) )
  {
    p_TimeStamp = &a3->TimeStamp;
    v12 = 0;
    v55 = &a3->TimeStamp;
  }
  else
  {
    v12 = 1;
  }
  v13 = (*((_DWORD *)a2 + 176) & 1) == 0;
  v14 = *((_DWORD *)a2 + 176) & 1;
  v54 = v12;
  LODWORD(v53) = v14;
  if ( v13 || v12 )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      *(_QWORD *)&v59 = L"UsnConsumer::TombstoneOrDelete";
      *((_QWORD *)&v59 + 1) = 0x400000B81LL;
      v60 = L"USNC";
      dbgobj::DbgPrint<unsigned short,GVSN>(&v59, L"LDB Deleting ID Record. uid:%?", a2);
    }
    v29 = (unsigned int *)(*(__int64 (__fastcall **)(_QWORD, struct ID_RECORD *, _QWORD))(**((_QWORD **)this + 13)
                                                                                        + 176LL))(
                            *((_QWORD *)this + 13),
                            a2,
                            0);
    if ( v29 )
    {
      CurrentThreadId = GetCurrentThreadId();
      v23 = FrsStatusList::PushNewError(
              v31,
              v29[1],
              v29[2],
              *v29,
              "base\\fs\\remotefs\\frs\\src\\db\\usnconsumer.cpp",
              "UsnConsumer::TombstoneOrDelete",
              2946,
              CurrentThreadId,
              v29);
      if ( v23 )
        return (struct FrsStatus *)v23;
    }
    else
    {
      v23 = 0;
    }
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      *(_QWORD *)&v59 = L"UsnConsumer::TombstoneOrDelete";
      *((_QWORD *)&v59 + 1) = 0x400000B87LL;
      v60 = L"USNC";
      dbgobj::DbgPrint<unsigned short,USN_RECORD_V2>(&v59, L"ID record deleted from USN_RECORD:%?", a3);
    }
    if ( !v54 )
      goto LABEL_94;
    ID_RECORD::ID_RECORD((ID_RECORD *)&v61);
    v32 = (__int64 *)*((_QWORD *)this + 13);
    v33 = *v32;
    ParentFileReferenceNumber = 0;
    v34 = (unsigned int *)(*(__int64 (__fastcall **)(__int64 *, int *, __int64 *, __int128 *, DWORDLONG *))(v33 + 40))(
                            v32,
                            &v52,
                            &v56,
                            &v61,
                            &ParentFileReferenceNumber);
    if ( v34 )
    {
      v35 = GetCurrentThreadId();
      v23 = FrsStatusList::PushNewError(
              v36,
              v34[1],
              v34[2],
              *v34,
              "base\\fs\\remotefs\\frs\\src\\db\\usnconsumer.cpp",
              "UsnConsumer::TombstoneOrDelete",
              2957,
              v35,
              v34);
      if ( v23 )
        return (struct FrsStatus *)v23;
    }
    else
    {
      v23 = 0;
    }
    if ( !v52 || !(unsigned int)ID_RECORD::Alive((ID_RECORD *)&v61) )
      goto LABEL_94;
    ParentFileReferenceNumber = v68;
    v60 = v62;
    v59 = v61;
    if ( (v70 & 1) != 0 )
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) != v37 && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
      {
        *(_QWORD *)&v57 = L"UsnConsumer::TombstoneOrDelete";
        *((_QWORD *)&v57 + 1) = 0x500000B9DLL;
        v58 = L"USNC";
        dbgobj::DbgPrint<unsigned short,GVSN>(&v57, L"Updating uid:%?", &v59);
      }
      UsnConsumer::GetNextVersion(this, &v64, (struct GVSN *)v63);
      Usn = a3->Usn;
      v67 &= 0xFFFFFFEE;
      v70 &= 0xFFFFFE11;
      v68 = Usn;
      ID_UPDATE::PromoteFenceValue((ID_UPDATE *)&v61);
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
      {
        *(_QWORD *)&v57 = L"UsnConsumer::TombstoneOrDelete";
        *((_QWORD *)&v57 + 1) = 0x400000BAALL;
        v58 = L"USNC";
        dbgobj::DbgPrint<unsigned short,ID_RECORD>(&v57, L"LDB Updating ID Record:%?", &v61);
      }
      v39 = (unsigned int *)(*(__int64 (__fastcall **)(_QWORD, __int128 *, __int128 *, _QWORD))(**((_QWORD **)this + 13)
                                                                                              + 200LL))(
                              *((_QWORD *)this + 13),
                              &v59,
                              &v61,
                              0);
      if ( !v39 )
        goto LABEL_79;
      v50 = (unsigned __int64)v39;
      v49 = GetCurrentThreadId();
      v48 = 2987;
    }
    else
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) != v37 && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
      {
        *(_QWORD *)&v57 = L"UsnConsumer::TombstoneOrDelete";
        *((_QWORD *)&v57 + 1) = 0x400000BB3LL;
        v58 = L"USNC";
        dbgobj::DbgPrint<unsigned short,GVSN>(&v57, L"LDB Deleting ID Record. uid:%?", &v59);
      }
      v39 = (unsigned int *)(*(__int64 (__fastcall **)(_QWORD, __int128 *, _QWORD))(**((_QWORD **)this + 13) + 176LL))(
                              *((_QWORD *)this + 13),
                              &v59,
                              0);
      if ( !v39 )
        goto LABEL_79;
      v50 = (unsigned __int64)v39;
      v49 = GetCurrentThreadId();
      v48 = 2996;
    }
    v23 = FrsStatusList::PushNewError(
            v40,
            v39[1],
            v39[2],
            *v39,
            "base\\fs\\remotefs\\frs\\src\\db\\usnconsumer.cpp",
            "UsnConsumer::TombstoneOrDelete",
            v48,
            v49,
            v50);
    if ( v23 )
      return (struct FrsStatus *)v23;
LABEL_79:
    UsnConsumer::GetNextVersion(this, &v64, (struct GVSN *)v63);
    v41 = *(_OWORD *)a2;
    v62 = (const wchar_t *)*((_QWORD *)a2 + 2);
    v66 = *(_QWORD *)((char *)a2 + 140);
    v68 = ParentFileReferenceNumber;
    v61 = v41;
    if ( (v70 & 1) != 0 || (v42 = 0, (_DWORD)v53) )
      v42 = 1;
    v67 |= 1u;
    v70 = v42 & 0xFFFFFFB1 | v70 & 0xFFFFFFB0;
    UpdateClock(&v65, v55);
    v43 = g_DebugLog;
    if ( g_DebugLog )
    {
      if ( LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
      {
        *(_QWORD *)&v57 = L"UsnConsumer::TombstoneOrDelete";
        *((_QWORD *)&v57 + 1) = 0x500000BCALL;
        v58 = L"USNC";
        dbgobj::DbgPrint<unsigned short,GVSN>(&v57, L"UID tunnelled. Inserting uid:%?", &v61);
        v43 = g_DebugLog;
      }
      if ( v43 && LODWORD(v43[1].LockSemaphore) && SLODWORD(v43[1].OwningThread) >= 4 )
      {
        *(_QWORD *)&v57 = L"UsnConsumer::TombstoneOrDelete";
        *((_QWORD *)&v57 + 1) = 0x400000BCBLL;
        v58 = L"USNC";
        dbgobj::DbgPrint<unsigned short,ID_RECORD>(&v57, L"LDB Inserting ID Record:%?", &v61);
      }
    }
    v44 = (unsigned int *)(*(__int64 (__fastcall **)(_QWORD, __int128 *))(**((_QWORD **)this + 13) + 160LL))(
                            *((_QWORD *)this + 13),
                            &v61);
    if ( v44 )
    {
      v45 = GetCurrentThreadId();
      v23 = FrsStatusList::PushNewError(
              v46,
              v44[1],
              v44[2],
              *v44,
              "base\\fs\\remotefs\\frs\\src\\db\\usnconsumer.cpp",
              "UsnConsumer::TombstoneOrDelete",
              3020,
              v45,
              v44);
      if ( v23 )
        return (struct FrsStatus *)v23;
    }
    else
    {
      v23 = 0;
    }
LABEL_94:
    ++*((_DWORD *)this + 24);
    *((_DWORD *)this + 84) = 1;
    return (struct FrsStatus *)v23;
  }
  UsnConsumer::GetNextVersion(this, (const struct _GUID *)((char *)a2 + 72), (struct ID_RECORD *)((char *)a2 + 24));
  v15 = *((_DWORD *)a2 + 176);
  *((_DWORD *)a2 + 38) &= 0xFFFFFFEE;
  v16 = -a4;
  *((_DWORD *)a2 + 176) = v15 & 0xFFFFFE21 | (v16 != 0 ? 0x10 : 0);
  v17 = v15 & 0xFFFFFE01 | (v16 != 0 ? 0x10 : 0);
  v18 = a3->Usn;
  *((_DWORD *)a2 + 176) = v17;
  v19 = (struct _FILETIME *)((char *)a2 + 132);
  *((_QWORD *)a2 + 85) = v18;
  if ( a6 )
  {
    *v19 = 0;
  }
  else
  {
    UpdateClock(v19, p_TimeStamp);
    ID_UPDATE::PromoteFenceValue(a2);
  }
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    *(_QWORD *)&v59 = L"UsnConsumer::TombstoneOrDelete";
    *((_QWORD *)&v59 + 1) = 0x400000BE9LL;
    v60 = L"USNC";
    dbgobj::DbgPrint<unsigned short,ID_RECORD>(&v59, L"LDB Updating ID Record:%?", a2);
  }
  v20 = (unsigned int *)(*(__int64 (__fastcall **)(_QWORD, struct ID_RECORD *, struct ID_RECORD *, _QWORD))(**((_QWORD **)this + 13) + 200LL))(
                          *((_QWORD *)this + 13),
                          a2,
                          a2,
                          0);
  if ( v20 )
  {
    v21 = GetCurrentThreadId();
    v23 = FrsStatusList::PushNewError(
            v22,
            v20[1],
            v20[2],
            *v20,
            "base\\fs\\remotefs\\frs\\src\\db\\usnconsumer.cpp",
            "UsnConsumer::TombstoneOrDelete",
            3050,
            v21,
            v20);
    if ( v23 )
      return (struct FrsStatus *)v23;
  }
  else
  {
    v23 = 0;
  }
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    *(_QWORD *)&v59 = L"UsnConsumer::TombstoneOrDelete";
    *((_QWORD *)&v59 + 1) = 0x400000BEFLL;
    v60 = L"USNC";
    dbgobj::DbgPrint<unsigned short,USN_RECORD_V2>(&v59, L"ID record tombstoned from USN_RECORD:%?", a3);
  }
  if ( a5 || (*((_BYTE *)a2 + 148) & 0x10) != 0 )
    goto LABEL_94;
  ID_RECORD::ID_RECORD((ID_RECORD *)&v61);
  v13 = (a3->Reason & 0x2000) == 0;
  v53 = 0;
  if ( v13 )
  {
    v53 = a3->ParentFileReferenceNumber;
LABEL_38:
    v28 = -1;
    do
      ++v28;
    while ( *((_WORD *)a2 + v28 + 78) );
    UsnConsumer::UidTunnelCache::Add(
      (UsnConsumer *)((char *)this + 192),
      (const struct FileId *)&v53,
      (struct ID_RECORD *)((char *)a2 + 688),
      v55,
      a2,
      (const unsigned __int16 *)a2 + 78,
      v28,
      0,
      0);
    goto LABEL_94;
  }
  v24 = (unsigned int *)(*(__int64 (__fastcall **)(_QWORD, int *, char *, __int128 *))(**((_QWORD **)this + 13) + 56LL))(
                          *((_QWORD *)this + 13),
                          &v52,
                          (char *)a2 + 48,
                          &v61);
  if ( !v24 )
  {
    v23 = 0;
LABEL_30:
    if ( v52 && (v70 & 1) != 0 && v69 == a3->ParentFileReferenceNumber )
    {
      v53 = v69;
      v27 = 1;
    }
    else
    {
      v27 = 0;
    }
    if ( !v27 )
      goto LABEL_94;
    goto LABEL_38;
  }
  v25 = GetCurrentThreadId();
  v23 = FrsStatusList::PushNewError(
          v26,
          v24[1],
          v24[2],
          *v24,
          "base\\fs\\remotefs\\frs\\src\\db\\usnconsumer.cpp",
          "UsnConsumer::TombstoneOrDelete",
          3066,
          v25,
          v24);
  if ( !v23 )
    goto LABEL_30;
  return (struct FrsStatus *)v23;
}

```

## disassembly

```asm
0x1400a4ac0  mov     [rsp-8+arg_18], rbx
0x1400a4ac5  push    rbp
0x1400a4ac6  push    rsi
0x1400a4ac7  push    rdi
0x1400a4ac8  push    r12
0x1400a4aca  push    r13
0x1400a4acc  push    r14
0x1400a4ace  push    r15
0x1400a4ad0  lea     rbp, [rsp-290h]
0x1400a4ad8  sub     rsp, 390h
0x1400a4adf  mov     rax, cs:__security_cookie
0x1400a4ae6  xor     rax, rsp
0x1400a4ae9  mov     [rbp+2C0h+var_40], rax
0x1400a4af0  xor     r12d, r12d
0x1400a4af3  xorps   xmm0, xmm0
0x1400a4af6  mov     ebx, r9d
0x1400a4af9  mov     r14, r8
0x1400a4afc  mov     rdi, rdx
0x1400a4aff  mov     r15, rcx
0x1400a4b02  movups  [rbp+2C0h+var_340], xmm0
0x1400a4b06  lea     r13d, [r12+1]
0x1400a4b0b  mov     [rbp+2C0h+var_330], r12
0x1400a4b0f  mov     [rsp+3C0h+var_348], r12
0x1400a4b14  mov     [rsp+3C0h+var_368], r12d
0x1400a4b19  cmp     [rbp+2C0h+arg_20], r12d
0x1400a4b20  jnz     short loc_1400A4B7F
0x1400a4b22  test    byte ptr [r8+34h], 10h
0x1400a4b27  jnz     short loc_1400A4B7F
0x1400a4b29  mov     rax, [r8+10h]
0x1400a4b2d  lea     rsi, [r8+20h]
0x1400a4b31  movzx   edx, word ptr [r8+38h]
0x1400a4b36  lea     r9, [r8+3Ch]
0x1400a4b3a  mov     [rsp+3C0h+var_370], rax
0x1400a4b3f  add     rcx, 0C0h
0x1400a4b46  shr     edx, 1
0x1400a4b48  lea     rax, [rsp+3C0h+var_348]
0x1400a4b4d  mov     [rsp+3C0h+var_388], rax
0x1400a4b52  mov     r8, rsi
0x1400a4b55  lea     rax, [rbp+2C0h+var_340]
0x1400a4b59  mov     [rsp+3C0h+var_350], rsi
0x1400a4b5e  mov     [rsp+3C0h+var_390], rax
0x1400a4b63  mov     dword ptr [rsp+3C0h+var_398], r13d
0x1400a4b68  mov     dword ptr [rsp+3C0h+var_3A0], edx
0x1400a4b6c  lea     rdx, [rsp+3C0h+var_370]
0x1400a4b71  call    ?NameExists@UidTunnelCache@UsnConsumer@@QEAAHAEBVFileId@@AEBT_LARGE_INTEGER@@PEBGHW4NAME_STATE@12@AEAVUID@@PEAV3@@Z; UsnConsumer::UidTunnelCache::NameExists(FileId const &,_LARGE_INTEGER const &,ushort const *,int,UsnConsumer::UidTunnelCache::NAME_STATE,UID &,FileId *)
0x1400a4b76  test    eax, eax
0x1400a4b78  jz      short loc_1400A4B7F
0x1400a4b7a  mov     eax, r13d
0x1400a4b7d  jmp     short loc_1400A4B8B
0x1400a4b7f  lea     rsi, [r14+20h]
0x1400a4b83  mov     eax, r12d
0x1400a4b86  mov     [rsp+3C0h+var_350], rsi
0x1400a4b8b  mov     ecx, [rdi+2C0h]
0x1400a4b91  and     ecx, r13d
0x1400a4b94  mov     [rsp+3C0h+var_358], eax
0x1400a4b98  mov     dword ptr [rsp+3C0h+var_360], ecx
0x1400a4b9c  jz      loc_1400A4E5D
0x1400a4ba2  test    eax, eax
0x1400a4ba4  jnz     loc_1400A4E5D
0x1400a4baa  lea     r8, [rdi+18h]; struct GVSN *
0x1400a4bae  mov     rcx, r15; this
0x1400a4bb1  lea     rdx, [rdi+48h]; struct _GUID *
0x1400a4bb5  call    ?GetNextVersion@UsnConsumer@@AEAAXAEBU_GUID@@AEAVGVSN@@@Z; UsnConsumer::GetNextVersion(_GUID const &,GVSN &)
0x1400a4bba  mov     eax, [rdi+2C0h]
0x1400a4bc0  and     dword ptr [rdi+98h], 0FFFFFFEEh
0x1400a4bc7  neg     ebx
0x1400a4bc9  sbb     ecx, ecx
0x1400a4bcb  and     eax, 0FFFFFFEFh
0x1400a4bce  and     ecx, 10h
0x1400a4bd1  or      ecx, eax
0x1400a4bd3  and     ecx, 0FFFFFE31h
0x1400a4bd9  mov     [rdi+2C0h], ecx
0x1400a4bdf  and     ecx, 0FFFFFFDFh
0x1400a4be2  mov     rax, [r14+18h]
0x1400a4be6  mov     [rdi+2C0h], ecx
0x1400a4bec  lea     rcx, [rdi+84h]; struct _FILETIME *
0x1400a4bf3  mov     [rdi+2A8h], rax
0x1400a4bfa  cmp     [rbp+2C0h+arg_28], r12d
0x1400a4c01  jz      short loc_1400A4C08
0x1400a4c03  mov     [rcx], r12
0x1400a4c06  jmp     short loc_1400A4C18
0x1400a4c08  mov     rdx, rsi; union _LARGE_INTEGER *
0x1400a4c0b  call    ?UpdateClock@@YAXAEAU_FILETIME@@AEBT_LARGE_INTEGER@@@Z; UpdateClock(_FILETIME &,_LARGE_INTEGER const &)
0x1400a4c10  mov     rcx, rdi; this
0x1400a4c13  call    ?PromoteFenceValue@ID_UPDATE@@QEAAXXZ; ID_UPDATE::PromoteFenceValue(void)
0x1400a4c18  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400a4c1f  lea     r12, aUsnconsumerTom_1; "UsnConsumer::TombstoneOrDelete"
0x1400a4c26  xor     ecx, ecx
0x1400a4c28  lea     r13, aUsnc; "USNC"
0x1400a4c2f  mov     esi, 4
0x1400a4c34  test    rax, rax
0x1400a4c37  jz      short loc_1400A4C68
0x1400a4c39  cmp     [rax+40h], ecx
0x1400a4c3c  jz      short loc_1400A4C68
0x1400a4c3e  cmp     [rax+38h], esi
0x1400a4c41  jl      short loc_1400A4C68
0x1400a4c43  mov     r8, rdi
0x1400a4c46  mov     qword ptr [rbp+2C0h+var_328], r12
0x1400a4c4a  lea     rdx, aLdbUpdatingIdR; "LDB Updating ID Record:%?"
0x1400a4c51  mov     dword ptr [rbp+2C0h+var_328+8], 0BE9h
0x1400a4c58  lea     rcx, [rbp+2C0h+var_328]
0x1400a4c5c  mov     dword ptr [rbp+2C0h+var_328+0Ch], esi
0x1400a4c5f  mov     [rbp+2C0h+var_318], r13
0x1400a4c63  call    ??$DbgPrint@GVID_RECORD@@@dbgobj@@QEAA_KPEBGAEBVID_RECORD@@@Z; dbgobj::DbgPrint<ushort,ID_RECORD>(ushort const *,ID_RECORD const &)
0x1400a4c68  mov     rcx, [r15+68h]
0x1400a4c6c  xor     r9d, r9d
0x1400a4c6f  mov     r8, rdi
0x1400a4c72  mov     rdx, rdi
0x1400a4c75  mov     rax, [rcx]
0x1400a4c78  mov     rax, [rax+0C8h]
0x1400a4c7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a4c84  xor     ecx, ecx
0x1400a4c86  mov     rbx, rax
0x1400a4c89  test    rax, rax
0x1400a4c8c  jz      short loc_1400A4CE2
0x1400a4c8e  call    cs:__imp_GetCurrentThreadId
0x1400a4c95  nop     dword ptr [rax+rax+00h]
0x1400a4c9a  mov     r9d, [rbx]
0x1400a4c9d  mov     r8d, [rbx+8]
0x1400a4ca1  mov     edx, [rbx+4]
0x1400a4ca4  mov     [rsp+3C0h+var_380], rbx
0x1400a4ca9  mov     dword ptr [rsp+3C0h+var_388], eax
0x1400a4cad  lea     rax, aUsnconsumerTom_2; "UsnConsumer::TombstoneOrDelete"
0x1400a4cb4  mov     dword ptr [rsp+3C0h+var_390], 0BEAh
0x1400a4cbc  mov     [rsp+3C0h+var_398], rax
0x1400a4cc1  lea     rax, aBaseFsRemotefs_51; "base\\fs\\remotefs\\frs\\src\\db\\usnco"...
0x1400a4cc8  mov     [rsp+3C0h+var_3A0], rax
0x1400a4ccd  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400a4cd2  xor     ecx, ecx
0x1400a4cd4  mov     rbx, rax
0x1400a4cd7  test    rax, rax
0x1400a4cda  jnz     loc_1400A5362
0x1400a4ce0  jmp     short loc_1400A4CE5
0x1400a4ce2  mov     rbx, rcx
0x1400a4ce5  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400a4cec  test    rax, rax
0x1400a4cef  jz      short loc_1400A4D20
0x1400a4cf1  cmp     [rax+40h], ecx
0x1400a4cf4  jz      short loc_1400A4D20
0x1400a4cf6  cmp     [rax+38h], esi
0x1400a4cf9  jl      short loc_1400A4D20
0x1400a4cfb  mov     r8, r14
0x1400a4cfe  mov     qword ptr [rbp+2C0h+var_328], r12
0x1400a4d02  lea     rdx, aIdRecordTombst; "ID record tombstoned from USN_RECORD:%?"
0x1400a4d09  mov     dword ptr [rbp+2C0h+var_328+8], 0BEFh
0x1400a4d10  lea     rcx, [rbp+2C0h+var_328]
0x1400a4d14  mov     dword ptr [rbp+2C0h+var_328+0Ch], esi
0x1400a4d17  mov     [rbp+2C0h+var_318], r13
0x1400a4d1b  call    ??$DbgPrint@GUUSN_RECORD_V2@@@dbgobj@@QEAA_KPEBGAEBUUSN_RECORD_V2@@@Z; dbgobj::DbgPrint<ushort,USN_RECORD_V2>(ushort const *,USN_RECORD_V2 const &)
0x1400a4d20  xor     esi, esi
0x1400a4d22  cmp     [rbp+2C0h+arg_20], esi
0x1400a4d28  jnz     loc_1400A5353
0x1400a4d2e  test    byte ptr [rdi+94h], 10h
0x1400a4d35  jnz     loc_1400A5353
0x1400a4d3b  lea     rcx, [rbp+2C0h+var_310]; this
0x1400a4d3f  call    ??0ID_RECORD@@QEAA@XZ; ID_RECORD::ID_RECORD(void)
0x1400a4d44  test    dword ptr [r14+28h], 2000h
0x1400a4d4c  mov     [rsp+3C0h+var_360], rsi
0x1400a4d51  jz      loc_1400A4E05
0x1400a4d57  mov     rcx, [r15+68h]
0x1400a4d5b  lea     r8, [rdi+30h]
0x1400a4d5f  lea     r9, [rbp+2C0h+var_310]
0x1400a4d63  lea     rdx, [rsp+3C0h+var_368]
0x1400a4d68  mov     rax, [rcx]
0x1400a4d6b  mov     rax, [rax+38h]
0x1400a4d6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a4d74  mov     rbx, rax
0x1400a4d77  test    rax, rax
0x1400a4d7a  jz      short loc_1400A4DCE
0x1400a4d7c  call    cs:__imp_GetCurrentThreadId
0x1400a4d83  nop     dword ptr [rax+rax+00h]
0x1400a4d88  mov     r9d, [rbx]
0x1400a4d8b  mov     r8d, [rbx+8]
0x1400a4d8f  mov     edx, [rbx+4]
0x1400a4d92  mov     [rsp+3C0h+var_380], rbx
0x1400a4d97  mov     dword ptr [rsp+3C0h+var_388], eax
0x1400a4d9b  lea     rax, aUsnconsumerTom_2; "UsnConsumer::TombstoneOrDelete"
0x1400a4da2  mov     dword ptr [rsp+3C0h+var_390], 0BFAh
0x1400a4daa  mov     [rsp+3C0h+var_398], rax
0x1400a4daf  lea     rax, aBaseFsRemotefs_51; "base\\fs\\remotefs\\frs\\src\\db\\usnco"...
0x1400a4db6  mov     [rsp+3C0h+var_3A0], rax
0x1400a4dbb  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400a4dc0  mov     rbx, rax
0x1400a4dc3  test    rax, rax
0x1400a4dc6  jnz     loc_1400A5362
0x1400a4dcc  jmp     short loc_1400A4DD1
0x1400a4dce  mov     rbx, rsi
0x1400a4dd1  cmp     [rsp+3C0h+var_368], esi
0x1400a4dd5  jz      short loc_1400A4DF9
0x1400a4dd7  test    byte ptr [rbp+2C0h+var_50], 1
0x1400a4dde  jz      short loc_1400A4DF9
0x1400a4de0  mov     rax, [rbp+2C0h+var_60]
0x1400a4de7  cmp     rax, [r14+10h]
0x1400a4deb  jnz     short loc_1400A4DF9
0x1400a4ded  mov     [rsp+3C0h+var_360], rax
0x1400a4df2  mov     eax, 1
0x1400a4df7  jmp     short loc_1400A4DFB
0x1400a4df9  mov     eax, esi
0x1400a4dfb  test    eax, eax
0x1400a4dfd  jz      loc_1400A5353
0x1400a4e03  jmp     short loc_1400A4E0E
0x1400a4e05  mov     rax, [r14+10h]
0x1400a4e09  mov     [rsp+3C0h+var_360], rax
0x1400a4e0e  lea     rdx, [rdi+9Ch]
0x1400a4e15  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400a4e19  inc     rax
0x1400a4e1c  cmp     [rdx+rax*2], si
0x1400a4e20  jnz     short loc_1400A4E19
0x1400a4e22  mov     r9, [rsp+3C0h+var_350]; union _LARGE_INTEGER *
0x1400a4e27  lea     r8, [rdi+2B0h]; struct FileId *
0x1400a4e2e  mov     [rsp+3C0h+var_380], rsi; unsigned __int64
0x1400a4e33  lea     rcx, [r15+0C0h]; this
0x1400a4e3a  mov     [rsp+3C0h+var_388], rsi; unsigned __int16 *
0x1400a4e3f  mov     [rsp+3C0h+var_390], rax; unsigned __int64
0x1400a4e44  mov     [rsp+3C0h+var_398], rdx; unsigned __int16 *
0x1400a4e49  lea     rdx, [rsp+3C0h+var_360]; struct FileId *
0x1400a4e4e  mov     [rsp+3C0h+var_3A0], rdi; struct UID *
0x1400a4e53  call    ?Add@UidTunnelCache@UsnConsumer@@QEAAXAEBVFileId@@0AEBT_LARGE_INTEGER@@AEBVUID@@PEBG_K34@Z; UsnConsumer::UidTunnelCache::Add(FileId const &,FileId const &,_LARGE_INTEGER const &,UID const &,ushort const *,unsigned __int64,ushort const *,unsigned __int64)
0x1400a4e58  jmp     loc_1400A5353
0x1400a4e5d  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400a4e64  lea     r12, aUsnconsumerTom_1; "UsnConsumer::TombstoneOrDelete"
0x1400a4e6b  xor     ecx, ecx
0x1400a4e6d  lea     r13, aUsnc; "USNC"
0x1400a4e74  mov     esi, 4
0x1400a4e79  test    rax, rax
0x1400a4e7c  jz      short loc_1400A4EAD
0x1400a4e7e  cmp     [rax+40h], ecx
0x1400a4e81  jz      short loc_1400A4EAD
0x1400a4e83  cmp     [rax+38h], esi
0x1400a4e86  jl      short loc_1400A4EAD
0x1400a4e88  mov     r8, rdi
0x1400a4e8b  mov     qword ptr [rbp+2C0h+var_328], r12
0x1400a4e8f  lea     rdx, aLdbDeletingIdR; "LDB Deleting ID Record. uid:%?"
0x1400a4e96  mov     dword ptr [rbp+2C0h+var_328+8], 0B81h
0x1400a4e9d  lea     rcx, [rbp+2C0h+var_328]
0x1400a4ea1  mov     dword ptr [rbp+2C0h+var_328+0Ch], esi
0x1400a4ea4  mov     [rbp+2C0h+var_318], r13
0x1400a4ea8  call    ??$DbgPrint@GVGVSN@@@dbgobj@@QEAA_KPEBGAEBVGVSN@@@Z; dbgobj::DbgPrint<ushort,GVSN>(ushort const *,GVSN const &)
0x1400a4ead  mov     rcx, [r15+68h]
0x1400a4eb1  xor     r8d, r8d
0x1400a4eb4  mov     rdx, rdi
0x1400a4eb7  mov     rax, [rcx]
0x1400a4eba  mov     rax, [rax+0B0h]
0x1400a4ec1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a4ec6  xor     ecx, ecx
0x1400a4ec8  mov     rbx, rax
0x1400a4ecb  test    rax, rax
0x1400a4ece  jz      short loc_1400A4F24
0x1400a4ed0  call    cs:__imp_GetCurrentThreadId
0x1400a4ed7  nop     dword ptr [rax+rax+00h]
0x1400a4edc  mov     r9d, [rbx]
0x1400a4edf  mov     r8d, [rbx+8]
0x1400a4ee3  mov     edx, [rbx+4]
0x1400a4ee6  mov     [rsp+3C0h+var_380], rbx
0x1400a4eeb  mov     dword ptr [rsp+3C0h+var_388], eax
0x1400a4eef  lea     rax, aUsnconsumerTom_2; "UsnConsumer::TombstoneOrDelete"
0x1400a4ef6  mov     dword ptr [rsp+3C0h+var_390], 0B82h
0x1400a4efe  mov     [rsp+3C0h+var_398], rax
0x1400a4f03  lea     rax, aBaseFsRemotefs_51; "base\\fs\\remotefs\\frs\\src\\db\\usnco"...
0x1400a4f0a  mov     [rsp+3C0h+var_3A0], rax
0x1400a4f0f  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400a4f14  xor     ecx, ecx
0x1400a4f16  mov     rbx, rax
0x1400a4f19  test    rax, rax
0x1400a4f1c  jnz     loc_1400A5362
0x1400a4f22  jmp     short loc_1400A4F27
0x1400a4f24  mov     rbx, rcx
0x1400a4f27  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400a4f2e  test    rax, rax
0x1400a4f31  jz      short loc_1400A4F64
0x1400a4f33  cmp     [rax+40h], ecx
0x1400a4f36  jz      short loc_1400A4F64
0x1400a4f38  cmp     [rax+38h], esi
0x1400a4f3b  jl      short loc_1400A4F64
0x1400a4f3d  mov     r8, r14
0x1400a4f40  mov     qword ptr [rbp+2C0h+var_328], r12
0x1400a4f44  lea     rdx, aIdRecordDelete; "ID record deleted from USN_RECORD:%?"
0x1400a4f4b  mov     dword ptr [rbp+2C0h+var_328+8], 0B87h
0x1400a4f52  lea     rcx, [rbp+2C0h+var_328]
0x1400a4f56  mov     dword ptr [rbp+2C0h+var_328+0Ch], esi
0x1400a4f59  mov     [rbp+2C0h+var_318], r13
0x1400a4f5d  call    ??$DbgPrint@GUUSN_RECORD_V2@@@dbgobj@@QEAA_KPEBGAEBUUSN_RECORD_V2@@@Z; dbgobj::DbgPrint<ushort,USN_RECORD_V2>(ushort const *,USN_RECORD_V2 const &)
0x1400a4f62  xor     ecx, ecx
0x1400a4f64  cmp     [rsp+3C0h+var_358], ecx
0x1400a4f68  jz      loc_1400A5353
0x1400a4f6e  lea     rcx, [rbp+2C0h+var_310]; this
0x1400a4f72  call    ??0ID_RECORD@@QEAA@XZ; ID_RECORD::ID_RECORD(void)
0x1400a4f77  mov     rcx, [r15+68h]
0x1400a4f7b  lea     rdx, [rsp+3C0h+var_370]
0x1400a4f80  mov     [rsp+3C0h+var_3A0], rdx
0x1400a4f85  lea     r9, [rbp+2C0h+var_310]
0x1400a4f89  lea     r8, [rsp+3C0h+var_348]
0x1400a4f8e  lea     rdx, [rsp+3C0h+var_368]
0x1400a4f93  mov     rax, [rcx]
0x1400a4f96  and     [rsp+3C0h+var_370], 0
0x1400a4f9c  mov     rax, [rax+28h]
0x1400a4fa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a4fa5  xor     edx, edx
0x1400a4fa7  mov     rbx, rax
0x1400a4faa  test    rax, rax
  ... truncated ...
```
