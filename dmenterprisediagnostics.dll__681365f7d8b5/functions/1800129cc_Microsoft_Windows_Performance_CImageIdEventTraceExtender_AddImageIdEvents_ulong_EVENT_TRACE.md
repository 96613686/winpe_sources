# Microsoft::Windows::Performance::CImageIdEventTraceExtender::AddImageIdEvents(ulong,_EVENT_TRACE *)

- ea: `0x1800129cc`
- end: `0x180013fc5`
- name: `?AddImageIdEvents@CImageIdEventTraceExtender@Performance@Windows@Microsoft@@AEAAJKPEAU_EVENT_TRACE@@@Z`
- size: `5625`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CImageIdEventTraceExtender *__hidden this, struct _EVENT_TRACE *, struct _EVENT_TRACE *)`
- caller_count: `1`
- callee_count: `32`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800169c0`

## callees

- `0x180001800`
- `0x180001824`
- `0x1800023e0`
- `0x1800029d5`
- `0x1800029e1`
- `0x180003658`
- `0x180003768`
- `0x180003b14`
- `0x180009a4c`
- `0x180009c3c`
- `0x18000c980`
- `0x1800123fc`
- `0x180012624`
- `0x18001266c`
- `0x1800127c4`
- `0x1800129cc`
- `0x180014240`
- `0x18001449c`
- `0x180014688`
- `0x180014bb0`
- `0x180014e68`
- `0x180014ecc`
- `0x180014f14`
- `0x180015bf4`
- `0x180015cf4`
- `0x1800176ec`
- `0x180017f3c`
- `0x180018a68`
- `0x1800238a4`
- `0x1800239a8`
- `0x180025290`
- `0x180027010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x1800138ca`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x1800138ca`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180012b16`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180012bc7`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180012b16`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180012bc7`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180013d07`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180013d07`

## string_xrefs

- `0x180012b55`: `Unable to parse image path: %s`
- `0x180012b7f`: `NULL path in image path.`
- `0x180012e2e`: `\SystemRoot\System32\DriverStore\FileRepository\`
- `0x180012eba`: `\\?\GLOBALROOT\DriverStores\BSPDRIVERS\System32\DriverStore\FileRepository\`
- `0x180012f83`: `OS bug workaround - trying alternate path: %s`
- `0x180013cb9`: `CreateEmbeddedPdb failed 0x%x. %s ({%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}) age: %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::Windows::Performance::CImageIdEventTraceExtender::AddImageIdEvents(
        Microsoft::Windows::Performance::CImageIdEventTraceExtender *this,
        struct _EVENT_TRACE *a2,
        struct _EVENT_TRACE *a3)
{
  struct _EVENT_TRACE *v3; // r15
  unsigned int v4; // r13d
  Microsoft::Windows::Performance::CImageIdEventTraceExtender *v5; // rdi
  unsigned int v6; // esi
  unsigned int v7; // ebx
  LARGE_INTEGER TimeStamp; // rax
  const wchar_t **v9; // r12
  wchar_t *v10; // rbx
  char FileName; // al
  __int64 v12; // rcx
  __int64 v13; // r14
  wchar_t *v14; // rax
  unsigned __int64 v15; // rcx
  unsigned __int64 v16; // rax
  __int64 result; // rax
  __int64 v18; // rbx
  wchar_t *v19; // rax
  unsigned __int64 v20; // rdx
  unsigned __int64 v21; // rax
  unsigned __int16 *v22; // rax
  int v23; // eax
  int v24; // r8d
  union _CVDD **v25; // r13
  wchar_t *v26; // rbx
  signed int Only2; // eax
  union _CVDD *v28; // r9
  int v29; // r14d
  unsigned __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // rdi
  LPCWSTR *v33; // rbx
  LPCWSTR *v34; // r8
  const WCHAR *v35; // rdx
  int v36; // eax
  unsigned __int16 *v37; // rdx
  LPCWSTR *v38; // rdx
  void **v39; // r12
  Microsoft::Windows::Performance::CImageIdEventTraceExtender *v40; // rcx
  unsigned int v41; // ecx
  int v42; // eax
  unsigned __int64 v43; // rdx
  unsigned __int64 v44; // rdx
  struct CODEVIEW_INFORMATION_1 **v45; // r14
  unsigned __int64 v46; // rdx
  unsigned __int16 *v47; // rdx
  struct CODEVIEW_INFORMATION_1 *v48; // r8
  unsigned int v49; // r12d
  unsigned int v50; // r14d
  int v51; // eax
  const union _CVDD *v52; // rdx
  union _CVDD *v53; // rcx
  const struct CODEVIEW_INFORMATION_1 *v54; // r8
  unsigned int v55; // r13d
  unsigned int v56; // r9d
  Microsoft::Windows::Performance::CImageIdEventTraceExtender *v57; // r14
  unsigned int v58; // r14d
  __int64 v59; // rcx
  int v60; // esp
  _DWORD *v61; // r13
  unsigned int v62; // eax
  unsigned int v63; // r12d
  __int64 v64; // rcx
  unsigned int v65; // eax
  _DWORD *v66; // rdx
  char v67; // al
  unsigned __int64 v68; // rax
  int v69; // eax
  int v70; // ecx
  unsigned int v71; // ecx
  unsigned int v72; // eax
  int EmbeddedPdb; // eax
  Microsoft::Windows::Performance::CImageIdEventTraceExtender *v74; // rbx
  int v75; // edx
  unsigned int *p_pguid; // rcx
  unsigned int v77; // r12d
  int v78; // eax
  int v79; // eax
  unsigned int v80; // [rsp+20h] [rbp-8E8h]
  unsigned int v81; // [rsp+20h] [rbp-8E8h]
  unsigned int v82; // [rsp+20h] [rbp-8E8h]
  union _CVDD **v83; // [rsp+20h] [rbp-8E8h]
  unsigned int **v84; // [rsp+28h] [rbp-8E0h]
  struct CODEVIEW_INFORMATION_1 **v85; // [rsp+30h] [rbp-8D8h]
  struct CODEVIEW_INFORMATION_1 **v86; // [rsp+30h] [rbp-8D8h]
  union _CVDD *v87; // [rsp+38h] [rbp-8D0h]
  struct CODEVIEW_INFORMATION_1 *v88; // [rsp+40h] [rbp-8C8h]
  struct CODEVIEW_INFORMATION_1 *v89; // [rsp+48h] [rbp-8C0h]
  bool *v90; // [rsp+50h] [rbp-8B8h]
  unsigned int *v91; // [rsp+58h] [rbp-8B0h]
  unsigned int v92; // [rsp+60h] [rbp-8A8h]
  bool *v93; // [rsp+60h] [rbp-8A8h]
  bool *v94; // [rsp+60h] [rbp-8A8h]
  unsigned int v95[2]; // [rsp+68h] [rbp-8A0h]
  __int64 MappedAsImage; // [rsp+70h] [rbp-898h]
  struct EMBEDDED_PDB_INFORMATION *v97; // [rsp+78h] [rbp-890h]
  struct XPerfCore::IErrorMessage *v98; // [rsp+90h] [rbp-878h] BYREF
  size_t Size; // [rsp+98h] [rbp-870h]
  Microsoft::Windows::Performance::CImageIdEventTraceExtender *v100; // [rsp+A0h] [rbp-868h] BYREF
  unsigned int v101; // [rsp+A8h] [rbp-860h] BYREF
  unsigned int v102; // [rsp+ACh] [rbp-85Ch]
  struct CODEVIEW_INFORMATION_1 *v103; // [rsp+B0h] [rbp-858h] BYREF
  union _CVDD *v104; // [rsp+B8h] [rbp-850h] BYREF
  unsigned __int16 *v105; // [rsp+C0h] [rbp-848h] BYREF
  unsigned int *v106; // [rsp+C8h] [rbp-840h]
  void *Src; // [rsp+D0h] [rbp-838h]
  unsigned int v108; // [rsp+D8h] [rbp-830h]
  __int64 v109; // [rsp+E0h] [rbp-828h] BYREF
  unsigned __int64 v110; // [rsp+E8h] [rbp-820h]
  __int64 v111; // [rsp+F0h] [rbp-818h] BYREF
  wchar_t *Str; // [rsp+F8h] [rbp-810h]
  union _CVDD *v113; // [rsp+108h] [rbp-800h]
  __int128 v114; // [rsp+110h] [rbp-7F8h] BYREF
  __int64 v115; // [rsp+120h] [rbp-7E8h]
  Microsoft::Windows::Performance::CImageIdEventTraceExtender *v116; // [rsp+128h] [rbp-7E0h]
  union _CVDD **v117; // [rsp+130h] [rbp-7D8h]
  __m128i si128; // [rsp+138h] [rbp-7D0h] BYREF
  unsigned __int16 *v119; // [rsp+148h] [rbp-7C0h]
  void *v120; // [rsp+150h] [rbp-7B8h]
  struct _EVENT_TRACE *v121; // [rsp+158h] [rbp-7B0h]
  Microsoft::Windows::Performance::CImageIdEventTraceExtender *v122; // [rsp+160h] [rbp-7A8h]
  union _CVDD *v123; // [rsp+168h] [rbp-7A0h]
  ATL::CAtlException *v124; // [rsp+170h] [rbp-798h] BYREF
  __int128 v125; // [rsp+180h] [rbp-788h] BYREF
  __m256i v126; // [rsp+190h] [rbp-778h]
  __int128 v127; // [rsp+1B0h] [rbp-758h]
  __int128 v128; // [rsp+1C0h] [rbp-748h]
  int v129; // [rsp+1D0h] [rbp-738h]
  int v130; // [rsp+1D4h] [rbp-734h]
  LPCWSTR lpFileName[2]; // [rsp+1E0h] [rbp-728h] BYREF
  __int64 v132; // [rsp+1F0h] [rbp-718h]
  unsigned __int64 v133; // [rsp+1F8h] [rbp-710h]
  GUID pguid; // [rsp+200h] [rbp-708h] BYREF
  unsigned __int64 v135; // [rsp+210h] [rbp-6F8h] BYREF
  unsigned __int64 v136; // [rsp+218h] [rbp-6F0h] BYREF
  unsigned int v137; // [rsp+220h] [rbp-6E8h] BYREF
  unsigned int v138; // [rsp+224h] [rbp-6E4h]
  unsigned __int16 v139[4]; // [rsp+228h] [rbp-6E0h] BYREF
  int v140; // [rsp+230h] [rbp-6D8h]
  wchar_t String2[56]; // [rsp+850h] [rbp-B8h] BYREF

