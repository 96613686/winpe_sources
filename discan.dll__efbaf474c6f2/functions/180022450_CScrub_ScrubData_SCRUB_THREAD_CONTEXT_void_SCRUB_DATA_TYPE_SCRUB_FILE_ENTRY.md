# CScrub::ScrubData(_SCRUB_THREAD_CONTEXT *,void *,_SCRUB_DATA_TYPE,_SCRUB_FILE_ENTRY *)

- ea: `0x180022450`
- end: `0x180023a3c`
- name: `?ScrubData@CScrub@@QEAAJPEAU_SCRUB_THREAD_CONTEXT@@PEAXW4_SCRUB_DATA_TYPE@@PEAU_SCRUB_FILE_ENTRY@@@Z`
- size: `5612`
- prototype: `__int64 __fastcall(__int64, struct _SCRUB_THREAD_CONTEXT *, void *, int, __int64)`
- caller_count: `6`
- callee_count: `35`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180023a44`
- `0x180023ecc`
- `0x180024280`
- `0x1800247c4`
- `0x180026eec`
- `0x1800293d4`

## callees

- `0x180001b78`
- `0x180001bc4`
- `0x180003134`
- `0x1800032f8`
- `0x180006688`
- `0x18000ad94`
- `0x180012048`
- `0x180012158`
- `0x18001bb10`
- `0x180021658`
- `0x1800216fc`
- `0x180021730`
- `0x180021ad8`
- `0x180022450`
- `0x1800271b4`
- `0x18002730c`
- `0x1800273d8`
- `0x1800288ac`
- `0x18002aeec`
- `0x18002b13c`
- `0x18002b5b8`
- `0x18002b83c`
- `0x18002b960`
- `0x18002c468`
- `0x18002c59c`
- `0x18002c6f8`
- `0x18002cba4`
- `0x18002cc9c`
- `0x18002cde0`
- `0x18002ced4`
- `0x18002d0c0`
- `0x18003061c`
- `0x1800375d6`
- `0x1800375e2`
- `0x1800375ee`

## import_xrefs

- `ntdll!NtFsControlFile` at `0x18002283e`
- `ntdll!NtFsControlFile` at `0x1800238c0`
- `ntdll!NtFsControlFile` at `0x18002283e`
- `ntdll!NtFsControlFile` at `0x1800238c0`

## pseudocode

```c
__int64 __fastcall CScrub::ScrubData(__int64 a1, struct _SCRUB_THREAD_CONTEXT *a2, void *a3, int a4, __int64 a5)
{
  struct _SCRUB_THREAD_CONTEXT *v6; // rbx
  __int64 v8; // r11
  USHORT v9; // dx
  USHORT Length; // cx
  USHORT v11; // ax
  unsigned __int64 InputBufferLength; // r12
  int v13; // ebx
  __int64 v14; // rsi
  volatile signed __int64 **v15; // r13
  char v16; // r14
  _QWORD *v17; // rcx
  struct _SCRUB_THREAD_CONTEXT *v18; // rdx
  unsigned __int64 v19; // r8
  unsigned __int64 v20; // r8
  __int64 v21; // r10
  _QWORD *v22; // rcx
  unsigned __int64 v23; // r8
  struct _SCRUB_THREAD_CONTEXT *v24; // rdx
  unsigned __int64 v25; // r8
  unsigned int v26; // eax
  unsigned int i; // r15d
  int v28; // eax
  int v29; // ebx
  int v30; // r8d
  struct _SCRUB_THREAD_CONTEXT *v31; // r10
  __int64 v32; // rax
  unsigned int v33; // ebx
  __int64 v34; // rax
  struct _SCRUB_THREAD_CONTEXT *v35; // rcx
  __int64 v36; // rdx
  unsigned __int64 v37; // rax
  __int64 v38; // rdx
  unsigned __int64 v39; // rax
  __int64 v40; // rdx
  char v41; // r14
  __int64 v42; // rax
  char *v43; // rsi
  PVOID *v44; // r11
  unsigned int v45; // eax
  int updated; // eax
  PVOID *v47; // r11
  int v48; // eax
  struct _SCRUB_THREAD_CONTEXT *v49; // rbx
  unsigned int v50; // r14d
  int v51; // edx
  int v52; // r8d
  unsigned int v53; // r15d
  PVOID *v54; // rcx
  char v55; // si
  unsigned int v56; // r8d
  __int64 v57; // r10
  unsigned __int64 v58; // rdx
  unsigned __int64 v59; // r8
  struct _SCRUB_THREAD_CONTEXT *v60; // rdx
  unsigned __int64 v61; // r15
  _QWORD *v62; // rcx
  unsigned __int64 v63; // r8
  unsigned __int64 v64; // r8
  __int64 v65; // rsi
  __int64 v66; // r8
  unsigned __int64 v67; // rbx
  _QWORD *v68; // rcx
  unsigned __int64 v69; // r8
  struct _SCRUB_THREAD_CONTEXT *v70; // rdx
  unsigned __int64 v71; // r8
  _QWORD *v72; // rcx
  unsigned __int64 v73; // r8
  struct _SCRUB_THREAD_CONTEXT *v74; // rdx
  unsigned __int64 v75; // r8
  unsigned __int64 v76; // r14
  struct _SCRUB_THREAD_CONTEXT *v77; // r14
  unsigned __int64 v78; // rdx
  unsigned __int64 v79; // r10
  unsigned __int64 v80; // r8
  struct _SCRUB_THREAD_CONTEXT *v81; // rdx
  unsigned __int64 v82; // rcx
  _QWORD *v83; // rbx
  __int64 *v84; // rsi
  _QWORD *v85; // rcx
  unsigned __int64 v86; // rdx
  unsigned __int64 v87; // r8
  _QWORD *v88; // rcx
  unsigned __int64 v89; // rdx
  unsigned __int64 v90; // r8
  unsigned __int64 v91; // rbx
  int v92; // r15d
  _QWORD *v93; // r14
  volatile signed __int64 *v94; // rax
  __int64 v95; // rcx
  __int64 v96; // r8
  __int64 v97; // r11
  struct _SCRUB_THREAD_CONTEXT *v98; // rsi
  unsigned __int64 v99; // rdx
  unsigned __int64 v100; // r10
  unsigned __int64 v101; // r8
  unsigned __int64 v102; // rdx
  _QWORD *v103; // rcx
  unsigned __int64 v104; // r8
  unsigned __int64 v105; // rdx
  bool v107; // [rsp+78h] [rbp-61h]
  unsigned __int64 v108; // [rsp+80h] [rbp-59h]
  unsigned __int64 v109; // [rsp+88h] [rbp-51h]
  _QWORD v110[2]; // [rsp+90h] [rbp-49h] BYREF
  int v111; // [rsp+A0h] [rbp-39h]
  unsigned int v112; // [rsp+A4h] [rbp-35h]
  __int64 v113; // [rsp+A8h] [rbp-31h] BYREF
  struct _SCRUB_THREAD_CONTEXT *v114; // [rsp+B0h] [rbp-29h] BYREF
  const char *v115; // [rsp+B8h] [rbp-21h] BYREF
  int v116; // [rsp+C0h] [rbp-19h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C8h] [rbp-11h] BYREF
  _BYTE v118[80]; // [rsp+D8h] [rbp-1h] BYREF
  char v119; // [rsp+138h] [rbp+5Fh]
  struct _SCRUB_THREAD_CONTEXT *v120; // [rsp+140h] [rbp+67h] BYREF
  HANDLE FileHandle; // [rsp+148h] [rbp+6Fh]
  int v122; // [rsp+150h] [rbp+77h]

  v122 = a4;
  FileHandle = a3;
  v120 = a2;
  v6 = a2;
  v8 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  *(_QWORD *)(v8 + 16) = "CScrub::ScrubData";
  v115 = "CScrub::ScrubData";
  v9 = ++*(_WORD *)(v8 + 8);
  Length = GlobalIndentString.Length;
  v11 = GlobalIndentString.Length;
  if ( v9 < GlobalIndentString.Length )
    v11 = *(_WORD *)(v8 + 8);
  LOWORD(v110[0]) = v11;
  if ( v9 < GlobalIndentString.Length )
    Length = v9;
  WORD1(v110[0]) = Length;
  HIDWORD(v110[0]) = 0;
  v110[1] = off_180047060;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"CScrub::ScrubData");
    v6 = v120;
  }
  *((_DWORD *)v6 + 31) = 64;
  *((_DWORD *)v120 + 32) = *(_DWORD *)(*(_QWORD *)(a1 + 8) + 32LL);
  *((_QWORD *)v120 + 19) = 0;
  *((_QWORD *)v120 + 20) = 0;
  IoStatusBlock = 0;
  v109 = 0;
  LOBYTE(InputBufferLength) = -1;
  v108 = -1;
  v113 = -1;
  v107 = 0;
  v13 = *(_DWORD *)(*(_QWORD *)(a1 + 8) + 8LL);
  v111 = v13;
  v14 = a5;
  v15 = (volatile signed __int64 **)(a5 + 56);
  if ( a5 && *v15 )
  {
    v16 = 0;
    v119 = 0;
    goto LABEL_17;
  }
  v16 = 1;
  v119 = 1;
  if ( a5 )
  {
    if ( *v15 )
      goto LABEL_17;
  }
  else
  {
    v16 = 1;
    v119 = 1;
  }
  ++*((_QWORD *)v120 + 191);
