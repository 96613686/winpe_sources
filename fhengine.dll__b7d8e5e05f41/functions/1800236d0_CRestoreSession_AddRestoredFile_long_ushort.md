# CRestoreSession::AddRestoredFile(long,ushort *)

- ea: `0x1800236d0`
- end: `0x180023e68`
- name: `?AddRestoredFile@CRestoreSession@@UEAAJJPEAG@Z`
- size: `1944`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, unsigned int, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `23`
- tags: `file_ops, loader_planting`

## callees

- `0x180002c24`
- `0x1800062d0`
- `0x1800077f0`
- `0x180007818`
- `0x180007a9c`
- `0x1800091a4`
- `0x18000935c`
- `0x180009404`
- `0x1800094d0`
- `0x180009920`
- `0x18000a1ec`
- `0x18000a2f8`
- `0x180010d48`
- `0x1800124a0`
- `0x18001284c`
- `0x1800236d0`
- `0x180024858`
- `0x180024a1c`
- `0x180024d00`
- `0x18002acd4`
- `0x180030aac`
- `0x180031680`
- `0x180034010`

## import_xrefs

- `ADVAPI32!SystemFunction036` at `0x180023939`
- `ADVAPI32!SystemFunction036` at `0x180023939`
- `KERNEL32!EnterCriticalSection` at `0x180023722`
- `KERNEL32!EnterCriticalSection` at `0x180023722`
- `KERNEL32!LeaveCriticalSection` at `0x180023e38`
- `KERNEL32!LeaveCriticalSection` at `0x180023e38`
- `KERNEL32!GetLastError` at `0x180023b1a`
- `KERNEL32!GetLastError` at `0x180023b6f`
- `KERNEL32!GetLastError` at `0x180023bfc`
- `KERNEL32!GetLastError` at `0x180023b1a`
- `KERNEL32!GetLastError` at `0x180023b6f`
- `KERNEL32!GetLastError` at `0x180023bfc`
- `KERNEL32!CloseHandle` at `0x180023c6b`
- `KERNEL32!CloseHandle` at `0x180023dc7`
- `KERNEL32!CloseHandle` at `0x180023c6b`
- `KERNEL32!CloseHandle` at `0x180023dc7`
- `KERNEL32!CreateFileW` at `0x180023b0b`
- `KERNEL32!CreateFileW` at `0x180023b0b`
- `KERNEL32!DeviceIoControl` at `0x180023bf2`
- `KERNEL32!DeviceIoControl` at `0x180023bf2`
- `KERNEL32!GetFileInformationByHandle` at `0x180023b65`
- `KERNEL32!GetFileInformationByHandle` at `0x180023b65`
- `ntdll!RtlNtStatusToDosError` at `0x180023d4e`
- `ntdll!RtlNtStatusToDosError` at `0x180023d4e`
- `ntdll!NtWriteFile` at `0x180023d3c`
- `ntdll!NtWriteFile` at `0x180023d3c`

## pseudocode

