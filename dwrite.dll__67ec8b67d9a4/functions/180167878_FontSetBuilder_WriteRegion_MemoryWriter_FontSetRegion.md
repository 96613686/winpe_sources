# FontSetBuilder::WriteRegion(MemoryWriter<FontSetRegion> &)

- ea: `0x180167878`
- end: `0x180169050`
- name: `?WriteRegion@FontSetBuilder@@QEAAXAEAV?$MemoryWriter@VFontSetRegion@@@@@Z`
- size: `6104`
- prototype: ``
- caller_count: `2`
- callee_count: `61`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180132cf0`
- `0x1801e453c`

## callees

- `0x18011df20`
- `0x18011ef30`
- `0x1801476c0`
- `0x180148b50`
- `0x180149e04`
- `0x18014ad5c`
- `0x18014ae00`
- `0x18014c7c4`
- `0x18014c864`
- `0x18014f880`
- `0x1801537f8`
- `0x1801644d0`
- `0x180165ef4`
- `0x180167278`
- `0x180167320`
- `0x180167878`
- `0x180169060`
- `0x18016933c`
- `0x1801693bc`
- `0x180169660`
- `0x18016a248`
- `0x1801bbe90`
- `0x1801bcadc`
- `0x1801bcb1c`
- `0x1801c56cc`
- `0x1801d94e8`
- `0x1801d9d70`
- `0x1801dc158`
- `0x1801dc56c`
- `0x1801ee258`
- `0x1801ef8d4`
- `0x1801efaac`
- `0x1801f33e8`
- `0x1801f37b0`
- `0x1801f9280`
- `0x1801fa81c`
- `0x1801fccf8`
- `0x1801ff0e4`
- `0x18020032c`
- `0x18020068c`
- `0x180201d4c`
- `0x180201e78`
- `0x180203ac8`
- `0x180204f20`
- `0x1802066a4`
- `0x18020a808`
- `0x18020d19c`
- `0x180212490`
- `0x180212a70`
- `0x180212e0a`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180168054`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1801681f7`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1801682e3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1801689dd`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180168c09`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180168cc5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180168efa`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180168f23`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180168f97`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180168ff8`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180169034`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180168054`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1801681f7`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1801682e3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1801689dd`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180168c09`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180168cc5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180168efa`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180168f23`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180168f97`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180168ff8`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180169034`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18016877c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18016877c`

## pseudocode