LABEL_17:
  ++*((_QWORD *)v120 + 192);
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v18 = v120;
    v19 = *(_QWORD *)(a1 + 1424);
    if ( v19 > (unsigned __int64)v120
      || (v18 = v120, v17 = WPP_GLOBAL_Control, (unsigned __int64)v120 > v19 + 35024LL * (*(_DWORD *)(a1 + 1372) - 1)) )
    {
      LOBYTE(v20) = ((unsigned __int64)v18 - *(_QWORD *)(a1 + 1416)) / 0x88D0 + 100;
    }
    else
    {
      v20 = ((unsigned __int64)v120 - *(_QWORD *)(a1 + 1424)) / 0x88D0;
    }
    WPP_SF_DDZdZq(
      v17[2],
      *(_DWORD *)(**(_QWORD **)a1 + 36LL),
      *(_QWORD *)(*(_QWORD *)a1 + 64LL),
      v20,
      (__int64)v120 + 88,
      (char)a3);
  }
  memset_0((void *)(a1 + 124), 0, 0x410u);
  *((_DWORD *)v120 + 30) = 1232;
  if ( v13 == 1 )
  {
    *((_DWORD *)v120 + 31) |= 2u;
    if ( v14 )
    {
      if ( *v15 )
      {
        *((_QWORD *)v120 + 19) = *(_QWORD *)(v14 + 64);
        *((_QWORD *)v120 + 20) = *(_QWORD *)(v14 + 72);
        v21 = *(_QWORD *)(v14 + 64);
        InputBufferLength = v21 + *(_QWORD *)(v14 + 72);
        v108 = InputBufferLength;
        v113 = InputBufferLength;
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v23 = *(_QWORD *)(a1 + 1424);
          v24 = v120;
          if ( v23 > (unsigned __int64)v120
            || (v24 = v120,
                v22 = WPP_GLOBAL_Control,
                (unsigned __int64)v120 > v23 + 35024LL * (*(_DWORD *)(a1 + 1372) - 1)) )
          {
            LODWORD(v25) = ((unsigned __int64)v24 - *(_QWORD *)(a1 + 1416)) / 0x88D0 + 100;
          }
          else
          {
            v25 = ((unsigned __int64)v120 - *(_QWORD *)(a1 + 1424)) / 0x88D0;
          }
          WPP_SF_DDZdii(
            v22[2],
            128,
            v25,
            *(_DWORD *)(**(_QWORD **)a1 + 16LL),
            *(_DWORD *)(**(_QWORD **)a1 + 36LL),
            *(_QWORD *)(*(_QWORD *)a1 + 64LL),
            v25,
            v21,
            InputBufferLength);
        }
      }
    }
  }
  else if ( **(_DWORD **)(a1 + 8) == 3 )
  {
    *((_DWORD *)v120 + 31) |= 4u;
  }
  if ( *(char *)(a1 + 1260) < 0 )
    *((_DWORD *)v120 + 31) |= 8u;
  v26 = NtFsControlFile(
          a3,
          *((HANDLE *)v120 + 9),
          0,
          0,
          &IoStatusBlock,
          0x902B0u,
          (char *)v120 + 120,
          0xC0u,
          (char *)v120 + 120,
          0x550u);
  for ( i = 0; ; i = v112 )
  {
    v28 = CScrub::_ScrubWaitIo(
            (CScrub *)a1,
            (struct _SCRUB_THREAD_CONTEXT *)v26,
            FileHandle,
            &IoStatusBlock,
            v26,
            *((HANDLE *)v120 + 9));
    v29 = v28;
    v116 = v28;
    if ( v28 == -805306102 )
      break;
    if ( v28 < 0 )
    {
      CScrub::_AddErrorRecord((CScrub *)a1, v28, (const struct _UNICODE_STRING *)((char *)v120 + 88));
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_DDZZd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          *(_DWORD *)(**(_QWORD **)a1 + 36LL),
          *(_QWORD *)(*(_QWORD *)a1 + 64LL),
          (__int64)v120 + 88,
          v29);
      }
      break;
    }
    v29 = ValidateScrubOutputData((struct _SCRUB_THREAD_CONTEXT *)((char *)v120 + 120), IoStatusBlock.Information);
    v116 = v29;
    if ( v29 < 0 || v14 && *v15 && *((_BYTE *)*v15 + 16) )
      break;
    v31 = v120;
    v32 = *((_QWORD *)v120 + 19);
    v33 = 0;
    if ( v32 )
    {
      *((_QWORD *)v120 + 186) += v32;
      v31 = v120;
    }
    v34 = *((_QWORD *)v31 + 20);
    if ( v34 )
    {
      *((_QWORD *)v31 + 187) += v34;
      v31 = v120;
    }
    if ( (*(_DWORD *)(a1 + 1260) & 0x20000000) != 0 )
    {
      *((_QWORD *)v31 + 193) += *((_QWORD *)v31 + 27);
      *((_QWORD *)v120 + 194) += *((_QWORD *)v120 + 28);
      v35 = v120;
      if ( v16 )
      {
        v36 = *((_QWORD *)v120 + 195);
        v37 = *((_QWORD *)v120 + 29);
        if ( !v36 )
          goto LABEL_57;
        if ( v37 && v37 != v36 )
        {
          v37 = (v36 + v37) >> 1;
LABEL_57:
          *((_QWORD *)v120 + 195) = v37;
          v35 = v120;
        }
        v38 = *((_QWORD *)v35 + 196);
        v39 = *((_QWORD *)v35 + 30);
        if ( v38 )
        {
          if ( v39 && v39 != v38 )
          {
            v39 = (v38 + v39) >> 1;
            goto LABEL_62;
          }
        }
        else
        {
LABEL_62:
          *((_QWORD *)v35 + 196) = v39;
          v35 = v120;
        }
      }
      if ( v111 == 1 && (*(_DWORD *)(a1 + 1260) & 0x20000000) != 0 && *(_BYTE *)(*(_QWORD *)(a1 + 8) + 6LL) && v14 )
      {
        v109 = *((_QWORD *)v35 + 24);
        v107 = v109 > 0x40000000;
      }
      v40 = 0;
      while ( 1 )
      {
        *((_QWORD *)v35 + v40 + 198) += *((_QWORD *)v35 + v40 + 31);
        if ( ++v40 == 8 )
          break;
        v35 = v120;
      }
      v31 = v120;
    }
    v41 = 0;
    if ( (*((_DWORD *)v31 + 31) & 0x20000) == 0 )
      goto LABEL_93;
    v42 = *((unsigned __int16 *)v31 + 89);
    if ( !(_WORD)v42 )
      goto LABEL_93;
    v41 = 1;
    v43 = (char *)v31 + v42;
    v44 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_DDZZD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        *(_DWORD *)(**(_QWORD **)a1 + 36LL),
        *(_QWORD *)(*(_QWORD *)a1 + 64LL),
        (__int64)v31 + 88,
        *((_WORD *)v43 + 62));
      v44 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( *((_WORD *)v43 + 62) )
    {
      do
      {
        if ( v44 != &WPP_GLOBAL_Control && (*((_BYTE *)v44 + 28) & 1) != 0 && *((_BYTE *)v44 + 25) >= 3u )
        {
          WPP_SF_DDZDii(
            (unsigned int)v44[2],
            *(_QWORD *)a1,
            v30,
            *(_DWORD *)(**(_QWORD **)a1 + 16LL),
            *(_DWORD *)(**(_QWORD **)a1 + 36LL),
            *(_QWORD *)(*(_QWORD *)a1 + 64LL),
            v33,
            *(_QWORD *)&v43[16 * v33 + 128],
            *(_QWORD *)&v43[16 * v33 + 136]);
          v44 = (PVOID *)WPP_GLOBAL_Control;
        }
        ++v33;
        v45 = *((unsigned __int16 *)v43 + 62);
      }
      while ( v33 < v45 );
    }
    else
    {
      LOWORD(v45) = *((_WORD *)v43 + 62);
    }
    updated = CScrubDatabase::UpdateParityExtent(
                (CScrubDatabase *)(a1 + 80),
                (const struct _SCRUB_PARITY_EXTENT *)(v43 + 128),
                (unsigned __int16)v45);
    v116 = updated;
    if ( updated >= 0 )
    {
      v31 = v120;
      goto LABEL_93;
    }
    v47 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_DDZd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        132,
        (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
        *(_DWORD *)(**(_QWORD **)a1 + 16LL),
        *(_DWORD *)(**(_QWORD **)a1 + 36LL),
        *(_QWORD *)(*(_QWORD *)a1 + 64LL),
        updated);
      v31 = v120;
