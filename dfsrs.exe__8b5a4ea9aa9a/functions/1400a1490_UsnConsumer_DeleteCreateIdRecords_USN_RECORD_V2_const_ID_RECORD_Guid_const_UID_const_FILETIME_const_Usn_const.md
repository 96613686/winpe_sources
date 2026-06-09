# UsnConsumer::DeleteCreateIdRecords(USN_RECORD_V2 const &,ID_RECORD &,Guid const &,UID const &,_FILETIME const &,Usn const &)

- ea: `0x1400a1490`
- end: `0x1400a19da`
- name: `?DeleteCreateIdRecords@UsnConsumer@@AEAAPEAVFrsStatus@@AEBUUSN_RECORD_V2@@AEAVID_RECORD@@AEBVGuid@@AEBVUID@@AEBU_FILETIME@@AEBVUsn@@@Z`
- size: `1354`
- prototype: `struct FrsStatus *__usercall@<rax>(UsnConsumer *__hidden this@<rcx>, const struct USN_RECORD_V2 *@<rdx>, struct ID_RECORD *@<r8>, const struct Guid *@<r9>, const struct UID *, const struct _FILETIME *, const struct Usn *)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task`

## callers

- `0x1400a2d5c`

## callees

- `0x1400036a0`
- `0x140024be4`
- `0x140028fcc`
- `0x140088fd8`
- `0x14009a000`
- `0x14009a288`
- `0x14009fd58`
- `0x1400a05b8`
- `0x1400a11f4`
- `0x1400a1490`
- `0x1400a450c`
- `0x1400a4ac0`
- `0x1400a6aec`
- `0x1401b9494`
- `0x140223010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x1400a193f`
- `KERNEL32!WaitForSingleObject` at `0x1400a193f`
- `KERNEL32!LeaveCriticalSection` at `0x1400a1929`
- `KERNEL32!LeaveCriticalSection` at `0x1400a1929`
- `KERNEL32!EnterCriticalSection` at `0x1400a19a0`
- `KERNEL32!EnterCriticalSection` at `0x1400a19a0`
- `KERNEL32!GetCurrentThreadId` at `0x1400a1575`
- `KERNEL32!GetCurrentThreadId` at `0x1400a15b5`
- `KERNEL32!GetCurrentThreadId` at `0x1400a1679`
- `KERNEL32!GetCurrentThreadId` at `0x1400a172a`
- `KERNEL32!GetCurrentThreadId` at `0x1400a17c5`
- `KERNEL32!GetCurrentThreadId` at `0x1400a1825`
- `KERNEL32!GetCurrentThreadId` at `0x1400a1952`
- `KERNEL32!GetCurrentThreadId` at `0x1400a1575`
- `KERNEL32!GetCurrentThreadId` at `0x1400a15b5`
- `KERNEL32!GetCurrentThreadId` at `0x1400a1679`
- `KERNEL32!GetCurrentThreadId` at `0x1400a172a`
- `KERNEL32!GetCurrentThreadId` at `0x1400a17c5`
- `KERNEL32!GetCurrentThreadId` at `0x1400a1825`
- `KERNEL32!GetCurrentThreadId` at `0x1400a1952`

## string_xrefs

