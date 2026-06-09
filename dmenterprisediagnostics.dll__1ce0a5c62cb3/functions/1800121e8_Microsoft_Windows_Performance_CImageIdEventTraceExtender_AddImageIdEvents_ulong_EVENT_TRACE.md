# Microsoft::Windows::Performance::CImageIdEventTraceExtender::AddImageIdEvents(ulong,_EVENT_TRACE *)

- ea: `0x1800121e8`
- end: `0x1800137dd`
- name: `?AddImageIdEvents@CImageIdEventTraceExtender@Performance@Windows@Microsoft@@AEAAJKPEAU_EVENT_TRACE@@@Z`
- size: `5621`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CImageIdEventTraceExtender *__hidden this, struct _EVENT_TRACE *, struct _EVENT_TRACE *)`
- caller_count: `1`
- callee_count: `32`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x180015fe0`

## callees

- `0x1800017e0`
- `0x180001804`
- `0x1800023c0`
- `0x1800029b5`
- `0x1800029c1`
- `0x180003604`
- `0x180003714`
- `0x180003b10`
- `0x18000958c`
- `0x18000977c`
- `0x18000c3b0`
- `0x180011bfc`
- `0x180011e38`
- `0x180011e80`
- `0x180011fec`
- `0x1800121e8`
- `0x180013a4c`
- `0x180013ca4`
- `0x180013e6c`
- `0x180014340`
- `0x1800145ec`
- `0x180014644`
- `0x18001468c`
- `0x180015350`
- `0x18001539c`
- `0x180016cfc`
- `0x18001753c`
- `0x1800180ac`
- `0x180022b0c`
- `0x180022c08`
- `0x1800243d0`
- `0x180026010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x1800130ee`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x1800130ee`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180012332`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800123dd`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180012332`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800123dd`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180013525`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180013525`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180012847`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180012847`

## string_xrefs

- `0x18001236b`: `Unable to parse image path: %s`
- `0x180012395`: `NULL path in image path.`
- `0x180012656`: `\SystemRoot\System32\DriverStore\FileRepository\`
- `0x1800126e2`: `\\?\GLOBALROOT\DriverStores\BSPDRIVERS\System32\DriverStore\FileRepository\`
- `0x1800127ab`: `OS bug workaround - trying alternate path: %s`
- `0x1800134d7`: `CreateEmbeddedPdb failed 0x%x. %s ({%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}) age: %d`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CImageIdEventTraceExtender::AddImageIdEvents(
        Microsoft::Windows::Performance::CImageIdEventTraceExtender *this,
        struct _EVENT_TRACE *a2,
        struct _EVENT_TRACE *a3)
{
  int v4; // r14d
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
  __int64 v21; // r13
  unsigned __int64 v22; // rax
  unsigned __int16 *v23; // rax
  int v24; // eax
  int v25; // r8d
  union _CVDD **v26; // r13
  wchar_t *v27; // rbx
  signed int Only2; // eax
  union _CVDD *v29; // r9
  int v30; // r14d
  unsigned __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // rdi
  LPCWSTR *v34; // rbx
  LPCWSTR *v35; // r8
  const WCHAR *v36; // rdx
  int v37; // eax
  void **v38; // r12
  unsigned __int16 *v39; // rdx
  LPCWSTR *v40; // rdx
  Microsoft::Windows::Performance::CImageIdEventTraceExtender *v41; // rcx
  unsigned int v42; // ecx
  int v43; // eax
  struct CODEVIEW_INFORMATION_1 **v44; // r14
  unsigned __int16 *v45; // rdx
  struct CODEVIEW_INFORMATION_1 *v46; // r8
  unsigned int v47; // r12d
  unsigned int v48; // r14d
  int v49; // eax
  const union _CVDD *v50; // rdx
  union _CVDD *v51; // rcx
  const struct CODEVIEW_INFORMATION_1 *v52; // r8
  unsigned int v53; // r13d
  int v54; // r9d
  Microsoft::Windows::Performance::CImageIdEventTraceExtender *v55; // r14
  unsigned int v56; // r14d
  int v57; // ecx
  int v58; // esp
  _DWORD *v59; // r13
  unsigned int v60; // eax
  unsigned int v61; // r12d
  __int64 v62; // rcx
  unsigned int v63; // eax
  _DWORD *v64; // rdx
  char v65; // al
  unsigned __int64 v66; // rax
  int v67; // eax
  int v68; // ecx
  unsigned int v69; // ecx
  int v70; // eax
  int EmbeddedPdb; // eax
  Microsoft::Windows::Performance::CImageIdEventTraceExtender *v72; // rbx
  int v73; // edx
  unsigned int *p_pguid; // rcx
  int v75; // r12d
  int v76; // eax
  int v77; // eax
  unsigned int v78; // [rsp+20h] [rbp-8E8h]
  unsigned int v79; // [rsp+20h] [rbp-8E8h]
  unsigned int v80; // [rsp+20h] [rbp-8E8h]
  union _CVDD **v81; // [rsp+20h] [rbp-8E8h]
  unsigned int **v82; // [rsp+28h] [rbp-8E0h]
  struct CODEVIEW_INFORMATION_1 **v83; // [rsp+30h] [rbp-8D8h]
  struct CODEVIEW_INFORMATION_1 **v84; // [rsp+30h] [rbp-8D8h]
  union _CVDD *v85; // [rsp+38h] [rbp-8D0h]
  struct CODEVIEW_INFORMATION_1 *v86; // [rsp+40h] [rbp-8C8h]
  struct CODEVIEW_INFORMATION_1 *v87; // [rsp+48h] [rbp-8C0h]
  bool *v88; // [rsp+50h] [rbp-8B8h]
  unsigned int *v89; // [rsp+58h] [rbp-8B0h]
  unsigned int v90; // [rsp+60h] [rbp-8A8h]
  bool *v91; // [rsp+60h] [rbp-8A8h]
  bool *v92; // [rsp+60h] [rbp-8A8h]
  unsigned int v93[2]; // [rsp+68h] [rbp-8A0h]
  __int64 MappedAsImage; // [rsp+70h] [rbp-898h]
  struct EMBEDDED_PDB_INFORMATION *v95; // [rsp+78h] [rbp-890h]
  struct XPerfCore::IErrorMessage *v96; // [rsp+90h] [rbp-878h] BYREF
  size_t Size; // [rsp+98h] [rbp-870h]
  Microsoft::Windows::Performance::CImageIdEventTraceExtender *v98; // [rsp+A0h] [rbp-868h] BYREF
  unsigned int v99; // [rsp+A8h] [rbp-860h] BYREF
  int v100; // [rsp+ACh] [rbp-85Ch]
  struct CODEVIEW_INFORMATION_1 *v101; // [rsp+B0h] [rbp-858h] BYREF
  union _CVDD *v102; // [rsp+B8h] [rbp-850h] BYREF
  unsigned __int16 *v103; // [rsp+C0h] [rbp-848h] BYREF
  unsigned int *v104; // [rsp+C8h] [rbp-840h]
  void *Src; // [rsp+D0h] [rbp-838h]
  unsigned int v106; // [rsp+D8h] [rbp-830h]
  __int64 v107; // [rsp+E0h] [rbp-828h] BYREF
  unsigned __int64 v108; // [rsp+E8h] [rbp-820h]
  __int64 v109; // [rsp+F0h] [rbp-818h] BYREF
  wchar_t *Str; // [rsp+F8h] [rbp-810h]
  union _CVDD *v111; // [rsp+108h] [rbp-800h]
  __int128 v112; // [rsp+110h] [rbp-7F8h] BYREF
  __int64 v113; // [rsp+120h] [rbp-7E8h]
  Microsoft::Windows::Performance::CImageIdEventTraceExtender *v114; // [rsp+128h] [rbp-7E0h]
  char *v115; // [rsp+130h] [rbp-7D8h]
  HANDLE hFile[2]; // [rsp+138h] [rbp-7D0h] BYREF
  unsigned __int16 *v117; // [rsp+148h] [rbp-7C0h]
  void *v118; // [rsp+150h] [rbp-7B8h]
  struct _EVENT_TRACE *v119; // [rsp+158h] [rbp-7B0h]
  Microsoft::Windows::Performance::CImageIdEventTraceExtender *v120; // [rsp+160h] [rbp-7A8h]
  union _CVDD *v121; // [rsp+168h] [rbp-7A0h]
  ATL::CAtlException *v122; // [rsp+170h] [rbp-798h] BYREF
  __int128 v123; // [rsp+180h] [rbp-788h] BYREF
  __m256i v124; // [rsp+190h] [rbp-778h]
  __int128 v125; // [rsp+1B0h] [rbp-758h]
  __int128 v126; // [rsp+1C0h] [rbp-748h]
  int v127; // [rsp+1D0h] [rbp-738h]
  int v128; // [rsp+1D4h] [rbp-734h]
  LPCWSTR lpFileName[2]; // [rsp+1E0h] [rbp-728h] BYREF
  __int64 v130; // [rsp+1F0h] [rbp-718h]
  unsigned __int64 v131; // [rsp+1F8h] [rbp-710h]
  GUID pguid; // [rsp+200h] [rbp-708h] BYREF
  unsigned __int64 v133; // [rsp+210h] [rbp-6F8h] BYREF
  unsigned __int64 v134; // [rsp+218h] [rbp-6F0h] BYREF
  unsigned int v135; // [rsp+220h] [rbp-6E8h] BYREF
  unsigned int v136; // [rsp+224h] [rbp-6E4h]
  unsigned __int16 v137[4]; // [rsp+228h] [rbp-6E0h] BYREF
  int v138; // [rsp+230h] [rbp-6D8h]
  wchar_t String2[56]; // [rsp+850h] [rbp-B8h] BYREF

  v119 = a3;
  v4 = (int)a2;
  v100 = (int)a2;
  v5 = this;
  v114 = this;
  v120 = this;
  v106 = (unsigned int)a2;
  *(_QWORD *)&pguid.Data1 = a3;
  v6 = 0;
  v107 = 0;
  v108 = 0;
  v109 = 0;
  Str = 0;
  if ( (int)Microsoft::Windows::Performance::ParseImageEvent(
              (Microsoft::Windows::Performance *)&v107,
              (struct Microsoft::Windows::Performance::CImageData *)a3,
              (const struct _EVENT_TRACE *)(unsigned int)a2,
              *((_DWORD *)this + 8),
              v78) < 0 )
  {
    if ( (**((unsigned __int8 (__fastcall ***)(char *, const wchar_t *))v5 + 47))(
           (char *)v5 + 376,
           L"Failed to parse image event.") )
    {
      Microsoft::Windows::Performance::CImageIdEventTraceExtender::AddErrorEvent(v5, a3);
    }
    return 1;
  }
  TimeStamp = a3->Header.TimeStamp;
  if ( *((_QWORD *)v5 + 5) == TimeStamp.QuadPart && *((_DWORD *)v5 + 12) == (_DWORD)v107 && *((_QWORD *)v5 + 7) == v108 )
    return 1;
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v9 = (const wchar_t **)((char *)v5 + 192);
    v10 = Str;
    FileName = Performance::NtImagePathDecoder::CLocalNtImagePathDecoder::GetFileName(
                 (char *)v5 + 64,
                 Str,
                 (char *)v5 + 192);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      result = 2147942414LL;
      __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_1800137AD);
      return result;
    }
    if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', &v122) )
    {
      if ( *(_DWORD *)v122 == -2147024882 )
      {
        result = 2147942414LL;
        __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_1800137AD);
      }
      else
      {
        *((_BYTE *)v120 + 200) = 1;
        result = 1;
        __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_1800137B4);
      }
      return result;
    }
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
        if ( !(**((unsigned __int8 (***)(char *, const wchar_t *, ...))v5 + 47))(
                (char *)v5 + 376,
                L"Unable to parse image path: %s",
                &v10[v13]) )
          return 1;
      }
      else if ( !(**((unsigned __int8 (__fastcall ***)(char *, const wchar_t *))v5 + 47))(
                   (char *)v5 + 376,
                   L"NULL path in image path.") )
      {
        return 1;
      }
      Microsoft::Windows::Performance::CImageIdEventTraceExtender::AddErrorEvent(v5, a3);
      return 1;
    }
  }
  if ( __eh34_try(-1, 2) )
  {
    __eh34_scope_strut(2);
    v111 = (Microsoft::Windows::Performance::CImageIdEventTraceExtender *)((char *)v5 + 201);
    if ( *((_BYTE *)v5 + 201) )
    {
      (**((void (***)(char *, const wchar_t *, ...))v5 + 47))((char *)v5 + 376, L"%s [%s] failure: ", *v9, v10);
      v21 = -1;
    }
    else
    {
      v18 = 0;
      v19 = wcsrchr(*v9, 0x5Cu);
      if ( v19 )
      {
        v20 = v19 - *v9 + 1;
        v21 = -1;
        v22 = -1;
        do
          ++v22;
        while ( (*v9)[v22] );
        v18 = v20 & -(__int64)(v20 < v22);
      }
      else
      {
        v21 = -1;
      }
      (**((void (***)(char *, const wchar_t *, ...))v5 + 47))((char *)v5 + 376, L"%s failure: ", &(*v9)[v18]);
    }
    v121 = v111;
  }
  if ( __eh34_catch(2) )
  {
    if ( __eh34_catch_type(2, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      result = 2147942414LL;
      __eh34_try_continuation(2, &std::bad_alloc `RTTI Type Descriptor', &loc_1800137AD);
      return result;
    }
  }
  memset_0(&v133, 0, 0x640u);
  if ( v4 == 4 )
  {
    v23 = (unsigned __int16 *)&v135;
  }
  else
  {
    if ( v4 != 8 )
      return 2147549183LL;
    v23 = v137;
  }
  v104 = (unsigned int *)v23;
  HIDWORD(v96) = 0;
  v102 = 0;
  v103 = 0;
  v101 = 0;
  v112 = 0;
  v113 = 0;
  BYTE1(v96) = 0;
  Src = (char *)v5 + 208;
  v24 = Microsoft::Windows::Performance::CCvDDCache::Find(
          (Microsoft::Windows::Performance::CImageIdEventTraceExtender *)((char *)v5 + 208),
          *v9,
          v109,
          (unsigned int *)&v96 + 1,
          &v102,
          (const unsigned int **)&v103,
          &v101,
          (unsigned int *)&v109 + 1,
          (unsigned int *)&v107 + 1,
          (struct EMBEDDED_PDB_INFORMATION *)&v112,
          (bool *)&v96 + 1,
          v23,
          v90);
  v25 = v24;
  if ( v24 >= 0 )
  {
    v7 = 1;
    v47 = HIDWORD(v109);
    v56 = v107;
    LODWORD(Size) = HIDWORD(v96);
    v111 = v102;
    v102 = (union _CVDD *)v103;
    v103 = (unsigned __int16 *)v101;
LABEL_109:
    if ( v100 == 4 )
    {
      v57 = v108;
      v133 = __PAIR64__(HIDWORD(v107), v108);
      v134 = __PAIR64__(v47, v56);
    }
    else
    {
      if ( v100 != 8 )
        return 2147549183LL;
      v57 = v108;
      v133 = v108;
      v134 = HIDWORD(v107);
      v135 = v56;
      v136 = v47;
    }
    HIDWORD(v96) = v57;
    do
      ++v21;
    while ( *((_WORD *)v104 + v21) );
    v123 = *(_OWORD *)&a3->Header.Size;
    v124 = *(__m256i *)&a3->Header.TimeStamp.LowPart;
    v125 = *(_OWORD *)&a3->InstanceId;
    v126 = *(_OWORD *)a3->ParentGuid.Data4;
    v128 = HIDWORD(*(_QWORD *)&a3->MofLength);
    *(struct _GUID *)&v124.m256i_u64[1] = ImageIdGuid;
    DWORD1(v123) = 0x20000;
    HIDWORD(v123) = v56;
    *((_QWORD *)&v126 + 1) = &v133;
    v127 = (_DWORD)v104 + 2 * v21 + 2 - (v58 + 528);
    result = (*(__int64 (__fastcall **)(_QWORD, __int128 *, _QWORD, _QWORD))(**((_QWORD **)v5 + 2) + 192LL))(
               *((_QWORD *)v5 + 2),
               &v123,
               0,
               0);
    if ( (int)result < 0 )
      return result;
    v59 = 0;
    v104 = 0;
    v60 = 0;
    LODWORD(v98) = 0;
    v61 = Size;
    while ( v60 < v61 )
    {
      v62 = v60;
      v63 = *((_DWORD *)v102 + v60);
      LODWORD(Size) = v63;
      if ( v63 >= 4 )
      {
        if ( v63 > 0x628 )
          return 2147549183LL;
        v64 = (_DWORD *)((char *)v111 + 1576 * v62);
        Src = v64;
        if ( *v64 )
        {
          switch ( *v64 )
          {
            case 1:
              v65 = 33;
              break;
            case 2:
              v65 = 34;
              break;
            case 3:
              v65 = 37;
              break;
            case 0x3031424E:
              v65 = 35;
              break;
            case 0x53445352:
              v65 = 36;
              break;
            default:
              return v7;
          }
        }
        else
        {
          v65 = 32;
        }
        LOBYTE(v96) = v65;
        if ( (_DWORD)v112 )
        {
          if ( v65 == 36 )
          {
            v66 = -1;
            do
              ++v66;
            while ( *((_BYTE *)v64 + v66 + 24) );
            if ( v66 <= 7 || (v67 = _o__stricmp((char *)v64 + v66 + 17, ".ni.pdb"), v64 = Src, v67) )
            {
              v59 = v64;
              v104 = v64;
            }
          }
        }
        if ( v100 == 4 )
        {
          memcpy_0((char *)&v133 + 4, v64, (unsigned int)Size);
          v133 = __PAIR64__(v56, HIDWORD(v96));
          v68 = Size + 4;
        }
        else
        {
          if ( v100 != 8 )
            return 2147549183LL;
          memcpy_0(&v134, v64, (unsigned int)Size);
          v133 = v108;
          LODWORD(v134) = v56;
          v68 = Size + 8;
        }
        v123 = *(_OWORD *)&a3->Header.Size;
        v124 = *(__m256i *)&a3->Header.TimeStamp.LowPart;
        v125 = *(_OWORD *)&a3->InstanceId;
        v126 = *(_OWORD *)a3->ParentGuid.Data4;
        v128 = HIDWORD(*(_QWORD *)&a3->MofLength);
        *(struct _GUID *)&v124.m256i_u64[1] = ImageIdGuid;
        DWORD1(v123) = (unsigned __int8)v96 | 0x20000;
        HIDWORD(v123) = v56;
        *((_QWORD *)&v126 + 1) = &v133;
        v127 = v68;
        result = (*(__int64 (__fastcall **)(_QWORD, __int128 *, _QWORD, _QWORD))(**((_QWORD **)v5 + 2) + 192LL))(
                   *((_QWORD *)v5 + 2),
                   &v123,
                   0,
                   0);
        if ( (int)result < 0 )
          return result;
      }
      v60 = (_DWORD)v98 + 1;
      LODWORD(v98) = v60;
    }
    v69 = 0;
    LODWORD(v98) = 0;
    if ( v61 )
    {
      v70 = v100;
      do
      {
        if ( v70 == 4 )
        {
          v133 = __PAIR64__(v56, HIDWORD(v96));
        }
        else
        {
          if ( v70 != 8 )
            return 2147549183LL;
          v133 = v108;
          LODWORD(v134) = v56;
        }
        if ( *(_DWORD *)&v103[4 * v69] )
        {
          HIDWORD(v134) = *(_DWORD *)&v103[4 * v69];
          v135 = *(_DWORD *)&v103[4 * v69 + 2];
          *(_OWORD *)String2 = *(_OWORD *)&a3->Header.Size;
          *(_OWORD *)&String2[8] = *(_OWORD *)&a3->Header.TimeStamp.LowPart;
          *(union _EVENT_TRACE_HEADER::$146F82FB58FCEC23F5D30A6BD72C4E4F *)&String2[16] = *(union _EVENT_TRACE_HEADER::$146F82FB58FCEC23F5D30A6BD72C4E4F *)((char *)&a3->Header.24 + 8);
          *(_OWORD *)&String2[24] = *(_OWORD *)&a3->InstanceId;
          *(_OWORD *)&String2[32] = *(_OWORD *)a3->ParentGuid.Data4;
          *(_DWORD *)&String2[42] = HIDWORD(*(_QWORD *)&a3->MofLength);
          *(struct _GUID *)&String2[12] = ImageIdGuid;
          *(_DWORD *)&String2[2] = 131110;
          *(_DWORD *)&String2[6] = v56;
          *(_QWORD *)&String2[36] = &v133;
          *(_DWORD *)&String2[40] = 20;
          result = (*(__int64 (__fastcall **)(_QWORD, wchar_t *, _QWORD, _QWORD))(**((_QWORD **)v5 + 2) + 192LL))(
                     *((_QWORD *)v5 + 2),
                     String2,
                     0,
                     0);
          if ( (int)result < 0 )
            return result;
          v70 = v100;
          v69 = (unsigned int)v98;
        }
        LODWORD(v98) = ++v69;
      }
      while ( v69 < v61 );
    }
    if ( !(_DWORD)v112 )
    {
      v75 = v100;
      goto LABEL_169;
    }
    pguid = 0;
    if ( v59 )
    {
      if ( __eh34_try(-1, 6) )
      {
        __eh34_scope_strut(6);
        Src = v59 + 1;
        v115 = (char *)(v59 + 6);
        EmbeddedPdb = Microsoft::Windows::Performance::CImageIdEventTraceExtender::CreateEmbeddedPdb(
                        v5,
                        (const char *)v59 + 24,
                        (const struct _GUID *)(v59 + 1),
                        v59[5],
                        (DWORD *)&v112);
      }
      if ( __eh34_catch(6) )
      {
        if ( __eh34_catch_type(6, &std::bad_alloc `RTTI Type Descriptor', 0) )
        {
          result = 2147942414LL;
          __eh34_try_continuation(6, &std::bad_alloc `RTTI Type Descriptor', &loc_1800137AD);
          return result;
        }
      }
      v106 = EmbeddedPdb;
      if ( EmbeddedPdb < 0 )
      {
        LODWORD(v95) = v104[5];
        LODWORD(MappedAsImage) = *((unsigned __int8 *)v59 + 19);
        v93[0] = *((unsigned __int8 *)v59 + 18);
        LODWORD(v91) = *((unsigned __int8 *)v59 + 17);
        LODWORD(v89) = *((unsigned __int8 *)v59 + 16);
        LODWORD(v88) = *((unsigned __int8 *)v59 + 15);
        LODWORD(v87) = *((unsigned __int8 *)v59 + 14);
        LODWORD(v86) = *((unsigned __int8 *)v59 + 13);
        LODWORD(v85) = *((unsigned __int8 *)v59 + 12);
        LODWORD(v83) = *((unsigned __int16 *)v59 + 5);
        LODWORD(v82) = *((unsigned __int16 *)v59 + 4);
        LODWORD(v81) = *(_DWORD *)Src;
        v72 = v114;
        (**((void (***)(char *, const wchar_t *, ...))v5 + 47))(
          (char *)v114 + 376,
          L"CreateEmbeddedPdb failed 0x%x. %s ({%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}) age: %d",
          v106,
          v115,
          v81,
          v82,
          v83,
          v85,
          v86,
          v87,
          v88,
          v89,
          v91,
          *(_QWORD *)v93,
          MappedAsImage,
          v95);
        Microsoft::Windows::Performance::CImageIdEventTraceExtender::AddErrorEvent(v72, v119);
        return 1;
      }
      v73 = v59[5];
      p_pguid = (unsigned int *)Src;
    }
    else
    {
      if ( CoCreateGuid(&pguid) < 0 )
        return v7;
      v73 = 1;
      p_pguid = (unsigned int *)&pguid;
    }
    v75 = v100;
    if ( v100 == 4 )
    {
      v133 = __PAIR64__(v56, HIDWORD(v96));
LABEL_166:
      HIDWORD(v134) = v113;
      v135 = *p_pguid;
      v136 = p_pguid[1];
      *(_QWORD *)v137 = *((_QWORD *)p_pguid + 1);
      v138 = v73;
      *(_OWORD *)String2 = *(_OWORD *)&a3->Header.Size;
      *(_OWORD *)&String2[8] = *(_OWORD *)&a3->Header.TimeStamp.LowPart;
      *(union _EVENT_TRACE_HEADER::$146F82FB58FCEC23F5D30A6BD72C4E4F *)&String2[16] = *(union _EVENT_TRACE_HEADER::$146F82FB58FCEC23F5D30A6BD72C4E4F *)((char *)&a3->Header.24 + 8);
      *(_OWORD *)&String2[24] = *(_OWORD *)&a3->InstanceId;
      *(_OWORD *)&String2[32] = *(_OWORD *)a3->ParentGuid.Data4;
      *(_DWORD *)&String2[42] = HIDWORD(*(_QWORD *)&a3->MofLength);
      *(struct _GUID *)&String2[12] = ImageIdGuid;
      *(_DWORD *)&String2[2] = 65575;
      *(_DWORD *)&String2[6] = v56;
      *(_QWORD *)&String2[36] = &v133;
      wcscpy(&String2[40], L"$");
      result = (*(__int64 (__fastcall **)(_QWORD, wchar_t *, _QWORD, _QWORD))(**((_QWORD **)v5 + 2) + 192LL))(
                 *((_QWORD *)v5 + 2),
                 String2,
                 0,
                 0);
      if ( (int)result < 0 )
        return result;
LABEL_169:
      if ( !BYTE1(v96) )
        return 0;
      if ( v75 == 4 )
      {
        v133 = __PAIR64__(v56, HIDWORD(v96));
        v76 = 8;
      }
      else
      {
        if ( v75 != 8 )
          return 2147549183LL;
        v133 = v108;
        LODWORD(v134) = v56;
        v76 = 12;
      }
      *(_OWORD *)String2 = *(_OWORD *)&a3->Header.Size;
      *(_OWORD *)&String2[8] = *(_OWORD *)&a3->Header.TimeStamp.LowPart;
      *(union _EVENT_TRACE_HEADER::$146F82FB58FCEC23F5D30A6BD72C4E4F *)&String2[16] = *(union _EVENT_TRACE_HEADER::$146F82FB58FCEC23F5D30A6BD72C4E4F *)((char *)&a3->Header.24 + 8);
      *(_OWORD *)&String2[24] = *(_OWORD *)&a3->InstanceId;
      *(_OWORD *)&String2[32] = *(_OWORD *)a3->ParentGuid.Data4;
      *(_DWORD *)&String2[42] = HIDWORD(*(_QWORD *)&a3->MofLength);
      *(struct _GUID *)&String2[12] = ImageIdGuid;
      *(_DWORD *)&String2[2] = 65576;
      *(_DWORD *)&String2[6] = v56;
      *(_QWORD *)&String2[36] = &v133;
      *(_DWORD *)&String2[40] = v76;
      v77 = (*(__int64 (__fastcall **)(_QWORD, wchar_t *, _QWORD, _QWORD))(**((_QWORD **)v5 + 2) + 192LL))(
              *((_QWORD *)v5 + 2),
              String2,
              0,
              0);
      if ( v77 < 0 )
        return (unsigned int)v77;
      return v6;
    }
    if ( v100 == 8 )
    {
      v133 = v108;
      LODWORD(v134) = v56;
      goto LABEL_166;
    }
    return 2147549183LL;
  }
  if ( v24 == -2147023728 )
  {
    LODWORD(Size) = *((_DWORD *)v5 + 92);
    HIDWORD(v96) = Size;
    v101 = (Microsoft::Windows::Performance::CImageIdEventTraceExtender *)((char *)v5 + 344);
    if ( !*((_QWORD *)v5 + 43) )
      return 2147549183LL;
    v26 = (union _CVDD **)((char *)v5 + 352);
    v115 = (char *)v5 + 352;
    if ( !*((_QWORD *)v5 + 44) )
      return 2147549183LL;
    v103 = (unsigned __int16 *)((char *)v5 + 360);
    if ( !*((_QWORD *)v5 + 45) )
      return 2147549183LL;
    LOBYTE(v96) = Performance::COSVersionInfo::IsWin8AndUp();
    *(__m128i *)hFile = _mm_load_si128((const __m128i *)&_xmm);
    v117 = 0;
    v118 = 0;
    v27 = (wchar_t *)*v9;
    v98 = (Microsoft::Windows::Performance::CImageIdEventTraceExtender *)v27;
    v102 = (union _CVDD *)v27;
    Only2 = XPerfCore::CFileMapping::MapExistingFileReadOnly2(
              (XPerfCore::CFileMapping *)hFile,
              v27,
              (char)v96,
              (Microsoft::Windows::Performance::CImageIdEventTraceExtender *)((char *)v5 + 376));
    v30 = Only2;
    if ( Only2 >= 0 )
      goto LABEL_70;
    if ( Only2 != -2147024893
      || (wcscpy(String2, L"\\SystemRoot\\System32\\DriverStore\\FileRepository\\"), wcsncmp_0(Str, String2, 0x30u)) )
    {
      v41 = (Microsoft::Windows::Performance::CImageIdEventTraceExtender *)v27;
      v38 = (void **)v101;
LABEL_80:
      if ( !*((_BYTE *)v5 + 202) )
      {
        v7 = 1;
        v47 = HIDWORD(v109);
        goto LABEL_88;
      }
      if ( *v38 )
      {
        if ( *v26 )
        {
          v45 = v103;
          v46 = *(struct CODEVIEW_INFORMATION_1 **)v103;
          if ( *(_QWORD *)v103 )
          {
            v7 = 1;
            LODWORD(Size) = 1;
            v47 = HIDWORD(v109);
            *(_DWORD *)v46 = HIDWORD(v109);
            *(_WORD *)(*(_QWORD *)v45 + 4LL) = 0;
            *(_WORD *)(*(_QWORD *)v45 + 6LL) = 0;
            v30 = Microsoft::Xbox::CvDbgInfoFromVBI(
                    v41,
                    v45,
                    *(struct Microsoft::Windows::Performance::CErrorEvent **)v101,
                    v29);
            *(_DWORD *)*v26 = 1576;
LABEL_88:
            if ( v30 < 0 )
            {
              Microsoft::Windows::Performance::CImageIdEventTraceExtender::AddErrorEvent(v5, a3);
              Microsoft::Windows::Performance::CCvDDCache::AddFailure(
                (Microsoft::Windows::Performance::CCvDDCache *)Src,
                (const unsigned __int16 *)v98,
                v109);
              goto LABEL_98;
            }
            v48 = Size;
            goto LABEL_92;
          }
        }
      }
      v7 = -2147418113;
LABEL_98:
      XPerfCore::CFileMapping::Cleanup((XPerfCore::CFileMapping *)hFile);
      return v7;
    }
    std::wstring::wstring(
      (__int64)lpFileName,
      (__int64)L"\\\\?\\GLOBALROOT\\DriverStores\\BSPDRIVERS\\System32\\DriverStore\\FileRepository\\");
    v31 = -1;
    do
      ++v31;
    while ( Str[v31 + 48] );
    v32 = v130;
    if ( v31 > v131 - v130 )
    {
      std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
        lpFileName,
        v31);
    }
    else
    {
      v33 = v130 + v31;
      v130 += v31;
      v34 = lpFileName;
      if ( v131 > 7 )
        v34 = (LPCWSTR *)lpFileName[0];
      memmove_0((char *)v34 + 2 * v32, Str + 48, 2 * v31);
      *((_WORD *)v34 + v33) = 0;
      v5 = v114;
      v27 = (wchar_t *)v98;
    }
    v35 = lpFileName;
    if ( v131 > 7 )
      v35 = (LPCWSTR *)lpFileName[0];
    (*(void (**)(char *, const wchar_t *, ...))(*((_QWORD *)v5 + 47) + 8LL))(
      (char *)v5 + 376,
      L"OS bug workaround - trying alternate path: %s",
      v35);
    v36 = (const WCHAR *)lpFileName;
    if ( v131 > 7 )
      v36 = lpFileName[0];
    v30 = XPerfCore::CFileMapping::MapExistingFileReadOnly2(
            (XPerfCore::CFileMapping *)hFile,
            v36,
            (char)v96,
            (Microsoft::Windows::Performance::CImageIdEventTraceExtender *)((char *)v5 + 376));
    if ( v30 >= 0 )
    {
      if ( hFile[0] == (HANDLE)-1LL )
      {
        LOWORD(v37) = 87;
LABEL_58:
        v30 = (unsigned __int16)v37 | 0x80070000;
        goto LABEL_59;
      }
      LODWORD(v98) = GetFinalPathNameByHandleW(hFile[0], 0, 0, 0);
      std::wstring::reserve(lpFileName);
      v39 = (unsigned __int16 *)lpFileName;
      if ( v131 > 7 )
        v39 = (unsigned __int16 *)lpFileName[0];
      v37 = XPerfCore::CFileMapping::GetFileName((XPerfCore::CFileMapping *)hFile, v39, (unsigned int *)&v98);
      if ( v37 )
      {
        if ( v37 > 0 )
          goto LABEL_58;
        v30 = v37;
      }
      else
      {
        v40 = lpFileName;
        if ( v131 > 7 )
          v40 = (LPCWSTR *)lpFileName[0];
        ATL::CSimpleStringT<unsigned short,0>::SetString(v9, v40);
        v27 = (wchar_t *)*v9;
        v102 = (union _CVDD *)*v9;
      }
    }
LABEL_59:
    v98 = (Microsoft::Windows::Performance::CImageIdEventTraceExtender *)v27;
    std::wstring::~wstring((__int64)lpFileName);
    if ( v30 < 0 )
    {
      v38 = (void **)v101;
LABEL_79:
      v41 = v98;
      goto LABEL_80;
    }
LABEL_70:
    v42 = (unsigned int)v118;
    v102 = (union _CVDD *)v118;
    if ( (unsigned __int64)v118 >= 0xFFFFFFFF )
    {
      v42 = -1;
      v102 = (union _CVDD *)0xFFFFFFFFLL;
    }
    LODWORD(v91) = 780;
    v38 = (void **)v101;
    v43 = ((__int64 (__fastcall *)(XPerf::Internal *, const unsigned __int16 *, void *, unsigned int, unsigned int, unsigned int *, union _CVDD *, union _CVDD *, struct CODEVIEW_INFORMATION_1 *, struct CODEVIEW_INFORMATION_1 *, unsigned int *, unsigned int *, unsigned __int16 *, unsigned int, BOOLEAN, struct EMBEDDED_PDB_INFORMATION *, struct EMBEDDED_PDB_INFORMATION *, bool *, struct XPerfCore::IErrorMessage *))XPerf::Internal::CvDbgInfoFromImage2)(
            (XPerf::Internal *)v27,
            v117,
            (void *)v42,
            v109,
            v79,
            (unsigned int *)&v96 + 1,
            *(union _CVDD **)v101,
            *v26,
            *(struct CODEVIEW_INFORMATION_1 **)v103,
            (struct CODEVIEW_INFORMATION_1 *)((char *)&v109 + 4),
            (unsigned int *)&v107 + 1,
            v104,
            (unsigned __int16 *)v91,
            (unsigned int)&v99,
            (BOOLEAN)v96,
            (struct EMBEDDED_PDB_INFORMATION *)&v112,
            (struct EMBEDDED_PDB_INFORMATION *)((char *)&v96 + 1),
            (bool *)v5 + 376,
            v96);
    v30 = v43;
    if ( v43 >= 0 )
      goto LABEL_90;
    if ( v43 == -2146893023 )
    {
      *((_DWORD *)v5 + 92) = 0;
      operator delete(*v38);
      *v38 = 0;
      operator delete(*v26);
      *v26 = 0;
      v44 = (struct CODEVIEW_INFORMATION_1 **)v103;
      operator delete(*(void **)v103);
      *v44 = 0;
      if ( !(unsigned __int8)ATL::CAutoVectorPtr<_CVDD>::Allocate(v38, HIDWORD(v96))
        || !ATL::CAutoVectorPtr<unsigned long>::Allocate((void **)v26, HIDWORD(v96))
        || !(unsigned __int8)ATL::CAutoVectorPtr<unsigned __int64>::Allocate(v44, HIDWORD(v96)) )
      {
        v7 = -2147024882;
        goto LABEL_98;
      }
      *((_DWORD *)v5 + 92) = HIDWORD(v96);
      LODWORD(v92) = 780;
      v30 = ((__int64 (__fastcall *)(XPerf::Internal *, const unsigned __int16 *, void *, unsigned int, unsigned int, unsigned int *, union _CVDD *, union _CVDD *, struct CODEVIEW_INFORMATION_1 *, struct CODEVIEW_INFORMATION_1 *, unsigned int *, unsigned int *, unsigned __int16 *, unsigned int, BOOLEAN, struct EMBEDDED_PDB_INFORMATION *, struct EMBEDDED_PDB_INFORMATION *, bool *, struct XPerfCore::IErrorMessage *))XPerf::Internal::CvDbgInfoFromImage2)(
              (XPerf::Internal *)v27,
              v117,
              (void *)(unsigned int)v102,
              v109,
              v80,
              (unsigned int *)&v96 + 1,
              (union _CVDD *)*v38,
              *v26,
              *v44,
              (struct CODEVIEW_INFORMATION_1 *)((char *)&v109 + 4),
              (unsigned int *)&v107 + 1,
              v104,
              (unsigned __int16 *)v92,
              (unsigned int)&v99,
              (BOOLEAN)v96,
              (struct EMBEDDED_PDB_INFORMATION *)&v112,
              (struct EMBEDDED_PDB_INFORMATION *)((char *)&v96 + 1),
              (bool *)v5 + 376,
              v96);
      if ( v30 >= 0 )
      {
LABEL_90:
        v7 = 1;
        v47 = HIDWORD(v109);
        v48 = HIDWORD(v96);
        LODWORD(Size) = HIDWORD(v96);
LABEL_92:
        if ( !*(_BYTE *)v111 )
        {
          v49 = Microsoft::Windows::Performance::CImageIdEventTraceExtender::RemovePIIFromCvDD(
                  v41,
                  v48,
                  *(union _CVDD **)v101,
                  (unsigned int *)*v26);
          if ( v49 < 0 )
            goto LABEL_97;
        }
        v50 = *(const union _CVDD **)v101;
        v111 = *(union _CVDD **)v101;
        v51 = *v26;
        v102 = *v26;
        v52 = *(const struct CODEVIEW_INFORMATION_1 **)v103;
        v103 = *(unsigned __int16 **)v103;
        if ( (*((_DWORD *)v5 + 93) & 0x100) == 0 )
        {
          v112 = 0;
          v113 = 0;
        }
        LOBYTE(v96) = 0;
        v53 = HIDWORD(v107);
        v54 = v48;
        v55 = v98;
        v49 = Microsoft::Windows::Performance::CCvDDCache::Add(
                (Microsoft::Windows::Performance::CCvDDCache *)Src,
                (const unsigned __int16 *)v98,
                v109,
                v54,
                v50,
                (const unsigned int *)v51,
                v52,
                v47,
                HIDWORD(v107),
                (const void **)&v112,
                SBYTE1(v96),
                (const unsigned __int16 *)v104,
                (bool *)&v96);
        if ( v49 < 0 )
        {
LABEL_97:
          v7 = v49;
          goto LABEL_98;
        }
        if ( (_BYTE)v96 )
        {
          v84 = (struct CODEVIEW_INFORMATION_1 **)v55;
          v56 = v107;
          Microsoft::Windows::Performance::CImageIdEventTraceExtender::AddFileVersionEvent(
            v5,
            a3,
            v107,
            v53,
            v47,
            (const unsigned __int16 *)v104,
            (const unsigned __int16 *)v84,
            (struct XPerfCore::CFileMapping *)hFile);
        }
        else
        {
          v56 = v107;
        }
        XPerfCore::CFileMapping::Cleanup((XPerfCore::CFileMapping *)hFile);
        v21 = -1;
        goto LABEL_109;
      }
    }
    LODWORD(Size) = HIDWORD(v96);
    goto LABEL_79;
  }
  if ( v24 == -2147467259 || v24 == -2147024774 )
    return 1;
  result = 2147942414LL;
  if ( v25 != -2147024882 )
  {
    (*(void (**)(char *, const wchar_t *, ...))(*((_QWORD *)v5 + 47) + 8LL))(
      (char *)v5 + 376,
      L"unexpected caching error: %x");
    Microsoft::Windows::Performance::CImageIdEventTraceExtender::AddErrorEvent(v5, a3);
    result = 1;
    *((_BYTE *)v5 + 200) = 1;
  }
  return result;
}

