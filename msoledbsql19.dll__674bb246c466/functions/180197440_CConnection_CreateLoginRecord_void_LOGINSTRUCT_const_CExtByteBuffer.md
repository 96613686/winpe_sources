# CConnection::CreateLoginRecord(void *,_LOGINSTRUCT const *,CExtByteBuffer *)

- ea: `0x180197440`
- end: `0x180198701`
- name: `?CreateLoginRecord@CConnection@@AEAAJPEAXPEBU_LOGINSTRUCT@@PEAVCExtByteBuffer@@@Z`
- size: `4801`
- prototype: `__int64 __fastcall(CConnection *__hidden this, void *, const struct _LOGINSTRUCT *, struct CExtByteBuffer *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180199740`

## callees

- `0x180003030`
- `0x1800030c0`
- `0x180003d80`
- `0x18001aeb0`
- `0x180134658`
- `0x180196730`
- `0x180196800`
- `0x180197440`
- `0x18019a370`
- `0x1801a0e70`
- `0x1801a1140`
- `0x1801a65e1`
- `0x1801a65f0`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1801977de`
- `KERNEL32!GetLastError` at `0x180197866`
- `KERNEL32!GetLastError` at `0x180197eec`
- `KERNEL32!GetLastError` at `0x1801982a8`
- `KERNEL32!GetLastError` at `0x180198330`
- `KERNEL32!GetLastError` at `0x1801977de`
- `KERNEL32!GetLastError` at `0x180197866`
- `KERNEL32!GetLastError` at `0x180197eec`
- `KERNEL32!GetLastError` at `0x1801982a8`
- `KERNEL32!GetLastError` at `0x180198330`
- `KERNEL32!GetCurrentProcessId` at `0x18019752e`
- `KERNEL32!GetCurrentProcessId` at `0x18019752e`
- `KERNEL32!GetTimeZoneInformation` at `0x1801975e2`
- `KERNEL32!GetTimeZoneInformation` at `0x1801975e2`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180197c90`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180197e97`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180198253`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180197c90`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180197e97`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180198253`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180197c9c`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180197ea3`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18019825f`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180197c9c`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180197ea3`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18019825f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CConnection::CreateLoginRecord(
        CConnection *this,
        void *a2,
        const struct _LOGINSTRUCT *a3,
        struct CExtByteBuffer *a4)
{
  struct CExtByteBuffer *v4; // rsi
  CConnection *v6; // r15
  SessionRecoveryFeatureExtension *v7; // r14
  __int64 v8; // rdi
  char v9; // dl
  char v10; // cl
  char v11; // r8
  char v12; // r8
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int16 v15; // ax
  _WORD *v16; // rdx
  int v17; // ebx
  __int64 v18; // r12
  __int64 v19; // rcx
  __int64 v20; // rdx
  _WORD *v21; // rdi
  _WORD *v22; // rax
  _WORD *v23; // rdx
  __int64 v24; // rcx
  SessionRecoveryFeatureExtension *v25; // rdi
  int (*v26)(void *, unsigned int, unsigned int); // r9
  _OWORD *v27; // rax
  _OWORD *v28; // rcx
  __int64 v29; // rdx
  DWORD v30; // eax
  void *v31; // r14
  __int64 v32; // rdi
  DWORD v33; // eax
  __int64 v34; // rcx
  SessionRecoveryFeatureExtension *v35; // rdx
  _WORD *v36; // rdx
  __int64 v37; // rcx
  _BYTE *v38; // rcx
  __int64 j; // rdx
  _WORD *v40; // rdx
  __int64 v41; // rcx
  __int64 v42; // rdi
  _WORD *v43; // rdx
  char v44; // al
  unsigned __int64 v45; // rax
  __int64 v46; // rcx
  __int64 v47; // rcx
  __int64 v48; // rdi
  _WORD *v49; // rdx
  __int64 v50; // rcx
  __int64 v51; // rdi
  _WORD *v52; // rdx
  __int64 v53; // rcx
  __int64 v54; // rdi
  _WORD *v55; // rdx
  __int64 v56; // rcx
  _WORD *v57; // rdi
  _DWORD *v58; // rcx
  _WORD *v59; // rdx
  __int64 v60; // rcx
  __int64 v61; // rdi
  char v62; // al
  __int64 v63; // rax
  int v64; // edx
  int v65; // ecx
  _OWORD *v66; // rax
  _OWORD *v67; // rcx
  __int64 v68; // r8
  DWORD LastError; // eax
  _BYTE *v70; // rcx
  __int64 i; // rdx
  __int64 v72; // rax
  const void *v73; // rdx
  unsigned int v74; // eax
  int v75; // eax
  __int64 v76; // r8
  size_t v77; // rax
  void *v78; // rcx
  const void *v79; // rdx
  unsigned int v80; // r9d
  DWORD v81; // eax
  void *v82; // r14
  __int64 v83; // rdi
  DWORD v84; // eax
  void *v85; // r12
  __int64 v86; // rcx
  char *v87; // rdx
  int v88; // eax
  void *v89; // r12
  __int64 v90; // rax
  __int64 v91; // rax
  SessionRecoveryFeatureExtension *v92; // rax
  int v93; // eax
  __int64 v94; // rdx
  int v95; // eax
  __int64 v97; // [rsp+20h] [rbp-298h]
  int v98; // [rsp+30h] [rbp-288h]
  int v99; // [rsp+38h] [rbp-280h]
  SessionRecoveryFeatureExtension *v100; // [rsp+40h] [rbp-278h] BYREF
  void *v101; // [rsp+48h] [rbp-270h]
  size_t Size; // [rsp+50h] [rbp-268h]
  int v103; // [rsp+58h] [rbp-260h]
  void *v104; // [rsp+60h] [rbp-258h]
  unsigned int v105; // [rsp+68h] [rbp-250h]
  __int64 v106; // [rsp+70h] [rbp-248h]
  struct CExtByteBuffer *v107; // [rsp+78h] [rbp-240h] BYREF
  void *v108; // [rsp+80h] [rbp-238h]
  CConnection *v109; // [rsp+88h] [rbp-230h]
  SessionRecoveryFeatureExtension *v110; // [rsp+90h] [rbp-228h]
  unsigned int v111; // [rsp+98h] [rbp-220h] BYREF
  int v112; // [rsp+9Ch] [rbp-21Ch] BYREF
  struct _TIME_ZONE_INFORMATION TimeZoneInformation; // [rsp+A0h] [rbp-218h] BYREF
  _WORD Src[144]; // [rsp+150h] [rbp-168h] BYREF