```c
// Hidden C++ exception states: #wind=54
void __fastcall FontSetBuilder::WriteRegion(__int64 a1, MemoryWriterImpl *a2)
{
  MemoryWriterImpl *v2; // r13
  __int64 v3; // rsi
  __int64 v4; // r8
  unsigned int v5; // eax
  const char *v6; // rdx
  __int64 v7; // r8
  unsigned __int64 v8; // rdi
  unsigned __int64 v9; // rcx
  __int64 v10; // r14
  const char *v11; // rdx
  __int64 v12; // rbx
  unsigned int v13; // ecx
  unsigned __int64 v14; // rdi
  unsigned __int64 v15; // rax
  int v16; // ebx
  unsigned int *v17; // rax
  unsigned __int64 v18; // rax
  __int64 v19; // rdx
  int *v20; // r12
  int *i; // rsi
  _QWORD *v22; // rbx
  _QWORD *v23; // rdx
  __int64 v24; // rcx
  void *v25; // rcx
  __int64 v26; // r15
  __int64 v27; // rbx
  _QWORD *v28; // r8
  unsigned __int64 j; // rcx
  __int16 v30; // dx
  unsigned __int64 k; // r9
  __int16 v32; // dx
  __int64 v33; // r15
  unsigned int v34; // eax
  unsigned __int64 v35; // rsi
  unsigned __int64 m; // r13
  __int64 v37; // rcx
  __int64 v38; // r12
  const void *v39; // r15
  unsigned int v40; // ecx
  unsigned __int64 v41; // rax
  unsigned __int64 v42; // rcx
  _DWORD *v43; // rax
  __int64 v44; // rdx
  __int64 v45; // r9
  _WORD *v46; // rbx
  size_t v47; // r8
  void *v48; // rcx
  const char *v49; // rdx
  size_t v50; // r8
  unsigned __int64 v51; // rsi
  unsigned int v52; // r10d
  _DWORD *v53; // r9
  unsigned int v54; // ecx
  char *v55; // rdx
  unsigned __int64 n; // r13
  __int64 v57; // rcx
  __int64 v58; // r12
  unsigned __int64 v59; // rdi
  const void *v60; // r15
  unsigned int v61; // ecx
  unsigned __int64 v62; // rax
  unsigned __int64 v63; // rcx
  _DWORD *v64; // rax
  __int64 v65; // rdx
  __int64 v66; // r9
  _WORD *v67; // rbx
  size_t v68; // r8
  void *v69; // rcx
  unsigned int v70; // ecx
  unsigned __int64 v71; // rax
  unsigned __int64 v72; // rcx
  char *v73; // r9
  int v74; // eax
  const char *v75; // rdx
  __int64 v76; // r9
  __int64 v77; // rcx
  __int64 v78; // rax
  __int64 v79; // rcx
  unsigned __int64 v80; // r10
  unsigned __int16 *v81; // r8
  unsigned int v82; // edx
  unsigned int v83; // ecx
  void *v84; // rcx
  _QWORD *v85; // rbx
  const void *v86; // rsi
  const void *v87; // rdi
  unsigned __int64 v88; // rcx
  unsigned int v89; // ebx
  __int64 v90; // r8
  int v91; // eax
  unsigned int ArrayOffset; // eax
  void *v93; // rcx
  unsigned int v94; // r8d
  _QWORD *v95; // rax
  __int64 v96; // rdx
  __int64 v97; // rbx
  __int64 v98; // rsi
  unsigned int v99; // r12d
  volatile signed __int32 *v100; // r15
  volatile signed __int32 **v101; // rdx
  __int64 v102; // rcx
  volatile signed __int32 *v103; // rdi
  struct DWrite::RefString::Data *v104; // rcx
  volatile signed __int32 **v105; // rdx
  __int64 v106; // r9
  __int64 ii; // r12
  __int64 v108; // rcx
  StringToIndexList *v109; // r8
  unsigned __int64 v110; // rcx
  unsigned __int64 v111; // rcx
  char *v112; // r8
  char *v113; // rdx
  _DWORD *v114; // r8
  char *v115; // rcx
  __int64 v116; // rax
  __int64 v117; // r8
  __int64 v118; // r9
  const WCHAR *v119; // r10
  unsigned __int64 v120; // rcx
  unsigned int v121; // r9d
  int v122; // eax
  bool v123; // zf
  const void *v124; // r12
  unsigned int v125; // ebx
  volatile signed __int32 *v126; // rbx
  void *v127; // r8
  void *v128; // rcx
  __int64 v129; // rax
  signed __int64 v130; // rdi
  MemoryWriterImpl *v131; // r12
  __int64 v132; // rcx
  unsigned int v133; // esi
  unsigned __int64 v134; // r13
  unsigned __int64 v135; // r14
  __int64 v136; // rbx
  __int64 v137; // r8
  unsigned __int64 v138; // rcx
  __int64 v139; // r8
  unsigned int v140; // edx
  unsigned __int64 v141; // rax
  unsigned __int64 v142; // rdx
  __int64 *v143; // rcx
  size_t v144; // r8
  __int64 v145; // rsi
  __int64 v146; // rbx
  _QWORD *v147; // rax
  __int64 v148; // r14
  MemoryWriterImpl *v149; // r13
  int v150; // ebx
  unsigned int jj; // r15d
  __int64 v152; // rdi
  __int64 v153; // rdx
  unsigned int v154; // eax
  char *v155; // r9
  unsigned int v156; // edx
  unsigned __int64 v157; // rcx
  const char *v158; // rdx
  char *v159; // rcx
  const char *v160; // rdx
  __int64 v161; // r9
  unsigned int v162; // eax
  char *v163; // rcx
  void *v164; // rbx
  void *v165; // rbx
  const struct FontNameList *v166; // rdx
  FontNameList *v167; // rcx
  const struct FontNameList *v168; // rdx
  FontNameList *v169; // rcx
  size_t v170; // r8
  __int64 v171; // rdx
  __int64 v172; // rcx
  __int64 v173; // r8
  __int64 v174; // r9
  __int64 v175; // rdx
  __int64 v176; // rcx
  __int64 v177; // r8
  __int64 v178; // r9
  __int64 v179; // rbx
  __int64 v180; // rdx
  __int64 v181; // rcx
  __int64 v182; // r8
  __int64 v183; // r9
  __int64 v184; // rdx
  __int64 v185; // rcx
  __int64 v186; // r8
  __int64 v187; // r9
  size_t Size; // [rsp+30h] [rbp-D0h] BYREF
  char v189; // [rsp+38h] [rbp-C8h]
  unsigned int v190; // [rsp+3Ch] [rbp-C4h] BYREF
  unsigned int v191; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v192; // [rsp+48h] [rbp-B8h]
  void *v193; // [rsp+50h] [rbp-B0h] BYREF
  void *Src[2]; // [rsp+58h] [rbp-A8h] BYREF
  char *v195; // [rsp+68h] [rbp-98h]
  __int128 Source; // [rsp+70h] [rbp-90h] BYREF
  MemoryWriterImpl *v197; // [rsp+80h] [rbp-80h]
  __int64 v198; // [rsp+88h] [rbp-78h]
  unsigned __int64 v199; // [rsp+90h] [rbp-70h] BYREF
  StringToIndexList *v200; // [rsp+98h] [rbp-68h] BYREF
  StringToIndexList *v201; // [rsp+A0h] [rbp-60h]
  StringToIndexList *v202; // [rsp+A8h] [rbp-58h]
  char *v203; // [rsp+B0h] [rbp-50h]
  void *v204; // [rsp+B8h] [rbp-48h] BYREF
  char *v205; // [rsp+C0h] [rbp-40h]
  void *v206; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v207; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v208; // [rsp+D8h] [rbp-28h]
  volatile signed __int32 *v209; // [rsp+E0h] [rbp-20h] BYREF
  void *v210; // [rsp+E8h] [rbp-18h]
  void *v211; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v212; // [rsp+F8h] [rbp-8h] BYREF
  int v213; // [rsp+100h] [rbp+0h]
  int v214; // [rsp+108h] [rbp+8h]
  volatile signed __int32 *v215; // [rsp+110h] [rbp+10h] BYREF
  unsigned int v216; // [rsp+118h] [rbp+18h]
  int v217; // [rsp+11Ch] [rbp+1Ch]
  unsigned int v218; // [rsp+120h] [rbp+20h]
  __int64 v219; // [rsp+128h] [rbp+28h]
  void *v220; // [rsp+130h] [rbp+30h] BYREF
  unsigned int v221; // [rsp+138h] [rbp+38h]
  int v222; // [rsp+13Ch] [rbp+3Ch]
  unsigned __int64 v223; // [rsp+140h] [rbp+40h]
  _WORD *v224; // [rsp+148h] [rbp+48h] BYREF
  char *v225; // [rsp+150h] [rbp+50h]
  unsigned __int64 v226; // [rsp+158h] [rbp+58h]
  _QWORD v227[5]; // [rsp+168h] [rbp+68h] BYREF
  _QWORD v228[3]; // [rsp+190h] [rbp+90h] BYREF
  unsigned __int64 v229; // [rsp+1A8h] [rbp+A8h]
  __int128 v230; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v231; // [rsp+1C0h] [rbp+C0h]
  __int64 v232; // [rsp+1C8h] [rbp+C8h]
  void *Block; // [rsp+1D0h] [rbp+D0h]
  _DWORD v234[20]; // [rsp+1E0h] [rbp+E0h] BYREF
  _QWORD v235[3]; // [rsp+230h] [rbp+130h] BYREF
  _QWORD v236[3]; // [rsp+248h] [rbp+148h] BYREF
  _QWORD v237[3]; // [rsp+260h] [rbp+160h] BYREF
  _QWORD v238[30]; // [rsp+278h] [rbp+178h] BYREF
  _QWORD v239[7]; // [rsp+368h] [rbp+268h] BYREF
  _QWORD v240[15]; // [rsp+3A0h] [rbp+2A0h] BYREF
  char v241[8]; // [rsp+418h] [rbp+318h] BYREF
  volatile signed __int32 **v242; // [rsp+420h] [rbp+320h]
  volatile signed __int32 **v243; // [rsp+428h] [rbp+328h]

  v2 = a2;
  v197 = a2;
  v3 = a1;
  v208 = a1;
  memset_0(v234, 0, sizeof(v234));
  DWORD1(Source) = 0;
  v5 = Align<unsigned int>(*((unsigned int *)v2 + 4), 4, v4);
  v8 = (unsigned __int64)v2 + 8;
  v203 = (char *)v2 + 8;
  if ( *(_QWORD *)v2 )
  {
    if ( *(_DWORD *)v8 < v5 || *(_DWORD *)v8 - v5 < 0x50 )
    {
      FailAssert(0x4Bu, v6);
      __debugbreak();
    }
  }
  else
  {
    v203 = (char *)v2 + 8;
  }
  v9 = v5 + 80LL;
  if ( v9 < v5 || (v10 = 0xFFFFFFFFLL, v9 > 0xFFFFFFFF) )
LABEL_275:
    ((void (__noreturn *)(void))SafeIntExceptionHandler<Exception>::SafeIntOnOverflow)();
  *((_DWORD *)v2 + 4) = v9;
  *((_QWORD *)&Source + 1) = *(_QWORD *)v3;
  LODWORD(Source) = *(_DWORD *)(v3 + 16) + 16;
  v12 = (unsigned int)Align<unsigned int>(v9, 8, v7);
  if ( !*(_QWORD *)v2 )
  {
    v14 = v12;
    goto LABEL_10;
  }
  if ( *(_DWORD *)v8 < (unsigned int)v12 || (v13 = *(_DWORD *)v8 - v12, v13 < 0x10) )
  {
    FailAssert(0x4Bu, v11);
    while ( 1 )
    {
      if ( (_DWORD)v12 == 10 )
      {
        if ( v82 - 1 <= 0x3E6 )
        {
          *(_WORD *)(v8 + 72) = v82;
          *(_WORD *)(v8 + 74) = v82;
        }
      }
      else if ( (_DWORD)v12 == 11 )
      {
        if ( v82 - 1 <= 8 )
          *(_BYTE *)(v8 + 76) = v82;
      }
      else if ( (_DWORD)v12 == 12 && v82 <= 2 )
      {
        *(_BYTE *)(v8 + 77) = v82;
        *(_BYTE *)(v8 + 78) = v82;
      }
      while ( 1 )
      {
        while ( 1 )
        {
LABEL_135:
          v84 = v206;
          if ( v206 && _InterlockedExchangeAdd((volatile signed __int32 *)v206, 0xFFFFFFFF) == 1 )
            RefCountedArrayImpl::Data::operator delete(v84);
          v12 = (unsigned int)(v12 + 1);
          v190 = v12;
          LOBYTE(v76) = v189;
          if ( (unsigned int)v12 >= 0xF )
          {
            v85 = (_QWORD *)(v8 + 176);
            v86 = (const void *)(v8 + 56);
            AddStandardAxes(v8 + 56, v8, v8 + 176, v76);
            v87 = *(const void **)(v8 + 176);
            v88 = 4 * ((__int64)(v85[1] - *v85) >> 2);
            if ( v88 > 0xFFFFFFFF )
              ((void (__noreturn *)(void))SafeIntExceptionHandler<Exception>::SafeIntOnOverflow)();
            v89 = 4 * ((__int64)(v85[1] - *v85) >> 2);
            RefCountedArrayImpl::AllocData(&v207, (unsigned int)v88, 1);
            memcpy_0((void *)(v207 + 8), v87, v89);
            v91 = InnerMemoryRegionDictionary::WriteInnerRegion(&v204, &v207, v90, v2);
            *((_DWORD *)v193 + 41) = v91;
            LODWORD(Size) = v10;
            ArrayOffset = BasedArrayPtr<FontSetRegion,FontSetRegion::FontEntry,unsigned int,unsigned int,8>::GetArrayOffset(&Size);
            MemoryWriterImpl::WriteArrayElementImpl(v2, ArrayOffset, v226, v86, 0x70u);
            RefCountedArrayImpl::~RefCountedArrayImpl((RefCountedArrayImpl *)&v207);
            `eh vector destructor iterator'(v235, 0x18u, 0xFu, (void (*)(void *))FontNameList::~FontNameList);
            v18 = v191 + 1;
            v191 = v18;
            if ( (unsigned int)v18 >= (unsigned int)v199 )
              goto LABEL_164;
            v3 = v208;