```c
__int64 __fastcall CRestoreSession::AddRestoredFile(
        struct _RTL_CRITICAL_SECTION *this,
        unsigned int a2,
        unsigned __int16 *a3)
{
  unsigned int v4; // r13d
  struct _RTL_CRITICAL_SECTION *v5; // r14
  __int64 v6; // rdx
  _QWORD *v7; // rcx
  const WCHAR *v8; // rbx
  int *v9; // rdi
  __int64 v10; // rbx
  int FileRecord; // eax
  unsigned int v12; // esi
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  __int64 v16; // rdi
  struct _RTL_CRITICAL_SECTION_DEBUG *v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rdx
  LONG v21; // r8d
  __int64 v22; // rax
  __int64 v23; // rax
  const unsigned __int16 *v24; // rdx
  _QWORD *v25; // rcx
  __int64 v26; // rdx
  HANDLE FileW; // rax
  void *v28; // rdi
  signed int LastError; // eax
  signed int v30; // eax
  _QWORD *v31; // rcx
  __int64 v32; // rdx
  signed int v33; // eax
  NTSTATUS v34; // eax
  unsigned int v35; // edi
  signed int v36; // eax
  __int64 v37; // rdx
  __int64 v38; // r8
  HANDLE hTemplateFile; // [rsp+30h] [rbp-348h]
  struct _RTL_CRITICAL_SECTION *v41; // [rsp+50h] [rbp-328h] BYREF
  LPCWSTR lpFileName; // [rsp+58h] [rbp-320h] BYREF
  int InBuffer; // [rsp+60h] [rbp-318h] BYREF
  DWORD BytesReturned; // [rsp+64h] [rbp-314h] BYREF
  __int64 v45; // [rsp+68h] [rbp-310h] BYREF
  unsigned int v46; // [rsp+70h] [rbp-308h]
  unsigned __int64 RandomBuffer; // [rsp+78h] [rbp-300h] BYREF
  PVOID Buffer; // [rsp+80h] [rbp-2F8h] BYREF
  __int64 v49; // [rsp+88h] [rbp-2F0h] BYREF
  int v50; // [rsp+90h] [rbp-2E8h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+98h] [rbp-2E0h]
  struct _RTL_CRITICAL_SECTION *v52; // [rsp+A0h] [rbp-2D8h]
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A8h] [rbp-2D0h] BYREF
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+B8h] [rbp-2C0h] BYREF
  unsigned int OutBuffer; // [rsp+F0h] [rbp-288h] BYREF
  __int16 v56; // [rsp+F4h] [rbp-284h]
  __int64 v57; // [rsp+108h] [rbp-270h]

  v4 = a2;
  v5 = this;
  v41 = this;
  v46 = a2;
  lpCriticalSection = this + 5;
  v52 = this + 5;
  EnterCriticalSection(this + 5);
  memset(&FileInformation, 0, sizeof(FileInformation));
  IoStatusBlock = 0;
  SmartPtr<CNamespaceRecord>::SmartPtr<CNamespaceRecord>(&v49);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&lpFileName);
  InBuffer = 0;
  BytesReturned = 0;
  RandomBuffer = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&Buffer);
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v6 = *(_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                      (__int64)&v45,
                      a3);
    v7 = (_QWORD *)(v6 - 24);
    v8 = lpFileName;
    v9 = (int *)(lpFileName - 12);
    if ( (LPCWSTR)(v6 - 24) != lpFileName - 12 )
    {
      if ( v9[4] >= 0 && *v7 == *(_QWORD *)v9 )
      {
        v10 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v7);
        ATL::CStringData::Release((ATL::CStringData *)v9);
        v8 = (const WCHAR *)(v10 + 24);
        lpFileName = v8;
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(&lpFileName, v6, *(unsigned int *)(v6 - 16));
        v8 = lpFileName;
      }
    }
    ATL::CStringData::Release((ATL::CStringData *)(v45 - 24));
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', (ATL::CAtlException *)&v50) )
    {
      LODWORD(v45) = v50;
      if ( v50 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            24,
            &WPP_bfc8787af4c333f8e14229724fcb8e50_Traceguids,
            (unsigned int)v50);
        v8 = lpFileName;
        v12 = v45;
        __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_180023805);
        goto LABEL_84;
      }
      v8 = lpFileName;
      v5 = v41;
      v4 = v46;
      __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_180023813);
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_dS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      25,
      (int)&WPP_bfc8787af4c333f8e14229724fcb8e50_Traceguids,
      v4,
      (__int64)v8);
  FileRecord = CSessionBaseRO::GetFileRecord(&v5[1].LockSemaphore, v4, &v49);
  v12 = FileRecord;
  if ( FileRecord < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_84;
    v14 = 26;
    v15 = (unsigned int)FileRecord;
LABEL_15:
    WPP_SF_d(v13[2], v14, &WPP_bfc8787af4c333f8e14229724fcb8e50_Traceguids, v15);
    goto LABEL_84;
  }
  v16 = v49;
  if ( !v49 || !*(_QWORD *)v49 )
  {
    v12 = -2147023728;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        27,
        &WPP_bfc8787af4c333f8e14229724fcb8e50_Traceguids,
        v4,
        -2147023728);
    goto LABEL_84;
  }
  if ( *(_WORD *)(*(_QWORD *)v49 + 40LL) == 4 )
  {
    ++v5[9].LockCount;
  }
  else if ( *(_WORD *)(*(_QWORD *)v49 + 40LL) == 3 )
  {
    ++v5[9].RecursionCount;
  }
  v5[9].OwningThread = (char *)v5[9].OwningThread + *(_QWORD *)(*(_QWORD *)v16 + 48LL);
  v17 = *(struct _RTL_CRITICAL_SECTION_DEBUG **)(*(_QWORD *)v16 + 48LL);
  if ( (__int64)v17 > (__int64)v5[8].DebugInfo )
  {
    v5[8].DebugInfo = v17;
    v18 = (__int64)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                     &v41,
                     &lpFileName);
    FheFileOperations::ExtractTruncatedFileExt(v18, &v5[8].SpinCount);
  }
  SystemFunction036(&RandomBuffer, 8u);
  if ( !(RandomBuffer % (v5[9].LockCount + v5[9].RecursionCount)) )
  {
    v5[7].SpinCount = *(_QWORD *)(*(_QWORD *)v16 + 48LL);
    v19 = (__int64)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                     &v41,
                     &lpFileName);
    FheFileOperations::ExtractTruncatedFileExt(v19, &v5[8].LockSemaphore);
  }
  v20 = *(unsigned int *)(*(_QWORD *)v16 + 64LL);
  if ( (_DWORD)v20 == v5[8].LockCount )
  {
    ++v5[8].RecursionCount;
  }
  else if ( (int)v20 < v5[8].LockCount )
  {
    (*(void (__fastcall **)(ULONG_PTR, __int64, HANDLE *))(*(_QWORD *)v5[1].SpinCount + 88LL))(
      v5[1].SpinCount,
      v20,
      &v5[8].OwningThread);
    v5[8].RecursionCount = 1;
  }
  v21 = *(_DWORD *)(*(_QWORD *)v16 + 64LL);
  if ( v21 < v5[8].LockCount || v21 == v5[8].LockCount && !(RandomBuffer % v5[8].RecursionCount) )
  {
    v5[8].LockCount = v21;
    v22 = (__int64)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                     &v41,
                     &lpFileName);
    FheFileOperations::ExtractTruncatedFileExt(v22, &v5[9]);
  }
  if ( v5[6].DebugInfo == (PRTL_CRITICAL_SECTION_DEBUG)-1LL )
  {
    v12 = CRestoreSession::OpenRestoreLog((CRestoreSession *)v5);
    if ( (v12 & 0x80000000) != 0 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_84;
      v14 = 28;
      goto LABEL_39;
    }
  }
  v23 = (__int64)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                   &v41,
                   &lpFileName);
  if ( !(unsigned int)CRestoreSession::PathIsWithinProtectionScope((__int64)v5, (const wchar_t **)v23) )
  {
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      goto LABEL_84;
    v26 = 29;
    goto LABEL_44;
  }
  if ( !(unsigned int)FhePathOperations::IsSourcePathSupported(v8, v24) )
  {
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      goto LABEL_84;
    v26 = 30;
LABEL_44:
    WPP_SF_(v25[2], v26, &WPP_bfc8787af4c333f8e14229724fcb8e50_Traceguids);
    goto LABEL_84;
  }
  FileW = CreateFileW(v8, 0x80u, 7u, 0, 3u, 0x200080u, 0);
  v28 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    if ( GetFileInformationByHandle(FileW, &FileInformation) )
    {
      InBuffer = 131074;
      if ( DeviceIoControl(v28, 0x900EBu, &InBuffer, 4u, &OutBuffer, 0x248u, &BytesReturned, 0) )
      {
        if ( BytesReturned >= 0x20 && OutBuffer >= 0x20 && v56 == 2 )
        {
          CloseHandle(v28);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Replace(
            &lpFileName,
            32,
            42);
          LODWORD(hTemplateFile) = FileInformation.dwFileAttributes;
          v8 = lpFileName;
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
            &Buffer,
            L"<1 %x %x %s %I64x %x %I64x %I64x>\n",
            (unsigned int)(HIDWORD(v5[2].LockSemaphore) + 1),
            v4,
            lpFileName,
            v57,
            hTemplateFile,
            FileInformation.ftCreationTime.dwLowDateTime
          + ((unsigned __int64)FileInformation.ftCreationTime.dwHighDateTime << 32),
            FileInformation.ftLastWriteTime.dwLowDateTime
          + ((unsigned __int64)FileInformation.ftLastWriteTime.dwHighDateTime << 32));
          v34 = NtWriteFile(v5[6].DebugInfo, 0, 0, 0, &IoStatusBlock, Buffer, 2 * *((_DWORD *)Buffer - 4), 0, 0);
          v35 = v34;
          if ( v34 )
          {
            v36 = RtlNtStatusToDosError(v34);
            v12 = v36;
            if ( v36 > 0 )
              v12 = (unsigned __int16)v36 | 0x80070000;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), v37, v38, v35);
          }
          goto LABEL_84;
        }
        v12 = -2147418113;
        v31 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
LABEL_80:
          CloseHandle(v28);
          goto LABEL_84;
        }
        v32 = 34;
      }
      else
      {
        v33 = GetLastError();
        v12 = v33;
        if ( v33 > 0 )
          v12 = (unsigned __int16)v33 | 0x80070000;
        v31 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_80;
        v32 = 33;
      }
    }
    else
    {
      v30 = GetLastError();
      v12 = v30;
      if ( v30 > 0 )
        v12 = (unsigned __int16)v30 | 0x80070000;
      v31 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_80;
      v32 = 32;
    }
    WPP_SF_d(v31[2], v32, &WPP_bfc8787af4c333f8e14229724fcb8e50_Traceguids, v12);
    goto LABEL_80;
  }
  LastError = GetLastError();
  v12 = LastError;
  if ( LastError > 0 )
    v12 = (unsigned __int16)LastError | 0x80070000;
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v14 = 31;
LABEL_39:
    v15 = v12;
    goto LABEL_15;
  }
LABEL_84:
  ATL::CStringData::Release((ATL::CStringData *)((char *)Buffer - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v8 - 12));
  SmartPtr<CFileRecord>::~SmartPtr<CFileRecord>(&v49);
  LeaveCriticalSection(lpCriticalSection);
  return v12;
}

```

