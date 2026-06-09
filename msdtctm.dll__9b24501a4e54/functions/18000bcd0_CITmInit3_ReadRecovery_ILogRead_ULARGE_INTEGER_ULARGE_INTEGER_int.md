# CITmInit3::ReadRecovery(ILogRead *,_ULARGE_INTEGER *,_ULARGE_INTEGER *,int *)

- ea: `0x18000bcd0`
- end: `0x18000d08a`
- name: `?ReadRecovery@CITmInit3@@AEAAHPEAUILogRead@@PEAT_ULARGE_INTEGER@@1PEAH@Z`
- size: `5050`
- prototype: `__int64 __fastcall(CITmInit3 *__hidden this, struct ILogRead *, union _ULARGE_INTEGER *, union _ULARGE_INTEGER *, void *Block)`
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180004120`

## callees

- `0x18000bcd0`
- `0x18000f430`
- `0x180015230`
- `0x180018bac`
- `0x18001a500`
- `0x18001cda8`
- `0x1800240b0`
- `0x1800240f0`
- `0x1800240fc`
- `0x1800392ac`
- `0x18003f4fc`
- `0x1800437b4`
- `0x180048520`
- `0x18004a7f0`
- `0x18004bbc0`
- `0x18005a29c`
- `0x18005c94c`
- `0x1800677ac`
- `0x18006ccc4`
- `0x18006e904`
- `0x18006eb84`
- `0x18006ed68`
- `0x18007338c`
- `0x18007863c`
- `0x18007bf5c`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c789`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c85c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c926`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ca9e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c789`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c85c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c926`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ca9e`

## string_xrefs

