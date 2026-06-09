# UsnConsumer::UpdateIdRecord(USN_RECORD_V2 const &,ID_RECORD &,UID const &,Usn const *)

- ea: `0x1400a58f0`
- end: `0x1400a6259`
- name: `?UpdateIdRecord@UsnConsumer@@AEAAPEAVFrsStatus@@AEBUUSN_RECORD_V2@@AEAVID_RECORD@@AEBVUID@@PEBVUsn@@@Z`
- size: `2409`
- prototype: `struct FrsStatus *__usercall@<rax>(UsnConsumer *__hidden this@<rcx>, const struct USN_RECORD_V2 *@<rdx>, struct ID_RECORD *@<r8>, const struct UID *@<r9>, const struct Usn *)`
- caller_count: `4`
- callee_count: `16`
- tags: `loader_planting, installer_update`

## callers

- `0x1400a2d5c`
- `0x1400a32d4`
- `0x1400a6260`
- `0x1400a6460`

## callees

- `0x1400036a0`
- `0x14002a15c`
- `0x14002a6d0`
- `0x14002c1c0`
- `0x1400380ec`
- `0x140088fd8`
- `0x140094f3c`
- `0x1400a033c`
- `0x1400a1d40`
- `0x1400a298c`
- `0x1400a5740`
- `0x1400a58c4`
- `0x1400a58f0`
- `0x1401b4040`
- `0x1401b9494`
- `0x140223010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400a5a7a`
- `KERNEL32!GetCurrentThreadId` at `0x1400a5c07`
- `KERNEL32!GetCurrentThreadId` at `0x1400a5cb9`
- `KERNEL32!GetCurrentThreadId` at `0x1400a5db8`
- `KERNEL32!GetCurrentThreadId` at `0x1400a5e8a`
- `KERNEL32!GetCurrentThreadId` at `0x1400a6013`
- `KERNEL32!GetCurrentThreadId` at `0x1400a6131`
- `KERNEL32!GetCurrentThreadId` at `0x1400a5a7a`
- `KERNEL32!GetCurrentThreadId` at `0x1400a5c07`
- `KERNEL32!GetCurrentThreadId` at `0x1400a5cb9`
- `KERNEL32!GetCurrentThreadId` at `0x1400a5db8`
- `KERNEL32!GetCurrentThreadId` at `0x1400a5e8a`
- `KERNEL32!GetCurrentThreadId` at `0x1400a6013`
- `KERNEL32!GetCurrentThreadId` at `0x1400a6131`

## string_xrefs

- `0x1400a5ba7`: `UsnConsumer::UpdateIdRecord`
- `0x1400a5d59`: `UsnConsumer::UpdateIdRecord`
- `0x1400a5e29`: `UsnConsumer::UpdateIdRecord`
- `0x1400a5f90`: `UsnConsumer::UpdateIdRecord`
- `0x1400a5a99`: `UsnConsumer::UpdateIdRecord`
- `0x1400a5c26`: `UsnConsumer::UpdateIdRecord`
- `0x1400a5c7a`: `UsnConsumer::UpdateIdRecord`
- `0x1400a5e99`: `UsnConsumer::UpdateIdRecord`
- `0x1400a6032`: `UsnConsumer::UpdateIdRecord`
- `0x1400a6150`: `UsnConsumer::UpdateIdRecord`
- `0x1400a60c1`: `Failed to update ID record from USN_RECORD:%?`
- `0x1400a6090`: `ID record updated from USN_RECORD:%?`

## pseudocode

