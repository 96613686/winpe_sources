# CEnumOfflineFilesItems::Next(ulong,IOfflineFilesItem * *,ulong *)

- ea: `0x1800020a0`
- end: `0x180002d74`
- name: `?Next@CEnumOfflineFilesItems@@UEAAJKPEAPEAUIOfflineFilesItem@@PEAK@Z`
- size: `3284`
- prototype: `__int64 __fastcall(CEnumOfflineFilesItems *__hidden this, unsigned int, struct IOfflineFilesItem **, unsigned int *)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800020a0`
- `0x180002d80`
- `0x180003600`
- `0x180003680`
- `0x180003710`
- `0x1800083f0`
- `0x180008550`
- `0x180008840`
- `0x18000943c`
- `0x18000b390`
- `0x18000b7c0`
- `0x18000c174`
- `0x1800102a8`
- `0x180011d08`
- `0x180011e04`
- `0x18002ac30`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002d2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002d2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800021ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002284`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800021ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002284`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002164`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002164`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002144`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800021ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002267`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002144`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800021ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002267`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800021c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000227a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800021c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000227a`
- `ntdll!RtlFreeUnicodeString` at `0x180002d1d`
- `ntdll!RtlFreeUnicodeString` at `0x180002d1d`
- `ntdll!RtlpEnsureBufferSize` at `0x1800025d6`
- `ntdll!RtlpEnsureBufferSize` at `0x18000273a`
- `ntdll!RtlpEnsureBufferSize` at `0x18000293c`
- `ntdll!RtlpEnsureBufferSize` at `0x180002b69`
- `ntdll!RtlpEnsureBufferSize` at `0x1800025d6`
- `ntdll!RtlpEnsureBufferSize` at `0x18000273a`
- `ntdll!RtlpEnsureBufferSize` at `0x18000293c`
- `ntdll!RtlpEnsureBufferSize` at `0x180002b69`
- `ntdll!RtlInitUnicodeString` at `0x18000259c`
- `ntdll!RtlInitUnicodeString` at `0x180002700`
- `ntdll!RtlInitUnicodeString` at `0x180002902`
- `ntdll!RtlInitUnicodeString` at `0x180002b2f`
- `ntdll!RtlInitUnicodeString` at `0x18000259c`
- `ntdll!RtlInitUnicodeString` at `0x180002700`
- `ntdll!RtlInitUnicodeString` at `0x180002902`
- `ntdll!RtlInitUnicodeString` at `0x180002b2f`

## pseudocode

```c
__int64 __fastcall CEnumOfflineFilesItems::Next(
        CEnumOfflineFilesItems *this,
        unsigned int a2,
        struct IOfflineFilesItem **a3,
        unsigned int *a4)
{
  unsigned __int64 v4; // r15
  unsigned int *v5; // r14
  __int64 v6; // rbx
  __int64 v7; // r12
  char *v8; // r13
  HANDLE ProcessHeap; // rcx
  void **v10; // r9
  int v11; // edi
  HANDLE v12; // rax
  __int64 i; // rbx
  void *v15; // rcx
  HANDLE v16; // rax
  CEnumOfflineFilesItems *v17; // rsi
  WCHAR *v18; // rcx
  _QWORD *v19; // r14
  const unsigned __int16 *ConstBuffer; // r15
  bool v21; // zf
  struct IOfflineFilesService *v22; // rbx
  char *v23; // r13
  int v24; // eax
  _DWORD *v25; // rax
  _DWORD *v26; // rsi
  _DWORD *v27; // rbx
  int v28; // r15d
  __int64 v29; // rdx
  SIZE_T v30; // r8
  __int64 v31; // rcx
  unsigned __int64 v32; // rax
  __int64 v33; // rcx
  unsigned __int64 v34; // rdx
  char *v35; // rax
  __int64 v36; // rcx
  __int128 v37; // xmm0
  const unsigned __int16 *NextComponent; // rax
  unsigned __int16 *v39; // rcx
  __int64 Length; // rdx
  SIZE_T v41; // r8
  __int64 v42; // rcx
  unsigned __int64 v43; // rax
  __int64 v44; // rcx
  unsigned __int64 v45; // rdx
  _DWORD *v46; // rax
  _DWORD *v47; // rbx
  int v48; // r15d
  __int64 v49; // rdx
  SIZE_T v50; // r8
  __int64 v51; // rcx
  unsigned __int64 v52; // rax
  __int64 v53; // rcx
  unsigned __int64 v54; // rdx
  char *v55; // rax
  __int64 v56; // rcx
  __int128 v57; // xmm0
  _QWORD *v58; // rax
  COfflineFilesItem *v59; // rbx
  _QWORD *v60; // rax
  int v61; // eax
  COfflineFilesShareItem *v62; // rbx
  int v63; // eax
  __int64 v64; // rdx
  SIZE_T v65; // r8
  __int64 v66; // rcx
  unsigned __int64 v67; // rax
  __int64 v68; // rcx
  unsigned __int64 v69; // rdx
  COfflineFilesShareItem *v70; // rax
  COfflineFilesShareItem *v71; // rax
  int v72; // ecx
  int v73; // ecx
  int v74; // ecx
  int v75; // ecx
  __int64 v76; // rsi
  struct IOfflineFilesItem **v77; // rdi
  struct IOfflineFilesItem **v78; // rbx
  int v79; // [rsp+30h] [rbp-D0h]
  int v80; // [rsp+30h] [rbp-D0h]
  _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-B8h] BYREF
  int v83; // [rsp+50h] [rbp-B0h]
  _QWORD *v84; // [rsp+58h] [rbp-A8h]
  unsigned int v85; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int *v86; // [rsp+68h] [rbp-98h]
  unsigned int v87; // [rsp+70h] [rbp-90h]
  CEnumOfflineFilesItems *v88; // [rsp+78h] [rbp-88h]
  char *v89; // [rsp+80h] [rbp-80h]
  struct IOfflineFilesItem **v90; // [rsp+88h] [rbp-78h]
  struct _UNICODE_STRING UnicodeString; // [rsp+90h] [rbp-70h] BYREF
  _WORD v92[260]; // [rsp+A0h] [rbp-60h] BYREF
  int v93; // [rsp+2A8h] [rbp+1A8h]
  _WORD *v94; // [rsp+2B0h] [rbp+1B0h]
  WCHAR *v95; // [rsp+2B8h] [rbp+1B8h]
  WCHAR *v96; // [rsp+2C0h] [rbp+1C0h]
  __int64 v97; // [rsp+2C8h] [rbp+1C8h]
  __int64 v98; // [rsp+2D0h] [rbp+1D0h]

  v4 = a2;
  v5 = a4;
  v87 = a2;
  v86 = a4;
  v90 = a3;
  v88 = this;
  if ( !a3 )
    return 2147500035LL;
  if ( !a4 && a2 != 1 )
    return 2147942487LL;
  v6 = a2;
  v7 = 0;
  v83 = 0;
  *(_QWORD *)&DestinationString.Length = 0;
  if ( is_mul_ok(a2, 0x300u) )
  {
    v8 = 0;
    v89 = 0;
    ProcessHeap = GetProcessHeap();
    v11 = -2147418113;
    if ( ProcessHeap )
    {
      v11 = 0;
      v89 = (char *)HeapAlloc(ProcessHeap, 8u, 768 * v4);
      v8 = v89;
      if ( !v89 )
        v11 = -2147024882;
    }
    if ( v11 >= 0 )
    {
      lpMem = 0;
      *(_QWORD *)&DestinationString.Length = 0;
      if ( !is_mul_ok(v4, 8u) )
      {
        v11 = -2147024362;
        v79 = -2147024362;
LABEL_10:
        if ( v8 )
        {
          v12 = GetProcessHeap();
          if ( v12 )
          {
            if ( !HeapFree(v12, 0, v8) )
              GetLastError();
          }
        }
        goto LABEL_14;
      }
      v79 = UstVarLib::CscUtil_HeapAlloc(8 * v6, (v4 * (unsigned __int128)8uLL) >> 64, &lpMem, v10);
      v11 = v79;
      if ( v79 < 0 )
        goto LABEL_10;
      v17 = v88;
      v19 = lpMem;
      v85 = 0;
      v79 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, char *, LPVOID, unsigned int *))(**((_QWORD **)v88 + 3) + 24LL))(
              *((_QWORD *)v88 + 3),
              (unsigned int)v4,
              v8,
              lpMem,
              &v85);
      v11 = v79;
      if ( v79 < 0 )
      {
LABEL_22:
        if ( v19 )
        {
          for ( i = (unsigned int)(v4 - 1); (int)i >= 0; i = (unsigned int)(i - 1) )
          {
            v15 = (void *)v19[i];
            if ( v15 )
              CoTaskMemFree(v15);
          }
          v16 = GetProcessHeap();
          if ( v16 && !HeapFree(v16, 0, v19) )
            GetLastError();
        }
        v5 = v86;
        goto LABEL_10;
      }
      v80 = 0;
      while ( 1 )
      {
        if ( (unsigned int)v7 >= v85 || (unsigned int)v7 >= (unsigned int)v4 )
        {
LABEL_21:
          LODWORD(v7) = v83;
          v79 = v11;
          goto LABEL_22;
        }
        ConstBuffer = (const unsigned __int16 *)*((_QWORD *)v17 + 71);
        if ( ConstBuffer == *((const unsigned __int16 **)v17 + 72) )
          ConstBuffer = (const unsigned __int16 *)*((_QWORD *)v17 + 70);
        v97 = 520;
        v95 = v92;
        v96 = v92;
        v94 = v92;
        v21 = (*((_BYTE *)v17 + 608) & 1) == 0;
        v98 = 520;
        v92[0] = 0;
        v93 = 34078720;
        if ( v21 )
          goto LABEL_52;
        v11 = CPath::Copy((CPath *)v92, (const unsigned __int16 *)v19[v7]);
        if ( v11 >= 0 )
        {
          v11 = CPath::RemoveFileSpecAndBackslash((CPath *)v92);
          if ( v11 >= 0 )
            break;
        }
LABEL_37:
        v18 = v96;
        if ( v95 && v95 != v96 )
        {
          *(_QWORD *)&UnicodeString.Length = 0;
          UnicodeString.Buffer = v95;
          RtlFreeUnicodeString(&UnicodeString);
          v18 = v96;
        }
        if ( v18 )
          *v18 = 0;
        LODWORD(v4) = v87;
        v7 = (unsigned int)(v7 + 1);
        if ( v11 < 0 )
          goto LABEL_21;
      }
      ConstBuffer = CPath::_GetConstBuffer((CPath *)v92);
