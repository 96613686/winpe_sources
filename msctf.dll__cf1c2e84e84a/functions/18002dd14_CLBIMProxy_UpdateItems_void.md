# CLBIMProxy::UpdateItems(void)

- ea: `0x18002dd14`
- end: `0x18002e84d`
- name: `?UpdateItems@CLBIMProxy@@AEAAXXZ`
- size: `2873`
- prototype: `void __fastcall(CLBIMProxy *__hidden this)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002dc28`

## callees

- `0x1800139a4`
- `0x1800139c0`
- `0x18002cacc`
- `0x18002da10`
- `0x18002db70`
- `0x18002dd14`
- `0x18002e860`
- `0x18002ed20`
- `0x18002ee38`
- `0x18002f140`
- `0x180040694`
- `0x180089830`
- `0x180089de0`
- `0x18008d588`
- `0x1800b1c40`
- `0x1800bd538`
- `0x1800bd5d4`
- `0x1800bd678`
- `0x1800bd720`
- `0x180106a60`
- `0x18010a010`

## import_xrefs

- `ntdll!NtAlpcDeleteSectionView` at `0x18002e5b3`
- `ntdll!NtAlpcDeleteSectionView` at `0x18002e5b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e049`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e049`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002e183`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002e183`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e007`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e246`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e33a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e43c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e68a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e6fc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e776`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e007`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e246`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e33a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e43c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e68a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e6fc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e776`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e0a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e0a8`

## pseudocode