LABEL_93:
      v47 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_94;
    }
    v31 = v120;
LABEL_94:
    v48 = *((_DWORD *)v31 + 32);
    if ( v48 < 0 || *((_QWORD *)v31 + 19) || *((_QWORD *)v31 + 20) )
    {
      if ( v47 != &WPP_GLOBAL_Control && (*((_BYTE *)v47 + 28) & 1) != 0 && *((_BYTE *)v47 + 25) >= 3u )
      {
        WPP_SF_DDZZDiiiiid(
          (TRACEHANDLE)v47[2],
          *(_DWORD *)(**(_QWORD **)a1 + 36LL),
          *(_QWORD *)(*(_QWORD *)a1 + 64LL),
          (__int64)v31 + 88,
          *((_DWORD *)v31 + 31),
          *((_QWORD *)v31 + 21),
          *((_QWORD *)v31 + 17),
          *((_QWORD *)v31 + 18),
          *((_QWORD *)v31 + 19),
          *((_QWORD *)v31 + 20),
          v48);
        v31 = v120;
      }
      *(_BYTE *)(a1 + 1496) = 1;
    }
    EventWriteScrubDataOutput(*(_QWORD *)(a1 + 8), *(_QWORD *)a1, (__int64)v31 + 88, v122, (__int64)v31 + 120, v41);
    *((_DWORD *)v120 + 32) = 0;
    *((_QWORD *)v120 + 18) = 0;
    *((_QWORD *)v120 + 17) = 0;
    *((_QWORD *)v120 + 19) = 0;
    *((_QWORD *)v120 + 20) = 0;
    v49 = v120;
    if ( (*((_BYTE *)v120 + 124) & 1) == 0 )
    {
      v103 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v104 = *(_QWORD *)(a1 + 1424);
        if ( v104 > (unsigned __int64)v120
          || (v49 = v120,
              v103 = WPP_GLOBAL_Control,
              (unsigned __int64)v120 > v104 + 35024LL * (*(_DWORD *)(a1 + 1372) - 1)) )
        {
          LOBYTE(v105) = ((unsigned __int64)v49 - *(_QWORD *)(a1 + 1416)) / 0x88D0 + 100;
        }
        else
        {
          v105 = ((unsigned __int64)v120 - *(_QWORD *)(a1 + 1424)) / 0x88D0;
        }
        WPP_SF_DDZdZqi(
          v103[2],
          *(_DWORD *)(**(_QWORD **)a1 + 36LL),
          *(_QWORD *)(*(_QWORD *)a1 + 64LL),
          v105,
          (__int64)v120 + 88,
          (char)FileHandle,
          InputBufferLength);
      }
      v116 = 0;
      v29 = 0;
      break;
    }
    v50 = 1040;
    if ( (*((_DWORD *)v120 + 31) & 0x40000) != 0 && *((unsigned __int16 *)v120 + 88) <= 0x410u )
      v50 = *((unsigned __int16 *)v120 + 88);
    if ( *(_DWORD *)(a1 + 120) != v50 || memcmp_0((const void *)(a1 + 124), (char *)v120 + 312, v50) )
    {
      v56 = 4;
      if ( v50 < 4 )
        v56 = v50;
      *(_DWORD *)(a1 + 120) = v56;
      memcpy_0((void *)(a1 + 124), (char *)v49 + 312, v56);
      v112 = 0;
LABEL_118:
      v54 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_119;
    }
    v53 = i + 1;
    v112 = v53;
    if ( v53 != 1 )
    {
      if ( v53 > 0x20 )
      {
        v29 = -1073740757;
        v116 = -1073740757;
        break;
      }
      goto LABEL_118;
    }
    v54 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_128;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v55 = (char)FileHandle;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_DDZqD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v51,
          v52,
          *(_DWORD *)(**(_QWORD **)a1 + 16LL),
          *(_DWORD *)(**(_QWORD **)a1 + 36LL),
          *(_QWORD *)(*(_QWORD *)a1 + 64LL),
          (char)FileHandle,
          1);
        v49 = v120;
        v54 = (PVOID *)WPP_GLOBAL_Control;
      }
      goto LABEL_120;
    }