- `0x18000cb17`: `com\complus\dtc\dtc\tm\src\tminit.cpp`
- `0x18000cb2a`: `com\complus\dtc\dtc\tm\src\tminit.cpp`
- `0x18000cb3d`: `com\complus\dtc\dtc\tm\src\tminit.cpp`
- `0x18000cb50`: `com\complus\dtc\dtc\tm\src\tminit.cpp`
- `0x18000cc0d`: `com\complus\dtc\dtc\tm\src\tminit.cpp`
- `0x18000cea6`: `com\complus\dtc\dtc\tm\src\tminit.cpp`
- `0x18000cfc3`: `com\complus\dtc\dtc\tm\src\tminit.cpp`
- `0x18000c58c`: `com\complus\dtc\dtc\tm\src\tmtrace.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall CITmInit3::ReadRecovery(
        CITmInit3 *this,
        struct ILogRead *a2,
        union _ULARGE_INTEGER *a3,
        union _ULARGE_INTEGER *a4,
        void **Block)
{
  void **v8; // r14
  int v9; // eax
  _QWORD *v10; // rax
  _QWORD *v11; // rbx
  unsigned int v12; // eax
  CTmTrace *v13; // rcx
  __int64 v14; // rax
  void **v15; // rsi
  _QWORD *v16; // rax
  CTmTrace *v17; // rcx
  __int64 v18; // rax
  void ***v19; // rcx
  void **v20; // rsi
  void *v21; // rcx
  __int64 v22; // rax
  void **v23; // rsi
  _QWORD *v24; // rax
  __int64 v25; // rax
  char *v26; // rcx
  __int64 v27; // rax
  __int64 v28; // rax
  void **v29; // rsi
  _QWORD *v30; // rax
  char *v31; // rcx
  __int64 v32; // rax
  __int64 v33; // rax
  int v35; // eax
  char *v36; // r13
  _DWORD *v37; // rbx
  char *v38; // rdi
  unsigned int v39; // esi
  char *v40; // r14
  _DWORD *v41; // r15
  unsigned int v42; // r12d
  char *v43; // rdx
  unsigned int *v44; // r8
  __int64 v45; // rcx
  BOOL v46; // edi
  CTmTrace *v47; // rcx
  CTx *v48; // rax
  CTmTrace *v49; // rcx
  CGatewaySuperior *v50; // rax
  CGatewaySuperior *v51; // rax
  CDtcLuSuperior *v52; // rax
  CDtcLuSuperior *v53; // rcx
  CXaSuperior *v54; // rax
  CXaSuperior *v55; // rcx
  CTxSuperior *v56; // rax
  CTxSuperior *v57; // rcx
  CTmTrace *v58; // rcx
  char *v59; // rbx
  int v60; // edi
  __int64 v61; // rcx
  int v62; // esi
  char *v63; // r14
  void **v64; // rax
  CDtcLu *v65; // rax
  CTmTrace *v66; // rcx
  char *v67; // rbx
  int v68; // edi
  void **v69; // rax
  CGatewayInstance *v70; // rax
  __int64 v71; // [rsp+20h] [rbp-E0h]
  __int64 v72; // [rsp+28h] [rbp-D8h]
  __int64 v73; // [rsp+38h] [rbp-C8h]
  char *v74; // [rsp+50h] [rbp-B0h] BYREF
  void **v75; // [rsp+58h] [rbp-A8h] BYREF
  int v76; // [rsp+60h] [rbp-A0h]
  __int128 v77; // [rsp+68h] [rbp-98h]
  void **v78; // [rsp+78h] [rbp-88h] BYREF
  int v79; // [rsp+80h] [rbp-80h]
  __int128 v80; // [rsp+88h] [rbp-78h]
  void **v81; // [rsp+98h] [rbp-68h] BYREF
  int v82; // [rsp+A0h] [rbp-60h]
  __int128 v83; // [rsp+A8h] [rbp-58h]
  void **v84; // [rsp+B8h] [rbp-48h] BYREF
  void **v85; // [rsp+C0h] [rbp-40h]
  __int64 v86; // [rsp+C8h] [rbp-38h]
  void ***v87; // [rsp+D0h] [rbp-30h]
  void **v88; // [rsp+D8h] [rbp-28h] BYREF
  void **v89; // [rsp+E0h] [rbp-20h]
  __int64 v90; // [rsp+E8h] [rbp-18h]
  void ***v91; // [rsp+F0h] [rbp-10h]
  void **v92; // [rsp+F8h] [rbp-8h] BYREF
  void **v93; // [rsp+100h] [rbp+0h]
  __int64 v94; // [rsp+108h] [rbp+8h]
  void ***v95; // [rsp+110h] [rbp+10h]
  ULONGLONG i; // [rsp+118h] [rbp+18h] BYREF
  _DWORD *v97; // [rsp+120h] [rbp+20h]
  __int64 v98; // [rsp+128h] [rbp+28h]
  __int64 v99; // [rsp+130h] [rbp+30h]
  _DWORD *v100; // [rsp+138h] [rbp+38h]
  __int64 v101; // [rsp+140h] [rbp+40h]
  char *v102; // [rsp+148h] [rbp+48h]
  CTx *v103; // [rsp+150h] [rbp+50h]
  CGatewaySuperior *v104; // [rsp+158h] [rbp+58h]
  CDtcLuSuperior *v105; // [rsp+160h] [rbp+60h]
  CXaSuperior *v106; // [rsp+168h] [rbp+68h]
  CTxSuperior *v107; // [rsp+170h] [rbp+70h]
  CITmInit3 *v108; // [rsp+1C0h] [rbp+C0h] BYREF
  unsigned __int64 v109; // [rsp+1C8h] [rbp+C8h] BYREF
  void *v110; // [rsp+1D0h] [rbp+D0h] BYREF

  v108 = this;
  i = 0;
  v110 = 0;
  v81 = &UTList<CCrashElement *>::`vftable';
  v82 = 0;
  v83 = 0;
  v92 = &UTListIterator<CCrashElement *>::`vftable';
  v95 = &v81;
  v94 = 0;
  v93 = 0;
  v78 = &UTList<CCrashElement *>::`vftable';
  v79 = 0;
  v80 = 0;
  v88 = &UTListIterator<CCrashElement *>::`vftable';
  v91 = &v78;
  v90 = 0;
  v89 = 0;
  v75 = &UTList<CCrashElement *>::`vftable';
  v76 = 0;
  v77 = 0;
  v84 = &UTListIterator<CCrashElement *>::`vftable';
  v87 = &v75;
  v86 = 0;
  v85 = 0;
  v74 = 0;
  LODWORD(v109) = 0;
  LOWORD(v108) = 0;
  v8 = Block;
  *(_DWORD *)Block = 0;
  v9 = (*(__int64 (__fastcall **)(struct ILogRead *, ULONGLONG, unsigned __int64 *, CITmInit3 **))(*(_QWORD *)a2 + 32LL))(
         a2,
         a3->QuadPart,
         &v109,
         &v108);
  for ( i = a3->QuadPart;
        ;
        v9 = (*(__int64 (__fastcall **)(struct ILogRead *, ULONGLONG *, unsigned __int64 *, CITmInit3 **))(*(_QWORD *)a2 + 40LL))(
               a2,
               &i,
               &v109,
               &v108) )
  {
    if ( v9 )
    {
      v102 = 0;
      LODWORD(v101) = 0;
      v100 = 0;
      LODWORD(v99) = 0;
      v36 = 0;
      LODWORD(v98) = 0;
      v97 = 0;
      LODWORD(Block) = 0;
      while ( (unsigned int)UTList<IUISDataProvider *>::RemoveFirst(&v81, &v110) )
      {
        v37 = *(_DWORD **)v110;
        if ( **(_DWORD **)v110 != 32 && **(_DWORD **)v110 != 33 && **(_DWORD **)v110 != 40 )
          CTmTrace::InternalError(
            (CTmTrace *)(unsigned int)(**(_DWORD **)v110 - 33),
            "com\\complus\\dtc\\dtc\\tm\\src\\tminit.cpp",
            1112);
        v74 = (char *)(v37 + 8);
        v38 = 0;
        v39 = 0;
        v40 = 0;
        v41 = 0;
        v42 = v37[8];
        v43 = (char *)v37 + ((v42 + 3) & 0xFFFFFFFC);
        v44 = (unsigned int *)(v43 + 36);
        v74 = v43 + 36;
        switch ( v37[1] )
        {
          case 1:
            v39 = *v44;
            v38 = v43 + 40;
            v45 = (__int64)&v43[((*v44 + 3) & 0xFFFFFFFC) + 40];
            break;
          case 2:
            v40 = v43 + 40;
            v74 = &v43[((*v44 + 3) & 0xFFFFFFFC) + 40];
            v41 = v74 + 4;
            v45 = (__int64)&v74[((*(_DWORD *)v74 + 3) & 0xFFFFFFFC) + 4];
            break;
          case 3:
            v101 = *v44;
            v102 = v43 + 40;
            v74 = &v43[(((_DWORD)v101 + 3) & 0xFFFFFFFC) + 40];
            v99 = *(unsigned int *)v74;
            v100 = v74 + 4;
            v45 = (__int64)&v74[(((_DWORD)v99 + 3) & 0xFFFFFFFC) + 4];
            break;
          case 4:
            v98 = *v44;
            v36 = v43 + 40;
            v74 = &v43[(((_DWORD)v98 + 3) & 0xFFFFFFFC) + 40];
            Block = (void **)*(unsigned int *)v74;
            v97 = v74 + 4;
            v45 = (__int64)&v74[(((_DWORD)Block + 3) & 0xFFFFFFFC) + 4];
            break;
          default:
            CTmTrace::InternalError(
              (CTmTrace *)(unsigned int)(v37[1] - 3),
              "com\\complus\\dtc\\dtc\\tm\\src\\tminit.cpp",
              957);
        }
        v74 = (char *)v45;
        if ( *v37 == 32 )
        {
          switch ( v37[1] )
          {
            case 1:
              v56 = (CTxSuperior *)HeapAlloc(g_CTxSuperior_MemAlloc, 0, 0x1D8u);
              v107 = v56;
              if ( v56 )
                v57 = CTxSuperior::CTxSuperior(v56);
              else
                v57 = 0;
              if ( !v57 )
              {
LABEL_143:
                CTmTrace::StartErrorNoMem(0);
                v84 = &UTListIterator<CCrashElement *>::`vftable';
                v75 = &UTList<CCrashElement *>::`vftable';
                UTList<CCrashElement *>::RemoveAll(&v75);
                v88 = &UTListIterator<CCrashElement *>::`vftable';
                v78 = &UTList<CCrashElement *>::`vftable';
                UTList<CCrashElement *>::RemoveAll(&v78);
                v92 = &UTListIterator<CCrashElement *>::`vftable';
                v81 = &UTList<CCrashElement *>::`vftable';
                UTList<CCrashElement *>::RemoveAll(&v81);
                return 0;
              }
              LODWORD(v72) = v42;
              if ( !(unsigned int)CTxSuperior::InitCrashed(v57, &v74, v38, v39, v37 + 9, v72, v37, &v74) )
              {
LABEL_120:
                v84 = &UTListIterator<CCrashElement *>::`vftable';
                v75 = &UTList<CCrashElement *>::`vftable';
                UTList<CCrashElement *>::RemoveAll(&v75);
                v88 = &UTListIterator<CCrashElement *>::`vftable';
                v78 = &UTList<CCrashElement *>::`vftable';
                UTList<CCrashElement *>::RemoveAll(&v78);
                v92 = &UTListIterator<CCrashElement *>::`vftable';
                v81 = &UTList<CCrashElement *>::`vftable';
                UTList<CCrashElement *>::RemoveAll(&v81);
                return 0;
              }
              break;
            case 2:
              v54 = (CXaSuperior *)operator new(0x200u);
              v106 = v54;
              if ( v54 )
                v55 = CXaSuperior::CXaSuperior(v54);
              else
                v55 = 0;
              if ( !v55 )
                goto LABEL_143;
              LODWORD(v72) = v42;
              if ( !(unsigned int)CXaSuperior::InitCrashed(v55, &v74, v40, v41, v37 + 9, v72, v37, &v74) )
                goto LABEL_126;
              break;
            case 3:
              v52 = (CDtcLuSuperior *)HeapAlloc(g_CDtcLuSuperior_MemAlloc, 0, 0xB8u);
              v105 = v52;
              if ( v52 )
                v53 = CDtcLuSuperior::CDtcLuSuperior(v52);
              else
                v53 = 0;
              if ( !v53 )
                goto LABEL_143;
              LODWORD(v73) = v42;
              LODWORD(v72) = v99;
              if ( !(unsigned int)((__int64 (__fastcall *)(CDtcLuSuperior *, char **, char *, _QWORD, _DWORD *, __int64, _DWORD *, __int64, _DWORD *, char **))CDtcLuSuperior::InitCrashed)(
                                    v53,
                                    &v74,
                                    v102,
                                    (unsigned int)v101,
                                    v100,
                                    v72,
                                    v37 + 9,
                                    v73,
                                    v37,
                                    &v74) )
                goto LABEL_120;
              break;
            case 4:
              v50 = (CGatewaySuperior *)HeapAlloc(g_CGatewaySuperior_MemAlloc, 0, 0x128u);
              v104 = v50;
              if ( !v50 || (v51 = CGatewaySuperior::CGatewaySuperior(v50)) == 0 )
              {
LABEL_126:
                CTmTrace::StartErrorNoMem(v49);
                v84 = &UTListIterator<CCrashElement *>::`vftable';
                v75 = &UTList<CCrashElement *>::`vftable';
                UTList<CCrashElement *>::RemoveAll(&v75);
                v88 = &UTListIterator<CCrashElement *>::`vftable';
                v78 = &UTList<CCrashElement *>::`vftable';
                UTList<CCrashElement *>::RemoveAll(&v78);
                v92 = &UTListIterator<CCrashElement *>::`vftable';
                v81 = &UTList<CCrashElement *>::`vftable';
                UTList<CCrashElement *>::RemoveAll(&v81);
                return 0;
              }
              LODWORD(v73) = v42;
              LODWORD(v72) = (_DWORD)Block;
              if ( !(unsigned int)((__int64 (__fastcall *)(CGatewaySuperior *, char **, char *, _QWORD, _DWORD *, __int64, _DWORD *, __int64, _DWORD *, char **))CGatewaySuperior::InitCrashed)(
                                    v51,
                                    &v74,
                                    v36,
                                    (unsigned int)v98,
                                    v97,
                                    v72,
                                    v37 + 9,
                                    v73,
                                    v37,
                                    &v74) )
                goto LABEL_120;
              break;
            default:
              CTmTrace::InternalError(
                (CTmTrace *)(unsigned int)(v37[1] - 3),
                "com\\complus\\dtc\\dtc\\tm\\src\\tminit.cpp",
                1099);
          }
        }
        else
        {
          if ( *v37 != 33 && *v37 != 40 )
            CTmTrace::InternalError(
              (CTmTrace *)(unsigned int)(*v37 - 33),
              "com\\complus\\dtc\\dtc\\tm\\src\\tminit.cpp",
              1106);
          v46 = *v37 == 40;
          if ( v37[1] != 1 && v37[1] != 2 )
          {
            v47 = (CTmTrace *)(unsigned int)(v37[1] - 3);
            if ( (unsigned int)v47 > 1 )
              CTmTrace::InternalError(v47, "com\\complus\\dtc\\dtc\\tm\\src\\tminit.cpp", 1001);
          }
          v48 = (CTx *)HeapAlloc(g_CTx_MemAlloc, 0, 0x5D8u);
          v103 = v48;
          if ( v48 )
            v48 = CTx::CTx(v48, (struct _GUID *)(v37 + 2));
          if ( !v48 )
            goto LABEL_126;
          if ( !(unsigned int)CTx::InitCrashedBeginner(v48, (unsigned int)(v46 + 2), v37 + 9, v42, v37, &v74) )
            goto LABEL_120;
        }
        operator delete(v37);
        operator delete(v110);
      }
      while ( (unsigned int)UTList<IUISDataProvider *>::RemoveFirst(&v78, &v110) )
      {
        v59 = *(char **)v110;
        if ( **(_DWORD **)v110 != 50 )
          CTmTrace::InternalError(v58, "com\\complus\\dtc\\dtc\\tm\\src\\tminit.cpp", 1161);
        v74 = v59 + 28;
        v60 = *((_DWORD *)v59 + 7);
        v61 = (v60 + 3) & 0xFFFFFFFC;
        v74 = &v59[v61 + 32];
        v62 = *(_DWORD *)v74;
        v63 = &v59[v61 + 36];
        v74 = &v63[(*(_DWORD *)v74 + 3) & 0xFFFFFFFC];
        v64 = (void **)operator new(0x360u);
        Block = v64;
        if ( !v64 )
          goto LABEL_126;
        v65 = CDtcLu::CDtcLu((CDtcLu *)v64);
        if ( !v65 )
          goto LABEL_126;
        LODWORD(v71) = *((_DWORD *)v59 + 6);
        (*(void (__fastcall **)(_QWORD, CDtcLu *, bool, _DWORD *, __int64, _DWORD *, int, char *, int))(**((_QWORD **)v65 + 83) + 32LL))(
          *((_QWORD *)v65 + 83),
          v65,
          *((_DWORD *)v59 + 5) == 2,
          (_DWORD *)v59 + 1,
          v71,
          (_DWORD *)v59 + 8,
          v60,
          v63,
          v62);
        operator delete(v59);
        operator delete(v110);
      }
      while ( (unsigned int)UTList<IUISDataProvider *>::RemoveFirst(&v75, &v110) )
      {
        v67 = *(char **)v110;
        if ( **(_DWORD **)v110 != 60 )
          CTmTrace::InternalError(v66, "com\\complus\\dtc\\dtc\\tm\\src\\tminit.cpp", 1204);
        v74 = v67 + 40;
        v68 = *((_DWORD *)v67 + 10);
        v74 = &v67[((v68 + 3) & 0xFFFFFFFC) + 44];
        v69 = (void **)operator new(0x248u);
        Block = v69;
        if ( !v69 )
          goto LABEL_126;
        v70 = CGatewayInstance::CGatewayInstance((CGatewayInstance *)v69);
        if ( !v70 )
          goto LABEL_126;
        LODWORD(v71) = *((_DWORD *)v67 + 9);
        (*(void (__fastcall **)(_QWORD, CGatewayInstance *, _DWORD *, _DWORD *, __int64, _DWORD *, int))(**((_QWORD **)v70 + 5) + 56LL))(
          *((_QWORD *)v70 + 5),
          v70,
          (_DWORD *)v67 + 1,
          (_DWORD *)v67 + 5,
          v71,
          (_DWORD *)v67 + 11,
          v68);
        operator delete(v67);
        operator delete(v110);
      }
      v84 = &UTListIterator<CCrashElement *>::`vftable';
      v75 = &UTList<CCrashElement *>::`vftable';
      UTList<CCrashElement *>::RemoveAll(&v75);
      v88 = &UTListIterator<CCrashElement *>::`vftable';
      v78 = &UTList<CCrashElement *>::`vftable';
      UTList<CCrashElement *>::RemoveAll(&v78);
      v92 = &UTListIterator<CCrashElement *>::`vftable';
      v81 = &UTList<CCrashElement *>::`vftable';
      UTList<CCrashElement *>::RemoveAll(&v81);
      return 1;
    }
    if ( (unsigned int)v109 < 0x20 )
      break;
    v10 = operator new[]((unsigned int)v109);
    v11 = v10;
    if ( !v10 )
      goto LABEL_82;
    v12 = (*(__int64 (__fastcall **)(struct ILogRead *, _QWORD *, _QWORD))(*(_QWORD *)a2 + 48LL))(
            a2,
            v10,
            (unsigned int)v109);
    if ( v12 )
    {
      CTmTrace::StartError(v13, 3, v12);
      v84 = &UTListIterator<CCrashElement *>::`vftable';
      v75 = &UTList<CCrashElement *>::`vftable';
      UTList<CCrashElement *>::RemoveAll(&v75);
      v88 = &UTListIterator<CCrashElement *>::`vftable';
      v78 = &UTList<CCrashElement *>::`vftable';
      UTList<CCrashElement *>::RemoveAll(&v78);
      v92 = &UTListIterator<CCrashElement *>::`vftable';
      v81 = &UTList<CCrashElement *>::`vftable';
      UTList<CCrashElement *>::RemoveAll(&v81);
      return 0;
    }
    if ( *(_DWORD *)v11 == 25 )
    {
LABEL_74:
      operator delete(v11);
    }
    else
    {
      switch ( *(_DWORD *)v11 )
      {
        case 0x14:
        case 0x15:
        case 0x16:
        case 0x17:
        case 0x18:
          goto LABEL_74;
        case 0x1E:
          a4->QuadPart = i;
          *(_DWORD *)v8 = 1;
          goto LABEL_74;
        case 0x1F:
          *(_DWORD *)v8 = 0;
          goto LABEL_74;
        case 0x20:
        case 0x21:
        case 0x28:
          v94 = 0;
          v93 = v95[2];
          while ( 2 )
          {
            if ( ((unsigned int (__fastcall *)(void ***))v92[2])(&v92) )
            {
              v110 = (void *)((__int64 (__fastcall *)(void ***))v92[1])(&v92);
              v14 = *(_QWORD *)(*(_QWORD *)v110 + 8LL) - v11[1];
              if ( !v14 )
                v14 = *(_QWORD *)(*(_QWORD *)v110 + 16LL) - v11[2];
              if ( v14 )
              {
                ((void (__fastcall *)(void ***, _QWORD))v92[3])(&v92, 0);
                continue;
              }
              Block = 0;
              UTListIterator<CCrashElement *>::RemoveCurrent(&v92, &Block);
              v15 = Block;
              if ( *Block )
                operator delete(*Block);
              operator delete(v15);
            }
            break;
          }
          v16 = operator new(0x18u);
          v110 = v16;
          if ( !v16 )
            goto LABEL_76;
          *v16 = v11;
          *((_DWORD *)v110 + 2) = v109;
          *((_QWORD *)v110 + 2) = i;
          UTList<CCrashElement *>::Add(&v81, &v110);
          continue;
        case 0x22:
        case 0x23:
          v94 = 0;
          v93 = v95[2];
          while ( 2 )
          {
            if ( !((unsigned int (__fastcall *)(void ***))v92[2])(&v92) )
              goto LABEL_74;
            v110 = (void *)((__int64 (__fastcall *)(void ***))v92[1])(&v92);
            v18 = *(_QWORD *)(*(_QWORD *)v110 + 8LL) - v11[1];
            if ( !v18 )
              v18 = *(_QWORD *)(*(_QWORD *)v110 + 16LL) - v11[2];
            if ( v18 )
            {
              ((void (__fastcall *)(void ***, _QWORD))v92[3])(&v92, 0);
              continue;
            }
            break;
          }
          v19 = &v92;
          goto LABEL_28;
        case 0x32:
          v90 = 0;
          v89 = v91[2];
          while ( 2 )
          {
            if ( ((unsigned int (__fastcall *)(void ***))v88[2])(&v88) )
            {
              v110 = (void *)((__int64 (__fastcall *)(void ***))v88[1])(&v88);
              v22 = *(_QWORD *)(*(_QWORD *)v110 + 4LL) - *(_QWORD *)((char *)v11 + 4);
              if ( !v22 )
                v22 = *(_QWORD *)(*(_QWORD *)v110 + 12LL) - *(_QWORD *)((char *)v11 + 12);
              if ( v22 )
              {
                ((void (__fastcall *)(void ***, _QWORD))v88[3])(&v88, 0);
                continue;
              }
              Block = 0;
              UTListIterator<CCrashElement *>::RemoveCurrent(&v88, &Block);
              v23 = Block;
              if ( *Block )
                operator delete(*Block);
              operator delete(v23);
            }
            break;
          }
          v24 = operator new(0x18u);
          v110 = v24;
          if ( !v24 )
            goto LABEL_76;
          *v24 = v11;
          *((_DWORD *)v110 + 2) = v109;
          *((_QWORD *)v110 + 2) = i;
          UTList<CCrashElement *>::Add(&v78, &v110);
          continue;
        case 0x33:
          v90 = 0;
          v89 = v91[2];
          while ( 2 )
          {
            if ( !((unsigned int (__fastcall *)(void ***))v88[2])(&v88) )
              goto LABEL_74;
            v110 = (void *)((__int64 (__fastcall *)(void ***))v88[1])(&v88);
            v25 = *(_QWORD *)(*(_QWORD *)v110 + 4LL) - *(_QWORD *)((char *)v11 + 4);
            if ( !v25 )
              v25 = *(_QWORD *)(*(_QWORD *)v110 + 12LL) - *(_QWORD *)((char *)v11 + 12);
            if ( v25 )
            {
              ((void (__fastcall *)(void ***, _QWORD))v88[3])(&v88, 0);
              continue;
            }
            break;
          }
          v19 = &v88;
LABEL_28:
          Block = 0;
          UTListIterator<CCrashElement *>::RemoveCurrent(v19, &Block);
          v20 = Block;
          v21 = *Block;
          if ( !*Block )
            goto LABEL_73;
          goto LABEL_72;
        case 0x3C:
          v86 = 0;
          v85 = v87[2];
          while ( 2 )
          {
            if ( ((unsigned int (__fastcall *)(void ***))v84[2])(&v84) )
            {
              v110 = (void *)((__int64 (__fastcall *)(void ***))v84[1])(&v84);
              v26 = *(char **)v110;
              v27 = *(_QWORD *)(*(_QWORD *)v110 + 4LL) - *(_QWORD *)((char *)v11 + 4);
              if ( !v27 )
                v27 = *(_QWORD *)(v26 + 12) - *(_QWORD *)((char *)v11 + 12);
              if ( v27 )
                goto LABEL_56;
              v28 = *(_QWORD *)(v26 + 20) - *(_QWORD *)((char *)v11 + 20);
              if ( !v28 )
                v28 = *(_QWORD *)(v26 + 28) - *(_QWORD *)((char *)v11 + 28);
              if ( v28 )
              {
LABEL_56:
                ((void (__fastcall *)(void ***, _QWORD))v84[3])(&v84, 0);
                continue;
              }
              Block = 0;
              UTListIterator<CCrashElement *>::RemoveCurrent(&v84, &Block);
              v29 = Block;
              if ( *Block )
                operator delete(*Block);
              operator delete(v29);
            }
            break;
          }
          v30 = operator new(0x18u);
          v110 = v30;
          if ( !v30 )
          {
LABEL_76:
            CTmTrace::StartErrorNoMem(v17);
            v84 = &UTListIterator<CCrashElement *>::`vftable';
            v75 = &UTList<CCrashElement *>::`vftable';
            UTList<CCrashElement *>::RemoveAll(&v75);
            v88 = &UTListIterator<CCrashElement *>::`vftable';
            v78 = &UTList<CCrashElement *>::`vftable';
            UTList<CCrashElement *>::RemoveAll(&v78);
            v92 = &UTListIterator<CCrashElement *>::`vftable';
            v81 = &UTList<CCrashElement *>::`vftable';
            UTList<CCrashElement *>::RemoveAll(&v81);
            return 0;
          }
          *v30 = v11;
          *((_DWORD *)v110 + 2) = v109;
          *((_QWORD *)v110 + 2) = i;
          UTList<CCrashElement *>::Add(&v75, &v110);
          break;
        case 0x3D:
          v86 = 0;
          v85 = v87[2];
          while ( 2 )
          {
            if ( ((unsigned int (__fastcall *)(void ***))v84[2])(&v84) )
            {
              v110 = (void *)((__int64 (__fastcall *)(void ***))v84[1])(&v84);
              v31 = *(char **)v110;
              v32 = *(_QWORD *)(*(_QWORD *)v110 + 4LL) - *(_QWORD *)((char *)v11 + 4);
              if ( !v32 )
                v32 = *(_QWORD *)(v31 + 12) - *(_QWORD *)((char *)v11 + 12);
              if ( v32 )
                goto LABEL_70;
              v33 = *(_QWORD *)(v31 + 20) - *(_QWORD *)((char *)v11 + 20);
              if ( !v33 )
                v33 = *(_QWORD *)(v31 + 28) - *(_QWORD *)((char *)v11 + 28);
              if ( v33 )
              {
LABEL_70:
                ((void (__fastcall *)(void ***, _QWORD))v84[3])(&v84, 0);
                continue;
              }
              Block = 0;
              UTListIterator<CCrashElement *>::RemoveCurrent(&v84, &Block);
              v20 = Block;
              v21 = *Block;
              if ( *Block )
LABEL_72:
                operator delete(v21);
LABEL_73:
              operator delete(v20);
            }
            goto LABEL_74;
          }
        default:
          CTmTrace::StartErrorLogRecUnknown(v13);
          v84 = &UTListIterator<CCrashElement *>::`vftable';
          v75 = &UTList<CCrashElement *>::`vftable';
          UTList<CCrashElement *>::RemoveAll(&v75);
          v88 = &UTListIterator<CCrashElement *>::`vftable';
          v78 = &UTList<CCrashElement *>::`vftable';
          UTList<CCrashElement *>::RemoveAll(&v78);
          v92 = &UTListIterator<CCrashElement *>::`vftable';
          v81 = &UTList<CCrashElement *>::`vftable';
          UTList<CCrashElement *>::RemoveAll(&v81);
          return 0;
      }
    }
  }
  v35 = (*(__int64 (__fastcall **)(struct IDtcTrace *, __int64, __int64, _QWORD, int, _DWORD, _QWORD, _QWORD))(*(_QWORD *)g_pIDtcTrace + 24LL))(
          g_pIDtcTrace,
          4097,
          2,
          0,
          -1073737635,
          0,
          0,
          0);
  if ( v35 < 0 )
    TraceFile(v35, "failed in g_pIDtcTrace->Trace", "com\\complus\\dtc\\dtc\\tm\\src\\tmtrace.cpp", 0x177u);
LABEL_82:
  v84 = &UTListIterator<CCrashElement *>::`vftable';
  v75 = &UTList<CCrashElement *>::`vftable';
  UTList<CCrashElement *>::RemoveAll(&v75);
  v88 = &UTListIterator<CCrashElement *>::`vftable';
  v78 = &UTList<CCrashElement *>::`vftable';
  UTList<CCrashElement *>::RemoveAll(&v78);
  v92 = &UTListIterator<CCrashElement *>::`vftable';
  v81 = &UTList<CCrashElement *>::`vftable';
  UTList<CCrashElement *>::RemoveAll(&v81);
  return 0;
}

```