  v4 = a4;
  v104 = a2;
  v6 = this;
  v109 = this;
  v107 = a4;
  v7 = 0;
  v112 = 0;
  v101 = 0;
  v108 = 0;
  Size = 0;
  v105 = 0;
  memset_0(&TimeZoneInformation, 0, sizeof(TimeZoneInformation));
  if ( !a3 || !v4 || *((_QWORD *)v4 + 2) < 0x5Eu )
  {
    v17 = -2147418113;
    if ( (bidGblFlags & 2) != 0 )
    {
      v20 = 1409033;
      goto LABEL_264;
    }
    return (unsigned int)v17;
  }
  v8 = *((_QWORD *)v4 + 4);
  *((_QWORD *)v4 + 1) = 94;
  *(_OWORD *)v8 = 0;
  *(_OWORD *)(v8 + 16) = 0;
  *(_OWORD *)(v8 + 32) = 0;
  *(_OWORD *)(v8 + 48) = 0;
  *(_OWORD *)(v8 + 64) = 0;
  *(_QWORD *)(v8 + 80) = 0;
  *(_DWORD *)(v8 + 88) = 0;
  *(_WORD *)(v8 + 92) = 0;
  *(_DWORD *)(v8 + 4) = *((unsigned __int16 *)v6 + 653) | (*((unsigned __int16 *)v6 + 652) << 16);
  *(_DWORD *)(v8 + 8) = *((_DWORD *)a3 + 32);
  *(_DWORD *)(v8 + 12) = 117440512;
  *(_DWORD *)(v8 + 16) = GetCurrentProcessId();
  *(_DWORD *)(v8 + 20) = 0;
  v9 = *(_BYTE *)(v8 + 24) & 0xFC;
  *(_BYTE *)(v8 + 24) = v9;
  *(_BYTE *)(v8 + 24) = v9 & 3 | (*((_DWORD *)a3 + 44) != 0 ? 0x10 : 0) | 0xE0;
  v10 = *(_BYTE *)(v8 + 26) & 0xF0;
  *(_BYTE *)(v8 + 26) = v10;
  *(_BYTE *)(v8 + 25) = *(_BYTE *)(v8 + 25) & 0xFA | 1;
  v11 = 0;
  if ( *((_DWORD *)a3 + 57) == 1 )
    v11 = 32;
  v12 = v10 & 0xDF | v11;
  *(_BYTE *)(v8 + 26) = v12;
  v13 = *((_QWORD *)a3 + 12);
  if ( !v13 )
  {
LABEL_260:
    v17 = -2147418113;
    if ( (bidGblFlags & 2) != 0 )
    {
      v20 = 1439753;
      goto LABEL_264;
    }
    return (unsigned int)v17;
  }
  v14 = 0;
  do
  {
    v15 = *(_WORD *)(v13 + 2 * v14++);
    if ( v15 != aOledb[v14 - 1] )
      goto LABEL_260;
  }
  while ( v14 != 6 );
  if ( (*(_BYTE *)(v8 + 27) & 6) != 0 )
    goto LABEL_260;
  *(_BYTE *)(v8 + 26) = v12 | 0x10;
  if ( GetTimeZoneInformation(&TimeZoneInformation) != -1 )
    *(_DWORD *)(v8 + 28) = TimeZoneInformation.Bias;
  *(_DWORD *)(v8 + 32) = *((_DWORD *)a3 + 47);
  v16 = (_WORD *)*((_QWORD *)a3 + 7);
  v17 = 0;
  v18 = -1;
  if ( v16 )
  {
    v19 = -1;
    do
      ++v19;
    while ( v16[v19] );
  }
  else
  {
    LOWORD(v19) = 0;
  }
  *(_WORD *)(v8 + 36) = *((_WORD *)v4 + 4);
  *(_WORD *)(v8 + 38) = v19;
  if ( (_WORD)v19 )
    v17 = CExtByteBuffer::WriteIntoExtBuffer(v4, v16, 2LL * (unsigned __int16)v19);
  if ( v17 < 0 )
  {
    if ( (bidGblFlags & 2) == 0 )
      return (unsigned int)v17;
    v20 = 1451017;
    goto LABEL_264;
  }
  _mm_lfence();
  v21 = (_WORD *)*((_QWORD *)v4 + 4);
  if ( *((_BYTE *)a3 + 132) || *((_QWORD *)a3 + 33) )
  {
    v22 = (_WORD *)*((_QWORD *)a3 + 9);
    if ( !v22 || !*v22 )
    {
LABEL_71:
      v40 = (_WORD *)*((_QWORD *)a3 + 11);
      v17 = 0;
      if ( v40 )
      {
        v41 = -1;
        do
          ++v41;
        while ( v40[v41] );
      }
      else
      {
        LOWORD(v41) = 0;
      }
      v21[24] = *((_WORD *)v4 + 4);
      v21[25] = v41;
      if ( (_WORD)v41 )
      {
        _mm_lfence();
        v17 = CExtByteBuffer::WriteIntoExtBuffer(v4, v40, 2LL * (unsigned __int16)v41);
      }
      if ( v17 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          v20 = 1512457;
          goto LABEL_264;
        }
        return (unsigned int)v17;
      }
      _mm_lfence();
      v42 = *((_QWORD *)v4 + 4);
      v43 = (_WORD *)*((_QWORD *)a3 + 9);
      if ( v43 && *v43 )
      {
        v44 = *(_BYTE *)(v42 + 25) & 0x8F | 0x20;
        *(_BYTE *)(v42 + 25) = v44;
      }
      else
      {
        v43 = (_WORD *)*((_QWORD *)a3 + 10);
        if ( v43 && *v43 )
        {
          v44 = *(_BYTE *)(v42 + 25) & 0x8F | 0x30;
          *(_BYTE *)(v42 + 25) = v44;
        }
        else
        {
          v43 = (_WORD *)*((_QWORD *)a3 + 8);
          *(_BYTE *)(v42 + 25) &= 0x8Fu;
          v44 = *(_BYTE *)(v42 + 25);
          if ( !v43 )
            goto LABEL_96;
        }
      }
      if ( (v44 & 0x70) == 0 )
      {
        v45 = -1;
        do
          ++v45;
        while ( v43[v45] );
        if ( v45 >= 0x80 )
        {
          LOWORD(v46) = 128;
          *(_WORD *)(v42 + 52) = *((_WORD *)v4 + 4);
          *(_WORD *)(v42 + 54) = 128;
        }
        else
        {
          _mm_lfence();
          v46 = -1;
          do
            ++v46;
          while ( v43[v46] );
          *(_WORD *)(v42 + 52) = *((_WORD *)v4 + 4);
          *(_WORD *)(v42 + 54) = v46;
        }
        goto LABEL_103;
      }
LABEL_96:
      v17 = 0;
      if ( v43 )
      {
        v46 = -1;
        do
          ++v46;
        while ( v43[v46] );
      }
      else
      {
        LOWORD(v46) = 0;
      }
      *(_WORD *)(v42 + 52) = *((_WORD *)v4 + 4);
      *(_WORD *)(v42 + 54) = v46;
      if ( !(_WORD)v46 )
      {
LABEL_104:
        if ( v17 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            v20 = 1545225;
            goto LABEL_264;
          }
          return (unsigned int)v17;
        }
        _mm_lfence();
        v47 = *((_QWORD *)v4 + 4);
        *(_WORD *)(v47 + 56) = *((_WORD *)v4 + 4);
        *(_WORD *)(v47 + 58) = 4;
        CExtByteBuffer::WriteIntoExtBuffer(v4, &v112, 4u);
        v48 = *((_QWORD *)v4 + 4);
        v49 = (_WORD *)*((_QWORD *)a3 + 12);
        v17 = 0;
        if ( v49 )
        {
          v50 = -1;
          do
            ++v50;
          while ( v49[v50] );
        }
        else
        {
          LOWORD(v50) = 0;
        }
        *(_WORD *)(v48 + 60) = *((_WORD *)v4 + 4);
        *(_WORD *)(v48 + 62) = v50;
        if ( (_WORD)v50 )
        {
          _mm_lfence();
          v17 = CExtByteBuffer::WriteIntoExtBuffer(v4, v49, 2LL * (unsigned __int16)v50);
        }
        if ( v17 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            v20 = 1557513;
            goto LABEL_264;
          }
          return (unsigned int)v17;
        }
        _mm_lfence();
        v51 = *((_QWORD *)v4 + 4);
        v52 = (_WORD *)*((_QWORD *)a3 + 3);
        v17 = 0;
        if ( v52 )
        {
          v53 = -1;
          do
            ++v53;
          while ( v52[v53] );
        }
        else
        {
          LOWORD(v53) = 0;
        }
        *(_WORD *)(v51 + 64) = *((_WORD *)v4 + 4);
        *(_WORD *)(v51 + 66) = v53;
        if ( (_WORD)v53 )
        {
          _mm_lfence();
          v17 = CExtByteBuffer::WriteIntoExtBuffer(v4, v52, 2LL * (unsigned __int16)v53);
        }
        if ( v17 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            v20 = 1561609;
            goto LABEL_264;
          }
          return (unsigned int)v17;
        }
        _mm_lfence();
        v54 = *((_QWORD *)v4 + 4);
        v55 = (_WORD *)*((_QWORD *)a3 + 2);
        v17 = 0;
        if ( v55 )
        {
          v56 = -1;
          do
            ++v56;
          while ( v55[v56] );
        }
        else
        {
          LOWORD(v56) = 0;
        }
        *(_WORD *)(v54 + 68) = *((_WORD *)v4 + 4);
        *(_WORD *)(v54 + 70) = v56;
        if ( (_WORD)v56 )
        {
          _mm_lfence();
          v17 = CExtByteBuffer::WriteIntoExtBuffer(v4, v55, 2LL * (unsigned __int16)v56);
        }
        if ( v17 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            v20 = 1565705;
            goto LABEL_264;
          }
          return (unsigned int)v17;
        }
        _mm_lfence();
        v57 = (_WORD *)*((_QWORD *)v4 + 4);
        v58 = v57 + 36;
        if ( v57 != (_WORD *)-72LL )
        {
          if ( a3 != (const struct _LOGINSTRUCT *)-192LL )
          {
            *v58 = *((_DWORD *)a3 + 48);
            v57[38] = *((_WORD *)a3 + 98);
            goto LABEL_142;
          }
          *v58 = 0;
          v57[38] = 0;
        }
        *_errno() = 22;
        _invalid_parameter_noinfo();