LABEL_119:
    v55 = (char)FileHandle;
LABEL_120:
    if ( v54 != &WPP_GLOBAL_Control && (*((_BYTE *)v54 + 28) & 1) != 0 && *((_BYTE *)v54 + 25) >= 5u )
    {
      v57 = (__int64)v49 + 88;
      v58 = *(_QWORD *)(a1 + 1424);
      if ( v58 > (unsigned __int64)v49
        || (v49 = v120,
            v54 = (PVOID *)WPP_GLOBAL_Control,
            (unsigned __int64)v120 > v58 + 35024LL * (*(_DWORD *)(a1 + 1372) - 1)) )
      {
        LOBYTE(v59) = ((unsigned __int64)v49 - *(_QWORD *)(a1 + 1416)) / 0x88D0 + 100;
      }
      else
      {
        v59 = ((unsigned __int64)v120 - *(_QWORD *)(a1 + 1424)) / 0x88D0;
      }
      WPP_SF_DDZdZq(
        (TRACEHANDLE)v54[2],
        *(_DWORD *)(**(_QWORD **)a1 + 36LL),
        *(_QWORD *)(*(_QWORD *)a1 + 64LL),
        v59,
        v57,
        v55);
      v49 = v120;
    }
LABEL_128:
    CScrub::_Checkpoint((RTL_SRWLOCK *)a1, v49, 0, 0, 0);
    ++*((_QWORD *)v120 + 192);
    v60 = v120;
    v61 = *((_QWORD *)v120 + 23);
    v62 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v63 = *(_QWORD *)(a1 + 1424);
      if ( v63 > (unsigned __int64)v120
        || (v60 = v120, v62 = WPP_GLOBAL_Control, (unsigned __int64)v120 > v63 + 35024LL * (*(_DWORD *)(a1 + 1372) - 1)) )
      {
        LODWORD(v64) = ((unsigned __int64)v60 - *(_QWORD *)(a1 + 1416)) / 0x88D0 + 100;
      }
      else
      {
        v64 = ((unsigned __int64)v120 - *(_QWORD *)(a1 + 1424)) / 0x88D0;
      }
      WPP_SF_DDZdii(
        v62[2],
        137,
        v64,
        *(_DWORD *)(**(_QWORD **)a1 + 16LL),
        *(_DWORD *)(**(_QWORD **)a1 + 36LL),
        *(_QWORD *)(*(_QWORD *)a1 + 64LL),
        v64,
        v61,
        InputBufferLength);
      v60 = v120;
    }
    memset_0((char *)v60 + 120, 0, 0xC0u);
    *((_DWORD *)v120 + 30) = 1232;
    *((_DWORD *)v120 + 31) = 65;
    *((_DWORD *)v120 + 32) = *(_DWORD *)(*(_QWORD *)(a1 + 8) + 32LL);
    v65 = a5;
    if ( !a5 || !*v15 )
    {
      *((_QWORD *)v120 + 20) = 0;
      *((_QWORD *)v120 + 19) = 0;
    }
    if ( v111 == 1 )
    {
      *((_DWORD *)v120 + 31) |= 2u;
    }
    else if ( **(_DWORD **)(a1 + 8) == 3 )
    {
      *((_DWORD *)v120 + 31) |= 4u;
    }
    if ( *(char *)(a1 + 1260) < 0 )
      *((_DWORD *)v120 + 31) |= 8u;
    LODWORD(InputBufferLength) = v50 + 192;
    if ( !v107 )
      goto LABEL_236;
    v114 = 0;
    lambda_d2dfc46f77b2634b1ca0c267f611ece0_::_lambda_d2dfc46f77b2634b1ca0c267f611ece0_(v118, a1, &v120);
    if ( *v15 )
    {
      v67 = v108;
      if ( v61 >= v108 )
      {
        v68 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v69 = *(_QWORD *)(a1 + 1424);
          v70 = v120;
          if ( v69 > (unsigned __int64)v120
            || (v70 = v120,
                v68 = WPP_GLOBAL_Control,
                (unsigned __int64)v120 > v69 + 35024LL * (*(_DWORD *)(a1 + 1372) - 1)) )
          {
            LODWORD(v71) = ((unsigned __int64)v70 - *(_QWORD *)(a1 + 1416)) / 0x88D0 + 100;
          }
          else
          {
            v71 = ((unsigned __int64)v120 - *(_QWORD *)(a1 + 1424)) / 0x88D0;
          }
          WPP_SF_DDZdii(
            v68[2],
            140,
            v71,
            *(_DWORD *)(**(_QWORD **)a1 + 16LL),
            *(_DWORD *)(**(_QWORD **)a1 + 36LL),
            *(_QWORD *)(*(_QWORD *)a1 + 64LL),
            v71,
            v61,
            v108);
        }
        v61 = lambda_65930a2d28a209420b1c221258c6fb24_::operator()(v68, *v15, v66, &v113);
        v72 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
        {
          v67 = v113;
          v108 = v113;
        }
        else
        {
          v67 = v113;
          v108 = v113;
          v73 = *(_QWORD *)(a1 + 1424);
          v74 = v120;
          if ( v73 > (unsigned __int64)v120
            || (v74 = v120,
                v72 = WPP_GLOBAL_Control,
                (unsigned __int64)v120 > v73 + 35024LL * (*(_DWORD *)(a1 + 1372) - 1)) )
          {
            LODWORD(v75) = ((unsigned __int64)v74 - *(_QWORD *)(a1 + 1416)) / 0x88D0 + 100;
          }
          else
          {
            v75 = ((unsigned __int64)v120 - *(_QWORD *)(a1 + 1424)) / 0x88D0;
          }
          WPP_SF_DDZdii(
            v72[2],
            141,
            v75,
            *(_DWORD *)(**(_QWORD **)a1 + 16LL),
            *(_DWORD *)(**(_QWORD **)a1 + 36LL),
            *(_QWORD *)(*(_QWORD *)a1 + 64LL),
            v75,
            v61,
            v113);
        }
      }