## disassembly

```asm
0x18000bcd0  mov     [rsp-8+arg_18], rbx
0x18000bcd5  mov     [rsp-8+arg_0], rcx
0x18000bcda  push    rbp
0x18000bcdb  push    rsi
0x18000bcdc  push    rdi
0x18000bcdd  push    r12
0x18000bcdf  push    r13
0x18000bce1  push    r14
0x18000bce3  push    r15
0x18000bce5  lea     rbp, [rsp-80h]
0x18000bcea  sub     rsp, 180h
0x18000bcf1  mov     r15, r9
0x18000bcf4  mov     rbx, r8
0x18000bcf7  mov     rdi, rdx
0x18000bcfa  xor     r12d, r12d
0x18000bcfd  mov     [rbp+0B0h+var_98], r12
0x18000bd01  mov     [rbp+0B0h+arg_10], r12
0x18000bd08  lea     rsi, ??_7?$UTList@PEAVCCrashElement@@@@6B@; const UTList<CCrashElement *>::`vftable'
0x18000bd0f  mov     [rbp+0B0h+var_118], rsi
0x18000bd13  mov     [rbp+0B0h+var_110], r12d
0x18000bd17  xorps   xmm0, xmm0
0x18000bd1a  movdqu  [rbp+0B0h+var_108], xmm0
0x18000bd1f  lea     r13, ??_7?$UTListIterator@PEAVCCrashElement@@@@6B@; const UTListIterator<CCrashElement *>::`vftable'
0x18000bd26  mov     [rbp+0B0h+var_B8], r13
0x18000bd2a  lea     rax, [rbp+0B0h+var_118]
0x18000bd2e  mov     [rbp+0B0h+var_A0], rax
0x18000bd32  mov     [rbp+0B0h+var_A8], r12
0x18000bd36  mov     [rbp+0B0h+var_B0], r12
0x18000bd3a  mov     [rsp+1B0h+var_138], rsi
0x18000bd3f  mov     [rbp+0B0h+var_130], r12d
0x18000bd43  movdqu  [rbp+0B0h+var_128], xmm0
0x18000bd48  mov     [rbp+0B0h+var_D8], r13
0x18000bd4c  lea     rax, [rsp+1B0h+var_138]
0x18000bd51  mov     [rbp+0B0h+var_C0], rax
0x18000bd55  mov     [rbp+0B0h+var_C8], r12
0x18000bd59  mov     [rbp+0B0h+var_D0], r12
0x18000bd5d  mov     [rsp+1B0h+var_158], rsi
0x18000bd62  mov     [rsp+1B0h+var_150], r12d
0x18000bd67  movdqu  [rsp+1B0h+var_148], xmm0
0x18000bd6d  mov     [rbp+0B0h+var_F8], r13
0x18000bd71  lea     rax, [rsp+1B0h+var_158]
0x18000bd76  mov     [rbp+0B0h+var_E0], rax
0x18000bd7a  mov     [rbp+0B0h+var_E8], r12
0x18000bd7e  mov     [rbp+0B0h+var_F0], r12
0x18000bd82  mov     [rsp+1B0h+var_160], r12
0x18000bd87  mov     dword ptr [rbp+0B0h+arg_8], r12d
0x18000bd8e  mov     word ptr [rbp+0B0h+arg_0], r12w
0x18000bd96  mov     r14, [rbp+0B0h+Block]
0x18000bd9d  mov     [r14], r12d
0x18000bda0  mov     rax, [rdx]
0x18000bda3  lea     r9, [rbp+0B0h+arg_0]
0x18000bdaa  lea     r8, [rbp+0B0h+arg_8]
0x18000bdb1  mov     rdx, [rbx]
0x18000bdb4  mov     rcx, rdi
0x18000bdb7  mov     rax, [rax+20h]
0x18000bdbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdc0  mov     rcx, [rbx]
0x18000bdc3  mov     [rbp+0B0h+var_98], rcx
0x18000bdc7  lea     rsi, cs:180000000h
0x18000bdce  xchg    ax, ax
0x18000bdd0  test    eax, eax
0x18000bdd2  jnz     loc_18000C5EA
0x18000bdd8  mov     eax, dword ptr [rbp+0B0h+arg_8]
0x18000bdde  cmp     eax, 20h ; ' '
0x18000bde1  jb      loc_18000C54A
0x18000bde7  mov     ecx, eax; unsigned __int64
0x18000bde9  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000bdee  mov     rbx, rax
0x18000bdf1  test    rax, rax
0x18000bdf4  jz      loc_18000C502
0x18000bdfa  mov     rax, [rdi]
0x18000bdfd  mov     r8d, dword ptr [rbp+0B0h+arg_8]
0x18000be04  mov     rdx, rbx
0x18000be07  mov     rcx, rdi
0x18000be0a  mov     rax, [rax+30h]
0x18000be0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be13  test    eax, eax
0x18000be15  jnz     loc_18000C4AC
0x18000be1b  mov     eax, [rbx]
0x18000be1d  cmp     eax, 19h
0x18000be20  jz      loc_18000C346; jumptable 000000018000BE46 cases 20-24
0x18000be26  add     eax, 0FFFFFFECh; switch 42 cases
0x18000be29  cmp     eax, 29h
0x18000be2c  ja      def_18000BE46; jumptable 000000018000BE46 default case, cases 25-29,36-39,41-49,52-59
0x18000be32  cdqe
0x18000be34  movzx   eax, ds:(byte_18000D060 - 180000000h)[rsi+rax]
0x18000be3c  mov     ecx, ds:(jpt_18000BE46 - 180000000h)[rsi+rax*4]
0x18000be43  add     rcx, rsi
0x18000be46  jmp     rcx; switch jump
0x18000be48  mov     rax, [rbp+0B0h+var_98]; jumptable 000000018000BE46 case 30
0x18000be4c  mov     [r15], rax
0x18000be4f  mov     dword ptr [r14], 1
0x18000be56  jmp     loc_18000C346; jumptable 000000018000BE46 cases 20-24
0x18000be5b  mov     [r14], r12d; jumptable 000000018000BE46 case 31
0x18000be5e  jmp     loc_18000C346; jumptable 000000018000BE46 cases 20-24
0x18000be63  mov     [rbp+0B0h+var_A8], r12; jumptable 000000018000BE46 cases 32,33,40
0x18000be67  mov     rax, [rbp+0B0h+var_A0]
0x18000be6b  mov     rcx, [rax+10h]
0x18000be6f  mov     [rbp+0B0h+var_B0], rcx
0x18000be73  mov     rax, [rbp+0B0h+var_B8]
0x18000be77  lea     rcx, [rbp+0B0h+var_B8]
0x18000be7b  mov     rax, [rax+10h]
0x18000be7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be84  test    eax, eax
0x18000be86  jz      loc_18000BF0D
0x18000be8c  mov     rax, [rbp+0B0h+var_B8]
0x18000be90  lea     rcx, [rbp+0B0h+var_B8]
0x18000be94  mov     rax, [rax+8]
0x18000be98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be9d  mov     [rbp+0B0h+arg_10], rax
0x18000bea4  mov     rcx, [rax]
0x18000bea7  mov     rax, [rcx+8]
0x18000beab  sub     rax, [rbx+8]
0x18000beaf  jnz     short loc_18000BEB9
0x18000beb1  mov     rax, [rcx+10h]
0x18000beb5  sub     rax, [rbx+10h]
0x18000beb9  test    rax, rax
0x18000bebc  jz      short loc_18000BED3
0x18000bebe  mov     rax, [rbp+0B0h+var_B8]
0x18000bec2  xor     edx, edx
0x18000bec4  lea     rcx, [rbp+0B0h+var_B8]
0x18000bec8  mov     rax, [rax+18h]
0x18000becc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bed1  jmp     short loc_18000BE73
0x18000bed3  mov     [rbp+0B0h+Block], r12
0x18000beda  lea     rdx, [rbp+0B0h+Block]
0x18000bee1  lea     rcx, [rbp+0B0h+var_B8]
0x18000bee5  call    ?RemoveCurrent@?$UTListIterator@PEAVCCrashElement@@@@UEAAHPEAPEAVCCrashElement@@@Z; UTListIterator<CCrashElement *>::RemoveCurrent(CCrashElement * *)
0x18000beea  mov     rsi, [rbp+0B0h+Block]
0x18000bef1  mov     rcx, [rsi]; Block
0x18000bef4  test    rcx, rcx
0x18000bef7  jz      short loc_18000BEFE
0x18000bef9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000befe  mov     rcx, rsi; Block
0x18000bf01  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000bf06  lea     rsi, cs:180000000h
0x18000bf0d  mov     ecx, 18h; Size
0x18000bf12  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bf17  mov     [rbp+0B0h+arg_10], rax
0x18000bf1e  test    rax, rax
0x18000bf21  jz      loc_18000C374
0x18000bf27  mov     [rax], rbx
0x18000bf2a  mov     rcx, [rbp+0B0h+arg_10]
0x18000bf31  mov     eax, dword ptr [rbp+0B0h+arg_8]
0x18000bf37  mov     [rcx+8], eax
0x18000bf3a  mov     rcx, [rbp+0B0h+var_98]
0x18000bf3e  mov     rax, [rbp+0B0h+arg_10]
0x18000bf45  mov     [rax+10h], rcx
0x18000bf49  lea     rdx, [rbp+0B0h+arg_10]
0x18000bf50  lea     rcx, [rbp+0B0h+var_118]
0x18000bf54  call    ?Add@?$UTList@PEAVCCrashElement@@@@UEAAXAEBQEAVCCrashElement@@@Z; UTList<CCrashElement *>::Add(CCrashElement * const &)
0x18000bf59  jmp     loc_18000C34E
0x18000bf5e  mov     [rbp+0B0h+var_A8], r12; jumptable 000000018000BE46 cases 34,35
0x18000bf62  mov     rax, [rbp+0B0h+var_A0]
0x18000bf66  mov     rcx, [rax+10h]
0x18000bf6a  mov     [rbp+0B0h+var_B0], rcx
0x18000bf6e  mov     rax, [rbp+0B0h+var_B8]
0x18000bf72  lea     rcx, [rbp+0B0h+var_B8]
0x18000bf76  mov     rax, [rax+10h]
0x18000bf7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf7f  test    eax, eax
0x18000bf81  jz      loc_18000C346; jumptable 000000018000BE46 cases 20-24
0x18000bf87  mov     rax, [rbp+0B0h+var_B8]
0x18000bf8b  lea     rcx, [rbp+0B0h+var_B8]
0x18000bf8f  mov     rax, [rax+8]
0x18000bf93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf98  mov     [rbp+0B0h+arg_10], rax
0x18000bf9f  mov     rcx, [rax]
0x18000bfa2  mov     rax, [rcx+8]
0x18000bfa6  sub     rax, [rbx+8]
0x18000bfaa  jnz     short loc_18000BFB4
0x18000bfac  mov     rax, [rcx+10h]
0x18000bfb0  sub     rax, [rbx+10h]
0x18000bfb4  test    rax, rax
0x18000bfb7  jz      short loc_18000BFCE
0x18000bfb9  mov     rax, [rbp+0B0h+var_B8]
0x18000bfbd  xor     edx, edx
0x18000bfbf  lea     rcx, [rbp+0B0h+var_B8]
0x18000bfc3  mov     rax, [rax+18h]
0x18000bfc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfcc  jmp     short loc_18000BF6E
0x18000bfce  lea     rcx, [rbp+0B0h+var_B8]
0x18000bfd2  lea     rdx, [rbp+0B0h+Block]
0x18000bfd9  mov     [rbp+0B0h+Block], r12
0x18000bfe0  call    ?RemoveCurrent@?$UTListIterator@PEAVCCrashElement@@@@UEAAHPEAPEAVCCrashElement@@@Z; UTListIterator<CCrashElement *>::RemoveCurrent(CCrashElement * *)
0x18000bfe5  mov     rsi, [rbp+0B0h+Block]
0x18000bfec  mov     rcx, [rsi]
0x18000bfef  test    rcx, rcx
0x18000bff2  jnz     loc_18000C332
0x18000bff8  jmp     loc_18000C337
0x18000bffd  mov     [rbp+0B0h+var_C8], r12; jumptable 000000018000BE46 case 50
0x18000c001  mov     rax, [rbp+0B0h+var_C0]
0x18000c005  mov     rcx, [rax+10h]
0x18000c009  mov     [rbp+0B0h+var_D0], rcx
0x18000c00d  mov     rax, [rbp+0B0h+var_D8]
0x18000c011  lea     rcx, [rbp+0B0h+var_D8]
0x18000c015  mov     rax, [rax+10h]
0x18000c019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c01e  test    eax, eax
0x18000c020  jz      loc_18000C0A7
0x18000c026  mov     rax, [rbp+0B0h+var_D8]
0x18000c02a  lea     rcx, [rbp+0B0h+var_D8]
0x18000c02e  mov     rax, [rax+8]
0x18000c032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c037  mov     [rbp+0B0h+arg_10], rax
0x18000c03e  mov     rcx, [rax]
0x18000c041  mov     rax, [rcx+4]
0x18000c045  sub     rax, [rbx+4]
0x18000c049  jnz     short loc_18000C053
0x18000c04b  mov     rax, [rcx+0Ch]
0x18000c04f  sub     rax, [rbx+0Ch]
0x18000c053  test    rax, rax
0x18000c056  jz      short loc_18000C06D
0x18000c058  mov     rax, [rbp+0B0h+var_D8]
0x18000c05c  xor     edx, edx
0x18000c05e  lea     rcx, [rbp+0B0h+var_D8]
0x18000c062  mov     rax, [rax+18h]
0x18000c066  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c06b  jmp     short loc_18000C00D
0x18000c06d  mov     [rbp+0B0h+Block], r12
0x18000c074  lea     rdx, [rbp+0B0h+Block]
0x18000c07b  lea     rcx, [rbp+0B0h+var_D8]
0x18000c07f  call    ?RemoveCurrent@?$UTListIterator@PEAVCCrashElement@@@@UEAAHPEAPEAVCCrashElement@@@Z; UTListIterator<CCrashElement *>::RemoveCurrent(CCrashElement * *)
0x18000c084  mov     rsi, [rbp+0B0h+Block]
0x18000c08b  mov     rcx, [rsi]; Block
0x18000c08e  test    rcx, rcx
0x18000c091  jz      short loc_18000C098
0x18000c093  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c098  mov     rcx, rsi; Block
0x18000c09b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c0a0  lea     rsi, cs:180000000h
0x18000c0a7  mov     ecx, 18h; Size
0x18000c0ac  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c0b1  mov     [rbp+0B0h+arg_10], rax
0x18000c0b8  test    rax, rax
0x18000c0bb  jz      loc_18000C3C2
0x18000c0c1  mov     [rax], rbx
0x18000c0c4  mov     rcx, [rbp+0B0h+arg_10]
0x18000c0cb  mov     eax, dword ptr [rbp+0B0h+arg_8]
0x18000c0d1  mov     [rcx+8], eax
0x18000c0d4  mov     rcx, [rbp+0B0h+var_98]
0x18000c0d8  mov     rax, [rbp+0B0h+arg_10]
0x18000c0df  mov     [rax+10h], rcx
0x18000c0e3  lea     rdx, [rbp+0B0h+arg_10]
0x18000c0ea  lea     rcx, [rsp+1B0h+var_138]
0x18000c0ef  call    ?Add@?$UTList@PEAVCCrashElement@@@@UEAAXAEBQEAVCCrashElement@@@Z; UTList<CCrashElement *>::Add(CCrashElement * const &)
0x18000c0f4  jmp     loc_18000C34E
0x18000c0f9  mov     [rbp+0B0h+var_C8], r12; jumptable 000000018000BE46 case 51
0x18000c0fd  mov     rax, [rbp+0B0h+var_C0]
0x18000c101  mov     rcx, [rax+10h]
0x18000c105  mov     [rbp+0B0h+var_D0], rcx
0x18000c109  mov     rax, [rbp+0B0h+var_D8]
0x18000c10d  lea     rcx, [rbp+0B0h+var_D8]
0x18000c111  mov     rax, [rax+10h]
0x18000c115  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c11a  test    eax, eax
0x18000c11c  jz      loc_18000C346; jumptable 000000018000BE46 cases 20-24
0x18000c122  mov     rax, [rbp+0B0h+var_D8]
0x18000c126  lea     rcx, [rbp+0B0h+var_D8]
0x18000c12a  mov     rax, [rax+8]
0x18000c12e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c133  mov     [rbp+0B0h+arg_10], rax
0x18000c13a  mov     rcx, [rax]
0x18000c13d  mov     rax, [rcx+4]
0x18000c141  sub     rax, [rbx+4]
0x18000c145  jnz     short loc_18000C14F
0x18000c147  mov     rax, [rcx+0Ch]
0x18000c14b  sub     rax, [rbx+0Ch]
0x18000c14f  test    rax, rax
0x18000c152  jz      short loc_18000C169
0x18000c154  mov     rax, [rbp+0B0h+var_D8]
0x18000c158  xor     edx, edx
0x18000c15a  lea     rcx, [rbp+0B0h+var_D8]
0x18000c15e  mov     rax, [rax+18h]
0x18000c162  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c167  jmp     short loc_18000C109
0x18000c169  lea     rcx, [rbp+0B0h+var_D8]
0x18000c16d  jmp     loc_18000BFD2
0x18000c172  mov     [rbp+0B0h+var_E8], r12; jumptable 000000018000BE46 case 60
0x18000c176  mov     rax, [rbp+0B0h+var_E0]
0x18000c17a  mov     rcx, [rax+10h]
0x18000c17e  mov     [rbp+0B0h+var_F0], rcx
0x18000c182  mov     rax, [rbp+0B0h+var_F8]
0x18000c186  lea     rcx, [rbp+0B0h+var_F8]
0x18000c18a  mov     rax, [rax+10h]
0x18000c18e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c193  test    eax, eax
0x18000c195  jz      loc_18000C233
0x18000c19b  mov     rax, [rbp+0B0h+var_F8]
0x18000c19f  lea     rcx, [rbp+0B0h+var_F8]
0x18000c1a3  mov     rax, [rax+8]
0x18000c1a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1ac  mov     [rbp+0B0h+arg_10], rax
0x18000c1b3  mov     rcx, [rax]
0x18000c1b6  mov     rax, [rcx+4]
0x18000c1ba  sub     rax, [rbx+4]
0x18000c1be  jnz     short loc_18000C1C8
0x18000c1c0  mov     rax, [rcx+0Ch]
0x18000c1c4  sub     rax, [rbx+0Ch]
0x18000c1c8  test    rax, rax
  ... truncated ...
```
