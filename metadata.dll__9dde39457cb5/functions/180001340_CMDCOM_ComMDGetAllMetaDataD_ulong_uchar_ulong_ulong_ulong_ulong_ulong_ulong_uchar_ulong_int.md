# CMDCOM::ComMDGetAllMetaDataD(ulong,uchar *,ulong,ulong,ulong,ulong *,ulong *,ulong,uchar *,ulong *,int)

- ea: `0x180001340`
- end: `0x180001eec`
- name: `?ComMDGetAllMetaDataD@CMDCOM@@QEAAJKPEAEKKKPEAK1K01H@Z`
- size: `2988`
- prototype: `int(CMDCOM *__hidden this, unsigned int, unsigned __int8 *, unsigned int, unsigned int, unsigned int, unsigned int *, unsigned int *, unsigned int, unsigned __int8 *, unsigned int *, int)`
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180018110`
- `0x180018180`

## callees

- `0x180001130`
- `0x180001340`
- `0x180001ef4`
- `0x1800022a4`
- `0x180002d60`
- `0x1800035d0`
- `0x18000363c`
- `0x180003678`
- `0x1800056d0`
- `0x18003098e`
- `0x18003099a`
- `0x1800309d0`
- `0x180031010`

## import_xrefs

- `USER32!CharNextExA` at `0x180001bf1`
- `USER32!CharNextExA` at `0x180001bf1`
- `KERNEL32!LCMapStringW` at `0x18000159b`
- `KERNEL32!LCMapStringW` at `0x18000159b`
- `KERNEL32!MultiByteToWideChar` at `0x180001c53`
- `KERNEL32!MultiByteToWideChar` at `0x180001c53`
- `KERNEL32!GetLastError` at `0x1800015ac`
- `KERNEL32!GetLastError` at `0x180001c5f`
- `KERNEL32!GetLastError` at `0x1800015ac`
- `KERNEL32!GetLastError` at `0x180001c5f`
- `IisRTL!??0STRAU@@QEAA@XZ` at `0x1800017aa`
- `IisRTL!??0STRAU@@QEAA@XZ` at `0x1800017aa`
- `IisRTL!??1STRAU@@QEAA@XZ` at `0x18000184e`
- `IisRTL!??1STRAU@@QEAA@XZ` at `0x180001a5d`
- `IisRTL!??1STRAU@@QEAA@XZ` at `0x18000184e`
- `IisRTL!??1STRAU@@QEAA@XZ` at `0x180001a5d`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x180001557`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x180001671`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x180001c17`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x180001c7f`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x180001557`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x180001671`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x180001c17`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x180001c7f`
- `IisRTL!?QuerySize@BUFFER@@QEBAKXZ` at `0x180001c29`
- `IisRTL!?QuerySize@BUFFER@@QEBAKXZ` at `0x180001c72`
- `IisRTL!?QuerySize@BUFFER@@QEBAKXZ` at `0x180001ca4`
- `IisRTL!?QuerySize@BUFFER@@QEBAKXZ` at `0x180001c29`
- `IisRTL!?QuerySize@BUFFER@@QEBAKXZ` at `0x180001c72`
- `IisRTL!?QuerySize@BUFFER@@QEBAKXZ` at `0x180001ca4`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180001600`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180001600`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000140e`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000140e`
- `IisRTL!??0BUFFER@@QEAA@PEAEK@Z` at `0x1800014f5`
- `IisRTL!??0BUFFER@@QEAA@PEAEK@Z` at `0x180001539`
- `IisRTL!??0BUFFER@@QEAA@PEAEK@Z` at `0x1800014f5`
- `IisRTL!??0BUFFER@@QEAA@PEAEK@Z` at `0x180001539`
- `IisRTL!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x1800016a2`
- `IisRTL!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x1800018b7`
- `IisRTL!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x1800016a2`
- `IisRTL!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x1800018b7`
- `IisRTL!??0BUFFER@@QEAA@XZ` at `0x1800017a0`
- `IisRTL!??0BUFFER@@QEAA@XZ` at `0x1800017a0`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x1800015c6`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x1800015d5`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180001686`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x1800016b0`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180001858`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180001a67`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180001d17`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x1800015c6`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x1800015d5`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180001686`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x1800016b0`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180001858`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180001a67`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180001d17`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000156d`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180001657`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180001c37`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180001c92`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000156d`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180001657`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180001c37`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180001c92`

## pseudocode

```c
__int64 __fastcall CMDCOM::ComMDGetAllMetaDataD(
        CMDCOM *this,
        unsigned int a2,
        const CHAR *a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int *a7,
        unsigned int *a8,
        unsigned int a9,
        unsigned __int8 *a10,
        unsigned int *a11,
        int a12)
{
  void **v12; // rdi
  int v14; // ebx
  int v15; // r12d
  unsigned int v16; // r14d
  int v17; // r13d
  unsigned int v18; // r15d
  struct CMDHandle *HandleObject; // rax
  CMDBaseObject *v20; // rdx
  CMDBaseObject *v21; // rcx
  __int16 v22; // ax
  LPSTR v23; // rdi
  CHAR v24; // al
  int v25; // r14d
  const WCHAR *v26; // r15
  unsigned int v27; // ebx
  int cchDest; // ebx
  WCHAR *lpDestStr; // rcx
  int v30; // eax
  int v31; // eax
  int v32; // ebx
  int v33; // ebx
  unsigned int v35; // ebx
  CMDBaseObject *v36; // rbx
  unsigned __int8 *v37; // r12
  unsigned __int64 v38; // r14
  void **v39; // r8
  _DWORD *v40; // rax
  void **v41; // rdx
  _QWORD *v42; // rcx
  volatile signed __int32 *v43; // rsi
  BOOL v44; // ebx
  unsigned int v45; // eax
  __int64 v46; // rcx
  unsigned int v47; // r15d
  void *v48; // r13
  unsigned __int8 v49; // cl
  unsigned __int8 *v50; // rbx
  __int16 v51; // r13
  unsigned int v52; // edi
  unsigned int v53; // esi
  unsigned int v54; // eax
  unsigned int v55; // r15d
  CMDBaseObject *v56; // r13
  unsigned int v57; // r14d
  CMDBaseObject *v58; // rcx
  unsigned int v59; // r8d
  unsigned int v60; // edx
  unsigned __int8 *v61; // r13
  void *v62; // rdx
  int v63; // eax
  _QWORD *v64; // rsi
  _QWORD *v65; // rcx
  unsigned int v66; // edx
  int inserted; // eax
  void **v68; // rcx
  unsigned int *v69; // rcx
  unsigned int v70; // r14d
  int v71; // ebx
  int IsSchemaObject; // eax
  void **MainDataBuffer; // rax
  int v74; // eax
  unsigned int v75; // ebx
  WCHAR *Ptr; // rax
  int v77; // ebx
  unsigned int Size; // eax
  int v79; // eax
  CMDBaseObject *v80; // rdi
  void **v81; // rsi
  unsigned int *v82; // rdx
  unsigned __int8 *v83; // r8
  unsigned int v84; // edx
  __int64 v85; // rax
  __int64 v86; // rax
  unsigned int v87; // ecx
  unsigned __int8 *v88; // r8
  int v89; // ebx
  __int64 v90; // [rsp+48h] [rbp-C0h] BYREF
  int v91[2]; // [rsp+50h] [rbp-B8h]
  CMDBaseObject *v92; // [rsp+58h] [rbp-B0h]
  unsigned int v93; // [rsp+60h] [rbp-A8h] BYREF
  unsigned int v94; // [rsp+64h] [rbp-A4h]
  __int64 v95; // [rsp+68h] [rbp-A0h]
  unsigned __int8 *v96; // [rsp+70h] [rbp-98h]
  void **Block; // [rsp+78h] [rbp-90h]
  int v98; // [rsp+80h] [rbp-88h]
  void *Src; // [rsp+88h] [rbp-80h] BYREF
  unsigned int v100; // [rsp+90h] [rbp-78h]
  unsigned int v101; // [rsp+94h] [rbp-74h]
  int v102; // [rsp+98h] [rbp-70h]
  unsigned int *v103; // [rsp+A0h] [rbp-68h]
  struct CMDBaseObject *v104; // [rsp+A8h] [rbp-60h] BYREF
  unsigned int v105; // [rsp+B0h] [rbp-58h]
  const CHAR *i; // [rsp+B8h] [rbp-50h]
  unsigned int *v107; // [rsp+C0h] [rbp-48h]
  unsigned int v108; // [rsp+C8h] [rbp-40h] BYREF
  CMDBaseObject *v109; // [rsp+D0h] [rbp-38h]
  _BYTE v110[48]; // [rsp+D8h] [rbp-30h] BYREF
  unsigned int j; // [rsp+108h] [rbp+0h]
  CMDBaseObject *v112; // [rsp+110h] [rbp+8h]
  _BYTE v113[48]; // [rsp+118h] [rbp+10h] BYREF
  _BYTE v114[128]; // [rsp+148h] [rbp+40h] BYREF
  unsigned __int8 v115[512]; // [rsp+1C8h] [rbp+C0h] BYREF
  unsigned __int8 v116[272]; // [rsp+3C8h] [rbp+2C0h] BYREF

  v12 = (void **)a8;
  v14 = a12;
  v15 = (a4 >> 8) & 1;
  v100 = a2;
  v103 = a11;
  v94 = a4;
  v107 = a7;
  Block = (void **)a8;
  v96 = a10;
  v91[0] = a12;
  if ( !g_dwInitialized )
    return 2148321280LL;
  if ( !a7 )
    return 2147942487LL;
  v16 = a9;
  if ( a9 )
  {
    if ( !a10 )
      return 2147942487LL;
  }
  v17 = a4 & 2;
  if ( (a4 & 2) != 0 && (a4 & 1) == 0 )
    return 2147942487LL;
  v18 = a6;
  if ( a6 >= 6 )
    return 2147942487LL;
  CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)&g_LockMasterResource);
  HandleObject = GetHandleObject(v100);
  if ( !HandleObject )
  {
    LODWORD(v90) = -2147024890;
    goto LABEL_37;
  }
  if ( (*((_BYTE *)HandleObject + 12) & 1) == 0 )
  {
    LODWORD(v90) = -2147024891;
    goto LABEL_37;
  }
  v20 = (CMDBaseObject *)*((_QWORD *)HandleObject + 3);
  v92 = v20;
  if ( !v20 )
    goto LABEL_15;
  if ( !a3 )
    goto LABEL_90;
  v21 = 0;
  if ( a12 )
  {
    if ( *(_WORD *)a3 == 47 || *(_WORD *)a3 == 92 )
      a3 += 2;
  }
  else if ( *a3 == 47 || *a3 == 92 )
  {
    ++a3;
  }
  while ( 1 )
  {
    LODWORD(v90) = -2147024893;
    if ( !v20 )
    {
      if ( v21 )
      {
        v20 = v21;
        v92 = v21;
        v33 = -2147024893;
        goto LABEL_35;
      }
LABEL_15:
      LODWORD(v90) = -2147467259;
      goto LABEL_37;
    }
    if ( !v14 )
    {
      v24 = *a3;
      if ( *a3 )
      {
        v23 = (LPSTR)a3;
        if ( v24 != 92 )
        {
          do
          {
            if ( v24 == 47 )
              break;
            if ( !v24 )
              break;
            v23 = CharNextExA(0, v23, 0);
            v24 = *v23;
          }
          while ( *v23 != 92 );
        }
        goto LABEL_25;
      }
LABEL_132:
      v92 = v20;
      v12 = Block;
      v18 = a6;
      v16 = a9;
LABEL_90:
      if ( v12 )
        *(_DWORD *)v12 = *((_DWORD *)v20 + 52);
      v52 = 0;
      v71 = 0;
      goto LABEL_93;
    }
    if ( !*(_WORD *)a3 )
      goto LABEL_132;
    v22 = *(_WORD *)a3;
    v23 = (LPSTR)a3;
    for ( i = a3; v22 != 92; v23 += 2 )
    {
      if ( v22 == 47 )
        break;
      if ( !v22 )
        break;
      v22 = *((_WORD *)v23 + 1);
    }
LABEL_25:
    BUFFER::BUFFER((BUFFER *)v110, v116, 0x104u);
    v112 = v92;
    j = 0;
    v25 = (_DWORD)v23 - (_DWORD)a3;
    if ( (_DWORD)v23 == (_DWORD)a3 )
    {
      BUFFER::~BUFFER((BUFFER *)v110);
      goto LABEL_37;
    }
    v26 = (const WCHAR *)a3;
    memset_0(v115, 0, sizeof(v115));
    BUFFER::BUFFER((BUFFER *)v113, v115, 0x200u);
    if ( !v14 )
    {
      if ( v25 > 0 && !BUFFER::Resize((BUFFER *)v113, 2 * v25 + 50) )
        goto LABEL_34;
      while ( 1 )
      {
        v75 = BUFFER::QuerySize((BUFFER *)v113) >> 1;
        Ptr = (WCHAR *)BUFFER::QueryPtr((BUFFER *)v113);
        v77 = MultiByteToWideChar(0, 1u, a3, v25, Ptr, v75);
        if ( v77 )
          break;
        if ( GetLastError() == 122 )
        {
          Size = BUFFER::QuerySize((BUFFER *)v113);
          if ( BUFFER::Resize((BUFFER *)v113, Size + 50) )
            continue;
        }
        goto LABEL_34;
      }
      v26 = (const WCHAR *)BUFFER::QueryPtr((BUFFER *)v113);
      v25 = 2 * v77;
    }
    if ( v25 > 0 )
      break;
    v27 = BUFFER::QuerySize((BUFFER *)v110);
    for ( j = v27; ; v27 = j )
    {
LABEL_30:
      cchDest = v27 >> 1;
      lpDestStr = (WCHAR *)BUFFER::QueryPtr((BUFFER *)v110);
      v30 = v25;
      if ( v25 >= 0 )
        v30 = v25 / 2;
      v31 = LCMapStringW(0x800u, 0x200u, v26, v30, lpDestStr, cchDest);
      v32 = v31;
      if ( v31 )
        break;
      if ( GetLastError() != 122 || !(unsigned int)CMDKeyBuffer::Resize((CMDKeyBuffer *)v110, j + 50) )
        goto LABEL_34;
    }
    if ( !*((_WORD *)BUFFER::QueryPtr((BUFFER *)v110) + v31 - 1) )
      --v32;
    v35 = 2 * v32;
    if ( !BUFFER::Resize((BUFFER *)v110, v35) )
      goto LABEL_34;
    j = v35;
    BUFFER::~BUFFER((BUFFER *)v113);
    Src = 0;
    CLKRHashTable::FindKey(g_phtChildren, v110, &Src);
    v36 = (CMDBaseObject *)Src;
    BUFFER::~BUFFER((BUFFER *)v110);
    v21 = v92;
    if ( v36 )
    {
      a3 = v23;
      if ( v91[0] )
      {
        if ( *(_WORD *)v23 == 47 || *(_WORD *)v23 == 92 )
          a3 = v23 + 2;
        goto LABEL_46;
      }
      if ( *v23 == 47 || *v23 == 92 )
      {
        v20 = v36;
        v92 = v36;
        v14 = v91[0];
        a3 = v23 + 1;
      }
      else
      {
        v20 = v36;
        v92 = v36;
        v14 = v91[0];
      }
    }
    else
    {
LABEL_46:
      v20 = v36;
      v92 = v36;
      v14 = v91[0];
    }
  }
  if ( BUFFER::Resize((BUFFER *)v110, v25) )
  {
    v27 = v25;
    j = v25;
    goto LABEL_30;
  }