LABEL_52:
      lpMem = 0;
      v22 = (struct IOfflineFilesService *)*((_QWORD *)v17 + 2);
      v11 = -2147024882;
      v23 = &v8[768 * (unsigned int)v7];
      *(_QWORD *)&DestinationString.Length = v22;
      v24 = *((_DWORD *)v23 + 1);
      if ( (v24 & 0x40) != 0 )
      {
        v58 = operator new(0x570u);
        v84 = v58;
        if ( !v58 )
          goto LABEL_35;
        v59 = (COfflineFilesItem *)(v58 + 2);
        COfflineFilesItem::COfflineFilesItem(
          (COfflineFilesItem *)(v58 + 2),
          OFFLINEFILES_ITEM_TYPE_SERVER,
          *(struct IOfflineFilesService **)&DestinationString.Length);
        v60 = v84;
        *v84 = &COfflineFilesServerItem::`vftable'{for `IOfflineFilesServerItem'};
        v60[1] = &COfflineFilesServerItem::`vftable'{for `IOfflineFilesItemContainer'};
        *(_QWORD *)v59 = &COfflineFilesServerItem::`vftable'{for `COfflineFilesItem'};
        *((_DWORD *)v60 + 346) = 1;
        v61 = COfflineFilesItem::_Initialize(v59, ConstBuffer, (const struct tagOFFLINEFILES_ITEM_DESCRIPTOR *)v23);
        v62 = (COfflineFilesShareItem *)v84;
        v11 = v61;
        if ( v61 < 0 )
          goto LABEL_100;
        v63 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, LPVOID *))*v84)(v84, &IID_IOfflineFilesItem, &lpMem);
      }
      else
      {
        if ( (v24 & 0x4000) == 0 )
        {
          if ( (v23[120] & 0x10) == 0 )
          {
            v25 = operator new(0x5B0u);
            v26 = v25;
            if ( !v25 )
              goto LABEL_34;
            v25[22] = 0;
            *((_QWORD *)v25 + 12) = v22;
            *((_QWORD *)v25 + 10) = &COfflineFilesItem::`vftable';
            *((_QWORD *)v25 + 80) = v25 + 26;
            *((_QWORD *)v25 + 82) = 520;
            *((_QWORD *)v25 + 81) = v25 + 26;
            *((_QWORD *)v25 + 83) = 520;
            *((_QWORD *)v25 + 79) = v25 + 26;
            if ( v25 != (_DWORD *)-104LL )
              **((_WORD **)v25 + 79) = 0;
            *((_WORD *)v25 + 313) = 520;
            *((_WORD *)v25 + 312) = 0;
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v25 + 12) + 8LL))(*((_QWORD *)v25 + 12));
            v27 = v26 + 170;
            memset_0(v26 + 170, 0, 0x300u);
            v26[362] = 1;
            *(_QWORD *)v26 = &COfflineFilesFileItem::`vftable'{for `IOfflineFilesFileItem'};
            *((_QWORD *)v26 + 1) = &COfflineFilesFileItem::`vftable'{for `IOfflineFilesChangeInfo'};
            *((_QWORD *)v26 + 2) = &COfflineFilesFileItem::`vftable'{for `IOfflineFilesDirtyInfo'};
            *((_QWORD *)v26 + 3) = &COfflineFilesFileItem::`vftable'{for `IOfflineFilesPinInfo2'};
            *((_QWORD *)v26 + 4) = &COfflineFilesFileItem::`vftable'{for `IOfflineFilesFileSysInfo'};
            *((_QWORD *)v26 + 5) = &COfflineFilesFileItem::`vftable'{for `IOfflineFilesConnectionInfo'};
            *((_QWORD *)v26 + 6) = &COfflineFilesFileItem::`vftable'{for `IOfflineFilesShareInfo'};
            *((_QWORD *)v26 + 7) = &COfflineFilesFileItem::`vftable'{for `IOfflineFilesSuspendInfo'};
            *((_QWORD *)v26 + 8) = &COfflineFilesFileItem::`vftable'{for `IOfflineFilesTransparentCacheInfo'};
            *((_QWORD *)v26 + 9) = &COfflineFilesFileItem::`vftable'{for `IOfflineFilesGhostInfo'};
            *((_QWORD *)v26 + 10) = &COfflineFilesFileItem::`vftable'{for `COfflineFilesItem'};
            if ( ConstBuffer && *ConstBuffer )
            {
              LODWORD(v84) = 1;
              DestinationString = 0;
              RtlInitUnicodeString(&DestinationString, ConstBuffer);
              Length = DestinationString.Length;
              *((_WORD *)v26 + 312) = 0;
              v41 = Length + 2;
              if ( (unsigned __int64)(Length + 2) > 0xFFFE )
              {
                v74 = -1073741562;
              }
              else
              {
                if ( v26 != (_DWORD *)-640LL && v41 <= *((_QWORD *)v26 + 82) )
                  goto LABEL_75;
                if ( RtlpEnsureBufferSize(0, (PRTL_BUFFER)(v26 + 160), v41) >= 0 )
                {
                  LOWORD(Length) = DestinationString.Length;
LABEL_75:
                  v42 = *((_QWORD *)v26 + 80);
                  v11 = 0;
                  v43 = (unsigned __int64)*((unsigned __int16 *)v26 + 312) >> 1;
                  *((_QWORD *)v26 + 79) = v42;
                  memmove_0((void *)(v42 + 2 * v43), DestinationString.Buffer, (unsigned __int16)Length);
                  v44 = *((_QWORD *)v26 + 79);
                  v45 = (unsigned __int16)(*((_WORD *)v26 + 312) + DestinationString.Length);
                  *((_WORD *)v26 + 312) = v45;
                  *((_WORD *)v26 + 313) = v45 + 2;
                  *(_WORD *)(v44 + 2 * (v45 >> 1)) = 0;
LABEL_76:
                  v28 = (int)v84;
                  goto LABEL_64;
                }
                v74 = -1073741801;
              }
              v11 = ResultFromNtStatus(v74);
              goto LABEL_76;
            }
            v28 = 0;
            DestinationString = 0;
            RtlInitUnicodeString(&DestinationString, L"\\\\");
            v29 = DestinationString.Length;
            *((_WORD *)v26 + 312) = 0;
            v30 = v29 + 2;
            if ( (unsigned __int64)(v29 + 2) > 0xFFFE )
            {
              v75 = -1073741562;
            }
            else
            {
              if ( v26 != (_DWORD *)-640LL && v30 <= *((_QWORD *)v26 + 82) )
                goto LABEL_63;
              if ( RtlpEnsureBufferSize(0, (PRTL_BUFFER)(v26 + 160), v30) >= 0 )
              {
                LOWORD(v29) = DestinationString.Length;
LABEL_63:
                v31 = *((_QWORD *)v26 + 80);
                v11 = 0;
                v32 = (unsigned __int64)*((unsigned __int16 *)v26 + 312) >> 1;
                *((_QWORD *)v26 + 79) = v31;
                memmove_0((void *)(v31 + 2 * v32), DestinationString.Buffer, (unsigned __int16)v29);
                v33 = *((_QWORD *)v26 + 79);
                v34 = (unsigned __int16)(*((_WORD *)v26 + 312) + DestinationString.Length);
                *((_WORD *)v26 + 312) = v34;
                *((_WORD *)v26 + 313) = v34 + 2;
                *(_WORD *)(v33 + 2 * (v34 >> 1)) = 0;
LABEL_64:
                if ( v11 < 0 )
                  goto LABEL_33;
                v35 = v23;
                v36 = 6;
                do
                {
                  v27 += 32;
                  v37 = *(_OWORD *)v35;
                  v35 += 128;
                  *((_OWORD *)v27 - 8) = v37;
                  *((_OWORD *)v27 - 7) = *((_OWORD *)v35 - 7);
                  *((_OWORD *)v27 - 6) = *((_OWORD *)v35 - 6);
                  *((_OWORD *)v27 - 5) = *((_OWORD *)v35 - 5);
                  *((_OWORD *)v27 - 4) = *((_OWORD *)v35 - 4);
                  *((_OWORD *)v27 - 3) = *((_OWORD *)v35 - 3);
                  *((_OWORD *)v27 - 2) = *((_OWORD *)v35 - 2);
                  *((_OWORD *)v27 - 1) = *((_OWORD *)v35 - 1);
                  --v36;
                }
                while ( v36 );
                if ( v28 || !(unsigned int)CscPath_IsUNCServer((const unsigned __int16 *)v23 + 107) )
                  goto LABEL_32;
                NextComponent = CscPath_FindNextComponent((const unsigned __int16 *)v26 + 447);
                v39 = (unsigned __int16 *)v26 + 447;
                goto LABEL_31;
              }
              v75 = -1073741801;
            }
            v11 = ResultFromNtStatus(v75);
            goto LABEL_64;
          }
          v46 = operator new(0x5B8u);
          v26 = v46;
          if ( !v46 )
            goto LABEL_34;
          v46[24] = 1;
          *((_QWORD *)v46 + 13) = v22;
          *((_QWORD *)v46 + 11) = &COfflineFilesItem::`vftable';
          *((_QWORD *)v46 + 81) = v46 + 28;
          *((_QWORD *)v46 + 83) = 520;
          *((_QWORD *)v46 + 82) = v46 + 28;
          *((_QWORD *)v46 + 84) = 520;
          *((_QWORD *)v46 + 80) = v46 + 28;
          if ( v46 != (_DWORD *)-112LL )
            **((_WORD **)v46 + 80) = 0;
          *((_WORD *)v46 + 317) = 520;
          *((_WORD *)v46 + 316) = 0;
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v46 + 13) + 8LL))(*((_QWORD *)v46 + 13));
          v47 = v26 + 172;
          memset_0(v26 + 172, 0, 0x300u);
          v26[364] = 1;
          *(_QWORD *)v26 = &COfflineFilesDirectoryItem::`vftable'{for `IOfflineFilesDirectoryItem'};
          *((_QWORD *)v26 + 1) = &COfflineFilesDirectoryItem::`vftable'{for `IOfflineFilesItemContainer'};
          *((_QWORD *)v26 + 2) = &COfflineFilesDirectoryItem::`vftable'{for `IOfflineFilesChangeInfo'};
          *((_QWORD *)v26 + 3) = &COfflineFilesDirectoryItem::`vftable'{for `IOfflineFilesPinInfo2'};
          *((_QWORD *)v26 + 4) = &COfflineFilesDirectoryItem::`vftable'{for `IOfflineFilesFileSysInfo'};
          *((_QWORD *)v26 + 5) = &COfflineFilesDirectoryItem::`vftable'{for `IOfflineFilesConnectionInfo'};
          *((_QWORD *)v26 + 6) = &COfflineFilesDirectoryItem::`vftable'{for `IOfflineFilesShareInfo'};
          *((_QWORD *)v26 + 7) = &COfflineFilesDirectoryItem::`vftable'{for `IOfflineFilesSuspend'};
          *((_QWORD *)v26 + 8) = &COfflineFilesDirectoryItem::`vftable'{for `IOfflineFilesSuspendInfo'};
          *((_QWORD *)v26 + 9) = &COfflineFilesDirectoryItem::`vftable'{for `IOfflineFilesTransparentCacheInfo'};
          *((_QWORD *)v26 + 10) = &COfflineFilesDirectoryItem::`vftable'{for `IOfflineFilesGhostInfo'};
          *((_QWORD *)v26 + 11) = &COfflineFilesDirectoryItem::`vftable'{for `COfflineFilesItem'};
          if ( ConstBuffer && *ConstBuffer )
          {
            LODWORD(v84) = 1;
            DestinationString = 0;
            RtlInitUnicodeString(&DestinationString, ConstBuffer);
            v64 = DestinationString.Length;
            *((_WORD *)v26 + 316) = 0;
            v65 = v64 + 2;
            if ( (unsigned __int64)(v64 + 2) > 0xFFFE )
            {
              v72 = -1073741562;
            }
            else
            {
              if ( v26 != (_DWORD *)-648LL && v65 <= *((_QWORD *)v26 + 83) )
                goto LABEL_106;
              if ( RtlpEnsureBufferSize(0, (PRTL_BUFFER)(v26 + 162), v65) >= 0 )
              {
                LOWORD(v64) = DestinationString.Length;
LABEL_106:
                v66 = *((_QWORD *)v26 + 81);
                v11 = 0;
                v67 = (unsigned __int64)*((unsigned __int16 *)v26 + 316) >> 1;
                *((_QWORD *)v26 + 80) = v66;
                memmove_0((void *)(v66 + 2 * v67), DestinationString.Buffer, (unsigned __int16)v64);
                v68 = *((_QWORD *)v26 + 80);
                v69 = (unsigned __int16)(*((_WORD *)v26 + 316) + DestinationString.Length);
                *((_WORD *)v26 + 316) = v69;
                *((_WORD *)v26 + 317) = v69 + 2;
                *(_WORD *)(v68 + 2 * (v69 >> 1)) = 0;
LABEL_107:
                v48 = (int)v84;
                goto LABEL_86;
              }
              v72 = -1073741801;
            }
            v11 = ResultFromNtStatus(v72);
            goto LABEL_107;
          }
          v48 = 0;
          DestinationString = 0;
          RtlInitUnicodeString(&DestinationString, L"\\\\");
          v49 = DestinationString.Length;
          *((_WORD *)v26 + 316) = 0;
          v50 = v49 + 2;
          if ( (unsigned __int64)(v49 + 2) > 0xFFFE )
          {
            v73 = -1073741562;
          }
          else
          {
            if ( v26 != (_DWORD *)-648LL && v50 <= *((_QWORD *)v26 + 83) )
              goto LABEL_85;
            if ( RtlpEnsureBufferSize(0, (PRTL_BUFFER)(v26 + 162), v50) >= 0 )
            {
              LOWORD(v49) = DestinationString.Length;
LABEL_85:
              v51 = *((_QWORD *)v26 + 81);
              v11 = 0;
              v52 = (unsigned __int64)*((unsigned __int16 *)v26 + 316) >> 1;
              *((_QWORD *)v26 + 80) = v51;
              memmove_0((void *)(v51 + 2 * v52), DestinationString.Buffer, (unsigned __int16)v49);
              v53 = *((_QWORD *)v26 + 80);
              v54 = (unsigned __int16)(*((_WORD *)v26 + 316) + DestinationString.Length);
              *((_WORD *)v26 + 316) = v54;
              *((_WORD *)v26 + 317) = v54 + 2;
              *(_WORD *)(v53 + 2 * (v54 >> 1)) = 0;
LABEL_86:
              if ( v11 < 0 )
                goto LABEL_33;
              v55 = v23;
              v56 = 6;
              do
              {
                v47 += 32;
                v57 = *(_OWORD *)v55;
                v55 += 128;
                *((_OWORD *)v47 - 8) = v57;
                *((_OWORD *)v47 - 7) = *((_OWORD *)v55 - 7);
                *((_OWORD *)v47 - 6) = *((_OWORD *)v55 - 6);
                *((_OWORD *)v47 - 5) = *((_OWORD *)v55 - 5);
                *((_OWORD *)v47 - 4) = *((_OWORD *)v55 - 4);
                *((_OWORD *)v47 - 3) = *((_OWORD *)v55 - 3);
                *((_OWORD *)v47 - 2) = *((_OWORD *)v55 - 2);
                *((_OWORD *)v47 - 1) = *((_OWORD *)v55 - 1);
                --v56;
              }
              while ( v56 );
              if ( v48 || !(unsigned int)CscPath_IsUNCServer((const unsigned __int16 *)v23 + 107) )
                goto LABEL_32;
              NextComponent = CscPath_FindNextComponent((const unsigned __int16 *)v26 + 451);
              v39 = (unsigned __int16 *)v26 + 451;
LABEL_31:
              v11 = StringCchCopyW(v39, 0x105u, NextComponent);
              if ( v11 < 0 )
              {
LABEL_33:
                (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v26 + 16LL))(v26);
LABEL_34:
                v17 = v88;
                goto LABEL_35;
              }
LABEL_32:
              v11 = (**(__int64 (__fastcall ***)(_DWORD *, GUID *, LPVOID *))v26)(v26, &IID_IOfflineFilesItem, &lpMem);
              goto LABEL_33;
            }
            v73 = -1073741801;
          }
          v11 = ResultFromNtStatus(v73);
          goto LABEL_86;
        }
        v70 = (COfflineFilesShareItem *)operator new(0x5B0u);
        if ( !v70 || (v71 = COfflineFilesShareItem::COfflineFilesShareItem(v70, v22), (v62 = v71) == 0) )
        {
LABEL_35:
          v8 = v89;
          if ( v11 >= 0 )
          {
            v90[v80] = (struct IOfflineFilesItem *)lpMem;
            ++v83;
            ++v80;
          }
          goto LABEL_37;
        }
        v11 = COfflineFilesItem::_Initialize(
                (COfflineFilesShareItem *)((char *)v71 + 80),
                ConstBuffer,
                (const struct tagOFFLINEFILES_ITEM_DESCRIPTOR *)v23);
        if ( v11 < 0 )
        {
LABEL_100:
          (*(void (__fastcall **)(COfflineFilesShareItem *))(*(_QWORD *)v62 + 16LL))(v62);
          goto LABEL_35;
        }
        v63 = (**(__int64 (__fastcall ***)(COfflineFilesShareItem *, GUID *, LPVOID *))v62)(
                v62,
                &IID_IOfflineFilesItem,
                &lpMem);
      }
      v11 = v63;
      goto LABEL_100;
    }
  }
  else
  {
    v11 = -2147024362;
  }
  v79 = v11;