LABEL_13:
            v226 = v18;
            v8 = *(_QWORD *)(v3 + 24) + 200 * v18;
            v193 = (void *)v8;
            *(_DWORD *)(v8 + 60) = FontFaceKey::GetSerializedByteSize((FontFaceKey *)v8);
            *(_DWORD *)(v8 + 56) = FontFaceKey::SerializeTo((FontFaceKey *)v8);
            `eh vector constructor iterator'(
              v235,
              0x18u,
              0xFu,
              (void (*)(void *))FontNameList::FontNameList,
              (void (*)(void *))FontNameList::~FontNameList);
            v19 = *(_QWORD *)(v3 + 72);
            v20 = (int *)(v19 + 24LL * *(unsigned int *)(v8 + 172));
            for ( i = (int *)(v19 + 24LL * *(unsigned int *)(v8 + 168)); i != v20; i += 6 )
            {
              v26 = *i;
              if ( (unsigned int)v26 < 0xF )
              {
                v27 = *((_QWORD *)i + 2);
                v8 = *(unsigned int *)(v27 + 4);
                std::wstring::wstring(v228);
                if ( v8 )
                {
                  std::wstring::assign(v228, v27 + 8, (unsigned int)v8);
                  v28 = v228;
                  if ( v229 > 7 )
                    v28 = (_QWORD *)v228[0];
                  for ( j = 0; j < v8; ++j )
                  {
                    v30 = *((_WORD *)v28 + j);
                    if ( (unsigned __int16)(v30 - 97) > 0x19u )
                    {
                      if ( (unsigned __int16)(v30 - 65) > 0x19u )
                        break;
                      *((_WORD *)v28 + j) = v30 + 32;
                    }
                  }
                  if ( j - 1 > 7 )
                  {
                    LODWORD(Size) = -2147024809;
                    CaptureStack(-2147024809, 0);
                    LogAndThrow<ArgumentException>(&Size, 0x676174676E616CLL, 120);
                  }
                  while ( j < v8 )
                  {
                    if ( *((_WORD *)v28 + j) != 45 && *((_WORD *)v28 + j) != 95 )
                      goto LABEL_46;
                    for ( k = ++j; j < v8; ++j )
                    {
                      v32 = *((_WORD *)v28 + j);
                      if ( (unsigned __int16)(v32 - 97) > 0x19u && (unsigned __int16)(v32 - 48) > 9u )
                      {
                        if ( (unsigned __int16)(v32 - 65) > 0x19u )
                          break;
                        *((_WORD *)v28 + j) = v32 + 32;
                      }
                    }
                    if ( j - k - 1 > 7 )
                    {
                      LODWORD(Size) = -2147024809;
                      CaptureStack(-2147024809, 0);
                      LogAndThrow<ArgumentException>(&Size, 0x676174676E616CLL, 142);
                    }
                  }
                  if ( j != v8 )
                  {
LABEL_46:
                    LODWORD(Size) = -2147024809;
                    CaptureStack(-2147024809, 0);
                    LogAndThrow<ArgumentException>(&Size, 0x676174676E616CLL, 147);
                  }
                }
                v22 = &v235[3 * v26];
                v227[2] = &v230;
                v230 = 0;
                v231 = 0;
                v232 = 0;
                v23 = v228;
                if ( v229 > 7 )
                  v23 = (_QWORD *)v228[0];
                std::wstring::_Construct<2,wchar_t const *>(&v230, v23, v228[2]);
                Block = (void *)*((_QWORD *)i + 1);
                _InterlockedIncrement((volatile signed __int32 *)Block);
                v24 = v22[1];
                if ( v24 == v22[2] )
                {
                  std::vector<KeyValuePair<GenericLanguageTag<std::wstring>,DWrite::RefString>>::_Emplace_reallocate<KeyValuePair<GenericLanguageTag<std::wstring>,DWrite::RefString>>(
                    &v235[3 * v26],
                    v22[1],
                    &v230);
                }
                else
                {
                  KeyValuePair<GenericLanguageTag<std::wstring>,DWrite::RefString>::KeyValuePair<GenericLanguageTag<std::wstring>,DWrite::RefString>(
                    v24,
                    &v230);
                  v22[1] += 40LL;
                }
                v25 = Block;
                if ( Block != &DWrite::RefString::empty_
                  && _InterlockedExchangeAdd((volatile signed __int32 *)Block, 0xFFFFFFFF) == 1 )
                {
                  operator delete(v25);
                }
                std::wstring::_Tidy_deallocate(&v230);
                std::wstring::_Tidy_deallocate(v228);
              }
            }
            if ( v237[0] == v237[1] )
            {
              v168 = (const struct FontNameList *)v236;
              v169 = (FontNameList *)v237;
            }
            else
            {
              if ( v236[0] != v236[1] )
                goto LABEL_50;
              v168 = (const struct FontNameList *)v237;
              v169 = (FontNameList *)v236;
            }
            FontNameList::AppendItems(v169, v168);
LABEL_50:
            if ( v239[0] == v239[1] )
            {
              v166 = (const struct FontNameList *)v238;
              v167 = (FontNameList *)v239;
            }
            else
            {
              if ( v238[0] != v238[1] )
              {
LABEL_52:
                v12 = 0;
                v190 = 0;
                v189 = 0;
                goto LABEL_53;
              }
              v166 = (const struct FontNameList *)v239;
              v167 = (FontNameList *)v238;
            }
            FontNameList::AppendItems(v167, v166);
            goto LABEL_52;
          }
LABEL_53:
          v33 = 3 * v12;
          v198 = 3 * v12;
          std::_Sort_unchecked<KeyValuePair<GenericLanguageTag<std::wstring>,DWrite::RefString> *,std::less<void>>(
            v235[3 * v12],
            v235[3 * v12 + 1],
            0xCCCCCCCCCCCCCCCDuLL * ((__int64)(v235[3 * v12 + 1] - v235[3 * v12]) >> 3));
          v34 = 0;
          v35 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(v235[3 * v12 + 1] - v235[3 * v12]) >> 3);
          v205 = (char *)v35;
          if ( v35 )
          {
            if ( v35 > 0xFFFFFFFF || !is_mul_ok(8u, v35) || (v192 = (unsigned int)(8 * v35) + 4LL, v192 > 0xFFFFFFFF) )
LABEL_148:
              ((void (__noreturn *)(void))SafeIntExceptionHandler<Exception>::SafeIntOnOverflow)();
            for ( m = 0; m < v35; ++m )
            {
              v37 = v235[v33];
              if ( m >= 0xCCCCCCCCCCCCCCCDuLL * ((v235[v33 + 1] - v37) >> 3) )
              {
                FailAssert(0x35u, (const char *)0xFFFFFFFFLL);
LABEL_290:
                FailAssert(0x95u, v55);
                __debugbreak();
              }
              v38 = v37 + 40 * m;
              v8 = *(_QWORD *)(v38 + 16);
              if ( *(_QWORD *)(v38 + 24) <= 7u )
                v39 = (const void *)(v37 + 40 * m);
              else
                v39 = *(const void **)v38;
              if ( v8 )
              {
                if ( v8 > 0xFFFFFFFF )
                  goto LABEL_148;
                v40 = 2 * v8;
                if ( !is_mul_ok(2u, v8) )
                  goto LABEL_148;
                v41 = v40;
                v42 = v40 + 10LL;
                if ( v42 < v41 || v42 > 0xFFFFFFFF )
                  goto LABEL_148;
                v43 = operator new((unsigned int)v42);
                v46 = v43;
                *v43 = 1;
                v43[1] = v8;
                if ( v39 )
                {
                  v47 = 2 * v8;
                  if ( 2 * v8 )
                  {
                    v48 = v43 + 2;
                    if ( v43 == (_DWORD *)-8LL )
                    {
                      *(_DWORD *)_o__errno(v48, v44, v47, v45) = 22;
                      invalid_parameter_noinfo();
                    }
                    else
                    {
                      memcpy_0(v48, v39, v47);
                    }
                  }
                }
                v46[v8 + 4] = 0;
                v35 = (unsigned __int64)v205;
              }
              else
              {
                v46 = &DWrite::RefString::empty_;
              }
              v227[0] = v46;
              StringMemoryRegionDictionary::WriteString(
                (StringMemoryRegionDictionary *)&v211,
                (const struct DWrite::RefString *)v227,
                (struct MemoryWriterImpl *)&v212);
              if ( v46 != (_WORD *)&DWrite::RefString::empty_
                && _InterlockedExchangeAdd((volatile signed __int32 *)v46, 0xFFFFFFFF) == 1 )
              {
                operator delete(v46);
              }
              StringMemoryRegionDictionary::WriteString(
                (StringMemoryRegionDictionary *)&v211,
                (const struct DWrite::RefString *)(v38 + 32),
                (struct MemoryWriterImpl *)&v212);
              v33 = v198;
            }
            v34 = v192;
            v12 = v190;
            v2 = v197;
          }
          RefCountedArrayImpl::AllocData(&v206, v34, 1);
          v51 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(v235[v33 + 1] - v235[v33]) >> 3);
          v223 = v51;
          if ( !v51 )
            goto LABEL_117;
          if ( v51 > 0xFFFFFFFF )
LABEL_131:
            ((void (__noreturn *)(void))SafeIntExceptionHandler<Exception>::SafeIntOnOverflow)();
          v52 = *((_DWORD *)v206 + 1);
          LODWORD(Size) = v52;
          v53 = (char *)v206 + 8;
          v205 = (char *)v206 + 8;
          if ( v206 == (void *)-8LL )
            goto LABEL_81;
          if ( v52 >= 4 )
            break;
          FailAssert(0x4Bu, v49);
LABEL_152:
          std::vector<StringToFontIndex>::_Emplace_reallocate<StringToFontIndex const &>(v95, v96, &v220);
          v93 = v220;
          while ( 1 )
          {
            if ( v93 != &DWrite::RefString::empty_
              && _InterlockedExchangeAdd((volatile signed __int32 *)v93, 0xFFFFFFFF) == 1 )
            {
              operator delete(v93);
            }
            v12 += 40;
LABEL_133:
            if ( v12 == v8 )
              break;
            v93 = *(void **)(v12 + 32);
            v220 = v93;
            _InterlockedIncrement((volatile signed __int32 *)v93);
            v94 = v191;
            v221 = v191;
            v222 = 0;
            v95 = &v240[v33];
            v96 = v95[1];
            if ( v96 == v95[2] )
              goto LABEL_152;
            v227[3] = v240[v33 + 1];
            *(_QWORD *)v96 = v93;
            _InterlockedIncrement((volatile signed __int32 *)v93);
            *(_DWORD *)(v96 + 8) = v94;
            v95[1] += 16LL;
          }
LABEL_134:
          v8 = (unsigned __int64)v193;
          LODWORD(v12) = v190;
        }
        *v53 = v51;
LABEL_81:
        v54 = 8 * v51;
        if ( !is_mul_ok(8u, v51) )
          goto LABEL_131;
        if ( v53 && (v52 < 4 || v52 - 4 < (unsigned __int64)v54) )
        {
          FailAssert(0x4Bu, (const char *)v54);
          goto LABEL_275;
        }
        v55 = (char *)(v54 + 4LL);
        v225 = v55;
        if ( (unsigned __int64)v55 > 0xFFFFFFFF )
          goto LABEL_131;
        for ( n = 0; n < v51; ++n )
        {
          v57 = v235[v33];
          if ( n >= 0xCCCCCCCCCCCCCCCDuLL * ((v235[v33 + 1] - v57) >> 3) )
          {
            FailAssert(0x35u, v55);
            __debugbreak();
          }
          v58 = v57 + 40 * n;
          v59 = *(_QWORD *)(v58 + 16);
          if ( *(_QWORD *)(v58 + 24) <= 7u )
            v60 = (const void *)(v57 + 40 * n);
          else
            v60 = *(const void **)v58;
          if ( v59 )
          {
            if ( v59 > 0xFFFFFFFF )
              goto LABEL_131;
            v61 = 2 * v59;
            if ( !is_mul_ok(2u, v59) )
              goto LABEL_131;
            v62 = v61;
            v63 = v61 + 10LL;
            if ( v63 < v62 || v63 > 0xFFFFFFFF )
              goto LABEL_131;
            v64 = operator new((unsigned int)v63);
            v67 = v64;
            *v64 = 1;
            v64[1] = v59;
            if ( v60 )
            {
              v68 = 2 * v59;
              if ( 2 * v59 )
              {
                v69 = v64 + 2;
                if ( v64 == (_DWORD *)-8LL )
                {
                  *(_DWORD *)_o__errno(v69, v65, v68, v66) = 22;
                  invalid_parameter_noinfo();
                }
                else
                {
                  memcpy_0(v69, v60, v68);
                }
              }
            }
            v67[v59 + 4] = 0;
            v51 = v223;
          }
          else
          {
            v67 = &DWrite::RefString::empty_;
          }
          v224 = v67;
          LODWORD(v219) = StringMemoryRegionDictionary::WriteString(
                            (StringMemoryRegionDictionary *)&v211,
                            (const struct DWrite::RefString *)&v224,
                            (struct MemoryWriterImpl *)&v212);
          if ( v67 != (_WORD *)&DWrite::RefString::empty_
            && _InterlockedExchangeAdd((volatile signed __int32 *)v67, 0xFFFFFFFF) == 1 )
          {
            operator delete(v67);
          }
          HIDWORD(v219) = StringMemoryRegionDictionary::WriteString(
                            (StringMemoryRegionDictionary *)&v211,
                            (const struct DWrite::RefString *)(v58 + 32),
                            (struct MemoryWriterImpl *)&v212);
          if ( v205 )
          {
            if ( n > 0xFFFFFFFF )
              goto LABEL_131;
            v70 = 8 * n;
            if ( !is_mul_ok(8u, n) )
              goto LABEL_131;
            v71 = v70;
            v72 = v70 + 4LL;
            if ( v72 < v71 )
              goto LABEL_131;
            v55 = v225;
            if ( (unsigned int)v225 <= 8 || (unsigned int)v72 > (unsigned __int64)(unsigned int)v225 - 8 )
            {
              FailAssert(0x94u, v225);
              __debugbreak();
            }
            if ( (unsigned int)Size < (unsigned int)v225 )
              goto LABEL_290;
            v73 = &v205[(unsigned int)v72];
            if ( !v73 )
            {
              *(_DWORD *)_o__errno((unsigned int)v72, v225, v50, 0) = 22;
LABEL_114:
              invalid_parameter_noinfo();
              goto LABEL_115;
            }
            v50 = (unsigned int)(Size - v72);
            if ( v50 < 8 )
            {
              memset_0(v73, 0, v50);
              *(_DWORD *)_o__errno(v172, v171, v173, v174) = 34;
              goto LABEL_114;
            }
            *(_QWORD *)v73 = v219;
          }
LABEL_115:
          v33 = v198;
        }
        v12 = v190;
        v2 = v197;
LABEL_117:
        v74 = InnerMemoryRegionDictionary::WriteInnerRegion(&v204, &v206, v50, v2);
        v8 = (unsigned __int64)v193;
        *((_DWORD *)v193 + (unsigned int)v12 + 26) = v74;
        if ( (_DWORD)v12 == 5 )
        {
          v97 = v238[6];
          v98 = v238[7];
          v99 = v191;
          while ( v97 != v98 )
          {
            v100 = *(volatile signed __int32 **)(v97 + 32);
            v215 = v100;
            _InterlockedIncrement(v100);
            v216 = v99;
            v217 = 0;
            v101 = v242;
            if ( v242 == v243 )
            {
              std::vector<StringToFontIndex>::_Emplace_reallocate<StringToFontIndex const &>(v241, v242, &v215);
              v100 = v215;
            }
            else
            {
              v227[4] = v242;
              *v242 = v100;
              _InterlockedIncrement(v100);
              *((_DWORD *)v101 + 2) = v99;
              v242 += 2;
            }
            v102 = *(_QWORD *)(v97 + 32);
            if ( *(_DWORD *)(v102 + 4) > 0x1Fu )
            {
              v103 = (volatile signed __int32 *)DWrite::RefString::NewData((const wchar_t *)(v102 + 8), 0x1Fu);
              v227[1] = v103;
              v104 = (struct DWrite::RefString::Data *)v103;
              *(_QWORD *)&Source = v103;
              _InterlockedIncrement(v103);
              *((_QWORD *)&Source + 1) = v99;
              v105 = v242;
              if ( v242 == v243 )
              {
                std::vector<StringToFontIndex>::_Emplace_reallocate<StringToFontIndex const &>(v241, v242, &Source);
                v104 = (struct DWrite::RefString::Data *)Source;
              }
              else
              {
                v209 = (volatile signed __int32 *)v242;
                *v242 = v103;
                _InterlockedIncrement(v103);
                *((_DWORD *)v105 + 2) = v99;
                v242 += 2;
              }
              DWrite::RefString::DecrementRef(v104);
              DWrite::RefString::DecrementRef((struct DWrite::RefString::Data *)v103);
            }
            DWrite::RefString::DecrementRef((struct DWrite::RefString::Data *)v100);
            v97 += 40;
          }
          goto LABEL_134;
        }
        if ( (_DWORD)v12 != 10 && (unsigned int)(v12 - 11) > 1 )
        {
          v12 = v235[v33];
          v8 = v235[v33 + 1];
          goto LABEL_133;
        }
        v77 = v235[v33];
        v78 = v235[v33 + 1];
        if ( v77 != v78 )
        {
          if ( !(0xCCCCCCCCCCCCCCCDuLL * ((v78 - v77) >> 3)) )
          {
            FailAssert(0x35u, v75);
            goto LABEL_294;
          }
          v79 = *(_QWORD *)(v77 + 32);
          v80 = v79 + 2 * (*(unsigned int *)(v79 + 4) + 4LL);
          v81 = (unsigned __int16 *)(v79 + 8);
          v82 = 0;
          if ( v79 + 8 < v80 )
            break;
        }
      }
      while ( (unsigned __int64)v81 < v80 )
      {
        v76 = *v81;
        if ( (unsigned int)(v76 - 48) > 9 )
          goto LABEL_135;
        v83 = v82;
        v82 = v76 + 2 * (5 * v82 - 24);
        if ( v82 < v83 )
          goto LABEL_135;
        ++v81;
      }
    }
  }
  v14 = (unsigned int)v12;
  memcpy_s((void *const)(v12 + *(_QWORD *)v2), v13, &Source, 0x10u);
LABEL_10:
  v15 = v14 + 16;
  if ( v14 + 16 < v14 || v15 > 0xFFFFFFFF )
    goto LABEL_275;
  *((_DWORD *)v2 + 4) = v15;
  v234[1] = v12;
  MemoryWriterImpl::WriteAligned(v2, *(const void **)(v3 + 8), *(unsigned int *)(v3 + 16), 1u);
  v199 = 0x8F5C28F5C28F5C29uLL * ((__int64)(*(_QWORD *)(v3 + 32) - *(_QWORD *)(v3 + 24)) >> 3);
  v16 = v199;
  v17 = (unsigned int *)MemoryWriter<FontSetRegion>::WriteArray<FontSetRegion::FontEntry>(v2);
  v10 = *v17;
  v234[2] = *v17;
  v211 = 0;
  v212 = 0;
  v213 = 0;
  v214 = 0;
  v204 = 0;
  `eh vector constructor iterator'(
    v240,
    0x18u,
    0xFu,
    std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>,
    std::vector<StringToFontIndex>::~vector<StringToFontIndex>);
  v18 = 0;
  v191 = 0;
  if ( v16 )
    goto LABEL_13;