## disassembly

```asm
0x1800236d0  mov     [rsp+arg_18], rbx
0x1800236d5  push    rsi
0x1800236d6  push    rdi
0x1800236d7  push    r12
0x1800236d9  push    r13
0x1800236db  push    r14
0x1800236dd  sub     rsp, 350h
0x1800236e4  mov     rax, cs:__security_cookie
0x1800236eb  xor     rax, rsp
0x1800236ee  mov     [rsp+378h+var_38], rax
0x1800236f6  mov     rbx, r8
0x1800236f9  mov     r13d, edx
0x1800236fc  mov     r14, rcx
0x1800236ff  mov     [rsp+378h+var_328], rcx
0x180023704  mov     [rsp+378h+var_308], edx
0x180023708  lea     rax, [rcx+0C8h]
0x18002370f  mov     [rsp+378h+lpCriticalSection], rax
0x180023717  mov     [rsp+378h+var_2D8], rax
0x18002371f  mov     rcx, rax; lpCriticalSection
0x180023722  call    cs:__imp_EnterCriticalSection
0x180023728  nop
0x180023729  xorps   xmm0, xmm0
0x18002372c  xor     eax, eax
0x18002372e  movups  xmmword ptr [rsp+378h+FileInformation.dwFileAttributes], xmm0
0x180023736  movups  xmmword ptr [rsp+378h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x18002373e  movups  xmmword ptr [rsp+378h+FileInformation.nFileSizeHigh], xmm0
0x180023746  mov     [rsp+378h+FileInformation.nFileIndexLow], eax
0x18002374d  movups  xmmword ptr [rsp+378h+IoStatusBlock], xmm0
0x180023755  lea     rcx, [rsp+378h+var_2F0]
0x18002375d  call    ??0?$SmartPtr@VCNamespaceRecord@@@@QEAA@PEAVCNamespaceRecord@@@Z; SmartPtr<CNamespaceRecord>::SmartPtr<CNamespaceRecord>(CNamespaceRecord *)
0x180023762  nop
0x180023763  lea     rcx, [rsp+378h+lpFileName]
0x180023768  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18002376d  nop
0x18002376e  mov     [rsp+378h+InBuffer], 0
0x180023776  mov     [rsp+378h+BytesReturned], 0
0x18002377e  mov     [rsp+378h+RandomBuffer], 0
0x180023787  lea     rcx, [rsp+378h+Buffer]
0x18002378f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180023794  nop
0x180023795  mov     rdx, rbx
0x180023798  lea     rcx, [rsp+378h+var_310]
0x18002379d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800237a2  nop
0x1800237a3  mov     rdx, [rax]
0x1800237a6  lea     rcx, [rdx-18h]
0x1800237aa  mov     rbx, [rsp+378h+lpFileName]
0x1800237af  lea     rdi, [rbx-18h]
0x1800237b3  cmp     rcx, rdi
0x1800237b6  jz      short loc_1800237F4
0x1800237b8  cmp     dword ptr [rdi+10h], 0
0x1800237bc  jl      short loc_1800237E1
0x1800237be  mov     rax, [rdi]
0x1800237c1  cmp     [rcx], rax
0x1800237c4  jnz     short loc_1800237E1
0x1800237c6  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x1800237cb  mov     rbx, rax
0x1800237ce  mov     rcx, rdi; this
0x1800237d1  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800237d6  add     rbx, 18h
0x1800237da  mov     [rsp+378h+lpFileName], rbx
0x1800237df  jmp     short loc_1800237F4
0x1800237e1  mov     r8d, [rdx-10h]
0x1800237e5  lea     rcx, [rsp+378h+lpFileName]
0x1800237ea  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800237ef  mov     rbx, [rsp+378h+lpFileName]
0x1800237f4  mov     rcx, [rsp+378h+var_310]
0x1800237f9  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800237fd  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180023802  nop
0x180023803  jmp     short loc_180023822
0x180023805  mov     rbx, [rsp+378h+lpFileName]
0x18002380a  mov     esi, dword ptr [rsp+378h+var_310]
0x18002380e  jmp     loc_180023E06
0x180023813  mov     rbx, [rsp+378h+lpFileName]
0x180023818  mov     r14, [rsp+378h+var_328]
0x18002381d  mov     r13d, [rsp+378h+var_308]
0x180023822  lea     rdi, WPP_GLOBAL_Control
0x180023829  mov     rcx, cs:WPP_GLOBAL_Control
0x180023830  lea     r12, WPP_bfc8787af4c333f8e14229724fcb8e50_Traceguids
0x180023837  cmp     rcx, rdi
0x18002383a  jz      short loc_18002385B
0x18002383c  test    byte ptr [rcx+1Ch], 8
0x180023840  jz      short loc_18002385B
0x180023842  mov     edx, 19h
0x180023847  mov     qword ptr [rsp+378h+dwCreationDisposition], rbx
0x18002384c  mov     r9d, r13d
0x18002384f  mov     r8, r12
0x180023852  mov     rcx, [rcx+10h]
0x180023856  call    WPP_SF_dS
0x18002385b  lea     rcx, [r14+40h]
0x18002385f  lea     r8, [rsp+378h+var_2F0]
0x180023867  mov     edx, r13d
0x18002386a  call    ?GetFileRecord@CSessionBaseRO@@IEAAJKAEAV?$SmartPtr@VCFileRecord@@@@@Z; CSessionBaseRO::GetFileRecord(ulong,SmartPtr<CFileRecord> &)
0x18002386f  mov     esi, eax
0x180023871  test    eax, eax
0x180023873  jns     short loc_1800238A8
0x180023875  mov     rcx, cs:WPP_GLOBAL_Control
0x18002387c  cmp     rcx, rdi
0x18002387f  jz      loc_180023E06
0x180023885  test    byte ptr [rcx+1Ch], 1
0x180023889  jz      loc_180023E06
0x18002388f  mov     edx, 1Ah
0x180023894  mov     r9d, eax
0x180023897  mov     r8, r12
0x18002389a  mov     rcx, [rcx+10h]
0x18002389e  call    WPP_SF_d
0x1800238a3  jmp     loc_180023E06
0x1800238a8  mov     rdi, [rsp+378h+var_2F0]
0x1800238b0  test    rdi, rdi
0x1800238b3  jz      loc_180023DCF
0x1800238b9  cmp     qword ptr [rdi], 0
0x1800238bd  jz      loc_180023DCF
0x1800238c3  mov     rax, [rdi]
0x1800238c6  mov     ecx, 4
0x1800238cb  cmp     [rax+28h], cx
0x1800238cf  jnz     short loc_1800238DA
0x1800238d1  inc     dword ptr [r14+170h]
0x1800238d8  jmp     short loc_1800238EC
0x1800238da  mov     edx, 3
0x1800238df  cmp     [rax+28h], dx
0x1800238e3  jnz     short loc_1800238EC
0x1800238e5  inc     dword ptr [r14+174h]
0x1800238ec  mov     rax, [rdi]
0x1800238ef  mov     rcx, [rax+30h]
0x1800238f3  add     [r14+178h], rcx
0x1800238fa  mov     rax, [rdi]
0x1800238fd  mov     rcx, [rax+30h]
0x180023901  cmp     rcx, [r14+140h]
0x180023908  jle     short loc_18002392F
0x18002390a  mov     [r14+140h], rcx
0x180023911  lea     rdx, [rsp+378h+lpFileName]
0x180023916  lea     rcx, [rsp+378h+var_328]
0x18002391b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180023920  lea     rdx, [r14+160h]
0x180023927  mov     rcx, rax
0x18002392a  call    ?ExtractTruncatedFileExt@FheFileOperations@@YAXV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV23@@Z; FheFileOperations::ExtractTruncatedFileExt(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18002392f  mov     edx, 8; RandomBufferLength
0x180023934  lea     rcx, [rsp+378h+RandomBuffer]; RandomBuffer
0x180023939  call    cs:__imp_SystemFunction036
0x18002393f  mov     eax, [r14+174h]
0x180023946  add     eax, [r14+170h]
0x18002394d  movsxd  rcx, eax
0x180023950  xor     edx, edx
0x180023952  mov     rax, [rsp+378h+RandomBuffer]
0x180023957  div     rcx
0x18002395a  test    rdx, rdx
0x18002395d  jnz     short loc_18002398B
0x18002395f  mov     rax, [rdi]
0x180023962  mov     rcx, [rax+30h]
0x180023966  mov     [r14+138h], rcx
0x18002396d  lea     rdx, [rsp+378h+lpFileName]
0x180023972  lea     rcx, [rsp+378h+var_328]
0x180023977  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18002397c  lea     rdx, [r14+158h]
0x180023983  mov     rcx, rax
0x180023986  call    ?ExtractTruncatedFileExt@FheFileOperations@@YAXV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV23@@Z; FheFileOperations::ExtractTruncatedFileExt(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18002398b  mov     rax, [rdi]
0x18002398e  mov     edx, [rax+40h]
0x180023991  cmp     edx, [r14+148h]
0x180023998  jnz     short loc_1800239A3
0x18002399a  inc     dword ptr [r14+14Ch]
0x1800239a1  jmp     short loc_1800239C7
0x1800239a3  jge     short loc_1800239C7
0x1800239a5  mov     rcx, [r14+48h]
0x1800239a9  mov     rax, [rcx]
0x1800239ac  lea     r8, [r14+150h]
0x1800239b3  mov     rax, [rax+58h]
0x1800239b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800239bc  mov     dword ptr [r14+14Ch], 1
0x1800239c7  mov     rax, [rdi]
0x1800239ca  mov     r8d, [rax+40h]
0x1800239ce  cmp     r8d, [r14+148h]
0x1800239d5  jl      short loc_1800239EF
0x1800239d7  jnz     short loc_180023A14
0x1800239d9  movsxd  rcx, dword ptr [r14+14Ch]
0x1800239e0  xor     edx, edx
0x1800239e2  mov     rax, [rsp+378h+RandomBuffer]
0x1800239e7  div     rcx
0x1800239ea  test    rdx, rdx
0x1800239ed  jnz     short loc_180023A14
0x1800239ef  mov     [r14+148h], r8d
0x1800239f6  lea     rdx, [rsp+378h+lpFileName]
0x1800239fb  lea     rcx, [rsp+378h+var_328]
0x180023a00  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180023a05  lea     rdx, [r14+168h]
0x180023a0c  mov     rcx, rax
0x180023a0f  call    ?ExtractTruncatedFileExt@FheFileOperations@@YAXV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV23@@Z; FheFileOperations::ExtractTruncatedFileExt(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180023a14  cmp     qword ptr [r14+0F0h], 0FFFFFFFFFFFFFFFFh
0x180023a1c  jnz     short loc_180023A5A
0x180023a1e  mov     rcx, r14; this
0x180023a21  call    ?OpenRestoreLog@CRestoreSession@@AEAAJXZ; CRestoreSession::OpenRestoreLog(void)
0x180023a26  mov     esi, eax
0x180023a28  test    eax, eax
0x180023a2a  jns     short loc_180023A5A
0x180023a2c  mov     rcx, cs:WPP_GLOBAL_Control
0x180023a33  lea     rax, WPP_GLOBAL_Control
0x180023a3a  cmp     rcx, rax
0x180023a3d  jz      loc_180023E06
0x180023a43  test    byte ptr [rcx+1Ch], 1
0x180023a47  jz      loc_180023E06
0x180023a4d  mov     edx, 1Ch
0x180023a52  mov     r9d, esi
0x180023a55  jmp     loc_180023897
0x180023a5a  lea     rdx, [rsp+378h+lpFileName]
0x180023a5f  lea     rcx, [rsp+378h+var_328]
0x180023a64  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180023a69  mov     rdx, rax
0x180023a6c  mov     rcx, r14
0x180023a6f  call    ?PathIsWithinProtectionScope@CRestoreSession@@AEAAHV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CRestoreSession::PathIsWithinProtectionScope(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>)
0x180023a74  test    eax, eax
0x180023a76  jnz     short loc_180023AAF
0x180023a78  mov     rcx, cs:WPP_GLOBAL_Control
0x180023a7f  lea     rax, WPP_GLOBAL_Control
0x180023a86  cmp     rcx, rax
0x180023a89  jz      loc_180023E06
0x180023a8f  test    byte ptr [rcx+1Ch], 8
0x180023a93  jz      loc_180023E06
0x180023a99  mov     edx, 1Dh
0x180023a9e  mov     r8, r12
0x180023aa1  mov     rcx, [rcx+10h]
0x180023aa5  call    WPP_SF_
0x180023aaa  jmp     loc_180023E06
0x180023aaf  mov     rcx, rbx; lpString
0x180023ab2  call    ?IsSourcePathSupported@FhePathOperations@@YAHPEBG@Z; FhePathOperations::IsSourcePathSupported(ushort const *)
0x180023ab7  test    eax, eax
0x180023ab9  jnz     short loc_180023AE3
0x180023abb  mov     rcx, cs:WPP_GLOBAL_Control
0x180023ac2  lea     rax, WPP_GLOBAL_Control
0x180023ac9  cmp     rcx, rax
0x180023acc  jz      loc_180023E06
0x180023ad2  test    byte ptr [rcx+1Ch], 8
0x180023ad6  jz      loc_180023E06
0x180023adc  mov     edx, 1Eh
0x180023ae1  jmp     short loc_180023A9E
0x180023ae3  mov     [rsp+378h+hTemplateFile], 0; hTemplateFile
0x180023aec  mov     [rsp+378h+dwFlagsAndAttributes], 200080h; dwFlagsAndAttributes
0x180023af4  mov     [rsp+378h+dwCreationDisposition], 3; dwCreationDisposition
0x180023afc  xor     r9d, r9d; lpSecurityAttributes
0x180023aff  mov     edx, 80h; dwDesiredAccess
0x180023b04  lea     r8d, [r9+7]; dwShareMode
0x180023b08  mov     rcx, rbx; lpFileName
0x180023b0b  call    cs:__imp_CreateFileW
0x180023b11  mov     rdi, rax
0x180023b14  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180023b18  jnz     short loc_180023B5A
0x180023b1a  call    cs:__imp_GetLastError
0x180023b20  mov     esi, eax
0x180023b22  test    eax, eax
0x180023b24  jle     short loc_180023B2F
0x180023b26  movzx   esi, ax
0x180023b29  or      esi, 80070000h
0x180023b2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180023b36  lea     rax, WPP_GLOBAL_Control
0x180023b3d  cmp     rcx, rax
0x180023b40  jz      loc_180023E06
0x180023b46  test    byte ptr [rcx+1Ch], 1
0x180023b4a  jz      loc_180023E06
0x180023b50  mov     edx, 1Fh
0x180023b55  jmp     loc_180023A52
0x180023b5a  lea     rdx, [rsp+378h+FileInformation]; lpFileInformation
0x180023b62  mov     rcx, rdi; hFile
0x180023b65  call    cs:__imp_GetFileInformationByHandle
0x180023b6b  test    eax, eax
0x180023b6d  jnz     short loc_180023BAF
0x180023b6f  call    cs:__imp_GetLastError
0x180023b75  mov     esi, eax
0x180023b77  test    eax, eax
0x180023b79  jle     short loc_180023B84
0x180023b7b  movzx   esi, ax
0x180023b7e  or      esi, 80070000h
0x180023b84  mov     rcx, cs:WPP_GLOBAL_Control
0x180023b8b  lea     rax, WPP_GLOBAL_Control
0x180023b92  cmp     rcx, rax
0x180023b95  jz      loc_180023DC4
0x180023b9b  test    byte ptr [rcx+1Ch], 1
0x180023b9f  jz      loc_180023DC4
0x180023ba5  mov     edx, 20h ; ' '
0x180023baa  jmp     loc_180023DB5
0x180023baf  mov     [rsp+378h+InBuffer], 20002h
0x180023bb7  mov     [rsp+378h+lpOverlapped], 0; lpOverlapped
0x180023bc0  lea     rax, [rsp+378h+BytesReturned]
0x180023bc5  mov     [rsp+378h+hTemplateFile], rax; lpBytesReturned
0x180023bca  mov     [rsp+378h+dwFlagsAndAttributes], 248h; nOutBufferSize
0x180023bd2  lea     rax, [rsp+378h+OutBuffer]
0x180023bda  mov     qword ptr [rsp+378h+dwCreationDisposition], rax; lpOutBuffer
0x180023bdf  mov     r9d, 4; nInBufferSize
0x180023be5  lea     r8, [rsp+378h+InBuffer]; lpInBuffer
0x180023bea  mov     edx, 900EBh; dwIoControlCode
0x180023bef  mov     rcx, rdi; hDevice
0x180023bf2  call    cs:__imp_DeviceIoControl
0x180023bf8  test    eax, eax
0x180023bfa  jnz     short loc_180023C3C
0x180023bfc  call    cs:__imp_GetLastError
0x180023c02  mov     esi, eax
0x180023c04  test    eax, eax
0x180023c06  jle     short loc_180023C11
0x180023c08  movzx   esi, ax
0x180023c0b  or      esi, 80070000h
0x180023c11  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