LABEL_34:
  v92 = 0;
  BUFFER::~BUFFER((BUFFER *)v113);
  v33 = -2147024882;
  BUFFER::~BUFFER((BUFFER *)v110);
  v20 = 0;
LABEL_35:
  if ( v33 != -2147024893 || !v20 || !v17 )
  {
    LODWORD(v90) = v33;
    goto LABEL_37;
  }
  if ( Block )
  {
    v79 = *((_DWORD *)v20 + 52) + 1;
    if ( !*((_QWORD *)v20 + 27) )
      v79 = *((_DWORD *)v20 + 52);
    *(_DWORD *)Block = v79;
  }
  v16 = a9;
  v71 = 1;
  v18 = a6;
  v52 = 0;
  v92 = v20;
LABEL_93:
  v98 = v71;
  IsSchemaObject = CMDBaseObject::IsSchemaObject(v20);
  LODWORD(v90) = IsSchemaObject;
  if ( IsSchemaObject < 0 )
    goto LABEL_37;
  MainDataBuffer = GetMainDataBuffer(IsSchemaObject == 0);
  Block = MainDataBuffer;
  if ( !MainDataBuffer )
  {
    LODWORD(v90) = -2147024882;
    goto LABEL_37;
  }
  v51 = v94;
  LODWORD(v95) = v94 & 8;
  LODWORD(v90) = 0;
  v93 = 0;
  CMDBaseObject::CopyDataObjectsToBufferByType(v92, a5, v18, MainDataBuffer, &v93, v71, v15);
  v53 = v93;
  v101 = v93;
  v102 = v51 & 1;
  v105 = v93;
  if ( (v51 & 1) != 0 )
  {
    v80 = (CMDBaseObject *)*((_QWORD *)v92 + 23);
    if ( v80 )
    {
      v81 = Block;
      do
      {
        CMDBaseObject::CopyDataObjectsToBufferByType(v80, a5, v18, v81, &v93, 1, v15);
        v80 = (CMDBaseObject *)*((_QWORD *)v80 + 23);
      }
      while ( v80 );
      v53 = v93;
      v101 = v93;
    }
    v52 = 0;
  }
  i = (const CHAR *)&v96[v16];
  if ( (_DWORD)v95 )
    v37 = &v96[40 * v53];
  else
    v37 = &v96[28 * v53];
  v38 = (unsigned __int64)v37;
  while ( 2 )
  {
    if ( v52 < v53 )
    {
      v39 = Block;
      v40 = *Block;
      if ( v52 == *((_DWORD *)*Block + 24) + 1 && (v41 = (void **)*((_QWORD *)v40 + 13)) != 0 )
      {
        if ( *v41 == v40 + 20 )
          goto LABEL_147;
        v40[24] = v52;
        v42 = *v41;
        *((_QWORD *)v40 + 13) = *v41;
        v43 = (volatile signed __int32 *)*(v42 - 2);
      }
      else
      {
        v64 = (_QWORD *)*((_QWORD *)v40 + 10);
        v65 = v40 + 20;
        v40[24] = v52;
        v66 = v52;
        if ( v52 )
        {
          while ( v64 != v65 )
          {
            v64 = (_QWORD *)*v64;
            if ( !--v66 )
              goto LABEL_78;
          }
LABEL_147:
          *((_QWORD *)v40 + 13) = 0;
          v40[24] = 0;
LABEL_148:
          LODWORD(v90) = -2147467259;
          v68 = v39;
LABEL_88:
          FreeMainDataBuffer(v68);
          v69 = v103;
          v70 = v38 - (_DWORD)v96;
LABEL_89:
          *v69 = v70 + 3;
          goto LABEL_37;
        }
LABEL_78:
        if ( v64 == v65 )
          goto LABEL_147;
        *((_QWORD *)v40 + 13) = v64;
        v43 = (volatile signed __int32 *)*(v64 - 2);
      }
      if ( !v43 )
        goto LABEL_148;
      v44 = (v51 & 0x200) == 0;
      v45 = (*(__int64 (__fastcall **)(volatile signed __int32 *, _QWORD, bool))(*(_QWORD *)v43 + 32LL))(
              v43,
              (unsigned int)v91[0],
              (v51 & 0x200) == 0);
      v46 = *(_QWORD *)v43;
      v47 = v45;
      v93 = v45;
      Src = (void *)(*(__int64 (__fastcall **)(volatile signed __int32 *, _QWORD, bool))(v46 + 24))(
                      v43,
                      (unsigned int)v91[0],
                      (v51 & 0x200) == 0);
      v48 = Src;
      v104 = 0;
      BUFFER::BUFFER((BUFFER *)v113);
      STRAU::STRAU((STRAU *)v114);
      if ( !v48 )
      {
        LODWORD(v90) = -2147024882;
        STRAU::~STRAU((STRAU *)v114);
        BUFFER::~BUFFER((BUFFER *)v113);
        v68 = Block;
        goto LABEL_88;
      }
      v49 = v94;
      if ( ((_BYTE)v43[6] & (unsigned __int8)v94 & 8) == 0 )
      {
        if ( ((_BYTE)v43[6] & (unsigned __int8)v94 & 0x40) == 0 )
          goto LABEL_58;
        v54 = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v43 + 8LL))(v43);
        if ( !v98 )
        {
          v55 = *((_DWORD *)v43 + 2);
          v56 = v92;
          v57 = v54;
          v109 = v92;
          v108 = v55;
          v90 = 0;
          if ( (unsigned int)CLKRHashTable::FindKey(g_phtData, &v108, &v90) )
            goto LABEL_69;
          if ( v57 )
          {
            if ( !v90 || v57 != (*(unsigned int (**)(void))(*(_QWORD *)v90 + 8LL))() )
            {
LABEL_69:
              if ( v102 )
              {
                v58 = (CMDBaseObject *)*((_QWORD *)v56 + 23);
                if ( v58 )
                {
                  v59 = v57;
                  v60 = v55;
                  goto LABEL_81;
                }
              }
              goto LABEL_84;
            }
          }
          else if ( !v90 )
          {
            goto LABEL_69;
          }
          v104 = v56;
          goto LABEL_84;
        }
        v60 = *((_DWORD *)v43 + 2);
        v59 = v54;
        v58 = v92;
LABEL_81:
        CMDBaseObject::GetInheritableDataObject(v58, v60, v59, &v104);
LABEL_84:
        inserted = InsertPathIntoData(
                     (struct BUFFER *)v113,
                     (struct STRAU *)v114,
                     (unsigned __int8 **)&Src,
                     &v93,
                     (struct CMDBaseData *)v43,
                     v100,
                     v104,
                     v91[0]);
        v49 = v94;
        v47 = v93;
        v48 = Src;
        LODWORD(v90) = inserted;
LABEL_58:
        v38 = (unsigned __int64)&v37[v47 + 3] & 0xFFFFFFFFFFFFFFFCuLL;
      }
      if ( (int)v90 >= 0 )
      {
        if ( (unsigned __int64)i < v38 )
        {
          LODWORD(v90) = -2147024774;
        }
        else if ( (_DWORD)v95 )
        {
          v61 = &v96[40 * v52];
          if ( (v49 & (_BYTE)v43[6] & 8) != 0 )
          {
            *((_QWORD *)v61 + 3) = (*(__int64 (__fastcall **)(volatile signed __int32 *, _QWORD, BOOL))(*(_QWORD *)v43 + 24LL))(
                                     v43,
                                     (unsigned int)v91[0],
                                     v44);
            _InterlockedIncrement(v43 + 8);
            v63 = *((_DWORD *)v43 + 9);
          }
          else
          {
            v62 = Src;
            *((_QWORD *)v61 + 3) = v37 - v96;
            memcpy_0(v37, v62, v47);
            v63 = 0;
          }
          *((_DWORD *)v61 + 8) = v63;
          *(_DWORD *)v61 = *((_DWORD *)v43 + 2);
          *((_DWORD *)v61 + 1) = *((_DWORD *)v43 + 6);
          *((_DWORD *)v61 + 2) = *((_DWORD *)v43 + 7);
          *((_DWORD *)v61 + 3) = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v43 + 8LL))(v43);
          *((_DWORD *)v61 + 4) = v47;
        }
        else
        {
          v50 = &v96[28 * v52];
          *((_DWORD *)v50 + 5) = (_DWORD)v37 - (_DWORD)v96;
          memcpy_0(v37, v48, v47);
          *((_DWORD *)v50 + 6) = 0;
          *(_DWORD *)v50 = *((_DWORD *)v43 + 2);
          *((_DWORD *)v50 + 1) = *((_DWORD *)v43 + 6);
          *((_DWORD *)v50 + 2) = *((_DWORD *)v43 + 7);
          *((_DWORD *)v50 + 3) = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v43 + 8LL))(v43);
          *((_DWORD *)v50 + 4) = v47;
        }
      }
      STRAU::~STRAU((STRAU *)v114);
      BUFFER::~BUFFER((BUFFER *)v113);
      v51 = v94;
      ++v52;
      v53 = v101;
      v37 = (unsigned __int8 *)v38;
      continue;
    }
    break;
  }
  FreeMainDataBuffer(Block);
  v74 = v90;
  if ( (int)v90 >= 0 && (v82 = v107, (*v107 = v53) != 0) && (v51 & 0x20) != 0 && v102 )
  {
    if ( v98 )
    {
      v83 = v96;
      v84 = 0;
      if ( (_DWORD)v95 )
      {
        do
        {
          v86 = v84++;
          *(_DWORD *)&v83[40 * v86 + 4] |= 0x20u;
        }
        while ( v84 < v53 );
      }
      else
      {
        LODWORD(v90) = v74;
        do
        {
          v85 = v84++;
          *(_DWORD *)&v83[28 * v85 + 4] |= 0x20u;
        }
        while ( v84 < v53 );
      }
      *v103 = v38 - (_DWORD)v83;
      goto LABEL_37;
    }
    v87 = v105;
    LODWORD(v90) = v74;
    if ( v105 < v53 )
    {
      v88 = v96;
      v89 = v95;
      do
      {
        if ( v89 )
          *(_DWORD *)&v88[40 * v87 + 4] |= 0x20u;
        else
          *(_DWORD *)&v88[28 * v87 + 4] |= 0x20u;
        ++v87;
      }
      while ( v87 < *v82 );
      *v103 = v38 - (_DWORD)v88;
      goto LABEL_37;
    }
  }
  else
  {
    LODWORD(v90) = v74;
  }
  v69 = v103;
  v70 = v38 - (_DWORD)v96;
  *v103 = v70;
  if ( v74 < 0 )
    goto LABEL_89;