LABEL_164:
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(Src);
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(&v200);
  for ( ii = 0; ; ii = (unsigned int)(Size + 1) )
  {
    LODWORD(Size) = ii;
    if ( (unsigned int)ii >= 0xF )
      break;
    v2 = (MemoryWriterImpl *)(unsigned int)ii;
    v51 = (unsigned int)ii + 2 * ii;
    v108 = v240[v51];
    v33 = (v240[v51 + 1] - v108) >> 4;
    LOBYTE(v106) = 0;
    std::_Sort_unchecked<StringToFontIndex *,std::less<void>>(v108, v240[v51 + 1], v33, v106);
    v109 = v200;
    if ( v200 != v201 )
    {
      std::_Destroy_range<std::allocator<StringToIndexList>>(v200);
      v109 = v200;
      v201 = v200;
    }
    v110 = (__int64)(v240[v51 + 1] - v240[v51]) >> 4;
    v199 = v110;
    if ( v110 > (v202 - v109) >> 4 )
    {
      if ( v110 > 0xFFFFFFFFFFFFFFFLL )
        std::vector<DWRITE_FONT_FEATURE>::_Xlength();
      std::vector<StringToIndexList>::_Reallocate<0>(&v200, &v199);
    }
    v111 = (__int64)(v240[v51 + 1] - v240[v51]) >> 4;
    v199 = v111;
    v112 = (char *)Src[0];
    if ( v111 > (v195 - (char *)Src[0]) >> 2 )
    {
      if ( v111 > 0x3FFFFFFFFFFFFFFFLL )
        std::vector<DWRITE_FONT_FEATURE>::_Xlength();
      std::vector<unsigned int>::_Reallocate<0>(Src, &v199);
      v112 = (char *)Src[0];
    }
    LODWORD(v8) = 0;
    while ( (unsigned int)v8 < (unsigned int)v33 )
    {
      v113 = (char *)Src[1];
      if ( v112 != Src[1] )
      {
        v113 = v112;
        Src[1] = v112;
      }
      v10 = 16LL * (unsigned int)v8;
      v114 = (_DWORD *)(v240[v51] + v10 + 8);
      if ( v113 == v195 )
      {
        std::vector<unsigned int>::_Emplace_reallocate<unsigned int const &>(Src, v113, v114);
        v115 = (char *)Src[1];
      }
      else
      {
        *(_DWORD *)v113 = *v114;
        v115 = (char *)Src[1] + 4;
        Src[1] = (char *)Src[1] + 4;
      }
      LODWORD(v8) = v8 + 1;
      while ( (unsigned int)v8 < (unsigned int)v33 )
      {
        v12 = 2LL * (unsigned int)v8;
        v116 = v240[v51];
        v117 = *(_QWORD *)(v116 + 16LL * (unsigned int)v8);
        v113 = (char *)(v117 + 8);
        v118 = *(_QWORD *)(v10 + v116);
        v119 = (const WCHAR *)(v118 + 8);
        if ( v118 == -8 )
        {
LABEL_294:
          v123 = v113 == 0;
        }
        else
        {
          if ( v117 == -8 )
            break;
          v120 = 0x7FFFFFFF;
          if ( *(_DWORD *)(v117 + 4) > 0x7FFFFFFFu )
            goto LABEL_226;
          v121 = *(_DWORD *)(v118 + 4);
          if ( v121 > 0x7FFFFFFF )
            goto LABEL_226;
          v122 = CompareStringW(0x7Fu, 1u, v119, v121, (PCNZWCH)(v117 + 8), *(_DWORD *)(v117 + 4));
          v115 = (char *)Src[1];
          v123 = v122 == 2;
        }
        if ( !v123 )
          break;
        v129 = v240[v51];
        v113 = (char *)*(unsigned int *)(v129 + 8 * v12 + 8);
        v191 = *(_DWORD *)(v129 + 8 * v12 + 8);
        if ( Src[0] == v115 || *((_DWORD *)v115 - 1) != (_DWORD)v113 )
        {
          if ( v115 == v195 )
          {
            std::vector<unsigned int>::_Emplace_reallocate<unsigned int const &>(Src, v115, &v191);
            v115 = (char *)Src[1];
          }
          else
          {
            *(_DWORD *)v115 = (_DWORD)v113;
            v115 = (char *)Src[1] + 4;
            Src[1] = (char *)Src[1] + 4;
          }
        }
        LODWORD(v8) = v8 + 1;
      }
      v124 = Src[0];
      v120 = (v115 - (char *)Src[0]) & 0xFFFFFFFFFFFFFFFCuLL;
      if ( v120 > 0xFFFFFFFF )
LABEL_226:
        SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(v120, v113);
      v125 = v120;
      RefCountedArrayImpl::AllocData(&v193, (unsigned int)v120, 1);
      memcpy_0((char *)v193 + 8, v124, v125);
      v126 = *(volatile signed __int32 **)(v10 + v240[v51]);
      v209 = v126;
      _InterlockedIncrement(v126);
      v210 = v193;
      if ( v193 )
        _InterlockedIncrement((volatile signed __int32 *)v193);
      if ( v201 == v202 )
      {
        std::vector<StringToIndexList>::_Emplace_reallocate<StringToIndexList const &>(&v200, v201, &v209);
        v127 = v210;
        v126 = v209;
      }
      else
      {
        StringToIndexList::StringToIndexList(v201, (const struct StringToIndexList *)&v209);
        v201 = (StringToIndexList *)((char *)v201 + 16);
      }
      if ( v127 && _InterlockedExchangeAdd((volatile signed __int32 *)v127, 0xFFFFFFFF) == 1 )
        RefCountedArrayImpl::Data::operator delete(v127);
      if ( v126 != (volatile signed __int32 *)&DWrite::RefString::empty_ && !_InterlockedDecrement(v126) )
        operator delete((void *)v126);
      v128 = v193;
      if ( v193 && !_InterlockedDecrement((volatile signed __int32 *)v193) )
        RefCountedArrayImpl::Data::operator delete(v128);
      v112 = (char *)Src[0];
    }
    v130 = (v201 - v200) >> 4;
    v131 = v197;
    v132 = *(unsigned int *)MemoryWriter<FontSetRegion>::WriteArray<FontSetRegion::StringToIndexList>(
                              v197,
                              &v190,
                              v112,
                              (unsigned int)v130);
    v234[(_QWORD)v2 + 5] = v132;
    v133 = 0;
    if ( (_DWORD)v130 )
    {
      v134 = (unsigned int)v132;
      v135 = v132 + 4;
      do
      {
        v136 = 16LL * v133;
        LODWORD(v198) = StringMemoryRegionDictionary::WriteString(
                          (StringMemoryRegionDictionary *)&v211,
                          (StringToIndexList *)((char *)v200 + v136),
                          (struct MemoryWriterImpl *)&v212);
        HIDWORD(v198) = InnerMemoryRegionDictionary::WriteInnerRegion(&v204, (char *)v200 + v136 + 8, v137, v131);
        if ( v135 < v134 )
          goto LABEL_224;
        v106 = 0xFFFFFFFFLL;
        if ( v135 > 0xFFFFFFFF )
          goto LABEL_224;
        v138 = (unsigned int)v135 + 3LL;
        if ( v138 < (unsigned int)v135 || v138 > 0xFFFFFFFF )
          goto LABEL_224;
        v139 = *(_QWORD *)v131;
        if ( *(_QWORD *)v131 )
        {
          v140 = 8 * v133;
          if ( !is_mul_ok(8u, v133) )
            goto LABEL_224;
          v141 = v140;
          v142 = v140 + (unsigned __int64)((unsigned int)v138 & 0xFFFFFFFC);
          if ( v142 < v141 || v142 > 0xFFFFFFFF )
            goto LABEL_224;
          if ( *((_DWORD *)v131 + 4) <= 8u
            || (v142 = (unsigned int)v142, (unsigned int)v142 > (unsigned __int64)*((unsigned int *)v131 + 4) - 8) )
          {
            FailAssert(0x94u, (const char *)v142);
            __debugbreak();
          }
          if ( *(_DWORD *)v203 < *((_DWORD *)v131 + 4) )
          {
            FailAssert(0x95u, (const char *)(unsigned int)v142);
            __debugbreak();
          }
          v143 = (__int64 *)(v139 + (unsigned int)v142);
          if ( v143 )
          {
            v144 = (unsigned int)(*(_DWORD *)v203 - v142);
            if ( v144 >= 8 )
            {
              *v143 = v198;
              goto LABEL_220;
            }
            memset_0(v143, 0, v144);
            *(_DWORD *)_o__errno(v176, v175, v177, v178) = 34;
          }
          else
          {
            *(_DWORD *)_o__errno(0, (unsigned int)v142, v139, 0xFFFFFFFFLL) = 22;
          }
          invalid_parameter_noinfo();
        }
LABEL_220:
        ++v133;
      }
      while ( v133 < (unsigned int)v130 );
    }
  }
  v145 = v208;
  LOBYTE(v106) = v189;
  std::_Sort_unchecked_FontSetBuilder::FileEntry____lambda_0f18e48da815e7d4c6cb3f627fd23bdc___(
    *(_QWORD *)(v208 + 48),
    *(_QWORD *)(v208 + 56),
    (__int64)(*(_QWORD *)(v208 + 56) - *(_QWORD *)(v208 + 48)) >> 4,
    v106);
  v146 = *(_QWORD *)(v145 + 56);
  v147 = (_QWORD *)std::unique<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<FontSetBuilder::FileEntry>>>>(
                     &v209,
                     *(_QWORD *)(v145 + 48),
                     v146);
  if ( *v147 != v146 )
  {
    v179 = std::_Move_unchecked<FontSetBuilder::FileEntry *,FontSetBuilder::FileEntry *>(
             v146,
             *(_QWORD *)(v145 + 56),
             *v147);
    std::_Destroy_range<std::allocator<FontSetBuilder::FileEntry>>(v179, *(_QWORD *)(v145 + 56));
    *(_QWORD *)(v145 + 56) = v179;
  }
  v148 = (__int64)(*(_QWORD *)(v145 + 56) - *(_QWORD *)(v145 + 48)) >> 4;
  v149 = v197;
  v150 = *(_DWORD *)MemoryWriter<FontSetRegion>::WriteArray<FontSetRegion::FileEntry>(v197);
  v234[3] = v150;
  for ( jj = 0; jj < (unsigned int)v148; ++jj )
  {
    v152 = *(_QWORD *)(v208 + 48);
    *(_QWORD *)&Source = *(_QWORD *)(v152 + 16LL * jj);
    v153 = *(_QWORD *)(v152 + 16LL * jj + 8);
    HIDWORD(Source) = MemoryWriterImpl::WriteAligned(v149, (const void *)(v153 + 8), *(unsigned int *)(v153 + 4), 1u);
    DWORD2(Source) = *(_DWORD *)(*(_QWORD *)(v152 + 16LL * jj + 8) + 4LL);
    LODWORD(Size) = v150;
    v154 = BasedArrayPtr<FontSetRegion,FontSetRegion::FontEntry,unsigned int,unsigned int,8>::GetArrayOffset(&Size);
    v155 = *(char **)v149;
    if ( *(_QWORD *)v149 )
    {
      v156 = 16 * jj;
      if ( !is_mul_ok(0x10u, jj)
        || (v157 = v156, v158 = (const char *)(v156 + (unsigned __int64)v154), (unsigned __int64)v158 < v157)
        || (unsigned __int64)v158 > 0xFFFFFFFF )
      {
LABEL_224:
        ((void (__noreturn *)(void))SafeIntExceptionHandler<Exception>::SafeIntOnOverflow)();
      }
      if ( *((_DWORD *)v149 + 4) <= 0x10u || (unsigned int)v158 > (unsigned __int64)*((unsigned int *)v149 + 4) - 16 )
      {
        FailAssert(0x94u, v158);
        __debugbreak();
      }
      if ( *(_DWORD *)v203 < *((_DWORD *)v149 + 4) )
      {
        FailAssert(0x95u, v158);
        __debugbreak();
      }
      v159 = &v155[(unsigned int)v158];
      if ( v159 )
      {
        v170 = (unsigned int)(*(_DWORD *)v203 - (_DWORD)v158);
        if ( v170 >= 0x10 )
        {
          *(_OWORD *)v159 = Source;
          continue;
        }
        memset_0(v159, 0, v170);
        *(_DWORD *)_o__errno(v181, v180, v182, v183) = 34;
      }
      else
      {
        *(_DWORD *)_o__errno(0, v158, (unsigned int)v158, v155) = 22;
      }
      invalid_parameter_noinfo();
    }
  }
  MemoryWriterImpl::BeginInnerRegionImpl(v149, &Source, 4);
  v215 = (volatile signed __int32 *)Source;
  v216 = DWORD2(Source);
  v218 = 0;
  StringMemoryRegionDictionary::WriteRegion((StringMemoryRegionDictionary *)&v211, (struct MemoryWriterImpl *)&v215);
  v234[4] = MemoryWriterImpl::EndInnerRegionImpl(v149, v218, 4u);
  v234[0] = *((_DWORD *)v149 + 4);
  if ( *(_QWORD *)v149 )
  {
    SafeCastHelper<unsigned int,unsigned __int64,2>::CastThrow<SafeIntExceptionHandler<Exception>>(80, &Size);
    v162 = *((_DWORD *)v149 + 4);
    if ( (unsigned int)Size > v162 )
    {
      FailAssert(0x7Au, v160);
      JUMPOUT(0x18016904FLL);
    }
    if ( *(_DWORD *)v203 < v162 )
    {
      FailAssert(0x7Bu, v203);
      __debugbreak();
    }
    if ( (_DWORD)Size )
    {
      v163 = *(char **)v149;
      if ( !*(_QWORD *)v149 )
      {
        *(_DWORD *)_o__errno(0, v203, (unsigned int)Size, v161) = 22;
LABEL_252:
        invalid_parameter_noinfo();
        goto LABEL_253;
      }
      if ( *(unsigned int *)v203 < (unsigned __int64)(unsigned int)Size )
      {
        memset_0(v163, 0, *(unsigned int *)v203);
        *(_DWORD *)_o__errno(v185, v184, v186, v187) = 34;
        goto LABEL_252;
      }
      memcpy_0(v163, v234, (unsigned int)Size);
    }
  }