LABEL_164:
      v76 = v109;
      goto LABEL_165;
    }
    v76 = v109;
    if ( v109 > v61 && v109 - v61 >= 0x46666666 && CScrub::_TryReservingIdlingThread((RTL_SRWLOCK *)a1, &v114) )
    {
      v77 = v114;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v78 = *(_QWORD *)(a1 + 1424);
        if ( v78 > (unsigned __int64)v114 || (unsigned __int64)v114 > v78 + 35024LL * (*(_DWORD *)(a1 + 1372) - 1) )
          LOBYTE(v79) = ((unsigned __int64)v114 - *(_QWORD *)(a1 + 1416)) / 0x88D0 + 100;
        else
          v79 = ((unsigned __int64)v114 - *(_QWORD *)(a1 + 1424)) / 0x88D0;
        v80 = *(_QWORD *)(a1 + 1424);
        v81 = v120;
        if ( v80 > (unsigned __int64)v120
          || (v81 = v120, (unsigned __int64)v120 > v80 + 35024LL * (*(_DWORD *)(a1 + 1372) - 1)) )
        {
          LOBYTE(v82) = ((unsigned __int64)v81 - *(_QWORD *)(a1 + 1416)) / 0x88D0 + 100;
        }
        else
        {
          v82 = ((unsigned __int64)v120 - *(_QWORD *)(a1 + 1424)) / 0x88D0;
        }
        WPP_SF_DDZdd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          142,
          v80,
          *(_DWORD *)(**(_QWORD **)a1 + 16LL),
          *(_DWORD *)(**(_QWORD **)a1 + 36LL),
          *(_QWORD *)(*(_QWORD *)a1 + 64LL),
          v82,
          v79);
      }
      v83 = operator new(0x18u);
      if ( v83 )
      {
        *(_OWORD *)v83 = 0;
        v83[2] = 0;
      }
      else
      {
        v83 = 0;
      }
      v110[0] = v83;
      v84 = (__int64 *)operator new(0x50u);
      if ( v84 )
        memset_0(v84, 0, 0x50u);
      else
        v84 = 0;
      if ( v83 && v84 )
      {
        _InterlockedIncrement64((volatile signed __int64 *)(a1 + 1488));
        *(_OWORD *)v83 = 0;
        v83[2] = 0;
        ++*((_DWORD *)v83 + 3);
        _SCRUB_FILE_ENTRY::operator=(v84, a5);
        v84[7] = (__int64)v83;
        CHandleT<void *,NtHandleTrait>::AddRef(v84[6]);
        v108 = v61 + 0x40000000;
        v84[8] = v61 + 0x40000000;
        v113 = v61 + 0x40000000;
        v84[9] = 0x40000000;
        *v83 = v61 + 0x80000000;
        v85 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v86 = (unsigned __int64)v120;
          v87 = *(_QWORD *)(a1 + 1424);
          if ( v87 > (unsigned __int64)v120
            || (v86 = (unsigned __int64)v120,
                v85 = WPP_GLOBAL_Control,
                (unsigned __int64)v120 > v87 + 35024LL * (*(_DWORD *)(a1 + 1372) - 1)) )
          {
            LOBYTE(v86) = (v86 - *(_QWORD *)(a1 + 1416)) / 0x88D0 + 100;
          }
          else
          {
            v86 = ((unsigned __int64)v120 - *(_QWORD *)(a1 + 1424)) / 0x88D0;
          }
          WPP_SF_DDZdiZ(
            v85[2],
            *(_DWORD *)(**(_QWORD **)a1 + 36LL),
            *(_QWORD *)(*(_QWORD *)a1 + 64LL),
            v86,
            v84[8],
            (__int64)v120 + 88);
        }
        ++*((_DWORD *)v83 + 3);
        *v15 = v83;
        v83 = 0;
        v110[0] = v84;
        lambda_d2dfc46f77b2634b1ca0c267f611ece0_::operator()(v118, v110, v77);
      }
      else
      {
        CScrub::_ReleaseReservedIdlingThread((RTL_SRWLOCK *)a1, v77, 0);
        if ( v84 )
        {
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v84 + 5);
          operator delete(v84);
        }
      }
      operator delete(v83);
      v67 = v108;
      v65 = a5;
      goto LABEL_164;
    }
    v67 = v108;
