# win_musl::consumption::ContainerSender::PartReceived(win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>)

- ea: `0x1800127c0`
- end: `0x180013541`
- name: `?PartReceived@ContainerSender@consumption@win_musl@@AEAAXV?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@Z`
- size: `3457`
- prototype: ``
- caller_count: `2`
- callee_count: `49`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18004d250`
- `0x180084c20`

## callees

- `0x180001de4`
- `0x180002f10`
- `0x180004680`
- `0x18000531c`
- `0x180011b14`
- `0x1800124f4`
- `0x1800127c0`
- `0x180013548`
- `0x1800136f4`
- `0x180014610`
- `0x1800147d0`
- `0x18001511c`
- `0x180015660`
- `0x180015778`
- `0x180017320`
- `0x1800190e0`
- `0x1800195ac`
- `0x18002b6c8`
- `0x18002bad0`
- `0x18002d8a0`
- `0x18002db70`
- `0x18002f58c`
- `0x1800315e4`
- `0x180034468`
- `0x180044944`
- `0x1800454b8`
- `0x180045f14`
- `0x18004829c`
- `0x180048a00`
- `0x180049a28`
- `0x18004aa18`
- `0x18004b830`
- `0x18004d3f8`
- `0x18004ea94`
- `0x180060c90`
- `0x180067770`
- `0x1800678f0`
- `0x18006f750`
- `0x180084010`
- `0x180085b84`
- `0x180085da8`
- `0x1800ab2a0`
- `0x1800cd1c4`
- `0x1800cd6fc`
- `0x1800cded0`
- `0x1800d6354`
- `0x1800e850c`
- `0x1801178f0`
- `0x18012a010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001291e`
- `msvcrt!memcpy_s` at `0x180012ad9`
- `msvcrt!memcpy_s` at `0x18001291e`
- `msvcrt!memcpy_s` at `0x180012ad9`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x180012edb`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x180012edb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001282f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001282f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012d2a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012d2a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001281c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001281c`

## string_xrefs

- `0x180012e6a`: `PartUri`
- `0x180012e32`: `Part has relationship content type, but its part Uri (%{PartUri}) is not a relationship Uri.`

## pseudocode

```c
// Hidden C++ exception states: #wind=41
void __fastcall win_musl::consumption::ContainerSender::PartReceived(__int64 a1, _QWORD *a2)
{
  char v4; // di
  __int64 v5; // rbx
  bool v6; // dl
  win_dox *v7; // rcx
  __int64 v8; // r12
  __int64 v9; // rax
  _QWORD *v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // rdi
  unsigned __int64 v13; // rsi
  _QWORD *v14; // r8
  void **v15; // rcx
  void **v16; // rcx
  __int64 *v17; // r9
  __int64 *v18; // rax
  void **v19; // r8
  unsigned __int64 v20; // rdx
  _QWORD *v21; // rcx
  bool v22; // cf
  __int64 ByteCollection; // r12
  __int64 v24; // rdi
  int v25; // r13d
  unsigned __int64 v26; // rdx
  unsigned __int64 v27; // rsi
  _QWORD *v28; // r8
  void **v29; // rcx
  void **v30; // rcx
  _WORD *v31; // rax
  unsigned __int64 v32; // r10
  unsigned __int64 v33; // rcx
  void **v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // rdx
  _QWORD *v37; // rax
  _BYTE *v38; // r12
  __int64 v39; // r14
  void (__fastcall *v40)(__int64, __int64 *, char *, _QWORD, __int64 *, __int64); // rsi
  __int64 v41; // rdi
  __int64 AbsoluteUri; // rax
  __int64 v44; // rax
  __int64 v45; // rdx
  __int64 v46; // rdi
  __int64 v47; // rbx
  win_musl::Formatter *v48; // rax
  const wchar_t *v49; // rax
  __int64 v50; // rcx
  void **v51; // rdx
  const wchar_t *v52; // r8
  _WORD *v53; // rax
  _WORD *v54; // rax
  __int64 ContainerPartReceiver; // rax
  _QWORD *v56; // rdi
  const char *v57; // rdx
  unsigned int v58; // r8d
  _QWORD *v59; // rdi
  __int64 v60; // rdi
  __int64 v61; // rax
  __int64 v62; // rsi
  __int64 v63; // rsi
  void (__fastcall *v64)(__int64, __int128 *); // rdi
  __int64 v65; // rax
  __int64 v66; // rax
  __int64 v67; // rdi
  __int64 v68; // rbx
  win_musl::Formatter *v69; // rax
  struct win_musl::TStringEllipseBase *v70; // rax
  __int64 v71; // rdi
  __int64 v72; // rbx
  __int64 v73; // rbx
  win_musl::Formatter *v74; // rax
  struct win_musl::TStringEllipseBase *v75; // rax
  __int64 v76; // rax
  __int64 v77; // rax
  __int64 v78; // rdx
  __int64 v79; // rax
  __int64 v80; // r10
  int v81; // r9d
  __int64 v82; // [rsp+48h] [rbp-C0h] BYREF
  _QWORD *v83; // [rsp+50h] [rbp-B8h] BYREF
  const char *v84; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v85; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v86; // [rsp+68h] [rbp-A0h]
  __int64 v87; // [rsp+70h] [rbp-98h]
  _BYTE *v88; // [rsp+78h] [rbp-90h] BYREF
  __int64 v89; // [rsp+80h] [rbp-88h]
  char v90[8]; // [rsp+88h] [rbp-80h] BYREF
  void *v91[2]; // [rsp+90h] [rbp-78h] BYREF
  unsigned __int64 v92; // [rsp+A0h] [rbp-68h]
  unsigned __int64 v93; // [rsp+A8h] [rbp-60h]
  __int64 v94; // [rsp+B0h] [rbp-58h]
  _QWORD *v95; // [rsp+B8h] [rbp-50h]
  __int64 v96; // [rsp+C0h] [rbp-48h]
  char v97[8]; // [rsp+C8h] [rbp-40h] BYREF
  void *Destination[2]; // [rsp+D0h] [rbp-38h] BYREF
  unsigned __int64 v99; // [rsp+E0h] [rbp-28h]
  unsigned __int64 v100; // [rsp+E8h] [rbp-20h]
  __int128 v101; // [rsp+F0h] [rbp-18h] BYREF
  __int64 v102; // [rsp+100h] [rbp-8h]
  __int64 v103; // [rsp+108h] [rbp+0h]
  _QWORD v104[5]; // [rsp+118h] [rbp+10h] BYREF
  char v105[8]; // [rsp+140h] [rbp+38h] BYREF
  void *Block; // [rsp+148h] [rbp+40h]
  __int64 v107; // [rsp+158h] [rbp+50h]
  unsigned __int64 v108; // [rsp+160h] [rbp+58h]
  _BYTE v109[48]; // [rsp+168h] [rbp+60h] BYREF
  _QWORD pExceptionObject[3]; // [rsp+198h] [rbp+90h] BYREF
  _DWORD v111[2]; // [rsp+1B0h] [rbp+A8h] BYREF
  const char *v112; // [rsp+1B8h] [rbp+B0h]
  char v113[56]; // [rsp+1C0h] [rbp+B8h] BYREF
  GUID v114; // [rsp+1F8h] [rbp+F0h]
  int v115; // [rsp+220h] [rbp+118h]
  _BYTE v116[48]; // [rsp+238h] [rbp+130h] BYREF
  _BYTE v117[96]; // [rsp+268h] [rbp+160h] BYREF
  _BYTE v118[160]; // [rsp+2C8h] [rbp+1C0h] BYREF

  v94 = -2;
  v95 = a2;
  v4 = 0;
  LODWORD(v82) = 0;
  v5 = a1 + 200;
  v96 = a1 + 200;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 200));
  v7 = (win_dox *)*(unsigned int *)(v5 + 44);
  *(_DWORD *)(v5 + 44) = (_DWORD)v7 + 1;
  if ( !(_DWORD)v7 )
    *(_DWORD *)(v5 + 40) = GetCurrentThreadId();
  LOBYTE(v7) = *(_BYTE *)(a1 + 256);
  win_dox::ThrowIfFailed(v7, v6);
  v8 = win_musl::InitOnceSingleton<win_musl::ContentType,win_musl::consumption::ContainerSender::RelationshipsContentTypeSingleton_tag>::Get<win_musl::consumption::ContainerSender::SingletonInitializer>();
  if ( *a2 && (v9 = a2[1]) != 0 )
  {
    v10 = (_QWORD *)(v9 + 8);
    if ( *(_QWORD *)(v9 + 32) >= 8u )
      v10 = (_QWORD *)*v10;
    win_dox::CreatePartUriInternal(&v85, v10);
    win_musl::MimeTable::FindContentType(a1 + 72, v105, &v85);
    if ( v107 )
    {
      win_musl::ContentTypeFromStdString(v118, v105);
      v12 = a2[1] + 40LL;
      v100 = 7;
      v99 = 0;
      LOWORD(Destination[0]) = 0;
      v13 = *(_QWORD *)(v12 + 24);
      if ( v97 == (char *)v12 )
      {
        std::wstring::erase(v97, *(_QWORD *)(v12 + 24), -1);
        std::wstring::erase(v97, 0, 0);
      }
      else
      {
        if ( v13 > 0x7FFFFFFFFFFFFFFELL )
          std::_String_base::_Xlen();
        if ( v100 < v13 )
        {
          std::wstring::_Copy(v97, *(_QWORD *)(v12 + 24), v99);
          if ( !v13 )
            goto LABEL_20;
        }
        else if ( !v13 )
        {
          v53 = (_WORD *)std::wstring::_Myptr(v97);
          v99 = 0;
          *v53 = 0;
          goto LABEL_20;
        }
        v14 = (_QWORD *)(v12 + 8);
        if ( *(_QWORD *)(v12 + 32) >= 8u )
          v14 = (_QWORD *)*v14;
        v15 = Destination;
        if ( v100 >= 8 )
          v15 = (void **)Destination[0];
        memcpy_s(v15, 2 * v100, v14, 2 * v13);
        v16 = Destination;
        if ( v100 >= 8 )
          v16 = (void **)Destination[0];
        v99 = v13;
        *((_WORD *)v16 + v13) = 0;
      }
LABEL_20:
      v17 = *(__int64 **)(a1 + 160);
      v18 = (__int64 *)v17[1];
      while ( !*((_BYTE *)v18 + 65) )
      {
        v19 = Destination;
        if ( v100 >= 8 )
          v19 = (void **)Destination[0];
        v20 = v99;
        if ( v18[6] < v99 )
          v20 = v18[6];
        v21 = v18 + 4;
        if ( (unsigned __int64)v18[7] >= 8 )
          v21 = (_QWORD *)*v21;
        while ( v20 )
        {
          v22 = *(_WORD *)v21 < *(_WORD *)v19;
          if ( *(_WORD *)v21 != *(_WORD *)v19 )
            goto LABEL_30;
          v21 = (_QWORD *)((char *)v21 + 2);
          v19 = (void **)((char *)v19 + 2);
          --v20;
        }
        v22 = v18[6] < v99;
LABEL_30:
        if ( v22 )
        {
          v18 = (__int64 *)v18[2];
        }
        else
        {
          v17 = v18;
          v18 = (__int64 *)*v18;
        }
      }
      if ( v17 != *(__int64 **)(a1 + 160) )
      {
        v31 = (_WORD *)std::wstring::_Myptr(v17 + 3);
        v33 = v32;
        if ( v99 < v32 )
          v33 = v99;
        v34 = Destination;
        if ( v100 >= 8 )
          v34 = (void **)Destination[0];
        while ( v33 )
        {
          if ( *(_WORD *)v34 != *v31 )
          {
            if ( *(_WORD *)v34 < *v31 )
              goto LABEL_34;
            goto LABEL_93;
          }
          v34 = (void **)((char *)v34 + 2);
          ++v31;
          --v33;
        }
        if ( v99 < v32 )
          goto LABEL_34;
LABEL_93:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0 )
        {
          AbsoluteUri = win_dox::Uri::GetAbsoluteUri(&v85, v104);
          v44 = std::wstring::_Myptr(AbsoluteUri);
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, WPP_26ae4a55cde332a86a17bdc34ef7b6d8_Traceguids, v44);
          LOBYTE(v45) = 1;
          std::wstring::_Tidy(v104, v45, 0);
        }
        goto LABEL_76;
      }