LABEL_253:
  std::vector<StringToIndexList>::~vector<StringToIndexList>(&v200);
  if ( Src[0] )
  {
    std::_Deallocate<16>(Src[0], (v195 - (char *)Src[0]) & 0xFFFFFFFFFFFFFFFCuLL);
    *(_OWORD *)Src = 0;
    v195 = 0;
  }
  `eh vector destructor iterator'(v240, 0x18u, 0xFu, std::vector<StringToFontIndex>::~vector<StringToFontIndex>);
  v164 = v204;
  if ( v204 )
  {
    std::_Tree<std::_Tmap_traits<RefCountedArray<unsigned char>,unsigned int,InnerMemoryRegionDictionary::OffsetMap::Comparer,std::allocator<std::pair<RefCountedArray<unsigned char> const,unsigned int>>,0>>::~_Tree<std::_Tmap_traits<RefCountedArray<unsigned char>,unsigned int,InnerMemoryRegionDictionary::OffsetMap::Comparer,std::allocator<std::pair<RefCountedArray<unsigned char> const,unsigned int>>,0>>(v204);
    RefCountedArrayImpl::Data::operator delete(v164);
  }
  v165 = v211;
  if ( v211 )
  {
    std::_Tree<std::_Tmap_traits<DWrite::RefString,unsigned int,std::less<DWrite::RefString>,std::allocator<std::pair<DWrite::RefString const,unsigned int>>,0>>::~_Tree<std::_Tmap_traits<DWrite::RefString,unsigned int,std::less<DWrite::RefString>,std::allocator<std::pair<DWrite::RefString const,unsigned int>>,0>>(v211);
    RefCountedArrayImpl::Data::operator delete(v165);
  }
}

```