LABEL_165:
    if ( v67 == -1 )
    {
      *((_QWORD *)v120 + 20) = 0;
    }
    else
    {
      *((_QWORD *)v120 + 19) = v61;
      *((_QWORD *)v120 + 20) = v67 - v61;
    }
    v88 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v89 = (unsigned __int64)v120;
      v90 = *(_QWORD *)(a1 + 1424);
      if ( v90 > (unsigned __int64)v120
        || (v89 = (unsigned __int64)v120,
            v88 = WPP_GLOBAL_Control,
            (unsigned __int64)v120 > v90 + 35024LL * (*(_DWORD *)(a1 + 1372) - 1)) )
      {
        LODWORD(v89) = (v89 - *(_QWORD *)(a1 + 1416)) / 0x88D0 + 100;
      }
      else
      {
        v89 = ((unsigned __int64)v120 - *(_QWORD *)(a1 + 1424)) / 0x88D0;
      }
      WPP_SF_DDZdiii(
        v88[2],
        v89,
        v90,
        *(_DWORD *)(**(_QWORD **)a1 + 16LL),
        *(_DWORD *)(**(_QWORD **)a1 + 36LL),
        *(_QWORD *)(*(_QWORD *)a1 + 64LL),
        v89,
        v61,
        v67,
        *((_QWORD *)v120 + 20));
    }
    if ( *v15 )
    {
      v91 = _InterlockedExchangeAdd64(*v15, 0);
      v92 = 0;
      while ( v76 > v91 && v76 - v91 >= 0x6666666 && CScrub::_TryReservingIdlingThread((RTL_SRWLOCK *)a1, &v114) )
      {
        v93 = operator new(0x50u);
        if ( !v93 )
        {
          CScrub::_ReleaseReservedIdlingThread((RTL_SRWLOCK *)a1, v114, 0);
LABEL_235:
          v16 = v119;
          goto LABEL_237;
        }
        memset_0(v93, 0, 0x50u);
        v110[0] = 0;
        _SCRUB_FILE_ENTRY::operator=(v93, v65);
        v94 = *v15;
        v93[7] = *v15;
        ++*((_DWORD *)v94 + 3);
        CHandleT<void *,NtHandleTrait>::AddRef(v93[6]);
        v97 = lambda_65930a2d28a209420b1c221258c6fb24_::operator()(v95, *v15, v96, v110);
        v93[8] = v97;
        v93[9] = 0x40000000;
        v98 = v114;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v99 = *(_QWORD *)(a1 + 1424);
          if ( v99 > (unsigned __int64)v114 || (unsigned __int64)v114 > v99 + 35024LL * (*(_DWORD *)(a1 + 1372) - 1) )
            LOBYTE(v100) = ((unsigned __int64)v114 - *(_QWORD *)(a1 + 1416)) / 0x88D0 + 100;
          else
            v100 = ((unsigned __int64)v114 - *(_QWORD *)(a1 + 1424)) / 0x88D0;
          v101 = *(_QWORD *)(a1 + 1424);
          v102 = (unsigned __int64)v120;
          if ( v101 > (unsigned __int64)v120
            || (v102 = (unsigned __int64)v120, (unsigned __int64)v120 > v101 + 35024LL * (*(_DWORD *)(a1 + 1372) - 1)) )
          {
            LODWORD(v102) = (v102 - *(_QWORD *)(a1 + 1416)) / 0x88D0 + 100;
          }
          else
          {
            v102 = ((unsigned __int64)v120 - *(_QWORD *)(a1 + 1424)) / 0x88D0;
          }
          WPP_SF_DDZddi(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v102,
            v101,
            *(_DWORD *)(**(_QWORD **)a1 + 16LL),
            *(_DWORD *)(**(_QWORD **)a1 + 36LL),
            *(_QWORD *)(*(_QWORD *)a1 + 64LL),
            v102,
            v100,
            v97);
        }
        v110[0] = v93;
        lambda_d2dfc46f77b2634b1ca0c267f611ece0_::operator()(v118, v110, v98);
        if ( v91 > 0xFFFFFFFFBFFFFFFFuLL )
          goto LABEL_235;
        if ( (unsigned int)++v92 >= *(_DWORD *)(a1 + 1372) )
          goto LABEL_235;
        v91 += 0x40000000LL;
        v65 = a5;
        v76 = v109;
      }
    }
LABEL_236:
    v16 = v119;
LABEL_237:
    v26 = NtFsControlFile(
            FileHandle,
            *((HANDLE *)v120 + 9),
            0,
            0,
            &IoStatusBlock,
            0x902B0u,
            (char *)v120 + 120,
            InputBufferLength,
            (char *)v120 + 120,
            0x550u);
    LOBYTE(InputBufferLength) = v108;
    v14 = a5;
  }
  CHResultImp::~CHResultImp((CHResultImp *)&v115);
  return (unsigned int)v29;
}