```c
struct FrsStatus *__fastcall UsnConsumer::UpdateIdRecord(
        UsnConsumer *this,
        const struct USN_RECORD_V2 *a2,
        struct ID_RECORD *a3,
        const struct UID *a4,
        const struct Usn *a5)
{
  struct GVSN *v6; // r13
  unsigned int v10; // ecx
  DWORD FileAttributes; // eax
  const unsigned __int16 *v12; // rsi
  __int64 v13; // rcx
  unsigned int *v14; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v16; // rcx
  __int64 v17; // rsi
  __int128 v18; // xmm6
  __int64 v19; // rbx
  int v20; // r12d
  USN Usn; // rax
  unsigned int *v22; // rsi
  DWORD v23; // eax
  __int64 v24; // rcx
  __int64 v25; // rax
  unsigned int *v26; // rbx
  DWORD v27; // eax
  __int64 v28; // rcx
  int v29; // eax
  int v30; // ecx
  unsigned int *v31; // rbx
  DWORD v32; // eax
  __int64 v33; // rcx
  unsigned int *v34; // rbx
  DWORD v35; // eax
  __int64 v36; // rcx
  __int64 v37; // rax
  unsigned int *v38; // rbx
  DWORD v39; // eax
  __int64 v40; // rcx
  const wchar_t *v41; // rdx
  const wchar_t *v42; // rdx
  unsigned int *v43; // rbx
  DWORD v44; // eax
  __int64 v45; // rcx
  const wchar_t *v47; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v48; // [rsp+60h] [rbp-A8h]
  const wchar_t *v49; // [rsp+68h] [rbp-A0h]
  int v50; // [rsp+70h] [rbp-98h] BYREF
  int v51; // [rsp+74h] [rbp-94h]
  DWORDLONG ParentFileReferenceNumber; // [rsp+78h] [rbp-90h] BYREF
  DWORDLONG FileReferenceNumber; // [rsp+80h] [rbp-88h] BYREF
  __int128 v54; // [rsp+88h] [rbp-80h] BYREF
  __int64 v55; // [rsp+98h] [rbp-70h]
  _BYTE v56[688]; // [rsp+A8h] [rbp-60h] BYREF
  _QWORD v57[4]; // [rsp+358h] [rbp+250h] BYREF
  _BYTE v58[140]; // [rsp+378h] [rbp+270h] BYREF
  __int64 v59; // [rsp+404h] [rbp+2FCh]
  char v60; // [rsp+638h] [rbp+530h]

  v6 = (struct ID_RECORD *)((char *)a3 + 24);
  v51 = 0;
  UsnConsumer::GetNextVersion(this, (const struct _GUID *)((char *)a3 + 72), (struct ID_RECORD *)((char *)a3 + 24));
  if ( (a2->Reason & 0x360C77) != 0 || (*((_BYTE *)a3 + 704) & 0x46) != 0 )
  {
    *(_OWORD *)((char *)a3 + 88) = 0;
    *((_DWORD *)a3 + 26) = 0;
    *(_OWORD *)((char *)a3 + 108) = 0;
  }
  *((_OWORD *)a3 + 3) = *(_OWORD *)a4;
  *((_QWORD *)a3 + 8) = *((_QWORD *)a4 + 2);
  v10 = *((_DWORD *)a3 + 176) & 0xFFFFFFB9;
  *((_QWORD *)a3 + 85) = a2->Usn;
  FileAttributes = a2->FileAttributes;
  *((_DWORD *)a3 + 38) &= ~0x10u;
  *((_DWORD *)a3 + 176) = v10 & 0xFFFFFE5F;
  *((_DWORD *)a3 + 37) = FileAttributes;
  UpdateClock((struct _FILETIME *)((char *)a3 + 132), &a2->TimeStamp);
  if ( (!a5 || a2->Usn > *(_QWORD *)a5) && *((_QWORD *)a3 + 2) != 1 )
    ID_UPDATE::PromoteFenceValue(a3);
  v12 = (const unsigned __int16 *)((char *)a3 + 156);
  if ( !(unsigned int)WStringEqual(
                        a2->FileName,
                        (unsigned __int64)a2->FileNameLength >> 1,
                        (const unsigned __int16 *)a3 + 78)
    && (a2->FileAttributes & 0x10) == 0
    && *((_QWORD *)a3 + 2) != 1 )
  {
    v55 = 0;
    v54 = 0;
    ID_RECORD::ID_RECORD((ID_RECORD *)v58);
    ID_RECORD::ID_RECORD((ID_RECORD *)v56);
    v13 = *((_QWORD *)this + 13);
    ParentFileReferenceNumber = a2->ParentFileReferenceNumber;
    FileReferenceNumber = ParentFileReferenceNumber;
    v50 = 0;
    v14 = (unsigned int *)(*(__int64 (__fastcall **)(__int64, int *, char *, _BYTE *))(*(_QWORD *)v13 + 56LL))(
                            v13,
                            &v50,
                            (char *)a3 + 48,
                            v56);
    if ( v14 )
    {
      CurrentThreadId = GetCurrentThreadId();
      v17 = FrsStatusList::PushNewError(
              v16,
              v14[1],
              v14[2],
              *v14,
              "base\\fs\\remotefs\\frs\\src\\db\\usnconsumer.cpp",
              "UsnConsumer::UpdateIdRecord",
              2518,
              CurrentThreadId,
              v14);
      if ( v17 )
        return (struct FrsStatus *)v17;
      v12 = (const unsigned __int16 *)((char *)a3 + 156);
    }
    if ( v50
      && v57[0] == ParentFileReferenceNumber
      && (unsigned int)UsnConsumer::UidTunnelCache::NameExists(
                         (char *)this + 192,
                         &FileReferenceNumber,
                         &a2->TimeStamp,
                         a2->FileName,
                         a2->FileNameLength >> 1,
                         2,
                         &v54,
                         0) )
    {
      if ( (*((_BYTE *)a3 + 704) & 1) != 0 )
      {
        v18 = *(_OWORD *)v6;
        v19 = *((_QWORD *)v6 + 2);
        v20 = *((_DWORD *)a3 + 38);
        UsnConsumer::GetNextVersion(this, (const struct _GUID *)((char *)a3 + 72), v6);
        Usn = a2->Usn;
        *((_DWORD *)a3 + 38) &= 0xFFFFFFEE;
        *((_QWORD *)a3 + 85) = Usn;
        *((_DWORD *)a3 + 176) &= 0xFFFFFE13;
        ID_UPDATE::PromoteFenceValue(a3);
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
        {
          v48 = 0x4000009F4LL;
          v47 = L"UsnConsumer::UpdateIdRecord";
          v49 = L"USNC";
          dbgobj::DbgPrint<unsigned short,ID_RECORD>(&v47, L"LDB Updating ID Record:%?", a3);
        }
        v22 = (unsigned int *)(*(__int64 (__fastcall **)(_QWORD, struct ID_RECORD *, struct ID_RECORD *, _QWORD))(**((_QWORD **)this + 13) + 200LL))(
                                *((_QWORD *)this + 13),
                                a3,
                                a3,
                                0);
        if ( v22 )
        {
          v23 = GetCurrentThreadId();
          v17 = FrsStatusList::PushNewError(
                  v24,
                  v22[1],
                  v22[2],
                  *v22,
                  "base\\fs\\remotefs\\frs\\src\\db\\usnconsumer.cpp",
                  "UsnConsumer::UpdateIdRecord",
                  2549,
                  v23,
                  v22);
          if ( v17 )
            return (struct FrsStatus *)v17;
        }
        *(_OWORD *)v6 = v18;
        *((_QWORD *)v6 + 2) = v19;
        *((_DWORD *)a3 + 38) ^= ((unsigned __int8)v20 ^ (unsigned __int8)*((_DWORD *)a3 + 38)) & 1;
      }
      else
      {
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
        {
          v48 = 0x4000009FDLL;
          v47 = L"UsnConsumer::UpdateIdRecord";
          v49 = L"USNC";
          dbgobj::DbgPrint<unsigned short,GVSN>(&v47, L"LDB Deleting ID Record. uid:%?", a3);
        }
        v34 = (unsigned int *)(*(__int64 (__fastcall **)(_QWORD, struct ID_RECORD *, _QWORD))(**((_QWORD **)this + 13)
                                                                                            + 176LL))(
                                *((_QWORD *)this + 13),
                                a3,
                                0);
        if ( v34 )
        {
          v35 = GetCurrentThreadId();
          v17 = FrsStatusList::PushNewError(
                  v36,
                  v34[1],
                  v34[2],
                  *v34,
                  "base\\fs\\remotefs\\frs\\src\\db\\usnconsumer.cpp",
                  "UsnConsumer::UpdateIdRecord",
                  2558,
                  v35,
                  v34);
          if ( v17 )
            return (struct FrsStatus *)v17;
        }
      }
      v25 = v55;
      *(_OWORD *)a3 = v54;
      *((_QWORD *)a3 + 2) = v25;
      v26 = (unsigned int *)(*(__int64 (__fastcall **)(_QWORD, int *, __int128 *, _BYTE *))(**((_QWORD **)this + 13)
                                                                                          + 56LL))(
                              *((_QWORD *)this + 13),
                              &v50,
                              &v54,
                              v58);
      if ( v26 )
      {
        v27 = GetCurrentThreadId();
        v17 = FrsStatusList::PushNewError(
                v28,
                v26[1],
                v26[2],
                *v26,
                "base\\fs\\remotefs\\frs\\src\\db\\usnconsumer.cpp",
                "UsnConsumer::UpdateIdRecord",
                2566,
                v27,
                v26);
        if ( v17 )
          return (struct FrsStatus *)v17;
      }
      if ( v50 )
      {
        *(_QWORD *)((char *)a3 + 140) = v59;
        v29 = *((_DWORD *)a3 + 176);
        if ( (v29 & 1) != 0 || (v30 = 0, (v60 & 1) != 0) )
          v30 = 1;
        *((_DWORD *)a3 + 176) = v30 | v29 & 0xFFFFFFFE;
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
        {
          v48 = 0x400000A0ELL;
          v47 = L"UsnConsumer::UpdateIdRecord";
          v49 = L"USNC";
          dbgobj::DbgPrint<unsigned short,GVSN>(&v47, L"LDB Deleting ID Record. uid:%?", &v54);
        }
        v31 = (unsigned int *)(*(__int64 (__fastcall **)(_QWORD, __int128 *, _QWORD))(**((_QWORD **)this + 13) + 176LL))(
                                *((_QWORD *)this + 13),
                                &v54,
                                0);
        if ( v31 )
        {
          v32 = GetCurrentThreadId();
          v17 = FrsStatusList::PushNewError(
                  v33,
                  v31[1],
                  v31[2],
                  *v31,
                  "base\\fs\\remotefs\\frs\\src\\db\\usnconsumer.cpp",
                  "UsnConsumer::UpdateIdRecord",
                  2575,
                  v32,
                  v31);
          if ( v17 )
            return (struct FrsStatus *)v17;
        }
      }
      v51 = 1;
    }
    else
    {
      FileReferenceNumber = a2->FileReferenceNumber;
      ParentFileReferenceNumber = a2->ParentFileReferenceNumber;
      UsnConsumer::UidTunnelCache::Update(
        (UsnConsumer *)((char *)this + 192),
        (const struct FileId *)&ParentFileReferenceNumber,
        (const struct FileId *)&FileReferenceNumber,
        &a2->TimeStamp,
        a2->FileName,
        a2->FileNameLength >> 1);
      if ( v57[0] == a2->ParentFileReferenceNumber )
      {
        v37 = -1;
        do
          ++v37;
        while ( v12[v37] );
        UsnConsumer::UidTunnelCache::Add(
          (UsnConsumer *)((char *)this + 192),
          (const struct FileId *)v57,
          (struct ID_RECORD *)((char *)a3 + 688),
          &a2->TimeStamp,
          a3,
          v12,
          (int)v37,
          a2->FileName,
          (unsigned __int64)a2->FileNameLength >> 1);
      }
    }
  }
  ID_UPDATE::Assign(a3, a2->FileName, (unsigned __int64)a2->FileNameLength >> 1);
  if ( v51 )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v47 = L"UsnConsumer::UpdateIdRecord";
      v49 = L"USNC";
      v48 = 0x400000A43LL;
      dbgobj::DbgPrint<unsigned short,ID_RECORD>(&v47, L"LDB Inserting ID Record:%?", a3);
    }
    v43 = (unsigned int *)(*(__int64 (__fastcall **)(_QWORD, struct ID_RECORD *))(**((_QWORD **)this + 13) + 160LL))(
                            *((_QWORD *)this + 13),
                            a3);
    if ( v43 )
    {
      v44 = GetCurrentThreadId();
      v17 = FrsStatusList::PushNewError(
              v45,
              v43[1],
              v43[2],
              *v43,
              "base\\fs\\remotefs\\frs\\src\\db\\usnconsumer.cpp",
              "UsnConsumer::UpdateIdRecord",
              2628,
              v44,
              v43);
    }
    else
    {
      v17 = 0;
    }
    if ( !v17 )
    {
      if ( !g_DebugLog || !LODWORD(g_DebugLog[1].LockSemaphore) || SLODWORD(g_DebugLog[1].OwningThread) < 4 )
        goto LABEL_78;
      LODWORD(v48) = 2630;
      v41 = L"ID record inserted from USN_RECORD:%?";
      goto LABEL_77;
    }
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      LODWORD(v48) = 2632;
      v42 = L"Failed to insert ID record from USN_RECORD:%?";
      goto LABEL_83;
    }
  }
  else
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v47 = L"UsnConsumer::UpdateIdRecord";
      v49 = L"USNC";
      v48 = 0x400000A3ALL;
      dbgobj::DbgPrint<unsigned short,ID_RECORD>(&v47, L"LDB Updating ID Record:%?", a3);
    }
    v38 = (unsigned int *)(*(__int64 (__fastcall **)(_QWORD, struct ID_RECORD *, struct ID_RECORD *, _QWORD))(**((_QWORD **)this + 13) + 200LL))(
                            *((_QWORD *)this + 13),
                            a3,
                            a3,
                            0);
    if ( v38 )
    {
      v39 = GetCurrentThreadId();
      v17 = FrsStatusList::PushNewError(
              v40,
              v38[1],
              v38[2],
              *v38,
              "base\\fs\\remotefs\\frs\\src\\db\\usnconsumer.cpp",
              "UsnConsumer::UpdateIdRecord",
              2619,
              v39,
              v38);
    }
    else
    {
      v17 = 0;
    }
    if ( !v17 )
    {
      if ( !g_DebugLog || !LODWORD(g_DebugLog[1].LockSemaphore) || SLODWORD(g_DebugLog[1].OwningThread) < 4 )
        goto LABEL_78;
      LODWORD(v48) = 2621;
      v41 = L"ID record updated from USN_RECORD:%?";
LABEL_77:
      v47 = L"UsnConsumer::UpdateIdRecord";
      v49 = L"USNC";
      HIDWORD(v48) = 4;
      dbgobj::DbgPrint<unsigned short,USN_RECORD_V2>(&v47, v41, a2);
LABEL_78:
      ++*((_DWORD *)this + 24);
      *((_DWORD *)this + 84) = 1;
      return (struct FrsStatus *)v17;
    }
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      LODWORD(v48) = 2623;
      v42 = L"Failed to update ID record from USN_RECORD:%?";
LABEL_83:
      v47 = L"UsnConsumer::UpdateIdRecord";
      v49 = L"USNC";
      HIDWORD(v48) = 4;
      dbgobj::DbgPrint<unsigned short,USN_RECORD_V2>(&v47, v42, a2);
    }
  }
  return (struct FrsStatus *)v17;
}

```