  v3 = a3;
  v121 = a3;
  v4 = (unsigned int)a2;
  v102 = (unsigned int)a2;
  v5 = this;
  v116 = this;
  v122 = this;
  v108 = (unsigned int)a2;
  *(_QWORD *)&pguid.Data1 = a3;
  v6 = 0;
  v109 = 0;
  v110 = 0;
  v111 = 0;
  Str = 0;
  if ( (int)Microsoft::Windows::Performance::ParseImageEvent(
              (Microsoft::Windows::Performance *)&v109,
              (struct Microsoft::Windows::Performance::CImageData *)a3,
              (const struct _EVENT_TRACE *)(unsigned int)a2,
              *((_DWORD *)this + 8),
              v80) < 0 )
  {
    if ( (**((unsigned __int8 (__fastcall ***)(__int64, const wchar_t *))v5 + 47))(
           (__int64)v5 + 376,
           L"Failed to parse image event.") )
    {
      Microsoft::Windows::Performance::CImageIdEventTraceExtender::AddErrorEvent(v5, v3);
    }
    return 1;
  }
  TimeStamp = v3->Header.TimeStamp;
  if ( *((_QWORD *)v5 + 5) == TimeStamp.QuadPart && *((_DWORD *)v5 + 12) == (_DWORD)v109 && *((_QWORD *)v5 + 7) == v110 )
    return 1;
  try
  {
    v9 = (const wchar_t **)((char *)v5 + 192);
    v10 = Str;
    FileName = Performance::NtImagePathDecoder::CLocalNtImagePathDecoder::GetFileName(
                 (char *)v5 + 64,
                 Str,
                 (char *)v5 + 192);
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  catch ( ATL::CAtlException *v124 )
  {
    if ( *(_DWORD *)v124 == -2147024882 )
      return 2147942414LL;
    *((_BYTE *)v122 + 200) = 1;
    return 1;
  }
  if ( !FileName )
  {
    v12 = *((_QWORD *)v5 + 23);
    if ( !v12 || !(unsigned __int8)Performance::NtImagePathDecoder::CNtImagePathDecoderBase::GetFileName(v12, v10, v9) )
    {
      if ( v10 )
      {
        v13 = 0;
        if ( !*((_BYTE *)v5 + 201) )
        {
          v14 = wcsrchr(v10, 0x5Cu);
          if ( v14 )
          {
            v15 = v14 - v10 + 1;
            v16 = -1;
            do
              ++v16;
            while ( v10[v16] );
            v13 = v15 & -(__int64)(v15 < v16);
          }
        }
        if ( !(**((unsigned __int8 (***)(__int64, const wchar_t *, ...))v5 + 47))(
                (__int64)v5 + 376,
                L"Unable to parse image path: %s",
                &v10[v13]) )
          return 1;
      }
      else if ( !(**((unsigned __int8 (__fastcall ***)(__int64, const wchar_t *))v5 + 47))(
                   (__int64)v5 + 376,
                   L"NULL path in image path.") )
      {
        return 1;
      }
      Microsoft::Windows::Performance::CImageIdEventTraceExtender::AddErrorEvent(v5, v3);
      return 1;
    }
  }
  try
  {
    v113 = (Microsoft::Windows::Performance::CImageIdEventTraceExtender *)((char *)v5 + 201);
    if ( *((_BYTE *)v5 + 201) )
    {
      (**((void (***)(__int64, const wchar_t *, ...))v5 + 47))((__int64)v5 + 376, L"%s [%s] failure: ", *v9, v10);
    }
    else
    {
      v18 = 0;
      v19 = wcsrchr(*v9, 0x5Cu);
      if ( v19 )
      {
        v20 = v19 - *v9 + 1;
        v21 = -1;
        do
          ++v21;
        while ( (*v9)[v21] );
        v18 = v20 & -(__int64)(v20 < v21);
      }
      (**((void (***)(__int64, const wchar_t *, ...))v5 + 47))((__int64)v5 + 376, L"%s failure: ", &(*v9)[v18]);
    }
    v123 = (Microsoft::Windows::Performance::CImageIdEventTraceExtender *)((char *)v5 + 201);
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  memset_0(&v135, 0, 0x640u);
  if ( v4 == 4 )
  {
    v22 = (unsigned __int16 *)&v137;
  }
  else
  {
    if ( v4 != 8 )
      return 2147549183LL;
    v22 = v139;
  }
  v106 = (unsigned int *)v22;
  HIDWORD(v98) = 0;
  v104 = 0;
  v105 = 0;
  v103 = 0;
  v114 = 0;
  v115 = 0;
  BYTE1(v98) = 0;
  Src = (char *)v5 + 208;
  v23 = Microsoft::Windows::Performance::CCvDDCache::Find(
          (Microsoft::Windows::Performance::CImageIdEventTraceExtender *)((char *)v5 + 208),
          *v9,
          v111,
          (unsigned int *)&v98 + 1,
          &v104,
          (const unsigned int **)&v105,
          &v103,
          (unsigned int *)&v111 + 1,
          (unsigned int *)&v109 + 1,
          (struct EMBEDDED_PDB_INFORMATION *)&v114,
          (bool *)&v98 + 1,
          v22,
          v92);
  v24 = v23;
  if ( v23 >= 0 )
  {
    v7 = 1;
    v49 = HIDWORD(v111);
    v58 = v109;
    LODWORD(Size) = HIDWORD(v98);
    v113 = (union _CVDD *)v105;
    v105 = (unsigned __int16 *)v103;
LABEL_110:
    if ( v4 == 4 )
    {
      HIDWORD(v98) = v110;
      v135 = __PAIR64__(HIDWORD(v109), v110);
      v136 = __PAIR64__(v49, v58);
    }
    else
    {
      if ( v4 != 8 )
        return 2147549183LL;
      v135 = v110;
      v136 = HIDWORD(v109);
      v137 = v58;
      v138 = v49;
      HIDWORD(v98) = v110;
    }
    v59 = -1;
    do
      ++v59;
    while ( *((_WORD *)v106 + v59) );
    v125 = *(_OWORD *)&v3->Header.Size;
    v126 = *(__m256i *)&v3->Header.TimeStamp.LowPart;
    v127 = *(_OWORD *)&v3->InstanceId;
    v128 = *(_OWORD *)v3->ParentGuid.Data4;
    v130 = HIDWORD(*(_QWORD *)&v3->MofLength);
    *(struct _GUID *)&v126.m256i_u64[1] = ImageIdGuid;
    DWORD1(v125) = 0x20000;
    HIDWORD(v125) = v58;
    *((_QWORD *)&v128 + 1) = &v135;
    v129 = (_DWORD)v106 + 2 * v59 + 2 - (v60 + 528);
    result = (*(__int64 (__fastcall **)(_QWORD, __int128 *, _QWORD, _QWORD))(**((_QWORD **)v5 + 2) + 192LL))(
               *((_QWORD *)v5 + 2),
               &v125,
               0,
               0);
    if ( (int)result < 0 )
      return result;
    v61 = 0;
    v106 = 0;
    v62 = 0;
    LODWORD(v100) = 0;
    v63 = Size;
    while ( v62 < v63 )
    {
      v64 = v62;
      v65 = *((_DWORD *)v113 + v62);
      LODWORD(Size) = v65;
      if ( v65 >= 4 )
      {
        if ( v65 > 0x628 )
          return 2147549183LL;
        v66 = (_DWORD *)((char *)v104 + 1576 * v64);
        Src = v66;
        if ( *v66 )
        {
          switch ( *v66 )
          {
            case 1:
              v67 = 33;
              break;
            case 2:
              v67 = 34;
              break;
            case 3:
              v67 = 37;
              break;
            case 0x3031424E:
              v67 = 35;
              break;
            case 0x53445352:
              v67 = 36;
              break;
            default:
              return v7;
          }
        }
        else
        {
          v67 = 32;
        }
        LOBYTE(v98) = v67;
        if ( (_DWORD)v114 )
        {
          if ( v67 == 36 )
          {
            v68 = -1;
            do
              ++v68;
            while ( *((_BYTE *)v66 + v68 + 24) );
            if ( v68 <= 7 || (v69 = _o__stricmp((char *)v66 + v68 + 17, ".ni.pdb"), v66 = Src, v69) )
            {
              v61 = v66;
              v106 = v66;
            }
          }
        }
        if ( v102 == 4 )
        {
          memcpy_0((char *)&v135 + 4, v66, (unsigned int)Size);
          v135 = __PAIR64__(v58, HIDWORD(v98));
          v70 = Size + 4;
        }
        else
        {
          if ( v102 != 8 )
            return 2147549183LL;
          memcpy_0(&v136, v66, (unsigned int)Size);
          v135 = v110;
          LODWORD(v136) = v58;
          v70 = Size + 8;
        }
        v125 = *(_OWORD *)&v3->Header.Size;
        v126 = *(__m256i *)&v3->Header.TimeStamp.LowPart;
        v127 = *(_OWORD *)&v3->InstanceId;
        v128 = *(_OWORD *)v3->ParentGuid.Data4;
        v130 = HIDWORD(*(_QWORD *)&v3->MofLength);
        *(struct _GUID *)&v126.m256i_u64[1] = ImageIdGuid;
        DWORD1(v125) = (unsigned __int8)v98 | 0x20000;
        HIDWORD(v125) = v58;
        *((_QWORD *)&v128 + 1) = &v135;
        v129 = v70;
        result = (*(__int64 (__fastcall **)(_QWORD, __int128 *, _QWORD, _QWORD))(**((_QWORD **)v5 + 2) + 192LL))(
                   *((_QWORD *)v5 + 2),
                   &v125,
                   0,
                   0);
        if ( (int)result < 0 )
          return result;
      }
      v62 = (_DWORD)v100 + 1;
      LODWORD(v100) = v62;
    }
    v71 = 0;
    LODWORD(v100) = 0;
    if ( v63 )
    {
      v72 = v102;
      do
      {
        if ( v72 == 4 )
        {
          v135 = __PAIR64__(v58, HIDWORD(v98));
        }
        else
        {
          if ( v72 != 8 )
            return 2147549183LL;
          v135 = v110;
          LODWORD(v136) = v58;
        }
        if ( *(_DWORD *)&v105[4 * v71] )
        {
          HIDWORD(v136) = *(_DWORD *)&v105[4 * v71];
          v137 = *(_DWORD *)&v105[4 * v71 + 2];
          *(_OWORD *)String2 = *(_OWORD *)&v3->Header.Size;
          *(_OWORD *)&String2[8] = *(_OWORD *)&v3->Header.TimeStamp.LowPart;
          *(union _EVENT_TRACE_HEADER::$146F82FB58FCEC23F5D30A6BD72C4E4F *)&String2[16] = *(union _EVENT_TRACE_HEADER::$146F82FB58FCEC23F5D30A6BD72C4E4F *)((char *)&v3->Header.24 + 8);
          *(_OWORD *)&String2[24] = *(_OWORD *)&v3->InstanceId;
          *(_OWORD *)&String2[32] = *(_OWORD *)v3->ParentGuid.Data4;
          *(_DWORD *)&String2[42] = HIDWORD(*(_QWORD *)&v3->MofLength);
          *(struct _GUID *)&String2[12] = ImageIdGuid;
          *(_DWORD *)&String2[2] = 131110;
          *(_DWORD *)&String2[6] = v58;
          *(_QWORD *)&String2[36] = &v135;
          *(_DWORD *)&String2[40] = 20;
          result = (*(__int64 (__fastcall **)(_QWORD, wchar_t *, _QWORD, _QWORD))(**((_QWORD **)v5 + 2) + 192LL))(
                     *((_QWORD *)v5 + 2),
                     String2,
                     0,
                     0);
          if ( (int)result < 0 )
            return result;
          v72 = v102;
          v71 = (unsigned int)v100;
        }
        LODWORD(v100) = ++v71;
      }
      while ( v71 < v63 );
    }
    if ( !(_DWORD)v114 )
    {
      v77 = v102;
      goto LABEL_170;
    }
    pguid = 0;
    if ( v61 )
    {
      try
      {
        Src = v61 + 1;
        v117 = (union _CVDD **)(v61 + 6);
        EmbeddedPdb = Microsoft::Windows::Performance::CImageIdEventTraceExtender::CreateEmbeddedPdb(
                        v5,
                        (const char *)v61 + 24,
                        (const struct _GUID *)(v61 + 1),
                        v61[5],
                        (DWORD *)&v114);
      }
      catch ( std::bad_alloc )
      {
        return 2147942414LL;
      }
      v108 = EmbeddedPdb;
      if ( EmbeddedPdb < 0 )
      {
        LODWORD(v97) = v106[5];
        LODWORD(MappedAsImage) = *((unsigned __int8 *)v61 + 19);
        v95[0] = *((unsigned __int8 *)v61 + 18);
        LODWORD(v93) = *((unsigned __int8 *)v61 + 17);
        LODWORD(v91) = *((unsigned __int8 *)v61 + 16);
        LODWORD(v90) = *((unsigned __int8 *)v61 + 15);
        LODWORD(v89) = *((unsigned __int8 *)v61 + 14);
        LODWORD(v88) = *((unsigned __int8 *)v61 + 13);
        LODWORD(v87) = *((unsigned __int8 *)v61 + 12);
        LODWORD(v85) = *((unsigned __int16 *)v61 + 5);
        LODWORD(v84) = *((unsigned __int16 *)v61 + 4);
        LODWORD(v83) = *(_DWORD *)Src;
        v74 = v116;
        (**((void (***)(char *, const wchar_t *, ...))v5 + 47))(
          (char *)v116 + 376,
          L"CreateEmbeddedPdb failed 0x%x. %s ({%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}) age: %d",
          v108,
          v117,
          v83,
          v84,
          v85,
          v87,
          v88,
          v89,
          v90,
          v91,
          v93,
          *(_QWORD *)v95,
          MappedAsImage,
          v97);
        Microsoft::Windows::Performance::CImageIdEventTraceExtender::AddErrorEvent(v74, v121);
        return 1;
      }
      v75 = v61[5];
      p_pguid = (unsigned int *)Src;
    }
    else
    {
      if ( CoCreateGuid(&pguid) < 0 )
        return v7;
      v75 = 1;
      p_pguid = (unsigned int *)&pguid;
    }
    v77 = v102;
    if ( v102 == 4 )
    {
      v135 = __PAIR64__(v58, HIDWORD(v98));
LABEL_167:
      HIDWORD(v136) = v115;
      v137 = *p_pguid;
      v138 = p_pguid[1];
      *(_QWORD *)v139 = *((_QWORD *)p_pguid + 1);
      v140 = v75;
      *(_OWORD *)String2 = *(_OWORD *)&v3->Header.Size;
      *(_OWORD *)&String2[8] = *(_OWORD *)&v3->Header.TimeStamp.LowPart;
      *(union _EVENT_TRACE_HEADER::$146F82FB58FCEC23F5D30A6BD72C4E4F *)&String2[16] = *(union _EVENT_TRACE_HEADER::$146F82FB58FCEC23F5D30A6BD72C4E4F *)((char *)&v3->Header.24 + 8);
      *(_OWORD *)&String2[24] = *(_OWORD *)&v3->InstanceId;
      *(_OWORD *)&String2[32] = *(_OWORD *)v3->ParentGuid.Data4;
      *(_DWORD *)&String2[42] = HIDWORD(*(_QWORD *)&v3->MofLength);
      *(struct _GUID *)&String2[12] = ImageIdGuid;
      *(_DWORD *)&String2[2] = 65575;
      *(_DWORD *)&String2[6] = v58;
      *(_QWORD *)&String2[36] = &v135;
      wcscpy(&String2[40], L"$");
      result = (*(__int64 (__fastcall **)(_QWORD, wchar_t *, _QWORD, _QWORD))(**((_QWORD **)v5 + 2) + 192LL))(
                 *((_QWORD *)v5 + 2),
                 String2,
                 0,
                 0);
      if ( (int)result < 0 )
        return result;
LABEL_170:
      if ( !BYTE1(v98) )
        return 0;
      if ( v77 == 4 )
      {
        v135 = __PAIR64__(v58, HIDWORD(v98));
        v78 = 8;
      }
      else
      {
        if ( v77 != 8 )
          return 2147549183LL;
        v135 = v110;
        LODWORD(v136) = v58;
        v78 = 12;
      }
      *(_OWORD *)String2 = *(_OWORD *)&v3->Header.Size;
      *(_OWORD *)&String2[8] = *(_OWORD *)&v3->Header.TimeStamp.LowPart;
      *(union _EVENT_TRACE_HEADER::$146F82FB58FCEC23F5D30A6BD72C4E4F *)&String2[16] = *(union _EVENT_TRACE_HEADER::$146F82FB58FCEC23F5D30A6BD72C4E4F *)((char *)&v3->Header.24 + 8);
      *(_OWORD *)&String2[24] = *(_OWORD *)&v3->InstanceId;
      *(_OWORD *)&String2[32] = *(_OWORD *)v3->ParentGuid.Data4;
      *(_DWORD *)&String2[42] = HIDWORD(*(_QWORD *)&v3->MofLength);
      *(struct _GUID *)&String2[12] = ImageIdGuid;
      *(_DWORD *)&String2[2] = 65576;
      *(_DWORD *)&String2[6] = v58;
      *(_QWORD *)&String2[36] = &v135;
      *(_DWORD *)&String2[40] = v78;
      v79 = (*(__int64 (__fastcall **)(_QWORD, wchar_t *, _QWORD, _QWORD))(**((_QWORD **)v5 + 2) + 192LL))(
              *((_QWORD *)v5 + 2),
              String2,
              0,
              0);
      if ( v79 < 0 )
        return (unsigned int)v79;
      return v6;
    }
    if ( v102 == 8 )
    {
      v135 = v110;
      LODWORD(v136) = v58;
      goto LABEL_167;
    }
    return 2147549183LL;
  }
  if ( v23 == -2147023728 )
  {
    LODWORD(Size) = *((_DWORD *)v5 + 92);
    HIDWORD(v98) = Size;
    v103 = (Microsoft::Windows::Performance::CImageIdEventTraceExtender *)((char *)v5 + 344);
    if ( !*((_QWORD *)v5 + 43) )
      return 2147549183LL;
    v25 = (union _CVDD **)((char *)v5 + 352);
    v117 = (union _CVDD **)((char *)v5 + 352);
    if ( !*((_QWORD *)v5 + 44) )
      return 2147549183LL;
    v105 = (unsigned __int16 *)((char *)v5 + 360);
    if ( !*((_QWORD *)v5 + 45) )
      return 2147549183LL;
    LOBYTE(v98) = Performance::COSVersionInfo::IsWin8AndUp();
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v119 = 0;
    v120 = 0;
    v26 = (wchar_t *)*v9;
    v100 = (Microsoft::Windows::Performance::CImageIdEventTraceExtender *)v26;
    v104 = (union _CVDD *)v26;
    Only2 = XPerfCore::CFileMapping::MapExistingFileReadOnly2(
              (XPerfCore::CFileMapping *)&si128,
              v26,
              (char)v98,
              (Microsoft::Windows::Performance::CImageIdEventTraceExtender *)((char *)v5 + 376));
    v29 = Only2;
    if ( Only2 >= 0 )
      goto LABEL_71;
    if ( Only2 != -2147024893
      || (wcscpy(String2, L"\\SystemRoot\\System32\\DriverStore\\FileRepository\\"), wcsncmp_0(Str, String2, 0x30u)) )
    {
      v40 = (Microsoft::Windows::Performance::CImageIdEventTraceExtender *)v26;
LABEL_69:
      v39 = (void **)v103;
      goto LABEL_81;
    }
    try
    {
      std::wstring::wstring(
        lpFileName,
        L"\\\\?\\GLOBALROOT\\DriverStores\\BSPDRIVERS\\System32\\DriverStore\\FileRepository\\");
      v30 = -1;
      do
        ++v30;
      while ( Str[v30 + 48] );
      v31 = v132;
      if ( v30 > v133 - v132 )
      {
        std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
          lpFileName,
          v30);
      }
      else
      {
        v32 = v132 + v30;
        v132 += v30;
        v33 = lpFileName;
        if ( v133 > 7 )
          v33 = (LPCWSTR *)lpFileName[0];
        memmove_0((char *)v33 + 2 * v31, Str + 48, 2 * v30);
        *((_WORD *)v33 + v32) = 0;
        v5 = v116;
        v26 = (wchar_t *)v100;
      }
      v34 = lpFileName;
      if ( v133 > 7 )
        v34 = (LPCWSTR *)lpFileName[0];
      (*(void (**)(__int64, const wchar_t *, ...))(*((_QWORD *)v5 + 47) + 8LL))(
        (__int64)v5 + 376,
        L"OS bug workaround - trying alternate path: %s",
        v34);
      v35 = (const WCHAR *)lpFileName;
      if ( v133 > 7 )
        v35 = lpFileName[0];
      v29 = XPerfCore::CFileMapping::MapExistingFileReadOnly2(
              (XPerfCore::CFileMapping *)&si128,
              v35,
              (char)v98,
              (Microsoft::Windows::Performance::CImageIdEventTraceExtender *)((char *)v5 + 376));
      if ( v29 >= 0 )
      {
        LODWORD(v100) = 0;
        v36 = XPerfCore::CFileMapping::GetFileName((XPerfCore::CFileMapping *)&si128, 0, (unsigned int *)&v100);
        if ( v36 == 122 )
        {
          std::wstring::reserve(lpFileName, (unsigned int)v100);
          v37 = (unsigned __int16 *)lpFileName;
          if ( v133 > 7 )
            v37 = (unsigned __int16 *)lpFileName[0];
          v36 = XPerfCore::CFileMapping::GetFileName((XPerfCore::CFileMapping *)&si128, v37, (unsigned int *)&v100);
        }
        if ( v36 )
        {
          if ( v36 > 0 )
            v29 = (unsigned __int16)v36 | 0x80070000;
          else
            v29 = v36;
        }
        else
        {
          v38 = lpFileName;
          if ( v133 > 7 )
            v38 = (LPCWSTR *)lpFileName[0];
          ATL::CSimpleStringT<unsigned short,0>::SetString(v9, v38);
          v26 = (wchar_t *)*v9;
          v104 = (union _CVDD *)*v9;
        }
      }
      v100 = (Microsoft::Windows::Performance::CImageIdEventTraceExtender *)v26;
      std::wstring::~wstring(lpFileName);
    }
    catch ( std::bad_alloc )
    {
      v6 = 0;
      v29 = -2147024882;
      LODWORD(Size) = HIDWORD(v98);
      v40 = v104;
      v100 = v104;
      v113 = v123;
      v5 = v122;
      v116 = v122;
      v102 = v108;
      v3 = *(struct _EVENT_TRACE **)&pguid.Data1;
      v121 = *(struct _EVENT_TRACE **)&pguid.Data1;
      v25 = v117;
      goto LABEL_69;
    }
    if ( v29 >= 0 )
    {
LABEL_71:
      v41 = (unsigned int)v120;
      v104 = (union _CVDD *)v120;
      if ( (unsigned __int64)v120 >= 0xFFFFFFFF )
      {
        v41 = -1;
        v104 = (union _CVDD *)0xFFFFFFFFLL;
      }
      LODWORD(v93) = 780;
      v39 = (void **)v103;
      v42 = XPerf::Internal::CvDbgInfoFromImage2(
              (XPerf::Internal *)v26,
              v119,
              (void *)v41,
              v111,
              v81,
              (unsigned int *)&v98 + 1,
              *(union _CVDD **)v103,
              *v25,
              *(struct CODEVIEW_INFORMATION_1 **)v105,
              (struct CODEVIEW_INFORMATION_1 *)((char *)&v111 + 4),
              (unsigned int *)&v109 + 1,
              v106,
              (unsigned __int16 *)v93,
              (unsigned int)&v101,
              (BOOLEAN)v98,
              (struct EMBEDDED_PDB_INFORMATION *)&v114,
              (struct EMBEDDED_PDB_INFORMATION *)((char *)&v98 + 1),
              (bool *)v5 + 376,
              v98);
      v29 = v42;
      if ( v42 >= 0 )
        goto LABEL_91;
      if ( v42 == -2146893023 )
      {
        *((_DWORD *)v5 + 92) = 0;
        operator delete(*v39, v43);
        *v39 = 0;
        operator delete(*v25, v44);
        *v25 = 0;
        v45 = (struct CODEVIEW_INFORMATION_1 **)v105;
        operator delete(*(void **)v105, v46);
        *v45 = 0;
        if ( !(unsigned __int8)ATL::CAutoVectorPtr<_CVDD>::Allocate(v39, HIDWORD(v98))
          || !(unsigned __int8)ATL::CAutoVectorPtr<unsigned long>::Allocate(v25, HIDWORD(v98))
          || !(unsigned __int8)ATL::CAutoVectorPtr<unsigned __int64>::Allocate(v45, HIDWORD(v98)) )
        {
          v7 = -2147024882;
          goto LABEL_99;
        }
        *((_DWORD *)v5 + 92) = HIDWORD(v98);
        LODWORD(v94) = 780;
        v29 = XPerf::Internal::CvDbgInfoFromImage2(
                (XPerf::Internal *)v26,
                v119,
                (void *)(unsigned int)v104,
                v111,
                v82,
                (unsigned int *)&v98 + 1,
                (union _CVDD *)*v39,
                *v25,
                *v45,
                (struct CODEVIEW_INFORMATION_1 *)((char *)&v111 + 4),
                (unsigned int *)&v109 + 1,
                v106,
                (unsigned __int16 *)v94,
                (unsigned int)&v101,
                (BOOLEAN)v98,
                (struct EMBEDDED_PDB_INFORMATION *)&v114,
                (struct EMBEDDED_PDB_INFORMATION *)((char *)&v98 + 1),
                (bool *)v5 + 376,
                v98);
        if ( v29 >= 0 )
        {
LABEL_91:
          v7 = 1;
          v49 = HIDWORD(v111);
          v50 = HIDWORD(v98);
          LODWORD(Size) = HIDWORD(v98);
LABEL_93:
          if ( !*(_BYTE *)v113 )
          {
            v51 = Microsoft::Windows::Performance::CImageIdEventTraceExtender::RemovePIIFromCvDD(
                    v40,
                    v50,
                    *(union _CVDD **)v103,
                    (unsigned int *)*v25);
            if ( v51 < 0 )
              goto LABEL_98;
          }
          v52 = *(const union _CVDD **)v103;
          v104 = *(union _CVDD **)v103;
          v53 = *v25;
          v113 = *v25;
          v54 = *(const struct CODEVIEW_INFORMATION_1 **)v105;
          v105 = *(unsigned __int16 **)v105;
          if ( (*((_DWORD *)v5 + 93) & 0x100) == 0 )
          {
            v114 = 0;
            v115 = 0;
          }
          LOBYTE(v98) = 0;
          v55 = HIDWORD(v109);
          v56 = v50;
          v57 = v100;
          v51 = Microsoft::Windows::Performance::CCvDDCache::Add(
                  (Microsoft::Windows::Performance::CCvDDCache *)Src,
                  (const unsigned __int16 *)v100,
                  v111,
                  v56,
                  v52,
                  (const unsigned int *)v53,
                  v54,
                  v49,
                  HIDWORD(v109),
                  (struct EMBEDDED_PDB_INFORMATION *)&v114,
                  SBYTE1(v98),
                  (const unsigned __int16 *)v106,
                  (bool *)&v98);
          if ( v51 < 0 )
          {
LABEL_98:
            v7 = v51;
            goto LABEL_99;
          }
          if ( (_BYTE)v98 )
          {
            v86 = (struct CODEVIEW_INFORMATION_1 **)v57;
            v58 = v109;
            Microsoft::Windows::Performance::CImageIdEventTraceExtender::AddFileVersionEvent(
              v5,
              v3,
              v109,
              v55,
              v49,
              (const unsigned __int16 *)v106,
              (const unsigned __int16 *)v86,
              (struct XPerfCore::CFileMapping *)&si128);
          }
          else
          {
            v58 = v109;
          }
          XPerfCore::CFileMapping::Cleanup((XPerfCore::CFileMapping *)&si128);
          v4 = v102;
          goto LABEL_110;
        }
      }
      LODWORD(Size) = HIDWORD(v98);
    }
    else
    {
      v39 = (void **)v103;
    }
    v40 = v100;
LABEL_81:
    if ( !*((_BYTE *)v5 + 202) )
    {
      v7 = 1;
      v49 = HIDWORD(v111);
      goto LABEL_89;
    }
    if ( *v39 )
    {
      if ( *v25 )
      {
        v47 = v105;
        v48 = *(struct CODEVIEW_INFORMATION_1 **)v105;
        if ( *(_QWORD *)v105 )
        {
          v7 = 1;
          LODWORD(Size) = 1;
          v49 = HIDWORD(v111);
          *(_DWORD *)v48 = HIDWORD(v111);
          *(_WORD *)(*(_QWORD *)v47 + 4LL) = 0;
          *(_WORD *)(*(_QWORD *)v47 + 6LL) = 0;
          v29 = Microsoft::Xbox::CvDbgInfoFromVBI(
                  v40,
                  v47,
                  *(struct Microsoft::Windows::Performance::CErrorEvent **)v103,
                  v28);
          *(_DWORD *)*v25 = 1576;
LABEL_89:
          if ( v29 < 0 )
          {
            Microsoft::Windows::Performance::CImageIdEventTraceExtender::AddErrorEvent(v5, v3);
            Microsoft::Windows::Performance::CCvDDCache::AddFailure(
              (Microsoft::Windows::Performance::CCvDDCache *)Src,
              (const unsigned __int16 *)v100,
              v111);
            goto LABEL_99;
          }
          v50 = Size;
          goto LABEL_93;
        }
      }
    }
    v7 = -2147418113;
LABEL_99:
    XPerfCore::CFileMapping::Cleanup((XPerfCore::CFileMapping *)&si128);
    return v7;
  }
  if ( v23 == -2147467259 || v23 == -2147024774 )
    return 1;
  result = 2147942414LL;
  if ( v24 != -2147024882 )
  {
    (*(void (**)(__int64, const wchar_t *, ...))(*((_QWORD *)v5 + 47) + 8LL))(
      (__int64)v5 + 376,
      L"unexpected caching error: %x");
    Microsoft::Windows::Performance::CImageIdEventTraceExtender::AddErrorEvent(v5, v3);
    result = 1;
    *((_BYTE *)v5 + 200) = 1;
  }
  return result;
}

```

## disassembly

```asm
0x1800129cc  mov     r11, rsp
0x1800129cf  push    rbx
0x1800129d0  push    rsi
0x1800129d1  push    rdi
0x1800129d2  push    r12
0x1800129d4  push    r13
0x1800129d6  push    r14
0x1800129d8  push    r15
0x1800129da  sub     rsp, 8D0h
0x1800129e1  mov     rax, cs:__security_cookie
0x1800129e8  xor     rax, rsp
0x1800129eb  mov     [rsp+908h+var_48], rax
0x1800129f3  mov     r15, r8
0x1800129f6  mov     [rsp+908h+var_7B0], r8
0x1800129fe  mov     r13d, edx
0x180012a01  mov     [rsp+908h+var_85C], edx
0x180012a08  mov     rdi, rcx
0x180012a0b  mov     [rsp+908h+var_7E0], rcx
0x180012a13  mov     [rsp+908h+var_7A8], rcx
0x180012a1b  mov     [rsp+908h+var_830], edx
0x180012a22  mov     qword ptr [rsp+908h+pguid.Data1], r8
0x180012a2a  xor     esi, esi
0x180012a2c  mov     [r11-828h], rsi
0x180012a33  mov     [r11-820h], rsi
0x180012a3a  mov     [r11-818h], rsi
0x180012a41  mov     [r11-810h], rsi
0x180012a48  mov     r9d, [rcx+20h]; unsigned int
0x180012a4c  mov     r8d, edx; struct _EVENT_TRACE *
0x180012a4f  mov     rdx, r15; struct Microsoft::Windows::Performance::CImageData *
0x180012a52  lea     rcx, [r11-828h]; this
0x180012a59  call    ?ParseImageEvent@Performance@Windows@Microsoft@@YAJPEAUCImageData@123@PEBU_EVENT_TRACE@@KK@Z; Microsoft::Windows::Performance::ParseImageEvent(Microsoft::Windows::Performance::CImageData *,_EVENT_TRACE const *,ulong,ulong)
0x180012a5e  test    eax, eax
0x180012a60  jns     short loc_180012A94
0x180012a62  lea     rcx, [rdi+178h]
0x180012a69  mov     rax, [rcx]
0x180012a6c  lea     rdx, aFailedToParseI; "Failed to parse image event."
0x180012a73  mov     rax, [rax]
0x180012a76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a7b  test    al, al
0x180012a7d  jz      short loc_180012A8A
0x180012a7f  mov     rdx, r15; struct _EVENT_TRACE *
0x180012a82  mov     rcx, rdi; this
0x180012a85  call    ?AddErrorEvent@CImageIdEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEAU_EVENT_TRACE@@@Z; Microsoft::Windows::Performance::CImageIdEventTraceExtender::AddErrorEvent(_EVENT_TRACE *)
0x180012a8a  mov     ebx, 1
0x180012a8f  jmp     loc_18001357D
0x180012a94  mov     rax, [r15+10h]
0x180012a98  cmp     [rdi+28h], rax
0x180012a9c  jnz     short loc_180012AB8
0x180012a9e  mov     eax, [rsp+908h+var_828]
0x180012aa5  cmp     [rdi+30h], eax
0x180012aa8  jnz     short loc_180012AB8
0x180012aaa  mov     rax, [rsp+908h+var_820]
0x180012ab2  cmp     [rdi+38h], rax
0x180012ab6  jz      short loc_180012A8A
0x180012ab8  lea     r12, [rdi+0C0h]
0x180012abf  lea     rcx, [rdi+40h]
0x180012ac3  mov     r8, r12
0x180012ac6  mov     rbx, [rsp+908h+Str]
0x180012ace  mov     rdx, rbx
0x180012ad1  call    ?GetFileName@CLocalNtImagePathDecoder@NtImagePathDecoder@Performance@@QEAA_NPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; Performance::NtImagePathDecoder::CLocalNtImagePathDecoder::GetFileName(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180012ad6  test    al, al
0x180012ad8  jnz     loc_180012BA7
0x180012ade  mov     rcx, [rdi+0B8h]
0x180012ae5  test    rcx, rcx
0x180012ae8  jz      short loc_180012AFD
0x180012aea  mov     r8, r12
0x180012aed  mov     rdx, rbx
0x180012af0  call    ?GetFileName@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEBA_NPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::GetFileName(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180012af5  test    al, al
0x180012af7  jnz     loc_180012BA7
0x180012afd  test    rbx, rbx
0x180012b00  jz      short loc_180012B75
0x180012b02  mov     r14, rsi
0x180012b05  cmp     [rdi+0C9h], sil
0x180012b0c  jnz     short loc_180012B47
0x180012b0e  mov     edx, 5Ch ; '\'; Ch
0x180012b13  mov     rcx, rbx; Str
0x180012b16  call    cs:__imp_wcsrchr
0x180012b1d  nop     dword ptr [rax+rax+00h]
0x180012b22  test    rax, rax
0x180012b25  jz      short loc_180012B47
0x180012b27  sub     rax, rbx
0x180012b2a  sar     rax, 1
0x180012b2d  lea     rcx, [rax+1]
0x180012b31  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012b35  inc     rax
0x180012b38  cmp     [rbx+rax*2], si
0x180012b3c  jnz     short loc_180012B35
0x180012b3e  cmp     rcx, rax
0x180012b41  sbb     r14, r14
0x180012b44  and     r14, rcx
0x180012b47  lea     rcx, [rdi+178h]
0x180012b4e  mov     rax, [rcx]
0x180012b51  lea     r8, [rbx+r14*2]
0x180012b55  lea     rdx, aUnableToParseI; "Unable to parse image path: %s"
0x180012b5c  mov     rax, [rax]
0x180012b5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b64  test    al, al
0x180012b66  jz      short loc_180012B9D
0x180012b68  mov     rdx, r15; struct _EVENT_TRACE *
0x180012b6b  mov     rcx, rdi; this
0x180012b6e  call    ?AddErrorEvent@CImageIdEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEAU_EVENT_TRACE@@@Z; Microsoft::Windows::Performance::CImageIdEventTraceExtender::AddErrorEvent(_EVENT_TRACE *)
0x180012b73  jmp     short loc_180012B9D
0x180012b75  lea     rcx, [rdi+178h]
0x180012b7c  mov     rax, [rcx]
0x180012b7f  lea     rdx, aNullPathInImag; "NULL path in image path."
0x180012b86  mov     rax, [rax]
0x180012b89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b8e  test    al, al
0x180012b90  jz      short loc_180012B9D
0x180012b92  mov     rdx, r15; struct _EVENT_TRACE *
0x180012b95  mov     rcx, rdi; this
0x180012b98  call    ?AddErrorEvent@CImageIdEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEAU_EVENT_TRACE@@@Z; Microsoft::Windows::Performance::CImageIdEventTraceExtender::AddErrorEvent(_EVENT_TRACE *)
0x180012b9d  mov     eax, 1
0x180012ba2  jmp     loc_180013FA1
0x180012ba7  lea     r14, [rdi+0C9h]
0x180012bae  mov     [rsp+908h+var_800], r14
0x180012bb6  cmp     [r14], sil
0x180012bb9  jnz     short loc_180012C1F
0x180012bbb  mov     rbx, rsi
0x180012bbe  mov     edx, 5Ch ; '\'; Ch
0x180012bc3  mov     rcx, [r12]; Str
0x180012bc7  call    cs:__imp_wcsrchr
0x180012bce  nop     dword ptr [rax+rax+00h]
0x180012bd3  test    rax, rax
0x180012bd6  jz      short loc_180012BFC
0x180012bd8  mov     rcx, [r12]
0x180012bdc  sub     rax, rcx
0x180012bdf  sar     rax, 1
0x180012be2  lea     rdx, [rax+1]
0x180012be6  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012bea  inc     rax
0x180012bed  cmp     [rcx+rax*2], si
0x180012bf1  jnz     short loc_180012BEA
0x180012bf3  cmp     rdx, rax
0x180012bf6  sbb     rbx, rbx
0x180012bf9  and     rbx, rdx
0x180012bfc  lea     rcx, [rdi+178h]
0x180012c03  mov     rdx, [rcx]
0x180012c06  mov     rax, [r12]
0x180012c0a  lea     r8, [rax+rbx*2]
0x180012c0e  mov     rax, [rdx]
0x180012c11  lea     rdx, aSFailure; "%s failure: "
0x180012c18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c1d  jmp     short loc_180012C3F
0x180012c1f  lea     rcx, [rdi+178h]
0x180012c26  mov     rax, [rcx]
0x180012c29  mov     r9, rbx
0x180012c2c  mov     r8, [r12]
0x180012c30  lea     rdx, aSSFailure; "%s [%s] failure: "
0x180012c37  mov     rax, [rax]
0x180012c3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c3f  mov     [rsp+908h+var_7A0], r14
0x180012c47  xor     edx, edx; Val
0x180012c49  mov     r8d, 640h; Size
0x180012c4f  lea     rcx, [rsp+908h+var_6F8]; void *
0x180012c57  call    memset_0
0x180012c5c  cmp     r13d, 4
0x180012c60  jz      short loc_180012C76
0x180012c62  cmp     r13d, 8
0x180012c66  jnz     loc_180013E9A
0x180012c6c  lea     rax, [rsp+908h+var_6E0]
0x180012c74  jmp     short loc_180012C7E
0x180012c76  lea     rax, [rsp+908h+var_6E8]
0x180012c7e  mov     [rsp+908h+var_840], rax
0x180012c86  mov     [rsp+908h+var_874], esi
0x180012c8d  mov     [rsp+908h+var_850], rsi
0x180012c95  mov     [rsp+908h+var_848], rsi
0x180012c9d  mov     [rsp+908h+var_858], rsi
0x180012ca5  xorps   xmm0, xmm0
0x180012ca8  xor     ecx, ecx
0x180012caa  movups  [rsp+908h+var_7F8], xmm0
0x180012cb2  mov     [rsp+908h+var_7E8], rcx
0x180012cba  mov     [rsp+908h+var_877], sil
0x180012cc2  lea     rcx, [rdi+0D0h]; this
0x180012cc9  mov     [rsp+908h+Src], rcx
0x180012cd1  mov     [rsp+908h+var_8B0], rax; unsigned __int16 *
0x180012cd6  lea     rax, [rsp+908h+var_877]
0x180012cde  mov     [rsp+908h+var_8B8], rax; bool *
0x180012ce3  lea     rax, [rsp+908h+var_7F8]
0x180012ceb  mov     [rsp+908h+var_8C0], rax; struct EMBEDDED_PDB_INFORMATION *
0x180012cf0  lea     rax, [rsp+908h+var_824]
0x180012cf8  mov     [rsp+908h+var_8C8], rax; unsigned int *
0x180012cfd  lea     rax, [rsp+908h+var_814]
0x180012d05  mov     [rsp+908h+var_8D0], rax; unsigned int *
0x180012d0a  lea     rax, [rsp+908h+var_858]
0x180012d12  mov     [rsp+908h+var_8D8], rax; struct CODEVIEW_INFORMATION_1 **
0x180012d17  lea     rax, [rsp+908h+var_848]
0x180012d1f  mov     [rsp+908h+var_8E0], rax; unsigned int **
0x180012d24  lea     rax, [rsp+908h+var_850]
0x180012d2c  mov     [rsp+908h+var_8E8], rax; unsigned int
0x180012d31  lea     r9, [rsp+908h+var_874]; unsigned int *
0x180012d39  mov     r8d, [rsp+908h+var_818]; unsigned int
0x180012d41  mov     rdx, [r12]; unsigned __int16 *
0x180012d45  call    ?Find@CCvDDCache@Performance@Windows@Microsoft@@QEAAJPEBGKPEAKPEAPEBT_CVDD@@PEAPEBKPEAPEBUCODEVIEW_INFORMATION_1@@11AEAUEMBEDDED_PDB_INFORMATION@@AEA_NPEAGK@Z; Microsoft::Windows::Performance::CCvDDCache::Find(ushort const *,ulong,ulong *,_CVDD const * *,ulong const * *,CODEVIEW_INFORMATION_1 const * *,ulong *,ulong *,EMBEDDED_PDB_INFORMATION &,bool &,ushort *,ulong)
0x180012d4a  mov     r8d, eax
0x180012d4d  test    eax, eax
0x180012d4f  jns     loc_18001364C
0x180012d55  cmp     eax, 80070490h
0x180012d5a  jnz     loc_1800135EF
0x180012d60  mov     eax, [rdi+170h]
0x180012d66  mov     dword ptr [rsp+908h+Size], eax
0x180012d6d  mov     [rsp+908h+var_874], eax
0x180012d74  lea     rax, [rdi+158h]
0x180012d7b  mov     [rsp+908h+var_858], rax
0x180012d83  cmp     [rax], rsi
0x180012d86  jz      loc_180013E9A
0x180012d8c  lea     r13, [rdi+160h]
0x180012d93  mov     [rsp+908h+var_7D8], r13
0x180012d9b  cmp     [r13+0], rsi
0x180012d9f  jz      loc_180013E9A
0x180012da5  lea     rax, [rdi+168h]
0x180012dac  mov     [rsp+908h+var_848], rax
0x180012db4  cmp     [rax], rsi
0x180012db7  jz      loc_180013E9A
0x180012dbd  call    ?IsWin8AndUp@COSVersionInfo@Performance@@SA_NXZ; Performance::COSVersionInfo::IsWin8AndUp(void)
0x180012dc2  mov     [rsp+908h+var_878], al; struct XPerfCore::IErrorMessage *
0x180012dc9  movdqa  xmm0, cs:__xmm@0000000000000000ffffffffffffffff
0x180012dd1  movdqu  [rsp+908h+var_7D0], xmm0
0x180012dda  mov     [rsp+908h+var_7C0], rsi
0x180012de2  mov     [rsp+908h+var_7B8], rsi
0x180012dea  mov     rbx, [r12]
0x180012dee  mov     [rsp+908h+var_868], rbx
0x180012df6  mov     [rsp+908h+var_850], rbx
0x180012dfe  lea     r9, [rdi+178h]; struct XPerfCore::IErrorMessage *
0x180012e05  mov     r8b, al; bool
0x180012e08  mov     rdx, rbx; lpFileName
0x180012e0b  lea     rcx, [rsp+908h+var_7D0]; this
0x180012e13  call    ?MapExistingFileReadOnly2@CFileMapping@XPerfCore@@QEAAJPEBG_NPEAVIErrorMessage@2@@Z; XPerfCore::CFileMapping::MapExistingFileReadOnly2(ushort const *,bool,XPerfCore::IErrorMessage *)
0x180012e18  mov     r14d, eax
0x180012e1b  test    eax, eax
0x180012e1d  jns     loc_18001312B
0x180012e23  cmp     eax, 80070003h
0x180012e28  jnz     loc_180013126
0x180012e2e  movaps  xmm0, xmmword ptr cs:aSystemrootSyst; "\\SystemRoot\\System32\\DriverStore\\Fi"...
0x180012e35  movaps  xmmword ptr [rsp+908h+String2], xmm0
0x180012e3d  movaps  xmm1, xmmword ptr cs:aSystemrootSyst+10h; "oot\\System32\\DriverStore\\FileReposit"...
0x180012e44  movaps  [rsp+908h+var_A8], xmm1
0x180012e4c  movaps  xmm0, xmmword ptr cs:aSystemrootSyst+20h; "em32\\DriverStore\\FileRepository\\"
0x180012e53  movaps  [rsp+908h+var_98], xmm0
0x180012e5b  movaps  xmm1, xmmword ptr cs:aSystemrootSyst+30h; "verStore\\FileRepository\\"
0x180012e62  movaps  [rsp+908h+var_88], xmm1
0x180012e6a  movaps  xmm0, xmmword ptr cs:aSystemrootSyst+40h; "\\FileRepository\\"
0x180012e71  movaps  [rsp+908h+var_78], xmm0
0x180012e79  movaps  xmm1, xmmword ptr cs:aSystemrootSyst+50h; "ository\\"
0x180012e80  movaps  [rsp+908h+var_68], xmm1
0x180012e88  movzx   eax, word ptr cs:aSystemrootSyst+60h; ""
0x180012e8f  mov     [rsp+908h+var_58], ax
0x180012e97  mov     r8d, 30h ; '0'; MaxCount
0x180012e9d  lea     rdx, [rsp+908h+String2]; String2
0x180012ea5  mov     rcx, [rsp+908h+Str]; String1
0x180012ead  call    wcsncmp_0
0x180012eb2  test    eax, eax
0x180012eb4  jnz     loc_180013126
0x180012eba  lea     rdx, aGlobalrootDriv; "\\\\?\\GLOBALROOT\\DriverStores\\BSPDRI"...
0x180012ec1  lea     rcx, [rsp+908h+lpFileName]
0x180012ec9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180012ece  nop
0x180012ecf  mov     r9, [rsp+908h+Str]
0x180012ed7  add     r9, 60h ; '`'
0x180012edb  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180012edf  inc     rdx
0x180012ee2  cmp     [r9+rdx*2], si
0x180012ee7  jnz     short loc_180012EDF
0x180012ee9  mov     rcx, [rsp+908h+var_718]
0x180012ef1  mov     rax, [rsp+908h+var_710]
0x180012ef9  sub     rax, rcx
0x180012efc  cmp     rdx, rax
0x180012eff  ja      short loc_180012F4D
0x180012f01  lea     rdi, [rcx+rdx]
0x180012f05  mov     [rsp+908h+var_718], rdi
0x180012f0d  lea     rbx, [rsp+908h+lpFileName]
0x180012f15  cmp     [rsp+908h+var_710], 7
0x180012f1e  cmova   rbx, [rsp+908h+lpFileName]
0x180012f27  lea     r8, [rdx+rdx]; Size
0x180012f2b  lea     rcx, [rbx+rcx*2]; void *
0x180012f2f  mov     rdx, r9; Src
0x180012f32  call    memmove_0
0x180012f37  mov     [rbx+rdi*2], si
0x180012f3b  mov     rdi, [rsp+908h+var_7E0]
0x180012f43  mov     rbx, [rsp+908h+var_868]
0x180012f4b  jmp     short loc_180012F5F
0x180012f4d  mov     [rsp+908h+var_8E8], rdx; __int64
0x180012f52  lea     rcx, [rsp+908h+lpFileName]; Src
0x180012f5a  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x180012f5f  lea     r14, [rdi+178h]
0x180012f66  mov     rax, [r14]
0x180012f69  lea     r8, [rsp+908h+lpFileName]
0x180012f71  cmp     [rsp+908h+var_710], 7
0x180012f7a  cmova   r8, [rsp+908h+lpFileName]
0x180012f83  lea     rdx, aOsBugWorkaroun; "OS bug workaround - trying alternate pa"...
0x180012f8a  mov     rcx, r14
0x180012f8d  mov     rax, [rax+8]
0x180012f91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f96  lea     rdx, [rsp+908h+lpFileName]
0x180012f9e  cmp     [rsp+908h+var_710], 7
0x180012fa7  cmova   rdx, [rsp+908h+lpFileName]; lpFileName
0x180012fb0  mov     r9, r14; struct XPerfCore::IErrorMessage *
0x180012fb3  mov     r8b, [rsp+908h+var_878]; bool
0x180012fbb  lea     rcx, [rsp+908h+var_7D0]; this
  ... truncated ...
```
