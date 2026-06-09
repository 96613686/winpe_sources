# Config::AdWriter::CreateSysVolLocalObjectsOnAnyWritableDc(Config::SYSVOL_PARAMETERS const *,Config::AdConfig::SYSVOL_OBJECTS const *,Config::AdObject const *,Config::AdObject const *,ulong const &)

- ea: `0x140202a50`
- end: `0x140203311`
- name: `?CreateSysVolLocalObjectsOnAnyWritableDc@AdWriter@Config@@IEAAPEAVFrsStatus@@PEBUSYSVOL_PARAMETERS@2@PEBUSYSVOL_OBJECTS@AdConfig@2@PEBVAdObject@2@2AEBK@Z`
- size: `2241`
- prototype: `struct FrsStatus *__usercall@<rax>(Config::AdWriter *__hidden this@<rcx>, const struct Config::SYSVOL_PARAMETERS *@<rdx>, const struct Config::AdConfig::SYSVOL_OBJECTS *@<r8>, const struct Config::AdObject *@<r9>, const struct Config::AdObject *, const unsigned int *)`
- caller_count: `2`
- callee_count: `26`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1402037fc`
- `0x140204318`

## callees

- `0x1400036d0`
- `0x14000c910`
- `0x14000cb00`
- `0x14000cd1c`
- `0x14000e34c`
- `0x14000ee94`
- `0x14001c1ac`
- `0x14001e04c`
- `0x14001e0a0`
- `0x1401b9450`
- `0x1401b9494`
- `0x1401de2c4`
- `0x1401df160`
- `0x1401e3a08`
- `0x1401ea144`
- `0x1401eb4c8`
- `0x1401ef600`
- `0x1401f2138`
- `0x1401f3094`
- `0x1401f55d0`
- `0x1402013f8`
- `0x140202a50`
- `0x140204844`
- `0x140204a90`
- `0x140205c00`
- `0x140223010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140202b1d`
- `KERNEL32!GetCurrentThreadId` at `0x140202c36`
- `KERNEL32!GetCurrentThreadId` at `0x140202cc0`
- `KERNEL32!GetCurrentThreadId` at `0x140202d11`
- `KERNEL32!GetCurrentThreadId` at `0x140203240`
- `KERNEL32!GetCurrentThreadId` at `0x140203294`
- `KERNEL32!GetCurrentThreadId` at `0x140202b1d`
- `KERNEL32!GetCurrentThreadId` at `0x140202c36`
- `KERNEL32!GetCurrentThreadId` at `0x140202cc0`
- `KERNEL32!GetCurrentThreadId` at `0x140202d11`
- `KERNEL32!GetCurrentThreadId` at `0x140203240`
- `KERNEL32!GetCurrentThreadId` at `0x140203294`

## string_xrefs

- `0x140202b46`: `base\fs\remotefs\frs\src\ad\adwriter.cpp`
- `0x140202ce9`: `base\fs\remotefs\frs\src\ad\adwriter.cpp`
- `0x140203269`: `base\fs\remotefs\frs\src\ad\adwriter.cpp`
- `0x1402032c0`: `base\fs\remotefs\frs\src\ad\adwriter.cpp`
- `0x140202dc9`: `[SYSVOL] Local settings object already exists.`
- `0x140202ae5`: `[SYSVOL] Create sysvol local objects on writable DC`
- `0x140202b3a`: `Config::AdWriter::CreateSysVolLocalObjectsOnAnyWritableDc`
- `0x140202cdd`: `Config::AdWriter::CreateSysVolLocalObjectsOnAnyWritableDc`
- `0x14020325d`: `Config::AdWriter::CreateSysVolLocalObjectsOnAnyWritableDc`
- `0x1402032b9`: `Config::AdWriter::CreateSysVolLocalObjectsOnAnyWritableDc`
- `0x140202aad`: `Config::AdWriter::CreateSysVolLocalObjectsOnAnyWritableDc`
- `0x140202bf5`: `Config::AdWriter::CreateSysVolLocalObjectsOnAnyWritableDc`
- `0x140202c83`: `Config::AdWriter::CreateSysVolLocalObjectsOnAnyWritableDc`
- `0x140202d83`: `Config::AdWriter::CreateSysVolLocalObjectsOnAnyWritableDc`
- `0x140202f37`: `Config::AdWriter::CreateSysVolLocalObjectsOnAnyWritableDc`
- `0x140202fd8`: `Config::AdWriter::CreateSysVolLocalObjectsOnAnyWritableDc`
- `0x14020305b`: `Config::AdWriter::CreateSysVolLocalObjectsOnAnyWritableDc`
- `0x14020310d`: `Config::AdWriter::CreateSysVolLocalObjectsOnAnyWritableDc`
- `0x1402031e6`: `Config::AdWriter::CreateSysVolLocalObjectsOnAnyWritableDc`
- `0x140203000`: `[SYSVOL] Delete subscriber object failed because it does not exist.`
- `0x140202cb0`: `[SYSVOL] RODC's member object does not exist, cannot continue to create local object at this time. DFSR migration will retry in few minutes and will continue when its member object is created by PDC. memberDn:%?`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
struct FrsStatus *__fastcall Config::AdWriter::CreateSysVolLocalObjectsOnAnyWritableDc(
        Config::AdWriter *this,
        const struct Config::SYSVOL_PARAMETERS *a2,
        const struct Config::AdConfig::SYSVOL_OBJECTS *a3,
        const struct Config::AdObject *a4,
        const struct Config::AdObject *a5,
        const unsigned int *a6)
{
  __int64 v7; // rbx
  struct FrsStatus *v8; // rdi
  DWORD v9; // eax
  __int64 v10; // rcx
  struct FrsStatus *v11; // rdi
  struct FrsStatus *v12; // rsi
  struct FrsStatus *v13; // r13
  Config::AdWriter **v14; // r14
  struct FrsStatus *v15; // rdi
  __int64 v16; // rcx
  __int64 v17; // rax
  DWORD v18; // eax
  __int64 v19; // rcx
  unsigned int *v20; // rdi
  __int64 v21; // rcx
  const unsigned __int16 *v22; // r14
  struct FrsStatus *v23; // rax
  struct FrsStatus *SysVolLocalFlags; // rdi
  Config::AdWriter *v25; // rsi
  const unsigned __int16 *v26; // r12
  int v27; // r8d
  struct FrsStatus *v28; // r9
  Config::AdWriter *v29; // r15
  Config::AdWriter *v30; // rax
  const unsigned __int16 *v31; // r14
  struct FrsStatus *v32; // rax
  Config::AdWriter *v33; // rcx
  struct FrsStatus *v34; // r9
  Config::AdWriter *v35; // rax
  struct FrsStatus *v36; // r9
  Config::AdWriter *v37; // rax
  const unsigned __int16 *v38; // rdi
  struct FrsStatus *v39; // r9
  DWORD v40; // eax
  __int64 v41; // rcx
  __int64 v42; // rcx
  DWORD v44; // [rsp+40h] [rbp-C8h]
  DWORD v45; // [rsp+40h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C8h]
  struct FrsStatus *v47; // [rsp+58h] [rbp-B0h] BYREF
  Config::AdWriter *v48; // [rsp+60h] [rbp-A8h] BYREF
  const wchar_t *v49; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v50; // [rsp+70h] [rbp-98h]
  const wchar_t *v51; // [rsp+78h] [rbp-90h]
  int v52; // [rsp+80h] [rbp-88h]
  unsigned int v53; // [rsp+84h] [rbp-84h] BYREF
  int v54; // [rsp+88h] [rbp-80h] BYREF
  const wchar_t *v55; // [rsp+90h] [rbp-78h] BYREF
  int v56; // [rsp+98h] [rbp-70h]
  int v57; // [rsp+9Ch] [rbp-6Ch]
  const wchar_t *v58; // [rsp+A0h] [rbp-68h]
  unsigned __int16 *v59; // [rsp+A8h] [rbp-60h] BYREF
  _QWORD v60[2]; // [rsp+B0h] [rbp-58h] BYREF
  unsigned __int16 *v61; // [rsp+C0h] [rbp-48h] BYREF
  _QWORD v62[2]; // [rsp+C8h] [rbp-40h] BYREF
  const wchar_t *v63; // [rsp+D8h] [rbp-30h] BYREF
  int v64; // [rsp+E0h] [rbp-28h]
  int v65; // [rsp+E4h] [rbp-24h]
  const wchar_t *v66; // [rsp+E8h] [rbp-20h]
  __int128 v67; // [rsp+F0h] [rbp-18h] BYREF
  __int64 v68; // [rsp+100h] [rbp-8h]
  __int128 v69; // [rsp+108h] [rbp+0h]
  int v70; // [rsp+118h] [rbp+10h]
  _BYTE v71[432]; // [rsp+128h] [rbp+20h] BYREF

  v59 = &FrsStringImpl<unsigned short,char>::s_Empty;
  v7 = 0;
  if ( !byte_140315A80 )
    _InterlockedIncrement((volatile signed __int32 *)&FrsStringImpl<unsigned short,char>::s_Empty);
  v54 = 0;
  v52 = 0;
  v53 = 0;
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v55 = L"Config::AdWriter::CreateSysVolLocalObjectsOnAnyWritableDc";
    v56 = 766;
    v57 = 4;
    v58 = L"ADWR";
    dbgobj::DbgPrint<unsigned short>(&v55, L"[SYSVOL] Create sysvol local objects on writable DC");
  }
  v67 = 0;
  v68 = 0;
  v69 = 0;
  v70 = 0;
  v8 = Config::AdConnection::ConnectToAnyWritableDc((Config::AdConnection *)&v67);
  if ( !v8 )
  {
    Config::AdReader::AdReader((Config::AdReader *)v71, (struct Config::AdConnection *)&v67);
    v11 = Config::AdConfig::SetRootNamingContextsAndComputerNameWithDns((Config::AdConfig *)v71, this);
    v12 = v11;
    v13 = v11;
    if ( v11 || (v11 = (struct FrsStatus *)Config::AdConfig::ReadServiceName(v71, &v59), v12 = v11, (v13 = v11) != 0) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v17 = FrsStatusList::PushNewError(
              v42,
              *((unsigned int *)v13 + 1),
              *((unsigned int *)v12 + 2),
              *(unsigned int *)v11,
              "base\\fs\\remotefs\\frs\\src\\ad\\adwriter.cpp",
              "Config::AdWriter::CreateSysVolLocalObjectsOnAnyWritableDc",
              788,
              CurrentThreadId,
              v11);
    }
    else
    {
      v14 = (Config::AdWriter **)((char *)a3 + 136);
      v15 = Config::AdReader::IsMemberObjectPresent(
              (Config::AdReader *)v71,
              (const struct Config::AdConfig::SYSVOL_OBJECTS *)((char *)a3 + 136),
              &v54);
      if ( v15 )
      {
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
        {
          v55 = L"Config::AdWriter::CreateSysVolLocalObjectsOnAnyWritableDc";
          v56 = 802;
          v57 = 2;
          v58 = L"ADWR";
          v48 = *v14;
          dbgobj::DbgPrint<unsigned short,unsigned short const *>(
            &v55,
            L"[SYSVOL] Failed to check member object. memberDn:%?",
            &v48);
        }
        v44 = GetCurrentThreadId();
        v17 = FrsStatusList::PushNewError(
                v16,
                *((unsigned int *)v15 + 1),
                *((unsigned int *)v15 + 2),
                *(unsigned int *)v15,
                "base\\fs\\remotefs\\frs\\src\\ad\\adwriter.cpp",
                "Config::AdWriter::CreateSysVolLocalObjectsOnAnyWritableDc",
                805,
                v44,
                v15);
      }
      else
      {
        if ( v54 )
        {
          v60[1] = &v67;
          v60[0] = &Config::AdObjectEditor::`vftable';
          v62[1] = *((_QWORD *)this + 5);
          v62[0] = &Config::AdAttrEditor::`vftable';
          v22 = (const unsigned __int16 *)*((_QWORD *)a3 + 1);
          v23 = Config::AdObjectEditor::AddObject(
                  (Config::AdObjectEditor *)v60,
                  L"msDFSR-LocalSettings",
                  *(const unsigned __int16 **)a3,
                  v22);
          SysVolLocalFlags = v23;
          v47 = v23;
          if ( v23 )
          {
            if ( *((_DWORD *)v23 + 1) == 183 )
            {
              if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
              {
                v63 = L"Config::AdWriter::CreateSysVolLocalObjectsOnAnyWritableDc";
                v64 = 842;
                v65 = 4;
                v66 = L"ADWR";
                dbgobj::DbgPrint<unsigned short>(&v63, L"[SYSVOL] Local settings object already exists.");
              }
              CLEAR_ERROR(&v47);
              SysVolLocalFlags = v47;
            }
            if ( SysVolLocalFlags )
              goto LABEL_85;
          }
          v61 = &FrsStringImpl<unsigned short,char>::s_Empty;
          if ( !byte_140315A80 )
            _InterlockedIncrement((volatile signed __int32 *)&FrsStringImpl<unsigned short,char>::s_Empty);
          SysVolLocalFlags = (struct FrsStatus *)Config::AdReader::GetSysVolLocalFlags((struct Config::AdConfig *)v71);
          FrsStringImpl<char,unsigned short>::ReleaseBody(&v61);
          if ( SysVolLocalFlags )
            goto LABEL_85;
          v53 = v52 & 0xFFFFFF0F | (16 * *a6);
          if ( v53 != v52 )
          {
            v48 = (Config::AdWriter *)operator new(0xC0u);
            v25 = (Config::AdWriter *)Config::AdWriter::AdWriter(v48, (struct Config::AdConnection *)&v67);
            if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
            {
              v49 = L"Config::AdWriter::CreateSysVolLocalObjectsOnAnyWritableDc";
              v50 = 0x400000368LL;
              v51 = L"ADWR";
              dbgobj::DbgPrint<unsigned short,unsigned int>(&v49, L"[MIG] Settings sysvol local flags to 0x%x", &v53);
            }
            SysVolLocalFlags = Config::AdWriter::SetSysVolLocalFlags(v25, v53);
            if ( v25 )
              (**(void (__fastcall ***)(Config::AdWriter *, __int64))v25)(v25, 1);
            if ( SysVolLocalFlags )
              goto LABEL_85;
          }
          v26 = v59 + 9;
          v28 = Config::AdAttrEditor::ReplicateSingleObject((Config::AdAttrEditor *)v62, v59 + 9, v22);
          v47 = v28;
          v29 = (Config::AdWriter *)L"NULL";
          if ( v28 )
          {
            if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
            {
              v49 = L"Config::AdWriter::CreateSysVolLocalObjectsOnAnyWritableDc";
              v50 = 0x30000037DLL;
              v51 = L"ADWR";
              v30 = (Config::AdWriter *)L"NULL";
              if ( v22 )
                v30 = (Config::AdWriter *)v22;
              v48 = v30;
              dbgobj::DbgPrint<unsigned short,unsigned short const *,FrsStatus>(
                &v49,
                L"[SYSVOL] (Ignored) Failed to replicate local settings object. Object:%ws Error:%?",
                &v48,
                v28);
            }
            CLEAR_ERROR(&v47);
            SysVolLocalFlags = v47;
            if ( v47 )
              goto LABEL_85;
          }
          v31 = (const unsigned __int16 *)*((_QWORD *)a3 + 3);
          v32 = Config::AdObjectEditor::DeleteObject((Config::AdObjectEditor *)v60, v31, v27, (unsigned int)v28);
          SysVolLocalFlags = v32;
          v47 = v32;
          if ( v32 )
          {
            if ( (unsigned int)FrsStatus::IsAdErrorNotFound(v32) )
            {
              if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
              {
                v49 = L"Config::AdWriter::CreateSysVolLocalObjectsOnAnyWritableDc";
                v50 = 0x400000398LL;
                v51 = L"ADWR";
                dbgobj::DbgPrint<unsigned short>(
                  &v49,
                  L"[SYSVOL] Delete subscriber object failed because it does not exist.");
              }
              CLEAR_ERROR(&v47);
              SysVolLocalFlags = v47;
            }
            if ( SysVolLocalFlags )
              goto LABEL_85;
          }
          v34 = Config::AdAttrEditor::ReplicateSingleObject((Config::AdAttrEditor *)v62, v26, v31);
          v47 = v34;
          if ( v34 )
          {
            if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
            {
              v49 = L"Config::AdWriter::CreateSysVolLocalObjectsOnAnyWritableDc";
              v50 = 0x3000003A4LL;
              v51 = L"ADWR";
              v35 = (Config::AdWriter *)L"NULL";
              if ( v31 )
                v35 = (Config::AdWriter *)v31;
              v48 = v35;
              dbgobj::DbgPrint<unsigned short,unsigned short const *,FrsStatus>(
                &v49,
                L"[SYSVOL] (Ignored) Failed to replicate subscriber object. Object:%ws Error:%?",
                &v48,
                v34);
            }
            CLEAR_ERROR(&v47);
            SysVolLocalFlags = v47;
            if ( v47 )
              goto LABEL_85;
          }
          SysVolLocalFlags = Config::AdWriter::CreateSysVolSubscriber(v33, (struct Config::AdObjectEditor *)v60, a3, a4);
          if ( SysVolLocalFlags )
            goto LABEL_85;
          v36 = Config::AdAttrEditor::ReplicateSingleObject((Config::AdAttrEditor *)v62, v26, v31);
          v47 = v36;
          if ( v36 )
          {
            if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
            {
              v49 = L"Config::AdWriter::CreateSysVolLocalObjectsOnAnyWritableDc";
              v50 = 0x3000003BFLL;
              v51 = L"ADWR";
              v37 = (Config::AdWriter *)L"NULL";
              if ( v31 )
                v37 = (Config::AdWriter *)v31;
              v48 = v37;
              dbgobj::DbgPrint<unsigned short,unsigned short const *,FrsStatus>(
                &v49,
                L"[SYSVOL] (Ignored) Failed to replicate subscriber object. Object:%ws Error:%?",
                &v48,
                v36);
            }
            CLEAR_ERROR(&v47);
            SysVolLocalFlags = v47;
            if ( v47 )
              goto LABEL_85;
          }
          SysVolLocalFlags = Config::AdWriter::CreateSysVolSubscription(
                               this,
                               (struct Config::AdObjectEditor *)v60,
                               a2,
                               a3,
                               a4,
                               a5);
          if ( SysVolLocalFlags )
            goto LABEL_85;
          v38 = (const unsigned __int16 *)*((_QWORD *)a3 + 5);
          v39 = Config::AdAttrEditor::ReplicateSingleObject((Config::AdAttrEditor *)v62, v26, v38);
          v47 = v39;
          if ( v39 )
          {
            if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
            {
              v49 = L"Config::AdWriter::CreateSysVolLocalObjectsOnAnyWritableDc";
              v50 = 0x3000003E0LL;
              v51 = L"ADWR";
              if ( v38 )
                v29 = (Config::AdWriter *)v38;
              v48 = v29;
              dbgobj::DbgPrint<unsigned short,unsigned short const *,FrsStatus>(
                &v49,
                L"[SYSVOL] (Ignored) Failed to replicate subscription object. Object:%ws Error:%?",
                &v48,
                v39);
            }
            CLEAR_ERROR(&v47);
            SysVolLocalFlags = v47;
            if ( v47 )
            {
LABEL_85:
              v40 = GetCurrentThreadId();
              v7 = FrsStatusList::PushNewError(
                     v41,
                     *((unsigned int *)SysVolLocalFlags + 1),
                     *((unsigned int *)SysVolLocalFlags + 2),
                     *(unsigned int *)SysVolLocalFlags,
                     "base\\fs\\remotefs\\frs\\src\\ad\\adwriter.cpp",
                     "Config::AdWriter::CreateSysVolLocalObjectsOnAnyWritableDc",
                     1004,
                     v40,
                     SysVolLocalFlags);
            }
          }
          v60[0] = &Config::AdEditor::`vftable';
          goto LABEL_89;
        }
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
        {
          v55 = L"Config::AdWriter::CreateSysVolLocalObjectsOnAnyWritableDc";
          v56 = 813;
          v57 = 3;
          v58 = L"ADWR";
          v48 = *v14;
          dbgobj::DbgPrint<unsigned short,unsigned short const *>(
            &v55,
            L"[SYSVOL] RODC's member object does not exist, cannot continue to create local object at this time. DFSR migr"
             "ation will retry in few minutes and will continue when its member object is created by PDC. memberDn:%?",
            &v48);
        }
        v18 = GetCurrentThreadId();
        v20 = (unsigned int *)FrsStatusList::PushNewError(
                                v19,
                                9514,
                                0,
                                3,
                                "base\\fs\\remotefs\\frs\\src\\ad\\adwriter.cpp",
                                "Config::AdWriter::CreateSysVolLocalObjectsOnAnyWritableDc",
                                819,
                                v18,
                                0);
        if ( !v20 )
        {
LABEL_89:
          Config::AdReader::~AdReader((Config::AdReader *)v71);
          goto LABEL_90;
        }
        v45 = GetCurrentThreadId();
        v17 = FrsStatusList::PushNewError(
                v21,
                v20[1],
                v20[2],
                *v20,
                "base\\fs\\remotefs\\frs\\src\\ad\\adwriter.cpp",
                "Config::AdWriter::CreateSysVolLocalObjectsOnAnyWritableDc",
                821,
                v45,
                v20);
      }
    }
    v7 = v17;
    goto LABEL_89;
  }
  v9 = GetCurrentThreadId();
  v7 = FrsStatusList::PushNewError(
         v10,
         *((unsigned int *)v8 + 1),
         *((unsigned int *)v8 + 2),
         *(unsigned int *)v8,
         "base\\fs\\remotefs\\frs\\src\\ad\\adwriter.cpp",
         "Config::AdWriter::CreateSysVolLocalObjectsOnAnyWritableDc",
         776,
         v9,
         v8);
LABEL_90:
  Config::AdConnection::~AdConnection((Config::AdConnection *)&v67);
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v59);
  return (struct FrsStatus *)v7;
}

```

## disassembly

```asm
0x140202a50  mov     rax, rsp
0x140202a53  mov     [rax+20h], r9
0x140202a57  mov     [rax+18h], r8
0x140202a5b  mov     [rax+10h], rdx
0x140202a5f  mov     [rax+8], rcx
0x140202a63  push    rbp
0x140202a64  push    rbx
0x140202a65  push    rsi
0x140202a66  push    rdi
0x140202a67  push    r12
0x140202a69  push    r13
0x140202a6b  push    r14
0x140202a6d  push    r15
0x140202a6f  lea     rbp, [rax-1D8h]
0x140202a76  sub     rsp, 298h
0x140202a7d  mov     r15, rcx
0x140202a80  lea     rax, ?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x140202a87  mov     [rbp+1D0h+var_230], rax
0x140202a8b  xor     ebx, ebx
0x140202a8d  cmp     cs:byte_140315A80, bl
0x140202a93  jnz     short loc_140202A9C
0x140202a95  lock inc cs:?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x140202a9c  mov     [rbp+1D0h+var_250], ebx
0x140202a9f  mov     [rsp+2D0h+var_258], ebx
0x140202aa3  mov     [rsp+2D0h+var_254], ebx
0x140202aa7  mov     r12d, 4
0x140202aad  lea     rcx, aConfigAdwriter_19; "Config::AdWriter::CreateSysVolLocalObje"...
0x140202ab4  lea     rdx, aAdwr; "ADWR"
0x140202abb  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140202ac2  test    rax, rax
0x140202ac5  jz      short loc_140202AF5
0x140202ac7  cmp     [rax+40h], ebx
0x140202aca  jz      short loc_140202AF5
0x140202acc  cmp     [rax+38h], r12d
0x140202ad0  jl      short loc_140202AF5
0x140202ad2  mov     [rbp+1D0h+var_248], rcx
0x140202ad6  mov     [rbp+1D0h+var_240], 2FEh
0x140202add  mov     [rbp+1D0h+var_23C], r12d
0x140202ae1  mov     [rbp+1D0h+var_238], rdx
0x140202ae5  lea     rdx, aSysvolCreateSy_0; "[SYSVOL] Create sysvol local objects on"...
0x140202aec  lea     rcx, [rbp+1D0h+var_248]
0x140202af0  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x140202af5  xorps   xmm0, xmm0
0x140202af8  movdqu  [rbp+1D0h+var_1E8], xmm0
0x140202afd  mov     [rbp+1D0h+var_1D8], rbx
0x140202b01  xorps   xmm1, xmm1
0x140202b04  movdqu  [rbp+1D0h+var_1D0], xmm1
0x140202b09  mov     [rbp+1D0h+var_1C0], ebx
0x140202b0c  lea     rcx, [rbp+1D0h+var_1E8]; this
0x140202b10  call    ?ConnectToAnyWritableDc@AdConnection@Config@@QEAAPEAVFrsStatus@@XZ; Config::AdConnection::ConnectToAnyWritableDc(void)
0x140202b15  mov     rdi, rax
0x140202b18  test    rax, rax
0x140202b1b  jz      short loc_140202B69
0x140202b1d  call    cs:__imp_GetCurrentThreadId
0x140202b24  nop     dword ptr [rax+rax+00h]
0x140202b29  mov     qword ptr [rsp+2D0h+var_298+8], rdi
0x140202b2e  mov     [rsp+2D0h+var_298], eax
0x140202b32  mov     [rsp+2D0h+var_2A0], 308h
0x140202b3a  lea     r14, aConfigAdwriter_27; "Config::AdWriter::CreateSysVolLocalObje"...
0x140202b41  mov     [rsp+2D0h+var_2A8], r14
0x140202b46  lea     r15, aBaseFsRemotefs_38; "base\\fs\\remotefs\\frs\\src\\ad\\adwri"...
0x140202b4d  mov     [rsp+2D0h+var_2B0], r15
0x140202b52  mov     r9d, [rdi]
0x140202b55  mov     r8d, [rdi+8]
0x140202b59  mov     edx, [rdi+4]
0x140202b5c  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140202b61  mov     rbx, rax
0x140202b64  jmp     loc_1402032E6
0x140202b69  lea     rdx, [rbp+1D0h+var_1E8]; struct Config::AdConnection *
0x140202b6d  lea     rcx, [rbp+1D0h+var_1B0]; this
0x140202b71  call    ??0AdReader@Config@@QEAA@PEAVAdConnection@1@@Z; Config::AdReader::AdReader(Config::AdConnection *)
0x140202b76  nop
0x140202b77  mov     rdx, r15; struct Config::AdConfig *
0x140202b7a  lea     rcx, [rbp+1D0h+var_1B0]; this
0x140202b7e  call    ?SetRootNamingContextsAndComputerNameWithDns@AdConfig@Config@@QEAAPEAVFrsStatus@@PEAV12@@Z; Config::AdConfig::SetRootNamingContextsAndComputerNameWithDns(Config::AdConfig *)
0x140202b83  mov     rdi, rax
0x140202b86  mov     rsi, rax
0x140202b89  mov     r13, rax
0x140202b8c  test    rax, rax
0x140202b8f  jnz     loc_140203294
0x140202b95  lea     rdx, [rbp+1D0h+var_230]
0x140202b99  lea     rcx, [rbp+1D0h+var_1B0]
0x140202b9d  call    ?ReadServiceName@AdConfig@Config@@QEAAPEAVFrsStatus@@AEAV?$FrsStringImpl@GD@@@Z; Config::AdConfig::ReadServiceName(FrsStringImpl<ushort,char> &)
0x140202ba2  mov     rdi, rax
0x140202ba5  mov     rsi, rax
0x140202ba8  mov     r13, rax
0x140202bab  test    rax, rax
0x140202bae  jnz     loc_140203294
0x140202bb4  mov     r13, [rbp+1D0h+arg_10]
0x140202bbb  lea     r14, [r13+88h]
0x140202bc2  lea     r8, [rbp+1D0h+var_250]; int *
0x140202bc6  mov     rdx, r14; struct Config::AdDn *
0x140202bc9  lea     rcx, [rbp+1D0h+var_1B0]; this
0x140202bcd  call    ?IsMemberObjectPresent@AdReader@Config@@QEAAPEAVFrsStatus@@AEBVAdDn@2@AEAH@Z; Config::AdReader::IsMemberObjectPresent(Config::AdDn const &,int &)
0x140202bd2  mov     rdi, rax
0x140202bd5  test    rax, rax
0x140202bd8  jz      loc_140202C5F
0x140202bde  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140202be5  test    rcx, rcx
0x140202be8  jz      short loc_140202C36
0x140202bea  cmp     [rcx+40h], ebx
0x140202bed  jz      short loc_140202C36
0x140202bef  cmp     dword ptr [rcx+38h], 2
0x140202bf3  jl      short loc_140202C36
0x140202bf5  lea     r15, aConfigAdwriter_19; "Config::AdWriter::CreateSysVolLocalObje"...
0x140202bfc  mov     [rbp+1D0h+var_248], r15
0x140202c00  mov     [rbp+1D0h+var_240], 322h
0x140202c07  mov     [rbp+1D0h+var_23C], 2
0x140202c0e  lea     rax, aAdwr; "ADWR"
0x140202c15  mov     [rbp+1D0h+var_238], rax
0x140202c19  mov     rax, [r14]
0x140202c1c  mov     [rsp+2D0h+var_278], rax
0x140202c21  lea     r8, [rsp+2D0h+var_278]
0x140202c26  lea     rdx, aSysvolFailedTo_1; "[SYSVOL] Failed to check member object."...
0x140202c2d  lea     rcx, [rbp+1D0h+var_248]
0x140202c31  call    ??$DbgPrint@GPEBG@dbgobj@@QEAA_KPEBGAEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort const *>(ushort const *,ushort const * const &)
0x140202c36  call    cs:__imp_GetCurrentThreadId
0x140202c3d  nop     dword ptr [rax+rax+00h]
0x140202c42  mov     qword ptr [rsp+2D0h+var_298+8], rdi
0x140202c47  mov     [rsp+2D0h+var_298], eax
0x140202c4b  mov     [rsp+2D0h+var_2A0], 325h
0x140202c53  mov     r8d, [rdi+8]
0x140202c57  mov     edx, [rdi+4]
0x140202c5a  jmp     loc_1402032B9
0x140202c5f  cmp     [rbp+1D0h+var_250], ebx
0x140202c62  jnz     loc_140202D3A
0x140202c68  mov     esi, 3
0x140202c6d  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140202c74  test    rax, rax
0x140202c77  jz      short loc_140202CC0
0x140202c79  cmp     [rax+40h], ebx
0x140202c7c  jz      short loc_140202CC0
0x140202c7e  cmp     [rax+38h], esi
0x140202c81  jl      short loc_140202CC0
0x140202c83  lea     r15, aConfigAdwriter_19; "Config::AdWriter::CreateSysVolLocalObje"...
0x140202c8a  mov     [rbp+1D0h+var_248], r15
0x140202c8e  mov     [rbp+1D0h+var_240], 32Dh
0x140202c95  mov     [rbp+1D0h+var_23C], esi
0x140202c98  lea     rax, aAdwr; "ADWR"
0x140202c9f  mov     [rbp+1D0h+var_238], rax
0x140202ca3  mov     rax, [r14]
0x140202ca6  mov     [rsp+2D0h+var_278], rax
0x140202cab  lea     r8, [rsp+2D0h+var_278]
0x140202cb0  lea     rdx, aSysvolRodcSMem; "[SYSVOL] RODC's member object does not "...
0x140202cb7  lea     rcx, [rbp+1D0h+var_248]
0x140202cbb  call    ??$DbgPrint@GPEBG@dbgobj@@QEAA_KPEBGAEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort const *>(ushort const *,ushort const * const &)
0x140202cc0  call    cs:__imp_GetCurrentThreadId
0x140202cc7  nop     dword ptr [rax+rax+00h]
0x140202ccc  mov     qword ptr [rsp+2D0h+var_298+8], rbx
0x140202cd1  mov     [rsp+2D0h+var_298], eax
0x140202cd5  mov     [rsp+2D0h+var_2A0], 333h
0x140202cdd  lea     r14, aConfigAdwriter_27; "Config::AdWriter::CreateSysVolLocalObje"...
0x140202ce4  mov     [rsp+2D0h+var_2A8], r14
0x140202ce9  lea     r15, aBaseFsRemotefs_38; "base\\fs\\remotefs\\frs\\src\\ad\\adwri"...
0x140202cf0  mov     [rsp+2D0h+var_2B0], r15
0x140202cf5  mov     r9d, esi
0x140202cf8  xor     r8d, r8d
0x140202cfb  mov     edx, 252Ah
0x140202d00  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140202d05  mov     rdi, rax
0x140202d08  test    rax, rax
0x140202d0b  jz      loc_1402032DC
0x140202d11  call    cs:__imp_GetCurrentThreadId
0x140202d18  nop     dword ptr [rax+rax+00h]
0x140202d1d  mov     qword ptr [rsp+2D0h+var_298+8], rdi
0x140202d22  mov     [rsp+2D0h+var_298], eax
0x140202d26  mov     [rsp+2D0h+var_2A0], 335h
0x140202d2e  mov     r8d, [rdi+8]
0x140202d32  mov     edx, [rdi+4]
0x140202d35  jmp     loc_1402032C7
0x140202d3a  lea     rax, [rbp+1D0h+var_1E8]
0x140202d3e  mov     [rbp+1D0h+var_220], rax
0x140202d42  lea     rax, ??_7AdObjectEditor@Config@@6B@; const Config::AdObjectEditor::`vftable'
0x140202d49  mov     [rbp+1D0h+var_228], rax
0x140202d4d  mov     rax, [r15+28h]
0x140202d51  mov     [rbp+1D0h+var_208], rax
0x140202d55  lea     rax, ??_7AdAttrEditor@Config@@6B@; const Config::AdAttrEditor::`vftable'
0x140202d5c  mov     [rbp+1D0h+var_210], rax
0x140202d60  mov     r14, [r13+8]
0x140202d64  mov     r9, r14; unsigned __int16 *
0x140202d67  mov     r8, [r13+0]; unsigned __int16 *
0x140202d6b  lea     rdx, aMsdfsrLocalset; "msDFSR-LocalSettings"
0x140202d72  lea     rcx, [rbp+1D0h+var_228]; this
0x140202d76  call    ?AddObject@AdObjectEditor@Config@@QEAAPEAVFrsStatus@@PEBG00@Z; Config::AdObjectEditor::AddObject(ushort const *,ushort const *,ushort const *)
0x140202d7b  mov     rdi, rax
0x140202d7e  mov     [rsp+2D0h+var_280], rax
0x140202d83  lea     r15, aConfigAdwriter_19; "Config::AdWriter::CreateSysVolLocalObje"...
0x140202d8a  test    rax, rax
0x140202d8d  jz      short loc_140202DF1
0x140202d8f  cmp     dword ptr [rax+4], 0B7h
0x140202d96  jnz     short loc_140202DE8
0x140202d98  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140202d9f  test    rax, rax
0x140202da2  jz      short loc_140202DD9
0x140202da4  cmp     [rax+40h], ebx
0x140202da7  jz      short loc_140202DD9
0x140202da9  cmp     [rax+38h], r12d
0x140202dad  jl      short loc_140202DD9
0x140202daf  mov     [rbp+1D0h+var_200], r15
0x140202db3  mov     [rbp+1D0h+var_1F8], 34Ah
0x140202dba  mov     [rbp+1D0h+var_1F4], r12d
0x140202dbe  lea     rax, aAdwr; "ADWR"
0x140202dc5  mov     [rbp+1D0h+var_1F0], rax
0x140202dc9  lea     rdx, aSysvolLocalSet; "[SYSVOL] Local settings object already "...
0x140202dd0  lea     rcx, [rbp+1D0h+var_200]
0x140202dd4  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x140202dd9  lea     rcx, [rsp+2D0h+var_280]; struct FrsStatus **
0x140202dde  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x140202de3  mov     rdi, [rsp+2D0h+var_280]
0x140202de8  test    rdi, rdi
0x140202deb  jnz     loc_140203240
0x140202df1  lea     rax, ?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x140202df8  mov     [rbp+1D0h+var_218], rax
0x140202dfc  cmp     cs:byte_140315A80, bl
0x140202e02  jnz     short loc_140202E0B
0x140202e04  lock inc cs:?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x140202e0b  lea     r8, [rsp+2D0h+var_258]
0x140202e10  lea     rdx, [rbp+1D0h+var_218]
0x140202e14  lea     rcx, [rbp+1D0h+var_1B0]; struct Config::AdConfig *
0x140202e18  call    ?GetSysVolLocalFlags@AdReader@Config@@QEAAPEAVFrsStatus@@AEAV?$FrsStringImpl@GD@@AEAK@Z; Config::AdReader::GetSysVolLocalFlags(FrsStringImpl<ushort,char> &,ulong &)
0x140202e1d  mov     rdi, rax
0x140202e20  lea     rcx, [rbp+1D0h+var_218]
0x140202e24  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x140202e29  test    rdi, rdi
0x140202e2c  jnz     loc_140203240
0x140202e32  mov     edx, [rsp+2D0h+var_258]
0x140202e36  and     edx, 0FFFFFF0Fh
0x140202e3c  mov     rax, [rbp+1D0h+arg_28]
0x140202e43  mov     ecx, [rax]
0x140202e45  shl     ecx, 4
0x140202e48  or      ecx, edx
0x140202e4a  mov     [rsp+2D0h+var_254], ecx
0x140202e4e  cmp     ecx, [rsp+2D0h+var_258]
0x140202e52  jz      loc_140202EF1
0x140202e58  mov     ecx, 0C0h; Size
0x140202e5d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140202e62  mov     [rsp+2D0h+var_278], rax
0x140202e67  lea     rdx, [rbp+1D0h+var_1E8]; struct Config::AdConnection *
0x140202e6b  mov     rcx, rax; this
0x140202e6e  call    ??0AdWriter@Config@@QEAA@PEAVAdConnection@1@@Z; Config::AdWriter::AdWriter(Config::AdConnection *)
0x140202e73  mov     rsi, rax
0x140202e76  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140202e7d  test    rcx, rcx
0x140202e80  jz      short loc_140202EC1
0x140202e82  cmp     [rcx+40h], ebx
0x140202e85  jz      short loc_140202EC1
0x140202e87  cmp     [rcx+38h], r12d
0x140202e8b  jl      short loc_140202EC1
0x140202e8d  mov     qword ptr [rsp+2D0h+var_270], r15
0x140202e92  mov     dword ptr [rsp+2D0h+var_268], 368h
0x140202e9a  mov     dword ptr [rsp+2D0h+var_268+4], r12d
0x140202e9f  lea     rax, aAdwr; "ADWR"
0x140202ea6  mov     qword ptr [rsp+2D0h+var_260], rax
0x140202eab  lea     r8, [rsp+2D0h+var_254]
0x140202eb0  lea     rdx, aMigSettingsSys; "[MIG] Settings sysvol local flags to 0x"...
0x140202eb7  lea     rcx, [rsp+2D0h+var_270]
0x140202ebc  call    ??$DbgPrint@GI@dbgobj@@QEAA_KPEBGAEBI@Z; dbgobj::DbgPrint<ushort,uint>(ushort const *,uint const &)
0x140202ec1  mov     edx, [rsp+2D0h+var_254]; unsigned int
0x140202ec5  mov     rcx, rsi; this
0x140202ec8  call    ?SetSysVolLocalFlags@AdWriter@Config@@QEAAPEAVFrsStatus@@K@Z; Config::AdWriter::SetSysVolLocalFlags(ulong)
0x140202ecd  mov     rdi, rax
0x140202ed0  test    rsi, rsi
0x140202ed3  jz      short loc_140202EE8
0x140202ed5  mov     rax, [rsi]
0x140202ed8  mov     edx, 1
0x140202edd  mov     rcx, rsi
0x140202ee0  mov     rax, [rax]
0x140202ee3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140202ee8  test    rdi, rdi
0x140202eeb  jnz     loc_140203240
0x140202ef1  mov     r12, [rbp+1D0h+var_230]
0x140202ef5  add     r12, 12h
0x140202ef9  mov     r8, r14; unsigned __int16 *
0x140202efc  mov     rdx, r12; unsigned __int16 *
0x140202eff  lea     rcx, [rbp+1D0h+var_210]; this
0x140202f03  call    ?ReplicateSingleObject@AdAttrEditor@Config@@QEAAPEAVFrsStatus@@PEBG0@Z; Config::AdAttrEditor::ReplicateSingleObject(ushort const *,ushort const *)
0x140202f08  mov     r9, rax
0x140202f0b  mov     [rsp+2D0h+var_280], rax
0x140202f10  mov     esi, 3
0x140202f15  lea     r15, aNull_2; "NULL"
0x140202f1c  test    rax, rax
0x140202f1f  jz      short loc_140202F98
0x140202f21  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140202f28  test    rax, rax
0x140202f2b  jz      short loc_140202F80
0x140202f2d  cmp     [rax+40h], ebx
0x140202f30  jz      short loc_140202F80
0x140202f32  cmp     [rax+38h], esi
0x140202f35  jl      short loc_140202F80
0x140202f37  lea     rax, aConfigAdwriter_19; "Config::AdWriter::CreateSysVolLocalObje"...
0x140202f3e  mov     qword ptr [rsp+2D0h+var_270], rax
0x140202f43  mov     dword ptr [rsp+2D0h+var_268], 37Dh
0x140202f4b  mov     dword ptr [rsp+2D0h+var_268+4], esi
0x140202f4f  lea     rax, aAdwr; "ADWR"
0x140202f56  mov     qword ptr [rsp+2D0h+var_260], rax
0x140202f5b  mov     rax, r15
0x140202f5e  test    r14, r14
0x140202f61  cmovnz  rax, r14
0x140202f65  mov     [rsp+2D0h+var_278], rax
0x140202f6a  lea     r8, [rsp+2D0h+var_278]
  ... truncated ...
```