```

## disassembly

```asm
0x180022450  mov     rax, rsp
0x180022453  mov     [rax+20h], r9d
0x180022457  mov     [rax+18h], r8
0x18002245b  mov     [rax+10h], rdx
0x18002245f  push    rbp
0x180022460  push    rbx
0x180022461  push    rsi
0x180022462  push    rdi
0x180022463  push    r12
0x180022465  push    r13
0x180022467  push    r14
0x180022469  push    r15
0x18002246b  lea     rbp, [rax-57h]
0x18002246f  sub     rsp, 0E8h
0x180022476  mov     r15, r8
0x180022479  mov     rbx, rdx
0x18002247c  mov     rdi, rcx
0x18002247f  mov     r10d, cs:_tls_index
0x180022486  mov     rax, gs:58h
0x18002248f  mov     r11, [rax+r10*8]
0x180022493  mov     eax, 10h
0x180022498  lea     r8, aCscrubScrubdat; "CScrub::ScrubData"
0x18002249f  mov     [rax+r11], r8
0x1800224a3  mov     [rbp+4Fh+var_70], r8
0x1800224a7  mov     edx, 8
0x1800224ac  mov     r9d, 1
0x1800224b2  add     [rdx+r11], r9w
0x1800224b7  movzx   edx, word ptr [rdx+r11]
0x1800224bc  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x1800224c3  movzx   eax, cx
0x1800224c6  cmp     dx, cx
0x1800224c9  cmovb   ax, dx
0x1800224cd  mov     word ptr [rbp+4Fh+var_98], ax
0x1800224d1  cmovb   cx, dx
0x1800224d5  mov     word ptr [rbp+4Fh+var_98+2], cx
0x1800224d9  xor     eax, eax
0x1800224db  mov     dword ptr [rbp+4Fh+var_98+4], eax
0x1800224de  mov     rax, cs:off_180047060; "                                       "...
0x1800224e5  mov     [rbp+4Fh+var_90], rax
0x1800224e9  lea     rdx, WPP_GLOBAL_Control
0x1800224f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800224f7  cmp     rcx, rdx
0x1800224fa  jz      short loc_18002252F
0x1800224fc  test    [rcx+1Ch], r9b
0x180022500  jz      short loc_18002252F
0x180022502  cmp     byte ptr [rcx+19h], 5
0x180022506  jb      short loc_18002252F
0x180022508  lea     edx, [r9+0Ch]
0x18002250c  mov     [rsp+120h+IoStatusBlock], r8; __int64
0x180022511  lea     r9, [rbp+4Fh+var_98]
0x180022515  mov     rcx, [rcx+10h]; LoggerHandle
0x180022519  call    WPP_SF_aZs
0x18002251e  mov     rbx, [rbp+4Fh+arg_8]
0x180022522  mov     r9d, 1
0x180022528  lea     rdx, WPP_GLOBAL_Control
0x18002252f  mov     dword ptr [rbx+7Ch], 40h ; '@'
0x180022536  mov     rax, [rdi+8]
0x18002253a  mov     ecx, [rax+20h]
0x18002253d  mov     rax, [rbp+4Fh+arg_8]
0x180022541  mov     [rax+80h], ecx
0x180022547  xor     ecx, ecx
0x180022549  mov     rax, [rbp+4Fh+arg_8]
0x18002254d  mov     [rax+98h], rcx
0x180022554  mov     rax, [rbp+4Fh+arg_8]
0x180022558  mov     [rax+0A0h], rcx
0x18002255f  xorps   xmm0, xmm0
0x180022562  movups  xmmword ptr [rbp+4Fh+var_60], xmm0
0x180022566  mov     [rbp+4Fh+var_A0], rcx
0x18002256a  or      r12, 0FFFFFFFFFFFFFFFFh
0x18002256e  mov     [rbp+4Fh+var_A8], r12
0x180022572  mov     [rbp+4Fh+var_80], r12
0x180022576  mov     [rbp+4Fh+var_B0], cl
0x180022579  mov     rax, [rdi+8]
0x18002257d  mov     ebx, [rax+8]
0x180022580  mov     [rbp+4Fh+var_88], ebx
0x180022583  mov     rsi, [rbp+4Fh+arg_20]
0x180022587  lea     r13, [rsi+38h]
0x18002258b  test    rsi, rsi
0x18002258e  jz      short loc_18002259E
0x180022590  cmp     [r13+0], rcx
0x180022594  jz      short loc_18002259E
0x180022596  mov     r14b, cl
0x180022599  mov     [rbp+4Fh+arg_0], cl
0x18002259c  jmp     short loc_1800225C4
0x18002259e  mov     r14b, r9b
0x1800225a1  mov     [rbp+4Fh+arg_0], r9b
0x1800225a5  test    rsi, rsi
0x1800225a8  jz      short loc_1800225B2
0x1800225aa  cmp     [r13+0], rcx
0x1800225ae  jnz     short loc_1800225C4
0x1800225b0  jmp     short loc_1800225B9
0x1800225b2  mov     r14b, r9b
0x1800225b5  mov     [rbp+4Fh+arg_0], r9b
0x1800225b9  mov     rax, [rbp+4Fh+arg_8]
0x1800225bd  add     [rax+5F8h], r9
0x1800225c4  mov     rax, [rbp+4Fh+arg_8]
0x1800225c8  add     [rax+600h], r9
0x1800225cf  mov     r11, 77C150CFB348283Bh
0x1800225d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800225e0  cmp     rcx, rdx
0x1800225e3  jz      loc_180022699
0x1800225e9  test    [rcx+1Ch], r9b
0x1800225ed  jz      loc_180022699
0x1800225f3  cmp     byte ptr [rcx+19h], 4
0x1800225f7  jb      loc_180022699
0x1800225fd  mov     rdx, [rbp+4Fh+arg_8]
0x180022601  lea     r10, [rdx+58h]
0x180022605  mov     r8, [rdi+590h]
0x18002260c  cmp     r8, rdx
0x18002260f  ja      short loc_18002264C
0x180022611  mov     eax, [rdi+55Ch]
0x180022617  sub     eax, r9d
0x18002261a  cdqe
0x18002261c  imul    rcx, rax, 88D0h
0x180022623  add     rcx, r8
0x180022626  mov     rdx, [rbp+4Fh+arg_8]
0x18002262a  cmp     rdx, rcx
0x18002262d  mov     rcx, cs:WPP_GLOBAL_Control
0x180022634  ja      short loc_18002264C
0x180022636  sub     rdx, [rdi+590h]
0x18002263d  mov     rax, r11
0x180022640  mul     rdx
0x180022643  mov     r8, rdx
0x180022646  shr     r8, 0Eh
0x18002264a  jmp     short loc_180022661
0x18002264c  sub     rdx, [rdi+588h]
0x180022653  mov     rax, r11
0x180022656  mul     rdx
0x180022659  shr     rdx, 0Eh
0x18002265d  lea     r8d, [rdx+64h]
0x180022661  mov     rax, [rdi]
0x180022664  mov     r9, [rax]
0x180022667  mov     edx, 7Fh
0x18002266c  mov     [rsp+120h+OutputBuffer], r15; char
0x180022671  mov     qword ptr [rsp+120h+InputBufferLength], r10; __int64
0x180022676  mov     dword ptr [rsp+120h+InputBuffer], r8d; char
0x18002267b  mov     rax, [rax+40h]
0x18002267f  mov     qword ptr [rsp+120h+FsControlCode], rax; __int64
0x180022684  mov     eax, [r9+24h]
0x180022688  mov     dword ptr [rsp+120h+IoStatusBlock], eax; char
0x18002268c  mov     r9d, [r9+10h]
0x180022690  mov     rcx, [rcx+10h]; LoggerHandle
0x180022694  call    WPP_SF_DDZdZq
0x180022699  lea     rcx, [rdi+7Ch]; void *
0x18002269d  xor     edx, edx; Val
0x18002269f  mov     r8d, 410h; Size
0x1800226a5  call    memset_0
0x1800226aa  mov     rax, [rbp+4Fh+arg_8]
0x1800226ae  mov     dword ptr [rax+78h], 4D0h
0x1800226b5  cmp     ebx, 1
0x1800226b8  jnz     loc_1800227DC
0x1800226be  mov     rax, [rbp+4Fh+arg_8]
0x1800226c2  or      dword ptr [rax+7Ch], 2
0x1800226c6  test    rsi, rsi
0x1800226c9  jz      loc_1800227ED
0x1800226cf  cmp     qword ptr [r13+0], 0
0x1800226d4  jz      loc_1800227ED
0x1800226da  mov     rcx, [rsi+40h]
0x1800226de  mov     rax, [rbp+4Fh+arg_8]
0x1800226e2  mov     [rax+98h], rcx
0x1800226e9  mov     rcx, [rsi+48h]
0x1800226ed  mov     rax, [rbp+4Fh+arg_8]
0x1800226f1  mov     [rax+0A0h], rcx
0x1800226f8  mov     r10, [rsi+40h]
0x1800226fc  mov     r12, [rsi+48h]
0x180022700  add     r12, r10
0x180022703  mov     [rbp+4Fh+var_A8], r12
0x180022707  mov     [rbp+4Fh+var_80], r12
0x18002270b  mov     rcx, cs:WPP_GLOBAL_Control
0x180022712  lea     rax, WPP_GLOBAL_Control
0x180022719  cmp     rcx, rax
0x18002271c  jz      loc_1800227ED
0x180022722  test    [rcx+1Ch], bl
0x180022725  jz      loc_1800227ED
0x18002272b  cmp     byte ptr [rcx+19h], 4
0x18002272f  jb      loc_1800227ED
0x180022735  mov     r8, [rdi+590h]
0x18002273c  mov     rdx, [rbp+4Fh+arg_8]
0x180022740  cmp     r8, rdx
0x180022743  ja      short loc_180022786
0x180022745  mov     eax, [rdi+55Ch]
0x18002274b  dec     eax
0x18002274d  cdqe
0x18002274f  imul    rcx, rax, 88D0h
0x180022756  add     rcx, r8
0x180022759  mov     rdx, [rbp+4Fh+arg_8]
0x18002275d  cmp     rdx, rcx
0x180022760  mov     rcx, cs:WPP_GLOBAL_Control
0x180022767  ja      short loc_180022786
0x180022769  sub     rdx, [rdi+590h]
0x180022770  mov     rax, 77C150CFB348283Bh
0x18002277a  mul     rdx
0x18002277d  mov     r8, rdx
0x180022780  shr     r8, 0Eh
0x180022784  jmp     short loc_1800227A2
0x180022786  sub     rdx, [rdi+588h]
0x18002278d  mov     rax, 77C150CFB348283Bh
0x180022797  mul     rdx
0x18002279a  shr     rdx, 0Eh
0x18002279e  lea     r8d, [rdx+64h]
0x1800227a2  mov     rax, [rdi]
0x1800227a5  mov     r9, [rax]
0x1800227a8  mov     edx, 80h
0x1800227ad  mov     [rsp+120h+OutputBuffer], r12
0x1800227b2  mov     qword ptr [rsp+120h+InputBufferLength], r10
0x1800227b7  mov     dword ptr [rsp+120h+InputBuffer], r8d
0x1800227bc  mov     rax, [rax+40h]
0x1800227c0  mov     qword ptr [rsp+120h+FsControlCode], rax
0x1800227c5  mov     eax, [r9+24h]
0x1800227c9  mov     dword ptr [rsp+120h+IoStatusBlock], eax
0x1800227cd  mov     r9d, [r9+10h]
0x1800227d1  mov     rcx, [rcx+10h]
0x1800227d5  call    WPP_SF_DDZdii
0x1800227da  jmp     short loc_1800227ED
0x1800227dc  mov     rax, [rdi+8]
0x1800227e0  cmp     dword ptr [rax], 3
0x1800227e3  jnz     short loc_1800227ED
0x1800227e5  mov     rax, [rbp+4Fh+arg_8]
0x1800227e9  or      dword ptr [rax+7Ch], 4
0x1800227ed  test    byte ptr [rdi+4ECh], 80h
0x1800227f4  jz      short loc_1800227FE
0x1800227f6  mov     rax, [rbp+4Fh+arg_8]
0x1800227fa  or      dword ptr [rax+7Ch], 8
0x1800227fe  mov     rdx, [rbp+4Fh+arg_8]
0x180022802  lea     rax, [rdx+78h]
0x180022806  mov     [rsp+120h+OutputBufferLength], 550h; OutputBufferLength
0x18002280e  mov     [rsp+120h+OutputBuffer], rax; OutputBuffer
0x180022813  mov     [rsp+120h+InputBufferLength], 0C0h; InputBufferLength
0x18002281b  mov     [rsp+120h+InputBuffer], rax; InputBuffer
0x180022820  mov     [rsp+120h+FsControlCode], 902B0h; FsControlCode
0x180022828  lea     rax, [rbp+4Fh+var_60]
0x18002282c  mov     [rsp+120h+IoStatusBlock], rax; IoStatusBlock
0x180022831  xor     r9d, r9d; ApcContext
0x180022834  xor     r8d, r8d; ApcRoutine
0x180022837  mov     rdx, [rdx+48h]; Event
0x18002283b  mov     rcx, r15; FileHandle
0x18002283e  call    cs:__imp_NtFsControlFile
0x180022844  xor     r15d, r15d
0x180022847  mov     edx, eax; struct _SCRUB_THREAD_CONTEXT *
0x180022849  mov     rax, [rbp+4Fh+arg_8]
0x18002284d  mov     rcx, [rax+48h]
0x180022851  mov     qword ptr [rsp+120h+FsControlCode], rcx; Handle
0x180022856  mov     dword ptr [rsp+120h+IoStatusBlock], edx; int
0x18002285a  lea     r9, [rbp+4Fh+var_60]; struct _IO_STATUS_BLOCK *
0x18002285e  mov     r8, [rbp+4Fh+FileHandle]; void *
0x180022862  mov     rcx, rdi; this
0x180022865  call    ?_ScrubWaitIo@CScrub@@AEAAJPEAU_SCRUB_THREAD_CONTEXT@@PEAXPEAU_IO_STATUS_BLOCK@@J1@Z; CScrub::_ScrubWaitIo(_SCRUB_THREAD_CONTEXT *,void *,_IO_STATUS_BLOCK *,long,void *)
0x18002286a  mov     ebx, eax
0x18002286c  mov     [rbp+4Fh+var_68], eax
0x18002286f  cmp     eax, 0D000010Ah
0x180022874  jz      loc_180023A1D
0x18002287a  test    eax, eax
0x18002287c  js      loc_1800239A9
0x180022882  mov     rcx, [rbp+4Fh+arg_8]
0x180022886  add     rcx, 78h ; 'x'; struct _SCRUB_DATA_OUTPUT *
0x18002288a  mov     rdx, [rbp+4Fh+var_60.Information]; unsigned __int64
0x18002288e  call    ?ValidateScrubOutputData@@YAJPEBU_SCRUB_DATA_OUTPUT@@_K@Z; ValidateScrubOutputData(_SCRUB_DATA_OUTPUT const *,unsigned __int64)
0x180022893  mov     ebx, eax
0x180022895  mov     [rbp+4Fh+var_68], eax
0x180022898  xor     ecx, ecx
0x18002289a  test    eax, eax
0x18002289c  js      loc_180023A1D
0x1800228a2  test    rsi, rsi
0x1800228a5  jz      short loc_1800228B9
0x1800228a7  mov     rax, [r13+0]
0x1800228ab  test    rax, rax
0x1800228ae  jz      short loc_1800228B9
0x1800228b0  cmp     [rax+10h], cl
0x1800228b3  jnz     loc_180023A1D
0x1800228b9  mov     r10, [rbp+4Fh+arg_8]
0x1800228bd  mov     rax, [r10+98h]
0x1800228c4  xor     ebx, ebx
0x1800228c6  test    rax, rax
0x1800228c9  jz      short loc_1800228D6
0x1800228cb  add     [r10+5D0h], rax
0x1800228d2  mov     r10, [rbp+4Fh+arg_8]
0x1800228d6  mov     rax, [r10+0A0h]
0x1800228dd  test    rax, rax
0x1800228e0  jz      short loc_1800228ED
0x1800228e2  add     [r10+5D8h], rax
0x1800228e9  mov     r10, [rbp+4Fh+arg_8]
0x1800228ed  test    dword ptr [rdi+4ECh], 20000000h
0x1800228f7  jz      loc_1800229DD
0x1800228fd  mov     rax, [r10+0D8h]
0x180022904  add     [r10+608h], rax
0x18002290b  mov     rcx, [rbp+4Fh+arg_8]
0x18002290f  mov     rax, [rcx+0E0h]
0x180022916  add     [rcx+610h], rax
0x18002291d  mov     rcx, [rbp+4Fh+arg_8]
0x180022921  test    r14b, r14b
0x180022924  jz      short loc_180022982
0x180022926  mov     rdx, [rcx+618h]
0x18002292d  mov     rax, [rcx+0E8h]
0x180022934  test    rdx, rdx
0x180022937  jz      short loc_180022949
0x180022939  test    rax, rax
0x18002293c  jz      short loc_180022954
0x18002293e  cmp     rax, rdx
0x180022941  jz      short loc_180022954
0x180022943  add     rax, rdx
  ... truncated ...
```