## disassembly

```asm
0x180167878  mov     [rsp-8+arg_10], rbx
0x18016787d  push    rbp
0x18016787e  push    rsi
0x18016787f  push    rdi
0x180167880  push    r12
0x180167882  push    r13
0x180167884  push    r14
0x180167886  push    r15
0x180167888  lea     rbp, [rsp-420h]
0x180167890  sub     rsp, 520h
0x180167897  mov     rax, cs:__security_cookie
0x18016789e  xor     rax, rsp
0x1801678a1  mov     [rbp+450h+var_40], rax
0x1801678a8  mov     r13, rdx
0x1801678ab  mov     [rbp+450h+var_4D0], rdx
0x1801678af  mov     rsi, rcx
0x1801678b2  mov     [rbp+450h+var_478], rcx
0x1801678b6  xor     edx, edx; Val
0x1801678b8  lea     r8d, [rdx+50h]; Size
0x1801678bc  lea     rcx, [rbp+450h+var_370]; void *
0x1801678c3  call    memset_0
0x1801678c8  mov     dword ptr [rsp+550h+Source+4], 0
0x1801678d0  mov     edx, 4
0x1801678d5  mov     ecx, [r13+10h]
0x1801678d9  call    ??$Align@I@@YAII_K@Z; Align<uint>(uint,unsigned __int64)
0x1801678de  lea     rdi, [r13+8]
0x1801678e2  mov     [rbp+450h+var_4A0], rdi
0x1801678e6  cmp     qword ptr [r13+0], 0
0x1801678eb  jz      loc_180168E0A
0x1801678f1  mov     ecx, [rdi]
0x1801678f3  cmp     ecx, eax
0x1801678f5  jb      loc_180168E82
0x1801678fb  sub     ecx, eax
0x1801678fd  cmp     ecx, 50h ; 'P'
0x180167900  jb      loc_180168E82
0x180167906  mov     eax, eax
0x180167908  lea     rcx, [rax+50h]
0x18016790c  cmp     rcx, rax
0x18016790f  jb      loc_180168E76
0x180167915  mov     r14d, 0FFFFFFFFh
0x18016791b  cmp     rcx, r14
0x18016791e  ja      loc_180168E76
0x180167924  mov     [r13+10h], ecx
0x180167928  mov     rax, [rsi]
0x18016792b  mov     qword ptr [rsp+550h+Source+8], rax
0x180167930  mov     eax, [rsi+10h]
0x180167933  add     eax, 10h
0x180167936  mov     dword ptr [rsp+550h+Source], eax
0x18016793a  mov     edx, 8
0x18016793f  call    ??$Align@I@@YAII_K@Z; Align<uint>(uint,unsigned __int64)
0x180167944  mov     ebx, eax
0x180167946  mov     rax, [r13+0]
0x18016794a  test    rax, rax
0x18016794d  jz      loc_180168E13
0x180167953  mov     ecx, [rdi]
0x180167955  cmp     ecx, ebx
0x180167957  jb      loc_180168E8D
0x18016795d  sub     ecx, ebx
0x18016795f  cmp     ecx, 10h
0x180167962  jb      loc_180168E8D
0x180167968  mov     edi, ebx
0x18016796a  mov     edx, ecx; DestinationSize
0x18016796c  lea     rcx, [rbx+rax]; Destination
0x180167970  mov     r9d, 10h; SourceSize
0x180167976  lea     r8, [rsp+550h+Source]; Source
0x18016797b  call    memcpy_s
0x180167980  lea     rax, [rdi+10h]
0x180167984  cmp     rax, rdi
0x180167987  jb      loc_180168E76
0x18016798d  cmp     rax, r14
0x180167990  ja      loc_180168E76
0x180167996  mov     [r13+10h], eax
0x18016799a  mov     [rbp+450h+var_36C], ebx
0x1801679a0  mov     r8d, [rsi+10h]; unsigned __int64
0x1801679a4  mov     r9d, 1; unsigned __int64
0x1801679aa  mov     rdx, [rsi+8]; void *
0x1801679ae  mov     rcx, r13; this
0x1801679b1  call    ?WriteAligned@MemoryWriterImpl@@IEAAIPEBX_K1@Z; MemoryWriterImpl::WriteAligned(void const *,unsigned __int64,unsigned __int64)
0x1801679b6  mov     rbx, [rsi+20h]
0x1801679ba  sub     rbx, [rsi+18h]
0x1801679be  sar     rbx, 3
0x1801679c2  mov     rax, 8F5C28F5C28F5C29h
0x1801679cc  imul    rbx, rax
0x1801679d0  mov     [rbp+450h+var_4C0], rbx
0x1801679d4  mov     r9d, ebx
0x1801679d7  lea     rdx, [rsp+550h+Size]
0x1801679dc  mov     rcx, r13; this
0x1801679df  call    ??$WriteArray@UFontEntry@FontSetRegion@@@?$MemoryWriter@VFontSetRegion@@@@QEAA?AV?$BasedArrayPtr@VFontSetRegion@@UFontEntry@1@II$07@@PEBUFontEntry@FontSetRegion@@_K@Z; MemoryWriter<FontSetRegion>::WriteArray<FontSetRegion::FontEntry>(FontSetRegion::FontEntry const *,unsigned __int64)
0x1801679e4  mov     r14d, [rax]
0x1801679e7  mov     [rbp+450h+var_368], r14d
0x1801679ee  mov     [rbp+450h+var_460], 0
0x1801679f6  mov     [rbp+450h+var_458], 0
0x1801679fe  mov     [rbp+450h+var_450], 0
0x180167a05  mov     [rbp+450h+var_448], 0
0x180167a0c  mov     [rbp+450h+var_498], 0
0x180167a14  lea     rax, ??1?$vector@UStringToFontIndex@@V?$allocator@UStringToFontIndex@@@std@@@std@@QEAA@XZ; std::vector<StringToFontIndex>::~vector<StringToFontIndex>(void)
0x180167a1b  mov     [rsp+550h+lpString2], rax; void (*)(void *)
0x180167a20  lea     r9, ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; void (*)(void *)
0x180167a27  mov     r8d, 0Fh; unsigned __int64
0x180167a2d  lea     r15d, [r8+9]
0x180167a31  mov     edx, r15d; unsigned __int64
0x180167a34  lea     rcx, [rbp+450h+var_1B0]; void *
0x180167a3b  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180167a40  nop
0x180167a41  xor     eax, eax
0x180167a43  mov     [rsp+550h+var_510], eax
0x180167a47  test    ebx, ebx
0x180167a49  jz      loc_180168601
0x180167a4f  lea     rbx, ??1FontNameList@@QEAA@XZ; FontNameList::~FontNameList(void)
0x180167a56  mov     [rbp+450h+var_3F8], rax
0x180167a5a  imul    rdi, rax, 0C8h
0x180167a61  add     rdi, [rsi+18h]
0x180167a65  mov     [rsp+550h+var_500], rdi
0x180167a6a  mov     rcx, rdi; this
0x180167a6d  call    ?GetSerializedByteSize@FontFaceKey@@QEBAIXZ; FontFaceKey::GetSerializedByteSize(void)
0x180167a72  mov     [rdi+3Ch], eax
0x180167a75  mov     rdx, r13
0x180167a78  mov     rcx, rdi; this
0x180167a7b  call    ?SerializeTo@FontFaceKey@@QEBAIAEAV?$MemoryWriter@VWriteableMemoryRegion@@@@@Z; FontFaceKey::SerializeTo(MemoryWriter<WriteableMemoryRegion> &)
0x180167a80  mov     [rdi+38h], eax
0x180167a83  mov     [rsp+550h+lpString2], rbx; void (*)(void *)
0x180167a88  lea     r9, ??0FontNameList@@QEAA@XZ; void (*)(void *)
0x180167a8f  mov     r8d, 0Fh; unsigned __int64
0x180167a95  mov     rdx, r15; unsigned __int64
0x180167a98  lea     rcx, [rbp+450h+var_320]; void *
0x180167a9f  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180167aa4  nop
0x180167aa5  mov     rdx, [rsi+48h]
0x180167aa9  mov     eax, [rdi+0ACh]
0x180167aaf  lea     rcx, [rax+rax*2]
0x180167ab3  lea     r12, [rdx+rcx*8]
0x180167ab7  mov     eax, [rdi+0A8h]
0x180167abd  lea     rcx, [rax+rax*2]
0x180167ac1  lea     rsi, [rdx+rcx*8]
0x180167ac5  jmp     loc_180167BA7
0x180167aca  jnz     loc_180167D06
0x180167ad0  lea     rcx, [r15+r15*2]
0x180167ad4  lea     rbx, [rbp+450h+var_320]
0x180167adb  lea     rbx, [rbx+rcx*8]
0x180167adf  lea     rax, [rbp+450h+var_3A0]
0x180167ae6  mov     [rbp+450h+var_3D8], rax
0x180167aea  xorps   xmm0, xmm0
0x180167aed  movups  [rbp+450h+var_3A0], xmm0
0x180167af4  mov     [rbp+450h+var_390], 0
0x180167aff  mov     [rbp+450h+var_388], 0
0x180167b0a  lea     rdx, [rbp+450h+var_3C0]
0x180167b11  cmp     [rbp+450h+var_3A8], 7
0x180167b19  cmova   rdx, [rbp+450h+var_3C0]
0x180167b21  mov     r8, [rbp+450h+var_3B0]
0x180167b28  lea     rcx, [rbp+450h+var_3A0]
0x180167b2f  call    ??$_Construct@$01PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<2,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180167b34  nop
0x180167b35  mov     rax, [rsi+8]
0x180167b39  mov     [rbp+450h+Block], rax
0x180167b40  lock inc dword ptr [rax]
0x180167b43  mov     rcx, [rbx+8]
0x180167b47  cmp     rcx, [rbx+10h]
0x180167b4b  jnz     loc_180167D2A
0x180167b51  lea     r8, [rbp+450h+var_3A0]
0x180167b58  mov     rdx, rcx
0x180167b5b  mov     rcx, rbx
0x180167b5e  call    ??$_Emplace_reallocate@V?$KeyValuePair@V?$GenericLanguageTag@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@@VRefString@DWrite@@@@@?$vector@V?$KeyValuePair@V?$GenericLanguageTag@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@@VRefString@DWrite@@@@V?$allocator@V?$KeyValuePair@V?$GenericLanguageTag@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@@VRefString@DWrite@@@@@std@@@std@@AEAAPEAV?$KeyValuePair@V?$GenericLanguageTag@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@@VRefString@DWrite@@@@QEAV2@$$QEAV2@@Z; std::vector<KeyValuePair<GenericLanguageTag<std::wstring>,DWrite::RefString>>::_Emplace_reallocate<KeyValuePair<GenericLanguageTag<std::wstring>,DWrite::RefString>>(KeyValuePair<GenericLanguageTag<std::wstring>,DWrite::RefString> * const,KeyValuePair<GenericLanguageTag<std::wstring>,DWrite::RefString> &&)
0x180167b63  nop
0x180167b64  mov     rcx, [rbp+450h+Block]; Block
0x180167b6b  lea     rax, ?empty_@RefString@DWrite@@0UData@12@A; DWrite::RefString::Data DWrite::RefString::empty_
0x180167b72  cmp     rcx, rax
0x180167b75  jz      short loc_180167B89
0x180167b77  or      eax, 0FFFFFFFFh
0x180167b7a  lock xadd [rcx], eax
0x180167b7e  cmp     eax, 1
0x180167b81  jnz     short loc_180167B89
0x180167b83  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180167b88  nop
0x180167b89  lea     rcx, [rbp+450h+var_3A0]
0x180167b90  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180167b95  nop
0x180167b96  lea     rcx, [rbp+450h+var_3C0]
0x180167b9d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180167ba2  nop
0x180167ba3  add     rsi, 18h
0x180167ba7  cmp     rsi, r12
0x180167baa  jz      loc_180167D40
0x180167bb0  movsxd  r15, dword ptr [rsi]
0x180167bb3  cmp     r15d, 0Fh
0x180167bb7  jnb     short loc_180167BA3
0x180167bb9  mov     rbx, [rsi+10h]
0x180167bbd  mov     edi, [rbx+4]
0x180167bc0  lea     rcx, [rbp+450h+var_3C0]; void *
0x180167bc7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180167bcc  nop
0x180167bcd  test    rdi, rdi
0x180167bd0  jz      loc_180167AD0
0x180167bd6  lea     rdx, [rbx+8]
0x180167bda  mov     r8d, edi
0x180167bdd  lea     rcx, [rbp+450h+var_3C0]
0x180167be4  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::assign(wchar_t const * const,unsigned __int64)
0x180167be9  lea     r8, [rbp+450h+var_3C0]
0x180167bf0  cmp     [rbp+450h+var_3A8], 7
0x180167bf8  cmova   r8, [rbp+450h+var_3C0]
0x180167c00  mov     rbx, 676174676E616Ch
0x180167c0a  xor     ecx, ecx
0x180167c0c  test    rdi, rdi
0x180167c0f  jz      loc_180167CE2
0x180167c15  mov     r10w, 19h
0x180167c1a  movzx   edx, word ptr [r8+rcx*2]
0x180167c1f  lea     eax, [rdx-61h]
0x180167c22  cmp     ax, r10w
0x180167c26  jbe     short loc_180167C3A
0x180167c28  lea     eax, [rdx-41h]
0x180167c2b  cmp     ax, r10w
0x180167c2f  ja      short loc_180167C42
0x180167c31  add     dx, 20h ; ' '
0x180167c35  mov     [r8+rcx*2], dx
0x180167c3a  inc     rcx
0x180167c3d  cmp     rcx, rdi
0x180167c40  jb      short loc_180167C1A
0x180167c42  lea     rax, [rcx-1]
0x180167c46  cmp     rax, 7
0x180167c4a  ja      loc_180167CE2
0x180167c50  cmp     rcx, rdi
0x180167c53  jnb     loc_180167ACA
0x180167c59  cmp     word ptr [r8+rcx*2], 2Dh ; '-'
0x180167c5f  jnz     loc_1801685F0
0x180167c65  inc     rcx
0x180167c68  mov     r9, rcx
0x180167c6b  cmp     rcx, rdi
0x180167c6e  jnb     short loc_180167CAF
0x180167c70  mov     ebx, 9
0x180167c75  movzx   edx, word ptr [r8+rcx*2]
0x180167c7a  lea     eax, [rdx-61h]
0x180167c7d  cmp     ax, r10w
0x180167c81  jbe     short loc_180167C9D
0x180167c83  lea     eax, [rdx-30h]
0x180167c86  cmp     ax, bx
0x180167c89  jbe     short loc_180167C9D
0x180167c8b  lea     eax, [rdx-41h]
0x180167c8e  cmp     ax, r10w
0x180167c92  ja      short loc_180167CA5
0x180167c94  add     dx, 20h ; ' '
0x180167c98  mov     [r8+rcx*2], dx
0x180167c9d  inc     rcx
0x180167ca0  cmp     rcx, rdi
0x180167ca3  jb      short loc_180167C75
0x180167ca5  mov     rbx, 676174676E616Ch
0x180167caf  mov     rax, rcx
0x180167cb2  sub     rax, r9
0x180167cb5  dec     rax
0x180167cb8  cmp     rax, 7
0x180167cbc  jbe     short loc_180167C50
0x180167cbe  mov     ecx, 80070057h; int
0x180167cc3  mov     dword ptr [rsp+550h+Size], ecx
0x180167cc7  xor     edx, edx; unsigned int
0x180167cc9  call    ?CaptureStack@@YAXJI@Z; CaptureStack(long,uint)
0x180167cce  mov     r8d, 8Eh
0x180167cd4  mov     rdx, rbx
0x180167cd7  lea     rcx, [rsp+550h+Size]
0x180167cdc  call    ??$LogAndThrow@VArgumentException@@@@YAXAEBVArgumentException@@VEventTag@@I@Z; LogAndThrow<ArgumentException>(ArgumentException const &,EventTag,uint)
0x180167ce2  mov     ecx, 80070057h; int
0x180167ce7  mov     dword ptr [rsp+550h+Size], ecx
0x180167ceb  xor     edx, edx; unsigned int
0x180167ced  call    ?CaptureStack@@YAXJI@Z; CaptureStack(long,uint)
0x180167cf2  mov     r8d, 78h ; 'x'
0x180167cf8  mov     rdx, rbx
0x180167cfb  lea     rcx, [rsp+550h+Size]
0x180167d00  call    ??$LogAndThrow@VArgumentException@@@@YAXAEBVArgumentException@@VEventTag@@I@Z; LogAndThrow<ArgumentException>(ArgumentException const &,EventTag,uint)
0x180167d06  mov     ecx, 80070057h; int
0x180167d0b  mov     dword ptr [rsp+550h+Size], ecx
0x180167d0f  xor     edx, edx; unsigned int
0x180167d11  call    ?CaptureStack@@YAXJI@Z; CaptureStack(long,uint)
0x180167d16  mov     r8d, 93h
0x180167d1c  mov     rdx, rbx
0x180167d1f  lea     rcx, [rsp+550h+Size]
0x180167d24  call    ??$LogAndThrow@VArgumentException@@@@YAXAEBVArgumentException@@VEventTag@@I@Z; LogAndThrow<ArgumentException>(ArgumentException const &,EventTag,uint)
0x180167d2a  lea     rdx, [rbp+450h+var_3A0]
0x180167d31  call    ??0?$KeyValuePair@V?$GenericLanguageTag@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@@VRefString@DWrite@@@@QEAA@$$QEAV0@@Z; KeyValuePair<GenericLanguageTag<std::wstring>,DWrite::RefString>::KeyValuePair<GenericLanguageTag<std::wstring>,DWrite::RefString>(KeyValuePair<GenericLanguageTag<std::wstring>,DWrite::RefString> &&)
0x180167d36  add     qword ptr [rbx+8], 28h ; '('
0x180167d3b  jmp     loc_180167B64
0x180167d40  mov     rax, [rbp+450h+var_2E8]
0x180167d47  cmp     [rbp+450h+var_2F0], rax
0x180167d4e  jz      loc_180168DCF
0x180167d54  mov     rax, [rbp+450h+var_300]
0x180167d5b  cmp     [rbp+450h+var_308], rax
0x180167d62  jz      loc_180168D99
0x180167d68  mov     rax, [rbp+450h+var_1E0]
0x180167d6f  cmp     [rbp+450h+var_1E8], rax
0x180167d76  jz      loc_180168DFA
0x180167d7c  mov     rax, [rbp+450h+var_2D0]
0x180167d83  cmp     [rbp+450h+var_2D8], rax
0x180167d8a  jz      loc_180168D81
0x180167d90  xor     ebx, ebx
0x180167d92  mov     [rsp+550h+var_514], ebx
0x180167d96  xor     r9d, r9d
0x180167d99  mov     [rsp+550h+var_518], r9b
0x180167d9e  lea     r15, [rbx+rbx*2]
0x180167da2  mov     [rbp+450h+var_4C8], r15
0x180167da6  mov     rdx, [rbp+r15*8+450h+var_318]
0x180167dae  mov     rcx, [rbp+r15*8+450h+var_320]
0x180167db6  mov     r8, rdx
0x180167db9  sub     r8, rcx
0x180167dbc  sar     r8, 3
  ... truncated ...
```