- `0x1400a1520`: `UsnConsumer::DeleteCreateIdRecords`
- `0x1400a15d2`: `UsnConsumer::DeleteCreateIdRecords`
- `0x1400a1696`: `UsnConsumer::DeleteCreateIdRecords`
- `0x1400a1747`: `UsnConsumer::DeleteCreateIdRecords`
- `0x1400a17e2`: `UsnConsumer::DeleteCreateIdRecords`
- `0x1400a1842`: `UsnConsumer::DeleteCreateIdRecords`
- `0x1400a196f`: `UsnConsumer::DeleteCreateIdRecords`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct FrsStatus *__fastcall UsnConsumer::DeleteCreateIdRecords(
        UsnConsumer *this,
        const struct USN_RECORD_V2 *a2,
        struct ID_RECORD *a3,
        struct _GUID *a4,
        const struct UID *a5,
        struct _FILETIME *a6,
        const struct Usn *a7)
{
  int v10; // r15d
  struct FrsStatus *v11; // rbx
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rbx
  struct FrsStatus *v15; // rbx
  __int64 v16; // rcx
  struct FrsStatus *NewRecord; // rbx
  DWORD v18; // eax
  __int64 v19; // rcx
  unsigned int *v20; // rbx
  DWORD v21; // eax
  __int64 v22; // rcx
  unsigned int *v23; // rbx
  DWORD v24; // eax
  __int64 v25; // rcx
  struct FrsStatus *v26; // rbx
  DWORD v27; // eax
  __int64 v28; // rcx
  __int64 v29; // rdx
  const unsigned __int16 *v30; // rax
  DWORD v31; // eax
  __int64 v32; // rcx
  int v34; // [rsp+28h] [rbp-D8h]
  DWORD CurrentThreadId; // [rsp+38h] [rbp-C8h]
  DWORD v36; // [rsp+38h] [rbp-C8h]
  void *v37; // [rsp+48h] [rbp-B8h]
  struct _FILETIME *FileReferenceNumber; // [rsp+60h] [rbp-A0h] BYREF
  int v39; // [rsp+68h] [rbp-98h]
  struct _GUID *v40; // [rsp+70h] [rbp-90h]
  const wchar_t *v41; // [rsp+78h] [rbp-88h] BYREF
  int v42; // [rsp+80h] [rbp-80h]
  int v43; // [rsp+84h] [rbp-7Ch]
  const wchar_t *v44; // [rsp+88h] [rbp-78h]
  __int128 v45; // [rsp+90h] [rbp-70h] BYREF
  __int64 v46; // [rsp+A0h] [rbp-60h]
  LARGE_INTEGER TimeStamp; // [rsp+A8h] [rbp-58h]
  __int64 v48; // [rsp+B0h] [rbp-50h]
  __int128 v49; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v50; // [rsp+C8h] [rbp-38h]
  _BYTE v51[32]; // [rsp+D0h] [rbp-30h] BYREF

  v40 = a4;
  FileReferenceNumber = a6;
  std::wstring::wstring(v51, a2->FileName, (unsigned __int64)a2->FileNameLength >> 1);
  v45 = 0;
  v46 = 0;
  v49 = 0;
  v50 = 0;
  v10 = 0;
  v39 = 1;
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v41 = L"UsnConsumer::DeleteCreateIdRecords";
    v42 = 2689;
    v43 = 4;
    v44 = L"USNC";
    dbgobj::DbgPrint<unsigned short,USN_RECORD_V2>(&v41, L"File tombstoned from USN_RECORD:%?", a2);
  }
  if ( (a2->FileAttributes & 0x10) != 0 )
  {
    v11 = UsnConsumer::SetPendingTombstoneFlag(this, a3, a2);
    if ( !v11 )
    {
      v14 = 0;
      goto LABEL_12;
    }
    CurrentThreadId = GetCurrentThreadId();
    v13 = FrsStatusList::PushNewError(
            v12,
            *((unsigned int *)v11 + 1),
            *((unsigned int *)v11 + 2),
            *(unsigned int *)v11,
            "base\\fs\\remotefs\\frs\\src\\db\\usnconsumer.cpp",
            "UsnConsumer::DeleteCreateIdRecords",
            2695,
            CurrentThreadId,
            v11);
LABEL_11:
    v14 = v13;
LABEL_12:
    if ( v14 )
      goto LABEL_36;
    goto LABEL_15;
  }
  v15 = UsnConsumer::TombstoneOrDelete(this, a3, a2, 0, 1, 0);
  if ( v15 )
  {
    v36 = GetCurrentThreadId();
    v13 = FrsStatusList::PushNewError(
            v16,
            *((unsigned int *)v15 + 1),
            *((unsigned int *)v15 + 2),
            *(unsigned int *)v15,
            "base\\fs\\remotefs\\frs\\src\\db\\usnconsumer.cpp",
            "UsnConsumer::DeleteCreateIdRecords",
            2697,
            v36,
            v15);
    goto LABEL_11;
  }
  v14 = 0;