```

## disassembly

```asm
0x1800121e8  mov     r11, rsp
0x1800121eb  push    rbx
0x1800121ec  push    rsi
0x1800121ed  push    rdi
0x1800121ee  push    r12
0x1800121f0  push    r13
0x1800121f2  push    r14
0x1800121f4  push    r15
0x1800121f6  sub     rsp, 8D0h
0x1800121fd  mov     rax, cs:__security_cookie
0x180012204  xor     rax, rsp
0x180012207  mov     [rsp+908h+var_48], rax
0x18001220f  mov     r15, r8
0x180012212  mov     [rsp+908h+var_7B0], r8
0x18001221a  mov     r14d, edx
0x18001221d  mov     [rsp+908h+var_85C], edx
0x180012224  mov     rdi, rcx
0x180012227  mov     [rsp+908h+var_7E0], rcx
0x18001222f  mov     [rsp+908h+var_7A8], rcx
0x180012237  mov     [rsp+908h+var_830], edx
0x18001223e  mov     qword ptr [rsp+908h+pguid.Data1], r8
0x180012246  xor     esi, esi
0x180012248  mov     [r11-828h], rsi
0x18001224f  mov     [r11-820h], rsi
0x180012256  mov     [r11-818h], rsi
0x18001225d  mov     [r11-810h], rsi
0x180012264  mov     r9d, [rcx+20h]; unsigned int
0x180012268  mov     r8d, edx; struct _EVENT_TRACE *
0x18001226b  mov     rdx, r15; struct Microsoft::Windows::Performance::CImageData *
0x18001226e  lea     rcx, [r11-828h]; this
0x180012275  call    ?ParseImageEvent@Performance@Windows@Microsoft@@YAJPEAUCImageData@123@PEBU_EVENT_TRACE@@KK@Z; Microsoft::Windows::Performance::ParseImageEvent(Microsoft::Windows::Performance::CImageData *,_EVENT_TRACE const *,ulong,ulong)
0x18001227a  test    eax, eax
0x18001227c  jns     short loc_1800122B0
0x18001227e  lea     rcx, [rdi+178h]
0x180012285  mov     rax, [rcx]
0x180012288  lea     rdx, aFailedToParseI; "Failed to parse image event."
0x18001228f  mov     rax, [rax]
0x180012292  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012297  test    al, al
0x180012299  jz      short loc_1800122A6
0x18001229b  mov     rdx, r15; struct _EVENT_TRACE *
0x18001229e  mov     rcx, rdi; this
0x1800122a1  call    ?AddErrorEvent@CImageIdEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEAU_EVENT_TRACE@@@Z; Microsoft::Windows::Performance::CImageIdEventTraceExtender::AddErrorEvent(_EVENT_TRACE *)
0x1800122a6  mov     ebx, 1
0x1800122ab  jmp     loc_180012DA9
0x1800122b0  mov     rax, [r15+10h]
0x1800122b4  cmp     [rdi+28h], rax
0x1800122b8  jnz     short loc_1800122D4
0x1800122ba  mov     eax, [rsp+908h+var_828]
0x1800122c1  cmp     [rdi+30h], eax
0x1800122c4  jnz     short loc_1800122D4
0x1800122c6  mov     rax, [rsp+908h+var_820]
0x1800122ce  cmp     [rdi+38h], rax
0x1800122d2  jz      short loc_1800122A6
0x1800122d4  lea     r12, [rdi+0C0h]
0x1800122db  lea     rcx, [rdi+40h]
0x1800122df  mov     r8, r12
0x1800122e2  mov     rbx, [rsp+908h+Str]
0x1800122ea  mov     rdx, rbx
0x1800122ed  call    ?GetFileName@CLocalNtImagePathDecoder@NtImagePathDecoder@Performance@@QEAA_NPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; Performance::NtImagePathDecoder::CLocalNtImagePathDecoder::GetFileName(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1800122f2  test    al, al
0x1800122f4  jnz     loc_1800123BD
0x1800122fa  mov     rcx, [rdi+0B8h]
0x180012301  test    rcx, rcx
0x180012304  jz      short loc_180012319
0x180012306  mov     r8, r12
0x180012309  mov     rdx, rbx
0x18001230c  call    ?GetFileName@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEBA_NPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::GetFileName(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180012311  test    al, al
0x180012313  jnz     loc_1800123BD
0x180012319  test    rbx, rbx
0x18001231c  jz      short loc_18001238B
0x18001231e  mov     r14, rsi
0x180012321  cmp     [rdi+0C9h], sil
0x180012328  jnz     short loc_18001235D
0x18001232a  mov     edx, 5Ch ; '\'; Ch
0x18001232f  mov     rcx, rbx; Str
0x180012332  call    cs:__imp_wcsrchr
0x180012338  test    rax, rax
0x18001233b  jz      short loc_18001235D
0x18001233d  sub     rax, rbx
0x180012340  sar     rax, 1
0x180012343  lea     rcx, [rax+1]
0x180012347  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001234b  inc     rax
0x18001234e  cmp     [rbx+rax*2], si
0x180012352  jnz     short loc_18001234B
0x180012354  cmp     rcx, rax
0x180012357  sbb     r14, r14
0x18001235a  and     r14, rcx
0x18001235d  lea     rcx, [rdi+178h]
0x180012364  mov     rax, [rcx]
0x180012367  lea     r8, [rbx+r14*2]
0x18001236b  lea     rdx, aUnableToParseI; "Unable to parse image path: %s"
0x180012372  mov     rax, [rax]
0x180012375  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001237a  test    al, al
0x18001237c  jz      short loc_1800123B3
0x18001237e  mov     rdx, r15; struct _EVENT_TRACE *
0x180012381  mov     rcx, rdi; this
0x180012384  call    ?AddErrorEvent@CImageIdEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEAU_EVENT_TRACE@@@Z; Microsoft::Windows::Performance::CImageIdEventTraceExtender::AddErrorEvent(_EVENT_TRACE *)
0x180012389  jmp     short loc_1800123B3
0x18001238b  lea     rcx, [rdi+178h]
0x180012392  mov     rax, [rcx]
0x180012395  lea     rdx, aNullPathInImag; "NULL path in image path."
0x18001239c  mov     rax, [rax]
0x18001239f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800123a4  test    al, al
0x1800123a6  jz      short loc_1800123B3
0x1800123a8  mov     rdx, r15; struct _EVENT_TRACE *
0x1800123ab  mov     rcx, rdi; this
0x1800123ae  call    ?AddErrorEvent@CImageIdEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEAU_EVENT_TRACE@@@Z; Microsoft::Windows::Performance::CImageIdEventTraceExtender::AddErrorEvent(_EVENT_TRACE *)
0x1800123b3  mov     eax, 1
0x1800123b8  jmp     loc_1800137B9
0x1800123bd  lea     rax, [rdi+0C9h]
0x1800123c4  mov     [rsp+908h+var_800], rax
0x1800123cc  cmp     [rax], sil
0x1800123cf  jnz     short loc_180012438
0x1800123d1  mov     rbx, rsi
0x1800123d4  mov     edx, 5Ch ; '\'; Ch
0x1800123d9  mov     rcx, [r12]; Str
0x1800123dd  call    cs:__imp_wcsrchr
0x1800123e3  test    rax, rax
0x1800123e6  jz      short loc_180012411
0x1800123e8  mov     rcx, [r12]
0x1800123ec  sub     rax, rcx
0x1800123ef  sar     rax, 1
0x1800123f2  lea     rdx, [rax+1]
0x1800123f6  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800123fa  mov     rax, r13
0x1800123fd  inc     rax
0x180012400  cmp     [rcx+rax*2], si
0x180012404  jnz     short loc_1800123FD
0x180012406  cmp     rdx, rax
0x180012409  sbb     rbx, rbx
0x18001240c  and     rbx, rdx
0x18001240f  jmp     short loc_180012415
0x180012411  or      r13, 0FFFFFFFFFFFFFFFFh
0x180012415  lea     rcx, [rdi+178h]
0x18001241c  mov     rdx, [rcx]
0x18001241f  mov     rax, [r12]
0x180012423  lea     r8, [rax+rbx*2]
0x180012427  mov     rax, [rdx]
0x18001242a  lea     rdx, aSFailure; "%s failure: "
0x180012431  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012436  jmp     short loc_18001245F
0x180012438  lea     rcx, [rdi+178h]
0x18001243f  mov     rax, [rcx]
0x180012442  mov     r9, rbx
0x180012445  mov     r8, [r12]
0x180012449  lea     rdx, aSSFailure; "%s [%s] failure: "
0x180012450  mov     rax, [rax]
0x180012453  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012458  mov     r13, 0FFFFFFFFFFFFFFFFh
0x18001245f  mov     rax, [rsp+908h+var_800]
0x180012467  mov     [rsp+908h+var_7A0], rax
0x18001246f  xor     edx, edx; Val
0x180012471  mov     r8d, 640h; Size
0x180012477  lea     rcx, [rsp+908h+var_6F8]; void *
0x18001247f  call    memset_0
0x180012484  cmp     r14d, 4
0x180012488  jz      short loc_18001249E
0x18001248a  cmp     r14d, 8
0x18001248e  jnz     loc_1800136B2
0x180012494  lea     rax, [rsp+908h+var_6E0]
0x18001249c  jmp     short loc_1800124A6
0x18001249e  lea     rax, [rsp+908h+var_6E8]
0x1800124a6  mov     [rsp+908h+var_840], rax
0x1800124ae  mov     [rsp+908h+var_874], esi
0x1800124b5  mov     [rsp+908h+var_850], rsi
0x1800124bd  mov     [rsp+908h+var_848], rsi
0x1800124c5  mov     [rsp+908h+var_858], rsi
0x1800124cd  xorps   xmm0, xmm0
0x1800124d0  xor     ecx, ecx
0x1800124d2  movups  [rsp+908h+var_7F8], xmm0
0x1800124da  mov     [rsp+908h+var_7E8], rcx
0x1800124e2  mov     [rsp+908h+var_877], sil
0x1800124ea  lea     rcx, [rdi+0D0h]; this
0x1800124f1  mov     [rsp+908h+Src], rcx
0x1800124f9  mov     [rsp+908h+var_8B0], rax; unsigned __int16 *
0x1800124fe  lea     rax, [rsp+908h+var_877]
0x180012506  mov     [rsp+908h+var_8B8], rax; bool *
0x18001250b  lea     rax, [rsp+908h+var_7F8]
0x180012513  mov     [rsp+908h+var_8C0], rax; struct EMBEDDED_PDB_INFORMATION *
0x180012518  lea     rax, [rsp+908h+var_824]
0x180012520  mov     [rsp+908h+var_8C8], rax; unsigned int *
0x180012525  lea     rax, [rsp+908h+var_814]
0x18001252d  mov     [rsp+908h+var_8D0], rax; unsigned int *
0x180012532  lea     rax, [rsp+908h+var_858]
0x18001253a  mov     [rsp+908h+var_8D8], rax; struct CODEVIEW_INFORMATION_1 **
0x18001253f  lea     rax, [rsp+908h+var_848]
0x180012547  mov     [rsp+908h+var_8E0], rax; unsigned int **
0x18001254c  lea     rax, [rsp+908h+var_850]
0x180012554  mov     [rsp+908h+var_8E8], rax; unsigned int
0x180012559  lea     r9, [rsp+908h+var_874]; unsigned int *
0x180012561  mov     r8d, [rsp+908h+var_818]; unsigned int
0x180012569  mov     rdx, [r12]; unsigned __int16 *
0x18001256d  call    ?Find@CCvDDCache@Performance@Windows@Microsoft@@QEAAJPEBGKPEAKPEAPEBT_CVDD@@PEAPEBKPEAPEBUCODEVIEW_INFORMATION_1@@11AEAUEMBEDDED_PDB_INFORMATION@@AEA_NPEAGK@Z; Microsoft::Windows::Performance::CCvDDCache::Find(ushort const *,ulong,ulong *,_CVDD const * *,ulong const * *,CODEVIEW_INFORMATION_1 const * *,ulong *,ulong *,EMBEDDED_PDB_INFORMATION &,bool &,ushort *,ulong)
0x180012572  mov     r8d, eax
0x180012575  test    eax, eax
0x180012577  jns     loc_180012E74
0x18001257d  cmp     eax, 80070490h
0x180012582  jnz     loc_180012E17
0x180012588  mov     eax, [rdi+170h]
0x18001258e  mov     dword ptr [rsp+908h+Size], eax
0x180012595  mov     [rsp+908h+var_874], eax
0x18001259c  lea     rax, [rdi+158h]
0x1800125a3  mov     [rsp+908h+var_858], rax
0x1800125ab  cmp     [rax], rsi
0x1800125ae  jz      loc_1800136B2
0x1800125b4  lea     r13, [rdi+160h]
0x1800125bb  mov     [rsp+908h+var_7D8], r13
0x1800125c3  cmp     [r13+0], rsi
0x1800125c7  jz      loc_1800136B2
0x1800125cd  lea     rax, [rdi+168h]
0x1800125d4  mov     [rsp+908h+var_848], rax
0x1800125dc  cmp     [rax], rsi
0x1800125df  jz      loc_1800136B2
0x1800125e5  call    ?IsWin8AndUp@COSVersionInfo@Performance@@SA_NXZ; Performance::COSVersionInfo::IsWin8AndUp(void)
0x1800125ea  mov     [rsp+908h+var_878], al; struct XPerfCore::IErrorMessage *
0x1800125f1  movdqa  xmm0, cs:__xmm@0000000000000000ffffffffffffffff
0x1800125f9  movdqu  xmmword ptr [rsp+908h+hFile], xmm0
0x180012602  mov     [rsp+908h+var_7C0], rsi
0x18001260a  mov     [rsp+908h+var_7B8], rsi
0x180012612  mov     rbx, [r12]
0x180012616  mov     [rsp+908h+var_868], rbx
0x18001261e  mov     [rsp+908h+var_850], rbx
0x180012626  lea     r9, [rdi+178h]; struct XPerfCore::IErrorMessage *
0x18001262d  mov     r8b, al; bool
0x180012630  mov     rdx, rbx; lpFileName
0x180012633  lea     rcx, [rsp+908h+hFile]; this
0x18001263b  call    ?MapExistingFileReadOnly2@CFileMapping@XPerfCore@@QEAAJPEBG_NPEAVIErrorMessage@2@@Z; XPerfCore::CFileMapping::MapExistingFileReadOnly2(ushort const *,bool,XPerfCore::IErrorMessage *)
0x180012640  mov     r14d, eax
0x180012643  test    eax, eax
0x180012645  jns     loc_180012957
0x18001264b  cmp     eax, 80070003h
0x180012650  jnz     loc_180012952
0x180012656  movaps  xmm0, xmmword ptr cs:aSystemrootSyst; "\\SystemRoot\\System32\\DriverStore\\Fi"...
0x18001265d  movaps  xmmword ptr [rsp+908h+String2], xmm0
0x180012665  movaps  xmm1, xmmword ptr cs:aSystemrootSyst+10h; "oot\\System32\\DriverStore\\FileReposit"...
0x18001266c  movaps  [rsp+908h+var_A8], xmm1
0x180012674  movaps  xmm0, xmmword ptr cs:aSystemrootSyst+20h; "em32\\DriverStore\\FileRepository\\"
0x18001267b  movaps  [rsp+908h+var_98], xmm0
0x180012683  movaps  xmm1, xmmword ptr cs:aSystemrootSyst+30h; "verStore\\FileRepository\\"
0x18001268a  movaps  [rsp+908h+var_88], xmm1
0x180012692  movaps  xmm0, xmmword ptr cs:aSystemrootSyst+40h; "\\FileRepository\\"
0x180012699  movaps  [rsp+908h+var_78], xmm0
0x1800126a1  movaps  xmm1, xmmword ptr cs:aSystemrootSyst+50h; "ository\\"
0x1800126a8  movaps  [rsp+908h+var_68], xmm1
0x1800126b0  movzx   eax, word ptr cs:aSystemrootSyst+60h; ""
0x1800126b7  mov     [rsp+908h+var_58], ax
0x1800126bf  mov     r8d, 30h ; '0'; MaxCount
0x1800126c5  lea     rdx, [rsp+908h+String2]; String2
0x1800126cd  mov     rcx, [rsp+908h+Str]; String1
0x1800126d5  call    wcsncmp_0
0x1800126da  test    eax, eax
0x1800126dc  jnz     loc_180012952
0x1800126e2  lea     rdx, aGlobalrootDriv; "\\\\?\\GLOBALROOT\\DriverStores\\BSPDRI"...
0x1800126e9  lea     rcx, [rsp+908h+lpFileName]
0x1800126f1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800126f6  nop
0x1800126f7  mov     r9, [rsp+908h+Str]
0x1800126ff  add     r9, 60h ; '`'
0x180012703  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180012707  inc     rdx
0x18001270a  cmp     [r9+rdx*2], si
0x18001270f  jnz     short loc_180012707
0x180012711  mov     rcx, [rsp+908h+var_718]
0x180012719  mov     rax, [rsp+908h+var_710]
0x180012721  sub     rax, rcx
0x180012724  cmp     rdx, rax
0x180012727  ja      short loc_180012775
0x180012729  lea     rdi, [rcx+rdx]
0x18001272d  mov     [rsp+908h+var_718], rdi
0x180012735  lea     rbx, [rsp+908h+lpFileName]
0x18001273d  cmp     [rsp+908h+var_710], 7
0x180012746  cmova   rbx, [rsp+908h+lpFileName]
0x18001274f  lea     r8, [rdx+rdx]; Size
0x180012753  lea     rcx, [rbx+rcx*2]; void *
0x180012757  mov     rdx, r9; Src
0x18001275a  call    memmove_0
0x18001275f  mov     [rbx+rdi*2], si
0x180012763  mov     rdi, [rsp+908h+var_7E0]
0x18001276b  mov     rbx, [rsp+908h+var_868]
0x180012773  jmp     short loc_180012787
0x180012775  mov     [rsp+908h+var_8E8], rdx; __int64
0x18001277a  lea     rcx, [rsp+908h+lpFileName]; Src
0x180012782  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x180012787  lea     r14, [rdi+178h]
0x18001278e  mov     rax, [r14]
0x180012791  lea     r8, [rsp+908h+lpFileName]
0x180012799  cmp     [rsp+908h+var_710], 7
0x1800127a2  cmova   r8, [rsp+908h+lpFileName]
0x1800127ab  lea     rdx, aOsBugWorkaroun; "OS bug workaround - trying alternate pa"...
0x1800127b2  mov     rcx, r14
0x1800127b5  mov     rax, [rax+8]
0x1800127b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127be  lea     rdx, [rsp+908h+lpFileName]
0x1800127c6  cmp     [rsp+908h+var_710], 7
0x1800127cf  cmova   rdx, [rsp+908h+lpFileName]; lpFileName
  ... truncated ...
```
