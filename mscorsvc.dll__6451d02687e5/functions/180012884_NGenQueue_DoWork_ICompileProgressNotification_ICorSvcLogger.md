# NGenQueue::DoWork(ICompileProgressNotification *,ICorSvcLogger *)

- ea: `0x180012884`
- end: `0x1800138b2`
- name: `?DoWork@NGenQueue@@SAXPEAUICompileProgressNotification@@PEAUICorSvcLogger@@@Z`
- size: `4142`
- prototype: `void __fastcall(struct ICompileProgressNotification *, struct ICorSvcLogger *)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001eed0`

## callees

- `0x1800011d0`
- `0x180001808`
- `0x180001da0`
- `0x180002320`
- `0x18000bb00`
- `0x180011b94`
- `0x180011cf8`
- `0x180011e5c`
- `0x180012884`
- `0x1800138b4`
- `0x180013954`
- `0x180013b34`
- `0x180013b9c`
- `0x180030568`
- `0x180030ab8`
- `0x180030d84`
- `0x180031e08`
- `0x1800330c4`
- `0x1800350c4`
- `0x1800363a8`
- `0x1800364c0`
- `0x18003dc30`
- `0x18003f280`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180012981`
- `KERNEL32!CloseHandle` at `0x180012a1f`
- `KERNEL32!CloseHandle` at `0x180012981`
- `KERNEL32!CloseHandle` at `0x180012a1f`
- `ucrtbase_clr0400!wcstol` at `0x180013272`
- `ucrtbase_clr0400!wcstol` at `0x180013272`

## string_xrefs

- `0x18001388f`: `Error:  unexpected registry value type found in the offline queue`

## pseudocode

```c
void __fastcall NGenQueue::DoWork(struct ICompileProgressNotification *a1, struct ICorSvcLogger *a2)
{
  BOOL NGenQueueKey; // ebx
  __int64 v3; // rdx
  __int64 v4; // r8
  BOOL NGenQueueMSIKey; // r12d
  int v6; // r14d
  char i; // al
  const unsigned __int16 *v8; // rbx
  const unsigned __int16 *v9; // rbx
  __int64 v10; // r9
  char v11; // bl
  int v12; // r15d
  int v13; // ecx
  __int64 v14; // rdx
  char *v15; // rax
  const unsigned __int16 *v16; // r8
  int v17; // esi
  char v18; // r10
  __int64 v19; // r12
  const wchar_t *v20; // rcx
  int v21; // r12d
  bool v22; // al
  __int64 v23; // r12
  const unsigned __int16 *v24; // rcx
  _BOOL8 v25; // r8
  __int64 v26; // rcx
  const unsigned __int16 *v27; // r9
  SString *v28; // rbx
  __int64 v29; // rdx
  const unsigned __int16 *v30; // r8
  SString *v31; // rbx
  __int64 v32; // rdx
  __int64 v33; // rax
  __int64 v34; // rbx
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 v40; // r9
  const unsigned __int16 *v41; // rdi
  __int64 v42; // rbx
  const unsigned __int16 *Unicode; // rax
  __int64 v44; // rdx
  const struct SString *v45; // rax
  _QWORD *v46; // rcx
  OLECHAR *v47; // rbx
  Exception *v48; // rcx
  bool v49; // dl
  unsigned int CurrentExceptionCode; // eax
  int v51; // edx
  bool v52; // [rsp+30h] [rbp-8A8h]
  char v53; // [rsp+30h] [rbp-8A8h]
  int v54; // [rsp+34h] [rbp-8A4h] BYREF
  int v55; // [rsp+38h] [rbp-8A0h] BYREF
  int v56; // [rsp+3Ch] [rbp-89Ch]
  int v57; // [rsp+40h] [rbp-898h]
  void *lpMem; // [rsp+48h] [rbp-890h]
  const unsigned __int16 *v59; // [rsp+50h] [rbp-888h]
  int v60; // [rsp+58h] [rbp-880h]
  void (__fastcall ***v61)(void *, __int64); // [rsp+60h] [rbp-878h] BYREF
  int v62; // [rsp+68h] [rbp-870h]
  const unsigned __int16 *v63; // [rsp+70h] [rbp-868h] BYREF
  int v64; // [rsp+78h] [rbp-860h]
  __int64 v65; // [rsp+80h] [rbp-858h] BYREF
  int v66; // [rsp+88h] [rbp-850h]
  const unsigned __int16 *v67; // [rsp+98h] [rbp-840h] BYREF
  int v68; // [rsp+A0h] [rbp-838h]
  bool v69; // [rsp+A8h] [rbp-830h] BYREF
  wchar_t *EndPtr; // [rsp+B0h] [rbp-828h] BYREF
  void **v71; // [rsp+B8h] [rbp-820h] BYREF
  HANDLE hObject; // [rsp+C0h] [rbp-818h]
  SString *v73; // [rsp+C8h] [rbp-810h]
  __int64 v74; // [rsp+D0h] [rbp-808h] BYREF
  int v75; // [rsp+D8h] [rbp-800h]
  void *v76; // [rsp+E0h] [rbp-7F8h]
  __int64 v77; // [rsp+E8h] [rbp-7F0h] BYREF
  int v78; // [rsp+F0h] [rbp-7E8h]
  __int64 v79; // [rsp+F8h] [rbp-7E0h]
  __int64 v80; // [rsp+100h] [rbp-7D8h] BYREF
  int v81; // [rsp+108h] [rbp-7D0h]
  void *v82; // [rsp+110h] [rbp-7C8h]
  int v83; // [rsp+118h] [rbp-7C0h] BYREF
  _QWORD *v84; // [rsp+120h] [rbp-7B8h]
  __int64 v85; // [rsp+128h] [rbp-7B0h] BYREF
  int v86; // [rsp+130h] [rbp-7A8h]
  __int64 v87; // [rsp+138h] [rbp-7A0h]
  _QWORD *v88; // [rsp+140h] [rbp-798h] BYREF
  BOOL v89; // [rsp+148h] [rbp-790h]
  __int64 v90; // [rsp+150h] [rbp-788h] BYREF
  int v91; // [rsp+158h] [rbp-780h]
  __int64 v92; // [rsp+160h] [rbp-778h]
  void (__fastcall ***v93)(_QWORD, __int64); // [rsp+168h] [rbp-770h] BYREF
  int v94; // [rsp+170h] [rbp-768h]
  void (__fastcall ***v95)(_QWORD, __int64); // [rsp+178h] [rbp-760h] BYREF
  int v96; // [rsp+180h] [rbp-758h]
  struct ICorSvcLogger *v97; // [rsp+188h] [rbp-750h]
  struct ICorSvcLogger *v98; // [rsp+190h] [rbp-748h]
  struct ICompileProgressNotification *v99; // [rsp+198h] [rbp-740h]
  _QWORD v100[4]; // [rsp+1A0h] [rbp-738h] BYREF
  BOOL v101; // [rsp+1C0h] [rbp-718h]
  struct ICompileProgressNotification *v102; // [rsp+1C8h] [rbp-710h]
  __m128i v103; // [rsp+1D0h] [rbp-708h] BYREF
  __int64 v104; // [rsp+1E0h] [rbp-6F8h]
  __m128i v105; // [rsp+1E8h] [rbp-6F0h]
  __int64 v106; // [rsp+1F8h] [rbp-6E0h]
  __m128i v107; // [rsp+200h] [rbp-6D8h]
  __int64 v108; // [rsp+210h] [rbp-6C8h]
  __m128i v109; // [rsp+218h] [rbp-6C0h] BYREF
  __int64 v110; // [rsp+228h] [rbp-6B0h]
  _QWORD *v111; // [rsp+230h] [rbp-6A8h] BYREF
  int v112; // [rsp+240h] [rbp-698h] BYREF
  __int64 v113; // [rsp+244h] [rbp-694h]
  unsigned __int16 *v114; // [rsp+250h] [rbp-688h]
  __int16 v115; // [rsp+258h] [rbp-680h] BYREF
  unsigned int v116; // [rsp+460h] [rbp-478h] BYREF
  __int64 v117; // [rsp+464h] [rbp-474h]
  unsigned __int16 *v118; // [rsp+470h] [rbp-468h]
  __int16 v119; // [rsp+478h] [rbp-460h] BYREF
  _DWORD v120[2]; // [rsp+680h] [rbp-258h] BYREF
  int v121; // [rsp+688h] [rbp-250h]
  OLECHAR *v122; // [rsp+690h] [rbp-248h]
  __int16 v123; // [rsp+698h] [rbp-240h] BYREF

  v97 = a2;
  v99 = a1;
  v102 = a1;
  v98 = a2;
  v95 = 0;
  v96 = 0;
  v63 = 0;
  v64 = 0;
  v93 = 0;
  v94 = 0;
  v67 = 0;
  v68 = 0;
  EndPtr = (wchar_t *)&v90;
  v90 = 0;
  v91 = 0;
  v92 = 0;
  hObject = (HANDLE)-1LL;
  v71 = (void **)&VersionedMutexHolder::`vftable';
  if ( (int)FileLockHolder::AcquireNoThrow((FileLockHolder *)&v71, L"ngenofflinequeuelock.dat", 0, 0) < 0 )
  {
    v71 = &FileLockHolder::`vftable';
    if ( hObject != (HANDLE)-1LL )
    {
      CloseHandle(hObject);
      hObject = (HANDLE)-1LL;
    }
LABEL_4:
    AssemblyExclusion::~AssemblyExclusion((AssemblyExclusion *)&v90);
    return;
  }
  if ( (int)AssemblyExclusion::LoadCbsExclusionList((AssemblyExclusion *)&v90) < 0 )
  {
    v71 = &FileLockHolder::`vftable';
    if ( hObject != (HANDLE)-1LL )
    {
      CloseHandle(hObject);
      hObject = (HANDLE)-1LL;
    }
    goto LABEL_4;
  }
  NGenQueueKey = GetNGenQueueKey((__int64)&v95, (__int64)&v63);
  NGenQueueMSIKey = GetNGenQueueMSIKey((__int64)&v93, (__int64)&v67);
  v77 = 0;
  v78 = 0;
  v79 = 0;
  v85 = 0;
  v86 = 0;
  v87 = 0;
  v80 = 0;
  v81 = 0;
  v82 = 0;
  v74 = 0;
  v75 = 0;
  v76 = 0;
  v6 = 0;
  v60 = 0;
  v113 = 512;
  v114 = (unsigned __int16 *)&v115;
  v112 = 2;
  v115 = 0;
  v117 = 512;
  v118 = (unsigned __int16 *)&v119;
  v116 = 2;
  v119 = 0;
  if ( NGenQueueKey )
  {
    for ( i = (*(__int64 (__fastcall **)(const unsigned __int16 *, _QWORD, int *, int *))(*(_QWORD *)v63 + 128LL))(
                v63,
                0,
                &v112,
                &v54);
          i;
          i = (*(__int64 (__fastcall **)(const unsigned __int16 *, _QWORD, int *, int *))(*(_QWORD *)v63 + 128LL))(
                v63,
                (unsigned int)v6,
                &v112,
                &v54) )
    {
      if ( v54 != 1 )
      {
        v41 = v63;
        v42 = *(_QWORD *)v63;
        Unicode = SString::GetUnicode((SString *)&v112);
        (*(void (__fastcall **)(const unsigned __int16 *, const unsigned __int16 *))(v42 + 80))(v41, Unicode);
        v45 = (const struct SString *)SString::SString(
                                        &v103,
                                        v44,
                                        L"Error:  unexpected registry value type found in the offline queue");
        ThrowHR(-2147418113, v45);
      }
      if ( !(*(unsigned __int8 (__fastcall **)(const unsigned __int16 *, _QWORD, int *, unsigned int *))(*(_QWORD *)v63 + 120LL))(
              v63,
              (unsigned int)v6,
              &v112,
              &v116) )
        break;
      EndPtr = (wchar_t *)&v55;
      SString::ConvertToUnicode((SString *)&v112);
      v55 = 2;
      v56 = 2;
      v57 = 16;
      lpMem = (void *)&SString::s_EmptyBuffer;
      SString::Set((SString *)&v55, v114);
      SArray<SString,0>::Append((SBuffer *)&v77, (struct SBuffer *)&v55);
      v59 = (const unsigned __int16 *)&v55;
      SString::ConvertToUnicode((SString *)&v116);
      v55 = 2;
      v56 = 2;
      v57 = 16;
      lpMem = (void *)&SString::s_EmptyBuffer;
      SString::Set((SString *)&v55, v118);
      SArray<SString,0>::Append((SBuffer *)&v85, (struct SBuffer *)&v55);
      SArray<bool,1>::Append((SBuffer *)&v80);
      SArray<bool,1>::Append((SBuffer *)&v74);
      v60 = ++v6;
    }
    v61 = 0;
    v62 = 0;
    (*(void (__fastcall **)(const unsigned __int16 *, _QWORD))(*(_QWORD *)v63 + 88LL))(v63, &v61);
    if ( (*(unsigned __int8 (__fastcall **)(const unsigned __int16 *, void (__fastcall ***)(void *, __int64), int *))(*(_QWORD *)v63 + 96LL))(
           v63,
           v61,
           &v112) )
    {
      do
      {
        v65 = 0;
        v66 = 0;
        v54 = 0;
        v8 = v63;
        SString::ConvertToUnicode((SString *)&v112);
        if ( (*(unsigned __int8 (__fastcall **)(const unsigned __int16 *, unsigned __int16 *, __int64 *))(*(_QWORD *)v8 + 8LL))(
               v8,
               v114,
               &v65)
          && (*(unsigned __int8 (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)v65 + 104LL))(v65, 0, &v54)
          && v54 == 1
          && (*(unsigned __int8 (__fastcall **)(__int64, _QWORD, unsigned int *))(*(_QWORD *)v65 + 40LL))(v65, 0, &v116)
          && v116 >> ((v117 & 0x100000000LL) == 0) != 1 )
        {
          EndPtr = (wchar_t *)&v55;
          SString::ConvertToUnicode((SString *)&v112);
          v55 = 2;
          v56 = 2;
          v57 = 16;
          lpMem = (void *)&SString::s_EmptyBuffer;
          SString::Set((SString *)&v55, v114);
          SArray<SString,0>::Append((SBuffer *)&v77, (struct SBuffer *)&v55);
          v59 = (const unsigned __int16 *)&v55;
          SString::ConvertToUnicode((SString *)&v116);
          v55 = 2;
          v56 = 2;
          v57 = 16;
          lpMem = (void *)&SString::s_EmptyBuffer;
          SString::Set((SString *)&v55, v118);
          SArray<SString,0>::Append((SBuffer *)&v85, (struct SBuffer *)&v55);
          SArray<bool,1>::Append((SBuffer *)&v80);
          SArray<bool,1>::Append((SBuffer *)&v74);
          ++v6;
        }
        if ( v66 )
        {
          if ( v65 )
            (**(void (__fastcall ***)(__int64, __int64))v65)(v65, 1);
          v66 = 0;
        }
      }
      while ( (*(unsigned __int8 (__fastcall **)(const unsigned __int16 *, void (__fastcall ***)(void *, __int64), int *))(*(_QWORD *)v63 + 96LL))(
                v63,
                v61,
                &v112) );
      v60 = v6;
    }
    if ( v62 )
    {
      if ( v61 )
        (**v61)(v61, 1);
      v62 = 0;
    }
  }
  if ( NGenQueueMSIKey )
  {
    v61 = 0;
    v62 = 0;
    (*(void (__fastcall **)(const unsigned __int16 *, _QWORD))(*(_QWORD *)v67 + 88LL))(v67, &v61);
    if ( (*(unsigned __int8 (__fastcall **)(const unsigned __int16 *, void (__fastcall ***)(void *, __int64), int *))(*(_QWORD *)v67 + 96LL))(
           v67,
           v61,
           &v112) )
    {
      do
      {
        v65 = 0;
        v66 = 0;
        v54 = 0;
        v9 = v67;
        SString::ConvertToUnicode((SString *)&v112);
        if ( (*(unsigned __int8 (__fastcall **)(const unsigned __int16 *, unsigned __int16 *, __int64 *))(*(_QWORD *)v9 + 8LL))(
               v9,
               v114,
               &v65)
          && (*(unsigned __int8 (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)v65 + 104LL))(v65, 0, &v54)
          && v54 == 1
          && (*(unsigned __int8 (__fastcall **)(__int64, _QWORD, unsigned int *))(*(_QWORD *)v65 + 40LL))(v65, 0, &v116)
          && v116 >> ((v117 & 0x100000000LL) == 0) != 1 )
        {
          EndPtr = (wchar_t *)&v55;
          SString::ConvertToUnicode((SString *)&v112);
          v55 = 2;
          v56 = 2;
          v57 = 16;
          lpMem = (void *)&SString::s_EmptyBuffer;
          SString::Set((SString *)&v55, v114);
          SArray<SString,0>::Append((SBuffer *)&v77, (struct SBuffer *)&v55);
          v59 = (const unsigned __int16 *)&v55;
          SString::ConvertToUnicode((SString *)&v116);
          v55 = 2;
          v56 = 2;
          v57 = 16;
          lpMem = (void *)&SString::s_EmptyBuffer;
          SString::Set((SString *)&v55, v118);
          SArray<SString,0>::Append((SBuffer *)&v85, (struct SBuffer *)&v55);
          SArray<bool,1>::Append((SBuffer *)&v80);
          SArray<bool,1>::Append((SBuffer *)&v74);
          ++v6;
        }
        if ( v66 )
        {
          if ( v65 )
            (**(void (__fastcall ***)(__int64, __int64))v65)(v65, 1);
          v66 = 0;
        }
      }
      while ( (*(unsigned __int8 (__fastcall **)(const unsigned __int16 *, void (__fastcall ***)(void *, __int64), int *))(*(_QWORD *)v67 + 96LL))(
                v67,
                v61,
                &v112) );
      v60 = v6;
    }
    if ( v62 )
    {
      if ( v61 )
        (**v61)(v61, 1);
      v62 = 0;
    }
  }
LABEL_50:
  v10 = 0x7FFFFFFF;
  if ( v6 > 0 )
  {
    v11 = 0;
    v12 = 0;
    v13 = 0;
    v54 = 0;
    v14 = 0;
    v65 = 0;
    v15 = (char *)v82;
    v61 = (void (__fastcall ***)(void *, __int64))v82;
    v16 = (const unsigned __int16 *)((_BYTE *)v76 - (_BYTE *)v82);
    v59 = (const unsigned __int16 *)((_BYTE *)v76 - (_BYTE *)v82);
    v17 = 0x7FFFFFFF;
    while ( 1 )
    {
      if ( !v15[(_QWORD)v16] )
      {
        v18 = *v15;
        if ( !v11 )
        {
          if ( v18 )
          {
            v11 = 1;
            v17 = 0x7FFFFFFF;
          }
LABEL_58:
          v19 = v14 + v79;
          v73 = (SString *)(v14 + v79);
          EndPtr = 0;
          if ( v14 + v79 )
          {
            SString::ConvertToUnicode((SString *)(v14 + v79));
            v20 = *(const wchar_t **)(v19 + 16);
          }
          else
          {
            v20 = 0;
          }
          v21 = wcstol(v20, &EndPtr, 10);
          if ( !v21 )
          {
            v55 = 4;
            v56 = 4;
            lpMem = L"0";
            v57 = 276;
            v22 = (unsigned int)SString::Equals(v73, (const struct SString *)&v55) == 0;
            v52 = v22;
            if ( (v57 & 8) != 0 )
            {
              operator delete(lpMem);
              v22 = v52;
            }
            if ( v22 )
              v21 = 0x7FFFFFFF;
          }
          v13 = v54;
          v15 = (char *)v61;
          v14 = v65;
          v16 = v59;
          if ( v21 < v17 )
          {
            v17 = v21;
            v12 = v54;
          }
          goto LABEL_68;
        }
        if ( v18 )
          goto LABEL_58;
      }
LABEL_68:
      v54 = ++v13;
      v61 = (void (__fastcall ***)(void *, __int64))++v15;
      v14 += 24;
      v65 = v14;
      if ( v13 >= v6 )
      {
        v53 = v11;
        v54 = v12;
        if ( !v12 )
        {
          v53 = v11;
          v54 = 0;
          if ( *(_BYTE *)v76 )
          {
            v11 = 1;
            v53 = 1;
            v54 = 0;
          }
        }
        v23 = v12;
        v65 = v12;
        v61 = (void (__fastcall ***)(void *, __int64))v12;
        v59 = (const unsigned __int16 *)(v87 + 24LL * v12);
        if ( v59 )
        {
          SString::ConvertToUnicode((SString *)(v87 + 24LL * v12));
          v24 = (const unsigned __int16 *)*((_QWORD *)v59 + 2);
        }
        else
        {
          v24 = 0;
        }
        v59 = v24;
        v83 = 0;
        v84 = 0;
        if ( __eh34_try(-1, 0) )
        {
          __eh34_scope_strut(0);
          if ( __eh34_try(0, 1) )
          {
            __eh34_scope_strut(1);
            v73 = (SString *)&v83;
            ExecuteNGenCommand(v24, v99, v97, *((_BYTE *)v76 + v12) == 0, (struct AssemblyExclusion *)&v90);
          }
          if ( __eh34_catch(1) )
          {
            if ( __eh34_catch_type(1, &Exception * `RTTI Type Descriptor', (Exception **)&v111) )
            {
              Exception::HandlerState::SetCaughtCxx((Exception::HandlerState *)&v83);
              v84 = v111;
              throw;
            }
          }
        }
        if ( __eh34_catch(0) )
        {
          if ( __eh34_catch_ellipsis(0) )
          {
            v100[1] = 0;
            v100[0] = &DelegatingException::`vftable';
            v100[2] = -1;
            v88 = v84;
            v89 = v84 != 0;
            Exception::HandlerState::SetupCatch((Exception::HandlerState *)&v83, 377, v25);
            v46 = v100;
            if ( v88 )
              v46 = v88;
            v121 = 0;
            v122 = (OLECHAR *)&v123;
            v120[1] = 512;
            v120[0] = 2;
            v123 = 0;
            (*(void (__fastcall **)(_QWORD *, _DWORD *))(*v46 + 24LL))(v46, v120);
            SString::Append((SString *)v120, L"\n");
            SString::ConvertToUnicode((SString *)v120);
            v47 = SysAllocString(v122);
            v100[3] = v47;
            v101 = v47 != 0;
            (*(void (__fastcall **)(struct ICorSvcLogger *, __int64, OLECHAR *))(*(_QWORD *)v98 + 24LL))(v98, 1, v47);
            if ( NGENService::g_bProcessNGENService )
              NGENService::EventLog(
                0,
                (const unsigned __int16 *)1,
                0x453u,
                (unsigned int)L"Failed to execute command from the offline queue: %s.  The error returned was %s.",
                v59,
                v47);
            if ( v47 )
            {
              SysFreeString(v47);
              v101 = 0;
            }
            if ( (v121 & 8) != 0 )
              operator delete(v122);
            v48 = (Exception *)v100;
            if ( v88 )
              v48 = (Exception *)v88;
            if ( (unsigned int)Exception::IsTerminal(v48)
              || !CLRConfig::GetConfigValue(
                    (const struct CLRConfig::ConfigDWORDInfo *)&CLRConfig::UNSUPPORTED_legacyCorruptedStateExceptionsPolicy,
                    v49,
                    &v69)
              && (CurrentExceptionCode = GetCurrentExceptionCode(),
                  (unsigned int)IsProcessCorruptedStateException(CurrentExceptionCode, v51)) )
            {
              v89 = 0;
              throw;
            }
            Wrapper<Exception *,&void DoNothing<Exception *>(Exception *),&void Exception__Delete<Exception>(Exception *),0,&int CompareDefault<Exception *>(Exception *,Exception *),2,1>::~Wrapper<Exception *,&void DoNothing<Exception *>(Exception *),&void Exception__Delete<Exception>(Exception *),0,&int CompareDefault<Exception *>(Exception *,Exception *),2,1>((__int64 *)&v88);
            DelegatingException::~DelegatingException((DelegatingException *)v100);
            v6 = v60;
            v11 = v53;
            v12 = v54;
            v99 = v102;
            v97 = v98;
            v23 = v65;
            __eh34_try_continuation(0, &loc_18001341A);
          }
        }
        if ( (v83 & 2) != 0 && g_fpHandleStackOverflowAfterCatch )
          g_fpHandleStackOverflowAfterCatch();
        v26 = 24LL * (_QWORD)v61;
        if ( !v11 )
        {
          v30 = v63;
          v59 = v63;
          v31 = (SString *)(v26 + v79);
          if ( v26 + v79 )
          {
            SString::ConvertToUnicode(v31);
            v32 = *((_QWORD *)v31 + 2);
            v30 = v59;
          }
          else
          {
            v32 = 0;
          }
          (*(void (__fastcall **)(const unsigned __int16 *, __int64))(*(_QWORD *)v30 + 80LL))(v30, v32);
          goto LABEL_91;
        }
        if ( !*((_BYTE *)v76 + v23) )
        {
          v27 = v63;
          v59 = v63;
          v28 = (SString *)(v26 + v79);
          if ( v26 + v79 )
            goto LABEL_85;
LABEL_84:
          v29 = 0;
          goto LABEL_86;
        }
        v27 = v67;
        v59 = v67;
        v28 = (SString *)(v26 + v79);
        if ( !(v26 + v79) )
          goto LABEL_84;
LABEL_85:
        SString::ConvertToUnicode(v28);
        v27 = v59;
        v29 = *((_QWORD *)v28 + 2);
LABEL_86:
        LOBYTE(v25) = 1;
        (*(void (__fastcall **)(const unsigned __int16 *, __int64, _BOOL8))(*(_QWORD *)v27 + 24LL))(v27, v29, v25);
LABEL_91:
        v33 = SArray<SString,0>::Begin(&v77, &v65);
        v105 = *(__m128i *)(v33 & ((unsigned __int128)-(__int128)(unsigned __int64)(v33 + 1) >> 64));
        v106 = *(_QWORD *)((v33 & ((unsigned __int128)-(__int128)(unsigned __int64)(v33 + 1) >> 64)) + 0x10);
        v34 = 24 * v12;
        v105.m128i_i64[1] = v34 + _mm_srli_si128(v105, 8).m128i_u64[0];
        SArray<SString,0>::Replace((SBuffer *)&v77);
        v35 = SArray<SString,0>::Begin(&v85, &v65);
        v107 = *(__m128i *)(v35 & ((unsigned __int128)-(__int128)(unsigned __int64)(v35 + 1) >> 64));
        v108 = *(_QWORD *)((v35 & ((unsigned __int128)-(__int128)(unsigned __int64)(v35 + 1) >> 64)) + 0x10);
        v107.m128i_i64[1] = v34 + _mm_srli_si128(v107, 8).m128i_u64[0];
        SArray<SString,0>::Replace((SBuffer *)&v85);
        v36 = SArray<SString,0>::Begin(&v80, &v65);
        v109 = *(__m128i *)(v36 & ((unsigned __int128)-(__int128)(unsigned __int64)(v36 + 1) >> 64));
        v110 = *(_QWORD *)((v36 & ((unsigned __int128)-(__int128)(unsigned __int64)(v36 + 1) >> 64)) + 0x10);
        v109.m128i_i64[1] = v23 + _mm_srli_si128(v109, 8).m128i_u64[0];
        SBuffer::Replace((SBuffer *)&v80, (const struct SBuffer::Iterator *)&v109.m128i_u64[1], 1u, 0);
        v37 = SArray<SString,0>::Begin(&v74, &v65);
        v103 = *(__m128i *)(v37 & ((unsigned __int128)-(__int128)(unsigned __int64)(v37 + 1) >> 64));
        v104 = *(_QWORD *)((v37 & ((unsigned __int128)-(__int128)(unsigned __int64)(v37 + 1) >> 64)) + 0x10);
        v103.m128i_i64[1] = v23 + _mm_srli_si128(v103, 8).m128i_u64[0];
        SBuffer::Replace((SBuffer *)&v74, (const struct SBuffer::Iterator *)&v103.m128i_u64[1], 1u, 0);
        v60 = --v6;
        goto LABEL_50;
      }
    }
  }
  if ( (v117 & 0x800000000LL) != 0 )
    operator delete(v118);
  if ( (v113 & 0x800000000LL) != 0 )
    operator delete(v114);
  if ( (v75 & 8) != 0 )
    operator delete(v76);
  if ( (v81 & 8) != 0 )
    operator delete(v82);
  SArray<SString,0>::~SArray<SString,0>(&v85, v3, v4, v10);
  SArray<SString,0>::~SArray<SString,0>(&v77, v38, v39, v40);
  FileLockHolder::~FileLockHolder((FileLockHolder *)&v71);
  AssemblyExclusion::~AssemblyExclusion((AssemblyExclusion *)&v90);
  if ( v68 )
  {
    if ( v67 )
      (**(void (__fastcall ***)(const unsigned __int16 *, __int64))v67)(v67, 1);
    v68 = 0;
  }
  if ( v94 )
  {
    if ( v93 )
      (**v93)(v93, 1);
    v94 = 0;
  }
  if ( v64 )
  {
    if ( v63 )
      (**(void (__fastcall ***)(const unsigned __int16 *, __int64))v63)(v63, 1);
    v64 = 0;
  }
  if ( v96 )
  {
    if ( v95 )
      (**v95)(v95, 1);
    v96 = 0;
  }
}

```

## disassembly

```asm
0x180012884  mov     r11, rsp
0x180012887  mov     [r11+18h], rbx
0x18001288b  push    rsi
0x18001288c  push    rdi
0x18001288d  push    r12
0x18001288f  push    r14
0x180012891  push    r15
0x180012893  sub     rsp, 8B0h
0x18001289a  mov     rax, cs:__security_cookie
0x1800128a1  xor     rax, rsp
0x1800128a4  mov     [rsp+8D8h+var_38], rax
0x1800128ac  mov     [rsp+8D8h+var_750], rdx
0x1800128b4  mov     [rsp+8D8h+var_740], rcx
0x1800128bc  mov     [rsp+8D8h+var_710], rcx
0x1800128c4  mov     [rsp+8D8h+var_748], rdx
0x1800128cc  xor     edi, edi
0x1800128ce  mov     [r11-760h], rdi
0x1800128d5  mov     [rsp+8D8h+var_758], edi
0x1800128dc  mov     [rsp+8D8h+var_868], rdi
0x1800128e1  mov     [rsp+8D8h+var_860], edi
0x1800128e5  mov     [r11-770h], rdi
0x1800128ec  mov     [rsp+8D8h+var_768], edi
0x1800128f3  mov     [r11-840h], rdi
0x1800128fa  mov     [rsp+8D8h+var_838], edi
0x180012901  lea     rax, [r11-788h]
0x180012908  mov     [r11-828h], rax
0x18001290f  mov     [r11-788h], rdi
0x180012916  mov     [rsp+8D8h+var_780], edi
0x18001291d  mov     [r11-778h], rdi
0x180012924  lea     rsi, ??_7FileLockHolder@@6B@; const FileLockHolder::`vftable'
0x18001292b  mov     [r11-820h], rsi
0x180012932  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180012936  mov     [r11-818h], rbx
0x18001293d  lea     rax, ??_7VersionedMutexHolder@@6B@; const VersionedMutexHolder::`vftable'
0x180012944  mov     [r11-820h], rax
0x18001294b  xor     r9d, r9d; int *
0x18001294e  xor     r8d, r8d; void *
0x180012951  lea     rdx, aNgenofflineque; "ngenofflinequeuelock.dat"
0x180012958  lea     rcx, [r11-820h]; this
0x18001295f  call    ?AcquireNoThrow@FileLockHolder@@QEAAJPEBGPEAXPEAH@Z; FileLockHolder::AcquireNoThrow(ushort const *,void *,int *)
0x180012964  test    eax, eax
0x180012966  jns     loc_1800129F5
0x18001296c  mov     [rsp+8D8h+var_820], rsi
0x180012974  mov     rcx, [rsp+8D8h+hObject]; hObject
0x18001297c  cmp     rcx, rbx
0x18001297f  jz      short loc_18001298F
0x180012981  call    cs:__imp_CloseHandle
0x180012987  mov     [rsp+8D8h+hObject], rbx
0x18001298f  lea     rcx, [rsp+8D8h+var_788]; this
0x180012997  call    ??1AssemblyExclusion@@QEAA@XZ; AssemblyExclusion::~AssemblyExclusion(void)
0x18001299c  nop
0x18001299d  cmp     [rsp+8D8h+var_838], edi
0x1800129a4  jz      short loc_1800129CB
0x1800129a6  mov     rcx, [rsp+8D8h+var_840]
0x1800129ae  test    rcx, rcx
0x1800129b1  jz      short loc_1800129C4
0x1800129b3  mov     rax, [rcx]
0x1800129b6  mov     edx, 1
0x1800129bb  mov     rax, [rax]
0x1800129be  call    cs:__guard_dispatch_icall_fptr
0x1800129c4  mov     [rsp+8D8h+var_838], edi
0x1800129cb  cmp     [rsp+8D8h+var_860], edi
0x1800129cf  jz      short loc_1800129F0
0x1800129d1  mov     rcx, [rsp+8D8h+var_868]
0x1800129d6  test    rcx, rcx
0x1800129d9  jz      short loc_1800129EC
0x1800129db  mov     rax, [rcx]
0x1800129de  mov     edx, 1
0x1800129e3  mov     rax, [rax]
0x1800129e6  call    cs:__guard_dispatch_icall_fptr
0x1800129ec  mov     [rsp+8D8h+var_860], edi
0x1800129f0  jmp     loc_180013842
0x1800129f5  lea     rcx, [rsp+8D8h+var_788]; this
0x1800129fd  call    ?LoadCbsExclusionList@AssemblyExclusion@@AEAAJXZ; AssemblyExclusion::LoadCbsExclusionList(void)
0x180012a02  test    eax, eax
0x180012a04  jns     loc_180012A93
0x180012a0a  mov     [rsp+8D8h+var_820], rsi
0x180012a12  mov     rcx, [rsp+8D8h+hObject]; hObject
0x180012a1a  cmp     rcx, rbx
0x180012a1d  jz      short loc_180012A2D
0x180012a1f  call    cs:__imp_CloseHandle
0x180012a25  mov     [rsp+8D8h+hObject], rbx
0x180012a2d  lea     rcx, [rsp+8D8h+var_788]; this
0x180012a35  call    ??1AssemblyExclusion@@QEAA@XZ; AssemblyExclusion::~AssemblyExclusion(void)
0x180012a3a  nop
0x180012a3b  cmp     [rsp+8D8h+var_838], edi
0x180012a42  jz      short loc_180012A69
0x180012a44  mov     rcx, [rsp+8D8h+var_840]
0x180012a4c  test    rcx, rcx
0x180012a4f  jz      short loc_180012A62
0x180012a51  mov     rax, [rcx]
0x180012a54  mov     edx, 1
0x180012a59  mov     rax, [rax]
0x180012a5c  call    cs:__guard_dispatch_icall_fptr
0x180012a62  mov     [rsp+8D8h+var_838], edi
0x180012a69  cmp     [rsp+8D8h+var_860], edi
0x180012a6d  jz      short loc_180012A8E
0x180012a6f  mov     rcx, [rsp+8D8h+var_868]
0x180012a74  test    rcx, rcx
0x180012a77  jz      short loc_180012A8A
0x180012a79  mov     rax, [rcx]
0x180012a7c  mov     edx, 1
0x180012a81  mov     rax, [rax]
0x180012a84  call    cs:__guard_dispatch_icall_fptr
0x180012a8a  mov     [rsp+8D8h+var_860], edi
0x180012a8e  jmp     loc_180013842
0x180012a93  lea     rdx, [rsp+8D8h+var_868]
0x180012a98  lea     rcx, [rsp+8D8h+var_760]
0x180012aa0  call    ?GetNGenQueueKey@@YAHAEAV?$NewHolder@VIRegWrapper@@@@AEAV?$NewHolder@VKey@IRegWrapper@@@@@Z; GetNGenQueueKey(NewHolder<IRegWrapper> &,NewHolder<IRegWrapper::Key> &)
0x180012aa5  mov     ebx, eax
0x180012aa7  lea     rdx, [rsp+8D8h+var_840]
0x180012aaf  lea     rcx, [rsp+8D8h+var_770]
0x180012ab7  call    ?GetNGenQueueMSIKey@@YAHAEAV?$NewHolder@VIRegWrapper@@@@AEAV?$NewHolder@VKey@IRegWrapper@@@@@Z; GetNGenQueueMSIKey(NewHolder<IRegWrapper> &,NewHolder<IRegWrapper::Key> &)
0x180012abc  mov     r12d, eax
0x180012abf  mov     [rsp+8D8h+var_7F0], rdi
0x180012ac7  mov     [rsp+8D8h+var_7E8], edi
0x180012ace  mov     [rsp+8D8h+var_7E0], rdi
0x180012ad6  mov     [rsp+8D8h+var_7B0], rdi
0x180012ade  mov     [rsp+8D8h+var_7A8], edi
0x180012ae5  mov     [rsp+8D8h+var_7A0], rdi
0x180012aed  mov     [rsp+8D8h+var_7D8], rdi
0x180012af5  mov     [rsp+8D8h+var_7D0], edi
0x180012afc  mov     [rsp+8D8h+var_7C8], rdi
0x180012b04  mov     [rsp+8D8h+var_808], rdi
0x180012b0c  mov     [rsp+8D8h+var_800], edi
0x180012b13  mov     [rsp+8D8h+var_7F8], rdi
0x180012b1b  mov     r14d, edi
0x180012b1e  mov     [rsp+8D8h+var_880], edi
0x180012b22  mov     [rsp+8D8h+var_698], rdi
0x180012b2a  mov     [rsp+8D8h+var_698+4], 200h
0x180012b36  mov     [rsp+8D8h+var_688], rdi
0x180012b3e  lea     rax, [rsp+8D8h+var_680]
0x180012b46  mov     [rsp+8D8h+var_688], rax
0x180012b4e  mov     esi, 2
0x180012b53  mov     dword ptr [rsp+8D8h+var_698], esi
0x180012b5a  mov     rax, [rsp+8D8h+var_688]
0x180012b62  mov     [rax], di
0x180012b65  mov     [rsp+8D8h+var_478], rdi
0x180012b6d  mov     [rsp+8D8h+var_478+4], 200h
0x180012b79  mov     [rsp+8D8h+var_468], rdi
0x180012b81  lea     rax, [rsp+8D8h+var_460]
0x180012b89  mov     [rsp+8D8h+var_468], rax
0x180012b91  mov     dword ptr [rsp+8D8h+var_478], esi
0x180012b98  mov     rax, [rsp+8D8h+var_468]
0x180012ba0  mov     [rax], di
0x180012ba3  cmp     ebx, 1
0x180012ba6  jnz     loc_180012F5D
0x180012bac  mov     rcx, [rsp+8D8h+var_868]
0x180012bb1  mov     rax, [rcx]
0x180012bb4  lea     r9, [rsp+8D8h+var_8A4]
0x180012bb9  lea     r8, [rsp+8D8h+var_698]
0x180012bc1  xor     edx, edx
0x180012bc3  mov     rax, [rax+80h]
0x180012bca  call    cs:__guard_dispatch_icall_fptr
0x180012bd0  lea     r15, ?s_EmptyBuffer@SString@@0QBEB; uchar const near * const SString::s_EmptyBuffer
0x180012bd7  jmp     loc_180012D04
0x180012bdc  cmp     [rsp+8D8h+var_8A4], 1
0x180012be1  jnz     loc_18001386A
0x180012be7  mov     rcx, [rsp+8D8h+var_868]
0x180012bec  mov     rax, [rcx]
0x180012bef  lea     r9, [rsp+8D8h+var_478]
0x180012bf7  lea     r8, [rsp+8D8h+var_698]
0x180012bff  mov     edx, r14d
0x180012c02  mov     rax, [rax+78h]
0x180012c06  call    cs:__guard_dispatch_icall_fptr
0x180012c0c  test    al, al
0x180012c0e  jz      loc_180012D0C
0x180012c14  lea     rax, [rsp+8D8h+var_8A0]
0x180012c19  mov     [rsp+8D8h+EndPtr], rax
0x180012c21  lea     rcx, [rsp+8D8h+var_698]; this
0x180012c29  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180012c2e  mov     rdx, [rsp+8D8h+var_688]; unsigned __int16 *
0x180012c36  mov     [rsp+8D8h+var_8A0], esi
0x180012c3a  mov     [rsp+8D8h+var_89C], esi
0x180012c3e  mov     [rsp+8D8h+var_898], 10h
0x180012c46  mov     [rsp+8D8h+lpMem], r15
0x180012c4b  lea     rcx, [rsp+8D8h+var_8A0]; this
0x180012c50  call    ?Set@SString@@QEAAXPEBG@Z; SString::Set(ushort const *)
0x180012c55  nop
0x180012c56  lea     rdx, [rsp+8D8h+var_8A0]; struct SBuffer *
0x180012c5b  lea     rcx, [rsp+8D8h+var_7F0]; this
0x180012c63  call    ?Append@?$SArray@VSString@@$0A@@@QEAAXVSString@@@Z; SArray<SString,0>::Append(SString)
0x180012c68  lea     rax, [rsp+8D8h+var_8A0]
0x180012c6d  mov     [rsp+8D8h+var_888], rax
0x180012c72  lea     rcx, [rsp+8D8h+var_478]; this
0x180012c7a  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180012c7f  mov     rdx, [rsp+8D8h+var_468]; unsigned __int16 *
0x180012c87  mov     [rsp+8D8h+var_8A0], esi
0x180012c8b  mov     [rsp+8D8h+var_89C], esi
0x180012c8f  mov     [rsp+8D8h+var_898], 10h
0x180012c97  mov     [rsp+8D8h+lpMem], r15
0x180012c9c  lea     rcx, [rsp+8D8h+var_8A0]; this
0x180012ca1  call    ?Set@SString@@QEAAXPEBG@Z; SString::Set(ushort const *)
0x180012ca6  nop
0x180012ca7  lea     rdx, [rsp+8D8h+var_8A0]; struct SBuffer *
0x180012cac  lea     rcx, [rsp+8D8h+var_7B0]; this
0x180012cb4  call    ?Append@?$SArray@VSString@@$0A@@@QEAAXVSString@@@Z; SArray<SString,0>::Append(SString)
0x180012cb9  xor     edx, edx
0x180012cbb  lea     rcx, [rsp+8D8h+var_7D8]; this
0x180012cc3  call    ?Append@?$SArray@_N$00@@QEAAX_N@Z; SArray<bool,1>::Append(bool)
0x180012cc8  xor     edx, edx
0x180012cca  lea     rcx, [rsp+8D8h+var_808]; this
0x180012cd2  call    ?Append@?$SArray@_N$00@@QEAAX_N@Z; SArray<bool,1>::Append(bool)
0x180012cd7  inc     r14d
0x180012cda  mov     [rsp+8D8h+var_880], r14d
0x180012cdf  mov     rcx, [rsp+8D8h+var_868]
0x180012ce4  mov     rax, [rcx]
0x180012ce7  lea     r9, [rsp+8D8h+var_8A4]
0x180012cec  lea     r8, [rsp+8D8h+var_698]
0x180012cf4  mov     edx, r14d
0x180012cf7  mov     rax, [rax+80h]
0x180012cfe  call    cs:__guard_dispatch_icall_fptr
0x180012d04  test    al, al
0x180012d06  jnz     loc_180012BDC
0x180012d0c  mov     [rsp+8D8h+var_878], rdi
0x180012d11  mov     [rsp+8D8h+var_870], edi
0x180012d15  mov     rcx, [rsp+8D8h+var_868]
0x180012d1a  mov     rax, [rcx]
0x180012d1d  lea     rdx, [rsp+8D8h+var_878]
0x180012d22  mov     rax, [rax+58h]
0x180012d26  call    cs:__guard_dispatch_icall_fptr
0x180012d2c  mov     rcx, [rsp+8D8h+var_868]
0x180012d31  mov     rax, [rcx]
0x180012d34  lea     r8, [rsp+8D8h+var_698]
0x180012d3c  mov     rdx, [rsp+8D8h+var_878]
0x180012d41  mov     rax, [rax+60h]
0x180012d45  call    cs:__guard_dispatch_icall_fptr
0x180012d4b  test    al, al
0x180012d4d  jz      loc_180012F36
0x180012d53  mov     [rsp+8D8h+var_858], rdi
0x180012d5b  mov     [rsp+8D8h+var_850], edi
0x180012d62  mov     [rsp+8D8h+var_8A4], edi
0x180012d66  mov     rbx, [rsp+8D8h+var_868]
0x180012d6b  lea     rcx, [rsp+8D8h+var_698]; this
0x180012d73  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180012d78  mov     rax, [rbx]
0x180012d7b  lea     r8, [rsp+8D8h+var_858]
0x180012d83  mov     rdx, [rsp+8D8h+var_688]
0x180012d8b  mov     rcx, rbx
0x180012d8e  mov     rax, [rax+8]
0x180012d92  call    cs:__guard_dispatch_icall_fptr
0x180012d98  test    al, al
0x180012d9a  jz      loc_180012EDC
0x180012da0  mov     rcx, [rsp+8D8h+var_858]
0x180012da8  mov     rax, [rcx]
0x180012dab  lea     r8, [rsp+8D8h+var_8A4]
0x180012db0  xor     edx, edx
0x180012db2  mov     rax, [rax+68h]
0x180012db6  call    cs:__guard_dispatch_icall_fptr
0x180012dbc  test    al, al
0x180012dbe  jz      loc_180012EDC
0x180012dc4  cmp     [rsp+8D8h+var_8A4], 1
0x180012dc9  jnz     loc_180012EDC
0x180012dcf  mov     rcx, [rsp+8D8h+var_858]
0x180012dd7  mov     rax, [rcx]
0x180012dda  lea     r8, [rsp+8D8h+var_478]
0x180012de2  xor     edx, edx
0x180012de4  mov     rax, [rax+28h]
0x180012de8  call    cs:__guard_dispatch_icall_fptr
0x180012dee  test    al, al
0x180012df0  jz      loc_180012EDC
0x180012df6  mov     ecx, [rsp+8D8h+var_470]
0x180012dfd  not     ecx
0x180012dff  and     ecx, 1
0x180012e02  mov     eax, dword ptr [rsp+8D8h+var_478]
0x180012e09  shr     eax, cl
0x180012e0b  cmp     eax, 1
0x180012e0e  jz      loc_180012EDC
0x180012e14  lea     rax, [rsp+8D8h+var_8A0]
0x180012e19  mov     [rsp+8D8h+EndPtr], rax
0x180012e21  lea     rcx, [rsp+8D8h+var_698]; this
0x180012e29  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180012e2e  mov     rdx, [rsp+8D8h+var_688]; unsigned __int16 *
0x180012e36  mov     [rsp+8D8h+var_8A0], esi
0x180012e3a  mov     [rsp+8D8h+var_89C], esi
0x180012e3e  mov     [rsp+8D8h+var_898], 10h
0x180012e46  mov     [rsp+8D8h+lpMem], r15
0x180012e4b  lea     rcx, [rsp+8D8h+var_8A0]; this
0x180012e50  call    ?Set@SString@@QEAAXPEBG@Z; SString::Set(ushort const *)
0x180012e55  nop
0x180012e56  lea     rdx, [rsp+8D8h+var_8A0]; struct SBuffer *
0x180012e5b  lea     rcx, [rsp+8D8h+var_7F0]; this
0x180012e63  call    ?Append@?$SArray@VSString@@$0A@@@QEAAXVSString@@@Z; SArray<SString,0>::Append(SString)
0x180012e68  lea     rax, [rsp+8D8h+var_8A0]
0x180012e6d  mov     [rsp+8D8h+var_888], rax
0x180012e72  lea     rcx, [rsp+8D8h+var_478]; this
0x180012e7a  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180012e7f  mov     rdx, [rsp+8D8h+var_468]; unsigned __int16 *
0x180012e87  mov     [rsp+8D8h+var_8A0], esi
0x180012e8b  mov     [rsp+8D8h+var_89C], esi
0x180012e8f  mov     [rsp+8D8h+var_898], 10h
0x180012e97  mov     [rsp+8D8h+lpMem], r15
0x180012e9c  lea     rcx, [rsp+8D8h+var_8A0]; this
0x180012ea1  call    ?Set@SString@@QEAAXPEBG@Z; SString::Set(ushort const *)
0x180012ea6  nop
0x180012ea7  lea     rdx, [rsp+8D8h+var_8A0]; struct SBuffer *
0x180012eac  lea     rcx, [rsp+8D8h+var_7B0]; this
0x180012eb4  call    ?Append@?$SArray@VSString@@$0A@@@QEAAXVSString@@@Z; SArray<SString,0>::Append(SString)
0x180012eb9  mov     dl, 1
0x180012ebb  lea     rcx, [rsp+8D8h+var_7D8]; this
  ... truncated ...
```