LABEL_14:
  if ( v5 )
    *v5 = v7;
  if ( v11 < 0 )
  {
    v76 = 0;
    if ( (_DWORD)v7 )
    {
      v77 = v90;
      do
      {
        v78 = &v77[v76];
        ((void (__fastcall *)(struct IOfflineFilesItem *))(*v78)->lpVtbl->Release)(*v78);
        v76 = (unsigned int)(v76 + 1);
        *v78 = 0;
      }
      while ( (unsigned int)v76 < (unsigned int)v7 );
      return (unsigned int)v79;
    }
  }
  else
  {
    return v7 != v4;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800020a0  push    rbp
0x1800020a2  push    r14
0x1800020a4  push    r15
0x1800020a6  lea     rbp, [rsp-220h]
0x1800020ae  sub     rsp, 320h
0x1800020b5  mov     rax, cs:__security_cookie
0x1800020bc  xor     rax, rsp
0x1800020bf  mov     [rbp+230h+var_50], rax
0x1800020c6  mov     r15d, edx
0x1800020c9  mov     r14, r9
0x1800020cc  mov     [rsp+330h+var_2C0], r15d
0x1800020d1  mov     [rsp+330h+var_2C8], r9
0x1800020d6  mov     [rbp+230h+var_2A8], r8
0x1800020da  mov     [rsp+330h+var_2B8], rcx
0x1800020df  test    r8, r8
0x1800020e2  jz      loc_180002C54
0x1800020e8  test    r9, r9
0x1800020eb  jz      loc_180002C5E
0x1800020f1  mov     [rsp+330h+var_18], rbx
0x1800020f9  mov     eax, 300h
0x1800020fe  mov     [rsp+330h+var_20], rsi
0x180002106  mov     rbx, r15
0x180002109  mul     r15
0x18000210c  mov     [rsp+330h+var_28], rdi
0x180002114  mov     [rsp+330h+var_30], r12
0x18000211c  mov     rsi, rax
0x18000211f  xor     r12d, r12d
0x180002122  mov     [rsp+330h+var_38], r13
0x18000212a  mov     [rsp+330h+var_2E0], r12d
0x18000212f  mov     qword ptr [rsp+330h+DestinationString.Length], r12
0x180002134  test    rdx, rdx
0x180002137  jnz     loc_18000222F
0x18000213d  xor     r13d, r13d
0x180002140  mov     [rbp+230h+var_2B0], r13
0x180002144  call    cs:__imp_GetProcessHeap
0x18000214a  mov     rcx, rax; hHeap
0x18000214d  mov     edi, 8000FFFFh
0x180002152  xor     eax, eax
0x180002154  test    rcx, rcx
0x180002157  cmovnz  edi, eax
0x18000215a  jz      short loc_18000217C
0x18000215c  mov     r8, rsi; dwBytes
0x18000215f  mov     edx, 8; dwFlags
0x180002164  call    cs:__imp_HeapAlloc
0x18000216a  test    rax, rax
0x18000216d  mov     [rbp+230h+var_2B0], rax
0x180002171  mov     r13, rax
0x180002174  mov     eax, 8007000Eh
0x180002179  cmovz   edi, eax
0x18000217c  test    edi, edi
0x18000217e  js      loc_180002234
0x180002184  mov     eax, 8
0x180002189  mov     [rsp+330h+lpMem], r12
0x18000218e  mul     rbx
0x180002191  mov     qword ptr [rsp+330h+DestinationString.Length], r12
0x180002196  test    rdx, rdx
0x180002199  jz      loc_180002336
0x18000219f  mov     edi, 80070216h
0x1800021a4  mov     [rsp+330h+var_300], edi
0x1800021a8  test    r13, r13
0x1800021ab  jz      short loc_1800021D0
0x1800021ad  call    cs:__imp_GetProcessHeap
0x1800021b3  test    rax, rax
0x1800021b6  jz      short loc_1800021D0
0x1800021b8  mov     r8, r13; lpMem
0x1800021bb  xor     edx, edx; dwFlags
0x1800021bd  mov     rcx, rax; hHeap
0x1800021c0  call    cs:__imp_HeapFree
0x1800021c6  test    eax, eax
0x1800021c8  jnz     short loc_1800021D0
0x1800021ca  call    cs:__imp_GetLastError
0x1800021d0  mov     r13, [rsp+330h+var_38]
0x1800021d8  test    r14, r14
0x1800021db  jz      short loc_1800021E0
0x1800021dd  mov     [r14], r12d
0x1800021e0  test    edi, edi
0x1800021e2  js      loc_180002D3A
0x1800021e8  xor     edi, edi
0x1800021ea  cmp     r12d, r15d
0x1800021ed  setnz   dil
0x1800021f1  mov     r12, [rsp+330h+var_30]
0x1800021f9  mov     eax, edi
0x1800021fb  mov     rdi, [rsp+330h+var_28]
0x180002203  mov     rsi, [rsp+330h+var_20]
0x18000220b  mov     rbx, [rsp+330h+var_18]
0x180002213  mov     rcx, [rbp+230h+var_50]
0x18000221a  xor     rcx, rsp; StackCookie
0x18000221d  call    __security_check_cookie
0x180002222  add     rsp, 320h
0x180002229  pop     r15
0x18000222b  pop     r14
0x18000222d  pop     rbp
0x18000222e  retn
0x18000222f  mov     edi, 80070216h
0x180002234  mov     [rsp+330h+var_300], edi
0x180002238  jmp     short loc_1800021D0
0x18000223a  mov     r12d, [rsp+330h+var_2E0]
0x18000223f  mov     [rsp+330h+var_300], edi
0x180002243  test    r14, r14
0x180002246  jz      short loc_18000228A
0x180002248  lea     ebx, [r15-1]
0x18000224c  test    ebx, ebx
0x18000224e  js      short loc_180002262
0x180002250  mov     rcx, [r14+rbx*8]; pv
0x180002254  test    rcx, rcx
0x180002257  jnz     loc_180002D2F
0x18000225d  sub     ebx, 1
0x180002260  jns     short loc_180002250
0x180002262  test    r14, r14
0x180002265  jz      short loc_18000228A
0x180002267  call    cs:__imp_GetProcessHeap
0x18000226d  test    rax, rax
0x180002270  jz      short loc_18000228A
0x180002272  mov     r8, r14; lpMem
0x180002275  xor     edx, edx; dwFlags
0x180002277  mov     rcx, rax; hHeap
0x18000227a  call    cs:__imp_HeapFree
0x180002280  test    eax, eax
0x180002282  jnz     short loc_18000228A
0x180002284  call    cs:__imp_GetLastError
0x18000228a  mov     r14, [rsp+330h+var_2C8]
0x18000228f  jmp     loc_1800021A8
0x180002294  mov     r8, rax; unsigned __int16 *
0x180002297  mov     edx, 105h; unsigned __int64
0x18000229c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800022a1  mov     edi, eax
0x1800022a3  test    eax, eax
0x1800022a5  js      short loc_1800022C3
0x1800022a7  mov     rax, [rsi]
0x1800022aa  lea     r8, [rsp+330h+lpMem]
0x1800022af  lea     rdx, IID_IOfflineFilesItem
0x1800022b6  mov     rcx, rsi
0x1800022b9  mov     rax, [rax]
0x1800022bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022c1  mov     edi, eax
0x1800022c3  mov     rax, [rsi]
0x1800022c6  mov     rcx, rsi
0x1800022c9  mov     rax, [rax+10h]
0x1800022cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022d2  mov     rsi, [rsp+330h+var_2B8]
0x1800022d7  mov     r13, [rbp+230h+var_2B0]
0x1800022db  test    edi, edi
0x1800022dd  js      short loc_1800022FA
0x1800022df  mov     edx, [rsp+330h+var_300]
0x1800022e3  mov     r8, [rbp+230h+var_2A8]
0x1800022e7  mov     rax, [rsp+330h+lpMem]
0x1800022ec  mov     [r8+rdx*8], rax
0x1800022f0  inc     edx
0x1800022f2  inc     [rsp+330h+var_2E0]
0x1800022f6  mov     [rsp+330h+var_300], edx
0x1800022fa  mov     rax, [rbp+230h+var_78]
0x180002301  mov     rcx, [rbp+230h+var_70]
0x180002308  test    rax, rax
0x18000230b  jz      short loc_180002316
0x18000230d  cmp     rax, rcx
0x180002310  jnz     loc_180002D0D
0x180002316  test    rcx, rcx
0x180002319  jz      short loc_180002320
0x18000231b  xor     eax, eax
0x18000231d  mov     [rcx], ax
0x180002320  mov     r15d, [rsp+330h+var_2C0]
0x180002325  inc     r12d
0x180002328  mov     ecx, 208h
0x18000232d  test    edi, edi
0x18000232f  jns     short loc_18000239B
0x180002331  jmp     loc_18000223A
0x180002336  lea     r8, [rsp+330h+lpMem]; int
0x18000233b  mov     rcx, rax; dwBytes
0x18000233e  call    ?CscUtil_HeapAlloc@UstVarLib@@YAJ_KHPEAPEAXPEAX@Z; UstVarLib::CscUtil_HeapAlloc(unsigned __int64,int,void * *,void *)
0x180002343  mov     [rsp+330h+var_300], eax
0x180002347  mov     edi, eax
0x180002349  test    eax, eax
0x18000234b  js      loc_1800021A8
0x180002351  mov     rsi, [rsp+330h+var_2B8]
0x180002356  lea     rdx, [rsp+330h+var_2D0]
0x18000235b  mov     r14, [rsp+330h+lpMem]
0x180002360  mov     r8, r13
0x180002363  mov     [rsp+330h+var_2D0], r12d
0x180002368  mov     r9, r14
0x18000236b  mov     [rsp+330h+var_310], rdx
0x180002370  mov     edx, r15d
0x180002373  mov     rcx, [rsi+18h]
0x180002377  mov     rax, [rcx]
0x18000237a  mov     rax, [rax+18h]
0x18000237e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002383  mov     [rsp+330h+var_300], eax
0x180002387  mov     edi, eax
0x180002389  test    eax, eax
0x18000238b  js      loc_180002243
0x180002391  mov     [rsp+330h+var_300], r12d
0x180002396  mov     ecx, 208h
0x18000239b  cmp     r12d, [rsp+330h+var_2D0]
0x1800023a0  jnb     loc_18000223A
0x1800023a6  cmp     r12d, r15d
0x1800023a9  jnb     loc_18000223A
0x1800023af  mov     r15, [rsi+238h]
0x1800023b6  cmp     r15, [rsi+240h]
0x1800023bd  jnz     short loc_1800023C6
0x1800023bf  mov     r15, [rsi+230h]
0x1800023c6  lea     rax, [rbp+230h+var_290]
0x1800023ca  mov     [rbp+230h+var_68], rcx
0x1800023d1  mov     [rbp+230h+var_78], rax
0x1800023d8  lea     rax, [rbp+230h+var_290]
0x1800023dc  mov     [rbp+230h+var_70], rax
0x1800023e3  lea     rax, [rbp+230h+var_290]
0x1800023e7  mov     [rbp+230h+var_80], rax
0x1800023ee  xor     eax, eax
0x1800023f0  test    byte ptr [rsi+260h], 1
0x1800023f7  mov     [rbp+230h+var_60], rcx
0x1800023fe  mov     [rbp+230h+var_290], ax
0x180002402  mov     [rbp+230h+var_88], 2080000h
0x18000240c  mov     ebx, r12d
0x18000240f  jnz     loc_180002C72
0x180002415  lea     rax, [rbx+rbx*2]
0x180002419  mov     [rsp+330h+lpMem], 0
0x180002422  mov     rbx, [rsi+10h]
0x180002426  mov     edi, 8007000Eh
0x18000242b  shl     rax, 8
0x18000242f  add     r13, rax
0x180002432  mov     qword ptr [rsp+330h+DestinationString.Length], rbx
0x180002437  mov     eax, [r13+4]
0x18000243b  test    al, 40h
0x18000243d  jnz     loc_180002A67
0x180002443  bt      eax, 0Eh
0x180002447  jb      loc_180002C06
0x18000244d  test    byte ptr [r13+78h], 10h
0x180002452  jnz     loc_1800027B3
0x180002458  mov     ecx, 5B0h; Size
0x18000245d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002462  mov     rsi, rax
0x180002465  test    rax, rax
0x180002468  jz      loc_1800022D2
0x18000246e  mov     dword ptr [rsi+58h], 0
0x180002475  lea     rdx, [rsi+68h]
0x180002479  mov     [rsi+60h], rbx
0x18000247d  mov     r8d, 208h
0x180002483  lea     rax, ??_7COfflineFilesItem@@6B@; const COfflineFilesItem::`vftable'
0x18000248a  mov     [rsi+50h], rax
0x18000248e  mov     [rsi+280h], rdx
0x180002495  mov     [rsi+290h], r8
0x18000249c  mov     [rsi+288h], rdx
0x1800024a3  mov     [rsi+298h], r8
0x1800024aa  mov     [rsi+278h], rdx
0x1800024b1  test    rdx, rdx
0x1800024b4  jz      short loc_1800024C2
0x1800024b6  mov     rcx, [rdx+210h]
0x1800024bd  xor     eax, eax
0x1800024bf  mov     [rcx], ax
0x1800024c2  xor     eax, eax
0x1800024c4  mov     [rsi+272h], r8w
0x1800024cc  mov     [rdx+208h], ax
0x1800024d3  mov     rcx, [rsi+60h]
0x1800024d7  mov     rax, [rcx]
0x1800024da  mov     rax, [rax+8]
0x1800024de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024e3  lea     rbx, [rsi+2A8h]
0x1800024ea  xor     edx, edx; Val
0x1800024ec  mov     rcx, rbx; void *
0x1800024ef  mov     r8d, 300h; Size
0x1800024f5  call    memset_0
0x1800024fa  mov     dword ptr [rsi+5A8h], 1
0x180002504  lea     rax, ??_7COfflineFilesFileItem@@6BIOfflineFilesFileItem@@@; const COfflineFilesFileItem::`vftable'{for `IOfflineFilesFileItem'}
0x18000250b  mov     [rsi], rax
0x18000250e  lea     rax, ??_7COfflineFilesFileItem@@6BIOfflineFilesChangeInfo@@@; const COfflineFilesFileItem::`vftable'{for `IOfflineFilesChangeInfo'}
0x180002515  mov     [rsi+8], rax
0x180002519  lea     rax, ??_7COfflineFilesFileItem@@6BIOfflineFilesDirtyInfo@@@; const COfflineFilesFileItem::`vftable'{for `IOfflineFilesDirtyInfo'}
0x180002520  mov     [rsi+10h], rax
0x180002524  lea     rax, ??_7COfflineFilesFileItem@@6BIOfflineFilesPinInfo2@@@; const COfflineFilesFileItem::`vftable'{for `IOfflineFilesPinInfo2'}
0x18000252b  mov     [rsi+18h], rax
0x18000252f  lea     rax, ??_7COfflineFilesFileItem@@6BIOfflineFilesFileSysInfo@@@; const COfflineFilesFileItem::`vftable'{for `IOfflineFilesFileSysInfo'}
0x180002536  mov     [rsi+20h], rax
0x18000253a  lea     rax, ??_7COfflineFilesFileItem@@6BIOfflineFilesConnectionInfo@@@; const COfflineFilesFileItem::`vftable'{for `IOfflineFilesConnectionInfo'}
0x180002541  mov     [rsi+28h], rax
0x180002545  lea     rax, ??_7COfflineFilesFileItem@@6BIOfflineFilesShareInfo@@@; const COfflineFilesFileItem::`vftable'{for `IOfflineFilesShareInfo'}
0x18000254c  mov     [rsi+30h], rax
0x180002550  lea     rax, ??_7COfflineFilesFileItem@@6BIOfflineFilesSuspendInfo@@@; const COfflineFilesFileItem::`vftable'{for `IOfflineFilesSuspendInfo'}
0x180002557  mov     [rsi+38h], rax
0x18000255b  lea     rax, ??_7COfflineFilesFileItem@@6BIOfflineFilesTransparentCacheInfo@@@; const COfflineFilesFileItem::`vftable'{for `IOfflineFilesTransparentCacheInfo'}
0x180002562  mov     [rsi+40h], rax
0x180002566  lea     rax, ??_7COfflineFilesFileItem@@6BIOfflineFilesGhostInfo@@@; const COfflineFilesFileItem::`vftable'{for `IOfflineFilesGhostInfo'}
0x18000256d  mov     [rsi+48h], rax
0x180002571  lea     rax, ??_7COfflineFilesFileItem@@6BCOfflineFilesItem@@@; const COfflineFilesFileItem::`vftable'{for `COfflineFilesItem'}
0x180002578  mov     [rsi+50h], rax
0x18000257c  test    r15, r15
0x18000257f  jnz     loc_1800026DD
0x180002585  xorps   xmm0, xmm0
0x180002588  lea     rdx, SourceString; "\\\\"
0x18000258f  lea     rcx, [rsp+330h+DestinationString]; DestinationString
0x180002594  xor     r15d, r15d
0x180002597  movups  xmmword ptr [rsp+330h+DestinationString.Length], xmm0
0x18000259c  call    cs:__imp_RtlInitUnicodeString
0x1800025a2  movzx   edx, [rsp+330h+DestinationString.Length]
0x1800025a7  xor     eax, eax
0x1800025a9  mov     [rsi+270h], ax
0x1800025b0  lea     r8, [rdx+2]; RequiredSize
0x1800025b4  cmp     r8, 0FFFEh
0x1800025bb  ja      loc_180002CF5
0x1800025c1  lea     rax, [rsi+280h]
0x1800025c8  test    rax, rax
0x1800025cb  jnz     loc_180002A43
  ... truncated ...
```