## disassembly

```asm
0x1400a58f0  mov     rax, rsp
0x1400a58f3  mov     [rax+20h], rbx
0x1400a58f7  push    rbp
0x1400a58f8  push    rsi
0x1400a58f9  push    rdi
0x1400a58fa  push    r12
0x1400a58fc  push    r13
0x1400a58fe  push    r14
0x1400a5900  push    r15
0x1400a5902  lea     rbp, [rax-598h]
0x1400a5909  sub     rsp, 660h
0x1400a5910  movaps  xmmword ptr [rax-48h], xmm6
0x1400a5914  mov     rax, cs:__security_cookie
0x1400a591b  xor     rax, rsp
0x1400a591e  mov     [rbp+590h+var_50], rax
0x1400a5925  mov     r14, rdx
0x1400a5928  lea     r13, [r8+18h]
0x1400a592c  lea     rdx, [r8+48h]; struct _GUID *
0x1400a5930  mov     rdi, r8
0x1400a5933  xor     eax, eax
0x1400a5935  mov     r8, r13; struct GVSN *
0x1400a5938  mov     rbx, r9
0x1400a593b  mov     dword ptr [rsp+690h+var_628+4], eax
0x1400a593f  mov     r15, rcx
0x1400a5942  call    ?GetNextVersion@UsnConsumer@@AEAAXAEBU_GUID@@AEAVGVSN@@@Z; UsnConsumer::GetNextVersion(_GUID const &,GVSN &)
0x1400a5947  test    dword ptr [r14+28h], 360C77h
0x1400a594f  setz    cl
0x1400a5952  test    byte ptr [rdi+2C0h], 46h
0x1400a5959  setz    al
0x1400a595c  test    al, cl
0x1400a595e  jnz     short loc_1400A5970
0x1400a5960  xorps   xmm0, xmm0
0x1400a5963  xor     eax, eax
0x1400a5965  movups  xmmword ptr [rdi+58h], xmm0
0x1400a5969  mov     [rdi+68h], eax
0x1400a596c  movups  xmmword ptr [rdi+6Ch], xmm0
0x1400a5970  movups  xmm0, xmmword ptr [rbx]
0x1400a5973  lea     r12, [r14+20h]
0x1400a5977  mov     rdx, r12; union _LARGE_INTEGER *
0x1400a597a  movdqu  xmmword ptr [rdi+30h], xmm0
0x1400a597f  mov     rax, [rbx+10h]
0x1400a5983  mov     [rdi+40h], rax
0x1400a5987  mov     rax, [r14+18h]
0x1400a598b  mov     ecx, [rdi+2C0h]
0x1400a5991  and     ecx, 0FFFFFFB9h
0x1400a5994  mov     [rdi+2A8h], rax
0x1400a599b  mov     eax, [r14+34h]
0x1400a599f  and     ecx, 0FFFFFE5Fh
0x1400a59a5  and     dword ptr [rdi+98h], 0FFFFFFEFh
0x1400a59ac  mov     [rdi+2C0h], ecx
0x1400a59b2  lea     rcx, [rdi+84h]; struct _FILETIME *
0x1400a59b9  mov     [rdi+94h], eax
0x1400a59bf  call    ?UpdateClock@@YAXAEAU_FILETIME@@AEBT_LARGE_INTEGER@@@Z; UpdateClock(_FILETIME &,_LARGE_INTEGER const &)
0x1400a59c4  mov     rax, [rbp+590h+arg_20]
0x1400a59cb  xor     ebx, ebx
0x1400a59cd  test    rax, rax
0x1400a59d0  jz      short loc_1400A59DB
0x1400a59d2  mov     rax, [rax]
0x1400a59d5  cmp     [r14+18h], rax
0x1400a59d9  jle     short loc_1400A59EA
0x1400a59db  cmp     qword ptr [rdi+10h], 1
0x1400a59e0  jz      short loc_1400A59EA
0x1400a59e2  mov     rcx, rdi; this
0x1400a59e5  call    ?PromoteFenceValue@ID_UPDATE@@QEAAXXZ; ID_UPDATE::PromoteFenceValue(void)
0x1400a59ea  movzx   edx, word ptr [r14+38h]
0x1400a59ef  lea     rsi, [rdi+9Ch]
0x1400a59f6  shr     rdx, 1; unsigned __int64
0x1400a59f9  lea     rcx, [r14+3Ch]; unsigned __int16 *
0x1400a59fd  mov     r8, rsi; unsigned __int16 *
0x1400a5a00  call    ?WStringEqual@@YAHPEBG_K0@Z; WStringEqual(ushort const *,unsigned __int64,ushort const *)
0x1400a5a05  test    eax, eax
0x1400a5a07  jnz     loc_1400A5F79
0x1400a5a0d  test    byte ptr [r14+34h], 10h
0x1400a5a12  jnz     loc_1400A5F79
0x1400a5a18  cmp     qword ptr [rdi+10h], 1
0x1400a5a1d  jz      loc_1400A5F79
0x1400a5a23  xorps   xmm0, xmm0
0x1400a5a26  mov     [rbp+590h+var_600], rbx
0x1400a5a2a  lea     rcx, [rbp+590h+var_320]; this
0x1400a5a31  movups  [rbp+590h+var_610], xmm0
0x1400a5a35  call    ??0ID_RECORD@@QEAA@XZ; ID_RECORD::ID_RECORD(void)
0x1400a5a3a  lea     rcx, [rbp+590h+var_5F0]; this
0x1400a5a3e  call    ??0ID_RECORD@@QEAA@XZ; ID_RECORD::ID_RECORD(void)
0x1400a5a43  mov     rax, [r14+10h]
0x1400a5a47  lea     r9, [rbp+590h+var_5F0]
0x1400a5a4b  mov     rcx, [r15+68h]
0x1400a5a4f  lea     r8, [rdi+30h]
0x1400a5a53  mov     [rsp+690h+var_620], rax
0x1400a5a58  lea     rdx, [rsp+690h+var_628]
0x1400a5a5d  mov     [rsp+690h+var_618], rax
0x1400a5a62  mov     dword ptr [rsp+690h+var_628], ebx
0x1400a5a66  mov     rax, [rcx]
0x1400a5a69  mov     rax, [rax+38h]
0x1400a5a6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a5a72  mov     rbx, rax
0x1400a5a75  test    rax, rax
0x1400a5a78  jz      short loc_1400A5AD5
0x1400a5a7a  call    cs:__imp_GetCurrentThreadId
0x1400a5a81  nop     dword ptr [rax+rax+00h]
0x1400a5a86  mov     r9d, [rbx]
0x1400a5a89  mov     r8d, [rbx+8]
0x1400a5a8d  mov     edx, [rbx+4]
0x1400a5a90  mov     [rsp+690h+var_650], rbx
0x1400a5a95  mov     dword ptr [rsp+690h+var_658], eax
0x1400a5a99  lea     rax, aUsnconsumerUpd_1; "UsnConsumer::UpdateIdRecord"
0x1400a5aa0  mov     dword ptr [rsp+690h+var_660], 9D6h
0x1400a5aa8  mov     [rsp+690h+var_668], rax
0x1400a5aad  lea     rax, aBaseFsRemotefs_51; "base\\fs\\remotefs\\frs\\src\\db\\usnco"...
0x1400a5ab4  mov     [rsp+690h+var_670], rax
0x1400a5ab9  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400a5abe  xor     ebx, ebx
0x1400a5ac0  mov     rsi, rax
0x1400a5ac3  test    rax, rax
0x1400a5ac6  jnz     loc_1400A6226
0x1400a5acc  lea     rsi, [rdi+9Ch]
0x1400a5ad3  jmp     short loc_1400A5AD7
0x1400a5ad5  xor     ebx, ebx
0x1400a5ad7  cmp     dword ptr [rsp+690h+var_628], ebx
0x1400a5adb  jz      loc_1400A5EDF
0x1400a5ae1  mov     rax, [rsp+690h+var_620]
0x1400a5ae6  cmp     [rbp+590h+var_340], rax
0x1400a5aed  jnz     loc_1400A5EDF
0x1400a5af3  movzx   eax, word ptr [r14+38h]
0x1400a5af8  lea     rdx, [rbp+590h+var_610]
0x1400a5afc  mov     [rsp+690h+var_658], rbx
0x1400a5b01  lea     rcx, [r15+0C0h]
0x1400a5b08  mov     [rsp+690h+var_660], rdx
0x1400a5b0d  lea     r9, [r14+3Ch]
0x1400a5b11  shr     eax, 1
0x1400a5b13  lea     rdx, [rsp+690h+var_618]
0x1400a5b18  mov     dword ptr [rsp+690h+var_668], 2
0x1400a5b20  mov     r8, r12
0x1400a5b23  mov     dword ptr [rsp+690h+var_670], eax
0x1400a5b27  call    ?NameExists@UidTunnelCache@UsnConsumer@@QEAAHAEBVFileId@@AEBT_LARGE_INTEGER@@PEBGHW4NAME_STATE@12@AEAVUID@@PEAV3@@Z; UsnConsumer::UidTunnelCache::NameExists(FileId const &,_LARGE_INTEGER const &,ushort const *,int,UsnConsumer::UidTunnelCache::NAME_STATE,UID &,FileId *)
0x1400a5b2c  test    eax, eax
0x1400a5b2e  jz      loc_1400A5EDF
0x1400a5b34  test    byte ptr [rdi+2C0h], 1
0x1400a5b3b  jz      loc_1400A5E0E
0x1400a5b41  movups  xmm6, xmmword ptr [r13+0]
0x1400a5b46  mov     rbx, [r13+10h]
0x1400a5b4a  lea     rdx, [rdi+48h]; struct _GUID *
0x1400a5b4e  mov     r12d, [rdi+98h]
0x1400a5b55  mov     r8, r13; struct GVSN *
0x1400a5b58  mov     rcx, r15; this
0x1400a5b5b  call    ?GetNextVersion@UsnConsumer@@AEAAXAEBU_GUID@@AEAVGVSN@@@Z; UsnConsumer::GetNextVersion(_GUID const &,GVSN &)
0x1400a5b60  mov     rax, [r14+18h]
0x1400a5b64  mov     rcx, rdi; this
0x1400a5b67  and     dword ptr [rdi+98h], 0FFFFFFEEh
0x1400a5b6e  mov     [rdi+2A8h], rax
0x1400a5b75  mov     eax, [rdi+2C0h]
0x1400a5b7b  and     eax, 0FFFFFFB3h
0x1400a5b7e  and     eax, 0FFFFFE5Fh
0x1400a5b83  mov     [rdi+2C0h], eax
0x1400a5b89  call    ?PromoteFenceValue@ID_UPDATE@@QEAAXXZ; ID_UPDATE::PromoteFenceValue(void)
0x1400a5b8e  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400a5b95  xor     ecx, ecx
0x1400a5b97  test    rax, rax
0x1400a5b9a  jz      short loc_1400A5BE3
0x1400a5b9c  cmp     [rax+40h], ecx
0x1400a5b9f  jz      short loc_1400A5BE3
0x1400a5ba1  cmp     dword ptr [rax+38h], 4
0x1400a5ba5  jl      short loc_1400A5BE3
0x1400a5ba7  lea     rax, aUsnconsumerUpd_0; "UsnConsumer::UpdateIdRecord"
0x1400a5bae  mov     dword ptr [rsp+690h+var_638], 9F4h
0x1400a5bb6  mov     [rsp+690h+var_640], rax
0x1400a5bbb  lea     rdx, aLdbUpdatingIdR; "LDB Updating ID Record:%?"
0x1400a5bc2  lea     rax, aUsnc; "USNC"
0x1400a5bc9  mov     dword ptr [rsp+690h+var_638+4], 4
0x1400a5bd1  mov     r8, rdi
0x1400a5bd4  mov     [rsp+690h+var_630], rax
0x1400a5bd9  lea     rcx, [rsp+690h+var_640]
0x1400a5bde  call    ??$DbgPrint@GVID_RECORD@@@dbgobj@@QEAA_KPEBGAEBVID_RECORD@@@Z; dbgobj::DbgPrint<ushort,ID_RECORD>(ushort const *,ID_RECORD const &)
0x1400a5be3  mov     rcx, [r15+68h]
0x1400a5be7  xor     r9d, r9d
0x1400a5bea  mov     r8, rdi
0x1400a5bed  mov     rdx, rdi
0x1400a5bf0  mov     rax, [rcx]
0x1400a5bf3  mov     rax, [rax+0C8h]
0x1400a5bfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a5bff  mov     rsi, rax
0x1400a5c02  test    rax, rax
0x1400a5c05  jz      short loc_1400A5C57
0x1400a5c07  call    cs:__imp_GetCurrentThreadId
0x1400a5c0e  nop     dword ptr [rax+rax+00h]
0x1400a5c13  mov     r9d, [rsi]
0x1400a5c16  mov     r8d, [rsi+8]
0x1400a5c1a  mov     edx, [rsi+4]
0x1400a5c1d  mov     [rsp+690h+var_650], rsi
0x1400a5c22  mov     dword ptr [rsp+690h+var_658], eax
0x1400a5c26  lea     rax, aUsnconsumerUpd_1; "UsnConsumer::UpdateIdRecord"
0x1400a5c2d  mov     dword ptr [rsp+690h+var_660], 9F5h
0x1400a5c35  mov     [rsp+690h+var_668], rax
0x1400a5c3a  lea     rax, aBaseFsRemotefs_51; "base\\fs\\remotefs\\frs\\src\\db\\usnco"...
0x1400a5c41  mov     [rsp+690h+var_670], rax
0x1400a5c46  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400a5c4b  mov     rsi, rax
0x1400a5c4e  test    rax, rax
0x1400a5c51  jnz     loc_1400A6226
0x1400a5c57  movdqu  xmmword ptr [r13+0], xmm6
0x1400a5c5d  mov     [r13+10h], rbx
0x1400a5c61  mov     eax, [rdi+98h]
0x1400a5c67  mov     ecx, eax
0x1400a5c69  xor     ecx, r12d
0x1400a5c6c  and     ecx, 1
0x1400a5c6f  xor     ecx, eax
0x1400a5c71  mov     [rdi+98h], ecx
0x1400a5c77  xor     r12d, r12d
0x1400a5c7a  lea     r13, aUsnconsumerUpd_1; "UsnConsumer::UpdateIdRecord"
0x1400a5c81  mov     rax, [rbp+590h+var_600]
0x1400a5c85  lea     r9, [rbp+590h+var_320]
0x1400a5c8c  movups  xmm0, [rbp+590h+var_610]
0x1400a5c90  lea     r8, [rbp+590h+var_610]
0x1400a5c94  lea     rdx, [rsp+690h+var_628]
0x1400a5c99  movdqu  xmmword ptr [rdi], xmm0
0x1400a5c9d  mov     [rdi+10h], rax
0x1400a5ca1  mov     rcx, [r15+68h]
0x1400a5ca5  mov     rax, [rcx]
0x1400a5ca8  mov     rax, [rax+38h]
0x1400a5cac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a5cb1  mov     rbx, rax
0x1400a5cb4  test    rax, rax
0x1400a5cb7  jz      short loc_1400A5D02
0x1400a5cb9  call    cs:__imp_GetCurrentThreadId
0x1400a5cc0  nop     dword ptr [rax+rax+00h]
0x1400a5cc5  mov     r9d, [rbx]
0x1400a5cc8  mov     r8d, [rbx+8]
0x1400a5ccc  mov     edx, [rbx+4]
0x1400a5ccf  mov     [rsp+690h+var_650], rbx
0x1400a5cd4  mov     dword ptr [rsp+690h+var_658], eax
0x1400a5cd8  lea     rax, aBaseFsRemotefs_51; "base\\fs\\remotefs\\frs\\src\\db\\usnco"...
0x1400a5cdf  mov     dword ptr [rsp+690h+var_660], 0A06h
0x1400a5ce7  mov     [rsp+690h+var_668], r13
0x1400a5cec  mov     [rsp+690h+var_670], rax
0x1400a5cf1  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400a5cf6  mov     rsi, rax
0x1400a5cf9  test    rax, rax
0x1400a5cfc  jnz     loc_1400A6226
0x1400a5d02  cmp     dword ptr [rsp+690h+var_628], r12d
0x1400a5d07  jz      loc_1400A5E01
0x1400a5d0d  mov     rax, [rbp+590h+var_294]
0x1400a5d14  mov     [rdi+8Ch], rax
0x1400a5d1b  mov     eax, [rdi+2C0h]
0x1400a5d21  test    al, 1
0x1400a5d23  jnz     short loc_1400A5D31
0x1400a5d25  test    [rbp+590h+var_60], 1
0x1400a5d2c  mov     ecx, r12d
0x1400a5d2f  jz      short loc_1400A5D36
0x1400a5d31  mov     ecx, 1
0x1400a5d36  and     eax, 0FFFFFFFEh
0x1400a5d39  or      eax, ecx
0x1400a5d3b  mov     [rdi+2C0h], eax
0x1400a5d41  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400a5d48  test    rax, rax
0x1400a5d4b  jz      short loc_1400A5D96
0x1400a5d4d  cmp     [rax+40h], r12d
0x1400a5d51  jz      short loc_1400A5D96
0x1400a5d53  cmp     dword ptr [rax+38h], 4
0x1400a5d57  jl      short loc_1400A5D96
0x1400a5d59  lea     rax, aUsnconsumerUpd_0; "UsnConsumer::UpdateIdRecord"
0x1400a5d60  mov     dword ptr [rsp+690h+var_638], 0A0Eh
0x1400a5d68  mov     [rsp+690h+var_640], rax
0x1400a5d6d  lea     r8, [rbp+590h+var_610]
0x1400a5d71  lea     rax, aUsnc; "USNC"
0x1400a5d78  mov     dword ptr [rsp+690h+var_638+4], 4
0x1400a5d80  lea     rdx, aLdbDeletingIdR; "LDB Deleting ID Record. uid:%?"
0x1400a5d87  mov     [rsp+690h+var_630], rax
0x1400a5d8c  lea     rcx, [rsp+690h+var_640]
0x1400a5d91  call    ??$DbgPrint@GVGVSN@@@dbgobj@@QEAA_KPEBGAEBVGVSN@@@Z; dbgobj::DbgPrint<ushort,GVSN>(ushort const *,GVSN const &)
0x1400a5d96  mov     rcx, [r15+68h]
0x1400a5d9a  lea     rdx, [rbp+590h+var_610]
0x1400a5d9e  xor     r8d, r8d
0x1400a5da1  mov     rax, [rcx]
0x1400a5da4  mov     rax, [rax+0B0h]
0x1400a5dab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a5db0  mov     rbx, rax
0x1400a5db3  test    rax, rax
0x1400a5db6  jz      short loc_1400A5E01
0x1400a5db8  call    cs:__imp_GetCurrentThreadId
0x1400a5dbf  nop     dword ptr [rax+rax+00h]
0x1400a5dc4  mov     r9d, [rbx]
0x1400a5dc7  mov     r8d, [rbx+8]
0x1400a5dcb  mov     edx, [rbx+4]
0x1400a5dce  mov     [rsp+690h+var_650], rbx
0x1400a5dd3  mov     dword ptr [rsp+690h+var_658], eax
0x1400a5dd7  lea     rax, aBaseFsRemotefs_51; "base\\fs\\remotefs\\frs\\src\\db\\usnco"...
0x1400a5dde  mov     dword ptr [rsp+690h+var_660], 0A0Fh
0x1400a5de6  mov     [rsp+690h+var_668], r13
0x1400a5deb  mov     [rsp+690h+var_670], rax
0x1400a5df0  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400a5df5  mov     rsi, rax
0x1400a5df8  test    rax, rax
0x1400a5dfb  jnz     loc_1400A6226
0x1400a5e01  mov     dword ptr [rsp+690h+var_628+4], 1
0x1400a5e09  jmp     loc_1400A5F7C
0x1400a5e0e  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400a5e15  xor     r12d, r12d
0x1400a5e18  test    rax, rax
0x1400a5e1b  jz      short loc_1400A5E65
0x1400a5e1d  cmp     [rax+40h], r12d
0x1400a5e21  jz      short loc_1400A5E65
  ... truncated ...
```