LABEL_15:
  if ( !(unsigned int)FilterMan::Match(
                        *((FilterMan **)this + 26),
                        v40,
                        a2->FileName,
                        a2->FileNameLength >> 1,
                        (a2->FileAttributes >> 4) & 1,
                        v34) )
  {
    NewRecord = UsnConsumer::CreateNewRecord(
                  this,
                  a2,
                  (const struct Guid *)v40,
                  a5,
                  FileReferenceNumber,
                  a7,
                  (struct UID *)&v49);
    if ( NewRecord )
    {
      v18 = GetCurrentThreadId();
      v14 = FrsStatusList::PushNewError(
              v19,
              *((unsigned int *)NewRecord + 1),
              *((unsigned int *)NewRecord + 2),
              *(unsigned int *)NewRecord,
              "base\\fs\\remotefs\\frs\\src\\db\\usnconsumer.cpp",
              "UsnConsumer::DeleteCreateIdRecords",
              2709,
              v18,
              NewRecord);
      if ( v14 )
        goto LABEL_36;
    }
    else
    {
      v14 = 0;
    }
    v10 = 1;
  }
  if ( (a2->FileAttributes & 0x10) != 0 )
  {
    v45 = *(_OWORD *)a3;
    v46 = *((_QWORD *)a3 + 2);
    TimeStamp = a2->TimeStamp;
    v48 = 2;
    v20 = (unsigned int *)(*(__int64 (__fastcall **)(_QWORD, __int128 *, _QWORD))(**((_QWORD **)this + 13) + 240LL))(
                            *((_QWORD *)this + 13),
                            &v45,
                            0);
    if ( !v20
      || (v21 = GetCurrentThreadId(),
          (v14 = FrsStatusList::PushNewError(
                   v22,
                   v20[1],
                   v20[2],
                   *v20,
                   "base\\fs\\remotefs\\frs\\src\\db\\usnconsumer.cpp",
                   "UsnConsumer::DeleteCreateIdRecords",
                   2723,
                   v21,
                   v20)) == 0) )
    {
      if ( !v10
        || (v45 = v49,
            v46 = v50,
            TimeStamp = a2->TimeStamp,
            v48 = 1,
            (v23 = (unsigned int *)(*(__int64 (__fastcall **)(_QWORD, __int128 *, _QWORD))(**((_QWORD **)this + 13)
                                                                                         + 240LL))(
                                     *((_QWORD *)this + 13),
                                     &v45,
                                     0)) == 0)
        || (v24 = GetCurrentThreadId(),
            (v14 = FrsStatusList::PushNewError(
                     v25,
                     v23[1],
                     v23[2],
                     *v23,
                     "base\\fs\\remotefs\\frs\\src\\db\\usnconsumer.cpp",
                     "UsnConsumer::DeleteCreateIdRecords",
                     2733,
                     v24,
                     v23)) == 0) )
      {
        v26 = UsnConsumer::CheckPoint(this);
        if ( v26 )
        {
          v27 = GetCurrentThreadId();
          v14 = FrsStatusList::PushNewError(
                  v28,
                  *((unsigned int *)v26 + 1),
                  *((unsigned int *)v26 + 2),
                  *(unsigned int *)v26,
                  "base\\fs\\remotefs\\frs\\src\\db\\usnconsumer.cpp",
                  "UsnConsumer::DeleteCreateIdRecords",
                  2741,
                  v27,
                  v26);
          if ( v14 )
            goto LABEL_36;
        }
        else
        {
          v14 = 0;
        }
        v29 = *((_QWORD *)this + 28);
        FileReferenceNumber = (struct _FILETIME *)a2->FileReferenceNumber;
        LODWORD(v37) = 0;
        DirWalkerTask::QueueMoveoutJob(
          *((_QWORD *)this + 27),
          &a2->TimeStamp,
          a3,
          (char *)a3 + 72,
          &FileReferenceNumber,
          0,
          0,
          0,
          v29);
        if ( v10 )
        {
          v30 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v51);
          FileReferenceNumber = (struct _FILETIME *)a2->FileReferenceNumber;
          DirWalkerTask::QueueMoveinJob(
            *((DirWalkerTask **)this + 27),
            v40,
            (const struct FileId *)&FileReferenceNumber,
            v30,
            &a2->TimeStamp,
            (const struct UID *)&v49,
            0,
            0,
            0,
            v37,
            0);
        }
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
        WaitForSingleObject(*((HANDLE *)this + 28), 0xFFFFFFFF);
        if ( !v39 )
        {
          v31 = GetCurrentThreadId();
          v14 = FrsStatusList::PushNewError(
                  v32,
                  9014,
                  0,
                  3,
                  "base\\fs\\remotefs\\frs\\src\\db\\usnconsumer.cpp",
                  "UsnConsumer::DeleteCreateIdRecords",
                  2775,
                  v31,
                  0);
        }
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
      }
    }
  }