LABEL_37:
  CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)&g_LockMasterResource);
  return (unsigned int)v90;
}

```

## disassembly

```asm
0x180001340  mov     r11, rsp
0x180001343  push    rbp
0x180001344  push    rbx
0x180001345  push    rsi
0x180001346  push    rdi
0x180001347  push    r12
0x180001349  lea     rbp, [r11-418h]
0x180001350  sub     rsp, 4F0h
0x180001357  mov     rax, cs:__security_cookie
0x18000135e  xor     rax, rsp
0x180001361  mov     [rbp+410h+var_40], rax
0x180001368  mov     rax, [rbp+410h+arg_50]
0x18000136f  mov     r12d, r9d
0x180001372  mov     rdi, [rbp+410h+arg_38]
0x180001379  mov     rsi, r8
0x18000137c  mov     rcx, [rbp+410h+arg_48]
0x180001383  mov     ebx, [rbp+410h+arg_58]
0x180001389  shr     r12d, 8
0x18000138d  and     r12d, 1
0x180001391  mov     [rbp+410h+var_488], edx
0x180001394  mov     rdx, [rbp+410h+arg_30]
0x18000139b  mov     [rbp+410h+var_478], rax
0x18000139f  mov     eax, cs:?g_dwInitialized@@3KC; ulong volatile g_dwInitialized
0x1800013a5  mov     [rsp+510h+var_4B4], r9d
0x1800013aa  mov     [rbp+410h+var_458], rdx
0x1800013ae  mov     [rsp+510h+Block], rdi
0x1800013b3  mov     [rsp+510h+var_4A8], rcx
0x1800013b8  mov     [rsp+510h+var_4C8], ebx
0x1800013bc  test    eax, eax
0x1800013be  jz      loc_180001B84
0x1800013c4  mov     [r11+8], r13
0x1800013c8  mov     [r11-30h], r14
0x1800013cc  mov     [r11-38h], r15
0x1800013d0  test    rdx, rdx
0x1800013d3  jz      loc_180001B97
0x1800013d9  mov     r14d, [rbp+410h+arg_40]
0x1800013e0  test    r14d, r14d
0x1800013e3  jnz     loc_180001B8E
0x1800013e9  mov     r13d, r9d
0x1800013ec  and     r13d, 2
0x1800013f0  jnz     loc_180001BA1
0x1800013f6  mov     r15d, [rbp+410h+arg_28]
0x1800013fd  cmp     r15d, 6
0x180001401  jnb     loc_180001B97
0x180001407  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x18000140e  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180001414  mov     ecx, [rbp+410h+var_488]; unsigned int
0x180001417  call    ?GetHandleObject@@YAPEAVCMDHandle@@K@Z; GetHandleObject(ulong)
0x18000141c  test    rax, rax
0x18000141f  jz      loc_180001BAC
0x180001425  test    byte ptr [rax+0Ch], 1
0x180001429  jz      loc_180001649
0x18000142f  mov     rdx, [rax+18h]
0x180001433  mov     [rsp+510h+var_4C0], rdx
0x180001438  test    rdx, rdx
0x18000143b  jz      short loc_180001482
0x18000143d  test    rsi, rsi
0x180001440  jz      loc_180001A8E
0x180001446  xor     r15d, r15d
0x180001449  mov     ecx, r15d
0x18000144c  test    ebx, ebx
0x18000144e  jz      loc_180001BC2
0x180001454  movzx   eax, word ptr [rsi]
0x180001457  cmp     ax, 2Fh ; '/'
0x18000145b  jz      loc_180001BB9
0x180001461  cmp     ax, 5Ch ; '\'
0x180001465  jz      loc_180001BB9
0x18000146b  mov     eax, 80070003h
0x180001470  mov     dword ptr [rsp+510h+var_4D0], eax
0x180001474  test    rdx, rdx
0x180001477  jnz     short loc_18000148F
0x180001479  test    rcx, rcx
0x18000147c  jnz     loc_180001D29
0x180001482  mov     dword ptr [rsp+510h+var_4D0], 80004005h
0x18000148a  jmp     loc_1800015F9
0x18000148f  test    ebx, ebx
0x180001491  jz      short loc_1800014CB
0x180001493  cmp     word ptr [rsi], 0
0x180001497  jz      loc_180001D22
0x18000149d  movzx   eax, word ptr [rsi]
0x1800014a0  mov     rdi, rsi
0x1800014a3  mov     [rbp+410h+var_460], rsi
0x1800014a7  cmp     ax, 5Ch ; '\'
0x1800014ab  jz      short loc_1800014E1
0x1800014ad  nop     dword ptr [rax]
0x1800014b0  cmp     ax, 2Fh ; '/'
0x1800014b4  jz      short loc_1800014E1
0x1800014b6  test    ax, ax
0x1800014b9  jz      short loc_1800014E1
0x1800014bb  movzx   eax, word ptr [rdi+2]
0x1800014bf  add     rdi, 2
0x1800014c3  cmp     ax, 5Ch ; '\'
0x1800014c7  jnz     short loc_1800014B0
0x1800014c9  jmp     short loc_1800014E1
0x1800014cb  movzx   eax, byte ptr [rsi]
0x1800014ce  test    al, al
0x1800014d0  jz      loc_180001D22
0x1800014d6  mov     rdi, rsi
0x1800014d9  cmp     al, 5Ch ; '\'
0x1800014db  jnz     loc_180001BD9
0x1800014e1  mov     r8d, 104h
0x1800014e7  lea     rdx, [rbp+410h+var_150]
0x1800014ee  lea     rcx, [rbp+410h+var_440]
0x1800014f2  mov     r14d, edi
0x1800014f5  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x1800014fb  mov     rax, [rsp+510h+var_4C0]
0x180001500  mov     [rbp+410h+var_408], rax
0x180001504  mov     [rbp+410h+var_410], r15d
0x180001508  sub     r14d, esi
0x18000150b  jz      loc_180001D13
0x180001511  xor     edx, edx; Val
0x180001513  lea     rcx, [rbp+410h+var_350]; void *
0x18000151a  mov     r8d, 200h; Size
0x180001520  mov     r15, rsi
0x180001523  call    memset_0
0x180001528  mov     r8d, 200h
0x18000152e  lea     rdx, [rbp+410h+var_350]
0x180001535  lea     rcx, [rbp+410h+var_400]
0x180001539  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x18000153f  test    ebx, ebx
0x180001541  jz      loc_180001C06
0x180001547  lea     rcx, [rbp+410h+var_440]
0x18000154b  test    r14d, r14d
0x18000154e  jle     loc_180001CA4
0x180001554  mov     edx, r14d
0x180001557  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18000155d  test    al, al
0x18000155f  jz      short loc_1800015BB
0x180001561  mov     ebx, r14d
0x180001564  mov     [rbp+410h+var_410], ebx
0x180001567  lea     rcx, [rbp+410h+var_440]
0x18000156b  shr     ebx, 1
0x18000156d  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180001573  mov     rcx, rax
0x180001576  mov     eax, r14d
0x180001579  test    r14d, r14d
0x18000157c  jns     loc_18000163F
0x180001582  mov     [rsp+510h+cchDest], ebx; cchDest
0x180001586  mov     r9d, eax; cchSrc
0x180001589  mov     [rsp+510h+lpDestStr], rcx; lpDestStr
0x18000158e  mov     r8, r15; lpSrcStr
0x180001591  mov     ecx, 800h; Locale
0x180001596  mov     edx, 200h; dwMapFlags
0x18000159b  call    cs:__imp_LCMapStringW
0x1800015a1  movsxd  rbx, eax
0x1800015a4  test    eax, eax
0x1800015a6  jnz     loc_180001653
0x1800015ac  call    cs:__imp_GetLastError
0x1800015b2  cmp     eax, 7Ah ; 'z'
0x1800015b5  jz      loc_180001CB4
0x1800015bb  xor     ecx, ecx
0x1800015bd  mov     [rsp+510h+var_4C0], rcx
0x1800015c2  lea     rcx, [rbp+410h+var_400]
0x1800015c6  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800015cc  lea     rcx, [rbp+410h+var_440]
0x1800015d0  mov     ebx, 8007000Eh
0x1800015d5  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800015db  mov     rdx, [rsp+510h+var_4C0]
0x1800015e0  mov     eax, 80070003h
0x1800015e5  test    ebx, ebx
0x1800015e7  jns     loc_180001D38
0x1800015ed  cmp     ebx, eax
0x1800015ef  jz      loc_180001D66
0x1800015f5  mov     dword ptr [rsp+510h+var_4D0], ebx
0x1800015f9  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x180001600  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180001606  mov     eax, dword ptr [rsp+510h+var_4D0]
0x18000160a  mov     r14, [rsp+4E8h]
0x180001612  mov     r13, [rsp+510h+arg_0]
0x18000161a  mov     r15, [rsp+510h+var_30]
0x180001622  mov     rcx, [rbp+410h+var_40]
0x180001629  xor     rcx, rsp; StackCookie
0x18000162c  call    __security_check_cookie
0x180001631  add     rsp, 4F0h
0x180001638  pop     r12
0x18000163a  pop     rdi
0x18000163b  pop     rsi
0x18000163c  pop     rbx
0x18000163d  pop     rbp
0x18000163e  retn
0x18000163f  cdq
0x180001640  sub     eax, edx
0x180001642  sar     eax, 1
0x180001644  jmp     loc_180001582
0x180001649  mov     dword ptr [rsp+510h+var_4D0], 80070005h
0x180001651  jmp     short loc_1800015F9
0x180001653  lea     rcx, [rbp+410h+var_440]
0x180001657  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000165d  cmp     word ptr [rax+rbx*2-2], 0
0x180001663  jz      loc_180001CD3
0x180001669  add     ebx, ebx
0x18000166b  lea     rcx, [rbp+410h+var_440]
0x18000166f  mov     edx, ebx
0x180001671  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180001677  test    al, al
0x180001679  jz      loc_1800015BB
0x18000167f  lea     rcx, [rbp+410h+var_400]
0x180001683  mov     [rbp+410h+var_410], ebx
0x180001686  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000168c  mov     rcx, cs:?g_phtChildren@@3PEAVCChildNodeHashTable@@EA; CChildNodeHashTable * g_phtChildren
0x180001693  lea     r8, [rbp+410h+Src]
0x180001697  xor     r15d, r15d
0x18000169a  lea     rdx, [rbp+410h+var_440]
0x18000169e  mov     [rbp+410h+Src], r15
0x1800016a2  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x1800016a8  mov     rbx, [rbp+410h+Src]
0x1800016ac  lea     rcx, [rbp+410h+var_440]
0x1800016b0  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800016b6  mov     rcx, [rsp+510h+var_4C0]
0x1800016bb  test    rbx, rbx
0x1800016be  jz      short loc_1800016E5
0x1800016c0  mov     rsi, rdi
0x1800016c3  cmp     [rsp+510h+var_4C8], r15d
0x1800016c8  jz      loc_180001CE3
0x1800016ce  movzx   eax, word ptr [rdi]
0x1800016d1  cmp     ax, 2Fh ; '/'
0x1800016d5  jz      loc_180001CDA
0x1800016db  cmp     ax, 5Ch ; '\'
0x1800016df  jz      loc_180001CDA
0x1800016e5  mov     rdx, rbx
0x1800016e8  mov     [rsp+510h+var_4C0], rbx
0x1800016ed  mov     ebx, [rsp+510h+var_4C8]
0x1800016f1  jmp     loc_18000146B
0x1800016f6  lea     rax, [rax+rax*4]
0x1800016fa  lea     r12, [r8+rax*8]
0x1800016fe  mov     r14, r12
0x180001701  cmp     edi, esi
0x180001703  jnb     loc_180001B4E
0x180001709  mov     r8, [rsp+510h+Block]
0x18000170e  mov     rax, [r8]
0x180001711  mov     ecx, [rax+60h]
0x180001714  inc     ecx
0x180001716  cmp     edi, ecx
0x180001718  jnz     loc_18000197A
0x18000171e  mov     rdx, [rax+68h]
0x180001722  test    rdx, rdx
0x180001725  jz      loc_18000197A
0x18000172b  lea     rcx, [rax+50h]
0x18000172f  cmp     [rdx], rcx
0x180001732  jz      loc_180001E1B
0x180001738  mov     [rax+60h], edi
0x18000173b  mov     rcx, [rdx]
0x18000173e  mov     [rax+68h], rcx
0x180001742  mov     rsi, [rcx-10h]
0x180001746  test    rsi, rsi
0x180001749  jz      loc_180001E24
0x18000174f  mov     rax, [rsi]
0x180001752  mov     ebx, r13d
0x180001755  mov     edx, [rsp+510h+var_4C8]
0x180001759  mov     rcx, rsi
0x18000175c  shr     ebx, 9
0x18000175f  not     ebx
0x180001761  mov     rax, [rax+20h]
0x180001765  and     ebx, 1
0x180001768  mov     r8d, ebx
0x18000176b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001770  mov     rcx, [rsi]
0x180001773  mov     r15d, eax
0x180001776  mov     edx, [rsp+510h+var_4C8]
0x18000177a  mov     r8d, ebx
0x18000177d  mov     [rsp+510h+var_4B8], eax
0x180001781  mov     rax, [rcx+18h]
0x180001785  mov     rcx, rsi
0x180001788  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000178d  lea     rcx, [rbp+410h+var_400]
0x180001791  mov     [rbp+410h+Src], rax
0x180001795  mov     r13, rax
0x180001798  mov     [rbp+410h+var_470], 0
0x1800017a0  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x1800017a6  lea     rcx, [rbp+410h+var_3D0]
0x1800017aa  call    cs:__imp_??0STRAU@@QEAA@XZ; STRAU::STRAU(void)
0x1800017b0  test    r13, r13
0x1800017b3  jz      loc_180001A51
0x1800017b9  mov     ecx, [rsp+510h+var_4B4]
0x1800017bd  mov     eax, ecx
0x1800017bf  and     eax, [rsi+18h]
0x1800017c2  test    al, 8
0x1800017c4  jnz     short loc_1800017DC
0x1800017c6  test    al, 40h
0x1800017c8  jnz     loc_180001870
0x1800017ce  mov     r14d, r15d
0x1800017d1  add     r14, 3
0x1800017d5  add     r14, r12
0x1800017d8  and     r14, 0FFFFFFFFFFFFFFFCh
0x1800017dc  cmp     dword ptr [rsp+510h+var_4D0], 0
0x1800017e1  jl      short loc_18000184A
0x1800017e3  cmp     [rbp+410h+var_460], r14
0x1800017e7  jb      loc_180001A1E
0x1800017ed  cmp     dword ptr [rsp+510h+var_4B0], 0
0x1800017f2  mov     eax, edi
0x1800017f4  jnz     loc_18000190E
0x1800017fa  mov     rcx, [rsp+510h+var_4A8]
0x1800017ff  mov     rdx, r13; Src
0x180001802  imul    rbx, rax, 1Ch
0x180001806  mov     eax, r12d
0x180001809  mov     r8d, r15d; Size
0x18000180c  add     rbx, rcx
0x18000180f  sub     eax, ecx
0x180001811  mov     rcx, r12; void *
0x180001814  mov     [rbx+14h], eax
  ... truncated ...
```