LABEL_142:
        v59 = (_WORD *)*((_QWORD *)a3 + 13);
        v17 = 0;
        if ( v59 )
        {
          v60 = -1;
          do
            ++v60;
          while ( v59[v60] );
        }
        else
        {
          LOWORD(v60) = 0;
        }
        v57[41] = *((_WORD *)v4 + 4);
        v57[42] = v60;
        if ( (_WORD)v60 )
        {
          _mm_lfence();
          v17 = CExtByteBuffer::WriteIntoExtBuffer(v4, v59, 2LL * (unsigned __int16)v60);
        }
        v103 = v17;
        if ( v17 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            v20 = 1574921;
            goto LABEL_264;
          }
          return (unsigned int)v17;
        }
        _mm_lfence();
        v61 = *((_QWORD *)v4 + 4);
        v106 = v61;
        v62 = *((_BYTE *)a3 + 132);
        if ( v62 == 1 || v62 == 2 && !*((_DWORD *)v6 + 111) )
        {
          v111 = 0;
          *(_BYTE *)(v61 + 25) |= 0x80u;
          if ( *((_QWORD *)a3 + 6) || *((_QWORD *)v6 + 11) || *(_DWORD *)(v61 + 90) )
          {
            v17 = -2147418113;
            if ( (bidGblFlags & 2) != 0 )
            {
              v20 = 1593353;
              goto LABEL_264;
            }
            return (unsigned int)v17;
          }
          v72 = (*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, _QWORD))(*(_QWORD *)g_pMO + 112LL))(
                  g_pMO,
                  *(unsigned int *)(*((_QWORD *)v6 + 165) + 208LL));
          *((_QWORD *)v6 + 11) = v72;
          if ( !v72 )
          {
            if ( (bidGblFlags & 2) != 0 )
              return (unsigned int)bidTraceHR(off_1802626C8[0], 1597449, 2147942414LL);
            return (unsigned int)-2147024882;
          }
          v17 = CConnection::GenClientContext(v6, 0, 0, &v111);
          _mm_lfence();
          if ( v17 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 && off_180265E08[0] )
              bidTraceW(off_1802626C8[0], 1602560, off_180265E08[0], v6);
            CTdsParser::PostSNIErrorEx(*((CTdsParser **)v6 + 165), v6, *(void **)(*((_QWORD *)v6 + 3) + 96LL), 0x9D25u);
            return (unsigned int)v17;
          }
          if ( v111 >= *(_DWORD *)(*((_QWORD *)v6 + 165) + 208LL) || *((_DWORD *)v6 + 24) )
          {
            v17 = -2147418113;
            if ( (bidGblFlags & 2) != 0 )
            {
              v20 = 1610761;
              goto LABEL_264;
            }
            return (unsigned int)v17;
          }
          _mm_lfence();
          v73 = (const void *)*((_QWORD *)v6 + 11);
          *(_WORD *)(v61 + 78) = *((_WORD *)v4 + 4);
          v74 = v111;
          *(_WORD *)(v61 + 80) = v111;
          v75 = CExtByteBuffer::WriteIntoExtBuffer(v4, v73, v74);
          v17 = v75;
          v103 = v75;
          if ( v75 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 )
            {
              v76 = (unsigned int)v75;
              v20 = 1614857;
LABEL_265:
              _mm_lfence();
              bidTraceHR(off_1802626C8[0], v20, v76);
              return (unsigned int)v17;
            }
            return (unsigned int)v17;
          }
          _mm_lfence();
          v61 = *((_QWORD *)v4 + 4);
          v106 = v61;
          if ( v111 > 0xFFFF )
          {
            *(_WORD *)(v61 + 80) = -1;
            *(_DWORD *)(v61 + 90) = v111;
          }
        }
        else
        {
          *(_BYTE *)(v61 + 25) &= ~0x80u;
          if ( *((_BYTE *)a3 + 132) )
          {
            v63 = (*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)g_pMO + 88LL))(g_pMO, 64);
            if ( !v63 )
            {
              if ( (bidGblFlags & 2) != 0 )
                return (unsigned int)bidTraceHR(off_1802626C8[0], 1636361, 2147942414LL);
              return (unsigned int)-2147024882;
            }
            v64 = ((unsigned __int8)(*((_BYTE *)a3 + 132) - 1) <= 1u) + 1;
            v65 = *((_DWORD *)v6 + 111);
            *(_BYTE *)(v63 + 8) = 2;
            *(_DWORD *)(v63 + 12) = 0;
            *(_QWORD *)v63 = &CFederatedAuthenticationFeatureExtension::`vftable';
            *(_BYTE *)(v63 + 16) = 2;
            *(_QWORD *)(v63 + 24) = 0;
            *(_DWORD *)(v63 + 32) = v64;
            *(_QWORD *)(v63 + 40) = 0;
            *(_QWORD *)(v63 + 48) = 0;
            *(_DWORD *)(v63 + 56) = 0;
            *(_DWORD *)(v63 + 60) = v65;
            v100 = (SessionRecoveryFeatureExtension *)v63;
            std::list<CFeatureExtension *>::push_front((char *)v6 + 1328, &v100);
          }
          else if ( *((_QWORD *)a3 + 6) )
          {
            *(_BYTE *)(v61 + 27) |= 1u;
            *((_DWORD *)v6 + 107) = 1;
            v66 = (_OWORD *)*((_QWORD *)a3 + 6);
            v67 = Src;
            if ( v66 )
            {
              v68 = 2;
              do
              {
                *v67 = *v66;
                v67[1] = v66[1];
                v67[2] = v66[2];
                v67[3] = v66[3];
                v67[4] = v66[4];
                v67[5] = v66[5];
                v67[6] = v66[6];
                v67 += 8;
                *(v67 - 1) = v66[7];
                v66 += 8;
                --v68;
              }
              while ( v68 );
              *v67 = *v66;
              v67[1] = v66[1];
            }
            else
            {
              memset_0(Src, 0, sizeof(Src));
              *_errno() = 22;
              _invalid_parameter_noinfo();
            }
            if ( g_pfnCryptUnprotectMemory && !g_pfnCryptUnprotectMemory(Src, 0x120u, 0) )
            {
              if ( (bidGblFlags & 2) != 0 && off_180265E10[0] )
              {
                LastError = GetLastError();
                bidTraceW(off_1802626C8[0], 1662976, off_180265E10[0], LastError);
              }
              v17 = -2147467259;
              if ( (bidGblFlags & 2) != 0 && off_180265E18[0] )
              {
                v99 = -2147467259;
                v98 = 40488;
                v31 = v104;
                HIDWORD(v97) = HIDWORD(v104);
                bidTraceW(off_1802626C8[0], 1665024, off_180265E18[0], v6);
                goto LABEL_51;
              }
              goto LABEL_50;
            }
            v17 = 0;
            do
              ++v18;
            while ( Src[v18] );
            *(_WORD *)(v61 + 86) = *((_WORD *)v4 + 4);
            *(_WORD *)(v61 + 88) = v18;
            if ( (_WORD)v18 )
              v17 = CExtByteBuffer::WriteIntoExtBuffer(v4, Src, 2LL * (unsigned __int16)v18);
            v103 = v17;
            memset(Src, 0, sizeof(Src));
            if ( v17 < 0 )
            {
              if ( (bidGblFlags & 2) != 0 )
              {
                v20 = 1677321;
                goto LABEL_264;
              }
              return (unsigned int)v17;
            }
            _mm_lfence();
            v61 = *((_QWORD *)v4 + 4);
            v106 = v61;
            v70 = (_BYTE *)(v61 + *(unsigned __int16 *)(v61 + 86));
            for ( i = 2LL * *(unsigned __int16 *)(v61 + 88); i; --i )
            {
              *v70 = __ROR1__(*v70, 4) ^ 0xA5;
              ++v70;
            }
          }
        }
        if ( !*((_DWORD *)v6 + 111) || !*((_QWORD *)a3 + 33) )
          goto LABEL_226;
        v77 = 2LL * *((unsigned int *)a3 + 68);
        Size = v77;
        if ( v77 <= 0xFFFFFFFF )
        {
          v78 = (void *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, _QWORD))(*(_QWORD *)g_pMO + 112LL))(
                          g_pMO,
                          (unsigned int)v77);
          v101 = v78;
          if ( v78 )
          {
            v79 = (const void *)*((_QWORD *)a3 + 33);
            v80 = Size;
            if ( (_DWORD)Size )
            {
              if ( v79 )
              {
                memcpy_0(v78, v79, (unsigned int)Size);
              }
              else
              {
                memset_0(v78, 0, (unsigned int)Size);
                *_errno() = 22;
                _invalid_parameter_noinfo();
              }
              v80 = Size;
              v78 = v101;
            }
            if ( g_pfnCryptUnprotectMemory && !g_pfnCryptUnprotectMemory(v78, v80, 0) )
            {
              if ( (bidGblFlags & 2) != 0 && off_180265E20[0] )
              {
                v81 = GetLastError();
                bidTraceW(off_1802626C8[0], 1707008, off_180265E20[0], v81);
              }
              v17 = -2147467259;
              if ( (bidGblFlags & 2) != 0 && off_180265E28[0] )
              {
                v99 = -2147467259;
                v98 = 40488;
                v82 = v104;
                HIDWORD(v97) = HIDWORD(v104);
                bidTraceW(off_1802626C8[0], 1709056, off_180265E28[0], v6);
              }
              else
              {
                v82 = v104;
              }
              v83 = *((_QWORD *)v6 + 165);
              v84 = GetLastError();
              LODWORD(v97) = -2147467259;
              CTdsParser::PostFormattedParserErrorEx(v83, v82, 3, 40488, v97, v84, v98, v99);
              v85 = v101;
              goto LABEL_255;
            }
            v86 = (*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)g_pMO + 88LL))(g_pMO, 64);
            if ( !v86 )
            {
              v85 = v101;
              if ( (bidGblFlags & 2) != 0 )
                v17 = bidTraceHR(off_1802626C8[0], 1716233, 2147942414LL);
              else
                v17 = -2147024882;
              goto LABEL_255;
            }
            v87 = (char *)v6 + 448;
            if ( !*((_DWORD *)v6 + 120) )
              v87 = 0;
            v88 = *((_DWORD *)v6 + 111);
            *(_BYTE *)(v86 + 8) = 2;
            *(_DWORD *)(v86 + 12) = 0;
            *(_QWORD *)v86 = &CFederatedAuthenticationFeatureExtension::`vftable';
            *(_BYTE *)(v86 + 16) = 1;
            v89 = v101;
            *(_QWORD *)(v86 + 24) = v101;
            *(_DWORD *)(v86 + 32) = 0;
            *(_QWORD *)(v86 + 40) = v87;
            *(_QWORD *)(v86 + 48) = 0;
            *(_DWORD *)(v86 + 56) = 0;
            *(_DWORD *)(v86 + 60) = v88;
            v101 = v89;
            v100 = (SessionRecoveryFeatureExtension *)v86;
            std::list<CFeatureExtension *>::push_front((char *)v6 + 1328, &v100);
            v108 = v89;
            v105 = Size;