```c
void __fastcall CLBIMProxy::UpdateItems(__int64 **this)
{
  unsigned int ActivedLangBarThreadID; // r15d
  int v3; // r14d
  unsigned int v4; // esi
  _DWORD *v5; // rax
  struct MsgBase *v6; // rbx
  DWORD CurrentThreadId; // eax
  int v8; // esi
  CCtfClientPort *Instance; // rax
  CCtfClientPort *v10; // r15
  __int64 i; // r8
  __int64 v12; // rcx
  __int64 v13; // rdx
  unsigned int v14; // r12d
  int v15; // r15d
  __int64 v16; // rsi
  bool v17; // zf
  __int64 *v18; // r14
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rax
  const WCHAR *lpString2; // rbx
  const WCHAR *v23; // rax
  int j; // ebx
  __int64 *v25; // rax
  __int64 *v26; // rsi
  char *v27; // rax
  CLanguageBarItemExtension *v28; // rbx
  __int64 v29; // rcx
  HICON v30; // r13
  __int64 v31; // r15
  LONG v32; // r12d
  int v33; // eax
  _WORD *v34; // r15
  __int64 v35; // rdx
  _WORD *v36; // rax
  __int64 v37; // r14
  unsigned __int64 v38; // r14
  _WORD *v39; // rax
  __int64 v40; // rcx
  _WORD *v41; // rcx
  unsigned __int16 *v42; // r9
  CLanguageBarItemExtension *v43; // r10
  CLanguageBarItemExtension *v44; // rax
  int v45; // eax
  int v46; // edx
  int v47; // r14d
  void (*v48)(void); // rax
  void **v49; // rax
  __int64 *v50; // rcx
  __int64 v51; // rax
  struct MsgBase *v52; // r14
  __int64 v53; // rcx
  int v54; // edx
  CLanguageBarItemBalloon *v55; // r11
  CLanguageBarItemBitmapButton *v56; // r11
  CLanguageBarItemBitmap *v57; // r11
  int v58; // edx
  int v59; // r8d
  __int64 v60; // rax
  int v61; // [rsp+48h] [rbp-B8h]
  int v62; // [rsp+60h] [rbp-A0h] BYREF
  struct MsgBase *v63; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v64; // [rsp+70h] [rbp-90h] BYREF
  __int64 v65; // [rsp+78h] [rbp-88h] BYREF
  __int64 v66; // [rsp+80h] [rbp-80h] BYREF
  __int64 v67; // [rsp+88h] [rbp-78h] BYREF
  __int64 v68; // [rsp+90h] [rbp-70h] BYREF
  __int64 v69; // [rsp+98h] [rbp-68h] BYREF
  __int64 v70; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v71; // [rsp+A8h] [rbp-58h] BYREF
  int v72; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v73; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v74; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int *v75; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int16 *v76; // [rsp+D0h] [rbp-30h]
  unsigned __int16 *v77; // [rsp+D8h] [rbp-28h]
  __int128 v78; // [rsp+E0h] [rbp-20h] BYREF
  int v79; // [rsp+F0h] [rbp-10h] BYREF
  unsigned int **v80; // [rsp+F8h] [rbp-8h]
  __int64 v81; // [rsp+100h] [rbp+0h]
  int v82; // [rsp+108h] [rbp+8h]
  int *v83; // [rsp+110h] [rbp+10h]
  int *v84; // [rsp+118h] [rbp+18h]
  int v85; // [rsp+120h] [rbp+20h]
  int v86; // [rsp+128h] [rbp+28h]
  __int64 *v87; // [rsp+130h] [rbp+30h]
  __int64 v88; // [rsp+138h] [rbp+38h]
  int v89; // [rsp+140h] [rbp+40h]
  int *v90; // [rsp+148h] [rbp+48h]
  unsigned int *v91; // [rsp+150h] [rbp+50h]
  int v92; // [rsp+158h] [rbp+58h]
  int v93; // [rsp+160h] [rbp+60h]
  __int64 *v94; // [rsp+168h] [rbp+68h]
  __int64 v95; // [rsp+170h] [rbp+70h]
  int v96; // [rsp+178h] [rbp+78h]
  int *v97; // [rsp+180h] [rbp+80h]
  unsigned int *v98; // [rsp+188h] [rbp+88h]
  int v99; // [rsp+190h] [rbp+90h]
  int v100; // [rsp+198h] [rbp+98h]
  __int64 *v101; // [rsp+1A0h] [rbp+A0h]
  __int64 v102; // [rsp+1A8h] [rbp+A8h]
  int v103; // [rsp+1B0h] [rbp+B0h]
  int *v104; // [rsp+1B8h] [rbp+B8h]
  unsigned int *v105; // [rsp+1C0h] [rbp+C0h]
  int v106; // [rsp+1C8h] [rbp+C8h]
  int v107; // [rsp+1D0h] [rbp+D0h]
  __int64 *v108; // [rsp+1D8h] [rbp+D8h]
  __int64 v109; // [rsp+1E0h] [rbp+E0h]
  int v110; // [rsp+1E8h] [rbp+E8h]
  int *v111; // [rsp+1F0h] [rbp+F0h]
  unsigned int *v112; // [rsp+1F8h] [rbp+F8h]
  int v113; // [rsp+200h] [rbp+100h]
  int v114; // [rsp+208h] [rbp+108h]
  __int64 *v115; // [rsp+210h] [rbp+110h]
  __int64 v116; // [rsp+218h] [rbp+118h]
  int v117; // [rsp+220h] [rbp+120h]
  int *v118; // [rsp+228h] [rbp+128h]
  unsigned int *v119; // [rsp+230h] [rbp+130h]
  int v120; // [rsp+238h] [rbp+138h]
  int v121; // [rsp+240h] [rbp+140h]
  __int64 *v122; // [rsp+248h] [rbp+148h]
  __int64 v123; // [rsp+250h] [rbp+150h]
  int v124; // [rsp+258h] [rbp+158h]
  int *v125; // [rsp+260h] [rbp+160h]
  unsigned int *v126; // [rsp+268h] [rbp+168h]
  int v127; // [rsp+270h] [rbp+170h]
  int v128; // [rsp+278h] [rbp+178h]
  __int64 *v129; // [rsp+280h] [rbp+180h]
  __int64 v130; // [rsp+288h] [rbp+188h]
  int v131; // [rsp+290h] [rbp+190h]
  int *v132; // [rsp+298h] [rbp+198h]
  unsigned int *v133; // [rsp+2A0h] [rbp+1A0h]
  int v134; // [rsp+2A8h] [rbp+1A8h]
  int v135; // [rsp+2B0h] [rbp+1B0h]
  __int64 *v136; // [rsp+2B8h] [rbp+1B8h]
  __int64 v137; // [rsp+2C0h] [rbp+1C0h]
  int v138; // [rsp+2C8h] [rbp+1C8h]
  int *v139; // [rsp+2D0h] [rbp+1D0h]
  unsigned int *v140; // [rsp+2D8h] [rbp+1D8h]
  int v141; // [rsp+2E0h] [rbp+1E0h]
  int v142; // [rsp+2E8h] [rbp+1E8h]
  __int64 *v143; // [rsp+2F0h] [rbp+1F0h]
  __int64 v144; // [rsp+2F8h] [rbp+1F8h]
  int v145; // [rsp+300h] [rbp+200h]
  int *v146; // [rsp+308h] [rbp+208h]
  unsigned int *v147; // [rsp+310h] [rbp+210h]
  int v148; // [rsp+318h] [rbp+218h]

  if ( this[6] )
  {
    v67 = 0;
    v75 = &v64;
    v66 = 0;
    v68 = 0;
    v65 = 0;
    v69 = 0;
    v73 = 0;
    v70 = 0;
    v71 = 0;
    v74 = 0;
    v64 = 0;
    ActivedLangBarThreadID = CLBIMProxy::GetActivedLangBarThreadID((CLBIMProxy *)this);
    v72 = 1;
    v62 = 0;
    v79 = 6;
    v81 = 0;
    v94 = &v66;
    v80 = &v75;
    v97 = &v62;
    v83 = &v72;
    v101 = &v68;
    v84 = &v72;
    v104 = &v62;
    v87 = &v67;
    v108 = &v65;
    v90 = &v62;
    v111 = &v62;
    v82 = 4;
    v115 = &v69;
    v118 = &v62;
    v122 = &v73;
    v85 = 0;
    v86 = 38;
    v88 = 0;
    v89 = 104;
    v91 = v75;
    v92 = 0;
    v93 = 38;
    v95 = 0;
    v96 = 4;
    v98 = v75;
    v99 = 0;
    v100 = 1078;
    v102 = 0;
    v103 = 8;
    v105 = v75;
    v106 = 0;
    v107 = 1078;
    v109 = 0;
    v110 = 8;
    v112 = v75;
    v113 = 0;
    v114 = 8246;
    v116 = 0;
    v117 = 8;
    v119 = v75;
    v120 = 0;
    v121 = 38;
    v123 = 0;
    v124 = 8;
    v142 = 38;
    v128 = 2102;
    v125 = &v62;
    v135 = 2102;
    v129 = &v70;
    v145 = 4;
    v132 = &v62;
    v126 = v75;
    v136 = &v71;
    v139 = &v62;
    v143 = &v74;
    v146 = &v62;
    v127 = 0;
    v130 = 0;
    v131 = 8;
    v133 = v75;
    v134 = 0;
    v137 = 0;
    v138 = 8;
    v140 = v75;
    v141 = 0;
    v144 = 0;
    v147 = v75;
    v148 = 0;
    LODWORD(v63) = 0;
    if ( (int)MsgBase::CalcParamMarshalingSize(1u, 0xAu, (struct tagCPROXY_PARAM *)&v79, (unsigned int *)&v63) >= 0
      && (v3 = (int)v63, v4 = (_DWORD)v63 + 72, (unsigned int)((_DWORD)v63 + 72) >= 0x48)
      && (v5 = LocalAlloc(0x40u, v4), (v6 = (struct MsgBase *)v5) != 0) )
    {
      if ( v4 > 0x200 )
      {
        v5[10] |= 0x4000000u;
        LOWORD(v4) = 72;
      }
      *((_WORD *)v5 + 1) = v4;
      *(_WORD *)v5 = v4 - 40;
      v5[14] = 10;
      v5[15] = v3;
      *((_QWORD *)v5 + 8) = v5 + 18;
      v5[10] |= 0xA0000028;
      CurrentThreadId = GetCurrentThreadId();
      *((_DWORD *)v6 + 12) = ActivedLangBarThreadID;
      *((_DWORD *)v6 + 11) = CurrentThreadId;
      v8 = MsgBase::Marshal(v6, 0xAu, (struct tagCPROXY_PARAM *)&v79);
      if ( v8 >= 0 )
      {
        Instance = CCtfClientPort::CreateInstance();
        v10 = Instance;
        if ( Instance )
        {
          v63 = 0;
          v8 = CCtfClientPort::SendAsync(Instance, v6, &v63);
          if ( v8 >= 0 )
          {
            v52 = v63;
            v8 = MsgBase::Unmarshal(v63, 0xAu, (struct tagCPROXY_PARAM *)&v79);
            if ( (*((_DWORD *)v52 + 10) & 0x4000000) != 0 )
              NtAlpcDeleteSectionView(*((_QWORD *)v10 + 1), 0, *((_QWORD *)v52 + 8));
            if ( v52 != v6 )
              cicMemFree(v52);
          }
          CCtfClientPort::Release(v10);
        }
        else
        {
          v8 = -2147467259;
        }
      }
      LocalFree(v6);
    }
    else
    {
      v8 = -2147024882;
    }
    for ( i = 0; (int)i < *((_DWORD *)this + 20); *(_DWORD *)(v13 + 32) |= 1u )
    {
      v12 = (int)i;
      i = (unsigned int)(i + 1);
      v13 = this[9][v12];
    }
    if ( v8 >= 0 )
    {
      v14 = 0;
      LODWORD(v63) = 0;
      if ( v64 )
      {
        while ( 1 )
        {
          if ( !this[6] )
            goto LABEL_32;
          v15 = 0;
          v16 = v14;
          while ( 1 )
          {
            v17 = v15 == *((_DWORD *)this + 20);
            if ( v15 >= *((_DWORD *)this + 20) )
              break;
            v18 = (__int64 *)this[9][v15];
            v19 = 104LL * v14;
            v20 = v18[7] - *(_QWORD *)(v19 + v67 + 16);
            if ( !v20 )
              v20 = v18[8] - *(_QWORD *)(v19 + v67 + 24);
            if ( !v20 )
            {
              v21 = v18[5] - *(_QWORD *)(v19 + v67);
              if ( !v21 )
                v21 = v18[6] - *(_QWORD *)(v19 + v67 + 8);
              if ( !v21
                && *((_DWORD *)v18 + 18) == *(_DWORD *)(v19 + v67 + 32)
                && *((_DWORD *)v18 + 19) == *(_DWORD *)(v19 + v67 + 36) )
              {
                lpString2 = (const WCHAR *)(v19 + v67 + 40);
                v23 = (const WCHAR *)CResStringCache::operator unsigned short *(v18 + 10, v67, i);
                if ( CompareStringW(0x7Fu, 0, v23, -1, lpString2, -1) == 2 )
                {
                  v53 = *v18;
                  v54 = *((_DWORD *)this + 25);
                  *((_DWORD *)v18 + 8) &= ~1u;
                  LOWORD(v61) = *(_WORD *)(v74 + 4LL * v14);
                  (*(void (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, __int64, _QWORD, _QWORD, int))(v53 + 144))(
                    v18,
                    ((v54 & 8) << 14) | 0x1003Fu,
                    *(unsigned int *)(v66 + 4LL * v14),
                    *(_QWORD *)(v65 + 8LL * v14),
                    *(_QWORD *)(v68 + 8LL * v14),
                    *(_QWORD *)(v69 + 8LL * v14),
                    v73 + 8LL * v14,
                    *(_QWORD *)(v70 + 8LL * v14),
                    *(_QWORD *)(v71 + 8LL * v14),
                    v61);
                  *(_QWORD *)(v69 + 8LL * v14) = 0;
                  *(_QWORD *)(v70 + 8LL * v14) = 0;
                  *(_QWORD *)(v71 + 8LL * v14) = 0;
                  v17 = v15 == *((_DWORD *)this + 20);
                  break;
                }
              }
            }
            ++v15;
          }
          if ( v17 )
            break;
LABEL_31:
          LODWORD(v63) = ++v14;
          if ( v14 >= v64 )
            goto LABEL_32;
        }
        switch ( *(_WORD *)(v74 + 4LL * v14 + 2) )
        {
          case 1:
            v27 = (char *)LocalAlloc(0x40u, 0xA8u);
            v28 = (CLanguageBarItemExtension *)v27;
            if ( !v27 )
              goto LABEL_31;
            v29 = v67;
            v30 = *(HICON *)(v69 + 8LL * v14);
            v31 = v67 + 40;
            v76 = *(unsigned __int16 **)(v68 + 8LL * v14);
            v77 = *(unsigned __int16 **)(v65 + 8LL * v14);
            v32 = *(_DWORD *)(v66 + 4LL * v14);
            *((_QWORD *)v27 + 1) = &CComObjectRootImmx_InternalReference::`vftable';
            *((_DWORD *)v27 + 4) = 1;
            *((_QWORD *)v27 + 3) = this + 1;
            *((_DWORD *)v27 + 9) = v32;
            *(_OWORD *)(v27 + 40) = *(_OWORD *)(104 * v16 + v29);
            *(_OWORD *)(v27 + 56) = *(_OWORD *)(104 * v16 + v29 + 16);
            *((_DWORD *)v27 + 18) = *(_DWORD *)(104 * v16 + v29 + 32);
            *((_DWORD *)v27 + 19) = *(_DWORD *)(104 * v16 + v29 + 36);
            v33 = *((_DWORD *)v27 + 20);
            *((_QWORD *)v28 + 11) = 0;
            *((_QWORD *)v28 + 19) = 0;
            *((_QWORD *)v28 + 12) = 0;
            *((_QWORD *)v28 + 13) = 0;
            *((_QWORD *)v28 + 10) = v33 & 0xFFFFFFFE;
            v34 = (_WORD *)(104 * v16 + v31);
            if ( !v34 )
              goto LABEL_58;
            v35 = 0x7FFFFFFF;
            v36 = v34;
            do
            {
              if ( !*v36 )
                break;
              ++v36;
              --v35;
            }
            while ( v35 );
            v37 = (0x7FFFFFFF - v35) & -(__int64)(v35 != 0);
            if ( !v35 || !v37 )
              goto LABEL_58;
            v38 = v37 + 1;
            v39 = LocalAlloc(0x40u, (unsigned int)(2 * v38));
            *((_QWORD *)v28 + 11) = v39;
            if ( v39 && v38 )
            {
              if ( v38 > 0x7FFFFFFF )
              {
                *v39 = 0;
              }
              else
              {
                v40 = 2147483646;
                do
                {
                  if ( !v40 )
                    break;
                  if ( !*v34 )
                    break;
                  *v39++ = *v34++;
                  --v40;
                  --v38;
                }
                while ( v38 );
                v41 = v39 - 1;
                if ( v38 )
                  v41 = v39;
                *v41 = 0;
                if ( v38 )
                {
                  *((_DWORD *)v28 + 20) |= 1u;
LABEL_58:
                  v42 = v77;
                  *(_QWORD *)v28 = &CLanguageBarItemButton::`vftable'{for `ITfSource'};
                  *((_QWORD *)v28 + 1) = &CLanguageBarItemBalloon::`vftable'{for `CComObjectRootImmx_InternalReference'};
                  *((_QWORD *)v28 + 20) = &CLanguageBarItemButton::`vftable';
                  CLanguageBarItem::Update((struct tagSIZE *)v28, 196615, v32, v42, v76, v30, 0, 0, 0, 0);
                  v14 = (unsigned int)v63;
                  goto LABEL_67;
                }
              }
            }
            cicMemFree(*((_QWORD *)v28 + 11));
            *((_QWORD *)v28 + 11) = 0;
            goto LABEL_58;
          case 2:
            v57 = (CLanguageBarItemBitmap *)LocalAlloc(0x40u, 0xA8u);
            if ( v57 )
            {
              v44 = CLanguageBarItemBitmap::CLanguageBarItemBitmap(
                      v57,
                      (struct ILanguageBarItemOwner *)(this + 1),
                      (struct TF_LANGBARITEMINFO *)(v67 + 104LL * v14),
                      *(_DWORD *)(v66 + 4LL * v14),
                      *(const unsigned __int16 **)(v65 + 8LL * v14),
                      (struct tagSIZE *)(v73 + 8LL * v14),
                      *(HBITMAP *)(v70 + 8LL * v14),
                      *(HBITMAP *)(v71 + 8LL * v14));
              goto LABEL_91;
            }
            break;
          case 3:
            v56 = (CLanguageBarItemBitmapButton *)LocalAlloc(0x40u, 0xA8u);
            if ( v56 )
            {
              v44 = CLanguageBarItemBitmapButton::CLanguageBarItemBitmapButton(
                      v56,
                      (struct ILanguageBarItemOwner *)(this + 1),
                      (struct TF_LANGBARITEMINFO *)(v67 + 104LL * v14),
                      *(_DWORD *)(v66 + 4LL * v14),
                      *(const unsigned __int16 **)(v65 + 8LL * v14),
                      *(const unsigned __int16 **)(v68 + 8LL * v14),
                      (struct tagSIZE *)(v73 + 8LL * v14),
                      *(HBITMAP *)(v70 + 8LL * v14),
                      *(HBITMAP *)(v71 + 8LL * v14));
              goto LABEL_91;
            }
            break;
          case 4:
            v55 = (CLanguageBarItemBalloon *)LocalAlloc(0x40u, 0xA8u);
            if ( v55 )
            {
              v44 = CLanguageBarItemBalloon::CLanguageBarItemBalloon(
                      v55,
                      (struct ILanguageBarItemOwner *)(this + 1),
                      (struct TF_LANGBARITEMINFO *)(v67 + 104LL * v14),
                      *(_DWORD *)(v66 + 4LL * v14),
                      *(const unsigned __int16 **)(v65 + 8LL * v14),
                      *(const unsigned __int16 **)(v68 + 8LL * v14),
                      (struct tagSIZE *)(v73 + 8LL * v14),
                      *(_WORD *)(v74 + 4LL * v14));
              goto LABEL_91;
            }
            break;
          case 0x3001:
            v43 = (CLanguageBarItemExtension *)LocalAlloc(0x40u, 0xB8u);
            if ( v43 )
            {
              v44 = CLanguageBarItemExtension::CLanguageBarItemExtension(
                      v43,
                      (struct ILanguageBarItemOwner *)(this + 1),
                      (struct TF_LANGBARITEMINFO *)(v67 + 104LL * v14),
                      *(_DWORD *)(v66 + 4LL * v14),
                      *(const unsigned __int16 **)(v65 + 8LL * v14),
                      *(const unsigned __int16 **)(v68 + 8LL * v14),
                      *(HICON *)(v69 + 8LL * v14));
LABEL_91:
              v28 = v44;
              goto LABEL_66;
            }
            break;
          default:
            goto LABEL_31;
        }
        v28 = 0;
LABEL_66:
        if ( !v28 )
          goto LABEL_31;
LABEL_67:
        if ( !this[6] )
          goto LABEL_29;
        v45 = (*(__int64 (__fastcall **)(CLanguageBarItemExtension *))(*(_QWORD *)v28 + 160LL))(v28);
        v63 = 0;
        if ( v45 == 5 )
        {
          v50 = this[6];
          v47 = -2147467259;
          v51 = *v50;
          v78 = *(_OWORD *)((char *)v28 + 56);
          if ( (*(int (__fastcall **)(__int64 *, __int128 *, struct MsgBase **))(v51 + 32))(v50, &v78, &v63) >= 0 )
            v47 = (*(__int64 (__fastcall **)(CLanguageBarItemExtension *, struct MsgBase *))(*(_QWORD *)v28 + 168LL))(
                    v28,
                    v63);
          if ( v63 )
          {
            v48 = *(void (**)(void))(*(_QWORD *)v63 + 16LL);
            goto LABEL_71;
          }
        }
        else
        {
          (**(void (__fastcall ***)(CLanguageBarItemExtension *, GUID *, struct MsgBase **))v28)(
            v28,
            &GUID_73540d69_edeb_4ee9_96c9_23aa30b25916,
            &v63);
          v47 = (*(__int64 (__fastcall **)(__int64 *, struct MsgBase *))(*this[6] + 40))(this[6], v63);
          if ( v63 )
          {
            v48 = *(void (**)(void))(*(_QWORD *)v63 + 16LL);
LABEL_71:
            v48();
          }
        }
        if ( v47 >= 0 )
        {
          v49 = CVoidPtrArray::Append((CVoidPtrArray *)(this + 8), v46);
          if ( v49 )
          {
            *v49 = v28;
            goto LABEL_30;
          }
        }
LABEL_29:
        (*(void (__fastcall **)(CLanguageBarItemExtension *))(*(_QWORD *)v28 + 16LL))(v28);
LABEL_30:
        *(_QWORD *)(v69 + 8 * v16) = 0;
        *(_QWORD *)(v70 + 8 * v16) = 0;
        *(_QWORD *)(v71 + 8 * v16) = 0;
        goto LABEL_31;
      }
    }
LABEL_32:
    for ( j = 0; j < *((_DWORD *)this + 20); ++j )
    {
      v25 = this[9];
      v26 = (__int64 *)v25[j];
      if ( (v26[4] & 1) != 0 )
      {
        CLBIMProxy::RemoveItem((CLBIMProxy *)this, (struct CLanguageBarItem *)v25[j]);
        v58 = j--;
        CVoidPtrArray::Remove((CVoidPtrArray *)(this + 8), v58, v59);
        v60 = *v26;
        v26[3] = 0;
        (*(void (__fastcall **)(__int64 *))(v60 + 16))(v26);
      }
    }
    CleanUpAutoParams(0xAu, (struct tagCPROXY_PARAM *)&v79);
  }
}

```

## disassembly

```asm
0x18002dd14  push    rbp
0x18002dd16  push    rbx
0x18002dd17  push    rsi
0x18002dd18  push    rdi
0x18002dd19  push    r12
0x18002dd1b  push    r13
0x18002dd1d  push    r14
0x18002dd1f  push    r15
0x18002dd21  lea     rbp, [rsp-238h]
0x18002dd29  sub     rsp, 338h
0x18002dd30  mov     rax, cs:__security_cookie
0x18002dd37  xor     rax, rsp
0x18002dd3a  mov     [rbp+270h+var_50], rax
0x18002dd41  xor     r13d, r13d
0x18002dd44  mov     rdi, rcx
0x18002dd47  cmp     [rcx+30h], r13
0x18002dd4b  jz      loc_18002E207
0x18002dd51  lea     rax, [rsp+370h+var_300]
0x18002dd56  mov     [rbp+270h+var_2E8], r13
0x18002dd5a  mov     [rbp+270h+var_2A8], rax
0x18002dd5e  mov     [rbp+270h+var_2F0], r13
0x18002dd62  mov     [rbp+270h+var_2E0], r13
0x18002dd66  mov     [rsp+370h+var_2F8], r13
0x18002dd6b  mov     [rbp+270h+var_2D8], r13
0x18002dd6f  mov     [rbp+270h+var_2B8], r13
0x18002dd73  mov     [rbp+270h+var_2D0], r13
0x18002dd77  mov     [rbp+270h+var_2C8], r13
0x18002dd7b  mov     [rbp+270h+var_2B0], r13
0x18002dd7f  mov     [rsp+370h+var_300], r13d
0x18002dd84  call    ?GetActivedLangBarThreadID@CLBIMProxy@@AEAAKXZ; CLBIMProxy::GetActivedLangBarThreadID(void)
0x18002dd89  mov     r15d, eax
0x18002dd8c  mov     [rbp+270h+var_2C0], 1
0x18002dd93  lea     r10d, [r13+8]
0x18002dd97  mov     [rsp+370h+var_310], r13d
0x18002dd9c  lea     r8d, [r13+26h]
0x18002dda0  mov     [rbp+270h+var_280], 6
0x18002dda7  lea     rcx, [rbp+270h+var_2F0]
0x18002ddab  mov     [rbp+270h+var_270], r13
0x18002ddaf  mov     [rbp+270h+var_208], rcx
0x18002ddb3  lea     rax, [rbp+270h+var_2A8]
0x18002ddb7  mov     [rbp+270h+var_278], rax
0x18002ddbb  lea     rcx, [rsp+370h+var_310]
0x18002ddc0  mov     [rbp+270h+var_1F0], rcx
0x18002ddc7  lea     rax, [rbp+270h+var_2C0]
0x18002ddcb  mov     [rbp+270h+var_260], rax
0x18002ddcf  lea     rcx, [rbp+270h+var_2E0]
0x18002ddd3  mov     [rbp+270h+var_1D0], rcx
0x18002ddda  lea     rax, [rbp+270h+var_2C0]
0x18002ddde  mov     [rbp+270h+var_258], rax
0x18002dde2  lea     rcx, [rsp+370h+var_310]
0x18002dde7  mov     [rbp+270h+var_1B8], rcx
0x18002ddee  lea     rax, [rbp+270h+var_2E8]
0x18002ddf2  lea     rcx, [rsp+370h+var_2F8]
0x18002ddf7  mov     [rbp+270h+var_240], rax
0x18002ddfb  mov     [rbp+270h+var_198], rcx
0x18002de02  lea     rax, [rsp+370h+var_310]
0x18002de07  lea     rcx, [rsp+370h+var_310]
0x18002de0c  mov     [rbp+270h+var_228], rax
0x18002de10  mov     rax, [rbp+270h+var_2A8]
0x18002de14  lea     r9d, [r13+4]
0x18002de18  mov     [rbp+270h+var_180], rcx
0x18002de1f  mov     edx, 436h
0x18002de24  lea     rcx, [rbp+270h+var_2D8]
0x18002de28  mov     [rbp+270h+var_268], r9d
0x18002de2c  mov     [rbp+270h+var_160], rcx
0x18002de33  lea     rcx, [rsp+370h+var_310]
0x18002de38  mov     [rbp+270h+var_148], rcx
0x18002de3f  lea     rcx, [rbp+270h+var_2B8]
0x18002de43  mov     [rbp+270h+var_128], rcx
0x18002de4a  mov     [rbp+270h+var_250], r13d
0x18002de4e  mov     [rbp+270h+var_248], r8d
0x18002de52  mov     [rbp+270h+var_238], r13
0x18002de56  mov     [rbp+270h+var_230], 68h ; 'h'
0x18002de5d  mov     [rbp+270h+var_220], rax
0x18002de61  mov     [rbp+270h+var_218], r13d
0x18002de65  mov     [rbp+270h+var_210], r8d
0x18002de69  mov     [rbp+270h+var_200], r13
0x18002de6d  mov     [rbp+270h+var_1F8], r9d
0x18002de71  mov     [rbp+270h+var_1E8], rax
0x18002de78  mov     [rbp+270h+var_1E0], r13d
0x18002de7f  mov     [rbp+270h+var_1D8], edx
0x18002de85  mov     [rbp+270h+var_1C8], r13
0x18002de8c  mov     [rbp+270h+var_1C0], r10d
0x18002de93  mov     [rbp+270h+var_1B0], rax
0x18002de9a  mov     [rbp+270h+var_1A8], r13d
0x18002dea1  mov     [rbp+270h+var_1A0], edx
0x18002dea7  mov     [rbp+270h+var_190], r13
0x18002deae  mov     [rbp+270h+var_188], r10d
0x18002deb5  mov     [rbp+270h+var_178], rax
0x18002debc  mov     [rbp+270h+var_170], r13d
0x18002dec3  mov     [rbp+270h+var_168], 2036h
0x18002decd  mov     [rbp+270h+var_158], r13
0x18002ded4  mov     [rbp+270h+var_150], r10d
0x18002dedb  mov     [rbp+270h+var_140], rax
0x18002dee2  mov     [rbp+270h+var_138], r13d
0x18002dee9  mov     [rbp+270h+var_130], r8d
0x18002def0  mov     [rbp+270h+var_120], r13
0x18002def7  mov     [rbp+270h+var_118], r10d
0x18002defe  mov     edx, 836h
0x18002df03  mov     [rbp+270h+var_88], r8d
0x18002df0a  lea     rcx, [rsp+370h+var_310]
0x18002df0f  mov     [rbp+270h+var_F8], edx
0x18002df15  mov     [rbp+270h+var_110], rcx
0x18002df1c  lea     r8, [rbp+270h+var_280]; struct tagCPROXY_PARAM *
0x18002df20  lea     rcx, [rbp+270h+var_2D0]
0x18002df24  mov     [rbp+270h+var_C0], edx
0x18002df2a  mov     [rbp+270h+var_F0], rcx
0x18002df31  lea     edx, [r13+0Ah]; unsigned int
0x18002df35  lea     rcx, [rsp+370h+var_310]
0x18002df3a  mov     [rbp+270h+var_70], r9d
0x18002df41  mov     [rbp+270h+var_D8], rcx
0x18002df48  lea     r9, [rsp+370h+var_308]; unsigned int *
0x18002df4d  lea     rcx, [rbp+270h+var_2C8]
0x18002df51  mov     [rbp+270h+var_108], rax
0x18002df58  mov     [rbp+270h+var_B8], rcx
0x18002df5f  lea     rcx, [rsp+370h+var_310]
0x18002df64  mov     [rbp+270h+var_A0], rcx
0x18002df6b  lea     rcx, [rbp+270h+var_2B0]
0x18002df6f  mov     [rbp+270h+var_80], rcx
0x18002df76  lea     rcx, [rsp+370h+var_310]
0x18002df7b  mov     [rbp+270h+var_68], rcx
0x18002df82  lea     ecx, [rdx-9]; unsigned int
0x18002df85  mov     [rbp+270h+var_100], r13d
0x18002df8c  mov     [rbp+270h+var_E8], r13
0x18002df93  mov     [rbp+270h+var_E0], r10d
0x18002df9a  mov     [rbp+270h+var_D0], rax
0x18002dfa1  mov     [rbp+270h+var_C8], r13d
0x18002dfa8  mov     [rbp+270h+var_B0], r13
0x18002dfaf  mov     [rbp+270h+var_A8], r10d
0x18002dfb6  mov     [rbp+270h+var_98], rax
0x18002dfbd  mov     [rbp+270h+var_90], r13d
0x18002dfc4  mov     [rbp+270h+var_78], r13
0x18002dfcb  mov     [rbp+270h+var_60], rax
0x18002dfd2  mov     [rbp+270h+var_58], r13d
0x18002dfd9  mov     dword ptr [rsp+370h+var_308], r13d
0x18002dfde  call    ?CalcParamMarshalingSize@MsgBase@@SAJKKPEAUtagCPROXY_PARAM@@AEAK@Z; MsgBase::CalcParamMarshalingSize(ulong,ulong,tagCPROXY_PARAM *,ulong &)
0x18002dfe3  test    eax, eax
0x18002dfe5  js      loc_18002E497
0x18002dfeb  mov     r14d, dword ptr [rsp+370h+var_308]
0x18002dff0  lea     r12d, [r13+48h]
0x18002dff4  lea     esi, [r14+48h]
0x18002dff8  cmp     esi, r12d
0x18002dffb  jb      loc_18002E497
0x18002e001  mov     edx, esi; uBytes
0x18002e003  lea     ecx, [r13+40h]; uFlags
0x18002e007  call    cs:__imp_LocalAlloc
0x18002e00d  mov     rbx, rax
0x18002e010  test    rax, rax
0x18002e013  jz      loc_18002E497
0x18002e019  cmp     esi, 200h
0x18002e01f  ja      loc_18002E579
0x18002e025  mov     [rax+2], si
0x18002e029  sub     si, 28h ; '('
0x18002e02d  mov     [rax], si
0x18002e030  mov     dword ptr [rax+38h], 0Ah
0x18002e037  mov     [rax+3Ch], r14d
0x18002e03b  add     rax, r12
0x18002e03e  mov     [rbx+40h], rax
0x18002e042  or      dword ptr [rbx+28h], 0A0000028h
0x18002e049  call    cs:__imp_GetCurrentThreadId
0x18002e04f  lea     r8, [rbp+270h+var_280]; struct tagCPROXY_PARAM *
0x18002e053  mov     [rbx+30h], r15d
0x18002e057  mov     edx, 0Ah; unsigned int
0x18002e05c  mov     [rbx+2Ch], eax
0x18002e05f  mov     rcx, rbx; struct MsgBase *
0x18002e062  call    ?Marshal@MsgBase@@SAJPEAU1@KPEAUtagCPROXY_PARAM@@@Z; MsgBase::Marshal(MsgBase *,ulong,tagCPROXY_PARAM *)
0x18002e067  mov     esi, eax
0x18002e069  test    eax, eax
0x18002e06b  js      short loc_18002E0A5
0x18002e06d  call    ?CreateInstance@CCtfClientPort@@SAPEAV1@XZ; CCtfClientPort::CreateInstance(void)
0x18002e072  mov     r15, rax
0x18002e075  test    rax, rax
0x18002e078  jz      loc_18002E5CF
0x18002e07e  lea     r8, [rsp+370h+var_308]; struct MsgBase **
0x18002e083  mov     [rsp+370h+var_308], r13
0x18002e088  mov     rdx, rbx; struct MsgBase *
0x18002e08b  mov     rcx, rax; this
0x18002e08e  call    ?SendAsync@CCtfClientPort@@QEAAJPEAUMsgBase@@PEAPEAU2@@Z; CCtfClientPort::SendAsync(MsgBase *,MsgBase * *)
0x18002e093  mov     esi, eax
0x18002e095  test    eax, eax
0x18002e097  jns     loc_18002E587
0x18002e09d  mov     rcx, r15; this
0x18002e0a0  call    ?Release@CCtfClientPort@@QEAAKXZ; CCtfClientPort::Release(void)
0x18002e0a5  mov     rcx, rbx; hMem
0x18002e0a8  call    cs:__imp_LocalFree
0x18002e0ae  mov     r8d, r13d
0x18002e0b1  cmp     [rdi+50h], r13d
0x18002e0b5  jle     short loc_18002E0CF
0x18002e0b7  mov     rax, [rdi+48h]
0x18002e0bb  movsxd  rcx, r8d
0x18002e0be  inc     r8d
0x18002e0c1  mov     rdx, [rax+rcx*8]
0x18002e0c5  or      dword ptr [rdx+20h], 1
0x18002e0c9  cmp     r8d, [rdi+50h]
0x18002e0cd  jl      short loc_18002E0B7
0x18002e0cf  test    esi, esi
0x18002e0d1  js      loc_18002E1D4
0x18002e0d7  mov     r12d, r13d
0x18002e0da  mov     dword ptr [rsp+370h+var_308], r13d
0x18002e0df  cmp     [rsp+370h+var_300], r13d
0x18002e0e4  jbe     loc_18002E1D4
0x18002e0ea  cmp     [rdi+30h], r13
0x18002e0ee  jz      loc_18002E1D4
0x18002e0f4  mov     r15d, r13d
0x18002e0f7  mov     esi, r12d
0x18002e0fa  cmp     r15d, [rdi+50h]
0x18002e0fe  jge     loc_18002E22A
0x18002e104  mov     rax, [rdi+48h]
0x18002e108  mov     rdx, [rbp+270h+var_2E8]
0x18002e10c  movsxd  rcx, r15d
0x18002e10f  mov     r14, [rax+rcx*8]
0x18002e113  imul    rcx, rsi, 68h ; 'h'
0x18002e117  mov     rax, [r14+38h]
0x18002e11b  sub     rax, [rcx+rdx+10h]
0x18002e120  jnz     short loc_18002E12B
0x18002e122  mov     rax, [r14+40h]
0x18002e126  sub     rax, [rcx+rdx+18h]
0x18002e12b  test    rax, rax
0x18002e12e  jnz     short loc_18002E192
0x18002e130  mov     rax, [r14+28h]
0x18002e134  sub     rax, [rcx+rdx]
0x18002e138  jnz     short loc_18002E143
0x18002e13a  mov     rax, [r14+30h]
0x18002e13e  sub     rax, [rcx+rdx+8]
0x18002e143  test    rax, rax
0x18002e146  jnz     short loc_18002E192
0x18002e148  mov     eax, [rcx+rdx+20h]
0x18002e14c  cmp     [r14+48h], eax
0x18002e150  jnz     short loc_18002E192
0x18002e152  mov     eax, [rcx+rdx+24h]
0x18002e156  cmp     [r14+4Ch], eax
0x18002e15a  jnz     short loc_18002E192
0x18002e15c  lea     rbx, [rdx+28h]
0x18002e160  add     rbx, rcx
0x18002e163  lea     rcx, [r14+50h]
0x18002e167  call    ??BCResStringCache@@QEAAPEAGXZ; CResStringCache::operator ushort *(void)
0x18002e16c  xor     edx, edx; dwCmpFlags
0x18002e16e  mov     r8, rax; lpString1
0x18002e171  or      eax, 0FFFFFFFFh
0x18002e174  mov     [rsp+370h+cchCount2], eax; cchCount2
0x18002e178  mov     r9d, eax; cchCount1
0x18002e17b  mov     [rsp+370h+lpString2], rbx; lpString2
0x18002e180  lea     ecx, [rdx+7Fh]; Locale
0x18002e183  call    cs:__imp_CompareStringW
0x18002e189  cmp     eax, 2
0x18002e18c  jz      loc_18002E5D9
0x18002e192  inc     r15d
0x18002e195  jmp     loc_18002E0FA
0x18002e19a  mov     rax, [rbx]
0x18002e19d  mov     rcx, rbx
0x18002e1a0  mov     rax, [rax+10h]
0x18002e1a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e1a9  mov     rax, [rbp+270h+var_2D8]
0x18002e1ad  mov     [rax+rsi*8], r13
0x18002e1b1  mov     rax, [rbp+270h+var_2D0]
0x18002e1b5  mov     [rax+rsi*8], r13
0x18002e1b9  mov     rax, [rbp+270h+var_2C8]
0x18002e1bd  mov     [rax+rsi*8], r13
0x18002e1c1  inc     r12d
0x18002e1c4  mov     dword ptr [rsp+370h+var_308], r12d
0x18002e1c9  cmp     r12d, [rsp+370h+var_300]
0x18002e1ce  jb      loc_18002E0EA
0x18002e1d4  mov     ebx, r13d
0x18002e1d7  cmp     [rdi+50h], r13d
0x18002e1db  jle     short loc_18002E1F9
0x18002e1dd  mov     rax, [rdi+48h]
0x18002e1e1  movsxd  rcx, ebx
0x18002e1e4  mov     rsi, [rax+rcx*8]
0x18002e1e8  test    byte ptr [rsi+20h], 1
0x18002e1ec  jnz     loc_18002E81D
0x18002e1f2  inc     ebx
0x18002e1f4  cmp     ebx, [rdi+50h]
0x18002e1f7  jl      short loc_18002E1DD
0x18002e1f9  lea     rdx, [rbp+270h+var_280]; struct tagCPROXY_PARAM *
0x18002e1fd  mov     ecx, 0Ah; unsigned int
0x18002e202  call    ?CleanUpAutoParams@@YAXKPEAUtagCPROXY_PARAM@@@Z; CleanUpAutoParams(ulong,tagCPROXY_PARAM *)
0x18002e207  mov     rcx, [rbp+270h+var_50]
0x18002e20e  xor     rcx, rsp; StackCookie
0x18002e211  call    __security_check_cookie
0x18002e216  add     rsp, 338h
0x18002e21d  pop     r15
0x18002e21f  pop     r14
0x18002e221  pop     r13
0x18002e223  pop     r12
0x18002e225  pop     rdi
0x18002e226  pop     rsi
0x18002e227  pop     rbx
0x18002e228  pop     rbp
0x18002e229  retn
0x18002e22a  jnz     short loc_18002E1C1
0x18002e22c  mov     rax, [rbp+270h+var_2B0]
0x18002e230  movzx   ecx, word ptr [rax+rsi*4+2]
0x18002e235  sub     ecx, 1
0x18002e238  jnz     loc_18002E40D
0x18002e23e  mov     edx, 0A8h; uBytes
0x18002e243  lea     ecx, [rdx-68h]; uFlags
0x18002e246  call    cs:__imp_LocalAlloc
0x18002e24c  mov     rbx, rax
0x18002e24f  test    rax, rax
0x18002e252  jz      loc_18002E1C1
  ... truncated ...
```