LABEL_36:
  std::wstring::~wstring(v51);
  return (struct FrsStatus *)v14;
}

```

## disassembly

```asm
0x1400a1490  push    rbp
0x1400a1492  push    rbx
0x1400a1493  push    rsi
0x1400a1494  push    rdi
0x1400a1495  push    r12
0x1400a1497  push    r13
0x1400a1499  push    r14
0x1400a149b  push    r15
0x1400a149d  lea     rbp, [rsp-8]
0x1400a14a2  sub     rsp, 108h
0x1400a14a9  mov     rax, cs:__security_cookie
0x1400a14b0  xor     rax, rsp
0x1400a14b3  mov     [rbp+40h+var_50], rax
0x1400a14b7  mov     [rsp+140h+var_D0], r9
0x1400a14bc  mov     r13, r8
0x1400a14bf  mov     rsi, rdx
0x1400a14c2  mov     rdi, rcx
0x1400a14c5  mov     r12, [rbp+40h+arg_20]
0x1400a14c9  mov     rax, [rbp+40h+arg_28]
0x1400a14cd  mov     [rsp+140h+var_E0], rax
0x1400a14d2  movzx   r8d, word ptr [rdx+38h]
0x1400a14d7  shr     r8, 1
0x1400a14da  add     rdx, 3Ch ; '<'
0x1400a14de  lea     rcx, [rbp+40h+var_70]
0x1400a14e2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG_K@Z; std::wstring::wstring(ushort const * const,unsigned __int64)
0x1400a14e7  nop
0x1400a14e8  xorps   xmm0, xmm0
0x1400a14eb  movups  [rbp+40h+var_B0], xmm0
0x1400a14ef  and     [rbp+40h+var_A0], 0
0x1400a14f4  movups  [rbp+40h+var_88], xmm0
0x1400a14f8  and     [rbp+40h+var_78], 0
0x1400a14fd  xor     r15d, r15d
0x1400a1500  mov     [rsp+140h+var_D8], 1
0x1400a1508  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400a150f  test    rax, rax
0x1400a1512  jz      short loc_1400A1559
0x1400a1514  cmp     [rax+40h], r15d
0x1400a1518  jz      short loc_1400A1559
0x1400a151a  cmp     dword ptr [rax+38h], 4
0x1400a151e  jl      short loc_1400A1559
0x1400a1520  lea     rax, aUsnconsumerDel_0; "UsnConsumer::DeleteCreateIdRecords"
0x1400a1527  mov     [rsp+140h+var_C8], rax
0x1400a152c  mov     [rbp+40h+var_C0], 0A81h
0x1400a1533  mov     [rbp+40h+var_BC], 4
0x1400a153a  lea     rax, aUsnc; "USNC"
0x1400a1541  mov     [rbp+40h+var_B8], rax
0x1400a1545  mov     r8, rsi
0x1400a1548  lea     rdx, aFileTombstoned; "File tombstoned from USN_RECORD:%?"
0x1400a154f  lea     rcx, [rsp+140h+var_C8]
0x1400a1554  call    ??$DbgPrint@GUUSN_RECORD_V2@@@dbgobj@@QEAA_KPEBGAEBUUSN_RECORD_V2@@@Z; dbgobj::DbgPrint<ushort,USN_RECORD_V2>(ushort const *,USN_RECORD_V2 const &)
0x1400a1559  mov     r8, rsi; struct USN_RECORD_V2 *
0x1400a155c  mov     rdx, r13; struct ID_RECORD *
0x1400a155f  mov     rcx, rdi; this
0x1400a1562  test    byte ptr [rsi+34h], 10h
0x1400a1566  jz      short loc_1400A1598
0x1400a1568  call    ?SetPendingTombstoneFlag@UsnConsumer@@AEAAPEAVFrsStatus@@AEAVID_RECORD@@AEBUUSN_RECORD_V2@@@Z; UsnConsumer::SetPendingTombstoneFlag(ID_RECORD &,USN_RECORD_V2 const &)
0x1400a156d  mov     rbx, rax
0x1400a1570  test    rax, rax
0x1400a1573  jz      short loc_1400A1594
0x1400a1575  call    cs:__imp_GetCurrentThreadId
0x1400a157c  nop     dword ptr [rax+rax+00h]
0x1400a1581  mov     qword ptr [rsp+140h+var_100], rbx
0x1400a1586  mov     dword ptr [rsp+140h+var_108], eax
0x1400a158a  mov     dword ptr [rsp+140h+var_110], 0A87h
0x1400a1592  jmp     short loc_1400A15D2
0x1400a1594  xor     ebx, ebx
0x1400a1596  jmp     short loc_1400A15FC
0x1400a1598  and     dword ptr [rsp+140h+var_118], r15d
0x1400a159d  mov     dword ptr [rsp+140h+var_120], 1; int
0x1400a15a5  xor     r9d, r9d; int
0x1400a15a8  call    ?TombstoneOrDelete@UsnConsumer@@AEAAPEAVFrsStatus@@AEAVID_RECORD@@AEBUUSN_RECORD_V2@@HHH@Z; UsnConsumer::TombstoneOrDelete(ID_RECORD &,USN_RECORD_V2 const &,int,int,int)
0x1400a15ad  mov     rbx, rax
0x1400a15b0  test    rax, rax
0x1400a15b3  jz      short loc_1400A1607
0x1400a15b5  call    cs:__imp_GetCurrentThreadId
0x1400a15bc  nop     dword ptr [rax+rax+00h]
0x1400a15c1  mov     qword ptr [rsp+140h+var_100], rbx
0x1400a15c6  mov     dword ptr [rsp+140h+var_108], eax
0x1400a15ca  mov     dword ptr [rsp+140h+var_110], 0A89h
0x1400a15d2  lea     rax, aUsnconsumerDel; "UsnConsumer::DeleteCreateIdRecords"
0x1400a15d9  mov     [rsp+140h+var_118], rax
0x1400a15de  lea     rax, aBaseFsRemotefs_51; "base\\fs\\remotefs\\frs\\src\\db\\usnco"...
0x1400a15e5  mov     [rsp+140h+var_120], rax
0x1400a15ea  mov     r9d, [rbx]
0x1400a15ed  mov     r8d, [rbx+8]
0x1400a15f1  mov     edx, [rbx+4]
0x1400a15f4  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400a15f9  mov     rbx, rax
0x1400a15fc  test    rbx, rbx
0x1400a15ff  jnz     loc_1400A19AD
0x1400a1605  jmp     short loc_1400A1609
0x1400a1607  xor     ebx, ebx
0x1400a1609  movzx   r9d, word ptr [rsi+38h]
0x1400a160e  shr     r9d, 1; unsigned int
0x1400a1611  mov     eax, [rsi+34h]
0x1400a1614  shr     eax, 4
0x1400a1617  and     eax, 1
0x1400a161a  mov     dword ptr [rsp+140h+var_120], eax; int
0x1400a161e  lea     r8, [rsi+3Ch]; unsigned __int16 *
0x1400a1622  mov     r14, [rsp+140h+var_D0]
0x1400a1627  mov     rdx, r14; struct _GUID *
0x1400a162a  mov     rcx, [rdi+0D0h]; this
0x1400a1631  call    ?Match@FilterMan@@QEAAHAEBU_GUID@@PEBGKHH@Z; FilterMan::Match(_GUID const &,ushort const *,ulong,int,int)
0x1400a1636  test    eax, eax
0x1400a1638  jnz     loc_1400A16D6
0x1400a163e  lea     rax, [rbp+40h+var_88]
0x1400a1642  mov     [rsp+140h+var_110], rax; struct UID *
0x1400a1647  mov     rax, [rbp+40h+arg_30]
0x1400a164e  mov     [rsp+140h+var_118], rax; struct Usn *
0x1400a1653  mov     rax, [rsp+140h+var_E0]
0x1400a1658  mov     [rsp+140h+var_120], rax; struct _FILETIME *
0x1400a165d  mov     r9, r12; struct UID *
0x1400a1660  mov     r8, r14; struct Guid *
0x1400a1663  mov     rdx, rsi; struct USN_RECORD_V2 *
0x1400a1666  mov     rcx, rdi; this
0x1400a1669  call    ?CreateNewRecord@UsnConsumer@@AEAAPEAVFrsStatus@@AEBUUSN_RECORD_V2@@AEBVGuid@@AEBVUID@@AEBU_FILETIME@@AEBVUsn@@AEAV5@@Z; UsnConsumer::CreateNewRecord(USN_RECORD_V2 const &,Guid const &,UID const &,_FILETIME const &,Usn const &,UID &)
0x1400a166e  mov     rbx, rax
0x1400a1671  xor     r12d, r12d
0x1400a1674  test    rax, rax
0x1400a1677  jz      short loc_1400A16CB
0x1400a1679  call    cs:__imp_GetCurrentThreadId
0x1400a1680  nop     dword ptr [rax+rax+00h]
0x1400a1685  mov     qword ptr [rsp+140h+var_100], rbx
0x1400a168a  mov     dword ptr [rsp+140h+var_108], eax
0x1400a168e  mov     dword ptr [rsp+140h+var_110], 0A95h
0x1400a1696  lea     rax, aUsnconsumerDel; "UsnConsumer::DeleteCreateIdRecords"
0x1400a169d  mov     [rsp+140h+var_118], rax
0x1400a16a2  lea     rax, aBaseFsRemotefs_51; "base\\fs\\remotefs\\frs\\src\\db\\usnco"...
0x1400a16a9  mov     [rsp+140h+var_120], rax
0x1400a16ae  mov     r9d, [rbx]
0x1400a16b1  mov     r8d, [rbx+8]
0x1400a16b5  mov     edx, [rbx+4]
0x1400a16b8  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400a16bd  mov     rbx, rax
0x1400a16c0  test    rax, rax
0x1400a16c3  jnz     loc_1400A19AD
0x1400a16c9  jmp     short loc_1400A16CE
0x1400a16cb  mov     rbx, r12
0x1400a16ce  mov     r15d, 1
0x1400a16d4  jmp     short loc_1400A16D9
0x1400a16d6  xor     r12d, r12d
0x1400a16d9  test    byte ptr [rsi+34h], 10h
0x1400a16dd  jz      loc_1400A19AD
0x1400a16e3  movups  xmm0, xmmword ptr [r13+0]
0x1400a16e8  movdqu  [rbp+40h+var_B0], xmm0
0x1400a16ed  mov     rax, [r13+10h]
0x1400a16f1  mov     [rbp+40h+var_A0], rax
0x1400a16f5  lea     r14, [rsi+20h]
0x1400a16f9  mov     rax, [r14]
0x1400a16fc  mov     [rbp+40h+var_98], rax
0x1400a1700  mov     [rbp+40h+var_90], 2
0x1400a1708  mov     rcx, [rdi+68h]
0x1400a170c  mov     rax, [rcx]
0x1400a170f  xor     r8d, r8d
0x1400a1712  lea     rdx, [rbp+40h+var_B0]
0x1400a1716  mov     rax, [rax+0F0h]
0x1400a171d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a1722  mov     rbx, rax
0x1400a1725  test    rax, rax
0x1400a1728  jz      short loc_1400A177A
0x1400a172a  call    cs:__imp_GetCurrentThreadId
0x1400a1731  nop     dword ptr [rax+rax+00h]
0x1400a1736  mov     qword ptr [rsp+140h+var_100], rbx
0x1400a173b  mov     dword ptr [rsp+140h+var_108], eax
0x1400a173f  mov     dword ptr [rsp+140h+var_110], 0AA3h
0x1400a1747  lea     rax, aUsnconsumerDel; "UsnConsumer::DeleteCreateIdRecords"
0x1400a174e  mov     [rsp+140h+var_118], rax
0x1400a1753  lea     rax, aBaseFsRemotefs_51; "base\\fs\\remotefs\\frs\\src\\db\\usnco"...
0x1400a175a  mov     [rsp+140h+var_120], rax
0x1400a175f  mov     r9d, [rbx]
0x1400a1762  mov     r8d, [rbx+8]
0x1400a1766  mov     edx, [rbx+4]
0x1400a1769  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400a176e  mov     rbx, rax
0x1400a1771  test    rax, rax
0x1400a1774  jnz     loc_1400A19AD
0x1400a177a  test    r15d, r15d
0x1400a177d  jz      loc_1400A1815
0x1400a1783  movups  xmm0, [rbp+40h+var_88]
0x1400a1787  movdqu  [rbp+40h+var_B0], xmm0
0x1400a178c  mov     rax, [rbp+40h+var_78]
0x1400a1790  mov     [rbp+40h+var_A0], rax
0x1400a1794  mov     rax, [r14]
0x1400a1797  mov     [rbp+40h+var_98], rax
0x1400a179b  mov     [rbp+40h+var_90], 1
0x1400a17a3  mov     rcx, [rdi+68h]
0x1400a17a7  mov     rax, [rcx]
0x1400a17aa  xor     r8d, r8d
0x1400a17ad  lea     rdx, [rbp+40h+var_B0]
0x1400a17b1  mov     rax, [rax+0F0h]
0x1400a17b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a17bd  mov     rbx, rax
0x1400a17c0  test    rax, rax
0x1400a17c3  jz      short loc_1400A1815
0x1400a17c5  call    cs:__imp_GetCurrentThreadId
0x1400a17cc  nop     dword ptr [rax+rax+00h]
0x1400a17d1  mov     qword ptr [rsp+140h+var_100], rbx
0x1400a17d6  mov     dword ptr [rsp+140h+var_108], eax
0x1400a17da  mov     dword ptr [rsp+140h+var_110], 0AADh
0x1400a17e2  lea     rax, aUsnconsumerDel; "UsnConsumer::DeleteCreateIdRecords"
0x1400a17e9  mov     [rsp+140h+var_118], rax
0x1400a17ee  lea     rax, aBaseFsRemotefs_51; "base\\fs\\remotefs\\frs\\src\\db\\usnco"...
0x1400a17f5  mov     [rsp+140h+var_120], rax
0x1400a17fa  mov     r9d, [rbx]
0x1400a17fd  mov     r8d, [rbx+8]
0x1400a1801  mov     edx, [rbx+4]
0x1400a1804  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400a1809  mov     rbx, rax
0x1400a180c  test    rax, rax
0x1400a180f  jnz     loc_1400A19AD
0x1400a1815  mov     rcx, rdi; this
0x1400a1818  call    ?CheckPoint@UsnConsumer@@AEAAPEAVFrsStatus@@XZ; UsnConsumer::CheckPoint(void)
0x1400a181d  mov     rbx, rax
0x1400a1820  test    rax, rax
0x1400a1823  jz      short loc_1400A1877
0x1400a1825  call    cs:__imp_GetCurrentThreadId
0x1400a182c  nop     dword ptr [rax+rax+00h]
0x1400a1831  mov     qword ptr [rsp+140h+var_100], rbx
0x1400a1836  mov     dword ptr [rsp+140h+var_108], eax
0x1400a183a  mov     dword ptr [rsp+140h+var_110], 0AB5h
0x1400a1842  lea     rax, aUsnconsumerDel; "UsnConsumer::DeleteCreateIdRecords"
0x1400a1849  mov     [rsp+140h+var_118], rax
0x1400a184e  lea     rax, aBaseFsRemotefs_51; "base\\fs\\remotefs\\frs\\src\\db\\usnco"...
0x1400a1855  mov     [rsp+140h+var_120], rax
0x1400a185a  mov     r9d, [rbx]
0x1400a185d  mov     r8d, [rbx+8]
0x1400a1861  mov     edx, [rbx+4]
0x1400a1864  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400a1869  mov     rbx, rax
0x1400a186c  test    rax, rax
0x1400a186f  jnz     loc_1400A19AD
0x1400a1875  jmp     short loc_1400A187A
0x1400a1877  mov     rbx, r12
0x1400a187a  mov     rdx, [rdi+0E0h]
0x1400a1881  mov     rax, [rsi+8]
0x1400a1885  mov     [rsp+140h+var_E0], rax
0x1400a188a  lea     r9, [r13+48h]
0x1400a188e  lea     rax, [rsp+140h+var_D8]
0x1400a1893  mov     [rsp+140h+var_F0], rax
0x1400a1898  mov     dword ptr [rsp+140h+var_F8], r12d; void *
0x1400a189d  mov     qword ptr [rsp+140h+var_100], rdx
0x1400a18a2  mov     dword ptr [rsp+140h+var_108], r12d
0x1400a18a7  mov     dword ptr [rsp+140h+var_110], r12d
0x1400a18ac  mov     dword ptr [rsp+140h+var_118], r12d
0x1400a18b1  lea     rax, [rsp+140h+var_E0]
0x1400a18b6  mov     [rsp+140h+var_120], rax
0x1400a18bb  mov     r8, r13
0x1400a18be  mov     rdx, r14
0x1400a18c1  mov     rcx, [rdi+0D8h]
0x1400a18c8  call    ?QueueMoveoutJob@DirWalkerTask@@QEAAXAEBT_LARGE_INTEGER@@AEBVUID@@AEBU_GUID@@AEBVFileId@@HHW4MOVEOUT_TYPE@@PEAXHPEAH@Z; DirWalkerTask::QueueMoveoutJob(_LARGE_INTEGER const &,UID const &,_GUID const &,FileId const &,int,int,MOVEOUT_TYPE,void *,int,int *)
0x1400a18cd  test    r15d, r15d
0x1400a18d0  jz      short loc_1400A191F
0x1400a18d2  lea     rcx, [rbp+40h+var_70]
0x1400a18d6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1400a18db  mov     r8, [rsi+8]
0x1400a18df  mov     [rsp+140h+var_E0], r8
0x1400a18e4  mov     [rsp+140h+var_F0], r12; struct ContentSetManager *
0x1400a18e9  mov     [rsp+140h+var_100], r12d; int
0x1400a18ee  mov     [rsp+140h+var_108], r12; struct Usn *
0x1400a18f3  mov     [rsp+140h+var_110], r12; struct _FILETIME *
0x1400a18f8  lea     rcx, [rbp+40h+var_88]
0x1400a18fc  mov     [rsp+140h+var_118], rcx; struct UID *
0x1400a1901  mov     [rsp+140h+var_120], r14; union _LARGE_INTEGER *
0x1400a1906  mov     r9, rax; unsigned __int16 *
0x1400a1909  lea     r8, [rsp+140h+var_E0]; struct FileId *
0x1400a190e  mov     rdx, [rsp+140h+var_D0]; struct _GUID *
0x1400a1913  mov     rcx, [rdi+0D8h]; this
0x1400a191a  call    ?QueueMoveinJob@DirWalkerTask@@QEAAXAEBU_GUID@@AEBVFileId@@PEBGAEBT_LARGE_INTEGER@@AEBVUID@@PEBU_FILETIME@@PEBVUsn@@HPEAXPEAVContentSetManager@@@Z; DirWalkerTask::QueueMoveinJob(_GUID const &,FileId const &,ushort const *,_LARGE_INTEGER const &,UID const &,_FILETIME const *,Usn const *,int,void *,ContentSetManager *)
0x1400a191f  lea     rsi, [rdi+0E8h]
0x1400a1926  mov     rcx, rsi; lpCriticalSection
0x1400a1929  call    cs:__imp_LeaveCriticalSection
0x1400a1930  nop     dword ptr [rax+rax+00h]
0x1400a1935  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1400a1938  mov     rcx, [rdi+0E0h]; hHandle
0x1400a193f  call    cs:__imp_WaitForSingleObject
0x1400a1946  nop     dword ptr [rax+rax+00h]
0x1400a194b  cmp     [rsp+140h+var_D8], r12d
0x1400a1950  jnz     short loc_1400A199D
0x1400a1952  call    cs:__imp_GetCurrentThreadId
0x1400a1959  nop     dword ptr [rax+rax+00h]
0x1400a195e  mov     qword ptr [rsp+140h+var_100], r12
0x1400a1963  mov     dword ptr [rsp+140h+var_108], eax
0x1400a1967  mov     dword ptr [rsp+140h+var_110], 0AD7h
0x1400a196f  lea     rax, aUsnconsumerDel; "UsnConsumer::DeleteCreateIdRecords"
0x1400a1976  mov     [rsp+140h+var_118], rax
0x1400a197b  lea     rax, aBaseFsRemotefs_51; "base\\fs\\remotefs\\frs\\src\\db\\usnco"...
0x1400a1982  mov     [rsp+140h+var_120], rax
0x1400a1987  mov     r9d, 3
0x1400a198d  xor     r8d, r8d
0x1400a1990  mov     edx, 2336h
0x1400a1995  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400a199a  mov     rbx, rax
0x1400a199d  mov     rcx, rsi; lpCriticalSection
0x1400a19a0  call    cs:__imp_EnterCriticalSection
0x1400a19a7  nop     dword ptr [rax+rax+00h]
0x1400a19ac  nop
0x1400a19ad  lea     rcx, [rbp+40h+var_70]
0x1400a19b1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400a19b6  mov     rax, rbx
0x1400a19b9  mov     rcx, [rbp+40h+var_50]
  ... truncated ...
```