LABEL_226:
            v90 = (*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)g_pMO + 88LL))(g_pMO, 16);
            if ( v90 )
            {
              *(_BYTE *)(v90 + 8) = 10;
              *(_DWORD *)(v90 + 12) = 0;
              *(_QWORD *)v90 = &SupportUTF8FeatureExtension::`vftable';
              v100 = (SessionRecoveryFeatureExtension *)v90;
              std::list<CFeatureExtension *>::push_front((char *)v6 + 1328, &v100);
              v91 = (*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)g_pMO + 88LL))(g_pMO, 16);
              if ( v91 )
              {
                *(_BYTE *)(v91 + 8) = 9;
                *(_DWORD *)(v91 + 12) = 0;
                *(_QWORD *)v91 = &DataClassificationExtension::`vftable';
                v100 = (SessionRecoveryFeatureExtension *)v91;
                std::list<CFeatureExtension *>::push_front((char *)v6 + 1328, &v100);
                if ( *((_BYTE *)a3 + 236) )
                {
                  v100 = 0;
                  try
                  {
                    v92 = (SessionRecoveryFeatureExtension *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)g_pMO + 88LL))(
                                                               g_pMO,
                                                               32);
                    v110 = v92;
                    if ( v92 )
                      v7 = SessionRecoveryFeatureExtension::SessionRecoveryFeatureExtension(
                             v92,
                             *((_BYTE *)a3 + 237),
                             v104);
                    v100 = v7;
                    v85 = v101;
                  }
                  catch ( std::invalid_argument )
                  {
                    v17 = v103;
                    v61 = v106;
                    v85 = v108;
                    Size = v105;
                    v7 = v100;
                    v6 = v109;
                    v4 = v107;
                  }
                  if ( !v7 )
                  {
                    if ( (bidGblFlags & 2) != 0 )
                    {
                      v17 = bidTraceHR(off_1802626C8[0], 1742857, 2147942414LL);
                      goto LABEL_254;
                    }
                    goto LABEL_253;
                  }
                  v107 = v7;
                  std::list<CFeatureExtension *>::push_front((char *)v6 + 1328, &v107);
                }
                else
                {
                  v85 = v101;
                }
                if ( *((_QWORD *)v6 + 167) )
                {
                  *(_BYTE *)(v61 + 27) |= 0x10u;
                  *(_DWORD *)(*((_QWORD *)v4 + 4) + *(unsigned __int16 *)(v61 + 56)) = *((_DWORD *)v4 + 2);
                  v93 = SerializeFeatureExtensions((CConnection *)((char *)v6 + 1328), v4);
                  v17 = v93;
                  if ( v93 < 0 )
                  {
                    if ( (bidGblFlags & 2) != 0 )
                    {
                      _mm_lfence();
                      bidTraceHR(off_1802626C8[0], 1758217, (unsigned int)v93);
                    }
LABEL_254:
                    if ( !v85 )
                      return (unsigned int)v17;
LABEL_255:
                    memset(v85, 0, (unsigned int)Size);
                    (*(void (__fastcall **)(struct ISOSHost_MemObj *, void *))(*(_QWORD *)g_pMO + 128LL))(g_pMO, v85);
                    return (unsigned int)v17;
                  }
                  _mm_lfence();
                  v61 = *((_QWORD *)v4 + 4);
                }
                *(_DWORD *)v61 = *((_DWORD *)v4 + 2);
                goto LABEL_254;
              }
              if ( (bidGblFlags & 2) != 0 )
              {
                v94 = 1726473;
LABEL_251:
                v95 = bidTraceHR(off_1802626C8[0], v94, 2147942414LL);
                v85 = v101;
                v17 = v95;
                goto LABEL_254;
              }
            }
            else if ( (bidGblFlags & 2) != 0 )
            {
              v94 = 1721353;
              goto LABEL_251;
            }
            v85 = v101;