LABEL_34:
      if ( (unsigned __int8)win_musl::DetectPrefixCollision(v97, a1 + 152) )
      {
        std::wstring::wstring(v104, L"Part %{Part} has a prefix collision");
        v67 = win_musl::Formatter::Formatter(v117, v104);
        v68 = win_dox::Uri::GetAbsoluteUri(&v85, &v101);
        std::wstring::wstring(v109, L"Part");
        v69 = (win_musl::Formatter *)win_musl::Formatter::insert<std::wstring>(v67, v109, v68);
        v70 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v69);
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::TSystemException *)pExceptionObject,
          0x11Du,
          0x80510004,
          v70);
        throw (SplException::THResultException *)pExceptionObject;
      }
      if ( win_dox::OpcPartUri::IsRelationshipsPartUri((win_dox::OpcPartUri *)&v85) )
      {
        if ( !(unsigned __int8)operator==(v118, v8) )
        {
          std::wstring::wstring(
            v104,
            L"Relationship part %{RelsPart} has non-relationship content type: %{ContentType}");
          v71 = win_musl::Formatter::Formatter(v117, v104);
          v72 = win_dox::Uri::GetAbsoluteUri(&v85, v116);
          std::wstring::wstring(v109, L"RelsPart");
          v73 = win_musl::Formatter::insert<std::wstring>(v71, v109, v72);
          std::wstring::wstring(&v101, L"ContentType");
          v74 = (win_musl::Formatter *)win_musl::Formatter::insert<std::wstring>(v73, &v101, v105);
          v75 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v74);
          win_musl::detail::ThrowBuilder<SplException::THResultException>(
            (SplException::TSystemException *)pExceptionObject,
            0x129u,
            0x80510005,
            v75);
          throw (SplException::THResultException *)pExceptionObject;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0 )
        {
          v76 = win_dox::Uri::GetAbsoluteUri(&v85, v104);
          v77 = std::wstring::_Myptr(v76);
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 12, WPP_26ae4a55cde332a86a17bdc34ef7b6d8_Traceguids, v77);
          LOBYTE(v78) = 1;
          std::wstring::_Tidy(v104, v78, 0);
        }
        v50 = 12;
        if ( v99 < 0xC )
          v50 = v99;
        v51 = Destination;
        if ( v100 >= 8 )
          v51 = (void **)Destination[0];
        v52 = L"/_RELS/.RELS";
        while ( v50 )
        {
          if ( *(_WORD *)v51 != *v52 )
            goto LABEL_76;
          v51 = (void **)((char *)v51 + 2);
          ++v52;
          --v50;
        }
        if ( v99 == 12 )
        {
          v63 = *(_QWORD *)(win_musl::consumption::MetroConsumptionState::GetContainerPartReceiver(*(_QWORD *)(a1 + 64))
                          + 8);
          v64 = *(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v63 + 40LL);
          win_dox::ByteCollection::ByteCollection(
            (win_dox::ByteCollection *)&v101,
            (const struct win_dox::ByteCollection *)(a2[1] + 88LL));
          v64(v63, &v101);
          *(_QWORD *)&v101 = &win_dox::OpcRelationshipSender::`vftable';
          v62 = 0;
          if ( *((_QWORD *)&v101 + 1) )
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v101 + 1) + 16LL))(*((_QWORD *)&v101 + 1));
          std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert(
            a1 + 152,
            v109,
            v97);
          ContainerPartReceiver = win_musl::consumption::MetroConsumptionState::GetContainerPartReceiver(*(_QWORD *)(a1 + 64));
          if ( (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(ContainerPartReceiver + 8) + 48LL))(*(_QWORD *)(ContainerPartReceiver + 8)) == 2 )
          {
            win_musl::consumption::MetroConsumptionState::IncrementOutstandingWork(*(win_musl::consumption::MetroConsumptionState **)(a1 + 64));
            v56 = (_QWORD *)win_scope::scope<IWin7InternalPartSender *,win_scope::const_policies<win_scope::com_policies>>::scope<IWin7InternalPartSender *,win_scope::const_policies<win_scope::com_policies>>(
                              &v84,
                              a1);
            v83 = v56;
            win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>(
              v104,
              v56);
            v104[1] = win_musl::consumption::ContainerSender::RootRelationshipFiber;
            v104[2] = 0;
            v104[3] = 0;
            if ( *v56 )
            {
              win_scope::close_com::close<win_musl::consumption::ContainerSender * *>(v56);
              *v56 = 0;
            }
            v59 = operator new(0x70u, v57, v58);
            v83 = v59;
            if ( v59 )
            {
              win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>(
                &v101,
                v104);
              *((_QWORD *)&v101 + 1) = win_musl::consumption::ContainerSender::RootRelationshipFiber;
              v102 = 0;
              v103 = 0;
              win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>(
                &v82,
                *(_QWORD *)(a1 + 64) + 32LL);
              v62 = win_musl::UnknownOnly<win_musl::FiberStream<win_musl::FiberStreamClient<win_musl::consumption::ContainerSender,win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>>>,win_mp_lib::null_type,win_mp_lib::null_type>::UnknownOnly<win_musl::FiberStream<win_musl::FiberStreamClient<win_musl::consumption::ContainerSender,win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>>>,win_mp_lib::null_type,win_mp_lib::null_type>(
                      (__int64)v59,
                      &v82,
                      &v101);
            }
            v60 = 0;
            v83 = 0;
            if ( v62 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 8LL))(v62);
              v60 = v62;
              v83 = (_QWORD *)v62;
            }
            win_musl::FiberStream<win_musl::FiberStreamClient<win_musl::consumption::ContainerSender,win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>>>::GetByteReceiver(
              v60,
              v109);
            win_dox::ByteCollection::ByteCollection(
              (win_dox::ByteCollection *)&v88,
              (const struct win_dox::ByteCollection *)(a2[1] + 88LL));
            v61 = win_dox::CreateSenderBase<IByteCollection>::CreateSender(&v88, &v101);
            win_dox::StartSendBase<IByteSender>::StartSend<win_dox::ByteReceiver>(v61, v109);
            *(_QWORD *)&v101 = &win_dox::OpcRelationshipSender::`vftable';
            if ( *((_QWORD *)&v101 + 1) )
            {
              (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v101 + 1) + 16LL))(*((_QWORD *)&v101 + 1));
              *((_QWORD *)&v101 + 1) = 0;
            }
            if ( v89 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v89 + 16LL))(v89);
            win_dox::ByteReceiver::~ByteReceiver((win_dox::ByteReceiver *)v109);
            if ( v60 )
              win_scope::close_com::close<win_musl::consumption::ContainerSender * *>(&v83);
            if ( v104[0] )
              win_scope::close_com::close<win_musl::consumption::ContainerSender * *>(v104);
          }
        }
        goto LABEL_76;
      }
      if ( (unsigned __int8)operator==(v118, v8) )
      {
        std::wstring::wstring(
          v104,
          L"Part has relationship content type, but its part Uri (%{PartUri}) is not a relationship Uri.");
        v46 = win_musl::Formatter::Formatter(v117, v104);
        v47 = win_dox::Uri::GetAbsoluteUri(&v85, v116);
        std::wstring::wstring(v109, L"PartUri");
        v48 = (win_musl::Formatter *)win_musl::Formatter::insert<std::wstring>(v46, v109, v47);
        v49 = win_musl::Formatter::c_str(v48);
        win_musl::DebugLogHelper("(no filename)", &word_180139126, 352, 1024, -2142175227, v49);
        v84 = "Unexpected HRESULT returned by API";
        exception::exception((exception *)pExceptionObject, &v84);
        memset_0(v113, 0, 0x68u);
        v112 = "(no filename)";
        v111[1] = 352;
        v115 = -1;
        pExceptionObject[0] = &SplException::THResultException::`vftable';
        v111[0] = -2142175227;
        v114 = GUID_NULL;
        if ( SplException::Functions )
          v115 = SplException::Functions(v111);
        throw (SplException::THResultException *)pExceptionObject;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0 )
      {
        std::wstring::_Myptr(a2[1]);
        v79 = std::wstring::_Myptr(v105);
        WPP_SF_SS(*(_QWORD *)(v80 + 56), 13, (unsigned int)WPP_26ae4a55cde332a86a17bdc34ef7b6d8_Traceguids, v81, v79);
      }
      std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert(
        a1 + 152,
        v109,
        v97);
      v88 = v109;
      ByteCollection = win_musl::consumption::MetroConsumptionState::ByteCollectionHolder::GetByteCollection(
                         a2[1],
                         v109);
      v24 = a2[1];
      v25 = *(_DWORD *)(v24 + 80);
      v84 = v90;
      v26 = 7;
      v93 = 7;
      v92 = 0;
      LOWORD(v91[0]) = 0;
      v27 = *(_QWORD *)(v24 + 24);
      if ( v90 == (char *)v24 )
      {
        std::wstring::erase(v90, *(_QWORD *)(v24 + 24), -1);
        std::wstring::erase(v90, 0, 0);
      }
      else
      {
        if ( v27 > 0x7FFFFFFFFFFFFFFELL )
          std::_String_base::_Xlen();
        if ( v27 > 7 )
        {
          std::wstring::_Copy(v90, *(_QWORD *)(v24 + 24), 0);
          v26 = v93;
          goto LABEL_44;
        }
        if ( v27 )
        {
LABEL_44:
          v28 = (_QWORD *)(v24 + 8);
          if ( *(_QWORD *)(v24 + 32) >= 8u )
            v28 = (_QWORD *)*v28;
          v29 = v91;
          if ( v26 >= 8 )
            v29 = (void **)v91[0];
          memcpy_s(v29, 2 * v26, v28, 2 * v27);
          v30 = v91;
          if ( v93 >= 8 )
            v30 = (void **)v91[0];
          v92 = v27;
          *((_WORD *)v30 + v27) = 0;
          goto LABEL_66;
        }
        v54 = (_WORD *)std::wstring::_Myptr(v90);
        v92 = 0;
        *v54 = 0;
      }
LABEL_66:
      v101 = 0;
      v35 = *(_QWORD *)(a1 + 56);
      if ( v35 )
      {
        v36 = *(_QWORD *)(a1 + 64);
        if ( _InterlockedIncrement((volatile signed __int32 *)(v35 + 8)) == 1 )
          _InterlockedIncrement((volatile signed __int32 *)(v35 + 12));
        *(_QWORD *)&v101 = v35;
        *((_QWORD *)&v101 + 1) = v36;
      }
      v37 = (_QWORD *)win_musl::UnknownOnly<win_musl::consumption::ContainerPartSender,win_mp_lib::null_type,win_mp_lib::null_type>::CreateInstance<win_scope::scope<win_musl::consumption::MetroConsumptionState *,win_scope::const_policies<win_scope::shared_policies>>,std::wstring,enum __MIDL___MIDL_itf_opc2Eio_0000_0000_0002,win_dox::ByteCollection>(
                        (unsigned int)&v83,
                        (unsigned int)&v101,
                        (unsigned int)v90,
                        v25,
                        ByteCollection);
      v38 = (_BYTE *)*v37;
      if ( *v37 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v38 + 8LL))(*v37);
      v88 = v38;
      if ( v83 )
      {
        (*(void (__fastcall **)(_QWORD *))(*v83 + 16LL))(v83);
        v83 = 0;
      }
      v39 = *(_QWORD *)(win_musl::consumption::MetroConsumptionState::GetContainerPartReceiver(*(_QWORD *)(a1 + 64)) + 8);
      v40 = *(void (__fastcall **)(__int64, __int64 *, char *, _QWORD, __int64 *, __int64))(*(_QWORD *)v39 + 8LL);
      v41 = a2[1] + 104LL;
      v82 = 0;
      win_scope::detail::scope_helper<win_musl::ByteReceiverUnique<win_musl::consumption::ZipLocalConsumer,1,IUnknown> *,win_scope::const_policies<win_scope::types_6<win_scope::close_com,win_scope::convert_normal,win_scope::acquire_com,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::safe_types_com>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::reset(
        &v82,
        v38);
      v40(v39, &v85, v105, *(unsigned int *)(a2[1] + 80LL), &v82, v41);
      if ( v38 )
        (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v38 + 16LL))(v38);
LABEL_76:
      if ( v100 >= 8 )
        operator delete(Destination[0]);
      v100 = 7;
      v99 = 0;
      LOWORD(Destination[0]) = 0;
      win_musl::ContentType::~ContentType((win_musl::ContentType *)v118);
      if ( v108 >= 8 )
        operator delete(Block);
      v108 = 7;
      v107 = 0;
      LOWORD(Block) = 0;
      if ( v87 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v87 + 16LL))(v87);
        v87 = 0;
      }
      if ( v86 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v86 + 16LL))(v86);
        v86 = 0;
      }
      if ( v85 )
      {
        win_scope::close_com::close<win_musl::consumption::ContainerSender * *>(&v85);
        v85 = 0;
      }
      if ( (*(_DWORD *)(v5 + 44))-- == 1 )
        *(_DWORD *)(v5 + 40) = 0;
      LeaveCriticalSection((LPCRITICAL_SECTION)v5);
      if ( *a2 )
      {
        if ( a2[1] )
        {
          win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)a2);
          *a2 = 0;
          a2[1] = 0;
        }
      }
      return;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0 )
    {
      v65 = win_dox::Uri::GetAbsoluteUri(&v85, v104);
      v4 = 1;
      v66 = std::wstring::_Myptr(v65);
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 10, WPP_26ae4a55cde332a86a17bdc34ef7b6d8_Traceguids, v66);
    }
    if ( (v4 & 1) != 0 )
    {
      LOBYTE(v11) = 1;
      std::wstring::_Tidy(v104, v11, 0);
    }
    if ( v108 >= 8 )
      operator delete(Block);
    v108 = 7;
    v107 = 0;
    LOWORD(Block) = 0;
    win_dox::OpcPartUri::~OpcPartUri((win_dox::OpcPartUri *)&v85);
    win_musl::CriticalSection::Leave((win_musl::CriticalSection *)v5);
  }
  else
  {
    win_musl::consumption::MetroConsumptionState::TestClose(*(win_musl::consumption::MetroConsumptionState **)(a1 + 64));
    win_musl::CriticalSection::Leave((win_musl::CriticalSection *)v5);
  }
  if ( *a2 && a2[1] )
  {
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)a2);
    *a2 = 0;
    a2[1] = 0;
  }
}

```

## disassembly

```asm
0x1800127c0  mov     rax, rsp
0x1800127c3  push    rbp
0x1800127c4  push    rsi
0x1800127c5  push    rdi
0x1800127c6  push    r12
0x1800127c8  push    r13
0x1800127ca  push    r14
0x1800127cc  push    r15
0x1800127ce  lea     rbp, [rax-2A8h]
0x1800127d5  sub     rsp, 370h
0x1800127dc  mov     [rbp+2A0h+var_2F8], 0FFFFFFFFFFFFFFFEh
0x1800127e4  mov     [rax+18h], rbx
0x1800127e8  mov     rax, cs:__security_cookie
0x1800127ef  xor     rax, rsp
0x1800127f2  mov     [rbp+2A0h+var_40], rax
0x1800127f9  mov     r15, rdx
0x1800127fc  mov     r14, rcx
0x1800127ff  mov     [rbp+2A0h+var_2F0], rdx
0x180012803  xor     r13d, r13d
0x180012806  mov     edi, r13d
0x180012809  mov     dword ptr [rsp+3A0h+var_360], r13d
0x18001280e  lea     rbx, [rcx+0C8h]
0x180012815  mov     [rbp+2A0h+var_2E8], rbx
0x180012819  mov     rcx, rbx; lpCriticalSection
0x18001281c  call    cs:__imp_EnterCriticalSection
0x180012822  mov     ecx, [rbx+2Ch]
0x180012825  lea     eax, [rcx+1]
0x180012828  mov     [rbx+2Ch], eax
0x18001282b  test    ecx, ecx
0x18001282d  jnz     short loc_180012838
0x18001282f  call    cs:__imp_GetCurrentThreadId
0x180012835  mov     [rbx+28h], eax
0x180012838  mov     cl, [r14+100h]; this
0x18001283f  call    ?ThrowIfFailed@win_dox@@YAX_N@Z; win_dox::ThrowIfFailed(bool)
0x180012844  call    ??$Get@VSingletonInitializer@ContainerSender@consumption@win_musl@@@?$InitOnceSingleton@UContentType@win_musl@@URelationshipsContentTypeSingleton_tag@ContainerSender@consumption@2@@win_musl@@SAPEAUContentType@1@VSingletonInitializer@ContainerSender@consumption@1@@Z; win_musl::InitOnceSingleton<win_musl::ContentType,win_musl::consumption::ContainerSender::RelationshipsContentTypeSingleton_tag>::Get<win_musl::consumption::ContainerSender::SingletonInitializer>(win_musl::consumption::ContainerSender::SingletonInitializer)
0x180012849  mov     r12, rax
0x18001284c  cmp     [r15], r13
0x18001284f  jz      loc_180012B05
0x180012855  mov     rax, [r15+8]
0x180012859  test    rax, rax
0x18001285c  jz      loc_180012B05
0x180012862  lea     rdx, [rax+8]
0x180012866  cmp     qword ptr [rax+20h], 8
0x18001286b  jb      short loc_180012870
0x18001286d  mov     rdx, [rdx]
0x180012870  lea     rcx, [rsp+3A0h+var_348]
0x180012875  call    ?CreatePartUriInternal@win_dox@@YA?AVOpcPartUri@1@PEB_W@Z; win_dox::CreatePartUriInternal(wchar_t const *)
0x18001287a  nop
0x18001287b  lea     rcx, [r14+48h]
0x18001287f  lea     r8, [rsp+3A0h+var_348]
0x180012884  lea     rdx, [rbp+2A0h+var_268]
0x180012888  call    ?FindContentType@MimeTable@win_musl@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@AEBVOpcPartUri@win_dox@@@Z; win_musl::MimeTable::FindContentType(win_dox::OpcPartUri const &)
0x18001288d  nop
0x18001288e  cmp     [rbp+2A0h+var_250], r13
0x180012892  jz      loc_180012F63
0x180012898  lea     rdx, [rbp+2A0h+var_268]
0x18001289c  lea     rcx, [rbp+2A0h+var_E0]
0x1800128a3  call    ?ContentTypeFromStdString@win_musl@@YA?AUContentType@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@J@Z; win_musl::ContentTypeFromStdString(std::wstring const &,long)
0x1800128a8  nop
0x1800128a9  mov     rdi, [r15+8]
0x1800128ad  add     rdi, 28h ; '('
0x1800128b1  mov     [rbp+2A0h+var_2C0], 7
0x1800128b9  mov     [rbp+2A0h+var_2C8], r13
0x1800128bd  mov     word ptr [rbp+2A0h+Destination], r13w
0x1800128c2  mov     rsi, [rdi+18h]
0x1800128c6  lea     rax, [rbp+2A0h+var_2E0]
0x1800128ca  mov     rcx, 7FFFFFFFFFFFFFFEh
0x1800128d4  cmp     rax, rdi
0x1800128d7  jz      loc_1800132F5
0x1800128dd  cmp     rsi, rcx
0x1800128e0  ja      loc_180013318
0x1800128e6  cmp     [rbp+2A0h+var_2C0], rsi
0x1800128ea  jb      short loc_18001293E
0x1800128ec  test    rsi, rsi
0x1800128ef  jz      loc_180013031
0x1800128f5  lea     r8, [rdi+8]
0x1800128f9  cmp     qword ptr [rdi+20h], 8
0x1800128fe  jb      short loc_180012903
0x180012900  mov     r8, [r8]; Source
0x180012903  mov     rdx, [rbp+2A0h+var_2C0]
0x180012907  lea     rcx, [rbp+2A0h+Destination]
0x18001290b  cmp     rdx, 8
0x18001290f  cmovnb  rcx, [rbp+2A0h+Destination]; Destination
0x180012914  lea     rdi, [rsi+rsi]
0x180012918  add     rdx, rdx; DestinationSize
0x18001291b  mov     r9, rdi; SourceSize
0x18001291e  call    cs:__imp_memcpy_s
0x180012924  lea     rcx, [rbp+2A0h+Destination]
0x180012928  cmp     [rbp+2A0h+var_2C0], 8
0x18001292d  cmovnb  rcx, [rbp+2A0h+Destination]
0x180012932  mov     [rbp+2A0h+var_2C8], rsi
0x180012936  xor     esi, esi
0x180012938  mov     [rdi+rcx], si
0x18001293c  jmp     short loc_180012955
0x18001293e  mov     r8, [rbp+2A0h+var_2C8]
0x180012942  mov     rdx, rsi
0x180012945  lea     rcx, [rbp+2A0h+var_2E0]
0x180012949  call    ?_Copy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x18001294e  test    rsi, rsi
0x180012951  jnz     short loc_1800128F5
0x180012953  xor     esi, esi
0x180012955  lea     r13, [r14+98h]
0x18001295c  mov     r9, [r13+8]
0x180012960  mov     rax, [r9+8]
0x180012964  cmp     [rax+41h], sil
0x180012968  jnz     short loc_1800129C8
0x18001296a  mov     rdi, [rbp+2A0h+var_2C8]
0x18001296e  lea     r8, [rbp+2A0h+Destination]
0x180012972  cmp     [rbp+2A0h+var_2C0], 8
0x180012977  cmovnb  r8, [rbp+2A0h+Destination]
0x18001297c  mov     rdx, rdi
0x18001297f  cmp     [rax+30h], rdi
0x180012983  cmovb   rdx, [rax+30h]
0x180012988  lea     rcx, [rax+20h]
0x18001298c  cmp     qword ptr [rax+38h], 8
0x180012991  jb      short loc_180012996
0x180012993  mov     rcx, [rcx]
0x180012996  test    rdx, rdx
0x180012999  jz      loc_180013322
0x18001299f  movzx   r10d, word ptr [rcx]
0x1800129a3  cmp     r10w, [r8]
0x1800129a7  jnz     short loc_1800129B6
0x1800129a9  add     rcx, 2
0x1800129ad  add     r8, 2
0x1800129b1  dec     rdx
0x1800129b4  jmp     short loc_180012996
0x1800129b6  jb      loc_180012AFC
0x1800129bc  mov     r9, rax
0x1800129bf  mov     rax, [rax]
0x1800129c2  cmp     [rax+41h], sil
0x1800129c6  jz      short loc_18001296E
0x1800129c8  cmp     r9, [r14+0A0h]
0x1800129cf  jnz     loc_180012B3F
0x1800129d5  mov     rdx, r13
0x1800129d8  lea     rcx, [rbp+2A0h+var_2E0]
0x1800129dc  call    ?DetectPrefixCollision@win_musl@@YA_NAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@AEAV?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@2@@3@@Z; win_musl::DetectPrefixCollision(std::wstring &,std::set<std::wstring> &)
0x1800129e1  test    al, al
0x1800129e3  jnz     loc_18001332B
0x1800129e9  lea     rcx, [rsp+3A0h+var_348]; this
0x1800129ee  call    ?IsRelationshipsPartUri@OpcPartUri@win_dox@@QEBA_NXZ; win_dox::OpcPartUri::IsRelationshipsPartUri(void)
0x1800129f3  mov     rdx, r12
0x1800129f6  lea     rcx, [rbp+2A0h+var_E0]
0x1800129fd  test    al, al
0x1800129ff  jnz     loc_180012FB9
0x180012a05  call    ??8@YA_NAEBUContentType@win_musl@@0@Z; operator==(win_musl::ContentType const &,win_musl::ContentType const &)
0x180012a0a  test    al, al
0x180012a0c  jnz     loc_180012E32
0x180012a12  lea     rax, WPP_GLOBAL_Control
0x180012a19  mov     r10, cs:WPP_GLOBAL_Control
0x180012a20  cmp     r10, rax
0x180012a23  jz      short loc_180012A30
0x180012a25  test    byte ptr [r10+44h], 4
0x180012a2a  jnz     loc_1800134D7
0x180012a30  lea     r8, [rbp+2A0h+var_2E0]
0x180012a34  lea     rdx, [rbp+2A0h+var_240]
0x180012a38  mov     rcx, r13
0x180012a3b  call    ?insert@?$_Tree@V?$_Tset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@Viterator@?$_Tree@V?$_Tset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@2@$0A@@std@@@std@@_N@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@2@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert(std::wstring const &)
0x180012a40  lea     rax, [rbp+2A0h+var_240]
0x180012a44  mov     [rsp+3A0h+var_330], rax
0x180012a49  lea     rdx, [rbp+2A0h+var_240]
0x180012a4d  mov     rcx, [r15+8]
0x180012a51  call    ?GetByteCollection@ByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@QEBA?AVByteCollection@win_dox@@XZ; win_musl::consumption::MetroConsumptionState::ByteCollectionHolder::GetByteCollection(void)
0x180012a56  mov     r12, rax
0x180012a59  mov     rdi, [r15+8]
0x180012a5d  mov     r13d, [rdi+50h]
0x180012a61  lea     rax, [rbp+2A0h+var_320]
0x180012a65  mov     [rsp+3A0h+var_350], rax
0x180012a6a  mov     edx, 7
0x180012a6f  mov     [rbp+2A0h+var_300], rdx
0x180012a73  mov     r8, rsi
0x180012a76  mov     [rbp+2A0h+var_308], rsi
0x180012a7a  mov     word ptr [rbp+2A0h+var_318], si
0x180012a7e  mov     rsi, [rdi+18h]
0x180012a82  lea     rax, [rbp+2A0h+var_320]
0x180012a86  cmp     rax, rdi
0x180012a89  jz      loc_18001350B
0x180012a8f  mov     rax, 7FFFFFFFFFFFFFFEh
0x180012a99  cmp     rsi, rax
0x180012a9c  ja      loc_18001352E
0x180012aa2  cmp     rdx, rsi
0x180012aa5  jb      loc_180012B93
0x180012aab  test    rsi, rsi
0x180012aae  jz      loc_180013056
0x180012ab4  lea     r8, [rdi+8]
0x180012ab8  cmp     qword ptr [rdi+20h], 8
0x180012abd  jb      short loc_180012AC2
0x180012abf  mov     r8, [r8]; Source
0x180012ac2  lea     rcx, [rbp+2A0h+var_318]
0x180012ac6  cmp     rdx, 8
0x180012aca  cmovnb  rcx, [rbp+2A0h+var_318]; Destination
0x180012acf  lea     rdi, [rsi+rsi]
0x180012ad3  add     rdx, rdx; DestinationSize
0x180012ad6  mov     r9, rdi; SourceSize
0x180012ad9  call    cs:__imp_memcpy_s
0x180012adf  lea     rcx, [rbp+2A0h+var_318]
0x180012ae3  cmp     [rbp+2A0h+var_300], 8
0x180012ae8  cmovnb  rcx, [rbp+2A0h+var_318]
0x180012aed  mov     [rbp+2A0h+var_308], rsi
0x180012af1  xor     eax, eax
0x180012af3  mov     [rdi+rcx], ax
0x180012af7  jmp     loc_180012BAC
0x180012afc  mov     rax, [rax+10h]
0x180012b00  jmp     loc_1800129C2
0x180012b05  mov     rcx, [r14+40h]; this
0x180012b09  call    ?TestClose@MetroConsumptionState@consumption@win_musl@@QEAAXXZ; win_musl::consumption::MetroConsumptionState::TestClose(void)
0x180012b0e  nop
0x180012b0f  mov     rcx, rbx; this
0x180012b12  call    ?Leave@CriticalSection@win_musl@@QEAAXXZ; win_musl::CriticalSection::Leave(void)
0x180012b17  nop
0x180012b18  cmp     [r15], r13
0x180012b1b  jz      loc_180012D4B
0x180012b21  cmp     [r15+8], r13
0x180012b25  jz      loc_180012D4B
0x180012b2b  mov     rcx, r15
0x180012b2e  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x180012b33  mov     [r15], r13
0x180012b36  mov     [r15+8], r13
0x180012b3a  jmp     loc_180012D4B
0x180012b3f  lea     rcx, [r9+18h]
0x180012b43  mov     r10, [rcx+18h]
0x180012b47  call    ?_Myptr@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEBAPEB_WXZ; std::wstring::_Myptr(void)
0x180012b4c  mov     r11, [rbp+2A0h+var_2C8]
0x180012b50  mov     rcx, r10
0x180012b53  cmp     r11, r10
0x180012b56  cmovb   rcx, r11
0x180012b5a  lea     rdx, [rbp+2A0h+Destination]
0x180012b5e  cmp     [rbp+2A0h+var_2C0], 8
0x180012b63  cmovnb  rdx, [rbp+2A0h+Destination]
0x180012b68  test    rcx, rcx
0x180012b6b  jz      loc_180012DC0
0x180012b71  movzx   r8d, word ptr [rdx]
0x180012b75  cmp     r8w, [rax]
0x180012b79  jnz     short loc_180012B88
0x180012b7b  add     rdx, 2
0x180012b7f  add     rax, 2
0x180012b83  dec     rcx
0x180012b86  jmp     short loc_180012B68
0x180012b88  jb      loc_1800129D5
0x180012b8e  jmp     loc_180012DC9
0x180012b93  mov     rdx, rsi
0x180012b96  lea     rcx, [rbp+2A0h+var_320]
0x180012b9a  call    ?_Copy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x180012b9f  mov     rdx, [rbp+2A0h+var_300]
0x180012ba3  test    rsi, rsi
0x180012ba6  jnz     loc_180012AB4
0x180012bac  xorps   xmm0, xmm0
0x180012baf  movdqu  [rbp+2A0h+var_2B8], xmm0
0x180012bb4  mov     rcx, [r14+38h]
0x180012bb8  test    rcx, rcx
0x180012bbb  jz      short loc_180012BDE
0x180012bbd  mov     rdx, [r14+40h]
0x180012bc1  mov     eax, 1
0x180012bc6  lock xadd [rcx+8], eax
0x180012bcb  inc     eax
0x180012bcd  cmp     eax, 1
0x180012bd0  jz      loc_180012DB7
0x180012bd6  mov     qword ptr [rbp+2A0h+var_2B8], rcx
0x180012bda  mov     qword ptr [rbp+2A0h+var_2B8+8], rdx
0x180012bde  mov     qword ptr [rsp+3A0h+var_380], r12
0x180012be3  mov     r9d, r13d
0x180012be6  lea     r8, [rbp+2A0h+var_320]
0x180012bea  lea     rdx, [rbp+2A0h+var_2B8]
0x180012bee  lea     rcx, [rsp+3A0h+var_358]
0x180012bf3  call    ??$CreateInstance@V?$scope@PEAVMetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@W4__MIDL___MIDL_itf_opc2Eio_0000_0000_0002@@VByteCollection@win_dox@@@?$UnknownOnly@VContainerPartSender@consumption@win_musl@@Vnull_type@win_mp_lib@@V45@@win_musl@@SA?AV?$scope@PEAV?$UnknownOnly@VContainerPartSender@consumption@win_musl@@Vnull_type@win_mp_lib@@V45@@win_musl@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVMetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@3@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@W4__MIDL___MIDL_itf_opc2Eio_0000_0000_0002@@VByteCollection@win_dox@@@Z; win_musl::UnknownOnly<win_musl::consumption::ContainerPartSender,win_mp_lib::null_type,win_mp_lib::null_type>::CreateInstance<win_scope::scope<win_musl::consumption::MetroConsumptionState *,win_scope::const_policies<win_scope::shared_policies>>,std::wstring,__MIDL___MIDL_itf_opc2Eio_0000_0000_0002,win_dox::ByteCollection>(win_scope::scope<win_musl::consumption::MetroConsumptionState *,win_scope::const_policies<win_scope::shared_policies>>,std::wstring,__MIDL___MIDL_itf_opc2Eio_0000_0000_0002,win_dox::ByteCollection)
0x180012bf8  nop
0x180012bf9  mov     r12, [rax]
0x180012bfc  test    r12, r12
0x180012bff  jz      short loc_180012C11
0x180012c01  mov     rax, [r12]
0x180012c05  mov     rcx, r12
0x180012c08  mov     rax, [rax+8]
0x180012c0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c11  mov     [rsp+3A0h+var_330], r12
0x180012c16  mov     rcx, [rsp+3A0h+var_358]
0x180012c1b  test    rcx, rcx
0x180012c1e  jz      short loc_180012C35
0x180012c20  mov     rax, [rcx]
0x180012c23  mov     rax, [rax+10h]
0x180012c27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c2c  mov     [rsp+3A0h+var_358], 0
0x180012c35  mov     rcx, [r14+40h]
0x180012c39  call    ?GetContainerPartReceiver@MetroConsumptionState@consumption@win_musl@@QEAAAEAV?$scope@PEAVOpcPackageReceiver@win_dox@@U?$const_policies@U?$types_1@U?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@XZ; win_musl::consumption::MetroConsumptionState::GetContainerPartReceiver(void)
0x180012c3e  mov     r14, [rax+8]
0x180012c42  mov     rax, [r14]
0x180012c45  mov     rsi, [rax+8]
0x180012c49  mov     rdi, [r15+8]
0x180012c4d  add     rdi, 68h ; 'h'
0x180012c51  mov     [rsp+3A0h+var_360], 0
0x180012c5a  mov     rdx, r12
0x180012c5d  lea     rcx, [rsp+3A0h+var_360]
0x180012c62  call    ?reset@?$scope_helper@PEAV?$ByteReceiverUnique@VZipLocalConsumer@consumption@win_musl@@$00UIUnknown@@@win_musl@@U?$const_policies@U?$types_6@Uclose_com@win_scope@@Uconvert_normal@2@Uacquire_com@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Usafe_types_com@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@detail@win_scope@@SAXAEAV?$scope@PEAV?$ByteReceiverUnique@VZipLocalConsumer@consumption@win_musl@@$00UIUnknown@@@win_musl@@U?$const_policies@U?$types_6@Uclose_com@win_scope@@Uconvert_normal@2@Uacquire_com@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Usafe_types_com@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@3@PEAV?$ByteReceiverUnique@VZipLocalConsumer@consumption@win_musl@@$00UIUnknown@@@win_musl@@@Z; win_scope::detail::scope_helper<win_musl::ByteReceiverUnique<win_musl::consumption::ZipLocalConsumer,1,IUnknown> *,win_scope::const_policies<win_scope::types_6<win_scope::close_com,win_scope::convert_normal,win_scope::acquire_com,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::safe_types_com>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::reset(win_scope::scope<win_musl::ByteReceiverUnique<win_musl::consumption::ZipLocalConsumer,1,IUnknown> *,win_scope::const_policies<win_scope::types_6<win_scope::close_com,win_scope::convert_normal,win_scope::acquire_com,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::safe_types_com>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>> &,win_musl::ByteReceiverUnique<win_musl::consumption::ZipLocalConsumer,1,IUnknown> *)
0x180012c67  mov     r9, [r15+8]
0x180012c6b  mov     qword ptr [rsp+3A0h+var_378], rdi
0x180012c70  lea     rax, [rsp+3A0h+var_360]
0x180012c75  mov     qword ptr [rsp+3A0h+var_380], rax
0x180012c7a  mov     r9d, [r9+50h]
0x180012c7e  lea     r8, [rbp+2A0h+var_268]
0x180012c82  lea     rdx, [rsp+3A0h+var_348]
0x180012c87  mov     rcx, r14
0x180012c8a  mov     rax, rsi
  ... truncated ...
```