LABEL_253:
            v17 = -2147024882;
            goto LABEL_254;
          }
        }
        return (unsigned int)-2147024882;
      }
      _mm_lfence();
LABEL_103:
      v17 = CExtByteBuffer::WriteIntoExtBuffer(v4, v43, 2LL * (unsigned __int16)v46);
      goto LABEL_104;
    }
  }
  v23 = (_WORD *)*((_QWORD *)a3 + 4);
  v17 = 0;
  if ( v23 )
  {
    v24 = -1;
    do
      ++v24;
    while ( v23[v24] );
  }
  else
  {
    LOWORD(v24) = 0;
  }
  v21[20] = *((_WORD *)v4 + 4);
  v21[21] = v24;
  if ( (_WORD)v24 )
    v17 = CExtByteBuffer::WriteIntoExtBuffer(v4, v23, 2LL * (unsigned __int16)v24);
  if ( v17 < 0 )
  {
    if ( (bidGblFlags & 2) == 0 )
      return (unsigned int)v17;
    v20 = 1458185;
    goto LABEL_264;
  }
  _mm_lfence();
  v25 = (SessionRecoveryFeatureExtension *)*((_QWORD *)v4 + 4);
  v100 = v25;
  v26 = g_pfnCryptUnprotectMemory;
  if ( g_pfnCryptUnprotectMemory )
  {
    v27 = (_OWORD *)*((_QWORD *)a3 + 5);
    if ( !v27 )
    {
      v17 = -2147418113;
      if ( (bidGblFlags & 2) == 0 )
        return (unsigned int)v17;
      v20 = 1467401;
      goto LABEL_264;
    }
    v28 = Src;
    v29 = 2;
    do
    {
      *v28 = *v27;
      v28[1] = v27[1];
      v28[2] = v27[2];
      v28[3] = v27[3];
      v28[4] = v27[4];
      v28[5] = v27[5];
      v28[6] = v27[6];
      v28 += 8;
      *(v28 - 1) = v27[7];
      v27 += 8;
      --v29;
    }
    while ( v29 );
    *v28 = *v27;
    v28[1] = v27[1];
    if ( !((unsigned int (__fastcall *)(_WORD *, __int64, _QWORD))v26)(Src, 288, 0) )
    {
      if ( (bidGblFlags & 2) != 0 && off_180265DF8[0] )
      {
        v30 = GetLastError();
        bidTraceW(off_1802626C8[0], 1483776, off_180265DF8[0], v30);
      }
      v17 = -2147467259;
      if ( (bidGblFlags & 2) != 0 && off_180265E00[0] )
      {
        v99 = -2147467259;
        v98 = 40488;
        v31 = v104;
        HIDWORD(v97) = HIDWORD(v104);
        bidTraceW(off_1802626C8[0], 1485824, off_180265E00[0], v6);
LABEL_51:
        v32 = *((_QWORD *)v6 + 165);
        v33 = GetLastError();
        LODWORD(v97) = -2147467259;
        CTdsParser::PostFormattedParserErrorEx(v32, v31, 3, 40488, v97, v33, v98, v99);
        return (unsigned int)v17;
      }
LABEL_50:
      v31 = v104;
      goto LABEL_51;
    }
    v17 = 0;
    v34 = -1;
    do
      ++v34;
    while ( Src[v34] );
    v35 = v100;
    *((_WORD *)v100 + 22) = *((_WORD *)v4 + 4);
    *((_WORD *)v35 + 23) = v34;
    if ( (_WORD)v34 )
      v17 = CExtByteBuffer::WriteIntoExtBuffer(v4, Src, 2LL * (unsigned __int16)v34);
    memset(Src, 0, sizeof(Src));
    if ( v17 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        v20 = 1497097;
LABEL_264:
        v76 = (unsigned int)v17;
        goto LABEL_265;
      }
      return (unsigned int)v17;
    }
    goto LABEL_69;
  }
  v36 = (_WORD *)*((_QWORD *)a3 + 5);
  v17 = 0;
  if ( v36 )
  {
    v37 = -1;
    do
      ++v37;
    while ( v36[v37] );
  }
  else
  {
    LOWORD(v37) = 0;
  }
  *((_WORD *)v25 + 22) = *((_WORD *)v4 + 4);
  *((_WORD *)v25 + 23) = v37;
  if ( (_WORD)v37 )
  {
    _mm_lfence();
    v17 = CExtByteBuffer::WriteIntoExtBuffer(v4, v36, 2LL * (unsigned __int16)v37);
  }
  if ( v17 >= 0 )
  {
LABEL_69:
    _mm_lfence();
    v21 = (_WORD *)*((_QWORD *)v4 + 4);
    v38 = (char *)v21 + (unsigned __int16)v21[22];
    for ( j = 2LL * (unsigned __int16)v21[23]; j; --j )
    {
      *v38 = __ROR1__(*v38, 4) ^ 0xA5;
      ++v38;
    }
    goto LABEL_71;
  }
  if ( (bidGblFlags & 2) != 0 )
  {
    v20 = 1502217;
    goto LABEL_264;
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x180197440  push    rbx
0x180197442  push    rsi
0x180197443  push    rdi
0x180197444  push    r12
0x180197446  push    r13
0x180197448  push    r14
0x18019744a  push    r15
0x18019744c  sub     rsp, 280h
0x180197453  mov     rax, cs:__security_cookie
0x18019745a  xor     rax, rsp
0x18019745d  mov     [rsp+2B8h+var_48], rax
0x180197465  mov     rsi, r9
0x180197468  mov     r13, r8
0x18019746b  mov     [rsp+2B8h+var_258], rdx
0x180197470  mov     r15, rcx
0x180197473  mov     [rsp+2B8h+var_230], rcx
0x18019747b  mov     [rsp+2B8h+var_240], r9
0x180197480  xor     r14d, r14d
0x180197483  mov     dword ptr [rsp+2B8h+var_220+4], r14d
0x18019748b  mov     eax, r14d
0x18019748e  mov     [rsp+2B8h+var_270], rax
0x180197493  mov     [rsp+2B8h+var_238], rax
0x18019749b  mov     [rsp+2B8h+Size], rax
0x1801974a0  mov     [rsp+2B8h+var_250], eax
0x1801974a4  xor     edx, edx; Val
0x1801974a6  mov     r8d, 0ACh; Size
0x1801974ac  lea     rcx, [rsp+2B8h+TimeZoneInformation]; void *
0x1801974b4  call    memset_0
0x1801974b9  test    r13, r13
0x1801974bc  jz      loc_1801986B7
0x1801974c2  test    rsi, rsi
0x1801974c5  jz      loc_1801986B7
0x1801974cb  cmp     qword ptr [rsi+10h], 5Eh ; '^'
0x1801974d0  jb      loc_1801986B7
0x1801974d6  mov     rdi, [rsi+20h]
0x1801974da  mov     qword ptr [rsi+8], 5Eh ; '^'
0x1801974e2  xorps   xmm0, xmm0
0x1801974e5  xor     eax, eax
0x1801974e7  movups  xmmword ptr [rdi], xmm0
0x1801974ea  movups  xmmword ptr [rdi+10h], xmm0
0x1801974ee  movups  xmmword ptr [rdi+20h], xmm0
0x1801974f2  movups  xmmword ptr [rdi+30h], xmm0
0x1801974f6  movups  xmmword ptr [rdi+40h], xmm0
0x1801974fa  mov     [rdi+50h], rax
0x1801974fe  mov     [rdi+58h], eax
0x180197501  mov     [rdi+5Ch], ax
0x180197505  movzx   ecx, word ptr [r15+518h]
0x18019750d  shl     ecx, 10h
0x180197510  movzx   eax, word ptr [r15+51Ah]
0x180197518  or      ecx, eax
0x18019751a  mov     [rdi+4], ecx
0x18019751d  mov     eax, [r13+80h]
0x180197524  mov     [rdi+8], eax
0x180197527  mov     dword ptr [rdi+0Ch], 7000000h
0x18019752e  call    cs:__imp_GetCurrentProcessId
0x180197534  mov     [rdi+10h], eax
0x180197537  mov     [rdi+14h], r14d
0x18019753b  movzx   edx, byte ptr [rdi+18h]
0x18019753f  and     dl, 0FCh
0x180197542  mov     [rdi+18h], dl
0x180197545  mov     eax, [r13+0B0h]
0x18019754c  neg     eax
0x18019754e  sbb     cl, cl
0x180197550  and     cl, 10h
0x180197553  and     dl, 3
0x180197556  or      cl, dl
0x180197558  or      cl, 0E0h
0x18019755b  mov     [rdi+18h], cl
0x18019755e  movzx   ecx, byte ptr [rdi+1Ah]
0x180197562  and     cl, 0F0h
0x180197565  mov     [rdi+1Ah], cl
0x180197568  movzx   eax, byte ptr [rdi+19h]
0x18019756c  and     al, 0FBh
0x18019756e  or      al, 1
0x180197570  mov     [rdi+19h], al
0x180197573  mov     r8d, r14d
0x180197576  mov     eax, 20h ; ' '
0x18019757b  cmp     dword ptr [r13+0E4h], 1
0x180197583  cmovz   r8d, eax
0x180197587  and     cl, 0DFh
0x18019758a  or      r8b, cl
0x18019758d  mov     [rdi+1Ah], r8b
0x180197591  mov     rdx, [r13+60h]
0x180197595  test    rdx, rdx
0x180197598  jz      loc_1801986A2
0x18019759e  mov     ecx, r14d
0x1801975a1  lea     r9, aOledb; "OLEDB"
0x1801975a8  nop     dword ptr [rax+rax+00000000h]
0x1801975b0  movzx   eax, word ptr [rdx+rcx*2]
0x1801975b4  inc     rcx
0x1801975b7  cmp     ax, [r9+rcx*2-2]
0x1801975bd  jnz     loc_1801986A2
0x1801975c3  cmp     rcx, 6
0x1801975c7  jnz     short loc_1801975B0
0x1801975c9  test    [rdi+1Bh], cl
0x1801975cc  jnz     loc_1801986A2
0x1801975d2  or      r8b, 10h
0x1801975d6  mov     [rdi+1Ah], r8b
0x1801975da  lea     rcx, [rsp+2B8h+TimeZoneInformation]; lpTimeZoneInformation
0x1801975e2  call    cs:__imp_GetTimeZoneInformation
0x1801975e8  mov     ecx, 0FFFFFFFFh
0x1801975ed  cmp     eax, ecx
0x1801975ef  jz      short loc_1801975FB
0x1801975f1  mov     eax, [rsp+2B8h+TimeZoneInformation.Bias]
0x1801975f8  mov     [rdi+1Ch], eax
0x1801975fb  mov     eax, [r13+0BCh]
0x180197602  mov     [rdi+20h], eax
0x180197605  mov     rdx, [r13+38h]; Src
0x180197609  mov     ebx, r14d
0x18019760c  mov     r12, 0FFFFFFFFFFFFFFFFh
0x180197613  test    rdx, rdx
0x180197616  jz      short loc_18019762B
0x180197618  mov     rcx, r12
0x18019761b  nop     dword ptr [rax+rax+00h]
0x180197620  inc     rcx
0x180197623  cmp     [rdx+rcx*2], bx
0x180197627  jnz     short loc_180197620
0x180197629  jmp     short loc_18019762E
0x18019762b  mov     rcx, r14
0x18019762e  movzx   eax, word ptr [rsi+8]
0x180197632  mov     [rdi+24h], ax
0x180197636  mov     [rdi+26h], cx
0x18019763a  test    cx, cx
0x18019763d  jz      short loc_180197650
0x18019763f  movzx   r8d, cx
0x180197643  add     r8, r8; Size
0x180197646  mov     rcx, rsi; this
0x180197649  call    ?WriteIntoExtBuffer@CExtByteBuffer@@QEAAJPEBX_K@Z; CExtByteBuffer::WriteIntoExtBuffer(void const *,unsigned __int64)
0x18019764e  mov     ebx, eax
0x180197650  test    ebx, ebx
0x180197652  jns     short loc_18019766B
0x180197654  test    byte ptr cs:_bidGblFlags, 2
0x18019765b  jz      loc_1801986DC
0x180197661  mov     edx, 162409h
0x180197666  jmp     loc_1801986CA
0x18019766b  lfence
0x18019766e  mov     rdi, [rsi+20h]
0x180197672  cmp     [r13+84h], r14b
0x180197679  jnz     short loc_180197684
0x18019767b  cmp     [r13+108h], r14
0x180197682  jz      short loc_18019769B
0x180197684  mov     rax, [r13+48h]
0x180197688  test    rax, rax
0x18019768b  jz      loc_180197996
0x180197691  cmp     [rax], r14w
0x180197695  jz      loc_180197996
0x18019769b  mov     rdx, [r13+20h]; Src
0x18019769f  mov     ebx, r14d
0x1801976a2  test    rdx, rdx
0x1801976a5  jz      short loc_1801976BB
0x1801976a7  mov     rcx, r12
0x1801976aa  nop     word ptr [rax+rax+00h]
0x1801976b0  inc     rcx
0x1801976b3  cmp     [rdx+rcx*2], bx
0x1801976b7  jnz     short loc_1801976B0
0x1801976b9  jmp     short loc_1801976BE
0x1801976bb  mov     rcx, r14
0x1801976be  movzx   eax, word ptr [rsi+8]
0x1801976c2  mov     [rdi+28h], ax
0x1801976c6  mov     [rdi+2Ah], cx
0x1801976ca  test    cx, cx
0x1801976cd  jz      short loc_1801976E0
0x1801976cf  movzx   r8d, cx
0x1801976d3  add     r8, r8; Size
0x1801976d6  mov     rcx, rsi; this
0x1801976d9  call    ?WriteIntoExtBuffer@CExtByteBuffer@@QEAAJPEBX_K@Z; CExtByteBuffer::WriteIntoExtBuffer(void const *,unsigned __int64)
0x1801976de  mov     ebx, eax
0x1801976e0  test    ebx, ebx
0x1801976e2  jns     short loc_1801976FB
0x1801976e4  test    byte ptr cs:_bidGblFlags, 2
0x1801976eb  jz      loc_1801986DC
0x1801976f1  mov     edx, 164009h
0x1801976f6  jmp     loc_1801986CA
0x1801976fb  lfence
0x1801976fe  mov     rdi, [rsi+20h]
0x180197702  mov     [rsp+2B8h+var_278], rdi
0x180197707  mov     r9, cs:?g_pfnCryptUnprotectMemory@@3P6AHPEAXKK@ZEA; int (*g_pfnCryptUnprotectMemory)(void *,ulong,ulong)
0x18019770e  test    r9, r9
0x180197711  jz      loc_180197904
0x180197717  mov     rax, [r13+28h]
0x18019771b  test    rax, rax
0x18019771e  jnz     short loc_18019773C
0x180197720  mov     ebx, 8000FFFFh
0x180197725  test    byte ptr cs:_bidGblFlags, 2
0x18019772c  jz      loc_1801986DC
0x180197732  mov     edx, 166409h
0x180197737  jmp     loc_1801986CA
0x18019773c  lea     rcx, [rsp+2B8h+Src]
0x180197744  mov     edx, 2
0x180197749  mov     edi, 80h
0x18019774e  xchg    ax, ax
0x180197750  movups  xmm0, xmmword ptr [rax]
0x180197753  movups  xmmword ptr [rcx], xmm0
0x180197756  movups  xmm1, xmmword ptr [rax+10h]
0x18019775a  movups  xmmword ptr [rcx+10h], xmm1
0x18019775e  movups  xmm0, xmmword ptr [rax+20h]
0x180197762  movups  xmmword ptr [rcx+20h], xmm0
0x180197766  movups  xmm1, xmmword ptr [rax+30h]
0x18019776a  movups  xmmword ptr [rcx+30h], xmm1
0x18019776e  movups  xmm0, xmmword ptr [rax+40h]
0x180197772  movups  xmmword ptr [rcx+40h], xmm0
0x180197776  movups  xmm1, xmmword ptr [rax+50h]
0x18019777a  movups  xmmword ptr [rcx+50h], xmm1
0x18019777e  movups  xmm0, xmmword ptr [rax+60h]
0x180197782  movups  xmmword ptr [rcx+60h], xmm0
0x180197786  add     rcx, rdi
0x180197789  movups  xmm1, xmmword ptr [rax+70h]
0x18019778d  movups  xmmword ptr [rcx-10h], xmm1
0x180197791  add     rax, rdi
0x180197794  sub     rdx, 1
0x180197798  jnz     short loc_180197750
0x18019779a  movups  xmm0, xmmword ptr [rax]
0x18019779d  movups  xmmword ptr [rcx], xmm0
0x1801977a0  movups  xmm1, xmmword ptr [rax+10h]
0x1801977a4  movups  xmmword ptr [rcx+10h], xmm1
0x1801977a8  xor     r8d, r8d
0x1801977ab  mov     edx, 120h
0x1801977b0  lea     rcx, [rsp+2B8h+Src]
0x1801977b8  mov     rax, r9
0x1801977bb  call    cs:__guard_dispatch_icall_fptr
0x1801977c1  test    eax, eax
0x1801977c3  jnz     loc_180197892
0x1801977c9  test    byte ptr cs:_bidGblFlags, 2
0x1801977d0  jz      short loc_1801977FF
0x1801977d2  mov     rax, cs:off_180265DF8; "<CConnection::CreateLoginRecord|ERR|SNA"...
0x1801977d9  test    rax, rax
0x1801977dc  jz      short loc_1801977FF
0x1801977de  call    cs:__imp_GetLastError
0x1801977e4  mov     r9d, eax
0x1801977e7  mov     r8, cs:off_180265DF8; "<CConnection::CreateLoginRecord|ERR|SNA"...
0x1801977ee  mov     edx, 16A400h
0x1801977f3  mov     rcx, cs:off_1802626C8; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\td"...
0x1801977fa  call    _bidTraceW
0x1801977ff  mov     ebx, 80004005h
0x180197804  test    byte ptr cs:_bidGblFlags, 2
0x18019780b  jz      short loc_180197855
0x18019780d  mov     rax, cs:off_180265E00; "<CConnection::CreateLoginRecord|TDS|ERR"...
0x180197814  test    rax, rax
0x180197817  jz      short loc_180197855
0x180197819  mov     [rsp+2B8h+var_280], ebx
0x18019781d  mov     esi, 9E28h
0x180197822  mov     [rsp+2B8h+var_288], esi
0x180197826  mov     [rsp+2B8h+var_290], 3
0x18019782e  mov     r14, [rsp+2B8h+var_258]
0x180197833  mov     [rsp+2B8h+var_298], r14
0x180197838  mov     r9, r15
0x18019783b  mov     r8, cs:off_180265E00; "<CConnection::CreateLoginRecord|TDS|ERR"...
0x180197842  mov     edx, 16AC00h
0x180197847  mov     rcx, cs:off_1802626C8; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\td"...
0x18019784e  call    _bidTraceW
0x180197853  jmp     short loc_18019785F
0x180197855  mov     esi, 9E28h
0x18019785a  mov     r14, [rsp+2B8h+var_258]
0x18019785f  mov     rdi, [r15+528h]
0x180197866  call    cs:__imp_GetLastError
0x18019786c  mov     [rsp+2B8h+var_290], eax
0x180197870  mov     dword ptr [rsp+2B8h+var_298], 80004005h
0x180197878  movzx   r9d, si
0x18019787c  mov     r8d, 3
0x180197882  mov     rdx, r14
0x180197885  mov     rcx, rdi
0x180197888  call    ?PostFormattedParserErrorEx@CTdsParser@@AEAAJPEAXW4_PARSE_ERR_TYPE@@GKZZ; CTdsParser::PostFormattedParserErrorEx(void *,_PARSE_ERR_TYPE,ushort,ulong,...)
0x18019788d  jmp     loc_1801986DC
0x180197892  mov     ebx, r14d
0x180197895  lea     rax, [rsp+2B8h+Src]
0x18019789d  mov     rcx, r12
0x1801978a0  inc     rcx
0x1801978a3  cmp     [rax+rcx*2], bx
0x1801978a7  jnz     short loc_1801978A0
0x1801978a9  movzx   eax, word ptr [rsi+8]
0x1801978ad  mov     rdx, [rsp+2B8h+var_278]
0x1801978b2  mov     [rdx+2Ch], ax
0x1801978b6  mov     [rdx+2Eh], cx
0x1801978ba  test    cx, cx
0x1801978bd  jz      short loc_1801978D8
0x1801978bf  movzx   r8d, cx
0x1801978c3  add     r8, r8; Size
0x1801978c6  lea     rdx, [rsp+2B8h+Src]; Src
0x1801978ce  mov     rcx, rsi; this
0x1801978d1  call    ?WriteIntoExtBuffer@CExtByteBuffer@@QEAAJPEBX_K@Z; CExtByteBuffer::WriteIntoExtBuffer(void const *,unsigned __int64)
0x1801978d6  mov     ebx, eax
0x1801978d8  lea     rdi, [rsp+2B8h+Src]
0x1801978e0  xor     eax, eax
0x1801978e2  mov     ecx, 120h
0x1801978e7  rep stosb
0x1801978e9  test    ebx, ebx
0x1801978eb  jns     short loc_180197961
0x1801978ed  test    byte ptr cs:_bidGblFlags, 2
0x1801978f4  jz      loc_1801986DC
0x1801978fa  mov     edx, 16D809h
0x1801978ff  jmp     loc_1801986CA
0x180197904  mov     rdx, [r13+28h]; Src
0x180197908  mov     ebx, r14d
0x18019790b  test    rdx, rdx
0x18019790e  jz      short loc_18019791E
0x180197910  mov     rcx, r12
0x180197913  inc     rcx
0x180197916  cmp     [rdx+rcx*2], bx
0x18019791a  jnz     short loc_180197913
0x18019791c  jmp     short loc_180197921
  ... truncated ...
```
